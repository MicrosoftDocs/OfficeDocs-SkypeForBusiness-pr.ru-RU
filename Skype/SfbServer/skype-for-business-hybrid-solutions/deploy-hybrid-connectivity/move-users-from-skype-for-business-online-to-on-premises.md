---
title: Перемещение пользователей из Скайп для бизнеса в Интернет для локально
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 12/19/2017
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- Ent_O365_Hybrid
- IT_Skype16
- IT_Skype4B_Hybrid
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 55733bb5-6742-4daf-8db5-1c5df86f4cea
description: 'Сводка: Узнайте, как для перемещения учетных записей пользователей из Интернета к локально в Скайп для Business Server.'
ms.openlocfilehash: 655c037fc2299044aa3799d06e0d231784248d7e
ms.sourcegitcommit: 08c6fe9955ea61dd9cded2210ae0153e06bdd8a6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/28/2018
ms.locfileid: "23260148"
---
# <a name="move-users-from-skype-for-business-online-to-on-premises"></a><span data-ttu-id="af3c9-103">Перемещение пользователей из Скайп для бизнеса в Интернет для локально</span><span class="sxs-lookup"><span data-stu-id="af3c9-103">Move users from Skype for Business Online to on premises</span></span>

<span data-ttu-id="af3c9-104">**Сводка:** Узнайте, как для перемещения учетных записей пользователей из Интернета к локально в Скайп для Business Server.</span><span class="sxs-lookup"><span data-stu-id="af3c9-104">**Summary:** Learn how to move user accounts from online to on premises in Skype for Business Server.</span></span>

<span data-ttu-id="af3c9-105">Может понадобиться для перемещения учетных записей пользователей из Интернета к локально убедитесь, что пользователи размещаются в Интернете и локально обнаруживаются друг с другом.</span><span class="sxs-lookup"><span data-stu-id="af3c9-105">You might need to move user accounts from online to on premises to ensure that users homed online and on premises are discoverable to one another.</span></span> <span data-ttu-id="af3c9-106">В обнаруживаемый друг с другом, все пользователи должны иметь состояние присутствия в локальной Active Directory.</span><span class="sxs-lookup"><span data-stu-id="af3c9-106">To be discoverable to one another, all users must have a presence in the on-premises Active Directory.</span></span> <span data-ttu-id="af3c9-107">Дополнительные сведения см в [планировании гибридного подключения между Скайп Business Server и Скайп для бизнеса в Интернет](../../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md).</span><span class="sxs-lookup"><span data-stu-id="af3c9-107">For more information, see [Plan hybrid connectivity between Skype for Business Server and Skype for Business Online](../../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md).</span></span> <span data-ttu-id="af3c9-108">Можно переместить online пользователям при локальном, например, если:</span><span class="sxs-lookup"><span data-stu-id="af3c9-108">You might want to move online users to on premises, for example, if:</span></span>

- <span data-ttu-id="af3c9-109">У вас есть новых пользователей, которые должны быть созданы локально и затем перемещен в облако.</span><span class="sxs-lookup"><span data-stu-id="af3c9-109">You have new users who need to be created on premises and then moved to the cloud.</span></span>

- <span data-ttu-id="af3c9-110">Вашей организации развернут Скайп для бизнеса в Интернет, прежде чем оно развернуто Скайп для Business Server.</span><span class="sxs-lookup"><span data-stu-id="af3c9-110">Your organization deployed Skype for Business Online before it deployed Skype for Business Server.</span></span> <span data-ttu-id="af3c9-111">Таким образом у пользователей, которые были созданы в облаке, сначала и теперь необходимо переместить при локальном прежде чем они станут переход в Скайп для бизнеса в Интернет.</span><span class="sxs-lookup"><span data-stu-id="af3c9-111">Therefore, you have users who were created in the cloud first, and now need to be moved to on premises before they are move to Skype for Business Online.</span></span>

<span data-ttu-id="af3c9-112">В этом разделе описывается два сценария:</span><span class="sxs-lookup"><span data-stu-id="af3c9-112">This topic describes two scenarios:</span></span>

