CHTTL Beacon Notify Lite 
===========
[![Run Status](https://api.shippable.com/projects/5704bb962a8192902e1ba498/badge?branch=master)](https://app.shippable.com/projects/5704bb962a8192902e1ba498)
[![Documentation Status](https://readthedocs.org/projects/-dc-beaconnotifydemo/badge/?version=latest)](http://-dc-beaconnotifydemo.readthedocs.io/en/latest/?badge=latest)

* * *

###### 本專案為針對 Android Studio 開發環境，若以Eclipse作為開發環境則請到[這裡][id-eclipse] ######
* * *

索引
------
+ [使用手冊][id-apiDoc]
+ [測試工具](http://bit.ly/BeaconNotifyNewRelease)
+ [錯誤回報][id-mantisBT]
+ [歷來更新][id-releaseNote]
* * *

最新消息
------
**[注意!!] 本次改版`(2.18.x)`變更了元件呼叫架構，請務必變更您原始的呼叫方式並參考使用手冊中的初始化章節**  
### Version: 2.18.06 ###
```
 1. 新增 [App][Lib] 簡訊顯示模式
 2. 新增 [App][Lib] 定位事件模式(有關事件定義及操作請參考前端編輯平台說明)
 3. 修正 [Lib] 初始呼叫元件框架架構，使呼叫元件更為彈性
 4. 修正 [Lib] 浮動泡泡顯示模式，使整個浮動泡泡更穩定、提昇效能及美化介面
 5. 更新 [Lib] 底層 SBeacon 核心元件升級為 V2.2.2
```
* * *

快速使用
------
> [注意!!] 本章節只注重於 **快速使用整個範例專案暨元件** ，不保證SDK為最新版本，因此一定要繼續 **[Update SDK](#markdown-header-update-sdk)**  

 1. 請至 **[Downloads][id-download]** 頁面，點選 `Download repository`，下載後解壓縮為一個資料夾(_名稱自訂_)至你習慣的工作環境(_work space_)中。
 2. 請下載 **[fabric.zip][id-download-fabric]** 檔案，將壓縮檔中的 `fabric.properties` 複製到 `BeaconNotifyApp\build.gradle` 同目錄下
 3. 打開 Android Studio IDE
 4. 點選 "Open an existing Android Studio Project"
 5. IDE 會詢問 "Select Modules to Include in Project Subset"，點選 `ok` 即可。
 6. IDE 開始載入專案並且自動 Build 第一次
 7. 請記得要參考 **使用手冊** 中的 [Initial Beacon SDK](https://bitbucket.org/beacondemoteam/as-beaconnotifydemo/wiki/Home#markdown-header-initial-beacon-sdk) 章節, 寫入屬於你自己專案的 **License Key**  
* * *

匯入元件專案
------
> [注意!!] 本章節只注重於 **匯入元件專案** ，不保證SDK為最新版本，因此一定要繼續 **[Update SDK](#markdown-header-update-sdk)**  

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
             //BeaconNotifyLite
             compile project(':BeaconNotifyLite')
         }

 6. 執行 `Make Project`
* * *

更新元件
------
 1. 請下載 **[BeaconNotifyLite.aar][id-download-aar]** 檔案，並覆蓋 `BeaconNotifyLite` 專案中的 `BeaconNotifyLite.aar` 檔
 2. 於 `Androdi Studio` 中點選 `Build` -> `Clean Build`，讓系統重新產生一份元件參考資源  
* * *

簡易使用元件
------
 1. 請務必先閱讀過 [使用手冊[id-apiDoc]
 2. 元件的呼叫請參考 [這裡]()
 2. Receiver 註冊範例請參考 [BeaconNotifyApp/AndroidManifest.xml](https://bitbucket.org/beacondemoteam/as-beaconnotifydemo/src/f36b509952b11a5e9fbc0cc0746a190652573bdf/BeaconNotifyApp/src/main/AndroidManifest.xml?at=master&fileviewer=file-view-default)中的 `receiver`
 3. Receiver 使用範例請參考 [BeaconNotifyApp/../Receiver](https://bitbucket.org/beacondemoteam/as-beaconnotifydemo/src/f36b509952b11a5e9fbc0cc0746a190652573bdf/BeaconNotifyApp/src/main/java/com/cht/beacon/notify/App/Receiver/?at=master) 下的檔案
* * *

Contact
------
+ 中華電信研究院匯流所 [MichaelAngelo][id-contact], Skype: ktasl.li
* * *

 [回目錄](#markdown-header-index)
* * *

[id-eclipse]: https://bitbucket.org/beacondemoteam/ec-beaconnotifydemo/src "(EC)BeaconNotifyDemo"
[id-download]: https://bitbucket.org/beacondemoteam/as-beaconnotifydemo/downloads  "專案下載"
[id-download-fabric]: https://bitbucket.org/beacondemoteam/as-beaconnotifydemo/downloads/fabric.zip  "fabric.zip"
[id-download-aar]: https://bitbucket.org/beacondemoteam/as-beaconnotifydemo/downloads/BeaconNotifyLite.aar  "BeaconNotifyLite.aar"
[id-download-aarzip]: https://bitbucket.org/beacondemoteam/as-beaconnotifydemo/downloads/BeaconNotifyLite.zip  "BeaconNotifyLite.zip"
[id-releaseNote]: https://bitbucket.org/beacondemoteam/as-beaconnotifydemo/wiki/Release%20Note
[id-updateLib]: https://bitbucket.org/beacondemoteam/as-beaconnotifydemo/wiki/Home#markdown-header-update-sdk
[id-apiDoc]: https://bitbucket.org/beacondemoteam/as-beaconnotifydemo/wiki
[id-mantisBT]: http://chtebgissue.eastasia.cloudapp.azure.com/
[id-contact]: mailto:michaelangelo@cht.com.tw