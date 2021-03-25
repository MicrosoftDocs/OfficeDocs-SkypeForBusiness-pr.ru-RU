---
title: Перенос устройств Lync Room System в комнаты Microsoft Teams
ms.author: dstrome
author: dstrome
ms.reviewer: sohailta
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.service: msteams
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
ms.assetid: ''
description: Из этой темы вы узнаете, как перенести устройства Lync Room System для использования программного обеспечения комнат Microsoft Teams.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 7e850b5f5f0f210abf7defc2e53cc510c5c0b0c2
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117527"
---
# <a name="migrate-lync-room-system-lrs-devices-to-microsoft-teams-rooms"></a><span data-ttu-id="5d365-103">Перенос устройств Lync Room System (LRS) в комнаты Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="5d365-103">Migrate Lync Room System (LRS) devices to Microsoft Teams Rooms</span></span>

<span data-ttu-id="5d365-104">Поддержка устройств Lync Room System (LRS) с программным обеспечением Skype Room System версии 1 (SRS версии 1) заканчивается 9 октября [2018 г.](https://support.microsoft.com/help/4043450/products-reaching-end-of-support-for-2018)</span><span class="sxs-lookup"><span data-stu-id="5d365-104">Lync Room System (LRS) devices with Skype Room System Version 1 (SRS v1) software has reached [end of support on October 9, 2018](https://support.microsoft.com/help/4043450/products-reaching-end-of-support-for-2018).</span></span> <span data-ttu-id="5d365-105">Это означает, что для приложения "Системы комнат Skype" версии 1 больше не будут выпускаться обновления и исправления.</span><span class="sxs-lookup"><span data-stu-id="5d365-105">This means Skype Room Systems v1 software will no longer get any product updates or fixes anymore.</span></span> <span data-ttu-id="5d365-106">Пользователям устройств системы комнат Lync, использующие приложение "Системы комнат Skype" версии 1, рекомендуем установить на своих устройствах приложение "Комнаты Microsoft Teams".</span><span class="sxs-lookup"><span data-stu-id="5d365-106">Customers with Lync Room System devices using Skype Room System v1 software are advised to upgrade their devices to Microsoft Teams Rooms.</span></span>

<span data-ttu-id="5d365-107">Программное обеспечение комнат Microsoft Teams работает с Microsoft Teams в дополнение к службам Skype для бизнеса Server и Online для собраний и звонков на всех поддерживаемых устройствах комнат Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="5d365-107">Microsoft Teams Rooms software works with Microsoft Teams in addition to Skype for Business Server and Online services for meetings and calling on all Microsoft Teams Rooms supported devices.</span></span>

<span data-ttu-id="5d365-108">Существующие устройства **могут продолжать** работать после окончания поддержки программного обеспечения Skype Room System 1.</span><span class="sxs-lookup"><span data-stu-id="5d365-108">Your existing devices **may** continue to work after the end of Skype Room System v1 software support.</span></span> <span data-ttu-id="5d365-109">Однако если данное программное обеспечение устраняет ошибку, из-за ошибки в программном обеспечении, из-за которую корпорация Майкрософт должна выпустить исправление, оно не будет поддерживаться.</span><span class="sxs-lookup"><span data-stu-id="5d365-109">However, if this software hits a software bug that needs Microsoft to release a fix, it will not be supported.</span></span> <span data-ttu-id="5d365-110">SRS v1 использует TLS 1.0/1.1, который в будущем будет неподготовлен корпорацией Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="5d365-110">SRS v1 uses TLS 1.0/ 1.1 which will be deprecated by Microsoft in the future.</span></span> <span data-ttu-id="5d365-111">Подробнее о подготовке к [деpreprecation для TLS 1.0/1.1.](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Preparing-for-TLS-1-0-1-1-Deprecation-O365-Skype-for-Business/bc-p/223608)</span><span class="sxs-lookup"><span data-stu-id="5d365-111">You can learn more about [preparing for TLS 1.0/1.1 deprecation](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Preparing-for-TLS-1-0-1-1-Deprecation-O365-Skype-for-Business/bc-p/223608).</span></span> 

## <a name="which-devices-are-affected"></a><span data-ttu-id="5d365-112">Какие устройства затронуты?</span><span class="sxs-lookup"><span data-stu-id="5d365-112">Which devices are affected?</span></span>

<span data-ttu-id="5d365-113">Вот список устройств, на которые влияет это изменение:</span><span class="sxs-lookup"><span data-stu-id="5d365-113">Here is the list of the devices that are affected by this change:</span></span>

- <span data-ttu-id="5d365-114">Ronron RL</span><span class="sxs-lookup"><span data-stu-id="5d365-114">Crestron RL</span></span>
- [<span data-ttu-id="5d365-115">12(12)</span><span class="sxs-lookup"><span data-stu-id="5d365-115">Crestron RL2</span></span>](https://www.crestron.com/Products/Featured-Solutions/Crestron-RL-2)
- [<span data-ttu-id="5d365-116">Системы комнат SMART Room</span><span class="sxs-lookup"><span data-stu-id="5d365-116">SMART Room systems</span></span>](https://support.smarttech.com/en/hardware/room-systems-skype)
- [<span data-ttu-id="5d365-117">Polycom CX8000</span><span class="sxs-lookup"><span data-stu-id="5d365-117">Polycom CX8000</span></span>](https://www.polycom.com/products-services/products-for-microsoft/skype-for-business/cx8000.html)

## <a name="upgrade-options"></a><span data-ttu-id="5d365-118">Варианты обновления</span><span class="sxs-lookup"><span data-stu-id="5d365-118">Upgrade options</span></span>

<span data-ttu-id="5d365-119">Существует несколько вариантов обновления систем комнат Lync до нового поколения комнат Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="5d365-119">There are multiple options for upgrading Lync Room Systems to the next generation of Microsoft Teams Rooms.</span></span>

### <a name="crestron-hardware-trade-in-program"></a><span data-ttu-id="5d365-120">Программа trade-in для аппаратного оборудования</span><span class="sxs-lookup"><span data-stu-id="5d365-120">Crestron hardware Trade-in program</span></span>

<span data-ttu-id="5d365-121">Ролан обновит [](https://www.crestron.com/products/featured-solutions/crestron-sr) систему Сротрона (или эквивалент) для всех клиентов, не взгляхив в Lync Room System (например, Smart или Polycom LRS).</span><span class="sxs-lookup"><span data-stu-id="5d365-121">Crestron will provide an upgrade to the [Crestron SR system](https://www.crestron.com/products/featured-solutions/crestron-sr) or equivalent for all Non-Crestron Lync Room System customers (e.g Smart or Polycom LRS).</span></span> <span data-ttu-id="5d365-122">Подробные сведения об этой программе см. [здесь или](https://support.crestron.com/app/answers/answer_view/a_id/1000220)</span><span class="sxs-lookup"><span data-stu-id="5d365-122">See details of this program [here](https://support.crestron.com/app/answers/answer_view/a_id/1000220) or</span></span> <!-- For details, --><span data-ttu-id="5d365-123">[электронная почта](mailto:lrsupgrade@crestron.com) Поддержка Скайпа LRS.</span><span class="sxs-lookup"><span data-stu-id="5d365-123">[email](mailto:lrsupgrade@crestron.com) Crestron LRS support.</span></span>  

### <a name="crestron-rl2-upgrade-to-microsoft-teams-rooms"></a><span data-ttu-id="5d365-124">Обновление Скайпа RL2 до комнат Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="5d365-124">Crestron RL2 upgrade to Microsoft Teams Rooms</span></span>

<span data-ttu-id="5d365-125">Существующие клиенты с использованием RL2 (Это также называется "Сротрон RL200") могут приобрести комплект обновления для обновления текущего набора RL2 до RL3 с минимальными затратами на устройство.</span><span class="sxs-lookup"><span data-stu-id="5d365-125">Existing Crestron RL2 (also referred to as Crestron RL200) customers can acquire an upgrade kit to upgrade current RL2 to RL3 using a for a minimal cost per device.</span></span> <span data-ttu-id="5d365-126">Подробные сведения об этой программе см. [здесь.](https://crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-RL-2/CCS-UC-250-KIT)</span><span class="sxs-lookup"><span data-stu-id="5d365-126">See details of this program [here](https://crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-RL-2/CCS-UC-250-KIT).</span></span>

### <a name="smart-room-systems-upgrade"></a><span data-ttu-id="5d365-127">Обновление системы smart Room Systems</span><span class="sxs-lookup"><span data-stu-id="5d365-127">SMART Room Systems upgrade</span></span>

<span data-ttu-id="5d365-128">Для клиентов, работающих с смарт-LRS, помимо программы товарооборота с оборудованием Висяка, SMART также работает над предоставлением решения для обновления до комнат Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="5d365-128">For SMART LRS customers, apart from Crestron hardware trade-in program, SMART is also working on providing a solution to upgrade to Microsoft Teams Rooms.</span></span> <span data-ttu-id="5d365-129">Это обновление будет предоставляться технологией SMART Technologies Inc. для клиентов в рамках поддержки продуктов.</span><span class="sxs-lookup"><span data-stu-id="5d365-129">This upgrade will be provided by SMART Technologies Inc. to customer under product support.</span></span> <span data-ttu-id="5d365-130">Подробнее об этом см. [здесь.](https://support.smarttech.com/docs/hardware/room-systems-skype/srs-skype-v2/en/about/default.cshtml)</span><span class="sxs-lookup"><span data-stu-id="5d365-130">Please see more about this [here](https://support.smarttech.com/docs/hardware/room-systems-skype/srs-skype-v2/en/about/default.cshtml).</span></span>


## <a name="what-should-you-do"></a><span data-ttu-id="5d365-131">Что вам делать?</span><span class="sxs-lookup"><span data-stu-id="5d365-131">What should you do?</span></span>

<span data-ttu-id="5d365-132">Мы рекомендуем обновить устройства Lync Room System до комнат Microsoft Teams до отзыва TLS 1.0/1.1 с помощью указанных выше параметров обновления.</span><span class="sxs-lookup"><span data-stu-id="5d365-132">We recommend you plan to update Lync Room System devices to Microsoft Teams Rooms before TLS 1.0/1.1 deprecation using upgrade options mentioned above.</span></span> <span data-ttu-id="5d365-133">Кроме того, можно заменить существующие устройства новыми устройствами, сертифицированными для комнат Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="5d365-133">Additionally, you may also consider replacing existing devices with new devices certified for Microsoft Teams Rooms.</span></span> <span data-ttu-id="5d365-134">Подробные [сведения см.](https://aka.ms/roomdevices) в сведениях о устройствах комнат, а также требованиях к комнатам [Microsoft Teams.](/skypeforbusiness/plan-your-deployment/clients-and-devices/requirements)</span><span class="sxs-lookup"><span data-stu-id="5d365-134">See [Room devices](https://aka.ms/roomdevices) for details and also take a look at [Microsoft Teams Rooms requirements](/skypeforbusiness/plan-your-deployment/clients-and-devices/requirements).</span></span>  


> [!NOTE]
> <span data-ttu-id="5d365-135">Программное обеспечение комнат Microsoft Teams поддерживает протокол TLS 1.2 с 14 декабря 2018 г. с версией приложения 4.0.64.0.</span><span class="sxs-lookup"><span data-stu-id="5d365-135">Microsoft Teams Rooms software supports the TLS 1.2 protocol as of December 14, 2018 with app version 4.0.64.0.</span></span> <span data-ttu-id="5d365-136">Для локального клиента для включения связи через TLS 1.2 для комнат Microsoft Teams требуется Skype для бизнеса Server 2015 с накопительным обновлением 9 (НАКОПИТЕЛЬ) или Skype для бизнеса Server 2019 с накопительным обновлением 1 (НАКОПИТЕЛЬ1).</span><span class="sxs-lookup"><span data-stu-id="5d365-136">For on-premises customers, enabling communication over TLS 1.2 for Microsoft Teams Rooms requires Skype for Business Server 2015 Cumulative Update 9 (CU9) or Skype for Business Server 2019 Cumulative Update 1 (CU1).</span></span> <span data-ttu-id="5d365-137">Это изменение не должно повлиять на клиентов Skype для бизнеса Online, так как они соответствуют требованиям клиентов вперед и назад.</span><span class="sxs-lookup"><span data-stu-id="5d365-137">The change should not affect Skype for Business Online customers as client changes are forward and backward compliant.</span></span>