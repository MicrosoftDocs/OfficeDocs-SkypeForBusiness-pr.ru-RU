---
title: Миграция системных устройств Lync в комнаты Microsoft Teams
ms.author: v-lanac
author: lanachin
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
description: В этой статье рассказывается о том, как переносить системные устройства комнат Lync для использования программного обеспечения Microsoft Teams.
ms.openlocfilehash: 4f0c255c40c64274ff4b104a8706eb8f73ee792f
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42155111"
---
# <a name="migrate-lync-room-system-lrs-devices-to-microsoft-teams-rooms"></a><span data-ttu-id="f2356-103">Миграция устройств из системы комнаты Lync (ЛРС) в комнаты Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="f2356-103">Migrate Lync Room System (LRS) devices to Microsoft Teams Rooms</span></span>

<span data-ttu-id="f2356-104">Система управления комнатой Lync (ЛРС) с помощью программного обеспечения системы комнат Skype версии 1 (SRS v1) закончила [поддержку до 9 октября 2018 г](https://support.microsoft.com/help/4043450/products-reaching-end-of-support-for-2018).</span><span class="sxs-lookup"><span data-stu-id="f2356-104">Lync Room System (LRS) devices with Skype Room System Version 1 (SRS v1) software has reached [end of support on October 9, 2018](https://support.microsoft.com/help/4043450/products-reaching-end-of-support-for-2018).</span></span> <span data-ttu-id="f2356-105">Это означает, что для приложения "Системы комнат Skype" версии 1 больше не будут выпускаться обновления и исправления.</span><span class="sxs-lookup"><span data-stu-id="f2356-105">This means Skype Room Systems v1 software will no longer get any product updates or fixes anymore.</span></span> <span data-ttu-id="f2356-106">Пользователям устройств системы комнат Lync, использующие приложение "Системы комнат Skype" версии 1, рекомендуем установить на своих устройствах приложение "Комнаты Microsoft Teams".</span><span class="sxs-lookup"><span data-stu-id="f2356-106">Customers with Lync Room System devices using Skype Room System v1 software are advised to upgrade their devices to Microsoft Teams Rooms.</span></span>

<span data-ttu-id="f2356-107">Программы Microsoft Teams работают с Microsoft Teams в дополнение к Skype для бизнеса Server и Интернет-службам для собраний и звонков по всем поддерживаемым устройствам Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="f2356-107">Microsoft Teams Rooms software works with Microsoft Teams in addition to Skype for Business Server and Online services for meetings and calling on all Microsoft Teams Rooms supported devices.</span></span>

<span data-ttu-id="f2356-108">Существующие **устройства** продолжают работать после завершения поддержки программного обеспечения для системы комнат Skype v1.</span><span class="sxs-lookup"><span data-stu-id="f2356-108">Your existing devices **may** continue to work after the end of Skype Room System v1 software support.</span></span> <span data-ttu-id="f2356-109">Тем не менее, если это программное обеспечение обнаружено в программной ошибке, требующей от корпорации Майкрософт устранения исправлений, она не будет поддерживаться.</span><span class="sxs-lookup"><span data-stu-id="f2356-109">However, if this software hits a software bug that needs Microsoft to release a fix, it will not be supported.</span></span> <span data-ttu-id="f2356-110">SRS v1 использует TLS 1.0/1,1, который будет использоваться корпорацией Майкрософт в будущем.</span><span class="sxs-lookup"><span data-stu-id="f2356-110">SRS v1 uses TLS 1.0/ 1.1 which will be deprecated by Microsoft in the future.</span></span> <span data-ttu-id="f2356-111">Вы можете узнать больше о том, как [подготовиться к использованию протокола TLS 1.0/1.1](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Preparing-for-TLS-1-0-1-1-Deprecation-O365-Skype-for-Business/bc-p/223608).</span><span class="sxs-lookup"><span data-stu-id="f2356-111">You can learn more about [preparing for TLS 1.0/1.1 deprecation](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Preparing-for-TLS-1-0-1-1-Deprecation-O365-Skype-for-Business/bc-p/223608).</span></span> 

## <a name="which-devices-are-affected"></a><span data-ttu-id="f2356-112">Какие устройства затронуты?</span><span class="sxs-lookup"><span data-stu-id="f2356-112">Which devices are affected?</span></span>

<span data-ttu-id="f2356-113">Ниже приведен список устройств, на которые влияет это изменение:</span><span class="sxs-lookup"><span data-stu-id="f2356-113">Here is the list of the devices that are affected by this change:</span></span>

- <span data-ttu-id="f2356-114">Крестрон РЛ</span><span class="sxs-lookup"><span data-stu-id="f2356-114">Crestron RL</span></span>
- [<span data-ttu-id="f2356-115">Крестрон RL2</span><span class="sxs-lookup"><span data-stu-id="f2356-115">Crestron RL2</span></span>](https://www.crestron.com/Products/Featured-Solutions/Crestron-RL-2)
- [<span data-ttu-id="f2356-116">Системы SMART rooming</span><span class="sxs-lookup"><span data-stu-id="f2356-116">SMART Room systems</span></span>](https://support.smarttech.com/en/hardware/room-systems-skype)
- [<span data-ttu-id="f2356-117">Polycom CX8000</span><span class="sxs-lookup"><span data-stu-id="f2356-117">Polycom CX8000</span></span>](https://www.polycom.com/products-services/products-for-microsoft/skype-for-business/cx8000.html)

## <a name="upgrade-options"></a><span data-ttu-id="f2356-118">Варианты обновления</span><span class="sxs-lookup"><span data-stu-id="f2356-118">Upgrade options</span></span>

<span data-ttu-id="f2356-119">Существует несколько вариантов обновления систем комнат Lync до нового поколения комнат Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="f2356-119">There are multiple options for upgrading Lync Room Systems to the next generation of Microsoft Teams Rooms.</span></span>

### <a name="crestron-hardware-trade-in-program"></a><span data-ttu-id="f2356-120">Программа крестрон оборудования</span><span class="sxs-lookup"><span data-stu-id="f2356-120">Crestron hardware Trade-in program</span></span>

<span data-ttu-id="f2356-121">Крестрон предоставит обновление [системы КРЕСТРОН SR](https://www.crestron.com/products/featured-solutions/crestron-sr) или эквивалент для всех пользователей системы, не являющихся крестрон, например Smart или Polycom ЛРС.</span><span class="sxs-lookup"><span data-stu-id="f2356-121">Crestron will provide an upgrade to the [Crestron SR system](https://www.crestron.com/products/featured-solutions/crestron-sr) or equivalent for all Non-Crestron Lync Room System customers (e.g Smart or Polycom LRS).</span></span> <span data-ttu-id="f2356-122">Просмотреть подробные сведения об этой [программе или](https://support.crestron.com/app/answers/answer_view/a_id/1000220)</span><span class="sxs-lookup"><span data-stu-id="f2356-122">See details of this program [here](https://support.crestron.com/app/answers/answer_view/a_id/1000220) or</span></span> <!-- For details, --><span data-ttu-id="f2356-123">[Электронная почта](mailto:lrsupgrade@crestron.com) Поддержка крестрон ЛРС.</span><span class="sxs-lookup"><span data-stu-id="f2356-123">[email](mailto:lrsupgrade@crestron.com) Crestron LRS support.</span></span>  

### <a name="crestron-rl2-upgrade-to-microsoft-teams-rooms"></a><span data-ttu-id="f2356-124">Крестрон RL2 переход к комнатам Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="f2356-124">Crestron RL2 upgrade to Microsoft Teams Rooms</span></span>

<span data-ttu-id="f2356-125">Существующие Крестрон RL2 (также называемые Крестрон RL200) пользователи могут получить комплект обновления, чтобы обновить текущую RL2 до RL3 с минимальной стоимостью на устройство.</span><span class="sxs-lookup"><span data-stu-id="f2356-125">Existing Crestron RL2 (also referred to as Crestron RL200) customers can acquire an upgrade kit to upgrade current RL2 to RL3 using a for a minimal cost per device.</span></span> <span data-ttu-id="f2356-126">Ознакомьтесь с подробными сведениями об [этой программе.](https://crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-RL-2/CCS-UC-250-KIT)</span><span class="sxs-lookup"><span data-stu-id="f2356-126">See details of this program [here](https://crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-RL-2/CCS-UC-250-KIT).</span></span>

### <a name="smart-room-systems-upgrade"></a><span data-ttu-id="f2356-127">Обновление системы SMART Room</span><span class="sxs-lookup"><span data-stu-id="f2356-127">SMART Room Systems upgrade</span></span>

<span data-ttu-id="f2356-128">Для пользователей SMART ЛРС, отличных от Крестрон аппаратной торговли, SMART также работает над предоставлением решения для перехода на комнаты Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="f2356-128">For SMART LRS customers, apart from Crestron hardware trade-in program, SMART is also working on providing a solution to upgrade to Microsoft Teams Rooms.</span></span> <span data-ttu-id="f2356-129">Это обновление будет предоставляться ИНТЕЛЛЕКТУАЛЬНым технологиям Inc. клиентам, которые поддерживаются в рамках поддержки продуктов.</span><span class="sxs-lookup"><span data-stu-id="f2356-129">This upgrade will be provided by SMART Technologies Inc. to customer under product support.</span></span> <span data-ttu-id="f2356-130">Подробнее об этом можно узнать [здесь](https://support.smarttech.com/docs/hardware/room-systems-skype/srs-skype-v2/en/about/default.cshtml).</span><span class="sxs-lookup"><span data-stu-id="f2356-130">Please see more about this [here](https://support.smarttech.com/docs/hardware/room-systems-skype/srs-skype-v2/en/about/default.cshtml).</span></span>


## <a name="what-should-you-do"></a><span data-ttu-id="f2356-131">Что нужно сделать?</span><span class="sxs-lookup"><span data-stu-id="f2356-131">What should you do?</span></span>

<span data-ttu-id="f2356-132">Мы рекомендуем вам запланировать обновление системных устройств Lync для комнат Microsoft Teams до устаревшей версии TLS 1.0/1.1 с помощью вариантов обновления, описанных выше.</span><span class="sxs-lookup"><span data-stu-id="f2356-132">We recommend you plan to update Lync Room System devices to Microsoft Teams Rooms before TLS 1.0/1.1 deprecation using upgrade options mentioned above.</span></span> <span data-ttu-id="f2356-133">Кроме того, вы можете заменить существующие устройства новыми устройствами, сертифицированными для комнат Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="f2356-133">Additionally, you may also consider replacing existing devices with new devices certified for Microsoft Teams Rooms.</span></span> <span data-ttu-id="f2356-134">Ознакомьтесь со сведениями о [комнатах](https://aka.ms/roomdevices) , а также ознакомьтесь с [требованиями к комнатам Microsoft Teams](https://docs.microsoft.com/skypeforbusiness/plan-your-deployment/clients-and-devices/requirements).</span><span class="sxs-lookup"><span data-stu-id="f2356-134">See [Room devices](https://aka.ms/roomdevices) for details and also take a look at [Microsoft Teams Rooms requirements](https://docs.microsoft.com/skypeforbusiness/plan-your-deployment/clients-and-devices/requirements).</span></span>  


> [!NOTE]
> <span data-ttu-id="f2356-135">Программы Microsoft Teams поддерживают протокол TLS 1,2 на 14 декабря 2018 г. с версией приложения 4.0.64.0.</span><span class="sxs-lookup"><span data-stu-id="f2356-135">Microsoft Teams Rooms software supports the TLS 1.2 protocol as of December 14, 2018 with app version 4.0.64.0.</span></span> <span data-ttu-id="f2356-136">Для локальных пользователей, обеспечивающих связь по протоколу TLS 1,2 для комнат Microsoft Teams, требуется Skype для бизнеса Server 2015 (CU9) или Skype для бизнеса Server 2019 накопительный пакет обновления 1 (CU1).</span><span class="sxs-lookup"><span data-stu-id="f2356-136">For on-premises customers, enabling communication over TLS 1.2 for Microsoft Teams Rooms requires Skype for Business Server 2015 Cumulative Update 9 (CU9) or Skype for Business Server 2019 Cumulative Update 1 (CU1).</span></span> <span data-ttu-id="f2356-137">Изменения не должны повлиять на пользователей Skype для бизнеса Online в отношении изменений, пересылаемых в соответствии с клиентами, в обратном направлении.</span><span class="sxs-lookup"><span data-stu-id="f2356-137">The change should not affect Skype for Business Online customers as client changes are forward and backward compliant.</span></span>
