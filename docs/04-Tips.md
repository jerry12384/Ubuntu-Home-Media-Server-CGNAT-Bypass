# For laptops: Disabling the sleep function when closing the lid

Use nano to edit the file `/etc/systemd/logind.conf`.

```bash
sudo nano /etc/systemd/logind.conf
```

Use the arrow keys to find the line for `HandleLidSwitch`, uncomment it by removing the # in the front and change it to `HandleLidSwitch=ignore`. Your config should look something like this:

```bash
##... more lines ...##
#HandleHibernateKey=hibernate
HandleLidSwitch=ignore
#HandleLidSwitchExternalPower=suspend
##... more lines ...##
```

Save your changes by pressing Ctrl+X, then Y and Enter.
