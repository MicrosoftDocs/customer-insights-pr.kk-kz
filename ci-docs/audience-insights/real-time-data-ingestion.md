---
title: Нақты уақыттағы деректерді қабылдау және шектеулер
description: Аудитория түсініктеріндегі нақты уақыттағы мүмкіндіктер туралы жалпы ақпарат.
ms.date: 10/27/2020
ms.reviewer: nikeller
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 7421ed9d2cb399d546815b2d1b0ea5ec51ca6b6d
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: kk-KZ
ms.lasthandoff: 02/15/2021
ms.locfileid: "5270287"
---
# <a name="real-time-data-ingestion-preview"></a><span data-ttu-id="ea489-103">Нақты уақыттағы деректерді қабылдау (алдын-ала қарау)</span><span class="sxs-lookup"><span data-stu-id="ea489-103">Real-time data ingestion (preview)</span></span>

<span data-ttu-id="ea489-104">Нақты уақыт функционалдылығы бірнеше секунд ішінде тұтынушыларыңыздың сіздің өнімдеріңіз немесе қызметтеріңізбен жасаған өзара әрекеттестіктерді көруге мүмкіндік береді.</span><span class="sxs-lookup"><span data-stu-id="ea489-104">The near real-time functionality lets you see, within seconds, the latest interactions that your customers have made with your products or services.</span></span>

