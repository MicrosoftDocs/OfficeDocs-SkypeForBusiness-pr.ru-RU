---
title: Create a Phone System call queue
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: makolomi
ms.topic: article
ms.assetid: 67ccda94-1210-43fb-a25b-7b9785f8a061
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Phone System
- Strat_SB_PSTN
description: 'Learn how to set up phone system for Office 365 (Cloud PBX) call queues to give you an organizational greeting, music on hold, and redirecting calls to call agents in distribution lists and security groups. You can also set the maximum queue size, time out, and call handling options. '
ms.openlocfilehash: 3396d7d56adc6fb8ecd531e17284e48bbee5edbf
ms.sourcegitcommit: a0d3e7a177fcd0667ab0d7d0e904f4053b09a92d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2018
---
# <a name="create-a-phone-system-call-queue"></a>Create a Phone System call queue

Phone System call queues include greetings that are used when someone calls in to a phone number for your organization, the ability to automatically put the calls on hold, and the ability to search for the next available call agent to handle the call while the people who call are listening to music on hold. You can create single or multiple call queues for your organization.
  
Phone System call queues can provide:
  
- Приветствие звонящим в организацию пользователям.
    
- Воспроизведение музыки во время удержания звонка.
    
- Redirecting of calls to call agents in mail-enabled distribution lists and security groups.
    
- Настройка максимального размера времени ожидания и правил обработки звонков для очереди.
    
When someone calls in to a phone number that is set up up with a call queue, they will hear a greeting first (if any is set up), and then they will be put in the queue and wait for the next available call agent. The person calling in will hear music while they are on hold waiting, and the calls will be offered to the call agents in the  *First In, First Out*  (FIFO) manner.
  
All calls waiting in the queue will be distributed using an attendant routing mode or serial routing mode:
  
- With attendant routing, the first call in the queue will ring all agents at the same time.
    
- With serial routing, the first call in the queue will ring all call agents one by one.
    
    > [!NOTE]
    > Call agents who are **Offline**, have set their presence to **Do not Disturb,** or have opted out of the call queue won't be called.
  
- Одновременно операторам отправляется только одно уведомление о звонке, находящемся в начале очереди.
    
- После того, как оператор принимает звонок, всем операторам поступает следующий входящий звонок из очереди.
    
## <a name="step-1---getting-started"></a>Шаг 1. Начало работы

Перед началом работы с очередями звонков необходимо запомнить следующие моменты.
  
- Your organization must have (at a minimum) an Enterprise E3 plus **Phone System** license or an Enterprise E5 license. The number of **Phone System** user licenses that are assigned affects the number of service numbers that are available to be used for call queues. The number of call queues you can have is dependent on the number of **Phone System** and **Audio Conferencing** licenses that are assigned in your organization. To learn more about licensing, go [here](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).
    
    > [!NOTE]
    > To redirect calls to people in your organization who are Online, they must have a **Phone System** license and be enabled for Enterprise Voice or have Office 365 Calling Plans. See [Assign Skype for Business and Microsoft Teams licenses](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md). To enable them for Enterprise Voice, you can use Windows PowerShell. For example run:  `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`
  
- To learn more about Office 365 Calling Plans, see [What are Calling Plans in Office 365?](../what-are-calling-plans-in-office-365/what-are-calling-plans-in-office-365.md) and [Calling Plans for Office 365](../skype-for-business-and-microsoft-teams-add-on-licensing/calling-plans-for-office-365.md).
    
    > [!NOTE]
    > Users hosted on-premises using Lync Server 2010 aren't supported as a Call Queue Agents. 
  
- You can only assign toll and toll-free service phone numbers that you got in the **Skype for Business admin center** or transferred from another service provider to Phone System call queues. To get and use toll-free service numbers, you need to set up Communications Credits.
    
    > [!NOTE]
    > Номера телефонов пользователей (абонентов) нельзя назначить очередям звонков  можно использовать платные или бесплатные номера телефонов служб. 
  
- When you are distributing the incoming calls from an Phone System call queue, these clients are supported for call agents:
    
  - Клиент Skype для бизнеса для настольных ПК 2016 (32- и 64-разрядные версии)
    
  - Клиент Lync для настольных ПК 2013 (32- и 64-разрядные версии)
    
  - All IP phone models supported for Skype for Business Online. See [Getting phones for Skype for Business Online](getting-phones-for-skype-for-business-online/getting-phones-for-skype-for-business-online.md).
    
  - Mac Skype for Business Client (version 16.8.196 and later) 
    
  - Android Skype for Business Client (version 6.16.0.9 and later)
    
  - iPhone Skype for Business Client (version 6.16.0 and later)
    
  - iPad Skype for Business Client (version 6.16.0 and later)
    
