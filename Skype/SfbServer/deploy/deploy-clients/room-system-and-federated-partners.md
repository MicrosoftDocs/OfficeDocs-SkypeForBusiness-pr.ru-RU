---
title: Федеративные партнеры системы комнат Skype и Skype для бизнеса
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 1cc20323-ecba-4e87-a861-e54193e64cf0
description: В этом разделе описывается настройка Системы комнат Skype для федеративных партнеров Skype для бизнеса.
ms.openlocfilehash: d5ee83857aa439791e2a31ef201e0f365dbb8408
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41768722"
---
# <a name="skype-room-system-and-skype-for-business-federated-partners"></a>Федеративные партнеры системы комнат Skype и Skype для бизнеса
 
В этом разделе описывается настройка Системы комнат Skype для федеративных партнеров Skype для бизнеса.
  
## <a name="skype-room-system-and-skype-for-business-federated-partners"></a>Федеративные партнеры системы комнат Skype и Skype для бизнеса

В приглашении на собрание в календаре для системы комнат Skype используется ссылка "присоединиться к собранию Skype для бизнеса". The join link is usually found in the body of a meeting request. Тем не менее, система комнаты Skype зависит от этой ссылки, которая должна быть представлена в свойствах MAPI сообщения. Если это приглашение на собрание будет отправлено в удаленные Организации (Федеративные партнеры Skype для бизнеса), по умолчанию в системе комнаты Skype удаленной организации не отображается ссылка присоединение к собранию в календаре. На самом деле пользователи Outlook в удаленной организации не смогут присоединиться к собранию Skype для бизнеса, щелкнув правой кнопкой мыши элемент календаря или в рамках напоминания о собрании. Они должны открыть приглашение на собрание и щелкнуть присоединиться к собранию Skype для бизнеса в тексте сообщения. 
  
The reason for this limitation is that Outlook and Microsoft Exchange do not use a special method to package information for sending messages across the Internet. This method, referred to as Transport Neutral Encapsulation Format (TNEF), is disabled by default for messages sent externally from an Exchange organization. Для отображения ссылки присоединения к собранию в удаленной системе комнат Skype необходимо включить TNEF с помощью следующей команды:
  
```powershell
New-RemoteDomain -DomainName Contoso.com -Name Contoso
Set-RemoteDomain -Identity Contoso -TNEFEnabled $true
```

Когда метод TNEF включен для удаленной организации, сообщения, отправляемые организации через Интернет, будут представлены в виде вложения в формате TNEF. При включенном формате TNEF при отправке приглашений на собрание Skype для бизнеса для федеративного партнера Skype для бизнеса система комнат Skype сможет отобразить собрание Skype для бизнеса, и удаленные пользователи смогут присоединиться к собраниям Skype для бизнеса. 
