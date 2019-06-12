---
title: 'Lync Server 2013: топологии для IP-телефонов'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Topologies for IP phones
ms:assetid: 26ebffcf-43ff-4e70-847d-0fbc90e94e57
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425740(v=OCS.15)
ms:contentKeyID: 48183662
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9d3247783acb0f65fb069f418c4a66a4c53b1a83
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34849355"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="topologies-for-ip-phones-in-lync-server-2013"></a>Топологии для IP-телефонов в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2012-06-21_

В этом разделе представлен обзор процесса подключения и описаны различия между подключением IP-телефона к внутренней и внешней сети.

<div>


> [!NOTE]  
> Lync Server поддерживает следующие IP-телефоны: Aastra 6721ip Common Area Phone, Aastra 6725ip стационарный телефон, HP 4110 IP Phone (на телефонах), HP 4120 IP-телефон (стационарный телефонный звонок), Polycom CX600 IP на стационарном телефоне, Polycom CX700 IP-телефонной сети, Polycom CX500 IP обычный телефон и Polycom CX3000 IP-телефон. Из этих телефонов все, кроме Polycom CX700, могут запускать Lync Phone Edition.



</div>

На приведенной ниже схеме описаны все компоненты, связанные с подключением к устройствам в корпоративной среде.

**Внутренняя топология**

![3d88893e-df57-46e3-855a-a1d24589030a] (images/Gg425740.3d88893e-df57-46e3-855a-a1d24589030a(OCS.15).jpg "3d88893e-df57-46e3-855a-a1d24589030a")

<div>


> [!NOTE]  
> Предыдущий рисунок является логическим представлением, а не физическим обзором. Например, доменные службы Active Directory (AD DS) редко находятся на том же компьютере, что и любые компоненты сервера Lync. Хранилище пользователей может находиться на сервере или на серверах архивации и мониторинга. Консоль управления Lync Server, веб-сервер и службы обновления являются частью роли сервера переднего плана.



</div>

На приведенной ниже схеме представлен обзор компонентов, которые используются, если устройство находится за пределами корпоративной сети.

**Внешняя топология**

![8ce6bb8e-b89c-4c4e-ac6d-41ac6c68f6f3] (images/Gg425740.8ce6bb8e-b89c-4c4e-ac6d-41ac6c68f6f3(OCS.15).jpg "8ce6bb8e-b89c-4c4e-ac6d-41ac6c68f6f3")

<div>


> [!NOTE]  
> Веб-служба обновления устройств обеспечивает внешний и внутренний веб-сайт, но здесь показан только внешний.<BR>Чтобы включить внешний доступ, необходимо опубликовать в службе DNS расположение регистратора и URL-адрес службы обновления устройства для Организации. Кроме того, пограничный сервер должен быть развернут и правильно настроен для разрешения внешней связи с устройства в корпоративную среду и обратно. Этот параметр не указан на предыдущей схеме, так как развертывание EDGE не предназначено для подключения устройства.



</div>

</div>

<span> </span>

</div>

</div>

</div>

