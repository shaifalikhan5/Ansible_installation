### **installation of ansible on ubuntu & centos**

## **step 1.**

**    **update all the machine 
    in ubuntu we run**

```

 sudo apt update
```
    
**on centos we run**

```
sudo yum update all
```
![img 1](/images/ansible1.PNG)

on centos machine we run the command


```
 sudo yum upade * -y
```
![img 2](/images/ansible2.PNG)

## **step2**

install ansible on only ansible server
```
sudo apt update
```
```
sudo apt install software-properties-common -y
```
```
sudo add-apt-repository --yes --update ppa:ansible/ansible
```
```
sudo apt install ansible -y
```
![img 3 ](/images/ansible3.PNG)

## **step3**
create a user(shaif) on each machine ansible server as well as nodes 
## command is
```
sudo adduser shaif
```

![img 4](/images/ansible4.PNG)

## **step 4**

go to the ssh configuration file and do two changes this process done all the machines like server as well as nodes like that showing in this image
![img 5](/images/ansible5.PNG)
![img 5](/images/ansible6.PNG)

## **step 5**

restart the sshd service command is
"sudo systemctl restart sshd"
![img 7](/images/ansible7.PNG)
## **step 6**

when we login this shaif user and try to install or update it shows that it has no writes so we shall give permission to this user to do activity we go to            ## 
** "sudo visudo" files and do chenges which are shown in below images
![img ](/images/ansible14.PNG)

![img ](/images/ansible8.PNG)
## **step7**
now we login shaif user and try to update and install it can easily do 
![img ](/images/ansible9.PNG)
![img ](/images/ansible10.PNG)
## **step8**
when we logout and again login from this shaif user to nodes each and every time it ask password to overcome this problem we create a key pair on ansible server and paste public key to all the nodes
![img ](/images/ansible11.PNG)
## **step 9**

now i want to ping this nodes from server to verify it response or not
![img ](/images/ansible12.PNG)
```
ansible -m ping -i host all
```
it shows unable to purse /home/shaif/host as an inventory source
## **step 10**
now we create an inventory
host file
```
"sudo vi /home/shaif/host"
```
here we put private ip of all the nodes and save and exit see in step 9 image 
## **last step**
now try to ping this time i am succes to ping all the nodes
```
ansible -m ping -i host all
```

![img ](/images/ansible13.PNG)

