---
title: Настройка сервера видеосвязи в Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 0fde142b-70b1-46c6-b1f9-f9d70115371d
description: 'Сводка: Настройка роли сервера видеосвязи (ВИС) в Skype для бизнеса Server.'
ms.openlocfilehash: 9ac7b64b33c48bd4010c1431b5c0d658f223599a
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/07/2019
ms.locfileid: "36235685"
---
# <a name="configure-the-video-interop-server-in-skype-for-business-server"></a><span data-ttu-id="229f3-103">Настройка сервера видеосвязи в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="229f3-103">Configure the Video Interop Server in Skype for Business Server</span></span>
 
<span data-ttu-id="229f3-104">**Сводка:** Настройте роль сервера видеосвязи (ВИС) в Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="229f3-104">**Summary:** Configure the Video Interop Server (VIS) role in Skype for Business Server.</span></span>
  
 <span data-ttu-id="229f3-105">Настройте параметры, которые будут связывать ВИС с помощью каналов видеомагистрали с использованием Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="229f3-105">Configure the settings that the VIS will associate with video trunks using Windows PowerShell.</span></span> <span data-ttu-id="229f3-106">Конфигурация видеомагистралей с глобальной областью действия создается после установки службы VIS.</span><span class="sxs-lookup"><span data-stu-id="229f3-106">A video trunk configuration with global scope is created once the VIS service is installed.</span></span> <span data-ttu-id="229f3-107">Эта конфигурация видеомагистралей посредством VIS применяется ко всем магистралям, для которых не задана конфигурация видеомагистралей с более узкой областью действия.</span><span class="sxs-lookup"><span data-stu-id="229f3-107">This video trunk configuration is applied by the VIS to all trunks which do not have video trunk configuration with a more specific scope.</span></span> <span data-ttu-id="229f3-108">Следует учитывать, что конфигурация видеомагистралей представляет собой набор параметров, применимых к видеомагистралям.</span><span class="sxs-lookup"><span data-stu-id="229f3-108">Note that the video trunk configuration is a collection of settings that is applicable to video trunks.</span></span>
  
## <a name="configure-video-trunk-and-dial-plan"></a><span data-ttu-id="229f3-109">Настройка видеомагистрали и абонентской группы</span><span class="sxs-lookup"><span data-stu-id="229f3-109">Configure video trunk and dial plan</span></span>

<span data-ttu-id="229f3-110">Используйте указанные ниже команды Windows PowerShell, чтобы указать конфигурацию и абонентскую магистральную схему, которая должна быть связана с новыми определенными каналами, определенными в документе топологии между ВИС и всеми видеошлюзами.</span><span class="sxs-lookup"><span data-stu-id="229f3-110">Use the following Windows PowerShell commands to specify the video trunk configuration and dial plan to be associated with the newly defined trunk(s) defined in the Topology Document between the VIS and all Video Gateways.</span></span> <span data-ttu-id="229f3-111">Все эти параметры могут быть заданы на глобальном уровне, уровне сайта или уровне службы (видеошлюза).</span><span class="sxs-lookup"><span data-stu-id="229f3-111">All these settings can be set at the Global, Site, or service (Video Gateway) levels.</span></span> 
  
<span data-ttu-id="229f3-112">Для развертывания Skype для бизнеса Server создается абонентская группа с глобальной областью действия.</span><span class="sxs-lookup"><span data-stu-id="229f3-112">A dial plan with global scope is created per Skype for Business Server deployment.</span></span> <span data-ttu-id="229f3-113">Эта абонентская группа посредством VIS применяется ко всем магистралям, для которых не задана абонентская группа с более узкой областью действия.</span><span class="sxs-lookup"><span data-stu-id="229f3-113">This dial plan is applied by VIS to all trunks which do not have any dial plan with more specific scope.</span></span> 
  
### <a name="configure-the-vis-using-windows-powershell"></a><span data-ttu-id="229f3-114">Настройка ВИС с помощью Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="229f3-114">Configure the VIS using Windows PowerShell</span></span>

