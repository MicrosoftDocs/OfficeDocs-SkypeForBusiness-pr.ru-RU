---
title: Вопросы миграции системы комнат Skype
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
ms.assetid: df9f33b6-0360-4354-b651-bd35da533e33
description: В этом разделе вы узнаете, как развернуть систему комнат Skype в среде с несколькими версиями Skype для бизнеса Server и Lync Server.
ms.openlocfilehash: 30b2a4733ea2e2e42b8a879914a2e0e3c4903c8e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49805789"
---
# <a name="skype-room-system-migration-considerations"></a>Вопросы миграции системы комнат Skype
 
В этом разделе вы узнаете, как развернуть систему комнат Skype в среде с несколькими версиями Skype для бизнеса Server и Lync Server.
  
## <a name="migration-considerations"></a>Сведения о выполнении миграции

В этом разделе содержатся рекомендации по развертыванию системы комнат Skype в среде с несколькими пулами, которая включает различные версии Skype для бизнеса Server или Lync Server. 
  
Компонент репликатора пользовательских данных (UR) в Lync Server получает объекты пользователей из Active Directory и помещает их в серверную SQL Server Lync Server. Только URL-адрес в Lync Server 2013 знает об объектах системы комнат Skype. URL-адрес в предыдущих версиях Lync Server и Office Communications Server не определяет атрибуты Active Directory, которые обозначают объекты LRS, и поэтому не знает о них. 
  
If a Skype Room System account tries to sign in to Lync , and performs auto discovery based on SRV record or DNS A record look up, and if those accounts point to a previous version of Lync Server or Office Communications Server, LRS will receive a 404 Not Found response from the legacy pool. Устаревший пул не сможет перенаправлять систему комнат Skype в домашний пул Lync Server 2013. 
  
Эту проблему можно решить с помощью следующих вариантов: 
  
- Указать запись SRV автообнаружена (_sipinternaltls._tcp.contoso.com) на пул Lync Server 2013.
    
- Если первый вариант невозможен, необходимо вручную настроить LRS и предоставить адрес пула Lync Server 2013, непосредственно настроив его в консольном приложении системы комнат Skype. 
    
- Если система комнат Skype развернута за пределами корпоративной сети, а Lync Edge Server развернут и настроен так, чтобы он указывает на устаревший пул или директор, требуется дополнительный сайт edge Server, который указывает на пул Lync Server 2013. Дополнительные сведения о развертывании дополнительного сервера можно найти в документации по развертыванию edge Server. 
    
## <a name="skype-room-system-interoperability-with-a-lync-server-2010-pool"></a>Skype Room System Interoperability with a Lync Server 2010 Pool

Если во время миграции пользователь, который находится в пуле Lync Server 2010, запланировать собрание и пригласить учетную запись системы комнат Skype, клиент системы комнат Skype будет иметь ограниченную функциональность при посещении собрания. 
  
When the Skype Room System client joins a scheduled conference call that has been organized by a user homed on Lync Server 2010, Skype Room System has the following in-meeting limitations: 
  
- Система комнат Skype не может показывать видеогалерею с несколькими представлениями.
    
- Если клиент системы комнат Skype является presenter, он не может применить блокировку видео к участникам.
    
- Система комнат Skype не может показывать разрешение видео 1080p (входящие и исходящие), даже если это разрешает политика Lync Server 2013, так как это возможно из-за следующих проблем: 
    
  - Lync Server 2010 не поддерживает разрешение 1080p.
    
  - Система комнат Skype всегда ограничена политикой конференций организатора для разрешения видео. Поэтому даже если пул Lync 2010 поддерживает разрешение 720p, система комнат Skype не сможет использовать разрешение 720p, если политика организатора не поддерживает его. 
    
- Клиенты Lync 2013 обнаруживают присутствие LRS в комнате для собраний и автоматически от звука, чтобы избежать эха в физической комнате для собраний. Эта функция не работает на собраниях, размещенных в Lync Server 2010.
    
- Существуют ограничения на производительность общего доступа к рабочему столу для собраний, которые находятся в Lync Server 2010.
    
- Пользователи не смогут присоединяться к частным (ограниченным) собраниям, которые будут проводиться в Lync 2010 с помощью системы комнат Skype.
    

