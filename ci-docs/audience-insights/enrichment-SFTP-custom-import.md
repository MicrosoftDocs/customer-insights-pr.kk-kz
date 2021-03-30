---
title: SFTP реттелетін импорттауы көмегімен арттыру
description: SFTP ерттелетін импорт арттыруы туралы жалпы ақпарат.
ms.date: 11/18/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: d9e095ef793cbd25415864f76a541dce68fafe47
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: kk-KZ
ms.lasthandoff: 03/15/2021
ms.locfileid: "5595862"
---
# <a name="enrich-customer-profiles-with-custom-data-preview"></a><span data-ttu-id="083cf-103">Тұтынушы профилдерін реттелетін деректермен арттыру (алдын ала қарау)</span><span class="sxs-lookup"><span data-stu-id="083cf-103">Enrich customer profiles with custom data (preview)</span></span>

<span data-ttu-id="083cf-104">Қауіпсіз файл тасымалдау протоколы (SFTP) реттелетін импорттау деректерді біріктіру процесі арқылы жүрмейтін деректерді импорттауға мүмкіндік береді.</span><span class="sxs-lookup"><span data-stu-id="083cf-104">Secure File Transfer Protocol(SFTP) custom import enables you to import data that doesn't have to go through the process of data unification.</span></span> <span data-ttu-id="083cf-105">Бұл деректерді алудың икемді, қауіпсіз және қарапайым жолы.</span><span class="sxs-lookup"><span data-stu-id="083cf-105">It's a flexible, secure, and easy way to bring in your data.</span></span> <span data-ttu-id="083cf-106">SFTP теңшелетін импортын арттыру үшін қажет тұтынушы профилі деректерін экспорттауға мүмкіндік беретін [SFTP экспортымен](export-sftp.md) бірге үйлесімдікте пайдалануға болады.</span><span class="sxs-lookup"><span data-stu-id="083cf-106">SFTP custom import can be used in combination with [SFTP export](export-sftp.md) that lets you export the customer profile data that is needed for enrichment.</span></span> <span data-ttu-id="083cf-107">Содан кейін деректерді өңдеуге, арттыруға болады және SFTP реттелетін импортын арттырылған деректерді Dynamics 365 Customer Insights бағдарламасының аудитория түсініктері мүмкіндігіне қайтару үшін пайдалануға болады.</span><span class="sxs-lookup"><span data-stu-id="083cf-107">The data can then be processed, enriched, and SFTP custom import can be used to bring the enriched data back to the audience insights capability of Dynamics 365 Customer Insights.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="083cf-108">Алғышарттар</span><span class="sxs-lookup"><span data-stu-id="083cf-108">Prerequisites</span></span>

<span data-ttu-id="083cf-109">SFTP реттелетін импортын конфигурациялау үшін келесі алғышарттар орындалуы керек:</span><span class="sxs-lookup"><span data-stu-id="083cf-109">To configure SFTP custom import, the following prerequisites must be met:</span></span>

