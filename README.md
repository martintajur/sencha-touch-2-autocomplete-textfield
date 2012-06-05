Sencha Touch 2 Autocomplete Textfield
=====================================

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