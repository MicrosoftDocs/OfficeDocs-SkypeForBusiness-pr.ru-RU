---
title: Мониторинг файлов журнала трасситуры запросов IIS в Skype для бизнеса Server 2015
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
description: Сводка. Сведения о поддержке службы Mobility Service (Mcx) в Skype для бизнеса Server 2015 для устаревших клиентов.
ms.openlocfilehash: 5fb9e66efa468e8755fe369c3ce4f2a4b8979e57
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49823509"
---
# <a name="monitoring-iis-request-tracing-log-files-in-skype-for-business-server-2015"></a>Мониторинг файлов журнала трасситуры запросов IIS в Skype для бизнеса Server 2015
 
**Сводка:** Learn about the Mobility Service (Mcx) in Skype for Business Server 2015 support for legacy clients.
  
Этот раздел относится к развертываниям, поддерживающих только клиенты Lync 2010 Lync Mobile, и предназначен для службы Mobility Service (Mcx).

> [!NOTE]
> Поддержка MCX (Mobility Service) для устаревших мобильных клиентов больше недоступна в Skype для бизнеса Server 2019. Все текущие мобильные клиенты Skype для бизнеса уже используют веб-API объединенных коммуникаций (UCWA) для поддержки обмена мгновенными сообщениями, присутствия и контактов. Пользователям с устаревшими клиентами, использующими MCX, потребуется обновиться до текущего клиента.
  
Если включить трассировку запросов служб IIS для Службы Skype для бизнеса Server Mobility Service (Mcx), созданные файлы журнала могут потреблять до трех гигабайт дискового пространства в день. Ведение журнала трассировки служб IIS включено по умолчанию. Необходимо отслеживать серверы переднего сервера, чтобы убедиться, что на них не заканчивается место на диске. 
  
По умолчанию службы IIS используют для хранения файлов журнала папку %SystemDrive%\inetpub\logs\LogFiles.
  
Чтобы отключить трассировку запросов служб IIS для всего сервера, выполните в командной строке следующую команду:
  
```console
%SystemDrive%\Windows\System32\inetsrv\appcmd set config /section:httpLogging /dontLog:True
```

Подробные сведения о **команде httpLogging** см. [в справке по команде.](https://go.microsoft.com/fwlink/p/?linkId=234927)
  

