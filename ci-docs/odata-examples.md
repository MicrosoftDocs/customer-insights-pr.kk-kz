---
title: Customer Insights API үшін OData сұрау мысалдары
description: Деректерді қарап шығу үшін Customer Insights API интерфейстерін сұрау үшін Ашық деректер протоколының (OData) жиі пайдаланылатын мысалдары.
ms.date: 08/30/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 26e56a3bab01ba55284a52e72efbcbfbaadaad6f
ms.sourcegitcommit: 624b27bb65a0de1970dc1ac436643b493f0a31cf
ms.translationtype: MT
ms.contentlocale: kk-KZ
ms.lasthandoff: 08/31/2022
ms.locfileid: "9387209"
---
# <a name="odata-query-examples-for-customer-insights-apis"></a>Customer Insights API үшін OData сұрау мысалдары

Open Data Protocol (OData) — HTTP сияқты негізгі протоколдарға негізделген деректерге қол жеткізу протоколы. Ол REST for web сияқты жалпы қабылданған әдістемелерді пайдаланады. OData қызметтерін тұтыну үшін пайдалануға болатын әртүрлі кітапханалар мен құралдар бар.

негізінде өзіңіздің іске асыруларыңызды құруға көмектесу үшін [Customer Insights API интерфейстері](apis.md), кейбір жиі сұралатын мысал сұрауларын қарап шығыңыз.

Мақсатты орталарда жұмыс істеу үшін сұрау үлгілерін өзгертіңіз:

- {serviceRoot}:`https://api.ci.ai.dynamics.com/v1/instances/{instanceId}/data` қайда{instanceId} сұрағыңыз келетін Customer Insights ортасының GUID болып табылады. The [ListAllInstances әрекеті](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights&operation=Get-all-instances) табуға мүмкіндік береді{InstanceId} қол жеткізе аласыз.
- {CID}: Бірыңғай тұтынушы жазбасының GUID. Мысал:`ce759201f786d590bf2134bff576c369`.
- {AlternateKey}: деректер көзі ішіндегі тұтынушы жазбасының бастапқы кілтінің идентификаторы. Мысалы: `CNTID_1002`
- {DSname}: Customer Insights жүйесіне енетін деректер көзі нысан атауы бар жол. Мысал:`Website_contacts`.
- {SegmentName}: Customer Insights ішіндегі сегменттің шығыс нысан атауы бар жол. Мысал:`Male_under_40`.

## <a name="customer"></a>Тұтынушы

үшін үлгі сұраулар *Тұтынушы* нысан.

|Сұрау түрі |Мысал  | Ескертпе  |
|---------|---------|---------|
|Бірыңғай тұтынушы идентификаторы     | `{serviceRoot}/Customer?$filter=CustomerId eq '{CID}'`          |  |
|баламалы кілт    | `{serviceRoot}/Customer?$filter={DSname_EntityName_PrimaryKeyColumnName} eq '{AlternateKey}'`         |  Баламалы кілттер бірыңғай тұтынушы нысанында сақталады       |
|Select   | `{serviceRoot}/Customer?$select=CustomerId,FullName&$filter=customerid eq '1'`        |         |
|Ішінде    | `{serviceRoot}/Customer?$filter=CustomerId in ('{CID1}',’{CID2}’)`        |         |
|баламалы кілт + In   | `{serviceRoot}/Customer?$filter={DSname_EntityName_PrimaryKeyColumnName} in ('{AlternateKey}','{AlternateKey}')`         |         |
|Іздеу  | `{serviceRoot}/Customer?$top=10&$skip=0&$search="string"`        |   Іздеу жолына арналған ең жақсы 10 нәтижені қайтарады      |
|Сегмент мүшелігі  | `{serviceRoot}/Customer?select=*&$filter=IsMemberOfSegment('{SegmentName}')&$top=10`     | Сегменттеу нысанынан жолдардың алдын ала орнатылған санын қайтарады.      |
|Тұтынушыға арналған сегмент мүшелігі | `{serviceRoot}/Customer?$filter=CustomerId eq '{CID}'&IsMemberOfSegment('{SegmentName}')`     | Егер олар берілген сегменттің мүшесі болса, тұтынушы профилін қайтарады     |

