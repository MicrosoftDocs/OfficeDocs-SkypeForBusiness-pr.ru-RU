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
ms.openlocfilehash: 954d7893572c1d97506f4b6845792b0b940c3f2b
ms.sourcegitcommit: 6212645c485c41aafe1206bf7d39171ce35837b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/22/2018
ms.locfileid: "24968639"
---
# <a name="migrate-lync-room-system-lrs-devices-to-skype-room-system-v2"></a><span data-ttu-id="41eac-103">Перенос устройств системы Lync комнаты (LRS) в системе комнаты Скайп версии 2</span><span class="sxs-lookup"><span data-stu-id="41eac-103">Migrate Lync Room System (LRS) devices to Skype Room System v2</span></span> 
<span data-ttu-id="41eac-104">Окончание поддержки на 9 октября 2018 достигнет устройств системы Lync комнаты (LRS) с помощью программ Скайп комнаты системы версии 1 (SRS v1).</span><span class="sxs-lookup"><span data-stu-id="41eac-104">Lync Room System (LRS) devices with Skype Room System Version 1 (SRS v1) software will reach end of support on October 9, 2018.</span></span> <span data-ttu-id="41eac-105">Это означает, что программное обеспечение Скайп комнаты систем не будет любой обновлений продукта или исправления после указанной даты.</span><span class="sxs-lookup"><span data-stu-id="41eac-105">This means Skype Room Systems software will not get any product updates or fixes after this date.</span></span> <span data-ttu-id="41eac-106">Пользователям с Lync комнаты системных устройств с использованием Скайп комнаты системное программное обеспечение v1 рекомендуется обновить свои устройства системы комнаты Скайп версии 2 (SRS v2).</span><span class="sxs-lookup"><span data-stu-id="41eac-106">Customers with Lync Room System devices using Skype Room System v1 software are advised to upgrade their devices to Skype Room System version 2 (SRS v2).</span></span>

<span data-ttu-id="41eac-107">Программное обеспечение Скайп комнаты системы версии 2 (SRS v2) работает с группами Майкрософт в дополнение к Скайп Business Server и Online Services для собраний и вызова на всех устройствах SRS поддерживаемые версии 2.</span><span class="sxs-lookup"><span data-stu-id="41eac-107">Skype Room System Version 2 (SRS v2) software works with Microsoft Teams in addition to Skype for Business Server and Online services for meetings and calling on all SRS v2 supported devices.</span></span>

<span data-ttu-id="41eac-108">Ваше существующего устройства **может** продолжать работу после окончания v1 Скайп комнаты системное программное обеспечение поддержки.</span><span class="sxs-lookup"><span data-stu-id="41eac-108">Your existing devices **may** continue to work after the end of Skype Room System v1 software support.</span></span> <span data-ttu-id="41eac-109">Это программное обеспечение в конечном счете сбора данных, которое должно Microsoft для освобождения исправление ошибки программного обеспечения или могут иметь случая, где существующего протокола обмена данными используемые изменения программного обеспечения v1 Скайп комнаты системы или больше не поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="41eac-109">This software will eventually hit a software bug that needs Microsoft to release a fix, or may have a case where an existing communication protocol used by Skype Room System v1 software changes or is no longer supported.</span></span> <span data-ttu-id="41eac-110">Одно из таких известных изменений является об использовании TLS 1.0 / 1.1 в Microsoft Office 365.</span><span class="sxs-lookup"><span data-stu-id="41eac-110">One such known change is deprecation of TLS 1.0/ 1.1 in Microsoft Office 365.</span></span> <span data-ttu-id="41eac-111">Дополнительные сведения о [Подготовка TLS 1.0/1.1, которые будут отменены](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Preparing-for-TLS-1-0-1-1-Deprecation-O365-Skype-for-Business/bc-p/223608).</span><span class="sxs-lookup"><span data-stu-id="41eac-111">You can learn more about [Preparing for TLS 1.0/1.1 Deprecation](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Preparing-for-TLS-1-0-1-1-Deprecation-O365-Skype-for-Business/bc-p/223608).</span></span>  

