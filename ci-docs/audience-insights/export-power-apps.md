---
title: Power Apps коннекторы
description: Power Apps және Power Automate арқылы қосылу.
ms.date: 01/19/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: Nils-2m
ms.author: nikeller
manager: shellyha
ms.openlocfilehash: 3fa91553fd50a22ab62b5a2b1e3f13b9483776a8
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: kk-KZ
ms.lasthandoff: 03/15/2021
ms.locfileid: "5598162"
---
# <a name="microsoft-power-apps-connector-preview"></a><span data-ttu-id="12ab9-103">Microsoft Power Apps қосқышы (алдын ала қарау)</span><span class="sxs-lookup"><span data-stu-id="12ab9-103">Microsoft Power Apps connector (preview)</span></span>

<span data-ttu-id="12ab9-104">Power Apps бағдарламасымен бірыңғай тұтынушы профильдерін жекелендірілген бағдарламаларыңызға қосыңыз.</span><span class="sxs-lookup"><span data-stu-id="12ab9-104">Bring unified customer profiles into your personalized apps with Power Apps.</span></span>

## <a name="connect-power-apps-and-dynamics-365-customer-insights"></a><span data-ttu-id="12ab9-105">Power Apps және Dynamics 365 Customer Insights бағдарламаларын қосу</span><span class="sxs-lookup"><span data-stu-id="12ab9-105">Connect Power Apps and Dynamics 365 Customer Insights</span></span>

<span data-ttu-id="12ab9-106">Customer Insights көптеген [Power Apps бағдарламасында қолжетімді көздердің](/powerapps/maker/canvas-apps/working-with-data-sources) бірі.</span><span class="sxs-lookup"><span data-stu-id="12ab9-106">Customer Insights is one of the many [available sources for data in Power Apps](/powerapps/maker/canvas-apps/working-with-data-sources).</span></span>

<span data-ttu-id="12ab9-107">[Бағдарламаға деректер қосылымын қосу](/powerapps/maker/canvas-apps/add-data-connection) жолы туралы ақпаратты Power Apps құжаттамасынан қараңыз.</span><span class="sxs-lookup"><span data-stu-id="12ab9-107">Refer to the Power Apps documentation to learn how to [add a data connection to an app](/powerapps/maker/canvas-apps/add-data-connection).</span></span> <span data-ttu-id="12ab9-108">Сондай-ақ сізге [Power Apps кенеп бағдарламаларында үлкен деректер жиындарын өңдеу үшін өкілеттеуді пайдалану жолын](/powerapps/maker/canvas-apps/delegation-overview) қарап шығуды ұсынамыз.</span><span class="sxs-lookup"><span data-stu-id="12ab9-108">We recommend you also review [how Power Apps uses delegation to handle large datasets in Canvas apps](/powerapps/maker/canvas-apps/delegation-overview).</span></span>

## <a name="available-entities"></a><span data-ttu-id="12ab9-109">Бар нысандар</span><span class="sxs-lookup"><span data-stu-id="12ab9-109">Available entities</span></span>

<span data-ttu-id="12ab9-110">Customer Insights деректер қосылымы ретінде қосқаннан кейін, келесі нысандарды Power Apps бағдарламасында таңдауға болады:</span><span class="sxs-lookup"><span data-stu-id="12ab9-110">After adding Customer Insights as a data connection, you can choose the following entities in Power Apps:</span></span>

- <span data-ttu-id="12ab9-111">Тұтынушы: [бірыңғай тұтынушы профилінің](customer-profiles.md) деректерін пайдалану.</span><span class="sxs-lookup"><span data-stu-id="12ab9-111">Customer: to use data from the [unified customer profile](customer-profiles.md).</span></span>
- <span data-ttu-id="12ab9-112">Бірыңғай әрекет: бағдарламада [әрекеттің уақыт шкаласын](activities.md) көрсету.</span><span class="sxs-lookup"><span data-stu-id="12ab9-112">UnifiedActivity: to display the [activity timeline](activities.md) on the app.</span></span>

## <a name="limitations"></a><span data-ttu-id="12ab9-113">Шектеулер</span><span class="sxs-lookup"><span data-stu-id="12ab9-113">Limitations</span></span>

### <a name="retrievable-entities"></a><span data-ttu-id="12ab9-114">Шығарып алуға болатын нысандар</span><span class="sxs-lookup"><span data-stu-id="12ab9-114">Retrievable entities</span></span>

<span data-ttu-id="12ab9-115">**Тұтынушы**, **Бірыңғай әрекет** және **Сегменттер** нысандарын тек Power Apps коннекторы арқылы шығарып ала аласыз.</span><span class="sxs-lookup"><span data-stu-id="12ab9-115">You can only retrieve the **Customer**, **UnifiedActivity**, and **Segments** entities through the Power Apps connector.</span></span> <span data-ttu-id="12ab9-116">Басқа нысандар негізгі коннектор бұл нысандарды Power Automate ішіндегі триггерлер арқылы қолдайтындықтан көрсетіледі.</span><span class="sxs-lookup"><span data-stu-id="12ab9-116">Other entities are shown because the underlying connector supports them through triggers in Power Automate.</span></span>  

### <a name="delegation"></a><span data-ttu-id="12ab9-117">Өкіл</span><span class="sxs-lookup"><span data-stu-id="12ab9-117">Delegation</span></span>

