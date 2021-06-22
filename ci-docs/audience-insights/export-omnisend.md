---
title: Customer Insights деректерін Omnisend қызметіне экспорттау
description: Omnisend қызметі үшін қосылымды конфигурациялау және экспорттау жолы туралы ақпарат.
ms.date: 05/21/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 8bd692819fa8451ded5e74191ee717f81f87425d
ms.sourcegitcommit: 831765a55775d358447cb7ffa56f2c3b85459084
ms.translationtype: HT
ms.contentlocale: kk-KZ
ms.lasthandoff: 06/01/2021
ms.locfileid: "6124514"
---
# <a name="export-segments-to-omnisend-preview"></a><span data-ttu-id="6ad80-103">Сегменттерді Omnisend қызметіне экспорттау (алдын ала қарау нұсқасы)</span><span class="sxs-lookup"><span data-stu-id="6ad80-103">Export segments to Omnisend (preview)</span></span>

<span data-ttu-id="6ad80-104">Тұтынушылардың бірыңғай профильдерінің сегменттерін Omnisend қызметіне экспорттаңыз және оларды маркетингтік әрекеттер үшін пайдаланыңыз.</span><span class="sxs-lookup"><span data-stu-id="6ad80-104">Export segments of unified customer profiles to Omnisend and use them for marketing activities.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="6ad80-105">Алғышарттар</span><span class="sxs-lookup"><span data-stu-id="6ad80-105">Prerequisites</span></span>

