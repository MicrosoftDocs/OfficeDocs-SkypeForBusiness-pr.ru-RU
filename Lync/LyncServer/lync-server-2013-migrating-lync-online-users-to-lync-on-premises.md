---
title: 'Lync Server 2013: переход пользователей Lync Online в локальное Lync'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Migrating Lync Online users to Lync on-premises
ms:assetid: 0e29605b-db2d-4cbf-b6a9-15db6b9fdabc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn689115(v=OCS.15)
ms:contentKeyID: 62258120
ms.date: 11/13/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 47fb8d24a2bb112ab07d35097414141b9eaaa606
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/08/2020
ms.locfileid: "40991654"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migrating-lync-online-users-to-lync-on-premises-in-lync-server-2013"></a><span data-ttu-id="bc7d9-102">Миграция пользователей Lync Online в локальное Lync в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bc7d9-102">Migrating Lync Online users to Lync on-premises in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bc7d9-103">_**Тема последнего изменения:** 2015-11-13_</span><span class="sxs-lookup"><span data-stu-id="bc7d9-103">_**Topic Last Modified:** 2015-11-13_</span></span>

<div class="">


> [!IMPORTANT]  
> <span data-ttu-id="bc7d9-104">Эти действия необходимы только для миграции учетных записей пользователей, изначально включенных для Lync в Lync Online, до того как вы разрешаете локальное развертывание Lync.</span><span class="sxs-lookup"><span data-stu-id="bc7d9-104">These steps are necessary only for migrating user accounts that were originally enabled for Lync in Lync Online, before you deployed Lync on-premises.</span></span> <span data-ttu-id="bc7d9-105">Чтобы переместить пользователей, изначально подключенных к локальной среде Lync, а затем переместить их в Lync Online, читайте в разделе <A href="lync-server-2013-administering-users-in-a-hybrid-deployment.md">Администрирование пользователей в гибридном развертывании Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="bc7d9-105">To move users who were originally enabled for Lync on-premises, then later moved to Lync Online, see <A href="lync-server-2013-administering-users-in-a-hybrid-deployment.md">Administering users in a hybrid Lync Server 2013 deployment</A>.</span></span><BR><span data-ttu-id="bc7d9-106">Кроме того, у всех перемещаемых пользователей должны быть учетные записи в локальной службе каталогов Active Directory.</span><span class="sxs-lookup"><span data-stu-id="bc7d9-106">Additionally, all users being moved must have accounts in the on-premises Active Directory.</span></span>



</div>

<div>

## <a name="migrating-user-accounts-originally-enabled-in-lync-online-to-lync-on-premises"></a><span data-ttu-id="bc7d9-107">Перенос учетных записей пользователей, изначально включенных в Lync Online, в локальное Lync</span><span class="sxs-lookup"><span data-stu-id="bc7d9-107">Migrating User Accounts Originally Enabled in Lync Online to Lync On-Premises</span></span>

1.  <span data-ttu-id="bc7d9-108">Сначала убедитесь в том, что ваша организация настроена для гибридного развертывания.</span><span class="sxs-lookup"><span data-stu-id="bc7d9-108">First, make sure that your organization is configured for hybrid.</span></span>
    
      - <span data-ttu-id="bc7d9-109">Установите средство синхронизации Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="bc7d9-109">Install the Azure Active Directory Sync Tool.</span></span> <span data-ttu-id="bc7d9-110">Дополнительные сведения см. в статье <http://social.technet.microsoft.com/wiki/contents/articles/19098.howto-install-the-windows-azure-active-directory-sync-tool.aspx>.</span><span class="sxs-lookup"><span data-stu-id="bc7d9-110">For more information, see <http://social.technet.microsoft.com/wiki/contents/articles/19098.howto-install-the-windows-azure-active-directory-sync-tool.aspx>.</span></span>
    
      - <span data-ttu-id="bc7d9-111">Чтобы разрешить пользователям использовать единый вход для Lync Online, установите службы <http://social.technet.microsoft.com/wiki/contents/articles/1011.active-directory-federation-services-ad-fs-overview.aspx>федерации Active Directory.</span><span class="sxs-lookup"><span data-stu-id="bc7d9-111">To enable your users to use single sign-on for Lync Online, install Active Directory Federation Services <http://social.technet.microsoft.com/wiki/contents/articles/1011.active-directory-federation-services-ad-fs-overview.aspx>.</span></span>
    
      - <span data-ttu-id="bc7d9-112">В локальной среде Lync Server Management Shell введите следующие командлеты, чтобы создать поставщика услуг размещения для Lync Online:</span><span class="sxs-lookup"><span data-stu-id="bc7d9-112">On your on-premises deployment, in Lync Server Management Shell, type the following cmdlets to create the hosting provider for Lync Online:</span></span>
        
           ```PowerShell
           Set-CsAccessEdgeConfiguration -AllowOutsideUsers 1 -AllowFederatedUsers 1 -UseDnsSrvRouting -EnablePartnerDiscovery $true
           ```
        
           ```PowerShell
            New-CsHostingProvider -Identity LyncOnline -ProxyFqdn "sipfed.online.lync.com" -Enabled $true -EnabledSharedAddressSpace $true -HostsOCSUsers $true -VerificationLevel UseSourceVerification -IsLocal $false -AutodiscoverUrl https://webdir.online.lync.com/Autodiscover/AutodiscoverService.svc/root
           ```

