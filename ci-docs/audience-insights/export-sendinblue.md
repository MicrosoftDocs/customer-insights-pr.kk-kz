---
title: Customer Insights деректерін Sendinblue қызметіне экспорттау
description: Sendinblue қызметіне қосылымды және экспорттауды конфигурациялау жолы туралы ақпарат.
ms.date: 06/29/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 58ca0ae5ad4a3a291f4336984d14fefb23a58ab3
ms.sourcegitcommit: 057079532e31c12bac36f374857ba3dc847d6ad0
ms.translationtype: HT
ms.contentlocale: kk-KZ
ms.lasthandoff: 06/29/2021
ms.locfileid: "6314637"
---
# <a name="export-segments-to-sendinblue-preview"></a><span data-ttu-id="c1bb9-103">Сегменттерді Sendinblue қызметіне экспорттау (алдын ала қарау нұсқасы)</span><span class="sxs-lookup"><span data-stu-id="c1bb9-103">Export segments to Sendinblue (preview)</span></span>

<span data-ttu-id="c1bb9-104">Бірыңғай тұтынушы профильдерінің сегменттерін науқандар жасау, электрондық пошта маркетингін қамтамасыз ету және Sendinblue қызметі арқылы тұтынушылардың белгілі бір топтарын қолдану үшін экспорттаңыз.</span><span class="sxs-lookup"><span data-stu-id="c1bb9-104">Export segments of unified customer profiles to generate campaigns, provide email marketing and use specific groups of customers with Sendinblue.</span></span>

## <a name="prerequisites-for-connection"></a><span data-ttu-id="c1bb9-105">Қосылым алғышарттары</span><span class="sxs-lookup"><span data-stu-id="c1bb9-105">Prerequisites for connection</span></span>

