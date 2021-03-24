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
description: Skype для бизнеса Server включает Role-Based управления доступом (RBAC), которые позволяют делегировать административные задачи при сохранении высоких стандартов безопасности. Эти группы создаются во время подготовки леса. Сведения о подготовке леса см. в материале Active Directory Domain Services for Skype for Business Server. Подробные сведения о конкретных группах, созданных при подготовке леса, см. в документации по развертыванию в Skype для бизнеса.
ms.openlocfilehash: e02123721433e2af0ca3576ac71dd5a49a0ad9a1
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51104215"
---
# <a name="role-based-access-control-rbac-for-skype-for-business-server"></a>Управление доступом на основе ролей (RBAC) для Skype для бизнеса Server
 
Skype для бизнеса Server включает Role-Based управления доступом (RBAC), которые позволяют делегировать административные задачи при сохранении высоких стандартов безопасности. Эти группы создаются во время подготовки леса. Сведения о подготовке леса см. в [материале Active Directory Domain Services for Skype for Business Server.](active-directory-domain-services.md) Подробные сведения о конкретных группах, созданных при подготовке леса, см. в документации по развертыванию в [Skype для](../../schema-reference/active-directory-schema-extensions-classes-and-attributes/changes-made-by-forest-preparation.md) бизнеса.
  
С помощью RBAC административная привилегия предоставляется путем назначения пользователям заранее определенных административных ролей, включая 11 предопределённых ролей, которые охватывают многие общие административные задачи. Каждая роль связана с определенным списком смещаний Skype для управления бизнес-серверами, которые разрешено запускать пользователям в этой роли. С помощью RBAC можно следовать принципу "наименьшие привилегии", в котором пользователям даются только административные возможности, которые требуются для их работы. 
  
Дополнительные сведения о ролях RBAC можно найти в "Планирование управления доступом на основе [ролей".](/lyncserver/lync-server-2013-planning-for-role-based-access-control)