---
title: Рекомендации по перемещению системы комнат Skype
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: davgroom
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: df9f33b6-0360-4354-b651-bd35da533e33
description: В этой статье рассказывается, как развернуть систему комнат Skype в среде с несколькими версиями Skype для бизнеса Server и Lync Server.
ms.openlocfilehash: 35dd7cff34134791ebaf62bf4d0fcd1cf3b83a4c
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "34293524"
---
# <a name="skype-room-system-migration-considerations"></a>Рекомендации по перемещению системы комнат Skype
 
В этой статье рассказывается, как развернуть систему комнат Skype в среде с несколькими версиями Skype для бизнеса Server и Lync Server.
  
## <a name="migration-considerations"></a>Рекомендации по перемещению

В этом разделе приведены рекомендации по развертыванию системы комнат Skype в среде с несколькими пулами, включающей различные версии Skype для бизнеса Server или Lync Server. 
  
The User Replicator (UR) component in Lync Server gets user objects from Active Directory and places them into the Lync Server back-end SQL Server database. Только UR в Lync Server 2013 знают об объектах системы комнаты Skype. The UR in previous versions of Lync Server and Office Communications Server do not detect the Active Directory attributes that designate LRS objects, and therefore was not aware of them. 
  
Если при попытке входа в приложение Lync с помощью учетной записи в комнате Skype выполняется автоматическое обнаружение на основе записи SRV или DNS A, а если эти учетные записи указывают на предыдущую версию Lync Server или Office Communications Server, ЛРС получит 404  пул устаревших. Пул из старого пула не сможет перенаправлять систему комнат Skype на свой пул Lync Server 2013 Home. 
  
Эту проблему можно решить следующими способами: 
  
- Сделайте так, чтобы запись SRV с автоматическим обнаружением (_sipinternaltls._tcp.contoso.com) указывала на пул Lync Server 2013.
    
- Если первый вариант невозможен, вы должны вручную настроить ЛРС и предоставить адрес пула Lync Server 2013, настроив его непосредственно в консольном приложении системы комнат Skype. 
    
- Если система комнат Skype развернута за пределами корпоративной сети, а граничный сервер Lync развернут и настроен на указание устаревшего пула или режиссера, требуется сайт дополнительного пограничного сервера, который указывает на пул Lync Server 2013. Refer to the Edge Server deployment documentation for more information about deploying a secondary Edge Server. 
    
## <a name="skype-room-system-interoperability-with-a-lync-server-2010-pool"></a>Взаимодействие системы комнаты Skype с использованием пула Lync Server 2010

Если пользователь, размещенный на сервере Lync Server 2010, планирует собрание и приглашает учетную запись системы комнаты для помещения в Skype, то при участии в собрании клиентская система комнаты Skype будет работать с ограниченными возможностями. 
  
Когда клиент системы комнаты Skype присоединяется к запланированным звонкам, которые упорядочены пользователем, настроенным на Lync Server 2010, в системе комнат Skype предусмотрены следующие ограничения для собраний. 
  
- Система комнат Skype не может показать коллекцию видео с несколькими представлениями.
    
- Если в качестве выступающего есть клиент системы комнаты Skype, он не сможет применять блокировку видео для участников.
    
- Система комнат Skype не может отобразить разрешение 1080p (входящее или исходящее), даже если эта возможность разрешена политикой конференц-связи Lync Server 2013, из-за указанных ниже действий. 
    
  - Lync Server 2010 не поддерживает разрешение 1080p.
    
  - Система комнат Skype всегда ограничивается политикой конференц-связи организатора для разрешения видеосигнала. Таким образом, даже если пул Lync 2010 поддерживает разрешение 720p, система комнат Skype не сможет использовать преимущества разрешения 720p, так как она не поддерживается политикой организатора. 
    
- Клиенты Lync 2013 обнаруживают присутствие LRS в комнате переговоров и автоматически отключают звук для себя, чтобы избежать возникновения эха в физической комнате переговоров. Эта функция не работает в собраниях, размещенных в системе Lync Server 2010.
    
- Для собраний, размещенных в системе Lync Server 2010, имеются ограничения по совместному использованию рабочего стола.
    
- Пользователи не смогут присоединиться к частным (ограниченным) собраниям, размещенным в Lync 2010, в системе комнат Skype.
    

