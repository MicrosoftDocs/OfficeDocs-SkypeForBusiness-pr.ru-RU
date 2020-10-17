---
title: 'Lync Server 2013: расширения схемы Active Directory, классы и атрибуты, используемые в Lync Server'
description: 'Lync Server 2013: расширения схемы Active Directory, классы и атрибуты, используемые в Lync Server.'
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
ms.openlocfilehash: beac778d3315573f4d5cc6cb9c827a3a2fce9d0e
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48567955"
---
# <a name="active-directory-schema-extensions-classes-and-attributes-used-by-lync-server-2013"></a><span data-ttu-id="467a8-103">Расширения схемы Active Directory, классы и атрибуты, используемые в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="467a8-103">Active Directory schema extensions, classes, and attributes used by Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="467a8-104">_**Последнее изменение темы:** 2012-06-19_</span><span class="sxs-lookup"><span data-stu-id="467a8-104">_**Topic Last Modified:** 2012-06-19_</span></span>

<span data-ttu-id="467a8-105">В этом справочном разделе представлены следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="467a8-105">This reference section includes the following information:</span></span>

  - <span data-ttu-id="467a8-106">Новые или измененные расширения схемы Active Directory для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="467a8-106">Active Directory schema extensions that are new or changed for Lync Server 2013</span></span>
    
    <span data-ttu-id="467a8-107">Схема Active Directory содержит формальные определения каждого класса объектов, который можно создать в лесу Active Directory.</span><span class="sxs-lookup"><span data-stu-id="467a8-107">The Active Directory schema contains formal definitions of every object class that can be created in an Active Directory forest.</span></span> <span data-ttu-id="467a8-108">Схема также содержит формальные определения каждого атрибута в объекте Active Directory.</span><span class="sxs-lookup"><span data-stu-id="467a8-108">The schema also contains formal definitions of every attribute that can exist on an Active Directory object.</span></span> <span data-ttu-id="467a8-109">Глобальный каталог Active Directory содержит реплики всех объектов для леса, а также подмножество атрибутов каждого объекта.</span><span class="sxs-lookup"><span data-stu-id="467a8-109">The Active Directory global catalog contains replicas of all the objects for the forest, along with a subset of the attributes for each object.</span></span> <span data-ttu-id="467a8-110">В этом разделе описываются классы и атрибуты, новые или измененные в Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="467a8-110">This section describes the classes and attributes that are new or changed in Lync Server 2013.</span></span>

  - <span data-ttu-id="467a8-111">Все классы, используемые в Lync Server, с описанием каждого из них.</span><span class="sxs-lookup"><span data-stu-id="467a8-111">All the classes used by Lync Server, with a description of each</span></span>

  - <span data-ttu-id="467a8-112">Все атрибуты, используемые в Lync Server, с описанием каждого из них.</span><span class="sxs-lookup"><span data-stu-id="467a8-112">All the attributes used by Lync Server, with a description of each</span></span>

  - <span data-ttu-id="467a8-113">Список классов, используемых Lync Server, с атрибутами, которые могут содержать</span><span class="sxs-lookup"><span data-stu-id="467a8-113">A list of the classes used by Lync Server, with the attributes each may contain</span></span>

  - <span data-ttu-id="467a8-114">Глобальные параметры и объекты, помимо универсальных групп служб и администрирования, созданных во время подготовки леса</span><span class="sxs-lookup"><span data-stu-id="467a8-114">Global settings and objects, in addition to the universal service and administration groups that are created during forest preparation</span></span>

  - <span data-ttu-id="467a8-115">Записи управления доступом (ACE), которые создаются в корне домена и встроенных контейнерах во время подготовки домена</span><span class="sxs-lookup"><span data-stu-id="467a8-115">Access control entries (ACEs) that are created on the domain root and built-in containers during domain preparation</span></span>

  - <span data-ttu-id="467a8-116">Изменения, вносимые в подразделение Active Directory (OU) с помощью \_ командлета Grant CsSetupPermission.</span><span class="sxs-lookup"><span data-stu-id="467a8-116">Changes that are made on an Active Directory organizational unit (OU) by the Grant\_CsSetupPermission cmdlet.</span></span>

  - <span data-ttu-id="467a8-117">Изменения, вносимые в подразделение Active Directory с помощью \_ командлета Grant CsOUPermission.</span><span class="sxs-lookup"><span data-stu-id="467a8-117">Changes that are made on an Active Directory OU by the Grant\_CsOUPermission cmdlet.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="467a8-118">Содержание</span><span class="sxs-lookup"><span data-stu-id="467a8-118">In This Section</span></span>

  - [<span data-ttu-id="467a8-119">Изменения схемы в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="467a8-119">Schema changes in Lync Server 2013</span></span>](lync-server-2013-schema-changes-in-lync-server-2013.md)

  - [<span data-ttu-id="467a8-120">Классы и описания схемы в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="467a8-120">Schema classes and descriptions in Lync Server 2013</span></span>](lync-server-2013-schema-classes-and-descriptions.md)

  - [<span data-ttu-id="467a8-121">Атрибуты и описания схемы в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="467a8-121">Schema attributes and descriptions in Lync Server 2013</span></span>](lync-server-2013-schema-attributes-and-descriptions.md)

  - [<span data-ttu-id="467a8-122">Атрибуты схемы по классу в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="467a8-122">Schema attributes by class in Lync Server 2013</span></span>](lync-server-2013-schema-attributes-by-class.md)

  - [<span data-ttu-id="467a8-123">Изменения, внесенные при подготовке леса в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="467a8-123">Changes made by forest preparation in Lync Server 2013</span></span>](lync-server-2013-changes-made-by-forest-preparation.md)

  - [<span data-ttu-id="467a8-124">Изменения, внесенные при подготовке домена в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="467a8-124">Changes made by domain preparation in Lync Server 2013</span></span>](lync-server-2013-changes-made-by-domain-preparation.md)

  - [<span data-ttu-id="467a8-125">Изменения, внесенные Grant-CsSetupPermission в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="467a8-125">Changes made by Grant-CsSetupPermission in Lync Server 2013</span></span>](lync-server-2013-changes-made-by-https://docs.microsoft.com/powershell/module/skype/Grant-CsSetupPermission)

  - [<span data-ttu-id="467a8-126">Изменения, внесенные Grant-CsOUPermission в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="467a8-126">Changes made by Grant-CsOUPermission in Lync Server 2013</span></span>](lync-server-2013-changes-made-by-https://docs.microsoft.com/powershell/module/skype/Grant-CsOUPermission)

</div>

</div>

<span> </span>

</div>

</div>

</div>

