# File path traversal, simple case
<a href="{{ site.url }}{{ site.baseurl }}"> Home</a>


Description:
```
This lab contains a path traversal vulnerability in the display of product images.

To solve the lab, retrieve the contents of the /etc/passwd file. 
```

## Solution
Once you're on the landing page, right click on one of the images shown below. In our case we will use the first image.
![image](https://github.com/CrestFallenTurtle/state-of-mind/blob/main/pictures/web_security_academy/path_traversal/landing_page.png?raw=true)

Capture the GET request for the selected image, and send it to the repeater.
![image](https://github.com/CrestFallenTurtle/state-of-mind/blob/main/pictures/web_security_academy/path_traversal/image.png?raw=true)

Once it's in the repeater, take a look at the `filename=63.jpg`, this will the parameter to modify.
![image](https://github.com/CrestFallenTurtle/state-of-mind/blob/main/pictures/web_security_academy/path_traversal/repeater.png?raw=true)

We should be able to obtain the `passwd` file by entering a good amount of `../` and ending it off with `/etc/passwd`.
![image](https://github.com/CrestFallenTurtle/state-of-mind/blob/main/pictures/web_security_academy/path_traversal/result.png?raw=true)

<b>Note:</b> The amount of `../` to use is typically hard to properly find out since it all depends on where on the system the webpage is served from. But it's better to enter "too many" since nothing happens if you're at root and try to back out of it.
