---
title: Расширения схемы Active Directory, классы и атрибуты
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2016
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 579bfa5a-9443-46dd-9a8e-07d00ba2824d
description: Этот справочный раздел содержит указанные ниже сведения.
ms.openlocfilehash: 98ce04f38d9ee6c572f517441a370823ab7647d5
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815557"
---
# <a name="active-directory-schema-extensions-classes-and-attributes"></a><span data-ttu-id="4468d-103">Расширения схемы Active Directory, классы и атрибуты</span><span class="sxs-lookup"><span data-stu-id="4468d-103">Active Directory schema extensions, classes, and attributes</span></span>
 
<span data-ttu-id="4468d-104">Этот справочный раздел содержит указанные ниже сведения.</span><span class="sxs-lookup"><span data-stu-id="4468d-104">This reference section includes the following information:</span></span> 
  
- <span data-ttu-id="4468d-105">Новые или измененные расширения схемы Active Directory для сервера Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="4468d-105">Active Directory schema extensions that are new or changed for Skype for Business Server</span></span>
    
    <span data-ttu-id="4468d-106">Схема Active Directory включает в себя формальные определения всех классов объектов, которые можно создать в лесу Active Directory.</span><span class="sxs-lookup"><span data-stu-id="4468d-106">The Active Directory schema contains formal definitions of every object class that can be created in an Active Directory forest.</span></span> <span data-ttu-id="4468d-107">Схема также содержит формальные определения всех атрибутов, которые могут существовать в объекте Active Directory.</span><span class="sxs-lookup"><span data-stu-id="4468d-107">The schema also contains formal definitions of every attribute that can exist on an Active Directory object.</span></span> <span data-ttu-id="4468d-108">Глобальный каталог Active Directory включает в себя реплики всех объектов для леса, а также подмножество атрибутов для каждого объекта.</span><span class="sxs-lookup"><span data-stu-id="4468d-108">The Active Directory global catalog contains replicas of all the objects for the forest, along with a subset of the attributes for each object.</span></span> <span data-ttu-id="4468d-109">В этом разделе описаны классы и атрибуты, новые или измененные в Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="4468d-109">This section describes the classes and attributes that are new or changed in Skype for Business Server.</span></span>
    
- <span data-ttu-id="4468d-110">Все классы, используемые в Skype для бизнеса Server, с описанием каждого из них.</span><span class="sxs-lookup"><span data-stu-id="4468d-110">All the classes used by Skype for Business Server, with a description of each</span></span>
    
- <span data-ttu-id="4468d-111">Все атрибуты, используемые в Skype для бизнеса Server, с описанием каждого из них.</span><span class="sxs-lookup"><span data-stu-id="4468d-111">All the attributes used by Skype for Business Server, with a description of each</span></span>
    
- <span data-ttu-id="4468d-112">Список классов, используемых в Skype для бизнеса Server, с атрибутами, которые могут содержать</span><span class="sxs-lookup"><span data-stu-id="4468d-112">A list of the classes used by Skype for Business Server, with the attributes each may contain</span></span>
    
- <span data-ttu-id="4468d-113">Глобальные параметры и объекты, в дополнение к универсальным службам и группам администрирования, которые создаются во время подготовки леса</span><span class="sxs-lookup"><span data-stu-id="4468d-113">Global settings and objects, in addition to the universal service and administration groups that are created during forest preparation</span></span>
    
- <span data-ttu-id="4468d-114">Элементы управления доступом (ACE), созданные в корне домена и встроенных контейнерах во время подготовки домена</span><span class="sxs-lookup"><span data-stu-id="4468d-114">Access control entries (ACEs) that are created on the domain root and built-in containers during domain preparation</span></span>
    
- <span data-ttu-id="4468d-115">Изменения, внесенные в организационное подразделение Active Directory (OU), с помощью командлета Grant_CsSetupPermission.</span><span class="sxs-lookup"><span data-stu-id="4468d-115">Changes that are made on an Active Directory organizational unit (OU) by the Grant_CsSetupPermission cmdlet.</span></span>
    
- <span data-ttu-id="4468d-116">Изменения, внесенные в подразделение Active Directory с помощью командлета Grant_CsOUPermission.</span><span class="sxs-lookup"><span data-stu-id="4468d-116">Changes that are made on an Active Directory OU by the Grant_CsOUPermission cmdlet.</span></span>
    
## <a name="in-this-section"></a><span data-ttu-id="4468d-117">Содержание</span><span class="sxs-lookup"><span data-stu-id="4468d-117">In This Section</span></span>

- [<span data-ttu-id="4468d-118">Изменения схемы в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="4468d-118">Schema changes in Skype for Business Server</span></span>](schema-changes.md)
    
- [<span data-ttu-id="4468d-119">Классы и описания схемы в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="4468d-119">Schema classes and descriptions in Skype for Business Server</span></span>](schema-classes-and-descriptions.md)
    
- [<span data-ttu-id="4468d-120">Атрибуты и описания схемы в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="4468d-120">Schema attributes and descriptions in Skype for Business Server</span></span>](schema-attributes-and-descriptions.md)
    
- [<span data-ttu-id="4468d-121">Атрибуты схемы по классу в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="4468d-121">Schema attributes by class in Skype for Business Server</span></span>](schema-attributes-by-class.md)
    
- [<span data-ttu-id="4468d-122">Изменения, внесенные в процессе подготовки леса в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="4468d-122">Changes made by forest preparation in Skype for Business Server</span></span>](changes-made-by-forest-preparation.md)
    
- [<span data-ttu-id="4468d-123">Изменения, внесенные в ходе подготовки домена в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="4468d-123">Changes made by domain preparation in Skype for Business Server</span></span>](changes-made-by-domain-preparation.md)
    
- [<span data-ttu-id="4468d-124">Изменения, внесенные с помощью GRANT-Кссетуппермиссион в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="4468d-124">Changes made by Grant-CsSetupPermission in Skype for Business Server</span></span>](changes-made-by-grant-cssetuppermission.md)
    
- [<span data-ttu-id="4468d-125">Изменения, внесенные с помощью GRANT-Ксаупермиссион в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="4468d-125">Changes made by Grant-CsOUPermission in Skype for Business Server</span></span>](changes-made-by-grant-csoupermission.md)
    

