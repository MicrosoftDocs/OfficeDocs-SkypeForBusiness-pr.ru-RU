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
# <a name="configure-a-vtc-for-interoperation-with-skype-for-business-server"></a><span data-ttu-id="b7e37-103">Настройка VTC для связи со Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="b7e37-103">Configure a VTC for Interoperation with Skype for Business Server</span></span>
 
<span data-ttu-id="b7e37-104">**Сводка:** Настройте устройства VTC для работы со Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="b7e37-104">**Summary:** Configure the VTC devices to work with Skype for Business Server.</span></span>
  
<span data-ttu-id="b7e37-105">Необходимо выполнить следующие процедуры настройки конфигурации для каждого VTC, который будет подключаться к серверу VIS Skype для бизнеса через магистраль SIP и видео шлюз Cisco Unified Communications Manager (CallManager или CUCM).</span><span class="sxs-lookup"><span data-stu-id="b7e37-105">You will need to perform the following configuration customization procedures for each VTC that will connect to the Skype for Business VIS server through a SIP trunk and Cisco Unified Communications Manager (CallManager, or CUCM) video gateway.</span></span>
  
<span data-ttu-id="b7e37-106">Описанные здесь параметры предназначены только в качестве примеров настройки CUCM для работы с VIS.</span><span class="sxs-lookup"><span data-stu-id="b7e37-106">The settings described here are meant only as examples of how CUCM can be configured to work with a VIS.</span></span> <span data-ttu-id="b7e37-107">Другие параметры и/или использование альтернативных функций CUCM также можно использовать для достижения такого же результата.</span><span class="sxs-lookup"><span data-stu-id="b7e37-107">Other settings and/or usages of alternate CUCM functionality could also be used to achieve the same result.</span></span> <span data-ttu-id="b7e37-108">Рекомендации по оптимальной конфигурации для конкретного сценария не подразумеваются.</span><span class="sxs-lookup"><span data-stu-id="b7e37-108">No recommendation is implied as to the optimal configuration for a particular scenario.</span></span>
  
### <a name="configure-a-vtc-registered-with-cucm"></a><span data-ttu-id="b7e37-109">Настройка VTC, зарегистрированного с помощью CUCM</span><span class="sxs-lookup"><span data-stu-id="b7e37-109">Configure a VTC registered with CUCM</span></span>

1. <span data-ttu-id="b7e37-110">Войдите на устройство Cisco VTC и перейдите к пункту \> Configuration-System Configuration- \> Provisioning.</span><span class="sxs-lookup"><span data-stu-id="b7e37-110">Log in to the Cisco VTC device and navigate to Configuration-\>System Configuration-\>Provisioning.</span></span>
    
2. <span data-ttu-id="b7e37-111">Проверьте следующие параметры, исправив их по мере необходимости:</span><span class="sxs-lookup"><span data-stu-id="b7e37-111">Verify the following settings, correcting as needed:</span></span> 
    
   |<span data-ttu-id="b7e37-112">**Параметр**</span><span class="sxs-lookup"><span data-stu-id="b7e37-112">**Parameter**</span></span>|<span data-ttu-id="b7e37-113">**Рекомендуемый параметр**</span><span class="sxs-lookup"><span data-stu-id="b7e37-113">**Recommended setting**</span></span>|
   |:-----|:-----|
   |<span data-ttu-id="b7e37-114">Режим предоставления</span><span class="sxs-lookup"><span data-stu-id="b7e37-114">Provisioning Mode</span></span>  <br/> | <span data-ttu-id="b7e37-115">CUCM</span><span class="sxs-lookup"><span data-stu-id="b7e37-115">CUCM</span></span> <br/> |
   |<span data-ttu-id="b7e37-116">Адрес ExternalManager</span><span class="sxs-lookup"><span data-stu-id="b7e37-116">ExternalManager Address</span></span>  <br/> | <span data-ttu-id="b7e37-117">FQDN CUCM</span><span class="sxs-lookup"><span data-stu-id="b7e37-117">CUCM's FQDN</span></span> <br/> |
   | <span data-ttu-id="b7e37-118">Домен ExternalManager</span><span class="sxs-lookup"><span data-stu-id="b7e37-118">ExternalManager Domain</span></span> <br/> |<span data-ttu-id="b7e37-119">Домен CUCM</span><span class="sxs-lookup"><span data-stu-id="b7e37-119">CUCM's domain</span></span>  <br/> |
   
