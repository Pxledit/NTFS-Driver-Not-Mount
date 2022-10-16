# NTFS-Driver-Not-Mount
Fix mounting NTFS drives asking for root password in Arch linux

Also install ntfs-3g if u haven't already using
```
sudo pacman -S ntfs-3g
```

open terminal and Create the following file as root: (editor vim/nano)
```
sudo  vim /etc/polkit-1/rules.d/49-nopasswd_global.rules
```

$paste these in that file
```
polkit.addRule(function(action, subject) {
    if (subject.isInGroup("wheel")) {
        return polkit.Result.YES;
    }
});
```
