---
title: Үшінші тарап Leadspace арттыру платформасы арқылы компания профильдерін арттыру
description: Leadspace үшінші тарап арттыруы туралы жалпы ақпарат.
ms.date: 11/24/2020
ms.reviewer: kishorem
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 12eed91a7ca4ef7fde0d53cca4a1dfd398b4634f
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: kk-KZ
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269429"
---
# <a name="enrichment-of-company-profiles-with-leadspace-preview"></a><span data-ttu-id="80263-103">Leadspace (алдын ала қарау) көмегімен компания профильдерін толықтыру</span><span class="sxs-lookup"><span data-stu-id="80263-103">Enrichment of company profiles with Leadspace (preview)</span></span>

<span data-ttu-id="80263-104">Leadspace — бизнес - бизнес тұтынушы деректері платформасын қамтамасыз ететін деректер ғылымы компаниясы.</span><span class="sxs-lookup"><span data-stu-id="80263-104">Leadspace is a data science company that provides a B2B Customer Data Platform.</span></span> <span data-ttu-id="80263-105">Ол компанияларға арналған бірыңғай тұтынушы профильдері бар тұтынушыларға деректерін толықтыруына мүмкіндік береді.</span><span class="sxs-lookup"><span data-stu-id="80263-105">It enables customers with unified customer profiles for companies to enrich their data.</span></span> <span data-ttu-id="80263-106">Арттырулар компания өлшемі, орын, саласы және т.б. сияқты қосымша төлсипаттарды қамтиды.</span><span class="sxs-lookup"><span data-stu-id="80263-106">Enrichments include additional attributes such as company size, location, industry, and more.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="80263-107">Алғышарттар</span><span class="sxs-lookup"><span data-stu-id="80263-107">Prerequisites</span></span>

<span data-ttu-id="80263-108">Leadspace теңшеу үшін мына алғышарттар сақталуы қажет:</span><span class="sxs-lookup"><span data-stu-id="80263-108">To configure Leadspace, the following prerequisites must be met:</span></span>

