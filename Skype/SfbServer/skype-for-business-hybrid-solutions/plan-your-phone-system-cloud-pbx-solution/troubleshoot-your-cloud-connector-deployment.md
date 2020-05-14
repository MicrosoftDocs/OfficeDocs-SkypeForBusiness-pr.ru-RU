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
ms.openlocfilehash: 97ece0ee1bcc11c22fd55709d025169ed95b16ff
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/13/2020
ms.locfileid: "44220229"
---
# <a name="troubleshoot-your-cloud-connector-deployment"></a><span data-ttu-id="78aef-103">Устранение неполадок с развертыванием Cloud Connector</span><span class="sxs-lookup"><span data-stu-id="78aef-103">Troubleshoot your Cloud Connector deployment</span></span>
 
<span data-ttu-id="78aef-104">Устранение неполадок развертывания Cloud Connector Edition.</span><span class="sxs-lookup"><span data-stu-id="78aef-104">Troubleshoot your Cloud Connector Edition deployment.</span></span>
  
<span data-ttu-id="78aef-105">В этом разделе описываются решения распространенных проблем, связанных с развертываниями Cloud Connector Edition.</span><span class="sxs-lookup"><span data-stu-id="78aef-105">This topic describes solutions to common issues with Cloud Connector Edition deployments.</span></span> <span data-ttu-id="78aef-106">Если у вас возникли проблемы с вызовами и из телефонной сети общего пользования (PSTN), вы можете изучить следующие решения, описанные в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="78aef-106">If you are experiencing issues with calls to and from the Public Switched Telephone Network (PSTN), you can investigate by following the solutions described in this topic.</span></span>
  
<span data-ttu-id="78aef-107">Cloud Connector предоставляет встроенные механизмы для автоматического устранения некоторых проблем.</span><span class="sxs-lookup"><span data-stu-id="78aef-107">Cloud Connector provides built-in mechanisms for automatically resolving some issues.</span></span> <span data-ttu-id="78aef-108">Процесс автоматического обнаружения выполняет поиск потенциальных проблем для устройств Cloud Connector и, если это возможно, предпринимает корректирующие меры по устранению этих проблем без необходимости вмешательства администратора.</span><span class="sxs-lookup"><span data-stu-id="78aef-108">An automatic detection process looks for potential issues with the Cloud Connector appliances, and, if possible, takes corrective action to resolve those issues without the need for administrator intervention.</span></span> <span data-ttu-id="78aef-109">Процесс обнаружения работает следующим образом:</span><span class="sxs-lookup"><span data-stu-id="78aef-109">The detection process works as follows:</span></span>
  
- <span data-ttu-id="78aef-110">**Последовательность обнаружения:** Служба управления Cloud Connector запускает процесс каждые 60 секунд, чтобы определить, не отключено ли устройство.</span><span class="sxs-lookup"><span data-stu-id="78aef-110">**Detection sequence:** The Cloud Connector Management service runs a process every 60 seconds for detecting whether an appliance is down.</span></span> <span data-ttu-id="78aef-111">В Cloud Connector версии 2,0 и более поздних в процессе обнаружения используется переключатель в корпоративной сети Skype для бизнеса для создания подключений PowerShell к машинам Cloud Connector; для версий, предшествующих 2,0, процесс обнаружения использует коммутатор управления Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="78aef-111">In Cloud Connector version 2.0 and later, the detection process uses the Skype for Business Corpnet switch for making PowerShell connections to the Cloud Connector machines; for versions previous to 2.0, the detection process uses the Cloud Connector management switch.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="78aef-112">Для успешного выполнения автоматического восстановления между узлом и виртуальными машинами должно быть установлено сетевое подключение через коммутатор узла сети.</span><span class="sxs-lookup"><span data-stu-id="78aef-112">For automatic recovery to succeed, there must be network connectivity between the host and virtual machines over the host network switch.</span></span> <span data-ttu-id="78aef-113">Обязательно проверьте сетевое подключение, чтобы убедиться, что автоматическое обнаружение и восстановление может быть успешным.</span><span class="sxs-lookup"><span data-stu-id="78aef-113">Be sure to check network connectivity to ensure that automatic detection and recovery can succeed.</span></span> 
  
- <span data-ttu-id="78aef-114">**Мониторинг:** Следующие службы отслеживаются в Cloud Connector версии 2,0 и более поздних:</span><span class="sxs-lookup"><span data-stu-id="78aef-114">**Monitoring:** The following services are monitored in Cloud Connector version 2.0 and later:</span></span>
    
  - <span data-ttu-id="78aef-115">Виртуальные машины не подключены к виртуальным коммутаторам Cloud Connector или Интернет</span><span class="sxs-lookup"><span data-stu-id="78aef-115">Virtual Machines are not connected to the Cloud Connector Corporate or Internet virtual switches</span></span>
    
  - <span data-ttu-id="78aef-116">Виртуальные машины находятся в состоянии "сохранено" или "остановлено"</span><span class="sxs-lookup"><span data-stu-id="78aef-116">Virtual Machines are in a saved or stopped status</span></span>
    
  - <span data-ttu-id="78aef-117">Службы сервера централизованного управления: РЕПЛИКа, основной</span><span class="sxs-lookup"><span data-stu-id="78aef-117">Central Management Server services: REPLICA, MASTER</span></span>
    
  - <span data-ttu-id="78aef-118">Службы сервера-посредника: РЕПЛИКа, RTCSRV и МЕДСВК</span><span class="sxs-lookup"><span data-stu-id="78aef-118">Mediation Server services: REPLICA, RTCSRV and MEDSVC</span></span>
    
  - <span data-ttu-id="78aef-119">Службы пограничных серверов: РЕПЛИКа, RTCSRV, РТКДАТАПРОКСИ, РТКМРАУС, РТКМЕДИАРЕЛАЙ</span><span class="sxs-lookup"><span data-stu-id="78aef-119">Edge Server services: REPLICA, RTCSRV, RTCDATAPROXY, RTCMRAUTH, RTCMEDIARELAY</span></span>
    
  - <span data-ttu-id="78aef-120">Правила брандмауэра для входящих подключений отключены для CS RTCSRV на пограничном сервере, CS РТКМЕДСРВ на сервере-посреднике</span><span class="sxs-lookup"><span data-stu-id="78aef-120">Inbound firewall rules are disabled for CS RTCSRV on Edge server, CS RTCMEDSRV on Mediation server</span></span>
    
    <span data-ttu-id="78aef-121">В Cloud Connector версии 1.4.2 отслеживаются только следующие службы:</span><span class="sxs-lookup"><span data-stu-id="78aef-121">In Cloud Connector version 1.4.2, only the following services are monitored:</span></span>
    
  - <span data-ttu-id="78aef-122">Службы сервера-посредника: RTCSRV и МЕДСВК</span><span class="sxs-lookup"><span data-stu-id="78aef-122">Mediation Server services: RTCSRV and MEDSVC</span></span>
    
  - <span data-ttu-id="78aef-123">Служба пограничного сервера: RTCSRV</span><span class="sxs-lookup"><span data-stu-id="78aef-123">Edge Server service: RTCSRV</span></span>
    
- <span data-ttu-id="78aef-124">**Процесс восстановления:** Если какие-либо отслеживаемые службы отключены, устройство помечается как отключенное, а службы останавливаются и помечаются вручную до тех пор, пока не будут устранены все проблемы.</span><span class="sxs-lookup"><span data-stu-id="78aef-124">**Recovery process:** If any monitored services are down, an appliance is marked down, and services are stopped and marked manual until all issues can be resolved.</span></span> <span data-ttu-id="78aef-125">Это предотвратит маршрутизацию звонков на устройство, которое может привести к сбоям вызовов.</span><span class="sxs-lookup"><span data-stu-id="78aef-125">This will prevent calls from routing to an appliance that may cause call failures.</span></span>
    
    <span data-ttu-id="78aef-126">Служба управления Cloud Connector повторит попытку автоматического восстановления, как показано ниже.</span><span class="sxs-lookup"><span data-stu-id="78aef-126">The Cloud Connector Management service will retry automatic recovery as follows</span></span>
    
  - <span data-ttu-id="78aef-127">Первый интервал повтора составляет каждые десять секунд с максимальным интервалом в один час.</span><span class="sxs-lookup"><span data-stu-id="78aef-127">The initial retry interval is every ten seconds with a maximum interval time of one hour.</span></span>
    
  - <span data-ttu-id="78aef-128">Для первых трех попыток восстановления время ожидания составляет 10 секунд.</span><span class="sxs-lookup"><span data-stu-id="78aef-128">For the first three recovery attempts, the interval time is 10 seconds.</span></span> <span data-ttu-id="78aef-129">Начиная с четвертой попытки, время в интервале увеличивается на два раза больше предыдущего интервала времени.</span><span class="sxs-lookup"><span data-stu-id="78aef-129">Starting from the fourth retry, the interval time increases by two times the previous interval time.</span></span> <span data-ttu-id="78aef-130">Например, четвертая повторная попытка будет выполнена в течение 20 секунд, пятый в 40 секунд и т. д.</span><span class="sxs-lookup"><span data-stu-id="78aef-130">For example, the fourth retry will occur in 20 seconds, the fifth in 40 seconds, and so on.</span></span> 
    
  - <span data-ttu-id="78aef-131">При достижении максимального интервала в один час количество повторных попыток будет продолжаться в час.</span><span class="sxs-lookup"><span data-stu-id="78aef-131">When the maximum interval time of one hour is reached, retries will continue once per hour.</span></span>
    
  - <span data-ttu-id="78aef-132">При успешном завершении восстановления в качестве интервала и числа повторных попыток задаются исходные значения.</span><span class="sxs-lookup"><span data-stu-id="78aef-132">When recovery is successful, the interval and retry counts are set to their initial values.</span></span>
    
  - <span data-ttu-id="78aef-133">Если служба управления перезапущена, счетчики интервалов и повторных попыток сбрасываются в исходные значения.</span><span class="sxs-lookup"><span data-stu-id="78aef-133">If the Management service is restarted, the interval and retry counts are reset to their initial values.</span></span>
    
