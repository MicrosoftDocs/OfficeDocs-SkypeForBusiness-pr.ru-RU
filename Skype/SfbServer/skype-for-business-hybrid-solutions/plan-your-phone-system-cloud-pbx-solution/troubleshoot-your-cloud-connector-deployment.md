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
# <a name="troubleshoot-your-cloud-connector-deployment"></a><span data-ttu-id="330b5-103">Устранение неполадок с развертыванием Cloud Connector</span><span class="sxs-lookup"><span data-stu-id="330b5-103">Troubleshoot your Cloud Connector deployment</span></span>

> [!Important]
> <span data-ttu-id="330b5-104">Cloud Connector Edition выйдет 31 июля 2021 вместе со Skype для бизнеса Online.</span><span class="sxs-lookup"><span data-stu-id="330b5-104">Cloud Connector Edition will retire July 31, 2021 along with Skype for Business Online.</span></span> <span data-ttu-id="330b5-105">После обновления вашей организации до Teams Узнайте, как подключить локальную телефонную сеть к Teams с помощью [прямой маршрутизации](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page).</span><span class="sxs-lookup"><span data-stu-id="330b5-105">Once your organization has upgraded to Teams, learn how to connect your on-premises telephony network to Teams using [Direct Routing](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page).</span></span>
 
<span data-ttu-id="330b5-106">Устранение неполадок развертывания Cloud Connector Edition.</span><span class="sxs-lookup"><span data-stu-id="330b5-106">Troubleshoot your Cloud Connector Edition deployment.</span></span>
  
<span data-ttu-id="330b5-107">В этом разделе описываются решения распространенных проблем, связанных с развертываниями Cloud Connector Edition.</span><span class="sxs-lookup"><span data-stu-id="330b5-107">This topic describes solutions to common issues with Cloud Connector Edition deployments.</span></span> <span data-ttu-id="330b5-108">Если у вас возникли проблемы с вызовами и из телефонной сети общего пользования (PSTN), вы можете изучить следующие решения, описанные в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="330b5-108">If you are experiencing issues with calls to and from the Public Switched Telephone Network (PSTN), you can investigate by following the solutions described in this topic.</span></span>
  
<span data-ttu-id="330b5-109">Cloud Connector предоставляет встроенные механизмы для автоматического устранения некоторых проблем.</span><span class="sxs-lookup"><span data-stu-id="330b5-109">Cloud Connector provides built-in mechanisms for automatically resolving some issues.</span></span> <span data-ttu-id="330b5-110">Процесс автоматического обнаружения выполняет поиск потенциальных проблем для устройств Cloud Connector и, если это возможно, предпринимает корректирующие меры по устранению этих проблем без необходимости вмешательства администратора.</span><span class="sxs-lookup"><span data-stu-id="330b5-110">An automatic detection process looks for potential issues with the Cloud Connector appliances, and, if possible, takes corrective action to resolve those issues without the need for administrator intervention.</span></span> <span data-ttu-id="330b5-111">Процесс обнаружения работает следующим образом:</span><span class="sxs-lookup"><span data-stu-id="330b5-111">The detection process works as follows:</span></span>
  
- <span data-ttu-id="330b5-112">**Последовательность обнаружения:** Служба управления Cloud Connector запускает процесс каждые 60 секунд, чтобы определить, не отключено ли устройство.</span><span class="sxs-lookup"><span data-stu-id="330b5-112">**Detection sequence:** The Cloud Connector Management service runs a process every 60 seconds for detecting whether an appliance is down.</span></span> <span data-ttu-id="330b5-113">В Cloud Connector версии 2,0 и более поздних в процессе обнаружения используется переключатель в корпоративной сети Skype для бизнеса для создания подключений PowerShell к машинам Cloud Connector; для версий, предшествующих 2,0, процесс обнаружения использует коммутатор управления Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="330b5-113">In Cloud Connector version 2.0 and later, the detection process uses the Skype for Business Corpnet switch for making PowerShell connections to the Cloud Connector machines; for versions previous to 2.0, the detection process uses the Cloud Connector management switch.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="330b5-114">Для успешного выполнения автоматического восстановления между узлом и виртуальными машинами должно быть установлено сетевое подключение через коммутатор узла сети.</span><span class="sxs-lookup"><span data-stu-id="330b5-114">For automatic recovery to succeed, there must be network connectivity between the host and virtual machines over the host network switch.</span></span> <span data-ttu-id="330b5-115">Обязательно проверьте сетевое подключение, чтобы убедиться, что автоматическое обнаружение и восстановление может быть успешным.</span><span class="sxs-lookup"><span data-stu-id="330b5-115">Be sure to check network connectivity to ensure that automatic detection and recovery can succeed.</span></span> 
  
- <span data-ttu-id="330b5-116">**Мониторинг:** Следующие службы отслеживаются в Cloud Connector версии 2,0 и более поздних:</span><span class="sxs-lookup"><span data-stu-id="330b5-116">**Monitoring:** The following services are monitored in Cloud Connector version 2.0 and later:</span></span>
    
  - <span data-ttu-id="330b5-117">Виртуальные машины не подключены к виртуальным коммутаторам Cloud Connector или Интернет</span><span class="sxs-lookup"><span data-stu-id="330b5-117">Virtual Machines are not connected to the Cloud Connector Corporate or Internet virtual switches</span></span>
    
  - <span data-ttu-id="330b5-118">Виртуальные машины находятся в состоянии "сохранено" или "остановлено"</span><span class="sxs-lookup"><span data-stu-id="330b5-118">Virtual Machines are in a saved or stopped status</span></span>
    
  - <span data-ttu-id="330b5-119">Службы сервера централизованного управления: РЕПЛИКа, основной</span><span class="sxs-lookup"><span data-stu-id="330b5-119">Central Management Server services: REPLICA, MASTER</span></span>
    
  - <span data-ttu-id="330b5-120">Службы сервера-посредника: РЕПЛИКа, RTCSRV и МЕДСВК</span><span class="sxs-lookup"><span data-stu-id="330b5-120">Mediation Server services: REPLICA, RTCSRV and MEDSVC</span></span>
    
  - <span data-ttu-id="330b5-121">Службы пограничных серверов: РЕПЛИКа, RTCSRV, РТКДАТАПРОКСИ, РТКМРАУС, РТКМЕДИАРЕЛАЙ</span><span class="sxs-lookup"><span data-stu-id="330b5-121">Edge Server services: REPLICA, RTCSRV, RTCDATAPROXY, RTCMRAUTH, RTCMEDIARELAY</span></span>
    
  - <span data-ttu-id="330b5-122">Правила брандмауэра для входящих подключений отключены для CS RTCSRV на пограничном сервере, CS РТКМЕДСРВ на сервере-посреднике</span><span class="sxs-lookup"><span data-stu-id="330b5-122">Inbound firewall rules are disabled for CS RTCSRV on Edge server, CS RTCMEDSRV on Mediation server</span></span>
    
    <span data-ttu-id="330b5-123">В Cloud Connector версии 1.4.2 отслеживаются только следующие службы:</span><span class="sxs-lookup"><span data-stu-id="330b5-123">In Cloud Connector version 1.4.2, only the following services are monitored:</span></span>
    
  - <span data-ttu-id="330b5-124">Службы сервера-посредника: RTCSRV и МЕДСВК</span><span class="sxs-lookup"><span data-stu-id="330b5-124">Mediation Server services: RTCSRV and MEDSVC</span></span>
    
  - <span data-ttu-id="330b5-125">Служба пограничного сервера: RTCSRV</span><span class="sxs-lookup"><span data-stu-id="330b5-125">Edge Server service: RTCSRV</span></span>
    
- <span data-ttu-id="330b5-126">**Процесс восстановления:** Если какие-либо отслеживаемые службы отключены, устройство помечается как отключенное, а службы останавливаются и помечаются вручную до тех пор, пока не будут устранены все проблемы.</span><span class="sxs-lookup"><span data-stu-id="330b5-126">**Recovery process:** If any monitored services are down, an appliance is marked down, and services are stopped and marked manual until all issues can be resolved.</span></span> <span data-ttu-id="330b5-127">Это предотвратит маршрутизацию звонков на устройство, которое может привести к сбоям вызовов.</span><span class="sxs-lookup"><span data-stu-id="330b5-127">This will prevent calls from routing to an appliance that may cause call failures.</span></span>
    
    <span data-ttu-id="330b5-128">Служба управления Cloud Connector повторит попытку автоматического восстановления, как показано ниже.</span><span class="sxs-lookup"><span data-stu-id="330b5-128">The Cloud Connector Management service will retry automatic recovery as follows</span></span>
    
  - <span data-ttu-id="330b5-129">Первый интервал повтора составляет каждые десять секунд с максимальным интервалом в один час.</span><span class="sxs-lookup"><span data-stu-id="330b5-129">The initial retry interval is every ten seconds with a maximum interval time of one hour.</span></span>
    
  - <span data-ttu-id="330b5-130">Для первых трех попыток восстановления время ожидания составляет 10 секунд.</span><span class="sxs-lookup"><span data-stu-id="330b5-130">For the first three recovery attempts, the interval time is 10 seconds.</span></span> <span data-ttu-id="330b5-131">Начиная с четвертой попытки, время в интервале увеличивается на два раза больше предыдущего интервала времени.</span><span class="sxs-lookup"><span data-stu-id="330b5-131">Starting from the fourth retry, the interval time increases by two times the previous interval time.</span></span> <span data-ttu-id="330b5-132">Например, четвертая повторная попытка будет выполнена в течение 20 секунд, пятый в 40 секунд и т. д.</span><span class="sxs-lookup"><span data-stu-id="330b5-132">For example, the fourth retry will occur in 20 seconds, the fifth in 40 seconds, and so on.</span></span> 
    
  - <span data-ttu-id="330b5-133">При достижении максимального интервала в один час количество повторных попыток будет продолжаться в час.</span><span class="sxs-lookup"><span data-stu-id="330b5-133">When the maximum interval time of one hour is reached, retries will continue once per hour.</span></span>
    
  - <span data-ttu-id="330b5-134">При успешном завершении восстановления в качестве интервала и числа повторных попыток задаются исходные значения.</span><span class="sxs-lookup"><span data-stu-id="330b5-134">When recovery is successful, the interval and retry counts are set to their initial values.</span></span>
    
  - <span data-ttu-id="330b5-135">Если служба управления перезапущена, счетчики интервалов и повторных попыток сбрасываются в исходные значения.</span><span class="sxs-lookup"><span data-stu-id="330b5-135">If the Management service is restarted, the interval and retry counts are reset to their initial values.</span></span>
    
