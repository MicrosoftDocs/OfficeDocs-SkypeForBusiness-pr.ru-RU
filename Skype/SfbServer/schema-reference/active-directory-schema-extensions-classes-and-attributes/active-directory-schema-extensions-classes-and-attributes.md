---
title: Расширения схемы Active Directory, классы и атрибуты
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/1/2016
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 579bfa5a-9443-46dd-9a8e-07d00ba2824d
description: 'В этом справочном разделе представлены следующие сведения:'
ms.openlocfilehash: 5c8a1ceb6b623466219cbd3df46ff2b39ccceb2c
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831939"
---
# <a name="active-directory-schema-extensions-classes-and-attributes"></a><span data-ttu-id="211d7-103">Расширения схемы Active Directory, классы и атрибуты</span><span class="sxs-lookup"><span data-stu-id="211d7-103">Active Directory schema extensions, classes, and attributes</span></span>
 
<span data-ttu-id="211d7-104">В этом справочном разделе представлены следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="211d7-104">This reference section includes the following information:</span></span> 
  
- <span data-ttu-id="211d7-105">Новые или измененные расширения схемы Active Directory для Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="211d7-105">Active Directory schema extensions that are new or changed for Skype for Business Server</span></span>
    
    <span data-ttu-id="211d7-106">Схема Active Directory содержит формальные определения каждого класса объектов, который можно создать в лесу Active Directory.</span><span class="sxs-lookup"><span data-stu-id="211d7-106">The Active Directory schema contains formal definitions of every object class that can be created in an Active Directory forest.</span></span> <span data-ttu-id="211d7-107">Схема также содержит формальные определения каждого атрибута в объекте Active Directory.</span><span class="sxs-lookup"><span data-stu-id="211d7-107">The schema also contains formal definitions of every attribute that can exist on an Active Directory object.</span></span> <span data-ttu-id="211d7-108">Глобальный каталог Active Directory содержит реплики всех объектов для леса, а также подмножество атрибутов каждого объекта.</span><span class="sxs-lookup"><span data-stu-id="211d7-108">The Active Directory global catalog contains replicas of all the objects for the forest, along with a subset of the attributes for each object.</span></span> <span data-ttu-id="211d7-109">В этом разделе описываются новые или измененные классы и атрибуты в Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="211d7-109">This section describes the classes and attributes that are new or changed in Skype for Business Server.</span></span>
    
- <span data-ttu-id="211d7-110">Все классы, используемые Skype для бизнеса Server, с описанием каждого из них</span><span class="sxs-lookup"><span data-stu-id="211d7-110">All the classes used by Skype for Business Server, with a description of each</span></span>
    
- <span data-ttu-id="211d7-111">Все атрибуты, используемые Skype для бизнеса Server, с описанием каждого из них</span><span class="sxs-lookup"><span data-stu-id="211d7-111">All the attributes used by Skype for Business Server, with a description of each</span></span>
    
- <span data-ttu-id="211d7-112">Список классов, используемых Skype для бизнеса Server, с атрибутами, которые могут содержать</span><span class="sxs-lookup"><span data-stu-id="211d7-112">A list of the classes used by Skype for Business Server, with the attributes each may contain</span></span>
    
- <span data-ttu-id="211d7-113">Глобальные параметры и объекты, помимо универсальных групп служб и администрирования, созданных во время подготовки леса</span><span class="sxs-lookup"><span data-stu-id="211d7-113">Global settings and objects, in addition to the universal service and administration groups that are created during forest preparation</span></span>
    
- <span data-ttu-id="211d7-114">Записи управления доступом (ACE), которые создаются в корне домена и встроенных контейнерах во время подготовки домена</span><span class="sxs-lookup"><span data-stu-id="211d7-114">Access control entries (ACEs) that are created on the domain root and built-in containers during domain preparation</span></span>
    
- <span data-ttu-id="211d7-115">Изменения, внесенные в подразделение Active Directory командлетом Grant_CsSetupPermission.</span><span class="sxs-lookup"><span data-stu-id="211d7-115">Changes that are made on an Active Directory organizational unit (OU) by the Grant_CsSetupPermission cmdlet.</span></span>
    
- <span data-ttu-id="211d7-116">Изменения, внесенные в подразделение Active Directory командлетом Grant_CsOUPermission.</span><span class="sxs-lookup"><span data-stu-id="211d7-116">Changes that are made on an Active Directory OU by the Grant_CsOUPermission cmdlet.</span></span>
    
## <a name="in-this-section"></a><span data-ttu-id="211d7-117">Содержание</span><span class="sxs-lookup"><span data-stu-id="211d7-117">In This Section</span></span>

- [<span data-ttu-id="211d7-118">Изменения схемы в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="211d7-118">Schema changes in Skype for Business Server</span></span>](schema-changes.md)
    
- [<span data-ttu-id="211d7-119">Классы и описания схемы в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="211d7-119">Schema classes and descriptions in Skype for Business Server</span></span>](schema-classes-and-descriptions.md)
    
- [<span data-ttu-id="211d7-120">Атрибуты и описания схемы в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="211d7-120">Schema attributes and descriptions in Skype for Business Server</span></span>](schema-attributes-and-descriptions.md)
    
- [<span data-ttu-id="211d7-121">Атрибуты схемы по классам в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="211d7-121">Schema attributes by class in Skype for Business Server</span></span>](schema-attributes-by-class.md)
    
- [<span data-ttu-id="211d7-122">Изменения, внесенные в ходе подготовки леса в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="211d7-122">Changes made by forest preparation in Skype for Business Server</span></span>](changes-made-by-forest-preparation.md)
    
- [<span data-ttu-id="211d7-123">Изменения, внесенные в ходе подготовки домена в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="211d7-123">Changes made by domain preparation in Skype for Business Server</span></span>](changes-made-by-domain-preparation.md)
    
- [<span data-ttu-id="211d7-124">Изменения, внесенные Grant-CsSetupPermission в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="211d7-124">Changes made by Grant-CsSetupPermission in Skype for Business Server</span></span>](changes-made-by-grant-cssetuppermission.md)
    
- [<span data-ttu-id="211d7-125">Изменения, внесенные Grant-CsOUPermission в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="211d7-125">Changes made by Grant-CsOUPermission in Skype for Business Server</span></span>](changes-made-by-grant-csoupermission.md)
    

