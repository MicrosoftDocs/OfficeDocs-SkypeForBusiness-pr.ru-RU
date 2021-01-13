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
# <a name="role-based-access-control-rbac-for-skype-for-business-server"></a>Управление доступом на основе ролей (RBAC) для Skype для бизнеса Server
 
Skype для бизнеса Server включает Role-Based управления доступом (RBAC), позволяющие делегировать административные задачи при сохранении высоких стандартов безопасности. Эти группы создаются во время подготовки леса. Подробные сведения о подготовке леса см. в доменных службах [Active Directory для Skype для бизнеса Server.](active-directory-domain-services.md) Подробные сведения об определенных группах, созданных при подготовке леса, см. в документации по развертыванию изменений, внесенных в ходе подготовки леса в Skype для бизнеса [Server.](../../schema-reference/active-directory-schema-extensions-classes-and-attributes/changes-made-by-forest-preparation.md)
  
С помощью RBAC административные привилегии лагаются путем назначения пользователям предварительно определенных административных ролей, включая 11 предопределеных ролей, которые охватывают множество распространенных задач администрирования. Каждая роль связана с определенным списком cmdlets оболочки управления Skype для бизнеса Server, которые пользователи в этой роли могут запускать. С помощью RBAC можно следовать принципу "наименьших привилегий", при котором пользователям даются только административные возможности, необходимые для их работы. 
  
Дополнительные сведения о ролях RBAC можно найти в области [планирования управления доступом на основе ролей.](https://docs.microsoft.com/lyncserver/lync-server-2013-planning-for-role-based-access-control)
