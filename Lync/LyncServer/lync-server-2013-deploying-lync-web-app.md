---
title: 'Lync Server 2013: развертывание Lync Web App'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying Lync Web App
ms:assetid: b6301e98-051c-4e4b-8e10-ec922a8f508a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205190(v=OCS.15)
ms:contentKeyID: 48185189
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6b7415be2210e6c791434ced8af8f309b49603e8
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757663"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploying-lync-web-app-in-lync-server-2013"></a><span data-ttu-id="62333-102">Развертывание Lync Web App в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="62333-102">Deploying Lync Web App in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="62333-103">_**Тема последнего изменения:** 2013-07-18_</span><span class="sxs-lookup"><span data-stu-id="62333-103">_**Topic Last Modified:** 2013-07-18_</span></span>

<span data-ttu-id="62333-104">Lync Web App — это веб-клиент служб IIS, который устанавливается вместе с Lync Server 2013 и включен по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="62333-104">Lync Web App is an Internet Information Services (IIS) web client that installs with Lync Server 2013 and is enabled by default.</span></span> <span data-ttu-id="62333-105">Чтобы включить Lync Web App на сервере или развернуть веб-клиент для пользователей, никаких дополнительных действий не требуется.</span><span class="sxs-lookup"><span data-stu-id="62333-105">No additional steps are necessary to either enable Lync Web App on the server or deploy the web client to users.</span></span> <span data-ttu-id="62333-106">Каждый раз, когда пользователь щелкает URL-адрес собрания, но на нем не установлен клиент Lync 2013, пользователю предоставляется возможность присоединиться к собранию с помощью последней версии Lync Web App.</span><span class="sxs-lookup"><span data-stu-id="62333-106">Whenever a user clicks a meeting URL but does not have the Lync 2013 client installed, the user is presented with the option to join the meeting by using the latest version of Lync Web App.</span></span>

<span data-ttu-id="62333-107">Для использования функций голосового и видеозвонков в Lync Web App требуется элемент управления Microsoft ActiveX.</span><span class="sxs-lookup"><span data-stu-id="62333-107">The voice, video, and sharing features in Lync Web App require a Microsoft ActiveX control.</span></span> <span data-ttu-id="62333-108">Вы можете установить элемент ActiveX заранее или разрешить пользователям устанавливать его при появлении соответствующего запроса, что происходит при первом использовании Lync Web App или при первом доступе к функции, для которой требуется элемент ActiveX.</span><span class="sxs-lookup"><span data-stu-id="62333-108">You can either install the ActiveX control in advance or allow users to install it when prompted, which happens the first time they use Lync Web App or the first time they access a feature that requires the ActiveX control.</span></span>

<div class=" ">


> [!NOTE]  
> <span data-ttu-id="62333-109">В Lync Server 2013 развертывание пограничного сервера — обратный прокси-сервер HTTPS в демилитаризованной зоне требуется для доступа клиентов Lync Web App.</span><span class="sxs-lookup"><span data-stu-id="62333-109">In Lync Server 2013 Edge Server deployments, an HTTPS reverse proxy in the perimeter network is required for Lync Web App client access.</span></span> <span data-ttu-id="62333-110">Помимо этого, необходимо опубликовать простые URL-адреса.</span><span class="sxs-lookup"><span data-stu-id="62333-110">You must also publish simple URLs.</span></span> <span data-ttu-id="62333-111">Подробнее: <A href="lync-server-2013-setting-up-reverse-proxy-servers.md">Настройка обратного прокси-серверов для Lync server 2013</A> и <A href="lync-server-2013-planning-for-simple-urls.md">планирование простых URL-адресов в Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="62333-111">For details, see <A href="lync-server-2013-setting-up-reverse-proxy-servers.md">Setting up reverse proxy servers for Lync Server 2013</A> and <A href="lync-server-2013-planning-for-simple-urls.md">Planning for simple URLs in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="enabling-multi-factor-authentication-for-lync-web-app"></a><span data-ttu-id="62333-112">Включение многофакторной проверки подлинности для Lync Web App</span><span class="sxs-lookup"><span data-stu-id="62333-112">Enabling Multi-Factor Authentication for Lync Web App</span></span>

