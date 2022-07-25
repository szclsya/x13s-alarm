Some Packages for the ThinkPad X13s

## Binary repository
Some packages are pre-built in my repository. To use, add this section to the end of your `/etc/pacman.conf`:

```conf
[x13s]
Server = https://lecs.dev/repo
```

You'll need to trust the public key in order to verify package signature:

```bash
# Run as root
curl -O https://lecs.dev/repo/public.asc
pacman-key --add public.asc
pacman-key --lsign 9FD0B48BBBD974B80A3310AB6462EE0B8E382F3F
```
