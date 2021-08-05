---
title: Power Apps коннекторы
description: Power Apps және Power Automate арқылы қосылу.
ms.date: 01/19/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: Nils-2m
ms.author: nikeller
manager: shellyha
ms.openlocfilehash: 2ab5a9059991611a2959a19cc688d232ec782e1e
ms.sourcegitcommit: dab2cbf818fafc9436e685376df94c5e44e4b144
ms.translationtype: HT
ms.contentlocale: kk-KZ
ms.lasthandoff: 07/13/2021
ms.locfileid: "6554120"
---
# <a name="microsoft-power-apps-connector-preview"></a>Microsoft Power Apps қосқышы (алдын ала қарау)

Power Apps бағдарламасымен бірыңғай тұтынушы профильдерін жекелендірілген бағдарламаларыңызға қосыңыз.

## <a name="connect-power-apps-and-dynamics-365-customer-insights"></a>Power Apps және Dynamics 365 Customer Insights бағдарламаларын қосу

Customer Insights көптеген [Power Apps бағдарламасында қолжетімді көздердің](/powerapps/maker/canvas-apps/working-with-data-sources) бірі.

[Бағдарламаға деректер қосылымын қосу](/powerapps/maker/canvas-apps/add-data-connection) жолы туралы ақпаратты Power Apps құжаттамасынан қараңыз. Сондай-ақ сізге [Power Apps кенеп бағдарламаларында үлкен деректер жиындарын өңдеу үшін өкілеттеуді пайдалану жолын](/powerapps/maker/canvas-apps/delegation-overview) қарап шығуды ұсынамыз.

## <a name="available-entities"></a>Бар нысандар

Customer Insights деректер қосылымы ретінде қосқаннан кейін, келесі нысандарды Power Apps бағдарламасында таңдауға болады:

- Тұтынушы: [бірыңғай тұтынушы профилінің](customer-profiles.md) деректерін пайдалану.
- Бірыңғай әрекет: бағдарламада [әрекеттің уақыт шкаласын](activities.md) көрсету.

## <a name="limitations"></a>Шектеулер

### <a name="retrievable-entities"></a>Шығарып алуға болатын нысандар

**Тұтынушы**, **Бірыңғай әрекет** және **Сегменттер** нысандарын тек Power Apps коннекторы арқылы шығарып ала аласыз. Басқа нысандар негізгі коннектор бұл нысандарды Power Automate ішіндегі триггерлер арқылы қолдайтындықтан көрсетіледі.  

### <a name="delegation"></a>Өкіл

Өкілеттеу «Тұтынушы» нысаны мен «Бірыңғай әрекет нысаны» үшін жұмыс істейді. 

- **Тұтынушы** нысанына арналған өкілеттік: осы нысан үшін өкілеттікті пайдалану үшін өрістерді [Іздеу және сүзгілеу индексі](search-filter-index.md) жүйесінде индекстеу керек.  

- **Бірыңғай әрекет** үшін өкілеттеу: бұл нысан үшін өкілеттеу тек **Әрекет идентификаторы** және **Тұтынушы идентификаторы** өрістері үшін жұмыс істейді.  

- Өкілеттеу туралы қосымша ақпаратты [Power Apps өкілеттеуге болатын функциялары мен әрекеттері](/connectors/commondataservice/#power-apps-delegable-functions-and-operations-for-the-cds-for-apps) бөлімінен қараңыз. 

## <a name="example-gallery-control"></a>Галереяны басқару мысалы

Мысалы, тұтынушы профильдерін [галереяны басқару элементіне](/powerapps/maker/canvas-apps/add-gallery) қосасыз.

1. Құрылатын бағдарламаға **Галерея** басқару құралын қосыңыз.

> [!div class="mx-imgBorder"]
> ![Галерея элементін қосыңыз.](media/connector-powerapps9.png "Галерея элементін қосу")

1. **Тұтынушы** параметрін элементтердің деректер көзі ретінде таңдаңыз.

    > [!div class="mx-imgBorder"]
    > ![Деректер көзін таңдаңыз.](media/choose-datasource-powerapps.png "Деректер көзін таңдау")

1. Галереяда көрсетілетін Тұтынушы нысаны өрісін таңдау үшін оң жақта деректер тақтасын өзгерте аласыз.

1. Галереяда таңдалған тұтынушыдан кез келген өрісті көрсету керек болса, белгінің мәтін сипатын толтырыңыз:  **{Name_of_the_gallery}.Selected.{property_name}**

    Мысалы: Gallery1.Selected.address1_city

1. Тұтынушының бірыңғай уақыт шкаласын көрсету үшін галерея элементін қосып, элементтер сипатын қосыңыз: **Filter('UnifiedActivity', CustomerId = {Customer_Id})**

    Мысалы: Filter('UnifiedActivity', CustomerId = Gallery1.Selected.CustomerId)


[!INCLUDE[footer-include](../includes/footer-banner.md)]