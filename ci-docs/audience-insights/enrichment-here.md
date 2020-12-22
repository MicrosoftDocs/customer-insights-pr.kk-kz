---
title: Үшінші тараптың арттыру HERE Technologies платформасымен арттыру
description: HERE Technologies үшінші тарап арттыруы туралы жалпы ақпарат.
ms.date: 10/27/2020
ms.reviewer: jodahl
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 7082fcfec099c3c9436b233c193be23625f6691a
ms.sourcegitcommit: a9b2cf598f256d07a48bba8617347ee90024a1dd
ms.translationtype: HT
ms.contentlocale: kk-KZ
ms.lasthandoff: 12/03/2020
ms.locfileid: "4668685"
---
# <a name="enrichment-of-customer-profiles-with-here-technologies-preview"></a><span data-ttu-id="50476-103">Тұтынушы профильдерін HERE Technologies көмегімен арттыру (алдын ала қарау)</span><span class="sxs-lookup"><span data-stu-id="50476-103">Enrichment of customer profiles with HERE Technologies (preview)</span></span>

<span data-ttu-id="50476-104">HERE Technologies — орынға бағытталған деректер мен қызметтерді ұсынатын, орынды анықтауға арналған платформа компаниясы.</span><span class="sxs-lookup"><span data-stu-id="50476-104">HERE Technologies is a location platform company that provides location-centric data and services.</span></span> <span data-ttu-id="50476-105">HERE Technologies деректерді арттыру қызметтерінің көмегімен өз мекенжайыңызды қалыпқа келтіру, ендік пен бойлықты алу және тағы басқалар арқылы тұтынушыларыңыздың орналасуын дәлірек анықтай аласыз.</span><span class="sxs-lookup"><span data-stu-id="50476-105">With HERE Technologies' data enrichment services, you can build a more precise location understanding of your customers with address normalization, latitude and longitude extraction, and more.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="50476-106">Алғышарттар</span><span class="sxs-lookup"><span data-stu-id="50476-106">Prerequisites</span></span>

<span data-ttu-id="50476-107">HERE Technologies арттыруларын конфигурациялау үшін келесі алғышарттар орындалуы керек:</span><span class="sxs-lookup"><span data-stu-id="50476-107">To configure HERE Technologies enrichments, the following prerequisites must be met:</span></span>

