---
title: Управление доступом на основе ролей (RBAC) для Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: d01fba36-eb7e-4de9-9bba-5102ae157820
description: Skype для бизнеса Server включает Role-Based управления доступом (RBAC), позволяющие делегировать административные задачи при сохранении высоких стандартов безопасности. Эти группы создаются во время подготовки леса. Подробные сведения о подготовке леса см. в доменных службах Active Directory для Skype для бизнеса Server. Подробные сведения об определенных группах, созданных при подготовке леса, см. в документации по развертыванию изменений, внесенных в ходе подготовки леса в Skype для бизнеса Server.
ms.openlocfilehash: 9d3c453d4e7c3057c03f99cf2ff31b5fe17ae0bb
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832109"
---
# <a name="role-based-access-control-rbac-for-skype-for-business-server"></a><span data-ttu-id="fe1d7-106">Управление доступом на основе ролей (RBAC) для Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="fe1d7-106">Role-based access control (RBAC) for Skype for Business Server</span></span>
 
<span data-ttu-id="fe1d7-107">Skype для бизнеса Server включает Role-Based управления доступом (RBAC), позволяющие делегировать административные задачи при сохранении высоких стандартов безопасности.</span><span class="sxs-lookup"><span data-stu-id="fe1d7-107">Skype for Business Server includes Role-Based Access Control (RBAC) groups to enable you to delegate administrative tasks while maintaining high standards for security.</span></span> <span data-ttu-id="fe1d7-108">Эти группы создаются во время подготовки леса.</span><span class="sxs-lookup"><span data-stu-id="fe1d7-108">These groups are created during forest preparation.</span></span> <span data-ttu-id="fe1d7-109">Подробные сведения о подготовке леса см. в доменных службах [Active Directory для Skype для бизнеса Server.](active-directory-domain-services.md)</span><span class="sxs-lookup"><span data-stu-id="fe1d7-109">For details about forest preparation, see [Active Directory Domain Services for Skype for Business Server](active-directory-domain-services.md).</span></span> <span data-ttu-id="fe1d7-110">Подробные сведения об определенных группах, созданных при подготовке леса, см. в документации по развертыванию изменений, внесенных в ходе подготовки леса в Skype для бизнеса [Server.](../../schema-reference/active-directory-schema-extensions-classes-and-attributes/changes-made-by-forest-preparation.md)</span><span class="sxs-lookup"><span data-stu-id="fe1d7-110">For details about the specific groups created by forest preparation, see [Changes made by forest preparation in Skype for Business Server](../../schema-reference/active-directory-schema-extensions-classes-and-attributes/changes-made-by-forest-preparation.md) in the Deployment documentation.</span></span>
  
<span data-ttu-id="fe1d7-111">С помощью RBAC административные привилегии лагаются путем назначения пользователям предварительно определенных административных ролей, включая 11 предопределеных ролей, которые охватывают множество распространенных задач администрирования.</span><span class="sxs-lookup"><span data-stu-id="fe1d7-111">With RBAC, administrative privilege is granted by assigning users to pre-defined administrative roles, including the 11 predefined roles that cover many common administrative tasks.</span></span> <span data-ttu-id="fe1d7-112">Каждая роль связана с определенным списком cmdlets оболочки управления Skype для бизнеса Server, которые пользователи в этой роли могут запускать.</span><span class="sxs-lookup"><span data-stu-id="fe1d7-112">Each role is associated with a specific list of Skype for Business Server Management Shell cmdlets that users in that role are allowed to run.</span></span> <span data-ttu-id="fe1d7-113">С помощью RBAC можно следовать принципу "наименьших привилегий", при котором пользователям даются только административные возможности, необходимые для их работы.</span><span class="sxs-lookup"><span data-stu-id="fe1d7-113">You can use RBAC to follow the principle of "least privilege," in which users are given only the administrative abilities that their jobs require.</span></span> 
  
<span data-ttu-id="fe1d7-114">Дополнительные сведения о ролях RBAC можно найти в области [планирования управления доступом на основе ролей.](https://docs.microsoft.com/lyncserver/lync-server-2013-planning-for-role-based-access-control)</span><span class="sxs-lookup"><span data-stu-id="fe1d7-114">More details on RBAC roles can be found at [Planning for role-based access control](https://docs.microsoft.com/lyncserver/lync-server-2013-planning-for-role-based-access-control).</span></span>
