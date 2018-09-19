# Check DR
Check DR is a script designed to check if the current server is in a production or DR environment.

It does this by comparing the current external IP address with a whitelist of ip addresses. 

If the current external IP address is in the whitelist it exits with a status of 0

if the current external IP is not in the whitelist it exits with a status of 1

heres an example bash script using it

``` bash
#!/bin/bash
check_dr
if [[ $? == 0 ]]; then
    echo "system is in production do more commands here"
else
    echo "system is at dr exit processing now"
    exit
fi
```




## Usage

**check_dr** with no options will just run the check

**check_dr -a <ip>** add an ip address to the white list

**check_dr -d <ip>** delete an ip address from the white list

**check_dr -l** list the current external ip address and display the whitelist

**check_dr -?** display the help
