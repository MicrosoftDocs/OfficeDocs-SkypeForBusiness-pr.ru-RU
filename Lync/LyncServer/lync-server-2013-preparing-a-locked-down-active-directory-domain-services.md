---
title: 'Lync Server 2013: подготовка заблокированных доменных служб Active Directory'
description: 'Lync Server 2013: подготовка заблокированных доменных служб Active Directory.'
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
ms.openlocfilehash: 4aea04b138de2630935713eda7cbef9e4d21572a
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48566305"
---
# <a name="preparing-a-locked-down-active-directory-domain-services-in-lync-server-2013"></a><span data-ttu-id="6f5c8-103">Подготовка заблокированных доменных служб Active Directory в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6f5c8-103">Preparing a locked-down Active Directory Domain Services in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6f5c8-104">_**Последнее изменение темы:** 2012-05-14_</span><span class="sxs-lookup"><span data-stu-id="6f5c8-104">_**Topic Last Modified:** 2012-05-14_</span></span>

<span data-ttu-id="6f5c8-105">Организации часто блокируют доменные службы Active Directory, чтобы снизить риски безопасности.</span><span class="sxs-lookup"><span data-stu-id="6f5c8-105">Organizations often lock down Active Directory Domain Services to help mitigate security risks.</span></span> <span data-ttu-id="6f5c8-106">Однако заблокированная среда Active Directory может ограничить разрешения, необходимые для Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="6f5c8-106">However, a locked-down Active Directory environment can limit the permissions that Lync Server 2013 requires.</span></span> <span data-ttu-id="6f5c8-107">Правильная подготовка заблокированной среды Active Directory для Lync Server 2013 включает некоторые дополнительные соображения и действия.</span><span class="sxs-lookup"><span data-stu-id="6f5c8-107">Properly preparing a locked-down Active Directory environment for Lync Server 2013 involves some additional considerations and steps.</span></span>

<span data-ttu-id="6f5c8-108">Обычно разрешения в заблокированной среде Active Directory ограничиваются двумя способами.</span><span class="sxs-lookup"><span data-stu-id="6f5c8-108">Two common ways in which permissions are limited in a locked-down Active Directory environment are as follows:</span></span>

  - <span data-ttu-id="6f5c8-109">Элементы управления доступом (ACE) прошедшего проверку пользователя удаляются из контейнеров.</span><span class="sxs-lookup"><span data-stu-id="6f5c8-109">Authenticated user access control entries (ACEs) are removed from containers.</span></span>

  - <span data-ttu-id="6f5c8-110">Наследование разрешений отключается для контейнеров объектов User, Contact, InetOrgPerson или Computer.</span><span class="sxs-lookup"><span data-stu-id="6f5c8-110">Permissions inheritance is disabled on containers of User, Contact, InetOrgPerson, or Computer objects.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="6f5c8-111">Содержание</span><span class="sxs-lookup"><span data-stu-id="6f5c8-111">In This Section</span></span>

  - [<span data-ttu-id="6f5c8-112">Разрешения для пользователей, прошедших проверку подлинности, удалены в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6f5c8-112">Authenticated user permissions are removed in Lync Server 2013</span></span>](lync-server-2013-authenticated-user-permissions-are-removed.md)

  - [<span data-ttu-id="6f5c8-113">Наследование разрешений отключено на компьютерах, пользователях и контейнерах InetOrgPerson в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6f5c8-113">Permissions inheritance Is disabled on computers, users, or InetOrgPerson containers in Lync Server 2013</span></span>](lync-server-2013-permissions-inheritance-is-disabled-on-computers-users-or-inetorgperson-containers.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

