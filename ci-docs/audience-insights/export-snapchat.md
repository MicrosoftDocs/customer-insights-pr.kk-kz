---
title: Customer Insights деректерін Snapchat қызметіне экспорттау
description: Snapchat қызметі үшін қосылымды конфигурациялау және экспорттау жолы туралы ақпарат.
ms.date: 03/22/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: d3dae7f0fef1fc3792c90c8ac0d3b037f5c0923d
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: kk-KZ
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760570"
---
# <a name="export-segment-lists-to-snapchat-preview"></a><span data-ttu-id="57544-103">Сегмент тізімдерін Snapchat қызметіне экспорттау (алдын ала қарау нұсқасы)</span><span class="sxs-lookup"><span data-stu-id="57544-103">Export segment lists to Snapchat (preview)</span></span>

<span data-ttu-id="57544-104">Тұтынушылардың бірыңғай профильдерінің сегменттерін Snapchat қызметіне экспорттаңыз және оларды жарнама үшін пайдаланыңыз.</span><span class="sxs-lookup"><span data-stu-id="57544-104">Export segments of unified customer profiles to Snapchat and use them for advertising.</span></span> 

## <a name="prerequisites-for-a-connection"></a><span data-ttu-id="57544-105">Қосылым алғышарттары</span><span class="sxs-lookup"><span data-stu-id="57544-105">Prerequisites for a connection</span></span>

