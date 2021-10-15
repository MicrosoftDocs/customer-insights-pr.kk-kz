---
title: Cookie файлдарын және пайдаланушы деректерін Dynamics 365 Customer Insights платформасында сақтауға пайдаланушының келісімін басқару
description: Веб-сайтқа кірушілерді анықтау үшін cookie файлдары мен пайдаланушы келісімінің пайдаланылу жолын түсініңіз.
author: mochimochi016
ms.reviewer: mhart
ms.author: jefhar
ms.date: 09/27/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: c824e50b723fe7f3b421048bb6ab96b7a9efc31f
ms.sourcegitcommit: f1e3cc51ea4cf68210eaf0210ad6e14b15ac4fe8
ms.translationtype: HT
ms.contentlocale: kk-KZ
ms.lasthandoff: 09/27/2021
ms.locfileid: "7558878"
---
# <a name="manage-cookies-and-user-consent"></a>Cookies файлдарын және пайдаланушы келісімін басқару

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Dynamics 365 Customer Insights өзара әрекеттестігі туралы түсініктер мүмкіндігі веб-сайтқа кірушілерді анықтау үшін cookie файлдарын және (`localStorage`) кілттерді пайдаланады.

Cookie файлдары — бұл пайдаланушының веб-сайтпен өзара әрекеттесуі туралы ақпарат үзінділерін сақтайтын шағын файлдар. Олар веб-шолғыштарда сақталады. Пайдаланушылар cookie файлдары сақталған веб-сайтқа кірген кезде, шолғыш сол ақпаратты серверге жібереді, ол тек пайдаланушыға қатысты ақпаратты қайтарады. Бұл, мысалы, пайдаланушы веб-сайттан тыс кетсе де, онлайн-дүкен себетінде таңдалған заттарды сақтауға мүмкіндік беретін технология болып табылады.

## <a name="user-consent"></a>Пайдаланушы келісімі

[Деректерді қорғау бойынша жалпы регламент (GDPR)](/dynamics365/get-started/gdpr/) – бұл ұйымдардың өз пайдаланушыларының құпиялылығы мен қауіпсіздігін басқару жолын анықтайтын Еуропалық Одақ (ЕО) регламенті. Cookie файлдары GDPR арқылы қамтылған онлайн идентификатор секілді "жеке деректерді" жиі сақтайды немесе жинайды. Егер сіздің бизнесіңіз ЕО деректерін қолданатын және/немесе сататын болса, GDPR ережесінің сізге әсері болады. [Microsoft корпорациясының сізге GDPR талаптарын орындауға көмектесу жолдары туралы ақпарат алыңыз](https://www.microsoft.com/trust-center/privacy/gdpr-faqs).

Өзара әрекеттестік түсініктерінің SDK жинағына cookie немесе басқа да құпия ақпаратты сақтауына мүмкіндік беру үшін пайдаланушыларыңыз келісім бергенін көрсету қажет. Бұл конфигурацияда `userConsent` өрісін орнату арқылы SDK инициализациялау кезінде орын алады.

Егер сіз пайдаланушының келісімі жоқ екенін көрсетсеңіз, SDK ешқандай деректерді сақтамайды және пайдаланушы әрекетін бақылау үшін пайдаланылуы мүмкін оқиғаларды жібермейді. Бұрын сақталған барлық деректер шолғыштан жойылады.

Егер пайдаланушының келісім мәні көрсетілмесе, SDK пайдаланушы келісім берді деп есептейді. Бұл дегеніміз, егер сіз (біздің тұтынушы ретінде) SDK жинағында пайдаланушы келісімінің мәнін көрсетпесеңіз, деректер жиналады. Алайда егер сіз пайдаланушы келісімінің мәні "шын" болуы керек екенін көрсетсеңіз, егер пайдаланушы бас тартса немесе нақты келісім бере алмаса, деректер жиналмайды.

Төменде пайдаланушы келісімімен веб SDK жиынын инициализациялауға арналған код үзіндісі берілген:
```js
<script>
  (function(a,t,i){var e="MSEI";var s="Analytics";var o=e+"queue";a[o]=a[o]||[];var r=a[e]||function(n){var t={};t[s]={};function e(e){while(e.length){var r=e.pop();t[s][r]=function(e){return function(){a[o].push([e,n,arguments])}}(r)}}var r="track";var i="set";e([r+"Event",r+"View",r+"Action",i+"Property",i+"User","initialize","teardown"]);return t}(i.name);var n=i.name;if(!a[e]){a[n]=r[s];a[o].push(["new",n]);setTimeout(function(){var e="script";var r=t.createElement(e);r.async=1;r.src=i.src;var n=t.getElementsByTagName(e)[0];n.parentNode.insertBefore(r,n)},1)}else{a[n]=new r[s]}if(i.user){a[n].setUser(i.user)}if(i.props){for(var c in i.props){a[n].setProperty(c,i.props[c])}}a[n].initialize(i.cfg)})(window,document,{
    src:"https://download.pi.dynamics.com/sdk/web/msei-1.min.js",
    name:"EiJS",
    cfg:{
      ingestionKey:"YOUR-INGESTIONKEY",
      autoCapture:{
        view:true,
        click:true
      },
      userConsent: true
    }
  });
</script>
```

## <a name="visitor-data-storage-in-engagement-insights-capability"></a>Өзара әрекеттестік туралы түсініктер мүмкіндігіндегі келуші деректерінің сақтау орны

### <a name="cookies"></a>Cookie файлдары

- _msei
    - Анонимді пайдаланушы идентификаторын сақтайды. Бұл cookie файлы тұтынушы доменінде орнатылған және оның мерзімі 365 күнде аяқталады.

### <a name="local-storage"></a>Жергілікті жад

Сондай-ақ өзара әрекеттестік туралы түсініктер мүмкіндігі құпия емес деректерді бақылау үшін (`localStorage`) кілттерін пайдаланады. Бұл деректер сіздің серверлеріңізге немесе серверлеріңізден жіберілген трафиксіз толығымен браузерде сақталады.

- *EISession.Id*
    - Ағымдағы пайдаланушы сеансы туралы ақпаратты сақтайды, мысалы сеанс идентификаторы, басталу уақыты және мерзімінің аяқталу уақыты.
- *EISession.Previous*
    - Бұрын қаралған беттің URL мекенжайын ағымдағы сеанста сақтайды.

Жергілікті жадтағы кілттердің мерзімі автоматты түрде аяқталмайды және олар келесі SDK сеансы кезінде қалпына келтіріледі.

## <a name="deleting-cookies"></a>Cookie файлдарын жою

Сіздің тұтынушыларыңыз кез келген уақытта өз браузерлерінің параметрлері арқылы cookie файлдарын және жергілікті сақтау кілттерін қолмен жоя алады.


[!INCLUDE[footer-include](../includes/footer-banner.md)]