---
title: 'Lync Server 2013: миграция пользователей Lync Online в локальную среду Lync'
description: 'Lync Server 2013: миграция пользователей Lync Online в локальную среду Lync.'
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
ms.openlocfilehash: 620bc07def8e3c1f6b761c6398b452b4dbcd3b04
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48561005"
---
# <a name="migrating-lync-online-users-to-lync-on-premises-in-lync-server-2013"></a><span data-ttu-id="c87c2-103">Миграция пользователей Lync Online в локальную среду Lync в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c87c2-103">Migrating Lync Online users to Lync on-premises in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c87c2-104">_**Последнее изменение темы:** 2015-11-13_</span><span class="sxs-lookup"><span data-stu-id="c87c2-104">_**Topic Last Modified:** 2015-11-13_</span></span>

<div class="">


> [!IMPORTANT]  
> <span data-ttu-id="c87c2-105">Эти действия необходимы только для переноса учетных записей пользователей, изначально включенных для Lync в Lync Online, перед развертыванием локального компьютера Lync.</span><span class="sxs-lookup"><span data-stu-id="c87c2-105">These steps are necessary only for migrating user accounts that were originally enabled for Lync in Lync Online, before you deployed Lync on-premises.</span></span> <span data-ttu-id="c87c2-106">Чтобы переместить пользователей, изначально подключенных к локальной среде Lync, а затем переместить их в Lync Online, ознакомьтесь со статьей <A href="lync-server-2013-administering-users-in-a-hybrid-deployment.md">Администрирование пользователей в гибридном развертывании Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="c87c2-106">To move users who were originally enabled for Lync on-premises, then later moved to Lync Online, see <A href="lync-server-2013-administering-users-in-a-hybrid-deployment.md">Administering users in a hybrid Lync Server 2013 deployment</A>.</span></span><BR><span data-ttu-id="c87c2-107">Кроме того, все перемещаемые пользователи должны иметь учетные записи в локальной службе Active Directory.</span><span class="sxs-lookup"><span data-stu-id="c87c2-107">Additionally, all users being moved must have accounts in the on-premises Active Directory.</span></span>



</div>

<div>

## <a name="migrating-user-accounts-originally-enabled-in-lync-online-to-lync-on-premises"></a><span data-ttu-id="c87c2-108">Перенос учетных записей пользователей, изначально включенных в Lync Online, в локальную среду Lync</span><span class="sxs-lookup"><span data-stu-id="c87c2-108">Migrating User Accounts Originally Enabled in Lync Online to Lync On-Premises</span></span>

1.  <span data-ttu-id="c87c2-109">Сначала убедитесь, что ваша организация настроена для гибридной среды.</span><span class="sxs-lookup"><span data-stu-id="c87c2-109">First, make sure that your organization is configured for hybrid.</span></span>
    
      - <span data-ttu-id="c87c2-110">Установите средство синхронизации Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="c87c2-110">Install the Azure Active Directory Sync Tool.</span></span> <span data-ttu-id="c87c2-111">Дополнительные сведения см. в статье <https://social.technet.microsoft.com/wiki/contents/articles/19098.howto-install-the-windows-azure-active-directory-sync-tool.aspx>.</span><span class="sxs-lookup"><span data-stu-id="c87c2-111">For more information, see <https://social.technet.microsoft.com/wiki/contents/articles/19098.howto-install-the-windows-azure-active-directory-sync-tool.aspx>.</span></span>
    
      - <span data-ttu-id="c87c2-112">Чтобы разрешить пользователям использовать единый вход для Lync Online, установите службы федерации Active Directory <https://social.technet.microsoft.com/wiki/contents/articles/1011.active-directory-federation-services-ad-fs-overview.aspx> .</span><span class="sxs-lookup"><span data-stu-id="c87c2-112">To enable your users to use single sign-on for Lync Online, install Active Directory Federation Services <https://social.technet.microsoft.com/wiki/contents/articles/1011.active-directory-federation-services-ad-fs-overview.aspx>.</span></span>
    
      - <span data-ttu-id="c87c2-113">В локальном развертывании в командной консоли Lync Server введите следующие командлеты, чтобы создать поставщика услуг хостинга для Lync Online:</span><span class="sxs-lookup"><span data-stu-id="c87c2-113">On your on-premises deployment, in Lync Server Management Shell, type the following cmdlets to create the hosting provider for Lync Online:</span></span>
        
           ```PowerShell
           Set-CsAccessEdgeConfiguration -AllowOutsideUsers 1 -AllowFederatedUsers 1 -UseDnsSrvRouting -EnablePartnerDiscovery $true
           ```
        
           ```PowerShell
            New-CsHostingProvider -Identity LyncOnline -ProxyFqdn "sipfed.online.lync.com" -Enabled $true -EnabledSharedAddressSpace $true -HostsOCSUsers $true -VerificationLevel UseSourceVerification -IsLocal $false -AutodiscoverUrl https://webdir.online.lync.com/Autodiscover/AutodiscoverService.svc/root
           ```

