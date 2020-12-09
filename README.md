# linux-commands-to-perform-different-tasks

1. Set a cron to print your name in a file which runs after every 2 minutes

Ans: vi /etc/crontab     #edit cronjob file
*/2 *   * * *    username   echo "Any Message" >> filename.txt    #cronjob
crontab /etc/crontab   #load cronjob

2. Add three users alan , james & sofia out of which two users should belong to Admin group 
and 1 user should belong to IT group

Ans: useradd -m Alan   #add user 
useradd -m James 
useradd -m Sofia 
groupadd admin    #add group
groupadd IT 
usermod -aG admin Alan    #add user to group
usermod -aG admin James
usermod -aG IT Sofia
awk -F: '{print $1}' /etc/passwd     #view all usernames only
cat /etc/group | grep admin          #find group admin

3. Find a file using " grep " which contains word "defaults " in /etc/ directory 

Ans: grep -l -r "defaults" /etc/* 

5. Run a single command to save the top 30 lines of syslog to a file called separate_logs 
(note file should not be created first only single command will do whole task )

Ans: head -n 30 /var/log/syslog >> seperate_logs.txt

6. Run a single command to append last 30 lines of auth log in a file called separate_logs  

Ans: tail -n 30 /var/log/auth.log >> seperate_logs.txt

9. Search which flag can show inverted output in grep command and which flag to be used if 
user want the line number of matched string of the file

Ans: -n Prints the line number of output.
-v invert

10. Run a single command to print the disk space size of your drive which is mounted on / 
(output of this command should be a single line only the size of your filesystem )   

Ans: df -ht ext4 >> home/talha/mountLog.txt

11. Set hostname of your VMs in your virtualbox 
(hostname should contain your name and it should be pingable)

Ans: vi /etc/hostname
vi /etc/hosts
sudo reboot

13. Create a text file and set it permission that owner has full rights and other user 
have only read rights

Ans: cat > 123.txt
chmod 744 123.txt
ls -la 123.txt

14. Virtual box VM should resolve facebook.com to 192.168.10.1

Ans: vi /etc/hosts   #add facebook.com against given ip 
sudo reboot

15. Virtual box VM should run ssh on 52 port

Ans: #first install ssh client on your os/vm
vi /etc/ssh/sshd_config
