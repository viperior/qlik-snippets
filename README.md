# qlik-snippets
A library of useful Qlik subroutines that automate common tasks, support templating, and speed up the development of ETL pipelines

## First-time setup
1. Download the repository to a location that is accessible from your Qlik Sense Enterprise server.
2. Create a new data connection in Qlik Management Console (QMC).
3. Copy the following code to a Qlik script and replace {FileName} with the name of the subroutine or snippet you want to use.

   ```$(Must_Include=lib://Qlik Utility Library/{FileName}.qvs);```

   Some subroutines have code that does not execute until called:
  
   ```Call ProfileTableFieldValues('Source Table Name', 'Output Table Name');```

## ProfileTableFieldValues Subroutine
This subroutine performs automated analysis of a table's field values.

### Usage

1. Copy the following code to the end of your Qlik script:

   ```
   $(Must_Include=lib://Qlik Utility Library/ProfileTableFieldValues.qvs);
   Call ProfileTableFieldValues('Source Table Name', 'Output Table Name');
   ```

2. Reload the script and check the data model viewer. You should see your new table.
