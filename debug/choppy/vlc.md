# VLC's audio is choppy

This is an known bug, infortunately, there's no solution actually.
You need changing to SoX and pulse:

## Install SoX

```
sudo apt-get install pulseaudio sox libsox-fmt-pulse
```

## Edit AlexaPi's config

### Locate config

The default AlexaPi's config emplacement is `/etc/opt/AlexaPi/config.yaml` or in the same folder as AlexaPi.
If there's no `config.yaml`, create it:
```
sudo cp /opt/AlexaPi/src/config.template.yaml /etc/opt/AlexaPi/config.yaml
```

### Edit config

Now edit it with `nano` for example:
```
sudo nano /etc/opt/AlexaPi/config.yaml
```

and change theses lines:
```
  input_device: "pulse"
  playback_handler: "sox"
  output: "pulseaudio"
  output_device: "default"
```
Now save (Ctrl+X - y - Enter - Enter for nano) and start/restart AlexaPi
```
sudo service alexapi restart
```

If it's not working, please [open an issue](https://github.com/alexa-pi/AlexaPi/issues/new).