## <a name="troubleshooting"></a><span data-ttu-id="78aef-134">Устранение неполадок</span><span class="sxs-lookup"><span data-stu-id="78aef-134">Troubleshooting</span></span>

<span data-ttu-id="78aef-135">Ниже приведены решения часто встречающихся проблем.</span><span class="sxs-lookup"><span data-stu-id="78aef-135">Following are solutions to commonly encountered issues:</span></span>
  
- <span data-ttu-id="78aef-136">**Ошибка: при выполнении сценариев развертывания развертывание завершается с ошибкой или перестает отвечать. После входа на каждую виртуальную машину IP-адрес отсутствует или неверен для управления/внутреннего или внешнего сетевого адаптера.**</span><span class="sxs-lookup"><span data-stu-id="78aef-136">**Issue: Deployment fails or stops responding when running the deployment scripts. After logging on to each VM, the IP address is missing or incorrect for the Management/Internal/External NIC.**</span></span>
    
    <span data-ttu-id="78aef-137">**Решение:** Эту проблему невозможно устранить автоматически.</span><span class="sxs-lookup"><span data-stu-id="78aef-137">**Resolution:** This issue cannot be resolved automatically.</span></span> <span data-ttu-id="78aef-138">Сетевые адаптеры Невозможно добавить к виртуальным машинам во время их выполнения.</span><span class="sxs-lookup"><span data-stu-id="78aef-138">NICs cannot be added to VMs while they are running.</span></span> <span data-ttu-id="78aef-139">Завершите работу виртуальных машин и удалите их в диспетчере Hyper – v, а затем выполните следующие командлеты:</span><span class="sxs-lookup"><span data-stu-id="78aef-139">Please shut down and remove these VMs in hyper-v manager, then run the following cmdlets:</span></span>
    
  ```powershell
  Uninstall-CcAppliance
  ```

  ```powershell
  Install-CcAppliance
  ```

- 
    
    <span data-ttu-id="78aef-140">**Вопрос: после установки сервера и/или сервера-посредника Active Directory сервер CMS и/или сервер-посредник не присоединяются к домену должным образом.**</span><span class="sxs-lookup"><span data-stu-id="78aef-140">**Issue: After the Active Directory Server and forest are installed, the CMS Server and/or Mediation Server did not join the domain correctly.**</span></span>
    
    <span data-ttu-id="78aef-141">**Решение:** Чтобы устранить эту проблему, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="78aef-141">**Resolution:** To resolve this issue, take the following steps:</span></span>
    
  - <span data-ttu-id="78aef-142">Выполните вход на сервер Active Directory и убедитесь, что домен создан правильно.</span><span class="sxs-lookup"><span data-stu-id="78aef-142">Log on to the Active Directory Server and verify that the domain was created correctly.</span></span>
    
  - <span data-ttu-id="78aef-143">Выполните вход на сервер CMS/-посредника и убедитесь, что в корпоративной NIC назначен допустимый IP-адрес, а действительный статический IP-адрес и DNS настроены как IP-адрес сервера AD.</span><span class="sxs-lookup"><span data-stu-id="78aef-143">Log on to the CMS/Mediation Server and verify that on the corpnet NIC a valid IP address is assigned, and that valid static IP and DNS is configured as the AD server's IP address.</span></span>
    
  - <span data-ttu-id="78aef-144">Выполните вход на сервер CMS/-посредника и откройте командную строку.</span><span class="sxs-lookup"><span data-stu-id="78aef-144">Log on to the CMS/Mediation Server, and open a command prompt.</span></span> <span data-ttu-id="78aef-145">Убедитесь, что вы можете выполнить команду ping для полного доменного имени и IP-адреса сервера Active Directory.</span><span class="sxs-lookup"><span data-stu-id="78aef-145">Make sure you can ping the FQDN and IP address of the Active Directory Server.</span></span> <span data-ttu-id="78aef-146">Если этого не сделать, может возникнуть конфликт IP-адресов.</span><span class="sxs-lookup"><span data-stu-id="78aef-146">If you cannot, there may be an IP address conflict.</span></span> <span data-ttu-id="78aef-147">Попробуйте назначить новый IP-адрес для Active Directory и соответствующим образом обновить DNS на сервере CMS/-посреднике.</span><span class="sxs-lookup"><span data-stu-id="78aef-147">Please try to assign a new IP for Active Directory and update DNS on the CMS/Mediation server accordingly.</span></span>
    
- <span data-ttu-id="78aef-148">**Причина: вы получите следующее сообщение об ошибке: "Remove – VMSwitch: сбой при удалении виртуального коммутатора Ethernet". Невозможно удалить виртуальный коммутатор с переключателем управления Cloud Connector, так как он используется работающими виртуальными машинами или назначен дочерним пулам. "**</span><span class="sxs-lookup"><span data-stu-id="78aef-148">**Issue: You receive the following error message, "Remove-VMSwitch : Failed while removing virtual Ethernet switch. The virtual switch 'Cloud Connector Management Switch' cannot be deleted because it is being used by running virtual machines or assigned to child pools."**</span></span>
    
    <span data-ttu-id="78aef-149">**Решение:** "Коммутатор управления Cloud Connector" не был удален после развертывания.</span><span class="sxs-lookup"><span data-stu-id="78aef-149">**Resolution:** The "Cloud Connector Management Switch" was not deleted after the deployment.</span></span> <span data-ttu-id="78aef-150">Если вы столкнулись с этой ошибкой, перейдите в Диспетчер Hyper-v и убедитесь, что к ней еще не подключена виртуальная машина.</span><span class="sxs-lookup"><span data-stu-id="78aef-150">If you hit this error, please go to Hyper-v manager and verify that there is not still a virtual machine still connected to it.</span></span> <span data-ttu-id="78aef-151">Если виртуальные машины по-прежнему подключены, отключите их и удалите переключатель управления.</span><span class="sxs-lookup"><span data-stu-id="78aef-151">If there are virtual machines still connected, disconnect them and delete the management switch.</span></span> <span data-ttu-id="78aef-152">Если параметр управления по-прежнему не может быть удален, перезапустите хост-сервер и повторите попытку.</span><span class="sxs-lookup"><span data-stu-id="78aef-152">If the management switch still cannot be deleted, restart the host server and try again.</span></span>
    
- <span data-ttu-id="78aef-153">**Причина: появится следующее сообщение об ошибке: "сбой при запуске службы РТКМРАУС. Убедитесь, что служба не отключена. "**</span><span class="sxs-lookup"><span data-stu-id="78aef-153">**Issue: You receive the following error message, "Service RTCMRAUTH failed to start. Check to make sure the service is not disabled."**</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="78aef-154">Эта проблема относится только к версиям Cloud Connector, предшествующим 1.4.2.</span><span class="sxs-lookup"><span data-stu-id="78aef-154">This issue only applies to Cloud Connector versions earlier than 1.4.2.</span></span> 
  
    <span data-ttu-id="78aef-155">Сбой при запуске может также быть вызван тем, что сервер переднего плана был ранее отработкой отказа (с использованием компьютера при сбое).</span><span class="sxs-lookup"><span data-stu-id="78aef-155">The failure to start could also be because this Front End server was previously failed over (using computer fail over).</span></span> <span data-ttu-id="78aef-156">Если это так, выйдите из строя и снова выйдите из системы.</span><span class="sxs-lookup"><span data-stu-id="78aef-156">If that's the case, please invoke fail back (using computer fail back).</span></span>
    
    <span data-ttu-id="78aef-157">**Решение:** Эта проблема возникает на пограничном сервере, если сертификат корневого центра сертификации или сертификат промежуточного центра сертификации не является доверенным для пограничного сервера.</span><span class="sxs-lookup"><span data-stu-id="78aef-157">**Resolution:** This issue happens on an Edge Server when the root CA certificate or intermediate CA certificate is not trusted by the Edge Server.</span></span> <span data-ttu-id="78aef-158">Даже если внешний сертификат можно импортировать, но цепочка сертификатов разорвана.</span><span class="sxs-lookup"><span data-stu-id="78aef-158">Even if the external certificate can be imported but the certificate chain is broken.</span></span> <span data-ttu-id="78aef-159">В этом случае служба РТКМРАУС и/или RTCSRV не может запуститься.</span><span class="sxs-lookup"><span data-stu-id="78aef-159">Under this condition, the RTCMRAUTH and/or RTCSRV service can not start.</span></span>
    
    <span data-ttu-id="78aef-160">Импортируйте сертификат корневого центра сертификации и все промежуточные сертификаты ЦС внешнего сертификата вручную в пограничный сервер, а затем перезапустите пограничный сервер.</span><span class="sxs-lookup"><span data-stu-id="78aef-160">Please import the root CA certificate and all intermediate CA certificates of your external certificate manually into the Edge Server and then restart the Edge Server.</span></span> <span data-ttu-id="78aef-161">После того как вы увидите службы РТКМРАУС и RTCSRV, запущенные на пограничном сервере, вернитесь на сервер узла, запустите консоль PowerShell от имени администратора и выполните следующий командлет, чтобы переключиться на новое развертывание:</span><span class="sxs-lookup"><span data-stu-id="78aef-161">After you see the RTCMRAUTH and RTCSRV services started on the Edge Server, go back to your host server, launch a PowerShell console as administrator, and run following cmdlet to switch to the new deployment:</span></span>
    
  ```powershell
  Switch-CcVersion
  ```

- 
    
    <span data-ttu-id="78aef-162">**Ошибка: сервер узла был перезапущен при применении обновлений Windows, а вызовы, обслуживаемые сервером, отправляются с ошибкой.**</span><span class="sxs-lookup"><span data-stu-id="78aef-162">**Issue: The host server was restarted when Windows updates were applied, and calls serviced by the server are failing.**</span></span>
    
    <span data-ttu-id="78aef-163">**Решение:** Если вы развернули среду с высокой доступностью, корпорация Майкрософт предоставляет командлет, позволяющий перемещать один хост-компьютер (экземпляр развертывания) в текущую топологию и из нее при проверке и установке центра обновления Windows вручную.</span><span class="sxs-lookup"><span data-stu-id="78aef-163">**Resolution:** If you deployed a high availability environment, Microsoft provides a cmdlet to help move one host machine (deployment instance) into or out of the current topology when you check and install Windows update manually.</span></span> <span data-ttu-id="78aef-164">Чтобы выполнить эту задачу, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="78aef-164">Use the following steps to accomplish this:</span></span>
    
