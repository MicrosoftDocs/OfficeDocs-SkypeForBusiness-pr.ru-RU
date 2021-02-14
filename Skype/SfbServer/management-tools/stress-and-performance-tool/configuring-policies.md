---
title: Настройка политик для средства skype for Business Server 2015 Stress and Performance Tool
ms.reviewer: ''
ms.author: v-cichur
author: cichur
ms.date: 11/11/2015
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 7e1435e2-d073-4265-8067-ebcb5bf28835
description: Настройка политики для средства Stress and Performance Skype для бизнеса Server 2015.
ms.openlocfilehash: bb049d5740d74e5ebeacd8a21d00e2644da61a7c
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49815039"
---
# <a name="configuring-policies-for-the-skype-for-business-server-2015-stress-and-performance-tool"></a><span data-ttu-id="35bca-103">Настройка политик для средства skype for Business Server 2015 Stress and Performance Tool</span><span class="sxs-lookup"><span data-stu-id="35bca-103">Configuring policies for the Skype for Business Server 2015 Stress and Performance Tool</span></span>
 
<span data-ttu-id="35bca-104">Настройка политики для средства Stress and Performance Skype для бизнеса Server 2015.</span><span class="sxs-lookup"><span data-stu-id="35bca-104">Policy configuration for Skype for Business Server 2015 Stress and Performance Tool.</span></span>
  
<span data-ttu-id="35bca-105">Существует несколько политик и других областей, которые можно настроить в Skype для бизнеса Server 2015 перед запуском средства Stress and Performance.</span><span class="sxs-lookup"><span data-stu-id="35bca-105">There are several policies and other areas that you can configure in Skype for Business Server 2015, prior to running the Stress and Performance Tool:</span></span>
  
