---
title: Изменение параметров настройки собраний в Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 11d1f9ac-0029-429b-be2b-d7591abfc192
description: 'Сводка: сведения о том, как изменить параметры конфигурации собрания в Skype для бизнеса Server.'
ms.openlocfilehash: 2e9d8a737a2bfc48cdcbe39540a22e4c236003b3
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/08/2020
ms.locfileid: "40992856"
---
# <a name="modify-meeting-configuration-settings-in-skype-for-business-server"></a>Изменение параметров настройки собраний в Skype для бизнеса Server
 
**Сводка:** Сведения о том, как изменить параметры конфигурации собрания в Skype для бизнеса Server.
  
Параметры конфигурации собрания можно изменить с помощью панели управления Skype для бизнеса Server или с помощью командной консоли Skype для бизнеса Server.
  
## <a name="modify-meeting-configuration-settings-by-using-skype-for-business-server-control-panel"></a>Изменение параметров конфигурации собраний с помощью панели управления Skype для бизнеса Server

1. Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.
    
2.  Откройте панель управления Skype для бизнеса Server.
    
3. В левой области навигации щелкните **Конференц-связь**, затем **Конфигурация собрания**.
    
4. В списке конфигураций собрания выберите конфигурацию, которую необходимо изменить, щелкните **Изменить**, а затем выберите **Показать подробности**.
    
5. В области **Изменение конфигурации собрания** можно изменить любые параметры конфигурации, за исключением имени конфигурации, которое не подлежит изменению.
    
6. Нажмите **Исполнить**.
    
## <a name="modify-meeting-configuration-settings-by-using-skype-for-business-server-management-shell"></a>Изменение параметров конфигурации собрания с помощью командной консоли Skype для бизнеса Server

Для изменения параметров конфигурации собрания используется командлет **Set-CsMeetingConfiguration**.
  
Приведенная в примере ниже команда изменяет назначенные сайту Redmond (-Identity site:Redmond) параметры конфигурации собраний. В данном случае свойству DesignateAsPresenter задается значение Everyone.
  
```PowerShell
Set-CsMeetingConfiguration -Identity "site:Redmond" -DesignateAsPresenter "Everyone"
```

Дополнительные сведения, в том числе полный список параметров, можно найти в разделе [Set-ксмитингконфигуратион](https://docs.microsoft.com/powershell/module/skype/set-csmeetingconfiguration?view=skype-ps).
  

