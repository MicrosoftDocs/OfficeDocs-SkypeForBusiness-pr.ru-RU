---
title: 'Lync Server 2013: развертывание серверов-посредников и определение одноранговых узлов'
description: 'Lync Server 2013: развертывание серверов-посредников и определение одноранговых узлов.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying Mediation Servers and defining peers
ms:assetid: a684f1da-6671-4011-adf6-2db49e2528e2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412780(v=OCS.15)
ms:contentKeyID: 48185077
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fc3afce038371920beea1cc52549d8d027429e08
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48545235"
---
# <a name="deploying-mediation-servers-and-defining-peers-in-lync-server-2013"></a><span data-ttu-id="0df33-103">Развертывание серверов-посредников и определение одноранговых узлов в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0df33-103">Deploying Mediation Servers and defining peers in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0df33-104">_**Последнее изменение темы:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="0df33-104">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="0df33-105">Рабочая нагрузка корпоративной голосовой связи, Конференц-связь с телефонным подключением и расширенные приложения для корпоративной голосовой связи (приложение группы ответа, приложение парковки вызовов, контроль допуска звонков и т. д.) доступны в интерфейсных пулах.</span><span class="sxs-lookup"><span data-stu-id="0df33-105">The Enterprise Voice workload, dial-in conferencing, and advanced Enterprise Voice applications (Response Group application, Call Park application, call admission control (CAC), and so on), are available in Front End pools.</span></span> <span data-ttu-id="0df33-106">В Lync Server 2013 функциональные возможности сервера-посредника встроены в интерфейсный сервер.</span><span class="sxs-lookup"><span data-stu-id="0df33-106">With Lync Server 2013, the functionality of the Mediation Server is built into the Front End Server.</span></span> <span data-ttu-id="0df33-107">Отдельный изолированный сервер-посредник больше не нужен.</span><span class="sxs-lookup"><span data-stu-id="0df33-107">A separate stand-alone Mediation Server is no longer necessary.</span></span> <span data-ttu-id="0df33-108">Интерфейсные пулы могут напрямую связываться с поддерживаемыми шлюзами (шлюзом телефонной сети общего пользования (PSTN) или IP-УАТС), что отменяет потребность сервера-посредника в качестве посредника.</span><span class="sxs-lookup"><span data-stu-id="0df33-108">Front End pools can communicate directly with supported gateways (a public switched telephone network (PSTN) gateway or an IP-PBX), removing the need for a Mediation Server to serve as an intermediary.</span></span>

<span data-ttu-id="0df33-109">Единственное исключение из данного правила — настройка магистрали SIP для подключения к пограничному контроллеру сеансов для поставщика услуг интернет-телефонии.</span><span class="sxs-lookup"><span data-stu-id="0df33-109">The only exception is if you configure a SIP trunk to connect to a Session Border Controller for an Internet Telephony Service Provider.</span></span> <span data-ttu-id="0df33-110">Чтобы подключить инфраструктуру корпоративной голосовой связи к поставщику магистрали SIP, необходимо развернуть отдельный сервер-посредник.</span><span class="sxs-lookup"><span data-stu-id="0df33-110">To connect your Enterprise Voice infrastructure to your SIP trunk provider, a separate Mediation Server must be deployed.</span></span>

<span data-ttu-id="0df33-111">Подключение между Lync Server (компонент сервера-посредника в интерфейсном пуле или на изолированном сервере-посреднике) и шлюз определяется как логическая связь, называемая *магистральной*линией.</span><span class="sxs-lookup"><span data-stu-id="0df33-111">The connection between Lync Server (the Mediation Server component on a Front End pool or stand-alone Mediation Server) and a gateway is defined as a logical association called a *trunk*.</span></span> <span data-ttu-id="0df33-112">В этом разделе даны инструкции по определению магистрали и развертыванию отдельного сервера-посредника при подключении к магистрали SIP.</span><span class="sxs-lookup"><span data-stu-id="0df33-112">The topics in this section describe how to define a trunk and how to deploy a stand-alone Mediation Server, if you connect to a SIP trunk.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="0df33-113">Содержание</span><span class="sxs-lookup"><span data-stu-id="0df33-113">In This Section</span></span>

  - [<span data-ttu-id="0df33-114">Определение сервера-посредника в построителе топологий в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0df33-114">Define a Mediation Server in Topology Builder in Lync Server 2013</span></span>](lync-server-2013-define-a-mediation-server-in-topology-builder.md)

  - [<span data-ttu-id="0df33-115">Определение шлюза в построителе топологий в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0df33-115">Define a gateway in Topology Builder in Lync Server 2013</span></span>](lync-server-2013-define-a-gateway-in-topology-builder.md)

  - [<span data-ttu-id="0df33-116">Установка файлов для сервера-посредника в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0df33-116">Install the files for Mediation Server in Lync Server 2013</span></span>](lync-server-2013-install-the-files-for-mediation-server.md)

  - [<span data-ttu-id="0df33-117">Определение дополнительных магистральных линий в построителе топологий в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0df33-117">Define additional trunks in Topology Builder in Lync Server 2013</span></span>](lync-server-2013-define-additional-trunks-in-topology-builder.md)

</div>

<div>

## <a name="related-sections"></a><span data-ttu-id="0df33-118">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="0df33-118">Related Sections</span></span>

[<span data-ttu-id="0df33-119">Настройка конференц-связи с телефонным подключением в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0df33-119">Configuring dial-in conferencing in Lync Server 2013</span></span>](lync-server-2013-configuring-dial-in-conferencing.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

