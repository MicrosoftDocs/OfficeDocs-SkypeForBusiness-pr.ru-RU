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
description: Устранение неполадок развертывания Cloud Connector Edition.
ms.openlocfilehash: 7a1caea67c5b5899c2dc0909ef771a57c7c50389
ms.sourcegitcommit: b424ab14683ab5080ebfd085adff7c0dbe1be84c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/03/2020
ms.locfileid: "47359335"
---
# <a name="troubleshoot-your-cloud-connector-deployment"></a><span data-ttu-id="374c3-103">Устранение неполадок с развертыванием Cloud Connector</span><span class="sxs-lookup"><span data-stu-id="374c3-103">Troubleshoot your Cloud Connector deployment</span></span>

> [!Important]
> <span data-ttu-id="374c3-104">Выпуск Cloud Connector Edition завершится 31 июля 2021 г. вместе со Skype для бизнеса Online.</span><span class="sxs-lookup"><span data-stu-id="374c3-104">Cloud Connector Edition will retire July 31, 2021 along with Skype for Business Online.</span></span> <span data-ttu-id="374c3-105">После обновления вашей организации до Teams узнайте, как подключить свою локальной телефонной сети к Teams с помощью [прямой маршрутизации.](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page)</span><span class="sxs-lookup"><span data-stu-id="374c3-105">Once your organization has upgraded to Teams, learn how to connect your on-premises telephony network to Teams using [Direct Routing](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page).</span></span>
 
<span data-ttu-id="374c3-106">Устранение неполадок развертывания Cloud Connector Edition.</span><span class="sxs-lookup"><span data-stu-id="374c3-106">Troubleshoot your Cloud Connector Edition deployment.</span></span>
  
<span data-ttu-id="374c3-107">В этом разделе описываются решения распространенных проблем с развертываниями Cloud Connector Edition.</span><span class="sxs-lookup"><span data-stu-id="374c3-107">This topic describes solutions to common issues with Cloud Connector Edition deployments.</span></span> <span data-ttu-id="374c3-108">Если у вас возникли проблемы со звонками в телефонную сеть общего звонков ( PSTN) и из нее, вы можете изучить их, следуя решениям, описанным в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="374c3-108">If you are experiencing issues with calls to and from the Public Switched Telephone Network (PSTN), you can investigate by following the solutions described in this topic.</span></span>
  
<span data-ttu-id="374c3-109">Cloud Connector предоставляет встроенные механизмы для автоматического решения некоторых проблем.</span><span class="sxs-lookup"><span data-stu-id="374c3-109">Cloud Connector provides built-in mechanisms for automatically resolving some issues.</span></span> <span data-ttu-id="374c3-110">Процесс автоматического обнаружения ищет потенциальные проблемы с устройствами Cloud Connector и, по возможности, устраняет эти проблемы без вмешательства администратора.</span><span class="sxs-lookup"><span data-stu-id="374c3-110">An automatic detection process looks for potential issues with the Cloud Connector appliances, and, if possible, takes corrective action to resolve those issues without the need for administrator intervention.</span></span> <span data-ttu-id="374c3-111">Процесс обнаружения работает следующим образом:</span><span class="sxs-lookup"><span data-stu-id="374c3-111">The detection process works as follows:</span></span>
  
- <span data-ttu-id="374c3-112">**Последовательность обнаружения:** Служба управления Cloud Connector запускает процесс каждые 60 секунд, чтобы определить, не работает ли устройство.</span><span class="sxs-lookup"><span data-stu-id="374c3-112">**Detection sequence:** The Cloud Connector Management service runs a process every 60 seconds for detecting whether an appliance is down.</span></span> <span data-ttu-id="374c3-113">В Cloud Connector версии 2.0 и более поздних версиях процесс обнаружения использует коммутатор Skype для бизнеса Corpnet для подключения PowerShell к компьютерам Cloud Connector; Для версий, предшествующих версии 2.0, процесс обнаружения использует коммутатор управления Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="374c3-113">In Cloud Connector version 2.0 and later, the detection process uses the Skype for Business Corpnet switch for making PowerShell connections to the Cloud Connector machines; for versions previous to 2.0, the detection process uses the Cloud Connector management switch.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="374c3-114">Для успешного автоматического восстановления должно быть сетевое подключение между хост-компьютером и виртуальными машинами через сетевой коммутатор хост-компьютера.</span><span class="sxs-lookup"><span data-stu-id="374c3-114">For automatic recovery to succeed, there must be network connectivity between the host and virtual machines over the host network switch.</span></span> <span data-ttu-id="374c3-115">Обязательно проверьте возможность подключения к сети, чтобы обеспечить успешное автоматическое обнаружение и восстановление.</span><span class="sxs-lookup"><span data-stu-id="374c3-115">Be sure to check network connectivity to ensure that automatic detection and recovery can succeed.</span></span> 
  
- <span data-ttu-id="374c3-116">**Мониторинг:** В Cloud Connector версии 2.0 и более поздних версиях отслеживаются следующие службы:</span><span class="sxs-lookup"><span data-stu-id="374c3-116">**Monitoring:** The following services are monitored in Cloud Connector version 2.0 and later:</span></span>
    
  - <span data-ttu-id="374c3-117">Виртуальные машины не подключены к корпоративным или интернет-виртуальным коммутаторам Cloud Connector</span><span class="sxs-lookup"><span data-stu-id="374c3-117">Virtual Machines are not connected to the Cloud Connector Corporate or Internet virtual switches</span></span>
    
  - <span data-ttu-id="374c3-118">Виртуальные машины находятся в сохраненной или остановленной состоянии</span><span class="sxs-lookup"><span data-stu-id="374c3-118">Virtual Machines are in a saved or stopped status</span></span>
    
  - <span data-ttu-id="374c3-119">Службы центрального сервера управления: РЕПЛИКА, MASTER</span><span class="sxs-lookup"><span data-stu-id="374c3-119">Central Management Server services: REPLICA, MASTER</span></span>
    
  - <span data-ttu-id="374c3-120">Службы сервера-посредника: REPLICA, RTCSRV и MEDSVC</span><span class="sxs-lookup"><span data-stu-id="374c3-120">Mediation Server services: REPLICA, RTCSRV and MEDSVC</span></span>
    
  - <span data-ttu-id="374c3-121">Службы edge Server: REPLICA, RTCSRV, RTCDATAPROXY, RTCMRAUTH, RTCMEDIARELAY</span><span class="sxs-lookup"><span data-stu-id="374c3-121">Edge Server services: REPLICA, RTCSRV, RTCDATAPROXY, RTCMRAUTH, RTCMEDIARELAY</span></span>
    
  - <span data-ttu-id="374c3-122">Правила брандмауэра входящие входящие отключены для CS RTCSRV на сервере-посреднике, CS RTCMEDSRV на сервере-посреднике</span><span class="sxs-lookup"><span data-stu-id="374c3-122">Inbound firewall rules are disabled for CS RTCSRV on Edge server, CS RTCMEDSRV on Mediation server</span></span>
    
    <span data-ttu-id="374c3-123">В Cloud Connector версии 1.4.2 отслеживаются только следующие службы:</span><span class="sxs-lookup"><span data-stu-id="374c3-123">In Cloud Connector version 1.4.2, only the following services are monitored:</span></span>
    
  - <span data-ttu-id="374c3-124">Службы серверов-посредников: RTCSRV и MEDSVC</span><span class="sxs-lookup"><span data-stu-id="374c3-124">Mediation Server services: RTCSRV and MEDSVC</span></span>
    
  - <span data-ttu-id="374c3-125">Служба edge Server: RTCSRV</span><span class="sxs-lookup"><span data-stu-id="374c3-125">Edge Server service: RTCSRV</span></span>
    
- <span data-ttu-id="374c3-126">**Процесс восстановления:** Если какие-либо отслеживаемая служба не работать, устройство помечается, а службы останавливаются и помечаются вручную до тех пор, пока не будут устранены все проблемы.</span><span class="sxs-lookup"><span data-stu-id="374c3-126">**Recovery process:** If any monitored services are down, an appliance is marked down, and services are stopped and marked manual until all issues can be resolved.</span></span> <span data-ttu-id="374c3-127">Это предотвратит маршрутику вызовов на устройство, которое может привести к сбоям вызовов.</span><span class="sxs-lookup"><span data-stu-id="374c3-127">This will prevent calls from routing to an appliance that may cause call failures.</span></span>
    
    <span data-ttu-id="374c3-128">Служба управления Cloud Connector повторно выполнит автоматическое восстановление следующим образом.</span><span class="sxs-lookup"><span data-stu-id="374c3-128">The Cloud Connector Management service will retry automatic recovery as follows</span></span>
    
  - <span data-ttu-id="374c3-129">Интервал первой повторной попытку составляет каждые десять секунд с максимальным интервалом в один час.</span><span class="sxs-lookup"><span data-stu-id="374c3-129">The initial retry interval is every ten seconds with a maximum interval time of one hour.</span></span>
    
  - <span data-ttu-id="374c3-130">Для первых трех попыток восстановления интервал составляет 10 секунд.</span><span class="sxs-lookup"><span data-stu-id="374c3-130">For the first three recovery attempts, the interval time is 10 seconds.</span></span> <span data-ttu-id="374c3-131">Начиная с четвертой повторной попытку интервал увеличивается в два раза по сравнению с предыдущим интервалом.</span><span class="sxs-lookup"><span data-stu-id="374c3-131">Starting from the fourth retry, the interval time increases by two times the previous interval time.</span></span> <span data-ttu-id="374c3-132">Например, четвертая повторить попытку произойдет через 20 секунд, пятая за 40 секунд и так далее.</span><span class="sxs-lookup"><span data-stu-id="374c3-132">For example, the fourth retry will occur in 20 seconds, the fifth in 40 seconds, and so on.</span></span> 
    
  - <span data-ttu-id="374c3-133">Когда достигается максимальный интервал в один час, повторы будут продолжаться один раз в час.</span><span class="sxs-lookup"><span data-stu-id="374c3-133">When the maximum interval time of one hour is reached, retries will continue once per hour.</span></span>
    
  - <span data-ttu-id="374c3-134">При успешном восстановлении интервал и количество повторной попытку устанавливаются на исходные значения.</span><span class="sxs-lookup"><span data-stu-id="374c3-134">When recovery is successful, the interval and retry counts are set to their initial values.</span></span>
    
  - <span data-ttu-id="374c3-135">При перезапуске службы управления интервал и количество повторов сбрасываются до исходных значений.</span><span class="sxs-lookup"><span data-stu-id="374c3-135">If the Management service is restarted, the interval and retry counts are reset to their initial values.</span></span>
    