<span data-ttu-id="12ab9-118">Өкілеттеу «Тұтынушы» нысаны мен «Бірыңғай әрекет нысаны» үшін жұмыс істейді.</span><span class="sxs-lookup"><span data-stu-id="12ab9-118">Delegation works for the Customer entity and UnifiedActivity entity.</span></span> 

- <span data-ttu-id="12ab9-119">**Тұтынушы** нысанына арналған өкілеттік: осы нысан үшін өкілеттікті пайдалану үшін өрістерді [Іздеу және сүзгілеу индексі](search-filter-index.md) жүйесінде индекстеу керек.</span><span class="sxs-lookup"><span data-stu-id="12ab9-119">Delegation for **Customer** entity: To use delegation for this entity, the fields need to be indexed in [Search & filter index](search-filter-index.md).</span></span>  

- <span data-ttu-id="12ab9-120">**Бірыңғай әрекет** үшін өкілеттеу: бұл нысан үшін өкілеттеу тек **Әрекет идентификаторы** және **Тұтынушы идентификаторы** өрістері үшін жұмыс істейді.</span><span class="sxs-lookup"><span data-stu-id="12ab9-120">Delegation for **UnifiedActivity**: Delegation for this entity only works for the fields **ActivityId** and **CustomerId**.</span></span>  

- <span data-ttu-id="12ab9-121">Өкілеттеу туралы қосымша ақпаратты [Power Apps өкілеттеуге болатын функциялары мен әрекеттері](/connectors/commondataservice/#power-apps-delegable-functions-and-operations-for-the-cds-for-apps) бөлімінен қараңыз.</span><span class="sxs-lookup"><span data-stu-id="12ab9-121">For more information about delegation, see [Power Apps delegable functions and operations](/connectors/commondataservice/#power-apps-delegable-functions-and-operations-for-the-cds-for-apps).</span></span> 

## <a name="example-gallery-control"></a><span data-ttu-id="12ab9-122">Галереяны басқару мысалы</span><span class="sxs-lookup"><span data-stu-id="12ab9-122">Example gallery control</span></span>

<span data-ttu-id="12ab9-123">Мысалы, тұтынушы профильдерін [галереяны басқару элементіне](/powerapps/maker/canvas-apps/add-gallery) қосасыз.</span><span class="sxs-lookup"><span data-stu-id="12ab9-123">For example, you add customer profiles to a [gallery control](/powerapps/maker/canvas-apps/add-gallery).</span></span>

1. <span data-ttu-id="12ab9-124">Құрылатын бағдарламаға **Галерея** басқару құралын қосыңыз.</span><span class="sxs-lookup"><span data-stu-id="12ab9-124">Add a **Gallery** control to an app you're building.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="12ab9-125">![Галерея элементін қосу](media/connector-powerapps9.png "Галерея элементін қосу")</span><span class="sxs-lookup"><span data-stu-id="12ab9-125">![Add a gallery element](media/connector-powerapps9.png "Add a gallery element")</span></span>

1. <span data-ttu-id="12ab9-126">**Тұтынушы** параметрін элементтердің деректер көзі ретінде таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="12ab9-126">Select **Customer** as the data source for items.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="12ab9-127">![Деректер көзін таңдау](media/choose-datasource-powerapps.png "Деректер көзін таңдау")</span><span class="sxs-lookup"><span data-stu-id="12ab9-127">![Select a data source](media/choose-datasource-powerapps.png "Select a data source")</span></span>

1. <span data-ttu-id="12ab9-128">Галереяда көрсетілетін Тұтынушы нысаны өрісін таңдау үшін оң жақта деректер тақтасын өзгерте аласыз.</span><span class="sxs-lookup"><span data-stu-id="12ab9-128">You can change the data panel on the right to select which field for the Customer entity to show on the gallery.</span></span>

1. <span data-ttu-id="12ab9-129">Галереяда таңдалған тұтынушыдан кез келген өрісті көрсету керек болса, белгінің мәтін сипатын толтырыңыз:  **{Name_of_the_gallery}.Selected.{property_name}**</span><span class="sxs-lookup"><span data-stu-id="12ab9-129">If you want to show any field from the selected customer on the gallery, fill in the Text property of a label:  **{Name_of_the_gallery}.Selected.{property_name}**</span></span>

    <span data-ttu-id="12ab9-130">Мысалы: Gallery1.Selected.address1_city</span><span class="sxs-lookup"><span data-stu-id="12ab9-130">Example: Gallery1.Selected.address1_city</span></span>

1. <span data-ttu-id="12ab9-131">Тұтынушының бірыңғай уақыт шкаласын көрсету үшін галерея элементін қосып, элементтер сипатын қосыңыз: **Filter('UnifiedActivity', CustomerId = {Customer_Id})**</span><span class="sxs-lookup"><span data-stu-id="12ab9-131">To display the unified timeline for a customer, add a Gallery element, and add the Items property: **Filter('UnifiedActivity', CustomerId = {Customer_Id})**</span></span>

    <span data-ttu-id="12ab9-132">Мысалы: Filter('UnifiedActivity', CustomerId = Gallery1.Selected.CustomerId)</span><span class="sxs-lookup"><span data-stu-id="12ab9-132">Example: Filter('UnifiedActivity', CustomerId = Gallery1.Selected.CustomerId)</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]