-   <span data-ttu-id="6ad80-106">Сізде [Omnisend қызметінің тіркелгісі](https://www.omnisend.com/) және тиісті әкімші тіркелгі деректері бар.</span><span class="sxs-lookup"><span data-stu-id="6ad80-106">You have an [Omnisend account](https://www.omnisend.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="6ad80-107">Аудитория түсініктерінде [конфигурацияланған сегменттер](segments.md) бар.</span><span class="sxs-lookup"><span data-stu-id="6ad80-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="6ad80-108">Экспортталған сегменттердегі тұтынушылардың бірыңғай профильдері электрондық пошта мекенжайын көрсететін өрістен тұрады.</span><span class="sxs-lookup"><span data-stu-id="6ad80-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="6ad80-109">Белгілі шектеулер</span><span class="sxs-lookup"><span data-stu-id="6ad80-109">Known limitations</span></span>

- <span data-ttu-id="6ad80-110">Omnisend қызметіне бір экспорттаған кезде 1 миллион профильді экспорттауға болады және оны аяқтау 4 сағатқа созылуы мүмкін.</span><span class="sxs-lookup"><span data-stu-id="6ad80-110">You can export up to 1 million profiles per export to Omnisend and it can take up to 4 hours to complete.</span></span>
- <span data-ttu-id="6ad80-111">Omnisend қызметіне экспорттау сегменттермен шектеледі.</span><span class="sxs-lookup"><span data-stu-id="6ad80-111">Exporting to Omnisend is limited to segments.</span></span>
- <span data-ttu-id="6ad80-112">Omnisend қызметіне экспорттауға болатын профильдер саны Omnisend қызметін келісімшартқа байланысты.</span><span class="sxs-lookup"><span data-stu-id="6ad80-112">The number of profiles that you can export to Omnisend depends on your contract with Omnisend.</span></span>

## <a name="set-up-connection-to-omnisend"></a><span data-ttu-id="6ad80-113">Omnisend қызметіне қосылым орнату</span><span class="sxs-lookup"><span data-stu-id="6ad80-113">Set up connection to Omnisend</span></span>

1. <span data-ttu-id="6ad80-114">**Әкімші** > **Қосылымдар** тармағына өтіңіз.</span><span class="sxs-lookup"><span data-stu-id="6ad80-114">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="6ad80-115">**Қосылым қосу** түймешігін таңдаңыз және қосылымды конфигурациялау үшін **Omnisend** параметрін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="6ad80-115">Select **Add connection** and choose **Omnisend** to configure the connection.</span></span>

1. <span data-ttu-id="6ad80-116">**Көрсетілетін аты** өрісінде қосылымға оңай танылатын атау енгізіңіз.</span><span class="sxs-lookup"><span data-stu-id="6ad80-116">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="6ad80-117">Қосылым атауы мен түрі осы қосылымды сипаттайды.</span><span class="sxs-lookup"><span data-stu-id="6ad80-117">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="6ad80-118">Қосылымның мақсатын түсіндіретін атауды таңдауды ұсынамыз.</span><span class="sxs-lookup"><span data-stu-id="6ad80-118">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="6ad80-119">Осы қосылымды кім пайдалана алатынын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="6ad80-119">Choose who can use this connection.</span></span> <span data-ttu-id="6ad80-120">Әдепкі бойынша бұл тек әкімшілер.</span><span class="sxs-lookup"><span data-stu-id="6ad80-120">By default it's only administrators.</span></span> <span data-ttu-id="6ad80-121">Қосымша ақпарат алу үшін [Салымшыларға экспорттау үшін қосылымды пайдалануға рұқсат беру](connections.md#allow-contributors-to-use-a-connection-for-exports) бөлімін қараңыз.</span><span class="sxs-lookup"><span data-stu-id="6ad80-121">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="6ad80-122">[Omnisend API кілтін](https://support.omnisend.com/en/articles/1061890-generating-api-key) енгізіңіз.</span><span class="sxs-lookup"><span data-stu-id="6ad80-122">Enter your [Omnisend API key](https://support.omnisend.com/en/articles/1061890-generating-api-key).</span></span>

1. <span data-ttu-id="6ad80-123">**Деректер құпиялығы мен сәйкестігін** растау үшін **Мен келісемін** параметрін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="6ad80-123">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="6ad80-124">Omnisend қызметіне қосылымды баптандыру үшін **Қосылу** түймешігін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="6ad80-124">Select **Connect** to initialize the connection to Omnisend.</span></span>

1. <span data-ttu-id="6ad80-125">**Өзіңізді экспорт пайдаланушысы ретінде қосу** пәрменін таңдап, өзіңіздің Customer Insights тіркелгі деректерін ұсыныңыз.</span><span class="sxs-lookup"><span data-stu-id="6ad80-125">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="6ad80-126">Қосылымды аяқтау үшін **Сақтау** түймешігін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="6ad80-126">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="6ad80-127">Экспорттауды конфигурациялау</span><span class="sxs-lookup"><span data-stu-id="6ad80-127">Configure an export</span></span>

<span data-ttu-id="6ad80-128">Егер сіз осы түрдегі қосылымға қатынаса алсаңыз, сіз бұл экспорттауды конфигурациялай аласыз.</span><span class="sxs-lookup"><span data-stu-id="6ad80-128">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="6ad80-129">Қосымша ақпарат алу үшін [Экспорттауды конфигурациялау үшін қажет рұқсаттар](export-destinations.md#set-up-a-new-export) бөлімін қараңыз.</span><span class="sxs-lookup"><span data-stu-id="6ad80-129">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="6ad80-130">**Деректер** > **Экспорттау** тармағына өтіңіз.</span><span class="sxs-lookup"><span data-stu-id="6ad80-130">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="6ad80-131">Жаңа экспорттау жасау үшін **Мақсатты орын қосу** түймешігін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="6ad80-131">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="6ad80-132">**Экспорттауға арналған қосылым** өрісінде Omnisend бөлімінен қосылым таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="6ad80-132">In the **Connection for export** field, choose a connection from the Omnisend section.</span></span> <span data-ttu-id="6ad80-133">Егер сіз осы бөлімнің атын көрмесеңіз, сізге қолжетімді осы түрдегі қосылым жоқ.</span><span class="sxs-lookup"><span data-stu-id="6ad80-133">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="6ad80-134">**Деректерді салыстыру** бөліміндегі **Электрондық пошта** өрісінде тұтынушының электрондық пошта мекенжайын көрсететін бірыңғай тұтынушы профиліндегі өрісті таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="6ad80-134">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="6ad80-135">Бұл Omnisend қызметіне сегменттерді экспорттау үшін қажет.</span><span class="sxs-lookup"><span data-stu-id="6ad80-135">It's required to export segments to Omnisend.</span></span> <span data-ttu-id="6ad80-136">Қажет болса, жекелендірілген электрондық пошта хабарларын жасау үшін аты, тегі, мекенжайы, ел/аймақ, штат және пошталық индексті конфигурациялауға болады.</span><span class="sxs-lookup"><span data-stu-id="6ad80-136">Optionally, you can export First name, Last name, Address, Country/Region, State, City, and Post Code to create more personalized emails.</span></span> <span data-ttu-id="6ad80-137">Осы өрістерді салыстыру үшін **Төлсипат қосу** пәрменін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="6ad80-137">Select **Add attribute** to map these fields.</span></span>

1. <span data-ttu-id="6ad80-138">**Сақтау** опциясын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="6ad80-138">Select **Save**.</span></span>

<span data-ttu-id="6ad80-139">Экспорттауды сақтау экспорттауды бірден іске қоспайды.</span><span class="sxs-lookup"><span data-stu-id="6ad80-139">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="6ad80-140">Экспорттау әр [жоспарланған жаңартумен](system.md#schedule-tab) іске қосылады.</span><span class="sxs-lookup"><span data-stu-id="6ad80-140">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="6ad80-141">Сондай-ақ [деректерді сұрау бойынша экспорттауға](export-destinations.md#run-exports-on-demand) болады.</span><span class="sxs-lookup"><span data-stu-id="6ad80-141">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="6ad80-142">Деректердің құпиялылығы мен сәйкестігі</span><span class="sxs-lookup"><span data-stu-id="6ad80-142">Data privacy and compliance</span></span>

<span data-ttu-id="6ad80-143">Деректерді Ommisend қызметіне тасымалдау үшін Dynamics 365 Customer Insights бағдарламасын қосқан кезде жеке деректер сияқты ықтимал құпия деректерді қоса алғанда, деректерді Dynamics 365 Customer Insights бағдарламасының үйлесімділік шегінен тыс тасымалдауға рұқсат бересіз.</span><span class="sxs-lookup"><span data-stu-id="6ad80-143">When you enable Dynamics 365 Customer Insights to transmit data to Ommisend, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="6ad80-144">Microsoft корпорациясы мұндай деректерді сіздің нұсқауыңыз бойынша жібереді, бірақ сіз Ommisend қызметінің кез келген құпиялылық немесе қауіпсіздік міндеттемелерінің орындалуына кепілдік беретініне жауаптысыз.</span><span class="sxs-lookup"><span data-stu-id="6ad80-144">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Omnisend meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="6ad80-145">Қосымша ақпаратты [Microsoft құпиялық туралы мәлімдемесі](https://go.microsoft.com/fwlink/?linkid=396732) бөлімінен қараңыз.</span><span class="sxs-lookup"><span data-stu-id="6ad80-145">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="6ad80-146">Бұл функцияны тоқтату үшін бұл экспорттау мақсатын кез келген уақытта Dynamics 365 Customer Insights әкімшісі жоя алады.</span><span class="sxs-lookup"><span data-stu-id="6ad80-146">Your Dynamics 365 Customer Insights administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
