---
title: Настройка политик для Скайп для Business Server 2015 Stress and Performance Tool
ms.reviewer: ''
ms.author: heidip
author: microsoftheidi
ms.date: 11/11/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 7e1435e2-d073-4265-8067-ebcb5bf28835
description: Настройка политики для Скайп для Business Server 2015 Stress and Performance Tool.
ms.openlocfilehash: c5dd20df0cac3121169f6eb5659eb6339d7875e2
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "32236185"
---
# <a name="configuring-policies-for-the-skype-for-business-server-2015-stress-and-performance-tool"></a><span data-ttu-id="cbfdd-103">Настройка политик для Скайп для Business Server 2015 Stress and Performance Tool</span><span class="sxs-lookup"><span data-stu-id="cbfdd-103">Configuring policies for the Skype for Business Server 2015 Stress and Performance Tool</span></span>
 
<span data-ttu-id="cbfdd-104">Настройка политики для Скайп для Business Server 2015 Stress and Performance Tool.</span><span class="sxs-lookup"><span data-stu-id="cbfdd-104">Policy configuration for Skype for Business Server 2015 Stress and Performance Tool.</span></span>
  
<span data-ttu-id="cbfdd-105">Существует несколько политик и других областях, которые можно настроить в Скайп для Business Server 2015, перед запуском Stress and Performance Tool.</span><span class="sxs-lookup"><span data-stu-id="cbfdd-105">There are several policies and other areas that you can configure in Skype for Business Server 2015, prior to running the Stress and Performance Tool:</span></span>
  
