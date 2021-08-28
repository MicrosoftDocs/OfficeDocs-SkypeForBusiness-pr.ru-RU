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
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: d01fba36-eb7e-4de9-9bba-5102ae157820
description: Skype для бизнеса Server включает Role-Based управления доступом (RBAC), которые позволяют делегировать административные задачи при сохранении высоких стандартов безопасности. Эти группы создаются во время подготовки леса. Сведения о подготовке леса см. в материале Active Directory Domain Services for Skype для бизнеса Server. Сведения о конкретных группах, созданных при подготовке леса, см. в документации по развертыванию в Skype для бизнеса Server изменения, внесенные подготовкой леса.
ms.openlocfilehash: 1768c61f902dddb456f6a80bccf3b72bd9757f77
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/26/2021
ms.locfileid: "58627941"
---
# <a name="role-based-access-control-rbac-for-skype-for-business-server"></a>Управление доступом на основе ролей (RBAC) для Skype для бизнеса Server
 
Skype для бизнеса Server включает Role-Based управления доступом (RBAC), которые позволяют делегировать административные задачи при сохранении высоких стандартов безопасности. Эти группы создаются во время подготовки леса. Сведения о подготовке леса см. в [материале Active Directory Domain Services for Skype для бизнеса Server.](active-directory-domain-services.md) Подробные сведения о конкретных группах, созданных в ходе подготовки леса, см. в материале [Изменения,](../../schema-reference/active-directory-schema-extensions-classes-and-attributes/changes-made-by-forest-preparation.md) внесенные подготовкой леса в Skype для бизнеса Server документации по развертыванию.
  
С помощью RBAC административная привилегия предоставляется путем назначения пользователям заранее определенных административных ролей, включая 11 предопределённых ролей, которые охватывают многие общие административные задачи. Каждая роль связана с определенным списком Skype для бизнеса Server, которые разрешено запускать пользователям в этой роли. С помощью RBAC можно следовать принципу "наименьшие привилегии", в котором пользователям даются только административные возможности, которые требуются для их работы. 
  
Дополнительные сведения о ролях RBAC можно найти в "Планирование управления доступом на основе [ролей".](/lyncserver/lync-server-2013-planning-for-role-based-access-control)