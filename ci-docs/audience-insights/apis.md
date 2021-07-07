---
title: API интерфейсімен жұмыс істеу
description: API пайдаланып, шектеулерді түсініңіз.
ms.date: 05/10/2021
ms.reviewer: wimohabb
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
ms.openlocfilehash: 9326f821f9970ba2254ab804814e369abb677eb0
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: kk-KZ
ms.lasthandoff: 06/24/2021
ms.locfileid: "6304749"
---
# <a name="work-with-customer-insights-apis"></a><span data-ttu-id="8be10-103">Customer Insights API жүйесімен жұмыс істеу</span><span class="sxs-lookup"><span data-stu-id="8be10-103">Work with Customer Insights APIs</span></span>

<span data-ttu-id="8be10-104">Dynamics 365 Customer Insights бағдарламасы Customer Insights ішіндегі деректер негізінде жеке бағдарламаларды жасау үшін API интерфейстерін ұсынады.</span><span class="sxs-lookup"><span data-stu-id="8be10-104">Dynamics 365 Customer Insights provides APIs to build your own applications based on your data in Customer Insights.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="8be10-105">Осы API интерфейстерін туралы толық мәліметтер [Customer Insights API интерфейстері анықтамасы](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights) бөлімінде көрсетілген.</span><span class="sxs-lookup"><span data-stu-id="8be10-105">Details of these APIs are listed on the [Customer Insights APIs reference](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights).</span></span> <span data-ttu-id="8be10-106">Олар операциялар, параметрлер және жауаптар туралы қосымша ақпаратты қамтиды.</span><span class="sxs-lookup"><span data-stu-id="8be10-106">They include additional information about operations, parameters, and responses.</span></span>

<span data-ttu-id="8be10-107">Бұл мақалада Customer Insights API интерфейстеріне қатынасу, Azure бағдарламасын тіркеу және қолжетімді клиенттік кітапханалармен жұмыс бастау жолы сипатталған.</span><span class="sxs-lookup"><span data-stu-id="8be10-107">This article describes how to access the Customer Insights APIs, create an Azure App Registration, and get started with the available client libraries.</span></span>

## <a name="get-started-trying-the-customer-insights-apis"></a><span data-ttu-id="8be10-108">Customer Insights API интерфейстерін қолдануды бастаңыз</span><span class="sxs-lookup"><span data-stu-id="8be10-108">Get started trying the Customer Insights APIs</span></span>

