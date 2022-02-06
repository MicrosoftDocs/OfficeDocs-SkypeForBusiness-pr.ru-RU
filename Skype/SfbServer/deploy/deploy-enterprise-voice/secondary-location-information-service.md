---
title: Настройка дополнительной службы сведений о местоположении в Skype для бизнеса Server
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
ms.assetid: 083ffbc6-7c18-4141-85f9-8825b62c3d10
description: Настройка базы данных дополнительного источника расположения (SLS) для E9-1-1 в Skype для бизнеса Server Корпоративная голосовая связь.
---

# <a name="configure-a-secondary-location-information-service-in-skype-for-business-server"></a>Настройка дополнительной службы сведений о местоположении в Skype для бизнеса Server
 
Настройка базы данных дополнительного источника расположения (SLS) для E9-1-1 в Skype для бизнеса Server Корпоративная голосовая связь. 
  
Skype для бизнеса Server интерфейс веб-службы, который можно использовать для указать службу информации о расположении на базу данных secondary Location Source (SLS). Интерфейс веб-службы, подключается к базе данных SLS, должен соответствовать службе сведений о расположении WSDL. Если настроена база данных расположения и вторичная база данных расположения, служба сведений о расположении сначала запрашивает базу данных расположения, а если совпадение не найдено, отправляет запрос о расположении от клиента в базу данных SLS. Если расположение существует в службе SLS, служба сведений о расположении отправляет его клиенту. 
  
### <a name="to-configure-a-secondary-location-database"></a>Настройка базы данных вторичного расположения

1. Запустите Skype для бизнеса Server: нажмите кнопку **Начните, нажмите** кнопку Все **программы, нажмите** кнопку Skype для бизнеса **2015**, а затем нажмите кнопку **Skype для бизнеса Server управленческой оболочки**.
    
2. Запустите следующий комдлет, чтобы настроить URL-адрес для расположения базы данных вторичного расположения. 
    
   ```powershell
   Set-CsWebServiceConfiguration -SecondaryLocationSourceURL "<web service url>" 
   ```

## <a name="see-also"></a>См. также

[Set-CsWebServiceConfiguration](/powershell/module/skype/set-cswebserviceconfiguration?view=skype-ps)