---
title: iOS SDK үлгісімен жұмысты бастау
description: iOS SDK бағдарламасын жекелендіру және іске қосу жолы туралы ақпарат
author: britl
ms.reviewer: mhart
ms.author: britl
ms.date: 06/23/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: de8291fc429ae6433301a47bfdf9a3271b1b77294fd58448c7aa6bd0783edc97
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: kk-KZ
ms.lasthandoff: 08/10/2021
ms.locfileid: "7036880"
---
# <a name="get-started-with-the-ios-sdk"></a>iOS SDK үлгісімен жұмысты бастау

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Бұл оқулық сізді iOS бағдарламасын Dynamics 365 Customer Insights өзара әрекеттестік түсініктерінің SDK үлгісімен қамтамасыз ету процесі арқылы өткізеді. Оқиғаларды порталда бес минуттан кейін немесе ертерек көре бастайсыз.

## <a name="configuration-options"></a>Конфигурация параметрлері

Келесі конфигурация опцияларын SDK үлгісіне берілген `EIConfig.plist` файлы арқылы жіберуге болады:

- **ingestionKey**: қабылдау кілті жобаға оқиғаларды жіберу үшін қолданылады.
- **autocollectAction**: әрекет оқиғасын автоматты түрде жабдықтауды қосуға немесе өшіруге арналған логикалық мән.
- **autocollectView**: көрініс оқиғасын автоматты түрде жабдықтауды қосуға немесе өшіруге арналған логикалық мән.
- **endpointUrl**: оқиғалар бағытталатын соңғы нүкте URL мекенжайы.

## <a name="prerequisites"></a>Алғышарттар

- Xcode 9+ нұсқасы
- iOS 8.2+ нұсқасы
- Қабылдау кілті (алу үшін төмендегі нұсқауларды қараңыз)

## <a name="integrate-the-sdk-into-your-application"></a>SDK үлгісін бағдарламаға ендіру

Процесті жұмыс істейтін жұмыс кеңістігін таңдау арқылы, iOS мобильді платформасын таңдау арқылы және SDK үлгісін жүктеп алу арқылы бастаңыз.

- Жұмыс кеңістігін таңдау үшін сол жақ навигация тақтасындағы жұмыс кеңістігін ауыстырғышты пайдаланыңыз.

- Егер сізде бұрыннан бар жұмыс кеңістігі болмаса,  **Жаңа жұмыс кеңістігі** түймешігін таңдаңыз және [жаңа жұмыс кеңістігін](create-workspace.md) жасау қадамдарын орындаңыз.

## <a name="configure-the-sdk"></a>SDK үлгісін конфигурациялау

SDK үлгісін жүктеп алғаннан кейін, оқиғаларды қосу және анықтау үшін онымен Xcode қызметінде жұмыс істей аласыз.

1. Жұмыс кеңістігін жасағаннан кейін **Әкімші** > **Жұмыс кеңістігі** тармағына өтіңіз және содан кейін **Орнату нұсқаулығы** параметрін таңдаңыз.

1. [Өзара әрекеттестік туралы түсініктердің iOS SDK](https://download.pi.dynamics.com/sdk/EI-SDKs/ei-ios-sdk.zip) үлгісін жүктеп алыңыз және `EIObjC.xcframework` файлын `Frameworks` қалтасына орналастырыңыз.

1. Егер `Frameworks` қалтасы жоқ болса, жоба қалтасында біреуін жасаңыз.

## <a name="enable-auto-instrumentation"></a>Автоматты жабдықтауды қосу
 
Автоматты жабдықтауды кодтаусыз оңай қосуға болады. Жоба іске қосылған кезде, ол конфигурацияланған қабылдау кілтін пайдалану арқылы `view` және `action` оқиғаларын автоматты түрде бақылайды. 

1. Жоба каталогының қалтасында берілген `EIConfig.plist` файлын жаңартыңыз және келесі өрістер үшін қосыңыз:
    - ingestionKey = `"Your-Ingestion-Key"`
    - autocollectView = ИӘ
    - autocollectAction = ИӘ

2. Содан кейін `EIConfig.plist` файлын Xcode қызметіндегі жобаға қосыңыз. 



Автоматты жабдықтауды өшіру үшін, жоба каталогының қалтасында берілген `EIConfig.plist` файлындағы келесі өрістерді жаңартыңыз. 

```objectivec
'autocollectView' = NO (to disable)
'autocollectAction' = NO (to disable)
```


## <a name="implement-custom-events"></a>Реттелетін оқиғаларды ендіру

1. Жобаны Xcode қызметінде ашыңыз және **Жалпы** параметрлерге өтіңіз. 
1. `EIObjC.xcframework` файлын "Құрылымдар, кітапханалар және ендірілген мазмұн" бөліміндегі жобаға қосыңыз.

1. Келесі код үзіндісі арқылы AppDelegate.m бағдарламасында арқаулықтың тақырып файлын импорттаңыз:

    ```objectivec
    #import <EIObjC/EIObjC.h>
    ```

1. Бағдарламадан өзара әрекеттестік туралы түсініктердің SDK үлгісін баптандырыңыз: didFinishLaunchingWithOptions.
1. **Орнату нұсқаулығы** құжатынан XML үзіндісін көшіріңіз.

    ```objectivec
    NSError *error = [NSError new];
    id<EIIAnalytics> analytics = [EIAnalyticsProvider analyticsForIngestionKey:nil error:&error];
    ```

1. Оқиғаны бақылау:

    ```objectivec
    EIEvent *event = [EIEvent new];
    event.name = @"video.log";
    [event setLongValue:320 forKey:@"duration"];
    [event setBoolValue:YES forKey:@"ad_shown"];
    [analytics trackEvent:event];
    ```

## <a name="set-user-details-for-your-event"></a>Оқиғаға арналған пайдаланушы мәліметтерін орнату

SDK жинағы әрбір оқиғамен жіберуге болатын пайдаланушы туралы ақпаратты анықтауға мүмкіндік береді. SDK үлгісіндегі `setUser:(nonnull EIUser *)user` API кілтін шақыру арқылы пайдаланушы ақпаратын көрсетуге болады.

`Analytics` деңгейінде пайдаланушы мәліметтерін көрсету барлық телеметрияда осы ақпарат болатынын білдіреді. Алайда, егер EIEvent нысанындағы `setUser:(nonnull EIUser *)user` API кілтін шақыру арқылы оқиға деңгейінде көрсетсеңіз, тек сол нақты оқиға ғана ақпаратты қамтитын болады.

`EIUser` деректер класы NSString сипаттарын қамтиды:

- **localId**: пайдаланушының жергілікті идентификаторы.
- **authId**: түпнұсқалығы расталған пайдаланушы идентификаторы.
- **authType**: түпнұсқалығы расталған пайдаланушы идентификаторын алу үшін пайдаланылатын аутентификация түрі.
- **name**: пайдаланушы аты.
- **email**: пайдаланушының электрондық пошта мекенжайы.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
