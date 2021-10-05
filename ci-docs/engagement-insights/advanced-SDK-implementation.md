---
title: Кеңейтілген веб-SDK сценарийлері
description: SDK көмегімен веб-сайтыңызды құралдармен қамтамасыз ету кезінде ескеру қажет кеңейтілген сценарийлер.
author: britl
ms.reviewer: mhart
ms.author: britl
ms.date: 09/27/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: 4c6646ecadbb604000d6c95b685cf6e420969a6d
ms.sourcegitcommit: f1e3cc51ea4cf68210eaf0210ad6e14b15ac4fe8
ms.translationtype: HT
ms.contentlocale: kk-KZ
ms.lasthandoff: 09/27/2021
ms.locfileid: "7558709"
---
# <a name="advanced-web-sdk-instrumentation"></a>Кеңейтілген веб-SDK бағдарламасын құралдармен қамтамасыз ету

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Бұл мақалада [веб-сайтыңызды](instrument-website.md) Dynamics 365 Customer Insights өзара әрекеттестік туралы түсініктер мүмкіндігінің SDK бағдарламасымен қамтамасыз ету кезінде ескерілуі қажет кеңейтілген сценарийлермен танысасыз.

## <a name="setting-user-details-for-your-event"></a>Оқиғаға арналған пайдаланушы мәліметтерін орнату

SDK жинағы әрбір оқиғамен жіберуге болатын пайдаланушы туралы ақпаратты анықтауға мүмкіндік береді. Пайдаланушы мәліметтерін код үзіндісі туралы ақпаратта `src`, `name` және `cfg` элементтеріне ұқсас `user` деп аталатын (осы сипаттың болжалды деректері – `IUser` нысаны) сипатта көрсетесіз.

`IUser` нысаны келесі жол сипаттарын қамтиды:

- **localId**: пайдаланушының жергілікті идентификаторы.
- **authId**: түпнұсқалығы расталған пайдаланушы идентификаторы.
- **authType**: түпнұсқалығы расталған пайдаланушы идентификаторын алу үшін пайдаланылатын аутентификация түрі.
- **name**: пайдаланушы аты.
- **email**: пайдаланушының электрондық пошта мекенжайы.

Келесі мысалда пайдаланушы туралы ақпаратты жіберетін код үзіндісі көрсетілген. Жұлдызша * белгісінің алдында функцияларды көргенде, функцияны реттелетін орындаумен ауыстырыңыз:

```
[…]
window, document
{
    src:"https://download.pi.dynamics.com/sdk/web/msei-1.min.js",
    name:"myproject",
    cfg:{
      ingestionKey:<paste your ingestion key>",
      autoCapture:{
        view:true,
        click:true
      }
    },
    user:{
      authId: getLoggedInUserId()*,
      email: getLoggedInUserEmail()*,
      authType: "MSA",
      name: "John Doe"
    }
[…]
```

Сондай-ақ `setUser(user: IUser)` API мүмкіндігін шақыру арқылы пайдаланушы туралы ақпаратты көрсетуге болады. `setUser` API мүмкіндігін шақырғаннан кейін жіберілген телеметрия пайдаланушы ақпаратын қамтиды.

## <a name="adding-custom-properties-for-each-event"></a>Әрбір оқиға үшін реттелетін сипаттарды қосу

SDK жинағы әрбір оқиғамен жіберуге болатын реттелетін сипаттарды көрсетуге мүмкіндік береді. Реттелетін сипаттарды нысаннан тұратын кілт мәні жұптары ретінде көрсетуге болады (мән `string | number | boolean` түрінде болуы мүмкін). Код үзіндісі конфигурациясында `src`,`name` және`cfg` ұқсас `props` деп аталатын қасиетке нысанды қосуға болады.

Келесі мысалда реттелетін сипаттарды жіберетін код үзіндісі көрсетілген:

```
[…]
window, document
{
    src:"https://download.pi.dynamics.com/sdk/web/msei-1.min.js",
    name:"myproject",
    cfg:{
      ingestionKey:<paste your ingestion key>",
      autoCapture:{
        view:true,
        click:true
      }
    },
    props:{
      "key_name_string": "value",
      "key_name_number": 10,
      "key_name_bool": true
    }
[…]
```

Сондай-ақ `setProperty(name: string, value: string | number | boolean)` API мүмкіндігін шақыру арқылы пайдаланушы қасиеттерін жекелей көрсетуге болады.

## <a name="sending-custom-events"></a>Реттелетін оқиғаларды жіберу

Реттелетін оқиғаларды жіберу үшін SDK жинағын пайдалануға болады. Оқиғамен жіберілетін оқиға мен сипаттар атауын көрсету қажет.

Келесі мысалда реттелетін оқиғаны бақылайтын код үзіндісі көрсетілген. "NAME" – үзінді конфигурациясындағы `name` кілтіндегі мән. Бұл – SDK жүктелген терезе нысанындағы айнымалы атау.

```
window["NAME"].trackEvent({
    name: "event_name",
    properties: {
        "duration": 320,
        "name": "getting_started",
        "ad_shown": true
    }
});
```


[!INCLUDE[footer-include](../includes/footer-banner.md)]
