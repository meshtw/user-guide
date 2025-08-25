# V3螢幕邊緣被裁切

問題來源自系統自動偵測I2C OLED裝置，識別到錯誤的顯示驅動導致。
![353520701-8ac1f9ec-baf7-4207-b338-4c27ab51ea19](https://hackmd.io/_uploads/ryy4lCyqR.png)
![353520715-9be6e056-95e1-4141-b333-fd457bb944ed](https://hackmd.io/_uploads/SJk4lRJcR.png)



解決辦法：
方法1.嘗試使用1.4.x以上的韌體，[BASHCAT](https://github.com/meshtastic/firmware/pull/4356)有修改韌體強制為使用SSD1306作為OLED選型
方法2.從設定->螢幕設定->OLED Type->SSD1306，保存後重啟即可。

![截圖 2024-08-07 凌晨12.31.50](https://hackmd.io/_uploads/SJsbeCkcA.png)
