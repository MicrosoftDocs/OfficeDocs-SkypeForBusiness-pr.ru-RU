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
description: Телефоны общего пользования — это IP-телефоны, находящиеся обычно в общих рабочих помещениях или местах общего пользования, таких как вестибюли, кухни или заводские цеха. Общие телефоны области не должны быть подключены к компьютеру, чтобы обеспечить Skype для бизнеса Server единой связи (UC). После переноса развертывания на Skype для бизнеса Server 2019 г. необходимо также перенести контактные объекты, связанные с устаревшим общим Телефон. С помощью Skype для бизнеса Server Management Shell вы сначала извлекаете все контактные объекты, связанные с устаревшими телефонами общей области, а затем переместите эти объекты в пул Skype для бизнеса Server 2019 г.
ms.openlocfilehash: 808e874216fac97b01face6efa7aae00e269b74ee0f009b106f872a33a6d6261
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2021
ms.locfileid: "54340435"
---
# <a name="migrate-common-area-phones"></a>Миграция телефонов общего пользования

Телефоны общего пользования — это IP-телефоны, находящиеся обычно в общих рабочих помещениях или местах общего пользования, таких как вестибюли, кухни или заводские цеха. Общие телефоны области не должны быть подключены к компьютеру, чтобы обеспечить Skype для бизнеса Server единой связи (UC). После переноса развертывания на Skype для бизнеса Server 2019 г. необходимо также перенести контактные объекты, связанные с устаревшим общим Телефон. С помощью Skype для бизнеса Server management Shell вы сначала извлекаете все контактные объекты, связанные с устаревшими телефонами общей области, а затем переместите эти объекты в пул Skype для бизнеса Server 2019 г.
  
### <a name="migrate-common-area-phones"></a>Миграция телефонов общего пользования

1. На сервере Skype для бизнеса Server 2019 откройте Skype для бизнеса Server управления.
    
2. В командной строке введите следующую команду:
    
   ```PowerShell
   Get-CsCommonAreaPhone -Filter {RegistrarPool -eq "pool01.contoso.net"} | Move-CsCommonAreaPhone -Target pool02.contoso.net
   ```

3. Чтобы убедиться, что все контактные объекты были перемещены в пул Skype для бизнеса Server 2019 г., из Skype для бизнеса Server management Shell введите следующее:
    
   ```PowerShell
   Get-CsCommonAreaPhone -Filter {RegistrarPool -eq "pool02.contoso.net"}
   ```

    Убедитесь, что все контактные объекты теперь связаны с пулом Skype для бизнеса Server 2019 года.
    

