---
title: 'Lync Server 2013: о сетевых областях, сайтах и подсетях'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: About network regions, sites, and subnets
ms:assetid: 6662123a-d011-408c-a290-92b2a8589943
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398467(v=OCS.15)
ms:contentKeyID: 48184335
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1f85d392f7d5f987bf14197fd5027c6568965ae8
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41723429"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="about-network-regions-sites-and-subnets-in-lync-server-2013"></a>О сетевых областях, сайтах и подсетях в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2013-02-24_

В этой статье описаны дополнительные требования к конфигурации для регионов сети, сайтов сети и подсетей. Например, для всех трех дополнительных функций требуется, чтобы каждая подсеть в топологии была связана с конкретным *сетевым сайтом*, а каждый сетевой сайт должен быть связан с *сетевым регионом*.

<div>


> [!IMPORTANT]  
> Прежде чем приступить к настройке сети для управления допуском звонков, E9-1-1 или мультимедиа, убедитесь, что вы просматриваете дополнительные сведения о параметрах сети в разделе <A href="lync-server-2013-network-settings-for-the-advanced-enterprise-voice-features.md">Параметры сети для расширенных функций голосовой связи в Lync Server 2013</A> в документации по планированию. Сведения о конфигурации сети в основном для управления допуском звонков также можно найти <A href="lync-server-2013-defining-your-requirements-for-call-admission-control.md">в разделе Определение требований к управлению допуском звонков в Lync Server 2013</A> в документации по планированию.



</div>

На контроль допуска звонков и E9-1-1 распространяются дополнительные требования относительно конфигурации для сетевых сайтов:

  - Для использования функции контроля допуска звонков необходимо указать *профиль политики пропускной способности* для каждого сайта, на который распространяются ограничения полосы пропускания WAN. Если вы планируете развернуть управление допуском звонков, необходимо [создать профили политики пропускной способности в Lync Server 2013](lync-server-2013-create-bandwidth-policy-profiles.md) перед настройкой сайтов сети.

  - Для использования E9-1-1 необходимо указать *политику расположения* для каждого сайта. Если вы планируете развернуть E9-1-1, необходимо [создать политики местоположений в Lync Server 2013](lync-server-2013-create-location-policies.md) перед настройкой сетевых сайтов.

<div>

## <a name="create-or-modify-network-regions-network-sites-and-subnets"></a>Создание и изменение регионов сети, сайтов сети и подсетей

Ниже описаны действия, которые можно использовать для создания и изменения областей сети и сетевых сайтов, а также для сопоставления подсетей с сетевыми сайтами. Эти темы не относятся к конкретным дополнительным функциям расширенной корпоративной голосовой связи.

  - [Создание или изменение сетевого региона в Lync Server 2013](lync-server-2013-create-or-modify-a-network-region.md)

  - [Создание или изменение сетевого сайта в Lync Server 2013](lync-server-2013-create-or-modify-a-network-site.md)

  - [Связь подсети с сетевым сайтом в Lync Server 2013](lync-server-2013-associate-a-subnet-with-a-network-site.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

