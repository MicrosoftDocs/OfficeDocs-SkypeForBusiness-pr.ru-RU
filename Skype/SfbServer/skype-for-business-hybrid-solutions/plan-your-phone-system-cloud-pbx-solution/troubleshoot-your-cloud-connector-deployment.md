---
title: Устранение неполадок с развертыванием Cloud Connector
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 12/5/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: e6cf58cc-dbd9-4f35-a51a-3e2fea71b5a5
description: Устранение неполадок развертывания облака соединителя Edition.
ms.openlocfilehash: b9ade46f46898d22bab862c3044e045de441b007
ms.sourcegitcommit: b2acf18ba6487154ebb4ee46938e96dc56cb2c9a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/09/2019
ms.locfileid: "33864920"
---
# <a name="troubleshoot-your-cloud-connector-deployment"></a><span data-ttu-id="2765c-103">Устранение неполадок с развертыванием Cloud Connector</span><span class="sxs-lookup"><span data-stu-id="2765c-103">Troubleshoot your Cloud Connector deployment</span></span>
 
<span data-ttu-id="2765c-104">Устранение неполадок развертывания облака соединителя Edition.</span><span class="sxs-lookup"><span data-stu-id="2765c-104">Troubleshoot your Cloud Connector Edition deployment.</span></span>
  
<span data-ttu-id="2765c-p101">В этом разделе описываются решения распространенных проблем, связанных с развертываниями Cloud Connector Edition. Если вы сталкиваетесь с проблемами при выполнении и приеме звонков через телефонную сеть общедоступного пользования (ТСОП), ознакомьтесь с возможными решениями, которые приводятся в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="2765c-p101">This topic describes solutions to common issues with Cloud Connector Edition deployments. If you are experiencing issues with calls to and from the Public Switched Telephone Network (PSTN), you can investigate by following the solutions described in this topic.</span></span>
  
<span data-ttu-id="2765c-107">Облако соединитель предоставляет встроенные механизмы для автоматического устранения некоторых проблем.</span><span class="sxs-lookup"><span data-stu-id="2765c-107">Cloud Connector provides built-in mechanisms for automatically resolving some issues.</span></span> <span data-ttu-id="2765c-108">Процесс автоматическое обнаружение ищет потенциальных проблем с appliances облачных соединителя и, если это возможно, вносит исправления для устранения этих проблем без необходимости вмешательства администратора.</span><span class="sxs-lookup"><span data-stu-id="2765c-108">An automatic detection process looks for potential issues with the Cloud Connector appliances, and, if possible, takes corrective action to resolve those issues without the need for administrator intervention.</span></span> <span data-ttu-id="2765c-109">Процесс обнаружения выполняется следующим образом.</span><span class="sxs-lookup"><span data-stu-id="2765c-109">The detection process works as follows:</span></span>
  
- <span data-ttu-id="2765c-110">**Последовательность обнаружения:** Служба управления соединителя облачных запускает процесс обнаружения ли устройства не работает в течение 60 секунд.</span><span class="sxs-lookup"><span data-stu-id="2765c-110">**Detection sequence:** The Cloud Connector Management service runs a process every 60 seconds for detecting whether an appliance is down.</span></span> <span data-ttu-id="2765c-111">В облаке соединителя версии 2.0 и более поздних версий процесс обнаружения использует Скайп переходу Corpnet бизнеса для принятия подключений оболочки PowerShell на компьютерах соединителя облачных; для версий до 2.0 процесс обнаружения использует переключатель управления соединителя облака.</span><span class="sxs-lookup"><span data-stu-id="2765c-111">In Cloud Connector version 2.0 and later, the detection process uses the Skype for Business Corpnet switch for making PowerShell connections to the Cloud Connector machines; for versions previous to 2.0, the detection process uses the Cloud Connector management switch.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="2765c-112">Для автоматического восстановления для успешного выполнения должна быть сетевое подключение между узлом и виртуальными машинами через коммутатор сетевого узла.</span><span class="sxs-lookup"><span data-stu-id="2765c-112">For automatic recovery to succeed, there must be network connectivity between the host and virtual machines over the host network switch.</span></span> <span data-ttu-id="2765c-113">Проверьте подключение к сети, чтобы убедиться, что автоматическое обнаружение и восстановление может быть успешным.</span><span class="sxs-lookup"><span data-stu-id="2765c-113">Be sure to check network connectivity to ensure that automatic detection and recovery can succeed.</span></span> 
  
- <span data-ttu-id="2765c-114">**Мониторинг:** Следующие службы отслеживаемые в облаке соединителя версии 2.0 и более поздних версий:</span><span class="sxs-lookup"><span data-stu-id="2765c-114">**Monitoring:** The following services are monitored in Cloud Connector version 2.0 and later:</span></span>
    
  - <span data-ttu-id="2765c-115">Виртуальные машины не подключены к облачных соединителя корпоративной или виртуальных коммутаторов Internet</span><span class="sxs-lookup"><span data-stu-id="2765c-115">Virtual Machines are not connected to the Cloud Connector Corporate or Internet virtual switches</span></span>
    
  - <span data-ttu-id="2765c-116">Виртуальные машины находятся в состояние сохраненного или остановленные</span><span class="sxs-lookup"><span data-stu-id="2765c-116">Virtual Machines are in a saved or stopped status</span></span>
    
  - <span data-ttu-id="2765c-117">Центральный сервер управления служб: РЕПЛИКИ, образец</span><span class="sxs-lookup"><span data-stu-id="2765c-117">Central Management Server services: REPLICA, MASTER</span></span>
    
  - <span data-ttu-id="2765c-118">Mediation Server services: РЕПЛИКИ, RTCSRV и MEDSVC</span><span class="sxs-lookup"><span data-stu-id="2765c-118">Mediation Server services: REPLICA, RTCSRV and MEDSVC</span></span>
    
  - <span data-ttu-id="2765c-119">Пограничный сервер служб: РЕПЛИКИ, RTCSRV, RTCDATAPROXY, RTCMRAUTH, RTCMEDIARELAY</span><span class="sxs-lookup"><span data-stu-id="2765c-119">Edge Server services: REPLICA, RTCSRV, RTCDATAPROXY, RTCMRAUTH, RTCMEDIARELAY</span></span>
    
  - <span data-ttu-id="2765c-120">Входящий трафик на пограничном сервере, CS RTCMEDSRV на сервер-посредник для CS RTCSRV отключаются правила брандмауэра</span><span class="sxs-lookup"><span data-stu-id="2765c-120">Inbound firewall rules are disabled for CS RTCSRV on Edge server, CS RTCMEDSRV on Mediation server</span></span>
    
    <span data-ttu-id="2765c-121">В облаке соединителя версии 1.4.2 отслеживаемые только следующие службы:</span><span class="sxs-lookup"><span data-stu-id="2765c-121">In Cloud Connector version 1.4.2, only the following services are monitored:</span></span>
    
  - <span data-ttu-id="2765c-122">Mediation Server services: RTCSRV и MEDSVC</span><span class="sxs-lookup"><span data-stu-id="2765c-122">Mediation Server services: RTCSRV and MEDSVC</span></span>
    
  - <span data-ttu-id="2765c-123">Пограничный сервер службы: RTCSRV</span><span class="sxs-lookup"><span data-stu-id="2765c-123">Edge Server service: RTCSRV</span></span>
    
- <span data-ttu-id="2765c-124">**Процесс восстановления:** Если какие-либо отслеживаемые службы не работают, снижении устройства и службы останавливаются и помеченные вручную, пока не будет распознано все проблемы.</span><span class="sxs-lookup"><span data-stu-id="2765c-124">**Recovery process:** If any monitored services are down, an appliance is marked down, and services are stopped and marked manual until all issues can be resolved.</span></span> <span data-ttu-id="2765c-125">Это предотвратит звонки из маршрутизации устройство, которое может стать причиной сбоями вызовов.</span><span class="sxs-lookup"><span data-stu-id="2765c-125">This will prevent calls from routing to an appliance that may cause call failures.</span></span>
    
    <span data-ttu-id="2765c-126">Служба управления соединителя облачных будет пытаться выполнить автоматическое восстановление следующим образом</span><span class="sxs-lookup"><span data-stu-id="2765c-126">The Cloud Connector Management service will retry automatic recovery as follows</span></span>
    
  - <span data-ttu-id="2765c-127">Интервал повтора начальной — каждые 10 секунд с временем максимальный интервал один час.</span><span class="sxs-lookup"><span data-stu-id="2765c-127">The initial retry interval is every ten seconds with a maximum interval time of one hour.</span></span>
    
  - <span data-ttu-id="2765c-128">Для попытки первым трем восстановления промежуток времени — 10 секунд.</span><span class="sxs-lookup"><span data-stu-id="2765c-128">For the first three recovery attempts, the interval time is 10 seconds.</span></span> <span data-ttu-id="2765c-129">Начиная с четвертого retry промежуток времени увеличивается на два раза предыдущей промежуток времени.</span><span class="sxs-lookup"><span data-stu-id="2765c-129">Starting from the fourth retry, the interval time increases by two times the previous interval time.</span></span> <span data-ttu-id="2765c-130">К примеру четвертый retry возникают в 20 секунд, пятой задаче в 40 секунд и так далее.</span><span class="sxs-lookup"><span data-stu-id="2765c-130">For example, the fourth retry will occur in 20 seconds, the fifth in 40 seconds, and so on.</span></span> 
    
  - <span data-ttu-id="2765c-131">При достижении максимальный интервал времени часа повторных попыток будет предоставляться один раз в час.</span><span class="sxs-lookup"><span data-stu-id="2765c-131">When the maximum interval time of one hour is reached, retries will continue once per hour.</span></span>
    
  - <span data-ttu-id="2765c-132">При успешной восстановления счетчики интервал и повторите попытку устанавливаются исходные значения.</span><span class="sxs-lookup"><span data-stu-id="2765c-132">When recovery is successful, the interval and retry counts are set to their initial values.</span></span>
    
  - <span data-ttu-id="2765c-133">При перезапуске службы управления, счетчики интервал и повторите попытку сбрасываются в исходные значения.</span><span class="sxs-lookup"><span data-stu-id="2765c-133">If the Management service is restarted, the interval and retry counts are reset to their initial values.</span></span>
    
