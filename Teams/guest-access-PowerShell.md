---
title: "Использование PowerShell для управления гостевым доступом в команде"
author: LaithAlShamri
ms.author: laal
manager: serdars
ms.date: 10/20/17
ms.topic: article
ms.service: msteams
ms.reviewer: laal
description: "Используйте PowerShell, чтобы разрешить или блокировать гостевой доступ к командам в Microsoft Teams."
appliesto:
- Microsoft Teams
ms.openlocfilehash: 0e5790fd6ee023720914835084ffc9f6ef4d3ac4
ms.sourcegitcommit: 85105cb4e42ae8eb6e7e76eaf6d4dd5b9568cf41
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2018
---
<a name="use-powershell-to-control-guest-access-to-a-team"></a>Использование PowerShell для управления гостевым доступом в команде
================================================

Кроме Центра администрирования Office 365 и портала Azure Active Directory, для управления гостевым доступом вы можете использовать Windows PowerShell. PowerShell предоставляет следующие возможности:
  
  
   

- Разрешение или запрет гостевого доступа для всех команд и групп Office 365
    
  
- Разрешение добавления гостей во все команды и группы Office 365
    
  
- Разрешение или блокировка гостевых пользователей из определенной команды или группы Office 365
    
  
Дополнительные сведения см. в разделе "Использование PowerShell для управления гостевым доступом" на вкладке "Управление" в статье [Гостевой доступ в группах Office 365](https://support.office.com/article/Use-PowerShell-to-control-guest-access-bfc7a840-868f-4fd6-a390-f347bf51aff6#bkmk_usepowershell).
  
    
    
Вы также можете использовать PowerShell, чтобы разрешить или заблокировать гостевого пользователя по его домену. Например, предположим, что ваша организация (Contoso) сотрудничает с другой организацией (Fabrikam). Вы можете добавить Fabrikam в список разрешений, чтобы пользователи могли добавлять этих гостей в свои группы. Дополнительные сведения см. в статье [Разрешение и блокировка гостевого доступа к группам Office 365](https://go.microsoft.com/fwlink/?linkid=854001).
  
 
Если вы хотите блокировать гостей в командах, разрешив им при этом доступ к сайтам SharePoint, можете воспользоваться командлетами Powershell Azure Active Directory, чтобы отключить параметр AllowGuestAccessToGroups объекта "Company", при условии, что для сайтов SharePoint включен внешний общий доступ.   

