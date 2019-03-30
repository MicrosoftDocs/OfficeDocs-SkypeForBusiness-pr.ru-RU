---
title: Отключить протокол TLS 1.0/1.1 в Скайп для Business Server 2015
ms.reviewer: ''
ms.author: heidip
author: heidip
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: ab748733-6bad-4c93-8dda-db8d5271653d
description: 'Сводка: Подготовка к и реализовать отключение TLS 1.0 и 1.1 в вашей среде.'
ms.openlocfilehash: dc835a68e47f9fac6036724d92ad336ead795e50
ms.sourcegitcommit: 4266c1fbd8557bf2bf65447557ee8d597f90ccd3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/30/2019
ms.locfileid: "31012935"
---
# <a name="disable-tls-1011-in-skype-for-business-server-2015"></a><span data-ttu-id="35124-103">Отключить протокол TLS 1.0/1.1 в Скайп для Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="35124-103">Disable TLS 1.0/1.1 in Skype for Business Server 2015</span></span>

<span data-ttu-id="35124-104">В этой статье предназначен для предоставления необходимых рекомендаций для подготовки и реализации отключение TLS 1.0 и 1.1 в вашей среде.</span><span class="sxs-lookup"><span data-stu-id="35124-104">The purpose of this article is to provide the necessary guidance for you to prepare for and implement disabling TLS 1.0 and 1.1 in your environments.</span></span> <span data-ttu-id="35124-105">Этот процесс требует тщательного планирования и подготовки.</span><span class="sxs-lookup"><span data-stu-id="35124-105">This process requires extensive planning and preparation.</span></span> <span data-ttu-id="35124-106">Тщательно проверьте все сведения в этой статье при принятии плана для отключения TLS 1.0 и 1.1 для вашей организации.</span><span class="sxs-lookup"><span data-stu-id="35124-106">Please carefully review all of the information in this article as you make your plan to disable TLS 1.0 and 1.1 for your organization.</span></span> <span data-ttu-id="35124-107">Обратите внимание на то, что существует множество внешние зависимости и подключения к условия, которые могут повлиять на работу отключение TLS 1.0/1.1, необходимо сделать так тщательного планирования и тестирования.</span><span class="sxs-lookup"><span data-stu-id="35124-107">Note that there are many external dependencies and connectivity conditions that could be impacted by disabling TLS 1.0/1.1, so extensive planning and testing is warranted.</span></span>

## <a name="in-this-article"></a><span data-ttu-id="35124-108">В этой статье</span><span class="sxs-lookup"><span data-stu-id="35124-108">In this article</span></span>

