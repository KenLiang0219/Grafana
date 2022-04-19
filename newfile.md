# Grafana 操作手冊
## 一、Grafana 下載&註冊

下載連結: https://grafana.com/grafana/download

Edition: 選擇OSS(Open Source Software)
作業系統: 依照自身電腦選擇對應的即可
![](https://i.imgur.com/Jk5DBY9.png)

---
## 二、Grafana 基本操作和設定 (以MySQL為主)
### 建立一個新的 Dashboard
1.在頁面左邊工具列找到 '+'，選擇 Create 中的 Dashboard

![](https://i.imgur.com/CtnCo9B.png)

2.畫面會出現一個 Add panel (假如沒有出現可以點右上角紅框處新增)，點擊 Add a new panel

![](https://i.imgur.com/m3E1tHf.png)

3.進入 edit panel 的模式後畫面可分為三個部分
>(1)紅框:圖形預覽
>(2)藍框:資料來源(data source)，我在這部分都使用MySQL資料庫，SQL搜尋的語法也是寫在這裡
>(3)綠框:選擇 panel 類型(time series, bar chart, gauge, table等等)，以及panel的設定(title, style, mapping)都在這邊更改

![](https://i.imgur.com/sXYQu2O.png)

這時候會發現沒有 data source 可以讀取資料，所以回過頭來新增 data source

### 新增 Data Source
1.在頁面左邊工具列點選 Configuration 中的 Data Source ，並選取右上方的 Add data source

![](https://i.imgur.com/zmqcjWT.png)

2.裡面有許多 data source 可以選擇，我的資料使用MySQL資料庫儲存，所以選擇 MySQL database

![](https://i.imgur.com/b4XAaFi.png)

3.紅框內為必填的部分，其他可以按照自己的需求去做更改，填完之後點擊底下 
++註: test 可能會出現 connecting error，請複製該 error 透過 google 參考解決辦法++

![](https://i.imgur.com/Uth6hBU.png)

### 建立一個符合自己需求的 Panel(以)

1.add a new panel 並且進入edit panel，點擊右上角紅框處即可選擇自己想要的panel類型 

![](https://i.imgur.com/9NtqFYE.png)

註: 在 Grafana plugin 裡可以增加 panel 的種類，可以搜尋有沒有你需要的 panel 類型可以 import 
　
https://grafana.com/grafana/plugins/

![](https://i.imgur.com/uGN2igs.png)




---
## 三、Grafana 進階應用與技巧分享
---
### 如何在同一個 Dashboard 中顯示多個不同時間區間的 Panels
- ### Override time range
    1.進入 edit panel 中，找到 Query options 設定
    
    ![](https://i.imgur.com/if5YrA3.png)

    2.將 Relative time 填入想要的時間範圍(從 now 往前推所填入的時間，s=秒 m=分 h=時 d=日)
    ++註:可以填入 variable 讓 relative time 隨著 variable 的輸入而改變，不用進入 edit panel 修改++
    
    ![](https://i.imgur.com/jbfd8vU.png)

    3.即可讓該 panel 不受右上角的 absolute time range 影響而變化
    
    ![](https://i.imgur.com/fuG28Rw.png)
    
    如果想將右上角的 Last XXX 關掉，把 Hide time info 打開就會消失了
    
    ![](https://i.imgur.com/trlsToO.png)


    


---

