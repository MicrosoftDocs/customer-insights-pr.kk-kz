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
# <a name="connect-to-data-in-a-common-data-service-managed-data-lake"></a><span data-ttu-id="0deb8-103">Common Data Service басқарылатын деректер ағынында деректерге қосылу</span><span class="sxs-lookup"><span data-stu-id="0deb8-103">Connect to data in a Common Data Service managed data lake</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="0deb8-104">Бұл мақалада бұрыннан бар Dynamics 365 тұтынушылары өздерінің аналитикалық нысандарына Common Data Service басқарылатын көлінде қалай жылдам қосыла алатыны туралы ақпарат берілген.</span><span class="sxs-lookup"><span data-stu-id="0deb8-104">This article provides information on how existing Dynamics 365 customers can quickly connect to their analytical entities in the Common Data Service managed lake.</span></span> <span data-ttu-id="0deb8-105">Жалғастыру және басқарылатын көлде бар нысандардың тізімін қарау үшін Common Data Service ұйымының әкімшісі болуыңыз керек.</span><span class="sxs-lookup"><span data-stu-id="0deb8-105">You must be an admin on the Common Data Service organization to proceed and see the list of entities available in the managed lake.</span></span>

## <a name="important-considerations"></a><span data-ttu-id="0deb8-106">Маңызды жайттар</span><span class="sxs-lookup"><span data-stu-id="0deb8-106">Important considerations</span></span>

