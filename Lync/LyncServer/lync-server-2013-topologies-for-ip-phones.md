---
title: 'Lync Server 2013: топологии для IP-телефонов'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Topologies for IP phones
ms:assetid: 26ebffcf-43ff-4e70-847d-0fbc90e94e57
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425740(v=OCS.15)
ms:contentKeyID: 48183662
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 36afef4fe357e79f1d6c9579273262b265d2c0ad
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42193572"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="topologies-for-ip-phones-in-lync-server-2013"></a>Топологии для IP-телефонов в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-06-21_

В этом разделе приводится обзор процесса подключения и рассматриваются различия в способах подключения IP-телефона во внутренней и внешней сетях.

<div>


> [!NOTE]  
> Lync Server обеспечивает поддержку для следующих IP-телефонов: Aastra 6721ip Common Area Phone, Aastra 6725ip стационарный телефон, HP 4110 IP-телефон (телефон с общим доступом), HP 4120 IP-телефон (стационарный телефон), Polycom CX600 IP Desk Phone, Polycom CX700 IP Desk Phone, Polycom CX500 IP Телефон общего пользования и Polycom CX3000 IP-телефон. Из этих телефонов все, кроме Polycom CX700, могут запускать Lync Phone Edition.



</div>

На следующей схеме показаны все компоненты, используемые для связи между устройствами в корпоративной среде.

**Внутренняя топология**

![3d88893e-df57-46e3-855a-a1d24589030a](images/Gg425740.3d88893e-df57-46e3-855a-a1d24589030a(OCS.15).jpg "3d88893e-df57-46e3-855a-a1d24589030a")

<div>


> [!NOTE]  
> Выше представлена логическая схема, которая не отражает особенности физического размещения. Например, доменные службы Active Directory (AD DS) редко располагаются на том же компьютере, что и компоненты Lync Server. Хранилище пользователя может располагаться на тыловом сервере или на сервере архивации и наблюдения. Консоль управления Lync Server, веб-сервер и службы обновления являются частью роли сервера переднего плана.



</div>

На следующей схеме приводится обзор компонентов, используемых в том случае, если устройство находится за пределами корпоративной сети.

**Внешняя топология**

![8ce6bb8e-b89c-4c4e-ac6d-41ac6c68f6f3](images/Gg425740.8ce6bb8e-b89c-4c4e-ac6d-41ac6c68f6f3(OCS.15).jpg "8ce6bb8e-b89c-4c4e-ac6d-41ac6c68f6f3")

<div>


> [!NOTE]  
> Веб-служба обновления устройств предоставляет внешний и внутренний веб-сайты, но здесь показан только внешний веб-сайт.<BR>Если планируется включать внешний доступ, в DNS необходимо опубликовать расположение Регистратора и URL-адрес веб-службы обновления устройств для организации. Кроме того, для обеспечения внешних подключений устройств к корпоративной среде и наоборот нужно развернуть и правильно настроить пограничный сервер. На предыдущей схеме этот компонент не показан, поскольку развертывание пограничного сервера не является необходимым для подключения устройств.



</div>

</div>

<span> </span>

</div>

</div>

</div>

