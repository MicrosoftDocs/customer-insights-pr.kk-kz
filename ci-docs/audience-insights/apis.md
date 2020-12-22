---
title: API интерфейсімен жұмыс істеу
description: API пайдаланып, шектеулерді түсініңіз.
ms.date: 12/04/2020
ms.reviewer: wimohabb
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 5a03e916676800afdd8692da865a1060952d5c4f
ms.sourcegitcommit: b50c754481d0af6d0cf4b550775d7b31d95846ef
ms.translationtype: HT
ms.contentlocale: kk-KZ
ms.lasthandoff: 12/06/2020
ms.locfileid: "4689137"
---
# <a name="work-with-customer-insights-apis"></a><span data-ttu-id="f1d68-103">Customer Insights API жүйесімен жұмыс істеу</span><span class="sxs-lookup"><span data-stu-id="f1d68-103">Work with Customer Insights APIs</span></span>

<span data-ttu-id="f1d68-104">Dynamics 365 Customer Insights Customer Insights жүйесіндегі деректер негізінде өз бағдарламаларыңызды құру үшін API ұсынады.</span><span class="sxs-lookup"><span data-stu-id="f1d68-104">Dynamics 365 Customer Insights provides APIs to build your own applications based you data in Customer Insights.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f1d68-105">Осы API элементтері туралы толық мәліметтер [Customer Insights APIs сілтемесінде](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights) көрсетілген.</span><span class="sxs-lookup"><span data-stu-id="f1d68-105">Details of these APIs, are listed on the [Customer Insights APIs reference](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights).</span></span> <span data-ttu-id="f1d68-106">Олар операциялар, параметрлер және жауаптар туралы қосымша ақпаратты қамтиды.</span><span class="sxs-lookup"><span data-stu-id="f1d68-106">They include additional information about operations, parameters, and responses.</span></span>

<span data-ttu-id="f1d68-107">Бұл мақала Customer Insights API интерфейсіне кіруге, Azure бағдарламаларын тіркеуді жасауға және қолжетімді клиенттік кітапханалармен жұмыс жасауға көмектесу үшін нұсқаулық береді.</span><span class="sxs-lookup"><span data-stu-id="f1d68-107">This article guides you to access to the Customer Insights APIs, create an Azure App Registration, and help you get started with the available client libraries.</span></span>

## <a name="get-started-trying-the-customer-insights-apis"></a><span data-ttu-id="f1d68-108">Customer Insights API интерфейстерін қолдануды бастаңыз</span><span class="sxs-lookup"><span data-stu-id="f1d68-108">Get started trying the Customer Insights APIs</span></span>

