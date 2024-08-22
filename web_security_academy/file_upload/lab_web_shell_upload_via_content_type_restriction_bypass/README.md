# Web shell upload via Content-Type restriction bypass
<a href="{{ site.url }}{{ site.baseurl }}"> Home</a>


Description:
```
This lab contains a vulnerable image upload function. It attempts to prevent users from uploading unexpected file types, but relies on checking user-controllable input to verify this.

To solve the lab, upload a basic PHP web shell and use it to exfiltrate the contents of the file /home/carlos/secret. Submit this secret using the button provided in the lab banner.

You can log in to your own account using the following credentials: wiener:peter 
```

Link: https://portswigger.net/web-security/learning-paths/server-side-vulnerabilities-apprentice/file-upload-apprentice/file-upload/lab-file-upload-web-shell-upload-via-content-type-restriction-bypass

## Solution
Once you start this lab, you will notice a "My Account" section in the top right corner.<br><br>
![image](https://github.com/CrestFallenTurtle/state-of-mind/blob/main/pictures/web_security_academy/file_upload/ladning_page.png?raw=true)

Enter the provided credentials ``wiener:peter``.<br><br>
![image](https://github.com/CrestFallenTurtle/state-of-mind/blob/main/pictures/web_security_academy/file_upload/my_account?raw=true)

Once you're logged in, take note of two things.
1. The feature to upload an avatar<br><br>
![image](https://github.com/CrestFallenTurtle/state-of-mind/blob/main/pictures/web_security_academy/file_upload/logged_in?raw=true)

2. The accepted image formats, this can be seen if you inspect the network traffic

![image](https://github.com/CrestFallenTurtle/state-of-mind/blob/main/pictures/web_security_academy/file_upload/accepted_file_formats?raw=true)

Now create a file locally on your system that contains the following, in our case we are going with `image.php` for the file name.
```
<?php echo file_get_contents('/home/carlos/secret'); ?>
```
<i>Function explanation: https://www.php.net/manual/en/function.file-get-contents.php</i>