## <a name="step-2---getting-or-transferring-toll-or-toll-free-service-phone-numbers"></a>Шаг 2. Получение или перенос платных или бесплатных номеров телефонов служб

Before you can create and set up your call queues, you will need to get or transfer your existing toll or toll-free service numbers. After you get the toll or toll-free service phone numbers, they will show up in **Skype for Business admin center** > **Voice** > **Phone numbers**, and the **Number type** listed will be listed as **Service - Toll-Free**. To get your service numbers, see [Getting service phone numbers for Skype for Business and Microsoft Teams](getting-service-phone-numbers.md) or if you want to transfer and existing service number, see [Transfer phone numbers to Office 365](../what-are-calling-plans-in-office-365/transfer-phone-numbers-to-office-365.md).
  
> [!NOTE]
> If you are outside the United States, you can't use the Skype for Business admin center to get service numbers. Go to [Manage phone numbers for your organization](../what-are-calling-plans-in-office-365/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) instead to see how to do it from the outside of the United States.
  
## <a name="step-3---create-a-new-call-queue"></a>Шаг 3. Создание новой очереди звонков

В **Центре администрирования Skype для бизнеса** выберите **Маршрутизация вызовов** > **Очереди звонков** и щелкните **Добавить**:
  
### <a name="set-the-call-queue-display-name-phone-number-and-domain-if-any"></a>Задайте отображаемое имя очереди, номер телефона и домен (если необходимо)

![Setting up a call queue.](../images/37ecc300-a108-4294-8463-fce570dfce72.png)
***
![Number 1](../images/sfbcallout1.png)<br/>
**Имя**. Введите описательное имя очереди звонков. Это поле является обязательным и может содержать до 64 знаков, включая пробелы.<br/> Это имя отображается в уведомлении о входящем звонке.
***
![Number 2](../images/sfbcallout2.png)<br/>**Phone number** Select a service toll or toll-free phone number for the call queue. Это необязательный параметр. <br/> If there aren't any listed, you need to get service numbers before you can create this call queue. To get your service numbers, see [Getting service phone numbers for Skype for Business and Microsoft Teams](getting-service-phone-numbers.md)
***
![Number 3](../images/sfbcallout3.png)<br/>**Домен**. Если необходимо, выберите используемый домен Office 365. Это поле доступно только в том случае, если используется несколько доменов Office 365. Если у вас есть несколько доменов, необходимо выбрать нужный в списке.<br/> Например, вы можете использовать домен следующего вида:  _contoso.com or redmond.contoso.com_
   
### <a name="set-the-greeting-and-music-played-while-on-hold"></a>Настройка приветствия и музыки, воспроизводимой во время удержания

![Setting up a call queue.](../images/1d395a93-7cab-4178-9295-12d5379e20de.png)
  
***
![Number 1](../images/sfbcallout1.png)<br/>**Приветствие**  необязательное поле. This is the greeting that is played for people who call in to the call queue number. <br/> You can upload an audio file (.wav, .mp3, or .wma formats).
***
![Number 2](../images/sfbcallout2.png)<br/>**Music on hold** You can either use the default Music on Hold provided with the call queue, or you can upload an audio file in .wav, mp3, or .wma formats to use as your custom Music on Hold. 
   

### <a name="select-the-call-distribution-method"></a>Select the call distribution method

![Shows the call distribution method options](../images/5d249515-d532-4af2-90da-011404028b89.png)
  
***
![Number 1](../images/sfbcallout1.png)<br/>**Call distribution method** You can choose either **Attendant** or **Serial** for your call queue distribution method. All new and existing call queues will have attendant routing selected by default. To use serial routing, you must explicitly choose the **Serial** routing option in UI and cmdlets. <br/><br/> When serial routing is chosen and the call queue is saved, the calls from the queue will ring your agents one by one, starting from the beginning of the agent list. If an agent dismisses or does not pick up a call, the call will ring the next agent on the list and will try all agents one by one until it is picked up or times out waiting in the queue.  <br/><br/>  **Note:** Serial routing will skip agents who are **Offline**, have set their presence to **Do not Disturb**, or have **opted out** of getting calls from this queue.  
   
### <a name="select-an-agent-opt-out-option"></a>Select an agent opt out option

