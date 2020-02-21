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
ms.openlocfilehash: 52903a2e7ae1b9a3a994a1199e32d8d7c4bd1e03
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42202355"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="export-your-lync-server-2013-topology-and-copy-it-to-external-media-for-edge-installation"></a><span data-ttu-id="ed0fd-102">Экспорт топологии Lync Server 2013 и ее копирование на внешние носители для установки пограничной системы</span><span class="sxs-lookup"><span data-stu-id="ed0fd-102">Export your Lync Server 2013 topology and copy it to external media for edge installation</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ed0fd-103">_**Последнее изменение темы:** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="ed0fd-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="ed0fd-104">После публикации топологии мастеру развертывания Lync Server требуется доступ к данным центрального хранилища управления, чтобы начать процесс развертывания на сервере.</span><span class="sxs-lookup"><span data-stu-id="ed0fd-104">After you publish your topology, the Lync Server Deployment Wizard needs access to the Central Management store data in order to start the deployment process on the server.</span></span> <span data-ttu-id="ed0fd-105">Во внутренней сети данные доступны непосредственно с серверов, однако пограничные серверы за пределами внутреннего домена не могут получить доступ к этим данным.</span><span class="sxs-lookup"><span data-stu-id="ed0fd-105">In the internal network, the data is available directly from the servers, but Edge Servers that are not in the internal domain cannot access the data.</span></span> <span data-ttu-id="ed0fd-106">Чтобы сделать данные конфигурации топологии доступными для развертывания пограничного сервера, необходимо экспортировать данные топологии в файл и скопировать его на внешний носитель (например, USB-диск или общий сетевой ресурс, доступный с пограничного сервера) перед запуском среды выполнения Lync Server. Мастер лоймент на пограничном сервере.</span><span class="sxs-lookup"><span data-stu-id="ed0fd-106">To make the topology configuration data available for an Edge Server deployment, you must export the topology data to a file and copy it to external media (for example, a USB drive or a network share that is available from the Edge Server) before you run the Lync Server Deployment Wizard on the Edge Server.</span></span> <span data-ttu-id="ed0fd-107">Используйте следующую процедуру, чтобы сделать ваши данные о конфигурации топологии доступными развертываемому пограничному серверу.</span><span class="sxs-lookup"><span data-stu-id="ed0fd-107">Use the following procedure to make your topology configuration data available on the Edge Server that you are deploying.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="ed0fd-108">После установки Lync Server 2013 на пограничном сервере управление пограничным сервером осуществляется с помощью средств администрирования внутренней сети, которые автоматически реплицируют конфигурацию на пограничные серверы в развертывании.</span><span class="sxs-lookup"><span data-stu-id="ed0fd-108">After you install Lync Server 2013 on an Edge Server, you manage the Edge Server using the administrative tools in the internal network, which automatically replicate configuration to any Edge Servers in your deployment.</span></span> <span data-ttu-id="ed0fd-109">Единственным исключением является назначение и установка сертификатов и остановка и запуск служб — обе эти операции необходимо выполнять на пограничном сервере.</span><span class="sxs-lookup"><span data-stu-id="ed0fd-109">The only exception is assigning and installing certificates and stopping and starting services, both of which must be done on the Edge Server.</span></span>



</div>

<div>

## <a name="to-make-your-topology-data-available-on-an-edge-server-by-using-lync-server-management-shell"></a><span data-ttu-id="ed0fd-110">Обеспечение доступа к данным о топологии на пограничном сервере с помощью командной консоли Lync Server</span><span class="sxs-lookup"><span data-stu-id="ed0fd-110">To make your topology data available on an Edge Server by using Lync Server Management Shell</span></span>

1.  <span data-ttu-id="ed0fd-111">Запустите командную консоль Lync Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Microsoft Lync Server 2013** и щелкните элемент **Командная консоль Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="ed0fd-111">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="ed0fd-112">В командной консоли Lync Server выполните следующий командлет:</span><span class="sxs-lookup"><span data-stu-id="ed0fd-112">In the Lync Server Management Shell, run the following cmdlet:</span></span>
    
        Export-CsConfiguration -FileName <ConfigurationFilePath.zip>

3.  <span data-ttu-id="ed0fd-113">Скопируйте экспортированный файл на внешний носитель (например, USB-диск или в сетевую общую папку, доступную с пограничного сервера во время развертывания).</span><span class="sxs-lookup"><span data-stu-id="ed0fd-113">Copy the exported file to external media (for example, a USB drive or a network share that is available from the Edge Server during deployment).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

