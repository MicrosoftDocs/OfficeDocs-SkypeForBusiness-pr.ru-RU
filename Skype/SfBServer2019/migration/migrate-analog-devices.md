---
title: Перенос аналоговых устройств
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
description: Skype для бизнеса Server обеспечивает поддержку аналоговых устройств. В частности, поддерживаются аналоговые устройства аналогового и аналогового факсимильного аппарата. Вы можете настроить полные шлюзы для поддержки использования аналоговых устройств в среде Skype для бизнеса Server. После перехода на Skype для бизнеса Server 2019 необходимо также перенести объекты контактов, связанные с аналоговыми устройствами. С помощью командной консоли Skype для бизнеса Server вы можете сначала получить все объекты контактов, связанные с аналоговыми устройствами, а затем переместить эти объекты в пул Skype для бизнеса Server 2019.
ms.openlocfilehash: b3b3cc1ebafa468a43043b202a01957c1cc06e87
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41813597"
---
# <a name="migrate-analog-devices"></a><span data-ttu-id="a2704-107">Перенос аналоговых устройств</span><span class="sxs-lookup"><span data-stu-id="a2704-107">Migrate analog devices</span></span>

<span data-ttu-id="a2704-108">Skype для бизнеса Server обеспечивает поддержку аналоговых устройств.</span><span class="sxs-lookup"><span data-stu-id="a2704-108">Skype for Business Server provides support for analog devices.</span></span> <span data-ttu-id="a2704-109">В частности, поддерживаются аналоговые устройства аналогового и аналогового факсимильного аппарата.</span><span class="sxs-lookup"><span data-stu-id="a2704-109">Specifically, the supported analog devices are analog audio phones and analog fax machines.</span></span> <span data-ttu-id="a2704-110">Вы можете настроить полные шлюзы для поддержки использования аналоговых устройств в среде Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="a2704-110">You can configure the qualified gateways to support the use of analog devices in your Skype for Business Server environment.</span></span> <span data-ttu-id="a2704-111">После перехода на Skype для бизнеса Server 2019 необходимо также перенести объекты контактов, связанные с аналоговыми устройствами.</span><span class="sxs-lookup"><span data-stu-id="a2704-111">After you migrate to Skype for Business Server 2019, you must also migrate the contact objects associated with the analog devices.</span></span> <span data-ttu-id="a2704-112">С помощью командной консоли Skype для бизнеса Server вы можете сначала получить все объекты контактов, связанные с аналоговыми устройствами, а затем переместить эти объекты в пул Skype для бизнеса Server 2019.</span><span class="sxs-lookup"><span data-stu-id="a2704-112">Use Skype for Business Server Management Shell to first retrieve all contact objects associated with the legacy analog devices, and then move those objects to the Skype for Business Server 2019 pool.</span></span>

### <a name="to-migrate-analog-devices"></a><span data-ttu-id="a2704-113">Миграция аналоговых устройств</span><span class="sxs-lookup"><span data-stu-id="a2704-113">To migrate analog devices</span></span>

1. <span data-ttu-id="a2704-114">Запустите консоль управления в Skype для бизнеса Server: нажмите кнопку **Пуск**, выберите пункт **все программы**, а затем — **Microsoft Skype для бизнеса Server 2019**, а затем — **Командная консоль управления Skype для бизнеса Server**.</span><span class="sxs-lookup"><span data-stu-id="a2704-114">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Skype for Business Server 2019**, and then click **Skype for Business Server Management Shell**.</span></span>

2. <span data-ttu-id="a2704-115">В командной строке выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="a2704-115">At the command line, type:</span></span>

   ```PowerShell
   Get-CsAnalogDevice -Filter {RegistrarPool -eq "pool01.contoso.net"} | Move-CsAnalogDevice -Target pool02.contoso.net
   ```

3. <span data-ttu-id="a2704-116">Убедитесь, что все объекты контакта были перемещены в пул 2019 в Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="a2704-116">Verify that all contact objects have been moved to the Skype for Business Server 2019 pool.</span></span> <span data-ttu-id="a2704-117">В командной строке выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="a2704-117">At the command line, type:</span></span>

   ```PowerShell
   Get-CsAnalogDevice -Filter {RegistrarPool -eq "pool02.contoso.net"}
   ```

4. <span data-ttu-id="a2704-118">Убедитесь, что все объекты контакта теперь связаны с пулом 2019 в Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="a2704-118">Verify that all the contact objects are now associated with the Skype for Business Server 2019 pool.</span></span>


