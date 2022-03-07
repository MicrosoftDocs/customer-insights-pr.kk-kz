---
title: Кеңейтілген веб-SDK сценарийлері
description: SDK көмегімен веб-сайтыңызды құралдармен қамтамасыз ету кезінде ескеру қажет кеңейтілген сценарийлер.
author: britl
ms.reviewer: mhart
ms.author: britl
ms.date: 11/12/2020
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: 7455d276035bfaf1f8a93d0e3b0b0884353a4010715c05d1d696309f7eb4b233
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: kk-KZ
ms.lasthandoff: 08/10/2021
ms.locfileid: "7036335"
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
    
Келесі мысалда пайдаланушы туралы ақпаратты жіберетін код үзіндісі көрсетілген. * белгісімен белгіленген Функциялар өрісін көргенде оны келесі мәндерді шақырумен ауыстырыңыз:  

```
[…]
window, document 
{
    src:"https://download.pi.dynamics.com/sdk/web/mspi-0.min.js", 
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

Сондай-ақ пайдаланушы ақпаратын SDK жинағында `setUser(user: IUser)` API мүмкіндігін шақыру арқылы көрсетуге болады. `setUser API` мүмкіндігін шақырғаннан кейінгі телеметрия пайдаланушы ақпаратын қамтиды.

## <a name="adding-custom-properties-for-each-event"></a>Әрбір оқиға үшін реттелетін сипаттарды қосу

SDK жинағы әрбір оқиғамен жіберуге болатын реттелетін сипаттарды көрсетуге мүмкіндік береді. Реттелетін сипаттарды нысаннан тұратын кілт мәні жұптары ретінде көрсетуге болады (мән `string | number | boolean` түрінде болуы мүмкін). Нысан код үзіндісі конфигурациясындағы `src`, `name` және `cfg` ұқсас `props` деп аталатын сипатта қосылуы мүмкін. 

Келесі мысалда реттелетін сипаттарды жіберетін код үзіндісі көрсетілген:

```
[…]
window, document 
{
    src:"https://download.pi.dynamics.com/sdk/web/mspi-0.min.js", 
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

Сондай-ақ реттелетін сипаттарды жекелей SDK жинағында `setProperty(name: string, value: string | number | boolean)` API элементін шақыру арқылы көрсетуге болады.

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