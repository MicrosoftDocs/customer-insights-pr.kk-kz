---
title: Үшінші тараптың арттыру HERE Technologies платформасымен арттыру
description: HERE Technologies үшінші тарап арттыруы туралы жалпы ақпарат.
ms.date: 12/10/2020
ms.reviewer: jodahl
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 258e37de9d9685d9ebc30b3c6b8d238d583431b4
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: kk-KZ
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269521"
---
# <a name="enrichment-of-customer-profiles-with-here-technologies-preview"></a><span data-ttu-id="aead6-103">Тұтынушы профильдерін HERE Technologies көмегімен арттыру (алдын ала қарау)</span><span class="sxs-lookup"><span data-stu-id="aead6-103">Enrichment of customer profiles with HERE Technologies (preview)</span></span>

<span data-ttu-id="aead6-104">HERE Technologies — орынға бағытталған деректер мен қызметтерді ұсынатын, орынды анықтауға арналған платформа компаниясы.</span><span class="sxs-lookup"><span data-stu-id="aead6-104">HERE Technologies is a location platform company that provides location-centric data and services.</span></span> <span data-ttu-id="aead6-105">HERE Technologies деректерді арттыру қызметтерінің көмегімен өз мекенжайыңызды қалыпқа келтіру, ендік пен бойлықты алу және тағы басқалар арқылы тұтынушыларыңыздың орналасуын дәлірек анықтай аласыз.</span><span class="sxs-lookup"><span data-stu-id="aead6-105">With HERE Technologies' data enrichment services, you can build a more precise location understanding of your customers with address normalization, latitude and longitude extraction, and more.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="aead6-106">Алғышарттар</span><span class="sxs-lookup"><span data-stu-id="aead6-106">Prerequisites</span></span>

<span data-ttu-id="aead6-107">HERE Technologies арттыруларын конфигурациялау үшін келесі алғышарттар орындалуы керек:</span><span class="sxs-lookup"><span data-stu-id="aead6-107">To configure HERE Technologies enrichments, the following prerequisites must be met:</span></span>

