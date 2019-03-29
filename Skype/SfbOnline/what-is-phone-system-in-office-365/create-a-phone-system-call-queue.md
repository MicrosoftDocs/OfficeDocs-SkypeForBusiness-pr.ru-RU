---
title: Создание очереди звонков в телефонной системе
author: Jambirk
ms.author: jambirk
manager: serdars
ms.reviewer: phans, wasseemh
ms.topic: article
ms.assetid: 67ccda94-1210-43fb-a25b-7b9785f8a061
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: ms.teamsadmincenter.callqueues.overview
ms.custom:
- Phone System
description: 'Узнайте о том, как настроить телефонную систему для работы с очередью вызовов Office 365 (Cloud PBX), позволяющей использовать корпоративное приветствие, музыкальную заставку при удержании вызова и функцию переадресации вызовов операторам, доступным в списках распределения и группах безопасности. Помимо этого, вы можете получить информацию о том, как настроить максимальный размер очереди, тайм-аут и параметры обработки вызовов. '
ms.openlocfilehash: c76f7e00c8c12e79c0dc333e05d4ccb0ca75266a
ms.sourcegitcommit: f9a9a7e4b7f6c821a3372f7dcb966a8a6d458752
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/28/2019
ms.locfileid: "30952354"
---
# <a name="create-a-phone-system-call-queue"></a>Создание очереди звонков в телефонной системе

Phone System call queues include greetings that are used when someone calls in to a phone number for your organization, the ability to automatically put the calls on hold, and the ability to search for the next available call agent to handle the call while the people who call are listening to music on hold. You can create single or multiple call queues for your organization.
  
Очереди вызовов в телефонной системе позволяют использовать следующие функции.
  
- Приветствие звонящим в организацию пользователям.
- Воспроизведение музыки во время удержания звонка.
- Перенаправление звонков вызов агентам в списки рассылки с включенной поддержкой почты и группы безопасности.
- Отображение параметров максимальный размер очереди вызовов, время ожидания и параметрах управления звонками.

При получении звонка номер телефона, настроенный с помощью вызова очередь они будут прослушать приветствия (Если какие-либо настройки), а затем они будут помещены в очередь и дождитесь следующего агента доступные звонок. Вызывающий абонент будет прослушивают музыку, пока они находятся на удержании Ожидание и вызовы будут предложены звонок агентам образом *Первого в, первый выходной параметр* (FIFO).
  
Все звонки в очереди будут распределяться с помощью автосекретаря маршрутизации режиме или режиме последовательного маршрутизации:
  
- С помощью автосекретаря маршрутизации первого звонка в очередь будет звонить все агенты в то же время.
- При последовательной маршрутизации первый вызов в очереди поступает операторам поочередно.

    > [!NOTE]
    > Те операторы, которые находятся **Не в сети**, характеризуют свое присутствие значением **Не беспокоить** или выходят из очереди во избежание поступления к ним вызовов.
  
- Одновременно операторам отправляется только одно уведомление о звонке, находящемся в начале очереди.
- После того, как оператор принимает звонок, всем операторам поступает следующий входящий звонок из очереди.

## <a name="step-1---getting-started"></a>Шаг 1. Начало работы

Перед началом работы с очередями звонков необходимо запомнить следующие моменты.
  
- Your organization must have (at a minimum) an Enterprise E3 plus **Phone System** license or an Enterprise E5 license. The number of **Phone System** user licenses that are assigned affects the number of service numbers that are available to be used for call queues. The number of call queues you can have is dependent on the number of **Phone System** and **Audio Conferencing** licenses that are assigned in your organization. To learn more about licensing, go [here](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).

    > [!NOTE]
    > To redirect calls to people in your organization who are Online, they must have a **Phone System** license and be enabled for Enterprise Voice or have Office 365 Calling Plans. See [Assign Skype for Business and Microsoft Teams licenses](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md). To enable them for Enterprise Voice, you can use Windows PowerShell. For example run:  `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`
  
