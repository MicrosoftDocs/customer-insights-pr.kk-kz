---
title: Үшінші тараптың арттыру Experian платформасымен арттыру
description: Үшінші тараптың Experian арттыруы туралы жалпы ақпарат.
ms.date: 12/10/2020
ms.reviewer: kishorem
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: baf3cc58a233b70c48fb94ac4a543d162f91bdd1
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: kk-KZ
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269567"
---
# <a name="enrich-customer-profiles-with-demographics-from-experian-preview"></a><span data-ttu-id="8212d-103">Тұтынушы профильдерін Experian ұсынған демография көмегімен арттыру (алдын ала қарау)</span><span class="sxs-lookup"><span data-stu-id="8212d-103">Enrich customer profiles with demographics from Experian (preview)</span></span>

<span data-ttu-id="8212d-104">Experian тұтынушылық және іскери несиелік есеп беру мен маркетингтік қызметтердің глобалдық көшбасшысы болып табылады.</span><span class="sxs-lookup"><span data-stu-id="8212d-104">Experian is a global leader in consumer and business credit reporting and marketing services.</span></span> <span data-ttu-id="8212d-105">Experian компаниясының деректерді арттыру қызметтерінің көмегімен өзіңіздің тұтынушыларыңыздың профилдерін тұрмыстық өлшем, кірісі және басқалары сияқты демографиясын арттыру арқылы тұтынушылар туралы тереңірек түсінік қалыптастыра аласыз.</span><span class="sxs-lookup"><span data-stu-id="8212d-105">With Experian’s data enrichment services, you can build a deeper understanding of your customers by enriching your customer profiles with demographic data such as household size, income, and more.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="8212d-106">Алғышарттар</span><span class="sxs-lookup"><span data-stu-id="8212d-106">Prerequisites</span></span>

<span data-ttu-id="8212d-107">Experian деректерін конфигурациялау үшін келесі алғышарттар орындалуы тиіс:</span><span class="sxs-lookup"><span data-stu-id="8212d-107">To configure Experian, the following prerequisites must be met:</span></span>

