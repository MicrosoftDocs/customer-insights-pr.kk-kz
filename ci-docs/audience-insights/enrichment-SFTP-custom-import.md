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
ms.openlocfilehash: f92b36ac5364ea8586f9cbba7ba03178641555c0
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: kk-KZ
ms.lasthandoff: 06/24/2021
ms.locfileid: "6304657"
---
# <a name="enrich-customer-profiles-with-custom-data-preview"></a><span data-ttu-id="02107-103">Тұтынушы профилдерін реттелетін деректермен арттыру (алдын ала қарау)</span><span class="sxs-lookup"><span data-stu-id="02107-103">Enrich customer profiles with custom data (preview)</span></span>

<span data-ttu-id="02107-104">Қауіпсіз файл тасымалдау протоколы (SFTP) реттелетін импорттау деректерді біріктіру процесі арқылы жүрмейтін деректерді импорттауға мүмкіндік береді.</span><span class="sxs-lookup"><span data-stu-id="02107-104">Secure File Transfer Protocol (SFTP) custom import enables you to import data that doesn't have to go through the process of data unification.</span></span> <span data-ttu-id="02107-105">Бұл деректерді алудың икемді, қауіпсіз және қарапайым жолы.</span><span class="sxs-lookup"><span data-stu-id="02107-105">It's a flexible, secure, and easy way to bring in your data.</span></span> <span data-ttu-id="02107-106">SFTP теңшелетін импортын арттыру үшін қажет тұтынушы профилі деректерін экспорттауға мүмкіндік беретін [SFTP экспортымен](export-sftp.md) бірге үйлесімдікте пайдалануға болады.</span><span class="sxs-lookup"><span data-stu-id="02107-106">SFTP custom import can be used in combination with [SFTP export](export-sftp.md) that lets you export the customer profile data that is needed for enrichment.</span></span> <span data-ttu-id="02107-107">Содан кейін деректерді өңдеуге және толықтыруға болады, ал толықтырылған деректерді Dynamics 365 Customer Insights бағдарламасының аудитория түсініктері мүмкіндігіне қайтару үшін SFTP реттелетін импорттауын пайдалануға болады.</span><span class="sxs-lookup"><span data-stu-id="02107-107">The data can then be processed and enriched, and SFTP custom import can be used to bring the enriched data back to the audience insights capability of Dynamics 365 Customer Insights.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="02107-108">Алғышарттар</span><span class="sxs-lookup"><span data-stu-id="02107-108">Prerequisites</span></span>

<span data-ttu-id="02107-109">SFTP реттелетін импортын конфигурациялау үшін келесі алғышарттар орындалуы керек:</span><span class="sxs-lookup"><span data-stu-id="02107-109">To configure SFTP custom import, the following prerequisites must be met:</span></span>

