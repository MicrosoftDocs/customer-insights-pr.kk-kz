---
title: Power Automate қосқышы | Microsoft Docs
description: Dynamics 365 Customer Insights жүйесінен Microsoft Power Automate ішінде ағындар жасаңыз.
ms.date: 01/20/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
ms.reviewer: philk
manager: shellyha
ms.openlocfilehash: fb1df4e9ab1f78300b8ec1f8dfdfbfbac0e71447
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: kk-KZ
ms.lasthandoff: 02/15/2021
ms.locfileid: "5268831"
---
# <a name="power-automate-connector-preview"></a><span data-ttu-id="d137f-103">Power Automate коннекторы (алдын ала қарау)</span><span class="sxs-lookup"><span data-stu-id="d137f-103">Power Automate connector (preview)</span></span>

<span data-ttu-id="d137f-104">Деректер өзгерген жағдайда, автоматты түрде орын алатын белгілі бір оқиғаларды іске қосыңыз және күрделірек ағындарды [Power Automate](https://flow.microsoft.com/) бағдарламасында тікелей басқарыңыз.</span><span class="sxs-lookup"><span data-stu-id="d137f-104">Trigger specific events to occur automatically when your data changes and manage more complex flows directly in [Power Automate](https://flow.microsoft.com/).</span></span>

## <a name="power-automate-triggers"></a><span data-ttu-id="d137f-105">Power Automate триггерлері</span><span class="sxs-lookup"><span data-stu-id="d137f-105">Power Automate triggers</span></span>

<span data-ttu-id="d137f-106">Бұлтты ағындарды құру және хабарландырулар немесе жетілдірілген әрекеттер секілді қайталанатын тапсырмаларды автоматтандыру үшін триггерлерді пайдаланыңыз.</span><span class="sxs-lookup"><span data-stu-id="d137f-106">Use triggers to create cloud flows and automate repetitive tasks, such as notifications or more advanced actions.</span></span> 

- <span data-ttu-id="d137f-107">Дереккөзді жаңарту сәтсіз болған кезде іске қосыңыз.</span><span class="sxs-lookup"><span data-stu-id="d137f-107">Trigger when a data source refresh fails.</span></span> 
- <span data-ttu-id="d137f-108">Дереккөзді жаңарту сәтті болған кезде іске қосыңыз.</span><span class="sxs-lookup"><span data-stu-id="d137f-108">Trigger when a data source refresh succeeds.</span></span>
- <span data-ttu-id="d137f-109">Сегментте шектен асқан кезде іске қосыңыз.</span><span class="sxs-lookup"><span data-stu-id="d137f-109">Trigger when a threshold is crossed on a segment.</span></span> <span data-ttu-id="d137f-110">Триггер шектен асырмауға шектелген.</span><span class="sxs-lookup"><span data-stu-id="d137f-110">The trigger is limited to crossing above the threshold.</span></span>
- <span data-ttu-id="d137f-111">Іскери шарада шектен асқан кезде іске қосыңыз.</span><span class="sxs-lookup"><span data-stu-id="d137f-111">Trigger when a threshold is crossed on a business measure.</span></span> <span data-ttu-id="d137f-112">Триггер шектен асырмау күйіне шектелген.</span><span class="sxs-lookup"><span data-stu-id="d137f-112">The trigger is limited crossing above the threshold.</span></span>
- <span data-ttu-id="d137f-113">Толық жаңарту (деректер көздері, сегменттер, шаралар,...) аяқталған кезде іске қосыңыз.</span><span class="sxs-lookup"><span data-stu-id="d137f-113">Trigger when a full refresh of (data sources, segments, measures,...) is completed.</span></span>
- <span data-ttu-id="d137f-114">Бірегейлендіру процесін жаңарту (карта, сәйкестік, біріктіру) аяқталған кезде іске қосу.</span><span class="sxs-lookup"><span data-stu-id="d137f-114">Trigger when a refresh of the unification process (map, match, merge) is completed.</span></span>

<span data-ttu-id="d137f-115">[Power Automate жүйесінде триггерлеріңізді теңшеңіз](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/).</span><span class="sxs-lookup"><span data-stu-id="d137f-115">[Configure your triggers in Power Automate](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/).</span></span>

## <a name="power-automate-actions"></a><span data-ttu-id="d137f-116">Power Automate әрекеттері</span><span class="sxs-lookup"><span data-stu-id="d137f-116">Power Automate actions</span></span>
<span data-ttu-id="d137f-117">Power Automate коннекторы қолжетімді триггерлерден бөлек басқа әрекеттерді қамтамасыз етеді.</span><span class="sxs-lookup"><span data-stu-id="d137f-117">The Power Automate connector provides other actions than the available triggers.</span></span> <span data-ttu-id="d137f-118">Толық ақпарат алу үшін [Dynamics 365 Customer Insights Connector](https://docs.microsoft.com/connectors/customerinsights/) қараңыз.</span><span class="sxs-lookup"><span data-stu-id="d137f-118">For more information, see the [Dynamics 365 Customer Insights Connector](https://docs.microsoft.com/connectors/customerinsights/).</span></span>

## <a name="create-a-power-automate-flow"></a><span data-ttu-id="d137f-119">Power Automate ағынын жасау</span><span class="sxs-lookup"><span data-stu-id="d137f-119">Create a Power Automate flow</span></span>

1. <span data-ttu-id="d137f-120">Аудитория мәліметтерінде **Әкімші** > **Экспорттау мақсаттары** тармағына өтіңіз.</span><span class="sxs-lookup"><span data-stu-id="d137f-120">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="d137f-121">**Power Automate** тақтасында **Реттеу** түймешігін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="d137f-121">On the **Power Automate** tile, select **Set up**.</span></span>

1. <span data-ttu-id="d137f-122">Power Automate жүйесінде Customer Insights қосқышы (алдын ала қарау) ашылады.</span><span class="sxs-lookup"><span data-stu-id="d137f-122">The Customer Insights Connector (preview) in Power Automate opens.</span></span> <span data-ttu-id="d137f-123">Power Automate жүйесіне **кіріңіз**.</span><span class="sxs-lookup"><span data-stu-id="d137f-123">**Sign in** to Power Automate.</span></span>

1. <span data-ttu-id="d137f-124">Қолжетімді триггерлердің бірін таңдап, жаңа ағынға қосымша қадамдар қосыңыз.</span><span class="sxs-lookup"><span data-stu-id="d137f-124">Choose one of the available triggers and add more steps to your new flow.</span></span> <span data-ttu-id="d137f-125">Қосымша ақпарат алу үшін [Power Automate бағдарламасында бұлттық ағынды жасау](https://docs.microsoft.com/power-automate/get-started-logic-flow) бөлімін қараңыз.</span><span class="sxs-lookup"><span data-stu-id="d137f-125">For more information, see [Create a cloud flow in Power Automate](https://docs.microsoft.com/power-automate/get-started-logic-flow).</span></span>

<span data-ttu-id="d137f-126">Ағындарды пайдалану мысалдары:</span><span class="sxs-lookup"><span data-stu-id="d137f-126">Examples how to use flows:</span></span> 
- <span data-ttu-id="d137f-127">Деректер көзін жаңарту орындалмаса, Microsoft Teams арнасына хабар жіберіңіз.</span><span class="sxs-lookup"><span data-stu-id="d137f-127">Post a message to a Microsoft Teams channel if a data source refresh fails.</span></span> 
- <span data-ttu-id="d137f-128">Сегменттегі шек қиылыспағанда, деректер иеленушілеріне электрондық хабар жіберіңіз.</span><span class="sxs-lookup"><span data-stu-id="d137f-128">Send an email to the data owners when a threshold on a segment is crossed.</span></span>



[!INCLUDE[footer-include](../includes/footer-banner.md)]