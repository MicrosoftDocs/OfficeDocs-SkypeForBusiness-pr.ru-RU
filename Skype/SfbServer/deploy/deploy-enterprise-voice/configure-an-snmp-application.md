---
title: Настройка SNMP-приложения в Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: c4b4a736-3b2e-45b9-a965-19d22161ad57
description: Настройте приложение SNMP для работы с E9-1-1 в корпоративной голосовой связи Skype для бизнеса Server.
ms.openlocfilehash: 575c982dae20ed085e49690edfbb141786390516
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "34303420"
---
# <a name="configure-an-snmp-application-in-skype-for-business-server"></a>Настройка SNMP-приложения в Skype для бизнеса Server
 
Настройте приложение SNMP для работы с E9-1-1 в корпоративной голосовой связи Skype для бизнеса Server. 
  
В Skype для бизнеса Server есть стандартный интерфейс веб-службы, который можно использовать для подключения службы сведений о расположении к приложениям SNMP, которые соответствуют MAC-адресам с портом и коммутатором. 
  
Если установлено приложение SNMP и служба "сведения о местоположении" не может найти соответствие в базе данных расположения, Служба сведений о расположении автоматически запрашивает это приложение, используя MAC-адрес, предоставленный клиентом. Затем служба сведения о местоположении использует данные порта и коммутатора, возвращенные приложением SNMP, для повторного запроса к базе данных о расположении.
  
> [!NOTE]
> MAC-адреса недоступны на компьютерах под управлением Windows 8. 
  
### <a name="to-configure-the-snmp-application-url"></a>Настройка URL-адреса приложения SNMP

1.  Запустите командную консоль Skype для бизнеса: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Skype для бизнеса 2015** и щелкните элемент **Командная консоль Skype для бизнеса**.
    
2. Запустите следующий командлет для настройки URL-адреса приложения SNMP. 
    
   ```
   Set-CsWebServiceConfiguration -MACResolverUrl "<SNMP application url>" 
   ```

## <a name="see-also"></a>См. также

[Set-Ксвебсервицеконфигуратион](https://docs.microsoft.com/powershell/module/skype/set-cswebserviceconfiguration?view=skype-ps)