1. <span data-ttu-id="78aef-165">На сервере узла запустите консоль PowerShell от имени администратора, а затем выполните команду:</span><span class="sxs-lookup"><span data-stu-id="78aef-165">On the host server, start a PowerShell console as administrator, then run:</span></span>
    
   ```powershell
   Enter-CcUpdate
   ```

2. <span data-ttu-id="78aef-166">Проверьте наличие обновлений и установите доступные.</span><span class="sxs-lookup"><span data-stu-id="78aef-166">Check for updates and install any that are available.</span></span>
    
3. <span data-ttu-id="78aef-167">В консоли PowerShell выполните следующий командлет:</span><span class="sxs-lookup"><span data-stu-id="78aef-167">In the PowerShell console, run the following cmdlet:</span></span>
    
   ```powershell
   Exit-CcUpdate
   ```

- 
    
    <span data-ttu-id="78aef-168">**Вопрос: при совершении вызова из клиента Skype для бизнеса с помощью номера PSTN этот звонок нельзя эскалировать на конференцию, приглашая еще один номер PSTN.**</span><span class="sxs-lookup"><span data-stu-id="78aef-168">**Issue: When a call is made from a Skype for Business client using a PSTN number, the call cannot be escalated to a conference by inviting another PSTN number.**</span></span>
    
    <span data-ttu-id="78aef-169">**Решение:** Чтобы устранить эту проблему, ознакомьтесь со статьей [Настройка параметров сервера гибридного гибридного сервера-посредника](configure-cloud-connector-integration-with-your-office-365-tenant.md#BKMK_ConfigureMediationServer).</span><span class="sxs-lookup"><span data-stu-id="78aef-169">**Resolution:** To resolve this issue, see [Configure online hybrid Mediation Server Settings](configure-cloud-connector-integration-with-your-office-365-tenant.md#BKMK_ConfigureMediationServer).</span></span>
    
- <span data-ttu-id="78aef-170">**Вопрос: при установке сервера Active Directory ("автоматическое обновление Windows") отображается предупреждающее сообщение об обновлении Windows: "автоматическое обновление Windows не включено". Чтобы убедиться, что недавно установленная роль или функция автоматически обновляется, включите обновление Windows. "**</span><span class="sxs-lookup"><span data-stu-id="78aef-170">**Issue: A warning message is displayed about Windows Update when you are installing Active Directory server - "Windows automatic updating is not enabled. To ensure that your newly-installed role or feature is automatically updated, turn on Windows Update."**</span></span>
    
    <span data-ttu-id="78aef-171">**Решение:** Запустите удаленный сеанс PowerShell клиента с помощью учетных данных администратора клиента Skype для бизнеса, а затем выполните следующий командлет, чтобы проверить конфигурацию _EnableAutoUpdate_ для сайта:</span><span class="sxs-lookup"><span data-stu-id="78aef-171">**Resolution:** Launch a Tenant Remote PowerShell session using Skype for Business tenant admin credentials, then run the following cmdlet to check the _EnableAutoUpdate_ configuration of your site:</span></span>
    
  ```powershell
  Get-CsHybridPSTNSite
  ```

    <span data-ttu-id="78aef-172">Если для _EnableAutoUpdate_ задано **значение true**, можно спокойно проигнорировать это предупреждение, так как служба кцеманажемент будет обрабатывать загрузку и установку обновлений Windows для виртуальных машин и хост-сервера.</span><span class="sxs-lookup"><span data-stu-id="78aef-172">If  _EnableAutoUpdate_ is set to **True**, you can safely ignore this warning message because the CCEManagement service will handle downloading and installing Windows updates for both virtual machines and the host server.</span></span> <span data-ttu-id="78aef-173">Если для _EnableAutoUpdate_ задано значение **false**, выполните следующий командлет, чтобы задать для него значение **true**.</span><span class="sxs-lookup"><span data-stu-id="78aef-173">If  _EnableAutoUpdate_ is set to **False**, run following cmdlet to set it to **True**.</span></span>
    
  ```powershell
  Set-CsHybridPSTNSite -EnableAutoUpdate $true
  ```

    <span data-ttu-id="78aef-174">Кроме того, вы можете вручную проверить наличие обновлений и установить их.</span><span class="sxs-lookup"><span data-stu-id="78aef-174">Alternatively, you can manually check for and install updates.</span></span> <span data-ttu-id="78aef-175">(см. следующий раздел).</span><span class="sxs-lookup"><span data-stu-id="78aef-175">See the next section.</span></span>
    
- <span data-ttu-id="78aef-176">**Причина: отображается сообщение об ошибке: не удается зарегистрировать устройство, так как текущий сервер входа/конфигурации \< SiteName или \> \< выступает имя устройства \> или \< \> IP-адрес сервера-посредника или \< IP-адрес сервера-посредника \> конфликтует с существующими устройствам. Удалите конфликтующее устройство или обновите сведения о входных и конфигурационных данных, а затем повторите регистрацию. ' при выполнении Register-CcAppliance для регистрации текущего устройства в оперативный режим.**</span><span class="sxs-lookup"><span data-stu-id="78aef-176">**Issue: You receive an error message: Cannot register appliance because your current input/configuration \<SiteName\> or \<ApplianceName\> or \<Mediation Server FQDN\> or \<Mediation Server IP Address\> conflicts with existing appliance(s). Remove conflict appliance or update your input/configuration information then register again. ' when run Register-CcAppliance to register current appliance to online.**</span></span>
    
    <span data-ttu-id="78aef-177">**Решение:** Значения для \< выступает имя устройства \> , \< полного доменного имени сервера-посредника \> и \< IP-адреса сервера-посредника \> должны быть уникальными и использоваться только для регистрации одного устройства.</span><span class="sxs-lookup"><span data-stu-id="78aef-177">**Resolution:** Values for the \<ApplianceName\>, \<Mediation Server FQDN\> and \<Mediation Server IP Address\> must be unique and only used for one appliance registration.</span></span> <span data-ttu-id="78aef-178">По умолчанию \< выступает имя устройства \> берется из имени узла.</span><span class="sxs-lookup"><span data-stu-id="78aef-178">By default, \<ApplianceName\> comes from the host name.</span></span> <span data-ttu-id="78aef-179">\<\> \< IP-адрес сервера-посредника и IP-адрес сервера-посредника, \> определенные в ini-файле конфигурации.</span><span class="sxs-lookup"><span data-stu-id="78aef-179">\<Mediation Server FQDN\> and \<Mediation Server IP Address\> defined in configuration ini file.</span></span>
    
    <span data-ttu-id="78aef-180">Например, при использовании (выступает имя устройства = Мисервернев, имя сервера-посредника FQDN = MS. contoso. com, IP-адрес сервера-посредника = 10.10.10.10) для регистрации на сайте SiteName = личного сайта, но при наличии зарегистрированного устройства (выступает имя устройства = MyServer, имя сервера-посредника = $. contoso. com, IP-адрес сервера-посредника — 10.10.10.10) возникает конфликт.</span><span class="sxs-lookup"><span data-stu-id="78aef-180">For example, using (ApplianceName= MyserverNew, Mediation Server FQDN=ms.contoso.com, Mediation Server IP Address=10.10.10.10) to register to SiteName=MySite, but if there is a registered appliance (ApplianceName= Myserver, Mediation Server FQDN=ms.contoso.com, Mediation Server IP Address=10.10.10.10), you will have the conflict.</span></span>
    
    <span data-ttu-id="78aef-181">Для начала проверьте файл CloudConnector. ini в разделе Апплианцерут Directory.</span><span class="sxs-lookup"><span data-stu-id="78aef-181">First, please check your CloudConnector.ini file in ApplianceRoot directory section.</span></span> <span data-ttu-id="78aef-182">\<В файле будут получены \> \< значения полного доменного имени \> и IP-адреса сервера-посредника сервера-посредника и сервера \< -посредника \> .</span><span class="sxs-lookup"><span data-stu-id="78aef-182">You will get \<SiteName\>, \<Mediation Server FQDN\> and \<Mediation Server IP Address\> values in the file.</span></span> <span data-ttu-id="78aef-183">\<Выступает имя устройства \> это имя сервера узла.</span><span class="sxs-lookup"><span data-stu-id="78aef-183">\<ApplianceName\> is your host server name.</span></span>
    
    <span data-ttu-id="78aef-184">Во-вторых, запустите удаленную консоль PowerShell клиента, используя учетные данные администратора клиента Skype для бизнеса, а затем выполните следующий командлет, чтобы проверить зарегистрированные устройства.</span><span class="sxs-lookup"><span data-stu-id="78aef-184">Second, Launch Tenant Remote PowerShell using your Skype for Business tenant admin credentials, then run the following cmdlet to check the registered appliance(s).</span></span>
    
  ```powershell
  Get-CsHybridPSTNAppliance
  ```

    <span data-ttu-id="78aef-185">Определив конфликты, можно либо обновить файл CloudConnector. ini, указав сведения, соответствующие зарегистрированному устройству, либо отменить регистрацию существующего устройства для устранения конфликтов.</span><span class="sxs-lookup"><span data-stu-id="78aef-185">After identifying any conflicts, you can either update your CloudConnector.ini file with information that matches the registered appliance, or unregister the existing appliance to resolve the conflicts.</span></span>
    
  ```powershell
  Unregister-CsHybridPSTNAppliance -Force
  ```

    
- <span data-ttu-id="78aef-186">**Ошибка: командлет Get-CcRunningVersion возвращает пустое значение, если на узле выполняется развернутое устройство.**</span><span class="sxs-lookup"><span data-stu-id="78aef-186">**Issue: The Get-CcRunningVersion cmdlet returns an empty value if there is a deployed appliance running on the host.**</span></span>
    
  <span data-ttu-id="78aef-187">**Решение:** Это может происходить при обновлении с 1.3.4 или 1.3.8 до 1.4.1.</span><span class="sxs-lookup"><span data-stu-id="78aef-187">**Resolution:** This can happen when you upgrade from 1.3.4 or 1.3.8 to 1.4.1.</span></span> <span data-ttu-id="78aef-188">После установки версии 1.4.1 с помощью MSI необходимо выполнить `Register-CcAppliance` перед запуском любого другого командлета.</span><span class="sxs-lookup"><span data-stu-id="78aef-188">After you install version 1.4.1 with the .msi, you must run `Register-CcAppliance` before you run any other cmdlet.</span></span> <span data-ttu-id="78aef-189">`Register-CcAppliance`переносит файл Module. ini из%Усерпрофиле%\клаудконнектор в%Програмдата%\клаудконнектор.</span><span class="sxs-lookup"><span data-stu-id="78aef-189">`Register-CcAppliance` will migrate the module.ini file from %UserProfile%\CloudConnector to %ProgramData%\CloudConnector.</span></span> <span data-ttu-id="78aef-190">Если вы пропустили его, в папке%Програмдата%\клаудконнектор будет создан новый модуль. ini и заменяются сведения о версии, используемой для 1.3.4 или 1.3.8.</span><span class="sxs-lookup"><span data-stu-id="78aef-190">If you missed it, a new module.ini will be created in %ProgramData%\CloudConnector folder and replace the running/backup version information for 1.3.4 or 1.3.8.</span></span>
    
  <span data-ttu-id="78aef-191">Сравните файлы Module. ini в папке%Усерпрофиле%\клаудконнектор и%Програмдата%\клаудконнектор.</span><span class="sxs-lookup"><span data-stu-id="78aef-191">Compare module.ini files in %UserProfile%\CloudConnector and %ProgramData%\CloudConnector folder.</span></span> <span data-ttu-id="78aef-192">При наличии различий удалите файл Module. ini в%Програмдата%\клаудконнектор и повторите операцию `Register-CcAppliance` .</span><span class="sxs-lookup"><span data-stu-id="78aef-192">If there are differences, delete the module.ini file in %ProgramData%\CloudConnector and rerun  `Register-CcAppliance`.</span></span> <span data-ttu-id="78aef-193">Вы также можете изменить файл вручную, дополнив его на правильную версию и резервную копию.</span><span class="sxs-lookup"><span data-stu-id="78aef-193">You could also modify the file manually to the correct running and backup version.</span></span>
    
- <span data-ttu-id="78aef-194">**Проблема: после выполнения командлета Switch-CcVersion для переключения на старую версию, которая отличается от текущей версии сценария, для этой старой версии нет поддержки высокого уровня доступности.**</span><span class="sxs-lookup"><span data-stu-id="78aef-194">**Issue: After you run the Switch-CcVersion cmdlet to switch to an old version which is different from current script version, there is no High Availability support for this old version.**</span></span>
    
    <span data-ttu-id="78aef-195">**Решение:** Например, вы выполнили обновление с 1.4.1 на 1.4.2.</span><span class="sxs-lookup"><span data-stu-id="78aef-195">**Resolution:** For example, you have upgraded from 1.4.1 to 1.4.2.</span></span> <span data-ttu-id="78aef-196">Текущая версия скрипта, которая может быть определена при запуске `Get-CcVersion` , и используемая версия, которую можно определить с помощью команды `Get-CcRunningVersion` 1.4.2.</span><span class="sxs-lookup"><span data-stu-id="78aef-196">Your current script version, which can be determined by running `Get-CcVersion`, and your running version, which can be determined by running  `Get-CcRunningVersion` are both 1.4.2.</span></span> <span data-ttu-id="78aef-197">В настоящее время, если вы перейдете на `Switch-CcVersion` 1.4.1, то для этой старой версии будет отсутствовать поддержка высокого уровня доступности.</span><span class="sxs-lookup"><span data-stu-id="78aef-197">At this time, if you run `Switch-CcVersion` to switch the running version back to 1.4.1, then there will be no High Availability support for this old version.</span></span>
    
    <span data-ttu-id="78aef-198">Чтобы получить поддержку высокого уровня доступности, переключитесь обратно в 1.4.2, поэтому действующая версия и версия сценария совпадают.</span><span class="sxs-lookup"><span data-stu-id="78aef-198">To get full High Availability support, please switch back to 1.4.2, so the running version and script version are the same.</span></span> <span data-ttu-id="78aef-199">Если у вас возникли проблемы с развертыванием 1.4.2, удалите и переустановите его как можно скорее.</span><span class="sxs-lookup"><span data-stu-id="78aef-199">If you are experiencing problems with your 1.4.2 deployment, please uninstall and reinstall it as soon as possible.</span></span>
    
- <span data-ttu-id="78aef-200">**Причина: сертификаты центра сертификации или внутренние сертификаты, выданные центральному хранилищу управления, серверу-посреднику и пограничному серверу, истекает из истечения срока действия или скомпрометированы.**</span><span class="sxs-lookup"><span data-stu-id="78aef-200">**Issue: Certificate authority certificates or internal certificates issued to Central Management Store, Mediation Server, and Edge Server are near expiration or are compromised.**</span></span>
    
    <span data-ttu-id="78aef-201">**Решение:** Сертификаты центра сертификации Skype для бизнеса действительны в течение пяти лет.</span><span class="sxs-lookup"><span data-stu-id="78aef-201">**Resolution:** Skype for Business certification authority certificates are valid for five years.</span></span> <span data-ttu-id="78aef-202">Внутренние сертификаты, выданные для центрального хранилища управления, сервера-посредника и пограничного сервера, действительны в течение двух лет.</span><span class="sxs-lookup"><span data-stu-id="78aef-202">Internal certificates issued to the Central Management Store, Mediation Server, and Edge Server are valid for two years.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="78aef-203">В Cloud Connector версии 2,0 и более поздних командлеты Update – CcServerCertificate изменились на Update — CcServerCertificate, а командлет продления — CcCACertificate изменился на Update CcCACertificate.</span><span class="sxs-lookup"><span data-stu-id="78aef-203">In Cloud Connector version 2.0 and later, the Renew-CcServerCertificate cmdlet has changed to Update-CcServerCertificate and the Renew-CcCACertificate cmdlet has changed to Update-CcCACertificate.</span></span> 
  
    <span data-ttu-id="78aef-204">Если срок действия внутренних сертификатов, выданных серверу центрального хранилища управления, серверу-посреднику и пограничному серверу, приближается к истечению срока действия или скомпрометирован, выполните командлет Update-CcServerCertificate или Update-CcServerCertificate для продления сертификатов.</span><span class="sxs-lookup"><span data-stu-id="78aef-204">If internal certificates issued to the Central Management Store, Mediation Server, and Edge Server are near expiration or compromised, run the Renew-CcServerCertificate or Update-CcServerCertificate cmdlet to renew your certificates.</span></span>
    
    <span data-ttu-id="78aef-205">Если срок действия сертификатов центра сертификации истек, выполните командлет Update – CcCACertificate или Update – CcCACertificate, чтобы обновить сертификаты.</span><span class="sxs-lookup"><span data-stu-id="78aef-205">If certification authority certificates are near expiration, run the Renew-CcCACertificate or Update-CcCACertificate cmdlet to renew your certificates.</span></span>
    
    <span data-ttu-id="78aef-206">**Если сертификаты центра сертификации скомпрометированы и на сайте имеется только одно устройство,** выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="78aef-206">**If certification authority certificates are compromised and there is only one appliance in the site,** perform the following steps:</span></span>
    
1. <span data-ttu-id="78aef-207">Выполните командлет Enter – CcUpdate, чтобы очистить службы и перевести устройство в режим обслуживания.</span><span class="sxs-lookup"><span data-stu-id="78aef-207">Run the Enter-CcUpdate cmdlet to drain services and put the appliance in maintenance mode.</span></span>
   
   ```powershell
   Enter-CcUpdate
   ```
   
2. <span data-ttu-id="78aef-208">Выполните следующие командлеты, чтобы сбросить и создать новые сертификаты центра сертификации и все внутренние сертификаты серверов:</span><span class="sxs-lookup"><span data-stu-id="78aef-208">Run the following cmdlets to reset and create new certification authority certificates and all internal server certificates:</span></span>
    
    <span data-ttu-id="78aef-209">Для выпусков Cloud Connector до 2,0:</span><span class="sxs-lookup"><span data-stu-id="78aef-209">For Cloud Connector releases before 2.0:</span></span>
    
    ```powershell
    Reset-CcCACertificate 
    Renew-CcServerCertificate 
    Remove-CcLegacyServerCertificate 
    ```

    <span data-ttu-id="78aef-210">В случае выпуска Cloud Connector 2,0 и более поздних версий:</span><span class="sxs-lookup"><span data-stu-id="78aef-210">Or for Cloud Connector release 2.0 and later:</span></span>
    
    ```powershell
    Reset-CcCACertificate 
    Update-CcServerCertificate 
    Remove-CcLegacyServerCertificate 
    ```
    
3. <span data-ttu-id="78aef-211">Если между шлюзом и сервером-посредником используется протокол TLS, выполните командлет Export-CcRootCertificate на устройстве, а затем установите экспортированный сертификат на шлюзы PSTN.</span><span class="sxs-lookup"><span data-stu-id="78aef-211">If TLS is used between the gateway and the Mediation Server, run the Export-CcRootCertificate cmdlet from the appliance, and then install the exported certificate to your PSTN gateways.</span></span> <span data-ttu-id="78aef-212">Кроме того, может потребоваться повторная выдача сертификата на шлюзе.</span><span class="sxs-lookup"><span data-stu-id="78aef-212">You may also be required to re-issue the certificate on your gateway.</span></span>

   ```powershell
   Export-CcRootCertificate
   ```

4. <span data-ttu-id="78aef-213">Выполните командлет Exit – CcUpdate, чтобы запустить службы и выйти из режима обслуживания.</span><span class="sxs-lookup"><span data-stu-id="78aef-213">Run the Exit-CcUpdate cmdlet to start services and exit maintenance mode.</span></span>

   ```powershell
   Exit-CcUpdate
   ```


    <span data-ttu-id="78aef-214">**Если сертификаты центра сертификации скомпрометированы и на сайте имеется несколько устройств,** выполните следующие действия на каждом устройстве на сайте.</span><span class="sxs-lookup"><span data-stu-id="78aef-214">**If certification authority certificates are compromised and there are multiple appliances in the site,** perform the following sequential steps on each appliance in the site.</span></span>
    
    <span data-ttu-id="78aef-215">Корпорация Майкрософт рекомендует выполнять эти действия в непиковое время использования.</span><span class="sxs-lookup"><span data-stu-id="78aef-215">Microsoft recommends that you perform these steps during non-peak usage times.</span></span>
    
1. <span data-ttu-id="78aef-216">На первом устройстве запустите командлет Remove – CcCertificationAuthorityFile, чтобы очистить файлы резервных копий ЦС в \< \> каталоге ситерут</span><span class="sxs-lookup"><span data-stu-id="78aef-216">On the first appliance, run the Remove-CcCertificationAuthorityFile cmdlet to clean up the CA backup files in the \<SiteRoot\> directory.</span></span>

     ```powershell
     Remove-CcCertificationAuthorityFile
     ```
    
2. <span data-ttu-id="78aef-217">Выполните командлет Enter – CcUpdate, чтобы сток служб и перевести каждое устройство в режим обслуживания.</span><span class="sxs-lookup"><span data-stu-id="78aef-217">Run the Enter-CcUpdate cmdlet to drain services and put each appliance in maintenance mode.</span></span>

     ```powershell
     Enter-CcUpdate
     ```
    
3. <span data-ttu-id="78aef-218">На первом устройстве выполните следующие командлеты, чтобы сбросить и создать новые сертификаты центра сертификации и все внутренние сертификаты серверов:</span><span class="sxs-lookup"><span data-stu-id="78aef-218">On the first appliance, run the following cmdlets to reset and create new certification authority certificates and all internal server certificates:</span></span>
    
     <span data-ttu-id="78aef-219">Для выпусков Cloud Connector до 2,0:</span><span class="sxs-lookup"><span data-stu-id="78aef-219">For Cloud Connector releases before 2.0:</span></span>
    
     ```powershell
     Reset-CcCACertificate
     Renew-CcServerCertificate
     Remove-CcLegacyServerCertificate 
     ```

     <span data-ttu-id="78aef-220">В случае выпуска Cloud Connector 2,0 и более поздних версий:</span><span class="sxs-lookup"><span data-stu-id="78aef-220">Or for Cloud Connector release 2.0 and later:</span></span>
    
     ```powershell
     Reset-CcCACertificate
     Update-CcServerCertificate
     Remove-CcLegacyServerCertificate 
     ```

4. <span data-ttu-id="78aef-221">На первом устройстве выполните следующий командлет, чтобы создать резервную копию файлов ЦС в \< \> папке ситерут</span><span class="sxs-lookup"><span data-stu-id="78aef-221">On the first appliance, run the following cmdlet to back up the CA files to the \<SiteRoot\> folder.</span></span>
    
     ```powershell
     Backup-CcCertificationAuthority
     ```
   
5. <span data-ttu-id="78aef-222">На любом другом устройстве на том же сайте выполните следующие команды для использования файлов резервных копий ЦС, чтобы все устройства использовали один корневой сертификат, а затем запрашивают новые сертификаты.</span><span class="sxs-lookup"><span data-stu-id="78aef-222">On all other appliance's in the same site, run the following commands to consume the CA backup files, so that the appliances all use the same root certificate, and then request new certificates.</span></span> 
   
     ```powershell
     Reset-CcCACertificate
     Update-CcServerCertificate
     Remove-CcLegacyServerCertificate 
     ```
     
6. <span data-ttu-id="78aef-223">Если между шлюзом и сервером-посредником используется протокол TLS, выполните командлет Export-CcRootCertificate на любом устройстве на сайте, а затем установите экспортированный сертификат на шлюзы PSTN.</span><span class="sxs-lookup"><span data-stu-id="78aef-223">If TLS is used between the gateway and the Mediation Server, run the Export-CcRootCertificate cmdlet from any appliance in the site, and then install the exported certificate to your PSTN gateways.</span></span> <span data-ttu-id="78aef-224">Кроме того, может потребоваться повторная выдача сертификата на шлюзе.</span><span class="sxs-lookup"><span data-stu-id="78aef-224">You may also be required to re-issue the certificate on your gateway.</span></span>
  
     ```powershell
     Export-CcRootCertificate
     ```
     
7. <span data-ttu-id="78aef-225">Выполните командлет Exit – CcUpdate, чтобы запустить службы и выйти из режима обслуживания.</span><span class="sxs-lookup"><span data-stu-id="78aef-225">Run the Exit-CcUpdate cmdlet to start services and exit maintenance mode.</span></span> 

     ```powershell
     Exit-CcUpdate
     ```
    
    
- <span data-ttu-id="78aef-226">**Причина: в журнале службы управления Cloud Connector отображается следующее сообщение об ошибке: "C:\Program Files\Skype for Business Cloud Connector Едитион\манажементсервице\кцеманажементсервице.лог": CceService Error: 0: непредвиденное исключение при отправке отчета о состоянии в Online: System. Management. Automation. Кмдлетинвокатионексцептион: сбой входа для \< глобального администратора клиента \> . Создайте новый объект учетных данных, убедившись, что вы использовали правильные имя пользователя и пароль. ---\>**</span><span class="sxs-lookup"><span data-stu-id="78aef-226">**Issue: You receive the following error message in the Cloud Connector Management Service Log, "C:\Program Files\Skype for Business Cloud Connector Edition\ManagementService\CceManagementService.log": CceService Error: 0 : Unexpected exception when reporting status to online: System.Management.Automation.CmdletInvocationException: Logon failed for the user \<Global Tenant Admin\>. Please create a new credential object, making sure that you have used the correct user name and password. ---\>**</span></span>
    
    <span data-ttu-id="78aef-227">**Решение:** Учетные данные глобального администратора клиента Microsoft 365 или Office 365 были изменены с момента регистрации устройства Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="78aef-227">**Resolution:** The Microsoft 365 or Office 365 global tenant admin credentials have been changed since the Cloud Connector appliance was registered.</span></span> <span data-ttu-id="78aef-228">Чтобы обновить локально хранимые учетные данные на устройстве Cloud Connector, выполните следующую команду в консоли PowerShell с правами администратора на хостном устройстве:</span><span class="sxs-lookup"><span data-stu-id="78aef-228">To update the locally stored credentials on the Cloud Connector appliance, run the following from Administrator PowerShell on the host appliance:</span></span>
    
  ```powershell
  Set-CcCredential -AccountType TenantAdmin
  ```

- <span data-ttu-id="78aef-229">**Вопрос: после изменения пароля для учетной записи сервера узла, используемой для развертывания, отображается следующее сообщение об ошибке: "ConvertTo-SecureString: ключ не является допустимым для использования в указанном состоянии". "в%ProgramFiles%\Skype для Business Cloud Connector Едитион\манажементсервице\кцеманажементсервице.лог или при запуске командлета Get-CcCredential.**</span><span class="sxs-lookup"><span data-stu-id="78aef-229">**Issue: After you change the password for the host server account you used for the deployment, you receive the following error message: "ConvertTo-SecureString : Key not valid for use in specified state." in %ProgramFiles%\Skype for Business Cloud Connector Edition\ManagementService\CceManagementService.log or while running the Get-CcCredential cmdlet.**</span></span>
    
    <span data-ttu-id="78aef-230">**Решение:** Все учетные данные Cloud Connector хранятся в следующем файле: "%SystemDrive%\Programdata\Cloudconnector\credentials. \< CurrentUser \> . XML ".</span><span class="sxs-lookup"><span data-stu-id="78aef-230">**Resolution:** All Cloud Connector credentials are stored in the following file: "%SystemDrive%\Programdata\Cloudconnector\credentials.\<CurrentUser\>.xml".</span></span> <span data-ttu-id="78aef-231">При изменении пароля на сервере узла необходимо обновить локально хранимые учетные данные.</span><span class="sxs-lookup"><span data-stu-id="78aef-231">When the password on the host server changes, you will need to update the locally stored credentials.</span></span>
    
    <span data-ttu-id="78aef-232">**Если вы используете Cloud Connector версии 1.4.2,** повторно создайте все пароли Cloud Connector, выполнив следующие действия:</span><span class="sxs-lookup"><span data-stu-id="78aef-232">**If you are running Cloud Connector version 1.4.2,** regenerate all Cloud Connector passwords by following these steps:</span></span>
    
  1. <span data-ttu-id="78aef-233">Перезапустите сервер узла.</span><span class="sxs-lookup"><span data-stu-id="78aef-233">Restart the host server.</span></span>
    
  2. <span data-ttu-id="78aef-234">Удалите следующий файл: "%SystemDrive%\Programdata\Cloudconnector\credentials. \< CurrentUser \> . XML ".</span><span class="sxs-lookup"><span data-stu-id="78aef-234">Delete the following file: "%SystemDrive%\Programdata\Cloudconnector\credentials.\<CurrentUser\>.xml".</span></span>
    
  3. <span data-ttu-id="78aef-235">Запустите консоль PowerShell от имени администратора, а затем выполните команду "Register – CcAppliance — Local", чтобы повторно ввести пароли, указанные в описании.</span><span class="sxs-lookup"><span data-stu-id="78aef-235">Launch a PowerShell console as administrator, and then run "Register-CcAppliance -Local" to re-enter the passwords following the description.</span></span> <span data-ttu-id="78aef-236">Введите те же пароли, которые были введены ранее для развертывания Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="78aef-236">Enter the same passwords you entered before for the Cloud Connector deployment.</span></span>
    
     <span data-ttu-id="78aef-237">**Если вы используете Cloud Connector версии 2,0 или более поздней,** повторно создайте все пароли Cloud Connector, выполнив следующие действия:</span><span class="sxs-lookup"><span data-stu-id="78aef-237">**If you are running Cloud Connector version 2.0 or later,** regenerate all Cloud Connector passwords by following these steps:</span></span>
    
  4. <span data-ttu-id="78aef-238">Перезапустите сервер узла.</span><span class="sxs-lookup"><span data-stu-id="78aef-238">Restart the host server.</span></span>
    
  5. <span data-ttu-id="78aef-239">Удалите следующий файл: "%SystemDrive%\Programdata\Cloudconnector\credentials. \< CurrentUser \> . XML ".</span><span class="sxs-lookup"><span data-stu-id="78aef-239">Delete the following file: "%SystemDrive%\Programdata\Cloudconnector\credentials.\<CurrentUser\>.xml" .</span></span>
    
  6. <span data-ttu-id="78aef-240">Запустите консоль PowerShell от имени администратора, а затем выполните команду "Register – CcAppliance — Local", чтобы повторно ввести пароли, указанные в описании.</span><span class="sxs-lookup"><span data-stu-id="78aef-240">Launch a PowerShell console as administrator, and then run "Register-CcAppliance -Local" to re-enter the passwords following the description.</span></span> 
    
     <span data-ttu-id="78aef-241">Если файл кэшированного пароля был создан с помощью 1.4.2 Cloud Connector версии, при появлении соответствующего запроса используйте пароль VMAdmin для пароля CceService.</span><span class="sxs-lookup"><span data-stu-id="78aef-241">If the cached password file was generated with Cloud Connector version 1.4.2, use the VMAdmin password for the CceService password when prompted.</span></span> <span data-ttu-id="78aef-242">Введите тот же пароль, который вы ввели перед развертыванием Cloud Connector для всех остальных учетных записей.</span><span class="sxs-lookup"><span data-stu-id="78aef-242">Enter the same password you entered before for the Cloud Connector deployment for all other accounts.</span></span>
    
     <span data-ttu-id="78aef-243">Если файл кэшированного пароля был создан с помощью Cloud Connector версии 1.4.2, а пароли DomainAdmin и VMAdmin отличаются, необходимо выполнить следующие действия:</span><span class="sxs-lookup"><span data-stu-id="78aef-243">If the cached password file was generated with Cloud Connector version 1.4.2 and the DomainAdmin and VMAdmin passwords are different, you must perform the following steps:</span></span>
    
  7. <span data-ttu-id="78aef-244">Выполните командлет Set – CcCredential – AccountType DomainAdmin, как показано ниже.</span><span class="sxs-lookup"><span data-stu-id="78aef-244">Run Set-CcCredential -AccountType DomainAdmin as follows:</span></span>
    
  8. <span data-ttu-id="78aef-245">При запросе учетных данных старой учетной записи введите учетные данные, которые использовались для пароля CceService.</span><span class="sxs-lookup"><span data-stu-id="78aef-245">When prompted for the old account credential, enter the credential you used for the CceService password.</span></span>
    
  9. <span data-ttu-id="78aef-246">При запросе учетных данных новой учетной записи введите пароль для пароля DomainAdmin, который вы использовали ранее.</span><span class="sxs-lookup"><span data-stu-id="78aef-246">When prompted for the new account credential, enter the password for the DomainAdmin password you used before.</span></span>
    
     <span data-ttu-id="78aef-247">Если файл кэшированного пароля был создан с помощью Cloud Connector версии 2,0 или более поздней версии, по умолчанию VmAdmin и DomainAdmin используют тот же пароль, что и в CceService.</span><span class="sxs-lookup"><span data-stu-id="78aef-247">If the cached password file was generated with Cloud Connector version 2.0 or later, by default, VmAdmin and DomainAdmin use the same password as CceService.</span></span> <span data-ttu-id="78aef-248">Если вы изменили пароли DomainAdmin и VMAdmin, необходимо выполнить следующие действия:</span><span class="sxs-lookup"><span data-stu-id="78aef-248">If you changed the DomainAdmin and VMAdmin passwords, you must perform the following steps:</span></span>
    
  10. <span data-ttu-id="78aef-249">Выполните командлет Set – CcCredential – AccountType DomainAdmin, как показано ниже.</span><span class="sxs-lookup"><span data-stu-id="78aef-249">Run Set-CcCredential -AccountType DomainAdmin as follows:</span></span>
    
       1. <span data-ttu-id="78aef-250">При запросе учетных данных старой учетной записи введите учетные данные, которые использовались для пароля CceService</span><span class="sxs-lookup"><span data-stu-id="78aef-250">When prompted for the old account credential, enter the credential you used for the CceService password</span></span>
    
       2. <span data-ttu-id="78aef-251">При запросе учетных данных новой учетной записи введите пароль для пароля DomainAdmin, который вы использовали ранее.</span><span class="sxs-lookup"><span data-stu-id="78aef-251">When prompted for the new account credential, enter the password for the DomainAdmin password you used before.</span></span>
    
  11. <span data-ttu-id="78aef-252">Выполните командлет Set – CcCredential – AccountType VmAdmin, как показано ниже.</span><span class="sxs-lookup"><span data-stu-id="78aef-252">Run Set-CcCredential -AccountType VmAdmin as follows:</span></span>
    
       1. <span data-ttu-id="78aef-253">При запросе учетных данных старой учетной записи введите учетные данные, которые использовались для пароля CceService</span><span class="sxs-lookup"><span data-stu-id="78aef-253">When prompted for the old account credential, enter the credential you used for the CceService password</span></span>
    
       2. <span data-ttu-id="78aef-254">При запросе учетных данных новой учетной записи введите пароль для пароля VmAdmin, который вы использовали ранее.</span><span class="sxs-lookup"><span data-stu-id="78aef-254">When prompted for the new account credential, enter the password for the VmAdmin password you used before.</span></span> 
    
- <span data-ttu-id="78aef-255">**Проблема: с помощью Cloud Connector версии 2,1 и более поздних версий при запуске командлета Register – CcAppliance или других командлетов на устройстве отображается сообщение об ошибке: "для каждого объекта: не удается найти свойство ' Common ' для этого объекта. Убедитесь, что свойство существует. В папке C:\Program Files\WindowsPowerShell\Modules\CloudConnector\Internal\MtHostCommon.ps1:681 char: 14 "**</span><span class="sxs-lookup"><span data-stu-id="78aef-255">**Issue: With Cloud Connector version 2.1 and later, when running Register-CcAppliance or other cmdlets on the appliance, you receive an error message such as: "For Each-Object : The property 'Common' cannot be found on this object. Verify that the property exists. At C:\Program Files\WindowsPowerShell\Modules\CloudConnector\Internal\MtHostCommon.ps1:681 char:14"**</span></span>
    
    <span data-ttu-id="78aef-256">**Решение:** Для Cloud Connector 2,1 и более поздних версий требуется платформа .NET Framework 4.6.1 или более поздняя версия.</span><span class="sxs-lookup"><span data-stu-id="78aef-256">**Resolution:** Cloud Connector 2.1 and later requires .NET Framework 4.6.1 or later.</span></span> <span data-ttu-id="78aef-257">Обновите .NET Framework на устройстве с помощью 4.6.1 или более поздней версии, а затем снова запустите командлеты.</span><span class="sxs-lookup"><span data-stu-id="78aef-257">Please update .NET Framework on the appliance to version 4.6.1 or later and run the cmdlet(s) again.</span></span>

- <span data-ttu-id="78aef-258">**Вопрос: с помощью Cloud Connector Edition 2,1 при запуске Install-CcAppliance появляется следующее сообщение об ошибке: "не удалось установить новый экземпляр, ошибка: невозможно задать" состояние ", так как только строки можно использовать в качестве значений для задания свойств XmlNode"**</span><span class="sxs-lookup"><span data-stu-id="78aef-258">**Issue: With Cloud Connector Edition 2.1, when running Install-CcAppliance, you receive an error message such as: "Failed to install new instance with error: Cannot set "State" because only strings can be used as values to set XmlNode properties"**</span></span>

   <span data-ttu-id="78aef-259">**Решение:** В Cloudconnector. ini в разделе [Common] добавьте конфигурацию "State", как указано ниже: CountryCode = US штат = Вашингтон город = Redmond</span><span class="sxs-lookup"><span data-stu-id="78aef-259">**Resolution:** In Cloudconnector.ini, under the [Common] section, please add the “State” config as below:  CountryCode=US  State=WA  City=Redmond</span></span>

   <span data-ttu-id="78aef-260">Строка State не является обязательной для значения, но строка "State" не может быть удалена из файла Cloudconnector. ini.</span><span class="sxs-lookup"><span data-stu-id="78aef-260">It is not mandatory for the "State" line to have value, however the "State" line cannot be removed from the Cloudconnector.ini file.</span></span>

- <span data-ttu-id="78aef-261">**Ошибка: получено следующее сообщение об ошибке: "Dismount — Виндовсимаже: Dismount – Виндовсимаже Failed. Код ошибки = 0xc1550115 "при установке или обновлении Cloud Connector Edition.**</span><span class="sxs-lookup"><span data-stu-id="78aef-261">**Issue: You receive the following error message "Dismount-WindowsImage : Dismount-WindowsImage failed. Error code = 0xc1550115" when installing or upgrading Cloud Connector Edition.**</span></span>
    
    <span data-ttu-id="78aef-262">**Решение:** Запустите консоль PowerShell от имени администратора, запустите "DISM-Cleanup-WIM".</span><span class="sxs-lookup"><span data-stu-id="78aef-262">**Resolution:** Launch a PowerShell console as administrator, run "DISM -Cleanup-Wim'".</span></span> <span data-ttu-id="78aef-263">При этом будут очищены все невыполненные изображения.</span><span class="sxs-lookup"><span data-stu-id="78aef-263">This will clean up all troubled images.</span></span> <span data-ttu-id="78aef-264">Повторно запустите командлет Install – CcAppliance или дождитесь автоматического обновления BITS.</span><span class="sxs-lookup"><span data-stu-id="78aef-264">Run Install-CcAppliance again or wait for the bits to automatically upgrade.</span></span>
    
- <span data-ttu-id="78aef-265">**Ошибка: не удается развернуть первое устройство Cloud Connector в среде высокой доступности**</span><span class="sxs-lookup"><span data-stu-id="78aef-265">**Issue: Deployment of the first Cloud Connector appliance in an HA environment fails**</span></span>
    
    <span data-ttu-id="78aef-266">**Решение:** Действия, которые необходимо выполнить, зависят от причины сбоя развертывания:</span><span class="sxs-lookup"><span data-stu-id="78aef-266">**Resolution:** The steps you take depend on the reason the deployment failed:</span></span>
    
  - <span data-ttu-id="78aef-267">Если первое устройство Cloud Connector завершается с ошибкой и вы не можете определить причину сбоя, необходимо установить устройство еще раз до успешного развертывания, а затем установить другие устройства.</span><span class="sxs-lookup"><span data-stu-id="78aef-267">If the first Cloud Connector appliance fails and you cannot determine the reason for the failure, you must install the appliance again until the deployment is successful, and then install the other appliances.</span></span>
    
  - <span data-ttu-id="78aef-268">Если первое устройство Cloud Connector потерпит незначительную проблему, например проблему с внешним сертификатом, вы можете устранить проблему без повторной установки устройства.</span><span class="sxs-lookup"><span data-stu-id="78aef-268">If the first Cloud Connector appliance fails with a minor issue, such as an external certificate issue, you might be able to fix the problem without re-installing the appliance.</span></span> <span data-ttu-id="78aef-269">Затем вы можете использовать удаленную оболочку PowerShell клиента, чтобы пометить развертывание как успешное, как показано ниже.</span><span class="sxs-lookup"><span data-stu-id="78aef-269">You can then use tenant remote PowerShell to mark the deployment as successful as follows.</span></span> <span data-ttu-id="78aef-270">(Вы также можете выполнить следующие действия, если первое развертывание прошло успешно, но по какой-либо причине облачному соединителю не удалось сообщить о развертывании как успешное.)</span><span class="sxs-lookup"><span data-stu-id="78aef-270">(You can also use the following steps if the first deployment was successful, but, for some reason, Cloud Connector fails to report the deployment as a success.)</span></span>
    
  - <span data-ttu-id="78aef-271">Чтобы получить идентификатор (GUID) первого устройства Cloud Connector, выполните командлет Get-Кшибридпстнапплианце.</span><span class="sxs-lookup"><span data-stu-id="78aef-271">To get the Identity (GUID) of the first Cloud Connector appliance, run the Get-CsHybridPSTNAppliance cmdlet.</span></span>
    
  - <span data-ttu-id="78aef-272">Чтобы пометить устройство как успешно развернутое, выполните командлет Set – Кскцеапплианцедеплойментстатус следующим образом:</span><span class="sxs-lookup"><span data-stu-id="78aef-272">To mark the appliance as successfully deployed, run the Set-CsCceApplianceDeploymentStatus as follows:</span></span>
    
  ```powershell
  Set-CsCceApplianceDeploymentStatus -Identity <Appliance Identity GUID> -Action Deploy -Status Finished
  ```

- <span data-ttu-id="78aef-273">**Вопрос: необходимо проверить наличие и установить обновления Windows вручную на сервере узла или виртуальных машинах.**</span><span class="sxs-lookup"><span data-stu-id="78aef-273">**Issue: You need to check for and install Windows updates manually on the host server or virtual machines.**</span></span>
    
   <span data-ttu-id="78aef-274">**Решение:** Мы рекомендуем использовать преимущества автоматических обновлений ОС, предоставляемых Skype для бизнеса Cloud Connector Edition.</span><span class="sxs-lookup"><span data-stu-id="78aef-274">**Resolution:** We recommend that you take advantage of automated OS updates provided by Skype for Business Cloud Connector Edition.</span></span> <span data-ttu-id="78aef-275">После регистрации устройства для управления через Интернет и включения автоматического обновления ОС сервер узла и виртуальные машины будут автоматически проверять и устанавливать обновления Windows в соответствии с параметрами окна "обновление операционной системы".</span><span class="sxs-lookup"><span data-stu-id="78aef-275">After an appliance is registered for online management and auto OS update is enabled, the host server and virtual machines will check and install Windows Updates automatically according to the OS update time window settings.</span></span>
    
   <span data-ttu-id="78aef-276">Если вам нужно проверить и установить обновления Windows вручную, выполните действия, описанные в этом разделе, которые относятся к типу развертывания.</span><span class="sxs-lookup"><span data-stu-id="78aef-276">If you need to check for and install Windows Updates manually, follow the steps in this section that apply to your type of deployment.</span></span> <span data-ttu-id="78aef-277">Необходимо запланировать обновление как сервера узла, так и виртуальных машин, работающих на нем, чтобы минимизировать время, необходимое для обновления.</span><span class="sxs-lookup"><span data-stu-id="78aef-277">You should plan on updating both the host server and the virtual machines running on it at the same time to minimize the amount of down time necessary for the updates.</span></span>
    
   <span data-ttu-id="78aef-278">При желании вы можете использовать сервер служб Windows Server Update Services (WSUS) для предоставления обновлений для серверов Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="78aef-278">If you prefer, you can use a Windows Server Update Services (WSUS) server to provide updates to Cloud Connector servers.</span></span> <span data-ttu-id="78aef-279">Необходимо убедиться, что обновление Windows **не** устанавливается автоматически.</span><span class="sxs-lookup"><span data-stu-id="78aef-279">Just be sure to configure the Windows Update to **not** install automatically.</span></span>
    
   <span data-ttu-id="78aef-280">Сведения о том, как вручную обновить развертывание Cloud Connector, можно найти в следующем разделе.</span><span class="sxs-lookup"><span data-stu-id="78aef-280">For information about how to manually update your Cloud Connector deployment, see the following section.</span></span>
    
- <span data-ttu-id="78aef-281">**Вопрос: при обновлении Cloud Connector до новой сборки командлеты Cloud Connector не обновляются.**</span><span class="sxs-lookup"><span data-stu-id="78aef-281">**Issue: When Cloud Connector updates to a new build, Cloud Connector cmdlets are not updated.**</span></span> <span data-ttu-id="78aef-282">Это может произойти, если окно PowerShell остается открытым при выполнении автоматического обновления.</span><span class="sxs-lookup"><span data-stu-id="78aef-282">This sometimes happens if a PowerShell window is left open when automatic update occurs.</span></span>
    
  <span data-ttu-id="78aef-283">**Решение:** Для загрузки обновленных командлетов можно выполнить одно из следующих действий:</span><span class="sxs-lookup"><span data-stu-id="78aef-283">**Resolution:** To load the updated cmdlets, you can do either of the following steps:</span></span>
    
   - <span data-ttu-id="78aef-284">Закройте PowerShell на устройстве Cloud Connector, а затем снова откройте PowerShell.</span><span class="sxs-lookup"><span data-stu-id="78aef-284">Close PowerShell on the Cloud Connector appliance, and then reopen PowerShell.</span></span>
    
     - <span data-ttu-id="78aef-285">Можно также выполнить командлет Import – Module CloudConnector — Force.</span><span class="sxs-lookup"><span data-stu-id="78aef-285">Or, you can run Import-Module CloudConnector -Force.</span></span> 
 
-   <span data-ttu-id="78aef-286">**Ошибка: "термин Stop-CsWindowsService" не распознается как имя командлета, функции, файла скрипта или программной программы. "ошибка при попытке выполнить командлет Enter-CcUpdate.**</span><span class="sxs-lookup"><span data-stu-id="78aef-286">**Issue: "The term 'Stop-CsWindowsService' is not recognized as the name of a cmdlet, function, script file, or operable program." error when attempting to run Enter-CcUpdate cmdlet.**</span></span>

    <span data-ttu-id="78aef-287">**Решение:** Удалите файл $HOME \Аппдата\локал\микрософт\виндовс\повершелл\модулеаналисискаче.</span><span class="sxs-lookup"><span data-stu-id="78aef-287">**Resolution:** Delete the $HOME\AppData\Local\Microsoft\Windows\PowerShell\ModuleAnalysisCache file.</span></span>
<span data-ttu-id="78aef-288">PowerShell создает этот файл в виде кэша командлетов из найденных модулей, чтобы не пришлось повторно анализировать все модули каждый раз, так как это приведет к значительному снижению производительности.</span><span class="sxs-lookup"><span data-stu-id="78aef-288">PowerShell creates this file as a cache of cmdlets from modules that it finds so that it doesn’t have to re-analyze all the modules each time as that would make things really slow.</span></span> <span data-ttu-id="78aef-289">Скорее всего, было вызвано повреждение файлов, предоставилее недостоверные результаты в PowerShell при чтении из кэша.</span><span class="sxs-lookup"><span data-stu-id="78aef-289">Most likely, there was some file corruption that provided misleading results to PowerShell when it was reading back from that cache.</span></span>

-   <span data-ttu-id="78aef-290">**Ошибка: "Import-Module CloudConnector" генерирует ошибку "Import-Module: указанный модуль" CloudConnector "не был загружен, так как в каком-либо из каталогов модулей не был найден допустимый файл модуля"**</span><span class="sxs-lookup"><span data-stu-id="78aef-290">**Issue: “Import-Module CloudConnector” generates error “Import-Module: The specified module “CloudConnector” was not loaded because no valid module file was found in any module directory”**</span></span>

    <span data-ttu-id="78aef-291">**Решение.**</span><span class="sxs-lookup"><span data-stu-id="78aef-291">**Resolution:**</span></span>
    - <span data-ttu-id="78aef-292">Проверка того, что в папке c:\Program Филес\виндовсповершелл\модулес существует модуль CloudConnector</span><span class="sxs-lookup"><span data-stu-id="78aef-292">Validate that indeed the CloudConnector module exists under c:\Program Files\WindowsPowerShell\Modules</span></span>
    
    - <span data-ttu-id="78aef-293">После проверки того, что модуль CloudConnector существует в этом расположении, переменная среды PSModulePath, в которой хранится путь к расположениям модулей, может быть изменена:</span><span class="sxs-lookup"><span data-stu-id="78aef-293">After validating that CloudConnector module exists under this location, the PSModulePath environment variable storing the path to the locations of the modules can be changed:</span></span>
    
     <span data-ttu-id="78aef-294">а)</span><span class="sxs-lookup"><span data-stu-id="78aef-294">a.</span></span> <span data-ttu-id="78aef-295">Временное изменение: запустите PowerShell от имени администратора и выполните следующую команду: $env:P Смодулепас = $env:P Смодулепас + "; C:\Program Филес\виндовсповершелл\модулес\"</span><span class="sxs-lookup"><span data-stu-id="78aef-295">Temporary change: Start Powershell as an Administrator and run the following command: $env:PSModulePath = $env:PSModulePath + ";C:\Program Files\WindowsPowerShell\Modules\"</span></span>
        
     <span data-ttu-id="78aef-296">б)</span><span class="sxs-lookup"><span data-stu-id="78aef-296">b.</span></span> <span data-ttu-id="78aef-297">Для сохранения изменений запустите PowerShell от имени администратора и выполните следующие команды, по одному: $CurrentValue = [Environment]:: Жетенвиронментвариабле ("PSModulePath", "Machine") Сетенвиронментвариабле ("PSModulePath", "Machine") ("", $CurrentValue + "; C:\Program Филес\виндовсповершелл\модулес "," Machine ")</span><span class="sxs-lookup"><span data-stu-id="78aef-297">For persistent change, Start PowerShell as an Administrator and run the following commands, one by one: $CurrentValue = [Environment]::GetEnvironmentVariable("PSModulePath", "Machine") SetEnvironmentVariable("PSModulePath", $CurrentValue + "; C:\Program Files\WindowsPowerShell\Modules", "Machine")</span></span>

    
