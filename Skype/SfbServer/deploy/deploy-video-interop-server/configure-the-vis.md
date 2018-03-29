---
title: Настройка VIS в Skype для бизнеса Server 2015
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 0fde142b-70b1-46c6-b1f9-f9d70115371d
description: 'Сводка: Настройка ролей сервера взаимодействия видео (VIS) в Скайп для Business Server 2015.'
ms.openlocfilehash: 7192135f5822e3086de7533afbdc8492194a3889
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/28/2018
---
# <a name="configure-the-video-interop-server-in-skype-for-business-server-2015"></a><span data-ttu-id="14b8b-103">Настройка VIS в Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="14b8b-103">Configure the Video Interop Server in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="14b8b-104">**Сводка:** Настройка ролей сервера взаимодействия видео (VIS) в Скайп для Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="14b8b-104">**Summary:** Configure the Video Interop Server (VIS) role in Skype for Business Server 2015.</span></span>
  
 <span data-ttu-id="14b8b-105">Настройте параметры, которые VIS будет связать с видео магистральных линий связи, с помощью Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="14b8b-105">Configure the settings that the VIS will associate with video trunks using Windows PowerShell.</span></span> <span data-ttu-id="14b8b-106">Конфигурация видеомагистралей с глобальной областью действия создается после установки службы VIS.</span><span class="sxs-lookup"><span data-stu-id="14b8b-106">A video trunk configuration with global scope is created once the VIS service is installed.</span></span> <span data-ttu-id="14b8b-107">Эта конфигурация видеомагистралей посредством VIS применяется ко всем магистралям, для которых не задана конфигурация видеомагистралей с более узкой областью действия.</span><span class="sxs-lookup"><span data-stu-id="14b8b-107">This video trunk configuration is applied by the VIS to all trunks which do not have video trunk configuration with a more specific scope.</span></span> <span data-ttu-id="14b8b-108">Следует учитывать, что конфигурация видеомагистралей представляет собой набор параметров, применимых к видеомагистралям.</span><span class="sxs-lookup"><span data-stu-id="14b8b-108">Note that the video trunk configuration is a collection of settings that is applicable to video trunks.</span></span>
  
## <a name="configure-video-trunk-and-dial-plan"></a><span data-ttu-id="14b8b-109">Настройка видеомагистрали и абонентской группы</span><span class="sxs-lookup"><span data-stu-id="14b8b-109">Configure video trunk and dial plan</span></span>

<span data-ttu-id="14b8b-110">Используйте следующие команды Windows PowerShell, чтобы указать Настройка видео линии связи и абонентская группа планирования должен быть связан с недавно определенной trunk(s), определенным в документе топологии между VIS и все шлюзы видео.</span><span class="sxs-lookup"><span data-stu-id="14b8b-110">Use the following Windows PowerShell commands to specify the video trunk configuration and dial plan to be associated with the newly defined trunk(s) defined in the Topology Document between the VIS and all Video Gateways.</span></span> <span data-ttu-id="14b8b-111">Все эти параметры могут быть заданы на глобальном уровне, уровне сайта или уровне службы (видеошлюза).</span><span class="sxs-lookup"><span data-stu-id="14b8b-111">All these settings can be set at the Global, Site, or service (Video Gateway) levels.</span></span> 
  
<span data-ttu-id="14b8b-112">Для развертывания сервера Business каждого Скайп создается абонентской группы с глобальной областью действия.</span><span class="sxs-lookup"><span data-stu-id="14b8b-112">A dial plan with global scope is created per Skype for Business Server deployment.</span></span> <span data-ttu-id="14b8b-113">Эта абонентская группа посредством VIS применяется ко всем магистралям, для которых не задана абонентская группа с более узкой областью действия.</span><span class="sxs-lookup"><span data-stu-id="14b8b-113">This dial plan is applied by VIS to all trunks which do not have any dial plan with more specific scope.</span></span> 
  