## <a name="troubleshooting"></a><span data-ttu-id="330b5-136">Устранение неполадок</span><span class="sxs-lookup"><span data-stu-id="330b5-136">Troubleshooting</span></span>

<span data-ttu-id="330b5-137">Ниже приведены решения часто встречающихся проблем.</span><span class="sxs-lookup"><span data-stu-id="330b5-137">Following are solutions to commonly encountered issues:</span></span>
  
- <span data-ttu-id="330b5-138">**Ошибка: при выполнении сценариев развертывания развертывание завершается с ошибкой или перестает отвечать. После входа на каждую виртуальную машину IP-адрес отсутствует или неверен для управления/внутреннего или внешнего сетевого адаптера.**</span><span class="sxs-lookup"><span data-stu-id="330b5-138">**Issue: Deployment fails or stops responding when running the deployment scripts. After logging on to each VM, the IP address is missing or incorrect for the Management/Internal/External NIC.**</span></span>
    
    <span data-ttu-id="330b5-139">**Решение:** Эту проблему невозможно устранить автоматически.</span><span class="sxs-lookup"><span data-stu-id="330b5-139">**Resolution:** This issue cannot be resolved automatically.</span></span> <span data-ttu-id="330b5-140">Сетевые адаптеры Невозможно добавить к виртуальным машинам во время их выполнения.</span><span class="sxs-lookup"><span data-stu-id="330b5-140">NICs cannot be added to VMs while they are running.</span></span> <span data-ttu-id="330b5-141">Завершите работу виртуальных машин и удалите их в диспетчере Hyper – v, а затем выполните следующие командлеты:</span><span class="sxs-lookup"><span data-stu-id="330b5-141">Please shut down and remove these VMs in hyper-v manager, then run the following cmdlets:</span></span>
    
  ```powershell
  Uninstall-CcAppliance
  ```

  ```powershell
  Install-CcAppliance
  ```

- 
    
    <span data-ttu-id="330b5-142">**Вопрос: после установки сервера и/или сервера-посредника Active Directory сервер CMS и/или сервер-посредник не присоединяются к домену должным образом.**</span><span class="sxs-lookup"><span data-stu-id="330b5-142">**Issue: After the Active Directory Server and forest are installed, the CMS Server and/or Mediation Server did not join the domain correctly.**</span></span>
    
    <span data-ttu-id="330b5-143">**Решение:** Чтобы устранить эту проблему, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="330b5-143">**Resolution:** To resolve this issue, take the following steps:</span></span>
    
  - <span data-ttu-id="330b5-144">Выполните вход на сервер Active Directory и убедитесь, что домен создан правильно.</span><span class="sxs-lookup"><span data-stu-id="330b5-144">Log on to the Active Directory Server and verify that the domain was created correctly.</span></span>
    
  - <span data-ttu-id="330b5-145">Выполните вход на сервер CMS/-посредника и убедитесь, что в корпоративной NIC назначен допустимый IP-адрес, а действительный статический IP-адрес и DNS настроены как IP-адрес сервера AD.</span><span class="sxs-lookup"><span data-stu-id="330b5-145">Log on to the CMS/Mediation Server and verify that on the corpnet NIC a valid IP address is assigned, and that valid static IP and DNS is configured as the AD server's IP address.</span></span>
    
  - <span data-ttu-id="330b5-146">Выполните вход на сервер CMS/-посредника и откройте командную строку.</span><span class="sxs-lookup"><span data-stu-id="330b5-146">Log on to the CMS/Mediation Server, and open a command prompt.</span></span> <span data-ttu-id="330b5-147">Убедитесь, что вы можете выполнить команду ping для полного доменного имени и IP-адреса сервера Active Directory.</span><span class="sxs-lookup"><span data-stu-id="330b5-147">Make sure you can ping the FQDN and IP address of the Active Directory Server.</span></span> <span data-ttu-id="330b5-148">Если этого не сделать, может возникнуть конфликт IP-адресов.</span><span class="sxs-lookup"><span data-stu-id="330b5-148">If you cannot, there may be an IP address conflict.</span></span> <span data-ttu-id="330b5-149">Попробуйте назначить новый IP-адрес для Active Directory и соответствующим образом обновить DNS на сервере CMS/-посреднике.</span><span class="sxs-lookup"><span data-stu-id="330b5-149">Please try to assign a new IP for Active Directory and update DNS on the CMS/Mediation server accordingly.</span></span>
    
- <span data-ttu-id="330b5-150">**Причина: вы получите следующее сообщение об ошибке: "Remove – VMSwitch: сбой при удалении виртуального коммутатора Ethernet". Невозможно удалить виртуальный коммутатор с переключателем управления Cloud Connector, так как он используется работающими виртуальными машинами или назначен дочерним пулам. "**</span><span class="sxs-lookup"><span data-stu-id="330b5-150">**Issue: You receive the following error message, "Remove-VMSwitch : Failed while removing virtual Ethernet switch. The virtual switch 'Cloud Connector Management Switch' cannot be deleted because it is being used by running virtual machines or assigned to child pools."**</span></span>
    
    <span data-ttu-id="330b5-151">**Решение:** "Коммутатор управления Cloud Connector" не был удален после развертывания.</span><span class="sxs-lookup"><span data-stu-id="330b5-151">**Resolution:** The "Cloud Connector Management Switch" was not deleted after the deployment.</span></span> <span data-ttu-id="330b5-152">Если вы столкнулись с этой ошибкой, перейдите в Диспетчер Hyper-v и убедитесь, что к ней еще не подключена виртуальная машина.</span><span class="sxs-lookup"><span data-stu-id="330b5-152">If you hit this error, please go to Hyper-v manager and verify that there is not still a virtual machine still connected to it.</span></span> <span data-ttu-id="330b5-153">Если виртуальные машины по-прежнему подключены, отключите их и удалите переключатель управления.</span><span class="sxs-lookup"><span data-stu-id="330b5-153">If there are virtual machines still connected, disconnect them and delete the management switch.</span></span> <span data-ttu-id="330b5-154">Если параметр управления по-прежнему не может быть удален, перезапустите хост-сервер и повторите попытку.</span><span class="sxs-lookup"><span data-stu-id="330b5-154">If the management switch still cannot be deleted, restart the host server and try again.</span></span>
    
- <span data-ttu-id="330b5-155">**Причина: появится следующее сообщение об ошибке: "сбой при запуске службы РТКМРАУС. Убедитесь, что служба не отключена. "**</span><span class="sxs-lookup"><span data-stu-id="330b5-155">**Issue: You receive the following error message, "Service RTCMRAUTH failed to start. Check to make sure the service is not disabled."**</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="330b5-156">Эта проблема относится только к версиям Cloud Connector, предшествующим 1.4.2.</span><span class="sxs-lookup"><span data-stu-id="330b5-156">This issue only applies to Cloud Connector versions earlier than 1.4.2.</span></span> 
  
    <span data-ttu-id="330b5-157">Сбой при запуске может также быть вызван тем, что сервер переднего плана был ранее отработкой отказа (с использованием компьютера при сбое).</span><span class="sxs-lookup"><span data-stu-id="330b5-157">The failure to start could also be because this Front End server was previously failed over (using computer fail over).</span></span> <span data-ttu-id="330b5-158">Если это так, выйдите из строя и снова выйдите из системы.</span><span class="sxs-lookup"><span data-stu-id="330b5-158">If that's the case, please invoke fail back (using computer fail back).</span></span>
    
    <span data-ttu-id="330b5-159">**Решение:** Эта проблема возникает на пограничном сервере, если сертификат корневого центра сертификации или сертификат промежуточного центра сертификации не является доверенным для пограничного сервера.</span><span class="sxs-lookup"><span data-stu-id="330b5-159">**Resolution:** This issue happens on an Edge Server when the root CA certificate or intermediate CA certificate is not trusted by the Edge Server.</span></span> <span data-ttu-id="330b5-160">Даже если внешний сертификат можно импортировать, но цепочка сертификатов разорвана.</span><span class="sxs-lookup"><span data-stu-id="330b5-160">Even if the external certificate can be imported but the certificate chain is broken.</span></span> <span data-ttu-id="330b5-161">В этом случае служба РТКМРАУС и/или RTCSRV не может запуститься.</span><span class="sxs-lookup"><span data-stu-id="330b5-161">Under this condition, the RTCMRAUTH and/or RTCSRV service can not start.</span></span>
    
    <span data-ttu-id="330b5-162">Импортируйте сертификат корневого центра сертификации и все промежуточные сертификаты ЦС внешнего сертификата вручную в пограничный сервер, а затем перезапустите пограничный сервер.</span><span class="sxs-lookup"><span data-stu-id="330b5-162">Please import the root CA certificate and all intermediate CA certificates of your external certificate manually into the Edge Server and then restart the Edge Server.</span></span> <span data-ttu-id="330b5-163">После того как вы увидите службы РТКМРАУС и RTCSRV, запущенные на пограничном сервере, вернитесь на сервер узла, запустите консоль PowerShell от имени администратора и выполните следующий командлет, чтобы переключиться на новое развертывание:</span><span class="sxs-lookup"><span data-stu-id="330b5-163">After you see the RTCMRAUTH and RTCSRV services started on the Edge Server, go back to your host server, launch a PowerShell console as administrator, and run following cmdlet to switch to the new deployment:</span></span>
    
  ```powershell
  Switch-CcVersion
  ```

