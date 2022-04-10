---
title: Бұрын аутентификацияланған кірушілерден "белгісізден белгіліге" мүмкіндігімен веб-оқиғаларды анықтау
description: "\"Белгісізден белгіліге\" мүмкіндігі веб-сайттағы оқиғаларды бұған дейін аутентификацияланған келушілермен байланыстыруға мүмкіндік береді."
ms.reviewer: mhart
ms.author: mkisel
author: mkisel11
ms.date: 7/15/2021
ms.subservice: engagement-insights
ms.topic: overview
ms.manager: shellyha
ms.openlocfilehash: 75ce776fd5be1c426508ae6f5c239c86bdd3ec39
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: HT
ms.contentlocale: kk-KZ
ms.lasthandoff: 02/16/2022
ms.locfileid: "8230687"
---
# <a name="recognize-web-events-from-previously-authenticated-visitors"></a>Бұрын аутентификацияланған кірушілерден веб-оқиғаларды анықтау

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Өзара әрекеттестік туралы пайдалы мәліметтер мүмкіндігіндегі **белгісізден белгіліге** мүмкіндігі веб-сайттағы оқиғаларды бұған дейін аутентификацияланған келушілермен байланыстыруға мүмкіндік береді. Егер бұл мүмкіндік өшірілген болса, алдыңғы сапар кезінде аутентификациядан өткен, содан кейін қайтып оралған кезде қайта аутентификациядан өтпеген келушілер анықталмайды. 

Мысалы, бір адам өткен аптада веб-сайтқа кіріп, сайттағы пайдаланушы тіркелгісіне кірді және өнім каталогын қарады. Адам келесі аптада есептік жазбасына кірместен басқа өнімдерді қарау үшін оралады. Сайт иесі **белгісізден белгіліге** мүмкіндігі арқылы сол адамның қайтып келгенін және сайтта не істегенін біледі. Бұл веб-сайттың әрекеттерін дәлірек есептеуге және талдауға мүмкіндік береді.

## <a name="enable-unknown-to-known"></a>"Белгісізден белгіліге" мүмкіндігін қосу

Бұл мүмкіндікті қосу үшін [жұмыс кеңістігі әкімшісі](user-roles.md) болуыңыз қажет. 

1. Өзара әрекеттестік туралы пайдалы мәліметтерде **Әкімші** > **Жұмыс кеңістігі** тармағына өтіңіз. 
2. **Параметрлер** қойыншасын таңдаңыз.
3. **Белгісізден белгіліге** бөлімінде қосқышты **Қосулы** күйіне орнатыңыз.

!["Белгісізден белгіліге" мүмкіндігін қосу](media/U2Ktoggle.png "&quot;Белгісізден белгіліге&quot; мүмкіндігін қосу")

## <a name="adding-javascript-code-to-your-sites-tracking-snippet"></a>Сайттың бақылау үзіндісіне JavaScript кодын қосу

Веб-сайт [өзара әрекеттестік туралы пайдалы мәліметтердің Web SDK құралы](advanced-SDK-implementation.md) арқылы келесі JavaScript үлгісімен **пайдаланушы аутентификациясының идентификаторын** түсіре алады. **Белгісізден белгіліге** мүмкіндігінің жұмыс істеуі үшін authId параметрін түсіріп, пайдаланушыны салыстыру мүмкіндігін *қосу* қажет: төмендегі үлгідегі JavaScript үзіндісінде рас.

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
},
userMapping: true
},
user:{
authId: getLoggedInUserId()*,
email: getLoggedInUserEmail()*,
authType: "MSA",
name: "Alex Jensen"
}
[…]
```

[!INCLUDE[footer-include](../includes/footer-banner.md)]