2.  <span data-ttu-id="bc7d9-113">Убедитесь, что на локальных серверах пограничного сервера есть цепочка сертификатов, обеспечивающая подключение к Lync Online, как показано в приведенной ниже таблице.</span><span class="sxs-lookup"><span data-stu-id="bc7d9-113">Confirm that, on your on-premises Edge Servers, you have the certificate chain that enables connection to Lync Online, as shown in the following table.</span></span> <span data-ttu-id="bc7d9-114">Вы можете загрузить эту цепь здесь:https://support.office.com/article/office-365-certificate-chains-0c03e6b3-e73f-4316-9e2b-bf4091ae96bb</span><span class="sxs-lookup"><span data-stu-id="bc7d9-114">You can download this chain here: https://support.office.com/article/office-365-certificate-chains-0c03e6b3-e73f-4316-9e2b-bf4091ae96bb</span></span>


    <table>
    <colgroup>
    <col style="width: 50%" />
    <col style="width: 50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><span data-ttu-id="bc7d9-115">Сертификат</span><span class="sxs-lookup"><span data-stu-id="bc7d9-115">Certificate</span></span></th>
    <th><span data-ttu-id="bc7d9-116">Хранилище сертификатов</span><span class="sxs-lookup"><span data-stu-id="bc7d9-116">Certificate Store</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><span data-ttu-id="bc7d9-117">Корневой Baltimore CyberTrust</span><span class="sxs-lookup"><span data-stu-id="bc7d9-117">Baltimore CyberTrust Root</span></span></p></td>
    <td><p><span data-ttu-id="bc7d9-118">Доверенный корневой ЦС</span><span class="sxs-lookup"><span data-stu-id="bc7d9-118">Trusted Root CA</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="bc7d9-119">Microsoft Internet Authority (сертификат нового ЦС)</span><span class="sxs-lookup"><span data-stu-id="bc7d9-119">Microsoft Internet Authority (New CA certificate)</span></span></p></td>
    <td><p><span data-ttu-id="bc7d9-120">Промежуточный ЦС</span><span class="sxs-lookup"><span data-stu-id="bc7d9-120">Intermediate CA</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="bc7d9-121">MSIT Machine Auth CA2 (новый выдающий ЦС2)</span><span class="sxs-lookup"><span data-stu-id="bc7d9-121">MSIT Machine Auth CA2 (New Issuing CA2)</span></span></p></td>
    <td><p><span data-ttu-id="bc7d9-122">Промежуточный ЦС</span><span class="sxs-lookup"><span data-stu-id="bc7d9-122">Intermediate CA</span></span></p></td>
    </tr>
    </tbody>
    </table>

3.  <span data-ttu-id="bc7d9-123">В локальной службе каталогов Active Directory включите затронутые учетные записи пользователей в локальной среде Lync.</span><span class="sxs-lookup"><span data-stu-id="bc7d9-123">In your on-premises Active Directory, enable the affected user accounts for Lync on-premises.</span></span> <span data-ttu-id="bc7d9-124">Для отдельных пользователей это можно сделать путем ввода следующего командлета:</span><span class="sxs-lookup"><span data-stu-id="bc7d9-124">You can do this for an individual user by typing the following cmdlet:</span></span>
    
        Enable-CsUser
        -Identity "username" 
        -SipAddress "sip: username@contoso.com"
        -HostingProviderProxyFqdn "sipfed.online.lync.com"
    
    <span data-ttu-id="bc7d9-125">Или можно создать сценарий для считывания имен пользователей из файла и передачи их как входных данных командлету Enable-CsUser:</span><span class="sxs-lookup"><span data-stu-id="bc7d9-125">Or you can create a script that reads user names from a file and provides them as input to the Enable-CsUser cmdlet:</span></span>
    
        Enable-CsUser
        -Identity $Identity 
        -SipAddress $SipAddress 
        -HostingProviderProxyFqdn "sipfed.online.lync.com"