### <a name="configure-the-vis-using-windows-powershell"></a><span data-ttu-id="14b8b-114">Настройка VIS, с помощью Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="14b8b-114">Configure the VIS using Windows PowerShell</span></span>

1. <span data-ttu-id="14b8b-115">Создание новой конфигурации магистрали видео (набор параметров) для использования на линии связи между VIS и CUCM, с помощью следующего командлета Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="14b8b-115">Create a new video trunk configuration (a collection of settings) to use on the trunk between the VIS and CUCM, using the following Windows PowerShell cmdlet:</span></span>
    
   ```
   New-CsVideoTrunkConfiguration -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com" -GatewaySendsRtcpForActiveCalls $false -GatewaySendsRtcpForCallsOnHold $false -EnableMediaEncryptionForSipOverTls $true(or $false)
   ```

    <span data-ttu-id="14b8b-116">Если имеется существующий видео линии связи, который необходимо изменить, используйте следующий командлет Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="14b8b-116">If there is an existing video trunk that needs to be modified, use the following Windows PowerShell cmdlet:</span></span>
    
   ```
   Set-CsVideoTrunkConfiguration -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com" -GatewaySendsRtcpForActiveCalls $false -GatewaySendsRtcpForCallsOnHold $false -EnableMediaEncryptionForSipOverTls  $true(or $false)
   ```

    <span data-ttu-id="14b8b-117">Чтобы просмотреть параметры, связанные с настройкой конкретной линии видео, используйте следующий командлет Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="14b8b-117">To view the settings associated with a particular video trunk configuration, use the following Windows PowerShell cmdlet:</span></span>
    
   ```
   Get-CsVideoTrunkConfiguration -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com"
   ```

    <span data-ttu-id="14b8b-118">Чтобы удалить конфигурацию конкретной линии видео, используйте следующий командлет Windows PowerShell (Обратите внимание на то, что конфигурация магистрали с глобальной областью видео будет использоваться, если не более конкретно с областью видео магистральной конфигурации для конкретной линии):</span><span class="sxs-lookup"><span data-stu-id="14b8b-118">To remove a particular video trunk configuration, use the following Windows PowerShell cmdlet (note that the globally scoped video trunk configuration will be applied if there is not a more specifically scoped video trunk configuration for a particular trunk):</span></span>
    
   ```
   Remove-CsVideoTrunkConfiguration -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com"
   ```

2. <span data-ttu-id="14b8b-119">Создание абонентской следует связать с магистралью, с помощью следующих командлетов Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="14b8b-119">Establish a dial plan to associate with the trunk, using the following Windows PowerShell cmdlets:</span></span>
    
   ```
   New-CsDialPlan -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com" -SimpleName "TrunkTestDialPlan" 
   New-CsVoiceNormalizationRule -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com/SevenDigitRule" -Pattern '^(\d{7})$' -Translation '+1425$1' 
   Get-CsDialPlan -Identity "Service:CUCMVIS1.CUCMInterop.contoso.com"
   Remove-CsVoiceNormalizationRule -Identity  "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com/Keep All"
   ```

<span data-ttu-id="14b8b-120">Команда **Remove-CsVoiceNormalizationRule** необходима для переопределения правила по умолчанию, которое нарушало бы ожидаемое взаимодействие между VIS и CUCM.</span><span class="sxs-lookup"><span data-stu-id="14b8b-120">The **Remove-CsVoiceNormalizationRule** command is needed to override a default rule that will interfere with the expected VIS and CUCM interaction.</span></span>
> [!NOTE]
> <span data-ttu-id="14b8b-121">[Remove-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/remove-csdialplan?view=skype-ps) используется для удаления абонентской группы.</span><span class="sxs-lookup"><span data-stu-id="14b8b-121">[Remove-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/remove-csdialplan?view=skype-ps) can be used to remove a dial plan.</span></span>
  
