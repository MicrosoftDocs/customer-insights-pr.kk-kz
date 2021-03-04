---
title: Common Data Service басқарылатын көлінде нысандарға қосылыңыз
description: Деректерді Common Data Service басқарылатын деректер көлінен импорттау.
ms.date: 09/29/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.reviewer: adkuppa
ms.openlocfilehash: 18b6cd3fdaf5b738877a73b520b91dbc6ded40de
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: kk-KZ
ms.lasthandoff: 02/15/2021
ms.locfileid: "5267821"
---
# <a name="connect-to-data-in-a-common-data-service-managed-data-lake"></a>Common Data Service басқарылатын деректер ағынында деректерге қосылу

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

Бұл мақалада бұрыннан бар Dynamics 365 тұтынушылары өздерінің аналитикалық нысандарына Common Data Service басқарылатын көлінде қалай жылдам қосыла алатыны туралы ақпарат берілген. Жалғастыру және басқарылатын көлде бар нысандардың тізімін қарау үшін Common Data Service ұйымының әкімшісі болуыңыз керек.

## <a name="important-considerations"></a>Маңызды жайттар

Azure Data Lake Storage сияқты онлайн қызметтерде сақталған деректер Dynamics 365 Customer Insights бағдарламасында деректер өңделетін немесе сақталатын жерден басқа жерде сақталуы мүмкін. Онлайн қызметтерде сақталған деректерді импорттау немесе қосу арқылы сіз деректердің Dynamics 365 Customer Insights бағдарламасына тасымалдануына және сақталуына келісім бересіз. [Қосымша ақпаратты Microsoft сенім орталығынан қараңыз.](https://www.microsoft.com/trust-center)

## <a name="connect-to-a-common-data-service-managed-lake"></a>Common Data Service басқарылатын ағынына қосылу

1. Аудитория мәліметтерінде **Деректер** > **Деректер көздері** тармағына өтіңіз.

2. **Деректер көзін қосу** түймешігін таңдаңыз.

3. **Common Data Service қызметіне қосылу** параметрін таңдап, **Келесі** параметрін таңдаңыз.

4. Деректер көзінің **Атау** өрісін енгізіңіз және **Келесі** түймешігін таңдаңыз. Нұсқаулықтар атауын енгізіңіз: 
   - Әріптен бастаңыз.
   - Тек әріптер мен сандарды пайдаланыңыз. Арнайы таңбалар мен бос орындарға рұқсат етілмейді.
   - 3-64 аралығындағы таңбаларды пайдаланыңыз.

5. Common Data Service ұйымының **Сервер мекенжайын** қамтамасыз етіп, **Кіру** параметрін таңдаңыз.

   > [!div class="mx-imgBorder"]
   > ![Common Data Service сервер мекенжайын енгізу диалог терезесі](media/enter-CDS-org-details.png)

6. Қолжетімді тізімінен қабылдау қажет нысандарды таңдаңыз.    

   > [!NOTE]
   > Кейбір нысандар бұрын таңдалған болса, оларды басқа Dynamics 365 бағдарламалары пайдалануы мүмкін (мысалы, Dynamics 365 Sales Insights немесе Customer Service Insights). Таңдауды өзгерте алмайсыз. Бұл нысандар деректер көзі жасалғаннан кейін қолжетімді болады.

   > [!div class="mx-imgBorder"]
   > ![Common Data Service ұйымындағы нысандар тізімін көрсететін диалог терезесі](media/select-analytical-entities.png)

7. Common Data Service басқарылатын ағынымен таңдалған нысандарды синхрондауды бастау үшін таңдауыңызды сақтаңыз. **Дереккөздер** бетінен жаңадан қосылған байланысты таба аласыз. Ол кезегімен жаңартылады және барлық нысандарды синхрондағанға дейін нысандар санын 0 деп көрсетеді.

Ортаның тек бір деректер көзі бір уақытта бір Common Data Service басқарылатын көлін пайдалана алады.

## <a name="edit-a-common-data-service-managed-lake-data-source"></a>Common Data Service басқарылатын ағынның дереккөзін өңдеу

Дереккөзді жасағаннан кейін ғана нысан таңдауын өңдейсіз. Мысалы, Common Data Service ішіне қосымша нысандар қосылса және оларды импорттау қажет болса.    
Басқа Common Data Service жүйесіне қосылу үшін [жаңа дереккөз жасаңыз](#connect-to-a-common-data-service-managed-lake).

1. Аудитория мәліметтерінде **Деректер** > **Деректер көздері** тармағына өтіңіз.

2. Жаңарту керек деректер көзінің жанындағы көп нүктені таңдаңыз.

3. Тізімнен **Өңдеу** параметрін таңдаңыз.

4. Қолжетімді нысандар тізімінен қосымша нысандарды таңдап, **Сақтау** параметрін таңдаңыз.


[!INCLUDE[footer-include](../includes/footer-banner.md)]