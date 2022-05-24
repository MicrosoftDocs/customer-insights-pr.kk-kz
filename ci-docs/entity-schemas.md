---
title: Common Data Model бағдарламасындағы Customer Insights нысаны схемалары
description: Common Data Model ішіндегі нысандармен жұмыс істеу.
ms.date: 08/13/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
ms.openlocfilehash: 33a0562854e97b9ac5218e060f965996305627fd
ms.sourcegitcommit: d45c00a5f6cb106714366af81e8070e7f53654b3
ms.translationtype: MT
ms.contentlocale: kk-KZ
ms.lasthandoff: 05/15/2022
ms.locfileid: "8757439"
---
# <a name="entity-schemas-in-common-data-model"></a>Common Data Model қызметіндегі нысан схемалары



[Common Data Model](/common-data-model/) – бұл сипаттамалы ерекшелік, сондай-ақ бизнес пен өнімділікке арналған бағдарламалардағы жиі пайдаланылатын тұжырымдамалар мен іс-әрекеттерді көрсететін стандартты нысандар анықтамасы. Бұл үлгі бақылау мен аналитикалық деректерге де қолданылады. Common Data Model жүйесі тіркелгі, бөлімше, іс, контакт, ықтимал тұтынушы, мүмкіндік және өнім секілді нақты анықталған, модульдік және кеңейтілмелі бөлімшелерді, сондай-ақ іс-әрекеттер және қызмет көрсету деңгейі жөніндегі келісімдер секілді жеткізушілермен, жұмысшылармен және тұтынушылармен өзара іс-әрекеттерді қамтамасыз етеді. Бизнеске арналған қосымша идеяларды алу үшін Common Data Model анықтамаларын кез келген адам құрып, кеңейте алады.

Бұл ортақ деректер үлгісі бағдарламалар мен деректерді біріктірушілерге деректердің бірыңғай анықтамасын беру арқылы өзара әрекеттесуді жеңілдетуге мүмкіндік береді. Common Data Model жүйесі стандартты нысандар, қарым-қатынастар, иерархиялар, белгілер және тағы басқалары бар пішімделген метадеректер жүйесін қамтиды. Ол Dynamics 365 бағдарламаларынан құрылған және 260-тан астам стандартты нысандардан тұратын GitHub жүйесінде ашық болып табылады. Ішкі және сыртқы серіктестердің ірі жүйесі Common Data Model қызметіне салалық тұжырымдамалар енгізеді.

Қазіргі уақытта Power BI деректер ағыны мен Azure Data Services жүйелерімен қоса Common Data Model жүйесі бірнеше жүйелер мен платформаларда жүзеге асырылады. Оған Microsoft Dataverse, Dynamics 365, Power Apps, Power BI және алдағы Azure деректер қызметтерінде қолдау көрсетіледі, ол [Open Data Initiative](https://dynamics.microsoft.com/en-us/open-data-initiative/) қызметінің құндылығын тікелей арттырады.

## <a name="customer-insights-entity-schemas"></a>Customer Insights нысаны схемалары

Тұтынушының 360 градустық көрінісін орнатып, Customer Insights үлгілерін кеңейту үшін Common Data Model қызметінде қолжетімді ету үшін келесі нысан схемаларын жарияладық:

| Нысан | Сипаттамасы |
|---------|---------|
|[Реттелетін әрекет](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/customeractivity) | Бизнесті бақылау мәні бар пайдаланушы арқылы орындалатын әрекет. |
|[Тұтынушы профилі](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/customerprofile) | Бизнес әрекеттерді орындайтын немесе оған қатысу ықтималдығы бар адам немесе ұйым. |
|[Өлшем анықтамасы](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/measuredefinition) | Нөл немесе одан көп өлшемдерге бөлінген KPI көрсеткіштерінің анықтамасы (мысалы, ай сайынғы белсенді пайдаланушылар, тұтынушы арқылы жасалған жалпы шығын, тұтынушыларды тартудың орташа құны) |
|[Сегмент](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/segment) | Жалпы ерекшеліктері бар мүшелер тобын анықтайды. |
|[Сегменттер мүшелігі](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/segmentmembership) | Берілген сегментке қатысатын мүшелер. |

Толығырақ ақпарат алу үшін [Common Data Model қызметіндегі Customer Insights нысан схемалары](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/overview) жөнінде құжаттаманы қараңыз.

## <a name="view-entities-using-the-common-data-model-entity-navigator"></a>Common Data Model нысан навигаторы арқылы нысандарды қарау

[Common Data Model нысаны навигаторында](https://microsoft.github.io/CDM/) нысандарды көре аласыз. Customer Insights нысандары мен олардың анықтамаларын алу үшін Insights бағдарлама бөлімінен нысанды таңдаңыз.
> [!div class="mx-imgBorder"]
> ![CustomerActivity нысанын көрсететін CDM нысаны навигаторы.](media/CDM-entity-navigator.png "CustomerActivity нысанын көрсететін CDM нысаны навигаторы")


[!INCLUDE [footer-include](includes/footer-banner.md)]
