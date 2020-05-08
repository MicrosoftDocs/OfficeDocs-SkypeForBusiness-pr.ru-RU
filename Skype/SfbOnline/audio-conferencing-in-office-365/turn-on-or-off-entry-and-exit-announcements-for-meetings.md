---
title: Включение и отключение уведомлений о входе и выходе из собраний в Skype для бизнеса Online
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: f2c7b5ea-07b6-4b77-8023-bec9596fcc32
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
description: 'Узнайте, как включать и выключать уведомления о входе и выходе из собраний Skype для бизнеса Online с помощью центра администрирования Skype для бизнеса. '
ms.openlocfilehash: 4ce040a329bbdc4095bbda1f964ede970021f80f
ms.sourcegitcommit: 36f7ec432090683aedb77a5bd7856e1b10af2a81
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2020
ms.locfileid: "44163868"
---
# <a name="turn-on-or-off-entry-and-exit-announcements-for-meetings-in-skype-for-business-online"></a>Включение и отключение уведомлений о входе и выходе из собраний в Skype для бизнеса Online

> [!Note]
> Информацию об уведомлениях о входе и выходе в Microsoft Teams см. в статье [Включение или отключение уведомлений о входе и выходе из собраний в Microsoft Teams](/MicrosoftTeams/turn-on-or-off-entry-and-exit-announcements-for-meetings-in-teams).

При настройке голосовой конференции в Microsoft 365 или Office 365 вы получаете мост для голосовой конференц-связи. Мост конференц-связи может содержать один или несколько телефонных номеров, с помощью которых пользователи смогут звонить на собрание Skype для бизнеса. 
  
The conferencing bridge answers a call for a user who is dialing in to a meeting using a phone. The conferencing bridge answers the caller with voice prompts from a conferencing auto attendant, and then, depending on your settings, can play notifications, ask callers to record their name, and set up the PIN security. A PIN is given to a Skype for Business meeting organizer, and it allows them to start a meeting if they can't start the meeting using the Skype for Business app. You can, however, set it so that a PIN isn't required to start a meeting.

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="setting-meeting-join-options"></a>Настройка параметров присоединения к собранию
    
1. В **центре администрирования Skype для бизнеса**на панели навигации слева перейдите к разделу**Настройка моста** **видеоконференций** > Microsoft.
    
2. Under **Meeting join experience**, select or clear **Enable meeting entry and exit notifications to be turned on**. This is selected by default. If you clear it, users who have already joined the meeting won't be notified when someone enters or leaves the meeting.
    
3. В разделе **Тип уведомлений о входе и выходе** выберите **Имена или номера телефонов** или **Гудки**.
    
4. Установите или снимите флажок **задать для вызывающих абонентов запись имени, прежде чем присоединиться к собранию**.
    
5. После внесения изменений нажмите кнопку **Сохранить**.
    

## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Сведения по управлению с помощью Windows PowerShell

- Для экономии времени или автоматизации процесса можно воспользоваться командлетом [Set-csonlinedialinconferencingtenantsettingshttp](https://docs.microsoft.com/powershell/module/skype/set-csonlinedialinconferencingtenantsettings?view=skype-ps) .
    
- Когда речь идет о Windows PowerShell, Skype для бизнеса Online — это все, что нужно для управления пользователями и для пользователей, которым разрешено или не разрешено выполнять эти действия. С помощью Windows PowerShell можно управлять Microsoft 365 или Office 365, используя единую точку администрирования, которая позволяет упростить повседневную работу, если у вас есть несколько задач. Чтобы приступить к работе с Windows PowerShell, ознакомьтесь со следующими разделами:
    
  - [Зачем использовать Microsoft 365 или Office 365 PowerShell](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Лучшие способы управления Microsoft 365 и Office 365 с помощью Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- Windows PowerShell обладает многими преимуществами для ускорения, простоты и продуктивности с помощью центра администрирования Microsoft 365, например при изменении параметров для нескольких пользователей одновременно. Ознакомьтесь с этими преимуществами в указанных ниже разделах. 
    
  - [Введение в Windows PowerShell и Skype для бизнеса Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Использование Windows PowerShell для управления Skype для бизнеса Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Использование возможностей Windows PowerShell для выполнения стандартных задач управления средой Skype для бизнеса Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > Модуль Windows PowerShell для Skype для бизнеса online позволяет запускать удаленные сеансы Windows PowerShell с подключением к Skype для бизнеса online. Этот модуль для 64-разрядных систем можно загрузить из Центра загрузки Microsoft здесь: [Модуль Windows PowerShell для Skype для бизнеса Online](https://go.microsoft.com/fwlink/?LinkId=294688).
  
## <a name="related-topics"></a>Статьи по теме

[Общие вопросы об аудиоконференциях](/MicrosoftTeams/audio-conferencing-common-questions)
