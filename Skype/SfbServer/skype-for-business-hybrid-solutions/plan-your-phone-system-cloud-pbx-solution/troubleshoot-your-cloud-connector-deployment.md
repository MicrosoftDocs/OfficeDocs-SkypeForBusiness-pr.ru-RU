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
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: e6cf58cc-dbd9-4f35-a51a-3e2fea71b5a5
description: Устранение неполадок при развертывании облачного соединителя.
ms.openlocfilehash: 3edc67d5887c21543e4cbb01a6057a0c657e95e3
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/09/2020
ms.locfileid: "41002079"
---
# <a name="troubleshoot-your-cloud-connector-deployment"></a><span data-ttu-id="9b870-103">Устранение неполадок с развертыванием Cloud Connector</span><span class="sxs-lookup"><span data-stu-id="9b870-103">Troubleshoot your Cloud Connector deployment</span></span>
 
<span data-ttu-id="9b870-104">Устранение неполадок при развертывании облачного соединителя.</span><span class="sxs-lookup"><span data-stu-id="9b870-104">Troubleshoot your Cloud Connector Edition deployment.</span></span>
  
<span data-ttu-id="9b870-p101">В этом разделе описываются решения распространенных проблем, связанных с развертываниями Cloud Connector Edition. Если вы сталкиваетесь с проблемами при выполнении и приеме звонков через телефонную сеть общедоступного пользования (ТСОП), ознакомьтесь с возможными решениями, которые приводятся в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="9b870-p101">This topic describes solutions to common issues with Cloud Connector Edition deployments. If you are experiencing issues with calls to and from the Public Switched Telephone Network (PSTN), you can investigate by following the solutions described in this topic.</span></span>
  
<span data-ttu-id="9b870-107">Облачный соединитель предоставляет встроенные механизмы для автоматического устранения некоторых проблем.</span><span class="sxs-lookup"><span data-stu-id="9b870-107">Cloud Connector provides built-in mechanisms for automatically resolving some issues.</span></span> <span data-ttu-id="9b870-108">Процесс автоматического обнаружения выявляет возможные проблемы с управляющими устройствами облачного соединителя, и, если это возможно, предпринимает меры для устранения этих проблем без необходимости вмешательства администратора.</span><span class="sxs-lookup"><span data-stu-id="9b870-108">An automatic detection process looks for potential issues with the Cloud Connector appliances, and, if possible, takes corrective action to resolve those issues without the need for administrator intervention.</span></span> <span data-ttu-id="9b870-109">Процесс обнаружения выполняется следующим образом.</span><span class="sxs-lookup"><span data-stu-id="9b870-109">The detection process works as follows:</span></span>
  
- <span data-ttu-id="9b870-110">**Последовательность обнаружения:** Служба управления облачным соединителем запускает процесс каждые 60 секунд, чтобы определить, не работает ли устройство.</span><span class="sxs-lookup"><span data-stu-id="9b870-110">**Detection sequence:** The Cloud Connector Management service runs a process every 60 seconds for detecting whether an appliance is down.</span></span> <span data-ttu-id="9b870-111">В облаке соединителя версии 2,0 и более поздних процесс обнаружения использует коммутатор в корпоративной сети Skype для бизнеса для создания подключений PowerShell к облачным соединительным машинам; для версий, предшествующих 2,0, процесс обнаружения использует ключ управления облачным соединителем.</span><span class="sxs-lookup"><span data-stu-id="9b870-111">In Cloud Connector version 2.0 and later, the detection process uses the Skype for Business Corpnet switch for making PowerShell connections to the Cloud Connector machines; for versions previous to 2.0, the detection process uses the Cloud Connector management switch.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="9b870-112">Чтобы автоматическое восстановление прошло успешно, между узлом и виртуальными машинами должно быть доступно сетевое подключение на коммутаторе сети узла.</span><span class="sxs-lookup"><span data-stu-id="9b870-112">For automatic recovery to succeed, there must be network connectivity between the host and virtual machines over the host network switch.</span></span> <span data-ttu-id="9b870-113">Убедитесь в том, что проверка подключения к сети выполнена, чтобы убедиться, что автоматическое обнаружение и восстановление может выполняться успешно.</span><span class="sxs-lookup"><span data-stu-id="9b870-113">Be sure to check network connectivity to ensure that automatic detection and recovery can succeed.</span></span> 
  
- <span data-ttu-id="9b870-114">**Наблюдение за:** Следующие службы отслеживаются в облаке соединителя версии 2,0 и более поздних:</span><span class="sxs-lookup"><span data-stu-id="9b870-114">**Monitoring:** The following services are monitored in Cloud Connector version 2.0 and later:</span></span>
    
  - <span data-ttu-id="9b870-115">Виртуальные машины не подключены к облачному соединителю для корпоративных и виртуальных коммутаторов Интернета</span><span class="sxs-lookup"><span data-stu-id="9b870-115">Virtual Machines are not connected to the Cloud Connector Corporate or Internet virtual switches</span></span>
    
  - <span data-ttu-id="9b870-116">Виртуальные машины находятся в состоянии "сохранено" или "остановлено"</span><span class="sxs-lookup"><span data-stu-id="9b870-116">Virtual Machines are in a saved or stopped status</span></span>
    
  - <span data-ttu-id="9b870-117">Службы сервера централизованного управления: РЕПЛИКа, образец</span><span class="sxs-lookup"><span data-stu-id="9b870-117">Central Management Server services: REPLICA, MASTER</span></span>
    
  - <span data-ttu-id="9b870-118">Сервер служб исправлений: РЕПЛИКа, РТКСРВ и МЕДСВК</span><span class="sxs-lookup"><span data-stu-id="9b870-118">Mediation Server services: REPLICA, RTCSRV and MEDSVC</span></span>
    
  - <span data-ttu-id="9b870-119">Службы пограничного сервера: РЕПЛИКа, РТКСРВ, РТКДАТАПРОКСИ, РТКМРАУС, РТКМЕДИАРЕЛАЙ</span><span class="sxs-lookup"><span data-stu-id="9b870-119">Edge Server services: REPLICA, RTCSRV, RTCDATAPROXY, RTCMRAUTH, RTCMEDIARELAY</span></span>
    
  - <span data-ttu-id="9b870-120">Правила брандмауэра для входящего трафика отключены для CS РТКСРВ на пограничном сервере, CS РТКМЕДСРВ на сервере обновлений</span><span class="sxs-lookup"><span data-stu-id="9b870-120">Inbound firewall rules are disabled for CS RTCSRV on Edge server, CS RTCMEDSRV on Mediation server</span></span>
    
    <span data-ttu-id="9b870-121">В облачном соединителе версии 1.4.2 отслеживается только следующие службы:</span><span class="sxs-lookup"><span data-stu-id="9b870-121">In Cloud Connector version 1.4.2, only the following services are monitored:</span></span>
    
  - <span data-ttu-id="9b870-122">Сервер служб исправлений: РТКСРВ и МЕДСВК</span><span class="sxs-lookup"><span data-stu-id="9b870-122">Mediation Server services: RTCSRV and MEDSVC</span></span>
    
  - <span data-ttu-id="9b870-123">Служба пограничного сервера: РТКСРВ</span><span class="sxs-lookup"><span data-stu-id="9b870-123">Edge Server service: RTCSRV</span></span>
    
- <span data-ttu-id="9b870-124">**Процесс восстановления:** Если какие – либо отслеживаемые службы отключены, устройство помечается как отключенное и помечается вручную, пока не будут устранены все возможные проблемы.</span><span class="sxs-lookup"><span data-stu-id="9b870-124">**Recovery process:** If any monitored services are down, an appliance is marked down, and services are stopped and marked manual until all issues can be resolved.</span></span> <span data-ttu-id="9b870-125">Это предотвратит маршрутизацию звонков на устройство, которое может вызвать сбои при вызове.</span><span class="sxs-lookup"><span data-stu-id="9b870-125">This will prevent calls from routing to an appliance that may cause call failures.</span></span>
    
    <span data-ttu-id="9b870-126">Служба управления облачным соединителем повторит попытку автоматического восстановления, как описано ниже.</span><span class="sxs-lookup"><span data-stu-id="9b870-126">The Cloud Connector Management service will retry automatic recovery as follows</span></span>
    
  - <span data-ttu-id="9b870-127">Первоначальный интервал повтора составляет каждые десять секунд с максимальным временем в один час.</span><span class="sxs-lookup"><span data-stu-id="9b870-127">The initial retry interval is every ten seconds with a maximum interval time of one hour.</span></span>
    
  - <span data-ttu-id="9b870-128">Для первых трех попыток восстановления интервал времени равен 10 секундам.</span><span class="sxs-lookup"><span data-stu-id="9b870-128">For the first three recovery attempts, the interval time is 10 seconds.</span></span> <span data-ttu-id="9b870-129">Начиная с четвертого повтора, время интервала увеличивается на два раза подряд, чем предыдущий интервал.</span><span class="sxs-lookup"><span data-stu-id="9b870-129">Starting from the fourth retry, the interval time increases by two times the previous interval time.</span></span> <span data-ttu-id="9b870-130">Например, четвертая попытка будет возникать в течение 20 секунд, пятого в 40 секунд и т. д.</span><span class="sxs-lookup"><span data-stu-id="9b870-130">For example, the fourth retry will occur in 20 seconds, the fifth in 40 seconds, and so on.</span></span> 
    
  - <span data-ttu-id="9b870-131">При достижении максимального интервала в один час повторные попытки будут продолжаться в течение часа.</span><span class="sxs-lookup"><span data-stu-id="9b870-131">When the maximum interval time of one hour is reached, retries will continue once per hour.</span></span>
    
  - <span data-ttu-id="9b870-132">Если восстановление прошло успешно, для интервала и счетчика повторов устанавливаются исходные значения.</span><span class="sxs-lookup"><span data-stu-id="9b870-132">When recovery is successful, the interval and retry counts are set to their initial values.</span></span>
    
  - <span data-ttu-id="9b870-133">Если служба управления перезапустится, значения интервала и повтора будут сброшены на начальные.</span><span class="sxs-lookup"><span data-stu-id="9b870-133">If the Management service is restarted, the interval and retry counts are reset to their initial values.</span></span>
    
