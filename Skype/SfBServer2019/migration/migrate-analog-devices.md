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
description: Skype для бизнеса Server поддерживает аналоговые устройства. В частности, к поддерживаемым аналоговым устройствам относятся аналоговые телефоны и факсимильные аппараты. Вы можете настроить квалифицированные шлюзы для поддержки использования аналоговых устройств в среде Skype для бизнеса Server. После перехода на Skype для бизнеса Server 2019 необходимо также перенести объекты контактов, связанные с аналоговыми устройствами. Используйте Skype для бизнеса Server Management Shell, чтобы сначала получить все объекты контактов, связанные с устаревшими аналоговыми устройствами, а затем переместить эти объекты в пул Skype для бизнеса Server 2019.
ms.openlocfilehash: 7b90a52486725c2cf30856dc643660d569d698e2
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752831"
---
# <a name="migrate-analog-devices"></a><span data-ttu-id="7ff68-107">Перенос аналоговых устройств</span><span class="sxs-lookup"><span data-stu-id="7ff68-107">Migrate analog devices</span></span>

<span data-ttu-id="7ff68-108">Skype для бизнеса Server поддерживает аналоговые устройства.</span><span class="sxs-lookup"><span data-stu-id="7ff68-108">Skype for Business Server provides support for analog devices.</span></span> <span data-ttu-id="7ff68-109">В частности, к поддерживаемым аналоговым устройствам относятся аналоговые телефоны и факсимильные аппараты.</span><span class="sxs-lookup"><span data-stu-id="7ff68-109">Specifically, the supported analog devices are analog audio phones and analog fax machines.</span></span> <span data-ttu-id="7ff68-110">Вы можете настроить квалифицированные шлюзы для поддержки использования аналоговых устройств в среде Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="7ff68-110">You can configure the qualified gateways to support the use of analog devices in your Skype for Business Server environment.</span></span> <span data-ttu-id="7ff68-111">После перехода на Skype для бизнеса Server 2019 необходимо также перенести объекты контактов, связанные с аналоговыми устройствами.</span><span class="sxs-lookup"><span data-stu-id="7ff68-111">After you migrate to Skype for Business Server 2019, you must also migrate the contact objects associated with the analog devices.</span></span> <span data-ttu-id="7ff68-112">Используйте Skype для бизнеса Server Management Shell, чтобы сначала получить все объекты контактов, связанные с устаревшими аналоговыми устройствами, а затем переместить эти объекты в пул Skype для бизнеса Server 2019.</span><span class="sxs-lookup"><span data-stu-id="7ff68-112">Use Skype for Business Server Management Shell to first retrieve all contact objects associated with the legacy analog devices, and then move those objects to the Skype for Business Server 2019 pool.</span></span>

### <a name="to-migrate-analog-devices"></a><span data-ttu-id="7ff68-113">Перенос аналоговых устройств</span><span class="sxs-lookup"><span data-stu-id="7ff68-113">To migrate analog devices</span></span>

1. <span data-ttu-id="7ff68-114">Запустите оболочку управления Skype для бизнеса Server: нажмите кнопку "Начните", выберите "Все программы", "Microsoft Skype для бизнеса Server **2019"** и щелкните "Skype для бизнеса Server Management **Shell".**</span><span class="sxs-lookup"><span data-stu-id="7ff68-114">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Skype for Business Server 2019**, and then click **Skype for Business Server Management Shell**.</span></span>

2. <span data-ttu-id="7ff68-115">В командной строке введите следующую команду.</span><span class="sxs-lookup"><span data-stu-id="7ff68-115">At the command line, type:</span></span>

   ```PowerShell
   Get-CsAnalogDevice -Filter {RegistrarPool -eq "pool01.contoso.net"} | Move-CsAnalogDevice -Target pool02.contoso.net
   ```

3. <span data-ttu-id="7ff68-116">Убедитесь, что все контактные объекты перемещены в пул Skype для бизнеса Server 2019.</span><span class="sxs-lookup"><span data-stu-id="7ff68-116">Verify that all contact objects have been moved to the Skype for Business Server 2019 pool.</span></span> <span data-ttu-id="7ff68-117">В командной строке введите следующую команду.</span><span class="sxs-lookup"><span data-stu-id="7ff68-117">At the command line, type:</span></span>

   ```PowerShell
   Get-CsAnalogDevice -Filter {RegistrarPool -eq "pool02.contoso.net"}
   ```

4. <span data-ttu-id="7ff68-118">Убедитесь, что все контактные объекты теперь связаны с пулом Skype для бизнеса Server 2019.</span><span class="sxs-lookup"><span data-stu-id="7ff68-118">Verify that all the contact objects are now associated with the Skype for Business Server 2019 pool.</span></span>


