---
title: Настройка приложения SNMP в Skype для бизнеса Server
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.collection:
  - IT_Skype16
  - Strat_SB_Admin
ms.custom: null
ms.assetid: c4b4a736-3b2e-45b9-a965-19d22161ad57
description: Настройка приложения SNMP для работы с E9-1-1 в Skype для бизнеса Server Корпоративная голосовая связь.
---

# <a name="configure-an-snmp-application-in-skype-for-business-server"></a>Настройка приложения SNMP в Skype для бизнеса Server
 
Настройка приложения SNMP для работы с E9-1-1 в Skype для бизнеса Server Корпоративная голосовая связь. 
  
Skype для бизнеса Server стандартный интерфейс веб-службы, который можно использовать для подключения службы информации о расположении к приложениям простого протокола управления сетью (SNMP), которые соответствуют mac-адресам с портом и сведениями о переключениях. 
  
Если приложение SNMP установлено и служба сведений о расположении не находит совпадение в базе данных расположения, служба информации о расположении автоматически запрашивает приложение с помощью mac-адреса, предоставленного клиентом. Затем служба сведений о расположении использует порт и переключение сведений, возвращаемой приложением SNMP, для повторного запроса базы данных расположения.
  
> [!NOTE]
> Mac-адреса недоступны на компьютерах с Windows 8. 
  
### <a name="to-configure-the-snmp-application-url"></a>Настройка URL-адреса приложения SNMP

1.  Запустите Skype для бизнеса Server: нажмите кнопку **Начните, нажмите** кнопку Все **программы, нажмите** кнопку Skype для бизнеса **2015**, а затем нажмите кнопку **Skype для бизнеса Server управленческой оболочки**.
    
2. Запустите следующий командлет для настройки URL-адреса приложения SNMP. 
    
   ```powershell
   Set-CsWebServiceConfiguration -MACResolverUrl "<SNMP application url>" 
   ```

## <a name="see-also"></a>См. также

[Set-CsWebServiceConfiguration](/powershell/module/skype/set-cswebserviceconfiguration?view=skype-ps)