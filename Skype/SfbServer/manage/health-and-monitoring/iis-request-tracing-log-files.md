---
title: Отслеживание файлов журнала трассировки запросов служб IIS в Skype для бизнеса Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b6730e92-6d74-4fa7-a83f-50b7bdadbffa
description: ': Сводка сведения о службе мобильности (Mcx) в Скайп для поддержки Business Server 2015 для устаревших клиентов.'
ms.openlocfilehash: cbb064cf868a557c5f30871df8f7ee4b60242679
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "33926622"
---
# <a name="monitoring-iis-request-tracing-log-files-in-skype-for-business-server-2015"></a><span data-ttu-id="3b758-103">Отслеживание файлов журнала трассировки запросов служб IIS в Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="3b758-103">Monitoring IIS request tracing log files in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="3b758-104">**Сводка:** Сведения о службе мобильности (Mcx) в Скайп для поддержки Business Server 2015 для устаревших клиентов.</span><span class="sxs-lookup"><span data-stu-id="3b758-104">**Summary:** Learn about the Mobility Service (Mcx) in Skype for Business Server 2015 support for legacy clients.</span></span>
  
<span data-ttu-id="3b758-105">В этом разделе описываются развертывания с поддержкой только для клиентов Lync 2010 Lync Mobile, он предназначен только для службы Mobility Service (Mcx).</span><span class="sxs-lookup"><span data-stu-id="3b758-105">This topic applies to deployments supporting Lync 2010 Lync Mobile clients only, and is intended for the Mobility Service (Mcx).</span></span>

> [!NOTE]
> <span data-ttu-id="3b758-106">Поддержка устаревших мобильных клиентов MCX (Mobility Service) больше не доступен в Скайп для Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="3b758-106">MCX (Mobility Service) support for legacy mobile clients is no longer available in Skype for Business Server 2019.</span></span> <span data-ttu-id="3b758-107">Все текущей Скайп для мобильных клиентов Business уже используете Unified Communications Web API (UCWA) для поддержки мгновенного обмена Мгновенными сообщениями, сведения о присутствии и контакты.</span><span class="sxs-lookup"><span data-stu-id="3b758-107">All current Skype for Business mobile clients already use Unified Communications Web API (UCWA) to support instant messaging (IM), presence, and contacts.</span></span> <span data-ttu-id="3b758-108">Пользователи с прежних версий клиентов, использующих MCX потребуется обновить до текущего клиента.</span><span class="sxs-lookup"><span data-stu-id="3b758-108">Users with legacy clients using MCX will need to upgrade to a current client.</span></span>
  
<span data-ttu-id="3b758-109">При включении трассировку запросов Internet Information Services (IIS) для Скайп для службы Mobility Business Server (Mcx), файлы журнала, которые создаются может использовать до трех гигабайт дискового пространства в день.</span><span class="sxs-lookup"><span data-stu-id="3b758-109">When you enable Internet Information Services (IIS) request tracing for the Skype for Business Server Mobility Service (Mcx), the log files that are generated can consume up to three gigabytes of disk space per day.</span></span> <span data-ttu-id="3b758-110">IIS trace logging is enabled by default.</span><span class="sxs-lookup"><span data-stu-id="3b758-110">IIS trace logging is enabled by default.</span></span> <span data-ttu-id="3b758-111">Следует отслеживать серверов переднего плана, чтобы убедиться в том, что они не хватает свободного места.</span><span class="sxs-lookup"><span data-stu-id="3b758-111">You should monitor the Front End Servers to make sure that they do not run out of disk space.</span></span> 
  
<span data-ttu-id="3b758-112">По умолчанию службы IIS используют для хранения файлов журнала папку %SystemDrive%\inetpub\logs\LogFiles.</span><span class="sxs-lookup"><span data-stu-id="3b758-112">By default, IIS stores the log files at %SystemDrive%\inetpub\logs\LogFiles.</span></span>
  
<span data-ttu-id="3b758-113">Чтобы отключить трассировку запросов служб IIS для всего сервера, выполните в командной строке следующую команду:</span><span class="sxs-lookup"><span data-stu-id="3b758-113">To turn off IIS request tracing for an entire server, at the command line, type the following:</span></span>
  
```
%SystemDrive%\Windows\System32\inetsrv\appcmd set config /section:httpLogging /dontLog:True
```

<span data-ttu-id="3b758-114">[Для получения дополнительных сведений о команде **httpLogging** см.](https://go.microsoft.com/fwlink/p/?linkId=234927)</span><span class="sxs-lookup"><span data-stu-id="3b758-114">For details about the **httpLogging** command, see [the command reference](https://go.microsoft.com/fwlink/p/?linkId=234927).</span></span>
  

