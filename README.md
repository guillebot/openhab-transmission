# openhab-transmission
Query and or control Transmission Bittorrent client from OpenHAB

# Motivation

As you can see in my other repo openhab-sucks, I'm pretty determined to integrate my whole house into OpenHAB.

There are a lot of stuff that you can control using provided OpenHAB bindings, but for some things you have to write your own. Going full "binding" is out of my abilities and scope so for some simple things I'm going the script way.

This is openhab-transmission, more about this readme and some associated files than a whole lot of programming.

## What do I want?

The goal behind transmission monitoring is:

* Being able to have some extremely simple controls from OpenHAB, mostly start/stop the whole thing. 
* Get upload and download speed, which I'll try to integrate in my Grafana bandwidth panel.

# References

* This guy converted the specs to markdown, I can't thank him enough. Thanks Robert.
`https://gist.github.com/RobertAudi/807ec699037542646584`


# First the manual tests

In my home network I have transmission bittorrent client running on 192.168.1.5, so the rpc url it's going to be:

`http://192.168.1.5:9091/transmission/rpc`

You can just call this from wget/curl. But without a correct session-id you are going to get something like this:

```
curl http://192.168.1.5:9091/transmission/rpc
% Total    % Received % Xferd  Average Speed   Time    Time     Time  Current
Dload  Upload   Total   Spent    Left  Speed
100   581  100   581    0     0    581      0  0:00:01 --:--:--  0:00:01 36312<h1>409: Conflict
</h1><p>Your request had an invalid session-id header.</p><p>To fix this, follow these steps:
<ol><li> When reading a response, get its X-Transmission-Session-Id header and remember it
<li> Add the updated header to your outgoing requests
<li> When you get this 409 error message, resend your request with the updated header</ol>
</p><p>This requirement has been added to help prevent 
<a href="https://en.wikipedia.org/wiki/Cross-site_request_forgery">CSRF</a> attacks.</p>
<p><code>**X-Transmission-Session-Id: EStz3BzxejO4fdjh5768h6ic4xMkVPiHxHFVnu9X6IGuS1**</code></p>
```



