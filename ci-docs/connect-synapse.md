---
title: Деректерді қабылдау Azure Synapse Analytics
description: Деректер базасын пайдаланыңыз Azure Synapse ішінде деректер көзі ретінде Dynamics 365 Customer Insights.
ms.date: 02/24/2022
ms.reviewer: v-wendysmith
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
ms.openlocfilehash: 7c758dccf7ea34dd7b8f80d05eff1ed12030526f
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: MT
ms.contentlocale: kk-KZ
ms.lasthandoff: 04/27/2022
ms.locfileid: "8643347"
---
# <a name="connect-an-azure-synapse-data-source-preview"></a>жалғаңыз Azure Synapse деректер көзі (алдын ала қарау)

Azure Synapse Analytics деректер қоймалары мен үлкен деректер жүйелері бойынша түсініктерге уақытты жылдамдататын кәсіпорынның аналитикалық қызметі. Azure Synapse Analytics кәсіпорын деректер қоймасында қолданылатын SQL технологияларының ең жақсысын, үлкен деректер үшін пайдаланылатын Spark технологияларын, журнал мен уақыт серияларын талдауға арналған Data Explorer бағдарламасын, деректерді біріктіру және ETL/ELT үшін құбыр желілерін және басқа Azure қызметтерімен терең интеграцияны біріктіреді.Power BI,Cosmos DB, және AzureML.

Қосымша ақпаратты қараңыз [Azure Synapse шолу](/azure/synapse-analytics/overview-what-is).

## <a name="prerequisites"></a>Алғышарттар

Қосылымды конфигурациялау үшін келесі алғышарттар орындалуы керек Dynamics 365 Customer Insights дейін Azure Synapse.

> [!IMPORTANT]
> Барлық **рөл тағайындауларын** сипатталғандай орнатқаныңызға көз жеткізіңіз.  

## <a name="prerequisites-in-customer-insights"></a>Customer Insights қызметіндегі алғышарттар

* Сізде бар **Әкімші** Customer Insights жүйесіндегі рөл. туралы көбірек біліңіз [Customer Insights ішіндегі пайдаланушы рұқсаттары](permissions.md#assign-roles-and-permissions).

Azure қызметінде: 

- Белсенді Azure жазылымы.

- Жаңасын пайдалансаңыз Azure Data Lake Storage Gen2 тіркелгісі, *Customer Insights үшін қызмет көрсетуші* қажеттіліктер **Сақтау Blob деректерінің қатысушысы** рұқсаттар. туралы көбірек біліңіз [-ге қосылу Azure Data Lake Storage Customer Insights үшін қызмет көрсетушімен](connect-service-principal.md). Data Lake Storage Gen2 **қызметінде** [иерархиялық атаулар кеңістігі](/azure/storage/blobs/data-lake-storage-namespace) қосулы болуы керек.

- Ресурстар тобында Azure Synapse жұмыс кеңістігі орналасқан, *қызмет көрсетуші* және *Customer Insights пайдаланушысы* кем дегенде тағайындау керек **Оқырман** рұқсаттар. Қосымша ақпарат алу үшін [Azure порталын пайдалану арқылы Azure рөлдерін тағайындау](/azure/role-based-access-control/role-assignments-portal) бөлімін қараңыз.

- *Пайдаланушы* деректер орналасқан және Azure Synapse жұмыс кеңістігімен байланыстырылған Azure Data Lake Storage Gen2 тіркелгісінде **Сақтау екілік нысанының деректер салымшысы** рұқсаттарын қажет етеді. [Azure порталын екілік нысан және кезек тізімі деректеріне қатынасуға арналған Azure рөлін тағайындау үшін пайдалану](/azure/storage/common/storage-auth-aad-rbac-portal) және [Сақтау екілік нысанының деректер салымшысы рұқсаттары](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor) туралы қосымша ақпарат.

- *[Azure Synapse жұмыс кеңістігінің басқарылатын идентификациясы](/azure/synapse-analytics/security/synapse-workspace-managed-identity)* деректер орналасқан және Azure Synapse жұмыс кеңістігімен байланыстырылған Azure Data Lake Storage Gen2 тіркелгісінде **Сақтау екілік нысанының деректер салымшысы** рұқсаттарын қажет етеді. [Azure порталын екілік нысан және кезек тізімі деректеріне қатынасуға арналған Azure рөлін тағайындау үшін пайдалану](/azure/storage/common/storage-auth-aad-rbac-portal) және [Сақтау екілік нысанының деректер салымшысы рұқсаттары](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor) туралы қосымша ақпарат алыңыз.

- Үстінде Azure Synapse жұмыс кеңістігі, *Customer Insights үшін қызмет көрсетуші* қажеттіліктер **Synapse әкімшісі** рөл тағайындалды. Қосымша ақпарат алу үшін [Synapse жұмыс кеңістігі үшін қатынасуды басқару элементін орнату жолы](/azure/synapse-analytics/security/how-to-set-up-access-control) бөлімін қараңыз.

## <a name="connect-to-data-lake-databases-in-azure-synapse-analytics"></a>Деректер көлінің дерекқорларына қосылыңыз Azure Synapse Analytics

1. **Деректер** > **Дерек көздері** тармағы бойынша өтіңіз.

1. **Деректер көзін қосу** түймешігін таңдаңыз.

1. таңдаңыз **Azure Synapse Analytics (Алдын ала қарау)** әдіс.

1. Дерек көзі үшін **Атауы** өрісін толтырып, дерек көзін жасау үшін **Келесі** опциясын таңдаңыз. 

1. таңдаңыз [қолжетімді қосылым](connections.md) дейін Azure Synapse Analytics немесе жаңасын жасаңыз.

1. а таңдаңыз **Көл деректер базасы** таңдалғанда қосылған жұмыс кеңістігінен Azure Synapse Analytics қосылым және таңдаңыз **Келесі**.

1. Қосылған дерекқордан қабылдау үшін нысандарды таңдаңыз. 

1. Қосымша деректер профилін жасауға рұқсат беру үшін деректер нысандарын таңдаңыз. 

1. таңдаңыз **Сақтау** таңдауыңызды қолдану және жаңадан жасалған деректер көзі ішінен Лейк дерекқор кестелерімен байланыстырылған деректерді қабылдауды бастау үшін Azure Synapse Analytics.
