---
title: Отслеживание файлов журнала трассировки запросов служб IIS в Skype для бизнеса Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b6730e92-6d74-4fa7-a83f-50b7bdadbffa
description: 'Сводка: сведения о службе Mobility Service (МККС) в Skype для бизнеса Server 2015, поддерживающем устаревшие клиенты.'
ms.openlocfilehash: b8d22146de43f020b62cc249a07990fb9f0cc73c
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "34305663"
---
# <a name="monitoring-iis-request-tracing-log-files-in-skype-for-business-server-2015"></a>Отслеживание файлов журнала трассировки запросов служб IIS в Skype для бизнеса Server 2015
 
**Сводка:** Узнайте о службе Mobility Service (МККС) в Skype для бизнеса Server 2015, поддерживающем устаревшие клиенты.
  
В этом разделе описываются развертывания с поддержкой только для клиентов Lync 2010 Lync Mobile, он предназначен только для службы Mobility Service (Mcx).

> [!NOTE]
> Поддержка МККС (служба Mobility Service) для устаревших мобильных клиентов больше не доступна в Skype для бизнеса Server 2019. На всех текущих мобильных клиентах Skype для бизнеса уже используется веб-API единой системы обмена сообщениями (УКВА) для поддержки мгновенных сообщений, присутствия и контактов. Пользователи с устаревшими клиентами, использующими МККС, должны обновиться до текущего клиента.
  
При включении трассировки запросов служб IIS для службы Mobility Service в Skype для бизнеса Server (МККС) создаваемые файлы журнала могут занимать до 3 ГБ дискового пространства за день. IIS trace logging is enabled by default. Убедитесь, что на серверах переднего плана не осталось свободного места. 
  
По умолчанию службы IIS используют для хранения файлов журнала папку %SystemDrive%\inetpub\logs\LogFiles.
  
Чтобы отключить трассировку запросов служб IIS для всего сервера, выполните в командной строке следующую команду:
  
```
%SystemDrive%\Windows\System32\inetsrv\appcmd set config /section:httpLogging /dontLog:True
```

Подробные сведения о команде **хттплоггинг** можно найти [в справочнике по командам](https://go.microsoft.com/fwlink/p/?linkId=234927).
  

