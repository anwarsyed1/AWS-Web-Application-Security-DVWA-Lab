<h1>AWS Web Application Security on DVWA (Damn Vulnerable Web Application)</h1>

<img src="https://imgur.com/omzPnOv.png" height="80%" width="80%" alt="diagram"/>
<img src="https://imgur.com/Qmdmzyu.png" height="80%" width="80%" alt="diagram"/>

<h2>Description</h2>
In this project, I setup an EC2 Instance on AWS with an HTTP server running on port 80. We then use docker to dock the server on a Kali Linux terminal to host the sever. Lastly we use DVWA to test vulnerabilities This is a step by step guide so feel free to follow along! 
<br />


<h2>Languages and Utilities Used</h2>

- <b>Bash</b> 

<h2>Environments Used </h2>

- <b>Oracle VirtualBox</b>
- <b>DVWA</b>
- <b>AWS</b>
- <b>Kali Linux</b>

<h2>Program walk-through:</h2>

<p align="center">
First we will create an Amazon EC2 Instance with SSH and HTTP (Port 80) running: <br/>
<img src="https://imgur.com/hKzlcnW.png" height="80%" width="80%" alt="set up"/>
<br />
<br />
Then we will start our Kali Linux VM via VirtualBox:  <br/>
<img src="https://imgur.com/W52mjHy.png" height="80%" width="80%" alt="set up"/>
<br />
<br />
I used my key pair to ssh into the ec2 public ipv4 address: <br/>
<img src="https://imgur.com/aHpu2HN.png" height="80%" width="80%" alt="set up"/>
<br />
<br />
Then I updated yum and installed docker, yum is a package in linux that manages dependencies:  <br/>
<img src="https://imgur.com/A5kouXv.png" height="80%" width="80%" alt="set up"/>
<br />
<br />
I started the docker service then ran the DVWA on the server:  <br/>
<img src="https://imgur.com/xBeH4JC.png" height="80%" width="80%" alt="set up"/>
<br />
<br />
Now we can search the public DNS that was given on AWS and sign in using the defult credentials, Username:"admin" Password:"password":  <br/>
<img src="https://imgur.com/ngY91LM.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Now we will click on DVWA Security and make the vulnerability level to low, and then click Command Execution :  <br/>
<img src="https://imgur.com/OXhNgKc.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://imgur.com/SKwgqil.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://imgur.com/K3Su883.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Then created another if statement to verify if the firstname and lastname match with the corresponding sin. If successfull return status 200 (OK) with the mediacal record and a JSON message, else return an error JSON message with status 401 (unauthorized):  <br/>
<img src="https://imgur.com/bGWNHPr.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
:  <br/>
<img src="https://imgur.com/INiv9Ii.png" height="80%" width="80%" alt="Cyber Attack Event Management"/>
<br />
<br />
For the next function, We will use the POST method to create a new patient we want to be able to assert a new patient from the header to the database. So if the patients sin match equals the firstname, lastname, and phone. then add the patient to the database with a status 200 (OK):  
<br/>
<img src="https://imgur.com/W5alK8v.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Next create a funtion for updating a patients phone number, we need to verify the sin, verify if the first and last name match the sin, then we can use the PUT method to update the phone number and return the updated database in the body:  <br/>
<img src="https://imgur.com/TkkHxBu.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Lastly we will create a funtion to delete patients and medical records, again we need to verify if the patients sin exists in the database, verify if the sin matches with the first and last name, then we are able to delete the patient or records from our database using the DELETE Method. Else return error code with JSON message indicating the credentials don't match the sin on file:  <br/>
<img src="https://imgur.com/vXCpzaR.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />

<br />
This Concludes This REST API for a Medical Clinic Project!
NOTE: You can build on this and add more security layers and conditions as it would be in real life!  <br/>
<br />
</p>

<!--
 ```diff
- text in red
+ text in green
! text in orange
# text in gray
@@ text in purple (and bold)@@
```
--!>
