# Changing output from terminal

Get the ids of PA sinks
```bash
pactl list short sinks
```

**Headset**
5   alsa_output.usb-SteelSeries_Arctis_7P_-00.analog-stereo         module-alsacard.c       s24le       2ch         28000Hmz

**Speakers**
7   alsa_output.pci-0000_03_00.1.hdmi-stero                         module-alsa-card.c      s16le2ch                44100Hz


## Change default output devices

```bash
pacmd set-default-sink <sink-name>
```


## Change default input device

```bash
pacmd set-default-source <source name>
```