<span data-ttu-id="0deb8-107">Azure Data Lake Storage сияқты онлайн қызметтерде сақталған деректер Dynamics 365 Customer Insights бағдарламасында деректер өңделетін немесе сақталатын жерден басқа жерде сақталуы мүмкін.</span><span class="sxs-lookup"><span data-stu-id="0deb8-107">Data stored in online services, such as Azure Data Lake Storage, may be stored in a different location than where data is processed or stored in Dynamics 365 Customer Insights.</span></span><span data-ttu-id="0deb8-108"> Онлайн қызметтерде сақталған деректерді импорттау немесе қосу арқылы сіз деректердің Dynamics 365 Customer Insights бағдарламасына тасымалдануына және сақталуына келісім бересіз. [Қосымша ақпаратты Microsoft сенім орталығынан қараңыз.](https://www.microsoft.com/trust-center)</span><span class="sxs-lookup"><span data-stu-id="0deb8-108"> By importing or connecting to data stored in online services, you agree that data can be transferred to and stored with Dynamics 365 Customer Insights. [Learn more at the Microsoft Trust Center.](https://www.microsoft.com/trust-center)</span></span>

## <a name="connect-to-a-common-data-service-managed-lake"></a><span data-ttu-id="0deb8-109">Common Data Service басқарылатын ағынына қосылу</span><span class="sxs-lookup"><span data-stu-id="0deb8-109">Connect to a Common Data Service managed lake</span></span>

1. <span data-ttu-id="0deb8-110">Аудитория мәліметтерінде **Деректер** > **Деректер көздері** тармағына өтіңіз.</span><span class="sxs-lookup"><span data-stu-id="0deb8-110">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="0deb8-111">**Деректер көзін қосу** түймешігін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="0deb8-111">Select **Add data source**.</span></span>

3. <span data-ttu-id="0deb8-112">**Common Data Service қызметіне қосылу** параметрін таңдап, **Келесі** параметрін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="0deb8-112">Select **Connect to Common Data Service** and select **Next**.</span></span>

4. <span data-ttu-id="0deb8-113">Деректер көзінің **Атау** өрісін енгізіңіз және **Келесі** түймешігін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="0deb8-113">Enter a **Name** for the data source and select **Next**.</span></span> <span data-ttu-id="0deb8-114">Нұсқаулықтар атауын енгізіңіз:</span><span class="sxs-lookup"><span data-stu-id="0deb8-114">Name guidelines:</span></span> 
   - <span data-ttu-id="0deb8-115">Әріптен бастаңыз.</span><span class="sxs-lookup"><span data-stu-id="0deb8-115">Start with a letter.</span></span>
   - <span data-ttu-id="0deb8-116">Тек әріптер мен сандарды пайдаланыңыз.</span><span class="sxs-lookup"><span data-stu-id="0deb8-116">Use letters and numbers only.</span></span> <span data-ttu-id="0deb8-117">Арнайы таңбалар мен бос орындарға рұқсат етілмейді.</span><span class="sxs-lookup"><span data-stu-id="0deb8-117">Special characters and spaces are not allowed.</span></span>
   - <span data-ttu-id="0deb8-118">3-64 аралығындағы таңбаларды пайдаланыңыз.</span><span class="sxs-lookup"><span data-stu-id="0deb8-118">Use between 3 and 64 characters.</span></span>

5. <span data-ttu-id="0deb8-119">Common Data Service ұйымының **Сервер мекенжайын** қамтамасыз етіп, **Кіру** параметрін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="0deb8-119">Provide the **Server address** for your Common Data Service organization, and select **Sign in**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="0deb8-120">![Common Data Service сервер мекенжайын енгізу диалог терезесі](media/enter-CDS-org-details.png)</span><span class="sxs-lookup"><span data-stu-id="0deb8-120">![Dialog box to enter Common Data Service server address](media/enter-CDS-org-details.png)</span></span>

6. <span data-ttu-id="0deb8-121">Қолжетімді тізімінен қабылдау қажет нысандарды таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="0deb8-121">Select the entities you want to ingest from the available list.</span></span>    

   > [!NOTE]
   > <span data-ttu-id="0deb8-122">Кейбір нысандар бұрын таңдалған болса, оларды басқа Dynamics 365 бағдарламалары пайдалануы мүмкін (мысалы, Dynamics 365 Sales Insights немесе Customer Service Insights).</span><span class="sxs-lookup"><span data-stu-id="0deb8-122">If some entities are already selected, they might be used by other Dynamics 365 applications (such as Dynamics 365 Sales Insights or Customer Service Insights).</span></span> <span data-ttu-id="0deb8-123">Таңдауды өзгерте алмайсыз.</span><span class="sxs-lookup"><span data-stu-id="0deb8-123">You can't change the selection.</span></span> <span data-ttu-id="0deb8-124">Бұл нысандар деректер көзі жасалғаннан кейін қолжетімді болады.</span><span class="sxs-lookup"><span data-stu-id="0deb8-124">These entities will be available once the data source is created.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="0deb8-125">![Common Data Service ұйымындағы нысандар тізімін көрсететін диалог терезесі](media/select-analytical-entities.png)</span><span class="sxs-lookup"><span data-stu-id="0deb8-125">![Dialog box showing a list of entities in the Common Data Service org](media/select-analytical-entities.png)</span></span>

7. <span data-ttu-id="0deb8-126">Common Data Service басқарылатын ағынымен таңдалған нысандарды синхрондауды бастау үшін таңдауыңызды сақтаңыз.</span><span class="sxs-lookup"><span data-stu-id="0deb8-126">Save your selection to start syncing the selected entities to the Common Data Service managed lake.</span></span> <span data-ttu-id="0deb8-127">**Дереккөздер** бетінен жаңадан қосылған байланысты таба аласыз.</span><span class="sxs-lookup"><span data-stu-id="0deb8-127">You'll find the newly added connection on the **Data sources** page.</span></span> <span data-ttu-id="0deb8-128">Ол кезегімен жаңартылады және барлық нысандарды синхрондағанға дейін нысандар санын 0 деп көрсетеді.</span><span class="sxs-lookup"><span data-stu-id="0deb8-128">It will be queued for refresh and show the entities count as 0 until all the entities are synced.</span></span>

<span data-ttu-id="0deb8-129">Ортаның тек бір деректер көзі бір уақытта бір Common Data Service басқарылатын көлін пайдалана алады.</span><span class="sxs-lookup"><span data-stu-id="0deb8-129">Only one data source of an environment can simultaneously use the same Common Data Service managed lake.</span></span>

## <a name="edit-a-common-data-service-managed-lake-data-source"></a><span data-ttu-id="0deb8-130">Common Data Service басқарылатын ағынның дереккөзін өңдеу</span><span class="sxs-lookup"><span data-stu-id="0deb8-130">Edit a Common Data Service managed lake data source</span></span>

<span data-ttu-id="0deb8-131">Дереккөзді жасағаннан кейін ғана нысан таңдауын өңдейсіз.</span><span class="sxs-lookup"><span data-stu-id="0deb8-131">You only edit the entity selection after creating the data source.</span></span> <span data-ttu-id="0deb8-132">Мысалы, Common Data Service ішіне қосымша нысандар қосылса және оларды импорттау қажет болса.</span><span class="sxs-lookup"><span data-stu-id="0deb8-132">For example, if additional entities were added to Common Data Service and you want to import them too.</span></span>    
<span data-ttu-id="0deb8-133">Басқа Common Data Service жүйесіне қосылу үшін [жаңа дереккөз жасаңыз](#connect-to-a-common-data-service-managed-lake).</span><span class="sxs-lookup"><span data-stu-id="0deb8-133">To connect to a different Common Data Service, [create a new data source](#connect-to-a-common-data-service-managed-lake).</span></span>

1. <span data-ttu-id="0deb8-134">Аудитория мәліметтерінде **Деректер** > **Деректер көздері** тармағына өтіңіз.</span><span class="sxs-lookup"><span data-stu-id="0deb8-134">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="0deb8-135">Жаңарту керек деректер көзінің жанындағы көп нүктені таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="0deb8-135">Next to the data source you'd like to update, select the ellipsis.</span></span>

3. <span data-ttu-id="0deb8-136">Тізімнен **Өңдеу** параметрін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="0deb8-136">Select the **Edit** option from the list.</span></span>

4. <span data-ttu-id="0deb8-137">Қолжетімді нысандар тізімінен қосымша нысандарды таңдап, **Сақтау** параметрін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="0deb8-137">Select additional entities from the available list of entities and select **Save**.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]