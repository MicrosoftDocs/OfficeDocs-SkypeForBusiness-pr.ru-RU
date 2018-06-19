---
title: Настройка SNMP-приложения в Skype для бизнеса Server 2015
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
ms.assetid: c4b4a736-3b2e-45b9-a965-19d22161ad57
description: Настройка SNMP-приложения для работы с E9-1-1 в Скайп Business Server корпоративной голосовой связи.
ms.openlocfilehash: 6024119042bede23f6b38f07c6ccdffa86a76db7
ms.sourcegitcommit: b14cfca231b618ec28cf9f4efe11cb3e8aceb34b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/19/2018
ms.locfileid: "19500419"
---
# <a name="configure-an-snmp-application-in-skype-for-business-server-2015"></a>Настройка SNMP-приложения в Skype для бизнеса Server 2015
 
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