2.  <span data-ttu-id="c87c2-114">Убедитесь, что на локальных пограничных серверах есть цепочка сертификатов, обеспечивающая подключение к Lync Online, как показано в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="c87c2-114">Confirm that, on your on-premises Edge Servers, you have the certificate chain that enables connection to Lync Online, as shown in the following table.</span></span> <span data-ttu-id="c87c2-115">Эту цепочку можно загрузить здесь: https://support.office.com/article/office-365-certificate-chains-0c03e6b3-e73f-4316-9e2b-bf4091ae96bb</span><span class="sxs-lookup"><span data-stu-id="c87c2-115">You can download this chain here: https://support.office.com/article/office-365-certificate-chains-0c03e6b3-e73f-4316-9e2b-bf4091ae96bb</span></span>


    <table>
    <colgroup>
    <col style="width: 50%" />
    <col style="width: 50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><span data-ttu-id="c87c2-116">Сертификат</span><span class="sxs-lookup"><span data-stu-id="c87c2-116">Certificate</span></span></th>
    <th><span data-ttu-id="c87c2-117">Хранилище сертификатов</span><span class="sxs-lookup"><span data-stu-id="c87c2-117">Certificate Store</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><span data-ttu-id="c87c2-118">Baltimore CyberTrust Root</span><span class="sxs-lookup"><span data-stu-id="c87c2-118">Baltimore CyberTrust Root</span></span></p></td>
    <td><p><span data-ttu-id="c87c2-119">Доверенный корневой ЦС</span><span class="sxs-lookup"><span data-stu-id="c87c2-119">Trusted Root CA</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="c87c2-120">Microsoft Internet Authority (новый сертификат ЦС)</span><span class="sxs-lookup"><span data-stu-id="c87c2-120">Microsoft Internet Authority (New CA certificate)</span></span></p></td>
    <td><p><span data-ttu-id="c87c2-121">Промежуточный ЦС</span><span class="sxs-lookup"><span data-stu-id="c87c2-121">Intermediate CA</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="c87c2-122">MSIT Machine auth CA2 (новый выпуск CA2)</span><span class="sxs-lookup"><span data-stu-id="c87c2-122">MSIT Machine Auth CA2 (New Issuing CA2)</span></span></p></td>
    <td><p><span data-ttu-id="c87c2-123">Промежуточный ЦС</span><span class="sxs-lookup"><span data-stu-id="c87c2-123">Intermediate CA</span></span></p></td>
    </tr>
    </tbody>
    </table>

3.  <span data-ttu-id="c87c2-124">В локальной службе Active Directory включите затронутые учетные записи пользователей для локальной среды Lync.</span><span class="sxs-lookup"><span data-stu-id="c87c2-124">In your on-premises Active Directory, enable the affected user accounts for Lync on-premises.</span></span> <span data-ttu-id="c87c2-125">Это можно сделать для отдельного пользователя, введя следующий командлет:</span><span class="sxs-lookup"><span data-stu-id="c87c2-125">You can do this for an individual user by typing the following cmdlet:</span></span>
    
        Enable-CsUser
        -Identity "username" 
        -SipAddress "sip: username@contoso.com"
        -HostingProviderProxyFqdn "sipfed.online.lync.com"
    
    <span data-ttu-id="c87c2-126">Или можно создать сценарий, считывающий имена пользователей из файла и предоставляющий их в качестве входных данных для командлета Enable-CsUser:</span><span class="sxs-lookup"><span data-stu-id="c87c2-126">Or you can create a script that reads user names from a file and provides them as input to the Enable-CsUser cmdlet:</span></span>
    
        Enable-CsUser
        -Identity $Identity 
        -SipAddress $SipAddress 
        -HostingProviderProxyFqdn "sipfed.online.lync.com"