4.  <span data-ttu-id="bc7d9-126">Запустите DirSync, чтобы синхронизировать пользователей Lync Online с обновленными локальными пользователями Lync.</span><span class="sxs-lookup"><span data-stu-id="bc7d9-126">Run DirSync to sync the Lync Online users with the updated Lync on-premises users.</span></span>

5.  <span data-ttu-id="bc7d9-127">Обновите некоторые записи DNS, чтобы направить весь трафик SIP на локальный Lync:</span><span class="sxs-lookup"><span data-stu-id="bc7d9-127">Update some DNS records to direct all SIP traffic to Lync on-premises:</span></span>
    
      - <span data-ttu-id="bc7d9-128">Обновите запись **lyncdiscover.contoso.com** A, указав полное доменное имя локального обратного прокси-сервера.</span><span class="sxs-lookup"><span data-stu-id="bc7d9-128">Update the **lyncdiscover.contoso.com** A record to point to the FQDN of the on-premises reverse proxy server.</span></span>
    
      - <span data-ttu-id="bc7d9-129">Обновите версию \*\**\_SIP *\_ . tls.contoso.com** SRV-запись, разрешаемая на общедоступный IP-адрес или виртуальную ЛС для службы Edge Access в локальной среде Lync.</span><span class="sxs-lookup"><span data-stu-id="bc7d9-129">Update the \***\_sip\*.\_tls.contoso.com** SRV record to resolve to the public IP or VIP address of the Access Edge service of Lync on-premises.</span></span>
    
      - <span data-ttu-id="bc7d9-130">Обновите \*\**\_сипфедератионтлс *.\_ tcp.contoso.com** SRV-запись, разрешаемая на общедоступный IP-адрес или виртуальную ЛС для службы Edge Access в локальной среде Lync.</span><span class="sxs-lookup"><span data-stu-id="bc7d9-130">Update the \***\_sipfederationtls\*.\_tcp.contoso.com** SRV record to resolve to the public IP or VIP address of the Access Edge service of Lync on-premises.</span></span>
    
      - <span data-ttu-id="bc7d9-131">Если в организации используется комбинированная DNS (иногда называется "разделенной DNS"), убедитесь, что пользователи, разрешающие имена во внутренней зоне DNS, направляются в интерфейсный пул.</span><span class="sxs-lookup"><span data-stu-id="bc7d9-131">If your organization uses split DNS (sometimes called “split-brain DNS”), make sure that users resolving names through the internal DNS zone are directed to the Front End Pool.</span></span>

6.  <span data-ttu-id="bc7d9-132">Введите `Get-CsUser` командлет для проверки некоторых свойств пользователей, которых вы хотите переместить.</span><span class="sxs-lookup"><span data-stu-id="bc7d9-132">Type the `Get-CsUser` cmdlet to check some properties about the users you’ll be moving.</span></span> <span data-ttu-id="bc7d9-133">Необходимо убедиться в том, что в Хостингпровидерпроксифкдн задано значение `"sipfed.online.lync.com"` и правильно заданы адреса SIP.</span><span class="sxs-lookup"><span data-stu-id="bc7d9-133">You want to make sure that the HostingProviderProxyFQDN is set to `"sipfed.online.lync.com"` and that the SIP addresses are set correctly.</span></span>

