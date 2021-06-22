---
title: Customer Insights деректерін AdRoll платформасына экспорттау
description: AdRoll қызметі үшін қосылымды конфигурациялау және экспорттау жолы туралы ақпарат.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: dbebc3ee3978ca6ee9d1ad1c15c226479876709f
ms.sourcegitcommit: 831765a55775d358447cb7ffa56f2c3b85459084
ms.translationtype: HT
ms.contentlocale: kk-KZ
ms.lasthandoff: 06/01/2021
ms.locfileid: "6124372"
---
# <a name="export-segments-to-adroll-preview"></a><span data-ttu-id="2f992-103">Сегменттерді AdRoll қызметіне экспорттау (алдын ала қарау нұсқасы)</span><span class="sxs-lookup"><span data-stu-id="2f992-103">Export segments to AdRoll (preview)</span></span>

<span data-ttu-id="2f992-104">Тұтынушының бірыңғай профильдерінің сегменттерін AdRoll платформасына экспорттап, оларды жарнама үшін пайдаланыңыз.</span><span class="sxs-lookup"><span data-stu-id="2f992-104">Export segments of unified customer profiles to AdRoll and use them for advertising.</span></span> 

## <a name="prerequisites-for-a-connection"></a><span data-ttu-id="2f992-105">Қосылым алғышарттары</span><span class="sxs-lookup"><span data-stu-id="2f992-105">Prerequisites for a connection</span></span>