4.  <span data-ttu-id="c87c2-127">Запустите DirSync, чтобы синхронизировать пользователей Lync Online с обновленными локальными пользователями Lync.</span><span class="sxs-lookup"><span data-stu-id="c87c2-127">Run DirSync to sync the Lync Online users with the updated Lync on-premises users.</span></span>

5.  <span data-ttu-id="c87c2-128">Обновите некоторые записи DNS, чтобы направить весь трафик SIP в локальную среду Lync:</span><span class="sxs-lookup"><span data-stu-id="c87c2-128">Update some DNS records to direct all SIP traffic to Lync on-premises:</span></span>
    
      - <span data-ttu-id="c87c2-129">Обновите запись **Lyncdiscover.contoso.com** A, УКАЗАВ полное доменное имя локального обратного прокси-сервера.</span><span class="sxs-lookup"><span data-stu-id="c87c2-129">Update the **lyncdiscover.contoso.com** A record to point to the FQDN of the on-premises reverse proxy server.</span></span>
    
      - <span data-ttu-id="c87c2-130">Обновление \*\*\* \_ SIP \*. \_ \*\*запись SRV TLS.contoso.com, которая разрешается в общедоступный IP-адрес или виртуальный IP-адрес службы пограничной службы доступа в локальной среде Lync.</span><span class="sxs-lookup"><span data-stu-id="c87c2-130">Update the \***\_sip\*.\_tls.contoso.com** SRV record to resolve to the public IP or VIP address of the Access Edge service of Lync on-premises.</span></span>
    
      - <span data-ttu-id="c87c2-131">Обновление \*\*\* \_ сипфедератионтлс \*. \_ \*\*запись SRV TCP.contoso.com, которая разрешается в общедоступный IP-адрес или виртуальный IP-адрес службы пограничной службы доступа в локальной среде Lync.</span><span class="sxs-lookup"><span data-stu-id="c87c2-131">Update the \***\_sipfederationtls\*.\_tcp.contoso.com** SRV record to resolve to the public IP or VIP address of the Access Edge service of Lync on-premises.</span></span>
    
      - <span data-ttu-id="c87c2-132">Если в организации используется разделение DNS (иногда называется "Split-мозговой DNS"), убедитесь, что пользователи, разрешающие имена через внутреннюю зону DNS, направляются в пул переднего плана.</span><span class="sxs-lookup"><span data-stu-id="c87c2-132">If your organization uses split DNS (sometimes called “split-brain DNS”), make sure that users resolving names through the internal DNS zone are directed to the Front End Pool.</span></span>

6.  <span data-ttu-id="c87c2-133">Введите `Get-CsUser` командлет, чтобы проверить некоторые свойства для перемещаемых пользователей.</span><span class="sxs-lookup"><span data-stu-id="c87c2-133">Type the `Get-CsUser` cmdlet to check some properties about the users you’ll be moving.</span></span> <span data-ttu-id="c87c2-134">Необходимо убедиться, что для параметра Хостингпровидерпроксифкдн задано значение, `"sipfed.online.lync.com"` а SIP-адреса настроены правильно.</span><span class="sxs-lookup"><span data-stu-id="c87c2-134">You want to make sure that the HostingProviderProxyFQDN is set to `"sipfed.online.lync.com"` and that the SIP addresses are set correctly.</span></span>

