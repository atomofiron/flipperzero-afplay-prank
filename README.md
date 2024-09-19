# afplay prank

paste this demo (30% sound volume) script into the your terminal and press Enter

```
curl -L https://gist.github.com/assets/14147217/f7094f73-9ba8-493c-abca-ac9a436fd85d -o ~/.config/track.mp4
touch ~/.prank
while :; do if [ -f ~/.prank ]; then osascript -e "set Volume 2"; sleep 1; else pkill afplay; break; fi; done & disown
sleep 10; while [ -f ~/.prank ]; do sleep 1; afplay ~/.config/track.mp4; done & disown
```

and run this to stop it

```
rm ~/.prank
```

or reboot your system because neither closing the terminal nor killing the `afplay` process will help you 😈
