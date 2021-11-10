user
```
I have no name
```


IPC
```
ipcs -q
ipcmk -Q
```

PID:
```
echo $$
```

mount:
```
mount -t proc proc /proc
```


UTS
```
pstree -pl

readlink /proc/111/ns/uts
readlink /proc/123/ns/uts

hostname test-hostname-01
hostname
```

---

enable user name space on centos:
```
grubby --args="user_namespace.enable=1" --update-kernel="$(grubby --default-kernel)"
reboot
echo 640 > /proc/sys/user/max_user_namespaces
```
disable
```
grubby --remove-args="user_namespace.enable=1" --update-kernel="$(grubby --default-kernel)"
reboot
```