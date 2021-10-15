---
title: Нақтыланған оқиғаларды экспорттау
description: Нақтыланған оқиғалар мен негізгі оқиғаларды экспорттау жолы.
ms.reviewer: mhart
ms.author: jusali
author: jusali
ms.date: 04/30/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: faa0c3afb08d1c0282b2164ed914637ce9aad88117af37ba44fdb81e7610e574
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: kk-KZ
ms.lasthandoff: 08/10/2021
ms.locfileid: "7032392"
---
# <a name="export-events"></a>Оқиғаларды экспорттау

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Оқиға пайдаланушының әрекетін білдіреді. Ол пайдаланушының бетті қарау (қарау оқиғасы) немесе мазмұнмен өзара әрекеттесу (әрекет оқиғасы) уақытын жазады. Есепте деректердің қандай сипаттарын көрсеткіңіз келетіндігін шешкен кезде деректердің бұл виртуалды көрінісі *нақтыланған оқиға* деп аталады. 

- Оқиғалар мен нақтыланған оқиғаларды сыртқы сақтау орнына экспорттауға болады. 
- Экспорттар — тікелей ақпарат ағыны. Ағынды қайта толтыру мүмкін емес. 
- Экспортта тұрақты схемалар бар. Егер оқиғаға реттелетін сипаттарды қоссаңыз, олар қамтылмайды. Жаңа экспорт жасау қажет.

## <a name="prerequisites"></a>Алғышарттар

Экспортты орнатпас бұрын, сізде Azure порталына қолжетімділік және белсенді жазылым болуы қажет. Экспорттау процесі кезінде сізге сақтау орны тіркелгісі туралы ақпарат қажет болады. 

### <a name="create-an-azure-data-lake-storage-gen-2-accounts"></a>Azure Data Lake Storage Gen 2 тіркелгілерін жасау

1. Azure порталына кіріп, [жаңа сақтау орны тіркелгісін жасаңыз](/azure/storage/common/storage-account-create). 

1. **Кеңейтілген** қойыншасында **Иерархиялық атаулар кеңістігі** параметрін қосыңыз. 

   :::image type="content" source="media/enable-hierarchical-namespace.png" alt-text="Кеңейтілген қойыншасында иерархиялық атаулар кеңістігі параметрін қосу.":::

1. Ол орналастырылғаннан кейін, жаңадан жасалған сақтау орын тіркелгісіне өтіңіз. Навигация тақтасында **Параметрлер** > **Қолжетімділік кілттері** опцияларын таңдаңыз. 

1. Жаңа экспорт жасау кезінде пайдаланылатын **Тіркелгі атауы** және **Кілт** параметрлерін көшіріңіз.
   :::image type="content" source="media/storage-account-access-keys.png" alt-text="Сақтау орны тіркелгісіндегі қолжетімділік кілттері.":::

## <a name="export-events"></a>Оқиғаларды экспорттау

Оқиғаларды экспорттаудың екі жолы бар: 
- **Деректер** > **Экспорттаулар** және **Жаңа экспорт** опцияларын таңдаңыз.
- **Деректер** > **Оқиғалар** тармағына өтіңіз, экспорттау керек оқиға жанындағы **Қосымша [...]** түймешігін таңдаңыз және ашылмалы мәзірден **Экспорттау** түймешігін таңдаңыз. 

Экспортты жасау бойынша қадамдарды басшылыққа аласыз:

1. **Экспорттау атауы** параметрін енгізіңіз.

1. **Оқиғаларды таңдау** ашылмалы тізімінде экспорттауды қосу үшін негізгі оқиғалар мен нақтыланған оқиғаларды таңдаңыз. 

1. **Файл құрылымы** бөлімінде межелі сақтау орнында жаңа файлдар жасау үшін каденция таңдаңыз. Оқиғалар келген кезде үздіксіз экспортталады.

1. Экспорттауға арналған пішімді таңдаңыз. **Common Data Model**, **CSV** және **JSON** пішімдері арасында таңдауға болады. Экспортты басқа Dynamics 365 бағдарламаларымен пайдалану үшін Common Data Model пішімін пайдалануға кеңес береміз.

1. **Межелі орынды таңдау** қадамында Azure Data Lake Storage Gen 2 орналасу орнын көрсетіңіз.
    1. **ADLS Gen 2 тіркелгі атауы** – экспортты сақтағыңыз келетін сақтау орны тіркелгісінің атауы. 
    1. **Қалта жолы** файлдың жүйесінде және сақтау орны тіркелгісінің каталогтік құрылымында экспорттың сақталу орнын анықтайды.
    1. **Ортақ кілт** сақтау орны тіркелгісі үшін Azure порталынан қолжетімді.

1. Таңдауларды қарап шығып, растаңыз.

## <a name="view-and-manage-exports"></a>Экспорттауларды көру және басқару

Экспортты орнатқаннан кейін оларды көру үшін **Деректер** > **Экспорттар** сілтемесіне өтіңіз. Өңдеу немесе жою үшін бұрыннан бар экспорт бойынша **Қосымша [...]** опциясын таңдаңыз.


[!INCLUDE[footer-include](../includes/footer-banner.md)]