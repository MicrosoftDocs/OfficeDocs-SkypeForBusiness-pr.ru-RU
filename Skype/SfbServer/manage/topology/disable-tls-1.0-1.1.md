---
title: Отключение TLS 1.0/1.1 в Skype для бизнеса Server 2015
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: ab748733-6bad-4c93-8dda-db8d5271653d
description: Сводка. Подготовка и реализация отключения TLS 1.0 и 1.1 в средах.
ms.openlocfilehash: da76280540f9d18435ed929aace6cf6fc439a4cf
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49826399"
---
# <a name="disable-tls-1011-in-skype-for-business-server-2015"></a><span data-ttu-id="211a2-103">Отключение TLS 1.0/1.1 в Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="211a2-103">Disable TLS 1.0/1.1 in Skype for Business Server 2015</span></span>

<span data-ttu-id="211a2-104">Цель этой статьи — предоставить необходимые инструкции по подготовке и внедрению отключения TLS 1.0 и 1.1 в средах.</span><span class="sxs-lookup"><span data-stu-id="211a2-104">The purpose of this article is to provide the necessary guidance for you to prepare for and implement disabling TLS 1.0 and 1.1 in your environments.</span></span> <span data-ttu-id="211a2-105">Этот процесс требует тщательного планирования и подготовки.</span><span class="sxs-lookup"><span data-stu-id="211a2-105">This process requires extensive planning and preparation.</span></span> <span data-ttu-id="211a2-106">Внимательно просмотрите все сведения из этой статьи при планировании отключения TLS 1.0 и 1.1 для организации.</span><span class="sxs-lookup"><span data-stu-id="211a2-106">Please carefully review all of the information in this article as you make your plan to disable TLS 1.0 and 1.1 for your organization.</span></span> <span data-ttu-id="211a2-107">Обратите внимание, что существует множество внешних зависимостей и условий подключения, на которые может повлиять отключение TLS 1.0/1.1, поэтому необходимо тщательное планирование и тестирование.</span><span class="sxs-lookup"><span data-stu-id="211a2-107">Note that there are many external dependencies and connectivity conditions that could be impacted by disabling TLS 1.0/1.1, so extensive planning and testing is warranted.</span></span>

## <a name="in-this-article"></a><span data-ttu-id="211a2-108">В этой статье</span><span class="sxs-lookup"><span data-stu-id="211a2-108">In this article</span></span>

