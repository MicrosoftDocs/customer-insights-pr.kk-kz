---
title: Customer Insights деректерін AdRoll платформасына экспорттау
description: AdRoll қосылымын конфигурациялау жолы туралы ақпарат.
ms.date: 02/15/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 6fedd549c2e7de362f36e3fb23d363200bb92a04
ms.sourcegitcommit: d24e52150fe5a4fab45128e12d6a03637771d9b9
ms.translationtype: HT
ms.contentlocale: kk-KZ
ms.lasthandoff: 03/19/2021
ms.locfileid: "5697081"
---
# <a name="connector-for-adroll-preview"></a><span data-ttu-id="362cf-103">AdRoll қосқышы (алдын ала қарау нұсқасы)</span><span class="sxs-lookup"><span data-stu-id="362cf-103">Connector for AdRoll (preview)</span></span>

<span data-ttu-id="362cf-104">Тұтынушының бірыңғай профильдерінің сегменттерін AdRoll платформасына экспорттап, оларды жарнама үшін пайдаланыңыз.</span><span class="sxs-lookup"><span data-stu-id="362cf-104">Export segments of unified customer profiles to AdRoll and use them for advertising.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="362cf-105">Алғышарттар</span><span class="sxs-lookup"><span data-stu-id="362cf-105">Prerequisites</span></span>

