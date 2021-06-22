---
title: Customer Insights деректерін LinkedIn Ads қызметіне экспорттау
description: LinkedIn Ads қызметі үшін қосылымды конфигурациялау және экспорттау жолы туралы ақпарат.
ms.date: 05/12/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 1c7b0c728bc4d4cf6b5aea79396cf0779fbf298d
ms.sourcegitcommit: 831765a55775d358447cb7ffa56f2c3b85459084
ms.translationtype: HT
ms.contentlocale: kk-KZ
ms.lasthandoff: 06/01/2021
ms.locfileid: "6124515"
---
# <a name="export-segments-to-linkedin-ads-preview"></a><span data-ttu-id="5d9f8-103">Сегменттерді LinkedIn Ads қызметіне экспорттау (алдын ала қарау нұсқасы)</span><span class="sxs-lookup"><span data-stu-id="5d9f8-103">Export segments to LinkedIn Ads (preview)</span></span>

<span data-ttu-id="5d9f8-104">Сәйкес аудиторияны жасау үшін бірыңғай тұтынушы профильдерінің сегменттерін LinkedIn Ads қызметіне экспорттаңыз.</span><span class="sxs-lookup"><span data-stu-id="5d9f8-104">Export segments of unified customer profiles to LinkedIn Ads to create matched audiences.</span></span> <span data-ttu-id="5d9f8-105">Сәйкес аудиторияны компанияны мақсаттауға және контактіні мақсаттауға пайдаланыңыз.</span><span class="sxs-lookup"><span data-stu-id="5d9f8-105">Use the matched audiences for company targeting and contact targeting.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="5d9f8-106">Алғышарттар</span><span class="sxs-lookup"><span data-stu-id="5d9f8-106">Prerequisites</span></span>

