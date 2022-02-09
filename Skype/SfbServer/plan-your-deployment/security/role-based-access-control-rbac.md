---
title: Управление доступом на основе ролей (RBAC) для Skype для бизнеса Server
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: d01fba36-eb7e-4de9-9bba-5102ae157820
description: Skype для бизнеса Server включает Role-Based управления доступом (RBAC), которые позволяют делегировать административные задачи при сохранении высоких стандартов безопасности. Эти группы создаются во время подготовки леса. Сведения о подготовке леса см. в материале Active Directory Domain Services for Skype для бизнеса Server. Сведения о конкретных группах, созданных при подготовке леса, см. в документации по развертыванию в Skype для бизнеса Server изменения, внесенные подготовкой леса.
ms.openlocfilehash: 3b7bec4bc5a8bfcad0a75f2e1652fd00377fde13
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/05/2022
ms.locfileid: "62398713"
---
# <a name="role-based-access-control-rbac-for-skype-for-business-server"></a>Управление доступом на основе ролей (RBAC) для Skype для бизнеса Server
 
Skype для бизнеса Server включает Role-Based управления доступом (RBAC), которые позволяют делегировать административные задачи при сохранении высоких стандартов безопасности. Эти группы создаются во время подготовки леса. Сведения о подготовке леса см. в [материале Active Directory Domain Services for Skype для бизнеса Server](active-directory-domain-services.md). Подробные сведения о конкретных группах, созданных при подготовке леса, см. в документации по развертыванию в Skype для бизнеса Server изменения, внесенные подготовкой леса.[](../../schema-reference/active-directory-schema-extensions-classes-and-attributes/changes-made-by-forest-preparation.md)
  
С помощью RBAC административная привилегия предоставляется путем назначения пользователям заранее определенных административных ролей, включая 11 предопределённых ролей, которые охватывают многие общие административные задачи. Каждая роль связана с определенным списком Skype для бизнеса Server, которые разрешено запускать пользователям в этой роли. С помощью RBAC можно следовать принципу "наименьшие привилегии", в котором пользователям даются только административные возможности, которые требуются для их работы. 
  
Дополнительные сведения о роли RBAC можно найти в ["Планирование управления доступом на основе ролей"](/lyncserver/lync-server-2013-planning-for-role-based-access-control).