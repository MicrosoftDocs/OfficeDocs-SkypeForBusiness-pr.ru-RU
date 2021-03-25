---
title: Настройка сервера межоператоров видеосвязи в Skype для бизнеса Server
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
ms.collection: IT_Skype16
ms.assetid: 0fde142b-70b1-46c6-b1f9-f9d70115371d
description: Сводка. Настройка роли Video Interop Server (VIS) в Skype для бизнеса Server.
ms.openlocfilehash: 8d5da36d07583cc1c20407d842b94531062947ba
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51120308"
---
# <a name="configure-the-video-interop-server-in-skype-for-business-server"></a><span data-ttu-id="3707d-103">Настройка сервера межоператоров видеосвязи в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="3707d-103">Configure the Video Interop Server in Skype for Business Server</span></span>
 
<span data-ttu-id="3707d-104">**Сводка:** Настройка роли Video Interop Server (VIS) в Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="3707d-104">**Summary:** Configure the Video Interop Server (VIS) role in Skype for Business Server.</span></span>
  
 <span data-ttu-id="3707d-105">Настройка параметров, которые VIS будет связывать с магистральми видео с помощью Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3707d-105">Configure the settings that the VIS will associate with video trunks using Windows PowerShell.</span></span> <span data-ttu-id="3707d-106">Конфигурация магистрали видео с глобальной областью создается после установки службы VIS.</span><span class="sxs-lookup"><span data-stu-id="3707d-106">A video trunk configuration with global scope is created once the VIS service is installed.</span></span> <span data-ttu-id="3707d-107">Эта конфигурация магистрали видео применяется VIS для всех магистральных магистрали, которые не имеют конфигурации магистрали видео с более определенной областью.</span><span class="sxs-lookup"><span data-stu-id="3707d-107">This video trunk configuration is applied by the VIS to all trunks which do not have video trunk configuration with a more specific scope.</span></span> <span data-ttu-id="3707d-108">Обратите внимание, что конфигурация магистрали видео — это коллекция параметров, применимых к магистральм видео.</span><span class="sxs-lookup"><span data-stu-id="3707d-108">Note that the video trunk configuration is a collection of settings that is applicable to video trunks.</span></span>
  
## <a name="configure-video-trunk-and-dial-plan"></a><span data-ttu-id="3707d-109">Настройка магистрали видео и набора номера</span><span class="sxs-lookup"><span data-stu-id="3707d-109">Configure video trunk and dial plan</span></span>

<span data-ttu-id="3707d-110">Используйте следующие команды Windows PowerShell, чтобы указать конфигурацию магистрали видео и план набора номера, которые будут связаны с недавно определенным магистральом(ы), определенным в документе топологии между VIS и всеми шлюзами видео.</span><span class="sxs-lookup"><span data-stu-id="3707d-110">Use the following Windows PowerShell commands to specify the video trunk configuration and dial plan to be associated with the newly defined trunk(s) defined in the Topology Document between the VIS and all Video Gateways.</span></span> <span data-ttu-id="3707d-111">Все эти параметры можно установить на уровнях Global, Site или Service (Video Gateway).</span><span class="sxs-lookup"><span data-stu-id="3707d-111">All these settings can be set at the Global, Site, or service (Video Gateway) levels.</span></span> 
  
<span data-ttu-id="3707d-112">Для развертывания Skype для бизнеса Server создается наборная программа с глобальной областью.</span><span class="sxs-lookup"><span data-stu-id="3707d-112">A dial plan with global scope is created per Skype for Business Server deployment.</span></span> <span data-ttu-id="3707d-113">Эта шкала применяется VIS для всех магистральных телефонов, у которых нет какой-либо телефонной программы с более определенной областью.</span><span class="sxs-lookup"><span data-stu-id="3707d-113">This dial plan is applied by VIS to all trunks which do not have any dial plan with more specific scope.</span></span> 
  