1. <span data-ttu-id="f1d68-109">Customer Insights жүйесіне [қосылыңыз](https://home.ci.ai.dynamics.com).</span><span class="sxs-lookup"><span data-stu-id="f1d68-109">[Sign in](https://home.ci.ai.dynamics.com) to Customer Insights.</span></span> <span data-ttu-id="f1d68-110">Егер сізде әлі жазылым болмаса, [Customer Insights бағдарламасының сынақ нұсқасына жазылыңыз](https://aka.ms/tryci).</span><span class="sxs-lookup"><span data-stu-id="f1d68-110">If you don't have a subscription yet, [sign up for a trial of Customer Insights](https://aka.ms/tryci).</span></span>

1. <span data-ttu-id="f1d68-111">Customer Insights ортасында API элементтерін қосу үшін **Әкімші** > **Рұқсаттар** тармағына өтіңіз.</span><span class="sxs-lookup"><span data-stu-id="f1d68-111">To enable APIs on your Customer Insights environment, go to **Admin** > **Permissions**.</span></span> <span data-ttu-id="f1d68-112">Ол үшін сізге әкімші рұқсаттары қажет.</span><span class="sxs-lookup"><span data-stu-id="f1d68-112">You'll need admin permissions to do so.</span></span>

1. <span data-ttu-id="f1d68-113">**API** қойындысына өтіп, **Қосу** түймесін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="f1d68-113">Go to the **APIs** tab and select the **Enable** button.</span></span>    
   <span data-ttu-id="f1d68-114">API элементін қосу API сұрауларында пайдаланылатын данаға арналған негізгі және қосымша жазылым кілтін жасайды.</span><span class="sxs-lookup"><span data-stu-id="f1d68-114">Enabling the APIs creates a primary and secondary subscription key for your instance that gets used in the API requests.</span></span> <span data-ttu-id="f1d68-115">**Әкімші** > **Рұқсаттар** > **API интерфейстері** тармағында **Негізгісін қайта құру** немесе **Қосымшасын қайта құру** опцияларын таңдау арқылы кілттерді қайта құруға болады.</span><span class="sxs-lookup"><span data-stu-id="f1d68-115">You can regenerate the keys by selecting the **Regenerate primary** or **Regenerate secondary** on **Admin** > **Permissions** > **APIs**.</span></span>

   :::image type="content" source="media/enable-apis.gif" alt-text="Customer Insights API интерфейстерін қосу":::

1. <span data-ttu-id="f1d68-117">API интерфейстерін сынап көру үшін **Біздің API интерфейсімізді зерттеу** опциясын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="f1d68-117">Select **Explore our APIs** to try out the APIs.</span></span>

1. <span data-ttu-id="f1d68-118">API операциясын таңдап, **Сынап көру** опциясын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="f1d68-118">Choose an API operation and select **Try it**.</span></span>

1. <span data-ttu-id="f1d68-119">Бүйірлік тақтадағы **Авторизация** ашылмалы мәзірінде мәнді **анық емес** мәнге орнатыңыз.</span><span class="sxs-lookup"><span data-stu-id="f1d68-119">In the side pane, set the value in the **Authorization** drop-down menu to **implicit**.</span></span> <span data-ttu-id="f1d68-120">`Authorization` тақырыбы тасушының таңбалауышымен қосылады.</span><span class="sxs-lookup"><span data-stu-id="f1d68-120">The `Authorization` header gets with a bearer token added.</span></span> <span data-ttu-id="f1d68-121">Жазылым кілті автоматты түрде толтырылады.</span><span class="sxs-lookup"><span data-stu-id="f1d68-121">Your subscription key will be automatically populated.</span></span>
  
1. <span data-ttu-id="f1d68-122">Оған қоса, қажетті барлық сұрау параметрлерін қосыңыз.</span><span class="sxs-lookup"><span data-stu-id="f1d68-122">Optionally, add all necessary query parameters.</span></span>

1. <span data-ttu-id="f1d68-123">Бүйірлік тақтаның төменгі жағына айналдырып, **Жіберу** опциясын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="f1d68-123">Scroll to the bottom of the side pane and select **Send**.</span></span>

<span data-ttu-id="f1d68-124">HTTP жауабы жақын арада төменде пайда болады.</span><span class="sxs-lookup"><span data-stu-id="f1d68-124">The HTTP response will soon appear below.</span></span>

## <a name="create-a-new-app-registration-in-the-azure-portal"></a><span data-ttu-id="f1d68-125">Azure порталында жаңа бағдарлама тіркелімін жасаңыз</span><span class="sxs-lookup"><span data-stu-id="f1d68-125">Create a new app registration in the Azure portal</span></span>

<span data-ttu-id="f1d68-126">Бұл қадамдар өкілетті рұқсаттар арқылы Azure бағдарламасындағы Customer Insights API интерфейстерінде жұмысты бастауға көмектеседі.</span><span class="sxs-lookup"><span data-stu-id="f1d68-126">These steps help you get started in using the Customer Insights APIs in an Azure application using delegated permissions.</span></span> <span data-ttu-id="f1d68-127">[Жұмысты бастау бөлімін](#get-started-trying-the-customer-insights-apis) бірінші аяқтағаныңызға көз жеткізіңіз.</span><span class="sxs-lookup"><span data-stu-id="f1d68-127">Make sure to have completed [Getting started section](#get-started-trying-the-customer-insights-apis) first.</span></span>

1. <span data-ttu-id="f1d68-128">Customer Insights деректеріне кіретін тіркелгімен [Azure порталына](https://portal.azure.com) кіріңіз.</span><span class="sxs-lookup"><span data-stu-id="f1d68-128">Sign in to the [Azure portal](https://portal.azure.com) with the account that can access the Customer Insights data.</span></span>

1. <span data-ttu-id="f1d68-129">Сол жақта **Бағдарламалар тіркелімі** опциясын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="f1d68-129">On the left, select **App registrations**.</span></span>

1. <span data-ttu-id="f1d68-130">**Жаңа тіркелім** опциясын таңдап, бағдарлама атауын беріңіз де, тіркелгі түрін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="f1d68-130">Select **New registration** provide an application name and choose the account type.</span></span>
   <span data-ttu-id="f1d68-131">Оған қоса, URL мекенжайын бағыттауды қосыңыз.</span><span class="sxs-lookup"><span data-stu-id="f1d68-131">Optionally, add a redirect URL.</span></span> <span data-ttu-id="f1d68-132">http://localhost сайты жергілікті компьютерде бағдарлама әзірлеу үшін жеткілікті.</span><span class="sxs-lookup"><span data-stu-id="f1d68-132">http://localhost is sufficient for developing an application on your local computer.</span></span>

1. <span data-ttu-id="f1d68-133">Жаңа бағдарлама тіркелімінде **API рұқсаттары** бөліміне өтіңіз.</span><span class="sxs-lookup"><span data-stu-id="f1d68-133">On your new App registration, go to **API permissions**.</span></span>

1. <span data-ttu-id="f1d68-134">**Рұқсат қосу** опциясын таңдап, бүйірлік тақтада **Customer Insights** опциясын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="f1d68-134">Select **Add a permission** and select **Customer Insights** in the side pane.</span></span>

1. <span data-ttu-id="f1d68-135">**Рұқсат түрі** үшін **Өкілетті рұқсаттар** түймесін және **user_impersonation** рұқсатын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="f1d68-135">For **Permission type**, select **Delegated permissions** and select the **user_impersonation** permission.</span></span>

1. <span data-ttu-id="f1d68-136">**Рұқсаттарды қосу** опциясын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="f1d68-136">Select **Add permissions**.</span></span> <span data-ttu-id="f1d68-137">Пайдаланушы кірмей-ақ API интерфейсіне қатынасу қажет болса, [Сервераралық бағдарлама рұқсаттары](#server-to-server-application-permissions) бөлімін қарап шығыңыз.</span><span class="sxs-lookup"><span data-stu-id="f1d68-137">If you need to access the API without a user signing in, review the [Server-to-server application permissions](#server-to-server-application-permissions) section.</span></span>

1. <span data-ttu-id="f1d68-138">Бағдарламаны тіркеуді аяқтау үшін **Әкімші келісімін келесілерге беру...** опциясын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="f1d68-138">Select **Grant admin consent for...** to complete the app registration.</span></span>

<span data-ttu-id="f1d68-139">Бағдарлама/клиент идентификаторын Microsoft аутентификация кітапханасында (MSAL) тіркеу үшін API интерфейсіне сұранысыңызбен жіберу мақсатында тасушы таңбалауышын алу үшін пайдалануға болады.</span><span class="sxs-lookup"><span data-stu-id="f1d68-139">You can use the Application/Client ID for this app registration with the Microsoft Authentication Library (MSAL) to obtain a bearer token to send with your request to the API.</span></span>

<span data-ttu-id="f1d68-140">MSAL туралы қосымша ақпарат алу үшін [Microsoft аутентификация кітапханасына (MSAL) шолу](https://docs.microsoft.com/azure/active-directory/develop/msal-overview) тақырыбына қараңыз.</span><span class="sxs-lookup"><span data-stu-id="f1d68-140">For more information about MSAL, see [Overview of Microsoft Authentication Library (MSAL)](https://docs.microsoft.com/azure/active-directory/develop/msal-overview).</span></span>

<span data-ttu-id="f1d68-141">Azure порталында бағдарламаны тіркеу туралы толығырақ ақпарат алу үшін [Жаңа Azure порталын тіркеу тәжірибесі](https://docs.microsoft.com/azure/active-directory/develop/app-registration-portal-training-guide) бөлімін қараңыз.</span><span class="sxs-lookup"><span data-stu-id="f1d68-141">For more information about app registration in Azure, see [The new Azure portal app registration experience](https://docs.microsoft.com/azure/active-directory/develop/app-registration-portal-training-guide).</span></span>

<span data-ttu-id="f1d68-142">Біздің API клиенттік кітапханаларымызда пайдалану туралы ақпаратты [Customer Insights клиенттік кітапханалары](#customer-insights-client-libraries) бөлімінен қараңыз.</span><span class="sxs-lookup"><span data-stu-id="f1d68-142">For information on using the APIs our client libraries, see [Customer Insights client libraries](#customer-insights-client-libraries).</span></span>

### <a name="server-to-server-application-permissions"></a><span data-ttu-id="f1d68-143">Сервераралық бағдарлама рұқсаттары</span><span class="sxs-lookup"><span data-stu-id="f1d68-143">Server-to-server application permissions</span></span>

<span data-ttu-id="f1d68-144">[Бағдарламаны тіркеу бөлімі](#create-a-new-app-registration-in-the-azure-portal) пайдаланушының аутентификация үшін жүйеге кіруін қажет ететін бағдарламаны тіркеу жолын көрсетеді.</span><span class="sxs-lookup"><span data-stu-id="f1d68-144">The [app registration section](#create-a-new-app-registration-in-the-azure-portal) outlines how to register an app that requires a user to sign in for authentication.</span></span> <span data-ttu-id="f1d68-145">Пайдаланушының өзара әрекеттестігін қажет етпейтін және серверде жұмыс істей алатын бағдарламаны тіркеу жолын жасау туралы мәлімет алыңыз.</span><span class="sxs-lookup"><span data-stu-id="f1d68-145">Learn how to create an app registration that does not need user interaction and can be run on a server.</span></span>

1. <span data-ttu-id="f1d68-146">Azure порталында бағдарламаны тіркеуде **API рұқсаттары** бөліміне өтіңіз.</span><span class="sxs-lookup"><span data-stu-id="f1d68-146">On your App registration in the Azure portal, go to **API permissions**.</span></span>

1. <span data-ttu-id="f1d68-147">**Рұқсат қосу** опциясын таңдап, бүйірлік тақтада **Customer Insights** опциясын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="f1d68-147">Select **Add a permission** and select **Customer Insights** in the side pane.</span></span>

1. <span data-ttu-id="f1d68-148">**Рұқсат түрі** үшін **Бағдарлама рұқсаттары** түймесін және **CustomerInsights.Api.All** рұқсатын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="f1d68-148">For **Permission type**, select **Application permissions** and select the **CustomerInsights.Api.All** permission.</span></span>

1. <span data-ttu-id="f1d68-149">**Рұқсаттарды қосу** опциясын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="f1d68-149">Select **Add permissions**.</span></span>

1. <span data-ttu-id="f1d68-150">Осы бағдарлама рұқсатында әкімші келісімін беру үшін субъект-қызметін қосу қажет.</span><span class="sxs-lookup"><span data-stu-id="f1d68-150">To give admin consent on this Application permission, you need to add a Service Principal.</span></span>

   1. <span data-ttu-id="f1d68-151">Azure Active Directory (AD) PowerShell модулін орнатыңыз: `Install-Module -Name AzureAD -AllowClobber -Scope AllUsers`</span><span class="sxs-lookup"><span data-stu-id="f1d68-151">Install the Azure Active Directory (AD) PowerShell module: `Install-Module -Name AzureAD -AllowClobber -Scope AllUsers`</span></span>
   1. <span data-ttu-id="f1d68-152">AD тіркелгіңізге қосылыңыз: `Connect-AzureAD -TenantId <your tenant id>`.</span><span class="sxs-lookup"><span data-stu-id="f1d68-152">Connect to your AD account: `Connect-AzureAD -TenantId <your tenant id>`.</span></span> <span data-ttu-id="f1d68-153">**Шолу** > **Azure Active Directory** тармағында қатысушы идентификаторын табуға болады.</span><span class="sxs-lookup"><span data-stu-id="f1d68-153">You can find your tenant ID on **Overview** > **Azure Active Directory**.</span></span>
   1. <span data-ttu-id="f1d68-154">Azure AD субъект-қызметін қосук үшін келесі пәрменді орындаңыз: `New-AzureADServicePrincipal -AppId "38c77d00-5fcb-4cce-9d93-af4738258e3c" -DisplayName "Microsoft Dynamics 365 Customer Insights"` AppId параметрі Customer Insights API бағдарламасына қатысты.</span><span class="sxs-lookup"><span data-stu-id="f1d68-154">Run the following command to add an Azure AD Service Principal: `New-AzureADServicePrincipal -AppId "38c77d00-5fcb-4cce-9d93-af4738258e3c" -DisplayName "Microsoft Dynamics 365 Customer Insights"` The AppId parameter pertains to the Customer Insights API app.</span></span>

   :::image type="content" source="media/azureAD-service-principal.png" alt-text="Субъект-қызмет үлгісі":::

1. <span data-ttu-id="f1d68-156">Бағдарламаны тіркеу үшін **API рұқсаттары** бөліміне қайта өтіңіз.</span><span class="sxs-lookup"><span data-stu-id="f1d68-156">Go back to **API permissions** for your app registration.</span></span>

1. <span data-ttu-id="f1d68-157">Бағдарламаны тіркеуді аяқтау үшін **Әкімші келісімін келесілерге беру...** опциясын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="f1d68-157">Select **Grant admin consent for...** to complete the app registration.</span></span>

1. <span data-ttu-id="f1d68-158">Қорытындылай келе, Customer Insights бағдарламасында пайдаланушы ретінде бағдарламаны тіркеу атауын қосу керек.</span><span class="sxs-lookup"><span data-stu-id="f1d68-158">To conclude, we have to add the name of the app registration as a user in Customer Insights.</span></span>    
   <span data-ttu-id="f1d68-159">Customer Insights бағдарламасын ашып, **Әкімші** > **Рұқсаттар** және **Пайдаланушыны қосу** тармағына өтіңіз.</span><span class="sxs-lookup"><span data-stu-id="f1d68-159">Open Customer Insights, go to **Admin** > **Permissions** and select **Add user**.</span></span>

1. <span data-ttu-id="f1d68-160">Бағдарламаны тіркеу атауын іздеп, оны іздеу нәтижелерінен таңдап, **Сақтау** түймесін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="f1d68-160">Search for the name of your app registration, select it from the search results, and select **Save**.</span></span>

## <a name="customer-insights-client-libraries"></a><span data-ttu-id="f1d68-161">Customer Insights клиенттік кітапханалары</span><span class="sxs-lookup"><span data-stu-id="f1d68-161">Customer Insights client libraries</span></span>

<span data-ttu-id="f1d68-162">Бұл бөлім Customer Insights API интерфейсі үшін қолжетімді клиенттік кітапханаларды пайдалануды бастауға көмектеседі.</span><span class="sxs-lookup"><span data-stu-id="f1d68-162">This section helps you get started using the client libraries available for the Customer Insights APIs.</span></span>

### <a name="c-nuget"></a><span data-ttu-id="f1d68-163">C# NuGet</span><span class="sxs-lookup"><span data-stu-id="f1d68-163">C# NuGet</span></span>

<span data-ttu-id="f1d68-164">NuGet.org. сайтынан C# клиенттік кітапханаларын пайдаланып жұмысты бастау туралы мәлімет алыңыз. NuGet жиынтығы туралы толығырақ ақпарат алу үшін [Microsoft.Dynamics.CustomerInsights.Api](https://www.nuget.org/packages/Microsoft.Dynamics.CustomerInsights.Api/) бөлімін қараңыз.</span><span class="sxs-lookup"><span data-stu-id="f1d68-164">Learn how to get started using the C# client libraries from NuGet.org. For more information on the NuGet package, see [Microsoft.Dynamics.CustomerInsights.Api](https://www.nuget.org/packages/Microsoft.Dynamics.CustomerInsights.Api/).</span></span> <span data-ttu-id="f1d68-165">Қазіргі уақытта бұл жиынтық netstandard2.0 және netcoreapp2.0 арқаулық жүйелеріне бағытталған.</span><span class="sxs-lookup"><span data-stu-id="f1d68-165">Currently, this package targets the netstandard2.0 and netcoreapp2.0 frameworks.</span></span>

#### <a name="add-the-c-client-library-to-a-c-project"></a><span data-ttu-id="f1d68-166">C# жобасына C# клиенттік кітапханасын қосыңыз</span><span class="sxs-lookup"><span data-stu-id="f1d68-166">Add the C# client library to a C# project</span></span>

1. <span data-ttu-id="f1d68-167">Visual Studio бағдарламасында жобаға арналған **NuGet жиынтық менеджері** жүйесін ашыңыз.</span><span class="sxs-lookup"><span data-stu-id="f1d68-167">In Visual Studio, open the **NuGet Package Manager** for your project.</span></span>

1. <span data-ttu-id="f1d68-168">**Microsoft.Dynamics.CustomerInsights.Api** іздеңіз.</span><span class="sxs-lookup"><span data-stu-id="f1d68-168">Search for **Microsoft.Dynamics.CustomerInsights.Api**.</span></span>

1. <span data-ttu-id="f1d68-169">Жобаға жиынтық қосу үшін **Орнату** түймесін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="f1d68-169">Select **Install** to add the package to the project.</span></span>
   <span data-ttu-id="f1d68-170">Сонымен қатар, **NuGet жиынтық менеджері консолі** жүйесінде мына пәрменді орындаңыз: `Install-Package -Id Microsoft.Dynamics.CustomerInsights.Api -Source nuget.org -ProjectName <project name> [-Version <version>]`</span><span class="sxs-lookup"><span data-stu-id="f1d68-170">Alternatively, run this command in the **NuGet Package Manager Console**: `Install-Package -Id Microsoft.Dynamics.CustomerInsights.Api -Source nuget.org -ProjectName <project name> [-Version <version>]`</span></span>

   :::image type="content" source="media/visual-studio-nuget-package.gif" alt-text="Visual Studio жобасына NuGet жиынтығын қосу":::

#### <a name="use-the-c-client-library"></a><span data-ttu-id="f1d68-172">C# клиенттік кітапханасын пайдаланыңыз</span><span class="sxs-lookup"><span data-stu-id="f1d68-172">Use the C# client library</span></span>

1. <span data-ttu-id="f1d68-173">Бұрыннан бар [Azure бағдарламасын тіркеу](#create-a-new-app-registration-in-the-azure-portal) жүйесін пайдаланып `AccessToken` алу үшін [Microsoft аутентификация кітапханасы (MSAL)](https://docs.microsoft.com/azure/active-directory/develop/msal-overview) пайдаланыңыз.</span><span class="sxs-lookup"><span data-stu-id="f1d68-173">Use the [Microsoft Authentication Library (MSAL)](https://docs.microsoft.com/azure/active-directory/develop/msal-overview) to get an `AccessToken` using your existing [Azure app registration](#create-a-new-app-registration-in-the-azure-portal).</span></span>

1. <span data-ttu-id="f1d68-174">Таңбалауышты сәтті аутентификациялап, алғаннан кейін, жаңасын құрастырыңыз немесе **Тасушы <access token>** және **Ocp-Apim-Subscription-Key**, [Customer Insights ортасынан  **жазылым кілті**](#get-started-trying-the-customer-insights-apis) күйлеріне орнатылған қосымша **DefaultRequestHeaders** авторизациясымен бұрыннан бар `HttpClient` пайдаланыңыз.</span><span class="sxs-lookup"><span data-stu-id="f1d68-174">After successfully authenticating and acquiring a token, construct a new or use an existing `HttpClient` with the additional **DefaultRequestHeaders "Authorization"** set to **Bearer <access token>** and **Ocp-Apim-Subscription-Key** set to the [**subscription key** from your Customer Insights environment](#get-started-trying-the-customer-insights-apis).</span></span>    
   <span data-ttu-id="f1d68-175">Қажет болған жағдайда **Авторизация** тақырыбын қалпына келтіріңіз.</span><span class="sxs-lookup"><span data-stu-id="f1d68-175">Reset the **Authorization** header when appropriate.</span></span> <span data-ttu-id="f1d68-176">Мысалы, таңбалауыш мерзімі аяқталған кезде.</span><span class="sxs-lookup"><span data-stu-id="f1d68-176">For example, when the token expired.</span></span>

1. <span data-ttu-id="f1d68-177">Осы `HttpClient` парамтерін `CustomerInsights` клиенті құрылымына өткізіңіз.</span><span class="sxs-lookup"><span data-stu-id="f1d68-177">Pass this `HttpClient` into the construction of the `CustomerInsights` client.</span></span>

   :::image type="content" source="media/httpclient-sample.png" alt-text="Httpclient үлгісі":::

1. <span data-ttu-id="f1d68-179">Клиентпен «кеңейту әдістеріне» қоңырау шалыңыз, мысалы,`GetAllInstancesAsync`.</span><span class="sxs-lookup"><span data-stu-id="f1d68-179">Make calls with the client to the "extension methods", for example, `GetAllInstancesAsync`.</span></span> <span data-ttu-id="f1d68-180">Егер негізгі `Microsoft.Rest.HttpOperationResponse` таңдаулы болса, «http хабарлама әдістерін» пайдаланыңыз, мысалы, `GetAllInstancesWithHttpMessagesAsync`.</span><span class="sxs-lookup"><span data-stu-id="f1d68-180">If access to the underlying `Microsoft.Rest.HttpOperationResponse` is preferred, use the "http message methods", for example `GetAllInstancesWithHttpMessagesAsync`.</span></span>

1. <span data-ttu-id="f1d68-181">Жауап түрі `object` болуы мүмкін, өйткені әдіс бірнеше түрді қайтара алады (мысалы, `IList<InstanceInfo>` және `ApiErrorResult`).</span><span class="sxs-lookup"><span data-stu-id="f1d68-181">The response will likely be of type `object` because the method can return multiple types (for example, `IList<InstanceInfo>` and `ApiErrorResult`).</span></span> <span data-ttu-id="f1d68-182">Қайтару түрін тексеру үшін нысандарды сол операция үшін [API мәліметтері бетінде](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights) көрсетілген жауап түрлеріне қауіпсіз түрде түрлендіруге болады.</span><span class="sxs-lookup"><span data-stu-id="f1d68-182">To check the return type, you can safely cast the objects into the response types specified on the [API details page](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights) for that operation.</span></span>    
   <span data-ttu-id="f1d68-183">Егер сұрау туралы қосымша ақпарат қажет болса, бастапқы жауап нысанына қол жеткізу үшін  **http хабары әдістерін** пайдаланыңыз.</span><span class="sxs-lookup"><span data-stu-id="f1d68-183">If more information on the request is needed, use the **http message methods** to access the raw response object.</span></span>
