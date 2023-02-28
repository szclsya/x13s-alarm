Some Packages for the ThinkPad X13s

## Binary repository
Some packages are pre-built in my repository. For now, these packages are provided:

+ `linux-x13s`: linux kernel with out-of-tree patches for X13s
+ `x13s-firmware`: firmware blob for X13s
  - Uses the official linux-firmware source, but alarm's linux-firmware is out-of-date. Will be removed when alarm's package get updated
+ `mesa-a690`: a patched version of Mesa to support a690 GPU found on 8cx Gen 3
+ `vulkan-a690`: part of mesa project, vulkan driver for Adreno A690
+ `pd-mapper` `qmic` `qrtr` `rmtfs`: campaign applications for Qualcomm platforms, required for battery and charging status report

To use, add this section to the end of your `/etc/pacman.conf`:

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

## Note on `linux-x13s`
In order to get the battery working, install `pd-mapper` `qmic` `qrtr` `rmtfs` and enable `pd-mapper.service`
