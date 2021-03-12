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
description: Подготовка и реализация отключения TLS 1.0 и 1.1 в средах.
ms.openlocfilehash: 214605f80c79d7ecb334aeca49d29210e888b511
ms.sourcegitcommit: 4d76837f9481ca2cda437afdf11de5eaf7a57d99
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/11/2021
ms.locfileid: "50726400"
---
# <a name="disable-tls-1011-in-skype-for-business-server-2015"></a><span data-ttu-id="5c7a7-103">Отключение TLS 1.0/1.1 в Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="5c7a7-103">Disable TLS 1.0/1.1 in Skype for Business Server 2015</span></span>

<span data-ttu-id="5c7a7-104">В этой статье вы можете подготовиться и реализовать отключение TLS 1.0 и 1.1 в средах.</span><span class="sxs-lookup"><span data-stu-id="5c7a7-104">This article helps you prepare for and implement disabling TLS 1.0 and 1.1 in your environments.</span></span> <span data-ttu-id="5c7a7-105">Этот процесс требует тщательного планирования и подготовки.</span><span class="sxs-lookup"><span data-stu-id="5c7a7-105">This process requires extensive planning and preparation.</span></span> <span data-ttu-id="5c7a7-106">Внимательно просмотрите все сведения в этой статье при планировании отключения TLS 1.0 и 1.1 для организации.</span><span class="sxs-lookup"><span data-stu-id="5c7a7-106">Carefully review all of the information in this article as you make your plan to disable TLS 1.0 and 1.1 for your organization.</span></span> <span data-ttu-id="5c7a7-107">Существует множество внешних зависимостей и условий подключения, на которые может повлиять отключение TLS 1.0/1.1, поэтому необходимо тщательное планирование и тестирование.</span><span class="sxs-lookup"><span data-stu-id="5c7a7-107">There are many external dependencies and connectivity conditions that could be impacted by disabling TLS 1.0/1.1, so extensive planning and testing is warranted.</span></span>