- <span data-ttu-id="35bca-106">[Archiving policy](configuring-policies.md#ArchivingPolicy) (Политика архивации),</span><span class="sxs-lookup"><span data-stu-id="35bca-106">[Archiving policy](configuring-policies.md#ArchivingPolicy)</span></span>
    
- <span data-ttu-id="35bca-107">[Политика конференц-связи](configuring-policies.md#ConferencingPolicy),</span><span class="sxs-lookup"><span data-stu-id="35bca-107">[Conferencing policy](configuring-policies.md#ConferencingPolicy)</span></span>
    
- [<span data-ttu-id="35bca-108">Политика контактов</span><span class="sxs-lookup"><span data-stu-id="35bca-108">Contacts policy</span></span>](configuring-policies.md#ContactsPolicy)
    
- [<span data-ttu-id="35bca-109">Политика федерации</span><span class="sxs-lookup"><span data-stu-id="35bca-109">Federation policy</span></span>](configuring-policies.md#FederationPolicy)
    
- [<span data-ttu-id="35bca-110">Политика контроля допуска вызовов</span><span class="sxs-lookup"><span data-stu-id="35bca-110">Call Admission Control policy</span></span>](configuring-policies.md#CACPolicy)
    
- [<span data-ttu-id="35bca-111">Правила маршрутки голосовой почты</span><span class="sxs-lookup"><span data-stu-id="35bca-111">Voice Routing rules</span></span>](configuring-policies.md#VoiceRoutingRules)
    
- [<span data-ttu-id="35bca-112">Приложение помощника по конференц-залам</span><span class="sxs-lookup"><span data-stu-id="35bca-112">Conference Attendant application</span></span>](configuring-policies.md#ConfAttendantApp)
    
- [<span data-ttu-id="35bca-113">Служба парковки вызовов сервера</span><span class="sxs-lookup"><span data-stu-id="35bca-113">Server Call Park service</span></span>](configuring-policies.md#ServerCallParkServ)
    
- [<span data-ttu-id="35bca-114">Экстренные вызовы</span><span class="sxs-lookup"><span data-stu-id="35bca-114">Emergency calls</span></span>](configuring-policies.md#EmergencyCalls)
    
- [<span data-ttu-id="35bca-115">Настройка приложения группы ответа</span><span class="sxs-lookup"><span data-stu-id="35bca-115">Configuring Response Group application</span></span>](configuring-policies.md#ConfigResponseGroupApp)
    
## <a name="archiving-policy"></a><span data-ttu-id="35bca-116">Политика архивации</span><span class="sxs-lookup"><span data-stu-id="35bca-116">Archiving policy</span></span>
<span data-ttu-id="35bca-117"><a name="ArchivingPolicy"> </a></span><span class="sxs-lookup"><span data-stu-id="35bca-117"><a name="ArchivingPolicy"> </a></span></span>

<span data-ttu-id="35bca-118">If you have an Archiving server deployed in your Skype for Business Server topology, you can look at the ArchivingPolicy.ps1 script.</span><span class="sxs-lookup"><span data-stu-id="35bca-118">If you have an Archiving server deployed in your Skype for Business Server topology, you can look at the ArchivingPolicy.ps1 script.</span></span> <span data-ttu-id="35bca-119">Если вам нужна дополнительная помощь, ознакомьтесь с дополнительными службами архива и веб-конференций.</span><span class="sxs-lookup"><span data-stu-id="35bca-119">If you need further assistance, check out the Archiving and Web Conferencing cmdlets.</span></span>
  
## <a name="conferencing-policy"></a><span data-ttu-id="35bca-120">Политика конференц-связи</span><span class="sxs-lookup"><span data-stu-id="35bca-120">Conferencing policy</span></span>
<span data-ttu-id="35bca-121"><a name="ConferencingPolicy"> </a></span><span class="sxs-lookup"><span data-stu-id="35bca-121"><a name="ConferencingPolicy"> </a></span></span>

<span data-ttu-id="35bca-122">Для conferencing у нас есть MeetingPolicy.ps1 сценарий.</span><span class="sxs-lookup"><span data-stu-id="35bca-122">For conferencing, we have the MeetingPolicy.ps1 script.</span></span> <span data-ttu-id="35bca-123">Если вам нужна дополнительная помощь, ознакомьтесь с помощью веб-служб.</span><span class="sxs-lookup"><span data-stu-id="35bca-123">If you need further assistance, check out the Web Conferencing cmdlets.</span></span>
  
## <a name="contacts-policy"></a><span data-ttu-id="35bca-124">Политика контактов</span><span class="sxs-lookup"><span data-stu-id="35bca-124">Contacts policy</span></span>
<span data-ttu-id="35bca-125"><a name="ContactsPolicy"> </a></span><span class="sxs-lookup"><span data-stu-id="35bca-125"><a name="ContactsPolicy"> </a></span></span>

<span data-ttu-id="35bca-126">ContactsPolicy.ps1 сценарий будет образцом, который необходимо просмотреть.</span><span class="sxs-lookup"><span data-stu-id="35bca-126">ContactsPolicy.ps1 script will be the sample you'll need to review.</span></span> <span data-ttu-id="35bca-127">Если вам нужны дополнительные ссылки, вам помогут эти дополнительные данные.</span><span class="sxs-lookup"><span data-stu-id="35bca-127">The IM and Presence cmdlets will help if you need further references.</span></span>
  
## <a name="federation-policy"></a><span data-ttu-id="35bca-128">Политика федерации</span><span class="sxs-lookup"><span data-stu-id="35bca-128">Federation policy</span></span>
<span data-ttu-id="35bca-129"><a name="FederationPolicy"> </a></span><span class="sxs-lookup"><span data-stu-id="35bca-129"><a name="FederationPolicy"> </a></span></span>

<span data-ttu-id="35bca-130">Пример сценария для федерации — FederationPolicy.ps1.</span><span class="sxs-lookup"><span data-stu-id="35bca-130">The sample script for federation is FederationPolicy.ps1.</span></span> <span data-ttu-id="35bca-131">Если вам нужны дополнительные сведения, это будет edge Server, федерация и внешний доступ.</span><span class="sxs-lookup"><span data-stu-id="35bca-131">The cmdlets to review, if you need further insight, will be Edge Server, federation, and external access.</span></span>
  
## <a name="call-admission-control-policy"></a><span data-ttu-id="35bca-132">Политика контроля допуска вызовов</span><span class="sxs-lookup"><span data-stu-id="35bca-132">Call Admission Control policy</span></span>
<span data-ttu-id="35bca-133"><a name="CACPolicy"> </a></span><span class="sxs-lookup"><span data-stu-id="35bca-133"><a name="CACPolicy"> </a></span></span>

<span data-ttu-id="35bca-134">Вы можете ссылаться на BandwidthPolicy.ps1 для этой политики.</span><span class="sxs-lookup"><span data-stu-id="35bca-134">You can reference BandwidthPolicy.ps1 for this policy.</span></span> <span data-ttu-id="35bca-135">Дополнительные сведения также будут иметься в дополнительных сведениях о диспетчере контроля допуска вызовов.</span><span class="sxs-lookup"><span data-stu-id="35bca-135">The Call Admission Control cmdlets will have further information as well.</span></span>
  
## <a name="voice-routing-rules"></a><span data-ttu-id="35bca-136">Правила маршрутки голосовой почты</span><span class="sxs-lookup"><span data-stu-id="35bca-136">Voice Routing rules</span></span>
<span data-ttu-id="35bca-137"><a name="VoiceRoutingRules"> </a></span><span class="sxs-lookup"><span data-stu-id="35bca-137"><a name="VoiceRoutingRules"> </a></span></span>

<span data-ttu-id="35bca-138">Вам потребуется пример сценария RoutingRules.ps1 для маршрутной голосовой почты.</span><span class="sxs-lookup"><span data-stu-id="35bca-138">You'll need the RoutingRules.ps1 sample script for Voice Routing.</span></span> <span data-ttu-id="35bca-139">При настройке этих правил заметьте контекст телефона (то есть /Location Profile или /SimpleName) и коды внутренней и внешней области, чтобы указать их при создании пользователей.</span><span class="sxs-lookup"><span data-stu-id="35bca-139">When you're configuring these rules, take note of the phone context (that is, /Location Profile or /SimpleName) and Internal/External Area Codes, so that you can specify them when creating users.</span></span> <span data-ttu-id="35bca-140">Они также потребуется во время настройки LyncPerfTool (в частности, для PSTN-UC и UC-PSTN).</span><span class="sxs-lookup"><span data-stu-id="35bca-140">You'll also need them during LyncPerfTool configuration (specifically for PSTN-UC and UC-PSTN).</span></span>
  
<span data-ttu-id="35bca-141">Например, параметр SimpleName в вызове для параметра **New-CsDialPlan** в примере RoutingRules.ps1 должен использоваться для значения LocationProfile на следующем рисунке UserProfileGenerator.exe:</span><span class="sxs-lookup"><span data-stu-id="35bca-141">For example, the SimpleName parameter in the call to the **New-CsDialPlan** cmdlet in the RoutingRules.ps1 example should be used for the LocationProfile value in the following figure of UserProfileGenerator.exe:</span></span>
  
![Средство настройки нагрузки Skype для бизнеса, вкладка "Сценарии голосовой связи", дополнительные параметры для бесед.](../../media/59f42e4e-8f1e-4d43-9ae2-9e6026191951.png)
  
<span data-ttu-id="35bca-143">Подробные сведения см. в Корпоративная голосовая связь управления.</span><span class="sxs-lookup"><span data-stu-id="35bca-143">For details, you can review the Enterprise Voice cmdlets.</span></span>
  
## <a name="conference-attendant-application"></a><span data-ttu-id="35bca-144">Приложение помощника по конференц-залам</span><span class="sxs-lookup"><span data-stu-id="35bca-144">Conference Attendant application</span></span>
<span data-ttu-id="35bca-145"><a name="ConfAttendantApp"> </a></span><span class="sxs-lookup"><span data-stu-id="35bca-145"><a name="ConfAttendantApp"> </a></span></span>

<span data-ttu-id="35bca-146">Сначала просмотрите сценарий ConferenceAutoAttendantConfiguration.ps1.</span><span class="sxs-lookup"><span data-stu-id="35bca-146">First review the ConferenceAutoAttendantConfiguration.ps1 script.</span></span> <span data-ttu-id="35bca-147">Обратите внимание на номер телефона conferencingAutoAttendant (1121111111 по умолчанию), чтобы ввести его в средство настройки LyncPerfTool для создания конфигурации, как по умолчанию:</span><span class="sxs-lookup"><span data-stu-id="35bca-147">You'll want to take note of the ConferencingAutoAttendant phone number (1121111111 by default), so that you can enter it into the LyncPerfTool configuration tool for configuration generation, as below:</span></span>
  
![Вкладка "Сценарии голосовой связи" с уровнем нагрузки на conferencing и номером телефона.](../../media/a3ea5fc0-8b3d-4842-b809-f137f470dbdc.png)
  
<span data-ttu-id="35bca-149">Дополнительные сведения см. в дополнительных сведениях в cmdlets conferencing and Dial-in Conferencing.</span><span class="sxs-lookup"><span data-stu-id="35bca-149">You'll find more details in the Conferencing and Dial-in Conferencing cmdlets.</span></span>
  
## <a name="server-call-park-service"></a><span data-ttu-id="35bca-150">Служба парковки вызовов сервера</span><span class="sxs-lookup"><span data-stu-id="35bca-150">Server Call Park service</span></span>
<span data-ttu-id="35bca-151"><a name="ServerCallParkServ"> </a></span><span class="sxs-lookup"><span data-stu-id="35bca-151"><a name="ServerCallParkServ"> </a></span></span>

<span data-ttu-id="35bca-152">По умолчанию этот режим отключен.</span><span class="sxs-lookup"><span data-stu-id="35bca-152">This is actually disabled by default.</span></span> <span data-ttu-id="35bca-153">Вы можете просмотреть пример CallParkConfiguration.ps1, если вам нужно проверить этот сценарий.</span><span class="sxs-lookup"><span data-stu-id="35bca-153">You can review the CallParkConfiguration.ps1 sample script if you need to test this.</span></span> <span data-ttu-id="35bca-154">Кроме того, при необходимости ознакомьтесь с необходимыми cmdlets приложения парковки вызовов.</span><span class="sxs-lookup"><span data-stu-id="35bca-154">Additionally, check out the Call Park Application cmdlets as needed.</span></span>
  
## <a name="emergency-calls"></a><span data-ttu-id="35bca-155">Экстренные вызовы</span><span class="sxs-lookup"><span data-stu-id="35bca-155">Emergency calls</span></span>
<span data-ttu-id="35bca-156"><a name="EmergencyCalls"> </a></span><span class="sxs-lookup"><span data-stu-id="35bca-156"><a name="EmergencyCalls"> </a></span></span>

<span data-ttu-id="35bca-157">Чтобы настроить тестирование нагрузки и производительности для экстренных вызовов, необходимо выполнить следующие действия.</span><span class="sxs-lookup"><span data-stu-id="35bca-157">You'll need to perform the following steps to configure stress and performance testing for emergency calls:</span></span>
  
1. <span data-ttu-id="35bca-158">Настройка маршрута голосовой почты для экстренных вызовов.</span><span class="sxs-lookup"><span data-stu-id="35bca-158">Set up a voice route for emergency calls.</span></span> <span data-ttu-id="35bca-159">Вы можете использовать сценарий RoutingRules.ps1 и проверить в комментарии **"Route E911 to PSTN"** пример того, как настроить этот маршрут голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="35bca-159">You can use the RoutingRules.ps1 script, and check under the comment " **Route E911 to PSTN** " for an example of how to set up this voice route.</span></span>
    
    > [!CAUTION]
    > <span data-ttu-id="35bca-160">Пример команды в RoutingRules.ps1 имеет шаблон числа, который включает число 119, а не 911.</span><span class="sxs-lookup"><span data-stu-id="35bca-160">The example command in RoutingRules.ps1 has a number pattern that includes the number 119 rather than 911.</span></span> <span data-ttu-id="35bca-161">Не следует использовать номер 911 (или фактический локальный номер экстренного вызова), чтобы предотвратить случайные вызовы локальных операторов экстренных служб во время нагрузок.</span><span class="sxs-lookup"><span data-stu-id="35bca-161">You should avoid using 911 (or your actual local emergency number) to prevent accidental calls to your local emergency operators during your load testing.</span></span> <span data-ttu-id="35bca-162">Помните, что эта конфигурация предназначена только для имитации!</span><span class="sxs-lookup"><span data-stu-id="35bca-162">Remember, this configuration is for simulation purposes only!</span></span> 
  
2. <span data-ttu-id="35bca-163">Настройте адреса, заполнив значения на вкладке **"Конфигурация** службы информации о расположении" в UserProvisioningTool, как показано на следующем рисунке:</span><span class="sxs-lookup"><span data-stu-id="35bca-163">Configure addresses by filling in the values on the **Location Info Service Config** tab in the UserProvisioningTool, as shown in the following figure:</span></span>
    
     ![Средство пользовательской подготовка, показывающая количество адресов, подсетей, коммутаторов и портов.](../../media/ebe85a0c-750f-4301-97d4-d158a40ea98a.png)
  
3. <span data-ttu-id="35bca-165">После того как вы ввели все данные в UserProvisioningTool, нажмите кнопку **"Создать файлы config LIS".**</span><span class="sxs-lookup"><span data-stu-id="35bca-165">When you've entered everything into the UserProvisioningTool, click the **Generate LIS Config Files** button.</span></span>
    
4. <span data-ttu-id="35bca-166">Теперь будут созданы CSV-файлы для портов, подсетей, коммутаторов и беспроводных точек доступа (WAP), а также XML-файл для средства Stress and Performance.</span><span class="sxs-lookup"><span data-stu-id="35bca-166">Now CSV files for ports, subnets, switches, and wireless access points (WAPs), as well as an XML file for the Stress and Performance tool will be generated.</span></span> <span data-ttu-id="35bca-167">CSV-файлы можно использовать для ввода при настройке службы сведений о местонахождении (LIS) с помощью LisConfiguration.ps1 сценария.</span><span class="sxs-lookup"><span data-stu-id="35bca-167">You can use the CSV files for inputs when configuring the Location Information service (LIS) with the LisConfiguration.ps1 script.</span></span> <span data-ttu-id="35bca-168">Для этого необходимо переместить файл Locations0.xml в ту же папку, что и исполняемый файл средства stress and Performance Tool (LyncPerfTool.exe).</span><span class="sxs-lookup"><span data-stu-id="35bca-168">To do this, you'll need to move the Locations0.xml file to the same folder as the Stress and Performance Tool executable (LyncPerfTool.exe).</span></span> <span data-ttu-id="35bca-169">Это позволит вам запускать сценарии профилей местоположений (телефонных планов).</span><span class="sxs-lookup"><span data-stu-id="35bca-169">This will let you run location profile (dial plan) scenarios.</span></span>
    
## <a name="configuring-response-group-application"></a><span data-ttu-id="35bca-170">Настройка приложения группы ответа</span><span class="sxs-lookup"><span data-stu-id="35bca-170">Configuring Response Group application</span></span>
<span data-ttu-id="35bca-171"><a name="ConfigResponseGroupApp"> </a></span><span class="sxs-lookup"><span data-stu-id="35bca-171"><a name="ConfigResponseGroupApp"> </a></span></span>

<span data-ttu-id="35bca-172">Пример скрипта ResponseGroupConfiguration.ps1.</span><span class="sxs-lookup"><span data-stu-id="35bca-172">The sample script is ResponseGroupConfiguration.ps1.</span></span> <span data-ttu-id="35bca-173">Кроме того, для получения дополнительных сведений о конфигурации необходимо просмотреть дополнительные сведения о приложениях группы ответа.</span><span class="sxs-lookup"><span data-stu-id="35bca-173">There are also Response Group application cmdlets to review for further configuration details.</span></span> <span data-ttu-id="35bca-174">На следующей схеме покажем некоторые сведения о конфигурации:</span><span class="sxs-lookup"><span data-stu-id="35bca-174">The following diagram will show some of the configuration details:</span></span>
  
![Средство проверки группы ответа, показывающая существующие процессы для тестирования.](../../media/e218a345-4813-4332-8cff-b48de05017ef.jpg)
  

