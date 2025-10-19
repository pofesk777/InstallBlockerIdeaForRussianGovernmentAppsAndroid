# InstallBlockerIdeaForRussianGovernmentAppsAndroid
Идея блокировщика установки гос. приложений Max, Rustore и ГосУслуги:

Можно создать приложение для Android, которое просто не даст установить Маx, Rustore, ГосУслуги, создавая конфликт разрешений и провайдеров при установке. Для этого нужно лишь добавить в манифест вашего приложения:

```xml
<permission
        android:name="ru.rostel.DYNAMIC_RECEIVER_NOT_EXPORTED_PERMISSION"
        android:protectionLevel="signature"/>
<permission
        android:name="ru.vk.store.DYNAMIC_RECEIVER_NOT_EXPORTED_PERMISSION"
        android:protectionLevel="signature"/>
    <permission
        android:name="ru.vk.store.usersstore.permission.LOAD"
        android:protectionLevel="signature"/>
    <permission
        android:name="ru.vk.store.usersstore.permission.SAVE"
        android:protectionLevel="signature"/>
    <permission
        android:name="ru.oneme.app.DYNAMIC_RECEIVER_NOT_EXPORTED_PERMISSION"
        android:protectionLevel="signature"/>

<provider
            android:name=".FakeProvider1"
            android:enabled="false"
            android:exported="false"
            android:authorities="ru.oneme.app.notifications"/>
        <provider
            android:name=".FakeProvider2"
            android:enabled="false"
            android:exported="false"
            android:authorities="ru.oneme.app.androidx-startup"/>
        <provider
            android:name=".FakeProvider3"
            android:enabled="false"
            android:exported="false"
            android:authorities="ru.oneme.app.tracer-startup"/>
        <provider
            android:name=".FakeProvider4"
            android:enabled="false"
            android:exported="false"
            android:authorities="ru.oneme.app.provider"/>
        <provider
            android:name=".FakeProvider5"
            android:enabled="false"
            android:exported="false"
            android:authorities="ru.oneme.app.firebaseinitprovider"/>
        <provider
            android:name=".FakeProvider6"
            android:enabled="false"
            android:exported="false"
            android:authorities="ru.vk.store.appmetrica.preloadinfo.retail"/>
        <provider
            android:name=".FakeProvider7"
            android:enabled="false"
            android:exported="false"
            android:authorities="ru.vk.store.firebaseinitprovider"/>
        <provider
            android:name=".FakeProvider8"
            android:enabled="false"
            android:exported="false"
            android:authorities="ru.vk.store.MailIDInitProvider"/>
        <provider
            android:name=".FakeProvider9"
            android:enabled="false"
            android:exported="false"
            android:authorities="ru.vk.store.com.inappstory.fileprovider"/>
        <provider
            android:name=".FakeProvider10"
            android:enabled="false"
            android:exported="false"
            android:authorities="ru.vk.store.verifyinitprovider"/>

<provider
            android:name=".FakeProvider11"
            android:enabled="false"
            android:exported="false" 
          android:authorities="ru.rostel.coreproject.fileProvider;ru.rostel.FileProvider"/>

<provider
android:name=".FakeProvider12"
            android:enabled="false"
            android:exported="false"

android:authorities="ru.rostel.androidx-startup"/>

<provider
android:name=".FakeProvider13"
            android:enabled="false"
            android:exported="false"
    android:authorities="ru.rostel.firebaseinitprovider"        />

<provider
android:name=".FakeProvider14"
            android:enabled="false"
            android:exported="false"
       android:authorities="ru.rostel.mlkitinitprovider"     />

<provider
android:name=".FakeProvider15"
            android:enabled="false"
            android:exported="false"
   android:authorities="ru.rostel.appmetrica.preloadinfo.retail"         />

<provider
android:name=".FakeProvider16"
            android:enabled="false"
            android:exported="false"
 android:authorities="ru.rostel.com.squareup.picasso"           />

<provider
android:name=".FakeProvider17"
            android:enabled="false"
            android:exported="false"
     android:authorities="ru.rostel.osagoinitprovider"       />

<provider
android:name=".FakeProvider18"
            android:enabled="false"
            android:exported="false"
   android:authorities="ru.rostel.AGCInitializeProvider"/>
   ```

Это можно добавить в абсолютно любое приложение и это не будет мешать его функционалу. Но если Max, Rustore, или ГосУслуги уже установлены, то уже ваше приложение нельзя будет установить. Тут важно, кто установлен первым.

Это пригодится чтобы создать иллюзию что на ваше устройство нельзя установить Max, Rustore и ГосУслуги, например если вас заставляют, а вы не хотите их устанавливать, например в таких случаях когда вас заставляют скачать Max для взаимодействия на учёбе или работе, либо ГосУслуги, чтобы оформить пушкинскую карту, либо Rustore раз у вас они не устаналиваются, но я предусмотрел это и Rustore тоже не будет.
