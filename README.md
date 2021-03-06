# Cordova Plugin Ping Cmd

# Contents
* [General](#general)
* [Install](#install)
* [Usage](#usage)
* [Improvement](#improvement)

# General
If you want to perform ICMP operation such as echo-request/reply using cordova, you will find yourself easily stuck.
If you get your index.html url you will find that cordova does not use ```http (http://)``` protocol but ```file:/```
This little plugin provides two functions to perform simple ICMP operations.

# Install
NPM:
```
cordova plugin add cordova-plugin-ping-cmd
```
Github:
```
cordova plugin add https://github.com/Spartan0nix/cordova-plugin-ping-cmd.git
```

# Usage

## Function 'ipReachable'
``` cordova.plugins.Ping.ipReachable(ipAddress, onsuccess, onerror);  ```
#### Check if host is reachable

   * **ipAddress** => Destination ip address 
      * The ip address need to be a public ip, ip address on the same private network as yours or a domain name (ex : google.fr).
   * **onsuccess**
      * Return a string 
        * ``` Host is reachable ```
        * ``` Host is not reachable ```
   * **onerror**
   
   
## Function 'ping'
``` cordova.plugins.Ping.ping(ipAddress, onsuccess, onerror);  ```
#### Perform a complete ``` ping <ipAddress> ```

   * **ipAddress** => Destination ip address 
      * The ip address need to be a public ip, ip address on the same private network as yours or a domain name (ex : google.fr).
   * **onsuccess**
      * Return the entire ping result in the same string.
      * Each line return is on a different ```<p></p>```.
   * **onerror**
      * Host not reachable, ping with 100% Packet Loss, etc... are not considered as an error *   

# Improvement
First time creating a Cordova plugin.
I did not manage to return the ping result line by line, just like in a terminal.
