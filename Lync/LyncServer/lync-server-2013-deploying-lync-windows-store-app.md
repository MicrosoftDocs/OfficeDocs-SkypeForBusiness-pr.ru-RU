---
title: 'Lync Server 2013: развертывание приложения Lync из Магазина Windows'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying Lync Windows Store app
ms:assetid: 9e00aaf4-15f9-4356-9ed7-5a58a2bfa043
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ822971(v=OCS.15)
ms:contentKeyID: 50117635
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 49fcea107a4613ca78661a21d492612f82d9775f
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757653"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploying-lync-windows-store-app-in-lync-server-2013"></a><span data-ttu-id="fc2c1-102">Развертывание приложения Lync из Магазина Windows в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fc2c1-102">Deploying Lync Windows Store app in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fc2c1-103">_**Тема последнего изменения:** 2013-12-03_</span><span class="sxs-lookup"><span data-stu-id="fc2c1-103">_**Topic Last Modified:** 2013-12-03_</span></span>

<span data-ttu-id="fc2c1-104">Прежде чем сделать приложение Lync из Магазина Windows доступным для пользователей, убедитесь, что развертывание соответствует [требованиям приложения Lync из Магазина Windows для Lync Server 2013](lync-server-2013-lync-windows-store-app-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fc2c1-104">Before making Lync Windows Store app available to users, make sure that your deployment meets the [Lync Windows Store app requirements for Lync Server 2013](lync-server-2013-lync-windows-store-app-requirements.md).</span></span> <span data-ttu-id="fc2c1-105">Дополнительные сведения о настройке Lync Server 2013 для поддержки приложения Lync из Магазина Windows можно найти в статье блогов для NextHop: "Автообнаружение Lync Server и приложение Lync из магазина [http://go.microsoft.com/fwlink/?LinkId=271966](http://go.microsoft.com/fwlink/?linkid=271966)Windows".</span><span class="sxs-lookup"><span data-stu-id="fc2c1-105">For details about configuring Lync Server 2013 to support Lync Windows Store app, see the NextHop Blog article, "Lync Server Autodiscover and the Lync Windows Store App," at [http://go.microsoft.com/fwlink/?LinkId=271966](http://go.microsoft.com/fwlink/?linkid=271966).</span></span> <span data-ttu-id="fc2c1-106">После правильной настройки серверной среды вы можете направлять пользователей для загрузки приложения Lync из Магазина Windows, выполнив поиск по слову "Lync".</span><span class="sxs-lookup"><span data-stu-id="fc2c1-106">After your server environment is configured correctly, you can direct users to download the Lync app from the Windows Store by searching for "Lync."</span></span>

<div>

## <a name="enabling-multi-factor-authentication-for-lync-windows-store-app"></a><span data-ttu-id="fc2c1-107">Включение многофакторной проверки подлинности для приложения Lync из Магазина Windows</span><span class="sxs-lookup"><span data-stu-id="fc2c1-107">Enabling Multi-Factor Authentication for Lync Windows Store app</span></span>

<span data-ttu-id="fc2c1-108">Накопительные обновления для Lync Server 2013: Июнь 2013 добавляет поддержку многофакторной проверки подлинности для клиентов приложений Lync из Магазина Windows.</span><span class="sxs-lookup"><span data-stu-id="fc2c1-108">Cumulative Updates for Lync Server 2013: June 2013 adds support for multi-factor authentication for Lync Windows Store app clients.</span></span> <span data-ttu-id="fc2c1-109">Помимо имени пользователя и пароля, для проверки подлинности внешних пользователей при входе в собрания Lync можно использовать дополнительные методы проверки подлинности, например смарт-карты или контакты.</span><span class="sxs-lookup"><span data-stu-id="fc2c1-109">In addition to user name and password, you can require additional authentication methods, such as smart cards or PINs, to authenticate external users when they sign in to Lync meetings.</span></span> <span data-ttu-id="fc2c1-110">Чтобы включить многофакторную проверку подлинности, вы можете развернуть сервер федерации служб федерации Active Directory (AD FS) и включить пассивную проверку подлинности в Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="fc2c1-110">To enable multi-factor authentication, you deploy Active Directory Federation Service (AD FS) federation server and enable passive authentication in Lync Server 2013.</span></span> <span data-ttu-id="fc2c1-111">После настройки AD FS внешние пользователи, пытающиеся присоединиться к собраниям Lync, будут представлены на веб-странице многофакторной проверки подлинности AD FS, которая содержит имя пользователя и пароль, а также любые дополнительные способы проверки подлинности, которые вы настроили. .</span><span class="sxs-lookup"><span data-stu-id="fc2c1-111">After AD FS is configured, external users who attempt to join Lync meetings are presented with an AD FS multi-factor authentication webpage that contains the user name and password challenge along with any additional authentication methods that you have configured.</span></span>

<div class=" ">


> [!IMPORTANT]  
> <span data-ttu-id="fc2c1-112">Ниже приведены важные моменты, которые следует учитывать при планировании настройки служб ADFS для многофакторной проверки подлинности в приложении Lync из Магазина Windows.</span><span class="sxs-lookup"><span data-stu-id="fc2c1-112">The following are important considerations if you plan to configure AD FS for multi-factor authentication for Lync Windows Store app:</span></span> 
> <UL>
> <LI>
> <P><span data-ttu-id="fc2c1-113">Lync Server 2013 с накопительными обновлениями для Lync Server 2013: требуется не менее июня 2013.</span><span class="sxs-lookup"><span data-stu-id="fc2c1-113">Lync Server 2013 with Cumulative Updates for Lync Server 2013: June 2013 is required at a minimum.</span></span> <span data-ttu-id="fc2c1-114">Пользователи Lync 2013 для настольных компьютеров не требуют накопительных обновлений для Lync Server 2013: Июнь 2013, поэтому может возникнуть ситуация, когда проверка подлинности в Lync 2013 клиенты смогут пройти проверку подлинности.</span><span class="sxs-lookup"><span data-stu-id="fc2c1-114">Lync 2013 desktop clients do not require Cumulative Updates for Lync Server 2013: June 2013, so it might appear that passive authentication is working because Lync 2013 clients are able to authenticate.</span></span> <span data-ttu-id="fc2c1-115">Тем не менее, процесс проверки подлинности для клиентов приложения Lync из Магазина Windows не будет выполнен, но уведомления или сообщение об ошибке выводиться не будут.</span><span class="sxs-lookup"><span data-stu-id="fc2c1-115">However, the authentication process for Lync Windows Store app clients will fail to complete and no notification or error message will display.</span></span></P>
> <LI>
> <P><span data-ttu-id="fc2c1-116">Сервер должен быть настроен таким образом, чтобы была доступна только для проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="fc2c1-116">The server must be configured so that passive authentication is the only authentication type offered.</span></span></P>
> <LI>
> <P><span data-ttu-id="fc2c1-117">Если вы используете подсистемы балансировки нагрузки для оборудования, включите сохраняемость файлов cookie для подсистем балансировки нагрузки, чтобы все запросы из клиента приложения Магазина Windows для Lync обрабатывались на одном и том же внешнем сервере.</span><span class="sxs-lookup"><span data-stu-id="fc2c1-117">If you use hardware load balancers, enable cookie persistence on the load balancers so that all requests from the Lync Windows Store app client are handled by the same Front End Server.</span></span></P>
> <LI>
> <P><span data-ttu-id="fc2c1-118">Если вы устанавливаете отношение доверия проверяющей стороны между сервером Lync Server и серверами AD FS, назначьте жизненный цикл, достаточно длинный, чтобы занимать максимальную длину собраний Lync.</span><span class="sxs-lookup"><span data-stu-id="fc2c1-118">When you establish a relying party trust between Lync Server and AD FS servers, assign a token life that is long enough to span the maximum length of your Lync meetings.</span></span> <span data-ttu-id="fc2c1-119">Как правило, 240 минут бывает достаточно.</span><span class="sxs-lookup"><span data-stu-id="fc2c1-119">Typically, a token life of 240 minutes is sufficient.</span></span></P></LI></UL>



</div>

<span data-ttu-id="fc2c1-120">**Настройка многофакторной проверки подлинности**</span><span class="sxs-lookup"><span data-stu-id="fc2c1-120">**To Configure Multi-Factor Authentication**</span></span>

1.  <span data-ttu-id="fc2c1-121">Установите роль сервера федерации служб федерации Active Directory.</span><span class="sxs-lookup"><span data-stu-id="fc2c1-121">Install an AD FS federation server role.</span></span> <span data-ttu-id="fc2c1-122">Подробные сведения можно найти в руководстве по развертыванию служб федерации Active Directory <http://go.microsoft.com/fwlink/p/?linkid=267511>2,0 по адресу.</span><span class="sxs-lookup"><span data-stu-id="fc2c1-122">For details, see the Active Directory Federation Services 2.0 Deployment Guide at <http://go.microsoft.com/fwlink/p/?linkid=267511>.</span></span>

2.  <span data-ttu-id="fc2c1-123">Создайте сертификаты для служб федерации Active Directory.</span><span class="sxs-lookup"><span data-stu-id="fc2c1-123">Create certificates for AD FS.</span></span> <span data-ttu-id="fc2c1-124">Для получения дополнительных сведений ознакомьтесь с разделом "сертификаты серверов федерации" плана и развертывания AD FS для использования с темой единого входа [http://go.microsoft.com/fwlink/p/?LinkId=285376](http://go.microsoft.com/fwlink/p/?linkid=285376).</span><span class="sxs-lookup"><span data-stu-id="fc2c1-124">For more information, see the "Federation server certificates" section of the Plan for and deploy AD FS for use with single sign-on topic at [http://go.microsoft.com/fwlink/p/?LinkId=285376](http://go.microsoft.com/fwlink/p/?linkid=285376).</span></span>

3.  <span data-ttu-id="fc2c1-125">В интерфейсе командной строки Windows PowerShell выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="fc2c1-125">From the Windows PowerShell command-line interface, run the following command:</span></span>
    ```powershell
    add-pssnapin Microsoft.Adfs.powershell
    ```
4.  <span data-ttu-id="fc2c1-126">Установите партнерство, выполнив следующую команду:</span><span class="sxs-lookup"><span data-stu-id="fc2c1-126">Establish a partnership by running the following command:</span></span>
    ```powershell
    Add-ADFSRelyingPartyTrust -Name ContosoApp -MetadataURL https://lyncpool.contoso.com/passiveauth/federationmetadata/2007-06/federationmetadata.xml
    ```
5.  <span data-ttu-id="fc2c1-127">Настройте следующие правила проверяющей стороны:</span><span class="sxs-lookup"><span data-stu-id="fc2c1-127">Set the following relying party rules:</span></span>
    
       ```powershell
        $IssuanceAuthorizationRules = '@RuleTemplate = "AllowAllAuthzRule" => issue(Type = "http://schemas.contoso.com/authorization/claims/permit", Value = "true");'$IssuanceTransformRules = '@RuleTemplate = "PassThroughClaims" @RuleName = "Sid" c:[Type == "http://schemas.contoso.com/ws/2008/06/identity/claims/primarysid"]=> issue(claim = c);'
       ```
    
       ```powershell
        Set-ADFSRelyingPartyTrust -TargetName ContosoApp -IssuanceAuthorizationRules $IssuanceAuthorizationRules -IssuanceTransformRules $IssuanceTransformRules
       ```
    
       ```powershell
        Set-CsWebServiceConfiguration -UseWsFedPassiveAuth $true -WsFedPassiveMetadataUri https://dc.contoso.com/federationmetadata/2007-06/federationmetadata.xml
       ```

</div>

<div>

## <a name="known-issues-that-can-prevent-sign-in"></a><span data-ttu-id="fc2c1-128">Известные проблемы, которые могут помешать входу</span><span class="sxs-lookup"><span data-stu-id="fc2c1-128">Known Issues that Can Prevent Sign-in</span></span>

<div>

## <a name="the-time-and-date-are-not-set-accurately-on-the-device-running-lync-windows-store-app"></a><span data-ttu-id="fc2c1-129">На устройстве с приложением Lync из магазина не задана точная дата и время.</span><span class="sxs-lookup"><span data-stu-id="fc2c1-129">The time and date are not set accurately on the device running Lync Windows Store app</span></span>

<span data-ttu-id="fc2c1-130">Время, установленное на устройстве, должно быть синхронизировано с параметром Time (время) на сервере.</span><span class="sxs-lookup"><span data-stu-id="fc2c1-130">The time setting on the device must be synchronized with the time setting on the server.</span></span> <span data-ttu-id="fc2c1-131">Это особенно важно для устройств, таких как Microsoft Surface и других устройств под управлением Windows RT, которые не подключены к домену.</span><span class="sxs-lookup"><span data-stu-id="fc2c1-131">This is particularly important for devices such as Microsoft Surface, and other devices running Windows RT that are not joined to a domain.</span></span> <span data-ttu-id="fc2c1-132">Чтобы автоматически настроить время на этих устройствах с сервера времени, выполните в командной строке с повышенными привилегиями на устройстве следующую команду:</span><span class="sxs-lookup"><span data-stu-id="fc2c1-132">To set the time on these devices automatically from a time server, run the following command from an elevated command prompt on the device:</span></span>
```console
w32tm /resync
```
</div>

<div>

## <a name="lync-windows-store-app-cannot-access-the-lync-server-or-services"></a><span data-ttu-id="fc2c1-133">Приложению Lync из Магазина Windows не удается получить доступ к серверу или службам Lync</span><span class="sxs-lookup"><span data-stu-id="fc2c1-133">Lync Windows Store app cannot access the Lync server or services</span></span>

<span data-ttu-id="fc2c1-134">Приложение Lync из Магазина Windows может не получить доступ к серверу Lync или службам через сетевые адаптеры, такие как 4G LTE USB-модемы, которые не регистрируются в Windows 8 как физические устройства.</span><span class="sxs-lookup"><span data-stu-id="fc2c1-134">Lync Windows Store app may not be able to access the Lync server or services through network adapters, such as 4G LTE USB modems, that do not register with Windows 8 as physical devices.</span></span> <span data-ttu-id="fc2c1-135">Приложение Lync из Магазина Windows может решить эту проблемы даже в том случае, если классические приложения и браузеры могут получить доступ к другим серверам и веб-сайтам.</span><span class="sxs-lookup"><span data-stu-id="fc2c1-135">Lync Windows Store app may have this issue even when the desktop apps and browsers are able to access other servers and web sites.</span></span>

</div>

<div>

## <a name="lync-windows-store-app-cannot-sign-in-with-lync-server-2010-and-office-communications-server-2007-r2-edge-server"></a><span data-ttu-id="fc2c1-136">Приложение Lync из Магазина Windows не может войти в составе Lync Server 2010 и Office Communications Server 2007 R2 Edge Server</span><span class="sxs-lookup"><span data-stu-id="fc2c1-136">Lync Windows Store app cannot sign in with Lync Server 2010 and Office Communications Server 2007 R2 Edge Server</span></span>

<span data-ttu-id="fc2c1-137">Если ваша топология состоит из Lync Server 2010 с пограничным сервером Office Communications Server 2007 R2, вам потребуется запустить обновленную версию построителя топологии, которая доступна в накопительном обновлении для Lync Server 2010: Июль 2013.</span><span class="sxs-lookup"><span data-stu-id="fc2c1-137">If your topology consists of Lync Server 2010 with Office Communications Server 2007 R2 Edge Server, you will need to run the updated version of Topology Builder available in the cumulative update for Lync Server 2010: July 2013.</span></span> <span data-ttu-id="fc2c1-138">Более ранние версии построителя топологии не создают необходимое сопоставление для Office Communications Server 2007 Edge Server, поэтому пользователи приложения Lync из Магазина Windows не могут войти в службу.</span><span class="sxs-lookup"><span data-stu-id="fc2c1-138">Earlier versions of Topology Builder do not create the required mapping to Office Communications Server 2007 Edge Server, so Lync Windows Store app clients are unable to sign in.</span></span> <span data-ttu-id="fc2c1-139">Необходимо выполнить указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="fc2c1-139">The following steps are required:</span></span>

1.  <span data-ttu-id="fc2c1-140">Установите накопительное обновление для Lync Server 2010: Июль 2013 для Lync Server 2010 Pools и режиссеров Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="fc2c1-140">Install the cumulative update for Lync Server 2010: July 2013 on Lync Server 2010 pools and Lync Server 2010 Directors.</span></span>

2.  <span data-ttu-id="fc2c1-141">Обновите конфигурацию автообнаружения Lync, чтобы указать, что внешняя точка входа SIP является адресом пограничного сервера, выполнив указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="fc2c1-141">Update the Lync AutoDiscover configuration to indicate that the external SIP entry point is the Edge server address by doing the following:</span></span>
    
    1.  <span data-ttu-id="fc2c1-142">Откройте командную консоль Lync Server.</span><span class="sxs-lookup"><span data-stu-id="fc2c1-142">Open Lync Server Management Shell.</span></span>
    
    2.  <span data-ttu-id="fc2c1-143">Выполните следующую команду.</span><span class="sxs-lookup"><span data-stu-id="fc2c1-143">Run the following command:</span></span>
        ```powershell
        Set-CsAutodiscoverConfiguration -ExternalSipClientAccessFqdn <FQDN of server used for external client access> -ExternalSipClientAccessPort 443
        ```
</div>

<div>

## <a name="lync-windows-store-app-cannot-sign-in-due-to-a-certificate-name-validation-failure"></a><span data-ttu-id="fc2c1-144">Не удается войти в приложение Lync из Магазина Windows из-за ошибки проверки имени сертификата</span><span class="sxs-lookup"><span data-stu-id="fc2c1-144">Lync Windows Store App cannot sign in due to a certificate name validation failure</span></span>

<span data-ttu-id="fc2c1-145">Для пользователей Office 365, не использующих самую последнюю версию приложения Lync из Магазина Windows, может возникнуть ошибка входа.</span><span class="sxs-lookup"><span data-stu-id="fc2c1-145">A sign-in issue can occur for Office 365 users who are not running the latest version of Lync Windows Store app.</span></span> <span data-ttu-id="fc2c1-146">Эта проблема обычно возникает при использовании нескольких доменов (например, если URI SIP — **userA@domainZ.com** , но пограничный сервер — **SIP.domainX.com**).</span><span class="sxs-lookup"><span data-stu-id="fc2c1-146">This issue generally occurs when using multiple domains (for example, when the SIP URI is **userA@domainZ.com** but the Edge Server is **sip.domainX.com**).</span></span> <span data-ttu-id="fc2c1-147">Чтобы устранить эту проблему, пользователи должны установить последнюю версию приложения Lync из Магазина Windows, в которой также требуется Windows 8,1.</span><span class="sxs-lookup"><span data-stu-id="fc2c1-147">To fix the issue, users should install the latest version of Lync Windows Store app, which also requires Windows 8.1.</span></span>

</div>

</div>

<div>

## <a name="use-lync-windows-store-app-logs-to-troubleshoot-issues"></a><span data-ttu-id="fc2c1-148">Устранение проблем с использованием журналов приложений Lync из Магазина Windows</span><span class="sxs-lookup"><span data-stu-id="fc2c1-148">Use Lync Windows Store app logs to troubleshoot issues</span></span>

<span data-ttu-id="fc2c1-149">Вы можете использовать журналы, созданные на устройстве, для устранения неполадок.</span><span class="sxs-lookup"><span data-stu-id="fc2c1-149">You can use the logs generated on the device to troubleshoot issues.</span></span> <span data-ttu-id="fc2c1-150">Журналы хранятся в следующей папке:</span><span class="sxs-lookup"><span data-stu-id="fc2c1-150">The logs are stored in the following folder:</span></span>

<span data-ttu-id="fc2c1-151">% LocalAppData%\\упаковывает\\Microsoft. линкмкс\_8wekyb3d8bbwe\\локалстате\\Tracing</span><span class="sxs-lookup"><span data-stu-id="fc2c1-151">%LocalAppData%\\Packages\\Microsoft.LyncMX\_8wekyb3d8bbwe\\LocalState\\Tracing</span></span>

<span data-ttu-id="fc2c1-152">Перед получением журналов от пользователя убедитесь в том, что ведение журнала включено, а затем посоветуйте ему сохранить журналы, чтобы все хранящиеся в памяти данные также сохранялись в файлах на жестком диске.</span><span class="sxs-lookup"><span data-stu-id="fc2c1-152">Before you get the logs from a user, make sure that logging is turned on, and then ask the user to save the logs so that all the information stored in memory is also saved to files on the hard drive.</span></span>

<span data-ttu-id="fc2c1-153">**Включение ведения журнала**</span><span class="sxs-lookup"><span data-stu-id="fc2c1-153">**To turn on logging**</span></span>

1.  <span data-ttu-id="fc2c1-154">Откройте приложение Lync из Магазина Windows на устройстве.</span><span class="sxs-lookup"><span data-stu-id="fc2c1-154">Open Lync Windows Store app on the device.</span></span>

2.  <span data-ttu-id="fc2c1-155">Проведите пальцем от правого края экрана.</span><span class="sxs-lookup"><span data-stu-id="fc2c1-155">Swipe from the right side of the screen.</span></span> <span data-ttu-id="fc2c1-156">Если вы используете мышь, наведите указатель мыши на правый верхний угол экрана, а затем наведите курсор на экран.</span><span class="sxs-lookup"><span data-stu-id="fc2c1-156">If you’re using a mouse, point to the upper-right corner of the screen and then move the mouse pointer down the screen.</span></span>

3.  <span data-ttu-id="fc2c1-157">Нажмите кнопку **Параметры**, выберите пункт **Параметры**, а затем установите для параметра **журналы диагностики** значение **вкл**.</span><span class="sxs-lookup"><span data-stu-id="fc2c1-157">Select **Settings**, select **Options**, and then set **Diagnostic Logs** to **On**.</span></span>

4.  <span data-ttu-id="fc2c1-158">Если **журналы диагностики** были ранее отключены, необходимо перезапустить Lync.</span><span class="sxs-lookup"><span data-stu-id="fc2c1-158">If **Diagnostic Logs** was off previously, you must restart Lync.</span></span> <span data-ttu-id="fc2c1-159">Чтобы перезапустить Lync, выполните одно из указанных ниже действий.</span><span class="sxs-lookup"><span data-stu-id="fc2c1-159">To restart Lync, do one of the following:</span></span>
    
      - <span data-ttu-id="fc2c1-160">Перезапустите устройство.</span><span class="sxs-lookup"><span data-stu-id="fc2c1-160">Restart the device.</span></span>
    
      - <span data-ttu-id="fc2c1-161">Завершите задачу Lync и запустите приложение еще раз.</span><span class="sxs-lookup"><span data-stu-id="fc2c1-161">End the Lync task and launch the app again.</span></span> <span data-ttu-id="fc2c1-162">Чтобы завершить задачу, откройте диспетчер задач Windows, выберите **Lync**и нажмите кнопку **завершить задачу**.</span><span class="sxs-lookup"><span data-stu-id="fc2c1-162">To end the task, open the Windows Task Manager, select **Lync**, and then tap **End task**.</span></span> <span data-ttu-id="fc2c1-163">Если Lync нет в списке, выберите **Дополнительные сведения** и найдите Lync в разделе **фоновые процессы**.</span><span class="sxs-lookup"><span data-stu-id="fc2c1-163">If Lync is not listed, tap **More details** and look for Lync under **Background processes**.</span></span>

<span data-ttu-id="fc2c1-164">**Сохранение журналов**</span><span class="sxs-lookup"><span data-stu-id="fc2c1-164">**To save the logs**</span></span>

1.  <span data-ttu-id="fc2c1-165">Откройте приложение Lync из Магазина Windows на устройстве.</span><span class="sxs-lookup"><span data-stu-id="fc2c1-165">Open Lync Windows Store app on the device.</span></span>

2.  <span data-ttu-id="fc2c1-166">Попробуйте войти в программу.</span><span class="sxs-lookup"><span data-stu-id="fc2c1-166">Try signing in.</span></span>

3.  <span data-ttu-id="fc2c1-167">Проведите пальцем от правого края экрана.</span><span class="sxs-lookup"><span data-stu-id="fc2c1-167">Swipe from the right side of the screen.</span></span> <span data-ttu-id="fc2c1-168">Если вы используете мышь, наведите указатель мыши на правый верхний угол экрана, а затем наведите курсор на экран.</span><span class="sxs-lookup"><span data-stu-id="fc2c1-168">If you’re using a mouse, point to the upper-right corner of the screen and then move the mouse pointer down the screen.</span></span>

4.  <span data-ttu-id="fc2c1-169">Нажмите кнопку **Параметры**, выберите пункт **о программе**, а затем — команду **сохранить журналы**.</span><span class="sxs-lookup"><span data-stu-id="fc2c1-169">Select **Settings**, select **About**, and then select **Save logs**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

