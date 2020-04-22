---
title: 'Lync Server 2013: миграция пользователей Lync Online в локальную среду Lync'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Migrating Lync Online users to Lync on-premises
ms:assetid: 0e29605b-db2d-4cbf-b6a9-15db6b9fdabc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn689115(v=OCS.15)
ms:contentKeyID: 62258120
ms.date: 11/13/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e87b977dd70227d134e5feae8df2ea089e216df3
ms.sourcegitcommit: ea54990240fcdde1fb061489468aadd02fb4afc7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2020
ms.locfileid: "43780748"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="migrating-lync-online-users-to-lync-on-premises-in-lync-server-2013"></a><span data-ttu-id="94808-102">Миграция пользователей Lync Online в локальную среду Lync в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="94808-102">Migrating Lync Online users to Lync on-premises in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="94808-103">_**Последнее изменение темы:** 2015-11-13_</span><span class="sxs-lookup"><span data-stu-id="94808-103">_**Topic Last Modified:** 2015-11-13_</span></span>

<div class="">


> [!IMPORTANT]  
> <span data-ttu-id="94808-104">Эти действия необходимы только для переноса учетных записей пользователей, изначально включенных для Lync в Lync Online, перед развертыванием локального компьютера Lync.</span><span class="sxs-lookup"><span data-stu-id="94808-104">These steps are necessary only for migrating user accounts that were originally enabled for Lync in Lync Online, before you deployed Lync on-premises.</span></span> <span data-ttu-id="94808-105">Чтобы переместить пользователей, изначально подключенных к локальной среде Lync, а затем переместить их в Lync Online, ознакомьтесь со статьей <A href="lync-server-2013-administering-users-in-a-hybrid-deployment.md">Администрирование пользователей в гибридном развертывании Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="94808-105">To move users who were originally enabled for Lync on-premises, then later moved to Lync Online, see <A href="lync-server-2013-administering-users-in-a-hybrid-deployment.md">Administering users in a hybrid Lync Server 2013 deployment</A>.</span></span><BR><span data-ttu-id="94808-106">Кроме того, все перемещаемые пользователи должны иметь учетные записи в локальной службе Active Directory.</span><span class="sxs-lookup"><span data-stu-id="94808-106">Additionally, all users being moved must have accounts in the on-premises Active Directory.</span></span>



</div>

<div>

## <a name="migrating-user-accounts-originally-enabled-in-lync-online-to-lync-on-premises"></a><span data-ttu-id="94808-107">Перенос учетных записей пользователей, изначально включенных в Lync Online, в локальную среду Lync</span><span class="sxs-lookup"><span data-stu-id="94808-107">Migrating User Accounts Originally Enabled in Lync Online to Lync On-Premises</span></span>

1.  <span data-ttu-id="94808-108">Сначала убедитесь, что ваша организация настроена для гибридной среды.</span><span class="sxs-lookup"><span data-stu-id="94808-108">First, make sure that your organization is configured for hybrid.</span></span>
    
      - <span data-ttu-id="94808-109">Установите средство синхронизации Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="94808-109">Install the Azure Active Directory Sync Tool.</span></span> <span data-ttu-id="94808-110">Дополнительные сведения см. в статье <https://social.technet.microsoft.com/wiki/contents/articles/19098.howto-install-the-windows-azure-active-directory-sync-tool.aspx>.</span><span class="sxs-lookup"><span data-stu-id="94808-110">For more information, see <https://social.technet.microsoft.com/wiki/contents/articles/19098.howto-install-the-windows-azure-active-directory-sync-tool.aspx>.</span></span>
    
      - <span data-ttu-id="94808-111">Чтобы разрешить пользователям использовать единый вход для Lync Online, установите службы <https://social.technet.microsoft.com/wiki/contents/articles/1011.active-directory-federation-services-ad-fs-overview.aspx>федерации Active Directory.</span><span class="sxs-lookup"><span data-stu-id="94808-111">To enable your users to use single sign-on for Lync Online, install Active Directory Federation Services <https://social.technet.microsoft.com/wiki/contents/articles/1011.active-directory-federation-services-ad-fs-overview.aspx>.</span></span>
    
      - <span data-ttu-id="94808-112">В локальном развертывании в командной консоли Lync Server введите следующие командлеты, чтобы создать поставщика услуг хостинга для Lync Online:</span><span class="sxs-lookup"><span data-stu-id="94808-112">On your on-premises deployment, in Lync Server Management Shell, type the following cmdlets to create the hosting provider for Lync Online:</span></span>
        
           ```PowerShell
           Set-CsAccessEdgeConfiguration -AllowOutsideUsers 1 -AllowFederatedUsers 1 -UseDnsSrvRouting -EnablePartnerDiscovery $true
           ```
        
           ```PowerShell
            New-CsHostingProvider -Identity LyncOnline -ProxyFqdn "sipfed.online.lync.com" -Enabled $true -EnabledSharedAddressSpace $true -HostsOCSUsers $true -VerificationLevel UseSourceVerification -IsLocal $false -AutodiscoverUrl https://webdir.online.lync.com/Autodiscover/AutodiscoverService.svc/root
           ```

