---
title: Make Audio Conferencing service decisions - Microsoft Teams
author: rmw2890
ms.author: MyAdvisor
manager: lehewe
ms.date: 03/13/2018
ms.topic: article
ms.service: msteams
ms.reviewer: rowille
description: Learn about meetings, licensing and availability, configure conference bridge settings, acquire or transfer phone numbers, choose tenant dial plans.
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 80a4007b328ec66bed0ccae0160491b4ee20f858
ms.sourcegitcommit: b985035b91ebd7ceff8d50e9e0fa9aa6ff971f3a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2018
---
# <a name="make-my-service-decisions"></a>Make my service decisions

To plan for the technical implementation of Audio Conferencing, you must make a series of service decisions ahead of time to better prepare your organization to implement a solution that meets your defined business requirements.

As part of defining required Audio Conferencing features in Microsoft Teams, one of the first steps is to evaluate the latest public roadmap to determine:

-   Which Audio Conferencing features in Teams that will be deployed for users in scope.

-   Expected user functionality requirements for Audio Conferencing in Teams.

-   Confirmation that Audio Conferencing features in Teams described in the latest public roadmap meet your user, functionality, and scope requirements, within the timeline of your deployment.

> [!NOTE]
> The latest Teams roadmap for identifying Teams Audio Conferencing features in scope for your deployment can be found at <https://aka.ms/skype2teamsroadmap>.

## <a name="meetings-in-teams"></a>Собрания в Teams

Teams gives your users the capability to schedule and join online meetings by using HD video, voice over IP (VoIP), and PSTN dial-in conferencing options.

Meetings can be scheduled as private meetings (only invited parties can join) or channel meetings (open for all users having access to the channel), and your users can also start impromptu meetings within channels.

> [!NOTE]
> To learn more about the features of meetings in Teams, see the [Skype for Business to Microsoft Teams Capabilities Roadmap] https://aka.ms/skype2teamsroadmap).

Meeting participants can join your Teams meetings by dialing in to the toll or toll-free dial-in conference bridge phone numbers via landlines or mobile phones. In addition, users can let the Audio Conferencing service initiate the “call me” feature so they can participate in a meeting by having the conference bridge call their phones (useful when the data connection isn’t reliable), or let meeting organizers invite meeting participants by dialing out to their phones.

> [!IMPORTANT]
> Audio Conferencing in Teams doesn’t support third-party audio conferencing providers (ACPs).

<!--ENDOFSECTION-->

## <a name="availability-of-audio-conferencing"></a>Доступность Аудиоконференций

