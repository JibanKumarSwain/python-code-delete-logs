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



## Run the script the file " chmod +x check_permissions.sh "

