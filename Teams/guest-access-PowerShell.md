---
title: Использование PowerShell для управления гостевым доступом в команде
author: lanachin
ms.author: v-lanac
manager: serdars
ms.date: 06/25/2019
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
ms.reviewer: sbhatta
search.appverid: MET150
description: Используйте PowerShell, чтобы разрешить или блокировать гостевой доступ к командам в Microsoft Teams.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 7e106dc56f56b5e26dd56384931deeecdd889305
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/07/2019
ms.locfileid: "36235524"
---
<a name="use-powershell-to-control-guest-access-to-a-team"></a>Использование PowerShell для управления гостевым доступом в команде
================================================

Кроме того, чтобы использовать центр администрирования Microsoft 365 и портал Azure Active Directory (Azure AD), вы можете управлять гостевым доступом с помощью Windows PowerShell. PowerShell предоставляет следующие возможности:
  
- Разрешение и блокирование гостевого доступа ко всем группам и Office 365

- Разрешение на добавление гостей ко всем группам и Office 365

- Разрешение или блокировка гостевых пользователей из определенной команды или группы Office 365

Дополнительные сведения можно найти в разделе "Использование PowerShell для управления гостевым доступом" на панели [управления доступом гостей в группах Office 365](https://docs.microsoft.com/office365/admin/create-groups/manage-guest-access-in-groups#use-powershell-to-control-guest-access).
  
Вы также можете использовать PowerShell, чтобы разрешить или заблокировать гостевого пользователя по его домену. Например, предположим, что ваша организация (Contoso) сотрудничает с другой организацией (Fabrikam). Вы можете добавить Fabrikam в список разрешений, чтобы пользователи могли добавлять этих гостей в свои группы. Дополнительные сведения можно найти [в разделе разрешение и блокирование гостевого доступа для групп Office 365](https://go.microsoft.com/fwlink/?linkid=854001).
  
Если вы хотите заблокировать гостей в Teams и по-прежнему хотите разрешить им доступ к сайтам SharePoint, можно использовать командлеты Azure AD PowerShell, чтобы отключить параметр Алловгуестстоакцессграупс для объекта Company, предполагая, что внешний общий доступ включен для сайтов SharePoint. .

## <a name="guest-access-vs-external-access"></a>Гостевой доступ и внешний доступ

[!INCLUDE [guest-vs-external-access](includes/guest-vs-external-access.md)]
