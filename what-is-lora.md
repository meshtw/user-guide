# LORA 是什麼

{%youtube dxYY097QNs0 %} 

:::info
LoRa（Long Range）是一種專為物聯網（IoT）設計的低功耗、長距離無線通信技術。它採用Chirp擴頻（CSS）調變技術，具有優異的抗干擾能力和靈敏度。LoRa運行在免授權的次GHz頻段，如433 MHz、868 MHz（歐洲）、915 MHz（北美）和923 MHz（亞洲），可在鄉村地區實現超過10公里的通信範圍。其資料傳輸速率依擴頻因子而定，範圍從0.3 Kbps到27 Kbps。 
:::

## LoRa技術的基本原理

LoRa技術的核心是其獨特的調變方式 - Chirp擴頻調變（CSS, Chirp Spread Spectrum）。這種調變技術原先用於軍事和太空通信，具有以下特點：

- **抗干擾性強**：即使在噪聲較大的環境中，仍能有效傳輸數據
- **低接收靈敏度**：能夠接收非常微弱的信號，最低可達-148 dBm
- **低功耗**：節點可以使用電池運行數年
- **長距離傳輸**：在開闊區域可達15km，城市中約2-5km

### LoRa的工作原理

LoRa使用的Chirp信號是一種頻率隨時間線性變化的信號。發送數據時，LoRa將信息編碼到不同起始頻率的Chirp信號中。接收方通過識別這些Chirp信號的起始頻率來解碼原始數據。這種方式有以下優勢：

1. **擴頻因子（SF, Spreading Factor）**：數值從7到12，SF越高，通信距離越遠，但數據傳輸速率越低
2. **碼率（CR, Coding Rate）**：增加傳輸可靠性的前向糾錯機制，可以抵抗短暫的干擾
3. **帶寬（BW, Bandwidth）**：常用值為125kHz、250kHz和500kHz，影響數據傳輸速率和通信距離

