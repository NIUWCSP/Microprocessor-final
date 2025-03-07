!!重要!!此程式未授權他人使用，請勿用於其他目的，如需授權請Issues請求或直接fork!!  

# Microprocessor-final
 微處理機實驗期末專題 

# 說明
目前報告已於20230615早上結束，未來更新將會放緩，歡迎大家一同更新  

# 完成程式碼
 Final.ino：整合DHT22tester.ino、Button.ino、IRsend.ino、LED.ino、MQTT.ino


# 主要貢獻
 - Tag說明：tag有v代表重要程式更新，沒有表示文件更新
 - 給予主題方向：黃坤成總監
 - 構思主題想法與實行步驟與進度監控：李杰儒組長(README.md與notion報告書)
 - 實作將四個溫度計程式顯示完成DHT22tester.ino：陳彥杰(v1.0.1)
 - 實現使用紅外線發射器實現訊號的發送ReadRemoteControl.ino：鄒閔丞(v1.0.2)
 - 設置一個物理按鍵強制開啟冷氣或關閉Button.ino：劉子睿(V1.0.3)
 - 可使冷氣接收到訊號後開啟IRsend.ino：陳柏睿(Tx)
 - 在機器上安裝紅外線接收器以記錄冷氣遙控器的紅外線訊號，並用於未來擴增機器使用ReadRemoteControl.ino(Rx)
 - 使其可在其他開發版上使用，例如arduino或ESP32等等ReadRemoteControl.ino(Rx)
 - 外接一個三色LED LED.ino：馬群勝(v1.0.4)
 - 協助測試紅外線訊號：李杰儒、陳彥杰、鄒閔丞、陳柏睿、馬群勝
 - 製作紅外線快速整理[試算表](https://docs.google.com/spreadsheets/d/1zR44exFmDHyra-3OzhaO2X6h2LUSSYcr3xJzH7o1jj8/edit#gid=1426875601)：李杰儒、陳彥杰、鄒閔丞
 - 拷貝遙控器開關紅外線訊號ReadRemoteControl.ino：李杰儒、陳彥杰、鄒閔丞(v1.0.5)
 - 完成TECO遙控器開機IRsend.ino：李杰儒、陳彥杰、鄒閔丞(v1.0.6)
 - 完成TECO遙控器關機IRsend.ino：李杰儒、陳彥杰、鄒閔丞(v1.0.7)
 - 整合(LED、IRsend、DHT22tester、Button)Final.ino：李杰儒、陳彥杰(v1.0.8)
 - buttonState連續按下超過5秒跳出while irsend的迴圈 Final.ino：李杰儒(v1.0.9)
 - 新增連接E605 WIFI功能ConnectWithWPA.ino：李杰儒(v1.0.10)
 - Debug buttonState連續按下超過5秒跳出while irsend的迴圈 Final.ino：李杰儒(v1.0.11)
 - 加入PPT與word：鄒閔丞、劉子睿(1.0.12)
 - 加入LWiFi的範例：李杰儒(1.0.13)
 - 加入使用MQTT上傳資料到Thingspeak MQTT.ino：古振宏(v1.0.14)
 - 整合程式使其可以上傳溫度到Thingspeak Final.ino：李杰儒、陳彥杰(v1.0.15)
 - 更新程式適用E608 Final.ino：李杰儒、陳彥杰(E608)
 - 協助E608布置：李杰儒、陳彥杰、陳柏睿、古振宏、馬群勝
 - 更新冷氣溫度判定溫度：李杰儒(E608v1)
 - 更新word跟PPT(影片無剪輯版)：陳柏睿(1.0.16)
 - fix bug(迴圈內加入溫度更新)：李杰儒(v1.0.17)
 - 加入console debug功能：模擬按下按鈕 Final.ino：李杰儒(v1.0.18)

# 預期目標
 根據環境溫度，當環境溫度高於設定溫度後，自動發射紅外線開啟冷氣，並經由安裝在冷氣出風口的溫度感測器判定冷氣是否開啟，並使用LED顯示冷氣開啟狀態  
 目前使用linkit7697作為主控

# 預期工作
 - 感測多個溫溼度，使用DHT22：陳彥杰(完成)
 - 實現使用紅外線發射器實現訊號的發送：鄒閔丞(完成)
 - 可使冷氣接收到訊號後開啟：陳柏睿(完成)
 - 顯示冷氣是否開啟狀態指示燈，外接一個三色LED：馬群勝(完成)
 - 設置一個物理按鍵強制開啟冷氣或關閉：劉子睿(完成)
 - 建立方便觀測數據的網頁端，可能使用node-red之類的網頁服務：古振宏(完成)
 - 在機器上安裝紅外線接收器以記錄冷氣遙控器的紅外線訊號，並用於未來擴增機器使用(完成)

# 未來方向
 - 使其可在其他開發版上使用，例如arduino(已完成)或ESP32等等
 - 將接收與發送整合在同一張板子中
 - 增加記憶按鍵功能
 - 設定增加更多可遠端Debug的方式
 - 允許OTP發送更新
 - 整合3D列印外殼

# 使用材料
 - 主控linkit7697 *1
 - 溫溼度感測DHT22 *2
 - 紅外線發射器1341-K090 *1
 - 紅外線接收器主控Arduino Uno *1
 - 紅外線接收器HX1838B *1

# 開發環境
 Arduino 1.8.19(理論上1.8.x都可)  
 將Lwifi-libraries底下的所有檔案放入本機IDE的examples裡面  
 將libraries底下的所有檔案放入本機IDE的libraries裡面  
 
# 實作照片
 ![20230615_105534](https://github.com/Goldbeibei/Microprocessor-final/assets/121147600/ee3b1c59-b70a-44ea-bd07-2629694d5dac)
 ![20230615_105527](https://github.com/Goldbeibei/Microprocessor-final/assets/121147600/f2aafbd2-5312-41bc-a2d5-1e5bd75a0c3d)
 ![20230615_105537](https://github.com/Goldbeibei/Microprocessor-final/assets/121147600/ac2ffa7a-8b17-4add-8f98-86e1ca8a2a57)
 ![20230615_105544](https://github.com/Goldbeibei/Microprocessor-final/assets/121147600/42840901-5ed8-42af-96f1-90b26611a5ca)
 ![20230615_105544](https://github.com/Goldbeibei/Microprocessor-final/assets/121147600/846f754b-d179-4d70-a803-7e2c1d85e18c)
 ![20230615_105545](https://github.com/Goldbeibei/Microprocessor-final/assets/121147600/0f347ee4-476e-4a10-8b1f-c67eae466281)

 
# linkit7697腳位
- 2：DHT22(環境溫度)
- 5：DHT22(TECO小台)
- 7：DHT22(SAMPO)
- 10：DHT22(TECO大台)
- 8：強制停止按鈕
- 3：傳送紅外線
- 11：LED_B
- 12：LED_G
- 13：LED_R

# Arduino腳位
- 4：接收紅外線

# 類似功能市面產品
[switch box hub mini](https://switchbot.tw/hubmini/) 約$1200  
我們的成本linkit7697*1($425)+DHT22*1($150)+紅外線發射器1341-K090*1($60)+紅外線接收器HX1838B*1($28)=$663  

![switch box hub mini](https://switchbot.tw/_nuxt/img/product-d.0f62765.png)
