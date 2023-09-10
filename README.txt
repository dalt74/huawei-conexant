Audio codec on Huawei/Honor notebooks is "slightly broken":

1. The "master" gain controls highfreq speakers
2. The "headphone" gain controls headphone and lowfreq speakers

To check this use the command: alsamixer -c 0 then start any
music/video and play with headphone and master gains alsamixer
shows.

So if you need speakers sound on you Huawei/Honor noutbook then
you need to unmute and change master and hedphone gains both. The
only problem is there are no Linux DE that allows you to setup this.

The scripts fix thisissue by synchronizing master/headphone gains.

How to Install:

1. Install acpid (!!!)

2. Copy files:
   acpi/* -> /etc/acpi/events
   bin/* -> /usr/local/bin

3. Start acpid, push volume control button and enjoy how the sound is working

4. Enable acpid startup on boot (systemctl enable acpid)

P.S.:

The sync script is called only when changing volume. But I'm shure you're
smart enough to setup <your_favorite_DE/distro> to call a sync script on boot

P.P.S.:

Don't forget to check SELinux logs if SELinux is enabled.

It may (and will) reject access acpid scripts from accessing device