2.  <span data-ttu-id="94808-113">Убедитесь, что на локальных пограничных серверах есть цепочка сертификатов, обеспечивающая подключение к Lync Online, как показано в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="94808-113">Confirm that, on your on-premises Edge Servers, you have the certificate chain that enables connection to Lync Online, as shown in the following table.</span></span> <span data-ttu-id="94808-114">Эту цепочку можно загрузить здесь:https://support.office.com/article/office-365-certificate-chains-0c03e6b3-e73f-4316-9e2b-bf4091ae96bb</span><span class="sxs-lookup"><span data-stu-id="94808-114">You can download this chain here: https://support.office.com/article/office-365-certificate-chains-0c03e6b3-e73f-4316-9e2b-bf4091ae96bb</span></span>


    <table>
    <colgroup>
    <col style="width: 50%" />
    <col style="width: 50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><span data-ttu-id="94808-115">Сертификат</span><span class="sxs-lookup"><span data-stu-id="94808-115">Certificate</span></span></th>
    <th><span data-ttu-id="94808-116">Хранилище сертификатов</span><span class="sxs-lookup"><span data-stu-id="94808-116">Certificate Store</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><span data-ttu-id="94808-117">Baltimore CyberTrust Root</span><span class="sxs-lookup"><span data-stu-id="94808-117">Baltimore CyberTrust Root</span></span></p></td>
    <td><p><span data-ttu-id="94808-118">Доверенный корневой ЦС</span><span class="sxs-lookup"><span data-stu-id="94808-118">Trusted Root CA</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="94808-119">Microsoft Internet Authority (новый сертификат ЦС)</span><span class="sxs-lookup"><span data-stu-id="94808-119">Microsoft Internet Authority (New CA certificate)</span></span></p></td>
    <td><p><span data-ttu-id="94808-120">Промежуточный ЦС</span><span class="sxs-lookup"><span data-stu-id="94808-120">Intermediate CA</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="94808-121">MSIT Machine auth CA2 (новый выпуск CA2)</span><span class="sxs-lookup"><span data-stu-id="94808-121">MSIT Machine Auth CA2 (New Issuing CA2)</span></span></p></td>
    <td><p><span data-ttu-id="94808-122">Промежуточный ЦС</span><span class="sxs-lookup"><span data-stu-id="94808-122">Intermediate CA</span></span></p></td>
    </tr>
    </tbody>
    </table>

3.  <span data-ttu-id="94808-123">В локальной службе Active Directory включите затронутые учетные записи пользователей для локальной среды Lync.</span><span class="sxs-lookup"><span data-stu-id="94808-123">In your on-premises Active Directory, enable the affected user accounts for Lync on-premises.</span></span> <span data-ttu-id="94808-124">Это можно сделать для отдельного пользователя, введя следующий командлет:</span><span class="sxs-lookup"><span data-stu-id="94808-124">You can do this for an individual user by typing the following cmdlet:</span></span>
    
        Enable-CsUser
        -Identity "username" 
        -SipAddress "sip: username@contoso.com"
        -HostingProviderProxyFqdn "sipfed.online.lync.com"
    
    <span data-ttu-id="94808-125">Или можно создать сценарий, считывающий имена пользователей из файла и предоставляющий их в качестве входных данных для командлета Enable – CsUser:</span><span class="sxs-lookup"><span data-stu-id="94808-125">Or you can create a script that reads user names from a file and provides them as input to the Enable-CsUser cmdlet:</span></span>
    
        Enable-CsUser
        -Identity $Identity 
        -SipAddress $SipAddress 
        -HostingProviderProxyFqdn "sipfed.online.lync.com"