- [<span data-ttu-id="af3c9-113">Перемещение пользователей online — пользователей, которые были изначально online —, чтобы локальный</span><span class="sxs-lookup"><span data-stu-id="af3c9-113">Move online users—who were originally online—to on premises</span></span>](move-users-from-skype-for-business-online-to-on-premises.md#BKMK_originallyonline)

- [<span data-ttu-id="af3c9-114">Переместите online пользователей (, которые были локально) локально</span><span class="sxs-lookup"><span data-stu-id="af3c9-114">Move online users (who were originally on premises) to on premises</span></span>](move-users-from-skype-for-business-online-to-on-premises.md#BKMK_originallyonprem)

## <a name="move-online-userswho-were-originally-onlineto-on-premises"></a><span data-ttu-id="af3c9-115">Перемещение пользователей online — пользователей, которые были изначально online —, чтобы локальный</span><span class="sxs-lookup"><span data-stu-id="af3c9-115">Move online users—who were originally online—to on premises</span></span>
<span data-ttu-id="af3c9-116"><a name="BKMK_originallyonline"> </a></span><span class="sxs-lookup"><span data-stu-id="af3c9-116"></span></span>

<span data-ttu-id="af3c9-117">Этот раздел применим только для пользователей, пользователей, которые были созданы и поддержкой Интернет-версия, однако, у которых нет учетной записи в локальный Active Directory.</span><span class="sxs-lookup"><span data-stu-id="af3c9-117">This section applies only to users who were created and enabled online, but who do not have an account in the on premises Active Directory.</span></span>

<span data-ttu-id="af3c9-118">Перед началом перемещения пользователей службы Online в локальную среду проверьте выполнение следующих условий.</span><span class="sxs-lookup"><span data-stu-id="af3c9-118">Before you start moving online users to your on-premises environment, check that all of the following are true:</span></span>

- <span data-ttu-id="af3c9-119">Локальная среда Lync Server должна быть полностью развернута и проверена.</span><span class="sxs-lookup"><span data-stu-id="af3c9-119">Your on-premises environment must be fully deployed and validated.</span></span> <span data-ttu-id="af3c9-120">Для получения дополнительных сведений см [развертывания Lync Server 2013](https://technet.microsoft.com/library/b76795a4-4e71-4c70-a5c0-d1197fa8028c.aspx) или [Развернуть Скайп для Business Server 2015](../../deploy/deploy.md), в зависимости от того, какая версия использовании локально.</span><span class="sxs-lookup"><span data-stu-id="af3c9-120">For more information, see [Deploying Lync Server 2013](https://technet.microsoft.com/library/b76795a4-4e71-4c70-a5c0-d1197fa8028c.aspx) or [Deploy Skype for Business Server 2015](../../deploy/deploy.md), depending on which version you are using on premises.</span></span>

- <span data-ttu-id="af3c9-121">Удаленный доступ к PowerShell должна быть настроена интерактивного клиента.</span><span class="sxs-lookup"><span data-stu-id="af3c9-121">Your online tenant must be configured for remote PowerShell access.</span></span>

    <span data-ttu-id="af3c9-122">Для этого сначала установить Скайп для бизнеса в Интернет модуля соединитель для Windows PowerShell, который вы можете получить здесь: [https://go.microsoft.com/fwlink/p/?LinkId=391911](https://go.microsoft.com/fwlink/p/?LinkId=391911).</span><span class="sxs-lookup"><span data-stu-id="af3c9-122">To do this, first install the Skype for Business Online connector module for Windows PowerShell, which you can get here: [https://go.microsoft.com/fwlink/p/?LinkId=391911](https://go.microsoft.com/fwlink/p/?LinkId=391911).</span></span>

    <span data-ttu-id="af3c9-123">После установки модуля может установить удаленный сеанс, введя следующие командлеты в Скайп для консоли Business Server.</span><span class="sxs-lookup"><span data-stu-id="af3c9-123">After you install the module, you can establish a remote session by typing the following cmdlets in the Skype for Business Server Management Shell:</span></span>

  ```
  Import-Module SkypeOnlineConnector
  ```

  ```
  $cred = Get-Credential
  ```

  ```
  $CSSession = New-CsOnlineSession -Credential $cred
  ```

  ```
  Import-PSSession $CSSession -AllowClobber
  ```

    <span data-ttu-id="af3c9-124">Дополнительные сведения об использовании PowerShell с Скайп для бизнеса в Интернет можно [настроить компьютер для Windows PowerShell](../../../SfbOnline/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)</span><span class="sxs-lookup"><span data-stu-id="af3c9-124">For more information about using PowerShell with Skype for Business Online, see [Set up your computer for Windows PowerShell](../../../SfbOnline/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)</span></span>

- <span data-ttu-id="af3c9-125">Общее адресное пространство SIP должна быть настроена интерактивного клиента.</span><span class="sxs-lookup"><span data-stu-id="af3c9-125">Your online tenant must be configured for a shared SIP address space.</span></span> <span data-ttu-id="af3c9-126">Для этого сначала удаленного сеанса Powershell с Скайп для бизнеса в Интернет.</span><span class="sxs-lookup"><span data-stu-id="af3c9-126">To do this, first start a remote Powershell session with Skype for Business Online.</span></span> <span data-ttu-id="af3c9-127">Затем выполните следующий командлет:</span><span class="sxs-lookup"><span data-stu-id="af3c9-127">Then run the following cmdlet:</span></span>

  ```
  Set-CsTenantFederationConfiguration -SharedSipAddressSpace $True
  ```

    > [!NOTE]
    > <span data-ttu-id="af3c9-128">Атрибут SharedSipAddressSpace необходимо оставаться «True», пока переход к Интернет-версия окончательный и пользователи не остаются локально.</span><span class="sxs-lookup"><span data-stu-id="af3c9-128">The SharedSipAddressSpace attribute needs to remain "True" until moving to online is final, and no users remain on premises.</span></span>

<span data-ttu-id="af3c9-129">После завершения этих действий можно перенести учетные записи пользователей, как описано в следующей процедуре:</span><span class="sxs-lookup"><span data-stu-id="af3c9-129">After you've finished these steps, you can migrate user accounts as described in the following procedure:</span></span>

### <a name="move-user-accounts-originally-enabled-online-to-an-on-premises-deployment"></a><span data-ttu-id="af3c9-130">Перемещение учетных записей пользователей, изначально включен в локальном развертывании Интернет-версия</span><span class="sxs-lookup"><span data-stu-id="af3c9-130">Move user accounts originally enabled online to an on-premises deployment</span></span>

1. <span data-ttu-id="af3c9-131">Сначала подготовьте организацию к гибридному развертыванию, включая установку Azure Active Directory Connect и средств синхронизации.</span><span class="sxs-lookup"><span data-stu-id="af3c9-131">First, make sure that your organization is configured for hybrid, including Azure Active Directory Connect and sync tools.</span></span> <span data-ttu-id="af3c9-132">Дополнительные сведения см в [планировании гибридного подключения между Скайп Business Server и Скайп для бизнеса в Интернет](../../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md).</span><span class="sxs-lookup"><span data-stu-id="af3c9-132">For more information, see [Plan hybrid connectivity between Skype for Business Server and Skype for Business Online](../../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md).</span></span>

  - <span data-ttu-id="af3c9-133">На локальном развертывании в Скайп для консоли Business Server, введите следующие командлеты для создания поставщика услуг размещения для Скайп для бизнеса в Интернет.</span><span class="sxs-lookup"><span data-stu-id="af3c9-133">On your on-premises deployment, in the Skype for Business Server Management Shell, type the following cmdlets to create the hosting provider for Skype for Business Online.</span></span> <span data-ttu-id="af3c9-134">Можно использовать любое значение для параметра Identity и Name.</span><span class="sxs-lookup"><span data-stu-id="af3c9-134">You can use whatever value you want for the Identity and Name parameters.</span></span>

  ```
  Set-CsAccessEdgeConfiguration -AllowOutsideUsers 1 -AllowFederatedUsers 1 -UseDnsSrvRouting -EnablePartnerDiscovery $true
  ```

  ```
  New-CsHostingProvider -Identity SkypeforBusinessOnline -ProxyFqdn "sipfed.online.lync.com" -Enabled $true -EnabledSharedAddressSpace $true -HostsOCSUsers $true -VerificationLevel UseSourceVerification -IsLocal $false -AutodiscoverUrl https://webdir.online.lync.com/Autodiscover/AutodiscoverService.svc/root
  ```

2. <span data-ttu-id="af3c9-135">Убедитесь, что на пограничных серверах локальной, у вас есть цепочки сертификатов, который позволяет подключение к Скайп для бизнеса в Интернет, как показано в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="af3c9-135">Confirm that on your on-premises Edge Servers, you have the certificate chain that enables connection to Skype for Business Online, as shown in the following table.</span></span> <span data-ttu-id="af3c9-136">Вы можете загрузить этот цепочки: [https://corp.sts.microsoft.com/Onboard/ADFS_Onboarding_Pack/corp_sts_certs.zip](https://corp.sts.microsoft.com/Onboard/ADFS_Onboarding_Pack/corp_sts_certs.zip).</span><span class="sxs-lookup"><span data-stu-id="af3c9-136">You can download this chain here: [https://corp.sts.microsoft.com/Onboard/ADFS_Onboarding_Pack/corp_sts_certs.zip](https://corp.sts.microsoft.com/Onboard/ADFS_Onboarding_Pack/corp_sts_certs.zip).</span></span>

|<span data-ttu-id="af3c9-137">**Сертификат**</span><span class="sxs-lookup"><span data-stu-id="af3c9-137">**Certificate**</span></span>|<span data-ttu-id="af3c9-138">**Хранилище сертификатов**</span><span class="sxs-lookup"><span data-stu-id="af3c9-138">**Certificate Store**</span></span>|
|:-----|:-----|
|<span data-ttu-id="af3c9-139">Корневой Baltimore CyberTrust</span><span class="sxs-lookup"><span data-stu-id="af3c9-139">Baltimore CyberTrust Root</span></span>  <br/> |<span data-ttu-id="af3c9-140">Доверенный корневой ЦС</span><span class="sxs-lookup"><span data-stu-id="af3c9-140">Trusted Root CA</span></span>  <br/> |
|<span data-ttu-id="af3c9-141">Microsoft Internet Authority (сертификат нового ЦС)</span><span class="sxs-lookup"><span data-stu-id="af3c9-141">Microsoft Internet Authority (New CA certificate)</span></span>  <br/> |<span data-ttu-id="af3c9-142">Промежуточный ЦС</span><span class="sxs-lookup"><span data-stu-id="af3c9-142">Intermediate CA</span></span>  <br/> |
|<span data-ttu-id="af3c9-143">MSIT Machine Auth CA2 (новый выдающий ЦС2)</span><span class="sxs-lookup"><span data-stu-id="af3c9-143">MSIT Machine Auth CA2 (New Issuing CA2)</span></span>  <br/> |<span data-ttu-id="af3c9-144">Промежуточный ЦС</span><span class="sxs-lookup"><span data-stu-id="af3c9-144">Intermediate CA</span></span>  <br/> |

3. <span data-ttu-id="af3c9-145">В Active Directory в локальной включение учетных записей пользователя для Скайп для Business Server 2015 локально.</span><span class="sxs-lookup"><span data-stu-id="af3c9-145">In your on-premises Active Directory, enable the affected user accounts for Skype for Business Server 2015 on premises.</span></span> <span data-ttu-id="af3c9-146">Для отдельных пользователей это можно сделать путем ввода следующего командлета:</span><span class="sxs-lookup"><span data-stu-id="af3c9-146">You can do this for an individual user by typing the following cmdlet:</span></span>

  ```
  Enable-CsUser
-Identity "username "
-SipAddress "sip: username @contoso.com"
-HostingProviderProxyFqdn "sipfed.online.lync.com"
  ```

    <span data-ttu-id="af3c9-147">Или можно создать сценарий для считывания имен пользователей из файла и передачи их как входных данных командлету Enable-CsUser:</span><span class="sxs-lookup"><span data-stu-id="af3c9-147">Or you can create a script that reads user names from a file and provides them as input to the Enable-CsUser cmdlet:</span></span>

  ```
  Enable-CsUser
-Identity $Identity
-SipAddress $SipAddress
-HostingProviderProxyFqdn "sipfed.online.lync.com"
  ```

4. <span data-ttu-id="af3c9-148">Синхронизация пользователей online с обновленные локальными пользователями.</span><span class="sxs-lookup"><span data-stu-id="af3c9-148">Synchronize the online users with the updated on-premises users.</span></span> <span data-ttu-id="af3c9-149">Для получения дополнительных сведений см [Средств интеграции каталогов](https://go.microsoft.com/fwlink/p/?LinkId=530320).</span><span class="sxs-lookup"><span data-stu-id="af3c9-149">For more information, see [Directory Integration Tools](https://go.microsoft.com/fwlink/p/?LinkId=530320).</span></span>

5. <span data-ttu-id="af3c9-150">Обновите следующие записи DNS для направления весь трафик SIP для локального развертывания:</span><span class="sxs-lookup"><span data-stu-id="af3c9-150">Update the following DNS records to direct all SIP traffic to your on-premises deployment:</span></span>

  - <span data-ttu-id="af3c9-151">Обновите запись **lyncdiscover.contoso.com** A, указав полное доменное имя локального обратного прокси-сервера.</span><span class="sxs-lookup"><span data-stu-id="af3c9-151">Update the **lyncdiscover.contoso.com** A record to point to the FQDN of the on-premises reverse proxy server.</span></span>

  - <span data-ttu-id="af3c9-152">Обновление \*\* *_sip* . _tls.contoso.com\*\* запись SRV для разрешения в общедоступный IP-адрес или виртуальный IP-адрес адрес пограничной службы доступа Lync локальных.</span><span class="sxs-lookup"><span data-stu-id="af3c9-152">Update the ***_sip*  ._tls.contoso.com** SRV record to resolve to the public IP or VIP address of the Access Edge service of Lync on-premises.</span></span>

  - <span data-ttu-id="af3c9-153">Обновление \*\* *_sipfederationtls* . _tcp.contoso.com\*\* запись SRV для разрешения в общедоступный IP-адрес или виртуальный IP-адрес адрес службы пограничного сервера доступа из Скайп for Business Server 2015 локальной.</span><span class="sxs-lookup"><span data-stu-id="af3c9-153">Update the ***_sipfederationtls*  ._tcp.contoso.com** SRV record to resolve to the public IP or VIP address of the Access Edge service of Skype for Business Server 2015 on-premises.</span></span>

  - <span data-ttu-id="af3c9-154">Если используемые организацией разделения DNS (иногда называется «разделенной DNS»), убедитесь в том, что пользователи, разрешение имен через внутреннюю зону DNS направляются пула переднего плана.</span><span class="sxs-lookup"><span data-stu-id="af3c9-154">If your organization uses split DNS (sometimes called "split-brain DNS"), make sure that users resolving names through the internal DNS zone are directed to the Front End Pool.</span></span>

6. <span data-ttu-id="af3c9-155">Тип `Get-CsUser` командлет, чтобы проверить некоторые свойства о пользователях, предполагается перемещать.</span><span class="sxs-lookup"><span data-stu-id="af3c9-155">Type the  `Get-CsUser` cmdlet to check some properties about the users you'll be moving.</span></span> <span data-ttu-id="af3c9-156">Необходимо убедиться в том, что параметру HostingProviderProxyFQDN присвоено значение `"sipfed.online.lync.com"`, и проверить правильность задания SIP-адресов.</span><span class="sxs-lookup"><span data-stu-id="af3c9-156">You want to make sure that the HostingProviderProxyFQDN is set to `"sipfed.online.lync.com"` and that the SIP addresses are set correctly.</span></span>

7. <span data-ttu-id="af3c9-157">Переместите online пользователей локально.</span><span class="sxs-lookup"><span data-stu-id="af3c9-157">Move online users to on premises.</span></span>

    <span data-ttu-id="af3c9-158">Чтобы переместить одного пользователя, введите следующее:</span><span class="sxs-lookup"><span data-stu-id="af3c9-158">To move a single user, type this:</span></span>

  ```
  $cred = Get-Credential
  Move-CsUser -Identity <username>@contoso.com  -Target "<fe-pool>.contoso.com " -Credential $cred -HostedMigrationOverrideURL <URL>
  ```

    <span data-ttu-id="af3c9-159">Можно переместить несколько пользователей с помощью командлета **Get-CsUSer** с параметром - фильтра для выбора пользователей с определенное свойство.</span><span class="sxs-lookup"><span data-stu-id="af3c9-159">You can move multiple users by using the **Get-CsUSer** cmdlet with the -Filter parameter to select the users with a specific property.</span></span> <span data-ttu-id="af3c9-160">Например можно выделить все активные пользователи, фильтрации для {поставщиком услуг размещения - eq «sipfed.online.lync.om»}.</span><span class="sxs-lookup"><span data-stu-id="af3c9-160">For example, you could select all Online users by filtering for {Hosting Provider -eq "sipfed.online.lync.om"}.</span></span> <span data-ttu-id="af3c9-161">Затем можно передать возвращенные пользователям командлета **Move-CsUSer** , как показано ниже.</span><span class="sxs-lookup"><span data-stu-id="af3c9-161">You can then pipe the returned users to the **Move-CsUSer** cmdlet, as shown below.</span></span>

  ```
  Get-CsUser -Filter {Hosting Provider -eq "sipfed.online.lync.com"} | Move-CsUser -Target "<fe-pool>.contoso.com " -Credential $creds -HostedMigrationOverrideURL <URL>
  ```

    <span data-ttu-id="af3c9-162">Формат URL-адрес, указанный для параметра **HostedMigrationOverrideUrl** должен быть URL-адрес в пул, где работает размещенная служба миграции, в следующем формате: _Https://\<полное доменное имя пула\>/HostedMigration/ hostedmigrationService.svc_.</span><span class="sxs-lookup"><span data-stu-id="af3c9-162">The format of the URL specified for the **HostedMigrationOverrideUrl** parameter must be the URL to the pool where the Hosted Migration service is running, in the following format: _Https://\<Pool FQDN\>/HostedMigration/hostedmigrationService.svc_.</span></span>

    <span data-ttu-id="af3c9-163">URL-адрес службы миграции с размещением можно определить по URL-адресу панели управления Lync Online для учетной записи клиента Office 365.</span><span class="sxs-lookup"><span data-stu-id="af3c9-163">You can determine the URL to the Hosted Migration Service by viewing the URL for the Lync Online Control Panel for your Office 365 tenant account.</span></span>

### <a name="to-determine-the-hosted-migration-service-url-for-your-office-365-tenant"></a><span data-ttu-id="af3c9-164">Определение URL-адреса размещенной службы миграции для своего клиента Office 365</span><span class="sxs-lookup"><span data-stu-id="af3c9-164">To determine the Hosted Migration Service URL for your Office 365 tenant</span></span>

1. <span data-ttu-id="af3c9-165">Выполните вход в свое клиентское приложение Office 365 как администратор.</span><span class="sxs-lookup"><span data-stu-id="af3c9-165">Login to your Office 365 tenant as an administrator.</span></span>

2. <span data-ttu-id="af3c9-166">Откройте **Центр администрирования Skype для бизнеса**.</span><span class="sxs-lookup"><span data-stu-id="af3c9-166">Open the **Skype for Business admin center**.</span></span>

3. <span data-ttu-id="af3c9-p112">Не закрывая окна **Центр администрирования Skype для бизнеса**, выделите и скопируйте URL-адрес в адресную строку в **lync.com**. Примерный URL-адрес выглядит так, как показано далее:</span><span class="sxs-lookup"><span data-stu-id="af3c9-p112">With the **Skype for Business admin center** displayed, select and copy the URL in the address bar up to **lync.com**. An example URL looks similar to the following:</span></span>

     `https://webdir0a.online.lync.com/lscp/?language=en-US&amp;tenantID=`

4. <span data-ttu-id="af3c9-169">Заменяя **webdir** в URL-адресе на **admin**, получаем следующее:</span><span class="sxs-lookup"><span data-stu-id="af3c9-169">Replace **webdir** in the URL with **admin**, resulting in the following:</span></span>

     `https://admin0a.online.lync.com`

5. <span data-ttu-id="af3c9-170">Добавьте к URL-адресу следующую строку: **/HostedMigration/hostedmigrationservice.svc**.</span><span class="sxs-lookup"><span data-stu-id="af3c9-170">Append the following string to the URL: **/HostedMigration/hostedmigrationservice.svc**.</span></span>

    <span data-ttu-id="af3c9-171">Полученный URL-адрес, который соответствует значению **HostedMigrationOverrideUrl**, должен выглядеть следующим образом:</span><span class="sxs-lookup"><span data-stu-id="af3c9-171">The resulting URL, which is the value of the **HostedMigrationOverrideUrl**, should look like the following:</span></span>

     `https://admin0a.online.lync.com/HostedMigration/hostedmigrationservice.svc`

    > [!NOTE]
    > <span data-ttu-id="af3c9-172">По умолчанию максимальный размер файлов журналов транзакций базы данных rtcxds составляет 16 ГБ.</span><span class="sxs-lookup"><span data-stu-id="af3c9-172">The default maximum size for transaction log files of the rtcxds database is 16 GB.</span></span> <span data-ttu-id="af3c9-173">Это не достаточно большой при перемещении большого числа пользователей, одновременно, особенно если зеркальное отображение включено.</span><span class="sxs-lookup"><span data-stu-id="af3c9-173">This might not be big enough if you're moving a large number of users at once, especially if you have mirroring enabled.</span></span> <span data-ttu-id="af3c9-174">Во избежание такой ситуации можно увеличить размер файлов или регулярно создавать резервные копии файлов журналов.</span><span class="sxs-lookup"><span data-stu-id="af3c9-174">To get around this you can increase the file size or back up the log files regularly.</span></span> <span data-ttu-id="af3c9-175">Дополнительные сведения можно [https://support.microsoft.com/kb/2756725](https://support.microsoft.com/kb/2756725).</span><span class="sxs-lookup"><span data-stu-id="af3c9-175">For more information, see [https://support.microsoft.com/kb/2756725](https://support.microsoft.com/kb/2756725).</span></span>

8. <span data-ttu-id="af3c9-176">Это необязательный шаг.</span><span class="sxs-lookup"><span data-stu-id="af3c9-176">This is an optional step.</span></span> <span data-ttu-id="af3c9-177">Если требуется интеграция с Exchange 2013 Online, необходимо для использования поставщика услуг размещения дополнительных.</span><span class="sxs-lookup"><span data-stu-id="af3c9-177">If you need to integrate with Exchange 2013 Online, you need to use an additional hosting provider.</span></span> <span data-ttu-id="af3c9-178">Дополнительные сведения см [Настройка интеграции между локальной Скайп Business Server 2015 и Outlook Web App](../../deploy/integrate-with-exchange-server/outlook-web-app.md).</span><span class="sxs-lookup"><span data-stu-id="af3c9-178">For details, see [Configure integration between on-premises Skype for Business Server 2015 and Outlook Web App](../../deploy/integrate-with-exchange-server/outlook-web-app.md).</span></span>

9. <span data-ttu-id="af3c9-p115">Теперь пользователи перемещаются. Чтобы проверить, что пользователь имеет правильные значения для атрибутов, показанных в таблице ниже, введите следующий командлет:</span><span class="sxs-lookup"><span data-stu-id="af3c9-p115">The users are now moved. To check that a user has correct values for the attributes shown in the following table, type this cmdlet:</span></span>

  ```
  Get-CsUser | fl DisplayName,HostingProvider,SipAddress,Enabled
  ```

|<span data-ttu-id="af3c9-181">**Атрибут Active Directory**</span><span class="sxs-lookup"><span data-stu-id="af3c9-181">**Active Directory attribute**</span></span>|<span data-ttu-id="af3c9-182">**Имя атрибута**</span><span class="sxs-lookup"><span data-stu-id="af3c9-182">**Attribute name**</span></span>|<span data-ttu-id="af3c9-183">**Правильное значение для пользователя Online**</span><span class="sxs-lookup"><span data-stu-id="af3c9-183">**Correct value for Online user**</span></span>|<span data-ttu-id="af3c9-184">**Правильное значение для локальных пользователей**</span><span class="sxs-lookup"><span data-stu-id="af3c9-184">**Correct value for on-premises users**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="af3c9-185">msRTCSIP-DeploymentLocator</span><span class="sxs-lookup"><span data-stu-id="af3c9-185">msRTCSIP-DeploymentLocator</span></span>  <br/> |<span data-ttu-id="af3c9-186">HostingProvider</span><span class="sxs-lookup"><span data-stu-id="af3c9-186">HostingProvider</span></span>  <br/> |<span data-ttu-id="af3c9-187">sipfed.Online.Lync.com</span><span class="sxs-lookup"><span data-stu-id="af3c9-187">sipfed.online.lync.com</span></span>  <br/> |<span data-ttu-id="af3c9-188">SRV:</span><span class="sxs-lookup"><span data-stu-id="af3c9-188">SRV:</span></span>  <br/> |
|<span data-ttu-id="af3c9-189">msRTCSIP-PrimaryUserAddress</span><span class="sxs-lookup"><span data-stu-id="af3c9-189">msRTCSIP-PrimaryUserAddress</span></span>  <br/> |<span data-ttu-id="af3c9-190">SIPAddress</span><span class="sxs-lookup"><span data-stu-id="af3c9-190">SIPAddress</span></span>  <br/> |<span data-ttu-id="af3c9-191">SIP:username@Contoso.com</span><span class="sxs-lookup"><span data-stu-id="af3c9-191">sip:userName@contoso.com</span></span>  <br/> |<span data-ttu-id="af3c9-192">SIP:username@Contoso.com</span><span class="sxs-lookup"><span data-stu-id="af3c9-192">sip:userName@contoso.com</span></span>  <br/> |
|<span data-ttu-id="af3c9-193">msRTCSIP-UserEnabled</span><span class="sxs-lookup"><span data-stu-id="af3c9-193">msRTCSIP-UserEnabled</span></span>  <br/> |<span data-ttu-id="af3c9-194">Включено</span><span class="sxs-lookup"><span data-stu-id="af3c9-194">Enabled</span></span>  <br/> |<span data-ttu-id="af3c9-195">True</span><span class="sxs-lookup"><span data-stu-id="af3c9-195">True</span></span>  <br/> |<span data-ttu-id="af3c9-196">True</span><span class="sxs-lookup"><span data-stu-id="af3c9-196">True</span></span>  <br/> |

10. <span data-ttu-id="af3c9-p116">Каждому перемещенному пользователю потребуется выйти из системы, а затем снова войти. При входе они должны проверить свои списки контактов и в случае необходимости добавить контакты.</span><span class="sxs-lookup"><span data-stu-id="af3c9-p116">Each user who has been moved will need to log out, then log back in. When they log in they should verify their contact lists, and add contacts if needed.</span></span>

    <span data-ttu-id="af3c9-p117">Следует учитывать, что запланированные собрания не переносятся из сетевого развертывания в локальное. После перемещения пользователям потребуется запланировать такие собрания заново.</span><span class="sxs-lookup"><span data-stu-id="af3c9-p117">Note that scheduled meetings are not migrated from online to on-premises. Users will need to reschedule these meetings after being moved.</span></span>

    <span data-ttu-id="af3c9-201">После обновления записей DNS и всех пользователей, направляются в локальной, атрибут HostingProvider пользователь переходит к используйте SRV-записи или их напрямую в Интернет-поставщика «sipfed.online.lync.com.»</span><span class="sxs-lookup"><span data-stu-id="af3c9-201">After the DNS records are updated and all users are directed to On-premises, the HostingProvider attribute directs the user to either use SRV records or direct them to the Online provider "sipfed.online.lync.com."</span></span>

## <a name="move-online-users-who-were-originally-on-premises-to-on-premises"></a><span data-ttu-id="af3c9-202">Переместите online пользователей (, которые были локально) локально</span><span class="sxs-lookup"><span data-stu-id="af3c9-202">Move online users (who were originally on premises) to on premises</span></span>
<span data-ttu-id="af3c9-203"><a name="BKMK_originallyonprem"> </a></span><span class="sxs-lookup"><span data-stu-id="af3c9-203"></span></span>

<span data-ttu-id="af3c9-204">Этот раздел применим только для пользователей, которые были созданы и включен для локального развертывания и затем перемещен из развертывания в локальной сети.</span><span class="sxs-lookup"><span data-stu-id="af3c9-204">This section applies only to users who were created and enabled for an on-premises deployment and then moved from an on-premises deployment to online.</span></span>

- <span data-ttu-id="af3c9-205">Выполните следующие командлеты перемещение пользователя из Скайп для бизнеса Online обратно в локальную, заменяя значения параметров **Identity** и **конечного** для исправления значений для вашей среды:</span><span class="sxs-lookup"><span data-stu-id="af3c9-205">Run the following cmdlets to move a user from Skype for Business Online back to on-premises, replacing the value for the **Identity** and **Target** parameters to correct values for your environment:</span></span>

  ```
  $cred=Get-Credential
  ```

  ```
  Move-CsUser -Identity username@contoso.com -Target localpool.contoso.com -Credential $cred -HostedMigrationOverrideUrl <URL>
  ```

<span data-ttu-id="af3c9-206">Формат URL-адрес, указанный для параметра **HostedMigrationOverrideUrl** должен быть URL-адрес в пул, где работает размещенная служба миграции, в следующем формате:</span><span class="sxs-lookup"><span data-stu-id="af3c9-206">The format of the URL specified for the **HostedMigrationOverrideUrl** parameter must be the URL to the pool where the Hosted Migration service is running, in the following format:</span></span>

 <span data-ttu-id="af3c9-207">_Https://\<полное доменное имя пула\>/HostedMigration/hostedmigrationService.svc_.</span><span class="sxs-lookup"><span data-stu-id="af3c9-207">_Https://\<Pool FQDN\>/HostedMigration/hostedmigrationService.svc_.</span></span> <span data-ttu-id="af3c9-208">URL-адрес службы миграции с размещением можно определить по URL-адресу панели управления Lync Online для учетной записи клиента Office 365.</span><span class="sxs-lookup"><span data-stu-id="af3c9-208">You can determine the URL to the Hosted Migration Service by viewing the URL for the Lync Online Control Panel for your Office 365 tenant account.</span></span>

### <a name="to-determine-the-hosted-migration-service-url-for-your-office-365-tenant"></a><span data-ttu-id="af3c9-209">Определение URL-адреса размещенной службы миграции для своего клиента Office 365</span><span class="sxs-lookup"><span data-stu-id="af3c9-209">To determine the Hosted Migration Service URL for your Office 365 tenant</span></span>

1. <span data-ttu-id="af3c9-210">Выполните вход в свое клиентское приложение Office 365 как администратор.</span><span class="sxs-lookup"><span data-stu-id="af3c9-210">Login to your Office 365 tenant as an administrator.</span></span>

2. <span data-ttu-id="af3c9-211">Откройте **Центр администрирования Skype для бизнеса**.</span><span class="sxs-lookup"><span data-stu-id="af3c9-211">Open the **Skype for Business admin center**.</span></span>

3. <span data-ttu-id="af3c9-p119">Не закрывая окна **Центр администрирования Skype для бизнеса**, выделите и скопируйте URL-адрес в адресную строку в **lync.com**. Примерный URL-адрес выглядит так, как показано далее:</span><span class="sxs-lookup"><span data-stu-id="af3c9-p119">With the **Skype for Business admin center** displayed, select and copy the URL in the address bar up to **lync.com**. An example URL looks similar to the following:</span></span>

     `https://webdir0a.online.lync.com/lscp/?language=en-US&amp;tenantID=`

4. <span data-ttu-id="af3c9-214">Заменяя **webdir** в URL-адресе на **admin**, получаем следующее:</span><span class="sxs-lookup"><span data-stu-id="af3c9-214">Replace **webdir** in the URL with **admin**, resulting in the following:</span></span>

     `https://admin0a.online.lync.com`

5. <span data-ttu-id="af3c9-215">Добавьте к URL-адресу следующую строку: **/HostedMigration/hostedmigrationservice.svc**.</span><span class="sxs-lookup"><span data-stu-id="af3c9-215">Append the following string to the URL: **/HostedMigration/hostedmigrationservice.svc**.</span></span>

    <span data-ttu-id="af3c9-216">Полученный URL-адрес, который соответствует значению **HostedMigrationOverrideUrl**, должен выглядеть следующим образом:</span><span class="sxs-lookup"><span data-stu-id="af3c9-216">The resulting URL, which is the value of the **HostedMigrationOverrideUrl**, should look like the following:</span></span>

     `https://admin0a.online.lync.com/HostedMigration/hostedmigrationservice.svc`


