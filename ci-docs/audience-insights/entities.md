---
title: Нысандар мен деректер жиындары
description: Нысандар бетіндегі деректерді қараңыз.
ms.date: 04/16/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
ms.openlocfilehash: f81128183b6e20e1078ad38c42c771d343909270
ms.sourcegitcommit: c1841ab91fbef9ead9db0f63fbc669cc3af80c12
ms.translationtype: HT
ms.contentlocale: kk-KZ
ms.lasthandoff: 05/17/2021
ms.locfileid: "6049401"
---
# <a name="entities-in-audience-insights"></a><span data-ttu-id="b593a-103">Аудитория мәліметтеріндегі нысандар</span><span class="sxs-lookup"><span data-stu-id="b593a-103">Entities in audience insights</span></span>

<span data-ttu-id="b593a-104">[Деректер көздерін теңшегеннен](data-sources.md) кейін қабылданған деректер сапасын бағалау үшін **Нысандар** бетіне өтіңіз.</span><span class="sxs-lookup"><span data-stu-id="b593a-104">After [configuring your data sources](data-sources.md), go to the **Entities** page to evaluate the quality of the ingested data.</span></span> <span data-ttu-id="b593a-105">Нысандар деректер жиындары болып саналады.</span><span class="sxs-lookup"><span data-stu-id="b593a-105">Entities are considered datasets.</span></span> <span data-ttu-id="b593a-106">Бірнеше Dynamics 365 Customer Insights мүмкіндіктері осы нысандардың айналасында құрылады.</span><span class="sxs-lookup"><span data-stu-id="b593a-106">Multiple capabilities of Dynamics 365 Customer Insights are built around these entities.</span></span> <span data-ttu-id="b593a-107">Оларды мұқият қарап шығу осы мүмкіндіктердің шығысын тексеруге көмектесуі мүмкін.</span><span class="sxs-lookup"><span data-stu-id="b593a-107">Reviewing them closely can help you validate the output of those capabilities.</span></span>

<span data-ttu-id="b593a-108">**Нысандар** бетінде нысандар тізімделген және бірнеше бағаннан тұрады:</span><span class="sxs-lookup"><span data-stu-id="b593a-108">The **Entities** page lists entities and includes several columns:</span></span>

- <span data-ttu-id="b593a-109">**Аты**: деректер нысанының аты.</span><span class="sxs-lookup"><span data-stu-id="b593a-109">**Name**: The name of your data entity.</span></span> <span data-ttu-id="b593a-110">Нысан атынан кейін ескерту таңбасын көрсеңіз, ол нысан деректерінің сәтті жүктелмегенін білдіреді.</span><span class="sxs-lookup"><span data-stu-id="b593a-110">If you see a warning symbol next to an entity name, it means that the data for that entity didn't load successfully.</span></span>
- <span data-ttu-id="b593a-111">**Көзі**: нысанды қабылдаған деректер көзінің түрі</span><span class="sxs-lookup"><span data-stu-id="b593a-111">**Source**: The type of data source that ingested the entity</span></span>
- <span data-ttu-id="b593a-112">**Жасаған**: нысанды жасаған тұлғаның аты</span><span class="sxs-lookup"><span data-stu-id="b593a-112">**Created by**: Name of the person who created the entity</span></span>
- <span data-ttu-id="b593a-113">**Жасалды**: нысанды жасау күні мен уақыты</span><span class="sxs-lookup"><span data-stu-id="b593a-113">**Created**: Date and time of the entity creation</span></span>
- <span data-ttu-id="b593a-114">**Жаңартқан**: нысанды жаңартқан тұлғаның аты</span><span class="sxs-lookup"><span data-stu-id="b593a-114">**Updated by**: Name of the person who updated the entity</span></span>
- <span data-ttu-id="b593a-115">**Соңғы жаңартылды**: нысаның соңғы жаңарту күні мен уақыты</span><span class="sxs-lookup"><span data-stu-id="b593a-115">**Last updated**: Date and time of the last update of the entity</span></span>
- <span data-ttu-id="b593a-116">**Соңғы жаңарту**: соңғы деректерді жаңарту күні мен уақыты</span><span class="sxs-lookup"><span data-stu-id="b593a-116">**Last refresh**: Date and time of the last data refresh</span></span>

## <a name="exploring-a-specific-entitys-data"></a><span data-ttu-id="b593a-117">Белгілі бір нысан деректерін зерттеу</span><span class="sxs-lookup"><span data-stu-id="b593a-117">Exploring a specific entity's data</span></span>

<span data-ttu-id="b593a-118">Нысанға қосылған әр түрлі өрістер мен жазбаларды зерттеу үшін нысанды таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="b593a-118">Select an entity to explore the different fields and records included within that entity.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="b593a-119">![Нысан таңдау](media/data-manager-entities-data.png "Нысанды таңдау")</span><span class="sxs-lookup"><span data-stu-id="b593a-119">![Select an entity](media/data-manager-entities-data.png "Select an entity")</span></span>