<span data-ttu-id="ea489-105">[Жоспарланған жаңартулар](system.md#schedule-tab) қойыншасы көптеген жазбалар мен бірнеше күрделі операцияларды қамтиды.</span><span class="sxs-lookup"><span data-stu-id="ea489-105">[Scheduled refreshes](system.md#schedule-tab) include large numbers of records and several complex operations.</span></span> <span data-ttu-id="ea489-106">Алдымен деректер деректер көзінен алынады.</span><span class="sxs-lookup"><span data-stu-id="ea489-106">First, data is pulled from the data source.</span></span> <span data-ttu-id="ea489-107">Әрі қарай деректер біріктіріліп, одан кейін қосымша мәліметтермен толықтырылады.</span><span class="sxs-lookup"><span data-stu-id="ea489-107">Next, the data is unified, and then enriched with additional information.</span></span> <span data-ttu-id="ea489-108">Бұл процесті әр іске қосу бірнеше минуттан сағатқа созылуы мүмкін.</span><span class="sxs-lookup"><span data-stu-id="ea489-108">Every run of this process can take minutes to hours.</span></span>

<span data-ttu-id="ea489-109">Кезекті жоспарланған жаңарту деректерді деректер көзінен шығарғанша, нақты уақыттағы функционалдылық бұл деректерді дереу тұтынуға мүмкіндік береді.</span><span class="sxs-lookup"><span data-stu-id="ea489-109">The real-time functionality provides data immediately for consumption, until the subsequent scheduled refresh pulls this data from the data source.</span></span>

<span data-ttu-id="ea489-110">Нақты уақыттағы жаңартулардың жарамдылық мерзімі бар, содан кейін олар деректер көзінен мәндерді алдын ала анықтамайды:</span><span class="sxs-lookup"><span data-stu-id="ea489-110">Real-time updates have an expiration time after which they no longer override the value from the data source:</span></span>

- <span data-ttu-id="ea489-111">Профиль жаңартулары 4 сағат бойы сақталады</span><span class="sxs-lookup"><span data-stu-id="ea489-111">Profile updates will be kept for 4 hours</span></span>
- <span data-ttu-id="ea489-112">Әрекеттер 30 күн бойы сақталады</span><span class="sxs-lookup"><span data-stu-id="ea489-112">Activities will be kept for 30 days</span></span>

<span data-ttu-id="ea489-113">Бұл мәндер сіз өзгерте алатын API қоңырау параметрлері болып табылады.</span><span class="sxs-lookup"><span data-stu-id="ea489-113">These values are API call parameters that you can change.</span></span> <span data-ttu-id="ea489-114">Олар сіздің бастапқы деректеріңіз шындық көзі болып қалуын қамтамасыз етуге бағытталған.</span><span class="sxs-lookup"><span data-stu-id="ea489-114">They aim to ensure that your source data remains your source of truth.</span></span> <span data-ttu-id="ea489-115">Нақты уақыттағы жаңартуларды ұзақ уақытқа қосу қажет болса, оларды келесі жоспарланған жаңарту кезінде алынатындай деректер көзіне қосу қажет.</span><span class="sxs-lookup"><span data-stu-id="ea489-115">If you want real-time updates to be included for longer, you need to add them to a data source so they get pulled during the next scheduled refresh.</span></span>

## <a name="real-time-update-of-the-unified-customer-profile-fields"></a><span data-ttu-id="ea489-116">Тұтынушы профилінің бірыңғай өрістерін нақты уақытта жаңарту</span><span class="sxs-lookup"><span data-stu-id="ea489-116">Real-time update of the unified customer profile fields</span></span>

<span data-ttu-id="ea489-117">Жаңартылған профильдер бірнеше секунд ішінде тұтынушы картасының көрінісінде немесе кез келген басқа көрнекі бейнеде көрінеді.</span><span class="sxs-lookup"><span data-stu-id="ea489-117">Updated profiles will show in the customer card view, or any other visualization, within a few seconds.</span></span>

<span data-ttu-id="ea489-118">Нақты уақыттағы операциялар деректерді біріктіру аяқталғаннан кейін жүзеге асырылатындықтан, олар тек бірыңғай тұтынушы профильдеріне қолданылады.</span><span class="sxs-lookup"><span data-stu-id="ea489-118">Because real-time operations take place after the data unification has happened, they only apply to the unified customer profiles.</span></span> <span data-ttu-id="ea489-119">Демек, нақты уақыттағы профиль өзгерістері өлшемдерді, сегменттің мүшелігін немесе толықтыруларды жаңартпайды.</span><span class="sxs-lookup"><span data-stu-id="ea489-119">Consequently, real-time profile changes will not update measures, segment membership, or enrichments.</span></span>

### <a name="limitations"></a><span data-ttu-id="ea489-120">Шектеулер</span><span class="sxs-lookup"><span data-stu-id="ea489-120">Limitations</span></span>

- <span data-ttu-id="ea489-121">Тұтынушы профильдерін жаңартуға болады, бірақ жасалмайды немесе жойылмайды.</span><span class="sxs-lookup"><span data-stu-id="ea489-121">Customer profiles can be updated, but not created or deleted.</span></span>
- <span data-ttu-id="ea489-122">Нақты уақыттағы жаңартуларды Power BI сияқты сыртқы жүйелерге экспорттау қазіргі уақытта мүмкін емес.</span><span class="sxs-lookup"><span data-stu-id="ea489-122">Exporting real-time updates to external systems, like Power BI, is not possible at the moment.</span></span>

## <a name="real-time-creation-of-activities"></a><span data-ttu-id="ea489-123">Әрекеттерді нақты уақытта жасау</span><span class="sxs-lookup"><span data-stu-id="ea489-123">Real-time creation of activities</span></span>

<span data-ttu-id="ea489-124">Нақты уақыттағы API бастапқы жүйеден (жеке бастапқы жазба) бірыңғай тұтынушы профиліне дейінгі жаңа әрекетті жариялауға мүмкіндік береді.</span><span class="sxs-lookup"><span data-stu-id="ea489-124">The real-time API lets you publish a new activity from your source system (an individual source record) to a unified customer profile.</span></span> <span data-ttu-id="ea489-125">Жаңа әрекет біртұтас тұтынушы профилінің уақыт шкаласында біртұтас әрекет ретінде бірнеше секунд ішінде қолжетімді болады.</span><span class="sxs-lookup"><span data-stu-id="ea489-125">The new activity will be available as a unified activity in that unified customer profile's timeline within seconds.</span></span> <span data-ttu-id="ea489-126">Уақыт шкаласын тұтынушы картасының көрінісінен немесе кез келген басқа конфигурациялаған уақыт шкаласының бірігуінен көруге болады.</span><span class="sxs-lookup"><span data-stu-id="ea489-126">You can see the timeline in the customer card view or any other timeline integration you configured.</span></span>

> [!NOTE]
>
> - <span data-ttu-id="ea489-127">Әрекеттер өзгермейді.</span><span class="sxs-lookup"><span data-stu-id="ea489-127">Activities are immutable.</span></span> <span data-ttu-id="ea489-128">Олар жасалғаннан кейін өзгермейді.</span><span class="sxs-lookup"><span data-stu-id="ea489-128">They don't change once created.</span></span>
> - <span data-ttu-id="ea489-129">Қазіргі уақытта сегменттер мен өлшемдер жаңа әрекет негізінде жаңартылмайды.</span><span class="sxs-lookup"><span data-stu-id="ea489-129">Currently, segments and measures won't update based on the new activity.</span></span>
> - <span data-ttu-id="ea489-130">Нақты уақыттағы API арқылы ғана қосылған әрекеттер экспорттың бөлігі болып табылмайды және PowerBI ішінде көрсетілмейді.</span><span class="sxs-lookup"><span data-stu-id="ea489-130">Activities added only through the real-time API are not part of exports and won't show up in PowerBI.</span></span>

<span data-ttu-id="ea489-131">Нақты уақыттағы API интерфейсіне қосылудың екі әдісі бар:</span><span class="sxs-lookup"><span data-stu-id="ea489-131">There are two ways to connect to the real-time API:</span></span>

- <span data-ttu-id="ea489-132">[жанама түрде](#connect-via-the-dynamics-365-customer-insights-connector) [Dynamics 365 Customer Insights қосқышы](https://docs.microsoft.com/connectors/customerinsights/) арқылы</span><span class="sxs-lookup"><span data-stu-id="ea489-132">[indirectly](#connect-via-the-dynamics-365-customer-insights-connector), using the [Dynamics 365 Customer Insights connector](https://docs.microsoft.com/connectors/customerinsights/)</span></span>
- <span data-ttu-id="ea489-133">[тікелей](#connect-directly-to-the-real-time-api), кодпен</span><span class="sxs-lookup"><span data-stu-id="ea489-133">[directly](#connect-directly-to-the-real-time-api), with code</span></span>

<span data-ttu-id="ea489-134">Екі әдіс те келесі алғышарттарға ие:</span><span class="sxs-lookup"><span data-stu-id="ea489-134">Both ways share the following prerequisites:</span></span>

- <span data-ttu-id="ea489-135">Customer Insights бағдарламасының ортасы</span><span class="sxs-lookup"><span data-stu-id="ea489-135">A Customer Insights environment</span></span>
- <span data-ttu-id="ea489-136">Бірыңғай тұтынушы профильдері</span><span class="sxs-lookup"><span data-stu-id="ea489-136">Unified customer profiles</span></span>
- <span data-ttu-id="ea489-137">Конфигурацияланған және орындалатын әрекеттер</span><span class="sxs-lookup"><span data-stu-id="ea489-137">Activities configured and run</span></span>
- <span data-ttu-id="ea489-138">Тіркелгіңіздің түпнұсқалығын растауға арналған салымшы немесе әкімші рұқсаттары</span><span class="sxs-lookup"><span data-stu-id="ea489-138">Contributor or Administrator permissions to authenticate your account</span></span>

## <a name="connect-via-the-dynamics-365-customer-insights-connector"></a><span data-ttu-id="ea489-139">Dynamics 365 Customer Insights қосқышы арқылы қосылыңыз</span><span class="sxs-lookup"><span data-stu-id="ea489-139">Connect via the Dynamics 365 Customer Insights connector</span></span>

<span data-ttu-id="ea489-140">Нақты уақыттағы API деректерді берілген Power Platform қосқышынан, [Dynamics 365 Customer Insights қосқышы](https://docs.microsoft.com/connectors/customerinsights/), қандай да бір кодты жазудың және орналастырудың қажетінсіз қабылдай алады.</span><span class="sxs-lookup"><span data-stu-id="ea489-140">The real-time API can ingest data from a dedicated Power Platform connector, the [Dynamics 365 Customer Insights connector](https://docs.microsoft.com/connectors/customerinsights/), without the need to write and deploy any code.</span></span>    
<span data-ttu-id="ea489-141">Қосқыш API сияқты нақты уақыттағы әрекеттерді орындай алады.</span><span class="sxs-lookup"><span data-stu-id="ea489-141">The connector can do the same real-time actions as the API.</span></span> <span data-ttu-id="ea489-142">Сізге премиум қосқыштар үшін жарамды лицензия қажет.</span><span class="sxs-lookup"><span data-stu-id="ea489-142">You need a valid license for premium connectors.</span></span> <span data-ttu-id="ea489-143">Қосымша ақпарат алу үшін, [Power Apps және Power Automate лицензиялауға қатысты жиі қойылатын сұрақтар](https://docs.microsoft.com/power-platform/admin/powerapps-flow-licensing-faq) бөлімін қараңыз.</span><span class="sxs-lookup"><span data-stu-id="ea489-143">For more information, see [Power Apps and Power Automate licensing FAQs](https://docs.microsoft.com/power-platform/admin/powerapps-flow-licensing-faq).</span></span>

- <span data-ttu-id="ea489-144">Power Platform [Power Apps және/немесе Power Automate](https://docs.microsoft.com/connectors/)</span><span class="sxs-lookup"><span data-stu-id="ea489-144">Power Platform [Power Apps and/or Power Automate](https://docs.microsoft.com/connectors/)</span></span>
- <span data-ttu-id="ea489-145">Azure [Логика бағдарламалары](https://docs.microsoft.com/azure/connectors/apis-list)</span><span class="sxs-lookup"><span data-stu-id="ea489-145">Azure [Logic Apps](https://docs.microsoft.com/azure/connectors/apis-list)</span></span>

<span data-ttu-id="ea489-146">Ағындарды жасау туралы толық мәліметтерді мына жерден қараңыз [Power Automate құжаттамасы](https://docs.microsoft.com/power-automate/).</span><span class="sxs-lookup"><span data-stu-id="ea489-146">For details about creating flows, see the [Power Automate documentation](https://docs.microsoft.com/power-automate/).</span></span>

## <a name="connect-directly-to-the-real-time-api"></a><span data-ttu-id="ea489-147">Нақты уақыттағы API интерфейсіне тікелей қосылыңыз</span><span class="sxs-lookup"><span data-stu-id="ea489-147">Connect directly to the real-time API</span></span>

<span data-ttu-id="ea489-148">Жеке сату үрдісін құру және нақты уақыттағы API интерфейсіне тікелей қосылу арқылы нақты уақыттағы мүмкіндіктерді пайдалануға болады.</span><span class="sxs-lookup"><span data-stu-id="ea489-148">You can use the real-time capabilities by building your own pipeline and connecting directly to the real-time API.</span></span>    
<span data-ttu-id="ea489-149">Әрекетті бастапқы жүйенің пішімінде немесе UnifiedActivity пішімінде жариялауға болады.</span><span class="sxs-lookup"><span data-stu-id="ea489-149">You can post an activity in the format of your source system or in the UnifiedActivity format.</span></span> <span data-ttu-id="ea489-150">Пішімді /api/instances/{instanceId}/manage/entities/UnifiedActivity тармағына API қоңырауын жасау арқылы алыңыз.</span><span class="sxs-lookup"><span data-stu-id="ea489-150">Get the format by making an API call to /api/instances/{instanceId}/manage/entities/UnifiedActivity.</span></span>

<span data-ttu-id="ea489-151">Параметрлер мен жауаптарды қоса алғанда, осы API туралы толық ақпаратты [Customer Insights API интерфейстері сілтемесіндегі](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights) **EntityData** бөлімінен табуға болады.</span><span class="sxs-lookup"><span data-stu-id="ea489-151">Details of this API, including parameters and responses, can be found in the **EntityData** section on the [Customer Insights APIs reference](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights).</span></span> <span data-ttu-id="ea489-152">Қосымша ақпарат алу үшін [Customer Insights API интерфейстерімен жұмыс істеу](apis.md) бөлімін қараңыз.</span><span class="sxs-lookup"><span data-stu-id="ea489-152">For more information, see [Work with Customer Insights APIs](apis.md).</span></span>

## <a name="understand-your-real-time-usage-with-telemetry"></a><span data-ttu-id="ea489-153">Телеметриямен нақты уақыт қолданысын түсіну</span><span class="sxs-lookup"><span data-stu-id="ea489-153">Understand your real-time usage with telemetry</span></span>

<span data-ttu-id="ea489-154">Нақты уақыттағы API сұрауларының көлеміне шолу жасаңыз және жүйе кездестіруі мүмкін мәселелер туралы ақпарат алыңыз.</span><span class="sxs-lookup"><span data-stu-id="ea489-154">Get an overview of the volume of requests to the real-time API and information about issues the system may encounter.</span></span> <span data-ttu-id="ea489-155">[Нақты уақыттағы телеметрияға қол жеткізуге](system.md#api-usage-tab) болады.</span><span class="sxs-lookup"><span data-stu-id="ea489-155">You can [access the real-time telemetry](system.md#api-usage-tab).</span></span> 


[!INCLUDE[footer-include](../includes/footer-banner.md)]