## <a name="troubleshooting"></a><span data-ttu-id="9b870-134">Поиск и устранение неполадок</span><span class="sxs-lookup"><span data-stu-id="9b870-134">Troubleshooting</span></span>

<span data-ttu-id="9b870-135">Ниже приведены решения часто встречающихся проблем.</span><span class="sxs-lookup"><span data-stu-id="9b870-135">Following are solutions to commonly encountered issues:</span></span>
  
- <span data-ttu-id="9b870-136">**Проблема. При выполнении сценариев развертывания происходит сбой или остановка развертывания. После выполнения входа на каждую виртуальную машину IP-адрес отсутствует или неверен для внешнего, внутреннего сетевого адаптера или сетевого адаптера управления.**</span><span class="sxs-lookup"><span data-stu-id="9b870-136">**Issue: Deployment fails or stops responding when running the deployment scripts. After logging on to each VM, the IP address is missing or incorrect for the Management/Internal/External NIC.**</span></span>
    
    <span data-ttu-id="9b870-137">**Решение:** Эту проблему невозможно устранить автоматически.</span><span class="sxs-lookup"><span data-stu-id="9b870-137">**Resolution:** This issue cannot be resolved automatically.</span></span> <span data-ttu-id="9b870-138">Сетевые адаптеры нельзя добавить на работающие виртуальные машины.</span><span class="sxs-lookup"><span data-stu-id="9b870-138">NICs cannot be added to VMs while they are running.</span></span> <span data-ttu-id="9b870-139">Завершите работу виртуальных машин и удалите их с помощью диспетчера Hyper-V, а затем выполните следующие командлеты:</span><span class="sxs-lookup"><span data-stu-id="9b870-139">Please shut down and remove these VMs in hyper-v manager, then run the following cmdlets:</span></span>
    
  ```powershell
  Uninstall-CcAppliance
  ```

  ```powershell
  Install-CcAppliance
  ```

- 
    
    <span data-ttu-id="9b870-140">**Проблема. После установки сервера Active Directory Server и леса сервер CMS и (или) сервер-посредник некорректно присоединяются к домену.**</span><span class="sxs-lookup"><span data-stu-id="9b870-140">**Issue: After the Active Directory Server and forest are installed, the CMS Server and/or Mediation Server did not join the domain correctly.**</span></span>
    
    <span data-ttu-id="9b870-141">**Решение**. Чтобы устранить эту проблему, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="9b870-141">**Resolution:** To resolve this issue, take the following steps:</span></span>
    
  - <span data-ttu-id="9b870-142">Войдите на сервер Active Directory и убедитесь, что домен создан правильно.</span><span class="sxs-lookup"><span data-stu-id="9b870-142">Log on to the Active Directory Server and verify that the domain was created correctly.</span></span>
    
  - <span data-ttu-id="9b870-143">Войдите на сервер CMS или сервер-посредник и убедитесь, что сетевому адаптеру корпоративной сети назначен допустимый IP-адрес, а серверу Active Directory назначены допустимый статический IP-адрес и DNS.</span><span class="sxs-lookup"><span data-stu-id="9b870-143">Log on to the CMS/Mediation Server and verify that on the corpnet NIC a valid IP address is assigned, and that valid static IP and DNS is configured as the AD server's IP address.</span></span>
    
  - <span data-ttu-id="9b870-144">Войдите на сервер CMS/-исправлений и откройте командную запись.</span><span class="sxs-lookup"><span data-stu-id="9b870-144">Log on to the CMS/Mediation Server, and open a command prompt.</span></span> <span data-ttu-id="9b870-145">Выполните проверку связи с сервером Active Directory по полному доменному имени и IP-адресу.</span><span class="sxs-lookup"><span data-stu-id="9b870-145">Make sure you can ping the FQDN and IP address of the Active Directory Server.</span></span> <span data-ttu-id="9b870-146">Если с сервером связаться не удается, это может указывать на конфликт IP-адресов.</span><span class="sxs-lookup"><span data-stu-id="9b870-146">If you cannot, there may be an IP address conflict.</span></span> <span data-ttu-id="9b870-147">Попробуйте назначить серверу новый IP-адрес и изменить параметры DNS на сервере-посреднике или сервере CMS соответствующим образом.</span><span class="sxs-lookup"><span data-stu-id="9b870-147">Please try to assign a new IP for Active Directory and update DNS on the CMS/Mediation server accordingly.</span></span>
    
- <span data-ttu-id="9b870-148">**Причина: появляется следующее сообщение об ошибке "Remove-VMSwitch: сбой при удалении виртуального коммутатора Ethernet. Невозможно удалить виртуальный коммутатор "переключатель управления с помощью облака-соединителя", так как он используется запущенными виртуальными машинами или назначен дочерним пулам. "**</span><span class="sxs-lookup"><span data-stu-id="9b870-148">**Issue: You receive the following error message, "Remove-VMSwitch : Failed while removing virtual Ethernet switch. The virtual switch 'Cloud Connector Management Switch' cannot be deleted because it is being used by running virtual machines or assigned to child pools."**</span></span>
    
    <span data-ttu-id="9b870-149">**Решение:** После развертывания не был удален "ключ управления облачным соединителем".</span><span class="sxs-lookup"><span data-stu-id="9b870-149">**Resolution:** The "Cloud Connector Management Switch" was not deleted after the deployment.</span></span> <span data-ttu-id="9b870-150">Если возникает эта ошибка, перейдите в диспетчер Hyper-V и убедитесь в отсутствии виртуальных машин, подключенных к этому коммутатору.</span><span class="sxs-lookup"><span data-stu-id="9b870-150">If you hit this error, please go to Hyper-v manager and verify that there is not still a virtual machine still connected to it.</span></span> <span data-ttu-id="9b870-151">При необходимости отключите подключенные виртуальные машины и удалите коммутатор управления.</span><span class="sxs-lookup"><span data-stu-id="9b870-151">If there are virtual machines still connected, disconnect them and delete the management switch.</span></span> <span data-ttu-id="9b870-152">Если удалить его по-прежнему не удается, перезапустите сервер узла и повторите попытку.</span><span class="sxs-lookup"><span data-stu-id="9b870-152">If the management switch still cannot be deleted, restart the host server and try again.</span></span>
    
- <span data-ttu-id="9b870-153">**Причина: появляется следующее сообщение об ошибке "не удается запустить службу РТКМРАУС. Убедитесь, что служба не отключена.**</span><span class="sxs-lookup"><span data-stu-id="9b870-153">**Issue: You receive the following error message, "Service RTCMRAUTH failed to start. Check to make sure the service is not disabled."**</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="9b870-154">Эта проблема применима только к версиям соединителя облака, предшествующим 1.4.2.</span><span class="sxs-lookup"><span data-stu-id="9b870-154">This issue only applies to Cloud Connector versions earlier than 1.4.2.</span></span> 
  
    <span data-ttu-id="9b870-p110">Причиной сбоя запуска может быть предыдущая отработка отказа этого сервера переднего плана (путем отработки отказа компьютера). В этом случае выполните откат (откат компьютера).</span><span class="sxs-lookup"><span data-stu-id="9b870-p110">The failure to start could also be because this Front End server was previously failed over (using computer fail over). If that's the case, please invoke fail back (using computer fail back).</span></span>
    
    <span data-ttu-id="9b870-p111">**Решение**. Эта проблема возникает на пограничном сервере, если пограничный сервер не доверяет сертификату корневого ЦС или промежуточного ЦС. Даже в том случае, если можно импортировать внешний сертификат, но цепочка сертификатов нарушена, службу RTCMRAUTH и (или) RTCSRV запустить невозможно.</span><span class="sxs-lookup"><span data-stu-id="9b870-p111">**Resolution:** This issue happens on an Edge Server when the root CA certificate or intermediate CA certificate is not trusted by the Edge Server. Even if the external certificate can be imported but the certificate chain is broken. Under this condition, the RTCMRAUTH and/or RTCSRV service can not start.</span></span>
    
    <span data-ttu-id="9b870-p112">Вручную импортируйте сертификат корневого ЦС или все сертификаты промежуточных ЦС внешнего сертификата на пограничный сервер, а затем перезапустите его. После запуска служб RTCMRAUTH и RTCSRV на пограничном сервере вернитесь на сервер узла, запустите консоль PowerShell от имени администратора и выполните следующий командлет, чтобы переключиться на новое развертывание:</span><span class="sxs-lookup"><span data-stu-id="9b870-p112">Please import the root CA certificate and all intermediate CA certificates of your external certificate manually into the Edge Server and then restart the Edge Server. After you see the RTCMRAUTH and RTCSRV services started on the Edge Server, go back to your host server, launch a PowerShell console as administrator, and run following cmdlet to switch to the new deployment:</span></span>
    
  ```powershell
  Switch-CcVersion
  ```

- 
    
    <span data-ttu-id="9b870-162">**Проблема. Сервер узла перезапускается после применения обновлений Windows, и происходит сбой вызовов, обслуживаемых этим сервером.**</span><span class="sxs-lookup"><span data-stu-id="9b870-162">**Issue: The host server was restarted when Windows updates were applied, and calls serviced by the server are failing.**</span></span>
    
    <span data-ttu-id="9b870-p113">**Решение**. Если развернута среда высокой доступности, Microsoft предоставляет командлет для переноса одного хост-компьютера (экземпляра развертывания) в текущую топологию или из нее при проверке и установке обновления для Windows вручную. Для этого выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="9b870-p113">**Resolution:** If you deployed a high availability environment, Microsoft provides a cmdlet to help move one host machine (deployment instance) into or out of the current topology when you check and install Windows update manually. Use the following steps to accomplish this:</span></span>
    
