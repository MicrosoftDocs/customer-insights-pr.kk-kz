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
ms.openlocfilehash: 8404515a20529c00708d84813f3a022ad98c45362a2f1e68d7aa890d085071a9
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: kk-KZ
ms.lasthandoff: 08/10/2021
ms.locfileid: "7033592"
---
# <a name="work-with-customer-insights-apis"></a>Customer Insights API жүйесімен жұмыс істеу

Dynamics 365 Customer Insights бағдарламасы Customer Insights ішіндегі деректер негізінде жеке бағдарламаларды жасау үшін API интерфейстерін ұсынады.

> [!IMPORTANT]
> Осы API интерфейстерін туралы толық мәліметтер [Customer Insights API интерфейстері анықтамасы](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights) бөлімінде көрсетілген. Олар операциялар, параметрлер және жауаптар туралы қосымша ақпаратты қамтиды.

Бұл мақалада Customer Insights API интерфейстеріне қатынасу, Azure бағдарламасын тіркеу және қолжетімді клиенттік кітапханалармен жұмыс бастау жолы сипатталған.

## <a name="get-started-trying-the-customer-insights-apis"></a>Customer Insights API интерфейстерін қолдануды бастаңыз

1. Customer Insights жүйесіне [қосылыңыз](https://home.ci.ai.dynamics.com). Егер сізде әлі жазылым болмаса, [Customer Insights бағдарламасының сынақ нұсқасына жазылыңыз](https://aka.ms/tryci).

1. Customer Insights ортасында API элементтерін қосу үшін **Әкімші** > **Рұқсаттар** тармағына өтіңіз. Ол үшін сізге әкімші рұқсаттары қажет.

1. **API** қойындысына өтіп, **Қосу** түймесін таңдаңыз.    
 
   API элементін қосу API сұрауларында пайдаланылатын данаға арналған негізгі және қосымша жазылым кілтін жасайды. **Әкімші** > **Рұқсаттар** > **API интерфейстері** тармағында **Негізгісін қайта құру** немесе **Қосымшасын қайта құру** опцияларын таңдау арқылы кілттерді қайта құруға болады.

   :::image type="content" source="media/enable-apis.gif" alt-text="Customer Insights API интерфейстерін қосу.":::

1. [API интерфейстерін сынап көру](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights&operation=Get-all-instances) үшін **Біздің API интерфейсімізді зерттеу** опциясын таңдаңыз.

1. API операциясын таңдап, **Сынап көру** опциясын таңдаңыз.

1. Бүйірлік тақтада **Авторизация** ашылмалы мәзіріндегі мәнді **жасырын** мәніне орнатыңыз. `Authorization` тақырыбы тасушы таңбалауышымен қосылады. Жазылым кілті автоматты түрде толтырылады.
  
1. Оған қоса, қажетті барлық сұрау параметрлерін қосыңыз.

1. Бүйірлік тақтаның төменгі жағына айналдырып, **Жіберу** опциясын таңдаңыз.

HTTP жауабы жақын арада төменде пайда болады.

   :::image type="content" source="media/try-apis.gif" alt-text="API интерфейстерін тексеру жолы.":::

## <a name="create-a-new-app-registration-in-the-azure-portal"></a>Azure порталында жаңа бағдарлама тіркелімін жасаңыз

Бұл қадамдар өкілетті рұқсаттар көмегімен Azure бағдарламасында Customer Insights API интерфейстерін пайдаланумен жұмысты бастауға көмектеседі. Алдымен [Жұмысты бастау бөлімін](#get-started-trying-the-customer-insights-apis) толтырғаныңызға көз жеткізіңіз.

1. Customer Insights деректеріне кіретін тіркелгімен [Azure порталына](https://portal.azure.com) кіріңіз.

1. Сол жақта **Бағдарламалар тіркелімі** опциясын таңдаңыз.

1. **Жаңа тіркелім** опциясын таңдап, бағдарлама атауын беріңіз де, тіркелгі түрін таңдаңыз.
 
   Оған қоса, URL мекенжайын бағыттауды қосыңыз. http://localhost сайты жергілікті компьютерде бағдарлама әзірлеу үшін жеткілікті.

1. Жаңа бағдарлама тіркелімінде **API рұқсаттары** бөліміне өтіңіз.

   :::image type="content" source="media/app-registration-1.gif" alt-text="Бағдарламаны тіркеуде API рұқсаттарын орнату жолы.":::

1. **Рұқсат қосу** опциясын таңдап, бүйірлік тақтада **Customer Insights** опциясын таңдаңыз.

1. **Рұқсат түрі** үшін **Өкілетті рұқсаттар** параметрін таңдаңыз, содан кейін **user_impersonation** рұқсатын таңдаңыз.

1. **Рұқсаттарды қосу** опциясын таңдаңыз. Пайдаланушы кірмей-ақ API интерфейсіне қатынасу қажет болса, [Сервераралық бағдарлама рұқсаттары](#server-to-server-application-permissions) бөлімін қарап шығыңыз.

1. Бағдарламаны тіркеуді аяқтау үшін **Әкімші келісімін келесілерге беру...** опциясын таңдаңыз.

Бағдарлама/клиент идентификаторын Microsoft аутентификация кітапханасында (MSAL) тіркеу үшін API интерфейсіне сұранысыңызбен жіберу мақсатында тасушы таңбалауышын алу үшін пайдалануға болады.

:::image type="content" source="media/grant-admin-consent.gif" alt-text="Әкімші келісімін беру жолы.":::

MSAL туралы қосымша ақпарат алу үшін [Microsoft аутентификация кітапханасына (MSAL) шолу](/azure/active-directory/develop/msal-overview) тақырыбына қараңыз.

Бағдарламаны Azure қызметінде тіркеу туралы қосымша ақпаратты [Бағдарламаны тіркеу](/azure/active-directory/develop/quickstart-register-app.md#register-an-application) бөлімінен қараңыз.

Біздің клиенттік кітапханаларымызда API интерфейстерін қолдану туралы ақпаратты [Customer Insights клиенттік кітапханалары](#customer-insights-client-libraries) бөлімін қараңыз.

### <a name="server-to-server-application-permissions"></a>Сервераралық бағдарлама рұқсаттары

[Бағдарламаны тіркеу бөлімі](#create-a-new-app-registration-in-the-azure-portal) пайдаланушының аутентификация үшін жүйеге кіруін қажет ететін бағдарламаны тіркеу жолын көрсетеді. Пайдаланушының өзара әрекеттестігін қажет етпейтін және серверде жұмыс істей алатын бағдарламаны тіркеу жолын жасау туралы мәлімет алыңыз.

1. Azure порталында бағдарламаны тіркеуде **API рұқсаттары** бөліміне өтіңіз.

1. **Рұқсат қосу** опциясын таңдаңыз. 

1. **Менің ұйымым пайдаланатын API интерфейстері** қойыншасын таңдаңыз және тізімнен **Dynamics 365 AI for Customer Insights** бағдарламасын таңдаңыз. 

1. **Рұқсат түрі** үшін **Бағдарлама рұқсаттары** параметрін таңдаңыз, содан кейін **CustomerInsights.Api.All** рұқсатын таңдаңыз.

1. **Рұқсаттарды қосу** опциясын таңдаңыз.

1. Бағдарламаны тіркеу үшін **API рұқсаттары** бөліміне қайта өтіңіз.

1. Бағдарламаны тіркеуді аяқтау үшін **Әкімші келісімін келесілерге беру...** опциясын таңдаңыз.

   :::image type="content" source="media/grant-admin-consent.gif" alt-text="Әкімші келісімін беру жолы.":::

1. Қорытындылай келе, Customer Insights бағдарламасында пайдаланушы ретінде бағдарламаны тіркеу атауын қосу керек.  
   
   Customer Insights бағдарламасын ашып, **Әкімші** > **Рұқсаттар** және **Пайдаланушыны қосу** тармағына өтіңіз.

1. Бағдарламаны тіркеу атауын іздеп, оны іздеу нәтижелерінен таңдап, **Сақтау** түймесін таңдаңыз.

## <a name="customer-insights-client-libraries"></a>Customer Insights клиенттік кітапханалары

Бұл бөлім Customer Insights API интерфейсі үшін қолжетімді клиенттік кітапханаларды пайдалануды бастауға көмектеседі. Кітапхананың барлық бастапқы коды мен бағдарлама үлгілерін [Customer Insights GitHub бетінен](https://github.com/microsoft/Dynamics365-CustomerInsights-Client-Libraries) табуға болады. 

### <a name="c-nuget"></a>C# NuGet

NuGet.org. сайтынан C# клиенттік кітапханаларын пайдаланып жұмысты бастау туралы мәлімет алыңыз. NuGet жиынтығы туралы толығырақ ақпарат алу үшін [Microsoft.Dynamics.CustomerInsights.Api](https://www.nuget.org/packages/Microsoft.Dynamics.CustomerInsights.Api/) бөлімін қараңыз. Қазіргі уақытта бұл жиынтық netstandard2.0 және netcoreapp2.0 арқаулық жүйелеріне бағытталған.

#### <a name="add-the-c-client-library-to-a-c-project"></a>C# жобасына C# клиенттік кітапханасын қосыңыз

1. Visual Studio бағдарламасында жобаға арналған **NuGet жиынтық менеджері** жүйесін ашыңыз.

1. **Microsoft.Dynamics.CustomerInsights.Api** іздеңіз.

1. Жобаға жиынтық қосу үшін **Орнату** түймесін таңдаңыз.
 
   Сонымен қатар **NuGet жиынтық менеджері консолі** жүйесінде мына пәрменді орындаңыз: `Install-Package -Id Microsoft.Dynamics.CustomerInsights.Api -Source nuget.org -ProjectName <project name> [-Version <version>]`

   :::image type="content" source="media/visual-studio-nuget-package.gif" alt-text="Visual Studio жобасына NuGet жиынтығын қосу.":::

#### <a name="use-the-c-client-library"></a>C# клиенттік кітапханасын пайдаланыңыз

1. Бұрыннан бар [Azure бағдарламасын тіркеу](#create-a-new-app-registration-in-the-azure-portal) жүйесін пайдаланып `AccessToken` алу үшін [Microsoft аутентификация кітапханасы (MSAL)](/azure/active-directory/develop/msal-overview) пайдаланыңыз.

1. Таңбалауышты сәтті аутентификациялап, алғаннан кейін, жаңасын құрастырыңыз немесе **Тасушы <access token>** және **Ocp-Apim-Subscription-Key**, [Customer Insights ортасынан  **жазылым кілті**](#get-started-trying-the-customer-insights-apis) күйлеріне орнатылған қосымша **DefaultRequestHeaders** авторизациясымен бұрыннан бар `HttpClient` пайдаланыңыз.   
 
   Қажет болған жағдайда **Авторизация** тақырыбын қалпына келтіріңіз. Мысалы, таңбалауыш мерзімі аяқталған кезде.

1. Осы `HttpClient` парамтерін `CustomerInsights` клиенті құрылымына өткізіңіз.

   :::image type="content" source="media/httpclient-sample.png" alt-text="Httpclient үлгісі.":::

1. Клиентпен "кеңейту әдістеріне" қоңырау шалыңыз,—мысалы, `GetAllInstancesAsync`. Егер негізгі `Microsoft.Rest.HttpOperationResponse` қатынасу керек болса, "http хабар әдістерін" пайдаланыңыз,—мысалы, `GetAllInstancesWithHttpMessagesAsync`.

1. Жауап түрі `object` болуы мүмкін, өйткені әдіс бірнеше түрді қайтара алады (мысалы, `IList<InstanceInfo>` және `ApiErrorResult`). Қайтару түрін тексеру үшін нысандарды сол операция үшін [API мәліметтері бетінде](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights) көрсетілген жауап түрлеріне қауіпсіз түрде түрлендіруге болады.    
   
   Егер сұрау туралы қосымша ақпарат қажет болса, бастапқы жауап нысанына қол жеткізу үшін  **http хабары әдістерін** пайдаланыңыз.

### <a name="nodejs-package"></a>NodeJS бумасы

NPM арқылы қолжетімді NodeJS клиенттік кітапханаларын пайдаланыңыз: https://www.npmjs.com/package/@microsoft/customerinsights

### <a name="python-package"></a>Python бумасы

PyPi арқылы қолжетімді Python клиенттік кітапханаларын пайдаланыңыз: https://pypi.org/project/customerinsights/

[!INCLUDE[footer-include](../includes/footer-banner.md)]
