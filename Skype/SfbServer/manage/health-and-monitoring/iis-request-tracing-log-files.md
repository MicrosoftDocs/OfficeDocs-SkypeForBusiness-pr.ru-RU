---
title: Отслеживание файлов журнала трассировки запросов служб IIS в Skype для бизнеса Server 2015
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b6730e92-6d74-4fa7-a83f-50b7bdadbffa
description: ': Сводка сведения о службе мобильности (Mcx) в Скайп для поддержки Business Server 2015 для устаревших клиентов.'
ms.openlocfilehash: 5ed817290bdf86d11dd4a2cf0e95c83fb4c31d9a
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/24/2018
ms.locfileid: "20983828"
---
# <a name="monitoring-iis-request-tracing-log-files-in-skype-for-business-server-2015"></a>Отслеживание файлов журнала трассировки запросов служб IIS в Skype для бизнеса Server 2015
 
**Сводка:** Сведения о службе мобильности (Mcx) в Скайп для поддержки Business Server 2015 для устаревших клиентов.
  
В этом разделе описываются развертывания с поддержкой только для клиентов Lync 2010 Lync Mobile, он предназначен только для службы Mobility Service (Mcx).

> [!NOTE]
> Поддержка MCX для устаревших мобильных клиентов больше не доступен в Скайп для Business Server 2019. Пользователям необходимо обновить до текущего клиента.
  
При включении трассировку запросов Internet Information Services (IIS) для Скайп для службы Mobility Business Server (Mcx), файлы журнала, которые создаются может использовать до трех гигабайт дискового пространства в день. Ведение журнала трассировки IIS включен по умолчанию. Следует отслеживать серверов переднего плана, чтобы убедиться в том, что они не хватает свободного места. 
  
По умолчанию службы IIS используют для хранения файлов журнала папку %SystemDrive%\inetpub\logs\LogFiles.
  
Чтобы отключить трассировку запросов служб IIS для всего сервера, выполните в командной строке следующую команду:
  
```
%SystemDrive%\Windows\System32\inetsrv\appcmd set config /section:httpLogging /dontLog:True
```

[Для получения дополнительных сведений о команде **httpLogging** см.](https://go.microsoft.com/fwlink/p/?linkId=234927)
  

