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
# <a name="migrate-analog-devices"></a><span data-ttu-id="a27c5-107">Перенос аналоговых устройств</span><span class="sxs-lookup"><span data-stu-id="a27c5-107">Migrate analog devices</span></span>

<span data-ttu-id="a27c5-108">Skype для бизнеса Server обеспечивает поддержку аналоговых устройств.</span><span class="sxs-lookup"><span data-stu-id="a27c5-108">Skype for Business Server provides support for analog devices.</span></span> <span data-ttu-id="a27c5-109">В частности, к поддерживаемым аналоговым устройствам относятся аналоговые телефоны и факсимильные аппараты.</span><span class="sxs-lookup"><span data-stu-id="a27c5-109">Specifically, the supported analog devices are analog audio phones and analog fax machines.</span></span> <span data-ttu-id="a27c5-110">Можно настроить квалифицированные шлюзы для поддержки использования аналоговых устройств в среде Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="a27c5-110">You can configure the qualified gateways to support the use of analog devices in your Skype for Business Server environment.</span></span> <span data-ttu-id="a27c5-111">После перехода на Skype для бизнеса Server 2019 необходимо также перенести объекты Contact, связанные с аналоговыми устройствами.</span><span class="sxs-lookup"><span data-stu-id="a27c5-111">After you migrate to Skype for Business Server 2019, you must also migrate the contact objects associated with the analog devices.</span></span> <span data-ttu-id="a27c5-112">Используйте командную консоль Skype для бизнеса Server для получения всех контактных объектов, связанных с старыми аналоговыми устройствами, а затем переместите эти объекты в пул Skype для бизнеса Server 2019.</span><span class="sxs-lookup"><span data-stu-id="a27c5-112">Use Skype for Business Server Management Shell to first retrieve all contact objects associated with the legacy analog devices, and then move those objects to the Skype for Business Server 2019 pool.</span></span>

### <a name="to-migrate-analog-devices"></a><span data-ttu-id="a27c5-113">Перенос аналоговых устройств</span><span class="sxs-lookup"><span data-stu-id="a27c5-113">To migrate analog devices</span></span>

1. <span data-ttu-id="a27c5-114">Запустите командную консоль Skype для бизнеса Server: нажмите кнопку **Пуск**, выберите **все программы**, затем **Microsoft Skype для бизнеса Server 2019**и щелкните **Командная консоль Skype для бизнеса Server**.</span><span class="sxs-lookup"><span data-stu-id="a27c5-114">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Skype for Business Server 2019**, and then click **Skype for Business Server Management Shell**.</span></span>

2. <span data-ttu-id="a27c5-115">В командной строке введите следующую команду.</span><span class="sxs-lookup"><span data-stu-id="a27c5-115">At the command line, type:</span></span>

   ```PowerShell
   Get-CsAnalogDevice -Filter {RegistrarPool -eq "pool01.contoso.net"} | Move-CsAnalogDevice -Target pool02.contoso.net
   ```

3. <span data-ttu-id="a27c5-116">Убедитесь, что все объекты Contacts были перемещены в пул Skype для бизнеса Server 2019.</span><span class="sxs-lookup"><span data-stu-id="a27c5-116">Verify that all contact objects have been moved to the Skype for Business Server 2019 pool.</span></span> <span data-ttu-id="a27c5-117">В командной строке введите следующую команду.</span><span class="sxs-lookup"><span data-stu-id="a27c5-117">At the command line, type:</span></span>

   ```PowerShell
   Get-CsAnalogDevice -Filter {RegistrarPool -eq "pool02.contoso.net"}
   ```

4. <span data-ttu-id="a27c5-118">Убедитесь, что все объекты Contact теперь связаны с пулом Skype для бизнеса Server 2019.</span><span class="sxs-lookup"><span data-stu-id="a27c5-118">Verify that all the contact objects are now associated with the Skype for Business Server 2019 pool.</span></span>


