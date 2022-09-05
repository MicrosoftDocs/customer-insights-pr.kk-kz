---
title: Customer Insights API жүйесімен жұмыс істеу
description: API пайдаланып, шектеулерді түсініңіз.
ms.date: 08/31/2022
ms.reviewer: wimohabb
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
searchScope:
- ci-system-api-usage
- customerInsights
ms.openlocfilehash: f499bff4a6ac07a88ff0f773b9cee77dc74989e8
ms.sourcegitcommit: 624b27bb65a0de1970dc1ac436643b493f0a31cf
ms.translationtype: MT
ms.contentlocale: kk-KZ
ms.lasthandoff: 08/31/2022
ms.locfileid: "9387347"
---
# <a name="work-with-customer-insights-apis"></a>Customer Insights API жүйесімен жұмыс істеу

Dynamics 365 Customer Insights бағдарламасы Customer Insights ішіндегі деректер негізінде жеке бағдарламаларды жасау үшін API интерфейстерін ұсынады.

> [!IMPORTANT]
> Осы API интерфейстерін туралы толық мәліметтер [Customer Insights API интерфейстері анықтамасы](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights) бөлімінде көрсетілген. Олар операциялар, параметрлер және жауаптар туралы қосымша ақпаратты қамтиды.

Customer Insights API интерфейстерін қолданып көріңіз, Azure қолданбасын тіркеуді жасаңыз және клиент кітапханаларымен жұмысты бастаңыз.

## <a name="get-started-trying-the-customer-insights-apis"></a>Customer Insights API интерфейстерін қолдануды бастаңыз

Customer Insights API интерфейстерін қосыңыз және оларды қолданып көріңіз. Customer Insights әкімшісі Customer Insights қолданбасына API қатынасын қосуы керек. Қол жеткізу қосылғаннан кейін кез келген пайдаланушы жазылым кілтімен API пайдалана алады.

