# python-code-delete-logs
Delete 3 days old logs
        
   
__________________________________________________________________________________________________________________________________________________
               
import os                                                           
                                      
import time                            
                          
current_time = time.time()   
   
three_days_ago = current_time - (3 * 24 * 60 * 60)    

for file in os.listdir("/path/to/your/logs"):

    file_path = os.path.join("/path/to/your/logs", file)
    
    if os.path.getmtime(file_path) < three_days_ago:
    
        os.remove(file_path)




___________________________________________________________________________________________________________________________________________________


  
## Run the script the file 
 " chmod +x check_permissions.sh  "  
 " ./check_permissions.sh /path/of/your/filename.txt"




# Chack the permission of any file

#!/bin/bash

# Check if a filename is provided
if [ $# -ne 1 ]; then
    echo "Usage: $0 <filename>"
    exit 1
fi

# Get the filename from the command line argument
filename=$1

# Check if the file exists
if [ ! -e "$filename" ]; then
    echo "File '$filename' does not exist."
    exit 1
fi

# Check write permission
if [ -w "$filename" ]; then
    echo "The file '$filename' has write permission."
else
    echo "The file '$filename' does not have write permission."
fi

# Check read permission
if [ -r "$filename" ]; then
    echo "The file '$filename' has read permission."
else
    echo "The file '$filename' does not have read permission."
fi

# Check execute permission
if [ -x "$filename" ]; then
    echo "The file '$filename' has execute permission."
else
    echo "The file '$filename' does not have execute permission."
fi
 
