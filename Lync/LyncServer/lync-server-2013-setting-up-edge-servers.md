---
title: 'Lync Server 2013: настройка пограничных серверов'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Setting up Edge Servers
ms:assetid: 09a22919-e36f-4122-8f0d-8d041198912d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398147(v=OCS.15)
ms:contentKeyID: 48183354
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a3702038781010ce56887ba39c89d09c23bffdbd
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42037609"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="setting-up-edge-servers-in-lync-server-2013"></a><span data-ttu-id="24c4f-102">Настройка пограничных серверов в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="24c4f-102">Setting up Edge Servers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="24c4f-103">_**Последнее изменение темы:** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="24c4f-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="24c4f-104">Для настройки пограничных серверов необходимо выполнить те же первостепенные задачи, что и для установки одного пограничного сервера или пула пограничных серверов с балансировкой нагрузки, за исключением того, что для пула пограничных серверов с аппаратной балансировкой нагрузки требуется развертывание балансировщиков нагрузки и дополнительные действия по репликации настройки на несколько пограничных серверов.</span><span class="sxs-lookup"><span data-stu-id="24c4f-104">The primary tasks required to set up Edge Servers are the same for installing a single Edge Server or a load-balanced pool of Edge Servers, except that a pool of hardware load balanced Edge Servers requires deployment of the load balancers and additional steps for replicating the set up on multiple Edge Servers.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="24c4f-105">Содержание</span><span class="sxs-lookup"><span data-stu-id="24c4f-105">In This Section</span></span>

  - [<span data-ttu-id="24c4f-106">Настройка сетевых интерфейсов для пограничных серверов в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="24c4f-106">Set up network interfaces for Edge Servers in Lync Server 2013</span></span>](lync-server-2013-set-up-network-interfaces-for-edge-servers.md)

  - [<span data-ttu-id="24c4f-107">Установка необходимого программного обеспечения на пограничных серверах для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="24c4f-107">Install prerequisite software on Edge Servers for Lync Server 2013</span></span>](lync-server-2013-install-prerequisite-software-on-edge-servers.md)

  - [<span data-ttu-id="24c4f-108">Экспорт топологии Lync Server 2013 и ее копирование на внешние носители для установки пограничной системы</span><span class="sxs-lookup"><span data-stu-id="24c4f-108">Export your Lync Server 2013 topology and copy it to external media for edge installation</span></span>](lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation.md)

  - [<span data-ttu-id="24c4f-109">Установка пограничных серверов для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="24c4f-109">Install Edge Servers for Lync Server 2013</span></span>](lync-server-2013-install-edge-servers.md)

  - [<span data-ttu-id="24c4f-110">Настройка пограничных сертификатов для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="24c4f-110">Set up Edge certificates for Lync Server 2013</span></span>](lync-server-2013-set-up-edge-certificates.md)

  - [<span data-ttu-id="24c4f-111">Запуск пограничных серверов в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="24c4f-111">Start Edge Servers in Lync Server 2013</span></span>](lync-server-2013-start-edge-servers.md)

  - [<span data-ttu-id="24c4f-112">Настройка обратных прокси-серверов для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="24c4f-112">Setting up reverse proxy servers for Lync Server 2013</span></span>](lync-server-2013-setting-up-reverse-proxy-servers.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

