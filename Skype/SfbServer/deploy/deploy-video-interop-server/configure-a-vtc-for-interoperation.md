---
title: Настройка VTC для связи со Skype для бизнеса Server
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
ms.assetid: 1016aed6-99fe-452e-8b20-81c814808c3d
description: Сводка. Настройка устройств VTC для работы со Skype для бизнеса Server.
ms.openlocfilehash: 7697fd9f33a4fece4871b056a05264ece888d357
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49802079"
---
# <a name="configure-a-vtc-for-interoperation-with-skype-for-business-server"></a><span data-ttu-id="40ccc-103">Настройка VTC для связи со Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="40ccc-103">Configure a VTC for Interoperation with Skype for Business Server</span></span>
 
<span data-ttu-id="40ccc-104">**Сводка:** Настройте устройства VTC для работы со Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="40ccc-104">**Summary:** Configure the VTC devices to work with Skype for Business Server.</span></span>
  
<span data-ttu-id="40ccc-105">Необходимо выполнить следующие процедуры настройки конфигурации для каждого VTC, который будет подключаться к серверу VIS Skype для бизнеса через магистраль SIP и видео шлюз Cisco Unified Communications Manager (CallManager или CUCM).</span><span class="sxs-lookup"><span data-stu-id="40ccc-105">You will need to perform the following configuration customization procedures for each VTC that will connect to the Skype for Business VIS server through a SIP trunk and Cisco Unified Communications Manager (CallManager, or CUCM) video gateway.</span></span>
  
<span data-ttu-id="40ccc-106">Описанные здесь параметры предназначены только в качестве примеров настройки CUCM для работы с VIS.</span><span class="sxs-lookup"><span data-stu-id="40ccc-106">The settings described here are meant only as examples of how CUCM can be configured to work with a VIS.</span></span> <span data-ttu-id="40ccc-107">Другие параметры и/или использование альтернативных функций CUCM также можно использовать для достижения такого же результата.</span><span class="sxs-lookup"><span data-stu-id="40ccc-107">Other settings and/or usages of alternate CUCM functionality could also be used to achieve the same result.</span></span> <span data-ttu-id="40ccc-108">Рекомендации по оптимальной конфигурации для конкретного сценария не подразумеваются.</span><span class="sxs-lookup"><span data-stu-id="40ccc-108">No recommendation is implied as to the optimal configuration for a particular scenario.</span></span>
  
### <a name="configure-a-vtc-registered-with-cucm"></a><span data-ttu-id="40ccc-109">Настройка VTC, зарегистрированного с помощью CUCM</span><span class="sxs-lookup"><span data-stu-id="40ccc-109">Configure a VTC registered with CUCM</span></span>

1. <span data-ttu-id="40ccc-110">Войдите на устройство Cisco VTC и перейдите к пункту \> Configuration-System Configuration- \> Provisioning.</span><span class="sxs-lookup"><span data-stu-id="40ccc-110">Log in to the Cisco VTC device and navigate to Configuration-\>System Configuration-\>Provisioning.</span></span>
    
2. <span data-ttu-id="40ccc-111">Проверьте следующие параметры, исправив их по мере необходимости:</span><span class="sxs-lookup"><span data-stu-id="40ccc-111">Verify the following settings, correcting as needed:</span></span> 
    
   |<span data-ttu-id="40ccc-112">**Параметр**</span><span class="sxs-lookup"><span data-stu-id="40ccc-112">**Parameter**</span></span>|<span data-ttu-id="40ccc-113">**Рекомендуемый параметр**</span><span class="sxs-lookup"><span data-stu-id="40ccc-113">**Recommended setting**</span></span>|
   |:-----|:-----|
   |<span data-ttu-id="40ccc-114">Режим предоставления</span><span class="sxs-lookup"><span data-stu-id="40ccc-114">Provisioning Mode</span></span>  <br/> | <span data-ttu-id="40ccc-115">CUCM</span><span class="sxs-lookup"><span data-stu-id="40ccc-115">CUCM</span></span> <br/> |
   |<span data-ttu-id="40ccc-116">Адрес ExternalManager</span><span class="sxs-lookup"><span data-stu-id="40ccc-116">ExternalManager Address</span></span>  <br/> | <span data-ttu-id="40ccc-117">FQDN CUCM</span><span class="sxs-lookup"><span data-stu-id="40ccc-117">CUCM's FQDN</span></span> <br/> |
   | <span data-ttu-id="40ccc-118">Домен ExternalManager</span><span class="sxs-lookup"><span data-stu-id="40ccc-118">ExternalManager Domain</span></span> <br/> |<span data-ttu-id="40ccc-119">Домен CUCM</span><span class="sxs-lookup"><span data-stu-id="40ccc-119">CUCM's domain</span></span>  <br/> |
   
