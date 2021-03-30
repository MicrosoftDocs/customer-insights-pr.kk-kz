---
title: Common Data Model бағдарламасындағы Customer Insights нысаны схемалары
description: Common Data Model ішіндегі нысандармен жұмыс істеу.
ms.date: 04/17/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
ms.openlocfilehash: 6667e411a1b56e13105a6b59b7b5d249bc8141ea
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: kk-KZ
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596368"
---
# <a name="entity-schemas-in-common-data-model"></a>Common Data Model қызметіндегі нысан схемалары

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

[Common Data Model](/common-data-model/) – бұл сипаттамалы ерекшелік, сондай-ақ бизнес пен өнімділікке арналған бағдарламалардағы жиі пайдаланылатын тұжырымдамалар мен іс-әрекеттерді көрсететін стандартты нысандар анықтамасы. Бұл үлгі бақылау мен аналитикалық деректерге де қолданылады. Common Data Model жүйесі тіркелгі, бөлімше, іс, контакт, ықтимал тұтынушы, мүмкіндік және өнім секілді нақты анықталған, модульдік және кеңейтілмелі бөлімшелерді, сондай-ақ іс-әрекеттер және қызмет көрсету деңгейі жөніндегі келісімдер секілді жеткізушілермен, жұмысшылармен және тұтынушылармен өзара іс-әрекеттерді қамтамасыз етеді. Бизнеске арналған қосымша идеяларды алу үшін Common Data Model анықтамаларын кез келген адам құрып, кеңейте алады.

Бұл ортақ деректер үлгісі бағдарламалар мен деректерді біріктірушілерге деректердің бірыңғай анықтамасын беру арқылы өзара әрекеттесуді жеңілдетуге мүмкіндік береді. Common Data Model жүйесі стандартты нысандар, қарым-қатынастар, иерархиялар, белгілер және тағы басқалары бар пішімделген метадеректер жүйесін қамтиды. Ол Dynamics 365 бағдарламаларынан құрылған және 260-тан астам стандартты нысандардан тұратын GitHub жүйесінде ашық болып табылады. Ішкі және сыртқы серіктестердің ірі жүйесі Common Data Model қызметіне салалық тұжырымдамалар енгізеді.

Бүгінде бірнеше жүйелер мен платформалар, оған қоса Power BI деректер ағыны мен Azure Data Services Azure Data Services қызметтері Common Data Model жүйесін жүзеге асырады. [Тікелей Open Data Initiative](https://www.microsoft.com/open-data-initiative) жүйесінің мәнін арттыра отырып, оған Common Data Service, Dynamics 365, Power Apps, Power BI және алдағы Azure деректер қызметінде қолдау көрсетіледі.

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

[Common Data Model нысаны навигаторында](https://microsoft.github.io/CDM/) нысандарды көре аласыз. **GitHub жүйесінен жүктеңіз!** опциясын таңдаңыз түймесін басып, Customer Insights нысандарының тізімі мен олардың анықтамалары орналасатын **foundationCommon** > **crmCommon** > **шешімдер** > **customerInsights** тармағына өтіңіз.
> [!div class="mx-imgBorder"]
> ![CustomerActivity нысанын көрсететін CDM нысаны навигаторы](media/CDM-entity-navigator.png "CustomerActivity нысанын көрсететін CDM нысаны навигаторы")


[!INCLUDE[footer-include](../includes/footer-banner.md)]