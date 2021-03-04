---
title: Customer Insights деректерін Facebook жарнама менеджеріне экспорттау
description: Facebook жарнамалар менеджерімен байланысты теңшеу жолы туралы ақпарат.
ms.date: 06/05/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: c839f9dc7e403412c0e3d936392d45a43bc63545
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: kk-KZ
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269981"
---
# <a name="connector-for-facebook-ads-manager-preview"></a><span data-ttu-id="d4b27-103">Facebook жарнамалар менеджерінің коннекторы (алдын ала қарау)</span><span class="sxs-lookup"><span data-stu-id="d4b27-103">Connector for Facebook Ads Manager (preview)</span></span>

<span data-ttu-id="d4b27-104">Facebook және Instagram желісінде науқандар жасау үшін Facebook жарнамалар менеджеріне біріккен тұтынушы профильдерінің сегменттерін экспорттаңыз.</span><span class="sxs-lookup"><span data-stu-id="d4b27-104">Export segments of unified customer profiles to Facebook Ads Manager to create campaigns on Facebook and Instagram.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="d4b27-105">Алғышарттар</span><span class="sxs-lookup"><span data-stu-id="d4b27-105">Prerequisites</span></span>

- <span data-ttu-id="d4b27-106">Сізде [**Facebook бизнес тіркелгісінен**](https://business.facebook.com/) тұратын [**Facebook жарнама тіркелгісі**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account) болуы керек.</span><span class="sxs-lookup"><span data-stu-id="d4b27-106">You need to have a [**Facebook Ad Account**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account) which includes a [**Facebook Business Account**](https://business.facebook.com/).</span></span>
- <span data-ttu-id="d4b27-107">[**Facebook жарнама тіркелгісінде**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account) әкімші болуыңыз керек.</span><span class="sxs-lookup"><span data-stu-id="d4b27-107">You need to be an administrator on the [**Facebook Ad Account**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account).</span></span>

## <a name="connect-to-facebook-ads-manager"></a><span data-ttu-id="d4b27-108">Facebook жарнамалар менеджеріне қосылу</span><span class="sxs-lookup"><span data-stu-id="d4b27-108">Connect to Facebook Ads Manager</span></span>

1. <span data-ttu-id="d4b27-109">**Әкімші** > **Экспорттық межелі орындар** тармағына өтіңіз.</span><span class="sxs-lookup"><span data-stu-id="d4b27-109">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="d4b27-110">**Facebook жарнамалар менеджері** астынан **Орнату** параметрін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="d4b27-110">Under **Facebook Ads Manager**, select **Set up**.</span></span>

1. <span data-ttu-id="d4b27-111">**Көрсетілетін атауы** өрісінде экспорттық межелі орынға танылатын атау беріңіз.</span><span class="sxs-lookup"><span data-stu-id="d4b27-111">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="d4b27-112">Facebook жарнама тіркелгісіне кіру үшін **Facebook көмегімен қосылу** параметрін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="d4b27-112">Select **Continue with Facebook** to sign in to your Facebook Ad Account.</span></span>

1. <span data-ttu-id="d4b27-113">Facebook көмегімен аутентификациялағаннан кейін, **ads_management** рұқсатына мүмкіндік беріңіз.</span><span class="sxs-lookup"><span data-stu-id="d4b27-113">Allow the **ads_management** permission after authenticating with Facebook.</span></span>

1. <span data-ttu-id="d4b27-114">Жұмыс істеу қажет **Facebook жарнамалар тіркелгісі** параметрін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="d4b27-114">Select the **Facebook Ads Account** that you want to work with.</span></span>

1. <span data-ttu-id="d4b27-115">Ашылмалы тізімнен **Бұрыннан бар реттелетін аудитория** параметрін таңдаңыз немесе **Жаңа реттелетін аудитория** жасаңыз.</span><span class="sxs-lookup"><span data-stu-id="d4b27-115">Select an **Existing custom audience** from the drop-down list or create a **New custom audience**.</span></span> <span data-ttu-id="d4b27-116">Қосымша ақпаратты [**Facebook жарнамалар менеджеріндегі аудиториялар**](https://www.facebook.com/business/help/744354708981227?id=2469097953376494) бөлімінен қараңыз.</span><span class="sxs-lookup"><span data-stu-id="d4b27-116">For more information, see [**Audiences in Facebook Ads Manager**](https://www.facebook.com/business/help/744354708981227?id=2469097953376494).</span></span>

1. <span data-ttu-id="d4b27-117">**Деректер құпиялығы мен сәйкестігін** растау үшін **Мен келісемін** параметрін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="d4b27-117">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="d4b27-118">Экспорттауды теңшеу үшін **Келесі** параметрін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="d4b27-118">Select **Next** to configure the export.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="d4b27-119">Қосқышты конфигурациялау</span><span class="sxs-lookup"><span data-stu-id="d4b27-119">Configure the connector</span></span>

1. <span data-ttu-id="d4b27-120">**Негізгі идентификатор өрісін таңдау** ішінде Facebook жарнамалар менеджеріне жіберу үшін **Электрондық пошта**, **Аты және мекенжай** немесе **Телефон** параметрін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="d4b27-120">In the **Choose your key identifier field**, select **Email**, **Name and address**, or **Phone** to send to Facebook Ads Manager.</span></span>

1. <span data-ttu-id="d4b27-121">Таңдалған негізгі идентификаторға арналған бірыңғай тұтынушы нысанының тиісті төлсипаттарын салыстырыңыз.</span><span class="sxs-lookup"><span data-stu-id="d4b27-121">Map the corresponding attributes from your unified customer entity for the selected key identifier.</span></span>
   > <span data-ttu-id="d4b27-122">[КЕҢЕС] Негізгі идентификатор ретінде **Электрондық пошта** параметрін таңдасаңыз, үздік сәйкестік мүмкіндіктері орын алады.</span><span class="sxs-lookup"><span data-stu-id="d4b27-122">[TIP] The best chances for a match occur if you select **Email** as key identifier.</span></span> <span data-ttu-id="d4b27-123">Қосымша идентификаторларды қосу сәйкестікті жақсартуы мүмкін.</span><span class="sxs-lookup"><span data-stu-id="d4b27-123">Adding additional identifiers may improve the matching.</span></span>

1. <span data-ttu-id="d4b27-124">Facebook жарнамалар менеджеріне жіберілетін қосымша төлсипаттарды салыстыру үшін **Төлсипат қосу** параметрін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="d4b27-124">Select **Add attribute** to map additional attributes to send to Facebook Ads Manager.</span></span> <span data-ttu-id="d4b27-125">Facebook жарнамалар менеджерінің төлсипаттары мына пайдаланушыға таныс аттармен салыстырылады: **FN** = **Аты**, **LN** = **Тегі**, **FI** = **Бірінші инициал**, **PHONE** = **Телефон**, **GEN** = **Жынысы**, **DOB** = **Туған күн**, **ST** = **Облыс**, **CT** = **Қала**, **ZIP** = **Пошта индексі**, **COUNTRY** = **Ел/аймақ**</span><span class="sxs-lookup"><span data-stu-id="d4b27-125">Attributes from Facebook Ads Manager are mapping to the following user friendly names: **FN** = **First Name**, **LN** = **Last Name**, **FI** = **First Initial**, **PHONE** = **Phone**, **GEN** = **Gender**, **DOB** = **Date of birth**, **ST** = **State**, **CT** = **City**, **ZIP** = **Postal code / Zip code**, **COUNTRY** = **Country / Region**</span></span>

1. <span data-ttu-id="d4b27-126">Экспорттау керек сегменттерді таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="d4b27-126">Select the segments you want to export.</span></span>

1. <span data-ttu-id="d4b27-127">**Сақтау** опциясын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="d4b27-127">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="d4b27-128">Деректерді экспорттау</span><span class="sxs-lookup"><span data-stu-id="d4b27-128">Export the data</span></span>

<span data-ttu-id="d4b27-129">[Сұрау бойынша деректерді экспорттауға](export-destinations.md) болады.</span><span class="sxs-lookup"><span data-stu-id="d4b27-129">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="d4b27-130">Экспорттау сондай-ақ әрбір [жоспарланған жаңарту](system.md#schedule-tab) сайын іске қосылады.</span><span class="sxs-lookup"><span data-stu-id="d4b27-130">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="d4b27-131">Белгілі шектеулер</span><span class="sxs-lookup"><span data-stu-id="d4b27-131">Known limitations</span></span>

- <span data-ttu-id="d4b27-132">Facebook жарнама менеджеріне экспорттаудағы 10 миллионға дейінгі тұтынушы профилі</span><span class="sxs-lookup"><span data-stu-id="d4b27-132">Up to 10 million customer profile per export to Facebook Ads Manager</span></span> 
- <span data-ttu-id="d4b27-133">Facebook жарнама менеджеріне экспорттау сегменттермен шектеледі</span><span class="sxs-lookup"><span data-stu-id="d4b27-133">Export to Facebook Ads Manager is limited to segments</span></span>
- <span data-ttu-id="d4b27-134">Жалпы саны 10 миллион профилі бар сегменттерді экспорттауды аяқтау 90 минутқа созылуы мүмкін</span><span class="sxs-lookup"><span data-stu-id="d4b27-134">Exporting segments with a total of 10 million profiles can take up to 90 minutes to complete</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="d4b27-135">Деректердің құпиялылығы мен сәйкестігі</span><span class="sxs-lookup"><span data-stu-id="d4b27-135">Data privacy and compliance</span></span>

<span data-ttu-id="d4b27-136">Деректерді Facebook жарнама менеджеріне жіберу үшін Dynamics 365 Customer Insights бағдарламасын қосқан кезде, Dynamics 365 Customer Insights талаптарына сәйкестік шекарасынан тыс деректерді, соның ішінде жеке деректер сияқты ықтимал құпия деректерді беруге мүмкіндік бересіз.</span><span class="sxs-lookup"><span data-stu-id="d4b27-136">When you enable Dynamics 365 Customer Insights to transmit data to Facebook Ads Manager, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="d4b27-137">Microsoft мұндай деректерді сіздің нұсқауыңыз бойынша тасымалдайды, бірақ Facebook жарнамаларының кез келген құпиялылық немесе қауіпсіздік міндеттемелеріне сәйкес келуіне жауап бересіз.</span><span class="sxs-lookup"><span data-stu-id="d4b27-137">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Facebook Ads meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="d4b27-138">Қосымша ақпаратты [Microsoft құпиялық туралы мәлімдемесі](https://go.microsoft.com/fwlink/?linkid=396732) бөлімінен қараңыз.</span><span class="sxs-lookup"><span data-stu-id="d4b27-138">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="d4b27-139">Бұл функцияны тоқтату үшін бұл экспорттау мақсатын кез келген уақытта Dynamics 365 Customer Insights әкімшісі жоя алады.</span><span class="sxs-lookup"><span data-stu-id="d4b27-139">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]