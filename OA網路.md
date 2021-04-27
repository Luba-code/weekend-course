# OA網路 office automation

---

* 設定NAT網路裝置與主機port相同

![](https://i.imgur.com/MMYStsD.png)

1. 進到 `C:\Program Files (x86)\VMware\VMware Player`找到vmnetcfg.exe

![](https://i.imgur.com/uTYp8HW.png)

2. 點選右下角Change Setting 

![](https://i.imgur.com/MpJpVrM.png)

3. 點選NAT網路裝置 NAT Settings...

![](https://i.imgur.com/vQ8Ti0W.png)

4. 點選add 打上與主機相同的port號，和虛擬機IP就設定完成了

---

* 進到ubuntu架一個網頁prot號80 

![](https://i.imgur.com/47ItPnX.png)

* 打主機名稱，不是虛擬機IP就可以連到自己建的網頁了

![](https://i.imgur.com/N8sYCU0.png)

* 這樣同一辦公室網段的主機，就都可以互相進入你架的網頁了，適合辦公室網路環境