Before you plan for the implementation of Audio Conferencing in Teams, you need to review the availability of the Audio Conferencing service as detailed in [Country and region availability for Audio Conferencing and Calling Plans](https://docs.microsoft.com/SkypeForBusiness/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans).

> [!IMPORTANT]
> Due to legal constraints, for Audio Conferencing to be available to multinational organizations, the contract for Office 365 subscriptions must be sourced from countries and regions where the Audio Conferencing service is commercially available.

After confirming your organization is eligible to obtain the Audio Conferencing service, compile the list of user locations or offices where you’ll implement the Audio Conferencing service, based on the list of available countries and regions.

<br>
|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|Decision points|<ul><li>Определите, в каких расположениях пользователей или офисах будет внедрена служба Аудиоконференций.</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|Дальнейшие действия|<ul><li>Задокументируйте расположения пользователей или офисы, где будет использоваться служба Аудиоконференций.</li></ul>|

> [!TIP]
> Below is an example of an Audio Conferencing site enablement list template:
>|Офис   |Расположение |Служба конференц-связи по ТСОП  |
>|---------|---------|---------|
>|One Epping Road|Австралия|Аудиоконференции|
>|100 Cyberport Road|Гонконг (специальный административный район)|Устаревшая служба конференц-связи по ТСОП|
>|One Marina Boulevard|Сингапур|Аудиоконференции|
>|32 London Bridge Street|Соединенное Королевство|Аудиоконференции|
>|39 quai du Président Roosevelt|Франция|Аудиоконференции|

<!--ENDOFSECTION-->

## <a name="licensing-for-audio-conferencing"></a>Лицензирование Аудиоконференций

An [Audio Conferencing license](https://docs.microsoft.com/SkypeForBusiness/skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing) is available as part of Office 365 E5 subscription plans, or as an add-on service to Office 365 E1 or Office 365 E3 subscription plans.

> [!NOTE]
> PSTN or dial-in conferencing in Teams doesn’t support third-party audio conferencing providers (ACPs).
> <br>Если вы уже используете конференц-связь по ТСОП Skype для бизнеса Online, то можете сразу же воспользоваться преимуществами Аудиоконференций в Teams.

To provide toll-free conference bridge phone numbers and to support conferencing dial-out to international phone numbers, you must set up [Communications Credits](https://docs.microsoft.com/SkypeForBusiness/skype-for-business-and-microsoft-teams-add-on-licensing/what-are-communications-credits) for your organization.

> [!IMPORTANT]
> Some countries are serviced by toll-free conference bridge phone numbers only. To support dial-in in these countries, you must use Communications Credits.

The first consideration when implementing Communications Credits is to decide the initial amount of funds you want to purchase. If your organization chooses to use auto-recharge, you need to decide the trigger amount (lowest amount of funds) and the auto-recharge amount. Your actual usage will determine the auto-recharge amount. You should monitor your Communications Credits usage over time and adjust the recharge amount as necessary.

You can learn more about Communications Credits [here](https://docs.microsoft.com/SkypeForBusiness/skype-for-business-and-microsoft-teams-add-on-licensing/what-are-communications-credits).

<br>
|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|Decision points|<ul><li>If your organization hasn’t already purchased the required Audio Conferencing licensing, decide whether you’ll acquire Audio Conferencing licenses by stepping up existing Office 365 subscriptions or by acquiring Audio Conferencing add-on licenses.</li><li>Decide whether Communications Credits are required for your Audio Conferencing implementation. Если нужны, определите начальный объем приобретаемых средств. При необходимости определите пороговую сумму и сумму для автоматического пополнения счета.</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|Дальнейшие действия|<ul><li>Document the users who will be assigned Audio Conferencing licenses.</li><li>Document the Communications Credits plan (initial amount, trigger amount,auto-recharge amount)</li></ul>|

> [!TIP]
> You can document the license assignment list for Audio Conferencing users by using the following example.
>|Пользователь  |Офис  |Лицензия на Office 365  |
>|---------|---------|---------|
>|Adele Vance|One Epping Road|Office 365 E5|
>|Alex Wilber|One Epping Road|Office 365 E3, надстройка Аудиоконференций|
>|Ben Walters|One Epping Road|Office 365 E3, надстройка Аудиоконференций|
>|Christie Cline|One Marina Boulevard|Office 365 E3, надстройка Аудиоконференций|
>|Debra Berger|One Marina Boulevard|Office 365 E5|
>|Lee Gu|One Marina Boulevard|Office 365 E5|
>|Emily Braun|32 London Bridge Street|Office 365 E5|
>|Lidia Holloway|32 London Bridge Street|Office 365 E5|
>|Louis Lahr|32 London Bridge Street|Office 365 E5|
>|Marcel Beauchamp|39 quai du Président Roosevelt|Office 365 E3, надстройка Аудиоконференций|
>|Rachelle Cormier|39 quai du Président Roosevelt|Office 365 E5|
>|Isabell Potvin|39 quai du Président Roosevelt|Office 365 E3, надстройка Аудиоконференций|

<br>
> [!TIP]
> Ниже приведен пример документирования планируемых сумм кредитов на связь.
>|         |         |
>|---------|---------|
>|Начальная сумма|1000 долл. США|
>|Пороговая сумма|400 долл. США|
>|Сумма для автоматического пополнения счета|Подлежит добавлению|

<!--ENDOFSECTION-->

## <a name="conference-bridge-phone-numbers"></a>Телефонные номера для моста конференций

Служба Аудиоконференций в Office 365 включает в себя следующее:

-   Несколько типов конференции мост телефонных номеров (звонки на платные телефоны и бесплатный номер)

-   Multiple categories of conference bridge phone numbers (dedicated and shared)

-   Поддержка нескольких языков для моста конференций (основной и дополнительный)

-   A default phone number for the tenant

> [!NOTE]
> Dedicated conference bridge phone numbers count toward the limit of phone numbers that can be acquired per tenant, based on the number of applicable licenses. Бесплатные телефонные номера для моста конференций требуют использования Кредитов на связь.

If you must transfer existing conference bridge phone numbers to the Audio Conferencing service—assuming they meet country-specific requirements—you can transfer these existing conference bridge phone numbers to Microsoft.

> [!NOTE]
The complexity of transferring phone numbers to Microsoft varies greatly depending on country or region, carrier, number of circuits involved, and many other contributing factors. Work with your current provider to investigate how long this is likely to take to help ensure that you start the process early enough to meet your timelines.

To learn more about conference bridge phone numbers, review the following articles:

-   [Настройка аудиоконференций в Skype для бизнеса и Microsoft Teams](https://docs.microsoft.com/SkypeForBusiness/audio-conferencing-in-office-365/set-up-audio-conferencing)

-   [Номера телефонов для аудиоконференций](https://docs.microsoft.com/SkypeForBusiness/audio-conferencing-in-office-365/phone-numbers-for-audio-conferencing)

-   [Получение служебных номеров телефонов](https://docs.microsoft.com/SkypeForBusiness/what-is-phone-system-in-office-365/getting-service-phone-numbers)

-   [Передача номеров телефонов в Office 365](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/transfer-phone-numbers-to-office-365)

<br>
|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|Точки принятия решений|<ul><li>Decide whether your organization needs dedicated conference bridge phone numbers.</li><li>Decide how the dedicated conference bridge phone numbers will be obtained for user locations or offices in-scope for the Audio Conferencing implementation (that is, obtain from Microsoft or transfer existing phone numbers).</li><li>If you choose to obtain them from Microsoft, decide the method to use (form submission or automated) for user locations or offices in-scope for the Audio Conferencing implementation.</li><li>Decide the language preferences to set up for each dedicated conference bridge phone number.</li><li>Decide the tenant default conference bridge phone number.</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|Дальнейшие действия|<ul><li>Document the master plan for phone number acquisition, detailing how phone numbers will be obtained for each user location or office in scope for the Audio Conferencing implementation.</li><li>If applicable, complete the New Telephone Number Request form—one form for each location or office.</li><li>Document the detailed conference bridge phone number configurations (shared and dedicated conference bridge phone numbers, language preferences for each dedicated conference bridge phone number, tenant default conference bridge phone number).</li></ul>|

Below is an example of a template you can use to capture conference bridge details.

> [!TIP]
> Ниже приведен пример шаблона по сбору сведений для моста конференций.
>|Офис   |Получение номеров моста и тип моста |Номер моста  |Язык моста|
>|---------|---------|---------|---------|
>|One Epping Road|Новый, выделенный|Подлежит добавлению|Английский (Австралия)|
>|One Marina Boulevard|Новый, общий|Подлежит добавлению|Английский (США), китайский (упрощенное письмо, КНР)|
>|32 London Bridge Street|Перенос, выделенный|+44 20 7946 0001|Английский (Соединенное Королевство)|
>|39 quai du Président Roosevelt|Новый, выделенный|Подлежит добавлению|Французский (Франция), английский (Соединенное Королевство)|

<!--ENDOFSECTION-->

## <a name="conference-bridge-settings"></a>Параметры моста конференций

Для дальнейшего уточнения удобство работы пользователей, можно настроить параметры всей организации по присоединению к аудиоконференции собрания (входе и выходе уведомлений и вызывающего имя записи собраний), организатор собрания длина ПИН-кода и уведомления по электронной почте:

-   Уведомления о входе на собрание и выходе из него доступны в форме записанного имени, номера телефона и мелодий.

-   Длина ПИН-кода настраивается в пределах от 4 до 12 цифр и по умолчанию равна 5 цифрам.

-   Notification emails sent on enablement of the Audio Conferencing license or any other admin-driven change are enabled by default. You can disable this feature and take control of your organization’s user communications.

For users who are assigned an Audio Conferencing license, the default toll/toll-free numbers, shown in the Audio Conferencing coordinates, can be configured to use:

-   The tenant-level default.

-   Автоматически назначенный bridge телефонных номеров.

-   Конференции bridge телефонных номеров вручную настроить для каждого пользователя.

User-specific conference bridge phone numbers are typically useful in global or nationwide organizations where users are distributed and must provide local numbers as the default conference bridge phone numbers in their meeting invitations.

Participants joining from different cities or overseas can look up additional numbers configured at the tenant level, but these numbers don’t appear directly in the meeting invitations. Приглашения на собрания укажите ссылку, участники **группы конференц-связи с телефонным номеров** страницу их поиск номера телефона конференции bridge, наиболее близкого к их расположения.

Можно также настроить как непроверенных вызывающих обрабатываются каждого отдельного Организатор — необходимость Организатор собрания, чтобы начать собрание перед не прошедшим проверку подлинности абонентов может быть присоединен или разрешить непроверенный абонентов начало собрания .

Также можно применить дополнительные конфигурации для каждого пользователя для управления использование бесплатных конференции bridge номера телефонов и подключение по телефонной линии из конференции.

> [!NOTE]
> Сейчас эти элементы управления затратами доступны только клиентам с предварительной версией. Регистрация организации в программу предварительного просмотра с службе https://www.skypepreview.com.

С помощью этих элементов управления можно ли организаторам собрания можно задать номера телефона bridge бесплатный номер конференции организованы их и ли участники могут выполнять звонки из собрания, которые они организованы. Уровень контроля подключение по телефонной линии диапазонов из полностью прекращения обратным звонком, к только что исходящие звонки в внутренних цифры, позволяя обратным звонком для внутренних и международных номеров.

<br>
|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|Точки принятия решений|<ul><li>Решите, требуется ли вашей организации уведомления о входе и выходе и — в этом случае — тип уведомления для реализации (мелодии, номер телефона или записанных имен).</li><li>Решите, длину ПИН-кода конференц-связи звук, требованиям безопасности предприятия.</li><li>Решите, требуется управлять коммуникаций пользователя, связанные со службой аудиоконференции вашей организации.</li><li>Определите телефонные номера для моста конференций, назначаемые каждому из организаторов собрания.</li><li>Решите, будет ли некоторые организаторам собрания необходимых бесплатный номер конференции bridge телефонных номеров для свои собрания.</li><li>Решите, нужно ли некоторые организаторам собрания не прошедшим проверку подлинности Звонящий начало собрания.</li><li>Решите, должны ли некоторые организаторам собрания конференции по телефону должно управляться.</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|Дальнейшие действия|<ul><li>Подробно задокументируйте параметры моста конференций (уведомления о входе на собрание и выходе из него, длина ПИН-кода, уведомление по электронной почте об изменении конфигурации).</li><li>Документ конференции bridge телефонных номеров, назначенный для каждой Организатор собрания и соответствующий параметр для управления политикой для вызывающих объектов, не прошедшим проверку подлинности и бесплатный номер и абонентской группы элементов управления.</li></ul>|

> [!TIP]
> Параметры bridge конференции можно документированы как показано в следующем примере.
>|         |         |
>|---------|---------|
>|Включить уведомления о входе на собрание и выходе из него|Включено|
>|Тип уведомления при входе и выходе|Мелодии|
>|Просить абонентов произносить свое имя перед присоединением к собранию|Отключено|
>|Длина ПИН-кода|5|
>|Автоматически отправлять электронные письма пользователям в случае изменения параметров набора номера|Отключено|

<br>
> [!TIP]
> Вы можете документировать параметры назначения конференции bridge списка для пользователей аудиоконференции с помощью в следующем примере.
>|Пользователь  |Офис  |Платный номер по умолчанию  |Бесплатный номер по умолчанию  |Разрешить бесплатные номера  |Непроверенные вызывающие абоненты минуют зал ожидания  |Обратный звонок из конференции  |
>|---------|---------|---------|---------|---------|---------|---------|
>|Adele Vance|One Epping Road|Подлежит добавлению|Подлежит добавлению|Да|Включено|Международный и внутренний|
>|Alex Wilber|One Epping Road|Подлежит добавлению|Подлежит добавлению|Нет|Отключено|Запрещено|
>|Ben Walters|One Epping Road|Подлежит добавлению|Подлежит добавлению|Нет|Отключено|Запрещено|
>|Christie Cline|One Marina Boulevard|Подлежит добавлению|Подлежит добавлению|Да|Отключено|Внутренний|
>|Debra Berger|One Marina Boulevard|Подлежит добавлению|Подлежит добавлению|Да|Включено|Внутренний|
>|Lee Gu|One Marina Boulevard|Подлежит добавлению|Подлежит добавлению|Да|Включено|Внутренний|
>|Emily Braun|32 London Bridge Street|Определите, нужд|Подлежит добавлению|Да|Включено|Запрещено|
>|Lidia Holloway|32 London Bridge Street|Определите, нужд|Подлежит добавлению|Да|Отключено|Запрещено|
>|Lahr Луис|32 London Bridge Street|Определите, нужд|Подлежит добавлению|Да|Отключено|Запрещено|
>|Marcel Beauchamp|39 quai du Président Roosevelt|Подлежит добавлению|Подлежит добавлению|Нет|Отключено|Внутренний|
>|Rachelle Cormier|39 quai du Président Roosevelt|Подлежит добавлению|Подлежит добавлению|Да|Включено|Международный и внутренний|
>|Isabell Potvin|39 quai du Président Roosevelt|Подлежит добавлению|Подлежит добавлению|Нет|Отключено|Внутренний|

<!--ENDOFSECTION-->

## <a name="manage-cloud-voice-telephone-numbers"></a>Управление облачных голосовой связи телефонных номеров

Для реализации звук конференц-связи Вы можете получить новый телефонных номеров или передачи/порт существующих телефонных номеров.

Пользователи для набора телефонных номеров способ их знаете, — например пропуск коды области для звонков, пропуск код страны для внутренних звонков или даже с помощью короткий цифры набор номера при выполнении конференции обратным звонком — можно настроить настраиваемого абонентской группы и назначьте ей пользователей.

## <a name="acquire-new-telephone-numbers"></a>Получить новый телефонных номеров

Существует два типа телефонных номеров в рамках решений голосовой связи Microsoft cloud::

-   Номера подписчика (пользователь), которые можно назначить пользователям в вашей организации.

-   Номера службы, доступен в качестве международную и номера бесплатных службы, которые имеют выше емкости возможность выполнения одновременных звонков, чем номера и могут быть назначены службы, такие как аудио конференц-связи, автосекретари или позвонить очереди.

Дополнительные сведения о следующих типах телефонных номеров просмотрите [различные виды телефонных номеров, используемый для вызова планов](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/different-kinds-of-phone-numbers-used-for-calling-plans).

Общее число телефона, от которых зависит номеров, которые вы можете получить типы номер телефона и число лицензий иметь куплены и назначить для пользователей.

Когда речь идет о номеров службы, необходимо тщательно спланировать внедрения звук конференц-связи. Определите, могут ли вашей организации требуется выделенный конференции bridge номеров телефонов в противном случае вашей организации можно использовать общую конференции bridge телефонных номеров.

Дополнительные сведения о общее число телефонных номеров, которую можно получить в разделе [Сколько номеров телефонов можно получить?](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/how-many-phone-numbers-can-you-get)

<br>
|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|Точки принятия решений|<ul><li>Выбор расположения пользователя или офисов, где будет использоваться новые телефонных номеров в корпорации Майкрософт.</li><li>Выбор типа телефонных номеров, которые необходимо получить от корпорации Майкрософт.</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|Дальнейшие действия|<ul><li>Документирование пользователя расположения или офисов, где будет использоваться новые телефонных номеров в корпорации Майкрософт.</li><li>Тип телефонных номеров, которые необходимо получить из Microsoft документа.</li></ul>|

## <a name="transfer-existing-telephone-numbers"></a>Перенос существующих телефонных номеров

Если ваша организация хочет для передачи (порт) существующих телефонных номеров в корпорацию Майкрософт, это можно сделать путем отправки запроса заказа порта в корпорацию Майкрософт.

Можно перенести все вашей существующих телефонных номеров за один раз (полный порт) и — в некоторых странах, можно перенести подмножество существующих телефонных номеров (частичное порт). Частичный порт можно использовать в тех случаях, где только что необходимо переместить вашей bridge конференц-связи к службе конференц-связи аудио.

Только один порт порядке можно перенести телефонных номеров к типу единый телефонный номер. Если требуется перенести некоторые вашей телефонных номеров в качестве номера и некоторыми номеров службы, мы рекомендуем сначала выполнить передачу в корпорацию Майкрософт, а затем выполнить преобразование, как только номера в элементе управления корпорации Майкрософт.

В качестве альтернативы поддерживается частичное порт, вы можете обратиться несколько запросов на порт, один порт запроса за раз. Тем не менее этот альтернативный подход будет продолжить контракта с поставщиком услуг существующей области телекоммуникационных услуг.

Телефонных номеров перенос сложных раздел и требует тщательного планирования, координация и соответствующим образом управление ожидания заинтересованных лиц. Для получения дополнительных сведений обратитесь к следующим статьям:

-   [Перенос номеров телефонов в Office 365](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/transfer-phone-numbers-to-office-365)

-   [Transferring phone numbers common questions](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/transferring-phone-numbers-common-questions)

<br>
|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|Точки принятия решений|<ul><li>Выбор расположения пользователя или офисов, где существующих телефонных номеров могут передаваться в корпорацию Майкрософт.</li><li>Выбор типа телефонных номеров для передаваться в корпорацию Майкрософт.</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|Дальнейшие действия|<ul><li>Документирование пользователя расположения или офисов, где существующих телефонных номеров могут передаваться в корпорацию Майкрософт.</li><li>Тип телефонных номеров для передаваться в корпорацию Майкрософт документа.</li></ul>|

<!--ENDOFSECTION-->

## <a name="dial-plans"></a>Абонентские группы

Абонентская группа в компоненте телефонной системой Office 365 — это набор правил нормализации, которое переводит набора телефонных номеров в альтернативный формат (обычно формат E.164) для маршрутизации вызовов и проверка подлинности вызовов. Служба конференц-связи звук использует те же возможности, используемые с телефонной системой для перевода набранного номера телефонов в сценариях конференции по телефону (например, пригласить участников через PSTN и снова, вызова функции «позвонить мне»).

В компоненте телефонной системой Office 365 существует два типа абонентских групп:

-   **Службы единой системы обмена сообщениями:** Это значение по умолчанию абонентской группы, которая применяется для пользователей на основе Office 365 использования расположения и его нельзя изменить.

-   **Клиента абонентская группа:** Это настраиваемый абонентской группы клиента, который разделить на два типа:

    -   **Глобального клиента абонентской группы:** Единой системы обмена сообщениями, которое применяется ко всем пользователям в клиента.

    -   **Абонентской группы пользователей клиента:** Единой системы обмена сообщениями, которое применяется только к определенным пользователям.

Эффективный абонентскую группу назначены пользователям представляет собой комбинацию абонентской службы (на основе пользователя Office 365 использования местоположения) и клиента абонентская группа (может быть глобального клиента абонентской группы или абонентской группы пользователей клиента).

![Таблице показаны три сочетания службы и клиента абонентские.] (media/audio_conferencing_image8.png "Таблице показаны три сочетания службы и клиента абонентские.")

> [!Important]
> В каждой абонентской группы клиента; может иметь длину не более 25 правил нормализации Таким образом, важно Избегайте дублирования правил нормализации, которые уже доступны в рамках службы абонентская группа.

Чтобы узнать больше о абонентских групп, обратитесь к разделу [Каковы абонентских групп?](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/what-are-dial-plans)

<br>
|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|Точки принятия решений|<ul><li>Решите, требуется ли вашей организации настраиваемого абонентских групп (бизнес-требований, требований к внедрения и т.д.).</li><li>Если возможно, определите область действия для абонентской группы клиента (на уровне клиента или отдельных пользователей), руководствуясь требованиями к настраиваемым абонентским группам.</li><li>Если это возможно, Выбор клиента абонентские группы, которые будут созданы для поддержки пользователя расположения или офисов в области для реализации облачных голосовой связи.</li><li>Если это возможно, Выбор пользователей, которые требуют настраиваемого абонентской группы и абонентской клиента для назначения для каждого пользователя.</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|Дальнейшие действия|<ul><li>Документа настраиваемой абонентских групп и правила нормализации связанного должен быть настроен как часть своей реализации облачных голосовой связи.</li><li>Документа пользователям назначить абонентской группы настраиваемых и абонентской клиента для назначения для каждого пользователя.</li></ul>|

> [!TIP]
> Если это применимо в проект, чтобы задокументировать конфигурации плана удаленного клиента можно использовать следующий шаблон.
>|Имя абонентской группы клиента<br>_Описание_  |Имя правил нормализации<br>_Описание_  |Шаблон<br>Преобразование<br>IsInternalExtension  |
>|---------|---------|---------|
>|**AU-NSW-NorthRyde-OER**<br>_Абонентская группа One Epping Road North Ryde, NSW, AU_|**AU-NSW-NorthRyde-OER-Internal**<br>_Внутренний номер (x7000–x7999) для офиса One Epping Road, North Ryde, NSW, Австралия_|^(7\d{3})$<br>+6125550$1<br>True|
>||**AU-NSW-Local**<br>_Нормализация местного номера для NSW, Австралия_|^([2-9]\d{7})$<br>+612$1<br>False|
>||**AU-TollFree**<br>_Нормализация бесплатного номера для Австралии_|^(1[38]\d{4,8})\d*$<br>+61$1<br>False|
>||**AU-Service**<br>_Нормализация номера службы для Австралии_|^(000\|1[0125]\d{1,8})$<br>$1<br>False|
>|**SG-Singapore-OMB**<br>_OMB в Сингапуре, абонентская группа SG_|**SG-OMB-Internal**<br>_Внутренний номер (x8000 â €«x 8999) для системы office OMB, Сингапур_|^(8\d{3})$<br>+656888$1<br>True|
>||**SG-TollFree**<br>_Нормализация бесплатного номера для Сингапура_|^(1?800\d{7})\d*$<br>+65$1<br>False|
>||**SG-Service**<br>_Нормализация номера службы для Сингапура_|^(1\d{3,4}\|9\d{2})$<br>$1<br>False|
>|**FR-Paris-Issy-39qdPR**<br>_Абонентская группа 39 quai du Président Roosevelt Issy-les-Moulineaux, Франция_|**FR-39qdPR-Internal**<br>_Внутренний номер (€ â x7000 «x 7999) для 39 office Рузвельта Président du quai, Issy-les-Moulineaux, Франция_|^(7\d{3})$<br>+3319999$1<br>True|
>||**FR-TollFree**<br>_Нормализация бесплатного номера для Франции_|^0?(80\d{7})\d*$<br>+33$1<br>False|
>||**FR-Service**<br>_Нормализация номера службы для Франции_|^(1\d{1,2}\|11[68]\d{3}\|10\d{2}\|3\d{3})$<br>$1<br>False|

<br>
> [!TIP]
> Приведенный ниже пример шаблона можно использовать для документирования назначений абонентской группы в вашем проекте.
>|Пользователь  |Офис  |Тип абонентской группы  |Имя абонентской группы  |
>|---------|---------|---------|---------|
>|Adele Vance|One Epping Road|Абонентская группа клиента|AU-NSW-NorthRyde-OER|
>|Alex Wilber|One Epping Road|Абонентская группа клиента|AU-NSW-NorthRyde-OER|
>|Ben Walters|One Epping Road|Абонентская группа клиента|AU-NSW-NorthRyde-OER|
>|Christie Cline|One Marina Boulevard|Абонентская группа клиента|SG-Singapore-OMB|
>|Debra Berger|One Marina Boulevard|Абонентская группа клиента|SG-Singapore-OMB|
>|Lee Gu|One Marina Boulevard|Абонентская группа клиента|SG-Singapore-OMB|
>|Emily Braun|32 London Bridge Street|Служебная абонентская группа|Н/Д|
>|Lidia Holloway|32 London Bridge Street|Служебная абонентская группа|Н/Д|
>|Lahr Луис|32 London Bridge Street|Служебная абонентская группа|Н/Д|
>|Marcel Beauchamp|39 quai du Président Roosevelt|Абонентская группа клиента|FR-Paris-Issy-30qdPR|
>|Rachelle Cormier|39 quai du Président Roosevelt|Абонентская группа клиента|FR-Paris-Issy-30qdPR|
>|Isabell Potvin|39 quai du Président Roosevelt|Абонентская группа клиента|FR-Paris-Issy-30qdPR|

<!--ENDOFSECTION-->

## <a name="document-service-decisions"></a>Решения службы документов 

Используйте сведения из предыдущих разделах этой статьи для документирования свои решения службы. Как правило эта документация содержит следующие разделы:

-   Список расположений для использования службы Аудиоконференций

-   Список назначения лицензий для организаторов собраний Аудиоконференций

-   Цифры для планирования Кредитов на связь

-   Сведения о мосте конференций

-   Параметры моста конференций

-   Назначенные параметры моста конференций

-   Планы приобретения раздела номера телефонов

-   Абонентские группы клиента

-   Назначенные абонентские группы

<!--ENDOFSECTION-->