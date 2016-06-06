CHTTL Beacon Notify Lite 
===========
[![Run Status](https://api.shippable.com/projects/5704bb962a8192902e1ba498/badge?branch=master)](https://app.shippable.com/projects/5704bb962a8192902e1ba498)
[![Documentation Status](https://readthedocs.org/projects/-dc-beaconnotifydemo/badge/?version=latest)](http://-dc-beaconnotifydemo.readthedocs.io/en/latest/?badge=latest)

* * *

###### ���M�׬��w�� Android Studio �}�o���ҡA�Y�HEclipse�@���}�o���ҫh�Ш�[�o��][id-eclipse] ######
* * *

����
------
+ [�ϥΤ�U][id-apiDoc]
+ [���դu��](http://bit.ly/BeaconNotifyNewRelease)
+ [���~�^��][id-mantisBT]
+ [���ӧ�s][id-releaseNote]
* * *

�̷s����
------
**[�`�N!!] �����睊`(2.18.x)`�ܧ�F����I�s�[�c�A�аȥ��ܧ�z��l���I�s�覡�ðѦҨϥΤ�U������l�Ƴ��`**  
### Version: 2.18.06 ###
```
 1. �s�W [App][Lib] ²�T��ܼҦ�
 2. �s�W [App][Lib] �w��ƥ�Ҧ�(�����ƥ�w�q�ξާ@�аѦҫe�ݽs�襭�x����)
 3. �ץ� [Lib] ��l�I�s����ج[�[�c�A�ϩI�s����󬰼u��
 4. �ץ� [Lib] �B�ʪw�w��ܼҦ��A�Ͼ�ӯB�ʪw�w��í�w�B���@�į�ά��Ƥ���
 5. ��s [Lib] ���h SBeacon �֤ߤ���ɯŬ� V2.2.2
```
* * *

�ֳt�ϥ�
------
> [�`�N!!] �����`�u�`���� **�ֳt�ϥξ�ӽd�ұM�׺[����** �A���O��SDK���̷s�����A�]���@�w�n�~�� **[Update SDK](#markdown-header-update-sdk)**  

 1. �Ц� **[Downloads][id-download]** �����A�I�� `Download repository`�A�U��������Y���@�Ӹ�Ƨ�(_�W�٦ۭq_)�ܧA�ߺD���u�@����(_work space_)���C
 2. �ФU�� **[fabric.zip][id-download-fabric]** �ɮסA�N���Y�ɤ��� `fabric.properties` �ƻs�� `BeaconNotifyApp\build.gradle` �P�ؿ��U
 3. ���} Android Studio IDE
 4. �I�� "Open an existing Android Studio Project"
 5. IDE �|�߰� "Select Modules to Include in Project Subset"�A�I�� `ok` �Y�i�C
 6. IDE �}�l���J�M�רåB�۰� Build �Ĥ@��
 7. �аO�o�n�Ѧ� **�ϥΤ�U** ���� [Initial Beacon SDK](https://bitbucket.org/beacondemoteam/as-beaconnotifydemo/wiki/Home#markdown-header-initial-beacon-sdk) ���`, �g�J�ݩ�A�ۤv�M�ת� **License Key**  
* * *

�פJ����M��
------
> [�`�N!!] �����`�u�`���� **�פJ����M��** �A���O��SDK���̷s�����A�]���@�w�n�~�� **[Update SDK](#markdown-header-update-sdk)**  

 1. �ФU�� **[BeaconNotifyLite.zip][id-download-aarzip]** �ɮסA�A�U��������Y�� **BeaconNotifyLite** ��Ƨ�
 2. �N����Ƨ��ƻs�� **�A��project** �ؿ��U
 3. �ФU�� **[fabric.zip][id-download-fabric]** �ɮסA�N���Y�ɤ��� `fabric.properties` �ƻs�� `app\build.gradle` �P�ؿ��U 
 4. ���} *project\setting.gradle*�ɮסA��̤U��s�W�G

         include ':BeaconNotifyLite'

 5. �� *app\build.gradle* ���A�s�W�p�U�N�X�G

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

 6. ���� `Make Project`
* * *

��s����
------
 1. �ФU�� **[BeaconNotifyLite.aar][id-download-aar]** �ɮסA���л\ `BeaconNotifyLite` �M�פ��� `BeaconNotifyLite.aar` ��
 2. �� `Androdi Studio` ���I�� `Build` -> `Clean Build`�A���t�έ��s���ͤ@������ѦҸ귽  
* * *

²���ϥΤ���
------
 1. �аȥ����\Ū�L [�ϥΤ�U[id-apiDoc]
 2. ���󪺩I�s�аѦ� [�o��]()
 2. Receiver ���U�d�ҽаѦ� [BeaconNotifyApp/AndroidManifest.xml](https://bitbucket.org/beacondemoteam/as-beaconnotifydemo/src/f36b509952b11a5e9fbc0cc0746a190652573bdf/BeaconNotifyApp/src/main/AndroidManifest.xml?at=master&fileviewer=file-view-default)���� `receiver`
 3. Receiver �ϥνd�ҽаѦ� [BeaconNotifyApp/../Receiver](https://bitbucket.org/beacondemoteam/as-beaconnotifydemo/src/f36b509952b11a5e9fbc0cc0746a190652573bdf/BeaconNotifyApp/src/main/java/com/cht/beacon/notify/App/Receiver/?at=master) �U���ɮ�
* * *

Contact
------
+ ���عq�H��s�|�׬y�� [MichaelAngelo][id-contact], Skype: ktasl.li
* * *

 [�^�ؿ�](#markdown-header-index)
* * *

[id-eclipse]: https://bitbucket.org/beacondemoteam/ec-beaconnotifydemo/src "(EC)BeaconNotifyDemo"
[id-download]: https://bitbucket.org/beacondemoteam/as-beaconnotifydemo/downloads  "�M�פU��"
[id-download-fabric]: https://bitbucket.org/beacondemoteam/as-beaconnotifydemo/downloads/fabric.zip  "fabric.zip"
[id-download-aar]: https://bitbucket.org/beacondemoteam/as-beaconnotifydemo/downloads/BeaconNotifyLite.aar  "BeaconNotifyLite.aar"
[id-download-aarzip]: https://bitbucket.org/beacondemoteam/as-beaconnotifydemo/downloads/BeaconNotifyLite.zip  "BeaconNotifyLite.zip"
[id-releaseNote]: https://bitbucket.org/beacondemoteam/as-beaconnotifydemo/wiki/Release%20Note
[id-updateLib]: https://bitbucket.org/beacondemoteam/as-beaconnotifydemo/wiki/Home#markdown-header-update-sdk
[id-apiDoc]: https://bitbucket.org/beacondemoteam/as-beaconnotifydemo/wiki
[id-mantisBT]: http://chtebgissue.eastasia.cloudapp.azure.com/
[id-contact]: mailto:michaelangelo@cht.com.tw