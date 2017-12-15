---
title: "Управление единой системой обмена сообщениями Exchange и размещенной голосовой почтой в Skype для бизнеса Online"
ms.author: tonysmit
author: tonysmit
ms.date: 5/18/2017
ms.audience: Admin
ms.topic: article
ms.prod: office-online-server
localization_priority: Normal
ms.collection: Adm_Skype4B_Online
ms.assetid: 707198df-df85-4833-9c15-aa29b71f085c

description: "Use PowerShell to manage Exchange Unified Messaging capabilities such as Auto Attendant and Subscriber Access and hosted voicemail in Skype for Business Online."
---

# Управление единой системой обмена сообщениями Exchange и размещенной голосовой почтой в Skype для бизнеса Online

Вы можете управлять единой системой обмена сообщениями Exchange и размещенной голосовой почтой в Skype для бизнеса online с помощью набора командлетов.
  
## Управление единой системой обмена сообщениями Exchange и размещенной голосовой почтой

Следующие командлеты можно использовать для управления единой системой обмена сообщениями Exchange и политиками размещенной голосовой почты:
  
|**Командлет**|**Описание**|
|:-----|:-----|
|[Get-CsExUmContact](https://go.microsoft.com/fwlink/p/?linkid=849628) <br/> [New-CsExUmContact](https://go.microsoft.com/fwlink/p/?linkid=849629) <br/> [Remove-CsExUmContact](https://go.microsoft.com/fwlink/p/?linkid=849630) <br/> [Set-CsExUmContact](https://go.microsoft.com/fwlink/p/?linkid=849631) <br/> |Создает объекты контактов, используемые для автосекретаря и служб абонентского доступа, и управляет ими, если единая система обмена сообщениями Exchange является размещенной службой.  <br/> Skype для бизнеса online вместе с единой системой обмена сообщениями Exchange предоставляет несколько возможностей, связанных с голосом, включая автосекретарь и абонентский доступ. Автосекретарь позволяет автоматически отвечать на звонки и перенаправлять их нужному человеку. С помощью абонентского доступа пользователи подключаются к единой системе обмена сообщениями Exchange и извлекают письма, голосовые сообщения, контакты и сведения о календаре.  <br/> Если единая система обмена сообщениями Exchange предоставляется как размещенная служба, объекты контактов, используемые для автосекретаря и служб абонентского доступа, нужно создать с помощью Microsoft PowerShell. Эти объекты создаются и управляются с помощью командлетов **CsExUmContact**. <br/> |
|[Get-CSHostedVoicemailPolicy](https://go.microsoft.com/fwlink/p/?linkid=849633) <br/> [Grant-CSHostedVoicemailPolicy](https://go.microsoft.com/fwlink/p/?linkid=849602) <br/> |Управляет политиками размещенной голосовой почты, используемыми в организации. Политики размещенной голосовой почты определяют, как неотвеченные звонки перенаправляются в службу единой системы обмена сообщениями Exchange. Эти политики затрагивают только пользователей, у которых разрешена размещенная голосовая почта единой системы обмена сообщениями Exchange.  <br/> Чтобы проверить, разрешена ли размещенная голосовая почта для пользователя, запустите команду, аналогичную следующей, из приглашения PowerShell.  <br/> ```Get-CsOnlineUser -Identity "kenmyer@litwareinc.com" | Select-Object HostedVoiceMail```|
   

