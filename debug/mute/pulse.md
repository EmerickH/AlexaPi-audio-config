# Solving Pulse errors

## /!\ Make shure you've followed the setup guide /!\

Please read [this](../../setup/pulse.md)!

## I've followed everything but it's not working!

Maybe pulseaudio is not correctly configured:

- If you have a graphical interface, install `pavucontrol`:
`sudo apt-get install pavucontrol`
and launch it with `pavucontrol` command.
You can now check if the input devices are correctly configured.

- If you don't have one, try `pamixer`
Try:
`sudo apt-get install pamixer`
if it's not working, install it manually:
```
git clone https://github.com/cdemoulins/pamixer.git
cd pamixer
make
./pamixer
```
