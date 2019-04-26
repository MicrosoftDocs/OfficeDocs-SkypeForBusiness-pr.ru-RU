---
title: Перенос аналоговых устройств
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Скайп для Business Server обеспечивает поддержку аналоговых устройств. В частности поддерживаемые аналоговых устройств, аналоговые звука телефонов и аналоговых факсов. Вы можете настроить квалифицированного шлюзов для поддержки использования аналоговых устройств в вашей Скайп среды Business Server. После миграции Скайп для Business Server 2019, также необходимо перенести контактных объектов, связанных с аналоговых устройств. Используйте Скайп для консоли Business Server для первой загрузки все контактные объекты, связанные с устаревших аналоговых устройств и затем перетащить эти объекты в Скайп для пула Business Server 2019.
ms.openlocfilehash: 80edf5b806ffd192d125bd5da27207a37f3074d1
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "32238392"
---
# <a name="migrate-analog-devices"></a><span data-ttu-id="c1bc0-107">Перенос аналоговых устройств</span><span class="sxs-lookup"><span data-stu-id="c1bc0-107">Migrate analog devices</span></span>

<span data-ttu-id="c1bc0-108">Скайп для Business Server обеспечивает поддержку аналоговых устройств.</span><span class="sxs-lookup"><span data-stu-id="c1bc0-108">Skype for Business Server provides support for analog devices.</span></span> <span data-ttu-id="c1bc0-109">В частности поддерживаемые аналоговых устройств, аналоговые звука телефонов и аналоговых факсов.</span><span class="sxs-lookup"><span data-stu-id="c1bc0-109">Specifically, the supported analog devices are analog audio phones and analog fax machines.</span></span> <span data-ttu-id="c1bc0-110">Вы можете настроить квалифицированного шлюзов для поддержки использования аналоговых устройств в вашей Скайп среды Business Server.</span><span class="sxs-lookup"><span data-stu-id="c1bc0-110">You can configure the qualified gateways to support the use of analog devices in your Skype for Business Server environment.</span></span> <span data-ttu-id="c1bc0-111">После миграции Скайп для Business Server 2019, также необходимо перенести контактных объектов, связанных с аналоговых устройств.</span><span class="sxs-lookup"><span data-stu-id="c1bc0-111">After you migrate to Skype for Business Server 2019, you must also migrate the contact objects associated with the analog devices.</span></span> <span data-ttu-id="c1bc0-112">Используйте Скайп для консоли Business Server для первой загрузки все контактные объекты, связанные с устаревших аналоговых устройств и затем перетащить эти объекты в Скайп для пула Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="c1bc0-112">Use Skype for Business Server Management Shell to first retrieve all contact objects associated with the legacy analog devices, and then move those objects to the Skype for Business Server 2019 pool.</span></span>

### <a name="to-migrate-analog-devices"></a><span data-ttu-id="c1bc0-113">Перенос аналоговых устройств</span><span class="sxs-lookup"><span data-stu-id="c1bc0-113">To migrate analog devices</span></span>

1. <span data-ttu-id="c1bc0-114">Запустите Скайп для консоли Business Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы**, щелкните **Скайп Microsoft для Business Server 2019**и нажмите кнопку **Скайп для консоли Business Server**.</span><span class="sxs-lookup"><span data-stu-id="c1bc0-114">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Skype for Business Server 2019**, and then click **Skype for Business Server Management Shell**.</span></span>

2. <span data-ttu-id="c1bc0-115">В командной строке выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="c1bc0-115">At the command line, type:</span></span>

   ```
   Get-CsAnalogDevice -Filter {RegistrarPool -eq "pool01.contoso.net"} | Move-CsAnalogDevice -Target pool02.contoso.net
   ```

3. <span data-ttu-id="c1bc0-116">Убедитесь в том, что все контактные объекты были перемещены в Скайп для пула Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="c1bc0-116">Verify that all contact objects have been moved to the Skype for Business Server 2019 pool.</span></span> <span data-ttu-id="c1bc0-117">В командной строке выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="c1bc0-117">At the command line, type:</span></span>

   ```
   Get-CsAnalogDevice -Filter {RegistrarPool -eq "pool02.contoso.net"}
   ```

4. <span data-ttu-id="c1bc0-118">Убедитесь, что все контактные объекты теперь связанных с Скайп для пула Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="c1bc0-118">Verify that all the contact objects are now associated with the Skype for Business Server 2019 pool.</span></span>


