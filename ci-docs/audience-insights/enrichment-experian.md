---
title: Үшінші тараптың арттыру Experian платформасымен арттыру
description: Үшінші тараптың Experian арттыруы туралы жалпы ақпарат.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 9cf2a7fa18ecc022ea67f6829f52381ad59f3172
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: kk-KZ
ms.lasthandoff: 04/14/2021
ms.locfileid: "5896380"
---
# <a name="enrich-customer-profiles-with-demographics-from-experian-preview"></a><span data-ttu-id="4d144-103">Тұтынушы профильдерін Experian ұсынған демография көмегімен арттыру (алдын ала қарау)</span><span class="sxs-lookup"><span data-stu-id="4d144-103">Enrich customer profiles with demographics from Experian (preview)</span></span>

<span data-ttu-id="4d144-104">Experian тұтынушылық және іскери несиелік есеп беру мен маркетингтік қызметтердің глобалдық көшбасшысы болып табылады.</span><span class="sxs-lookup"><span data-stu-id="4d144-104">Experian is a global leader in consumer and business credit reporting and marketing services.</span></span> <span data-ttu-id="4d144-105">Experian компаниясының деректерді арттыру қызметтерінің көмегімен өзіңіздің тұтынушыларыңыздың профилдерін тұрмыстық өлшем, кірісі және басқалары сияқты демографиясын арттыру арқылы тұтынушылар туралы тереңірек түсінік қалыптастыра аласыз.</span><span class="sxs-lookup"><span data-stu-id="4d144-105">With Experian’s data enrichment services, you can build a deeper understanding of your customers by enriching your customer profiles with demographic data such as household size, income, and more.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="4d144-106">Алғышарттар</span><span class="sxs-lookup"><span data-stu-id="4d144-106">Prerequisites</span></span>

<span data-ttu-id="4d144-107">Experian деректерін конфигурациялау үшін келесі алғышарттар орындалуы тиіс:</span><span class="sxs-lookup"><span data-stu-id="4d144-107">To configure Experian, the following prerequisites must be met:</span></span>

