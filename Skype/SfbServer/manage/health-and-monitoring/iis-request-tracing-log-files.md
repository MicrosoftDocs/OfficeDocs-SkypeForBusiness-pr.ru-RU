---
title: Мониторинг IIS-запросов на отслеживание файлов журналов в Skype для бизнеса Server 2015
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: b6730e92-6d74-4fa7-a83f-50b7bdadbffa
description: Сводка. Сведения о службе мобильности (Mcx) в Skype для бизнеса Server 2015 поддержки устаревших клиентов.
ms.openlocfilehash: 7d0d15b4c3db3d768117d73ed610b38c7a819196
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51118638"
---
# <a name="monitoring-iis-request-tracing-log-files-in-skype-for-business-server-2015"></a>Мониторинг IIS-запросов на отслеживание файлов журналов в Skype для бизнеса Server 2015
 
**Сводка:** Узнайте о службе мобильности (Mcx) в Skype для бизнеса Server 2015, которая поддерживает устаревших клиентов.
  
Этот раздел относится к развертываниям, поддерживающих только клиентов Lync Lync Mobile, и предназначен для службы мобильности (Mcx).

> [!NOTE]
> Поддержка mcX (Mobility Service) для устаревших мобильных клиентов больше недоступна в Skype для бизнеса Server 2019. Все текущие мобильные клиенты Skype для бизнеса уже используют веб-API единой связи (UCWA) для поддержки обмена мгновенными сообщениями, присутствия и контактов. Пользователям с устаревшими клиентами, использующими MCX, потребуется обновиться до текущего клиента.
  
Если включить отслеживание запросов служб интернет-информации (IIS) для службы мобильности Skype для бизнес-серверов (Mcx), созданные файлы журналов могут потреблять до трех гигабайт дискового пространства в день. Ведение журнала трассировки служб IIS включено по умолчанию. Необходимо отслеживать серверы переднего конца, чтобы убедиться, что у них не заканчивается пространство диска. 
  
По умолчанию службы IIS используют для хранения файлов журнала папку %SystemDrive%\inetpub\logs\LogFiles.
  
Чтобы отключить трассировку запросов служб IIS для всего сервера, выполните в командной строке следующую команду:
  
```console
%SystemDrive%\Windows\System32\inetsrv\appcmd set config /section:httpLogging /dontLog:True
```

Сведения о команде **httpLogging см.** в [ссылке на командную ссылку.](/previous-versions/iis/settings-schema/aa347466(v=vs.90))
