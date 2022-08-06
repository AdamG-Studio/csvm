# csvm
An idea for a command line tool I would like to have. csvm name might already exist, this is just a temporary name. If someone can write something like this that would be great.

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

       -oc :accepts:  c | m | d :
            Copy, Move or Delete columns. Examples:
            csvm -i file -oc c 3 5,6 - Example copy column 3 to between columns 5 and 6. If the last column is specified it will be copied to the end.
            csvm -i file -oc m 3 5,6 - Example move column 3 to between columns 5 and 6.
            csvm -i file -oc d 3 - Example delete column 3.
            
       -or :accepts:  c | m | d
            Copy, Move or Delete rows. Examples:
            csvm -i file -or c 3 5,6 - Example copy row 3 to between rows 5 and 6. If the last row is specified it will be copied to the end.
            csvm -i file -or m 3 5,6 - Example move row 3 to between rows 5 and 6.
            csvm -i file -or d 3 - Example delete row 3.
     
       -c  :accepts: -dontcare | -care | -nexttoit
            -dontcare: Doesn't care if headers are correct which might and probably will break the output file.
            -care: Check if columns and headers are correct before operation.
            -nexttoit: puts all columns from one file next to another file.
            Combines multiple files Examples:
            csvm -i file1 file2 -o file3 -c - on its own will put each file under another file and export to file3. Enabled -dontcare by default.
            csvm -i file1 file2 -o file3 -c -nexttoit - on its own will put columns from one file next to columns from another file. Enabled -dontcare by default.
