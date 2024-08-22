# Unprotected admin functionality
<a href="{{ site.url }}{{ site.baseurl }}"> Home</a>


Description:
```
This lab has an unprotected admin panel.

Solve the lab by deleting the user carlos. 
```

## Solution
Go to the landing page, and once it's loaded add a `/robots.txt` to the end of the url.

In the `robots.txt` we can see that there should be an administrator panel over at `/administrator-panel`.


Once the admin panel has loaded, delete `carlos` and the lab is done.