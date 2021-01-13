---
title: Система комнат Skype и федераированные партнеры Skype для бизнеса
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 1cc20323-ecba-4e87-a861-e54193e64cf0
description: В этом разделе вы узнаете, как настроить систему комнат Skype для федераированных партнеров Skype для бизнеса.
ms.openlocfilehash: ac0203479907f830f1bc6cec6831f8804906e669
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49820809"
---
# <a name="skype-room-system-and-skype-for-business-federated-partners"></a>Система комнат Skype и федераированные партнеры Skype для бизнеса
 
В этом разделе вы узнаете, как настроить систему комнат Skype для федераированных партнеров Skype для бизнеса.
  
## <a name="skype-room-system-and-skype-for-business-federated-partners"></a>Система комнат Skype и федераированные партнеры Skype для бизнеса

Система комнат Skype использует ссылку "Присоединиться к собранию Skype для бизнеса" в календарном запросе на собрание. Ссылка на присоединиться обычно находится в теле запроса на собрание. Однако система комнат Skype зависит от того, присутствует ли эта ссылка в свойствах MAPI сообщения. When this meeting request is sent to remote organizations (Skype for Business federated partners), by default the remote organization's Skype Room System will not show the meeting join link on the calendar. Пользователи Outlook в удаленной организации не смогут присоединиться к собранию Skype для бизнеса, щелкнув правой кнопкой мыши элемент календаря или из напоминания о собрании. Они должны открыть приглашение на собрание и щелкнуть "Присоединиться к собранию Skype для бизнеса" в тексте сообщения. 
  
Причина этого ограничения заключается в том, что Outlook и Microsoft Exchange не используют специальный метод для упаковки сведений для отправки сообщений через Интернет. Этот метод, который называется форматом TNEF, по умолчанию отключен для сообщений, отправленных извне из организации Exchange. Чтобы ссылка присоединилась к собранию в удаленной системе комнат Skype, отправляя организация должна включить TNEF с помощью следующей команды:
  
```powershell
New-RemoteDomain -DomainName Contoso.com -Name Contoso
Set-RemoteDomain -Identity Contoso -TNEFEnabled $true
```

После включения формата TNEF для удаленной организации все сообщения, отправленные в организацию через Интернет, отправляются в виде вложения в формате TNEF. При включаемом режиме TNEF при отправлении запроса на собрание Skype для бизнеса федератированному партнеру Skype для бизнеса система комнат Skype сможет отрисовки собрания перейти к собранию Skype для бизнеса, а удаленные пользователи смогут присоединяться к собраниям Skype для бизнеса. 
