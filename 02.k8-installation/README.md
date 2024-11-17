### K8 installation

Uninstall any prior old versions:
```
[root@k8-node1 ~]# rpm -e docker docker-engine docker.io containerd runc
error: package docker is not installed
error: package docker-engine is not installed
error: package docker.io is not installed
error: package containerd is not installed
[root@k8-node1 ~]# 
[root@k8-node1 ~]# rpm -e runc podman cockpit-podman buildah podman-catatonit 
/sbin/ldconfig: /etc/ld.so.conf.d/kernel-5.4.17-2102.201.3.el8uek.x86_64.conf:6: hwcap directive ignored
[root@k8-node1 ~]# 
[root@k8-node1 ~]# dnf -y install dnf-plugins-core
Last metadata expiration check: 0:12:02 ago on Sat 16 Nov 2024 09:42:06 PM EST.
Package dnf-plugins-core-4.0.18-4.el8.noarch is already installed.
Dependencies resolved.
================================================================================================================================================
 Package                                  Architecture           Version                                Repository                         Size
================================================================================================================================================
Upgrading:
 dnf                                      noarch                 4.7.0-20.0.1.el8                       ol8_baseos_latest                 542 k
 dnf-data                                 noarch                 4.7.0-20.0.1.el8                       ol8_baseos_latest                 156 k
 dnf-plugins-core                         noarch                 4.0.21-25.0.1.el8                      ol8_baseos_latest                  76 k
 json-c                                   x86_64                 0.13.1-3.el8                           ol8_baseos_latest                  41 k
 libdnf                                   x86_64                 0.63.0-20.0.1.el8_10                   ol8_baseos_latest                 711 k
 libmodulemd                              x86_64                 2.13.0-1.el8                           ol8_baseos_latest                 233 k
 librepo                                  x86_64                 1.14.2-5.el8                           ol8_baseos_latest                  92 k
 libsolv                                  x86_64                 0.7.20-6.el8                           ol8_baseos_latest                 376 k
 python3-dnf                              noarch                 4.7.0-20.0.1.el8                       ol8_baseos_latest                 549 k
 python3-dnf-plugins-core                 noarch                 4.0.21-25.0.1.el8                      ol8_baseos_latest                 263 k
 python3-hawkey                           x86_64                 0.63.0-20.0.1.el8_10                   ol8_baseos_latest                 118 k
 python3-libdnf                           x86_64                 0.63.0-20.0.1.el8_10                   ol8_baseos_latest                 780 k
 python3-librepo                          x86_64                 1.14.2-5.el8                           ol8_baseos_latest                  53 k
 yum                                      noarch                 4.7.0-20.0.1.el8                       ol8_baseos_latest                 208 k

Transaction Summary
================================================================================================================================================
Upgrade  14 Packages

Total download size: 4.1 M
Downloading Packages:
(1/14): dnf-plugins-core-4.0.21-25.0.1.el8.noarch.rpm                                                           327 kB/s |  76 kB     00:00    
(2/14): json-c-0.13.1-3.el8.x86_64.rpm                                                                          1.0 MB/s |  41 kB     00:00    
(3/14): dnf-data-4.7.0-20.0.1.el8.noarch.rpm                                                                    574 kB/s | 156 kB     00:00     
(4/14): dnf-4.7.0-20.0.1.el8.noarch.rpm                                                                         1.7 MB/s | 542 kB     00:00     
(5/14): libmodulemd-2.13.0-1.el8.x86_64.rpm                                                                     3.0 MB/s | 233 kB     00:00     
(6/14): librepo-1.14.2-5.el8.x86_64.rpm                                                                         3.0 MB/s |  92 kB     00:00     
(7/14): libdnf-0.63.0-20.0.1.el8_10.x86_64.rpm                                                                  5.9 MB/s | 711 kB     00:00     
(8/14): python3-dnf-4.7.0-20.0.1.el8.noarch.rpm                                                                 7.9 MB/s | 549 kB     00:00     
(9/14): libsolv-0.7.20-6.el8.x86_64.rpm                                                                         4.6 MB/s | 376 kB     00:00     
(10/14): python3-dnf-plugins-core-4.0.21-25.0.1.el8.noarch.rpm                                                  6.5 MB/s | 263 kB     00:00     
(11/14): python3-hawkey-0.63.0-20.0.1.el8_10.x86_64.rpm                                                         3.8 MB/s | 118 kB     00:00     
(12/14): python3-librepo-1.14.2-5.el8.x86_64.rpm                                                                1.5 MB/s |  53 kB     00:00     
(13/14): yum-4.7.0-20.0.1.el8.noarch.rpm                                                                        5.7 MB/s | 208 kB     00:00     
(14/14): python3-libdnf-0.63.0-20.0.1.el8_10.x86_64.rpm                                                          10 MB/s | 780 kB     00:00     
------------------------------------------------------------------------------------------------------------------------------------------------
Total                                                                                                           8.0 MB/s | 4.1 MB     00:00     
Running transaction check
Transaction check succeeded.
Running transaction test
Transaction test succeeded.
Running transaction
  Preparing        :                                                                                                                        1/1 
  Running scriptlet: librepo-1.14.2-5.el8.x86_64                                                                                            1/1 
  Upgrading        : librepo-1.14.2-5.el8.x86_64                                                                                           1/28 
  Upgrading        : libmodulemd-2.13.0-1.el8.x86_64                                                                                       2/28 
  Upgrading        : libsolv-0.7.20-6.el8.x86_64                                                                                           3/28 
  Upgrading        : json-c-0.13.1-3.el8.x86_64                                                                                            4/28 
  Upgrading        : libdnf-0.63.0-20.0.1.el8_10.x86_64                                                                                    5/28 
  Upgrading        : python3-libdnf-0.63.0-20.0.1.el8_10.x86_64                                                                            6/28 
  Upgrading        : python3-hawkey-0.63.0-20.0.1.el8_10.x86_64                                                                            7/28 
  Upgrading        : dnf-data-4.7.0-20.0.1.el8.noarch                                                                                      8/28 
  Upgrading        : python3-dnf-4.7.0-20.0.1.el8.noarch                                                                                   9/28 
  Upgrading        : dnf-4.7.0-20.0.1.el8.noarch                                                                                          10/28 
  Running scriptlet: dnf-4.7.0-20.0.1.el8.noarch                                                                                          10/28 
  Upgrading        : python3-dnf-plugins-core-4.0.21-25.0.1.el8.noarch                                                                    11/28 
  Upgrading        : dnf-plugins-core-4.0.21-25.0.1.el8.noarch                                                                            12/28 
  Upgrading        : yum-4.7.0-20.0.1.el8.noarch                                                                                          13/28 
  Upgrading        : python3-librepo-1.14.2-5.el8.x86_64                                                                                  14/28 
  Cleanup          : yum-4.4.2-11.el8.noarch                                                                                              15/28 
  Running scriptlet: dnf-4.4.2-11.el8.noarch                                                                                              16/28 
  Cleanup          : dnf-4.4.2-11.el8.noarch                                                                                              16/28 
  Running scriptlet: dnf-4.4.2-11.el8.noarch                                                                                              16/28 
  Cleanup          : dnf-plugins-core-4.0.18-4.el8.noarch                                                                                 17/28 
  Cleanup          : python3-dnf-plugins-core-4.0.18-4.el8.noarch                                                                         18/28 
  Cleanup          : python3-dnf-4.4.2-11.el8.noarch                                                                                      19/28 
  Cleanup          : python3-hawkey-0.55.0-7.0.1.el8.x86_64                                                                               20/28 
  Cleanup          : python3-libdnf-0.55.0-7.0.1.el8.x86_64                                                                               21/28 
  Cleanup          : libdnf-0.55.0-7.0.1.el8.x86_64                                                                                       22/28 
  Cleanup          : python3-librepo-1.12.0-3.el8.x86_64                                                                                  23/28 
  Cleanup          : dnf-data-4.4.2-11.el8.noarch                                                                                         24/28 
  Cleanup          : librepo-1.12.0-3.el8.x86_64                                                                                          25/28 
  Cleanup          : json-c-0.13.1-0.4.el8.x86_64                                                                                         26/28 
  Cleanup          : libmodulemd-2.9.4-2.el8.x86_64                                                                                       27/28 
  Cleanup          : libsolv-0.7.16-2.el8.x86_64                                                                                          28/28 
  Running scriptlet: libsolv-0.7.16-2.el8.x86_64                                                                                          28/28 
/sbin/ldconfig: /etc/ld.so.conf.d/kernel-5.4.17-2102.201.3.el8uek.x86_64.conf:6: hwcap directive ignored

/sbin/ldconfig: /etc/ld.so.conf.d/kernel-5.4.17-2102.201.3.el8uek.x86_64.conf:6: hwcap directive ignored

  Verifying        : dnf-4.7.0-20.0.1.el8.noarch                                                                                           1/28 
  Verifying        : dnf-4.4.2-11.el8.noarch                                                                                               2/28 
  Verifying        : dnf-data-4.7.0-20.0.1.el8.noarch                                                                                      3/28 
  Verifying        : dnf-data-4.4.2-11.el8.noarch                                                                                          4/28 
  Verifying        : dnf-plugins-core-4.0.21-25.0.1.el8.noarch                                                                             5/28 
  Verifying        : dnf-plugins-core-4.0.18-4.el8.noarch                                                                                  6/28 
  Verifying        : json-c-0.13.1-3.el8.x86_64                                                                                            7/28 
  Verifying        : json-c-0.13.1-0.4.el8.x86_64                                                                                          8/28 
  Verifying        : libdnf-0.63.0-20.0.1.el8_10.x86_64                                                                                    9/28 
  Verifying        : libdnf-0.55.0-7.0.1.el8.x86_64                                                                                       10/28 
  Verifying        : libmodulemd-2.13.0-1.el8.x86_64                                                                                      11/28 
  Verifying        : libmodulemd-2.9.4-2.el8.x86_64                                                                                       12/28 
  Verifying        : librepo-1.14.2-5.el8.x86_64                                                                                          13/28 
  Verifying        : librepo-1.12.0-3.el8.x86_64                                                                                          14/28 
  Verifying        : libsolv-0.7.20-6.el8.x86_64                                                                                          15/28 
  Verifying        : libsolv-0.7.16-2.el8.x86_64                                                                                          16/28 
  Verifying        : python3-dnf-4.7.0-20.0.1.el8.noarch                                                                                  17/28 
  Verifying        : python3-dnf-4.4.2-11.el8.noarch                                                                                      18/28 
  Verifying        : python3-dnf-plugins-core-4.0.21-25.0.1.el8.noarch                                                                    19/28 
  Verifying        : python3-dnf-plugins-core-4.0.18-4.el8.noarch                                                                         20/28 
  Verifying        : python3-hawkey-0.63.0-20.0.1.el8_10.x86_64                                                                           21/28 
  Verifying        : python3-hawkey-0.55.0-7.0.1.el8.x86_64                                                                               22/28 
  Verifying        : python3-libdnf-0.63.0-20.0.1.el8_10.x86_64                                                                           23/28 
  Verifying        : python3-libdnf-0.55.0-7.0.1.el8.x86_64                                                                               24/28 
  Verifying        : python3-librepo-1.14.2-5.el8.x86_64                                                                                  25/28 
  Verifying        : python3-librepo-1.12.0-3.el8.x86_64                                                                                  26/28 
  Verifying        : yum-4.7.0-20.0.1.el8.noarch                                                                                          27/28 
  Verifying        : yum-4.4.2-11.el8.noarch                                                                                              28/28 

Upgraded:
  dnf-4.7.0-20.0.1.el8.noarch                         dnf-data-4.7.0-20.0.1.el8.noarch             dnf-plugins-core-4.0.21-25.0.1.el8.noarch    
  json-c-0.13.1-3.el8.x86_64                          libdnf-0.63.0-20.0.1.el8_10.x86_64           libmodulemd-2.13.0-1.el8.x86_64
  librepo-1.14.2-5.el8.x86_64                         libsolv-0.7.20-6.el8.x86_64                  python3-dnf-4.7.0-20.0.1.el8.noarch
  python3-dnf-plugins-core-4.0.21-25.0.1.el8.noarch   python3-hawkey-0.63.0-20.0.1.el8_10.x86_64   python3-libdnf-0.63.0-20.0.1.el8_10.x86_64   
  python3-librepo-1.14.2-5.el8.x86_64                 yum-4.7.0-20.0.1.el8.noarch

Complete!
[root@k8-node1 ~]# 
[root@k8-node1 ~]# dnf config-manager --add-repo https://download.docker.com/linux/rhel/docker-ce.repo
Adding repo from: https://download.docker.com/linux/rhel/docker-ce.repo
[root@k8-node1 ~]# 
[root@k8-node1 ~]# dnf install docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin
Last metadata expiration check: 0:03:27 ago on Sat 16 Nov 2024 09:55:32 PM EST.
Dependencies resolved.
================================================================================================================================================
 Package                                    Architecture            Version                            Repository                          Size 
================================================================================================================================================
Installing:
 containerd.io                              x86_64                  1.7.23-3.1.el8                     docker-ce-stable                    45 M 
 docker-buildx-plugin                       x86_64                  0.17.1-1.el8                       docker-ce-stable                    14 M 
 docker-ce                                  x86_64                  3:27.3.1-1.el8                     docker-ce-stable                    28 M 
 docker-ce-cli                              x86_64                  1:27.3.1-1.el8                     docker-ce-stable                   8.0 M 
 docker-compose-plugin                      x86_64                  2.29.7-1.el8                       docker-ce-stable                    14 M 
Installing dependencies:
 libcgroup                                  x86_64                  0.41-19.el8                        ol8_baseos_latest                   70 k 
Installing weak dependencies:
 docker-ce-rootless-extras                  x86_64                  27.3.1-1.el8                       docker-ce-stable                   5.1 M 

Transaction Summary
================================================================================================================================================
Install  7 Packages

Total download size: 113 M
Installed size: 426 M
Is this ok [y/N]: y
Downloading Packages:
(1/7): docker-buildx-plugin-0.17.1-1.el8.x86_64.rpm                                                              14 MB/s |  14 MB     00:00     
(2/7): docker-ce-cli-27.3.1-1.el8.x86_64.rpm                                                                     23 MB/s | 8.0 MB     00:00     
(3/7): docker-ce-rootless-extras-27.3.1-1.el8.x86_64.rpm                                                         22 MB/s | 5.1 MB     00:00     
(4/7): containerd.io-1.7.23-3.1.el8.x86_64.rpm                                                                   25 MB/s |  45 MB     00:01     
(5/7): libcgroup-0.41-19.el8.x86_64.rpm                                                                         334 kB/s |  70 kB     00:00     
(6/7): docker-ce-27.3.1-1.el8.x86_64.rpm                                                                         13 MB/s |  28 MB     00:02     
(7/7): docker-compose-plugin-2.29.7-1.el8.x86_64.rpm                                                             16 MB/s |  14 MB     00:00     
------------------------------------------------------------------------------------------------------------------------------------------------
Total                                                                                                            47 MB/s | 113 MB     00:02     
Docker CE Stable - x86_64                                                                                        18 kB/s | 1.6 kB     00:00    
Importing GPG key 0x621E9F35:
 Userid     : "Docker Release (CE rpm) <docker@docker.com>"
 Fingerprint: 060A 61C5 1B55 8A7F 742B 77AA C52F EB6B 621E 9F35
 From       : https://download.docker.com/linux/rhel/gpg
Is this ok [y/N]: y
Key imported successfully
Running transaction check
Transaction check succeeded.
Running transaction test
Transaction test succeeded.
Running transaction
  Preparing        :                                                                                                                        1/1 
  Installing       : docker-compose-plugin-2.29.7-1.el8.x86_64                                                                              1/7 
  Running scriptlet: docker-compose-plugin-2.29.7-1.el8.x86_64                                                                              1/7 
  Running scriptlet: libcgroup-0.41-19.el8.x86_64                                                                                           2/7 
  Installing       : libcgroup-0.41-19.el8.x86_64                                                                                           2/7 
  Running scriptlet: libcgroup-0.41-19.el8.x86_64                                                                                           2/7 
/sbin/ldconfig: /etc/ld.so.conf.d/kernel-5.4.17-2102.201.3.el8uek.x86_64.conf:6: hwcap directive ignored

  Installing       : docker-buildx-plugin-0.17.1-1.el8.x86_64                                                                               3/7 
  Running scriptlet: docker-buildx-plugin-0.17.1-1.el8.x86_64                                                                               3/7 
  Installing       : docker-ce-cli-1:27.3.1-1.el8.x86_64                                                                                    4/7 
  Running scriptlet: docker-ce-cli-1:27.3.1-1.el8.x86_64                                                                                    4/7 
  Installing       : containerd.io-1.7.23-3.1.el8.x86_64                                                                                    5/7 
  Running scriptlet: containerd.io-1.7.23-3.1.el8.x86_64                                                                                    5/7 
  Installing       : docker-ce-rootless-extras-27.3.1-1.el8.x86_64                                                                          6/7 
  Running scriptlet: docker-ce-rootless-extras-27.3.1-1.el8.x86_64                                                                          6/7 
  Installing       : docker-ce-3:27.3.1-1.el8.x86_64                                                                                        7/7 
  Running scriptlet: docker-ce-3:27.3.1-1.el8.x86_64                                                                                        7/7 
/sbin/ldconfig: /etc/ld.so.conf.d/kernel-5.4.17-2102.201.3.el8uek.x86_64.conf:6: hwcap directive ignored

  Verifying        : containerd.io-1.7.23-3.1.el8.x86_64                                                                                    1/7 
  Verifying        : docker-buildx-plugin-0.17.1-1.el8.x86_64                                                                               2/7 
  Verifying        : docker-ce-3:27.3.1-1.el8.x86_64                                                                                        3/7 
  Verifying        : docker-ce-cli-1:27.3.1-1.el8.x86_64                                                                                    4/7 
  Verifying        : docker-ce-rootless-extras-27.3.1-1.el8.x86_64                                                                          5/7 
  Verifying        : docker-compose-plugin-2.29.7-1.el8.x86_64                                                                              6/7 
  Verifying        : libcgroup-0.41-19.el8.x86_64                                                                                           7/7 

Installed:
  containerd.io-1.7.23-3.1.el8.x86_64       docker-buildx-plugin-0.17.1-1.el8.x86_64            docker-ce-3:27.3.1-1.el8.x86_64
  docker-ce-cli-1:27.3.1-1.el8.x86_64       docker-ce-rootless-extras-27.3.1-1.el8.x86_64       docker-compose-plugin-2.29.7-1.el8.x86_64       
  libcgroup-0.41-19.el8.x86_64

Complete!
[root@k8-node1 ~]# 
```

