---
title: 'Lync Server 2013: сведения об областях сети, сайтах и подсетях'
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
ms.openlocfilehash: f4fe7b93f00ce7af6354fa8a1bc94c104f3af14f
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48523216"
---
# <a name="about-network-regions-sites-and-subnets-in-lync-server-2013"></a>Сведения о регионах сети, сайтах и подсетях в Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2013-02-24_

На расширенные функции корпоративной голосовой связи, описанные в этом разделе, распространяются общие определенные требования относительно конфигурации для регионов сети, сетевых сайтов и подсетей. Например, для всех трех расширенных функций необходимо, чтобы каждая подсеть в топологии была связана с определенным *сетевым сайтом*, а каждый сетевой сайт был связан с *регионом сети*.

<div>


> [!IMPORTANT]  
> Прежде чем приступить к настройке сети для контроля допуска звонков, E9 – 1 – 1 или обхода сервера мультимедиа, убедитесь в том, что вы проверили дополнительные сведения о параметрах сети в <A href="lync-server-2013-network-settings-for-the-advanced-enterprise-voice-features.md">параметрах сети для функций расширенной корпоративной голосовой связи в статье Lync Server 2013</A> в документации по планированию. Сведения о конфигурации сети в основном об управлении допуском звонков также приведены в статье <A href="lync-server-2013-defining-your-requirements-for-call-admission-control.md">Определение требований для контроля допуска звонков в Lync Server 2013</A> в документации по планированию.



</div>

На контроль допуска звонков и E9-1-1 распространяются дополнительные требования относительно конфигурации для сетевых сайтов:

  - Для использования функции контроля допуска звонков необходимо указать *профиль политики пропускной способности* для каждого сайта, на который распространяются ограничения полосы пропускания WAN. Если вы планируете развернуть контроль допуска звонков, необходимо [создать профили политики пропускной способности в Lync Server 2013](lync-server-2013-create-bandwidth-policy-profiles.md) перед настройкой сетевых сайтов.

  - Для использования E9-1-1 необходимо указать *политику расположения* для каждого сайта. Если вы планируете развернуть E9-1-1, необходимо [создать политики расположения в Lync Server 2013](lync-server-2013-create-location-policies.md) перед настройкой сетевых сайтов.

<div>

## <a name="create-or-modify-network-regions-network-sites-and-subnets"></a>Создание или изменение регионов сети, сетевых сайтов и подсетей

В следующих разделах приведены процедуры создания или изменения регионов сети и сетевых сайтов, а также сопоставления подсетей с сетевыми сайтами. В этих разделах не рассматриваются какие-либо определенные расширенные функции корпоративной голосовой связи.

  - [Создание или изменение области сети в Lync Server 2013](lync-server-2013-create-or-modify-a-network-region.md)

  - [Создание или изменение сетевого сайта в Lync Server 2013](lync-server-2013-create-or-modify-a-network-site.md)

  - [Связывание подсети с сетевым сайтом в Lync Server 2013](lync-server-2013-associate-a-subnet-with-a-network-site.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

