# SeniorResearch
My senior research project based on public key encryption written in python 3 in a linux os

First download all the encryption files and save them to one directory on each computer

Then set up ftp on both computers by:

	sudo apt-get install vsftpd
 	sudo apt-get install xinetd
	sudo apt-get install ftp
  in 
	
	sudo nano /etc/vsftpd.conf 
  change 
	
	listen = YES
   to 
	 
	listen = NO
			
  In the file:
	
	sudo nano /etc/xinetd.d/vsftpd
  write:
   
   	service ftp
        {
          disable                 = no
          socket_type             = stream
          wait                    = no
          user                    = thisComputersUserName
          server                  = /usr/sbin/vsftpd
          per_source              = 5
          instances               = 200
          banner_fail             = /etc/vsftpd.busy
          log_on_success          += PID HOST DURATION
          log_on_failure          += HOST
        }
exit to command line then type:	
				
  	sudo service vsftpd stop
  	sudo service vsftpd start
  	sudo add userNameOfOtherComputer
  in the file :
	
	sudo nano /etc/passwd
write/change:

	jfkdlsa
 Exit to command line, then type 
 
	sudo passwd userNameOfOtherComputer
  	passWordOfOtherComputer
  in the file:
		
	sudo nano ~/.bashrc
   write in 
   
	 alais encrypt = 'echo "your path is " ; pwd; cd / home/pathToEncryptionFile ; p$n2 calledAction.py; cd -'
