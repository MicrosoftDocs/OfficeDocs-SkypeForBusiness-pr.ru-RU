---
title: Устранение неполадок с развертыванием Cloud Connector
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 12/5/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: e6cf58cc-dbd9-4f35-a51a-3e2fea71b5a5
description: Устранение неполадок в развертывании Cloud Connector Edition.
ms.openlocfilehash: 9da10f1b3e8dd800e57b46f6a56eb6a82c29e22c
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51094827"
---
# <a name="troubleshoot-your-cloud-connector-deployment"></a><span data-ttu-id="33402-103">Устранение неполадок с развертыванием Cloud Connector</span><span class="sxs-lookup"><span data-stu-id="33402-103">Troubleshoot your Cloud Connector deployment</span></span>

> [!Important]
> <span data-ttu-id="33402-104">Cloud Connector Edition завершит карьеру 31 июля 2021 г. вместе со Skype для бизнеса Online.</span><span class="sxs-lookup"><span data-stu-id="33402-104">Cloud Connector Edition will retire July 31, 2021 along with Skype for Business Online.</span></span> <span data-ttu-id="33402-105">После обновления организации до Teams узнайте, как подключить сеть локальной телефонии к Teams с помощью прямой [маршрутизации.](/MicrosoftTeams/direct-routing-landing-page)</span><span class="sxs-lookup"><span data-stu-id="33402-105">Once your organization has upgraded to Teams, learn how to connect your on-premises telephony network to Teams using [Direct Routing](/MicrosoftTeams/direct-routing-landing-page).</span></span>
 
<span data-ttu-id="33402-106">Устранение неполадок в развертывании Cloud Connector Edition.</span><span class="sxs-lookup"><span data-stu-id="33402-106">Troubleshoot your Cloud Connector Edition deployment.</span></span>
  
<span data-ttu-id="33402-107">В этом разделе описываются решения распространенных проблем с развертываниями Cloud Connector Edition.</span><span class="sxs-lookup"><span data-stu-id="33402-107">This topic describes solutions to common issues with Cloud Connector Edition deployments.</span></span> <span data-ttu-id="33402-108">Если у вас возникли проблемы с вызовами в и из сети общедоступных телефонных звонков (PSTN), вы можете исследовать, следуя решениям, описанным в этой теме.</span><span class="sxs-lookup"><span data-stu-id="33402-108">If you are experiencing issues with calls to and from the Public Switched Telephone Network (PSTN), you can investigate by following the solutions described in this topic.</span></span>
  
<span data-ttu-id="33402-109">Cloud Connector предоставляет встроенные механизмы автоматического решения некоторых проблем.</span><span class="sxs-lookup"><span data-stu-id="33402-109">Cloud Connector provides built-in mechanisms for automatically resolving some issues.</span></span> <span data-ttu-id="33402-110">Автоматический процесс обнаружения ищет потенциальные проблемы с устройствами облачного соединителя и по возможности принимает меры по исправлению этих проблем без вмешательства администратора.</span><span class="sxs-lookup"><span data-stu-id="33402-110">An automatic detection process looks for potential issues with the Cloud Connector appliances, and, if possible, takes corrective action to resolve those issues without the need for administrator intervention.</span></span> <span data-ttu-id="33402-111">Процесс обнаружения работает следующим образом:</span><span class="sxs-lookup"><span data-stu-id="33402-111">The detection process works as follows:</span></span>
  
- <span data-ttu-id="33402-112">**Последовательность обнаружения:** Служба управления облачным соединитетелем выполняет процесс каждые 60 секунд для обнаружения того, не работает ли устройство.</span><span class="sxs-lookup"><span data-stu-id="33402-112">**Detection sequence:** The Cloud Connector Management service runs a process every 60 seconds for detecting whether an appliance is down.</span></span> <span data-ttu-id="33402-113">В версии Cloud Connector 2.0 и более поздней версии процесс обнаружения использует переключатель Skype для бизнеса Corpnet для подключения PowerShell к машинам облачного соединитела; для версий, предшествующих 2.0, в процессе обнаружения используется переключатель управления облачным соединитетелем.</span><span class="sxs-lookup"><span data-stu-id="33402-113">In Cloud Connector version 2.0 and later, the detection process uses the Skype for Business Corpnet switch for making PowerShell connections to the Cloud Connector machines; for versions previous to 2.0, the detection process uses the Cloud Connector management switch.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="33402-114">Для успешного автоматического восстановления необходимо подключение к сети между хост-компьютерами и виртуальными машинами через переключатель хост-сети.</span><span class="sxs-lookup"><span data-stu-id="33402-114">For automatic recovery to succeed, there must be network connectivity between the host and virtual machines over the host network switch.</span></span> <span data-ttu-id="33402-115">Убедитесь, что проверьте подключение к сети, чтобы обеспечить успешное автоматическое обнаружение и восстановление.</span><span class="sxs-lookup"><span data-stu-id="33402-115">Be sure to check network connectivity to ensure that automatic detection and recovery can succeed.</span></span> 
  
- <span data-ttu-id="33402-116">**Мониторинг:** Следующие службы отслеживаются в версии Cloud Connector 2.0 и более поздней версии:</span><span class="sxs-lookup"><span data-stu-id="33402-116">**Monitoring:** The following services are monitored in Cloud Connector version 2.0 and later:</span></span>
    
  - <span data-ttu-id="33402-117">Виртуальные машины не подключены к корпоративным или виртуальным коммутаторам облачного соединитела</span><span class="sxs-lookup"><span data-stu-id="33402-117">Virtual Machines are not connected to the Cloud Connector Corporate or Internet virtual switches</span></span>
    
  - <span data-ttu-id="33402-118">Виртуальные машины находятся в сохраненных или остановленных состояниях</span><span class="sxs-lookup"><span data-stu-id="33402-118">Virtual Machines are in a saved or stopped status</span></span>
    
  - <span data-ttu-id="33402-119">Службы центрального сервера управления: REPLICA, MASTER</span><span class="sxs-lookup"><span data-stu-id="33402-119">Central Management Server services: REPLICA, MASTER</span></span>
    
  - <span data-ttu-id="33402-120">Службы-посредники: REPLICA, RTCSRV и MEDSVC</span><span class="sxs-lookup"><span data-stu-id="33402-120">Mediation Server services: REPLICA, RTCSRV and MEDSVC</span></span>
    
  - <span data-ttu-id="33402-121">Службы edge Server: REPLICA, RTCSRV, RTCDATAPROXY, RTCMRAUTH, RTCMEDIARELAY</span><span class="sxs-lookup"><span data-stu-id="33402-121">Edge Server services: REPLICA, RTCSRV, RTCDATAPROXY, RTCMRAUTH, RTCMEDIARELAY</span></span>
    
  - <span data-ttu-id="33402-122">Правила входящий брандмауэр отключены для CS RTCSRV на краевом сервере, CS RTCMEDSRV на сервере-посреднике</span><span class="sxs-lookup"><span data-stu-id="33402-122">Inbound firewall rules are disabled for CS RTCSRV on Edge server, CS RTCMEDSRV on Mediation server</span></span>
    
    <span data-ttu-id="33402-123">В версии Cloud Connector 1.4.2 отслеживаются только следующие службы:</span><span class="sxs-lookup"><span data-stu-id="33402-123">In Cloud Connector version 1.4.2, only the following services are monitored:</span></span>
    
  - <span data-ttu-id="33402-124">Службы-посредники: RTCSRV и MEDSVC</span><span class="sxs-lookup"><span data-stu-id="33402-124">Mediation Server services: RTCSRV and MEDSVC</span></span>
    
  - <span data-ttu-id="33402-125">Служба edge Server: RTCSRV</span><span class="sxs-lookup"><span data-stu-id="33402-125">Edge Server service: RTCSRV</span></span>
    
- <span data-ttu-id="33402-126">**Процесс восстановления:** Если какие-либо отслеживаемые службы не будут работать, устройство будет помечено вниз, а службы будут остановлены и помечены вручную до тех пор, пока не будут устранены все проблемы.</span><span class="sxs-lookup"><span data-stu-id="33402-126">**Recovery process:** If any monitored services are down, an appliance is marked down, and services are stopped and marked manual until all issues can be resolved.</span></span> <span data-ttu-id="33402-127">Это предотвратит маршрутику вызовов на устройство, которое может привести к сбоям вызовов.</span><span class="sxs-lookup"><span data-stu-id="33402-127">This will prevent calls from routing to an appliance that may cause call failures.</span></span>
    
    <span data-ttu-id="33402-128">Служба управления облачными соединителями повторно выполнит автоматическое восстановление следующим образом.</span><span class="sxs-lookup"><span data-stu-id="33402-128">The Cloud Connector Management service will retry automatic recovery as follows</span></span>
    
  - <span data-ttu-id="33402-129">Начальный интервал повторной работы — каждые 10 секунд с максимальным интервалом в один час.</span><span class="sxs-lookup"><span data-stu-id="33402-129">The initial retry interval is every ten seconds with a maximum interval time of one hour.</span></span>
    
  - <span data-ttu-id="33402-130">Для первых трех попыток восстановления интервал составляет 10 секунд.</span><span class="sxs-lookup"><span data-stu-id="33402-130">For the first three recovery attempts, the interval time is 10 seconds.</span></span> <span data-ttu-id="33402-131">Начиная с четвертой повторной работы, время интервала увеличивается в два раза по сравнению с предыдущим интервалом.</span><span class="sxs-lookup"><span data-stu-id="33402-131">Starting from the fourth retry, the interval time increases by two times the previous interval time.</span></span> <span data-ttu-id="33402-132">Например, четвертая повторное повторить будет происходить через 20 секунд, пятая за 40 секунд и так далее.</span><span class="sxs-lookup"><span data-stu-id="33402-132">For example, the fourth retry will occur in 20 seconds, the fifth in 40 seconds, and so on.</span></span> 
    
  - <span data-ttu-id="33402-133">Когда будет достигнуто максимальное время интервала в один час, повторы будут продолжаться один раз в час.</span><span class="sxs-lookup"><span data-stu-id="33402-133">When the maximum interval time of one hour is reached, retries will continue once per hour.</span></span>
    
  - <span data-ttu-id="33402-134">При успешном восстановлении значения интервала и повторной оценки заданные для них начальные значения.</span><span class="sxs-lookup"><span data-stu-id="33402-134">When recovery is successful, the interval and retry counts are set to their initial values.</span></span>
    
  - <span data-ttu-id="33402-135">Если служба управления перезапущена, количество интервалов и повторов сбрасывается с первоначальных значений.</span><span class="sxs-lookup"><span data-stu-id="33402-135">If the Management service is restarted, the interval and retry counts are reset to their initial values.</span></span>
    