4.  <span data-ttu-id="94808-126">Запустите DirSync, чтобы синхронизировать пользователей Lync Online с обновленными локальными пользователями Lync.</span><span class="sxs-lookup"><span data-stu-id="94808-126">Run DirSync to sync the Lync Online users with the updated Lync on-premises users.</span></span>

5.  <span data-ttu-id="94808-127">Обновите некоторые записи DNS, чтобы направить весь трафик SIP в локальную среду Lync:</span><span class="sxs-lookup"><span data-stu-id="94808-127">Update some DNS records to direct all SIP traffic to Lync on-premises:</span></span>
    
      - <span data-ttu-id="94808-128">Обновите запись **Lyncdiscover.contoso.com** A, УКАЗАВ полное доменное имя локального обратного прокси-сервера.</span><span class="sxs-lookup"><span data-stu-id="94808-128">Update the **lyncdiscover.contoso.com** A record to point to the FQDN of the on-premises reverse proxy server.</span></span>
    
      - <span data-ttu-id="94808-129">Обновление \*\*\*\_SIP \*.\_ \*\*запись SRV TLS.contoso.com, которая разрешается в общедоступный IP-адрес или виртуальный IP-адрес службы пограничной службы доступа в локальной среде Lync.</span><span class="sxs-lookup"><span data-stu-id="94808-129">Update the \***\_sip\*.\_tls.contoso.com** SRV record to resolve to the public IP or VIP address of the Access Edge service of Lync on-premises.</span></span>
    
      - <span data-ttu-id="94808-130">Обновление \*\*\*\_сипфедератионтлс \*.\_ \*\*запись SRV TCP.contoso.com, которая разрешается в общедоступный IP-адрес или виртуальный IP-адрес службы пограничной службы доступа в локальной среде Lync.</span><span class="sxs-lookup"><span data-stu-id="94808-130">Update the \***\_sipfederationtls\*.\_tcp.contoso.com** SRV record to resolve to the public IP or VIP address of the Access Edge service of Lync on-premises.</span></span>
    
      - <span data-ttu-id="94808-131">Если в организации используется разделение DNS (иногда называется "Split-мозговой DNS"), убедитесь, что пользователи, разрешающие имена через внутреннюю зону DNS, направляются в пул переднего плана.</span><span class="sxs-lookup"><span data-stu-id="94808-131">If your organization uses split DNS (sometimes called “split-brain DNS”), make sure that users resolving names through the internal DNS zone are directed to the Front End Pool.</span></span>

6.  <span data-ttu-id="94808-132">Введите `Get-CsUser` командлет, чтобы проверить некоторые свойства для перемещаемых пользователей.</span><span class="sxs-lookup"><span data-stu-id="94808-132">Type the `Get-CsUser` cmdlet to check some properties about the users you’ll be moving.</span></span> <span data-ttu-id="94808-133">Необходимо убедиться, что для `"sipfed.online.lync.com"` параметра хостингпровидерпроксифкдн задано значение, а SIP-адреса настроены правильно.</span><span class="sxs-lookup"><span data-stu-id="94808-133">You want to make sure that the HostingProviderProxyFQDN is set to `"sipfed.online.lync.com"` and that the SIP addresses are set correctly.</span></span>