![MBXY-CR-09bd676fba563bcb0f0b1905ccd544f7](https://hackmd.io/_uploads/H1yirtGxel.png)


## 歐洲頻段

歐盟國家通常受無線電設備指令([2014/53/EU](http://data.europa.eu/eli/dir/2014/53/2023-10-01))及其後續修正案的約束，這些規定隨後被納入當地法律。有關於此的有用資訊位於[此處](https://single-market-economy.ec.europa.eu/single-market/european-standards/harmonised-standards/radio-equipment_en)。

以下頻段是根據可用的最大功率和工作週期選擇的。對於特定應用可能可以使用其他頻段，但這些頻段目前不受「開箱即用」的支援。

### 433 MHz

歐洲允許的最大功率為 +10 dBm ERP ([有效輻射功率](https://en.wikipedia.org/wiki/Effective_radiated_power))。

頻段範圍為 433 至 434 MHz。

使用標準無線電預設值 `LongFast` 定義了四個頻率槽。出廠重置後，無線電將設定為頻率槽 4，中心頻率為 433.875 MHz。

### 868 MHz

歐洲允許的最大功率為 +27 dBm ERP ([有效輻射功率](https://en.wikipedia.org/wiki/Effective_radiated_power))。

頻段範圍為 869.40 至 869.65 MHz。這低於定義為 SRD ([短距離設備](https://www.etsi.org/technologies/short-range-devices)) 頻段的 863–870 MHz 範圍，但允許更高的 ERP 和 10% 的工作週期。

使用標準無線電預設值 `LongFast` 定義了一個頻率槽。出廠重置後，無線電將設定為頻率槽 1，中心頻率為 869.525 MHz。

值得注意的是，868 MHz 通常是歐洲 Meshtastic 最常用的頻段。

## 北美頻段

### 915 MHz (ISM 頻段)

北美的最大輸出功率為 +30 dBm ERP ([有效輻射功率](https://en.wikipedia.org/wiki/Effective_radiated_power))。

頻段範圍為 902 至 928 MHz。

在北美，可用的頻率槽取決於頻寬設定，這包含在所選的無線電預設值中。標準預設值 LongFast 提供 104 個頻率槽。出廠重置後，無線電預設為 LongFast，頻率槽為 0，根據通道雜湊算法，這對應於 20 號槽（中心頻率為 906.875 MHz）。


## LoRaWAN網路架構

LoRaWAN則是在LoRa技術的基礎上，實現了完整的網路協定和安全機制，使得節點之間能夠相互通信，以及與雲端進行通信，主要提供了物聯網通信所需要的網路協定和安全機制等。

:::success
### LoRaWAN網路的三層架構
1. **終端設備（End Devices）**：傳感器、執行器等，通常採用電池供電
2. **網關（Gateways）**：負責收集終端設備的數據並轉發到網路服務器
3. **網路服務器（Network Server）**：管理網路，處理數據，並轉發到應用服務器
:::

### LoRaWAN設備分類

LoRaWAN協議定義了三種不同類型的終端設備：

- **Class A**：最省電的設備類型，只在發送數據後短暫開啟接收窗口
- **Class B**：在Class A基礎上添加了定時接收窗口，適合需要定期接收指令的設備
- **Class C**：接收窗口始終開啟，延遲最低，但耗電量最大

## Meshtastic：基於LoRa的開源通信系統

Meshtastic是一個開源的通信系統，利用LoRa技術實現長距離、低功耗的數據傳輸。它特別適合在無手機信號或其他傳統通信基礎設施無法覆蓋的地區使用。Meshtastic專案允許使用者使用廉價的LoRa無線電作為長距離的離線通信平台，特別適用於缺乏現有或可靠通信基礎設施的地區。 

### Meshtastic的主要特點

- **長距離通信**：在理想條件下，通信距離可達數百公里
- **無需手機**：不需要手機即可進行網狀通信
- **去中心化**：無需專用路由器，每個節點都能充當中繼
- **加密通信**：確保通信內容的安全性
- **優異的電池壽命**：適合長時間運行
- **文本消息傳輸**：在網狀網路中發送和接收文本消息
- **可選的GPS定位功能**：支援基於GPS的定位功能


### 在台灣使用Meshtastic

在台灣，Meshtastic也有活躍的社群，提供本地化的支援和資源，協助使用者瞭解和使用這項技術。新手可以：

1. 加入「Meshtastic Taiwan」Facebook群組取得支援
2. 配置時選擇區域為「TW」（923.875Mhz）
3. 參考社群整理的「Meshtastic入門手冊」

:::spoiler Meshtastic安裝與配置步驟
1. 購買支援的硬體（如Heltec LoRa32 V3開發板）
2. 安裝Meshtastic韌體
3. 通過手機App或Web界面進行配置
4. 設置正確的區域與頻段（台灣使用TW區域）
5. 設置設備角色（一般使用者選擇CLIENT）
6. 設置通信頻道與密鑰
7. 進行通信測試
:::

## LoRa與Meshtastic的應用場景

1. **災難通信**：地震、颱風等自然災害時的緊急通信
2. **戶外探險**：登山、遠足等活動中的團隊通信
3. **智慧農業**：農田監測、灌溉控制
4. **智慧城市**：路燈控制、停車管理、環境監測
5. **資產追蹤**：物流、資產管理

總體而言，LoRa和Meshtastic的結合為在缺乏傳統通信基礎設施的地區提供了一種可靠且高效的通信解決方案，特別適合物聯網應用和戶外活動。

## 參考資料
- [WIKI LoRa](https://zh.wikipedia.org/zh-tw/LoRa)
- [LoRaWAN 技術介紹](https://www.digikey.tw/zh/resources/iot-resource-center/lora)
- [Meshtastic 中文社區](https://meshcn.net/introduction/)
- [Meshtastic Taiwan Facebook群組](https://www.facebook.com/groups/meshtastictw/)
- [八雲無線-BX4ACP: Meshtastic快速新手入門](https://www.youtube.com/watch?v=6hW40yaj3x4)

