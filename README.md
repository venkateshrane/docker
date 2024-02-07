# docker

Docker Basic Commands

List All the Docker Images 
=========================
192:Docker Garima$ docker image ls

REPOSITORY                                TAG                                                                          IMAGE ID       CREATED         SIZE
ubuntu                                    latest                                                                       fd1d8f58e8ae   12 days ago     77.9MB
docker/desktop-kubernetes                 kubernetes-v1.29.1-cni-v1.4.0-critools-v1.29.0-cri-dockerd-v0.3.8-1-debian   ace10e261811   2 weeks ago     438MB
registry.k8s.io/kube-apiserver            v1.29.1                                                                      53b148a9d196   3 weeks ago     127MB
registry.k8s.io/kube-controller-manager   v1.29.1                                                                      79d451ca186a   3 weeks ago     122MB
registry.k8s.io/kube-scheduler            v1.29.1                                                                      406945b51154   3 weeks ago     59.5MB
registry.k8s.io/kube-proxy                v1.29.1                                                                      43c6c10396b8   3 weeks ago     82.3MB
docker/welcome-to-docker                  latest                                                                       c1f619b6477e   3 months ago    18.6MB
registry.k8s.io/etcd                      3.5.10-0                                                                     a0eed15eed44   3 months ago    148MB
nginx                                     latest                                                                       b690f5f0a2d5   3 months ago    187MB
registry.k8s.io/coredns/coredns           v1.11.1                                                                      cbb01a7bd410   5 months ago    59.8MB
docker/desktop-vpnkit-controller          dc331cb22850be0cdd97c84a9cfecaf44a1afb6e                                     556098075b3d   8 months ago    36.2MB
registry.k8s.io/pause                     3.9                                                                          e6f181688397   16 months ago   744kB
docker/desktop-storage-provisioner        v2.0                                                                         99f89471f470   2 years ago     41.9MB



==================================================================================================================
List the container 
(-a will list all the containers be it stopped or started)
(-q will give the container id)

==================================================================================================================
192:Docker Garima$ docker container ls -a
CONTAINER ID   IMAGE     COMMAND                  CREATED          STATUS          PORTS     NAMES
40af99d0121e   nginx     "/docker-entrypoint.…"   14 seconds ago   Up 14 seconds   80/tcp    zen_poincare

==================================================================================================================
HOW to run a container
(-d will run the container in deattached mode)
type "docker container run --help" for more information
==================================================================================================================
192:Docker Garima$ docker container run -d nginx
40af99d0121e0ae79d641a253748583e9469fb0a5d174e411aa308ca8f615898