## <a name="troubleshooting"></a><span data-ttu-id="374c3-136">Устранение неполадок</span><span class="sxs-lookup"><span data-stu-id="374c3-136">Troubleshooting</span></span>

<span data-ttu-id="374c3-137">Ниже даны решения распространенных проблем.</span><span class="sxs-lookup"><span data-stu-id="374c3-137">Following are solutions to commonly encountered issues:</span></span>
  
- <span data-ttu-id="374c3-138">**Проблема: развертывание не отвечает или перестает отвечать при запуске сценариев развертывания. После входа на каждую ВМ IP-адрес отсутствует или неверен для сети управления, внутренней или внешней сети.**</span><span class="sxs-lookup"><span data-stu-id="374c3-138">**Issue: Deployment fails or stops responding when running the deployment scripts. After logging on to each VM, the IP address is missing or incorrect for the Management/Internal/External NIC.**</span></span>
    
    <span data-ttu-id="374c3-139">**Решение:** Эту проблему невозможно устранить автоматически.</span><span class="sxs-lookup"><span data-stu-id="374c3-139">**Resolution:** This issue cannot be resolved automatically.</span></span> <span data-ttu-id="374c3-140">NiCs нельзя добавить на ВМ во время их работы.</span><span class="sxs-lookup"><span data-stu-id="374c3-140">NICs cannot be added to VMs while they are running.</span></span> <span data-ttu-id="374c3-141">Закройте и удалите эти ВМ в диспетчере Hyper-V, а затем запустите следующие команды:</span><span class="sxs-lookup"><span data-stu-id="374c3-141">Please shut down and remove these VMs in hyper-v manager, then run the following cmdlets:</span></span>
    
  ```powershell
  Uninstall-CcAppliance
  ```

  ```powershell
  Install-CcAppliance
  ```

- 
    
    <span data-ttu-id="374c3-142">**Проблема: после установки сервера Active Directory и леса сервер CMS и/или сервер-посредник не присоединились к домену правильно.**</span><span class="sxs-lookup"><span data-stu-id="374c3-142">**Issue: After the Active Directory Server and forest are installed, the CMS Server and/or Mediation Server did not join the domain correctly.**</span></span>
    
    <span data-ttu-id="374c3-143">**Решение:** Чтобы устранить эту проблему, необходимо предпринять следующие действия.</span><span class="sxs-lookup"><span data-stu-id="374c3-143">**Resolution:** To resolve this issue, take the following steps:</span></span>
    
  - <span data-ttu-id="374c3-144">Войдите на сервер Active Directory Server и убедитесь, что домен создан правильно.</span><span class="sxs-lookup"><span data-stu-id="374c3-144">Log on to the Active Directory Server and verify that the domain was created correctly.</span></span>
    
  - <span data-ttu-id="374c3-145">Войдите на сервер CMS или сервер-посредник и убедитесь, что в подсети corpnet назначен действительный IP-адрес, а допустимый статический IP-адрес и DNS настроены в качестве IP-адреса сервера AD.</span><span class="sxs-lookup"><span data-stu-id="374c3-145">Log on to the CMS/Mediation Server and verify that on the corpnet NIC a valid IP address is assigned, and that valid static IP and DNS is configured as the AD server's IP address.</span></span>
    
  - <span data-ttu-id="374c3-146">Войдите на сервер CMS или сервер-посредник и откройте командную подсказку.</span><span class="sxs-lookup"><span data-stu-id="374c3-146">Log on to the CMS/Mediation Server, and open a command prompt.</span></span> <span data-ttu-id="374c3-147">Убедитесь, что вы можете сделать ping FQDN и IP-адрес сервера Active Directory Server.</span><span class="sxs-lookup"><span data-stu-id="374c3-147">Make sure you can ping the FQDN and IP address of the Active Directory Server.</span></span> <span data-ttu-id="374c3-148">Если это невозможно, может возникнуть конфликт IP-адресов.</span><span class="sxs-lookup"><span data-stu-id="374c3-148">If you cannot, there may be an IP address conflict.</span></span> <span data-ttu-id="374c3-149">Попробуйте назначить новый IP-адрес для Active Directory и соответствующим образом обновить DNS на сервере-посреднике или CMS.</span><span class="sxs-lookup"><span data-stu-id="374c3-149">Please try to assign a new IP for Active Directory and update DNS on the CMS/Mediation server accordingly.</span></span>
    
- <span data-ttu-id="374c3-150">**Проблема: вы получаете следующее сообщение об ошибке: "Remove-VMSwitch : Failed while removing virtual Ethernet switch. Виртуальный коммутатор "Cloud Connector Management Switch" нельзя удалить, так как он используется при запуске виртуальных машин или в качестве назначенного для него пула".**</span><span class="sxs-lookup"><span data-stu-id="374c3-150">**Issue: You receive the following error message, "Remove-VMSwitch : Failed while removing virtual Ethernet switch. The virtual switch 'Cloud Connector Management Switch' cannot be deleted because it is being used by running virtual machines or assigned to child pools."**</span></span>
    
    <span data-ttu-id="374c3-151">**Решение:** После развертывания не был удален переключатель управления Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="374c3-151">**Resolution:** The "Cloud Connector Management Switch" was not deleted after the deployment.</span></span> <span data-ttu-id="374c3-152">Если вы нажмете эту ошибку, перейдите в диспетчер Hyper-v и убедитесь, что виртуальная машина еще не подключена к ней.</span><span class="sxs-lookup"><span data-stu-id="374c3-152">If you hit this error, please go to Hyper-v manager and verify that there is not still a virtual machine still connected to it.</span></span> <span data-ttu-id="374c3-153">Если виртуальные машины по-прежнему подключены, отключите их и удалите коммутатор управления.</span><span class="sxs-lookup"><span data-stu-id="374c3-153">If there are virtual machines still connected, disconnect them and delete the management switch.</span></span> <span data-ttu-id="374c3-154">Если удалить коммутатор управления по-прежнему невозможно, перезапустите сервер хост-сервера и повторите попытку.</span><span class="sxs-lookup"><span data-stu-id="374c3-154">If the management switch still cannot be deleted, restart the host server and try again.</span></span>
    
- <span data-ttu-id="374c3-155">**Проблема: вы получаете следующее сообщение об ошибке: "Не удалось запустить службу RTCMRAUTH. Убедитесь, что служба не отключена".**</span><span class="sxs-lookup"><span data-stu-id="374c3-155">**Issue: You receive the following error message, "Service RTCMRAUTH failed to start. Check to make sure the service is not disabled."**</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="374c3-156">Эта проблема относится только к версиям Cloud Connector более ранних версий, чем 1.4.2.</span><span class="sxs-lookup"><span data-stu-id="374c3-156">This issue only applies to Cloud Connector versions earlier than 1.4.2.</span></span> 
  
    <span data-ttu-id="374c3-157">Сбой при запуске также может произойти из-за того, что этот сервер переднего сервера был ранее переудачен (с помощью отказа компьютера).</span><span class="sxs-lookup"><span data-stu-id="374c3-157">The failure to start could also be because this Front End server was previously failed over (using computer fail over).</span></span> <span data-ttu-id="374c3-158">В этом случае вы должны вызвать отбой (используя отбой компьютера).</span><span class="sxs-lookup"><span data-stu-id="374c3-158">If that's the case, please invoke fail back (using computer fail back).</span></span>
    
    <span data-ttu-id="374c3-159">**Решение:** Эта проблема происходит на сервере, когда сертификат корневого или промежуточного ЦС не является доверенным для этого сервера.</span><span class="sxs-lookup"><span data-stu-id="374c3-159">**Resolution:** This issue happens on an Edge Server when the root CA certificate or intermediate CA certificate is not trusted by the Edge Server.</span></span> <span data-ttu-id="374c3-160">Даже если внешний сертификат можно импортировать, но цепочка сертификатов разбита.</span><span class="sxs-lookup"><span data-stu-id="374c3-160">Even if the external certificate can be imported but the certificate chain is broken.</span></span> <span data-ttu-id="374c3-161">При этом условии не может запуститься служба RTCMRAUTH и/или RTCSRV.</span><span class="sxs-lookup"><span data-stu-id="374c3-161">Under this condition, the RTCMRAUTH and/or RTCSRV service can not start.</span></span>
    
    <span data-ttu-id="374c3-162">Импортировать сертификат корневого ЦС и все промежуточные сертификаты ЦС внешнего сертификата вручную на edge-сервер, а затем перезапустить его.</span><span class="sxs-lookup"><span data-stu-id="374c3-162">Please import the root CA certificate and all intermediate CA certificates of your external certificate manually into the Edge Server and then restart the Edge Server.</span></span> <span data-ttu-id="374c3-163">После запуска служб RTCMRAUTH и RTCSRV на сервере edge, перейдите на хост-сервер, запустите консоль PowerShell от имени администратора и запустите следующий cmdlet, чтобы переключиться на новое развертывание:</span><span class="sxs-lookup"><span data-stu-id="374c3-163">After you see the RTCMRAUTH and RTCSRV services started on the Edge Server, go back to your host server, launch a PowerShell console as administrator, and run following cmdlet to switch to the new deployment:</span></span>
    
  ```powershell
  Switch-CcVersion
  ```

