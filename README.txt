Huawei notebook Conexant AC97 coded support scripts

Conexant codec on Huawei/Honor notebooks is "slightly broken":

1. The "master" gain controls highfreq speakers
2. The "headphone" gain controls headphone and lowfreq speakers

To check this use the command: alsamixer -c 0

So if you need speakeers sound you need to unmute master and hedphone gains both.

The scripts fix the issue - it sync master/headphone gains while adjusting volume.

How to Install:

1. Install acpid (!!!)

2. Copy files
   acpi/* -> /etc/acpi/events
   bin/* -> /usr/local/bin

3. Start acpid, push volume control button and enjoy how the sound is working

4. Enable acpid startup on boot (systemctl enable acpid)

P.S.:

The sync script is called only when changing volume.

But I'm shure you're smart enough to setup <your_favorite_DE> to call a sync script on boot
