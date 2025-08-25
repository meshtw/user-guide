# 場勘使用

## Line of Sight (LOS) 地圖網站指南

:::info
**什麼是Line of Sight (LOS)?**
Line of Sight (視線)是指兩點之間無障礙物阻擋的直線路徑。在無線通訊和RF（射頻）規劃中，LOS是評估信號傳輸可行性的關鍵因素。良好的LOS路徑可以確保無線電信號傳輸的最佳效能和可靠性。
:::

### LOS在無線通訊中的重要性

- **信號強度**: LOS路徑可以最大化信號強度，減少衰減
- **可靠性**: 清晰的LOS路徑可降低信號中斷風險
- **距離**: 適當的LOS可以增加通訊的有效距離
- **干擾**: 良好的LOS規劃可以減少環境干擾

### 常見的LOS規劃考量因素

1. **地形障礙**: 山脈、丘陵、建築物等
2. **地球曲率**: 長距離傳輸需考慮地球曲率效應
3. **菲涅爾區(Fresnel Zone)**: 除了直線視線外，還需考慮信號傳播的橢圓區域
4. **天氣因素**: 雨、霧、雪等天氣狀況對信號的影響
5. **天線高度**: 調整天線高度可顯著改善LOS條件

### 推薦的LOS地圖工具

1. **Radio Mobile Online**
   - 這是一個基於Radio Mobile軟件的線上服務，用於創建專業級的RF覆蓋和LOS圖
   - **優點**: 高度專業化，提供詳細的無線電傳播分析
   - **適合用戶**: 有無線電通訊基礎知識的中級到高級用戶
   - **新手指南**: 首先設置發射點位置和天線高度，然後添加接收點進行分析
   - [訪問Radio Mobile Online](http://www.ve2dbe.com/rmonline.html)

2. **HeyWhatsThat**
   - 提供高級的視線和地平線分析工具，能夠生成包括山脈和其他地形特徵的詳細視線圖
   - **優點**: 介面直觀，提供360度全方位視線分析
   - **適合用戶**: 初學者到高級用戶皆適用
   - **新手指南**: 在地圖上點選位置，設定天線高度(elevation offset)，系統會顯示所有可視點
   - [訪問HeyWhatsThat](http://www.heywhatsthat.com)

3. **CloudRF**
   - 是一個專業的RF規劃工具，支持LOS和非LOS路徑分析，界面用戶友好
   - **優點**: 提供雲端運算，強大的模擬能力，支持多種傳播模型
   - **適合用戶**: 中級到專業無線網絡規劃人員
   - **特色功能**: 支持3D建模和多種地形數據
   - [訪問CloudRF](https://cloudrf.com/)

4. **The Splat! Project**
   - SPLAT! 是一個開源的RF信號傳播、覆蓋和地形分析工具，適用於業餘無線電愛好者和專業人士
   - **優點**: 免費開源，功能豐富，可自定義參數
   - **適合用戶**: 有技術背景的無線電愛好者
   - **限制**: 需要一定的技術知識和安裝設置能力
   - [訪問The Splat! Project](http://www.qsl.net/kd2bd/splat.html)

5. **SCADACore RF Line-of-Sight**
   - 允許用戶在Google地圖上輕鬆拖放位置並獲取點對點LOS信息
   - **優點**: 直觀易用，基於Google地圖，使用便捷
   - **適合用戶**: 初學者或需要快速評估的用戶
   - [訪問SCADACore](https://www.scadacore.com/tools/rf-path/rf-line-of-sight/)

6. **everythingRF Line of Sight Calculator**
   - 提供簡單的線上計算器，用於計算發射機和接收機之間的視線距離
   - **優點**: 快速簡便的計算工具，適合初步評估
   - **適合用戶**: 所有級別的用戶
   - [訪問everythingRF計算器](https://www.everythingrf.com/rf-calculators/line-of-sight-calculator)

### 菲涅爾區(Fresnel Zone)的重要性

:::warning
**新手必知**: 在LOS規劃中，不僅要確保視線直接可見，還需要考慮信號傳播的菲涅爾區是否被阻擋。理想情況下，至少60%的第一菲涅爾區應保持暢通。
:::

菲涅爾區是無線電信號傳播時形成的橢圓形區域。即使兩點有直接視線，但如果菲涅爾區被嚴重阻擋，信號仍可能受到顯著衰減。

![菲涅爾區示意圖](https://upload.wikimedia.org/wikipedia/commons/thumb/f/f1/Fresnel_zone.svg/500px-Fresnel_zone.svg.png)

### 進階提示

1. **結合多種工具**:
   - 使用HeyWhatsThat進行初步視線分析
   - 用CloudRF或Radio Mobile進行詳細的無線電傳播模擬
   - 使用Splat!進行高級自定義分析

2. **考慮季節變化**:
   - 樹木在夏季有茂密的樹葉可能影響信號
   - 冬季雪可能改變反射特性

3. **實地測試**:
   - LOS工具提供理論分析，實地測試仍然不可或缺
   - 使用便攜式設備在關鍵點進行測量

這些工具提供從簡單到高度複雜的分析功能，用戶可以根據自己的需求選擇合適的工具來進行LOS分析或更廣泛的無線網絡規劃。

## 實用資源

- [RF線路規劃指南(PDF)](https://gbppr.net/splat/Ingvar_Henne_Per_Thorvaldsen_Planning_of.pdf) - 詳細的無線電中繼網絡規劃教材
- [無線電覆蓋映射指南](https://freegeographytools.com/2007/mapping-radio-coverage-and-viewing-it-in-google-earth) - 使用Google Earth查看無線電覆蓋