- 
    
    <span data-ttu-id="374c3-164">**Проблема: сервер-сервер был перезапущен при применении обновлений Windows и сбое вызовов, отслужив их.**</span><span class="sxs-lookup"><span data-stu-id="374c3-164">**Issue: The host server was restarted when Windows updates were applied, and calls serviced by the server are failing.**</span></span>
    
    <span data-ttu-id="374c3-165">**Решение:** Если развернута среда с высоким уровнем доступности, корпорация Майкрософт предоставляет для перемещения одного хост-компьютера (экземпляра развертывания) в текущую топологию или из нее при проверке и установке обновления Windows вручную.</span><span class="sxs-lookup"><span data-stu-id="374c3-165">**Resolution:** If you deployed a high availability environment, Microsoft provides a cmdlet to help move one host machine (deployment instance) into or out of the current topology when you check and install Windows update manually.</span></span> <span data-ttu-id="374c3-166">Для этого с помощью следующих действий:</span><span class="sxs-lookup"><span data-stu-id="374c3-166">Use the following steps to accomplish this:</span></span>
    
1. <span data-ttu-id="374c3-167">На сервере хост-сервера запустите консоль PowerShell от учетной записи администратора, а затем запустите ок.</span><span class="sxs-lookup"><span data-stu-id="374c3-167">On the host server, start a PowerShell console as administrator, then run:</span></span>
    
   ```powershell
   Enter-CcUpdate
   ```

2. <span data-ttu-id="374c3-168">Проверьте, нет ли обновлений и установите все доступные.</span><span class="sxs-lookup"><span data-stu-id="374c3-168">Check for updates and install any that are available.</span></span>
    
3. <span data-ttu-id="374c3-169">В консоли PowerShell запустите следующий cmdlet:</span><span class="sxs-lookup"><span data-stu-id="374c3-169">In the PowerShell console, run the following cmdlet:</span></span>
    
   ```powershell
   Exit-CcUpdate
   ```