3. <span data-ttu-id="40ccc-120">Перейдите к configuration- \> System Configuration- \> Network.</span><span class="sxs-lookup"><span data-stu-id="40ccc-120">Navigate to Configuration-\>System Configuration-\>Network.</span></span>
    
4. <span data-ttu-id="40ccc-121">Проверьте следующие параметры, исправив их по мере необходимости:</span><span class="sxs-lookup"><span data-stu-id="40ccc-121">Verify the following settings, correcting as needed:</span></span> 
    
   |<span data-ttu-id="40ccc-122">**Параметр**</span><span class="sxs-lookup"><span data-stu-id="40ccc-122">**Parameter**</span></span>|<span data-ttu-id="40ccc-123">**Рекомендуемый параметр**</span><span class="sxs-lookup"><span data-stu-id="40ccc-123">**Recommended setting**</span></span>|
   |:-----|:-----|
   |<span data-ttu-id="40ccc-124">DNS-имя домена</span><span class="sxs-lookup"><span data-stu-id="40ccc-124">DNS Domain Name</span></span>  <br/> | <span data-ttu-id="40ccc-125">Имя домена CUCM</span><span class="sxs-lookup"><span data-stu-id="40ccc-125">CUCM's Domain name</span></span> <br/> |
   |<span data-ttu-id="40ccc-126">Адрес DNS-сервера 1</span><span class="sxs-lookup"><span data-stu-id="40ccc-126">DNS Server 1 Address</span></span>  <br/> | <span data-ttu-id="40ccc-127">нужный адрес DNS-сервера</span><span class="sxs-lookup"><span data-stu-id="40ccc-127">your desired DNS server address</span></span> <br/> |
   
5. <span data-ttu-id="40ccc-128">Перейдите к сайту Configuration- \> System Configuration— \> Network Services.</span><span class="sxs-lookup"><span data-stu-id="40ccc-128">Navigate to Configuration-\>System Configuration-\>Network Services.</span></span> <span data-ttu-id="40ccc-129">Убедитесь, что режим H.323 отключен и режим SIP включен.</span><span class="sxs-lookup"><span data-stu-id="40ccc-129">Ensure that H.323 mode is turned off and SIP mode is turned on.</span></span> 
    