- <span data-ttu-id="cbfdd-106">[Политика архивации](configuring-policies.md#ArchivingPolicy),</span><span class="sxs-lookup"><span data-stu-id="cbfdd-106">[Archiving policy](configuring-policies.md#ArchivingPolicy)</span></span>
    
- <span data-ttu-id="cbfdd-107">[Политика конференц-связи](configuring-policies.md#ConferencingPolicy),</span><span class="sxs-lookup"><span data-stu-id="cbfdd-107">[Conferencing policy](configuring-policies.md#ConferencingPolicy)</span></span>
    
- [<span data-ttu-id="cbfdd-108">Политика контактов</span><span class="sxs-lookup"><span data-stu-id="cbfdd-108">Contacts policy</span></span>](configuring-policies.md#ContactsPolicy)
    
- [<span data-ttu-id="cbfdd-109">Политика федерации</span><span class="sxs-lookup"><span data-stu-id="cbfdd-109">Federation policy</span></span>](configuring-policies.md#FederationPolicy)
    
- [<span data-ttu-id="cbfdd-110">Политика контроля допуска звонков</span><span class="sxs-lookup"><span data-stu-id="cbfdd-110">Call Admission Control policy</span></span>](configuring-policies.md#CACPolicy)
    
- [<span data-ttu-id="cbfdd-111">Правила маршрутизации голосовой связи</span><span class="sxs-lookup"><span data-stu-id="cbfdd-111">Voice Routing rules</span></span>](configuring-policies.md#VoiceRoutingRules)
    
- [<span data-ttu-id="cbfdd-112">Помощника по конференции</span><span class="sxs-lookup"><span data-stu-id="cbfdd-112">Conference Attendant application</span></span>](configuring-policies.md#ConfAttendantApp)
    
- [<span data-ttu-id="cbfdd-113">Служба приостановки звонков сервера</span><span class="sxs-lookup"><span data-stu-id="cbfdd-113">Server Call Park service</span></span>](configuring-policies.md#ServerCallParkServ)
    
- [<span data-ttu-id="cbfdd-114">Экстренные вызовы</span><span class="sxs-lookup"><span data-stu-id="cbfdd-114">Emergency calls</span></span>](configuring-policies.md#EmergencyCalls)
    
- [<span data-ttu-id="cbfdd-115">Настройка группы ответа приложения</span><span class="sxs-lookup"><span data-stu-id="cbfdd-115">Configuring Response Group application</span></span>](configuring-policies.md#ConfigResponseGroupApp)
    
## <a name="archiving-policy"></a><span data-ttu-id="cbfdd-116">Политики архивации</span><span class="sxs-lookup"><span data-stu-id="cbfdd-116">Archiving policy</span></span>
<span data-ttu-id="cbfdd-117"><a name="ArchivingPolicy"> </a></span><span class="sxs-lookup"><span data-stu-id="cbfdd-117"></span></span>

<span data-ttu-id="cbfdd-118">Если у вас есть сервер архивации, развернутых в вашей Скайп для топологии Business Server, вы откроете ArchivingPolicy.ps1 скрипта.</span><span class="sxs-lookup"><span data-stu-id="cbfdd-118">If you have an Archiving server deployed in your Skype for Business Server topology, you can look at the ArchivingPolicy.ps1 script.</span></span> <span data-ttu-id="cbfdd-119">Если вам требуется дополнительная помощь, просмотрите командлеты архивации и веб-конференций.</span><span class="sxs-lookup"><span data-stu-id="cbfdd-119">If you need further assistance, check out the Archiving and Web Conferencing cmdlets.</span></span>
  
## <a name="conferencing-policy"></a><span data-ttu-id="cbfdd-120">Политика конференц-связи</span><span class="sxs-lookup"><span data-stu-id="cbfdd-120">Conferencing policy</span></span>
<span data-ttu-id="cbfdd-121"><a name="ConferencingPolicy"> </a></span><span class="sxs-lookup"><span data-stu-id="cbfdd-121"></span></span>

<span data-ttu-id="cbfdd-122">Для конференц-связи у нас есть сценарий MeetingPolicy.ps1.</span><span class="sxs-lookup"><span data-stu-id="cbfdd-122">For conferencing, we have the MeetingPolicy.ps1 script.</span></span> <span data-ttu-id="cbfdd-123">Если вам требуется дополнительная помощь, просмотрите командлеты веб-конференций.</span><span class="sxs-lookup"><span data-stu-id="cbfdd-123">If you need further assistance, check out the Web Conferencing cmdlets.</span></span>
  
## <a name="contacts-policy"></a><span data-ttu-id="cbfdd-124">Политика контактов</span><span class="sxs-lookup"><span data-stu-id="cbfdd-124">Contacts policy</span></span>
<span data-ttu-id="cbfdd-125"><a name="ContactsPolicy"> </a></span><span class="sxs-lookup"><span data-stu-id="cbfdd-125"></span></span>

<span data-ttu-id="cbfdd-126">Сценарий ContactsPolicy.ps1 будет пример, который необходимо просмотреть.</span><span class="sxs-lookup"><span data-stu-id="cbfdd-126">ContactsPolicy.ps1 script will be the sample you'll need to review.</span></span> <span data-ttu-id="cbfdd-127">Командлеты обмена мгновенными Сообщениями и присутствия представлены сведения, если вам требуется дополнительная ссылки.</span><span class="sxs-lookup"><span data-stu-id="cbfdd-127">The IM and Presence cmdlets will help if you need further references.</span></span>
  
## <a name="federation-policy"></a><span data-ttu-id="cbfdd-128">Политика федерации</span><span class="sxs-lookup"><span data-stu-id="cbfdd-128">Federation policy</span></span>
<span data-ttu-id="cbfdd-129"><a name="FederationPolicy"> </a></span><span class="sxs-lookup"><span data-stu-id="cbfdd-129"></span></span>

<span data-ttu-id="cbfdd-130">Образец сценария для федерации — FederationPolicy.ps1.</span><span class="sxs-lookup"><span data-stu-id="cbfdd-130">The sample script for federation is FederationPolicy.ps1.</span></span> <span data-ttu-id="cbfdd-131">Командлеты для просмотра, если вам требуется дополнительная возможность получения, будут пограничного сервера, Федерация и внешний доступ.</span><span class="sxs-lookup"><span data-stu-id="cbfdd-131">The cmdlets to review, if you need further insight, will be Edge Server, federation, and external access.</span></span>
  
## <a name="call-admission-control-policy"></a><span data-ttu-id="cbfdd-132">Политика контроля допуска звонков</span><span class="sxs-lookup"><span data-stu-id="cbfdd-132">Call Admission Control policy</span></span>
<span data-ttu-id="cbfdd-133"><a name="CACPolicy"> </a></span><span class="sxs-lookup"><span data-stu-id="cbfdd-133"></span></span>

<span data-ttu-id="cbfdd-134">Можно указывать BandwidthPolicy.ps1 для этой политики.</span><span class="sxs-lookup"><span data-stu-id="cbfdd-134">You can reference BandwidthPolicy.ps1 for this policy.</span></span> <span data-ttu-id="cbfdd-135">Дополнительные сведения также будут иметь командлеты контроля допуска звонков.</span><span class="sxs-lookup"><span data-stu-id="cbfdd-135">The Call Admission Control cmdlets will have further information as well.</span></span>
  
## <a name="voice-routing-rules"></a><span data-ttu-id="cbfdd-136">Правила маршрутизации голосовой связи</span><span class="sxs-lookup"><span data-stu-id="cbfdd-136">Voice Routing rules</span></span>
<span data-ttu-id="cbfdd-137"><a name="VoiceRoutingRules"> </a></span><span class="sxs-lookup"><span data-stu-id="cbfdd-137"></span></span>

<span data-ttu-id="cbfdd-138">Образец сценария RoutingRules.ps1 потребуются для маршрутизации голосовых вызовов.</span><span class="sxs-lookup"><span data-stu-id="cbfdd-138">You'll need the RoutingRules.ps1 sample script for Voice Routing.</span></span> <span data-ttu-id="cbfdd-139">При настройке эти правила, запомните контекста телефона (то есть, профиль /Location или /SimpleName) и коды области внутренний или внешний, таким образом, чтобы их можно задать при создании пользователей.</span><span class="sxs-lookup"><span data-stu-id="cbfdd-139">When you're configuring these rules, take note of the phone context (that is, /Location Profile or /SimpleName) and Internal/External Area Codes, so that you can specify them when creating users.</span></span> <span data-ttu-id="cbfdd-140">Вам также понадобится их во время настройки LyncPerfTool (специально для объединенных Коммуникаций ТСОП и объединенных Коммуникаций PSTN).</span><span class="sxs-lookup"><span data-stu-id="cbfdd-140">You'll also need them during LyncPerfTool configuration (specifically for PSTN-UC and UC-PSTN).</span></span>
  
<span data-ttu-id="cbfdd-141">Например параметр SimpleName в вызове командлета **New-CsDialPlan** в примере RoutingRules.ps1 должен использоваться для значения LocationProfile на следующем рисунке UserProfileGenerator.exe:</span><span class="sxs-lookup"><span data-stu-id="cbfdd-141">For example, the SimpleName parameter in the call to the **New-CsDialPlan** cmdlet in the RoutingRules.ps1 example should be used for the LocationProfile value in the following figure of UserProfileGenerator.exe:</span></span>
  
![Средство конфигурации нагрузки Skype для бизнеса, вкладка Voice Scenarios (Голосовые сценарии), дополнительные параметры для бесед.](../../media/59f42e4e-8f1e-4d43-9ae2-9e6026191951.png)
  
<span data-ttu-id="cbfdd-143">Для получения дополнительных сведений можно просмотреть командлеты корпоративной голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="cbfdd-143">For details, you can review the Enterprise Voice cmdlets.</span></span>
  
## <a name="conference-attendant-application"></a><span data-ttu-id="cbfdd-144">Помощника по конференции</span><span class="sxs-lookup"><span data-stu-id="cbfdd-144">Conference Attendant application</span></span>
<span data-ttu-id="cbfdd-145"><a name="ConfAttendantApp"> </a></span><span class="sxs-lookup"><span data-stu-id="cbfdd-145"></span></span>

<span data-ttu-id="cbfdd-146">Сначала просмотрите сценарий ConferenceAutoAttendantConfiguration.ps1.</span><span class="sxs-lookup"><span data-stu-id="cbfdd-146">First review the ConferenceAutoAttendantConfiguration.ps1 script.</span></span> <span data-ttu-id="cbfdd-147">Вы наверняка хотели бы принять к сведению ConferencingAutoAttendant номер телефона (1121111111 по умолчанию), чтобы ввести в средстве настройки LyncPerfTool для создания конфигурации, как показано ниже:</span><span class="sxs-lookup"><span data-stu-id="cbfdd-147">You'll want to take note of the ConferencingAutoAttendant phone number (1121111111 by default), so that you can enter it into the LyncPerfTool configuration tool for configuration generation, as below:</span></span>
  
![Вкладка Voice Scenarios (Голосовые сценарии) с уровнем нагрузки конференц-связи и номером телефона.](../../media/a3ea5fc0-8b3d-4842-b809-f137f470dbdc.png)
  
<span data-ttu-id="cbfdd-149">Более подробные сведения можно найти в конференц-связь и конференц связи с телефонным командлетов.</span><span class="sxs-lookup"><span data-stu-id="cbfdd-149">You'll find more details in the Conferencing and Dial-in Conferencing cmdlets.</span></span>
  
## <a name="server-call-park-service"></a><span data-ttu-id="cbfdd-150">Служба приостановки звонков сервера</span><span class="sxs-lookup"><span data-stu-id="cbfdd-150">Server Call Park service</span></span>
<span data-ttu-id="cbfdd-151"><a name="ServerCallParkServ"> </a></span><span class="sxs-lookup"><span data-stu-id="cbfdd-151"></span></span>

<span data-ttu-id="cbfdd-152">Фактически отключена по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="cbfdd-152">This is actually disabled by default.</span></span> <span data-ttu-id="cbfdd-153">Если вам нужно проверить это, можно просмотреть образец сценария CallParkConfiguration.ps1.</span><span class="sxs-lookup"><span data-stu-id="cbfdd-153">You can review the CallParkConfiguration.ps1 sample script if you need to test this.</span></span> <span data-ttu-id="cbfdd-154">Кроме того извлекать командлеты приложения парковки вызовов при необходимости.</span><span class="sxs-lookup"><span data-stu-id="cbfdd-154">Additionally, check out the Call Park Application cmdlets as needed.</span></span>
  
## <a name="emergency-calls"></a><span data-ttu-id="cbfdd-155">Экстренные вызовы</span><span class="sxs-lookup"><span data-stu-id="cbfdd-155">Emergency calls</span></span>
<span data-ttu-id="cbfdd-156"><a name="EmergencyCalls"> </a></span><span class="sxs-lookup"><span data-stu-id="cbfdd-156"></span></span>

<span data-ttu-id="cbfdd-157">Вам потребуется выполнить следующие действия по настройке нагрузка и тестирование производительности для экстренных вызовов:</span><span class="sxs-lookup"><span data-stu-id="cbfdd-157">You'll need to perform the following steps to configure stress and performance testing for emergency calls:</span></span>
  
1. <span data-ttu-id="cbfdd-158">Настройка маршрута голосовой связи для экстренных вызовов.</span><span class="sxs-lookup"><span data-stu-id="cbfdd-158">Set up a voice route for emergency calls.</span></span> <span data-ttu-id="cbfdd-159">Можно использовать сценарий RoutingRules.ps1 и проверьте в поле Примечание « **Службы E911 маршрут ТСОП** » пример того, как настроить этот маршрут голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="cbfdd-159">You can use the RoutingRules.ps1 script, and check under the comment " **Route E911 to PSTN** " for an example of how to set up this voice route.</span></span>
    
    > [!CAUTION]
    > <span data-ttu-id="cbfdd-160">Пример команды в RoutingRules.ps1 имеет шаблон номера, который включает в себя номер 119, а не 911.</span><span class="sxs-lookup"><span data-stu-id="cbfdd-160">The example command in RoutingRules.ps1 has a number pattern that includes the number 119 rather than 911.</span></span> <span data-ttu-id="cbfdd-161">Следует избегать использования 911 (или фактический номер экстренного вызова на локальном), чтобы предотвратить случайное вызовы вашей локальной экстренных операторов во время нагрузочного тестирования.</span><span class="sxs-lookup"><span data-stu-id="cbfdd-161">You should avoid using 911 (or your actual local emergency number) to prevent accidental calls to your local emergency operators during your load testing.</span></span> <span data-ttu-id="cbfdd-162">Имейте в виду, эта конфигурация только для целей моделирования!</span><span class="sxs-lookup"><span data-stu-id="cbfdd-162">Remember, this configuration is for simulation purposes only!</span></span> 
  
2. <span data-ttu-id="cbfdd-163">Настройте адреса, заполнив значения на вкладке **Расположение файла конфигурации службы сведения** в UserProvisioningTool, как показано на следующем рисунке:</span><span class="sxs-lookup"><span data-stu-id="cbfdd-163">Configure addresses by filling in the values on the **Location Info Service Config** tab in the UserProvisioningTool, as shown in the following figure:</span></span>
    
     ![Средство подготовки пользователей, отображающее количество адресов, подсетей, коммутаторов и портов.](../../media/ebe85a0c-750f-4301-97d4-d158a40ea98a.png)
  
3. <span data-ttu-id="cbfdd-165">После ввода всех компонентов в UserProvisioningTool, нажмите кнопку **Создать файлы Config локальный источник установки** .</span><span class="sxs-lookup"><span data-stu-id="cbfdd-165">When you've entered everything into the UserProvisioningTool, click the **Generate LIS Config Files** button.</span></span>
    
4. <span data-ttu-id="cbfdd-166">Теперь будет создан CSV-файлов для портов, подсетей, коммутаторы и точки беспроводного доступа (WAPs), а также XML-файла для средства нагрузка и производительность.</span><span class="sxs-lookup"><span data-stu-id="cbfdd-166">Now CSV files for ports, subnets, switches, and wireless access points (WAPs), as well as an XML file for the Stress and Performance tool will be generated.</span></span> <span data-ttu-id="cbfdd-167">При настройке службы сведения о местоположении (LIS) с помощью сценария LisConfiguration.ps1 можно использовать CSV-файлов для входные данные.</span><span class="sxs-lookup"><span data-stu-id="cbfdd-167">You can use the CSV files for inputs when configuring the Location Information service (LIS) with the LisConfiguration.ps1 script.</span></span> <span data-ttu-id="cbfdd-168">Для этого необходимо переместить файл Locations0.xml в ту же папку Stress and Performance Tool исполняемый файл (LyncPerfTool.exe).</span><span class="sxs-lookup"><span data-stu-id="cbfdd-168">To do this, you'll need to move the Locations0.xml file to the same folder as the Stress and Performance Tool executable (LyncPerfTool.exe).</span></span> <span data-ttu-id="cbfdd-169">Это позволит выполнить расположение сценарии профиля (абонентской группы).</span><span class="sxs-lookup"><span data-stu-id="cbfdd-169">This will let you run location profile (dial plan) scenarios.</span></span>
    
## <a name="configuring-response-group-application"></a><span data-ttu-id="cbfdd-170">Настройка группы ответа приложения</span><span class="sxs-lookup"><span data-stu-id="cbfdd-170">Configuring Response Group application</span></span>
<span data-ttu-id="cbfdd-171"><a name="ConfigResponseGroupApp"> </a></span><span class="sxs-lookup"><span data-stu-id="cbfdd-171"></span></span>

<span data-ttu-id="cbfdd-172">Образец сценария — ResponseGroupConfiguration.ps1.</span><span class="sxs-lookup"><span data-stu-id="cbfdd-172">The sample script is ResponseGroupConfiguration.ps1.</span></span> <span data-ttu-id="cbfdd-173">Также есть командлеты приложения группы ответа для просмотра для сведения о конфигурации.</span><span class="sxs-lookup"><span data-stu-id="cbfdd-173">There are also Response Group application cmdlets to review for further configuration details.</span></span> <span data-ttu-id="cbfdd-174">Следующая схема будет показывать некоторые сведения о конфигурации:</span><span class="sxs-lookup"><span data-stu-id="cbfdd-174">The following diagram will show some of the configuration details:</span></span>
  
![Средство конфигурации "Группа ответа" с существующими рабочими процессами для тестирования.](../../media/e218a345-4813-4332-8cff-b48de05017ef.jpg)
  

