<h2> Nmap </h2>

| Command | Usage                                                                                                | Writtenas   |
| ------- | ---------------------------------------------------------------------------------------------------- | ----------- |
| \-p     | Used to scan a set of ports whether it is on a local or remote server.                                | nmap \-p    |
| \-sT    | It is used to scan open ports and can work with the TCP protocol without any problems. | nmap \-sT   |
| \-p \-n | Used to disable DNS to speed up scans.                                                               | nmap –p \-n |
| \-sp    | It is used to scan the ping command.                                                                     | nmap -sp    |

<h3> Command to scan Nmap ports by using this command, a port, or a set of ports can be scanned whether it is on local or remote servers depending on your configuration. As we can see from the image below, we have scanned 20 ports on the local host computer.</h3>

Nmap -p 1-65535 localhost

<h3> Nmap Ping Scan When you want to perform a ping scan on any existing network to discover the host, this command is the most commonly used and popular command to do so. </h3>

Nmap –sp 192.168.5.0/24


<img src="https://github.com/user-attachments/assets/ac48fc9a-9a2d-4cdb-9232-6c96ebcfb27f" width="700">

<h3> Host and IP address scan with Nmap Nmap Scan Against Host and IP Address We used this command as a method of scanning either the IP address or hostname, as shown in the picture below.</h3>

nmap 1.1.1.1


<img src="https://github.com/user-attachments/assets/91f1c9e5-d05b-4bc7-ae27-079d00d80fb3" width="700">


<h3> Nmap scan of multiple IP addresses Multiple IP Address Scan Using this command, we can scan multiple IP addresses simultaneously, which is a very useful feature when scanning multiple addresses at once.</h3>

nmap 1.1.1.1 8.8.8.8

<h3> DNS Name Resolution Disabled Using Nmap Disabling DNS Name Resolution, this command aims to speed up the scans, if there are a lot of scans that need to be performed. To achieve this, we had to disable the reverse DNS to speed up the scans. The SSH port was filtered. </h3>

map -p 80 -n 8.8.8.8

<img src="https://github.com/user-attachments/assets/78be7930-b07a-4103-aa9d-a91944cae5a2" width="700">

<h3> Using TCP for scanning Nmap can scan open ports and can work with the TCP protocol without any issues, so when we used this command as shown in the picture, here was the output that we got when using standard TCP to scan ports.</h3>

map-sT 192.168.1.1


<img src="https://github.com/user-attachments/assets/8e8c3767-0d79-417b-92e5-426745c624a2" width="700">



<h3> Nmap results and analysis: </h3> 

- Scanning ports (open and close)
- Opening of a closed port to an open port

<h2> SQLmap </h2>

| Command         | Usage                                                                          | Written as             |
| --------------- | ------------------------------------------------------------------------------ | ---------------------- |
| \--wizard       | Help new users by providing an interface to help to get familiar with the tool | sqlmap –wizard         |
| \-u             | Include vulnerable query parameters in the target URL                          | sqlmap \-u             |
| \--purge        | Used to clear the entire database folder                                       | sqlmap \-purge         |
| \--dependencies | Used to detect any missing dependencies                                        | sqlmap\-\-dependencies |
| \-d direct      | Used for the direct connection with the database                               | sqlmap\-d              |



<h2> Hydra </h2>

| Command | Usage                                                                | Written as |
| ------- | -------------------------------------------------------------------- | ---------- |
| crunch  | Generator used to specify the number of characters that will be used | $ crunch   |
| \-p     | Used as a password list                                              | \-p        |
| \-l     | Used as login                                                        | \-l        |

Brutal force attack was used in this tool

<img src="https://github.com/user-attachments/assets/626a6928-b50b-4f8d-89ff-abb99048c515" width="700">

<h3>Password.text</h3>

<img src="https://github.com/user-attachments/assets/a6db0504-d154-452f-8132-cec928ec752d" width="700">

<img src="https://github.com/user-attachments/assets/0f02eaff-ab4e-448d-94c5-3d584f7a6f39" width="700">

<h3>We selected User.text and Password.text and the chosen target which is ssh//71.46.236.250, a server port identified from Nmap. Nmap revealed open and closed ports. Despite the address being closed, we reopened it in Nmap, used Hydra to start the attack with the command below.</h3>

The attack succeeded, and we retrieved passwords from the server ssh//71.46.236.250.

<h3>We attempted to log in with the username “asma112” using Password.text, and Hydra started guessing the password. It tested the password “asma112” (the same as the username) and the reversed version “211amsa” until a match was found.</h3>

<pre>Hydra -l user.text -p password.text ssh://71.46.236.250 -v</pre>

<h3>We successfully opened the closed port ssh//71.46.236.250.</h3>

<img src="https://github.com/user-attachments/assets/ab00865e-00bb-4b1c-9cf5-3098ac513445" width="700">
