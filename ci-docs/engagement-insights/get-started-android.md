---
title: Android SDK пайдалануды бастаңыз
description: Android SDK жекелендіру және іске қосу жолын үйреніңіз
author: britl
ms.reviewer: mhart
ms.author: britl
ms.date: 10/19/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: c678c2dafbb77926269b5602bca363c678ec6b3f
ms.sourcegitcommit: ef823f3d7fa28d3a90cfde9409be9465ffa2cf09
ms.translationtype: HT
ms.contentlocale: kk-KZ
ms.lasthandoff: 10/19/2021
ms.locfileid: "7655349"
---
# <a name="get-started-with-the-android-sdk"></a>Android SDK-мен бастаңыз

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Бұл оқулық Android қолданбасын Dynamics 365 Customer Insights engagement insights SDK көмегімен құралға келтіру процесінде сізге нұсқау береді. Оқиғаларды порталда бес минуттан кейін немесе ертерек көре бастайсыз.

## <a name="configuration-options"></a>Конфигурация параметрлері
SDK үлгісіне келесі конфигурация опцияларын жіберуге болады:

- **ingestionKey**: қабылдау кілті сіздің жұмыс кеңістігіңізге оқиғаларды жіберу үшін қолданылады.

## <a name="prerequisites"></a>Алғышарттар

- Android Studio

- Ең аз Android API деңгейі: 16 (Jelly Bean)

- Қабылдау кілті (алу туралы нұсқаулық үшін төменгі жақты қараңыз)

## <a name="integrate-the-sdk-into-your-application"></a>SDK үлгісін бағдарламаға ендіру
Жұмыс кеңістігін таңдау, Android мобильді платформасын таңдау және Android SDK жүктеп алу арқылы процесті бастаңыз.

- Жұмыс кеңістігін таңдау үшін сол жақ навигация тақтасындағы жұмыс кеңістігін ауыстырғышты пайдаланыңыз.

- Егер сізде бұрыннан бар жұмыс кеңістігі болмаса,  **Жаңа жұмыс кеңістігі** түймешігін таңдаңыз және [жаңа жұмыс кеңістігін](create-workspace.md) жасау қадамдарын орындаңыз.

- Жұмыс кеңістігін жасағаннан кейін **Әкімші** > **Жұмыс кеңістігі** тармағына өтіңіз және содан кейін  **Орнату нұсқаулығы** параметрін таңдаңыз.

## <a name="configure-the-sdk"></a>SDK үлгісін конфигурациялау

SDK жүктеп алғаннан кейін оқиғаларды қосу және анықтау үшін онымен Android Studio ішінде жұмыс істеуге болады. Оның екі жолы бар:
### <a name="option-1-use-jitpack-recommended"></a>1-нұсқа: JitPack пайдалану (ұсынылады)
1. JitPack репозиторийін негізгі `build.gradle` қосыңыз:
    ```gradle
    allprojects {
        repositories {
            ...
            maven { url 'https://jitpack.io' }
        }
    }
    ```

1. Тәуелділікті қосыңыз:
    ```gradle
    dependencies {
        implementation 'com.github.microsoft:engagementinsights-sdk-android:v1.0.0'
        api 'com.google.code.gson:gson:2.8.1'
    }
    ```