-   <span data-ttu-id="57544-106">Сізде [Snapchat бизнес тіркелгісі](https://business.snapchat.com/), [Snapchat жарнама тіркелгісі](https://ads.snapchat.com/) және тиісті әкімші тіркелгі деректері бар.</span><span class="sxs-lookup"><span data-stu-id="57544-106">You have a [Snapchat Business account](https://business.snapchat.com/), a [Snapchat Ads account](https://ads.snapchat.com/), and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="57544-107">Аудитория түсініктерінде [конфигурацияланған сегменттер](segments.md) бар.</span><span class="sxs-lookup"><span data-stu-id="57544-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="57544-108">Экспортталған сегменттердегі тұтынушылардың бірыңғай профильдері электрондық пошта мекенжайын көрсететін өрістен тұрады.</span><span class="sxs-lookup"><span data-stu-id="57544-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="57544-109">Белгілі шектеулер</span><span class="sxs-lookup"><span data-stu-id="57544-109">Known limitations</span></span>

- <span data-ttu-id="57544-110">Snapchat қызметіне экспорттау сегменттермен шектеледі.</span><span class="sxs-lookup"><span data-stu-id="57544-110">Exporting to Snapchat is limited to segments.</span></span>
- <span data-ttu-id="57544-111">Snapchat қызметіне 1 миллионға дейінгі профильді экспорттауды аяқтау 15 минутқа созылуы мүмкін.</span><span class="sxs-lookup"><span data-stu-id="57544-111">Exporting up to 1 million profiles to Snapchat can take up to 15 minutes to complete.</span></span> 

## <a name="set-up-connection-to-snapchat"></a><span data-ttu-id="57544-112">Snapchat қызметіне қосылым орнату</span><span class="sxs-lookup"><span data-stu-id="57544-112">Set up connection to Snapchat</span></span>

1. <span data-ttu-id="57544-113">**Әкімші** > **Қосылымдар** тармағына өтіңіз.</span><span class="sxs-lookup"><span data-stu-id="57544-113">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="57544-114">**Қосылым қосу** түймешігін таңдаңыз және қосылымды конфигурациялау үшін **Snapchat** параметрін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="57544-114">Select **Add connection** and choose **Snapchat** to configure the connection.</span></span>

1. <span data-ttu-id="57544-115">**Көрсетілетін аты** өрісінде қосылымға оңай танылатын атау енгізіңіз.</span><span class="sxs-lookup"><span data-stu-id="57544-115">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="57544-116">Қосылым атауы мен түрі осы қосылымды сипаттайды.</span><span class="sxs-lookup"><span data-stu-id="57544-116">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="57544-117">Қосылымның мақсатын түсіндіретін атауды таңдауды ұсынамыз.</span><span class="sxs-lookup"><span data-stu-id="57544-117">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="57544-118">Осы қосылымды кім пайдалана алатынын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="57544-118">Choose who can use this connection.</span></span> <span data-ttu-id="57544-119">Егер сіз ешқандай әрекет жасамасаңыз, әдепкі бойынша Әкімшілер болады.</span><span class="sxs-lookup"><span data-stu-id="57544-119">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="57544-120">Қосымша ақпарат алу үшін [Салымшыларға экспорттау үшін қосылымды пайдалануға рұқсат беру](connections.md#allow-contributors-to-use-a-connection-for-exports) бөлімін қараңыз.</span><span class="sxs-lookup"><span data-stu-id="57544-120">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="57544-121">**Деректер құпиялығы мен сәйкестігін** растау үшін **Мен келісемін** параметрін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="57544-121">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="57544-122">Snapchat қызметіне қосылымды баптандыру үшін **Қосылу** түймешігін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="57544-122">Select **Connect** to initialize the connection to Snapchat.</span></span>

1. <span data-ttu-id="57544-123">**Snapchat қызметімен аутентификациялау** опциясын таңдаңыз және Snapchat қызметі үшін әкімші тіркелгі деректерін беріңіз.</span><span class="sxs-lookup"><span data-stu-id="57544-123">Select **Authenticate with Snapchat** and provide your admin credentials for Snapchat.</span></span> 

1. <span data-ttu-id="57544-124">**Өзіңізді экспорт пайдаланушысы ретінде қосу** пәрменін таңдап, өзіңіздің Customer Insights тіркелгі деректерін ұсыныңыз.</span><span class="sxs-lookup"><span data-stu-id="57544-124">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="57544-125">Қосылымды аяқтау үшін **Сақтау** түймешігін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="57544-125">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="57544-126">Экспорттауды конфигурациялау</span><span class="sxs-lookup"><span data-stu-id="57544-126">Configure an export</span></span>

<span data-ttu-id="57544-127">Егер сіз осы түрдегі қосылымға қатынаса алсаңыз, сіз бұл экспорттауды конфигурациялай аласыз.</span><span class="sxs-lookup"><span data-stu-id="57544-127">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="57544-128">Қосымша ақпарат алу үшін [Экспорттауды конфигурациялау үшін қажет рұқсаттар](export-destinations.md#set-up-a-new-export) бөлімін қараңыз.</span><span class="sxs-lookup"><span data-stu-id="57544-128">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="57544-129">**Деректер** > **Экспорттау** тармағына өтіңіз.</span><span class="sxs-lookup"><span data-stu-id="57544-129">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="57544-130">Жаңа экспорттау жасау үшін **Мақсатты орын қосу** түймешігін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="57544-130">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="57544-131">**Экспорттауға арналған қосылым** өрісінде Snapchat бөлімінен қосылым таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="57544-131">In the **Connection for export** field, choose a connection from the Snapchat section.</span></span> <span data-ttu-id="57544-132">Егер сіз осы бөлімнің атын көрмесеңіз, сізге қолжетімді осы түрдегі қосылым жоқ.</span><span class="sxs-lookup"><span data-stu-id="57544-132">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="57544-133">[**Snapchat аудитория идентификаторын**](https://businesshelp.snapchat.com/s/article/custom-audiences) енгізіңіз.</span><span class="sxs-lookup"><span data-stu-id="57544-133">Enter the [**Snapchat Audience ID**](https://businesshelp.snapchat.com/s/article/custom-audiences).</span></span>

1. <span data-ttu-id="57544-134">**Деректерді салыстыру** бөліміндегі **Электрондық пошта** өрісінде тұтынушының электрондық пошта мекенжайын көрсететін бірыңғай тұтынушы профиліндегі өрісті таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="57544-134">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="57544-135">Бұл Snapchat қызметіне сегменттерді экспорттау үшін қажет.</span><span class="sxs-lookup"><span data-stu-id="57544-135">It's required to export segments to Snapchat.</span></span>

1. <span data-ttu-id="57544-136">Экспорттау керек сегменттерді таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="57544-136">Select the segments you want to export.</span></span> 

1. <span data-ttu-id="57544-137">**Сақтау** опциясын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="57544-137">Select **Save**.</span></span>

<span data-ttu-id="57544-138">Экспорттауды сақтау экспорттауды бірден іске қоспайды.</span><span class="sxs-lookup"><span data-stu-id="57544-138">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="57544-139">Экспорттау әр [жоспарланған жаңартумен](system.md#schedule-tab) іске қосылады.</span><span class="sxs-lookup"><span data-stu-id="57544-139">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="57544-140">Сондай-ақ [деректерді сұрау бойынша экспорттауға](export-destinations.md#run-exports-on-demand) болады.</span><span class="sxs-lookup"><span data-stu-id="57544-140">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="57544-141">Деректердің құпиялылығы мен сәйкестігі</span><span class="sxs-lookup"><span data-stu-id="57544-141">Data privacy and compliance</span></span>

<span data-ttu-id="57544-142">Деректерді Snapchat қызметіне тасымалдау үшін Dynamics 365 Customer Insights бағдарламасын қосқан кезде жеке деректер сияқты ықтимал құпия деректерді қоса алғанда, деректерді Dynamics 365 Customer Insights бағдарламасының үйлесімділік шегінен тыс тасымалдауға рұқсат бересіз.</span><span class="sxs-lookup"><span data-stu-id="57544-142">When you enable Dynamics 365 Customer Insights to transmit data to Snapchat, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="57544-143">Microsoft корпорациясы мұндай деректерді сіздің нұсқауыңыз бойынша жібереді, бірақ сіз Snapchat қызметінің кез-келген құпиялылық немесе қауіпсіздік міндеттемелерінің орындалуына кепілдік беретініне жауаптысыз.</span><span class="sxs-lookup"><span data-stu-id="57544-143">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Snapchat meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="57544-144">Қосымша ақпаратты [Microsoft құпиялық туралы мәлімдемесі](https://go.microsoft.com/fwlink/?linkid=396732) бөлімінен қараңыз.</span><span class="sxs-lookup"><span data-stu-id="57544-144">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="57544-145">Бұл функцияны тоқтату үшін бұл экспорттау мақсатын кез келген уақытта Dynamics 365 Customer Insights әкімшісі жоя алады.</span><span class="sxs-lookup"><span data-stu-id="57544-145">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