Now lets check docker version:
```
[root@k8-node1 ~]# docker --version
Docker version 27.3.1, build ce12230
[root@k8-node1 ~]# systemctl enable docker
Created symlink /etc/systemd/system/multi-user.target.wants/docker.service → /usr/lib/systemd/system/docker.service.
[root@k8-node1 ~]# 
```

Now we will setup KubeCtl, and this can be done in two ways one by downloading the binaries other is by using package manager, here we will do both

Using package manager:

Create repo and install 
```
[root@k8-node1 ~]# cat <<EOF | sudo tee /etc/yum.repos.d/kubernetes.repo
> [kubernetes]
> name=Kubernetes
> baseurl=https://pkgs.k8s.io/core:/stable:/v1.31/rpm/
> enabled=1
> gpgcheck=1
> gpgkey=https://pkgs.k8s.io/core:/stable:/v1.31/rpm/repodata/repomd.xml.key
> EOF
[kubernetes]
name=Kubernetes
baseurl=https://pkgs.k8s.io/core:/stable:/v1.31/rpm/
enabled=1
gpgcheck=1
gpgkey=https://pkgs.k8s.io/core:/stable:/v1.31/rpm/repodata/repomd.xml.key
[root@k8-node1 ~]# 
[root@k8-node1 ~]# yum install -y kubectl
Kubernetes                                                                                                       17 kB/s |  11 kB     00:00    
Dependencies resolved.
================================================================================================================================================
 Package                        Architecture                  Version                                   Repository                         Size
================================================================================================================================================
Installing:
 kubectl                        x86_64                        1.31.2-150500.1.1                         kubernetes                         11 M

Transaction Summary
================================================================================================================================================
Install  1 Package

Total download size: 11 M
Installed size: 54 M
Downloading Packages:
kubectl-1.31.2-150500.1.1.x86_64.rpm                                                                             14 MB/s |  11 MB     00:00    
------------------------------------------------------------------------------------------------------------------------------------------------
Total                                                                                                            14 MB/s |  11 MB     00:00     
Kubernetes                                                                                                      7.7 kB/s | 1.7 kB     00:00    
Importing GPG key 0x9A296436:
 Userid     : "isv:kubernetes OBS Project <isv:kubernetes@build.opensuse.org>"
 Fingerprint: DE15 B144 86CD 377B 9E87 6E1A 2346 54DA 9A29 6436
 From       : https://pkgs.k8s.io/core:/stable:/v1.31/rpm/repodata/repomd.xml.key
Key imported successfully
Running transaction check
Transaction check succeeded.
Running transaction test
Transaction test succeeded.
Running transaction
  Preparing        :                                                                                                                        1/1 
  Installing       : kubectl-1.31.2-150500.1.1.x86_64                                                                                       1/1 
  Verifying        : kubectl-1.31.2-150500.1.1.x86_64                                                                                       1/1 

Installed:
  kubectl-1.31.2-150500.1.1.x86_64

Complete!
[root@k8-node1 ~]#
[root@k8-node1 ~]# kubectl version --client
Client Version: v1.31.2
Kustomize Version: v5.4.2
[root@k8-node1 ~]#
```

