---
title: Изменение параметров конфигурации собраний в Skype для бизнеса Server
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
ms.assetid: 11d1f9ac-0029-429b-be2b-d7591abfc192
description: Сводка. Узнайте, как изменить параметры конфигурации собраний в Skype для бизнеса Server.
ms.openlocfilehash: 80ba12266ebc45fdae3256f5238ecf18415734c8
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49827999"
---
# <a name="modify-meeting-configuration-settings-in-skype-for-business-server"></a>Изменение параметров конфигурации собраний в Skype для бизнеса Server
 
**Сводка:** Узнайте, как изменить параметры конфигурации собраний в Skype для бизнеса Server.
  
Изменить параметры конфигурации собраний можно с помощью панели управления Skype для бизнеса Server или с помощью skype для бизнеса Server Management Shell.
  
## <a name="modify-meeting-configuration-settings-by-using-skype-for-business-server-control-panel"></a>Изменение параметров конфигурации собраний с помощью панели управления Skype для бизнеса Server

1. Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.
    
2.  Откройте панель управления Skype для бизнеса Server.
    
3. В левой панели навигации щелкните **"Conferencing"**(Конфигурация собрания) и выберите **"Конфигурация собрания".**
    
4. В списке конфигураций собраний выберите конфигурацию, которую нужно изменить, нажмите кнопку "Изменить", а затем щелкните **"Показать подробности".**
    
5. В **области "Изменение конфигурации** собрания" измените любые параметры конфигурации, за исключением имени конфигурации, которое нельзя изменить.
    
6. Щелкните **Исполнить**.
    
## <a name="modify-meeting-configuration-settings-by-using-skype-for-business-server-management-shell"></a>Изменение параметров конфигурации собраний с помощью оболочки управления Skype для бизнеса Server

Чтобы изменить параметры конфигурации собрания, используйте **cmdlet Set-CsMeetingConfiguration.**
  
Команда, показанная в следующем примере, изменяет параметры конфигурации собраний, присвоенные сайту Redmond (-Identity site:Redmond). В этом случае свойству DesignateAsPresenter задается значение Everyone:
  
```PowerShell
Set-CsMeetingConfiguration -Identity "site:Redmond" -DesignateAsPresenter "Everyone"
```

Дополнительные сведения, включая полный список параметров, см. в подстроке [Set-CsMeetingConfiguration.](https://docs.microsoft.com/powershell/module/skype/set-csmeetingconfiguration?view=skype-ps)
  

