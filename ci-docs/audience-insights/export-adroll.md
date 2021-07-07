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
ms.openlocfilehash: 67bfa23d56b26ae592efa4d7197713664bb02623
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: kk-KZ
ms.lasthandoff: 06/24/2021
ms.locfileid: "6304840"
---
# <a name="export-segments-to-adroll-preview"></a><span data-ttu-id="705c4-103">Сегменттерді AdRoll қызметіне экспорттау (алдын ала қарау нұсқасы)</span><span class="sxs-lookup"><span data-stu-id="705c4-103">Export segments to AdRoll (preview)</span></span>

<span data-ttu-id="705c4-104">Тұтынушының бірыңғай профильдерінің сегменттерін AdRoll платформасына экспорттап, оларды жарнама үшін пайдаланыңыз.</span><span class="sxs-lookup"><span data-stu-id="705c4-104">Export segments of unified customer profiles to AdRoll and use them for advertising.</span></span> 

## <a name="prerequisites-for-a-connection"></a><span data-ttu-id="705c4-105">Қосылым алғышарттары</span><span class="sxs-lookup"><span data-stu-id="705c4-105">Prerequisites for a connection</span></span>

-   <span data-ttu-id="705c4-106">Сізде [AdRoll тіркелгісі](https://www.adroll.com/) және тиісті әкімшінің тіркелгі деректері бар.</span><span class="sxs-lookup"><span data-stu-id="705c4-106">You have an [AdRoll account](https://www.adroll.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="705c4-107">Аудитория түсініктерінде [конфигурацияланған сегменттер](segments.md) бар.</span><span class="sxs-lookup"><span data-stu-id="705c4-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="705c4-108">Экспортталған сегменттердегі тұтынушылардың бірыңғай профильдері электрондық пошта мекенжайын көрсететін өрістен тұрады.</span><span class="sxs-lookup"><span data-stu-id="705c4-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="705c4-109">Белгілі шектеулер</span><span class="sxs-lookup"><span data-stu-id="705c4-109">Known limitations</span></span>

- <span data-ttu-id="705c4-110">Бір уақытта AdRoll қызметіне 250000 профиль экспорттауға болады.</span><span class="sxs-lookup"><span data-stu-id="705c4-110">You can export up to 250,000 profiles at a time to AdRoll.</span></span>
- <span data-ttu-id="705c4-111">AdRoll платформасына сегменттерді 100-ден кем профильмен экспорттау мүмкін емес.</span><span class="sxs-lookup"><span data-stu-id="705c4-111">You can't export segments with fewer than 100 profiles to AdRoll.</span></span> 
- <span data-ttu-id="705c4-112">AdRoll нысанына экспорттау тек сегменттермен шектеледі.</span><span class="sxs-lookup"><span data-stu-id="705c4-112">Exporting to AdRoll is limited to segments.</span></span>
- <span data-ttu-id="705c4-113">AdRoll платформасына 250000 профиль экспорттау 10 минутқа дейін созылуы мүмкін.</span><span class="sxs-lookup"><span data-stu-id="705c4-113">Exporting up to 250,000 profiles to AdRoll can take up to 10 minutes to complete.</span></span> 
- <span data-ttu-id="705c4-114">AdRoll қызметіне экспорттауға болатын профильдер саны AdRoll қызметімен келісімшартқа байланысты.</span><span class="sxs-lookup"><span data-stu-id="705c4-114">The number of profiles that you can export to AdRoll is dependent on your contract with AdRoll.</span></span>

## <a name="set-up-connection-to-adroll"></a><span data-ttu-id="705c4-115">AdRoll қызметіне қосылым орнату</span><span class="sxs-lookup"><span data-stu-id="705c4-115">Set up connection to AdRoll</span></span>

1. <span data-ttu-id="705c4-116">**Әкімші** > **Қосылымдар** тармағына өтіңіз.</span><span class="sxs-lookup"><span data-stu-id="705c4-116">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="705c4-117">**Қосылым қосу** түймешігін таңдаңыз және қосылымды конфигурациялау үшін **AdRoll** параметрін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="705c4-117">Select **Add connection** and choose **AdRoll** to configure the connection.</span></span>

1. <span data-ttu-id="705c4-118">**Көрсетілетін аты** өрісінде қосылымға оңай танылатын атау енгізіңіз.</span><span class="sxs-lookup"><span data-stu-id="705c4-118">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="705c4-119">Қосылым атауы мен түрі осы қосылымды сипаттайды.</span><span class="sxs-lookup"><span data-stu-id="705c4-119">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="705c4-120">Қосылымның мақсатын түсіндіретін атауды таңдауды ұсынамыз.</span><span class="sxs-lookup"><span data-stu-id="705c4-120">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="705c4-121">Осы қосылымды кім пайдалана алатынын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="705c4-121">Choose who can use this connection.</span></span> <span data-ttu-id="705c4-122">Егер сіз ешқандай әрекет жасамасаңыз, әдепкі бойынша Әкімшілер болады.</span><span class="sxs-lookup"><span data-stu-id="705c4-122">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="705c4-123">Қосымша ақпарат алу үшін [Салымшыларға экспорттау үшін қосылымды пайдалануға рұқсат беру](connections.md#allow-contributors-to-use-a-connection-for-exports) бөлімін қараңыз.</span><span class="sxs-lookup"><span data-stu-id="705c4-123">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="705c4-124">**Деректер құпиялығы мен сәйкестігін** растау үшін **Мен келісемін** параметрін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="705c4-124">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="705c4-125">AdRoll қосылымын баптандыру үшін **Қосылу** пәрменін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="705c4-125">Select **Connect** to initialize the connection to AdRoll.</span></span>

1. <span data-ttu-id="705c4-126">**AdRoll көмегімен аутентификациялау** пәрменін таңдап, AdRoll платформасына арналған әкімшінің тіркелгі деректерін ұсыныңыз.</span><span class="sxs-lookup"><span data-stu-id="705c4-126">Select **Authenticate with AdRoll** and provide your admin credentials for AdRoll.</span></span> 

1. <span data-ttu-id="705c4-127">**Өзіңізді экспорт пайдаланушысы ретінде қосу** пәрменін таңдап, өзіңіздің Customer Insights тіркелгі деректерін ұсыныңыз.</span><span class="sxs-lookup"><span data-stu-id="705c4-127">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="705c4-128">Қосылымды аяқтау үшін **Сақтау** түймешігін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="705c4-128">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="705c4-129">Экспорттауды конфигурациялау</span><span class="sxs-lookup"><span data-stu-id="705c4-129">Configure an export</span></span>

<span data-ttu-id="705c4-130">Егер сіз осы түрдегі қосылымға қатынаса алсаңыз, сіз бұл экспорттауды конфигурациялай аласыз.</span><span class="sxs-lookup"><span data-stu-id="705c4-130">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="705c4-131">Қосымша ақпарат алу үшін [Экспорттауды конфигурациялау үшін қажет рұқсаттар](export-destinations.md#set-up-a-new-export) бөлімін қараңыз.</span><span class="sxs-lookup"><span data-stu-id="705c4-131">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="705c4-132">**Деректер** > **Экспорттау** тармағына өтіңіз.</span><span class="sxs-lookup"><span data-stu-id="705c4-132">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="705c4-133">Жаңа экспорттау жасау үшін **Мақсатты орын қосу** түймешігін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="705c4-133">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="705c4-134">**Экспорттауға арналған қосылым** өрісінде AdRoll бөлімінен қосылым таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="705c4-134">In the **Connection for export** field, choose a connection from the AdRoll section.</span></span> <span data-ttu-id="705c4-135">Егер сіз бұл бөлімнің атауын көрмесеңіз, онда сіз үшін осы түрдегі қосылымдар қолжетімді емес.</span><span class="sxs-lookup"><span data-stu-id="705c4-135">If you don't see this section name, then no connections of this type are available to you.</span></span>

1. <span data-ttu-id="705c4-136">**AdRoll жарнама берушілерінің идентификаторын** енгізіңіз.</span><span class="sxs-lookup"><span data-stu-id="705c4-136">Enter your **AdRoll Advertiser ID**.</span></span> <span data-ttu-id="705c4-137">Қосымша ақпарат алу үшін [AdRoll жарнама берушілерінің профильдері](https://help.adroll.com/hc/articles/212011838-Advertiser-Profiles) бөлімін қараңыз.</span><span class="sxs-lookup"><span data-stu-id="705c4-137">For more information, see [AdRoll Advertiser Profiles](https://help.adroll.com/hc/articles/212011838-Advertiser-Profiles).</span></span>

3. <span data-ttu-id="705c4-138">**Деректерді салыстыру** бөліміндегі **Электрондық пошта** өрісінде тұтынушының электрондық пошта мекенжайын көрсететін бірыңғай тұтынушы профиліндегі өрісті таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="705c4-138">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="705c4-139">Сегменттерді AdRoll платформасына экспорттау қажет.</span><span class="sxs-lookup"><span data-stu-id="705c4-139">It's required to export segments to AdRoll.</span></span>

1. <span data-ttu-id="705c4-140">Экспорттау керек сегменттерді таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="705c4-140">Select the segments you want to export.</span></span> <span data-ttu-id="705c4-141">Кемінде 100 мүшесі бар сегментті таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="705c4-141">Select a segment with a least 100 members.</span></span> <span data-ttu-id="705c4-142">Кішірек сегменттерді экспорттау мүмкін емес.</span><span class="sxs-lookup"><span data-stu-id="705c4-142">You can't export smaller segments.</span></span> <span data-ttu-id="705c4-143">Сонымен қатар экспортталатын сегменттің максималды мөлшері әр экспортқа 250000 мүшені құрайды.</span><span class="sxs-lookup"><span data-stu-id="705c4-143">Additionally the maximum size of a segment to export is 250,000 members per export.</span></span> 

1. <span data-ttu-id="705c4-144">**Сақтау** опциясын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="705c4-144">Select **Save**.</span></span>

<span data-ttu-id="705c4-145">Экспорттауды сақтау экспорттауды бірден іске қоспайды.</span><span class="sxs-lookup"><span data-stu-id="705c4-145">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="705c4-146">Экспорттау әр [жоспарланған жаңартумен](system.md#schedule-tab) іске қосылады.</span><span class="sxs-lookup"><span data-stu-id="705c4-146">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> 

<span data-ttu-id="705c4-147">Сондай-ақ [деректерді сұрау бойынша экспорттауға](export-destinations.md#run-exports-on-demand) болады.</span><span class="sxs-lookup"><span data-stu-id="705c4-147">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="705c4-148">Деректердің құпиялылығы мен сәйкестігі</span><span class="sxs-lookup"><span data-stu-id="705c4-148">Data privacy and compliance</span></span>

<span data-ttu-id="705c4-149">Деректерді AdRoll платформасына жіберу үшін Dynamics 365 Customer Insights бағдарламасын қосқан кезде, Dynamics 365 Customer Insights талаптарына сәйкестік шекарасынан тыс деректерді, соның ішінде жеке деректер сияқты ықтимал құпия деректерді беруге мүмкіндік бересіз.</span><span class="sxs-lookup"><span data-stu-id="705c4-149">When you enable Dynamics 365 Customer Insights to transmit data to AdRoll, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="705c4-150">Microsoft мұндай деректерді сіздің нұсқауыңыз бойынша тасымалдайды, бірақ AdRoll платформасының кез келген құпиялылық немесе қауіпсіздік міндеттемелеріне сәйкес келуіне жауап бересіз.</span><span class="sxs-lookup"><span data-stu-id="705c4-150">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that AdRoll meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="705c4-151">Қосымша ақпаратты [Microsoft құпиялық туралы мәлімдемесі](https://go.microsoft.com/fwlink/?linkid=396732) бөлімінен қараңыз.</span><span class="sxs-lookup"><span data-stu-id="705c4-151">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="705c4-152">Бұл функцияны тоқтату үшін бұл экспорттау мақсатын кез келген уақытта Dynamics 365 Customer Insights әкімшісі жоя алады.</span><span class="sxs-lookup"><span data-stu-id="705c4-152">Your Dynamics 365 Customer Insights administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
