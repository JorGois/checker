---
title: Checker
description: Will make a resume of list of nodes, and have multiple options to create a ansible inventory
author: Jorge Góis
tags: check, ping, port check, ansible inventary, hostname check
created:  2015 Apr 6
edit: 2015 Apr 30
---

# Checker

Basic idea:

 * List a large group of nodes with similar names
 * Verify simple name resolucion and if is on or off
 * Verify the principal ports are open.
 * Create a ansible inventory with informaction of resolved nodes [-A]

## Example

* Nodes group:

	- vmdk001
    - vmdk002
    - vmdk003
    - ...
    - vmdk200

- Sub Domain: notexist
- Domain: lan

```shell
$ checker vmdk -o notexist -D lan -s 150 -n 200 -P 6969 -A
```

### Output
```
--------------------------------------------------------------------------------------
    IP	   		HOST		STATE	22	8080	9101	9001	6969
192.168.0.1	   vmdk150.notexit.lan	  UP   OPEN	OPEN	CLOSE	CLOSE	OPEN
...
192.168.0.200	   vmdk200.notexit.lan	  UP   OPEN	OPEN	CLOSE	CLOSE	OPEN
--------------------------------------------------------------------------------------
Hosts not resolve: 0 	 Hosts Down: 0  Host example: vmdk150.notexit.lan
[Info] File inventory_sp1ssw create
--------------------------------------------------------------------------------------
