---
title: Customer Insights деректерін RollWorks қызметіне экспорттау
description: RollWorks қызметі үшін қосылымды конфигурациялау және экспорттау жолы туралы ақпарат.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: dce5d51ca4587b4d7a0644cc701c1826854882b5
ms.sourcegitcommit: 831765a55775d358447cb7ffa56f2c3b85459084
ms.translationtype: HT
ms.contentlocale: kk-KZ
ms.lasthandoff: 06/01/2021
ms.locfileid: "6124096"
---
# <a name="export-segments-to-rollworks-preview"></a><span data-ttu-id="90d70-103">Сегменттерді RollWorks қызметіне экспорттау (алдын ала қарау нұсқасы)</span><span class="sxs-lookup"><span data-stu-id="90d70-103">Export segments to RollWorks (preview)</span></span>

<span data-ttu-id="90d70-104">Тұтынушылардың бірыңғай профильдерінің сегменттерін RollWorks қызметіне экспорттаңыз және оларды жарнама үшін пайдаланыңыз.</span><span class="sxs-lookup"><span data-stu-id="90d70-104">Export segments of unified customer profiles to RollWorks and use them for advertising.</span></span> 

## <a name="prerequisites-for-a-connection"></a><span data-ttu-id="90d70-105">Қосылым алғышарттары</span><span class="sxs-lookup"><span data-stu-id="90d70-105">Prerequisites for a connection</span></span>

