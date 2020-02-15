---
title: Отключение протокола TLS 1.0/1.1 в Skype для бизнеса Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: ab748733-6bad-4c93-8dda-db8d5271653d
description: 'Сводка: подготовка и реализация отключения TLS 1,0 и 1,1 в средах.'
ms.openlocfilehash: 0a25060463ed3b67db8ca523171c2bc48660293d
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42012752"
---
# <a name="disable-tls-1011-in-skype-for-business-server-2015"></a><span data-ttu-id="2e52b-103">Отключение протокола TLS 1.0/1.1 в Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="2e52b-103">Disable TLS 1.0/1.1 in Skype for Business Server 2015</span></span>

<span data-ttu-id="2e52b-104">В этой статье представлены необходимые рекомендации по подготовке и реализации отключения TLS 1,0 и 1,1 в средах.</span><span class="sxs-lookup"><span data-stu-id="2e52b-104">The purpose of this article is to provide the necessary guidance for you to prepare for and implement disabling TLS 1.0 and 1.1 in your environments.</span></span> <span data-ttu-id="2e52b-105">Этот процесс требует тщательного планирования и подготовки.</span><span class="sxs-lookup"><span data-stu-id="2e52b-105">This process requires extensive planning and preparation.</span></span> <span data-ttu-id="2e52b-106">Внимательно изучите все сведения, приведенные в этой статье, как сделать план отключение TLS 1,0 и 1,1 для вашей организации.</span><span class="sxs-lookup"><span data-stu-id="2e52b-106">Please carefully review all of the information in this article as you make your plan to disable TLS 1.0 and 1.1 for your organization.</span></span> <span data-ttu-id="2e52b-107">Обратите внимание на то, что существует множество внешних зависимостей и условий подключения, которые могут быть затронуты при отключении TLS 1.0/1.1, поэтому рекомендуется использовать подробные сведения о планировании и тестировании.</span><span class="sxs-lookup"><span data-stu-id="2e52b-107">Note that there are many external dependencies and connectivity conditions that could be impacted by disabling TLS 1.0/1.1, so extensive planning and testing is warranted.</span></span>

## <a name="in-this-article"></a><span data-ttu-id="2e52b-108">В этой статье</span><span class="sxs-lookup"><span data-stu-id="2e52b-108">In this article</span></span>

