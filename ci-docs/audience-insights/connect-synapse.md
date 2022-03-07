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
ms.openlocfilehash: 163bef897880f0497bf00e90fd095621a2d14378
ms.sourcegitcommit: 73cb021760516729e696c9a90731304d92e0e1ef
ms.translationtype: MT
ms.contentlocale: kk-KZ
ms.lasthandoff: 02/25/2022
ms.locfileid: "8356048"
---
# <a name="connect-an-azure-synapse-data-source-preview"></a>жалғаңыз Azure Synapse деректер көзі (алдын ала қарау)

Azure Synapse Analytics деректер қоймалары мен үлкен деректер жүйелері бойынша түсініктерге уақытты жылдамдататын кәсіпорынның аналитикалық қызметі. Azure Synapse Analytics кәсіпорын деректер қоймасында қолданылатын SQL технологияларының ең жақсысын, үлкен деректер үшін пайдаланылатын Spark технологияларын, журнал мен уақыт серияларын талдауға арналған Data Explorer бағдарламасын, деректерді біріктіру және ETL/ELT үшін құбыр желілерін және басқа Azure қызметтерімен терең интеграцияны біріктіреді.Power BI,Cosmos DB, және AzureML.

Қосымша ақпаратты қараңыз [Azure Synapse шолу](/azure/synapse-analytics/overview-what-is).

## <a name="prerequisites"></a>Алғышарттар

Customer Insights қосылымын Azure Synapse қызметінде конфигурациялау үшін келесі алғышарттар орындалуы керек.

> [!IMPORTANT]
> Барлық **рөл тағайындауларын** сипатталғандай орнатқаныңызға көз жеткізіңіз.  

## <a name="prerequisites-in-customer-insights"></a>Customer Insights қызметіндегі алғышарттар

* Сізде бар **Әкімші** Customer Insights жүйесіндегі рөл. [Аудитория түсініктеріндегі пайдаланушы рұқсаттары](permissions.md#assign-roles-and-permissions) туралы қосымша ақпарат.

Azure қызметінде: 

- Белсенді Azure жазылымы.

- Егер жаңа Azure Data Lake Storage Gen2 тіркелгісін пайдалансаңыз, the *аудитория туралы түсініктерге арналған қызмет негізі* **Сақтау екілік нысанының деректер салымшысы** рұқсаттарын қажет етеді. туралы көбірек біліңіз [-ге қосылу Azure Data Lake Storage аудитория туралы түсінік беру үшін қызмет көрсетушімен](connect-service-principal.md). Data Lake Storage Gen2 **қызметінде** [иерархиялық атаулар кеңістігі](/azure/storage/blobs/data-lake-storage-namespace) қосулы болуы керек.

- Ресурс тобында Azure Synapse жұмыс кеңістігі орналасқан, *қызмет негізі* және *аудитория туралы түсініктерге арналған пайдаланушыға* кем дегенде **Оқушы** рұқсаттары тағайындалуы керек. Қосымша ақпарат алу үшін [Azure порталын пайдалану арқылы Azure рөлдерін тағайындау](/azure/role-based-access-control/role-assignments-portal) бөлімін қараңыз.

- *Пайдаланушы* деректер орналасқан және Azure Synapse жұмыс кеңістігімен байланыстырылған Azure Data Lake Storage Gen2 тіркелгісінде **Сақтау екілік нысанының деректер салымшысы** рұқсаттарын қажет етеді. [Azure порталын екілік нысан және кезек тізімі деректеріне қатынасуға арналған Azure рөлін тағайындау үшін пайдалану](/azure/storage/common/storage-auth-aad-rbac-portal) және [Сақтау екілік нысанының деректер салымшысы рұқсаттары](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor) туралы қосымша ақпарат.

- *[Azure Synapse жұмыс кеңістігінің басқарылатын идентификациясы](/azure/synapse-analytics/security/synapse-workspace-managed-identity)* деректер орналасқан және Azure Synapse жұмыс кеңістігімен байланыстырылған Azure Data Lake Storage Gen2 тіркелгісінде **Сақтау екілік нысанының деректер салымшысы** рұқсаттарын қажет етеді. [Azure порталын екілік нысан және кезек тізімі деректеріне қатынасуға арналған Azure рөлін тағайындау үшін пайдалану](/azure/storage/common/storage-auth-aad-rbac-portal) және [Сақтау екілік нысанының деректер салымшысы рұқсаттары](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor) туралы қосымша ақпарат алыңыз.

- Azure Synapse жұмыс кеңістігінде *аудитория туралы түсініктерге арналған қызмет негізі* **Synapse әкімшісі** рөлінің тағайындалуын қажет етеді. Қосымша ақпарат алу үшін [Synapse жұмыс кеңістігі үшін қатынасуды басқару элементін орнату жолы](/azure/synapse-analytics/security/how-to-set-up-access-control) бөлімін қараңыз.

## <a name="connect-to-data-lake-databases-in-azure-synapse-analytics"></a>Деректер көлінің дерекқорларына қосылыңыз Azure Synapse Analytics

1. **Деректер** > **Дерек көздері** тармағы бойынша өтіңіз.

1. **Деректер көзін қосу** түймешігін таңдаңыз.

1. таңдаңыз **Azure Synapse Analytics (Алдын ала қарау)** әдіс.

1. Дерек көзі үшін **Атауы** өрісін толтырып, дерек көзін жасау үшін **Келесі** опциясын таңдаңыз. 

1. таңдаңыз [қолжетімді қосылым](connections.md) дейін Azure Synapse Analytics немесе жаңасын жасаңыз.

1. а таңдаңыз **Көл деректер базасы** таңдалғанда қосылған жұмыс кеңістігінен Azure Synapse Analytics қосылым және таңдаңыз **Келесі**.

1. Қосылған дерекқордан қабылдау үшін нысандарды таңдаңыз. 

1. Қосымша деректер профилін жасауға рұқсат беру үшін деректер нысандарын таңдаңыз. 

1. таңдаңыз **Сақтау** таңдауыңызды қолдану және жаңадан жасалған деректер көзі ішінен Лейк дерекқор кестелеріне байланыстырылған деректерді қабылдауды бастау үшін Azure Synapse Analytics.
