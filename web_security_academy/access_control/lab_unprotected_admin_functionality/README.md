# Unprotected admin functionality
<a href="{{ site.url }}{{ site.baseurl }}"> Home</a>


Description:
```
This lab has an unprotected admin panel.

Solve the lab by deleting the user carlos. 
```

## Solution
Go to the landing page, and once it's loaded add a `/robots.txt` to the end of the url.

![image](https://github.com/CrestFallenTurtle/state-of-mind/blob/main/pictures/web_security_academy/access_control/landing_page.png?raw=true)

In the `robots.txt` we can see that there should be an administrator panel over at `/administrator-panel`.

![image](https://github.com/CrestFallenTurtle/state-of-mind/blob/main/pictures/web_security_academy/access_control/robots.png?raw=true)

Once the admin panel has loaded, delete `carlos` and the lab is done.

![image](https://github.com/CrestFallenTurtle/state-of-mind/blob/main/pictures/web_security_academy/access_control/admin_panel.png?raw=true)
<br/><br/>
![image](https://github.com/CrestFallenTurtle/state-of-mind/blob/main/pictures/web_security_academy/access_control/result.png?raw=true)