![Shows the agent opt out check box](../images/99279eff-db61-4acf-9b62-64be84b6414b.png)
  
***
![Number 1](../images/sfbcallout1.png)<br/>**Agent Opt out option** You can choose to allow call queue agents to opt out of taking calls from a particular queue by selecting **Agent Opt out option**.  <br/> Enabling this option allows all agents in this queue to start or stop receiving call from this call queue at will. You can revoke the agent opt-out privilege at any time by clearing the check box, causing agents to become automatically opted in for this queue again (the default setting for all agents).  <br/><br/> To access the opt-out option, agents can do the following:
 1. Open **Options** in their desktop Skype for Business client. 
 2. On the **Call Forwarding** tab, click the **Edit settings online** link.
 3. On the user settings page, click **Call Queues**, and then clear the check boxes for any queues for which they want to opt out.
 
    > [!NOTE] 
    > Agents using Mac, mobile, or Lync 2013 clients, or Hybrid Voice users who are hosted on-premises using Skype for Business 2015 server, can go to [https://aka.ms/cqsettings](https://aka.ms/cqsettings) to access the opt out option.
   
### <a name="add-call-agents-to-a-call-queue"></a>Добавление операторов в очередь звонков

![Set up call queues.](../images/skype-for-business-add-agents-to-call-queue.png)
  
***
![Number 1](../images/sfbcallout1.png)<br/><br/>Call agents (50 maximum) can be:
*    An Online user with a **Phone System** license and enabled for Enterprise Voice or with a Calling Plan. <br/><br/> **Note:**  To redirect calls to people in your organization who are Online, they must have a **Phone System** license and be enabled for Enterprise Voice or have a Calling Plan. See [Assign Skype for Business and Microsoft Teams licenses](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md). To enable them for Enterprise Voice, you can use Windows PowerShell. For example run:  `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true` <br/><br/>
*    Online users with a with a **Phone System** license and a Calling Plan that are added to an Office 365 Group, a mail-enabled Distribution List, or a Security Group. It might take up to 30 minutes for a new agent added for a distribution list or a security group to start receiving calls from a call queue. A newly created distribution list or security group might take up to 48 hours to become available to be used with call queues. Newly created Office 365 Groups are available almost immediately. <br/> 

    > [!NOTE] 
    > Users hosted on-premises using Lync Server 2010 aren't supported.           
   
### <a name="set-the-maximum-queue-size-and-maximum-wait-time"></a>Настройка максимального размера и максимального времени ожидания в очереди

![Set up a call queue.](../images/3f018734-16fe-458b-827d-71fc25155cde.png)
  
***
![Number 1](../images/sfbcallout1.png)<br/><br/>**Maximum calls in the queue** Use this to set the maximum calls that can wait in the queue at the same time. The default is 50, but it can range from 0 to 200.When this limit is reached, the call will be handled in way you have set on the **When the maximum number of calls is reached** setting below.
***
![Number 2](../images/sfbcallout2.png)<br/><br/>**When the maximum number of calls is reached** When the call queue reaches its maximum size (set using the **Maximum calls in the queue** setting), you can choose what happens to new incoming calls.
*    **Отключить с сигналом занятости**. Звонок отключается. 
*    **Forward this call to** When you choose this, you will have these options:
     *    **Person in your company** An Online user with a **Phone System** license and be enabled for Enterprise Voice or have a Calling Plan. Ее можно настроить так, что звонки вызывающего абонента будут отправляться в голосовую почту. To do this, select a **Person in your company** and set this person to have their calls forwarded directly to voicemail. <br/> <br/>To learn about licensing required for voicemail, see [Set up Phone System voicemail](../what-is-phone-system-in-office-365/phone-system-voicemail/set-up-phone-system-voicemail.md). 
     
        > [!Note]
        > Users hosted on-premises using Lync Server 2010 aren't supported.<br/>
     
     *    **Call Queue** You must have already created another call queue, but after you do, you can select that call queue.
     *    **Auto Attendant** You must have already created an auto attendant, but after you do, you can select that auto attendant. See [Set up a Phone System auto attendant](set-up-a-phone-system-auto-attendant.md).
***
![Number 3](../images/sfbcallout3.png)<br/><br/>**Как долго звонок может находиться в очереди**. Вы также можете настроить продолжительность удержания звонка в очереди до того, как истечет время ожидания и этот звонок будет вынужденно переадресован или отключен. Порядок обработки такого звонка задается в параметре **При истечении времени ожидания звонка**. Можно установить время в диапазоне от 0 до 45 минут.  <br/><br/> The timeout value can be set in seconds, at 15-second intervals. This allows you to manipulate the call flow with finer granularity. For example, you could specify that any calls that are not answered by an agent within 30 seconds go to a Directory Search Auto Attendant. 

***
![Number 4](../images/sfbcallout4.png)<br/><br/>**При истечении времени ожидания звонка**. Определяет порядок дальнейшей звонков по истечении времени, заданного в параметре **Как долго звонок может находиться в очереди**:   
*    **Отключить**. Звонок отключается. 
*    **Forward this call to** When you choose this, you will have these options:
     *    **Person in your company** An Online user with a **Phone System** license and be enabled for Enterprise Voice or have Calling Plans. Ее можно настроить так, что звонки вызывающего абонента будут отправляться в голосовую почту. To do this, select a **Person in your company** and set this person to have their calls forwarded directly to voicemail. </br><br/>  To learn about licensing required for voicemail, see [Set up Phone System voicemail](../what-is-phone-system-in-office-365/phone-system-voicemail/set-up-phone-system-voicemail.md). 

        > [!Note]
        > Users hosted on-premises using Lync Server 2010 aren't supported.<br/>

     *    **Call Queue** You must have already created another call queue, but after you do, you can select that call queue.
     *    **Auto Attendant** You must have already created an auto attendant, but after you do, you can select that auto attendant. See [Set up a Phone System auto attendant](set-up-a-phone-system-auto-attendant.md).
   
## <a name="changing-the-users-caller-id-to-be-a-call-queues-phone-number"></a>Changing the user's Caller ID to be a call queue's phone number

You can protect a user's identity by changing their caller ID for the outbound calls to a call queue instead by creating a policy using the **New-CallingLineIdentity** cmdlet.
  
Для этого выполните команду:
  
```
New-CsCallingLineIdentity -Identity "UKSalesQueue" -CallingIdSubstitute "Service" -ServiceNumber 14258828080 -EnableUserOverride $False -Verbose
```

Then apply the policy to the user using the **Grant-CallingLineIdentity** cmdlet. Для этого выполните команду:
  
```
Grant-CsCallingLineIdentity -PolicyName UKSalesQueue -Identity "AmosMarble@contoso.com"
```

You can get more information on how to make changes to caller ID settings in your organization [here](../what-are-calling-plans-in-office-365/how-can-caller-id-be-used-in-your-organization.md).
  
## <a name="want-to-know-more"></a>Дополнительные сведения

Для создания и настройки очередей звонков также можно использовать Windows PowerShell.
  
### <a name="call-queue-cmdlets"></a>Командлеты для работы с очередями звонков

Далее перечислены командлеты, необходимые для управления очередью звонков.
  
- [New-CsHuntgroup](https://technet.microsoft.com/en-us/library/mt796459.aspx)
    
- [Set-CsHuntgroup](https://technet.microsoft.com/en-us/library/mt796457.aspx)
    
- [Get-CsHuntgroup](https://technet.microsoft.com/en-us/library/mt796458.aspx)
    
- [Remove-CsHuntgroup](https://technet.microsoft.com/en-us/library/mt796456.aspx)
    
### <a name="more-about-windows-powershell"></a>Дополнительные сведения о Windows PowerShell

- Windows PowerShell, дает возможность управлять пользователями, предоставляя им права на определенные действия. С помощью Windows PowerShell вы можете управлять Office 365 и Skype для бизнеса online, используя единый центр администрирования, который упростит выполнение ваших повседневных задач. Чтобы начать работу с Windows PowerShell, ознакомьтесь с приведенными ниже разделами.
    
  - [Введение в Windows PowerShell и Skype для бизнеса Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Шесть причин использовать Windows PowerShell для управления Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- Windows PowerShell имеет множество преимуществ в скорости, простоте и эффективности работы по сравнению с использованием только Центра администрирования Office 365, например при внесении изменений для множества пользователей одновременно. Подробнее об этих преимуществах можно узнать в следующих разделах:
    
  - [Лучшие способы управления Office 365 с помощью Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [Использование Windows PowerShell для управления Skype для бизнеса Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Использование возможностей Windows PowerShell для выполнения стандартных задач управления средой Skype для бизнеса Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a>See also
[Преимущества телефонной системы в Office 365](here-s-what-you-get-with-phone-system.md)

[Получение номеров телефонов служб для Skype для бизнеса и Microsoft Teams](getting-service-phone-numbers.md)

[Страны и регионы, для которых доступны аудиоконференции и планы звонков](../country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)

  
 