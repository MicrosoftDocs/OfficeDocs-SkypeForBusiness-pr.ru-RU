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
description: 'Сведения о том, как включить или отключить в Skype отправку сообщений пользователям при изменении таких настроек, как ПИН-код или номер по умолчанию для конференц-связи в Microsoft Teams. '
ms.openlocfilehash: 36c7e9dce17de1e6f9bbf8b812d62ddd91bc6ffe
ms.sourcegitcommit: 1807ea5509f8efa6abba8462bce2f3646117e8bf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/10/2020
ms.locfileid: "44691605"
---
# <a name="enable-or-disable-sending-emails-when-audio-conferencing-settings-change-in-microsoft-teams"></a>Включение и отключение отправки сообщений электронной почты при изменении настроек аудиоконференций в Microsoft Teams

Если пользователи активированы для участия в аудиоконференциях, они автоматически получают уведомление по электронной почте. В некоторых случаях потребуется сократить количество уведомлений по электронной почте. Для этого можно отключить отправку сообщений.
  
Если отправка уведомлений по электронной почте отключена, пользователи не будут получать сообщения аудиоконференций, включая сообщения о разрешении/запрете на использование аудиоконференций, а также о сбросе ПИН-кода и изменении идентификатора конференции или телефонного номера для конференц-связи по умолчанию.
  
Ниже приведен пример сообщения, отправляемого пользователям, для которых разрешены аудиоконференции:
  
![Пример сообщения электронной почты для аудиоконференции](media/teams-emails-sent-to-users-when-settings-change-image1.png)
  
## <a name="when-are-emails-being-sent-to-your-users"></a>Когда сообщения отправляются пользователям по электронной почте?

- Когда пользователям в вашей организации разрешены аудиоконференции, им направляется несколько сообщений электронной почты в следующих случаях.
    
  - При назначении пользователям лицензии **аудиоконференций**.
    
  - Сброс ПИН-кода аудиоконференции пользователя вручную.
    
  - Сброс идентификатора конференции пользователя вручную.
    
  - Если удаляется лицензия  **Аудиоконференции**.
    
  - Изменение поставщика услуг аудиоконференций с Майкрософт на другого поставщика или на значение **Нет**.
    
  - Изменение поставщика услуг аудиоконференций на Майкрософт.


## <a name="enable-or-disable-email-from-being-sent-to-users"></a>Включение или отключение отправки сообщения пользователям

Вы можете использовать Microsoft Teams или Windows PowerShell, чтобы включить или отключить отправку сообщения пользователям.

![Значок с логотипом Microsoft Teams](media/teams-logo-30x30.png) **Использование центра администрирования Microsoft Teams**

1. На панели навигации слева перейдите в раздел **Собрания** > **Мосты конференц-связи**. 

2. В верхней части страницы **Мосты конференц-связи** щелкните **Настройки моста**. 

3. В области **Настройки моста** включите или отключите настройку **Автоматически отправлять пользователям электронные письма при изменении их настроек телефонного подключения**.

4. Нажмите кнопку **Сохранить**.

  
> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

**Использование Windows PowerShell**
  
Дополнительные сведения см. в [справочнике по Microsoft Teams PowerShell](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps).

    
## <a name="want-to-know-more-about-windows-powershell"></a>Хотите узнать больше о Windows PowerShell?

Windows PowerShell все о том, как управлять пользователями, а также о том, какие пользователи разрешены или не разрешены. С Windows PowerShell вы можете управлять Microsoft 365 или Office 365, используя единый пункт администрирования, который упростит выполнение ваших повседневных задач. Чтобы начать работу с Windows PowerShell, см. указанные здесь разделы.
    
  - [Шесть причин использовать Windows PowerShell для управления Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Лучшие способы управления Office 365 с помощью Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
Дополнительные сведения о Windows PowerShell см. в [справочнике по Microsoft Teams PowerShell](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps).
    
  
## <a name="related-topics"></a>Связанные разделы

[Сообщения электронной почты, отправляемые пользователям при изменении их настроек аудиоконференций](emails-sent-to-users-when-their-settings-change-in-teams.md)

[Отправка пользователю сообщения электронной почты со сведениями об аудиоконференции](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md)


