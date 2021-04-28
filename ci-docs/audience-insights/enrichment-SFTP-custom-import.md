---
title: SFTP реттелетін импорттауы көмегімен арттыру
description: SFTP ерттелетін импорт арттыруы туралы жалпы ақпарат.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: a2d450635c19432bdd88db74b61c17febdeb568d
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: kk-KZ
ms.lasthandoff: 04/14/2021
ms.locfileid: "5896288"
---
# <a name="enrich-customer-profiles-with-custom-data-preview"></a><span data-ttu-id="4659c-103">Тұтынушы профилдерін реттелетін деректермен арттыру (алдын ала қарау)</span><span class="sxs-lookup"><span data-stu-id="4659c-103">Enrich customer profiles with custom data (preview)</span></span>

<span data-ttu-id="4659c-104">Файлдарды қауіпсіз тасымалдау протоколының (SFTP) custom import қызметі деректерді біріздендіру процесі арқылы өтпейтін деректерді импорттауға мүмкіндік береді.</span><span class="sxs-lookup"><span data-stu-id="4659c-104">Secure File Transfer Protocol (SFTP) custom import enables you to import data that does not have to go through the process of data unification.</span></span> <span data-ttu-id="4659c-105">Бұл деректерді алудың икемді, қауіпсіз және қарапайым жолы.</span><span class="sxs-lookup"><span data-stu-id="4659c-105">It's a flexible, secure, and easy way to bring in your data.</span></span> <span data-ttu-id="4659c-106">SFTP теңшелетін импортын арттыру үшін қажет тұтынушы профилі деректерін экспорттауға мүмкіндік беретін [SFTP экспортымен](export-sftp.md) бірге үйлесімдікте пайдалануға болады.</span><span class="sxs-lookup"><span data-stu-id="4659c-106">SFTP custom import can be used in combination with [SFTP export](export-sftp.md) that lets you export the customer profile data that is needed for enrichment.</span></span> <span data-ttu-id="4659c-107">Содан кейін деректерді өңдеуге, арттыруға болады және SFTP реттелетін импортын арттырылған деректерді Dynamics 365 Customer Insights бағдарламасының аудитория түсініктері мүмкіндігіне қайтару үшін пайдалануға болады.</span><span class="sxs-lookup"><span data-stu-id="4659c-107">The data can then be processed, enriched, and SFTP custom import can be used to bring the enriched data back to the audience insights capability of Dynamics 365 Customer Insights.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="4659c-108">Алғышарттар</span><span class="sxs-lookup"><span data-stu-id="4659c-108">Prerequisites</span></span>

<span data-ttu-id="4659c-109">SFTP реттелетін импортын конфигурациялау үшін келесі алғышарттар орындалуы керек:</span><span class="sxs-lookup"><span data-stu-id="4659c-109">To configure SFTP custom import, the following prerequisites must be met:</span></span>