- [<span data-ttu-id="35124-109">Фон и область действия</span><span class="sxs-lookup"><span data-stu-id="35124-109">Background and scope</span></span>](#background)
- [<span data-ttu-id="35124-110">Необходимые условия и процесс</span><span class="sxs-lookup"><span data-stu-id="35124-110">Prerequisites and process</span></span>](#prerequisites-and-process)
- [<span data-ttu-id="35124-111">Расширенные сценарии развертывания</span><span class="sxs-lookup"><span data-stu-id="35124-111">Advanced deployment scenarios</span></span>](#advanced-deployment-scenarios)

## <a name="background"></a><span data-ttu-id="35124-112">Общие сведения</span><span class="sxs-lookup"><span data-stu-id="35124-112">Background</span></span>

<span data-ttu-id="35124-113">Основной факторами для предоставления TLS 1.0 и 1.1 отключить поддержку для Скайп для Business Server локальной перечислены требования к Совет стандартов безопасности индустрии платежных карт (PCI) и федеральных стандартов обработки информации.</span><span class="sxs-lookup"><span data-stu-id="35124-113">The primary drivers for providing TLS 1.0 and 1.1 disable support for Skype for Business Server On-Premises are Payment Card Industry (PCI) Security Standards Council and Federal Information Processing Standards requirements.</span></span> <span data-ttu-id="35124-114">Требования к PCI Дополнительные сведения можно найти [здесь](https://blog.pcisecuritystandards.org/are-you-ready-for-30-june-2018-sayin-goodbye-to-ssl-early-tls).</span><span class="sxs-lookup"><span data-stu-id="35124-114">More information for PCI requirements can be found [here](https://blog.pcisecuritystandards.org/are-you-ready-for-30-june-2018-sayin-goodbye-to-ssl-early-tls).</span></span>  <span data-ttu-id="35124-115">Корпорация Майкрософт не предоставляет рекомендации на ли вашей организации должны соблюдать эти или другие требования.</span><span class="sxs-lookup"><span data-stu-id="35124-115">Microsoft cannot provide guidance on whether or not your organization is required to adhere to these or other requirements.</span></span> <span data-ttu-id="35124-116">Необходимо определить, если он необходим позволяет отключить TLS 1.0 и 1.1 в вашей среде.</span><span class="sxs-lookup"><span data-stu-id="35124-116">You must determine if it is required for you to disable TLS 1.0 and/or 1.1 in your environments.</span></span>

<span data-ttu-id="35124-117">Майкрософт разработала Технический документ на TLS доступные [здесь](https://cloudblogs.microsoft.com/microsoftsecure/2017/06/20/tls-1-2-support-at-microsoft/), поэтому рекомендуется также фоновом режиме чтения недоступны в этом [блоге Exchange](https://blogs.technet.microsoft.com/exchange/2018/01/26/exchange-server-tls-guidance-part-1-getting-ready-for-tls-1-2/).</span><span class="sxs-lookup"><span data-stu-id="35124-117">Microsoft has produced a white paper on TLS available [here](https://cloudblogs.microsoft.com/microsoftsecure/2017/06/20/tls-1-2-support-at-microsoft/), and we also recommend the background reading available in this [Exchange blog](https://blogs.technet.microsoft.com/exchange/2018/01/26/exchange-server-tls-guidance-part-1-getting-ready-for-tls-1-2/).</span></span>

## <a name="supportability-scope"></a><span data-ttu-id="35124-118">Область технической поддержке</span><span class="sxs-lookup"><span data-stu-id="35124-118">Supportability Scope</span></span>

<span data-ttu-id="35124-119">*Область* относится к границам технической поддержке.</span><span class="sxs-lookup"><span data-stu-id="35124-119">*Scope* refers to supportability boundaries.</span></span> <span data-ttu-id="35124-120">Для Скайп для Business Server локальной *в области действия* означает, что мы полностью поддерживает и проверены отключение TLS 1.0 и 1.1 для версии перечисленных продуктов.</span><span class="sxs-lookup"><span data-stu-id="35124-120">For Skype for Business Server On-Premises, *in scope* means we fully support and have tested disabling of TLS 1.0 and 1.1 for the listed product versions.</span></span> <span data-ttu-id="35124-121">*В настоящее время изучению* означает, что только что; активно ведется расследование, внедрение этих продуктов в область действия для отключения поддержки TLS.</span><span class="sxs-lookup"><span data-stu-id="35124-121">*Currently being investigated* means just that; we are actively investigating bringing these products into scope for TLS disable support.</span></span> <span data-ttu-id="35124-122">*Из области действия* означает, что эти версии продукта не поддерживают отключение TLS 1.0 или 1.1 и не будут работать, за исключением указанных.</span><span class="sxs-lookup"><span data-stu-id="35124-122">*Out of scope* means these product versions do not support disabling TLS 1.0 or 1.1 and will not work, with noted exceptions.</span></span>

### <a name="fully-tested-and-supported-servers"></a><span data-ttu-id="35124-123">Полностью протестированы и поддерживаемые серверы</span><span class="sxs-lookup"><span data-stu-id="35124-123">Fully tested and supported servers</span></span>

- <span data-ttu-id="35124-124">Skype для бизнеса Server 2019</span><span class="sxs-lookup"><span data-stu-id="35124-124">Skype for Business Server 2019</span></span>
- <span data-ttu-id="35124-125">Скайп для Business Server 2015 CU6 HF2 6.0.9319.516 ([Обновить 2018 марта](https://support.microsoft.com/en-us/help/4086059/march-2018-cumulative-update-6-0-9319-516-for-skype-for-business)) и выше на:</span><span class="sxs-lookup"><span data-stu-id="35124-125">Skype for Business Server 2015 CU6 HF2 6.0.9319.516 ([March 2018 update](https://support.microsoft.com/en-us/help/4086059/march-2018-cumulative-update-6-0-9319-516-for-skype-for-business)) and higher on:</span></span> 
    - <span data-ttu-id="35124-126">Windows Server 2012 (с 3140245 КБ или заменяющего обновления), 2012 R2 или 2016</span><span class="sxs-lookup"><span data-stu-id="35124-126">Windows Server 2012 (with KB 3140245 or superseding update), 2012 R2 or 2016</span></span>
- <span data-ttu-id="35124-127">Скайп обновления на месте для 2015 Business Server, с CU6 HF2 и более высоких прав для</span><span class="sxs-lookup"><span data-stu-id="35124-127">In-place Upgraded Skype for Business Server 2015, with CU6 HF2 and higher on</span></span> 
    - <span data-ttu-id="35124-128">Windows Server 2008 R2, 2012 г. (с статья БАЗЫ знаний [3140245](https://support.microsoft.com/en-us/help/3140245/update-to-enable-tls-1-1-and-tls-1-2-as-a-default-secure-protocols-in) или заменяющее обновление) или 2012 R2</span><span class="sxs-lookup"><span data-stu-id="35124-128">Windows Server 2008 R2, 2012 (with KB [3140245](https://support.microsoft.com/en-us/help/3140245/update-to-enable-tls-1-1-and-tls-1-2-as-a-default-secure-protocols-in) or superseding update), or 2012 R2</span></span>
- <span data-ttu-id="35124-129">Подключение к Exchange и Outlook Web App с Exchange Server 2010 с пакетом обновления 3 RU19 или более поздней версии, руководство [здесь](https://blogs.technet.microsoft.com/exchange/2018/01/26/exchange-server-tls-guidance-part-1-getting-ready-for-tls-1-2/)</span><span class="sxs-lookup"><span data-stu-id="35124-129">Exchange Connectivity and Outlook Web App with Exchange Server 2010 SP3 RU19 or higher, guidance [here](https://blogs.technet.microsoft.com/exchange/2018/01/26/exchange-server-tls-guidance-part-1-getting-ready-for-tls-1-2/)</span></span>
- <span data-ttu-id="35124-130">Устройство для обеспечения связи в филиалах (SBA) с Скайп для Business Server 2015 CU6 HF2 или более поздней версии (проверьте с поставщиком, что они упакованных обновлений appropiate и доступному для устройства)</span><span class="sxs-lookup"><span data-stu-id="35124-130">Survivable Branch Appliance (SBA) with Skype for Business Server 2015 CU6 HF2 or higher (confirm with your vendor that they packaged the appropiate updates and have been made available for your appliance)</span></span>
- <span data-ttu-id="35124-131">Сервер для обеспечения связи в филиалах (SBS) с Скайп для Business Server 2015 CU6 HF2 или более поздней версии</span><span class="sxs-lookup"><span data-stu-id="35124-131">Survivable Branch Server (SBS) with Skype for Business Server 2015 CU6 HF2 or higher</span></span>
- <span data-ttu-id="35124-132">Lync Server 2013 **Только роли пограничного сервера**, это, поскольку роль пограничного отсутствуют зависимости на Windows Fabric 1.0.</span><span class="sxs-lookup"><span data-stu-id="35124-132">Lync Server 2013 **Edge Role Only**, this is because Edge role does not have a dependency on Windows Fabric 1.0.</span></span>


### <a name="fully-tested-and-supported-clients"></a><span data-ttu-id="35124-133">Полностью протестированы и поддерживаемые клиенты</span><span class="sxs-lookup"><span data-stu-id="35124-133">Fully tested and supported clients</span></span>

- <span data-ttu-id="35124-134">Настольный клиент Lync 2013 (Скайп для бизнеса), MSI и C2R, включая Basic [15.0.5023.1000 и последующие версии](https://support.microsoft.com/en-us/help/4018334/april-3-2018-update-for-skype-for-business-2015-lync-2013-kb4018334)</span><span class="sxs-lookup"><span data-stu-id="35124-134">Lync 2013 (Skype for Business) Desktop Client, MSI and C2R, including Basic [15.0.5023.1000 and higher](https://support.microsoft.com/en-us/help/4018334/april-3-2018-update-for-skype-for-business-2015-lync-2013-kb4018334)</span></span>
- <span data-ttu-id="35124-135">Скайп для бизнеса 2016 настольный клиент, MSI [16.0.4678.1000 и последующие версии](https://support.microsoft.com/en-us/help/4018323/april-3-2018-update-for-skype-for-business-2016-kb4018323), включая Basic</span><span class="sxs-lookup"><span data-stu-id="35124-135">Skype for Business 2016 Desktop Client, MSI [16.0.4678.1000 and higher](https://support.microsoft.com/en-us/help/4018323/april-3-2018-update-for-skype-for-business-2016-kb4018323), including Basic</span></span>
- <span data-ttu-id="35124-136">Скайп для бизнеса, 2016 нажмите кнопку Запуск, требуют обновления [2018 апреля](https://docs.microsoft.com/officeupdates/release-notes-office365-proplus) :</span><span class="sxs-lookup"><span data-stu-id="35124-136">Skype for Business 2016 Click to Run Require the [April 2018](https://docs.microsoft.com/officeupdates/release-notes-office365-proplus) Updates:</span></span> 
    - <span data-ttu-id="35124-137">Ежемесячно и точками годовая нацелено 16\.0\.9126\.2152 и выше</span><span class="sxs-lookup"><span data-stu-id="35124-137">Monthly and Semi-Annual Targeted, 16\.0\.9126\.2152 and higher</span></span>
    - <span data-ttu-id="35124-138">Годовая точками и отложенный канала, 16\.0\.8431\.2242 и выше</span><span class="sxs-lookup"><span data-stu-id="35124-138">Semi-Annual and Deferred Channel, 16\.0\.8431\.2242 and higher</span></span>
- <span data-ttu-id="35124-139">Скайп для бизнеса на Mac 16.15 и более поздней версии</span><span class="sxs-lookup"><span data-stu-id="35124-139">Skype for Business on Mac 16.15 and higher</span></span>
- <span data-ttu-id="35124-140">Скайп для деловых операций ввода-вывода и Android 6.19 и выше</span><span class="sxs-lookup"><span data-stu-id="35124-140">Skype for Business for iOS and Android 6.19 and higher</span></span>
- <span data-ttu-id="35124-141">Скайп Web App 2015 CU6 HF2 и выше (поставляется с сервера)</span><span class="sxs-lookup"><span data-stu-id="35124-141">Skype Web App 2015 CU6 HF2 and higher (ships with Server)</span></span>

### <a name="currently-being-investigated"></a><span data-ttu-id="35124-142">В настоящее время изучению</span><span class="sxs-lookup"><span data-stu-id="35124-142">Currently being investigated</span></span>

#### <a name="devices"></a><span data-ttu-id="35124-143">Устройства</span><span class="sxs-lookup"><span data-stu-id="35124-143">Devices</span></span>

- <span data-ttu-id="35124-144">Система комнаты Lync (известной как</span><span class="sxs-lookup"><span data-stu-id="35124-144">Lync Room System (a.k.a.</span></span> <span data-ttu-id="35124-145">SRSv1)</span><span class="sxs-lookup"><span data-stu-id="35124-145">SRSv1)</span></span>
- <span data-ttu-id="35124-146">Комнат группами Майкрософт</span><span class="sxs-lookup"><span data-stu-id="35124-146">Microsoft Teams Rooms</span></span>
- <span data-ttu-id="35124-147">Контактной сервера-концентратора</span><span class="sxs-lookup"><span data-stu-id="35124-147">Surface Hub</span></span>
- <span data-ttu-id="35124-148">на основе 2015, устройство для обеспечения связи в филиалах (SBA) или сервера обеспечения связи в филиалах (SBS)</span><span class="sxs-lookup"><span data-stu-id="35124-148">2015 based Survivable Branch Appliance (SBA) or Survivable Branch Server (SBS)</span></span>

#### <a name="other"></a><span data-ttu-id="35124-149">Другое</span><span class="sxs-lookup"><span data-stu-id="35124-149">Other</span></span>

- <span data-ttu-id="35124-150">Вызов мониторинга качества (были отключены с новой установки после TLS 1.0, 1.1, см) \*</span><span class="sxs-lookup"><span data-stu-id="35124-150">Call Quality Dashboard (new install after TLS 1.0, 1.1 have been disabled, see below)\*</span></span>
 
### <a name="out-of-scope"></a><span data-ttu-id="35124-151">Из области действия</span><span class="sxs-lookup"><span data-stu-id="35124-151">Out of scope</span></span>

<span data-ttu-id="35124-152">Если не указано иное следующих продуктов не входящих в область для TLS 1.0/1.1 отключить поддержку и не будет работать в среде, где были отключены TLS 1.0 и 1.1.</span><span class="sxs-lookup"><span data-stu-id="35124-152">Except where noted, the following products are not in scope for TLS 1.0/1.1 disable support and will not function in an environment where TLS 1.0 and 1.1 have been disabled.</span></span>  <span data-ttu-id="35124-153">Это означает: Если вы по-прежнему использовать вне области серверы или клиенты, необходимо обновить или удалить эти поля, если требуется отключить протокол TLS 1.0/1.1 в любом месте вашего Скайп for Business Server локальное развертывание.</span><span class="sxs-lookup"><span data-stu-id="35124-153">What this means: if you still utilize out-of-scope servers or clients, you must update or remove these if you need to disable TLS 1.0/1.1 anywhere in your Skype for Business Server on-premises deployment.</span></span>

- <span data-ttu-id="35124-154">Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="35124-154">Lync Server 2013</span></span>
- <span data-ttu-id="35124-155">Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="35124-155">Lync Server 2010</span></span>
- <span data-ttu-id="35124-156">Windows Server 2008 и нижний край</span><span class="sxs-lookup"><span data-stu-id="35124-156">Windows Server 2008 and lower</span></span>
- <span data-ttu-id="35124-157">Lync для Mac 2011</span><span class="sxs-lookup"><span data-stu-id="35124-157">Lync for Mac 2011</span></span>
- <span data-ttu-id="35124-158">Lync 2013 для мобильных устройств - операций ввода-вывода, iPad, Android или Windows Phone</span><span class="sxs-lookup"><span data-stu-id="35124-158">Lync 2013 for Mobile - iOS, iPad, Android or Windows Phone</span></span>
- <span data-ttu-id="35124-159">Клиент Lync «MX» для магазина Windows</span><span class="sxs-lookup"><span data-stu-id="35124-159">Lync "MX" Windows Store client</span></span>
- <span data-ttu-id="35124-160">Все клиенты Lync 2010</span><span class="sxs-lookup"><span data-stu-id="35124-160">All Lync 2010 clients</span></span>
- <span data-ttu-id="35124-161">Lync Phone Edition - обновлено руководство [здесь](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Certified-Skype-for-Business-Online-Phones-and-what-this-means/ba-p/120035).</span><span class="sxs-lookup"><span data-stu-id="35124-161">Lync Phone Edition - updated guidance [here](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Certified-Skype-for-Business-Online-Phones-and-what-this-means/ba-p/120035).</span></span>
- <span data-ttu-id="35124-162">2013 на основе устройство для обеспечения связи в филиалах (SBA) или сервера обеспечения связи в филиалах (SBS)</span><span class="sxs-lookup"><span data-stu-id="35124-162">2013 based Survivable Branch Appliance (SBA) or Survivable Branch Server (SBS)</span></span>
- <span data-ttu-id="35124-163">Облако соединителя Edition (системы CCE)</span><span class="sxs-lookup"><span data-stu-id="35124-163">Cloud Connector Edition (CCE)</span></span>
- <span data-ttu-id="35124-164">Skype для бизнеса для Windows Phone</span><span class="sxs-lookup"><span data-stu-id="35124-164">Skype for Business for Windows Phone</span></span>

### <a name="exceptions"></a><span data-ttu-id="35124-165">Исключения</span><span class="sxs-lookup"><span data-stu-id="35124-165">Exceptions</span></span>

#### <a name="lync-server-2013"></a><span data-ttu-id="35124-166">Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="35124-166">Lync Server 2013</span></span>

<span data-ttu-id="35124-167">Lync Server 2013 зависит Windows Fabric версии 1.0.</span><span class="sxs-lookup"><span data-stu-id="35124-167">Lync Server 2013 takes a dependency on Windows Fabric version 1.0.</span></span>  <span data-ttu-id="35124-168">На этапе разработки для Lync Server 2013 Windows Fabric 1.0 был выбран для привлекательные и новые распределенной архитектуры для обеспечения репликации, высокая доступность и устойчивость к сбоям.</span><span class="sxs-lookup"><span data-stu-id="35124-168">In the design phase for Lync Server 2013, Windows Fabric 1.0 was chosen for its compelling and new distributed architecture to provide replication, high availability, and fault tolerance.</span></span>  <span data-ttu-id="35124-169">Со временем обоих Скайп Business Server и Windows Fabric значительно повысили Эта архитектура совместного с значительные повторно проектирование в последующих версиях.</span><span class="sxs-lookup"><span data-stu-id="35124-169">Over time, both Skype for Business Server and Windows Fabric have greatly improved this joint architecture with significant re-design in subsequent versions.</span></span>  <span data-ttu-id="35124-170">Текущий Скайп для Business 2015 Server использует Windows Fabric 3.0, например.</span><span class="sxs-lookup"><span data-stu-id="35124-170">Current Skype for Business 2015 Server uses Windows Fabric 3.0, for example.</span></span>

<span data-ttu-id="35124-171">К сожалению Windows Fabric 1.0 **не поддерживает TLS 1.2.  Тем не менее, мы будет обновляться Lync Server 2013 для работы с тактовой частотой 1,2 TLS**.</span><span class="sxs-lookup"><span data-stu-id="35124-171">Unfortunately, Windows Fabric 1.0 **does not support TLS 1.2.  However, we will be updating Lync Server 2013 to work with TLS 1.2**.</span></span> <span data-ttu-id="35124-172">Это должен быть выпущен в далее накопительные пакеты обновления для Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="35124-172">This will be coming in the next Cumulative Update for Lync Server 2013.</span></span>  <span data-ttu-id="35124-173">Мы предлагаем поддержки TLS 1.2 для включения совместная работа, переноса, федерации и гибридных сценариев.</span><span class="sxs-lookup"><span data-stu-id="35124-173">We're providing TLS 1.2 support to enable co-existence, migration, federation, and hybrid scenarios.</span></span>

<span data-ttu-id="35124-174">Если вы уже используете Lync Server 2013 вашей организации требуется отключить протокол TLS 1.0 и 1.1, рекомендуется начать в процессе планирования, существует возможность в некоторых случаях требуется обновление на месте или рядом друг с другом перенос (новые пулы, перемещение пользователей) в Скайп для Business Server 2015 или более поздней версии.</span><span class="sxs-lookup"><span data-stu-id="35124-174">If your organization is required to disable TLS 1.0 and 1.1, and you currently use Lync Server 2013, we recommend you begin your planning process, with the possibility you may have to In-place upgrade or Side-by-Side migrate (new pools, move users) to Skype for Business Server 2015 or higher.</span></span>  <span data-ttu-id="35124-175">Или воспользуйтесь для ускорения миграции для Скайп для бизнеса в Интернет.</span><span class="sxs-lookup"><span data-stu-id="35124-175">Or you may want to accelerate migration to Skype for Business Online.</span></span>

#### <a name="call-quality-dashboard"></a><span data-ttu-id="35124-176">Панель мониторинга качества вызовов</span><span class="sxs-lookup"><span data-stu-id="35124-176">Call Quality Dashboard</span></span>

<span data-ttu-id="35124-177">Панель мониторинга качества звонков в локальной в настоящее время имеет зависимости от TLS 1.0 во время новой установки (установка в вашей локальной среды первый раз).</span><span class="sxs-lookup"><span data-stu-id="35124-177">On-Premises Call Quality Dashboard currently has a dependency on TLS 1.0 during new install (first time installing into your On-Premises environments).</span></span>  <span data-ttu-id="35124-178">Мы в настоящее время ведется расследование этой проблемы и планирование для освобождения исправление в ближайшем будущем.</span><span class="sxs-lookup"><span data-stu-id="35124-178">We are currently investigating this issue and plan to release a fix in the near future.</span></span>  <span data-ttu-id="35124-179">При планировании установки CQD и также отключить TLS 1.0 рекомендуется сначала завершить установку CQD и нажмите Продолжить отключение TLS 1.0.</span><span class="sxs-lookup"><span data-stu-id="35124-179">If you are planning to install CQD and also disable TLS 1.0, we recommend that you complete CQD installation first, and then proceed with TLS 1.0 disabling.</span></span>

#### <a name="third-party-devices"></a><span data-ttu-id="35124-180">Устройствами сторонних производителей</span><span class="sxs-lookup"><span data-stu-id="35124-180">Third-party devices</span></span>

<span data-ttu-id="35124-181">На устройствах сторонних производителей, таких как телефоны 3PIP видео-конференций, обратных прокси-серверов и подсистем балансировки нагрузки, не забудьте проверить технической поддержке TLS 1.2, тщательно проверьте и обратитесь к поставщику и при необходимости.</span><span class="sxs-lookup"><span data-stu-id="35124-181">On third-party devices such as 3PIP phones, Video conferencing, Reverse Proxies and Load Balancers, be sure to validate TLS 1.2 supportability, test carefully, and contact the vendor if needed.</span></span>

### <a name="federation-considerations-when-disabling-tls-1011-on-edge-servers"></a><span data-ttu-id="35124-182">Сведения о выполнении федерации при отключении TLS 1.0/1.1 на пограничных серверах</span><span class="sxs-lookup"><span data-stu-id="35124-182">Federation considerations when disabling TLS 1.0/1.1 on Edge servers</span></span>

<span data-ttu-id="35124-183">Необходимо тщательно спланировать и рассмотрите влияние отключения TLS 1.0/1.1 на пограничных серверах.</span><span class="sxs-lookup"><span data-stu-id="35124-183">You must carefully plan for and consider the impact of disabling TLS 1.0/1.1 on your Edge servers.</span></span>  <span data-ttu-id="35124-184">После TLS 1.0 и 1.1 отключены, может оказаться, что других организаций больше не смогут в федерацию с вашей организации.</span><span class="sxs-lookup"><span data-stu-id="35124-184">Once TLS 1.0 and 1.1 are disabled, you may find that other organizations are no longer be able to federate with your organization.</span></span>

<span data-ttu-id="35124-185">Может выбрать для хранения TLS 1.0/1.1 включен на пограничных серверах для обеспечения обратной совместимости с не исправленный (SfB 2015, Lync 2013) или более старые внешними системами (2010).</span><span class="sxs-lookup"><span data-stu-id="35124-185">You may opt to keep TLS 1.0/1.1 enabled on your Edge servers to maintain backward compatibility with non-patched (SfB 2015, Lync 2013) or older (2010) external systems.</span></span>

<span data-ttu-id="35124-186">Корпорация Майкрософт не предоставляет советы и рекомендации на ли вашей пограничной сети (или любую сеть) попадает в разделе PCI standard; который необходимо определить в отдельных компании.</span><span class="sxs-lookup"><span data-stu-id="35124-186">Microsoft cannot provide advice or recommendations on whether or not your Edge network (or any network) falls under PCI standard; that must be determined by the individual company.</span></span>

<span data-ttu-id="35124-187">Скайп для бизнеса в Интернет способен TLS 1.2 в настоящее время, без воздействия на гибридные/федерацию с Online не ожидается.</span><span class="sxs-lookup"><span data-stu-id="35124-187">Skype for Business Online is capable of TLS 1.2 today, so no impact to Hybrid/Federation with Online is expected.</span></span>

<span data-ttu-id="35124-188">PIC (общедоступной службы обмена Мгновенными сообщениями) к службе Скайп потребителей: не ожидается, что отключение TLS 1.0/1.1 влияние [Подключения к Скайп](../../deploy/deploy-skype-connectivity.md); Шлюзы PIC Microsoft уже может 1.2 TLS.</span><span class="sxs-lookup"><span data-stu-id="35124-188">PIC (Public IM Connectivity) to Skype Consumer service: We do not expect disabling TLS 1.0/1.1 to impact [Skype Connectivity](../../deploy/deploy-skype-connectivity.md); Microsoft PIC Gateways are already TLS 1.2 capable.</span></span>

## <a name="prerequisites-and-process"></a><span data-ttu-id="35124-189">Необходимые условия и процесс</span><span class="sxs-lookup"><span data-stu-id="35124-189">Prerequisites and process</span></span>

<span data-ttu-id="35124-190">Если не указано иное, после TLS 1.0 и 1.1 отключенных вне области серверов, клиентов и устройств будет работать неправильно или вообще, за исключением.</span><span class="sxs-lookup"><span data-stu-id="35124-190">Except where noted above, once TLS 1.0 and 1.1 are disabled out-of-scope servers, clients and devices will longer function properly, or at all.</span></span> <span data-ttu-id="35124-191">Это означает, что необходимо приостановить и дождитесь обновлено руководство корпорации Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="35124-191">This may mean you need to pause and wait for updated guidance from Microsoft.</span></span> <span data-ttu-id="35124-192">Как только вы удовлетворены соответствовать всем требованиям и составить план адрес перерывов в работе, продолжить работу.</span><span class="sxs-lookup"><span data-stu-id="35124-192">Once you are satisfied that you meet all requirements and have a plan to address gaps, proceed.</span></span>

<span data-ttu-id="35124-193">На высоком уровне во время Скайп для Business Server 2019 готова к процедуре во время установки Скайп для Business Server 2015 требуется установить HF2 CU6, необходимые предварительные обновление .NET и SQL, развертывание необходимого реестра и наконец отдельных обновляет Round конфигурации операционной системы (то есть отключение TLS 1.0 и 1.1 с помощью импорта файла реестра).</span><span class="sxs-lookup"><span data-stu-id="35124-193">At a high level, while Skype for Business Server 2019 is ready for procedure at install, Skype for Business Server 2015 will require that you install CU6 HF2, applying pre-requisite updates to .NET and SQL, deploying prerequisite registry keys, and finally a separate round of OS configuration updates (i.e. disabling TLS 1.0 and 1.1 via registry file import).</span></span> <span data-ttu-id="35124-194">Очень важно выполнить установку необходимых, включая Скайп для Business Server 2015 CU6 HF2, перед отключение TLS 1.0 и 1.1 на любом сервере в вашей среде.</span><span class="sxs-lookup"><span data-stu-id="35124-194">It is critically important that you complete installation of all prerequisites, including Skype for Business Server 2015 CU6 HF2, prior to disabling TLS 1.0 and 1.1 on any server in your environment.</span></span> <span data-ttu-id="35124-195">Каждый Скайп для Business server, включая роли пограничного сервера и серверных системах SQL требует обновления.</span><span class="sxs-lookup"><span data-stu-id="35124-195">Every Skype for Business server, including Edge role and SQL Backends, requires the updates.</span></span> <span data-ttu-id="35124-196">Кроме того, убедитесь, что минимальные требуемые версии были обновлены все поддерживаемые клиенты (в области).</span><span class="sxs-lookup"><span data-stu-id="35124-196">Also ensure that all supported (in-scope) clients have been updated to the required minimum versions.</span></span> <span data-ttu-id="35124-197">Не забудьте обновить также рабочие станции управления.</span><span class="sxs-lookup"><span data-stu-id="35124-197">Don’t forget to update management workstations as well.</span></span>

<span data-ttu-id="35124-198">Мы хотим следуйте обычным порядке операций «внутри выход» для обновления Скайп для серверов организаций.</span><span class="sxs-lookup"><span data-stu-id="35124-198">We want to follow the usual order of operations of "inside out" for upgrading Skype for Business servers.</span></span> <span data-ttu-id="35124-199">Рассматривать пулов, сохраняемого чата и сопоставленных пулов директоров в точно так же, как обычно.</span><span class="sxs-lookup"><span data-stu-id="35124-199">Treat Director pools, Persistent chat, and Paired Pools in the same manner you normally would.</span></span> <span data-ttu-id="35124-200">Порядок и методов обновления рассматривается [здесь](topology.md) и [здесь](https://support.microsoft.com/en-us/help/3061064/updates-for-skype-for-business-server-2015).</span><span class="sxs-lookup"><span data-stu-id="35124-200">Order and methods for upgrade are covered [here](topology.md) and [here](https://support.microsoft.com/en-us/help/3061064/updates-for-skype-for-business-server-2015).</span></span>

### <a name="high-level-process"></a><span data-ttu-id="35124-201">Высокоуровневый процесс</span><span class="sxs-lookup"><span data-stu-id="35124-201">High-level process</span></span>

1. <span data-ttu-id="35124-202">Проверьте все действия, описанные в лабораторной среде перед настройкой рабочих серверах.</span><span class="sxs-lookup"><span data-stu-id="35124-202">Test all steps in your lab prior to configuring production servers.</span></span>
2. <span data-ttu-id="35124-203">Резервное копирование и сохранения копии экспортированного реестра на всех отдельного сервера, который требуется обновить.</span><span class="sxs-lookup"><span data-stu-id="35124-203">Back up and preserve a copy of exported registry on each and every individual server to be updated.</span></span> <span data-ttu-id="35124-204">Не могут совместно использовать значений между серверами; они содержат уникальные ключи компьютера.</span><span class="sxs-lookup"><span data-stu-id="35124-204">You cannot share registries between servers; they contain unique machine-based keys.</span></span>
3. <span data-ttu-id="35124-205">Обновление всех Скайп для серверов Business 2015 CU6 HF2 или выше.</span><span class="sxs-lookup"><span data-stu-id="35124-205">Upgrade all Skype for Business 2015 servers to CU6 HF2 or higher.</span></span> <span data-ttu-id="35124-206">(Для Скайп для Business Server 2019 необходима не накопительный пакет обновления)</span><span class="sxs-lookup"><span data-stu-id="35124-206">(For Skype for Business Server 2019, no CU is needed)</span></span>
4. <span data-ttu-id="35124-207">Установите все необходимые компоненты на все серверы.</span><span class="sxs-lookup"><span data-stu-id="35124-207">Install all prerequisites to all servers.</span></span>
5. <span data-ttu-id="35124-208">Разверните разделы реестра, необходимых компонентов.</span><span class="sxs-lookup"><span data-stu-id="35124-208">Deploy prerequisite registry keys.</span></span>
6. <span data-ttu-id="35124-209">Убедитесь, что все клиенты в области обновляются.</span><span class="sxs-lookup"><span data-stu-id="35124-209">Ensure that all in-scope clients are updated.</span></span>
7. <span data-ttu-id="35124-210">Отключите протокол TLS 1.0 и 1.1 с помощью реестра импорта.</span><span class="sxs-lookup"><span data-stu-id="35124-210">Disable TLS 1.0 and 1.1 via registry import.</span></span>
8. <span data-ttu-id="35124-211">Убедитесь, что рабочие нагрузки работают должным образом.</span><span class="sxs-lookup"><span data-stu-id="35124-211">Validate that workloads are functioning as expected.</span></span>
    - <span data-ttu-id="35124-212">Если возникли проблемы, устранение неполадок и устранить, или</span><span class="sxs-lookup"><span data-stu-id="35124-212">If problems are encountered, troubleshoot and resolve, or</span></span>
    - <span data-ttu-id="35124-213">Восстановление реестра в шаге 2, чтобы повторно включить TLS 1.0 и 1.1</span><span class="sxs-lookup"><span data-stu-id="35124-213">Restore registry from step 2 to re-enable TLS 1.0 and 1.1</span></span>
9. <span data-ttu-id="35124-214">Убедитесь, что используется только протокол TLS 1.2.</span><span class="sxs-lookup"><span data-stu-id="35124-214">Validate that only TLS 1.2 is being used.</span></span>

### <a name="install-prerequisites-to-all-servers"></a><span data-ttu-id="35124-215">Установка необходимых компонентов на всех серверах</span><span class="sxs-lookup"><span data-stu-id="35124-215">Install prerequisites to all servers</span></span>

<span data-ttu-id="35124-216">Широкое зависимостей обновление не требуется, перед началом работы для отключения TLS 1.0 и 1.1 на уровне операционной системы в вашей Скайп для развертываний Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="35124-216">Extensive dependency updating is required before you begin to disable TLS 1.0 and 1.1 at the operating system level in your Skype for Business Server 2015 deployments.</span></span> <span data-ttu-id="35124-217">Ниже приведены минимальные версий, помогающие обеспечить TLS 1.2.</span><span class="sxs-lookup"><span data-stu-id="35124-217">The following are the minimum versions that can support TLS 1.2.</span></span> <span data-ttu-id="35124-218">Разверните все необходимые обновления на каждый Скайп для Business server в среде, прежде чем начать, отключение TLS 1.0 и 1.1.</span><span class="sxs-lookup"><span data-stu-id="35124-218">Deploy all prerequisite updates across every Skype for Business server in your environment before you begin disabling TLS 1.0 and 1.1.</span></span>

- <span data-ttu-id="35124-219">Скайп для Business Server 2015 CU6 HF2 6.0.9319.516 ([Обновить 2018 марта](https://support.microsoft.com/en-us/help/4086059/march-2018-cumulative-update-6-0-9319-516-for-skype-for-business)) или более поздней версии</span><span class="sxs-lookup"><span data-stu-id="35124-219">Skype for Business Server 2015 CU6 HF2 6.0.9319.516 ([March 2018 update](https://support.microsoft.com/en-us/help/4086059/march-2018-cumulative-update-6-0-9319-516-for-skype-for-business)) or higher</span></span>
- <span data-ttu-id="35124-220">[.NET framework 4.7](https://www.microsoft.com/en-us/download/details.aspx?id=55167) или выше с SchUseStrongCrypto, включенных в реестр (представлены ниже)</span><span class="sxs-lookup"><span data-stu-id="35124-220">[.NET Framework 4.7](https://www.microsoft.com/en-us/download/details.aspx?id=55167) or higher with SchUseStrongCrypto enabled in the registry (provided below)</span></span>
- <span data-ttu-id="35124-221">Необходимо обновить SQL на всех Скайп для бизнеса 2015 серверов и серверных системах.</span><span class="sxs-lookup"><span data-stu-id="35124-221">SQL must be updated on all Skype for Business 2015 servers and backends.</span></span> <span data-ttu-id="35124-222">Обновление серверных системах SQL Enterprise Edition пула во-первых, затем их соответствующих FEs.</span><span class="sxs-lookup"><span data-stu-id="35124-222">Update Enterprise Edition Pool SQL Backends first, then their respective FEs.</span></span> 
    - <span data-ttu-id="35124-223">SQL Server 2014 с пакетом обновления 1 + накопительным пакетом обновления 5 ([ссылки](https://support.microsoft.com/help/3130926)) или выше / CU16 + SQL Server 2012 с пакетом обновления 2 или выше / SQL Server 2014 RTM + CU12 ([ссылки](https://support.microsoft.com/en-us/help/3130923/cumulative-update-12-for-sql-server-2014)) или более поздней версии / с пакетом обновления 2 для SQL Server 2014 г.</span><span class="sxs-lookup"><span data-stu-id="35124-223">SQL Server 2014 SP1 + CU5 ([link](https://support.microsoft.com/help/3130926)), or higher / SQL Server 2012 SP2 + CU16 or higher/ SQL Server 2014 RTM + CU12 ([link](https://support.microsoft.com/en-us/help/3130923/cumulative-update-12-for-sql-server-2014)) or higher / SQL Server 2014 SP2</span></span>
    - <span data-ttu-id="35124-224">Собственный клиент SQL Server для SQL Server 2012 ([ссылки](https://www.microsoft.com/en-us/download/details.aspx?id=50402))</span><span class="sxs-lookup"><span data-stu-id="35124-224">SQL Server Native Client for SQL Server 2012 ([link](https://www.microsoft.com/en-us/download/details.aspx?id=50402))</span></span>
    - <span data-ttu-id="35124-225">Драйвер ODBC Microsoft 11 для SQL Server ([ссылки](https://www.microsoft.com/en-us/download/details.aspx?id=36434)) или более поздней версии</span><span class="sxs-lookup"><span data-stu-id="35124-225">Microsoft ODBC Driver 11 for SQL Server ([link](https://www.microsoft.com/en-us/download/details.aspx?id=36434)), or higher</span></span>
    - <span data-ttu-id="35124-226">Общие объекты управления для SQL Server 2014 г., с пакетом обновления 2 ([ссылки](https://www.microsoft.com/en-in/download/details.aspx?id=42295))</span><span class="sxs-lookup"><span data-stu-id="35124-226">Shared Management Objects for SQL Server 2014 SP2 ([link](https://www.microsoft.com/en-in/download/details.aspx?id=42295))</span></span>
    - <span data-ttu-id="35124-227">SQLSysClrTypes для SQL server 2014 с пакетом обновления 2 ([ссылки](https://www.microsoft.com/en-in/download/details.aspx?id=42295))</span><span class="sxs-lookup"><span data-stu-id="35124-227">SQLSysClrTypes for SQL server 2014 SP2 ([link](https://www.microsoft.com/en-in/download/details.aspx?id=42295))</span></span>

### <a name="basic-steps-to-install-pre-requisites-in-recommended-order-of-operations"></a><span data-ttu-id="35124-228">Основные действия для установки необходимых компонентов в Рекомендуемая последовательность операций</span><span class="sxs-lookup"><span data-stu-id="35124-228">Basic steps to install pre-requisites, in recommended order of operations</span></span>

1. <span data-ttu-id="35124-229">Установка Скайп для Business Server CU6HF2 (6.0.9319.516) обновление на все серверы.</span><span class="sxs-lookup"><span data-stu-id="35124-229">Install the Skype for Business Server CU6HF2 (6.0.9319.516) update to all servers.</span></span> 
    1. <span data-ttu-id="35124-230">Установите обновление для компонентов с помощью программы обновления.</span><span class="sxs-lookup"><span data-stu-id="35124-230">Install the update to components using the updater.</span></span>
    2. <span data-ttu-id="35124-231">Обновление баз данных в соответствии с документированным процедур.</span><span class="sxs-lookup"><span data-stu-id="35124-231">Update databases according to documented procedures.</span></span> <span data-ttu-id="35124-232">Инструкции по описаны на [https://support.microsoft.com/en-us/help/3061064/updates-for-skype-for-business-server-2015](https://support.microsoft.com/en-us/help/3061064/updates-for-skype-for-business-server-2015).</span><span class="sxs-lookup"><span data-stu-id="35124-232">Instructions are documented at [https://support.microsoft.com/en-us/help/3061064/updates-for-skype-for-business-server-2015](https://support.microsoft.com/en-us/help/3061064/updates-for-skype-for-business-server-2015).</span></span>
    3. <span data-ttu-id="35124-233">Проверьте функциональные возможности продуктов в развертывании, прежде чем продолжать другие изменения.</span><span class="sxs-lookup"><span data-stu-id="35124-233">Validate product functionality in the deployment prior to moving forward with any other changes.</span></span>
2. <span data-ttu-id="35124-234">Загрузить .NET 4.7 автономного установщика.</span><span class="sxs-lookup"><span data-stu-id="35124-234">Download .NET 4.7 Offline Installer.</span></span> 
    1. <span data-ttu-id="35124-235">Ссылка:[https://www.microsoft.com/en-us/download/details.aspx?id=55167](https://www.microsoft.com/en-us/download/details.aspx?id=55167)</span><span class="sxs-lookup"><span data-stu-id="35124-235">Reference: [https://www.microsoft.com/en-us/download/details.aspx?id=55167](https://www.microsoft.com/en-us/download/details.aspx?id=55167)</span></span>
    2. <span data-ttu-id="35124-236">Убедитесь, что Скайп для служб Business Server 2015 останавливаются на сервере переднего плана.</span><span class="sxs-lookup"><span data-stu-id="35124-236">Ensure that Skype for Business Server 2015 services are stopped on the Front End server.</span></span>
    3. <span data-ttu-id="35124-237">Ссылка:[https://support.microsoft.com/en-us/help/3061064/updates-for-skype-for-business-server-2015](https://support.microsoft.com/en-us/help/3061064/updates-for-skype-for-business-server-2015)</span><span class="sxs-lookup"><span data-stu-id="35124-237">Reference: [https://support.microsoft.com/en-us/help/3061064/updates-for-skype-for-business-server-2015](https://support.microsoft.com/en-us/help/3061064/updates-for-skype-for-business-server-2015)</span></span>
    4. <span data-ttu-id="35124-238">Ex (Standard Edition): Stop-CsWindowsServices</span><span class="sxs-lookup"><span data-stu-id="35124-238">Ex (Standard Edition): Stop-CsWindowsServices</span></span>
    5. <span data-ttu-id="35124-239">Ex (Enterprise Edition): Invoke-CsComputerFailover</span><span class="sxs-lookup"><span data-stu-id="35124-239">Ex (Enterprise Edition): Invoke-CsComputerFailover</span></span>
    6. <span data-ttu-id="35124-240">Запустите пакет установки.</span><span class="sxs-lookup"><span data-stu-id="35124-240">Run the installer package.</span></span>
    7. <span data-ttu-id="35124-241">Перезагрузите сервер.</span><span class="sxs-lookup"><span data-stu-id="35124-241">Reboot the server.</span></span>
3. <span data-ttu-id="35124-242">Обновление SQL Express 2014 г. на всех серверах.</span><span class="sxs-lookup"><span data-stu-id="35124-242">Update SQL Express 2014 on all servers.</span></span> 
    1. <span data-ttu-id="35124-243">Ссылка:[https://support.microsoft.com/en-us/help/3135244/tls-1-2-support-for-microsoft-sql-server](https://support.microsoft.com/en-us/help/3135244/tls-1-2-support-for-microsoft-sql-server)</span><span class="sxs-lookup"><span data-stu-id="35124-243">Reference: [https://support.microsoft.com/en-us/help/3135244/tls-1-2-support-for-microsoft-sql-server](https://support.microsoft.com/en-us/help/3135244/tls-1-2-support-for-microsoft-sql-server)</span></span>
    2. <span data-ttu-id="35124-244">Загрузить пакет обновления 2 для SQL 2014 г.</span><span class="sxs-lookup"><span data-stu-id="35124-244">Download SQL 2014 SP2</span></span> 
        - <span data-ttu-id="35124-245">Ссылка:[https://www.microsoft.com/en-us/download/details.aspx?id=53168](https://www.microsoft.com/en-us/download/details.aspx?id=53168)</span><span class="sxs-lookup"><span data-stu-id="35124-245">Reference: [https://www.microsoft.com/en-us/download/details.aspx?id=53168](https://www.microsoft.com/en-us/download/details.aspx?id=53168)</span></span>
    3. <span data-ttu-id="35124-246">Скопируйте установочного носителя в папку на сервере (например: C:\01_2014SqlSp2)</span><span class="sxs-lookup"><span data-stu-id="35124-246">Copy the installation media to a folder on the server (Ex: C:\01_2014SqlSp2)</span></span>
    4. <span data-ttu-id="35124-247">Обеспечить Скайп Business Server 2015 остановлен служб на сервере переднего плана</span><span class="sxs-lookup"><span data-stu-id="35124-247">Ensure Skype for Business Server 2015 services are stopped on the Front End server</span></span> 
        - <span data-ttu-id="35124-248">Ex (Standard Edition): Stop-CsWindowsService</span><span class="sxs-lookup"><span data-stu-id="35124-248">Ex (Standard Edition): Stop-CsWindowsService</span></span>
        - <span data-ttu-id="35124-249">Ex (Enterprise Edition): Invoke-CsComputerFailove</span><span class="sxs-lookup"><span data-stu-id="35124-249">Ex (Enterprise Edition): Invoke-CsComputerFailove</span></span>
    5. <span data-ttu-id="35124-250">Откройте командную строку администратора и обновление всех установленных компонентов и экземпляров</span><span class="sxs-lookup"><span data-stu-id="35124-250">Open an Admin Command Prompt, and upgrade all installed components and instances</span></span> 
        - <span data-ttu-id="35124-251">Пример: C:\01_2014SqlSp2\SQLServer2014SP2-KB3171021-x64-ENU.exe /qs /IAcceptSQLServerLicenseTerms /Action = исправление строки.</span><span class="sxs-lookup"><span data-stu-id="35124-251">Example: C:\01_2014SqlSp2\SQLServer2014SP2-KB3171021-x64-ENU.exe /qs /IAcceptSQLServerLicenseTerms /Action=Patch /AllInstances</span></span>
4. <span data-ttu-id="35124-252">Обновите собственного клиента SQL.</span><span class="sxs-lookup"><span data-stu-id="35124-252">Update SQL Native Client.</span></span> 
    1. <span data-ttu-id="35124-253">Ссылка: [https://support.microsoft.com/en-us/help/3135244/tls-1-2-support-for-microsoft-sql-server](https://support.microsoft.com/en-us/help/3135244/tls-1-2-support-for-microsoft-sql-server).</span><span class="sxs-lookup"><span data-stu-id="35124-253">Reference: [https://support.microsoft.com/en-us/help/3135244/tls-1-2-support-for-microsoft-sql-server](https://support.microsoft.com/en-us/help/3135244/tls-1-2-support-for-microsoft-sql-server).</span></span>
    2. <span data-ttu-id="35124-254">Загрузите из[https://www.microsoft.com/en-us/download/details.aspx?id=50402](https://www.microsoft.com/en-us/download/details.aspx?id=50402)</span><span class="sxs-lookup"><span data-stu-id="35124-254">Download from [https://www.microsoft.com/en-us/download/details.aspx?id=50402](https://www.microsoft.com/en-us/download/details.aspx?id=50402)</span></span>
    3. <span data-ttu-id="35124-255">Обеспечить Скайп Business Server 2015 остановлен служб на сервере переднего плана.</span><span class="sxs-lookup"><span data-stu-id="35124-255">Ensure Skype for Business Server 2015 services are stopped on the Front End server.</span></span> 
        - <span data-ttu-id="35124-256">Ex (Standard Edition): Stop-CsWindowsServices</span><span class="sxs-lookup"><span data-stu-id="35124-256">Ex (Standard Edition): Stop-CsWindowsServices</span></span>
        - <span data-ttu-id="35124-257">Ex (Enterprise Edition): Invoke-CsComputerFailove</span><span class="sxs-lookup"><span data-stu-id="35124-257">Ex (Enterprise Edition): Invoke-CsComputerFailove</span></span>
    4. <span data-ttu-id="35124-258">Остановка установленных запуск экземпляров SQL</span><span class="sxs-lookup"><span data-stu-id="35124-258">Stop the SQL instances installed from running</span></span> 
        - <span data-ttu-id="35124-259">Пример: «RTCLOCAL MSSQL$» Get-Service | Остановить служва</span><span class="sxs-lookup"><span data-stu-id="35124-259">Ex: Get-Service 'MSSQL$RTCLOCAL' | Stop-Servic</span></span>
        - <span data-ttu-id="35124-260">Пример: «LYNCLOCAL MSSQL$» Get-Service | Остановить служва</span><span class="sxs-lookup"><span data-stu-id="35124-260">Ex: Get-Service 'MSSQL$LYNCLOCAL' | Stop-Servic</span></span>
        - <span data-ttu-id="35124-261">Ex (Standard Edition только): Get-Service «RTC MSSQL$» | Остановить служва</span><span class="sxs-lookup"><span data-stu-id="35124-261">Ex (Standard Edition Only): Get-Service 'MSSQL$RTC' | Stop-Servic</span></span>
    5. <span data-ttu-id="35124-262">Установите обновление.</span><span class="sxs-lookup"><span data-stu-id="35124-262">Install the update.</span></span>
5. <span data-ttu-id="35124-263">Обновите драйвер ODBC 11 для SQL Server.</span><span class="sxs-lookup"><span data-stu-id="35124-263">Update ODBC Driver 11 for SQL Server.</span></span> 
    1. <span data-ttu-id="35124-264">Ссылка: [https://support.microsoft.com/en-us/help/3135244/tls-1-2-support-for-microsoft-sql-server](https://support.microsoft.com/en-us/help/3135244/tls-1-2-support-for-microsoft-sql-server).</span><span class="sxs-lookup"><span data-stu-id="35124-264">Reference: [https://support.microsoft.com/en-us/help/3135244/tls-1-2-support-for-microsoft-sql-server](https://support.microsoft.com/en-us/help/3135244/tls-1-2-support-for-microsoft-sql-server).</span></span>
    2. <span data-ttu-id="35124-265">Загрузите из[https://www.microsoft.com/en-us/download/confirmation.aspx?id=36434](https://www.microsoft.com/en-us/download/confirmation.aspx?id=36434)</span><span class="sxs-lookup"><span data-stu-id="35124-265">Download from [https://www.microsoft.com/en-us/download/confirmation.aspx?id=36434](https://www.microsoft.com/en-us/download/confirmation.aspx?id=36434)</span></span>
    3. <span data-ttu-id="35124-266">Убедитесь, что Скайп для служб Business Server 2015 останавливаются на сервере переднего плана</span><span class="sxs-lookup"><span data-stu-id="35124-266">Ensure that Skype for Business Server 2015 services are stopped on the Front End server</span></span> 
        - <span data-ttu-id="35124-267">Ex (Standard Edition): Stop-CsWindowsService</span><span class="sxs-lookup"><span data-stu-id="35124-267">Ex (Standard Edition): Stop-CsWindowsService</span></span>
        - <span data-ttu-id="35124-268">Ex (Enterprise Edition): Invoke-CsComputerFailove</span><span class="sxs-lookup"><span data-stu-id="35124-268">Ex (Enterprise Edition): Invoke-CsComputerFailove</span></span>
    4. <span data-ttu-id="35124-269">Установите обновление.</span><span class="sxs-lookup"><span data-stu-id="35124-269">Install the update.</span></span>
6. <span data-ttu-id="35124-270">Разверните разделы реестра, необходимых компонентов.</span><span class="sxs-lookup"><span data-stu-id="35124-270">Deploy prerequisite registry keys.</span></span>

### <a name="pre-requisite-registry-keys"></a><span data-ttu-id="35124-271">Необходимые предварительные реестра</span><span class="sxs-lookup"><span data-stu-id="35124-271">Pre-requisite registry keys</span></span>

<span data-ttu-id="35124-272">Копирование и вставка следующего теста в Блокнот и переименуйте TLSPreReq.reg или имя собственное, а затем импортировать:</span><span class="sxs-lookup"><span data-stu-id="35124-272">Copy/paste the following test into Notepad and rename TLSPreReq.reg or a name of your choice, then import:</span></span>

```
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

<span data-ttu-id="35124-273">Для SQL назад, отключить концов пулы Enterprise Edition, необходимые условия и TLS следует рассматривать как бы все SQL и операционная система обновления; Обратитесь к:[https://docs.microsoft.com/skypeforbusiness/manage/topology/patch-or-update-a-back-end-or-standard-edition-server](https://docs.microsoft.com/skypeforbusiness/manage/topology/patch-or-update-a-back-end-or-standard-edition-server)</span><span class="sxs-lookup"><span data-stu-id="35124-273">For SQL back ends for Enterprise Edition Pools, prerequisites and TLS disable should be treated as any SQL or OS updates would; refer to: [https://docs.microsoft.com/skypeforbusiness/manage/topology/patch-or-update-a-back-end-or-standard-edition-server](https://docs.microsoft.com/skypeforbusiness/manage/topology/patch-or-update-a-back-end-or-standard-edition-server)</span></span>

<span data-ttu-id="35124-274">Хотя можно сочетать необходимых приложений и отключение действия TLS, мы настоятельно рекомендуем применить все необходимые компоненты перед тем как продолжить отключение TLS 1.0 и 1.1 на уровне операционной системы.</span><span class="sxs-lookup"><span data-stu-id="35124-274">While both the prerequisite application and TLS disabling steps can be combined, we strongly recommend all prerequisites be applied before proceeding with disabling of TLS 1.0 and 1.1 at the operating system level.</span></span> <span data-ttu-id="35124-275">Подготовка среды развертывания все необходимые компоненты, проверка, что все рабочие нагрузки работает правильно и надлежащим образом, а затем отключите переходом с TLS 1.0/1.1 позднее будет best practice подход.</span><span class="sxs-lookup"><span data-stu-id="35124-275">The best practice approach would be to prepare the environment by deploying all prerequisites, validating that workloads all function correctly and as expected, and then proceeding with TLS 1.0/1.1 disable at a later time.</span></span>

### <a name="disable-tls-10-and-11-via-registry-import"></a><span data-ttu-id="35124-276">Отключить протокол TLS 1.0 и 1.1 с помощью реестра импорта</span><span class="sxs-lookup"><span data-stu-id="35124-276">Disable TLS 1.0 and 1.1 via registry import</span></span>

<span data-ttu-id="35124-277">Перед началом дальнейшие действия, *Убедитесь, что выполнены все необходимые условия и обновление Скайп для серверов организаций*.</span><span class="sxs-lookup"><span data-stu-id="35124-277">Before you proceed with the next steps, *make sure you have completed all prerequisites and updated Skype for Business Servers*.</span></span>

<span data-ttu-id="35124-278">Скопируйте следующий текст в файл Блокнота и переименуйте его **TLSDisable.reg**:</span><span class="sxs-lookup"><span data-stu-id="35124-278">Copy the following text into a Notepad file and rename it **TLSDisable.reg**:</span></span>

```
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

<span data-ttu-id="35124-279">Импортируйте REG-файл на каждом сервере, который вы хотите отключить TLS 1.0 и 1.1.</span><span class="sxs-lookup"><span data-stu-id="35124-279">Import the .reg file on each server you wish to disable TLS 1.0 and 1.1.</span></span> <span data-ttu-id="35124-280">Перезагрузите сервер.</span><span class="sxs-lookup"><span data-stu-id="35124-280">Reboot the server.</span></span> <span data-ttu-id="35124-281">После службы оперативный, перемещение к следующему серверу.</span><span class="sxs-lookup"><span data-stu-id="35124-281">Once the services have come back online, move to the next server.</span></span> <span data-ttu-id="35124-282">Подход для пулов Enterprise Edition — это же может занять все обновления операционной системы.</span><span class="sxs-lookup"><span data-stu-id="35124-282">The approach for Enterprise Edition Pools is the same you would take for any OS update.</span></span>

<span data-ttu-id="35124-283">Вы могли заметить, что это делается больше, чем просто отключение TLS 1.0 и 1.1 здесь.</span><span class="sxs-lookup"><span data-stu-id="35124-283">You may have noticed we are doing more than just disabling TLS 1.0 and 1.1 here.</span></span> <span data-ttu-id="35124-284">Мы это вспомогательные шифрования Suite, изменять порядок (как показано выше) и отключение некоторых старых слабые шифры.</span><span class="sxs-lookup"><span data-stu-id="35124-284">We are supporting Cipher Suite re-order (as shown above) and the disabling of some older weak ciphers.</span></span> <span data-ttu-id="35124-285">В первый раз мы официально поддерживаемые эти изменения SCHANNEL и API шифрования на Скайп для Business Server и важно Обратите внимание на то, что эти изменения являются единственными мы поддержки и тестирования в данный момент.</span><span class="sxs-lookup"><span data-stu-id="35124-285">This is the first time we have officially supported these changes to SCHANNEL and Crypto API on Skype for Business Server, and it is important to note that these changes are the only ones we support and have tested at this time.</span></span> <span data-ttu-id="35124-286">Мы рассмотрим дополнительных конфигураций в будущем, но в данный момент, не изменяйте файл импорта реестра в реализации.</span><span class="sxs-lookup"><span data-stu-id="35124-286">We may consider additional configurations in the future, but for now, please do not modify the registry import file in your implementation.</span></span>

### <a name="validate-that-workloads-are-functioning-as-expected"></a><span data-ttu-id="35124-287">Убедиться, что рабочие нагрузки работают должным образом</span><span class="sxs-lookup"><span data-stu-id="35124-287">Validate that workloads are functioning as expected</span></span>

<span data-ttu-id="35124-288">После TLS 1.0 и 1.1 отключены в вашей среде, убедитесь, что все основные рабочие нагрузки работают должным образом, такие как обмен мгновенными Сообщениями & сведения о присутствии, P2P вызовов корпоративной голосовой связи и т.д.</span><span class="sxs-lookup"><span data-stu-id="35124-288">Once TLS 1.0 and 1.1 have been disabled in your environment, ensure that all your main workloads are functioning as expected, such as IM & Presence, P2P calls, Enterprise Voice, etc.</span></span>

<span data-ttu-id="35124-289">**Проверить, используется только протокол TLS 1.2 (en)**</span><span class="sxs-lookup"><span data-stu-id="35124-289">**Validate only TLS 1.2 is being used**</span></span>

<span data-ttu-id="35124-290">У группы безопасности выполнение новых аудита Скайп для бизнес-трафика, чтобы убедиться, что старые протоколы TLS 1.0 и 1.1 больше не используется.</span><span class="sxs-lookup"><span data-stu-id="35124-290">Have your Security Team perform a new audit of Skype for Business traffic to ensure that the older protocols TLS 1.0 and 1.1 are no longer in use.</span></span>

<span data-ttu-id="35124-291">Кроме того можно использовать Internet Explorer для проверки подключений TLS для веб-служб из Скайп Business Server 2015 после отключения TLS 1.0 и TLS 1.1.</span><span class="sxs-lookup"><span data-stu-id="35124-291">Alternatively, you can use Internet Explorer to test TLS connections to web services from Skype for Business Server 2015 after TLS 1.0 and TLS 1.1 have been disabled.</span></span>

1. <span data-ttu-id="35124-292">Запустите браузер Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="35124-292">Launch Internet Explorer.</span></span>
2. <span data-ttu-id="35124-293">Выбор **инструментов** > **Свойства обозревателя**.</span><span class="sxs-lookup"><span data-stu-id="35124-293">Select **Tools** > **Internet Options**.</span></span>
3. <span data-ttu-id="35124-294">Перейдите на вкладку **Дополнительно** .</span><span class="sxs-lookup"><span data-stu-id="35124-294">Select the **Advanced** tab.</span></span>
4. <span data-ttu-id="35124-295">В разделе **Параметры**прокрутите список вниз.</span><span class="sxs-lookup"><span data-stu-id="35124-295">Under **Settings**, scroll to the bottom.</span></span>
5. <span data-ttu-id="35124-296">Убедитесь, что включены TLS 1.0, TLS 1.1 и TLS 1.2.</span><span class="sxs-lookup"><span data-stu-id="35124-296">Verify that TLS 1.0, TLS 1.1, and TLS 1.2 are enabled.</span></span>
6. <span data-ttu-id="35124-297">Обзор внутренних Web URL-адрес службы пула SfB 2015 (должен установить связь).</span><span class="sxs-lookup"><span data-stu-id="35124-297">Browse the Internal Web Service URL of your SfB 2015 pool (should connect successfully).</span></span>
7. <span data-ttu-id="35124-298">Вернитесь в Internet Explorer и отключить возможность **использования TLS 1.2** только.</span><span class="sxs-lookup"><span data-stu-id="35124-298">Go back into Internet Explorer and disable the option to **Use TLS 1.2** only.</span></span>
8. <span data-ttu-id="35124-299">Обзор внутренних Web URL-адрес службы SfB 2015 пула еще раз (не сможет выполнить подключение).</span><span class="sxs-lookup"><span data-stu-id="35124-299">Browse the Internal Web Service URL of your SfB 2015 pool again (should fail to connect).</span></span>

![Свойства обозревателя](../../media/internet-options.jpg)

## <a name="advanced-deployment-scenarios"></a><span data-ttu-id="35124-301">Расширенные сценарии развертывания</span><span class="sxs-lookup"><span data-stu-id="35124-301">Advanced deployment scenarios</span></span>

<span data-ttu-id="35124-302">Так как некоторые компоненты зависимость требуются для поддержки TLS 1.2 в Скайп для бизнеса пользователе 2015, установка с носителя RTM завершится ошибкой в любой системе, где были отключены TLS 1.0 и 1.1.</span><span class="sxs-lookup"><span data-stu-id="35124-302">Because some dependency prerequisites are required to support TLS 1.2 in Skype for Business Ser 2015, installing from RTM media will fail on any system where TLS 1.0 and 1.1 have been disabled.</span></span>

<span data-ttu-id="35124-303">**Развертывание новых серверов Standard Edition или пулы Enterprise Edition после TLS 1.0 и 1.1 отключены в вашей среде.**</span><span class="sxs-lookup"><span data-stu-id="35124-303">**Deploying New Standard Edition Servers or Enterprise Edition Pools once TLS 1.0 and 1.1 have been disabled in your environment.**</span></span>

<span data-ttu-id="35124-304">**Вариант 1:** С помощью [SmartSetup](../../deploy/install/install-skype-for-business-server.md).</span><span class="sxs-lookup"><span data-stu-id="35124-304">**Option 1:** Use [SmartSetup](../../deploy/install/install-skype-for-business-server.md).</span></span> <span data-ttu-id="35124-305">Обратите внимание, что мы обновления SmartSetup для учета обновленные двоичные файлы SQL в будущем накопительный пакет обновления за и будут обновляться в этой статье.</span><span class="sxs-lookup"><span data-stu-id="35124-305">Note that we are updating SmartSetup to accommodate the updated SQL binaries in a future CU, and will update this article in the future.</span></span>

<span data-ttu-id="35124-306">**Вариант 2:** Предварительная установка экземпляров SQL (RTCLOCAL и LYNCLOCAL)</span><span class="sxs-lookup"><span data-stu-id="35124-306">**Option 2:** Pre-install local SQL instances (RTCLOCAL and LYNCLOCAL)</span></span>

1. <span data-ttu-id="35124-307">Загрузите и скопируйте SQL Express 2014 с пакетом обновления 2 (SQLEXPR_x64.exe) в локальной папке на FE.</span><span class="sxs-lookup"><span data-stu-id="35124-307">Download and copy SQL Express 2014 SP2 (SQLEXPR_x64.exe) to local folder on FE.</span></span> <span data-ttu-id="35124-308">Предположим, <SQL_FOLDER_PATH> путь папки.</span><span class="sxs-lookup"><span data-stu-id="35124-308">Let’s say folder path <SQL_FOLDER_PATH>.</span></span>
2. <span data-ttu-id="35124-309">Запустите PowerShell или командной строки и перейдите к <SQL_FOLDER_PATH>.</span><span class="sxs-lookup"><span data-stu-id="35124-309">Launch PowerShell or Command Prompt and navigate to <SQL_FOLDER_PATH>.</span></span>
3. <span data-ttu-id="35124-310">Создайте экземпляр RTCLOCAL SQL с помощью следующей команды.</span><span class="sxs-lookup"><span data-stu-id="35124-310">Create the RTCLOCAL SQL instance by running the command below.</span></span> <span data-ttu-id="35124-311">Подождите, пока завершится SQLEXPR_x64.exe перед тем как:</span><span class="sxs-lookup"><span data-stu-id="35124-311">Wait until SQLEXPR_x64.exe finishes before proceeding:</span></span>

    <span data-ttu-id="35124-312">SQLEXPR_x64.exe /Q /IACCEPTSQLSERVERLICENSETERMS /UPDATEENABLED = 0 /HIDECONSOLE /ACTION = Установка/КОМПОНЕНТЫ = SQLEngine, средств режим = RTCLOCAL /TCPENABLED = 1 /SQLSVCACCOUNT = «NT AUTHORITY\NetworkService» /SQLSYSADMINACCOUNTS = «Builtin\ Администраторы» /BROWSERSVCSTARTUPTYPE = «Automatic» /AGTSVCACCOUNT = «NTAUTHORITY\NetworkService» /SQLSVCSTARTUPTYPE = автомати</span><span class="sxs-lookup"><span data-stu-id="35124-312">SQLEXPR_x64.exe  /Q /IACCEPTSQLSERVERLICENSETERMS /UPDATEENABLED=0 /HIDECONSOLE /ACTION=Install /FEATURES=SQLEngine,Tools /INSTANCENAME=RTCLOCAL /TCPENABLED=1 /SQLSVCACCOUNT="NT AUTHORITY\NetworkService" /SQLSYSADMINACCOUNTS="Builtin\Administrators" /BROWSERSVCSTARTUPTYPE="Automatic" /AGTSVCACCOUNT="NTAUTHORITY\NetworkService" /SQLSVCSTARTUPTYPE=Automati</span></span>
1. <span data-ttu-id="35124-313">Создайте экземпляр LYNCLOCAL SQL с помощью следующей команды.</span><span class="sxs-lookup"><span data-stu-id="35124-313">Create the LYNCLOCAL SQL instance by running the command below.</span></span> <span data-ttu-id="35124-314">Подождите, пока завершится SQLEXPR_x64.exe перед переходом к следующему шагу:</span><span class="sxs-lookup"><span data-stu-id="35124-314">Wait until SQLEXPR_x64.exe finishes before proceeding to the next step:</span></span>

    <span data-ttu-id="35124-315">SQLEXPR_x64.exe /Q /IACCEPTSQLSERVERLICENSETERMS /UPDATEENABLED = 0 /HIDECONSOLE /ACTION = Установка/КОМПОНЕНТЫ = SQLEngine, средств режим = LYNCLOCAL /TCPENABLED = 1 /SQLSVCACCOUNT = «NT AUTHORITY\NetworkService» /SQLSYSADMINACCOUNTS = «Builtin\ Администраторы» /BROWSERSVCSTARTUPTYPE = «Automatic» /AGTSVCACCOUNT = «NTAUTHORITY\NetworkService» /SQLSVCSTARTUPTYPE = автоматический</span><span class="sxs-lookup"><span data-stu-id="35124-315">SQLEXPR_x64.exe /Q /IACCEPTSQLSERVERLICENSETERMS /UPDATEENABLED=0 /HIDECONSOLE /ACTION=Install /FEATURES=SQLEngine,Tools /INSTANCENAME=LYNCLOCAL /TCPENABLED=1 /SQLSVCACCOUNT="NT AUTHORITY\NetworkService" /SQLSYSADMINACCOUNTS="Builtin\Administrators" /BROWSERSVCSTARTUPTYPE="Automatic" /AGTSVCACCOUNT="NTAUTHORITY\NetworkService" /SQLSVCSTARTUPTYPE=Automatic</span></span>
1. <span data-ttu-id="35124-316">Запустите Скайп для программы установки, Business Server 2015 RTM.</span><span class="sxs-lookup"><span data-stu-id="35124-316">Run Skype for Business Server 2015 RTM setup.</span></span>
2. <span data-ttu-id="35124-317">Выполните остальные действия в предыдущем разделе необходимых компонентов.</span><span class="sxs-lookup"><span data-stu-id="35124-317">Follow the remaining steps from the prerequisites section above.</span></span>

<span data-ttu-id="35124-318">**Вариант 3:** Могут также вручную замените двоичные файлы в каталог мультимедиа локальной установки следующим образом:</span><span class="sxs-lookup"><span data-stu-id="35124-318">**Option 3:** You may also manually replace binaries in a local installation media directory as follows:</span></span>

1. [<span data-ttu-id="35124-319">Установка необходимых компонентов для Скайп для Business Server</span><span class="sxs-lookup"><span data-stu-id="35124-319">Install prerequisites for Skype for Business Server</span></span>](../../deploy/install/install-prerequisites.md)  
2. 2. <span data-ttu-id="35124-320">Установка .NET 4.7:</span><span class="sxs-lookup"><span data-stu-id="35124-320">Install .NET 4.7:</span></span> 
      - <span data-ttu-id="35124-321">**Примечание:** Мы впервые представлена поддержка 4.7 .NET в Скайп для Business Server 2015 накопительным пакетом обновления 5 + (6.0.9319.281).</span><span class="sxs-lookup"><span data-stu-id="35124-321">**Note:** We first introduced support for .NET 4.7 in Skype for Business Server 2015 CU5+ (6.0.9319.281).</span></span> <span data-ttu-id="35124-322">Таким образом на последующих этапах ниже мы будет обновляться основные компоненты до основной установки.</span><span class="sxs-lookup"><span data-stu-id="35124-322">Therefore, in later steps below we will be updating Core Components prior to the main install.</span></span>
      - <span data-ttu-id="35124-323">Загрузка: https://www.microsoft.com/en-us/download/details.aspx?id=55167.</span><span class="sxs-lookup"><span data-stu-id="35124-323">Download: https://www.microsoft.com/en-us/download/details.aspx?id=55167.</span></span>
      - <span data-ttu-id="35124-324">Ссылка: [программное обеспечение, которое должны быть установлены перед Скайп для развертывания Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md#software-that-should-be-installed-before-a-skype-for-business-server-2015-deployment)</span><span class="sxs-lookup"><span data-stu-id="35124-324">Reference: [Software that should be installed before a Skype for Business Server 2015 deployment](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md#software-that-should-be-installed-before-a-skype-for-business-server-2015-deployment)</span></span>
3. <span data-ttu-id="35124-325">Скопируйте файлы/папки ISO:</span><span class="sxs-lookup"><span data-stu-id="35124-325">Copy ISO Files/Folders:</span></span> 
    - <span data-ttu-id="35124-326">С помощью Скайп для Business Server 2015 ISO подключенное, откройте корневой каталог диска, подключенный как (Ex: D:\) в File Explorer.</span><span class="sxs-lookup"><span data-stu-id="35124-326">With the Skype for Business Server 2015 ISO attached, open the root directory of the drive it is attached as (Ex: D:\) in File Explorer.</span></span>
    - <span data-ttu-id="35124-327">Скопируйте все папки и файлы в папку на локальном диске (например: C:\SkypeForBusiness2015ISO).</span><span class="sxs-lookup"><span data-stu-id="35124-327">Copy all folders and files to a folder on a local disk (Ex: C:\SkypeForBusiness2015ISO).</span></span>
    - <span data-ttu-id="35124-328">**Примечание:** Перед установкой компонентов, некоторые файлы необходимо обновить для поддержки TLS 1.2.</span><span class="sxs-lookup"><span data-stu-id="35124-328">**Note:** Prior to installing components, some files will need to be updated for support of TLS 1.2.</span></span>
4. <span data-ttu-id="35124-329">Замените пакеты MSI и exe-ФАЙЛ:</span><span class="sxs-lookup"><span data-stu-id="35124-329">Replace MSI/EXE Packages:</span></span> 
    - <span data-ttu-id="35124-330">Замена существующих пакетов MSI и exe-ФАЙЛ в папку/amd64 / / Setup установочного носителя на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="35124-330">Replace the existing MSI and EXE packages in the /Setup/amd64/ folder of the installation media on the local machine.</span></span>
    - <span data-ttu-id="35124-331">SQL Express с пакетом обновления 2 2014 г.:https://www.microsoft.com/en-us/download/details.aspx?id=53167</span><span class="sxs-lookup"><span data-stu-id="35124-331">SQL 2014 SP2 Express: https://www.microsoft.com/en-us/download/details.aspx?id=53167</span></span> 
        - <span data-ttu-id="35124-332">Измените имя на SQLEXPR_x64 на локальном компьютере и заменить существующий файл в установки/amd64/папки с установочного носителя.</span><span class="sxs-lookup"><span data-stu-id="35124-332">Rename to SQLEXPR_x64 on the local machine, and replace the existing file in the Setup/amd64/ folder of the installation media.</span></span>
    - <span data-ttu-id="35124-333">Собственный клиент SQL:https://www.microsoft.com/en-us/download/details.aspx?id=50402</span><span class="sxs-lookup"><span data-stu-id="35124-333">SQL Native Client: https://www.microsoft.com/en-us/download/details.aspx?id=50402</span></span> 
        - <span data-ttu-id="35124-334">**Примечание:** Переименование это при необходимости sqlncli.msi, а затем заменить существующий файл, который существует в установки/amd64/папки с установочного носителя.</span><span class="sxs-lookup"><span data-stu-id="35124-334">**Note:** Rename this if necessary to sqlncli.msi, and then replace the existing file that exists in the Setup/amd64/ folder of the installation media.</span></span>
    - <span data-ttu-id="35124-335">Объекты AMO SQL:https://www.microsoft.com/en-us/download/details.aspx?id=53164</span><span class="sxs-lookup"><span data-stu-id="35124-335">SQL Management Objects: https://www.microsoft.com/en-us/download/details.aspx?id=53164</span></span> 
        - <span data-ttu-id="35124-336">**Примечание:** Пакет дополнительных компонентов будут иметь много элементов, которые можно загрузить.</span><span class="sxs-lookup"><span data-stu-id="35124-336">**Note:** The Feature pack will have a lot of items that can be downloaded.</span></span> <span data-ttu-id="35124-337">Выберите только для загрузки SharedManagementObjects.msi.</span><span class="sxs-lookup"><span data-stu-id="35124-337">Select to download SharedManagementObjects.msi only.</span></span>
        - <span data-ttu-id="35124-338">**Примечание:** Заменить существующий файл, который существует в установки/amd64/папки с установочного носителя.</span><span class="sxs-lookup"><span data-stu-id="35124-338">**Note:** Replace the existing file that exists in the Setup/amd64/ folder of the installation media.</span></span>
    - <span data-ttu-id="35124-339">Типы SQL CLR:https://www.microsoft.com/en-us/download/details.aspx?id=53164</span><span class="sxs-lookup"><span data-stu-id="35124-339">SQL CLR Types: https://www.microsoft.com/en-us/download/details.aspx?id=53164</span></span> 
        - <span data-ttu-id="35124-340">**Примечание:** Пакет дополнительных компонентов будут иметь много элементов, которые можно загрузить.</span><span class="sxs-lookup"><span data-stu-id="35124-340">**Note:** The Feature pack will have a lot of items that can be downloaded.</span></span> <span data-ttu-id="35124-341">Выберите только для загрузки CQLSysClrTypes.msi</span><span class="sxs-lookup"><span data-stu-id="35124-341">Select to download CQLSysClrTypes.msi only</span></span>
        - <span data-ttu-id="35124-342">**Примечание**: заменить существующий файл, который существует в установки/amd64/папки с установочного носителя.</span><span class="sxs-lookup"><span data-stu-id="35124-342">**Note**: Replace the existing file that exists in the Setup/amd64/ folder of the installation media.</span></span>
5. <span data-ttu-id="35124-343">Установите основные компоненты:</span><span class="sxs-lookup"><span data-stu-id="35124-343">Install Core Components:</span></span> 
    - <span data-ttu-id="35124-344">Запустите Setup.exe из программы установки и amd64/папки с установочного носителя.</span><span class="sxs-lookup"><span data-stu-id="35124-344">Run Setup.exe from the Setup/amd64/ folder of the installation media.</span></span> <span data-ttu-id="35124-345">Следуйте инструкциям, чтобы установить компоненты ядра</span><span class="sxs-lookup"><span data-stu-id="35124-345">Follow the instructions to install Core Components</span></span>
    - <span data-ttu-id="35124-346">Закройте основные компоненты.</span><span class="sxs-lookup"><span data-stu-id="35124-346">Close Core Components.</span></span>
6. <span data-ttu-id="35124-347">Обновление основных компонентов:</span><span class="sxs-lookup"><span data-stu-id="35124-347">Update Core Components:</span></span> 
    - <span data-ttu-id="35124-348">Загрузите Скайп для установки обновлений бизнеса.</span><span class="sxs-lookup"><span data-stu-id="35124-348">Download the Skype for Business Update Installer.</span></span>
    - <span data-ttu-id="35124-349">Программа установки обновления основных компонентов и установить счетчики производительности.</span><span class="sxs-lookup"><span data-stu-id="35124-349">Run the installer to update Core Components and install the performance counters.</span></span>
    - <span data-ttu-id="35124-350">**Примечание:** По состоянию на выпуск CU6HF2 функция автоматического обновления в настоящее время только предназначенным для установки до CU6.</span><span class="sxs-lookup"><span data-stu-id="35124-350">**Note:** As of the release of CU6HF2, the auto-update feature currently only will install up to CU6.</span></span> <span data-ttu-id="35124-351">Таким образом средство обновления необходимо выполнить отдельно для обновления основных компонентов 6.0.9319.516.</span><span class="sxs-lookup"><span data-stu-id="35124-351">Therefore, the updater must be run separately to update Core Components to 6.0.9319.516.</span></span>
    - <span data-ttu-id="35124-352">Ссылка:https://support.microsoft.com/en-us/help/3061064/updates-for-skype-for-business-server-2015</span><span class="sxs-lookup"><span data-stu-id="35124-352">Reference: https://support.microsoft.com/en-us/help/3061064/updates-for-skype-for-business-server-2015</span></span>
7. <span data-ttu-id="35124-353">Установка средств администрирования (необязательно):</span><span class="sxs-lookup"><span data-stu-id="35124-353">Install Administrative Tools (Optional):</span></span> 
    - <span data-ttu-id="35124-354">Будет выполнена установка собственного клиента Microsoft SQL Server 2012, 2014 управляющих объектов SQL Server (x64) и системные типы CLR для SQL Server 2014 (x64) с использованием обновленных файлов.</span><span class="sxs-lookup"><span data-stu-id="35124-354">This will install the Microsoft SQL Server 2012 Native Client, SQL Server 2014 Management Objects (x64), and Microsoft System CLR Types for SQL Server 2014 (x64) using the updated files.</span></span> <span data-ttu-id="35124-355">Кроме того Скайп для Business Server 2015 Topology Builder и панель управления, будут доступны на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="35124-355">Additionally, the Skype for Business Server 2015 Topology Builder and Control Panel will be available on the local machine.</span></span>
8. <span data-ttu-id="35124-356">Установка локального хранилища конфигурации (шаг 1):</span><span class="sxs-lookup"><span data-stu-id="35124-356">Install Local Configuration Store (Step 1):</span></span> 
     - <span data-ttu-id="35124-357">Откройте мастер развертывания, выберите установить или обновление Скайп для бизнес-системы сервера и выберите команду **выполнить** в шаге 1: Установка локального хранилища конфигурации.</span><span class="sxs-lookup"><span data-stu-id="35124-357">Open the Deployment Wizard, click Install or Update Skype for Business Server System, and click on **Run** at Step 1: Install Local Configuration Store.</span></span>
     - <span data-ttu-id="35124-358">Нажмите кнопку **Далее** в диалоговом окне **Установка локального хранилища конфигурации** .</span><span class="sxs-lookup"><span data-stu-id="35124-358">Click **Next** in the **Install Local Configuration Store** dialog box.</span></span>
     <span data-ttu-id="35124-359">![Диалоговое окно Установка локального хранилища конфигурации](../../media/local-configuration-store.png)</span><span class="sxs-lookup"><span data-stu-id="35124-359">![Install Local Configuration Store dialog box](../../media/local-configuration-store.png)</span></span>
     - <span data-ttu-id="35124-360">Проанализируйте результаты и убедитесь, что состояние задачи завершено.</span><span class="sxs-lookup"><span data-stu-id="35124-360">Review the results, and ensure that the Task Status is Completed.</span></span> <span data-ttu-id="35124-361">Просмотрите созданный файл журнала, нажав кнопку **Просмотреть журнал**.</span><span class="sxs-lookup"><span data-stu-id="35124-361">Review the resulting log file by clicking **View Log**.</span></span>
     <span data-ttu-id="35124-362">![Состояние задачи отображается как завершено](../../media/local-configuration-task-completed.png)</span><span class="sxs-lookup"><span data-stu-id="35124-362">![Task status shows as Completed](../../media/local-configuration-task-completed.png)</span></span>
     - <span data-ttu-id="35124-363">Нажмите **Готово**.</span><span class="sxs-lookup"><span data-stu-id="35124-363">Click **Finish**.</span></span>
9. <span data-ttu-id="35124-364">Установка и удаление Скайп для бизнес-компоненты сервера (шаг 2):</span><span class="sxs-lookup"><span data-stu-id="35124-364">Set up or remove Skype for Business Server Components (Step 2):</span></span>
    - <span data-ttu-id="35124-365">Откройте мастер развертывания, выберите **установить или обновление Скайп для бизнес-системы сервера**и нажмите кнопку **Запуск** на шаге 2: Установка и удаление Скайп для бизнеса серверных компонентов</span><span class="sxs-lookup"><span data-stu-id="35124-365">Open the Deployment Wizard, click **Install or Update Skype for Business Server System**, and click **Run** at Step 2: Set up or Remove Skype for Business Server Components</span></span>
    - <span data-ttu-id="35124-366">Нажмите кнопку **Далее** в задать копирование Скайп для диалогового окна Business серверных компонентов.</span><span class="sxs-lookup"><span data-stu-id="35124-366">Click **Next** in the Set Up Skype for Business Server Components dialog box.</span></span>
    <span data-ttu-id="35124-367">![Задайте копирование Скайп для бизнеса серверных компонентов окна](../../media/set-up-skype-for-business-server-components-window.png)</span><span class="sxs-lookup"><span data-stu-id="35124-367">![the Set Up Skype for Business Server Components window](../../media/set-up-skype-for-business-server-components-window.png)</span></span>
    - <span data-ttu-id="35124-368">Просмотр журнала с помощью просмотреть журнал и проверки, установка завершена без проблем.</span><span class="sxs-lookup"><span data-stu-id="35124-368">Review the log using View Log, and validate that setup completed without issues.</span></span> 
    - <span data-ttu-id="35124-369">Нажмите **Готово**.</span><span class="sxs-lookup"><span data-stu-id="35124-369">Click **Finish**.</span></span>
10. <span data-ttu-id="35124-370">Дополнительные установки и конфигурации в соответствии с требованиями (можно возобновить процедуры обычной установки на этом этапе).</span><span class="sxs-lookup"><span data-stu-id="35124-370">Proceed with additional installation and configuration as required (you can resume normal installation procedures at this point).</span></span>
