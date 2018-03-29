---
title: Управление доступом на основе ролей (RBAC) для Skype для бизнеса Server 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 4/6/2016
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: d01fba36-eb7e-4de9-9bba-5102ae157820
description: Скайп для Business Server 2015 включает в себя группы управления доступом на основе ролей (RBAC) для делегирования административных задач без снижения безопасности стандартам. Эти группы создаются в процессе подготовки леса. Для получения дополнительных сведений о подготовки леса приведена доменных служб Active Directory для Скайп Business Server 2015. Для получения дополнительных сведений об определенных групп, созданные подготовки леса просмотра изменений, внесенных путем подготовки леса в Скайп для Business Server в документации по развертыванию.
ms.openlocfilehash: f637ef752bb122cb73220d66fd8aa19c16fb358e
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/28/2018
---
# <a name="role-based-access-control-rbac-for-skype-for-business-server-2015"></a><span data-ttu-id="48ba8-106">Управление доступом на основе ролей (RBAC) для Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="48ba8-106">Role-based access control (RBAC) for Skype for Business Server 2015</span></span>
 
<span data-ttu-id="48ba8-107">Скайп для Business Server 2015 включает в себя группы управления доступом на основе ролей (RBAC) для делегирования административных задач без снижения безопасности стандартам.</span><span class="sxs-lookup"><span data-stu-id="48ba8-107">Skype for Business Server 2015 includes Role-Based Access Control (RBAC) groups to enable you to delegate administrative tasks while maintaining high standards for security.</span></span> <span data-ttu-id="48ba8-108">Эти группы создаются в процессе подготовки леса.</span><span class="sxs-lookup"><span data-stu-id="48ba8-108">These groups are created during forest preparation.</span></span> <span data-ttu-id="48ba8-109">Для получения дополнительных сведений о подготовки леса видеть [Доменных служб Active Directory для Скайп для Business Server 2015](active-directory-domain-services.md).</span><span class="sxs-lookup"><span data-stu-id="48ba8-109">For details about forest preparation, see [Active Directory Domain Services for Skype for Business Server 2015](active-directory-domain-services.md).</span></span> <span data-ttu-id="48ba8-110">Для получения дополнительных сведений об определенных групп, созданные подготовки леса просмотрите [изменения, внесенные с подготовки леса в Скайп для Business Server](../../schema-reference/active-directory-schema-extensions-classes-and-attributes/changes-made-by-forest-preparation.md) в документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="48ba8-110">For details about the specific groups created by forest preparation, see [Changes made by forest preparation in Skype for Business Server](../../schema-reference/active-directory-schema-extensions-classes-and-attributes/changes-made-by-forest-preparation.md) in the Deployment documentation.</span></span>
  
<span data-ttu-id="48ba8-111">С RBAC привилегии администратора полномочия, назначив пользователям предопределенные административные роли, включая 11 предопределенных ролей, которые охватывают множество общие административные задачи.</span><span class="sxs-lookup"><span data-stu-id="48ba8-111">With RBAC, administrative privilege is granted by assigning users to pre-defined administrative roles, including the 11 predefined roles that cover many common administrative tasks.</span></span> <span data-ttu-id="48ba8-112">Каждой роли связан с определенным списком командлеты командную консоль Lync Server, могут выполняться пользователи в этой роли.</span><span class="sxs-lookup"><span data-stu-id="48ba8-112">Each role is associated with a specific list of Lync Server Management Shell cmdlets that users in that role are allowed to run.</span></span> <span data-ttu-id="48ba8-113">Позволяет RBAC следуйте принципу «минимальных прав», в какие пользователи получают только административные возможности, которые требуют их работы.</span><span class="sxs-lookup"><span data-stu-id="48ba8-113">You can use RBAC to follow the principle of "least privilege," in which users are given only the administrative abilities that their jobs require.</span></span> 
  

