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
ms.openlocfilehash: c87081ccd40765b10929a0d2762d834ce6a1b2ab
ms.sourcegitcommit: 2e11749734ff26b18709a1442b2c417f33430144
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/05/2018
ms.locfileid: "25429454"
---
# <a name="migrate-lync-room-system-lrs-devices-to-skype-room-system-v2"></a><span data-ttu-id="f2eff-103">Перенос устройств системы Lync комнаты (LRS) в системе комнаты Скайп версии 2</span><span class="sxs-lookup"><span data-stu-id="f2eff-103">Migrate Lync Room System (LRS) devices to Skype Room System v2</span></span> 
<span data-ttu-id="f2eff-104">[Окончание поддержки на 9 октября 2018](https://support.microsoft.com/en-us/help/4043450/products-reaching-end-of-support-for-2018)достигнет устройств системы Lync комнаты (LRS) с помощью программ Скайп комнаты системы версии 1 (SRS v1).</span><span class="sxs-lookup"><span data-stu-id="f2eff-104">Lync Room System (LRS) devices with Skype Room System Version 1 (SRS v1) software will reach [end of support on October 9, 2018](https://support.microsoft.com/en-us/help/4043450/products-reaching-end-of-support-for-2018).</span></span> <span data-ttu-id="f2eff-105">Это означает, что программное обеспечение v1 Скайп комнаты систем не будет любой обновлений продукта или исправления после указанной даты.</span><span class="sxs-lookup"><span data-stu-id="f2eff-105">This means Skype Room Systems v1 software will not get any product updates or fixes after this date.</span></span> <span data-ttu-id="f2eff-106">Пользователям с Lync комнаты системных устройств с использованием Скайп комнаты системное программное обеспечение v1 рекомендуется обновить свои устройства системы комнаты Скайп версии 2 (SRS v2).</span><span class="sxs-lookup"><span data-stu-id="f2eff-106">Customers with Lync Room System devices using Skype Room System v1 software are advised to upgrade their devices to Skype Room System version 2 (SRS v2).</span></span>

<span data-ttu-id="f2eff-107">Программное обеспечение Скайп комнаты системы версии 2 (SRS v2) работает с группами Майкрософт в дополнение к Скайп Business Server и Online Services для собраний и вызова на всех устройствах SRS поддерживаемые версии 2.</span><span class="sxs-lookup"><span data-stu-id="f2eff-107">Skype Room System Version 2 (SRS v2) software works with Microsoft Teams in addition to Skype for Business Server and Online services for meetings and calling on all SRS v2 supported devices.</span></span>

<span data-ttu-id="f2eff-108">Вашей существующего устройства **может** продолжать работу после окончания поддержке программного обеспечения системы комнаты Скайп v1 пока это программное обеспечение попадает ошибка программного обеспечения, требуется Microsoft для освобождения исправление или могут иметь дела использования существующего протокола обмена данными с Скайп комнаты системы программное обеспечение v1 изменяется или больше не поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="f2eff-108">Your existing devices **may** continue to work after the end of Skype Room System v1 software suppor until this software hits a software bug that needs Microsoft to release a fix, or may have a case where an existing communication protocol used by Skype Room System v1 software changes or is no longer supported.</span></span> <span data-ttu-id="f2eff-109">Одно из таких известных изменений является об использовании TLS 1.0 / 1.1 в Microsoft Office 365.</span><span class="sxs-lookup"><span data-stu-id="f2eff-109">One such known change is deprecation of TLS 1.0/ 1.1 in Microsoft Office 365.</span></span> <span data-ttu-id="f2eff-110">Дополнительные сведения о [Подготовка TLS 1.0/1.1, которые будут отменены](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Preparing-for-TLS-1-0-1-1-Deprecation-O365-Skype-for-Business/bc-p/223608).</span><span class="sxs-lookup"><span data-stu-id="f2eff-110">You can learn more about [Preparing for TLS 1.0/1.1 Deprecation](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Preparing-for-TLS-1-0-1-1-Deprecation-O365-Skype-for-Business/bc-p/223608).</span></span>  

## <a name="which-devices-are-affected"></a><span data-ttu-id="f2eff-111">Какие устройства будут затронуты?</span><span class="sxs-lookup"><span data-stu-id="f2eff-111">Which devices are affected?</span></span>
<span data-ttu-id="f2eff-112">Ниже приведен список устройств, которые затрагиваются это изменение:</span><span class="sxs-lookup"><span data-stu-id="f2eff-112">Here is the list of the devices that are affected by this change:</span></span>
- [<span data-ttu-id="f2eff-113">Смарт-систем комнаты</span><span class="sxs-lookup"><span data-stu-id="f2eff-113">SMART Room systems</span></span>](https://smartkapp.com/products/smart-room-systems)
- [<span data-ttu-id="f2eff-114">Crestron RL2</span><span class="sxs-lookup"><span data-stu-id="f2eff-114">Crestron RL2</span></span>](https://www.crestron.com/en-US/Products/Featured-Solutions/Crestron-RL-2)
- [<span data-ttu-id="f2eff-115">Polycom CX8000</span><span class="sxs-lookup"><span data-stu-id="f2eff-115">Polycom CX8000</span></span>](http://www.polycom.com/products-services/products-for-microsoft/skype-for-business/cx8000.html)
- <span data-ttu-id="f2eff-116">Crestron RL</span><span class="sxs-lookup"><span data-stu-id="f2eff-116">Crestron RL</span></span>

## <a name="upgrade-options"></a><span data-ttu-id="f2eff-117">Варианты обновления</span><span class="sxs-lookup"><span data-stu-id="f2eff-117">Upgrade options</span></span>
<span data-ttu-id="f2eff-118">Существует несколько вариантов обновления Lync комнаты систем следующего поколения Скайп комнаты систем (SRS v2).</span><span class="sxs-lookup"><span data-stu-id="f2eff-118">There are multiple options for upgrading Lync Room Systems to the next generation of Skype Room Systems (SRS v2).</span></span>

### <a name="crestron-hardware-trade-in-program"></a><span data-ttu-id="f2eff-119">Программа Trade-in Crestron оборудование</span><span class="sxs-lookup"><span data-stu-id="f2eff-119">Crestron hardware Trade-in program</span></span>
<span data-ttu-id="f2eff-120">Для всех клиентов системы комнаты Lync не Crestron Crestron обеспечит обновления [Crestron SR системы](https://www.crestron.com/en-us/products/featured-solutions/crestron-sr) или иметь эквивалентные права.</span><span class="sxs-lookup"><span data-stu-id="f2eff-120">Crestron will provide an upgrade to the [Crestron SR system](https://www.crestron.com/en-us/products/featured-solutions/crestron-sr) or equivalent for all Non-Crestron Lync Room System customers.</span></span> <span data-ttu-id="f2eff-121">Ознакомиться с подробными сведениями этой программы [здесь](https://support.crestron.com/app/answers/answer_view/a_id/1000220) или <!-- For details, --> [электронной почты](mailto:lrsupgrade@crestron.com) Crestron LRS поддержки.</span><span class="sxs-lookup"><span data-stu-id="f2eff-121">See details of this program [here](https://support.crestron.com/app/answers/answer_view/a_id/1000220) or <!-- For details, -->[email](mailto:lrsupgrade@crestron.com) Crestron LRS support.</span></span>  


### <a name="crestron-rl2-to-rl3"></a><span data-ttu-id="f2eff-122">Crestron RL2 для RL3</span><span class="sxs-lookup"><span data-stu-id="f2eff-122">Crestron RL2 to RL3</span></span>
<span data-ttu-id="f2eff-123">Существующие клиенты Crestron RL2 (также называется Crestron RL200) можно получить в пакет обновления для обновления текущей RL2 RL3, используя для минимальными затратами на устройство.</span><span class="sxs-lookup"><span data-stu-id="f2eff-123">Existing Crestron RL2 (also referred to as Crestron RL200) customers can acquire an upgrade package to upgrade current RL2 to RL3 using a for a minimal cost per device.</span></span> <span data-ttu-id="f2eff-124">Ознакомиться с подробными сведениями этой программы [здесь](https://support.crestron.com/app/answers/answer_view/a_id/1000220) или <!-- For details, --> [электронной почты](mailto:lrsupgrade@crestron.com) Crestron LRS поддержки.</span><span class="sxs-lookup"><span data-stu-id="f2eff-124">See details of this program [here](https://support.crestron.com/app/answers/answer_view/a_id/1000220) or <!-- For details, -->[email](mailto:lrsupgrade@crestron.com) Crestron LRS support.</span></span>  


### <a name="smart-room-systems-upgrade"></a><span data-ttu-id="f2eff-125">Обновление смарт-систем комнаты</span><span class="sxs-lookup"><span data-stu-id="f2eff-125">SMART Room Systems upgrade</span></span> 
<span data-ttu-id="f2eff-126">Для клиентов, смарт-LRS, за исключением программы trade-in Crestron оборудования Корпорация Майкрософт и СМАРТ также работают на предоставление решений для обновления до версии 2 Скайп комнаты системы.</span><span class="sxs-lookup"><span data-stu-id="f2eff-126">For SMART LRS customers, apart from Crestron hardware trade-in program, Microsoft and SMART are also working on providing a solution to upgrade to Skype Room System v2.</span></span> <span data-ttu-id="f2eff-127">Это обновление предлагается с помощью ИНТЕЛЛЕКТУАЛЬНОГО все существующие клиенты смарт-LRS.</span><span class="sxs-lookup"><span data-stu-id="f2eff-127">This upgrade will be offered by SMART to all existing SMART LRS customers.</span></span> <span data-ttu-id="f2eff-128">Дополнительные сведения об этой программы будет предоставляться на этой странице в 2018 октября.</span><span class="sxs-lookup"><span data-stu-id="f2eff-128">More details of this program will be provided on this page in October 2018.</span></span> <span data-ttu-id="f2eff-129">Убедитесь, что на наличие обновлений.</span><span class="sxs-lookup"><span data-stu-id="f2eff-129">Please make sure to check back for updates.</span></span>

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

## <a name="what-should-you-do"></a><span data-ttu-id="f2eff-130">Что делать?</span><span class="sxs-lookup"><span data-stu-id="f2eff-130">What should you do?</span></span>
<span data-ttu-id="f2eff-131">Мы рекомендуем планируется обновить систему комнаты Lync устройств систем комнаты Скайп версии 2 до устаревания TLS 1.0/1.1, с помощью параметров обновления уже было сказано.</span><span class="sxs-lookup"><span data-stu-id="f2eff-131">We recommend you plan to update Lync Room System devices to Skype Room Systems v2 before TLS 1.0/1.1 deprecation using upgrade options mentioned above.</span></span> <span data-ttu-id="f2eff-132">Кроме того также можно замена существующего устройства на новых устройств, сертифицированном для SRS версии 2.</span><span class="sxs-lookup"><span data-stu-id="f2eff-132">Additionally, you may also consider replacing existing devices with new devices certified for SRS v2.</span></span> <span data-ttu-id="f2eff-133">Просмотреть [устройств комнаты](https://aka.ms/roomdevices) для получения дополнительных сведений и также взглянем на [требования к версии 2 Скайп комнаты систем](https://docs.microsoft.com/en-us/skypeforbusiness/plan-your-deployment/clients-and-devices/requirements).</span><span class="sxs-lookup"><span data-stu-id="f2eff-133">See [Room devices](https://aka.ms/roomdevices) for details and also take a look at [Skype Room Systems v2 requirements](https://docs.microsoft.com/en-us/skypeforbusiness/plan-your-deployment/clients-and-devices/requirements).</span></span>  

> [!NOTE]
> <span data-ttu-id="f2eff-134">Функции сенсорного ввода и доски еще не поддерживается в системе комнаты Скайп версии 2.</span><span class="sxs-lookup"><span data-stu-id="f2eff-134">Touch and whiteboard functionality is not yet supported in Skype Room System v2.</span></span> <span data-ttu-id="f2eff-135">Поддержка сенсорного ввода и доски находится в невыполненной работы для системы комнаты Скайп версии 2 и будет добавлен в H1 CY2019.</span><span class="sxs-lookup"><span data-stu-id="f2eff-135">Touch and whiteboard support is in the backlog for Skype Room System v2 and will be added in H1 CY2019.</span></span>