- Чтобы узнать больше о вызове планы Office 365, обратитесь к разделу [телефонной системой и вызов планов](/microsoftteams/calling-plan-landing-page) и [Вызов планов Office 365](/microsoftteams/calling-plans-for-office-365).

    > [!NOTE]
    > Пользователи размещенных в локальной Lync Server 2010 не поддерживается агентами вызова очереди. 
  
- You can only assign toll and toll-free service phone numbers that you got in the **Skype for Business admin center** or transferred from another service provider to Phone System call queues. To get and use toll-free service numbers, you need to set up Communications Credits.

    > [!NOTE]
    > Номера телефонов пользователей (абонентов) нельзя назначить очередям звонков  можно использовать платные или бесплатные номера телефонов служб. 
  
- При распределении входящие звонки из очереди вызовов телефонной системой этих клиентов поддерживаются для агентов звонка:

  - Клиент Skype для бизнеса для настольных ПК 2016 (32- и 64-разрядные версии)

  - Клиент Lync для настольных ПК 2013 (32- и 64-разрядные версии)

  - All IP phone models supported for Skype for Business Online. See [Getting phones for Skype for Business Online](getting-phones-for-skype-for-business-online/getting-phones-for-skype-for-business-online.md).

  - Клиент Mac Skype для бизнеса (версия 16.8.196 и более поздние) 

  - Клиент Android Skype для бизнеса (версия 6.16.0.9 и более поздние)

  - Клиент iPhone Skype для бизнеса (версия 6.16.0 и более поздние)

  - Клиент iPad Skype для бизнеса (версия 6.16.0 и более поздние)

  - Клиент Microsoft Teams Windows (32- и 64-разрядные версии)

  - Клиент Microsoft Teams Mac

  - Группами Майкрософт для iPhone

  - Приложения для Android группами Майкрософт

## <a name="step-2---getting-or-transferring-toll-or-toll-free-service-phone-numbers"></a>Шаг 2. Получение или перенос платных или бесплатных номеров телефонов служб

Before you can create and set up your call queues, you will need to get or transfer your existing toll or toll-free service numbers. After you get the toll or toll-free service phone numbers, they will show up in **Skype for Business admin center** > **Voice** > **Phone numbers**, and the **Number type** listed will be listed as **Service - Toll-Free**. To get your service numbers, see [Getting service phone numbers for Skype for Business and Microsoft Teams](getting-service-phone-numbers.md) or if you want to transfer and existing service number, see [Transfer phone numbers to Office 365](/microsoftteams/transfer-phone-numbers-to-office-365).
  
> [!NOTE]
> If you are outside the United States, you can't use the Skype for Business admin center to get service numbers. Go to [Manage phone numbers for your organization](/microsoftteams/manage-phone-numbers-for-your-organization) instead to see how to do it from the outside of the United States.
  
## <a name="step-3---create-a-new-call-queue"></a>Шаг 3. Создание новой очереди звонков

 **С помощью центра администрирования группами Майкрософт**

**Центр администрирования группами Майкрософт**, нажмите кнопку ![sfb логотип 30x30.png](../images/sfb-logo-30x30.png) **Портала прежних версий** >  **Перенаправление звонков** > **вызова очередей**, нажмите кнопку **+ Добавить новый**:
  
### <a name="set-the-call-queue-display-name-phone-number-and-domain-if-any"></a>Задайте отображаемое имя очереди, номер телефона и домен (если необходимо)

![Setting up a call queue.](../images/37ecc300-a108-4294-8463-fce570dfce72.png)
***
![Номер 1](../images/sfbcallout1.png)<br/>
**Имя**. Введите описательное имя очереди звонков. Это поле является обязательным и может содержать до 64 знаков, включая пробелы.<br/> Это имя отображается в уведомлении о входящем звонке.
***
![Номер 2](../images/sfbcallout2.png)<br/>**Phone number** Select a service toll or toll-free phone number for the call queue. This is optional. <br/> If there aren't any listed, you need to get service numbers before you can create this call queue. To get your service numbers, see [Getting service phone numbers for Skype for Business and Microsoft Teams](getting-service-phone-numbers.md)
***
![Номер 3](../images/sfbcallout3.png)<br/>**Домен**. Если необходимо, выберите используемый домен Office 365. Это поле доступно только в том случае, если используется несколько доменов Office 365. Если у вас есть несколько доменов, необходимо выбрать нужный в списке. <br/> Например, вы можете использовать домен следующего вида:  _contoso.com or redmond.contoso.com_

