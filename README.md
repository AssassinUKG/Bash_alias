# Bash_alias (created by me ac1d) - For Bash not zsh!

## Bash alians's for an easy life!

### Get ips 
IP Addresses
```
ipa() {
ips=$(ifconfig | grep "inet " | cut -d " "  -f 10| xargs)
IFS=" " read -ra iparr <<< "$ips"
ipnames=$(ifconfig | cut -d ":" -f1 | cut -d " " -f1| xargs)
IFS=" " read -ra iparr2 <<< "$ipnames"
count=0

for ((i = 0 ; i < "${#iparr2}" ; i++)); do
        printf "%06s: %-15s\n" "${iparr2[i]}" " ${iparr[i]}"
done
}

```

Add this to your .bashrc, then source it after 
```
source ~/.bashrc
```

Then in your term call
```
ipa
```
to get the ips listed. 

