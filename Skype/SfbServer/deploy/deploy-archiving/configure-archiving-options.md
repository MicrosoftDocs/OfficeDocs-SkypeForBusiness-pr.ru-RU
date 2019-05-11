---
title: Настройка параметров архивации для Скайп для Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 2f534697-ac7f-45b7-8cdc-ba67f052223b
description: 'Сводка: Сведения в этой статье описывается настройка начальной параметров архивации для Скайп для Business Server. Изначально Настройка конфигураций архивации при развертывании архивации, но можно изменять, добавлять и удалять конфигурации после развертывания.'
ms.openlocfilehash: 58dd94cb5d42e3d0dabb845acbb5b72e7e90d8bd
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "33895927"
---
# <a name="configure-archiving-options-for-skype-for-business-server"></a><span data-ttu-id="66caa-104">Настройка параметров архивации для Скайп для Business Server</span><span class="sxs-lookup"><span data-stu-id="66caa-104">Configure archiving options for Skype for Business Server</span></span>
 
<span data-ttu-id="66caa-105">**Сводка:** Прочтите этот раздел, чтобы узнать, как Настройка начальной параметров архивации для Скайп для Business Server.</span><span class="sxs-lookup"><span data-stu-id="66caa-105">**Summary:** Read this topic to learn how to configure initial archiving options for Skype for Business Server.</span></span> <span data-ttu-id="66caa-106">Изначально Настройка конфигураций архивации при развертывании архивации, но можно изменять, добавлять и удалять конфигурации после развертывания.</span><span class="sxs-lookup"><span data-stu-id="66caa-106">You initially set up archiving configurations when you deploy archiving, but you can change, add, and delete configurations after deployment.</span></span>
  
<span data-ttu-id="66caa-107">Настройка начальной архивации конфигурации, используйте Скайп для панели управления Business Server для укажите следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="66caa-107">To configure initial archiving configurations, you use Skype for Business Server Control Panel to specify the following:</span></span>
  
- <span data-ttu-id="66caa-108">Настройки глобального уровня, которая создается по умолчанию при развертывании Скайп для Business Server</span><span class="sxs-lookup"><span data-stu-id="66caa-108">Global-level configuration that is created by default when you deploy Skype for Business Server</span></span>
    
- <span data-ttu-id="66caa-109">необязательные конфигурации уровня сайта, определяющие реализацию архивации на отдельных сайтах;</span><span class="sxs-lookup"><span data-stu-id="66caa-109">Optional site-level configurations that specify how archiving is implemented for a specific site</span></span>
    
- <span data-ttu-id="66caa-110">Дополнительные конфигурации на уровне пула, которые определяют, как архивация реализуется для конкретного пула</span><span class="sxs-lookup"><span data-stu-id="66caa-110">Optional pool-level configurations that specify how archiving is implemented for a specific pool</span></span>
    
<span data-ttu-id="66caa-111">При настройке конфигурации необходимо ответить на следующие вопросы:</span><span class="sxs-lookup"><span data-stu-id="66caa-111">You will need to configure options for the following:</span></span>
  
- <span data-ttu-id="66caa-112">включить или отключить архивацию;</span><span class="sxs-lookup"><span data-stu-id="66caa-112">Whether to enable or disable archiving</span></span>
    
- <span data-ttu-id="66caa-113">архивировать ли сеансы обмена мгновенными сообщениями;</span><span class="sxs-lookup"><span data-stu-id="66caa-113">Whether to archive IM sessions</span></span>
    
- <span data-ttu-id="66caa-114">архивировать ли сеансы веб-конференций;</span><span class="sxs-lookup"><span data-stu-id="66caa-114">Whether to archive web conferencing sessions</span></span>
    
- <span data-ttu-id="66caa-115">блокировать ли действия при невозможности архивации;</span><span class="sxs-lookup"><span data-stu-id="66caa-115">Whether to block activity when archiving is not available</span></span>
    
- <span data-ttu-id="66caa-116">пользоваться ли взаимодействием с Exchange;</span><span class="sxs-lookup"><span data-stu-id="66caa-116">Whether to use Exchange integration</span></span>
    
- <span data-ttu-id="66caa-117">как настроить удаление и экспорт данных.</span><span class="sxs-lookup"><span data-stu-id="66caa-117">How to set up purging and exporting of data</span></span>
    
