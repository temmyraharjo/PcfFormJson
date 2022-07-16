
# PCF Form Json

A PCF Component that receives a predefined JSON format string and displays it as a Bootstrap Form. Then, Users can interact with the form and can save the value as a JSON format value.

![PCF Form Json](https://temmyraharjo.files.wordpress.com/2021/04/demo-pcf-form.gif)

## Sample JSON Form string

```javascript
{
    "controls": [
        {
            "name": "name",
            "label": "Name",
            "type": "string"
        },
        {
            "name": "total",
            "label": "Total Amount",
            "type": "number"
        },
        {
            "name": "active",
            "label": "Active",
            "type": "boolean"
        },
        {
            "name": "account",
            "label": "Account",
            "type": "lookup"
        },
        {
            "name": "status",
            "label": "Status",
            "type": "optionset"
        },
        {
            "name": "birthdate",
            "label": "Birthdate",
            "type": "date"
        },
        {
            "name": "numbers",
            "label": "Numbers",
            "type": "checkbox"
        },
        {
            "name": "datetime",
            "label": "DateTime",
            "type": "datetime"
        }
    ],
    "lookupMetadata": {
        "account": {
            "allowMultiSelect": true,
            "defaultEntityType": "account",
            "defaultViewId": "",
            "entityTypes": [
                "account",
                "contact"
            ],
            "viewIds": []
        }
    },
    "optionSetMetadata": {
        "status": [
            {
                "label": "Active",
                "value": 1
            },
            {
                "label": "Inactive",
                "value": 2
            }
        ],
        "numbers": [
            {
                "label": "1",
                "value": "one"
            },
            {
                "label": "2",
                "value": "two"
            },
            {
                "label": "3",
                "value": "three"
            },
            {
                "label": "4",
                "value": "four"
            },
            {
                "label": "5",
                "value": "five"
            }
        ]
    }
}
```

Supported data types:  

- String with type: 'string'
- Lookup with type: 'lookup'
- Number with type: 'number'
- Boolean with type: 'boolean'
- Date with type: 'date'
- DateTime with type: 'datetime'
- OptionSet with type: 'optionset' (You should define optionSetMetadata)
- Checkbox with type: 'checkbox' (You should define optionSetMetadata)

## Sample JSON Result

```javascript
{
    "name": "Temmy",
    "total": 200000,
    "active": true,
    "account": [
        {
            "id": "96EF3EA2-2B77-E511-80DB-00155DFD1F02",
            "etn": "account",
            "name": "Temmy Wahyu Raharjo"
        }
    ],
    "status": 1,
    "birthdate": "2021-05-20",
    "numbers": [
        "one",
        "two",
        "three"
    ],
    "datetime": "2021-05-19 20:00"
}
```

## Solutions

You can download the solution in Release folder (Managed + Unmanaged available).

## How to Install

Install the zip (unmanaged or managed) that you can find in the Release Tab.

On the string (Single Text or Multiline Text) you can go the Field Properties > Controls > Json Form Component (If you not find it, you need to Add Control). This will help you to bind this attribute to the property _**String Property**_ or the result attribute.

![PCF Form Json Properties](https://temmyraharjo.files.wordpress.com/2021/05/add-control.png)

This PCF Form needs 2 string parameters to run:

- _**String Property**_ to define the result of the JSON Form after being saved (look for **Sample JSON Result** string for the result).
- _**Control Form Json**_ to define the form metadata (look for **Sample JSON Form String** section to define the string).

Then for _**Control Form Json**_ you need to set it to another attribute (as long as string data type) or you can bind it with static string value:

![Control Form JSON settings](https://temmyraharjo.files.wordpress.com/2021/05/control-form-json-attribute.png)

Remember, you can't set the _**String Property**_ attribute same as _**Control Form Json**_ attribute
