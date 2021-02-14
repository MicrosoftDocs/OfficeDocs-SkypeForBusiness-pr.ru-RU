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
description: Телефоны общего пользования — это IP-телефоны, находящиеся обычно в общих рабочих помещениях или местах общего пользования, таких как вестибюли, кухни или заводские цеха. Телефоны общего звонков не требуется подключать к компьютеру, чтобы обеспечить функциональность объединенных коммуникаций Skype для бизнеса Server. После переноса развертывания в Skype для бизнеса Server 2019 необходимо также перенести контактные объекты, связанные с устаревшим телефоном общего звонков. В оболочке управления Skype для бизнеса Server сначала извлекаются все контактные объекты, связанные с устаревшими телефонами общего пользования, а затем эти объекты перемещаются в пул Skype для бизнеса Server 2019.
ms.openlocfilehash: b9cf5a32614ac41ac3c82773af4f37907c16e6f2
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752711"
---
# <a name="migrate-common-area-phones"></a>Миграция телефонов общего пользования

Телефоны общего пользования — это IP-телефоны, находящиеся обычно в общих рабочих помещениях или местах общего пользования, таких как вестибюли, кухни или заводские цеха. Телефоны общего звонков не требуется подключать к компьютеру, чтобы обеспечить функциональность объединенных коммуникаций Skype для бизнеса Server. After migrating a deployment to Skype for Business Server 2019, you must also migrate the contact objects associated with the legacy Common Area Phone. В оболочке управления Skype для бизнеса Server сначала извлекаются все объекты контактов, связанные с устаревшими телефонами общего пользования, а затем эти объекты перемещаются в пул Skype для бизнеса Server 2019.
  
### <a name="migrate-common-area-phones"></a>Миграция телефонов общего пользования

1. From the Skype for Business Server 2019 Front End server, open Skype for Business Server Management Shell.
    
2. В командной строке введите следующую команду:
    
   ```PowerShell
   Get-CsCommonAreaPhone -Filter {RegistrarPool -eq "pool01.contoso.net"} | Move-CsCommonAreaPhone -Target pool02.contoso.net
   ```

3. Чтобы убедиться, что все контактные объекты перемещены в пул Skype для бизнеса Server 2019, из оболочки управления Skype для бизнеса Server введите следующую информацию:
    
   ```PowerShell
   Get-CsCommonAreaPhone -Filter {RegistrarPool -eq "pool02.contoso.net"}
   ```

    Убедитесь, что все контактные объекты теперь связаны с пулом Skype для бизнеса Server 2019.
    

