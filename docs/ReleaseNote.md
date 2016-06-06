# Version: 2.18.06 #
```
 1. 新增 [App][Lib] 簡訊顯示模式
 2. 新增 [App][Lib] 定位事件模式(有關事件定義及操作請參考前端編輯平台說明)
 3. 修正 [Lib] 初始呼叫元件框架架構，使呼叫元件更為彈性
 4. 修正 [Lib] 浮動泡泡顯示模式，使整個浮動泡泡更穩定、提昇效能及美化介面
 5. 更新 [Lib] 底層 SBeacon 核心元件升級為 V2.2.2
```
# Version: 2.16 #
```
 1. 新增 [App][Lib] 廣告事件『加最愛』功能 [Issue #17]
 2. 修正 [App][Lib] 套件衝突問題，詳情請看 Readme.md [Issue #19]
 3. 修正 [Lib] 降低安全性以提高效能，並解決不會Block UI Thread及 NullPoint問題 [Issue #14]
 4. 調整 [App] 調整 Receiver 的註冊方式
 5. 修正 [Lib] SenseBeacon 改成一次回傳 ArrayList而非單顆DataParcelableBeacon [Issue #20]
 6. 修正 [App] SensedBeaconReceiver中Parcelable無法抓值之問題 [Issue #16]
 7. 修正 [Lib] 會Fatal Exception: java.lang.NullPointerException之問題 [Issue #14]
 8. 新增 [App] 由App控制卡片列表標題
 9. 新增 [App] 由App控制DM卡片標題
 10. 修正 [App] 註冊 Broadcast Receiver的方式 (* 若您的SDK小於此版，請務必參考範例程式
 11. 修正 [Lib] 元件啟動時間 (20sec -> 8sec)
```
# Version 2.15 #
``` 
 1. 新增 Sense Beacon 功能 (* Sense 功能請洽 技術窗口 詢問
 2. 修正 間隔時間改為 大於等於
 3. 修正 當開發者Set User Id為空時，以 UUID代替 (bit#6)
 4. 修正 套件衝突問題，未來將更新為全部以App自己引用為主
 5. 新增 setUserId 介面 (bit#4)
 6. 修正 圖片顯示套件更新，可cache圖檔(bit#5)
 7. 修正 統計資料的更新 (bit#3)
 8. 新增 錯誤回報機制
 9. 修正 訊息無法更新的錯誤 (bit#1)
 10. 修正 服務重啟有可能的錯誤 (bit#2)
```
# Version 2.14 #
```
* 修正 後端平台無事件會造成服務崩潰
* 修正 啟動SDK會有數秒的黑屏
* 修正 藍牙狀態變更導致服務發生錯誤
* 修正 混碼所造成的衝突
* 更新 sBeacon SDK 至 2.1.7T版本
* 修正 ANR問題
* 修正 穩定性及效能提昇
```
# Version 2.13 #
```
* 更新 sBeacon SDK 至 2.1.6版本
* 修正 偶發性 ANR之問題
* 修正 效能提昇
* 修正 資料未下載完就感測到Beacon發生的錯誤
* 修正 除錯訊息會一直重複出現的問題
* 更新 延長與伺服器檢查更新時間為 3分鐘
* 修正 前景背景切換一直連線伺服器之問題
* 修正 卡片主內容也可以點擊觸發Action
* 修正 減少程式記憶體用量
* 更新 連線套件版本更新
* 新增 一個新的無UI介面模式
* 修正 減少程式記憶體用量
* 修正 泡泡打開後關閉會發生無回應之問題
* 新增 客製化事件特殊字元回傳參數之功能
```