---
title: Үшінші тараптың арттыру HERE Technologies платформасымен арттыру
description: HERE Technologies үшінші тарап арттыруы туралы жалпы ақпарат.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: 5d1f037377010153045c9255d2d01f98ebf1fdfd
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: kk-KZ
ms.lasthandoff: 04/14/2021
ms.locfileid: "5896058"
---
# <a name="enrichment-of-customer-profiles-with-here-technologies-preview"></a><span data-ttu-id="608c7-103">Тұтынушы профильдерін HERE Technologies көмегімен арттыру (алдын ала қарау)</span><span class="sxs-lookup"><span data-stu-id="608c7-103">Enrichment of customer profiles with HERE Technologies (preview)</span></span>

<span data-ttu-id="608c7-104">HERE Technologies — орынға бағытталған деректер мен қызметтерді ұсынатын, орынды анықтауға арналған платформа компаниясы.</span><span class="sxs-lookup"><span data-stu-id="608c7-104">HERE Technologies is a location platform company that provides location-centric data and services.</span></span> <span data-ttu-id="608c7-105">HERE Technologies деректерді арттыру қызметтерінің көмегімен өз мекенжайыңызды қалыпқа келтіру, ендік пен бойлықты алу және тағы басқалар арқылы тұтынушыларыңыздың орналасуын дәлірек анықтай аласыз.</span><span class="sxs-lookup"><span data-stu-id="608c7-105">With HERE Technologies' data enrichment services, you can build a more precise location understanding of your customers with address normalization, latitude and longitude extraction, and more.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="608c7-106">Алғышарттар</span><span class="sxs-lookup"><span data-stu-id="608c7-106">Prerequisites</span></span>

<span data-ttu-id="608c7-107">HERE Technologies арттыруларын конфигурациялау үшін келесі алғышарттар орындалуы керек:</span><span class="sxs-lookup"><span data-stu-id="608c7-107">To configure HERE Technologies enrichments, the following prerequisites must be met:</span></span>

