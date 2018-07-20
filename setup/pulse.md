# 🇵 Pulse setup

First, make shure PulseAudio is installed:
```
sudo apt install pulseaudio
```

## Edit AlexaPi's config

### Locate config

The default AlexaPi's config emplacement is `/etc/opt/AlexaPi/config.yaml` or in the same folder as AlexaPi.

🚫 *If there's no `config.yaml`, create it:*
```
sudo cp /opt/AlexaPi/src/config.template.yaml /etc/opt/AlexaPi/config.yaml
```

### Edit config

Now edit it with `nano` for example:
```
sudo nano /etc/opt/AlexaPi/config.yaml
```

and change theses lines with your input and output devices:
#### With VLC (default)
```
  input_device: "pulse"
  output: "pulse"
  output_device: ""
```
#### With SoX (if VLC is not working or for Rapberry ![R](rasp.png))
```
  input_device: "pulse"
  output: "pulseaudio"
  output_device: "default"
```

Now save (Ctrl+X - y - Enter - Enter for nano) and start/restart AlexaPi
```
sudo service alexapi restart
```

## Pulse config

Now you have to change pulse config.
It can be done with `pavucontrol` if you have a graphical interface:
```
sudo apt install pavucontrol
pavucontrol
```
Or with `pamixer` in command line:
```
sudo apt install pamixer
pamixer
```
If it's not working, install it manually:
```
git clone https://github.com/cdemoulins/pamixer.git
cd pamixer
make
./pamixer
```


If you have issues, please read [debug doc](../debug/index.md)
