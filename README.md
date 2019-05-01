# SWIMMER
Statistical Workflow for Identification of Molecular Modulators of ribonucleoprotEins by Random variance modeling

the sg raw data analysis script analyzes a screen run on a single cell type, and ideally all the plates of the screen tested on the same day

-data (such as qualified granule area/qualified nuclear area) need to be arrayed in a csv in the following format:
a. each plate of data should reside in a single column, and each data point on the plate is entered into this column on a row by row fashion (e.g. for a 384 well plate, A1 through A24 are in the first 24 rows of the data column, then B1 through B24).  each column therefore contains a separate plate of data
b. the first biological replicate set of plates should be listed in the first few columns; after that the second biological replicate set of plates should be listed, etc (for example, a screen with 3 plates A, B, and C, and 2 biological replicates 1, 2, should be listed in columns as follows: A1, B1, C1, A2, B2, C2)
c. the block of data should have the upper left hand corner in the 5th row, 2nd column

-enter the filepath for the above csv file containing the data, in the cell below the heading “ENTER PATH OF DATA FILE HERE:”

-adjust analysis parameters in the cell below the heading “CHANGE ANALYSIS PARAMETERS HERE:”
a. under “PLATES,” write down the total number of plates (counting replicate plates)
b. change "PLATE_ROWS" and "PLATE_COLS" if doing 96 vs 384 well plates
c. change "NUM_REPL" to show number of replicates for the screen library
d. adjust the “LASTROW” value if doing 96 well plates or 384 well, etc (remember to add 1 for correct numpy indexing)
e. adjust the “LASTCOLUMN” value depending on the number of total plates entered into the “PLATES” variable (remember to add 1 for correct numpy indexing)
f. change the MAD “THRESHOLD” and “SIGMA” for more or less stringent hit cutoffs

-change name of the output file to directory and name as needed, in the cell below the heading “GIVE NAME OF ANALYSIS OUTPUT FILE:”

-change name of the parameters output file to directory and name as needed, in the cell below the heading “GIVE NAME OF ANALYSIS PARAMETER FILE:”

-run program



troubleshooting:
watch out for hidden cells with DIV0 excel error; these need to be replaced with blank cells.  to see which row threw the DIV0 error, check the python traceback (e.g. line xxx gave m columns, expected n columns)
