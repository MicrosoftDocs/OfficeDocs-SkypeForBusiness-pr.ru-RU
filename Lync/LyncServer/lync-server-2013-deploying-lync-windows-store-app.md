---
title: 'Lync Server 2013: развертывание приложения Lync Windows для магазина'
description: 'Lync Server 2013: развертывание приложения Lync Windows для магазина.'
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
ms.openlocfilehash: b9260d656079fb694a14aadf5049ca36241830c0
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48571715"
---
# <a name="deploying-lync-windows-store-app-in-lync-server-2013"></a><span data-ttu-id="eef21-103">Развертывание приложения Lync Windows для магазина в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="eef21-103">Deploying Lync Windows Store app in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="eef21-104">_**Последнее изменение темы:** 2013-12-03_</span><span class="sxs-lookup"><span data-stu-id="eef21-104">_**Topic Last Modified:** 2013-12-03_</span></span>

<span data-ttu-id="eef21-105">Прежде чем сделать приложение Lync Windows Store доступным для пользователей, убедитесь, что развертывание соответствует [требованиям к приложению для Магазина Windows Lync для Lync Server 2013](lync-server-2013-lync-windows-store-app-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="eef21-105">Before making Lync Windows Store app available to users, make sure that your deployment meets the [Lync Windows Store app requirements for Lync Server 2013](lync-server-2013-lync-windows-store-app-requirements.md).</span></span> <span data-ttu-id="eef21-106">Для получения дополнительных сведений о настройке Lync Server 2013 для поддержки приложения Lync Windows для магазина ознакомьтесь со статьей блогов "Автообнаружение Lync Server" и "Lync Windows Store" по адресу [https://go.microsoft.com/fwlink/?LinkId=271966](https://go.microsoft.com/fwlink/?linkid=271966) .</span><span class="sxs-lookup"><span data-stu-id="eef21-106">For details about configuring Lync Server 2013 to support Lync Windows Store app, see the NextHop Blog article, "Lync Server Autodiscover and the Lync Windows Store App," at [https://go.microsoft.com/fwlink/?LinkId=271966](https://go.microsoft.com/fwlink/?linkid=271966).</span></span> <span data-ttu-id="eef21-107">После правильной настройки серверной среды можно направить пользователей на загрузку приложения Lync из Магазина Windows, выполнив поиск по словам "Lync".</span><span class="sxs-lookup"><span data-stu-id="eef21-107">After your server environment is configured correctly, you can direct users to download the Lync app from the Windows Store by searching for "Lync."</span></span>

<div>

## <a name="enabling-multi-factor-authentication-for-lync-windows-store-app"></a><span data-ttu-id="eef21-108">Включение многофакторной проверки подлинности для приложения Lync Windows для магазина</span><span class="sxs-lookup"><span data-stu-id="eef21-108">Enabling Multi-Factor Authentication for Lync Windows Store app</span></span>

<span data-ttu-id="eef21-109">Накопительные пакеты обновления для Lync Server 2013: Июнь 2013 Добавление поддержки многофакторной проверки подлинности для клиентов приложений Магазина Windows для Lync.</span><span class="sxs-lookup"><span data-stu-id="eef21-109">Cumulative Updates for Lync Server 2013: June 2013 adds support for multi-factor authentication for Lync Windows Store app clients.</span></span> <span data-ttu-id="eef21-110">Помимо имени пользователя и пароля, для проверки подлинности внешних пользователей при входе в собрания Lync могут потребоваться дополнительные методы проверки подлинности, такие как смарт-карты или ПИН-коды.</span><span class="sxs-lookup"><span data-stu-id="eef21-110">In addition to user name and password, you can require additional authentication methods, such as smart cards or PINs, to authenticate external users when they sign in to Lync meetings.</span></span> <span data-ttu-id="eef21-111">Чтобы включить многофакторную проверку подлинности, необходимо развернуть сервер федерации службы федерации Active Directory (AD FS) и включить пассивную проверку подлинности в Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="eef21-111">To enable multi-factor authentication, you deploy Active Directory Federation Service (AD FS) federation server and enable passive authentication in Lync Server 2013.</span></span> <span data-ttu-id="eef21-112">После настройки AD FS внешние пользователи, пытающиеся присоединиться к собраниям Lync, отображаются с помощью веб-страницы многофакторной проверки подлинности AD FS, которая содержит имя пользователя и пароль, а также дополнительные методы проверки подлинности, которые вы настроили.</span><span class="sxs-lookup"><span data-stu-id="eef21-112">After AD FS is configured, external users who attempt to join Lync meetings are presented with an AD FS multi-factor authentication webpage that contains the user name and password challenge along with any additional authentication methods that you have configured.</span></span>

<div class=" ">


> [!IMPORTANT]  
> <span data-ttu-id="eef21-113">Ниже приведены важные рекомендации по настройке служб федерации Active Directory для многофакторной проверки подлинности для приложения Lync Windows для магазина:</span><span class="sxs-lookup"><span data-stu-id="eef21-113">The following are important considerations if you plan to configure AD FS for multi-factor authentication for Lync Windows Store app:</span></span> 
> <UL>
> <LI>
> <P><span data-ttu-id="eef21-114">Lync Server 2013 с накопительными пакетами обновления для Lync Server 2013: Июнь 2013 — обязательно по крайней мере.</span><span class="sxs-lookup"><span data-stu-id="eef21-114">Lync Server 2013 with Cumulative Updates for Lync Server 2013: June 2013 is required at a minimum.</span></span> <span data-ttu-id="eef21-115">Для настольных клиентов Lync 2013 не требуется накопительный пакет обновления для Lync Server 2013: Июнь 2013, поэтому может показаться, что пассивная проверка подлинности работает, так как клиенты Lync 2013 могут пройти проверку подлинности.</span><span class="sxs-lookup"><span data-stu-id="eef21-115">Lync 2013 desktop clients do not require Cumulative Updates for Lync Server 2013: June 2013, so it might appear that passive authentication is working because Lync 2013 clients are able to authenticate.</span></span> <span data-ttu-id="eef21-116">Однако процесс проверки подлинности для клиентов приложений Магазина Windows Lync не будет выполнен, и уведомления или сообщение об ошибке отображаться не будут.</span><span class="sxs-lookup"><span data-stu-id="eef21-116">However, the authentication process for Lync Windows Store app clients will fail to complete and no notification or error message will display.</span></span></P>
> <LI>
> <P><span data-ttu-id="eef21-117">Сервер должен быть настроен таким образом, чтобы пассивная проверка подлинности — единственный предлагаемый тип проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="eef21-117">The server must be configured so that passive authentication is the only authentication type offered.</span></span></P>
> <LI>
> <P><span data-ttu-id="eef21-118">Если вы используете аппаратные средства балансировки нагрузки, включите сохранение файлов cookie в подсистемах балансировки нагрузки, чтобы все запросы из клиента приложения Магазина Windows Lync обрабатывались одним сервером переднего плана.</span><span class="sxs-lookup"><span data-stu-id="eef21-118">If you use hardware load balancers, enable cookie persistence on the load balancers so that all requests from the Lync Windows Store app client are handled by the same Front End Server.</span></span></P>
> <LI>
> <P><span data-ttu-id="eef21-119">При установке отношения доверия с проверяющей стороной между Lync Server и серверами AD FS назначьте срок действия маркера, достаточного для достижения максимальной длины собраний Lync.</span><span class="sxs-lookup"><span data-stu-id="eef21-119">When you establish a relying party trust between Lync Server and AD FS servers, assign a token life that is long enough to span the maximum length of your Lync meetings.</span></span> <span data-ttu-id="eef21-120">Как правило, 240 минут бывает достаточно.</span><span class="sxs-lookup"><span data-stu-id="eef21-120">Typically, a token life of 240 minutes is sufficient.</span></span></P></LI></UL>



</div>

<span data-ttu-id="eef21-121">**Настройка многофакторной проверки подлинности**</span><span class="sxs-lookup"><span data-stu-id="eef21-121">**To Configure Multi-Factor Authentication**</span></span>

1.  <span data-ttu-id="eef21-122">Установите роль сервера федерации службы федерации Active Directory.</span><span class="sxs-lookup"><span data-stu-id="eef21-122">Install an AD FS federation server role.</span></span> <span data-ttu-id="eef21-123">Подробные сведения можно найти в руководстве по развертыванию служб федерации Active Directory 2,0 по адресу <https://go.microsoft.com/fwlink/p/?linkid=267511> .</span><span class="sxs-lookup"><span data-stu-id="eef21-123">For details, see the Active Directory Federation Services 2.0 Deployment Guide at <https://go.microsoft.com/fwlink/p/?linkid=267511>.</span></span>

2.  <span data-ttu-id="eef21-124">Создайте сертификаты для AD FS.</span><span class="sxs-lookup"><span data-stu-id="eef21-124">Create certificates for AD FS.</span></span> <span data-ttu-id="eef21-125">Для получения дополнительных сведений обратитесь к разделу "сертификаты сервера федерации" плана for Active Directory для использования с одним входом в разделе "планирование и развертывание AD FS" [https://go.microsoft.com/fwlink/p/?LinkId=285376](https://go.microsoft.com/fwlink/p/?linkid=285376) .</span><span class="sxs-lookup"><span data-stu-id="eef21-125">For more information, see the "Federation server certificates" section of the Plan for and deploy AD FS for use with single sign-on topic at [https://go.microsoft.com/fwlink/p/?LinkId=285376](https://go.microsoft.com/fwlink/p/?linkid=285376).</span></span>

3.  <span data-ttu-id="eef21-126">В интерфейсе командной строки Windows PowerShell выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="eef21-126">From the Windows PowerShell command-line interface, run the following command:</span></span>
    ```powershell
    add-pssnapin Microsoft.Adfs.powershell
    ```
4.  <span data-ttu-id="eef21-127">Установите отношение доверия, выполнив следующую команду.</span><span class="sxs-lookup"><span data-stu-id="eef21-127">Establish a partnership by running the following command:</span></span>
    ```powershell
    Add-ADFSRelyingPartyTrust -Name ContosoApp -MetadataURL https://lyncpool.contoso.com/passiveauth/federationmetadata/2007-06/federationmetadata.xml
    ```
5.  <span data-ttu-id="eef21-128">Настройте правила проверяющей стороны.</span><span class="sxs-lookup"><span data-stu-id="eef21-128">Set the following relying party rules:</span></span>
    
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

## <a name="known-issues-that-can-prevent-sign-in"></a><span data-ttu-id="eef21-129">Известные проблемы, которые могут препятствовать входу</span><span class="sxs-lookup"><span data-stu-id="eef21-129">Known Issues that Can Prevent Sign-in</span></span>

<div>

## <a name="the-time-and-date-are-not-set-accurately-on-the-device-running-lync-windows-store-app"></a><span data-ttu-id="eef21-130">Дата и время не заданы точно на устройстве, на котором работает приложение Магазина Windows в Lync</span><span class="sxs-lookup"><span data-stu-id="eef21-130">The time and date are not set accurately on the device running Lync Windows Store app</span></span>

<span data-ttu-id="eef21-131">Параметр времени на устройстве должен быть синхронизирован с параметром Time на сервере.</span><span class="sxs-lookup"><span data-stu-id="eef21-131">The time setting on the device must be synchronized with the time setting on the server.</span></span> <span data-ttu-id="eef21-132">Это особенно важно для таких устройств, как Microsoft Surface, и других устройств под управлением Windows RT, которые не присоединены к домену.</span><span class="sxs-lookup"><span data-stu-id="eef21-132">This is particularly important for devices such as Microsoft Surface, and other devices running Windows RT that are not joined to a domain.</span></span> <span data-ttu-id="eef21-133">Чтобы автоматически настроить время для этих устройств с сервера времени, выполните следующую команду в командной строке с повышенными привилегиями на устройстве:</span><span class="sxs-lookup"><span data-stu-id="eef21-133">To set the time on these devices automatically from a time server, run the following command from an elevated command prompt on the device:</span></span>
```console
w32tm /resync
```
</div>

<div>

## <a name="lync-windows-store-app-cannot-access-the-lync-server-or-services"></a><span data-ttu-id="eef21-134">Приложение Lync Windows Store не может получить доступ к серверу или службам Lync</span><span class="sxs-lookup"><span data-stu-id="eef21-134">Lync Windows Store app cannot access the Lync server or services</span></span>

<span data-ttu-id="eef21-135">Приложение Lync Windows Store может не иметь доступа к Lync Server или службам с помощью сетевых адаптеров, таких как USB-модемы 4G LTE, которые не регистрируются в Windows 8 как физические устройства.</span><span class="sxs-lookup"><span data-stu-id="eef21-135">Lync Windows Store app may not be able to access the Lync server or services through network adapters, such as 4G LTE USB modems, that do not register with Windows 8 as physical devices.</span></span> <span data-ttu-id="eef21-136">Приложение Lync Windows Store может столкнуться с этой ошибкой, даже если классические приложения и браузеры могут получать доступ к другим серверам и веб-сайтам.</span><span class="sxs-lookup"><span data-stu-id="eef21-136">Lync Windows Store app may have this issue even when the desktop apps and browsers are able to access other servers and web sites.</span></span>

</div>

<div>

## <a name="lync-windows-store-app-cannot-sign-in-with-lync-server-2010-and-office-communications-server-2007-r2-edge-server"></a><span data-ttu-id="eef21-137">Приложение Lync Windows Store не может войти в систему с помощью Lync Server 2010 и Office Communications Server 2007 R2 Edge Server</span><span class="sxs-lookup"><span data-stu-id="eef21-137">Lync Windows Store app cannot sign in with Lync Server 2010 and Office Communications Server 2007 R2 Edge Server</span></span>

<span data-ttu-id="eef21-138">Если ваша топология состоит из Lync Server 2010 с пограничным сервером Office Communications Server 2007 R2, вам потребуется запустить обновленную версию построителя топологий, которая доступна в накопительном пакете обновления для Lync Server 2010: Июль 2013.</span><span class="sxs-lookup"><span data-stu-id="eef21-138">If your topology consists of Lync Server 2010 with Office Communications Server 2007 R2 Edge Server, you will need to run the updated version of Topology Builder available in the cumulative update for Lync Server 2010: July 2013.</span></span> <span data-ttu-id="eef21-139">Более ранние версии построителя топологий не создают необходимое сопоставление с пограничным сервером Office Communications Server 2007, поэтому не удается войти в Lync для клиентов приложений Магазина Windows.</span><span class="sxs-lookup"><span data-stu-id="eef21-139">Earlier versions of Topology Builder do not create the required mapping to Office Communications Server 2007 Edge Server, so Lync Windows Store app clients are unable to sign in.</span></span> <span data-ttu-id="eef21-140">Необходимо выполнить следующие действия:</span><span class="sxs-lookup"><span data-stu-id="eef21-140">The following steps are required:</span></span>

1.  <span data-ttu-id="eef21-141">Установите накопительный пакет обновления для Lync Server 2010:2013 июля в пулы Lync Server 2010 и Lync Server 2010 Директораs.</span><span class="sxs-lookup"><span data-stu-id="eef21-141">Install the cumulative update for Lync Server 2010: July 2013 on Lync Server 2010 pools and Lync Server 2010 Directors.</span></span>

2.  <span data-ttu-id="eef21-142">Обновите конфигурацию автообнаружения Lync, чтобы указать, что внешняя точка входа SIP является адресом пограничного сервера, выполнив следующие действия:</span><span class="sxs-lookup"><span data-stu-id="eef21-142">Update the Lync AutoDiscover configuration to indicate that the external SIP entry point is the Edge server address by doing the following:</span></span>
    
    1.  <span data-ttu-id="eef21-143">Откройте консоль управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="eef21-143">Open Lync Server Management Shell.</span></span>
    
    2.  <span data-ttu-id="eef21-144">Выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="eef21-144">Run the following command:</span></span>
        ```powershell
        Set-CsAutodiscoverConfiguration -ExternalSipClientAccessFqdn <FQDN of server used for external client access> -ExternalSipClientAccessPort 443
        ```
</div>

<div>

## <a name="lync-windows-store-app-cannot-sign-in-due-to-a-certificate-name-validation-failure"></a><span data-ttu-id="eef21-145">Приложение Lync Windows Store не может выполнить вход из-за ошибки проверки имени сертификата</span><span class="sxs-lookup"><span data-stu-id="eef21-145">Lync Windows Store App cannot sign in due to a certificate name validation failure</span></span>

<span data-ttu-id="eef21-146">Ошибка входа в систему для Microsoft 365 или Office 365 пользователи, которые не работают с последней версией Lync Windows App Store.</span><span class="sxs-lookup"><span data-stu-id="eef21-146">A sign-in issue can occur for Microsoft 365 or Office 365 users who are not running the latest version of Lync Windows Store app.</span></span> <span data-ttu-id="eef21-147">Эта проблема обычно возникает при использовании нескольких доменов (например, когда URI SIP — **userA@domainZ.com** , но пограничный сервер — **SIP.domainX.com**).</span><span class="sxs-lookup"><span data-stu-id="eef21-147">This issue generally occurs when using multiple domains (for example, when the SIP URI is **userA@domainZ.com** but the Edge Server is **sip.domainX.com**).</span></span> <span data-ttu-id="eef21-148">Чтобы устранить эту проблему, пользователи должны установить последнюю версию приложения Lync Windows для магазина, в которой также требуется Windows 8,1.</span><span class="sxs-lookup"><span data-stu-id="eef21-148">To fix the issue, users should install the latest version of Lync Windows Store app, which also requires Windows 8.1.</span></span>

</div>

</div>

<div>

## <a name="use-lync-windows-store-app-logs-to-troubleshoot-issues"></a><span data-ttu-id="eef21-149">Устранение неполадок с помощью журналов приложений для Магазина Windows в Lync</span><span class="sxs-lookup"><span data-stu-id="eef21-149">Use Lync Windows Store app logs to troubleshoot issues</span></span>

<span data-ttu-id="eef21-150">Чтобы устранить неполадки, можно использовать журналы, созданные на устройстве.</span><span class="sxs-lookup"><span data-stu-id="eef21-150">You can use the logs generated on the device to troubleshoot issues.</span></span> <span data-ttu-id="eef21-151">Журналы хранятся в следующей папке:</span><span class="sxs-lookup"><span data-stu-id="eef21-151">The logs are stored in the following folder:</span></span>

<span data-ttu-id="eef21-152">% Локалаппдата% \\ пакетов \\ , трассировка Microsoft. линкмкс \_ 8wekyb3d8bbwe \\ локалстате \\</span><span class="sxs-lookup"><span data-stu-id="eef21-152">%LocalAppData%\\Packages\\Microsoft.LyncMX\_8wekyb3d8bbwe\\LocalState\\Tracing</span></span>

<span data-ttu-id="eef21-153">Перед получением журналов от пользователя убедитесь, что ведение журнала включено, а затем попросите пользователя сохранить журналы, чтобы вся информация, хранящаяся в памяти, сохранялась в файлах на жестком диске.</span><span class="sxs-lookup"><span data-stu-id="eef21-153">Before you get the logs from a user, make sure that logging is turned on, and then ask the user to save the logs so that all the information stored in memory is also saved to files on the hard drive.</span></span>

<span data-ttu-id="eef21-154">**Включение ведения журнала**</span><span class="sxs-lookup"><span data-stu-id="eef21-154">**To turn on logging**</span></span>

1.  <span data-ttu-id="eef21-155">Откройте на устройстве приложение Lync Windows Store.</span><span class="sxs-lookup"><span data-stu-id="eef21-155">Open Lync Windows Store app on the device.</span></span>

2.  <span data-ttu-id="eef21-156">Проведите пальцем с правой части экрана.</span><span class="sxs-lookup"><span data-stu-id="eef21-156">Swipe from the right side of the screen.</span></span> <span data-ttu-id="eef21-157">Если вы используете мышь, наведите указатель мыши на правый верхний угол экрана, а затем наведите указатель мыши на экран.</span><span class="sxs-lookup"><span data-stu-id="eef21-157">If you’re using a mouse, point to the upper-right corner of the screen and then move the mouse pointer down the screen.</span></span>

3.  <span data-ttu-id="eef21-158">Выберите **Параметры**, выберите **Параметры**, а затем настройте **журналы диагностики** в **On**.</span><span class="sxs-lookup"><span data-stu-id="eef21-158">Select **Settings**, select **Options**, and then set **Diagnostic Logs** to **On**.</span></span>

4.  <span data-ttu-id="eef21-159">Если **журналы диагностики** были ранее отключены, необходимо перезапустить Lync.</span><span class="sxs-lookup"><span data-stu-id="eef21-159">If **Diagnostic Logs** was off previously, you must restart Lync.</span></span> <span data-ttu-id="eef21-160">Чтобы перезапустить Lync, выполните одно из следующих действий.</span><span class="sxs-lookup"><span data-stu-id="eef21-160">To restart Lync, do one of the following:</span></span>
    
      - <span data-ttu-id="eef21-161">Перезапустите устройство.</span><span class="sxs-lookup"><span data-stu-id="eef21-161">Restart the device.</span></span>
    
      - <span data-ttu-id="eef21-162">Завершите задачу Lync и снова запустите приложение.</span><span class="sxs-lookup"><span data-stu-id="eef21-162">End the Lync task and launch the app again.</span></span> <span data-ttu-id="eef21-163">Чтобы завершить задачу, откройте диспетчер задач Windows, выберите **Lync**, а затем нажмите кнопку **завершить задачу**.</span><span class="sxs-lookup"><span data-stu-id="eef21-163">To end the task, open the Windows Task Manager, select **Lync**, and then tap **End task**.</span></span> <span data-ttu-id="eef21-164">Если Lync отсутствует в списке, коснитесь пункта **Дополнительные сведения** и найдите Lync в разделе **фоновые процессы**.</span><span class="sxs-lookup"><span data-stu-id="eef21-164">If Lync is not listed, tap **More details** and look for Lync under **Background processes**.</span></span>

<span data-ttu-id="eef21-165">**Сохранение журналов**</span><span class="sxs-lookup"><span data-stu-id="eef21-165">**To save the logs**</span></span>

1.  <span data-ttu-id="eef21-166">Откройте на устройстве приложение Lync Windows Store.</span><span class="sxs-lookup"><span data-stu-id="eef21-166">Open Lync Windows Store app on the device.</span></span>

2.  <span data-ttu-id="eef21-167">Попробуйте войти.</span><span class="sxs-lookup"><span data-stu-id="eef21-167">Try signing in.</span></span>

3.  <span data-ttu-id="eef21-168">Проведите пальцем с правой части экрана.</span><span class="sxs-lookup"><span data-stu-id="eef21-168">Swipe from the right side of the screen.</span></span> <span data-ttu-id="eef21-169">Если вы используете мышь, наведите указатель мыши на правый верхний угол экрана, а затем наведите указатель мыши на экран.</span><span class="sxs-lookup"><span data-stu-id="eef21-169">If you’re using a mouse, point to the upper-right corner of the screen and then move the mouse pointer down the screen.</span></span>

4.  <span data-ttu-id="eef21-170">Выберите **Параметры**, выберите пункт **о программе**и нажмите кнопку **сохранить журналы**.</span><span class="sxs-lookup"><span data-stu-id="eef21-170">Select **Settings**, select **About**, and then select **Save logs**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

