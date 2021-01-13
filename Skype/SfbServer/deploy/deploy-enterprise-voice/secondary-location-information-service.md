---
title: Настройка дополнительной службы сведений о местоположении в Skype для бизнеса Server
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
ms.assetid: 083ffbc6-7c18-4141-85f9-8825b62c3d10
description: Настройка базы данных дополнительного источника расположения (SLS) для E9-1-1 в Skype для бизнеса Server Корпоративная голосовая связь.
ms.openlocfilehash: fd70957526d193951b56211c0d5a6623a26419e2
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49830649"
---
# <a name="configure-a-secondary-location-information-service-in-skype-for-business-server"></a>Настройка дополнительной службы сведений о местоположении в Skype для бизнеса Server
 
Настройка базы данных дополнительного источника расположения (SLS) для E9-1-1 в Skype для бизнеса Server Корпоративная голосовая связь. 
  
Skype для бизнеса Server предоставляет интерфейс веб-службы, который можно использовать, чтобы указать службе сведений о расположении базу данных дополнительного источника расположения (SLS). Интерфейс веб-службы, который подключается к базе данных SLS, должен соответствовать WSDL-службе сведений о расположении. Если настроены как база данных расположений, так и база данных дополнительных расположений, служба сведений о расположении сначала запрашивает базу данных расположений и, если совпадение не найдено, отправляет запрос о расположении от клиента в базу данных SLS. Если расположение существует в SLS, служба сведений о расположении отправляет его обратно клиенту. 
  
### <a name="to-configure-a-secondary-location-database"></a>Настройка базы данных дополнительного расположения

1. Запустите оболочку управления Skype для бизнеса Server: нажмите кнопку "Начните", выберите "Все программы", "Skype для бизнеса **2015",** а затем щелкните "Skype для бизнеса Server Management **Shell".**
    
2. Чтобы настроить URL-адрес для расположения базы данных дополнительных расположений, запустите следующий cmdlet. 
    
   ```powershell
   Set-CsWebServiceConfiguration -SecondaryLocationSourceURL "<web service url>" 
   ```

## <a name="see-also"></a>См. также

[Set-CsWebServiceConfiguration](https://docs.microsoft.com/powershell/module/skype/set-cswebserviceconfiguration?view=skype-ps)

