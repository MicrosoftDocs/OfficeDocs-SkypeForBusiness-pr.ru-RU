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
ms.openlocfilehash: eb1947f24968dccc6f45b6d8ea3a7df42282a58f
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49804159"
---
# <a name="configure-an-snmp-application-in-skype-for-business-server"></a>Настройка приложения SNMP в Skype для бизнеса Server
 
Настройка приложения SNMP для работы с E9-1-1 в Skype для бизнеса Server Корпоративная голосовая связь. 
  
Skype для бизнеса Server включает стандартный интерфейс веб-службы, который можно использовать для подключения службы сведений о расположении к приложениям SNMP, которые соответствуют MAC-адресам с данными о портах и коммутаторах. 
  
Если приложение SNMP установлено и службе сведений о расположении не удается найти совпадение в базе данных расположений, служба сведений о расположении автоматически запрашивает приложение с помощью MAC-адреса, предоставленного клиентом. Затем служба сведений о расположении использует порт и сведения о коммутаторе, возвращенные приложением SNMP, для повторного запроса базы данных расположений.
  
> [!NOTE]
> MAC-адреса недоступны на компьютерах с Windows 8. 
  
### <a name="to-configure-the-snmp-application-url"></a>Настройка URL-адреса приложения SNMP

1.  Запустите оболочку управления Skype для бизнеса Server: нажмите кнопку "Начните", выберите "Все программы", "Skype для бизнеса **2015",** а затем щелкните "Skype для бизнеса Server Management **Shell".**
    
2. Запустите следующий командлет для настройки URL-адреса приложения SNMP. 
    
   ```powershell
   Set-CsWebServiceConfiguration -MACResolverUrl "<SNMP application url>" 
   ```

## <a name="see-also"></a>См. также

[Set-CsWebServiceConfiguration](https://docs.microsoft.com/powershell/module/skype/set-cswebserviceconfiguration?view=skype-ps)

