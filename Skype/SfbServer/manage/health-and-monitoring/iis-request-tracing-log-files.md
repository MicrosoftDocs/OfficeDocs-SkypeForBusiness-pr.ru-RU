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
# <a name="monitoring-iis-request-tracing-log-files-in-skype-for-business-server-2015"></a><span data-ttu-id="c4399-103">Отслеживание файлов журнала трассировки запросов служб IIS в Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="c4399-103">Monitoring IIS request tracing log files in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="c4399-104">**Сводка:** Сведения о службе мобильности (Mcx) в Скайп для поддержки Business Server 2015 для устаревших клиентов.</span><span class="sxs-lookup"><span data-stu-id="c4399-104">**Summary:** Learn about the Mobility Service (Mcx) in Skype for Business Server 2015 support for legacy clients.</span></span>
  
<span data-ttu-id="c4399-105">В этом разделе описываются развертывания с поддержкой только для клиентов Lync 2010 Lync Mobile, он предназначен только для службы Mobility Service (Mcx).</span><span class="sxs-lookup"><span data-stu-id="c4399-105">This topic applies to deployments supporting Lync 2010 Lync Mobile clients only, and is intended for the Mobility Service (Mcx).</span></span>

> [!NOTE]
> <span data-ttu-id="c4399-106">Поддержка MCX для устаревших мобильных клиентов больше не доступен в Скайп для Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="c4399-106">MCX support for legacy mobile clients is no longer available in Skype for Business Server 2019.</span></span> <span data-ttu-id="c4399-107">Пользователям необходимо обновить до текущего клиента.</span><span class="sxs-lookup"><span data-stu-id="c4399-107">Your users will need to upgrade to a current client.</span></span>
  
<span data-ttu-id="c4399-108">При включении трассировку запросов Internet Information Services (IIS) для Скайп для службы Mobility Business Server (Mcx), файлы журнала, которые создаются может использовать до трех гигабайт дискового пространства в день.</span><span class="sxs-lookup"><span data-stu-id="c4399-108">When you enable Internet Information Services (IIS) request tracing for the Skype for Business Server Mobility Service (Mcx), the log files that are generated can consume up to three gigabytes of disk space per day.</span></span> <span data-ttu-id="c4399-109">Ведение журнала трассировки IIS включен по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="c4399-109">IIS trace logging is enabled by default.</span></span> <span data-ttu-id="c4399-110">Следует отслеживать серверов переднего плана, чтобы убедиться в том, что они не хватает свободного места.</span><span class="sxs-lookup"><span data-stu-id="c4399-110">You should monitor the Front End Servers to make sure that they do not run out of disk space.</span></span> 
  
<span data-ttu-id="c4399-111">По умолчанию службы IIS используют для хранения файлов журнала папку %SystemDrive%\inetpub\logs\LogFiles.</span><span class="sxs-lookup"><span data-stu-id="c4399-111">By default, IIS stores the log files at %SystemDrive%\inetpub\logs\LogFiles.</span></span>
  
<span data-ttu-id="c4399-112">Чтобы отключить трассировку запросов служб IIS для всего сервера, выполните в командной строке следующую команду:</span><span class="sxs-lookup"><span data-stu-id="c4399-112">To turn off IIS request tracing for an entire server, at the command line, type the following:</span></span>
  
```
%SystemDrive%\Windows\System32\inetsrv\appcmd set config /section:httpLogging /dontLog:True
```

<span data-ttu-id="c4399-113">[Для получения дополнительных сведений о команде **httpLogging** см.](https://go.microsoft.com/fwlink/p/?linkId=234927)</span><span class="sxs-lookup"><span data-stu-id="c4399-113">For details about the **httpLogging** command, see [the command reference](https://go.microsoft.com/fwlink/p/?linkId=234927).</span></span>
  