## <a name="install-windows-updates-manually"></a><span data-ttu-id="78aef-298">Установка обновлений Windows вручную</span><span class="sxs-lookup"><span data-stu-id="78aef-298">Install Windows updates manually</span></span>

<span data-ttu-id="78aef-299">Если вы не хотите использовать автоматические обновления в своей среде, выполните следующие действия, чтобы вручную проверить и применить обновления Windows.</span><span class="sxs-lookup"><span data-stu-id="78aef-299">If you do not want to use automatic updates in your environment, follow these steps to manually check for and apply Windows updates.</span></span> <span data-ttu-id="78aef-300">Для проверки и установки обновлений Windows может потребоваться перезагрузка сервера.</span><span class="sxs-lookup"><span data-stu-id="78aef-300">Checking for and installing Windows updates may require a server restart.</span></span> <span data-ttu-id="78aef-301">При перезапуске сервера узла пользователи не смогут использовать Cloud Connector для размещения или приема звонков.</span><span class="sxs-lookup"><span data-stu-id="78aef-301">When a host server is restarting, users will not be able to use Cloud Connector to place or receive calls.</span></span> <span data-ttu-id="78aef-302">Вы можете вручную проверять наличие обновлений и устанавливать их, чтобы контролировать, когда они происходят, а затем перезапускать компьютеры при необходимости, чтобы избежать перерывов в работе служб.</span><span class="sxs-lookup"><span data-stu-id="78aef-302">You can manually check for and install updates to control when the updates take place, and then restart the machines as needed during times you choose to avoid disruption of services.</span></span>
  
