---
title: Настройка приложения SNMP в Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: c4b4a736-3b2e-45b9-a965-19d22161ad57
description: Настройка приложения SNMP для работы с E9-1-1 в Skype для бизнеса Server Корпоративная голосовая связь.
ms.openlocfilehash: f8b4c7503524dacdc20e85fc68f0a79286e38c2e
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51103635"
---
# <a name="configure-an-snmp-application-in-skype-for-business-server"></a>Настройка приложения SNMP в Skype для бизнеса Server
 
Настройка приложения SNMP для работы с E9-1-1 в Skype для бизнеса Server Корпоративная голосовая связь. 
  
Skype для бизнеса Server включает стандартный интерфейс веб-службы, который можно использовать для подключения службы информации о расположении к приложениям простого протокола управления сетью (SNMP), которые соответствуют mac-адресам с портом и сведениями о переключениях. 
  
Если приложение SNMP установлено и служба сведений о расположении не находит совпадение в базе данных расположения, служба информации о расположении автоматически запрашивает приложение с помощью mac-адреса, предоставленного клиентом. Затем служба сведений о расположении использует порт и переключение сведений, возвращаемой приложением SNMP, для повторного запроса базы данных расположения.
  
> [!NOTE]
> Mac-адреса недоступны на компьютерах с Windows 8. 
  
### <a name="to-configure-the-snmp-application-url"></a>Настройка URL-адреса приложения SNMP

1.  Запустите оболочку управления Skype для бизнес-серверов: нажмите кнопку Начните, щелкните Все **программы,** щелкните Skype для бизнеса **2015,** а затем нажмите **кнопку Skype для управления бизнес-серверами.**
    
2. Запустите следующий командлет для настройки URL-адреса приложения SNMP. 
    
   ```powershell
   Set-CsWebServiceConfiguration -MACResolverUrl "<SNMP application url>" 
   ```

## <a name="see-also"></a>См. также

[Set-CsWebServiceConfiguration](/powershell/module/skype/set-cswebserviceconfiguration?view=skype-ps)