- <span data-ttu-id="b593a-120">**Деректер** қойыншасында нысанның жеке жазбалары туралы мәліметтер келтірілген кесте көрсетілген.</span><span class="sxs-lookup"><span data-stu-id="b593a-120">The **Data** tab shows a table listing details about individual records of the entity.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="b593a-121">![Өрістер кестесі](media/data-manager-entities-fields.PNG "Өрістер кестесі")</span><span class="sxs-lookup"><span data-stu-id="b593a-121">![Fields table](media/data-manager-entities-fields.PNG "Fields table")</span></span>

- <span data-ttu-id="b593a-122">**Төлсипаттар** қойыншасы әдепкі бойынша таңдалады және өріс атаулары, деректер түрлері және түрлер сияқты таңдалған нысан үшін мәліметтерді қарап шығу кестесін көрсетеді.</span><span class="sxs-lookup"><span data-stu-id="b593a-122">The **Attributes** tab is selected by default and shows a table to review details for the selected entity, such as field names, data types, and types.</span></span> <span data-ttu-id="b593a-123">**Түрі** бағанында жүйемен автоматты анықталатын немесе пайдаланушылар [қолмен салыстыратын](map-entities.md) Common Data Model байланысты түрлері көрсетіледі.</span><span class="sxs-lookup"><span data-stu-id="b593a-123">The **Type** column shows Common Data Model associated types, which are either auto-identified by the system or [manually mapped](map-entities.md) by users.</span></span> <span data-ttu-id="b593a-124">Олар — төлсипаттардан өзгеше болуы мүмкін семантикалық түрлер (мысалы, төмендегі *Электрондық пошта* өрісінде *Мәтін* деректер түрі бар), бірақ оның (семантикалық) Common Data Model түрі *Электрондық пошта* немесе *Электрондық пошта мекенжайы* болуы мүмкін.</span><span class="sxs-lookup"><span data-stu-id="b593a-124">These are semantic types that can differ from the attributes' data types—for example, the field *Email* below has a data type *Text* but its (semantic) Common Data Model type might be *Email* or *EmailAddress*.</span></span>

> [!NOTE]
> <span data-ttu-id="b593a-125">Екі кестеде тек нысан деректерінің үлгісі көрсетіледі.</span><span class="sxs-lookup"><span data-stu-id="b593a-125">Both tables show only a sample of your entity's data.</span></span> <span data-ttu-id="b593a-126">Толық деректер жиынын көру үшін **Деректер көздері** бетіне өтіп, нысанды таңдап, **Өңдеу** параметрін таңдап, [Деректер көздері](data-sources.md) ішінде түсіндірілгендей Power Query редакторы бар осы нысан деректерін көріңіз.</span><span class="sxs-lookup"><span data-stu-id="b593a-126">To view the full data set, go to the **Data sources** page, select an entity, select **Edit**, and then view this entity's data with the Power Query editor as explained in [Data sources](data-sources.md).</span></span>

<span data-ttu-id="b593a-127">Нысанда қабылданған деректер туралы қосымша ақпарат алу үшін, **Қорытынды** бағанында бос мәндер, жоқ мәндер, бірегей мәндер, сандар сияқты кейбір маңызды сипаттамалар және деректеріңізге қолданылатын таратулар қамтамасыз етіледі.</span><span class="sxs-lookup"><span data-stu-id="b593a-127">To learn more about the data ingested in the entity, the **Summary** column provides you with some important characteristics of the data, such as nulls, missing values, unique values, counts, and distributions, as applicable to your data.</span></span>

<span data-ttu-id="b593a-128">Деректер қорытындысын көру үшін диаграмма белгішесін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="b593a-128">Select the chart icon to see the summary of the data.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="b593a-129">![Қорытынды таңбасы](media/data-manager-entities-summary.png "Деректер қорытындысы кестесі")</span><span class="sxs-lookup"><span data-stu-id="b593a-129">![Summary symbol](media/data-manager-entities-summary.png "Data summary table")</span></span>

### <a name="next-step"></a><span data-ttu-id="b593a-130">Келесі қадам</span><span class="sxs-lookup"><span data-stu-id="b593a-130">Next step</span></span>

<span data-ttu-id="b593a-131">Қабылданған деректерді *салыстыру*, *сәйкестендіру* және *біріктіру* жолы туралы ақпарат алу үшін [Біріктіру](data-unification.md) тақырыбын қараңыз.</span><span class="sxs-lookup"><span data-stu-id="b593a-131">See the [Unify](data-unification.md) topic to learn how to *map*, *match*, and *merge* the ingested data.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