> [!NOTE]
> <span data-ttu-id="66caa-118">Все необходимые параметры следует задать до включения архивации.</span><span class="sxs-lookup"><span data-stu-id="66caa-118">You should specify all appropriate options before enabling archiving.</span></span> 
  
<span data-ttu-id="66caa-119">Для получения дополнительных сведений о том, как реализован конфигураций архивации, в том числе которых можно указать параметры и иерархии архивации конфигурации, ознакомьтесь со статьей [Plan для архивации в Скайп для Business Server](../../plan-your-deployment/archiving/archiving.md).</span><span class="sxs-lookup"><span data-stu-id="66caa-119">For details about how archiving configurations are implemented, including which options you can specify and the hierarchy of archiving configurations, see [Plan for archiving in Skype for Business Server](../../plan-your-deployment/archiving/archiving.md).</span></span> <span data-ttu-id="66caa-120">Для получения дополнительных сведений об управлении конфигураций после развертывания с помощью панели управления или с помощью Windows PowerShell обнаружить [Управление архивации в Скайп для Business Server](../../manage/archiving/options.md).</span><span class="sxs-lookup"><span data-stu-id="66caa-120">For details about how to manage configurations after deployment by using the Control Panel or by using Windows PowerShell, see [Manage archiving options in Skype for Business Server](../../manage/archiving/options.md).</span></span>
  
## <a name="configure-global-level-archiving-options"></a><span data-ttu-id="66caa-121">Настройка параметров архивации на глобальном уровне</span><span class="sxs-lookup"><span data-stu-id="66caa-121">Configure global level archiving options</span></span>

<span data-ttu-id="66caa-122">При добавлении архивации в топологию и опубликовать эту топологию, Скайп для Business Server создается Глобальная конфигурация архивации.</span><span class="sxs-lookup"><span data-stu-id="66caa-122">When you add archiving to your topology and publish the topology, Skype for Business Server creates a global configuration for archiving.</span></span> <span data-ttu-id="66caa-123">По умолчанию в глобальной конфигурации все параметры архивации отключены.</span><span class="sxs-lookup"><span data-stu-id="66caa-123">By default, no archiving options are enabled in the global configuration.</span></span> <span data-ttu-id="66caa-124">Глобальная конфигурация определяет параметры, включенные для развертывания в целом, если не заданы конфигурации на уровне сайта или пула, переопределяющие глобальную конфигурацию.</span><span class="sxs-lookup"><span data-stu-id="66caa-124">The global configuration controls which options are enabled for your entire deployment, unless you set up site or pool configurations, which override the global configuration.</span></span>
  
<span data-ttu-id="66caa-125">Для настройки параметров архивации на глобальном уровне выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="66caa-125">To configure archiving options at the global level:</span></span>
  
1. <span data-ttu-id="66caa-126">Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsArchivingAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="66caa-126">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="66caa-127">Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть Скайп для панели управления Business Server.</span><span class="sxs-lookup"><span data-stu-id="66caa-127">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="66caa-128">На левой панели навигации щелкните **Мониторинг и архивация**, а затем щелкните **Конфигурация архивации**.</span><span class="sxs-lookup"><span data-stu-id="66caa-128">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Configuration**.</span></span>
    
4. <span data-ttu-id="66caa-129">На странице **Конфигурация архивации** щелкните **Глобальная** и **Изменить**, затем **Показать сведения**.</span><span class="sxs-lookup"><span data-stu-id="66caa-129">On the **Archiving Configuration** page, click **Global**, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="66caa-130">В разделе **Изменение настройки архивации — глобальная** выберите в раскрывающемся списке **Настройки архивации** один из следующих параметров архивации.</span><span class="sxs-lookup"><span data-stu-id="66caa-130">In **Edit Archiving Setting - Global**, in the **Archiving setting** drop-down list, select one of the following archiving options:</span></span>
    
   - <span data-ttu-id="66caa-131">**Отключить архивацию**</span><span class="sxs-lookup"><span data-stu-id="66caa-131">**Disable archiving**</span></span>
    
   - <span data-ttu-id="66caa-132">**Архивировать сеансы мгновенных сообщений**</span><span class="sxs-lookup"><span data-stu-id="66caa-132">**Archive IM sessions**</span></span>
    
   - <span data-ttu-id="66caa-133">**Архивировать сеансы мгновенных сообщений и веб-конференций**</span><span class="sxs-lookup"><span data-stu-id="66caa-133">**Archive IM and web conferencing sessions**</span></span>
    