- <span data-ttu-id="8212d-108">Сізде белсенді Experian жазылымы бар.</span><span class="sxs-lookup"><span data-stu-id="8212d-108">You have an active Experian subscription.</span></span> <span data-ttu-id="8212d-109">Жазылым алу үшін тікелей [Experian компаниясына хабарласыңыз](https://www.experian.com/marketing-services/contact).</span><span class="sxs-lookup"><span data-stu-id="8212d-109">To get a subscription, [contact Experian](https://www.experian.com/marketing-services/contact) directly.</span></span> <span data-ttu-id="8212d-110">[Experian деректерін арттыру туралы қосымша ақпарат](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).</span><span class="sxs-lookup"><span data-stu-id="8212d-110">[Learn more about Experian Data Enrichment](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).</span></span>
- <span data-ttu-id="8212d-111">Experian сіз үшін жасаған SSH-қосылған қауіпсіз тасымалдау (ST) тіркелгісіне арналған пайдаланушы идентификаторы, тарап идентификаторы және үлгі нөмірі бар.</span><span class="sxs-lookup"><span data-stu-id="8212d-111">You have the User ID, Party ID, and Model Number for your SSH-enabled Secure Transport (ST) account that Experian created for you.</span></span>
- <span data-ttu-id="8212d-112">Аудитория түсініктерінде [әкімші](permissions.md#administrator) рұқсаттарыңыз бар.</span><span class="sxs-lookup"><span data-stu-id="8212d-112">You have [Administrator](permissions.md#administrator) permissions in audience insights.</span></span>

## <a name="configuration"></a><span data-ttu-id="8212d-113">Теңшелім</span><span class="sxs-lookup"><span data-stu-id="8212d-113">Configuration</span></span>

1. <span data-ttu-id="8212d-114">**Деректер** > **Арттыру** тармағына өтіп, **Анықтау** қойыншасын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="8212d-114">Go to **Data** > **Enrichment** and select the **Discover** tab.</span></span>

1. <span data-ttu-id="8212d-115">Experian тақтайшасында **Менің деректерімді арттыру** пәрменін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="8212d-115">Select **Enrich my data** on the Experian tile.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="8212d-116">![Experian тақтайшасы](media/experian-tile.png "Experian тақтайшасы")</span><span class="sxs-lookup"><span data-stu-id="8212d-116">![Experian tile](media/experian-tile.png "Experian tile")</span></span>

1. <span data-ttu-id="8212d-117">**Бастау** пәрменін таңдап, Experian қауіпсіз тасымалдау тіркелгісі үшін пайдаланушы идентификаторы, тарап идентификаторы мен үлгі нөмірін енгізіңіз.</span><span class="sxs-lookup"><span data-stu-id="8212d-117">Select **Get started** and enter the User ID, Party ID, and Model Number for your Experian Secure Transport account.</span></span> <span data-ttu-id="8212d-118">**Келісемін** құсбелгісін таңдау арқылы **Деректер құпиялығы мен сәйкестігі** келісімін қарап шығыңыз және қамтамасыз етіңіз.</span><span class="sxs-lookup"><span data-stu-id="8212d-118">Review and provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox.</span></span> <span data-ttu-id="8212d-119">**Қолдану** пәрменін таңдау арқылы барлық кірістерді растаңыз.</span><span class="sxs-lookup"><span data-stu-id="8212d-119">Confirm all inputs by selecting **Apply**.</span></span>

## <a name="map-your-fields"></a><span data-ttu-id="8212d-120">Өрістерді салыстыру</span><span class="sxs-lookup"><span data-stu-id="8212d-120">Map your fields</span></span>

1.  <span data-ttu-id="8212d-121">**Деректерді қосу** опциясын таңдап, Experian жүйесіндегі демографиялық деректермен арттыру қажет **Тұтынушы деректерінің жиынтығын** таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="8212d-121">Select **Add data** and choose the **Customer data set** you want to enrich with demographics data from Experian.</span></span> <span data-ttu-id="8212d-122">Барлық тұтынушы профильдерін арттыру үшін **Тұтынушы** нысанын таңдауға болады немесе сол сегменттегі тек тұтынушы профильдерін арттыру үшін сегмент нысанын таңдауға болады.</span><span class="sxs-lookup"><span data-stu-id="8212d-122">You can select the **Customer** entity to enrich all your customer profiles or select a segment entity to enrich only customer profiles contained in that segment.</span></span>

1. <span data-ttu-id="8212d-123">Идентификациялық рұқсат үшін Experian жүйесіне жіберілетін **Атауы және мекенжайы**, **Электрондық поштасы** немесе **Телефон** кілттік идентификаторларын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="8212d-123">Select your key identifiers from **Name and Address**, **E-mail**, or **Phone** to send to Experian for identity resolution.</span></span>

   > [!TIP]
   > <span data-ttu-id="8212d-124">Experian компаниясына жіберілген басқа негізгі идентификатор сипаттары сәйкес келу жылдамдығын жоғарылатуы мүмкін.</span><span class="sxs-lookup"><span data-stu-id="8212d-124">More key identifier attributes sent to Experian likely yield a higher match rate.</span></span>

1. <span data-ttu-id="8212d-125">**Келесі** пәрменін таңдап, таңдалған негізгі идентификатор өрістеріне бірыңғай тұтынушы нысанынан сәйкес төлсипаттарды салыстырыңыз.</span><span class="sxs-lookup"><span data-stu-id="8212d-125">Select **Next** and map the corresponding attributes from your unified customer entity for the selected key identifier fields.</span></span>

1. <span data-ttu-id="8212d-126">Experian компаниясына жіберу керек қосымша төлсипаттарды салыстыру үшін **Төлсипат қосу** пәрменін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="8212d-126">Select **Add attribute** to map any additional attributes you would like to send to Experian.</span></span>

1.  <span data-ttu-id="8212d-127">Өрісті салыстыруды аяқтау үшін **Сақтау** опциясын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="8212d-127">Select **Save** to complete the field mapping.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="8212d-128">![Experian өрісін салыстыру](media/experian-field-mapping.png "Experian өрісін салыстыру")</span><span class="sxs-lookup"><span data-stu-id="8212d-128">![Experian field mapping](media/experian-field-mapping.png "Experian field mapping")</span></span>

## <a name="enrichment-results"></a><span data-ttu-id="8212d-129">Толықтыру нәтижелері</span><span class="sxs-lookup"><span data-stu-id="8212d-129">Enrichment results</span></span>

<span data-ttu-id="8212d-130">Арттыру процесін бастау үшін пәрмендер жолағынан **Іске қосу** пәрменін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="8212d-130">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="8212d-131">Сондай-ақ, жүйеге [жоспарланған жаңарту](system.md#schedule-tab) бөлігі ретінде арттыруды автоматты түрде іске қосуына мүмкіндік беруге болады.</span><span class="sxs-lookup"><span data-stu-id="8212d-131">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="8212d-132">Өңдеу уақыты тұтынушы деректерінің көлеміне және Experian тіркелгісіне арналған арттыру процестеріне байланысты болады.</span><span class="sxs-lookup"><span data-stu-id="8212d-132">The processing time will depend on the size of your customer data and the enrichment processes set up for your account by Experian.</span></span>

<span data-ttu-id="8212d-133">Арттыру процесі аяқталғаннан кейін, жаңа арттырылған тұтынушы профильдерінің деректерін **Менің арттыруларым** астынан қарап шығуға болады.</span><span class="sxs-lookup"><span data-stu-id="8212d-133">After the enrichment process completes, you can review the newly enriched customer profiles data under **My enrichments**.</span></span> <span data-ttu-id="8212d-134">Сонымен қатар, соңғы жаңартудың уақыты мен арттырылған профильдер санын таба аласыз.</span><span class="sxs-lookup"><span data-stu-id="8212d-134">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="8212d-135">**Толықтырылған деректерді көру** параметрін таңдау арқылы әрбір толықтырылған профильдің толық көрінісіне қатынаса аласыз.</span><span class="sxs-lookup"><span data-stu-id="8212d-135">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="8212d-136">Келесі қадамдар</span><span class="sxs-lookup"><span data-stu-id="8212d-136">Next steps</span></span>

<span data-ttu-id="8212d-137">Толықтырылған тұтынушы деректерінің негізінде жасаңыз.</span><span class="sxs-lookup"><span data-stu-id="8212d-137">Build on top of your enriched customer data.</span></span> <span data-ttu-id="8212d-138">Тұтынушыларға жекелендірілген тәжірибелерді жеткізу үшін [сегменттер](segments.md), [шаралар](measures.md) жасаңыз және [деректерді экспорттаңыз](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="8212d-138">Create [segments](segments.md), [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="8212d-139">Деректердің құпиялылығы мен сәйкестігі</span><span class="sxs-lookup"><span data-stu-id="8212d-139">Data privacy and compliance</span></span>

<span data-ttu-id="8212d-140">Деректерді Experian платформасына жіберу үшін Dynamics 365 Customer Insights бағдарламасын қосқан кезде, Dynamics 365 Customer Insights талаптарына сәйкестік шекарасынан тыс деректерді, соның ішінде жеке деректер сияқты ықтимал құпия деректерді беруге мүмкіндік бересіз.</span><span class="sxs-lookup"><span data-stu-id="8212d-140">When you enable Dynamics 365 Customer Insights to transmit data to Experian, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="8212d-141">Microsoft мұндай деректерді сіздің нұсқауыңыз бойынша тасымалдайды, бірақ Experian платформасының кез келген құпиялылық немесе қауіпсіздік міндеттемелеріне сәйкес келуіне жауап бересіз.</span><span class="sxs-lookup"><span data-stu-id="8212d-141">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Experian meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="8212d-142">Қосымша ақпаратты [Microsoft құпиялық туралы мәлімдемесі](https://go.microsoft.com/fwlink/?linkid=396732) бөлімінен қараңыз.</span><span class="sxs-lookup"><span data-stu-id="8212d-142">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="8212d-143">Бұл функцияны тоқтату үшін бұл арттыруды кез келген уақытта Dynamics 365 Customer Insights әкімшісі жоя алады.</span><span class="sxs-lookup"><span data-stu-id="8212d-143">Your Dynamics 365 Customer Insights Administrator can remove this enrichment at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]