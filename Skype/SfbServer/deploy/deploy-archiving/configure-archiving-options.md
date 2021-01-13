---
title: Настройка параметров архива для Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 2f534697-ac7f-45b7-8cdc-ba67f052223b
description: Сводка. В этом разделе вы узнаете, как настроить начальные параметры архива для Skype для бизнеса Server. Конфигурации архивации изначально устанавливаются при развертывании архивации, но после развертывания можно изменять, добавлять и удалять конфигурации.
ms.openlocfilehash: 0a4803b821ee082a548b9f429b9596fd8019500f
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49815539"
---
# <a name="configure-archiving-options-for-skype-for-business-server"></a><span data-ttu-id="4b012-104">Настройка параметров архива для Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="4b012-104">Configure archiving options for Skype for Business Server</span></span>
 
<span data-ttu-id="4b012-105">**Сводка:** В этом разделе вы узнаете, как настроить исходные параметры архива для Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="4b012-105">**Summary:** Read this topic to learn how to configure initial archiving options for Skype for Business Server.</span></span> <span data-ttu-id="4b012-106">Конфигурации архивации изначально устанавливаются при развертывании архивации, но после развертывания можно изменять, добавлять и удалять конфигурации.</span><span class="sxs-lookup"><span data-stu-id="4b012-106">You initially set up archiving configurations when you deploy archiving, but you can change, add, and delete configurations after deployment.</span></span>
  
<span data-ttu-id="4b012-107">Чтобы настроить начальные конфигурации архивации, используйте панель управления Skype для бизнеса Server, чтобы указать следующее:</span><span class="sxs-lookup"><span data-stu-id="4b012-107">To configure initial archiving configurations, you use Skype for Business Server Control Panel to specify the following:</span></span>
  
- <span data-ttu-id="4b012-108">Конфигурация глобального уровня, которая создается по умолчанию при развертывании Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="4b012-108">Global-level configuration that is created by default when you deploy Skype for Business Server</span></span>
    
- <span data-ttu-id="4b012-109">Необязательные конфигурации на уровне сайта, определяющие реализации архивации для определенного сайта</span><span class="sxs-lookup"><span data-stu-id="4b012-109">Optional site-level configurations that specify how archiving is implemented for a specific site</span></span>
    
- <span data-ttu-id="4b012-110">Необязательные конфигурации уровня пула, определяющие реализации архивации для определенного пула</span><span class="sxs-lookup"><span data-stu-id="4b012-110">Optional pool-level configurations that specify how archiving is implemented for a specific pool</span></span>
    
<span data-ttu-id="4b012-111">Вам потребуется настроить параметры для следующих параметров:</span><span class="sxs-lookup"><span data-stu-id="4b012-111">You will need to configure options for the following:</span></span>
  
- <span data-ttu-id="4b012-112">Следует ли включить или отключить архивировать</span><span class="sxs-lookup"><span data-stu-id="4b012-112">Whether to enable or disable archiving</span></span>
    
- <span data-ttu-id="4b012-113">Следует ли архивировать сеансы im</span><span class="sxs-lookup"><span data-stu-id="4b012-113">Whether to archive IM sessions</span></span>
    
- <span data-ttu-id="4b012-114">Следует ли архивировать сеансы веб-conferencing</span><span class="sxs-lookup"><span data-stu-id="4b012-114">Whether to archive web conferencing sessions</span></span>
    
- <span data-ttu-id="4b012-115">Следует ли блокировать действия, когда архивная информация недоступна</span><span class="sxs-lookup"><span data-stu-id="4b012-115">Whether to block activity when archiving is not available</span></span>
    
- <span data-ttu-id="4b012-116">Следует ли использовать интеграцию с Exchange</span><span class="sxs-lookup"><span data-stu-id="4b012-116">Whether to use Exchange integration</span></span>
    
- <span data-ttu-id="4b012-117">Настройка и экспорт данных</span><span class="sxs-lookup"><span data-stu-id="4b012-117">How to set up purging and exporting of data</span></span>
    
> [!NOTE]
> <span data-ttu-id="4b012-118">Перед включением архива необходимо указать все соответствующие параметры.</span><span class="sxs-lookup"><span data-stu-id="4b012-118">You should specify all appropriate options before enabling archiving.</span></span> 
  