## <a name="troubleshooting"></a><span data-ttu-id="33402-136">Устранение неполадок</span><span class="sxs-lookup"><span data-stu-id="33402-136">Troubleshooting</span></span>

<span data-ttu-id="33402-137">Ниже ниже поданы решения распространенных проблем:</span><span class="sxs-lookup"><span data-stu-id="33402-137">Following are solutions to commonly encountered issues:</span></span>
  
- <span data-ttu-id="33402-138">**Проблема. При запуске сценариев развертывания развертывание сбой или остановка ответа. После входа в каждый VM IP-адрес отсутствует или неправильная для службы управления/внутренней и внешней службы.**</span><span class="sxs-lookup"><span data-stu-id="33402-138">**Issue: Deployment fails or stops responding when running the deployment scripts. After logging on to each VM, the IP address is missing or incorrect for the Management/Internal/External NIC.**</span></span>
    
    <span data-ttu-id="33402-139">**Разрешение:** Эта проблема не может быть решена автоматически.</span><span class="sxs-lookup"><span data-stu-id="33402-139">**Resolution:** This issue cannot be resolved automatically.</span></span> <span data-ttu-id="33402-140">Во время работы они не могут быть добавлены в VMs.</span><span class="sxs-lookup"><span data-stu-id="33402-140">NICs cannot be added to VMs while they are running.</span></span> <span data-ttu-id="33402-141">Пожалуйста, отключите и удалите эти VMs в диспетчере hyper-v, а затем запустите следующие команды:</span><span class="sxs-lookup"><span data-stu-id="33402-141">Please shut down and remove these VMs in hyper-v manager, then run the following cmdlets:</span></span>
    
  ```powershell
  Uninstall-CcAppliance
  ```

  ```powershell
  Install-CcAppliance
  ```

- 
    
    <span data-ttu-id="33402-142">**Проблема. После установки сервера Active Directory и леса сервер CMS Server и/или сервер-посредник не присоединились к домену правильно.**</span><span class="sxs-lookup"><span data-stu-id="33402-142">**Issue: After the Active Directory Server and forest are installed, the CMS Server and/or Mediation Server did not join the domain correctly.**</span></span>
    
    <span data-ttu-id="33402-143">**Разрешение:** Чтобы устранить эту проблему, необходимо предпринять следующие действия:</span><span class="sxs-lookup"><span data-stu-id="33402-143">**Resolution:** To resolve this issue, take the following steps:</span></span>
    
  - <span data-ttu-id="33402-144">Войдите на сервер Active Directory Server и убедитесь, что домен создан правильно.</span><span class="sxs-lookup"><span data-stu-id="33402-144">Log on to the Active Directory Server and verify that the domain was created correctly.</span></span>
    
  - <span data-ttu-id="33402-145">Войдите на сервер CMS/Mediation Server и убедитесь, что на корневом NIC назначен допустимый IP-адрес, а допустимый статический IP-адрес и DNS настроены как IP-адрес сервера AD.</span><span class="sxs-lookup"><span data-stu-id="33402-145">Log on to the CMS/Mediation Server and verify that on the corpnet NIC a valid IP address is assigned, and that valid static IP and DNS is configured as the AD server's IP address.</span></span>
    
  - <span data-ttu-id="33402-146">Войдите на сервер CMS/Mediation Server и откройте командную подсказку.</span><span class="sxs-lookup"><span data-stu-id="33402-146">Log on to the CMS/Mediation Server, and open a command prompt.</span></span> <span data-ttu-id="33402-147">Убедитесь, что вы можете получить доступ к FQDN и IP-адресу сервера Active Directory Server.</span><span class="sxs-lookup"><span data-stu-id="33402-147">Make sure you can ping the FQDN and IP address of the Active Directory Server.</span></span> <span data-ttu-id="33402-148">Если это невозможно, может возникнуть конфликт IP-адресов.</span><span class="sxs-lookup"><span data-stu-id="33402-148">If you cannot, there may be an IP address conflict.</span></span> <span data-ttu-id="33402-149">Попробуйте назначить новый IP для Active Directory и соответствующим образом обновить DNS на сервере CMS/Mediation.</span><span class="sxs-lookup"><span data-stu-id="33402-149">Please try to assign a new IP for Active Directory and update DNS on the CMS/Mediation server accordingly.</span></span>
    
- <span data-ttu-id="33402-150">**Проблема. Вы получаете следующее сообщение об ошибке" Remove-VMSwitch: Failed при удалении виртуального переключателя Ethernet. Виртуальный переключатель "Переключатель управления облачным соединитетелем" не может быть удален, так как он используется с помощью виртуальных машин или для детских пулов".**</span><span class="sxs-lookup"><span data-stu-id="33402-150">**Issue: You receive the following error message, "Remove-VMSwitch : Failed while removing virtual Ethernet switch. The virtual switch 'Cloud Connector Management Switch' cannot be deleted because it is being used by running virtual machines or assigned to child pools."**</span></span>
    
    <span data-ttu-id="33402-151">**Разрешение:** После развертывания не был удален "Переключатель управления облачным соединитетелем".</span><span class="sxs-lookup"><span data-stu-id="33402-151">**Resolution:** The "Cloud Connector Management Switch" was not deleted after the deployment.</span></span> <span data-ttu-id="33402-152">Если вы нажмёте эту ошибку, перейдите к менеджеру Hyper-v и убедитесь, что к ней по-прежнему не подключен виртуальный компьютер.</span><span class="sxs-lookup"><span data-stu-id="33402-152">If you hit this error, please go to Hyper-v manager and verify that there is not still a virtual machine still connected to it.</span></span> <span data-ttu-id="33402-153">Если виртуальные машины по-прежнему подключены, отключите их и удалите переключатель управления.</span><span class="sxs-lookup"><span data-stu-id="33402-153">If there are virtual machines still connected, disconnect them and delete the management switch.</span></span> <span data-ttu-id="33402-154">Если переключатель управления по-прежнему не удается удалить, перезапустите хост-сервер и повторите попытку.</span><span class="sxs-lookup"><span data-stu-id="33402-154">If the management switch still cannot be deleted, restart the host server and try again.</span></span>
    
- <span data-ttu-id="33402-155">**Проблема. Вы получаете следующее сообщение об ошибке: "Не удалось запустить службу RTCMRAUTH. Убедитесь, что служба не отключена".**</span><span class="sxs-lookup"><span data-stu-id="33402-155">**Issue: You receive the following error message, "Service RTCMRAUTH failed to start. Check to make sure the service is not disabled."**</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="33402-156">Эта проблема применяется только к версиям облачного соединитела раньше 1.4.2.</span><span class="sxs-lookup"><span data-stu-id="33402-156">This issue only applies to Cloud Connector versions earlier than 1.4.2.</span></span> 
  
    <span data-ttu-id="33402-157">Сбой в запуске также может быть из-за того, что этот сервер переднего конца был ранее сбой (с помощью компьютера сбой более).</span><span class="sxs-lookup"><span data-stu-id="33402-157">The failure to start could also be because this Front End server was previously failed over (using computer fail over).</span></span> <span data-ttu-id="33402-158">Если это так, пожалуйста, вызывайте сбой обратно (с помощью компьютера сбой обратно).</span><span class="sxs-lookup"><span data-stu-id="33402-158">If that's the case, please invoke fail back (using computer fail back).</span></span>
    
    <span data-ttu-id="33402-159">**Разрешение:** Эта проблема происходит на краевом сервере, когда корневой сертификат CA или промежуточный сертификат ЦС не доверяют edge Server.</span><span class="sxs-lookup"><span data-stu-id="33402-159">**Resolution:** This issue happens on an Edge Server when the root CA certificate or intermediate CA certificate is not trusted by the Edge Server.</span></span> <span data-ttu-id="33402-160">Даже если внешний сертификат можно импортировать, но цепочка сертификатов нарушена.</span><span class="sxs-lookup"><span data-stu-id="33402-160">Even if the external certificate can be imported but the certificate chain is broken.</span></span> <span data-ttu-id="33402-161">При этом условии служба RTCMRAUTH и/или RTCSRV не может запускаться.</span><span class="sxs-lookup"><span data-stu-id="33402-161">Under this condition, the RTCMRAUTH and/or RTCSRV service can not start.</span></span>
    
    <span data-ttu-id="33402-162">Ввозимый корневой сертификат CA и все промежуточные сертификаты ЦС внешнего сертификата вручную в Edge Server, а затем перезапустите edge Server.</span><span class="sxs-lookup"><span data-stu-id="33402-162">Please import the root CA certificate and all intermediate CA certificates of your external certificate manually into the Edge Server and then restart the Edge Server.</span></span> <span data-ttu-id="33402-163">После запуска служб RTCMRAUTH и RTCSRV на краевом сервере перейдите на хост-сервер, запустите консоль PowerShell в качестве администратора и запустите следующий комдлет, чтобы перейти на новое развертывание:</span><span class="sxs-lookup"><span data-stu-id="33402-163">After you see the RTCMRAUTH and RTCSRV services started on the Edge Server, go back to your host server, launch a PowerShell console as administrator, and run following cmdlet to switch to the new deployment:</span></span>
    
  ```powershell
  Switch-CcVersion
  ```

