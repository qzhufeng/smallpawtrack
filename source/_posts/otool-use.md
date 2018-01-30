---
title: otool使用说明
date: 2018-01-30 10:29:38
tags: ['mactools']
categories:
  - 安全
  - apple
  - apple-tools
---


# otool 工具 查看库／反编译等二进制信息

### 1 依赖库查询
```otool -L Payload/XXX.app/XXX```
### 2 查看该应用是否砸壳
```otool -l Payload/XXX.app/XXX | grep -B 2 crypt ```

cryptid 0（砸壳） 1（未砸壳）
```
otool -l DingTalk | grep -B 2 crypt
          cmd LC_ENCRYPTION_INFO
      cmdsize 20
     cryptoff 16384
    cryptsize 40239104
      cryptid 0
--
          cmd LC_ENCRYPTION_INFO_64
      cmdsize 24
     cryptoff 16384
    cryptsize 45400064
      cryptid 0
```


