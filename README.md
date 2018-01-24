Eric Diep, CS725, Spring 2018

# Tutorial - University Data
## Under "Clean up country names", what other countries had issues with spelling?
I changed the method selection to "nearest neighbor", distance function selection to "PPM", and increased value of radius and/or block chars.
- Netherlands had variations of "Netherlands" or "the Netherlands". 
- United Kingdom had variations of "United Kingdom", "England, United Kingdom", or "Scotland, United Kingdom".
- England had variations of "England" or "England, UK".
- Scotland had variations of "Scotland" or "Scotland, UK".
- Canada had variations of "Canada" or "Canada B1P 6L2".
- Russian Federation had variations of "Russian Federation" or "Russia".

I changed the method selection to "key collision" and key function to "colonge-phonetic".
- Russia had variations of "Rossija" or Russia


## Under "Clean up values for the endowment", report the number of entries that used the term "million" or "Million" in the endowment column. Also report the number that used the word "billion" or "Billion".
- 1379 entires used the term "million" or "Million" in the endowment column.
- 18922 entries used the term "billion" or "Billion" in the endowment column.

## Under "Finding issues in other columns", identify and report on issues that you find in at least one other column (other than the country column shown in the tutorial).
- In the established column, there are 6233 entries contains more than just a year of establishment. Within the 6233 entries, there are entries that are in date format, or contains a year and a message.

## Under "Exploring the data with scatter plots", export the endowment(x) vs. numStudents(y) plot, save it into your Gitlab project, and insert the image into your project README.md. Is there a correlation between endowment and number of students?
![alt text](EndowmentVsNumStudent.png)
- I did not find any correlation between the number of students and the amount for endowment. There is no correlation between number of students and the amount for endowment because I found 2 entries where the number of students were 28 and 44, and the listed endowment 700 million and 5.27 billion, respectively.

## After completing the "Geocoding names and addresses" section, export your cleaned data file as a CSV (comma-separated value) file and add this file to your Gitlab project. How many rows did you end up with?
- I ended up with 61 entires.

# Is the 27 Club Real? 
After my analysis and research, I found there were 25 entries where musicians died at the approximate age of 27.

After creating a project and uploading the Musician Excel file. For my analysis of the data, I first created a cluster on the name of the artist to check 
if there was any artist that had different formats for their name. I went through the different clustering methods, and keying functions to clean up as much 
of the musician's name as possible. When performing the cluster and edit, I noticed a musician can have multiple records. I decided to dedupilcate the records. 
I sorted the records according to the name of the artist, and reordered the list. Then I used the selection blank down to remove duplicate names. Afterwards, 
I used a custom facet on the name column to search for the entries where the name is now blank. When I found the entries with blank in the name field, 
I selected to remove all entries where the name field was blank.

After cleaning up the artists' name and deduplicating the records, I had to clean up the birth date fields and death date fields. For all of the fields, I first
converted the field to text, then converted them to date. Convert the fields to text ensure scenarios where only a year is provided is converted from numeric to text;
when converted to date January 1st would be used. For some of the the date fields, I had to use the timeline facets to check if there were any entries that did not contain
a date. I noticed there were some entries that had non-time data, so I attempted to clean it up. I could not think of a way or find a way to replace lines of text with a blank.
Thus, I only replaced "null" with a blank.

Finally, with the data as clean as I could get it, I created two additional columns. One column contains the first encountered birth date from the 3 birth date fields.
The other column contains the first encountered death date from the 3 death date fields. Then I created two more columns, each which contained the birth year and death year.
Lastly, I created a column which calculated approximate age from the birth year and death year column. Before creating the last column, I had to convert the birth year and death year
column to numeric first to allow for calculation. 

To find the artists where their approximate age of death is 27, I created a text facet on the approximate age column. Then I selected the entry for 27. This displayed the 25 entries for artists
where their approximate age of death is 27.

