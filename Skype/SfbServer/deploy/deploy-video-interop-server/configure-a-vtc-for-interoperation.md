---
title: Настройка VTC для взаимодействия с Скайп для Business Server
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 1016aed6-99fe-452e-8b20-81c814808c3d
description: 'Сводка: Настройка VTC устройства для работы с Скайп для Business Server.'
ms.openlocfilehash: 1a8422ddfa33652fa13d5aeb42b86a72b809126b
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/27/2019
ms.locfileid: "30880674"
---
# <a name="configure-a-vtc-for-interoperation-with-skype-for-business-server"></a><span data-ttu-id="7b2f1-103">Настройка VTC для взаимодействия с Скайп для Business Server</span><span class="sxs-lookup"><span data-stu-id="7b2f1-103">Configure a VTC for Interoperation with Skype for Business Server</span></span>
 
<span data-ttu-id="7b2f1-104">**Сводка:** Настройка VTC устройства для работы с Скайп для Business Server.</span><span class="sxs-lookup"><span data-stu-id="7b2f1-104">**Summary:** Configure the VTC devices to work with Skype for Business Server.</span></span>
  
<span data-ttu-id="7b2f1-105">Необходимо выполнить следующие процедуры настройки конфигурации для каждого VTC, которые будут подключаться к Скайп для Business VIS server через магистраль SIP и Cisco объединенных коммуникаций Manager (CallManager или CUCM) видео шлюза.</span><span class="sxs-lookup"><span data-stu-id="7b2f1-105">You will need to perform the following configuration customization procedures for each VTC that will connect to the Skype for Business VIS server through a SIP trunk and Cisco Unified Communications Manager (CallManager, or CUCM) video gateway.</span></span>
  
<span data-ttu-id="7b2f1-106">Параметры, описанные здесь приведены только в качестве примеров того, как можно настроить CUCM для работы с VIS.</span><span class="sxs-lookup"><span data-stu-id="7b2f1-106">The settings described here are meant only as examples of how CUCM can be configured to work with a VIS.</span></span> <span data-ttu-id="7b2f1-107">Такого же результата также можно достичь с помощью других настроек и/или использования альтернативных функциональных возможностей CUCM.</span><span class="sxs-lookup"><span data-stu-id="7b2f1-107">Other settings and/or usages of alternate CUCM functionality could also be used to achieve the same result.</span></span> <span data-ttu-id="7b2f1-108">Рекомендаций в отношении оптимальной конфигурации для конкретного сценария нет.</span><span class="sxs-lookup"><span data-stu-id="7b2f1-108">No recommendation is implied as to the optimal configuration for a particular scenario.</span></span>
  
### <a name="configure-a-vtc-registered-with-cucm"></a><span data-ttu-id="7b2f1-109">Настройка VTC, зарегистрированной с помощью CUCM</span><span class="sxs-lookup"><span data-stu-id="7b2f1-109">Configure a VTC registered with CUCM</span></span>

1. <span data-ttu-id="7b2f1-110">Выполните вход в систему устройства Cisco VTC и перейдите к конфигурации -\>системы конфигурации -\>подготовки.</span><span class="sxs-lookup"><span data-stu-id="7b2f1-110">Log in to the Cisco VTC device and navigate to Configuration-\>System Configuration-\>Provisioning.</span></span>
    