### <a name="set-the-greeting-and-music-played-while-on-hold"></a>Настройка приветствия и музыки, воспроизводимой во время удержания

![Setting up a call queue.](../images/1d395a93-7cab-4178-9295-12d5379e20de.png)
  
***
![Номер 1](../images/sfbcallout1.png)<br/>**Greeting** is optional. This is the greeting that is played for people who call in to the call queue number. <br/> Можно загрузить звукового файла (форматы формате WAV, .mp3 или WMA).
***
![Номер 2](../images/sfbcallout2.png)<br/>**Музыка на удержание** Можно либо использовать музыку по умолчанию на удержание, входящие в состав очереди звонок или можно будет загрузить звукового файла в формате WAV, mp3 или WMA форматов для использования в качестве настраиваемого музыки при удержании.

### <a name="select-the-call-distribution-method"></a>Выбор метода распределения вызовов

![Позволяет отобразить доступные методы распределения вызовов](../images/5d249515-d532-4af2-90da-011404028b89.png)
  
***
![Номер 1](../images/sfbcallout1.png)<br/>**Call distribution method** You can choose either **Attendant** or **Serial** for your call queue distribution method. All new and existing call queues will have attendant routing selected by default. To use serial routing, you must explicitly choose the **Serial** routing option in UI and cmdlets. <br/><br/> When serial routing is chosen and the call queue is saved, the calls from the queue will ring your agents one by one, starting from the beginning of the agent list. If an agent dismisses or does not pick up a call, the call will ring the next agent on the list and will try all agents one by one until it is picked up or times out waiting in the queue.   

> [!NOTE]
> При последовательной маршрутизации пропускаются те операторы, которые имеют статус **Не в сети**, характеризуют свою доступность с помощью опции **Не беспокоить** или **отказались** от получения вызовов из этой очереди. 

### <a name="select-an-agent-opt-out-option"></a>Выбор функции отказа от получения вызова оператором

![Позволяет отобразить флажок отказа от получения вызова оператором](../images/99279eff-db61-4acf-9b62-64be84b6414b.png)
  