6. <span data-ttu-id="66caa-134">На странице **Изменение параметров архивации — глобальный** выполните следующее:</span><span class="sxs-lookup"><span data-stu-id="66caa-134">Also on the **Edit Archiving Setting - Global** page, do the following:</span></span>
    
   - <span data-ttu-id="66caa-135">Для запрета действия при невозможности архивации установите флажок **При сбое архивации заблокировать обмен мгновенными сообщениями или сеансы веб-конференции**.</span><span class="sxs-lookup"><span data-stu-id="66caa-135">To block activity when archiving is not available, select the **Block instant messaging (IM) or web conferencing sessions if archiving fails** check box.</span></span>
    
   - <span data-ttu-id="66caa-136">Чтобы использовать Microsoft Exchange Server для хранения архивных данных, установите флажок **Интеграция с Microsoft Exchange** .</span><span class="sxs-lookup"><span data-stu-id="66caa-136">To use Microsoft Exchange Server to store archiving data, click the **Microsoft Exchange integration** check box.</span></span>
    
   - <span data-ttu-id="66caa-137">Для включения функции удаления данных установите флажок **Разрешить удаление данных архивации**, затем выполните одно из следующих действий.</span><span class="sxs-lookup"><span data-stu-id="66caa-137">To enable data purging, select the **Enable purging of archiving data** check box, and then do one of the following:</span></span>
    
   - <span data-ttu-id="66caa-138">Для настройки удаления записей по истечении заданного срока (в днях) щелкните **Очищать экспортированные данные архивации, а также данные архивации по окончании максимального срока хранения (дн.)**, затем укажите количество дней.</span><span class="sxs-lookup"><span data-stu-id="66caa-138">To specify purging after a specific number of days, click **Purge exported archiving data and stored archiving data after maximum duration (days)**, and then specify the number of days.</span></span>
    
   - <span data-ttu-id="66caa-139">Для удаления только экспортированных данных выберите **Удалять только экспортированные данные архивации**.</span><span class="sxs-lookup"><span data-stu-id="66caa-139">To limit purging to archiving data that has been exported, click **Purge exported archiving data only**.</span></span>
    
7. <span data-ttu-id="66caa-140">Нажмите **Исполнить**.</span><span class="sxs-lookup"><span data-stu-id="66caa-140">Click **Commit**.</span></span>
    
## <a name="configure-site-level-archiving-options"></a><span data-ttu-id="66caa-141">Настройка параметров архивации на уровне сайта</span><span class="sxs-lookup"><span data-stu-id="66caa-141">Configure site level archiving options</span></span>

<span data-ttu-id="66caa-142">Параметры архивации можно задать для отдельного сайта.</span><span class="sxs-lookup"><span data-stu-id="66caa-142">You can specify archiving options for a specific site.</span></span> <span data-ttu-id="66caa-143">Конфигурация сайта переопределяет глобальную конфигурацию, но только для сайта, указанного в конфигурации сайта.</span><span class="sxs-lookup"><span data-stu-id="66caa-143">A site configuration overrides the global configuration, but only for the site specified in the site configuration.</span></span> 
  
1. <span data-ttu-id="66caa-144">Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsArchivingAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="66caa-144">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="66caa-145">Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть Скайп для панели управления Business Server.</span><span class="sxs-lookup"><span data-stu-id="66caa-145">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="66caa-146">На левой панели навигации щелкните **Мониторинг и архивация**, а затем щелкните **Конфигурация архивации**.</span><span class="sxs-lookup"><span data-stu-id="66caa-146">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Configuration**.</span></span>
    
4. <span data-ttu-id="66caa-147">На странице **Конфигурация архивации** нажмите кнопку **Создать**, затем выберите **Конфигурация сайта**.</span><span class="sxs-lookup"><span data-stu-id="66caa-147">On the **Archiving Configuration** page, click **New**, and then click **Site Configuration**.</span></span>
    
5. <span data-ttu-id="66caa-148">В разделе **Выбор службы** выберите сайт для настройки архивации.</span><span class="sxs-lookup"><span data-stu-id="66caa-148">In **Select a Site**, select the site to be configured for archiving.</span></span>
    
