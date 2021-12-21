Ansible role to configure BGP using bird

See [this blog post](https://cybercyber.org/site-to-site-vpn-using-ipsec-virtual-tunnels-and-bgp.html) for an extended use-case.

Install using `ansible-galaxy install cybercyber_org.setup_bgp`.

Supply the variable `bgp` with this content:

```yaml
bgp:
  netns: eth0 # the namespace the daemon should run in
  router_id: 192.168.1.1
  as: 65158
  publish_interfaces:
    - eth0
  neighbors:
    - name: A
      address: 192.168.1.2
      as: 65159
    - name: B
      address: 10.0.12.23
      as: 65400
```
