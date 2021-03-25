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
ms.openlocfilehash: 2f0d1220312ac810d26fdd4691492133e54db9b6
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51119418"
---
# <a name="modify-meeting-configuration-settings-in-skype-for-business-server"></a>Изменение параметров конфигурации собраний в Skype для бизнеса Server
 
**Сводка:** Узнайте, как изменить параметры конфигурации собраний в Skype для бизнеса Server.
  
Параметры конфигурации собраний можно изменить с помощью панели управления Skype для бизнес-серверов или с помощью оболочки управления Skype для бизнес-серверов.
  
## <a name="modify-meeting-configuration-settings-by-using-skype-for-business-server-control-panel"></a>Изменение параметров конфигурации собраний с помощью панели управления Skype для бизнес-серверов

1. Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.
    
2.  Откройте панель управления Skype для бизнес-серверов.
    
3. В левой панели навигации нажмите **кнопку Conferencing** и нажмите кнопку **Конфигурация собраний**.
    
4. В списке конфигураций собраний щелкните конфигурацию, которую необходимо изменить, нажмите **кнопку Изменить** и нажмите **кнопку Показать сведения**.
    
5. В **изменении конфигурации** собраний измените любые параметры конфигурации, за исключением имени конфигурации, которое невозможно изменить.
    
6. Щелкните **Исполнить**.
    
## <a name="modify-meeting-configuration-settings-by-using-skype-for-business-server-management-shell"></a>Изменение параметров конфигурации собраний с помощью оболочки управления Skype для бизнес-серверов

Чтобы изменить параметры конфигурации собраний, используйте комлет **Set-CsMeetingConfiguration.**
  
Команда, показанная в следующем примере, изменяет параметры конфигурации собраний, присвоенные сайту Redmond (-Identity site:Redmond). В этом случае значение свойства DesignateAsPresenter устанавливается для всех:
  
```PowerShell
Set-CsMeetingConfiguration -Identity "site:Redmond" -DesignateAsPresenter "Everyone"
```

Дополнительные сведения, включая полный список параметров, см. в [списке Set-CsMeetingConfiguration.](/powershell/module/skype/set-csmeetingconfiguration?view=skype-ps)
