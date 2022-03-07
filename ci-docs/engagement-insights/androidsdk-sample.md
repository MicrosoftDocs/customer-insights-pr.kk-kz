---
title: Android SDK үлгісі
description: Android SDK туралы үйренуге арналған үлгі жоба
author: britl
ms.reviewer: m-hartmann
ms.author: britl
ms.date: 06/23/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: ba51961bc7f9555d7dba5b6a21c8636011438d75cba87bc132b896841c467a33
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: kk-KZ
ms.lasthandoff: 08/10/2021
ms.locfileid: "7035833"
---
# <a name="run-the-android-sdk-sample"></a>Android SDK үлгісін іске қосу

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Бұл үлгі Android жобасы SDK үлгісінің бағдарламада қалай жұмыс істейтінін түсінуге көмектеседі. Кодты жазудың қажеті жоқ. Тек қабылдау кілтін қоссаңыз, жұмыс кеңістігіндегі оқиғаларды бірден көруге болады.

## <a name="prerequisites"></a>Алғышарттар

- [Android Studio](https://developer.android.com/studio)
- [Қабылдау кілті](get-started-android.md)

## <a name="download-the-android-sdk-sample"></a>Android SDK үлгісін жүктеп алу

1. [Өзара әрекеттестік туралы түсініктердің Android SDK үлгісін жүктеп алу](https://download.pi.dynamics.com/sdk/EI-SDKs/ei-android-sample.zip).
1. Қысылған `ei-android-sample.zip` файлын мұрағаттан шығарыңыз.
1. Android Studio бағдарламасындағы мұрағатталмаған қалтаны ашыңыз.
1. `AndroidManifest.xml` файлында `"Your-Ingestion-Key"` жолын **Әкімші** > **Жұмыс кеңістігі** > **Орнату нұсқаулығы** тармағындағы өзара әрекеттестік түсініктеріндегі жұмыс кеңістігін қабылдау кілтімен ауыстырыңыз. 

   > [!NOTE]
   > `${applicationId}` бөлімін ауыстырудың қажеті жоқ. Ол автоматты түрде толтырылады.

   ```xml
   <application>
   ...
       <provider
           android:authorities="${applicationId}.com.microsoft.engagementinsights.eiandroidsdk.AnalyticsContentProvider"
           android:name="microsoft.dynamics.engagementinsights.eiandroidsdk.AnalyticsContentProvider" />
       <meta-data
           android:name="com.microsoft.engagementinsights.ingestionKey"
           android:value="Your-Ingestion-Key" />
       <meta-data
           android:name="com.microsoft.engagementinsights.autoCapture"
           android:value="true" />
   ...
   </application>
   ```

1. Үлгі жобасын бастау үшін **Іске қосу** түймешігін таңдаңыз.
1. Жұмыс кеңістігіндегі оқиғаларды көріңіз.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