3. <span data-ttu-id="b7e37-120">Перейдите к configuration- \> System Configuration- \> Network.</span><span class="sxs-lookup"><span data-stu-id="b7e37-120">Navigate to Configuration-\>System Configuration-\>Network.</span></span>
    
4. <span data-ttu-id="b7e37-121">Проверьте следующие параметры, исправив их по мере необходимости:</span><span class="sxs-lookup"><span data-stu-id="b7e37-121">Verify the following settings, correcting as needed:</span></span> 
    
   |<span data-ttu-id="b7e37-122">**Параметр**</span><span class="sxs-lookup"><span data-stu-id="b7e37-122">**Parameter**</span></span>|<span data-ttu-id="b7e37-123">**Рекомендуемый параметр**</span><span class="sxs-lookup"><span data-stu-id="b7e37-123">**Recommended setting**</span></span>|
   |:-----|:-----|
   |<span data-ttu-id="b7e37-124">DNS-имя домена</span><span class="sxs-lookup"><span data-stu-id="b7e37-124">DNS Domain Name</span></span>  <br/> | <span data-ttu-id="b7e37-125">Имя домена CUCM</span><span class="sxs-lookup"><span data-stu-id="b7e37-125">CUCM's Domain name</span></span> <br/> |
   |<span data-ttu-id="b7e37-126">Адрес DNS-сервера 1</span><span class="sxs-lookup"><span data-stu-id="b7e37-126">DNS Server 1 Address</span></span>  <br/> | <span data-ttu-id="b7e37-127">нужный адрес DNS-сервера</span><span class="sxs-lookup"><span data-stu-id="b7e37-127">your desired DNS server address</span></span> <br/> |
   
5. <span data-ttu-id="b7e37-128">Перейдите к сайту Configuration- \> System Configuration— \> Network Services.</span><span class="sxs-lookup"><span data-stu-id="b7e37-128">Navigate to Configuration-\>System Configuration-\>Network Services.</span></span> <span data-ttu-id="b7e37-129">Убедитесь, что режим H.323 отключен и режим SIP включен.</span><span class="sxs-lookup"><span data-stu-id="b7e37-129">Ensure that H.323 mode is turned off and SIP mode is turned on.</span></span> 
    
