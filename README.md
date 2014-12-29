random-notes
============

Random notes. Useful for me... but for you, I know it can help

Show first ipv4 adress from first interface only.

`ip -o -4 addr show | awk -F '[ /]+' '/global/ {print $4}' | head -n1`


stop etcd from supervisord et start it from puplic etcd discovery url

  supervisorctl stop etcd; etcd -name `hostname` -initial-advertise-peer-urls https://`ip -o -4 addr show | awk -F '[ /]+' '/global/ {print $4}' | head -n1`:2380  \
  -listen-peer-urls https://`ip -o -4 addr show | awk -F '[ /]+' '/global/ {print $4}' | head -n1`:2380  \
  -discovery https://discovery.etcd.io/9bb9396de0f894a62fad7aa117f59d03
