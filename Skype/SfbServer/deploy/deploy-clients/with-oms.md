---
title: Развертывание управления системами комнат Skype версии 2 с помощью OMS
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/20/2017
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.custom: Strat_SB_Admin
ms.assetid: d86ff657-ee92-4b06-aee3-d4c43090bdcb
description: Эта статья посвящена процедуре для развертывания управления устройствами v2 систем комнаты Скайп интегрированная, начала до конца способом, с помощью Microsoft Operations Management Suite.
ms.openlocfilehash: 0d0490d92a5513dad38a9ff6348a957204274878
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/28/2018
---
# <a name="deploy-skype-room-systems-v2-management-with-oms"></a><span data-ttu-id="98cc9-103">Развертывание управления системами комнат Skype версии 2 с помощью OMS</span><span class="sxs-lookup"><span data-stu-id="98cc9-103">Deploy Skype Room Systems v2 management with OMS</span></span>
 
<span data-ttu-id="98cc9-104">Эта статья посвящена процедуре для развертывания управления устройствами v2 систем комнаты Скайп интегрированная, начала до конца способом, с помощью Microsoft Operations Management Suite.</span><span class="sxs-lookup"><span data-stu-id="98cc9-104">This article discusses how to deploy management of Skype Room Systems v2 devices in an integrated, end-to-end manner using Microsoft Operations Management Suite.</span></span> 
  
<span data-ttu-id="98cc9-p101">Microsoft Operations Management Suite (OMS) можно настроить для предоставления базовых данных телеметрии, которые помогут управлять устройствами для конференц-залов Skype. По мере повышения эффективности решения для управления можно приобрести дополнительные данные и возможности управления для создания более подробного представления о производительности устройств.</span><span class="sxs-lookup"><span data-stu-id="98cc9-p101">You can configure Microsoft Operations Management Suite (OMS) to provide basic telemetry that will help you manage Skype meeting room devices. As your management solution matures, you can purchase additional data and management capabilities to create a more detailed view of device performance.</span></span>
  
<span data-ttu-id="98cc9-107">В общих чертах вам необходимо выполнить следующие задачи.</span><span class="sxs-lookup"><span data-stu-id="98cc9-107">At a high level, you need to perform the following tasks:</span></span>
  
