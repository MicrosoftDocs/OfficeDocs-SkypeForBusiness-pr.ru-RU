---
title: Экспорт топологии и ее копирование на внешние носители для установки в пограничной топологии
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Export your topology and copy it to external media for edge installation
ms:assetid: def9f416-c519-4a72-b242-7d3057d9c1fd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398983(v=OCS.15)
ms:contentKeyID: 48185615
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8eb8f20e7af8cbfd772226917b027a33a688a4a5
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756213"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="export-your-lync-server-2013-topology-and-copy-it-to-external-media-for-edge-installation"></a><span data-ttu-id="8c85c-102">Экспорт топологии Lync Server 2013 и ее копирование на внешние носители для установки в пограничной топологии</span><span class="sxs-lookup"><span data-stu-id="8c85c-102">Export your Lync Server 2013 topology and copy it to external media for edge installation</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8c85c-103">_**Тема последнего изменения:** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="8c85c-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="8c85c-104">После публикации топологии мастеру развертывания Lync Server требуется доступ к данным центрального хранилища, чтобы начать процесс развертывания на сервере.</span><span class="sxs-lookup"><span data-stu-id="8c85c-104">After you publish your topology, the Lync Server Deployment Wizard needs access to the Central Management store data in order to start the deployment process on the server.</span></span> <span data-ttu-id="8c85c-105">Во внутренней сети данные доступны непосредственно с серверов, но пограничные серверы, которые не входят в внутренний домен, не могут получить доступ к данным.</span><span class="sxs-lookup"><span data-stu-id="8c85c-105">In the internal network, the data is available directly from the servers, but Edge Servers that are not in the internal domain cannot access the data.</span></span> <span data-ttu-id="8c85c-106">Чтобы данные конфигурации топологии были доступны для развертывания пограничного сервера, необходимо экспортировать данные топологии в файл и скопировать его на внешний носитель (например, USB-накопитель или сетевую общую информацию, доступную с пограничного сервера) перед запуском среды выполнения Lync Server. Мастер лоймент на пограничном сервере.</span><span class="sxs-lookup"><span data-stu-id="8c85c-106">To make the topology configuration data available for an Edge Server deployment, you must export the topology data to a file and copy it to external media (for example, a USB drive or a network share that is available from the Edge Server) before you run the Lync Server Deployment Wizard on the Edge Server.</span></span> <span data-ttu-id="8c85c-107">Выполните описанные ниже действия, чтобы сделать данные конфигурации топологии доступными на пограничном сервере, который вы развертываете.</span><span class="sxs-lookup"><span data-stu-id="8c85c-107">Use the following procedure to make your topology configuration data available on the Edge Server that you are deploying.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="8c85c-108">После установки Lync Server 2013 на пограничном сервере вы можете управлять пограничным сервером с помощью средств администрирования внутренней сети, которые автоматически реплицируют конфигурацию на любые пограничные серверы в развертывании.</span><span class="sxs-lookup"><span data-stu-id="8c85c-108">After you install Lync Server 2013 on an Edge Server, you manage the Edge Server using the administrative tools in the internal network, which automatically replicate configuration to any Edge Servers in your deployment.</span></span> <span data-ttu-id="8c85c-109">Единственным исключением является назначение и установка сертификатов, остановка и запуск служб, которые должны быть выполнены на пограничном сервере.</span><span class="sxs-lookup"><span data-stu-id="8c85c-109">The only exception is assigning and installing certificates and stopping and starting services, both of which must be done on the Edge Server.</span></span>



</div>

<div>

## <a name="to-make-your-topology-data-available-on-an-edge-server-by-using-lync-server-management-shell"></a><span data-ttu-id="8c85c-110">Как сделать данные топологии доступными на пограничном сервере с помощью командной консоли Lync Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="8c85c-110">To make your topology data available on an Edge Server by using Lync Server Management Shell</span></span>

1.  <span data-ttu-id="8c85c-111">Запустите командную консоль Lync Server Management Shell: нажмите кнопку **Пуск**, выберите **все программы**, а затем — **Microsoft Lync Server 2013**, а затем — **Командная консоль Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="8c85c-111">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="8c85c-112">В командной консоли Lync Server выполните следующий командлет:</span><span class="sxs-lookup"><span data-stu-id="8c85c-112">In the Lync Server Management Shell, run the following cmdlet:</span></span>
    
        Export-CsConfiguration -FileName <ConfigurationFilePath.zip>

3.  <span data-ttu-id="8c85c-113">Скопируйте экспортированный файл на внешний носитель (например, USB-накопитель или сетевую общую сеть, доступную на пограничном сервере во время развертывания).</span><span class="sxs-lookup"><span data-stu-id="8c85c-113">Copy the exported file to external media (for example, a USB drive or a network share that is available from the Edge Server during deployment).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