Now lets install using binary files
```
[root@k8-node1 ~]# curl -LO "https://dl.k8s.io/release/$(curl -L -s https://dl.k8s.io/release/stable.txt)/bin/linux/amd64/kubectl"
  % Total    % Received % Xferd  Average Speed   Time    Time     Time  Current
                                 Dload  Upload   Total   Spent    Left  Speed
100   138  100   138    0     0   1210      0 --:--:-- --:--:-- --:--:--  1210
100 53.7M  100 53.7M    0     0  15.5M      0  0:00:03  0:00:03 --:--:-- 17.3M
[root@k8-node1 ~]# 
[root@k8-node1 ~]# curl -LO "https://dl.k8s.io/release/$(curl -L -s https://dl.k8s.io/release/stable.txt)/bin/linux/amd64/kubectl.sha256"
  % Total    % Received % Xferd  Average Speed   Time    Time     Time  Current
                                 Dload  Upload   Total   Spent    Left  Speed
100   138  100   138    0     0   1289      0 --:--:-- --:--:-- --:--:--  1277
100    64  100    64    0     0    219      0 --:--:-- --:--:-- --:--:--   219
[root@k8-node1 ~]# 
[root@k8-node1 ~]# echo "$(cat kubectl.sha256)  kubectl" | sha256sum --check
kubectl: OK
[root@k8-node1 ~]# install -o root -g root -m 0755 kubectl /usr/local/bin/kubectl
[root@k8-node1 ~]# 
[root@k8-node1 ~]# kubectl version --client
Client Version: v1.31.2
Kustomize Version: v5.4.2
[root@k8-node1 ~]# 
```