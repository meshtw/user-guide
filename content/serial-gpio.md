# 串口數據傳輸


1. 啟用串口模組：使用手機將串口設定開啟將 serial.enabled 設為 1 以啟用串行通信模組。

2. 設置 RX 和 TX 引腳：設定 serial.rxd 和 serial.txd 為所選的 RX 和 TX GPIO 引腳。

3. 在 V3 板上，建議使用以下引腳配置：
![截圖 2024-08-15 晚上10.32.28](https://hackmd.io/_uploads/rk7qZqi9R.png)
    - RXD：GPIO 7
    - TXD：GPIO 6
    
4. 設定超時時間：使用 serial.timeout 設定在考慮數據包傳輸完成前的等待時間。

5. 設定通信模式：如果你希望在一般文字訊息通道中傳送和接收訊息，將 serial.mode 設為 TEXTMSG。

發射端 TX
![截圖 2024-08-15 晚上10.25.42](https://hackmd.io/_uploads/BkOrgcocA.png)

注意 V3設置Baudrate需要相同
![截圖 2024-08-15 晚上10.27.37](https://hackmd.io/_uploads/HJ4wx5o5R.png)

收到訊息如下
![截圖 2024-08-15 晚上10.34.19](https://hackmd.io/_uploads/SJ8xz9o5R.png)
