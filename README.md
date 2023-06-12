# Juniper_commands
Just a brief description of juniper commands and usage

# __Hello :)__

In Juniper you will be always in operational mode first 
that is you see below prompt
```
>
``` 
Here you can run some show commands like 

```console
> show version
> show chassis hardware detail
> show system processes extensive
```

you can always use question mark `?` to get context sensitive help like below 

```console
> show ?
```

To configure anything you must first enter into edit or configure mode


## __The command to enter configure mode is `configure`__

```console
> configure
```

## __Configuring ip addresses on interfaces__

```console
> set interfaces ge-0/0/1.0 family inet address 192.168.1.3/24
```

above one is the example

family means like ip version 4 or 6, 

for version 4 it just `inet`

for version 6 it `inet6`

## __Configuring OSPF__

It is configured in between two routers to share routes within one Autonomous system

only one command

```console
> set protocols ospf area 0 interface ge-0/0/1.0
```

## __Configuring BGP__

It is configured in between two routers to share routes from one autonomous system to another autonomous system

```console
> set bgp group <bgp_name_here> local-as <bgp_number>
> set bgp group <bgp_name_here> neighbor <connecting_router_ip_address_here> peer-as <connected_router_bgp_number>
```
For example

```console
> set bgp group my_bgp local-as 100
> set bgp group my_bgp neighbor 100.25.1.3 peer-as 200
```

you can check it by running

```console
show bgp neighbor
```

Always 

```
commit check
```
and
```
commit
```

Thank you
Bye:)
