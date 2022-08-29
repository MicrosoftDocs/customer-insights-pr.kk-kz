---
title: Өзіңізді пайдаланыңыз Azure Data Lake Storage Gen2 тіркелгісі
author: mukeshpo
description: Өзіңізді пайдалану талаптары туралы біліңіз Azure Data Lake Storage Customer Insights деректерін сақтауға арналған тіркелгі.
ms.author: mukeshpo
ms.date: 08/15/2022
ms.topic: conceptual
ms.manager: shellyha
ms.custom: intro-internal
ms.reviewer: mhart
ms.openlocfilehash: 5e4b9348f06d4e5e10b4499ad86b38c9d52da1f5
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: MT
ms.contentlocale: kk-KZ
ms.lasthandoff: 08/16/2022
ms.locfileid: "9304388"
---
# <a name="use-your-own-azure-data-lake-storage-gen2-account"></a>Өзіңізді пайдаланыңыз Azure Data Lake Storage Gen2 тіркелгісі

Dynamics 365 Customer Insights барлық деректеріңізді сақтау мүмкіндігін береді [Azure Data Lake Storage Gen2](/azure/storage/blobs/data-lake-storage-introduction). Деректерді Data Lake Storage жүйесіне сақтау арқылы деректердің сол Azure сақтау тіркелгісі үшін сәйкес географиялық орынға тасымалданатынына және сақталатынына келісесіз. Қосымша ақпаратты қараңыз [Microsoft сенім орталығы](https://www.microsoft.com/trust-center).

Customer Insights жүйесіндегі әкімшілер мүмкін [орталар құру](create-environment.md) және [деректерді сақтау опциясын көрсетіңіз](create-environment.md#step-2-configure-data-storage) процесінде.

## <a name="prerequisites"></a>Алғышарттар

- Azure Data Lake Storage тіркелгілер Customer Insights ортасын жасау кезінде таңдаған бірдей Azure аймағында болуы керек. Қоршаған ортаның аймағын білу үшін мына жерге өтіңіз **Админ** > **Жүйе** > **туралы** Customer Insights ішінде.
- Data Lake Storage тіркелгісі Gen2 болуы керек. Azure Data Lake Gen1 сақтау тіркелгілеріне қолдау көрсетілмейді.
- Data Lake Storage тіркелгісі болуы керек [иерархиялық аттар кеңістігі қосылды](/azure/storage/blobs/data-lake-storage-namespace).
- Контейнер аталды`customerinsights` сақтау тіркелгісінде болуы керек. Customer Insights қолданбасында жеке деректер көлінің қоймасын пайдаланбас бұрын оны жасаңыз.
- Customer Insights ортасын орнататын әкімшіге сақтау тіркелгісінде немесе сақтау блогында деректердің Сақтау Blob қатысушысы немесе Storage Blob деректерінің иесі рөлі қажет.`customerinsights` контейнер. Сақтау тіркелгісінде рұқсатты тағайындау туралы қосымша ақпаратты қараңыз [Сақтау есептік жазбасын жасаңыз](/azure/storage/common/storage-account-create?toc=%2Fazure%2Fstorage%2Fblobs%2Ftoc.json&tabs=azure-portal).

## <a name="connect-customer-insights-with-your-storage-account"></a>Customer Insights қолданбасын сақтау тіркелгісімен қосыңыз

Жаңа ортаны жасаған кезде, Data Lake Storage тіркелгісі бар екенін және барлық алғышарттардың орындалғанын тексеріңіз.

1. Ішінде **Деректерді сақтау** ортаны құру кезіндегі қадам, орнату **Шығару деректерін сақтаңыз** дейін **Azure Data Lake Storage Gen2**.
1. Қалай жасау керектігін таңдаңыз **Жадты қосыңыз**. Аутентификация үшін ресурсқа негізделген опция мен жазылымға негізделген опцияны таңдауға болады. Қосымша ақпаратты қараңыз [қосылыңыз Azure Data Lake Storage тіркелгіні Azure қызмет көрсетушісі арқылы пайдаланыңыз](connect-service-principal.md).
   - Үшін **Azure жазылымы**, таңдаңыз **Жазылым**, **тобы**, және **Сақтау тіркелгісі** құрамында`customerinsights` контейнер.
   - Үшін **Есептік жазба кілті**, қамтамасыз етіңіз **Төлем алушы** және **Есептік жазба кілті** Data Lake Storage тіркелгісі үшін. Бұл аутентификация әдісін пайдалану ұйымыңыз кілттерді айналдыратыны туралы хабардар екеніңізді білдіреді. Сен міндеттісің [орта конфигурациясын жаңартыңыз](manage-environments.md#edit-an-existing-environment) бұрылған кезде жаңа кілтпен.
1. Жад тіркелгісіне қосылу үшін Azure Private Link қолданбасын пайдаланғыңыз келе ме, жоқ па таңдаңыз [Жеке сілтемеге қосылым жасаңыз](security-overview.md#set-up-an-azure-private-link).

Деректерді қабылдау сияқты жүйе процестері аяқталғанда, жүйе сақтау тіркелгісінде сәйкес қалталарды жасайды. Деректер файлдары мен model.json файлдары процесс атауының негізінде құрылады және қалталарға қосылады.

Егер сіз Customer Insights бірнеше ортасын жасасаңыз және сол орталардағы шығыс нысандарын сақтау тіркелгісінде сақтауды таңдасаңыз, Customer Insights бағдарламасы контейнерде әр орта үшін `ci_environmentID` параметрі бар бөлек қалталар жасайды.