1. [<span data-ttu-id="98cc9-108">Настройка устройств для управления с помощью OMS </span><span class="sxs-lookup"><span data-stu-id="98cc9-108">Configure devices for OMS Management </span></span>](with-oms.md#config_devices)
    
2. [<span data-ttu-id="98cc9-109">Сопоставление настраиваемых полей</span><span class="sxs-lookup"><span data-stu-id="98cc9-109">Map custom fields</span></span>](with-oms.md#Custom_fields)
    
3. [<span data-ttu-id="98cc9-110">Определение представлений SRS версии 2 в OMS</span><span class="sxs-lookup"><span data-stu-id="98cc9-110">Define the SRS v2 views in OMS</span></span>](with-oms.md#Views)
    
## <a name="find-and-record-device-locations-capabilities-and-configurations"></a><span data-ttu-id="98cc9-111">Поиск и запись расположений, возможностей и конфигураций устройств</span><span class="sxs-lookup"><span data-stu-id="98cc9-111">Find and record device locations, capabilities, and configurations</span></span>
<span data-ttu-id="98cc9-112"><a name="find_devices"> </a></span><span class="sxs-lookup"><span data-stu-id="98cc9-112"></span></span>

<span data-ttu-id="98cc9-p102">Первым шагом является создание подробной базы данных всего оборудования в системе с указанием сведений о его возможностях, конфигурациях и расположении. Для выполнения этой задачи в малых и средних организациях может быть достаточно сформировать электронную таблицу. В более крупной организации, возможно, потребуется рассмотреть использование средств управления активами и сторонних служб. Важно записать расположение каждого устройства и все относящиеся к нему сведения.</span><span class="sxs-lookup"><span data-stu-id="98cc9-p102">The first step is to create a detailed database of all of the equipment in the system, the details of its capabilities and configuration, and its location. A spreadsheet may be adequate for this task in small to medium organizations. If you work at a larger organization, you may need to consider asset management tools and third-party services. What is important is that you record the location and all the relevant details of every device.</span></span>
  
<span data-ttu-id="98cc9-117">После выполнения этой задачи вы можете использовать эту информацию для отправки технических специалистов на место, а также для управления исправлениями и обновлениями устройств.</span><span class="sxs-lookup"><span data-stu-id="98cc9-117">Once that work is done, you can use this information to dispatch technicians and manage device patches and upgrades.</span></span>
  
## <a name="configure-devices-for-oms-management"></a><span data-ttu-id="98cc9-118">Настройка устройств для управления с помощью OMS </span><span class="sxs-lookup"><span data-stu-id="98cc9-118">Configure devices for OMS Management</span></span>
<span data-ttu-id="98cc9-119"><a name="config_devices"> </a></span><span class="sxs-lookup"><span data-stu-id="98cc9-119"></span></span>

<span data-ttu-id="98cc9-120">Для каждого устройства SRS следуйте инструкциям на компьютерах [Windows подключиться к службе анализа журнала в Azure](https://docs.microsoft.com/en-us/azure/log-analytics/log-analytics-windows-agents).</span><span class="sxs-lookup"><span data-stu-id="98cc9-120">For each SRS device, follow the instructions found in [Connect Windows computers to the Log Analytics service in Azure](https://docs.microsoft.com/en-us/azure/log-analytics/log-analytics-windows-agents).</span></span>
  
## <a name="configure-oms-to-collect-device-event-logs"></a><span data-ttu-id="98cc9-121">Настройка OMS для сбора журналов событий устройств</span><span class="sxs-lookup"><span data-stu-id="98cc9-121">Configure OMS to collect device event logs</span></span>
<span data-ttu-id="98cc9-122"><a name="config_devices"> </a></span><span class="sxs-lookup"><span data-stu-id="98cc9-122"></span></span>

<span data-ttu-id="98cc9-123">Необходимо будет специально настроить OMS собирать журналы событий с помощью SRS устройств с помощью действия, описанные в [Источники данных журнала событий Windows в аналитике журнала](https://docs.microsoft.com/en-us/azure/log-analytics/log-analytics-data-sources-windows-events).</span><span class="sxs-lookup"><span data-stu-id="98cc9-123">You will need to specifically configure OMS to collect event logs from SRS devices using the steps at [Windows event log data sources in Log Analytics](https://docs.microsoft.com/en-us/azure/log-analytics/log-analytics-data-sources-windows-events).</span></span> <span data-ttu-id="98cc9-124">В журнал событий SRS для выбора — «Система комнаты Скайп» и должен установите флажки параметр для всех типов: ошибки, предупреждения и информации.</span><span class="sxs-lookup"><span data-stu-id="98cc9-124">The SRS event log to select is "Skype Room System" and you should check the option boxes for all types: Error, Warning and Information.</span></span>
  
## <a name="map-custom-fields"></a><span data-ttu-id="98cc9-125">Сопоставление настраиваемых полей</span><span class="sxs-lookup"><span data-stu-id="98cc9-125">Map custom fields</span></span>
<span data-ttu-id="98cc9-126"><a name="Custom_fields"> </a></span><span class="sxs-lookup"><span data-stu-id="98cc9-126"></span></span>

<span data-ttu-id="98cc9-127">Прежде чем можно будет использовать заголовков, созданные в [версии 2 SRS определение представления в OMS](with-oms.md#Views) , вам потребуется создать настраиваемые поля для представления.</span><span class="sxs-lookup"><span data-stu-id="98cc9-127">Before the tiles created in the [Define the SRS v2 views in OMS](with-oms.md#Views) can be used, you'll need to create custom fields for your view.</span></span> <span data-ttu-id="98cc9-128">Просмотрите [настраиваемых полей в аналитике журнала](https://docs.microsoft.com/en-us/azure/log-analytics/log-analytics-custom-fields) для получения дополнительных сведений о создании настраиваемых полей.</span><span class="sxs-lookup"><span data-stu-id="98cc9-128">see [Custom fields in Log Analytics](https://docs.microsoft.com/en-us/azure/log-analytics/log-analytics-custom-fields) for details on creating custom fields.</span></span>
  
<span data-ttu-id="98cc9-129">Использование сопоставления, показанного ниже, OMS автоматическое добавление _CF при определении нового поля.</span><span class="sxs-lookup"><span data-stu-id="98cc9-129">Use the mappings shown below, OMS will automatically add the _CF when defining the new field.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="98cc9-130">Обратите внимание, что во всех полях JSON и OMS учитывается регистр символов.</span><span class="sxs-lookup"><span data-stu-id="98cc9-130">Remember that all JSON and OMS fields are case sensitive.</span></span> 
  
<span data-ttu-id="98cc9-131">**Сопоставление настраиваемого поля**</span><span class="sxs-lookup"><span data-stu-id="98cc9-131">**Custom fields mapping**</span></span>

|<span data-ttu-id="98cc9-132">**Поле JSON**</span><span class="sxs-lookup"><span data-stu-id="98cc9-132">**JSON field**</span></span>|<span data-ttu-id="98cc9-133">**Настраиваемое поле OMS**</span><span class="sxs-lookup"><span data-stu-id="98cc9-133">**OMS custom field**</span></span>|
|:-----|:-----|
|<span data-ttu-id="98cc9-134">Описание</span><span class="sxs-lookup"><span data-stu-id="98cc9-134">Description</span></span>  <br/> |<span data-ttu-id="98cc9-135">SRSEventDescription_CF</span><span class="sxs-lookup"><span data-stu-id="98cc9-135">SRSEventDescription_CF</span></span>  <br/> |
|<span data-ttu-id="98cc9-136">ResourceState</span><span class="sxs-lookup"><span data-stu-id="98cc9-136">ResourceState</span></span>  <br/> |<span data-ttu-id="98cc9-137">SRSResourceState_CF</span><span class="sxs-lookup"><span data-stu-id="98cc9-137">SRSResourceState_CF</span></span>  <br/> |
|<span data-ttu-id="98cc9-138">Имя_операции</span><span class="sxs-lookup"><span data-stu-id="98cc9-138">OperationName</span></span>  <br/> |<span data-ttu-id="98cc9-139">SRSOperationName_CF</span><span class="sxs-lookup"><span data-stu-id="98cc9-139">SRSOperationName_CF</span></span>  <br/> |
|<span data-ttu-id="98cc9-140">OperationResult</span><span class="sxs-lookup"><span data-stu-id="98cc9-140">OperationResult</span></span>  <br/> |<span data-ttu-id="98cc9-141">SRSOperationResult_CF</span><span class="sxs-lookup"><span data-stu-id="98cc9-141">SRSOperationResult_CF</span></span>  <br/> |
|<span data-ttu-id="98cc9-142">OS</span><span class="sxs-lookup"><span data-stu-id="98cc9-142">OS</span></span>  <br/> |<span data-ttu-id="98cc9-143">SRSOSVersion_CF</span><span class="sxs-lookup"><span data-stu-id="98cc9-143">SRSOSVersion_CF</span></span>  <br/> |
|<span data-ttu-id="98cc9-144">OSVersion</span><span class="sxs-lookup"><span data-stu-id="98cc9-144">OSVersion</span></span>  <br/> |<span data-ttu-id="98cc9-145">SRSOSLongVersion_CF</span><span class="sxs-lookup"><span data-stu-id="98cc9-145">SRSOSLongVersion_CF</span></span>  <br/> |
|<span data-ttu-id="98cc9-146">Alias</span><span class="sxs-lookup"><span data-stu-id="98cc9-146">Alias</span></span>  <br/> |<span data-ttu-id="98cc9-147">SRSAlias_CF</span><span class="sxs-lookup"><span data-stu-id="98cc9-147">SRSAlias_CF</span></span>  <br/> |
|<span data-ttu-id="98cc9-148">Отображаемое имя</span><span class="sxs-lookup"><span data-stu-id="98cc9-148">DisplayName</span></span>  <br/> |<span data-ttu-id="98cc9-149">SRSDisplayName_CF</span><span class="sxs-lookup"><span data-stu-id="98cc9-149">SRSDisplayName_CF</span></span>  <br/> |
|<span data-ttu-id="98cc9-150">AppVersion</span><span class="sxs-lookup"><span data-stu-id="98cc9-150">AppVersion</span></span>  <br/> |<span data-ttu-id="98cc9-151">SRSAppVersion_CF</span><span class="sxs-lookup"><span data-stu-id="98cc9-151">SRSAppVersion_CF</span></span>  <br/> |
|<span data-ttu-id="98cc9-152">IPv4-адрес</span><span class="sxs-lookup"><span data-stu-id="98cc9-152">IPv4Address</span></span>  <br/> |<span data-ttu-id="98cc9-153">SRSIPv4Address_CF</span><span class="sxs-lookup"><span data-stu-id="98cc9-153">SRSIPv4Address_CF</span></span>  <br/> |
|<span data-ttu-id="98cc9-154">IPv6-адрес</span><span class="sxs-lookup"><span data-stu-id="98cc9-154">IPv6Address</span></span>  <br/> |<span data-ttu-id="98cc9-155">SRSIPv6Address_CF</span><span class="sxs-lookup"><span data-stu-id="98cc9-155">SRSIPv6Address_CF</span></span>  <br/> |
   
## <a name="define-the-srs-v2-views-in-oms"></a><span data-ttu-id="98cc9-156">Определение представлений SRS версии 2 в OMS</span><span class="sxs-lookup"><span data-stu-id="98cc9-156">Define the SRS v2 views in OMS</span></span>
<span data-ttu-id="98cc9-157"><a name="Views"> </a></span><span class="sxs-lookup"><span data-stu-id="98cc9-157"></span></span>

<span data-ttu-id="98cc9-158">После сбора данных и сопоставления настраиваемых полей можно использовать конструктор представлений OMS для разработки панели мониторинга с плитками для мониторинга событий SRS версии 2.</span><span class="sxs-lookup"><span data-stu-id="98cc9-158">Once data is collected and custom fields are mapped, you can use OMS View Designer to develop a Dashboard containing Tiles to monitor SRS v2 events.</span></span> <span data-ttu-id="98cc9-159">Используйте конструктор представлений для создания следующих плиток, обратитесь к [Открыть в конструкторе используется для создания настраиваемых представлений в аналитике журнала](https://docs.microsoft.com/en-us/azure/log-analytics/log-analytics-view-designer) при необходимости.</span><span class="sxs-lookup"><span data-stu-id="98cc9-159">Use View Designer to create the following tiles, refer to [Use View Designer to create custom views in Log Analytics](https://docs.microsoft.com/en-us/azure/log-analytics/log-analytics-view-designer) as necessary.</span></span>
  
### <a name="create-a-tile-that-shows-healthy-devices"></a><span data-ttu-id="98cc9-160">Создание плитки, отображающей работоспособные устройства</span><span class="sxs-lookup"><span data-stu-id="98cc9-160">Create a tile that shows healthy devices</span></span>

1. <span data-ttu-id="98cc9-161">Определите ситуацию использования. </span><span class="sxs-lookup"><span data-stu-id="98cc9-161">Define the case:</span></span> 
    
    <span data-ttu-id="98cc9-162">На этой плитке отображаются все устройства, отправившие сообщение периодического сигнала в течение последних 10 минут.</span><span class="sxs-lookup"><span data-stu-id="98cc9-162">This tile displays all devices that have sent a heartbeat message in the last 10 minutes.</span></span>
    
2. <span data-ttu-id="98cc9-163">Укажите заголовок группы. </span><span class="sxs-lookup"><span data-stu-id="98cc9-163">Assign Group Title</span></span> 
    
   ```
   SRS v2
   ```

3. <span data-ttu-id="98cc9-164">Установите флажок для новой группы.</span><span class="sxs-lookup"><span data-stu-id="98cc9-164">Check the new group box</span></span>
    
4. <span data-ttu-id="98cc9-165">Добавьте текст условных обозначений для плитки.</span><span class="sxs-lookup"><span data-stu-id="98cc9-165">Add the Tile legend text</span></span>
    
   ```
   All healthy devices (Heartbeat sent in last 10 minutes)
   ```

5. <span data-ttu-id="98cc9-166">Введите запрос для плитки.</span><span class="sxs-lookup"><span data-stu-id="98cc9-166">Enter the tile query</span></span>
    
   ```
   Type:Event EventLog:"Skype Room System" SRSOperationName_CF:"Heartbeat" TimeGenerated >NOW-10MINUTES|measure count() by SRSDisplayName_CF 
   ```

6. <span data-ttu-id="98cc9-167">Введите запрос для списка.</span><span class="sxs-lookup"><span data-stu-id="98cc9-167">Enter the list query</span></span>
    
   ```
   Type:Event EventLog:"Skype Room System" SRSOperationName_CF:"Heartbeat" |measure max(TimeGenerated) as LastHB by SRSDisplayName_CF |Where LastHB>NOW-10MINUTES
   ```

7. <span data-ttu-id="98cc9-168">Определите имя заголовков столбцов.</span><span class="sxs-lookup"><span data-stu-id="98cc9-168">Define column titles name</span></span>
    
   ```
   Display Name
   ```

8. <span data-ttu-id="98cc9-169">Определите значение заголовков столбцов.</span><span class="sxs-lookup"><span data-stu-id="98cc9-169">Define Column titles value</span></span>
    
   ```
   Last HB
   ```

9. <span data-ttu-id="98cc9-170">Введите запрос навигации.</span><span class="sxs-lookup"><span data-stu-id="98cc9-170">Enter Navigation query</span></span>
    
   ```
   {selected item} EventLog:"Skype Room System" SRSOperationName_CF:"Heartbeat"|Dedup SRSDisplayName_CF|Select TimeGenerated, Computer, SRSOperationName_CF, SRSOperationResult_CF,SRSEventDescription_CF, SRSAppVersion_CF, SRSDisplayName_CF, SRSAlias_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF
   ```

### <a name="create-the-tile-that-shows-devices-with-connectivity-issues"></a><span data-ttu-id="98cc9-171">Создание плитки, отображающей устройства с проблемами подключения</span><span class="sxs-lookup"><span data-stu-id="98cc9-171">Create the tile that shows devices with connectivity issues</span></span>

1. <span data-ttu-id="98cc9-172">Определите ситуацию использования. </span><span class="sxs-lookup"><span data-stu-id="98cc9-172">Define the case:</span></span> 
    
    <span data-ttu-id="98cc9-p106">На этой плитке отображаются все устройства, не отправившие сообщение периодического сигнала в течение последних 10 минут. Возможно, у этих устройств возникли проблемы с сетевым подключением, подключением к Exchange или подключением к Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="98cc9-p106">This tile displays all devices that have not sent a heartbeat message in the last 10 minutes. These devices may be experiencing issues with network connectivity, Exchange connectivity, or Skype for Business connectivity.</span></span>
    
2. <span data-ttu-id="98cc9-175">Укажите заголовок группы. </span><span class="sxs-lookup"><span data-stu-id="98cc9-175">Assign Group Title</span></span> 
    
   ```
   SRS v2
   ```

3. <span data-ttu-id="98cc9-176">Не устанавливайте флажок для новой группы.</span><span class="sxs-lookup"><span data-stu-id="98cc9-176">Do not check the new group box.</span></span> <span data-ttu-id="98cc9-177">Вы уже сделали это при создании плитки 1, поэтому выполнять это действие повторно не нужно.</span><span class="sxs-lookup"><span data-stu-id="98cc9-177">You already did this when creating tile 1, and don't need to do it again.</span></span>
    
4. <span data-ttu-id="98cc9-178">Добавьте текст условных обозначений для плитки.</span><span class="sxs-lookup"><span data-stu-id="98cc9-178">Add the Tile legend text</span></span>
    
   ```
   Devices no longer sending Heartbeat messages
   ```

5. <span data-ttu-id="98cc9-179">Введите запрос для плитки.</span><span class="sxs-lookup"><span data-stu-id="98cc9-179">Enter the tile query</span></span>
    
   ```
   Type:Event EventLog:"Skype Room System" SRSOperationName_CF:"Heartbeat" |measure max(TimeGenerated) as LastHB by Computer|Where LastHB<NOW-10MINUTES
   ```

6. <span data-ttu-id="98cc9-180">Введите запрос для списка.</span><span class="sxs-lookup"><span data-stu-id="98cc9-180">Enter the list query</span></span>
    
   ```
   Type:Event EventLog:"Skype Room System" SRSOperationName_CF:"Heartbeat" |measure max(TimeGenerated) as LastHB by Computer|Where LastHB<NOW-10MINUTES
   ```

7. <span data-ttu-id="98cc9-181">Определите имя заголовков столбцов.</span><span class="sxs-lookup"><span data-stu-id="98cc9-181">Define column titles name</span></span>
    
   ```
   Device Name
   ```

8. <span data-ttu-id="98cc9-182">Определите значение заголовков столбцов. </span><span class="sxs-lookup"><span data-stu-id="98cc9-182">Define Column titles Value</span></span> 
    
   ```
   Last HB
   ```

9. <span data-ttu-id="98cc9-183">Введите запрос навигации.</span><span class="sxs-lookup"><span data-stu-id="98cc9-183">Enter Navigation query</span></span>
    
   ```
   {selected item} EventLog:"Skype Room System" SRSOperationName_CF:"Heartbeat" |Dedup SRSDisplayName_CF|Select TimeGenerated, Computer, SRSDisplayName_CF, SRSAlias_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF
   ```

### <a name="list-devices-with-a-hardware-error"></a><span data-ttu-id="98cc9-184">Выведите список устройств с ошибкой оборудования. </span><span class="sxs-lookup"><span data-stu-id="98cc9-184">List devices with a hardware error</span></span>

1. <span data-ttu-id="98cc9-185">Определите ситуацию использования. </span><span class="sxs-lookup"><span data-stu-id="98cc9-185">Define the case:</span></span> 
    
   <span data-ttu-id="98cc9-186">В этом плитки отображаются все устройства, которые отправлены сообщение, указывающее один или несколько компонентов неполадки с оборудованием в течение последних 10 минут.</span><span class="sxs-lookup"><span data-stu-id="98cc9-186">This tile displays all devices that sent a message indicating a one or more hardware component issues in the last 10 minutes.</span></span> 
    
2. <span data-ttu-id="98cc9-187">Укажите заголовок группы. </span><span class="sxs-lookup"><span data-stu-id="98cc9-187">Assign Group Title</span></span> 
    
   ```
   SRS v2
   ```

3. <span data-ttu-id="98cc9-188">Не устанавливайте флажок для новой группы.</span><span class="sxs-lookup"><span data-stu-id="98cc9-188">Do not check the new group box.</span></span> <span data-ttu-id="98cc9-189">Вы уже сделали это при создании плитки 1, поэтому выполнять это действие повторно не нужно.</span><span class="sxs-lookup"><span data-stu-id="98cc9-189">You already did this when creating tile 1, and don't need to do it again.</span></span>
    
4. <span data-ttu-id="98cc9-190">Условные обозначения для плитки: </span><span class="sxs-lookup"><span data-stu-id="98cc9-190">Tile legend:</span></span> 
    
   ```
   Devices with a Hardware Error
   ```

5. <span data-ttu-id="98cc9-191">Запрос для плитки</span><span class="sxs-lookup"><span data-stu-id="98cc9-191">Tile Query</span></span>
    
   ```
   Type:Event EventLog:"Skype Room System" EventLevelName:Error EventID:3001 TimeGenerated>NOW-10MINUTES|measure count() by SRSDisplayName_CF
   ```

6. <span data-ttu-id="98cc9-192">Запрос для списка:</span><span class="sxs-lookup"><span data-stu-id="98cc9-192">List query:</span></span>
    
   ```
   Type:Event EventLog:"Skype Room System" EventLevelName:Error EventID:3001 TimeGenerated>NOW-10MINUTES|measure max(TimeGenerated) by SRSDisplayName_CF
   ```

7. <span data-ttu-id="98cc9-193">Имя заголовков столбцов: </span><span class="sxs-lookup"><span data-stu-id="98cc9-193">Column titles Name:</span></span> 
    
   ```
   Display Name
   ```

8. <span data-ttu-id="98cc9-194">Значение заголовков столбцов: </span><span class="sxs-lookup"><span data-stu-id="98cc9-194">Column titles Value:</span></span> 
    
   ```
   Last Error
   ```

9. <span data-ttu-id="98cc9-195">Запрос навигации: </span><span class="sxs-lookup"><span data-stu-id="98cc9-195">Navigation query:</span></span> 
    
   ```
   {selected item}  EventLevelName:Error EventID:3001|Dedup SRSDisplayName_CF|Select TimeGenerated, Computer, SRSOperationName_CF, SRSOperationResult_CF,SRSEventDescription_CF, SRSAppVersion_CF, SRSDisplayName_CF, SRSAlias_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF
   ```

### <a name="list-devices-with-an-app-error"></a><span data-ttu-id="98cc9-196">Выведите список устройств с ошибкой приложения. </span><span class="sxs-lookup"><span data-stu-id="98cc9-196">List devices with an App error</span></span>

1. <span data-ttu-id="98cc9-197">Определите ситуацию использования.</span><span class="sxs-lookup"><span data-stu-id="98cc9-197">Define the case:</span></span> 
    
   <span data-ttu-id="98cc9-198">На этой плитке отображаются все устройства SRS, сообщившие об одной или нескольких ошибках компонента приложения в течение последних 10 минут</span><span class="sxs-lookup"><span data-stu-id="98cc9-198">This tile displays all SRS devices that report 1 or more app component errors within the last 10 minutes</span></span>
    
2. <span data-ttu-id="98cc9-199">Укажите заголовок группы. </span><span class="sxs-lookup"><span data-stu-id="98cc9-199">Assign Group Title</span></span> 
    
   ```
   SRS v2
   ```

3. <span data-ttu-id="98cc9-200">Не устанавливайте флажок для новой группы.</span><span class="sxs-lookup"><span data-stu-id="98cc9-200">Do not check the new group box.</span></span> <span data-ttu-id="98cc9-201">Вы уже сделали это при создании плитки 1, поэтому выполнять это действие повторно не нужно.</span><span class="sxs-lookup"><span data-stu-id="98cc9-201">You already did this when creating tile 1, and don't need to do it again.</span></span>
    
4. <span data-ttu-id="98cc9-202">Условные обозначения для плитки: </span><span class="sxs-lookup"><span data-stu-id="98cc9-202">Tile legend:</span></span> 
   ``` 
    Device with App Errors (in prior 10 minutes)
   ``` 
5. <span data-ttu-id="98cc9-203">Запрос для плитки: </span><span class="sxs-lookup"><span data-stu-id="98cc9-203">Tile Query:</span></span> 
    
   ```
   Type:Event EventLog:"Skype Room System" EventLevelName:Error EventID:2001 TimeGenerated>NOW-10MINUTES|measure count() by Computer
   ```

6. <span data-ttu-id="98cc9-204">Запрос для списка: </span><span class="sxs-lookup"><span data-stu-id="98cc9-204">List query:</span></span> 
    
   ```
   Type:Event EventLog:"Skype Room System" EventLevelName:Error EventID:2001 TimeGenerated>NOW-10MINUTES|measure max(TimeGenerated) by Computer
   ```

7. <span data-ttu-id="98cc9-205">Имя заголовков столбцов: </span><span class="sxs-lookup"><span data-stu-id="98cc9-205">Column titles Name:</span></span> 
    
   ```
   Device Name
   ```

8. <span data-ttu-id="98cc9-206">Значение заголовков столбцов: </span><span class="sxs-lookup"><span data-stu-id="98cc9-206">Column titles Value:</span></span> 
    
   ```
   Last Error
   ```

9. <span data-ttu-id="98cc9-207">Запрос навигации:</span><span class="sxs-lookup"><span data-stu-id="98cc9-207">Navigation query:</span></span>
    
   ```
   {selected item} EventLevelName:Error|Dedup SRSDisplayName_CF|Select TimeGenerated, Computer, SRSOperationName_CF, SRSOperationResult_CF,SRSEventDescription_CF, SRSAppVersion_CF, SRSDisplayName_CF, SRSAlias_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF
   ```

### <a name="list-devices-requiring-a-restart"></a><span data-ttu-id="98cc9-208">Вывод списка устройств, требующих перезапуска</span><span class="sxs-lookup"><span data-stu-id="98cc9-208">List devices requiring a restart</span></span>

1. <span data-ttu-id="98cc9-209">Определите ситуацию использования. </span><span class="sxs-lookup"><span data-stu-id="98cc9-209">Define the case:</span></span> 
    
   <span data-ttu-id="98cc9-210">На этой плитке отображаются все устройства SRS, которые были перезапущены в течение последних 24 часов, и количество перезапусков</span><span class="sxs-lookup"><span data-stu-id="98cc9-210">This tile displays all SRS devices that have been restarted in the past 24 hours and number of restarts</span></span>
    
2. <span data-ttu-id="98cc9-211">Укажите заголовок группы. </span><span class="sxs-lookup"><span data-stu-id="98cc9-211">Assign Group Title</span></span> 
    
  ```
  SRS v2
  ```

3. <span data-ttu-id="98cc9-212">Не устанавливайте флажок для новой группы.</span><span class="sxs-lookup"><span data-stu-id="98cc9-212">Do not check the new group box.</span></span> <span data-ttu-id="98cc9-213">Вы уже сделали это при создании плитки 1, поэтому выполнять это действие повторно не нужно.</span><span class="sxs-lookup"><span data-stu-id="98cc9-213">You already did this when creating tile 1, and don't need to do it again.</span></span>
    
4. <span data-ttu-id="98cc9-214">Условные обозначения для плитки: </span><span class="sxs-lookup"><span data-stu-id="98cc9-214">Tile legend:</span></span> 
    
   ```
   Devices with App restarted (past 24 hours)
   ```

5. <span data-ttu-id="98cc9-215">Запрос для плитки: </span><span class="sxs-lookup"><span data-stu-id="98cc9-215">Tile Query:</span></span> 
    
   ```
   Type:Event EventLog:"Skype Room System" EventID:4000 TimeGenerated>NOW-24HOURS|measure count() by Computer
   ```

6. <span data-ttu-id="98cc9-216">Запрос для списка: </span><span class="sxs-lookup"><span data-stu-id="98cc9-216">List query:</span></span> 
    
   ```
   Type:Event EventLog:"Skype Room System" EventID:4000 TimeGenerated>NOW-24HOURS|measure count(EventID) by SRSDisplayName_CF
   ```

7. <span data-ttu-id="98cc9-217">Имя заголовков столбцов: </span><span class="sxs-lookup"><span data-stu-id="98cc9-217">Column titles Name:</span></span> 
    
   ```
   Display Name
   ```

8. <span data-ttu-id="98cc9-218">Значение заголовков столбцов: </span><span class="sxs-lookup"><span data-stu-id="98cc9-218">Column titles Value:</span></span> 
    
   ```
   Number of restarts
   ```

9. <span data-ttu-id="98cc9-219">Запрос навигации: </span><span class="sxs-lookup"><span data-stu-id="98cc9-219">Navigation query:</span></span> 
    
   ```
   {selected item} EventID:4000 TimeGenerated >NOW-24HOURS|Select TimeGenerated, Computer, SRSOperationName_CF, SRSOperationResult_CF,SRSEventDescription_CF, SRSAppVersion_CF, SRSDisplayName_CF, SRSAlias_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF
   ```

<span data-ttu-id="98cc9-p111">На этом создание представления завершено. Все доступные на данный момент оповещения отображаются на одной или нескольких этих плитках.</span><span class="sxs-lookup"><span data-stu-id="98cc9-p111">That completes view creation. The alerts currently available are all reflected in one or more of these tiles.</span></span>
## <a name="see-also"></a><span data-ttu-id="98cc9-222">Были ли эти инструкции полезны? Если да, укажите это в конце статьи. Если нет, сообщите нам о недочетах, и мы постараемся найти решение.</span><span class="sxs-lookup"><span data-stu-id="98cc9-222">See also</span></span>
<span data-ttu-id="98cc9-223"><a name="Views"> </a></span><span class="sxs-lookup"><span data-stu-id="98cc9-223"></span></span>

#### 

[<span data-ttu-id="98cc9-224">Планирование управления системами комнаты Скайп версии 2 с OMS</span><span class="sxs-lookup"><span data-stu-id="98cc9-224">Plan Skype Room Systems v2 management with OMS</span></span>](../../plan-your-deployment/clients-and-devices/oms-management.md)
  
[<span data-ttu-id="98cc9-225">Управление устройствами систем комнаты Скайп версии 2 с OMS</span><span class="sxs-lookup"><span data-stu-id="98cc9-225">Manage Skype Room Systems v2 devices with OMS</span></span>](../../manage/skype-room-systems-v2/oms.md)