2. <span data-ttu-id="7b2f1-111">Проверьте следующие параметры, внося необходимые исправления:</span><span class="sxs-lookup"><span data-stu-id="7b2f1-111">Verify the following settings, correcting as needed:</span></span> 
    
   |<span data-ttu-id="7b2f1-112">**Параметр**</span><span class="sxs-lookup"><span data-stu-id="7b2f1-112">**Parameter**</span></span>|<span data-ttu-id="7b2f1-113">**Рекомендованная настройка**</span><span class="sxs-lookup"><span data-stu-id="7b2f1-113">**Recommended setting**</span></span>|
   |:-----|:-----|
   |<span data-ttu-id="7b2f1-114">Режим подготовки</span><span class="sxs-lookup"><span data-stu-id="7b2f1-114">Provisioning Mode</span></span>  <br/> | <span data-ttu-id="7b2f1-115">CUCM</span><span class="sxs-lookup"><span data-stu-id="7b2f1-115">CUCM</span></span> <br/> |
   |<span data-ttu-id="7b2f1-116">Адрес ExternalManager</span><span class="sxs-lookup"><span data-stu-id="7b2f1-116">ExternalManager Address</span></span>  <br/> | <span data-ttu-id="7b2f1-117">Полное доменное имя CUCM</span><span class="sxs-lookup"><span data-stu-id="7b2f1-117">CUCM's FQDN</span></span> <br/> |
   | <span data-ttu-id="7b2f1-118">ExternalManager домена</span><span class="sxs-lookup"><span data-stu-id="7b2f1-118">ExternalManager Domain</span></span> <br/> |<span data-ttu-id="7b2f1-119">Домен пользователя CUCM</span><span class="sxs-lookup"><span data-stu-id="7b2f1-119">CUCM's domain</span></span>  <br/> |
   
3. <span data-ttu-id="7b2f1-120">Перейдите к конфигурации -\>системы конфигурации -\>сети.</span><span class="sxs-lookup"><span data-stu-id="7b2f1-120">Navigate to Configuration-\>System Configuration-\>Network.</span></span>
    
4. <span data-ttu-id="7b2f1-121">Проверьте следующие параметры, внося необходимые исправления:</span><span class="sxs-lookup"><span data-stu-id="7b2f1-121">Verify the following settings, correcting as needed:</span></span> 
    
   |<span data-ttu-id="7b2f1-122">**Параметр**</span><span class="sxs-lookup"><span data-stu-id="7b2f1-122">**Parameter**</span></span>|<span data-ttu-id="7b2f1-123">**Рекомендованная настройка**</span><span class="sxs-lookup"><span data-stu-id="7b2f1-123">**Recommended setting**</span></span>|
   |:-----|:-----|
   |<span data-ttu-id="7b2f1-124">Имя домена DNS</span><span class="sxs-lookup"><span data-stu-id="7b2f1-124">DNS Domain Name</span></span>  <br/> | <span data-ttu-id="7b2f1-125">Имя домена CUCM</span><span class="sxs-lookup"><span data-stu-id="7b2f1-125">CUCM's Domain name</span></span> <br/> |
   |<span data-ttu-id="7b2f1-126">Адрес DNS-сервера 1</span><span class="sxs-lookup"><span data-stu-id="7b2f1-126">DNS Server 1 Address</span></span>  <br/> | <span data-ttu-id="7b2f1-127">адрес вашего желательного DNS-сервера</span><span class="sxs-lookup"><span data-stu-id="7b2f1-127">your desired DNS server address</span></span> <br/> |
   
5. <span data-ttu-id="7b2f1-128">Перейдите к конфигурации -\>системы конфигурации -\>сетевой службы.</span><span class="sxs-lookup"><span data-stu-id="7b2f1-128">Navigate to Configuration-\>System Configuration-\>Network Services.</span></span> <span data-ttu-id="7b2f1-129">Убедитесь, что режим H.323 отключен, а режим SIP включен.</span><span class="sxs-lookup"><span data-stu-id="7b2f1-129">Ensure that H.323 mode is turned off and SIP mode is turned on.</span></span> 
    