-   <span data-ttu-id="90d70-106">Сізде [RollWorks қызметінің тіркелгісі](https://www.rollworks.com/) және тиісті әкімші тіркелгі деректері бар.</span><span class="sxs-lookup"><span data-stu-id="90d70-106">You have an [RollWorks account](https://www.rollworks.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="90d70-107">Аудитория түсініктерінде [конфигурацияланған сегменттер](segments.md) бар.</span><span class="sxs-lookup"><span data-stu-id="90d70-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="90d70-108">Экспортталған сегменттердегі тұтынушылардың бірыңғай профильдері электрондық пошта мекенжайын көрсететін өрістен тұрады.</span><span class="sxs-lookup"><span data-stu-id="90d70-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="90d70-109">Белгілі шектеулер</span><span class="sxs-lookup"><span data-stu-id="90d70-109">Known limitations</span></span>

- <span data-ttu-id="90d70-110">RollWorks қызметіне бір экспорттаған кезде 250000 профильді экспорттауға болады.</span><span class="sxs-lookup"><span data-stu-id="90d70-110">You can export up to 250'000 profiles in per export to RollWorks.</span></span>
- <span data-ttu-id="90d70-111">RollWorks қызметіне 100-ден аз профилі бар сегменттерді экспорттау мүмкін емес.</span><span class="sxs-lookup"><span data-stu-id="90d70-111">You can't export segments with fewer than 100 profiles to RollWorks.</span></span> 
- <span data-ttu-id="90d70-112">RollWorks қызметіне экспорттау сегменттермен шектеледі.</span><span class="sxs-lookup"><span data-stu-id="90d70-112">Exporting to RollWorks is limited to segments.</span></span>
- <span data-ttu-id="90d70-113">RollWorks қызметіне 250000 дейінгі профильді экспорттауды аяқтау 10 минутқа созылуы мүмкін.</span><span class="sxs-lookup"><span data-stu-id="90d70-113">Exporting up to 250'000 profiles to RollWorks can take up to 10 minutes to complete.</span></span> 
- <span data-ttu-id="90d70-114">RollWorks қызметіне экспорттауға болатын профильдер саны RollWorks қызметімен келісімшартқа байланысты және шектеулі.</span><span class="sxs-lookup"><span data-stu-id="90d70-114">The number of profiles that you can export to RollWorks is dependent and limited on your contract with RollWorks.</span></span>

## <a name="set-up-connection-to-rollworks"></a><span data-ttu-id="90d70-115">RollWorks қызметіне қосылым орнату</span><span class="sxs-lookup"><span data-stu-id="90d70-115">Set up connection to RollWorks</span></span>

1. <span data-ttu-id="90d70-116">**Әкімші** > **Қосылымдар** тармағына өтіңіз.</span><span class="sxs-lookup"><span data-stu-id="90d70-116">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="90d70-117">**Қосылым қосу** түймешігін таңдаңыз және қосылымды конфигурациялау үшін **RollWorks** параметрін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="90d70-117">Select **Add connection** and choose **RollWorks** to configure the connection.</span></span>

1. <span data-ttu-id="90d70-118">**Көрсетілетін аты** өрісінде қосылымға оңай танылатын атау енгізіңіз.</span><span class="sxs-lookup"><span data-stu-id="90d70-118">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="90d70-119">Қосылым атауы мен түрі осы қосылымды сипаттайды.</span><span class="sxs-lookup"><span data-stu-id="90d70-119">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="90d70-120">Қосылымның мақсатын түсіндіретін атауды таңдауды ұсынамыз.</span><span class="sxs-lookup"><span data-stu-id="90d70-120">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="90d70-121">Осы қосылымды кім пайдалана алатынын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="90d70-121">Choose who can use this connection.</span></span> <span data-ttu-id="90d70-122">Егер сіз ешқандай әрекет жасамасаңыз, әдепкі бойынша Әкімшілер болады.</span><span class="sxs-lookup"><span data-stu-id="90d70-122">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="90d70-123">Қосымша ақпарат алу үшін [Салымшыларға экспорттау үшін қосылымды пайдалануға рұқсат беру](connections.md#allow-contributors-to-use-a-connection-for-exports) бөлімін қараңыз.</span><span class="sxs-lookup"><span data-stu-id="90d70-123">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="90d70-124">**Деректер құпиялығы мен сәйкестігін** растау үшін **Мен келісемін** параметрін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="90d70-124">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="90d70-125">RollWorks қызметіне қосылымды баптандыру үшін **Қосылу** түймешігін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="90d70-125">Select **Connect** to initialize the connection to RollWorks.</span></span>

1. <span data-ttu-id="90d70-126">**RollWorks қызметімен аутентификациялау** опциясын таңдаңыз және RollWorks қызметі үшін әкімші тіркелгі деректерін беріңіз.</span><span class="sxs-lookup"><span data-stu-id="90d70-126">Select **Authenticate with RollWorks** and provide your admin credentials for RollWorks.</span></span>

1. <span data-ttu-id="90d70-127">**Өзіңізді экспорт пайдаланушысы ретінде қосу** пәрменін таңдап, өзіңіздің Customer Insights тіркелгі деректерін ұсыныңыз.</span><span class="sxs-lookup"><span data-stu-id="90d70-127">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="90d70-128">Қосылымды аяқтау үшін **Сақтау** түймешігін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="90d70-128">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="90d70-129">Экспорттауды конфигурациялау</span><span class="sxs-lookup"><span data-stu-id="90d70-129">Configure an export</span></span>

<span data-ttu-id="90d70-130">Егер сіз осы түрдегі қосылымға қатынаса алсаңыз, сіз бұл экспорттауды конфигурациялай аласыз.</span><span class="sxs-lookup"><span data-stu-id="90d70-130">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="90d70-131">Қосымша ақпарат алу үшін [Экспорттауды конфигурациялау үшін қажет рұқсаттар](export-destinations.md#set-up-a-new-export) бөлімін қараңыз.</span><span class="sxs-lookup"><span data-stu-id="90d70-131">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="90d70-132">**Деректер** > **Экспорттау** тармағына өтіңіз.</span><span class="sxs-lookup"><span data-stu-id="90d70-132">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="90d70-133">Жаңа экспорттау жасау үшін **Мақсатты орын қосу** түймешігін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="90d70-133">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="90d70-134">**Экспорттауға арналған қосылым** өрісінде RollWorks бөлімінен қосылым таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="90d70-134">In the **Connection for export** field, choose a connection from the RollWorks section.</span></span> <span data-ttu-id="90d70-135">Егер сіз осы бөлімнің атын көрмесеңіз, сізге қолжетімді осы түрдегі қосылым жоқ.</span><span class="sxs-lookup"><span data-stu-id="90d70-135">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="90d70-136">**RollWorks жарнама беруші идентификаторын** [RollWorks Advertisable](https://help.adroll.com/hc/articles/212011838-Advertiser-Profiles) енгізіңіз.</span><span class="sxs-lookup"><span data-stu-id="90d70-136">Enter your **RollWorks Advertiser ID** [RollWorks Advertisable](https://help.adroll.com/hc/articles/212011838-Advertiser-Profiles).</span></span>

3. <span data-ttu-id="90d70-137">**Деректерді салыстыру** бөліміндегі **Электрондық пошта** өрісінде тұтынушының электрондық пошта мекенжайын көрсететін бірыңғай тұтынушы профиліндегі өрісті таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="90d70-137">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="90d70-138">Бұл RollWorks қызметіне сегменттерді экспорттау үшін қажет.</span><span class="sxs-lookup"><span data-stu-id="90d70-138">It's required to export segments to RollWorks.</span></span>

1. <span data-ttu-id="90d70-139">Экспорттау керек сегменттерді таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="90d70-139">Select the segments you want to export.</span></span> <span data-ttu-id="90d70-140">Кемінде 100 мүшесі бар сегментті таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="90d70-140">Select a segment with a least 100 members.</span></span> <span data-ttu-id="90d70-141">Кішірек сегменттерді экспорттау мүмкін емес.</span><span class="sxs-lookup"><span data-stu-id="90d70-141">You can't export smaller segments.</span></span> <span data-ttu-id="90d70-142">Сонымен қатар, экспортталатын сегменттің максималды мөлшері әр экспортқа 250000 мүшені құрайды.</span><span class="sxs-lookup"><span data-stu-id="90d70-142">Additionally the maximum size of a segment to export is 250'000 members per export.</span></span> 

1. <span data-ttu-id="90d70-143">**Сақтау** опциясын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="90d70-143">Select **Save**.</span></span>

<span data-ttu-id="90d70-144">Экспорттауды сақтау экспорттауды бірден іске қоспайды.</span><span class="sxs-lookup"><span data-stu-id="90d70-144">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="90d70-145">Экспорттау әр [жоспарланған жаңартумен](system.md#schedule-tab) іске қосылады.</span><span class="sxs-lookup"><span data-stu-id="90d70-145">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="90d70-146">Сондай-ақ [деректерді сұрау бойынша экспорттауға](export-destinations.md#run-exports-on-demand) болады.</span><span class="sxs-lookup"><span data-stu-id="90d70-146">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="90d70-147">Деректердің құпиялылығы мен сәйкестігі</span><span class="sxs-lookup"><span data-stu-id="90d70-147">Data privacy and compliance</span></span>

<span data-ttu-id="90d70-148">Деректерді RollWorks қызметіне тасымалдау үшін Dynamics 365 Customer Insights бағдарламасын қосқан кезде жеке деректер сияқты ықтимал құпия деректерді қоса алғанда, деректерді Dynamics 365 Customer Insights бағдарламасының үйлесімділік шегінен тыс тасымалдауға рұқсат бересіз.</span><span class="sxs-lookup"><span data-stu-id="90d70-148">When you enable Dynamics 365 Customer Insights to transmit data to RollWorks, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="90d70-149">Microsoft корпорациясы мұндай деректерді сіздің нұсқауыңыз бойынша жібереді, бірақ сіз RollWorks қызметінің кез келген құпиялылық немесе қауіпсіздік міндеттемелерінің орындалуына кепілдік беретініне жауаптысыз.</span><span class="sxs-lookup"><span data-stu-id="90d70-149">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that RollWorks meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="90d70-150">Қосымша ақпаратты [Microsoft құпиялық туралы мәлімдемесі](https://go.microsoft.com/fwlink/?linkid=396732) бөлімінен қараңыз.</span><span class="sxs-lookup"><span data-stu-id="90d70-150">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="90d70-151">Бұл функцияны тоқтату үшін бұл экспорттау мақсатын кез келген уақытта Dynamics 365 Customer Insights әкімшісі жоя алады.</span><span class="sxs-lookup"><span data-stu-id="90d70-151">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
