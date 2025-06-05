# コンテナ技術


## 仕様全般

### Opne Container Initiative

* OCI Runtime Spec
    * Container
    * Runtime
* OCI Image
    * OCI Image Format Specification によって定義されるコンテナイメージ仕様


### CRI (Container Runtime Interface) 

* CNCF(Kubernetes)からリリースされたkubeletとContainer RuntimeとのI/F仕様

## Runtime 

### Low Level Container Runtime

name| 説明
----|------
runc| -
runv | -
cc-runtime | - 
kata-runtime |-
runq |-
railcar | - 
runnc |-
[gVisor](https://github.com/google/gvisor)  | -

### HighLevel Container Runtime


name | 説明
------|------
containerd |-
cri-o | - 
podman | - 
docker | CRI互換ではない
rkt|-


##  アーキテクチャ


dockerを例にして

```plantuml
title コンテナ階層

component docker 
component dockerd
component containerd
component runC


docker -down- dockerd:REST
dockerd -down- containerd:gRPC
containerd -down- runC:OC


```