6. <span data-ttu-id="40ccc-130">Эти параметры устанавливаются автоматически при регистрации конечной точки с помощью CUCM.</span><span class="sxs-lookup"><span data-stu-id="40ccc-130">These options are set automatically when the endpoint is registered with CUCM.</span></span> <span data-ttu-id="40ccc-131">Проверьте следующие параметры, исправив их по мере необходимости:</span><span class="sxs-lookup"><span data-stu-id="40ccc-131">Verify the following settings, correcting as needed:</span></span> 
    
   |<span data-ttu-id="40ccc-132">**Параметр**</span><span class="sxs-lookup"><span data-stu-id="40ccc-132">**Parameter**</span></span>|<span data-ttu-id="40ccc-133">**Рекомендуемый параметр**</span><span class="sxs-lookup"><span data-stu-id="40ccc-133">**Recommended setting**</span></span>|
   |:-----|:-----|
   |<span data-ttu-id="40ccc-134">Режим H.323</span><span class="sxs-lookup"><span data-stu-id="40ccc-134">H.323 Mode</span></span>  <br/> | <span data-ttu-id="40ccc-135">Выкл.</span><span class="sxs-lookup"><span data-stu-id="40ccc-135">Off</span></span> <br/> |
   |<span data-ttu-id="40ccc-136">Режим HTTP</span><span class="sxs-lookup"><span data-stu-id="40ccc-136">HTTP Mode</span></span>  <br/> | <span data-ttu-id="40ccc-137">Вкл.</span><span class="sxs-lookup"><span data-stu-id="40ccc-137">On</span></span> <br/> |
   | <span data-ttu-id="40ccc-138">Режим SIP</span><span class="sxs-lookup"><span data-stu-id="40ccc-138">SIP Mode</span></span> <br/> | <span data-ttu-id="40ccc-139">Вкл.</span><span class="sxs-lookup"><span data-stu-id="40ccc-139">On</span></span> <br/> |
   |<span data-ttu-id="40ccc-140">Режим Telnet</span><span class="sxs-lookup"><span data-stu-id="40ccc-140">Telnet Mode</span></span>  <br/> | <span data-ttu-id="40ccc-141">Вкл.</span><span class="sxs-lookup"><span data-stu-id="40ccc-141">On</span></span> <br/> |
   |<span data-ttu-id="40ccc-142">WelcomeText</span><span class="sxs-lookup"><span data-stu-id="40ccc-142">WelcomeText</span></span>  <br/> | <span data-ttu-id="40ccc-143">Вкл.</span><span class="sxs-lookup"><span data-stu-id="40ccc-143">On</span></span> <br/> |
   |<span data-ttu-id="40ccc-144">Режим XMLAPI</span><span class="sxs-lookup"><span data-stu-id="40ccc-144">XMLAPI Mode</span></span>  <br/> | <span data-ttu-id="40ccc-145">Вкл.</span><span class="sxs-lookup"><span data-stu-id="40ccc-145">On</span></span> <br/> |
   
7. <span data-ttu-id="40ccc-146">Перейдите к \> configuration-System Configuration- \> SIP.</span><span class="sxs-lookup"><span data-stu-id="40ccc-146">Navigate to Configuration-\>System Configuration-\>SIP.</span></span>
    
8. <span data-ttu-id="40ccc-147">Проверьте следующие параметры, исправив их по мере необходимости:</span><span class="sxs-lookup"><span data-stu-id="40ccc-147">Verify the following settings, correcting as needed:</span></span> 
    
   |<span data-ttu-id="40ccc-148">**Параметр**</span><span class="sxs-lookup"><span data-stu-id="40ccc-148">**Parameter**</span></span>|<span data-ttu-id="40ccc-149">**Рекомендуемый параметр**</span><span class="sxs-lookup"><span data-stu-id="40ccc-149">**Recommended setting**</span></span>|
   |:-----|:-----|
   |<span data-ttu-id="40ccc-150">Профиль 1 — DefaultTransport</span><span class="sxs-lookup"><span data-stu-id="40ccc-150">Profile 1 - DefaultTransport</span></span>  <br/> | <span data-ttu-id="40ccc-151">TCP</span><span class="sxs-lookup"><span data-stu-id="40ccc-151">TCP</span></span> <br/> |
   |<span data-ttu-id="40ccc-152">Профиль 1 — исходящие данные</span><span class="sxs-lookup"><span data-stu-id="40ccc-152">Profile 1 - Outbound</span></span>  <br/> | <span data-ttu-id="40ccc-153">Выкл.</span><span class="sxs-lookup"><span data-stu-id="40ccc-153">Off</span></span> <br/> |
   |<span data-ttu-id="40ccc-154">Профиль 1 — TlsVerify</span><span class="sxs-lookup"><span data-stu-id="40ccc-154">Profile 1 - TlsVerify</span></span>  <br/> | <span data-ttu-id="40ccc-155">Вкл.</span><span class="sxs-lookup"><span data-stu-id="40ccc-155">On</span></span> <br/> |
   |<span data-ttu-id="40ccc-156">Профиль 1 — тип</span><span class="sxs-lookup"><span data-stu-id="40ccc-156">Profile 1 - Type</span></span>  <br/> | <span data-ttu-id="40ccc-157">Cisco</span><span class="sxs-lookup"><span data-stu-id="40ccc-157">Cisco</span></span> <br/> |
   |<span data-ttu-id="40ccc-158">Профиль 1 — URI</span><span class="sxs-lookup"><span data-stu-id="40ccc-158">Profile 1 - URI</span></span>  <br/> | <span data-ttu-id="40ccc-159">Автоматическое присвоение при регистрации CUCM</span><span class="sxs-lookup"><span data-stu-id="40ccc-159">Automatically assigned at CUCM registration</span></span> <br/> |
   |<span data-ttu-id="40ccc-160">Прокси-сервер 1 — адрес</span><span class="sxs-lookup"><span data-stu-id="40ccc-160">Proxy 1 - Address</span></span>  <br/> |<span data-ttu-id="40ccc-161">Имя хоста CUCM</span><span class="sxs-lookup"><span data-stu-id="40ccc-161">The host name of the CUCM</span></span>  <br/> |
   
