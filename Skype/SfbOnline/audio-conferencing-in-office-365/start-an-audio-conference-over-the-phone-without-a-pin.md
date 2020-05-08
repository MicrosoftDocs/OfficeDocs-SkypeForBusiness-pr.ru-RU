---
title: Начало аудиоконференции по телефону без PIN-кода в Skype для бизнеса Online
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: d5b1f775-d7ed-4d30-853a-1d49f81e8fde
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Audio Conferencing
description: 'Узнайте, как разрешить или запретить анонимным абонентам присоединяться к собранию с помощью центра администрирования Skype for Business admin или путем использования сценария PowerShell. '
ms.openlocfilehash: f02d458450f07b64f3daf4d23b1c56aa2bb846a3
ms.sourcegitcommit: 36f7ec432090683aedb77a5bd7856e1b10af2a81
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2020
ms.locfileid: "44163878"
---
# <a name="start-an-audio-conference-over-the-phone-without-a-pin-in-skype-for-business-online"></a>Начало аудиоконференции по телефону без PIN-кода в Skype для бизнеса Online

> [!Note]
> Сведения о начале аудиоконференции без PIN-кода в Microsoft Teams см. в статье [Начало аудиоконференции по телефону без PIN-кода в Microsoft Teams](/MicrosoftTeams/start-an-audio-conference-over-the-phone-without-a-pin-in-teams).

Пользователи, которые подключаются к собранию, могут столкнуться с тем, что они будут храниться в конференц-зале собрания, так как организатор собрания Skype для бизнеса не начал собрание. 
  
If a meeting organizer calls in to the meeting, by default, a PIN is required to start a meeting. You can set it up so that anyone can dial in to a meeting and not be prompted for a PIN to start the meeting. You can use the Skype for Business admin center to enable or disable this setting for a single user.
  
A PIN isn't required for the meeting organizer if someone has started the meeting from the Skype for Business app. A PIN is only required when a meeting organizer joins their meeting over a phone. The PIN for meetings is sent to the audio user when they are assigned the **Audio Conferencing** license and are enabled for Audio Conferencing. See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information.md) and [Emails that are automatically sent to users when their Audio Conferencing settings change](emails-sent-to-users-when-their-settings-change.md).

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="enable-or-disable-anonymous-callers-from-joining-a-meeting"></a>Разрешение и запрет присоединения анонимных абонентов к собранию
    
1. В **центре администрирования Skype для бизнеса**на панели навигации слева перейдите к разделу Пользователи **голосовой конференции** > **Users**. 
    
2. В списке выберите пользователя и на панели действий нажмите кнопку **изменить**. 
    
3. На странице свойств пользователя в разделе **параметры собрания**установите или снимите флажок **Разрешить звонящим, не прошедшим проверку подлинности, первым участникам собрания. В противном случае они будут ждать в зале ожидания, пока пользователь не пройдет проверку подлинности**.
    
4. Нажмите кнопку **Сохранить**. 


    
 ** Использование Windows PowerShell**
  
- Выполните следующее: 
    
  ```PowerShell
  Set-CsOnlineDialInConferencingTenantSettings -AllowPSTNOnlyMeetingsByDefault $true | $false
  ```

## <a name="what-else-should-you-know"></a>Дополнительные сведения

- Если вы хотите сбросить PIN-код, посмотрите ссылку [Сброс ПИН-кода голосовой](reset-the-audio-conferencing-pin.md)связи.
    
- Если анонимный доступ или не требуется ПИН-код для начала собрания, это значение отключено:
    
  - Если собрание еще не началось (в собрании пока нет ни одного участника): абоненту будет предложено выбрать его, если он является организатором. Если он говорит Да, ему будет предложено ввести ПИН-код, и после ввода PIN-кода собрание начнется, и пользователь присоединится к собранию.
    
  - Если собрание уже началось (кто-либо присоединился): абонент не получит сообщения с вопросом, является ли он организатором. Кроме того, PIN-код запрашиваться не будет. Собрание уже началось, и пользователь присоединится к нему.
    
- Если анонимный доступ или не требуется ПИН-код для начала собрания, включается:
    
  - If the meeting hasn't started (there's no one in the meeting yet): A caller won't be prompted if she's the organizer, and she'll never be prompted for the PIN. Because the setting of the organizer is set to off, the meeting will start and the anonymous callers will join the meeting.
    
  - Если собрание уже началось (кто-либо присоединился): абонент не получит сообщения с вопросом, является ли он организатором. Кроме того, PIN-код запрашиваться не будет. Собрание уже началось, и абонент присоединится к нему.
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Сведения по управлению с помощью Windows PowerShell

- Для экономии времени или автоматизации процесса можно воспользоваться командлетом [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688 ).
    
- Когда речь идет о Windows PowerShell, Skype для бизнеса Online — это все, что нужно для управления пользователями и для пользователей, которым разрешено или не разрешено выполнять эти действия. С помощью Windows PowerShell можно управлять Microsoft 365 или Office 365, используя единую точку администрирования, которая позволяет упростить повседневную работу, если у вас есть несколько задач. Чтобы приступить к работе с Windows PowerShell, ознакомьтесь со следующими разделами:
    
  - [Зачем использовать Microsoft 365 или Office 365 PowerShell](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Лучшие способы управления Microsoft 365 и Office 365 с помощью Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- Windows PowerShell обладает многими преимуществами для ускорения, простоты и продуктивности при использовании только в центре администрирования Microsoft 365, например при изменении параметров для нескольких пользователей за один раз. Ознакомьтесь с этими преимуществами в указанных ниже разделах. 
    
  - [Введение в Windows PowerShell и Skype для бизнеса Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
    [Использование Windows PowerShell для управления Skype для бизнеса Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Использование возможностей Windows PowerShell для выполнения стандартных задач управления средой Skype для бизнеса Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > Модуль Windows PowerShell для Skype для бизнеса online позволяет запускать удаленные сеансы Windows PowerShell с подключением к Skype для бизнеса online. Этот модуль для 64-разрядных систем можно загрузить из Центра загрузки Microsoft здесь: [Модуль Windows PowerShell для Skype для бизнеса Online](https://go.microsoft.com/fwlink/?LinkId=294688).
  
## <a name="related-topics"></a>См. также

[Попробуйте или купите голосовую конференцию в Microsoft 365 или Office 365](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
