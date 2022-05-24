---
title: үшін OData мысалдары Dynamics 365 Customer Insights API интерфейстері
description: Деректерді қарап шығу үшін Customer Insights API интерфейсін сұрау үшін Ашық деректер протоколының (OData) жиі пайдаланылатын мысалдары.
ms.date: 05/10/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 007278e1330e1a8e64d524ded8496acaf83b874c
ms.sourcegitcommit: a50c5e70d2baf4db41a349162fd1b1f84c3e03b6
ms.translationtype: MT
ms.contentlocale: kk-KZ
ms.lasthandoff: 05/11/2022
ms.locfileid: "8740069"
---
# <a name="odata-query-examples"></a>OData сұрау мысалдары

Open Data Protocol (OData) HTTP сияқты негізгі протоколдарға негізделген деректерге қол жеткізу протоколы болып табылады. Ол REST for web сияқты жалпы қабылданған әдістемелерді пайдаланады. OData қызметтерін тұтыну үшін пайдалануға болатын әртүрлі кітапханалар мен құралдар бар.

Бұл мақалада кейбір жиі сұралатын мысал сұрауларының тізімі берілген [Customer Insights API интерфейстері](apis.md).

Мақсатты орталарда жұмыс істеу үшін сұрау үлгілерін өзгерту керек: 

- {serviceRoot}:`https://api.ci.ai.dynamics.com/v1/instances/{instanceId}` қайда{instanceId} сұрағыңыз келетін Customer Insights ортасының GUID болып табылады. The [ListAllInstances әрекеті](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights&operation=Get-all-instances) табуға мүмкіндік береді{InstanceId} қол жеткізе аласыз.
- {CID}: Бірыңғай тұтынушы жазбасының GUID. Мысал:`ce759201f786d590bf2134bff576c369`.
- {AlternateKey}: деректер көзі ішіндегі тұтынушы жазбасының бастапқы кілтінің идентификаторы. Мысалы: `CNTID_1002`
- {DSname}: Customer Insights жүйесіне енетін деректер көзі нысан атауы бар жол. Мысал:`Website_contacts`.
- {SegmentName}: Customer Insights ішіндегі сегменттің шығыс нысанының атауы бар жол. Мысал:`Male_under_40`.

## <a name="customer"></a>Тұтынушы

Келесі кестеде сұрау үлгілерінің жиыны бар *Тұтынушы* нысан.


|Сұрау түрі |Мысал  | Ескертпе  |
|---------|---------|---------|
|Жалғыз тұтынушы идентификаторы     | `{serviceRoot}/Customer?$filter=CustomerId eq '{CID}'`          |  |
|баламалы кілт    | `{serviceRoot}/Customer?$filter={DSname_EntityName_PrimaryKeyColumnName} eq '{AlternateKey}' `         |  Балама кілттер бірыңғай тұтынушы нысанында сақталады       |
|Select   | `{serviceRoot}/Customer?$select=CustomerId,FullName&$filter=customerid eq '1'`        |         |
|Ішінде    | `{serviceRoot}/Customer?$filter=CustomerId in ('{CID1}',’{CID2}’)`        |         |
|баламалы кілт + In   | `Customer?$filter={DSname_EntityName_PrimaryKeyColumnName} in ('{AlternateKey}','{AlternateKey}')`         |         |
|Іздеу  | `{serviceRoot}/Customer?$top=10&$skip=0&$search="string"`        |   Іздеу жолына арналған ең жақсы 10 нәтижені қайтарады      |
|Сегмент мүшелігі  | `{serviceRoot}/Customer?select=*&$filter=IsMemberOfSegment('{SegmentName}')&$top=10  `     | Сегменттеу нысанынан жолдардың алдын ала орнатылған санын қайтарады.      |

## <a name="unified-activity"></a>Бірыңғай әрекет

Келесі кестеде сұрау үлгілерінің жиыны бар *UnifiedActivity* нысан.

|Сұрау түрі |Мысал  | Ескертпе  |
|---------|---------|---------|
|CID қызметі     | `{serviceRoot}/UnifiedActivity?$filter=CustomerId eq '{CID}'`          | Нақты тұтынушы профилінің әрекеттерін тізімдейді |
|Әрекеттің уақыт шеңбері    | `{serviceRoot}/UnifiedActivity?$filter=CustomerId eq '{CID}' and ActivityTime gt 2017-01-01T00:00:00.000Z and ActivityTime lt 2020-01-01T00:00:00.000Z`     |  Уақыт шеңберіндегі тұтынушы профилінің әрекеттері       |
|Әрекет түрі    |   `{serviceRoot}/UnifiedActivity?$filter=CustomerId eq '{CID}' and ActivityType eq '{ActivityName}'`        |         |
|Көрсетілетін атау бойынша әрекет     | `{serviceRoot}/UnifiedActivity$filter=CustomerId eq ‘{CID}’ and ActivityTypeDisplay eq ‘{ActivityDisplayName}’ `        | |
|Әрекетті сұрыптау    | `{serviceRoot}/UnifiedActivity?$filter=CustomerId eq ‘{CID}’ & $orderby=ActivityTime asc`     |  Әрекеттерді өсу немесе кему бойынша сұрыптау       |
|Белсенділік сегмент мүшелігінен кеңейтілді  |   `{serviceRoot}/Customer?$expand=UnifiedActivity,Customer_Measure&$filter=CustomerId eq '{CID}'`     |         |

## <a name="other-examples"></a>Басқа мысалдар

Келесі кестеде басқа нысандар үшін үлгі сұраулар жиыны бар.

|Сұрау түрі |Мысал  | Ескертпе  |
|---------|---------|---------|
|CID шаралары    | `{serviceRoot}/Customer_Measure?$filter=CustomerId eq '{CID}'`          |  |
|Байытылған CID брендтері    | `{serviceRoot}/BrandShareOfVoiceFromMicrosoft?$filter=CustomerId eq '{CID}'`  |       |
|CID-тің байытылған мүдделері    |   `{serviceRoot}/InterestShareOfVoiceFromMicrosoft?$filter=CustomerId eq '{CID}'`       |         |
|In-Clause + Кеңейту     | `{serviceRoot}/Customer?$expand=UnifiedActivity,Customer_Measure&$filter=CustomerId in ('{CID}', '{CID}')`         | |
