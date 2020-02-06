---
title: Управление доступом на основе ролей (RBAC) для Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: d01fba36-eb7e-4de9-9bba-5102ae157820
description: 'Skype для бизнеса Server включает в себя группы управления доступом на основе ролей (RBAC), позволяющие делегировать задачи администрирования, обеспечивая высокий стандарт безопасности. Эти группы создаются в процессе подготовки леса. Подробнее о подготовке леса можно узнать в статьях доменные службы Active Directory для Skype для бизнеса Server. Подробные сведения о конкретных группах, созданных с помощью подготовки леса, можно найти в документации по развертыванию: изменения, внесенные с помощью подготовки леса в Skype для бизнеса Server.'
ms.openlocfilehash: 41efad45b442d9c7fca82d090afa0d1aa23e7d63
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815627"
---
# <a name="role-based-access-control-rbac-for-skype-for-business-server"></a>Управление доступом на основе ролей (RBAC) для Skype для бизнеса Server
 
Skype для бизнеса Server включает в себя группы управления доступом на основе ролей (RBAC), позволяющие делегировать задачи администрирования, обеспечивая высокий стандарт безопасности. Эти группы создаются в процессе подготовки леса. Подробнее о подготовке леса можно узнать в статьях [доменные службы Active Directory для Skype для бизнеса Server](active-directory-domain-services.md). Подробные сведения о конкретных группах, созданных с помощью подготовки леса, можно найти в документации по развертыванию: [изменения, внесенные с помощью подготовки леса в Skype для бизнеса Server](../../schema-reference/active-directory-schema-extensions-classes-and-attributes/changes-made-by-forest-preparation.md) .
  
С помощью RBAC права администратора предоставлены путем назначения пользователей предварительно определенным административным ролям, включая 11 предопределенных ролей, которые охватывают многие общие задачи администрирования. Каждая роль связана с определенным списком командлетов командной консоли Skype для бизнеса Server, для которых разрешено выполнение пользователей этой роли. Можно использовать RBAC для выполнения принципа "наименьших привилегий", в котором пользователям предоставляются только возможности администрирования, необходимые для работы. 
  
Дополнительные сведения о ролях RBAC можно найти на странице [Планирование управления доступом на основе ролей](https://docs.microsoft.com/lyncserver/lync-server-2013-planning-for-role-based-access-control).