6. <span data-ttu-id="b7e37-130">Эти параметры устанавливаются автоматически при регистрации конечной точки с помощью CUCM.</span><span class="sxs-lookup"><span data-stu-id="b7e37-130">These options are set automatically when the endpoint is registered with CUCM.</span></span> <span data-ttu-id="b7e37-131">Проверьте следующие параметры, исправив их по мере необходимости:</span><span class="sxs-lookup"><span data-stu-id="b7e37-131">Verify the following settings, correcting as needed:</span></span> 
    
   |<span data-ttu-id="b7e37-132">**Параметр**</span><span class="sxs-lookup"><span data-stu-id="b7e37-132">**Parameter**</span></span>|<span data-ttu-id="b7e37-133">**Рекомендуемый параметр**</span><span class="sxs-lookup"><span data-stu-id="b7e37-133">**Recommended setting**</span></span>|
   |:-----|:-----|
   |<span data-ttu-id="b7e37-134">Режим H.323</span><span class="sxs-lookup"><span data-stu-id="b7e37-134">H.323 Mode</span></span>  <br/> | <span data-ttu-id="b7e37-135">Выкл.</span><span class="sxs-lookup"><span data-stu-id="b7e37-135">Off</span></span> <br/> |
   |<span data-ttu-id="b7e37-136">Режим HTTP</span><span class="sxs-lookup"><span data-stu-id="b7e37-136">HTTP Mode</span></span>  <br/> | <span data-ttu-id="b7e37-137">Вкл.</span><span class="sxs-lookup"><span data-stu-id="b7e37-137">On</span></span> <br/> |
   | <span data-ttu-id="b7e37-138">Режим SIP</span><span class="sxs-lookup"><span data-stu-id="b7e37-138">SIP Mode</span></span> <br/> | <span data-ttu-id="b7e37-139">Вкл.</span><span class="sxs-lookup"><span data-stu-id="b7e37-139">On</span></span> <br/> |
   |<span data-ttu-id="b7e37-140">Режим Telnet</span><span class="sxs-lookup"><span data-stu-id="b7e37-140">Telnet Mode</span></span>  <br/> | <span data-ttu-id="b7e37-141">Вкл.</span><span class="sxs-lookup"><span data-stu-id="b7e37-141">On</span></span> <br/> |
   |<span data-ttu-id="b7e37-142">WelcomeText</span><span class="sxs-lookup"><span data-stu-id="b7e37-142">WelcomeText</span></span>  <br/> | <span data-ttu-id="b7e37-143">Вкл.</span><span class="sxs-lookup"><span data-stu-id="b7e37-143">On</span></span> <br/> |
   |<span data-ttu-id="b7e37-144">Режим XMLAPI</span><span class="sxs-lookup"><span data-stu-id="b7e37-144">XMLAPI Mode</span></span>  <br/> | <span data-ttu-id="b7e37-145">Вкл.</span><span class="sxs-lookup"><span data-stu-id="b7e37-145">On</span></span> <br/> |
   
7. <span data-ttu-id="b7e37-146">Перейдите к \> configuration-System Configuration- \> SIP.</span><span class="sxs-lookup"><span data-stu-id="b7e37-146">Navigate to Configuration-\>System Configuration-\>SIP.</span></span>
    
8. <span data-ttu-id="b7e37-147">Проверьте следующие параметры, исправив их по мере необходимости:</span><span class="sxs-lookup"><span data-stu-id="b7e37-147">Verify the following settings, correcting as needed:</span></span> 
    
   |<span data-ttu-id="b7e37-148">**Параметр**</span><span class="sxs-lookup"><span data-stu-id="b7e37-148">**Parameter**</span></span>|<span data-ttu-id="b7e37-149">**Рекомендуемый параметр**</span><span class="sxs-lookup"><span data-stu-id="b7e37-149">**Recommended setting**</span></span>|
   |:-----|:-----|
   |<span data-ttu-id="b7e37-150">Профиль 1 — DefaultTransport</span><span class="sxs-lookup"><span data-stu-id="b7e37-150">Profile 1 - DefaultTransport</span></span>  <br/> | <span data-ttu-id="b7e37-151">TCP</span><span class="sxs-lookup"><span data-stu-id="b7e37-151">TCP</span></span> <br/> |
   |<span data-ttu-id="b7e37-152">Профиль 1 — исходящие данные</span><span class="sxs-lookup"><span data-stu-id="b7e37-152">Profile 1 - Outbound</span></span>  <br/> | <span data-ttu-id="b7e37-153">Выкл.</span><span class="sxs-lookup"><span data-stu-id="b7e37-153">Off</span></span> <br/> |
   |<span data-ttu-id="b7e37-154">Профиль 1 — TlsVerify</span><span class="sxs-lookup"><span data-stu-id="b7e37-154">Profile 1 - TlsVerify</span></span>  <br/> | <span data-ttu-id="b7e37-155">Вкл.</span><span class="sxs-lookup"><span data-stu-id="b7e37-155">On</span></span> <br/> |
   |<span data-ttu-id="b7e37-156">Профиль 1 — тип</span><span class="sxs-lookup"><span data-stu-id="b7e37-156">Profile 1 - Type</span></span>  <br/> | <span data-ttu-id="b7e37-157">Cisco</span><span class="sxs-lookup"><span data-stu-id="b7e37-157">Cisco</span></span> <br/> |
   |<span data-ttu-id="b7e37-158">Профиль 1 — URI</span><span class="sxs-lookup"><span data-stu-id="b7e37-158">Profile 1 - URI</span></span>  <br/> | <span data-ttu-id="b7e37-159">Автоматическое присвоение при регистрации CUCM</span><span class="sxs-lookup"><span data-stu-id="b7e37-159">Automatically assigned at CUCM registration</span></span> <br/> |
   |<span data-ttu-id="b7e37-160">Прокси-сервер 1 — адрес</span><span class="sxs-lookup"><span data-stu-id="b7e37-160">Proxy 1 - Address</span></span>  <br/> |<span data-ttu-id="b7e37-161">Имя хоста CUCM</span><span class="sxs-lookup"><span data-stu-id="b7e37-161">The host name of the CUCM</span></span>  <br/> |
   