<span data-ttu-id="4b012-119">Подробные сведения о реализации конфигураций архивации, включая параметры, которые можно указать, и иерархию конфигураций архивации, см. в плане архивации в [Skype для бизнеса Server.](../../plan-your-deployment/archiving/archiving.md)</span><span class="sxs-lookup"><span data-stu-id="4b012-119">For details about how archiving configurations are implemented, including which options you can specify and the hierarchy of archiving configurations, see [Plan for archiving in Skype for Business Server](../../plan-your-deployment/archiving/archiving.md).</span></span> <span data-ttu-id="4b012-120">Подробные сведения об управлении конфигурациями после развертывания с помощью панели управления или с помощью Windows PowerShell см. в сведениях об управлении настройками архивации [в Skype для бизнеса Server.](../../manage/archiving/options.md)</span><span class="sxs-lookup"><span data-stu-id="4b012-120">For details about how to manage configurations after deployment by using the Control Panel or by using Windows PowerShell, see [Manage archiving options in Skype for Business Server](../../manage/archiving/options.md).</span></span>
  
## <a name="configure-global-level-archiving-options"></a><span data-ttu-id="4b012-121">Настройка параметров архива на глобальном уровне</span><span class="sxs-lookup"><span data-stu-id="4b012-121">Configure global level archiving options</span></span>

<span data-ttu-id="4b012-122">При добавлении архивации в топологию и публикации топологии Skype для бизнеса Server создает глобальную конфигурацию для архивации.</span><span class="sxs-lookup"><span data-stu-id="4b012-122">When you add archiving to your topology and publish the topology, Skype for Business Server creates a global configuration for archiving.</span></span> <span data-ttu-id="4b012-123">По умолчанию в глобальной конфигурации не включены параметры архивации.</span><span class="sxs-lookup"><span data-stu-id="4b012-123">By default, no archiving options are enabled in the global configuration.</span></span> <span data-ttu-id="4b012-124">Глобальная конфигурация задает параметры, включенные для всего развертывания, если не заданы параметры на уровне сайта или пула, которые переопределяют глобальную конфигурацию.</span><span class="sxs-lookup"><span data-stu-id="4b012-124">The global configuration controls which options are enabled for your entire deployment, unless you set up site or pool configurations, which override the global configuration.</span></span>
  
<span data-ttu-id="4b012-125">Чтобы настроить параметры архива на глобальном уровне:</span><span class="sxs-lookup"><span data-stu-id="4b012-125">To configure archiving options at the global level:</span></span>
  
1. <span data-ttu-id="4b012-126">Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsArchivingAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="4b012-126">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="4b012-127">Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="4b012-127">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="4b012-128">В левой панели навигации щелкните **"Мониторинг** и архивация" и выберите **"Конфигурация архивации".**</span><span class="sxs-lookup"><span data-stu-id="4b012-128">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Configuration**.</span></span>
    
4. <span data-ttu-id="4b012-129">На странице **Конфигурация архивации** последовательно щелкните **Глобальная**, **Изменить** и **Показать сведения**.</span><span class="sxs-lookup"><span data-stu-id="4b012-129">On the **Archiving Configuration** page, click **Global**, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="4b012-130">На странице **Изменение параметров архивации — глобальный уровень** выберите в раскрывающемся списке **Параметр архивации** один из следующих параметров:</span><span class="sxs-lookup"><span data-stu-id="4b012-130">In **Edit Archiving Setting - Global**, in the **Archiving setting** drop-down list, select one of the following archiving options:</span></span>
    
   - <span data-ttu-id="4b012-131">**Отключить архивацию**</span><span class="sxs-lookup"><span data-stu-id="4b012-131">**Disable archiving**</span></span>
    
   - <span data-ttu-id="4b012-132">**Архивировать сеансы обмена мгновенными сообщениями**</span><span class="sxs-lookup"><span data-stu-id="4b012-132">**Archive IM sessions**</span></span>
    
   - <span data-ttu-id="4b012-133">**Архивировать сеансы обмена мгновенными сообщениями и веб-конференций**</span><span class="sxs-lookup"><span data-stu-id="4b012-133">**Archive IM and web conferencing sessions**</span></span>
    