-   <span data-ttu-id="c1bb9-106">Сізде [Sendinblue тіркелгісі](https://www.sendinblue.com/) және тиісті әкімші тіркелгі деректері бар.</span><span class="sxs-lookup"><span data-stu-id="c1bb9-106">You have a [Sendinblue account](https://www.sendinblue.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="c1bb9-107">Sendinblue қызметінде бұрыннан бар тізімдер және тиісті идентификаторлар бар.</span><span class="sxs-lookup"><span data-stu-id="c1bb9-107">There are existing lists in Sendinblue and the corresponding IDs.</span></span>
-   <span data-ttu-id="c1bb9-108">Сізде [конфигурацияланған сегменттер](segments.md) бар.</span><span class="sxs-lookup"><span data-stu-id="c1bb9-108">You have [configured segments](segments.md).</span></span>
-   <span data-ttu-id="c1bb9-109">Экспортталған сегменттердегі тұтынушылардың бірыңғай профильдері электрондық пошта мекенжайын көрсететін өрістен тұрады.</span><span class="sxs-lookup"><span data-stu-id="c1bb9-109">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="c1bb9-110">Белгілі шектеулер</span><span class="sxs-lookup"><span data-stu-id="c1bb9-110">Known limitations</span></span>

- <span data-ttu-id="c1bb9-111">Sendinblue қызметіне бір экспорттағанда 1 миллион профиль экспорттауға болады.</span><span class="sxs-lookup"><span data-stu-id="c1bb9-111">Up to 1 million profiles per export to Sendinblue.</span></span>
- <span data-ttu-id="c1bb9-112">Sendinblue қызметіне экспорттау сегменттермен шектеледі.</span><span class="sxs-lookup"><span data-stu-id="c1bb9-112">Exporting to Sendinblue is limited to segments.</span></span>
- <span data-ttu-id="c1bb9-113">Жалпы 1 миллион профилі бар сегменттерді экспорттауға 90 минут кетуі мүмкін.</span><span class="sxs-lookup"><span data-stu-id="c1bb9-113">Exporting segments with a total of 1 million profiles can take up to 90 minutes.</span></span> 
- <span data-ttu-id="c1bb9-114">Sendinblue қызметіне экспорттауға болатын профильдер саны Sendinblue қызметімен келісімшартқа байланысты және сонымен шектеулі.</span><span class="sxs-lookup"><span data-stu-id="c1bb9-114">The number of profiles that you can export to Sendinblue is dependent and limited on your contract with Sendinblue.</span></span>

## <a name="set-up-connection-to-sendinblue"></a><span data-ttu-id="c1bb9-115">Sendinblue қызметіне қосылым орнату</span><span class="sxs-lookup"><span data-stu-id="c1bb9-115">Set up connection to Sendinblue</span></span>

1. <span data-ttu-id="c1bb9-116">**Әкімші** > **Қосылымдар** тармағына өтіңіз.</span><span class="sxs-lookup"><span data-stu-id="c1bb9-116">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="c1bb9-117">**Қосылым қосу** түймешігін таңдаңыз және қосылымды конфигурациялау үшін **Sendinblue** қызметін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="c1bb9-117">Select **Add connection** and choose **Sendinblue** to configure the connection.</span></span>

1. <span data-ttu-id="c1bb9-118">**Көрсетілетін аты** өрісінде қосылымға оңай танылатын атау енгізіңіз.</span><span class="sxs-lookup"><span data-stu-id="c1bb9-118">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="c1bb9-119">Қосылым атауы мен түрі осы қосылымды сипаттайды.</span><span class="sxs-lookup"><span data-stu-id="c1bb9-119">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="c1bb9-120">Қосылымның мақсатын түсіндіретін атауды таңдауды ұсынамыз.</span><span class="sxs-lookup"><span data-stu-id="c1bb9-120">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="c1bb9-121">Осы қосылымды кім пайдалана алатынын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="c1bb9-121">Choose who can use this connection.</span></span> <span data-ttu-id="c1bb9-122">Әдепкі бойынша бұл тек әкімшілер.</span><span class="sxs-lookup"><span data-stu-id="c1bb9-122">By default it's only administrators.</span></span> <span data-ttu-id="c1bb9-123">Қосымша ақпарат алу үшін [Салымшыларға экспорттау үшін қосылымды пайдалануға рұқсат беру](connections.md#allow-contributors-to-use-a-connection-for-exports) бөлімін қараңыз.</span><span class="sxs-lookup"><span data-stu-id="c1bb9-123">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="c1bb9-124">**[SendinBlue API кілтін](https://developers.sendinblue.com/docs/getting-started#:~:text=Get%20your%20API%20key&text=You%20can%20create%20one%20from,your%20settings%20This%20API%20key)** енгізіңіз.</span><span class="sxs-lookup"><span data-stu-id="c1bb9-124">Enter your **[SendinBlue API key](https://developers.sendinblue.com/docs/getting-started#:~:text=Get%20your%20API%20key&text=You%20can%20create%20one%20from,your%20settings%20This%20API%20key)**.</span></span>

1. <span data-ttu-id="c1bb9-125">**Деректердің құпиялығы және сәйкестігі** бөлімін растау үшін **Келісемін** құсбелгісін қойыңыз және Sendinblue қызметіне қосылымды баптандыру үшін **Қосылу** түймешігін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="c1bb9-125">Select **I agree** to confirm the **Data privacy and compliance** and select **Connect** to initialize the connection to Sendinblue.</span></span>

1. <span data-ttu-id="c1bb9-126">**Өзіңізді экспорт пайдаланушысы ретінде қосу** пәрменін таңдап, өзіңіздің Customer Insights тіркелгі деректерін ұсыныңыз.</span><span class="sxs-lookup"><span data-stu-id="c1bb9-126">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="c1bb9-127">Қосылымды аяқтау үшін **Сақтау** түймешігін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="c1bb9-127">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="c1bb9-128">Экспорттауды конфигурациялау</span><span class="sxs-lookup"><span data-stu-id="c1bb9-128">Configure an export</span></span>

<span data-ttu-id="c1bb9-129">Егер сіз осы түрдегі қосылымға қатынаса алсаңыз, сіз бұл экспорттауды конфигурациялай аласыз.</span><span class="sxs-lookup"><span data-stu-id="c1bb9-129">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="c1bb9-130">Қосымша ақпарат алу үшін [Экспорттауды конфигурациялау үшін қажет рұқсаттар](export-destinations.md#set-up-a-new-export) бөлімін қараңыз.</span><span class="sxs-lookup"><span data-stu-id="c1bb9-130">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="c1bb9-131">**Деректер** > **Экспорттау** тармағына өтіңіз.</span><span class="sxs-lookup"><span data-stu-id="c1bb9-131">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="c1bb9-132">Жаңа экспорттау жасау үшін **Мақсатты орын қосу** түймешігін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="c1bb9-132">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="c1bb9-133">**Экспорттауға арналған қосылым** өрісінде Sendinblue бөлімінен қосылым таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="c1bb9-133">In the **Connection for export** field, choose a connection from the Sendinblue section.</span></span> <span data-ttu-id="c1bb9-134">Егер сіз осы бөлімнің атын көрмесеңіз, сізге қолжетімді осы түрдегі қосылым жоқ.</span><span class="sxs-lookup"><span data-stu-id="c1bb9-134">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="c1bb9-135">**Sendinblue тізімінің идентификаторы** параметрін енгізіңіз</span><span class="sxs-lookup"><span data-stu-id="c1bb9-135">Enter your **Sendinblue list ID**</span></span> 

1. <span data-ttu-id="c1bb9-136">**Деректерді салыстыру** бөліміндегі **Электрондық пошта** өрісінде тұтынушының электрондық пошта мекенжайын көрсететін бірыңғай тұтынушы профиліндегі өрісті таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="c1bb9-136">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> 

1. <span data-ttu-id="c1bb9-137">Таңдау бойынша жеке электронды хаттар жасау үшін **Аты**, **Тегі** және **Телефон** өрістерін экспорттауға болады.</span><span class="sxs-lookup"><span data-stu-id="c1bb9-137">Optionally, you can export **First name**, **Last name**, and **Phone**  to create more personalized emails.</span></span> <span data-ttu-id="c1bb9-138">Осы өрістерді салыстыру үшін **Төлсипат қосу** пәрменін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="c1bb9-138">Select **Add attribute** to map these fields.</span></span>

1. <span data-ttu-id="c1bb9-139">Экспорттау керек сегменттерді таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="c1bb9-139">Select the segments you want to export.</span></span> 

1. <span data-ttu-id="c1bb9-140">**Сақтау** опциясын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="c1bb9-140">Select **Save**.</span></span>

<span data-ttu-id="c1bb9-141">Экспорттауды сақтау экспорттауды бірден іске қоспайды.</span><span class="sxs-lookup"><span data-stu-id="c1bb9-141">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="c1bb9-142">Экспорттау әр [жоспарланған жаңартумен](system.md#schedule-tab) іске қосылады.</span><span class="sxs-lookup"><span data-stu-id="c1bb9-142">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="c1bb9-143">Сондай-ақ [деректерді сұрау бойынша экспорттауға](export-destinations.md#run-exports-on-demand) болады.</span><span class="sxs-lookup"><span data-stu-id="c1bb9-143">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="c1bb9-144">Деректердің құпиялылығы мен сәйкестігі</span><span class="sxs-lookup"><span data-stu-id="c1bb9-144">Data privacy and compliance</span></span>

<span data-ttu-id="c1bb9-145">Dynamics 365 Customer Insights бағдарламасын деректерді Sendinblue қызметіне тасымалдау үшін қосқан кезде, жеке деректер сияқты ықтимал құпия деректерді қоса алғанда сіз Dynamics 365 Customer Insights бағдарламасы үшін деректерді сәйкестік шекарасынан тыс тасымалдауға рұқсат бересіз.</span><span class="sxs-lookup"><span data-stu-id="c1bb9-145">When you enable Dynamics 365 Customer Insights to transmit data to Sendinblue, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="c1bb9-146">Microsoft мұндай деректерді сіздің нұсқауыңыз бойынша тасымалдайды, бірақ сіз Sendinblue қызметінің сізде болуы мүмкін кез келген құпиялылық немесе қауіпсіздік міндеттемелерін орындауын қамтамасыз етуіне жауаптысыз.</span><span class="sxs-lookup"><span data-stu-id="c1bb9-146">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Sendinblue meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="c1bb9-147">Қосымша ақпаратты [Microsoft құпиялық туралы мәлімдемесі](https://go.microsoft.com/fwlink/?linkid=396732) бөлімінен қараңыз.</span><span class="sxs-lookup"><span data-stu-id="c1bb9-147">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="c1bb9-148">Бұл функцияны тоқтату үшін бұл экспорттау мақсатын кез келген уақытта Dynamics 365 Customer Insights әкімшісі жоя алады.</span><span class="sxs-lookup"><span data-stu-id="c1bb9-148">Your Dynamics 365 Customer Insights administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
