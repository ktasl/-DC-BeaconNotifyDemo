


Welecome Beacon 感知元件 使用手冊
======
本元件為 **中華電信研究院 Beacon 技術研發團隊** 開發製作  

若有任何問題歡迎請直接聯繫 **[技術窗口](mailto:michaelangelo@cht.com.tw)**
***




特別聲明
======

- 本元件為使用 The official Android IDE: Android Studio 製作。
- 本元件最低支持Android版本為4.3.1。
- 本元件核心為自行開發外，額外使用的套件皆為開源套件，並遵守 Apache License 2.0 規範。
- 本元件所提供之各項資料，僅供參考，開發者須依照開發環境實際情況使用功能。
- 本元件有要求下列的裝置權限，皆為了感測及正常使用，為了確保元件正常使用，請開發者務必於軟體中告知使用者並要求允許這些權限的使用權限，否則將無法正常使用元件。
- 本元件作動時需網路連線，將驗證並且收集系統紀錄：包含硬體及錯誤資訊，無任何個人私密資料，並只作為開發改進系統所使用，不另使用於私人用途。

- 本元件目前僅供中華電信及其夥伴使用。
- 中華電信研究院對開發者因使用本元件所造成之損失，不負任何責任承擔及損失賠償。  
  ※ 繼續使用本元件視為同意以上聲明事項  
***




裝置權限
==================

### Dangerous permissions

| 權限名稱                   | 用途                   |
| ---------------------- | -------------------- |
| ACCESS_FINE_LOCATION   | 透過Beacon感知得知使用者位置    |
| ACCESS_COARSE_LOCATION | 透過Beacon感知得知使用者位置    |
| READ_PHONE_STATE       | 得知使用者裝置的UUID用以紀錄系統資訊 |
| CALL_PHONE             | 使浮動視窗能顯示於各視窗之上       |
| READ_EXTERNAL_STORAGE  | 讀取至於外部記憶體中的設定檔       |
| WRITE_EXTERNAL_STORAGE | 將設定檔寫入到外部記憶體中        |


### Normal permissions

| 權限名稱                   | 用途                 |
| ---------------------- | ------------------ |
| ACCESS_NETWORK_STATE   | 得知目前網路狀態           |
| ACCESS_WIFI_STATE      | 得知目前無線網路網路狀態       |
| BLUETOOTH              | 開啟藍牙               |
| BLUETOOTH_ADMIN        | 開啟藍牙               |
| INTERNET               | 網路連線               |
| READ_LOGS              | 讀取Log              |
| RECEIVE_BOOT_COMPLETED | 開機時將Beacon背景感測服務註冊 |
| SYSTEM_ALERT_WINDOW    | 使浮動視窗能顯示於各視窗之上     |
| VIBRATE                | 收到推播時震動            |

***



Relative Link
======

| 資源名稱 | 說明   | 備註                               |
| ---- | ---- | -------------------------------- |
| 專案   | 專案位址 | [鍊結](http://bit.ly/BeaconDemoAS) |

***
