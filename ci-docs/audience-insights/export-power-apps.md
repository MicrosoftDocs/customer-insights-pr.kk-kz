---
title: Power Apps коннекторы
description: Power Apps және Power Automate арқылы қосылу.
ms.date: 08/21/2020
ms.reviewer: nikeller
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: b6ec103e29e218b2f27bfc1193300ea793a6b30b
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: kk-KZ
ms.lasthandoff: 11/03/2020
ms.locfileid: "4406208"
---
# <a name="microsoft-power-apps-connector-preview"></a><span data-ttu-id="4b605-103">Microsoft Power Apps қосқышы (алдын ала қарау)</span><span class="sxs-lookup"><span data-stu-id="4b605-103">Microsoft Power Apps connector (preview)</span></span>

<span data-ttu-id="4b605-104">Power Apps бағдарламасымен бірыңғай тұтынушы профильдерін жекелендірілген бағдарламаларыңызға қосыңыз.</span><span class="sxs-lookup"><span data-stu-id="4b605-104">Bring unified customer profiles into your personalized apps with Power Apps.</span></span>

## <a name="connect-power-apps-and-dynamics-365-customer-insights"></a><span data-ttu-id="4b605-105">Power Apps және Dynamics 365 Customer Insights бағдарламаларын қосу</span><span class="sxs-lookup"><span data-stu-id="4b605-105">Connect Power Apps and Dynamics 365 Customer Insights</span></span>

