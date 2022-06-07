---
title: API интерфейсімен жұмыс істеу
description: API пайдаланып, шектеулерді түсініңіз.
ms.date: 05/10/2021
ms.reviewer: wimohabb
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
searchScope:
- ci-system-api-usage
- customerInsights
ms.openlocfilehash: 9a04276f7326533cd389cba6554f468123463bac
ms.sourcegitcommit: bf65bc0a54cdab71680e658e1617bee7b2c2bb68
ms.translationtype: MT
ms.contentlocale: kk-KZ
ms.lasthandoff: 05/27/2022
ms.locfileid: "8808513"
---
# <a name="work-with-customer-insights-apis"></a>Customer Insights API жүйесімен жұмыс істеу

Dynamics 365 Customer Insights бағдарламасы Customer Insights ішіндегі деректер негізінде жеке бағдарламаларды жасау үшін API интерфейстерін ұсынады.

> [!IMPORTANT]
> Осы API интерфейстерін туралы толық мәліметтер [Customer Insights API интерфейстері анықтамасы](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights) бөлімінде көрсетілген. Олар операциялар, параметрлер және жауаптар туралы қосымша ақпаратты қамтиды.

Бұл мақала Customer Insights API интерфейстеріне қатынасу, Azure қолданбасын тіркеуді жасау және клиент кітапханаларымен жұмысты бастау жолын сипаттайды.

## <a name="get-started-trying-the-customer-insights-apis"></a>Customer Insights API интерфейстерін қолдануды бастаңыз

