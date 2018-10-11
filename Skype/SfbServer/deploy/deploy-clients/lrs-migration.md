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
ms.openlocfilehash: 790872ceaf919d4b58bdbd753dc32e1303b2da63
ms.sourcegitcommit: 08933c8f795048feaa05828e000df5082ac90761
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/11/2018
ms.locfileid: "25495592"
---
# <a name="migrate-lync-room-system-lrs-devices-to-skype-room-system-v2"></a><span data-ttu-id="49769-103">Перенос устройств системы Lync комнаты (LRS) в системе комнаты Скайп версии 2</span><span class="sxs-lookup"><span data-stu-id="49769-103">Migrate Lync Room System (LRS) devices to Skype Room System v2</span></span> 
<span data-ttu-id="49769-104">Устройства системы Lync комнаты (LRS) с помощью программ Скайп комнаты системы версии 1 (SRS v1) достиг [окончания поддержки 9 октября 2018](https://support.microsoft.com/en-us/help/4043450/products-reaching-end-of-support-for-2018).</span><span class="sxs-lookup"><span data-stu-id="49769-104">Lync Room System (LRS) devices with Skype Room System Version 1 (SRS v1) software has reached [end of support on October 9, 2018](https://support.microsoft.com/en-us/help/4043450/products-reaching-end-of-support-for-2018).</span></span> <span data-ttu-id="49769-105">Это означает, что программное обеспечение v1 систем Скайп комнаты больше не будет любой обновлений продукта или исправления больше.</span><span class="sxs-lookup"><span data-stu-id="49769-105">This means Skype Room Systems v1 software will no longer get any product updates or fixes anymore.</span></span> <span data-ttu-id="49769-106">Пользователям с Lync комнаты системных устройств с использованием Скайп комнаты системное программное обеспечение v1 рекомендуется обновить свои устройства системы комнаты Скайп версии 2 (SRS v2).</span><span class="sxs-lookup"><span data-stu-id="49769-106">Customers with Lync Room System devices using Skype Room System v1 software are advised to upgrade their devices to Skype Room System version 2 (SRS v2).</span></span>

<span data-ttu-id="49769-107">Программное обеспечение Скайп комнаты системы версии 2 (SRS v2) работает с группами Майкрософт в дополнение к Скайп Business Server и Online Services для собраний и вызова на всех устройствах SRS поддерживаемые версии 2.</span><span class="sxs-lookup"><span data-stu-id="49769-107">Skype Room System Version 2 (SRS v2) software works with Microsoft Teams in addition to Skype for Business Server and Online services for meetings and calling on all SRS v2 supported devices.</span></span>

<span data-ttu-id="49769-108">Ваше существующего устройства **может** продолжать работу после окончания v1 Скайп комнаты системное программное обеспечение поддержки.</span><span class="sxs-lookup"><span data-stu-id="49769-108">Your existing devices **may** continue to work after the end of Skype Room System v1 software support.</span></span> <span data-ttu-id="49769-109">Тем не менее если это программное обеспечение достигает ошибки программного обеспечения, которое должно Microsoft для освобождения исправление, он будет не поддерживаться.</span><span class="sxs-lookup"><span data-stu-id="49769-109">However, if this software hits a software bug that needs Microsoft to release a fix, it will not be supported.</span></span> <span data-ttu-id="49769-110">Программное обеспечение Скайп комнаты системы V1 не также будут обновлены для поддержки TLS 1.2.</span><span class="sxs-lookup"><span data-stu-id="49769-110">Skype Room System V1 software will also not be upgraded to support TLS 1.2.</span></span> <span data-ttu-id="49769-111">Дополнительные сведения о [Подготовка TLS 1.0/1.1, которые будут отменены](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Preparing-for-TLS-1-0-1-1-Deprecation-O365-Skype-for-Business/bc-p/223608).</span><span class="sxs-lookup"><span data-stu-id="49769-111">You can learn more about [Preparing for TLS 1.0/1.1 Deprecation](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Preparing-for-TLS-1-0-1-1-Deprecation-O365-Skype-for-Business/bc-p/223608).</span></span> <span data-ttu-id="49769-112">Скайп помещения системы V2 Добавление поддержки TLS 1.2 и будет продолжать работать без какого-либо ущерба от этой амортизации.</span><span class="sxs-lookup"><span data-stu-id="49769-112">Skype Room System V2 is adding support for TLS 1.2 and will continue to work without any impact from this deprecation.</span></span>   

## <a name="which-devices-are-affected"></a><span data-ttu-id="49769-113">Какие устройства будут затронуты?</span><span class="sxs-lookup"><span data-stu-id="49769-113">Which devices are affected?</span></span>
<span data-ttu-id="49769-114">Ниже приведен список устройств, которые затрагиваются это изменение:</span><span class="sxs-lookup"><span data-stu-id="49769-114">Here is the list of the devices that are affected by this change:</span></span>
- [<span data-ttu-id="49769-115">Смарт-систем комнаты</span><span class="sxs-lookup"><span data-stu-id="49769-115">SMART Room systems</span></span>](https://support.smarttech.com/en/hardware/room-systems-skype)
- [<span data-ttu-id="49769-116">Crestron RL2</span><span class="sxs-lookup"><span data-stu-id="49769-116">Crestron RL2</span></span>](https://www.crestron.com/en-US/Products/Featured-Solutions/Crestron-RL-2)
- [<span data-ttu-id="49769-117">Polycom CX8000</span><span class="sxs-lookup"><span data-stu-id="49769-117">Polycom CX8000</span></span>](http://www.polycom.com/products-services/products-for-microsoft/skype-for-business/cx8000.html)
- <span data-ttu-id="49769-118">Crestron RL</span><span class="sxs-lookup"><span data-stu-id="49769-118">Crestron RL</span></span>

## <a name="upgrade-options"></a><span data-ttu-id="49769-119">Варианты обновления</span><span class="sxs-lookup"><span data-stu-id="49769-119">Upgrade options</span></span>
<span data-ttu-id="49769-120">Существует несколько вариантов обновления Lync комнаты систем следующего поколения Скайп комнаты систем (SRS v2).</span><span class="sxs-lookup"><span data-stu-id="49769-120">There are multiple options for upgrading Lync Room Systems to the next generation of Skype Room Systems (SRS v2).</span></span>

### <a name="crestron-hardware-trade-in-program"></a><span data-ttu-id="49769-121">Программа Trade-in Crestron оборудование</span><span class="sxs-lookup"><span data-stu-id="49769-121">Crestron hardware Trade-in program</span></span>
<span data-ttu-id="49769-122">Для всех клиентов системы комнаты Lync не Crestron Crestron обеспечит обновления [Crestron SR системы](https://www.crestron.com/en-us/products/featured-solutions/crestron-sr) или иметь эквивалентные права.</span><span class="sxs-lookup"><span data-stu-id="49769-122">Crestron will provide an upgrade to the [Crestron SR system](https://www.crestron.com/en-us/products/featured-solutions/crestron-sr) or equivalent for all Non-Crestron Lync Room System customers.</span></span> <span data-ttu-id="49769-123">Ознакомиться с подробными сведениями этой программы [здесь](https://support.crestron.com/app/answers/answer_view/a_id/1000220) или <!-- For details, --> [электронной почты](mailto:lrsupgrade@crestron.com) Crestron LRS поддержки.</span><span class="sxs-lookup"><span data-stu-id="49769-123">See details of this program [here](https://support.crestron.com/app/answers/answer_view/a_id/1000220) or <!-- For details, -->[email](mailto:lrsupgrade@crestron.com) Crestron LRS support.</span></span>  


### <a name="crestron-rl2-to-rl3"></a><span data-ttu-id="49769-124">Crestron RL2 для RL3</span><span class="sxs-lookup"><span data-stu-id="49769-124">Crestron RL2 to RL3</span></span>
<span data-ttu-id="49769-125">Существующие клиенты Crestron RL2 (также называется Crestron RL200) можно получить в пакет обновления для обновления текущей RL2 RL3, используя для минимальными затратами на устройство.</span><span class="sxs-lookup"><span data-stu-id="49769-125">Existing Crestron RL2 (also referred to as Crestron RL200) customers can acquire an upgrade package to upgrade current RL2 to RL3 using a for a minimal cost per device.</span></span> <span data-ttu-id="49769-126">Ознакомиться с подробными сведениями этой программы [здесь](https://support.crestron.com/app/answers/answer_view/a_id/1000220) или <!-- For details, --> [электронной почты](mailto:lrsupgrade@crestron.com) Crestron LRS поддержки.</span><span class="sxs-lookup"><span data-stu-id="49769-126">See details of this program [here](https://support.crestron.com/app/answers/answer_view/a_id/1000220) or <!-- For details, -->[email](mailto:lrsupgrade@crestron.com) Crestron LRS support.</span></span>  


### <a name="smart-room-systems-upgrade"></a><span data-ttu-id="49769-127">Обновление смарт-систем комнаты</span><span class="sxs-lookup"><span data-stu-id="49769-127">SMART Room Systems upgrade</span></span> 
<span data-ttu-id="49769-128">Для клиентов, смарт-LRS, за исключением программы trade-in Crestron оборудования Корпорация Майкрософт и СМАРТ также работают на предоставление решений для обновления до версии 2 Скайп комнаты системы.</span><span class="sxs-lookup"><span data-stu-id="49769-128">For SMART LRS customers, apart from Crestron hardware trade-in program, Microsoft and SMART are also working on providing a solution to upgrade to Skype Room System v2.</span></span> <span data-ttu-id="49769-129">Это обновление будет предоставлено смарт-Technologies Inc. Можно найти дополнительные сведения о этой [здесь](https://support.smarttech.com/docs/hardware/room-systems-skype/srs-skype-v2/en/about/default.cshtml).</span><span class="sxs-lookup"><span data-stu-id="49769-129">This upgrade will be provided by SMART Technologies Inc. Please see more about this [here](https://support.smarttech.com/docs/hardware/room-systems-skype/srs-skype-v2/en/about/default.cshtml).</span></span>

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

## <a name="what-should-you-do"></a><span data-ttu-id="49769-130">Что делать?</span><span class="sxs-lookup"><span data-stu-id="49769-130">What should you do?</span></span>
<span data-ttu-id="49769-131">Мы рекомендуем планируется обновить систему комнаты Lync устройств систем комнаты Скайп версии 2 до устаревания TLS 1.0/1.1, с помощью параметров обновления уже было сказано.</span><span class="sxs-lookup"><span data-stu-id="49769-131">We recommend you plan to update Lync Room System devices to Skype Room Systems v2 before TLS 1.0/1.1 deprecation using upgrade options mentioned above.</span></span> <span data-ttu-id="49769-132">Кроме того также можно замена существующего устройства на новых устройств, сертифицированном для SRS версии 2.</span><span class="sxs-lookup"><span data-stu-id="49769-132">Additionally, you may also consider replacing existing devices with new devices certified for SRS v2.</span></span> <span data-ttu-id="49769-133">Просмотреть [устройств комнаты](https://aka.ms/roomdevices) для получения дополнительных сведений и также взглянем на [требования к версии 2 Скайп комнаты систем](https://docs.microsoft.com/en-us/skypeforbusiness/plan-your-deployment/clients-and-devices/requirements).</span><span class="sxs-lookup"><span data-stu-id="49769-133">See [Room devices](https://aka.ms/roomdevices) for details and also take a look at [Skype Room Systems v2 requirements](https://docs.microsoft.com/en-us/skypeforbusiness/plan-your-deployment/clients-and-devices/requirements).</span></span>  

> [!NOTE]
> <span data-ttu-id="49769-134">Функции сенсорного ввода и доски еще не поддерживается в системе комнаты Скайп версии 2.</span><span class="sxs-lookup"><span data-stu-id="49769-134">Touch and whiteboard functionality is not yet supported in Skype Room System v2.</span></span> <span data-ttu-id="49769-135">Поддержка сенсорного ввода и доски находится в невыполненной работы для системы комнаты Скайп версии 2 и будет добавлен в H1 CY2019.</span><span class="sxs-lookup"><span data-stu-id="49769-135">Touch and whiteboard support is in the backlog for Skype Room System v2 and will be added in H1 CY2019.</span></span>

> [!NOTE]
> <span data-ttu-id="49769-136">Программное обеспечение Скайп комнаты системы версии 2 в настоящее время не поддерживает протокол TLS 1.2.</span><span class="sxs-lookup"><span data-stu-id="49769-136">Skype Room System V2 software currently does not support TLS 1.2 protocol.</span></span> <span data-ttu-id="49769-137">Поддержка TLS 1.2 работает на и будут выполнены до 1/0/1.1 TLS амортизации.</span><span class="sxs-lookup"><span data-stu-id="49769-137">TLS 1.2 support is being worked on and will be completed before TLS 1/0/1.1 deprecation.</span></span> <span data-ttu-id="49769-138">Upgradging клиентов к версии 2 SRS не будут отображаться любые влияния амортизации TLS 1.0/1.1 на комнаты устройств с последней версией приложения SRS версии 2.</span><span class="sxs-lookup"><span data-stu-id="49769-138">Customers upgradging to SRS v2 will not see any impact of TLS 1.0/1.1 deprecation on Room devices running latest version of SRS v2 app.</span></span>
