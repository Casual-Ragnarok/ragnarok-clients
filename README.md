---
license: apache-2.0
---

现在已经很难找到 PRE 的客户端了（2008 EP13.2）
而且就算 rAthena 把 renewal.h 的 `#define PRERE` 取消注释，不管是 Ragexe 还是 RagexeRE 的封包都无法接入到服务端。

```
What is the difference between "Ragexe" and "RagexeRE"?
Ragexe - EXE for kRO main server
RagexeRE - EXE for kRO test server
```

现在只有一种 PRE 的方法：

通过注释掉职业变更脚本来移除第三职业，然后创建一个源文件来实现renewal.h（或者干脆保留这个文件）的功能吗？我自己也不喜欢renewal的经验/掉落率限制，所以我把它们移除了。这样一来，你现在就相当于拥有了一个P-RE服务器。非第三职业仍然在使用P-RE的计算方式。有必要有两个不同的版本吗？


二转前的职业伤害公式，在 RE 和 PRE 都一样。

在 Nemo http://nemo.herc.ws/downloads/