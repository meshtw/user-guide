# 如何確認傳輸成功

Meshtestic有兩種傳輸方式一個是透過LORA另外一個則是透過MQTT。


最快的方式就是在臉書聊天室敲敲群內各位朋友，看看有沒有收到XD

- LoRA

    1. 有獲取Ack
    ![截圖 2024-08-07 凌晨1.01.58](https://hackmd.io/_uploads/H16MD0kqA.png)
    2. 目標節點無響應但其他節點做響應
    ![截圖 2024-08-07 凌晨1.01.22](https://hackmd.io/_uploads/r15lPAJ5A.png)
    3. 長按訊息可確認，並可以確認SNR
    ![截圖 2024-08-07 凌晨1.01.09](https://hackmd.io/_uploads/HJy-DAJc0.png)


- MQTT

    可以透過Telegram來確認是否傳輸到MQTT服務器，注意Telegram也是有可能的產生漏訊息的狀況。
    [Telegram MeshTW](https://t.me/MeshTW_MQTT)
        ![截圖 2024-08-07 凌晨12.57.38](https://hackmd.io/_uploads/ryCZICycA.png)


Q.有人知道為什麼有些沒有ack對方卻收得到
A.簡單來說...你講話夠大聲...對方有聽到，對方要回答你，但是對方聲音比較小聲，所以你沒聽到