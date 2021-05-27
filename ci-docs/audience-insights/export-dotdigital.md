---
title: Customer Insights деректерін DotDigital платформасына экспорттау
description: DotDigital қызметі үшін қосылымды конфигурациялау және экспорттау жолы туралы ақпарат.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: d08504856e1c673ef32433b83bf491d7f4e8cee4
ms.sourcegitcommit: e8e03309ba2515374a70c132d0758f3e1e1851d0
ms.translationtype: HT
ms.contentlocale: kk-KZ
ms.lasthandoff: 05/04/2021
ms.locfileid: "5976853"
---
# <a name="export-segment-lists-to-dotdigital-preview"></a><span data-ttu-id="b45a4-103">Сегмент тізімдерін DotDigital қызметіне экспорттау (алдын ала қарау нұсқасы)</span><span class="sxs-lookup"><span data-stu-id="b45a4-103">Export segment lists to DotDigital (preview)</span></span>

<span data-ttu-id="b45a4-104">Бірыңғай тұтынушы профильдерінің сегменттерін DotDigital мекенжай кітаптарына экспорттаңыз және оларды науқандар, электрондық пошта маркетингі және dotdigital көмегімен тұтынушы сегменттерін құру үшін пайдаланыңыз.</span><span class="sxs-lookup"><span data-stu-id="b45a4-104">Export segments of unified customer profiles to DotDigital address books and use them for campaigns, email marketing, and to build customer segments with DotDigital.</span></span> 

## <a name="prerequisites-for-a-connection"></a><span data-ttu-id="b45a4-105">Қосылым алғышарттары</span><span class="sxs-lookup"><span data-stu-id="b45a4-105">Prerequisites for a connection</span></span>

