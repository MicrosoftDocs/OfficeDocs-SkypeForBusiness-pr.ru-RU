---
title: Расширения схемы Active Directory, классы и атрибуты
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 579bfa5a-9443-46dd-9a8e-07d00ba2824d
description: 'В этом справочном разделе представлены следующие сведения:'
ms.openlocfilehash: 37dee1a029a0d8872452082aebb9b8f0fcf2f072
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/27/2019
ms.locfileid: "30888838"
---
# <a name="active-directory-schema-extensions-classes-and-attributes"></a><span data-ttu-id="c2481-103">Расширения схемы Active Directory, классы и атрибуты</span><span class="sxs-lookup"><span data-stu-id="c2481-103">Active Directory schema extensions, classes, and attributes</span></span>
 
<span data-ttu-id="c2481-104">В этом справочном разделе представлены следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="c2481-104">This reference section includes the following information:</span></span> 
  
- <span data-ttu-id="c2481-105">Расширения схемы Active Directory, которые являются новые или измененные для Скайп для Business Server</span><span class="sxs-lookup"><span data-stu-id="c2481-105">Active Directory schema extensions that are new or changed for Skype for Business Server</span></span>
    
    <span data-ttu-id="c2481-106">Схемы Active Directory содержит формальные определения каждого класса объектов, которые могут быть созданы в лесу Active Directory.</span><span class="sxs-lookup"><span data-stu-id="c2481-106">The Active Directory schema contains formal definitions of every object class that can be created in an Active Directory forest.</span></span> <span data-ttu-id="c2481-107">Схема также содержит формальные определения каждого атрибута, которые могут находиться на объект Active Directory.</span><span class="sxs-lookup"><span data-stu-id="c2481-107">The schema also contains formal definitions of every attribute that can exist on an Active Directory object.</span></span> <span data-ttu-id="c2481-108">Глобального каталога Active Directory содержит реплики всех объектов в лесу, а также ограниченный набор атрибутов для каждого объекта.</span><span class="sxs-lookup"><span data-stu-id="c2481-108">The Active Directory global catalog contains replicas of all the objects for the forest, along with a subset of the attributes for each object.</span></span> <span data-ttu-id="c2481-109">В этом разделе описываются классы и атрибуты, которые являются новые или измененные в Скайп для Business Server.</span><span class="sxs-lookup"><span data-stu-id="c2481-109">This section describes the classes and attributes that are new or changed in Skype for Business Server.</span></span>
    
- <span data-ttu-id="c2481-110">Все классы, используемые Скайп для Business Server, с описанием каждого из них</span><span class="sxs-lookup"><span data-stu-id="c2481-110">All the classes used by Skype for Business Server, with a description of each</span></span>
    
- <span data-ttu-id="c2481-111">Все атрибуты, используемые Скайп для Business Server, с описанием каждого из них</span><span class="sxs-lookup"><span data-stu-id="c2481-111">All the attributes used by Skype for Business Server, with a description of each</span></span>
    
- <span data-ttu-id="c2481-112">Список классов, используемых Скайп для Business Server, с атрибутами, которые они могут содержать</span><span class="sxs-lookup"><span data-stu-id="c2481-112">A list of the classes used by Skype for Business Server, with the attributes each may contain</span></span>
    
- <span data-ttu-id="c2481-113">Глобальные параметры и объекты, помимо универсальных групп служб и административные, созданных во время подготовки леса</span><span class="sxs-lookup"><span data-stu-id="c2481-113">Global settings and objects, in addition to the universal service and administration groups that are created during forest preparation</span></span>
    
- <span data-ttu-id="c2481-114">Записи управления доступом (ACE), которые созданы на домен корневого и встроенных контейнерах во время подготовки домена</span><span class="sxs-lookup"><span data-stu-id="c2481-114">Access control entries (ACEs) that are created on the domain root and built-in containers during domain preparation</span></span>
    
- <span data-ttu-id="c2481-115">Изменения, внесенные в подразделения (OU) Active Directory командлетом grant_cssetuppermission.</span><span class="sxs-lookup"><span data-stu-id="c2481-115">Changes that are made on an Active Directory organizational unit (OU) by the Grant_CsSetupPermission cmdlet.</span></span>
    
- <span data-ttu-id="c2481-116">Изменения, внесенные в Подразделение Active Directory командлетом grant_csoupermission.</span><span class="sxs-lookup"><span data-stu-id="c2481-116">Changes that are made on an Active Directory OU by the Grant_CsOUPermission cmdlet.</span></span>
    
## <a name="in-this-section"></a><span data-ttu-id="c2481-117">Содержание</span><span class="sxs-lookup"><span data-stu-id="c2481-117">In This Section</span></span>

- [<span data-ttu-id="c2481-118">Изменения схемы в Скайп для Business Server</span><span class="sxs-lookup"><span data-stu-id="c2481-118">Schema changes in Skype for Business Server</span></span>](schema-changes.md)
    
- [<span data-ttu-id="c2481-119">Классы схемы и описания в Скайп Business Server</span><span class="sxs-lookup"><span data-stu-id="c2481-119">Schema classes and descriptions in Skype for Business Server</span></span>](schema-classes-and-descriptions.md)
    
- [<span data-ttu-id="c2481-120">Атрибуты схемы и описания в Скайп Business Server</span><span class="sxs-lookup"><span data-stu-id="c2481-120">Schema attributes and descriptions in Skype for Business Server</span></span>](schema-attributes-and-descriptions.md)
    
- [<span data-ttu-id="c2481-121">Атрибуты схемы по классам в Скайп для Business Server</span><span class="sxs-lookup"><span data-stu-id="c2481-121">Schema attributes by class in Skype for Business Server</span></span>](schema-attributes-by-class.md)
    
- [<span data-ttu-id="c2481-122">Изменения, внесенные с подготовки леса в Скайп для Business Server</span><span class="sxs-lookup"><span data-stu-id="c2481-122">Changes made by forest preparation in Skype for Business Server</span></span>](changes-made-by-forest-preparation.md)
    
- [<span data-ttu-id="c2481-123">Изменения, внесенные с подготовки домена в Скайп для Business Server</span><span class="sxs-lookup"><span data-stu-id="c2481-123">Changes made by domain preparation in Skype for Business Server</span></span>](changes-made-by-domain-preparation.md)
    
- [<span data-ttu-id="c2481-124">Изменения, сделанные Grant-CsSetupPermission в Скайп для Business Server</span><span class="sxs-lookup"><span data-stu-id="c2481-124">Changes made by Grant-CsSetupPermission in Skype for Business Server</span></span>](changes-made-by-grant-cssetuppermission.md)
    
- [<span data-ttu-id="c2481-125">Изменения, сделанные Grant-CsOUPermission в Скайп для Business Server</span><span class="sxs-lookup"><span data-stu-id="c2481-125">Changes made by Grant-CsOUPermission in Skype for Business Server</span></span>](changes-made-by-grant-csoupermission.md)
    