- <span data-ttu-id="4d144-108">Сізде белсенді Experian жазылымы бар.</span><span class="sxs-lookup"><span data-stu-id="4d144-108">You have an active Experian subscription.</span></span> <span data-ttu-id="4d144-109">Жазылым алу үшін тікелей [Experian компаниясына хабарласыңыз](https://www.experian.com/marketing-services/contact).</span><span class="sxs-lookup"><span data-stu-id="4d144-109">To get a subscription, [contact Experian](https://www.experian.com/marketing-services/contact) directly.</span></span> <span data-ttu-id="4d144-110">[Experian деректерін арттыру туралы қосымша ақпарат](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).</span><span class="sxs-lookup"><span data-stu-id="4d144-110">[Learn more about Experian Data Enrichment](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).</span></span>

- <span data-ttu-id="4d144-111">Experian қосылымын әкімші конфигурациялап қойған *немесе* сізде [әкімші](permissions.md#administrator) рұқсаттары бар.</span><span class="sxs-lookup"><span data-stu-id="4d144-111">An Experian connection has already been configured by an administrator *or* you have [administrator](permissions.md#administrator) permissions.</span></span> <span data-ttu-id="4d144-112">Сондай-ақ сізге Experian жасаған SSH қосылған Secure Transport (ST) тіркелгісі үшін пайдаланушы идентификаторы, тарап идентификаторы және модель нөмірі қажет.</span><span class="sxs-lookup"><span data-stu-id="4d144-112">You also need the User ID, Party ID, and Model Number for your SSH-enabled Secure Transport (ST) account that Experian created for you.</span></span>

## <a name="configure-the-enrichment"></a><span data-ttu-id="4d144-113">Жақсартуды конфигурациялау</span><span class="sxs-lookup"><span data-stu-id="4d144-113">Configure the enrichment</span></span>

1. <span data-ttu-id="4d144-114">**Деректер** > **Арттыру** тармағына өтіп, **Анықтау** қойыншасын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="4d144-114">Go to **Data** > **Enrichment** and select the **Discover** tab.</span></span>

1. <span data-ttu-id="4d144-115">Experian тақтайшасында **Менің деректерімді арттыру** пәрменін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="4d144-115">Select **Enrich my data** on the Experian tile.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="4d144-116">![Experian тақтайшасы](media/experian-tile.png "Experian тақтайшасы")</span><span class="sxs-lookup"><span data-stu-id="4d144-116">![Experian tile](media/experian-tile.png "Experian tile")</span></span>
   > 

1. <span data-ttu-id="4d144-117">Ашылмалы тізімнен [қосылымды](connections.md) таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="4d144-117">Select a [connection](connections.md) from the drop-down.</span></span> <span data-ttu-id="4d144-118">Егер қосылым болмаса, әкімшіге хабарласыңыз.</span><span class="sxs-lookup"><span data-stu-id="4d144-118">Contact an administrator if no connection is available.</span></span> <span data-ttu-id="4d144-119">Егер сіз әкімші болсаңыз, **Қосылым қосу** түймешігін және ашылмалы тізімнен Experian қосылымын таңдау арқылы қосылым жасай аласыз.</span><span class="sxs-lookup"><span data-stu-id="4d144-119">If you are an administrator, you can create a connection by selecting **Add connection** and choosing Experian from the drop-down.</span></span> 

1. <span data-ttu-id="4d144-120">Қосылым таңдауын растау үшін **Experian қосылымына қосылу** түймешігін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="4d144-120">Select **Connect to Experian** to confirm the connection selection.</span></span>

1.  <span data-ttu-id="4d144-121">**Келесі** түймешігін таңдаңыз және Experian қосылымындағы демографиялық деректермен жақсарту керек **Тұтынушы деректерінің жиынтығы** параметрін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="4d144-121">Select **Next** and choose the **Customer data set** you want to enrich with demographics data from Experian.</span></span> <span data-ttu-id="4d144-122">Барлық тұтынушы профильдерін арттыру үшін **Тұтынушы** нысанын таңдауға болады немесе сол сегменттегі тек тұтынушы профильдерін арттыру үшін сегмент нысанын таңдауға болады.</span><span class="sxs-lookup"><span data-stu-id="4d144-122">You can select the **Customer** entity to enrich all your customer profiles or select a segment entity to enrich only customer profiles contained in that segment.</span></span>

    :::image type="content" source="media/enrichment-Experian-configuration-customer-data-set.png" alt-text="Тұтынушының деректер жиынтығын таңдау кезіндегі скриншот.":::

1. <span data-ttu-id="4d144-124">**Келесі** түймешігін таңдаңыз және бірыңғай профильдердегі өрістердің қай түрін Experian қосылымындағы сәйкес келетін демографиялық деректерді іздеу үшін қолдану керектігін анықтаңыз.</span><span class="sxs-lookup"><span data-stu-id="4d144-124">Select **Next** and define which type of fields from your unified profiles should be used to look for matching demographics data from Experian.</span></span> <span data-ttu-id="4d144-125">**Атауы және мекен-жайы**, **Телефон** немесе **Электрондық пошта** өрістерінің кем дегенде біреуі қажет.</span><span class="sxs-lookup"><span data-stu-id="4d144-125">At least one of the fields **Name and address**, **Phone**, or **Email** is required.</span></span> <span data-ttu-id="4d144-126">Сәйкестіктің жоғары дәлдігі үшін тағы екі өрісті қосуға болады.</span><span class="sxs-lookup"><span data-stu-id="4d144-126">For a higher match accuracy, up to two other fields can be added.</span></span> <span data-ttu-id="4d144-127">Бұл таңдау келесі қадамда қатынасатын салыстыру өрістеріне әсер етеді.</span><span class="sxs-lookup"><span data-stu-id="4d144-127">This selection will affect the mapping fields you have access to in the next step.</span></span>

    > [!TIP]
    > <span data-ttu-id="4d144-128">Experian компаниясына жіберілген басқа негізгі идентификатор сипаттары сәйкес келу жылдамдығын жоғарылатуы мүмкін.</span><span class="sxs-lookup"><span data-stu-id="4d144-128">More key identifier attributes sent to Experian likely yield a higher match rate.</span></span>

1. <span data-ttu-id="4d144-129">Өрістерді салыстыруды бастау үшін **Келесі** түймешігін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="4d144-129">Select **Next** to start the field mapping.</span></span>

1. <span data-ttu-id="4d144-130">Бірыңғай профильдердегі өрістердің қай түрін Experian қосылымындағы сәйкес келетін демографиялық деректерді іздеу үшін қолдану керектігін анықтаңыз.</span><span class="sxs-lookup"><span data-stu-id="4d144-130">Define which fields from your unified profiles should be used to look for matching demographics data from Experian.</span></span> <span data-ttu-id="4d144-131">Қажетті өрістер белгіленген.</span><span class="sxs-lookup"><span data-stu-id="4d144-131">Required fields are marked.</span></span>

1. <span data-ttu-id="4d144-132">Жақсарту атауын және шығыс ұйымның атауын көрсетіңіз.</span><span class="sxs-lookup"><span data-stu-id="4d144-132">Provide a name for the enrichment and a name for the output entity.</span></span>

1. <span data-ttu-id="4d144-133">Таңдауларды қарап шыққаннан кейін **Жақсартуды сақтау** түймешігін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="4d144-133">Select **Save enrichment** after reviewing your choices.</span></span>

## <a name="configure-the-connection-for-experian"></a><span data-ttu-id="4d144-134">Experian үшін қосылымды конфигурациялау</span><span class="sxs-lookup"><span data-stu-id="4d144-134">Configure the connection for Experian</span></span> 

<span data-ttu-id="4d144-135">Қосылымдарды конфигурациялау үшін сіз әкімші болуыңыз керек.</span><span class="sxs-lookup"><span data-stu-id="4d144-135">You need to be an administrator to configure connections.</span></span> <span data-ttu-id="4d144-136">Жақсартуды конфигурациялау кезінде **Қосылым қосу** түймешігін таңдаңыз *немесе* **Әкімші** > **Қосылымдар** тармағына өтіңіз және Experian тақтасында **Орнату** түймешігін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="4d144-136">Select **Add connection** when configuring an enrichment *or* go to **Admin** > **Connections** and select **Set up** on the Experian tile.</span></span>

1. <span data-ttu-id="4d144-137">**Жұмысты бастау** түймешігін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="4d144-137">Select **Get Started**.</span></span>

1. <span data-ttu-id="4d144-138">Қосылым атауын **Көрсетілетін атауы** терезесіне енгізіңіз.</span><span class="sxs-lookup"><span data-stu-id="4d144-138">Enter a name for the connection in the **Display name** box.</span></span>

1. <span data-ttu-id="4d144-139">Experian Secure Transport тіркелгісіне жарамды пайдаланушы идентификаторын, тарап идентификаторын және модель нөмірін енгізіңіз.</span><span class="sxs-lookup"><span data-stu-id="4d144-139">Enter valid User ID, Party ID, and Model Number for your Experian Secure Transport account.</span></span>

1. <span data-ttu-id="4d144-140">**Келісемін** құсбелгісін таңдау арқылы **Деректер құпиялығы мен сәйкестігі** келісімін қарап шығыңыз және қамтамасыз етіңіз</span><span class="sxs-lookup"><span data-stu-id="4d144-140">Review and provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox</span></span>

1. <span data-ttu-id="4d144-141">Конфигурацияны тексеру үшін **Тексеру** түймешігін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="4d144-141">Select **Verify** to validate the configuration.</span></span>

1. <span data-ttu-id="4d144-142">Тексеруді аяқтағаннан кейін **Сақтау** түймешігін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="4d144-142">After completing the verification, select **Save**.</span></span>
   
   :::image type="content" source="media/enrichment-Experian-connection.png" alt-text="Experian қосылымын конфигурациялау тақтасы.":::

## <a name="enrichment-results"></a><span data-ttu-id="4d144-144">Толықтыру нәтижелері</span><span class="sxs-lookup"><span data-stu-id="4d144-144">Enrichment results</span></span>

<span data-ttu-id="4d144-145">Арттыру процесін бастау үшін пәрмендер жолағынан **Іске қосу** пәрменін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="4d144-145">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="4d144-146">Сондай-ақ, жүйеге [жоспарланған жаңарту](system.md#schedule-tab) бөлігі ретінде арттыруды автоматты түрде іске қосуына мүмкіндік беруге болады.</span><span class="sxs-lookup"><span data-stu-id="4d144-146">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="4d144-147">Өңдеу уақыты тұтынушы деректерінің көлеміне және Experian тіркелгісіне арналған арттыру процестеріне байланысты болады.</span><span class="sxs-lookup"><span data-stu-id="4d144-147">The processing time will depend on the size of your customer data and the enrichment processes set up for your account by Experian.</span></span>

<span data-ttu-id="4d144-148">Арттыру процесі аяқталғаннан кейін, жаңа арттырылған тұтынушы профильдерінің деректерін **Менің арттыруларым** астынан қарап шығуға болады.</span><span class="sxs-lookup"><span data-stu-id="4d144-148">After the enrichment process completes, you can review the newly enriched customer profiles data under **My enrichments**.</span></span> <span data-ttu-id="4d144-149">Сонымен қатар, соңғы жаңартудың уақыты мен арттырылған профильдер санын таба аласыз.</span><span class="sxs-lookup"><span data-stu-id="4d144-149">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="4d144-150">**Толықтырылған деректерді көру** параметрін таңдау арқылы әрбір толықтырылған профильдің толық көрінісіне қатынаса аласыз.</span><span class="sxs-lookup"><span data-stu-id="4d144-150">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="4d144-151">Келесі қадамдар</span><span class="sxs-lookup"><span data-stu-id="4d144-151">Next steps</span></span>

<span data-ttu-id="4d144-152">Толықтырылған тұтынушы деректерінің негізінде жасаңыз.</span><span class="sxs-lookup"><span data-stu-id="4d144-152">Build on top of your enriched customer data.</span></span> <span data-ttu-id="4d144-153">Тұтынушыларға жекелендірілген тәжірибелерді жеткізу үшін [сегменттер](segments.md), [шаралар](measures.md) жасаңыз және [деректерді экспорттаңыз](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="4d144-153">Create [segments](segments.md), [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="4d144-154">Деректердің құпиялылығы мен сәйкестігі</span><span class="sxs-lookup"><span data-stu-id="4d144-154">Data privacy and compliance</span></span>

<span data-ttu-id="4d144-155">Деректерді Experian платформасына жіберу үшін Dynamics 365 Customer Insights бағдарламасын қосқан кезде, Dynamics 365 Customer Insights талаптарына сәйкестік шекарасынан тыс деректерді, соның ішінде жеке деректер сияқты ықтимал құпия деректерді беруге мүмкіндік бересіз.</span><span class="sxs-lookup"><span data-stu-id="4d144-155">When you enable Dynamics 365 Customer Insights to transmit data to Experian, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="4d144-156">Microsoft мұндай деректерді сіздің нұсқауыңыз бойынша тасымалдайды, бірақ Experian платформасының кез келген құпиялылық немесе қауіпсіздік міндеттемелеріне сәйкес келуіне жауап бересіз.</span><span class="sxs-lookup"><span data-stu-id="4d144-156">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Experian meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="4d144-157">Қосымша ақпаратты [Microsoft құпиялық туралы мәлімдемесі](https://go.microsoft.com/fwlink/?linkid=396732) бөлімінен қараңыз.</span><span class="sxs-lookup"><span data-stu-id="4d144-157">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="4d144-158">Бұл функцияны тоқтату үшін бұл арттыруды кез келген уақытта Dynamics 365 Customer Insights әкімшісі жоя алады.</span><span class="sxs-lookup"><span data-stu-id="4d144-158">Your Dynamics 365 Customer Insights Administrator can remove this enrichment at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
