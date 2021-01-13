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
description: Сводка. Узнайте, как удалить параметры конфигурации собраний в Skype для бизнеса Server.
ms.openlocfilehash: 418ce7418be5a09658626491121dd2e2b3542110
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49828186"
---
# <a name="delete-meeting-configuration-settings-in-skype-for-business-server"></a>Удаление параметров конфигурации собраний в Skype для бизнеса Server
 
**Сводка:** Узнайте, как удалить параметры конфигурации собраний в Skype для бизнеса Server.
  
You can delete meeting configuration settings by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.
  
Вы можете удалить конфигурацию сайта или пользователя, но не глобальную конфигурацию. При попытке удалить глобальную конфигурацию она автоматически сбрасывается до значений по умолчанию.
  
## <a name="delete-meeting-configuration-settings-by-using-skype-for-business-server-control-panel"></a>Удаление параметров конфигурации собраний с помощью панели управления Skype для бизнеса Server

1. Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.
    
2.  Откройте панель управления Skype для бизнеса Server.
    
3. В левой панели навигации щелкните **"Conferencing"**(Конфигурация собрания) и выберите **"Конфигурация собрания".**
    
4. В списке конфигураций собраний выберите конфигурацию сайта или пула, которую нужно удалить, нажмите кнопку "Изменить", а затем выберите **"Удалить".**
    
## <a name="delete-meeting-configuration-settings-by-using-skype-for-business-server-management-shell"></a>Удаление параметров конфигурации собраний с помощью оболочки управления Skype для бизнеса Server

Чтобы удалить параметры собрания, используйте **cmdlet Remove-CsMeetingConfiguration.**
  
Следующая команда удаляет параметры конфигурации собраний, применяемые к сайту Redmond:
  
```PowerShell
Remove-CsMeetingConfiguration -Identity "site:Redmond"
```

Следующая команда удаляет все параметры конфигурации собраний, примененные к области сайта:
  
```PowerShell
Get-CsMeetingConfiguration -Filter "site:*" | Remove-CsMeetingConfiguration
```

Дополнительные сведения, включая полный список параметров, см. в подстроке [Remove-CsMeetingConfiguration.](https://docs.microsoft.com/powershell/module/skype/remove-csmeetingconfiguration?view=skype-ps)
  