7.  <span data-ttu-id="bc7d9-134">Переместить пользователей Lync Online в локальное Lync.</span><span class="sxs-lookup"><span data-stu-id="bc7d9-134">Move Lync Online users to Lync on-premises.</span></span>
    
    <span data-ttu-id="bc7d9-135">Чтобы переместить одного пользователя, введите следующее:</span><span class="sxs-lookup"><span data-stu-id="bc7d9-135">To move a single user, type this:</span></span>
    
       ```PowerShell
       $cred = Get-Credential
       ```
    
       ```PowerShell
       Move-CsUser -Identity <username>@contoso.com -Target "<fe-pool>.contoso.com" -Credential $cred -HostedMigrationOverrideURL <URL>
       ```
    
    <span data-ttu-id="bc7d9-136">Командлет **Get-CsUSer** позволяет переместить несколько пользователей, выбрав их по некоторому свойству.</span><span class="sxs-lookup"><span data-stu-id="bc7d9-136">You can move multiple users by using the **Get-CsUSer** cmdlet with the –Filter parameter to select the users with a specific property.</span></span> <span data-ttu-id="bc7d9-137">Например, вы можете выбрать всех пользователей Lync Online с помощью фильтрации для {Host Provider-EQ "sipfed.online.lync.om"}.</span><span class="sxs-lookup"><span data-stu-id="bc7d9-137">For example, you could select all Lync Online users by filtering for {Hosting Provider –eq “sipfed.online.lync.om”}.</span></span> <span data-ttu-id="bc7d9-138">Возвращенных пользователей можно затем передать командлету **Move-CsUSer**, как показано ниже.</span><span class="sxs-lookup"><span data-stu-id="bc7d9-138">You can then pipe the returned users to the **Move-CsUSer** cmdlet, as shown below.</span></span>
    
        Get-CsUser -Filter {Hosting Provider -eq "sipfed.online.lync.com"} | Move-CsUser -Target "<fe-pool>.contoso.com" -Credential $creds -HostedMigrationOverrideURL <URL>
    
    <span data-ttu-id="bc7d9-139">Формат URL-адреса, заданный для параметра **хостедмигратионоверридеурл** , должен быть URL-адресом пула, на котором запущена служба размещенной миграции, в следующем формате *:\<HTTPS://FQDN\>Pool/хостедмигратион/хостедмигратионсервице.СВК*.</span><span class="sxs-lookup"><span data-stu-id="bc7d9-139">The format of the URL specified for the **HostedMigrationOverrideUrl** parameter must be the URL to the pool where the Hosted Migration service is running, in the following format: *Https://\<Pool FQDN\>/HostedMigration/hostedmigrationService.svc*.</span></span>
    
    <span data-ttu-id="bc7d9-140">URL-адрес службы миграции с размещением можно определить по URL-адресу панели управления Lync Online для учетной записи клиента Office 365.</span><span class="sxs-lookup"><span data-stu-id="bc7d9-140">You can determine the URL to the Hosted Migration Service by viewing the URL for the Lync Online Control Panel for your Office 365 tenant account.</span></span>
    
    <div>
    
    ## <a name="to-determine-the-hosted-migration-service-url-for-your-office-365-tenant"></a><span data-ttu-id="bc7d9-141">Определение URL-адреса размещенной службы миграции для своего клиента Office 365</span><span class="sxs-lookup"><span data-stu-id="bc7d9-141">To determine the Hosted Migration Service URL for your Office 365 tenant</span></span>
    
    1.  <span data-ttu-id="bc7d9-142">Выполните вход в свое клиентское приложение Office 365 как администратор.</span><span class="sxs-lookup"><span data-stu-id="bc7d9-142">Login to your Office 365 tenant as an administrator.</span></span>
    
    2.  <span data-ttu-id="bc7d9-143">Откройте **центр администрирования Lync**.</span><span class="sxs-lookup"><span data-stu-id="bc7d9-143">Open the **Lync admin center**.</span></span>
    
    3.  <span data-ttu-id="bc7d9-144">В **центре администрирования Lync** выберите и скопируйте URL-адрес в адресной строке на **Lync.com**.</span><span class="sxs-lookup"><span data-stu-id="bc7d9-144">With the **Lync admin center** displayed, select and copy the URL in the address bar up to **lync.com**.</span></span> <span data-ttu-id="bc7d9-145">Ниже показан возможны пример URL-адреса</span><span class="sxs-lookup"><span data-stu-id="bc7d9-145">An example URL looks similar to the following:</span></span>
        
        `https://webdir0a.online.lync.com/lscp/?language=en-US&tenantID=`
    
    4.  <span data-ttu-id="bc7d9-146">После замены фрагмента **webdir** в URL-адресе фрагментом **admin** получается следующий результат:</span><span class="sxs-lookup"><span data-stu-id="bc7d9-146">Replace **webdir** in the URL with **admin**, resulting in the following:</span></span>
        
        `https://admin0a.online.lync.com`
    
    5.  <span data-ttu-id="bc7d9-147">Добавьте к URL-адресу следующую строку: **/HostedMigration/hostedmigrationservice.svc**.</span><span class="sxs-lookup"><span data-stu-id="bc7d9-147">Append the following string to the URL: **/HostedMigration/hostedmigrationservice.svc**.</span></span>
        
        <span data-ttu-id="bc7d9-148">Итоговый URL-адрес, который служит значением параметра **HostedMigrationOverrideUrl**, должен выглядеть следующим образом:</span><span class="sxs-lookup"><span data-stu-id="bc7d9-148">The resulting URL, which is the value of the **HostedMigrationOverrideUrl**, should look like the following:</span></span>
        
        `https://admin0a.online.lync.com/HostedMigration/hostedmigrationservice.svc`
    
    </div>
    
    <div class="">
    

    > [!NOTE]  
    > <span data-ttu-id="bc7d9-149">По умолчанию максимальный размер файлов журналов транзакций базы данных rtcxds составляет 16 ГБ.</span><span class="sxs-lookup"><span data-stu-id="bc7d9-149">The default maximum size for transaction log files of the rtcxds database is 16 GB.</span></span> <span data-ttu-id="bc7d9-150">Это может оказаться недостаточным для одновременного перемещения большого количества пользователей, особенно если включено зеркальное отображение.</span><span class="sxs-lookup"><span data-stu-id="bc7d9-150">This might not be big enough if you’re moving a large number of users at once, especially if you have mirroring enabled.</span></span> <span data-ttu-id="bc7d9-151">Во избежание такой ситуации можно увеличить размер файлов или регулярно создавать резервные копии файлов журналов.</span><span class="sxs-lookup"><span data-stu-id="bc7d9-151">To get around this you can increase the file size or back up the log files regularly.</span></span> <span data-ttu-id="bc7d9-152">Дополнительные сведения см. в статье <A class=uri href="http://support.microsoft.com/kb/2756725">http://support.microsoft.com/kb/2756725</A>.</span><span class="sxs-lookup"><span data-stu-id="bc7d9-152">For more information, see <A class=uri href="http://support.microsoft.com/kb/2756725">http://support.microsoft.com/kb/2756725</A>.</span></span>

    
    </div>