## <a name="unified-activity"></a>Бірыңғай әрекет

үшін үлгі сұраулар *UnifiedActivity* нысан.

|Сұрау түрі |Мысал  | Ескертпе  |
|---------|---------|---------|
|CID қызметі     | `{serviceRoot}/UnifiedActivity?$filter=CustomerId eq '{CID}'`          | Нақты тұтынушы профилінің әрекеттерін тізімдейді |
|Әрекеттің уақыт шеңбері    | `{serviceRoot}/UnifiedActivity?$filter=CustomerId eq '{CID}' and ActivityTime gt 2017-01-01T00:00:00.000Z and ActivityTime lt 2020-01-01T00:00:00.000Z`     |  Уақыт шеңберіндегі тұтынушы профилінің әрекеттері       |
|Әрекет түрі    |   `{serviceRoot}/UnifiedActivity?$filter=CustomerId eq '{CID}' and ActivityType eq '{ActivityName}'`        |         |
|Көрсетілетін атау бойынша әрекет     | `{serviceRoot}/UnifiedActivity$filter=CustomerId eq ‘{CID}’ and ActivityTypeDisplay eq ‘{ActivityDisplayName}’`        | |
|Әрекетті сұрыптау    | `{serviceRoot}/UnifiedActivity?$filter=CustomerId eq ‘{CID}’ & $orderby=ActivityTime asc`     |  Әрекеттерді өсу немесе кему бойынша сұрыптау       |
|Белсенділік сегмент мүшелігінен кеңейтілді  |   `{serviceRoot}/Customer?$expand=UnifiedActivity,Customer_Measure&$filter=CustomerId eq '{CID}'`     |         |

## <a name="other-examples"></a>Басқа мысалдар

Басқа нысандар үшін үлгі сұраулар.

|Сұрау түрі |Мысал  | Ескертпе  |
|---------|---------|---------|
|CID шаралары    | `{serviceRoot}/Customer_Measure?$filter=CustomerId eq '{CID}'`          |  |
|Байытылған CID брендтері    | `{serviceRoot}/BrandShareOfVoiceFromMicrosoft?$filter=CustomerId eq '{CID}'`  |       |
|CID-тің байытылған мүдделері    |   `{serviceRoot}/InterestShareOfVoiceFromMicrosoft?$filter=CustomerId eq '{CID}'`       |         |
|In-Clause + Кеңейту     | `{serviceRoot}/Customer?$expand=UnifiedActivity,Customer_Measure&$filter=CustomerId in ('{CID}', '{CID}')`         | |

## <a name="not-supported-odata-queries"></a>OData сұрауларына қолдау көрсетілмейді

Келесі сұрауларға Customer Insights қолдау көрсетпейді:

- `$filter` қабылданған бастапқы нысандарда. Сіз тек Customer Insights жасайтын жүйе нысандарында $сүзгі сұрауларын іске қоса аласыз.
- `$expand` а`$search` сұрау. Мысалы: `Customer?$expand=UnifiedActivity$top=10&$skip=0&$search="corey"`
- `$expand` бастап`$select` атрибуттардың ішкі жиыны ғана таңдалған болса. Мысалы: `Customer?$select=CustomerId,FullName&$expand=UnifiedActivity&$filter=CustomerId eq '{CID}'`
- `$expand` белгілі бір тұтынушы үшін байытылған бренд немесе қызығушылық ұқсастықтары. Мысалы: `Customer?$expand=BrandShareOfVoiceFromMicrosoft&$filter=CustomerId eq '518291faaa12f6d853c417835d40eb10'`
- баламалы кілт арқылы болжам үлгісінің шығу нысандарын сұрау. Мысалы: `OOBModelOutputEntity?$filter=HotelCustomerID eq '{AK}'`
