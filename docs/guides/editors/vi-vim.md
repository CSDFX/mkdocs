# Linux vi/vim

Vim 是从 vi 发展出来的一个文本编辑器。代码补全、编译及错误跳转等方便编程的功能特别丰富，在程序员中被广泛使用。

简单的来说， vi 是老式的字处理器，不过功能已经很齐全了，但是还是有可以进步的地方。 vim 则可以说是程序开发者的一项很好用的工具。

<del>我用过Debian的Vi，那里的Vi很纯粹</del>


## 基本概念

Vim 有 3 个主要模式：

| 模式名             | 说明                             | 切换方式            |
| ------------------ | -------------------------------- | ------------------- |
| 普通模式 (Normal)  | 默认模式，用于导航、删除等       | 启动 Vim 后默认进入 |
| 插入模式 (Insert)  | 输入文本内容的模式               | `i`/`a`/`o`等 |
| 命令模式 (Command) | 执行保存、退出、查找、替换等命令 | `:`进入命令模式   |
