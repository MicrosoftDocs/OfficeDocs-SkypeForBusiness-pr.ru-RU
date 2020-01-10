---
title: Настройка дополнительной службы сведений о расположении в Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 083ffbc6-7c18-4141-85f9-8825b62c3d10
description: Настройте базу данных дополнительного расположения (СЛС) для E9-1-1 в корпоративной голосовой связи Skype для бизнеса Server.
ms.openlocfilehash: 1743a4c5f49fcc01fe2f0878c596e0d1bb530621
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/09/2020
ms.locfileid: "41002000"
---
# <a name="configure-a-secondary-location-information-service-in-skype-for-business-server"></a>Настройка дополнительной службы сведений о расположении в Skype для бизнеса Server
 
Настройте базу данных дополнительного расположения (СЛС) для E9-1-1 в корпоративной голосовой связи Skype для бизнеса Server. 
  
Skype для бизнеса Server предоставляет интерфейс веб-службы, который можно использовать для указания службы сведений о расположении в базу данных дополнительного расположения (СЛС). Интерфейс веб-службы, который подключается к базе данных СЛС, должен соответствовать WSDL службы сведений о расположении. Если вы настроили базу данных расположения и дополнительную базу данных расположения, Служба сведений о расположении сначала запрашивает базу данных расположения, а если совпадений не найдено, отправляет запрос на расположение от клиента в базу данных СЛС. Если расположение находится в СЛС, служба сведения о местоположении затем отправляет клиенту расположение обратно. 
  
### <a name="to-configure-a-secondary-location-database"></a>Настройка базы данных дополнительных расположений

1. Запустите командную консоль Skype для бизнеса: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Skype для бизнеса 2015** и щелкните элемент **Командная консоль Skype для бизнеса**.
    
2. Чтобы настроить URL-адрес базы данных дополнительных расположений, выполните следующий командлет. 
    
   ```powershell
   Set-CsWebServiceConfiguration -SecondaryLocationSourceURL "<web service url>" 
   ```

## <a name="see-also"></a>См. также

[Set-Ксвебсервицеконфигуратион](https://docs.microsoft.com/powershell/module/skype/set-cswebserviceconfiguration?view=skype-ps)

