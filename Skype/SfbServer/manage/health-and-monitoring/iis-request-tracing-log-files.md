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
# <a name="monitoring-iis-request-tracing-log-files-in-skype-for-business-server-2015"></a><span data-ttu-id="1b933-103">Отслеживание файлов журнала трассировки запросов служб IIS в Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="1b933-103">Monitoring IIS request tracing log files in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="1b933-104">**Сводка:** Узнайте о службе Mobility Service (МККС) в Skype для бизнеса Server 2015, поддерживающем устаревшие клиенты.</span><span class="sxs-lookup"><span data-stu-id="1b933-104">**Summary:** Learn about the Mobility Service (Mcx) in Skype for Business Server 2015 support for legacy clients.</span></span>
  
<span data-ttu-id="1b933-105">В этом разделе описываются развертывания с поддержкой только для клиентов Lync 2010 Lync Mobile, он предназначен только для службы Mobility Service (Mcx).</span><span class="sxs-lookup"><span data-stu-id="1b933-105">This topic applies to deployments supporting Lync 2010 Lync Mobile clients only, and is intended for the Mobility Service (Mcx).</span></span>

> [!NOTE]
> <span data-ttu-id="1b933-106">Поддержка МККС (служба Mobility Service) для устаревших мобильных клиентов больше не доступна в Skype для бизнеса Server 2019.</span><span class="sxs-lookup"><span data-stu-id="1b933-106">MCX (Mobility Service) support for legacy mobile clients is no longer available in Skype for Business Server 2019.</span></span> <span data-ttu-id="1b933-107">На всех текущих мобильных клиентах Skype для бизнеса уже используется веб-API единой системы обмена сообщениями (УКВА) для поддержки мгновенных сообщений, присутствия и контактов.</span><span class="sxs-lookup"><span data-stu-id="1b933-107">All current Skype for Business mobile clients already use Unified Communications Web API (UCWA) to support instant messaging (IM), presence, and contacts.</span></span> <span data-ttu-id="1b933-108">Пользователи с устаревшими клиентами, использующими МККС, должны обновиться до текущего клиента.</span><span class="sxs-lookup"><span data-stu-id="1b933-108">Users with legacy clients using MCX will need to upgrade to a current client.</span></span>
  
<span data-ttu-id="1b933-109">При включении трассировки запросов служб IIS для службы Mobility Service в Skype для бизнеса Server (МККС) создаваемые файлы журнала могут занимать до 3 ГБ дискового пространства за день.</span><span class="sxs-lookup"><span data-stu-id="1b933-109">When you enable Internet Information Services (IIS) request tracing for the Skype for Business Server Mobility Service (Mcx), the log files that are generated can consume up to three gigabytes of disk space per day.</span></span> <span data-ttu-id="1b933-110">IIS trace logging is enabled by default.</span><span class="sxs-lookup"><span data-stu-id="1b933-110">IIS trace logging is enabled by default.</span></span> <span data-ttu-id="1b933-111">Убедитесь, что на серверах переднего плана не осталось свободного места.</span><span class="sxs-lookup"><span data-stu-id="1b933-111">You should monitor the Front End Servers to make sure that they do not run out of disk space.</span></span> 
  
<span data-ttu-id="1b933-112">По умолчанию службы IIS используют для хранения файлов журнала папку %SystemDrive%\inetpub\logs\LogFiles.</span><span class="sxs-lookup"><span data-stu-id="1b933-112">By default, IIS stores the log files at %SystemDrive%\inetpub\logs\LogFiles.</span></span>
  
<span data-ttu-id="1b933-113">Чтобы отключить трассировку запросов служб IIS для всего сервера, выполните в командной строке следующую команду:</span><span class="sxs-lookup"><span data-stu-id="1b933-113">To turn off IIS request tracing for an entire server, at the command line, type the following:</span></span>
  
```console
%SystemDrive%\Windows\System32\inetsrv\appcmd set config /section:httpLogging /dontLog:True
```

<span data-ttu-id="1b933-114">Подробные сведения о команде **хттплоггинг** можно найти [в справочнике по командам](https://go.microsoft.com/fwlink/p/?linkId=234927).</span><span class="sxs-lookup"><span data-stu-id="1b933-114">For details about the **httpLogging** command, see [the command reference](https://go.microsoft.com/fwlink/p/?linkId=234927).</span></span>
  

