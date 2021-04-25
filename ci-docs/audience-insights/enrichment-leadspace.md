---
title: Үшінші тарап Leadspace арттыру платформасы арқылы компания профильдерін арттыру
description: Leadspace үшінші тарап арттыруы туралы жалпы ақпарат.
ms.date: 11/24/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-MS
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 41c56aece043c2d7658fd2655713e1e98775edec
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: kk-KZ
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597656"
---
# <a name="enrichment-of-company-profiles-with-leadspace-preview"></a>Leadspace (алдын ала қарау) көмегімен компания профильдерін толықтыру

Leadspace — бизнес - бизнес тұтынушы деректері платформасын қамтамасыз ететін деректер ғылымы компаниясы. Ол компанияларға арналған бірыңғай тұтынушы профильдері бар тұтынушыларға деректерін толықтыруына мүмкіндік береді. Арттырулар компания өлшемі, орын, саласы және т.б. сияқты қосымша төлсипаттарды қамтиды.

## <a name="prerequisites"></a>Алғышарттар

Leadspace теңшеу үшін мына алғышарттар сақталуы қажет:

- Сізде Leadspace белсенді лицензиясы және"үздіксіз кілт" (**Leadspace таңбалауышы** деп те аталады) бар. Өнім туралы мәліметтер үшін тікелей [Leadspace](https://www.leadspace.com/products/leadspace-on-demand/) желісіне хабарласыңыз.
- Сізде [әкімші](permissions.md#administrator) рұқсаттары бар.
- Компаниялар үшін [бірыңғай тұтынушы профильдері](customer-profiles.md) бар.

## <a name="configuration"></a>Теңшелім

1. Аудитория мәліметтерінде **Деректер** > **Арттыру** тармағына өтіңіз.

1. Leadspace тақтасынан **Менің деректерімді арттыру** параметрін таңдаңыз.

   :::image type="content" source="media/leadspace-tile.png" alt-text="Leadspace тақтасының скриншоты.":::

1. **Бастау** пәрменін таңдап, содан кейін белсенді **Leadspace таңбалауышы** (үздіксіз кілт) енгізіңіз. **Келісемін** құсбелгісін таңдау арқылы **Деректер құпиялығы мен сәйкестігі** келісімін қарап шығыңыз және қамтамасыз етіңіз. **Leadspace платформасына қосылу** таңдау арқылы екі кірісті де растаңыз.

1. **Деректерді салыстыру** опциясын таңдап, Leadspace жүйесіндегі компания деректерімен арттыру қажет деректер жиынтығын таңдаңыз. Барлық тұтынушы профильдерін арттыру үшін *Тұтынушы* нысанын таңдауға болады немесе сол сегменттегі тек тұтынушы профильдерін арттыру үшін сегмент нысанын таңдауға болады.

   :::image type="content" source="media/enrichment-leadspace-select-segment.png" alt-text="Тұтынушы профилі мен сегментті арттырудың бірін таңдаңыз.":::

1. **Келесі** түймешігін басып, Leadspace платформасынан тиісті компания деректерін іздеу үшін бірыңғай профильдердің қай өрістерін пайдалану керектігін анықтаңыз. **Компания атауы** өрісі қажет. Дәлдіктің жоғары сәйкестігі үшін басқа екі өріске дейін, **Компания веб-сайты** және **Компанияның орналасқан жері** өрістерін қосуға болады.

   :::image type="content" source="media/enrichment-leadspace-mapping.png" alt-text="Leadspace өрісін салыстыру тақтасы.":::
   
1. Өрісті салыстыруды аяқтау үшін **Қолдану** пәрменін таңдаңыз.

1. Компания профильдерін толықтыру үшін **Іске қосу** параметрін таңдаңыз. Арттыру қанша уақыт алатыны тұтынушылардың бірыңғай профильдерінің санына байланысты.

## <a name="enrichment-results"></a>Толықтыру нәтижелері

Толықтыруды жаңартқаннан кейін сіз жаңадан толықтырылған компания туралы деректерді [Менің толықтыруларым](enrichment-hub.md) тармағында қарап шыға аласыз. Толықтырылған профильдер саны мен соңғы жаңарту уақытын таба аласыз.

**Толықтырылған деректерді көру** параметрін таңдау арқылы әрбір толықтырылған профильдің толық көрінісіне қатынаса аласыз.

Қосымша ақпарат алу үшін [Leadspace API көрсеткіштері](https://support.leadspace.com/hc/en-us/sections/201997649-API) бөлімін қараңыз.

## <a name="next-steps"></a>Келесі қадамдар

Толықтырылған тұтынушы деректерінің негізінде жасаңыз. Тұтынушыларға жекелендірілген тәжірибелерді жеткізу үшін [сегменттер](segments.md), [шаралар](measures.md) жасаңыз және [деректерді экспорттаңыз](export-destinations.md).

## <a name="data-privacy-and-compliance"></a>Деректердің құпиялылығы мен сәйкестігі

Деректерді Leadspace платформасына жіберу үшін Dynamics 365 Customer Insights бағдарламасын қосқан кезде, Dynamics 365 Customer Insights талаптарына сәйкестік шекарасынан тыс деректерді, соның ішінде жеке деректер сияқты ықтимал құпия деректерді беруге мүмкіндік бересіз. Microsoft мұндай деректерді сіздің нұсқауыңыз бойынша тасымалдайды, бірақ Leadspace платформасының кез келген құпиялылық немесе қауіпсіздік міндеттемелеріне сәйкес келуіне жауап бересіз. Қосымша ақпаратты [Microsoft құпиялық туралы мәлімдемесі](https://go.microsoft.com/fwlink/?linkid=396732) бөлімінен қараңыз.
Бұл функцияны тоқтату үшін бұл арттыруды кез келген уақытта Dynamics 365 Customer Insights әкімшісі жоя алады.


[!INCLUDE[footer-include](../includes/footer-banner.md)]