1. <span data-ttu-id="8be10-109">Customer Insights жүйесіне [қосылыңыз](https://home.ci.ai.dynamics.com).</span><span class="sxs-lookup"><span data-stu-id="8be10-109">[Sign in](https://home.ci.ai.dynamics.com) to Customer Insights.</span></span> <span data-ttu-id="8be10-110">Егер сізде әлі жазылым болмаса, [Customer Insights бағдарламасының сынақ нұсқасына жазылыңыз](https://aka.ms/tryci).</span><span class="sxs-lookup"><span data-stu-id="8be10-110">If you don't have a subscription yet, [sign up for a trial of Customer Insights](https://aka.ms/tryci).</span></span>

1. <span data-ttu-id="8be10-111">Customer Insights ортасында API элементтерін қосу үшін **Әкімші** > **Рұқсаттар** тармағына өтіңіз.</span><span class="sxs-lookup"><span data-stu-id="8be10-111">To enable APIs on your Customer Insights environment, go to **Admin** > **Permissions**.</span></span> <span data-ttu-id="8be10-112">Ол үшін сізге әкімші рұқсаттары қажет.</span><span class="sxs-lookup"><span data-stu-id="8be10-112">You'll need admin permissions to do so.</span></span>

1. <span data-ttu-id="8be10-113">**API** қойындысына өтіп, **Қосу** түймесін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="8be10-113">Go to the **APIs** tab and select the **Enable** button.</span></span>    
 
   <span data-ttu-id="8be10-114">API элементін қосу API сұрауларында пайдаланылатын данаға арналған негізгі және қосымша жазылым кілтін жасайды.</span><span class="sxs-lookup"><span data-stu-id="8be10-114">Enabling the APIs creates a primary and secondary subscription key for your instance that gets used in the API requests.</span></span> <span data-ttu-id="8be10-115">**Әкімші** > **Рұқсаттар** > **API интерфейстері** тармағында **Негізгісін қайта құру** немесе **Қосымшасын қайта құру** опцияларын таңдау арқылы кілттерді қайта құруға болады.</span><span class="sxs-lookup"><span data-stu-id="8be10-115">You can regenerate the keys by selecting the **Regenerate primary** or **Regenerate secondary** on **Admin** > **Permissions** > **APIs**.</span></span>

   :::image type="content" source="media/enable-apis.gif" alt-text="Customer Insights API интерфейстерін қосу":::

1. <span data-ttu-id="8be10-117">[API интерфейстерін сынап көру](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights&operation=Get-all-instances) үшін **Біздің API интерфейсімізді зерттеу** опциясын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="8be10-117">Select **Explore our APIs** to [try out the APIs](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights&operation=Get-all-instances).</span></span>

1. <span data-ttu-id="8be10-118">API операциясын таңдап, **Сынап көру** опциясын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="8be10-118">Choose an API operation and select **Try it**.</span></span>

1. <span data-ttu-id="8be10-119">Бүйірлік тақтада **Авторизация** ашылмалы мәзіріндегі мәнді **жасырын** мәніне орнатыңыз.</span><span class="sxs-lookup"><span data-stu-id="8be10-119">In the side pane, set the value in the **Authorization** dropdown menu to **implicit**.</span></span> <span data-ttu-id="8be10-120">`Authorization` тақырыбы тасушы таңбалауышымен қосылады.</span><span class="sxs-lookup"><span data-stu-id="8be10-120">The `Authorization` header gets added with a bearer token.</span></span> <span data-ttu-id="8be10-121">Жазылым кілті автоматты түрде толтырылады.</span><span class="sxs-lookup"><span data-stu-id="8be10-121">Your subscription key will be automatically populated.</span></span>
  
1. <span data-ttu-id="8be10-122">Оған қоса, қажетті барлық сұрау параметрлерін қосыңыз.</span><span class="sxs-lookup"><span data-stu-id="8be10-122">Optionally, add all necessary query parameters.</span></span>

1. <span data-ttu-id="8be10-123">Бүйірлік тақтаның төменгі жағына айналдырып, **Жіберу** опциясын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="8be10-123">Scroll to the bottom of the side pane and select **Send**.</span></span>

<span data-ttu-id="8be10-124">HTTP жауабы жақын арада төменде пайда болады.</span><span class="sxs-lookup"><span data-stu-id="8be10-124">The HTTP response will soon appear below.</span></span>

   :::image type="content" source="media/try-apis.gif" alt-text="API интерфейстерін тексеру жолы.":::

## <a name="create-a-new-app-registration-in-the-azure-portal"></a><span data-ttu-id="8be10-126">Azure порталында жаңа бағдарлама тіркелімін жасаңыз</span><span class="sxs-lookup"><span data-stu-id="8be10-126">Create a new app registration in the Azure portal</span></span>

<span data-ttu-id="8be10-127">Бұл қадамдар өкілетті рұқсаттар көмегімен Azure бағдарламасында Customer Insights API интерфейстерін пайдаланумен жұмысты бастауға көмектеседі.</span><span class="sxs-lookup"><span data-stu-id="8be10-127">These steps help you get started with using the Customer Insights APIs in an Azure application using delegated permissions.</span></span> <span data-ttu-id="8be10-128">Алдымен [Жұмысты бастау бөлімін](#get-started-trying-the-customer-insights-apis) толтырғаныңызға көз жеткізіңіз.</span><span class="sxs-lookup"><span data-stu-id="8be10-128">Make sure to complete the [Getting started section](#get-started-trying-the-customer-insights-apis) first.</span></span>

1. <span data-ttu-id="8be10-129">Customer Insights деректеріне кіретін тіркелгімен [Azure порталына](https://portal.azure.com) кіріңіз.</span><span class="sxs-lookup"><span data-stu-id="8be10-129">Sign in to the [Azure portal](https://portal.azure.com) with the account that can access the Customer Insights data.</span></span>

1. <span data-ttu-id="8be10-130">Сол жақта **Бағдарламалар тіркелімі** опциясын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="8be10-130">On the left, select **App registrations**.</span></span>

1. <span data-ttu-id="8be10-131">**Жаңа тіркелім** опциясын таңдап, бағдарлама атауын беріңіз де, тіркелгі түрін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="8be10-131">Select **New registration**, provide an application name and choose the account type.</span></span>
 
   <span data-ttu-id="8be10-132">Оған қоса, URL мекенжайын бағыттауды қосыңыз.</span><span class="sxs-lookup"><span data-stu-id="8be10-132">Optionally, add a redirect URL.</span></span> <span data-ttu-id="8be10-133">http://localhost сайты жергілікті компьютерде бағдарлама әзірлеу үшін жеткілікті.</span><span class="sxs-lookup"><span data-stu-id="8be10-133">http://localhost is sufficient for developing an application on your local computer.</span></span>

1. <span data-ttu-id="8be10-134">Жаңа бағдарлама тіркелімінде **API рұқсаттары** бөліміне өтіңіз.</span><span class="sxs-lookup"><span data-stu-id="8be10-134">On your new App registration, go to **API permissions**.</span></span>

   :::image type="content" source="media/app-registration-1.gif" alt-text="Бағдарламаны тіркеуде API рұқсаттарын орнату жолы.":::

1. <span data-ttu-id="8be10-136">**Рұқсат қосу** опциясын таңдап, бүйірлік тақтада **Customer Insights** опциясын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="8be10-136">Select **Add a permission** and select **Customer Insights** in the side pane.</span></span>

1. <span data-ttu-id="8be10-137">**Рұқсат түрі** үшін **Өкілетті рұқсаттар** параметрін таңдаңыз, содан кейін **user_impersonation** рұқсатын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="8be10-137">For **Permission type**, select **Delegated permissions** and then select the **user_impersonation** permission.</span></span>

1. <span data-ttu-id="8be10-138">**Рұқсаттарды қосу** опциясын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="8be10-138">Select **Add permissions**.</span></span> <span data-ttu-id="8be10-139">Пайдаланушы кірмей-ақ API интерфейсіне қатынасу қажет болса, [Сервераралық бағдарлама рұқсаттары](#server-to-server-application-permissions) бөлімін қарап шығыңыз.</span><span class="sxs-lookup"><span data-stu-id="8be10-139">If you need to access the API without a user signing in, review the [Server-to-server application permissions](#server-to-server-application-permissions) section.</span></span>

1. <span data-ttu-id="8be10-140">Бағдарламаны тіркеуді аяқтау үшін **Әкімші келісімін келесілерге беру...** опциясын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="8be10-140">Select **Grant admin consent for...** to complete the app registration.</span></span>

<span data-ttu-id="8be10-141">Бағдарлама/клиент идентификаторын Microsoft аутентификация кітапханасында (MSAL) тіркеу үшін API интерфейсіне сұранысыңызбен жіберу мақсатында тасушы таңбалауышын алу үшін пайдалануға болады.</span><span class="sxs-lookup"><span data-stu-id="8be10-141">You can use the Application/Client ID for this app registration with the Microsoft Authentication Library (MSAL) to obtain a bearer token to send with your request to the API.</span></span>

:::image type="content" source="media/grant-admin-consent.gif" alt-text="Әкімші келісімін беру жолы.":::

<span data-ttu-id="8be10-143">MSAL туралы қосымша ақпарат алу үшін [Microsoft аутентификация кітапханасына (MSAL) шолу](/azure/active-directory/develop/msal-overview) тақырыбына қараңыз.</span><span class="sxs-lookup"><span data-stu-id="8be10-143">For more information about MSAL, see [Overview of Microsoft Authentication Library (MSAL)](/azure/active-directory/develop/msal-overview).</span></span>

<span data-ttu-id="8be10-144">Бағдарламаны Azure қызметінде тіркеу туралы қосымша ақпаратты [Бағдарламаны тіркеу](/azure/active-directory/develop/quickstart-register-app.md#register-an-application) бөлімінен қараңыз.</span><span class="sxs-lookup"><span data-stu-id="8be10-144">For more information about app registration in Azure, see [Register an application](/azure/active-directory/develop/quickstart-register-app.md#register-an-application).</span></span>

<span data-ttu-id="8be10-145">Біздің клиенттік кітапханаларымызда API интерфейстерін қолдану туралы ақпаратты [Customer Insights клиенттік кітапханалары](#customer-insights-client-libraries) бөлімін қараңыз.</span><span class="sxs-lookup"><span data-stu-id="8be10-145">For information on using the APIs in our client libraries, see [Customer Insights client libraries](#customer-insights-client-libraries).</span></span>

### <a name="server-to-server-application-permissions"></a><span data-ttu-id="8be10-146">Сервераралық бағдарлама рұқсаттары</span><span class="sxs-lookup"><span data-stu-id="8be10-146">Server-to-server application permissions</span></span>

<span data-ttu-id="8be10-147">[Бағдарламаны тіркеу бөлімі](#create-a-new-app-registration-in-the-azure-portal) пайдаланушының аутентификация үшін жүйеге кіруін қажет ететін бағдарламаны тіркеу жолын көрсетеді.</span><span class="sxs-lookup"><span data-stu-id="8be10-147">The [app registration section](#create-a-new-app-registration-in-the-azure-portal) outlines how to register an app that requires a user to sign in for authentication.</span></span> <span data-ttu-id="8be10-148">Пайдаланушының өзара әрекеттестігін қажет етпейтін және серверде жұмыс істей алатын бағдарламаны тіркеу жолын жасау туралы мәлімет алыңыз.</span><span class="sxs-lookup"><span data-stu-id="8be10-148">Learn how to create an app registration that does not need user interaction and can be run on a server.</span></span>

1. <span data-ttu-id="8be10-149">Azure порталында бағдарламаны тіркеуде **API рұқсаттары** бөліміне өтіңіз.</span><span class="sxs-lookup"><span data-stu-id="8be10-149">On your App registration in the Azure portal, go to **API permissions**.</span></span>

1. <span data-ttu-id="8be10-150">**Рұқсат қосу** опциясын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="8be10-150">Select **Add a permission**.</span></span> 

1. <span data-ttu-id="8be10-151">**Менің ұйымым пайдаланатын API интерфейстері** қойыншасын таңдаңыз және тізімнен **Dynamics 365 AI for Customer Insights** бағдарламасын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="8be10-151">Select the **APIs my organization uses** tab and choose **Dynamics 365 AI for Customer Insights** from the list.</span></span> 

1. <span data-ttu-id="8be10-152">**Рұқсат түрі** үшін **Бағдарлама рұқсаттары** параметрін таңдаңыз, содан кейін **CustomerInsights.Api.All** рұқсатын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="8be10-152">For **Permission type**, select **Application permissions** and then select the **CustomerInsights.Api.All** permission.</span></span>

1. <span data-ttu-id="8be10-153">**Рұқсаттарды қосу** опциясын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="8be10-153">Select **Add permissions**.</span></span>

1. <span data-ttu-id="8be10-154">Бағдарламаны тіркеу үшін **API рұқсаттары** бөліміне қайта өтіңіз.</span><span class="sxs-lookup"><span data-stu-id="8be10-154">Go back to **API permissions** for your app registration.</span></span>

1. <span data-ttu-id="8be10-155">Бағдарламаны тіркеуді аяқтау үшін **Әкімші келісімін келесілерге беру...** опциясын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="8be10-155">Select **Grant admin consent for...** to complete the app registration.</span></span>

   :::image type="content" source="media/grant-admin-consent.gif" alt-text="Әкімші келісімін беру жолы.":::

1. <span data-ttu-id="8be10-157">Қорытындылай келе, Customer Insights бағдарламасында пайдаланушы ретінде бағдарламаны тіркеу атауын қосу керек.</span><span class="sxs-lookup"><span data-stu-id="8be10-157">To conclude, we have to add the name of the app registration as a user in Customer Insights.</span></span>  
   
   <span data-ttu-id="8be10-158">Customer Insights бағдарламасын ашып, **Әкімші** > **Рұқсаттар** және **Пайдаланушыны қосу** тармағына өтіңіз.</span><span class="sxs-lookup"><span data-stu-id="8be10-158">Open Customer Insights, go to **Admin** > **Permissions** and select **Add user**.</span></span>

1. <span data-ttu-id="8be10-159">Бағдарламаны тіркеу атауын іздеп, оны іздеу нәтижелерінен таңдап, **Сақтау** түймесін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="8be10-159">Search for the name of your app registration, select it from the search results, and select **Save**.</span></span>

## <a name="customer-insights-client-libraries"></a><span data-ttu-id="8be10-160">Customer Insights клиенттік кітапханалары</span><span class="sxs-lookup"><span data-stu-id="8be10-160">Customer Insights client libraries</span></span>

<span data-ttu-id="8be10-161">Бұл бөлім Customer Insights API интерфейсі үшін қолжетімді клиенттік кітапханаларды пайдалануды бастауға көмектеседі.</span><span class="sxs-lookup"><span data-stu-id="8be10-161">This section helps you get started using the client libraries available for the Customer Insights APIs.</span></span> <span data-ttu-id="8be10-162">Кітапхананың барлық бастапқы коды мен бағдарлама үлгілерін [Customer Insights GitHub бетінен](https://github.com/microsoft/Dynamics365-CustomerInsights-Client-Libraries) табуға болады.</span><span class="sxs-lookup"><span data-stu-id="8be10-162">All library source code and sample applications can be found on the [Customer Insights GitHub page](https://github.com/microsoft/Dynamics365-CustomerInsights-Client-Libraries).</span></span> 

### <a name="c-nuget"></a><span data-ttu-id="8be10-163">C# NuGet</span><span class="sxs-lookup"><span data-stu-id="8be10-163">C# NuGet</span></span>

<span data-ttu-id="8be10-164">NuGet.org. сайтынан C# клиенттік кітапханаларын пайдаланып жұмысты бастау туралы мәлімет алыңыз. NuGet жиынтығы туралы толығырақ ақпарат алу үшін [Microsoft.Dynamics.CustomerInsights.Api](https://www.nuget.org/packages/Microsoft.Dynamics.CustomerInsights.Api/) бөлімін қараңыз.</span><span class="sxs-lookup"><span data-stu-id="8be10-164">Learn how to get started using the C# client libraries from NuGet.org. For more information on the NuGet package, see [Microsoft.Dynamics.CustomerInsights.Api](https://www.nuget.org/packages/Microsoft.Dynamics.CustomerInsights.Api/).</span></span> <span data-ttu-id="8be10-165">Қазіргі уақытта бұл жиынтық netstandard2.0 және netcoreapp2.0 арқаулық жүйелеріне бағытталған.</span><span class="sxs-lookup"><span data-stu-id="8be10-165">Currently, this package targets the netstandard2.0 and netcoreapp2.0 frameworks.</span></span>

#### <a name="add-the-c-client-library-to-a-c-project"></a><span data-ttu-id="8be10-166">C# жобасына C# клиенттік кітапханасын қосыңыз</span><span class="sxs-lookup"><span data-stu-id="8be10-166">Add the C# client library to a C# project</span></span>

1. <span data-ttu-id="8be10-167">Visual Studio бағдарламасында жобаға арналған **NuGet жиынтық менеджері** жүйесін ашыңыз.</span><span class="sxs-lookup"><span data-stu-id="8be10-167">In Visual Studio, open the **NuGet Package Manager** for your project.</span></span>

1. <span data-ttu-id="8be10-168">**Microsoft.Dynamics.CustomerInsights.Api** іздеңіз.</span><span class="sxs-lookup"><span data-stu-id="8be10-168">Search for **Microsoft.Dynamics.CustomerInsights.Api**.</span></span>

1. <span data-ttu-id="8be10-169">Жобаға жиынтық қосу үшін **Орнату** түймесін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="8be10-169">Select **Install** to add the package to the project.</span></span>
 
   <span data-ttu-id="8be10-170">Сонымен қатар **NuGet жиынтық менеджері консолі** жүйесінде мына пәрменді орындаңыз: `Install-Package -Id Microsoft.Dynamics.CustomerInsights.Api -Source nuget.org -ProjectName <project name> [-Version <version>]`</span><span class="sxs-lookup"><span data-stu-id="8be10-170">Alternatively, run this command in the **NuGet Package Manager Console**: `Install-Package -Id Microsoft.Dynamics.CustomerInsights.Api -Source nuget.org -ProjectName <project name> [-Version <version>]`</span></span>

   :::image type="content" source="media/visual-studio-nuget-package.gif" alt-text="Visual Studio жобасына NuGet жиынтығын қосу":::

#### <a name="use-the-c-client-library"></a><span data-ttu-id="8be10-172">C# клиенттік кітапханасын пайдаланыңыз</span><span class="sxs-lookup"><span data-stu-id="8be10-172">Use the C# client library</span></span>

1. <span data-ttu-id="8be10-173">Бұрыннан бар [Azure бағдарламасын тіркеу](#create-a-new-app-registration-in-the-azure-portal) жүйесін пайдаланып `AccessToken` алу үшін [Microsoft аутентификация кітапханасы (MSAL)](/azure/active-directory/develop/msal-overview) пайдаланыңыз.</span><span class="sxs-lookup"><span data-stu-id="8be10-173">Use the [Microsoft Authentication Library (MSAL)](/azure/active-directory/develop/msal-overview) to get an `AccessToken` using your existing [Azure app registration](#create-a-new-app-registration-in-the-azure-portal).</span></span>

1. <span data-ttu-id="8be10-174">Таңбалауышты сәтті аутентификациялап, алғаннан кейін, жаңасын құрастырыңыз немесе **Тасушы <access token>** және **Ocp-Apim-Subscription-Key**, [Customer Insights ортасынан  **жазылым кілті**](#get-started-trying-the-customer-insights-apis) күйлеріне орнатылған қосымша **DefaultRequestHeaders** авторизациясымен бұрыннан бар `HttpClient` пайдаланыңыз.</span><span class="sxs-lookup"><span data-stu-id="8be10-174">After successfully authenticating and acquiring a token, construct a new or use an existing `HttpClient` with the additional **DefaultRequestHeaders "Authorization"** set to **Bearer <access token>** and **Ocp-Apim-Subscription-Key** set to the [**subscription key** from your Customer Insights environment](#get-started-trying-the-customer-insights-apis).</span></span>   
 
   <span data-ttu-id="8be10-175">Қажет болған жағдайда **Авторизация** тақырыбын қалпына келтіріңіз.</span><span class="sxs-lookup"><span data-stu-id="8be10-175">Reset the **Authorization** header when appropriate.</span></span> <span data-ttu-id="8be10-176">Мысалы, таңбалауыш мерзімі аяқталған кезде.</span><span class="sxs-lookup"><span data-stu-id="8be10-176">For example, when the token expired.</span></span>

1. <span data-ttu-id="8be10-177">Осы `HttpClient` парамтерін `CustomerInsights` клиенті құрылымына өткізіңіз.</span><span class="sxs-lookup"><span data-stu-id="8be10-177">Pass this `HttpClient` into the construction of the `CustomerInsights` client.</span></span>

   :::image type="content" source="media/httpclient-sample.png" alt-text="Httpclient үлгісі":::

1. <span data-ttu-id="8be10-179">Клиентпен "кеңейту әдістеріне" қоңырау шалыңыз,—мысалы, `GetAllInstancesAsync`.</span><span class="sxs-lookup"><span data-stu-id="8be10-179">Make calls with the client to the "extension methods"—for example, `GetAllInstancesAsync`.</span></span> <span data-ttu-id="8be10-180">Егер негізгі `Microsoft.Rest.HttpOperationResponse` қатынасу керек болса, "http хабар әдістерін" пайдаланыңыз,—мысалы, `GetAllInstancesWithHttpMessagesAsync`.</span><span class="sxs-lookup"><span data-stu-id="8be10-180">If access to the underlying `Microsoft.Rest.HttpOperationResponse` is preferred, use the "http message methods"—for example, `GetAllInstancesWithHttpMessagesAsync`.</span></span>

1. <span data-ttu-id="8be10-181">Жауап түрі `object` болуы мүмкін, өйткені әдіс бірнеше түрді қайтара алады (мысалы, `IList<InstanceInfo>` және `ApiErrorResult`).</span><span class="sxs-lookup"><span data-stu-id="8be10-181">The response will likely be of type `object` because the method can return multiple types (for example, `IList<InstanceInfo>` and `ApiErrorResult`).</span></span> <span data-ttu-id="8be10-182">Қайтару түрін тексеру үшін нысандарды сол операция үшін [API мәліметтері бетінде](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights) көрсетілген жауап түрлеріне қауіпсіз түрде түрлендіруге болады.</span><span class="sxs-lookup"><span data-stu-id="8be10-182">To check the return type, you can safely cast the objects into the response types specified on the [API details page](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights) for that operation.</span></span>    
   
   <span data-ttu-id="8be10-183">Егер сұрау туралы қосымша ақпарат қажет болса, бастапқы жауап нысанына қол жеткізу үшін  **http хабары әдістерін** пайдаланыңыз.</span><span class="sxs-lookup"><span data-stu-id="8be10-183">If more information on the request is needed, use the **http message methods** to access the raw response object.</span></span>

### <a name="nodejs-package"></a><span data-ttu-id="8be10-184">NodeJS бумасы</span><span class="sxs-lookup"><span data-stu-id="8be10-184">NodeJS package</span></span>

<span data-ttu-id="8be10-185">NPM арқылы қолжетімді NodeJS клиенттік кітапханаларын пайдаланыңыз: https://www.npmjs.com/package/@microsoft/customerinsights</span><span class="sxs-lookup"><span data-stu-id="8be10-185">Use the NodeJS client libraries available through NPM: https://www.npmjs.com/package/@microsoft/customerinsights</span></span>

### <a name="python-package"></a><span data-ttu-id="8be10-186">Python бумасы</span><span class="sxs-lookup"><span data-stu-id="8be10-186">Python package</span></span>

<span data-ttu-id="8be10-187">PyPi арқылы қолжетімді Python клиенттік кітапханаларын пайдаланыңыз: https://pypi.org/project/customerinsights/</span><span class="sxs-lookup"><span data-stu-id="8be10-187">Use the Python client libraries available through PyPi: https://pypi.org/project/customerinsights/</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