- <span data-ttu-id="80263-109">Сізде Leadspace белсенді лицензиясы және"үздіксіз кілт" (**Leadspace таңбалауышы** деп те аталады) бар.</span><span class="sxs-lookup"><span data-stu-id="80263-109">You have an active Leadspace license and the “perpetual key” (referred to as **Leadspace token**).</span></span> <span data-ttu-id="80263-110">Өнім туралы мәліметтер үшін тікелей [Leadspace](https://www.leadspace.com/products/leadspace-on-demand/) желісіне хабарласыңыз.</span><span class="sxs-lookup"><span data-stu-id="80263-110">Contact directly [Leadspace](https://www.leadspace.com/products/leadspace-on-demand/) for details about their product.</span></span>
- <span data-ttu-id="80263-111">Сізде [әкімші](permissions.md#administrator) рұқсаттары бар.</span><span class="sxs-lookup"><span data-stu-id="80263-111">You have [Administrator](permissions.md#administrator) permissions.</span></span>
- <span data-ttu-id="80263-112">Компаниялар үшін [бірыңғай тұтынушы профильдері](customer-profiles.md) бар.</span><span class="sxs-lookup"><span data-stu-id="80263-112">You have [unified customer profiles](customer-profiles.md) for companies.</span></span>

## <a name="configuration"></a><span data-ttu-id="80263-113">Теңшелім</span><span class="sxs-lookup"><span data-stu-id="80263-113">Configuration</span></span>

1. <span data-ttu-id="80263-114">Аудитория мәліметтерінде **Деректер** > **Арттыру** тармағына өтіңіз.</span><span class="sxs-lookup"><span data-stu-id="80263-114">In audience insights, go to **Data** > **Enrichment**.</span></span>

1. <span data-ttu-id="80263-115">Leadspace тақтасынан **Менің деректерімді арттыру** параметрін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="80263-115">Select **Enrich my data** on the Leadspace tile.</span></span>

   :::image type="content" source="media/leadspace-tile.png" alt-text="Leadspace тақтасының скриншоты.":::

1. <span data-ttu-id="80263-117">**Бастау** пәрменін таңдап, содан кейін белсенді **Leadspace таңбалауышы** (үздіксіз кілт) енгізіңіз.</span><span class="sxs-lookup"><span data-stu-id="80263-117">Select **Get Started** and then enter an active **Leadspace token** (perpetual key).</span></span> <span data-ttu-id="80263-118">**Келісемін** құсбелгісін таңдау арқылы **Деректер құпиялығы мен сәйкестігі** келісімін қарап шығыңыз және қамтамасыз етіңіз.</span><span class="sxs-lookup"><span data-stu-id="80263-118">Review and provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox.</span></span> <span data-ttu-id="80263-119">**Leadspace платформасына қосылу** таңдау арқылы екі кірісті де растаңыз.</span><span class="sxs-lookup"><span data-stu-id="80263-119">Confirm both inputs by selecting **Connect to Leadspace**.</span></span>

1. <span data-ttu-id="80263-120">**Деректерді салыстыру** опциясын таңдап, Leadspace жүйесіндегі компания деректерімен арттыру қажет деректер жиынтығын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="80263-120">Select **Map data** and choose the data set you want to enrich with company data from Leadspace.</span></span> <span data-ttu-id="80263-121">Барлық тұтынушы профильдерін арттыру үшін *Тұтынушы* нысанын таңдауға болады немесе сол сегменттегі тек тұтынушы профильдерін арттыру үшін сегмент нысанын таңдауға болады.</span><span class="sxs-lookup"><span data-stu-id="80263-121">You can select the *Customer* entity to enrich all your customer profiles or select a segment entity to enrich only customer profiles contained in that segment.</span></span>

   :::image type="content" source="media/enrichment-leadspace-select-segment.png" alt-text="Тұтынушы профилі мен сегментті арттырудың бірін таңдаңыз.":::

1. <span data-ttu-id="80263-123">**Келесі** түймешігін басып, Leadspace платформасынан тиісті компания деректерін іздеу үшін бірыңғай профильдердің қай өрістерін пайдалану керектігін анықтаңыз.</span><span class="sxs-lookup"><span data-stu-id="80263-123">Click **Next** and define which fields from your unified profiles should be used to look for matching company data from Leadspace.</span></span> <span data-ttu-id="80263-124">**Компания атауы** өрісі қажет.</span><span class="sxs-lookup"><span data-stu-id="80263-124">The **Name of company** field is required.</span></span> <span data-ttu-id="80263-125">Дәлдіктің жоғары сәйкестігі үшін басқа екі өріске дейін, **Компания веб-сайты** және **Компанияның орналасқан жері** өрістерін қосуға болады.</span><span class="sxs-lookup"><span data-stu-id="80263-125">For a higher match accuracy, up to two other fields, **Company website** and **Company location**, can be added.</span></span>

   :::image type="content" source="media/enrichment-leadspace-mapping.png" alt-text="Leadspace өрісін салыстыру тақтасы.":::
   
1. <span data-ttu-id="80263-127">Өрісті салыстыруды аяқтау үшін **Қолдану** пәрменін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="80263-127">Select **Apply** to complete the field mapping.</span></span>

1. <span data-ttu-id="80263-128">Компания профильдерін толықтыру үшін **Іске қосу** параметрін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="80263-128">Select **Run** to enrich the company profiles.</span></span> <span data-ttu-id="80263-129">Арттыру қанша уақыт алатыны тұтынушылардың бірыңғай профильдерінің санына байланысты.</span><span class="sxs-lookup"><span data-stu-id="80263-129">How long an enrichment takes depends on the number of unified customer profiles.</span></span>

## <a name="enrichment-results"></a><span data-ttu-id="80263-130">Толықтыру нәтижелері</span><span class="sxs-lookup"><span data-stu-id="80263-130">Enrichment results</span></span>

<span data-ttu-id="80263-131">Толықтыруды жаңартқаннан кейін сіз жаңадан толықтырылған компания туралы деректерді [Менің толықтыруларым](enrichment-hub.md) тармағында қарап шыға аласыз.</span><span class="sxs-lookup"><span data-stu-id="80263-131">After refreshing the enrichment, you can review the newly enriched company data under [My enrichments](enrichment-hub.md).</span></span> <span data-ttu-id="80263-132">Толықтырылған профильдер саны мен соңғы жаңарту уақытын таба аласыз.</span><span class="sxs-lookup"><span data-stu-id="80263-132">You can find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="80263-133">**Толықтырылған деректерді көру** параметрін таңдау арқылы әрбір толықтырылған профильдің толық көрінісіне қатынаса аласыз.</span><span class="sxs-lookup"><span data-stu-id="80263-133">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

<span data-ttu-id="80263-134">Қосымша ақпарат алу үшін [Leadspace API көрсеткіштері](https://support.leadspace.com/hc/en-us/sections/201997649-API) бөлімін қараңыз.</span><span class="sxs-lookup"><span data-stu-id="80263-134">For more information, see [Leadspace APIs](https://support.leadspace.com/hc/en-us/sections/201997649-API).</span></span>

## <a name="next-steps"></a><span data-ttu-id="80263-135">Келесі қадамдар</span><span class="sxs-lookup"><span data-stu-id="80263-135">Next steps</span></span>

<span data-ttu-id="80263-136">Толықтырылған тұтынушы деректерінің негізінде жасаңыз.</span><span class="sxs-lookup"><span data-stu-id="80263-136">Build on top of your enriched customer data.</span></span> <span data-ttu-id="80263-137">Тұтынушыларға жекелендірілген тәжірибелерді жеткізу үшін [сегменттер](segments.md), [шаралар](measures.md) жасаңыз және [деректерді экспорттаңыз](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="80263-137">Create [segments](segments.md), [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="80263-138">Деректердің құпиялылығы мен сәйкестігі</span><span class="sxs-lookup"><span data-stu-id="80263-138">Data privacy and compliance</span></span>

<span data-ttu-id="80263-139">Деректерді Leadspace платформасына жіберу үшін Dynamics 365 Customer Insights бағдарламасын қосқан кезде, Dynamics 365 Customer Insights талаптарына сәйкестік шекарасынан тыс деректерді, соның ішінде жеке деректер сияқты ықтимал құпия деректерді беруге мүмкіндік бересіз.</span><span class="sxs-lookup"><span data-stu-id="80263-139">When you enable Dynamics 365 Customer Insights to transmit data to Leadspace, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="80263-140">Microsoft мұндай деректерді сіздің нұсқауыңыз бойынша тасымалдайды, бірақ Leadspace платформасының кез келген құпиялылық немесе қауіпсіздік міндеттемелеріне сәйкес келуіне жауап бересіз.</span><span class="sxs-lookup"><span data-stu-id="80263-140">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Leadspace meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="80263-141">Қосымша ақпаратты [Microsoft құпиялық туралы мәлімдемесі](https://go.microsoft.com/fwlink/?linkid=396732) бөлімінен қараңыз.</span><span class="sxs-lookup"><span data-stu-id="80263-141">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="80263-142">Бұл функцияны тоқтату үшін бұл арттыруды кез келген уақытта Dynamics 365 Customer Insights әкімшісі жоя алады.</span><span class="sxs-lookup"><span data-stu-id="80263-142">Your Dynamics 365 Customer Insights Administrator can remove this enrichment at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]