6. <span data-ttu-id="7b2f1-p103">Эти параметры задаются автоматически, когда конечная точка регистрируется с помощью CUCM. Проверьте следующие параметры, внося необходимые исправления:</span><span class="sxs-lookup"><span data-stu-id="7b2f1-p103">These options are set automatically when the endpoint is registered with CUCM. Verify the following settings, correcting as needed:</span></span> 
    
   |<span data-ttu-id="7b2f1-132">**Параметр**</span><span class="sxs-lookup"><span data-stu-id="7b2f1-132">**Parameter**</span></span>|<span data-ttu-id="7b2f1-133">**Рекомендованная настройка**</span><span class="sxs-lookup"><span data-stu-id="7b2f1-133">**Recommended setting**</span></span>|
   |:-----|:-----|
   |<span data-ttu-id="7b2f1-134">Режим H.323</span><span class="sxs-lookup"><span data-stu-id="7b2f1-134">H.323 Mode</span></span>  <br/> | <span data-ttu-id="7b2f1-135">Выкл.</span><span class="sxs-lookup"><span data-stu-id="7b2f1-135">Off</span></span> <br/> |
   |<span data-ttu-id="7b2f1-136">Режим HTTP</span><span class="sxs-lookup"><span data-stu-id="7b2f1-136">HTTP Mode</span></span>  <br/> | <span data-ttu-id="7b2f1-137">Вкл.</span><span class="sxs-lookup"><span data-stu-id="7b2f1-137">On</span></span> <br/> |
   | <span data-ttu-id="7b2f1-138">Режим SIP</span><span class="sxs-lookup"><span data-stu-id="7b2f1-138">SIP Mode</span></span> <br/> | <span data-ttu-id="7b2f1-139">Вкл.</span><span class="sxs-lookup"><span data-stu-id="7b2f1-139">On</span></span> <br/> |
   |<span data-ttu-id="7b2f1-140">Режим Telnet</span><span class="sxs-lookup"><span data-stu-id="7b2f1-140">Telnet Mode</span></span>  <br/> | <span data-ttu-id="7b2f1-141">Вкл.</span><span class="sxs-lookup"><span data-stu-id="7b2f1-141">On</span></span> <br/> |
   |<span data-ttu-id="7b2f1-142">WelcomeText</span><span class="sxs-lookup"><span data-stu-id="7b2f1-142">WelcomeText</span></span>  <br/> | <span data-ttu-id="7b2f1-143">Вкл.</span><span class="sxs-lookup"><span data-stu-id="7b2f1-143">On</span></span> <br/> |
   |<span data-ttu-id="7b2f1-144">Режим XMLAPI</span><span class="sxs-lookup"><span data-stu-id="7b2f1-144">XMLAPI Mode</span></span>  <br/> | <span data-ttu-id="7b2f1-145">Вкл.</span><span class="sxs-lookup"><span data-stu-id="7b2f1-145">On</span></span> <br/> |
   
7. <span data-ttu-id="7b2f1-146">Перейдите к конфигурации -\>системы конфигурации -\>SIP.</span><span class="sxs-lookup"><span data-stu-id="7b2f1-146">Navigate to Configuration-\>System Configuration-\>SIP.</span></span>
    
8. <span data-ttu-id="7b2f1-147">Проверьте следующие параметры, внося необходимые исправления:</span><span class="sxs-lookup"><span data-stu-id="7b2f1-147">Verify the following settings, correcting as needed:</span></span> 
    
   |<span data-ttu-id="7b2f1-148">**Параметр**</span><span class="sxs-lookup"><span data-stu-id="7b2f1-148">**Parameter**</span></span>|<span data-ttu-id="7b2f1-149">**Рекомендованная настройка**</span><span class="sxs-lookup"><span data-stu-id="7b2f1-149">**Recommended setting**</span></span>|
   |:-----|:-----|
   |<span data-ttu-id="7b2f1-150">Профиль 1 — DefaultTransport</span><span class="sxs-lookup"><span data-stu-id="7b2f1-150">Profile 1 - DefaultTransport</span></span>  <br/> | <span data-ttu-id="7b2f1-151">TCP</span><span class="sxs-lookup"><span data-stu-id="7b2f1-151">TCP</span></span> <br/> |
   |<span data-ttu-id="7b2f1-152">Профиль 1 — исходящий</span><span class="sxs-lookup"><span data-stu-id="7b2f1-152">Profile 1 - Outbound</span></span>  <br/> | <span data-ttu-id="7b2f1-153">Выкл.</span><span class="sxs-lookup"><span data-stu-id="7b2f1-153">Off</span></span> <br/> |
   |<span data-ttu-id="7b2f1-154">Профиль 1 - TlsVerify</span><span class="sxs-lookup"><span data-stu-id="7b2f1-154">Profile 1 - TlsVerify</span></span>  <br/> | <span data-ttu-id="7b2f1-155">Вкл.</span><span class="sxs-lookup"><span data-stu-id="7b2f1-155">On</span></span> <br/> |
   |<span data-ttu-id="7b2f1-156">Профиль 1 — тип</span><span class="sxs-lookup"><span data-stu-id="7b2f1-156">Profile 1 - Type</span></span>  <br/> | <span data-ttu-id="7b2f1-157">Cisco</span><span class="sxs-lookup"><span data-stu-id="7b2f1-157">Cisco</span></span> <br/> |
   |<span data-ttu-id="7b2f1-158">Профиль 1 — URI-адрес</span><span class="sxs-lookup"><span data-stu-id="7b2f1-158">Profile 1 - URI</span></span>  <br/> | <span data-ttu-id="7b2f1-159">Автоматически назначается во время регистрации CUCM</span><span class="sxs-lookup"><span data-stu-id="7b2f1-159">Automatically assigned at CUCM registration</span></span> <br/> |
   |<span data-ttu-id="7b2f1-160">Прокси-сервер 1 — адрес</span><span class="sxs-lookup"><span data-stu-id="7b2f1-160">Proxy 1 - Address</span></span>  <br/> |<span data-ttu-id="7b2f1-161">Имя узла CUCM</span><span class="sxs-lookup"><span data-stu-id="7b2f1-161">The host name of the CUCM</span></span>  <br/> |
   
