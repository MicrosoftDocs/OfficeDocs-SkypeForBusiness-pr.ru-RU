---
title: Удаление параметров конфигурации собраний в Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 8ebafb86-13b9-468e-beda-f85f6786da85
description: Сводка. Сведения об удалении параметров конфигурации собраний в Skype для бизнеса Server.
ms.openlocfilehash: b0c739f0149b4e28ca23df1437caab0505e1118d
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51119498"
---
# <a name="delete-meeting-configuration-settings-in-skype-for-business-server"></a>Удаление параметров конфигурации собраний в Skype для бизнеса Server
 
**Сводка:** Узнайте, как удалить параметры конфигурации собраний в Skype для бизнеса Server.
  
Параметры конфигурации собраний можно удалить с помощью панели управления Skype для бизнес-серверов или с помощью оболочки управления Skype для бизнес-серверов.
  
Вы можете удалить конфигурацию сайта или пользователя, но не можете удалить глобальную конфигурацию. Если вы попытайтесь удалить глобальную конфигурацию, она автоматически сброшена до значений по умолчанию.
  
## <a name="delete-meeting-configuration-settings-by-using-skype-for-business-server-control-panel"></a>Удаление параметров конфигурации собраний с помощью панели управления Skype для бизнес-серверов

1. Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.
    
2.  Откройте панель управления Skype для бизнес-серверов.
    
3. В левой панели навигации нажмите **кнопку Conferencing** и нажмите кнопку **Конфигурация собраний**.
    
4. В списке конфигураций собраний щелкните конфигурацию сайта или пула, которую необходимо удалить, нажмите кнопку **Изменить** и нажмите **кнопку Удалить**.
    
## <a name="delete-meeting-configuration-settings-by-using-skype-for-business-server-management-shell"></a>Удаление параметров конфигурации собраний с помощью оболочки управления Skype для бизнес-серверов

Чтобы удалить параметры собраний, используйте комлет **Remove-CsMeetingConfiguration.**
  
Следующая команда удаляет параметры конфигурации собраний, применяемые к сайту Redmond:
  
```PowerShell
Remove-CsMeetingConfiguration -Identity "site:Redmond"
```

Следующая команда удаляет все параметры конфигурации собраний, применяемые к области сайта:
  
```PowerShell
Get-CsMeetingConfiguration -Filter "site:*" | Remove-CsMeetingConfiguration
```

Дополнительные сведения, включая полный список параметров, см. в [рублях Remove-CsMeetingConfiguration.](/powershell/module/skype/remove-csmeetingconfiguration?view=skype-ps)
