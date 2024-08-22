# Unprotected admin functionality with unpredictable URL
<a href="{{ site.url }}{{ site.baseurl }}"> Home</a>


Description:
```
This lab has an unprotected admin panel. It's located at an unpredictable location, but the location is disclosed somewhere in the application.

Solve the lab by accessing the admin panel, and using it to delete the user carlos. 
```

## Solution
Go to the landing page.

![image](https://github.com/CrestFallenTurtle/state-of-mind/blob/main/pictures/web_security_academy/access_control/landing_page_2.png?raw=true)

Once it has loaded, pull up the code for the website, take note of the content between `<sript>...</script>` tags

![image](https://github.com/CrestFallenTurtle/state-of-mind/blob/main/pictures/web_security_academy/access_control/jscript.png?raw=true)

We can see that the admin page is hosted at `/admin-cym84y`, so let us go there.

Once the admin panel has loaded, delete `carlos` and the lab is done.

![image](https://github.com/CrestFallenTurtle/state-of-mind/blob/main/pictures/web_security_academy/access_control/admin_page_2.png?raw=true)
<br/><br/>
![image](https://github.com/CrestFallenTurtle/state-of-mind/blob/main/pictures/web_security_academy/access_control/result_2.png?raw=true)