- 
    
    <span data-ttu-id="33402-164">**Проблема. При применении обновлений Windows сервер хост-сервера был перезапущен, а вызовы, служив на сервере, сбои.**</span><span class="sxs-lookup"><span data-stu-id="33402-164">**Issue: The host server was restarted when Windows updates were applied, and calls serviced by the server are failing.**</span></span>
    
    <span data-ttu-id="33402-165">**Разрешение:** Если вы развернули среду с высокой доступностью, корпорация Майкрософт предоставляет комлет, который поможет переместить одну хост-машину (экземпляр развертывания) в текущую топологию или выйти из нее при проверке и установке обновления Windows вручную.</span><span class="sxs-lookup"><span data-stu-id="33402-165">**Resolution:** If you deployed a high availability environment, Microsoft provides a cmdlet to help move one host machine (deployment instance) into or out of the current topology when you check and install Windows update manually.</span></span> <span data-ttu-id="33402-166">Чтобы выполнить следующие действия, используйте следующие действия:</span><span class="sxs-lookup"><span data-stu-id="33402-166">Use the following steps to accomplish this:</span></span>
    
1. <span data-ttu-id="33402-167">На сервере хост-сервера запустите консоль PowerShell в качестве администратора, а затем запустите:</span><span class="sxs-lookup"><span data-stu-id="33402-167">On the host server, start a PowerShell console as administrator, then run:</span></span>
    
   ```powershell
   Enter-CcUpdate
   ```

2. <span data-ttu-id="33402-168">Проверьте обновления и установите все доступные обновления.</span><span class="sxs-lookup"><span data-stu-id="33402-168">Check for updates and install any that are available.</span></span>
    
3. <span data-ttu-id="33402-169">В консоли PowerShell запустите следующий cmdlet:</span><span class="sxs-lookup"><span data-stu-id="33402-169">In the PowerShell console, run the following cmdlet:</span></span>
    
   ```powershell
   Exit-CcUpdate
   ```

