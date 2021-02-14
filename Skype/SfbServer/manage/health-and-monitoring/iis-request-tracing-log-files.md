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
# <a name="monitoring-iis-request-tracing-log-files-in-skype-for-business-server-2015"></a><span data-ttu-id="69fe8-103">Мониторинг файлов журнала трасситуры запросов IIS в Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="69fe8-103">Monitoring IIS request tracing log files in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="69fe8-104">**Сводка:** Learn about the Mobility Service (Mcx) in Skype for Business Server 2015 support for legacy clients.</span><span class="sxs-lookup"><span data-stu-id="69fe8-104">**Summary:** Learn about the Mobility Service (Mcx) in Skype for Business Server 2015 support for legacy clients.</span></span>
  
<span data-ttu-id="69fe8-105">Этот раздел относится к развертываниям, поддерживающих только клиенты Lync 2010 Lync Mobile, и предназначен для службы Mobility Service (Mcx).</span><span class="sxs-lookup"><span data-stu-id="69fe8-105">This topic applies to deployments supporting Lync 2010 Lync Mobile clients only, and is intended for the Mobility Service (Mcx).</span></span>

> [!NOTE]
> <span data-ttu-id="69fe8-106">Поддержка СЛУЖБЫ MCX (Mobility Service) для устаревших мобильных клиентов больше недоступна в Skype для бизнеса Server 2019.</span><span class="sxs-lookup"><span data-stu-id="69fe8-106">MCX (Mobility Service) support for legacy mobile clients is no longer available in Skype for Business Server 2019.</span></span> <span data-ttu-id="69fe8-107">Все текущие мобильные клиенты Skype для бизнеса уже используют веб-API объединенных коммуникаций (UCWA) для поддержки обмена мгновенными сообщениями, присутствия и контактов.</span><span class="sxs-lookup"><span data-stu-id="69fe8-107">All current Skype for Business mobile clients already use Unified Communications Web API (UCWA) to support instant messaging (IM), presence, and contacts.</span></span> <span data-ttu-id="69fe8-108">Пользователям с устаревшими клиентами, использующими MCX, потребуется обновиться до текущего клиента.</span><span class="sxs-lookup"><span data-stu-id="69fe8-108">Users with legacy clients using MCX will need to upgrade to a current client.</span></span>
  
<span data-ttu-id="69fe8-109">Если включить трассировку запросов служб IIS для Службы Skype для бизнеса Server Mobility Service (Mcx), созданные файлы журнала могут потреблять до трех гигабайт дискового пространства в день.</span><span class="sxs-lookup"><span data-stu-id="69fe8-109">When you enable Internet Information Services (IIS) request tracing for the Skype for Business Server Mobility Service (Mcx), the log files that are generated can consume up to three gigabytes of disk space per day.</span></span> <span data-ttu-id="69fe8-110">Ведение журнала трассировки служб IIS включено по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="69fe8-110">IIS trace logging is enabled by default.</span></span> <span data-ttu-id="69fe8-111">Необходимо отслеживать серверы переднего сервера, чтобы убедиться, что на них не заканчивается место на диске.</span><span class="sxs-lookup"><span data-stu-id="69fe8-111">You should monitor the Front End Servers to make sure that they do not run out of disk space.</span></span> 
  
<span data-ttu-id="69fe8-112">По умолчанию службы IIS используют для хранения файлов журнала папку %SystemDrive%\inetpub\logs\LogFiles.</span><span class="sxs-lookup"><span data-stu-id="69fe8-112">By default, IIS stores the log files at %SystemDrive%\inetpub\logs\LogFiles.</span></span>
  
<span data-ttu-id="69fe8-113">Чтобы отключить трассировку запросов служб IIS для всего сервера, выполните в командной строке следующую команду:</span><span class="sxs-lookup"><span data-stu-id="69fe8-113">To turn off IIS request tracing for an entire server, at the command line, type the following:</span></span>
  
```console
%SystemDrive%\Windows\System32\inetsrv\appcmd set config /section:httpLogging /dontLog:True
```

<span data-ttu-id="69fe8-114">Подробные сведения о **команде httpLogging** см. [в ссылке на команду.](https://go.microsoft.com/fwlink/p/?linkId=234927)</span><span class="sxs-lookup"><span data-stu-id="69fe8-114">For details about the **httpLogging** command, see [the command reference](https://go.microsoft.com/fwlink/p/?linkId=234927).</span></span>
  

