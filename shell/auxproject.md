So we will create a shell script that reads a csv file that contains the first name of the users to be onboarded.
In this project, I need to onboard 20 new Linux users onto a server using a shell script.

Create the project folder called Shell and cd into the folder

mkdir cd shell && cd shell

Create a csv file name names.csv

touch names.csv $$ vim names.csv

Insert the names of the 20 new users

Create the developers group

sudo groupadd developers

create a file for the public key

 touch id_rsa.pub && vim id_rsa.pub

 
create a file for your private key

touch id_rsa && Vim id_rsa

Copy and paste the private and public keys from the project documentation into the respective files

Create a file onboard.sh and vim into it

write the shell script that will  do the following

1. This script will read a CSV file that contains 20 new Linux users.
2. This script will create each user on the server and add to an existing group called 'Developers'.
3. This script will first check for the existence of the user on the system, before it will attempt to create that it.
4. The user that is being created also must also have a default home folder
5. Each user should have a .ssh folder within its HOME folder. If it does not exist, then it will be created.
6. For each user’s SSH configuration, We will create an authorized_keys file and add the below public key.

Run the script to create the 20 new users as a root user using this command

./onboard.sh


Output ![users](USERS.png)

Then from aa differnt terminal, using Gitbash, use different users to connect to the server thus 
ssh -i "mauxproject.pem" Buharu@ec2-3-91-64-202.compute-1.amazonaws.com


![users](user1.png)


![user2](user2.png)

However before running the above command to connect, open a new terminal. I used Gitbash. Create a file and vim into the file
vi mauxproject.pem

Copy and paste and save the public key in the file.
Next run a chmod command to cjange the permissions on the key. 

chmod 400 mauxproject.pem



![user3](user3.png)