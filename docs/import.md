
Import Sample Project
======
> [�`�N!!] �����`�u�`���� **�פJ�d�ұM��** �A���O��SDK���̷s�����A�]���@�w�n�~�� **[Update SDK](#markdown-header-update-sdk)**  
``` 
 *�p�G�A�O�Ĥ@���}�o Android ���ε{���A��ĳ�A���F�Ѧp��}�o Android ���ε{����A�ӨϥΤ���* 
```
������ϥ� Android Studio �@���}�o�u��(IDE)�A�]����ĳ�ϥ� Android Studio �@���}�o�u��̬��ֳt�C

> Android Studio���w�˱оǩx������W���\�h�귽�A�Цۦ�Ѧ�([Link](http://developer.android.com/intl/zh-tw/sdk/index.html))  

### Android Studio
 1. �Ц� **[Downloads][id-download]** �����A�I�� `Download repository`�A�U��������Y���@�Ӹ�Ƨ�(_�W�٦ۭq_)�ܧA�ߺD���u�@����(_work space_)���C
 2. �ФU�� **[fabric.zip][id-download-fabric]** �ɮסA�N���Y�ɤ��� `fabric.properties` �ƻs�� `BeaconNotifyApp\build.gradle` �P�ؿ��U
 3. ���} Android Studio IDE
 4. �I�� "Open an existing Android Studio Project"
 5. IDE �|�߰� "Select Modules to Include in Project Subset"�A�I�� `ok` �Y�i�C
 6. IDE �}�l���J�M�רåB�۰� Build �Ĥ@��
 7. �аO�o�n�Ѧ� API��󤤪� Initial Beacon SDK ���`, �g�J�ݩ�A�ۤv�M�ת� License Key

### Eclipse

> �������̾� Mars���������A�Ӥ��P��Eclipse�����]�w�W�|���Ҥ��P�A�Цۦ�ѦҺ������
  
 1. �Ц� **Eclipse �M�פ���[Downloads][id-download-ec]** �����A�I�� `Download repository`�A�U��������Y���@�Ӹ�Ƨ�(_�W�٦ۭq_)�ܧA�ߺD���u�@����(_work space_)���C
 2. �}�� Eclipse IDE
 3. ��� `File` �� `Import` �� `Android` �� `Existing Android Code Into Workspace` �� `Next`
 4. ��� ����Ƨ����� **(Eclipse)BeaconNotifyLite** ��Ƨ� �� `Finish`
 5. �����󦳥Ψ� **android.support.v7**���� **appcompat** , **cardview** , **recyclerview** , �Цۦ�W���d�ߦp��פJ�귽
 5. ���ƨB�J2. �N **(Eclipse)BeaconNotifyApp** �M�׸�Ƨ��]�פJ�� Eclipse ��
 6. �ˬd **(Eclipse)BeaconNotifyApp** ���M�׳]�w�A�ݬO�_�����\�P **(Eclipse)BeaconNotifyLite** �M�׬ۨ�, �Y�L�h�бN�����ۨ�  
 7. Eclipse �|���w�� fabric�M��Χ����U�ɡA�e�ګ���A������s

 [�^�ؿ�](#markdown-header-index)
* * *

Import SDK
======
�����`���P��[Import Sample Project](#markdown-header-import-sample-project)�ӬO���Цp��N SDK �פJ�� **�A�����ε{���M��** ��
> [�`�N!!] �����`�u�`���� **�פJSDK** �A���O��SDK���̷s�����A�]���@�w�n�~�� **[Update SDK](#markdown-header-update-sdk)**

### Android Studio
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
         }

 6. ���� `Make Project`

### Eclipse
�]�� Eclipse �]�w�D�`�������A�]�����ӦA��

 [�^�ؿ�](#markdown-header-index)
* * *

Update SDK
======
�����`�D�n�O�����p���s Beacon Notify SDK
> BeaconNotifyLite.aar �N�|��ۧ�s�åB�O����̷s������

### Android Studio
 1. �ФU�� **[BeaconNotifyLite.aar][id-download-aar]** �ɮסA���л\ `BeaconNotifyLite` �M�פ��� `BeaconNotifyLite.aar` ��
 2. �I�� `Build` �� `Clean Build`�A���t�έ��s���ͤ@������ѦҸ귽

### Eclipse
�]�� Eclipse �]�w�D�`�������A�]�����ӦA��

 [�^�ؿ�](#markdown-header-index)