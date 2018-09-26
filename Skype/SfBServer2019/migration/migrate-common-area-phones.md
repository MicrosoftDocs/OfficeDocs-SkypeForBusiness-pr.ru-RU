---
title: Миграция телефонов общего пользования
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Региональные телефоны обладают IP-телефоны, что наиболее часто находятся в общей рабочей области или общего доступа как основной, кухни или фабрики этажа. Региональные телефоны, подключенной к компьютеру, чтобы обеспечить Скайп для Business Server объединенных коммуникаций (UC) функциональные возможности не требуется. После миграции в развертывании Скайп for Business Server 2019, необходимо выполнить миграцию контактных объектов, связанных с устаревших телефона общего пользования. С помощью Скайп для консоли Business Server будет сначала извлечь все контактные объекты, связанные с устаревших телефонов общего пользования и затем перетащить эти объекты в Скайп для пула Business Server 2019.
ms.openlocfilehash: 6d5adebd4ab1b4cb79d79f4049c7d7456bb07a29
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/24/2018
ms.locfileid: "25028028"
---
# <a name="migrate-common-area-phones"></a><span data-ttu-id="393b4-106">Миграция телефонов общего пользования</span><span class="sxs-lookup"><span data-stu-id="393b4-106">Migrate Common Area Phones</span></span>

<span data-ttu-id="393b4-107">Региональные телефоны обладают IP-телефоны, что наиболее часто находятся в общей рабочей области или общего доступа как основной, кухни или фабрики этажа.</span><span class="sxs-lookup"><span data-stu-id="393b4-107">Common Area Phones are IP phones that most often reside in a shared workspace or common area, like a lobby, kitchen, or factory floor.</span></span> <span data-ttu-id="393b4-108">Региональные телефоны, подключенной к компьютеру, чтобы обеспечить Скайп для Business Server объединенных коммуникаций (UC) функциональные возможности не требуется.</span><span class="sxs-lookup"><span data-stu-id="393b4-108">Common Area Phones do not need to be connected to a computer to provide Skype for Business Server unified communications (UC) functionality.</span></span> <span data-ttu-id="393b4-109">После миграции в развертывании Скайп for Business Server 2019, необходимо выполнить миграцию контактных объектов, связанных с устаревших телефона общего пользования.</span><span class="sxs-lookup"><span data-stu-id="393b4-109">After migrating a deployment to Skype for Business Server 2019, you must also migrate the contact objects associated with the legacy Common Area Phone.</span></span> <span data-ttu-id="393b4-110">Использование Скайп для консоли Business Server, будет сначала извлечь все контактные объекты, связанные с устаревших телефонов общего пользования и затем перетащить эти объекты в Скайп для пула Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="393b4-110">Using Skype for Business Server Management Shell, you will first retrieve all contact objects associated with the legacy Common Area Phones, and then move those objects to the Skype for Business Server 2019 pool.</span></span>
  
### <a name="migrate-common-area-phones"></a><span data-ttu-id="393b4-111">Миграция телефонов общего пользования</span><span class="sxs-lookup"><span data-stu-id="393b4-111">Migrate Common Area Phones</span></span>

1. <span data-ttu-id="393b4-112">Скайп для сервера переднего плана Business Server 2019 откройте Скайп для консоли Business Server.</span><span class="sxs-lookup"><span data-stu-id="393b4-112">From the Skype for Business Server 2019 Front End server, open Skype for Business Server Management Shell.</span></span>
    
2. <span data-ttu-id="393b4-113">В командной строке введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="393b4-113">From the command line, type the following:</span></span>
    
  ```
  Get-CsCommonAreaPhone -Filter {RegistrarPool -eq "pool01.contoso.net"} | Move-CsCommonAreaPhone -Target pool02.contoso.net
  ```

3. <span data-ttu-id="393b4-114">Чтобы убедиться в том, что все контактные объекты были перемещены в Скайп для пула Business Server 2019, в Скайп для консоли Business Server введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="393b4-114">To verify that all contact objects have been moved to the Skype for Business Server 2019 pool, from the Skype for Business Server Management Shell type the following:</span></span>
    
  ```
  Get-CsCommonAreaPhone -Filter {RegistrarPool -eq "pool02.contoso.net"}
  ```

    <span data-ttu-id="393b4-115">Убедитесь, что все контактные объекты теперь связанных с Скайп для пула Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="393b4-115">Verify that all contact objects are now associated with the Skype for Business Server 2019 pool.</span></span>
    