<span data-ttu-id="40ccc-162">Теперь VTC настроена для межсервейного межсерваторного перенастройки.</span><span class="sxs-lookup"><span data-stu-id="40ccc-162">The VTC is now configured for interoperation.</span></span> <span data-ttu-id="40ccc-163">Перед началом работы службы необходимо выполнить последние действия на стороне CUCM.</span><span class="sxs-lookup"><span data-stu-id="40ccc-163">Before service can begin, there are final steps to perform on the CUCM side.</span></span>
### <a name="configure-vtc-devices-on-cucm"></a><span data-ttu-id="40ccc-164">Настройка устройств VTC на CUCM</span><span class="sxs-lookup"><span data-stu-id="40ccc-164">Configure VTC devices on CUCM</span></span>

1. <span data-ttu-id="40ccc-165">Войдите в CUCM и перейдите к cisco Unified CM Administration- \> Device- \> Phone- \> Find.</span><span class="sxs-lookup"><span data-stu-id="40ccc-165">Log in to CUCM and Navigate to Cisco Unified CM Administration-\>Device-\>Phone-\>Find.</span></span> 
    
2. <span data-ttu-id="40ccc-166">Выберите устройство VTC, которое необходимо настроить.</span><span class="sxs-lookup"><span data-stu-id="40ccc-166">Select the VTC device to be configured.</span></span> <span data-ttu-id="40ccc-167">Проверьте следующие параметры на экране "Конфигурация телефона", исправив их по мере необходимости.</span><span class="sxs-lookup"><span data-stu-id="40ccc-167">Verify the following settings on the Phone Configuration screen, correcting as needed.</span></span> <span data-ttu-id="40ccc-168">После изменения или проверки этих параметров нажмите кнопку **"Сохранить".**</span><span class="sxs-lookup"><span data-stu-id="40ccc-168">Once these settings have been changed or verified, click on **Save**.</span></span>
    
   |<span data-ttu-id="40ccc-169">**Параметр**</span><span class="sxs-lookup"><span data-stu-id="40ccc-169">**Parameter**</span></span>|<span data-ttu-id="40ccc-170">**Рекомендуемый параметр**</span><span class="sxs-lookup"><span data-stu-id="40ccc-170">**Recommended setting**</span></span>|
   |:-----|:-----|
   |<span data-ttu-id="40ccc-171">Сведения об устройстве — шаблон кнопки телефона</span><span class="sxs-lookup"><span data-stu-id="40ccc-171">Device Information - Phone Button Template</span></span>  <br/> | <span data-ttu-id="40ccc-172">Standard Cisco Telepresence Codec C40</span><span class="sxs-lookup"><span data-stu-id="40ccc-172">Standard Cisco Telepresence Codec C40</span></span> <br/> |
   |<span data-ttu-id="40ccc-173">Сведения об устройстве — общий профиль телефона</span><span class="sxs-lookup"><span data-stu-id="40ccc-173">Device Information - Common Phone Profile</span></span>  <br/> | <span data-ttu-id="40ccc-174">Стандартный общий профиль телефона</span><span class="sxs-lookup"><span data-stu-id="40ccc-174">Standard Common Phone Profile</span></span> <br/> |
   |<span data-ttu-id="40ccc-175">Сведения об устройстве — пространство поиска вызовов</span><span class="sxs-lookup"><span data-stu-id="40ccc-175">Device Information - Calling Search Space</span></span>  <br/> | <span data-ttu-id="40ccc-176">CSS_SfBVideoInterop</span><span class="sxs-lookup"><span data-stu-id="40ccc-176">CSS_SfBVideoInterop</span></span> <br/> |
   |<span data-ttu-id="40ccc-177">Сведения об устройстве — пространство поиска вызовов AAR</span><span class="sxs-lookup"><span data-stu-id="40ccc-177">Device Information - AAR Calling Search Space</span></span>  <br/> | <span data-ttu-id="40ccc-178">CSS_SfBVideoInterop</span><span class="sxs-lookup"><span data-stu-id="40ccc-178">CSS_SfBVideoInterop</span></span> <br/> |
   |<span data-ttu-id="40ccc-179">Сведения об устройстве — список групп ресурсов мультимедиа</span><span class="sxs-lookup"><span data-stu-id="40ccc-179">Device Information - Media Resource Group List</span></span>  <br/> | <span data-ttu-id="40ccc-180">MRGL_SfBVideoInterop</span><span class="sxs-lookup"><span data-stu-id="40ccc-180">MRGL_SfBVideoInterop</span></span> <br/> |
   |<span data-ttu-id="40ccc-181">Сведения о протоколе — профиль безопасности устройства</span><span class="sxs-lookup"><span data-stu-id="40ccc-181">Protocol Specific Information - Device Security Profile</span></span>  <br/> | <span data-ttu-id="40ccc-182">Cisco Telepresence Codec C40</span><span class="sxs-lookup"><span data-stu-id="40ccc-182">Cisco Telepresence Codec C40</span></span> <br/> |
   |<span data-ttu-id="40ccc-183">Сведения о протоколе — перенамеряние пространства поиска вызовов</span><span class="sxs-lookup"><span data-stu-id="40ccc-183">Protocol Specific Information - Rerouting Calling Search Space</span></span>  <br/> | <span data-ttu-id="40ccc-184">CSS_SfBVideoInterop</span><span class="sxs-lookup"><span data-stu-id="40ccc-184">CSS_SfBVideoInterop</span></span> <br/> |
   |<span data-ttu-id="40ccc-185">Сведения о протоколе — пространство поиска вызовов SUBSCRIBE</span><span class="sxs-lookup"><span data-stu-id="40ccc-185">Protocol Specific Information - SUBSCRIBE Calling Search Space</span></span>  <br/> | <span data-ttu-id="40ccc-186">CSS_SfBVideoInterop</span><span class="sxs-lookup"><span data-stu-id="40ccc-186">CSS_SfBVideoInterop</span></span> <br/> |
   |<span data-ttu-id="40ccc-187">Сведения о протоколе - профиль SIP</span><span class="sxs-lookup"><span data-stu-id="40ccc-187">Protocol Specific Information -SIP Profile</span></span>  <br/> | <span data-ttu-id="40ccc-188">Стандартный профиль SIP для конечной точки телеприсутства</span><span class="sxs-lookup"><span data-stu-id="40ccc-188">Standard SIP Profile for Telepresence Endpoint</span></span> <br/> |
   
