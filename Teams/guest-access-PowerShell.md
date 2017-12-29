---
title: "Использование PowerShell для управления гостевым доступом в команде"
author: LaithAlShamri
ms.author: laal
manager: lolaj
ms.date: 10/20/17
ms.topic: article
ms.service: msteams
description: "Используйте PowerShell, чтобы разрешить или блокировать гостевой доступ к командам в Microsoft Teams."
Set_Free_Tag: Strat_MT_TeamsAdmin
ms.openlocfilehash: 0e087aadced6980db80890f423e3e6e3c4b7a701
ms.sourcegitcommit: 8f2e49bc813125137c90de997fb7a6dd74e6d1d5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/15/2017
---
<a name="use-powershell-to-control-guest-access-to-a-team"></a>Использование PowerShell для управления гостевым доступом в команде
================================================

Кроме Центра администрирования Office 365 и портала Azure Active Directory, для управления гостевым доступом вы можете использовать Windows PowerShell. PowerShell предоставляет следующие возможности:
  
  
   

- Разрешение или запрет гостевого доступа для всех команд и групп Office 365
    
  
- Разрешение добавления гостей во все команды и группы Office 365
    
  
- Разрешение или блокировка гостевых пользователей из определенной команды или группы Office 365
    
  
Дополнительные сведения см. в разделе "Использование PowerShell для управления гостевым доступом" на вкладке "Управление" в статье [Гостевой доступ в группах Office 365](https://support.office.com/en-us/article/Use-PowerShell-to-control-guest-access-bfc7a840-868f-4fd6-a390-f347bf51aff6#bkmk_usepowershell).
  
    
    
Вы также можете использовать PowerShell, чтобы разрешить или заблокировать гостевого пользователя по его домену. Например, предположим, что ваша организация (Contoso) сотрудничает с другой организацией (Fabrikam). Вы можете добавить Fabrikam в список разрешений, чтобы пользователи могли добавлять этих гостей в свои группы. Дополнительные сведения см. в статье [Разрешение и блокировка гостевого доступа к группам Office 365](https://go.microsoft.com/fwlink/?linkid=854001).
  
 
Если вы хотите блокировать гостей в командах, разрешив им при этом доступ к сайтам SharePoint, можете воспользоваться командлетами Powershell Azure Active Directory, чтобы отключить параметр AllowGuestAccessToGroups объекта "Company", при условии, что для сайтов SharePoint включен внешний общий доступ.   

