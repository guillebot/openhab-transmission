# openhab-transmission
Query and or control Transmission Bittorrent client from OpenHAB

# Motivation

As you can see in my other repo openhab-sucks, I'm pretty determined to integrate my whole home into OpenHAB.

There are a lot of stuff that you can control using provided OpenHAB bindings, but for some thinks you have to write your own. Going full "binding" is out of my abilities and scope so for some simple things I'm going the script way.

This is openhab-transmission, more about this readme and some associated files than a whole lot of programming.

## My goal behind transmission monitoring is:

* Being able to have some extremely simple controls from OpenHAB, mostly start/stop the whole thing. 
* And get upload and download speed, which I'll try to integrate in my grafana bandwidth panel.

# First the manual tests

In my home network I have transmission bittorrent client running on 192.168.1.5, so the rpc url it's going to be:

`http://192.168.1.5:9091/transmission/rpc`