3. <span data-ttu-id="40ccc-189">После с сохраненной конфигурации VTC перейдите на экран конфигурации телефона для устройства.</span><span class="sxs-lookup"><span data-stu-id="40ccc-189">Once VTC configuration is saved, re-navigate to the Phone Configuration screen for the device.</span></span> <span data-ttu-id="40ccc-190">В верхней части экрана в группе "Связь" щелкните связь для видеосвязи.</span><span class="sxs-lookup"><span data-stu-id="40ccc-190">At the top of the screen in the Association group, click on the association for the Video Interop.</span></span> <span data-ttu-id="40ccc-191">При этом будет отсвеяна экран настройки номера каталога.</span><span class="sxs-lookup"><span data-stu-id="40ccc-191">This brings up the Directory Number Configuration screen.</span></span> 
    
4. <span data-ttu-id="40ccc-192">Проверьте следующие параметры, исправив их по мере необходимости:</span><span class="sxs-lookup"><span data-stu-id="40ccc-192">Verify the following settings, correcting as needed:</span></span> 
    
    <span data-ttu-id="40ccc-193">Внести соответствующие изменения, как показано в параметрах "Сведения о номере каталога" и "Параметры номера каталога".</span><span class="sxs-lookup"><span data-stu-id="40ccc-193">Make the appropriate changes as shown to the Directory Number Information and the Directory Number Settings.</span></span>
    
   |<span data-ttu-id="40ccc-194">**Параметр**</span><span class="sxs-lookup"><span data-stu-id="40ccc-194">**Parameter**</span></span>|<span data-ttu-id="40ccc-195">**Рекомендуемый параметр**</span><span class="sxs-lookup"><span data-stu-id="40ccc-195">**Recommended setting**</span></span>|
   |:-----|:-----|
   | <span data-ttu-id="40ccc-196">Сведения о номере каталога — раздел маршрута</span><span class="sxs-lookup"><span data-stu-id="40ccc-196">Directory Number Information - Route Partition</span></span> <br/> | <span data-ttu-id="40ccc-197">SfBVideoInterop_RoutePartition</span><span class="sxs-lookup"><span data-stu-id="40ccc-197">SfBVideoInterop_RoutePartition</span></span> <br/> |
   |<span data-ttu-id="40ccc-198">Параметры номера каталога — пространство поиска вызовов</span><span class="sxs-lookup"><span data-stu-id="40ccc-198">Directory Number Settings - Calling Search Space</span></span>  <br/> | <span data-ttu-id="40ccc-199">CSS_SfBVideoInterop</span><span class="sxs-lookup"><span data-stu-id="40ccc-199">CSS_SfBVideoInterop</span></span> <br/> |
   |<span data-ttu-id="40ccc-200">Параметры альтернативной стороны и уровня конфиденциального доступа MLPP — пространство поиска вызовов MLPP</span><span class="sxs-lookup"><span data-stu-id="40ccc-200">MLPP Alternate Party and Confidential Access Level Settings - MLPP Calling Search Space</span></span>  <br/> | <span data-ttu-id="40ccc-201">CSS_SfBVideoInterop</span><span class="sxs-lookup"><span data-stu-id="40ccc-201">CSS_SfBVideoInterop</span></span> <br/> |
   |<span data-ttu-id="40ccc-202">Строка 1 на устройстве — отображение (ИД вызываемого)</span><span class="sxs-lookup"><span data-stu-id="40ccc-202">Line 1 on Device - Display (Caller ID)</span></span>  <br/> | <span data-ttu-id="40ccc-203">При желании</span><span class="sxs-lookup"><span data-stu-id="40ccc-203">As desired</span></span> <br/> |
   |<span data-ttu-id="40ccc-204">Строка 1 на устройстве — asCII Display (Caller ID)</span><span class="sxs-lookup"><span data-stu-id="40ccc-204">Line 1 on Device - ASCII Display (Caller ID)</span></span>  <br/> | <span data-ttu-id="40ccc-205">При желании</span><span class="sxs-lookup"><span data-stu-id="40ccc-205">As desired</span></span> <br/> |
   
5. <span data-ttu-id="40ccc-206">По завершению прокрутите экран до верхней части экрана и нажмите кнопку **"Сохранить".**</span><span class="sxs-lookup"><span data-stu-id="40ccc-206">When finished, scroll to the top of the screen and press **Save**.</span></span> 
    
<span data-ttu-id="40ccc-207">Настройка для этого устройства VTC завершена.</span><span class="sxs-lookup"><span data-stu-id="40ccc-207">Configuration is now complete for this VTC device.</span></span> <span data-ttu-id="40ccc-208">Вам потребуется повторить этот процесс для других устройств VTC на предприятии.</span><span class="sxs-lookup"><span data-stu-id="40ccc-208">You will need to repeat this process for other VTC devices in your enterprise.</span></span>

