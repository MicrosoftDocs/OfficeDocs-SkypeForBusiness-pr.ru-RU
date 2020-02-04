---
title: 'Lync Server 2013: подготовка доменных служб Active Directory'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Preparing Active Directory Domain Services for Lync Server 2013
ms:assetid: 7e126464-5d29-4013-9c44-0ccc2fbdea0f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398630(v=OCS.15)
ms:contentKeyID: 48184620
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: da033b8b7589b5257a73d77f3cd618236a2e4747
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41724989"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="preparing-active-directory-domain-services-for-lync-server-2013"></a><span data-ttu-id="0f271-102">Подготовка доменных служб Active Directory для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0f271-102">Preparing Active Directory Domain Services for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0f271-103">_**Тема последнего изменения:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="0f271-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="0f271-104">Перед развертыванием и эксплуатацией Lync Server 2013 необходимо подготовить доменные службы Active Directory, расширив схему, а затем создав и настроив объекты.</span><span class="sxs-lookup"><span data-stu-id="0f271-104">Before you deploy and operate Lync Server 2013, you must prepare Active Directory Domain Services by extending the schema and then creating and configuring objects.</span></span> <span data-ttu-id="0f271-105">Расширения схемы добавляют классы и атрибуты Active Directory, необходимые для Lync Server.</span><span class="sxs-lookup"><span data-stu-id="0f271-105">The schema extensions add the Active Directory classes and attributes that are required by Lync Server.</span></span>

<span data-ttu-id="0f271-106">В этом разделе описывается подготовка доменных служб Active Directory для развертывания Lync Server и назначение разрешений на настройку и разрешения организационных подразделений (OU).</span><span class="sxs-lookup"><span data-stu-id="0f271-106">The topics in this section describe how to prepare AD DS for deploying Lync Server and how to assign setup and organizational unit (OU) permissions.</span></span> <span data-ttu-id="0f271-107">Дополнительные сведения об изменениях схемы, необходимых для Lync Server, можно найти в разделе [расширения схемы Active Directory, классы и атрибуты, используемые в Lync server 2013](lync-server-2013-active-directory-schema-extensions-classes-and-attributes-used-by-lync-server.md).</span><span class="sxs-lookup"><span data-stu-id="0f271-107">For details about the schema changes required for Lync Server, see [Active Directory schema extensions, classes, and attributes used by Lync Server 2013](lync-server-2013-active-directory-schema-extensions-classes-and-attributes-used-by-lync-server.md).</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="0f271-108">Содержание</span><span class="sxs-lookup"><span data-stu-id="0f271-108">In This Section</span></span>

  - [<span data-ttu-id="0f271-109">Требования к инфраструктуре Active Directory для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0f271-109">Active Directory infrastructure requirements for Lync Server 2013</span></span>](lync-server-2013-active-directory-infrastructure-requirements.md)

  - [<span data-ttu-id="0f271-110">Обзор подготовки доменных служб Active Directory в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0f271-110">Overview of Active Directory Domain Services preparation in Lync Server 2013</span></span>](lync-server-2013-overview-of-active-directory-domain-services-preparation.md)

  - [<span data-ttu-id="0f271-111">Подготовка доменных служб Active Directory в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0f271-111">Preparing Active Directory Domain Services in Lync Server 2013</span></span>](lync-server-2013-preparing-active-directory-domain-services_1.md)

  - [<span data-ttu-id="0f271-112">Подготовка заблокированных доменных служб Active Directory в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0f271-112">Preparing a locked-down Active Directory Domain Services in Lync Server 2013</span></span>](lync-server-2013-preparing-a-locked-down-active-directory-domain-services.md)

  - [<span data-ttu-id="0f271-113">Предоставление разрешений в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0f271-113">Granting permissions in Lync Server 2013</span></span>](lync-server-2013-granting-permissions.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