## <a name="troubleshooting"></a><span data-ttu-id="2765c-134">Поиск и устранение неполадок</span><span class="sxs-lookup"><span data-stu-id="2765c-134">Troubleshooting</span></span>

<span data-ttu-id="2765c-135">Ниже приведены решения обычно возникают проблемы:</span><span class="sxs-lookup"><span data-stu-id="2765c-135">Following are solutions to commonly encountered issues:</span></span>
  
- <span data-ttu-id="2765c-136">**Проблема. При выполнении сценариев развертывания происходит сбой или остановка развертывания. После выполнения входа на каждую виртуальную машину IP-адрес отсутствует или неверен для внешнего, внутреннего сетевого адаптера или сетевого адаптера управления.**</span><span class="sxs-lookup"><span data-stu-id="2765c-136">**Issue: Deployment fails or stops responding when running the deployment scripts. After logging on to each VM, the IP address is missing or incorrect for the Management/Internal/External NIC.**</span></span>
    
    <span data-ttu-id="2765c-137">**Решение:** Эта проблема не удается разрешить автоматически.</span><span class="sxs-lookup"><span data-stu-id="2765c-137">**Resolution:** This issue cannot be resolved automatically.</span></span> <span data-ttu-id="2765c-138">Сетевые адаптеры нельзя добавить на работающие виртуальные машины.</span><span class="sxs-lookup"><span data-stu-id="2765c-138">NICs cannot be added to VMs while they are running.</span></span> <span data-ttu-id="2765c-139">Завершите работу виртуальных машин и удалите их с помощью диспетчера Hyper-V, а затем выполните следующие командлеты:</span><span class="sxs-lookup"><span data-stu-id="2765c-139">Please shut down and remove these VMs in hyper-v manager, then run the following cmdlets:</span></span>
    
  ```
  Uninstall-CcAppliance
  ```

  ```
  Install-CcAppliance
  ```

- 
    
    <span data-ttu-id="2765c-140">**Проблема. После установки сервера Active Directory Server и леса сервер CMS и (или) сервер-посредник некорректно присоединяются к домену.**</span><span class="sxs-lookup"><span data-stu-id="2765c-140">**Issue: After the Active Directory Server and forest are installed, the CMS Server and/or Mediation Server did not join the domain correctly.**</span></span>
    
    <span data-ttu-id="2765c-141">**Решение**. Чтобы устранить эту проблему, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="2765c-141">**Resolution:** To resolve this issue, take the following steps:</span></span>
    
  - <span data-ttu-id="2765c-142">Войдите на сервер Active Directory и убедитесь, что домен создан правильно.</span><span class="sxs-lookup"><span data-stu-id="2765c-142">Log on to the Active Directory Server and verify that the domain was created correctly.</span></span>
    
  - <span data-ttu-id="2765c-143">Войдите на сервер CMS или сервер-посредник и убедитесь, что сетевому адаптеру корпоративной сети назначен допустимый IP-адрес, а серверу Active Directory назначены допустимый статический IP-адрес и DNS.</span><span class="sxs-lookup"><span data-stu-id="2765c-143">Log on to the CMS/Mediation Server and verify that on the corpnet NIC a valid IP address is assigned, and that valid static IP and DNS is configured as the AD server's IP address.</span></span>
    
  - <span data-ttu-id="2765c-144">Выполните вход на сервер-посредник/CMS и откройте командную строку.</span><span class="sxs-lookup"><span data-stu-id="2765c-144">Log on to the CMS/Mediation Server, and open a command prompt.</span></span> <span data-ttu-id="2765c-145">Выполните проверку связи с сервером Active Directory по полному доменному имени и IP-адресу.</span><span class="sxs-lookup"><span data-stu-id="2765c-145">Make sure you can ping the FQDN and IP address of the Active Directory Server.</span></span> <span data-ttu-id="2765c-146">Если с сервером связаться не удается, это может указывать на конфликт IP-адресов.</span><span class="sxs-lookup"><span data-stu-id="2765c-146">If you cannot, there may be an IP address conflict.</span></span> <span data-ttu-id="2765c-147">Попробуйте назначить серверу новый IP-адрес и изменить параметры DNS на сервере-посреднике или сервере CMS соответствующим образом.</span><span class="sxs-lookup"><span data-stu-id="2765c-147">Please try to assign a new IP for Active Directory and update DNS on the CMS/Mediation server accordingly.</span></span>
    
- <span data-ttu-id="2765c-148">**Проблема: Вы получаете следующее сообщение об ошибке «Remove-VMSwitch: Сбой при удалении виртуального коммутатора Ethernet. Для виртуального коммутатора «Переключиться управления соединителя облако» нельзя удалить так как она используется, выполнив виртуальных машин и назначается пулы дочерних.»**</span><span class="sxs-lookup"><span data-stu-id="2765c-148">**Issue: You receive the following error message, "Remove-VMSwitch : Failed while removing virtual Ethernet switch. The virtual switch 'Cloud Connector Management Switch' cannot be deleted because it is being used by running virtual machines or assigned to child pools."**</span></span>
    
    <span data-ttu-id="2765c-149">**Решение:** «Облако соединителя управления переключатель» не была удалена после развертывания.</span><span class="sxs-lookup"><span data-stu-id="2765c-149">**Resolution:** The "Cloud Connector Management Switch" was not deleted after the deployment.</span></span> <span data-ttu-id="2765c-150">Если возникает эта ошибка, перейдите в диспетчер Hyper-V и убедитесь в отсутствии виртуальных машин, подключенных к этому коммутатору.</span><span class="sxs-lookup"><span data-stu-id="2765c-150">If you hit this error, please go to Hyper-v manager and verify that there is not still a virtual machine still connected to it.</span></span> <span data-ttu-id="2765c-151">При необходимости отключите подключенные виртуальные машины и удалите коммутатор управления.</span><span class="sxs-lookup"><span data-stu-id="2765c-151">If there are virtual machines still connected, disconnect them and delete the management switch.</span></span> <span data-ttu-id="2765c-152">Если удалить его по-прежнему не удается, перезапустите сервер узла и повторите попытку.</span><span class="sxs-lookup"><span data-stu-id="2765c-152">If the management switch still cannot be deleted, restart the host server and try again.</span></span>
    
- <span data-ttu-id="2765c-153">**Проблема: Вы получаете следующее сообщение об ошибке, «RTCMRAUTH не удается запустить службу. Проверьте, убедитесь, что службы не отключены.»**</span><span class="sxs-lookup"><span data-stu-id="2765c-153">**Issue: You receive the following error message, "Service RTCMRAUTH failed to start. Check to make sure the service is not disabled."**</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="2765c-154">Эту проблему применяется только к версии облачных соединителя раньше, чем 1.4.2.</span><span class="sxs-lookup"><span data-stu-id="2765c-154">This issue only applies to Cloud Connector versions earlier than 1.4.2.</span></span> 
  
    <span data-ttu-id="2765c-p110">Причиной сбоя запуска может быть предыдущая отработка отказа этого сервера переднего плана (путем отработки отказа компьютера). В этом случае выполните откат (откат компьютера).</span><span class="sxs-lookup"><span data-stu-id="2765c-p110">The failure to start could also be because this Front End server was previously failed over (using computer fail over). If that's the case, please invoke fail back (using computer fail back).</span></span>
    
    <span data-ttu-id="2765c-p111">**Решение**. Эта проблема возникает на пограничном сервере, если пограничный сервер не доверяет сертификату корневого ЦС или промежуточного ЦС. Даже в том случае, если можно импортировать внешний сертификат, но цепочка сертификатов нарушена, службу RTCMRAUTH и (или) RTCSRV запустить невозможно.</span><span class="sxs-lookup"><span data-stu-id="2765c-p111">**Resolution:** This issue happens on an Edge Server when the root CA certificate or intermediate CA certificate is not trusted by the Edge Server. Even if the external certificate can be imported but the certificate chain is broken. Under this condition, the RTCMRAUTH and/or RTCSRV service can not start.</span></span>
    
    <span data-ttu-id="2765c-p112">Вручную импортируйте сертификат корневого ЦС или все сертификаты промежуточных ЦС внешнего сертификата на пограничный сервер, а затем перезапустите его. После запуска служб RTCMRAUTH и RTCSRV на пограничном сервере вернитесь на сервер узла, запустите консоль PowerShell от имени администратора и выполните следующий командлет, чтобы переключиться на новое развертывание:</span><span class="sxs-lookup"><span data-stu-id="2765c-p112">Please import the root CA certificate and all intermediate CA certificates of your external certificate manually into the Edge Server and then restart the Edge Server. After you see the RTCMRAUTH and RTCSRV services started on the Edge Server, go back to your host server, launch a PowerShell console as administrator, and run following cmdlet to switch to the new deployment:</span></span>
    
  ```
  Switch-CcVersion
  ```

- 
    
    <span data-ttu-id="2765c-162">**Проблема. Сервер узла перезапускается после применения обновлений Windows, и происходит сбой вызовов, обслуживаемых этим сервером.**</span><span class="sxs-lookup"><span data-stu-id="2765c-162">**Issue: The host server was restarted when Windows updates were applied, and calls serviced by the server are failing.**</span></span>
    
    <span data-ttu-id="2765c-p113">**Решение**. Если развернута среда высокой доступности, Microsoft предоставляет командлет для переноса одного хост-компьютера (экземпляра развертывания) в текущую топологию или из нее при проверке и установке обновления для Windows вручную. Для этого выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="2765c-p113">**Resolution:** If you deployed a high availability environment, Microsoft provides a cmdlet to help move one host machine (deployment instance) into or out of the current topology when you check and install Windows update manually. Use the following steps to accomplish this:</span></span>
    