<span data-ttu-id="62333-113">В версии Lync Server 2013 для Lync Web App поддерживается многофакторная проверка подлинности.</span><span class="sxs-lookup"><span data-stu-id="62333-113">The Lync Server 2013 version of Lync Web App supports multi-factor authentication.</span></span> <span data-ttu-id="62333-114">Помимо имени пользователя и пароля, для проверки подлинности пользователей, присоединяющихся к собраниям Lync, вы можете потребовать дополнительные методы проверки подлинности, например смарт-карты или контакты.</span><span class="sxs-lookup"><span data-stu-id="62333-114">In addition to user name and password, you can require additional authentication methods, such as smart cards or PINs, to authenticate users who are joining from external networks when they sign in to Lync meetings.</span></span> <span data-ttu-id="62333-115">Вы можете включить многофакторную проверку подлинности, развернув сервер федерации служб федерации Active Directory (AD FS) и включив пассивную проверку подлинности в Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="62333-115">You can enable multi-factor authentication by deploying Active Directory Federation Service (AD FS) federation server and enabling passive authentication in Lync Server 2013.</span></span> <span data-ttu-id="62333-116">После настройки AD FS внешние пользователи, пытающиеся присоединиться к собраниям Lync, будут представлены на веб-странице многофакторной проверки подлинности AD FS, которая содержит имя пользователя и пароль, а также любые дополнительные способы проверки подлинности, которые вы настроили. .</span><span class="sxs-lookup"><span data-stu-id="62333-116">After AD FS is configured, external users who attempt to join Lync meetings are presented with an AD FS multi-factor authentication webpage that contains the user name and password challenge along with any additional authentication methods that you have configured.</span></span>

<div class=" ">


> [!IMPORTANT]  
> <span data-ttu-id="62333-117">Если вы планируете настроить службу федерации Active Directory для многофакторной проверки подлинности, учтите следующие рекомендации.</span><span class="sxs-lookup"><span data-stu-id="62333-117">The following are important considerations if you plan to configure AD FS for multi-factor authentication:</span></span> 
> <UL>
> <LI>
> <P><span data-ttu-id="62333-p105">Многофакторная проверка подлинности службы федерации Active Directory действует в том случае, если как участник, так и организатор собрания относятся к одной организации (в том числе с федерацией AD FS). Многофакторная проверка подлинности службы федерации Active Directory не действует для федеративных пользователей Lync, так как веб-инфраструктура сервера Lync не поддерживает такую возможность в настоящий момент.</span><span class="sxs-lookup"><span data-stu-id="62333-p105">Multi-factor ADFS authentication works if the meeting participant and organizer are both in the same organization or are both from an AD FS federated organization. Multi-factor ADFS authentication does not work for Lync federated users because the Lync server web infrastructure does not currently support it.</span></span></P>
> <LI>
> <P><span data-ttu-id="62333-120">Если вы используете подсистемы балансировки нагрузки для оборудования, включите сохраняемость файлов cookie в подсистемах балансировки нагрузки, чтобы все запросы из клиента Lync Web App обрабатывались на одном и том же внешнем сервере.</span><span class="sxs-lookup"><span data-stu-id="62333-120">If you use hardware load balancers, enable cookie persistence on the load balancers so that all requests from the Lync Web App client are handled by the same Front End Server.</span></span></P>
> <LI>
> <P><span data-ttu-id="62333-121">Если вы устанавливаете отношение доверия проверяющей стороны между сервером Lync Server и серверами AD FS, назначьте жизненный цикл, достаточно длинный, чтобы занимать максимальную длину собраний Lync.</span><span class="sxs-lookup"><span data-stu-id="62333-121">When you establish a relying party trust between Lync Server and AD FS servers, assign a token life that is long enough to span the maximum length of your Lync meetings.</span></span> <span data-ttu-id="62333-122">Как правило, 240 минут бывает достаточно.</span><span class="sxs-lookup"><span data-stu-id="62333-122">Typically, a token life of 240 minutes is sufficient.</span></span></P>
> <LI>
> <P><span data-ttu-id="62333-123">Эта конфигурация не действует для мобильных клиентов Lync.</span><span class="sxs-lookup"><span data-stu-id="62333-123">This configuration does not apply to Lync mobile clients.</span></span></P></LI></UL>