1. Customer Insights жүйесіне [қосылыңыз](https://home.ci.ai.dynamics.com). Егер сізде әлі жазылым болмаса, [Customer Insights бағдарламасының сынақ нұсқасына жазылыңыз](https://aka.ms/tryci).

1. Бару **Админ** > **Қауіпсіздік** және таңдаңыз **API интерфейстері** қойындысы.

1. Ортаға API қатынасы орнатылмаған болса, таңдаңыз **Қосу** .

   API элементін қосу API сұрауларында пайдаланылатын данаға арналған негізгі және қосымша жазылым кілтін жасайды. Пернелерді қалпына келтіру үшін опциясын таңдаңыз **Бастапқы қалпына келтіру** немесе **Екінші ретті қалпына келтіру** үстінде **API интерфейстері** қойындысы.

1. таңдаңыз [**API интерфейстерін зерттеңіз**](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights&operation=Get-all-instances) API интерфейстерін сынап көру үшін.

1. API операциясын іздеңіз және таңдаңыз және таңдаңыз **Байқап көріңіз** .

   :::image type="content" source="media/try-api.png" alt-text="API интерфейстерін тексеру жолы.":::

1. Бүйірлік тақтада **Авторизация** ашылмалы мәзіріндегі мәнді **жасырын** мәніне орнатыңыз. `Authorization` тақырыбы тасушы таңбалауышымен қосылады. Жазылым кілті автоматты түрде толтырылады.
  
1. Оған қоса, қажетті барлық сұрау параметрлерін қосыңыз.

1. Бүйірлік тақтаның төменгі жағына айналдырып, **Жіберу** опциясын таңдаңыз.

   HTTP жауабы тақтаның төменгі жағында көрсетіледі.

## <a name="create-a-new-app-registration-in-the-azure-portal"></a>Azure порталында жаңа бағдарлама тіркелімін жасаңыз

Жаңасын жасау [қолданбаны тіркеу](/graph/auth-register-app-v2) берілген рұқсаттарды пайдаланып Azure қолданбасында Customer Insights API интерфейстерін пайдалану.

1. Аяқтау [Жұмысты бастау бөлімі](#get-started-trying-the-customer-insights-apis) .

1. Customer Insights деректеріне кіретін тіркелгімен [Azure порталына](https://portal.azure.com) кіріңіз.

1. Іздеңіз, содан кейін таңдаңыз **Қолданбаларды тіркеу** .

1. **Жаңа тіркелім** опциясын таңдап, бағдарлама атауын беріңіз де, тіркелгі түрін таңдаңыз.

   Оған қоса, URL мекенжайын бағыттауды қосыңыз. http://localhost сайты жергілікті компьютерде бағдарлама әзірлеу үшін жеткілікті.

1. **Тіркеу** опциясын таңдаңыз.

1. Жаңа бағдарлама тіркелімінде **API рұқсаттары** бөліміне өтіңіз.

1. таңдаңыз **Рұқсат қосыңыз** және таңдаңыз **Customer Insights үшін Dynamics 365 AI** бүйірлік тақтада.

1. **Рұқсат түрі** үшін **Өкілетті рұқсаттар** параметрін таңдаңыз, содан кейін **user_impersonation** рұқсатын таңдаңыз.

1. **Рұқсаттарды қосу** опциясын таңдаңыз.

1. Бағдарламаны тіркеуді аяқтау үшін **Әкімші келісімін келесілерге беру...** опциясын таңдаңыз.

1. Пайдаланушы кірместен API интерфейсіне кіру үшін мына мекенжайға өтіңіз [Серверден серверге қолданба рұқсаттары](#server-to-server-application-permissions) .

Бұл қолданбаны тіркеу үшін қолданбаны/клиент идентификаторын пайдалана аласыз [Microsoft аутентификация кітапханасы (MSAL)](/azure/active-directory/develop/msal-overview) API-ге сұрауыңызбен жіберу үшін жеткізуші таңбалауышын алу үшін.

<!-- :::image type="content" source="media/grant-admin-consent.gif" alt-text="How to grant admin consent."::: -->

Біздің клиенттік кітапханаларымызда API интерфейстерін қолдану туралы ақпаратты [Customer Insights клиенттік кітапханалары](#customer-insights-client-libraries) бөлімін қараңыз.

### <a name="server-to-server-application-permissions"></a>Сервераралық бағдарлама рұқсаттары

Пайдаланушы әрекетін қажет етпейтін және серверде іске қосуға болатын қолданбаны тіркеуді жасаңыз.

1. Azure порталында бағдарламаны тіркеуде **API рұқсаттары** бөліміне өтіңіз.

1. **Рұқсат қосу** опциясын таңдаңыз.

1. **Менің ұйымым пайдаланатын API интерфейстері** қойыншасын таңдаңыз және тізімнен **Dynamics 365 AI for Customer Insights** бағдарламасын таңдаңыз.

1. **Рұқсат түрі** үшін **Бағдарлама рұқсаттары** параметрін таңдаңыз, содан кейін **CustomerInsights.Api.All** рұқсатын таңдаңыз.

1. **Рұқсаттарды қосу** опциясын таңдаңыз.

1. Бағдарламаны тіркеу үшін **API рұқсаттары** бөліміне қайта өтіңіз.

1. Бағдарламаны тіркеуді аяқтау үшін **Әкімші келісімін келесілерге беру...** опциясын таңдаңыз.

   <!--  :::image type="content" source="media/grant-admin-consent.gif" alt-text="How to grant admin consent."::: -->

1. Customer Insights ішінде пайдаланушы ретінде қолданбаны тіркеу атауын қосыңыз.

   1. Customer Insights қолданбасын ашыңыз, өтіңіз **Админ** > **Қауіпсіздік** және таңдаңыз **Пайдаланушыларды қосыңыз** .

   1. Бағдарламаны тіркеу атауын іздеп, оны іздеу нәтижелерінен таңдап, **Сақтау** түймесін таңдаңыз.

## <a name="sample-queries"></a>Сұрау үлгісі

API интерфейстерімен жұмыс істеуге арналған OData үлгі сұрауларының қысқаша тізімін қараңыз [OData сұрау мысалдары](odata-examples.md) .

## <a name="customer-insights-client-libraries"></a>Customer Insights клиенттік кітапханалары

Customer Insights API интерфейстері үшін қолжетімді клиент кітапханаларын пайдалануды бастаңыз. Кітапхананың барлық бастапқы коды мен бағдарлама үлгілерін [Customer Insights GitHub бетінен](https://github.com/microsoft/Dynamics365-CustomerInsights-Client-Libraries) табуға болады.

### <a name="c-nuget"></a>C# NuGet

C# клиенттік кітапханаларын пайдаланыңыз NuGet .org. Қазіргі уақытта бума netstandard2.0 және netcoreapp2.0 жақтауларына бағытталған. туралы қосымша ақпарат алу үшін NuGet пакет, қараңыз [Microsoft.Dynamics.CustomerInsights.Api](https://www.nuget.org/packages/Microsoft.Dynamics.CustomerInsights.Api/) .

#### <a name="add-the-c-client-library-to-a-c-project"></a>C# жобасына C# клиенттік кітапханасын қосыңыз

1. Visual Studio бағдарламасында жобаға арналған **NuGet жиынтық менеджері** жүйесін ашыңыз.

1. **Microsoft.Dynamics.CustomerInsights.Api** іздеңіз.

1. Жобаға жиынтық қосу үшін **Орнату** түймесін таңдаңыз.

   Сонымен қатар **NuGet жиынтық менеджері консолі** жүйесінде мына пәрменді орындаңыз: `Install-Package -Id Microsoft.Dynamics.CustomerInsights.Api -Source nuget.org -ProjectName <project name> [-Version <version>]`

   <!--  :::image type="content" source="media/visual-studio-nuget-package.gif" alt-text="Add NuGet package to Visual Studio project."::: -->

#### <a name="use-the-c-client-library"></a>C# клиенттік кітапханасын пайдаланыңыз

1. Бұрыннан бар [Azure бағдарламасын тіркеу](#create-a-new-app-registration-in-the-azure-portal) жүйесін пайдаланып `AccessToken` алу үшін [Microsoft аутентификация кітапханасы (MSAL)](/azure/active-directory/develop/msal-overview) пайдаланыңыз.

1. Сәтті аутентификация және таңбалауыш алғаннан кейін жаңасын жасаңыз немесе барын пайдаланыңыз`HttpClient` бірге **DefaultRequestHeaders "Авторизация"** деп орнатыңыз **Тасымалдаушы «қолжетімділік белгісі»** және **Ocp-Apim-жазылым кілті** мәніне орнатыңыз [**жазылым кілті** Customer Insights ортаңыздан](#get-started-trying-the-customer-insights-apis) .   

   Қажет болған жағдайда **Авторизация** тақырыбын қалпына келтіріңіз. Мысалы, таңбалауыш мерзімі аяқталған кезде.

1. Осы `HttpClient` парамтерін `CustomerInsights` клиенті құрылымына өткізіңіз.

   <!--   :::image type="content" source="media/httpclient-sample.png" alt-text="Sample of httpclient."::: -->

1. Клиентпен «кеңейту әдістеріне» қоңырау шалыңыз, мысалы,`GetAllInstancesAsync`. Егер негізге қол жетімділік болса`Microsoft.Rest.HttpOperationResponse` таңдалған болса, "http хабарлама әдістерін" пайдаланыңыз, мысалы,`GetAllInstancesWithHttpMessagesAsync` .

1. Жауап болуы ықтимал`object` теріңіз, себебі әдіс бірнеше түрді қайтара алады (мысалы,`IList<InstanceInfo>` және`ApiErrorResult` ). Қайтару түрін тексеру үшін файлда көрсетілген жауап түрлеріндегі нысандарды пайдаланыңыз [API мәліметтер беті](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights) сол операция үшін.

   Егер сұрау туралы қосымша ақпарат қажет болса, бастапқы жауап нысанына қол жеткізу үшін  **http хабары әдістерін** пайдаланыңыз.

### <a name="nodejs-package"></a>NodeJS бумасы

NPM арқылы қолжетімді NodeJS клиенттік кітапханаларын пайдаланыңыз: https://www.npmjs.com/package/@microsoft/customerinsights

### <a name="python-package"></a>Python бумасы

PyPi арқылы қолжетімді Python клиенттік кітапханаларын пайдаланыңыз: https://pypi.org/project/customerinsights/

[!INCLUDE [footer-include](includes/footer-banner.md)]