- <span data-ttu-id="02107-110">Сізде SFTP хостына импортталатын файл атауы және файлдың орны (жолы) бар.</span><span class="sxs-lookup"><span data-stu-id="02107-110">You have the file name and location (path) of the file to be imported on the SFTP host.</span></span>
- <span data-ttu-id="02107-111">Импортталатын деректер үшін [Common Data Model схемасын](/common-data-model/) анықтайтын *model.json* файлы бар.</span><span class="sxs-lookup"><span data-stu-id="02107-111">There is a *model.json* file that specifies [the Common Data Model schema](/common-data-model/) for the data to be imported.</span></span> <span data-ttu-id="02107-112">Бұл файл импортталатын файл сияқты бірдей каталогта болуы тиіс.</span><span class="sxs-lookup"><span data-stu-id="02107-112">This file must be in the same directory as the file to import.</span></span>
- <span data-ttu-id="02107-113">SFTP қосылымын әкімші конфигурациялап қойған *немесе* сізде [әкімші](permissions.md#administrator) рұқсаттары бар.</span><span class="sxs-lookup"><span data-stu-id="02107-113">An SFTP connection has already been configured by an administrator *or* you have [administrator](permissions.md#administrator) permissions.</span></span> <span data-ttu-id="02107-114">Сізге деректерді импорттайтын SFTP орны үшін пайдаланушының тіркелгі деректері, URL мекенжайы және порт нөмірі қажет болады.</span><span class="sxs-lookup"><span data-stu-id="02107-114">You'll need the user credentials, URL, and port number for the SFTP location where you want to import data from.</span></span>


## <a name="configure-the-import"></a><span data-ttu-id="02107-115">Импорттауды конфигурациялау</span><span class="sxs-lookup"><span data-stu-id="02107-115">Configure the import</span></span>

1. <span data-ttu-id="02107-116">**Деректер** > **Арттыру** тармағына өтіп, **Анықтау** қойыншасын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="02107-116">Go to **Data** > **Enrichment** and select the **Discover** tab.</span></span>

1. <span data-ttu-id="02107-117">**SFTP custom import тақтасында** **Менің деректерімді жақсарту** параметрін таңдаңыз, содан кейін **Жұмысты бастау** түймешігін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="02107-117">On the **SFTP custom import tile**, select **Enrich my data** and then select **Get started**.</span></span>

   :::image type="content" source="media/SFTP_Custom_Import_tile.png" alt-text="SFTP custom import тақтасы.":::

1. <span data-ttu-id="02107-119">Ашылмалы тізімнен [қосылым](connections.md) таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="02107-119">Select a [connection](connections.md) from the dropdown list.</span></span> <span data-ttu-id="02107-120">Егер қосылым болмаса, әкімшіге хабарласыңыз.</span><span class="sxs-lookup"><span data-stu-id="02107-120">Contact an administrator if no connection is available.</span></span> <span data-ttu-id="02107-121">Егер сіз әкімші болсаңыз, **Қосылым қосу** және ашылмалы тізімнен **SFTP реттелетін импорттау** қызметін таңдау арқылы қосылым жасай аласыз.</span><span class="sxs-lookup"><span data-stu-id="02107-121">If you are an administrator, you can create a connection by selecting **Add connection** and choosing **SFTP Custom Import** from the dropdown list.</span></span>

1. <span data-ttu-id="02107-122">Таңдалған қосылымды растау үшін **Custom Import қызметіне қосылу** түймешігін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="02107-122">Select **Connect to Custom Import** to confirm the selected connection.</span></span>

1.  <span data-ttu-id="02107-123">**Келесі** түймешігін таңдаңыз және импорттау керек деректер файлының **Жол** және **Файл атауы** өрістерін енгізіңіз.</span><span class="sxs-lookup"><span data-stu-id="02107-123">Select **Next** and enter the **Path** and **Filename** of the data file that you want to import.</span></span>

    :::image type="content" source="media/enrichment-SFTP-path-and-filename.png" alt-text="Деректердің орнын енгізу кезіндегі скриншот.":::

1. <span data-ttu-id="02107-125">**Келесі** түймешігін таңдаңыз және жақсарту атауын және шығыс ұйымның атауын көрсетіңіз.</span><span class="sxs-lookup"><span data-stu-id="02107-125">Select **Next** and provide a name for the enrichment and a name for the output entity.</span></span> 

1. <span data-ttu-id="02107-126">Таңдауларды қарап шыққаннан кейін **Жақсартуды сақтау** түймешігін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="02107-126">Select **Save enrichment** after reviewing your choices.</span></span>

## <a name="configure-the-connection-for-sftp-custom-import"></a><span data-ttu-id="02107-127">SFTP Custom Import үшін қосылымды конфигурациялау</span><span class="sxs-lookup"><span data-stu-id="02107-127">Configure the connection for SFTP Custom Import</span></span> 

<span data-ttu-id="02107-128">Қосылымдарды конфигурациялау үшін сіз әкімші болуыңыз керек.</span><span class="sxs-lookup"><span data-stu-id="02107-128">You need to be an administrator to configure connections.</span></span> <span data-ttu-id="02107-129">Жақсартуды конфигурациялау кезінде **Қосылым қосу** түймешігін таңдаңыз *немесе* **Әкімші** > **Қосылымдар** тармағына өтіңіз және Custom Import тақтасында **Орнату** түймешігін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="02107-129">Select **Add connection** when configuring an enrichment *or* go to **Admin** > **Connections** and select **Set up** on the Custom Import tile.</span></span>

1. <span data-ttu-id="02107-130">Қосылым атауын **Көрсетілетін атауы** терезесіне енгізіңіз.</span><span class="sxs-lookup"><span data-stu-id="02107-130">Enter a name for the connection in the **Display name** box.</span></span>

1. <span data-ttu-id="02107-131">Импортталатын деректер орналасқан SFTP сервері үшін жарамды пайдаланушы атын, құпиясөзді және хосттың URL мекенжайын енгізіңіз.</span><span class="sxs-lookup"><span data-stu-id="02107-131">Enter a valid username, password, and host URL for the SFTP server that the data to be imported resides on.</span></span>

1. <span data-ttu-id="02107-132">**Келісемін** құсбелгісін таңдау арқылы **Деректер құпиялығы мен сәйкестігі** келісімін қарап шығыңыз және қамтамасыз етіңіз.</span><span class="sxs-lookup"><span data-stu-id="02107-132">Review and provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox.</span></span>

1. <span data-ttu-id="02107-133">Конфигурацияны тексеру үшін **Тексеру** түймешігін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="02107-133">Select **Verify** to validate the configuration.</span></span>

1. <span data-ttu-id="02107-134">Тексеру аяқталғаннан кейін қосылымды **Сақтау** түймешігін таңдау арқылы сақтауға болады.</span><span class="sxs-lookup"><span data-stu-id="02107-134">Once the verification has completed, the connection can be saved by selecting **Save**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="02107-135">![Experian қосылым конфигурациясы беті](media/enrichment-SFTP-connection.png "Experian қосылым конфигурациясы беті")</span><span class="sxs-lookup"><span data-stu-id="02107-135">![Experian connection configuration page](media/enrichment-SFTP-connection.png "Experian connection configuration page")</span></span>


## <a name="defining-field-mappings"></a><span data-ttu-id="02107-136">Салыстырылатын өрісті анықтау</span><span class="sxs-lookup"><span data-stu-id="02107-136">Defining field mappings</span></span> 

<span data-ttu-id="02107-137">SFTP серверіне импортталатын файлды қамтитын каталогта *model.json* файлы болуы тиіс.</span><span class="sxs-lookup"><span data-stu-id="02107-137">The directory that contains the file to be imported on the SFTP server must also contain a *model.json* file.</span></span> <span data-ttu-id="02107-138">Бұл файл деректерді импорттауға арналған схеманы анықтайды.</span><span class="sxs-lookup"><span data-stu-id="02107-138">This file defines the schema to use for importing the data.</span></span> <span data-ttu-id="02107-139">Өріс салыстыруын көрсету үшін схема [Common Data Model](/common-data-model/) қызметін пайдалануы керек.</span><span class="sxs-lookup"><span data-stu-id="02107-139">The schema has to use [Common Data Model](/common-data-model/) to specify the field mapping.</span></span> <span data-ttu-id="02107-140">Model.json файлының қарапайым мысалы келесідей:</span><span class="sxs-lookup"><span data-stu-id="02107-140">A simple example of a model.json file looks like this:</span></span>

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

## <a name="enrichment-results"></a><span data-ttu-id="02107-141">Толықтыру нәтижелері</span><span class="sxs-lookup"><span data-stu-id="02107-141">Enrichment results</span></span>

<span data-ttu-id="02107-142">Арттыру процесін бастау үшін пәрмендер жолағынан **Іске қосу** пәрменін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="02107-142">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="02107-143">Сондай-ақ, жүйеге [жоспарланған жаңарту](system.md#schedule-tab) бөлігі ретінде арттыруды автоматты түрде іске қосуына мүмкіндік беруге болады.</span><span class="sxs-lookup"><span data-stu-id="02107-143">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="02107-144">Өңдеу уақыты импортталатын деректердің көлеміне және SFTP серверіне қосылуға байланысты болады.</span><span class="sxs-lookup"><span data-stu-id="02107-144">The processing time will depend on the size of the data to be imported and the connection to the SFTP server.</span></span>

<span data-ttu-id="02107-145">Арттыру процесі аяқталғаннан кейін, **Менің арттыруларым** астындағы жаңа импортталған реттелетін арттыру деректерін қарап шығуға болады.</span><span class="sxs-lookup"><span data-stu-id="02107-145">After the enrichment process completes, you can review your newly imported custom enrichment data under **My enrichments**.</span></span> <span data-ttu-id="02107-146">Сонымен қатар, соңғы жаңартудың уақыты мен арттырылған профильдер санын таба аласыз.</span><span class="sxs-lookup"><span data-stu-id="02107-146">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="02107-147">**Толықтырылған деректерді көру** параметрін таңдау арқылы әрбір толықтырылған профильдің толық көрінісіне қатынаса аласыз.</span><span class="sxs-lookup"><span data-stu-id="02107-147">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="02107-148">Келесі қадамдар</span><span class="sxs-lookup"><span data-stu-id="02107-148">Next steps</span></span>

<span data-ttu-id="02107-149">Толықтырылған тұтынушы деректерінің негізінде жасаңыз.</span><span class="sxs-lookup"><span data-stu-id="02107-149">Build on top of your enriched customer data.</span></span> <span data-ttu-id="02107-150">Тұтынушыларға жеке тәжірибелер ұсыну үшін [сегменттер](segments.md) мен [өлшемдер](measures.md) жасаңыз және [деректерді экспорттаңыз](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="02107-150">Create [segments](segments.md) and [measures](measures.md), and [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
