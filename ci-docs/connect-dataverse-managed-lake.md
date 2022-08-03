---
title: Microsoft Dataverse басқарылатын деректер ағынында деректерге қосылу
description: Деректерді Microsoft Dataverse басқарылатын деректер көлінен импорттау.
ms.date: 07/26/2022
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
manager: shellyha
ms.reviewer: v-wendysmith
searchScope:
- ci-dataverse
- customerInsights
ms.openlocfilehash: b21150a1c51bdad35250cae7fde7f38a014ec876
ms.sourcegitcommit: 5807b7d8c822925b727b099713a74ce2cb7897ba
ms.translationtype: MT
ms.contentlocale: kk-KZ
ms.lasthandoff: 07/28/2022
ms.locfileid: "9206960"
---
# <a name="connect-to-data-in-a-microsoft-dataverse-managed-data-lake"></a>Microsoft Dataverse басқарылатын деректер ағынында деректерге қосылу

Microsoft Dataverse пайдаланушылар аналитикалық нысандарға жылдам қосыла алады Microsoft Dataverse басқарылатын көл. Ортаның тек бір деректер көзі бір уақытта бір Dataverse басқарылатын көлін пайдалана алады.

> [!NOTE]
> Сіз сайтта әкімші болуыңыз керек Dataverse басқарылатын көлде қолжетімді нысандар тізімін жалғастыру және көру үшін ұйым.

## <a name="prerequisites"></a>Алғышарттар

- Azure Data Lake Storage сияқты онлайн қызметтерде сақталған деректер Dynamics 365 Customer Insights бағдарламасында деректер өңделетін немесе сақталатын жерден басқа жерде сақталуы мүмкін.Онлайн қызметтерде сақталған деректерді импорттау немесе оларға қосылу арқылы сіз деректерді тасымалдауға және сақтауға болатынына келісесіз Dynamics 365 Customer Insights . [Толығырақ Microsoft сенім орталығынан біліңіз](https://www.microsoft.com/trust-center).

- Тек Dataverse бар субъектілер [бақылауды өзгерту](/power-platform/admin/enable-change-tracking-control-data-synchronization) қосылғандар көрінеді. Бұл нысандарды экспорттауға болады Dataverse -басқарылатын деректер көлі және Customer Insights жүйесінде пайдаланылады. Қораптан тыс Dataverse кестелерде әдепкі бойынша өзгерістерді бақылау қосылған. Теңшелетін кестелер үшін өзгерістерді бақылауды қосу керек. Тексеру үшін а Dataverse кесте өзгерістерді бақылау үшін қосылған, өтіңіз [Power Apps](https://make.powerapps.com) > **Деректер** > **Кестелер**. Өзіңізді қызықтыратын кестені тауып, оны таңдаңыз. Бару **Параметрлер** > **Қосымша опциялар** және қарап шығыңыз **Өзгерістерді бақылаңыз** орнату.

## <a name="connect-to-a-dataverse-managed-lake"></a>Dataverse басқарылатын ағынына қосылу

1. **Деректер** > **Дерек көздері** тармағы бойынша өтіңіз.

1. **Деректер көзін қосу** түймешігін таңдаңыз.

1. **Microsoft Dataverse** таңдаңыз.

1. А енгізіңіз **Аты** деректер көзі және қосымша үшін **Сипаттама**.

1. Dataverse ұйымы үшін **Сервер мекенжайы** параметрін енгізіп, **Жүйеге кіру** опциясын таңдаңыз.

1. Қол жетімді тізімнен Customer Insights жүйесіне нысандар ретінде енгізгіңіз келетін кестелерді таңдаңыз.

   > [!NOTE]
   > Егер кейбір кестелер бұрыннан таңдалған болса, оларды басқа Dynamics 365 бағдарламалары арқылы пайдалануға болады (мысалы, Dynamics 365 Sales Insights немесе Customer Service Insights). Таңдауды өзгерте алмайсыз. Бұл кестелер деректер көзі жасалғаннан кейін нысандар ретінде қолжетімді болады.

    :::image type="content" source="media/select-dataverse-entities.png" alt-text="Dataverse ортасындағы нысандар тізімін көрсететін диалогтік терезе.":::

1. Таңдалған кестелерді Dataverse жүйесінен синхрондауды бастау үшін таңдауды сақтаңыз. **Дереккөздер** бетінен жаңадан қосылған байланысты таба аласыз. Ол жаңарту үшін кезекке қойылады және барлық таңдалған кестелер синхрондалғанша нысандар санын 0 ретінде көрсетеді.

   [!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

Деректерді жүктеу уақыт алуы мүмкін. Сәтті жаңартудан кейін енгізілген деректерді мына жерден қарап шығуға болады [**Субъектілер**](entities.md) бет.

## <a name="edit-a-dataverse-managed-lake-data-source"></a>Dataverse басқарылатын ағынның дереккөзін өңдеу

Дереккөзді жасағаннан кейін ғана нысан таңдауын өңдейсіз. Мысалы, Dataverse ішіне қосымша нысандар қосылса және оларды импорттау қажет болса.
Басқа Dataverse деректер көліне қосылу үшін [жаңа деректер көзін жасаңыз](#connect-to-a-dataverse-managed-lake).

1. **Деректер** > **Дерек көздері** тармағы бойынша өтіңіз.

1. Жаңартқыңыз келетін деректер көзі жанындағы таңдаңыз **Өңдеу**.

1. Қол жетімді нысандар тізімінен қосымша нысандарды таңдаңыз.

1. басыңыз **Сақтау** өзгертулерді қолданып, параметріне оралу үшін **Деректер көздері** бет.

   [!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
