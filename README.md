# qlik-snippets
A library of useful Qlik subroutines that automate common tasks, support templating, and speed up the development of ETL pipelines

## First-time setup
1. Clone this repository to a location that is accessible to your Qlik Sense Enterprise server:
    * ```git clone https://github.com/viperior/qlik-snippets PATH_TO_UTILITY_SCRIPTS_FOLDER```
2. Create a new data connection in Qlik Management Console (QMC):
    * Name: Qlik Utility Library
    * Type: Folder
    * Path: PATH_TO_UTILITY_SCRIPTS_FOLDER as defined in step 1
3. Congratulations! You're ready to make use of the subroutines in this library.

## Updating
1. ```cd PATH_TO_UTILITY_SCRIPTS_FOLDER```
2. ```git pull```

## GetMaxValue
This subroutine retrieves the maximum value from a field when given a field name and table name.

### Usage
```
[Example]:
Load
    RowNo() AS [Row Number]
Autogenerate(100)
;

Let vTableName = 'Example';
Let vFieldName = 'Row Number';
Let vIncludePath = 'lib://Qlik Utility Library/GetMaxValue.qvs';
$(Must_Include=$(vIncludePath));
Call GetMaxValue(vMaxValue, vTableName, vFieldName);
Let vMessage = 'Max($(vFieldName)) = $(vMaxValue)';
Trace $(vMessage);
// Output: "Max(Row Number) = 100"
```

## ProfileTableFieldValues
This subroutine performs automated analysis of a table's field values.

### Usage

1. Copy the following code to the end of your Qlik script:

    ```
    Let vIncludePath = 'lib://Qlik Utility Library/ProfileTableFieldValues.qvs';
    $(Must_Include=$(vIncludePath));
    Call ProfileTableFieldValues('Source Table Name', 'Output Table Name');
    ```

2. Reload the script and check the data model viewer. You should see your new table.
