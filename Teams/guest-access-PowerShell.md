---
title: Использование PowerShell для управления гостевым доступом в команде
author: somakbhattacharyya
ms.author: sbhatta
manager: serdars
ms.date: 11/09/17
ms.topic: article
ms.service: msteams
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
ms.reviewer: sbhatta
search.appverid: MET150
description: Используйте PowerShell, чтобы разрешить или блокировать гостевой доступ к командам в Microsoft Teams.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 0efb3a8054008d179b9d2e7e674b3482fe62a32c
ms.sourcegitcommit: b2acf18ba6487154ebb4ee46938e96dc56cb2c9a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/09/2019
ms.locfileid: "33865092"
---
<a name="use-powershell-to-control-guest-access-to-a-team"></a>Использование PowerShell для управления гостевым доступом в команде
================================================

С помощью центра администрирования Microsoft 365 и Azure Active Directory портала, можно использовать Windows PowerShell для управления доступом гостя. PowerShell предоставляет следующие возможности:
  
- Разрешение или запрет гостевого доступа для всех команд и групп Office 365
    
- Разрешение добавления гостей во все команды и группы Office 365
      
- Разрешение или блокировка гостевых пользователей из определенной команды или группы Office 365
    
Для получения дополнительных сведений обратитесь к разделу «Использование PowerShell для управления доступом Гость» на вкладке Управление [гостевого доступа в Office 365 групп](https://support.office.com/article/Use-PowerShell-to-control-guest-access-bfc7a840-868f-4fd6-a390-f347bf51aff6#bkmk_usepowershell).
  
Вы также можете использовать PowerShell, чтобы разрешить или заблокировать гостевого пользователя по его домену. Например, предположим, что ваша организация (Contoso) сотрудничает с другой организацией (Fabrikam). Вы можете добавить Fabrikam в список разрешений, чтобы пользователи могли добавлять этих гостей в свои группы. Дополнительные сведения см. в статье [Разрешение и блокировка гостевого доступа к группам Office 365](https://go.microsoft.com/fwlink/?linkid=854001).
  
Если требуется заблокировать гости в группах и по-прежнему требуется разрешить им доступ к сайтам SharePoint, можно использовать командлеты Windows Azure Active Directory Powershell отключить параметр AllowGuestsToAccessGroups на объекте компании при условии, что внешний общий доступ для включено Сайты SharePoint.   

## <a name="guest-access-vs-external-access"></a>Доступ в качестве гостя и внешнего доступа

[!INCLUDE [guest-vs-external-access](includes/guest-vs-external-access.md)]
