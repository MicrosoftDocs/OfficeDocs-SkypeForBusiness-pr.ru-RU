---
title: Перенос аналоговых устройств
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Skype для бизнеса Server обеспечивает поддержку аналоговых устройств. В частности, к поддерживаемым аналоговым устройствам относятся аналоговые телефоны и факсимильные аппараты. Можно настроить квалифицированные шлюзы для поддержки использования аналоговых устройств в среде Skype для бизнеса Server. После перехода на Skype для бизнеса Server 2019 необходимо также перенести объекты Contact, связанные с аналоговыми устройствами. Используйте командную консоль Skype для бизнеса Server для получения всех контактных объектов, связанных с старыми аналоговыми устройствами, а затем переместите эти объекты в пул Skype для бизнеса Server 2019.
ms.openlocfilehash: 7b90a52486725c2cf30856dc643660d569d698e2
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752831"
---
# <a name="migrate-analog-devices"></a>Перенос аналоговых устройств

Skype для бизнеса Server обеспечивает поддержку аналоговых устройств. В частности, к поддерживаемым аналоговым устройствам относятся аналоговые телефоны и факсимильные аппараты. Можно настроить квалифицированные шлюзы для поддержки использования аналоговых устройств в среде Skype для бизнеса Server. После перехода на Skype для бизнеса Server 2019 необходимо также перенести объекты Contact, связанные с аналоговыми устройствами. Используйте командную консоль Skype для бизнеса Server для получения всех контактных объектов, связанных с старыми аналоговыми устройствами, а затем переместите эти объекты в пул Skype для бизнеса Server 2019.

### <a name="to-migrate-analog-devices"></a>Перенос аналоговых устройств

1. Запустите командную консоль Skype для бизнеса Server: нажмите кнопку **Пуск**, выберите **все программы**, затем **Microsoft Skype для бизнеса Server 2019**и щелкните **Командная консоль Skype для бизнеса Server**.

2. В командной строке введите следующую команду.

   ```PowerShell
   Get-CsAnalogDevice -Filter {RegistrarPool -eq "pool01.contoso.net"} | Move-CsAnalogDevice -Target pool02.contoso.net
   ```

3. Убедитесь, что все объекты Contacts были перемещены в пул Skype для бизнеса Server 2019. В командной строке введите следующую команду.

   ```PowerShell
   Get-CsAnalogDevice -Filter {RegistrarPool -eq "pool02.contoso.net"}
   ```

4. Убедитесь, что все объекты Contact теперь связаны с пулом Skype для бизнеса Server 2019.