1. <span data-ttu-id="2765c-165">На сервере узла запустите консоль PowerShell от имени администратора, а затем выполните команду:</span><span class="sxs-lookup"><span data-stu-id="2765c-165">On the host server, start a PowerShell console as administrator, then run:</span></span>
    
   ```
   Enter-CcUpdate
   ```

2. <span data-ttu-id="2765c-166">Проверьте наличие обновлений и установите доступные обновления.</span><span class="sxs-lookup"><span data-stu-id="2765c-166">Check for updates and install any that are available.</span></span>
    
3. <span data-ttu-id="2765c-167">В консоли PowerShell запустите следующий командлет:</span><span class="sxs-lookup"><span data-stu-id="2765c-167">In the PowerShell console, run the following cmdlet:</span></span>
    
   ```
   Exit-CcUpdate
   ```

- 
    
    <span data-ttu-id="2765c-168">**Проблема. При выполнении звонка из клиента Skype для бизнеса с использованием номера ТСОП невозможно повысить уровень звонка до конференции, пригласив к участию в нем другой номер ТСОП**.</span><span class="sxs-lookup"><span data-stu-id="2765c-168">**Issue: When a call is made from a Skype for Business client using a PSTN number, the call cannot be escalated to a conference by inviting another PSTN number.**</span></span>
    
    <span data-ttu-id="2765c-169">**Решение:** Чтобы устранить эту проблему, видеть [online гибридного настроить параметры сервера-посредника](configure-cloud-connector-integration-with-your-office-365-tenant.md#BKMK_ConfigureMediationServer).</span><span class="sxs-lookup"><span data-stu-id="2765c-169">**Resolution:** To resolve this issue, see [Configure online hybrid Mediation Server Settings](configure-cloud-connector-integration-with-your-office-365-tenant.md#BKMK_ConfigureMediationServer).</span></span>
    
- <span data-ttu-id="2765c-170">**Проблема. При установке сервера Active Directory отображается предупреждение о Центре обновления Windows: «Автоматическое обновление Windows отключено. Чтобы обеспечить автоматическое обновление только что установленной роли или компонента, включите Центр обновления Windows».**</span><span class="sxs-lookup"><span data-stu-id="2765c-170">**Issue: A warning message is displayed about Windows Update when you are installing Active Directory server - "Windows automatic updating is not enabled. To ensure that your newly-installed role or feature is automatically updated, turn on Windows Update."**</span></span>
    
    <span data-ttu-id="2765c-171">**Решение:** Запустить сеанс удаленной оболочки PowerShell клиента с помощью Скайп for Business учетные данные администратора клиента, а затем выполните следующий командлет, чтобы проверить конфигурацию _EnableAutoUpdate_ узла:</span><span class="sxs-lookup"><span data-stu-id="2765c-171">**Resolution:** Launch a Tenant Remote PowerShell session using Skype for Business tenant admin credentials, then run the following cmdlet to check the _EnableAutoUpdate_ configuration of your site:</span></span>
    
  ```
  Get-CsHybridPSTNSite
  ```

    <span data-ttu-id="2765c-172">Если _EnableAutoUpdate_ задано значение **True**, можно игнорировать это предупреждение, так как служба CCEManagement будет обрабатывать загрузку и установку обновлений Windows для виртуальных машин и хост-сервера.</span><span class="sxs-lookup"><span data-stu-id="2765c-172">If  _EnableAutoUpdate_ is set to **True**, you can safely ignore this warning message because the CCEManagement service will handle downloading and installing Windows updates for both virtual machines and the host server.</span></span> <span data-ttu-id="2765c-173">Если _EnableAutoUpdate_ задано значение **False**, запустите следующий командлет, чтобы присвоить значение **True**.</span><span class="sxs-lookup"><span data-stu-id="2765c-173">If  _EnableAutoUpdate_ is set to **False**, run following cmdlet to set it to **True**.</span></span>
    
  ```
  Set-CsHybridPSTNSite -EnableAutoUpdate $true
  ```

    <span data-ttu-id="2765c-174">Кроме того можно вручную проверить для и установки обновлений.</span><span class="sxs-lookup"><span data-stu-id="2765c-174">Alternatively, you can manually check for and install updates.</span></span> <span data-ttu-id="2765c-175">Содержится в следующем разделе.</span><span class="sxs-lookup"><span data-stu-id="2765c-175">See the next section.</span></span>
    
- <span data-ttu-id="2765c-176">**Проблема: Вы получаете сообщение об ошибке: не удалось зарегистрировать устройства, так как входные данные и конфигурацию \<SiteName\> или \<имя устройства\> или \<полное доменное имя сервера посредника\> или \<IP-адрес сервера посредника \> конфликтует с существующей appliance(s). Удалите устройство для конфликта или обновление сведений о входных данных и конфигурации, затем повторно зарегистрировать. "при запуске Register-CcAppliance для регистрации текущего устройства для обеспечения связи в сети.**</span><span class="sxs-lookup"><span data-stu-id="2765c-176">**Issue: You receive an error message: Cannot register appliance because your current input/configuration \<SiteName\> or \<ApplianceName\> or \<Mediation Server FQDN\> or \<Mediation Server IP Address\> conflicts with existing appliance(s). Remove conflict appliance or update your input/configuration information then register again. ' when run Register-CcAppliance to register current appliance to online.**</span></span>
    
    <span data-ttu-id="2765c-177">**Решение:** Значением параметра \<имя устройства\>, \<полное доменное имя сервера посредника\> и \<IP-адрес сервера посредника\> должен быть уникальным и только для регистрации одно устройство.</span><span class="sxs-lookup"><span data-stu-id="2765c-177">**Resolution:** Values for the \<ApplianceName\>, \<Mediation Server FQDN\> and \<Mediation Server IP Address\> must be unique and only used for one appliance registration.</span></span> <span data-ttu-id="2765c-178">По умолчанию \<имя устройства\> , поступающие из имени узла.</span><span class="sxs-lookup"><span data-stu-id="2765c-178">By default, \<ApplianceName\> comes from the host name.</span></span> <span data-ttu-id="2765c-179">\<Полное доменное имя сервера посредника\> и \<IP-адрес сервера посредника\> определенные в файле конфигурации ini.</span><span class="sxs-lookup"><span data-stu-id="2765c-179">\<Mediation Server FQDN\> and \<Mediation Server IP Address\> defined in configuration ini file.</span></span>
    
    <span data-ttu-id="2765c-180">Например, при использовании (ApplianceName= MyserverNew, Mediation Server FQDN=ms.contoso.com, Mediation Server IP Address=10.10.10.10) для регистрации на сайте SiteName=MySite, если существует зарегистрированное устройство (ApplianceName= Myserver, Mediation Server FQDN=ms.contoso.com, Mediation Server IP Address=10.10.10.10), возникнет конфликт.</span><span class="sxs-lookup"><span data-stu-id="2765c-180">For example, using (ApplianceName= MyserverNew, Mediation Server FQDN=ms.contoso.com, Mediation Server IP Address=10.10.10.10) to register to SiteName=MySite, but if there is a registered appliance (ApplianceName= Myserver, Mediation Server FQDN=ms.contoso.com, Mediation Server IP Address=10.10.10.10), you will have the conflict.</span></span>
    
    <span data-ttu-id="2765c-181">Прежде всего проверьте файл CloudConnector.ini в каталоге ApplianceRoot.</span><span class="sxs-lookup"><span data-stu-id="2765c-181">First, please check your CloudConnector.ini file in ApplianceRoot directory section.</span></span> <span data-ttu-id="2765c-182">Вы получите \<SiteName\>, \<полное доменное имя сервера посредника\> и \<IP-адрес сервера посредника\> значения в файле.</span><span class="sxs-lookup"><span data-stu-id="2765c-182">You will get \<SiteName\>, \<Mediation Server FQDN\> and \<Mediation Server IP Address\> values in the file.</span></span> <span data-ttu-id="2765c-183">\<Имя устройства\> — это имя хост-сервера.</span><span class="sxs-lookup"><span data-stu-id="2765c-183">\<ApplianceName\> is your host server name.</span></span>
    
    <span data-ttu-id="2765c-184">Во-вторых запуска клиента удаленной оболочки PowerShell с помощью вашего Скайп for Business учетные данные администратора клиента, запустите следующий командлет, чтобы проверить зарегистрированных appliance(s).</span><span class="sxs-lookup"><span data-stu-id="2765c-184">Second, Launch Tenant Remote PowerShell using your Skype for Business tenant admin credentials, then run the following cmdlet to check the registered appliance(s).</span></span>
    
  ```
  Get-CsHybridPSTNAppliance
  ```

    <span data-ttu-id="2765c-185">После обнаружения конфликтов вы можете обновить файл CloudConnector.ini, включив в него данные зарегистрированного устройства, или отменить регистрацию существующего устройства для устранения конфликтов.</span><span class="sxs-lookup"><span data-stu-id="2765c-185">After identifying any conflicts, you can either update your CloudConnector.ini file with information that matches the registered appliance, or unregister the existing appliance to resolve the conflicts.</span></span>
    
  ```
  Unregister-CsHybridPSTNAppliance -Force
  ```

    
- <span data-ttu-id="2765c-186">**Проблема: Командлет Get-CcRunningVersion возвращает пустое значение, при наличии развернутого устройства, размещенных на нем.**</span><span class="sxs-lookup"><span data-stu-id="2765c-186">**Issue: The Get-CcRunningVersion cmdlet returns an empty value if there is a deployed appliance running on the host.**</span></span>
    
  <span data-ttu-id="2765c-187">**Решение:** Это может произойти при обновлении от 1.3.4 или 1.3.8 для версии 1.4.1.</span><span class="sxs-lookup"><span data-stu-id="2765c-187">**Resolution:** This can happen when you upgrade from 1.3.4 or 1.3.8 to 1.4.1.</span></span> <span data-ttu-id="2765c-188">После установки версии версии 1.4.1 с MSI-файла, необходимо запустить `Register-CcAppliance` перед запуском любым другим командлетом.</span><span class="sxs-lookup"><span data-stu-id="2765c-188">After you install version 1.4.1 with the .msi, you must run `Register-CcAppliance` before you run any other cmdlet.</span></span> <span data-ttu-id="2765c-189">`Register-CcAppliance`будет переноситься файл module.ini из %UserProfile%\CloudConnector % ProgramData%\CloudConnector.</span><span class="sxs-lookup"><span data-stu-id="2765c-189">`Register-CcAppliance` will migrate the module.ini file from %UserProfile%\CloudConnector to %ProgramData%\CloudConnector.</span></span> <span data-ttu-id="2765c-190">Если пропустить этот шаг, в папке %ProgramData%\CloudConnector будет создан новый файл module.ini, который заменит сведения о выполняющейся или резервной версии для 1.3.4 или 1.3.8.</span><span class="sxs-lookup"><span data-stu-id="2765c-190">If you missed it, a new module.ini will be created in %ProgramData%\CloudConnector folder and replace the running/backup version information for 1.3.4 or 1.3.8.</span></span>
    
  <span data-ttu-id="2765c-191">Сравните файлы module.ini в папках %UserProfile%\CloudConnector и %ProgramData%\CloudConnector.</span><span class="sxs-lookup"><span data-stu-id="2765c-191">Compare module.ini files in %UserProfile%\CloudConnector and %ProgramData%\CloudConnector folder.</span></span> <span data-ttu-id="2765c-192">Если имеются различия, удалите файл module.ini в %ProgramData%\CloudConnector и повторить `Register-CcAppliance`.</span><span class="sxs-lookup"><span data-stu-id="2765c-192">If there are differences, delete the module.ini file in %ProgramData%\CloudConnector and rerun  `Register-CcAppliance`.</span></span> <span data-ttu-id="2765c-193">Можно также изменить файл вручную для правильного выполнения и резервной версии.</span><span class="sxs-lookup"><span data-stu-id="2765c-193">You could also modify the file manually to the correct running and backup version.</span></span>
    
- <span data-ttu-id="2765c-194">**Проблема: После выполнения командлета переключатель CcVersion Чтобы переключиться в старой версии, в которой отличается от текущей версии сценария не поддерживается высокой доступности для этого старой версии.**</span><span class="sxs-lookup"><span data-stu-id="2765c-194">**Issue: After you run the Switch-CcVersion cmdlet to switch to an old version which is different from current script version, there is no High Availability support for this old version.**</span></span>
    
    <span data-ttu-id="2765c-195">**Решение:** Например, для обновления от версии 1.4.1 до 1.4.2.</span><span class="sxs-lookup"><span data-stu-id="2765c-195">**Resolution:** For example, you have upgraded from 1.4.1 to 1.4.2.</span></span> <span data-ttu-id="2765c-196">Текущая версия скрипта, который можно определить, выполнив `Get-CcVersion`и на выполнение, которое можно получить, запустив `Get-CcRunningVersion` являются оба 1.4.2.</span><span class="sxs-lookup"><span data-stu-id="2765c-196">Your current script version, which can be determined by running `Get-CcVersion`, and your running version, which can be determined by running  `Get-CcRunningVersion` are both 1.4.2.</span></span> <span data-ttu-id="2765c-197">В настоящее время, если вы выполняете `Switch-CcVersion` для переключения используемой версии версии 1.4.1, затем будет не поддерживается высокой доступности для этого старой версии.</span><span class="sxs-lookup"><span data-stu-id="2765c-197">At this time, if you run `Switch-CcVersion` to switch the running version back to 1.4.1, then there will be no High Availability support for this old version.</span></span>
    
    <span data-ttu-id="2765c-p121">Чтобы получить полную поддержку высокой готовности, вернитесь к версии 1.4.2 (запущенная версия и версия скрипта должны быть одинаковыми). При возникновении проблем с развертыванием версии 1.4.2 удалите и повторно установите ее.</span><span class="sxs-lookup"><span data-stu-id="2765c-p121">To get full High Availability support, please switch back to 1.4.2, so the running version and script version are the same. If you are experiencing problems with your 1.4.2 deployment, please uninstall and reinstall it as soon as possible.</span></span>
    
- <span data-ttu-id="2765c-200">**Проблема. Срок действия сертификатов, выданных центром сертификации, или внутренних сертификатов, выданных серверу центрального хранилища управления (CMS), серверу-посреднику или пограничному серверу, истекает, либо они скомпрометированы.**</span><span class="sxs-lookup"><span data-stu-id="2765c-200">**Issue: Certificate authority certificates or internal certificates issued to Central Management Store, Mediation Server, and Edge Server are near expiration or are compromised.**</span></span>
    
    <span data-ttu-id="2765c-p122">**Решение.** Сертификаты Skype для бизнеса, выданные центром сертификации, действуют в течение пяти лет. Внутренние сертификаты, выданные серверу центрального хранилища управления (CMS), серверу-посреднику или пограничному серверу, действуют в течение двух лет.</span><span class="sxs-lookup"><span data-stu-id="2765c-p122">**Resolution:** Skype for Business certification authority certificates are valid for five years. Internal certificates issued to the Central Management Store, Mediation Server, and Edge Server are valid for two years.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="2765c-203">В облаке соединителя версии 2.0 и более поздних версий командлет обновления CcServerCertificate изменилось на CcServerCertificate обновления и командлет CcCACertificate обновления на обновление CcCACertificate.</span><span class="sxs-lookup"><span data-stu-id="2765c-203">In Cloud Connector version 2.0 and later, the Renew-CcServerCertificate cmdlet has changed to Update-CcServerCertificate and the Renew-CcCACertificate cmdlet has changed to Update-CcCACertificate.</span></span> 
  
    <span data-ttu-id="2765c-204">Если внутренний сертификаты, выданные центрального хранилища управления, сервер-посредник и пограничного сервера, срок действия или атаке, выполните командлет Update-CcServerCertificate или CcServerCertificate обновления для обновления сертификатов.</span><span class="sxs-lookup"><span data-stu-id="2765c-204">If internal certificates issued to the Central Management Store, Mediation Server, and Edge Server are near expiration or compromised, run the Renew-CcServerCertificate or Update-CcServerCertificate cmdlet to renew your certificates.</span></span>
    
    <span data-ttu-id="2765c-205">Если срок действия сертификатов центра сертификации, выполните командлет CcCACertificate обновления или обновления CcCACertificate для обновления сертификатов.</span><span class="sxs-lookup"><span data-stu-id="2765c-205">If certification authority certificates are near expiration, run the Renew-CcCACertificate or Update-CcCACertificate cmdlet to renew your certificates.</span></span>
    
    <span data-ttu-id="2765c-206">**Если скомпрометированы сертификаты центра сертификации и имеется только одно устройство для сайта,** выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="2765c-206">**If certification authority certificates are compromised and there is only one appliance in the site,** perform the following steps:</span></span>
    
1. <span data-ttu-id="2765c-207">Выполните командлет Enter-CcUpdate, чтобы очистить службы и перевести устройство в режим обслуживания.</span><span class="sxs-lookup"><span data-stu-id="2765c-207">Run the Enter-CcUpdate cmdlet to drain services and put the appliance in maintenance mode.</span></span>
   
   ```
   Enter-CcUpdate
   ```
   
2. <span data-ttu-id="2765c-208">Выполните следующие командлеты, чтобы сбросить и создать новые сертификаты центра сертификации, а также все внутренние сертификаты.</span><span class="sxs-lookup"><span data-stu-id="2765c-208">Run the following cmdlets to reset and create new certification authority certificates and all internal server certificates:</span></span>
    
    <span data-ttu-id="2765c-209">Для соединителя облачных предыдущих выпусках 2.0:</span><span class="sxs-lookup"><span data-stu-id="2765c-209">For Cloud Connector releases before 2.0:</span></span>
    
    ```
    Reset-CcCACertificate 
    Renew-CcServerCertificate 
    Remove-CcLegacyServerCertificate 
    ```

    <span data-ttu-id="2765c-210">Или для соединителя облачных версии 2.0 и более поздних версий:</span><span class="sxs-lookup"><span data-stu-id="2765c-210">Or for Cloud Connector release 2.0 and later:</span></span>
    
    ```
    Reset-CcCACertificate 
    Update-CcServerCertificate 
    Remove-CcLegacyServerCertificate 
    ```
    
3. <span data-ttu-id="2765c-211">Если протокол TLS используется между шлюзом и сервера-посредника, выполните командлет Export-CcRootCertificate из устройства, а затем установите экспортированный сертификат для шлюзов PSTN.</span><span class="sxs-lookup"><span data-stu-id="2765c-211">If TLS is used between the gateway and the Mediation Server, run the Export-CcRootCertificate cmdlet from the appliance, and then install the exported certificate to your PSTN gateways.</span></span> <span data-ttu-id="2765c-212">Вам может потребоваться повторное выдаст сертификат на шлюз.</span><span class="sxs-lookup"><span data-stu-id="2765c-212">You may also be required to re-issue the certificate on your gateway.</span></span>

   ```
   Export-CcRootCertificate
   ```

4. <span data-ttu-id="2765c-213">Выполните командлет CcUpdate выхода для запуска служб и выйти из режима обслуживания.</span><span class="sxs-lookup"><span data-stu-id="2765c-213">Run the Exit-CcUpdate cmdlet to start services and exit maintenance mode.</span></span>

   ```
   Exit-CcUpdate
   ```


    <span data-ttu-id="2765c-214">**Если скомпрометированы сертификаты центра сертификации и существует несколько устройств на сайте,** выполните следующие действия последовательных на каждом устройстве на сайте.</span><span class="sxs-lookup"><span data-stu-id="2765c-214">**If certification authority certificates are compromised and there are multiple appliances in the site,** perform the following sequential steps on each appliance in the site.</span></span>
    
    <span data-ttu-id="2765c-215">Корпорация Майкрософт рекомендует, выполните следующие действия в периоды наименьшей использования.</span><span class="sxs-lookup"><span data-stu-id="2765c-215">Microsoft recommends that you perform these steps during non-peak usage times.</span></span>
    
1. <span data-ttu-id="2765c-216">На первом устройстве, используйте командлет Remove-CcCertificationAuthorityFile для очистки ЦС резервного копирования файлов в \<SiteRoot\> каталога.</span><span class="sxs-lookup"><span data-stu-id="2765c-216">On the first appliance, run the Remove-CcCertificationAuthorityFile cmdlet to clean up the CA backup files in the \<SiteRoot\> directory.</span></span>

     ```
     Remove-CcCertificationAuthorityFile
     ```
    
2. <span data-ttu-id="2765c-217">Выполните командлет CcUpdate ввод для извлечения служб и поместить каждого устройства для обеспечения связи в режиме обслуживания.</span><span class="sxs-lookup"><span data-stu-id="2765c-217">Run the Enter-CcUpdate cmdlet to drain services and put each appliance in maintenance mode.</span></span>

     ```
     Enter-CcUpdate
     ```
    
3. <span data-ttu-id="2765c-218">На первом устройстве выполните следующие командлеты сбросить и создать новые сертификаты центра сертификации и все сертификаты внутреннего сервера:</span><span class="sxs-lookup"><span data-stu-id="2765c-218">On the first appliance, run the following cmdlets to reset and create new certification authority certificates and all internal server certificates:</span></span>
    
     <span data-ttu-id="2765c-219">Для соединителя облачных предыдущих выпусках 2.0:</span><span class="sxs-lookup"><span data-stu-id="2765c-219">For Cloud Connector releases before 2.0:</span></span>
    
     ```
     Reset-CcCACertificate
     Renew-CcServerCertificate
     Remove-CcLegacyServerCertificate 
     ```

     <span data-ttu-id="2765c-220">Или для соединителя облачных версии 2.0 и более поздних версий:</span><span class="sxs-lookup"><span data-stu-id="2765c-220">Or for Cloud Connector release 2.0 and later:</span></span>
    
     ```
     Reset-CcCACertificate
     Update-CcServerCertificate
     Remove-CcLegacyServerCertificate 
     ```

4. <span data-ttu-id="2765c-221">На первом appliance запустите следующий командлет, чтобы выполнить резервное копирование файлов центра сертификации для \<SiteRoot\> папки.</span><span class="sxs-lookup"><span data-stu-id="2765c-221">On the first appliance, run the following cmdlet to back up the CA files to the \<SiteRoot\> folder.</span></span>
    
     ```
     Backup-CcCertificationAuthority
     ```
   
5. <span data-ttu-id="2765c-222">На все другие устройства для на том же сайте выполните следующие команды, чтобы использовать резервные копии ЦС, чтобы все используют один и тот же сертификат корневого устройства, а затем запрос новых сертификатов.</span><span class="sxs-lookup"><span data-stu-id="2765c-222">On all other appliance's in the same site, run the following commands to consume the CA backup files, so that the appliances all use the same root certificate, and then request new certificates.</span></span> 
   
     ```
     Reset-CcCACertificate
     Update-CcServerCertificate
     Remove-CcLegacyServerCertificate 
     ```
     
6. <span data-ttu-id="2765c-223">Если протокол TLS используется между шлюзом и сервера-посредника, выполните командлет Export-CcRootCertificate из любого устройства на сайте, а затем установите экспортированный сертификат для шлюзов PSTN.</span><span class="sxs-lookup"><span data-stu-id="2765c-223">If TLS is used between the gateway and the Mediation Server, run the Export-CcRootCertificate cmdlet from any appliance in the site, and then install the exported certificate to your PSTN gateways.</span></span> <span data-ttu-id="2765c-224">Вам может потребоваться повторное выдаст сертификат на шлюз.</span><span class="sxs-lookup"><span data-stu-id="2765c-224">You may also be required to re-issue the certificate on your gateway.</span></span>
  
     ```
     Export-CcRootCertificate
     ```
     
7. <span data-ttu-id="2765c-225">Выполните командлет CcUpdate выхода для запуска служб и выйти из режима обслуживания.</span><span class="sxs-lookup"><span data-stu-id="2765c-225">Run the Exit-CcUpdate cmdlet to start services and exit maintenance mode.</span></span> 

     ```
     Exit-CcUpdate
     ```
    
    
- <span data-ttu-id="2765c-226">**Проблема: Вы получаете следующее сообщение об ошибке в журнале службы управления соединителя облаке, «C:\Program Files\Skype для Business Cloud соединителя Edition\ManagementService\CceManagementService.log»: ошибка CceService: 0: непредвиденное исключение при сообщения о состоянии на online: System.Management.Automation.CmdletInvocationException: не удалось выполнить вход для пользователя \<глобального администратора клиента\>. Создайте новый объект учетных данных, убедившись, что используется правильное имя пользователя и пароль. ---\>**</span><span class="sxs-lookup"><span data-stu-id="2765c-226">**Issue: You receive the following error message in the Cloud Connector Management Service Log, "C:\Program Files\Skype for Business Cloud Connector Edition\ManagementService\CceManagementService.log": CceService Error: 0 : Unexpected exception when reporting status to online: System.Management.Automation.CmdletInvocationException: Logon failed for the user \<Global Tenant Admin\>. Please create a new credential object, making sure that you have used the correct user name and password. ---\>**</span></span>
    
    <span data-ttu-id="2765c-227">**Решение:** Учетные данные администратора глобального клиента Office 365 были изменены с момента appliance соединителя облачных была зарегистрирована.</span><span class="sxs-lookup"><span data-stu-id="2765c-227">**Resolution:** The Office 365 global tenant admin credentials have been changed since the Cloud Connector appliance was registered.</span></span> <span data-ttu-id="2765c-228">Для обновления локально сохраненных учетных данных на устройстве облачных соединителя, выполните следующие от администратора PowerShell на устройстве узла:</span><span class="sxs-lookup"><span data-stu-id="2765c-228">To update the locally stored credentials on the Cloud Connector appliance, run the following from Administrator PowerShell on the host appliance:</span></span>
    
  ```
  Set-CcCredential -AccountType TenantAdmin
  ```

- <span data-ttu-id="2765c-229">**Проблема: После изменения пароля для учетной записи сервера узла, используется для развертывания, появляется следующее сообщение об ошибке: «ConvertTo-SecureString: недопустимый ключ для использования в указанном состоянии.» в %ProgramFiles%\Skype для Cloud Business Connector Edition\ManagementService\CceManagementService.log или во время выполнения командлета Get-CcCredential.**</span><span class="sxs-lookup"><span data-stu-id="2765c-229">**Issue: After you change the password for the host server account you used for the deployment, you receive the following error message: "ConvertTo-SecureString : Key not valid for use in specified state." in %ProgramFiles%\Skype for Business Cloud Connector Edition\ManagementService\CceManagementService.log or while running the Get-CcCredential cmdlet.**</span></span>
    
    <span data-ttu-id="2765c-230">**Решение:** Все облака соединителя учетные данные хранятся в следующий файл: «% SystemDrive%\Programdata\Cloudconnector\credentials. \<CurrentUser\>.xml».</span><span class="sxs-lookup"><span data-stu-id="2765c-230">**Resolution:** All Cloud Connector credentials are stored in the following file: "%SystemDrive%\Programdata\Cloudconnector\credentials.\<CurrentUser\>.xml".</span></span> <span data-ttu-id="2765c-231">При изменении пароля на сервере узла необходимо обновить учетные данные, сохраненные локально.</span><span class="sxs-lookup"><span data-stu-id="2765c-231">When the password on the host server changes, you will need to update the locally stored credentials.</span></span>
    
    <span data-ttu-id="2765c-232">**При запуске Cloud Connector версии 1.4.2,** повторно создайте все пароли Cloud Connector, выполнив следующие действия.</span><span class="sxs-lookup"><span data-stu-id="2765c-232">**If you are running Cloud Connector version 1.4.2,** regenerate all Cloud Connector passwords by following these steps:</span></span>
    
  1. <span data-ttu-id="2765c-233">Перезапустите сервер узла.</span><span class="sxs-lookup"><span data-stu-id="2765c-233">Restart the host server.</span></span>
    
  2. <span data-ttu-id="2765c-234">Удалите следующий файл: «% SystemDrive%\Programdata\Cloudconnector\credentials. \<CurrentUser\>.xml».</span><span class="sxs-lookup"><span data-stu-id="2765c-234">Delete the following file: "%SystemDrive%\Programdata\Cloudconnector\credentials.\<CurrentUser\>.xml".</span></span>
    
  3. <span data-ttu-id="2765c-235">Запуск консоли PowerShell от имени администратора и запустите «Register CcAppliance-локальный» повторного ввода после описания службы и паролей.</span><span class="sxs-lookup"><span data-stu-id="2765c-235">Launch a PowerShell console as administrator, and then run "Register-CcAppliance -Local" to re-enter the passwords following the description.</span></span> <span data-ttu-id="2765c-236">Введите те же пароли, которые были указаны ранее для развертывания Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="2765c-236">Enter the same passwords you entered before for the Cloud Connector deployment.</span></span>
    
     <span data-ttu-id="2765c-237">**При использовании соединителя облачных версии 2.0 или более поздней версии,** обновите всех паролей облачных соединителя, выполнив следующие действия:</span><span class="sxs-lookup"><span data-stu-id="2765c-237">**If you are running Cloud Connector version 2.0 or later,** regenerate all Cloud Connector passwords by following these steps:</span></span>
    
  4. <span data-ttu-id="2765c-238">Перезапустите сервер узла.</span><span class="sxs-lookup"><span data-stu-id="2765c-238">Restart the host server.</span></span>
    
  5. <span data-ttu-id="2765c-239">Удалите следующий файл: «% SystemDrive%\Programdata\Cloudconnector\credentials. \<CurrentUser\>.xml».</span><span class="sxs-lookup"><span data-stu-id="2765c-239">Delete the following file: "%SystemDrive%\Programdata\Cloudconnector\credentials.\<CurrentUser\>.xml" .</span></span>
    
  6. <span data-ttu-id="2765c-240">Запуск консоли PowerShell от имени администратора и запустите «Register CcAppliance-локальный» повторного ввода после описания службы и паролей.</span><span class="sxs-lookup"><span data-stu-id="2765c-240">Launch a PowerShell console as administrator, and then run "Register-CcAppliance -Local" to re-enter the passwords following the description.</span></span> 
    
     <span data-ttu-id="2765c-p128">Если файл кэшированного пароля был сгенерирован с помощью Cloud Connector версии 1.4.2, при появлении запроса используйте пароль VMAdmin для пароля CceService. Для всех остальных учетных записей введите тот же пароль, который был указан ранее для развертывания Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="2765c-p128">If the cached password file was generated with Cloud Connector version 1.4.2, use the VMAdmin password for the CceService password when prompted. Enter the same password you entered before for the Cloud Connector deployment for all other accounts.</span></span>
    
     <span data-ttu-id="2765c-243">Если файл кэшированного пароля был сгенерирован с помощью Cloud Connector версии 1.4.2, и пароли учетных записей DomainAdmin и VMAdmin отличаются друг от друга, необходимо выполнить следующие действия.</span><span class="sxs-lookup"><span data-stu-id="2765c-243">If the cached password file was generated with Cloud Connector version 1.4.2 and the DomainAdmin and VMAdmin passwords are different, you must perform the following steps:</span></span>
    
  7. <span data-ttu-id="2765c-244">Запустите командлет Set-CcCredential -AccountType DomainAdmin, следуя инструкциям ниже.</span><span class="sxs-lookup"><span data-stu-id="2765c-244">Run Set-CcCredential -AccountType DomainAdmin as follows:</span></span>
    
  8. <span data-ttu-id="2765c-245">При запросе учетных данных старой учетной записи введите учетные данные, которые использовались с паролем для учетной записи CceService.</span><span class="sxs-lookup"><span data-stu-id="2765c-245">When prompted for the old account credential, enter the credential you used for the CceService password.</span></span>
    
  9. <span data-ttu-id="2765c-246">При запросе учетных данных новой учетной записи введите пароль для DomainAdmin, использованный ранее.</span><span class="sxs-lookup"><span data-stu-id="2765c-246">When prompted for the new account credential, enter the password for the DomainAdmin password you used before.</span></span>
    
     <span data-ttu-id="2765c-247">Если файл кэширования пароль был создан с облачных соединителя версии 2.0 и более поздних версий, по умолчанию, VmAdmin и страница используют тот же пароль как CceService.</span><span class="sxs-lookup"><span data-stu-id="2765c-247">If the cached password file was generated with Cloud Connector version 2.0 or later, by default, VmAdmin and DomainAdmin use the same password as CceService.</span></span> <span data-ttu-id="2765c-248">Если пароли для DomainAdmin и VMAdmin были изменены, необходимо выполнить следующие действия.</span><span class="sxs-lookup"><span data-stu-id="2765c-248">If you changed the DomainAdmin and VMAdmin passwords, you must perform the following steps:</span></span>
    
  10. <span data-ttu-id="2765c-249">Запустите командлет Set-CcCredential -AccountType DomainAdmin, следуя инструкциям ниже.</span><span class="sxs-lookup"><span data-stu-id="2765c-249">Run Set-CcCredential -AccountType DomainAdmin as follows:</span></span>
    
       1. <span data-ttu-id="2765c-250">При запросе учетных данных старой учетной записи введите учетные данные, которые использовались с паролем для CceService.</span><span class="sxs-lookup"><span data-stu-id="2765c-250">When prompted for the old account credential, enter the credential you used for the CceService password</span></span>
    
       2. <span data-ttu-id="2765c-251">При запросе учетных данных новой учетной записи введите пароль для DomainAdmin, использованный ранее.</span><span class="sxs-lookup"><span data-stu-id="2765c-251">When prompted for the new account credential, enter the password for the DomainAdmin password you used before.</span></span>
    
  11. <span data-ttu-id="2765c-252">Запустите командлет Set-CcCredential -AccountType VmAdmin, следуя инструкциям ниже.</span><span class="sxs-lookup"><span data-stu-id="2765c-252">Run Set-CcCredential -AccountType VmAdmin as follows:</span></span>
    
       1. <span data-ttu-id="2765c-253">При запросе учетных данных старой учетной записи введите учетные данные, которые использовались с паролем для CceService.</span><span class="sxs-lookup"><span data-stu-id="2765c-253">When prompted for the old account credential, enter the credential you used for the CceService password</span></span>
    
       2. <span data-ttu-id="2765c-254">При запросе учетных данных новой учетной записи введите пароль для VmAdmin, использованный ранее. </span><span class="sxs-lookup"><span data-stu-id="2765c-254">When prompted for the new account credential, enter the password for the VmAdmin password you used before.</span></span> 
    
- <span data-ttu-id="2765c-255">**Проблема: С соединителем облачных версии 2.1 и более поздних версий, при запуске Register CcAppliance или других командлетов на устройстве, вы получаете сообщение об ошибке таких как: «для каждого объекта: свойство «Общий» не удается найти на этот объект. Убедитесь, что свойство существует. В C:\Program Files\WindowsPowerShell\Modules\CloudConnector\Internal\MtHostCommon.ps1:681 символов: 14»**</span><span class="sxs-lookup"><span data-stu-id="2765c-255">**Issue: With Cloud Connector version 2.1 and later, when running Register-CcAppliance or other cmdlets on the appliance, you receive an error message such as: "For Each-Object : The property 'Common' cannot be found on this object. Verify that the property exists. At C:\Program Files\WindowsPowerShell\Modules\CloudConnector\Internal\MtHostCommon.ps1:681 char:14"**</span></span>
    
    <span data-ttu-id="2765c-256">**Решение:** Облако 2.1 соединителя и более поздних версий требуется .NET Framework 4.6.1 или более поздней версии.</span><span class="sxs-lookup"><span data-stu-id="2765c-256">**Resolution:** Cloud Connector 2.1 and later requires .NET Framework 4.6.1 or later.</span></span> <span data-ttu-id="2765c-257">Обновите на устройстве до версии 4.6.1 .NET Framework или более поздней версии и снова запустите cmdlet(s).</span><span class="sxs-lookup"><span data-stu-id="2765c-257">Please update .NET Framework on the appliance to version 4.6.1 or later and run the cmdlet(s) again.</span></span>

- <span data-ttu-id="2765c-258">**Проблема: С облачных соединителя версии 2.1, при запуске Install-CcAppliance, вы получаете сообщение об ошибке таких как: «не удалось установить новый экземпляр с ошибкой: не удалось установить «Состояние», поскольку только строки можно использовать в качестве значения для настройки свойств XmlNode»**</span><span class="sxs-lookup"><span data-stu-id="2765c-258">**Issue: With Cloud Connector Edition 2.1, when running Install-CcAppliance, you receive an error message such as: "Failed to install new instance with error: Cannot set "State" because only strings can be used as values to set XmlNode properties"**</span></span>

   <span data-ttu-id="2765c-259">**Решение:** В Cloudconnector.ini, в разделе [распространенных] добавьте config «Состояние» следующим образом: CountryCode = "мне Нравится" состояние = WA Город = Redmond</span><span class="sxs-lookup"><span data-stu-id="2765c-259">**Resolution:** In Cloudconnector.ini, under the [Common] section, please add the “State” config as below:  CountryCode=US  State=WA  City=Redmond</span></span>

   <span data-ttu-id="2765c-260">Необязательно для строки «Состояние», чтобы иметь значение, однако в строке «Состояние» не может быть удалена из файла Cloudconnector.ini.</span><span class="sxs-lookup"><span data-stu-id="2765c-260">It is not mandatory for the "State" line to have value, however the "State" line cannot be removed from the Cloudconnector.ini file.</span></span>

- <span data-ttu-id="2765c-261">**Проблема: Вы получаете следующее сообщение об ошибке «отключить WindowsImage: не удалось Dismount-WindowsImage. Код ошибки = 0xc1550115» при установке или обновлении Edition соединителя облака.**</span><span class="sxs-lookup"><span data-stu-id="2765c-261">**Issue: You receive the following error message "Dismount-WindowsImage : Dismount-WindowsImage failed. Error code = 0xc1550115" when installing or upgrading Cloud Connector Edition.**</span></span>
    
    <span data-ttu-id="2765c-262">**Решение:** Запуск от имени администратора, запустите консоль PowerShell «DISM-Cleanup-Wim "».</span><span class="sxs-lookup"><span data-stu-id="2765c-262">**Resolution:** Launch a PowerShell console as administrator, run "DISM -Cleanup-Wim'".</span></span> <span data-ttu-id="2765c-263">Произойдет очистка всех изображений с проблемами.</span><span class="sxs-lookup"><span data-stu-id="2765c-263">This will clean up all troubled images.</span></span> <span data-ttu-id="2765c-264">Запустите командлет Install-CcAppliance повторно или дождитесь автоматического обновления.</span><span class="sxs-lookup"><span data-stu-id="2765c-264">Run Install-CcAppliance again or wait for the bits to automatically upgrade.</span></span>
    
- <span data-ttu-id="2765c-265">**Проблема: Не удается выполнить развертывание первого устройства соединителя облака в среде высокой ДОСТУПНОСТИ**</span><span class="sxs-lookup"><span data-stu-id="2765c-265">**Issue: Deployment of the first Cloud Connector appliance in an HA environment fails**</span></span>
    
    <span data-ttu-id="2765c-266">**Решение:** Действия, выполняемые зависят от причину, ошибка развертывания:</span><span class="sxs-lookup"><span data-stu-id="2765c-266">**Resolution:** The steps you take depend on the reason the deployment failed:</span></span>
    
  - <span data-ttu-id="2765c-267">Если первый appliance облачных соединителя, возникает ошибка, и не может определить причину сбоя, необходимо повторно установить устройство только после успешного развертывания и установить другие устройства.</span><span class="sxs-lookup"><span data-stu-id="2765c-267">If the first Cloud Connector appliance fails and you cannot determine the reason for the failure, you must install the appliance again until the deployment is successful, and then install the other appliances.</span></span>
    
  - <span data-ttu-id="2765c-268">В случае сбоя первого appliance соединителя облачных незначительные проблемы, такие как проблема внешний сертификат, можно устранить проблему без повторная установка устройства.</span><span class="sxs-lookup"><span data-stu-id="2765c-268">If the first Cloud Connector appliance fails with a minor issue, such as an external certificate issue, you might be able to fix the problem without re-installing the appliance.</span></span> <span data-ttu-id="2765c-269">Затем можно использовать клиентов удаленной оболочки PowerShell на развертывание помечается как успешно следующим образом.</span><span class="sxs-lookup"><span data-stu-id="2765c-269">You can then use tenant remote PowerShell to mark the deployment as successful as follows.</span></span> <span data-ttu-id="2765c-270">(Можно также использовать следующие шаги первого развертывания прошла успешно, но, по какой-либо причине, облако соединителя происходит сбой развертывание как успешно отчетов.)</span><span class="sxs-lookup"><span data-stu-id="2765c-270">(You can also use the following steps if the first deployment was successful, but, for some reason, Cloud Connector fails to report the deployment as a success.)</span></span>
    
  - <span data-ttu-id="2765c-271">Чтобы получить удостоверение (GUID) первого устройства облачных соединителя, запустите командлет Get-CsHybridPSTNAppliance.</span><span class="sxs-lookup"><span data-stu-id="2765c-271">To get the Identity (GUID) of the first Cloud Connector appliance, run the Get-CsHybridPSTNAppliance cmdlet.</span></span>
    
  - <span data-ttu-id="2765c-272">Чтобы отметить как успешно развернуты устройства, выполните Set-CsCceApplianceDeploymentStatus следующим образом:</span><span class="sxs-lookup"><span data-stu-id="2765c-272">To mark the appliance as successfully deployed, run the Set-CsCceApplianceDeploymentStatus as follows:</span></span>
    
  ```
  Set-CsCceApplianceDeploymentStatus -Identity <Appliance Identity GUID> -Action Deploy -Status Finished
  ```

- <span data-ttu-id="2765c-273">**Проблема. Требуется вручную проверять и устанавливать обновления Windows на сервере узла или виртуальных машинах.**</span><span class="sxs-lookup"><span data-stu-id="2765c-273">**Issue: You need to check for and install Windows updates manually on the host server or virtual machines.**</span></span>
    
   <span data-ttu-id="2765c-p133">**Решение**. Рекомендуется использовать преимущества функции автоматического применения обновлений ОС в составе Skype для бизнеса Cloud Connector Edition. После регистрации устройства для управления через Интернет и включения автоматического обновления ОС сервер узла и виртуальные машины будут проверять и устанавливать обновления Windows автоматически согласно параметрам периода обновления ОС.</span><span class="sxs-lookup"><span data-stu-id="2765c-p133">**Resolution:** We recommend that you take advantage of automated OS updates provided by Skype for Business Cloud Connector Edition. After an appliance is registered for online management and auto OS update is enabled, the host server and virtual machines will check and install Windows Updates automatically according to the OS update time window settings.</span></span>
    
   <span data-ttu-id="2765c-p134">Если вам требуется вручную проверять и устанавливать обновления Windows, выполните процедуру в этом разделе, соответствующую вашему типу развертывания. Необходимо запланировать одновременное обновление сервера узла и выполняющихся на нем виртуальных машин, чтобы свести к минимум время простоя, необходимое для обновления.</span><span class="sxs-lookup"><span data-stu-id="2765c-p134">If you need to check for and install Windows Updates manually, follow the steps in this section that apply to your type of deployment. You should plan on updating both the host server and the virtual machines running on it at the same time to minimize the amount of down time necessary for the updates.</span></span>
    
   <span data-ttu-id="2765c-p135">При желании можно использовать сервер служб WSUS для предоставления обновлений серверам Cloud Connector. Однако необходимо убедиться, что для обновлений Windows **не задана** автоматическая установка.</span><span class="sxs-lookup"><span data-stu-id="2765c-p135">If you prefer, you can use a Windows Server Update Services (WSUS) server to provide updates to Cloud Connector servers. Just be sure to configure the Windows Update to **not** install automatically.</span></span>
    
   <span data-ttu-id="2765c-280">Дополнительные сведения об обновлении развертывания Cloud Connector вручную см. в следующем разделе.</span><span class="sxs-lookup"><span data-stu-id="2765c-280">For information about how to manually update your Cloud Connector deployment, see the following section.</span></span>
    
- <span data-ttu-id="2765c-281">**Проблема: При соединителя облачных обновлений на новое построение и командлеты соединителей облако не обновляются.**</span><span class="sxs-lookup"><span data-stu-id="2765c-281">**Issue: When Cloud Connector updates to a new build, Cloud Connector cmdlets are not updated.**</span></span> <span data-ttu-id="2765c-282">В некоторых случаях это происходит, если окно PowerShell будет открыта в случае автоматического обновления.</span><span class="sxs-lookup"><span data-stu-id="2765c-282">This sometimes happens if a PowerShell window is left open when automatic update occurs.</span></span>
    
  <span data-ttu-id="2765c-283">**Решение:** Чтобы загрузить обновленные командлеты, можно выполнить одно из следующих действий:</span><span class="sxs-lookup"><span data-stu-id="2765c-283">**Resolution:** To load the updated cmdlets, you can do either of the following steps:</span></span>
    
   - <span data-ttu-id="2765c-284">Закройте PowerShell на устройстве облачных соединителя и снова запустите PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2765c-284">Close PowerShell on the Cloud Connector appliance, and then reopen PowerShell.</span></span>
    
     - <span data-ttu-id="2765c-285">Или можно запустить CloudConnector Import-Module-Force.</span><span class="sxs-lookup"><span data-stu-id="2765c-285">Or, you can run Import-Module CloudConnector -Force.</span></span> 
 
-   <span data-ttu-id="2765c-286">**Проблема: «термин «Stop-CsWindowsService» не распознается как имя командлета, функции, файл сценария или исполняемой программы.» Ошибка при попытке выполнить командлет CcUpdate ввод.**</span><span class="sxs-lookup"><span data-stu-id="2765c-286">**Issue: "The term 'Stop-CsWindowsService' is not recognized as the name of a cmdlet, function, script file, or operable program." error when attempting to run Enter-CcUpdate cmdlet.**</span></span>

    <span data-ttu-id="2765c-287">**Решение:** Удалите файл HOME\AppData\Local\Microsoft\Windows\PowerShell\ModuleAnalysisCache $.</span><span class="sxs-lookup"><span data-stu-id="2765c-287">**Resolution:** Delete the $HOME\AppData\Local\Microsoft\Windows\PowerShell\ModuleAnalysisCache file.</span></span>
<span data-ttu-id="2765c-288">PowerShell создает этот файл как кэш командлеты из модулей, его поиск, чтобы его не нужно каждый раз, как повторно анализировать все модули, которые может сделать очень медленно.</span><span class="sxs-lookup"><span data-stu-id="2765c-288">PowerShell creates this file as a cache of cmdlets from modules that it finds so that it doesn’t have to re-analyze all the modules each time as that would make things really slow.</span></span> <span data-ttu-id="2765c-289">Скорее всего была повреждена файла, которое указано вводящих в заблуждение результатов PowerShell, когда читает из этого кэша.</span><span class="sxs-lookup"><span data-stu-id="2765c-289">Most likely, there was some file corruption that provided misleading results to PowerShell when it was reading back from that cache.</span></span>

-   <span data-ttu-id="2765c-290">**Проблема: «Import-Module CloudConnector» возникает ошибка «Import-Module: указанный модуль «CloudConnector» не был загружен, так как файл допустимый модуль не найден в любой другой каталог, модуль»**</span><span class="sxs-lookup"><span data-stu-id="2765c-290">**Issue: “Import-Module CloudConnector” generates error “Import-Module: The specified module “CloudConnector” was not loaded because no valid module file was found in any module directory”**</span></span>

    <span data-ttu-id="2765c-291">**Решение:**</span><span class="sxs-lookup"><span data-stu-id="2765c-291">**Resolution:**</span></span>
    - <span data-ttu-id="2765c-292">Проверить, что действительно CloudConnector модуль присутствует в разделе c:\Program Files\WindowsPowerShell\Modules</span><span class="sxs-lookup"><span data-stu-id="2765c-292">Validate that indeed the CloudConnector module exists under c:\Program Files\WindowsPowerShell\Modules</span></span>
    
    - <span data-ttu-id="2765c-293">После проверки правильности модуля CloudConnector существует в этом расположении, может быть изменен в переменную PSModulePath среды хранения путь для расположения модули:</span><span class="sxs-lookup"><span data-stu-id="2765c-293">After validating that CloudConnector module exists under this location, the PSModulePath environment variable storing the path to the locations of the modules can be changed:</span></span>
    
     <span data-ttu-id="2765c-294">a)</span><span class="sxs-lookup"><span data-stu-id="2765c-294">a.</span></span> <span data-ttu-id="2765c-295">Изменение временной: Powershell Start как администратора и выполните следующую команду: $env: PSModulePath = $env: PSModulePath + «; C:\Program Files\WindowsPowerShell\Modules\"</span><span class="sxs-lookup"><span data-stu-id="2765c-295">Temporary change: Start Powershell as an Administrator and run the following command: $env:PSModulePath = $env:PSModulePath + ";C:\Program Files\WindowsPowerShell\Modules\"</span></span>
        
     <span data-ttu-id="2765c-296">б)</span><span class="sxs-lookup"><span data-stu-id="2765c-296">b.</span></span> <span data-ttu-id="2765c-297">Для сохраняемых изменений, запустите PowerShell как администратор и выполнить следующие команды, по одному: $CurrentValue = [среды]:: GetEnvironmentVariable("PSModulePath", "Machine") SetEnvironmentVariable("PSModulePath", $CurrentValue + "; C:\Program Files\WindowsPowerShell\Modules», «Компьютер»)</span><span class="sxs-lookup"><span data-stu-id="2765c-297">For persistent change, Start PowerShell as an Administrator and run the following commands, one by one: $CurrentValue = [Environment]::GetEnvironmentVariable("PSModulePath", "Machine") SetEnvironmentVariable("PSModulePath", $CurrentValue + "; C:\Program Files\WindowsPowerShell\Modules", "Machine")</span></span>

    
## <a name="install-windows-updates-manually"></a><span data-ttu-id="2765c-298">Установка обновления Windows вручную</span><span class="sxs-lookup"><span data-stu-id="2765c-298">Install Windows updates manually</span></span>

<span data-ttu-id="2765c-299">Если вы не хотите использовать автоматическое обновление в вашей среде, выполните следующие действия для проверки вручную и применение обновлений Windows.</span><span class="sxs-lookup"><span data-stu-id="2765c-299">If you do not want to use automatic updates in your environment, follow these steps to manually check for and apply Windows updates.</span></span> <span data-ttu-id="2765c-300">Поиск и установку обновлений Windows может потребоваться перезагрузка сервера.</span><span class="sxs-lookup"><span data-stu-id="2765c-300">Checking for and installing Windows updates may require a server restart.</span></span> <span data-ttu-id="2765c-301">При перезапуске хост-сервера, пользователи не смогут использовать облачных соединитель для помещения и принимать звонки.</span><span class="sxs-lookup"><span data-stu-id="2765c-301">When a host server is restarting, users will not be able to use Cloud Connector to place or receive calls.</span></span> <span data-ttu-id="2765c-302">Вы можете вручную проверить и установить обновления, указав время их применения, а затем перезагрузить компьютеры по мере необходимости, выбрав периоды, которые позволят избежать перерывов в обслуживании.</span><span class="sxs-lookup"><span data-stu-id="2765c-302">You can manually check for and install updates to control when the updates take place, and then restart the machines as needed during times you choose to avoid disruption of services.</span></span>
  
<span data-ttu-id="2765c-303">Чтобы вручную проверить обновления, подключитесь к каждому серверу узла и откройте **панель управления**.</span><span class="sxs-lookup"><span data-stu-id="2765c-303">To manually check for updates, connect to each host server and open the **Control Panel**.</span></span> <span data-ttu-id="2765c-304">Выберите **Система и безопасность \>Windows Update**и затем Управление обновлениями и сервер перезагружается подходящим для вашей среды.</span><span class="sxs-lookup"><span data-stu-id="2765c-304">Select **System and Security \>Windows Update**, and then manage the updates and server restarts as appropriate for your environment.</span></span>
  
- <span data-ttu-id="2765c-305">Если на сайте имеется только одно устройство, подключитесь к каждой виртуальной машине и откройте **панель управления**.</span><span class="sxs-lookup"><span data-stu-id="2765c-305">If there is only one appliance in the site, connect to each virtual machine and open the **Control Panel**.</span></span> <span data-ttu-id="2765c-306">Выберите **Система и безопасность \>Windows Update**и затем настроить получение обновлений и при необходимости перезагрузки сервера.</span><span class="sxs-lookup"><span data-stu-id="2765c-306">Select **System and Security \>Windows Update**, and then configure the updates and server restarts as appropriate.</span></span>
    
- <span data-ttu-id="2765c-p143">Если на сайте несколько устройств, обновляемый и перезагружаемый экземпляр будет недоступен для пользователей во время обновления. Пользователи будут подключаться к другим экземплярам в развертывании до тех пор, пока все виртуальные машины и все службы Skype для бизнеса на виртуальных машинах не запустятся после завершения обновления. Чтобы избежать перерывов в обслуживании, можно удалить экземпляр из среды высокой доступности на время применения обновлений, а затем восстановить его. Для этого выполните следующую процедуру.</span><span class="sxs-lookup"><span data-stu-id="2765c-p143">If there are more than one appliance in the site, the instance being updated and restarted cannot be accessed by users during the updates. Users will connect to other instances in the deployment until all virtual machines and all Skype for Business services start on the virtual machines after the updates are completed. To avoid any potential disruption to service, you can remove the instance from HA while you apply the updates, and then restore it when complete. To do so:</span></span>
    
1. <span data-ttu-id="2765c-311">На каждом сервере узла откройте консоль PowerShell от имени администратора.</span><span class="sxs-lookup"><span data-stu-id="2765c-311">On each host server, open a PowerShell console as administrator.</span></span>
    
2. <span data-ttu-id="2765c-312">Удалите экземпляр из среды высокой доступности, используя следующий командлет:</span><span class="sxs-lookup"><span data-stu-id="2765c-312">Remove the instance from HA with the following cmdlet:</span></span>
    
   ```
   Enter-CcUpdate
   ```

3. 
    
    <span data-ttu-id="2765c-313">Выполните процедуру применения обновлений вручную для одного экземпляра и перезапустите виртуальную машину.</span><span class="sxs-lookup"><span data-stu-id="2765c-313">Follow the steps for a single instance to manually apply the updates and restart the virtual machine.</span></span>
    
4. <span data-ttu-id="2765c-314">Верните экземпляр в среду высокой доступности, используя следующий командлет:</span><span class="sxs-lookup"><span data-stu-id="2765c-314">Set the instance back to HA with the following cmdlet:</span></span>
    
   ```
   Exit-CcUpdate
   ```

<span data-ttu-id="2765c-315">Для развертываний с несколькими сайтами выполните процедуру для отдельного сайта для всех сайтов в развертывании, применяя обновления к одному сайту за раз.</span><span class="sxs-lookup"><span data-stu-id="2765c-315">For multi-site deployments, follow the steps for a single site for each site in the deployment, applying updates to one site at a time.</span></span>
  
## <a name="tips-when-installing-anti-virus-software-on-the-cloud-connector-host-machine"></a><span data-ttu-id="2765c-316">Советы при установке антивирусное программное обеспечение на главном компьютере облачных соединителя</span><span class="sxs-lookup"><span data-stu-id="2765c-316">Tips when installing anti-virus software on the Cloud Connector host machine</span></span>

<span data-ttu-id="2765c-317">Если необходимо установить антивирусное программное обеспечение на главном компьютере облачных соединителя, необходимо добавить следующие исключения:</span><span class="sxs-lookup"><span data-stu-id="2765c-317">If you need to install anti-virus software on the Cloud Connector host machine, you need to add the following exclusions:</span></span>
  
- <span data-ttu-id="2765c-318">Локальный каталог устройства для обеспечения связи на каждом компьютере.</span><span class="sxs-lookup"><span data-stu-id="2765c-318">Local Appliance Directory on each machine.</span></span>
    
- <span data-ttu-id="2765c-319">Удаленный каталог сайтов на каждом компьютере.</span><span class="sxs-lookup"><span data-stu-id="2765c-319">Remote Site Directory on each machine.</span></span>
    
- <span data-ttu-id="2765c-320">Локальный каталог сайта на компьютере, где размещается в корневой папке общего веб-узла.</span><span class="sxs-lookup"><span data-stu-id="2765c-320">Local Site Directory on the machine hosts the shared site root folder.</span></span>
    
- <span data-ttu-id="2765c-321">%ProgramFiles%\Skype облаке соединитель для выпуска для бизнеса</span><span class="sxs-lookup"><span data-stu-id="2765c-321">%ProgramFiles%\Skype for Business Cloud Connector Edition</span></span>
    
- <span data-ttu-id="2765c-322">%ALLUSERSPROFILE%\CloudConnector</span><span class="sxs-lookup"><span data-stu-id="2765c-322">%ALLUSERSPROFILE%\CloudConnector</span></span>
    
- <span data-ttu-id="2765c-323">%ProgramFiles%\WindowsPowerShell\Modules\CloudConnector</span><span class="sxs-lookup"><span data-stu-id="2765c-323">%ProgramFiles%\WindowsPowerShell\Modules\CloudConnector</span></span>
    
- <span data-ttu-id="2765c-324">Процесс Microsoft.Rtc.CCE.ManagementService.exe.</span><span class="sxs-lookup"><span data-stu-id="2765c-324">The process Microsoft.Rtc.CCE.ManagementService.exe.</span></span>
