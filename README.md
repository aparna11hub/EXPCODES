Q. Create a directory named project, navigate into it, create a file data.txt, write "Linux Practical" into it, display its contents, then create a copy named backup.txt and list all files with detailed information.

mkdir project
cd project
touch data.txt
echo "Linux Practical" > data.txt
cat data.txt
cp data.txt backup.txt
ls -l

Q. Create a file secure.txt and set permissions such that: •	Owner → Read, Write, Execute  •	Group → Read and Write  •	Others → No permissions Verify the permissions using a command.

touch secure.txt
chmod 760 secure.txt
ls -l secure.txt

Q. Display all running processes, identify any one process, and terminate it using its PID. Also display real-time system performance.

ps -ef
top
ps -ef | tail
kill <PID>

Q. Write a shell script that accepts a number from the user and displays whether the number is positive, negative, or zero. Execute the script.

nano check.sh

#!/bin/bash
echo "Enter a number:"
read num
if [ $num -gt 0 ]
then
echo "Positive"
elif [ $num -lt 0 ]
then
echo "Negative"
else
echo "Zero"
fi

chmod +x check.sh
./check.sh

Q. Display your system’s IP address, check connectivity with google.com, and display all active network connections on your system.

ip addr
ping google.com
netstat -tuln

(if not installed , sudo apt install net-tools or ss -tuln )

Q. Install and start an Apache web server, create a simple webpage displaying "Welcome to Linux Server", and verify it in a web browser using your system IP.

sudo apt update
sudo apt install apache2 -y
sudo systemctl start apache2
sudo systemctl status apache2
sudo nano /var/www/html/index.html

<html>
<body style="margin:0;font-family:Arial;background:#f4f6f8;">

<div style="background:#2c3e50;color:white;text-align:center;padding:25px;">
<h1>Welcome to My Website</h1>
<p>A simple webpage example</p>
</div>

<div style="background:#444;text-align:center;padding:8px;">
<a href="#" style="color:white;margin:10px;">Home</a>
<a href="#" style="color:white;margin:10px;">About</a>
<a href="#" style="color:white;margin:10px;">Contact</a>
</div>

<div style="padding:25px;text-align:center;">
<h2>Hello!</h2>
<p>This is a small webpage built using HTML, CSS, and JavaScript.</p>

<button onclick="alert('Working!')" 
style="padding:8px;background:#3498db;color:white;border:none;">
Click Me
</button>
</div>

<div style="background:#2c3e50;color:white;text-align:center;padding:10px;">
© 2026 My Website
</div>

</body>
</html>

Q. Deploy a custom webpage by replacing the default Apache page with your own HTML file displaying "My First Deployed Website", then restart the server and verify output.

cd /var/www/html/
sudo rm index.html
sudo nano index.html

<html>
<body style="margin:0;font-family:Arial;background:#f4f6f8;">

<div style="background:#2c3e50;color:white;text-align:center;padding:25px;">
<h1>Welcome to My Website</h1>
<p>A simple webpage example</p>
</div>

<div style="background:#444;text-align:center;padding:8px;">
<a href="#" style="color:white;margin:10px;">Home</a>
<a href="#" style="color:white;margin:10px;">About</a>
<a href="#" style="color:white;margin:10px;">Contact</a>
</div>

<div style="padding:25px;text-align:center;">
<h2>Hello!</h2>
<p>This is a small webpage built using HTML, CSS, and JavaScript.</p>

<button onclick="alert('Working!')" 
style="padding:8px;background:#3498db;color:white;border:none;">
Click Me
</button>
</div>

<div style="background:#2c3e50;color:white;text-align:center;padding:10px;">
© 2026 My Website
</div>

</body>
</html>

sudo systemctl restart apache2

Q. Install a DNS server and verify domain name resolution by resolving google.com using a command-line tool.

sudo apt install bind9
sudo systemctl start bind9
nslookup google.com

Q. Install and start an FTP server, then test the connection locally and verify successful login.

sudo apt install vsftpd
sudo systemctl start vsftpd
ftp localhost