- 
    
    <span data-ttu-id="33402-170">**Проблема. При вызове клиента Skype для бизнеса с помощью номера PSTN вызов не может быть перенастроен на конференцию, приглашая другой номер PSTN.**</span><span class="sxs-lookup"><span data-stu-id="33402-170">**Issue: When a call is made from a Skype for Business client using a PSTN number, the call cannot be escalated to a conference by inviting another PSTN number.**</span></span>
    
    <span data-ttu-id="33402-171">**Разрешение:** Чтобы устранить эту проблему, см. [в руб. Настройка параметров гибридного сервера-посредника](configure-cloud-connector-integration-with-your-office-365-tenant.md#BKMK_ConfigureMediationServer)в Интернете.</span><span class="sxs-lookup"><span data-stu-id="33402-171">**Resolution:** To resolve this issue, see [Configure online hybrid Mediation Server Settings](configure-cloud-connector-integration-with-your-office-365-tenant.md#BKMK_ConfigureMediationServer).</span></span>
    
- <span data-ttu-id="33402-172">**Проблема. При установке сервера Active Directory отображается предупреждение об обновлении Windows. "Автоматическое обновление Windows не включено. Чтобы убедиться, что ваша недавно установленная роль или функция автоматически обновляется, включите обновление Windows".**</span><span class="sxs-lookup"><span data-stu-id="33402-172">**Issue: A warning message is displayed about Windows Update when you are installing Active Directory server - "Windows automatic updating is not enabled. To ensure that your newly-installed role or feature is automatically updated, turn on Windows Update."**</span></span>
    
    <span data-ttu-id="33402-173">**Разрешение:** Запустите сеанс удаленной powerShell для клиента с помощью учетных данных администратора Skype для бизнеса, а затем запустите следующий cmdlet, чтобы проверить конфигурацию _EnableAutoUpdate_ вашего сайта:</span><span class="sxs-lookup"><span data-stu-id="33402-173">**Resolution:** Launch a Tenant Remote PowerShell session using Skype for Business tenant admin credentials, then run the following cmdlet to check the _EnableAutoUpdate_ configuration of your site:</span></span>
    
  ```powershell
  Get-CsHybridPSTNSite
  ```

    <span data-ttu-id="33402-174">Если  _значение EnableAutoUpdate_ заданной для **True,** вы можете смело игнорировать это предупреждение, так как служба CCEManagement будет обрабатывать загрузку и установку обновлений Windows для виртуальных машин и хост-сервера.</span><span class="sxs-lookup"><span data-stu-id="33402-174">If  _EnableAutoUpdate_ is set to **True**, you can safely ignore this warning message because the CCEManagement service will handle downloading and installing Windows updates for both virtual machines and the host server.</span></span> <span data-ttu-id="33402-175">Если _EnableAutoUpdate_ задавалось **false,** запустите следующий кодлет, чтобы задать его **true.**</span><span class="sxs-lookup"><span data-stu-id="33402-175">If  _EnableAutoUpdate_ is set to **False**, run following cmdlet to set it to **True**.</span></span>
    
  ```powershell
  Set-CsHybridPSTNSite -EnableAutoUpdate $true
  ```

    <span data-ttu-id="33402-176">Кроме того, вы можете вручную проверять и устанавливать обновления.</span><span class="sxs-lookup"><span data-stu-id="33402-176">Alternatively, you can manually check for and install updates.</span></span> <span data-ttu-id="33402-177">(см. следующий раздел).</span><span class="sxs-lookup"><span data-stu-id="33402-177">See the next section.</span></span>
    
- <span data-ttu-id="33402-178">**Проблема. Вы получаете сообщение об ошибке: не удается зарегистрировать устройство из-за текущего ввода/конфигурации или или конфликтов с существующим \<SiteName\> \<ApplianceName\> \<Mediation Server FQDN\> \<Mediation Server IP Address\> устройством(ы). Удалите устройство конфликтов или обновите сведения о входе или конфигурации, а затем снова зарегистрируйтесь. ' при запуске Register-CcAppliance для регистрации текущего устройства в Интернете.**</span><span class="sxs-lookup"><span data-stu-id="33402-178">**Issue: You receive an error message: Cannot register appliance because your current input/configuration \<SiteName\> or \<ApplianceName\> or \<Mediation Server FQDN\> or \<Mediation Server IP Address\> conflicts with existing appliance(s). Remove conflict appliance or update your input/configuration information then register again. ' when run Register-CcAppliance to register current appliance to online.**</span></span>
    
    <span data-ttu-id="33402-179">**Разрешение:** Значения для \<ApplianceName\> и должны \<Mediation Server FQDN\> быть уникальными \<Mediation Server IP Address\> и использоваться только для одной регистрации устройства.</span><span class="sxs-lookup"><span data-stu-id="33402-179">**Resolution:** Values for the \<ApplianceName\>, \<Mediation Server FQDN\> and \<Mediation Server IP Address\> must be unique and only used for one appliance registration.</span></span> <span data-ttu-id="33402-180">По умолчанию происходит \<ApplianceName\> от имени хоста.</span><span class="sxs-lookup"><span data-stu-id="33402-180">By default, \<ApplianceName\> comes from the host name.</span></span> <span data-ttu-id="33402-181">\<Mediation Server FQDN\> и \<Mediation Server IP Address\> определяется в файле ini конфигурации.</span><span class="sxs-lookup"><span data-stu-id="33402-181">\<Mediation Server FQDN\> and \<Mediation Server IP Address\> defined in configuration ini file.</span></span>
    
    <span data-ttu-id="33402-182">Например, использование (ApplianceName= MyserverNew, Сервер-посредник FQDN=ms.contoso.com, IP-адрес сервера-посредника=10.10.10.10) для регистрации в SiteName=MySite, но если имеется зарегистрированное устройство (ApplianceName= Myserver, Mediation Server FQDN=ms.contoso.com, IP-адрес сервера-посредника=10.10.10), у вас будет конфликт.</span><span class="sxs-lookup"><span data-stu-id="33402-182">For example, using (ApplianceName= MyserverNew, Mediation Server FQDN=ms.contoso.com, Mediation Server IP Address=10.10.10.10) to register to SiteName=MySite, but if there is a registered appliance (ApplianceName= Myserver, Mediation Server FQDN=ms.contoso.com, Mediation Server IP Address=10.10.10.10), you will have the conflict.</span></span>
    
    <span data-ttu-id="33402-183">Сначала проверьте файл CloudConnector.ini в разделе Каталог ApplianceRoot.</span><span class="sxs-lookup"><span data-stu-id="33402-183">First, please check your CloudConnector.ini file in ApplianceRoot directory section.</span></span> <span data-ttu-id="33402-184">Вы получите \<SiteName\> и значения в \<Mediation Server FQDN\> \<Mediation Server IP Address\> файле.</span><span class="sxs-lookup"><span data-stu-id="33402-184">You will get \<SiteName\>, \<Mediation Server FQDN\> and \<Mediation Server IP Address\> values in the file.</span></span> <span data-ttu-id="33402-185">\<ApplianceName\> это имя сервера хост-сервера.</span><span class="sxs-lookup"><span data-stu-id="33402-185">\<ApplianceName\> is your host server name.</span></span>
    
    <span data-ttu-id="33402-186">Во-вторых, запустите удаленную powerShell клиента с помощью учетных данных администратора клиента Skype для бизнеса, а затем запустите следующий cmdlet для проверки зарегистрированного устройства (s).</span><span class="sxs-lookup"><span data-stu-id="33402-186">Second, Launch Tenant Remote PowerShell using your Skype for Business tenant admin credentials, then run the following cmdlet to check the registered appliance(s).</span></span>
    
  ```powershell
  Get-CsHybridPSTNAppliance
  ```

    <span data-ttu-id="33402-187">После выявления конфликтов можно обновить CloudConnector.ini с информацией, которая соответствует зарегистрированным устройствам, или отозарегистрировать существующий прибор для разрешения конфликтов.</span><span class="sxs-lookup"><span data-stu-id="33402-187">After identifying any conflicts, you can either update your CloudConnector.ini file with information that matches the registered appliance, or unregister the existing appliance to resolve the conflicts.</span></span>
    
  ```powershell
  Unregister-CsHybridPSTNAppliance -Force
  ```

    
- <span data-ttu-id="33402-188">**Проблема. Get-CcRunningVersion возвращает пустое значение, если на хосте запущен развернутый прибор.**</span><span class="sxs-lookup"><span data-stu-id="33402-188">**Issue: The Get-CcRunningVersion cmdlet returns an empty value if there is a deployed appliance running on the host.**</span></span>
    
  <span data-ttu-id="33402-189">**Разрешение:** Это может произойти при обновлении с 1.3.4 или 1.3.8 до 1.4.1.</span><span class="sxs-lookup"><span data-stu-id="33402-189">**Resolution:** This can happen when you upgrade from 1.3.4 or 1.3.8 to 1.4.1.</span></span> <span data-ttu-id="33402-190">После установки версии 1.4.1 с помощью .msi необходимо выполнить перед запуском любого `Register-CcAppliance` другого cmdlet.</span><span class="sxs-lookup"><span data-stu-id="33402-190">After you install version 1.4.1 with the .msi, you must run `Register-CcAppliance` before you run any other cmdlet.</span></span> <span data-ttu-id="33402-191">`Register-CcAppliance` будет перенесен файл module.ini с %UserProfile%\CloudConnector на %ProgramData%\CloudConnector.</span><span class="sxs-lookup"><span data-stu-id="33402-191">`Register-CcAppliance` will migrate the module.ini file from %UserProfile%\CloudConnector to %ProgramData%\CloudConnector.</span></span> <span data-ttu-id="33402-192">Если вы его пропустили, module.ini будет создан в папке %ProgramData%\CloudConnector и заменит сведения о запущенной или резервной версии для 1.3.4 или 1.3.8.</span><span class="sxs-lookup"><span data-stu-id="33402-192">If you missed it, a new module.ini will be created in %ProgramData%\CloudConnector folder and replace the running/backup version information for 1.3.4 or 1.3.8.</span></span>
    
  <span data-ttu-id="33402-193">Сравнение module.ini файлов в папке %UserProfile%\CloudConnector и %ProgramData%\CloudConnector.</span><span class="sxs-lookup"><span data-stu-id="33402-193">Compare module.ini files in %UserProfile%\CloudConnector and %ProgramData%\CloudConnector folder.</span></span> <span data-ttu-id="33402-194">Если есть различия, удалите файл module.ini в %ProgramData%\CloudConnector и повторно. `Register-CcAppliance`</span><span class="sxs-lookup"><span data-stu-id="33402-194">If there are differences, delete the module.ini file in %ProgramData%\CloudConnector and rerun  `Register-CcAppliance`.</span></span> <span data-ttu-id="33402-195">Вы также можете вручную изменить файл в правильную версию запуска и резервного копирования.</span><span class="sxs-lookup"><span data-stu-id="33402-195">You could also modify the file manually to the correct running and backup version.</span></span>
    
- <span data-ttu-id="33402-196">**Проблема. После запуска Switch-CcVersion для перехода на старую версию, которая отличается от текущей версии скрипта, поддержка высокой доступности для этой старой версии не поддерживается.**</span><span class="sxs-lookup"><span data-stu-id="33402-196">**Issue: After you run the Switch-CcVersion cmdlet to switch to an old version which is different from current script version, there is no High Availability support for this old version.**</span></span>
    
    <span data-ttu-id="33402-197">**Разрешение:** Например, вы обновили с 1.4.1 до 1.4.2.</span><span class="sxs-lookup"><span data-stu-id="33402-197">**Resolution:** For example, you have upgraded from 1.4.1 to 1.4.2.</span></span> <span data-ttu-id="33402-198">Текущая версия скрипта, которую можно определить с помощью запуска, и запущенная версия, которую можно определить при запуске, — `Get-CcVersion`  `Get-CcRunningVersion` 1.4.2.</span><span class="sxs-lookup"><span data-stu-id="33402-198">Your current script version, which can be determined by running `Get-CcVersion`, and your running version, which can be determined by running  `Get-CcRunningVersion` are both 1.4.2.</span></span> <span data-ttu-id="33402-199">В это время при запуске для переключения запущенной версии на 1.4.1 поддержка высокой доступности для этой старой `Switch-CcVersion` версии не будет.</span><span class="sxs-lookup"><span data-stu-id="33402-199">At this time, if you run `Switch-CcVersion` to switch the running version back to 1.4.1, then there will be no High Availability support for this old version.</span></span>
    
    <span data-ttu-id="33402-200">Чтобы получить полную поддержку высокой доступности, переключение на 1.4.2, поэтому запущенная версия и версия скрипта одинаковы.</span><span class="sxs-lookup"><span data-stu-id="33402-200">To get full High Availability support, please switch back to 1.4.2, so the running version and script version are the same.</span></span> <span data-ttu-id="33402-201">Если у вас возникли проблемы с развертыванием 1.4.2, необходимо как можно скорее удалить его и переустановить.</span><span class="sxs-lookup"><span data-stu-id="33402-201">If you are experiencing problems with your 1.4.2 deployment, please uninstall and reinstall it as soon as possible.</span></span>
    
- <span data-ttu-id="33402-202">**Проблема. Сертификаты или внутренние сертификаты, выдавлимые в Центральный магазин управления, сервер-посредник и edge Server, находятся вблизи истечения срока действия или находятся под угрозой.**</span><span class="sxs-lookup"><span data-stu-id="33402-202">**Issue: Certificate authority certificates or internal certificates issued to Central Management Store, Mediation Server, and Edge Server are near expiration or are compromised.**</span></span>
    
    <span data-ttu-id="33402-203">**Разрешение:** Сертификаты сертификации Skype для бизнеса действительны в течение пяти лет.</span><span class="sxs-lookup"><span data-stu-id="33402-203">**Resolution:** Skype for Business certification authority certificates are valid for five years.</span></span> <span data-ttu-id="33402-204">Внутренние сертификаты, выдавлимые в Центральный магазин управления, сервер-посредник и edge Server, действительны в течение двух лет.</span><span class="sxs-lookup"><span data-stu-id="33402-204">Internal certificates issued to the Central Management Store, Mediation Server, and Edge Server are valid for two years.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="33402-205">В версии Cloud Connector 2.0 и более поздней версии Renew-CcServerCertificate изменен на Update-CcServerCertificate, а Renew-CcCACertificate — на Update-CcCACertificate.</span><span class="sxs-lookup"><span data-stu-id="33402-205">In Cloud Connector version 2.0 and later, the Renew-CcServerCertificate cmdlet has changed to Update-CcServerCertificate and the Renew-CcCACertificate cmdlet has changed to Update-CcCACertificate.</span></span> 
  
    <span data-ttu-id="33402-206">Если внутренние сертификаты, выдав центру управления, серверу-посреднику и edge Server, находятся вблизи истечения срока действия или компрометации, запустите Renew-CcServerCertificate или Update-CcServerCertificate для обновления сертификатов.</span><span class="sxs-lookup"><span data-stu-id="33402-206">If internal certificates issued to the Central Management Store, Mediation Server, and Edge Server are near expiration or compromised, run the Renew-CcServerCertificate or Update-CcServerCertificate cmdlet to renew your certificates.</span></span>
    
    <span data-ttu-id="33402-207">Если срок действия сертификатов сертификации истек, запустите Renew-CcCACertificate или Update-CcCACertificate, чтобы обновить сертификаты.</span><span class="sxs-lookup"><span data-stu-id="33402-207">If certification authority certificates are near expiration, run the Renew-CcCACertificate or Update-CcCACertificate cmdlet to renew your certificates.</span></span>
    
    <span data-ttu-id="33402-208">**Если сертификаты органа сертификации скомпрометированы** и на сайте имеется только один прибор, выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="33402-208">**If certification authority certificates are compromised and there is only one appliance in the site,** perform the following steps:</span></span>
    
1. <span data-ttu-id="33402-209">Запустите Enter-CcUpdate для слива служб и вставьте устройство в режим обслуживания.</span><span class="sxs-lookup"><span data-stu-id="33402-209">Run the Enter-CcUpdate cmdlet to drain services and put the appliance in maintenance mode.</span></span>
   
   ```powershell
   Enter-CcUpdate
   ```
   
2. <span data-ttu-id="33402-210">Запустите следующие cmdlets для сброса и создания новых сертификатов сертификации и всех внутренних сертификатов сервера:</span><span class="sxs-lookup"><span data-stu-id="33402-210">Run the following cmdlets to reset and create new certification authority certificates and all internal server certificates:</span></span>
    
    <span data-ttu-id="33402-211">Для выпусков облачного соединитетеля до 2.0:</span><span class="sxs-lookup"><span data-stu-id="33402-211">For Cloud Connector releases before 2.0:</span></span>
    
    ```powershell
    Reset-CcCACertificate 
    Renew-CcServerCertificate 
    Remove-CcLegacyServerCertificate 
    ```

    <span data-ttu-id="33402-212">Или для облачного соединитетеля выпуска 2.0 и более поздней версии:</span><span class="sxs-lookup"><span data-stu-id="33402-212">Or for Cloud Connector release 2.0 and later:</span></span>
    
    ```powershell
    Reset-CcCACertificate 
    Update-CcServerCertificate 
    Remove-CcLegacyServerCertificate 
    ```
    
3. <span data-ttu-id="33402-213">Если TLS используется между шлюзом и сервером-посредником, запустите Export-CcRootCertificate из устройства, а затем установите экспортируемую справку на шлюзы PSTN.</span><span class="sxs-lookup"><span data-stu-id="33402-213">If TLS is used between the gateway and the Mediation Server, run the Export-CcRootCertificate cmdlet from the appliance, and then install the exported certificate to your PSTN gateways.</span></span> <span data-ttu-id="33402-214">Кроме того, может потребоваться повторное выпуск сертификата на шлюзе.</span><span class="sxs-lookup"><span data-stu-id="33402-214">You may also be required to re-issue the certificate on your gateway.</span></span>

   ```powershell
   Export-CcRootCertificate
   ```

4. <span data-ttu-id="33402-215">Запустите Exit-CcUpdate, чтобы запустить службы и выйти из режима обслуживания.</span><span class="sxs-lookup"><span data-stu-id="33402-215">Run the Exit-CcUpdate cmdlet to start services and exit maintenance mode.</span></span>

   ```powershell
   Exit-CcUpdate
   ```


    <span data-ttu-id="33402-216">**Если сертификаты сертификационного** органа скомпрометированы и на сайте имеется несколько устройств, выполните следующие последовательно действия на каждом устройстве на сайте.</span><span class="sxs-lookup"><span data-stu-id="33402-216">**If certification authority certificates are compromised and there are multiple appliances in the site,** perform the following sequential steps on each appliance in the site.</span></span>
    
    <span data-ttu-id="33402-217">Корпорация Майкрософт рекомендует выполнять эти действия в периоды не пикового использования.</span><span class="sxs-lookup"><span data-stu-id="33402-217">Microsoft recommends that you perform these steps during non-peak usage times.</span></span>
    
1. <span data-ttu-id="33402-218">На первом устройстве запустите Remove-CcCertificationAuthorityFile для очистки файлов резервного копирования ca \<SiteRoot\> в каталоге.</span><span class="sxs-lookup"><span data-stu-id="33402-218">On the first appliance, run the Remove-CcCertificationAuthorityFile cmdlet to clean up the CA backup files in the \<SiteRoot\> directory.</span></span>

     ```powershell
     Remove-CcCertificationAuthorityFile
     ```
    
2. <span data-ttu-id="33402-219">Запустите Enter-CcUpdate, чтобы осушить службы и поместить каждое устройство в режим обслуживания.</span><span class="sxs-lookup"><span data-stu-id="33402-219">Run the Enter-CcUpdate cmdlet to drain services and put each appliance in maintenance mode.</span></span>

     ```powershell
     Enter-CcUpdate
     ```
    
3. <span data-ttu-id="33402-220">На первом устройстве запустите следующие cmdlets для сброса и создания новых сертификатов сертификации и всех внутренних сертификатов сервера:</span><span class="sxs-lookup"><span data-stu-id="33402-220">On the first appliance, run the following cmdlets to reset and create new certification authority certificates and all internal server certificates:</span></span>
    
     <span data-ttu-id="33402-221">Для выпусков облачного соединитетеля до 2.0:</span><span class="sxs-lookup"><span data-stu-id="33402-221">For Cloud Connector releases before 2.0:</span></span>
    
     ```powershell
     Reset-CcCACertificate
     Renew-CcServerCertificate
     Remove-CcLegacyServerCertificate 
     ```

     <span data-ttu-id="33402-222">Или для облачного соединитетеля выпуска 2.0 и более поздней версии:</span><span class="sxs-lookup"><span data-stu-id="33402-222">Or for Cloud Connector release 2.0 and later:</span></span>
    
     ```powershell
     Reset-CcCACertificate
     Update-CcServerCertificate
     Remove-CcLegacyServerCertificate 
     ```

4. <span data-ttu-id="33402-223">На первом устройстве запустите следующий комдлет, чтобы архивовать файлы ЦС в \<SiteRoot\> папку.</span><span class="sxs-lookup"><span data-stu-id="33402-223">On the first appliance, run the following cmdlet to back up the CA files to the \<SiteRoot\> folder.</span></span>
    
     ```powershell
     Backup-CcCertificationAuthority
     ```
   
5. <span data-ttu-id="33402-224">На всех остальных устройствах на том же сайте запустите следующие команды для использования файлов резервного копирования CA, чтобы все устройства использовали один и тот же корневой сертификат, а затем запросили новые сертификаты.</span><span class="sxs-lookup"><span data-stu-id="33402-224">On all other appliance's in the same site, run the following commands to consume the CA backup files, so that the appliances all use the same root certificate, and then request new certificates.</span></span> 
   
     ```powershell
     Reset-CcCACertificate
     Update-CcServerCertificate
     Remove-CcLegacyServerCertificate 
     ```
     
6. <span data-ttu-id="33402-225">Если TLS используется между шлюзом и сервером-посредником, запустите Export-CcRootCertificate из любого устройства на сайте, а затем установите экспортируемую справку на шлюзы PSTN.</span><span class="sxs-lookup"><span data-stu-id="33402-225">If TLS is used between the gateway and the Mediation Server, run the Export-CcRootCertificate cmdlet from any appliance in the site, and then install the exported certificate to your PSTN gateways.</span></span> <span data-ttu-id="33402-226">Кроме того, может потребоваться повторное выпуск сертификата на шлюзе.</span><span class="sxs-lookup"><span data-stu-id="33402-226">You may also be required to re-issue the certificate on your gateway.</span></span>
  
     ```powershell
     Export-CcRootCertificate
     ```
     
7. <span data-ttu-id="33402-227">Запустите Exit-CcUpdate, чтобы запустить службы и выйти из режима обслуживания.</span><span class="sxs-lookup"><span data-stu-id="33402-227">Run the Exit-CcUpdate cmdlet to start services and exit maintenance mode.</span></span> 

     ```powershell
     Exit-CcUpdate
     ```
    
    
- <span data-ttu-id="33402-228">**Проблема. В журнале службы управления облачными соединителями вы получаете следующее сообщение об ошибке: "C:\Program Files\Skype для бизнес-облачных соединителей Edition\ManagementService\CceManagementService.log": Ошибка CceService: 0: неожиданное исключение при сообщении о состоянии онлайн: System.Management.Automation.CmdletInvocationException: Logon не удалось для пользователя \<Global Tenant Admin\> . Создайте новый объект учетных данных, чтобы убедиться, что вы использовали правильное имя пользователя и пароль. ---\>**</span><span class="sxs-lookup"><span data-stu-id="33402-228">**Issue: You receive the following error message in the Cloud Connector Management Service Log, "C:\Program Files\Skype for Business Cloud Connector Edition\ManagementService\CceManagementService.log": CceService Error: 0 : Unexpected exception when reporting status to online: System.Management.Automation.CmdletInvocationException: Logon failed for the user \<Global Tenant Admin\>. Please create a new credential object, making sure that you have used the correct user name and password. ---\>**</span></span>
    
    <span data-ttu-id="33402-229">**Разрешение:** Учетные данные глобального клиента Microsoft 365 или Office 365 были изменены с момента регистрации устройства Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="33402-229">**Resolution:** The Microsoft 365 or Office 365 global tenant admin credentials have been changed since the Cloud Connector appliance was registered.</span></span> <span data-ttu-id="33402-230">Чтобы обновить локально хранимые учетные данные в устройстве Cloud Connector, запустите следующее из администратора PowerShell на устройстве хост:</span><span class="sxs-lookup"><span data-stu-id="33402-230">To update the locally stored credentials on the Cloud Connector appliance, run the following from Administrator PowerShell on the host appliance:</span></span>
    
  ```powershell
  Set-CcCredential -AccountType TenantAdmin
  ```

- <span data-ttu-id="33402-231">**Проблема. После изменения пароля учетной записи хост-сервера, используемой для развертывания, вы получаете следующее сообщение об ошибке: "ConvertTo-SecureString: key not valid for use in specified state." in %ProgramFiles%\Skype for Business Cloud Connector Edition\ManagementService\CceManagementService.log или при запуске Get-CcCredential cmdlet.**</span><span class="sxs-lookup"><span data-stu-id="33402-231">**Issue: After you change the password for the host server account you used for the deployment, you receive the following error message: "ConvertTo-SecureString : Key not valid for use in specified state." in %ProgramFiles%\Skype for Business Cloud Connector Edition\ManagementService\CceManagementService.log or while running the Get-CcCredential cmdlet.**</span></span>
    
    <span data-ttu-id="33402-232">**Разрешение:** Все учетные данные cloud Connector хранятся в следующем файле: "%SystemDrive%\Programdata\Cloudconnector\credentials. \<CurrentUser\> . xml".</span><span class="sxs-lookup"><span data-stu-id="33402-232">**Resolution:** All Cloud Connector credentials are stored in the following file: "%SystemDrive%\Programdata\Cloudconnector\credentials.\<CurrentUser\>.xml".</span></span> <span data-ttu-id="33402-233">Когда пароль на сервере хост-сервера изменится, вам потребуется обновить учетные данные, хранимые на локальном уровне.</span><span class="sxs-lookup"><span data-stu-id="33402-233">When the password on the host server changes, you will need to update the locally stored credentials.</span></span>
    
    <span data-ttu-id="33402-234">**Если вы работаете в версии Cloud Connector 1.4.2,** регенерируете все пароли облачного соединитетеля, следуя следующим шагам:</span><span class="sxs-lookup"><span data-stu-id="33402-234">**If you are running Cloud Connector version 1.4.2,** regenerate all Cloud Connector passwords by following these steps:</span></span>
    
  1. <span data-ttu-id="33402-235">Перезапустите хост-сервер.</span><span class="sxs-lookup"><span data-stu-id="33402-235">Restart the host server.</span></span>
    
  2. <span data-ttu-id="33402-236">Удалите следующий файл: "%SystemDrive%\Programdata\Cloudconnector\credentials. \<CurrentUser\> . xml".</span><span class="sxs-lookup"><span data-stu-id="33402-236">Delete the following file: "%SystemDrive%\Programdata\Cloudconnector\credentials.\<CurrentUser\>.xml".</span></span>
    
  3. <span data-ttu-id="33402-237">Запустите консоль PowerShell в качестве администратора, а затем запустите "Register-CcAppliance-Local", чтобы повторно ввести пароли, следующие описанию.</span><span class="sxs-lookup"><span data-stu-id="33402-237">Launch a PowerShell console as administrator, and then run "Register-CcAppliance -Local" to re-enter the passwords following the description.</span></span> <span data-ttu-id="33402-238">Введите те же пароли, которые были введены ранее для развертывания облачного соединиттеля.</span><span class="sxs-lookup"><span data-stu-id="33402-238">Enter the same passwords you entered before for the Cloud Connector deployment.</span></span>
    
     <span data-ttu-id="33402-239">**Если вы работаете в версии Cloud Connector версии 2.0** или более поздней версии, регенерируете все пароли облачного соединиттеля, следуя следующим шагам:</span><span class="sxs-lookup"><span data-stu-id="33402-239">**If you are running Cloud Connector version 2.0 or later,** regenerate all Cloud Connector passwords by following these steps:</span></span>
    
  4. <span data-ttu-id="33402-240">Перезапустите хост-сервер.</span><span class="sxs-lookup"><span data-stu-id="33402-240">Restart the host server.</span></span>
    
  5. <span data-ttu-id="33402-241">Удалите следующий файл: "%SystemDrive%\Programdata\Cloudconnector\credentials. \<CurrentUser\> . xml" .</span><span class="sxs-lookup"><span data-stu-id="33402-241">Delete the following file: "%SystemDrive%\Programdata\Cloudconnector\credentials.\<CurrentUser\>.xml" .</span></span>
    
  6. <span data-ttu-id="33402-242">Запустите консоль PowerShell в качестве администратора, а затем запустите "Register-CcAppliance-Local", чтобы повторно ввести пароли, следующие описанию.</span><span class="sxs-lookup"><span data-stu-id="33402-242">Launch a PowerShell console as administrator, and then run "Register-CcAppliance -Local" to re-enter the passwords following the description.</span></span> 
    
     <span data-ttu-id="33402-243">Если кэшированная папка паролей была сгенерирована с помощью версии Cloud Connector 1.4.2, при запросе используйте пароль VMAdmin для пароля CceService.</span><span class="sxs-lookup"><span data-stu-id="33402-243">If the cached password file was generated with Cloud Connector version 1.4.2, use the VMAdmin password for the CceService password when prompted.</span></span> <span data-ttu-id="33402-244">Введите тот же пароль, который был введен ранее для развертывания облачного соединиттеля для всех остальных учетных записей.</span><span class="sxs-lookup"><span data-stu-id="33402-244">Enter the same password you entered before for the Cloud Connector deployment for all other accounts.</span></span>
    
     <span data-ttu-id="33402-245">Если кэшированная папка паролей была сгенерирована с помощью облачной соединители версии 1.4.2, а пароли DomainAdmin и VMAdmin отличаются, необходимо выполнить следующие действия:</span><span class="sxs-lookup"><span data-stu-id="33402-245">If the cached password file was generated with Cloud Connector version 1.4.2 and the DomainAdmin and VMAdmin passwords are different, you must perform the following steps:</span></span>
    
  7. <span data-ttu-id="33402-246">Выполните Set-CcCredential-AccountType DomainAdmin следующим образом:</span><span class="sxs-lookup"><span data-stu-id="33402-246">Run Set-CcCredential -AccountType DomainAdmin as follows:</span></span>
    
  8. <span data-ttu-id="33402-247">При запросе на старую учетную запись введите учетные данные, используемые для пароля CceService.</span><span class="sxs-lookup"><span data-stu-id="33402-247">When prompted for the old account credential, enter the credential you used for the CceService password.</span></span>
    
  9. <span data-ttu-id="33402-248">При запросе новой учетной записи введите пароль для пароля DomainAdmin, который вы использовали ранее.</span><span class="sxs-lookup"><span data-stu-id="33402-248">When prompted for the new account credential, enter the password for the DomainAdmin password you used before.</span></span>
    
     <span data-ttu-id="33402-249">Если кэшированная папка паролей была сгенерирована с помощью версии 2.0 или более поздней версии Cloud Connector, по умолчанию VmAdmin и DomainAdmin используют тот же пароль, что и CceService.</span><span class="sxs-lookup"><span data-stu-id="33402-249">If the cached password file was generated with Cloud Connector version 2.0 or later, by default, VmAdmin and DomainAdmin use the same password as CceService.</span></span> <span data-ttu-id="33402-250">Если вы изменили пароли DomainAdmin и VMAdmin, необходимо выполнить следующие действия:</span><span class="sxs-lookup"><span data-stu-id="33402-250">If you changed the DomainAdmin and VMAdmin passwords, you must perform the following steps:</span></span>
    
  10. <span data-ttu-id="33402-251">Выполните Set-CcCredential-AccountType DomainAdmin следующим образом:</span><span class="sxs-lookup"><span data-stu-id="33402-251">Run Set-CcCredential -AccountType DomainAdmin as follows:</span></span>
    
       1. <span data-ttu-id="33402-252">При запросе на старую учетную запись введите учетные данные, используемые для пароля CceService</span><span class="sxs-lookup"><span data-stu-id="33402-252">When prompted for the old account credential, enter the credential you used for the CceService password</span></span>
    
       2. <span data-ttu-id="33402-253">При запросе новой учетной записи введите пароль для пароля DomainAdmin, который вы использовали ранее.</span><span class="sxs-lookup"><span data-stu-id="33402-253">When prompted for the new account credential, enter the password for the DomainAdmin password you used before.</span></span>
    
  11. <span data-ttu-id="33402-254">Выполните Set-CcCredential-AccountType VmAdmin следующим образом:</span><span class="sxs-lookup"><span data-stu-id="33402-254">Run Set-CcCredential -AccountType VmAdmin as follows:</span></span>
    
       1. <span data-ttu-id="33402-255">При запросе на старую учетную запись введите учетные данные, используемые для пароля CceService</span><span class="sxs-lookup"><span data-stu-id="33402-255">When prompted for the old account credential, enter the credential you used for the CceService password</span></span>
    
       2. <span data-ttu-id="33402-256">При запросе новой учетной записи введите пароль для пароля VmAdmin, который вы использовали ранее.</span><span class="sxs-lookup"><span data-stu-id="33402-256">When prompted for the new account credential, enter the password for the VmAdmin password you used before.</span></span> 
    
- <span data-ttu-id="33402-257">**Проблема. С помощью облачного соединителя версии 2.1 и более поздней версии при запуске Register-CcAppliance или других комлетов на устройстве вы получаете сообщение об ошибке, например: "Для Each-Object: свойство "Common" не может быть найдено на этом объекте. Убедитесь, что свойство существует. В C:\Program Files\WindowsPowerShell\Modules\CloudConnector\Internal\MtHostCommon.ps1:681 char:14"**</span><span class="sxs-lookup"><span data-stu-id="33402-257">**Issue: With Cloud Connector version 2.1 and later, when running Register-CcAppliance or other cmdlets on the appliance, you receive an error message such as: "For Each-Object : The property 'Common' cannot be found on this object. Verify that the property exists. At C:\Program Files\WindowsPowerShell\Modules\CloudConnector\Internal\MtHostCommon.ps1:681 char:14"**</span></span>
    
    <span data-ttu-id="33402-258">**Разрешение:** Cloud Connector 2.1 и более поздний платформа .NET Framework 4.6.1 или более поздней.</span><span class="sxs-lookup"><span data-stu-id="33402-258">**Resolution:** Cloud Connector 2.1 and later requires .NET Framework 4.6.1 or later.</span></span> <span data-ttu-id="33402-259">Обновите платформа .NET Framework на устройстве до версии 4.6.1 или более поздней версии и запустите cmdlet(s) снова.</span><span class="sxs-lookup"><span data-stu-id="33402-259">Please update .NET Framework on the appliance to version 4.6.1 or later and run the cmdlet(s) again.</span></span>

- <span data-ttu-id="33402-260">**Проблема. С cloud Connector Edition 2.1 при запуске Install-CcAppliance вы получаете сообщение об ошибке, например: "Не удалось установить новый экземпляр с ошибкой: невозможно задать "состояние", так как только строки можно использовать в качестве значений для установки свойств XmlNode"**</span><span class="sxs-lookup"><span data-stu-id="33402-260">**Issue: With Cloud Connector Edition 2.1, when running Install-CcAppliance, you receive an error message such as: "Failed to install new instance with error: Cannot set "State" because only strings can be used as values to set XmlNode properties"**</span></span>

   <span data-ttu-id="33402-261">**Разрешение:** В Cloudconnector.ini разделе [Common] добавьте конфигурию "State" как ниже: CountryCode=US State=WA City=Redmond</span><span class="sxs-lookup"><span data-stu-id="33402-261">**Resolution:** In Cloudconnector.ini, under the [Common] section, please add the “State” config as below:  CountryCode=US  State=WA  City=Redmond</span></span>

   <span data-ttu-id="33402-262">Для строки "Состояние" значение не обязательно, однако строка "Состояние" не может быть удалена из Cloudconnector.ini файла.</span><span class="sxs-lookup"><span data-stu-id="33402-262">It is not mandatory for the "State" line to have value, however the "State" line cannot be removed from the Cloudconnector.ini file.</span></span>

- <span data-ttu-id="33402-263">**Проблема. Вы получаете следующее сообщение об ошибке "Dismount-WindowsImage: Dismount-WindowsImage не удалось. Код ошибки = 0xc1550115" при установке или обновлении Cloud Connector Edition.**</span><span class="sxs-lookup"><span data-stu-id="33402-263">**Issue: You receive the following error message "Dismount-WindowsImage : Dismount-WindowsImage failed. Error code = 0xc1550115" when installing or upgrading Cloud Connector Edition.**</span></span>
    
    <span data-ttu-id="33402-264">**Разрешение:** Запустите консоль PowerShell в качестве администратора, запустите "DISM-Cleanup-Wim".</span><span class="sxs-lookup"><span data-stu-id="33402-264">**Resolution:** Launch a PowerShell console as administrator, run "DISM -Cleanup-Wim'".</span></span> <span data-ttu-id="33402-265">Это позволит очистить все проблемные изображения.</span><span class="sxs-lookup"><span data-stu-id="33402-265">This will clean up all troubled images.</span></span> <span data-ttu-id="33402-266">Запустите Install-CcAppliance или дождись автоматического обновления битов.</span><span class="sxs-lookup"><span data-stu-id="33402-266">Run Install-CcAppliance again or wait for the bits to automatically upgrade.</span></span>
    
- <span data-ttu-id="33402-267">**Проблема. Развертывание первого устройства облачного соединитела в среде HA не удается**</span><span class="sxs-lookup"><span data-stu-id="33402-267">**Issue: Deployment of the first Cloud Connector appliance in an HA environment fails**</span></span>
    
    <span data-ttu-id="33402-268">**Разрешение:** Действия, которые вы принимаете, зависят от причины сбой развертывания:</span><span class="sxs-lookup"><span data-stu-id="33402-268">**Resolution:** The steps you take depend on the reason the deployment failed:</span></span>
    
  - <span data-ttu-id="33402-269">Если первый аппарат облачного соединителя сбой и вы не можете определить причину сбоя, необходимо установить устройство снова, пока развертывание не будет успешным, а затем установить другие устройства.</span><span class="sxs-lookup"><span data-stu-id="33402-269">If the first Cloud Connector appliance fails and you cannot determine the reason for the failure, you must install the appliance again until the deployment is successful, and then install the other appliances.</span></span>
    
  - <span data-ttu-id="33402-270">Если первый аппарат облачного соединителя не справился с небольшой проблемой, например с внешним сертификатом, можно устранить проблему без повторной установки устройства.</span><span class="sxs-lookup"><span data-stu-id="33402-270">If the first Cloud Connector appliance fails with a minor issue, such as an external certificate issue, you might be able to fix the problem without re-installing the appliance.</span></span> <span data-ttu-id="33402-271">Затем можно использовать удаленную powerShell клиента, чтобы отметить развертывание как успешное следующим образом.</span><span class="sxs-lookup"><span data-stu-id="33402-271">You can then use tenant remote PowerShell to mark the deployment as successful as follows.</span></span> <span data-ttu-id="33402-272">(Вы также можете использовать следующие действия, если первое развертывание было успешным, но по некоторым причинам Cloud Connector не сообщает об успешном развертывании.)</span><span class="sxs-lookup"><span data-stu-id="33402-272">(You can also use the following steps if the first deployment was successful, but, for some reason, Cloud Connector fails to report the deployment as a success.)</span></span>
    
  - <span data-ttu-id="33402-273">Чтобы получить идентификатор (GUID) первого устройства облачного соединителя, запустите Get-CsHybridPSTNAppliance.</span><span class="sxs-lookup"><span data-stu-id="33402-273">To get the Identity (GUID) of the first Cloud Connector appliance, run the Get-CsHybridPSTNAppliance cmdlet.</span></span>
    
  - <span data-ttu-id="33402-274">Чтобы пометить устройство как успешно развернутый, выполните Set-CsCceApplianceDeploymentStatus следующим образом:</span><span class="sxs-lookup"><span data-stu-id="33402-274">To mark the appliance as successfully deployed, run the Set-CsCceApplianceDeploymentStatus as follows:</span></span>
    
  ```powershell
  Set-CsCceApplianceDeploymentStatus -Identity <Appliance Identity GUID> -Action Deploy -Status Finished
  ```

- <span data-ttu-id="33402-275">**Проблема. Необходимо вручную проверять и устанавливать обновления Windows на хост-сервере или виртуальных машинах.**</span><span class="sxs-lookup"><span data-stu-id="33402-275">**Issue: You need to check for and install Windows updates manually on the host server or virtual machines.**</span></span>
    
   <span data-ttu-id="33402-276">**Разрешение:** Рекомендуется использовать автоматические обновления ОС, предоставляемые Skype для бизнеса Cloud Connector Edition.</span><span class="sxs-lookup"><span data-stu-id="33402-276">**Resolution:** We recommend that you take advantage of automated OS updates provided by Skype for Business Cloud Connector Edition.</span></span> <span data-ttu-id="33402-277">После регистрации устройства для управления в Интернете и включения автоматического обновления ОС сервер хост и виртуальные машины будут проверять и устанавливать обновления Windows автоматически в соответствии с настройками окне времени обновления ОС.</span><span class="sxs-lookup"><span data-stu-id="33402-277">After an appliance is registered for online management and auto OS update is enabled, the host server and virtual machines will check and install Windows Updates automatically according to the OS update time window settings.</span></span>
    
   <span data-ttu-id="33402-278">Если необходимо вручную проверять и устанавливать обновления Windows, выполните действия в этом разделе, применимые к типу развертывания.</span><span class="sxs-lookup"><span data-stu-id="33402-278">If you need to check for and install Windows Updates manually, follow the steps in this section that apply to your type of deployment.</span></span> <span data-ttu-id="33402-279">Чтобы свести к минимуму время простоя, необходимое для обновления, необходимо одновременно обновить сервер хост-сервера и виртуальные машины, работающие на нем.</span><span class="sxs-lookup"><span data-stu-id="33402-279">You should plan on updating both the host server and the virtual machines running on it at the same time to minimize the amount of down time necessary for the updates.</span></span>
    
   <span data-ttu-id="33402-280">Если вы хотите, вы можете использовать cлужбы Windows Server Update Services (WSUS) для предоставления обновлений для серверов облачного соединителю.</span><span class="sxs-lookup"><span data-stu-id="33402-280">If you prefer, you can use a Windows Server Update Services (WSUS) server to provide updates to Cloud Connector servers.</span></span> <span data-ttu-id="33402-281">Просто не забудьте настроить обновление Windows, чтобы **не** устанавливаться автоматически.</span><span class="sxs-lookup"><span data-stu-id="33402-281">Just be sure to configure the Windows Update to **not** install automatically.</span></span>
    
   <span data-ttu-id="33402-282">Сведения о том, как вручную обновить развертывание облачного соединителю, см. в следующем разделе.</span><span class="sxs-lookup"><span data-stu-id="33402-282">For information about how to manually update your Cloud Connector deployment, see the following section.</span></span>
    
- <span data-ttu-id="33402-283">**Проблема. При обновлении облачного соединителя до новой сборки не обновляются кодлеты Cloud Connector.**</span><span class="sxs-lookup"><span data-stu-id="33402-283">**Issue: When Cloud Connector updates to a new build, Cloud Connector cmdlets are not updated.**</span></span> <span data-ttu-id="33402-284">Иногда это происходит, если окно PowerShell остается открытым при автоматическом обновлении.</span><span class="sxs-lookup"><span data-stu-id="33402-284">This sometimes happens if a PowerShell window is left open when automatic update occurs.</span></span>
    
  <span data-ttu-id="33402-285">**Разрешение:** Чтобы загрузить обновленные cmdlets, вы можете сделать любой из следующих действий:</span><span class="sxs-lookup"><span data-stu-id="33402-285">**Resolution:** To load the updated cmdlets, you can do either of the following steps:</span></span>
    
   - <span data-ttu-id="33402-286">Закрой PowerShell на устройстве облачного соединитетеля и снова открой PowerShell.</span><span class="sxs-lookup"><span data-stu-id="33402-286">Close PowerShell on the Cloud Connector appliance, and then reopen PowerShell.</span></span>
    
     - <span data-ttu-id="33402-287">Или можно запустить Import-Module CloudConnector-Force.</span><span class="sxs-lookup"><span data-stu-id="33402-287">Or, you can run Import-Module CloudConnector -Force.</span></span> 
 
-   <span data-ttu-id="33402-288">**Проблема. "Термин "Stop-CsWindowsService" не распознается как имя cmdlet, function, script file или operable program." при попытке запуска Enter-CcUpdate cmdlet.**</span><span class="sxs-lookup"><span data-stu-id="33402-288">**Issue: "The term 'Stop-CsWindowsService' is not recognized as the name of a cmdlet, function, script file, or operable program." error when attempting to run Enter-CcUpdate cmdlet.**</span></span>

    <span data-ttu-id="33402-289">**Разрешение:** Удаление файла $HOME\AppData\Local\Microsoft\Windows\PowerShell\ModuleAnalysisCache.</span><span class="sxs-lookup"><span data-stu-id="33402-289">**Resolution:** Delete the $HOME\AppData\Local\Microsoft\Windows\PowerShell\ModuleAnalysisCache file.</span></span>
<span data-ttu-id="33402-290">PowerShell создает этот файл в качестве кэша командлетов из модулей, которые он находит, чтобы ему не нужно было каждый раз анализировать все модули, так как это сделает процесс действительно медленным.</span><span class="sxs-lookup"><span data-stu-id="33402-290">PowerShell creates this file as a cache of cmdlets from modules that it finds so that it doesn’t have to re-analyze all the modules each time as that would make things really slow.</span></span> <span data-ttu-id="33402-291">Скорее всего, при чтении из этого кэша в PowerShell была какая-то коррупция файлов, которая предоставляла ложные результаты.</span><span class="sxs-lookup"><span data-stu-id="33402-291">Most likely, there was some file corruption that provided misleading results to PowerShell when it was reading back from that cache.</span></span>

-   <span data-ttu-id="33402-292">**Проблема: "Import-Module CloudConnector" создает ошибку "Импорт-модуль: указанный модуль "CloudConnector" не был загружен, так как в каталоге модулей не обнаружен допустимый файл модуля"**</span><span class="sxs-lookup"><span data-stu-id="33402-292">**Issue: “Import-Module CloudConnector” generates error “Import-Module: The specified module “CloudConnector” was not loaded because no valid module file was found in any module directory”**</span></span>

    <span data-ttu-id="33402-293">**Решение:**</span><span class="sxs-lookup"><span data-stu-id="33402-293">**Resolution:**</span></span>
    - <span data-ttu-id="33402-294">Проверка того, что модуль CloudConnector действительно существует в c:\Program Files\WindowsPowerShell\Modules</span><span class="sxs-lookup"><span data-stu-id="33402-294">Validate that indeed the CloudConnector module exists under c:\Program Files\WindowsPowerShell\Modules</span></span>
    
    - <span data-ttu-id="33402-295">После проверки того, что модуль CloudConnector существует в этом расположении, переменная среды PSModulePath, храня путь к расположениям модулей, может быть изменена:</span><span class="sxs-lookup"><span data-stu-id="33402-295">After validating that CloudConnector module exists under this location, the PSModulePath environment variable storing the path to the locations of the modules can be changed:</span></span>
    
     <span data-ttu-id="33402-296">а)</span><span class="sxs-lookup"><span data-stu-id="33402-296">a.</span></span> <span data-ttu-id="33402-297">Временное изменение: запустите Powershell в качестве администратора и запустите следующую команду: $env:PSModulePath = $env:PSModulePath + "; C:\Program Files\WindowsPowerShell\Modules\"</span><span class="sxs-lookup"><span data-stu-id="33402-297">Temporary change: Start Powershell as an Administrator and run the following command: $env:PSModulePath = $env:PSModulePath + ";C:\Program Files\WindowsPowerShell\Modules\"</span></span>
        
     <span data-ttu-id="33402-298">б)</span><span class="sxs-lookup"><span data-stu-id="33402-298">b.</span></span> <span data-ttu-id="33402-299">Для настойчивых изменений запустите PowerShell в качестве администратора и запустите следующие команды по одному: $CurrentValue = [Окружающая среда]::GetEnvironmentVariable ("PSModulePath", "Machine") SetEnvironmentVariable ("PSModulePath", $CurrentValue + "; C:\Program Files\WindowsPowerShell\Modules", "Machine")</span><span class="sxs-lookup"><span data-stu-id="33402-299">For persistent change, Start PowerShell as an Administrator and run the following commands, one by one: $CurrentValue = [Environment]::GetEnvironmentVariable("PSModulePath", "Machine") SetEnvironmentVariable("PSModulePath", $CurrentValue + "; C:\Program Files\WindowsPowerShell\Modules", "Machine")</span></span>

    
