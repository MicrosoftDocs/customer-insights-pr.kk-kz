---
title: жалғаңыз Azure Synapse деректер көзі (алдын ала қарау)
description: ішінде дерекқорды пайдаланыңыз Azure Synapse ішінде деректер көзі ретінде Dynamics 365 Customer Insights.
ms.date: 03/25/2022
ms.reviewer: v-wendysmith
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
ms.openlocfilehash: c4ae65613a02df38a30f907dae72d413bf1a702f
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: MT
ms.contentlocale: kk-KZ
ms.lasthandoff: 06/29/2022
ms.locfileid: "9052706"
---
# <a name="connect-an-azure-synapse-analytics-data-source-preview"></a>жалғаңыз Azure Synapse Analytics деректер көзі (алдын ала қарау)

Azure Synapse Analytics деректер қоймалары мен үлкен деректер жүйелері бойынша түсініктерге уақытты жылдамдататын кәсіпорынның аналитикалық қызметі. Azure Synapse Analytics кәсіпорын деректер қоймасында қолданылатын SQL технологияларының ең жақсысын, үлкен деректер үшін пайдаланылатын Spark технологияларын, журнал мен уақыт қатарын талдауға арналған Data Explorer бағдарламасын, деректерді біріктіру және ETL/ELT үшін құбыр желілерін және басқа Azure қызметтерімен терең интеграцияны біріктіреді.Power BI,Cosmos DB, және AzureML.

Қосымша ақпарат алу үшін қараңыз [Azure Synapse шолу](/azure/synapse-analytics/overview-what-is).

## <a name="prerequisites"></a>Алғышарттар

> [!IMPORTANT]
> Барлық **рөл тағайындауларын** сипатталғандай орнатқаныңызға көз жеткізіңіз.  

**Customer Insights бөлімінде**:

* Сізде бар **Әкімші** Customer Insights жүйесіндегі рөл. туралы көбірек біліңіз [Customer Insights ішіндегі пайдаланушы рұқсаттары](permissions.md#assign-roles-and-permissions).

**Azure ішінде**:

- Белсенді Azure жазылымы.

- Жаңасын пайдалансаңыз Azure Data Lake Storage Gen2 тіркелгісі, *Customer Insights үшін қызмет көрсетуші* қажеттіліктер **Сақтау Blob деректерінің қатысушысы** рұқсаттар. туралы көбірек біліңіз [-ге қосылу Azure Data Lake Storage Customer Insights үшін қызмет көрсетушімен](connect-service-principal.md). Data Lake Storage Gen2 **қызметінде** [иерархиялық атаулар кеңістігі](/azure/storage/blobs/data-lake-storage-namespace) қосулы болуы керек.

- Ресурстар тобында Azure Synapse жұмыс кеңістігі орналасқан, *қызмет көрсетуші* және *Customer Insights пайдаланушысы* кем дегенде тағайындау керек **Оқырман** рұқсаттар. Қосымша ақпарат алу үшін [Azure порталын пайдалану арқылы Azure рөлдерін тағайындау](/azure/role-based-access-control/role-assignments-portal) бөлімін қараңыз.

- *Пайдаланушы* деректер орналасқан және Azure Synapse жұмыс кеңістігімен байланыстырылған Azure Data Lake Storage Gen2 тіркелгісінде **Сақтау екілік нысанының деректер салымшысы** рұқсаттарын қажет етеді. [Azure порталын екілік нысан және кезек тізімі деректеріне қатынасуға арналған Azure рөлін тағайындау үшін пайдалану](/azure/storage/common/storage-auth-aad-rbac-portal) және [Сақтау екілік нысанының деректер салымшысы рұқсаттары](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor) туралы қосымша ақпарат.

- *[Azure Synapse жұмыс кеңістігінің басқарылатын идентификациясы](/azure/synapse-analytics/security/synapse-workspace-managed-identity)* деректер орналасқан және Azure Synapse жұмыс кеңістігімен байланыстырылған Azure Data Lake Storage Gen2 тіркелгісінде **Сақтау екілік нысанының деректер салымшысы** рұқсаттарын қажет етеді. [Azure порталын екілік нысан және кезек тізімі деректеріне қатынасуға арналған Azure рөлін тағайындау үшін пайдалану](/azure/storage/common/storage-auth-aad-rbac-portal) және [Сақтау екілік нысанының деректер салымшысы рұқсаттары](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor) туралы қосымша ақпарат алыңыз.

- Үстінде Azure Synapse жұмыс кеңістігі, *Customer Insights үшін қызмет көрсетуші* қажеттіліктер **Synapse әкімшісі** рөл тағайындалды. Қосымша ақпарат алу үшін [Synapse жұмыс кеңістігі үшін қатынасуды басқару элементін орнату жолы](/azure/synapse-analytics/security/how-to-set-up-access-control) бөлімін қараңыз.

## <a name="connect-to-the-data-lake-database-in-azure-synapse-analytics"></a>Data Lake дерекқорына қосылыңыз Azure Synapse Analytics

1. **Деректер** > **Дерек көздері** тармағы бойынша өтіңіз.

1. **Деректер көзін қосу** түймешігін таңдаңыз.

1. таңдаңыз **Azure Synapse Analytics (Алдын ала қарау)** әдіс.

   :::image type="content" source="media/data_sources_synapse.png" alt-text="Synapse Analytics деректеріне қосылу үшін диалогтық терезе":::
  
1. А енгізіңіз **Аты** деректер көзі және қосымша үшін **Сипаттама**.

1. таңдаңыз [қолжетімді қосылым](connections.md) дейін Azure Synapse Analytics немесе жаңасын жасаңыз.

1. а таңдаңыз **Дерекқор** таңдалғанда қосылған жұмыс кеңістігінен Azure Synapse Analytics қосылым және таңдаңыз **Келесі**. Қазіргі уақытта біз тек дерекқор түрін қолдаймыз *Көл деректері*.

1. Қосылған дерекқордан қабылданатын нысандарды таңдап, таңдаңыз **Келесі**.

1. Қосымша деректер профилін жасауға рұқсат беру үшін деректер нысандарын таңдаңыз.

1. таңдаңыз **Сақтау** таңдауыңызды қолдану және жаңадан жасалған деректер көзі ішінен Лейк дерекқор кестелеріне байланыстырылған деректерді қабылдауды бастау үшін Azure Synapse Analytics. The **Деректер көздері** жаңа деректер көзі көрсететін бет ашылады **Сергіту** күй.
