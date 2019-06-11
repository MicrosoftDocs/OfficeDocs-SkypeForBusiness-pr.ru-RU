---
title: 'Lync Server 2013: подготовка заблокированных доменных служб Active Directory'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Preparing a locked-down Active Directory Domain Services
ms:assetid: 68bde963-3fa3-4102-88d6-ac931c1dd2d7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398492(v=OCS.15)
ms:contentKeyID: 48184377
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 482c5a59c6dc53fc712db7e77430367dd9c37af5
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34823940"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="preparing-a-locked-down-active-directory-domain-services-in-lync-server-2013"></a>Подготовка заблокированных доменных служб Active Directory в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2012-05-14_

Организации часто заблокировали доменные службы Active Directory, чтобы снизить риски безопасности. Однако заблокированная среда Active Directory может ограничивать разрешения, необходимые для Lync Server 2013. Правильная подготовка заблокированной среды Active Directory для Lync Server 2013 включает некоторые дополнительные аспекты и инструкции.

Два распространенных способа ограничения разрешений в заблокированной среде Active Directory описаны ниже.

  - Элементы управления доступом пользователей, прошедшие проверку подлинности, удаляются из контейнеров.

  - Наследование разрешений отключено для контейнеров пользователей, контактов, InetOrgPerson или объектов компьютера.

<div>

## <a name="in-this-section"></a>Содержание

  - [Удаление разрешений пользователей, прошедших проверку подлинности в Lync Server 2013](lync-server-2013-authenticated-user-permissions-are-removed.md)

  - [Заблокировано наследование разрешений для компьютеров, пользователей и контейнеров inetOrgPerson в Lync Server 2013](lync-server-2013-permissions-inheritance-is-disabled-on-computers-users-or-inetorgperson-containers.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