- [<span data-ttu-id="211a2-109">Фон и область действия</span><span class="sxs-lookup"><span data-stu-id="211a2-109">Background and scope</span></span>](#background)
- [<span data-ttu-id="211a2-110">Необходимые условия и процесс</span><span class="sxs-lookup"><span data-stu-id="211a2-110">Prerequisites and process</span></span>](#prerequisites-and-process)
- [<span data-ttu-id="211a2-111">Расширенные сценарии развертывания</span><span class="sxs-lookup"><span data-stu-id="211a2-111">Advanced deployment scenarios</span></span>](#advanced-deployment-scenarios)

## <a name="background"></a><span data-ttu-id="211a2-112">Общие сведения</span><span class="sxs-lookup"><span data-stu-id="211a2-112">Background</span></span>

<span data-ttu-id="211a2-113">The primary drivers for providing TLS 1.0 and 1.1 disable support for Skype for Business Server On-Premises are Payment Card Industry (PCI) Security Standards И Federal Information Processing Standards requirements.</span><span class="sxs-lookup"><span data-stu-id="211a2-113">The primary drivers for providing TLS 1.0 and 1.1 disable support for Skype for Business Server On-Premises are Payment Card Industry (PCI) Security Standards Council and Federal Information Processing Standards requirements.</span></span> <span data-ttu-id="211a2-114">Дополнительные сведения о требованиях PCI можно найти [здесь.](https://blog.pcisecuritystandards.org/are-you-ready-for-30-june-2018-sayin-goodbye-to-ssl-early-tls)</span><span class="sxs-lookup"><span data-stu-id="211a2-114">More information for PCI requirements can be found [here](https://blog.pcisecuritystandards.org/are-you-ready-for-30-june-2018-sayin-goodbye-to-ssl-early-tls).</span></span>  <span data-ttu-id="211a2-115">Корпорация Майкрософт не может предоставлять инструкции о том, требуется ли вашей организации соблюдать эти или другие требования.</span><span class="sxs-lookup"><span data-stu-id="211a2-115">Microsoft cannot provide guidance on whether or not your organization is required to adhere to these or other requirements.</span></span> <span data-ttu-id="211a2-116">Необходимо определить, требуется ли отключение TLS 1.0 и/или 1.1 в средах.</span><span class="sxs-lookup"><span data-stu-id="211a2-116">You must determine if it is required for you to disable TLS 1.0 and/or 1.1 in your environments.</span></span>

<span data-ttu-id="211a2-117">Корпорация Майкрософт подготовила документ по [](https://cloudblogs.microsoft.com/microsoftsecure/2017/06/20/tls-1-2-support-at-microsoft/)TLS, доступный здесь, и мы также рекомендуем фоновые чтения, доступные в этом блоге [Exchange.](https://blogs.technet.microsoft.com/exchange/2018/01/26/exchange-server-tls-guidance-part-1-getting-ready-for-tls-1-2/)</span><span class="sxs-lookup"><span data-stu-id="211a2-117">Microsoft has produced a white paper on TLS available [here](https://cloudblogs.microsoft.com/microsoftsecure/2017/06/20/tls-1-2-support-at-microsoft/), and we also recommend the background reading available in this [Exchange blog](https://blogs.technet.microsoft.com/exchange/2018/01/26/exchange-server-tls-guidance-part-1-getting-ready-for-tls-1-2/).</span></span>

## <a name="supportability-scope"></a><span data-ttu-id="211a2-118">Область поддержки</span><span class="sxs-lookup"><span data-stu-id="211a2-118">Supportability Scope</span></span>

<span data-ttu-id="211a2-119">*Область* относится к границам поддержки.</span><span class="sxs-lookup"><span data-stu-id="211a2-119">*Scope* refers to supportability boundaries.</span></span> <span data-ttu-id="211a2-120">*Полностью протестированная* и поддерживаемая версия означает, что мы полностью поддерживаем и протестировали отключение TLS 1.0 и 1.1 для перечисленных версий продуктов.</span><span class="sxs-lookup"><span data-stu-id="211a2-120">*Fully tested and supported* means we fully support and have tested disabling of TLS 1.0 and 1.1 for the listed product versions.</span></span> <span data-ttu-id="211a2-121">*В настоящее время это* означает только это; Мы активно исследуем возможность применения этих продуктов для отключения поддержки TLS.</span><span class="sxs-lookup"><span data-stu-id="211a2-121">*Currently being investigated* means just that; we are actively investigating bringing these products into scope for TLS disable support.</span></span> <span data-ttu-id="211a2-122">*Выходит за рамки* означает, что эти версии продуктов не поддерживают отключение TLS 1.0 или 1.1 и не будут работать с указанными исключениями.</span><span class="sxs-lookup"><span data-stu-id="211a2-122">*Out of scope* means these product versions do not support disabling TLS 1.0 or 1.1 and will not work, with noted exceptions.</span></span>

### <a name="fully-tested-and-supported-servers"></a><span data-ttu-id="211a2-123">Полностью протестные и поддерживаемые серверы</span><span class="sxs-lookup"><span data-stu-id="211a2-123">Fully tested and supported servers</span></span>

- <span data-ttu-id="211a2-124">Skype для бизнеса Server 2019 CU1 17.0.2046.123 (июнь 2019 г.) или более высокий</span><span class="sxs-lookup"><span data-stu-id="211a2-124">Skype for Business Server 2019 CU1 17.0.2046.123 (June 2019) or higher</span></span>
- <span data-ttu-id="211a2-125">Skype для бизнеса Server 2015 CU9 6.0.9319.548 (май 2019 г.) или более высокий в Windows Server 2012 (с обновлением KB [3140245](https://support.microsoft.com/help/3140245/update-to-enable-tls-1-1-and-tls-1-2-as-a-default-secure-protocols-in) или более новым), 2012 R2 или 2016.</span><span class="sxs-lookup"><span data-stu-id="211a2-125">Skype for Business Server 2015 CU9 6.0.9319.548 (May 2019) or higher on Windows Server 2012 (with KB [3140245](https://support.microsoft.com/help/3140245/update-to-enable-tls-1-1-and-tls-1-2-as-a-default-secure-protocols-in) or superseding update), 2012 R2 or 2016.</span></span>
- <span data-ttu-id="211a2-126">На месте обновлен Skype для бизнеса Server 2015 с cu9 6.0.9319.548 (май 2019 г.) или более высокой версией Windows Server 2008 R2, 2012 г. (с обновлением KB [3140245](https://support.microsoft.com/help/3140245/update-to-enable-tls-1-1-and-tls-1-2-as-a-default-secure-protocols-in) или более новым обновлением) или 2012 R2.</span><span class="sxs-lookup"><span data-stu-id="211a2-126">In-place Upgraded Skype for Business Server 2015, with CU9 6.0.9319.548 (May 2019) or higher on Windows Server 2008 R2, 2012 (with KB [3140245](https://support.microsoft.com/help/3140245/update-to-enable-tls-1-1-and-tls-1-2-as-a-default-secure-protocols-in) or superseding update), or 2012 R2.</span></span>
- <span data-ttu-id="211a2-127">Руководство по подключению и Outlook Web App Exchange с Exchange Server 2010 с sp3 RU19 или более высокой [](https://blogs.technet.microsoft.com/exchange/2018/01/26/exchange-server-tls-guidance-part-1-getting-ready-for-tls-1-2/)</span><span class="sxs-lookup"><span data-stu-id="211a2-127">Exchange Connectivity and Outlook Web App with Exchange Server 2010 SP3 RU19 or higher, guidance [here](https://blogs.technet.microsoft.com/exchange/2018/01/26/exchange-server-tls-guidance-part-1-getting-ready-for-tls-1-2/)</span></span>
- <span data-ttu-id="211a2-128">Survivable Branch Appliance (SBA) with Skype for Business Server 2015 CU6 HF2 or higher (confirm with your vendor that they packaged the appropriate updates and have been made available for your appliance)</span><span class="sxs-lookup"><span data-stu-id="211a2-128">Survivable Branch Appliance (SBA) with Skype for Business Server 2015 CU6 HF2 or higher (confirm with your vendor that they packaged the appropriate updates and have been made available for your appliance)</span></span>
- <span data-ttu-id="211a2-129">Survivable Branch Server (SBS) with Skype for Business Server 2015 CU6 HF2 or higher</span><span class="sxs-lookup"><span data-stu-id="211a2-129">Survivable Branch Server (SBS) with Skype for Business Server 2015 CU6 HF2 or higher</span></span>
- <span data-ttu-id="211a2-130">Lync Server 2013 **Edge Role Only**, это происходит потому, что роль edge не имеет зависимости от Windows Fabric 1.0.</span><span class="sxs-lookup"><span data-stu-id="211a2-130">Lync Server 2013 **Edge Role Only**, this is because Edge role does not have a dependency on Windows Fabric 1.0.</span></span>

### <a name="fully-tested-and-supported-clients"></a><span data-ttu-id="211a2-131">Полностью протестированные и поддерживаемые клиенты</span><span class="sxs-lookup"><span data-stu-id="211a2-131">Fully tested and supported clients</span></span>

- <span data-ttu-id="211a2-132">Настольный клиент Lync 2013 (Skype для бизнеса), MSI и C2R, в том числе базовый [15.0.5023.1000](https://support.microsoft.com/help/4018334/april-3-2018-update-for-skype-for-business-2015-lync-2013-kb4018334) или более высокий</span><span class="sxs-lookup"><span data-stu-id="211a2-132">Lync 2013 (Skype for Business) Desktop Client, MSI and C2R, including Basic [15.0.5023.1000 or higher](https://support.microsoft.com/help/4018334/april-3-2018-update-for-skype-for-business-2015-lync-2013-kb4018334)</span></span>
- <span data-ttu-id="211a2-133">Клиент Skype для бизнеса 2016 для настольных ПК, MSI [16.0.4678.1000](https://support.microsoft.com/help/4018323/april-3-2018-update-for-skype-for-business-2016-kb4018323)или более высокий, включая базовый</span><span class="sxs-lookup"><span data-stu-id="211a2-133">Skype for Business 2016 Desktop Client, MSI [16.0.4678.1000 or higher](https://support.microsoft.com/help/4018323/april-3-2018-update-for-skype-for-business-2016-kb4018323), including Basic</span></span>
- <span data-ttu-id="211a2-134">Skype для бизнеса 2016 Click to Run Require the [April 2018](https://docs.microsoft.com/officeupdates/release-notes-office365-proplus) Updates:</span><span class="sxs-lookup"><span data-stu-id="211a2-134">Skype for Business 2016 Click to Run Require the [April 2018](https://docs.microsoft.com/officeupdates/release-notes-office365-proplus) Updates:</span></span> 
    - <span data-ttu-id="211a2-135">Monthly and Semi-Annual Targeted, 16 \. 0 \. 9126 \. 2152 or higher</span><span class="sxs-lookup"><span data-stu-id="211a2-135">Monthly and Semi-Annual Targeted, 16\.0\.9126\.2152 or higher</span></span>
    - <span data-ttu-id="211a2-136">Semi-Annual и Deferred Channel, 16 \. 0 \. 8431 \. 2242 или более поздних</span><span class="sxs-lookup"><span data-stu-id="211a2-136">Semi-Annual and Deferred Channel, 16\.0\.8431\.2242 or higher</span></span>
- <span data-ttu-id="211a2-137">Skype для бизнеса на Mac 16.15 или более высокой</span><span class="sxs-lookup"><span data-stu-id="211a2-137">Skype for Business on Mac 16.15 or higher</span></span>
- <span data-ttu-id="211a2-138">Skype для бизнеса для iOS и Android 6.19 или более высоких версий</span><span class="sxs-lookup"><span data-stu-id="211a2-138">Skype for Business for iOS and Android 6.19 or higher</span></span>
- <span data-ttu-id="211a2-139">Комнаты Microsoft Teams (ранее известные как Система комнат Skype V2 SRS V2) 4.0.64.0 (декабрь 2018 г.) или более высокий</span><span class="sxs-lookup"><span data-stu-id="211a2-139">Microsoft Teams Rooms (previously known as Skype Room System V2 SRS V2) 4.0.64.0 (December 2018) or higher</span></span>
- <span data-ttu-id="211a2-140">Обновление Surface Hub для выпуска Team на основе KB4499162 (май 2019 г., сборка ОС 15063.1835) или более высокого уровня</span><span class="sxs-lookup"><span data-stu-id="211a2-140">Surface Hub update for Team edition based on KB4499162 (May 2019, OS Build 15063.1835) or higher</span></span>
- <span data-ttu-id="211a2-141">Skype Web App 2015 CU6 HF2 или более высокого уровня (включает сервер)</span><span class="sxs-lookup"><span data-stu-id="211a2-141">Skype Web App 2015 CU6 HF2 or higher (ships with Server)</span></span>

### <a name="currently-being-investigated"></a><span data-ttu-id="211a2-142">В настоящее время ведется исследование</span><span class="sxs-lookup"><span data-stu-id="211a2-142">Currently being investigated</span></span>

- <span data-ttu-id="211a2-143">Панель мониторинга качества вызовов (новая установка после отключения TLS 1.0, 1.1, см. ниже)\*</span><span class="sxs-lookup"><span data-stu-id="211a2-143">Call Quality Dashboard (new install after TLS 1.0, 1.1 have been disabled, see below)\*</span></span>
 
### <a name="out-of-scope"></a><span data-ttu-id="211a2-144">Вне области поддержки</span><span class="sxs-lookup"><span data-stu-id="211a2-144">Out of scope</span></span>

<span data-ttu-id="211a2-145">Если не отмечено, следующие продукты не находятся в области применения TLS 1.0/1.1 и не будут работать в среде, где отключены TLS 1.0 и 1.1.</span><span class="sxs-lookup"><span data-stu-id="211a2-145">Except where noted, the following products are not in scope for TLS 1.0/1.1 disable support and will not function in an environment where TLS 1.0 and 1.1 have been disabled.</span></span> <span data-ttu-id="211a2-146">Что это означает: если вы по-прежнему используете серверы или клиенты вне области, их необходимо обновить или удалить, если требуется отключить TLS 1.0/1.1 в локальном развертывании Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="211a2-146">What this means: if you still utilize out-of-scope servers or clients, you must update or remove these if you need to disable TLS 1.0/1.1 anywhere in your Skype for Business Server on-premises deployment.</span></span>

- <span data-ttu-id="211a2-147">Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="211a2-147">Lync Server 2013</span></span>
- <span data-ttu-id="211a2-148">Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="211a2-148">Lync Server 2010</span></span>
- <span data-ttu-id="211a2-149">Windows Server 2008 или более низкий</span><span class="sxs-lookup"><span data-stu-id="211a2-149">Windows Server 2008 or lower</span></span>
- <span data-ttu-id="211a2-150">Lync для Mac 2011</span><span class="sxs-lookup"><span data-stu-id="211a2-150">Lync for Mac 2011</span></span>
- <span data-ttu-id="211a2-151">Lync 2013 для мобильных устройств — iOS, iPad, Android или Windows Phone</span><span class="sxs-lookup"><span data-stu-id="211a2-151">Lync 2013 for Mobile - iOS, iPad, Android or Windows Phone</span></span>
- <span data-ttu-id="211a2-152">Клиент Магазина Windows Lync "MX"</span><span class="sxs-lookup"><span data-stu-id="211a2-152">Lync "MX" Windows Store client</span></span>
- <span data-ttu-id="211a2-153">Система комнат Lync (т. е.</span><span class="sxs-lookup"><span data-stu-id="211a2-153">Lync Room System (a.k.a.</span></span> <span data-ttu-id="211a2-154">SRSv1).</span><span class="sxs-lookup"><span data-stu-id="211a2-154">SRSv1).</span></span> <span data-ttu-id="211a2-155">Поддержка LRS была достигнута 9 октября 2018 г. и не будет обновлена для поддержки TLS 1.2.</span><span class="sxs-lookup"><span data-stu-id="211a2-155">LRS reached end of support on October 9, 2018 and will not be updated to support TLS 1.2.</span></span>
- <span data-ttu-id="211a2-156">Все клиенты Lync 2010</span><span class="sxs-lookup"><span data-stu-id="211a2-156">All Lync 2010 clients</span></span>
- <span data-ttu-id="211a2-157">Lync Phone Edition — обновленное [руководство здесь.](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Certified-Skype-for-Business-Online-Phones-and-what-this-means/ba-p/120035)</span><span class="sxs-lookup"><span data-stu-id="211a2-157">Lync Phone Edition - updated guidance [here](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Certified-Skype-for-Business-Online-Phones-and-what-this-means/ba-p/120035).</span></span>
- <span data-ttu-id="211a2-158">Устройство для survivable Branch Appliance (SBA) или SBS на основе 2013 г.</span><span class="sxs-lookup"><span data-stu-id="211a2-158">2013 based Survivable Branch Appliance (SBA) or Survivable Branch Server (SBS)</span></span>
- <span data-ttu-id="211a2-159">Cloud Connector Edition (CCE)</span><span class="sxs-lookup"><span data-stu-id="211a2-159">Cloud Connector Edition (CCE)</span></span>
- <span data-ttu-id="211a2-160">Skype для бизнеса для Windows Phone</span><span class="sxs-lookup"><span data-stu-id="211a2-160">Skype for Business for Windows Phone</span></span>

### <a name="exceptions"></a><span data-ttu-id="211a2-161">Exceptions</span><span class="sxs-lookup"><span data-stu-id="211a2-161">Exceptions</span></span>

#### <a name="lync-server-2013"></a><span data-ttu-id="211a2-162">Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="211a2-162">Lync Server 2013</span></span>

<span data-ttu-id="211a2-163">Lync Server 2013 принимает зависимость от Windows Fabric версии 1.0.</span><span class="sxs-lookup"><span data-stu-id="211a2-163">Lync Server 2013 takes a dependency on Windows Fabric version 1.0.</span></span>  <span data-ttu-id="211a2-164">На этапе разработки для Lync Server 2013 Windows Fabric 1.0 была выбрана для привлекательных и новых распределенных архитектур, чтобы обеспечить репликацию, высокую доступность и устойчивость к сбоям.</span><span class="sxs-lookup"><span data-stu-id="211a2-164">In the design phase for Lync Server 2013, Windows Fabric 1.0 was chosen for its compelling and new distributed architecture to provide replication, high availability, and fault tolerance.</span></span>  <span data-ttu-id="211a2-165">Со временем и Skype для бизнеса Server, и Windows Fabric значительно улучшили эту совместную архитектуру и значительно перепроектировали ее в последующих версиях.</span><span class="sxs-lookup"><span data-stu-id="211a2-165">Over time, both Skype for Business Server and Windows Fabric have greatly improved this joint architecture with significant re-design in subsequent versions.</span></span>  <span data-ttu-id="211a2-166">Например, в текущем Skype для бизнеса 2015 Server используется Windows Fabric 3.0.</span><span class="sxs-lookup"><span data-stu-id="211a2-166">Current Skype for Business 2015 Server uses Windows Fabric 3.0, for example.</span></span>

<span data-ttu-id="211a2-167">К сожалению, Windows Fabric 1.0 **не поддерживает TLS 1.2.  Однако мы обновим Lync Server 2013 для работы с TLS 1.2.**</span><span class="sxs-lookup"><span data-stu-id="211a2-167">Unfortunately, Windows Fabric 1.0 **does not support TLS 1.2.  However, we will be updating Lync Server 2013 to work with TLS 1.2**.</span></span> <span data-ttu-id="211a2-168">Это будет в следующем накопительном обновлении для Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="211a2-168">This will be coming in the next Cumulative Update for Lync Server 2013.</span></span>  <span data-ttu-id="211a2-169">Мы предоставляем поддержку TLS 1.2 для обеспечения сосуществования, миграции, федерации и гибридных сценариев.</span><span class="sxs-lookup"><span data-stu-id="211a2-169">We're providing TLS 1.2 support to enable co-existence, migration, federation, and hybrid scenarios.</span></span>

<span data-ttu-id="211a2-170">Если вашей организации требуется отключить TLS 1.0 и 1.1 и в настоящее время вы используете Lync Server 2013, рекомендуем начать процесс планирования с возможностью обновления на месте или переноса на месте (новые пулы, перемещение пользователей) в Skype для бизнеса Server 2015 или более новой.</span><span class="sxs-lookup"><span data-stu-id="211a2-170">If your organization is required to disable TLS 1.0 and 1.1, and you currently use Lync Server 2013, we recommend you begin your planning process, with the possibility you may have to In-place upgrade or Side-by-Side migrate (new pools, move users) to Skype for Business Server 2015 or higher.</span></span>  <span data-ttu-id="211a2-171">Или вы можете ускорить миграцию в Skype для бизнеса Online.</span><span class="sxs-lookup"><span data-stu-id="211a2-171">Or you may want to accelerate migration to Skype for Business Online.</span></span>

#### <a name="call-quality-dashboard"></a><span data-ttu-id="211a2-172">Панель мониторинга качества звонка</span><span class="sxs-lookup"><span data-stu-id="211a2-172">Call Quality Dashboard</span></span>

<span data-ttu-id="211a2-173">В настоящее время на локальной панели мониторинга качества вызовов во время новой установки (при первой установке в локальной среде) есть зависимость от TLS 1.0.</span><span class="sxs-lookup"><span data-stu-id="211a2-173">On-Premises Call Quality Dashboard currently has a dependency on TLS 1.0 during new install (first time installing into your On-Premises environments).</span></span>  <span data-ttu-id="211a2-174">В настоящее время мы исследуем эту проблему и планируем выпустить исправление в ближайшем будущем.</span><span class="sxs-lookup"><span data-stu-id="211a2-174">We are currently investigating this issue and plan to release a fix in the near future.</span></span>  <span data-ttu-id="211a2-175">Если вы планируете установить CQD и отключить TLS 1.0, рекомендуется сначала завершить установку CQD, а затем продолжить отключение TLS 1.0.</span><span class="sxs-lookup"><span data-stu-id="211a2-175">If you are planning to install CQD and also disable TLS 1.0, we recommend that you complete CQD installation first, and then proceed with TLS 1.0 disabling.</span></span>

#### <a name="skype-for-business-sdn-manager"></a><span data-ttu-id="211a2-176">Skype для бизнеса SDN Manager</span><span class="sxs-lookup"><span data-stu-id="211a2-176">Skype for Business SDN Manager</span></span>

<span data-ttu-id="211a2-177">Диспетчер SDN Skype для бизнеса, SQL база данных во время новой установки зависит от TLS 1.0.</span><span class="sxs-lookup"><span data-stu-id="211a2-177">Skype for Business SDN Manager using SQL a database has a dependency on TLS 1.0 during new install.</span></span> <span data-ttu-id="211a2-178">Если вы планируете установить Диспетчер SDN Skype для бизнеса с помощью SQL базы данных, а также отключить TLS 1.0, рекомендуем сначала завершить диспетчер SDN Skype для бизнеса, а затем отключить TLS 1.0.</span><span class="sxs-lookup"><span data-stu-id="211a2-178">If you are planning to install Skype for Business SDN Manager using SQL a database and also disable TLS 1.0, we recommend that you complete Skype for Business SDN Manager first, and then proceed with TLS 1.0 disabling.</span></span> <span data-ttu-id="211a2-179">Если перед установкой TLS 1.0 был отключен, необходимо временно включить TLS 1.0 на сервере SQL Server, который будет использоваться для SQL skype for Business SDN Manager.</span><span class="sxs-lookup"><span data-stu-id="211a2-179">In case TLS 1.0 was disabled prior to installation, you should temporarily enabled TLS 1.0 back in SQL Server backend server that will be used to host Skype for Business SDN Manager SQL database.</span></span>

#### <a name="third-party-devices"></a><span data-ttu-id="211a2-180">Сторонние устройства</span><span class="sxs-lookup"><span data-stu-id="211a2-180">Third-party devices</span></span>

<span data-ttu-id="211a2-181">На сторонних устройствах, таких как телефоны 3PIP, видеоконференция, обратные прокси и балансиры нагрузки, обязательно проверьте возможность поддержки TLS 1.2, тщательно протестировать и при необходимости свяжитесь с поставщиком.</span><span class="sxs-lookup"><span data-stu-id="211a2-181">On third-party devices such as 3PIP phones, Video conferencing, Reverse Proxies and Load Balancers, be sure to validate TLS 1.2 supportability, test carefully, and contact the vendor if needed.</span></span>

### <a name="federation-considerations-when-disabling-tls-1011-on-edge-servers"></a><span data-ttu-id="211a2-182">Вопросы федерации при отключке TLS 1.0/1.1 на серверах</span><span class="sxs-lookup"><span data-stu-id="211a2-182">Federation considerations when disabling TLS 1.0/1.1 on Edge servers</span></span>

<span data-ttu-id="211a2-183">Необходимо тщательно спланировать и учитывать влияние отключения TLS 1.0/1.1 на ваши серверы.</span><span class="sxs-lookup"><span data-stu-id="211a2-183">You must carefully plan for and consider the impact of disabling TLS 1.0/1.1 on your Edge servers.</span></span>  <span data-ttu-id="211a2-184">После отключения TLS 1.0 и 1.1 вы можете обнаружить, что другие организации больше не смогут федерации с вашей организацией.</span><span class="sxs-lookup"><span data-stu-id="211a2-184">Once TLS 1.0 and 1.1 are disabled, you may find that other organizations are no longer be able to federate with your organization.</span></span>

<span data-ttu-id="211a2-185">Вы можете оставить TLS 1.0/1.1 включенным на ваших серверах, чтобы обеспечить обратную совместимость с внешними системами без исправлений (SfB 2015, Lync 2013) или более старыми (2010).</span><span class="sxs-lookup"><span data-stu-id="211a2-185">You may opt to keep TLS 1.0/1.1 enabled on your Edge servers to maintain backward compatibility with non-patched (SfB 2015, Lync 2013) or older (2010) external systems.</span></span>

<span data-ttu-id="211a2-186">Корпорация Майкрософт не может предоставлять советы или рекомендации относительно того, относится ли ваша побративная сеть (или любая сеть) к стандарту PCI; определяется отдельной компанией.</span><span class="sxs-lookup"><span data-stu-id="211a2-186">Microsoft cannot provide advice or recommendations on whether or not your Edge network (or any network) falls under PCI standard; that must be determined by the individual company.</span></span>

<span data-ttu-id="211a2-187">В настоящее время Skype для бизнеса Online может использовать TLS 1.2, поэтому влияние на гибридную или федерацию с Интернетом не ожидается.</span><span class="sxs-lookup"><span data-stu-id="211a2-187">Skype for Business Online is capable of TLS 1.2 today, so no impact to Hybrid/Federation with Online is expected.</span></span>

<span data-ttu-id="211a2-188">PIC (Public IM Connectivity) to Skype Consumer service: We do not expect disabling TLS 1.0/1.1 to impact [Skype Connectivity;](../../deploy/deploy-skype-connectivity.md) Шлюзы Microsoft PIC уже имеют TLS 1.2.</span><span class="sxs-lookup"><span data-stu-id="211a2-188">PIC (Public IM Connectivity) to Skype Consumer service: We do not expect disabling TLS 1.0/1.1 to impact [Skype Connectivity](../../deploy/deploy-skype-connectivity.md); Microsoft PIC Gateways are already TLS 1.2 capable.</span></span>

## <a name="prerequisites-and-process"></a><span data-ttu-id="211a2-189">Необходимые условия и процесс</span><span class="sxs-lookup"><span data-stu-id="211a2-189">Prerequisites and process</span></span>

<span data-ttu-id="211a2-190">За исключением случаев, когда TLS 1.0 и 1.1 отключены вне области действия серверов, клиенты и устройства будут работать должным образом или вообще.</span><span class="sxs-lookup"><span data-stu-id="211a2-190">Except where noted above, once TLS 1.0 and 1.1 are disabled out-of-scope servers, clients and devices will longer function properly, or at all.</span></span> <span data-ttu-id="211a2-191">Это может означать, что вам нужно приостановить и дождаться обновленных инструкций от Корпорации Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="211a2-191">This may mean you need to pause and wait for updated guidance from Microsoft.</span></span> <span data-ttu-id="211a2-192">После удовлетворения всех требований и планирования устранения пробелов продолжите работу.</span><span class="sxs-lookup"><span data-stu-id="211a2-192">Once you are satisfied that you meet all requirements and have a plan to address gaps, proceed.</span></span>

<span data-ttu-id="211a2-193">На высоком уровне, пока Skype для бизнеса Server 2019 готов к установке, Skype для бизнеса Server 2015 требует установки CU9, применения необходимых обновлений к .NET и SQL, развертывания необходимых разделов реестра и, наконец, отдельного круга обновлений конфигурации ОС (т. е. отключения TLS 1.0 и 1.1 с помощью импорта файлов реестра).</span><span class="sxs-lookup"><span data-stu-id="211a2-193">At a high level, while Skype for Business Server 2019 is ready for procedure at install, Skype for Business Server 2015 will require that you install CU9, applying pre-requisite updates to .NET and SQL, deploying prerequisite registry keys, and finally a separate round of OS configuration updates (i.e. disabling TLS 1.0 and 1.1 via registry file import).</span></span> <span data-ttu-id="211a2-194">Очень важно завершить установку всех необходимых условий, включая Skype для бизнеса Server 2015 CU6 HF2, перед отключением TLS 1.0 и 1.1 на любом сервере в вашей среде.</span><span class="sxs-lookup"><span data-stu-id="211a2-194">It is critically important that you complete installation of all prerequisites, including Skype for Business Server 2015 CU6 HF2, prior to disabling TLS 1.0 and 1.1 on any server in your environment.</span></span> <span data-ttu-id="211a2-195">Для каждого сервера Skype для бизнеса, включая роль edge и SQL серверов, требуются обновления.</span><span class="sxs-lookup"><span data-stu-id="211a2-195">Every Skype for Business server, including Edge role and SQL Backends, requires the updates.</span></span> <span data-ttu-id="211a2-196">Также убедитесь, что все поддерживаемые клиенты (в области) обновлены до требуемой минимальной версии.</span><span class="sxs-lookup"><span data-stu-id="211a2-196">Also ensure that all supported (in-scope) clients have been updated to the required minimum versions.</span></span> <span data-ttu-id="211a2-197">Не забудьте обновить и рабочие станции управления.</span><span class="sxs-lookup"><span data-stu-id="211a2-197">Don’t forget to update management workstations as well.</span></span>

<span data-ttu-id="211a2-198">Мы хотим следовать обычному порядку операций "изнутри" для обновления серверов Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="211a2-198">We want to follow the usual order of operations of "inside out" for upgrading Skype for Business servers.</span></span> <span data-ttu-id="211a2-199">Обрабатывать пулы директоров, сохраняемую беседу и сопряженные пулы так же, как обычно.</span><span class="sxs-lookup"><span data-stu-id="211a2-199">Treat Director pools, Persistent chat, and Paired Pools in the same manner you normally would.</span></span> <span data-ttu-id="211a2-200">Порядок и методы обновления здесь [и](topology.md) [здесь.](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015)</span><span class="sxs-lookup"><span data-stu-id="211a2-200">Order and methods for upgrade are covered [here](topology.md) and [here](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015).</span></span>

### <a name="high-level-process"></a><span data-ttu-id="211a2-201">Высокоуровневый процесс</span><span class="sxs-lookup"><span data-stu-id="211a2-201">High-level process</span></span>

1. <span data-ttu-id="211a2-202">Протестировать все действия в лаборатории перед настройкой производственных серверов.</span><span class="sxs-lookup"><span data-stu-id="211a2-202">Test all steps in your lab prior to configuring production servers.</span></span>
2. <span data-ttu-id="211a2-203">Скопируйте и сохраните копию экспортируемого реестра на каждом отдельном сервере, который требуется обновить.</span><span class="sxs-lookup"><span data-stu-id="211a2-203">Back up and preserve a copy of exported registry on each and every individual server to be updated.</span></span> <span data-ttu-id="211a2-204">Нельзя совместное управление реестрами между серверами; они содержат уникальные ключи на основе компьютера.</span><span class="sxs-lookup"><span data-stu-id="211a2-204">You cannot share registries between servers; they contain unique machine-based keys.</span></span>
3. <span data-ttu-id="211a2-205">Обновим все серверы Skype для бизнеса 2015 до cu9 или более высокого уровня.</span><span class="sxs-lookup"><span data-stu-id="211a2-205">Upgrade all Skype for Business 2015 servers to CU9 or higher.</span></span> <span data-ttu-id="211a2-206">Для Skype для бизнеса Server 2019 обновим до cu1 или более высокого уровня.</span><span class="sxs-lookup"><span data-stu-id="211a2-206">For Skype for Business Server 2019, upgrade to CU1 or higher.</span></span>
4. <span data-ttu-id="211a2-207">Установите все необходимые условия на все серверы.</span><span class="sxs-lookup"><span data-stu-id="211a2-207">Install all prerequisites to all servers.</span></span>
5. <span data-ttu-id="211a2-208">Развернем необходимые ключи реестра.</span><span class="sxs-lookup"><span data-stu-id="211a2-208">Deploy prerequisite registry keys.</span></span>
6. <span data-ttu-id="211a2-209">Убедитесь, что обновлены все клиенты, которые находятся в области действия.</span><span class="sxs-lookup"><span data-stu-id="211a2-209">Ensure that all in-scope clients are updated.</span></span>
7. <span data-ttu-id="211a2-210">Отключать TLS 1.0 и 1.1 с помощью импорта реестра.</span><span class="sxs-lookup"><span data-stu-id="211a2-210">Disable TLS 1.0 and 1.1 via registry import.</span></span>
8. <span data-ttu-id="211a2-211">Проверьте правильность работы рабочих нагрузок.</span><span class="sxs-lookup"><span data-stu-id="211a2-211">Validate that workloads are functioning as expected.</span></span>
    - <span data-ttu-id="211a2-212">Если возникают проблемы, устранять и устранять неполадки, а также</span><span class="sxs-lookup"><span data-stu-id="211a2-212">If problems are encountered, troubleshoot and resolve, or</span></span>
    - <span data-ttu-id="211a2-213">Восстановление реестра с шага 2, чтобы повторно включить TLS 1.0 и 1.1</span><span class="sxs-lookup"><span data-stu-id="211a2-213">Restore registry from step 2 to re-enable TLS 1.0 and 1.1</span></span>
9. <span data-ttu-id="211a2-214">Проверьте, используется ли только TLS 1.2.</span><span class="sxs-lookup"><span data-stu-id="211a2-214">Validate that only TLS 1.2 is being used.</span></span>

### <a name="install-prerequisites-to-all-servers"></a><span data-ttu-id="211a2-215">Установка необходимых условий на все серверы</span><span class="sxs-lookup"><span data-stu-id="211a2-215">Install prerequisites to all servers</span></span>

<span data-ttu-id="211a2-216">Перед отключением TLS 1.0 и 1.1 на уровне операционной системы в развертываниях Skype для бизнеса Server 2015 требуется тщательное обновление зависимостей.</span><span class="sxs-lookup"><span data-stu-id="211a2-216">Extensive dependency updating is required before you begin to disable TLS 1.0 and 1.1 at the operating system level in your Skype for Business Server 2015 deployments.</span></span> <span data-ttu-id="211a2-217">Ниже следующую версию можно использовать для поддержки TLS 1.2.</span><span class="sxs-lookup"><span data-stu-id="211a2-217">The following are the minimum versions that can support TLS 1.2.</span></span> <span data-ttu-id="211a2-218">Перед отключением TLS 1.0 и 1.1 разверните все необходимые обновления на каждом сервере Skype для бизнеса в вашей среде.</span><span class="sxs-lookup"><span data-stu-id="211a2-218">Deploy all prerequisite updates across every Skype for Business server in your environment before you begin disabling TLS 1.0 and 1.1.</span></span>

- <span data-ttu-id="211a2-219">Skype для бизнеса Server 2015 CU9 6.0.9319.548 (май 2019 г.) или более высокий</span><span class="sxs-lookup"><span data-stu-id="211a2-219">Skype for Business Server 2015 CU9 6.0.9319.548 (May 2019) or higher</span></span>
- <span data-ttu-id="211a2-220">[.NET Framework 4.7](https://www.microsoft.com/download/details.aspx?id=55167) или выше с включенным в реестре SchUseStrongCrypto (см. ниже)</span><span class="sxs-lookup"><span data-stu-id="211a2-220">[.NET Framework 4.7](https://www.microsoft.com/download/details.aspx?id=55167) or higher with SchUseStrongCrypto enabled in the registry (provided below)</span></span>
- <span data-ttu-id="211a2-221">SQL должны быть обновлены на всех серверах и серверах Skype для бизнеса 2015.</span><span class="sxs-lookup"><span data-stu-id="211a2-221">SQL must be updated on all Skype for Business 2015 servers and backends.</span></span> <span data-ttu-id="211a2-222">Сначала обновим пул Enterprise Edition SQL, а затем соответствующие FES.</span><span class="sxs-lookup"><span data-stu-id="211a2-222">Update Enterprise Edition Pool SQL Backends first, then their respective FEs.</span></span> 
    - <span data-ttu-id="211a2-223">[SQL Server 2014 с sp1 + CU5](https://support.microsoft.com/help/3130926), или выше / SQL Server 2012 с sp2 + CU16 или выше / [SQL Server 2014 RTM + CU12](https://support.microsoft.com/help/3130923/cumulative-update-12-for-sql-server-2014), или выше / SQL Server 2014 SP2</span><span class="sxs-lookup"><span data-stu-id="211a2-223">[SQL Server 2014 SP1 + CU5](https://support.microsoft.com/help/3130926), or higher / SQL Server 2012 SP2 + CU16 or higher / [SQL Server 2014 RTM + CU12](https://support.microsoft.com/help/3130923/cumulative-update-12-for-sql-server-2014), or higher / SQL Server 2014 SP2</span></span>
     - [<span data-ttu-id="211a2-224">SQL Server Native Client для SQL Server 2012</span><span class="sxs-lookup"><span data-stu-id="211a2-224">SQL Server Native Client for SQL Server 2012</span></span>](https://www.microsoft.com/download/details.aspx?id=50402)
     - <span data-ttu-id="211a2-225">[Microsoft ODBC Driver 11 for SQL Server](https://www.microsoft.com/download/details.aspx?id=36434), or higher</span><span class="sxs-lookup"><span data-stu-id="211a2-225">[Microsoft ODBC Driver 11 for SQL Server](https://www.microsoft.com/download/details.aspx?id=36434), or higher</span></span>
     - [<span data-ttu-id="211a2-226">Общие объекты управления для SQL Server 2014 с sp2</span><span class="sxs-lookup"><span data-stu-id="211a2-226">Shared Management Objects for SQL Server 2014 SP2</span></span>](https://www.microsoft.com/download/details.aspx?id=53164)
     - [<span data-ttu-id="211a2-227">SQLSysClrTypes для SQL Server 2014 с sp2</span><span class="sxs-lookup"><span data-stu-id="211a2-227">SQLSysClrTypes for SQL server 2014 SP2</span></span>](https://www.microsoft.com/download/details.aspx?id=42295)

### <a name="basic-steps-to-install-pre-requisites-in-recommended-order-of-operations"></a><span data-ttu-id="211a2-228">Основные действия по установке необходимых условий в рекомендуемом порядке операций</span><span class="sxs-lookup"><span data-stu-id="211a2-228">Basic steps to install pre-requisites, in recommended order of operations</span></span>

1. <span data-ttu-id="211a2-229">Установите обновление Skype для бизнеса Server CU9 на все серверы.</span><span class="sxs-lookup"><span data-stu-id="211a2-229">Install the Skype for Business Server CU9 update to all servers.</span></span> 
    1. <span data-ttu-id="211a2-230">Установите обновление компонентов с помощью обновления.</span><span class="sxs-lookup"><span data-stu-id="211a2-230">Install the update to components using the updater.</span></span>
    2. <span data-ttu-id="211a2-231">Обновление баз данных в соответствии с задокументированными процедурами.</span><span class="sxs-lookup"><span data-stu-id="211a2-231">Update databases according to documented procedures.</span></span> <span data-ttu-id="211a2-232">Для Skype для бизнеса Server 2015 см. KB [3061064](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015).</span><span class="sxs-lookup"><span data-stu-id="211a2-232">For Skype for Business Server 2015, see KB [3061064](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015).</span></span>
    3. <span data-ttu-id="211a2-233">Проверьте функциональные возможности продукта в развертывании, прежде чем двигаться дальше с любыми другими изменениями.</span><span class="sxs-lookup"><span data-stu-id="211a2-233">Validate product functionality in the deployment prior to moving forward with any other changes.</span></span>
2. <span data-ttu-id="211a2-234">Скачайте автономный установщик .NET 4.7.</span><span class="sxs-lookup"><span data-stu-id="211a2-234">Download .NET 4.7 Offline Installer.</span></span> 
    1. <span data-ttu-id="211a2-235">Справка: [https://www.microsoft.com/download/details.aspx?id=55167](https://www.microsoft.com/download/details.aspx?id=55167)</span><span class="sxs-lookup"><span data-stu-id="211a2-235">Reference: [https://www.microsoft.com/download/details.aspx?id=55167](https://www.microsoft.com/download/details.aspx?id=55167)</span></span>
    2. <span data-ttu-id="211a2-236">Убедитесь, что службы Skype для бизнеса Server 2015 остановлены на сервере переднего сервера.</span><span class="sxs-lookup"><span data-stu-id="211a2-236">Ensure that Skype for Business Server 2015 services are stopped on the Front End server.</span></span>
    3. <span data-ttu-id="211a2-237">Справка: [https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015)</span><span class="sxs-lookup"><span data-stu-id="211a2-237">Reference: [https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015)</span></span>
    4. <span data-ttu-id="211a2-238">Ex (Standard Edition): ```Stop-CsWindowsService```</span><span class="sxs-lookup"><span data-stu-id="211a2-238">Ex (Standard Edition): ```Stop-CsWindowsService```</span></span>
    5. <span data-ttu-id="211a2-239">Ex (Enterprise Edition): ```Invoke-CsComputerFailover```</span><span class="sxs-lookup"><span data-stu-id="211a2-239">Ex (Enterprise Edition): ```Invoke-CsComputerFailover```</span></span>
    6. <span data-ttu-id="211a2-240">Запустите пакет установщика.</span><span class="sxs-lookup"><span data-stu-id="211a2-240">Run the installer package.</span></span>
    7. <span data-ttu-id="211a2-241">Перезагрузите сервер.</span><span class="sxs-lookup"><span data-stu-id="211a2-241">Reboot the server.</span></span>
3. <span data-ttu-id="211a2-242">Обновление SQL Express 2014 на всех серверах.</span><span class="sxs-lookup"><span data-stu-id="211a2-242">Update SQL Express 2014 on all servers.</span></span> 
    1. <span data-ttu-id="211a2-243">Справка: [https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server](https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server)</span><span class="sxs-lookup"><span data-stu-id="211a2-243">Reference: [https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server](https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server)</span></span>
    2. <span data-ttu-id="211a2-244">Загрузка SQL 2014 с sp2</span><span class="sxs-lookup"><span data-stu-id="211a2-244">Download SQL 2014 SP2</span></span> 
        - <span data-ttu-id="211a2-245">Справка: [https://www.microsoft.com/download/details.aspx?id=53168](https://www.microsoft.com/download/details.aspx?id=53168)</span><span class="sxs-lookup"><span data-stu-id="211a2-245">Reference: [https://www.microsoft.com/download/details.aspx?id=53168](https://www.microsoft.com/download/details.aspx?id=53168)</span></span>
    3. <span data-ttu-id="211a2-246">Скопируйте установщик в папку на сервере (например, C:\01_2014SqlSp2)</span><span class="sxs-lookup"><span data-stu-id="211a2-246">Copy the installation media to a folder on the server (Ex: C:\01_2014SqlSp2)</span></span>
    4. <span data-ttu-id="211a2-247">Убедитесь, что службы Skype для бизнеса Server 2015 остановлены на сервере переднего сервера</span><span class="sxs-lookup"><span data-stu-id="211a2-247">Ensure Skype for Business Server 2015 services are stopped on the Front End server</span></span> 
        - <span data-ttu-id="211a2-248">Ex (Standard Edition): ```Stop-CsWindowsService```</span><span class="sxs-lookup"><span data-stu-id="211a2-248">Ex (Standard Edition): ```Stop-CsWindowsService```</span></span>
        - <span data-ttu-id="211a2-249">Ex (Enterprise Edition): ```Invoke-CsComputerFailover```</span><span class="sxs-lookup"><span data-stu-id="211a2-249">Ex (Enterprise Edition): ```Invoke-CsComputerFailover```</span></span>
    5. <span data-ttu-id="211a2-250">Откройте командную подсказку администратора и обновим все установленные компоненты и экземпляры</span><span class="sxs-lookup"><span data-stu-id="211a2-250">Open an Admin Command Prompt, and upgrade all installed components and instances</span></span> 
        - <span data-ttu-id="211a2-251">Пример: C:\01_2014SqlSp2\SQLServer2014SP2-KB3171021-x64-ENU.exe /qs /IAcceptSQLServerLicenseTerms /Action=Patch /AllInstances</span><span class="sxs-lookup"><span data-stu-id="211a2-251">Example: C:\01_2014SqlSp2\SQLServer2014SP2-KB3171021-x64-ENU.exe /qs /IAcceptSQLServerLicenseTerms /Action=Patch /AllInstances</span></span>
4. <span data-ttu-id="211a2-252">Обновление SQL Native Client.</span><span class="sxs-lookup"><span data-stu-id="211a2-252">Update SQL Native Client.</span></span> 
    1. <span data-ttu-id="211a2-253">Справка: [https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server](https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server) .</span><span class="sxs-lookup"><span data-stu-id="211a2-253">Reference: [https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server](https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server).</span></span>
    2. <span data-ttu-id="211a2-254">Скачать с [https://www.microsoft.com/download/details.aspx?id=50402](https://www.microsoft.com/download/details.aspx?id=50402)</span><span class="sxs-lookup"><span data-stu-id="211a2-254">Download from [https://www.microsoft.com/download/details.aspx?id=50402](https://www.microsoft.com/download/details.aspx?id=50402)</span></span>
    3. <span data-ttu-id="211a2-255">Убедитесь, что службы Skype для бизнеса Server 2015 остановлены на сервере переднего сервера.</span><span class="sxs-lookup"><span data-stu-id="211a2-255">Ensure Skype for Business Server 2015 services are stopped on the Front End server.</span></span> 
        - <span data-ttu-id="211a2-256">Ex (Standard Edition): ```Stop-CsWindowsServices```</span><span class="sxs-lookup"><span data-stu-id="211a2-256">Ex (Standard Edition): ```Stop-CsWindowsServices```</span></span>
        - <span data-ttu-id="211a2-257">Ex (Enterprise Edition): ```Invoke-CsComputerFailover```</span><span class="sxs-lookup"><span data-stu-id="211a2-257">Ex (Enterprise Edition): ```Invoke-CsComputerFailover```</span></span>
    4. <span data-ttu-id="211a2-258">Остановка SQL установленных экземпляров</span><span class="sxs-lookup"><span data-stu-id="211a2-258">Stop the SQL instances installed from running</span></span> 
        - <span data-ttu-id="211a2-259">Ex: ```Get-Service 'MSSQL$RTCLOCAL' | Stop-Service```</span><span class="sxs-lookup"><span data-stu-id="211a2-259">Ex: ```Get-Service 'MSSQL$RTCLOCAL' | Stop-Service```</span></span>
        - <span data-ttu-id="211a2-260">Ex: ```Get-Service 'MSSQL$LYNCLOCAL' | Stop-Service```</span><span class="sxs-lookup"><span data-stu-id="211a2-260">Ex: ```Get-Service 'MSSQL$LYNCLOCAL' | Stop-Service```</span></span>
        - <span data-ttu-id="211a2-261">Ex (только Standard Edition): ```Get-Service 'MSSQL$RTC' | Stop-Service```</span><span class="sxs-lookup"><span data-stu-id="211a2-261">Ex (Standard Edition Only): ```Get-Service 'MSSQL$RTC' | Stop-Service```</span></span>
    5. <span data-ttu-id="211a2-262">Установите обновление.</span><span class="sxs-lookup"><span data-stu-id="211a2-262">Install the update.</span></span>
5. <span data-ttu-id="211a2-263">Обновив драйвер ODBC 11 для SQL Server включить поддержку TLS 1.2 (KB [3135244).](https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server)</span><span class="sxs-lookup"><span data-stu-id="211a2-263">Update ODBC Driver 11 for SQL Server to include support for TLS 1.2 (KB [3135244](https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server)).</span></span>
    1. <span data-ttu-id="211a2-264">Скачайте [драйвер ODBC 11 для SQL Server Windows.](https://www.microsoft.com/download/confirmation.aspx?id=36434)</span><span class="sxs-lookup"><span data-stu-id="211a2-264">Download [ODBC Driver 11 for SQL Server - Windows](https://www.microsoft.com/download/confirmation.aspx?id=36434).</span></span>
    2. <span data-ttu-id="211a2-265">Убедитесь, что службы Skype для бизнеса Server 2015 остановлены на сервере переднего сервера.</span><span class="sxs-lookup"><span data-stu-id="211a2-265">Ensure that Skype for Business Server 2015 services are stopped on the Front End server.</span></span>
        - <span data-ttu-id="211a2-266">Пример (Standard Edition): ```Stop-CsWindowsService```</span><span class="sxs-lookup"><span data-stu-id="211a2-266">Example (Standard Edition): ```Stop-CsWindowsService```</span></span>
        - <span data-ttu-id="211a2-267">Пример (Enterprise Edition): ```Invoke-CsComputerFailover```</span><span class="sxs-lookup"><span data-stu-id="211a2-267">Example (Enterprise Edition): ```Invoke-CsComputerFailover```</span></span>
    3. <span data-ttu-id="211a2-268">Установите обновление.</span><span class="sxs-lookup"><span data-stu-id="211a2-268">Install the update.</span></span>
6. <span data-ttu-id="211a2-269">Развернем необходимые ключи реестра.</span><span class="sxs-lookup"><span data-stu-id="211a2-269">Deploy prerequisite registry keys.</span></span>

### <a name="pre-requisite-registry-keys"></a><span data-ttu-id="211a2-270">Необходимые ключи реестра</span><span class="sxs-lookup"><span data-stu-id="211a2-270">Pre-requisite registry keys</span></span>

<span data-ttu-id="211a2-271">Скопируйте или в paste следующий тест в Блокноте и переименуйте TLSPreReq.reg или имя по вашему выбору, а затем импортируйте:</span><span class="sxs-lookup"><span data-stu-id="211a2-271">Copy/paste the following test into Notepad and rename TLSPreReq.reg or a name of your choice, then import:</span></span>

```console
Windows Registry Editor Version 5.00

[HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\.NETFramework\v2.0.50727]

"SchUseStrongCrypto"=dword:00000001

[HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\.NETFramework\v4.0.30319]

"SchUseStrongCrypto"=dword:00000001

[HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\.NETFramework\v2.0.50727]

"SchUseStrongCrypto"=dword:00000001

[HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\.NETFramework\v4.0.30319]

"SchUseStrongCrypto"=dword:00000001

[HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion\Internet Settings\WinHttp]

"DefaultSecureProtocols"=dword:00000AA0

[HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\Windows\CurrentVersion\Internet Settings\WinHttp]

"DefaultSecureProtocols"=dword:00000AA0

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\TLS 1.2]

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\TLS 1.2\Client]

"DisabledByDefault"=dword:00000000

"Enabled"=dword:00000001

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\TLS 1.2\Server]

"DisabledByDefault"=dword:00000000

"Enabled"=dword:00000001
```

<span data-ttu-id="211a2-272">Для SQL для пулов Enterprise Edition предварительные условия и отключение TLS должны рассматриваться как любые SQL обновления ОС; обратитесь к: [https://docs.microsoft.com/skypeforbusiness/manage/topology/patch-or-update-a-back-end-or-standard-edition-server](https://docs.microsoft.com/skypeforbusiness/manage/topology/patch-or-update-a-back-end-or-standard-edition-server)</span><span class="sxs-lookup"><span data-stu-id="211a2-272">For SQL back ends for Enterprise Edition Pools, prerequisites and TLS disable should be treated as any SQL or OS updates would; refer to: [https://docs.microsoft.com/skypeforbusiness/manage/topology/patch-or-update-a-back-end-or-standard-edition-server](https://docs.microsoft.com/skypeforbusiness/manage/topology/patch-or-update-a-back-end-or-standard-edition-server)</span></span>

<span data-ttu-id="211a2-273">Несмотря на то, что действия, необходимые для приложения и отключения TLS, можно объединить, мы настоятельно рекомендуем применить все предварительные условия, прежде чем при этом отключать TLS 1.0 и 1.1 на уровне операционной системы.</span><span class="sxs-lookup"><span data-stu-id="211a2-273">While both the prerequisite application and TLS disabling steps can be combined, we strongly recommend all prerequisites be applied before proceeding with disabling of TLS 1.0 and 1.1 at the operating system level.</span></span> <span data-ttu-id="211a2-274">Лучше всего подготовить среду путем развертывания всех необходимых условий, проверки правильности и правильности работы рабочих нагрузок, а затем позднее отключить TLS 1.0/1.1.</span><span class="sxs-lookup"><span data-stu-id="211a2-274">The best practice approach would be to prepare the environment by deploying all prerequisites, validating that workloads all function correctly and as expected, and then proceeding with TLS 1.0/1.1 disable at a later time.</span></span>

### <a name="disable-tls-10-and-11-via-registry-import"></a><span data-ttu-id="211a2-275">Отключение TLS 1.0 и 1.1 с помощью импорта реестра</span><span class="sxs-lookup"><span data-stu-id="211a2-275">Disable TLS 1.0 and 1.1 via registry import</span></span>

<span data-ttu-id="211a2-276">Прежде чем приступить к следующим шагам, убедитесь, что выполнены все необходимые условия *и обновлены Skype для бизнеса Server.*</span><span class="sxs-lookup"><span data-stu-id="211a2-276">Before you proceed with the next steps, *make sure you have completed all prerequisites and updated Skype for Business Servers*.</span></span>

<span data-ttu-id="211a2-277">Скопируйте следующий текст в файл Блокнота и переименуйте **его в TLSDisable.reg:**</span><span class="sxs-lookup"><span data-stu-id="211a2-277">Copy the following text into a Notepad file and rename it **TLSDisable.reg**:</span></span>

```console
Windows Registry Editor Version 5.00

[HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Cryptography\Configuration\SSL\00010002]

"Functions"="TLS_ECDHE_ECDSA_WITH_AES_256_GCM_SHA384_P384,TLS_ECDHE_ECDSA_WITH_AES_128_GCM_SHA256_P256,TLS_ECDHE_RSA_WITH_AES_256_GCM_SHA384_P384,TLS_ECDHE_RSA_WITH_AES_128_GCM_SHA256_P256,TLS_ECDHE_ECDSA_WITH_AES_256_CBC_SHA384_P384,TLS_ECDHE_ECDSA_WITH_AES_128_CBC_SHA256_P256,TLS_ECDHE_RSA_WITH_AES_256_CBC_SHA384_P384,TLS_ECDHE_RSA_WITH_AES_128_CBC_SHA256_P256,TLS_RSA_WITH_AES_256_GCM_SHA384,TLS_RSA_WITH_AES_128_GCM_SHA256,TLS_RSA_WITH_AES_256_CBC_SHA256,TLS_RSA_WITH_AES_128_CBC_SHA256"

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL]

"AllowInsecureRenegoClients"=dword:00000000

"AllowInsecureRenegoServers"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Ciphers]

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Ciphers\AES 128/128]

"Enabled"=dword:FFFFFFFF

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Ciphers\AES 256/256]

"Enabled"=dword:FFFFFFFF

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Ciphers\DES 56/56]

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Ciphers\NULL]

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Ciphers\RC2 128/128]

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Ciphers\RC2 40/128]

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Ciphers\RC2 56/128]

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Ciphers\RC2 56/56]

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Ciphers\RC4 128/128]

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Ciphers\RC4 40/128]

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Ciphers\RC4 56/128]

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Ciphers\RC4 64/128]

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Ciphers\Triple DES 168]

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Hashes]

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Hashes\MD5]

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Hashes\SHA]

"Enabled"=dword:FFFFFFFF

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Hashes\SHA256]

"Enabled"=dword:FFFFFFFF

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Hashes\SHA384]

"Enabled"=dword:FFFFFFFF

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Hashes\SHA512]

"Enabled"=dword:FFFFFFFF

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\KeyExchangeAlgorithms]

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\KeyExchangeAlgorithms\Diffie-Hellman]

"Enabled"=dword:FFFFFFFF

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\KeyExchangeAlgorithms\ECDH]

"Enabled"=dword:FFFFFFFF

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\KeyExchangeAlgorithms\PKCS]

"Enabled"=dword:FFFFFFFF

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols]

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\Multi-Protocol Unified Hello]

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\Multi-Protocol Unified Hello\Client]

"DisabledByDefault"=dword:00000001

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\Multi-Protocol Unified Hello\Server]

"DisabledByDefault"=dword:00000001

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\PCT 1.0]

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\PCT 1.0\Client]

"DisabledByDefault"=dword:00000001

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\PCT 1.0\Server]

"DisabledByDefault"=dword:00000001

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\SSL 2.0]

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\SSL 2.0\Client]

"DisabledByDefault"=dword:00000001

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\SSL 2.0\Server]

"DisabledByDefault"=dword:00000001

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\SSL 3.0]

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\SSL 3.0\Client]

"DisabledByDefault"=dword:00000001

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\SSL 3.0\Server]

"DisabledByDefault"=dword:00000001

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\TLS 1.0]

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\TLS 1.0\Client]

"DisabledByDefault"=dword:00000001

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\TLS 1.0\Server]

"DisabledByDefault"=dword:00000001

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\TLS 1.1]

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\TLS 1.1\Client]

"DisabledByDefault"=dword:00000001

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\TLS 1.1\Server]

"DisabledByDefault"=dword:00000001

"Enabled"=dword:00000000
```

<span data-ttu-id="211a2-278">Импортировать REG-файл на каждый сервер, для которых необходимо отключить TLS 1.0 и 1.1.</span><span class="sxs-lookup"><span data-stu-id="211a2-278">Import the .reg file on each server you wish to disable TLS 1.0 and 1.1.</span></span> <span data-ttu-id="211a2-279">Перезагрузите сервер.</span><span class="sxs-lookup"><span data-stu-id="211a2-279">Reboot the server.</span></span> <span data-ttu-id="211a2-280">После того как службы снова будут в сети, переходить на следующий сервер.</span><span class="sxs-lookup"><span data-stu-id="211a2-280">Once the services have come back online, move to the next server.</span></span> <span data-ttu-id="211a2-281">Подход к пулам Enterprise Edition тот же, что и для любого обновления ОС.</span><span class="sxs-lookup"><span data-stu-id="211a2-281">The approach for Enterprise Edition Pools is the same you would take for any OS update.</span></span>

<span data-ttu-id="211a2-282">Вы могли заметить, что мы не просто отключаем TLS 1.0 и 1.1.</span><span class="sxs-lookup"><span data-stu-id="211a2-282">You may have noticed we are doing more than just disabling TLS 1.0 and 1.1 here.</span></span> <span data-ttu-id="211a2-283">Мы поддерживаем переупорядочение cipher Suite (как показано выше) и отключение некоторых старых слабых шифров.</span><span class="sxs-lookup"><span data-stu-id="211a2-283">We are supporting Cipher Suite re-order (as shown above) and the disabling of some older weak ciphers.</span></span> <span data-ttu-id="211a2-284">Это первый раз, когда мы официально поддерживаем эти изменения В SCHANNEL и Crypto API в Skype для бизнеса Server, и важно отметить, что эти изменения поддерживаются и протестированы на данный момент.</span><span class="sxs-lookup"><span data-stu-id="211a2-284">This is the first time we have officially supported these changes to SCHANNEL and Crypto API on Skype for Business Server, and it is important to note that these changes are the only ones we support and have tested at this time.</span></span> <span data-ttu-id="211a2-285">В будущем мы можем рассмотреть дополнительные конфигурации, но пока не изменяйте файл импорта реестра в вашей реализации.</span><span class="sxs-lookup"><span data-stu-id="211a2-285">We may consider additional configurations in the future, but for now, please do not modify the registry import file in your implementation.</span></span>

### <a name="validate-that-workloads-are-functioning-as-expected"></a><span data-ttu-id="211a2-286">Проверка правильной работы рабочих нагрузок</span><span class="sxs-lookup"><span data-stu-id="211a2-286">Validate that workloads are functioning as expected</span></span>

<span data-ttu-id="211a2-287">После отключения TLS 1.0 и 1.1 убедитесь, что все основные рабочие нагрузки работают должным образом, например мгновенные & Присутствия, вызовы P2P, Корпоративная голосовая связь и т. д.</span><span class="sxs-lookup"><span data-stu-id="211a2-287">Once TLS 1.0 and 1.1 have been disabled in your environment, ensure that all your main workloads are functioning as expected, such as IM & Presence, P2P calls, Enterprise Voice, etc.</span></span>

<span data-ttu-id="211a2-288">**Проверка использования только TLS 1.2**</span><span class="sxs-lookup"><span data-stu-id="211a2-288">**Validate only TLS 1.2 is being used**</span></span>

<span data-ttu-id="211a2-289">Команда безопасности должна выполнить новый аудит трафика Skype для бизнеса, чтобы убедиться, что более старые протоколы TLS 1.0 и 1.1 больше не используются.</span><span class="sxs-lookup"><span data-stu-id="211a2-289">Have your Security Team perform a new audit of Skype for Business traffic to ensure that the older protocols TLS 1.0 and 1.1 are no longer in use.</span></span>

<span data-ttu-id="211a2-290">Кроме того, вы можете использовать Internet Explorer для тестирования подключений TLS к веб-службам Из Skype для бизнеса Server 2015 после отключения TLS 1.0 и TLS 1.1.</span><span class="sxs-lookup"><span data-stu-id="211a2-290">Alternatively, you can use Internet Explorer to test TLS connections to web services from Skype for Business Server 2015 after TLS 1.0 and TLS 1.1 have been disabled.</span></span>

1. <span data-ttu-id="211a2-291">Запустите Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="211a2-291">Launch Internet Explorer.</span></span>
2. <span data-ttu-id="211a2-292">Выберите **"Инструменты:**  >  **интернет-параметры".**</span><span class="sxs-lookup"><span data-stu-id="211a2-292">Select **Tools** > **Internet Options**.</span></span>
3. <span data-ttu-id="211a2-293">Выберите **вкладку "Дополнительные".**</span><span class="sxs-lookup"><span data-stu-id="211a2-293">Select the **Advanced** tab.</span></span>
4. <span data-ttu-id="211a2-294">В **области "Параметры"** прокрутите страницу вниз.</span><span class="sxs-lookup"><span data-stu-id="211a2-294">Under **Settings**, scroll to the bottom.</span></span>
5. <span data-ttu-id="211a2-295">Убедитесь, что включены TLS 1.0, TLS 1.1 и TLS 1.2.</span><span class="sxs-lookup"><span data-stu-id="211a2-295">Verify that TLS 1.0, TLS 1.1, and TLS 1.2 are enabled.</span></span>
6. <span data-ttu-id="211a2-296">Перейдите по URL-адресу внутренней веб-службы пула SfB 2015 (должно быть успешно подключено).</span><span class="sxs-lookup"><span data-stu-id="211a2-296">Browse the Internal Web Service URL of your SfB 2015 pool (should connect successfully).</span></span>
7. <span data-ttu-id="211a2-297">Вернуться в Internet Explorer и отключить параметр **"Использовать только TLS 1.2".**</span><span class="sxs-lookup"><span data-stu-id="211a2-297">Go back into Internet Explorer and disable the option to **Use TLS 1.2** only.</span></span>
8. <span data-ttu-id="211a2-298">Снова просмотрите URL-адрес внутренней веб-службы пула SfB 2015 (не удается подключиться).</span><span class="sxs-lookup"><span data-stu-id="211a2-298">Browse the Internal Web Service URL of your SfB 2015 pool again (should fail to connect).</span></span>

![Параметры интернета](../../media/internet-options.jpg)

## <a name="advanced-deployment-scenarios"></a><span data-ttu-id="211a2-300">Расширенные сценарии развертывания</span><span class="sxs-lookup"><span data-stu-id="211a2-300">Advanced deployment scenarios</span></span>

<span data-ttu-id="211a2-301">Поскольку для поддержки TLS 1.2 в Skype для бизнеса Server 2015 требуются некоторые предварительные условия для зависимостей, установка с RTM-носителя не будет работать в любой системе, где отключены TLS 1.0 и 1.1.</span><span class="sxs-lookup"><span data-stu-id="211a2-301">Because some dependency prerequisites are required to support TLS 1.2 in Skype for Business Server 2015, installing from RTM media will fail on any system where TLS 1.0 and 1.1 have been disabled.</span></span>

<span data-ttu-id="211a2-302">**Развертывание новых серверов Standard Edition или пулов Enterprise Edition после отключения TLS 1.0 и 1.1 в среде.**</span><span class="sxs-lookup"><span data-stu-id="211a2-302">**Deploying New Standard Edition Servers or Enterprise Edition Pools once TLS 1.0 and 1.1 have been disabled in your environment.**</span></span>

<span data-ttu-id="211a2-303">**Вариант 1:** Используйте [SmartSetup.](../../deploy/install/install-skype-for-business-server.md)</span><span class="sxs-lookup"><span data-stu-id="211a2-303">**Option 1:** Use [SmartSetup](../../deploy/install/install-skype-for-business-server.md).</span></span> <span data-ttu-id="211a2-304">Обратите внимание, что мы обновляем SmartSetup с учетом обновленных SQL в будущем cu и обновим эту статью в будущем.</span><span class="sxs-lookup"><span data-stu-id="211a2-304">Note that we are updating SmartSetup to accommodate the updated SQL binaries in a future CU, and will update this article in the future.</span></span>

<span data-ttu-id="211a2-305">**Вариант 2:** Предварительная установка локальных SQL (RTCLOCAL и LYNCLOCAL)</span><span class="sxs-lookup"><span data-stu-id="211a2-305">**Option 2:** Pre-install local SQL instances (RTCLOCAL and LYNCLOCAL)</span></span>

1. <span data-ttu-id="211a2-306">Скачайте и скопируйте SQL Express 2014 SP2 (SQLEXPR_x64.exe) в локализованную папку на fe.</span><span class="sxs-lookup"><span data-stu-id="211a2-306">Download and copy SQL Express 2014 SP2 (SQLEXPR_x64.exe) to local folder on FE.</span></span> <span data-ttu-id="211a2-307">Допустим, путь к папке <SQL_FOLDER_PATH>.</span><span class="sxs-lookup"><span data-stu-id="211a2-307">Let’s say folder path <SQL_FOLDER_PATH>.</span></span>
2. <span data-ttu-id="211a2-308">Запустите PowerShell или командную <SQL_FOLDER_PATH>.</span><span class="sxs-lookup"><span data-stu-id="211a2-308">Launch PowerShell or Command Prompt and navigate to <SQL_FOLDER_PATH>.</span></span>
3. <span data-ttu-id="211a2-309">Создайте экземпляр RTCLOCAL SQL с помощью приведенной ниже команды.</span><span class="sxs-lookup"><span data-stu-id="211a2-309">Create the RTCLOCAL SQL instance by running the command below.</span></span> <span data-ttu-id="211a2-310">Подождите, SQLEXPR_x64.exe завершится, прежде чем ировать:</span><span class="sxs-lookup"><span data-stu-id="211a2-310">Wait until SQLEXPR_x64.exe finishes before proceeding:</span></span>

    <span data-ttu-id="211a2-311">SQLEXPR_x64.exe /Q /IACCEPTSQLSERVERLICENSETERMS /UPDATEENABLED=0 /HIDECONSOLE /ACTION=Install /FEATURES=SQLEngine,Tools /INSTANCENAME=RTCLOCAL /TCPENABLED=1 /SQLSVCACCOUNT="NT AUTHORITY\NetworkService" /SQLSYSADMINACCOUNTS="Builtin\Administrators" /BROWSERSVCSTARTUPTYPE="Automatic" /AGTSVCACCOUNT="NTAUTHORITY\NetworkService" /SQLSVCSTARTUPTYPE=Automati</span><span class="sxs-lookup"><span data-stu-id="211a2-311">SQLEXPR_x64.exe  /Q /IACCEPTSQLSERVERLICENSETERMS /UPDATEENABLED=0 /HIDECONSOLE /ACTION=Install /FEATURES=SQLEngine,Tools /INSTANCENAME=RTCLOCAL /TCPENABLED=1 /SQLSVCACCOUNT="NT AUTHORITY\NetworkService" /SQLSYSADMINACCOUNTS="Builtin\Administrators" /BROWSERSVCSTARTUPTYPE="Automatic" /AGTSVCACCOUNT="NTAUTHORITY\NetworkService" /SQLSVCSTARTUPTYPE=Automati</span></span>
1. <span data-ttu-id="211a2-312">Создайте экземпляр LYNCLOCAL SQL с помощью приведенной ниже команды.</span><span class="sxs-lookup"><span data-stu-id="211a2-312">Create the LYNCLOCAL SQL instance by running the command below.</span></span> <span data-ttu-id="211a2-313">Дождись SQLEXPR_x64.exe завершения, прежде чем ступить к следующему шагу:</span><span class="sxs-lookup"><span data-stu-id="211a2-313">Wait until SQLEXPR_x64.exe finishes before proceeding to the next step:</span></span>

    <span data-ttu-id="211a2-314">SQLEXPR_x64.exe /Q /IACCEPTSQLSERVERLICENSETERMS /UPDATEENABLED=0 /HIDECONSOLE /ACTION=Install /FEATURES=SQLEngine,Tools /INSTANCENAME=LYNCLOCAL /TCPENABLED=1 /SQLSVCACCOUNT ="NT AUTHORITY\NetworkService" /SQLSYSADMINACCOUNTS="Builtin\Administrators" /BROWSERSVCSTARTUPTYPE="Automatic" /AGTSVCACCOUNT="NTAUTHORITY\NetworkService" /SQLSVCSTARTUPTYPE=Automatic</span><span class="sxs-lookup"><span data-stu-id="211a2-314">SQLEXPR_x64.exe /Q /IACCEPTSQLSERVERLICENSETERMS /UPDATEENABLED=0 /HIDECONSOLE /ACTION=Install /FEATURES=SQLEngine,Tools /INSTANCENAME=LYNCLOCAL /TCPENABLED=1 /SQLSVCACCOUNT="NT AUTHORITY\NetworkService" /SQLSYSADMINACCOUNTS="Builtin\Administrators" /BROWSERSVCSTARTUPTYPE="Automatic" /AGTSVCACCOUNT="NTAUTHORITY\NetworkService" /SQLSVCSTARTUPTYPE=Automatic</span></span>
1. <span data-ttu-id="211a2-315">Запустите установку Skype для бизнеса Server 2015 RTM.</span><span class="sxs-lookup"><span data-stu-id="211a2-315">Run Skype for Business Server 2015 RTM setup.</span></span>
2. <span data-ttu-id="211a2-316">Следуйте оставшимся шагам из раздела предварительных условий выше.</span><span class="sxs-lookup"><span data-stu-id="211a2-316">Follow the remaining steps from the prerequisites section above.</span></span>

<span data-ttu-id="211a2-317">**Вариант 3:** Вы также можете вручную заменить binaries в локальном каталоге установщика мультимедиа следующим образом:</span><span class="sxs-lookup"><span data-stu-id="211a2-317">**Option 3:** You may also manually replace binaries in a local installation media directory as follows:</span></span>

1. [<span data-ttu-id="211a2-318">Установка необходимых условий для Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="211a2-318">Install prerequisites for Skype for Business Server</span></span>](../../deploy/install/install-prerequisites.md)  
2. <span data-ttu-id="211a2-319">Установите .NET 4.7:</span><span class="sxs-lookup"><span data-stu-id="211a2-319">Install .NET 4.7:</span></span> 
      - <span data-ttu-id="211a2-320">**Примечание.** Мы впервые представили поддержку .NET 4.7 в Skype для бизнеса Server 2015 CU5 (6.0.9319.281).</span><span class="sxs-lookup"><span data-stu-id="211a2-320">**Note:** We first introduced support for .NET 4.7 in Skype for Business Server 2015 CU5 (6.0.9319.281).</span></span> <span data-ttu-id="211a2-321">Поэтому на последующих шагах ниже мы обновим основные компоненты перед основной установкой.</span><span class="sxs-lookup"><span data-stu-id="211a2-321">Therefore, in later steps below we will be updating Core Components prior to the main install.</span></span>
      - <span data-ttu-id="211a2-322">Скачать: https://www.microsoft.com/download/details.aspx?id=55167 .</span><span class="sxs-lookup"><span data-stu-id="211a2-322">Download: https://www.microsoft.com/download/details.aspx?id=55167.</span></span> 
      - <span data-ttu-id="211a2-323">Справка. [Программное обеспечение, которое должно быть установлено перед развертыванием Skype для бизнеса Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md#software-that-should-be-installed-before-a-skype-for-business-server-2015-deployment)</span><span class="sxs-lookup"><span data-stu-id="211a2-323">Reference: [Software that should be installed before a Skype for Business Server 2015 deployment](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md#software-that-should-be-installed-before-a-skype-for-business-server-2015-deployment)</span></span>
3. <span data-ttu-id="211a2-324">Копирование ISO-файлов и папок:</span><span class="sxs-lookup"><span data-stu-id="211a2-324">Copy ISO Files/Folders:</span></span> 
    - <span data-ttu-id="211a2-325">При присоединении ISO-файла Skype для бизнеса Server 2015 откройте корневой каталог диска, вложенного в него (например, D: \) в проводнике.</span><span class="sxs-lookup"><span data-stu-id="211a2-325">With the Skype for Business Server 2015 ISO attached, open the root directory of the drive it is attached as (Ex: D:\) in File Explorer.</span></span>
    - <span data-ttu-id="211a2-326">Скопируйте все папки и файлы в папку на локальном диске (например, C:\SkypeForBusiness2015ISO).</span><span class="sxs-lookup"><span data-stu-id="211a2-326">Copy all folders and files to a folder on a local disk (Ex: C:\SkypeForBusiness2015ISO).</span></span>
    - <span data-ttu-id="211a2-327">**Примечание.** Перед установкой компонентов необходимо обновить некоторые файлы для поддержки TLS 1.2.</span><span class="sxs-lookup"><span data-stu-id="211a2-327">**Note:** Prior to installing components, some files will need to be updated for support of TLS 1.2.</span></span>
4. <span data-ttu-id="211a2-328">Замените пакеты MSI/EXE:</span><span class="sxs-lookup"><span data-stu-id="211a2-328">Replace MSI/EXE Packages:</span></span> 
    - <span data-ttu-id="211a2-329">Замените существующие пакеты MSI и EXE в папке /Setup/amd64/ установщика на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="211a2-329">Replace the existing MSI and EXE packages in the /Setup/amd64/ folder of the installation media on the local machine.</span></span>
    - <span data-ttu-id="211a2-330">SQL 2014 SP2 Express: https://www.microsoft.com/download/details.aspx?id=53167</span><span class="sxs-lookup"><span data-stu-id="211a2-330">SQL 2014 SP2 Express: https://www.microsoft.com/download/details.aspx?id=53167</span></span> 
        - <span data-ttu-id="211a2-331">Переименуем SQLEXPR_x64 на локальном компьютере и замените существующий файл в папке Setup/amd64/ установщика.</span><span class="sxs-lookup"><span data-stu-id="211a2-331">Rename to SQLEXPR_x64 on the local machine, and replace the existing file in the Setup/amd64/ folder of the installation media.</span></span>
    - <span data-ttu-id="211a2-332">SQL Native Client: https://www.microsoft.com/download/details.aspx?id=50402</span><span class="sxs-lookup"><span data-stu-id="211a2-332">SQL Native Client: https://www.microsoft.com/download/details.aspx?id=50402</span></span> 
        - <span data-ttu-id="211a2-333">**Примечание.** При необходимости переименуем его, чтобы sqlncli.msi, а затем замените существующий файл, существующий в папке Setup/amd64/ установщика.</span><span class="sxs-lookup"><span data-stu-id="211a2-333">**Note:** Rename this if necessary to sqlncli.msi, and then replace the existing file that exists in the Setup/amd64/ folder of the installation media.</span></span>
    - <span data-ttu-id="211a2-334">SQL объектов управления: https://www.microsoft.com/download/details.aspx?id=53164</span><span class="sxs-lookup"><span data-stu-id="211a2-334">SQL Management Objects: https://www.microsoft.com/download/details.aspx?id=53164</span></span> 
        - <span data-ttu-id="211a2-335">**Примечание.** Пакет функций будет иметь множество элементов, которые можно скачать.</span><span class="sxs-lookup"><span data-stu-id="211a2-335">**Note:** The Feature pack will have a lot of items that can be downloaded.</span></span> <span data-ttu-id="211a2-336">Выберите для скачивания только SharedManagementObjects.msi.</span><span class="sxs-lookup"><span data-stu-id="211a2-336">Select to download SharedManagementObjects.msi only.</span></span>
        - <span data-ttu-id="211a2-337">**Примечание.** Замените существующий файл, существующий в папке Setup/amd64/ установщика.</span><span class="sxs-lookup"><span data-stu-id="211a2-337">**Note:** Replace the existing file that exists in the Setup/amd64/ folder of the installation media.</span></span>
    - <span data-ttu-id="211a2-338">SQL CLR: https://www.microsoft.com/download/details.aspx?id=53164</span><span class="sxs-lookup"><span data-stu-id="211a2-338">SQL CLR Types: https://www.microsoft.com/download/details.aspx?id=53164</span></span> 
        - <span data-ttu-id="211a2-339">**Примечание.** Пакет функций будет иметь множество элементов, которые можно скачать.</span><span class="sxs-lookup"><span data-stu-id="211a2-339">**Note:** The Feature pack will have a lot of items that can be downloaded.</span></span> <span data-ttu-id="211a2-340">Выберите для скачивания только CQLSysClrTypes.msi</span><span class="sxs-lookup"><span data-stu-id="211a2-340">Select to download CQLSysClrTypes.msi only</span></span>
        - <span data-ttu-id="211a2-341">**Примечание.** Замените существующий файл, существующий в папке Setup/amd64/ установщика.</span><span class="sxs-lookup"><span data-stu-id="211a2-341">**Note**: Replace the existing file that exists in the Setup/amd64/ folder of the installation media.</span></span>
5. <span data-ttu-id="211a2-342">Установите основные компоненты:</span><span class="sxs-lookup"><span data-stu-id="211a2-342">Install Core Components:</span></span> 
    - <span data-ttu-id="211a2-343">Запустите Setup.exe из папки Setup/amd64/ установщика.</span><span class="sxs-lookup"><span data-stu-id="211a2-343">Run Setup.exe from the Setup/amd64/ folder of the installation media.</span></span> <span data-ttu-id="211a2-344">Следуйте инструкциям по установке основных компонентов</span><span class="sxs-lookup"><span data-stu-id="211a2-344">Follow the instructions to install Core Components</span></span>
    - <span data-ttu-id="211a2-345">Закроем основные компоненты.</span><span class="sxs-lookup"><span data-stu-id="211a2-345">Close Core Components.</span></span>
6. <span data-ttu-id="211a2-346">Обновление основных компонентов:</span><span class="sxs-lookup"><span data-stu-id="211a2-346">Update Core Components:</span></span> 
    - <span data-ttu-id="211a2-347">Скачайте установщик обновлений Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="211a2-347">Download the Skype for Business Update Installer.</span></span>
    - <span data-ttu-id="211a2-348">Запустите установщик, чтобы обновить основные компоненты и установить счетчики производительности.</span><span class="sxs-lookup"><span data-stu-id="211a2-348">Run the installer to update Core Components and install the performance counters.</span></span>
    - <span data-ttu-id="211a2-349">**Примечание.** В выпуске CU6HF2 функция автоматического обновления в настоящее время устанавливается только до CU6.</span><span class="sxs-lookup"><span data-stu-id="211a2-349">**Note:** As of the release of CU6HF2, the auto-update feature currently only will install up to CU6.</span></span> <span data-ttu-id="211a2-350">Поэтому обновление необходимо запустить отдельно для обновления основных компонентов до версии 6.0.9319.516.</span><span class="sxs-lookup"><span data-stu-id="211a2-350">Therefore, the updater must be run separately to update Core Components to 6.0.9319.516.</span></span>
    - <span data-ttu-id="211a2-351">Справка: https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015</span><span class="sxs-lookup"><span data-stu-id="211a2-351">Reference: https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015</span></span>
7. <span data-ttu-id="211a2-352">Установка средств администрирования (необязательно):</span><span class="sxs-lookup"><span data-stu-id="211a2-352">Install Administrative Tools (Optional):</span></span> 
    - <span data-ttu-id="211a2-353">Будет устанавливаться клиент Microsoft SQL Server 2012 Native Client, объекты управления SQL Server 2014 (x64) и microsoft System CLR Types для SQL Server 2014 (x64) с использованием обновленных файлов.</span><span class="sxs-lookup"><span data-stu-id="211a2-353">This will install the Microsoft SQL Server 2012 Native Client, SQL Server 2014 Management Objects (x64), and Microsoft System CLR Types for SQL Server 2014 (x64) using the updated files.</span></span> <span data-ttu-id="211a2-354">Кроме того, построитель топологий и панель управления Skype для бизнеса Server 2015 будут доступны на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="211a2-354">Additionally, the Skype for Business Server 2015 Topology Builder and Control Panel will be available on the local machine.</span></span>
8. <span data-ttu-id="211a2-355">Установка локального магазина конфигурации (шаг 1):</span><span class="sxs-lookup"><span data-stu-id="211a2-355">Install Local Configuration Store (Step 1):</span></span> 
     - <span data-ttu-id="211a2-356">Откройте мастер развертывания, щелкните "Установить или обновить систему  Skype для бизнеса Server" и выберите "Выполнить на шаге 1. Установка локального магазина конфигурации".</span><span class="sxs-lookup"><span data-stu-id="211a2-356">Open the Deployment Wizard, click Install or Update Skype for Business Server System, and click on **Run** at Step 1: Install Local Configuration Store.</span></span>
     - <span data-ttu-id="211a2-357">Нажмите **кнопку** "Далее" в диалоговом окне "Установка **локального магазина** конфигураций".</span><span class="sxs-lookup"><span data-stu-id="211a2-357">Click **Next** in the **Install Local Configuration Store** dialog box.</span></span>
     <span data-ttu-id="211a2-358">![Диалоговое окно "Установка локального магазина конфигураций"](../../media/local-configuration-store.png)</span><span class="sxs-lookup"><span data-stu-id="211a2-358">![Install Local Configuration Store dialog box](../../media/local-configuration-store.png)</span></span>
     - <span data-ttu-id="211a2-359">Просмотрите результаты и убедитесь, что состояние задачи завершено.</span><span class="sxs-lookup"><span data-stu-id="211a2-359">Review the results, and ensure that the Task Status is Completed.</span></span> <span data-ttu-id="211a2-360">Просмотрите итоговую папку журнала, щелкнув **"Просмотреть журнал".**</span><span class="sxs-lookup"><span data-stu-id="211a2-360">Review the resulting log file by clicking **View Log**.</span></span>
     <span data-ttu-id="211a2-361">![Состояние задачи показывается как завершено](../../media/local-configuration-task-completed.png)</span><span class="sxs-lookup"><span data-stu-id="211a2-361">![Task status shows as Completed](../../media/local-configuration-task-completed.png)</span></span>
     - <span data-ttu-id="211a2-362">Нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="211a2-362">Click **Finish**.</span></span>
9. <span data-ttu-id="211a2-363">Настройка или удаление компонентов Skype для бизнеса Server (шаг 2):</span><span class="sxs-lookup"><span data-stu-id="211a2-363">Set up or remove Skype for Business Server Components (Step 2):</span></span>
    - <span data-ttu-id="211a2-364">Откройте мастер развертывания, щелкните "Установить или обновить  систему Skype для бизнеса **Server"** и выберите "Выполнить на шаге 2. Настройка или удаление компонентов Skype для бизнеса Server"</span><span class="sxs-lookup"><span data-stu-id="211a2-364">Open the Deployment Wizard, click **Install or Update Skype for Business Server System**, and click **Run** at Step 2: Set up or Remove Skype for Business Server Components</span></span>
    - <span data-ttu-id="211a2-365">Нажмите **кнопку** "Далее" в диалоговом окне "Настройка компонентов Skype для бизнеса Server".</span><span class="sxs-lookup"><span data-stu-id="211a2-365">Click **Next** in the Set Up Skype for Business Server Components dialog box.</span></span>
    <span data-ttu-id="211a2-366">![Окно "Настройка компонентов Skype для бизнеса Server"](../../media/set-up-skype-for-business-server-components-window.png)</span><span class="sxs-lookup"><span data-stu-id="211a2-366">![the Set Up Skype for Business Server Components window](../../media/set-up-skype-for-business-server-components-window.png)</span></span>
    - <span data-ttu-id="211a2-367">Просмотрите журнал с помощью журнала просмотра и проверьте, что установка завершена без проблем.</span><span class="sxs-lookup"><span data-stu-id="211a2-367">Review the log using View Log, and validate that setup completed without issues.</span></span> 
    - <span data-ttu-id="211a2-368">Нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="211a2-368">Click **Finish**.</span></span>
10. <span data-ttu-id="211a2-369">При необходимости продолжите дополнительную установку и настройку (на этом этапе можно возобновить обычные процедуры установки).</span><span class="sxs-lookup"><span data-stu-id="211a2-369">Proceed with additional installation and configuration as required (you can resume normal installation procedures at this point).</span></span>
