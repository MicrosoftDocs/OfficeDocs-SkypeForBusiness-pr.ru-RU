---
title: Развертывание устройства для обеспечения связи в филиалах или задач сервера-центрального сайта
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying a Survivable Branch Appliance or Server - central site tasks
ms:assetid: 0f631a36-fc2e-41cd-8a0d-f27e84f4a89e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398189(v=OCS.15)
ms:contentKeyID: 48183422
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8ebb3dd9fbeeaed69951ac11ee780bbe8d371a86
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48531366"
---
# <a name="deploying-a-survivable-branch-appliance-or-server-with-lync-server-2013---central-site-tasks"></a>Развертывание устройства или сервера для обеспечения связи в филиалах с помощью Lync Server 2013-Central Site Tasks

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-10-18_

Выполните задачи, описанные в данном разделе, на центральном сайте. Если вы развертываете сервер для обеспечения связи в филиалах, пропустите первую задачу.

<div>


> [!IMPORTANT]
> Перед выполнением данных задач следует обеспечить выполнение следующих условий: 
> <UL>
> <LI>
> <P>Lync Server должен быть настроен на центральном сайте.</P>
> <LI>
> <P>Следует добавить техника по установке на сайте филиала в группу RTCUniversalSBATechnicians.</P></LI></UL>Кроме того, мы рекомендуем вам выполнить следующее:
> <UL>
> <LI>
> <P>Разверните DHCP-сервер на каждом сайте филиала, чтобы клиенты могли получать IP-адреса.</P>
> <LI>
> <P>В качестве альтернативы развертыванию DHCP-сервера на каждом сайте филиала включите службу DHCP Lync Server на устройстве для обеспечения связи в филиалах или сервере для обеспечения связи в филиалах с помощью командлета командной консоли Lync Server <STRONG>Set-CsRegistrarConfiguration – енабледхкпсервер $true</STRONG>. Для получения дополнительных сведений обратитесь к разделу "требования к оборудованию и программному обеспечению" <A href="lync-server-2013-branch-site-resiliency-requirements.md">для обеспечения устойчивости сайта филиала для Lync Server 2013</A> в документации по планированию.</P></LI></UL>



</div>

<div>

## <a name="in-this-section"></a>Содержание

  - [Добавление устройства для обеспечения связи в филиалах в Active Directory в Lync Server 2013](lync-server-2013-add-a-survivable-branch-appliance-to-active-directory.md)

  - [Добавление сайтов филиалов в топологию в Lync Server 2013](lync-server-2013-add-branch-sites-to-your-topology.md)

  - [Определение устройства или сервера для обеспечения связи в филиалах в Lync Server 2013](lync-server-2013-define-a-survivable-branch-appliance-or-server.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

