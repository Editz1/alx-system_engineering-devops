ssh sammy@yourserveriporremotehostname
If that works, exit back out by typing:

exit
Now we can establish an SFTP session by issuing the following command:

sftp sammy@yourserveriporremotehostname
You will connect the the remote system and your prompt will change to an SFTP prompt.

Transferring Local Files to the Remote System
Transferring files to the remote system works the same way, but with a put command:

put localFile
Output
Uploading localFile to /home/demouser/localFile
localFile                                     100% 7607     7.4KB/s   00:00
The same flags that work with get apply to put. So to copy an entire local directory, you can run put -r:

put -r localDirectory
One familiar tool that is useful when downloading and uploading files is the df command, which works similarly to the command line version. Using this, you can check that you have enough space to complete the transfers you are interested in:

df -h
Output
    Size     Used    Avail   (root)    %Capacity
  19.9GB   1016MB   17.9GB   18.9GB           4%
Please note, that there is no local variation of this command, but we can get around that by issuing the ! command.

The ! command drops us into a local shell, where we can run any command available on our local system. We can check disk usage by typing:

!
and then

df -h

Explain
Output
Filesystem      Size   Used  Avail Capacity  Mounted on
/dev/disk0s2   595Gi   52Gi  544Gi     9%    /
devfs          181Ki  181Ki    0Bi   100%    /dev
map -hosts       0Bi    0Bi    0Bi   100%    /net
map autohome    0Bi    0Bi    0Bi   100%    /home
Any other local command will work as expected. To return to your SFTP session, type:

exit
You should now see the SFTP prompt return.