- <span data-ttu-id="aead6-108">Сізде белсенді HERE Technologies жазылымы болуы қажет.</span><span class="sxs-lookup"><span data-stu-id="aead6-108">You have an active HERE Technologies subscription.</span></span> <span data-ttu-id="aead6-109">Жазылым алу үшін [осы жерде тіркелуге](https://developer.here.com/sign-up?utm_medium=referral&utm_source=Microsoft-Dynamics-CI&create=Freemium-Basic) немесе тікелей [HERE Technologies компаниясына хабарласуға](https://developer.here.com/help?utm_medium=referral&utm_source=Microsoft-Dynamics-CI#how-can-we-help-you) болады.</span><span class="sxs-lookup"><span data-stu-id="aead6-109">To get a subscription, you can [sign-up here](https://developer.here.com/sign-up?utm_medium=referral&utm_source=Microsoft-Dynamics-CI&create=Freemium-Basic) or [contact HERE Technologies](https://developer.here.com/help?utm_medium=referral&utm_source=Microsoft-Dynamics-CI#how-can-we-help-you) directly.</span></span> [<span data-ttu-id="aead6-110">HERE Technologies орынды арттыру туралы қосымша ақпарат.</span><span class="sxs-lookup"><span data-stu-id="aead6-110">Learn more about HERE Technologies Location Enrichment.</span></span>](https://developer.here.com/location-enrichment?cid=Dev-MicrosoftDynamics-DB-0-Dev-&utm_source=MicrosoftDynamics&utm_medium=referral&utm_campaign=Online_Dev_ReferralMicrosoft)

- <span data-ttu-id="aead6-111">Сізде HERE Technologies API кілті бар.</span><span class="sxs-lookup"><span data-stu-id="aead6-111">You have the HERE Technologies API key.</span></span>

- <span data-ttu-id="aead6-112">Сізде [әкімші](permissions.md#administrator) рұқсаттары бар.</span><span class="sxs-lookup"><span data-stu-id="aead6-112">You have [Administrator](permissions.md#administrator) permissions.</span></span>

## <a name="configuration"></a><span data-ttu-id="aead6-113">Теңшелім</span><span class="sxs-lookup"><span data-stu-id="aead6-113">Configuration</span></span>

1. <span data-ttu-id="aead6-114">**Деректер** > **Толықтыру** тармағына өтіңіз.</span><span class="sxs-lookup"><span data-stu-id="aead6-114">Go to **Data** > **Enrichment**.</span></span>

1. <span data-ttu-id="aead6-115">HERE Technologies тақтасында **Менің деректерімді арттыру** пәрменін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="aead6-115">Select **Enrich my data** on the HERE Technologies tile.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="aead6-116">![HERE Technologies тақтасы](media/HERE-tile.png "HERE Technologies тақтасы")</span><span class="sxs-lookup"><span data-stu-id="aead6-116">![HERE Technologies tile](media/HERE-tile.png "HERE Technologies tile")</span></span>

1. <span data-ttu-id="aead6-117">Белсенді **HERE Technologies API кілтін** енгізіңіз.</span><span class="sxs-lookup"><span data-stu-id="aead6-117">Enter an active **HERE Technologies API key**.</span></span> <span data-ttu-id="aead6-118">**Келісемін** құсбелгісін таңдау арқылы **Деректер құпиялығы мен сәйкестігі** келісімін қарап шығыңыз және қамтамасыз етіңіз.</span><span class="sxs-lookup"><span data-stu-id="aead6-118">Review and provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox.</span></span> 

1. <span data-ttu-id="aead6-119">**HERE платформасына қосылу** таңдау арқылы екі кірісті де растаңыз.</span><span class="sxs-lookup"><span data-stu-id="aead6-119">Confirm both inputs by selecting **Connect to HERE**.</span></span>

1.  <span data-ttu-id="aead6-120">**Деректерді қосу** опциясын таңдап, HERE Technologies жүйесіндегі орын деректерімен арттыру қажет **Тұтынушы деректерінің жиынтығын** таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="aead6-120">Select **Add data** and choose the **Customer data set** you want to enrich with location data from HERE Technologies.</span></span> <span data-ttu-id="aead6-121">Барлық тұтынушы профильдерін арттыру үшін **Тұтынушы** нысанын таңдауға болады немесе сол сегменттегі тек тұтынушы профильдерін арттыру үшін сегмент нысанын таңдауға болады.</span><span class="sxs-lookup"><span data-stu-id="aead6-121">You can select the **Customer** entity to enrich all your customer profiles or select a segment entity to enrich only customer profiles contained in that segment.</span></span>

    :::image type="content" source="media/enrichment-HERE-configuration-customer-data-set.png" alt-text="Тұтынушының деректер жиынтығын таңдау кезіндегі скриншот.":::

1. <span data-ttu-id="aead6-123">Өрістерді негізгі және/немесе қосымша мекенжаймен салыстырғыңыз келетінін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="aead6-123">Choose if you want to map fields to the primary and/or secondary address.</span></span> <span data-ttu-id="aead6-124">Екі мекенжай үшін өріс салыстырмасын көрсетуге (мысалы, үй және бизнес мекенжайы) және екі мекенжайдың профильдерін бөлек арттыруға аласыз.</span><span class="sxs-lookup"><span data-stu-id="aead6-124">You can specify a field mapping for both addresses (for example, a home and a business address) and enrich the profiles for both addresses separately.</span></span> <span data-ttu-id="aead6-125">**Келесі** пәрменін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="aead6-125">Select **Next**.</span></span>

1. <span data-ttu-id="aead6-126">HERE Technologies платформасынан тиісті орын деректерін іздеу үшін бірыңғай профильдердің қай өрістерін пайдалану керектігін анықтаңыз.</span><span class="sxs-lookup"><span data-stu-id="aead6-126">Define which fields from your unified profiles should be used to look for matching location data from HERE Technologies.</span></span> <span data-ttu-id="aead6-127">**1-көше** және **Пошта индексі** өрістері таңдалған негізгі және/немесе қосымша мекенжай үшін қажет.</span><span class="sxs-lookup"><span data-stu-id="aead6-127">The **Street 1** and **Zip/Postal Code** fields are required for the selected primary and/or secondary address.</span></span> <span data-ttu-id="aead6-128">Сәйкестіктің жоғары дәлдігі үшін қосымша өрістер қосуға болады.</span><span class="sxs-lookup"><span data-stu-id="aead6-128">For a higher match accuracy, more fields can be added.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="aead6-129">![HERE Technologies арттыру конфигурациясының беті](media/enrichment-HERE-configuration.png "HERE Technologies арттыру конфигурациясының беті")</span><span class="sxs-lookup"><span data-stu-id="aead6-129">![HERE Technologies enrichment configuration page](media/enrichment-HERE-configuration.png "HERE Technologies enrichment configuration page")</span></span>

1. <span data-ttu-id="aead6-130">Өрісті салыстыруды аяқтау үшін **Қолдану** пәрменін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="aead6-130">Select **Apply** to complete the field mapping.</span></span>

## <a name="enrichment-results"></a><span data-ttu-id="aead6-131">Толықтыру нәтижелері</span><span class="sxs-lookup"><span data-stu-id="aead6-131">Enrichment results</span></span>

<span data-ttu-id="aead6-132">Арттыру процесін бастау үшін пәрмендер жолағынан **Іске қосу** пәрменін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="aead6-132">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="aead6-133">Сондай-ақ, жүйеге [жоспарланған жаңарту](system.md#schedule-tab) бөлігі ретінде арттыруды автоматты түрде іске қосуына мүмкіндік беруге болады.</span><span class="sxs-lookup"><span data-stu-id="aead6-133">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="aead6-134">Өңдеу уақыты тұтынушы деректерінің көлеміне және HERE Technologies платформасындағы API жауап беру уақытына байланысты болады.</span><span class="sxs-lookup"><span data-stu-id="aead6-134">The processing time will depend on the size of your customer data and the API response times from HERE Technologies.</span></span>

<span data-ttu-id="aead6-135">Арттыру процесі аяқталғаннан кейін, жаңа арттырылған тұтынушы профильдерінің деректерін **Менің арттыруларым** астынан қарап шығуға болады.</span><span class="sxs-lookup"><span data-stu-id="aead6-135">After the enrichment process completes, you can review the newly enriched customer profiles data under **My enrichments**.</span></span> <span data-ttu-id="aead6-136">Сонымен қатар, соңғы жаңартудың уақыты мен арттырылған профильдер санын таба аласыз.</span><span class="sxs-lookup"><span data-stu-id="aead6-136">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="aead6-137">**Толықтырылған деректерді көру** параметрін таңдау арқылы әрбір толықтырылған профильдің толық көрінісіне қатынаса аласыз.</span><span class="sxs-lookup"><span data-stu-id="aead6-137">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="aead6-138">Келесі қадамдар</span><span class="sxs-lookup"><span data-stu-id="aead6-138">Next steps</span></span>

<span data-ttu-id="aead6-139">Толықтырылған тұтынушы деректерінің негізінде жасаңыз.</span><span class="sxs-lookup"><span data-stu-id="aead6-139">Build on top of your enriched customer data.</span></span> <span data-ttu-id="aead6-140">Тұтынушыларға жекелендірілген тәжірибелерді жеткізу үшін [сегменттер](segments.md), [шаралар](measures.md) жасаңыз және [деректерді экспорттаңыз](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="aead6-140">Create [segments](segments.md), [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="aead6-141">Деректердің құпиялылығы мен сәйкестігі</span><span class="sxs-lookup"><span data-stu-id="aead6-141">Data privacy and compliance</span></span>

<span data-ttu-id="aead6-142">Деректерді HERE Technologies платформасына жіберу үшін Dynamics 365 Customer Insights бағдарламасын қосқан кезде, Dynamics 365 Customer Insights талаптарына сәйкестік шекарасынан тыс деректерді, соның ішінде жеке деректер сияқты ықтимал құпия деректерді беруге мүмкіндік бересіз.</span><span class="sxs-lookup"><span data-stu-id="aead6-142">When you enable Dynamics 365 Customer Insights to transmit data to HERE Technologies, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="aead6-143">Microsoft мұндай деректерді сіздің нұсқауыңыз бойынша тасымалдайды, бірақ HERE Technologies платформасының кез келген құпиялылық немесе қауіпсіздік міндеттемелеріне сәйкес келуіне жауап бересіз.</span><span class="sxs-lookup"><span data-stu-id="aead6-143">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that HERE Technologies meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="aead6-144">Қосымша ақпаратты [Microsoft құпиялық туралы мәлімдемесі](https://go.microsoft.com/fwlink/?linkid=396732) бөлімінен қараңыз.</span><span class="sxs-lookup"><span data-stu-id="aead6-144">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="aead6-145">Бұл функцияны тоқтату үшін бұл арттыруды кез келген уақытта Dynamics 365 Customer Insights әкімшісі жоя алады.</span><span class="sxs-lookup"><span data-stu-id="aead6-145">Your Dynamics 365 Customer Insights Administrator can remove this enrichment at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]