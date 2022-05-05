---
title: Нысандар мен деректер жиындары
description: Нысандар бетіндегі деректерді қараңыз.
ms.date: 12/06/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
searchScope:
- ci-entities
- customerInsight
ms.openlocfilehash: c1094bc2f6d137087b317ed20d0615289d6f1187
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: MT
ms.contentlocale: kk-KZ
ms.lasthandoff: 04/27/2022
ms.locfileid: "8643420"
---
# <a name="entities-in-customer-insights"></a>Customer Insights бағдарламасындағы нысандар

[Деректер көздерін теңшегеннен](data-sources.md) кейін қабылданған деректер сапасын бағалау үшін **Нысандар** бетіне өтіңіз. Нысандар деректер жиындары болып саналады. Бірнеше Dynamics 365 Customer Insights мүмкіндіктері осы нысандардың айналасында құрылады. Оларды мұқият қарап шығу осы мүмкіндіктердің шығысын тексеруге көмектесуі мүмкін.

The **Субъектілер** бет нысандарды тізімдейді және мына бағандарды қамтиды:

- **Аты** : Деректер нысанының атауы. Нысан атынан кейін ескерту таңбасын көрсеңіз, ол нысан деректерінің сәтті жүктелмегенін білдіреді.
- **Дереккөз** : Нысанды қабылдаған деректер көзі түрі.
- **Жаңартылған** : Нысанның соңғы жаңартылған уақыты.
- **Күй** : Нысанның соңғы жаңартуы туралы мәліметтер.

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

## <a name="explore-a-specific-entitys-data"></a>Белгілі бір нысан деректерін зерттеу

1. Бару **Деректер** > **Субъектілер**.
1. бастап **Субъектілер** бетінде, мәліметтер бетін ашу үшін нысанды таңдаңыз.  
1. Осы нысан үшін енгізілген әртүрлі өрістер мен жазбаларды зерттеңіз.

- **Төлсипаттар** қойыншасы әдепкі бойынша таңдалады және өріс атаулары, деректер түрлері және түрлер сияқты таңдалған нысан үшін мәліметтерді қарап шығу кестесін көрсетеді. **Түрі** бағанында жүйемен автоматты анықталатын немесе пайдаланушылар [қолмен салыстыратын](map-entities.md) Common Data Model байланысты түрлері көрсетіледі. Бұл түрлер — төлсипаттардың деректер түрлерінен өзгеше болуы мүмкін семантикалық түрлер. Мысалы, төмендегі *Электрондық пошта хабары* өрісінің деректер түрі — *Мәтін*, бірақ оның (семантикалық) Common Data Model түрі *Электрондық пошта хабары* немесе *Электрондық пошта мекенжайы* болуы мүмкін.

> [!div class="mx-imgBorder"]
> ![Өрістер кестесі.](media/data-manager-entities-fields.PNG "Өрістер кестесі")

> [!NOTE]
> Бұл бетте ұйым деректерінің үлгісі ғана көрсетіледі. Толық деректер жинағын көру үшін бөліміне өтіңіз **Деректер көздері** бет, нысанды таңдаңыз, таңдаңыз **Өңдеу**, содан кейін осы нысанның деректерін арқылы қараңыз Power Query түсіндірілгендей редактор [Деректер көздері](data-sources.md).

Нысанда қабылданған деректер туралы қосымша ақпарат алу үшін, **Қорытынды** бағанында бос мәндер, жоқ мәндер, бірегей мәндер, сандар сияқты кейбір маңызды сипаттамалар және деректеріңізге қолданылатын таратулар қамтамасыз етіледі. Деректер қорытындысын көру үшін диаграмма белгішесін таңдаңыз.

> [!div class="mx-imgBorder"]
> ![Қорытынды таңбасы.](media/data-manager-entities-summary.png "Деректер қорытындысы кестесі")

- **Деректер** қойыншасында нысанның жеке жазбалары туралы мәліметтер келтірілген кесте көрсетілген. Тізімдегі мәліметтер нысанның деректер түріне байланысты.

> [!div class="mx-imgBorder"]
> ![Нысан таңдаңыз.](media/data-manager-entities-data.png "Нысан таңдау")

- The **Есептер** қойындысы (кейбір нысандар үшін қолжетімді) есеп жасау арқылы деректеріңізді визуализациялауға мүмкіндік береді және мына бағандарды қамтиды:

  - **Есеп атауы** : Есептің атауы.
  - **Жасалған** : Нысанды жасаған адамның аты.
  - **Құрылды** : Нысанның жасалған күні мен уақыты.
  - **Өңдеген** : Нысанды өзгерткен тұлғаның аты.
  - **Өңделген** : нысанды өзгерту күні мен уақыты. 

## <a name="entity-specific-information"></a>Нысанға қатысты ақпарат

Келесі бөлімде жүйе құрған кейбір нысандар туралы ақпарат берілген.

### <a name="corrupted-data-sources"></a>Бүлінген деректер көзі

Қабылданған деректер көзі өрістерінде бүлінген деректер болуы мүмкін. Бүлінген өрістері бар жазбалар жүйеде құрылған нысандарда көрсетіледі. Бүлінген жазбалар туралы білу бастапқы жүйеде қандай деректерді қарап шығуға және жаңартуға болатынын анықтауға көмектеседі. Деректер көзін келесі рет жаңартқаннан кейін, түзетілген жазбалар Customer Insights бағдарламасына қабылданады және төменгі процестерге өткізіледі. 

Мысалы, 'туған күн' бағанында 'күн' деп белгіленген деректер түрі бар. Тұтынушы жазбасында олардың туған күні '01.01.1977' деп жазылады. Жүйе бұл жазбаны бүлінген деп белгілейді. Енді біреу туған күнді бастапқы жүйеде '1977' деп өзгерте алады. Деректер көздерін автоматты түрде жаңартқаннан кейін, өрістің енді жарамды пішімі болады және жазба бүлінген нысаннан жойылады. 

**Деректер** > **Нысандар** тармағына өтіп, **Жүйе** бөлімінен бүлінген нысандарды іздеңіз. Бүлінген нысандарды атау схемасы: 'DataSourceName_EntityName_corrupt'. Жеке жазба деңгейінде барлық бүлінген өрістерді және себебін анықтау үшін бүлінген нысанды таңдаңыз.
> [!div class="mx-imgBorder"]
> ![Сыбайлас жемқорлық себебі.](media/corruption-reason.png "Сыбайлас жемқорлық себебі")

Customer Insights бағдарламасы әлі де бүлінген жазбаларды өңдейді. Алайда, олар бірыңғай деректермен жұмыс кезінде қиындықтар туғызуы мүмкін.

Зақымдалған жазбаларды ашу үшін енгізілген деректер бойынша келесі тексерулер жүргізіледі: 

- Өрістің мәні оның бағанының деректер түріне сәйкес келмейді.
- Өрістерде бағандар күтілетін схемаға сәйкес келмейтін таңбалар бар. Мысалы: қате пішімделген тырнақшалар, алынбаған тырнақшалар немесе жаңа жол таңбалары.
- Datetime/date/datetimeoffset бағандары болса, стандартты ISO пішіміне сәйкес келмесе, олардың пішімі үлгіде көрсетілуі керек.


[!INCLUDE [footer-include](includes/footer-banner.md)]