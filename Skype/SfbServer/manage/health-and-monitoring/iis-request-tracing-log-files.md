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
ms.openlocfilehash: f519a04f878caf953c54873a6a704232245b344b
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/08/2020
ms.locfileid: "40992184"
---
# <a name="monitoring-iis-request-tracing-log-files-in-skype-for-business-server-2015"></a>Отслеживание файлов журнала трассировки запросов служб IIS в Skype для бизнеса Server 2015
 
**Сводка:** Узнайте о службе Mobility Service (МККС) в Skype для бизнеса Server 2015, поддерживающем устаревшие клиенты.
  
В этом разделе описываются развертывания с поддержкой только для клиентов Lync 2010 Lync Mobile, он предназначен только для службы Mobility Service (Mcx).

> [!NOTE]
> Поддержка МККС (служба Mobility Service) для устаревших мобильных клиентов больше не доступна в Skype для бизнеса Server 2019. На всех текущих мобильных клиентах Skype для бизнеса уже используется веб-API единой системы обмена сообщениями (УКВА) для поддержки мгновенных сообщений, присутствия и контактов. Пользователи с устаревшими клиентами, использующими МККС, должны обновиться до текущего клиента.
  
При включении трассировки запросов служб IIS для службы Mobility Service в Skype для бизнеса Server (МККС) создаваемые файлы журнала могут занимать до 3 ГБ дискового пространства за день. IIS trace logging is enabled by default. Убедитесь, что на серверах переднего плана не осталось свободного места. 
  
По умолчанию службы IIS используют для хранения файлов журнала папку %SystemDrive%\inetpub\logs\LogFiles.
  
Чтобы отключить трассировку запросов служб IIS для всего сервера, выполните в командной строке следующую команду:
  
```console
%SystemDrive%\Windows\System32\inetsrv\appcmd set config /section:httpLogging /dontLog:True
```

Подробные сведения о команде **хттплоггинг** можно найти [в справочнике по командам](https://go.microsoft.com/fwlink/p/?linkId=234927).
  

