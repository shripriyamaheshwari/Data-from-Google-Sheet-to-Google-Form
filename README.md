# Data-from-Google-Sheet-to-Google-Form
Populate your data automatically from Google Sheet to Google Form using Google Script Code
## What parameters to change while running the code?
1. In Line 3, Replace the .openById("Your FORM ID") with your customised form id. You can find the form ID from your google form URL. For e.g. the url would look like this "docs.google.com/forms/d/11YhQ3ixxxxxxxxxxxxx/edit". Copy-paste the part after d/ and before /edit.
2. In line 4, replace .getItemById("Your dropdown id") with your customised dropdown id. You can find the dropdown id in your google form by right clicking your desired question and selecting inspect element. Search for "data-item id" using Cltr+F to find the dropdown id for that particular question.
3. In line 10, replace getSheetByName("Your sheet name") with your sheet name you want to populate the data from. Note that give the sheet name (displayed by a tab at the left side on google sheets) and not the document name.
4. In line 13, names.getRange(1, 1, names.getMaxRows() - 1).getValues(), here the first '1' represents the row number. The second '1' represents the column number. In case you want to skip the header row, pass '2' as the first parameter. If you want to populate the data from column B, change it to 2 and so on.
## Step by Step:
1. Create a Google Sheet and populate the data in the order you want your dropdowns to look. Sort it or trim it, if needed. Note that when you populate the data from google sheets to a dropdown, it considers every character as a string. Thus, it would add extra whitespaces to your form if they are present it in your sheet. 
2. Create a Google form and take note of the form id. After creating the questions, note down the "dropdown id" using inspect element as explained above (Point 2).
3. Now that you have your form id along with the drop-down id. Open the script editor by clicking on tools->script editor. You will be directed to a new tab for writing the google script code. Paste the given code and run the "debug" option first to check for any errors.
4. Run the script if debug function gives no error. In case of any errors, make sure the number of rows in the sheet <1000 and also, double check the parameters you've passed.
