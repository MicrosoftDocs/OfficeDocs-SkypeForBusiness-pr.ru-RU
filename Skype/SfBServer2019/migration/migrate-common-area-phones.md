---
title: Миграция телефонов общего пользования
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
description: Телефоны общего пользования — это IP-телефоны, находящиеся обычно в общих рабочих помещениях или местах общего пользования, таких как вестибюли, кухни или заводские цеха. Для поддержки функций объединенных коммуникаций в Skype для бизнеса Server не требуется подключение к компьютеру телефонов. После переноса развертывания на Skype для бизнеса Server 2019 необходимо также перенести объекты Contacts, связанные с устаревшим стандартом Common Area Phone. С помощью командной консоли Skype для бизнеса Server вы сначала получите все объекты Contacts, связанные с устаревшими телефонами общего пользования, а затем переместите эти объекты в пул Skype для бизнеса Server 2019.
ms.openlocfilehash: b9cf5a32614ac41ac3c82773af4f37907c16e6f2
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752711"
---
# <a name="migrate-common-area-phones"></a>Миграция телефонов общего пользования

Телефоны общего пользования — это IP-телефоны, находящиеся обычно в общих рабочих помещениях или местах общего пользования, таких как вестибюли, кухни или заводские цеха. Для поддержки функций объединенных коммуникаций в Skype для бизнеса Server не требуется подключение к компьютеру телефонов. После переноса развертывания на Skype для бизнеса Server 2019 необходимо также перенести объекты Contacts, связанные с устаревшим стандартом Common Area Phone. С помощью командной консоли Skype для бизнеса Server вы сначала получите все объекты Contacts, связанные с устаревшими телефонами, а затем переместите эти объекты в пул Skype для бизнеса Server 2019.
  
### <a name="migrate-common-area-phones"></a>Миграция телефонов общего пользования

1. На сервере переднего плана Skype для бизнеса Server 2019 откройте консоль управления Skype для бизнеса Server.
    
2. В командной строке введите следующую команду:
    
   ```PowerShell
   Get-CsCommonAreaPhone -Filter {RegistrarPool -eq "pool01.contoso.net"} | Move-CsCommonAreaPhone -Target pool02.contoso.net
   ```

3. Чтобы убедиться, что все объекты контакта были перемещены в пул Skype для бизнеса Server 2019, в командной консоли Skype для бизнеса Server введите следующую команду:
    
   ```PowerShell
   Get-CsCommonAreaPhone -Filter {RegistrarPool -eq "pool02.contoso.net"}
   ```

    Убедитесь, что все объекты Contact теперь связаны с пулом Skype для бизнеса Server 2019.
    

