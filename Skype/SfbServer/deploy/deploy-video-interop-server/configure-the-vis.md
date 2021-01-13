---
title: Настройка сервера видеосвязи в Skype для бизнеса Server
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
description: Сводка. Настройка роли сервера видеосвязи (VIS) в Skype для бизнеса Server.
ms.openlocfilehash: 84ab821249ae388bc1ba0dc41cb980c90d4f0853
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49820699"
---
# <a name="configure-the-video-interop-server-in-skype-for-business-server"></a><span data-ttu-id="f2721-103">Настройка сервера видеосвязи в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="f2721-103">Configure the Video Interop Server in Skype for Business Server</span></span>
 
<span data-ttu-id="f2721-104">**Сводка:** Настройте роль сервера video interop Server (VIS) в Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="f2721-104">**Summary:** Configure the Video Interop Server (VIS) role in Skype for Business Server.</span></span>
  
 <span data-ttu-id="f2721-105">Настройте параметры, которые VIS будет связывать с видеомагольниками с помощью Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f2721-105">Configure the settings that the VIS will associate with video trunks using Windows PowerShell.</span></span> <span data-ttu-id="f2721-106">После установки службы VIS создается конфигурация видеоманкетов с глобальной областью действия.</span><span class="sxs-lookup"><span data-stu-id="f2721-106">A video trunk configuration with global scope is created once the VIS service is installed.</span></span> <span data-ttu-id="f2721-107">Эта конфигурация видеомафигуры применяется VIS для всех магистральных магистрали, которые не имеют конфигурации видеомаголи с более конкретной областью действия.</span><span class="sxs-lookup"><span data-stu-id="f2721-107">This video trunk configuration is applied by the VIS to all trunks which do not have video trunk configuration with a more specific scope.</span></span> <span data-ttu-id="f2721-108">Обратите внимание, что конфигурация видеомайлов — это коллекция параметров, применимых к видеомагольникам.</span><span class="sxs-lookup"><span data-stu-id="f2721-108">Note that the video trunk configuration is a collection of settings that is applicable to video trunks.</span></span>
  
## <a name="configure-video-trunk-and-dial-plan"></a><span data-ttu-id="f2721-109">Настройка видеомаголи и телефонной плана</span><span class="sxs-lookup"><span data-stu-id="f2721-109">Configure video trunk and dial plan</span></span>

<span data-ttu-id="f2721-110">Используйте следующие Windows PowerShell, чтобы указать конфигурацию видеомайлов и телефонную связь, которые должны быть связаны с новыми магистральными магистральми, определенными в документе топологии между VIS и всеми видео шлюзами.</span><span class="sxs-lookup"><span data-stu-id="f2721-110">Use the following Windows PowerShell commands to specify the video trunk configuration and dial plan to be associated with the newly defined trunk(s) defined in the Topology Document between the VIS and all Video Gateways.</span></span> <span data-ttu-id="f2721-111">Все эти параметры можно установить на глобальном уровне, уровне сайта или службы (видео шлюза).</span><span class="sxs-lookup"><span data-stu-id="f2721-111">All these settings can be set at the Global, Site, or service (Video Gateway) levels.</span></span> 
  
<span data-ttu-id="f2721-112">Для каждого развертывания Skype для бизнеса Server создается dial plan с глобальной областью действия.</span><span class="sxs-lookup"><span data-stu-id="f2721-112">A dial plan with global scope is created per Skype for Business Server deployment.</span></span> <span data-ttu-id="f2721-113">Эта dial plan is applied by VIS to all trunks which do not have any dial plan with more specific scope.</span><span class="sxs-lookup"><span data-stu-id="f2721-113">This dial plan is applied by VIS to all trunks which do not have any dial plan with more specific scope.</span></span> 
  
### <a name="configure-the-vis-using-windows-powershell"></a><span data-ttu-id="f2721-114">Настройка VIS с помощью Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="f2721-114">Configure the VIS using Windows PowerShell</span></span>

