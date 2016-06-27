狀態監聽器
======
本章節主要說明如何設定元件狀態監聽器及除錯監聽器

* * *

### Register Init Listener

```
    sBeaconNotifyLib.setInitListener(new IInitListener() {
        @Override
        public void onSuccess() {
        //=== 啟動元件成功 ===//
        }

        @Override
        public void onError(final int errorType, final String errorMsg) {
		//=== 啟動元件失敗，錯誤代碼請參照下表 ===//
        });
```

| errorType參數名稱 | 說明 | 備註 |
|-|-|-|
| 4 |TIPS_TYPE_VERIFY_FAILED | 認證錯誤 |
| 129| DIALOG_TYPE_ERROR_NO_NET | 裝置無網路連線 |
| 130 | DIALOG_TYPE_ERROR_NO_SERVER碼 | 伺服器無回應 |
        
* * *

### Register Log Listener

```
    sBeaconNotifyLib.setLogListener(new ILogListener() {
        @Override
        public void onUpdate(final String tag, final String msg) {
        //=== 從底層傳回來之Log訊息，包含Tag及Msg ===//
        }
```
        
* * *