1. <span data-ttu-id="229f3-115">Создайте новую конфигурацию магистральной видеосвязи (коллекцию параметров) для использования на магистралье между ВИС и Cisco Unified Communications Manager (Каллманажер или КУКМ) с помощью следующего командлета Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="229f3-115">Create a new video trunk configuration (a collection of settings) to use on the trunk between the VIS and Cisco Unified Communications Manager (CallManager, or CUCM), using the following Windows PowerShell cmdlet:</span></span>
    
   ```
   New-CsVideoTrunkConfiguration -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com" -GatewaySendsRtcpForActiveCalls $false -GatewaySendsRtcpForCallsOnHold $false -EnableMediaEncryptionForSipOverTls $true(or $false)
   ```

    <span data-ttu-id="229f3-116">Если вы хотите изменить существующую магистральную схему видео, используйте следующий командлет Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="229f3-116">If there is an existing video trunk that needs to be modified, use the following Windows PowerShell cmdlet:</span></span>
    
   ```
   Set-CsVideoTrunkConfiguration -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com" -GatewaySendsRtcpForActiveCalls $false -GatewaySendsRtcpForCallsOnHold $false -EnableMediaEncryptionForSipOverTls  $true(or $false)
   ```

    <span data-ttu-id="229f3-117">Чтобы просмотреть параметры, связанные с конкретной конфигурацией магистрали видео, используйте следующий командлет Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="229f3-117">To view the settings associated with a particular video trunk configuration, use the following Windows PowerShell cmdlet:</span></span>
    
   ```
   Get-CsVideoTrunkConfiguration -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com"
   ```

    <span data-ttu-id="229f3-118">Чтобы удалить определенную конфигурацию магистрали видео, используйте следующий командлет Windows PowerShell (Обратите внимание на то, что будет применена конфигурация магистральной магистрали с глобальными областями, если для конкретной магистрали не определена особая конфигурация магистральной магистрали).</span><span class="sxs-lookup"><span data-stu-id="229f3-118">To remove a particular video trunk configuration, use the following Windows PowerShell cmdlet (note that the globally scoped video trunk configuration will be applied if there is not a more specifically scoped video trunk configuration for a particular trunk):</span></span>
    
   ```
   Remove-CsVideoTrunkConfiguration -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com"
   ```

2. <span data-ttu-id="229f3-119">Создайте абонентскую группу, которая будет связана с магистрали, используя следующие командлеты Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="229f3-119">Establish a dial plan to associate with the trunk, using the following Windows PowerShell cmdlets:</span></span>
    
   ```
   New-CsDialPlan -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com" -SimpleName "TrunkTestDialPlan" 
   New-CsVoiceNormalizationRule -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com/SevenDigitRule" -Pattern '^(\d{7})$' -Translation '+1425$1' 
   Get-CsDialPlan -Identity "Service:CUCMVIS1.CUCMInterop.contoso.com"
   Remove-CsVoiceNormalizationRule -Identity  "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com/Keep All"
   ```

