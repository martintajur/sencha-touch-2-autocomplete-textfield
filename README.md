Sencha Touch 2 Autocomplete Textfield
=====================================

Usage
-----

AJAX driven autocomplete field inside a fieldset:

```
{
	xtype: 'autocompletefield',
	label: 'Person',
	value: '',
	config: {
		proxy: {
        	type: 'ajax',
        	url: 'https://api.example.com/search',
        	reader: {
        		type: 'json',
        		rootProperty: 'results'
        	}
        },
        resultsHeight: 300,
		needleKey: 'term',
		labelKey: 'name'
	}
}
```


How does it work?
-----------------

It uses a regular textfield for text entry, then performs an AJAX request with the ```needleKey``` and uses the ```labelKey``` field from the results model. The proxy config you see in the example uses the standard ExtJS store proxy configuration syntax.

It then displays the results from the AJAX request response in a List below the textfield, allowing the user to select an existing item from the results.


Full example
------------

```
Ext.create('Ext.Container', {
	fullscreen: true,
	items: [{
		xtype: 'fieldset',
		items: [
			{
				xtype: 'emailfield',
				label: 'Name',
				value: 'asd'
			},
			{
				xtype: 'autocompletefield',
				label: 'Person',
				value: '',
				config: {
					proxy: {
			        	type: 'ajax',
			        	url: 'https://api.example.com/search',
			        	reader: {
			        		type: 'json',
			        		rootProperty: 'results'
			        	}
			        },
			        resultsHeight: 300,
					needleKey: 'term',
					labelKey: 'name'
				}
			},
			{
				xtype: 'autocompletefield',
				label: 'Organization',
				value: '',
				config: {
					proxy: {
			        	type: 'ajax',
			        	url: 'https://api.example.com/search',
			        	reader: {
			        		type: 'json',
			        		rootProperty: 'results'
			        	}
			        },
			        resultsHeight: 300,
					needleKey: 'term',
					labelKey: 'name'
				}
			}

		]
	}]
});
```

Licence
=======

MIT Licence.