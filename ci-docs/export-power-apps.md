---
title: Power Apps коннекторы
description: Power Apps және Power Automate арқылы қосылу.
ms.date: 10/01/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: Nils-2m
ms.author: nikeller
manager: shellyha
ms.openlocfilehash: e99d7d4f231eb2ade67f27c9e52c61af3a21b99d
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: MT
ms.contentlocale: kk-KZ
ms.lasthandoff: 04/27/2022
ms.locfileid: "8643950"
---
# <a name="microsoft-power-apps-connector-preview"></a>Microsoft Power Apps қосқышы (алдын ала қарау)

Power Apps бағдарламасымен бірыңғай тұтынушы профильдерін жекелендірілген бағдарламаларыңызға қосыңыз.

## <a name="connect-power-apps-and-dynamics-365-customer-insights"></a>Power Apps және Dynamics 365 Customer Insights бағдарламаларын қосу

Customer Insights көптеген [Power Apps бағдарламасында қолжетімді көздердің](/powerapps/maker/canvas-apps/working-with-data-sources) бірі.

[Бағдарламаға деректер қосылымын қосу](/powerapps/maker/canvas-apps/add-data-connection) жолы туралы ақпаратты Power Apps құжаттамасынан қараңыз. Сондай-ақ сізге [Power Apps кенеп бағдарламаларында үлкен деректер жиындарын өңдеу үшін өкілеттеуді пайдалану жолын](/powerapps/maker/canvas-apps/delegation-overview) қарап шығуды ұсынамыз.

## <a name="available-entities"></a>Бар нысандар

Customer Insights деректер қосылымы ретінде қосқаннан кейін, келесі нысандарды Power Apps бағдарламасында таңдауға болады:

- **Тұтынушы**: [бірыңғай тұтынушы профилінің](customer-profiles.md) деректерін пайдалану үшін.
- **UnifiedActivity** : бағдарламадағы [әрекеттің уақыт шкаласын](activities.md) көрсету үшін.
- **ContactProfile**: тұтынушының контактілерін көрсету үшін. Бұл нысан бизнес тіркелгілеріне арналған Customer Insights орталарында ғана қолжетімді.

## <a name="limitations"></a>Шектеулер

### <a name="retrievable-entities"></a>Шығарып алуға болатын нысандар

Power Apps қосқышы арқылы тек **Тұтынушы**, **UnifiedActivity**, **Сегменттер** және **ContactProfile** нысандарын ғана шығаруға болады. ContactProfile бизнес тіркелгілері үшін Customer Insights данасында ғана қолжетімді. Басқа нысандар негізгі коннектор бұл нысандарды Power Automate ішіндегі триггерлер арқылы қолдайтындықтан көрсетіледі.

Сіз 60 секундта ең көбі 100 қоңырау шала аласыз. $skip параметрін пайдалану арқылы API соңғы нүктесіне бірнеше рет қоңырау шалуға болады. [$skip параметрі туралы көбірек біліңіз](/connectors/customerinsights/#get-items-from-an-entity).

### <a name="delegation"></a>Өкіл

**Тұтынушы** нысаны және **UnifiedActivity** нысаны үшін жұмысты өкілеттеу. 

- **Тұтынушы** нысанына арналған өкілеттік: осы нысан үшін өкілеттікті пайдалану үшін өрістерді [Іздеу және сүзгілеу индексі](search-filter-index.md) жүйесінде индекстеу керек.  
- **Бірыңғай әрекет** үшін өкілеттеу: бұл нысан үшін өкілеттеу тек **Әрекет идентификаторы** және **Тұтынушы идентификаторы** өрістері үшін жұмыс істейді.  
- **ContactProfile** нысаны үшін өкілеттеу: бұл нысан үшін өкілеттеу тек **ContactId** және **CustomerId** өрістері үшін ғана жұмыс істейді. ContactProfile іскери тіркелгілерге арналған Customer Insights орталарында ғана қолжетімді.

Өкілеттеу туралы қосымша ақпарат алу үшін [Power Apps өкілетті функциялары мен операциялары](/powerapps/maker/canvas-apps/delegation-overview) бөліміне өтіңіз. 

## <a name="example-gallery-control"></a>Галереяны басқару мысалы

Тұтынушы профильдерін [галерея басқару элементіне](/powerapps/maker/canvas-apps/add-gallery) қосуға болады.

1. Жасап жатқан бағдарламаға **галерея** басқару элементін қосыңыз.

    > [!div class="mx-imgBorder"]
    > ![Галерея элементін қосыңыз.](media/connector-powerapps9.png "Галерея элементін қосыңыз.")

2. **Тұтынушы** параметрін элементтердің деректер көзі ретінде таңдаңыз.

    > [!div class="mx-imgBorder"]
    > ![Деректер көзін таңдаңыз.](media/choose-datasource-powerapps.png "Деректер көзін таңдаңыз.")

3. Галереяда көрсетілетін Тұтынушы нысаны өрісін таңдау үшін оң жақта деректер тақтасын өзгерте аласыз.

4. Галереяда таңдалған тұтынушыдан кез келген өрісті көрсету керек болса, **{Name_of_the_gallery}.Selected.{property_name}** параметрін пайдалану арқылы белгінің **мәтін** сипатын толтырыңыз  
    - Мысалы: _Gallery1.Selected.address1_city_

5. Тұтынушының бірыңғай уақыт шкаласын көрсету үшін галерея элементін қосып, **Filter('UnifiedActivity', CustomerId = {Customer_Id})** параметрін пайдалану арқылы **Элементтер** сипатын қосыңыз  
    - Мысалы: _Filter('UnifiedActivity', CustomerId = Gallery1.Selected.CustomerId)_


[!INCLUDE [footer-include](includes/footer-banner.md)]
