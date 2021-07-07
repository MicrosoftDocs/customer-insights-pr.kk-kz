---
title: Үшінші тарап Leadspace арттыру платформасы арқылы компания профильдерін арттыру
description: Leadspace үшінші тарап арттыруы туралы жалпы ақпарат.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-MS
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 0496d10c994cd077a778a6e745e3774e316765ae
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: kk-KZ
ms.lasthandoff: 06/24/2021
ms.locfileid: "6305209"
---
# <a name="enrichment-of-company-profiles-with-leadspace-preview"></a><span data-ttu-id="4778a-103">Leadspace (алдын ала қарау) көмегімен компания профильдерін толықтыру</span><span class="sxs-lookup"><span data-stu-id="4778a-103">Enrichment of company profiles with Leadspace (preview)</span></span>

<span data-ttu-id="4778a-104">Leadspace — бизнес - бизнес тұтынушы деректері платформасын қамтамасыз ететін деректер ғылымы компаниясы.</span><span class="sxs-lookup"><span data-stu-id="4778a-104">Leadspace is a data science company that provides a B2B Customer Data Platform.</span></span> <span data-ttu-id="4778a-105">Ол компанияларға арналған бірыңғай тұтынушы профильдері бар тұтынушыларға деректерін толықтыруына мүмкіндік береді.</span><span class="sxs-lookup"><span data-stu-id="4778a-105">It enables customers with unified customer profiles for companies to enrich their data.</span></span> <span data-ttu-id="4778a-106">Жақсартулар компания өлшемі, орны, саласы және т.б. сияқты көптеген төлсипаттарды қамтиды.</span><span class="sxs-lookup"><span data-stu-id="4778a-106">Enrichments include more attributes such as company size, location, industry, and more.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="4778a-107">Алғышарттар</span><span class="sxs-lookup"><span data-stu-id="4778a-107">Prerequisites</span></span>

<span data-ttu-id="4778a-108">Leadspace теңшеу үшін мына алғышарттар сақталуы қажет:</span><span class="sxs-lookup"><span data-stu-id="4778a-108">To configure Leadspace, the following prerequisites must be met:</span></span>