7.  <span data-ttu-id="94808-134">Перемещение пользователей Lync Online в локальную среду Lync.</span><span class="sxs-lookup"><span data-stu-id="94808-134">Move Lync Online users to Lync on-premises.</span></span>
    
    <span data-ttu-id="94808-135">Чтобы переместить одного пользователя, введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="94808-135">To move a single user, type this:</span></span>
    
       ```PowerShell
       $cred = Get-Credential
       ```
    
       ```PowerShell
       Move-CsUser -Identity <username>@contoso.com -Target "<fe-pool>.contoso.com" -Credential $cred -HostedMigrationOverrideURL <URL>
       ```
    
    <span data-ttu-id="94808-136">Можно переместить несколько пользователей с помощью командлета **Get-CsUSer** с параметром – Filter, чтобы выбрать пользователей с определенным свойством.</span><span class="sxs-lookup"><span data-stu-id="94808-136">You can move multiple users by using the **Get-CsUSer** cmdlet with the –Filter parameter to select the users with a specific property.</span></span> <span data-ttu-id="94808-137">Например, вы можете выбрать всех пользователей Lync Online, выполнив фильтрацию {Hosting Provider – EQ "sipfed.online.lync.om"}.</span><span class="sxs-lookup"><span data-stu-id="94808-137">For example, you could select all Lync Online users by filtering for {Hosting Provider –eq “sipfed.online.lync.om”}.</span></span> <span data-ttu-id="94808-138">Затем можно передать возвращенных пользователей в командлет **Move – CsUSer** , как показано ниже.</span><span class="sxs-lookup"><span data-stu-id="94808-138">You can then pipe the returned users to the **Move-CsUSer** cmdlet, as shown below.</span></span>
    
        Get-CsUser -Filter {Hosting Provider -eq "sipfed.online.lync.com"} | Move-CsUser -Target "<fe-pool>.contoso.com" -Credential $creds -HostedMigrationOverrideURL <URL>
    
    <span data-ttu-id="94808-139">Формат URL-адреса, указанный для параметра **хостедмигратионоверридеурл** , должен быть URL-адресом пула, где запущена служба переноса, в следующем формате: *https://\<Pool FQDN\>/HostedMigration/hostedmigrationService.svc*.</span><span class="sxs-lookup"><span data-stu-id="94808-139">The format of the URL specified for the **HostedMigrationOverrideUrl** parameter must be the URL to the pool where the Hosted Migration service is running, in the following format: *Https://\<Pool FQDN\>/HostedMigration/hostedmigrationService.svc*.</span></span>
    
    <span data-ttu-id="94808-140">Можно определить URL-адрес размещенной службы миграции, просмотрев URL-адрес панели управления Lync Online для учетной записи организации Office 365.</span><span class="sxs-lookup"><span data-stu-id="94808-140">You can determine the URL to the Hosted Migration Service by viewing the URL for the Lync Online Control Panel for your Office 365 organization account.</span></span>
    
    <div>
    
    ## <a name="to-determine-the-hosted-migration-service-url-for-your-office-365-organization"></a><span data-ttu-id="94808-141">Определение URL-адреса размещенной службы миграции для организации Office 365</span><span class="sxs-lookup"><span data-stu-id="94808-141">To determine the Hosted Migration Service URL for your Office 365 organization</span></span>
    
    1.  <span data-ttu-id="94808-142">Войдите в организацию Office 365 от имени администратора.</span><span class="sxs-lookup"><span data-stu-id="94808-142">Login to your Office 365 organization as an administrator.</span></span>
    
    2.  <span data-ttu-id="94808-143">Откройте **центр администрирования Lync**.</span><span class="sxs-lookup"><span data-stu-id="94808-143">Open the **Lync admin center**.</span></span>
    
    3.  <span data-ttu-id="94808-144">При отображении **центра администрирования Lync** выберите и скопируйте URL-адрес в адресную строку вплоть до **Lync.com**.</span><span class="sxs-lookup"><span data-stu-id="94808-144">With the **Lync admin center** displayed, select and copy the URL in the address bar up to **lync.com**.</span></span> <span data-ttu-id="94808-145">Пример URL-адреса выглядит примерно следующим образом:</span><span class="sxs-lookup"><span data-stu-id="94808-145">An example URL looks similar to the following:</span></span>
        
        `https://webdir0a.online.lync.com/lscp/?language=en-US&tenantID=`
    
    4.  <span data-ttu-id="94808-146">Замените **webdir** в URL-адресе на **"Администратор"**, что приводит к следующим действиям:</span><span class="sxs-lookup"><span data-stu-id="94808-146">Replace **webdir** in the URL with **admin**, resulting in the following:</span></span>
        
        `https://admin0a.online.lync.com`
    
    5.  <span data-ttu-id="94808-147">Добавьте указанную ниже строку в URL-адрес: **/HostedMigration/hostedmigrationservice.svc**.</span><span class="sxs-lookup"><span data-stu-id="94808-147">Append the following string to the URL: **/HostedMigration/hostedmigrationservice.svc**.</span></span>
        
        <span data-ttu-id="94808-148">Итоговый URL-адрес, который является значением **хостедмигратионоверридеурл**, должен выглядеть следующим образом:</span><span class="sxs-lookup"><span data-stu-id="94808-148">The resulting URL, which is the value of the **HostedMigrationOverrideUrl**, should look like the following:</span></span>
        
        `https://admin0a.online.lync.com/HostedMigration/hostedmigrationservice.svc`
    
    </div>
    
    <div class="">
    

    > [!NOTE]  
    > <span data-ttu-id="94808-149">Максимальный размер файлов журналов транзакций для базы данных rtcxds по умолчанию равен 16 ГБ.</span><span class="sxs-lookup"><span data-stu-id="94808-149">The default maximum size for transaction log files of the rtcxds database is 16 GB.</span></span> <span data-ttu-id="94808-150">Это может быть недостаточно, если вы перемещаете большое число пользователей одновременно, особенно если зеркальное отображение включено.</span><span class="sxs-lookup"><span data-stu-id="94808-150">This might not be big enough if you’re moving a large number of users at once, especially if you have mirroring enabled.</span></span> <span data-ttu-id="94808-151">Чтобы обойти эту проблему, вы можете увеличить размер файла или регулярно создавать резервные копии файлов журналов.</span><span class="sxs-lookup"><span data-stu-id="94808-151">To get around this you can increase the file size or back up the log files regularly.</span></span> <span data-ttu-id="94808-152">Для получения дополнительных сведений см <A class=uri href="https://support.microsoft.com/kb/2756725">https://support.microsoft.com/kb/2756725</A>.</span><span class="sxs-lookup"><span data-stu-id="94808-152">For more information, see <A class=uri href="https://support.microsoft.com/kb/2756725">https://support.microsoft.com/kb/2756725</A>.</span></span>

    
    </div>