6. <span data-ttu-id="66caa-149">В разделе **Создание новой настройки архивации** выберите в раскрывающемся списке **Настройки архивации** один из следующих вариантов.</span><span class="sxs-lookup"><span data-stu-id="66caa-149">In **New Archiving Setting**, in the **Archiving setting** drop-down list box, do one of the following:</span></span>
    
   - <span data-ttu-id="66caa-150">Если требуется разрешить архивацию только для сеансов обмена мгновенными сообщениями, щелкните **Архивировать сеансы мгновенных сообщений**.</span><span class="sxs-lookup"><span data-stu-id="66caa-150">To enable archiving only for instant messaging (IM) sessions, click **Archive IM sessions**.</span></span>
    
   - <span data-ttu-id="66caa-151">Если требуется разрешить архивацию как для сеансов обмена мгновенными сообщениями, как и для конференц-связи, щелкните **Архивировать сеансы мгновенных сообщений и веб-конференций**.</span><span class="sxs-lookup"><span data-stu-id="66caa-151">To enable archiving for both IM sessions and conferences, click **Archive IM and web conferencing sessions**.</span></span>
    
   - <span data-ttu-id="66caa-152">Если требуется запретить архивацию для данной политики, щелкните **Отключить архивацию**.</span><span class="sxs-lookup"><span data-stu-id="66caa-152">To disable archiving for the policy, click **Disable archiving**.</span></span>
    
7. <span data-ttu-id="66caa-153">На странице **Создание новой настройки архивации** можно также выполнить следующие действия.</span><span class="sxs-lookup"><span data-stu-id="66caa-153">Also in **New Archiving Setting**, do the following:</span></span>
    
   - <span data-ttu-id="66caa-154">Чтобы заблокировать действия, когда архивирование невозможно, установите флажок **При сбое архивации заблокировать обмен мгновенными сообщениями или сеансы веб-конференции**.</span><span class="sxs-lookup"><span data-stu-id="66caa-154">To block activity when archiving is not available, select the **Block instant messaging (IM) or web conferencing sessions if archiving fails** check box.</span></span>
    
   - <span data-ttu-id="66caa-155">Чтобы использовать Microsoft Exchange Server для хранения архивных данных, установите флажок **Интеграция с Microsoft Exchange** .</span><span class="sxs-lookup"><span data-stu-id="66caa-155">To use Microsoft Exchange Server to store archiving data, click the **Microsoft Exchange integration** check box.</span></span>
    
   - <span data-ttu-id="66caa-156">Для включения функции удаления данных установите флажок **Разрешить удаление данных архивации**, затем выполните одно из следующих действий.</span><span class="sxs-lookup"><span data-stu-id="66caa-156">To enable data purging, select the **Enable purging of archiving data** check box, and then do one of the following:</span></span>
    
   - <span data-ttu-id="66caa-157">Для настройки удаления записей по истечении заданного срока (в днях) щелкните **Очищать экспортированные данные архивации, а также данные архивации по окончании максимального срока хранения (дн.)**, затем укажите количество дней.</span><span class="sxs-lookup"><span data-stu-id="66caa-157">To specify purging after a specific number of days, click **Purge exported archiving data and stored archiving data after maximum duration (days)**, and then specify the number of days.</span></span>
    
   - <span data-ttu-id="66caa-158">Для удаления только экспортированных данных выберите **Удалять только экспортированные данные архивации**.</span><span class="sxs-lookup"><span data-stu-id="66caa-158">To limit purging to archiving data that has been exported, click **Purge exported archiving data only**.</span></span>
    
8. <span data-ttu-id="66caa-159">Щелкните **Исполнить**.</span><span class="sxs-lookup"><span data-stu-id="66caa-159">Click **Commit**.</span></span>
    
## <a name="configure-pool-level-archiving-options"></a><span data-ttu-id="66caa-160">Настройка параметров архивации на уровне пула</span><span class="sxs-lookup"><span data-stu-id="66caa-160">Configure pool level archiving options</span></span>

<span data-ttu-id="66caa-p106">Параметры архивации можно задать для отдельного пула. Конфигурация пула переопределяет глобальную конфигурацию и конфигурацию на уровне сайта, но только для пула, указанного в конфигурации пула.</span><span class="sxs-lookup"><span data-stu-id="66caa-p106">You can specify archiving options for a specific pool. A pool configuration overrides the global configuration and site configuration, but only for the pool specified in the pool configuration.</span></span>
  
