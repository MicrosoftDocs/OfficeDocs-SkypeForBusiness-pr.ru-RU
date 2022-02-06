---
title: Изменение параметров конфигурации собраний в Skype для бизнеса Server
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.assetid: 11d1f9ac-0029-429b-be2b-d7591abfc192
description: Сводка. Сведения об изменении параметров конфигурации собраний в Skype для бизнеса Server.
---

# <a name="modify-meeting-configuration-settings-in-skype-for-business-server"></a>Изменение параметров конфигурации собраний в Skype для бизнеса Server
 
**Сводка:** Узнайте, как изменить параметры конфигурации собраний в Skype для бизнеса Server.
  
Параметры конфигурации собраний можно изменить с помощью Skype для бизнеса Server панели управления или с помощью Skype для бизнеса Server управленческой оболочки.
  
## <a name="modify-meeting-configuration-settings-by-using-skype-for-business-server-control-panel"></a>Изменение параметров конфигурации собраний с помощью Skype для бизнеса Server панели управления

1. Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.
    
2.  Откройте панель Skype для бизнеса Server управления.
    
3. В левой панели навигации нажмите **кнопку Conferencing** и нажмите кнопку **Конфигурация собраний**.
    
4. В списке конфигураций собраний щелкните конфигурацию, которую необходимо изменить, нажмите **кнопку Изменить**, а затем нажмите **кнопку Показать сведения**.
    
5. В **изменении конфигурации** собраний измените все параметры конфигурации, за исключением имени конфигурации, которое невозможно изменить.
    
6. Щелкните **Исполнить**.
    
## <a name="modify-meeting-configuration-settings-by-using-skype-for-business-server-management-shell"></a>Изменение параметров конфигурации собраний с помощью Skype для бизнеса Server Management Shell

Чтобы изменить параметры конфигурации собраний, используйте комлет **Set-CsMeetingConfiguration** .
  
Команда, показанная в следующем примере, изменяет параметры конфигурации собраний, присвоенные сайту Redmond (-Identity site:Redmond). В этом случае значение свойства DesignateAsPresenter устанавливается для всех:
  
```PowerShell
Set-CsMeetingConfiguration -Identity "site:Redmond" -DesignateAsPresenter "Everyone"
```

Дополнительные сведения, включая полный список параметров, см. в [списке Set-CsMeetingConfiguration](/powershell/module/skype/set-csmeetingconfiguration?view=skype-ps).