- <span data-ttu-id="4778a-109">Сізде белсенді Leadspace лицензиясы бар.</span><span class="sxs-lookup"><span data-stu-id="4778a-109">You have an active Leadspace license.</span></span>
- <span data-ttu-id="4778a-110">Компаниялар үшін [бірыңғай тұтынушы профильдері](customer-profiles.md) бар.</span><span class="sxs-lookup"><span data-stu-id="4778a-110">You have [unified customer profiles](customer-profiles.md) for companies.</span></span>
- <span data-ttu-id="4778a-111">Leadspace қосылымын әкімші әлдеқашан конфигурациялаған немесе сізде [әкімші](permissions.md#administrator) рұқсаттары және "мерзімсіз кілт" (**Leadspace таңбалауышы** деп аталады) бар.</span><span class="sxs-lookup"><span data-stu-id="4778a-111">A Leadspace connection has already been configured by an administrator or you have [administrator](permissions.md#administrator) permissions and the “perpetual key” (referred to as **Leadspace token**).</span></span> <span data-ttu-id="4778a-112">Олардың өнімдері туралы ақпарат алу үшін [Leadspace](https://www.leadspace.com/products/leadspace-on-demand/) компаниясына тікелей хабарласыңыз.</span><span class="sxs-lookup"><span data-stu-id="4778a-112">Contact [Leadspace](https://www.leadspace.com/products/leadspace-on-demand/) directly for details about their product.</span></span>

## <a name="configure-the-enrichment"></a><span data-ttu-id="4778a-113">Жақсартуды конфигурациялау</span><span class="sxs-lookup"><span data-stu-id="4778a-113">Configure the enrichment</span></span>

1. <span data-ttu-id="4778a-114">Аудитория мәліметтерінде **Деректер** > **Арттыру** тармағына өтіңіз.</span><span class="sxs-lookup"><span data-stu-id="4778a-114">In audience insights, go to **Data** > **Enrichment**.</span></span>

1. <span data-ttu-id="4778a-115">Leadspace тақтасында **Менің деректерімді жақсарту** параметрін таңдаңыз және **Жұмысты бастау** түймешігін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="4778a-115">Select **Enrich my data** on the Leadspace tile and select **Get started**.</span></span>

   :::image type="content" source="media/leadspace-tile.png" alt-text="Leadspace тақтасының скриншоты.":::

1. <span data-ttu-id="4778a-117">Ашылмалы тізімнен [қосылым](connections.md) таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="4778a-117">Select a [connection](connections.md) from the dropdown list.</span></span> <span data-ttu-id="4778a-118">Егер қосылым болмаса, әкімшіге хабарласыңыз.</span><span class="sxs-lookup"><span data-stu-id="4778a-118">Contact an administrator if no connection is available.</span></span> <span data-ttu-id="4778a-119">Егер сіз әкімші болсаңыз, **Қосылым қосу** түймешігін таңдау арқылы және **Leadspace** параметрін таңдау арқылы қосылым жасай аласыз.</span><span class="sxs-lookup"><span data-stu-id="4778a-119">If you are an administrator, you can create a connection by selecting **Add connection** and choosing **Leadspace**.</span></span> 

1. <span data-ttu-id="4778a-120">Қосылымды растау үшін **Leadspace қосылымына қосылу** түймешігін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="4778a-120">Select **Connect to Leadspace** to confirm the connection.</span></span>

1. <span data-ttu-id="4778a-121">**Келесі** түймешігін таңдаңыз және Leadspace қосылымындағы компания деректерімен жақсарту керек **Тұтынушы деректерінің жиынтығы** параметрін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="4778a-121">Select **Next** and choose the **Customer data set** you want to enrich with company data from Leadspace.</span></span> <span data-ttu-id="4778a-122">Барлық тұтынушы профильдерін арттыру үшін **Тұтынушы** нысанын таңдауға болады немесе сол сегменттегі тек тұтынушы профильдерін арттыру үшін сегмент нысанын таңдауға болады.</span><span class="sxs-lookup"><span data-stu-id="4778a-122">You can select the **Customer** entity to enrich all your customer profiles or select a segment entity to enrich only customer profiles contained in that segment.</span></span>

    :::image type="content" source="media/enrichment-Leadspace-configuration-customer-data-set.png" alt-text="Тұтынушының деректер жиынтығын таңдау кезіндегі скриншот.":::

1. <span data-ttu-id="4778a-124">**Келесі** түймешігін таңдаңыз және бірыңғай профильдердегі өрістердің қай түрін Leadspace қосылымында сәйкес келетін компанияны іздеу үшін қолдану керектігін анықтаңыз.</span><span class="sxs-lookup"><span data-stu-id="4778a-124">Select **Next** and define which fields from your unified profiles are used to look for matching company data from Leadspace.</span></span> <span data-ttu-id="4778a-125">**Компания атауы** өрісі қажет.</span><span class="sxs-lookup"><span data-stu-id="4778a-125">The **Name of company** field is required.</span></span> <span data-ttu-id="4778a-126">Дәлдіктің жоғары сәйкестігі үшін басқа екі өріске дейін, **Компания веб-сайты** және **Компанияның орналасқан жері** өрістерін қосуға болады.</span><span class="sxs-lookup"><span data-stu-id="4778a-126">For a higher match accuracy, up to two other fields, **Company website** and **Company location**, can be added.</span></span>

   :::image type="content" source="media/enrichment-leadspace-mapping.png" alt-text="Leadspace өрісін салыстыру тақтасы.":::

1. <span data-ttu-id="4778a-128">Өрістерді салыстыруды аяқтау үшін **Келесі** түймешігін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="4778a-128">Select **Next** to complete the field mapping.</span></span>

1. <span data-ttu-id="4778a-129">Жақсарту үшін атау беріңіз және таңдауларды қарап шыққаннан кейін **Жақсарту сақтау** түймешігін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="4778a-129">Provide a name for the enrichment and select **Save enrichment** after reviewing your choices.</span></span>


## <a name="configure-the-connection-for-leadspace"></a><span data-ttu-id="4778a-130">Leadspace үшін қосылымды конфигурациялау</span><span class="sxs-lookup"><span data-stu-id="4778a-130">Configure the connection for Leadspace</span></span> 

<span data-ttu-id="4778a-131">Қосылымдарды конфигурациялау үшін сіз әкімші болуыңыз керек.</span><span class="sxs-lookup"><span data-stu-id="4778a-131">You need to be an administrator to configure connections.</span></span> <span data-ttu-id="4778a-132">Жақсартуды конфигурациялау кезінде **Қосылым қосу** түймешігін таңдаңыз *немесе* **Әкімші** > **Қосылымдар** тармағына өтіңіз және Leadspace тақтасында **Орнату** түймешігін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="4778a-132">Select **Add connection** when configuring an enrichment *or* go to **Admin** > **Connections** and select **Set up** on the Leadspace tile.</span></span>

1. <span data-ttu-id="4778a-133">**Жұмысты бастау** түймешігін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="4778a-133">Select **Get Started**.</span></span> 

1. <span data-ttu-id="4778a-134">Қосылым атауын **Көрсетілетін атауы** терезесіне енгізіңіз.</span><span class="sxs-lookup"><span data-stu-id="4778a-134">Enter a name for the connection in the **Display name** box.</span></span>

1. <span data-ttu-id="4778a-135">Жарамды Leadspace таңбалауышын қамтамасыз етіңіз.</span><span class="sxs-lookup"><span data-stu-id="4778a-135">Provide a valid Leadspace token.</span></span>

1. <span data-ttu-id="4778a-136">**Деректердің құпиялылығы мен сәйкестігі** бөлімін қарап шығыңыз және **Келісемін** құсбелгісін қою арқылы келісім беріңіз.</span><span class="sxs-lookup"><span data-stu-id="4778a-136">Review and provide your consent for **Data privacy and compliance** by selecting **I agree**.</span></span>

1. <span data-ttu-id="4778a-137">Конфигурацияны тексеру үшін **Тексеру** түймешігін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="4778a-137">Select **Verify** to validate the configuration.</span></span>

1. <span data-ttu-id="4778a-138">Тексеруді аяқтағаннан кейін **Сақтау** түймешігін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="4778a-138">After completing the verification, select **Save**.</span></span>
   
   :::image type="content" source="media/enrichment-Leadspace-connection.png" alt-text="Leadspace қосылымын конфигурациялау беті.":::

## <a name="enrichment-results"></a><span data-ttu-id="4778a-140">Толықтыру нәтижелері</span><span class="sxs-lookup"><span data-stu-id="4778a-140">Enrichment results</span></span>

<span data-ttu-id="4778a-141">Толықтыруды жаңартқаннан кейін сіз жаңадан толықтырылған компания туралы деректерді [Менің толықтыруларым](enrichment-hub.md) тармағында қарап шыға аласыз.</span><span class="sxs-lookup"><span data-stu-id="4778a-141">After refreshing the enrichment, you can review the newly enriched company data under [My enrichments](enrichment-hub.md).</span></span> <span data-ttu-id="4778a-142">Толықтырылған профильдер саны мен соңғы жаңарту уақытын таба аласыз.</span><span class="sxs-lookup"><span data-stu-id="4778a-142">You can find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="4778a-143">**Толықтырылған деректерді көру** параметрін таңдау арқылы әрбір толықтырылған профильдің толық көрінісіне қатынаса аласыз.</span><span class="sxs-lookup"><span data-stu-id="4778a-143">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

<span data-ttu-id="4778a-144">Қосымша ақпарат алу үшін [Leadspace API көрсеткіштері](https://support.leadspace.com/hc/en-us/sections/201997649-API) бөлімін қараңыз.</span><span class="sxs-lookup"><span data-stu-id="4778a-144">For more information, see [Leadspace APIs](https://support.leadspace.com/hc/en-us/sections/201997649-API).</span></span>

## <a name="next-steps"></a><span data-ttu-id="4778a-145">Келесі қадамдар</span><span class="sxs-lookup"><span data-stu-id="4778a-145">Next steps</span></span>

<span data-ttu-id="4778a-146">Толықтырылған тұтынушы деректерінің негізінде жасаңыз.</span><span class="sxs-lookup"><span data-stu-id="4778a-146">Build on top of your enriched customer data.</span></span> <span data-ttu-id="4778a-147">Тұтынушыларға жеке тәжірибелер ұсыну үшін [сегменттер](segments.md) мен [өлшемдер](measures.md) жасаңыз және тіпті [деректерді экспорттаңыз](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="4778a-147">Create [segments](segments.md) and [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="4778a-148">Деректердің құпиялылығы мен сәйкестігі</span><span class="sxs-lookup"><span data-stu-id="4778a-148">Data privacy and compliance</span></span>

<span data-ttu-id="4778a-149">Деректерді Leadspace платформасына жіберу үшін Dynamics 365 Customer Insights бағдарламасын қосқан кезде, Dynamics 365 Customer Insights талаптарына сәйкестік шекарасынан тыс деректерді, соның ішінде жеке деректер сияқты ықтимал құпия деректерді беруге мүмкіндік бересіз.</span><span class="sxs-lookup"><span data-stu-id="4778a-149">When you enable Dynamics 365 Customer Insights to transmit data to Leadspace, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="4778a-150">Microsoft мұндай деректерді сіздің нұсқауыңыз бойынша тасымалдайды, бірақ Leadspace платформасының кез келген құпиялылық немесе қауіпсіздік міндеттемелеріне сәйкес келуіне жауап бересіз.</span><span class="sxs-lookup"><span data-stu-id="4778a-150">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Leadspace meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="4778a-151">Қосымша ақпаратты [Microsoft құпиялық туралы мәлімдемесі](https://go.microsoft.com/fwlink/?linkid=396732) бөлімінен қараңыз.</span><span class="sxs-lookup"><span data-stu-id="4778a-151">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="4778a-152">Бұл функцияны тоқтату үшін Dynamics 365 Customer Insights әкімшісі бұл толықтыруды кез келген уақытта жоя алады.</span><span class="sxs-lookup"><span data-stu-id="4778a-152">Your Dynamics 365 Customer Insights administrator can remove this enrichment at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
