---
title: 'Lync Server 2013: связывание подсетей с сетевыми сайтами для обхода сервера-посредника'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Associate subnets with network sites for media bypass
ms:assetid: 5bc632b7-1446-470f-b332-48ea0ca4d1fd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398401(v=OCS.15)
ms:contentKeyID: 48184244
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 911a6a91d0797e6d09942cbc2a4ef2af7ff00ce4
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48531566"
---
# <a name="associate-subnets-with-network-sites-for-media-bypass-in-lync-server-2013"></a>Связывание подсетей с сетевыми сайтами для обхода сервера-посредника в Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-09-12_

<div>


> [!NOTE]  
> В этом разделе предполагается, что параметры обхода сервера-посредника настроены, и что имеются настроенные области сети и сетевые узлы для обхода сервера-посредника.



</div>

Каждая подсеть в вашей сети должна быть связана с конкретным сетевым узлом, поскольку информация подсети используется для определения сетевого узла, в котором расположена конечная точка. Когда известны расположения обеих сторон сеанса, обход сервера-посредника может определить, куда следует отправлять мультимедиа для обработки.

Для обхода сервера-посредника не существуют какие-либо особые требования относительно связи подсетей с сетевыми узлами. Чтобы создать связь между подсетями и сетевыми сайтами в топологии, выполните процедуры, описанные в разделе [связывание подсети с сетевым сайтом в Lync Server 2013](lync-server-2013-associate-a-subnet-with-a-network-site.md).

<div>

## <a name="next-steps-create-bandwidth-policy-profiles"></a>Следующие действия: создание профилей политик пропускной способности

После создания связи подсетей с сетевыми узлами для обхода сервера-посредника необходимо создать хотя бы один профиль политики пропускной способности, который для осуществления обхода сервера-посредника будет разделять сети на имеющие хорошие возможности подключения и на не имеющие таких возможностей. Все подсети в области сети с сетевыми узлами, в которых отсутствуют ограничения пропускной способности, имеют хорошие возможности подключения и, следовательно, могут использовать обход сервера-посредника.

Процедуры настройки профилей политики пропускной способности приведены [в статье Create Profile Policy Profiles in Lync Server 2013](lync-server-2013-create-bandwidth-policy-profiles.md).

</div>

</div>

<span> </span>

</div>

</div>

</div>

