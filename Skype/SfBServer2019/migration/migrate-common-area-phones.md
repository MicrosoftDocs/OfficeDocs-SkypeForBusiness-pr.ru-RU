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
# <a name="migrate-common-area-phones"></a><span data-ttu-id="42c60-106">Миграция телефонов общего пользования</span><span class="sxs-lookup"><span data-stu-id="42c60-106">Migrate Common Area Phones</span></span>

<span data-ttu-id="42c60-107">Телефоны общего пользования — это IP-телефоны, находящиеся обычно в общих рабочих помещениях или местах общего пользования, таких как вестибюли, кухни или заводские цеха.</span><span class="sxs-lookup"><span data-stu-id="42c60-107">Common Area Phones are IP phones that most often reside in a shared workspace or common area, like a lobby, kitchen, or factory floor.</span></span> <span data-ttu-id="42c60-108">Телефоны общего звонков не требуется подключать к компьютеру, чтобы обеспечить функциональность объединенных коммуникаций Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="42c60-108">Common Area Phones do not need to be connected to a computer to provide Skype for Business Server unified communications (UC) functionality.</span></span> <span data-ttu-id="42c60-109">After migrating a deployment to Skype for Business Server 2019, you must also migrate the contact objects associated with the legacy Common Area Phone.</span><span class="sxs-lookup"><span data-stu-id="42c60-109">After migrating a deployment to Skype for Business Server 2019, you must also migrate the contact objects associated with the legacy Common Area Phone.</span></span> <span data-ttu-id="42c60-110">В оболочке управления Skype для бизнеса Server сначала извлекаются все объекты контактов, связанные с устаревшими телефонами общего пользования, а затем эти объекты перемещаются в пул Skype для бизнеса Server 2019.</span><span class="sxs-lookup"><span data-stu-id="42c60-110">Using Skype for Business Server Management Shell, you will first retrieve all contact objects associated with the legacy Common Area Phones, and then move those objects to the Skype for Business Server 2019 pool.</span></span>
  
### <a name="migrate-common-area-phones"></a><span data-ttu-id="42c60-111">Миграция телефонов общего пользования</span><span class="sxs-lookup"><span data-stu-id="42c60-111">Migrate Common Area Phones</span></span>

1. <span data-ttu-id="42c60-112">From the Skype for Business Server 2019 Front End server, open Skype for Business Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="42c60-112">From the Skype for Business Server 2019 Front End server, open Skype for Business Server Management Shell.</span></span>
    
2. <span data-ttu-id="42c60-113">В командной строке введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="42c60-113">From the command line, type the following:</span></span>
    
   ```PowerShell
   Get-CsCommonAreaPhone -Filter {RegistrarPool -eq "pool01.contoso.net"} | Move-CsCommonAreaPhone -Target pool02.contoso.net
   ```

3. <span data-ttu-id="42c60-114">Чтобы убедиться, что все контактные объекты перемещены в пул Skype для бизнеса Server 2019, из оболочки управления Skype для бизнеса Server введите следующую информацию:</span><span class="sxs-lookup"><span data-stu-id="42c60-114">To verify that all contact objects have been moved to the Skype for Business Server 2019 pool, from the Skype for Business Server Management Shell type the following:</span></span>
    
   ```PowerShell
   Get-CsCommonAreaPhone -Filter {RegistrarPool -eq "pool02.contoso.net"}
   ```

    <span data-ttu-id="42c60-115">Убедитесь, что все контактные объекты теперь связаны с пулом Skype для бизнеса Server 2019.</span><span class="sxs-lookup"><span data-stu-id="42c60-115">Verify that all contact objects are now associated with the Skype for Business Server 2019 pool.</span></span>
    

