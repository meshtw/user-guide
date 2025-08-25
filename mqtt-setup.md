# MQTT設置

### MQTT 使用與設定
若你所在區域的 Meshtastic 覆蓋率還不高，或是因爲四週都是高樓大廈導致無法穩定的收到其他裝置的 LoRa 訊號，那你就需要需要開啓 MQTT ，來利用網際網路傳送訊息，設定方法如下：
* Android app
    * Radio configuration(裝備設定) → Lora → 不要勾選 Ignore MQTT → 開啟 OK to MQTT → 按下 Send → 裝置會重開機，等它開完機並重新連上手機
    * 回到 Radio configuration(裝備設定) → 往下捲動找到 MQTT → 打開 MQTT enabled 開關 → 打開 Encryption enabled 開關 → 打開 Proxy to client enabled 開關（讓裝置透過手機的網路來接收與傳送訊息） → （其他的開關都不用開）→ 按下 Send → 裝置會重開機，等它開完機並重新連上手機即完成
    * 同樣在 MQTT 的設定頁面，Root Topic 的部分確保設定爲 msh/TW，不要是 msh/TW/XXX 之類的，只要 msh/TW 就好，不然會收不到其他人的訊息

最後再檢查Channel Setting中要啟用MQTT的頻道是否有打開Uplink及Downlink

* iOS app
    * 設定頁 → LoRa → 不要勾選 Ignore MQTT → 按下儲存 → 裝置會重開機，等它開完機並重新連上手機
    * 設定頁 → 往下捲動找到 MQTT → 從畫面最上方數起，第 1 2 3 4 個選項的開關打開。
![451786627_792825912839187_4315039696692845276_n](https://hackmd.io/_uploads/BJnVc8ou0.png)

    * 同樣在 MQTT 的設定頁面，Root Topic 的部分確保設定爲 msh/TW，不要是 msh/TW/XXX 之類的，只要 msh/TW 就好，不然會收不到其他人的訊息
    * 確認後按下儲存 → 裝置會重開機，等它開完機並重新連上手機即完成
* 在使用 MQTT 時，因爲是透過手機網路來接收與傳送訊息，因此請不要把手機網路關掉唷。