# iptables 

---

* iptables 安裝 

![](https://i.imgur.com/ftM4tCz.png)

1. 安裝`sudo apk add iptables`
2. 成功之後可以下` sudo iptables -V` 檢查版本
3. 看iptables裡面三個表所有鍊的規則 `sudo iptables -L -n`

---

* iptables裡面的三個表(含鍊)

![](https://i.imgur.com/IdEq7tz.png)



---

* 此圖環境為iptables的規則圖

![](https://i.imgur.com/gERWwaT.png)

---

* 練習圖

![](https://i.imgur.com/4zNUJi4.jpg)

---

* 首先練習擋住10.233.0.129IP
1. 輸入`sudo iptables -I INPUT -s 10.233.0.129 -j DROP`
    * 因為它是走本機IP所以走規定圖上面那條，要阻擋就設規則在filter表裡面的INPUT鍊 ，DROP的意思就是指定IP的任何動作都丟掉。 

![](https://i.imgur.com/3E7bO4H.png)

從10.233.0.129 ping 120.96.143.181的結果

![](https://i.imgur.com/b2EkAS5.png)

* 再來練習擋住10.233.0.192這網段的所有IP
1. 輸入`sudo iptables -I INPUT -s 10.233.0.192/26 -j DROP`

![](https://i.imgur.com/eXdR8Q5.png)

從10.233.0.203 ping 120.96.143.181的結果

![](https://i.imgur.com/mzjkFoi.png)

最後我們試著讓10.233.0.129連出外網

1. 輸入`sudo iptables -t nat -A POSTROUTING -o eth0 ! -d 10.233.0.0/24 -j MASQUERADE`

![](https://i.imgur.com/qykGToV.png)

* 成功連出外網，因為我們在nat表的POSTROUTING鍊讓所有10.233.0.0的IP偽裝出去，才能練到外網