8.  <span data-ttu-id="94808-153">Это действие не является обязательным.</span><span class="sxs-lookup"><span data-stu-id="94808-153">This is an optional step.</span></span> <span data-ttu-id="94808-154">Если вам требуется интеграция с Exchange 2013 Online, необходимо использовать дополнительного поставщика услуг хостинга.</span><span class="sxs-lookup"><span data-stu-id="94808-154">If you need to integrate with Exchange 2013 Online, you need to use an additional hosting provider.</span></span> <span data-ttu-id="94808-155">Для получения дополнительных сведений см [Настройка локальной интеграции Lync Server 2013 с Exchange Online](lync-server-2013-configuring-on-premises-lync-server-integration-with-exchange-online.md).</span><span class="sxs-lookup"><span data-stu-id="94808-155">For details, see [Configuring on-premises Lync Server 2013 integration with Exchange Online](lync-server-2013-configuring-on-premises-lync-server-integration-with-exchange-online.md).</span></span>

9.  <span data-ttu-id="94808-156">Теперь пользователи перемещаются.</span><span class="sxs-lookup"><span data-stu-id="94808-156">The users are now moved.</span></span> <span data-ttu-id="94808-157">Чтобы убедиться, что пользователь имеет правильные значения для атрибутов, показанных в следующей таблице, введите следующий командлет:</span><span class="sxs-lookup"><span data-stu-id="94808-157">To check that a user has correct values for the attributes shown in the following table, type this cmdlet:</span></span>
    
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
    <th><span data-ttu-id="94808-158">Атрибут Active Directory</span><span class="sxs-lookup"><span data-stu-id="94808-158">Active Directory attribute</span></span></th>
    <th><span data-ttu-id="94808-159">Имя атрибута</span><span class="sxs-lookup"><span data-stu-id="94808-159">Attribute name</span></span></th>
    <th><span data-ttu-id="94808-160">Правильное значение для пользователя Lync Online</span><span class="sxs-lookup"><span data-stu-id="94808-160">Correct value for Lync Online user</span></span></th>
    <th><span data-ttu-id="94808-161">Правильное значение для локальных пользователей Lync</span><span class="sxs-lookup"><span data-stu-id="94808-161">Correct value for Lync on–premises users</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><span data-ttu-id="94808-162">msRTCSIP — Деплойментлокатор</span><span class="sxs-lookup"><span data-stu-id="94808-162">msRTCSIP-DeploymentLocator</span></span></p></td>
    <td><p><span data-ttu-id="94808-163">хостингпровидер</span><span class="sxs-lookup"><span data-stu-id="94808-163">HostingProvider</span></span></p></td>
    <td><p><span data-ttu-id="94808-164">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="94808-164">sipfed.online.lync.com</span></span></p></td>
    <td><p><span data-ttu-id="94808-165">SRV</span><span class="sxs-lookup"><span data-stu-id="94808-165">SRV:</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="94808-166">msRTCSIP — PrimaryUserAddress</span><span class="sxs-lookup"><span data-stu-id="94808-166">msRTCSIP-PrimaryUserAddress</span></span></p></td>
    <td><p><span data-ttu-id="94808-167">SIPAddress</span><span class="sxs-lookup"><span data-stu-id="94808-167">SIPAddress</span></span></p></td>
    <td><p><span data-ttu-id="94808-168">sip:userName@contoso.com</span><span class="sxs-lookup"><span data-stu-id="94808-168">sip:userName@contoso.com</span></span></p></td>
    <td><p><span data-ttu-id="94808-169">sip:userName@contoso.com</span><span class="sxs-lookup"><span data-stu-id="94808-169">sip:userName@contoso.com</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="94808-170">msRTCSIP — UserEnabled</span><span class="sxs-lookup"><span data-stu-id="94808-170">msRTCSIP-UserEnabled</span></span></p></td>
    <td><p><span data-ttu-id="94808-171">Включено</span><span class="sxs-lookup"><span data-stu-id="94808-171">Enabled</span></span></p></td>
    <td><p><span data-ttu-id="94808-172">Да</span><span class="sxs-lookup"><span data-stu-id="94808-172">True</span></span></p></td>
    <td><p><span data-ttu-id="94808-173">Да</span><span class="sxs-lookup"><span data-stu-id="94808-173">True</span></span></p></td>
    </tr>
    </tbody>
    </table>


