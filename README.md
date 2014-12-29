random-notes
============

Random notes. Useful for me... but for you, I know it can help

Show first ipv4 adress from first interface only.

`ip -o -4 addr show | awk -F '[ /]+' '/global/ {print $4}' | head -n1`