<span data-ttu-id="78aef-303">Чтобы проверить наличие обновлений вручную, подключитесь к каждому серверу узла и откройте **Панель управления**.</span><span class="sxs-lookup"><span data-stu-id="78aef-303">To manually check for updates, connect to each host server and open the **Control Panel**.</span></span> <span data-ttu-id="78aef-304">Выберите **система и безопасность \> Windows Update**, а затем — Управление обновлениями и перезапусками сервера в соответствии с вашей средой.</span><span class="sxs-lookup"><span data-stu-id="78aef-304">Select **System and Security \>Windows Update**, and then manage the updates and server restarts as appropriate for your environment.</span></span>
  
- <span data-ttu-id="78aef-305">Если на сайте только одно устройство, подключитесь к каждой виртуальной машине и откройте **Панель управления**.</span><span class="sxs-lookup"><span data-stu-id="78aef-305">If there is only one appliance in the site, connect to each virtual machine and open the **Control Panel**.</span></span> <span data-ttu-id="78aef-306">Выберите **система и безопасность \> Windows Update**, а затем настройте обновления и перезапускать сервер соответствующим образом.</span><span class="sxs-lookup"><span data-stu-id="78aef-306">Select **System and Security \>Windows Update**, and then configure the updates and server restarts as appropriate.</span></span>
    