- <span data-ttu-id="083cf-110">Сізде деректер импортталатын SFTP орны үшін пайдаланушы тіркелгі деректері (пайдаланушы аты және құпиясөз) бар.</span><span class="sxs-lookup"><span data-stu-id="083cf-110">You have user credentials (user name and password) for the SFTP location where the data that is going to be imported from.</span></span>
- <span data-ttu-id="083cf-111">Сізде STFP хостына арналған URL мекенжайы және порт нөмірі (әдетте 22) бар.</span><span class="sxs-lookup"><span data-stu-id="083cf-111">You have the URL and port number (usually 22) for the STFP host.</span></span>
- <span data-ttu-id="083cf-112">Сізде SFTP хостына импортталатын файлдың аты мен орналасқан орны бар.</span><span class="sxs-lookup"><span data-stu-id="083cf-112">You have the filename and location of the file to be imported on the SFTP host.</span></span>
- <span data-ttu-id="083cf-113">Импортталатын деректер схемасын көрсететін *model.json* файлы бар.</span><span class="sxs-lookup"><span data-stu-id="083cf-113">There's a *model.json* file that specifies the schema for the data that are to be imported.</span></span> <span data-ttu-id="083cf-114">Бұл файл импортталатын файл сияқты бірдей каталогта болуы тиіс.</span><span class="sxs-lookup"><span data-stu-id="083cf-114">This file must be in the same directory as the file to import.</span></span>
- <span data-ttu-id="083cf-115">Сізде [әкімші](permissions.md#administrator) рұқсаты бар.</span><span class="sxs-lookup"><span data-stu-id="083cf-115">You have [Administrator](permissions.md#administrator) permission.</span></span>

## <a name="configuration"></a><span data-ttu-id="083cf-116">Теңшелім</span><span class="sxs-lookup"><span data-stu-id="083cf-116">Configuration</span></span>

1. <span data-ttu-id="083cf-117">**Деректер** > **Арттыру** тармағына өтіп, **Анықтау** қойыншасын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="083cf-117">Go to **Data** > **Enrichment** and select the **Discover** tab.</span></span>

1. <span data-ttu-id="083cf-118">**SFTP реттелетін импорттау тақтасы** тақтасында **Менің деректерімді арттыру** пәрменін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="083cf-118">On the **SFTP custom import tile**, select **Enrich my data**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="083cf-119">![SFTP реттелетін импорттау тақтасы](media/SFTP_Custom_Import_tile.png "SFTP реттелетін импорттау тақтасы")</span><span class="sxs-lookup"><span data-stu-id="083cf-119">![SFTP Custom Import tile](media/SFTP_Custom_Import_tile.png "SFTP Custom Import tile")</span></span>

1. <span data-ttu-id="083cf-120">**Бастау** пәрменін таңдап, SFTP сервері үшін тіркелгі деректері мен мекенжайын ұсыныңыз.</span><span class="sxs-lookup"><span data-stu-id="083cf-120">Select **Get started** and provide the credentials and the address for the SFTP server.</span></span> <span data-ttu-id="083cf-121">Мысалы, sftp://mysftpserver.com:22.</span><span class="sxs-lookup"><span data-stu-id="083cf-121">For example, sftp://mysftpserver.com:22.</span></span>

1. <span data-ttu-id="083cf-122">Деректер бар файлдың атын және SFTP серверіндегі файл жолын, егер ол түбірлік қалтада болмаса, енгізіңіз.</span><span class="sxs-lookup"><span data-stu-id="083cf-122">Enter the name of the file that contains the data and path to the file on the SFTP server if it's not in the root folder.</span></span>

1. <span data-ttu-id="083cf-123">**Реттелетін импортқа қосылу** өрісін таңдау арқылы барлық кірістерді растаңыз.</span><span class="sxs-lookup"><span data-stu-id="083cf-123">Confirm all inputs by selecting **Connect to Custom Import**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="083cf-124">![SFTP реттелетін импорттау конфигурациясының қалқымалы мәзірі](media/SFTP_Custom_Import_Configuration_flyout.png "SFTP реттелетін импорттау конфигурациясының қалқымалы мәзірі")</span><span class="sxs-lookup"><span data-stu-id="083cf-124">![SFTP Custom Import Configuration flyout](media/SFTP_Custom_Import_Configuration_flyout.png "SFTP Custom Import Configuration flyout")</span></span>

## <a name="defining-field-mappings"></a><span data-ttu-id="083cf-125">Салыстырылатын өрісті анықтау</span><span class="sxs-lookup"><span data-stu-id="083cf-125">Defining field mappings</span></span> 

<span data-ttu-id="083cf-126">SFTP серверіне импортталатын файлды қамтитын каталогта *model.json* файлы болуы тиіс.</span><span class="sxs-lookup"><span data-stu-id="083cf-126">The directory that contains the file to be imported on the SFTP server must also contain a *model.json* file.</span></span> <span data-ttu-id="083cf-127">Бұл файл деректерді импорттауға арналған схеманы анықтайды.</span><span class="sxs-lookup"><span data-stu-id="083cf-127">This file defines the schema to use for importing the data.</span></span> <span data-ttu-id="083cf-128">Салыстырылатын өрісті көрсету үшін схема [Common Data Model](/common-data-model/) пайдалануы керек.</span><span class="sxs-lookup"><span data-stu-id="083cf-128">The schema has to use [the Common Data Model](/common-data-model/) to specify the field mapping.</span></span> <span data-ttu-id="083cf-129">Model.json файлының қарапайым мысалы келесідей:</span><span class="sxs-lookup"><span data-stu-id="083cf-129">A simple example of a model.json file looks like this:</span></span>

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

## <a name="enrichment-results"></a><span data-ttu-id="083cf-130">Толықтыру нәтижелері</span><span class="sxs-lookup"><span data-stu-id="083cf-130">Enrichment results</span></span>

<span data-ttu-id="083cf-131">Арттыру процесін бастау үшін пәрмендер жолағынан **Іске қосу** пәрменін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="083cf-131">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="083cf-132">Сондай-ақ, жүйеге [жоспарланған жаңарту](system.md#schedule-tab) бөлігі ретінде арттыруды автоматты түрде іске қосуына мүмкіндік беруге болады.</span><span class="sxs-lookup"><span data-stu-id="083cf-132">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="083cf-133">Өңдеу уақыты импортталатын деректердің көлеміне және SFTP серверіне қосылуға байланысты болады.</span><span class="sxs-lookup"><span data-stu-id="083cf-133">The processing time will depend on the size of the data to be imported and the connection to the SFTP server.</span></span>

<span data-ttu-id="083cf-134">Арттыру процесі аяқталғаннан кейін, **Менің арттыруларым** астындағы жаңа импортталған реттелетін арттыру деректерін қарап шығуға болады.</span><span class="sxs-lookup"><span data-stu-id="083cf-134">After the enrichment process completes, you can review your newly imported custom enrichment data under **My enrichments**.</span></span> <span data-ttu-id="083cf-135">Сонымен қатар, соңғы жаңартудың уақыты мен арттырылған профильдер санын таба аласыз.</span><span class="sxs-lookup"><span data-stu-id="083cf-135">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="083cf-136">**Толықтырылған деректерді көру** параметрін таңдау арқылы әрбір толықтырылған профильдің толық көрінісіне қатынаса аласыз.</span><span class="sxs-lookup"><span data-stu-id="083cf-136">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="083cf-137">Келесі қадамдар</span><span class="sxs-lookup"><span data-stu-id="083cf-137">Next steps</span></span>

<span data-ttu-id="083cf-138">Толықтырылған тұтынушы деректерінің негізінде жасаңыз.</span><span class="sxs-lookup"><span data-stu-id="083cf-138">Build on top of your enriched customer data.</span></span> <span data-ttu-id="083cf-139">Тұтынушыларға жеке тәжірибе беру үшін [сегменттер](segments.md), [шаралар](measures.md) жасаңыз және [деректерді экспорттаңыз](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="083cf-139">Create [segments](segments.md), [measures](measures.md), and [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>




[!INCLUDE[footer-include](../includes/footer-banner.md)]