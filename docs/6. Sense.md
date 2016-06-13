
掃描周遭 Beacon 
======

此章節介紹如何直接掃描周遭Beacon資訊給前端應用程式

### Get Sensed Beacon Array Content

> 要使用 Sensed Beacon 必須先專案先開通掃描權限，如需申請請聯絡 **[技術窗口][id-contact]**

 + Register a Broadcast Receiver on AndroidManifest.xml
```
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
public class SensedBeaconReceiver extends BroadcastReceiver {
    @Override
    public void onReceive(Context context, Intent intent) {
        ArrayList<DataParcelableBeacon> parcelablesArrayList = 
            intent.getParcelableArrayListExtra("sBeaconArrayList");
    }
}
```

* * *

[id-contact]: mailto:michaelangelo@cht.com.tw