6. <span data-ttu-id="4b012-134">Кроме того, на странице **"Изменение параметров архива — глобальная"** сделайте следующее:</span><span class="sxs-lookup"><span data-stu-id="4b012-134">Also on the **Edit Archiving Setting - Global** page, do the following:</span></span>
    
   - <span data-ttu-id="4b012-135">Чтобы заблокировать действия, когда архивирование невозможно, установите флажок **Block instant messaging (IM) or web conferencing sessions if archiving fails** (Блокировать сеансы обмена мгновенными сообщениями или веб-конференций, если не удается выполнить архивирование).</span><span class="sxs-lookup"><span data-stu-id="4b012-135">To block activity when archiving is not available, select the **Block instant messaging (IM) or web conferencing sessions if archiving fails** check box.</span></span>
    
   - <span data-ttu-id="4b012-136">Чтобы использовать Microsoft Exchange Server для хранения данных архивации, нажмите кнопку **"Интеграция Microsoft Exchange".**</span><span class="sxs-lookup"><span data-stu-id="4b012-136">To use Microsoft Exchange Server to store archiving data, click the **Microsoft Exchange integration** check box.</span></span>
    
   - <span data-ttu-id="4b012-137">Чтобы включить удаление данных, установите флажок **Включить удаление архивных данных**, а затем выполните одно из следующих действий:</span><span class="sxs-lookup"><span data-stu-id="4b012-137">To enable data purging, select the **Enable purging of archiving data** check box, and then do one of the following:</span></span>
    
   - <span data-ttu-id="4b012-138">Чтобы задать удаление после определенного числа дней, щелкните **Удалять экспортированные архивные данные и сохраненные архивные данные максимум в течение (дней)**, а затем задайте число дней.</span><span class="sxs-lookup"><span data-stu-id="4b012-138">To specify purging after a specific number of days, click **Purge exported archiving data and stored archiving data after maximum duration (days)**, and then specify the number of days.</span></span>
    
   - <span data-ttu-id="4b012-139">Чтобы ограничить удаление только теми данными, которые были экспортированы, щелкните **Удалять только экспортированные архивные данные**.</span><span class="sxs-lookup"><span data-stu-id="4b012-139">To limit purging to archiving data that has been exported, click **Purge exported archiving data only**.</span></span>
    
7. <span data-ttu-id="4b012-140">Нажмите кнопку **Зафиксировать**.</span><span class="sxs-lookup"><span data-stu-id="4b012-140">Click **Commit**.</span></span>
    
## <a name="configure-site-level-archiving-options"></a><span data-ttu-id="4b012-141">Настройка параметров архива на уровне сайта</span><span class="sxs-lookup"><span data-stu-id="4b012-141">Configure site level archiving options</span></span>

<span data-ttu-id="4b012-142">Можно указать параметры архива для определенного сайта.</span><span class="sxs-lookup"><span data-stu-id="4b012-142">You can specify archiving options for a specific site.</span></span> <span data-ttu-id="4b012-143">Конфигурация сайта переопределяет глобальную конфигурацию, но только для сайта, указанного в конфигурации.</span><span class="sxs-lookup"><span data-stu-id="4b012-143">A site configuration overrides the global configuration, but only for the site specified in the site configuration.</span></span> 
  
1. <span data-ttu-id="4b012-144">Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsArchivingAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="4b012-144">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="4b012-145">Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="4b012-145">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="4b012-146">В левой панели навигации щелкните **"Мониторинг** и архивация" и выберите **"Конфигурация архивации".**</span><span class="sxs-lookup"><span data-stu-id="4b012-146">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Configuration**.</span></span>
    
4. <span data-ttu-id="4b012-147">На странице **Конфигурация архивации** щелкните **Создать** и затем выберите пункт **Конфигурация сайта**.</span><span class="sxs-lookup"><span data-stu-id="4b012-147">On the **Archiving Configuration** page, click **New**, and then click **Site Configuration**.</span></span>
    
5. <span data-ttu-id="4b012-148">В разделе **Выбор сайта** выберите сайт, для которого нужно настроить архивацию.</span><span class="sxs-lookup"><span data-stu-id="4b012-148">In **Select a Site**, select the site to be configured for archiving.</span></span>
    
