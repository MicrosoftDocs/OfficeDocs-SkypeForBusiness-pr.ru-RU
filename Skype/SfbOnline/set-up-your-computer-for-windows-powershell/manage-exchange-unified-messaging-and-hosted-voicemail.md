---
title: Управление единой системой обмена сообщениями Exchange и размещенной голосовой почтой
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: 707198df-df85-4833-9c15-aa29b71f085c
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- PowerShell
description: Use PowerShell to manage Exchange Unified Messaging capabilities such as Auto Attendant and Subscriber Access and hosted voicemail in Skype for Business Online.
ms.openlocfilehash: 1a841b377fbc84d85f085dc9d479fa05cc0b2be4
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/06/2021
ms.locfileid: "52238742"
---
# <a name="manage-exchange-unified-messaging-and-hosted-voicemail"></a>Управление единой системой обмена сообщениями Exchange и размещенной голосовой почтой

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

[] Вы можете управлять единой системой обмена сообщениями Exchange и размещенной голосовой почтой в Skype для бизнеса online с помощью набора командлетов.
  
## <a name="manage-exchange-unified-messaging-and-hosted-voice-mail"></a>Управление единой системой обмена сообщениями Exchange и размещенной голосовой почтой

Следующие командлеты можно использовать для управления единой системой обмена сообщениями Exchange и политиками размещенной голосовой почты:
  

| **Командлет**                                                                                                                                                                                                                                                                                                                        | **Описание**                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    |
|:----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|:-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| [Get-CsExUmContact](/powershell/module/skype/Get-CsExUmContact) <br/><br/> [New-CsExUmContact](/powershell/module/skype/New-CsExUmContact) <br/> <br/>[Remove-CsExUmContact](/powershell/module/skype/Remove-CsExUmContact) <br/> <br/>[Set-CsExUmContact](/powershell/module/skype/Set-CsExUmContact) <br/> | Создает объекты контактов, используемые для автосекретаря и служб абонентского доступа, и управляет ими, если единая система обмена сообщениями Exchange является размещенной службой.  <br/><br/> Skype для бизнеса online вместе с единой системой обмена сообщениями Exchange предоставляет несколько возможностей, связанных с голосом, включая автосекретарь и абонентский доступ. Автосекретарь позволяет автоматически отвечать на звонки и перенаправлять их нужному человеку. С помощью абонентского доступа пользователи подключаются к единой системе обмена сообщениями Exchange и извлекают письма, голосовые сообщения, контакты и сведения о календаре.<br/><br/> Если единая система обмена сообщениями Exchange предоставляется как размещенная служба, объекты контактов, используемые для автосекретаря и служб абонентского доступа, нужно создать с помощью Microsoft PowerShell. Эти объекты создаются и управляются с помощью командлетов **CsExUmContact**.<br/> |
| [Get-CSHostedVoicemailPolicy](/powershell/module/skype/Grant-CsHostedVoicemailPolicy) <br/> <br/>[Grant-CSHostedVoicemailPolicy](/powershell/module/skype/Set-CsTenantPublicProvider) <br/>                                                                                                                                                | Управляет политиками размещенной голосовой почты, используемыми в организации. Политики размещенной голосовой почты определяют, как неотвеченные звонки перенаправляются в службу единой системы обмена сообщениями Exchange. Эти политики затрагивают только пользователей, у которых разрешена размещенная голосовая почта единой системы обмена сообщениями Exchange.    <br/><br/> Чтобы проверить, разрешена ли размещенная голосовая почта для пользователя, запустите команду, аналогичную следующей, из приглашения PowerShell.  <br/> \`Get-CsOnlineUser -Identity "kenmyer@litwareinc.com"                                                                                                                                                                                                                                                                                                                                                           |

## <a name="related-topics"></a>Статьи по теме
[Настройка компьютера для управления Skype для бизнеса online с помощью Windows PowerShell](set-up-your-computer-for-windows-powershell.md)

  
