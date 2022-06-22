---
title: Өзіңізді пайдаланыңыз Azure Data Lake Storage Gen2 тіркелгісі
author: mukeshpo
description: Өзіңізді пайдалану талаптары туралы біліңіз Azure Data Lake Storage Customer Insights деректерін сақтауға арналған тіркелгі.
ms.author: mukeshpo
ms.date: 06/08/2022
ms.topic: conceptual
ms.manager: shellyha
ms.custom: intro-internal
ms.reviewer: mhart
ms.openlocfilehash: 5acb58906c1a9db54337f3b4dc2ab7891db7954e
ms.sourcegitcommit: 5e26cbb6d2258074471505af2da515818327cf2c
ms.translationtype: MT
ms.contentlocale: kk-KZ
ms.lasthandoff: 06/14/2022
ms.locfileid: "9011940"
---
# <a name="use-your-own-azure-data-lake-storage-gen2-account"></a>Өзіңізді пайдаланыңыз Azure Data Lake Storage Gen2 тіркелгісі

Dynamics 365 Customer Insights барлық деректеріңізді сақтау мүмкіндігін береді [Azure Data Lake Storage Gen2](/azure/storage/blobs/data-lake-storage-introduction).

Деректерді Data Lake Storage жүйесіне сақтау арқылы деректердің сол Azure сақтау тіркелгісі үшін сәйкес географиялық орынға тасымалданатынына және сақталатынына келісесіз. Қосымша ақпаратты қараңыз [Microsoft сенім орталығы](https://www.microsoft.com/trust-center).

Customer Insights жүйесіндегі әкімшілер мүмкін [орталарды құру](create-environment.md) және [деректерді сақтау опциясын көрсетіңіз](create-environment.md#step-2-configure-data-storage) процесінде.

## <a name="prerequisites-to-use-your-storage-account"></a>Жад тіркелгісін пайдаланудың алғышарттары

- Azure Data Lake Storage тіркелгілер Customer Insights ортасын жасау кезінде таңдаған бірдей Azure аймағында болуы керек. Customer Insights ортасының аймағын астында тексеруге болады **Админ** > **Жүйе** > **туралы**.
- Data Lake Storage Gen2 болуы керек және болуы керек [иерархиялық аттар кеңістігі қосылды](/azure/storage/blobs/create-data-lake-storage-account). Gen1 сақтау тіркелгілеріне қолдау көрсетілмейді.
- Контейнер аталды`customerinsights` сақтау тіркелгісінде болуы керек. Customer Insights қолданбасында жеке деректер көлінің қоймасын пайдаланбас бұрын оны жасау керек. Customer Insights ортасын орнататын әкімшіге сақтау тіркелгісінде немесе сақтау блогында деректердің Сақтау Blob қатысушысы немесе Storage Blob деректерінің иесі рөлі қажет.`customerinsights` контейнер. Сақтау тіркелгісінде рұқсатты тағайындау туралы қосымша ақпаратты қараңыз [Сақтау тіркелгісін жасаңыз](/azure/storage/common/storage-account-create?toc=%2Fazure%2Fstorage%2Fblobs%2Ftoc.json&tabs=azure-portal).

## <a name="connect-customer-insights-with-your-storage-account"></a>Customer Insights қолданбасын сақтау тіркелгісімен қосыңыз

Жаңа ортаны жасаған кезде, Data Lake Storage тіркелгісі бар екенін және барлық алғышарттардың орындалғанын тексеріңіз.

1. Ішінде **Деректерді сақтау** ортаны құру кезіндегі қадам, орнату **Шығару деректерін сақтаңыз** дейін **Azure Data Lake Storage Gen2**.
1. Қалай жасау керектігін таңдаңыз **Жадты қосыңыз**. Аутентификация үшін ресурсқа негізделген опция мен жазылымға негізделген опцияны таңдауға болады. Қосымша ақпаратты қараңыз [қосылыңыз Azure Data Lake Storage тіркелгісін Azure қызмет көрсетушісі арқылы пайдаланыңыз](connect-service-principal.md).
   - Үшін **Azure жазылымы**, таңдаңыз **Жазылым**, **тобы**, және **Сақтау тіркелгісі** құрамында`customerinsights` контейнер.
   - Үшін **Есептік жазба кілті**, қамтамасыз етіңіз **Төлем алушы** және **Есептік жазба кілті** Data Lake Storage тіркелгісі үшін. Бұл аутентификация әдісін пайдалану ұйымыңыз кілттерді айналдыратыны туралы хабардар екеніңізді білдіреді. Сен міндеттісің [орта конфигурациясын жаңартыңыз](manage-environments.md#edit-an-existing-environment) бұрылған кезде жаңа кілтпен.
1. Сақтау тіркелгісіне қосылу үшін Azure Private Link қолданбасын пайдаланғыңыз келе ме, жоқ па таңдаңыз [Жеке сілтемеге қосылым жасаңыз](security-overview.md#private-links-tab) екі сатылы процесспен.

Деректерді қабылдау сияқты жүйе процестері аяқталғанда, жүйе сақтау тіркелгісінде сәйкес қалталарды жасайды. Деректер файлдары мен *model.json* файлдары жасалады және процесс атауының негізінде қалталарға қосылады.

Егер сіз Customer Insights бірнеше ортасын жасасаңыз және сол орталардағы шығыс нысандарын сақтау тіркелгісінде сақтауды таңдасаңыз, Customer Insights бағдарламасы контейнерде әр орта үшін `ci_environmentID` параметрі бар бөлек қалталар жасайды.