## <a name="install-windows-updates-manually"></a><span data-ttu-id="33402-300">Установка обновлений Windows вручную</span><span class="sxs-lookup"><span data-stu-id="33402-300">Install Windows updates manually</span></span>

<span data-ttu-id="33402-301">Если вы не хотите использовать автоматические обновления в среде, выполните эти действия, чтобы вручную проверить и применить обновления Windows.</span><span class="sxs-lookup"><span data-stu-id="33402-301">If you do not want to use automatic updates in your environment, follow these steps to manually check for and apply Windows updates.</span></span> <span data-ttu-id="33402-302">Для проверки и установки обновлений Windows может потребоваться перезапуск сервера.</span><span class="sxs-lookup"><span data-stu-id="33402-302">Checking for and installing Windows updates may require a server restart.</span></span> <span data-ttu-id="33402-303">При перезапуске хост-сервера пользователи не смогут использовать cloud Connector для места или получения вызовов.</span><span class="sxs-lookup"><span data-stu-id="33402-303">When a host server is restarting, users will not be able to use Cloud Connector to place or receive calls.</span></span> <span data-ttu-id="33402-304">Вы можете вручную проверять и устанавливать обновления для управления при обновлении, а затем перезапустить машины по мере необходимости во время, когда вы решите избежать сбоев в работе служб.</span><span class="sxs-lookup"><span data-stu-id="33402-304">You can manually check for and install updates to control when the updates take place, and then restart the machines as needed during times you choose to avoid disruption of services.</span></span>
  