-   <span data-ttu-id="362cf-106">Сізде [AdRoll тіркелгісі](https://www.adroll.com/) және тиісті әкімшінің тіркелгі деректері бар.</span><span class="sxs-lookup"><span data-stu-id="362cf-106">You have an [AdRoll account](https://www.adroll.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="362cf-107">Аудитория түсініктерінде [конфигурацияланған сегменттер](segments.md) бар.</span><span class="sxs-lookup"><span data-stu-id="362cf-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="362cf-108">Экспортталған сегменттердегі тұтынушылардың бірыңғай профильдері электрондық пошта мекенжайын көрсететін өрістен тұрады.</span><span class="sxs-lookup"><span data-stu-id="362cf-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="connect-to-adroll"></a><span data-ttu-id="362cf-109">AdRoll қызметіне қосылу</span><span class="sxs-lookup"><span data-stu-id="362cf-109">Connect to AdRoll</span></span>

1. <span data-ttu-id="362cf-110">**Әкімші** > **Экспорттық межелі орындар** тармағына өтіңіз.</span><span class="sxs-lookup"><span data-stu-id="362cf-110">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="362cf-111">**AdRoll** бөліміндегі **Орнату** пәрменін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="362cf-111">Under **AdRoll**, select **Set up**.</span></span>

1. <span data-ttu-id="362cf-112">**Көрсетілетін атауы** өрісінде экспорттық межелі орынға танылатын атау беріңіз.</span><span class="sxs-lookup"><span data-stu-id="362cf-112">Give your export destination a recognizable name in the **Display name** field.</span></span>

   :::image type="content" source="media/AdRoll_config.PNG" alt-text="AdRoll қосылымына арналған конфигурация тақтасы.":::

1. <span data-ttu-id="362cf-114">**Деректер құпиялығы мен сәйкестігін** растау үшін **Мен келісемін** параметрін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="362cf-114">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="362cf-115">AdRoll қосылымын баптандыру үшін **Қосылу** пәрменін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="362cf-115">Select **Connect** to initialize the connection to AdRoll.</span></span>

1. <span data-ttu-id="362cf-116">**AdRoll көмегімен аутентификациялау** пәрменін таңдап, AdRoll платформасына арналған әкімшінің тіркелгі деректерін ұсыныңыз.</span><span class="sxs-lookup"><span data-stu-id="362cf-116">Select **Authenticate with AdRoll** and provide your admin credentials for AdRoll.</span></span> 

1. <span data-ttu-id="362cf-117">**Өзіңізді экспорт пайдаланушысы ретінде қосу** пәрменін таңдап, өзіңіздің Customer Insights тіркелгі деректерін ұсыныңыз.</span><span class="sxs-lookup"><span data-stu-id="362cf-117">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="362cf-118">**AdRoll жарнама беруші идентификаторы** [Жарнамаланатын AdRoll](https://help.adroll.com/hc/en-us/articles/212011838-Advertiser-Profiles) параметрін енгізіңіз.</span><span class="sxs-lookup"><span data-stu-id="362cf-118">Enter your **AdRoll Advertiser ID** [AdRoll Advertisable](https://help.adroll.com/hc/en-us/articles/212011838-Advertiser-Profiles).</span></span>

1. <span data-ttu-id="362cf-119">Экспорттауды теңшеу үшін **Келесі** параметрін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="362cf-119">Select **Next** to configure the export.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="362cf-120">Қосқышты конфигурациялау</span><span class="sxs-lookup"><span data-stu-id="362cf-120">Configure the connector</span></span>

1. <span data-ttu-id="362cf-121">**Деректерді салыстыру** бөліміндегі **Электрондық пошта** өрісінде тұтынушының электрондық пошта мекенжайын көрсететін бірыңғай тұтынушы профиліндегі өрісті таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="362cf-121">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="362cf-122">Сегменттерді AdRoll платформасына экспорттау қажет.</span><span class="sxs-lookup"><span data-stu-id="362cf-122">It's required to export segments to AdRoll.</span></span>

1. <span data-ttu-id="362cf-123">Экспорттау керек сегменттерді таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="362cf-123">Select the segments you want to export.</span></span> <span data-ttu-id="362cf-124">Кемінде 100 мүшесі бар сегментті таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="362cf-124">Select a segment with a least 100 members.</span></span> <span data-ttu-id="362cf-125">Кішірек сегменттерді экспорттау мүмкін емес.</span><span class="sxs-lookup"><span data-stu-id="362cf-125">You can't export smaller segments.</span></span> <span data-ttu-id="362cf-126">Сонымен қатар, экспортталатын сегменттің максималды мөлшері әр экспортқа 250000 мүшені құрайды.</span><span class="sxs-lookup"><span data-stu-id="362cf-126">Additionally the maximum size of a segment to export is 250'000 members per export.</span></span> 

1. <span data-ttu-id="362cf-127">**Сақтау** опциясын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="362cf-127">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="362cf-128">Деректерді экспорттау</span><span class="sxs-lookup"><span data-stu-id="362cf-128">Export the data</span></span>

<span data-ttu-id="362cf-129">[Сұрау бойынша деректерді экспорттауға](export-destinations.md) болады.</span><span class="sxs-lookup"><span data-stu-id="362cf-129">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="362cf-130">Экспорттау сондай-ақ әрбір [жоспарланған жаңарту](system.md#schedule-tab) сайын іске қосылады.</span><span class="sxs-lookup"><span data-stu-id="362cf-130">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="362cf-131">Белгілі шектеулер</span><span class="sxs-lookup"><span data-stu-id="362cf-131">Known limitations</span></span>

- <span data-ttu-id="362cf-132">AdRoll платформасында бір экспорттауда 250000 профильге дейін экспорттауға болады.</span><span class="sxs-lookup"><span data-stu-id="362cf-132">You can export up to 250'000 profiles in per export to AdRoll.</span></span>
- <span data-ttu-id="362cf-133">AdRoll платформасына сегменттерді 100-ден кем профильмен экспорттау мүмкін емес.</span><span class="sxs-lookup"><span data-stu-id="362cf-133">You can't export segments with fewer than 100 profiles to AdRoll.</span></span> 
- <span data-ttu-id="362cf-134">AdRoll нысанына экспорттау тек сегменттермен шектеледі.</span><span class="sxs-lookup"><span data-stu-id="362cf-134">Exporting to AdRoll is limited to segments.</span></span>
- <span data-ttu-id="362cf-135">AdRoll платформасына 250000-ға дейін профильді экспорттау 10 минутқа дейін созылуы мүмкін.</span><span class="sxs-lookup"><span data-stu-id="362cf-135">Exporting up to 250'000 profiles to AdRoll can take up to 10 minutes to complete.</span></span> 
- <span data-ttu-id="362cf-136">AdRoll платформасына экспорттауға болатын профильдер саны AdRoll платформасымен жасалған келісімшартқа байланысты және шектеулі.</span><span class="sxs-lookup"><span data-stu-id="362cf-136">The number of profiles that you can export to AdRoll is dependent and limited on your contract with AdRoll.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="362cf-137">Деректердің құпиялылығы мен сәйкестігі</span><span class="sxs-lookup"><span data-stu-id="362cf-137">Data privacy and compliance</span></span>

<span data-ttu-id="362cf-138">Деректерді AdRoll платформасына жіберу үшін Dynamics 365 Customer Insights бағдарламасын қосқан кезде, Dynamics 365 Customer Insights талаптарына сәйкестік шекарасынан тыс деректерді, соның ішінде жеке деректер сияқты ықтимал құпия деректерді беруге мүмкіндік бересіз.</span><span class="sxs-lookup"><span data-stu-id="362cf-138">When you enable Dynamics 365 Customer Insights to transmit data to AdRoll, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="362cf-139">Microsoft мұндай деректерді сіздің нұсқауыңыз бойынша тасымалдайды, бірақ AdRoll платформасының кез келген құпиялылық немесе қауіпсіздік міндеттемелеріне сәйкес келуіне жауап бересіз.</span><span class="sxs-lookup"><span data-stu-id="362cf-139">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that AdRoll meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="362cf-140">Қосымша ақпаратты [Microsoft құпиялық туралы мәлімдемесі](https://go.microsoft.com/fwlink/?linkid=396732) бөлімінен қараңыз.</span><span class="sxs-lookup"><span data-stu-id="362cf-140">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="362cf-141">Бұл функцияны тоқтату үшін бұл экспорттау мақсатын кез келген уақытта Dynamics 365 Customer Insights әкімшісі жоя алады.</span><span class="sxs-lookup"><span data-stu-id="362cf-141">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