## <a name="which-devices-are-affected"></a><span data-ttu-id="41eac-112">Какие устройства будут затронуты?</span><span class="sxs-lookup"><span data-stu-id="41eac-112">Which devices are affected?</span></span>
<span data-ttu-id="41eac-113">Ниже приведен список устройств, которые затрагиваются это изменение:</span><span class="sxs-lookup"><span data-stu-id="41eac-113">Here is the list of the devices that are affected by this change:</span></span>
- [<span data-ttu-id="41eac-114">Смарт-систем комнаты</span><span class="sxs-lookup"><span data-stu-id="41eac-114">SMART Room systems</span></span>](https://smartkapp.com/products/smart-room-systems)
- [<span data-ttu-id="41eac-115">Crestron RL2</span><span class="sxs-lookup"><span data-stu-id="41eac-115">Crestron RL2</span></span>](https://www.crestron.com/en-US/Products/Featured-Solutions/Crestron-RL-2)
- [<span data-ttu-id="41eac-116">Polycom CX8000</span><span class="sxs-lookup"><span data-stu-id="41eac-116">Polycom CX8000</span></span>](http://www.polycom.com/products-services/products-for-microsoft/skype-for-business/cx8000.html)
- <span data-ttu-id="41eac-117">Crestron RL</span><span class="sxs-lookup"><span data-stu-id="41eac-117">Crestron RL</span></span>

## <a name="upgrade-options"></a><span data-ttu-id="41eac-118">Варианты обновления</span><span class="sxs-lookup"><span data-stu-id="41eac-118">Upgrade options</span></span>
<span data-ttu-id="41eac-119">Существует несколько вариантов обновления Lync комнаты систем следующего поколения Скайп комнаты систем (SRS v2).</span><span class="sxs-lookup"><span data-stu-id="41eac-119">There are multiple options for upgrading Lync Room Systems to the next generation of Skype Room Systems (SRS v2).</span></span>

### <a name="crestron-hardware-trade-in-program"></a><span data-ttu-id="41eac-120">Программа Trade-in Crestron оборудование</span><span class="sxs-lookup"><span data-stu-id="41eac-120">Crestron hardware Trade-in program</span></span>
<span data-ttu-id="41eac-121">Для всех клиентов системы комнаты Lync не Crestron Crestron обеспечит обновления [Crestron SR системы](https://www.crestron.com/en-us/products/featured-solutions/crestron-sr) или иметь эквивалентные права.</span><span class="sxs-lookup"><span data-stu-id="41eac-121">Crestron will provide an upgrade to the [Crestron SR system](https://www.crestron.com/en-us/products/featured-solutions/crestron-sr) or equivalent for all Non-Crestron Lync Room System customers.</span></span> <span data-ttu-id="41eac-122">Ознакомиться с подробными сведениями этой программы [здесь](https://support.crestron.com/app/answers/answer_view/a_id/1000220) или <!-- For details, --> [электронной почты](mailto:lrsupgrade@crestron.com) Crestron LRS поддержки.</span><span class="sxs-lookup"><span data-stu-id="41eac-122">See details of this program [here](https://support.crestron.com/app/answers/answer_view/a_id/1000220) or <!-- For details, -->[email](mailto:lrsupgrade@crestron.com) Crestron LRS support.</span></span>  


### <a name="crestron-rl2-to-rl3"></a><span data-ttu-id="41eac-123">Crestron RL2 для RL3</span><span class="sxs-lookup"><span data-stu-id="41eac-123">Crestron RL2 to RL3</span></span>
<span data-ttu-id="41eac-124">Существующие клиенты Crestron RL2 (также называется Crestron RL200) можно получить в пакет обновления для обновления текущей RL2 RL3, используя для минимальными затратами на устройство.</span><span class="sxs-lookup"><span data-stu-id="41eac-124">Existing Crestron RL2 (also referred to as Crestron RL200) customers can acquire an upgrade package to upgrade current RL2 to RL3 using a for a minimal cost per device.</span></span> <span data-ttu-id="41eac-125">Ознакомиться с подробными сведениями этой программы [здесь](https://support.crestron.com/app/answers/answer_view/a_id/1000220) или <!-- For details, --> [электронной почты](mailto:lrsupgrade@crestron.com) Crestron LRS поддержки.</span><span class="sxs-lookup"><span data-stu-id="41eac-125">See details of this program [here](https://support.crestron.com/app/answers/answer_view/a_id/1000220) or <!-- For details, -->[email](mailto:lrsupgrade@crestron.com) Crestron LRS support.</span></span>  


### <a name="smart-room-systems-upgrade--diy-program"></a><span data-ttu-id="41eac-126">Смарт-систем комнаты обновления & DIY программы</span><span class="sxs-lookup"><span data-stu-id="41eac-126">SMART Room Systems upgrade & DIY program</span></span>
<span data-ttu-id="41eac-127">Для клиентов, смарт-LRS, за исключением программы trade-in Crestron оборудования Корпорация Майкрософт и СМАРТ также работают на предоставление решений для обновления до версии 2 Скайп комнаты системы.</span><span class="sxs-lookup"><span data-stu-id="41eac-127">For SMART LRS customers, apart from Crestron hardware trade-in program, Microsoft and SMART are also working on providing a solution to upgrade to Skype Room System v2.</span></span> <span data-ttu-id="41eac-128">Майкрософт также тестирует DIY решения для смарт-LRS клиентов.</span><span class="sxs-lookup"><span data-stu-id="41eac-128">Microsoft is also testing a DIY solution for SMART LRS customers.</span></span> <span data-ttu-id="41eac-129">Дополнительные сведения о таких программ будет предоставляться на этой странице в первых 2018 октября.</span><span class="sxs-lookup"><span data-stu-id="41eac-129">More details of these programs will be provided on this page in early October 2018.</span></span> <span data-ttu-id="41eac-130">Убедитесь, что на наличие обновлений на эти варианты обновления.</span><span class="sxs-lookup"><span data-stu-id="41eac-130">Please make sure to check back for updates on these upgrade options.</span></span>

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

## <a name="what-should-you-do"></a><span data-ttu-id="41eac-131">Что делать?</span><span class="sxs-lookup"><span data-stu-id="41eac-131">What should you do?</span></span>
<span data-ttu-id="41eac-132">Мы рекомендуем планируется обновить систему комнаты Lync устройств систем комнаты Скайп версии 2 до устаревания TLS 1.0/1.1, с помощью параметров обновления уже было сказано.</span><span class="sxs-lookup"><span data-stu-id="41eac-132">We recommend you plan to update Lync Room System devices to Skype Room Systems v2 before TLS 1.0/1.1 deprecation using upgrade options mentioned above.</span></span> <span data-ttu-id="41eac-133">Кроме того также можно замена существующего устройства на новых устройств, сертифицированном для SRS версии 2.</span><span class="sxs-lookup"><span data-stu-id="41eac-133">Additionally, you may also consider replacing existing devices with new devices certified for SRS v2.</span></span> <span data-ttu-id="41eac-134">Ознакомиться с подробными сведениями в [системах комнаты Скайп требования к версии 2](https://docs.microsoft.com/en-us/skypeforbusiness/plan-your-deployment/clients-and-devices/requirements).</span><span class="sxs-lookup"><span data-stu-id="41eac-134">See details in [Skype Room Systems v2 requirements](https://docs.microsoft.com/en-us/skypeforbusiness/plan-your-deployment/clients-and-devices/requirements).</span></span>  

> [!NOTE]
> <span data-ttu-id="41eac-135">Функции сенсорного ввода и доски еще не поддерживается в системе комнаты Скайп версии 2.</span><span class="sxs-lookup"><span data-stu-id="41eac-135">Touch and whiteboard functionality is not yet supported in Skype Room System v2.</span></span> <span data-ttu-id="41eac-136">Поддержка сенсорного ввода и доски находится в невыполненной работы для системы комнаты Скайп версии 2 и будет добавлен в H1 CY2019.</span><span class="sxs-lookup"><span data-stu-id="41eac-136">Touch and whiteboard support is in the backlog for Skype Room System v2 and will be added in H1 CY2019.</span></span>
