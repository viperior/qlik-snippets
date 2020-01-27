# ProfileTableFieldValues Subroutine
This subroutine performs automated analysis of a table's field values.

## Usage
1. Create a new section named "ProfileTableFieldValues Subroutine" in your script.
2. Copy/paste the subroutine into this new section.
3. Ensure that this section is placed somewhere above where you want to first call it.
4. Place the following code on a line by itself, somewhere after the table you want to analyze has been loaded:

   `Call ProfileTableFieldValues('Name Of Table You Want To Analyze', 'Name For Results Table')`

5. Reload the script and check the data model viewer. You should see your new table.
