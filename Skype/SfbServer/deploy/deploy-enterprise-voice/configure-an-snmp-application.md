---
title: Настройка SNMP-приложения в Скайп для Business Server
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: c4b4a736-3b2e-45b9-a965-19d22161ad57
description: Настройка SNMP-приложения для работы с E9-1-1 в Скайп Business Server корпоративной голосовой связи.
ms.openlocfilehash: 9c325777b43c455016657caf4e15316a07282b52
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/24/2018
ms.locfileid: "20992437"
---
# <a name="configure-an-snmp-application-in-skype-for-business-server"></a>Настройка SNMP-приложения в Скайп для Business Server
 
Настройка SNMP-приложения для работы с E9-1-1 в Скайп Business Server корпоративной голосовой связи. 
  
Скайп для Business Server включает в себя стандартных веб-интерфейс службы, которые можно использовать для подключения к сети протокола SNMP (Simple Management) приложений, которые соответствуют MAC-адреса с портом и сведений о переключении службе информирования о местонахождении. 
  
Если установлено приложение SNMP и происходит сбой службы сведения о расположении для поиска в базе данных местонахождения, сведения о расположении службы автоматически отправляет запрос приложения с помощью MAC-адрес, заданных клиентом. Сведения о расположении службы затем использует порт и переключатель информацию, возвращенную приложения SNMP для запроса базы данных местоположений еще раз.
  
> [!NOTE]
> MAC-адреса недоступны на компьютерах под управлением Windows 8. 
  
### <a name="to-configure-the-snmp-application-url"></a>Настройка URL-адреса приложения SNMP

1.  Запустите командную консоль Skype для бизнеса: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Skype для бизнеса 2015** и щелкните элемент **Командная консоль Skype для бизнеса**.
    
2. Запустите следующий командлет для настройки URL-адреса приложения SNMP. 
    
   ```
   Set-CsWebServiceConfiguration -MACResolverUrl "<SNMP application url>" 
   ```

## <a name="see-also"></a>См. также

[Командлет Set-CsWebServiceConfiguration](https://docs.microsoft.com/powershell/module/skype/set-cswebserviceconfiguration?view=skype-ps)