- <span data-ttu-id="78aef-307">Если на сайте несколько устройств, то во время обновлений пользователи не смогут получить доступ к обновляемому и перезапускаемому экземпляру.</span><span class="sxs-lookup"><span data-stu-id="78aef-307">If there are more than one appliance in the site, the instance being updated and restarted cannot be accessed by users during the updates.</span></span> <span data-ttu-id="78aef-308">Пользователи будут подключаться к другим экземплярам в развертывании до тех пор, пока все виртуальные машины и все службы Skype для бизнеса не будут запущены на виртуальных машинах после завершения обновления.</span><span class="sxs-lookup"><span data-stu-id="78aef-308">Users will connect to other instances in the deployment until all virtual machines and all Skype for Business services start on the virtual machines after the updates are completed.</span></span> <span data-ttu-id="78aef-309">Чтобы избежать возможного перерыва в обслуживании, можно удалить экземпляр из HA при применении обновлений, а затем восстановить его по завершении.</span><span class="sxs-lookup"><span data-stu-id="78aef-309">To avoid any potential disruption to service, you can remove the instance from HA while you apply the updates, and then restore it when complete.</span></span> <span data-ttu-id="78aef-310">Для этого:</span><span class="sxs-lookup"><span data-stu-id="78aef-310">To do so:</span></span>
    
