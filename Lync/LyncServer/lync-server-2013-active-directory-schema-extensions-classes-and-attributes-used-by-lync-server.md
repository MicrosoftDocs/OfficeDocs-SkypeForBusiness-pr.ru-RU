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
ms.openlocfilehash: e393c5c65e77f22763380563e61c30bcdb69b23a
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42145057"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="active-directory-schema-extensions-classes-and-attributes-used-by-lync-server-2013"></a><span data-ttu-id="9a924-102">Расширения схемы Active Directory, классы и атрибуты, используемые в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9a924-102">Active Directory schema extensions, classes, and attributes used by Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9a924-103">_**Последнее изменение темы:** 2012-06-19_</span><span class="sxs-lookup"><span data-stu-id="9a924-103">_**Topic Last Modified:** 2012-06-19_</span></span>

<span data-ttu-id="9a924-104">В этом справочном разделе представлены следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="9a924-104">This reference section includes the following information:</span></span>

  - <span data-ttu-id="9a924-105">Новые или измененные расширения схемы Active Directory для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9a924-105">Active Directory schema extensions that are new or changed for Lync Server 2013</span></span>
    
    <span data-ttu-id="9a924-106">Схема Active Directory содержит формальные определения каждого класса объектов, который можно создать в лесу Active Directory.</span><span class="sxs-lookup"><span data-stu-id="9a924-106">The Active Directory schema contains formal definitions of every object class that can be created in an Active Directory forest.</span></span> <span data-ttu-id="9a924-107">Схема также содержит формальные определения каждого атрибута в объекте Active Directory.</span><span class="sxs-lookup"><span data-stu-id="9a924-107">The schema also contains formal definitions of every attribute that can exist on an Active Directory object.</span></span> <span data-ttu-id="9a924-108">Глобальный каталог Active Directory содержит реплики всех объектов для леса, а также подмножество атрибутов каждого объекта.</span><span class="sxs-lookup"><span data-stu-id="9a924-108">The Active Directory global catalog contains replicas of all the objects for the forest, along with a subset of the attributes for each object.</span></span> <span data-ttu-id="9a924-109">В этом разделе описываются классы и атрибуты, новые или измененные в Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="9a924-109">This section describes the classes and attributes that are new or changed in Lync Server 2013.</span></span>

  - <span data-ttu-id="9a924-110">Все классы, используемые в Lync Server, с описанием каждого из них.</span><span class="sxs-lookup"><span data-stu-id="9a924-110">All the classes used by Lync Server, with a description of each</span></span>

  - <span data-ttu-id="9a924-111">Все атрибуты, используемые в Lync Server, с описанием каждого из них.</span><span class="sxs-lookup"><span data-stu-id="9a924-111">All the attributes used by Lync Server, with a description of each</span></span>

  - <span data-ttu-id="9a924-112">Список классов, используемых Lync Server, с атрибутами, которые могут содержать</span><span class="sxs-lookup"><span data-stu-id="9a924-112">A list of the classes used by Lync Server, with the attributes each may contain</span></span>

  - <span data-ttu-id="9a924-113">Глобальные параметры и объекты, помимо универсальных групп служб и администрирования, созданных во время подготовки леса</span><span class="sxs-lookup"><span data-stu-id="9a924-113">Global settings and objects, in addition to the universal service and administration groups that are created during forest preparation</span></span>

  - <span data-ttu-id="9a924-114">Записи управления доступом (ACE), которые создаются в корне домена и встроенных контейнерах во время подготовки домена</span><span class="sxs-lookup"><span data-stu-id="9a924-114">Access control entries (ACEs) that are created on the domain root and built-in containers during domain preparation</span></span>

  - <span data-ttu-id="9a924-115">Изменения, вносимые в подразделение Active Directory (OU) с помощью командлета Grant\_CsSetupPermission.</span><span class="sxs-lookup"><span data-stu-id="9a924-115">Changes that are made on an Active Directory organizational unit (OU) by the Grant\_CsSetupPermission cmdlet.</span></span>

  - <span data-ttu-id="9a924-116">Изменения, вносимые в подразделение Active Directory с помощью командлета\_Grant CsOUPermission.</span><span class="sxs-lookup"><span data-stu-id="9a924-116">Changes that are made on an Active Directory OU by the Grant\_CsOUPermission cmdlet.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="9a924-117">Содержание</span><span class="sxs-lookup"><span data-stu-id="9a924-117">In This Section</span></span>

  - [<span data-ttu-id="9a924-118">Изменения схемы в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9a924-118">Schema changes in Lync Server 2013</span></span>](lync-server-2013-schema-changes-in-lync-server-2013.md)

  - [<span data-ttu-id="9a924-119">Классы и описания схемы в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9a924-119">Schema classes and descriptions in Lync Server 2013</span></span>](lync-server-2013-schema-classes-and-descriptions.md)

  - [<span data-ttu-id="9a924-120">Атрибуты и описания схемы в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9a924-120">Schema attributes and descriptions in Lync Server 2013</span></span>](lync-server-2013-schema-attributes-and-descriptions.md)

  - [<span data-ttu-id="9a924-121">Атрибуты схемы по классу в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9a924-121">Schema attributes by class in Lync Server 2013</span></span>](lync-server-2013-schema-attributes-by-class.md)

  - [<span data-ttu-id="9a924-122">Изменения, внесенные при подготовке леса в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9a924-122">Changes made by forest preparation in Lync Server 2013</span></span>](lync-server-2013-changes-made-by-forest-preparation.md)

  - [<span data-ttu-id="9a924-123">Изменения, внесенные при подготовке домена в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9a924-123">Changes made by domain preparation in Lync Server 2013</span></span>](lync-server-2013-changes-made-by-domain-preparation.md)

  - [<span data-ttu-id="9a924-124">Изменения, внесенные с помощью GRANT – CsSetupPermission в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9a924-124">Changes made by Grant-CsSetupPermission in Lync Server 2013</span></span>](lync-server-2013-changes-made-by-https://docs.microsoft.com/powershell/module/skype/Grant-CsSetupPermission)

  - [<span data-ttu-id="9a924-125">Изменения, внесенные с помощью Grant – CsOUPermission в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9a924-125">Changes made by Grant-CsOUPermission in Lync Server 2013</span></span>](lync-server-2013-changes-made-by-https://docs.microsoft.com/powershell/module/skype/Grant-CsOUPermission)

</div>

</div>

<span> </span>

</div>

</div>

</div>

