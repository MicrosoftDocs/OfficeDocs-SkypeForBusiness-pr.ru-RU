---
title: Управление доступом на основе ролей (RBAC) для Скайп для Business Server
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: d01fba36-eb7e-4de9-9bba-5102ae157820
description: Скайп для Business Server включает в себя группы управления доступом на основе ролей (RBAC) для делегирования административных задач без снижения безопасности стандартам. Эти группы создаются в процессе подготовки леса. Для получения дополнительных сведений о подготовки леса приведена доменных служб Active Directory для Скайп Business Server. Для получения дополнительных сведений об определенных групп, созданные подготовки леса просмотра изменений, внесенных путем подготовки леса в Скайп для Business Server в документации по развертыванию.
ms.openlocfilehash: 461fa82809b16ccf6db1ac02e7c8d0e6698e2b61
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/27/2019
ms.locfileid: "30894275"
---
# <a name="role-based-access-control-rbac-for-skype-for-business-server"></a>Управление доступом на основе ролей (RBAC) для Скайп для Business Server
 
Скайп для Business Server включает в себя группы управления доступом на основе ролей (RBAC) для делегирования административных задач без снижения безопасности стандартам. Эти группы создаются в процессе подготовки леса. Для получения дополнительных сведений о подготовки леса видеть [Доменных служб Active Directory для Скайп для Business Server](active-directory-domain-services.md). Для получения дополнительных сведений об определенных групп, созданные подготовки леса просмотрите [изменения, внесенные с подготовки леса в Скайп для Business Server](../../schema-reference/active-directory-schema-extensions-classes-and-attributes/changes-made-by-forest-preparation.md) в документации по развертыванию.
  
С RBAC привилегии администратора полномочия, назначив пользователям предопределенные административные роли, включая 11 предопределенных ролей, которые охватывают множество общие административные задачи. Каждой роли связан с определенным списком командлеты командную консоль Lync Server, могут выполняться пользователи в этой роли. Позволяет RBAC следуйте принципу «минимальных прав», в какие пользователи получают только административные возможности, которые требуют их работы. 
  
Дополнительные сведения о ролях RBAC, можно найти в:https://technet.microsoft.com/en-us/library/gg425917(v=ocs.15).aspx