==================================================================================================================
How to check the details about a container
==================================================================================================================
192:Docker Garima$ docker container ls
CONTAINER ID   IMAGE     COMMAND                  CREATED         STATUS         PORTS     NAMES
40af99d0121e   nginx     "/docker-entrypoint.…"   5 minutes ago   Up 5 minutes   80/tcp    zen_poincare
192:Docker Garima$ conker container inspect 40a
bash: conker: command not found
192:Docker Garima$ docker container inspect 40a
[
    {
        "Id": "40af99d0121e0ae79d641a253748583e9469fb0a5d174e411aa308ca8f615898",
        "Created": "2024-02-07T17:20:36.218450385Z",
        "Path": "/docker-entrypoint.sh",
        "Args": [
            "nginx",
            "-g",
            "daemon off;"
        ],
        "State": {
            "Status": "running",
            "Running": true,
            "Paused": false,
            "Restarting": false,
            "OOMKilled": false,
            "Dead": false,
            "Pid": 28503,
            "ExitCode": 0,
            "Error": "",
            "StartedAt": "2024-02-07T17:20:36.611399581Z",
            "FinishedAt": "0001-01-01T00:00:00Z"
        },
        "Image": "sha256:b690f5f0a2d535cee5e08631aa508fef339c43bb91d5b1f7d77a1a05cea021a8",
        "ResolvConfPath": "/var/lib/docker/containers/40af99d0121e0ae79d641a253748583e9469fb0a5d174e411aa308ca8f615898/resolv.conf",
        "HostnamePath": "/var/lib/docker/containers/40af99d0121e0ae79d641a253748583e9469fb0a5d174e411aa308ca8f615898/hostname",
        "HostsPath": "/var/lib/docker/containers/40af99d0121e0ae79d641a253748583e9469fb0a5d174e411aa308ca8f615898/hosts",
        "LogPath": "/var/lib/docker/containers/40af99d0121e0ae79d641a253748583e9469fb0a5d174e411aa308ca8f615898/40af99d0121e0ae79d641a253748583e9469fb0a5d174e411aa308ca8f615898-json.log",
        "Name": "/zen_poincare",
        "RestartCount": 0,
        "Driver": "overlay2",
        "Platform": "linux",
        "MountLabel": "",
        "ProcessLabel": "",
        "AppArmorProfile": "",
        "ExecIDs": null,
        "HostConfig": {
            "Binds": null,
            "ContainerIDFile": "",
            "LogConfig": {
                "Type": "json-file",
                "Config": {}
            },
            "NetworkMode": "default",
            "PortBindings": {},
            "RestartPolicy": {
                "Name": "no",
                "MaximumRetryCount": 0
            },
            "AutoRemove": false,
            "VolumeDriver": "",
            "VolumesFrom": null,
            "ConsoleSize": [
                33,
                168
            ],
            "CapAdd": null,
            "CapDrop": null,
            "CgroupnsMode": "private",
            "Dns": [],
            "DnsOptions": [],
            "DnsSearch": [],
            "ExtraHosts": null,
            "GroupAdd": null,
            "IpcMode": "private",
            "Cgroup": "",
            "Links": null,
            "OomScoreAdj": 0,
            "PidMode": "",
            "Privileged": false,
            "PublishAllPorts": false,
            "ReadonlyRootfs": false,
            "SecurityOpt": null,
            "UTSMode": "",
            "UsernsMode": "",
            "ShmSize": 67108864,
            "Runtime": "runc",
            "Isolation": "",
            "CpuShares": 0,
            "Memory": 0,
            "NanoCpus": 0,
            "CgroupParent": "",
            "BlkioWeight": 0,
            "BlkioWeightDevice": [],
            "BlkioDeviceReadBps": [],
            "BlkioDeviceWriteBps": [],
            "BlkioDeviceReadIOps": [],
            "BlkioDeviceWriteIOps": [],
            "CpuPeriod": 0,
            "CpuQuota": 0,
            "CpuRealtimePeriod": 0,
            "CpuRealtimeRuntime": 0,
            "CpusetCpus": "",
            "CpusetMems": "",
            "Devices": [],
            "DeviceCgroupRules": null,
            "DeviceRequests": null,
            "MemoryReservation": 0,
            "MemorySwap": 0,
            "MemorySwappiness": null,
            "OomKillDisable": null,
            "PidsLimit": null,
            "Ulimits": [],
            "CpuCount": 0,
            "CpuPercent": 0,
            "IOMaximumIOps": 0,
            "IOMaximumBandwidth": 0,
            "MaskedPaths": [
                "/proc/asound",
                "/proc/acpi",
                "/proc/kcore",
                "/proc/keys",
                "/proc/latency_stats",
                "/proc/timer_list",
                "/proc/timer_stats",
                "/proc/sched_debug",
                "/proc/scsi",
                "/sys/firmware",
                "/sys/devices/virtual/powercap"
            ],
            "ReadonlyPaths": [
                "/proc/bus",
                "/proc/fs",
                "/proc/irq",
                "/proc/sys",
                "/proc/sysrq-trigger"
            ]
        },
        "GraphDriver": {
            "Data": {
                "LowerDir": "/var/lib/docker/overlay2/73f160c4c07174af1b75457f6c5e1e5938bfe0358041da14d970a2406cf24278-init/diff:/var/lib/docker/overlay2/0611749da1ca9d613a8f10dca1353e6f097ce952856ff9bda5f029c2ee78a968/diff:/var/lib/docker/overlay2/1aaf6839c525f46c466e2c7211c45548b0f07aee3f11fd73a35766d905922b71/diff:/var/lib/docker/overlay2/6e90f6987b4974cba0d62ca2c1dedd21a4e828405f822ddc1974812ebc818652/diff:/var/lib/docker/overlay2/24845aee4e08c47373a37dedfdc3abcdad619784b9788e4e55b7b737791cb391/diff:/var/lib/docker/overlay2/53e235b253817493ec29ca5a603bfe4cc1046882de43dbf2a3784fc147706a60/diff:/var/lib/docker/overlay2/a63831a9c0e9b4923d4a9323ababa4836b17d12491c224f87dc28797e29b581b/diff:/var/lib/docker/overlay2/5cfcf99de149e8c55e2b792f222461ee7ee98007bd670e9c1ed31170d53f3dea/diff",
                "MergedDir": "/var/lib/docker/overlay2/73f160c4c07174af1b75457f6c5e1e5938bfe0358041da14d970a2406cf24278/merged",
                "UpperDir": "/var/lib/docker/overlay2/73f160c4c07174af1b75457f6c5e1e5938bfe0358041da14d970a2406cf24278/diff",
                "WorkDir": "/var/lib/docker/overlay2/73f160c4c07174af1b75457f6c5e1e5938bfe0358041da14d970a2406cf24278/work"
            },
            "Name": "overlay2"
        },
        "Mounts": [],
        "Config": {
            "Hostname": "40af99d0121e",
            "Domainname": "",
            "User": "",
            "AttachStdin": false,
            "AttachStdout": false,
            "AttachStderr": false,
            "ExposedPorts": {
                "80/tcp": {}
            },
            "Tty": false,
            "OpenStdin": false,
            "StdinOnce": false,
            "Env": [
                "PATH=/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin",
                "NGINX_VERSION=1.25.3",
                "NJS_VERSION=0.8.2",
                "PKG_RELEASE=1~bookworm"
            ],
            "Cmd": [
                "nginx",
                "-g",
                "daemon off;"
            ],
            "Image": "nginx",
            "Volumes": null,
            "WorkingDir": "",
            "Entrypoint": [
                "/docker-entrypoint.sh"
            ],
            "OnBuild": null,
            "Labels": {
                "maintainer": "NGINX Docker Maintainers \u003cdocker-maint@nginx.com\u003e"
            },
            "StopSignal": "SIGQUIT"
        },
        "NetworkSettings": {
            "Bridge": "",
            "SandboxID": "d3c7cd45bb889fbd39dc828ccec028301816858a4968b312af48f7430c6e8492",
            "SandboxKey": "/var/run/docker/netns/d3c7cd45bb88",
            "Ports": {
                "80/tcp": null
            },
            "HairpinMode": false,
            "LinkLocalIPv6Address": "",
            "LinkLocalIPv6PrefixLen": 0,
            "SecondaryIPAddresses": null,
            "SecondaryIPv6Addresses": null,
            "EndpointID": "c0fe855e39cce1c8db7d58303423c859f75c65200a760785ea9e0dd9dca824d4",
            "Gateway": "172.17.0.1",
            "GlobalIPv6Address": "",
            "GlobalIPv6PrefixLen": 0,
            "IPAddress": "172.17.0.2",
            "IPPrefixLen": 16,
            "IPv6Gateway": "",
            "MacAddress": "02:42:ac:11:00:02",
            "Networks": {
                "bridge": {
                    "IPAMConfig": null,
                    "Links": null,
                    "Aliases": null,
                    "MacAddress": "02:42:ac:11:00:02",
                    "NetworkID": "9a0ce544a33a9d1bcc85d4aa2303ecf328e37d56c217ce11bd93a4423dbe3fb6",
                    "EndpointID": "c0fe855e39cce1c8db7d58303423c859f75c65200a760785ea9e0dd9dca824d4",
                    "Gateway": "172.17.0.1",
                    "IPAddress": "172.17.0.2",
                    "IPPrefixLen": 16,
                    "IPv6Gateway": "",
                    "GlobalIPv6Address": "",
                    "GlobalIPv6PrefixLen": 0,
                    "DriverOpts": null,
                    "DNSNames": null
                }
            }
        }
    }
]
192:Docker Garima$ 