- 
    
    <span data-ttu-id="330b5-164">**Ошибка: сервер узла был перезапущен при применении обновлений Windows, а вызовы, обслуживаемые сервером, отправляются с ошибкой.**</span><span class="sxs-lookup"><span data-stu-id="330b5-164">**Issue: The host server was restarted when Windows updates were applied, and calls serviced by the server are failing.**</span></span>
    
    <span data-ttu-id="330b5-165">**Решение:** Если вы развернули среду с высокой доступностью, корпорация Майкрософт предоставляет командлет, позволяющий перемещать один хост-компьютер (экземпляр развертывания) в текущую топологию и из нее при проверке и установке центра обновления Windows вручную.</span><span class="sxs-lookup"><span data-stu-id="330b5-165">**Resolution:** If you deployed a high availability environment, Microsoft provides a cmdlet to help move one host machine (deployment instance) into or out of the current topology when you check and install Windows update manually.</span></span> <span data-ttu-id="330b5-166">Чтобы выполнить эту задачу, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="330b5-166">Use the following steps to accomplish this:</span></span>
    
1. <span data-ttu-id="330b5-167">На сервере узла запустите консоль PowerShell от имени администратора, а затем выполните команду:</span><span class="sxs-lookup"><span data-stu-id="330b5-167">On the host server, start a PowerShell console as administrator, then run:</span></span>
    
   ```powershell
   Enter-CcUpdate
   ```

2. <span data-ttu-id="330b5-168">Проверьте наличие обновлений и установите доступные.</span><span class="sxs-lookup"><span data-stu-id="330b5-168">Check for updates and install any that are available.</span></span>
    
3. <span data-ttu-id="330b5-169">В консоли PowerShell выполните следующий командлет:</span><span class="sxs-lookup"><span data-stu-id="330b5-169">In the PowerShell console, run the following cmdlet:</span></span>
    
   ```powershell
   Exit-CcUpdate
   ```