-   <span data-ttu-id="b45a4-106">Сізде [DotDigital тіркелгісі](https://dotdigital.com/) және тиісті әкімшінің тіркелгі деректері бар.</span><span class="sxs-lookup"><span data-stu-id="b45a4-106">You have a [DotDigital account](https://dotdigital.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="b45a4-107">DotDigital платформасына қолданыстағы мекенжай кітаптары және тиісті идентификаторлар бар.</span><span class="sxs-lookup"><span data-stu-id="b45a4-107">There are existing address books in DotDigital and the corresponding IDs.</span></span> <span data-ttu-id="b45a4-108">Идентификаторды мекенжай кітабын таңдап, ашқан кезде URL мекенжайынан табуға болады.</span><span class="sxs-lookup"><span data-stu-id="b45a4-108">The ID can be found in the URL when you select and open an address book.</span></span> <span data-ttu-id="b45a4-109">Қосымша ақпарат алу үшін [DotDigital мекенжай кітаптарын](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book) қараңыз.</span><span class="sxs-lookup"><span data-stu-id="b45a4-109">For more information, see [DotDigital address books](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).</span></span>
-   <span data-ttu-id="b45a4-110">Аудитория түсініктерінде [конфигурацияланған сегменттер](segments.md) бар.</span><span class="sxs-lookup"><span data-stu-id="b45a4-110">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="b45a4-111">Экспортталған сегменттердегі тұтынушылардың бірыңғай профильдері электрондық пошта мекенжайын көрсететін өрістен тұрады.</span><span class="sxs-lookup"><span data-stu-id="b45a4-111">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="b45a4-112">Белгілі шектеулер</span><span class="sxs-lookup"><span data-stu-id="b45a4-112">Known limitations</span></span>

- <span data-ttu-id="b45a4-113">DotDigital нысанына 1 миллионға дейін профильді экспорттауға болады.</span><span class="sxs-lookup"><span data-stu-id="b45a4-113">Up to 1 million profiles per export to DotDigital.</span></span>
- <span data-ttu-id="b45a4-114">DotDigital нысанына экспорттау тек сегменттермен шектеледі.</span><span class="sxs-lookup"><span data-stu-id="b45a4-114">Exporting to DotDigital is limited to segments.</span></span>
- <span data-ttu-id="b45a4-115">Жалпы саны 1 миллион профильді экспорттайтын сегменттер провайдер тарапынан шектеулер болғандықтан 3 сағатқа созылуы мүмкін.</span><span class="sxs-lookup"><span data-stu-id="b45a4-115">Exporting segments with a total of 1 million profiles can take up to 3 hours because of limitations on the provider side.</span></span> 
- <span data-ttu-id="b45a4-116">DotDigital платформасына экспорттауға болатын профильдер саны DotDigital платформасымен жасалған келісім-шартқа байланысты және шектеулі.</span><span class="sxs-lookup"><span data-stu-id="b45a4-116">The number of profiles that you can export to DotDigital is dependent and limited on your contract with DotDigital.</span></span>

## <a name="set-up-connection-to-dotdigital"></a><span data-ttu-id="b45a4-117">DotDigital қызметіне қосылым орнату</span><span class="sxs-lookup"><span data-stu-id="b45a4-117">Set up connection to DotDigital</span></span>

1. <span data-ttu-id="b45a4-118">**Әкімші** > **Қосылымдар** тармағына өтіңіз.</span><span class="sxs-lookup"><span data-stu-id="b45a4-118">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="b45a4-119">**Қосылым қосу** түймешігін таңдаңыз және қосылымды конфигурациялау үшін **DotDigital** параметрін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="b45a4-119">Select **Add connection** and choose **DotDigital** to configure the connection.</span></span>

1. <span data-ttu-id="b45a4-120">**Көрсетілетін аты** өрісінде қосылымға оңай танылатын атау енгізіңіз.</span><span class="sxs-lookup"><span data-stu-id="b45a4-120">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="b45a4-121">Қосылым атауы мен түрі осы қосылымды сипаттайды.</span><span class="sxs-lookup"><span data-stu-id="b45a4-121">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="b45a4-122">Қосылымның мақсатын түсіндіретін атауды таңдауды ұсынамыз.</span><span class="sxs-lookup"><span data-stu-id="b45a4-122">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="b45a4-123">Осы қосылымды кім пайдалана алатынын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="b45a4-123">Choose who can use this connection.</span></span> <span data-ttu-id="b45a4-124">Егер сіз ешқандай әрекет жасамасаңыз, әдепкі бойынша Әкімшілер болады.</span><span class="sxs-lookup"><span data-stu-id="b45a4-124">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="b45a4-125">Қосымша ақпарат алу үшін [Салымшыларға экспорттау үшін қосылымды пайдалануға рұқсат беру](connections.md#allow-contributors-to-use-a-connection-for-exports) бөлімін қараңыз.</span><span class="sxs-lookup"><span data-stu-id="b45a4-125">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="b45a4-126">**DotDigital пайдаланушы аты мен құпиясөзін** енгізіңіз.</span><span class="sxs-lookup"><span data-stu-id="b45a4-126">Enter your **DotDigital username and password**.</span></span>

1. <span data-ttu-id="b45a4-127">**[DotDigital мекенжай кітабының идентификаторын](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book)** енгізіңіз.</span><span class="sxs-lookup"><span data-stu-id="b45a4-127">Enter your **[DotDigital address book ID](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book)**.</span></span>

1. <span data-ttu-id="b45a4-128">**Деректер құпиялығы мен сәйкестігін** растау үшін **Мен келісемін** параметрін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="b45a4-128">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="b45a4-129">DotDigital қосылымын баптандыру үшін **Қосылу** пәрменін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="b45a4-129">Select **Connect** to initialize the connection to DotDigital.</span></span>

1. <span data-ttu-id="b45a4-130">**Өзіңізді экспорт пайдаланушысы ретінде қосу** пәрменін таңдап, өзіңіздің Customer Insights тіркелгі деректерін ұсыныңыз.</span><span class="sxs-lookup"><span data-stu-id="b45a4-130">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="b45a4-131">Қосылымды аяқтау үшін **Сақтау** түймешігін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="b45a4-131">Select **Save** to complete the connection.</span></span> 

## <a name="configure-an-export"></a><span data-ttu-id="b45a4-132">Экспорттауды конфигурациялау</span><span class="sxs-lookup"><span data-stu-id="b45a4-132">Configure an export</span></span>

<span data-ttu-id="b45a4-133">Егер сіз осы түрдегі қосылымға қатынаса алсаңыз, сіз бұл экспорттауды конфигурациялай аласыз.</span><span class="sxs-lookup"><span data-stu-id="b45a4-133">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="b45a4-134">Қосымша ақпарат алу үшін [Экспорттауды конфигурациялау үшін қажет рұқсаттар](export-destinations.md#set-up-a-new-export) бөлімін қараңыз.</span><span class="sxs-lookup"><span data-stu-id="b45a4-134">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="b45a4-135">**Деректер** > **Экспорттау** тармағына өтіңіз.</span><span class="sxs-lookup"><span data-stu-id="b45a4-135">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="b45a4-136">Жаңа экспорттау жасау үшін **Мақсатты орын қосу** түймешігін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="b45a4-136">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="b45a4-137">**Экспорттауға арналған қосылым** өрісінде DotDigital бөлімінен қосылым таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="b45a4-137">In the **Connection for export** field, choose a connection from the DotDigital section.</span></span> <span data-ttu-id="b45a4-138">Егер сіз осы бөлімнің атын көрмесеңіз, сізге қолжетімді осы түрдегі қосылым жоқ.</span><span class="sxs-lookup"><span data-stu-id="b45a4-138">If you don't see this section name, there are no connections of this type available to you.</span></span>


1. <span data-ttu-id="b45a4-139">**Деректерді салыстыру** бөліміндегі **Электрондық пошта** өрісінде тұтынушының электрондық пошта мекенжайын көрсететін бірыңғай тұтынушы профиліндегі өрісті таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="b45a4-139">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="b45a4-140">**Аты**, **Тегі**, **Толық аты-жөні**, **Жынысы** және **Пошта индексі** сияқты басқа қосымша өрістер үшін сол қадамдарды қайталаңыз.</span><span class="sxs-lookup"><span data-stu-id="b45a4-140">Repeat the same steps for other optional fields such as **First name**, **Last name**, **Full name**, **Gender**, and **Post code**.</span></span>

1. <span data-ttu-id="b45a4-141">Экспорттау керек сегменттерді таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="b45a4-141">Select the segments you want to export.</span></span> <span data-ttu-id="b45a4-142">DotDigital платформасына жалпы 1 миллионға дейін тұтынушы профилін экспорттай аласыз.</span><span class="sxs-lookup"><span data-stu-id="b45a4-142">You can export up to 1 million customer profiles in total to DotDigital.</span></span>

1. <span data-ttu-id="b45a4-143">**Сақтау** опциясын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="b45a4-143">Select **Save**.</span></span>

<span data-ttu-id="b45a4-144">Экспорттауды сақтау экспорттауды бірден іске қоспайды.</span><span class="sxs-lookup"><span data-stu-id="b45a4-144">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="b45a4-145">Экспорттау әр [жоспарланған жаңартумен](system.md#schedule-tab) іске қосылады.</span><span class="sxs-lookup"><span data-stu-id="b45a4-145">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="b45a4-146">Сондай-ақ [деректерді сұрау бойынша экспорттауға](export-destinations.md#run-exports-on-demand) болады.</span><span class="sxs-lookup"><span data-stu-id="b45a4-146">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 
 
<span data-ttu-id="b45a4-147">DotDigital платформасында [DotDigital мекенжай кітаптарындағы](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book) сегменттерді табуға болады.</span><span class="sxs-lookup"><span data-stu-id="b45a4-147">In DotDigital, you can now find your segments in [DotDigital address books](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).</span></span>


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="b45a4-148">Деректердің құпиялылығы мен сәйкестігі</span><span class="sxs-lookup"><span data-stu-id="b45a4-148">Data privacy and compliance</span></span>

<span data-ttu-id="b45a4-149">Деректерді DotDigital платформасына жіберу үшін Dynamics 365 Customer Insights бағдарламасын қосқан кезде, Dynamics 365 Customer Insights талаптарына сәйкестік шекарасынан тыс деректерді, соның ішінде жеке деректер сияқты ықтимал құпия деректерді беруге мүмкіндік бересіз.</span><span class="sxs-lookup"><span data-stu-id="b45a4-149">When you enable Dynamics 365 Customer Insights to transmit data to DotDigital, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="b45a4-150">Microsoft мұндай деректерді сіздің нұсқауыңыз бойынша тасымалдайды, бірақ DotDigital кез келген құпиялылық немесе қауіпсіздік міндеттемелеріне сәйкес келуіне жауап бересіз.</span><span class="sxs-lookup"><span data-stu-id="b45a4-150">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that DotDigital meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="b45a4-151">Қосымша ақпаратты [Microsoft құпиялық туралы мәлімдемесі](https://go.microsoft.com/fwlink/?linkid=396732) бөлімінен қараңыз.</span><span class="sxs-lookup"><span data-stu-id="b45a4-151">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="b45a4-152">Бұл функцияны тоқтату үшін бұл экспорттау мақсатын кез келген уақытта Dynamics 365 Customer Insights әкімшісі жоя алады.</span><span class="sxs-lookup"><span data-stu-id="b45a4-152">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
