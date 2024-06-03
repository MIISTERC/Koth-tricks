# Protect your king.txt
<hr>
<b></i>Level - 0:-</b>
<hr>

## If you are first to to root the machine follow the below steps to protect the king.
1.To prevent overwriting the `king.txt` file, you can set the `noclobber` option in your shell.

```sh
# Set the noclobber option to prevent overwriting files
set -o noclobber /root/king.txt
```
2.Make King.txt unwritable using `chattr` chattr makes king.txt unwritable even for root.
```sh
#add the immutable bit to king.txt
chattr +ia /root/king.txt
```
3.Make `king.txt` a read-only system file, make sure you are `root` before running the below command.
```sh
#the 'ro' makes king.txt a read-only system file.
sudo mount --bind -o ro /root/king.txt /root/king.txt 2>/dev/null
```
## Snatch Other's king and make it yours 😂
1.If you cant overwrite king.txt then someone already set noclobber on `king.txt` you can unset it by
```sh
set +o noclobber /root/king.txt
```
or 
```sh
echo "USERNAME" >| /root/king.txt
```

2.When you write your username to `king.txt` and `operation not permitted` occurs then probably someone used `chattr` , you can easily remove the immutable bit from king.txt by
```sh
chattr -ia /root/king.txt
```
3.If `read-only system file` appears when you write your name in it , then someone mounted it to make `king.txt` unwritable, to unmount it 
```sh
sudo umount -l /root/king.txt
```