1. <span data-ttu-id="9b870-165">На сервере узла запустите консоль PowerShell от имени администратора, а затем выполните команду:</span><span class="sxs-lookup"><span data-stu-id="9b870-165">On the host server, start a PowerShell console as administrator, then run:</span></span>
    
   ```powershell
   Enter-CcUpdate
   ```

2. <span data-ttu-id="9b870-166">Проверьте наличие обновлений и установите доступные обновления.</span><span class="sxs-lookup"><span data-stu-id="9b870-166">Check for updates and install any that are available.</span></span>
    
3. <span data-ttu-id="9b870-167">В консоли PowerShell запустите следующий командлет:</span><span class="sxs-lookup"><span data-stu-id="9b870-167">In the PowerShell console, run the following cmdlet:</span></span>
    
   ```powershell
   Exit-CcUpdate
   ```

- 
    
    <span data-ttu-id="9b870-168">**Проблема. При выполнении звонка из клиента Skype для бизнеса с использованием номера ТСОП невозможно повысить уровень звонка до конференции, пригласив к участию в нем другой номер ТСОП**.</span><span class="sxs-lookup"><span data-stu-id="9b870-168">**Issue: When a call is made from a Skype for Business client using a PSTN number, the call cannot be escalated to a conference by inviting another PSTN number.**</span></span>
    
    <span data-ttu-id="9b870-169">**Решение:** Чтобы устранить эту проблему, ознакомьтесь со сведениями в разделе [Настройка параметров сервера гибридных сетевых исправлений](configure-cloud-connector-integration-with-your-office-365-tenant.md#BKMK_ConfigureMediationServer).</span><span class="sxs-lookup"><span data-stu-id="9b870-169">**Resolution:** To resolve this issue, see [Configure online hybrid Mediation Server Settings](configure-cloud-connector-integration-with-your-office-365-tenant.md#BKMK_ConfigureMediationServer).</span></span>
    
- <span data-ttu-id="9b870-170">**Проблема. При установке сервера Active Directory отображается предупреждение о Центре обновления Windows: «Автоматическое обновление Windows отключено. Чтобы обеспечить автоматическое обновление только что установленной роли или компонента, включите Центр обновления Windows».**</span><span class="sxs-lookup"><span data-stu-id="9b870-170">**Issue: A warning message is displayed about Windows Update when you are installing Active Directory server - "Windows automatic updating is not enabled. To ensure that your newly-installed role or feature is automatically updated, turn on Windows Update."**</span></span>
    
    <span data-ttu-id="9b870-171">**Решение:** Запустите удаленный сеанс PowerShell клиента с помощью учетных данных администратора Skype для бизнеса, а затем выполните следующий командлет для проверки конфигурации _енаблеаутаупдате_ на сайте:</span><span class="sxs-lookup"><span data-stu-id="9b870-171">**Resolution:** Launch a Tenant Remote PowerShell session using Skype for Business tenant admin credentials, then run the following cmdlet to check the _EnableAutoUpdate_ configuration of your site:</span></span>
    
  ```powershell
  Get-CsHybridPSTNSite
  ```

    <span data-ttu-id="9b870-172">Если для _енаблеаутаупдате_ установлено **значение true**, вы можете спокойно проигнорировать это предупреждение, так как служба кцеманажемент будет обрабатывать загрузку и установку обновлений для Windows как для виртуальных машин, так и для основного сервера.</span><span class="sxs-lookup"><span data-stu-id="9b870-172">If  _EnableAutoUpdate_ is set to **True**, you can safely ignore this warning message because the CCEManagement service will handle downloading and installing Windows updates for both virtual machines and the host server.</span></span> <span data-ttu-id="9b870-173">Если для _енаблеаутаупдате_ задано **значение false**, запустите следующий командлет, чтобы установить для него значение **true**.</span><span class="sxs-lookup"><span data-stu-id="9b870-173">If  _EnableAutoUpdate_ is set to **False**, run following cmdlet to set it to **True**.</span></span>
    
  ```powershell
  Set-CsHybridPSTNSite -EnableAutoUpdate $true
  ```

    <span data-ttu-id="9b870-174">Кроме того, вы можете вручную проверить наличие обновлений и установить их.</span><span class="sxs-lookup"><span data-stu-id="9b870-174">Alternatively, you can manually check for and install updates.</span></span> <span data-ttu-id="9b870-175">Просмотрите следующий раздел.</span><span class="sxs-lookup"><span data-stu-id="9b870-175">See the next section.</span></span>
    
- <span data-ttu-id="9b870-176">**Причина: вы получаете сообщение об ошибке: не удается зарегистрировать устройство управления, так как \<ваши\> текущие \<входные \<и конфигурации sitename\> или \<апплианценаме\> либо IP-\> адрес сервера исходящих серверов или сервер исходящих сообщений конфликтуют с существующим устройством. Удалите конфликтующее устройство или обновите данные ввода и настройки, а затем повторите регистрацию. ' при выполнении Register-Ккапплианце зарегистрировать текущее устройство в сети.**</span><span class="sxs-lookup"><span data-stu-id="9b870-176">**Issue: You receive an error message: Cannot register appliance because your current input/configuration \<SiteName\> or \<ApplianceName\> or \<Mediation Server FQDN\> or \<Mediation Server IP Address\> conflicts with existing appliance(s). Remove conflict appliance or update your input/configuration information then register again. ' when run Register-CcAppliance to register current appliance to online.**</span></span>
    
    <span data-ttu-id="9b870-177">**Решение:** Значения для IP \<-\>адреса \<\> сервера апплианценаме,\> полного \<доменного имени и сервера исданных исправлений должны быть уникальными и использоваться только для одной регистрации устройства.</span><span class="sxs-lookup"><span data-stu-id="9b870-177">**Resolution:** Values for the \<ApplianceName\>, \<Mediation Server FQDN\> and \<Mediation Server IP Address\> must be unique and only used for one appliance registration.</span></span> <span data-ttu-id="9b870-178">По умолчанию \<апплианценаме\> берется из имени узла.</span><span class="sxs-lookup"><span data-stu-id="9b870-178">By default, \<ApplianceName\> comes from the host name.</span></span> <span data-ttu-id="9b870-179">\<IP-адрес\> \> сервера \<исправлений, заданный в файле конфигурации ini.</span><span class="sxs-lookup"><span data-stu-id="9b870-179">\<Mediation Server FQDN\> and \<Mediation Server IP Address\> defined in configuration ini file.</span></span>
    
    <span data-ttu-id="9b870-180">Например, при использовании (ApplianceName= MyserverNew, Mediation Server FQDN=ms.contoso.com, Mediation Server IP Address=10.10.10.10) для регистрации на сайте SiteName=MySite, если существует зарегистрированное устройство (ApplianceName= Myserver, Mediation Server FQDN=ms.contoso.com, Mediation Server IP Address=10.10.10.10), возникнет конфликт.</span><span class="sxs-lookup"><span data-stu-id="9b870-180">For example, using (ApplianceName= MyserverNew, Mediation Server FQDN=ms.contoso.com, Mediation Server IP Address=10.10.10.10) to register to SiteName=MySite, but if there is a registered appliance (ApplianceName= Myserver, Mediation Server FQDN=ms.contoso.com, Mediation Server IP Address=10.10.10.10), you will have the conflict.</span></span>
    
    <span data-ttu-id="9b870-181">Прежде всего проверьте файл CloudConnector.ini в каталоге ApplianceRoot.</span><span class="sxs-lookup"><span data-stu-id="9b870-181">First, please check your CloudConnector.ini file in ApplianceRoot directory section.</span></span> <span data-ttu-id="9b870-182">Вы получите \<в файле\>значения \<IP-адреса\> \> сервера \<доменных имен (FQDN) и сервера исправлений.</span><span class="sxs-lookup"><span data-stu-id="9b870-182">You will get \<SiteName\>, \<Mediation Server FQDN\> and \<Mediation Server IP Address\> values in the file.</span></span> <span data-ttu-id="9b870-183">\<Апплианценаме\> — это имя вашего сервера узла.</span><span class="sxs-lookup"><span data-stu-id="9b870-183">\<ApplianceName\> is your host server name.</span></span>
    
    <span data-ttu-id="9b870-184">Во-вторых, запустите удаленную оболочку PowerShell с помощью учетных данных администратора клиента Skype для бизнеса, а затем выполните следующий командлет для проверки зарегистрированного устройства (-ов).</span><span class="sxs-lookup"><span data-stu-id="9b870-184">Second, Launch Tenant Remote PowerShell using your Skype for Business tenant admin credentials, then run the following cmdlet to check the registered appliance(s).</span></span>
    
  ```powershell
  Get-CsHybridPSTNAppliance
  ```

    <span data-ttu-id="9b870-185">После обнаружения конфликтов вы можете обновить файл CloudConnector.ini, включив в него данные зарегистрированного устройства, или отменить регистрацию существующего устройства для устранения конфликтов.</span><span class="sxs-lookup"><span data-stu-id="9b870-185">After identifying any conflicts, you can either update your CloudConnector.ini file with information that matches the registered appliance, or unregister the existing appliance to resolve the conflicts.</span></span>
    
  ```powershell
  Unregister-CsHybridPSTNAppliance -Force
  ```

    
- <span data-ttu-id="9b870-186">**Вопрос: командлет Get-Ккруннингверсион возвращает пустое значение, если на хосте запущено приложение с развернутым устройством.**</span><span class="sxs-lookup"><span data-stu-id="9b870-186">**Issue: The Get-CcRunningVersion cmdlet returns an empty value if there is a deployed appliance running on the host.**</span></span>
    
  <span data-ttu-id="9b870-187">**Решение:** Это может случиться при переходе с 1.3.4 или 1.3.8 на 1.4.1.</span><span class="sxs-lookup"><span data-stu-id="9b870-187">**Resolution:** This can happen when you upgrade from 1.3.4 or 1.3.8 to 1.4.1.</span></span> <span data-ttu-id="9b870-188">После установки версии 1.4.1 с помощью MSI-файла необходимо запустить `Register-CcAppliance` перед запуском любого другого командлета.</span><span class="sxs-lookup"><span data-stu-id="9b870-188">After you install version 1.4.1 with the .msi, you must run `Register-CcAppliance` before you run any other cmdlet.</span></span> <span data-ttu-id="9b870-189">`Register-CcAppliance`выполняет миграцию файла Module. ini из%Усерпрофиле%\клаудконнектор в%Програмдата%\клаудконнектор.</span><span class="sxs-lookup"><span data-stu-id="9b870-189">`Register-CcAppliance` will migrate the module.ini file from %UserProfile%\CloudConnector to %ProgramData%\CloudConnector.</span></span> <span data-ttu-id="9b870-190">Если пропустить этот шаг, в папке %ProgramData%\CloudConnector будет создан новый файл module.ini, который заменит сведения о выполняющейся или резервной версии для 1.3.4 или 1.3.8.</span><span class="sxs-lookup"><span data-stu-id="9b870-190">If you missed it, a new module.ini will be created in %ProgramData%\CloudConnector folder and replace the running/backup version information for 1.3.4 or 1.3.8.</span></span>
    
  <span data-ttu-id="9b870-191">Сравните файлы module.ini в папках %UserProfile%\CloudConnector и %ProgramData%\CloudConnector.</span><span class="sxs-lookup"><span data-stu-id="9b870-191">Compare module.ini files in %UserProfile%\CloudConnector and %ProgramData%\CloudConnector folder.</span></span> <span data-ttu-id="9b870-192">Если есть различия, удалите файл Module. ini в%Програмдата%\клаудконнектор и снова запустите `Register-CcAppliance`его.</span><span class="sxs-lookup"><span data-stu-id="9b870-192">If there are differences, delete the module.ini file in %ProgramData%\CloudConnector and rerun  `Register-CcAppliance`.</span></span> <span data-ttu-id="9b870-193">Вы также можете изменить файл вручную, чтобы он был правильно запущенный и резервная версия.</span><span class="sxs-lookup"><span data-stu-id="9b870-193">You could also modify the file manually to the correct running and backup version.</span></span>
    
- <span data-ttu-id="9b870-194">**Проблема: после запуска командлета Switch-Ккверсион для переключения на старую версию, которая отличается от текущей версии сценария, для этой старой версии отсутствует поддержка высокого уровня доступности.**</span><span class="sxs-lookup"><span data-stu-id="9b870-194">**Issue: After you run the Switch-CcVersion cmdlet to switch to an old version which is different from current script version, there is no High Availability support for this old version.**</span></span>
    
    <span data-ttu-id="9b870-195">**Решение:** Например, вы перешли с 1.4.1 на 1.4.2.</span><span class="sxs-lookup"><span data-stu-id="9b870-195">**Resolution:** For example, you have upgraded from 1.4.1 to 1.4.2.</span></span> <span data-ttu-id="9b870-196">Текущая версия сценария, которая может быть определена при запуске `Get-CcVersion`, и используемая версия, которую можно определить с помощью команды `Get-CcRunningVersion` "1.4.2".</span><span class="sxs-lookup"><span data-stu-id="9b870-196">Your current script version, which can be determined by running `Get-CcVersion`, and your running version, which can be determined by running  `Get-CcRunningVersion` are both 1.4.2.</span></span> <span data-ttu-id="9b870-197">В настоящее время, если вы `Switch-CcVersion` перейдете на 1.4.1, для этой старой версии отсутствует поддержка высокого уровня доступности.</span><span class="sxs-lookup"><span data-stu-id="9b870-197">At this time, if you run `Switch-CcVersion` to switch the running version back to 1.4.1, then there will be no High Availability support for this old version.</span></span>
    
    <span data-ttu-id="9b870-p121">Чтобы получить полную поддержку высокой готовности, вернитесь к версии 1.4.2 (запущенная версия и версия скрипта должны быть одинаковыми). При возникновении проблем с развертыванием версии 1.4.2 удалите и повторно установите ее.</span><span class="sxs-lookup"><span data-stu-id="9b870-p121">To get full High Availability support, please switch back to 1.4.2, so the running version and script version are the same. If you are experiencing problems with your 1.4.2 deployment, please uninstall and reinstall it as soon as possible.</span></span>
    
- <span data-ttu-id="9b870-200">**Проблема. Срок действия сертификатов, выданных центром сертификации, или внутренних сертификатов, выданных серверу центрального хранилища управления (CMS), серверу-посреднику или пограничному серверу, истекает, либо они скомпрометированы.**</span><span class="sxs-lookup"><span data-stu-id="9b870-200">**Issue: Certificate authority certificates or internal certificates issued to Central Management Store, Mediation Server, and Edge Server are near expiration or are compromised.**</span></span>
    
    <span data-ttu-id="9b870-p122">**Решение.** Сертификаты Skype для бизнеса, выданные центром сертификации, действуют в течение пяти лет. Внутренние сертификаты, выданные серверу центрального хранилища управления (CMS), серверу-посреднику или пограничному серверу, действуют в течение двух лет.</span><span class="sxs-lookup"><span data-stu-id="9b870-p122">**Resolution:** Skype for Business certification authority certificates are valid for five years. Internal certificates issued to the Central Management Store, Mediation Server, and Edge Server are valid for two years.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="9b870-203">В облачном соединителе версии 2,0 и более поздних командлета Update-Кксерверцертификате изменилось на обновление Кксерверцертификате, а командлет продления-Кккацертификате изменился на Update-Кккацертификате.</span><span class="sxs-lookup"><span data-stu-id="9b870-203">In Cloud Connector version 2.0 and later, the Renew-CcServerCertificate cmdlet has changed to Update-CcServerCertificate and the Renew-CcCACertificate cmdlet has changed to Update-CcCACertificate.</span></span> 
  
    <span data-ttu-id="9b870-204">Если внутренние сертификаты, выданные для хранилища централизованного управления, сервера-посредника и пограничного сервера, приближается к истечении срока действия или скомпрометированы, запустите командлет Restore-Кксерверцертификате или Update-Кксерверцертификате для продления сертификатов.</span><span class="sxs-lookup"><span data-stu-id="9b870-204">If internal certificates issued to the Central Management Store, Mediation Server, and Edge Server are near expiration or compromised, run the Renew-CcServerCertificate or Update-CcServerCertificate cmdlet to renew your certificates.</span></span>
    
    <span data-ttu-id="9b870-205">Если срок действия сертификатов центра сертификации истек, выполните командлет возобновления-Кккацертификате или Update-Кккацертификате для продления сертификатов.</span><span class="sxs-lookup"><span data-stu-id="9b870-205">If certification authority certificates are near expiration, run the Renew-CcCACertificate or Update-CcCACertificate cmdlet to renew your certificates.</span></span>
    
    <span data-ttu-id="9b870-206">**Если сертификаты центра сертификации скомпрометированы и на сайте есть только одно устройство,** выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="9b870-206">**If certification authority certificates are compromised and there is only one appliance in the site,** perform the following steps:</span></span>
    
1. <span data-ttu-id="9b870-207">Выполните командлет Enter-CcUpdate, чтобы очистить службы и перевести устройство в режим обслуживания.</span><span class="sxs-lookup"><span data-stu-id="9b870-207">Run the Enter-CcUpdate cmdlet to drain services and put the appliance in maintenance mode.</span></span>
   
   ```powershell
   Enter-CcUpdate
   ```
   
2. <span data-ttu-id="9b870-208">Выполните следующие командлеты, чтобы сбросить и создать новые сертификаты центра сертификации, а также все внутренние сертификаты.</span><span class="sxs-lookup"><span data-stu-id="9b870-208">Run the following cmdlets to reset and create new certification authority certificates and all internal server certificates:</span></span>
    
    <span data-ttu-id="9b870-209">Для выпусков облачных соединителей перед 2,0:</span><span class="sxs-lookup"><span data-stu-id="9b870-209">For Cloud Connector releases before 2.0:</span></span>
    
    ```powershell
    Reset-CcCACertificate 
    Renew-CcServerCertificate 
    Remove-CcLegacyServerCertificate 
    ```

    <span data-ttu-id="9b870-210">А также для облачного соединителя выпуска 2,0 и более поздних версий:</span><span class="sxs-lookup"><span data-stu-id="9b870-210">Or for Cloud Connector release 2.0 and later:</span></span>
    
    ```powershell
    Reset-CcCACertificate 
    Update-CcServerCertificate 
    Remove-CcLegacyServerCertificate 
    ```
    
3. <span data-ttu-id="9b870-211">Если между шлюзом и сервером-посредником используется протокол TLS, выполните командлет Export-Ккрутцертификате на устройстве, а затем установите экспортированный сертификат на шлюзы PSTN.</span><span class="sxs-lookup"><span data-stu-id="9b870-211">If TLS is used between the gateway and the Mediation Server, run the Export-CcRootCertificate cmdlet from the appliance, and then install the exported certificate to your PSTN gateways.</span></span> <span data-ttu-id="9b870-212">Кроме того, вам может потребоваться повторно выдать сертификат на ваш шлюз.</span><span class="sxs-lookup"><span data-stu-id="9b870-212">You may also be required to re-issue the certificate on your gateway.</span></span>

   ```powershell
   Export-CcRootCertificate
   ```

4. <span data-ttu-id="9b870-213">Запустите командлет Exit-Ккупдате, чтобы запустить службы и выйти из режима обслуживания.</span><span class="sxs-lookup"><span data-stu-id="9b870-213">Run the Exit-CcUpdate cmdlet to start services and exit maintenance mode.</span></span>

   ```powershell
   Exit-CcUpdate
   ```


    <span data-ttu-id="9b870-214">**Если сертификаты центра сертификации скомпрометированы и на сайте есть несколько устройств,** выполните указанные ниже действия на каждом устройстве сайта.</span><span class="sxs-lookup"><span data-stu-id="9b870-214">**If certification authority certificates are compromised and there are multiple appliances in the site,** perform the following sequential steps on each appliance in the site.</span></span>
    
    <span data-ttu-id="9b870-215">Корпорация Microsoft рекомендует выполнять эти действия во время непикового использования.</span><span class="sxs-lookup"><span data-stu-id="9b870-215">Microsoft recommends that you perform these steps during non-peak usage times.</span></span>
    
1. <span data-ttu-id="9b870-216">На первом устройстве выполните командлет Remove-Ккцертификатионаусоритифиле для очистки файлов резервных копий ЦС в каталоге \<ситерут.\></span><span class="sxs-lookup"><span data-stu-id="9b870-216">On the first appliance, run the Remove-CcCertificationAuthorityFile cmdlet to clean up the CA backup files in the \<SiteRoot\> directory.</span></span>

     ```powershell
     Remove-CcCertificationAuthorityFile
     ```
    
2. <span data-ttu-id="9b870-217">Запустите командлет Enter-Ккупдате для сток служб и помещения каждого устройства в режим обслуживания.</span><span class="sxs-lookup"><span data-stu-id="9b870-217">Run the Enter-CcUpdate cmdlet to drain services and put each appliance in maintenance mode.</span></span>

     ```powershell
     Enter-CcUpdate
     ```
    
3. <span data-ttu-id="9b870-218">На первом устройстве выполните следующие командлеты для сброса и создания новых сертификатов центра сертификации и всех внутренних сертификатов сервера.</span><span class="sxs-lookup"><span data-stu-id="9b870-218">On the first appliance, run the following cmdlets to reset and create new certification authority certificates and all internal server certificates:</span></span>
    
     <span data-ttu-id="9b870-219">Для выпусков облачных соединителей перед 2,0:</span><span class="sxs-lookup"><span data-stu-id="9b870-219">For Cloud Connector releases before 2.0:</span></span>
    
     ```powershell
     Reset-CcCACertificate
     Renew-CcServerCertificate
     Remove-CcLegacyServerCertificate 
     ```

     <span data-ttu-id="9b870-220">А также для облачного соединителя выпуска 2,0 и более поздних версий:</span><span class="sxs-lookup"><span data-stu-id="9b870-220">Or for Cloud Connector release 2.0 and later:</span></span>
    
     ```powershell
     Reset-CcCACertificate
     Update-CcServerCertificate
     Remove-CcLegacyServerCertificate 
     ```

4. <span data-ttu-id="9b870-221">На первом устройстве запустите следующий командлет для резервного копирования файлов ЦС в папку \<ситерут.\></span><span class="sxs-lookup"><span data-stu-id="9b870-221">On the first appliance, run the following cmdlet to back up the CA files to the \<SiteRoot\> folder.</span></span>
    
     ```powershell
     Backup-CcCertificationAuthority
     ```
   
5. <span data-ttu-id="9b870-222">На любом другом устройстве на том же сайте выполните следующие команды, чтобы использовать резервные файлы центра сертификации, чтобы все устройства использовали один и тот же корневой сертификат, а затем запросить новые сертификаты.</span><span class="sxs-lookup"><span data-stu-id="9b870-222">On all other appliance's in the same site, run the following commands to consume the CA backup files, so that the appliances all use the same root certificate, and then request new certificates.</span></span> 
   
     ```powershell
     Reset-CcCACertificate
     Update-CcServerCertificate
     Remove-CcLegacyServerCertificate 
     ```
     
6. <span data-ttu-id="9b870-223">Если между шлюзом и сервером-посредником используется протокол TLS, выполните командлет Export-Ккрутцертификате на любом устройстве сайта, а затем установите экспортированный сертификат на шлюзы PSTN.</span><span class="sxs-lookup"><span data-stu-id="9b870-223">If TLS is used between the gateway and the Mediation Server, run the Export-CcRootCertificate cmdlet from any appliance in the site, and then install the exported certificate to your PSTN gateways.</span></span> <span data-ttu-id="9b870-224">Кроме того, вам может потребоваться повторно выдать сертификат на ваш шлюз.</span><span class="sxs-lookup"><span data-stu-id="9b870-224">You may also be required to re-issue the certificate on your gateway.</span></span>
  
     ```powershell
     Export-CcRootCertificate
     ```
     
7. <span data-ttu-id="9b870-225">Запустите командлет Exit-Ккупдате, чтобы запустить службы и выйти из режима обслуживания.</span><span class="sxs-lookup"><span data-stu-id="9b870-225">Run the Exit-CcUpdate cmdlet to start services and exit maintenance mode.</span></span> 

     ```powershell
     Exit-CcUpdate
     ```
    
    
- <span data-ttu-id="9b870-226">**Причина: в журнале службы управления облачным соединителем появляется следующее сообщение об ошибке: "C:\Program Филес\скипе для бизнеса Cloud Connector Едитион\манажементсервице\кцеманажементсервице.лог". Кцесервице Error: 0: непредвиденное исключение при отправке отчета о состоянии в сети: вход в System. Management. Automation. \<кмдлетинвокатионексцептион: сбой\>входа для администратора глобального клиента. Создайте новый объект учетных данных, убедившись в том, что вы использовали правильные имя пользователя и пароль. ---\>**</span><span class="sxs-lookup"><span data-stu-id="9b870-226">**Issue: You receive the following error message in the Cloud Connector Management Service Log, "C:\Program Files\Skype for Business Cloud Connector Edition\ManagementService\CceManagementService.log": CceService Error: 0 : Unexpected exception when reporting status to online: System.Management.Automation.CmdletInvocationException: Logon failed for the user \<Global Tenant Admin\>. Please create a new credential object, making sure that you have used the correct user name and password. ---\>**</span></span>
    
    <span data-ttu-id="9b870-227">**Решение:** Учетные данные администратора глобального клиента Office 365 были изменены с момента регистрации устройства облачного соединителя.</span><span class="sxs-lookup"><span data-stu-id="9b870-227">**Resolution:** The Office 365 global tenant admin credentials have been changed since the Cloud Connector appliance was registered.</span></span> <span data-ttu-id="9b870-228">Чтобы обновить локально хранящиеся учетные данные на устройстве облачного соединителя, выполните следующие действия от администратора PowerShell на устройстве узла:</span><span class="sxs-lookup"><span data-stu-id="9b870-228">To update the locally stored credentials on the Cloud Connector appliance, run the following from Administrator PowerShell on the host appliance:</span></span>
    
  ```powershell
  Set-CcCredential -AccountType TenantAdmin
  ```

- <span data-ttu-id="9b870-229">**Вопрос: после изменения пароля для учетной записи сервера узла, которую вы использовали для развертывания, появляется следующее сообщение об ошибке: "ConvertTo-SecureString: ключ не является допустимым для использования в указанном состоянии" в%Програмфилес%\скипе для бизнеса Cloud Connector Едитион\манажементсервице\кцеманажементсервице.лог или при выполнении командлета Get-Кккредентиал.**</span><span class="sxs-lookup"><span data-stu-id="9b870-229">**Issue: After you change the password for the host server account you used for the deployment, you receive the following error message: "ConvertTo-SecureString : Key not valid for use in specified state." in %ProgramFiles%\Skype for Business Cloud Connector Edition\ManagementService\CceManagementService.log or while running the Get-CcCredential cmdlet.**</span></span>
    
    <span data-ttu-id="9b870-230">**Решение:** Все учетные данные облачного соединителя хранятся в следующем файле: "%Системдриве%\програмдата\клаудконнектор\кредентиалс. \<CurrentUser\>. XML ".</span><span class="sxs-lookup"><span data-stu-id="9b870-230">**Resolution:** All Cloud Connector credentials are stored in the following file: "%SystemDrive%\Programdata\Cloudconnector\credentials.\<CurrentUser\>.xml".</span></span> <span data-ttu-id="9b870-231">При изменении пароля на сервере узла необходимо обновить учетные данные, сохраненные локально.</span><span class="sxs-lookup"><span data-stu-id="9b870-231">When the password on the host server changes, you will need to update the locally stored credentials.</span></span>
    
    <span data-ttu-id="9b870-232">**При запуске Cloud Connector версии 1.4.2,** повторно создайте все пароли Cloud Connector, выполнив следующие действия.</span><span class="sxs-lookup"><span data-stu-id="9b870-232">**If you are running Cloud Connector version 1.4.2,** regenerate all Cloud Connector passwords by following these steps:</span></span>
    
  1. <span data-ttu-id="9b870-233">Перезапустите сервер узла.</span><span class="sxs-lookup"><span data-stu-id="9b870-233">Restart the host server.</span></span>
    
  2. <span data-ttu-id="9b870-234">Удалите следующий файл: "%Системдриве%\програмдата\клаудконнектор\кредентиалс. \<CurrentUser\>. XML ".</span><span class="sxs-lookup"><span data-stu-id="9b870-234">Delete the following file: "%SystemDrive%\Programdata\Cloudconnector\credentials.\<CurrentUser\>.xml".</span></span>
    
  3. <span data-ttu-id="9b870-235">Запустите консоль PowerShell с правами администратора, а затем выполните команду "Register-Ккапплианце-Local", чтобы повторно ввести пароли после описания.</span><span class="sxs-lookup"><span data-stu-id="9b870-235">Launch a PowerShell console as administrator, and then run "Register-CcAppliance -Local" to re-enter the passwords following the description.</span></span> <span data-ttu-id="9b870-236">Введите те же пароли, которые были указаны ранее для развертывания Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="9b870-236">Enter the same passwords you entered before for the Cloud Connector deployment.</span></span>
    
     <span data-ttu-id="9b870-237">**Если вы используете облачный соединитель версии 2,0 или более поздней,** повторно создайте все пароли из облачных соединителей, выполнив следующие действия:</span><span class="sxs-lookup"><span data-stu-id="9b870-237">**If you are running Cloud Connector version 2.0 or later,** regenerate all Cloud Connector passwords by following these steps:</span></span>
    
  4. <span data-ttu-id="9b870-238">Перезапустите сервер узла.</span><span class="sxs-lookup"><span data-stu-id="9b870-238">Restart the host server.</span></span>
    
  5. <span data-ttu-id="9b870-239">Удалите следующий файл: "%Системдриве%\програмдата\клаудконнектор\кредентиалс. \<CurrentUser\>. XML ".</span><span class="sxs-lookup"><span data-stu-id="9b870-239">Delete the following file: "%SystemDrive%\Programdata\Cloudconnector\credentials.\<CurrentUser\>.xml" .</span></span>
    
  6. <span data-ttu-id="9b870-240">Запустите консоль PowerShell с правами администратора, а затем выполните команду "Register-Ккапплианце-Local", чтобы повторно ввести пароли после описания.</span><span class="sxs-lookup"><span data-stu-id="9b870-240">Launch a PowerShell console as administrator, and then run "Register-CcAppliance -Local" to re-enter the passwords following the description.</span></span> 
    
     <span data-ttu-id="9b870-p128">Если файл кэшированного пароля был сгенерирован с помощью Cloud Connector версии 1.4.2, при появлении запроса используйте пароль VMAdmin для пароля CceService. Для всех остальных учетных записей введите тот же пароль, который был указан ранее для развертывания Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="9b870-p128">If the cached password file was generated with Cloud Connector version 1.4.2, use the VMAdmin password for the CceService password when prompted. Enter the same password you entered before for the Cloud Connector deployment for all other accounts.</span></span>
    
     <span data-ttu-id="9b870-243">Если файл кэшированного пароля был сгенерирован с помощью Cloud Connector версии 1.4.2, и пароли учетных записей DomainAdmin и VMAdmin отличаются друг от друга, необходимо выполнить следующие действия.</span><span class="sxs-lookup"><span data-stu-id="9b870-243">If the cached password file was generated with Cloud Connector version 1.4.2 and the DomainAdmin and VMAdmin passwords are different, you must perform the following steps:</span></span>
    
  7. <span data-ttu-id="9b870-244">Запустите командлет Set-CcCredential -AccountType DomainAdmin, следуя инструкциям ниже.</span><span class="sxs-lookup"><span data-stu-id="9b870-244">Run Set-CcCredential -AccountType DomainAdmin as follows:</span></span>
    
  8. <span data-ttu-id="9b870-245">При запросе учетных данных старой учетной записи введите учетные данные, которые использовались с паролем для учетной записи CceService.</span><span class="sxs-lookup"><span data-stu-id="9b870-245">When prompted for the old account credential, enter the credential you used for the CceService password.</span></span>
    
  9. <span data-ttu-id="9b870-246">При запросе учетных данных новой учетной записи введите пароль для DomainAdmin, использованный ранее.</span><span class="sxs-lookup"><span data-stu-id="9b870-246">When prompted for the new account credential, enter the password for the DomainAdmin password you used before.</span></span>
    
     <span data-ttu-id="9b870-247">Если файл с кэшированным паролем был создан с помощью облачного соединителя версии 2,0 или более поздней, по умолчанию Вмадмин и Домаинадмин используют тот же пароль, что и в Кцесервице.</span><span class="sxs-lookup"><span data-stu-id="9b870-247">If the cached password file was generated with Cloud Connector version 2.0 or later, by default, VmAdmin and DomainAdmin use the same password as CceService.</span></span> <span data-ttu-id="9b870-248">Если пароли для DomainAdmin и VMAdmin были изменены, необходимо выполнить следующие действия.</span><span class="sxs-lookup"><span data-stu-id="9b870-248">If you changed the DomainAdmin and VMAdmin passwords, you must perform the following steps:</span></span>
    
  10. <span data-ttu-id="9b870-249">Запустите командлет Set-CcCredential -AccountType DomainAdmin, следуя инструкциям ниже.</span><span class="sxs-lookup"><span data-stu-id="9b870-249">Run Set-CcCredential -AccountType DomainAdmin as follows:</span></span>
    
       1. <span data-ttu-id="9b870-250">При запросе учетных данных старой учетной записи введите учетные данные, которые использовались с паролем для CceService.</span><span class="sxs-lookup"><span data-stu-id="9b870-250">When prompted for the old account credential, enter the credential you used for the CceService password</span></span>
    
       2. <span data-ttu-id="9b870-251">При запросе учетных данных новой учетной записи введите пароль для DomainAdmin, использованный ранее.</span><span class="sxs-lookup"><span data-stu-id="9b870-251">When prompted for the new account credential, enter the password for the DomainAdmin password you used before.</span></span>
    
  11. <span data-ttu-id="9b870-252">Запустите командлет Set-CcCredential -AccountType VmAdmin, следуя инструкциям ниже.</span><span class="sxs-lookup"><span data-stu-id="9b870-252">Run Set-CcCredential -AccountType VmAdmin as follows:</span></span>
    
       1. <span data-ttu-id="9b870-253">При запросе учетных данных старой учетной записи введите учетные данные, которые использовались с паролем для CceService.</span><span class="sxs-lookup"><span data-stu-id="9b870-253">When prompted for the old account credential, enter the credential you used for the CceService password</span></span>
    
       2. <span data-ttu-id="9b870-254">При запросе учетных данных новой учетной записи введите пароль для VmAdmin, использованный ранее. </span><span class="sxs-lookup"><span data-stu-id="9b870-254">When prompted for the new account credential, enter the password for the VmAdmin password you used before.</span></span> 
    
- <span data-ttu-id="9b870-255">**Проблема: если у вас есть облачный соединитель версии 2,1 или более поздней, то при запуске Register-Ккапплианце или других командлетов на устройстве появляется следующее сообщение об ошибке: "для каждого объекта: невозможно найти свойство" Common "для этого объекта. Убедитесь, что свойство существует. На странице C:\Program Files\WindowsPowerShell\Modules\CloudConnector\Internal\MtHostCommon.ps1:681 char: 14 "**</span><span class="sxs-lookup"><span data-stu-id="9b870-255">**Issue: With Cloud Connector version 2.1 and later, when running Register-CcAppliance or other cmdlets on the appliance, you receive an error message such as: "For Each-Object : The property 'Common' cannot be found on this object. Verify that the property exists. At C:\Program Files\WindowsPowerShell\Modules\CloudConnector\Internal\MtHostCommon.ps1:681 char:14"**</span></span>
    
    <span data-ttu-id="9b870-256">**Решение:** Для облачного соединителя 2,1 и более поздних версий требуется платформа .NET Framework 4.6.1 или более поздней версии.</span><span class="sxs-lookup"><span data-stu-id="9b870-256">**Resolution:** Cloud Connector 2.1 and later requires .NET Framework 4.6.1 or later.</span></span> <span data-ttu-id="9b870-257">Обновите .NET Framework на устройстве с помощью 4.6.1 или более поздней версии, а затем снова запустите командлеты.</span><span class="sxs-lookup"><span data-stu-id="9b870-257">Please update .NET Framework on the appliance to version 4.6.1 or later and run the cmdlet(s) again.</span></span>

- <span data-ttu-id="9b870-258">**Вопрос: с помощью Cloud Connector Edition 2,1 при запуске Install-Ккапплианце появляется следующее сообщение об ошибке: "сбой при установке нового экземпляра с ошибкой: невозможно установить" состояние ", так как только строки можно использовать в качестве значений для задания свойств XmlNode"**</span><span class="sxs-lookup"><span data-stu-id="9b870-258">**Issue: With Cloud Connector Edition 2.1, when running Install-CcAppliance, you receive an error message such as: "Failed to install new instance with error: Cannot set "State" because only strings can be used as values to set XmlNode properties"**</span></span>

   <span data-ttu-id="9b870-259">**Решение:** В Клаудконнектор. ini в разделе [общие] добавьте следующую конфигурацию "состояние": Каунтрикоде = US штат = WA City = Redmond</span><span class="sxs-lookup"><span data-stu-id="9b870-259">**Resolution:** In Cloudconnector.ini, under the [Common] section, please add the “State” config as below:  CountryCode=US  State=WA  City=Redmond</span></span>

   <span data-ttu-id="9b870-260">Значение "State" для строки "состояние" не является обязательным, но строка "состояние" не может быть удалена из файла Клаудконнектор. ini.</span><span class="sxs-lookup"><span data-stu-id="9b870-260">It is not mandatory for the "State" line to have value, however the "State" line cannot be removed from the Cloudconnector.ini file.</span></span>

- <span data-ttu-id="9b870-261">**Причина: сообщение об ошибке "Dismount-Виндовсимаже: Dismount-Виндовсимаже не удалось. Код ошибки = 0xc1550115 "при установке или обновлении Cloud Connector Edition.**</span><span class="sxs-lookup"><span data-stu-id="9b870-261">**Issue: You receive the following error message "Dismount-WindowsImage : Dismount-WindowsImage failed. Error code = 0xc1550115" when installing or upgrading Cloud Connector Edition.**</span></span>
    
    <span data-ttu-id="9b870-262">**Решение:** Запустите консоль PowerShell с правами администратора, запустите "DISM-Cleanup-WIM".</span><span class="sxs-lookup"><span data-stu-id="9b870-262">**Resolution:** Launch a PowerShell console as administrator, run "DISM -Cleanup-Wim'".</span></span> <span data-ttu-id="9b870-263">Произойдет очистка всех изображений с проблемами.</span><span class="sxs-lookup"><span data-stu-id="9b870-263">This will clean up all troubled images.</span></span> <span data-ttu-id="9b870-264">Запустите командлет Install-CcAppliance повторно или дождитесь автоматического обновления.</span><span class="sxs-lookup"><span data-stu-id="9b870-264">Run Install-CcAppliance again or wait for the bits to automatically upgrade.</span></span>
    
- <span data-ttu-id="9b870-265">**Ошибка: не удается развернуть первое устройство облачного соединителя в среде высокой надежности**</span><span class="sxs-lookup"><span data-stu-id="9b870-265">**Issue: Deployment of the first Cloud Connector appliance in an HA environment fails**</span></span>
    
    <span data-ttu-id="9b870-266">**Решение:** Действия, которые вы хотите выполнить, зависят от причины сбоя развертывания.</span><span class="sxs-lookup"><span data-stu-id="9b870-266">**Resolution:** The steps you take depend on the reason the deployment failed:</span></span>
    
  - <span data-ttu-id="9b870-267">Если первое устройство облачного соединителя завершается сбоем и вы не можете определить причину сбоя, необходимо установить устройство еще раз, пока развертывание не завершится успешно, а затем установить другие устройства.</span><span class="sxs-lookup"><span data-stu-id="9b870-267">If the first Cloud Connector appliance fails and you cannot determine the reason for the failure, you must install the appliance again until the deployment is successful, and then install the other appliances.</span></span>
    
  - <span data-ttu-id="9b870-268">Если первое устройство облачного соединителя не проходит из-за незначительной проблемы, например проблемы с внешним сертификатом, возможно, вам удастся устранить проблему без повторной установки устройства.</span><span class="sxs-lookup"><span data-stu-id="9b870-268">If the first Cloud Connector appliance fails with a minor issue, such as an external certificate issue, you might be able to fix the problem without re-installing the appliance.</span></span> <span data-ttu-id="9b870-269">Затем вы можете использовать удаленную оболочку клиента PowerShell, чтобы помечать развертывание как выполненное следующим образом.</span><span class="sxs-lookup"><span data-stu-id="9b870-269">You can then use tenant remote PowerShell to mark the deployment as successful as follows.</span></span> <span data-ttu-id="9b870-270">(Кроме того, если первое развертывание прошло успешно, вы также можете выполнить следующие действия, но по какой-либо причине облачный соединитель не смог сообщить об этом развертывание как успешное.)</span><span class="sxs-lookup"><span data-stu-id="9b870-270">(You can also use the following steps if the first deployment was successful, but, for some reason, Cloud Connector fails to report the deployment as a success.)</span></span>
    
  - <span data-ttu-id="9b870-271">Чтобы получить идентификатор (GUID) первого устройства облачного соединителя, выполните командлет Get-Кшибридпстнапплианце.</span><span class="sxs-lookup"><span data-stu-id="9b870-271">To get the Identity (GUID) of the first Cloud Connector appliance, run the Get-CsHybridPSTNAppliance cmdlet.</span></span>
    
  - <span data-ttu-id="9b870-272">Чтобы помечать устройство как успешно развернутое, выполните параметр SET-Кскцеапплианцедеплойментстатус следующим образом:</span><span class="sxs-lookup"><span data-stu-id="9b870-272">To mark the appliance as successfully deployed, run the Set-CsCceApplianceDeploymentStatus as follows:</span></span>
    
  ```powershell
  Set-CsCceApplianceDeploymentStatus -Identity <Appliance Identity GUID> -Action Deploy -Status Finished
  ```

- <span data-ttu-id="9b870-273">**Проблема. Требуется вручную проверять и устанавливать обновления Windows на сервере узла или виртуальных машинах.**</span><span class="sxs-lookup"><span data-stu-id="9b870-273">**Issue: You need to check for and install Windows updates manually on the host server or virtual machines.**</span></span>
    
   <span data-ttu-id="9b870-p133">**Решение**. Рекомендуется использовать преимущества функции автоматического применения обновлений ОС в составе Skype для бизнеса Cloud Connector Edition. После регистрации устройства для управления через Интернет и включения автоматического обновления ОС сервер узла и виртуальные машины будут проверять и устанавливать обновления Windows автоматически согласно параметрам периода обновления ОС.</span><span class="sxs-lookup"><span data-stu-id="9b870-p133">**Resolution:** We recommend that you take advantage of automated OS updates provided by Skype for Business Cloud Connector Edition. After an appliance is registered for online management and auto OS update is enabled, the host server and virtual machines will check and install Windows Updates automatically according to the OS update time window settings.</span></span>
    
   <span data-ttu-id="9b870-p134">Если вам требуется вручную проверять и устанавливать обновления Windows, выполните процедуру в этом разделе, соответствующую вашему типу развертывания. Необходимо запланировать одновременное обновление сервера узла и выполняющихся на нем виртуальных машин, чтобы свести к минимум время простоя, необходимое для обновления.</span><span class="sxs-lookup"><span data-stu-id="9b870-p134">If you need to check for and install Windows Updates manually, follow the steps in this section that apply to your type of deployment. You should plan on updating both the host server and the virtual machines running on it at the same time to minimize the amount of down time necessary for the updates.</span></span>
    
   <span data-ttu-id="9b870-p135">При желании можно использовать сервер служб WSUS для предоставления обновлений серверам Cloud Connector. Однако необходимо убедиться, что для обновлений Windows **не задана** автоматическая установка.</span><span class="sxs-lookup"><span data-stu-id="9b870-p135">If you prefer, you can use a Windows Server Update Services (WSUS) server to provide updates to Cloud Connector servers. Just be sure to configure the Windows Update to **not** install automatically.</span></span>
    
   <span data-ttu-id="9b870-280">Дополнительные сведения об обновлении развертывания Cloud Connector вручную см. в следующем разделе.</span><span class="sxs-lookup"><span data-stu-id="9b870-280">For information about how to manually update your Cloud Connector deployment, see the following section.</span></span>
    
- <span data-ttu-id="9b870-281">**Вопрос: при обновлении облачного соединителя до новой сборки командлеты облачного соединителя не обновляются.**</span><span class="sxs-lookup"><span data-stu-id="9b870-281">**Issue: When Cloud Connector updates to a new build, Cloud Connector cmdlets are not updated.**</span></span> <span data-ttu-id="9b870-282">Это может произойти, если при выполнении автоматического обновления окно PowerShell остается открытым.</span><span class="sxs-lookup"><span data-stu-id="9b870-282">This sometimes happens if a PowerShell window is left open when automatic update occurs.</span></span>
    
  <span data-ttu-id="9b870-283">**Решение:** Чтобы загрузить обновленные командлеты, выполните одно из указанных ниже действий.</span><span class="sxs-lookup"><span data-stu-id="9b870-283">**Resolution:** To load the updated cmdlets, you can do either of the following steps:</span></span>
    
   - <span data-ttu-id="9b870-284">Закройте PowerShell на устройстве облачного соединителя, а затем снова откройте PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9b870-284">Close PowerShell on the Cloud Connector appliance, and then reopen PowerShell.</span></span>
    
     - <span data-ttu-id="9b870-285">Кроме того, можно выполнить Import-Module Клаудконнектор-Force.</span><span class="sxs-lookup"><span data-stu-id="9b870-285">Or, you can run Import-Module CloudConnector -Force.</span></span> 
 
-   <span data-ttu-id="9b870-286">**Ошибка: "Stop-Ксвиндовссервице" не распознается как имя командлета, функции, файла сценария или программы, которая не может быть запущена. "при попытке выполнить командлет Enter-Ккупдате.**</span><span class="sxs-lookup"><span data-stu-id="9b870-286">**Issue: "The term 'Stop-CsWindowsService' is not recognized as the name of a cmdlet, function, script file, or operable program." error when attempting to run Enter-CcUpdate cmdlet.**</span></span>

    <span data-ttu-id="9b870-287">**Решение:** Удалите файл $HOME \Аппдата\локал\микрософт\виндовс\повершелл\модулеаналисискаче.</span><span class="sxs-lookup"><span data-stu-id="9b870-287">**Resolution:** Delete the $HOME\AppData\Local\Microsoft\Windows\PowerShell\ModuleAnalysisCache file.</span></span>
<span data-ttu-id="9b870-288">Оболочка PowerShell создает этот файл в виде кэша командлетов из найденных модулей, поэтому не нужно каждый раз заново анализировать все модули, так как это сделает что-нибудь очень медленно.</span><span class="sxs-lookup"><span data-stu-id="9b870-288">PowerShell creates this file as a cache of cmdlets from modules that it finds so that it doesn’t have to re-analyze all the modules each time as that would make things really slow.</span></span> <span data-ttu-id="9b870-289">Скорее всего, обнаружено повреждение файлов, которое привело бы к недействительности результатов PowerShell при чтении из кэша.</span><span class="sxs-lookup"><span data-stu-id="9b870-289">Most likely, there was some file corruption that provided misleading results to PowerShell when it was reading back from that cache.</span></span>

-   <span data-ttu-id="9b870-290">**Ошибка: "Import-Module Клаудконнектор" создает ошибку "Import-Module: указанный модуль" Клаудконнектор "не был загружен, так как в каталоге модулей не найден допустимый файл модуля**</span><span class="sxs-lookup"><span data-stu-id="9b870-290">**Issue: “Import-Module CloudConnector” generates error “Import-Module: The specified module “CloudConnector” was not loaded because no valid module file was found in any module directory”**</span></span>

    <span data-ttu-id="9b870-291">**Решение:**</span><span class="sxs-lookup"><span data-stu-id="9b870-291">**Resolution:**</span></span>
    - <span data-ttu-id="9b870-292">Проверка наличия модуля Клаудконнектор в папке c:\Program Филес\виндовсповершелл\модулес</span><span class="sxs-lookup"><span data-stu-id="9b870-292">Validate that indeed the CloudConnector module exists under c:\Program Files\WindowsPowerShell\Modules</span></span>
    
    - <span data-ttu-id="9b870-293">После проверки наличия модуля Клаудконнектор в этом расположении переменная среды Псмодулепас, в которой хранится путь к расположениям модулей, может быть изменена.</span><span class="sxs-lookup"><span data-stu-id="9b870-293">After validating that CloudConnector module exists under this location, the PSModulePath environment variable storing the path to the locations of the modules can be changed:</span></span>
    
     <span data-ttu-id="9b870-294">a)</span><span class="sxs-lookup"><span data-stu-id="9b870-294">a.</span></span> <span data-ttu-id="9b870-295">Временное изменение: запустите PowerShell с правами администратора и выполните следующую команду: $env:P Смодулепас = $env:P Смодулепас + "; C:\Program Филес\виндовсповершелл\модулес\"</span><span class="sxs-lookup"><span data-stu-id="9b870-295">Temporary change: Start Powershell as an Administrator and run the following command: $env:PSModulePath = $env:PSModulePath + ";C:\Program Files\WindowsPowerShell\Modules\"</span></span>
        
     <span data-ttu-id="9b870-296">б)</span><span class="sxs-lookup"><span data-stu-id="9b870-296">b.</span></span> <span data-ttu-id="9b870-297">Чтобы внести постоянные изменения, запустите PowerShell как администратор и выполните следующие команды: $CurrentValue = [Environment]:: Жетенвиронментвариабле ("Псмодулепас", "Machine") Сетенвиронментвариабле ("Псмодулепас"; $CurrentValue C:\Program Филес\виндовсповершелл\модулес "," Machine ")</span><span class="sxs-lookup"><span data-stu-id="9b870-297">For persistent change, Start PowerShell as an Administrator and run the following commands, one by one: $CurrentValue = [Environment]::GetEnvironmentVariable("PSModulePath", "Machine") SetEnvironmentVariable("PSModulePath", $CurrentValue + "; C:\Program Files\WindowsPowerShell\Modules", "Machine")</span></span>

    
## <a name="install-windows-updates-manually"></a><span data-ttu-id="9b870-298">Установка обновлений для Windows вручную</span><span class="sxs-lookup"><span data-stu-id="9b870-298">Install Windows updates manually</span></span>

<span data-ttu-id="9b870-299">Если вы не хотите использовать автоматические обновления в своей среде, выполните эти действия для ручной проверки и применения обновлений Windows.</span><span class="sxs-lookup"><span data-stu-id="9b870-299">If you do not want to use automatic updates in your environment, follow these steps to manually check for and apply Windows updates.</span></span> <span data-ttu-id="9b870-300">Для проверки наличия и установки обновлений для Windows может потребоваться перезапуск сервера.</span><span class="sxs-lookup"><span data-stu-id="9b870-300">Checking for and installing Windows updates may require a server restart.</span></span> <span data-ttu-id="9b870-301">При перезапуске хост-сервера пользователи не смогут использовать облачный соединитель для размещения и приема звонков.</span><span class="sxs-lookup"><span data-stu-id="9b870-301">When a host server is restarting, users will not be able to use Cloud Connector to place or receive calls.</span></span> <span data-ttu-id="9b870-302">Вы можете вручную проверить и установить обновления, указав время их применения, а затем перезагрузить компьютеры по мере необходимости, выбрав периоды, которые позволят избежать перерывов в обслуживании.</span><span class="sxs-lookup"><span data-stu-id="9b870-302">You can manually check for and install updates to control when the updates take place, and then restart the machines as needed during times you choose to avoid disruption of services.</span></span>
  
<span data-ttu-id="9b870-303">Чтобы вручную проверить обновления, подключитесь к каждому серверу узла и откройте **панель управления**.</span><span class="sxs-lookup"><span data-stu-id="9b870-303">To manually check for updates, connect to each host server and open the **Control Panel**.</span></span> <span data-ttu-id="9b870-304">Выберите **система и безопасность \>**, а затем — Управление обновлениями и сервером в соответствии с вашей средой.</span><span class="sxs-lookup"><span data-stu-id="9b870-304">Select **System and Security \>Windows Update**, and then manage the updates and server restarts as appropriate for your environment.</span></span>
  
- <span data-ttu-id="9b870-305">Если на сайте имеется только одно устройство, подключитесь к каждой виртуальной машине и откройте **панель управления**.</span><span class="sxs-lookup"><span data-stu-id="9b870-305">If there is only one appliance in the site, connect to each virtual machine and open the **Control Panel**.</span></span> <span data-ttu-id="9b870-306">Выберите пункт **Обновление Windows \>для системы и безопасность**, а затем настройте обновления и сервер, если это необходимо.</span><span class="sxs-lookup"><span data-stu-id="9b870-306">Select **System and Security \>Windows Update**, and then configure the updates and server restarts as appropriate.</span></span>
    
- <span data-ttu-id="9b870-p143">Если на сайте несколько устройств, обновляемый и перезагружаемый экземпляр будет недоступен для пользователей во время обновления. Пользователи будут подключаться к другим экземплярам в развертывании до тех пор, пока все виртуальные машины и все службы Skype для бизнеса на виртуальных машинах не запустятся после завершения обновления. Чтобы избежать перерывов в обслуживании, можно удалить экземпляр из среды высокой доступности на время применения обновлений, а затем восстановить его. Для этого выполните следующую процедуру.</span><span class="sxs-lookup"><span data-stu-id="9b870-p143">If there are more than one appliance in the site, the instance being updated and restarted cannot be accessed by users during the updates. Users will connect to other instances in the deployment until all virtual machines and all Skype for Business services start on the virtual machines after the updates are completed. To avoid any potential disruption to service, you can remove the instance from HA while you apply the updates, and then restore it when complete. To do so:</span></span>
    
1. <span data-ttu-id="9b870-311">На каждом сервере узла откройте консоль PowerShell от имени администратора.</span><span class="sxs-lookup"><span data-stu-id="9b870-311">On each host server, open a PowerShell console as administrator.</span></span>
    
2. <span data-ttu-id="9b870-312">Удалите экземпляр из среды высокой доступности, используя следующий командлет:</span><span class="sxs-lookup"><span data-stu-id="9b870-312">Remove the instance from HA with the following cmdlet:</span></span>
    
   ```powershell
   Enter-CcUpdate
   ```

3. 
    
    <span data-ttu-id="9b870-313">Выполните процедуру применения обновлений вручную для одного экземпляра и перезапустите виртуальную машину.</span><span class="sxs-lookup"><span data-stu-id="9b870-313">Follow the steps for a single instance to manually apply the updates and restart the virtual machine.</span></span>
    
4. <span data-ttu-id="9b870-314">Верните экземпляр в среду высокой доступности, используя следующий командлет:</span><span class="sxs-lookup"><span data-stu-id="9b870-314">Set the instance back to HA with the following cmdlet:</span></span>
    
   ```powershell
   Exit-CcUpdate
   ```

<span data-ttu-id="9b870-315">Для развертываний с несколькими сайтами выполните процедуру для отдельного сайта для всех сайтов в развертывании, применяя обновления к одному сайту за раз.</span><span class="sxs-lookup"><span data-stu-id="9b870-315">For multi-site deployments, follow the steps for a single site for each site in the deployment, applying updates to one site at a time.</span></span>
  
## <a name="tips-when-installing-anti-virus-software-on-the-cloud-connector-host-machine"></a><span data-ttu-id="9b870-316">Советы по установке антивирусной программы на хост-компьютере облачного соединителя</span><span class="sxs-lookup"><span data-stu-id="9b870-316">Tips when installing anti-virus software on the Cloud Connector host machine</span></span>

<span data-ttu-id="9b870-317">Если вам нужно установить антивирусную программу на хост-компьютере облачного соединителя, необходимо добавить следующие исключения:</span><span class="sxs-lookup"><span data-stu-id="9b870-317">If you need to install anti-virus software on the Cloud Connector host machine, you need to add the following exclusions:</span></span>
  
- <span data-ttu-id="9b870-318">Каталог локального устройства на каждом компьютере.</span><span class="sxs-lookup"><span data-stu-id="9b870-318">Local Appliance Directory on each machine.</span></span>
    
- <span data-ttu-id="9b870-319">Каталог удаленных сайтов на каждом компьютере.</span><span class="sxs-lookup"><span data-stu-id="9b870-319">Remote Site Directory on each machine.</span></span>
    
- <span data-ttu-id="9b870-320">Каталог локального сайта на компьютере содержит корневую папку общего сайта.</span><span class="sxs-lookup"><span data-stu-id="9b870-320">Local Site Directory on the machine hosts the shared site root folder.</span></span>
    
- <span data-ttu-id="9b870-321">%Програмфилес%\скипе для бизнеса Cloud Connector Edition</span><span class="sxs-lookup"><span data-stu-id="9b870-321">%ProgramFiles%\Skype for Business Cloud Connector Edition</span></span>
    
- <span data-ttu-id="9b870-322">%аллусерспрофиле%\клаудконнектор</span><span class="sxs-lookup"><span data-stu-id="9b870-322">%ALLUSERSPROFILE%\CloudConnector</span></span>
    
- <span data-ttu-id="9b870-323">%програмфилес%\виндовсповершелл\модулес\клаудконнектор</span><span class="sxs-lookup"><span data-stu-id="9b870-323">%ProgramFiles%\WindowsPowerShell\Modules\CloudConnector</span></span>
    
- <span data-ttu-id="9b870-324">Процесс Microsoft. RTC. КЦЕ. Манажементсервице. exe.</span><span class="sxs-lookup"><span data-stu-id="9b870-324">The process Microsoft.Rtc.CCE.ManagementService.exe.</span></span>
