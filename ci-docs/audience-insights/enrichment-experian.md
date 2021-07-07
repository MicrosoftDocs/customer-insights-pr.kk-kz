---
title: Experian үшінші тарап толықтыруымен толықтыру
description: Experian үшінші тарап толықтыруы туралы жалпы ақпарат.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 7c82fe92b3351a782a4fa6510300d870b742d042
ms.sourcegitcommit: 42b3bce1e20e7cc707d232844dacfeed3d6fc096
ms.translationtype: HT
ms.contentlocale: kk-KZ
ms.lasthandoff: 06/28/2021
ms.locfileid: "6309827"
---
# <a name="enrich-customer-profiles-with-demographics-from-experian-preview"></a><span data-ttu-id="c23f2-103">Тұтынушы профильдерін Experian (алдын ала қарау нұсқасы) демографиялық деректермен толықтырыңыз</span><span class="sxs-lookup"><span data-stu-id="c23f2-103">Enrich customer profiles with demographics from Experian (preview)</span></span>

<span data-ttu-id="c23f2-104">Experian — тұтынушылық және бизнес несиелік есептілік пен маркетингтік қызметтердің әлемдік көшбасшысы болып табылады.</span><span class="sxs-lookup"><span data-stu-id="c23f2-104">Experian is a global leader in consumer and business credit reporting and marketing services.</span></span> <span data-ttu-id="c23f2-105">Experian деректерді толықтыру қызметтерімен сіз өзіңіздің тұтынушыларыңыздың профильдерін отбасындағы адамдар саны, кірісі және басқалары сияқты демографиялық деректермен толықтыру арқылы тұтынушыларыңыз туралы тереңірек түсінік қалыптастыра аласыз.</span><span class="sxs-lookup"><span data-stu-id="c23f2-105">With Experian’s data enrichment services, you can build a deeper understanding of your customers by enriching your customer profiles with demographic data such as household size, income, and more.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="c23f2-106">Алғышарттар</span><span class="sxs-lookup"><span data-stu-id="c23f2-106">Prerequisites</span></span>

<span data-ttu-id="c23f2-107">Experian қызметін конфигурациялау үшін, келесі алғышарттар орындалуы керек:</span><span class="sxs-lookup"><span data-stu-id="c23f2-107">To configure Experian, the following prerequisites must be met:</span></span>