### <a name="configure-the-vis-using-windows-powershell"></a><span data-ttu-id="3707d-114">Настройка VIS с помощью Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="3707d-114">Configure the VIS using Windows PowerShell</span></span>

1. <span data-ttu-id="3707d-115">Создайте новую конфигурацию магистрали видео (набор параметров), которая будет использовать в магистрали между диспетчером единой связи VIS и Cisco (CallManager или CUCM), используя следующий Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="3707d-115">Create a new video trunk configuration (a collection of settings) to use on the trunk between the VIS and Cisco Unified Communications Manager (CallManager, or CUCM), using the following Windows PowerShell cmdlet:</span></span>
    
   ```powershell
   New-CsVideoTrunkConfiguration -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com" -GatewaySendsRtcpForActiveCalls $false -GatewaySendsRtcpForCallsOnHold $false -EnableMediaEncryptionForSipOverTls $true(or $false)
   ```

    <span data-ttu-id="3707d-116">Если имеется существующий магистраль видео, который необходимо изменить, используйте следующий Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3707d-116">If there is an existing video trunk that needs to be modified, use the following Windows PowerShell cmdlet:</span></span>
    
   ```powershell
   Set-CsVideoTrunkConfiguration -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com" -GatewaySendsRtcpForActiveCalls $false -GatewaySendsRtcpForCallsOnHold $false -EnableMediaEncryptionForSipOverTls  $true(or $false)
   ```

    <span data-ttu-id="3707d-117">Чтобы просмотреть параметры, связанные с определенной конфигурацией магистрали видео, используйте следующий Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="3707d-117">To view the settings associated with a particular video trunk configuration, use the following Windows PowerShell cmdlet:</span></span>
    
   ```powershell
   Get-CsVideoTrunkConfiguration -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com"
   ```

    <span data-ttu-id="3707d-118">Чтобы удалить определенную конфигурацию магистрали видео, используйте следующий Windows PowerShell (обратите внимание, что глобально масштабная конфигурация магистрали видео будет применяться, если не существует более конкретной конфигурации магистрали видео для определенного магистраля):</span><span class="sxs-lookup"><span data-stu-id="3707d-118">To remove a particular video trunk configuration, use the following Windows PowerShell cmdlet (note that the globally scoped video trunk configuration will be applied if there is not a more specifically scoped video trunk configuration for a particular trunk):</span></span>
    
   ```powershell
   Remove-CsVideoTrunkConfiguration -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com"
   ```

2. <span data-ttu-id="3707d-119">Создайте план набора для связи с магистралью, используя следующие Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="3707d-119">Establish a dial plan to associate with the trunk, using the following Windows PowerShell cmdlets:</span></span>
    
   ```powershell
   New-CsDialPlan -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com" -SimpleName "TrunkTestDialPlan" 
   New-CsVoiceNormalizationRule -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com/SevenDigitRule" -Pattern '^(\d{7})$' -Translation '+1425$1' 
   Get-CsDialPlan -Identity "Service:CUCMVIS1.CUCMInterop.contoso.com"
   Remove-CsVoiceNormalizationRule -Identity  "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com/Keep All"
   ```

<span data-ttu-id="3707d-120">Команда **Remove-CsVoiceNormalizationRule** необходима для переопределения правила по умолчанию, которое будет мешать ожидаемому взаимодействию VIS и CUCM.</span><span class="sxs-lookup"><span data-stu-id="3707d-120">The **Remove-CsVoiceNormalizationRule** command is needed to override a default rule that will interfere with the expected VIS and CUCM interaction.</span></span>
> [!NOTE]
> <span data-ttu-id="3707d-121">[Remove-CsDialPlan](/powershell/module/skype/remove-csdialplan?view=skype-ps) можно использовать для удаления набора номера.</span><span class="sxs-lookup"><span data-stu-id="3707d-121">[Remove-CsDialPlan](/powershell/module/skype/remove-csdialplan?view=skype-ps) can be used to remove a dial plan.</span></span>
  
