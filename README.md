# tunnel-repo
deb/rpm repository for Tunnel

## Debian/Ubuntu

```
$ sudo apt-get install wget apt-transport-https gnupg
$ wget -qO - https://khulnasoft.github.io/tunnel-repo/deb/public.key | gpg --dearmor | sudo tee /usr/share/keyrings/tunnel.gpg > /dev/null
$ echo "deb [signed-by=/usr/share/keyrings/tunnel.gpg] https://khulnasoft.github.io/tunnel-repo/deb generic main" | sudo tee -a /etc/apt/sources.list.d/tunnel.list
$ sudo apt-get update
$ sudo apt-get install tunnel
```

## RHEL/CentOS

Add repository setting

```
$ sudo tee /etc/yum.repos.d/tunnel.repo << 'EOF'
[tunnel]
name=Tunnel repository
baseurl=https://khulnasoft.github.io/tunnel-repo/rpm/releases/$basearch/
gpgcheck=1
enabled=1
gpgkey=https://khulnasoft.github.io/tunnel-repo/rpm/public.key
EOF
```
Using `yum`:
```
$ sudo yum -y update
$ sudo yum -y install tunnel
```
Using `dnf`:
```
$ sudo dnf -y update
$ sudo dnf -y install tunnel
```