<span data-ttu-id="b7e37-162">Теперь VTC настроен для межсервейного межсервирования.</span><span class="sxs-lookup"><span data-stu-id="b7e37-162">The VTC is now configured for interoperation.</span></span> <span data-ttu-id="b7e37-163">Перед началом работы службы необходимо выполнить последние действия на стороне CUCM.</span><span class="sxs-lookup"><span data-stu-id="b7e37-163">Before service can begin, there are final steps to perform on the CUCM side.</span></span>
### <a name="configure-vtc-devices-on-cucm"></a><span data-ttu-id="b7e37-164">Настройка устройств VTC на CUCM</span><span class="sxs-lookup"><span data-stu-id="b7e37-164">Configure VTC devices on CUCM</span></span>

1. <span data-ttu-id="b7e37-165">Войдите в CUCM и перейдите в веб-сайт Cisco Unified CM Administration- \> Device- \> Phone- \> Find.</span><span class="sxs-lookup"><span data-stu-id="b7e37-165">Log in to CUCM and Navigate to Cisco Unified CM Administration-\>Device-\>Phone-\>Find.</span></span> 
    
2. <span data-ttu-id="b7e37-166">Выберите устройство VTC, которое необходимо настроить.</span><span class="sxs-lookup"><span data-stu-id="b7e37-166">Select the VTC device to be configured.</span></span> <span data-ttu-id="b7e37-167">Проверьте следующие параметры на экране "Конфигурация телефона", исправив их по мере необходимости.</span><span class="sxs-lookup"><span data-stu-id="b7e37-167">Verify the following settings on the Phone Configuration screen, correcting as needed.</span></span> <span data-ttu-id="b7e37-168">После изменения или проверки этих параметров нажмите кнопку **"Сохранить".**</span><span class="sxs-lookup"><span data-stu-id="b7e37-168">Once these settings have been changed or verified, click on **Save**.</span></span>
    
   |<span data-ttu-id="b7e37-169">**Параметр**</span><span class="sxs-lookup"><span data-stu-id="b7e37-169">**Parameter**</span></span>|<span data-ttu-id="b7e37-170">**Рекомендуемый параметр**</span><span class="sxs-lookup"><span data-stu-id="b7e37-170">**Recommended setting**</span></span>|
   |:-----|:-----|
   |<span data-ttu-id="b7e37-171">Сведения об устройстве — шаблон кнопки телефона</span><span class="sxs-lookup"><span data-stu-id="b7e37-171">Device Information - Phone Button Template</span></span>  <br/> | <span data-ttu-id="b7e37-172">Standard Cisco Telepresence Codec C40</span><span class="sxs-lookup"><span data-stu-id="b7e37-172">Standard Cisco Telepresence Codec C40</span></span> <br/> |
   |<span data-ttu-id="b7e37-173">Сведения об устройстве — общий профиль телефона</span><span class="sxs-lookup"><span data-stu-id="b7e37-173">Device Information - Common Phone Profile</span></span>  <br/> | <span data-ttu-id="b7e37-174">Стандартный общий профиль телефона</span><span class="sxs-lookup"><span data-stu-id="b7e37-174">Standard Common Phone Profile</span></span> <br/> |
   |<span data-ttu-id="b7e37-175">Сведения об устройстве — пространство поиска вызовов</span><span class="sxs-lookup"><span data-stu-id="b7e37-175">Device Information - Calling Search Space</span></span>  <br/> | <span data-ttu-id="b7e37-176">CSS_SfBVideoInterop</span><span class="sxs-lookup"><span data-stu-id="b7e37-176">CSS_SfBVideoInterop</span></span> <br/> |
   |<span data-ttu-id="b7e37-177">Сведения об устройстве — пространство поиска вызовов AAR</span><span class="sxs-lookup"><span data-stu-id="b7e37-177">Device Information - AAR Calling Search Space</span></span>  <br/> | <span data-ttu-id="b7e37-178">CSS_SfBVideoInterop</span><span class="sxs-lookup"><span data-stu-id="b7e37-178">CSS_SfBVideoInterop</span></span> <br/> |
   |<span data-ttu-id="b7e37-179">Сведения об устройстве — список групп ресурсов мультимедиа</span><span class="sxs-lookup"><span data-stu-id="b7e37-179">Device Information - Media Resource Group List</span></span>  <br/> | <span data-ttu-id="b7e37-180">MRGL_SfBVideoInterop</span><span class="sxs-lookup"><span data-stu-id="b7e37-180">MRGL_SfBVideoInterop</span></span> <br/> |
   |<span data-ttu-id="b7e37-181">Сведения о протоколе — профиль безопасности устройства</span><span class="sxs-lookup"><span data-stu-id="b7e37-181">Protocol Specific Information - Device Security Profile</span></span>  <br/> | <span data-ttu-id="b7e37-182">Cisco Telepresence Codec C40</span><span class="sxs-lookup"><span data-stu-id="b7e37-182">Cisco Telepresence Codec C40</span></span> <br/> |
   |<span data-ttu-id="b7e37-183">Сведения о протоколе — перенамеряние пространства поиска вызовов</span><span class="sxs-lookup"><span data-stu-id="b7e37-183">Protocol Specific Information - Rerouting Calling Search Space</span></span>  <br/> | <span data-ttu-id="b7e37-184">CSS_SfBVideoInterop</span><span class="sxs-lookup"><span data-stu-id="b7e37-184">CSS_SfBVideoInterop</span></span> <br/> |
   |<span data-ttu-id="b7e37-185">Сведения о протоколе — пространство поиска вызовов SUBSCRIBE</span><span class="sxs-lookup"><span data-stu-id="b7e37-185">Protocol Specific Information - SUBSCRIBE Calling Search Space</span></span>  <br/> | <span data-ttu-id="b7e37-186">CSS_SfBVideoInterop</span><span class="sxs-lookup"><span data-stu-id="b7e37-186">CSS_SfBVideoInterop</span></span> <br/> |
   |<span data-ttu-id="b7e37-187">Сведения о протоколе - профиль SIP</span><span class="sxs-lookup"><span data-stu-id="b7e37-187">Protocol Specific Information -SIP Profile</span></span>  <br/> | <span data-ttu-id="b7e37-188">Стандартный профиль SIP для конечной точки телеприсутства</span><span class="sxs-lookup"><span data-stu-id="b7e37-188">Standard SIP Profile for Telepresence Endpoint</span></span> <br/> |
   
