---
title: 'Lync Server 2013: компоненты, необходимые для директора'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Components required for the Director
ms:assetid: 15c7c8d4-b93f-4386-b2d1-d76dab8f801e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398228(v=OCS.15)
ms:contentKeyID: 48183502
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 84a5765ce21ba955e4354c693171180a9d828210
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42204705"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="components-required-for-the-director-in-lync-server-2013"></a>Компоненты, необходимые для директора в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-09-08_

Единственным компонентом, необходимым для создания и настройки директора, является развертывание роли сервера Director. Это можно сделать с помощью построителя топологий и определить один пул компьютеров или пул из нескольких компьютеров в узле "директор пула". Определив директор или пул директоров, запустите мастер развертывания Lync Server на компьютере, который будет директор. В случае пула директоров мастер развертывания Lync Server запускается на каждом сервере, который будет участником пула.

<div>

## <a name="topologies"></a>Топологии

Вы можете реализовать один сервер директоров или пул директоров. Директор всегда является отдельным сервером или пулом, но не связан с какой-либо другой ролью сервера в Lync Server 2013.

<div>


> [!NOTE]  
> Если вы не развертываете режиссеров, роль директора будет возлагаться на сервер переднего плана или интерфейсный пул.



</div>

Необходимо сбалансировать балансировку нагрузки для пула директоров. Для этого можно выполнить одно из следующих действий.

  - Создать топологию, которая использует аппаратный балансировщик нагрузки для веб-служб и балансировку нагрузки на DNS для остальных типов трафика.
    
    [Масштабируемый пул директоров — балансировка нагрузки на DNS и аппаратный балансировщик нагрузки в Lync Server 2013](lync-server-2013-scaled-director-pool-dns-load-balancing-and-hardware-load-balancer.md)

  - Создайте топологию, использующую аппаратную подсистему балансировки нагрузки для балансировки нагрузки, необходимой для пула директоров.
    
    [Масштабируемый пул директоров — аппаратный балансировщик нагрузки в Lync Server 2013](lync-server-2013-scaled-director-pool-hardware-load-balancer.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

