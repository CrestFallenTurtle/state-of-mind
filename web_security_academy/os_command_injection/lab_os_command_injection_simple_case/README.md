# OS command injection, simple case
<a href="{{ site.url }}{{ site.baseurl }}"> Home</a>


Description:
```
This lab contains an OS command injection vulnerability in the product stock checker.

The application executes a shell command containing user-supplied product and store IDs, and returns the raw output from the command in its response.

To solve the lab, execute the whoami command to determine the name of the current user. 
```

## Solution
To start off, load up the website in Burp suite and when you're on the landing page, select one of the products.
![image](https://github.com/CrestFallenTurtle/state-of-mind/blob/main/pictures/web_security_academy/os_command_injection/landing_page.png?raw=true)

When you have selected a product, click on the button to check the stock and make sure that you capture this package.
![image](https://github.com/CrestFallenTurtle/state-of-mind/blob/main/pictures/web_security_academy/os_command_injection/check_stock.png?raw=true)

When the package has been captured, send it to the repeater.
![image](https://github.com/CrestFallenTurtle/state-of-mind/blob/main/pictures/web_security_academy/os_command_injection/repeater.png?raw=true)

We can now modify the paramters to inject our os command. Insert `|whoami` behind the 1 in the `storeID` parameter and we should see the final results.
![image](https://github.com/CrestFallenTurtle/state-of-mind/blob/main/pictures/web_security_academy/os_command_injection/result.png?raw=true)