7.  <span data-ttu-id="c87c2-135">Перемещение пользователей Lync Online в локальную среду Lync.</span><span class="sxs-lookup"><span data-stu-id="c87c2-135">Move Lync Online users to Lync on-premises.</span></span>
    
    <span data-ttu-id="c87c2-136">Чтобы переместить одного пользователя, введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="c87c2-136">To move a single user, type this:</span></span>
    
       ```PowerShell
       $cred = Get-Credential
       ```
    
       ```PowerShell
       Move-CsUser -Identity <username>@contoso.com -Target "<fe-pool>.contoso.com" -Credential $cred -HostedMigrationOverrideURL <URL>
       ```
    
    <span data-ttu-id="c87c2-137">Можно переместить несколько пользователей с помощью командлета **Get-CsUSer** с параметром – Filter, чтобы выбрать пользователей с определенным свойством.</span><span class="sxs-lookup"><span data-stu-id="c87c2-137">You can move multiple users by using the **Get-CsUSer** cmdlet with the –Filter parameter to select the users with a specific property.</span></span> <span data-ttu-id="c87c2-138">Например, вы можете выбрать всех пользователей Lync Online, выполнив фильтрацию {Hosting Provider – EQ "sipfed.online.lync.om"}.</span><span class="sxs-lookup"><span data-stu-id="c87c2-138">For example, you could select all Lync Online users by filtering for {Hosting Provider –eq “sipfed.online.lync.om”}.</span></span> <span data-ttu-id="c87c2-139">Затем можно передать возвращенных пользователей в командлет **Move – CsUSer** , как показано ниже.</span><span class="sxs-lookup"><span data-stu-id="c87c2-139">You can then pipe the returned users to the **Move-CsUSer** cmdlet, as shown below.</span></span>
    
        Get-CsUser -Filter {Hosting Provider -eq "sipfed.online.lync.com"} | Move-CsUser -Target "<fe-pool>.contoso.com" -Credential $creds -HostedMigrationOverrideURL <URL>
    
    <span data-ttu-id="c87c2-140">Формат URL-адреса, заданный для параметра **хостедмигратионоверридеурл** , должен быть URL-адресом пула, где запущена служба переноса, в следующем формате: *https:// \<Pool FQDN\> /HostedMigration/hostedmigrationService.svc*.</span><span class="sxs-lookup"><span data-stu-id="c87c2-140">The format of the URL specified for the **HostedMigrationOverrideUrl** parameter must be the URL to the pool where the Hosted Migration service is running, in the following format: *Https://\<Pool FQDN\>/HostedMigration/hostedmigrationService.svc*.</span></span>
    
    <span data-ttu-id="c87c2-141">Можно определить URL-адрес размещенной службы миграции, просмотрев URL-адрес панели управления Lync Online для учетной записи организации Microsoft 365 или Office 365.</span><span class="sxs-lookup"><span data-stu-id="c87c2-141">You can determine the URL to the Hosted Migration Service by viewing the URL for the Lync Online Control Panel for your Microsoft 365 or Office 365 organization account.</span></span>
    
    <div>
    
    ## <a name="to-determine-the-hosted-migration-service-url-for-your-organizaton"></a><span data-ttu-id="c87c2-142">Определение URL-адреса размещенной службы миграции для организатон</span><span class="sxs-lookup"><span data-stu-id="c87c2-142">To determine the Hosted Migration Service URL for your organizaton</span></span>
    
    1.  <span data-ttu-id="c87c2-143">Войдите в организацию Microsoft 365 или Office 365 с правами администратора.</span><span class="sxs-lookup"><span data-stu-id="c87c2-143">Log in to your Microsoft 365 or Office 365 organization as an administrator.</span></span>
    
    2.  <span data-ttu-id="c87c2-144">Откройте **центр администрирования Lync**.</span><span class="sxs-lookup"><span data-stu-id="c87c2-144">Open the **Lync admin center**.</span></span>
    
    3.  <span data-ttu-id="c87c2-145">При отображении **центра администрирования Lync** выберите и скопируйте URL-адрес в адресную строку вплоть до **Lync.com**.</span><span class="sxs-lookup"><span data-stu-id="c87c2-145">With the **Lync admin center** displayed, select and copy the URL in the address bar up to **lync.com**.</span></span> <span data-ttu-id="c87c2-146">Пример URL-адреса выглядит примерно следующим образом:</span><span class="sxs-lookup"><span data-stu-id="c87c2-146">An example URL looks similar to the following:</span></span>
        
        `https://webdir0a.online.lync.com/lscp/?language=en-US&tenantID=`
    
    4.  <span data-ttu-id="c87c2-147">Замените **webdir** в URL-адресе на **"Администратор"**, что приводит к следующим действиям:</span><span class="sxs-lookup"><span data-stu-id="c87c2-147">Replace **webdir** in the URL with **admin**, resulting in the following:</span></span>
        
        `https://admin0a.online.lync.com`
    
    5.  <span data-ttu-id="c87c2-148">Добавьте указанную ниже строку в URL-адрес: **/HostedMigration/hostedmigrationservice.svc**.</span><span class="sxs-lookup"><span data-stu-id="c87c2-148">Append the following string to the URL: **/HostedMigration/hostedmigrationservice.svc**.</span></span>
        
        <span data-ttu-id="c87c2-149">Итоговый URL-адрес, который является значением **хостедмигратионоверридеурл**, должен выглядеть следующим образом:</span><span class="sxs-lookup"><span data-stu-id="c87c2-149">The resulting URL, which is the value of the **HostedMigrationOverrideUrl**, should look like the following:</span></span>
        
        `https://admin0a.online.lync.com/HostedMigration/hostedmigrationservice.svc`
    
    </div>
    
    <div class="">
    

    > [!NOTE]  
    > <span data-ttu-id="c87c2-150">Максимальный размер файлов журналов транзакций для базы данных rtcxds по умолчанию равен 16 ГБ.</span><span class="sxs-lookup"><span data-stu-id="c87c2-150">The default maximum size for transaction log files of the rtcxds database is 16 GB.</span></span> <span data-ttu-id="c87c2-151">Это может быть недостаточно, если вы перемещаете большое число пользователей одновременно, особенно если зеркальное отображение включено.</span><span class="sxs-lookup"><span data-stu-id="c87c2-151">This might not be big enough if you’re moving a large number of users at once, especially if you have mirroring enabled.</span></span> <span data-ttu-id="c87c2-152">Чтобы обойти эту проблему, вы можете увеличить размер файла или регулярно создавать резервные копии файлов журналов.</span><span class="sxs-lookup"><span data-stu-id="c87c2-152">To get around this you can increase the file size or back up the log files regularly.</span></span> <span data-ttu-id="c87c2-153">Для получения дополнительных сведений см <A class=uri href="https://support.microsoft.com/kb/2756725">https://support.microsoft.com/kb/2756725</A> .</span><span class="sxs-lookup"><span data-stu-id="c87c2-153">For more information, see <A class=uri href="https://support.microsoft.com/kb/2756725">https://support.microsoft.com/kb/2756725</A>.</span></span>

    
    </div>