8.  <span data-ttu-id="bc7d9-153">Это необязательный шаг.</span><span class="sxs-lookup"><span data-stu-id="bc7d9-153">This is an optional step.</span></span> <span data-ttu-id="bc7d9-154">Если вам нужно интегрироваться с Exchange 2013 Online, необходимо использовать дополнительного поставщика услуг размещения.</span><span class="sxs-lookup"><span data-stu-id="bc7d9-154">If you need to integrate with Exchange 2013 Online, you need to use an additional hosting provider.</span></span> <span data-ttu-id="bc7d9-155">Подробности можно найти [в разделе Настройка локальной интеграции Lync Server 2013 с Exchange Online](lync-server-2013-configuring-on-premises-lync-server-integration-with-exchange-online.md).</span><span class="sxs-lookup"><span data-stu-id="bc7d9-155">For details, see [Configuring on-premises Lync Server 2013 integration with Exchange Online](lync-server-2013-configuring-on-premises-lync-server-integration-with-exchange-online.md).</span></span>

9.  <span data-ttu-id="bc7d9-p110">Теперь пользователи перемещаются. Чтобы проверить, что пользователь имеет правильные значения для атрибутов, показанных в таблице ниже, введите следующий командлет:</span><span class="sxs-lookup"><span data-stu-id="bc7d9-p110">The users are now moved. To check that a user has correct values for the attributes shown in the following table, type this cmdlet:</span></span>
    
        Get-CsUser | fl DisplayName,HostingProvider,SipAddress,Enabled
    
    
    <table>
    <colgroup>
    <col style="width: 25%" />
    <col style="width: 25%" />
    <col style="width: 25%" />
    <col style="width: 25%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><span data-ttu-id="bc7d9-158">Атрибут Active Directory</span><span class="sxs-lookup"><span data-stu-id="bc7d9-158">Active Directory attribute</span></span></th>
    <th><span data-ttu-id="bc7d9-159">Имя атрибута</span><span class="sxs-lookup"><span data-stu-id="bc7d9-159">Attribute name</span></span></th>
    <th><span data-ttu-id="bc7d9-160">Правильное значение для пользователя Lync Online</span><span class="sxs-lookup"><span data-stu-id="bc7d9-160">Correct value for Lync Online user</span></span></th>
    <th><span data-ttu-id="bc7d9-161">Правильное значение для локальных пользователей Lync</span><span class="sxs-lookup"><span data-stu-id="bc7d9-161">Correct value for Lync on–premises users</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><span data-ttu-id="bc7d9-162">msRTCSIP-DeploymentLocator</span><span class="sxs-lookup"><span data-stu-id="bc7d9-162">msRTCSIP-DeploymentLocator</span></span></p></td>
    <td><p><span data-ttu-id="bc7d9-163">HostingProvider</span><span class="sxs-lookup"><span data-stu-id="bc7d9-163">HostingProvider</span></span></p></td>
    <td><p><span data-ttu-id="bc7d9-164">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="bc7d9-164">sipfed.online.lync.com</span></span></p></td>
    <td><p><span data-ttu-id="bc7d9-165">SRV:</span><span class="sxs-lookup"><span data-stu-id="bc7d9-165">SRV:</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="bc7d9-166">msRTCSIP-PrimaryUserAddress</span><span class="sxs-lookup"><span data-stu-id="bc7d9-166">msRTCSIP-PrimaryUserAddress</span></span></p></td>
    <td><p><span data-ttu-id="bc7d9-167">SIPAddress</span><span class="sxs-lookup"><span data-stu-id="bc7d9-167">SIPAddress</span></span></p></td>
    <td><p><span data-ttu-id="bc7d9-168">sip:userName@contoso.com</span><span class="sxs-lookup"><span data-stu-id="bc7d9-168">sip:userName@contoso.com</span></span></p></td>
    <td><p><span data-ttu-id="bc7d9-169">sip:userName@contoso.com</span><span class="sxs-lookup"><span data-stu-id="bc7d9-169">sip:userName@contoso.com</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="bc7d9-170">msRTCSIP-UserEnabled</span><span class="sxs-lookup"><span data-stu-id="bc7d9-170">msRTCSIP-UserEnabled</span></span></p></td>
    <td><p><span data-ttu-id="bc7d9-171">Включено</span><span class="sxs-lookup"><span data-stu-id="bc7d9-171">Enabled</span></span></p></td>
    <td><p><span data-ttu-id="bc7d9-172">Верно</span><span class="sxs-lookup"><span data-stu-id="bc7d9-172">True</span></span></p></td>
    <td><p><span data-ttu-id="bc7d9-173">Верно</span><span class="sxs-lookup"><span data-stu-id="bc7d9-173">True</span></span></p></td>
    </tr>
    </tbody>
    </table>


