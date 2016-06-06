Welecome Beacon 感知元件 使用手冊
======
本元件為 中華電信研究院 Beacon 技術研發團隊 開發製作
若有任何問題歡迎請直接聯繫 **[技術窗口][id-contact]**
* * *

Index
======
+ [Announcements](http://-dc-beaconnotifydemo.readthedocs.io/en/latest/announcements/)
+ [Relative Resources](http://-dc-beaconnotifydemo.readthedocs.io/en/latest/#import-sample-project)
+ [Import Sample Project](#markdown-header-import-sample-project)
+ [Import SDK](#markdown-header-import-sdk)
+ [Update SDK](#markdown-header-update-sdk)
+ Control Beacon SDK
    + [Initial Beacon SDK](#markdown-header-initial-beacon-sdk)
+ [Set Reference Value](#markdown-header-set-reference-value)
+ Control Advertise Event
    + [Set Advertise Event Reference Value](#markdown-header-set-advertise-event-reference-value)
    + [Control Advertise Event UI](#markdown-header-control-advertise-event-ui)
+ Get Event Content
    + [Get Custom Event Content](#markdown-header-get-custom-event-content)
    + [Get Custom Advertise Event Content](#markdown-header-get-custom-advertise-event-content)
    + [Get Add Favorite Event Content](#markdown-header-get-add-favorite-event-content)
+ Get Sensed Beacon Content
    + [Get Sensed Beacon Array Content](#markdown-header-get-sensed-beacon-array-content)
+ [Finally](#markdown-header-finally)
* * *

Relative Resources
======
| 資源名稱 | 說明 | 備註 |
|-|-|-|
| 測試程式 | 各客戶的測試程式 | [鍊結](http://bit.ly/BeaconNotifyNewRelease)
| BeaconNotifyLite.aar | BeaconNotify元件檔 | [下載][id-download-aar]|
| fabric.zip | 元件必要用套件設定檔 | [下載][id-download-fabric] |


 [回目錄](#markdown-header-index)
* * *

Import Sample Project
======
> [注意!!] 本章節只注重於 **匯入範例專案** ，不保證SDK為最新版本，因此一定要繼續 **[Update SDK](#markdown-header-update-sdk)**  
``` 
 *如果你是第一次開發 Android 應用程式，建議你先了解如何開發 Android 應用程式後再來使用元件* 
```
本元件使用 Android Studio 作為開發工具(IDE)，因此建議使用 Android Studio 作為開發工具最為快速。

> Android Studio的安裝教學官方網站上有許多資源，請自行參考([Link](http://developer.android.com/intl/zh-tw/sdk/index.html))  

### Android Studio
 1. 請至 **[Downloads][id-download]** 頁面，點選 `Download repository`，下載後解壓縮為一個資料夾(_名稱自訂_)至你習慣的工作環境(_work space_)中。
 2. 請下載 **[fabric.zip][id-download-fabric]** 檔案，將壓縮檔中的 `fabric.properties` 複製到 `BeaconNotifyApp\build.gradle` 同目錄下
 3. 打開 Android Studio IDE
 4. 點選 "Open an existing Android Studio Project"
 5. IDE 會詢問 "Select Modules to Include in Project Subset"，點選 `ok` 即可。
 6. IDE 開始載入專案並且自動 Build 第一次
 7. 請記得要參考 API文件中的 Initial Beacon SDK 章節, 寫入屬於你自己專案的 License Key

### Eclipse

> 本說明依據 Mars版本說明，而不同的Eclipse版本設定上會有所不同，請自行參考網路資料
  
 1. 請至 **Eclipse 專案中的[Downloads][id-download-ec]** 頁面，點選 `Download repository`，下載後解壓縮為一個資料夾(_名稱自訂_)至你習慣的工作環境(_work space_)中。
 2. 開啟 Eclipse IDE
 3. 選擇 `File` → `Import` → `Android` → `Existing Android Code Into Workspace` → `Next`
 4. 選擇 剛剛資料夾中的 **(Eclipse)BeaconNotifyLite** 資料夾 → `Finish`
 5. 本元件有用到 **android.support.v7**中的 **appcompat** , **cardview** , **recyclerview** , 請自行上網查詢如何匯入資源
 5. 重複步驟2. 將 **(Eclipse)BeaconNotifyApp** 專案資料夾也匯入到 Eclipse 中
 6. 檢查 **(Eclipse)BeaconNotifyApp** 的專案設定，看是否有成功與 **(Eclipse)BeaconNotifyLite** 專案相依, 若無則請將彼此相依  
 7. Eclipse 尚須安裝 fabric套件及更改註冊檔，容我後續再做文件更新

 [回目錄](#markdown-header-index)
* * *

Import SDK
======
此章節不同於[Import Sample Project](#markdown-header-import-sample-project)而是介紹如何將 SDK 匯入到 **你的應用程式專案** 中
> [注意!!] 本章節只注重於 **匯入SDK** ，不保證SDK為最新版本，因此一定要繼續 **[Update SDK](#markdown-header-update-sdk)**

### Android Studio
 1. 請下載 **[BeaconNotifyLite.zip][id-download-aarzip]** 檔案，，下載後解壓縮為 **BeaconNotifyLite** 資料夾
 2. 將此資料夾複製到 **你的project** 目錄下
 3. 請下載 **[fabric.zip][id-download-fabric]** 檔案，將壓縮檔中的 `fabric.properties` 複製到 `app\build.gradle` 同目錄下 
 4. 打開 *project\setting.gradle*檔案，於最下方新增：

         include ':BeaconNotifyLite'

 5. 於 *app\build.gradle* 中，新增如下代碼：

         buildscript {
             repositories {
                 maven { url 'https://maven.fabric.io/public' }
             }
             dependencies {
                 classpath 'io.fabric.tools:gradle:1.21.5'
             }
         }
         apply plugin: 'com.android.application'
         apply plugin: 'io.fabric'
         ...
         ...
         ...
         defaultConfig {
             applicationId "Your Application ID"
             manifestPlaceholders = [ LibApplicationId:applicationId]
         }
         ...
         ...
         ...
         dependencies {
             // Support lib
             compile 'com.android.support:support-v4:23.0.1'
             compile 'com.android.support:appcompat-v7:23.0.1'
             compile 'com.android.support:cardview-v7:23.0.1'
             //Glide, Image loader
             compile 'com.github.bumptech.glide:glide:3.7.0'
             //OkHttp
             compile 'com.squareup.okhttp3:okhttp:3.2.0'
             //EventBus
             compile 'org.greenrobot:eventbus:3.0.0'
             //Gson
             compile 'com.google.code.gson:gson:2.6.2'
         }

 6. 執行 `Make Project`

### Eclipse
因為 Eclipse 設定非常的複雜，因此未來再弄

 [回目錄](#markdown-header-index)
* * *

Update SDK
======
此章節主要是說明如何更新 Beacon Notify SDK
> BeaconNotifyLite.aar 將會跟著更新並且保持於最新的版本

### Android Studio
 1. 請下載 **[BeaconNotifyLite.aar][id-download-aar]** 檔案，並覆蓋 `BeaconNotifyLite` 專案中的 `BeaconNotifyLite.aar` 檔
 2. 點選 `Build` → `Clean Build`，讓系統重新產生一份元件參考資源

### Eclipse
因為 Eclipse 設定非常的複雜，因此未來再弄

 [回目錄](#markdown-header-index)
* * *

Control Beacon SDK
======
此章節將介紹如何使用 Beacon SDK

### Initial Beacon SDK
 1 . Get the Beacon Notify Lib instance 
```
#!java
         private static BeaconNotifyLib sBeaconNotifyLib;
         ...
         sBeaconNotifyLib = BeaconNotifyLib.getInstance();
```
 2 . Init the Beacon Notify Library
```
#!java
         sBeaconNotifyLib.initBeaconSDK(applicationId, userId, licenseKey,MessageOutcomeMode,new IInitListener() {
             @Override
             public void onSuccess() {
             //啟動成功
             //在此設定 BeaconSDK 額外參數
             }   
             @Override
             public void onError(final int errorType, final String errorMsg) {
             // 啟動失敗
             }
```
| Parameter | Description | usage |
|-|-|-|  
|*applicationId*| app的 application ID, 可用 `BuildConfig.APPLICATION_ID` 帶入|判斷授權所使用|
|*userId*| 使用者識別碼, 由app自行輸入, 預設值**可**為 *空* | 統計報表所使用 |
|*licenseKey*| 專案授權碼, 由專案管理員提供, 預設值**不可**為 *空*  |判斷授權所使用|
|*MessageOutcomeMode*| 事件呈現UI方式| **MODE_NO_UI**:無介面形式, 用於客製化事件, **MODE_BUBBLE_CARD**:有浮動泡泡按鈕及卡片列表, 用於廣告事件|

 [回目錄](#markdown-header-index)
* * *

Set Reference Value
======
### Set Beacon Scan Period  
Set the beacon scan period when Foreground Scan, Foreground between Scan, Background Scan, Background between Scan.  
> System will use the default value, if didn't call this.
```
#!java
sBeaconNotifyLib.setBeaconScanPeriod(5000, 5000, 5000, 300000);
```
* * *

### Set User ID  
Set the User ID anywhere for statistical analysis
```
#!java
sBeaconNotifyLib.setUserId(userId);
```
 [回目錄](#markdown-header-index)
* * *

Control Advertise Event
======
### Set Advertise Event Reference Value
#### Set the Beacon Notify Float Bubble Icon  
Input the *“Icon Resource Id”*, when notified, the **Bubble** will show this icon.
```
#!java
sBeaconNotifyLib.setBubbleIconResID(R.drawable.ic_logo);
```
* * *

#### Set the Beacon Notify Card List Title Name  
Input the *“Card List Title Name”*, when card list open, the **Card List Title** will show this.
```
#!java
sBeaconNotifyLib.setCardListTitleResID(R.string.str_your_title_name);
```
* * *

#### Set the Beacon default DM Banner Image  
Input the *"Icon Resource Id"*, when event display, the **DM banner** will show this image. 
```
#!java
sBeaconNotifyLib.setDefaultAdvertiseBannerImgResID(R.drawable.babber);
```
* * *

#### Set the Beacon default DM Banner Title Name  
Input the *"DM Banner Title Name"*, when event display, the **DM Banner Title Name** will show this. 
```
#!java
sBeaconNotifyLib.setDMCardTitleResID(R.string.str_card_your_dm_title);
```
* * *

#### Set the Beacon default Advertise Icon Image  
Input the *"Icon Resource Id"*, when event display, if there are no main icon, the **Icon** will show this image. 
```
#!java
sBeaconNotifyLib.setDefaultAdvertiseIconImgResID(R.drawable.ic_icon);
```
* * *

### Control Advertise Event UI
#### Show Event Float Bubble
App can show event float bubble directly when you want to show
```
#!java
sBeaconNotifyLib.showEventBubble();
```
* * *

#### Dismiss Event Float Bubble
App can close event float bubble directly when you want to close
```
#!java
sBeaconNotifyLib.closeEventBubble();
```

 [回目錄](#markdown-header-index)
* * *

Get Broadcast Event Content
======
### Get Custom Event Content
 + Register a Broadcast Receiver on AndroidManifest.xml
```
#!xml
<receiver
    android:name="yourAppID.Receiver.CustomEventReceiver"
    android:permission="yourAppID.permission.GET_ALL_TYPE_BEACONS">
    <intent-filter>
        <action android:name="receiver_custom_event" />
    </intent-filter>
</receiver>
```
 + Get the Broadcast Receiver bundle content
```
#!java
public class CustomEventReceiver extends BroadcastReceiver {
    long beaconId;
    int beaconPositionX;
    int beaconPositionY;
    String eventContent;
    String userDefineData;

    @Override
    public void onReceive(Context context, Intent intent) {
        if (intent.getExtras() != null) {
            //=== 這個事件感測的 Beacon 的ID @ ===//
            beaconId = intent.getExtras().getLong("BeaconId");
            //=== 這個事件感測的 Beacon 所在地圖中的位置 @ ===//
            beaconPositionX = intent.getExtras().getInt("BeaconX");
            beaconPositionY = intent.getExtras().getInt("BeaconY");
            //=== 這個事件的資訊 @ ===//
            eventContent = intent.getExtras().getString("EventContent");
            userDefineData = intent.getExtras().getString("UserDefineData");
        }
    }

    public long getBeaconId() {
        return beaconId;
    }

    public int getBeaconPositionX() {
        return beaconPositionX;
    }

    public int getBeaconPositionY() {
        return beaconPositionY;
    }

    public String getEventContent() {
        return eventContent;
    }

    public String getUserDefineData() {
        return userDefineData;
    }
}
```
 [回目錄](#markdown-header-index)
* * *

### Get Custom Advertise Event Content
 + Register a Broadcast Receiver on AndroidManifest.xml
```
#!xml
<receiver
    android:name="yourAppID.Receiver.CustomAdvertiseEventReceiver"
    android:permission="yourAppID.permission.GET_ALL_TYPE_BEACONS">
    <intent-filter>
        <action android:name="receiver_custom_advertise_event" />
    </intent-filter>
</receiver>
```
 + Get the Broadcast Receiver bundle content
```
#!java
public class CustomAdvertiseEventReceiver extends BroadcastReceiver {
    int mBeaconPositionX;
    int mBeaconPositionY;
    String mCardTitle;
    String mCardContent1;
    String mCardContent2;
    String mCardActionContent;

    @Override
    public void onReceive(Context context, Intent intent) {
        if (intent.getExtras() != null) {
            //=== 這個事件感測的 Beacon 所在微地圖中的位置 @ ===//
            mBeaconPositionX = intent.getExtras().getInt("BeaconX");
            mBeaconPositionY = intent.getExtras().getInt("BeaconY");
            //=== 這個事件的資訊 @ ===//
            mCardTitle = intent.getExtras().getString("CardTitle");
            mCardContent1 = intent.getExtras().getString("CardContent1");
            mCardContent2 = intent.getExtras().getString("CardContent2");
            mCardActionContent = intent.getExtras().getString("CardActionContent");
        }
    }

    public int getBeaconPositionX() {
        return mBeaconPositionX;
    }

    public int getBeaconPositionY() {
        return mBeaconPositionY;
    }

    public String getCardTitle() {
        return mCardTitle;
    }

    public String getCardContent1() {
        return mCardContent1;
    }

    public String getCardContent2() {
        return mCardContent2;
    }

    public String getCardActionContent() {
        return mCardActionContent;
    }
}
```
 [回目錄](#markdown-header-index)
* * *

### Get Add Favorite Event Content
 + Register a Broadcast Receiver on AndroidManifest.xml
```
#!xml
<receiver
    android:name="yourAppID.Receiver.AddFavoriteReceiver"
    android:permission="yourAppID.permission.GET_ALL_TYPE_BEACONS">
    <intent-filter>
        <action android:name="receiver_add_favorite" />
    </intent-filter>
</receiver>
```
 + Get the Broadcast Receiver bundle content
```
#!java
public class AddFavoriteReceiver extends BroadcastReceiver {
    @Override
    public void onReceive(Context context, Intent intent) {
        if (intent.getExtras() != null) {
            long eventID = intent.getExtras().getLong("EventID");
            String endDate = intent.getExtras().getString("EndDate");
            String mainIconURL = intent.getExtras().getString("MainIconURL");
            String backgroundImgURL = intent.getExtras().getString("BackgroundImgURL");
            String cardTitle = intent.getExtras().getString("CardTitle");
            String cardContent1 = intent.getExtras().getString("CardContent1");
            String cardContent2 = intent.getExtras().getString("CardContent2");
            int cardAction = intent.getExtras().getInt("CardAction");
            String cardActionContent = intent.getExtras().getString("CardActionContent");
        }
    }
}
```
 [回目錄](#markdown-header-index)
* * *

Get Sensed Beacon Content
======
### Get Sensed Beacon Array Content
 + Register a Broadcast Receiver on AndroidManifest.xml
```
#!xml
<receiver
    android:name="yourAppID.Receiver.SensedBeaconReceiver"
    android:permission="yourAppID.permission.GET_ALL_TYPE_BEACONS">
    <intent-filter>
        <action android:name="receiver_sense_beacon" />
    </intent-filter>
</receiver>
```
 + Get the Broadcast Receiver bundle content
```
#!java
public class SensedBeaconReceiver extends BroadcastReceiver {
    @Override
    public void onReceive(Context context, Intent intent) {
        ArrayList<DataParcelableBeacon> parcelablesArrayList = intent.getParcelableArrayListExtra("sBeaconArrayList"); //=== [ISSUE#20](https://bitbucket.org/michaelangelo/beaconnotifylib/issues/20/beacon-beacon) ===//
        for (DataParcelableBeacon dataParcelableBeacon : parcelablesArrayList) {
            int a = dataParcelableBeacon.getRSSI();
        }
    }
}
```
 [回目錄](#markdown-header-index)
* * *

Finally
======
#最後，祝您使用愉快！
#中華電信研究院 Beacon 技術研發團隊 敬上


[id-download-doc]: https://bitbucket.org/beacondemoteam/as-beaconnotifydemo/downloads/ "使用手冊下載"
[id-contact]: mailto:michaelangelo@cht.com.tw
[id-download]: https://bitbucket.org/beacondemoteam/as-beaconnotifydemo/downloads  "專案下載"
[id-download-fabric]: https://bitbucket.org/beacondemoteam/as-beaconnotifydemo/downloads/fabric.zip  "fabric.zip"
[id-download-aar]: https://bitbucket.org/beacondemoteam/as-beaconnotifydemo/downloads/BeaconNotifyLite.aar  "BeaconNotifyLite.aar"
[id-download-aarzip]: https://bitbucket.org/beacondemoteam/as-beaconnotifydemo/downloads/BeaconNotifyLite.zip  "BeaconNotifyLite.zip"
