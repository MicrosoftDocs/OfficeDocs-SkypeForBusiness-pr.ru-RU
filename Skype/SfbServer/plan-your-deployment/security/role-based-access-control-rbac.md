---
title: Управление доступом на основе ролей (RBAC) для Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
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
ms.openlocfilehash: 05f1b4873e6d671ecb53e6778a67b5558d4aa1ee
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/04/2021
ms.locfileid: "60744106"
---
# <a name="role-based-access-control-rbac-for-skype-for-business-server"></a>Управление доступом на основе ролей (RBAC) для Skype для бизнеса Server
 
Skype для бизнеса Server включает Role-Based управления доступом (RBAC), которые позволяют делегировать административные задачи при сохранении высоких стандартов безопасности. Эти группы создаются во время подготовки леса. Сведения о подготовке леса см. в [материале Active Directory Domain Services for Skype для бизнеса Server.](active-directory-domain-services.md) Подробные сведения о конкретных группах, созданных в ходе подготовки леса, см. в материале [Изменения,](../../schema-reference/active-directory-schema-extensions-classes-and-attributes/changes-made-by-forest-preparation.md) внесенные подготовкой леса в Skype для бизнеса Server документации по развертыванию.
  
С помощью RBAC административная привилегия предоставляется путем назначения пользователям заранее определенных административных ролей, включая 11 предопределённых ролей, которые охватывают многие общие административные задачи. Каждая роль связана с определенным списком Skype для бизнеса Server, которые разрешено запускать пользователям в этой роли. С помощью RBAC можно следовать принципу "наименьшие привилегии", в котором пользователям даются только административные возможности, которые требуются для их работы. 
  
Дополнительные сведения о ролях RBAC можно найти в "Планирование управления доступом на основе [ролей".](/lyncserver/lync-server-2013-planning-for-role-based-access-control)