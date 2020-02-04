---
title: 'Lync Server 2013: расширения схемы Active Directory, классы и атрибуты, используемые в Lync Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Active Directory schema extensions, classes, and attributes used by Lync Server 2013
ms:assetid: 579bfa5a-9443-46dd-9a8e-07d00ba2824d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398379(v=OCS.15)
ms:contentKeyID: 48184188
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2ec6b3eff05ba27b41488aea49bb0347d058b6f0
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41735199"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="active-directory-schema-extensions-classes-and-attributes-used-by-lync-server-2013"></a><span data-ttu-id="ca5fe-102">Расширения схемы Active Directory, классы и атрибуты, используемые в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ca5fe-102">Active Directory schema extensions, classes, and attributes used by Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ca5fe-103">_**Тема последнего изменения:** 2012-06-19_</span><span class="sxs-lookup"><span data-stu-id="ca5fe-103">_**Topic Last Modified:** 2012-06-19_</span></span>

<span data-ttu-id="ca5fe-104">Этот справочный раздел содержит указанные ниже сведения.</span><span class="sxs-lookup"><span data-stu-id="ca5fe-104">This reference section includes the following information:</span></span>

  - <span data-ttu-id="ca5fe-105">Новые или измененные расширения схемы Active Directory для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ca5fe-105">Active Directory schema extensions that are new or changed for Lync Server 2013</span></span>
    
    <span data-ttu-id="ca5fe-106">Схема Active Directory включает в себя формальные определения всех классов объектов, которые можно создать в лесу Active Directory.</span><span class="sxs-lookup"><span data-stu-id="ca5fe-106">The Active Directory schema contains formal definitions of every object class that can be created in an Active Directory forest.</span></span> <span data-ttu-id="ca5fe-107">Схема также содержит формальные определения всех атрибутов, которые могут существовать в объекте Active Directory.</span><span class="sxs-lookup"><span data-stu-id="ca5fe-107">The schema also contains formal definitions of every attribute that can exist on an Active Directory object.</span></span> <span data-ttu-id="ca5fe-108">Глобальный каталог Active Directory включает в себя реплики всех объектов для леса, а также подмножество атрибутов для каждого объекта.</span><span class="sxs-lookup"><span data-stu-id="ca5fe-108">The Active Directory global catalog contains replicas of all the objects for the forest, along with a subset of the attributes for each object.</span></span> <span data-ttu-id="ca5fe-109">В этом разделе описаны классы и атрибуты, новые или измененные в Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="ca5fe-109">This section describes the classes and attributes that are new or changed in Lync Server 2013.</span></span>

  - <span data-ttu-id="ca5fe-110">Все классы, используемые в Lync Server, с описанием каждого из них.</span><span class="sxs-lookup"><span data-stu-id="ca5fe-110">All the classes used by Lync Server, with a description of each</span></span>

  - <span data-ttu-id="ca5fe-111">Все атрибуты, используемые в Lync Server, с описанием каждого из них.</span><span class="sxs-lookup"><span data-stu-id="ca5fe-111">All the attributes used by Lync Server, with a description of each</span></span>

  - <span data-ttu-id="ca5fe-112">Список классов, используемых Lync Server, с атрибутами, которые могут содержать</span><span class="sxs-lookup"><span data-stu-id="ca5fe-112">A list of the classes used by Lync Server, with the attributes each may contain</span></span>

  - <span data-ttu-id="ca5fe-113">Глобальные параметры и объекты, в дополнение к универсальным службам и группам администрирования, которые создаются во время подготовки леса</span><span class="sxs-lookup"><span data-stu-id="ca5fe-113">Global settings and objects, in addition to the universal service and administration groups that are created during forest preparation</span></span>

  - <span data-ttu-id="ca5fe-114">Элементы управления доступом (ACE), созданные в корне домена и встроенных контейнерах во время подготовки домена</span><span class="sxs-lookup"><span data-stu-id="ca5fe-114">Access control entries (ACEs) that are created on the domain root and built-in containers during domain preparation</span></span>

  - <span data-ttu-id="ca5fe-115">Изменения, вносимые в подразделение службы каталогов Active Directory (OU) с помощью командлета Grant\_кссетуппермиссион.</span><span class="sxs-lookup"><span data-stu-id="ca5fe-115">Changes that are made on an Active Directory organizational unit (OU) by the Grant\_CsSetupPermission cmdlet.</span></span>

  - <span data-ttu-id="ca5fe-116">Изменения, вносимые в подразделение Active Directory с помощью командлета\_Grant ксаупермиссион.</span><span class="sxs-lookup"><span data-stu-id="ca5fe-116">Changes that are made on an Active Directory OU by the Grant\_CsOUPermission cmdlet.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="ca5fe-117">Содержание</span><span class="sxs-lookup"><span data-stu-id="ca5fe-117">In This Section</span></span>

  - [<span data-ttu-id="ca5fe-118">Изменения схемы в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ca5fe-118">Schema changes in Lync Server 2013</span></span>](lync-server-2013-schema-changes-in-lync-server-2013.md)

  - [<span data-ttu-id="ca5fe-119">Классы схем и описания в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ca5fe-119">Schema classes and descriptions in Lync Server 2013</span></span>](lync-server-2013-schema-classes-and-descriptions.md)

  - [<span data-ttu-id="ca5fe-120">Атрибуты и описания схемы в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ca5fe-120">Schema attributes and descriptions in Lync Server 2013</span></span>](lync-server-2013-schema-attributes-and-descriptions.md)

  - [<span data-ttu-id="ca5fe-121">Атрибуты схемы по классу в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ca5fe-121">Schema attributes by class in Lync Server 2013</span></span>](lync-server-2013-schema-attributes-by-class.md)

  - [<span data-ttu-id="ca5fe-122">Изменения, внесенные в процессе подготовки леса в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ca5fe-122">Changes made by forest preparation in Lync Server 2013</span></span>](lync-server-2013-changes-made-by-forest-preparation.md)

  - [<span data-ttu-id="ca5fe-123">Изменения, внесенные в ходе подготовки домена в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ca5fe-123">Changes made by domain preparation in Lync Server 2013</span></span>](lync-server-2013-changes-made-by-domain-preparation.md)

  - [<span data-ttu-id="ca5fe-124">Изменения, внесенные функцией Grant-Кссетуппермиссион в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ca5fe-124">Changes made by Grant-CsSetupPermission in Lync Server 2013</span></span>](lync-server-2013-changes-made-by-https://docs.microsoft.com/powershell/module/skype/Grant-CsSetupPermission)

  - [<span data-ttu-id="ca5fe-125">Изменения, внесенные функцией Grant-Ксаупермиссион в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ca5fe-125">Changes made by Grant-CsOUPermission in Lync Server 2013</span></span>](lync-server-2013-changes-made-by-https://docs.microsoft.com/powershell/module/skype/Grant-CsOUPermission)

</div>

</div>

<span> </span>

</div>

</div>

</div>

