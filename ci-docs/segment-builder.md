---
title: Сегмент құрастырғышымен сегменттер жасау
description: Әр түрлі төлсипаттарға байланысты топқа тұтынушылар сегменттерін жасаңыз.
ms.date: 03/25/2022
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-segments
- ci-segment-builder
- ci-segment-details
- customerInsights
ms.openlocfilehash: c8e9e4976ade36c1c3c4f688a667b329bfde6e3e
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: MT
ms.contentlocale: kk-KZ
ms.lasthandoff: 04/27/2022
ms.locfileid: "8643551"
---
# <a name="create-segments"></a>Сегменттер жасау

Бірыңғай тұтынушы нысаны мен оған қатысты нысандар айналасындағы күрделі сүзгілерді анықтаңыз. Өңдеуден кейін әрбір сегмент экспорттауға және әрекет етуге болатын тұтынушы жазбалары жинағын жасайды. Сегменттер **Сегменттер** бетінде басқарылады. Сегмент құрастырғышының көмегімен [жаңа сегменттер жасауға](#create-a-new-segment) немесе бағдарламаның басқа аймақтарынан [жылдам сегменттер жасауға](#quick-segments) болады.

> [!TIP]
> - Жылдам сегменттерге тек **жеке тұтынушыларға** арналған орталарда қолдау көрсетіледі.
> - **Жеке тұтынушыларға** негізделген сегменттер сегмент мүшелері үшін қолжетімді байланыс ақпаратын автоматты түрде қамтиды. **Бизнес тіркелгілерге** арналған орталарда сегменттер тіркелгілерге негізделеді (компаниялар немесе еншілес ұйымдар). Байланыс ақпаратын сегментке қосу үшін сегмент құрастырғышындағы **Жоба төлсипаттары** функциясын пайдаланыңыз. Байланыс деректерінің көздері [ContactProfile нысанымен семантикалық түрде салыстырылғанына](semantic-mappings.md#define-a-contactprofile-semantic-entity-mapping) көз жеткізіңіз.

## <a name="segment-builder"></a>Сегмент құрастырғышы

Келесі кескінде сегмент құрастырғышының әртүрлі аспектілері көрсетілген. Ол тұтынушылар тобын құрайтын сегментті көрсетеді. Тұтынушылар белгілі бір уақыт аралығында тауарларға тапсырыс беріп, сыйақы ұпайларын жинады немесе белгілі бір ақша көлемін жұмсады.

:::image type="content" source="media/segment-builder-overview.png" alt-text="Сегмент құрастырғышының элементтері." lightbox="media/segment-builder-overview.png":::

1. Сегментті ережелер және ішкі ережелермен ұйымдастырыңыз. Әрбір ереже немесе ішкі ереже шарттардан тұрады. Шарттарды логикалық операторлармен біріктіріңіз

1. Ережеге қолданылатын нысандар арасында [қарым-қатынас жолын](relationships.md) таңдаңыз. Қарым-қатынас жолы шартта қандай төлсипаттарды пайдалануға болатынын анықтайды.

1. Ережелер мен ішкі ережелерді басқарыңыз. Ереженің орнын өзгертіңіз немесе жойыңыз.

1. Шарттарды қосыңыз және ішкі ережелер көмегімен қабатталымның қажетті деңгейін құрыңыз.

1. Қосылған ережелерге орнатылған әрекеттерді қолданыңыз.

1. Қолжетімді нысан төлсипаттарын қосу немесе төлсипаттарға негізделген шарттарды жасау үшін төлсипаттар тақтасын пайдаланыңыз. Тақта таңдалған ереже үшін қолжетімді таңдалған қатынас жолына негізделген нысандар мен төлсипаттар тізімін көрсетеді.

1. Қолданыстағы ережелер мен ішкі ережелерге төлсипаттарға негізделген шарттарды қосыңыз немесе оны жаңа ережеге қосыңыз.

1. Сегмент жасау кезінде өзгерістерді болдырмау және қайта жасау.

Жоғарыдағы мысал сегменттеу мүмкіндігін көрсетеді. Біз желіде кем дегенде $500 тауарларын сатып алған тұтынушыларға арналған сегментті анықтадық *және* бағдарламалық қамтамасыз етуді жасауға қызығушылық танытады.

## <a name="create-a-new-segment"></a>Жаңа сегментті жасау

Жаңа сегмент жасаудың бірнеше әдісі бар. Бұл бөлімде жеке сегментті басынан құру жолы керектігі сипатталған. Сондай‑ақ бұрыннан бар нысандар негізінде *жылдам сегмент* жасауға болады немесе *ұсынылған сегменттерді* алу үшін компьютерлік оқыту модельдерін пайдалануға болады. Қосымша ақпарат алу үшін [Сегменттерге шолу](segments.md) бөліміне өтіңіз.

Сегментті жасау кезінде нобайды сақтай аласыз. Жоба кезеңінде сегмент белсенді емес сегмент ретінде сақталады. Сегменттің конфигурациясын аяқтағаннан кейін, сегментті белсендіру үшін оны іске қосыңыз. Сондай-ақ сегментті **Барлық сегменттер** бетінен **Іске қосуға** болады.

1. **Сегменттер** бетіне өтіңіз.

1. **Жаңа** > **Өзіңіздікін құру** тармағын таңдаңыз.

1. Сегмент құрастырғышы бетінде сіз ережелерді анықтайсыз немесе құрастырасыз. Ереже тұтынушылардың жиынтығын анықтайтын бір немесе бірнеше шарттан тұрады.

1. Ішінде **Ереже 1** бөлімінде тұтынушыларды сүзгіңіз келетін нысан төлсипатын таңдаңыз. Төлсипаттарды таңдаудың екі жолы бар:
   - **Ережеге қосу** тақтасында қолжетімді нысандар мен төлсипаттар тізімін қарап шығыңыз және қосылатын төлсипат жанында **+** белгішесін таңдаңыз. Төлсипаттары бұрыннан бар ережеге қосқыңыз келетінін немесе оны жаңа ереже жасау үшін пайдаланғыңыз келетінін таңдаңыз.
   - Сәйкес ұсыныстарды көру үшін ереже бөліміне төлсипат атауын енгізіңіз.

1. Шарттың сәйкес келетін мәндерін көрсету үшін операторларды таңдаңыз. Төлсипат мән ретінде төрт деректер түрінің біреуіне ие бола алады: сандық, жолдық, күндік немесе логикалық. Төлсипаттың деректер түріне байланысты шартты көрсету үшін әртүрлі операторлар қолжетімді. Бизнес тіркелгілері бар сегменттер үшін қабылданған тіркелгілер арасындағы ықтимал иерархияларды қамтитын екі арнайы оператор бар. Байланысты тіркелгілерді қамту үшін *еншілес* және *басты* операторларды пайдаланыңыз.

1. Ережеге қосымша шарттарды қосу үшін **Шарт қосу** опциясын таңдаңыз. Ағымдағы ереже бойынша ереже жасау үшін **Ішкі ережені қосу** опциясын таңдаңыз.

1. Егер ереже *Тұтынушы* нысанынан басқа нысандарды пайдаланатын болса, қарым-қатынас жолын орнатуыңыз керек. Қарым-қатынас жолы бірыңғай профиль нысанына қатынастың қандай қатынаста болатынын хабарлау үшін қажет. Таңдалған нысанды бірыңғай тұтынушы нысанына салыстыру үшін **Қарым-қатынас жолы** опциясын таңдаңыз. Егер мүмкін болатын бір ғана қатынас жолы болса, жүйе оны автоматты түрде таңдайды. Әртүрлі қарым-қатынас жолдары әртүрлі нәтижелерге әкелуі мүмкін. Әр ереженің өзіндік қарым-қатынас жолы болуы мүмкін.

   :::image type="content" source="media/relationship-path.png" alt-text="Бірыңғай тұтынушы нысанына салыстырылған нысанға негізделген ережені құру кезіндегі ықтимал қатынас жолы.":::

   Мысалы, скриншоттағы *eCommerce_eCommercePurchases* нысанында *Тұтынушы* нысанына салыстыру үшін төрт нұсқасы бар:
   - eCommerce_eCommercePurchases > eCommerce_eCommerceContacts > Тұтынушы
   - eCommerce_eCommercePurchases > Тұтынушы
   - eCommerce_eCommercePurchases > eCommerce_eCommerceContacts > POS_posPurchases > Тұтынушы
   - eCommerce_eCommercePurchases > eCommerce_eCommerceContacts > POS_posPurchases > loyaltyScheme_loyCustomers > Тұтынушы Соңғы опцияны таңдағанда, біз ереже шарттарына барлық тізімделген нысандардан төлсипаттарды қоса аламыз. Біз аз нәтиже аламыз, себебі сәйкес келетін тұтынушы жазбалары барлық құрылымдардың бөлігі болуы керек. Бұл мысалда олар тауарларды сауда нүктесінде(*POS_posPurchases*) электронды сауда(*eCommerce_eCommercePurchases*) арқылы сатып алып, біздің адалдық бағдарламасына (*loyaltyScheme_loyCustomers*) қатысуы керек. Екінші нұсқаны таңдағанда, *eCommerce_eCommercePurchases* және *Тұтынушы* нысанынан тек төлсипаттарды таңдай аламыз. Бұл тұтынушы профилін жақсартуға әкелуі мүмкін.

1. Егер ережеде бірнеше шарт болса, оларды қосатын логикалық операторды таңдауға болады.  
   - **ЖӘНЕ** оператор: сегментке жазбаны қосу үшін барлық шарттар орындалуы керек. Әр түрлі нысандар бойынша шарттарды анықтаған кезде осы опция өте пайдалы болады.
   - **НЕМЕСЕ** оператор: сегментке жазбаны қосу үшін шарттардың бірі орындалуы керек. Бір нысан үшін бірнеше шартты анықтаған кезде осы опция өте пайдалы болады.

   :::image type="content" source="media/segmentation-either-condition.png" alt-text="Екі ЖӘНЕ шарты бар ереже.":::

   НЕМЕСЕ операторын қолданған кезде барлық шарттар қатынас жолына қосылған нысандарға негізделуі керек.

   - Тұтынушы жазбаларының әртүрлі жиынтығын жасау үшін бірнеше ережелер жасауға болады. Сіз өзіңіздің бизнес ісіңізге қажетті тұтынушыларды қосу үшін топтарды біріктіре аласыз. Жаңа ережені жасау үшін **Ереже қосу** пәрменін таңдаңыз. Атап айтқанда, көрсетілген қатынас жолына байланысты ережеге нысанды қоса алмасаңыз, оны құрайтын төлсипаттарды таңдау үшін жаңа ереже жасауыңыз керек.

      :::image type="content" source="media/segment-rule-grouping.png" alt-text="Сегментке жаңа ереже қосып, орнатылған операторды таңдаңыз.":::

   - Орнатылған операторлардың бірін таңдаңыз: **Біріктіру**, **Қиылысу** немесе **Басқа**.

      - **Бірлестік** екі топты біріктіреді.
      - **Қиылысу** екі топты қабаттастырады. Екі топ үшін *жалпы* болып табылатын деректер ғана біріктірілген топта қалады.
      - **Қоспағанда** екі топты біріктіреді. В тобындағы деректермен *жалпы емес* А тобындағы деректер ғана сақталады.

1. Әдепкі бойынша, сегменттер анықталған сүзгілерге сәйкес келетін тұтынушы профильдерінің барлық төлсипаттары бар шығыс нысанын жасайды. Егер сегмент *Тұтынушы* нысанынан басқа нысандарға негізделген болса, осы нысандардан шығыс нысанға қосымша төлсипаттар қосуға болады. Шығыс нысанға қосылатын төлсипаттарды таңдау үшін **Жоба төлсипаттары** опциясын таңдаңыз.

   > [!IMPORTANT]
   > Бизнес тіркелгілерге негізделген сегменттер үшін байланыс ақпаратын қажет ететін межелі орындарға осы сегментті іске қосуға немесе экспорттауға мүмкіндік беру үшін сегментте *ContactProfile* нысанынан әрбір тіркелгінің бір немесе бірнеше контактілерінің мәліметтерін қосу қажет. *ContactProfile* нысаны туралы қосымша ақпарат алу үшін [Семантикалық салыстырулар](semantic-mappings.md) тақырыбын қараңыз.
   > Контактілердің болжамды төлсипаттары бар бизнес тіркелгілеріне негізделген сегментке арналған шығыс үлгісі келесідей болуы мүмкін:
   >
   > |Идентификатор  |Тіркелгі атауы  |Табыс  |Контакт аты  | Контакт рөлі|
   > |---------|---------|---------|---------|---|
   > |10021     | Contoso | 100 мың | [Abbie Moss, Ruth Soto]  | [Бас директор, сатып алу жөніндегі менеджер]

   :::image type="content" source="media/segments-project-attributes.png" alt-text="Шығыс нысанына қосылатын бүйірлік тақтада таңдалған жобаланған төлсипаттар мысалы.":::
  
   Мысалы: сегмент *Тұтынушы* нысанына қатысты сатып алу деректерін қамтитын нысанға негізделген. Сегмент ағымдағы жылы тауар сатып алған Испаниядан келген барлық тұтынушыларды іздейді. Сіз тауардың бағасы немесе сатып алу күні сияқты төлсипаттарды шығыс нысанындағы барлық сәйкес келетін тұтынушы жазбаларына қосуды таңдай аласыз. Бұл ақпарат шығыстардың жалпы көлемінің маусымдық өзара қатынастарын талдау үшін пайдалы болуы мүмкін.

   > [!NOTE]
   > - **Жоба төлсипаттары** тек тұтынушы нысанымен біреуі көпке қатынасы бар нысандар үшін ғана жұмыс істейді. Мысалы, бір тұтынушы бірнеше жазылымға ие бола алады.
   > - Егер сіз жобалау керек төлсипат *Тұтынушы* нысанынан бір айналымнан көп қашықтықта болса, қатынаспен анықталғандай, бұл төлсипат сіз құратын сегмент сұрауының әрбір ережесінде қолданылуы керек.
   > - Егер сіз жобалау керек төлсипат *Тұтынушы* нысанынан тек бір айналым қашықтықта болса, ол төлсипат сіз құратын сегмент сұрауының әрбір ережесінде болуы міндетті емес.
   > - **Жобаланған төлсипаттар** орнатылған операторларды пайдалану кезінде ескеріледі.

1. таңдаңыз **Мәліметтерді өңдеу** Атаусыз сегменттің жанында. Сегментке атау беріңіз және сегментке арналған ұсынылған **Шығыс нысан атауы** өрісін жаңартыңыз. Қажет болса, сипаттаманы қосыңыз және [тегтер](work-with-tags-columns.md#manage-tags) сегментіне.

   :::image type="content" source="media/segments_edit_details.png" alt-text="Мәліметтерді өңдеу диалогтық терезесі.":::

1. Сегментті сақтау үшін **Іске қосу** түймешігін таңдаңыз, оны белсендіріңіз және сегментті барлық ережелер мен шарттар негізінде өңдей бастаңыз. Әйтпесе, ол белсенді емес сегмент ретінде сақталады.

1. **Сегменттер** бетіне кері өту үшін **Сегменттерге оралу** параметрін таңдаңыз.

1. Әдепкі бойынша сегмент динамикалық сегмент ретінде жасалады. Бұл сегменттің жүйені жаңарту кезінде жаңартылатынын білдіреді. [Автоматты жаңартуды тоқтату үшін](segments.md#manage-existing-segments) сегментті және **Статикалық ету** опциясын таңдаңыз. Статикалық сегменттерді кез келген уақытта [қолмен жаңартуға болады](segments.md#refresh-segments).

> [!TIP]
> - Сегментті құрушы операторларға шарттарды орнатқан кезде нысандардан жарамды мәндерді ұсынбайды. **Деректер** > **Нысандар** тармағына өтіп, қолжетімді мәндерді көру үшін нысан деректерін жүктеңіз.
> - Күндерге негізделген шарттар белгіленген күндер мен өзгермелі күндер ауқымы арасында ауысуға мүмкіндік береді.
> - Егер сізде сегмент үшін бірнеше ереже болса, онда сіз өңдеп жатқан ереженің қасында тік көк сызық болады.
> - Ережелер мен шарттарды сегмент анықтамасындағы басқа орындарға жылжытуға болады. Ереженің немесе шарттың жанындағы [...] тармағын таңдап, оны қалай және қайда жылжытуды таңдаңыз.
> - Пәрмен жолағындағы **Болдырмау** және **Қайталау** басқару элементтері өзгерістерді қайтаруға мүмкіндік береді.

## <a name="quick-segments"></a>Жылдам сегменттер

Жылдам сегменттер тезірек түсіну үшін бір оператормен қарапайым сегменттерді жылдам құруға мүмкіндік береді.

1. **Сегменттер** бетінде **Жаңа** > **Жасалатын орын** тармағын таңдаңыз.
   - *Бірыңғай тұтынушы* нысанына негізделген сегментті құрастыру үшін **Профильдер** опциясын таңдаңыз.
   - Бұрын жасаған өлшемдер бойынша сегмент құру үшін **Өлшемдер** опциясын таңдаңыз.
   - **Болжамдар** немесе **Реттелетін үлгілер** мүмкіндіктерінің бірін пайдалану арқылы құрылған шығыс нысандарының бірінің айналасында сегмент құру үшін **Интеллект** опциясын таңдаңыз.

2. **Жаңа жылдам сегмент** диалогтік терезесінде **Өріс** ашылмалы мәзірінен төлсипатты таңдаңыз.

3. Жүйе сіздің тұтынушыларыңыздың жақсы сегменттерін құруға көмектесетін қосымша ақпарат береді.
   - Санаттық өрістер үшін 10 үздік тұтынушы санын көрсетеміз. **Мән** таңдап, **Қарап шығу** параметрін таңдаңыз.
   - Сандық төлсипат үшін жүйе әрбір тұтынушы процентиліне қандай төлсипат мәні жататынын көрсетеді. **Оператор** және **Мән** таңдап, **Қарап шығу** параметрін таңдаңыз.

4. Жүйе сізге **Болжалды сегмент өлшемін** береді. Сіз анықтаған сегментті құруды немесе басқа сегмент өлшемін алу үшін қайта кіруді таңдай аласыз.

   :::image type="content" source="media/quick-segment-name.png" alt-text="Жылдам сегменттің атауы және болжамы.":::

5. А қамтамасыз етіңіз **Аты** және **Шығару нысанының атауы** сіздің сегментіңіз үшін. Қажет болса, қосыңыз [тегтер](work-with-tags-columns.md#manage-tags).

6. Сегментті жасау үшін **Сақтау** пәрменін таңдаңыз.

7. Сегментті өңдеуді аяқтаған соң, сіз жасаған басқа сегмент сияқтыны көре аласыз.

## <a name="next-steps"></a>Келесі қадамдар

Басқа бағдарламаларда сегменттерді пайдалану үшін [сегментті экспорттаңыз](export-destinations.md) және [тұтынушы картасы интеграциясын](customer-card-add-in.md) зерттеңіз.

[!INCLUDE [footer-include](includes/footer-banner.md)]