<span data-ttu-id="229f3-120">Команда **Remove-CsVoiceNormalizationRule** необходима для переопределения правила по умолчанию, которое нарушало бы ожидаемое взаимодействие между VIS и CUCM.</span><span class="sxs-lookup"><span data-stu-id="229f3-120">The **Remove-CsVoiceNormalizationRule** command is needed to override a default rule that will interfere with the expected VIS and CUCM interaction.</span></span>
> [!NOTE]
> <span data-ttu-id="229f3-121">Для удаления абонентской группы можно использовать [Remove-ксдиалплан](https://docs.microsoft.com/powershell/module/skype/remove-csdialplan?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="229f3-121">[Remove-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/remove-csdialplan?view=skype-ps) can be used to remove a dial plan.</span></span>
  
<span data-ttu-id="229f3-122">Для звонков по магистрали видеосвязи с видеошлюза, чей URI запроса содержит номер, отличный от E. 164, ВИС прочтите имя абонентской группы, связанной с соответствующей магистральной каналом, и включит имя абонентской группы в частную часть URI запроса в приглашении VI. S отправляется на интерфейсный сервер.</span><span class="sxs-lookup"><span data-stu-id="229f3-122">For a video SIP Trunk call from a Video Gateway whose Request URI contains a non-E.164 number, VIS will read the name of the dial plan associated with the associated trunk, and will include the dial plan name in the phone context part of the Request URI in the Invite that VIS sends to the Front End.</span></span> <span data-ttu-id="229f3-123">Затем в приложении трансляции на сервере переднего плана извлекаются связанные с абонентской группой правила нормализации для их применения к идентификатору URI запроса.</span><span class="sxs-lookup"><span data-stu-id="229f3-123">The Translation Application on the Front End then extracts and applies the normalization rules associated with the dial plan to the Request URI.</span></span>
## <a name="trunk-configuration-options"></a><span data-ttu-id="229f3-124">Варианты конфигурации магистралей</span><span class="sxs-lookup"><span data-stu-id="229f3-124">Trunk configuration options</span></span>

<span data-ttu-id="229f3-125">Командлеты Windows PowerShell для настройки магистральной видеосвязи, упомянутые ранее, были впервые добавлены в Skype для бизнеса Server 2015.</span><span class="sxs-lookup"><span data-stu-id="229f3-125">The Windows PowerShell cmdlets for video trunk configuration mentioned previously were new to Skype for Business Server 2015.</span></span> <span data-ttu-id="229f3-126">Параметры, связанные с конфигурацией видеомагистрали, требуют краткого пояснения.</span><span class="sxs-lookup"><span data-stu-id="229f3-126">The settings associated with video trunk configuration require a brief explanation.</span></span>
  
 <span data-ttu-id="229f3-127">**Гатевайсендсрткпфорактивекаллс** Этот параметр определяет, отправляются ли пакеты РТКП из ВТК в ВИС для активных звонков.</span><span class="sxs-lookup"><span data-stu-id="229f3-127">**GatewaySendsRtcpForActiveCalls** This parameter determines whether RTCP packets are sent from the VTC to the VIS for active calls.</span></span> <span data-ttu-id="229f3-128">В данном контексте активным считается вызов, для которого хотя бы в одном направлении разрешен поток мультимедийных данных.</span><span class="sxs-lookup"><span data-stu-id="229f3-128">An active call in this context is a call where media is allowed to flow in at least one direction.</span></span> <span data-ttu-id="229f3-129">Если для параметра GatewaySendsRtcpForActiveCalls задано значение True, а на VIS в течение периода, превышающего 30 секунд, не принят ни один пакет RTCP, вызов завершается.</span><span class="sxs-lookup"><span data-stu-id="229f3-129">If GatewaySendsRtcpForActiveCalls is set to True, VIS can terminate a call if it does not receive RTCP packets for a period exceeding 30 seconds.</span></span> <span data-ttu-id="229f3-130">По умолчанию задано значение **True**.</span><span class="sxs-lookup"><span data-stu-id="229f3-130">The default is **True**.</span></span>
  
 <span data-ttu-id="229f3-131">**Гатевайсендсрткпфоркаллсонхолд** Этот параметр определяет, должны ли пакеты РТКП по каналу обмена для вызовов, размещенных на удержании, а также при отсутствии пакетов мультимедиа, которые должны передаваться в любом направлении.</span><span class="sxs-lookup"><span data-stu-id="229f3-131">**GatewaySendsRtcpForCallsOnHold** This parameter determines whether RTCP packets continue to be sent across the trunk for calls that have been placed on hold and no media packets are expected to flow in either direction.</span></span> <span data-ttu-id="229f3-132">Если в режиме удержания вызова поток пакетов RTCP из VTC на VIS отсутствует, вызов может быть завершен средствами VIS.</span><span class="sxs-lookup"><span data-stu-id="229f3-132">VIS can terminate the call, if there are no RTCP packets flowing from the VTC to VIS while the call is on Hold.</span></span> <span data-ttu-id="229f3-133">По умолчанию задано значение **True**.</span><span class="sxs-lookup"><span data-stu-id="229f3-133">The default is **True**.</span></span> <span data-ttu-id="229f3-134">Этот параметр игнорируется, если в качестве транспортного протокола SIP задан протокол TCP.</span><span class="sxs-lookup"><span data-stu-id="229f3-134">When the SIPTransport protocol is set to TCP, this setting is ignored.</span></span>
  
 <span data-ttu-id="229f3-135">**Енаблемедиаенкриптионфорсиповертлс** Этот параметр включает или выключает SRTP для мультимедиа, когда для протокола Сиптранспорт задано значение TLS.</span><span class="sxs-lookup"><span data-stu-id="229f3-135">**EnableMediaEncryptionForSipOverTls** This parameter enables or disables SRTP for media when the SIPTransport protocol is set to TLS.</span></span> <span data-ttu-id="229f3-136">По умолчанию задано значение **True**.</span><span class="sxs-lookup"><span data-stu-id="229f3-136">The default is **True**.</span></span> <span data-ttu-id="229f3-137">Этот параметр игнорируется, если в качестве транспортного протокола SIP задан протокол TCP.</span><span class="sxs-lookup"><span data-stu-id="229f3-137">When the SIPTransport protocol is set to TCP, this setting is ignored.</span></span>
  
 <span data-ttu-id="229f3-138">**Енаблесессионтимер** Этот параметр включает и выключает таймеры сеанса на стороне ВИС для каждого диалогового окна SIP, связанного с каналом SIP.</span><span class="sxs-lookup"><span data-stu-id="229f3-138">**EnableSessionTimer** This parameter enables or disables session timers on the VIS side for each SIP dialog associated with the video SIP trunk.</span></span> <span data-ttu-id="229f3-139">По умолчанию задано значение **False**.</span><span class="sxs-lookup"><span data-stu-id="229f3-139">The default is **False**.</span></span>
  
 <span data-ttu-id="229f3-140">**Форвардерроркорректионтипе** Этот параметр используется для определения того, следует ли применять коррекцию переадресации ошибок (FEC) для видеопотоков в промежутке между сервером видеосвязи и видеошлюзом.</span><span class="sxs-lookup"><span data-stu-id="229f3-140">**ForwardErrorCorrectionType** This parameter is used to determine if Forward Error Correction (FEC) for video streams is to be applied on the leg between the Video Interop Server and a Video Gateway.</span></span> <span data-ttu-id="229f3-141">Установка для Форвардерроркорректионтипе значения "нет" выключает FEC между ВИС и видеошлюзом/ВТК.</span><span class="sxs-lookup"><span data-stu-id="229f3-141">Setting ForwardErrorCorrectionType to "None" turns off FEC between VIS and Video Gateway/VTC.</span></span> <span data-ttu-id="229f3-142">Установка для Форвардерроркорректионтипе значения "Cisco" обеспечивает совместимость FEC с видеошлюзами Cisco, например диспетчер единой системы обмена сообщениями Cisco (КУКМ).</span><span class="sxs-lookup"><span data-stu-id="229f3-142">Setting ForwardErrorCorrectionType to "Cisco" enables FEC compatible with Video Gateways by Cisco, such as Cisco Unified Communications Manager (CUCM).</span></span> <span data-ttu-id="229f3-143">По умолчанию задано значение **Нет**.</span><span class="sxs-lookup"><span data-stu-id="229f3-143">The default is **None**.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="229f3-144">См. также</span><span class="sxs-lookup"><span data-stu-id="229f3-144">See also</span></span>

[<span data-ttu-id="229f3-145">Настройка КУКМ для взаимодействия с Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="229f3-145">Configure CUCM for Interoperation with Skype for Business Server</span></span>](configure-cucm-for-interoperation.md)