8.  <span data-ttu-id="c87c2-154">Это действие не является обязательным.</span><span class="sxs-lookup"><span data-stu-id="c87c2-154">This is an optional step.</span></span> <span data-ttu-id="c87c2-155">Если вам требуется интеграция с Exchange 2013 Online, необходимо использовать дополнительного поставщика услуг хостинга.</span><span class="sxs-lookup"><span data-stu-id="c87c2-155">If you need to integrate with Exchange 2013 Online, you need to use an additional hosting provider.</span></span> <span data-ttu-id="c87c2-156">Для получения дополнительных сведений см [Настройка локальной интеграции Lync Server 2013 с Exchange Online](lync-server-2013-configuring-on-premises-lync-server-integration-with-exchange-online.md).</span><span class="sxs-lookup"><span data-stu-id="c87c2-156">For details, see [Configuring on-premises Lync Server 2013 integration with Exchange Online](lync-server-2013-configuring-on-premises-lync-server-integration-with-exchange-online.md).</span></span>

9.  <span data-ttu-id="c87c2-157">Теперь пользователи перемещаются.</span><span class="sxs-lookup"><span data-stu-id="c87c2-157">The users are now moved.</span></span> <span data-ttu-id="c87c2-158">Чтобы убедиться, что пользователь имеет правильные значения для атрибутов, показанных в следующей таблице, введите следующий командлет:</span><span class="sxs-lookup"><span data-stu-id="c87c2-158">To check that a user has correct values for the attributes shown in the following table, type this cmdlet:</span></span>
    
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
    <th><span data-ttu-id="c87c2-159">Атрибут Active Directory</span><span class="sxs-lookup"><span data-stu-id="c87c2-159">Active Directory attribute</span></span></th>
    <th><span data-ttu-id="c87c2-160">Имя атрибута</span><span class="sxs-lookup"><span data-stu-id="c87c2-160">Attribute name</span></span></th>
    <th><span data-ttu-id="c87c2-161">Правильное значение для пользователя Lync Online</span><span class="sxs-lookup"><span data-stu-id="c87c2-161">Correct value for Lync Online user</span></span></th>
    <th><span data-ttu-id="c87c2-162">Правильное значение для локальных пользователей Lync</span><span class="sxs-lookup"><span data-stu-id="c87c2-162">Correct value for Lync on–premises users</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><span data-ttu-id="c87c2-163">msRTCSIP — Деплойментлокатор</span><span class="sxs-lookup"><span data-stu-id="c87c2-163">msRTCSIP-DeploymentLocator</span></span></p></td>
    <td><p><span data-ttu-id="c87c2-164">хостингпровидер</span><span class="sxs-lookup"><span data-stu-id="c87c2-164">HostingProvider</span></span></p></td>
    <td><p><span data-ttu-id="c87c2-165">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="c87c2-165">sipfed.online.lync.com</span></span></p></td>
    <td><p><span data-ttu-id="c87c2-166">SRV</span><span class="sxs-lookup"><span data-stu-id="c87c2-166">SRV:</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="c87c2-167">msRTCSIP — PrimaryUserAddress</span><span class="sxs-lookup"><span data-stu-id="c87c2-167">msRTCSIP-PrimaryUserAddress</span></span></p></td>
    <td><p><span data-ttu-id="c87c2-168">SIPAddress</span><span class="sxs-lookup"><span data-stu-id="c87c2-168">SIPAddress</span></span></p></td>
    <td><p><span data-ttu-id="c87c2-169">sip:userName@contoso.com</span><span class="sxs-lookup"><span data-stu-id="c87c2-169">sip:userName@contoso.com</span></span></p></td>
    <td><p><span data-ttu-id="c87c2-170">sip:userName@contoso.com</span><span class="sxs-lookup"><span data-stu-id="c87c2-170">sip:userName@contoso.com</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="c87c2-171">msRTCSIP — UserEnabled</span><span class="sxs-lookup"><span data-stu-id="c87c2-171">msRTCSIP-UserEnabled</span></span></p></td>
    <td><p><span data-ttu-id="c87c2-172">Включено</span><span class="sxs-lookup"><span data-stu-id="c87c2-172">Enabled</span></span></p></td>
    <td><p><span data-ttu-id="c87c2-173">Да</span><span class="sxs-lookup"><span data-stu-id="c87c2-173">True</span></span></p></td>
    <td><p><span data-ttu-id="c87c2-174">Да</span><span class="sxs-lookup"><span data-stu-id="c87c2-174">True</span></span></p></td>
    </tr>
    </tbody>
    </table>


