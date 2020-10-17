---
title: 'Lync Server 2013: настройка пограничных серверов'
description: 'Lync Server 2013: настройка пограничных серверов.'
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
ms.openlocfilehash: 4e25c40e8d642d38b38afbab35225b2c7dda4d68
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48559505"
---
# <a name="setting-up-edge-servers-in-lync-server-2013"></a><span data-ttu-id="6a09b-103">Настройка пограничных серверов в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6a09b-103">Setting up Edge Servers in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6a09b-104">_**Последнее изменение темы:** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="6a09b-104">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="6a09b-105">Для настройки пограничных серверов необходимо выполнить те же первостепенные задачи, что и для установки одного пограничного сервера или пула пограничных серверов с балансировкой нагрузки, за исключением того, что для пула пограничных серверов с аппаратной балансировкой нагрузки требуется развертывание балансировщиков нагрузки и дополнительные действия по репликации настройки на несколько пограничных серверов.</span><span class="sxs-lookup"><span data-stu-id="6a09b-105">The primary tasks required to set up Edge Servers are the same for installing a single Edge Server or a load-balanced pool of Edge Servers, except that a pool of hardware load balanced Edge Servers requires deployment of the load balancers and additional steps for replicating the set up on multiple Edge Servers.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="6a09b-106">Содержание</span><span class="sxs-lookup"><span data-stu-id="6a09b-106">In This Section</span></span>

  - [<span data-ttu-id="6a09b-107">Настройка сетевых интерфейсов для пограничных серверов в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6a09b-107">Set up network interfaces for Edge Servers in Lync Server 2013</span></span>](lync-server-2013-set-up-network-interfaces-for-edge-servers.md)

  - [<span data-ttu-id="6a09b-108">Установка необходимого программного обеспечения на пограничных серверах для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6a09b-108">Install prerequisite software on Edge Servers for Lync Server 2013</span></span>](lync-server-2013-install-prerequisite-software-on-edge-servers.md)

  - [<span data-ttu-id="6a09b-109">Экспорт топологии Lync Server 2013 и ее копирование на внешние носители для установки пограничной системы</span><span class="sxs-lookup"><span data-stu-id="6a09b-109">Export your Lync Server 2013 topology and copy it to external media for edge installation</span></span>](lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation.md)

  - [<span data-ttu-id="6a09b-110">Установка пограничных серверов для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6a09b-110">Install Edge Servers for Lync Server 2013</span></span>](lync-server-2013-install-edge-servers.md)

  - [<span data-ttu-id="6a09b-111">Настройка пограничных сертификатов для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6a09b-111">Set up Edge certificates for Lync Server 2013</span></span>](lync-server-2013-set-up-edge-certificates.md)

  - [<span data-ttu-id="6a09b-112">Запуск пограничных серверов в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6a09b-112">Start Edge Servers in Lync Server 2013</span></span>](lync-server-2013-start-edge-servers.md)

  - [<span data-ttu-id="6a09b-113">Настройка обратных прокси-серверов для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6a09b-113">Setting up reverse proxy servers for Lync Server 2013</span></span>](lync-server-2013-setting-up-reverse-proxy-servers.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

