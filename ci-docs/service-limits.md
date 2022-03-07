---
title: Dynamics 365 Customer Insights жүйесіндегі қызмет шектері
description: Шектеулер мен шектерді түсіну.
ms.date: 09/03/2021
ms.subservice: audience-insights
ms.topic: conceptual
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 9bf8f03b785fb3035e3fc979a3304d4e98fd8d28
ms.sourcegitcommit: 1946d7af0bd2ca216885bec3c5c95009996d9a28
ms.translationtype: MT
ms.contentlocale: kk-KZ
ms.lasthandoff: 02/25/2022
ms.locfileid: "8350414"
---
# <a name="service-limits-in-customer-insights-capabilities"></a>Customer Insights мүмкіндіктеріндегі қызмет шектеулері

Бұл мақалада қызметтің сенімділігі мен тұрақтылығын қамтамасыз етуге арналған Customer Insights қызметіне ендірілген шектеулер сипатталады. Өзгерістер туралы кез келген сұрауды мына мекенжай бойынша жасауға болады: [Идеялар форумы](https://go.microsoft.com/fwlink/?linkid=2074172). 

## <a name="audience-insights"></a>Аудитория туралы пайдалы мәліметтер

| Аумақ  | Шектеулер  | Ескертпелер |
|-------------|---------------------------------------------------------------------|---------------------------------------------------------------------|
| Сегменттер, өлшемдер және болжамдар | 300  | Жалпы саны [сегменттер](audience-insights/segments.md),[шаралар](audience-insights/measures.md), және [болжамдар](audience-insights/predictions.md) біріктірілген 300-ден аспауы керек.  |
| Қатынастар | Нысан жолдарындағы қатынастардың 20 тереңдік деңгейі. | Құрастырушы интерфейсін пайдаланып [сегменттер](audience-insights/segments.md) немесе [өлшеулер](audience-insights/measures.md) жасау кезінде нысан жолдарында бастапқы нысан мен мақсатты нысан арасында 20 қарым-қатынас секірісі болуы мүмкін.  |

<!--
## Engagement insights

### Workspace and event quotas

Engagement insights is a highly scalable application that can support millions of events per second. During public preview, events have a volume threshold. There's also a limit to the number of workspaces in an organization.

### Engagement insights limits

- Maximum event volume per workspace  = 100 events per second

- Maximum number of workspaces per organization = 100

When events exceed the threshold, it can lead to loss of data in reports based on those events. You can [contact support](https://go.microsoft.com/fwlink/?linkid=2145734) to request a volume increase before you exceed limits. We'll work with you to determine your need for a volume increase and support your request.
-->

[!INCLUDE[footer-include](includes/footer-banner.md)]