6. <span data-ttu-id="4b012-149">На странице **Новый параметр архивации** в раскрывающемся списке **Параметр архивации** выполните одно из следующих действий.</span><span class="sxs-lookup"><span data-stu-id="4b012-149">In **New Archiving Setting**, in the **Archiving setting** drop-down list box, do one of the following:</span></span>
    
   - <span data-ttu-id="4b012-150">Чтобы включить архивацию только для сеансов обмена мгновенными сообщениями, выберите пункт **Архивировать сеансы обмена мгновенными сообщениями**.</span><span class="sxs-lookup"><span data-stu-id="4b012-150">To enable archiving only for instant messaging (IM) sessions, click **Archive IM sessions**.</span></span>
    
   - <span data-ttu-id="4b012-151">Чтобы включить архивацию как для сеансов обмена мгновенными сообщениями, так и для конференций, выберите пункт **Архивировать сеансы обмена мгновенными сообщениями и веб-конференций**.</span><span class="sxs-lookup"><span data-stu-id="4b012-151">To enable archiving for both IM sessions and conferences, click **Archive IM and web conferencing sessions**.</span></span>
    
   - <span data-ttu-id="4b012-152">Чтобы отключить архивацию для политики, щелкните **Отключить архивацию**.</span><span class="sxs-lookup"><span data-stu-id="4b012-152">To disable archiving for the policy, click **Disable archiving**.</span></span>
    
7. <span data-ttu-id="4b012-153">Также в разделе **Новый параметр архивирования** выполните следующее:</span><span class="sxs-lookup"><span data-stu-id="4b012-153">Also in **New Archiving Setting**, do the following:</span></span>
    
   - <span data-ttu-id="4b012-154">Чтобы заблокировать действия, когда архивирование невозможно, установите флажок **Block instant messaging (IM) or web conferencing sessions if archiving fails** (Блокировать сеансы обмена мгновенными сообщениями или веб-конференций, если не удается выполнить архивирование).</span><span class="sxs-lookup"><span data-stu-id="4b012-154">To block activity when archiving is not available, select the **Block instant messaging (IM) or web conferencing sessions if archiving fails** check box.</span></span>
    
   - <span data-ttu-id="4b012-155">Чтобы использовать Microsoft Exchange Server для хранения данных архивации, нажмите кнопку **"Интеграция Microsoft Exchange".**</span><span class="sxs-lookup"><span data-stu-id="4b012-155">To use Microsoft Exchange Server to store archiving data, click the **Microsoft Exchange integration** check box.</span></span>
    
   - <span data-ttu-id="4b012-156">Чтобы включить удаление данных, установите флажок **Включить удаление архивных данных**, а затем выполните одно из следующих действий:</span><span class="sxs-lookup"><span data-stu-id="4b012-156">To enable data purging, select the **Enable purging of archiving data** check box, and then do one of the following:</span></span>
    
   - <span data-ttu-id="4b012-157">Чтобы задать удаление после определенного числа дней, щелкните **Удалять экспортированные архивные данные и сохраненные архивные данные максимум в течение (дней)**, а затем задайте число дней.</span><span class="sxs-lookup"><span data-stu-id="4b012-157">To specify purging after a specific number of days, click **Purge exported archiving data and stored archiving data after maximum duration (days)**, and then specify the number of days.</span></span>
    
   - <span data-ttu-id="4b012-158">Чтобы ограничить удаление только теми данными, которые были экспортированы, щелкните **Удалять только экспортированные архивные данные**.</span><span class="sxs-lookup"><span data-stu-id="4b012-158">To limit purging to archiving data that has been exported, click **Purge exported archiving data only**.</span></span>
    
8. <span data-ttu-id="4b012-159">Нажмите кнопку **Зафиксировать**.</span><span class="sxs-lookup"><span data-stu-id="4b012-159">Click **Commit**.</span></span>
    
## <a name="configure-pool-level-archiving-options"></a><span data-ttu-id="4b012-160">Настройка параметров архива на уровне пула</span><span class="sxs-lookup"><span data-stu-id="4b012-160">Configure pool level archiving options</span></span>

<span data-ttu-id="4b012-161">Можно указать параметры архива для определенного пула.</span><span class="sxs-lookup"><span data-stu-id="4b012-161">You can specify archiving options for a specific pool.</span></span> <span data-ttu-id="4b012-162">Конфигурация пула переопределяет глобальную конфигурацию и конфигурацию на уровне сайта, но только для пула, указанного в конфигурации пула.</span><span class="sxs-lookup"><span data-stu-id="4b012-162">A pool configuration overrides the global configuration and site configuration, but only for the pool specified in the pool configuration.</span></span>
  
