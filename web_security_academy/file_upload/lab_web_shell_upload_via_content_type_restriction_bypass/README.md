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
![image](https://github.com/CrestFallenTurtle/state-of-mind/blob/main/pictures/web_security_academy/file_upload/landing_page.png?raw=true)

Enter the provided credentials ``wiener:peter``.<br><br>
![image](https://github.com/CrestFallenTurtle/state-of-mind/blob/main/pictures/web_security_academy/file_upload/my_account.png?raw=true)

Once you're logged in, take note of two things.
1. The feature to upload an avatar<br><br>
![image](https://github.com/CrestFallenTurtle/state-of-mind/blob/main/pictures/web_security_academy/file_upload/logged_in.png?raw=true)

2. The accepted image formats, this can be seen if you inspect the network traffic
![image](https://github.com/CrestFallenTurtle/state-of-mind/blob/main/pictures/web_security_academy/file_upload/accepted_file_formats.png?raw=true)

Now create a file locally on your system that contains the following, in our case we are going with `web_shell.php` for the file name.
```
<?php echo file_get_contents('/home/carlos/secret'); ?>
```
<i>Function explanation: https://www.php.net/manual/en/function.file-get-contents.php</i>

For this exploit to work, we will have to upload the file and intercept the package for further modifying.

![image](https://github.com/CrestFallenTurtle/state-of-mind/blob/main/pictures/web_security_academy/file_upload/new_upload.png?raw=true)

Intercept the package in burp suite, and change the `Content-Type` to be e.g. `Content-Type: image/apng`. This will allow us to bypass the built in filters
![image](https://github.com/CrestFallenTurtle/state-of-mind/blob/main/pictures/web_security_academy/file_upload/intercepted_package.png?raw=true)

Once it has been uploaded you should see a success message be printed on the screen.<br/>
![image](https://github.com/CrestFallenTurtle/state-of-mind/blob/main/pictures/web_security_academy/file_upload/web_shell_uploaded.png?raw=true)

When you now return to your account page, you should see that the avatar image is displayed as if it's broken. Right click on it and open it in a new tab.
Doing this should now provide you with the secret for solving this lab.
![image](https://github.com/CrestFallenTurtle/state-of-mind/blob/main/pictures/web_security_academy/file_upload/secret_obtained.png?raw=true) 