- 
    
    <span data-ttu-id="330b5-170">**Вопрос: при совершении вызова из клиента Skype для бизнеса с помощью номера PSTN этот звонок нельзя эскалировать на конференцию, приглашая еще один номер PSTN.**</span><span class="sxs-lookup"><span data-stu-id="330b5-170">**Issue: When a call is made from a Skype for Business client using a PSTN number, the call cannot be escalated to a conference by inviting another PSTN number.**</span></span>
    
    <span data-ttu-id="330b5-171">**Решение:** Чтобы устранить эту проблему, ознакомьтесь со статьей [Настройка параметров сервера гибридного гибридного сервера-посредника](configure-cloud-connector-integration-with-your-office-365-tenant.md#BKMK_ConfigureMediationServer).</span><span class="sxs-lookup"><span data-stu-id="330b5-171">**Resolution:** To resolve this issue, see [Configure online hybrid Mediation Server Settings](configure-cloud-connector-integration-with-your-office-365-tenant.md#BKMK_ConfigureMediationServer).</span></span>
    
- <span data-ttu-id="330b5-172">**Вопрос: при установке сервера Active Directory ("автоматическое обновление Windows") отображается предупреждающее сообщение об обновлении Windows: "автоматическое обновление Windows не включено". Чтобы убедиться, что недавно установленная роль или функция автоматически обновляется, включите обновление Windows. "**</span><span class="sxs-lookup"><span data-stu-id="330b5-172">**Issue: A warning message is displayed about Windows Update when you are installing Active Directory server - "Windows automatic updating is not enabled. To ensure that your newly-installed role or feature is automatically updated, turn on Windows Update."**</span></span>
    
    <span data-ttu-id="330b5-173">**Решение:** Запустите удаленный сеанс PowerShell клиента с помощью учетных данных администратора клиента Skype для бизнеса, а затем выполните следующий командлет, чтобы проверить конфигурацию _EnableAutoUpdate_ для сайта:</span><span class="sxs-lookup"><span data-stu-id="330b5-173">**Resolution:** Launch a Tenant Remote PowerShell session using Skype for Business tenant admin credentials, then run the following cmdlet to check the _EnableAutoUpdate_ configuration of your site:</span></span>
    
  ```powershell
  Get-CsHybridPSTNSite
  ```

    <span data-ttu-id="330b5-174">Если для  _EnableAutoUpdate_ задано **значение true**, можно спокойно проигнорировать это предупреждение, так как служба кцеманажемент будет обрабатывать загрузку и установку обновлений Windows для виртуальных машин и хост-сервера.</span><span class="sxs-lookup"><span data-stu-id="330b5-174">If  _EnableAutoUpdate_ is set to **True**, you can safely ignore this warning message because the CCEManagement service will handle downloading and installing Windows updates for both virtual machines and the host server.</span></span> <span data-ttu-id="330b5-175">Если для  _EnableAutoUpdate_ задано значение **false**, выполните следующий командлет, чтобы задать для него значение **true**.</span><span class="sxs-lookup"><span data-stu-id="330b5-175">If  _EnableAutoUpdate_ is set to **False**, run following cmdlet to set it to **True**.</span></span>
    
  ```powershell
  Set-CsHybridPSTNSite -EnableAutoUpdate $true
  ```

    <span data-ttu-id="330b5-176">Кроме того, вы можете вручную проверить наличие обновлений и установить их.</span><span class="sxs-lookup"><span data-stu-id="330b5-176">Alternatively, you can manually check for and install updates.</span></span> <span data-ttu-id="330b5-177">(см. следующий раздел).</span><span class="sxs-lookup"><span data-stu-id="330b5-177">See the next section.</span></span>
    
- <span data-ttu-id="330b5-178">**Вопрос: вы получаете сообщение об ошибке: "не удается зарегистрировать устройство", так как текущие входные данные (или или или или или \<SiteName\> \<ApplianceName\> \<Mediation Server FQDN\> \<Mediation Server IP Address\> ) конфликтуют с существующими устройствам. Удалите конфликтующее устройство или обновите сведения о входных и конфигурационных данных, а затем повторите регистрацию. ' при выполнении Register-CcAppliance для регистрации текущего устройства в оперативный режим.**</span><span class="sxs-lookup"><span data-stu-id="330b5-178">**Issue: You receive an error message: Cannot register appliance because your current input/configuration \<SiteName\> or \<ApplianceName\> or \<Mediation Server FQDN\> or \<Mediation Server IP Address\> conflicts with existing appliance(s). Remove conflict appliance or update your input/configuration information then register again. ' when run Register-CcAppliance to register current appliance to online.**</span></span>
    
    <span data-ttu-id="330b5-179">**Решение:** Значения параметра \<ApplianceName\> \<Mediation Server FQDN\> и \<Mediation Server IP Address\> должны быть уникальными и использоваться только для регистрации одного устройства.</span><span class="sxs-lookup"><span data-stu-id="330b5-179">**Resolution:** Values for the \<ApplianceName\>, \<Mediation Server FQDN\> and \<Mediation Server IP Address\> must be unique and only used for one appliance registration.</span></span> <span data-ttu-id="330b5-180">По умолчанию \<ApplianceName\> берется из имени узла.</span><span class="sxs-lookup"><span data-stu-id="330b5-180">By default, \<ApplianceName\> comes from the host name.</span></span> <span data-ttu-id="330b5-181">\<Mediation Server FQDN\> и \<Mediation Server IP Address\> определен в ini-файле конфигурации.</span><span class="sxs-lookup"><span data-stu-id="330b5-181">\<Mediation Server FQDN\> and \<Mediation Server IP Address\> defined in configuration ini file.</span></span>
    
    <span data-ttu-id="330b5-182">Например, при использовании (выступает имя устройства = Мисервернев, имя сервера-посредника FQDN = MS. contoso. com, IP-адрес сервера-посредника = 10.10.10.10) для регистрации на сайте SiteName = личного сайта, но при наличии зарегистрированного устройства (выступает имя устройства = MyServer, имя сервера-посредника = $. contoso. com, IP-адрес сервера-посредника — 10.10.10.10) возникает конфликт.</span><span class="sxs-lookup"><span data-stu-id="330b5-182">For example, using (ApplianceName= MyserverNew, Mediation Server FQDN=ms.contoso.com, Mediation Server IP Address=10.10.10.10) to register to SiteName=MySite, but if there is a registered appliance (ApplianceName= Myserver, Mediation Server FQDN=ms.contoso.com, Mediation Server IP Address=10.10.10.10), you will have the conflict.</span></span>
    
    <span data-ttu-id="330b5-183">Для начала проверьте файл CloudConnector.ini в разделе Апплианцерут Directory.</span><span class="sxs-lookup"><span data-stu-id="330b5-183">First, please check your CloudConnector.ini file in ApplianceRoot directory section.</span></span> <span data-ttu-id="330b5-184">\<SiteName\>В файле будут получены \<Mediation Server FQDN\> и \<Mediation Server IP Address\> значения.</span><span class="sxs-lookup"><span data-stu-id="330b5-184">You will get \<SiteName\>, \<Mediation Server FQDN\> and \<Mediation Server IP Address\> values in the file.</span></span> <span data-ttu-id="330b5-185">\<ApplianceName\> — Это имя сервера узла.</span><span class="sxs-lookup"><span data-stu-id="330b5-185">\<ApplianceName\> is your host server name.</span></span>
    
    <span data-ttu-id="330b5-186">Во-вторых, запустите удаленную консоль PowerShell клиента, используя учетные данные администратора клиента Skype для бизнеса, а затем выполните следующий командлет, чтобы проверить зарегистрированные устройства.</span><span class="sxs-lookup"><span data-stu-id="330b5-186">Second, Launch Tenant Remote PowerShell using your Skype for Business tenant admin credentials, then run the following cmdlet to check the registered appliance(s).</span></span>
    
  ```powershell
  Get-CsHybridPSTNAppliance
  ```

    <span data-ttu-id="330b5-187">Определив конфликты, можно либо обновить файл CloudConnector.ini, указав сведения, соответствующие зарегистрированному устройству, либо отменить регистрацию существующего устройства для разрешения конфликтов.</span><span class="sxs-lookup"><span data-stu-id="330b5-187">After identifying any conflicts, you can either update your CloudConnector.ini file with information that matches the registered appliance, or unregister the existing appliance to resolve the conflicts.</span></span>
    
  ```powershell
  Unregister-CsHybridPSTNAppliance -Force
  ```

    
- <span data-ttu-id="330b5-188">**Ошибка: командлет Get-CcRunningVersion возвращает пустое значение, если на узле выполняется развернутое устройство.**</span><span class="sxs-lookup"><span data-stu-id="330b5-188">**Issue: The Get-CcRunningVersion cmdlet returns an empty value if there is a deployed appliance running on the host.**</span></span>
    
  <span data-ttu-id="330b5-189">**Решение:** Это может происходить при обновлении с 1.3.4 или 1.3.8 до 1.4.1.</span><span class="sxs-lookup"><span data-stu-id="330b5-189">**Resolution:** This can happen when you upgrade from 1.3.4 or 1.3.8 to 1.4.1.</span></span> <span data-ttu-id="330b5-190">После установки версии 1.4.1 с помощью MSI необходимо выполнить `Register-CcAppliance` перед запуском любого другого командлета.</span><span class="sxs-lookup"><span data-stu-id="330b5-190">After you install version 1.4.1 with the .msi, you must run `Register-CcAppliance` before you run any other cmdlet.</span></span> <span data-ttu-id="330b5-191">`Register-CcAppliance` будет переносить файл module.ini из%Усерпрофиле%\клаудконнектор в%Програмдата%\клаудконнектор.</span><span class="sxs-lookup"><span data-stu-id="330b5-191">`Register-CcAppliance` will migrate the module.ini file from %UserProfile%\CloudConnector to %ProgramData%\CloudConnector.</span></span> <span data-ttu-id="330b5-192">Если вы пропустили его, в папке%Програмдата%\клаудконнектор будет создан новый module.ini и заменяются сведения о версии, используемой для 1.3.4 или 1.3.8.</span><span class="sxs-lookup"><span data-stu-id="330b5-192">If you missed it, a new module.ini will be created in %ProgramData%\CloudConnector folder and replace the running/backup version information for 1.3.4 or 1.3.8.</span></span>
    
  <span data-ttu-id="330b5-193">Сравните module.ini файлы в папке%Усерпрофиле%\клаудконнектор и%Програмдата%\клаудконнектор.</span><span class="sxs-lookup"><span data-stu-id="330b5-193">Compare module.ini files in %UserProfile%\CloudConnector and %ProgramData%\CloudConnector folder.</span></span> <span data-ttu-id="330b5-194">При наличии различий удалите файл module.ini в%Програмдата%\клаудконнектор и повторите операцию  `Register-CcAppliance` .</span><span class="sxs-lookup"><span data-stu-id="330b5-194">If there are differences, delete the module.ini file in %ProgramData%\CloudConnector and rerun  `Register-CcAppliance`.</span></span> <span data-ttu-id="330b5-195">Вы также можете изменить файл вручную, дополнив его на правильную версию и резервную копию.</span><span class="sxs-lookup"><span data-stu-id="330b5-195">You could also modify the file manually to the correct running and backup version.</span></span>
    
- <span data-ttu-id="330b5-196">**Проблема: после выполнения командлета Switch-CcVersion для переключения на старую версию, которая отличается от текущей версии сценария, для этой старой версии нет поддержки высокого уровня доступности.**</span><span class="sxs-lookup"><span data-stu-id="330b5-196">**Issue: After you run the Switch-CcVersion cmdlet to switch to an old version which is different from current script version, there is no High Availability support for this old version.**</span></span>
    
    <span data-ttu-id="330b5-197">**Решение:** Например, вы выполнили обновление с 1.4.1 на 1.4.2.</span><span class="sxs-lookup"><span data-stu-id="330b5-197">**Resolution:** For example, you have upgraded from 1.4.1 to 1.4.2.</span></span> <span data-ttu-id="330b5-198">Текущая версия скрипта, которая может быть определена при запуске `Get-CcVersion` , и используемая версия, которую можно определить с помощью команды  `Get-CcRunningVersion` 1.4.2.</span><span class="sxs-lookup"><span data-stu-id="330b5-198">Your current script version, which can be determined by running `Get-CcVersion`, and your running version, which can be determined by running  `Get-CcRunningVersion` are both 1.4.2.</span></span> <span data-ttu-id="330b5-199">В настоящее время, если вы перейдете на `Switch-CcVersion` 1.4.1, то для этой старой версии будет отсутствовать поддержка высокого уровня доступности.</span><span class="sxs-lookup"><span data-stu-id="330b5-199">At this time, if you run `Switch-CcVersion` to switch the running version back to 1.4.1, then there will be no High Availability support for this old version.</span></span>
    
    <span data-ttu-id="330b5-200">Чтобы получить поддержку высокого уровня доступности, переключитесь обратно в 1.4.2, поэтому действующая версия и версия сценария совпадают.</span><span class="sxs-lookup"><span data-stu-id="330b5-200">To get full High Availability support, please switch back to 1.4.2, so the running version and script version are the same.</span></span> <span data-ttu-id="330b5-201">Если у вас возникли проблемы с развертыванием 1.4.2, удалите и переустановите его как можно скорее.</span><span class="sxs-lookup"><span data-stu-id="330b5-201">If you are experiencing problems with your 1.4.2 deployment, please uninstall and reinstall it as soon as possible.</span></span>
    
- <span data-ttu-id="330b5-202">**Причина: сертификаты центра сертификации или внутренние сертификаты, выданные центральному хранилищу управления, серверу-посреднику и пограничному серверу, истекает из истечения срока действия или скомпрометированы.**</span><span class="sxs-lookup"><span data-stu-id="330b5-202">**Issue: Certificate authority certificates or internal certificates issued to Central Management Store, Mediation Server, and Edge Server are near expiration or are compromised.**</span></span>
    
    <span data-ttu-id="330b5-203">**Решение:** Сертификаты центра сертификации Skype для бизнеса действительны в течение пяти лет.</span><span class="sxs-lookup"><span data-stu-id="330b5-203">**Resolution:** Skype for Business certification authority certificates are valid for five years.</span></span> <span data-ttu-id="330b5-204">Внутренние сертификаты, выданные для центрального хранилища управления, сервера-посредника и пограничного сервера, действительны в течение двух лет.</span><span class="sxs-lookup"><span data-stu-id="330b5-204">Internal certificates issued to the Central Management Store, Mediation Server, and Edge Server are valid for two years.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="330b5-205">В Cloud Connector версии 2,0 и более поздних командлеты Update – CcServerCertificate изменились на Update — CcServerCertificate, а командлет продления — CcCACertificate изменился на Update CcCACertificate.</span><span class="sxs-lookup"><span data-stu-id="330b5-205">In Cloud Connector version 2.0 and later, the Renew-CcServerCertificate cmdlet has changed to Update-CcServerCertificate and the Renew-CcCACertificate cmdlet has changed to Update-CcCACertificate.</span></span> 
  
    <span data-ttu-id="330b5-206">Если срок действия внутренних сертификатов, выданных серверу центрального хранилища управления, серверу-посреднику и пограничному серверу, приближается к истечению срока действия или скомпрометирован, выполните командлет Update-CcServerCertificate или Update-CcServerCertificate для продления сертификатов.</span><span class="sxs-lookup"><span data-stu-id="330b5-206">If internal certificates issued to the Central Management Store, Mediation Server, and Edge Server are near expiration or compromised, run the Renew-CcServerCertificate or Update-CcServerCertificate cmdlet to renew your certificates.</span></span>
    
    <span data-ttu-id="330b5-207">Если срок действия сертификатов центра сертификации истек, выполните командлет Update – CcCACertificate или Update – CcCACertificate, чтобы обновить сертификаты.</span><span class="sxs-lookup"><span data-stu-id="330b5-207">If certification authority certificates are near expiration, run the Renew-CcCACertificate or Update-CcCACertificate cmdlet to renew your certificates.</span></span>
    
    <span data-ttu-id="330b5-208">**Если сертификаты центра сертификации скомпрометированы и на сайте имеется только одно устройство,** выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="330b5-208">**If certification authority certificates are compromised and there is only one appliance in the site,** perform the following steps:</span></span>
    
1. <span data-ttu-id="330b5-209">Выполните командлет Enter – CcUpdate, чтобы очистить службы и перевести устройство в режим обслуживания.</span><span class="sxs-lookup"><span data-stu-id="330b5-209">Run the Enter-CcUpdate cmdlet to drain services and put the appliance in maintenance mode.</span></span>
   
   ```powershell
   Enter-CcUpdate
   ```
   
2. <span data-ttu-id="330b5-210">Выполните следующие командлеты, чтобы сбросить и создать новые сертификаты центра сертификации и все внутренние сертификаты серверов:</span><span class="sxs-lookup"><span data-stu-id="330b5-210">Run the following cmdlets to reset and create new certification authority certificates and all internal server certificates:</span></span>
    
    <span data-ttu-id="330b5-211">Для выпусков Cloud Connector до 2,0:</span><span class="sxs-lookup"><span data-stu-id="330b5-211">For Cloud Connector releases before 2.0:</span></span>
    
    ```powershell
    Reset-CcCACertificate 
    Renew-CcServerCertificate 
    Remove-CcLegacyServerCertificate 
    ```

    <span data-ttu-id="330b5-212">В случае выпуска Cloud Connector 2,0 и более поздних версий:</span><span class="sxs-lookup"><span data-stu-id="330b5-212">Or for Cloud Connector release 2.0 and later:</span></span>
    
    ```powershell
    Reset-CcCACertificate 
    Update-CcServerCertificate 
    Remove-CcLegacyServerCertificate 
    ```
    
3. <span data-ttu-id="330b5-213">Если между шлюзом и сервером-посредником используется протокол TLS, выполните командлет Export-CcRootCertificate на устройстве, а затем установите экспортированный сертификат на шлюзы PSTN.</span><span class="sxs-lookup"><span data-stu-id="330b5-213">If TLS is used between the gateway and the Mediation Server, run the Export-CcRootCertificate cmdlet from the appliance, and then install the exported certificate to your PSTN gateways.</span></span> <span data-ttu-id="330b5-214">Кроме того, может потребоваться повторная выдача сертификата на шлюзе.</span><span class="sxs-lookup"><span data-stu-id="330b5-214">You may also be required to re-issue the certificate on your gateway.</span></span>

   ```powershell
   Export-CcRootCertificate
   ```

4. <span data-ttu-id="330b5-215">Выполните командлет Exit – CcUpdate, чтобы запустить службы и выйти из режима обслуживания.</span><span class="sxs-lookup"><span data-stu-id="330b5-215">Run the Exit-CcUpdate cmdlet to start services and exit maintenance mode.</span></span>

   ```powershell
   Exit-CcUpdate
   ```


    <span data-ttu-id="330b5-216">**Если сертификаты центра сертификации скомпрометированы и на сайте имеется несколько устройств,** выполните следующие действия на каждом устройстве на сайте.</span><span class="sxs-lookup"><span data-stu-id="330b5-216">**If certification authority certificates are compromised and there are multiple appliances in the site,** perform the following sequential steps on each appliance in the site.</span></span>
    
    <span data-ttu-id="330b5-217">Корпорация Майкрософт рекомендует выполнять эти действия в непиковое время использования.</span><span class="sxs-lookup"><span data-stu-id="330b5-217">Microsoft recommends that you perform these steps during non-peak usage times.</span></span>
    
1. <span data-ttu-id="330b5-218">На первом устройстве запустите командлет Remove – CcCertificationAuthorityFile, чтобы очистить файлы резервных копий ЦС в \<SiteRoot\> каталоге.</span><span class="sxs-lookup"><span data-stu-id="330b5-218">On the first appliance, run the Remove-CcCertificationAuthorityFile cmdlet to clean up the CA backup files in the \<SiteRoot\> directory.</span></span>

     ```powershell
     Remove-CcCertificationAuthorityFile
     ```
    
2. <span data-ttu-id="330b5-219">Выполните командлет Enter – CcUpdate, чтобы сток служб и перевести каждое устройство в режим обслуживания.</span><span class="sxs-lookup"><span data-stu-id="330b5-219">Run the Enter-CcUpdate cmdlet to drain services and put each appliance in maintenance mode.</span></span>

     ```powershell
     Enter-CcUpdate
     ```
    
3. <span data-ttu-id="330b5-220">На первом устройстве выполните следующие командлеты, чтобы сбросить и создать новые сертификаты центра сертификации и все внутренние сертификаты серверов:</span><span class="sxs-lookup"><span data-stu-id="330b5-220">On the first appliance, run the following cmdlets to reset and create new certification authority certificates and all internal server certificates:</span></span>
    
     <span data-ttu-id="330b5-221">Для выпусков Cloud Connector до 2,0:</span><span class="sxs-lookup"><span data-stu-id="330b5-221">For Cloud Connector releases before 2.0:</span></span>
    
     ```powershell
     Reset-CcCACertificate
     Renew-CcServerCertificate
     Remove-CcLegacyServerCertificate 
     ```

     <span data-ttu-id="330b5-222">В случае выпуска Cloud Connector 2,0 и более поздних версий:</span><span class="sxs-lookup"><span data-stu-id="330b5-222">Or for Cloud Connector release 2.0 and later:</span></span>
    
     ```powershell
     Reset-CcCACertificate
     Update-CcServerCertificate
     Remove-CcLegacyServerCertificate 
     ```

4. <span data-ttu-id="330b5-223">На первом устройстве выполните следующий командлет, чтобы создать резервную копию файлов ЦС в \<SiteRoot\> папке.</span><span class="sxs-lookup"><span data-stu-id="330b5-223">On the first appliance, run the following cmdlet to back up the CA files to the \<SiteRoot\> folder.</span></span>
    
     ```powershell
     Backup-CcCertificationAuthority
     ```
   
5. <span data-ttu-id="330b5-224">На любом другом устройстве на том же сайте выполните следующие команды для использования файлов резервных копий ЦС, чтобы все устройства использовали один корневой сертификат, а затем запрашивают новые сертификаты.</span><span class="sxs-lookup"><span data-stu-id="330b5-224">On all other appliance's in the same site, run the following commands to consume the CA backup files, so that the appliances all use the same root certificate, and then request new certificates.</span></span> 
   
     ```powershell
     Reset-CcCACertificate
     Update-CcServerCertificate
     Remove-CcLegacyServerCertificate 
     ```
     
6. <span data-ttu-id="330b5-225">Если между шлюзом и сервером-посредником используется протокол TLS, выполните командлет Export-CcRootCertificate на любом устройстве на сайте, а затем установите экспортированный сертификат на шлюзы PSTN.</span><span class="sxs-lookup"><span data-stu-id="330b5-225">If TLS is used between the gateway and the Mediation Server, run the Export-CcRootCertificate cmdlet from any appliance in the site, and then install the exported certificate to your PSTN gateways.</span></span> <span data-ttu-id="330b5-226">Кроме того, может потребоваться повторная выдача сертификата на шлюзе.</span><span class="sxs-lookup"><span data-stu-id="330b5-226">You may also be required to re-issue the certificate on your gateway.</span></span>
  
     ```powershell
     Export-CcRootCertificate
     ```
     
7. <span data-ttu-id="330b5-227">Выполните командлет Exit – CcUpdate, чтобы запустить службы и выйти из режима обслуживания.</span><span class="sxs-lookup"><span data-stu-id="330b5-227">Run the Exit-CcUpdate cmdlet to start services and exit maintenance mode.</span></span> 

     ```powershell
     Exit-CcUpdate
     ```
    
    
- <span data-ttu-id="330b5-228">**Причина: в журнале службы управления Cloud Connector отображается следующее сообщение об ошибке: "C:\Program Files\Skype for Business Cloud Connector Едитион\манажементсервице\кцеманажементсервице.лог": CceService Error: 0: непредвиденное исключение при отправке отчета о состоянии в Online: System. Management. Automation. Кмдлетинвокатионексцептион: не удалось войти в систему пользователя \<Global Tenant Admin\> . Создайте новый объект учетных данных, убедившись, что вы использовали правильные имя пользователя и пароль. ---\>**</span><span class="sxs-lookup"><span data-stu-id="330b5-228">**Issue: You receive the following error message in the Cloud Connector Management Service Log, "C:\Program Files\Skype for Business Cloud Connector Edition\ManagementService\CceManagementService.log": CceService Error: 0 : Unexpected exception when reporting status to online: System.Management.Automation.CmdletInvocationException: Logon failed for the user \<Global Tenant Admin\>. Please create a new credential object, making sure that you have used the correct user name and password. ---\>**</span></span>
    
    <span data-ttu-id="330b5-229">**Решение:** Учетные данные глобального администратора клиента Microsoft 365 или Office 365 были изменены с момента регистрации устройства Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="330b5-229">**Resolution:** The Microsoft 365 or Office 365 global tenant admin credentials have been changed since the Cloud Connector appliance was registered.</span></span> <span data-ttu-id="330b5-230">Чтобы обновить локально хранимые учетные данные на устройстве Cloud Connector, выполните следующую команду в консоли PowerShell с правами администратора на хостном устройстве:</span><span class="sxs-lookup"><span data-stu-id="330b5-230">To update the locally stored credentials on the Cloud Connector appliance, run the following from Administrator PowerShell on the host appliance:</span></span>
    
  ```powershell
  Set-CcCredential -AccountType TenantAdmin
  ```

- <span data-ttu-id="330b5-231">**Вопрос: после изменения пароля для учетной записи сервера узла, используемой для развертывания, отображается следующее сообщение об ошибке: "ConvertTo-SecureString: ключ не является допустимым для использования в указанном состоянии". "в%ProgramFiles%\Skype для Business Cloud Connector Едитион\манажементсервице\кцеманажементсервице.лог или при запуске командлета Get-CcCredential.**</span><span class="sxs-lookup"><span data-stu-id="330b5-231">**Issue: After you change the password for the host server account you used for the deployment, you receive the following error message: "ConvertTo-SecureString : Key not valid for use in specified state." in %ProgramFiles%\Skype for Business Cloud Connector Edition\ManagementService\CceManagementService.log or while running the Get-CcCredential cmdlet.**</span></span>
    
    <span data-ttu-id="330b5-232">**Решение:** Все учетные данные Cloud Connector хранятся в следующем файле: "%SystemDrive%\Programdata\Cloudconnector\credentials. \<CurrentUser\> . XML ".</span><span class="sxs-lookup"><span data-stu-id="330b5-232">**Resolution:** All Cloud Connector credentials are stored in the following file: "%SystemDrive%\Programdata\Cloudconnector\credentials.\<CurrentUser\>.xml".</span></span> <span data-ttu-id="330b5-233">При изменении пароля на сервере узла необходимо обновить локально хранимые учетные данные.</span><span class="sxs-lookup"><span data-stu-id="330b5-233">When the password on the host server changes, you will need to update the locally stored credentials.</span></span>
    
    <span data-ttu-id="330b5-234">**Если вы используете Cloud Connector версии 1.4.2,** повторно создайте все пароли Cloud Connector, выполнив следующие действия:</span><span class="sxs-lookup"><span data-stu-id="330b5-234">**If you are running Cloud Connector version 1.4.2,** regenerate all Cloud Connector passwords by following these steps:</span></span>
    
  1. <span data-ttu-id="330b5-235">Перезапустите сервер узла.</span><span class="sxs-lookup"><span data-stu-id="330b5-235">Restart the host server.</span></span>
    
  2. <span data-ttu-id="330b5-236">Удалите следующий файл: "%SystemDrive%\Programdata\Cloudconnector\credentials. \<CurrentUser\> . XML ".</span><span class="sxs-lookup"><span data-stu-id="330b5-236">Delete the following file: "%SystemDrive%\Programdata\Cloudconnector\credentials.\<CurrentUser\>.xml".</span></span>
    
  3. <span data-ttu-id="330b5-237">Запустите консоль PowerShell от имени администратора, а затем выполните команду "Register – CcAppliance — Local", чтобы повторно ввести пароли, указанные в описании.</span><span class="sxs-lookup"><span data-stu-id="330b5-237">Launch a PowerShell console as administrator, and then run "Register-CcAppliance -Local" to re-enter the passwords following the description.</span></span> <span data-ttu-id="330b5-238">Введите те же пароли, которые были введены ранее для развертывания Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="330b5-238">Enter the same passwords you entered before for the Cloud Connector deployment.</span></span>
    
     <span data-ttu-id="330b5-239">**Если вы используете Cloud Connector версии 2,0 или более поздней,** повторно создайте все пароли Cloud Connector, выполнив следующие действия:</span><span class="sxs-lookup"><span data-stu-id="330b5-239">**If you are running Cloud Connector version 2.0 or later,** regenerate all Cloud Connector passwords by following these steps:</span></span>
    
  4. <span data-ttu-id="330b5-240">Перезапустите сервер узла.</span><span class="sxs-lookup"><span data-stu-id="330b5-240">Restart the host server.</span></span>
    
  5. <span data-ttu-id="330b5-241">Удалите следующий файл: "%SystemDrive%\Programdata\Cloudconnector\credentials. \<CurrentUser\> . XML ".</span><span class="sxs-lookup"><span data-stu-id="330b5-241">Delete the following file: "%SystemDrive%\Programdata\Cloudconnector\credentials.\<CurrentUser\>.xml" .</span></span>
    
  6. <span data-ttu-id="330b5-242">Запустите консоль PowerShell от имени администратора, а затем выполните команду "Register – CcAppliance — Local", чтобы повторно ввести пароли, указанные в описании.</span><span class="sxs-lookup"><span data-stu-id="330b5-242">Launch a PowerShell console as administrator, and then run "Register-CcAppliance -Local" to re-enter the passwords following the description.</span></span> 
    
     <span data-ttu-id="330b5-243">Если файл кэшированного пароля был создан с помощью 1.4.2 Cloud Connector версии, при появлении соответствующего запроса используйте пароль VMAdmin для пароля CceService.</span><span class="sxs-lookup"><span data-stu-id="330b5-243">If the cached password file was generated with Cloud Connector version 1.4.2, use the VMAdmin password for the CceService password when prompted.</span></span> <span data-ttu-id="330b5-244">Введите тот же пароль, который вы ввели перед развертыванием Cloud Connector для всех остальных учетных записей.</span><span class="sxs-lookup"><span data-stu-id="330b5-244">Enter the same password you entered before for the Cloud Connector deployment for all other accounts.</span></span>
    
     <span data-ttu-id="330b5-245">Если файл кэшированного пароля был создан с помощью Cloud Connector версии 1.4.2, а пароли DomainAdmin и VMAdmin отличаются, необходимо выполнить следующие действия:</span><span class="sxs-lookup"><span data-stu-id="330b5-245">If the cached password file was generated with Cloud Connector version 1.4.2 and the DomainAdmin and VMAdmin passwords are different, you must perform the following steps:</span></span>
    
  7. <span data-ttu-id="330b5-246">Выполните командлет Set – CcCredential – AccountType DomainAdmin, как показано ниже.</span><span class="sxs-lookup"><span data-stu-id="330b5-246">Run Set-CcCredential -AccountType DomainAdmin as follows:</span></span>
    
  8. <span data-ttu-id="330b5-247">При запросе учетных данных старой учетной записи введите учетные данные, которые использовались для пароля CceService.</span><span class="sxs-lookup"><span data-stu-id="330b5-247">When prompted for the old account credential, enter the credential you used for the CceService password.</span></span>
    
  9. <span data-ttu-id="330b5-248">При запросе учетных данных новой учетной записи введите пароль для пароля DomainAdmin, который вы использовали ранее.</span><span class="sxs-lookup"><span data-stu-id="330b5-248">When prompted for the new account credential, enter the password for the DomainAdmin password you used before.</span></span>
    
     <span data-ttu-id="330b5-249">Если файл кэшированного пароля был создан с помощью Cloud Connector версии 2,0 или более поздней версии, по умолчанию VmAdmin и DomainAdmin используют тот же пароль, что и в CceService.</span><span class="sxs-lookup"><span data-stu-id="330b5-249">If the cached password file was generated with Cloud Connector version 2.0 or later, by default, VmAdmin and DomainAdmin use the same password as CceService.</span></span> <span data-ttu-id="330b5-250">Если вы изменили пароли DomainAdmin и VMAdmin, необходимо выполнить следующие действия:</span><span class="sxs-lookup"><span data-stu-id="330b5-250">If you changed the DomainAdmin and VMAdmin passwords, you must perform the following steps:</span></span>
    
  10. <span data-ttu-id="330b5-251">Выполните командлет Set – CcCredential – AccountType DomainAdmin, как показано ниже.</span><span class="sxs-lookup"><span data-stu-id="330b5-251">Run Set-CcCredential -AccountType DomainAdmin as follows:</span></span>
    
       1. <span data-ttu-id="330b5-252">При запросе учетных данных старой учетной записи введите учетные данные, которые использовались для пароля CceService</span><span class="sxs-lookup"><span data-stu-id="330b5-252">When prompted for the old account credential, enter the credential you used for the CceService password</span></span>
    
       2. <span data-ttu-id="330b5-253">При запросе учетных данных новой учетной записи введите пароль для пароля DomainAdmin, который вы использовали ранее.</span><span class="sxs-lookup"><span data-stu-id="330b5-253">When prompted for the new account credential, enter the password for the DomainAdmin password you used before.</span></span>
    
  11. <span data-ttu-id="330b5-254">Выполните командлет Set – CcCredential – AccountType VmAdmin, как показано ниже.</span><span class="sxs-lookup"><span data-stu-id="330b5-254">Run Set-CcCredential -AccountType VmAdmin as follows:</span></span>
    
       1. <span data-ttu-id="330b5-255">При запросе учетных данных старой учетной записи введите учетные данные, которые использовались для пароля CceService</span><span class="sxs-lookup"><span data-stu-id="330b5-255">When prompted for the old account credential, enter the credential you used for the CceService password</span></span>
    
       2. <span data-ttu-id="330b5-256">При запросе учетных данных новой учетной записи введите пароль для пароля VmAdmin, который вы использовали ранее.</span><span class="sxs-lookup"><span data-stu-id="330b5-256">When prompted for the new account credential, enter the password for the VmAdmin password you used before.</span></span> 
    
- <span data-ttu-id="330b5-257">**Проблема: с помощью Cloud Connector версии 2,1 и более поздних версий при запуске командлета Register – CcAppliance или других командлетов на устройстве отображается сообщение об ошибке: "для каждого объекта: не удается найти свойство ' Common ' для этого объекта. Убедитесь, что свойство существует. В папке C:\Program Files\WindowsPowerShell\Modules\CloudConnector\Internal\MtHostCommon.ps1:681 char: 14 "**</span><span class="sxs-lookup"><span data-stu-id="330b5-257">**Issue: With Cloud Connector version 2.1 and later, when running Register-CcAppliance or other cmdlets on the appliance, you receive an error message such as: "For Each-Object : The property 'Common' cannot be found on this object. Verify that the property exists. At C:\Program Files\WindowsPowerShell\Modules\CloudConnector\Internal\MtHostCommon.ps1:681 char:14"**</span></span>
    
    <span data-ttu-id="330b5-258">**Решение:** Для Cloud Connector 2,1 и более поздних версий требуется платформа .NET Framework 4.6.1 или более поздняя версия.</span><span class="sxs-lookup"><span data-stu-id="330b5-258">**Resolution:** Cloud Connector 2.1 and later requires .NET Framework 4.6.1 or later.</span></span> <span data-ttu-id="330b5-259">Обновите .NET Framework на устройстве с помощью 4.6.1 или более поздней версии, а затем снова запустите командлеты.</span><span class="sxs-lookup"><span data-stu-id="330b5-259">Please update .NET Framework on the appliance to version 4.6.1 or later and run the cmdlet(s) again.</span></span>

- <span data-ttu-id="330b5-260">**Вопрос: с помощью Cloud Connector Edition 2,1 при запуске Install-CcAppliance появляется следующее сообщение об ошибке: "не удалось установить новый экземпляр, ошибка: невозможно задать" состояние ", так как только строки можно использовать в качестве значений для задания свойств XmlNode"**</span><span class="sxs-lookup"><span data-stu-id="330b5-260">**Issue: With Cloud Connector Edition 2.1, when running Install-CcAppliance, you receive an error message such as: "Failed to install new instance with error: Cannot set "State" because only strings can be used as values to set XmlNode properties"**</span></span>

   <span data-ttu-id="330b5-261">**Решение:** В разделе [Common] (Cloudconnector.ini) в разделе [Common] добавьте конфигурацию "State", как указано ниже: CountryCode = US штат = WA City = Redmond</span><span class="sxs-lookup"><span data-stu-id="330b5-261">**Resolution:** In Cloudconnector.ini, under the [Common] section, please add the “State” config as below:  CountryCode=US  State=WA  City=Redmond</span></span>

   <span data-ttu-id="330b5-262">Строка State не является обязательной для значения, но строка "State" не может быть удалена из файла Cloudconnector.ini.</span><span class="sxs-lookup"><span data-stu-id="330b5-262">It is not mandatory for the "State" line to have value, however the "State" line cannot be removed from the Cloudconnector.ini file.</span></span>

- <span data-ttu-id="330b5-263">**Ошибка: получено следующее сообщение об ошибке: "Dismount — Виндовсимаже: Dismount – Виндовсимаже Failed. Код ошибки = 0xc1550115 "при установке или обновлении Cloud Connector Edition.**</span><span class="sxs-lookup"><span data-stu-id="330b5-263">**Issue: You receive the following error message "Dismount-WindowsImage : Dismount-WindowsImage failed. Error code = 0xc1550115" when installing or upgrading Cloud Connector Edition.**</span></span>
    
    <span data-ttu-id="330b5-264">**Решение:** Запустите консоль PowerShell от имени администратора, запустите "DISM-Cleanup-WIM".</span><span class="sxs-lookup"><span data-stu-id="330b5-264">**Resolution:** Launch a PowerShell console as administrator, run "DISM -Cleanup-Wim'".</span></span> <span data-ttu-id="330b5-265">При этом будут очищены все невыполненные изображения.</span><span class="sxs-lookup"><span data-stu-id="330b5-265">This will clean up all troubled images.</span></span> <span data-ttu-id="330b5-266">Повторно запустите командлет Install – CcAppliance или дождитесь автоматического обновления BITS.</span><span class="sxs-lookup"><span data-stu-id="330b5-266">Run Install-CcAppliance again or wait for the bits to automatically upgrade.</span></span>
    
- <span data-ttu-id="330b5-267">**Ошибка: не удается развернуть первое устройство Cloud Connector в среде высокой доступности**</span><span class="sxs-lookup"><span data-stu-id="330b5-267">**Issue: Deployment of the first Cloud Connector appliance in an HA environment fails**</span></span>
    
    <span data-ttu-id="330b5-268">**Решение:** Действия, которые необходимо выполнить, зависят от причины сбоя развертывания:</span><span class="sxs-lookup"><span data-stu-id="330b5-268">**Resolution:** The steps you take depend on the reason the deployment failed:</span></span>
    
  - <span data-ttu-id="330b5-269">Если первое устройство Cloud Connector завершается с ошибкой и вы не можете определить причину сбоя, необходимо установить устройство еще раз до успешного развертывания, а затем установить другие устройства.</span><span class="sxs-lookup"><span data-stu-id="330b5-269">If the first Cloud Connector appliance fails and you cannot determine the reason for the failure, you must install the appliance again until the deployment is successful, and then install the other appliances.</span></span>
    
  - <span data-ttu-id="330b5-270">Если первое устройство Cloud Connector потерпит незначительную проблему, например проблему с внешним сертификатом, вы можете устранить проблему без повторной установки устройства.</span><span class="sxs-lookup"><span data-stu-id="330b5-270">If the first Cloud Connector appliance fails with a minor issue, such as an external certificate issue, you might be able to fix the problem without re-installing the appliance.</span></span> <span data-ttu-id="330b5-271">Затем вы можете использовать удаленную оболочку PowerShell клиента, чтобы пометить развертывание как успешное, как показано ниже.</span><span class="sxs-lookup"><span data-stu-id="330b5-271">You can then use tenant remote PowerShell to mark the deployment as successful as follows.</span></span> <span data-ttu-id="330b5-272">(Вы также можете выполнить следующие действия, если первое развертывание прошло успешно, но по какой-либо причине облачному соединителю не удалось сообщить о развертывании как успешное.)</span><span class="sxs-lookup"><span data-stu-id="330b5-272">(You can also use the following steps if the first deployment was successful, but, for some reason, Cloud Connector fails to report the deployment as a success.)</span></span>
    
  - <span data-ttu-id="330b5-273">Чтобы получить идентификатор (GUID) первого устройства Cloud Connector, выполните командлет Get-Кшибридпстнапплианце.</span><span class="sxs-lookup"><span data-stu-id="330b5-273">To get the Identity (GUID) of the first Cloud Connector appliance, run the Get-CsHybridPSTNAppliance cmdlet.</span></span>
    
  - <span data-ttu-id="330b5-274">Чтобы пометить устройство как успешно развернутое, выполните командлет Set – Кскцеапплианцедеплойментстатус следующим образом:</span><span class="sxs-lookup"><span data-stu-id="330b5-274">To mark the appliance as successfully deployed, run the Set-CsCceApplianceDeploymentStatus as follows:</span></span>
    
  ```powershell
  Set-CsCceApplianceDeploymentStatus -Identity <Appliance Identity GUID> -Action Deploy -Status Finished
  ```

- <span data-ttu-id="330b5-275">**Вопрос: необходимо проверить наличие и установить обновления Windows вручную на сервере узла или виртуальных машинах.**</span><span class="sxs-lookup"><span data-stu-id="330b5-275">**Issue: You need to check for and install Windows updates manually on the host server or virtual machines.**</span></span>
    
   <span data-ttu-id="330b5-276">**Решение:** Мы рекомендуем использовать преимущества автоматических обновлений ОС, предоставляемых Skype для бизнеса Cloud Connector Edition.</span><span class="sxs-lookup"><span data-stu-id="330b5-276">**Resolution:** We recommend that you take advantage of automated OS updates provided by Skype for Business Cloud Connector Edition.</span></span> <span data-ttu-id="330b5-277">После регистрации устройства для управления через Интернет и включения автоматического обновления ОС сервер узла и виртуальные машины будут автоматически проверять и устанавливать обновления Windows в соответствии с параметрами окна "обновление операционной системы".</span><span class="sxs-lookup"><span data-stu-id="330b5-277">After an appliance is registered for online management and auto OS update is enabled, the host server and virtual machines will check and install Windows Updates automatically according to the OS update time window settings.</span></span>
    
   <span data-ttu-id="330b5-278">Если вам нужно проверить и установить обновления Windows вручную, выполните действия, описанные в этом разделе, которые относятся к типу развертывания.</span><span class="sxs-lookup"><span data-stu-id="330b5-278">If you need to check for and install Windows Updates manually, follow the steps in this section that apply to your type of deployment.</span></span> <span data-ttu-id="330b5-279">Необходимо запланировать обновление как сервера узла, так и виртуальных машин, работающих на нем, чтобы минимизировать время, необходимое для обновления.</span><span class="sxs-lookup"><span data-stu-id="330b5-279">You should plan on updating both the host server and the virtual machines running on it at the same time to minimize the amount of down time necessary for the updates.</span></span>
    
   <span data-ttu-id="330b5-280">При желании вы можете использовать сервер служб Windows Server Update Services (WSUS) для предоставления обновлений для серверов Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="330b5-280">If you prefer, you can use a Windows Server Update Services (WSUS) server to provide updates to Cloud Connector servers.</span></span> <span data-ttu-id="330b5-281">Необходимо убедиться, что обновление Windows **не** устанавливается автоматически.</span><span class="sxs-lookup"><span data-stu-id="330b5-281">Just be sure to configure the Windows Update to **not** install automatically.</span></span>
    
   <span data-ttu-id="330b5-282">Сведения о том, как вручную обновить развертывание Cloud Connector, можно найти в следующем разделе.</span><span class="sxs-lookup"><span data-stu-id="330b5-282">For information about how to manually update your Cloud Connector deployment, see the following section.</span></span>
    
- <span data-ttu-id="330b5-283">**Вопрос: при обновлении Cloud Connector до новой сборки командлеты Cloud Connector не обновляются.**</span><span class="sxs-lookup"><span data-stu-id="330b5-283">**Issue: When Cloud Connector updates to a new build, Cloud Connector cmdlets are not updated.**</span></span> <span data-ttu-id="330b5-284">Это может произойти, если окно PowerShell остается открытым при выполнении автоматического обновления.</span><span class="sxs-lookup"><span data-stu-id="330b5-284">This sometimes happens if a PowerShell window is left open when automatic update occurs.</span></span>
    
  <span data-ttu-id="330b5-285">**Решение:** Для загрузки обновленных командлетов можно выполнить одно из следующих действий:</span><span class="sxs-lookup"><span data-stu-id="330b5-285">**Resolution:** To load the updated cmdlets, you can do either of the following steps:</span></span>
    
   - <span data-ttu-id="330b5-286">Закройте PowerShell на устройстве Cloud Connector, а затем снова откройте PowerShell.</span><span class="sxs-lookup"><span data-stu-id="330b5-286">Close PowerShell on the Cloud Connector appliance, and then reopen PowerShell.</span></span>
    
     - <span data-ttu-id="330b5-287">Можно также выполнить командлет Import – Module CloudConnector — Force.</span><span class="sxs-lookup"><span data-stu-id="330b5-287">Or, you can run Import-Module CloudConnector -Force.</span></span> 
 
-   <span data-ttu-id="330b5-288">**Ошибка: "термин Stop-CsWindowsService" не распознается как имя командлета, функции, файла скрипта или программной программы. "ошибка при попытке выполнить командлет Enter-CcUpdate.**</span><span class="sxs-lookup"><span data-stu-id="330b5-288">**Issue: "The term 'Stop-CsWindowsService' is not recognized as the name of a cmdlet, function, script file, or operable program." error when attempting to run Enter-CcUpdate cmdlet.**</span></span>

    <span data-ttu-id="330b5-289">**Решение:** Удалите файл $HOME \Аппдата\локал\микрософт\виндовс\повершелл\модулеаналисискаче.</span><span class="sxs-lookup"><span data-stu-id="330b5-289">**Resolution:** Delete the $HOME\AppData\Local\Microsoft\Windows\PowerShell\ModuleAnalysisCache file.</span></span>
<span data-ttu-id="330b5-290">PowerShell создает этот файл в виде кэша командлетов из найденных модулей, чтобы не пришлось повторно анализировать все модули каждый раз, так как это приведет к значительному снижению производительности.</span><span class="sxs-lookup"><span data-stu-id="330b5-290">PowerShell creates this file as a cache of cmdlets from modules that it finds so that it doesn’t have to re-analyze all the modules each time as that would make things really slow.</span></span> <span data-ttu-id="330b5-291">Скорее всего, было вызвано повреждение файлов, предоставилее недостоверные результаты в PowerShell при чтении из кэша.</span><span class="sxs-lookup"><span data-stu-id="330b5-291">Most likely, there was some file corruption that provided misleading results to PowerShell when it was reading back from that cache.</span></span>

-   <span data-ttu-id="330b5-292">**Ошибка: "Import-Module CloudConnector" генерирует ошибку "Import-Module: указанный модуль" CloudConnector "не был загружен, так как в каком-либо из каталогов модулей не был найден допустимый файл модуля"**</span><span class="sxs-lookup"><span data-stu-id="330b5-292">**Issue: “Import-Module CloudConnector” generates error “Import-Module: The specified module “CloudConnector” was not loaded because no valid module file was found in any module directory”**</span></span>

    <span data-ttu-id="330b5-293">**Решение.**</span><span class="sxs-lookup"><span data-stu-id="330b5-293">**Resolution:**</span></span>
    - <span data-ttu-id="330b5-294">Проверка того, что в папке c:\Program Филес\виндовсповершелл\модулес существует модуль CloudConnector</span><span class="sxs-lookup"><span data-stu-id="330b5-294">Validate that indeed the CloudConnector module exists under c:\Program Files\WindowsPowerShell\Modules</span></span>
    
    - <span data-ttu-id="330b5-295">После проверки того, что модуль CloudConnector существует в этом расположении, переменная среды PSModulePath, в которой хранится путь к расположениям модулей, может быть изменена:</span><span class="sxs-lookup"><span data-stu-id="330b5-295">After validating that CloudConnector module exists under this location, the PSModulePath environment variable storing the path to the locations of the modules can be changed:</span></span>
    
     <span data-ttu-id="330b5-296">а)</span><span class="sxs-lookup"><span data-stu-id="330b5-296">a.</span></span> <span data-ttu-id="330b5-297">Временное изменение: запустите PowerShell от имени администратора и выполните следующую команду: $env:P Смодулепас = $env:P Смодулепас + "; C:\Program Филес\виндовсповершелл\модулес\"</span><span class="sxs-lookup"><span data-stu-id="330b5-297">Temporary change: Start Powershell as an Administrator and run the following command: $env:PSModulePath = $env:PSModulePath + ";C:\Program Files\WindowsPowerShell\Modules\"</span></span>
        
     <span data-ttu-id="330b5-298">б)</span><span class="sxs-lookup"><span data-stu-id="330b5-298">b.</span></span> <span data-ttu-id="330b5-299">Для сохранения изменений запустите PowerShell от имени администратора и выполните следующие команды, по одному: $CurrentValue = [Environment]:: Жетенвиронментвариабле ("PSModulePath", "Machine") Сетенвиронментвариабле ("PSModulePath", "Machine") ("", $CurrentValue + "; C:\Program Филес\виндовсповершелл\модулес "," Machine ")</span><span class="sxs-lookup"><span data-stu-id="330b5-299">For persistent change, Start PowerShell as an Administrator and run the following commands, one by one: $CurrentValue = [Environment]::GetEnvironmentVariable("PSModulePath", "Machine") SetEnvironmentVariable("PSModulePath", $CurrentValue + "; C:\Program Files\WindowsPowerShell\Modules", "Machine")</span></span>

    