-   <span data-ttu-id="5d9f8-107">Сізде [LinkedIn Campaign Manager тіркелгісі](https://business.linkedin.com/marketing-solutions/ads) және тиісті әкімші тіркелгі деректері бар.</span><span class="sxs-lookup"><span data-stu-id="5d9f8-107">You have an [LinkedIn Campaign Manager account](https://business.linkedin.com/marketing-solutions/ads) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="5d9f8-108">Аудитория түсініктерінде [конфигурацияланған сегменттер](segments.md) бар.</span><span class="sxs-lookup"><span data-stu-id="5d9f8-108">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="5d9f8-109">Экспортталған сегменттердегі тұтынушылардың профильдері электрондық пошта мекенжайы бар өрісті қамтиды.</span><span class="sxs-lookup"><span data-stu-id="5d9f8-109">Customer profiles in the exported segments contain a field with an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="5d9f8-110">Белгілі шектеулер</span><span class="sxs-lookup"><span data-stu-id="5d9f8-110">Known limitations</span></span>

- <span data-ttu-id="5d9f8-111">LinkedIn Ads қызметіне бір экспорттаған кезде 100000 профильді экспорттауға болады.</span><span class="sxs-lookup"><span data-stu-id="5d9f8-111">You can export up to 100K profiles per export to LinkedIn Ads.</span></span>
- <span data-ttu-id="5d9f8-112">LinkedIn Ads қызметіне экспорттау сегменттермен шектеледі.</span><span class="sxs-lookup"><span data-stu-id="5d9f8-112">Exporting to LinkedIn Ads is limited to segments.</span></span>
- <span data-ttu-id="5d9f8-113">LinkedIn Ads қызметіне 100000 дейінгі профильді экспорттауды аяқтау 10 минутқа созылуы мүмкін.</span><span class="sxs-lookup"><span data-stu-id="5d9f8-113">Exporting up to 100K profiles to LinkedIn Ads can take up to 10 minutes to complete.</span></span> 

## <a name="set-up-the-connection-to-linkedin-ads"></a><span data-ttu-id="5d9f8-114">LinkedIn Ads қызметіне қосылым орнату</span><span class="sxs-lookup"><span data-stu-id="5d9f8-114">Set up the connection to LinkedIn Ads</span></span>

1. <span data-ttu-id="5d9f8-115">Audience insights бағдарламасында **Әкімші** > **Қосылымдар** тармағына өтіңіз.</span><span class="sxs-lookup"><span data-stu-id="5d9f8-115">In audience insights, go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="5d9f8-116">**Қосылым қосу** түймешігін таңдаңыз және қосылымды конфигурациялау үшін **LinkedIn Ads** параметрін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="5d9f8-116">Select **Add connection** and choose **LinkedIn Ads** to configure the connection.</span></span>

1. <span data-ttu-id="5d9f8-117">**Көрсетілетін аты** өрісінде қосылымға оңай танылатын атау енгізіңіз.</span><span class="sxs-lookup"><span data-stu-id="5d9f8-117">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="5d9f8-118">Қосылым атауы мен түрі осы қосылымды сипаттайды.</span><span class="sxs-lookup"><span data-stu-id="5d9f8-118">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="5d9f8-119">Қосылымның мақсатын түсіндіретін атауды таңдауды ұсынамыз.</span><span class="sxs-lookup"><span data-stu-id="5d9f8-119">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="5d9f8-120">Осы қосылымды кім пайдалана алатынын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="5d9f8-120">Choose who can use this connection.</span></span> <span data-ttu-id="5d9f8-121">Егер сіз ешқандай әрекет жасамасаңыз, әдепкі бойынша әкімшілер болады.</span><span class="sxs-lookup"><span data-stu-id="5d9f8-121">If you take no action, the default is administrators.</span></span> <span data-ttu-id="5d9f8-122">Қосымша ақпарат алу үшін [Салымшыларға экспорттау үшін қосылымды пайдалануға рұқсат беру](connections.md#allow-contributors-to-use-a-connection-for-exports) бөлімін қараңыз.</span><span class="sxs-lookup"><span data-stu-id="5d9f8-122">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="5d9f8-123">Өзіңіздің [LinkedIn Campaign Manager тіркелгі идентификаторыңызды](https://www.linkedin.com/help/lms/answer/a424270) ұсыныңыз.</span><span class="sxs-lookup"><span data-stu-id="5d9f8-123">Provide your [LinkedIn Campaign Manager Account ID](https://www.linkedin.com/help/lms/answer/a424270).</span></span>

1. <span data-ttu-id="5d9f8-124">**Деректер құпиялығы мен сәйкестігін** растау үшін **Мен келісемін** параметрін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="5d9f8-124">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="5d9f8-125">Campaign Monitor қызметіне қосылымды баптандыру үшін **Қосылу** түймешігін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="5d9f8-125">Select **Connect** to initialize the connection to Campaign Monitor.</span></span>

1. <span data-ttu-id="5d9f8-126">**LinkedIn қызметімен аутентификациялау** опциясын таңдаңыз және LinkedIn Campaign Manager қызметі үшін әкімші тіркелгі деректерін беріңіз.</span><span class="sxs-lookup"><span data-stu-id="5d9f8-126">Select **Authenticate with LinkedIn** and provide your admin credentials for LinkedIn Campaign Manager.</span></span>

1. <span data-ttu-id="5d9f8-127">**Өзіңізді экспорт пайдаланушысы ретінде қосу** пәрменін таңдап, өзіңіздің Customer Insights тіркелгі деректерін ұсыныңыз.</span><span class="sxs-lookup"><span data-stu-id="5d9f8-127">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="5d9f8-128">Қосылымды аяқтау үшін **Сақтау** түймешігін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="5d9f8-128">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="5d9f8-129">Экспорттауды конфигурациялау</span><span class="sxs-lookup"><span data-stu-id="5d9f8-129">Configure an export</span></span>

<span data-ttu-id="5d9f8-130">Егер сіз осы түрдегі қосылымға қатынаса алсаңыз, сіз экспорттауды конфигурациялай аласыз.</span><span class="sxs-lookup"><span data-stu-id="5d9f8-130">You can configure an export if you have access to a connection of this type.</span></span> <span data-ttu-id="5d9f8-131">Қосымша ақпарат алу үшін [Экспорттауды конфигурациялау үшін қажет рұқсаттар](export-destinations.md#set-up-a-new-export) бөлімін қараңыз.</span><span class="sxs-lookup"><span data-stu-id="5d9f8-131">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="5d9f8-132">**Деректер** > **Экспорттау** тармағына өтіңіз.</span><span class="sxs-lookup"><span data-stu-id="5d9f8-132">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="5d9f8-133">Жаңа экспорттау жасау үшін **Мақсатты орын қосу** түймешігін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="5d9f8-133">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="5d9f8-134">**Экспорттауға арналған қосылым** өрісінде LinkedIn Ads бөлімінен қосылым таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="5d9f8-134">In the **Connection for export** field, choose a connection from the LinkedIn Ads section.</span></span> <span data-ttu-id="5d9f8-135">Егер сіз осы бөлімнің атын көрмесеңіз, сізге қолжетімді осы түрдегі қосылым жоқ.</span><span class="sxs-lookup"><span data-stu-id="5d9f8-135">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="5d9f8-136">LinkedIn қызметінде деректерді [контактіні мақсаттау](https://business.linkedin.com/marketing-solutions/ad-targeting/contact-targeting) немесе [компания мақсаттау](https://business.linkedin.com/marketing-solutions/ad-targeting/account-targeting) үшін экспорттау керектігін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="5d9f8-136">Choose whether you want to export data to do [contact targeting](https://business.linkedin.com/marketing-solutions/ad-targeting/contact-targeting) or [company targeting](https://business.linkedin.com/marketing-solutions/ad-targeting/account-targeting) on LinkedIn.</span></span> 

1. <span data-ttu-id="5d9f8-137">**Деректерді сәйкестендіру** бөлімінде тұтынушының электрондық пошта мекенжайын көрсететін бірыңғай тұтынушы профиліндегі өрісті таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="5d9f8-137">In the **Data matching** section, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="5d9f8-138">Бұл LinkedIn Ads қызметіне сегменттерді экспорттау үшін қажет.</span><span class="sxs-lookup"><span data-stu-id="5d9f8-138">It's required to export segments to LinkedIn Ads.</span></span>

1. <span data-ttu-id="5d9f8-139">Экспорттау керек сегменттерді таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="5d9f8-139">Select the segments you want to export.</span></span> <span data-ttu-id="5d9f8-140">LinkedIn Campaign Manager қызметіндегі сәйкес аудитория экспорттау үшін таңдаған сегменттердің атымен автоматты түрде жасалады.</span><span class="sxs-lookup"><span data-stu-id="5d9f8-140">The matched audiences in LinkedIn Campaign Manager will automatically be created with the name of the segments that you selected to export.</span></span> <span data-ttu-id="5d9f8-141">Әрбір сегмент бөлек сәйкес аудиторияға әкеледі.</span><span class="sxs-lookup"><span data-stu-id="5d9f8-141">Each segment will result in a separate matched audience.</span></span> 

1. <span data-ttu-id="5d9f8-142">**Сақтау** опциясын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="5d9f8-142">Select **Save**.</span></span>

<span data-ttu-id="5d9f8-143">Экспорттауды сақтау экспорттауды бірден іске қоспайды.</span><span class="sxs-lookup"><span data-stu-id="5d9f8-143">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="5d9f8-144">Экспорттау әр [жоспарланған жаңартумен](system.md#schedule-tab) іске қосылады.</span><span class="sxs-lookup"><span data-stu-id="5d9f8-144">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="5d9f8-145">Сондай-ақ [деректерді сұрау бойынша экспорттауға](export-destinations.md#run-exports-on-demand) болады.</span><span class="sxs-lookup"><span data-stu-id="5d9f8-145">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="5d9f8-146">Деректердің құпиялылығы мен сәйкестігі</span><span class="sxs-lookup"><span data-stu-id="5d9f8-146">Data privacy and compliance</span></span>

<span data-ttu-id="5d9f8-147">Деректерді LinkedIn Ads қызметіне тасымалдау үшін Dynamics 365 Customer Insights бағдарламасын қосқан кезде жеке деректер сияқты ықтимал құпия деректерді қоса алғанда, деректерді Dynamics 365 Customer Insights бағдарламасының үйлесімділік шегінен тыс тасымалдауға рұқсат бересіз.</span><span class="sxs-lookup"><span data-stu-id="5d9f8-147">When you enable Dynamics 365 Customer Insights to transmit data to LinkedIn Ads, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="5d9f8-148">Microsoft корпорациясы мұндай деректерді сіздің нұсқауыңыз бойынша жібереді, бірақ сіз LinkedIn Ads қызметінің кез келген құпиялылық немесе қауіпсіздік міндеттемелерінің орындалуына кепілдік беретініне жауаптысыз.</span><span class="sxs-lookup"><span data-stu-id="5d9f8-148">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that LinkedIn Ads meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="5d9f8-149">Қосымша ақпаратты [Microsoft құпиялық туралы мәлімдемесі](https://go.microsoft.com/fwlink/?linkid=396732) бөлімінен қараңыз.</span><span class="sxs-lookup"><span data-stu-id="5d9f8-149">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="5d9f8-150">Dynamics 365 Customer Insights әкімшісі бұл функцияны тоқтату үшін бұл экспорттау мақсатын кез келген уақытта жоя алады.</span><span class="sxs-lookup"><span data-stu-id="5d9f8-150">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to stop the use of this functionality.</span></span>