1. <span data-ttu-id="78aef-311">На каждом сервере узла откройте консоль PowerShell от имени администратора.</span><span class="sxs-lookup"><span data-stu-id="78aef-311">On each host server, open a PowerShell console as administrator.</span></span>
    
2. <span data-ttu-id="78aef-312">Удалите экземпляр из HA с помощью следующего командлета:</span><span class="sxs-lookup"><span data-stu-id="78aef-312">Remove the instance from HA with the following cmdlet:</span></span>
    
   ```powershell
   Enter-CcUpdate
   ```

3. 
    
    <span data-ttu-id="78aef-313">Выполните действия для одного экземпляра, чтобы вручную применить обновления и перезапустить виртуальную машину.</span><span class="sxs-lookup"><span data-stu-id="78aef-313">Follow the steps for a single instance to manually apply the updates and restart the virtual machine.</span></span>
    
4. <span data-ttu-id="78aef-314">Установите для экземпляра значение HA с помощью следующего командлета:</span><span class="sxs-lookup"><span data-stu-id="78aef-314">Set the instance back to HA with the following cmdlet:</span></span>
    
   ```powershell
   Exit-CcUpdate
   ```

<span data-ttu-id="78aef-315">Для развертываний с несколькими сайтами выполните действия для отдельного сайта для каждого сайта в развертывании, применяя обновления к одному сайту за раз.</span><span class="sxs-lookup"><span data-stu-id="78aef-315">For multi-site deployments, follow the steps for a single site for each site in the deployment, applying updates to one site at a time.</span></span>
  