## <a name="install-windows-updates-manually"></a><span data-ttu-id="330b5-300">Установка обновлений Windows вручную</span><span class="sxs-lookup"><span data-stu-id="330b5-300">Install Windows updates manually</span></span>

<span data-ttu-id="330b5-301">Если вы не хотите использовать автоматические обновления в своей среде, выполните следующие действия, чтобы вручную проверить и применить обновления Windows.</span><span class="sxs-lookup"><span data-stu-id="330b5-301">If you do not want to use automatic updates in your environment, follow these steps to manually check for and apply Windows updates.</span></span> <span data-ttu-id="330b5-302">Для проверки и установки обновлений Windows может потребоваться перезагрузка сервера.</span><span class="sxs-lookup"><span data-stu-id="330b5-302">Checking for and installing Windows updates may require a server restart.</span></span> <span data-ttu-id="330b5-303">При перезапуске сервера узла пользователи не смогут использовать Cloud Connector для размещения или приема звонков.</span><span class="sxs-lookup"><span data-stu-id="330b5-303">When a host server is restarting, users will not be able to use Cloud Connector to place or receive calls.</span></span> <span data-ttu-id="330b5-304">Вы можете вручную проверять наличие обновлений и устанавливать их, чтобы контролировать, когда они происходят, а затем перезапускать компьютеры при необходимости, чтобы избежать перерывов в работе служб.</span><span class="sxs-lookup"><span data-stu-id="330b5-304">You can manually check for and install updates to control when the updates take place, and then restart the machines as needed during times you choose to avoid disruption of services.</span></span>
  