- <span data-ttu-id="c23f2-108">Сізде белсенді Experian жазылымы бар.</span><span class="sxs-lookup"><span data-stu-id="c23f2-108">You have an active Experian subscription.</span></span> <span data-ttu-id="c23f2-109">Жазылымды алу үшін, [Experian](https://www.experian.com/marketing-services/contact) компаниясына тікелей хабарласыңыз.</span><span class="sxs-lookup"><span data-stu-id="c23f2-109">To get a subscription, [contact Experian](https://www.experian.com/marketing-services/contact) directly.</span></span> <span data-ttu-id="c23f2-110">[Experian деректерді толықтыру қызметі туралы қосымша ақпарат](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).</span><span class="sxs-lookup"><span data-stu-id="c23f2-110">[Learn more about Experian Data Enrichment](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).</span></span>

- <span data-ttu-id="c23f2-111">Experian қосылымын әкімші конфигурациялап қойған *немесе* сізде [әкімші](permissions.md#administrator) рұқсаттары бар.</span><span class="sxs-lookup"><span data-stu-id="c23f2-111">An Experian connection has already been configured by an administrator *or* you have [administrator](permissions.md#administrator) permissions.</span></span> <span data-ttu-id="c23f2-112">Сонымен қатар Experian сіз үшін жасаған SSH қосулы қауіпсіз тасымалдау (ST) тіркелгісі үшін пайдаланушы идентификаторы, тарап идентификаторы және үлгі нөмірі қажет.</span><span class="sxs-lookup"><span data-stu-id="c23f2-112">You also need the User ID, Party ID, and Model Number for your SSH-enabled Secure Transport (ST) account that Experian created for you.</span></span>

## <a name="supported-countriesregions"></a><span data-ttu-id="c23f2-113">Қолдау көрсетілетін елдер/аймақтар</span><span class="sxs-lookup"><span data-stu-id="c23f2-113">Supported countries/regions</span></span>

<span data-ttu-id="c23f2-114">Қазіргі уақытта біз тек Америка Құрама Штаттарында тұтынушы профильдерін толықтыруға қолдау көрсетеміз.</span><span class="sxs-lookup"><span data-stu-id="c23f2-114">We currently support enriching customer profiles in the United States only.</span></span>

## <a name="configure-the-enrichment"></a><span data-ttu-id="c23f2-115">Жақсартуды конфигурациялау</span><span class="sxs-lookup"><span data-stu-id="c23f2-115">Configure the enrichment</span></span>

1. <span data-ttu-id="c23f2-116">**Деректер** > **Арттыру** тармағына өтіп, **Анықтау** қойыншасын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="c23f2-116">Go to **Data** > **Enrichment** and select the **Discover** tab.</span></span>

1. <span data-ttu-id="c23f2-117">Experian қатарында **Деректерімді толықтыру** түймешігін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="c23f2-117">Select **Enrich my data** on the Experian tile.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="c23f2-118">![Experian қатар](media/experian-tile.png "Experian tile")</span><span class="sxs-lookup"><span data-stu-id="c23f2-118">![Experian tile](media/experian-tile.png "Experian tile")</span></span>
   > 

1. <span data-ttu-id="c23f2-119">Ашылмалы тізімнен [қосылым](connections.md) таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="c23f2-119">Select a [connection](connections.md) from the dropdown list.</span></span> <span data-ttu-id="c23f2-120">Егер қосылым болмаса, әкімшіге хабарласыңыз.</span><span class="sxs-lookup"><span data-stu-id="c23f2-120">Contact an administrator if no connection is available.</span></span> <span data-ttu-id="c23f2-121">Егер сіз әкімші болсаңыз, **Қосылым қосу** және ашылмалы тізімнен Experian қызметін таңдау арқылы қосылым жасай аласыз.</span><span class="sxs-lookup"><span data-stu-id="c23f2-121">If you are an administrator, you can create a connection by selecting **Add connection** and choosing Experian from the dropdown list.</span></span> 

1. <span data-ttu-id="c23f2-122">Қосылым таңдауын растау үшін **Experian қызметіне қосылу** түймешігін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="c23f2-122">Select **Connect to Experian** to confirm the connection selection.</span></span>

1.  <span data-ttu-id="c23f2-123">**Келесі** түймешігін таңдаңыз және Experian демографиялық деректерімен толықтыру керек **Тұтынушының деректер жинағын** таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="c23f2-123">Select **Next** and choose the **Customer data set** you want to enrich with demographics data from Experian.</span></span> <span data-ttu-id="c23f2-124">Барлық тұтынушы профильдерін арттыру үшін **Тұтынушы** нысанын таңдауға болады немесе сол сегменттегі тек тұтынушы профильдерін арттыру үшін сегмент нысанын таңдауға болады.</span><span class="sxs-lookup"><span data-stu-id="c23f2-124">You can select the **Customer** entity to enrich all your customer profiles or select a segment entity to enrich only customer profiles contained in that segment.</span></span>

    :::image type="content" source="media/enrichment-Experian-configuration-customer-data-set.png" alt-text="Тұтынушының деректер жиынтығын таңдау кезіндегі скриншот.":::

1. <span data-ttu-id="c23f2-126">**Келесі** түймешігін таңдаңыз және Experian ішінен сәйкес келетін демографиялық деректерді іздеу үшін бірыңғай профильдеріңізден өрістердің қай түрін қолдану керектігін анықтаңыз.</span><span class="sxs-lookup"><span data-stu-id="c23f2-126">Select **Next** and define which type of fields from your unified profiles should be used to look for matching demographics data from Experian.</span></span> <span data-ttu-id="c23f2-127">**Атауы және мекен-жайы**, **Телефон** немесе **Электрондық пошта** өрістерінің кем дегенде біреуі қажет.</span><span class="sxs-lookup"><span data-stu-id="c23f2-127">At least one of the fields **Name and address**, **Phone**, or **Email** is required.</span></span> <span data-ttu-id="c23f2-128">Сәйкестіктің жоғары дәлдігі үшін тағы екі өрісті қосуға болады.</span><span class="sxs-lookup"><span data-stu-id="c23f2-128">For a higher match accuracy, up to two other fields can be added.</span></span> <span data-ttu-id="c23f2-129">Бұл таңдау келесі қадамда қатынасатын салыстыру өрістеріне әсер етеді.</span><span class="sxs-lookup"><span data-stu-id="c23f2-129">This selection will affect the mapping fields you have access to in the next step.</span></span>

    > [!TIP]
    > <span data-ttu-id="c23f2-130">Experian қызметіне қосымша негізгі төлсипаттарды жіберу жоғары сәйкестік коэффициентіне алып келуі мүмкін.</span><span class="sxs-lookup"><span data-stu-id="c23f2-130">More key identifier attributes sent to Experian likely yield a higher match rate.</span></span>

1. <span data-ttu-id="c23f2-131">Өрістерді салыстыруды бастау үшін **Келесі** түймешігін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="c23f2-131">Select **Next** to start the field mapping.</span></span>

1. <span data-ttu-id="c23f2-132">Experian ішінен сәйкес келетін демографиялық деректерді іздеу үшін бірыңғай профильдеріңізден өрістердің қай түрін қолдану керектігін анықтаңыз.</span><span class="sxs-lookup"><span data-stu-id="c23f2-132">Define which fields from your unified profiles should be used to look for matching demographics data from Experian.</span></span> <span data-ttu-id="c23f2-133">Қажетті өрістер белгіленген.</span><span class="sxs-lookup"><span data-stu-id="c23f2-133">Required fields are marked.</span></span>

1. <span data-ttu-id="c23f2-134">Жақсарту атауын және шығыс ұйымның атауын көрсетіңіз.</span><span class="sxs-lookup"><span data-stu-id="c23f2-134">Provide a name for the enrichment and a name for the output entity.</span></span>

1. <span data-ttu-id="c23f2-135">Таңдауларды қарап шыққаннан кейін **Жақсартуды сақтау** түймешігін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="c23f2-135">Select **Save enrichment** after reviewing your choices.</span></span>

## <a name="configure-the-connection-for-experian"></a><span data-ttu-id="c23f2-136">Experian қосылымын конфигурациялау</span><span class="sxs-lookup"><span data-stu-id="c23f2-136">Configure the connection for Experian</span></span> 

<span data-ttu-id="c23f2-137">Қосылымдарды конфигурациялау үшін сіз әкімші болуыңыз керек.</span><span class="sxs-lookup"><span data-stu-id="c23f2-137">You need to be an administrator to configure connections.</span></span> <span data-ttu-id="c23f2-138">Толықтыруды конфигурациялау кезінде **Қосылым қосу** түймешігін таңдаңыз *немесе* **Әкімші** > **Қосылымдар** тармағына өтіңіз және Experian қатарынан **Орнату** түймешігін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="c23f2-138">Select **Add connection** when configuring an enrichment *or* go to **Admin** > **Connections** and select **Set up** on the Experian tile.</span></span>

1. <span data-ttu-id="c23f2-139">**Жұмысты бастау** түймешігін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="c23f2-139">Select **Get Started**.</span></span>

1. <span data-ttu-id="c23f2-140">Қосылым атауын **Көрсетілетін атауы** терезесіне енгізіңіз.</span><span class="sxs-lookup"><span data-stu-id="c23f2-140">Enter a name for the connection in the **Display name** box.</span></span>

1. <span data-ttu-id="c23f2-141">Experian қауіпсіз тасымалдау тіркелгісі үшін жарамды пайдаланушы идентификаторын, тарап идентификаторын және үлгі нөмірін енгізіңіз.</span><span class="sxs-lookup"><span data-stu-id="c23f2-141">Enter valid User ID, Party ID, and Model Number for your Experian Secure Transport account.</span></span>

1. <span data-ttu-id="c23f2-142">**Деректердің құпиялылығы мен сәйкестігі** бөлімін қарап шығыңыз және **Келісемін** құсбелгісін қою арқылы келісім беріңіз.</span><span class="sxs-lookup"><span data-stu-id="c23f2-142">Review and provide your consent for **Data privacy and compliance** by selecting **I agree**.</span></span>

1. <span data-ttu-id="c23f2-143">Конфигурацияны тексеру үшін **Тексеру** түймешігін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="c23f2-143">Select **Verify** to validate the configuration.</span></span>

1. <span data-ttu-id="c23f2-144">Тексеруді аяқтағаннан кейін **Сақтау** түймешігін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="c23f2-144">After completing the verification, select **Save**.</span></span>
   
   :::image type="content" source="media/enrichment-Experian-connection.png" alt-text="Experian қосылым конфигурациясы тақтасы.":::

## <a name="enrichment-results"></a><span data-ttu-id="c23f2-146">Толықтыру нәтижелері</span><span class="sxs-lookup"><span data-stu-id="c23f2-146">Enrichment results</span></span>

<span data-ttu-id="c23f2-147">Арттыру процесін бастау үшін пәрмендер жолағынан **Іске қосу** пәрменін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="c23f2-147">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="c23f2-148">Сондай-ақ, жүйеге [жоспарланған жаңарту](system.md#schedule-tab) бөлігі ретінде арттыруды автоматты түрде іске қосуына мүмкіндік беруге болады.</span><span class="sxs-lookup"><span data-stu-id="c23f2-148">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="c23f2-149">Өңдеу уақыты тұтынушы деректерінің көлеміне және Experian қызметі үшін тіркелгі орнатқан толықтыру процестеріне байланысты болады.</span><span class="sxs-lookup"><span data-stu-id="c23f2-149">The processing time will depend on the size of your customer data and the enrichment processes set up for your account by Experian.</span></span>

<span data-ttu-id="c23f2-150">Арттыру процесі аяқталғаннан кейін, жаңа арттырылған тұтынушы профильдерінің деректерін **Менің арттыруларым** астынан қарап шығуға болады.</span><span class="sxs-lookup"><span data-stu-id="c23f2-150">After the enrichment process completes, you can review the newly enriched customer profiles data under **My enrichments**.</span></span> <span data-ttu-id="c23f2-151">Сонымен қатар соңғы жаңартудың уақыты мен арттырылған профильдер санын таба аласыз.</span><span class="sxs-lookup"><span data-stu-id="c23f2-151">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="c23f2-152">**Толықтырылған деректерді көру** параметрін таңдау арқылы әрбір толықтырылған профильдің толық көрінісіне қатынаса аласыз.</span><span class="sxs-lookup"><span data-stu-id="c23f2-152">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="c23f2-153">Келесі қадамдар</span><span class="sxs-lookup"><span data-stu-id="c23f2-153">Next steps</span></span>

<span data-ttu-id="c23f2-154">Толықтырылған тұтынушы деректерінің негізінде жасаңыз.</span><span class="sxs-lookup"><span data-stu-id="c23f2-154">Build on top of your enriched customer data.</span></span> <span data-ttu-id="c23f2-155">Тұтынушыларға жеке тәжірибелер ұсыну үшін [сегменттер](segments.md) мен [өлшемдер](measures.md) жасаңыз және тіпті [деректерді экспорттаңыз](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="c23f2-155">Create [segments](segments.md) and [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="c23f2-156">Деректердің құпиялылығы мен сәйкестігі</span><span class="sxs-lookup"><span data-stu-id="c23f2-156">Data privacy and compliance</span></span>

<span data-ttu-id="c23f2-157">Dynamics 365 Customer Insights бағдарламасын деректерді Experian қызметіне тасымалдау үшін қосқан кезде, жеке деректер сияқты ықтимал құпия деректерді қоса алғанда сіз Dynamics 365 Customer Insights бағдарламасы үшін деректерді сәйкестік шекарасынан тыс тасымалдауға рұқсат бересіз.</span><span class="sxs-lookup"><span data-stu-id="c23f2-157">When you enable Dynamics 365 Customer Insights to transmit data to Experian, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="c23f2-158">Microsoft мұндай деректерді сіздің нұсқауыңыз бойынша тасымалдайды, бірақ сіз Experian қызметінің сізде болуы мүмкін кез келген құпиялылық немесе қауіпсіздік міндеттемелерін орындауын қамтамасыз етуіне жауаптысыз.</span><span class="sxs-lookup"><span data-stu-id="c23f2-158">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Experian meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="c23f2-159">Қосымша ақпаратты [Microsoft құпиялық туралы мәлімдемесі](https://go.microsoft.com/fwlink/?linkid=396732) бөлімінен қараңыз.</span><span class="sxs-lookup"><span data-stu-id="c23f2-159">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="c23f2-160">Бұл функцияны тоқтату үшін Dynamics 365 Customer Insights әкімшісі бұл толықтыруды кез келген уақытта жоя алады.</span><span class="sxs-lookup"><span data-stu-id="c23f2-160">Your Dynamics 365 Customer Insights administrator can remove this enrichment at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
