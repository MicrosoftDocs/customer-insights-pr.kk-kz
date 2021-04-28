---
title: Customer Insights деректерін Autopilot нысанына экспорттау
description: Autopilot қызметі үшін қосылымды конфигурациялау және экспорттау жолы туралы ақпарат.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: e320a48d5b7c35b530e3a38567b226b804879e4e
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: kk-KZ
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760150"
---
# <a name="export-segments-to-autopilot-preview"></a><span data-ttu-id="54a2b-103">Сегменттерді Autopilot қызметіне экспорттау (алдын ала қарау нұсқасы)</span><span class="sxs-lookup"><span data-stu-id="54a2b-103">Export segments to Autopilot (preview)</span></span>

<span data-ttu-id="54a2b-104">Тұтынушылардың бірыңғай профильдерінің сегменттерін Autopilot жүйесіне экспорттап, оларды Autopilot жүйесіндегі электрондық пошта маркетингі үшін пайдаланыңыз.</span><span class="sxs-lookup"><span data-stu-id="54a2b-104">Export segments of unified customer profiles to Autopilot and use them for email marketing in Autopilot.</span></span> 

## <a name="prerequisites-for-a-connection"></a><span data-ttu-id="54a2b-105">Қосылым алғышарттары</span><span class="sxs-lookup"><span data-stu-id="54a2b-105">Prerequisites for a connection</span></span>