- [<span data-ttu-id="5c7a7-108">Фон и область</span><span class="sxs-lookup"><span data-stu-id="5c7a7-108">Background and scope</span></span>](#background-and-scope)
- [<span data-ttu-id="5c7a7-109">Необходимые условия и процесс</span><span class="sxs-lookup"><span data-stu-id="5c7a7-109">Prerequisites and process</span></span>](#prerequisites-and-process)
- [<span data-ttu-id="5c7a7-110">Расширенные сценарии развертывания</span><span class="sxs-lookup"><span data-stu-id="5c7a7-110">Advanced deployment scenarios</span></span>](#advanced-deployment-scenarios)

## <a name="background-and-scope"></a><span data-ttu-id="5c7a7-111">Фон и область</span><span class="sxs-lookup"><span data-stu-id="5c7a7-111">Background and scope</span></span>

<span data-ttu-id="5c7a7-112">Основными драйверами для предоставления TLS 1.0 и 1.1 отключения поддержки локального сервера Skype для бизнеса являются Совет по стандартам безопасности индустрии платежных карт (PCI) и требования к федеральным стандартам обработки информации.</span><span class="sxs-lookup"><span data-stu-id="5c7a7-112">The primary drivers for providing TLS 1.0 and 1.1 disable support for Skype for Business Server On-Premises are Payment Card Industry (PCI) Security Standards Council and Federal Information Processing Standards requirements.</span></span> <span data-ttu-id="5c7a7-113">Дополнительные сведения о требованиях PCI можно найти [здесь.](https://blog.pcisecuritystandards.org/are-you-ready-for-30-june-2018-sayin-goodbye-to-ssl-early-tls)</span><span class="sxs-lookup"><span data-stu-id="5c7a7-113">More information for PCI requirements can be found [here](https://blog.pcisecuritystandards.org/are-you-ready-for-30-june-2018-sayin-goodbye-to-ssl-early-tls).</span></span>  <span data-ttu-id="5c7a7-114">Корпорация Майкрософт не может предоставить рекомендации о том, требуется ли вашей организации придерживаться этих или других требований.</span><span class="sxs-lookup"><span data-stu-id="5c7a7-114">Microsoft cannot provide guidance on whether or not your organization is required to adhere to these or other requirements.</span></span> <span data-ttu-id="5c7a7-115">Необходимо определить, требуется ли отключить TLS 1.0 и/или 1.1 в средах.</span><span class="sxs-lookup"><span data-stu-id="5c7a7-115">You must determine if it is required for you to disable TLS 1.0 and/or 1.1 in your environments.</span></span>

<span data-ttu-id="5c7a7-116">Корпорация Майкрософт подготовила белый документ по TLS, доступный [здесь,](https://cloudblogs.microsoft.com/microsoftsecure/2017/06/20/tls-1-2-support-at-microsoft/)и мы также рекомендуем фоновое чтение, доступное в этом [блоге Exchange](https://blogs.technet.microsoft.com/exchange/2018/01/26/exchange-server-tls-guidance-part-1-getting-ready-for-tls-1-2/).</span><span class="sxs-lookup"><span data-stu-id="5c7a7-116">Microsoft has produced a white paper on TLS available [here](https://cloudblogs.microsoft.com/microsoftsecure/2017/06/20/tls-1-2-support-at-microsoft/), and we also recommend the background reading available in this [Exchange blog](https://blogs.technet.microsoft.com/exchange/2018/01/26/exchange-server-tls-guidance-part-1-getting-ready-for-tls-1-2/).</span></span>

## <a name="supportability-scope"></a><span data-ttu-id="5c7a7-117">Область поддержки</span><span class="sxs-lookup"><span data-stu-id="5c7a7-117">Supportability Scope</span></span>

<span data-ttu-id="5c7a7-118">*Область* относится к границам поддержки.</span><span class="sxs-lookup"><span data-stu-id="5c7a7-118">*Scope* refers to supportability boundaries.</span></span> <span data-ttu-id="5c7a7-119">*Полное тестирование и* поддержка означает, что мы полностью поддерживаем и протестировали отключение TLS 1.0 и 1.1 для перечисленных версий продукта.</span><span class="sxs-lookup"><span data-stu-id="5c7a7-119">*Fully tested and supported* means we fully support and have tested disabling of TLS 1.0 and 1.1 for the listed product versions.</span></span> <span data-ttu-id="5c7a7-120">*В настоящее время ведется расследование* означает именно это; мы активно исследуем возможность применения этих продуктов в области поддержки отключения TLS.</span><span class="sxs-lookup"><span data-stu-id="5c7a7-120">*Currently being investigated* means just that; we are actively investigating bringing these products into scope for TLS disable support.</span></span> <span data-ttu-id="5c7a7-121">*Выход из области* означает, что эти версии продуктов не поддерживают отключение TLS 1.0 или 1.1 и не будут работать, за указанными исключениями.</span><span class="sxs-lookup"><span data-stu-id="5c7a7-121">*Out of scope* means these product versions do not support disabling TLS 1.0 or 1.1 and will not work, with noted exceptions.</span></span>

### <a name="fully-tested-and-supported-servers"></a><span data-ttu-id="5c7a7-122">Полностью протестированная и поддерживаемая серверы</span><span class="sxs-lookup"><span data-stu-id="5c7a7-122">Fully tested and supported servers</span></span>

- <span data-ttu-id="5c7a7-123">Skype для бизнеса Server 2019 CU1 17.0.2046.123 (июнь 2019 г.) или выше</span><span class="sxs-lookup"><span data-stu-id="5c7a7-123">Skype for Business Server 2019 CU1 17.0.2046.123 (June 2019) or higher</span></span>
- <span data-ttu-id="5c7a7-124">Skype для бизнеса Server 2015 CU9 6.0.9319.548 (май 2019 г.) или выше на Windows Server 2012 (с обновлением KB [3140245](https://support.microsoft.com/help/3140245/update-to-enable-tls-1-1-and-tls-1-2-as-a-default-secure-protocols-in) или на выходе), 2012 R2 или 2016.</span><span class="sxs-lookup"><span data-stu-id="5c7a7-124">Skype for Business Server 2015 CU9 6.0.9319.548 (May 2019) or higher on Windows Server 2012 (with KB [3140245](https://support.microsoft.com/help/3140245/update-to-enable-tls-1-1-and-tls-1-2-as-a-default-secure-protocols-in) or superseding update), 2012 R2 or 2016.</span></span>
- <span data-ttu-id="5c7a7-125">На месте обновлен Skype для бизнеса Server 2015 с cu9 6.0.9319.548 (май 2019 г.) или более высокой по Windows Server 2008 R2, 2012 г. (с KB [3140245](https://support.microsoft.com/help/3140245/update-to-enable-tls-1-1-and-tls-1-2-as-a-default-secure-protocols-in) или обновлением с перенастройки) или 2012 R2.</span><span class="sxs-lookup"><span data-stu-id="5c7a7-125">In-place Upgraded Skype for Business Server 2015, with CU9 6.0.9319.548 (May 2019) or higher on Windows Server 2008 R2, 2012 (with KB [3140245](https://support.microsoft.com/help/3140245/update-to-enable-tls-1-1-and-tls-1-2-as-a-default-secure-protocols-in) or superseding update), or 2012 R2.</span></span>
- <span data-ttu-id="5c7a7-126">Подключение к exchange и Outlook Web App с Exchange Server 2010 SP3 RU19 или более, руководство [здесь](https://blogs.technet.microsoft.com/exchange/2018/01/26/exchange-server-tls-guidance-part-1-getting-ready-for-tls-1-2/)</span><span class="sxs-lookup"><span data-stu-id="5c7a7-126">Exchange Connectivity and Outlook Web App with Exchange Server 2010 SP3 RU19 or higher, guidance [here](https://blogs.technet.microsoft.com/exchange/2018/01/26/exchange-server-tls-guidance-part-1-getting-ready-for-tls-1-2/)</span></span>
- <span data-ttu-id="5c7a7-127">Уцелевшая ветвная техника (SBA) в Skype для бизнеса Server 2015 CU6 HF2 или выше (подтвердите у поставщика, что они упаковал соответствующие обновления и были доступны для вашего устройства)</span><span class="sxs-lookup"><span data-stu-id="5c7a7-127">Survivable Branch Appliance (SBA) with Skype for Business Server 2015 CU6 HF2 or higher (confirm with your vendor that they packaged the appropriate updates and have been made available for your appliance)</span></span>
- <span data-ttu-id="5c7a7-128">Выживший сервер филиалов (SBS) с Skype для бизнеса Server 2015 CU6 HF2 или выше</span><span class="sxs-lookup"><span data-stu-id="5c7a7-128">Survivable Branch Server (SBS) with Skype for Business Server 2015 CU6 HF2 or higher</span></span>
- <span data-ttu-id="5c7a7-129">Lync Server 2013 **Edge Role Only**, это потому, что роль Edge не имеет зависимости от Windows Fabric 1.0.</span><span class="sxs-lookup"><span data-stu-id="5c7a7-129">Lync Server 2013 **Edge Role Only**, this is because Edge role does not have a dependency on Windows Fabric 1.0.</span></span>

### <a name="fully-tested-and-supported-clients"></a><span data-ttu-id="5c7a7-130">Полностью протестированная и поддерживаемая клиенты</span><span class="sxs-lookup"><span data-stu-id="5c7a7-130">Fully tested and supported clients</span></span>

- <span data-ttu-id="5c7a7-131">Настольный клиент Lync 2013 (Skype для бизнеса), MSI и C2R, включая базовые [15.0.5023.1000 или более](https://support.microsoft.com/help/4018334/april-3-2018-update-for-skype-for-business-2015-lync-2013-kb4018334)</span><span class="sxs-lookup"><span data-stu-id="5c7a7-131">Lync 2013 (Skype for Business) Desktop Client, MSI and C2R, including Basic [15.0.5023.1000 or higher](https://support.microsoft.com/help/4018334/april-3-2018-update-for-skype-for-business-2015-lync-2013-kb4018334)</span></span>
- <span data-ttu-id="5c7a7-132">Настольный клиент Skype для бизнеса 2016, MSI [16.0.4678.1000 или](https://support.microsoft.com/help/4018323/april-3-2018-update-for-skype-for-business-2016-kb4018323)выше, включая Basic</span><span class="sxs-lookup"><span data-stu-id="5c7a7-132">Skype for Business 2016 Desktop Client, MSI [16.0.4678.1000 or higher](https://support.microsoft.com/help/4018323/april-3-2018-update-for-skype-for-business-2016-kb4018323), including Basic</span></span>
- <span data-ttu-id="5c7a7-133">Skype для бизнеса 2016 Нажмите кнопку Выполнить Требуй обновлений за [апрель 2018](https://docs.microsoft.com/officeupdates/release-notes-office365-proplus) г.:</span><span class="sxs-lookup"><span data-stu-id="5c7a7-133">Skype for Business 2016 Click to Run Require the [April 2018](https://docs.microsoft.com/officeupdates/release-notes-office365-proplus) Updates:</span></span> 
    - <span data-ttu-id="5c7a7-134">Ежемесячные и Semi-Annual, 16 \. 0 \. 9126 \. 2152 или более</span><span class="sxs-lookup"><span data-stu-id="5c7a7-134">Monthly and Semi-Annual Targeted, 16\.0\.9126\.2152 or higher</span></span>
    - <span data-ttu-id="5c7a7-135">Semi-Annual и отложенный канал, 16 \. 0 \. 8431 \. 2242 или более</span><span class="sxs-lookup"><span data-stu-id="5c7a7-135">Semi-Annual and Deferred Channel, 16\.0\.8431\.2242 or higher</span></span>
- <span data-ttu-id="5c7a7-136">Skype для бизнеса на Mac 16.15 или более</span><span class="sxs-lookup"><span data-stu-id="5c7a7-136">Skype for Business on Mac 16.15 or higher</span></span>
- <span data-ttu-id="5c7a7-137">Skype для бизнеса для iOS и Android 6.19 или более</span><span class="sxs-lookup"><span data-stu-id="5c7a7-137">Skype for Business for iOS and Android 6.19 or higher</span></span>
- <span data-ttu-id="5c7a7-138">Комнаты Microsoft Teams (ранее известная как Skype Room System V2 SRS V2) 4.0.64.0 (декабрь 2018 г.) или выше</span><span class="sxs-lookup"><span data-stu-id="5c7a7-138">Microsoft Teams Rooms (previously known as Skype Room System V2 SRS V2) 4.0.64.0 (December 2018) or higher</span></span>
- <span data-ttu-id="5c7a7-139">Surface Hub update for Team edition based on KB4499162 (May 2019, OS Build 15063.1835) or higher</span><span class="sxs-lookup"><span data-stu-id="5c7a7-139">Surface Hub update for Team edition based on KB4499162 (May 2019, OS Build 15063.1835) or higher</span></span>
- <span data-ttu-id="5c7a7-140">Skype Web App 2015 CU6 HF2 или выше (корабли с сервером)</span><span class="sxs-lookup"><span data-stu-id="5c7a7-140">Skype Web App 2015 CU6 HF2 or higher (ships with Server)</span></span>

### <a name="currently-being-investigated"></a><span data-ttu-id="5c7a7-141">В настоящее время проводится расследование</span><span class="sxs-lookup"><span data-stu-id="5c7a7-141">Currently being investigated</span></span>

- <span data-ttu-id="5c7a7-142">Панель мониторинга качества вызовов (новая установка после отключения TLS 1.0, 1.1 см. ниже)\*</span><span class="sxs-lookup"><span data-stu-id="5c7a7-142">Call Quality Dashboard (new install after TLS 1.0, 1.1 have been disabled, see below)\*</span></span>
 
### <a name="out-of-scope"></a><span data-ttu-id="5c7a7-143">Вне области поддержки</span><span class="sxs-lookup"><span data-stu-id="5c7a7-143">Out of scope</span></span>

<span data-ttu-id="5c7a7-144">Кроме отмеченных, следующие продукты не находятся в области поддержки отключения TLS 1.0/1.1 и не будут работать в среде, в которой отключены TLS 1.0 и 1.1.</span><span class="sxs-lookup"><span data-stu-id="5c7a7-144">Except where noted, the following products are not in scope for TLS 1.0/1.1 disable support and will not function in an environment where TLS 1.0 and 1.1 have been disabled.</span></span> <span data-ttu-id="5c7a7-145">Это означает, что если вы по-прежнему используете серверы или клиенты из-за точки звонков, их необходимо обновить или удалить, если требуется отключить TLS 1.0/1.1 в любом месте локального развертывания Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="5c7a7-145">What this means: if you still utilize out-of-scope servers or clients, you must update or remove these if you need to disable TLS 1.0/1.1 anywhere in your Skype for Business Server on-premises deployment.</span></span>

- <span data-ttu-id="5c7a7-146">Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5c7a7-146">Lync Server 2013</span></span>
- <span data-ttu-id="5c7a7-147">Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="5c7a7-147">Lync Server 2010</span></span>
- <span data-ttu-id="5c7a7-148">Windows Server 2008 или ниже</span><span class="sxs-lookup"><span data-stu-id="5c7a7-148">Windows Server 2008 or lower</span></span>
- <span data-ttu-id="5c7a7-149">Lync для Mac 2011</span><span class="sxs-lookup"><span data-stu-id="5c7a7-149">Lync for Mac 2011</span></span>
- <span data-ttu-id="5c7a7-150">Lync 2013 для мобильных устройств — iOS, iPad, Android или Windows Phone</span><span class="sxs-lookup"><span data-stu-id="5c7a7-150">Lync 2013 for Mobile - iOS, iPad, Android or Windows Phone</span></span>
- <span data-ttu-id="5c7a7-151">Клиент Магазина Windows Lync "MX"</span><span class="sxs-lookup"><span data-stu-id="5c7a7-151">Lync "MX" Windows Store client</span></span>
- <span data-ttu-id="5c7a7-152">Lync Room System (a.k.a.</span><span class="sxs-lookup"><span data-stu-id="5c7a7-152">Lync Room System (a.k.a.</span></span> <span data-ttu-id="5c7a7-153">SRSv1).</span><span class="sxs-lookup"><span data-stu-id="5c7a7-153">SRSv1).</span></span> <span data-ttu-id="5c7a7-154">LRS достигла конца поддержки 9 октября 2018 г. и не будет обновляться для поддержки TLS 1.2.</span><span class="sxs-lookup"><span data-stu-id="5c7a7-154">LRS reached end of support on October 9, 2018 and will not be updated to support TLS 1.2.</span></span>
- <span data-ttu-id="5c7a7-155">Все клиенты Lync 2010</span><span class="sxs-lookup"><span data-stu-id="5c7a7-155">All Lync 2010 clients</span></span>
- <span data-ttu-id="5c7a7-156">Lync Phone Edition — обновленное руководство [здесь.](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Certified-Skype-for-Business-Online-Phones-and-what-this-means/ba-p/120035)</span><span class="sxs-lookup"><span data-stu-id="5c7a7-156">Lync Phone Edition - updated guidance [here](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Certified-Skype-for-Business-Online-Phones-and-what-this-means/ba-p/120035).</span></span>
- <span data-ttu-id="5c7a7-157">2013 на основе сохранившихся ветвейных устройств (SBA) или выживаемого сервера филиала (SBS)</span><span class="sxs-lookup"><span data-stu-id="5c7a7-157">2013 based Survivable Branch Appliance (SBA) or Survivable Branch Server (SBS)</span></span>
- <span data-ttu-id="5c7a7-158">Cloud Connector Edition (CCE)</span><span class="sxs-lookup"><span data-stu-id="5c7a7-158">Cloud Connector Edition (CCE)</span></span>
- <span data-ttu-id="5c7a7-159">Skype для бизнеса для Windows Phone</span><span class="sxs-lookup"><span data-stu-id="5c7a7-159">Skype for Business for Windows Phone</span></span>

### <a name="exceptions"></a><span data-ttu-id="5c7a7-160">Exceptions</span><span class="sxs-lookup"><span data-stu-id="5c7a7-160">Exceptions</span></span>

#### <a name="lync-server-2013"></a><span data-ttu-id="5c7a7-161">Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5c7a7-161">Lync Server 2013</span></span>

<span data-ttu-id="5c7a7-162">Lync Server 2013 зависит от версии Windows Fabric 1.0.</span><span class="sxs-lookup"><span data-stu-id="5c7a7-162">Lync Server 2013 takes a dependency on Windows Fabric version 1.0.</span></span>  <span data-ttu-id="5c7a7-163">На этапе разработки Lync Server 2013 Windows Fabric 1.0 была выбрана для своей убедительной и новой распределенной архитектуры для обеспечения репликации, высокой доступности и допуска неисправностей.</span><span class="sxs-lookup"><span data-stu-id="5c7a7-163">In the design phase for Lync Server 2013, Windows Fabric 1.0 was chosen for its compelling and new distributed architecture to provide replication, high availability, and fault tolerance.</span></span>  <span data-ttu-id="5c7a7-164">Со временем Skype для бизнеса Server и Windows Fabric значительно улучшили эту совместную архитектуру, значительно перепроектив ее в последующих версиях.</span><span class="sxs-lookup"><span data-stu-id="5c7a7-164">Over time, both Skype for Business Server and Windows Fabric have greatly improved this joint architecture with significant re-design in subsequent versions.</span></span>  <span data-ttu-id="5c7a7-165">Например, в current Skype for Business 2015 Server используется Windows Fabric 3.0.</span><span class="sxs-lookup"><span data-stu-id="5c7a7-165">Current Skype for Business 2015 Server uses Windows Fabric 3.0, for example.</span></span>

<span data-ttu-id="5c7a7-166">К сожалению, Windows Fabric 1.0 **не поддерживает TLS 1.2.  Тем не менее, мы будем обновлять Lync Server 2013 для работы с TLS 1.2**.</span><span class="sxs-lookup"><span data-stu-id="5c7a7-166">Unfortunately, Windows Fabric 1.0 **does not support TLS 1.2.  However, we will be updating Lync Server 2013 to work with TLS 1.2**.</span></span> <span data-ttu-id="5c7a7-167">Это будет в следующем накопительном обновлении для Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="5c7a7-167">This will be coming in the next Cumulative Update for Lync Server 2013.</span></span>  <span data-ttu-id="5c7a7-168">Мы предоставляем поддержку TLS 1.2 для обеспечения совместной жизни, миграции, федерации и гибридных сценариев.</span><span class="sxs-lookup"><span data-stu-id="5c7a7-168">We're providing TLS 1.2 support to enable co-existence, migration, federation, and hybrid scenarios.</span></span>

<span data-ttu-id="5c7a7-169">Если вашей организации требуется отключить TLS 1.0 и 1.1 и в настоящее время используется Lync Server 2013, рекомендуется приступить к процессу планирования с возможностью переноса обновления на месте или переноса (новые пулы, перемещение пользователей) в Skype для бизнеса Server 2015 или более.</span><span class="sxs-lookup"><span data-stu-id="5c7a7-169">If your organization is required to disable TLS 1.0 and 1.1, and you currently use Lync Server 2013, we recommend you begin your planning process, with the possibility you may have to In-place upgrade or Side-by-Side migrate (new pools, move users) to Skype for Business Server 2015 or higher.</span></span>  <span data-ttu-id="5c7a7-170">Или вы можете ускорить миграцию в Skype для бизнеса Online.</span><span class="sxs-lookup"><span data-stu-id="5c7a7-170">Or you may want to accelerate migration to Skype for Business Online.</span></span>

#### <a name="call-quality-dashboard"></a><span data-ttu-id="5c7a7-171">Панель мониторинга качества звонка</span><span class="sxs-lookup"><span data-stu-id="5c7a7-171">Call Quality Dashboard</span></span>

<span data-ttu-id="5c7a7-172">Панель мониторинга качества вызовов локального вызова в настоящее время имеет зависимость от TLS 1.0 во время новой установки (при первой установке в локальной среде).</span><span class="sxs-lookup"><span data-stu-id="5c7a7-172">On-Premises Call Quality Dashboard currently has a dependency on TLS 1.0 during new install (first time installing into your On-Premises environments).</span></span>  <span data-ttu-id="5c7a7-173">В настоящее время мы исследуем эту проблему и планируем выпустить исправление в ближайшем будущем.</span><span class="sxs-lookup"><span data-stu-id="5c7a7-173">We are currently investigating this issue and plan to release a fix in the near future.</span></span>  <span data-ttu-id="5c7a7-174">Если планируется установить CQD, а также отключить TLS 1.0, рекомендуется сначала завершить установку CQD, а затем приступить к отключению TLS 1.0.</span><span class="sxs-lookup"><span data-stu-id="5c7a7-174">If you are planning to install CQD and also disable TLS 1.0, we recommend that you complete CQD installation first, and then proceed with TLS 1.0 disabling.</span></span>

#### <a name="skype-for-business-sdn-manager"></a><span data-ttu-id="5c7a7-175">Skype для бизнеса SDN Manager</span><span class="sxs-lookup"><span data-stu-id="5c7a7-175">Skype for Business SDN Manager</span></span>

<span data-ttu-id="5c7a7-176">Skype для бизнеса SDN Manager с SQL базы данных имеет зависимость от TLS 1.0 во время новой установки.</span><span class="sxs-lookup"><span data-stu-id="5c7a7-176">Skype for Business SDN Manager using SQL a database has a dependency on TLS 1.0 during new install.</span></span> <span data-ttu-id="5c7a7-177">Если вы планируете установить Skype для бизнеса SDN Manager с помощью SQL базы данных, а также отключить TLS 1.0, рекомендуется сначала завершить Skype для бизнеса SDN Manager, а затем приступить к отключению TLS 1.0.</span><span class="sxs-lookup"><span data-stu-id="5c7a7-177">If you are planning to install Skype for Business SDN Manager using SQL a database and also disable TLS 1.0, we recommend that you complete Skype for Business SDN Manager first, and then proceed with TLS 1.0 disabling.</span></span> <span data-ttu-id="5c7a7-178">В случае отключения TLS 1.0 до установки необходимо временно включить TLS 1.0 обратно в SQL Server сервере, который будет использоваться для установки базы данных Skype для бизнеса SDN Manager SQL.</span><span class="sxs-lookup"><span data-stu-id="5c7a7-178">In case TLS 1.0 was disabled prior to installation, you should temporarily enabled TLS 1.0 back in SQL Server backend server that will be used to host Skype for Business SDN Manager SQL database.</span></span>

#### <a name="third-party-devices"></a><span data-ttu-id="5c7a7-179">Сторонние устройства</span><span class="sxs-lookup"><span data-stu-id="5c7a7-179">Third-party devices</span></span>

<span data-ttu-id="5c7a7-180">На сторонних устройствах, таких как телефоны 3PIP, видеоконференциалы, обратные прокси-службы и балансиры нагрузки, убедитесь, что они могут поддерживать TLS 1.2, тщательно протестировать и при необходимости обратиться к поставщику.</span><span class="sxs-lookup"><span data-stu-id="5c7a7-180">On third-party devices such as 3PIP phones, Video conferencing, Reverse Proxies and Load Balancers, be sure to validate TLS 1.2 supportability, test carefully, and contact the vendor if needed.</span></span>

### <a name="federation-considerations-when-disabling-tls-1011-on-edge-servers"></a><span data-ttu-id="5c7a7-181">Соображения Федерации при отключении TLS 1.0/1.1 на edge-серверах</span><span class="sxs-lookup"><span data-stu-id="5c7a7-181">Federation considerations when disabling TLS 1.0/1.1 on Edge servers</span></span>

<span data-ttu-id="5c7a7-182">Необходимо тщательно планировать и учитывать влияние отключения TLS 1.0/1.1 на серверы Edge.</span><span class="sxs-lookup"><span data-stu-id="5c7a7-182">You must carefully plan for and consider the impact of disabling TLS 1.0/1.1 on your Edge servers.</span></span>  <span data-ttu-id="5c7a7-183">После отключения TLS 1.0 и 1.1 вы можете обнаружить, что другие организации больше не смогут федератироваться с вашей организацией.</span><span class="sxs-lookup"><span data-stu-id="5c7a7-183">Once TLS 1.0 and 1.1 are disabled, you may find that other organizations are no longer be able to federate with your organization.</span></span>

<span data-ttu-id="5c7a7-184">Для поддержания обратной совместимости с не исправленными (SfB 2015, Lync 2013) или более старыми (2010) внешними системами может быть включено TLS 1.0/1.1.</span><span class="sxs-lookup"><span data-stu-id="5c7a7-184">You may opt to keep TLS 1.0/1.1 enabled on your Edge servers to maintain backward compatibility with non-patched (SfB 2015, Lync 2013) or older (2010) external systems.</span></span>

<span data-ttu-id="5c7a7-185">Корпорация Майкрософт не может предоставить советы или рекомендации относительно того, относится ли ваша сеть Edge (или к какой-либо сети) к стандарту PCI; которые должны определяться отдельной компанией.</span><span class="sxs-lookup"><span data-stu-id="5c7a7-185">Microsoft cannot provide advice or recommendations on whether or not your Edge network (or any network) falls under PCI standard; that must be determined by the individual company.</span></span>

<span data-ttu-id="5c7a7-186">Skype для бизнеса Online сегодня способен на TLS 1.2, поэтому никакого влияния на гибридную и федерацию с Интернетом не ожидается.</span><span class="sxs-lookup"><span data-stu-id="5c7a7-186">Skype for Business Online is capable of TLS 1.2 today, so no impact to Hybrid/Federation with Online is expected.</span></span>

<span data-ttu-id="5c7a7-187">PIC (подключение к чату общего звонков) для службы потребителей Skype. Мы не ожидаем отключения TLS 1.0/1.1, чтобы повлиять на [подключение Skype;](../../deploy/deploy-skype-connectivity.md) Шлюзы MICROSOFT PIC уже способны к TLS 1.2.</span><span class="sxs-lookup"><span data-stu-id="5c7a7-187">PIC (Public IM Connectivity) to Skype Consumer service: We do not expect disabling TLS 1.0/1.1 to impact [Skype Connectivity](../../deploy/deploy-skype-connectivity.md); Microsoft PIC Gateways are already TLS 1.2 capable.</span></span>

## <a name="prerequisites-and-process"></a><span data-ttu-id="5c7a7-188">Необходимые условия и процесс</span><span class="sxs-lookup"><span data-stu-id="5c7a7-188">Prerequisites and process</span></span>

<span data-ttu-id="5c7a7-189">Кроме случаев, когда отмечено выше, после отключения серверов TLS 1.0 и 1.1 клиенты и устройства будут работать должным образом или вообще.</span><span class="sxs-lookup"><span data-stu-id="5c7a7-189">Except where noted above, once TLS 1.0 and 1.1 are disabled out-of-scope servers, clients and devices will longer function properly, or at all.</span></span> <span data-ttu-id="5c7a7-190">Это может означать, что необходимо приостановить и дождаться обновленных указаний от Корпорации Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="5c7a7-190">This may mean you need to pause and wait for updated guidance from Microsoft.</span></span> <span data-ttu-id="5c7a7-191">После того как вы будете удовлетворены тем, что вы соответствуете всем требованиям и имеете план устранения пробелов, продолжайте.</span><span class="sxs-lookup"><span data-stu-id="5c7a7-191">Once you are satisfied that you meet all requirements and have a plan to address gaps, proceed.</span></span>

<span data-ttu-id="5c7a7-192">На высоком уровне, в то время как Skype для бизнеса Server 2019 готов к процедуре установки, Skype для бизнеса Server 2015 потребует установки CU9, применяя предварительные обновления к .NET и SQL, развертывание ключей реестра предварительных условий и, наконец, отдельный раунд обновлений конфигурации ОС (например, отключение TLS 1.0 и 1.1 с помощью импорта файлов реестра).</span><span class="sxs-lookup"><span data-stu-id="5c7a7-192">At a high level, while Skype for Business Server 2019 is ready for procedure at install, Skype for Business Server 2015 will require that you install CU9, applying pre-requisite updates to .NET and SQL, deploying prerequisite registry keys, and finally a separate round of OS configuration updates (i.e. disabling TLS 1.0 and 1.1 via registry file import).</span></span> <span data-ttu-id="5c7a7-193">Крайне важно завершить установку всех необходимых условий, включая Skype для бизнеса Server 2015 CU6 HF2, до отключения TLS 1.0 и 1.1 на любом сервере в вашей среде.</span><span class="sxs-lookup"><span data-stu-id="5c7a7-193">It is critically important that you complete installation of all prerequisites, including Skype for Business Server 2015 CU6 HF2, prior to disabling TLS 1.0 and 1.1 on any server in your environment.</span></span> <span data-ttu-id="5c7a7-194">Каждый сервер Skype для бизнеса, включая роль Edge и SQL backends, требует обновлений.</span><span class="sxs-lookup"><span data-stu-id="5c7a7-194">Every Skype for Business server, including Edge role and SQL Backends, requires the updates.</span></span> <span data-ttu-id="5c7a7-195">Кроме того, убедитесь, что все поддерживаемые (в области) клиенты были обновлены до необходимых минимальных версий.</span><span class="sxs-lookup"><span data-stu-id="5c7a7-195">Also ensure that all supported (in-scope) clients have been updated to the required minimum versions.</span></span> <span data-ttu-id="5c7a7-196">Не забудьте также обновить рабочие станции управления.</span><span class="sxs-lookup"><span data-stu-id="5c7a7-196">Don’t forget to update management workstations as well.</span></span>

<span data-ttu-id="5c7a7-197">Мы хотим следовать обычному порядку операций "наизнано" для обновления серверов Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="5c7a7-197">We want to follow the usual order of operations of "inside out" for upgrading Skype for Business servers.</span></span> <span data-ttu-id="5c7a7-198">Относитесь к пулам Director, сохраняемой беседе и парным пулам таким же образом, как обычно.</span><span class="sxs-lookup"><span data-stu-id="5c7a7-198">Treat Director pools, Persistent chat, and Paired Pools in the same manner you normally would.</span></span> <span data-ttu-id="5c7a7-199">Порядок и методы обновления здесь [и](topology.md) [здесь.](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015)</span><span class="sxs-lookup"><span data-stu-id="5c7a7-199">Order and methods for upgrade are covered [here](topology.md) and [here](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015).</span></span>

### <a name="high-level-process"></a><span data-ttu-id="5c7a7-200">Процесс высокого уровня</span><span class="sxs-lookup"><span data-stu-id="5c7a7-200">High-level process</span></span>

1. <span data-ttu-id="5c7a7-201">Проверьте все действия в лаборатории перед настройкой производственных серверов.</span><span class="sxs-lookup"><span data-stu-id="5c7a7-201">Test all steps in your lab prior to configuring production servers.</span></span>
2. <span data-ttu-id="5c7a7-202">Копирование и сохранение копии экспортируемого реестра на каждом отдельном сервере, который будет обновляться.</span><span class="sxs-lookup"><span data-stu-id="5c7a7-202">Back up and preserve a copy of exported registry on each and every individual server to be updated.</span></span> <span data-ttu-id="5c7a7-203">Вы не можете обмениваться реестрами между серверами; они содержат уникальные клавиши на основе машин.</span><span class="sxs-lookup"><span data-stu-id="5c7a7-203">You cannot share registries between servers; they contain unique machine-based keys.</span></span>
3. <span data-ttu-id="5c7a7-204">Обновление всех серверов Skype для бизнеса 2015 до cu9 или более высокой.</span><span class="sxs-lookup"><span data-stu-id="5c7a7-204">Upgrade all Skype for Business 2015 servers to CU9 or higher.</span></span> <span data-ttu-id="5c7a7-205">Для Skype для бизнеса Server 2019 обновление до cu1 или выше.</span><span class="sxs-lookup"><span data-stu-id="5c7a7-205">For Skype for Business Server 2019, upgrade to CU1 or higher.</span></span>
4. <span data-ttu-id="5c7a7-206">Установите все необходимые условия на все серверы.</span><span class="sxs-lookup"><span data-stu-id="5c7a7-206">Install all prerequisites to all servers.</span></span>
5. <span data-ttu-id="5c7a7-207">Развертывание необходимых ключей реестра.</span><span class="sxs-lookup"><span data-stu-id="5c7a7-207">Deploy prerequisite registry keys.</span></span>
6. <span data-ttu-id="5c7a7-208">Убедитесь, что все клиенты в области обновляются.</span><span class="sxs-lookup"><span data-stu-id="5c7a7-208">Ensure that all in-scope clients are updated.</span></span>
7. <span data-ttu-id="5c7a7-209">Отключить TLS 1.0 и 1.1 с помощью импорта реестра.</span><span class="sxs-lookup"><span data-stu-id="5c7a7-209">Disable TLS 1.0 and 1.1 via registry import.</span></span>
8. <span data-ttu-id="5c7a7-210">Проверка того, что рабочие нагрузки функционируют так, как ожидалось.</span><span class="sxs-lookup"><span data-stu-id="5c7a7-210">Validate that workloads are functioning as expected.</span></span>
    - <span data-ttu-id="5c7a7-211">Если возникают проблемы, устранение и устранение неполадок или</span><span class="sxs-lookup"><span data-stu-id="5c7a7-211">If problems are encountered, troubleshoot and resolve, or</span></span>
    - <span data-ttu-id="5c7a7-212">Восстановление реестра со 2-й ступени для повторного включить TLS 1.0 и 1.1</span><span class="sxs-lookup"><span data-stu-id="5c7a7-212">Restore registry from step 2 to re-enable TLS 1.0 and 1.1</span></span>
9. <span data-ttu-id="5c7a7-213">Проверьте, используется ли только TLS 1.2.</span><span class="sxs-lookup"><span data-stu-id="5c7a7-213">Validate that only TLS 1.2 is being used.</span></span>

### <a name="install-prerequisites-to-all-servers"></a><span data-ttu-id="5c7a7-214">Установка необходимых условий для всех серверов</span><span class="sxs-lookup"><span data-stu-id="5c7a7-214">Install prerequisites to all servers</span></span>

<span data-ttu-id="5c7a7-215">Перед отключением TLS 1.0 и 1.1 на уровне операционной системы в развертываниях Skype для бизнеса Server 2015 требуется масштабное обновление зависимости.</span><span class="sxs-lookup"><span data-stu-id="5c7a7-215">Extensive dependency updating is required before you begin to disable TLS 1.0 and 1.1 at the operating system level in your Skype for Business Server 2015 deployments.</span></span> <span data-ttu-id="5c7a7-216">Ниже приводится минимум версий, которые могут поддерживать TLS 1.2.</span><span class="sxs-lookup"><span data-stu-id="5c7a7-216">The following are the minimum versions that can support TLS 1.2.</span></span> <span data-ttu-id="5c7a7-217">Перед отключением TLS 1.0 и 1.1 разверните все необходимые обновления на каждом сервере Skype для бизнеса в среде.</span><span class="sxs-lookup"><span data-stu-id="5c7a7-217">Deploy all prerequisite updates across every Skype for Business server in your environment before you begin disabling TLS 1.0 and 1.1.</span></span>

- <span data-ttu-id="5c7a7-218">Skype для бизнеса Server 2015 CU9 6.0.9319.548 (май 2019 г.) или выше</span><span class="sxs-lookup"><span data-stu-id="5c7a7-218">Skype for Business Server 2015 CU9 6.0.9319.548 (May 2019) or higher</span></span>
- <span data-ttu-id="5c7a7-219">[платформа .NET Framework 4.7](https://www.microsoft.com/download/details.aspx?id=55167) или выше с включенной в реестр SchUseStrongCrypto (приведен ниже)</span><span class="sxs-lookup"><span data-stu-id="5c7a7-219">[.NET Framework 4.7](https://www.microsoft.com/download/details.aspx?id=55167) or higher with SchUseStrongCrypto enabled in the registry (provided below)</span></span>
- <span data-ttu-id="5c7a7-220">SQL должны быть обновлены на всех серверах и серверах Skype для бизнеса 2015.</span><span class="sxs-lookup"><span data-stu-id="5c7a7-220">SQL must be updated on all Skype for Business 2015 servers and backends.</span></span> <span data-ttu-id="5c7a7-221">Сначала обновим корпоративный SQL, а затем соответствующие FES.</span><span class="sxs-lookup"><span data-stu-id="5c7a7-221">Update Enterprise Edition Pool SQL Backends first, then their respective FEs.</span></span> 
    - <span data-ttu-id="5c7a7-222">[SQL Server 2014 SP1 + CU5](https://support.microsoft.com/help/3130926), или выше / SQL Server 2012 SP2 + CU16 или выше / [SQL Server 2014 RTM + CU12](https://support.microsoft.com/help/3130923/cumulative-update-12-for-sql-server-2014), или выше / SQL Server 2014 SP2</span><span class="sxs-lookup"><span data-stu-id="5c7a7-222">[SQL Server 2014 SP1 + CU5](https://support.microsoft.com/help/3130926), or higher / SQL Server 2012 SP2 + CU16 or higher / [SQL Server 2014 RTM + CU12](https://support.microsoft.com/help/3130923/cumulative-update-12-for-sql-server-2014), or higher / SQL Server 2014 SP2</span></span>
     - [<span data-ttu-id="5c7a7-223">SQL Server родной клиент для SQL Server 2012 г.</span><span class="sxs-lookup"><span data-stu-id="5c7a7-223">SQL Server Native Client for SQL Server 2012</span></span>](https://www.microsoft.com/download/details.aspx?id=50402)
     - <span data-ttu-id="5c7a7-224">[Драйвер Microsoft ODBC 11 для SQL Server](https://www.microsoft.com/download/details.aspx?id=36434)или выше</span><span class="sxs-lookup"><span data-stu-id="5c7a7-224">[Microsoft ODBC Driver 11 for SQL Server](https://www.microsoft.com/download/details.aspx?id=36434), or higher</span></span>
     - [<span data-ttu-id="5c7a7-225">Общие объекты управления для SQL Server 2014 SP2</span><span class="sxs-lookup"><span data-stu-id="5c7a7-225">Shared Management Objects for SQL Server 2014 SP2</span></span>](https://www.microsoft.com/download/details.aspx?id=53164)
     - [<span data-ttu-id="5c7a7-226">SQLSysClrTypes для SQL 2014 SP2</span><span class="sxs-lookup"><span data-stu-id="5c7a7-226">SQLSysClrTypes for SQL server 2014 SP2</span></span>](https://www.microsoft.com/download/details.aspx?id=42295)

### <a name="basic-steps-to-install-pre-requisites-in-recommended-order-of-operations"></a><span data-ttu-id="5c7a7-227">Основные действия по установке предварительных условий в рекомендуемом порядке операций</span><span class="sxs-lookup"><span data-stu-id="5c7a7-227">Basic steps to install pre-requisites, in recommended order of operations</span></span>

1. <span data-ttu-id="5c7a7-228">Установите обновление Skype для бизнеса Server CU9 на все серверы.</span><span class="sxs-lookup"><span data-stu-id="5c7a7-228">Install the Skype for Business Server CU9 update to all servers.</span></span> 
    1. <span data-ttu-id="5c7a7-229">Установите обновление на компоненты с помощью обновления.</span><span class="sxs-lookup"><span data-stu-id="5c7a7-229">Install the update to components using the updater.</span></span>
    2. <span data-ttu-id="5c7a7-230">Обновление баз данных в соответствии с задокументированными процедурами.</span><span class="sxs-lookup"><span data-stu-id="5c7a7-230">Update databases according to documented procedures.</span></span> <span data-ttu-id="5c7a7-231">Для Skype для бизнеса Server 2015 см. в руб. KB [3061064.](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015)</span><span class="sxs-lookup"><span data-stu-id="5c7a7-231">For Skype for Business Server 2015, see KB [3061064](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015).</span></span>
    3. <span data-ttu-id="5c7a7-232">Проверка функциональных возможностей продукта в развертывании до перехода к любым другим изменениям.</span><span class="sxs-lookup"><span data-stu-id="5c7a7-232">Validate product functionality in the deployment prior to moving forward with any other changes.</span></span>
2. <span data-ttu-id="5c7a7-233">Скачайте автономный установщик .NET 4.7.</span><span class="sxs-lookup"><span data-stu-id="5c7a7-233">Download .NET 4.7 Offline Installer.</span></span> 
    1. <span data-ttu-id="5c7a7-234">Справка: [https://www.microsoft.com/download/details.aspx?id=55167](https://www.microsoft.com/download/details.aspx?id=55167)</span><span class="sxs-lookup"><span data-stu-id="5c7a7-234">Reference: [https://www.microsoft.com/download/details.aspx?id=55167](https://www.microsoft.com/download/details.aspx?id=55167)</span></span>
    2. <span data-ttu-id="5c7a7-235">Убедитесь, что службы Skype для бизнеса Server 2015 остановлены на переднем сервере.</span><span class="sxs-lookup"><span data-stu-id="5c7a7-235">Ensure that Skype for Business Server 2015 services are stopped on the Front End server.</span></span>
    3. <span data-ttu-id="5c7a7-236">Справка: [https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015)</span><span class="sxs-lookup"><span data-stu-id="5c7a7-236">Reference: [https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015)</span></span>
    4. <span data-ttu-id="5c7a7-237">Ex (Стандартное издание): ```Stop-CsWindowsService```</span><span class="sxs-lookup"><span data-stu-id="5c7a7-237">Ex (Standard Edition): ```Stop-CsWindowsService```</span></span>
    5. <span data-ttu-id="5c7a7-238">Ex (Enterprise Edition): ```Invoke-CsComputerFailover```</span><span class="sxs-lookup"><span data-stu-id="5c7a7-238">Ex (Enterprise Edition): ```Invoke-CsComputerFailover```</span></span>
    6. <span data-ttu-id="5c7a7-239">Запустите пакет установщика.</span><span class="sxs-lookup"><span data-stu-id="5c7a7-239">Run the installer package.</span></span>
    7. <span data-ttu-id="5c7a7-240">Перезагрузите сервер.</span><span class="sxs-lookup"><span data-stu-id="5c7a7-240">Reboot the server.</span></span>
3. <span data-ttu-id="5c7a7-241">Обновление SQL Express 2014 на всех серверах.</span><span class="sxs-lookup"><span data-stu-id="5c7a7-241">Update SQL Express 2014 on all servers.</span></span> 
    1. <span data-ttu-id="5c7a7-242">Справка: [https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server](https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server)</span><span class="sxs-lookup"><span data-stu-id="5c7a7-242">Reference: [https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server](https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server)</span></span>
    2. <span data-ttu-id="5c7a7-243">Загрузка SQL 2014 SP2</span><span class="sxs-lookup"><span data-stu-id="5c7a7-243">Download SQL 2014 SP2</span></span> 
        - <span data-ttu-id="5c7a7-244">Справка: [https://www.microsoft.com/download/details.aspx?id=53168](https://www.microsoft.com/download/details.aspx?id=53168)</span><span class="sxs-lookup"><span data-stu-id="5c7a7-244">Reference: [https://www.microsoft.com/download/details.aspx?id=53168](https://www.microsoft.com/download/details.aspx?id=53168)</span></span>
    3. <span data-ttu-id="5c7a7-245">Скопируйте носителя установки в папку на сервере (Ex: C:\01_2014SqlSp2)</span><span class="sxs-lookup"><span data-stu-id="5c7a7-245">Copy the installation media to a folder on the server (Ex: C:\01_2014SqlSp2)</span></span>
    4. <span data-ttu-id="5c7a7-246">Убедитесь, что службы Skype для бизнеса Server 2015 остановлены на переднем сервере</span><span class="sxs-lookup"><span data-stu-id="5c7a7-246">Ensure Skype for Business Server 2015 services are stopped on the Front End server</span></span> 
        - <span data-ttu-id="5c7a7-247">Ex (Стандартное издание): ```Stop-CsWindowsService```</span><span class="sxs-lookup"><span data-stu-id="5c7a7-247">Ex (Standard Edition): ```Stop-CsWindowsService```</span></span>
        - <span data-ttu-id="5c7a7-248">Ex (Enterprise Edition): ```Invoke-CsComputerFailover```</span><span class="sxs-lookup"><span data-stu-id="5c7a7-248">Ex (Enterprise Edition): ```Invoke-CsComputerFailover```</span></span>
    5. <span data-ttu-id="5c7a7-249">Откройте командный запрос администратора и обновим все установленные компоненты и экземпляры</span><span class="sxs-lookup"><span data-stu-id="5c7a7-249">Open an Admin Command Prompt, and upgrade all installed components and instances</span></span> 
        - <span data-ttu-id="5c7a7-250">Пример: C:\01_2014SqlSp2\SQLServer2014SP2-KB3171021-x64-ENU.exe /qs /IAcceptSQLServerLicenseTerms /Action=Patch /AllInstances</span><span class="sxs-lookup"><span data-stu-id="5c7a7-250">Example: C:\01_2014SqlSp2\SQLServer2014SP2-KB3171021-x64-ENU.exe /qs /IAcceptSQLServerLicenseTerms /Action=Patch /AllInstances</span></span>
4. <span data-ttu-id="5c7a7-251">Обновление SQL родной клиент.</span><span class="sxs-lookup"><span data-stu-id="5c7a7-251">Update SQL Native Client.</span></span> 
    1. <span data-ttu-id="5c7a7-252">Справка. [https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server](https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server) .</span><span class="sxs-lookup"><span data-stu-id="5c7a7-252">Reference: [https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server](https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server).</span></span>
    2. <span data-ttu-id="5c7a7-253">Загрузка из [https://www.microsoft.com/download/details.aspx?id=50402](https://www.microsoft.com/download/details.aspx?id=50402)</span><span class="sxs-lookup"><span data-stu-id="5c7a7-253">Download from [https://www.microsoft.com/download/details.aspx?id=50402](https://www.microsoft.com/download/details.aspx?id=50402)</span></span>
    3. <span data-ttu-id="5c7a7-254">Убедитесь, что службы Skype для бизнеса Server 2015 остановлены на переднем сервере.</span><span class="sxs-lookup"><span data-stu-id="5c7a7-254">Ensure Skype for Business Server 2015 services are stopped on the Front End server.</span></span> 
        - <span data-ttu-id="5c7a7-255">Ex (Стандартное издание): ```Stop-CsWindowsServices```</span><span class="sxs-lookup"><span data-stu-id="5c7a7-255">Ex (Standard Edition): ```Stop-CsWindowsServices```</span></span>
        - <span data-ttu-id="5c7a7-256">Ex (Enterprise Edition): ```Invoke-CsComputerFailover```</span><span class="sxs-lookup"><span data-stu-id="5c7a7-256">Ex (Enterprise Edition): ```Invoke-CsComputerFailover```</span></span>
    4. <span data-ttu-id="5c7a7-257">Остановка SQL установленных экземпляров</span><span class="sxs-lookup"><span data-stu-id="5c7a7-257">Stop the SQL instances installed from running</span></span> 
        - <span data-ttu-id="5c7a7-258">Ex: ```Get-Service 'MSSQL$RTCLOCAL' | Stop-Service```</span><span class="sxs-lookup"><span data-stu-id="5c7a7-258">Ex: ```Get-Service 'MSSQL$RTCLOCAL' | Stop-Service```</span></span>
        - <span data-ttu-id="5c7a7-259">Ex: ```Get-Service 'MSSQL$LYNCLOCAL' | Stop-Service```</span><span class="sxs-lookup"><span data-stu-id="5c7a7-259">Ex: ```Get-Service 'MSSQL$LYNCLOCAL' | Stop-Service```</span></span>
        - <span data-ttu-id="5c7a7-260">Ex (только стандартное издание): ```Get-Service 'MSSQL$RTC' | Stop-Service```</span><span class="sxs-lookup"><span data-stu-id="5c7a7-260">Ex (Standard Edition Only): ```Get-Service 'MSSQL$RTC' | Stop-Service```</span></span>
    5. <span data-ttu-id="5c7a7-261">Установите обновление.</span><span class="sxs-lookup"><span data-stu-id="5c7a7-261">Install the update.</span></span>
5. <span data-ttu-id="5c7a7-262">Обновление драйвера ODBC 11 для SQL Server для поддержки TLS 1.2 (KB [3135244).](https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server)</span><span class="sxs-lookup"><span data-stu-id="5c7a7-262">Update ODBC Driver 11 for SQL Server to include support for TLS 1.2 (KB [3135244](https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server)).</span></span>
    1. <span data-ttu-id="5c7a7-263">Скачайте [драйвер ODBC 11 для SQL Server - Windows](https://www.microsoft.com/download/confirmation.aspx?id=36434).</span><span class="sxs-lookup"><span data-stu-id="5c7a7-263">Download [ODBC Driver 11 for SQL Server - Windows](https://www.microsoft.com/download/confirmation.aspx?id=36434).</span></span>
    2. <span data-ttu-id="5c7a7-264">Убедитесь, что службы Skype для бизнеса Server 2015 остановлены на переднем сервере.</span><span class="sxs-lookup"><span data-stu-id="5c7a7-264">Ensure that Skype for Business Server 2015 services are stopped on the Front End server.</span></span>
        - <span data-ttu-id="5c7a7-265">Пример (стандартное издание): ```Stop-CsWindowsService```</span><span class="sxs-lookup"><span data-stu-id="5c7a7-265">Example (Standard Edition): ```Stop-CsWindowsService```</span></span>
        - <span data-ttu-id="5c7a7-266">Пример (Корпоративная версия): ```Invoke-CsComputerFailover```</span><span class="sxs-lookup"><span data-stu-id="5c7a7-266">Example (Enterprise Edition): ```Invoke-CsComputerFailover```</span></span>
    3. <span data-ttu-id="5c7a7-267">Установите обновление.</span><span class="sxs-lookup"><span data-stu-id="5c7a7-267">Install the update.</span></span>
6. <span data-ttu-id="5c7a7-268">Развертывание необходимых ключей реестра.</span><span class="sxs-lookup"><span data-stu-id="5c7a7-268">Deploy prerequisite registry keys.</span></span>

### <a name="pre-requisite-registry-keys"></a><span data-ttu-id="5c7a7-269">Клавиши предварительного реестра</span><span class="sxs-lookup"><span data-stu-id="5c7a7-269">Pre-requisite registry keys</span></span>

<span data-ttu-id="5c7a7-270">Скопируйте или вклейте следующий тест в блокнот и переименуйте TLSPreReq.reg или имя по вашему выбору, а затем импортируйте:</span><span class="sxs-lookup"><span data-stu-id="5c7a7-270">Copy/paste the following test into Notepad and rename TLSPreReq.reg or a name of your choice, then import:</span></span>

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

<span data-ttu-id="5c7a7-271">Для SQL для корпоративных пулов выпусков необходимо рассматривать предварительные условия и отключение TLS как любые обновления SQL или ОС; обратитесь к: [https://docs.microsoft.com/skypeforbusiness/manage/topology/patch-or-update-a-back-end-or-standard-edition-server](https://docs.microsoft.com/skypeforbusiness/manage/topology/patch-or-update-a-back-end-or-standard-edition-server)</span><span class="sxs-lookup"><span data-stu-id="5c7a7-271">For SQL back ends for Enterprise Edition Pools, prerequisites and TLS disable should be treated as any SQL or OS updates would; refer to: [https://docs.microsoft.com/skypeforbusiness/manage/topology/patch-or-update-a-back-end-or-standard-edition-server](https://docs.microsoft.com/skypeforbusiness/manage/topology/patch-or-update-a-back-end-or-standard-edition-server)</span></span>

<span data-ttu-id="5c7a7-272">Хотя необходимое приложение и действия по отключению TLS можно объединить, мы настоятельно рекомендуем применять все необходимые условия перед началом работы с отключением TLS 1.0 и 1.1 на уровне операционной системы.</span><span class="sxs-lookup"><span data-stu-id="5c7a7-272">While both the prerequisite application and TLS disabling steps can be combined, we strongly recommend all prerequisites be applied before proceeding with disabling of TLS 1.0 and 1.1 at the operating system level.</span></span> <span data-ttu-id="5c7a7-273">Оптимальный подход заключается в подготовке среды путем развертывания всех необходимых условий, проверки правильности и правильности всех рабочих нагрузок, а затем отключения TLS 1.0/1.1 в более позднее время.</span><span class="sxs-lookup"><span data-stu-id="5c7a7-273">The best practice approach would be to prepare the environment by deploying all prerequisites, validating that workloads all function correctly and as expected, and then proceeding with TLS 1.0/1.1 disable at a later time.</span></span>

### <a name="disable-tls-10-and-11-via-registry-import"></a><span data-ttu-id="5c7a7-274">Отключение TLS 1.0 и 1.1 с помощью импорта реестра</span><span class="sxs-lookup"><span data-stu-id="5c7a7-274">Disable TLS 1.0 and 1.1 via registry import</span></span>

<span data-ttu-id="5c7a7-275">Прежде чем приступить к следующим шагам, убедитесь, что вы выполнили все необходимые условия и обновили *Skype для бизнес-серверов.*</span><span class="sxs-lookup"><span data-stu-id="5c7a7-275">Before you proceed with the next steps, *make sure you have completed all prerequisites and updated Skype for Business Servers*.</span></span>

<span data-ttu-id="5c7a7-276">Скопируйте следующий текст в файл Блокнот и переименуйте **его в TLSDisable.reg:**</span><span class="sxs-lookup"><span data-stu-id="5c7a7-276">Copy the following text into a Notepad file and rename it **TLSDisable.reg**:</span></span>

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

<span data-ttu-id="5c7a7-277">Импорт файла .reg на каждом сервере, который необходимо отключить TLS 1.0 и 1.1.</span><span class="sxs-lookup"><span data-stu-id="5c7a7-277">Import the .reg file on each server you wish to disable TLS 1.0 and 1.1.</span></span> <span data-ttu-id="5c7a7-278">Перезагрузите сервер.</span><span class="sxs-lookup"><span data-stu-id="5c7a7-278">Reboot the server.</span></span> <span data-ttu-id="5c7a7-279">После того как службы вернулись в режиме онлайн, переехав на следующий сервер.</span><span class="sxs-lookup"><span data-stu-id="5c7a7-279">Once the services have come back online, move to the next server.</span></span> <span data-ttu-id="5c7a7-280">Подход к корпоративным пулам выпусков тот же, что и для любого обновления ОС.</span><span class="sxs-lookup"><span data-stu-id="5c7a7-280">The approach for Enterprise Edition Pools is the same you would take for any OS update.</span></span>

<span data-ttu-id="5c7a7-281">Возможно, вы заметили, что мы делаем больше, чем просто отключение TLS 1.0 и 1.1 здесь.</span><span class="sxs-lookup"><span data-stu-id="5c7a7-281">You may have noticed we are doing more than just disabling TLS 1.0 and 1.1 here.</span></span> <span data-ttu-id="5c7a7-282">Мы поддерживаем повторное заказ cipher Suite (как показано выше) и отключение некоторых старых слабых шифров.</span><span class="sxs-lookup"><span data-stu-id="5c7a7-282">We are supporting Cipher Suite re-order (as shown above) and the disabling of some older weak ciphers.</span></span> <span data-ttu-id="5c7a7-283">Мы впервые официально поддерживаем эти изменения в API SCHANNEL и Crypto в Skype для бизнеса Server, и важно отметить, что эти изменения являются единственными, которые мы поддерживаем и протестировали в настоящее время.</span><span class="sxs-lookup"><span data-stu-id="5c7a7-283">This is the first time we have officially supported these changes to SCHANNEL and Crypto API on Skype for Business Server, and it is important to note that these changes are the only ones we support and have tested at this time.</span></span> <span data-ttu-id="5c7a7-284">Мы можем рассмотреть дополнительные конфигурации в будущем, но пока, пожалуйста, не измените файл импорта реестра в реализации.</span><span class="sxs-lookup"><span data-stu-id="5c7a7-284">We may consider additional configurations in the future, but for now, please do not modify the registry import file in your implementation.</span></span>

### <a name="validate-that-workloads-are-functioning-as-expected"></a><span data-ttu-id="5c7a7-285">Проверка того, что рабочие нагрузки функционируют так, как ожидалось</span><span class="sxs-lookup"><span data-stu-id="5c7a7-285">Validate that workloads are functioning as expected</span></span>

<span data-ttu-id="5c7a7-286">После отключения TLS 1.0 и 1.1 в вашей среде убедитесь, что все основные рабочие нагрузки будут функционировать так, как ожидалось, такие как im & Presence, вызовы P2P, Корпоративная голосовая связь и т.д.</span><span class="sxs-lookup"><span data-stu-id="5c7a7-286">Once TLS 1.0 and 1.1 have been disabled in your environment, ensure that all your main workloads are functioning as expected, such as IM & Presence, P2P calls, Enterprise Voice, etc.</span></span>

<span data-ttu-id="5c7a7-287">**Проверка использования только TLS 1.2**</span><span class="sxs-lookup"><span data-stu-id="5c7a7-287">**Validate only TLS 1.2 is being used**</span></span>

<span data-ttu-id="5c7a7-288">Чтобы убедиться, что старые протоколы TLS 1.0 и 1.1 больше не используются, группа безопасности выполнит новый аудит трафика Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="5c7a7-288">Have your Security Team perform a new audit of Skype for Business traffic to ensure that the older protocols TLS 1.0 and 1.1 are no longer in use.</span></span>

<span data-ttu-id="5c7a7-289">Кроме того, вы можете использовать Internet Explorer для тестирования подключений TLS к веб-службам skype для бизнеса Server 2015 после отключения TLS 1.0 и TLS 1.1.</span><span class="sxs-lookup"><span data-stu-id="5c7a7-289">Alternatively, you can use Internet Explorer to test TLS connections to web services from Skype for Business Server 2015 after TLS 1.0 and TLS 1.1 have been disabled.</span></span>

1. <span data-ttu-id="5c7a7-290">Запуск Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="5c7a7-290">Launch Internet Explorer.</span></span>
2. <span data-ttu-id="5c7a7-291">Выберите **Параметры**  >  **Интернета Средства**.</span><span class="sxs-lookup"><span data-stu-id="5c7a7-291">Select **Tools** > **Internet Options**.</span></span>
3. <span data-ttu-id="5c7a7-292">Выберите **вкладку Advanced.**</span><span class="sxs-lookup"><span data-stu-id="5c7a7-292">Select the **Advanced** tab.</span></span>
4. <span data-ttu-id="5c7a7-293">В **параметрах** прокрутите вниз.</span><span class="sxs-lookup"><span data-stu-id="5c7a7-293">Under **Settings**, scroll to the bottom.</span></span>
5. <span data-ttu-id="5c7a7-294">Убедитесь, что включены TLS 1.0, TLS 1.1 и TLS 1.2.</span><span class="sxs-lookup"><span data-stu-id="5c7a7-294">Verify that TLS 1.0, TLS 1.1, and TLS 1.2 are enabled.</span></span>
6. <span data-ttu-id="5c7a7-295">Просмотрите URL-адрес внутренней веб-службы пула SfB 2015 (должен успешно подключиться).</span><span class="sxs-lookup"><span data-stu-id="5c7a7-295">Browse the Internal Web Service URL of your SfB 2015 pool (should connect successfully).</span></span>
7. <span data-ttu-id="5c7a7-296">Возвращайтесь в Internet Explorer и отключайте параметр **только для использования TLS 1.2.**</span><span class="sxs-lookup"><span data-stu-id="5c7a7-296">Go back into Internet Explorer and disable the option to **Use TLS 1.2** only.</span></span>
8. <span data-ttu-id="5c7a7-297">Снова просмотрите URL-адрес внутренней веб-службы пула SfB 2015 (если не удастся подключиться).</span><span class="sxs-lookup"><span data-stu-id="5c7a7-297">Browse the Internal Web Service URL of your SfB 2015 pool again (should fail to connect).</span></span>

![Параметры Интернета](../../media/internet-options.jpg)

## <a name="advanced-deployment-scenarios"></a><span data-ttu-id="5c7a7-299">Расширенные сценарии развертывания</span><span class="sxs-lookup"><span data-stu-id="5c7a7-299">Advanced deployment scenarios</span></span>

<span data-ttu-id="5c7a7-300">Так как для поддержки TLS 1.2 в Skype для бизнеса Server 2015 необходимы некоторые предпосылки для зависимостей, установка из RTM-мультимедиа не будет работать в любой системе, где отключены TLS 1.0 и 1.1.</span><span class="sxs-lookup"><span data-stu-id="5c7a7-300">Because some dependency prerequisites are required to support TLS 1.2 in Skype for Business Server 2015, installing from RTM media will fail on any system where TLS 1.0 and 1.1 have been disabled.</span></span>

<span data-ttu-id="5c7a7-301">**Развертывание серверов стандартных выпусков или корпоративных пулов выпусков после отключения TLS 1.0 и 1.1 в среде.**</span><span class="sxs-lookup"><span data-stu-id="5c7a7-301">**Deploying New Standard Edition Servers or Enterprise Edition Pools once TLS 1.0 and 1.1 have been disabled in your environment.**</span></span>

<span data-ttu-id="5c7a7-302">**Вариант 1:** Используйте [SmartSetup](../../deploy/install/install-skype-for-business-server.md).</span><span class="sxs-lookup"><span data-stu-id="5c7a7-302">**Option 1:** Use [SmartSetup](../../deploy/install/install-skype-for-business-server.md).</span></span> <span data-ttu-id="5c7a7-303">Обратите внимание, что мы обновляем SmartSetup для размещения обновленных SQL в будущем cu и будем обновлять эту статью в будущем.</span><span class="sxs-lookup"><span data-stu-id="5c7a7-303">Note that we are updating SmartSetup to accommodate the updated SQL binaries in a future CU, and will update this article in the future.</span></span>

<span data-ttu-id="5c7a7-304">**Вариант 2:** Предварительная установка локальных SQL экземпляров (RTCLOCAL и LYNCLOCAL)</span><span class="sxs-lookup"><span data-stu-id="5c7a7-304">**Option 2:** Pre-install local SQL instances (RTCLOCAL and LYNCLOCAL)</span></span>

1. <span data-ttu-id="5c7a7-305">Скачайте и скопируйте SQL Express 2014 SP2 (SQLEXPR_x64.exe) в локализованную папку fe.</span><span class="sxs-lookup"><span data-stu-id="5c7a7-305">Download and copy SQL Express 2014 SP2 (SQLEXPR_x64.exe) to local folder on FE.</span></span> <span data-ttu-id="5c7a7-306">Допустим, путь папки <SQL_FOLDER_PATH>.</span><span class="sxs-lookup"><span data-stu-id="5c7a7-306">Let’s say folder path <SQL_FOLDER_PATH>.</span></span>
2. <span data-ttu-id="5c7a7-307">Запустите PowerShell или командную подсказку и перейдите <SQL_FOLDER_PATH>.</span><span class="sxs-lookup"><span data-stu-id="5c7a7-307">Launch PowerShell or Command Prompt and navigate to <SQL_FOLDER_PATH>.</span></span>
3. <span data-ttu-id="5c7a7-308">Создайте экземпляр RTCLOCAL SQL, запуская команду ниже.</span><span class="sxs-lookup"><span data-stu-id="5c7a7-308">Create the RTCLOCAL SQL instance by running the command below.</span></span> <span data-ttu-id="5c7a7-309">Подождите, SQLEXPR_x64.exe закончится перед началом.</span><span class="sxs-lookup"><span data-stu-id="5c7a7-309">Wait until SQLEXPR_x64.exe finishes before proceeding:</span></span>

    <span data-ttu-id="5c7a7-310">SQLEXPR_x64.exe /Q /IACCEPTSQLSERVERLICENSETERMS /UPDATEENABLED=0 /HIDECONSOLE /ACTION=Install=FEATURES=SQLEngine,Tools /INSTANCENAME=RTCLOCAL/TCPENABLED=1 /SQLSVCACCOUNT="NT AUTHORITY\NetworkService" /SQLSYSADMINACCOUNTS="Builtin\Administrators" /BROWSERSVCSTARTUPTYPE="Automatic" /AGTSVCACCOUNT="NTAUTHORITY\NetworkService" /SQLSVCSTARTUPTYPE=Automati</span><span class="sxs-lookup"><span data-stu-id="5c7a7-310">SQLEXPR_x64.exe  /Q /IACCEPTSQLSERVERLICENSETERMS /UPDATEENABLED=0 /HIDECONSOLE /ACTION=Install /FEATURES=SQLEngine,Tools /INSTANCENAME=RTCLOCAL /TCPENABLED=1 /SQLSVCACCOUNT="NT AUTHORITY\NetworkService" /SQLSYSADMINACCOUNTS="Builtin\Administrators" /BROWSERSVCSTARTUPTYPE="Automatic" /AGTSVCACCOUNT="NTAUTHORITY\NetworkService" /SQLSVCSTARTUPTYPE=Automati</span></span>
1. <span data-ttu-id="5c7a7-311">Создайте экземпляр LYNCLOCAL SQL, запуская команду ниже.</span><span class="sxs-lookup"><span data-stu-id="5c7a7-311">Create the LYNCLOCAL SQL instance by running the command below.</span></span> <span data-ttu-id="5c7a7-312">Подождите, SQLEXPR_x64.exe завершится, прежде чем приступить к следующему шагу:</span><span class="sxs-lookup"><span data-stu-id="5c7a7-312">Wait until SQLEXPR_x64.exe finishes before proceeding to the next step:</span></span>

    <span data-ttu-id="5c7a7-313">SQLEXPR_x64.exe /Q /IACCEPTSQLSERVERLICENSETERMS /UPDATEENABLED=0 /HIDECONSOLE /ACTION=Install=FEATURES=SQLEngine,Tools /INSTANCENAME=LYNCLOCAL/TCPENABLED=1 /SQLSVCACCOUNT ="NT AUTHORITY\NetworkService" /SQLSYSADMINACCOUNTS="Builtin\Administrators" /BROWSERSVCSTARTUPTYPE="Automatic" /AGTSVCACCOUNT="NTAUTHORITY\NetworkService" /SQLSVCSTARTUPTYPE=Automatic</span><span class="sxs-lookup"><span data-stu-id="5c7a7-313">SQLEXPR_x64.exe /Q /IACCEPTSQLSERVERLICENSETERMS /UPDATEENABLED=0 /HIDECONSOLE /ACTION=Install /FEATURES=SQLEngine,Tools /INSTANCENAME=LYNCLOCAL /TCPENABLED=1 /SQLSVCACCOUNT="NT AUTHORITY\NetworkService" /SQLSYSADMINACCOUNTS="Builtin\Administrators" /BROWSERSVCSTARTUPTYPE="Automatic" /AGTSVCACCOUNT="NTAUTHORITY\NetworkService" /SQLSVCSTARTUPTYPE=Automatic</span></span>
1. <span data-ttu-id="5c7a7-314">Запуск установки Skype для бизнеса Server 2015 RTM.</span><span class="sxs-lookup"><span data-stu-id="5c7a7-314">Run Skype for Business Server 2015 RTM setup.</span></span>
2. <span data-ttu-id="5c7a7-315">Следуйте оставшимся шагам из раздела предварительных условий выше.</span><span class="sxs-lookup"><span data-stu-id="5c7a7-315">Follow the remaining steps from the prerequisites section above.</span></span>

<span data-ttu-id="5c7a7-316">**Вариант 3:** Кроме того, можно вручную заменить бинарии в локальном каталоге мультимедиа установки следующим образом:</span><span class="sxs-lookup"><span data-stu-id="5c7a7-316">**Option 3:** You may also manually replace binaries in a local installation media directory as follows:</span></span>

1. [<span data-ttu-id="5c7a7-317">Установка необходимых условий для Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="5c7a7-317">Install prerequisites for Skype for Business Server</span></span>](../../deploy/install/install-prerequisites.md)  
2. <span data-ttu-id="5c7a7-318">Установка .NET 4.7:</span><span class="sxs-lookup"><span data-stu-id="5c7a7-318">Install .NET 4.7:</span></span> 
      - <span data-ttu-id="5c7a7-319">**Примечание:** Мы впервые представили поддержку .NET 4.7 в Skype для бизнеса Server 2015 CU5 (6.0.9319.281).</span><span class="sxs-lookup"><span data-stu-id="5c7a7-319">**Note:** We first introduced support for .NET 4.7 in Skype for Business Server 2015 CU5 (6.0.9319.281).</span></span> <span data-ttu-id="5c7a7-320">Таким образом, в последующих шагах ниже мы будем обновлять основные компоненты до основной установки.</span><span class="sxs-lookup"><span data-stu-id="5c7a7-320">Therefore, in later steps below we will be updating Core Components prior to the main install.</span></span>
      - <span data-ttu-id="5c7a7-321">Скачать: https://www.microsoft.com/download/details.aspx?id=55167 .</span><span class="sxs-lookup"><span data-stu-id="5c7a7-321">Download: https://www.microsoft.com/download/details.aspx?id=55167.</span></span> 
      - <span data-ttu-id="5c7a7-322">Справка. Программное обеспечение, которое должно быть [установлено перед развертыванием Skype для бизнеса Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md#software-that-should-be-installed-before-a-skype-for-business-server-2015-deployment)</span><span class="sxs-lookup"><span data-stu-id="5c7a7-322">Reference: [Software that should be installed before a Skype for Business Server 2015 deployment](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md#software-that-should-be-installed-before-a-skype-for-business-server-2015-deployment)</span></span>
3. <span data-ttu-id="5c7a7-323">Копирование файлов ISO/папок:</span><span class="sxs-lookup"><span data-stu-id="5c7a7-323">Copy ISO Files/Folders:</span></span> 
    - <span data-ttu-id="5c7a7-324">При присоединении ISO Skype для бизнеса Server 2015 откройте корневой каталог диска, который он присоединен как (Ex: D: \) in File Explorer).</span><span class="sxs-lookup"><span data-stu-id="5c7a7-324">With the Skype for Business Server 2015 ISO attached, open the root directory of the drive it is attached as (Ex: D:\) in File Explorer.</span></span>
    - <span data-ttu-id="5c7a7-325">Скопируйте все папки и файлы в папку на локальном диске (Ex: C:\SkypeForBusiness2015ISO).</span><span class="sxs-lookup"><span data-stu-id="5c7a7-325">Copy all folders and files to a folder on a local disk (Ex: C:\SkypeForBusiness2015ISO).</span></span>
    - <span data-ttu-id="5c7a7-326">**Примечание:** Перед установкой компонентов необходимо обновить некоторые файлы для поддержки TLS 1.2.</span><span class="sxs-lookup"><span data-stu-id="5c7a7-326">**Note:** Prior to installing components, some files will need to be updated for support of TLS 1.2.</span></span>
4. <span data-ttu-id="5c7a7-327">Замените пакеты MSI/EXE:</span><span class="sxs-lookup"><span data-stu-id="5c7a7-327">Replace MSI/EXE Packages:</span></span> 
    - <span data-ttu-id="5c7a7-328">Замените существующие пакеты MSI и EXE в папке установки/amd64/на локальной машине.</span><span class="sxs-lookup"><span data-stu-id="5c7a7-328">Replace the existing MSI and EXE packages in the /Setup/amd64/ folder of the installation media on the local machine.</span></span>
    - <span data-ttu-id="5c7a7-329">SQL 2014 SP2 Express: https://www.microsoft.com/download/details.aspx?id=53167</span><span class="sxs-lookup"><span data-stu-id="5c7a7-329">SQL 2014 SP2 Express: https://www.microsoft.com/download/details.aspx?id=53167</span></span> 
        - <span data-ttu-id="5c7a7-330">Переименовать SQLEXPR_x64 на локальном компьютере и заменить существующий файл в папке Установки/amd64/средства установки.</span><span class="sxs-lookup"><span data-stu-id="5c7a7-330">Rename to SQLEXPR_x64 on the local machine, and replace the existing file in the Setup/amd64/ folder of the installation media.</span></span>
    - <span data-ttu-id="5c7a7-331">SQL родной клиент: https://www.microsoft.com/download/details.aspx?id=50402</span><span class="sxs-lookup"><span data-stu-id="5c7a7-331">SQL Native Client: https://www.microsoft.com/download/details.aspx?id=50402</span></span> 
        - <span data-ttu-id="5c7a7-332">**Примечание:** Переименуй это, sqlncli.msi, а затем замените существующий файл, существующий в папке Setup/amd64/of the installation media.</span><span class="sxs-lookup"><span data-stu-id="5c7a7-332">**Note:** Rename this if necessary to sqlncli.msi, and then replace the existing file that exists in the Setup/amd64/ folder of the installation media.</span></span>
    - <span data-ttu-id="5c7a7-333">SQL объекты управления: https://www.microsoft.com/download/details.aspx?id=53164</span><span class="sxs-lookup"><span data-stu-id="5c7a7-333">SQL Management Objects: https://www.microsoft.com/download/details.aspx?id=53164</span></span> 
        - <span data-ttu-id="5c7a7-334">**Примечание:** Пакет функций будет иметь множество элементов, которые можно скачать.</span><span class="sxs-lookup"><span data-stu-id="5c7a7-334">**Note:** The Feature pack will have a lot of items that can be downloaded.</span></span> <span data-ttu-id="5c7a7-335">Выберите для загрузки SharedManagementObjects.msi только.</span><span class="sxs-lookup"><span data-stu-id="5c7a7-335">Select to download SharedManagementObjects.msi only.</span></span>
        - <span data-ttu-id="5c7a7-336">**Примечание:** Замените существующий файл, существующий в папке установки/amd64/.</span><span class="sxs-lookup"><span data-stu-id="5c7a7-336">**Note:** Replace the existing file that exists in the Setup/amd64/ folder of the installation media.</span></span>
    - <span data-ttu-id="5c7a7-337">SQL типов CLR: https://www.microsoft.com/download/details.aspx?id=53164</span><span class="sxs-lookup"><span data-stu-id="5c7a7-337">SQL CLR Types: https://www.microsoft.com/download/details.aspx?id=53164</span></span> 
        - <span data-ttu-id="5c7a7-338">**Примечание:** Пакет функций будет иметь множество элементов, которые можно скачать.</span><span class="sxs-lookup"><span data-stu-id="5c7a7-338">**Note:** The Feature pack will have a lot of items that can be downloaded.</span></span> <span data-ttu-id="5c7a7-339">Выберите для загрузки CQLSysClrTypes.msi только</span><span class="sxs-lookup"><span data-stu-id="5c7a7-339">Select to download CQLSysClrTypes.msi only</span></span>
        - <span data-ttu-id="5c7a7-340">**Примечание.** Замените существующий файл, существующий в папке установки/amd64/.</span><span class="sxs-lookup"><span data-stu-id="5c7a7-340">**Note**: Replace the existing file that exists in the Setup/amd64/ folder of the installation media.</span></span>
5. <span data-ttu-id="5c7a7-341">Установка основных компонентов:</span><span class="sxs-lookup"><span data-stu-id="5c7a7-341">Install Core Components:</span></span> 
    - <span data-ttu-id="5c7a7-342">Запустите Setup.exe из папки Установки/amd64/средства установки.</span><span class="sxs-lookup"><span data-stu-id="5c7a7-342">Run Setup.exe from the Setup/amd64/ folder of the installation media.</span></span> <span data-ttu-id="5c7a7-343">Следуйте инструкциям по установке основных компонентов</span><span class="sxs-lookup"><span data-stu-id="5c7a7-343">Follow the instructions to install Core Components</span></span>
    - <span data-ttu-id="5c7a7-344">Закрыть основные компоненты.</span><span class="sxs-lookup"><span data-stu-id="5c7a7-344">Close Core Components.</span></span>
6. <span data-ttu-id="5c7a7-345">Обновление основных компонентов:</span><span class="sxs-lookup"><span data-stu-id="5c7a7-345">Update Core Components:</span></span> 
    - <span data-ttu-id="5c7a7-346">Скачайте установщик обновления Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="5c7a7-346">Download the Skype for Business Update Installer.</span></span>
    - <span data-ttu-id="5c7a7-347">Запустите установщик, чтобы обновить основные компоненты и установить счетчики производительности.</span><span class="sxs-lookup"><span data-stu-id="5c7a7-347">Run the installer to update Core Components and install the performance counters.</span></span>
    - <span data-ttu-id="5c7a7-348">**Примечание:** С выпуском CU6HF2 функция автоматического обновления в настоящее время устанавливается только до CU6.</span><span class="sxs-lookup"><span data-stu-id="5c7a7-348">**Note:** As of the release of CU6HF2, the auto-update feature currently only will install up to CU6.</span></span> <span data-ttu-id="5c7a7-349">Поэтому для обновления основных компонентов до 6.0.9319.516 необходимо запустить отдельно.</span><span class="sxs-lookup"><span data-stu-id="5c7a7-349">Therefore, the updater must be run separately to update Core Components to 6.0.9319.516.</span></span>
    - <span data-ttu-id="5c7a7-350">Справка: https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015</span><span class="sxs-lookup"><span data-stu-id="5c7a7-350">Reference: https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015</span></span>
7. <span data-ttu-id="5c7a7-351">Установка средств администрирования (необязательный):</span><span class="sxs-lookup"><span data-stu-id="5c7a7-351">Install Administrative Tools (Optional):</span></span> 
    - <span data-ttu-id="5c7a7-352">Это установит Microsoft SQL Server 2012 родной клиент, объекты управления SQL Server 2014 (x64) и типы CLR системы Майкрософт для SQL Server 2014 (x64) с помощью обновленных файлов.</span><span class="sxs-lookup"><span data-stu-id="5c7a7-352">This will install the Microsoft SQL Server 2012 Native Client, SQL Server 2014 Management Objects (x64), and Microsoft System CLR Types for SQL Server 2014 (x64) using the updated files.</span></span> <span data-ttu-id="5c7a7-353">Кроме того, панель топологии и панели управления Skype для бизнеса Server 2015 будет доступна на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="5c7a7-353">Additionally, the Skype for Business Server 2015 Topology Builder and Control Panel will be available on the local machine.</span></span>
8. <span data-ttu-id="5c7a7-354">Установка локального магазина конфигурации (шаг 1):</span><span class="sxs-lookup"><span data-stu-id="5c7a7-354">Install Local Configuration Store (Step 1):</span></span> 
     - <span data-ttu-id="5c7a7-355">Откройте мастер развертывания, щелкните Установите или обновите систему Skype для бизнес-серверов и нажмите кнопку **Выполнить** на шаге 1: Установите локальный магазин конфигурации.</span><span class="sxs-lookup"><span data-stu-id="5c7a7-355">Open the Deployment Wizard, click Install or Update Skype for Business Server System, and click on **Run** at Step 1: Install Local Configuration Store.</span></span>
     - <span data-ttu-id="5c7a7-356">Нажмите **кнопку Далее** в диалоговом окне **Install Local Configuration Store.**</span><span class="sxs-lookup"><span data-stu-id="5c7a7-356">Click **Next** in the **Install Local Configuration Store** dialog box.</span></span>
     <span data-ttu-id="5c7a7-357">![Установка диалогового окна Локального магазина конфигурации](../../media/local-configuration-store.png)</span><span class="sxs-lookup"><span data-stu-id="5c7a7-357">![Install Local Configuration Store dialog box](../../media/local-configuration-store.png)</span></span>
     - <span data-ttu-id="5c7a7-358">Просмотрите результаты и убедитесь, что состояние задачи завершено.</span><span class="sxs-lookup"><span data-stu-id="5c7a7-358">Review the results, and ensure that the Task Status is Completed.</span></span> <span data-ttu-id="5c7a7-359">Просмотрите результативный файл журнала, нажав **журнал Представления**.</span><span class="sxs-lookup"><span data-stu-id="5c7a7-359">Review the resulting log file by clicking **View Log**.</span></span>
     <span data-ttu-id="5c7a7-360">![Состояние задачи показывается как Завершено](../../media/local-configuration-task-completed.png)</span><span class="sxs-lookup"><span data-stu-id="5c7a7-360">![Task status shows as Completed](../../media/local-configuration-task-completed.png)</span></span>
     - <span data-ttu-id="5c7a7-361">Нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="5c7a7-361">Click **Finish**.</span></span>
9. <span data-ttu-id="5c7a7-362">Настройка или удаление компонентов Skype для бизнес-сервера (шаг 2):</span><span class="sxs-lookup"><span data-stu-id="5c7a7-362">Set up or remove Skype for Business Server Components (Step 2):</span></span>
    - <span data-ttu-id="5c7a7-363">Откройте мастер развертывания, щелкните Установите или обновите  **систему Skype для** бизнес-серверов и нажмите кнопку Выполнить на шаге 2: Настройка или удаление компонентов Skype для бизнес-серверов</span><span class="sxs-lookup"><span data-stu-id="5c7a7-363">Open the Deployment Wizard, click **Install or Update Skype for Business Server System**, and click **Run** at Step 2: Set up or Remove Skype for Business Server Components</span></span>
    - <span data-ttu-id="5c7a7-364">Нажмите **кнопку Далее** в диалоговом окне Настройка компонентов Skype для бизнес-серверов.</span><span class="sxs-lookup"><span data-stu-id="5c7a7-364">Click **Next** in the Set Up Skype for Business Server Components dialog box.</span></span>
    <span data-ttu-id="5c7a7-365">![окно Настройка компонентов Skype для бизнес-серверов](../../media/set-up-skype-for-business-server-components-window.png)</span><span class="sxs-lookup"><span data-stu-id="5c7a7-365">![the Set Up Skype for Business Server Components window](../../media/set-up-skype-for-business-server-components-window.png)</span></span>
    - <span data-ttu-id="5c7a7-366">Просмотрите журнал с помощью журнала View Log и проверьте, завершена ли установка без проблем.</span><span class="sxs-lookup"><span data-stu-id="5c7a7-366">Review the log using View Log, and validate that setup completed without issues.</span></span> 
    - <span data-ttu-id="5c7a7-367">Нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="5c7a7-367">Click **Finish**.</span></span>
10. <span data-ttu-id="5c7a7-368">Приступить к дополнительной установке и конфигурации по мере необходимости (на данном этапе можно возобновить обычные процедуры установки).</span><span class="sxs-lookup"><span data-stu-id="5c7a7-368">Proceed with additional installation and configuration as required (you can resume normal installation procedures at this point).</span></span>