10. <span data-ttu-id="c87c2-175">Для каждого перемещенного пользователя потребуется выйти из Lync, а затем войти снова.</span><span class="sxs-lookup"><span data-stu-id="c87c2-175">Each user who has been moved will need to log out of Lync, then log back in.</span></span> <span data-ttu-id="c87c2-176">Когда они выполняют вход в систему, должны проверить свои списки контактов и при необходимости добавлять контакты.</span><span class="sxs-lookup"><span data-stu-id="c87c2-176">When they log in they should verify their contact lists, and add contacts if needed.</span></span>
    
    <span data-ttu-id="c87c2-177">Обратите внимание, что запланированные собрания не переносятся из Lync Online в локальную среду Lync.</span><span class="sxs-lookup"><span data-stu-id="c87c2-177">Note that scheduled meetings are not migrated from Lync Online to Lync on-premises.</span></span> <span data-ttu-id="c87c2-178">После перемещения пользователи должны будут перепланировать эти собрания.</span><span class="sxs-lookup"><span data-stu-id="c87c2-178">Users will need to reschedule these meetings after being moved.</span></span>
    
    <span data-ttu-id="c87c2-179">После обновления DNS-записей, когда все пользователи перенаправляются на локальную версию, атрибут Хостингпровидер указывает пользователю Lync либо использовать записи SRV, либо направить их интерактивному поставщику "sipfed.online.lync.com".</span><span class="sxs-lookup"><span data-stu-id="c87c2-179">After the DNS records are updated and all users are directed to On premise, the HostingProvider attribute directs the Lync user to either use SRV records or direct them to the Online provider “sipfed.online.lync.com.”</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