<span data-ttu-id="33402-305">Чтобы вручную проверить обновления, подключите к каждому серверу хост и откройте **панель управления.**</span><span class="sxs-lookup"><span data-stu-id="33402-305">To manually check for updates, connect to each host server and open the **Control Panel**.</span></span> <span data-ttu-id="33402-306">Выберите **обновление Windows System и \> Security,** а затем управляйте обновлениями и перезапусками сервера в соответствующей среде.</span><span class="sxs-lookup"><span data-stu-id="33402-306">Select **System and Security \>Windows Update**, and then manage the updates and server restarts as appropriate for your environment.</span></span>
  
- <span data-ttu-id="33402-307">Если на сайте есть только один прибор, подключите к каждой виртуальной машине и откройте **панель управления.**</span><span class="sxs-lookup"><span data-stu-id="33402-307">If there is only one appliance in the site, connect to each virtual machine and open the **Control Panel**.</span></span> <span data-ttu-id="33402-308">Выберите **обновление Windows System и \> Security,** а затем настроите обновления и перезапуски сервера по мере необходимости.</span><span class="sxs-lookup"><span data-stu-id="33402-308">Select **System and Security \>Windows Update**, and then configure the updates and server restarts as appropriate.</span></span>
    
- <span data-ttu-id="33402-309">Если на сайте имеется несколько устройств, экземпляр, обновляемый и перезапущенный, не может быть доступны пользователям во время обновления.</span><span class="sxs-lookup"><span data-stu-id="33402-309">If there are more than one appliance in the site, the instance being updated and restarted cannot be accessed by users during the updates.</span></span> <span data-ttu-id="33402-310">Пользователи будут подключаться к другим экземплярам развертывания до тех пор, пока все виртуальные машины и все службы Skype для бизнеса не начнут работать на виртуальных машинах после завершения обновлений.</span><span class="sxs-lookup"><span data-stu-id="33402-310">Users will connect to other instances in the deployment until all virtual machines and all Skype for Business services start on the virtual machines after the updates are completed.</span></span> <span data-ttu-id="33402-311">Чтобы избежать потенциальных сбоев в работе службы, вы можете удалить экземпляр из HA во время применения обновлений, а затем восстановить его по завершению.</span><span class="sxs-lookup"><span data-stu-id="33402-311">To avoid any potential disruption to service, you can remove the instance from HA while you apply the updates, and then restore it when complete.</span></span> <span data-ttu-id="33402-312">Для этого:</span><span class="sxs-lookup"><span data-stu-id="33402-312">To do so:</span></span>
    
