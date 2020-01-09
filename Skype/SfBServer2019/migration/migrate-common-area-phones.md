---
title: Миграция телефонов общего пользования
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Обычные телефоны — это IP-телефоны, которые чаще всего находятся в общей рабочей области или в общей области, например в зале ожидания, кухни или фабрики. Для поддержки функций объединенных коммуникаций в Skype для бизнеса Server не нужно подключаться к компьютеру с помощью обычных телефонов. После миграции развертывания на Skype для бизнеса Server 2019 необходимо также перенести объекты контактов, связанные с устаревшим стандартным телефонным пространством. С помощью командной консоли Skype для бизнеса Server вы сначала получите все объекты контактов, связанные с устаревшими телефонными устройствами, а затем переместите эти объекты в пул Skype для бизнеса Server 2019.
ms.openlocfilehash: f268c22f1d1132b3b5b8c1c1676e5b3a0182cf3f
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/08/2020
ms.locfileid: "40991154"
---
# <a name="migrate-common-area-phones"></a><span data-ttu-id="3a152-106">Миграция телефонов общего пользования</span><span class="sxs-lookup"><span data-stu-id="3a152-106">Migrate Common Area Phones</span></span>

<span data-ttu-id="3a152-107">Обычные телефоны — это IP-телефоны, которые чаще всего находятся в общей рабочей области или в общей области, например в зале ожидания, кухни или фабрики.</span><span class="sxs-lookup"><span data-stu-id="3a152-107">Common Area Phones are IP phones that most often reside in a shared workspace or common area, like a lobby, kitchen, or factory floor.</span></span> <span data-ttu-id="3a152-108">Для поддержки функций объединенных коммуникаций в Skype для бизнеса Server не нужно подключаться к компьютеру с помощью обычных телефонов.</span><span class="sxs-lookup"><span data-stu-id="3a152-108">Common Area Phones do not need to be connected to a computer to provide Skype for Business Server unified communications (UC) functionality.</span></span> <span data-ttu-id="3a152-109">После миграции развертывания на Skype для бизнеса Server 2019 необходимо также перенести объекты контактов, связанные с устаревшим стандартным телефонным пространством.</span><span class="sxs-lookup"><span data-stu-id="3a152-109">After migrating a deployment to Skype for Business Server 2019, you must also migrate the contact objects associated with the legacy Common Area Phone.</span></span> <span data-ttu-id="3a152-110">С помощью командной консоли Skype для бизнеса Server вы сначала получите все объекты контактов, связанные с устаревшими телефонными устройствами, а затем переместите эти объекты в пул Skype для бизнеса Server 2019.</span><span class="sxs-lookup"><span data-stu-id="3a152-110">Using Skype for Business Server Management Shell, you will first retrieve all contact objects associated with the legacy Common Area Phones, and then move those objects to the Skype for Business Server 2019 pool.</span></span>
  
### <a name="migrate-common-area-phones"></a><span data-ttu-id="3a152-111">Миграция телефонов общего пользования</span><span class="sxs-lookup"><span data-stu-id="3a152-111">Migrate Common Area Phones</span></span>

1. <span data-ttu-id="3a152-112">На сервере переднего плана Skype для бизнеса Server 2019 откройте консоль управления Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="3a152-112">From the Skype for Business Server 2019 Front End server, open Skype for Business Server Management Shell.</span></span>
    
2. <span data-ttu-id="3a152-113">В командной строке введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="3a152-113">From the command line, type the following:</span></span>
    
   ```PowerShell
   Get-CsCommonAreaPhone -Filter {RegistrarPool -eq "pool01.contoso.net"} | Move-CsCommonAreaPhone -Target pool02.contoso.net
   ```

3. <span data-ttu-id="3a152-114">Чтобы убедиться в том, что все объекты контакта были перемещены в пул Skype для бизнеса Server 2019, в командной консоли управления Skype для бизнеса Server введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="3a152-114">To verify that all contact objects have been moved to the Skype for Business Server 2019 pool, from the Skype for Business Server Management Shell type the following:</span></span>
    
   ```PowerShell
   Get-CsCommonAreaPhone -Filter {RegistrarPool -eq "pool02.contoso.net"}
   ```

    <span data-ttu-id="3a152-115">Убедитесь, что все объекты контакта теперь связаны с пулом 2019 в Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="3a152-115">Verify that all contact objects are now associated with the Skype for Business Server 2019 pool.</span></span>
    

