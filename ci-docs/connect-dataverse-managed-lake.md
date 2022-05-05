---
title: Microsoft Dataverse ішінде кестелерге қосылу
description: Деректерді Microsoft Dataverse басқарылатын деректер көлінен импорттау.
ms.date: 03/18/2022
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
manager: shellyha
ms.reviewer: mhart
searchScope:
- ci-dataverse
- customerInsights
ms.openlocfilehash: e8a294a4bad1581539b5905160cddcd625699d90
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: MT
ms.contentlocale: kk-KZ
ms.lasthandoff: 04/27/2022
ms.locfileid: "8643113"
---
# <a name="connect-to-data-in-a-microsoft-dataverse-managed-data-lake"></a>Microsoft Dataverse басқарылатын деректер ағынында деректерге қосылу

Бұл мақалада қалай болатыны туралы ақпарат берілген Dataverse пайдаланушылар а ішіндегі аналитикалық нысандарға жылдам қосыла алады Microsoft Dataverse басқарылатын көл. 

> [!NOTE]
> Сіз сайтта әкімші болуыңыз керек Dataverse басқарылатын көлде қолжетімді нысандар тізімін жалғастыру және көру үшін ұйым.

## <a name="important-considerations"></a>Маңызды жайттар

1. Azure Data Lake Storage сияқты онлайн қызметтерде сақталған деректер Dynamics 365 Customer Insights бағдарламасында деректер өңделетін немесе сақталатын жерден басқа жерде сақталуы мүмкін.Онлайн қызметтерде сақталған деректерді импорттау немесе оларға қосылу арқылы сіз деректерді тасымалдауға және сақтауға болатынына келісесіз Dynamics 365 Customer Insights . [Толығырақ Microsoft сенім орталығында біліңіз](https://www.microsoft.com/trust-center).
2. Тек Dataverse бар субъектілер [бақылауды өзгерту](/power-platform/admin/enable-change-tracking-control-data-synchronization) қосылғандар көрінеді. Бұл нысандарды экспорттауға болады Dataverse -басқарылатын деректер көлі және Customer Insights жүйесінде пайдаланылады. Қораптан тыс Dataverse кестелерде әдепкі бойынша өзгерістерді қадағалау қосылған. Теңшелетін кестелер үшін өзгерістерді бақылауды қосу керек. Тексеру үшін а Dataverse кесте өзгерістерді бақылау үшін қосылған, өтіңіз [Power Apps](https://make.powerapps.com) > **Деректер** > **Кестелер**. Өзіңізді қызықтыратын кестені тауып, оны таңдаңыз. Бару **Параметрлер** > **Қосымша опциялар** және қарап шығыңыз **Өзгерістерді бақылаңыз** орнату.

## <a name="connect-to-a-dataverse-managed-lake"></a>Dataverse басқарылатын ағынына қосылу

1. Customer Insights жүйесінде **Деректер** > **Дерек көздері** тармағына өтіңіз.

2. **Деректер көзін қосу** түймешігін таңдаңыз.

3. таңдаңыз **Microsoft Dataverse** және таңдаңыз **Келесі**.

4. Деректер көзінің **Атау** өрісін енгізіңіз және **Келесі** түймешігін таңдаңыз. 

5. Dataverse ұйымы үшін **Сервер мекенжайы** параметрін енгізіп, **Жүйеге кіру** опциясын таңдаңыз.

   :::image type="content" source="media/ingest-dataverse-server-address.png" alt-text="Пайдаланушы Dataverse ортасының URL мекенжайына кіретін деректерді қабылдау қадамындағы экран.":::

6. Қол жетімді тізімнен Customer Insights жүйесіне нысандар ретінде енгізгіңіз келетін кестелерді таңдаңыз.    

   > [!NOTE]
   > Егер кейбір кестелер бұрыннан таңдалған болса, оларды басқа Dynamics 365 бағдарламалары арқылы пайдалануға болады (мысалы, Dynamics 365 Sales Insights немесе Customer Service Insights). Таңдауды өзгерте алмайсыз. Бұл кестелер деректер көзі жасалғаннан кейін нысандар ретінде қолжетімді болады.

   :::image type="content" source="media/select-dataverse-entities.png" alt-text="Dataverse ортасындағы нысандар тізімін көрсететін диалогтік терезе.":::

7. Таңдалған кестелерді Dataverse жүйесінен синхрондауды бастау үшін таңдауды сақтаңыз. **Дереккөздер** бетінен жаңадан қосылған байланысты таба аласыз. Ол жаңарту үшін кезекке қойылады және барлық таңдалған кестелер синхрондалғанша нысандар санын 0 ретінде көрсетеді.

Ортаның тек бір деректер көзі бір уақытта бір Dataverse басқарылатын көлін пайдалана алады.

## <a name="edit-a-dataverse-managed-lake-data-source"></a>Dataverse басқарылатын ағынның дереккөзін өңдеу

Дереккөзді жасағаннан кейін ғана нысан таңдауын өңдейсіз. Мысалы, Dataverse ішіне қосымша нысандар қосылса және оларды импорттау қажет болса.    
Басқа Dataverse деректер көліне қосылу үшін [жаңа деректер көзін жасаңыз](#connect-to-a-dataverse-managed-lake).

1. **Деректер** > **Дерек көздері** тармағы бойынша өтіңіз.

2. Жаңарту керек деректер көзінің жанындағы көп нүктені таңдаңыз.

3. Тізімнен **Өңдеу** параметрін таңдаңыз.

4. Қолжетімді нысандар тізімінен қосымша нысандарды таңдап, **Сақтау** параметрін таңдаңыз.

[!INCLUDE [footer-include](includes/footer-banner.md)]