# API Parameters

There are many parameters accepted by the CiviCRM API. Most parameters
depend on the entity – for current details in your see the [API Explorer]
and the [API examples]. However, some parameters are particularly dynamic or
generic; these may not be explained well by the auto-generated
documentation. The format for passing options as parameters using the
REST interface is explained at [REST
interface\#optionsparameters](https://wiki.civicrm.org/confluence/display/CRMDOC/REST+interface#RESTinterface-optionsparameters).

[API Explorer]: /api/general/#api-explorer
[API examples]: /api/general/#api-examples

## sequential

-   **Action**: get
-   **Type**: bool
-   **Default**: FALSE
-   **Compatibility**: ??
-   **Description**:

Determine whether the returned records are indexed sequentially (0, 1, 2, ...)
or by ID.

Example without sequential:

```php
$result = civicrm_api('UFMatch', 'get', array(
  'version' => 3,
  'uf_id' => $user->uid,
));
$contactId = $result['values'][$result['id']]['contact_id'];
```

Example with sequential:

```php
$result = civicrm_api('UFMatch', 'get', array(
  'version' => 3,
  'uf_id' => $user->uid,
  'sequential' => 1,
));
$contactId = $result['values'][0]['contact_id'];
```

Note that a single record is returned in this example - whenever a single
record is returned the `entity_id` of that record should be in `$result['id']`


## options.limit

-   **Action**: get
-   **Type**: int
-   **Default**: 25
-   **Compatibility**: ??
-   **Description**:

The maximum number of records to return

Example:

```php
civicrm_api('UFMatch', 'get', array(
  'version' => 3,
  'uf_id' => $user->uid,
  'options' => array(
    'limit' => 25,
  ),
));
```


## options.offset

-   **Action**: get
-   **Type**: int
-   **Default**: 0
-   **Description**:

The numerical offset of the first result record

Example:

```php
civicrm_api('UFMatch', 'get', array(
  'version' => 3,
  'uf_id' => $user->uid,
  'options' => array(
    'limit' => 25,
    'offset' => 50,
  ),
));
```

## options.sort

-   **Action**: get
-   **Type**: ??
-   **Default**: ??
-   **Parameters**: field name, order (ASC / DESC)
-   **Description**:

The criterion to sort on

Example

```php
civicrm_api3('Contact', 'get', array(
  'sequential' => 1,
  'return' => "contact_type",
  'options' => array('sort' => "contact_type ASC"),
));
```

## options.reload

-   **Action**: create
-   **Type**: bool
-   **Default**: FALSE
-   **Compatibility**: v4.4+
-   **Description**:

Whether to reload and return the final record after the saving process
completes.

Example:

```php
civicrm_api('Contact', 'create', array(
  'version' => 3,
  'contact_type' => 'Individual',
  'first_name' => 'First',
  'last_name' => 'Last',
  'nick_name' => 'Firstie',
  'options' => array(
    'reload' => 1,
  ),
));
```

## options.match

-   **Action**: create | replace
-   **Type**: string | array
-   **Default**: NULL
-   **Compatibility**: v4.4+
-   **Description**:

Attempt to update an existing record by matching against the specified
field.

-   If **one** matching record already exists, then the record will be
    **updated**.
-   If **no** matching record exists, then a new one will be **inserted**.
-   If **multiple** matching records exist, then return an **error**.

Example:

```php
civicrm_api('Contact', 'create', array(
  'version' => 3,
  'contact_type' => 'Individual',
  'first_name' => 'Jeffrey',
  'last_name' => 'Lebowski',
  'nick_name' => 'The Dude',
  'external_identifier' => '1234',
  'options' => array(
    'match' => 'external_identifier',
  ),
));
```

## options.match-mandatory

-   **Action**: create | replace
-   **Type**: string | array
-   **Default**: NULL
-   **Compatibility**: v4.4+
-   **Description**:

Attempt to update an existing record by matching against the specified
field.

-   If **one** matching record already exists, then the record will be
    updated.
-   If **no** matching record exists, then return an **error**.
-   If **multiple** matching records exist, then return an **error**.

Example:

```php
civicrm_api('Contact', 'create', array(
  'version' => 3,
  'contact_type' => 'Individual',
  'first_name' => 'Jeffrey',
  'last_name' => 'Lebowski',
  'nick_name' => 'The Dude',
  'external_identifier' => '1234',
  'options' => array(
    'match-mandatory' => 'external_identifier',
  ),
));
```


## Custom Data

Custom data attached to entities is referenced by `custom_N` where `N` is
the unique numerical ID for the custom data field.

To set a custom field, or find entities with custom fields of a
particular value, you typically use a parameter like this:

```php
$params['custom_N'] = 'value';
```

To return custom data for an entity, you typically pass a param like the
following:

```php
$params['return.custom_N'] = 1;
```

*or (depending on which API entity you are querying)*
```php
$params['return'] = 'custom_N';
```

*or*
```php
$params['return'] = 'custom_N,custom_O,custom_P';
```

For setting custom date fields, (ie CustomValue create), date format is
`YmdHis`, for example: `20050425000000`.

This is just a brief introduction; each API may have different requirements
and allow different formats for accessing the custom data. See the
[API function documentation](https://wiki.civicrm.org/confluence/display/CRMDOC/Using+the+API)
and also read the comments and documentation in each API php file
(under civicrm/CRM/api/v3 in your CiviCRM installation) for exact details,
which vary for each API entity and function.

For more details and examples,
[see the tutorial on using custom data with the API here](https://wiki.civicrm.org/confluence/display/CRMDOC/Using+Custom+Data+with+the+API).
