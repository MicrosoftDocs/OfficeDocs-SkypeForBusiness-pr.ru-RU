---
title: Параметры электронной почты при изменении параметров аудиоконференции
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 26ea19d3-e420-4fc1-baa3-2692d17e5e1d
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-collaboration
audience: Admin
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- seo-marvel-mar2020
description: 'Узнайте, как включить или отключить отправку Skype пользователям при изменениях параметров, таких как изменение пин-кода или номер для Microsoft Teams. '
ms.openlocfilehash: f81572feb976ab68a6a65631ec772ec4421f2b1e
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/30/2021
ms.locfileid: "58727448"
---
# <a name="enable-or-disable-sending-emails-when-audio-conferencing-settings-change-in-microsoft-teams"></a>Включение и отключение отправки сообщений электронной почты при изменении настроек аудиоконференций в Microsoft Teams

Пользователи автоматически получают уведомления по электронной почте, если они активированы для аудиоконференций. Однако иногда может потребоваться уменьшить количество сообщений электронной почты, отправленных Microsoft Teams пользователям. В этом случае можно отключить функцию отправки сообщений по электронной почте.
  
Если отключить отправку сообщений электронной почты, электронные письма для аудиоконференции не будут отправляться пользователям, включая сообщения о том, когда пользователи включены или отключены для аудиоконференции, при сбросе ПИН-кода, а также при смене кода конференции и номера телефона конференц-связи по умолчанию.
  
Вот пример сообщения электронной почты, которое отправляется пользователям, если для них включена аудиоконференция:
  
![Пример сообщения электронной почты для аудиоконференции.](media/teams-emails-sent-to-users-when-settings-change-image1.png)
  
## <a name="when-are-emails-being-sent-to-your-users"></a>Когда пользователи получают уведомления по электронной почте?

- После включения аудиоконференции пользователям в организации отправляется несколько сообщений электронной почты:
    
  - При назначении пользователям лицензии **аудиоконференций**.
    
  - При сбросе ПИН-кода аудиоконференции пользователя вручную.
    
  - Выполнение сброса идентификатора конференции пользователя вручную.
    
  - Если удаляется лицензия  **Аудиоконференции**.
    
  - При смене поставщика услуг аудиоконференций пользователя с Майкрософт на другого поставщика или **нет**.
    
  - При смене поставщика услуг аудиоконференций пользователя на Майкрософт.


## <a name="enable-or-disable-email-from-being-sent-to-users"></a>Включить или отключить отправку электронной почты пользователям

Вы можете Microsoft Teams или Windows PowerShell, чтобы включить или отключить электронную почту, отправленную пользователям.

![Значок с логотипом Microsoft Teams.](media/teams-logo-30x30.png) **С помощью Центра администрирования Microsoft Teams**

1. На панели навигации слева перейдите в раздел **Собрания** > **Мосты конференц-связи**. 

2. В верхней части страницы **Мосты конференций** щелкните **Параметры моста**. 

3. В области **Параметры моста** включите или отключите параметр Автоматически отправлять сообщения электронной почты пользователям при изменении параметров телефонного **дозвона.**

4. Нажмите кнопку **Сохранить**.

  
> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

**Использование Windows PowerShell**
  
Вы также можете использовать модуль Microsoft Teams PowerShell и выполнить:

```PowerShell
Set-CsOnlineDialInConferencingTenantSettings -AutomaticallySendEmailsToUsers $true|$false
```

С помощью [Set-CsOnlineDialInConferencingTenantSettings](/powershell/module/skype/set-csonlinedialinconferencingtenantsettings) можно управлять другими настройками для организации, включая электронную почту.

Дополнительные сведения см. в Microsoft Teams [PowerShell.](/powershell/module/teams/?view=teams-ps)

    
## <a name="want-to-know-more-about-windows-powershell"></a>Хотите узнать больше о Windows PowerShell?

Windows PowerShell is all about managing users and what users are allowed or not allowed to do. С Windows PowerShell вы можете управлять Microsoft 365 или Office 365 с помощью единого администрирования, который упростит выполнение повседневных задач. Для начала работы с Windows PowerShell ознакомьтесь с приведенными ниже разделами.
    
  - [Шесть причин использовать Windows PowerShell для управления Office 365](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
  - [Лучшие способы управления Office 365 с помощью Windows PowerShell](/previous-versions//dn568025(v=technet.10))
    
Дополнительные сведения о Windows PowerShell см. в [справочнике по Microsoft Teams PowerShell](/powershell/module/teams/?view=teams-ps).
    
  
## <a name="related-topics"></a>Связанные разделы

[Сообщения электронной почты, отправленные пользователям при изменении параметров аудиоконференции](emails-sent-to-users-when-their-settings-change-in-teams.md)

[Отправка пользователю сообщения электронной почты со сведениями об аудиоконференции](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md)
