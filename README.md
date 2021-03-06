[![GitHub release][release-img]][release]
[![License][license-img]][license]

## Overview
Kubeletctl is a command line tool that implement kubelet's API.  
Part of kubelet's API is documented but most of it is not.  
This tool covers all the documented and undocumented APIs.
The full list of all kubelet's API can be view through the tool or this [API table](https://github.com/cyberark/kubeletctl/blob/master/API_TABLE.md).  

## What can it do ?
- Run any kubelet API call 
- Scan for nodes with opened kubelet API
- Scan for containers with RCE
- Run a command on all the available containers by kubelet at the same time
- Get service account tokens from all available containers by kubelet
- Nice printing :)

## Usage
kubeletctl works similar to kubectl, use the following syntax to run commands:  
```
Usage:
  kubeletctl [flags]
  kubeletctl [command]

Available Commands:
  attach        Attach to a container
  configz       Return kubelet's configuration.
  containerLogs Return container log
  cri           Run commands inside a container through the Container Runtime Interface (CRI)
  debug         Return debug information (pprof or flags)
  exec          Run commands inside a container
  healthz       Check the state of the node
  help          Help about any command
  log           Return the log from the node.
  metrics       Return information about node CPU and memory usage
  pods          Get list of pods on the node
  portForward   Attach to a container
  run           Run commands inside a container
  runningpods   Returns all pods running on kubelet from looking at the container runtime cache.
  scan          Scans for nodes with opened kubelet API
  spec          Cached MachineInfo returned by cadvisor
  stats         Return performance stats of node, pods and containers.
  version       Print the version of the kubeletctl

Flags:
      --cidr string        A network of IP addresses (Example: x.x.x.x/24)
  -c, --container string   container
  -h, --help               help for kubeletctl
  -n, --namespace string   pod namespace
  -p, --pod string         container
      --port string        Kubelet's port, default is 10250
  -r, --raw                Prints raw data
  -s, --server string      Server address (format: x.x.x.x. For Example: 123.123.123.123)
  -u, --uid string         container

Use "kubeletctl [command] --help" for more information about a command.
```

To view the details on each command or subcommand use the `-h`\\`--help` switch.

## Demo
![kubeletctl](https://github.com/cyberark/kubeletctl/blob/assets/kubeletctl_gif2.gif)



## Build  
To build the project run:  
```
go build -ldflags "-s -w"
```

## Build with Dockerfile locally
You can use the attached docker file to build a local image by running:  
```
docker build -t kubeletctl -f Dockerfile .
```

Then run:  
```
docker run -it --rm kubeletctl
```

## Contributing

We welcome contributions of all kinds to this repository.  
For instructions on how to get started and descriptions
of our development workflows, please see our [contributing guide](https://github.com/cyberark/conjur-api-go/blob/master/CONTRIBUTING.md).

## License

This repository is licensed under Apache License 2.0 - see [`LICENSE`](LICENSE) for more details.

## Share Your Thoughts And Feedback
For more comments, suggestions or questions, you can contact Eviatar Gerzi ([@g3rzi](https://twitter.com/g3rzi)) from CyberArk Labs.
You can find more projects developed by us in https://github.com/cyberark/.

[release-img]: https://img.shields.io/github/release/cyberark/kubeletctl.svg
[release]: https://github.com/cyberark/kubeletctl/releases

[license-img]: https://img.shields.io/github/license/cyberark/kubeletctl.svg
[license]: https://github.com/cyberark/kubeletctl/blob/master/LICENSE

