## HTTP Basic Auth

When we visit the exercise found at the end of this section, it prompts us to enter a username and a password. Unlike the usual login forms, which utilize HTTP parameters to validate the user credentials (e.g. POST request), this type of authentication utilizes a `basic HTTP authentication`, which is handled directly by the webserver to protect a specific page/directory, without directly interacting with the web application.

To access the page, we have to enter a valid pair of credentials, which are `admin`:`admin` in this case:

As shown in the screenshot:

![[Pasted image 20241003163422.png]]

Your page will look something like this:

![[Pasted image 20241003163503.png]]

so we can use the `curl -i` command (used to send an HTTP request and includes the response headers in the output)

![[Pasted image 20241003163611.png]]

And it's denied. So what we can do is do a `curl -u` (used to pass user credentials for authentication when making an HTTP request. It allows you to specify a username and password in the request, typically for Basic HTTP Authentication.) remember to put admin:admin as it's the username and password.

![[Pasted image 20241003163659.png]]

So here's how we are able to see the authorization by doing a -v and inserting the username and password with the link.

![[Pasted image 20241003163859.png]]

As we are using `basic HTTP auth`, we see that our HTTP request sets the `Authorization` header to `Basic YWRtaW46YWRtaW4=`, which is the base64 encoded value of `admin:admin`. If we were using a modern method of authentication (e.g. `JWT`), the `Authorization` would be of type `Bearer` and would contain a longer encrypted token.

Let's try to manually set the `Authorization`, without supplying the credentials, to see if it does allow us access to the page. We can set the header with the `-H` flag, and will use the same value from the above HTTP request. We can add the `-H` flag multiple times to specify multiple headers:

![[Pasted image 20241003164049.png]]

## GET Parameters

Once we are authenticated, we get access to a `City Search` function, in which we can enter a search term and get a list of matching cities: