---
title: Мониторинг IIS запрашивает отслеживание файлов журналов в Skype для бизнеса Server 2015 г.
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: b6730e92-6d74-4fa7-a83f-50b7bdadbffa
description: Сводка. Сведения о службе мобильности (Mcx) в Skype для бизнеса Server 2015 г. для устаревших клиентов.
ms.openlocfilehash: 2b571ceb583f7a42c6f41fba3c868fbe1628631a
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/08/2021
ms.locfileid: "60857556"
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

Сведения о команде **httpLogging см.** в [ссылке на командную ссылку.](/previous-versions/iis/settings-schema/aa347466(v=vs.90))