<span data-ttu-id="3707d-122">Для вызова магистрали видео SIP из видео шлюза, у которого URI запроса содержит номер, не связанный с E.164, VIS будет читать имя плана набора, связанного с связанным магистралью, и будет включать имя плана набора в контекстной части телефона URI запроса в приглашении, которое VIS отправляет в переднюю часть.</span><span class="sxs-lookup"><span data-stu-id="3707d-122">For a video SIP Trunk call from a Video Gateway whose Request URI contains a non-E.164 number, VIS will read the name of the dial plan associated with the associated trunk, and will include the dial plan name in the phone context part of the Request URI in the Invite that VIS sends to the Front End.</span></span> <span data-ttu-id="3707d-123">Приложение для перевода на переднем конце извлекает и применяет правила нормализации, связанные с телефонной линией, к URI запроса.</span><span class="sxs-lookup"><span data-stu-id="3707d-123">The Translation Application on the Front End then extracts and applies the normalization rules associated with the dial plan to the Request URI.</span></span>
## <a name="trunk-configuration-options"></a><span data-ttu-id="3707d-124">Параметры конфигурации магистрали</span><span class="sxs-lookup"><span data-stu-id="3707d-124">Trunk configuration options</span></span>

<span data-ttu-id="3707d-125">Эти Windows PowerShell для конфигурации магистрали видео, упомянутые ранее, были новыми для Skype для бизнеса Server 2015.</span><span class="sxs-lookup"><span data-stu-id="3707d-125">The Windows PowerShell cmdlets for video trunk configuration mentioned previously were new to Skype for Business Server 2015.</span></span> <span data-ttu-id="3707d-126">Параметры, связанные с конфигурацией магистрали видео, требуют краткого объяснения.</span><span class="sxs-lookup"><span data-stu-id="3707d-126">The settings associated with video trunk configuration require a brief explanation.</span></span>
  
 <span data-ttu-id="3707d-127">**GatewaySendsRtcpForActiveCalls** Этот параметр определяет, отправляются ли пакеты RTCP из ВТС в VIS для активных вызовов.</span><span class="sxs-lookup"><span data-stu-id="3707d-127">**GatewaySendsRtcpForActiveCalls** This parameter determines whether RTCP packets are sent from the VTC to the VIS for active calls.</span></span> <span data-ttu-id="3707d-128">В этом контексте активным вызовом является вызов, в котором разрешается передавать мультимедиа хотя бы в одном направлении.</span><span class="sxs-lookup"><span data-stu-id="3707d-128">An active call in this context is a call where media is allowed to flow in at least one direction.</span></span> <span data-ttu-id="3707d-129">Если в GatewaySendsRtcpForActiveCalls установлено true, VIS может прекратить вызов, если он не получает пакеты RTCP в течение более 30 секунд.</span><span class="sxs-lookup"><span data-stu-id="3707d-129">If GatewaySendsRtcpForActiveCalls is set to True, VIS can terminate a call if it does not receive RTCP packets for a period exceeding 30 seconds.</span></span> <span data-ttu-id="3707d-130">По умолчанию используется значение **True**.</span><span class="sxs-lookup"><span data-stu-id="3707d-130">The default is **True**.</span></span>
  
 <span data-ttu-id="3707d-131">**GatewaySendsRtcpForCallsOnHold** Этот параметр определяет, будут ли пакеты RTCP по-прежнему отправлены по магистрали для вызовов, которые были помещены на удержание, и не ожидается, что пакеты мультимедиа будут поступать в любом направлении.</span><span class="sxs-lookup"><span data-stu-id="3707d-131">**GatewaySendsRtcpForCallsOnHold** This parameter determines whether RTCP packets continue to be sent across the trunk for calls that have been placed on hold and no media packets are expected to flow in either direction.</span></span> <span data-ttu-id="3707d-132">VIS может прекратить вызов, если пакеты RTCP не будут поступать из ВТС в VIS во время удержания вызова.</span><span class="sxs-lookup"><span data-stu-id="3707d-132">VIS can terminate the call, if there are no RTCP packets flowing from the VTC to VIS while the call is on Hold.</span></span> <span data-ttu-id="3707d-133">По умолчанию используется значение **True**.</span><span class="sxs-lookup"><span data-stu-id="3707d-133">The default is **True**.</span></span> <span data-ttu-id="3707d-134">Если протокол SIPTransport заданной для TCP, этот параметр игнорируется.</span><span class="sxs-lookup"><span data-stu-id="3707d-134">When the SIPTransport protocol is set to TCP, this setting is ignored.</span></span>
  
 <span data-ttu-id="3707d-135">**EnableMediaEncryptionForSipOverTls** Этот параметр включает или отключает SRTP для мультимедиа при задании протокола SIPTransport к TLS.</span><span class="sxs-lookup"><span data-stu-id="3707d-135">**EnableMediaEncryptionForSipOverTls** This parameter enables or disables SRTP for media when the SIPTransport protocol is set to TLS.</span></span> <span data-ttu-id="3707d-136">По умолчанию используется значение **True**.</span><span class="sxs-lookup"><span data-stu-id="3707d-136">The default is **True**.</span></span> <span data-ttu-id="3707d-137">Если протокол SIPTransport заданной для TCP, этот параметр игнорируется.</span><span class="sxs-lookup"><span data-stu-id="3707d-137">When the SIPTransport protocol is set to TCP, this setting is ignored.</span></span>
  
 <span data-ttu-id="3707d-138">**EnableSessionTimer** Этот параметр включает или отключает время сеанса на стороне VIS для каждого диалоговика SIP, связанного с магистралью SIP видео.</span><span class="sxs-lookup"><span data-stu-id="3707d-138">**EnableSessionTimer** This parameter enables or disables session timers on the VIS side for each SIP dialog associated with the video SIP trunk.</span></span> <span data-ttu-id="3707d-139">Значение по умолчанию - **false**.</span><span class="sxs-lookup"><span data-stu-id="3707d-139">The default is **False**.</span></span>
  
 <span data-ttu-id="3707d-140">**ForwardErrorCorrectionType** Этот параметр используется для определения того, следует ли применять исправление ошибок вперед (FEC) для видеопотоков на ноге между сервером видеосвязи и шлюзом видео.</span><span class="sxs-lookup"><span data-stu-id="3707d-140">**ForwardErrorCorrectionType** This parameter is used to determine if Forward Error Correction (FEC) for video streams is to be applied on the leg between the Video Interop Server and a Video Gateway.</span></span> <span data-ttu-id="3707d-141">Настройка ForwardErrorCorrectionType на "Нет" отключит FEC между VIS и видео шлюзом/VTC.</span><span class="sxs-lookup"><span data-stu-id="3707d-141">Setting ForwardErrorCorrectionType to "None" turns off FEC between VIS and Video Gateway/VTC.</span></span> <span data-ttu-id="3707d-142">Настройка ForwardErrorCorrectionType в "Cisco" позволяет FEC совместим с видео шлюзами Cisco, такими как Cisco Unified Communications Manager (CUCM).</span><span class="sxs-lookup"><span data-stu-id="3707d-142">Setting ForwardErrorCorrectionType to "Cisco" enables FEC compatible with Video Gateways by Cisco, such as Cisco Unified Communications Manager (CUCM).</span></span> <span data-ttu-id="3707d-143">По умолчанию **нет**.</span><span class="sxs-lookup"><span data-stu-id="3707d-143">The default is **None**.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="3707d-144">См. также</span><span class="sxs-lookup"><span data-stu-id="3707d-144">See also</span></span>

[<span data-ttu-id="3707d-145">Настройка CUCM для межоперации с помощью Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="3707d-145">Configure CUCM for Interoperation with Skype for Business Server</span></span>](configure-cucm-for-interoperation.md)