1. <span data-ttu-id="33402-313">На каждом сервере хост-сервера откройте консоль PowerShell в качестве администратора.</span><span class="sxs-lookup"><span data-stu-id="33402-313">On each host server, open a PowerShell console as administrator.</span></span>
    
2. <span data-ttu-id="33402-314">Удалите экземпляр из HA с помощью следующего cmdlet:</span><span class="sxs-lookup"><span data-stu-id="33402-314">Remove the instance from HA with the following cmdlet:</span></span>
    
   ```powershell
   Enter-CcUpdate
   ```

3. 
    
    <span data-ttu-id="33402-315">Выполните действия для одного экземпляра, чтобы вручную применить обновления и перезапустить виртуальную машину.</span><span class="sxs-lookup"><span data-stu-id="33402-315">Follow the steps for a single instance to manually apply the updates and restart the virtual machine.</span></span>
    
4. <span data-ttu-id="33402-316">Установите экземпляр обратно в HA с помощью следующего cmdlet:</span><span class="sxs-lookup"><span data-stu-id="33402-316">Set the instance back to HA with the following cmdlet:</span></span>
    
   ```powershell
   Exit-CcUpdate
   ```

<span data-ttu-id="33402-317">Для развертывания нескольких сайтов выполните действия по одному сайту для каждого сайта в развертывании, применяя обновления к одному сайту одновременно.</span><span class="sxs-lookup"><span data-stu-id="33402-317">For multi-site deployments, follow the steps for a single site for each site in the deployment, applying updates to one site at a time.</span></span>
  