<span data-ttu-id="330b5-305">Чтобы проверить наличие обновлений вручную, подключитесь к каждому серверу узла и откройте **Панель управления**.</span><span class="sxs-lookup"><span data-stu-id="330b5-305">To manually check for updates, connect to each host server and open the **Control Panel**.</span></span> <span data-ttu-id="330b5-306">Выберите **система и безопасность \> Windows Update**, а затем — Управление обновлениями и перезапусками сервера в соответствии с вашей средой.</span><span class="sxs-lookup"><span data-stu-id="330b5-306">Select **System and Security \>Windows Update**, and then manage the updates and server restarts as appropriate for your environment.</span></span>
  
- <span data-ttu-id="330b5-307">Если на сайте только одно устройство, подключитесь к каждой виртуальной машине и откройте **Панель управления**.</span><span class="sxs-lookup"><span data-stu-id="330b5-307">If there is only one appliance in the site, connect to each virtual machine and open the **Control Panel**.</span></span> <span data-ttu-id="330b5-308">Выберите **система и безопасность \> Windows Update**, а затем настройте обновления и перезапускать сервер соответствующим образом.</span><span class="sxs-lookup"><span data-stu-id="330b5-308">Select **System and Security \>Windows Update**, and then configure the updates and server restarts as appropriate.</span></span>
    