## <a name="tips-when-installing-anti-virus-software-on-the-cloud-connector-host-machine"></a><span data-ttu-id="78aef-316">Советы по установке антивирусного программного обеспечения на хостном компьютере Cloud Connector</span><span class="sxs-lookup"><span data-stu-id="78aef-316">Tips when installing anti-virus software on the Cloud Connector host machine</span></span>

<span data-ttu-id="78aef-317">Если необходимо установить антивирусную программу на хост машины Cloud Connector, необходимо добавить следующие исключения:</span><span class="sxs-lookup"><span data-stu-id="78aef-317">If you need to install anti-virus software on the Cloud Connector host machine, you need to add the following exclusions:</span></span>
  
- <span data-ttu-id="78aef-318">Локальный каталог устройств на каждом компьютере.</span><span class="sxs-lookup"><span data-stu-id="78aef-318">Local Appliance Directory on each machine.</span></span>
    
- <span data-ttu-id="78aef-319">Каталог удаленных сайтов на каждом компьютере.</span><span class="sxs-lookup"><span data-stu-id="78aef-319">Remote Site Directory on each machine.</span></span>
    
- <span data-ttu-id="78aef-320">Каталог локального сайта на компьютере содержит корневую папку общего сайта.</span><span class="sxs-lookup"><span data-stu-id="78aef-320">Local Site Directory on the machine hosts the shared site root folder.</span></span>
    
- <span data-ttu-id="78aef-321">%ProgramFiles%\Skype для бизнеса Cloud Connector Edition</span><span class="sxs-lookup"><span data-stu-id="78aef-321">%ProgramFiles%\Skype for Business Cloud Connector Edition</span></span>
    
- <span data-ttu-id="78aef-322">%аллусерспрофиле%\клаудконнектор</span><span class="sxs-lookup"><span data-stu-id="78aef-322">%ALLUSERSPROFILE%\CloudConnector</span></span>
    
- <span data-ttu-id="78aef-323">%програмфилес%\виндовсповершелл\модулес\клаудконнектор</span><span class="sxs-lookup"><span data-stu-id="78aef-323">%ProgramFiles%\WindowsPowerShell\Modules\CloudConnector</span></span>
    
- <span data-ttu-id="78aef-324">Процесс Microsoft. RTC. CCE. Манажементсервице. exe.</span><span class="sxs-lookup"><span data-stu-id="78aef-324">The process Microsoft.Rtc.CCE.ManagementService.exe.</span></span>