- <span data-ttu-id="608c7-108">Сізде белсенді HERE Technologies жазылымы болуы қажет.</span><span class="sxs-lookup"><span data-stu-id="608c7-108">You have an active HERE Technologies subscription.</span></span> <span data-ttu-id="608c7-109">Жазылым алу үшін [осы жерде тіркелуге](https://developer.here.com/sign-up?utm_medium=referral&utm_source=Microsoft-Dynamics-CI&create=Freemium-Basic) немесе тікелей [HERE Technologies компаниясына хабарласуға](https://developer.here.com/help?utm_medium=referral&utm_source=Microsoft-Dynamics-CI#how-can-we-help-you) болады.</span><span class="sxs-lookup"><span data-stu-id="608c7-109">To get a subscription, you can [sign-up here](https://developer.here.com/sign-up?utm_medium=referral&utm_source=Microsoft-Dynamics-CI&create=Freemium-Basic) or [contact HERE Technologies](https://developer.here.com/help?utm_medium=referral&utm_source=Microsoft-Dynamics-CI#how-can-we-help-you) directly.</span></span> [<span data-ttu-id="608c7-110">HERE Technologies орынды арттыру туралы қосымша ақпарат.</span><span class="sxs-lookup"><span data-stu-id="608c7-110">Learn more about HERE Technologies Location Enrichment.</span></span>](https://developer.here.com/location-enrichment?cid=Dev-MicrosoftDynamics-DB-0-Dev-&utm_source=MicrosoftDynamics&utm_medium=referral&utm_campaign=Online_Dev_ReferralMicrosoft)

- <span data-ttu-id="608c7-111">Мұнда HERE [қосылымы](connections.md) қолжетімді *немесе* сізде [әкімші](permissions.md#administrator) рұқсаттары және HERE Technologies API кілті бар.</span><span class="sxs-lookup"><span data-stu-id="608c7-111">There is a HERE [connection](connections.md) available *or* you have [administrator](permissions.md#administrator) permissions and the HERE Technologies API key.</span></span>

## <a name="configure-the-enrichment"></a><span data-ttu-id="608c7-112">Жақсартуды конфигурациялау</span><span class="sxs-lookup"><span data-stu-id="608c7-112">Configure the enrichment</span></span>

1. <span data-ttu-id="608c7-113">**Деректер** > **Толықтыру** тармағына өтіңіз.</span><span class="sxs-lookup"><span data-stu-id="608c7-113">Go to **Data** > **Enrichment**.</span></span> 

1. <span data-ttu-id="608c7-114">HERE Technologies тақтасында **Менің деректерімді жақсарту** параметрін таңдаңыз және **Жұмысты бастау** түймешігін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="608c7-114">Select **Enrich my data** on the HERE Technologies tile and select **Get started**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="608c7-115">![HERE Technologies тақтасы](media/HERE-tile.png "HERE Technologies тақтасы")</span><span class="sxs-lookup"><span data-stu-id="608c7-115">![HERE Technologies tile](media/HERE-tile.png "HERE Technologies tile")</span></span>

1. <span data-ttu-id="608c7-116">Ашылмалы тізімнен [қосылымды](connections.md) таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="608c7-116">Select a [connection](connections.md) from the drop-down.</span></span> <span data-ttu-id="608c7-117">Егер қосылым болмаса, әкімшіге хабарласыңыз.</span><span class="sxs-lookup"><span data-stu-id="608c7-117">Contact  an administrator if no connection is available.</span></span> <span data-ttu-id="608c7-118">Егер сіз әкімші болсаңыз, **Қосылым қосу** түймешігін таңдау арқылы қосылым жасай аласыз.</span><span class="sxs-lookup"><span data-stu-id="608c7-118">If you are an administrator, you can create a connection by selecting **Add connection**.</span></span> <span data-ttu-id="608c7-119">Ашылмалы тізімнен **HERE Technologies** параметрін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="608c7-119">Choose **HERE Technologies** from the drop-down.</span></span> 

1. <span data-ttu-id="608c7-120">Таңдауды растау үшін **HERE Technologies қосылымына қосылу** түймешігін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="608c7-120">Select **Connect to HERE Technologies** to confirm the selection.</span></span>

1.  <span data-ttu-id="608c7-121">**Келесі** түймешігін таңдаңыз және HERE Technologies қызметіндегі орын деректермен жақсарту керек **Тұтынушы деректерінің жиынтығы** параметрін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="608c7-121">Select **Next** and choose the **Customer data set** you want to enrich with location data from HERE Technologies.</span></span> <span data-ttu-id="608c7-122">Барлық тұтынушы профильдерін арттыру үшін **Тұтынушы** нысанын таңдауға болады немесе сол сегменттегі тек тұтынушы профильдерін арттыру үшін сегмент нысанын таңдауға болады.</span><span class="sxs-lookup"><span data-stu-id="608c7-122">You can select the **Customer** entity to enrich all your customer profiles or select a segment entity to enrich only customer profiles contained in that segment.</span></span>

    :::image type="content" source="media/enrichment-HERE-configuration-customer-data-set.png" alt-text="Тұтынушының деректер жиынтығын таңдау кезіндегі скриншот.":::

1. <span data-ttu-id="608c7-124">Өрістерді негізгі және/немесе қосымша мекенжаймен салыстырғыңыз келетінін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="608c7-124">Choose if you want to map fields to the primary and/or secondary address.</span></span> <span data-ttu-id="608c7-125">Сіз екі мекенжай үшін өріс картасын көрсете аласыз және екі мекенжайдың профильдерін бөлек жақсарта аласыз.</span><span class="sxs-lookup"><span data-stu-id="608c7-125">You can specify a field mapping for both addresses and enrich the profiles for both addresses separately.</span></span> <span data-ttu-id="608c7-126">Мысалы, егер үй және бизнес мекенжайы болса.</span><span class="sxs-lookup"><span data-stu-id="608c7-126">For example, if there's a home and a business address.</span></span> <span data-ttu-id="608c7-127">**Келесі** пәрменін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="608c7-127">Select **Next**.</span></span>

1. <span data-ttu-id="608c7-128">HERE Technologies платформасынан тиісті орын деректерін іздеу үшін бірыңғай профильдердің қай өрістерін пайдалану керектігін анықтаңыз.</span><span class="sxs-lookup"><span data-stu-id="608c7-128">Define which fields from your unified profiles should be used to look for matching location data from HERE Technologies.</span></span> <span data-ttu-id="608c7-129">**1-көше** және **Пошта индексі** өрістері таңдалған негізгі және/немесе қосымша мекенжай үшін қажет.</span><span class="sxs-lookup"><span data-stu-id="608c7-129">The **Street 1** and **Zip/Postal Code** fields are required for the selected primary and/or secondary address.</span></span> <span data-ttu-id="608c7-130">Сәйкестіктің жоғары дәлдігі үшін қосымша өрістер қосуға болады.</span><span class="sxs-lookup"><span data-stu-id="608c7-130">For a higher match accuracy, more fields can be added.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="608c7-131">![HERE Technologies арттыру конфигурациясының беті](media/enrichment-HERE-configuration.png "HERE Technologies арттыру конфигурациясының беті")</span><span class="sxs-lookup"><span data-stu-id="608c7-131">![HERE Technologies enrichment configuration page](media/enrichment-HERE-configuration.png "HERE Technologies enrichment configuration page")</span></span>

1. <span data-ttu-id="608c7-132">Өрістерді салыстыруды аяқтау үшін **Келесі** түймешігін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="608c7-132">Select **Next** to complete the field mapping.</span></span>

1. <span data-ttu-id="608c7-133">Жақсартуға атау беріңіз.</span><span class="sxs-lookup"><span data-stu-id="608c7-133">Provide a name for the enrichment.</span></span> 

<span data-ttu-id="608c7-134">1. Таңдауларды қарап шыққаннан кейін **Жақсартуды сақтау** түймешігін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="608c7-134">1.Select **Save enrichment** after reviewing your choices.</span></span>

## <a name="configure-the-connection-for-here-technologies"></a><span data-ttu-id="608c7-135">HERE technologies үшін қосылымды конфигурациялау</span><span class="sxs-lookup"><span data-stu-id="608c7-135">Configure the connection for HERE technologies</span></span> 

<span data-ttu-id="608c7-136">Қосылымдарды конфигурациялау үшін сіз әкімші болуыңыз керек.</span><span class="sxs-lookup"><span data-stu-id="608c7-136">You need to be an administrator to configure connections.</span></span> <span data-ttu-id="608c7-137">Жақсартуды конфигурациялау кезінде **Қосылым қосу** түймешігін таңдаңыз *немесе* **Әкімші** > **Қосылымдар** тармағына өтіңіз және HERE technologies тақтасында **Орнату** түймешігін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="608c7-137">Select **Add connection** when configuring an enrichment *or* go to **Admin** > **Connections** and select **Set up** on the HERE Technologies tile.</span></span>

1. <span data-ttu-id="608c7-138">Қосылым атауын **Көрсетілетін атауы** терезесіне енгізіңіз.</span><span class="sxs-lookup"><span data-stu-id="608c7-138">Enter a name for the connection in the **Display name** box.</span></span>

1. <span data-ttu-id="608c7-139">Жарамды HERE Technologies API кілтін беріңіз.</span><span class="sxs-lookup"><span data-stu-id="608c7-139">Provide a valid HERE Technologies API key.</span></span>

1. <span data-ttu-id="608c7-140">**Келісемін** құсбелгісін таңдау арқылы **Деректер құпиялығы мен сәйкестігі** келісімін қарап шығыңыз және қамтамасыз етіңіз</span><span class="sxs-lookup"><span data-stu-id="608c7-140">Review and provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox</span></span>

1. <span data-ttu-id="608c7-141">Конфигурацияны тексеру үшін **Тексеру** түймешігін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="608c7-141">Select **Verify** to validate the configuration.</span></span>

1. <span data-ttu-id="608c7-142">Тексеруді аяқтағаннан кейін **Сақтау** түймешігін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="608c7-142">After completing the verification, select **Save**.</span></span>

> [!div class="mx-imgBorder"]
   > <span data-ttu-id="608c7-143">![HERE technologies қосылымын конфигурациялау беті](media/enrichment-HERE-connection.png "HERE technologies қосылымын конфигурациялау беті")</span><span class="sxs-lookup"><span data-stu-id="608c7-143">![HERE Technologies connection configuration page](media/enrichment-HERE-connection.png "HERE Technologies connection configuration page")</span></span>

## <a name="enrichment-results"></a><span data-ttu-id="608c7-144">Толықтыру нәтижелері</span><span class="sxs-lookup"><span data-stu-id="608c7-144">Enrichment results</span></span>

<span data-ttu-id="608c7-145">Арттыру процесін бастау үшін пәрмендер жолағынан **Іске қосу** пәрменін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="608c7-145">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="608c7-146">Сондай-ақ, жүйеге [жоспарланған жаңарту](system.md#schedule-tab) бөлігі ретінде арттыруды автоматты түрде іске қосуына мүмкіндік беруге болады.</span><span class="sxs-lookup"><span data-stu-id="608c7-146">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="608c7-147">Өңдеу уақыты тұтынушы деректерінің көлеміне және HERE Technologies платформасындағы API жауап беру уақытына байланысты болады.</span><span class="sxs-lookup"><span data-stu-id="608c7-147">The processing time will depend on the size of your customer data and the API response times from HERE Technologies.</span></span>

<span data-ttu-id="608c7-148">Арттыру процесі аяқталғаннан кейін, жаңа арттырылған тұтынушы профильдерінің деректерін **Менің арттыруларым** астынан қарап шығуға болады.</span><span class="sxs-lookup"><span data-stu-id="608c7-148">After the enrichment process completes, you can review the newly enriched customer profiles data under **My enrichments**.</span></span> <span data-ttu-id="608c7-149">Сонымен қатар, соңғы жаңартудың уақыты мен арттырылған профильдер санын таба аласыз.</span><span class="sxs-lookup"><span data-stu-id="608c7-149">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="608c7-150">**Толықтырылған деректерді көру** параметрін таңдау арқылы әрбір толықтырылған профильдің толық көрінісіне қатынаса аласыз.</span><span class="sxs-lookup"><span data-stu-id="608c7-150">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="608c7-151">Келесі қадамдар</span><span class="sxs-lookup"><span data-stu-id="608c7-151">Next steps</span></span>

<span data-ttu-id="608c7-152">Толықтырылған тұтынушы деректерінің негізінде жасаңыз.</span><span class="sxs-lookup"><span data-stu-id="608c7-152">Build on top of your enriched customer data.</span></span> <span data-ttu-id="608c7-153">Тұтынушыларға жекелендірілген тәжірибелерді жеткізу үшін [сегменттер](segments.md), [шаралар](measures.md) жасаңыз және [деректерді экспорттаңыз](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="608c7-153">Create [segments](segments.md), [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="608c7-154">Деректердің құпиялылығы мен сәйкестігі</span><span class="sxs-lookup"><span data-stu-id="608c7-154">Data privacy and compliance</span></span>

<span data-ttu-id="608c7-155">Деректерді HERE Technologies платформасына жіберу үшін Dynamics 365 Customer Insights бағдарламасын қосқан кезде, Dynamics 365 Customer Insights талаптарына сәйкестік шекарасынан тыс деректерді, соның ішінде жеке деректер сияқты ықтимал құпия деректерді беруге мүмкіндік бересіз.</span><span class="sxs-lookup"><span data-stu-id="608c7-155">When you enable Dynamics 365 Customer Insights to transmit data to HERE Technologies, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="608c7-156">Microsoft мұндай деректерді сіздің нұсқауыңыз бойынша тасымалдайды, бірақ HERE Technologies платформасының кез келген құпиялылық немесе қауіпсіздік міндеттемелеріне сәйкес келуіне жауап бересіз.</span><span class="sxs-lookup"><span data-stu-id="608c7-156">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that HERE Technologies meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="608c7-157">Қосымша ақпаратты [Microsoft құпиялық туралы мәлімдемесі](https://go.microsoft.com/fwlink/?linkid=396732) бөлімінен қараңыз.</span><span class="sxs-lookup"><span data-stu-id="608c7-157">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="608c7-158">Бұл функцияны тоқтату үшін бұл арттыруды кез келген уақытта Dynamics 365 Customer Insights әкімшісі жоя алады.</span><span class="sxs-lookup"><span data-stu-id="608c7-158">Your Dynamics 365 Customer Insights Administrator can remove this enrichment at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