### <a name="option-2-use-download-link"></a>2-нұсқа: Жүктеп алу сілтемесін пайдаланыңыз
1. жүктеп алыңыз [қатысу туралы түсініктер Android SDK](https://download.pi.dynamics.com/sdk/EI-SDKs/ei-android-sdk.zip), және қойыңыз`eiandroidsdk-debug.aar` ішіндегі файл`libs` қалта.

1. Жоба деңгейіндегі `build.gradle` файлын ашып, келесі үзінділерді қосыңыз:
    ```gradle
    dependencies {
        implementation(name: 'eiandroidsdk-debug', ext: 'aar')
        api 'com.google.code.gson:gson:2.8.1'
    }

    repositories {
        flatDir {
            dirs 'libs'
        }
    }
    ```

## <a name="enable-auto-instrumentation"></a>Автоматты жабдықтауды қосу

1. `manifests` қалтасында орналасқан `AndroidManifest.xml` файлында желіге және интернетке рұқсат қосыңыз:
    ```xml
    <manifest>
        ...
        <uses-permission android:name="android.permission.INTERNET" />
        <uses-permission android:name="android.permission.ACCESS_NETWORK_STATE" />
    ```

1. `AndroidManifest.xml` файлы арқылы өзара әрекеттестік туралы түсініктердің SDK конфигурациясын орнатыңыз.

1. **Орнату нұсқаулығы** құжатынан XML үзіндісін көшіріңіз. `Your-Ingestion-Key` кілті автоматты түрде толтырылуы керек.

   > [!NOTE]
   > `${applicationId}` бөлімін ауыстырудың қажеті жоқ. Ол автоматты түрде толтырылады.


   ```xml
   <application>
   ...
       <provider
           android:authorities="${applicationId}.com.microsoft.engagementinsights.AnalyticsContentProvider"
           android:name="com.microsoft.engagementinsights.AnalyticsContentProvider" />
       <meta-data
           android:name="com.microsoft.engagementinsights.ingestionKey"
           android:value="Your-Ingestion-Key" />
       <meta-data
           android:name="com.microsoft.engagementinsights.autoCapture"
           android:value="true" />
   ...
   </application>
   ```

1. Жоғарыдағы `autoCapture` өрісін `true` немесе `false` мәніне орнату арқылы `View` оқиғаларын автоматты жазуды қосыңыз немесе өшіріңіз. 

   >[!NOTE]
   >`Action` оқиғаларды қолмен қосу керек.

1. (Қосымша) Басқа конфигурациялар соңғы нүкте коллекторының URL мекенжайын орнатуды қамтиды. Оларды енгізу кілті метадеректерінің астына қосуға болады `AndroidManifest.xml`.

   ```xml
        <meta-data
            android:name="com.microsoft.engagementinsights.endpointUrl"
            android:value="https://some-endpoint-url.com" />
   ```

## <a name="implement-custom-events"></a>Реттелетін оқиғаларды ендіру

SDK үлгісін баптандырғаннан кейін `MainActivity` ортасында оқиғалармен және олардың сипаттарымен жұмыс істеуге болады.


Java:
```java
Analytics analytics = new Analytics();
```

Kotlin:
```kotlin
var analytics = Analytics()
```

### <a name="set-property-for-all-events-optional"></a>Барлық оқиғалар үшін сипатты орнату (міндетті емес)

Java:
```java
analytics.setProperty("year", 2021);
```

Kotlin:
```kotlin
analytics.setProperty("year", 2021)
```

Мәнмәтін оқиға сипаттары үшін келесі түрлерге қолдау көрсетіледі:
- String
- Күні
- Қос
- Ұзын
- Boolean
- UUID

### <a name="track-an-event"></a>Оқиғаны бақылау

Java:
```java
Event event = new Event("video");
event.setProperty("duration", 320);
event.setProperty("ad_shown", true);
analytics.trackEvent(event);
```

Kotlin:
```kotlin
var event = Event("video")
event.setProperty("duration", 320)
event.setProperty("ad_shown", true)
analytics.trackEvent(event)
```

## <a name="set-user-details-for-your-event-optional"></a>Оқиғаға арналған пайдаланушы мәліметтерін орнату (міндетті емес)

SDK жинағы әрбір оқиғамен жіберуге болатын пайдаланушы туралы ақпаратты анықтауға мүмкіндік береді. `Analytics` деңгейіндегі `setUser(user: User)` API кілтін шақыру арқылы пайдаланушы ақпаратын көрсетуге болады.

Java:
```java
User user = new User();
user.setName("testuser");
user.setEmail("abc@xyz.com");
analytics.setUser(user);
```

Kotlin:
```kotlin
var user = User()
user.name = "testuser"
user.email = "abc@xyz.com"
analytics.setUser(user)
```

`User` деректер класы келесі жол сипаттарын қамтиды:

- **localId**: пайдаланушының жергілікті идентификаторы.
- **authId**: түпнұсқалығы расталған пайдаланушы идентификаторы.
- **authType**: аутентификацияланған пайдаланушы идентификаторын алу үшін пайдаланылатын аутентификация түрі.
- **name**: пайдаланушы аты.
- **email**: пайдаланушының электрондық пошта мекенжайы.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
