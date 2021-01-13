---
title: Enable or Disable Offline Instant Messaging (IM) in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: c0f44352-fb4a-45d3-85b0-a4320d4b8339
description: Learn to enable or disable Offline Instant Messaging (IM) in Skype for Business Server.
ms.openlocfilehash: 510ebe65e60b9ea12d2f368b0e2d33c705b8d0d6
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49801949"
---
# <a name="enable-or-disable-offline-instant-messaging-im-in-skype-for-business-server"></a>Enable or Disable Offline Instant Messaging (IM) in Skype for Business Server
 
Learn to enable or disable Offline Instant Messaging (IM) in Skype for Business Server.
  
## <a name="enable-offline-instant-messaging-im-in-skype-for-business-server"></a>Enable Offline Instant Messaging (IM) in Skype for Business Server

Автономный обмен мгновенными сообщениями — это клиентская функция, встроенная в клиент Skype для бизнеса (сборка 2016 C2R 16.0.6701.1000 или выше), которая использует веб-службы Exchange (EWS) для отправки сообщений из клиента Skype для бизнеса в почтовый ящик Exchange пользователя. Автономный обмен мгновенными сообщениями использует веб-службы Exchange (EWS) для отправки автономных сообщений из клиента Skype для бизнеса в почтовый ящик получателя. EWS должен быть доступен клиенту Skype для бизнеса, чтобы отправлять автономные сообщения. Дополнительные информацию о планировании обмена мгновенными сообщениями и присутствия см. в этой теме. [](../../plan-your-deployment/instant-messaging-and-presence.md)
  
> [!NOTE]
> Если почтовый ящик пользователя находится в локальной сети Exchange, требуется клиент Skype для бизнеса (сборка 2016 C2R 16.0.6920.1000) 
  
### <a name="to-enable-or-disable-offline-im-in-skype-for-business-server"></a>Чтобы включить или отключить автономный чат в Skype для бизнеса Server

1. Откройте оболочку управления Skype для бизнеса Server.
    
2. Чтобы включить автономный мгновенный доступ, запустите следующую команду:
    
   ```powershell
   Set-CsImConfiguration -EnableOfflineIM $True
   ```

    > [!NOTE]
    > В Skype для бизнеса Server 2015 CU3 для параметра EnableOfflineIM $True по умолчанию. Чтобы отключить, установите для этого значения значение $False. 
  
3. Чтобы подтвердить, что установлена возможность хранения автономных мгновенных мгновенных данных, запустите следующую команду.
    
   ```powershell
   Get-CsImConfiguration
   ```

## <a name="offline-im-integration-with-exchange"></a>Интеграция автономного обмена мгновенными мгновенными данными с Exchange

Автономный обмен мгновенными сообщениями не будет доступен отправителям, если у них есть политика клиента, которая отключает автоматическое сохранение автономных сообщений в папку истории бесед (EnableIMAutoArchiving = $false). Механизм проверки возможности получения сообщений в автономном режиме не существует.
  
Для автономных сообщений, отправленных в пределах той же организации, они будут получены в качестве сообщения электронной  почты с классом сообщений IM.Note.MissedConversation и будут включены в папку "Пропущенная беседа" Outlook, а также историю бесед, которую можно получить на вкладке "Последние списки" или "История бесед" в клиентах Skype для бизнеса.
  
Для автономных сообщений, отправленных из федерационной организации, они будут получены как сообщения электронной почты без im.Note.MisssedConversation и не будут отображены в папках пропущенных бесед или истории бесед. 
  
## <a name="troubleshooting"></a>Устранение неполадок

Существует двухминутный период времени, с того времени, когда автономное сообщение отправляется, когда оно будет обработано и обработано. Если автономные сообщения не могут быть обработаны, они отображаются в следующем каталоге: 
  
  <pre>  %localappdata%\microsoft\office\16.0\lync\SipUserAddress\History Spooler   </pre>

Основной журнал ETL Skype для бизнеса будет содержать сведения об обработке автономных сообщений и является лучшим источником для исследования и устранения неполадок. 
  
> [!NOTE]
> Сообщалось о проблеме, из-за которой автономные сообщения не удалось отправить, а папка "Черновики" заполнялась сообщениями. Это произошло с почтовыми ящиками локального exchange. The issue has been fixed in all C2R channels as of 6/14/2016.  