<span data-ttu-id="7b2f1-p104">Теперь VTC настроена на взаимодействие. Чтобы службу можно было запустить, на стороне CUCM необходимо выполнить последние действия.</span><span class="sxs-lookup"><span data-stu-id="7b2f1-p104">The VTC is now configured for interoperation. Before service can begin, there are final steps to perform on the CUCM side.</span></span>
### <a name="configure-vtc-devices-on-cucm"></a><span data-ttu-id="7b2f1-164">Настройка устройств VTC в CUCM</span><span class="sxs-lookup"><span data-stu-id="7b2f1-164">Configure VTC devices on CUCM</span></span>

1. <span data-ttu-id="7b2f1-165">Выполните вход в систему CUCM и перейдите к единой Cisco CM администрирования -\>устройства -\>телефона -\>поиска.</span><span class="sxs-lookup"><span data-stu-id="7b2f1-165">Log in to CUCM and Navigate to Cisco Unified CM Administration-\>Device-\>Phone-\>Find.</span></span> 
    
2. <span data-ttu-id="7b2f1-p105">Выберите устройство VTC, которое требуется настроить. Проверьте приведенные ниже параметры на экране Phone Configuration (Конфигурация телефона), внося необходимые исправления. После изменения или проверки этих параметров, нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="7b2f1-p105">Select the VTC device to be configured. Verify the following settings on the Phone Configuration screen, correcting as needed. Once these settings have been changed or verified, click on **Save**.</span></span>
    
   |<span data-ttu-id="7b2f1-169">**Параметр**</span><span class="sxs-lookup"><span data-stu-id="7b2f1-169">**Parameter**</span></span>|<span data-ttu-id="7b2f1-170">**Рекомендованная настройка**</span><span class="sxs-lookup"><span data-stu-id="7b2f1-170">**Recommended setting**</span></span>|
   |:-----|:-----|
   |<span data-ttu-id="7b2f1-171">Сведения об устройстве — шаблон кнопки телефона</span><span class="sxs-lookup"><span data-stu-id="7b2f1-171">Device Information - Phone Button Template</span></span>  <br/> | <span data-ttu-id="7b2f1-172">Стандартный Cisco виртуального присутствия кодек C40</span><span class="sxs-lookup"><span data-stu-id="7b2f1-172">Standard Cisco Telepresence Codec C40</span></span> <br/> |
   |<span data-ttu-id="7b2f1-173">Сведения об устройстве — общий профиль телефона</span><span class="sxs-lookup"><span data-stu-id="7b2f1-173">Device Information - Common Phone Profile</span></span>  <br/> | <span data-ttu-id="7b2f1-174">Стандартный общий профиль телефона</span><span class="sxs-lookup"><span data-stu-id="7b2f1-174">Standard Common Phone Profile</span></span> <br/> |
   |<span data-ttu-id="7b2f1-175">Сведения об устройстве — пространство поиска вызовов</span><span class="sxs-lookup"><span data-stu-id="7b2f1-175">Device Information - Calling Search Space</span></span>  <br/> | <span data-ttu-id="7b2f1-176">CSS_SfBVideoInterop</span><span class="sxs-lookup"><span data-stu-id="7b2f1-176">CSS_SfBVideoInterop</span></span> <br/> |
   |<span data-ttu-id="7b2f1-177">Сведения об устройстве — пространство поиска вызовов AAR</span><span class="sxs-lookup"><span data-stu-id="7b2f1-177">Device Information - AAR Calling Search Space</span></span>  <br/> | <span data-ttu-id="7b2f1-178">CSS_SfBVideoInterop</span><span class="sxs-lookup"><span data-stu-id="7b2f1-178">CSS_SfBVideoInterop</span></span> <br/> |
   |<span data-ttu-id="7b2f1-179">Сведения об устройствах — список групп ресурсов мультимедиа</span><span class="sxs-lookup"><span data-stu-id="7b2f1-179">Device Information - Media Resource Group List</span></span>  <br/> | <span data-ttu-id="7b2f1-180">MRGL_SfBVideoInterop</span><span class="sxs-lookup"><span data-stu-id="7b2f1-180">MRGL_SfBVideoInterop</span></span> <br/> |
   |<span data-ttu-id="7b2f1-181">Специальные сведения о протоколе — профиль безопасности устройства</span><span class="sxs-lookup"><span data-stu-id="7b2f1-181">Protocol Specific Information - Device Security Profile</span></span>  <br/> | <span data-ttu-id="7b2f1-182">C40 Cisco кодек виртуального присутствия</span><span class="sxs-lookup"><span data-stu-id="7b2f1-182">Cisco Telepresence Codec C40</span></span> <br/> |
   |<span data-ttu-id="7b2f1-183">Специальные сведения о протоколе — переадресация пространства поиска вызовов</span><span class="sxs-lookup"><span data-stu-id="7b2f1-183">Protocol Specific Information - Rerouting Calling Search Space</span></span>  <br/> | <span data-ttu-id="7b2f1-184">CSS_SfBVideoInterop</span><span class="sxs-lookup"><span data-stu-id="7b2f1-184">CSS_SfBVideoInterop</span></span> <br/> |
   |<span data-ttu-id="7b2f1-185">Протокол конкретные сведения — ПОДПИСКА вызов пространство поиска</span><span class="sxs-lookup"><span data-stu-id="7b2f1-185">Protocol Specific Information - SUBSCRIBE Calling Search Space</span></span>  <br/> | <span data-ttu-id="7b2f1-186">CSS_SfBVideoInterop</span><span class="sxs-lookup"><span data-stu-id="7b2f1-186">CSS_SfBVideoInterop</span></span> <br/> |
   |<span data-ttu-id="7b2f1-187">Специальные сведения о протоколе — профиль SIP</span><span class="sxs-lookup"><span data-stu-id="7b2f1-187">Protocol Specific Information -SIP Profile</span></span>  <br/> | <span data-ttu-id="7b2f1-188">Стандартный профиль SIP для конечной точки телеприсутствия</span><span class="sxs-lookup"><span data-stu-id="7b2f1-188">Standard SIP Profile for Telepresence Endpoint</span></span> <br/> |
   