<span data-ttu-id="14b8b-122">Для SIP-магистрали видеозвонка от видео шлюза, чей URI запроса содержит номер не E.164 будет считывать имя абонентской, связанные с сопоставленном VIS, а в контексте телефона часть URI запроса в приглашении, VI будут включены имя абонентской группы S отправляет на сервере переднего плана.</span><span class="sxs-lookup"><span data-stu-id="14b8b-122">For a video SIP Trunk call from a Video Gateway whose Request URI contains a non-E.164 number, VIS will read the name of the dial plan associated with the associated trunk, and will include the dial plan name in the phone context part of the Request URI in the Invite that VIS sends to the Front End.</span></span> <span data-ttu-id="14b8b-123">Затем в приложении трансляции на сервере переднего плана извлекаются связанные с абонентской группой правила нормализации для их применения к идентификатору URI запроса.</span><span class="sxs-lookup"><span data-stu-id="14b8b-123">The Translation Application on the Front End then extracts and applies the normalization rules associated with the dial plan to the Request URI.</span></span>
## <a name="trunk-configuration-options"></a><span data-ttu-id="14b8b-124">Варианты конфигурации магистралей</span><span class="sxs-lookup"><span data-stu-id="14b8b-124">Trunk configuration options</span></span>

<span data-ttu-id="14b8b-125">Командлеты Windows PowerShell для настройки видео магистрали, указанным выше появились в Скайп для Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="14b8b-125">The Windows PowerShell cmdlets for video trunk configuration mentioned previously are new to the Skype for Business Server 2015.</span></span> <span data-ttu-id="14b8b-126">Параметры, связанные с конфигурацией видеомагистрали, требуют краткого пояснения.</span><span class="sxs-lookup"><span data-stu-id="14b8b-126">The settings associated with video trunk configuration require a brief explanation.</span></span>
  
 <span data-ttu-id="14b8b-127">**GatewaySendsRtcpForActiveCalls** Этот параметр определяет ли RTCP пакеты, отправляются из VTC VIS для активных звонков.</span><span class="sxs-lookup"><span data-stu-id="14b8b-127">**GatewaySendsRtcpForActiveCalls** This parameter determines whether RTCP packets are sent from the VTC to the VIS for active calls.</span></span> <span data-ttu-id="14b8b-128">В данном контексте активным считается вызов, для которого хотя бы в одном направлении разрешен поток мультимедийных данных.</span><span class="sxs-lookup"><span data-stu-id="14b8b-128">An active call in this context is a call where media is allowed to flow in at least one direction.</span></span> <span data-ttu-id="14b8b-129">Если для параметра GatewaySendsRtcpForActiveCalls задано значение True, а на VIS в течение периода, превышающего 30 секунд, не принят ни один пакет RTCP, вызов завершается.</span><span class="sxs-lookup"><span data-stu-id="14b8b-129">If GatewaySendsRtcpForActiveCalls is set to True, VIS can terminate a call if it does not receive RTCP packets for a period exceeding 30 seconds.</span></span> <span data-ttu-id="14b8b-130">По умолчанию задано значение **True**.</span><span class="sxs-lookup"><span data-stu-id="14b8b-130">The default is **True**.</span></span>
  
 <span data-ttu-id="14b8b-131">**GatewaySendsRtcpForCallsOnHold** Этот параметр определяет, пакеты RTCP продолжить передаваемых по линии связи для вызовов, которые были размещены на удержание и не пакетов мультимедиа должны проходить в обоих направлениях.</span><span class="sxs-lookup"><span data-stu-id="14b8b-131">**GatewaySendsRtcpForCallsOnHold** This parameter determines whether RTCP packets continue to be sent across the trunk for calls that have been placed on hold and no media packets are expected to flow in either direction.</span></span> <span data-ttu-id="14b8b-132">Если в режиме удержания вызова поток пакетов RTCP из VTC на VIS отсутствует, вызов может быть завершен средствами VIS.</span><span class="sxs-lookup"><span data-stu-id="14b8b-132">VIS can terminate the call, if there are no RTCP packets flowing from the VTC to VIS while the call is on Hold.</span></span> <span data-ttu-id="14b8b-133">По умолчанию задано значение **True**.</span><span class="sxs-lookup"><span data-stu-id="14b8b-133">The default is **True**.</span></span> <span data-ttu-id="14b8b-134">Этот параметр игнорируется, если в качестве транспортного протокола SIP задан протокол TCP.</span><span class="sxs-lookup"><span data-stu-id="14b8b-134">When the SIPTransport protocol is set to TCP, this setting is ignored.</span></span>
  
 <span data-ttu-id="14b8b-135">**EnableMediaEncryptionForSipOverTls** Этот параметр включает или отключает SRTP для мультимедиа, если протокол SIPTransport задано значение TLS.</span><span class="sxs-lookup"><span data-stu-id="14b8b-135">**EnableMediaEncryptionForSipOverTls** This parameter enables or disables SRTP for media when the SIPTransport protocol is set to TLS.</span></span> <span data-ttu-id="14b8b-136">По умолчанию задано значение **True**.</span><span class="sxs-lookup"><span data-stu-id="14b8b-136">The default is **True**.</span></span> <span data-ttu-id="14b8b-137">Этот параметр игнорируется, если в качестве транспортного протокола SIP задан протокол TCP.</span><span class="sxs-lookup"><span data-stu-id="14b8b-137">When the SIPTransport protocol is set to TCP, this setting is ignored.</span></span>
  
 <span data-ttu-id="14b8b-138">**EnableSessionTimer** Этот параметр включает или отключает таймеры сеанса на стороне VIS для каждого диалогового окна SIP, связанный с видео канала SIP.</span><span class="sxs-lookup"><span data-stu-id="14b8b-138">**EnableSessionTimer** This parameter enables or disables session timers on the VIS side for each SIP dialog associated with the video SIP trunk.</span></span> <span data-ttu-id="14b8b-139">По умолчанию задано значение **False**.</span><span class="sxs-lookup"><span data-stu-id="14b8b-139">The default is **False**.</span></span>
  
 <span data-ttu-id="14b8b-140">**ForwardErrorCorrectionType** Этот параметр используется для определения переадресовывать ошибка коррекции (FEC) для потоковое видео для применения на ветвь между сервером видео взаимодействия и видео шлюза.</span><span class="sxs-lookup"><span data-stu-id="14b8b-140">**ForwardErrorCorrectionType** This parameter is used to determine if Forward Error Correction (FEC) for video streams is to be applied on the leg between the Video Interop Server and a Video Gateway.</span></span> <span data-ttu-id="14b8b-141">Параметр ForwardErrorCorrectionType значение «None» отключает FEC между VIS и видео шлюза/VTC.</span><span class="sxs-lookup"><span data-stu-id="14b8b-141">Setting ForwardErrorCorrectionType to "None" turns off FEC between VIS and Video Gateway/VTC.</span></span> <span data-ttu-id="14b8b-142">Установка ForwardErrorCorrectionType для «Cisco» позволяет FEC, совместимый с видео шлюзы, Cisco, таких как Cisco объединенных коммуникаций Manager (CUCM).</span><span class="sxs-lookup"><span data-stu-id="14b8b-142">Setting ForwardErrorCorrectionType to "Cisco" enables FEC compatible with Video Gateways by Cisco, such as Cisco Unified Communications Manager (CUCM).</span></span> <span data-ttu-id="14b8b-143">По умолчанию задано значение **Нет**.</span><span class="sxs-lookup"><span data-stu-id="14b8b-143">The default is **None**.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="14b8b-144">См. также</span><span class="sxs-lookup"><span data-stu-id="14b8b-144">See also</span></span>

#### 

[<span data-ttu-id="14b8b-145">Настройка CUCM для взаимодействия с Скайп для Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="14b8b-145">Configure CUCM for Interoperation with Skype for Business Server 2015</span></span>](configure-cucm-for-interoperation.md)