***
![Номер 1](../images/sfbcallout1.png)<br/>**Функция отказа от получения вызова оператором**. Операторам очереди вызовов можно разрешить отказываться от приема вызовов из определенной очереди, выбрав **Функцию отказа от получения вызова оператором**.  <br/> Enabling this option allows all agents in this queue to start or stop receiving call from this call queue at will. You can revoke the agent opt-out privilege at any time by clearing the check box, causing agents to become automatically opted in for this queue again (the default setting for all agents).  <br/><br/> Для доступа к функции отказа операторы могут выполнить следующие действия.
 1. Открыть секцию  **Параметры** на своем рабочем столе клиента Skype для бизнеса. 
 2. На вкладке **Переадресация вызовов** нажать на ссылку **Изменить параметры при подключении к сети** .
 3. На странице пользовательских параметров нажать на кнопку **Очереди вызовов**, а затем — снять  флажки для всех очередей, прием вызовов из которых следует отключить.

    > [!NOTE] 
    > Операторы, использующие клиент Mac, мобильный клиент или клиент Lync 2013, а также локальные пользователи Hybrid Voice, пользующиеся сервером Skype для бизнеса 2015, могут перейти к [https://aka.ms/cqsettings](https://aka.ms/cqsettings) для доступа к функции отказа от приема вызовов.

### <a name="add-call-agents-to-a-call-queue"></a>Добавление операторов в очередь звонков

![Set up call queues.](../images/skype-for-business-add-agents-to-call-queue.png)
  
***
![Номер 1](../images/sfbcallout1.png)<br/><br/>Агенты вызова (200 максимальное) может быть:
* подключенные к сети пользователи, обладающие лицензией на **телефонную систему** и разрешением на использование корпоративной голосовой связи, либо тарифным планом. <br/><br/> **Note:**  To redirect calls to people in your organization who are Online, they must have a **Phone System** license and be enabled for Enterprise Voice or have a Calling Plan. See [Assign Skype for Business and Microsoft Teams licenses](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md). To enable them for Enterprise Voice, you can use Windows PowerShell. For example run:  `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true` <br/><br/>
* Online users with a **Phone System** license and a Calling Plan that are added to an Office 365 Group, a mail-enabled Distribution List, or a Security Group. It might take up to 30 minutes for a new agent added for a distribution list or a security group to start receiving calls from a call queue. A newly created distribution list or security group might take up to 48 hours to become available to be used with call queues. Newly created Office 365 Groups are available almost immediately. <br/> 

  > [!NOTE] 
  > Пользователи размещенных в локальной Lync Server 2010 не поддерживается.

### <a name="set-the-maximum-queue-size-and-maximum-wait-time"></a>Настройка максимального размера и максимального времени ожидания в очереди

![Set up a call queue.](../images/3f018734-16fe-458b-827d-71fc25155cde.png)
  
***
![Номер 1](../images/sfbcallout1.png)<br/><br/>**Maximum calls in the queue** Use this to set the maximum calls that can wait in the queue at the same time. The default is 50, but it can range from 0 to 200.When this limit is reached, the call will be handled in way you have set on the **When the maximum number of calls is reached** setting below.
***
![Номер 2](../images/sfbcallout2.png)<br/><br/>**При достижении максимальное число звонков** Очереди звонок по достижении максимального размера (задается с помощью параметра **Maximum вызывает в очереди** ), можно выбрать, что происходит с новой входящие звонки.
* **Отключить с сигналом занятости**. Звонок отключается.   
* **Переадресация этот вызов** При выборе это будет иметь следующие параметры:
  * **Person in your company** An Online user with a **Phone System** license and be enabled for Enterprise Voice or have a Calling Plan. You can set it up so the person calling in can be sent to voicemail. To do this, select a **Person in your company** and set this person to have their calls forwarded directly to voicemail. <br/> <br/>Дополнительные сведения о лицензировании, необходимые для голосовой почты, см [голосовой почты в облаке](/microsoftteams/set-up-phone-system-voicemail). 

    > [!Note]
    > Пользователи размещенных в локальной Lync Server 2010 не поддерживается.<br/>

  * **Вызов очереди** Вы должны создать другую очередь звонков, но после выполнения, вы можете выбрать очереди вызовов.
  * **Auto Attendant** You must have already created an auto attendant, but after you do, you can select that auto attendant. See [Set up a Phone System auto attendant](set-up-a-phone-system-auto-attendant.md).
***
![Номер 3](../images/sfbcallout3.png)<br/><br/>**Как долго звонок может находиться в очереди**. Вы также можете настроить продолжительность удержания звонка в очереди до того, как истечет время ожидания и этот звонок будет вынужденно переадресован или отключен. Порядок обработки такого звонка задается в параметре **При истечении времени ожидания звонка**. Можно установить время в диапазоне от 0 до 45 минут. <br/><br/> The timeout value can be set in seconds, at 15-second intervals. This allows you to manipulate the call flow with finer granularity. For example, you could specify that any calls that are not answered by an agent within 30 seconds go to a Directory Search Auto Attendant. 

***
![Номер 4](../images/sfbcallout4.png)<br/><br/>**При истечении времени ожидания звонка**. Определяет порядок дальнейшей звонков по истечении времени, заданного в параметре **Как долго звонок может находиться в очереди**:
* **Отключить**. Звонок отключается.   
* **Переадресация этот вызов** При выборе это будет иметь следующие параметры:
  * **Person in your company** An Online user with a **Phone System** license and be enabled for Enterprise Voice or have Calling Plans. You can set it up so the person calling in can be sent to voicemail. To do this, select a **Person in your company** and set this person to have their calls forwarded directly to voicemail. </br><br/>  Дополнительные сведения о лицензировании, необходимые для голосовой почты, см [голосовой почты в облаке](/microsoftteams/set-up-phone-system-voicemail). 

    > [!Note]
    > Пользователи размещенных в локальной Lync Server 2010 не поддерживается.<br/>

  * **Вызов очереди** Вы должны создать другую очередь звонков, но после выполнения, вы можете выбрать очереди вызовов.
  * **Auto Attendant** You must have already created an auto attendant, but after you do, you can select that auto attendant. See [Set up a Phone System auto attendant](set-up-a-phone-system-auto-attendant.md).
   
## <a name="changing-the-users-caller-id-to-be-a-call-queues-phone-number"></a>Замена присвоенного пользователю идентификатора вызывающео абонента на телефонный номер очереди вызовов

Для защиты персональных данных пользователя его идентификатор вызывающего абонента для исходящих вызовов можно заменить на номер очереди вызовов, создав политику использования командлета **New-CallingLineIdentity**.
  
Для этого выполните команду:
  
```
New-CsCallingLineIdentity -Identity "UKSalesQueue" -CallingIdSubstitute "Service" -ServiceNumber 14258828080 -EnableUserOverride $False -Verbose
```

Then apply the policy to the user using the **Grant-CallingLineIdentity** cmdlet. To do this, run:
  
```
Grant-CsCallingLineIdentity -PolicyName UKSalesQueue -Identity "AmosMarble@contoso.com"
```

Дополнительную информацию о внесении изменений в параметры идентификатора вызывающего абонента в организации можно найти [здесь](../what-are-calling-plans-in-office-365/how-can-caller-id-be-used-in-your-organization.md).
  
## <a name="want-to-know-more"></a>Дополнительные сведения

Для создания и настройки очередей звонков также можно использовать Windows PowerShell.
  
### <a name="call-queue-cmdlets"></a>Командлеты для работы с очередями звонков

Далее перечислены командлеты, необходимые для управления очередью звонков.
  
- [New-CsHuntgroup](https://technet.microsoft.com/en-us/library/mt796459.aspx)

- [Set-CsHuntgroup](https://technet.microsoft.com/en-us/library/mt796457.aspx)

- [Get-CsHuntgroup](https://technet.microsoft.com/en-us/library/mt796458.aspx)

- [Remove-CsHuntgroup](https://technet.microsoft.com/en-us/library/mt796456.aspx)

### <a name="more-about-windows-powershell"></a>Дополнительные сведения о Windows PowerShell

- Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:

  - [Введение в Windows PowerShell и Skype для бизнеса Online](https://go.microsoft.com/fwlink/?LinkId=525039)

  - [Шесть причин использовать Windows PowerShell для управления Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)

- Windows PowerShell имеет множество преимуществ в скорости, простоте и эффективности работы по сравнению с использованием только Центра администрирования Office 365, например при внесении изменений для множества пользователей одновременно. Подробнее об этих преимуществах можно узнать в следующих разделах:

  - [Лучшие способы управления Office 365 с помощью Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)

  - [Использование Windows PowerShell для управления Skype для бизнеса Online](https://go.microsoft.com/fwlink/?LinkId=525453)

  - [Использование возможностей Windows PowerShell для выполнения стандартных задач управления средой Skype для бизнеса Online](https://go.microsoft.com/fwlink/?LinkId=525038)

## <a name="related-topics"></a>Связанные разделы
[Возможности телефонной системы в Office 365](/MicrosoftTeams/here-s-what-you-get-with-phone-system)

[Получение номеров телефонов служб для Skype для бизнеса и Microsoft Teams](getting-service-phone-numbers.md)

[Страны и регионы, для которых доступны аудиоконференции и планы звонков](/microsoftteams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans)
