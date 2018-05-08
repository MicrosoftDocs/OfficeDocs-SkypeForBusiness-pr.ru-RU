---
title: Настройка службы сведений о дополнительном местоположении в Skype для бизнеса Server 2015
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 8/17/2015
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 083ffbc6-7c18-4141-85f9-8825b62c3d10
description: Настройка базы данных-источника (SLS) дополнительных расположений для E9-1-1 в Скайп Business Server корпоративной голосовой связи.
ms.openlocfilehash: 4eaab1b6dfaae9b1298cce3544d89f8b6724733e
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="configure-a-secondary-location-information-service-in-skype-for-business-server-2015"></a>Настройка службы сведений о дополнительном местоположении в Skype для бизнеса Server 2015
 
Настройка базы данных-источника (SLS) дополнительных расположений для E9-1-1 в Скайп Business Server корпоративной голосовой связи. 
  
Скайп для Business Server предоставляет интерфейс веб-службы, которые можно использовать для указания службе информирования о местонахождении к базе данных дополнительного источника местоположения (SLS). Интерфейс веб-службы, который подключается к базе данных SLS должен соответствовать типу WSDL службы и сведения о расположении. Если расположение базы данных и базы данных дополнительных расположений службе информирования о местонахождении сначала отправляет запрос базы данных местоположений и если совпадение не найдено, отправляет запрос местоположения из клиента в SLS базу данных. Если оно существует в SLS, сведения о расположении службы отправляет расположение клиенту. 
  
### <a name="to-configure-a-secondary-location-database"></a>Настройка базы данных дополнительных расположений

1. Запустите командную консоль Skype для бизнеса: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Skype для бизнеса 2015** и щелкните элемент **Командная консоль Skype для бизнеса**.
    
2. Чтобы настроить URL-адрес базы данных дополнительных расположений, выполните следующий командлет. 
    
   ```
   Set-CsWebServiceConfiguration -SecondaryLocationSourceURL "<web service url>" 
   ```

## <a name="see-also"></a>См. также

#### 

[Командлет Set-CsWebServiceConfiguration](https://docs.microsoft.com/powershell/module/skype/set-cswebserviceconfiguration?view=skype-ps)