10. <span data-ttu-id="bc7d9-174">Каждый пользователь, который был перемещен, должен выйти из Lync, а затем снова войти в систему.</span><span class="sxs-lookup"><span data-stu-id="bc7d9-174">Each user who has been moved will need to log out of Lync, then log back in.</span></span> <span data-ttu-id="bc7d9-175">При входе они должны проверить свои списки контактов и в случае необходимости добавить контакты.</span><span class="sxs-lookup"><span data-stu-id="bc7d9-175">When they log in they should verify their contact lists, and add contacts if needed.</span></span>
    
    <span data-ttu-id="bc7d9-176">Обратите внимание, что запланированные собрания не переносятся из Lync Online в локальное Lync.</span><span class="sxs-lookup"><span data-stu-id="bc7d9-176">Note that scheduled meetings are not migrated from Lync Online to Lync on-premises.</span></span> <span data-ttu-id="bc7d9-177">После перемещения пользователям потребуется запланировать такие собрания заново.</span><span class="sxs-lookup"><span data-stu-id="bc7d9-177">Users will need to reschedule these meetings after being moved.</span></span>
    
    <span data-ttu-id="bc7d9-178">После того как DNS-записи обновлены и все пользователи направлены на локальные, атрибут Хостингпровидер направляет пользователю Lync команду либо использовать записи SRV, либо направить их на Интернет-провайдер "sipfed.online.lync.com".</span><span class="sxs-lookup"><span data-stu-id="bc7d9-178">After the DNS records are updated and all users are directed to On premise, the HostingProvider attribute directs the Lync user to either use SRV records or direct them to the Online provider “sipfed.online.lync.com.”</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