1. <span data-ttu-id="f2721-115">Создайте новую конфигурацию видеомагигании (коллекцию параметров) для использования в магистрали между VIS и Cisco Unified Communications Manager (CallManager или CUCM), используя следующий Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="f2721-115">Create a new video trunk configuration (a collection of settings) to use on the trunk between the VIS and Cisco Unified Communications Manager (CallManager, or CUCM), using the following Windows PowerShell cmdlet:</span></span>
    
   ```powershell
   New-CsVideoTrunkConfiguration -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com" -GatewaySendsRtcpForActiveCalls $false -GatewaySendsRtcpForCallsOnHold $false -EnableMediaEncryptionForSipOverTls $true(or $false)
   ```

    <span data-ttu-id="f2721-116">Если требуется изменить существующую видеомаголь, используйте следующий Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="f2721-116">If there is an existing video trunk that needs to be modified, use the following Windows PowerShell cmdlet:</span></span>
    
   ```powershell
   Set-CsVideoTrunkConfiguration -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com" -GatewaySendsRtcpForActiveCalls $false -GatewaySendsRtcpForCallsOnHold $false -EnableMediaEncryptionForSipOverTls  $true(or $false)
   ```

    <span data-ttu-id="f2721-117">Чтобы просмотреть параметры, связанные с определенной конфигурацией видеоманкетов, используйте следующий Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="f2721-117">To view the settings associated with a particular video trunk configuration, use the following Windows PowerShell cmdlet:</span></span>
    
   ```powershell
   Get-CsVideoTrunkConfiguration -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com"
   ```

    <span data-ttu-id="f2721-118">Чтобы удалить определенную конфигурацию видеоманкстрали, используйте следующий Windows PowerShell (обратите внимание, что конфигурация видеомайлов с глобальной областью действия будет применяться, если для определенной магистрали нет более конкретной конфигурации видеоманкстрали):</span><span class="sxs-lookup"><span data-stu-id="f2721-118">To remove a particular video trunk configuration, use the following Windows PowerShell cmdlet (note that the globally scoped video trunk configuration will be applied if there is not a more specifically scoped video trunk configuration for a particular trunk):</span></span>
    
   ```powershell
   Remove-CsVideoTrunkConfiguration -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com"
   ```

2. <span data-ttu-id="f2721-119">Создайте dial plan to associate with the trunk, using the following Windows PowerShell cmdlets:</span><span class="sxs-lookup"><span data-stu-id="f2721-119">Establish a dial plan to associate with the trunk, using the following Windows PowerShell cmdlets:</span></span>
    
   ```powershell
   New-CsDialPlan -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com" -SimpleName "TrunkTestDialPlan" 
   New-CsVoiceNormalizationRule -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com/SevenDigitRule" -Pattern '^(\d{7})$' -Translation '+1425$1' 
   Get-CsDialPlan -Identity "Service:CUCMVIS1.CUCMInterop.contoso.com"
   Remove-CsVoiceNormalizationRule -Identity  "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com/Keep All"
   ```

<span data-ttu-id="f2721-120">Команда **Remove-CsVoiceNormalizationRule** необходима для переопределения правила по умолчанию, которое будет мешать ожидаемому взаимодействию VIS и CUCM.</span><span class="sxs-lookup"><span data-stu-id="f2721-120">The **Remove-CsVoiceNormalizationRule** command is needed to override a default rule that will interfere with the expected VIS and CUCM interaction.</span></span>
> [!NOTE]
> <span data-ttu-id="f2721-121">[Remove-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/remove-csdialplan?view=skype-ps) можно использовать для удаления телефонной программы.</span><span class="sxs-lookup"><span data-stu-id="f2721-121">[Remove-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/remove-csdialplan?view=skype-ps) can be used to remove a dial plan.</span></span>
  