3. <span data-ttu-id="7b2f1-189">После сохранения конфигурации VTC снова перейдите к экрану Phone Configuration (Конфигурация телефона) данного устройства.</span><span class="sxs-lookup"><span data-stu-id="7b2f1-189">Once VTC configuration is saved, re-navigate to the Phone Configuration screen for the device.</span></span> <span data-ttu-id="7b2f1-190">В верхней части экрана в группе Association (Сопоставление) щелкните сопоставление для видеовзаимодействия.</span><span class="sxs-lookup"><span data-stu-id="7b2f1-190">At the top of the screen in the Association group, click on the association for the Video Interop.</span></span> <span data-ttu-id="7b2f1-191">Открывается экран Directory Number Configuration (Настройка числа каталогов).</span><span class="sxs-lookup"><span data-stu-id="7b2f1-191">This brings up the Directory Number Configuration screen.</span></span> 
    
4. <span data-ttu-id="7b2f1-192">Проверьте следующие параметры, внося необходимые исправления:</span><span class="sxs-lookup"><span data-stu-id="7b2f1-192">Verify the following settings, correcting as needed:</span></span> 
    
    <span data-ttu-id="7b2f1-193">Внесите соответствующие изменения, как показано на экране Directory Number Information (Сведения о числе каталогов) и Directory Number Settings (Параметры числа каталогов).</span><span class="sxs-lookup"><span data-stu-id="7b2f1-193">Make the appropriate changes as shown to the Directory Number Information and the Directory Number Settings.</span></span>
    
   |<span data-ttu-id="7b2f1-194">**Параметр**</span><span class="sxs-lookup"><span data-stu-id="7b2f1-194">**Parameter**</span></span>|<span data-ttu-id="7b2f1-195">**Рекомендованная настройка**</span><span class="sxs-lookup"><span data-stu-id="7b2f1-195">**Recommended setting**</span></span>|
   |:-----|:-----|
   | <span data-ttu-id="7b2f1-196">Сведения о числе каталогов — раздел маршрута</span><span class="sxs-lookup"><span data-stu-id="7b2f1-196">Directory Number Information - Route Partition</span></span> <br/> | <span data-ttu-id="7b2f1-197">SfBVideoInterop_RoutePartition</span><span class="sxs-lookup"><span data-stu-id="7b2f1-197">SfBVideoInterop_RoutePartition</span></span> <br/> |
   |<span data-ttu-id="7b2f1-198">Сведения о числе каталогов — пространство поиска вызовов</span><span class="sxs-lookup"><span data-stu-id="7b2f1-198">Directory Number Settings - Calling Search Space</span></span>  <br/> | <span data-ttu-id="7b2f1-199">CSS_SfBVideoInterop</span><span class="sxs-lookup"><span data-stu-id="7b2f1-199">CSS_SfBVideoInterop</span></span> <br/> |
   |<span data-ttu-id="7b2f1-200">Альтернативная сторона MLPP и параметры уровня доступа к конфиденциальной информации — пространство поиска вызовов MLPP</span><span class="sxs-lookup"><span data-stu-id="7b2f1-200">MLPP Alternate Party and Confidential Access Level Settings - MLPP Calling Search Space</span></span>  <br/> | <span data-ttu-id="7b2f1-201">CSS_SfBVideoInterop</span><span class="sxs-lookup"><span data-stu-id="7b2f1-201">CSS_SfBVideoInterop</span></span> <br/> |
   |<span data-ttu-id="7b2f1-202">Строка 1 на устройстве - отображения (идентификатор вызывающего абонента)</span><span class="sxs-lookup"><span data-stu-id="7b2f1-202">Line 1 on Device - Display (Caller ID)</span></span>  <br/> | <span data-ttu-id="7b2f1-203">По желанию</span><span class="sxs-lookup"><span data-stu-id="7b2f1-203">As desired</span></span> <br/> |
   |<span data-ttu-id="7b2f1-204">Строка 1 на устройстве - ASCII отображения (идентификатор вызывающего абонента)</span><span class="sxs-lookup"><span data-stu-id="7b2f1-204">Line 1 on Device - ASCII Display (Caller ID)</span></span>  <br/> | <span data-ttu-id="7b2f1-205">По желанию</span><span class="sxs-lookup"><span data-stu-id="7b2f1-205">As desired</span></span> <br/> |
   
5. <span data-ttu-id="7b2f1-206">После завершения прокрутите экран вверх и нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="7b2f1-206">When finished, scroll to the top of the screen and press **Save**.</span></span> 
    
<span data-ttu-id="7b2f1-p107">Конфигурация для данного устройства VTC завершена. Этот процесс потребуется повторить для остальных устройств VTC предприятия.</span><span class="sxs-lookup"><span data-stu-id="7b2f1-p107">Configuration is now complete for this VTC device. You will need to repeat this process for other VTC devices in your enterprise.</span></span>