- <span data-ttu-id="4659c-110">Сізде SFTP хостына импортталатын файлдың аты мен орны (жолы) бар.</span><span class="sxs-lookup"><span data-stu-id="4659c-110">You have the filename and location (path) of the file to be imported on the SFTP host.</span></span>
- <span data-ttu-id="4659c-111">Импортталатын деректер үшін [Common Data Model схемасын](/common-data-model/) анықтайтын *model.json* файлы бар.</span><span class="sxs-lookup"><span data-stu-id="4659c-111">There is a *model.json* file that specifies [the Common Data Model schema](/common-data-model/) for the data to be imported.</span></span> <span data-ttu-id="4659c-112">Бұл файл импортталатын файл сияқты бірдей каталогта болуы тиіс.</span><span class="sxs-lookup"><span data-stu-id="4659c-112">This file must be in the same directory as the file to import.</span></span>
- <span data-ttu-id="4659c-113">SFTP қосылымын әкімші конфигурациялап қойған *немесе* сізде [әкімші](permissions.md#administrator) рұқсаттары бар.</span><span class="sxs-lookup"><span data-stu-id="4659c-113">An SFTP connection has already been configured by an administrator *or* you have [administrator](permissions.md#administrator) permissions.</span></span> <span data-ttu-id="4659c-114">Сізге деректерді импорттайтын SFTP орны үшін пайдаланушының тіркелгі деректері, URL мекенжайы және порт нөмірі қажет болады.</span><span class="sxs-lookup"><span data-stu-id="4659c-114">You'll need the user credentials, URL, and port number for the SFTP location where you want to import data from.</span></span>


## <a name="configure-the-import"></a><span data-ttu-id="4659c-115">Импорттауды конфигурациялау</span><span class="sxs-lookup"><span data-stu-id="4659c-115">Configure the import</span></span>

1. <span data-ttu-id="4659c-116">**Деректер** > **Арттыру** тармағына өтіп, **Анықтау** қойыншасын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="4659c-116">Go to **Data** > **Enrichment** and select the **Discover** tab.</span></span>

1. <span data-ttu-id="4659c-117">**SFTP custom import тақтасында** **Менің деректерімді жақсарту** параметрін таңдаңыз, содан кейін **Жұмысты бастау** түймешігін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="4659c-117">On the **SFTP custom import tile**, select **Enrich my data** and then select **Get started**.</span></span>

   :::image type="content" source="media/SFTP_Custom_Import_tile.png" alt-text="SFTP custom import тақтасы.":::

1. <span data-ttu-id="4659c-119">Ашылмалы тізімнен [қосылымды](connections.md) таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="4659c-119">Select a [connection](connections.md) from the drop-down.</span></span> <span data-ttu-id="4659c-120">Егер қосылым болмаса, әкімшіге хабарласыңыз.</span><span class="sxs-lookup"><span data-stu-id="4659c-120">Contact an administrator if no connection is available.</span></span> <span data-ttu-id="4659c-121">Егер сіз әкімші болсаңыз, **Қосылым қосу** түймешігін және ашылмалы тізімнен **SFTP Custom Import** параметрін таңдау арқылы қосылым жасай аласыз.</span><span class="sxs-lookup"><span data-stu-id="4659c-121">If you are an administrator, you can create a connection by selecting **Add connection** and choosing **SFTP Custom Import** from the drop-down.</span></span>

1. <span data-ttu-id="4659c-122">Таңдалған қосылымды растау үшін **Custom Import қызметіне қосылу** түймешігін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="4659c-122">Select **Connect to Custom Import** to confirm the selected connection.</span></span>

1.  <span data-ttu-id="4659c-123">**Келесі** түймешігін таңдаңыз және импорттау керек деректер файлының **Файл атауы** және **Жолы** параметрін енгізіңіз.</span><span class="sxs-lookup"><span data-stu-id="4659c-123">Select **Next** and enter the **Filename** and **Path** of the data file that you want to import.</span></span>

    :::image type="content" source="media/enrichment-SFTP-path-and-filename.png" alt-text="Деректердің орнын енгізу кезіндегі скриншот.":::

1. <span data-ttu-id="4659c-125">**Келесі** түймешігін таңдаңыз және жақсарту атауын және шығыс ұйымның атауын көрсетіңіз.</span><span class="sxs-lookup"><span data-stu-id="4659c-125">Select **Next** and provide a name for the enrichment and a name for the output entity.</span></span> 

1. <span data-ttu-id="4659c-126">Таңдауларды қарап шыққаннан кейін **Жақсартуды сақтау** түймешігін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="4659c-126">Select **Save enrichment** after reviewing your choices.</span></span>

## <a name="configure-the-connection-for-sftp-custom-import"></a><span data-ttu-id="4659c-127">SFTP Custom Import үшін қосылымды конфигурациялау</span><span class="sxs-lookup"><span data-stu-id="4659c-127">Configure the connection for SFTP Custom Import</span></span> 

<span data-ttu-id="4659c-128">Қосылымдарды конфигурациялау үшін сіз әкімші болуыңыз керек.</span><span class="sxs-lookup"><span data-stu-id="4659c-128">You need to be an administrator to configure connections.</span></span> <span data-ttu-id="4659c-129">Жақсартуды конфигурациялау кезінде **Қосылым қосу** түймешігін таңдаңыз *немесе* **Әкімші** > **Қосылымдар** тармағына өтіңіз және Custom Import тақтасында **Орнату** түймешігін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="4659c-129">Select **Add connection** when configuring an enrichment *or* go to **Admin** > **Connections** and select **Set up** on the Custom Import tile.</span></span>

1. <span data-ttu-id="4659c-130">Қосылым атауын **Көрсетілетін атауы** терезесіне енгізіңіз.</span><span class="sxs-lookup"><span data-stu-id="4659c-130">Enter a name for the connection in the **Display name** box.</span></span>

1. <span data-ttu-id="4659c-131">Импортталатын деректер орналасқан STFP сервері үшін жарамды пайдаланушы атын, құпиясөзін және хосттың URL мекенжайын енгізіңіз.</span><span class="sxs-lookup"><span data-stu-id="4659c-131">Enter valid user name, password, and host URL for the STFP server the data to be imported resides on.</span></span>

1. <span data-ttu-id="4659c-132">**Келісемін** құсбелгісін таңдау арқылы **Деректер құпиялығы мен сәйкестігі** келісімін қарап шығыңыз және қамтамасыз етіңіз.</span><span class="sxs-lookup"><span data-stu-id="4659c-132">Review and provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox.</span></span>

1. <span data-ttu-id="4659c-133">Конфигурацияны тексеру үшін **Тексеру** түймешігін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="4659c-133">Select **Verify** to validate the configuration.</span></span>

1. <span data-ttu-id="4659c-134">Тексеру аяқталғаннан кейін қосылымды **Сақтау** түймешігін басу арқылы сақтауға болады.</span><span class="sxs-lookup"><span data-stu-id="4659c-134">Once the verification has completed, the connection can be saved by clicking **Save**.</span></span>

> [!div class="mx-imgBorder"]
   > <span data-ttu-id="4659c-135">![Experian қосылымын конфигурациялау беті](media/enrichment-SFTP-connection.png "Experian қосылымын конфигурациялау беті")</span><span class="sxs-lookup"><span data-stu-id="4659c-135">![Experian connection configuration page](media/enrichment-SFTP-connection.png "Experian connection configuration page")</span></span>


## <a name="defining-field-mappings"></a><span data-ttu-id="4659c-136">Салыстырылатын өрісті анықтау</span><span class="sxs-lookup"><span data-stu-id="4659c-136">Defining field mappings</span></span> 

<span data-ttu-id="4659c-137">SFTP серверіне импортталатын файлды қамтитын каталогта *model.json* файлы болуы тиіс.</span><span class="sxs-lookup"><span data-stu-id="4659c-137">The directory that contains the file to be imported on the SFTP server must also contain a *model.json* file.</span></span> <span data-ttu-id="4659c-138">Бұл файл деректерді импорттауға арналған схеманы анықтайды.</span><span class="sxs-lookup"><span data-stu-id="4659c-138">This file defines the schema to use for importing the data.</span></span> <span data-ttu-id="4659c-139">Салыстырылатын өрісті көрсету үшін схема [Common Data Model](/common-data-model/) пайдалануы керек.</span><span class="sxs-lookup"><span data-stu-id="4659c-139">The schema has to use [the Common Data Model](/common-data-model/) to specify the field mapping.</span></span> <span data-ttu-id="4659c-140">Model.json файлының қарапайым мысалы келесідей:</span><span class="sxs-lookup"><span data-stu-id="4659c-140">A simple example of a model.json file looks like this:</span></span>

```
{
    "name": "EnrichmentFromMicrosoft",
    "description": "Model containing data enrichment",
    "entities": [
        {
            "name": "CustomImport",
            "attributes": [
                {
                    "name": "CustomerId",
                    "friendlyName": "Client id",
                    "dataType": "string"
                },
                {
                    "name": "PreferredCity",
                    "friendlyName": "Preferred City for vacation",
                    "dataType": "string"
                },
                {
                    "name": "PreferredTransportation",
                    "friendlyName": "Preferred transportation",
                    "dataType": "string"
                }
            ],
            "annotations": [
                {
                    "name": "c360:PrimaryKey",
                    "value": "CustomerId"
                }
            ]
        }
    ],
    "modifiedTime": "2020-01-02T12:00:00+08:00",
    "annotations": [
        {
            "name": "testAnnotation",
            "value": "testValue"
        }
    ]
}
```

## <a name="enrichment-results"></a><span data-ttu-id="4659c-141">Толықтыру нәтижелері</span><span class="sxs-lookup"><span data-stu-id="4659c-141">Enrichment results</span></span>

<span data-ttu-id="4659c-142">Арттыру процесін бастау үшін пәрмендер жолағынан **Іске қосу** пәрменін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="4659c-142">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="4659c-143">Сондай-ақ, жүйеге [жоспарланған жаңарту](system.md#schedule-tab) бөлігі ретінде арттыруды автоматты түрде іске қосуына мүмкіндік беруге болады.</span><span class="sxs-lookup"><span data-stu-id="4659c-143">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="4659c-144">Өңдеу уақыты импортталатын деректердің көлеміне және SFTP серверіне қосылуға байланысты болады.</span><span class="sxs-lookup"><span data-stu-id="4659c-144">The processing time will depend on the size of the data to be imported and the connection to the SFTP server.</span></span>

<span data-ttu-id="4659c-145">Арттыру процесі аяқталғаннан кейін, **Менің арттыруларым** астындағы жаңа импортталған реттелетін арттыру деректерін қарап шығуға болады.</span><span class="sxs-lookup"><span data-stu-id="4659c-145">After the enrichment process completes, you can review your newly imported custom enrichment data under **My enrichments**.</span></span> <span data-ttu-id="4659c-146">Сонымен қатар, соңғы жаңартудың уақыты мен арттырылған профильдер санын таба аласыз.</span><span class="sxs-lookup"><span data-stu-id="4659c-146">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="4659c-147">**Толықтырылған деректерді көру** параметрін таңдау арқылы әрбір толықтырылған профильдің толық көрінісіне қатынаса аласыз.</span><span class="sxs-lookup"><span data-stu-id="4659c-147">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="4659c-148">Келесі қадамдар</span><span class="sxs-lookup"><span data-stu-id="4659c-148">Next steps</span></span>

<span data-ttu-id="4659c-149">Толықтырылған тұтынушы деректерінің негізінде жасаңыз.</span><span class="sxs-lookup"><span data-stu-id="4659c-149">Build on top of your enriched customer data.</span></span> <span data-ttu-id="4659c-150">Тұтынушыларға жеке тәжірибе беру үшін [сегменттер](segments.md), [шаралар](measures.md) жасаңыз және [деректерді экспорттаңыз](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="4659c-150">Create [segments](segments.md), [measures](measures.md), and [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
