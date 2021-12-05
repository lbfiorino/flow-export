# Disable NIC receive offloading

In order to avoid such distortions, all receive offload mechanisms need to be disabled. In the case of GRO (and the older LRO), this can be done with ethtool. The following call returns a list of the current status of all offload mechanisms for interface:

```bash
$ ethtool -k <dev>
```
If GRO is not shown, you probably need to install a newer version of ethtool. To disable GRO (and LRO), execute:

```bash
$ ethtool -K <dev> gro off
$ ethtool -K <dev> lro off
```