-   <span data-ttu-id="2f992-106">Сізде [AdRoll тіркелгісі](https://www.adroll.com/) және тиісті әкімшінің тіркелгі деректері бар.</span><span class="sxs-lookup"><span data-stu-id="2f992-106">You have an [AdRoll account](https://www.adroll.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="2f992-107">Аудитория түсініктерінде [конфигурацияланған сегменттер](segments.md) бар.</span><span class="sxs-lookup"><span data-stu-id="2f992-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="2f992-108">Экспортталған сегменттердегі тұтынушылардың бірыңғай профильдері электрондық пошта мекенжайын көрсететін өрістен тұрады.</span><span class="sxs-lookup"><span data-stu-id="2f992-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="2f992-109">Белгілі шектеулер</span><span class="sxs-lookup"><span data-stu-id="2f992-109">Known limitations</span></span>

- <span data-ttu-id="2f992-110">AdRoll платформасында бір экспорттауда 250000 профильге дейін экспорттауға болады.</span><span class="sxs-lookup"><span data-stu-id="2f992-110">You can export up to 250'000 profiles in per export to AdRoll.</span></span>
- <span data-ttu-id="2f992-111">AdRoll платформасына сегменттерді 100-ден кем профильмен экспорттау мүмкін емес.</span><span class="sxs-lookup"><span data-stu-id="2f992-111">You can't export segments with fewer than 100 profiles to AdRoll.</span></span> 
- <span data-ttu-id="2f992-112">AdRoll нысанына экспорттау тек сегменттермен шектеледі.</span><span class="sxs-lookup"><span data-stu-id="2f992-112">Exporting to AdRoll is limited to segments.</span></span>
- <span data-ttu-id="2f992-113">AdRoll платформасына 250000-ға дейін профильді экспорттау 10 минутқа дейін созылуы мүмкін.</span><span class="sxs-lookup"><span data-stu-id="2f992-113">Exporting up to 250'000 profiles to AdRoll can take up to 10 minutes to complete.</span></span> 
- <span data-ttu-id="2f992-114">AdRoll платформасына экспорттауға болатын профильдер саны AdRoll платформасымен жасалған келісімшартқа байланысты және шектеулі.</span><span class="sxs-lookup"><span data-stu-id="2f992-114">The number of profiles that you can export to AdRoll is dependent and limited on your contract with AdRoll.</span></span>

## <a name="set-up-connection-to-adroll"></a><span data-ttu-id="2f992-115">AdRoll қызметіне қосылым орнату</span><span class="sxs-lookup"><span data-stu-id="2f992-115">Set up connection to AdRoll</span></span>

1. <span data-ttu-id="2f992-116">**Әкімші** > **Қосылымдар** тармағына өтіңіз.</span><span class="sxs-lookup"><span data-stu-id="2f992-116">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="2f992-117">**Қосылым қосу** түймешігін таңдаңыз және қосылымды конфигурациялау үшін **AdRoll** параметрін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="2f992-117">Select **Add connection** and choose **AdRoll** to configure the connection.</span></span>

1. <span data-ttu-id="2f992-118">**Көрсетілетін аты** өрісінде қосылымға оңай танылатын атау енгізіңіз.</span><span class="sxs-lookup"><span data-stu-id="2f992-118">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="2f992-119">Қосылым атауы мен түрі осы қосылымды сипаттайды.</span><span class="sxs-lookup"><span data-stu-id="2f992-119">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="2f992-120">Қосылымның мақсатын түсіндіретін атауды таңдауды ұсынамыз.</span><span class="sxs-lookup"><span data-stu-id="2f992-120">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="2f992-121">Осы қосылымды кім пайдалана алатынын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="2f992-121">Choose who can use this connection.</span></span> <span data-ttu-id="2f992-122">Егер сіз ешқандай әрекет жасамасаңыз, әдепкі бойынша Әкімшілер болады.</span><span class="sxs-lookup"><span data-stu-id="2f992-122">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="2f992-123">Қосымша ақпарат алу үшін [Салымшыларға экспорттау үшін қосылымды пайдалануға рұқсат беру](connections.md#allow-contributors-to-use-a-connection-for-exports) бөлімін қараңыз.</span><span class="sxs-lookup"><span data-stu-id="2f992-123">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="2f992-124">**Деректер құпиялығы мен сәйкестігін** растау үшін **Мен келісемін** параметрін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="2f992-124">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="2f992-125">AdRoll қосылымын баптандыру үшін **Қосылу** пәрменін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="2f992-125">Select **Connect** to initialize the connection to AdRoll.</span></span>

1. <span data-ttu-id="2f992-126">**AdRoll көмегімен аутентификациялау** пәрменін таңдап, AdRoll платформасына арналған әкімшінің тіркелгі деректерін ұсыныңыз.</span><span class="sxs-lookup"><span data-stu-id="2f992-126">Select **Authenticate with AdRoll** and provide your admin credentials for AdRoll.</span></span> 

1. <span data-ttu-id="2f992-127">**Өзіңізді экспорт пайдаланушысы ретінде қосу** пәрменін таңдап, өзіңіздің Customer Insights тіркелгі деректерін ұсыныңыз.</span><span class="sxs-lookup"><span data-stu-id="2f992-127">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="2f992-128">Қосылымды аяқтау үшін **Сақтау** түймешігін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="2f992-128">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="2f992-129">Экспорттауды конфигурациялау</span><span class="sxs-lookup"><span data-stu-id="2f992-129">Configure an export</span></span>

<span data-ttu-id="2f992-130">Егер сіз осы түрдегі қосылымға қатынаса алсаңыз, сіз бұл экспорттауды конфигурациялай аласыз.</span><span class="sxs-lookup"><span data-stu-id="2f992-130">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="2f992-131">Қосымша ақпарат алу үшін [Экспорттауды конфигурациялау үшін қажет рұқсаттар](export-destinations.md#set-up-a-new-export) бөлімін қараңыз.</span><span class="sxs-lookup"><span data-stu-id="2f992-131">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="2f992-132">**Деректер** > **Экспорттау** тармағына өтіңіз.</span><span class="sxs-lookup"><span data-stu-id="2f992-132">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="2f992-133">Жаңа экспорттау жасау үшін **Мақсатты орын қосу** түймешігін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="2f992-133">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="2f992-134">**Экспорттауға арналған қосылым** өрісінде AdRoll бөлімінен қосылым таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="2f992-134">In the **Connection for export** field, choose a connection from the AdRoll section.</span></span> <span data-ttu-id="2f992-135">Егер сіз осы бөлімнің атын көрмесеңіз, сізге қолжетімді осы түрдегі қосылым жоқ.</span><span class="sxs-lookup"><span data-stu-id="2f992-135">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="2f992-136">**AdRoll жарнама беруші идентификаторын** енгізіңіз Қосымша ақпарат алу үшін [AdRoll жарнама берушілерінің профильдері](https://help.adroll.com/hc/articles/212011838-Advertiser-Profiles) бөлімін қараңыз.</span><span class="sxs-lookup"><span data-stu-id="2f992-136">Enter your **AdRoll Advertiser ID** For more information, see [AdRoll Advertiser Profiles](https://help.adroll.com/hc/articles/212011838-Advertiser-Profiles).</span></span>

3. <span data-ttu-id="2f992-137">**Деректерді салыстыру** бөліміндегі **Электрондық пошта** өрісінде тұтынушының электрондық пошта мекенжайын көрсететін бірыңғай тұтынушы профиліндегі өрісті таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="2f992-137">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="2f992-138">Сегменттерді AdRoll платформасына экспорттау қажет.</span><span class="sxs-lookup"><span data-stu-id="2f992-138">It's required to export segments to AdRoll.</span></span>

1. <span data-ttu-id="2f992-139">Экспорттау керек сегменттерді таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="2f992-139">Select the segments you want to export.</span></span> <span data-ttu-id="2f992-140">Кемінде 100 мүшесі бар сегментті таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="2f992-140">Select a segment with a least 100 members.</span></span> <span data-ttu-id="2f992-141">Кішірек сегменттерді экспорттау мүмкін емес.</span><span class="sxs-lookup"><span data-stu-id="2f992-141">You can't export smaller segments.</span></span> <span data-ttu-id="2f992-142">Сонымен қатар, экспортталатын сегменттің максималды мөлшері әр экспортқа 250000 мүшені құрайды.</span><span class="sxs-lookup"><span data-stu-id="2f992-142">Additionally the maximum size of a segment to export is 250'000 members per export.</span></span> 

1. <span data-ttu-id="2f992-143">**Сақтау** опциясын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="2f992-143">Select **Save**.</span></span>

<span data-ttu-id="2f992-144">Экспорттауды сақтау экспорттауды бірден іске қоспайды.</span><span class="sxs-lookup"><span data-stu-id="2f992-144">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="2f992-145">Экспорттау әр [жоспарланған жаңартумен](system.md#schedule-tab) іске қосылады.</span><span class="sxs-lookup"><span data-stu-id="2f992-145">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="2f992-146">Сондай-ақ [деректерді сұрау бойынша экспорттауға](export-destinations.md#run-exports-on-demand) болады.</span><span class="sxs-lookup"><span data-stu-id="2f992-146">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="2f992-147">Деректердің құпиялылығы мен сәйкестігі</span><span class="sxs-lookup"><span data-stu-id="2f992-147">Data privacy and compliance</span></span>

<span data-ttu-id="2f992-148">Деректерді AdRoll платформасына жіберу үшін Dynamics 365 Customer Insights бағдарламасын қосқан кезде, Dynamics 365 Customer Insights талаптарына сәйкестік шекарасынан тыс деректерді, соның ішінде жеке деректер сияқты ықтимал құпия деректерді беруге мүмкіндік бересіз.</span><span class="sxs-lookup"><span data-stu-id="2f992-148">When you enable Dynamics 365 Customer Insights to transmit data to AdRoll, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="2f992-149">Microsoft мұндай деректерді сіздің нұсқауыңыз бойынша тасымалдайды, бірақ AdRoll платформасының кез келген құпиялылық немесе қауіпсіздік міндеттемелеріне сәйкес келуіне жауап бересіз.</span><span class="sxs-lookup"><span data-stu-id="2f992-149">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that AdRoll meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="2f992-150">Қосымша ақпаратты [Microsoft құпиялық туралы мәлімдемесі](https://go.microsoft.com/fwlink/?linkid=396732) бөлімінен қараңыз.</span><span class="sxs-lookup"><span data-stu-id="2f992-150">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="2f992-151">Бұл функцияны тоқтату үшін бұл экспорттау мақсатын кез келген уақытта Dynamics 365 Customer Insights әкімшісі жоя алады.</span><span class="sxs-lookup"><span data-stu-id="2f992-151">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
