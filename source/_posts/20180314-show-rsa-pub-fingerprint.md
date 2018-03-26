---
title: 怎么看rsa公钥的指纹
date: 2018-03-14 10:00:20
tags: [ssh,rsa]
categories: 工具使用
---
The newer SSH commands will list fingerprints as a SHA256 Key.

For example

    ssh-keygen -lf ~/.ssh/id_rsa.pub 
    1024 SHA256:19n6fkdz0qqmowiBy6XEaA87EuG/jgWUr44ZSBhJl6Y (DSA)

If you need to compare it against a old fingerprint you also need to specify to use the md5 fingerprint hashing function.

	ssh-keygen -E md5 -lf ~/.ssh/id_rsa.pub
	2048 MD5:4d:5b:97:19:8c:fe:06:f0:29:e7:f5:96:77:cb:3c:71 (DSA)
	
Also available: -E sha1