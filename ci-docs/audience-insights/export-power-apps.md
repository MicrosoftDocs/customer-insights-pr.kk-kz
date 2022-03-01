---
title: Power Apps коннекторы
description: Power Apps және Power Automate арқылы қосылу.
ms.date: 08/21/2020
ms.reviewer: nikeller
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: b6ec103e29e218b2f27bfc1193300ea793a6b30b
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: kk-KZ
ms.lasthandoff: 11/03/2020
ms.locfileid: "4406208"
---
# <a name="microsoft-power-apps-connector-preview"></a>Microsoft Power Apps қосқышы (алдын ала қарау)

Power Apps бағдарламасымен бірыңғай тұтынушы профильдерін жекелендірілген бағдарламаларыңызға қосыңыз.

## <a name="connect-power-apps-and-dynamics-365-customer-insights"></a>Power Apps және Dynamics 365 Customer Insights бағдарламаларын қосу

Customer Insights көптеген [Power Apps бағдарламасында қолжетімді көздердің](https://docs.microsoft.com/powerapps/maker/canvas-apps/working-with-data-sources) бірі.

[Бағдарламаға деректер қосылымын қосу](https://docs.microsoft.com/powerapps/maker/canvas-apps/add-data-connection) жолы туралы ақпаратты Power Apps құжаттамасынан қараңыз. Сондай-ақ сізге [Power Apps кенеп бағдарламаларында үлкен деректер жиындарын өңдеу үшін өкілеттеуді пайдалану жолын](https://docs.microsoft.com/powerapps/maker/canvas-apps/delegation-overview) қарап шығуды ұсынамыз.

## <a name="available-entities"></a>Бар нысандар

Customer Insights деректер қосылымы ретінде қосқаннан кейін, келесі нысандарды Power Apps бағдарламасында таңдауға болады:

- Тұтынушы: [бірыңғай тұтынушы профилінің](customer-profiles.md) деректерін пайдалану.
- Бірыңғай тұтынушы әрекеті: бағдарламада [бірыңғай уақыт шкаласын](activities.md) көрсету.

## <a name="limitations"></a>Шектеулер

### <a name="retrievable-entities"></a>Шығарып алуға болатын нысандар

**Тұтынушы**, **Бірыңғай әрекет** және **Сегменттер** нысандарын тек Power Apps коннекторы арқылы шығарып ала аласыз. Басқа нысандар негізгі коннектор бұл нысандарды Power Automate ішіндегі триггерлер арқылы қолдайтындықтан көрсетіледі.  

### <a name="delegation"></a>Өкіл

Өкілеттеу «Тұтынушы» нысаны мен «Бірыңғай әрекет нысаны» үшін жұмыс істейді. 

- **Тұтынушы** нысанына арналған өкілеттік: осы нысан үшін өкілеттікті пайдалану үшін өрістерді [Іздеу және сүзгілеу индексі](search-filter-index.md) жүйесінде индекстеу керек.  

- **Бірыңғай әрекет** үшін өкілеттеу: бұл нысан үшін өкілеттеу тек **Әрекет идентификаторы** және **Тұтынушы идентификаторы** өрістері үшін жұмыс істейді.  

- Өкілеттеу туралы қосымша ақпаратты [Power Apps өкілеттеуге болатын функциялары мен әрекеттері](https://docs.microsoft.com/connectors/commondataservice/#power-apps-delegable-functions-and-operations-for-the-cds-for-apps) бөлімінен қараңыз. 

## <a name="example-gallery-control"></a>Галереяны басқару мысалы

Мысалы, тұтынушы профильдерін [галереяны басқару элементіне](https://docs.microsoft.com/powerapps/maker/canvas-apps/add-gallery) қосасыз.

1. Құрылатын бағдарламаға **Галерея** басқару құралын қосыңыз.

> [!div class="mx-imgBorder"]
> ![Галерея элементін қосу](media/connector-powerapps9.png "Галерея элементін қосу")

1. **Тұтынушы** параметрін элементтердің деректер көзі ретінде таңдаңыз.

    > [!div class="mx-imgBorder"]
    > ![Деректер көзін таңдау](media/choose-datasource-powerapps.png "Деректер көзін таңдау")

1. Галереяда көрсетілетін Тұтынушы нысаны өрісін таңдау үшін оң жақта деректер тақтасын өзгерте аласыз.

1. Галереяда таңдалған тұтынушыдан кез келген өрісті көрсету керек болса, белгінің мәтін сипатын толтырыңыз:  **{Name_of_the_gallery}.Selected.{property_name}**

    Мысалы: Gallery1.Selected.address1_city

1. Тұтынушының бірыңғай уақыт шкаласын көрсету үшін галерея элементін қосып, элементтер сипатын қосыңыз: **Filter('UnifiedActivity', CustomerId = {Customer_Id})**

    Мысалы: Filter('UnifiedActivity', CustomerId = Gallery1.Selected.CustomerId)
