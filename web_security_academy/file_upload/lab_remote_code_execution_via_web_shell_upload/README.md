# Remote code execution via web shell upload
<a href="{{ site.url }}{{ site.baseurl }}"> Home</a>


Description:
```
This lab contains a vulnerable image upload function. It doesn't perform any validation on the files users upload before storing them on the server's filesystem.

To solve the lab, upload a basic PHP web shell and use it to exfiltrate the contents of the file /home/carlos/secret. Submit this secret using the button provided in the lab banner.

You can log in to your own account using the following credentials: wiener:peter 
```

## Solution
Once you start this lab, you will notice a "My Account" section in the top right corner.<br><br>
![image](https://github.com/CrestFallenTurtle/state-of-mind/blob/main/pictures/web_security_academy/file_upload/359171312-9e32b5e5-2816-4d56-97c6-3d0c13164dfc.png?raw=true)

Enter the provided credentials ``wiener:peter``.<br><br>
![image](https://github.com/CrestFallenTurtle/state-of-mind/blob/main/pictures/web_security_academy/file_upload/359171419-4271ec78-b8e6-487b-8e73-e23173ba5b35.png?raw=true)

Once you're logged in, take note of the feature to upload an avatar<br><br>
![image](https://github.com/CrestFallenTurtle/state-of-mind/blob/main/pictures/web_security_academy/file_upload/359171568-e11fd2b5-6134-4d84-92d3-acb9e817cb5e.png?raw=true)

Create a file locally on your system that contains the following, in our case we are going with `image.php` for the file name.
```
<?php echo file_get_contents('/home/carlos/secret'); ?>
```
<i>Function explanation: https://www.php.net/manual/en/function.file-get-contents.php</i>

We are ready to upload this file once it has been saved.<br><br>
![image](https://github.com/CrestFallenTurtle/state-of-mind/blob/main/pictures/web_security_academy/file_upload/359171701-501e548f-7198-4460-8269-15a9a9c3e926.png?raw=true)

Continue with the upload, and you should now recieve a message informing you that the image has been uploaded
successfully.<br><br>
![image](https://github.com/CrestFallenTurtle/state-of-mind/blob/main/pictures/web_security_academy/file_upload/359171797-40860b38-2bb4-47c4-82e3-b7a46e0da2fb.png?raw=true)

Now when you go back to your account settings, you should see a broken image icon indicating
that the system failed to parse the image.<br><br>
![image](https://github.com/CrestFallenTurtle/state-of-mind/blob/main/pictures/web_security_academy/file_upload/359172018-a548c76e-dd5b-4785-b548-933135851fa4.png?raw=true)

Right click on the image, and open up the image in a new tab.
You should now see that the secret key is printed to the screen, submit this and you will be done.




