---
title: Мониторинг IIS запрашивает отслеживание файлов журналов в Skype для бизнеса Server 2015 г.
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: b6730e92-6d74-4fa7-a83f-50b7bdadbffa
description: Сводка. Сведения о службе мобильности (Mcx) в Skype для бизнеса Server 2015 г. для устаревших клиентов.
ms.openlocfilehash: a2331d4f18488171b1862e53f06f4910b463ccb5
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/05/2022
ms.locfileid: "62396561"
---
# <a name="monitoring-iis-request-tracing-log-files-in-skype-for-business-server-2015"></a>Мониторинг IIS запрашивает отслеживание файлов журналов в Skype для бизнеса Server 2015 г.
 
**Сводка:** Узнайте о службе мобильности (Mcx) в Skype для бизнеса Server 2015 г. для устаревших клиентов.
  
Этот раздел относится к развертываниям, поддерживающих только клиентов Lync Lync Mobile, и предназначен для службы мобильности (Mcx).

> [!NOTE]
> Поддержка mcX (Mobility Service) для устаревших мобильных клиентов больше недоступна в Skype для бизнеса Server 2019 г. Все современные Skype для бизнеса мобильные клиенты уже используют веб-API единой связи (UCWA) для поддержки обмена мгновенными сообщениями,присутствия и контактов. Пользователям с устаревшими клиентами, использующими MCX, потребуется обновиться до текущего клиента.
  
Если включить отслеживание службы IIS (IIS) для службы мобильности Skype для бизнеса Server (Mcx), созданные файлы журналов могут потреблять до трех гигабайт дискового пространства в день. Ведение журнала трассировки служб IIS включено по умолчанию. Необходимо отслеживать серверы переднего конца, чтобы убедиться, что у них не заканчивается пространство диска. 
  
По умолчанию службы IIS используют для хранения файлов журнала папку %SystemDrive%\inetpub\logs\LogFiles.
  
Чтобы отключить трассировку запросов служб IIS для всего сервера, выполните в командной строке следующую команду:
  
```console
%SystemDrive%\Windows\System32\inetsrv\appcmd set config /section:httpLogging /dontLog:True
```

Сведения о команде **httpLogging см.** в [ссылке на команду](/previous-versions/iis/settings-schema/aa347466(v=vs.90)).