1. <span data-ttu-id="4b012-163">Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsArchivingAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="4b012-163">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="4b012-164">Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="4b012-164">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="4b012-165">В левой панели навигации щелкните **"Мониторинг** и архивация" и выберите **"Конфигурация архивации".**</span><span class="sxs-lookup"><span data-stu-id="4b012-165">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Configuration**.</span></span>
    
4. <span data-ttu-id="4b012-166">На странице **Конфигурация архивации** нажмите кнопку **Создать** и затем выберите **Конфигурация пула**.</span><span class="sxs-lookup"><span data-stu-id="4b012-166">On the **Archiving Configuration** page, click **New**, and then click **Pool Configuration**.</span></span>
    
5. <span data-ttu-id="4b012-167">В списке **Select a Service** (Выбор службы) выберите пул, для которого необходимо настроить архивацию.</span><span class="sxs-lookup"><span data-stu-id="4b012-167">In **Select a Service**, select the pool to be configured for archiving.</span></span>
    
6. <span data-ttu-id="4b012-168">На странице **New Archiving Setting** (Создание параметра архивации) выберите один из следующих параметров архивации в раскрывающемся списке **Archiving setting** (Параметр архивации):</span><span class="sxs-lookup"><span data-stu-id="4b012-168">In **New Archiving Setting**, in the **Archiving setting** drop-down list, select one of the following archiving options:</span></span>
    
   - <span data-ttu-id="4b012-169">**Disable archiving** (Отключить архивацию)</span><span class="sxs-lookup"><span data-stu-id="4b012-169">**Disable archiving**</span></span>
    
   - <span data-ttu-id="4b012-170">**Архивировать сеансы обмена мгновенными сообщениями**</span><span class="sxs-lookup"><span data-stu-id="4b012-170">**Archive IM sessions**</span></span>
    
   - <span data-ttu-id="4b012-171">**Архивировать сеансы мгновенных сообщений и веб-конференций**</span><span class="sxs-lookup"><span data-stu-id="4b012-171">**Archive IM and web conferencing sessions**</span></span>
    
7. <span data-ttu-id="4b012-172">Кроме того, на странице **New Archiving Setting** (Создание параметра архивации) выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="4b012-172">Also in **New Archiving Setting** page, do the following:</span></span>
    
   - <span data-ttu-id="4b012-173">Чтобы заблокировать коммуникации, когда архивация недоступна, установите флажок **При сбое архивации заблокировать обмен мгновенными сообщениями или сеансы веб-конференции**.</span><span class="sxs-lookup"><span data-stu-id="4b012-173">To block activity when archiving is not available, select the **Block instant messaging (IM) or web conferencing sessions if archiving fails** check box.</span></span>
    
   - <span data-ttu-id="4b012-174">Чтобы использовать Microsoft Exchange Server для хранения данных архивации, нажмите кнопку **"Интеграция Microsoft Exchange".**</span><span class="sxs-lookup"><span data-stu-id="4b012-174">To use Microsoft Exchange Server to store archiving data, click the **Microsoft Exchange integration** check box.</span></span>
    
   - <span data-ttu-id="4b012-175">Чтобы включить удаление данных, установите флажок **Включить удаление архивных данных**, а затем выполните одно из следующих действий:</span><span class="sxs-lookup"><span data-stu-id="4b012-175">To enable data purging, select the **Enable purging of archiving data** check box, and then do one of the following:</span></span>
    
   - <span data-ttu-id="4b012-176">Чтобы задать удаление после определенного числа дней, щелкните **Удалять экспортированные архивные данные и сохраненные архивные данные максимум в течение (дней)**, а затем задайте число дней.</span><span class="sxs-lookup"><span data-stu-id="4b012-176">To specify purging after a specific number of days, click **Purge exported archiving data and stored archiving data after maximum duration (days)**, and then specify the number of days.</span></span>
    
   - <span data-ttu-id="4b012-177">Чтобы ограничить удаление только теми данными, которые были экспортированы, щелкните **Удалять только экспортированные архивные данные**.</span><span class="sxs-lookup"><span data-stu-id="4b012-177">To limit purging to archiving data that has been exported, click **Purge exported archiving data only**.</span></span>
    
8. <span data-ttu-id="4b012-178">Нажмите кнопку **Зафиксировать**.</span><span class="sxs-lookup"><span data-stu-id="4b012-178">Click **Commit**.</span></span>
    

