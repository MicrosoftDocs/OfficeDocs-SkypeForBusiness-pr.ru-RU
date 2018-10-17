---
title: Перенос системы комнаты Lync устройств системе комнаты Скайп версии 2
ms.author: jambirk
author: jambirk
ms.reviewer: sohailta
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: ''
description: В данном разделе приведены в этой статье описывается перенос системы комнаты Lync устройств для использования версии 2 Скайп комнаты системного программного обеспечения.
ms.openlocfilehash: a04eb857ee876b52507d21d5ee791ea327175921
ms.sourcegitcommit: f2b89fea199e7a1d2a3c90c153c94b0a35965e6f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2018
ms.locfileid: "25599206"
---
# <a name="migrate-lync-room-system-lrs-devices-to-skype-room-system-v2"></a><span data-ttu-id="59be4-103">Перенос устройств системы Lync комнаты (LRS) в системе комнаты Скайп версии 2</span><span class="sxs-lookup"><span data-stu-id="59be4-103">Migrate Lync Room System (LRS) devices to Skype Room System v2</span></span> 
<span data-ttu-id="59be4-104">Устройства системы Lync комнаты (LRS) с помощью программ Скайп комнаты системы версии 1 (SRS v1) достиг [окончания поддержки 9 октября 2018](https://support.microsoft.com/en-us/help/4043450/products-reaching-end-of-support-for-2018).</span><span class="sxs-lookup"><span data-stu-id="59be4-104">Lync Room System (LRS) devices with Skype Room System Version 1 (SRS v1) software has reached [end of support on October 9, 2018](https://support.microsoft.com/en-us/help/4043450/products-reaching-end-of-support-for-2018).</span></span> <span data-ttu-id="59be4-105">Это означает, что программное обеспечение v1 систем Скайп комнаты больше не будет любой обновлений продукта или исправления больше.</span><span class="sxs-lookup"><span data-stu-id="59be4-105">This means Skype Room Systems v1 software will no longer get any product updates or fixes anymore.</span></span> <span data-ttu-id="59be4-106">Пользователям с Lync комнаты системных устройств с использованием Скайп комнаты системное программное обеспечение v1 рекомендуется обновить свои устройства системы комнаты Скайп версии 2 (SRS v2).</span><span class="sxs-lookup"><span data-stu-id="59be4-106">Customers with Lync Room System devices using Skype Room System v1 software are advised to upgrade their devices to Skype Room System version 2 (SRS v2).</span></span>

<span data-ttu-id="59be4-107">Программное обеспечение Скайп комнаты системы версии 2 (SRS v2) работает с группами Майкрософт в дополнение к Скайп Business Server и Online Services для собраний и вызова на всех устройствах SRS поддерживаемые версии 2.</span><span class="sxs-lookup"><span data-stu-id="59be4-107">Skype Room System Version 2 (SRS v2) software works with Microsoft Teams in addition to Skype for Business Server and Online services for meetings and calling on all SRS v2 supported devices.</span></span>

<span data-ttu-id="59be4-108">Ваше существующего устройства **может** продолжать работу после окончания v1 Скайп комнаты системное программное обеспечение поддержки.</span><span class="sxs-lookup"><span data-stu-id="59be4-108">Your existing devices **may** continue to work after the end of Skype Room System v1 software support.</span></span> <span data-ttu-id="59be4-109">Тем не менее если это программное обеспечение достигает ошибки программного обеспечения, которое должно Microsoft для освобождения исправление, он будет не поддерживаться.</span><span class="sxs-lookup"><span data-stu-id="59be4-109">However, if this software hits a software bug that needs Microsoft to release a fix, it will not be supported.</span></span> <span data-ttu-id="59be4-110">SRS v1 использует протокол TLS 1.0 / 1.1, который в будущем является устаревшим корпорацией Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="59be4-110">SRS v1 uses TLS 1.0/ 1.1 which will be deprecated by Microsoft in future.</span></span> <span data-ttu-id="59be4-111">Дополнительные сведения о [Подготовка TLS 1.0/1.1, которые будут отменены](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Preparing-for-TLS-1-0-1-1-Deprecation-O365-Skype-for-Business/bc-p/223608).</span><span class="sxs-lookup"><span data-stu-id="59be4-111">You can learn more about [Preparing for TLS 1.0/1.1 Deprecation](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Preparing-for-TLS-1-0-1-1-Deprecation-O365-Skype-for-Business/bc-p/223608).</span></span> <span data-ttu-id="59be4-112">Скайп помещения системы V2 Добавление поддержки TLS 1.2 и продолжат работу после 31 октября 2018.</span><span class="sxs-lookup"><span data-stu-id="59be4-112">Skype Room System V2 is adding support for TLS 1.2 and will continue to work past October 31, 2018.</span></span> <span data-ttu-id="59be4-113">Скайп для бизнеса на локально клиенты не следует отключить TLS 1.0/1.1, пока не поддерживают annouces Скайп комнаты системы V2 для TLS 1.2 независимо от того, общие рекомендации по амортизации TLS 1.0/1.1.</span><span class="sxs-lookup"><span data-stu-id="59be4-113">Skype for Business on premise customers should not disable TLS 1.0/1.1 until Skype Room System V2 annouces support for TLS 1.2 regardless of general guidelines on TLS 1.0/1.1 deprecation.</span></span>

## <a name="which-devices-are-affected"></a><span data-ttu-id="59be4-114">Какие устройства будут затронуты?</span><span class="sxs-lookup"><span data-stu-id="59be4-114">Which devices are affected?</span></span>
<span data-ttu-id="59be4-115">Ниже приведен список устройств, которые затрагиваются это изменение:</span><span class="sxs-lookup"><span data-stu-id="59be4-115">Here is the list of the devices that are affected by this change:</span></span>
- [<span data-ttu-id="59be4-116">Смарт-систем комнаты</span><span class="sxs-lookup"><span data-stu-id="59be4-116">SMART Room systems</span></span>](https://support.smarttech.com/en/hardware/room-systems-skype)
- [<span data-ttu-id="59be4-117">Crestron RL2</span><span class="sxs-lookup"><span data-stu-id="59be4-117">Crestron RL2</span></span>](https://www.crestron.com/en-US/Products/Featured-Solutions/Crestron-RL-2)
- [<span data-ttu-id="59be4-118">Polycom CX8000</span><span class="sxs-lookup"><span data-stu-id="59be4-118">Polycom CX8000</span></span>](http://www.polycom.com/products-services/products-for-microsoft/skype-for-business/cx8000.html)
- <span data-ttu-id="59be4-119">Crestron RL</span><span class="sxs-lookup"><span data-stu-id="59be4-119">Crestron RL</span></span>

## <a name="upgrade-options"></a><span data-ttu-id="59be4-120">Варианты обновления</span><span class="sxs-lookup"><span data-stu-id="59be4-120">Upgrade options</span></span>
<span data-ttu-id="59be4-121">Существует несколько вариантов обновления Lync комнаты систем следующего поколения Скайп комнаты систем (SRS v2).</span><span class="sxs-lookup"><span data-stu-id="59be4-121">There are multiple options for upgrading Lync Room Systems to the next generation of Skype Room Systems (SRS v2).</span></span>

### <a name="crestron-hardware-trade-in-program"></a><span data-ttu-id="59be4-122">Программа Trade-in Crestron оборудование</span><span class="sxs-lookup"><span data-stu-id="59be4-122">Crestron hardware Trade-in program</span></span>
<span data-ttu-id="59be4-123">Для всех клиентов системы комнаты Lync не Crestron Crestron обеспечит обновления [Crestron SR системы](https://www.crestron.com/en-us/products/featured-solutions/crestron-sr) или иметь эквивалентные права.</span><span class="sxs-lookup"><span data-stu-id="59be4-123">Crestron will provide an upgrade to the [Crestron SR system](https://www.crestron.com/en-us/products/featured-solutions/crestron-sr) or equivalent for all Non-Crestron Lync Room System customers.</span></span> <span data-ttu-id="59be4-124">Ознакомиться с подробными сведениями этой программы [здесь](https://support.crestron.com/app/answers/answer_view/a_id/1000220) или <!-- For details, --> [электронной почты](mailto:lrsupgrade@crestron.com) Crestron LRS поддержки.</span><span class="sxs-lookup"><span data-stu-id="59be4-124">See details of this program [here](https://support.crestron.com/app/answers/answer_view/a_id/1000220) or <!-- For details, -->[email](mailto:lrsupgrade@crestron.com) Crestron LRS support.</span></span>  


### <a name="crestron-rl2-to-rl3"></a><span data-ttu-id="59be4-125">Crestron RL2 для RL3</span><span class="sxs-lookup"><span data-stu-id="59be4-125">Crestron RL2 to RL3</span></span>
<span data-ttu-id="59be4-126">Существующие клиенты Crestron RL2 (также называется Crestron RL200) можно получить в пакет обновления для обновления текущей RL2 RL3, используя для минимальными затратами на устройство.</span><span class="sxs-lookup"><span data-stu-id="59be4-126">Existing Crestron RL2 (also referred to as Crestron RL200) customers can acquire an upgrade package to upgrade current RL2 to RL3 using a for a minimal cost per device.</span></span> <span data-ttu-id="59be4-127">Ознакомиться с подробными сведениями этой программы [здесь](https://support.crestron.com/app/answers/answer_view/a_id/1000220) или <!-- For details, --> [электронной почты](mailto:lrsupgrade@crestron.com) Crestron LRS поддержки.</span><span class="sxs-lookup"><span data-stu-id="59be4-127">See details of this program [here](https://support.crestron.com/app/answers/answer_view/a_id/1000220) or <!-- For details, -->[email](mailto:lrsupgrade@crestron.com) Crestron LRS support.</span></span>  


### <a name="smart-room-systems-upgrade"></a><span data-ttu-id="59be4-128">Обновление смарт-систем комнаты</span><span class="sxs-lookup"><span data-stu-id="59be4-128">SMART Room Systems upgrade</span></span> 
<span data-ttu-id="59be4-129">Для клиентов, смарт-LRS, за исключением программы trade-in Crestron оборудования Корпорация Майкрософт и СМАРТ также работают на предоставление решений для обновления до версии 2 Скайп комнаты системы.</span><span class="sxs-lookup"><span data-stu-id="59be4-129">For SMART LRS customers, apart from Crestron hardware trade-in program, Microsoft and SMART are also working on providing a solution to upgrade to Skype Room System v2.</span></span> <span data-ttu-id="59be4-130">Это обновление будет предоставлено смарт-Technologies Inc. Можно найти дополнительные сведения о этой [здесь](https://support.smarttech.com/docs/hardware/room-systems-skype/srs-skype-v2/en/about/default.cshtml).</span><span class="sxs-lookup"><span data-stu-id="59be4-130">This upgrade will be provided by SMART Technologies Inc. Please see more about this [here](https://support.smarttech.com/docs/hardware/room-systems-skype/srs-skype-v2/en/about/default.cshtml).</span></span>

<!--  
For later 
### Do-It-Yourself
A Do-It-Yourself option is also available for customers with upgrade to Windows 10 and Skype Room Systems v2 software. Windows 10 Enterprise Licenses are available through [approved resellers](https://www.microsoft.com/en-us/Licensing/how-to-buy/how-to-buy.aspx) and Skype Room System V2 software will be available through this guide. 
 
  
To use this option however, customers must additionaly buy a [Logitech Screen Share](https://www.logitech.com/en-us/product/screen-share) adapter. Microsoft will provide instructions on how to use this adapter with Skype Room System v2 software. 


Look for upgrade instructions on this page shortly. 
  
### Summary of upgrade options
This table lists summary of all available options for existing LRS devices:
<!--  For later 
| Upgrade Option | SMART Room Systems | Crestron RL2 | Polycom CX8000 | Crestron RL |
|:--- |:--- |:--- |:--- |:--- |
|**Crestron hardware </br>Trade-in program**|Available|Available|Available|Available|
|**Crestron RL3**|Not Available|Available|Not Available|Not Available|
|**Do-It-Yourself**|Available|Not Available|Not Available|Not Available|
| | | | | |
-->

## <a name="what-should-you-do"></a><span data-ttu-id="59be4-131">Что делать?</span><span class="sxs-lookup"><span data-stu-id="59be4-131">What should you do?</span></span>
<span data-ttu-id="59be4-132">Мы рекомендуем планируется обновить систему комнаты Lync устройств систем комнаты Скайп версии 2 до устаревания TLS 1.0/1.1, с помощью параметров обновления уже было сказано.</span><span class="sxs-lookup"><span data-stu-id="59be4-132">We recommend you plan to update Lync Room System devices to Skype Room Systems v2 before TLS 1.0/1.1 deprecation using upgrade options mentioned above.</span></span> <span data-ttu-id="59be4-133">Кроме того также можно замена существующего устройства на новых устройств, сертифицированном для SRS версии 2.</span><span class="sxs-lookup"><span data-stu-id="59be4-133">Additionally, you may also consider replacing existing devices with new devices certified for SRS v2.</span></span> <span data-ttu-id="59be4-134">Просмотреть [устройств комнаты](https://aka.ms/roomdevices) для получения дополнительных сведений и также взглянем на [требования к версии 2 Скайп комнаты систем](https://docs.microsoft.com/en-us/skypeforbusiness/plan-your-deployment/clients-and-devices/requirements).</span><span class="sxs-lookup"><span data-stu-id="59be4-134">See [Room devices](https://aka.ms/roomdevices) for details and also take a look at [Skype Room Systems v2 requirements](https://docs.microsoft.com/en-us/skypeforbusiness/plan-your-deployment/clients-and-devices/requirements).</span></span>  

> [!NOTE]
> <span data-ttu-id="59be4-135">Функции сенсорного ввода и доски еще не поддерживается в системе комнаты Скайп версии 2.</span><span class="sxs-lookup"><span data-stu-id="59be4-135">Touch and whiteboard functionality is not yet supported in Skype Room System v2.</span></span> <span data-ttu-id="59be4-136">Поддержка сенсорного ввода и доски находится в невыполненной работы для системы комнаты Скайп версии 2 и будет добавлен в H1 CY2019.</span><span class="sxs-lookup"><span data-stu-id="59be4-136">Touch and whiteboard support is in the backlog for Skype Room System v2 and will be added in H1 CY2019.</span></span>

> [!NOTE]
> <span data-ttu-id="59be4-137">Программное обеспечение Скайп комнаты системы версии 2 в настоящее время не поддерживает протокол TLS 1.2.</span><span class="sxs-lookup"><span data-stu-id="59be4-137">Skype Room System V2 software currently does not support TLS 1.2 protocol.</span></span> <span data-ttu-id="59be4-138">Поддержка TLS 1.2 работает на и будут выполнены до устаревания TLS 1.0/1.1.</span><span class="sxs-lookup"><span data-stu-id="59be4-138">TLS 1.2 support is being worked on and will be completed before TLS 1.0/1.1 deprecation.</span></span> <span data-ttu-id="59be4-139">Upgradging клиентов к версии 2 SRS не будут отображаться любые влияния амортизации TLS 1.0/1.1 на комнаты устройств с последней версией приложения SRS версии 2.</span><span class="sxs-lookup"><span data-stu-id="59be4-139">Customers upgradging to SRS v2 will not see any impact of TLS 1.0/1.1 deprecation on Room devices running latest version of SRS v2 app.</span></span> <span data-ttu-id="59be4-140">Скайп для бизнеса на локально клиенты не следует отключить TLS 1.0/1.1, пока не поддерживают annouces Скайп комнаты системы V2 для TLS 1.2.</span><span class="sxs-lookup"><span data-stu-id="59be4-140">Skype for Business on premise customers should not disable TLS 1.0/1.1 until Skype Room System V2 annouces support for TLS 1.2.</span></span> 
