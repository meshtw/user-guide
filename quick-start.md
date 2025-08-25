# 快速使用
快速入門教學影片

{%youtube 6hW40yaj3x4 %} 

感謝 [八雲無線-BX4ACP](https://www.youtube.com/@Yakumo-BX4ACP) 製作

---

給新手的提示：
1. 任何射頻裝置，請務必先安裝天線後再進行開機，Meshtastic 也是一樣，要養成好習慣。
2. 請在確認接下來不會需要使用藍牙與裝置連線時，才開啟WI-FI模式。Meshtastic ESP32 的開發板可以開啓 WI-FI 功能，但只能藍牙/WI-FI二選一，不小心開啟的朋友可以透過電腦+裝置IP與裝置連線，或者是使用 USB 與電腦或是安卓手機連線後重新開啓藍牙功能，不一定要重新刷韌體喔。
3. iOS版本中 設定>裝置>Managed Device 選項在尚未完成所有配置前，請先不要開啟，否則會無法透過BLE進行設定，可以跟第2點一樣進行 USB 與電腦或是安卓手機連線後修改回來唷。
4. 建議保持韌體更新至最新穩定版本。雖然不必每次有新版本就更新，但建議關注[官方Discord](https://meshtastic.org/docs/community/discord/)和[論壇](https://meshtastic.discourse.group/)，了解重要更新資訊。

## 1.硬體的選擇
-[硬體的選擇](/epmnQ5wqSsWzof9KkxvA4Q)
入門建議使用 HeltecV3、登山與戶外運動者可嘗試跨國購買 LILYGO TTGO T-Echo

Meshtastic支援多種硬體平台，包含：
- **ESP32系列**：如Heltec WiFi LoRa 32、TTGO T-Beam等
- **nRF52系列**：如RAK WisBlock等
- **RP2040/RP2350**：更省電的芯片選擇
- **Linux支援**：可在特定Linux設備上運行

:::warning
注意：購買前請確認硬體的頻段支援是否符合你所在地區的規範。臺灣地區能使用的是915/923MHz頻段的模塊或是設備。
:::

## 2.確認韌體版本或是燒寫韌體

-[如何更新韌體](/IsTGhz_wT1KGgLuAmBTt6Q)
Meshtastic 功能還在持續成長中，若有需要更新韌體，可以參考 https://www.facebook.com/groups/meshtastictw/permalink/414578450951353/

### 韌體更新方式
1. **網頁刷機工具**：使用Chrome或Edge瀏覽器開啟[Meshtastic Web Flasher](https://flasher.meshtastic.org/)
2. **Android用戶**：使用「nRF Device Firmware Update」應用程式更新nRF52設備
3. **命令列工具**：適合進階用戶，可使用esptool.py等工具

:::success
小技巧：首次刷機後，之後的更新會變得更簡單，可通過應用程式或網頁進行OTA更新。
:::

## 3.軟體設定

**對於LoRa設置不建議進行調整(hops,Frequency Slot,Rx Boosted Gain)，對於入門用戶來說，預設設置已經足夠**

需要設定的有：
1. 使用藍牙連上設備，輸入 Meshtastic 裝置螢幕上顯示或廠商預設的 PIN 碼
2. 裝置使用地區原先預設是 UNSET，請設定為 TW，若未設定則裝置不會收發任何訊號。 
3. 設定裝置的長名稱與短名稱
4. 點擊本文章的 QRCODE，或使用掃描方式，加入臺灣的頻道（可以視爲聊天室）設定

### 連接方式
Meshtastic設備支援多種連接方式：
- **藍牙連接**：最常用的方式，直接與手機配對
- **USB連接**：通過數據線連接至電腦或手機
- **Wi-Fi連接**（僅ESP32設備）：設備可創建Wi-Fi熱點或連接到現有網路
- **網頁客戶端**：訪問client.meshtastic.org進行配置

### 應用程式設定
1. 安裝[Meshtastic應用程式](https://play.google.com/store/apps/details?id=com.geeksville.mesh)（Android）或[iOS版本](https://apps.apple.com/us/app/meshtastic/id1586432531)
2. 開啟應用程式，連接設備（藍牙或USB）
3. 點擊「UNSET」設定地區為TW（臺灣）
4. 設定裝置名稱（長名稱和短名稱）
5. 設定頻道和加密（可使用QR碼掃描加入現有頻道）

## 4.發送數據
可以挑選頻道（聊天室）：MESH TW 或是 SignalTest 跟大家打聲招呼



:::info
**目前台灣建議採用MF方式進行設定**
[![台灣頻道 QRCODE](https://hackmd.io/_uploads/HkVtdCSDeg.png)](https://meshtastic.org/e/#CgsSAQEoATABOgIIIAo3EiCKwOEes2kk-UZfcYEkFfqSO4rspA2nhnQzs5MOmdfk3hoGTWVzaFRXJQEAAAAoATABOgIIIAo7EiDLUdyJWCmXkfOHTkolR7-6ZZQfxeEbdSNHWu9kd9QcVRoKU2lnbmFsVGVzdCUCAAAAKAEwAToCCCAKOxIgy2jnf86fTpf_4AFAf-mCwbzRoxpCV0P90dqJo0-w_SYaCkVtZXJnZW5jeSElAwAAACgBMAE6AgggEhEIARAEOAhABkgBUBZYAcgGAQ) 
:::


:::warning
**目前不建議採用LF的配置**
[![台灣頻道 QRCODE](https://hackmd.io/_uploads/B1bKd0Bwex.png)](https://meshtastic.org/e/#CgMSAQEKLxIgisDhHrNpJPlGX3GBJBX6kjuK7KQNp4Z0M7OTDpnX5N4aBk1lc2hUVyUBAAAACjMSIMtR3IlYKZeR84dOSiVHv7pllB_F4Rt1I0da72R31BxVGgpTaWduYWxUZXN0JQIAAAAKMxIgy2jnf86fTpf_4AFAf-mCwbzRoxpCV0P90dqJo0-w_SYaCkVtZXJnZW5jeSElAwAAABIRCAE4CEADSAFQEVgQaAHIBgE)
:::


### 消息類型
Meshtastic支援多種通訊功能：
- **文字消息**：基本的短消息通訊
- **位置分享**：分享GPS坐標
- **語音消息**：部分設備支援語音通訊
- **緊急警報**：發送SOS信號
- **網狀路由**：消息可通過多個設備中繼傳輸

:::info
通訊範圍取決於地形、障礙物和設備天線。在開闊地區，通訊距離可達數公里；在城市環境中，距離會縮短。
:::

## 5.設定 GPS 或開啟 FixedGPS 資訊
非必要，但如果你想要在網上的一些地圖出現自己的節點，請設置。

### GPS設定選項
- **動態GPS**：使用內建或外接GPS模組獲取實時位置
- **固定GPS**：手動設定固定位置坐標（適用於固定節點）
- **智能GPS**：僅在移動時更新位置，節省電量

### 高級功能
- **頻道管理**：創建和管理多個頻道，設定不同的加密密鑰
- **節點間路由**：設定Hop訊息轉發次數
- **電源管理**：調整發射頻率和功率以延長電池壽命
- **頻段設置**：根據地區法規選擇適當的頻段
- **外部整合**：通過MQTT、串口或API與其他系統連接

:::spoiler Meshtastic技術規格
- **支援頻段**：433/470/868/915 MHz（依地區不同）
- **發射功率**：最高20dBm（依設備及地區規範而異）
- **網路類型**：彈性網狀網路
- **加密方式**：AES-128/256加密
- **協議**：專用輕量級網狀協議
- **節點數量**：理論上單一網路可支援數百個節點
:::

## 6.常見問題解答

**Q: 為什麼我的設備無法連接到手機？**
A: 請檢查藍牙是否開啟，並確認設備有電。某些手機需要啟用位置權限才能使用藍牙搜索功能。

**Q: 訊息發送失敗或延遲很高？**
A: 檢查設備之間的距離，以及是否有障礙物阻擋。歐洲地區868MHz頻段有1%的小時工作週期限制，可能導致傳輸受限。

**Q: 電池壽命不如預期？**
A: 調整GPS和位置更新間隔，關閉不必要的功能，降低發射功率或頻率。

**Q: 如何擴展網路覆蓋範圍？**
A: 增加中繼節點，放置在戰略位置。調整天線高度和方向，使用增益更高的天線。

---

## 實用資源
- [官方文檔](https://meshtastic.org/docs/)
- [臺灣Meshtastic社群](https://www.facebook.com/groups/meshtastictw/)
- [GitHub倉庫](https://github.com/meshtastic/firmware)
- [TWC_Mesh Discord社群](https://discord.gg/2vZkuckp8E)