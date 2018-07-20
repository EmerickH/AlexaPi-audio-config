# 🅰 Alsa setup

## Find your devices

First you must find your input/output devices,

### Output device

Type in a terminal:
```
aplay -L
```
and search for `plughw:CARD=XXXX,DEV=X` where XXXX is your device name and X its number.

### Input device

Same thing for input device but with this command:
```
arecord -L
```

ℹ *With some USB mics, you may have to use something like `USB PnP Sound Device: Audio (plughw:1,0)` instead of `plughw:CARD=XXXX,DEV=X`*

## Edit AlexaPi's config

### Locate config

The default AlexaPi's config emplacement is `/etc/opt/AlexaPi/config.yaml` or in the same folder as AlexaPi.

🚫 *If there's no `config.yaml`, create it:*
```
sudo cp -n /etc/opt/AlexaPi/src/config.template.yaml /etc/opt/AlexaPi/config.yaml
```

### Edit config

Now edit it with `nano` for example:
```
sudo nano /etc/opt/AlexaPi/config.yaml
```

and change theses lines with your input and output devices:
```
  input_device: "plughw:CARD=XXXX,DEV=X"
  output: "alsa"
  output_device: "plughw:CARD=XXXX,DEV=X"
```
Now save (Ctrl+X - y - Enter - Enter for nano) and start/restart AlexaPi
```
sudo service alexapi restart
```

If you have issues, please read [debug doc](../debug/index.md)
