---
title: 'Lync Server 2013: подготовка заблокированных доменных служб Active Directory'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Preparing a locked-down Active Directory Domain Services
ms:assetid: 68bde963-3fa3-4102-88d6-ac931c1dd2d7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398492(v=OCS.15)
ms:contentKeyID: 48184377
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ae8ea746ba8ea2ddea8d696d42865324da60ecbc
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42152577"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="preparing-a-locked-down-active-directory-domain-services-in-lync-server-2013"></a>Подготовка заблокированных доменных служб Active Directory в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-05-14_

Организации часто блокируют доменные службы Active Directory, чтобы снизить риски безопасности. Однако заблокированная среда Active Directory может ограничить разрешения, необходимые для Lync Server 2013. Правильная подготовка заблокированной среды Active Directory для Lync Server 2013 включает некоторые дополнительные соображения и действия.

Обычно разрешения в заблокированной среде Active Directory ограничиваются двумя способами.

  - Элементы управления доступом (ACE) прошедшего проверку пользователя удаляются из контейнеров.

  - Наследование разрешений отключается для контейнеров объектов User, Contact, InetOrgPerson или Computer.

<div>

## <a name="in-this-section"></a>Содержание

  - [Разрешения для пользователей, прошедших проверку подлинности, удалены в Lync Server 2013](lync-server-2013-authenticated-user-permissions-are-removed.md)

  - [Наследование разрешений отключено на компьютерах, пользователях и контейнерах InetOrgPerson в Lync Server 2013](lync-server-2013-permissions-inheritance-is-disabled-on-computers-users-or-inetorgperson-containers.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

