---
title: Перенос аналоговых устройств
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Скайп для Business Server обеспечивает поддержку аналоговых устройств. В частности поддерживаемые аналоговых устройств, аналоговые звука телефонов и аналоговых факсов. Вы можете настроить квалифицированного шлюзов для поддержки использования аналоговых устройств в вашей Скайп среды Business Server. После миграции Скайп для Business Server 2019, также необходимо перенести контактных объектов, связанных с аналоговых устройств. Используйте Скайп для консоли Business Server для первой загрузки все контактные объекты, связанные с устаревших аналоговых устройств и затем перетащить эти объекты в Скайп для пула Business Server 2019.
ms.openlocfilehash: 25de46ce2d0b6a86553b78d591f35f9d881fb55e
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/24/2018
ms.locfileid: "25030415"
---
# <a name="migrate-analog-devices"></a>Перенос аналоговых устройств

Скайп для Business Server обеспечивает поддержку аналоговых устройств. В частности поддерживаемые аналоговых устройств, аналоговые звука телефонов и аналоговых факсов. Вы можете настроить квалифицированного шлюзов для поддержки использования аналоговых устройств в вашей Скайп среды Business Server. После миграции Скайп для Business Server 2019, также необходимо перенести контактных объектов, связанных с аналоговых устройств. Используйте Скайп для консоли Business Server для первой загрузки все контактные объекты, связанные с устаревших аналоговых устройств и затем перетащить эти объекты в Скайп для пула Business Server 2019.
  
### <a name="to-migrate-analog-devices"></a>Перенос аналоговых устройств

1. Запустите Скайп для консоли Business Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы**, щелкните **Скайп Microsoft для Business Server 2019**и нажмите кнопку **Скайп для консоли Business Server**.
    
2. В командной строке введите следующую команду:
    
  ```
  Get-CsAnalogDevice -Filter {RegistrarPool -eq "pool01.contoso.net"} | Move-CsAnalogDevice -Target pool02.contoso.net
  
  ```

3. Убедитесь в том, что все контактные объекты были перемещены в Скайп для пула Business Server 2019. В командной строке введите следующую команду:
    
  ```
  Get-CsAnalogDevice -Filter {RegistrarPool -eq "pool02.contoso.net"}
  ```

4. Убедитесь, что все контактные объекты теперь связанных с Скайп для пула Business Server 2019.
    

