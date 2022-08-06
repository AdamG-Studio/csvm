# csvm
An idea for a command line tool I would like to have. csvm name might already exist, this is just a temporary name.

NAME         csvm
       csvm - tool for manipulating csv files
              
COMMAND-LINE Options

       -h | -v  :Help/Version
            Show csvm version and the usage prompt, then quit.

       -log-level :Log levels: debug | normal
            Optional. Default normal.
            
       -di  :Delimiter for input files: ; | : | ,
            
       -do  :Delimiter for output files: ; | : | ,
            
       -i  :Input files. Requires all files to have correct headers.
            Specify input files as a single file or multiple files: file1.csv file2.csv ...

       -oc :operation as:  c | m | d :
            Copy, Move or Delete columns. Examples:
            csvm -i file -oc c 3 5,6 - Example copy column 3 to between columns 5 and 6. If the last column is specified it will be copied to the end.
            csvm -i file -oc m 3 5,6 - Example move column 3 to between columns 5 and 6.
            csvm -i file -oc d 3 - Example delete column 3.
            
       -or :operation as:  c | m | d
            Copy, Move or Delete rows. Examples:
            csvm -i file -or c 3 5,6 - Example copy row 3 to between rows 5 and 6. If the last row is specified it will be copied to the end.
            csvm -i file -or m 3 5,6 - Example move row 3 to between rows 5 and 6.
            csvm -i file -or d 3 - Example delete row 3.

