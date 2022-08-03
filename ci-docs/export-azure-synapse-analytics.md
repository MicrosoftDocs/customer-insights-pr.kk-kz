---
title: Деректерді экспорттау Azure Synapse Analytics (алдын ала қарау)
description: Қосылымды конфигурациялауды үйреніңіз Azure Synapse Analytics.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: f9c9ee55f2874ae1dcaf82f2ff17ed0fbbb7804d
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: kk-KZ
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196401"
---
# <a name="export-data-to-azure-synapse-analytics-preview"></a>Деректерді экспорттау Azure Synapse Analytics (алдын ала қарау)

Azure Synapse — бұл деректер қоймалары мен үлкен деректер жүйелері бойынша талдау уақытын жеделдететін аналитикалық қызмет. Customer Insights деректерін [Azure Synapse](/azure/synapse-analytics/overview-what-is) қызметінен алуға және пайдалануға болады.

## <a name="prerequisites"></a>Алғышарттар

> [!NOTE]
> Барлық **рөл тағайындауларын** сипатталғандай орнатқаныңызға көз жеткізіңіз.

- Customer Insights қолданбасында сіздің Azure Active Directory (AD) пайдаланушы тіркелгісінде болуы керек [Әкімші рөлі](permissions.md#assign-roles-and-permissions).

Azure қызметінде:

- Белсенді Azure жазылымы.

- Жаңасын пайдалансаңыз Azure Data Lake Storage Gen2 тіркелгісі, [Customer Insights үшін қызмет көрсетуші](connect-service-principal.md) бар **Сақтау Blob деректерінің қатысушысы** рұқсаттар. Data Lake Storage Gen2 **қызметінде** [иерархиялық атаулар кеңістігі](/azure/storage/blobs/data-lake-storage-namespace) қосулы болуы керек.

- Ресурстар тобында Azure Synapse жұмыс кеңістігі орналасқан, *қызмет көрсетуші* және *Azure AD Customer Insights жүйесінде әкімші рұқсаттары бар пайдаланушы* кем дегенде тағайындалуы керек **Оқырман**[рұқсаттар](/azure/role-based-access-control/role-assignments-portal).

- The *Azure AD Customer Insights жүйесінде әкімші рұқсаттары бар пайдаланушы* бар **Сақтау Blob деректерінің қатысушысы** бойынша рұқсаттар Azure Data Lake Storage Деректер орналасқан және байланыстырылған Gen2 тіркелгісі Azure Synapse жұмыс кеңістігі. [Azure порталын екілік нысан және кезек тізімі деректеріне қатынасуға арналған Azure рөлін тағайындау үшін пайдалану](/azure/storage/common/storage-auth-aad-rbac-portal) және [Сақтау екілік нысанының деректер салымшысы рұқсаттары](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor) туралы қосымша ақпарат.

- The *[Azure Synapse жұмыс кеңістігі басқарылатын сәйкестік](/azure/synapse-analytics/security/synapse-workspace-managed-identity)* бар **Сақтау Blob деректерінің қатысушысы** бойынша рұқсаттар Azure Data Lake Storage Деректер орналасқан және байланыстырылған Gen2 тіркелгісі Azure Synapse жұмыс кеңістігі. [Azure порталын екілік нысан және кезек тізімі деректеріне қатынасуға арналған Azure рөлін тағайындау үшін пайдалану](/azure/storage/common/storage-auth-aad-rbac-portal) және [Сақтау екілік нысанының деректер салымшысы рұқсаттары](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor) туралы қосымша ақпарат алыңыз.

- Үстінде Azure Synapse жұмыс кеңістігі, *Customer Insights үшін қызмет көрсетуші* бар **Synapse әкімшісі**[рөл тағайындалды](/azure/synapse-analytics/security/how-to-set-up-access-control).

## <a name="set-up-connection-to-azure-synapse"></a>Қосылымды орнату Azure Synapse

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. **Әкімші** > **Қосылымдар** тармағына өтіңіз.

1. таңдаңыз **Қосылым қосыңыз** және таңдаңыз **Azure Synapse Analytics**.

1. **Көрсетілетін аты** өрісінде қосылымға оңай танылатын атау енгізіңіз. Қосылым атауы мен түрі осы қосылымды сипаттайды. Қосылымның мақсатын түсіндіретін атауды таңдауды ұсынамыз.

1. Осы қосылымды кім пайдалана алатынын таңдаңыз. Әдепкі бойынша бұл тек әкімшілер. Қосымша ақпарат алу үшін [Салымшыларға экспорттау үшін қосылымды пайдалануға рұқсат беру](connections.md#allow-contributors-to-use-a-connection-for-exports) бөлімін қараңыз.

1. Customer Insights деректерін пайдалану керек жазылымды таңдаңыз немесе іздеңіз. Жазылымды таңдағаннан кейін **Жұмыс кеңістігі**, **Сақтау тіркелгісі** және **Контейнер** параметрлерін таңдауға болады.

1. шолу [деректердің құпиялылығы және сәйкестігі](connections.md#data-privacy-and-compliance) және таңдаңыз **Мен келісемін**.

1. Қосылымды аяқтау үшін **Сақтау** түймешігін таңдаңыз.

## <a name="configure-an-export"></a>Экспорттауды конфигурациялау

[!INCLUDE [export-permission-include](includes/export-permission.md)] Ортақ қосылыммен экспорттауды конфигурациялау үшін сізге кем дегенде қажет **Қатысушы** Customer Insights ішіндегі рұқсаттар.

1. **Деректер** > **Экспорттау** тармағына өтіңіз.

1. таңдаңыз **Экспортты қосыңыз**.

1. Ішінде **Экспортқа арналған қосылым** өрісінен қосылымды таңдаңыз Azure Synapse Analytics бөлім. Егер қосылым болмаса, әкімшіге хабарласыңыз.

1. Экспорттау және **Дерекқор атауы** үшін танылатын **Көрсетілетін атау** беріңіз. Экспорт жаңасын жасайды [Azure Synapse көл деректер базасы](/azure/synapse-analytics/database-designer/concepts-lake-database) қосылымда анықталған жұмыс кеңістігінде.

1. Қай нысандарға экспорттағыңыз келетінін таңдаңыз Azure Synapse Analytics.
   > [!NOTE]
   > [Common Data Model қалтасына](connect-common-data-model.md) негізделген деректер көздеріне қолдау көрсетілмейді.

1. **Сақтау** пәрменін таңдаңыз.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

Synapse Analytics қызметіне экспортталған деректерді сұрау үшін сізге қажет **Blob деректерін оқу құралы** экспорттың жұмыс кеңістігіндегі тағайындалған қоймаға қол жеткізу.

## <a name="update-an-export"></a>Экспорттауды жаңарту

1. **Деректер** > **Экспорттау** тармағына өтіңіз.

1. Жаңарту керек экспорттауда **Өңдеу** түймешігін таңдаңыз.

   - Таңдаудан нысандарды **қосыңыз** немесе **жойыңыз**. Егер нысандар таңдаудан алынып тасталса, олар Synapse Analytics дерекқорынан жойылмайды. Алайда болашақ деректерді жаңарту сол дерекқордағы жойылған нысандарды жаңартпайды.

   - **Дерекқордың атауын өзгерту** опциясы жаңа Synapse Analytics дерекқорын жасайды. Бұрын конфигурацияланған атауы бар дерекқор болашақта жаңартулар алмайды.

[!INCLUDE [footer-include](includes/footer-banner.md)]