3. <span data-ttu-id="b7e37-189">После с сохраненной конфигурации VTC перейдите на экран конфигурации телефона для устройства.</span><span class="sxs-lookup"><span data-stu-id="b7e37-189">Once VTC configuration is saved, re-navigate to the Phone Configuration screen for the device.</span></span> <span data-ttu-id="b7e37-190">В верхней части экрана в группе "Связь" щелкните связь для видеосвязи.</span><span class="sxs-lookup"><span data-stu-id="b7e37-190">At the top of the screen in the Association group, click on the association for the Video Interop.</span></span> <span data-ttu-id="b7e37-191">При этом будет отсвеяна экран настройки номера каталога.</span><span class="sxs-lookup"><span data-stu-id="b7e37-191">This brings up the Directory Number Configuration screen.</span></span> 
    
4. <span data-ttu-id="b7e37-192">Проверьте следующие параметры, исправив их по мере необходимости:</span><span class="sxs-lookup"><span data-stu-id="b7e37-192">Verify the following settings, correcting as needed:</span></span> 
    
    <span data-ttu-id="b7e37-193">Внести соответствующие изменения, как показано в сведениях о номере каталога и параметрах номера каталога.</span><span class="sxs-lookup"><span data-stu-id="b7e37-193">Make the appropriate changes as shown to the Directory Number Information and the Directory Number Settings.</span></span>
    
   |<span data-ttu-id="b7e37-194">**Параметр**</span><span class="sxs-lookup"><span data-stu-id="b7e37-194">**Parameter**</span></span>|<span data-ttu-id="b7e37-195">**Рекомендуемый параметр**</span><span class="sxs-lookup"><span data-stu-id="b7e37-195">**Recommended setting**</span></span>|
   |:-----|:-----|
   | <span data-ttu-id="b7e37-196">Сведения о номере каталога — раздел маршрута</span><span class="sxs-lookup"><span data-stu-id="b7e37-196">Directory Number Information - Route Partition</span></span> <br/> | <span data-ttu-id="b7e37-197">SfBVideoInterop_RoutePartition</span><span class="sxs-lookup"><span data-stu-id="b7e37-197">SfBVideoInterop_RoutePartition</span></span> <br/> |
   |<span data-ttu-id="b7e37-198">Параметры номера каталога — пространство поиска вызовов</span><span class="sxs-lookup"><span data-stu-id="b7e37-198">Directory Number Settings - Calling Search Space</span></span>  <br/> | <span data-ttu-id="b7e37-199">CSS_SfBVideoInterop</span><span class="sxs-lookup"><span data-stu-id="b7e37-199">CSS_SfBVideoInterop</span></span> <br/> |
   |<span data-ttu-id="b7e37-200">Параметры альтернативной стороны и уровня конфиденциального доступа MLPP — пространство поиска вызовов MLPP</span><span class="sxs-lookup"><span data-stu-id="b7e37-200">MLPP Alternate Party and Confidential Access Level Settings - MLPP Calling Search Space</span></span>  <br/> | <span data-ttu-id="b7e37-201">CSS_SfBVideoInterop</span><span class="sxs-lookup"><span data-stu-id="b7e37-201">CSS_SfBVideoInterop</span></span> <br/> |
   |<span data-ttu-id="b7e37-202">Строка 1 на устройстве — отображение (ИД вызываемого)</span><span class="sxs-lookup"><span data-stu-id="b7e37-202">Line 1 on Device - Display (Caller ID)</span></span>  <br/> | <span data-ttu-id="b7e37-203">При желании</span><span class="sxs-lookup"><span data-stu-id="b7e37-203">As desired</span></span> <br/> |
   |<span data-ttu-id="b7e37-204">Строка 1 на устройстве — asCII Display (Caller ID)</span><span class="sxs-lookup"><span data-stu-id="b7e37-204">Line 1 on Device - ASCII Display (Caller ID)</span></span>  <br/> | <span data-ttu-id="b7e37-205">При желании</span><span class="sxs-lookup"><span data-stu-id="b7e37-205">As desired</span></span> <br/> |
   
5. <span data-ttu-id="b7e37-206">По завершению прокрутите экран до верхней части экрана и нажмите кнопку **"Сохранить".**</span><span class="sxs-lookup"><span data-stu-id="b7e37-206">When finished, scroll to the top of the screen and press **Save**.</span></span> 
    
<span data-ttu-id="b7e37-207">Настройка для этого устройства VTC завершена.</span><span class="sxs-lookup"><span data-stu-id="b7e37-207">Configuration is now complete for this VTC device.</span></span> <span data-ttu-id="b7e37-208">Вам потребуется повторить этот процесс для других устройств VTC на предприятии.</span><span class="sxs-lookup"><span data-stu-id="b7e37-208">You will need to repeat this process for other VTC devices in your enterprise.</span></span>