1. Customer Insights жүйесіне [қосылыңыз](https://home.ci.ai.dynamics.com). Егер сізде әлі жазылым болмаса, [Customer Insights бағдарламасының сынақ нұсқасына жазылыңыз](https://aka.ms/tryci).

1. Customer Insights ортаңызда API интерфейстерін қосу үшін өтіңіз **Админ** > **Қауіпсіздік**. Ол үшін сізге әкімші рұқсаттары қажет.

1. **API** қойындысына өтіп, **Қосу** түймесін таңдаңыз.    
 
   API элементін қосу API сұрауларында пайдаланылатын данаға арналған негізгі және қосымша жазылым кілтін жасайды. түймесін таңдау арқылы пернелерді қалпына келтіруге болады **Бастапқы қалпына келтіру** немесе **Екінші ретті қалпына келтіру** қосулы **Админ** > **Қауіпсіздік** > **API интерфейстері**.

<!--  :::image type="content" source="media/enable-apis.gif" alt-text="Enable Customer Insights APIs."::: -->

1. [API интерфейстерін сынап көру](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights&operation=Get-all-instances) үшін **Біздің API интерфейсімізді зерттеу** опциясын таңдаңыз.

1. API операциясын таңдап, **Сынап көру** опциясын таңдаңыз.

1. Бүйірлік тақтада **Авторизация** ашылмалы мәзіріндегі мәнді **жасырын** мәніне орнатыңыз. `Authorization` тақырыбы тасушы таңбалауышымен қосылады. Жазылым кілті автоматты түрде толтырылады.
  
1. Оған қоса, қажетті барлық сұрау параметрлерін қосыңыз.

1. Бүйірлік тақтаның төменгі жағына айналдырып, **Жіберу** опциясын таңдаңыз.

HTTP жауабы жақын арада төменде пайда болады.

<!--   :::image type="content" source="media/try-apis.gif" alt-text="How to test the APIs."::: -->

## <a name="create-a-new-app-registration-in-the-azure-portal"></a>Azure порталында жаңа бағдарлама тіркелімін жасаңыз

Бұл қадамдар өкілетті рұқсаттар көмегімен Azure бағдарламасында Customer Insights API интерфейстерін пайдаланумен жұмысты бастауға көмектеседі. Алдымен [Жұмысты бастау бөлімін](#get-started-trying-the-customer-insights-apis) толтырғаныңызға көз жеткізіңіз.

1. Customer Insights деректеріне кіретін тіркелгімен [Azure порталына](https://portal.azure.com) кіріңіз.

1. Сол жақта **Бағдарламалар тіркелімі** опциясын таңдаңыз.

1. **Жаңа тіркелім** опциясын таңдап, бағдарлама атауын беріңіз де, тіркелгі түрін таңдаңыз.

   Оған қоса, URL мекенжайын бағыттауды қосыңыз. http://localhost сайты жергілікті компьютерде бағдарлама әзірлеу үшін жеткілікті.

1. Жаңа бағдарлама тіркелімінде **API рұқсаттары** бөліміне өтіңіз.

1. таңдаңыз **Рұқсат қосыңыз** және таңдаңыз **Customer Insights үшін Dynamics 365 AI** бүйірлік тақтада.

1. **Рұқсат түрі** үшін **Өкілетті рұқсаттар** параметрін таңдаңыз, содан кейін **user_impersonation** рұқсатын таңдаңыз.

1. **Рұқсаттарды қосу** опциясын таңдаңыз. Пайдаланушы кірмей-ақ API интерфейсіне қатынасу қажет болса, [Сервераралық бағдарлама рұқсаттары](#server-to-server-application-permissions) бөлімін қарап шығыңыз.

1. Бағдарламаны тіркеуді аяқтау үшін **Әкімші келісімін келесілерге беру...** опциясын таңдаңыз.

Бағдарлама/клиент идентификаторын Microsoft аутентификация кітапханасында (MSAL) тіркеу үшін API интерфейсіне сұранысыңызбен жіберу мақсатында тасушы таңбалауышын алу үшін пайдалануға болады.

<!-- :::image type="content" source="media/grant-admin-consent.gif" alt-text="How to grant admin consent."::: -->

MSAL туралы қосымша ақпарат алу үшін [Microsoft аутентификация кітапханасына (MSAL) шолу](/azure/active-directory/develop/msal-overview) тақырыбына қараңыз.

Бағдарламаны Azure қызметінде тіркеу туралы қосымша ақпаратты [Бағдарламаны тіркеу](/graph/auth-register-app-v2) бөлімінен қараңыз.

Біздің клиенттік кітапханаларымызда API интерфейстерін қолдану туралы ақпаратты [Customer Insights клиенттік кітапханалары](#customer-insights-client-libraries) бөлімін қараңыз.

### <a name="server-to-server-application-permissions"></a>Сервераралық бағдарлама рұқсаттары

[Бағдарламаны тіркеу бөлімі](#create-a-new-app-registration-in-the-azure-portal) пайдаланушының аутентификация үшін жүйеге кіруін қажет ететін бағдарламаны тіркеу жолын көрсетеді. Пайдаланушы әрекетін қажет етпейтін және серверде іске қосуға болатын қолданбаны тіркеуді қалай жасау керектігін біліңіз.

1. Azure порталында бағдарламаны тіркеуде **API рұқсаттары** бөліміне өтіңіз.

1. **Рұқсат қосу** опциясын таңдаңыз. 

1. **Менің ұйымым пайдаланатын API интерфейстері** қойыншасын таңдаңыз және тізімнен **Dynamics 365 AI for Customer Insights** бағдарламасын таңдаңыз. 

1. **Рұқсат түрі** үшін **Бағдарлама рұқсаттары** параметрін таңдаңыз, содан кейін **CustomerInsights.Api.All** рұқсатын таңдаңыз.

1. **Рұқсаттарды қосу** опциясын таңдаңыз.

1. Бағдарламаны тіркеу үшін **API рұқсаттары** бөліміне қайта өтіңіз.

1. Бағдарламаны тіркеуді аяқтау үшін **Әкімші келісімін келесілерге беру...** опциясын таңдаңыз.

 <!--  :::image type="content" source="media/grant-admin-consent.gif" alt-text="How to grant admin consent."::: -->

1. Қорытындылай келе, Customer Insights бағдарламасында пайдаланушы ретінде бағдарламаны тіркеу атауын қосу керек.  
   
   Customer Insights қолданбасын ашыңыз, өтіңіз **Админ** > **Қауіпсіздік** және таңдаңыз **Пайдаланушы қосу**.

1. Бағдарламаны тіркеу атауын іздеп, оны іздеу нәтижелерінен таңдап, **Сақтау** түймесін таңдаңыз.

## <a name="sample-queries"></a>Сұрау үлгісі

API интерфейстерімен жұмыс істеу үшін OData үлгі сұрауларының қысқаша тізімін жасадық: [OData сұрау мысалдары](odata-examples.md).

## <a name="customer-insights-client-libraries"></a>Customer Insights клиенттік кітапханалары

Бұл бөлім Customer Insights API интерфейсі үшін қолжетімді клиенттік кітапханаларды пайдалануды бастауға көмектеседі. Кітапхананың барлық бастапқы коды мен бағдарлама үлгілерін [Customer Insights GitHub бетінен](https://github.com/microsoft/Dynamics365-CustomerInsights-Client-Libraries) табуға болады. 

### <a name="c-nuget"></a>C# NuGet

NuGet.org. сайтынан C# клиенттік кітапханаларын пайдаланып жұмысты бастау туралы мәлімет алыңыз. NuGet жиынтығы туралы толығырақ ақпарат алу үшін [Microsoft.Dynamics.CustomerInsights.Api](https://www.nuget.org/packages/Microsoft.Dynamics.CustomerInsights.Api/) бөлімін қараңыз. Қазіргі уақытта бұл жиынтық netstandard2.0 және netcoreapp2.0 арқаулық жүйелеріне бағытталған.

#### <a name="add-the-c-client-library-to-a-c-project"></a>C# жобасына C# клиенттік кітапханасын қосыңыз

1. Visual Studio бағдарламасында жобаға арналған **NuGet жиынтық менеджері** жүйесін ашыңыз.

1. **Microsoft.Dynamics.CustomerInsights.Api** іздеңіз.

1. Жобаға жиынтық қосу үшін **Орнату** түймесін таңдаңыз.
 
   Сонымен қатар **NuGet жиынтық менеджері консолі** жүйесінде мына пәрменді орындаңыз: `Install-Package -Id Microsoft.Dynamics.CustomerInsights.Api -Source nuget.org -ProjectName <project name> [-Version <version>]`

 <!--  :::image type="content" source="media/visual-studio-nuget-package.gif" alt-text="Add NuGet package to Visual Studio project."::: -->

#### <a name="use-the-c-client-library"></a>C# клиенттік кітапханасын пайдаланыңыз

1. Бұрыннан бар [Azure бағдарламасын тіркеу](#create-a-new-app-registration-in-the-azure-portal) жүйесін пайдаланып `AccessToken` алу үшін [Microsoft аутентификация кітапханасы (MSAL)](/azure/active-directory/develop/msal-overview) пайдаланыңыз.

1. Сәтті аутентификация және таңбалауыш алғаннан кейін жаңасын жасаңыз немесе барын пайдаланыңыз`HttpClient` бірге **DefaultRequestHeaders "Авторизация"** деп орнатыңыз **Тасымалдаушы «қолжетімділік белгісі»** және **Ocp-Apim-жазылым кілті** мәніне орнатыңыз [**жазылым кілті** Customer Insights ортаңыздан](#get-started-trying-the-customer-insights-apis).   
 
   Қажет болған жағдайда **Авторизация** тақырыбын қалпына келтіріңіз. Мысалы, таңбалауыш мерзімі аяқталған кезде.

1. Осы `HttpClient` парамтерін `CustomerInsights` клиенті құрылымына өткізіңіз.

<!--   :::image type="content" source="media/httpclient-sample.png" alt-text="Sample of httpclient."::: -->

1. Клиентпен "кеңейту әдістеріне" қоңырау шалыңыз,—мысалы, `GetAllInstancesAsync`. Егер негізгі `Microsoft.Rest.HttpOperationResponse` қатынасу керек болса, "http хабар әдістерін" пайдаланыңыз,—мысалы, `GetAllInstancesWithHttpMessagesAsync`.

1. Жауап түрі `object` болуы мүмкін, өйткені әдіс бірнеше түрді қайтара алады (мысалы, `IList<InstanceInfo>` және `ApiErrorResult`). Қайтару түрін тексеру үшін сіз нысанда көрсетілген жауап түрлеріндегі нысандарды пайдаланасыз [API мәліметтер беті](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights) сол операция үшін.    
   
   Егер сұрау туралы қосымша ақпарат қажет болса, бастапқы жауап нысанына қол жеткізу үшін  **http хабары әдістерін** пайдаланыңыз.

### <a name="nodejs-package"></a>NodeJS бумасы

NPM арқылы қолжетімді NodeJS клиенттік кітапханаларын пайдаланыңыз: https://www.npmjs.com/package/@microsoft/customerinsights

### <a name="python-package"></a>Python бумасы

PyPi арқылы қолжетімді Python клиенттік кітапханаларын пайдаланыңыз: https://pypi.org/project/customerinsights/

[!INCLUDE [footer-include](includes/footer-banner.md)]