10. <span data-ttu-id="94808-174">Для каждого перемещенного пользователя потребуется выйти из Lync, а затем войти снова.</span><span class="sxs-lookup"><span data-stu-id="94808-174">Each user who has been moved will need to log out of Lync, then log back in.</span></span> <span data-ttu-id="94808-175">Когда они выполняют вход в систему, должны проверить свои списки контактов и при необходимости добавлять контакты.</span><span class="sxs-lookup"><span data-stu-id="94808-175">When they log in they should verify their contact lists, and add contacts if needed.</span></span>
    
    <span data-ttu-id="94808-176">Обратите внимание, что запланированные собрания не переносятся из Lync Online в локальную среду Lync.</span><span class="sxs-lookup"><span data-stu-id="94808-176">Note that scheduled meetings are not migrated from Lync Online to Lync on-premises.</span></span> <span data-ttu-id="94808-177">После перемещения пользователи должны будут перепланировать эти собрания.</span><span class="sxs-lookup"><span data-stu-id="94808-177">Users will need to reschedule these meetings after being moved.</span></span>
    
    <span data-ttu-id="94808-178">После обновления DNS-записей, когда все пользователи перенаправляются на локальную версию, атрибут Хостингпровидер указывает пользователю Lync либо использовать записи SRV, либо направить их интерактивному поставщику "sipfed.online.lync.com".</span><span class="sxs-lookup"><span data-stu-id="94808-178">After the DNS records are updated and all users are directed to On premise, the HostingProvider attribute directs the Lync user to either use SRV records or direct them to the Online provider “sipfed.online.lync.com.”</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

