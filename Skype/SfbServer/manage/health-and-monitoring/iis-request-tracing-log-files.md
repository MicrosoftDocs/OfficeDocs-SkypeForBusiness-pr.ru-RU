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
# <a name="monitoring-iis-request-tracing-log-files-in-skype-for-business-server-2015"></a><span data-ttu-id="5f79c-103">Мониторинг IIS-запросов на отслеживание файлов журналов в Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="5f79c-103">Monitoring IIS request tracing log files in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="5f79c-104">**Сводка:** Узнайте о службе мобильности (Mcx) в Skype для бизнеса Server 2015, которая поддерживает устаревших клиентов.</span><span class="sxs-lookup"><span data-stu-id="5f79c-104">**Summary:** Learn about the Mobility Service (Mcx) in Skype for Business Server 2015 support for legacy clients.</span></span>
  
<span data-ttu-id="5f79c-105">Этот раздел относится к развертываниям, поддерживающих только клиентов Lync Lync Mobile, и предназначен для службы мобильности (Mcx).</span><span class="sxs-lookup"><span data-stu-id="5f79c-105">This topic applies to deployments supporting Lync 2010 Lync Mobile clients only, and is intended for the Mobility Service (Mcx).</span></span>

> [!NOTE]
> <span data-ttu-id="5f79c-106">Поддержка mcX (Mobility Service) для устаревших мобильных клиентов больше недоступна в Skype для бизнеса Server 2019.</span><span class="sxs-lookup"><span data-stu-id="5f79c-106">MCX (Mobility Service) support for legacy mobile clients is no longer available in Skype for Business Server 2019.</span></span> <span data-ttu-id="5f79c-107">Все текущие мобильные клиенты Skype для бизнеса уже используют веб-API единой связи (UCWA) для поддержки обмена мгновенными сообщениями, присутствия и контактов.</span><span class="sxs-lookup"><span data-stu-id="5f79c-107">All current Skype for Business mobile clients already use Unified Communications Web API (UCWA) to support instant messaging (IM), presence, and contacts.</span></span> <span data-ttu-id="5f79c-108">Пользователям с устаревшими клиентами, использующими MCX, потребуется обновиться до текущего клиента.</span><span class="sxs-lookup"><span data-stu-id="5f79c-108">Users with legacy clients using MCX will need to upgrade to a current client.</span></span>
  
<span data-ttu-id="5f79c-109">Если включить отслеживание запросов служб интернет-информации (IIS) для службы мобильности Skype для бизнес-серверов (Mcx), созданные файлы журналов могут потреблять до трех гигабайт дискового пространства в день.</span><span class="sxs-lookup"><span data-stu-id="5f79c-109">When you enable Internet Information Services (IIS) request tracing for the Skype for Business Server Mobility Service (Mcx), the log files that are generated can consume up to three gigabytes of disk space per day.</span></span> <span data-ttu-id="5f79c-110">Ведение журнала трассировки служб IIS включено по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="5f79c-110">IIS trace logging is enabled by default.</span></span> <span data-ttu-id="5f79c-111">Необходимо отслеживать серверы переднего конца, чтобы убедиться, что у них не заканчивается пространство диска.</span><span class="sxs-lookup"><span data-stu-id="5f79c-111">You should monitor the Front End Servers to make sure that they do not run out of disk space.</span></span> 
  
<span data-ttu-id="5f79c-112">По умолчанию службы IIS используют для хранения файлов журнала папку %SystemDrive%\inetpub\logs\LogFiles.</span><span class="sxs-lookup"><span data-stu-id="5f79c-112">By default, IIS stores the log files at %SystemDrive%\inetpub\logs\LogFiles.</span></span>
  
<span data-ttu-id="5f79c-113">Чтобы отключить трассировку запросов служб IIS для всего сервера, выполните в командной строке следующую команду:</span><span class="sxs-lookup"><span data-stu-id="5f79c-113">To turn off IIS request tracing for an entire server, at the command line, type the following:</span></span>
  
```console
%SystemDrive%\Windows\System32\inetsrv\appcmd set config /section:httpLogging /dontLog:True
```

<span data-ttu-id="5f79c-114">Сведения о команде **httpLogging см.** в [ссылке на командную ссылку.](/previous-versions/iis/settings-schema/aa347466(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="5f79c-114">For details about the **httpLogging** command, see [the command reference](/previous-versions/iis/settings-schema/aa347466(v=vs.90)).</span></span>
