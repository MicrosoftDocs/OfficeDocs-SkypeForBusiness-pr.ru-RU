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
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- seo-marvel-mar2020
description: 'Узнайте, как включить или отключить отправку электронных писем пользователям Skype при изменениях настроек, таких как изменение пин-кода или изменение номера для телефонной сети по умолчанию в Microsoft Teams. '
ms.openlocfilehash: e1bb6df0a443f01ed3c9bc70d03eedc05f217ce4
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51092707"
---
# <a name="enable-or-disable-sending-emails-when-audio-conferencing-settings-change-in-microsoft-teams"></a>Включение и отключение отправки сообщений электронной почты при изменении настроек аудиоконференций в Microsoft Teams

Пользователи автоматически получают уведомления по электронной почте, если они активированы для аудиоконференций. Однако иногда вам может потребоваться уменьшить количество сообщений электронной почты, отправленных пользователям Microsoft Teams. В этом случае можно отключить функцию отправки сообщений по электронной почте.
  
Если отключить отправку сообщений электронной почты, электронные сообщения для аудиоконференции не будут отправляться пользователям, включая сообщения электронной почты о том, когда пользователи включены или отключены для аудиоконференции, когда сбрасывается ПИН-код, а также когда изменяется код конференции и номер телефона конференц-связи по умолчанию.
  
Вот пример сообщения электронной почты, которое отправляется пользователям, если для них включена аудиоконференция:
  
![Пример сообщения электронной почты для аудиоконференции](media/teams-emails-sent-to-users-when-settings-change-image1.png)
  
## <a name="when-are-emails-being-sent-to-your-users"></a>Когда пользователи получают уведомления по электронной почте?

- После включения аудиоконференции пользователям в организации отправляется несколько сообщений электронной почты.
    
  - При назначении пользователям лицензии **аудиоконференций**.
    
  - При сбросе ПИН-кода аудиоконференции пользователя вручную.
    
  - Выполнение сброса идентификатора конференции пользователя вручную.
    
  - Если удаляется лицензия  **Аудиоконференции**.
    
  - При смене поставщика услуг аудиоконференций для пользователя с Microsoft на другого поставщика или **"Нет".**
    
  - При смене поставщика услуг аудиоконференций пользователя на Майкрософт.


## <a name="enable-or-disable-email-from-being-sent-to-users"></a>Включить или отключить отправку электронной почты пользователям

Вы можете использовать Microsoft Teams или Windows PowerShell, чтобы включить или отключить электронную почту, отправленную пользователям.

![Значок с логотипом Microsoft Teams](media/teams-logo-30x30.png) **Использование центра администрирования Microsoft Teams**

1. На панели навигации слева перейдите в раздел **Собрания** > **Мосты конференц-связи**. 

2. В верхней части страницы **"Мосты** конференций" щелкните **"Параметры моста".** 

3. В области **параметров моста** включите или отключите автоматическое отправку электронных писем пользователям в случае изменения настроек телефонного **дозвона.**

4. Нажмите кнопку **Сохранить**.

  
> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

**Использование Windows PowerShell**
  
Дополнительные [сведения см. в справочнике по Microsoft Teams PowerShell.](/powershell/module/teams/?view=teams-ps)

    
## <a name="want-to-know-more-about-windows-powershell"></a>Хотите узнать больше о Windows PowerShell?

Windows PowerShell is all about managing users and what users are allowed or not allowed to do. С Windows PowerShell вы можете управлять Microsoft 365 или Office 365, используя единый пункт администрирования, который упростит выполнение ваших повседневных задач. Для начала работы с Windows PowerShell ознакомьтесь с приведенными ниже разделами.
    
  - [Шесть причин использовать Windows PowerShell для управления Office 365](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
  - [Лучшие способы управления Office 365 с помощью Windows PowerShell](/previous-versions//dn568025(v=technet.10))
    
Дополнительные сведения о Windows PowerShell см. в [справочнике по Microsoft Teams PowerShell](/powershell/module/teams/?view=teams-ps).
    
  
## <a name="related-topics"></a>Связанные разделы

[Сообщения электронной почты, отправленные пользователям при изменении параметров аудиоконференции](emails-sent-to-users-when-their-settings-change-in-teams.md)

[Отправка пользователю сообщения электронной почты со сведениями об аудиоконференции](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md)