- 
    
    <span data-ttu-id="374c3-170">**Проблема: при вызове из клиента Skype для бизнеса с использованием номера STN вызов не может быть перенастроен в конференцию путем приглашения другого номера ЗВОНКОВ.**</span><span class="sxs-lookup"><span data-stu-id="374c3-170">**Issue: When a call is made from a Skype for Business client using a PSTN number, the call cannot be escalated to a conference by inviting another PSTN number.**</span></span>
    
    <span data-ttu-id="374c3-171">**Решение:** Чтобы устранить эту проблему, см. ["Настройка параметров сетевого гибридного сервера-посредника".](configure-cloud-connector-integration-with-your-office-365-tenant.md#BKMK_ConfigureMediationServer)</span><span class="sxs-lookup"><span data-stu-id="374c3-171">**Resolution:** To resolve this issue, see [Configure online hybrid Mediation Server Settings](configure-cloud-connector-integration-with-your-office-365-tenant.md#BKMK_ConfigureMediationServer).</span></span>
    
- <span data-ttu-id="374c3-172">**Проблема: при установке сервера Active Directory отображается предупреждение об Обновлении Windows : "Автоматическое обновление Windows не включено. Чтобы убедиться, что новая роль или функция автоматически обновлены, включите Обновление Windows".**</span><span class="sxs-lookup"><span data-stu-id="374c3-172">**Issue: A warning message is displayed about Windows Update when you are installing Active Directory server - "Windows automatic updating is not enabled. To ensure that your newly-installed role or feature is automatically updated, turn on Windows Update."**</span></span>
    
    <span data-ttu-id="374c3-173">**Решение:** Запустите удаленный сеанс PowerShell клиента с помощью учетных данных администратора клиента Skype для бизнеса, а затем запустите следующий cmdlet, чтобы проверить конфигурацию _EnableAutoUpdate_ сайта:</span><span class="sxs-lookup"><span data-stu-id="374c3-173">**Resolution:** Launch a Tenant Remote PowerShell session using Skype for Business tenant admin credentials, then run the following cmdlet to check the _EnableAutoUpdate_ configuration of your site:</span></span>
    
  ```powershell
  Get-CsHybridPSTNSite
  ```

    <span data-ttu-id="374c3-174">Если  _для enableAutoUpdate_ установлено значение **True,** вы можете игнорировать это предупреждение, так как служба CCEManagement будет обрабатывать загрузку и установку обновлений Windows для виртуальных машин и хост-сервера.</span><span class="sxs-lookup"><span data-stu-id="374c3-174">If  _EnableAutoUpdate_ is set to **True**, you can safely ignore this warning message because the CCEManagement service will handle downloading and installing Windows updates for both virtual machines and the host server.</span></span> <span data-ttu-id="374c3-175">Если _для enableAutoUpdate установлено_ **false,** запустите следующий cmdlet, чтобы установить для него **true.**</span><span class="sxs-lookup"><span data-stu-id="374c3-175">If  _EnableAutoUpdate_ is set to **False**, run following cmdlet to set it to **True**.</span></span>
    
  ```powershell
  Set-CsHybridPSTNSite -EnableAutoUpdate $true
  ```

    <span data-ttu-id="374c3-176">Кроме того, вы можете вручную проверить и установить обновления.</span><span class="sxs-lookup"><span data-stu-id="374c3-176">Alternatively, you can manually check for and install updates.</span></span> <span data-ttu-id="374c3-177">(см. следующий раздел).</span><span class="sxs-lookup"><span data-stu-id="374c3-177">See the next section.</span></span>
    
- <span data-ttu-id="374c3-178">**Проблема: вы получаете сообщение об ошибке: не удается зарегистрировать устройство, так как текущая ввод/конфигурация или или конфликтующая с существующими \<SiteName\> \<ApplianceName\> \<Mediation Server FQDN\> \<Mediation Server IP Address\> устройствами. Удалите устройство для конфликтов или обновите данные ввода и конфигурации, а затем снова зарегистрируйтесь. ' при запуске Register-CcAppliance для регистрации текущего устройства в Сети.**</span><span class="sxs-lookup"><span data-stu-id="374c3-178">**Issue: You receive an error message: Cannot register appliance because your current input/configuration \<SiteName\> or \<ApplianceName\> or \<Mediation Server FQDN\> or \<Mediation Server IP Address\> conflicts with existing appliance(s). Remove conflict appliance or update your input/configuration information then register again. ' when run Register-CcAppliance to register current appliance to online.**</span></span>
    
    <span data-ttu-id="374c3-179">**Решение:** Значения для и должны быть \<ApplianceName\> \<Mediation Server FQDN\> \<Mediation Server IP Address\> уникальными и использоваться только для одной регистрации устройства.</span><span class="sxs-lookup"><span data-stu-id="374c3-179">**Resolution:** Values for the \<ApplianceName\>, \<Mediation Server FQDN\> and \<Mediation Server IP Address\> must be unique and only used for one appliance registration.</span></span> <span data-ttu-id="374c3-180">По умолчанию происходит \<ApplianceName\> из имени хоста.</span><span class="sxs-lookup"><span data-stu-id="374c3-180">By default, \<ApplianceName\> comes from the host name.</span></span> <span data-ttu-id="374c3-181">\<Mediation Server FQDN\> и \<Mediation Server IP Address\> определено в ini-файле конфигурации.</span><span class="sxs-lookup"><span data-stu-id="374c3-181">\<Mediation Server FQDN\> and \<Mediation Server IP Address\> defined in configuration ini file.</span></span>
    
    <span data-ttu-id="374c3-182">Например, using (ApplianceName= MyserverNew, Сервер-посредник: FQDN=ms.contoso.com, IP-адрес сервера-посредника=10.10.10.10) для регистрации в SiteName=MySite, но если имеется зарегистрированное устройство (ApplianceName= Myserver, Mediation Server FQDN=ms.contoso.com, MEDIATION Server IP Address=10.10.10.10), будет возник конфликт.</span><span class="sxs-lookup"><span data-stu-id="374c3-182">For example, using (ApplianceName= MyserverNew, Mediation Server FQDN=ms.contoso.com, Mediation Server IP Address=10.10.10.10) to register to SiteName=MySite, but if there is a registered appliance (ApplianceName= Myserver, Mediation Server FQDN=ms.contoso.com, Mediation Server IP Address=10.10.10.10), you will have the conflict.</span></span>
    
    <span data-ttu-id="374c3-183">Сначала проверьте файл CloudConnector.ini в разделе каталога ApplianceRoot.</span><span class="sxs-lookup"><span data-stu-id="374c3-183">First, please check your CloudConnector.ini file in ApplianceRoot directory section.</span></span> <span data-ttu-id="374c3-184">Вы получите \<SiteName\> и значения в \<Mediation Server FQDN\> \<Mediation Server IP Address\> файле.</span><span class="sxs-lookup"><span data-stu-id="374c3-184">You will get \<SiteName\>, \<Mediation Server FQDN\> and \<Mediation Server IP Address\> values in the file.</span></span> <span data-ttu-id="374c3-185">\<ApplianceName\> — имя сервера хост-сервера.</span><span class="sxs-lookup"><span data-stu-id="374c3-185">\<ApplianceName\> is your host server name.</span></span>
    
    <span data-ttu-id="374c3-186">Во-вторых, запустите удаленную powerShell клиента с помощью учетных данных администратора клиента Skype для бизнеса, а затем запустите следующий cmdlet, чтобы проверить зарегистрированные устройства.</span><span class="sxs-lookup"><span data-stu-id="374c3-186">Second, Launch Tenant Remote PowerShell using your Skype for Business tenant admin credentials, then run the following cmdlet to check the registered appliance(s).</span></span>
    
  ```powershell
  Get-CsHybridPSTNAppliance
  ```

    <span data-ttu-id="374c3-187">После выявления конфликтов можно либо обновить файл CloudConnector.ini данными, которые совпадают с зарегистрированным устройством, либо отозарегистрировать существующее устройство для устранения конфликтов.</span><span class="sxs-lookup"><span data-stu-id="374c3-187">After identifying any conflicts, you can either update your CloudConnector.ini file with information that matches the registered appliance, or unregister the existing appliance to resolve the conflicts.</span></span>
    
  ```powershell
  Unregister-CsHybridPSTNAppliance -Force
  ```

    
- <span data-ttu-id="374c3-188">**Проблема: Get-CcRunningVersion возвращает пустое значение, если на хосте запущено развернуто устройство.**</span><span class="sxs-lookup"><span data-stu-id="374c3-188">**Issue: The Get-CcRunningVersion cmdlet returns an empty value if there is a deployed appliance running on the host.**</span></span>
    
  <span data-ttu-id="374c3-189">**Решение:** Это может произойти при обновлении с 1.3.4 или 1.3.8 до 1.4.1.</span><span class="sxs-lookup"><span data-stu-id="374c3-189">**Resolution:** This can happen when you upgrade from 1.3.4 or 1.3.8 to 1.4.1.</span></span> <span data-ttu-id="374c3-190">После установки версии 1.4.1 с MSI необходимо выполнить перед запуском любого `Register-CcAppliance` другого cmdlet.</span><span class="sxs-lookup"><span data-stu-id="374c3-190">After you install version 1.4.1 with the .msi, you must run `Register-CcAppliance` before you run any other cmdlet.</span></span> <span data-ttu-id="374c3-191">`Register-CcAppliance` будет перенесен module.ini из %UserProfile%\CloudConnector в %ProgramData%\CloudConnector.</span><span class="sxs-lookup"><span data-stu-id="374c3-191">`Register-CcAppliance` will migrate the module.ini file from %UserProfile%\CloudConnector to %ProgramData%\CloudConnector.</span></span> <span data-ttu-id="374c3-192">Если вы пропустили его, module.ini будет создан в папке %ProgramData%\CloudConnector и замените сведения о запущенной или резервной версии для версии 1.3.4 или 1.3.8.</span><span class="sxs-lookup"><span data-stu-id="374c3-192">If you missed it, a new module.ini will be created in %ProgramData%\CloudConnector folder and replace the running/backup version information for 1.3.4 or 1.3.8.</span></span>
    
  <span data-ttu-id="374c3-193">Сравните module.ini файлов в папках %UserProfile%\CloudConnector и %ProgramData%\CloudConnector.</span><span class="sxs-lookup"><span data-stu-id="374c3-193">Compare module.ini files in %UserProfile%\CloudConnector and %ProgramData%\CloudConnector folder.</span></span> <span data-ttu-id="374c3-194">Если имеются различия, удалите файл module.ini в папке %ProgramData%\CloudConnector и повторно перезапустить  `Register-CcAppliance` .</span><span class="sxs-lookup"><span data-stu-id="374c3-194">If there are differences, delete the module.ini file in %ProgramData%\CloudConnector and rerun  `Register-CcAppliance`.</span></span> <span data-ttu-id="374c3-195">Вы также можете изменить файл вручную до правильной запущенной и резервной версии.</span><span class="sxs-lookup"><span data-stu-id="374c3-195">You could also modify the file manually to the correct running and backup version.</span></span>
    
- <span data-ttu-id="374c3-196">**Проблема: после запуска Switch-CcVersion для перехода на старую версию, которая отличается от текущей версии сценария, поддержка высокой доступности для этой старой версии не поддерживается.**</span><span class="sxs-lookup"><span data-stu-id="374c3-196">**Issue: After you run the Switch-CcVersion cmdlet to switch to an old version which is different from current script version, there is no High Availability support for this old version.**</span></span>
    
    <span data-ttu-id="374c3-197">**Решение:** Например, вы обновили 1.4.1 до 1.4.2.</span><span class="sxs-lookup"><span data-stu-id="374c3-197">**Resolution:** For example, you have upgraded from 1.4.1 to 1.4.2.</span></span> <span data-ttu-id="374c3-198">Текущая версия сценария, которую можно определить при запуске, и текущая версия, которую можно определить при запуске, — `Get-CcVersion`  `Get-CcRunningVersion` 1.4.2.</span><span class="sxs-lookup"><span data-stu-id="374c3-198">Your current script version, which can be determined by running `Get-CcVersion`, and your running version, which can be determined by running  `Get-CcRunningVersion` are both 1.4.2.</span></span> <span data-ttu-id="374c3-199">В настоящее время, если вы запустите для переключения запущенной версии обратно на 1.4.1, поддержка высокой доступности для этой старой версии `Switch-CcVersion` не будет.</span><span class="sxs-lookup"><span data-stu-id="374c3-199">At this time, if you run `Switch-CcVersion` to switch the running version back to 1.4.1, then there will be no High Availability support for this old version.</span></span>
    
    <span data-ttu-id="374c3-200">Чтобы получить полную поддержку высокой доступности, переключиться обратно на версию 1.4.2, чтобы версия и версия сценария были одинаковыми.</span><span class="sxs-lookup"><span data-stu-id="374c3-200">To get full High Availability support, please switch back to 1.4.2, so the running version and script version are the same.</span></span> <span data-ttu-id="374c3-201">Если у вас возникают проблемы с развертыванием 1.4.2, как можно скорее удалить и переустановить его.</span><span class="sxs-lookup"><span data-stu-id="374c3-201">If you are experiencing problems with your 1.4.2 deployment, please uninstall and reinstall it as soon as possible.</span></span>
    
- <span data-ttu-id="374c3-202">**Проблема: срок действия сертификатов центра сертификации или внутренних сертификатов, выдав центру управления, серверу-посреднику и серверу-посреднику, истекает или они скомпрометированы.**</span><span class="sxs-lookup"><span data-stu-id="374c3-202">**Issue: Certificate authority certificates or internal certificates issued to Central Management Store, Mediation Server, and Edge Server are near expiration or are compromised.**</span></span>
    
    <span data-ttu-id="374c3-203">**Решение:** Сертификаты сертификации Skype для бизнеса действительны в течение пяти лет.</span><span class="sxs-lookup"><span data-stu-id="374c3-203">**Resolution:** Skype for Business certification authority certificates are valid for five years.</span></span> <span data-ttu-id="374c3-204">Внутренние сертификаты, выдамые центральному правлению, серверу-посреднику и серверу-посреднику, действуют в течение двух лет.</span><span class="sxs-lookup"><span data-stu-id="374c3-204">Internal certificates issued to the Central Management Store, Mediation Server, and Edge Server are valid for two years.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="374c3-205">В Cloud Connector версии 2.0 и более поздних версиях Renew-CcServerCertificate был изменен на Update-CcServerCertificate, а Renew-CcCACertificate — на Update-CcCACertificate.</span><span class="sxs-lookup"><span data-stu-id="374c3-205">In Cloud Connector version 2.0 and later, the Renew-CcServerCertificate cmdlet has changed to Update-CcServerCertificate and the Renew-CcCACertificate cmdlet has changed to Update-CcCACertificate.</span></span> 
  
    <span data-ttu-id="374c3-206">Если срок действия внутренних сертификатов, выданных центральному окнову управления, серверу-посреднику и серверу-посреднику, истекает или скомпрометирован, запустите Renew-CcServerCertificate или Update-CcServerCertificate для обновления сертификатов.</span><span class="sxs-lookup"><span data-stu-id="374c3-206">If internal certificates issued to the Central Management Store, Mediation Server, and Edge Server are near expiration or compromised, run the Renew-CcServerCertificate or Update-CcServerCertificate cmdlet to renew your certificates.</span></span>
    
    <span data-ttu-id="374c3-207">Если срок действия сертификатов цс сертификации истекает, запустите Renew-CcCACertificate или Update-CcCACertificate для продления сертификатов.</span><span class="sxs-lookup"><span data-stu-id="374c3-207">If certification authority certificates are near expiration, run the Renew-CcCACertificate or Update-CcCACertificate cmdlet to renew your certificates.</span></span>
    
    <span data-ttu-id="374c3-208">**Если сертификаты сертификационного** органа скомпрометированы и на сайте имеется только одно устройство, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="374c3-208">**If certification authority certificates are compromised and there is only one appliance in the site,** perform the following steps:</span></span>
    
1. <span data-ttu-id="374c3-209">Запустите Enter-CcUpdate для истощать службы и помещая устройство в режим обслуживания.</span><span class="sxs-lookup"><span data-stu-id="374c3-209">Run the Enter-CcUpdate cmdlet to drain services and put the appliance in maintenance mode.</span></span>
   
   ```powershell
   Enter-CcUpdate
   ```
   
2. <span data-ttu-id="374c3-210">Чтобы сбросить и создать новые сертификаты цс сертификации и все внутренние сертификаты сервера, запустите следующие cmdlets:</span><span class="sxs-lookup"><span data-stu-id="374c3-210">Run the following cmdlets to reset and create new certification authority certificates and all internal server certificates:</span></span>
    
    <span data-ttu-id="374c3-211">Для выпусков Cloud Connector до версии 2.0:</span><span class="sxs-lookup"><span data-stu-id="374c3-211">For Cloud Connector releases before 2.0:</span></span>
    
    ```powershell
    Reset-CcCACertificate 
    Renew-CcServerCertificate 
    Remove-CcLegacyServerCertificate 
    ```

    <span data-ttu-id="374c3-212">Или для Cloud Connector версии 2.0 и более поздних версий:</span><span class="sxs-lookup"><span data-stu-id="374c3-212">Or for Cloud Connector release 2.0 and later:</span></span>
    
    ```powershell
    Reset-CcCACertificate 
    Update-CcServerCertificate 
    Remove-CcLegacyServerCertificate 
    ```
    
3. <span data-ttu-id="374c3-213">Если между шлюзом и сервером-посредником используется TLS, запустите Export-CcRootCertificate с устройства, а затем установите экспортный сертификат на шлюзы STN.</span><span class="sxs-lookup"><span data-stu-id="374c3-213">If TLS is used between the gateway and the Mediation Server, run the Export-CcRootCertificate cmdlet from the appliance, and then install the exported certificate to your PSTN gateways.</span></span> <span data-ttu-id="374c3-214">Кроме того, может потребоваться повторное выдача сертификата на шлюзе.</span><span class="sxs-lookup"><span data-stu-id="374c3-214">You may also be required to re-issue the certificate on your gateway.</span></span>

   ```powershell
   Export-CcRootCertificate
   ```

4. <span data-ttu-id="374c3-215">Запустите Exit-CcUpdate, чтобы запустить службы и выйти из режима обслуживания.</span><span class="sxs-lookup"><span data-stu-id="374c3-215">Run the Exit-CcUpdate cmdlet to start services and exit maintenance mode.</span></span>

   ```powershell
   Exit-CcUpdate
   ```


    <span data-ttu-id="374c3-216">**Если сертификаты сертификации** скомпрометированы и на сайте имеется несколько устройств, выполните следующие последовательное действия на каждом устройстве на сайте.</span><span class="sxs-lookup"><span data-stu-id="374c3-216">**If certification authority certificates are compromised and there are multiple appliances in the site,** perform the following sequential steps on each appliance in the site.</span></span>
    
    <span data-ttu-id="374c3-217">Корпорация Майкрософт рекомендует выполнять эти действия в периоды не пиковой нагрузки.</span><span class="sxs-lookup"><span data-stu-id="374c3-217">Microsoft recommends that you perform these steps during non-peak usage times.</span></span>
    
1. <span data-ttu-id="374c3-218">На первом устройстве запустите Remove-CcCertificationAuthorityFile для очистки файлов резервной копии ЦС в \<SiteRoot\> каталоге.</span><span class="sxs-lookup"><span data-stu-id="374c3-218">On the first appliance, run the Remove-CcCertificationAuthorityFile cmdlet to clean up the CA backup files in the \<SiteRoot\> directory.</span></span>

     ```powershell
     Remove-CcCertificationAuthorityFile
     ```
    
2. <span data-ttu-id="374c3-219">Запустите Enter-CcUpdate, чтобы оцедить службы и поместить каждое устройство в режим обслуживания.</span><span class="sxs-lookup"><span data-stu-id="374c3-219">Run the Enter-CcUpdate cmdlet to drain services and put each appliance in maintenance mode.</span></span>

     ```powershell
     Enter-CcUpdate
     ```
    
3. <span data-ttu-id="374c3-220">На первом устройстве запустите следующие cmdlets для сброса и создания новых сертификатов цс сертификации и всех внутренних сертификатов сервера:</span><span class="sxs-lookup"><span data-stu-id="374c3-220">On the first appliance, run the following cmdlets to reset and create new certification authority certificates and all internal server certificates:</span></span>
    
     <span data-ttu-id="374c3-221">Для выпусков Cloud Connector до версии 2.0:</span><span class="sxs-lookup"><span data-stu-id="374c3-221">For Cloud Connector releases before 2.0:</span></span>
    
     ```powershell
     Reset-CcCACertificate
     Renew-CcServerCertificate
     Remove-CcLegacyServerCertificate 
     ```

     <span data-ttu-id="374c3-222">Или для Cloud Connector версии 2.0 и более поздних версий:</span><span class="sxs-lookup"><span data-stu-id="374c3-222">Or for Cloud Connector release 2.0 and later:</span></span>
    
     ```powershell
     Reset-CcCACertificate
     Update-CcServerCertificate
     Remove-CcLegacyServerCertificate 
     ```

4. <span data-ttu-id="374c3-223">На первом устройстве запустите следующий cmdlet для архива файлов ЦС в \<SiteRoot\> папке.</span><span class="sxs-lookup"><span data-stu-id="374c3-223">On the first appliance, run the following cmdlet to back up the CA files to the \<SiteRoot\> folder.</span></span>
    
     ```powershell
     Backup-CcCertificationAuthority
     ```
   
5. <span data-ttu-id="374c3-224">На всех остальных устройствах на том же сайте запустите следующие команды, чтобы использовать файлы резервных копий ЦС, чтобы все устройства использовали один и тот же корневой сертификат, а затем запросите новые сертификаты.</span><span class="sxs-lookup"><span data-stu-id="374c3-224">On all other appliance's in the same site, run the following commands to consume the CA backup files, so that the appliances all use the same root certificate, and then request new certificates.</span></span> 
   
     ```powershell
     Reset-CcCACertificate
     Update-CcServerCertificate
     Remove-CcLegacyServerCertificate 
     ```
     
6. <span data-ttu-id="374c3-225">Если между шлюзом и сервером-посредником используется TLS, запустите Export-CcRootCertificate с любого устройства на сайте, а затем установите экспортный сертификат на шлюзы STN.</span><span class="sxs-lookup"><span data-stu-id="374c3-225">If TLS is used between the gateway and the Mediation Server, run the Export-CcRootCertificate cmdlet from any appliance in the site, and then install the exported certificate to your PSTN gateways.</span></span> <span data-ttu-id="374c3-226">Кроме того, может потребоваться повторное выдача сертификата на шлюзе.</span><span class="sxs-lookup"><span data-stu-id="374c3-226">You may also be required to re-issue the certificate on your gateway.</span></span>
  
     ```powershell
     Export-CcRootCertificate
     ```
     
7. <span data-ttu-id="374c3-227">Запустите Exit-CcUpdate, чтобы запустить службы и выйти из режима обслуживания.</span><span class="sxs-lookup"><span data-stu-id="374c3-227">Run the Exit-CcUpdate cmdlet to start services and exit maintenance mode.</span></span> 

     ```powershell
     Exit-CcUpdate
     ```
    
    
- <span data-ttu-id="374c3-228">**Проблема: в журнале службы управления Cloud Connector вы получаете следующее сообщение об ошибке: "C:\Program Files\Skype for Business Cloud Connector Edition\ManagementService\CceManagementService.log": ошибка CceService: 0 : непредвиденное исключение при отчете о состоянии в сети: System.Management.Automation.CmdletInvocationException: ошибка входа для пользователя \<Global Tenant Admin\> . Создайте новый объект учетных данных, убедившись, что вы использовали правильное имя пользователя и пароль. ---\>**</span><span class="sxs-lookup"><span data-stu-id="374c3-228">**Issue: You receive the following error message in the Cloud Connector Management Service Log, "C:\Program Files\Skype for Business Cloud Connector Edition\ManagementService\CceManagementService.log": CceService Error: 0 : Unexpected exception when reporting status to online: System.Management.Automation.CmdletInvocationException: Logon failed for the user \<Global Tenant Admin\>. Please create a new credential object, making sure that you have used the correct user name and password. ---\>**</span></span>
    
    <span data-ttu-id="374c3-229">**Решение:** Учетные данные глобального администратора клиента Microsoft 365 или Office 365 были изменены с момента регистрации устройства Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="374c3-229">**Resolution:** The Microsoft 365 or Office 365 global tenant admin credentials have been changed since the Cloud Connector appliance was registered.</span></span> <span data-ttu-id="374c3-230">Чтобы обновить локально хранимые учетные данные на устройстве Cloud Connector, запустите в powerShell администратора на хост-устройстве следующее:</span><span class="sxs-lookup"><span data-stu-id="374c3-230">To update the locally stored credentials on the Cloud Connector appliance, run the following from Administrator PowerShell on the host appliance:</span></span>
    
  ```powershell
  Set-CcCredential -AccountType TenantAdmin
  ```

- <span data-ttu-id="374c3-231">**Проблема: после изменения пароля учетной записи сервера размещения, используемой для развертывания, вы получите следующее сообщение об ошибке: "ConvertTo-SecureString : key not valid for use in specified state." in %ProgramFiles%\Skype for Business Cloud Connector Edition\ManagementService\CceManagementService.log or while running the Get-CcCredential cmdlet.**</span><span class="sxs-lookup"><span data-stu-id="374c3-231">**Issue: After you change the password for the host server account you used for the deployment, you receive the following error message: "ConvertTo-SecureString : Key not valid for use in specified state." in %ProgramFiles%\Skype for Business Cloud Connector Edition\ManagementService\CceManagementService.log or while running the Get-CcCredential cmdlet.**</span></span>
    
    <span data-ttu-id="374c3-232">**Решение:** Все учетные данные Cloud Connector хранятся в следующем файле: "%SystemDrive%\Programdata\Cloudconnector\credentials. \<CurrentUser\> xml".</span><span class="sxs-lookup"><span data-stu-id="374c3-232">**Resolution:** All Cloud Connector credentials are stored in the following file: "%SystemDrive%\Programdata\Cloudconnector\credentials.\<CurrentUser\>.xml".</span></span> <span data-ttu-id="374c3-233">При смене пароля на сервере на хост-сервере потребуется обновить локально сохраненные учетные данные.</span><span class="sxs-lookup"><span data-stu-id="374c3-233">When the password on the host server changes, you will need to update the locally stored credentials.</span></span>
    
    <span data-ttu-id="374c3-234">**Если вы работаете с Cloud Connector версии 1.4.2,** повторно развяжите все пароли Cloud Connector, выдав следующие действия:</span><span class="sxs-lookup"><span data-stu-id="374c3-234">**If you are running Cloud Connector version 1.4.2,** regenerate all Cloud Connector passwords by following these steps:</span></span>
    
  1. <span data-ttu-id="374c3-235">Перезапустите сервер хост-сервера.</span><span class="sxs-lookup"><span data-stu-id="374c3-235">Restart the host server.</span></span>
    
  2. <span data-ttu-id="374c3-236">Удалите следующий файл: "%SystemDrive%\Programdata\Cloudconnector\credentials. \<CurrentUser\> xml".</span><span class="sxs-lookup"><span data-stu-id="374c3-236">Delete the following file: "%SystemDrive%\Programdata\Cloudconnector\credentials.\<CurrentUser\>.xml".</span></span>
    
  3. <span data-ttu-id="374c3-237">Запустите консоль PowerShell от учетной записи администратора, а затем запустите "Register-CcAppliance -Local", чтобы повторно ввести пароли, следуя описанию.</span><span class="sxs-lookup"><span data-stu-id="374c3-237">Launch a PowerShell console as administrator, and then run "Register-CcAppliance -Local" to re-enter the passwords following the description.</span></span> <span data-ttu-id="374c3-238">Введите те же пароли, которые были введены ранее для развертывания Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="374c3-238">Enter the same passwords you entered before for the Cloud Connector deployment.</span></span>
    
     <span data-ttu-id="374c3-239">**Если вы работаете под управлением Cloud Connector версии 2.0** или более поздней, повторно вы можете повторно использовать все пароли Cloud Connector, выдав следующие действия:</span><span class="sxs-lookup"><span data-stu-id="374c3-239">**If you are running Cloud Connector version 2.0 or later,** regenerate all Cloud Connector passwords by following these steps:</span></span>
    
  4. <span data-ttu-id="374c3-240">Перезапустите сервер хост-сервера.</span><span class="sxs-lookup"><span data-stu-id="374c3-240">Restart the host server.</span></span>
    
  5. <span data-ttu-id="374c3-241">Удалите следующий файл: "%SystemDrive%\Programdata\Cloudconnector\credentials. \<CurrentUser\> xml" .</span><span class="sxs-lookup"><span data-stu-id="374c3-241">Delete the following file: "%SystemDrive%\Programdata\Cloudconnector\credentials.\<CurrentUser\>.xml" .</span></span>
    
  6. <span data-ttu-id="374c3-242">Запустите консоль PowerShell от учетной записи администратора, а затем запустите "Register-CcAppliance -Local", чтобы повторно ввести пароли, следуя описанию.</span><span class="sxs-lookup"><span data-stu-id="374c3-242">Launch a PowerShell console as administrator, and then run "Register-CcAppliance -Local" to re-enter the passwords following the description.</span></span> 
    
     <span data-ttu-id="374c3-243">Если cached password file was generated with Cloud Connector version 1.4.2, use the VMAdmin password for the CceService password when prompted.</span><span class="sxs-lookup"><span data-stu-id="374c3-243">If the cached password file was generated with Cloud Connector version 1.4.2, use the VMAdmin password for the CceService password when prompted.</span></span> <span data-ttu-id="374c3-244">Введите тот же пароль, который был введен ранее для развертывания Cloud Connector для всех остальных учетных записей.</span><span class="sxs-lookup"><span data-stu-id="374c3-244">Enter the same password you entered before for the Cloud Connector deployment for all other accounts.</span></span>
    
     <span data-ttu-id="374c3-245">Если cached password file was generated with Cloud Connector version 1.4.2 and the DomainAdmin and VMAdmin passwords are different, you must perform the following steps:</span><span class="sxs-lookup"><span data-stu-id="374c3-245">If the cached password file was generated with Cloud Connector version 1.4.2 and the DomainAdmin and VMAdmin passwords are different, you must perform the following steps:</span></span>
    
  7. <span data-ttu-id="374c3-246">Выполните Set-CcCredential -AccountType DomainAdmin следующим образом:</span><span class="sxs-lookup"><span data-stu-id="374c3-246">Run Set-CcCredential -AccountType DomainAdmin as follows:</span></span>
    
  8. <span data-ttu-id="374c3-247">При запросе учетных данных старой учетной записи введите учетные данные, использованные для пароля CceService.</span><span class="sxs-lookup"><span data-stu-id="374c3-247">When prompted for the old account credential, enter the credential you used for the CceService password.</span></span>
    
  9. <span data-ttu-id="374c3-248">При запросе учетных данных новой учетной записи введите пароль для пароля DomainAdmin, который вы использовали ранее.</span><span class="sxs-lookup"><span data-stu-id="374c3-248">When prompted for the new account credential, enter the password for the DomainAdmin password you used before.</span></span>
    
     <span data-ttu-id="374c3-249">Если файл кэширован паролей был создан с помощью Cloud Connector версии 2.0 или более поздней, по умолчанию VmAdmin и DomainAdmin используют тот же пароль, что и CceService.</span><span class="sxs-lookup"><span data-stu-id="374c3-249">If the cached password file was generated with Cloud Connector version 2.0 or later, by default, VmAdmin and DomainAdmin use the same password as CceService.</span></span> <span data-ttu-id="374c3-250">Если вы изменили пароли DomainAdmin и VMAdmin, необходимо выполнить следующие действия:</span><span class="sxs-lookup"><span data-stu-id="374c3-250">If you changed the DomainAdmin and VMAdmin passwords, you must perform the following steps:</span></span>
    
  10. <span data-ttu-id="374c3-251">Выполните Set-CcCredential -AccountType DomainAdmin следующим образом:</span><span class="sxs-lookup"><span data-stu-id="374c3-251">Run Set-CcCredential -AccountType DomainAdmin as follows:</span></span>
    
       1. <span data-ttu-id="374c3-252">При запросе учетных данных старой учетной записи введите учетные данные, использованные для пароля CceService</span><span class="sxs-lookup"><span data-stu-id="374c3-252">When prompted for the old account credential, enter the credential you used for the CceService password</span></span>
    
       2. <span data-ttu-id="374c3-253">При запросе учетных данных новой учетной записи введите пароль для пароля DomainAdmin, который вы использовали ранее.</span><span class="sxs-lookup"><span data-stu-id="374c3-253">When prompted for the new account credential, enter the password for the DomainAdmin password you used before.</span></span>
    
  11. <span data-ttu-id="374c3-254">Выполните Set-CcCredential -AccountType VmAdmin следующим образом:</span><span class="sxs-lookup"><span data-stu-id="374c3-254">Run Set-CcCredential -AccountType VmAdmin as follows:</span></span>
    
       1. <span data-ttu-id="374c3-255">При запросе учетных данных старой учетной записи введите учетные данные, использованные для пароля CceService</span><span class="sxs-lookup"><span data-stu-id="374c3-255">When prompted for the old account credential, enter the credential you used for the CceService password</span></span>
    
       2. <span data-ttu-id="374c3-256">При запросе учетных данных новой учетной записи введите пароль для ранее использованного пароля VmAdmin.</span><span class="sxs-lookup"><span data-stu-id="374c3-256">When prompted for the new account credential, enter the password for the VmAdmin password you used before.</span></span> 
    
- <span data-ttu-id="374c3-257">**Проблема: При работе с Cloud Connector версии 2.1 и более поздних версий при запуске Register-CcAppliance или других cmdlets на устройстве вы получаете сообщение об ошибке, например: "For Each-Object : The property 'Common' cannot be found on this object. Убедитесь, что свойство существует. В C:\Program Files\WindowsPowerShell\Modules\CloudConnector\Internal\MtHostCommon.ps1:681 char:14"**</span><span class="sxs-lookup"><span data-stu-id="374c3-257">**Issue: With Cloud Connector version 2.1 and later, when running Register-CcAppliance or other cmdlets on the appliance, you receive an error message such as: "For Each-Object : The property 'Common' cannot be found on this object. Verify that the property exists. At C:\Program Files\WindowsPowerShell\Modules\CloudConnector\Internal\MtHostCommon.ps1:681 char:14"**</span></span>
    
    <span data-ttu-id="374c3-258">**Решение:** Для Cloud Connector 2.1 и более поздних требуется .NET Framework 4.6.1 или более поздней.</span><span class="sxs-lookup"><span data-stu-id="374c3-258">**Resolution:** Cloud Connector 2.1 and later requires .NET Framework 4.6.1 or later.</span></span> <span data-ttu-id="374c3-259">Обновите .NET Framework на устройстве до версии 4.6.1 или более поздней, а затем снова запустите их.</span><span class="sxs-lookup"><span data-stu-id="374c3-259">Please update .NET Framework on the appliance to version 4.6.1 or later and run the cmdlet(s) again.</span></span>

- <span data-ttu-id="374c3-260">**Проблема: в Cloud Connector Edition 2.1 при запуске Install-CcAppliance вы получаете сообщение об ошибке, например: "Не удалось установить новый экземпляр с ошибкой: не удается установить "State", так как только строки можно использовать в качестве значений для установки свойств XmlNode"**</span><span class="sxs-lookup"><span data-stu-id="374c3-260">**Issue: With Cloud Connector Edition 2.1, when running Install-CcAppliance, you receive an error message such as: "Failed to install new instance with error: Cannot set "State" because only strings can be used as values to set XmlNode properties"**</span></span>

   <span data-ttu-id="374c3-261">**Решение:** В Cloudconnector.ini разделе [Common] добавьте config "State", как по умолчанию: CountryCode=US State=WA City=Redmond</span><span class="sxs-lookup"><span data-stu-id="374c3-261">**Resolution:** In Cloudconnector.ini, under the [Common] section, please add the “State” config as below:  CountryCode=US  State=WA  City=Redmond</span></span>

   <span data-ttu-id="374c3-262">Строка "Состояние" не обязательно должна иметь значение, но строку "Состояние" нельзя удалить из Cloudconnector.ini файла.</span><span class="sxs-lookup"><span data-stu-id="374c3-262">It is not mandatory for the "State" line to have value, however the "State" line cannot be removed from the Cloudconnector.ini file.</span></span>

- <span data-ttu-id="374c3-263">**Проблема: вы получаете следующее сообщение об ошибке"Dismount-WindowsImage : Dismount-WindowsImage ошибка. Код ошибки = 0xc1550115" при установке или обновлении Cloud Connector Edition.**</span><span class="sxs-lookup"><span data-stu-id="374c3-263">**Issue: You receive the following error message "Dismount-WindowsImage : Dismount-WindowsImage failed. Error code = 0xc1550115" when installing or upgrading Cloud Connector Edition.**</span></span>
    
    <span data-ttu-id="374c3-264">**Решение:** Запустите консоль PowerShell от администратора и запустите "DISM -Cleanup-Wim".</span><span class="sxs-lookup"><span data-stu-id="374c3-264">**Resolution:** Launch a PowerShell console as administrator, run "DISM -Cleanup-Wim'".</span></span> <span data-ttu-id="374c3-265">При этом будут очищены все проблемные изображения.</span><span class="sxs-lookup"><span data-stu-id="374c3-265">This will clean up all troubled images.</span></span> <span data-ttu-id="374c3-266">Запустите Install-CcAppliance или дождись автоматического обновления битов.</span><span class="sxs-lookup"><span data-stu-id="374c3-266">Run Install-CcAppliance again or wait for the bits to automatically upgrade.</span></span>
    
- <span data-ttu-id="374c3-267">**Проблема: сбой развертывания первого устройства Cloud Connector в среде ha**</span><span class="sxs-lookup"><span data-stu-id="374c3-267">**Issue: Deployment of the first Cloud Connector appliance in an HA environment fails**</span></span>
    
    <span data-ttu-id="374c3-268">**Решение:** Действия, которые необходимо предпринять, зависят от причины сбой развертывания:</span><span class="sxs-lookup"><span data-stu-id="374c3-268">**Resolution:** The steps you take depend on the reason the deployment failed:</span></span>
    
  - <span data-ttu-id="374c3-269">В случае сбоя первого устройства Cloud Connector и невозможно определить причину сбоя, необходимо снова установить устройство, пока развертывание не будет успешным, а затем установить другие устройства.</span><span class="sxs-lookup"><span data-stu-id="374c3-269">If the first Cloud Connector appliance fails and you cannot determine the reason for the failure, you must install the appliance again until the deployment is successful, and then install the other appliances.</span></span>
    
  - <span data-ttu-id="374c3-270">Если сбой первого устройства Cloud Connector возникает из-за незначительных проблем, таких как проблема с внешним сертификатом, вы можете устранить проблему без повторной установки устройства.</span><span class="sxs-lookup"><span data-stu-id="374c3-270">If the first Cloud Connector appliance fails with a minor issue, such as an external certificate issue, you might be able to fix the problem without re-installing the appliance.</span></span> <span data-ttu-id="374c3-271">Затем вы можете использовать удаленную удаленную овецу PowerShell клиента, чтобы отметить развертывание как успешное следующим образом.</span><span class="sxs-lookup"><span data-stu-id="374c3-271">You can then use tenant remote PowerShell to mark the deployment as successful as follows.</span></span> <span data-ttu-id="374c3-272">(Вы также можете использовать следующие действия, если первое развертывание было успешным, но по какой-либо причине Cloud Connector не сообщает об успешном развертывании.)</span><span class="sxs-lookup"><span data-stu-id="374c3-272">(You can also use the following steps if the first deployment was successful, but, for some reason, Cloud Connector fails to report the deployment as a success.)</span></span>
    
  - <span data-ttu-id="374c3-273">Чтобы получить идентификатор (GUID) первого устройства Cloud Connector, запустите Get-CsHybridPSTNAppliance.</span><span class="sxs-lookup"><span data-stu-id="374c3-273">To get the Identity (GUID) of the first Cloud Connector appliance, run the Get-CsHybridPSTNAppliance cmdlet.</span></span>
    
  - <span data-ttu-id="374c3-274">Чтобы пометить устройство как успешно развернуто, выполните Set-CsCceApplianceDeploymentStatus следующим образом:</span><span class="sxs-lookup"><span data-stu-id="374c3-274">To mark the appliance as successfully deployed, run the Set-CsCceApplianceDeploymentStatus as follows:</span></span>
    
  ```powershell
  Set-CsCceApplianceDeploymentStatus -Identity <Appliance Identity GUID> -Action Deploy -Status Finished
  ```

- <span data-ttu-id="374c3-275">**Проблема: необходимо вручную проверить и установить обновления Windows на сервере хост-сервера или виртуальных машинах.**</span><span class="sxs-lookup"><span data-stu-id="374c3-275">**Issue: You need to check for and install Windows updates manually on the host server or virtual machines.**</span></span>
    
   <span data-ttu-id="374c3-276">**Решение:** Мы рекомендуем использовать преимущества автоматических обновлений ОС, предоставляемых Skype для бизнеса Cloud Connector Edition.</span><span class="sxs-lookup"><span data-stu-id="374c3-276">**Resolution:** We recommend that you take advantage of automated OS updates provided by Skype for Business Cloud Connector Edition.</span></span> <span data-ttu-id="374c3-277">После регистрации устройства для управления через Интернет и включения автоматического обновления ОС сервер хост-сервера и виртуальные машины будут проверять и устанавливать обновления Windows автоматически в соответствии с настройками времени обновления ОС.</span><span class="sxs-lookup"><span data-stu-id="374c3-277">After an appliance is registered for online management and auto OS update is enabled, the host server and virtual machines will check and install Windows Updates automatically according to the OS update time window settings.</span></span>
    
   <span data-ttu-id="374c3-278">Если вам нужно проверить и установить обновления Windows вручную, выполните действия в этом разделе, применимые к вашему типу развертывания.</span><span class="sxs-lookup"><span data-stu-id="374c3-278">If you need to check for and install Windows Updates manually, follow the steps in this section that apply to your type of deployment.</span></span> <span data-ttu-id="374c3-279">Следует запланировать одновременное обновление сервера хост-сервера и виртуальных машин, работающих на нем, чтобы свести к минимуму время простоя, необходимое для обновления.</span><span class="sxs-lookup"><span data-stu-id="374c3-279">You should plan on updating both the host server and the virtual machines running on it at the same time to minimize the amount of down time necessary for the updates.</span></span>
    
   <span data-ttu-id="374c3-280">При этом можно использовать сервер cлужбы Windows Server Update Services (WSUS) для предоставления обновлений серверам Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="374c3-280">If you prefer, you can use a Windows Server Update Services (WSUS) server to provide updates to Cloud Connector servers.</span></span> <span data-ttu-id="374c3-281">Просто убедитесь, что Обновление Windows не **устанавливается** автоматически.</span><span class="sxs-lookup"><span data-stu-id="374c3-281">Just be sure to configure the Windows Update to **not** install automatically.</span></span>
    
   <span data-ttu-id="374c3-282">Сведения об обновлении развертывания Cloud Connector вручную см. в следующем разделе.</span><span class="sxs-lookup"><span data-stu-id="374c3-282">For information about how to manually update your Cloud Connector deployment, see the following section.</span></span>
    
- <span data-ttu-id="374c3-283">**Проблема: при обновлении Cloud Connector до новой сборки, не обновляются их cmdlets.**</span><span class="sxs-lookup"><span data-stu-id="374c3-283">**Issue: When Cloud Connector updates to a new build, Cloud Connector cmdlets are not updated.**</span></span> <span data-ttu-id="374c3-284">Иногда это происходит, если окно PowerShell остается открытым при автоматическом обновлении.</span><span class="sxs-lookup"><span data-stu-id="374c3-284">This sometimes happens if a PowerShell window is left open when automatic update occurs.</span></span>
    
  <span data-ttu-id="374c3-285">**Решение:** Чтобы загрузить обновленные cmdlets, можно сделать один из следующих действий:</span><span class="sxs-lookup"><span data-stu-id="374c3-285">**Resolution:** To load the updated cmdlets, you can do either of the following steps:</span></span>
    
   - <span data-ttu-id="374c3-286">Закроем PowerShell на устройстве Cloud Connector, а затем снова откроете PowerShell.</span><span class="sxs-lookup"><span data-stu-id="374c3-286">Close PowerShell on the Cloud Connector appliance, and then reopen PowerShell.</span></span>
    
     - <span data-ttu-id="374c3-287">Также можно запустить Import-Module CloudConnector -Force.</span><span class="sxs-lookup"><span data-stu-id="374c3-287">Or, you can run Import-Module CloudConnector -Force.</span></span> 
 
-   <span data-ttu-id="374c3-288">**Проблема: "Термин "Stop-CsWindowsService" не распознается как имя Enter-CcUpdate, функции, файла скрипта или программы.**</span><span class="sxs-lookup"><span data-stu-id="374c3-288">**Issue: "The term 'Stop-CsWindowsService' is not recognized as the name of a cmdlet, function, script file, or operable program." error when attempting to run Enter-CcUpdate cmdlet.**</span></span>

    <span data-ttu-id="374c3-289">**Решение:** Удалите файл $HOME\AppData\Local\Microsoft\Windows\PowerShell\ModuleAnalysisCache.</span><span class="sxs-lookup"><span data-stu-id="374c3-289">**Resolution:** Delete the $HOME\AppData\Local\Microsoft\Windows\PowerShell\ModuleAnalysisCache file.</span></span>
<span data-ttu-id="374c3-290">PowerShell создает этот файл как кэш командлетов из модулей, которые он находит, чтобы не каждый раз повторно анализировать все модули, так как это может замедлить процесс.</span><span class="sxs-lookup"><span data-stu-id="374c3-290">PowerShell creates this file as a cache of cmdlets from modules that it finds so that it doesn’t have to re-analyze all the modules each time as that would make things really slow.</span></span> <span data-ttu-id="374c3-291">Скорее всего, при чтении данных из этого кэша в PowerShell были повреждения файлов, которые вводящие в заблуждение результаты.</span><span class="sxs-lookup"><span data-stu-id="374c3-291">Most likely, there was some file corruption that provided misleading results to PowerShell when it was reading back from that cache.</span></span>

-   <span data-ttu-id="374c3-292">**Проблема: "Import-Module CloudConnector" генерирует ошибку "Import-Module: указанный модуль "CloudConnector" не загружен, так как в каталоге модулей не найден действительный файл модуля"**</span><span class="sxs-lookup"><span data-stu-id="374c3-292">**Issue: “Import-Module CloudConnector” generates error “Import-Module: The specified module “CloudConnector” was not loaded because no valid module file was found in any module directory”**</span></span>

    <span data-ttu-id="374c3-293">**Решение.**</span><span class="sxs-lookup"><span data-stu-id="374c3-293">**Resolution:**</span></span>
    - <span data-ttu-id="374c3-294">Проверьте, существует ли модуль CloudConnector в папке c:\Program Files\WindowsPowerShell\Modules</span><span class="sxs-lookup"><span data-stu-id="374c3-294">Validate that indeed the CloudConnector module exists under c:\Program Files\WindowsPowerShell\Modules</span></span>
    
    - <span data-ttu-id="374c3-295">После проверки того, что модуль CloudConnector существует в этом расположении, переменную среды PSModulePath, в которой хранятся пути к расположениям модулей, можно изменить:</span><span class="sxs-lookup"><span data-stu-id="374c3-295">After validating that CloudConnector module exists under this location, the PSModulePath environment variable storing the path to the locations of the modules can be changed:</span></span>
    
     <span data-ttu-id="374c3-296">а.</span><span class="sxs-lookup"><span data-stu-id="374c3-296">a.</span></span> <span data-ttu-id="374c3-297">Временное изменение: запустите Powershell с учетной записи администратора и запустите следующую команду: $env:PSModulePath = $env:PSModulePath + "; C:\Program Files\WindowsPowerShell\Modules\"</span><span class="sxs-lookup"><span data-stu-id="374c3-297">Temporary change: Start Powershell as an Administrator and run the following command: $env:PSModulePath = $env:PSModulePath + ";C:\Program Files\WindowsPowerShell\Modules\"</span></span>
        
     <span data-ttu-id="374c3-298">б.</span><span class="sxs-lookup"><span data-stu-id="374c3-298">b.</span></span> <span data-ttu-id="374c3-299">Для постоянного изменения запустите PowerShell как администратор и запустите следующие команды по одной: $CurrentValue = [Среда]::GetEnvironmentVariable("PSModulePath", "Machine") SetEnvironmentVariable("PSModulePath", $CurrentValue + "; C:\Program Files\WindowsPowerShell\Modules", "Machine")</span><span class="sxs-lookup"><span data-stu-id="374c3-299">For persistent change, Start PowerShell as an Administrator and run the following commands, one by one: $CurrentValue = [Environment]::GetEnvironmentVariable("PSModulePath", "Machine") SetEnvironmentVariable("PSModulePath", $CurrentValue + "; C:\Program Files\WindowsPowerShell\Modules", "Machine")</span></span>

    
## <a name="install-windows-updates-manually"></a><span data-ttu-id="374c3-300">Установка обновлений Windows вручную</span><span class="sxs-lookup"><span data-stu-id="374c3-300">Install Windows updates manually</span></span>

<span data-ttu-id="374c3-301">Если вы не хотите использовать автоматические обновления в своей среде, выполните следующие действия, чтобы вручную проверить и применить обновления Windows.</span><span class="sxs-lookup"><span data-stu-id="374c3-301">If you do not want to use automatic updates in your environment, follow these steps to manually check for and apply Windows updates.</span></span> <span data-ttu-id="374c3-302">Для проверки и установки обновлений Windows может потребоваться перезапуск сервера.</span><span class="sxs-lookup"><span data-stu-id="374c3-302">Checking for and installing Windows updates may require a server restart.</span></span> <span data-ttu-id="374c3-303">При перезапуске хост-сервера пользователи не смогут использовать Cloud Connector для проведения или получения вызовов.</span><span class="sxs-lookup"><span data-stu-id="374c3-303">When a host server is restarting, users will not be able to use Cloud Connector to place or receive calls.</span></span> <span data-ttu-id="374c3-304">Вы можете вручную проверить и установить обновления, чтобы контролировать время обновления, а затем перезапустить компьютеры по мере необходимости во время, чтобы избежать нарушения работы служб.</span><span class="sxs-lookup"><span data-stu-id="374c3-304">You can manually check for and install updates to control when the updates take place, and then restart the machines as needed during times you choose to avoid disruption of services.</span></span>
  
<span data-ttu-id="374c3-305">Чтобы вручную проверить обновления, подключите каждый сервер и откройте панель **управления.**</span><span class="sxs-lookup"><span data-stu-id="374c3-305">To manually check for updates, connect to each host server and open the **Control Panel**.</span></span> <span data-ttu-id="374c3-306">Выберите **"System and Security \> Update"**(Обновление Windows для системы и системы безопасности), а затем управляйте обновлениями и перезапусками сервера в соответствующей среде.</span><span class="sxs-lookup"><span data-stu-id="374c3-306">Select **System and Security \>Windows Update**, and then manage the updates and server restarts as appropriate for your environment.</span></span>
  
- <span data-ttu-id="374c3-307">Если на сайте имеется только одно устройство, подключите каждую виртуальную машину и откройте панель **управления.**</span><span class="sxs-lookup"><span data-stu-id="374c3-307">If there is only one appliance in the site, connect to each virtual machine and open the **Control Panel**.</span></span> <span data-ttu-id="374c3-308">Выберите **"System and Security \> Update"**(Обновление Windows для системы и системы безопасности), а затем настройте обновления и перезагрузку сервера соответствующим образом.</span><span class="sxs-lookup"><span data-stu-id="374c3-308">Select **System and Security \>Windows Update**, and then configure the updates and server restarts as appropriate.</span></span>
    
- <span data-ttu-id="374c3-309">Если на сайте несколько устройств, обновляемая и перезапускаемая версия экземпляра не будет доступны пользователям во время обновления.</span><span class="sxs-lookup"><span data-stu-id="374c3-309">If there are more than one appliance in the site, the instance being updated and restarted cannot be accessed by users during the updates.</span></span> <span data-ttu-id="374c3-310">Пользователи будут подключаться к другим экземплярам в развертывании до тех пор, пока все виртуальные машины и все службы Skype для бизнеса не будут запускаться на виртуальных машинах после завершения обновления.</span><span class="sxs-lookup"><span data-stu-id="374c3-310">Users will connect to other instances in the deployment until all virtual machines and all Skype for Business services start on the virtual machines after the updates are completed.</span></span> <span data-ttu-id="374c3-311">Чтобы избежать потенциального нарушения работы службы, можно удалить экземпляр из службы ha во время применения обновлений, а затем восстановить его по завершению.</span><span class="sxs-lookup"><span data-stu-id="374c3-311">To avoid any potential disruption to service, you can remove the instance from HA while you apply the updates, and then restore it when complete.</span></span> <span data-ttu-id="374c3-312">Для этого:</span><span class="sxs-lookup"><span data-stu-id="374c3-312">To do so:</span></span>
    
1. <span data-ttu-id="374c3-313">На каждом сервере хост-сервера откройте консоль PowerShell от учетной записи администратора.</span><span class="sxs-lookup"><span data-stu-id="374c3-313">On each host server, open a PowerShell console as administrator.</span></span>
    
2. <span data-ttu-id="374c3-314">Удалите экземпляр из ha с помощью следующего cmdlet:</span><span class="sxs-lookup"><span data-stu-id="374c3-314">Remove the instance from HA with the following cmdlet:</span></span>
    
   ```powershell
   Enter-CcUpdate
   ```

3. 
    
    <span data-ttu-id="374c3-315">Выполните действия для одного экземпляра, чтобы вручную применить обновления и перезапустить виртуальную машину.</span><span class="sxs-lookup"><span data-stu-id="374c3-315">Follow the steps for a single instance to manually apply the updates and restart the virtual machine.</span></span>
    
4. <span data-ttu-id="374c3-316">Установите для экземпляра обратно ha с помощью следующего cmdlet:</span><span class="sxs-lookup"><span data-stu-id="374c3-316">Set the instance back to HA with the following cmdlet:</span></span>
    
   ```powershell
   Exit-CcUpdate
   ```

<span data-ttu-id="374c3-317">Для развертывания с несколькими сайтами выполните действия для одного сайта для каждого сайта в развертывании, применяя обновления к одному сайту за раз.</span><span class="sxs-lookup"><span data-stu-id="374c3-317">For multi-site deployments, follow the steps for a single site for each site in the deployment, applying updates to one site at a time.</span></span>
  
## <a name="tips-when-installing-anti-virus-software-on-the-cloud-connector-host-machine"></a><span data-ttu-id="374c3-318">Советы по установке антивирусного программного обеспечения на хост-компьютер Cloud Connector</span><span class="sxs-lookup"><span data-stu-id="374c3-318">Tips when installing anti-virus software on the Cloud Connector host machine</span></span>

<span data-ttu-id="374c3-319">Если необходимо установить антивирусное ПО на хост-компьютер Cloud Connector, необходимо добавить следующие исключения:</span><span class="sxs-lookup"><span data-stu-id="374c3-319">If you need to install anti-virus software on the Cloud Connector host machine, you need to add the following exclusions:</span></span>
  
- <span data-ttu-id="374c3-320">Локальный каталог устройств на каждом компьютере.</span><span class="sxs-lookup"><span data-stu-id="374c3-320">Local Appliance Directory on each machine.</span></span>
    
- <span data-ttu-id="374c3-321">Удаленный каталог сайтов на каждом компьютере.</span><span class="sxs-lookup"><span data-stu-id="374c3-321">Remote Site Directory on each machine.</span></span>
    
- <span data-ttu-id="374c3-322">В локальном каталоге сайтов на компьютере размещена общая корневая папка сайта.</span><span class="sxs-lookup"><span data-stu-id="374c3-322">Local Site Directory on the machine hosts the shared site root folder.</span></span>
    
- <span data-ttu-id="374c3-323">%ProgramFiles%\Skype for Business Cloud Connector Edition</span><span class="sxs-lookup"><span data-stu-id="374c3-323">%ProgramFiles%\Skype for Business Cloud Connector Edition</span></span>
    
- <span data-ttu-id="374c3-324">%ALLUSERSPROFILE%\CloudConnector</span><span class="sxs-lookup"><span data-stu-id="374c3-324">%ALLUSERSPROFILE%\CloudConnector</span></span>
    
- <span data-ttu-id="374c3-325">%ProgramFiles%\WindowsPowerShell\Modules\CloudConnector</span><span class="sxs-lookup"><span data-stu-id="374c3-325">%ProgramFiles%\WindowsPowerShell\Modules\CloudConnector</span></span>
    
- <span data-ttu-id="374c3-326">Процесс Microsoft.Rtc.CCE.ManagementService.exe.</span><span class="sxs-lookup"><span data-stu-id="374c3-326">The process Microsoft.Rtc.CCE.ManagementService.exe.</span></span>
