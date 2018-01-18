---
title: "Управление единой системы обмена сообщениями Exchange и размещенной голосовой почты"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 12/15/2017
ms.topic: article
ms.assetid: 707198df-df85-4833-9c15-aa29b71f085c
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
ms.appliesto: Skype for Business
localization_priority: Normal
ROBOTS: None
f1keywords: None
ms.custom: PowerShell
description: Use PowerShell to manage Exchange Unified Messaging capabilities such as Auto Attendant and Subscriber Access and hosted voicemail in Skype for Business Online.
ms.openlocfilehash: a5f358d06ed7c7e805aeffbce6a6898cc2a86b73
ms.sourcegitcommit: 8f2e49bc813125137c90de997fb7a6dd74e6d1d5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/15/2017
---
# <a name="manage-exchange-unified-messaging-and-hosted-voicemail"></a>Управление единой системы обмена сообщениями Exchange и размещенной голосовой почты

[] Вы можете управлять единой системой обмена сообщениями Exchange и размещенной голосовой почтой в Skype для бизнеса online с помощью набора командлетов.
  
## <a name="manage-exchange-unified-messaging-and-hosted-voice-mail"></a>Управление единой системой обмена сообщениями Exchange и размещенной голосовой почтой

Следующие командлеты можно использовать для управления единой системой обмена сообщениями Exchange и политиками размещенной голосовой почты:
  
|**Командлет**|**Описание**|
|:-----|:-----|
|[Get-CsExUmContact](https://go.microsoft.com/fwlink/p/?linkid=849628) <br/><br/> [Новый CsExUmContact](https://go.microsoft.com/fwlink/p/?linkid=849629) <br/> <br/>[Remove-CsExUmContact](https://go.microsoft.com/fwlink/p/?linkid=849630) <br/> <br/>[SET-CsExUmContact](https://go.microsoft.com/fwlink/p/?linkid=849631) <br/> |Создает объекты контактов, используемые для автосекретаря и служб абонентского доступа, и управляет ими, если единая система обмена сообщениями Exchange является размещенной службой.  <br/><br/> Skype для бизнеса online вместе с единой системой обмена сообщениями Exchange предоставляет несколько возможностей, связанных с голосом, включая автосекретарь и абонентский доступ. Автосекретарь позволяет автоматически отвечать на звонки и перенаправлять их нужному человеку. С помощью абонентского доступа пользователи подключаются к единой системе обмена сообщениями Exchange и извлекают письма, голосовые сообщения, контакты и сведения о календаре.<br/><br/> Если единая система обмена сообщениями Exchange предоставляется как размещенная служба, объекты контактов, используемые для автосекретаря и служб абонентского доступа, нужно создать с помощью Microsoft PowerShell. Эти объекты создаются и управляются с помощью командлетов **CsExUmContact**.<br/> |
|[Get-CSHostedVoicemailPolicy](https://go.microsoft.com/fwlink/p/?linkid=849633) <br/> <br/>[GRANT-CSHostedVoicemailPolicy](https://go.microsoft.com/fwlink/p/?linkid=849602) <br/> |Управляет политиками размещенной голосовой почты, используемыми в организации. Политики размещенной голосовой почты определяют, как неотвеченные звонки перенаправляются в службу единой системы обмена сообщениями Exchange. Эти политики затрагивают только пользователей, у которых разрешена размещенная голосовая почта единой системы обмена сообщениями Exchange.  <br/><br/> Чтобы проверить, разрешена ли размещенная голосовая почта для пользователя, запустите команду, аналогичную следующей, из приглашения PowerShell.  <br/> "Get-CsOnlineUser-Identity «kenmyer@litwareinc.com» | SELECT-Object HostedVoiceMail "|
   

## <a name="related-topics"></a>См. также:
[Настройка компьютера для Скайп online управления бизнес-процессов с помощью Windows PowerShell](set-up-your-computer-for-windows-powershell.md)