<span data-ttu-id="f2721-122">Для видеовызова SIP-магистрали от видеошлюзов, URI запроса которого содержит номер, не отправляемый по номеру E.164, VIS считывает имя телефонной линии, связанной с связанной магистралью, и будет включать имя телефонной линии в контекстную часть URI запроса в приглашении, отправляемом VIS на передний план.</span><span class="sxs-lookup"><span data-stu-id="f2721-122">For a video SIP Trunk call from a Video Gateway whose Request URI contains a non-E.164 number, VIS will read the name of the dial plan associated with the associated trunk, and will include the dial plan name in the phone context part of the Request URI in the Invite that VIS sends to the Front End.</span></span> <span data-ttu-id="f2721-123">Затем приложение перевода на переднем плане извлекает и применяет правила нормализации, связанные с этой телефонной линией, к URI запроса.</span><span class="sxs-lookup"><span data-stu-id="f2721-123">The Translation Application on the Front End then extracts and applies the normalization rules associated with the dial plan to the Request URI.</span></span>
## <a name="trunk-configuration-options"></a><span data-ttu-id="f2721-124">Параметры конфигурации магистрали</span><span class="sxs-lookup"><span data-stu-id="f2721-124">Trunk configuration options</span></span>

<span data-ttu-id="f2721-125">Указанные Windows PowerShell для конфигурации видеоманкетов были впервые в Skype для бизнеса Server 2015.</span><span class="sxs-lookup"><span data-stu-id="f2721-125">The Windows PowerShell cmdlets for video trunk configuration mentioned previously were new to Skype for Business Server 2015.</span></span> <span data-ttu-id="f2721-126">Параметры, связанные с конфигурацией видеоманкетов, требуют краткого пояснения.</span><span class="sxs-lookup"><span data-stu-id="f2721-126">The settings associated with video trunk configuration require a brief explanation.</span></span>
  
 <span data-ttu-id="f2721-127">**GatewaySendsRtcpForActiveCalls** Этот параметр определяет, отправляются ли пакеты RTCP из VTC в VIS для активных вызовов.</span><span class="sxs-lookup"><span data-stu-id="f2721-127">**GatewaySendsRtcpForActiveCalls** This parameter determines whether RTCP packets are sent from the VTC to the VIS for active calls.</span></span> <span data-ttu-id="f2721-128">В этом контексте активным вызовом является вызов, в котором разрешается передавать мультимедиа хотя бы в одном направлении.</span><span class="sxs-lookup"><span data-stu-id="f2721-128">An active call in this context is a call where media is allowed to flow in at least one direction.</span></span> <span data-ttu-id="f2721-129">Если для GatewaySendsRtcpForActiveCalls задано true, VIS может завершить вызов, если он не получает пакеты RTCP в течение периода, превышающий 30 секунд.</span><span class="sxs-lookup"><span data-stu-id="f2721-129">If GatewaySendsRtcpForActiveCalls is set to True, VIS can terminate a call if it does not receive RTCP packets for a period exceeding 30 seconds.</span></span> <span data-ttu-id="f2721-130">По умолчанию используется значение **True**.</span><span class="sxs-lookup"><span data-stu-id="f2721-130">The default is **True**.</span></span>
  
 <span data-ttu-id="f2721-131">**GatewaySendsRtcpForCallsOnHold** Этот параметр определяет, будут ли пакеты RTCP по-прежнему перенаправлены по магистрали для вызовов, помещенных на удержание, и пакеты мультимедиа не будут поступать в любом направлении.</span><span class="sxs-lookup"><span data-stu-id="f2721-131">**GatewaySendsRtcpForCallsOnHold** This parameter determines whether RTCP packets continue to be sent across the trunk for calls that have been placed on hold and no media packets are expected to flow in either direction.</span></span> <span data-ttu-id="f2721-132">ViS может завершить вызов, если пакеты RTCP, которые в настоящее время находятся на удержании, не перетекают из VTC в VIS.</span><span class="sxs-lookup"><span data-stu-id="f2721-132">VIS can terminate the call, if there are no RTCP packets flowing from the VTC to VIS while the call is on Hold.</span></span> <span data-ttu-id="f2721-133">По умолчанию используется значение **True**.</span><span class="sxs-lookup"><span data-stu-id="f2721-133">The default is **True**.</span></span> <span data-ttu-id="f2721-134">Если протокол SIPTransport имеет TCP, этот параметр игнорируется.</span><span class="sxs-lookup"><span data-stu-id="f2721-134">When the SIPTransport protocol is set to TCP, this setting is ignored.</span></span>
  
 <span data-ttu-id="f2721-135">**EnableMediaEncryptionForSipOverTls** Этот параметр включает или отключает SRTP для мультимедиа, если для протокола SIPTransport задан протокол TLS.</span><span class="sxs-lookup"><span data-stu-id="f2721-135">**EnableMediaEncryptionForSipOverTls** This parameter enables or disables SRTP for media when the SIPTransport protocol is set to TLS.</span></span> <span data-ttu-id="f2721-136">По умолчанию используется значение **True**.</span><span class="sxs-lookup"><span data-stu-id="f2721-136">The default is **True**.</span></span> <span data-ttu-id="f2721-137">Если протокол SIPTransport имеет TCP, этот параметр игнорируется.</span><span class="sxs-lookup"><span data-stu-id="f2721-137">When the SIPTransport protocol is set to TCP, this setting is ignored.</span></span>
  
 <span data-ttu-id="f2721-138">**EnableSessionTimer** Этот параметр включает или отключает timers сеанса на стороне VIS для каждого диалоговое окно SIP, связанное с магистралью SIP видео.</span><span class="sxs-lookup"><span data-stu-id="f2721-138">**EnableSessionTimer** This parameter enables or disables session timers on the VIS side for each SIP dialog associated with the video SIP trunk.</span></span> <span data-ttu-id="f2721-139">Значение по умолчанию - **false**.</span><span class="sxs-lookup"><span data-stu-id="f2721-139">The default is **False**.</span></span>
  
 <span data-ttu-id="f2721-140">**ForwardErrorCorrectionType** Этот параметр используется для определения того, следует ли применять для видеопотоков прямое исправление ошибок (FEC) на этапе между сервером видеосвязи и видео шлюзом.</span><span class="sxs-lookup"><span data-stu-id="f2721-140">**ForwardErrorCorrectionType** This parameter is used to determine if Forward Error Correction (FEC) for video streams is to be applied on the leg between the Video Interop Server and a Video Gateway.</span></span> <span data-ttu-id="f2721-141">Если параметр ForwardErrorCorrectionType имеет "None", FEC отключается между VIS и видео шлюзом/VTC.</span><span class="sxs-lookup"><span data-stu-id="f2721-141">Setting ForwardErrorCorrectionType to "None" turns off FEC between VIS and Video Gateway/VTC.</span></span> <span data-ttu-id="f2721-142">Установка параметра ForwardErrorCorrectionType в "Cisco" позволяет службе FEC совместимой с видео шлюзами Cisco, такими как Cisco Unified Communications Manager (CUCM).</span><span class="sxs-lookup"><span data-stu-id="f2721-142">Setting ForwardErrorCorrectionType to "Cisco" enables FEC compatible with Video Gateways by Cisco, such as Cisco Unified Communications Manager (CUCM).</span></span> <span data-ttu-id="f2721-143">Значение по умолчанию **— None**.</span><span class="sxs-lookup"><span data-stu-id="f2721-143">The default is **None**.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="f2721-144">См. также</span><span class="sxs-lookup"><span data-stu-id="f2721-144">See also</span></span>

[<span data-ttu-id="f2721-145">Настройка CUCM для связи со Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="f2721-145">Configure CUCM for Interoperation with Skype for Business Server</span></span>](configure-cucm-for-interoperation.md)
