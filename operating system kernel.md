# operating system kernel

---

![](https://i.imgur.com/tHtBJQs.jpg)

* 電腦作業系統kernel構造的基本圖
1. 最中心的kernel可以去操作memory、disk、cpu、network這四個主要硬體，操作的權限都是用root
2. 在kernel space 裡面有很多module(模組)，而且都是動態模組，動態意思是需要就掛進來，不需要就拿走
3. 模組裡面有很多程式，協助kernel來處理命令
4. 外圍的四個區域分別有不同的作用，像貝殼程式，假設我用keyboard打貝殼程式，可能會去使用tools裡面的ls，再用ls去file system裡面找資料，或是輸入busybox，到app功能去執行，那執行就需要用到模組去幫助kernel操控那四個硬體來進行你輸入的命令