<span data-ttu-id="4b605-106">Customer Insights көптеген [Power Apps бағдарламасында қолжетімді көздердің](https://docs.microsoft.com/powerapps/maker/canvas-apps/working-with-data-sources) бірі.</span><span class="sxs-lookup"><span data-stu-id="4b605-106">Customer Insights is one of the many [available sources for data in Power Apps](https://docs.microsoft.com/powerapps/maker/canvas-apps/working-with-data-sources).</span></span>

<span data-ttu-id="4b605-107">[Бағдарламаға деректер қосылымын қосу](https://docs.microsoft.com/powerapps/maker/canvas-apps/add-data-connection) жолы туралы ақпаратты Power Apps құжаттамасынан қараңыз.</span><span class="sxs-lookup"><span data-stu-id="4b605-107">Refer to the Power Apps documentation to learn how to [add a data connection to an app](https://docs.microsoft.com/powerapps/maker/canvas-apps/add-data-connection).</span></span> <span data-ttu-id="4b605-108">Сондай-ақ сізге [Power Apps кенеп бағдарламаларында үлкен деректер жиындарын өңдеу үшін өкілеттеуді пайдалану жолын](https://docs.microsoft.com/powerapps/maker/canvas-apps/delegation-overview) қарап шығуды ұсынамыз.</span><span class="sxs-lookup"><span data-stu-id="4b605-108">We recommend you also review [how Power Apps uses delegation to handle large datasets in Canvas apps](https://docs.microsoft.com/powerapps/maker/canvas-apps/delegation-overview).</span></span>

## <a name="available-entities"></a><span data-ttu-id="4b605-109">Бар нысандар</span><span class="sxs-lookup"><span data-stu-id="4b605-109">Available entities</span></span>

<span data-ttu-id="4b605-110">Customer Insights деректер қосылымы ретінде қосқаннан кейін, келесі нысандарды Power Apps бағдарламасында таңдауға болады:</span><span class="sxs-lookup"><span data-stu-id="4b605-110">After adding Customer Insights as a data connection, you can choose the following entities in Power Apps:</span></span>

- <span data-ttu-id="4b605-111">Тұтынушы: [бірыңғай тұтынушы профилінің](customer-profiles.md) деректерін пайдалану.</span><span class="sxs-lookup"><span data-stu-id="4b605-111">Customer: to use data from the [unified customer profile](customer-profiles.md).</span></span>
- <span data-ttu-id="4b605-112">Бірыңғай тұтынушы әрекеті: бағдарламада [бірыңғай уақыт шкаласын](activities.md) көрсету.</span><span class="sxs-lookup"><span data-stu-id="4b605-112">Unified Customer Activity: to display the [activity timeline](activities.md) on the app.</span></span>

## <a name="limitations"></a><span data-ttu-id="4b605-113">Шектеулер</span><span class="sxs-lookup"><span data-stu-id="4b605-113">Limitations</span></span>

### <a name="retrievable-entities"></a><span data-ttu-id="4b605-114">Шығарып алуға болатын нысандар</span><span class="sxs-lookup"><span data-stu-id="4b605-114">Retrievable entities</span></span>

<span data-ttu-id="4b605-115">**Тұтынушы**, **Бірыңғай әрекет** және **Сегменттер** нысандарын тек Power Apps коннекторы арқылы шығарып ала аласыз.</span><span class="sxs-lookup"><span data-stu-id="4b605-115">You can only retrieve the **Customer**, **UnifiedActivity**, and **Segments** entities through the Power Apps connector.</span></span> <span data-ttu-id="4b605-116">Басқа нысандар негізгі коннектор бұл нысандарды Power Automate ішіндегі триггерлер арқылы қолдайтындықтан көрсетіледі.</span><span class="sxs-lookup"><span data-stu-id="4b605-116">Other entities are shown because the underlying connector supports them through triggers in Power Automate.</span></span>  

### <a name="delegation"></a><span data-ttu-id="4b605-117">Өкіл</span><span class="sxs-lookup"><span data-stu-id="4b605-117">Delegation</span></span>

<span data-ttu-id="4b605-118">Өкілеттеу «Тұтынушы» нысаны мен «Бірыңғай әрекет нысаны» үшін жұмыс істейді.</span><span class="sxs-lookup"><span data-stu-id="4b605-118">Delegation works for the Customer entity and UnifiedActivity entity.</span></span> 

- <span data-ttu-id="4b605-119">**Тұтынушы** нысанына арналған өкілеттік: осы нысан үшін өкілеттікті пайдалану үшін өрістерді [Іздеу және сүзгілеу индексі](search-filter-index.md) жүйесінде индекстеу керек.</span><span class="sxs-lookup"><span data-stu-id="4b605-119">Delegation for **Customer** entity: To use delegation for this entity, the fields need to be indexed in [Search & filter index](search-filter-index.md).</span></span>  

- <span data-ttu-id="4b605-120">**Бірыңғай әрекет** үшін өкілеттеу: бұл нысан үшін өкілеттеу тек **Әрекет идентификаторы** және **Тұтынушы идентификаторы** өрістері үшін жұмыс істейді.</span><span class="sxs-lookup"><span data-stu-id="4b605-120">Delegation for **UnifiedActivity**: Delegation for this entity only works for the fields **ActivityId** and **CustomerId**.</span></span>  

- <span data-ttu-id="4b605-121">Өкілеттеу туралы қосымша ақпаратты [Power Apps өкілеттеуге болатын функциялары мен әрекеттері](https://docs.microsoft.com/connectors/commondataservice/#power-apps-delegable-functions-and-operations-for-the-cds-for-apps) бөлімінен қараңыз.</span><span class="sxs-lookup"><span data-stu-id="4b605-121">For more information about delegation, see [Power Apps delegable functions and operations](https://docs.microsoft.com/connectors/commondataservice/#power-apps-delegable-functions-and-operations-for-the-cds-for-apps).</span></span> 

## <a name="example-gallery-control"></a><span data-ttu-id="4b605-122">Галереяны басқару мысалы</span><span class="sxs-lookup"><span data-stu-id="4b605-122">Example gallery control</span></span>

<span data-ttu-id="4b605-123">Мысалы, тұтынушы профильдерін [галереяны басқару элементіне](https://docs.microsoft.com/powerapps/maker/canvas-apps/add-gallery) қосасыз.</span><span class="sxs-lookup"><span data-stu-id="4b605-123">For example, you add customer profiles to a [gallery control](https://docs.microsoft.com/powerapps/maker/canvas-apps/add-gallery).</span></span>

1. <span data-ttu-id="4b605-124">Құрылатын бағдарламаға **Галерея** басқару құралын қосыңыз.</span><span class="sxs-lookup"><span data-stu-id="4b605-124">Add a **Gallery** control to an app you're building.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="4b605-125">![Галерея элементін қосу](media/connector-powerapps9.png "Галерея элементін қосу")</span><span class="sxs-lookup"><span data-stu-id="4b605-125">![Add a gallery element](media/connector-powerapps9.png "Add a gallery element")</span></span>

1. <span data-ttu-id="4b605-126">**Тұтынушы** параметрін элементтердің деректер көзі ретінде таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="4b605-126">Select **Customer** as the data source for items.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="4b605-127">![Деректер көзін таңдау](media/choose-datasource-powerapps.png "Деректер көзін таңдау")</span><span class="sxs-lookup"><span data-stu-id="4b605-127">![Select a data source](media/choose-datasource-powerapps.png "Select a data source")</span></span>

1. <span data-ttu-id="4b605-128">Галереяда көрсетілетін Тұтынушы нысаны өрісін таңдау үшін оң жақта деректер тақтасын өзгерте аласыз.</span><span class="sxs-lookup"><span data-stu-id="4b605-128">You can change the data panel on the right to select which field for the Customer entity to show on the gallery.</span></span>

1. <span data-ttu-id="4b605-129">Галереяда таңдалған тұтынушыдан кез келген өрісті көрсету керек болса, белгінің мәтін сипатын толтырыңыз:  **{Name_of_the_gallery}.Selected.{property_name}**</span><span class="sxs-lookup"><span data-stu-id="4b605-129">If you want to show any field from the selected customer on the gallery, fill in the Text property of a label:  **{Name_of_the_gallery}.Selected.{property_name}**</span></span>

    <span data-ttu-id="4b605-130">Мысалы: Gallery1.Selected.address1_city</span><span class="sxs-lookup"><span data-stu-id="4b605-130">Example: Gallery1.Selected.address1_city</span></span>

1. <span data-ttu-id="4b605-131">Тұтынушының бірыңғай уақыт шкаласын көрсету үшін галерея элементін қосып, элементтер сипатын қосыңыз: **Filter('UnifiedActivity', CustomerId = {Customer_Id})**</span><span class="sxs-lookup"><span data-stu-id="4b605-131">To display the unified timeline for a customer, add a Gallery element, and add the Items property: **Filter('UnifiedActivity', CustomerId = {Customer_Id})**</span></span>

    <span data-ttu-id="4b605-132">Мысалы: Filter('UnifiedActivity', CustomerId = Gallery1.Selected.CustomerId)</span><span class="sxs-lookup"><span data-stu-id="4b605-132">Example: Filter('UnifiedActivity', CustomerId = Gallery1.Selected.CustomerId)</span></span>
