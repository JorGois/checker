---
title: Checker
description: Will make a resume of list of nodes
author: Jorge Góis
tags: check, ping, port check
created:  2015 Apr 6
---

# Checker

Basic idea:

 * List a large group of nodes with similar names
 * Verify simple name resolucion and if is on or off
 * Verify the principal ports are open.

## Example

* Nodes group:

	- vmdk001
    - vmdk002
    - vmdk003
    - ...
    - vmdk200
    
- Sub Domain: notexist
- Domain: pt

```shell
$ checker vmdk -o notexist -D pt -n 200 -e 2 -P 6969
```

### Output
```
--------------------------------------------------------------------------------------
	IP				HOST			STATE	22		8080	9101	9001	6969
192.168.0.1	   vmdk001.notexit.pt	  UP   OPEN		OPEN	CLOSE	CLOSE	OPEN
...
192.168.0.200  vmdk200.notexit.pt	  UP   OPEN		OPEN	CLOSE	CLOSE	OPEN
--------------------------------------------------------------------------------------
Hosts not resolve: 0 	 Hosts Down: 0
Host example: vmdk001.notexit.pt
--------------------------------------------------------------------------------------