</div>

<span data-ttu-id="62333-124">**Настройка многофакторной проверки подлинности**</span><span class="sxs-lookup"><span data-stu-id="62333-124">**To Configure Multi-Factor Authentication**</span></span>

1.  <span data-ttu-id="62333-125">Установите роль сервера федерации служб федерации Active Directory.</span><span class="sxs-lookup"><span data-stu-id="62333-125">Install an AD FS federation server role.</span></span> <span data-ttu-id="62333-126">Подробные сведения можно найти в руководстве по развертыванию служб федерации Active Directory 2,0 на странице<http://go.microsoft.com/fwlink/p/?linkid=267511></span><span class="sxs-lookup"><span data-stu-id="62333-126">For details, see the Active Directory Federation Services 2.0 Deployment Guide at <http://go.microsoft.com/fwlink/p/?linkid=267511></span></span>

2.  <span data-ttu-id="62333-127">Создайте сертификаты для служб федерации Active Directory.</span><span class="sxs-lookup"><span data-stu-id="62333-127">Create certificates for AD FS.</span></span> <span data-ttu-id="62333-128">Для получения дополнительных сведений ознакомьтесь с разделом "сертификаты серверов федерации" плана и развертывания AD FS для использования с темой единого входа [http://go.microsoft.com/fwlink/p/?LinkId=285376](http://go.microsoft.com/fwlink/p/?linkid=285376).</span><span class="sxs-lookup"><span data-stu-id="62333-128">For more information, see the "Federation server certificates" section of the Plan for and deploy AD FS for use with single sign-on topic at [http://go.microsoft.com/fwlink/p/?LinkId=285376](http://go.microsoft.com/fwlink/p/?linkid=285376).</span></span>

3.  <span data-ttu-id="62333-129">В интерфейсе командной строки Windows PowerShell выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="62333-129">From the Windows PowerShell command-line interface, run the following command:</span></span>
    ```powershell
    add-pssnapin Microsoft.Adfs.powershell
    ```
4.  <span data-ttu-id="62333-130">Установите партнерство, выполнив следующую команду:</span><span class="sxs-lookup"><span data-stu-id="62333-130">Establish a partnership by running the following command:</span></span>
    ```powershell
    Add-ADFSRelyingPartyTrust -Name ContosoApp -MetadataURL https://lyncpool.contoso.com/passiveauth/federationmetadata/2007-06/federationmetadata.xml
     ```
5.  <span data-ttu-id="62333-131">Настройте следующие правила проверяющей стороны:</span><span class="sxs-lookup"><span data-stu-id="62333-131">Set the following relying party rules:</span></span>
    
       ```powershell
        $IssuanceAuthorizationRules = '@RuleTemplate = "AllowAllAuthzRule" => issue(Type = "http://schemas.contoso.com/authorization/claims/permit", Value = "true");'
        $IssuanceTransformRules = '@RuleTemplate = "PassThroughClaims" @RuleName = "Sid" c:[Type == "http://schemas.contoso.com/ws/2008/06/identity/claims/primarysid"]=> issue(claim = c);'
       ```
    
       ```powershell
        Set-ADFSRelyingPartyTrust -TargetName ContosoApp -IssuanceAuthorizationRules $IssuanceAuthorizationRules -IssuanceTransformRules $IssuanceTransformRules
       ```
    
       ```powershell
        Set-CsWebServiceConfiguration -UseWsFedPassiveAuth $true -WsFedPassiveMetadataUri https://dc.contoso.com/federationmetadata/2007-06/federationmetadata.xml
       ```

</div>

<div>

## <a name="branchcache-configuration"></a><span data-ttu-id="62333-132">Настройка BranchCache</span><span class="sxs-lookup"><span data-stu-id="62333-132">BranchCache Configuration</span></span>

<span data-ttu-id="62333-133">Функция BranchCache в Windows 7 и Windows Server 2008 R2 может повлиять на веб-компоненты Lync Web App.</span><span class="sxs-lookup"><span data-stu-id="62333-133">The BranchCache feature in Windows 7 and Windows Server 2008 R2 can interfere with Lync Web App web components.</span></span> <span data-ttu-id="62333-134">Чтобы не допустить проблем для пользователей Lync Web App, убедитесь, что служба BranchCache не включена.</span><span class="sxs-lookup"><span data-stu-id="62333-134">To prevent issues for Lync Web App users, make sure that BranchCache is not enabled.</span></span>

<span data-ttu-id="62333-135">Подробнее об отключении BranchCache можно узнать в руководстве по развертыванию BranchCache, которое доступно в формате Word в центре загрузки Майкрософт по [http://go.microsoft.com/fwlink/p/?LinkId=268788](http://go.microsoft.com/fwlink/p/?linkid=268788) адресу и в формате HTML в технической библиотеке Windows Server 2008 R2 [http://go.microsoft.com/fwlink/p/?LinkId=268789](http://go.microsoft.com/fwlink/p/?linkid=268789)по адресу.</span><span class="sxs-lookup"><span data-stu-id="62333-135">For details about disabling BranchCache, see the BranchCache Deployment Guide, which is available in Word format at the Microsoft Download Center at [http://go.microsoft.com/fwlink/p/?LinkId=268788](http://go.microsoft.com/fwlink/p/?linkid=268788) and in HTML format in the Windows Server 2008 R2 Technical Library at [http://go.microsoft.com/fwlink/p/?LinkId=268789](http://go.microsoft.com/fwlink/p/?linkid=268789).</span></span>

</div>

<div>

## <a name="verifying-lync-web-app-deployment"></a><span data-ttu-id="62333-136">Проверка развертывания Lync Web App</span><span class="sxs-lookup"><span data-stu-id="62333-136">Verifying Lync Web App Deployment</span></span>

<span data-ttu-id="62333-137">С помощью командлета Test-CsUcwaConference вы можете проверить возможность участия двух тестовых пользователей в конференции с использованием веб-API объединенных коммуникаций (UCWA).</span><span class="sxs-lookup"><span data-stu-id="62333-137">You can use the Test-CsUcwaConference cmdlet to verify that a pair of test users can participate in a conference using the Unified Communications Web API (UCWA).</span></span> <span data-ttu-id="62333-138">Подробнее об этом командлете можно найти в разделе [Test-ксукваконференце](https://docs.microsoft.com/powershell/module/skype/Test-CsUcwaConference) в документации по среде управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="62333-138">For details about this cmdlet, see [Test-CsUcwaConference](https://docs.microsoft.com/powershell/module/skype/Test-CsUcwaConference) in the Lync Server Management Shell documentation.</span></span>

</div>

<div>

## <a name="troubleshooting-plug-in-installation-on-windows-server2008r2"></a><span data-ttu-id="62333-139">Устранение неполадок при установке модулей в Windows Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="62333-139">Troubleshooting Plug-in Installation on Windows Server 2008 R2</span></span>

<span data-ttu-id="62333-140">Если установка надстройки завершается сбоем на компьютере под управлением Windows Server 2008 R2, возможно, потребуется изменить параметр безопасности Internet Explorer или параметр раздела реестра Дисаблемси.</span><span class="sxs-lookup"><span data-stu-id="62333-140">If installation of the plug-in fails on a computer running Windows Server 2008 R2, you may need to modify the Internet Explorer security setting or the DisableMSI registry key setting.</span></span>

<span data-ttu-id="62333-141">**Изменение параметров безопасности в Internet Explorer**</span><span class="sxs-lookup"><span data-stu-id="62333-141">**To modify the security setting in Internet Explorer**</span></span>

1.  <span data-ttu-id="62333-142">Откройте Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="62333-142">Open Internet Explorer.</span></span>

2.  <span data-ttu-id="62333-143">В меню **Сервис** выберите пункт **Свойства обозревателя** и перейдите на вкладку **Дополнительно**.</span><span class="sxs-lookup"><span data-stu-id="62333-143">Click **Tools**, click **Internet Options**, and then click **Advanced**.</span></span>

3.  <span data-ttu-id="62333-144">Перейдите к разделу **Безопасность**.</span><span class="sxs-lookup"><span data-stu-id="62333-144">Scroll down to the **Security** section.</span></span>

4.  <span data-ttu-id="62333-145">Снимите флажок **Не сохранять зашифрованные страницы на диск** и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="62333-145">Clear **Do not save encrypted pages to disk**, and then click **OK**.</span></span>
    
    <div class=" ">
    

    > [!NOTE]  
    > <span data-ttu-id="62333-146">Если флажок установлен, этот параметр также приведет к ошибке при попытке загрузить вложение из Lync Web App.</span><span class="sxs-lookup"><span data-stu-id="62333-146">If selected, this setting will also cause an error when trying to download an attachment from Lync Web App.</span></span>

    
    </div>

5.  <span data-ttu-id="62333-147">Присоединитесь к собранию повторно.</span><span class="sxs-lookup"><span data-stu-id="62333-147">Rejoin the meeting.</span></span> <span data-ttu-id="62333-148">Подключаемый модуль должен загрузиться без ошибок.</span><span class="sxs-lookup"><span data-stu-id="62333-148">The plug-in should download without errors.</span></span>

<span data-ttu-id="62333-149">**Изменение параметра реестра Дисаблемси**</span><span class="sxs-lookup"><span data-stu-id="62333-149">**To modify the DisableMSI Registry setting**</span></span>

1.  <span data-ttu-id="62333-150">В меню **Пуск** выберите пункт **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="62333-150">Click **Start**, and then click **Run**.</span></span>

2.  <span data-ttu-id="62333-151">Чтобы открыть редактор реестра, введите команду **regedit**.</span><span class="sxs-lookup"><span data-stu-id="62333-151">To access the Registry Editor, type **regedit**.</span></span>

3.  <span data-ttu-id="62333-152">\_Перейдите к политикам\_\\\\\\программного обеспечения локального\\компьютера\\(hKey) установщика Microsoft Windows.</span><span class="sxs-lookup"><span data-stu-id="62333-152">Navigate to HKEY\_LOCAL\_MACHINE\\Software\\Policies\\Microsoft\\Windows\\Installer.</span></span>

4.  <span data-ttu-id="62333-153">Измените или добавьте раздел реестра Дисаблемси для типа REG\_(DWORD) и установите для него значение 0.</span><span class="sxs-lookup"><span data-stu-id="62333-153">Edit or add the DisableMSI registry key of type REG\_DWORD and set it to 0.</span></span>

5.  <span data-ttu-id="62333-154">Присоединитесь к собранию повторно.</span><span class="sxs-lookup"><span data-stu-id="62333-154">Rejoin the meeting.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="62333-155">См. также</span><span class="sxs-lookup"><span data-stu-id="62333-155">See Also</span></span>


[<span data-ttu-id="62333-156">Конфигурация страницы присоединения к собранию в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="62333-156">Configuring the meeting join page in Lync Server 2013</span></span>](lync-server-2013-configuring-the-meeting-join-page.md)  
[<span data-ttu-id="62333-157">Платформы, поддерживаемые Lync Web App для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="62333-157">Lync Web App supported platforms for Lync Server 2013</span></span>](lync-server-2013-lync-web-app-supported-platforms.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