## <a name="tips-when-installing-anti-virus-software-on-the-cloud-connector-host-machine"></a><span data-ttu-id="33402-318">Советы при установке антивирусного программного обеспечения на хост-машину облачного соединителя</span><span class="sxs-lookup"><span data-stu-id="33402-318">Tips when installing anti-virus software on the Cloud Connector host machine</span></span>

<span data-ttu-id="33402-319">Если необходимо установить антивирусное программное обеспечение на компьютере-хост-платформе Cloud Connector, необходимо добавить следующие исключения:</span><span class="sxs-lookup"><span data-stu-id="33402-319">If you need to install anti-virus software on the Cloud Connector host machine, you need to add the following exclusions:</span></span>
  
- <span data-ttu-id="33402-320">Локальный каталог приборов на каждой машине.</span><span class="sxs-lookup"><span data-stu-id="33402-320">Local Appliance Directory on each machine.</span></span>
    
- <span data-ttu-id="33402-321">Каталог удаленного сайта на каждой машине.</span><span class="sxs-lookup"><span data-stu-id="33402-321">Remote Site Directory on each machine.</span></span>
    
- <span data-ttu-id="33402-322">В локальном каталоге сайтов на компьютере размещена общая корневая папка сайта.</span><span class="sxs-lookup"><span data-stu-id="33402-322">Local Site Directory on the machine hosts the shared site root folder.</span></span>
    
- <span data-ttu-id="33402-323">%ProgramFiles%\Skype для бизнеса Cloud Connector Edition</span><span class="sxs-lookup"><span data-stu-id="33402-323">%ProgramFiles%\Skype for Business Cloud Connector Edition</span></span>
    
- <span data-ttu-id="33402-324">%ALLUSERSPROFILE%\CloudConnector</span><span class="sxs-lookup"><span data-stu-id="33402-324">%ALLUSERSPROFILE%\CloudConnector</span></span>
    
- <span data-ttu-id="33402-325">%ProgramFiles%\WindowsPowerShell\Modules\CloudConnector</span><span class="sxs-lookup"><span data-stu-id="33402-325">%ProgramFiles%\WindowsPowerShell\Modules\CloudConnector</span></span>
    
- <span data-ttu-id="33402-326">Процесс Microsoft.Rtc.CCE.ManagementService.exe.</span><span class="sxs-lookup"><span data-stu-id="33402-326">The process Microsoft.Rtc.CCE.ManagementService.exe.</span></span>