- [<span data-ttu-id="2e52b-109">Фон и область</span><span class="sxs-lookup"><span data-stu-id="2e52b-109">Background and scope</span></span>](#background)
- [<span data-ttu-id="2e52b-110">Необходимые условия и процесс</span><span class="sxs-lookup"><span data-stu-id="2e52b-110">Prerequisites and process</span></span>](#prerequisites-and-process)
- [<span data-ttu-id="2e52b-111">Расширенные сценарии развертывания</span><span class="sxs-lookup"><span data-stu-id="2e52b-111">Advanced deployment scenarios</span></span>](#advanced-deployment-scenarios)

## <a name="background"></a><span data-ttu-id="2e52b-112">Общие сведения</span><span class="sxs-lookup"><span data-stu-id="2e52b-112">Background</span></span>

<span data-ttu-id="2e52b-113">Основными факторами для предоставления поддержки протоколов TLS 1,0 и 1,1 отключить поддержку протоколов локальной среды Skype для бизнеса Server являются отраслевые стандарты безопасности PCI и федеральные стандарты обработки информации.</span><span class="sxs-lookup"><span data-stu-id="2e52b-113">The primary drivers for providing TLS 1.0 and 1.1 disable support for Skype for Business Server On-Premises are Payment Card Industry (PCI) Security Standards Council and Federal Information Processing Standards requirements.</span></span> <span data-ttu-id="2e52b-114">Дополнительные сведения о требованиях PCI можно найти [здесь](https://blog.pcisecuritystandards.org/are-you-ready-for-30-june-2018-sayin-goodbye-to-ssl-early-tls).</span><span class="sxs-lookup"><span data-stu-id="2e52b-114">More information for PCI requirements can be found [here](https://blog.pcisecuritystandards.org/are-you-ready-for-30-june-2018-sayin-goodbye-to-ssl-early-tls).</span></span>  <span data-ttu-id="2e52b-115">Корпорация Майкрософт не может предоставить указания относительно того, требуется ли Организация для соблюдения этих или других требований.</span><span class="sxs-lookup"><span data-stu-id="2e52b-115">Microsoft cannot provide guidance on whether or not your organization is required to adhere to these or other requirements.</span></span> <span data-ttu-id="2e52b-116">Необходимо определить, требуется ли отключить TLS 1,0 и/или 1,1 в средах.</span><span class="sxs-lookup"><span data-stu-id="2e52b-116">You must determine if it is required for you to disable TLS 1.0 and/or 1.1 in your environments.</span></span>

<span data-ttu-id="2e52b-117">Корпорация Майкрософт [выпустила](https://cloudblogs.microsoft.com/microsoftsecure/2017/06/20/tls-1-2-support-at-microsoft/)технический документ по протоколу TLS, и мы также рекомендуем использовать фоновое чтение, доступное в данном [блоге Exchange](https://blogs.technet.microsoft.com/exchange/2018/01/26/exchange-server-tls-guidance-part-1-getting-ready-for-tls-1-2/).</span><span class="sxs-lookup"><span data-stu-id="2e52b-117">Microsoft has produced a white paper on TLS available [here](https://cloudblogs.microsoft.com/microsoftsecure/2017/06/20/tls-1-2-support-at-microsoft/), and we also recommend the background reading available in this [Exchange blog](https://blogs.technet.microsoft.com/exchange/2018/01/26/exchange-server-tls-guidance-part-1-getting-ready-for-tls-1-2/).</span></span>

## <a name="supportability-scope"></a><span data-ttu-id="2e52b-118">Область поддержки</span><span class="sxs-lookup"><span data-stu-id="2e52b-118">Supportability Scope</span></span>

<span data-ttu-id="2e52b-119">*Область* — это границы поддержки.</span><span class="sxs-lookup"><span data-stu-id="2e52b-119">*Scope* refers to supportability boundaries.</span></span> <span data-ttu-id="2e52b-120">*Полное тестирование и поддержка* означает, что мы полностью поддерживаем Отключение протокола TLS 1,0 и 1,1 для перечисленных версий продуктов.</span><span class="sxs-lookup"><span data-stu-id="2e52b-120">*Fully tested and supported* means we fully support and have tested disabling of TLS 1.0 and 1.1 for the listed product versions.</span></span> <span data-ttu-id="2e52b-121">*В настоящее время исследование* означает только то, что; Мы активно изучаем, как перевод этих продуктов в область для поддержки отключения TLS.</span><span class="sxs-lookup"><span data-stu-id="2e52b-121">*Currently being investigated* means just that; we are actively investigating bringing these products into scope for TLS disable support.</span></span> <span data-ttu-id="2e52b-122">*Вне области видимости* означает, что эти версии продуктов не поддерживают отключение протокола TLS 1,0 или 1,1 и не будут работать, с указанными исключениями.</span><span class="sxs-lookup"><span data-stu-id="2e52b-122">*Out of scope* means these product versions do not support disabling TLS 1.0 or 1.1 and will not work, with noted exceptions.</span></span>

### <a name="fully-tested-and-supported-servers"></a><span data-ttu-id="2e52b-123">Полностью протестированные и Поддерживаемые серверы</span><span class="sxs-lookup"><span data-stu-id="2e52b-123">Fully tested and supported servers</span></span>

- <span data-ttu-id="2e52b-124">Skype для бизнеса Server 2019 CU1 17.0.2046.123 (июнь 2019) или более поздней версии</span><span class="sxs-lookup"><span data-stu-id="2e52b-124">Skype for Business Server 2019 CU1 17.0.2046.123 (June 2019) or higher</span></span>
- <span data-ttu-id="2e52b-125">Skype для бизнеса Server 2015 CU9 6.0.9319.548 (Май 2019) или более поздней версии в Windows Server 2012 (с обновлением базы знаний [3140245](https://support.microsoft.com/help/3140245/update-to-enable-tls-1-1-and-tls-1-2-as-a-default-secure-protocols-in) или замены), 2012 R2 или 2016.</span><span class="sxs-lookup"><span data-stu-id="2e52b-125">Skype for Business Server 2015 CU9 6.0.9319.548 (May 2019) or higher on Windows Server 2012 (with KB [3140245](https://support.microsoft.com/help/3140245/update-to-enable-tls-1-1-and-tls-1-2-as-a-default-secure-protocols-in) or superseding update), 2012 R2 or 2016.</span></span>
- <span data-ttu-id="2e52b-126">Обновление для Skype для бизнеса Server 2015 на месте с помощью CU9 6.0.9319.548 (Май 2019) или более поздней версии в Windows Server 2008 R2, 2012 (с обновлением KB [3140245](https://support.microsoft.com/help/3140245/update-to-enable-tls-1-1-and-tls-1-2-as-a-default-secure-protocols-in) или обновлением для замены) или 2012 R2.</span><span class="sxs-lookup"><span data-stu-id="2e52b-126">In-place Upgraded Skype for Business Server 2015, with CU9 6.0.9319.548 (May 2019) or higher on Windows Server 2008 R2, 2012 (with KB [3140245](https://support.microsoft.com/help/3140245/update-to-enable-tls-1-1-and-tls-1-2-as-a-default-secure-protocols-in) or superseding update), or 2012 R2.</span></span>
- <span data-ttu-id="2e52b-127">Подключение к Exchange и Outlook Web App с Exchange Server 2010 с пакетом обновления 3 (SP3) RU19 или более поздней версии [, руководство](https://blogs.technet.microsoft.com/exchange/2018/01/26/exchange-server-tls-guidance-part-1-getting-ready-for-tls-1-2/)</span><span class="sxs-lookup"><span data-stu-id="2e52b-127">Exchange Connectivity and Outlook Web App with Exchange Server 2010 SP3 RU19 or higher, guidance [here](https://blogs.technet.microsoft.com/exchange/2018/01/26/exchange-server-tls-guidance-part-1-getting-ready-for-tls-1-2/)</span></span>
- <span data-ttu-id="2e52b-128">Устройство для обеспечения связи в филиалах (SBA) с помощью Skype для бизнеса Server 2015 CU6 HF2 или более поздней версии (уточните у поставщика, что они упакованы в обновления аппропиате и сделаны доступными для вашего устройства).</span><span class="sxs-lookup"><span data-stu-id="2e52b-128">Survivable Branch Appliance (SBA) with Skype for Business Server 2015 CU6 HF2 or higher (confirm with your vendor that they packaged the appropiate updates and have been made available for your appliance)</span></span>
- <span data-ttu-id="2e52b-129">Сервер для обеспечения связи в филиалах (SBS) с Skype для бизнеса Server 2015 CU6 HF2 или более поздней версии</span><span class="sxs-lookup"><span data-stu-id="2e52b-129">Survivable Branch Server (SBS) with Skype for Business Server 2015 CU6 HF2 or higher</span></span>
- <span data-ttu-id="2e52b-130">Lync Server 2013 **только пограничная роль**, это связано с тем, что пограничная роль не зависит от Windows Fabric 1,0.</span><span class="sxs-lookup"><span data-stu-id="2e52b-130">Lync Server 2013 **Edge Role Only**, this is because Edge role does not have a dependency on Windows Fabric 1.0.</span></span>

### <a name="fully-tested-and-supported-clients"></a><span data-ttu-id="2e52b-131">Полностью протестированные и поддерживаемые клиенты</span><span class="sxs-lookup"><span data-stu-id="2e52b-131">Fully tested and supported clients</span></span>

- <span data-ttu-id="2e52b-132">Клиентское приложение Lync 2013 (Skype для бизнеса) для настольных ПК, MSI и C2R, включая базовые [15.0.5023.1000 и более поздние версии](https://support.microsoft.com/help/4018334/april-3-2018-update-for-skype-for-business-2015-lync-2013-kb4018334)</span><span class="sxs-lookup"><span data-stu-id="2e52b-132">Lync 2013 (Skype for Business) Desktop Client, MSI and C2R, including Basic [15.0.5023.1000 or higher](https://support.microsoft.com/help/4018334/april-3-2018-update-for-skype-for-business-2015-lync-2013-kb4018334)</span></span>
- <span data-ttu-id="2e52b-133">Клиент для настольных ПК Skype для бизнеса 2016, MSI [16.0.4678.1000 или более поздней версии](https://support.microsoft.com/help/4018323/april-3-2018-update-for-skype-for-business-2016-kb4018323), включая Basic</span><span class="sxs-lookup"><span data-stu-id="2e52b-133">Skype for Business 2016 Desktop Client, MSI [16.0.4678.1000 or higher](https://support.microsoft.com/help/4018323/april-3-2018-update-for-skype-for-business-2016-kb4018323), including Basic</span></span>
- <span data-ttu-id="2e52b-134">Skype для бизнеса 2016 щелкните, чтобы запустить требуется обновление за [апрель 2018](https://docs.microsoft.com/officeupdates/release-notes-office365-proplus) :</span><span class="sxs-lookup"><span data-stu-id="2e52b-134">Skype for Business 2016 Click to Run Require the [April 2018](https://docs.microsoft.com/officeupdates/release-notes-office365-proplus) Updates:</span></span> 
    - <span data-ttu-id="2e52b-135">Ежемесячное и полугодое целевое значение\.,\.16\.0 9126 2152 или выше</span><span class="sxs-lookup"><span data-stu-id="2e52b-135">Monthly and Semi-Annual Targeted, 16\.0\.9126\.2152 or higher</span></span>
    - <span data-ttu-id="2e52b-136">Половина ежегодного и отложенного канала, 16\.0\.8431\.2242 или выше</span><span class="sxs-lookup"><span data-stu-id="2e52b-136">Semi-Annual and Deferred Channel, 16\.0\.8431\.2242 or higher</span></span>
- <span data-ttu-id="2e52b-137">Skype для бизнеса на Mac 16,15 или более поздней версии</span><span class="sxs-lookup"><span data-stu-id="2e52b-137">Skype for Business on Mac 16.15 or higher</span></span>
- <span data-ttu-id="2e52b-138">Skype для бизнеса для iOS и Android 6,19 или более поздней версии</span><span class="sxs-lookup"><span data-stu-id="2e52b-138">Skype for Business for iOS and Android 6.19 or higher</span></span>
- <span data-ttu-id="2e52b-139">Комнаты Microsoft Teams (ранее известной как SRS для системы комнат Skype v2) 4.0.64.0 (декабрь 2018) или более поздней версии</span><span class="sxs-lookup"><span data-stu-id="2e52b-139">Microsoft Teams Rooms (previously known as Skype Room System V2 SRS V2) 4.0.64.0 (December 2018) or higher</span></span>
- <span data-ttu-id="2e52b-140">Обновление Surface Hub для Team Edition на основе KB4499162 (Май 2019, сборка ОС 15063,1835) или более поздней версии</span><span class="sxs-lookup"><span data-stu-id="2e52b-140">Surface Hub update for Team edition based on KB4499162 (May 2019, OS Build 15063.1835) or higher</span></span>
- <span data-ttu-id="2e52b-141">Skype Web App 2015 CU6 HF2 или более поздней версии (поставляется с сервером)</span><span class="sxs-lookup"><span data-stu-id="2e52b-141">Skype Web App 2015 CU6 HF2 or higher (ships with Server)</span></span>

### <a name="currently-being-investigated"></a><span data-ttu-id="2e52b-142">В настоящее время выполняется исследование</span><span class="sxs-lookup"><span data-stu-id="2e52b-142">Currently being investigated</span></span>

- <span data-ttu-id="2e52b-143">Панель мониторинга качества звонков (Новая установка после TLS 1,0, 1,1 отключена, см. ниже) \*</span><span class="sxs-lookup"><span data-stu-id="2e52b-143">Call Quality Dashboard (new install after TLS 1.0, 1.1 have been disabled, see below)\*</span></span>
 
### <a name="out-of-scope"></a><span data-ttu-id="2e52b-144">Вне области поддержки</span><span class="sxs-lookup"><span data-stu-id="2e52b-144">Out of scope</span></span>

<span data-ttu-id="2e52b-145">За исключением случаев, когда отмечено, следующие продукты недоступны для поддержки отключения TLS 1.0/1.1 и не будут работать в среде, где отключен протокол TLS 1,0 и 1,1.</span><span class="sxs-lookup"><span data-stu-id="2e52b-145">Except where noted, the following products are not in scope for TLS 1.0/1.1 disable support and will not function in an environment where TLS 1.0 and 1.1 have been disabled.</span></span> <span data-ttu-id="2e52b-146">Что означает: Если вы по-прежнему можете использовать серверы или клиенты вне области, их необходимо обновить или удалить, если вам нужно отключить протокол TLS 1.0/1.1 в любом месте локального развертывания Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="2e52b-146">What this means: if you still utilize out-of-scope servers or clients, you must update or remove these if you need to disable TLS 1.0/1.1 anywhere in your Skype for Business Server on-premises deployment.</span></span>

- <span data-ttu-id="2e52b-147">Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2e52b-147">Lync Server 2013</span></span>
- <span data-ttu-id="2e52b-148">Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="2e52b-148">Lync Server 2010</span></span>
- <span data-ttu-id="2e52b-149">Windows Server 2008 или более ранняя</span><span class="sxs-lookup"><span data-stu-id="2e52b-149">Windows Server 2008 or lower</span></span>
- <span data-ttu-id="2e52b-150">Lync для Mac 2011</span><span class="sxs-lookup"><span data-stu-id="2e52b-150">Lync for Mac 2011</span></span>
- <span data-ttu-id="2e52b-151">Lync 2013 для мобильных устройств, iOS, iPad, Android и Windows Phone</span><span class="sxs-lookup"><span data-stu-id="2e52b-151">Lync 2013 for Mobile - iOS, iPad, Android or Windows Phone</span></span>
- <span data-ttu-id="2e52b-152">Клиент магазина Windows для Lync "MX"</span><span class="sxs-lookup"><span data-stu-id="2e52b-152">Lync "MX" Windows Store client</span></span>
- <span data-ttu-id="2e52b-153">Система комнат Lync (неизвестное</span><span class="sxs-lookup"><span data-stu-id="2e52b-153">Lync Room System (a.k.a.</span></span> <span data-ttu-id="2e52b-154">SRSv1).</span><span class="sxs-lookup"><span data-stu-id="2e52b-154">SRSv1).</span></span> <span data-ttu-id="2e52b-155">LRS достиг конца поддержки 9 октября 2018 и не будет обновлен для поддержки TLS 1,2.</span><span class="sxs-lookup"><span data-stu-id="2e52b-155">LRS reached end of support on October 9, 2018 and will not be updated to support TLS 1.2.</span></span>
- <span data-ttu-id="2e52b-156">Все клиенты Lync 2010</span><span class="sxs-lookup"><span data-stu-id="2e52b-156">All Lync 2010 clients</span></span>
- <span data-ttu-id="2e52b-157">Lync Phone Edition — обновленные [рекомендации.](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Certified-Skype-for-Business-Online-Phones-and-what-this-means/ba-p/120035)</span><span class="sxs-lookup"><span data-stu-id="2e52b-157">Lync Phone Edition - updated guidance [here](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Certified-Skype-for-Business-Online-Phones-and-what-this-means/ba-p/120035).</span></span>
- <span data-ttu-id="2e52b-158">Устройство для обеспечения связи в филиалах 2013 (SBA) или сервер для обеспечения связи в филиалах (SBS)</span><span class="sxs-lookup"><span data-stu-id="2e52b-158">2013 based Survivable Branch Appliance (SBA) or Survivable Branch Server (SBS)</span></span>
- <span data-ttu-id="2e52b-159">Cloud Connector Edition (CCE)</span><span class="sxs-lookup"><span data-stu-id="2e52b-159">Cloud Connector Edition (CCE)</span></span>
- <span data-ttu-id="2e52b-160">Skype для бизнеса для Windows Phone</span><span class="sxs-lookup"><span data-stu-id="2e52b-160">Skype for Business for Windows Phone</span></span>

### <a name="exceptions"></a><span data-ttu-id="2e52b-161">Исключения</span><span class="sxs-lookup"><span data-stu-id="2e52b-161">Exceptions</span></span>

#### <a name="lync-server-2013"></a><span data-ttu-id="2e52b-162">Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2e52b-162">Lync Server 2013</span></span>

<span data-ttu-id="2e52b-163">Lync Server 2013 использует зависимость от Windows Fabric версии 1,0.</span><span class="sxs-lookup"><span data-stu-id="2e52b-163">Lync Server 2013 takes a dependency on Windows Fabric version 1.0.</span></span>  <span data-ttu-id="2e52b-164">На этапе проектирования Lync Server 2013 была выбрана Windows Fabric 1,0 для своей привлекательной и новой распределенной архитектуры для обеспечения репликации, высокой доступности и отказоустойчивости.</span><span class="sxs-lookup"><span data-stu-id="2e52b-164">In the design phase for Lync Server 2013, Windows Fabric 1.0 was chosen for its compelling and new distributed architecture to provide replication, high availability, and fault tolerance.</span></span>  <span data-ttu-id="2e52b-165">Со временем Skype для бизнеса Server и Windows Fabric значительно улучшили эту совместную архитектуру с значительным повторным проектированием в последующих версиях.</span><span class="sxs-lookup"><span data-stu-id="2e52b-165">Over time, both Skype for Business Server and Windows Fabric have greatly improved this joint architecture with significant re-design in subsequent versions.</span></span>  <span data-ttu-id="2e52b-166">В качестве примера для текущего сервера Skype для бизнеса 2015 используется Windows Fabric 3,0.</span><span class="sxs-lookup"><span data-stu-id="2e52b-166">Current Skype for Business 2015 Server uses Windows Fabric 3.0, for example.</span></span>

<span data-ttu-id="2e52b-167">К сожалению, Windows Fabric 1,0 не **поддерживает TLS 1,2.  Тем не менее, Lync Server 2013 будет обновлен для работы с протоколом TLS 1,2**.</span><span class="sxs-lookup"><span data-stu-id="2e52b-167">Unfortunately, Windows Fabric 1.0 **does not support TLS 1.2.  However, we will be updating Lync Server 2013 to work with TLS 1.2**.</span></span> <span data-ttu-id="2e52b-168">Это будет присутствовать в следующем накопительном пакете обновления для Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="2e52b-168">This will be coming in the next Cumulative Update for Lync Server 2013.</span></span>  <span data-ttu-id="2e52b-169">Мы предоставляем поддержку протокола TLS 1,2, чтобы включить сценарии совместной работы, миграции, Федерации и гибридной среды.</span><span class="sxs-lookup"><span data-stu-id="2e52b-169">We're providing TLS 1.2 support to enable co-existence, migration, federation, and hybrid scenarios.</span></span>

<span data-ttu-id="2e52b-170">Если вашей организации требуется отключить TLS 1,0 и 1,1, и в настоящее время вы используете Lync Server 2013, рекомендуем начать процесс планирования с возможностью обновления на месте или параллельной миграции (новые пулы, перемещение пользователей) в Skype для Business Server 2015 или более поздней версии.</span><span class="sxs-lookup"><span data-stu-id="2e52b-170">If your organization is required to disable TLS 1.0 and 1.1, and you currently use Lync Server 2013, we recommend you begin your planning process, with the possibility you may have to In-place upgrade or Side-by-Side migrate (new pools, move users) to Skype for Business Server 2015 or higher.</span></span>  <span data-ttu-id="2e52b-171">Или вы можете ускорить переход на Skype для бизнеса Online.</span><span class="sxs-lookup"><span data-stu-id="2e52b-171">Or you may want to accelerate migration to Skype for Business Online.</span></span>

#### <a name="call-quality-dashboard"></a><span data-ttu-id="2e52b-172">Панель мониторинга качества звонка</span><span class="sxs-lookup"><span data-stu-id="2e52b-172">Call Quality Dashboard</span></span>

<span data-ttu-id="2e52b-173">Локальная панель мониторинга качества звонков в настоящее время зависит от протокола TLS 1,0 во время новой установки (при первом выполнении установки в локальной среде).</span><span class="sxs-lookup"><span data-stu-id="2e52b-173">On-Premises Call Quality Dashboard currently has a dependency on TLS 1.0 during new install (first time installing into your On-Premises environments).</span></span>  <span data-ttu-id="2e52b-174">В настоящее время мы изучаем эту проблему и планируем выпустить исправление в ближайшем будущем.</span><span class="sxs-lookup"><span data-stu-id="2e52b-174">We are currently investigating this issue and plan to release a fix in the near future.</span></span>  <span data-ttu-id="2e52b-175">Если вы планируете установить CQD, а также отключите TLS 1,0, рекомендуем сначала выполнить установку CQD, а затем перейдите к отключению TLS 1,0.</span><span class="sxs-lookup"><span data-stu-id="2e52b-175">If you are planning to install CQD and also disable TLS 1.0, we recommend that you complete CQD installation first, and then proceed with TLS 1.0 disabling.</span></span>

#### <a name="third-party-devices"></a><span data-ttu-id="2e52b-176">Сторонние устройства</span><span class="sxs-lookup"><span data-stu-id="2e52b-176">Third-party devices</span></span>

<span data-ttu-id="2e52b-177">На сторонних устройствах, таких как телефоны 3PIP, видеоконференций, обратные прокси-серверы и подсистемы балансировки нагрузки, обязательно проверьте поддержку протокола TLS 1,2, тщательно протестируйте и при необходимости обратитесь к поставщику.</span><span class="sxs-lookup"><span data-stu-id="2e52b-177">On third-party devices such as 3PIP phones, Video conferencing, Reverse Proxies and Load Balancers, be sure to validate TLS 1.2 supportability, test carefully, and contact the vendor if needed.</span></span>

### <a name="federation-considerations-when-disabling-tls-1011-on-edge-servers"></a><span data-ttu-id="2e52b-178">Рекомендации по Федерации при отключении TLS 1.0/1.1 на пограничных серверах</span><span class="sxs-lookup"><span data-stu-id="2e52b-178">Federation considerations when disabling TLS 1.0/1.1 on Edge servers</span></span>

<span data-ttu-id="2e52b-179">Необходимо тщательно спланировать и оценить влияние отключения TLS 1.0/1.1 на пограничных серверах.</span><span class="sxs-lookup"><span data-stu-id="2e52b-179">You must carefully plan for and consider the impact of disabling TLS 1.0/1.1 on your Edge servers.</span></span>  <span data-ttu-id="2e52b-180">После отключения протокола TLS 1,0 и 1,1 вы можете обнаружить, что другие организации не смогут выполнять Федерацию с вашей организацией.</span><span class="sxs-lookup"><span data-stu-id="2e52b-180">Once TLS 1.0 and 1.1 are disabled, you may find that other organizations are no longer be able to federate with your organization.</span></span>

<span data-ttu-id="2e52b-181">Вы можете отказаться от использования протоколов TLS 1.0/1.1 на пограничных серверах для обеспечения обратной совместимости с неисправленными (SfB 2015, Lync 2013) или более старыми (2010) внешними системами.</span><span class="sxs-lookup"><span data-stu-id="2e52b-181">You may opt to keep TLS 1.0/1.1 enabled on your Edge servers to maintain backward compatibility with non-patched (SfB 2015, Lync 2013) or older (2010) external systems.</span></span>

<span data-ttu-id="2e52b-182">Корпорация Майкрософт не может предоставить советы или рекомендации относительно того, попадает ли пограничная сеть (или любая сеть) в соответствии со стандартом PCI; , которые должны быть определены отдельной компанией.</span><span class="sxs-lookup"><span data-stu-id="2e52b-182">Microsoft cannot provide advice or recommendations on whether or not your Edge network (or any network) falls under PCI standard; that must be determined by the individual company.</span></span>

<span data-ttu-id="2e52b-183">Skype для бизнеса Online поддерживает протокол TLS 1,2 на сегодняшний день, поэтому не требуется воздействовать на гибридную среду/Федерацию с Online.</span><span class="sxs-lookup"><span data-stu-id="2e52b-183">Skype for Business Online is capable of TLS 1.2 today, so no impact to Hybrid/Federation with Online is expected.</span></span>

<span data-ttu-id="2e52b-184">PIC (общедоступное подключение к службе обмена мгновенными сообщениями) для службы потребителей Skype: мы не будем ожидать, что протокол TLS 1.0/1.1 не будет влиять на [Подключение Skype](../../deploy/deploy-skype-connectivity.md); Шлюзы Microsoft PIC уже поддерживают TLS 1,2.</span><span class="sxs-lookup"><span data-stu-id="2e52b-184">PIC (Public IM Connectivity) to Skype Consumer service: We do not expect disabling TLS 1.0/1.1 to impact [Skype Connectivity](../../deploy/deploy-skype-connectivity.md); Microsoft PIC Gateways are already TLS 1.2 capable.</span></span>

## <a name="prerequisites-and-process"></a><span data-ttu-id="2e52b-185">Необходимые условия и процесс</span><span class="sxs-lookup"><span data-stu-id="2e52b-185">Prerequisites and process</span></span>

<span data-ttu-id="2e52b-186">За исключением отмеченных выше случаев, когда протоколы TLS 1,0 и 1,1 отключены серверами, не включенными в область, клиенты и устройства будут работать правильно или вообще.</span><span class="sxs-lookup"><span data-stu-id="2e52b-186">Except where noted above, once TLS 1.0 and 1.1 are disabled out-of-scope servers, clients and devices will longer function properly, or at all.</span></span> <span data-ttu-id="2e52b-187">Это может означать, что необходимо приостановить и дождаться получения обновленных руководств от Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="2e52b-187">This may mean you need to pause and wait for updated guidance from Microsoft.</span></span> <span data-ttu-id="2e52b-188">После того как вы удовлетворены всеми требованиями и запланировать пропуски, продолжите.</span><span class="sxs-lookup"><span data-stu-id="2e52b-188">Once you are satisfied that you meet all requirements and have a plan to address gaps, proceed.</span></span>

<span data-ttu-id="2e52b-189">На высоком уровне, в то время как Skype для бизнеса Server 2019 готов к выполнению процедуры установки, Skype для бизнеса Server 2015 потребует установки CU9, применения предварительных обновлений к .NET и SQL, развертывания разделов реестра, необходимых для использования, и, наконец, отдельного Округление обновлений конфигурации ОС (например, отключение TLS 1,0 и 1,1 с помощью импорта файлов реестра).</span><span class="sxs-lookup"><span data-stu-id="2e52b-189">At a high level, while Skype for Business Server 2019 is ready for procedure at install, Skype for Business Server 2015 will require that you install CU9, applying pre-requisite updates to .NET and SQL, deploying prerequisite registry keys, and finally a separate round of OS configuration updates (i.e. disabling TLS 1.0 and 1.1 via registry file import).</span></span> <span data-ttu-id="2e52b-190">Критически важно полностью установить все необходимые компоненты, в том числе Skype для бизнеса Server 2015 CU6 HF2, перед отключением TLS 1,0 и 1,1 на любом сервере в вашей среде.</span><span class="sxs-lookup"><span data-stu-id="2e52b-190">It is critically important that you complete installation of all prerequisites, including Skype for Business Server 2015 CU6 HF2, prior to disabling TLS 1.0 and 1.1 on any server in your environment.</span></span> <span data-ttu-id="2e52b-191">Для каждого Skype для бизнеса Server, включая пограничные роли и SQL Server, требуются обновления.</span><span class="sxs-lookup"><span data-stu-id="2e52b-191">Every Skype for Business server, including Edge role and SQL Backends, requires the updates.</span></span> <span data-ttu-id="2e52b-192">Кроме того, убедитесь, что все поддерживаемые клиенты (в области) обновлены до требуемых минимальных версий.</span><span class="sxs-lookup"><span data-stu-id="2e52b-192">Also ensure that all supported (in-scope) clients have been updated to the required minimum versions.</span></span> <span data-ttu-id="2e52b-193">Не забудьте также обновить рабочие станции управления.</span><span class="sxs-lookup"><span data-stu-id="2e52b-193">Don’t forget to update management workstations as well.</span></span>

<span data-ttu-id="2e52b-194">Мы хотим подписаться к обычному порядку операций "Внутренняя часть" для обновления серверов Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="2e52b-194">We want to follow the usual order of operations of "inside out" for upgrading Skype for Business servers.</span></span> <span data-ttu-id="2e52b-195">Рассматриваете пулы директоров, сохраняемые чат и связанные пулы обычным образом.</span><span class="sxs-lookup"><span data-stu-id="2e52b-195">Treat Director pools, Persistent chat, and Paired Pools in the same manner you normally would.</span></span> <span data-ttu-id="2e52b-196">Порядок и методы обновления описаны [здесь](topology.md) и [здесь](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015).</span><span class="sxs-lookup"><span data-stu-id="2e52b-196">Order and methods for upgrade are covered [here](topology.md) and [here](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015).</span></span>

### <a name="high-level-process"></a><span data-ttu-id="2e52b-197">Процесс высокого уровня</span><span class="sxs-lookup"><span data-stu-id="2e52b-197">High-level process</span></span>

1. <span data-ttu-id="2e52b-198">Перед настройкой рабочих серверов протестируйте все действия, описанные в лаборатории.</span><span class="sxs-lookup"><span data-stu-id="2e52b-198">Test all steps in your lab prior to configuring production servers.</span></span>
2. <span data-ttu-id="2e52b-199">Создайте резервную копию и сохраните копию экспортируемого реестра на каждом отдельном сервере, который необходимо обновить.</span><span class="sxs-lookup"><span data-stu-id="2e52b-199">Back up and preserve a copy of exported registry on each and every individual server to be updated.</span></span> <span data-ttu-id="2e52b-200">Вы не можете обмениваться реестрами между серверами; они содержат уникальные ключи на уровне компьютера.</span><span class="sxs-lookup"><span data-stu-id="2e52b-200">You cannot share registries between servers; they contain unique machine-based keys.</span></span>
3. <span data-ttu-id="2e52b-201">Обновите все серверы Skype для бизнеса 2015 до CU9 или более поздней версии.</span><span class="sxs-lookup"><span data-stu-id="2e52b-201">Upgrade all Skype for Business 2015 servers to CU9 or higher.</span></span> <span data-ttu-id="2e52b-202">Для Skype для бизнеса Server 2019 выполните обновление до CU1 или более поздней версии.</span><span class="sxs-lookup"><span data-stu-id="2e52b-202">For Skype for Business Server 2019, upgrade to CU1 or higher.</span></span>
4. <span data-ttu-id="2e52b-203">Установите все необходимые компоненты на все серверы.</span><span class="sxs-lookup"><span data-stu-id="2e52b-203">Install all prerequisites to all servers.</span></span>
5. <span data-ttu-id="2e52b-204">Развертывайте разделы реестра, необходимые для использования.</span><span class="sxs-lookup"><span data-stu-id="2e52b-204">Deploy prerequisite registry keys.</span></span>
6. <span data-ttu-id="2e52b-205">Убедитесь, что все клиенты в области обновлены.</span><span class="sxs-lookup"><span data-stu-id="2e52b-205">Ensure that all in-scope clients are updated.</span></span>
7. <span data-ttu-id="2e52b-206">Отключите TLS 1,0 и 1,1 с помощью импорта реестра.</span><span class="sxs-lookup"><span data-stu-id="2e52b-206">Disable TLS 1.0 and 1.1 via registry import.</span></span>
8. <span data-ttu-id="2e52b-207">Убедитесь, что рабочие нагрузки работают должным образом.</span><span class="sxs-lookup"><span data-stu-id="2e52b-207">Validate that workloads are functioning as expected.</span></span>
    - <span data-ttu-id="2e52b-208">Если возникли проблемы, устраните неполадки и устраните или</span><span class="sxs-lookup"><span data-stu-id="2e52b-208">If problems are encountered, troubleshoot and resolve, or</span></span>
    - <span data-ttu-id="2e52b-209">Восстановление реестра из шага 2 для повторного включения TLS 1,0 и 1,1</span><span class="sxs-lookup"><span data-stu-id="2e52b-209">Restore registry from step 2 to re-enable TLS 1.0 and 1.1</span></span>
9. <span data-ttu-id="2e52b-210">Проверка того, что используется только протокол TLS 1,2.</span><span class="sxs-lookup"><span data-stu-id="2e52b-210">Validate that only TLS 1.2 is being used.</span></span>

### <a name="install-prerequisites-to-all-servers"></a><span data-ttu-id="2e52b-211">Установка необходимых компонентов для всех серверов</span><span class="sxs-lookup"><span data-stu-id="2e52b-211">Install prerequisites to all servers</span></span>

<span data-ttu-id="2e52b-212">Перед отключением протокола TLS 1,0 и 1,1 на уровне операционной системы в развертывании Skype для бизнеса Server 2015 необходимо выполнить полное обновление зависимости.</span><span class="sxs-lookup"><span data-stu-id="2e52b-212">Extensive dependency updating is required before you begin to disable TLS 1.0 and 1.1 at the operating system level in your Skype for Business Server 2015 deployments.</span></span> <span data-ttu-id="2e52b-213">Ниже приведены минимальные версии, поддерживающие TLS 1,2.</span><span class="sxs-lookup"><span data-stu-id="2e52b-213">The following are the minimum versions that can support TLS 1.2.</span></span> <span data-ttu-id="2e52b-214">Перед отключением TLS 1,0 и 1,1 разверните все необходимые обновления для каждого сервера Skype для бизнеса в вашей среде.</span><span class="sxs-lookup"><span data-stu-id="2e52b-214">Deploy all prerequisite updates across every Skype for Business server in your environment before you begin disabling TLS 1.0 and 1.1.</span></span>

- <span data-ttu-id="2e52b-215">Skype для бизнеса Server 2015 CU9 6.0.9319.548 (Май 2019) или более поздней версии</span><span class="sxs-lookup"><span data-stu-id="2e52b-215">Skype for Business Server 2015 CU9 6.0.9319.548 (May 2019) or higher</span></span>
- <span data-ttu-id="2e52b-216">[.NET Framework 4,7](https://www.microsoft.com/download/details.aspx?id=55167) или более поздней версии с включенной функцией SchUseStrongCrypto в реестре (приведенной ниже)</span><span class="sxs-lookup"><span data-stu-id="2e52b-216">[.NET Framework 4.7](https://www.microsoft.com/download/details.aspx?id=55167) or higher with SchUseStrongCrypto enabled in the registry (provided below)</span></span>
- <span data-ttu-id="2e52b-217">SQL должен быть обновлен на всех серверах Skype для бизнеса 2015 и в конце.</span><span class="sxs-lookup"><span data-stu-id="2e52b-217">SQL must be updated on all Skype for Business 2015 servers and backends.</span></span> <span data-ttu-id="2e52b-218">Сначала обновите SQL Server Enterprise Edition, а затем соответствующие Фес.</span><span class="sxs-lookup"><span data-stu-id="2e52b-218">Update Enterprise Edition Pool SQL Backends first, then their respective FEs.</span></span> 
    - <span data-ttu-id="2e52b-219">[SQL server 2014 с пакетом обновления 1 (SP1), CU5](https://support.microsoft.com/help/3130926), выше/sql Server 2012 (SP2) + CU16 или выше/ [SQL Server 2014 RTM + CU12](https://support.microsoft.com/help/3130923/cumulative-update-12-for-sql-server-2014)или выше/SQL Server 2014 с пакетом обновления 2 (SP2)</span><span class="sxs-lookup"><span data-stu-id="2e52b-219">[SQL Server 2014 SP1 + CU5](https://support.microsoft.com/help/3130926), or higher / SQL Server 2012 SP2 + CU16 or higher / [SQL Server 2014 RTM + CU12](https://support.microsoft.com/help/3130923/cumulative-update-12-for-sql-server-2014), or higher / SQL Server 2014 SP2</span></span>
     - [<span data-ttu-id="2e52b-220">Собственный клиент SQL Server для SQL Server 2012</span><span class="sxs-lookup"><span data-stu-id="2e52b-220">SQL Server Native Client for SQL Server 2012</span></span>](https://www.microsoft.com/download/details.aspx?id=50402)
     - <span data-ttu-id="2e52b-221">[Драйвер Microsoft ODBC 11 для SQL Server](https://www.microsoft.com/download/details.aspx?id=36434)или более поздней версии</span><span class="sxs-lookup"><span data-stu-id="2e52b-221">[Microsoft ODBC Driver 11 for SQL Server](https://www.microsoft.com/download/details.aspx?id=36434), or higher</span></span>
     - [<span data-ttu-id="2e52b-222">Общие объекты управления для SQL Server 2014 с пакетом обновления 2 (SP2)</span><span class="sxs-lookup"><span data-stu-id="2e52b-222">Shared Management Objects for SQL Server 2014 SP2</span></span>](https://www.microsoft.com/download/details.aspx?id=53164)
     - [<span data-ttu-id="2e52b-223">SQLSysClrTypes для SQL Server 2014 с пакетом обновления 2</span><span class="sxs-lookup"><span data-stu-id="2e52b-223">SQLSysClrTypes for SQL server 2014 SP2</span></span>](https://www.microsoft.com/download/details.aspx?id=42295)

### <a name="basic-steps-to-install-pre-requisites-in-recommended-order-of-operations"></a><span data-ttu-id="2e52b-224">Основные действия по установке предварительных требований в рекомендуемом порядке операций</span><span class="sxs-lookup"><span data-stu-id="2e52b-224">Basic steps to install pre-requisites, in recommended order of operations</span></span>

1. <span data-ttu-id="2e52b-225">Установите обновление CU9 для Skype для бизнеса Server на все серверы.</span><span class="sxs-lookup"><span data-stu-id="2e52b-225">Install the Skype for Business Server CU9 update to all servers.</span></span> 
    1. <span data-ttu-id="2e52b-226">Установите обновление для компонентов, использующих обновление.</span><span class="sxs-lookup"><span data-stu-id="2e52b-226">Install the update to components using the updater.</span></span>
    2. <span data-ttu-id="2e52b-227">Обновление баз данных в соответствии с документированными процедурами.</span><span class="sxs-lookup"><span data-stu-id="2e52b-227">Update databases according to documented procedures.</span></span> <span data-ttu-id="2e52b-228">Для Skype для бизнеса Server 2015, ознакомьтесь со статьей KB [3061064](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015).</span><span class="sxs-lookup"><span data-stu-id="2e52b-228">For Skype for Business Server 2015, see KB [3061064](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015).</span></span>
    3. <span data-ttu-id="2e52b-229">Проверка функциональности продукта в развертывании перед переходом с других изменений.</span><span class="sxs-lookup"><span data-stu-id="2e52b-229">Validate product functionality in the deployment prior to moving forward with any other changes.</span></span>
2. <span data-ttu-id="2e52b-230">Скачайте автономный установщик .NET 4,7.</span><span class="sxs-lookup"><span data-stu-id="2e52b-230">Download .NET 4.7 Offline Installer.</span></span> 
    1. <span data-ttu-id="2e52b-231">Ссылкой[https://www.microsoft.com/download/details.aspx?id=55167](https://www.microsoft.com/download/details.aspx?id=55167)</span><span class="sxs-lookup"><span data-stu-id="2e52b-231">Reference: [https://www.microsoft.com/download/details.aspx?id=55167](https://www.microsoft.com/download/details.aspx?id=55167)</span></span>
    2. <span data-ttu-id="2e52b-232">Убедитесь, что службы Skype для бизнеса Server 2015 на сервере переднего плана остановлены.</span><span class="sxs-lookup"><span data-stu-id="2e52b-232">Ensure that Skype for Business Server 2015 services are stopped on the Front End server.</span></span>
    3. <span data-ttu-id="2e52b-233">Ссылкой[https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015)</span><span class="sxs-lookup"><span data-stu-id="2e52b-233">Reference: [https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015)</span></span>
    4. <span data-ttu-id="2e52b-234">EX (стандартный выпуск):```Stop-CsWindowsService```</span><span class="sxs-lookup"><span data-stu-id="2e52b-234">Ex (Standard Edition): ```Stop-CsWindowsService```</span></span>
    5. <span data-ttu-id="2e52b-235">EX (корпоративный выпуск):```Invoke-CsComputerFailover```</span><span class="sxs-lookup"><span data-stu-id="2e52b-235">Ex (Enterprise Edition): ```Invoke-CsComputerFailover```</span></span>
    6. <span data-ttu-id="2e52b-236">Запустите пакет установщика.</span><span class="sxs-lookup"><span data-stu-id="2e52b-236">Run the installer package.</span></span>
    7. <span data-ttu-id="2e52b-237">Перезагрузите сервер.</span><span class="sxs-lookup"><span data-stu-id="2e52b-237">Reboot the server.</span></span>
3. <span data-ttu-id="2e52b-238">Обновите SQL Express 2014 на всех серверах.</span><span class="sxs-lookup"><span data-stu-id="2e52b-238">Update SQL Express 2014 on all servers.</span></span> 
    1. <span data-ttu-id="2e52b-239">Ссылкой[https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server](https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server)</span><span class="sxs-lookup"><span data-stu-id="2e52b-239">Reference: [https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server](https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server)</span></span>
    2. <span data-ttu-id="2e52b-240">Загрузка SQL 2014 с пакетом обновления 2</span><span class="sxs-lookup"><span data-stu-id="2e52b-240">Download SQL 2014 SP2</span></span> 
        - <span data-ttu-id="2e52b-241">Ссылкой[https://www.microsoft.com/download/details.aspx?id=53168](https://www.microsoft.com/download/details.aspx?id=53168)</span><span class="sxs-lookup"><span data-stu-id="2e52b-241">Reference: [https://www.microsoft.com/download/details.aspx?id=53168](https://www.microsoft.com/download/details.aspx?id=53168)</span></span>
    3. <span data-ttu-id="2e52b-242">Скопируйте установочный носитель в папку на сервере (пример: C:\ 01_2014SqlSp2).</span><span class="sxs-lookup"><span data-stu-id="2e52b-242">Copy the installation media to a folder on the server (Ex: C:\01_2014SqlSp2)</span></span>
    4. <span data-ttu-id="2e52b-243">Проверка остановки служб 2015 Skype для бизнеса Server на сервере переднего плана</span><span class="sxs-lookup"><span data-stu-id="2e52b-243">Ensure Skype for Business Server 2015 services are stopped on the Front End server</span></span> 
        - <span data-ttu-id="2e52b-244">EX (стандартный выпуск):```Stop-CsWindowsService```</span><span class="sxs-lookup"><span data-stu-id="2e52b-244">Ex (Standard Edition): ```Stop-CsWindowsService```</span></span>
        - <span data-ttu-id="2e52b-245">EX (корпоративный выпуск):```Invoke-CsComputerFailover```</span><span class="sxs-lookup"><span data-stu-id="2e52b-245">Ex (Enterprise Edition): ```Invoke-CsComputerFailover```</span></span>
    5. <span data-ttu-id="2e52b-246">Открытие командной строки администратора и обновление всех установленных компонентов и экземпляров</span><span class="sxs-lookup"><span data-stu-id="2e52b-246">Open an Admin Command Prompt, and upgrade all installed components and instances</span></span> 
        - <span data-ttu-id="2e52b-247">Пример: C:\ 01_2014SqlSp2 \SQLServer2014SP2-KB3171021-x64-ENU.exe/КС/Иакцептсклсерверлиценсетермс/Актион = Patch/Аллинстанцес</span><span class="sxs-lookup"><span data-stu-id="2e52b-247">Example: C:\01_2014SqlSp2\SQLServer2014SP2-KB3171021-x64-ENU.exe /qs /IAcceptSQLServerLicenseTerms /Action=Patch /AllInstances</span></span>
4. <span data-ttu-id="2e52b-248">Обновление собственного клиента SQL.</span><span class="sxs-lookup"><span data-stu-id="2e52b-248">Update SQL Native Client.</span></span> 
    1. <span data-ttu-id="2e52b-249">Ссылка: [https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server](https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server).</span><span class="sxs-lookup"><span data-stu-id="2e52b-249">Reference: [https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server](https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server).</span></span>
    2. <span data-ttu-id="2e52b-250">Загрузка из[https://www.microsoft.com/download/details.aspx?id=50402](https://www.microsoft.com/download/details.aspx?id=50402)</span><span class="sxs-lookup"><span data-stu-id="2e52b-250">Download from [https://www.microsoft.com/download/details.aspx?id=50402](https://www.microsoft.com/download/details.aspx?id=50402)</span></span>
    3. <span data-ttu-id="2e52b-251">Убедитесь, что на сервере переднего плана остановлены службы 2015 для Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="2e52b-251">Ensure Skype for Business Server 2015 services are stopped on the Front End server.</span></span> 
        - <span data-ttu-id="2e52b-252">EX (стандартный выпуск):```Stop-CsWindowsServices```</span><span class="sxs-lookup"><span data-stu-id="2e52b-252">Ex (Standard Edition): ```Stop-CsWindowsServices```</span></span>
        - <span data-ttu-id="2e52b-253">EX (корпоративный выпуск):```Invoke-CsComputerFailover```</span><span class="sxs-lookup"><span data-stu-id="2e52b-253">Ex (Enterprise Edition): ```Invoke-CsComputerFailover```</span></span>
    4. <span data-ttu-id="2e52b-254">Остановка выполнения экземпляров SQL</span><span class="sxs-lookup"><span data-stu-id="2e52b-254">Stop the SQL instances installed from running</span></span> 
        - <span data-ttu-id="2e52b-255">Пример```Get-Service 'MSSQL$RTCLOCAL' | Stop-Service```</span><span class="sxs-lookup"><span data-stu-id="2e52b-255">Ex: ```Get-Service 'MSSQL$RTCLOCAL' | Stop-Service```</span></span>
        - <span data-ttu-id="2e52b-256">Пример```Get-Service 'MSSQL$LYNCLOCAL' | Stop-Service```</span><span class="sxs-lookup"><span data-stu-id="2e52b-256">Ex: ```Get-Service 'MSSQL$LYNCLOCAL' | Stop-Service```</span></span>
        - <span data-ttu-id="2e52b-257">EX (только для выпуска Standard Edition):```Get-Service 'MSSQL$RTC' | Stop-Service```</span><span class="sxs-lookup"><span data-stu-id="2e52b-257">Ex (Standard Edition Only): ```Get-Service 'MSSQL$RTC' | Stop-Service```</span></span>
    5. <span data-ttu-id="2e52b-258">Установите обновление.</span><span class="sxs-lookup"><span data-stu-id="2e52b-258">Install the update.</span></span>
5. <span data-ttu-id="2e52b-259">Обновите драйвер ODBC 11 для SQL Server, чтобы включить поддержку протокола TLS 1,2 (KB [3135244](https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server)).</span><span class="sxs-lookup"><span data-stu-id="2e52b-259">Update ODBC Driver 11 for SQL Server to include support for TLS 1.2 (KB [3135244](https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server)).</span></span>
    1. <span data-ttu-id="2e52b-260">Скачайте [драйвер ODBC 11 для SQL Server — Windows](https://www.microsoft.com/download/confirmation.aspx?id=36434).</span><span class="sxs-lookup"><span data-stu-id="2e52b-260">Download [ODBC Driver 11 for SQL Server - Windows](https://www.microsoft.com/download/confirmation.aspx?id=36434).</span></span>
    2. <span data-ttu-id="2e52b-261">Убедитесь, что службы Skype для бизнеса Server 2015 на сервере переднего плана остановлены.</span><span class="sxs-lookup"><span data-stu-id="2e52b-261">Ensure that Skype for Business Server 2015 services are stopped on the Front End server.</span></span>
        - <span data-ttu-id="2e52b-262">Пример (стандартный выпуск):```Stop-CsWindowsService```</span><span class="sxs-lookup"><span data-stu-id="2e52b-262">Example (Standard Edition): ```Stop-CsWindowsService```</span></span>
        - <span data-ttu-id="2e52b-263">Пример (корпоративный выпуск):```Invoke-CsComputerFailover```</span><span class="sxs-lookup"><span data-stu-id="2e52b-263">Example (Enterprise Edition): ```Invoke-CsComputerFailover```</span></span>
    3. <span data-ttu-id="2e52b-264">Установите обновление.</span><span class="sxs-lookup"><span data-stu-id="2e52b-264">Install the update.</span></span>
6. <span data-ttu-id="2e52b-265">Развертывайте разделы реестра, необходимые для использования.</span><span class="sxs-lookup"><span data-stu-id="2e52b-265">Deploy prerequisite registry keys.</span></span>

### <a name="pre-requisite-registry-keys"></a><span data-ttu-id="2e52b-266">Разделы реестра, необходимые для предварительной версии</span><span class="sxs-lookup"><span data-stu-id="2e52b-266">Pre-requisite registry keys</span></span>

<span data-ttu-id="2e52b-267">Скопируйте или вставьте следующий тест в блокнот и переименуйте Тлспререк. reg или имя вашего выбора, а затем выполните импорт:</span><span class="sxs-lookup"><span data-stu-id="2e52b-267">Copy/paste the following test into Notepad and rename TLSPreReq.reg or a name of your choice, then import:</span></span>

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

<span data-ttu-id="2e52b-268">Для SQL Server в случае пулов Enterprise Edition предварительные требования и отключение протокола TLS должны рассматриваться как любые обновления SQL или ОС; Ссылка на:[https://docs.microsoft.com/skypeforbusiness/manage/topology/patch-or-update-a-back-end-or-standard-edition-server](https://docs.microsoft.com/skypeforbusiness/manage/topology/patch-or-update-a-back-end-or-standard-edition-server)</span><span class="sxs-lookup"><span data-stu-id="2e52b-268">For SQL back ends for Enterprise Edition Pools, prerequisites and TLS disable should be treated as any SQL or OS updates would; refer to: [https://docs.microsoft.com/skypeforbusiness/manage/topology/patch-or-update-a-back-end-or-standard-edition-server](https://docs.microsoft.com/skypeforbusiness/manage/topology/patch-or-update-a-back-end-or-standard-edition-server)</span></span>

<span data-ttu-id="2e52b-269">Несмотря на то, что вы можете объединять как необходимые, так и дополнительные действия по отключению приложений и TLS, настоятельно рекомендуем применить все предварительные требования, прежде чем переходить к отключению TLS 1,0 и 1,1 на уровне операционной системы.</span><span class="sxs-lookup"><span data-stu-id="2e52b-269">While both the prerequisite application and TLS disabling steps can be combined, we strongly recommend all prerequisites be applied before proceeding with disabling of TLS 1.0 and 1.1 at the operating system level.</span></span> <span data-ttu-id="2e52b-270">Рекомендуемый подход — подготовить среду, развертывая все необходимые компоненты, проверяя, правильно ли работают все рабочие нагрузки и как ожидается, а затем отключать протокол TLS 1.0/1.1 позже.</span><span class="sxs-lookup"><span data-stu-id="2e52b-270">The best practice approach would be to prepare the environment by deploying all prerequisites, validating that workloads all function correctly and as expected, and then proceeding with TLS 1.0/1.1 disable at a later time.</span></span>

### <a name="disable-tls-10-and-11-via-registry-import"></a><span data-ttu-id="2e52b-271">Отключение TLS 1,0 и 1,1 с помощью импорта реестра</span><span class="sxs-lookup"><span data-stu-id="2e52b-271">Disable TLS 1.0 and 1.1 via registry import</span></span>

<span data-ttu-id="2e52b-272">Перед выполнением дальнейших действий убедитесь, *что выполнены все необходимые условия и обновленные серверы Skype для бизнеса*.</span><span class="sxs-lookup"><span data-stu-id="2e52b-272">Before you proceed with the next steps, *make sure you have completed all prerequisites and updated Skype for Business Servers*.</span></span>

<span data-ttu-id="2e52b-273">Скопируйте приведенный ниже текст в файл блокнота и переименуйте его в **тлсдисабле. reg**:</span><span class="sxs-lookup"><span data-stu-id="2e52b-273">Copy the following text into a Notepad file and rename it **TLSDisable.reg**:</span></span>

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

<span data-ttu-id="2e52b-274">Импортируйте reg файл на каждый сервер, на котором необходимо отключить TLS 1,0 и 1,1.</span><span class="sxs-lookup"><span data-stu-id="2e52b-274">Import the .reg file on each server you wish to disable TLS 1.0 and 1.1.</span></span> <span data-ttu-id="2e52b-275">Перезагрузите сервер.</span><span class="sxs-lookup"><span data-stu-id="2e52b-275">Reboot the server.</span></span> <span data-ttu-id="2e52b-276">После возврата служб в оперативный режим перейдите на следующий сервер.</span><span class="sxs-lookup"><span data-stu-id="2e52b-276">Once the services have come back online, move to the next server.</span></span> <span data-ttu-id="2e52b-277">Подход к пулам Enterprise Edition — это то же самое, что и обновление операционной системы.</span><span class="sxs-lookup"><span data-stu-id="2e52b-277">The approach for Enterprise Edition Pools is the same you would take for any OS update.</span></span>

<span data-ttu-id="2e52b-278">Вы могли заметить, что мы сделали больше, чем просто отключать TLS 1,0 и 1,1 здесь.</span><span class="sxs-lookup"><span data-stu-id="2e52b-278">You may have noticed we are doing more than just disabling TLS 1.0 and 1.1 here.</span></span> <span data-ttu-id="2e52b-279">Мы поддерживаем Переупорядочение комплекта шифров (как показано выше) и отключение некоторых устаревших слабых шифров.</span><span class="sxs-lookup"><span data-stu-id="2e52b-279">We are supporting Cipher Suite re-order (as shown above) and the disabling of some older weak ciphers.</span></span> <span data-ttu-id="2e52b-280">В первый раз мы официально поддерживали эти изменения в SCHANNEL и API шифрования в Skype для бизнеса Server, и важно отметить, что эти изменения поддерживаются и в настоящее время проверены.</span><span class="sxs-lookup"><span data-stu-id="2e52b-280">This is the first time we have officially supported these changes to SCHANNEL and Crypto API on Skype for Business Server, and it is important to note that these changes are the only ones we support and have tested at this time.</span></span> <span data-ttu-id="2e52b-281">Мы можем рассмотреть дополнительные конфигурации в будущем, но сейчас не изменяйте файл импорта реестра в своей реализации.</span><span class="sxs-lookup"><span data-stu-id="2e52b-281">We may consider additional configurations in the future, but for now, please do not modify the registry import file in your implementation.</span></span>

### <a name="validate-that-workloads-are-functioning-as-expected"></a><span data-ttu-id="2e52b-282">Проверка правильности работы рабочих нагрузок</span><span class="sxs-lookup"><span data-stu-id="2e52b-282">Validate that workloads are functioning as expected</span></span>

<span data-ttu-id="2e52b-283">После отключения протокола TLS 1,0 и 1,1 в среде убедитесь, что все основные рабочие нагрузки работают должным образом, например, & присутствия, подключения к службе мгновенных сообщений, вызовы P2P, Корпоративная голосовая связь и т. д.</span><span class="sxs-lookup"><span data-stu-id="2e52b-283">Once TLS 1.0 and 1.1 have been disabled in your environment, ensure that all your main workloads are functioning as expected, such as IM & Presence, P2P calls, Enterprise Voice, etc.</span></span>

<span data-ttu-id="2e52b-284">**Проверка использования протокола TLS 1,2**</span><span class="sxs-lookup"><span data-stu-id="2e52b-284">**Validate only TLS 1.2 is being used**</span></span>

<span data-ttu-id="2e52b-285">Чтобы ваша группа безопасности выполнила новый аудит трафика Skype для бизнеса, убедитесь, что старые протоколы TLS 1,0 и 1,1 больше не используются.</span><span class="sxs-lookup"><span data-stu-id="2e52b-285">Have your Security Team perform a new audit of Skype for Business traffic to ensure that the older protocols TLS 1.0 and 1.1 are no longer in use.</span></span>

<span data-ttu-id="2e52b-286">Кроме того, с помощью Internet Explorer можно проверить подключения TLS для веб-служб из Skype для бизнеса Server 2015 после отключения TLS 1,0 и TLS 1,1.</span><span class="sxs-lookup"><span data-stu-id="2e52b-286">Alternatively, you can use Internet Explorer to test TLS connections to web services from Skype for Business Server 2015 after TLS 1.0 and TLS 1.1 have been disabled.</span></span>

1. <span data-ttu-id="2e52b-287">Запустите Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="2e52b-287">Launch Internet Explorer.</span></span>
2. <span data-ttu-id="2e52b-288">Выберите **инструменты** > **Интернет свойства**.</span><span class="sxs-lookup"><span data-stu-id="2e52b-288">Select **Tools** > **Internet Options**.</span></span>
3. <span data-ttu-id="2e52b-289">Перейдите на вкладку **Дополнительно** .</span><span class="sxs-lookup"><span data-stu-id="2e52b-289">Select the **Advanced** tab.</span></span>
4. <span data-ttu-id="2e52b-290">В разделе **Параметры**прокрутите вниз.</span><span class="sxs-lookup"><span data-stu-id="2e52b-290">Under **Settings**, scroll to the bottom.</span></span>
5. <span data-ttu-id="2e52b-291">Убедитесь, что протокол TLS 1,0, TLS 1,1 и TLS 1,2 включены.</span><span class="sxs-lookup"><span data-stu-id="2e52b-291">Verify that TLS 1.0, TLS 1.1, and TLS 1.2 are enabled.</span></span>
6. <span data-ttu-id="2e52b-292">Просмотрите URL-адрес внутренней веб-службы вашего пула SfB 2015 (должно успешно подключиться).</span><span class="sxs-lookup"><span data-stu-id="2e52b-292">Browse the Internal Web Service URL of your SfB 2015 pool (should connect successfully).</span></span>
7. <span data-ttu-id="2e52b-293">Вернитесь в Internet Explorer и отключите параметр для **использования протокола TLS 1,2** .</span><span class="sxs-lookup"><span data-stu-id="2e52b-293">Go back into Internet Explorer and disable the option to **Use TLS 1.2** only.</span></span>
8. <span data-ttu-id="2e52b-294">Снова просмотрите URL-адрес внутренней веб-службы SfB пула 2015 (должно произойти ошибка подключения).</span><span class="sxs-lookup"><span data-stu-id="2e52b-294">Browse the Internal Web Service URL of your SfB 2015 pool again (should fail to connect).</span></span>

![Свойства браузера](../../media/internet-options.jpg)

## <a name="advanced-deployment-scenarios"></a><span data-ttu-id="2e52b-296">Расширенные сценарии развертывания</span><span class="sxs-lookup"><span data-stu-id="2e52b-296">Advanced deployment scenarios</span></span>

<span data-ttu-id="2e52b-297">Так как некоторые компоненты зависимости необходимы для поддержки протокола TLS 1,2 в Skype для бизнеса SER 2015, то установка с носителя RTM приведет к сбою в любой системе, где отключены TLS 1,0 и 1,1.</span><span class="sxs-lookup"><span data-stu-id="2e52b-297">Because some dependency prerequisites are required to support TLS 1.2 in Skype for Business Ser 2015, installing from RTM media will fail on any system where TLS 1.0 and 1.1 have been disabled.</span></span>

<span data-ttu-id="2e52b-298">**Развертывание новых серверов Standard Edition или пулов Enterprise Edition после отключения TLS 1,0 и 1,1 в вашей среде.**</span><span class="sxs-lookup"><span data-stu-id="2e52b-298">**Deploying New Standard Edition Servers or Enterprise Edition Pools once TLS 1.0 and 1.1 have been disabled in your environment.**</span></span>

<span data-ttu-id="2e52b-299">**Вариант 1:** Используйте [смартсетуп](../../deploy/install/install-skype-for-business-server.md).</span><span class="sxs-lookup"><span data-stu-id="2e52b-299">**Option 1:** Use [SmartSetup](../../deploy/install/install-skype-for-business-server.md).</span></span> <span data-ttu-id="2e52b-300">Обратите внимание, что мы обновляем Смартсетуп в соответствии с обновленными двоичными двоичными файлами SQL в будущем CU, и в будущем будет обновлена эта статья.</span><span class="sxs-lookup"><span data-stu-id="2e52b-300">Note that we are updating SmartSetup to accommodate the updated SQL binaries in a future CU, and will update this article in the future.</span></span>

<span data-ttu-id="2e52b-301">**Вариант 2:** Предварительная установка локальных экземпляров SQL (RTCLOCAL и ЛИНКЛОКАЛ)</span><span class="sxs-lookup"><span data-stu-id="2e52b-301">**Option 2:** Pre-install local SQL instances (RTCLOCAL and LYNCLOCAL)</span></span>

1. <span data-ttu-id="2e52b-302">Скачайте и скопируйте SQL Express 2014 с пакетом обновления 2 (SQLEXPR_x64. exe) в локальную папку на FE.</span><span class="sxs-lookup"><span data-stu-id="2e52b-302">Download and copy SQL Express 2014 SP2 (SQLEXPR_x64.exe) to local folder on FE.</span></span> <span data-ttu-id="2e52b-303">Предположим, что путь к папке <SQL_FOLDER_PATH>.</span><span class="sxs-lookup"><span data-stu-id="2e52b-303">Let’s say folder path <SQL_FOLDER_PATH>.</span></span>
2. <span data-ttu-id="2e52b-304">Запустите PowerShell или командную строку и перейдите к <SQL_FOLDER_PATH>.</span><span class="sxs-lookup"><span data-stu-id="2e52b-304">Launch PowerShell or Command Prompt and navigate to <SQL_FOLDER_PATH>.</span></span>
3. <span data-ttu-id="2e52b-305">Создайте экземпляр SQL RTCLOCAL, выполнив указанную ниже команду.</span><span class="sxs-lookup"><span data-stu-id="2e52b-305">Create the RTCLOCAL SQL instance by running the command below.</span></span> <span data-ttu-id="2e52b-306">Дождитесь завершения работы SQLEXPR_x64. exe, прежде чем продолжить выполнение:</span><span class="sxs-lookup"><span data-stu-id="2e52b-306">Wait until SQLEXPR_x64.exe finishes before proceeding:</span></span>

    <span data-ttu-id="2e52b-307">SQLEXPR_x64. exe/Q/ИАКЦЕПТСКЛСЕРВЕРЛИЦЕНСЕТЕРМС/УПДАТИНАБЛЕД = 0/ХИДЕКОНСОЛЕ/АКТИОН = Install/ФЕАТУРЕС = Скленгине, Tools/INSTANCENAME = RTCLOCAL/TCPENABLED = 1/SQLSVCACCOUNT = "NT AUTHORITY\NetworkService"/SQLSYSADMINACCOUNTS = "Builtin \ Администраторы"/BROWSERSVCSTARTUPTYPE = "Automatic"/AGTSVCACCOUNT = "NTAUTHORITY\NetworkService"/SQLSVCSTARTUPTYPE = automati</span><span class="sxs-lookup"><span data-stu-id="2e52b-307">SQLEXPR_x64.exe  /Q /IACCEPTSQLSERVERLICENSETERMS /UPDATEENABLED=0 /HIDECONSOLE /ACTION=Install /FEATURES=SQLEngine,Tools /INSTANCENAME=RTCLOCAL /TCPENABLED=1 /SQLSVCACCOUNT="NT AUTHORITY\NetworkService" /SQLSYSADMINACCOUNTS="Builtin\Administrators" /BROWSERSVCSTARTUPTYPE="Automatic" /AGTSVCACCOUNT="NTAUTHORITY\NetworkService" /SQLSVCSTARTUPTYPE=Automati</span></span>
1. <span data-ttu-id="2e52b-308">Создайте экземпляр SQL ЛИНКЛОКАЛ, выполнив указанную ниже команду.</span><span class="sxs-lookup"><span data-stu-id="2e52b-308">Create the LYNCLOCAL SQL instance by running the command below.</span></span> <span data-ttu-id="2e52b-309">Дождитесь завершения работы SQLEXPR_x64. exe, прежде чем переходить к следующему шагу:</span><span class="sxs-lookup"><span data-stu-id="2e52b-309">Wait until SQLEXPR_x64.exe finishes before proceeding to the next step:</span></span>

    <span data-ttu-id="2e52b-310">SQLEXPR_x64. exe/Q/ИАКЦЕПТСКЛСЕРВЕРЛИЦЕНСЕТЕРМС/УПДАТИНАБЛЕД = 0/ХИДЕКОНСОЛЕ/АКТИОН = Install/ФЕАТУРЕС = Скленгине, Tools/INSTANCENAME = LYNCLOCAL/TCPENABLED = 1/SQLSVCACCOUNT = "NT AUTHORITY\NetworkService"/SQLSYSADMINACCOUNTS = "Builtin \ Администраторы"/BROWSERSVCSTARTUPTYPE = "Automatic"/AGTSVCACCOUNT = "NTAUTHORITY\NetworkService"/SQLSVCSTARTUPTYPE = Automatic</span><span class="sxs-lookup"><span data-stu-id="2e52b-310">SQLEXPR_x64.exe /Q /IACCEPTSQLSERVERLICENSETERMS /UPDATEENABLED=0 /HIDECONSOLE /ACTION=Install /FEATURES=SQLEngine,Tools /INSTANCENAME=LYNCLOCAL /TCPENABLED=1 /SQLSVCACCOUNT="NT AUTHORITY\NetworkService" /SQLSYSADMINACCOUNTS="Builtin\Administrators" /BROWSERSVCSTARTUPTYPE="Automatic" /AGTSVCACCOUNT="NTAUTHORITY\NetworkService" /SQLSVCSTARTUPTYPE=Automatic</span></span>
1. <span data-ttu-id="2e52b-311">Запустите программу установки Skype для бизнеса Server 2015 RTM.</span><span class="sxs-lookup"><span data-stu-id="2e52b-311">Run Skype for Business Server 2015 RTM setup.</span></span>
2. <span data-ttu-id="2e52b-312">Выполните остальные действия из раздела предварительные требования выше.</span><span class="sxs-lookup"><span data-stu-id="2e52b-312">Follow the remaining steps from the prerequisites section above.</span></span>

<span data-ttu-id="2e52b-313">**Вариант 3:** Кроме того, вы можете вручную заменить двоичные файлы в локальном каталоге установочного носителя следующим образом:</span><span class="sxs-lookup"><span data-stu-id="2e52b-313">**Option 3:** You may also manually replace binaries in a local installation media directory as follows:</span></span>

1. [<span data-ttu-id="2e52b-314">Установка необходимых компонентов для Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="2e52b-314">Install prerequisites for Skype for Business Server</span></span>](../../deploy/install/install-prerequisites.md)  
2. <span data-ttu-id="2e52b-315">Установите .NET 4,7:</span><span class="sxs-lookup"><span data-stu-id="2e52b-315">Install .NET 4.7:</span></span> 
      - <span data-ttu-id="2e52b-316">**Примечание:** Мы впервые предоставили поддержку .NET 4,7 в Skype для бизнеса Server 2015 CU5 (6.0.9319.281).</span><span class="sxs-lookup"><span data-stu-id="2e52b-316">**Note:** We first introduced support for .NET 4.7 in Skype for Business Server 2015 CU5 (6.0.9319.281).</span></span> <span data-ttu-id="2e52b-317">Поэтому в последующих шагах ниже мы будем обновлять основные компоненты до выполнения основной установки.</span><span class="sxs-lookup"><span data-stu-id="2e52b-317">Therefore, in later steps below we will be updating Core Components prior to the main install.</span></span>
      - <span data-ttu-id="2e52b-318">Download: https://www.microsoft.com/download/details.aspx?id=55167.</span><span class="sxs-lookup"><span data-stu-id="2e52b-318">Download: https://www.microsoft.com/download/details.aspx?id=55167.</span></span> 
      - <span data-ttu-id="2e52b-319">Ссылка: [программное обеспечение, которое следует установить перед развертыванием Skype для бизнеса Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md#software-that-should-be-installed-before-a-skype-for-business-server-2015-deployment)</span><span class="sxs-lookup"><span data-stu-id="2e52b-319">Reference: [Software that should be installed before a Skype for Business Server 2015 deployment](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md#software-that-should-be-installed-before-a-skype-for-business-server-2015-deployment)</span></span>
3. <span data-ttu-id="2e52b-320">Копирование файлов и папок ISO:</span><span class="sxs-lookup"><span data-stu-id="2e52b-320">Copy ISO Files/Folders:</span></span> 
    - <span data-ttu-id="2e52b-321">С прикрепленным ISO-файлом ISO для Skype для бизнеса Server 2015 откройте корневой каталог диска, к которому он подключен, как (\) ex: D: в проводнике).</span><span class="sxs-lookup"><span data-stu-id="2e52b-321">With the Skype for Business Server 2015 ISO attached, open the root directory of the drive it is attached as (Ex: D:\) in File Explorer.</span></span>
    - <span data-ttu-id="2e52b-322">Скопируйте все папки и файлы в папку на локальном диске (например, C:\SkypeForBusiness2015ISO).</span><span class="sxs-lookup"><span data-stu-id="2e52b-322">Copy all folders and files to a folder on a local disk (Ex: C:\SkypeForBusiness2015ISO).</span></span>
    - <span data-ttu-id="2e52b-323">**Примечание:** Прежде чем устанавливать компоненты, некоторые файлы потребуется обновить для поддержки протокола TLS 1,2.</span><span class="sxs-lookup"><span data-stu-id="2e52b-323">**Note:** Prior to installing components, some files will need to be updated for support of TLS 1.2.</span></span>
4. <span data-ttu-id="2e52b-324">Замена пакетов MSI/EXE:</span><span class="sxs-lookup"><span data-stu-id="2e52b-324">Replace MSI/EXE Packages:</span></span> 
    - <span data-ttu-id="2e52b-325">Замените существующие пакеты MSI и EXE в папке/Setup/AMD64/установочного носителя на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="2e52b-325">Replace the existing MSI and EXE packages in the /Setup/amd64/ folder of the installation media on the local machine.</span></span>
    - <span data-ttu-id="2e52b-326">SQL 2014 SP2 Express:https://www.microsoft.com/download/details.aspx?id=53167</span><span class="sxs-lookup"><span data-stu-id="2e52b-326">SQL 2014 SP2 Express: https://www.microsoft.com/download/details.aspx?id=53167</span></span> 
        - <span data-ttu-id="2e52b-327">Переименуйте SQLEXPR_x64 на локальном компьютере и замените существующий файл в папке Setup/AMD64/на установочном носителе.</span><span class="sxs-lookup"><span data-stu-id="2e52b-327">Rename to SQLEXPR_x64 on the local machine, and replace the existing file in the Setup/amd64/ folder of the installation media.</span></span>
    - <span data-ttu-id="2e52b-328">Собственный клиент SQL:https://www.microsoft.com/download/details.aspx?id=50402</span><span class="sxs-lookup"><span data-stu-id="2e52b-328">SQL Native Client: https://www.microsoft.com/download/details.aspx?id=50402</span></span> 
        - <span data-ttu-id="2e52b-329">**Примечание:** Переименуйте его, если это необходимо, в sqlncli. msi, а затем замените существующий файл, существующий в папке Setup/AMD64/, на установочном носителе.</span><span class="sxs-lookup"><span data-stu-id="2e52b-329">**Note:** Rename this if necessary to sqlncli.msi, and then replace the existing file that exists in the Setup/amd64/ folder of the installation media.</span></span>
    - <span data-ttu-id="2e52b-330">Объекты управления SQL:https://www.microsoft.com/download/details.aspx?id=53164</span><span class="sxs-lookup"><span data-stu-id="2e52b-330">SQL Management Objects: https://www.microsoft.com/download/details.aspx?id=53164</span></span> 
        - <span data-ttu-id="2e52b-331">**Примечание:** Пакет дополнительных компонентов содержит множество элементов, которые можно скачать.</span><span class="sxs-lookup"><span data-stu-id="2e52b-331">**Note:** The Feature pack will have a lot of items that can be downloaded.</span></span> <span data-ttu-id="2e52b-332">Выберите загрузку только Шаредманажементобжектс. msi.</span><span class="sxs-lookup"><span data-stu-id="2e52b-332">Select to download SharedManagementObjects.msi only.</span></span>
        - <span data-ttu-id="2e52b-333">**Примечание:** Замените существующий файл, существующий в папке Setup/AMD64/, на установочном носителе.</span><span class="sxs-lookup"><span data-stu-id="2e52b-333">**Note:** Replace the existing file that exists in the Setup/amd64/ folder of the installation media.</span></span>
    - <span data-ttu-id="2e52b-334">Типы SQL CLR:https://www.microsoft.com/download/details.aspx?id=53164</span><span class="sxs-lookup"><span data-stu-id="2e52b-334">SQL CLR Types: https://www.microsoft.com/download/details.aspx?id=53164</span></span> 
        - <span data-ttu-id="2e52b-335">**Примечание:** Пакет дополнительных компонентов содержит множество элементов, которые можно скачать.</span><span class="sxs-lookup"><span data-stu-id="2e52b-335">**Note:** The Feature pack will have a lot of items that can be downloaded.</span></span> <span data-ttu-id="2e52b-336">Выберите, чтобы загружать только Кклсисклртипес. msi</span><span class="sxs-lookup"><span data-stu-id="2e52b-336">Select to download CQLSysClrTypes.msi only</span></span>
        - <span data-ttu-id="2e52b-337">**Note**: замените существующий файл, существующий в папке Setup/AMD64/, на установочном носителе.</span><span class="sxs-lookup"><span data-stu-id="2e52b-337">**Note**: Replace the existing file that exists in the Setup/amd64/ folder of the installation media.</span></span>
5. <span data-ttu-id="2e52b-338">Установка основных компонентов:</span><span class="sxs-lookup"><span data-stu-id="2e52b-338">Install Core Components:</span></span> 
    - <span data-ttu-id="2e52b-339">Запустите setup. exe из папки "Настройка/AMD64/" установочного носителя.</span><span class="sxs-lookup"><span data-stu-id="2e52b-339">Run Setup.exe from the Setup/amd64/ folder of the installation media.</span></span> <span data-ttu-id="2e52b-340">Следуйте инструкциям по установке основных компонентов</span><span class="sxs-lookup"><span data-stu-id="2e52b-340">Follow the instructions to install Core Components</span></span>
    - <span data-ttu-id="2e52b-341">Закройте основные компоненты.</span><span class="sxs-lookup"><span data-stu-id="2e52b-341">Close Core Components.</span></span>
6. <span data-ttu-id="2e52b-342">Обновление основных компонентов:</span><span class="sxs-lookup"><span data-stu-id="2e52b-342">Update Core Components:</span></span> 
    - <span data-ttu-id="2e52b-343">Скачайте установщик обновлений Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="2e52b-343">Download the Skype for Business Update Installer.</span></span>
    - <span data-ttu-id="2e52b-344">Запустите установщик, чтобы обновить основные компоненты и установить счетчики производительности.</span><span class="sxs-lookup"><span data-stu-id="2e52b-344">Run the installer to update Core Components and install the performance counters.</span></span>
    - <span data-ttu-id="2e52b-345">**Примечание:** При выпуске CU6HF2 в настоящее время функция автоматического обновления будет устанавливаться только до CU6.</span><span class="sxs-lookup"><span data-stu-id="2e52b-345">**Note:** As of the release of CU6HF2, the auto-update feature currently only will install up to CU6.</span></span> <span data-ttu-id="2e52b-346">Таким образом, чтобы обновить основные компоненты до 6.0.9319.516, необходимо выполнить отдельное обновление.</span><span class="sxs-lookup"><span data-stu-id="2e52b-346">Therefore, the updater must be run separately to update Core Components to 6.0.9319.516.</span></span>
    - <span data-ttu-id="2e52b-347">Ссылкойhttps://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015</span><span class="sxs-lookup"><span data-stu-id="2e52b-347">Reference: https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015</span></span>
7. <span data-ttu-id="2e52b-348">Установка средств администрирования (необязательно):</span><span class="sxs-lookup"><span data-stu-id="2e52b-348">Install Administrative Tools (Optional):</span></span> 
    - <span data-ttu-id="2e52b-349">При этом будет установлено приложение Microsoft SQL Server 2012 Native Client, управляющие объекты SQL Server 2014 (x64) и Microsoft System CLR Types для SQL Server 2014 (x64), используя обновленные файлы.</span><span class="sxs-lookup"><span data-stu-id="2e52b-349">This will install the Microsoft SQL Server 2012 Native Client, SQL Server 2014 Management Objects (x64), and Microsoft System CLR Types for SQL Server 2014 (x64) using the updated files.</span></span> <span data-ttu-id="2e52b-350">Кроме того, построитель топологий и панель управления Skype для бизнеса Server 2015 будут доступны на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="2e52b-350">Additionally, the Skype for Business Server 2015 Topology Builder and Control Panel will be available on the local machine.</span></span>
8. <span data-ttu-id="2e52b-351">Установка локального хранилища конфигурации (шаг 1):</span><span class="sxs-lookup"><span data-stu-id="2e52b-351">Install Local Configuration Store (Step 1):</span></span> 
     - <span data-ttu-id="2e52b-352">Откройте мастер развертывания, щелкните установить или обновить систему Skype для бизнеса Server и выберите пункт **выполнить** на шаге 1: Установка локального хранилища конфигурации.</span><span class="sxs-lookup"><span data-stu-id="2e52b-352">Open the Deployment Wizard, click Install or Update Skype for Business Server System, and click on **Run** at Step 1: Install Local Configuration Store.</span></span>
     - <span data-ttu-id="2e52b-353">В диалоговом окне **Установка локального хранилища конфигурации** нажмите кнопку **Далее** .</span><span class="sxs-lookup"><span data-stu-id="2e52b-353">Click **Next** in the **Install Local Configuration Store** dialog box.</span></span>
     <span data-ttu-id="2e52b-354">![Диалоговое окно установки локального хранилища конфигурации](../../media/local-configuration-store.png)</span><span class="sxs-lookup"><span data-stu-id="2e52b-354">![Install Local Configuration Store dialog box](../../media/local-configuration-store.png)</span></span>
     - <span data-ttu-id="2e52b-355">Просмотрите результаты и убедитесь, что состояние задачи завершено.</span><span class="sxs-lookup"><span data-stu-id="2e52b-355">Review the results, and ensure that the Task Status is Completed.</span></span> <span data-ttu-id="2e52b-356">Изучите полученный файл журнала, нажав кнопку **Просмотреть журнал**.</span><span class="sxs-lookup"><span data-stu-id="2e52b-356">Review the resulting log file by clicking **View Log**.</span></span>
     <span data-ttu-id="2e52b-357">![Состояние задачи отображается как завершенное](../../media/local-configuration-task-completed.png)</span><span class="sxs-lookup"><span data-stu-id="2e52b-357">![Task status shows as Completed](../../media/local-configuration-task-completed.png)</span></span>
     - <span data-ttu-id="2e52b-358">Нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="2e52b-358">Click **Finish**.</span></span>
9. <span data-ttu-id="2e52b-359">Установка или удаление компонентов Skype для бизнеса Server (шаг 2):</span><span class="sxs-lookup"><span data-stu-id="2e52b-359">Set up or remove Skype for Business Server Components (Step 2):</span></span>
    - <span data-ttu-id="2e52b-360">Откройте мастер развертывания, выберите **установить или обновить систему Skype для бизнеса Server**и нажмите **выполнить** на шаге 2: Установка или удаление компонентов Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="2e52b-360">Open the Deployment Wizard, click **Install or Update Skype for Business Server System**, and click **Run** at Step 2: Set up or Remove Skype for Business Server Components</span></span>
    - <span data-ttu-id="2e52b-361">В диалоговом окне Настройка компонентов Skype для бизнеса Server нажмите кнопку **Далее** .</span><span class="sxs-lookup"><span data-stu-id="2e52b-361">Click **Next** in the Set Up Skype for Business Server Components dialog box.</span></span>
    <span data-ttu-id="2e52b-362">![окно "Настройка компонентов Skype для бизнеса Server"](../../media/set-up-skype-for-business-server-components-window.png)</span><span class="sxs-lookup"><span data-stu-id="2e52b-362">![the Set Up Skype for Business Server Components window](../../media/set-up-skype-for-business-server-components-window.png)</span></span>
    - <span data-ttu-id="2e52b-363">Просмотрите журнал с помощью журнала просмотра и проверьте, что установка выполнена без проблем.</span><span class="sxs-lookup"><span data-stu-id="2e52b-363">Review the log using View Log, and validate that setup completed without issues.</span></span> 
    - <span data-ttu-id="2e52b-364">Нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="2e52b-364">Click **Finish**.</span></span>
10. <span data-ttu-id="2e52b-365">Продолжите дополнительную установку и настройку (на этом шаге можно возобновить нормальную установку).</span><span class="sxs-lookup"><span data-stu-id="2e52b-365">Proceed with additional installation and configuration as required (you can resume normal installation procedures at this point).</span></span>