- <span data-ttu-id="330b5-309">Если на сайте несколько устройств, то во время обновлений пользователи не смогут получить доступ к обновляемому и перезапускаемому экземпляру.</span><span class="sxs-lookup"><span data-stu-id="330b5-309">If there are more than one appliance in the site, the instance being updated and restarted cannot be accessed by users during the updates.</span></span> <span data-ttu-id="330b5-310">Пользователи будут подключаться к другим экземплярам в развертывании до тех пор, пока все виртуальные машины и все службы Skype для бизнеса не будут запущены на виртуальных машинах после завершения обновления.</span><span class="sxs-lookup"><span data-stu-id="330b5-310">Users will connect to other instances in the deployment until all virtual machines and all Skype for Business services start on the virtual machines after the updates are completed.</span></span> <span data-ttu-id="330b5-311">Чтобы избежать возможного перерыва в обслуживании, можно удалить экземпляр из HA при применении обновлений, а затем восстановить его по завершении.</span><span class="sxs-lookup"><span data-stu-id="330b5-311">To avoid any potential disruption to service, you can remove the instance from HA while you apply the updates, and then restore it when complete.</span></span> <span data-ttu-id="330b5-312">Для этого:</span><span class="sxs-lookup"><span data-stu-id="330b5-312">To do so:</span></span>
    