1. <span data-ttu-id="66caa-163">Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsArchivingAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="66caa-163">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="66caa-164">Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть Скайп для панели управления Business Server.</span><span class="sxs-lookup"><span data-stu-id="66caa-164">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="66caa-165">На левой панели навигации щелкните **Мониторинг и архивация**, а затем щелкните **Конфигурация архивации**.</span><span class="sxs-lookup"><span data-stu-id="66caa-165">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Configuration**.</span></span>
    
4. <span data-ttu-id="66caa-166">На странице **Конфигурация архивации** нажмите кнопку **Создать**, затем выберите **Конфигурация пула**.</span><span class="sxs-lookup"><span data-stu-id="66caa-166">On the **Archiving Configuration** page, click **New**, and then click **Pool Configuration**.</span></span>
    
5. <span data-ttu-id="66caa-167">В разделе **Выбор службы** выберите пул для настройки архивации.</span><span class="sxs-lookup"><span data-stu-id="66caa-167">In **Select a Service**, select the pool to be configured for archiving.</span></span>
    
6. <span data-ttu-id="66caa-168">В разделе **Создание новой настройки архивации** выберите в раскрывающемся списке **Настройки архивации** один из следующих параметров архивации.</span><span class="sxs-lookup"><span data-stu-id="66caa-168">In **New Archiving Setting**, in the **Archiving setting** drop-down list, select one of the following archiving options:</span></span>
    
   - <span data-ttu-id="66caa-169">**Отключить архивацию**</span><span class="sxs-lookup"><span data-stu-id="66caa-169">**Disable archiving**</span></span>
    
   - <span data-ttu-id="66caa-170">**Архивировать сеансы мгновенных сообщений**</span><span class="sxs-lookup"><span data-stu-id="66caa-170">**Archive IM sessions**</span></span>
    
   - <span data-ttu-id="66caa-171">**Архивировать сеансы мгновенных сообщений и веб-конференций**</span><span class="sxs-lookup"><span data-stu-id="66caa-171">**Archive IM and web conferencing sessions**</span></span>
    
7. <span data-ttu-id="66caa-172">На странице **Создание новой настройки архивации** можно также выполнить следующие действия.</span><span class="sxs-lookup"><span data-stu-id="66caa-172">Also in **New Archiving Setting** page, do the following:</span></span>
    
   - <span data-ttu-id="66caa-173">Для запрета действия при невозможности архивации установите флажок **При сбое архивации заблокировать обмен мгновенными сообщениями или сеансы веб-конференции**.</span><span class="sxs-lookup"><span data-stu-id="66caa-173">To block activity when archiving is not available, select the **Block instant messaging (IM) or web conferencing sessions if archiving fails** check box.</span></span>
    
   - <span data-ttu-id="66caa-174">Чтобы использовать Microsoft Exchange Server для хранения архивных данных, установите флажок **Интеграция с Microsoft Exchange** .</span><span class="sxs-lookup"><span data-stu-id="66caa-174">To use Microsoft Exchange Server to store archiving data, click the **Microsoft Exchange integration** check box.</span></span>
    
   - <span data-ttu-id="66caa-175">Для включения функции удаления данных установите флажок **Разрешить удаление данных архивации**, затем выполните одно из следующих действий.</span><span class="sxs-lookup"><span data-stu-id="66caa-175">To enable data purging, select the **Enable purging of archiving data** check box, and then do one of the following:</span></span>
    
   - <span data-ttu-id="66caa-176">Для настройки удаления записей по истечении заданного срока (в днях) щелкните **Очищать экспортированные данные архивации, а также данные архивации по окончании максимального срока хранения (дн.)**, затем укажите количество дней.</span><span class="sxs-lookup"><span data-stu-id="66caa-176">To specify purging after a specific number of days, click **Purge exported archiving data and stored archiving data after maximum duration (days)**, and then specify the number of days.</span></span>
    
   - <span data-ttu-id="66caa-177">Для удаления только экспортированных данных выберите **Удалять только экспортированные данные архивации**.</span><span class="sxs-lookup"><span data-stu-id="66caa-177">To limit purging to archiving data that has been exported, click **Purge exported archiving data only**.</span></span>
    
8. <span data-ttu-id="66caa-178">Нажмите **Исполнить**.</span><span class="sxs-lookup"><span data-stu-id="66caa-178">Click **Commit**.</span></span>
    

