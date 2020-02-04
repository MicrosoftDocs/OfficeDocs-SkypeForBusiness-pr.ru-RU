---
title: Развертывание устройства или сервера для обеспечения связи в филиалах — задачи центрального сайта
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
ms.openlocfilehash: a9aa6d38ec873652feae6ef6a374ee5b771520b1
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41729629"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploying-a-survivable-branch-appliance-or-server-with-lync-server-2013---central-site-tasks"></a>Развертывание устройства или сервера для обеспечения связи в филиалах с помощью Lync Server 2013 — задачи центрального сайта

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2012-10-18_

Выполните задачи, описанные в этом разделе, на центральном сайте. Если вы развертываете бесперебойный сервер филиала, пропустите первую задачу.

<div>


> [!IMPORTANT]
> Перед выполнением задач, описанных в этом разделе, должны быть выполнены следующие условия: 
> <UL>
> <LI>
> <P>Сервер Lync Server должен быть настроен на центральном сайте.</P>
> <LI>
> <P>Специалист по установке на сайте филиала должен быть добавлен в группу РткуниверсалсбатечниЦианс.</P></LI></UL>Кроме того, мы рекомендуем вам выполнить указанные ниже действия.
> <UL>
> <LI>
> <P>Разверните DHCP-сервер на каждом сайте филиала, чтобы разрешить клиентам получать IP-адреса.</P>
> <LI>
> <P>Кроме того, чтобы развернуть DHCP-сервер на каждом сайте филиала, включите службу DHCP для Lync Server на устройстве с бесперебойной ветвью или работающем сервере филиала с помощью командлета оболочки Lync Server Management Shell <STRONG>Set-ксрегистрарконфигуратион-енабледхкпсервер $true</STRONG>. Подробные сведения можно найти в разделе Требования к оборудованию и программному обеспечению <A href="lync-server-2013-branch-site-resiliency-requirements.md">для обеспечения устойчивости сайтов для Lync Server 2013</A> в документации по планированию.</P></LI></UL>



</div>

<div>

## <a name="in-this-section"></a>Содержание

  - [Добавление устройства для обеспечения связи в филиалах к Active Directory в Lync Server 2013](lync-server-2013-add-a-survivable-branch-appliance-to-active-directory.md)

  - [Добавление сайтов филиалов в топологию в Lync Server 2013](lync-server-2013-add-branch-sites-to-your-topology.md)

  - [Определение устройства или сервера для обеспечения связи в филиалах в Lync Server 2013](lync-server-2013-define-a-survivable-branch-appliance-or-server.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

