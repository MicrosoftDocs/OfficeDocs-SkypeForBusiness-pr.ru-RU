---
title: Управление доступом на основе ролей (RBAC) для Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: d01fba36-eb7e-4de9-9bba-5102ae157820
description: 'Skype для бизнеса Server включает в себя группы управления доступом на основе ролей (RBAC), позволяющие делегировать задачи администрирования, обеспечивая высокий стандарт безопасности. Эти группы создаются в процессе подготовки леса. Подробнее о подготовке леса можно узнать в статьях доменные службы Active Directory для Skype для бизнеса Server. Подробные сведения о конкретных группах, созданных с помощью подготовки леса, можно найти в документации по развертыванию: изменения, внесенные с помощью подготовки леса в Skype для бизнеса Server.'
ms.openlocfilehash: 493af102ae42658d51cfcb5d65fde6c26596d82d
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "34296842"
---
# <a name="role-based-access-control-rbac-for-skype-for-business-server"></a><span data-ttu-id="f9e5e-106">Управление доступом на основе ролей (RBAC) для Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="f9e5e-106">Role-based access control (RBAC) for Skype for Business Server</span></span>
 
<span data-ttu-id="f9e5e-107">Skype для бизнеса Server включает в себя группы управления доступом на основе ролей (RBAC), позволяющие делегировать задачи администрирования, обеспечивая высокий стандарт безопасности.</span><span class="sxs-lookup"><span data-stu-id="f9e5e-107">Skype for Business Server includes Role-Based Access Control (RBAC) groups to enable you to delegate administrative tasks while maintaining high standards for security.</span></span> <span data-ttu-id="f9e5e-108">Эти группы создаются в процессе подготовки леса.</span><span class="sxs-lookup"><span data-stu-id="f9e5e-108">These groups are created during forest preparation.</span></span> <span data-ttu-id="f9e5e-109">Подробнее о подготовке леса можно узнать в статьях [доменные службы Active Directory для Skype для бизнеса Server](active-directory-domain-services.md).</span><span class="sxs-lookup"><span data-stu-id="f9e5e-109">For details about forest preparation, see [Active Directory Domain Services for Skype for Business Server](active-directory-domain-services.md).</span></span> <span data-ttu-id="f9e5e-110">Подробные сведения о конкретных группах, созданных с помощью подготовки леса, можно найти в документации по развертыванию: [изменения, внесенные с помощью подготовки леса в Skype для бизнеса Server](../../schema-reference/active-directory-schema-extensions-classes-and-attributes/changes-made-by-forest-preparation.md) .</span><span class="sxs-lookup"><span data-stu-id="f9e5e-110">For details about the specific groups created by forest preparation, see [Changes made by forest preparation in Skype for Business Server](../../schema-reference/active-directory-schema-extensions-classes-and-attributes/changes-made-by-forest-preparation.md) in the Deployment documentation.</span></span>
  
<span data-ttu-id="f9e5e-111">С помощью RBAC права администратора предоставлены путем назначения пользователей предварительно определенным административным ролям, включая 11 предопределенных ролей, которые охватывают многие общие задачи администрирования.</span><span class="sxs-lookup"><span data-stu-id="f9e5e-111">With RBAC, administrative privilege is granted by assigning users to pre-defined administrative roles, including the 11 predefined roles that cover many common administrative tasks.</span></span> <span data-ttu-id="f9e5e-112">Каждая роль связана с определенным списком командлетов командной консоли для Lync Server, для которых разрешено выполнение пользователей этой роли.</span><span class="sxs-lookup"><span data-stu-id="f9e5e-112">Each role is associated with a specific list of Lync Server Management Shell cmdlets that users in that role are allowed to run.</span></span> <span data-ttu-id="f9e5e-113">Можно использовать RBAC для выполнения принципа "наименьших привилегий", в котором пользователям предоставляются только возможности администрирования, необходимые для работы.</span><span class="sxs-lookup"><span data-stu-id="f9e5e-113">You can use RBAC to follow the principle of "least privilege," in which users are given only the administrative abilities that their jobs require.</span></span> 
  
<span data-ttu-id="f9e5e-114">Дополнительные сведения о ролях RBAC можно найти по адресу:https://technet.microsoft.com/en-us/library/gg425917(v=ocs.15).aspx</span><span class="sxs-lookup"><span data-stu-id="f9e5e-114">More details on RBAC roles can be found at: https://technet.microsoft.com/en-us/library/gg425917(v=ocs.15).aspx</span></span>