1. <span data-ttu-id="330b5-313">На каждом сервере узла откройте консоль PowerShell от имени администратора.</span><span class="sxs-lookup"><span data-stu-id="330b5-313">On each host server, open a PowerShell console as administrator.</span></span>
    
2. <span data-ttu-id="330b5-314">Удалите экземпляр из HA с помощью следующего командлета:</span><span class="sxs-lookup"><span data-stu-id="330b5-314">Remove the instance from HA with the following cmdlet:</span></span>
    
   ```powershell
   Enter-CcUpdate
   ```

3. 
    
    <span data-ttu-id="330b5-315">Выполните действия для одного экземпляра, чтобы вручную применить обновления и перезапустить виртуальную машину.</span><span class="sxs-lookup"><span data-stu-id="330b5-315">Follow the steps for a single instance to manually apply the updates and restart the virtual machine.</span></span>
    
4. <span data-ttu-id="330b5-316">Установите для экземпляра значение HA с помощью следующего командлета:</span><span class="sxs-lookup"><span data-stu-id="330b5-316">Set the instance back to HA with the following cmdlet:</span></span>
    
   ```powershell
   Exit-CcUpdate
   ```

<span data-ttu-id="330b5-317">Для развертываний с несколькими сайтами выполните действия для отдельного сайта для каждого сайта в развертывании, применяя обновления к одному сайту за раз.</span><span class="sxs-lookup"><span data-stu-id="330b5-317">For multi-site deployments, follow the steps for a single site for each site in the deployment, applying updates to one site at a time.</span></span>
  
## <a name="tips-when-installing-anti-virus-software-on-the-cloud-connector-host-machine"></a><span data-ttu-id="330b5-318">Советы по установке антивирусного программного обеспечения на хостном компьютере Cloud Connector</span><span class="sxs-lookup"><span data-stu-id="330b5-318">Tips when installing anti-virus software on the Cloud Connector host machine</span></span>

<span data-ttu-id="330b5-319">Если необходимо установить антивирусную программу на хост машины Cloud Connector, необходимо добавить следующие исключения:</span><span class="sxs-lookup"><span data-stu-id="330b5-319">If you need to install anti-virus software on the Cloud Connector host machine, you need to add the following exclusions:</span></span>
  
- <span data-ttu-id="330b5-320">Локальный каталог устройств на каждом компьютере.</span><span class="sxs-lookup"><span data-stu-id="330b5-320">Local Appliance Directory on each machine.</span></span>
    
- <span data-ttu-id="330b5-321">Каталог удаленных сайтов на каждом компьютере.</span><span class="sxs-lookup"><span data-stu-id="330b5-321">Remote Site Directory on each machine.</span></span>
    
- <span data-ttu-id="330b5-322">Каталог локального сайта на компьютере содержит корневую папку общего сайта.</span><span class="sxs-lookup"><span data-stu-id="330b5-322">Local Site Directory on the machine hosts the shared site root folder.</span></span>
    
- <span data-ttu-id="330b5-323">%ProgramFiles%\Skype для бизнеса Cloud Connector Edition</span><span class="sxs-lookup"><span data-stu-id="330b5-323">%ProgramFiles%\Skype for Business Cloud Connector Edition</span></span>
    
- <span data-ttu-id="330b5-324">%аллусерспрофиле%\клаудконнектор</span><span class="sxs-lookup"><span data-stu-id="330b5-324">%ALLUSERSPROFILE%\CloudConnector</span></span>
    
- <span data-ttu-id="330b5-325">%програмфилес%\виндовсповершелл\модулес\клаудконнектор</span><span class="sxs-lookup"><span data-stu-id="330b5-325">%ProgramFiles%\WindowsPowerShell\Modules\CloudConnector</span></span>
    
- <span data-ttu-id="330b5-326">Microsoft.Rtc.CCE.ManagementService.exe процесса.</span><span class="sxs-lookup"><span data-stu-id="330b5-326">The process Microsoft.Rtc.CCE.ManagementService.exe.</span></span>
