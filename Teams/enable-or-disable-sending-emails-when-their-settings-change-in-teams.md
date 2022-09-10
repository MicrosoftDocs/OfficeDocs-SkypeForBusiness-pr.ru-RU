---
title: Email параметры при изменении параметров аудиоконференций
ms.author: heidip
author: MicrosoftHeidi
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
description: 'Узнайте, как включить или отключить Отправку сообщений электронной почты пользователям в Microsoft Teams при изменении параметров, таких как изменения контактов или номер конференции по умолчанию в Teams. '
ms.openlocfilehash: a5119d6f612ed083ac4e72ab52f6bb189af4c9d1
ms.sourcegitcommit: 5abfb6f1abe10b6d32cf6eb97a890cf3138ed0e6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/10/2022
ms.locfileid: "67642110"
---
# <a name="enable-or-disable-sending-emails-when-audio-conferencing-settings-change-in-microsoft-teams"></a>Включение и отключение отправки сообщений электронной почты при изменении настроек аудиоконференций в Microsoft Teams

Пользователи автоматически получают уведомления по электронной почте, если они активированы для аудиоконференций. Однако иногда требуется уменьшить количество сообщений электронной почты, отправляемых пользователям Microsoft Teams. В этом случае можно отключить функцию отправки сообщений по электронной почте.
  
Если отключить отправку сообщений электронной почты, сообщения электронной почты аудиоконференций не будут отправляться пользователям, включая сообщения электронной почты о том, когда пользователи включены или отключены для аудиоконференций, при сбросе ПИН-кода и при изменении идентификатора конференции и номера телефона конференции по умолчанию.
  
Ниже приведен пример сообщения электронной почты, которое отправляется пользователям, если они включены для аудиоконференций:
  
![Пример сообщения электронной почты для аудиоконференций.](media/teams-emails-sent-to-users-when-settings-change-image1.png)
  
## <a name="when-are-emails-being-sent-to-your-users"></a>Когда пользователи получают уведомления по электронной почте?

- После включения аудиоконференций пользователям в организации отправляется несколько сообщений электронной почты:

  - При назначении пользователям лицензии **аудиоконференций**.

  - При сбросе ПИН-кода аудиоконференций пользователя вручную.

  - Выполнение сброса идентификатора конференции пользователя вручную.

  - Если удаляется лицензия  **Аудиоконференции**.

  - При изменении поставщика аудиоконференций пользователя с Microsoft на другого поставщика или **none**.

  - При изменении поставщика аудиоконференций пользователя на Microsoft.

## <a name="enable-or-disable-email-from-being-sent-to-users"></a>Включение или отключение отправки электронной почты пользователям

Вы можете использовать Microsoft Teams или Windows PowerShell, чтобы включить или отключить электронную почту, отправленную пользователям.

### <a name="using-the-microsoft-teams-admin-center"></a>С помощью Центра администрирования Microsoft Teams

1. На панели навигации слева перейдите в раздел **Собрания** > **Мосты конференц-связи**.

2. В верхней части страницы **"Мосты** конференций" щелкните **"Параметры моста"**.

3. В области **параметров моста** включите или отключите автоматическую отправку сообщений электронной почты пользователям, если их параметры **телефонного подключения меняются**.

4. Нажмите кнопку **Сохранить**.

> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

### <a name="using-windows-powershell"></a>Использование Windows PowerShell

Вы также можете использовать модуль Microsoft Teams PowerShell и выполнить:

```PowerShell
Set-CsOnlineDialInConferencingTenantSettings -AutomaticallySendEmailsToUsers $true|$false
```

Командлет [Set-CsOnlineDialInConferencingTenantSettings](/powershell/module/skype/set-csonlinedialinconferencingtenantsettings) позволяет управлять другими параметрами организации, включая электронную почту.

Дополнительные сведения см. в справочнике [по Microsoft Teams PowerShell](/powershell/module/teams/?view=teams-ps) .

## <a name="want-to-know-more-about-windows-powershell"></a>Хотите узнать больше о Windows PowerShell?

Windows PowerShell is all about managing users and what users are allowed or not allowed to do. С Windows PowerShell вы можете управлять Microsoft 365 или Office 365 с помощью единой точки администрирования, которая может упростить вашу ежедневную работу при наличии нескольких задач. Для начала работы с Windows PowerShell ознакомьтесь с приведенными ниже разделами.

- [Шесть причин использовать Windows PowerShell для управления Office 365](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)

- [Лучшие способы управления Office 365 с помощью Windows PowerShell](/previous-versions//dn568025(v=technet.10))

Дополнительные сведения о Windows PowerShell см. в [справочнике по Microsoft Teams PowerShell](/powershell/module/teams/?view=teams-ps).

## <a name="related-topics"></a>Связанные разделы

[Сообщения электронной почты, отправляемые пользователям при изменении параметров аудиоконференций](emails-sent-to-users-when-their-settings-change-in-teams.md)

[Отправка пользователю сообщения электронной почты со сведениями об аудиоконференции](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md)