- <span data-ttu-id="50476-108">Сізде белсенді HERE Technologies жазылымы болуы қажет.</span><span class="sxs-lookup"><span data-stu-id="50476-108">You have an active HERE Technologies subscription.</span></span> <span data-ttu-id="50476-109">Жазылым алу үшін [осы жерде тіркелуге](https://developer.here.com/sign-up?utm_medium=referral&utm_source=Microsoft-Dynamics-CI&create=Freemium-Basic) немесе тікелей [HERE Technologies компаниясына хабарласуға](https://developer.here.com/help?utm_medium=referral&utm_source=Microsoft-Dynamics-CI#how-can-we-help-you) болады.</span><span class="sxs-lookup"><span data-stu-id="50476-109">To get a subscription, you can [sign-up here](https://developer.here.com/sign-up?utm_medium=referral&utm_source=Microsoft-Dynamics-CI&create=Freemium-Basic) or [contact HERE Technologies](https://developer.here.com/help?utm_medium=referral&utm_source=Microsoft-Dynamics-CI#how-can-we-help-you) directly.</span></span> [<span data-ttu-id="50476-110">HERE Technologies орынды арттыру туралы қосымша ақпарат.</span><span class="sxs-lookup"><span data-stu-id="50476-110">Learn more about HERE Technologies Location Enrichment.</span></span>](https://developer.here.com/location-enrichment?cid=Dev-MicrosoftDynamics-DB-0-Dev-&utm_source=MicrosoftDynamics&utm_medium=referral&utm_campaign=Online_Dev_ReferralMicrosoft)

- <span data-ttu-id="50476-111">Сізде HERE Technologies API кілті бар.</span><span class="sxs-lookup"><span data-stu-id="50476-111">You have the HERE Technologies API key.</span></span>

- <span data-ttu-id="50476-112">Сізде [әкімші](permissions.md#administrator) рұқсаттары бар.</span><span class="sxs-lookup"><span data-stu-id="50476-112">You have [Administrator](permissions.md#administrator) permissions.</span></span>

## <a name="configuration"></a><span data-ttu-id="50476-113">Теңшелім</span><span class="sxs-lookup"><span data-stu-id="50476-113">Configuration</span></span>

1. <span data-ttu-id="50476-114">**Деректер** > **Толықтыру** тармағына өтіңіз.</span><span class="sxs-lookup"><span data-stu-id="50476-114">Go to **Data** > **Enrichment**.</span></span>

1. <span data-ttu-id="50476-115">HERE Technologies тақтасында **Менің деректерімді арттыру** пәрменін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="50476-115">Select **Enrich my data** on the HERE Technologies tile.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="50476-116">![HERE Technologies тақтасы](media/HERE-tile.png "HERE Technologies тақтасы")</span><span class="sxs-lookup"><span data-stu-id="50476-116">![HERE Technologies tile](media/HERE-tile.png "HERE Technologies tile")</span></span>

1. <span data-ttu-id="50476-117">Белсенді **HERE Technologies API кілтін** енгізіңіз.</span><span class="sxs-lookup"><span data-stu-id="50476-117">Enter an active **HERE Technologies API key**.</span></span> <span data-ttu-id="50476-118">**Келісемін** құсбелгісін таңдау арқылы **Деректер құпиялығы мен сәйкестігі** келісімін қарап шығыңыз және қамтамасыз етіңіз.</span><span class="sxs-lookup"><span data-stu-id="50476-118">Review and provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox.</span></span> 

1. <span data-ttu-id="50476-119">**HERE платформасына қосылу** таңдау арқылы екі кірісті де растаңыз.</span><span class="sxs-lookup"><span data-stu-id="50476-119">Confirm both inputs by selecting **Connect to HERE**.</span></span>

1. <span data-ttu-id="50476-120">**Деректер қосу** пәрменін таңдап, өрістерді негізгі және/немесе қосымша мекенжаймен салыстырғыңыз келетінін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="50476-120">Select **Add data** and choose if you want to map fields to the primary and/or secondary address.</span></span> <span data-ttu-id="50476-121">Екі мекенжай үшін өріс салыстырмасын көрсетуге (мысалы, үй және бизнес мекенжайы) және екі мекенжайдың профильдерін бөлек арттыруға аласыз.</span><span class="sxs-lookup"><span data-stu-id="50476-121">You can specify a field mapping for both addresses (for example, a home and a business address) and enrich the profiles for both addresses separately.</span></span> <span data-ttu-id="50476-122">**Келесі** пәрменін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="50476-122">Select **Next**.</span></span>

1. <span data-ttu-id="50476-123">HERE Technologies платформасынан тиісті орын деректерін іздеу үшін бірыңғай профильдердің қай өрістерін пайдалану керектігін анықтаңыз.</span><span class="sxs-lookup"><span data-stu-id="50476-123">Define which fields from your unified profiles should be used to look for matching location data from HERE Technologies.</span></span> <span data-ttu-id="50476-124">**1-көше** және **Пошта индексі** өрістері таңдалған негізгі және/немесе қосымша мекенжай үшін қажет.</span><span class="sxs-lookup"><span data-stu-id="50476-124">The **Street 1** and **Zip/Postal Code** fields are required for the selected primary and/or secondary address.</span></span> <span data-ttu-id="50476-125">Сәйкестіктің жоғары дәлдігі үшін қосымша өрістер қосуға болады.</span><span class="sxs-lookup"><span data-stu-id="50476-125">For a higher match accuracy, more fields can be added.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="50476-126">![HERE Technologies арттыру конфигурациясының беті](media/enrichment-HERE-configuration.png "HERE Technologies арттыру конфигурациясының беті")</span><span class="sxs-lookup"><span data-stu-id="50476-126">![HERE Technologies enrichment configuration page](media/enrichment-HERE-configuration.png "HERE Technologies enrichment configuration page")</span></span>

1. <span data-ttu-id="50476-127">Өрісті салыстыруды аяқтау үшін **Қолдану** пәрменін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="50476-127">Select **Apply** to complete the field mapping.</span></span>

## <a name="enrichment-results"></a><span data-ttu-id="50476-128">Толықтыру нәтижелері</span><span class="sxs-lookup"><span data-stu-id="50476-128">Enrichment results</span></span>

<span data-ttu-id="50476-129">Арттыру процесін бастау үшін пәрмендер жолағынан **Іске қосу** пәрменін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="50476-129">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="50476-130">Сондай-ақ, жүйеге [жоспарланған жаңарту](system.md#schedule-tab) бөлігі ретінде арттыруды автоматты түрде іске қосуына мүмкіндік беруге болады.</span><span class="sxs-lookup"><span data-stu-id="50476-130">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="50476-131">Өңдеу уақыты тұтынушы деректерінің көлеміне және HERE Technologies платформасындағы API жауап беру уақытына байланысты болады.</span><span class="sxs-lookup"><span data-stu-id="50476-131">The processing time will depend on the size of your customer data and the API response times from HERE Technologies.</span></span>

<span data-ttu-id="50476-132">Арттыру процесі аяқталғаннан кейін, жаңа арттырылған тұтынушы профильдерінің деректерін **Менің арттыруларым** астынан қарап шығуға болады.</span><span class="sxs-lookup"><span data-stu-id="50476-132">After the enrichment process completes, you can review the newly enriched customer profiles data under **My enrichments**.</span></span> <span data-ttu-id="50476-133">Сонымен қатар, соңғы жаңартудың уақыты мен арттырылған профильдер санын таба аласыз.</span><span class="sxs-lookup"><span data-stu-id="50476-133">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="50476-134">**Толықтырылған деректерді көру** параметрін таңдау арқылы әрбір толықтырылған профильдің толық көрінісіне қатынаса аласыз.</span><span class="sxs-lookup"><span data-stu-id="50476-134">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="50476-135">Келесі қадамдар</span><span class="sxs-lookup"><span data-stu-id="50476-135">Next steps</span></span>

<span data-ttu-id="50476-136">Толықтырылған тұтынушы деректерінің негізінде жасаңыз.</span><span class="sxs-lookup"><span data-stu-id="50476-136">Build on top of your enriched customer data.</span></span> <span data-ttu-id="50476-137">Тұтынушыларға жекелендірілген тәжірибелерді жеткізу үшін [сегменттер](segments.md), [шаралар](measures.md) жасаңыз және [деректерді экспорттаңыз](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="50476-137">Create [segments](segments.md), [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="50476-138">Деректердің құпиялылығы мен сәйкестігі</span><span class="sxs-lookup"><span data-stu-id="50476-138">Data privacy and compliance</span></span>

<span data-ttu-id="50476-139">Деректерді HERE Technologies платформасына жіберу үшін Dynamics 365 Customer Insights бағдарламасын қосқан кезде, Dynamics 365 Customer Insights талаптарына сәйкестік шекарасынан тыс деректерді, соның ішінде жеке деректер сияқты ықтимал құпия деректерді беруге мүмкіндік бересіз.</span><span class="sxs-lookup"><span data-stu-id="50476-139">When you enable Dynamics 365 Customer Insights to transmit data to HERE Technologies, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="50476-140">Microsoft мұндай деректерді сіздің нұсқауыңыз бойынша тасымалдайды, бірақ HERE Technologies платформасының кез келген құпиялылық немесе қауіпсіздік міндеттемелеріне сәйкес келуіне жауап бересіз.</span><span class="sxs-lookup"><span data-stu-id="50476-140">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that HERE Technologies meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="50476-141">Қосымша ақпаратты [Microsoft құпиялық туралы мәлімдемесі](https://go.microsoft.com/fwlink/?linkid=396732) бөлімінен қараңыз.</span><span class="sxs-lookup"><span data-stu-id="50476-141">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="50476-142">Бұл функцияны тоқтату үшін бұл арттыруды кез келген уақытта Dynamics 365 Customer Insights әкімшісі жоя алады.</span><span class="sxs-lookup"><span data-stu-id="50476-142">Your Dynamics 365 Customer Insights Administrator can remove this enrichment at any time to discontinue use of this functionality.</span></span>
