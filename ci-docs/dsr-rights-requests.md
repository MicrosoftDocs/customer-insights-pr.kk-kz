---
title: GDPR бойынша деректер нысанының құқықтарына (DSR) қатысты сұраулар | Microsoft Docs
description: Dynamics 365 Customer Insights аудитория мәліметтері мүмкіндіктері үшін деректер субъектілеріне қатысты сұрауға жауап беріңіз.
ms.date: 08/11/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
ms.openlocfilehash: 6faaeb6a1ee34c3e5c8e7d465b37cee589bc920c
ms.sourcegitcommit: 5704002484cdf85ebbcf4e7e4fd12470fd8e259f
ms.translationtype: HT
ms.contentlocale: kk-KZ
ms.lasthandoff: 09/08/2021
ms.locfileid: "7483682"
---
# <a name="data-subject-rights-dsr-requests-under-gdpr"></a>GDPR бойынша деректер субъектілерінің құқықтарына (DSR) қатысты сұраулар

Еуропалық Одақтың Деректерді қорғау бойынша жалпы регламенті (GDPR) 2018 жылдың 25 мамырынан бастап күшіне енді. Бұл жеке тұлғаларда олардың деректеріне қатысты айтарлықтай құқықтар береді. GDPR жеке тұлғалардың құпиялылық құқықтарын қорғауға және қамтамасыз етуге бағытталған. Microsoft корпорациясының қауіпсіздік пен сәйкестікке қатысты міндеттемелері туралы [Microsoft қауіпсіздікті басқару орталығында](https://www.microsoft.com/trust-center) қосымша ақпарат оқи аласыз.

Біз өз тұтынушыларымызға GDPR талаптарын орындауға көмектесуге дайынбыз. Ол пайдаланушы идентификаторы, телефон нөмірлері және электрондық пошта мекенжайлары секілді жеке ақпаратты қамтитын деректерді жою және экспорттау құқығын қамтиды. Әкімшілер пайдаланушылардың жеке деректерді жою немесе экспорттау туралы сұраныстарын жүзеге асыра алады.

## <a name="audience-insights"></a>Аудитория туралы пайдалы мәліметтер

### <a name="responding-to-gdpr-data-subject-delete-requests-for-dynamics-365-customer-insights-audience-insights-capability"></a>Dynamics 365 Customer Insights аудитория мәліметтері мүмкіндіктері үшін GDPR деректер субъектілерін жою сұрауларына жауап беру

Ұйымның тұтынушы деректерінен жеке деректерді "жою құқығы" Деректерді қорғау бойынша жалпы регламенттің (GDPR) негізгі қорғанысы болып табылады. Жеке деректерді жою процесі аудит журналының ақпаратын қоспағанда, барлық жеке деректерді және жүйемен жасалған журналдарды жоюды қамтиды.

#### <a name="manage-data-subject-delete-requests"></a>Деректер нысанын жою сұрауларын басқару

Аудитория мәліметтері белгілі бір тұтынушының немесе пайдаланушының жеке деректерін жою үшін мына өнімдегі тәжірибелерді ұсынады:

- **Тұтынушы деректерінің жою сұрауларын басқару**: Customer Insights ішіндегі тұтынушы деректері бастапқы сыртқы деректер көздерінен Customer Insights жүйесіне қабылданады. Барлық GDPR жою сұраулары бастапқы деректер көзінде орындалуы қажет.
- **Customer Insights пайдаланушы деректерін жою сұрауларын басқару**: Customer Insights жасаған пайдаланушыларға арналған деректер. Барлық GDPR жою сұраулары Customer Insights бағдарламасында орындалуы қажет.

##### <a name="manage-requests-to-delete-customer-data"></a>Тұтынушы деректерін жою сұрауларын басқару

Customer Insights әкімші дереккөзден жойылған тұтынушы деректерін жою үшін осы қадамдарды орындай алады:

1. Dynamics 365 Customer Insights жүйесіне кіріңіз.
2. Аудитория мәліметтерінде **Деректер** > **Деректер көздері** тармағына өтіңіз
3. Жойылған тұтынушы деректерінен тұратын тізімдегі әрбір дереккөз үшін:
   1. (...) параметрін таңдап, одан кейін **Жаңарту** параметрін таңдаңыз.
   2. **Күй** астынан деректер көзі күйін тексеріңіз. Құсбелгі жаңарту сәтті болғанын білдіреді. Ескерту үшбұрышы бірдеңе дұрыс болмағанын білдіреді. Ескерту үшбұрышы көрсетілсе, D365CI@microsoft.com торабына хабарласыңыз.

> [!div class="mx-imgBorder"]
> ![GDPR шешімін қолдану тұтынушы деректерінің сұрауларын жояды.](audience-insights/media/gdpr-data-sources.png "GDPR шешімін қолдану тұтынушы деректерінің сұрауларын жояды")

##### <a name="manage-delete-requests-for-user-data"></a>Пайдаланушы деректерін жою сұрауларын басқару

Customer Insights әкімшісі Customer Insights пайдаланушысы деректерін жою үшін осы қадамдарды орындай алады:

1. Dynamics 365 Customer Insights жүйесіне кіріңіз.
2. Аудитория мәліметтерінде **Әкімші** > **Рұқсаттар** тармағына өтіңіз.
3. Жою керек пайдаланушы құсбелгісін таңдаңыз.
4. **Жою** параметрін таңдаңыз.

### <a name="responding-to-gdpr-data-subject-export-requests"></a>GDPR деректер субъектілерін экспорттау сұрауларына жауап беру

Деректерді қорғау бойынша жалпы регламент (GDPR) бойынша сізбен серіктес құру міндеттемесінің бөлігі ретінде дайындыққа көмектесетін құжатты әзірледік. Бұл құжаттамада аудитория мәліметтерін пайдаланған кезде GDPR сәйкестігіне қолдау көрсету үшін бүгін жасауға болатын қадамдар сипатталған.

#### <a name="manage-export-and-view-requests"></a>Экспорттау және көру сұрауларын басқару

Деректерді тасымалдау құқығы деректер субъектілеріне басқа деректер контроллеріне берілуі мүмкін электрондық пішімдегі ("құрылымдалған, жиі қолданылатын, машинамен оқылатын және өзара жұмыс істейтін пішім" ретінде анықталған) жеке деректердің көшірмесін сұрауға мүмкіндік береді.

##### <a name="export-customer-data-tenant-admin"></a>Тұтынушы деректерін экспорттау (қатысушы әкімшісі)

Қатысушы әкімшісі деректерді экспорттау үшін мына қадамдарды орындай алуы мүмкін:

1. Сұрауда тұтынушының электрондық пошта мекенжайын көрсетіп, D365CI@microsoft.com мекенжайына электрондық хабар жіберіңіз. Customer Insights тобы деректерді экспорттау растауын сұрайтын тіркелген қатысушы әкімшісі электрондық пошта мекенжайына электрондық хабарды жібереді.
2. Сұралған тұтынушыға деректерді экспорттау үшін растауды мақұлдаңыз.
3. Қатысушы әкімшісінің электрондық пошта мекенжайы арқылы экспортталған деректерді алыңыз.

##### <a name="export-user-data-tenant-admin"></a>Пайдаланушы деректерін экспорттау (қатысушы әкімші)

1. Сұрауда пайдаланушының электрондық пошта мекенжайын көрсетіп, D365CI@microsoft.com мекенжайына электрондық хабар жіберіңіз. Customer Insights тобы деректерді экспорттау растауын сұрайтын тіркелген қатысушы әкімшісі электрондық пошта мекенжайына электрондық хабарды жібереді.
2. Сұралған пайдаланушыға деректерді экспорттау үшін растауды мақұлдаңыз.
3. Қатысушы әкімшісінің электрондық пошта мекенжайы арқылы экспортталған деректерді алыңыз.

## <a name="engagement-insights"></a>Өзара әрекеттестік туралы мәліметтер

### <a name="deleting-and-exporting-event-data-containing-end-user-identifiable-information"></a>Соңғы пайдаланушының жеке басын анықтауға болатын ақпаратын қамтитын оқиға деректерін жою және экспорттау

Келесі бөлімдерде жеке деректерді қамтуы мүмкін оқиға деректерін жою және экспорттау әрекеттері сипатталған.

Деректерді жою немесе экспорттау үшін:

1. Жеке ақпаратпен бірге деректерді қамтитын оқиға сипаттарын белгілеңіз.
2. Белгілі бір мәндермен байланысты деректерді жою немесе экспорттау (мысалы: көрсетілген пайдаланушы идентификаторы).

#### <a name="tag-and-update-event-properties"></a>Оқиға сипаттарын белгілеу және жаңарту

Жеке деректер оқиға сипаты деңгейінде белгіленеді. Алдымен жою немесе экспорттау үшін қарастырылатын сипаттарды белгілеңіз.

Оқиға сипатын жеке ақпараты бар деп белгілеу үшін келесі әрекеттерді орындаңыз:

1. Оқиғасы бар жұмыс кеңістігін ашыңыз.

1. Таңдалған жұмыс кеңістігінде оқиғалар тізімін көру үшін **Деректер** > **Оқиғалар** тармағына өтіңіз.
  
1. Белгілеу қажет оқиғаны таңдаңыз.

1. Таңдалған оқиғаның барлық сипаттары көрсетілген тақтаны ашу үшін **Сипаттарды өңдеу** опциясын таңдаңыз.
     
1. **...** белгісін таңдап, **Сипатты жаңарту** диалогтік терезесін ашу үшін **Өңдеу** түймешігін таңдаңыз.

   ![Оқиғаны өзгертіңіз.](engagement-insights/media/edit-event.png "Оқиғаны өзгерту")

1. **Сипатты жаңарту** терезесінде жоғарғы оң жақ бұрышта **...** опциясын таңдап, содан кейін **EUII қамтиды** өрісін таңдаңыз. Өзгерістерді сақтау үшін **Жаңарту** түймешігін басыңыз.

   ![Өзгертулерді сақтау.](engagement-insights/media/update-property.png "Өзгертулерді сақтау")

   > [!NOTE]
   > Оқиғалар схемасы өзгерген сайын немесе жаңа оқиғаны жасаған кезде, байланысты оқиғалардың сипаттарын бағалауға және қажет болған жағдайда оларды дербес деректерді қамтитын ретінде белгілеуге немесе белгісін алып тастауға кеңес беріледі.

#### <a name="delete-or-export-tagged-event-data"></a>Белгіленген оқиға туралы деректерді жою немесе экспорттау

Егер барлық оқиға сипаттары алдыңғы қадамда сипатталғандай тиісті түрде белгіленсе, орта әкімшісі белгіленген оқиғалар туралы деректерді жою туралы сұрау жібере алады.

EUII жою немесе экспорттау туралы сұраныстарды басқару үшін

1. **Әкімші** > **Орта** > **Параметрлер** тармағына өтіңіз.

1. **Соңғы пайдаланушының жеке басын анықтайтын ақпаратын басқару (EUII)** бөлімінде **EUII басқару** опциясын таңдаңыз.

##### <a name="deletion"></a>Жою

Жою үшін сіз **Соңғы пайдаланушының жеке басын анықтайтын ақпаратын жою (EUII)** бөлімінде үтірмен бөлінген пайдаланушы идентификаторларының тізімін енгізуге болады. Содан кейін бұл идентификаторлар жолды нақты сәйкестендіру арқылы ағымдағы ортадағы барлық жобалардың барлық белгіленген оқиғалар сипаттамаларымен салыстырылады. 

Егер сипат мәні берілген идентификаторлардың біріне сәйкес келсе, байланысты оқиға біржола жойылады. Бұл әрекеттің қайтымсыздығына байланысты, **Жою** опциясын таңдағаннан кейін жоюды растау қажет.

##### <a name="export"></a>Export

Экспорттау процесі **Соңғы пайдаланушының жеке басын анықтайтын ақпаратын экспорттау (EUII)**  бөліміндегі оқиға сипатының мәндерін анықтауға келгенде жою процесіне ұқсас. Сонымен қатар экспорттау межелі орнын көрсету үшін **Azure blob сақтау орнының URL мекенжайы** мәнін енгізу қажет. Azure Blob URL мекенжайы [Ортақ қатынасу қолтаңбасы (SAS)](/azure/storage/common/storage-sas-overview) параметрін қамтуы тиіс.

**Экспорттау** опциясы таңдалғаннан кейін сәйкестендірілген сипаттарды қамтитын ағымдағы топтың барлық оқиғалары CSV пішімінде экспорттау орнына экспортталады.

### <a name="good-practices"></a>Үздік тәжірибелер

* Жеке деректерді қамтитын қандай да бір оқиғаларды жіберуге әрекеттенбеңіз.
* EUII деректері бар оқиғаларды жіберу қажет болса, EUII деректері бар оқиғалар мен оқиғалар сипаттарын шектеңіз. Ең дұрысы, осындай оқиғалардың бірімен шектеліңіз.
* Жіберілген жеке деректерге мүмкіндігінше аз адам қол жеткізе алатынына көз жеткізіңіз.
* Жеке деректер бар оқиғалар үшін белгілі бір пайдаланушыға оңай байланыстырылатын бірегей идентификатор шығаратын бір сипатты орнатқаныңызға көз жеткізіңіз (мысалы, пайдаланушының идентификаторы). Бұл деректерді бөлуді және дұрыс деректерді экспорттауды немесе жоюды жеңілдетеді.
* Әр оқиға үшін жеке деректерді қамтитын бір ғана сипатты белгілеңіз. Ең дұрысы тек бір мәнді идентификаторы барын таңдаңыз.
* Толық мәндері бар сипаттарды белгілемеңіз (мысалы, бүкіл сұрау мәтіні). Өзара әрекеттестік туралы түсініктер мүмкіндігі қандай оқиғаларды жою немесе экспорттау қажеттігін шешкен кезде жолдың нақты сәйкестігін пайдаланады.

[!INCLUDE[footer-include](includes/footer-banner.md)]