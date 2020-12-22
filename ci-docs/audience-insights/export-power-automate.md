---
title: Power Automate қосқышы | Microsoft Docs
description: Dynamics 365 Customer Insights жүйесінен Microsoft Power Automate ішінде ағындар жасаңыз.
ms.date: 08/03/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: philk
manager: shellyha
ms.openlocfilehash: ffe92414365b0b777691a4a2d585100e4fbea591
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: kk-KZ
ms.lasthandoff: 11/03/2020
ms.locfileid: "4406206"
---
# <a name="power-automate-connector-preview"></a><span data-ttu-id="2efb6-103">Power Automate коннекторы (алдын ала қарау)</span><span class="sxs-lookup"><span data-stu-id="2efb6-103">Power Automate connector (preview)</span></span>

<span data-ttu-id="2efb6-104">Деректер өзгерген жағдайда, автоматты түрде орын алатын белгілі бір оқиғаларды іске қосыңыз және күрделірек ағындарды [Power Automate](https://flow.microsoft.com/) бағдарламасында тікелей басқарыңыз.</span><span class="sxs-lookup"><span data-stu-id="2efb6-104">Trigger specific events to occur automatically when your data changes and manage more complex flows directly in [Power Automate](https://flow.microsoft.com/).</span></span>

## <a name="power-automate-triggers"></a><span data-ttu-id="2efb6-105">Power Automate триггерлері</span><span class="sxs-lookup"><span data-stu-id="2efb6-105">Power Automate triggers</span></span>

<span data-ttu-id="2efb6-106">Хабарландырулар немесе қосымша кеңейтілген әрекеттер сияқты қайталанатын тапсырмаларды автоматтандыру үшін ағындарды жасауға мүмкіндік беретін әртүрлі триггерлерді пайдалана аласыз.</span><span class="sxs-lookup"><span data-stu-id="2efb6-106">You can use a variety of triggers that allow you to create flows to automate repetitive tasks, such as notifications or more advanced actions.</span></span> 

- <span data-ttu-id="2efb6-107">Дереккөзді жаңарту сәтсіз болған кезде іске қосыңыз.</span><span class="sxs-lookup"><span data-stu-id="2efb6-107">Trigger when a data source refresh fails.</span></span> 
- <span data-ttu-id="2efb6-108">Дереккөзді жаңарту сәтті болған кезде іске қосыңыз.</span><span class="sxs-lookup"><span data-stu-id="2efb6-108">Trigger when a data source refresh succeeds.</span></span>
- <span data-ttu-id="2efb6-109">Сегментте шектен асқан кезде іске қосыңыз.</span><span class="sxs-lookup"><span data-stu-id="2efb6-109">Trigger when a threshold is crossed on a segment.</span></span> <span data-ttu-id="2efb6-110">Триггер шектен асырмауға шектелген.</span><span class="sxs-lookup"><span data-stu-id="2efb6-110">The trigger is limited to crossing above the threshold.</span></span>
- <span data-ttu-id="2efb6-111">Іскери шарада шектен асқан кезде іске қосыңыз.</span><span class="sxs-lookup"><span data-stu-id="2efb6-111">Trigger when a threshold is crossed on a business measure.</span></span> <span data-ttu-id="2efb6-112">Триггер шектен асырмау күйіне шектелген.</span><span class="sxs-lookup"><span data-stu-id="2efb6-112">The trigger is limited crossing above the threshold.</span></span>
- <span data-ttu-id="2efb6-113">Толық жаңарту (деректер көздері, сегменттер, шаралар,...) аяқталған кезде іске қосыңыз.</span><span class="sxs-lookup"><span data-stu-id="2efb6-113">Trigger when a full refresh of (data sources, segments, measures,...) is completed.</span></span>
- <span data-ttu-id="2efb6-114">Бірегейлендіру процесін жаңарту (карта, сәйкестік, біріктіру) аяқталған кезде іске қосу.</span><span class="sxs-lookup"><span data-stu-id="2efb6-114">Trigger when a refresh of the unification process (map, match, merge) is completed.</span></span>

<span data-ttu-id="2efb6-115">[Power Automate жүйесінде триггерлеріңізді теңшеңіз](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/).</span><span class="sxs-lookup"><span data-stu-id="2efb6-115">[Configure your triggers in Power Automate](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/).</span></span>

## <a name="power-automate-actions"></a><span data-ttu-id="2efb6-116">Power Automate әрекеттері</span><span class="sxs-lookup"><span data-stu-id="2efb6-116">Power Automate actions</span></span>
<span data-ttu-id="2efb6-117">Power Automate коннекторы қолжетімді триггерлерден бөлек басқа әрекеттерді қамтамасыз етеді.</span><span class="sxs-lookup"><span data-stu-id="2efb6-117">The Power Automate connector provides other actions than the available triggers.</span></span> <span data-ttu-id="2efb6-118">Толық ақпарат алу үшін [Dynamics 365 Customer Insights Connector](https://docs.microsoft.com/connectors/customerinsights/) қараңыз.</span><span class="sxs-lookup"><span data-stu-id="2efb6-118">For more information, see the [Dynamics 365 Customer Insights Connector](https://docs.microsoft.com/connectors/customerinsights/).</span></span>

## <a name="create-a-power-automate-flow-in-audience-insights"></a><span data-ttu-id="2efb6-119">Аудитория түсініктерінде Power Automate ағынын жасау</span><span class="sxs-lookup"><span data-stu-id="2efb6-119">Create a Power Automate flow in audience insights</span></span>

1. <span data-ttu-id="2efb6-120">Аудитория түсініктерінде **Әкімші** > **Жүйе** тармағына өтіңіз.</span><span class="sxs-lookup"><span data-stu-id="2efb6-120">In audience insights, go to **Admin** > **System**.</span></span>

1. <span data-ttu-id="2efb6-121">**Жүйе** бетінен **Күй** қойыншасын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="2efb6-121">On the **System** page, select the **Status** tab.</span></span>

1. <span data-ttu-id="2efb6-122">**Деректер көздері** бөлімінде **Ағындар** параметріне және ашылмалы тізімнен **Ағын жасау** опциясын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="2efb6-122">In the **Data Sources** section, select **Flows** and select **Create a flow** from the dropdown list.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="2efb6-123">![Power Automate коннекторы Ағынды жасау әрекетін көрсетеді](media/power-automate-connector-create-flow.png "Power Automate коннекторы Ағынды жасау әрекетін көрсетеді")</span><span class="sxs-lookup"><span data-stu-id="2efb6-123">![Power Automate connector showing Create a Flow action](media/power-automate-connector-create-flow.png "Power Automate connector showing Create a Flow action")</span></span>

1. <span data-ttu-id="2efb6-124">Power Automate бағдарламасында қажетті ағынды жасау үшін қолжетімді триггерлердің біреуін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="2efb6-124">In Power Automate, select one of the available triggers to create your preferred flow.</span></span> <span data-ttu-id="2efb6-125">Алғашқы ағынды жасап жатсаңыз, алдымен Power Automate коннекторы көмегімен түпнұсқалығын растауыңыз керек болады.</span><span class="sxs-lookup"><span data-stu-id="2efb6-125">If you're creating your first flow, you'll need to authenticate with the Power Automate connector first.</span></span>