-   <span data-ttu-id="54a2b-106">Сізде [Autopilot тіркелгісі](https://www.autopilothq.com/) және тиісті әкімшінің тіркелгі деректері бар.</span><span class="sxs-lookup"><span data-stu-id="54a2b-106">You have an [Autopilot account](https://www.autopilothq.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="54a2b-107">Аудитория түсініктерінде [конфигурацияланған сегменттер](segments.md) бар.</span><span class="sxs-lookup"><span data-stu-id="54a2b-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="54a2b-108">Экспортталған сегменттердегі тұтынушылардың бірыңғай профильдері электрондық пошта мекенжайын көрсететін өрістен тұрады.</span><span class="sxs-lookup"><span data-stu-id="54a2b-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="54a2b-109">Белгілі шектеулер</span><span class="sxs-lookup"><span data-stu-id="54a2b-109">Known limitations</span></span>

- <span data-ttu-id="54a2b-110">Autopilot платформасына жалпы 100000-ға дейін профильді экспорттай аласыз.</span><span class="sxs-lookup"><span data-stu-id="54a2b-110">You can export up to 100'000 profiles in total to Autopilot.</span></span>
- <span data-ttu-id="54a2b-111">Autopilot нысанына экспорттау тек сегменттермен шектеледі.</span><span class="sxs-lookup"><span data-stu-id="54a2b-111">Exporting to Autopilot is limited to segments.</span></span>
- <span data-ttu-id="54a2b-112">Autopilot жүйесіне 100000 дейін профильді экспорттау бірнеше сағатқа созылуы мүмкін.</span><span class="sxs-lookup"><span data-stu-id="54a2b-112">Exporting up to 100'000 profiles to Autopilot can take up to a few hours to complete.</span></span> 
- <span data-ttu-id="54a2b-113">Autopilot нысанына экспорттауға болатын профильдер саны Autopilot нысанымен жасалған келісімшартқа байланысты және шектеулі.</span><span class="sxs-lookup"><span data-stu-id="54a2b-113">The number of profiles that you can export to Autopilot is dependent and limited on your contract with Autopilot.</span></span>

## <a name="set-up-connection-to-autopilot"></a><span data-ttu-id="54a2b-114">Autopilot қызметіне қосылым орнату</span><span class="sxs-lookup"><span data-stu-id="54a2b-114">Set up connection to Autopilot</span></span>

1. <span data-ttu-id="54a2b-115">**Әкімші** > **Қосылымдар** тармағына өтіңіз.</span><span class="sxs-lookup"><span data-stu-id="54a2b-115">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="54a2b-116">**Қосылым қосу** түймешігін таңдаңыз және қосылымды конфигурациялау үшін **Autopilot** параметрін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="54a2b-116">Select **Add connection** and choose **Autopilot** to configure the connection.</span></span>

1. <span data-ttu-id="54a2b-117">**Көрсетілетін аты** өрісінде қосылымға оңай танылатын атау енгізіңіз.</span><span class="sxs-lookup"><span data-stu-id="54a2b-117">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="54a2b-118">Қосылым атауы мен түрі осы қосылымды сипаттайды.</span><span class="sxs-lookup"><span data-stu-id="54a2b-118">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="54a2b-119">Қосылымның мақсатын түсіндіретін атауды таңдауды ұсынамыз.</span><span class="sxs-lookup"><span data-stu-id="54a2b-119">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="54a2b-120">Осы қосылымды кім пайдалана алатынын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="54a2b-120">Choose who can use this connection.</span></span> <span data-ttu-id="54a2b-121">Егер сіз ешқандай әрекет жасамасаңыз, әдепкі бойынша Әкімшілер болады.</span><span class="sxs-lookup"><span data-stu-id="54a2b-121">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="54a2b-122">Қосымша ақпарат алу үшін [Салымшыларға экспорттау үшін қосылымды пайдалануға рұқсат беру](connections.md#allow-contributors-to-use-a-connection-for-exports) бөлімін қараңыз.</span><span class="sxs-lookup"><span data-stu-id="54a2b-122">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

3. <span data-ttu-id="54a2b-123">[Autopilot API кілтін](https://autopilot.docs.apiary.io/#) енгізіңіз.</span><span class="sxs-lookup"><span data-stu-id="54a2b-123">Enter your [Autopilot API key](https://autopilot.docs.apiary.io/#).</span></span>

1. <span data-ttu-id="54a2b-124">**Деректер құпиялығы мен сәйкестігін** растау үшін **Мен келісемін** параметрін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="54a2b-124">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="54a2b-125">Autopilot қосылымын баптандыру үшін **Қосылу** пәрменін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="54a2b-125">Select **Connect** to initialize the connection to Autopilot.</span></span>

1. <span data-ttu-id="54a2b-126">**Өзіңізді экспорт пайдаланушысы ретінде қосу** пәрменін таңдап, өзіңіздің Customer Insights тіркелгі деректерін ұсыныңыз.</span><span class="sxs-lookup"><span data-stu-id="54a2b-126">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="54a2b-127">Қосылымды аяқтау үшін **Сақтау** түймешігін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="54a2b-127">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="54a2b-128">Экспорттауды конфигурациялау</span><span class="sxs-lookup"><span data-stu-id="54a2b-128">Configure an export</span></span>

<span data-ttu-id="54a2b-129">Егер сіз осы түрдегі қосылымға қатынаса алсаңыз, сіз бұл экспорттауды конфигурациялай аласыз.</span><span class="sxs-lookup"><span data-stu-id="54a2b-129">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="54a2b-130">Қосымша ақпарат алу үшін [Экспорттауды конфигурациялау үшін қажет рұқсаттар](export-destinations.md#set-up-a-new-export) бөлімін қараңыз.</span><span class="sxs-lookup"><span data-stu-id="54a2b-130">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="54a2b-131">**Деректер** > **Экспорттау** тармағына өтіңіз.</span><span class="sxs-lookup"><span data-stu-id="54a2b-131">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="54a2b-132">Жаңа экспорттау жасау үшін **Мақсатты орын қосу** түймешігін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="54a2b-132">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="54a2b-133">**Экспорттауға арналған қосылым** өрісінде Autopilot бөлімінен қосылым таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="54a2b-133">In the **Connection for export** field, choose a connection from the Autopilot section.</span></span> <span data-ttu-id="54a2b-134">Егер сіз осы бөлімнің атын көрмесеңіз, сізге қолжетімді осы түрдегі қосылым жоқ.</span><span class="sxs-lookup"><span data-stu-id="54a2b-134">If you don't see this section name, there are no connections of this type available to you.</span></span>

3. <span data-ttu-id="54a2b-135">**Деректерді салыстыру** бөліміндегі **Электрондық пошта** өрісінде тұтынушының электрондық пошта мекенжайын көрсететін бірыңғай тұтынушы профиліндегі өрісті таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="54a2b-135">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="54a2b-136">**Аты**, **Тегі** секілді басқа қосымша өрістер үшін сол қадамдарды қайталаңыз.</span><span class="sxs-lookup"><span data-stu-id="54a2b-136">Repeat the same steps for other optional fields such as **First name**, **Last name**.</span></span>

1. <span data-ttu-id="54a2b-137">Экспорттау керек сегменттерді таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="54a2b-137">Select the segments you want to export.</span></span> <span data-ttu-id="54a2b-138">Біз Autopilot жүйесіне **100000-нан астам тұтынушы профильдерін экспорттамауға кеңес береміз**.</span><span class="sxs-lookup"><span data-stu-id="54a2b-138">We strongly **recommend to not export more than 100'000 customer profiles in total** to Autopilot.</span></span> 

1. <span data-ttu-id="54a2b-139">**Сақтау** опциясын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="54a2b-139">Select **Save**.</span></span>

<span data-ttu-id="54a2b-140">Экспорттауды сақтау экспорттауды бірден іске қоспайды.</span><span class="sxs-lookup"><span data-stu-id="54a2b-140">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="54a2b-141">Экспорттау әр [жоспарланған жаңартумен](system.md#schedule-tab) іске қосылады.</span><span class="sxs-lookup"><span data-stu-id="54a2b-141">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="54a2b-142">Сондай-ақ [деректерді сұрау бойынша экспорттауға](export-destinations.md#run-exports-on-demand) болады.</span><span class="sxs-lookup"><span data-stu-id="54a2b-142">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="54a2b-143">Деректердің құпиялылығы мен сәйкестігі</span><span class="sxs-lookup"><span data-stu-id="54a2b-143">Data privacy and compliance</span></span>

<span data-ttu-id="54a2b-144">Деректерді Autopilot платформасына жіберу үшін Dynamics 365 Customer Insights бағдарламасын қосқан кезде, Dynamics 365 Customer Insights талаптарына сәйкестік шекарасынан тыс деректерді, соның ішінде жеке деректер сияқты ықтимал құпия деректерді беруге мүмкіндік бересіз.</span><span class="sxs-lookup"><span data-stu-id="54a2b-144">When you enable Dynamics 365 Customer Insights to transmit data to Autopilot, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="54a2b-145">Microsoft мұндай деректерді сіздің нұсқауыңыз бойынша тасымалдайды, бірақ Autopilot кез келген құпиялылық немесе қауіпсіздік міндеттемелеріне сәйкес келуіне жауап бересіз.</span><span class="sxs-lookup"><span data-stu-id="54a2b-145">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Autopilot meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="54a2b-146">Қосымша ақпаратты [Microsoft құпиялық туралы мәлімдемесі](https://go.microsoft.com/fwlink/?linkid=396732) бөлімінен қараңыз.</span><span class="sxs-lookup"><span data-stu-id="54a2b-146">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="54a2b-147">Бұл функцияны тоқтату үшін бұл экспорттау мақсатын кез келген уақытта Dynamics 365 Customer Insights әкімшісі жоя алады.</span><span class="sxs-lookup"><span data-stu-id="54a2b-147">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
