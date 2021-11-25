---
title: Dynamics 365 Customer Insights ішіндегі қызмет шектеулері
description: Шектеулер мен шектерді түсіну.
ms.date: 09/03/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: eb25e050b8aa768e6e1d8d4c5adce6095cccc346
ms.sourcegitcommit: 31a9b531dacd3a6465b3030c704ff5c085b7e122
ms.translationtype: MT
ms.contentlocale: kk-KZ
ms.lasthandoff: 11/10/2021
ms.locfileid: "7791988"
---
# <a name="service-limits-in-customer-insights-capabilities"></a>Customer Insights мүмкіндіктеріндегі қызмет шектеулері

Бұл мақалада қызметтің сенімділігі мен тұрақтылығын қамтамасыз етуге арналған Customer Insights қызметіне ендірілген шектеулер сипатталады. Өзгерістер туралы кез келген сұрауды мына мекенжай бойынша жасауға болады: [Идеялар форумы](https://go.microsoft.com/fwlink/?linkid=2074172). 

## <a name="audience-insights"></a>Аудитория туралы пайдалы мәліметтер

### <a name="service-limits-in-dynamics-365-customer-insights-audience-insights-capability"></a>Dynamics 365 Customer Insights аудитория туралы түсініктер мүмкіндігіндегі қызмет шектеулері

| Аумақ  | Шектеулер  | Ескертпелер |
|-------------|---------------------------------------------------------------------|---------------------------------------------------------------------|
| Сегменттер, өлшемдер және болжамдар | 300  | Жалпы саны [сегменттер](audience-insights/segments.md),[шаралар](audience-insights/measures.md), және [болжамдар](audience-insights/predictions.md) біріктірілген 300-ден аспауы керек.  |
| Қатынастар | Нысан жолдарындағы қатынастардың 20 тереңдік деңгейі. | Құрастырушы интерфейсін пайдаланып [сегменттер](audience-insights/segments.md) немесе [өлшеулер](audience-insights/measures.md) жасау кезінде нысан жолдарында бастапқы нысан мен мақсатты нысан арасында 20 қарым-қатынас секірісі болуы мүмкін.  |


## <a name="engagement-insights"></a>Өзара әрекеттестік туралы мәліметтер

### <a name="workspace-and-event-quotas"></a>Жұмыс кеңістігі мен оқиғаларға квоталар

Өзара әрекеттестік туралы түсінік – бұл секундына миллион оқиғаны қолдай алатын өте ауқымды бағдарлама. Жалпыға қолжетімді алдын ала қарау нұсқасы барысында оқиғаларда көлемдік шек болады. Сондай-ақ ұйымдағы жұмыс кеңістіктерінің санына шектеу бар.

### <a name="engagement-insights-limits"></a>Өзара әрекеттестік туралы түсініктер шектеулері

- Бір жұмыс кеңістігіндегі оқиғалардың максималды көлемі = секундына 100 оқиға

- Бір ұйымға арналған жұмыс кеңістіктерінің максималды саны = 100

Оқиғалар шектен асып кетсе, бұл сол оқиғаларға негізделген есептердегі деректердің жоғалуына әкелуі мүмкін. Шектен аспас бұрын көлемді арттыруға сұрау жіберу үшін [қолдау көрсету қызметімен байланысуға](https://go.microsoft.com/fwlink/?linkid=2145734) болады. Біз сізбен көлем деңгейін жоғарылату қажеттілігін анықтау үшін бірге жұмыс жасап, сұранысыңызды қолдаймыз.


[!INCLUDE[footer-include](includes/footer-banner.md)]
