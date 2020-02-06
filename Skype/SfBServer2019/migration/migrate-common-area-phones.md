---
title: Миграция телефонов общего пользования
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Обычные телефоны — это IP-телефоны, которые чаще всего находятся в общей рабочей области или в общей области, например в зале ожидания, кухни или фабрики. Для поддержки функций объединенных коммуникаций в Skype для бизнеса Server не нужно подключаться к компьютеру с помощью обычных телефонов. После миграции развертывания на Skype для бизнеса Server 2019 необходимо также перенести объекты контактов, связанные с устаревшим стандартным телефонным пространством. С помощью командной консоли Skype для бизнеса Server вы сначала получите все объекты контактов, связанные с устаревшими телефонными устройствами, а затем переместите эти объекты в пул Skype для бизнеса Server 2019.
ms.openlocfilehash: 5110f91788d09f644e20680f91f1cbafe146bdd6
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41813567"
---
# <a name="migrate-common-area-phones"></a><span data-ttu-id="7d15f-106">Миграция телефонов общего пользования</span><span class="sxs-lookup"><span data-stu-id="7d15f-106">Migrate Common Area Phones</span></span>

<span data-ttu-id="7d15f-107">Обычные телефоны — это IP-телефоны, которые чаще всего находятся в общей рабочей области или в общей области, например в зале ожидания, кухни или фабрики.</span><span class="sxs-lookup"><span data-stu-id="7d15f-107">Common Area Phones are IP phones that most often reside in a shared workspace or common area, like a lobby, kitchen, or factory floor.</span></span> <span data-ttu-id="7d15f-108">Для поддержки функций объединенных коммуникаций в Skype для бизнеса Server не нужно подключаться к компьютеру с помощью обычных телефонов.</span><span class="sxs-lookup"><span data-stu-id="7d15f-108">Common Area Phones do not need to be connected to a computer to provide Skype for Business Server unified communications (UC) functionality.</span></span> <span data-ttu-id="7d15f-109">После миграции развертывания на Skype для бизнеса Server 2019 необходимо также перенести объекты контактов, связанные с устаревшим стандартным телефонным пространством.</span><span class="sxs-lookup"><span data-stu-id="7d15f-109">After migrating a deployment to Skype for Business Server 2019, you must also migrate the contact objects associated with the legacy Common Area Phone.</span></span> <span data-ttu-id="7d15f-110">С помощью командной консоли Skype для бизнеса Server вы сначала получите все объекты контактов, связанные с устаревшими телефонными устройствами, а затем переместите эти объекты в пул Skype для бизнеса Server 2019.</span><span class="sxs-lookup"><span data-stu-id="7d15f-110">Using Skype for Business Server Management Shell, you will first retrieve all contact objects associated with the legacy Common Area Phones, and then move those objects to the Skype for Business Server 2019 pool.</span></span>
  
### <a name="migrate-common-area-phones"></a><span data-ttu-id="7d15f-111">Миграция телефонов общего пользования</span><span class="sxs-lookup"><span data-stu-id="7d15f-111">Migrate Common Area Phones</span></span>

1. <span data-ttu-id="7d15f-112">На сервере переднего плана Skype для бизнеса Server 2019 откройте консоль управления Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="7d15f-112">From the Skype for Business Server 2019 Front End server, open Skype for Business Server Management Shell.</span></span>
    
2. <span data-ttu-id="7d15f-113">В командной строке введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="7d15f-113">From the command line, type the following:</span></span>
    
   ```PowerShell
   Get-CsCommonAreaPhone -Filter {RegistrarPool -eq "pool01.contoso.net"} | Move-CsCommonAreaPhone -Target pool02.contoso.net
   ```

3. <span data-ttu-id="7d15f-114">Чтобы убедиться в том, что все объекты контакта были перемещены в пул Skype для бизнеса Server 2019, в командной консоли управления Skype для бизнеса Server введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="7d15f-114">To verify that all contact objects have been moved to the Skype for Business Server 2019 pool, from the Skype for Business Server Management Shell type the following:</span></span>
    
   ```PowerShell
   Get-CsCommonAreaPhone -Filter {RegistrarPool -eq "pool02.contoso.net"}
   ```

    <span data-ttu-id="7d15f-115">Убедитесь, что все объекты контакта теперь связаны с пулом 2019 в Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="7d15f-115">Verify that all contact objects are now associated with the Skype for Business Server 2019 pool.</span></span>
    

