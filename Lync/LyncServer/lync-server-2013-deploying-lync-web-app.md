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
ms.openlocfilehash: 8babb6bf37e3dd75f2051dd08f0b2ebf3a4f093b
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42195352"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deploying-lync-web-app-in-lync-server-2013"></a><span data-ttu-id="275b0-102">Развертывание Lync Web App в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="275b0-102">Deploying Lync Web App in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="275b0-103">_**Последнее изменение темы:** 2013-07-18_</span><span class="sxs-lookup"><span data-stu-id="275b0-103">_**Topic Last Modified:** 2013-07-18_</span></span>

<span data-ttu-id="275b0-104">Lync Web App — это веб-клиент служб IIS, устанавливаемый с Lync Server 2013 и включенный по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="275b0-104">Lync Web App is an Internet Information Services (IIS) web client that installs with Lync Server 2013 and is enabled by default.</span></span> <span data-ttu-id="275b0-105">Для включения Lync Web App на сервере или развертывания веб-клиента для пользователей не требуется выполнять какие-либо дополнительные действия.</span><span class="sxs-lookup"><span data-stu-id="275b0-105">No additional steps are necessary to either enable Lync Web App on the server or deploy the web client to users.</span></span> <span data-ttu-id="275b0-106">Когда пользователь щелкает URL-адрес собрания, но на нем не установлен клиент Lync 2013, пользователю предоставляется возможность присоединиться к собранию с помощью последней версии Lync Web App.</span><span class="sxs-lookup"><span data-stu-id="275b0-106">Whenever a user clicks a meeting URL but does not have the Lync 2013 client installed, the user is presented with the option to join the meeting by using the latest version of Lync Web App.</span></span>

<span data-ttu-id="275b0-107">Функции голосовых, видео и общего доступа в Lync Web App требуют наличия элемента управления Microsoft ActiveX.</span><span class="sxs-lookup"><span data-stu-id="275b0-107">The voice, video, and sharing features in Lync Web App require a Microsoft ActiveX control.</span></span> <span data-ttu-id="275b0-108">Вы можете либо установить элемент управления ActiveX заранее, либо разрешить пользователям устанавливать его при появлении соответствующего запроса, что происходит при первом использовании Lync Web App или при первом доступе к функции, требующей элемента управления ActiveX.</span><span class="sxs-lookup"><span data-stu-id="275b0-108">You can either install the ActiveX control in advance or allow users to install it when prompted, which happens the first time they use Lync Web App or the first time they access a feature that requires the ActiveX control.</span></span>

<div class=" ">


> [!NOTE]  
> <span data-ttu-id="275b0-109">В развертываниях пограничных серверов Lync Server 2013 для клиентского доступа Lync Web App необходимо использовать обратный прокси-сервер HTTPS в сети периметра.</span><span class="sxs-lookup"><span data-stu-id="275b0-109">In Lync Server 2013 Edge Server deployments, an HTTPS reverse proxy in the perimeter network is required for Lync Web App client access.</span></span> <span data-ttu-id="275b0-110">Вам также нужно опубликовать простые URL-адреса.</span><span class="sxs-lookup"><span data-stu-id="275b0-110">You must also publish simple URLs.</span></span> <span data-ttu-id="275b0-111">Дополнительную информацию можно узнать в статье <A href="lync-server-2013-setting-up-reverse-proxy-servers.md">Настройка обратных прокси-серверов для Lync server 2013</A> и <A href="lync-server-2013-planning-for-simple-urls.md">планирование простых URL-адресов в Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="275b0-111">For details, see <A href="lync-server-2013-setting-up-reverse-proxy-servers.md">Setting up reverse proxy servers for Lync Server 2013</A> and <A href="lync-server-2013-planning-for-simple-urls.md">Planning for simple URLs in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="enabling-multi-factor-authentication-for-lync-web-app"></a><span data-ttu-id="275b0-112">Включение многофакторной проверки подлинности для Lync Web App</span><span class="sxs-lookup"><span data-stu-id="275b0-112">Enabling Multi-Factor Authentication for Lync Web App</span></span>

<span data-ttu-id="275b0-113">Lync Server 2013 версии Lync Web App поддерживает многофакторную проверку подлинности.</span><span class="sxs-lookup"><span data-stu-id="275b0-113">The Lync Server 2013 version of Lync Web App supports multi-factor authentication.</span></span> <span data-ttu-id="275b0-114">Помимо имени пользователя и пароля, для проверки подлинности пользователей, присоединяющихся к собраниям Lync, могут потребоваться дополнительные методы проверки подлинности, такие как смарт-карты или ПИН-коды.</span><span class="sxs-lookup"><span data-stu-id="275b0-114">In addition to user name and password, you can require additional authentication methods, such as smart cards or PINs, to authenticate users who are joining from external networks when they sign in to Lync meetings.</span></span> <span data-ttu-id="275b0-115">Вы можете включить многофакторную проверку подлинности, развернув сервер федерации службы федерации Active Directory (AD FS) и включив пассивную проверку подлинности в Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="275b0-115">You can enable multi-factor authentication by deploying Active Directory Federation Service (AD FS) federation server and enabling passive authentication in Lync Server 2013.</span></span> <span data-ttu-id="275b0-116">После настройки AD FS внешние пользователи, пытающиеся присоединиться к собраниям Lync, отображаются с помощью веб-страницы многофакторной проверки подлинности AD FS, которая содержит имя пользователя и пароль, а также дополнительные методы проверки подлинности, настроенные .</span><span class="sxs-lookup"><span data-stu-id="275b0-116">After AD FS is configured, external users who attempt to join Lync meetings are presented with an AD FS multi-factor authentication webpage that contains the user name and password challenge along with any additional authentication methods that you have configured.</span></span>

<div class=" ">


> [!IMPORTANT]  
> <span data-ttu-id="275b0-117">Если вы планируете настроить службу федерации Active Directory для многофакторной проверки подлинности, учтите следующие рекомендации.</span><span class="sxs-lookup"><span data-stu-id="275b0-117">The following are important considerations if you plan to configure AD FS for multi-factor authentication:</span></span> 
> <UL>
> <LI>
> <P><span data-ttu-id="275b0-118">Многофакторная проверка подлинности в службах ADFS работает, если участник и организатор собрания одновременно находятся в одной организации или в федеративной организации AD FS.</span><span class="sxs-lookup"><span data-stu-id="275b0-118">Multi-factor ADFS authentication works if the meeting participant and organizer are both in the same organization or are both from an AD FS federated organization.</span></span> <span data-ttu-id="275b0-119">Многофакторная проверка подлинности ADFS не работает для федеративных пользователей Lync, так как веб-инфраструктура Lync Server в настоящее время не поддерживает эту службу.</span><span class="sxs-lookup"><span data-stu-id="275b0-119">Multi-factor ADFS authentication does not work for Lync federated users because the Lync server web infrastructure does not currently support it.</span></span></P>
> <LI>
> <P><span data-ttu-id="275b0-120">Если вы используете аппаратные средства балансировки нагрузки, включите сохранение файлов cookie в подсистемах балансировки нагрузки, чтобы все запросы от клиента Lync Web App обрабатывались одним сервером переднего плана.</span><span class="sxs-lookup"><span data-stu-id="275b0-120">If you use hardware load balancers, enable cookie persistence on the load balancers so that all requests from the Lync Web App client are handled by the same Front End Server.</span></span></P>
> <LI>
> <P><span data-ttu-id="275b0-121">При установке отношения доверия с проверяющей стороной между Lync Server и серверами AD FS назначьте срок действия маркера, достаточного для достижения максимальной длины собраний Lync.</span><span class="sxs-lookup"><span data-stu-id="275b0-121">When you establish a relying party trust between Lync Server and AD FS servers, assign a token life that is long enough to span the maximum length of your Lync meetings.</span></span> <span data-ttu-id="275b0-122">Как правило, 240 минут бывает достаточно.</span><span class="sxs-lookup"><span data-stu-id="275b0-122">Typically, a token life of 240 minutes is sufficient.</span></span></P>
> <LI>
> <P><span data-ttu-id="275b0-123">Эта конфигурация не применяется к мобильным клиентам Lync.</span><span class="sxs-lookup"><span data-stu-id="275b0-123">This configuration does not apply to Lync mobile clients.</span></span></P></LI></UL>



</div>

<span data-ttu-id="275b0-124">**Настройка многофакторной проверки подлинности**</span><span class="sxs-lookup"><span data-stu-id="275b0-124">**To Configure Multi-Factor Authentication**</span></span>

1.  <span data-ttu-id="275b0-125">Установите роль сервера федерации службы федерации Active Directory.</span><span class="sxs-lookup"><span data-stu-id="275b0-125">Install an AD FS federation server role.</span></span> <span data-ttu-id="275b0-126">Подробные сведения см. в руководстве по развертыванию служб федерации Active Directory 2,0 в<https://go.microsoft.com/fwlink/p/?linkid=267511></span><span class="sxs-lookup"><span data-stu-id="275b0-126">For details, see the Active Directory Federation Services 2.0 Deployment Guide at <https://go.microsoft.com/fwlink/p/?linkid=267511></span></span>

2.  <span data-ttu-id="275b0-127">Создайте сертификаты для AD FS.</span><span class="sxs-lookup"><span data-stu-id="275b0-127">Create certificates for AD FS.</span></span> <span data-ttu-id="275b0-128">Для получения дополнительных сведений обратитесь к разделу "сертификаты сервера федерации" плана for Active Directory для использования с одним входом в [https://go.microsoft.com/fwlink/p/?LinkId=285376](https://go.microsoft.com/fwlink/p/?linkid=285376)разделе "планирование и развертывание AD FS".</span><span class="sxs-lookup"><span data-stu-id="275b0-128">For more information, see the "Federation server certificates" section of the Plan for and deploy AD FS for use with single sign-on topic at [https://go.microsoft.com/fwlink/p/?LinkId=285376](https://go.microsoft.com/fwlink/p/?linkid=285376).</span></span>

3.  <span data-ttu-id="275b0-129">В интерфейсе командной строки Windows PowerShell выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="275b0-129">From the Windows PowerShell command-line interface, run the following command:</span></span>
    ```powershell
    add-pssnapin Microsoft.Adfs.powershell
    ```
4.  <span data-ttu-id="275b0-130">Установите отношение доверия, выполнив следующую команду.</span><span class="sxs-lookup"><span data-stu-id="275b0-130">Establish a partnership by running the following command:</span></span>
    ```powershell
    Add-ADFSRelyingPartyTrust -Name ContosoApp -MetadataURL https://lyncpool.contoso.com/passiveauth/federationmetadata/2007-06/federationmetadata.xml
     ```
5.  <span data-ttu-id="275b0-131">Настройте правила проверяющей стороны.</span><span class="sxs-lookup"><span data-stu-id="275b0-131">Set the following relying party rules:</span></span>
    
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

## <a name="branchcache-configuration"></a><span data-ttu-id="275b0-132">Настройка BranchCache</span><span class="sxs-lookup"><span data-stu-id="275b0-132">BranchCache Configuration</span></span>

<span data-ttu-id="275b0-133">Функция BranchCache в Windows 7 и Windows Server 2008 R2 может повлиять на веб-компоненты Lync Web App.</span><span class="sxs-lookup"><span data-stu-id="275b0-133">The BranchCache feature in Windows 7 and Windows Server 2008 R2 can interfere with Lync Web App web components.</span></span> <span data-ttu-id="275b0-134">Чтобы предотвратить возникновение проблем для пользователей Lync Web App, убедитесь, что служба BranchCache отключена.</span><span class="sxs-lookup"><span data-stu-id="275b0-134">To prevent issues for Lync Web App users, make sure that BranchCache is not enabled.</span></span>

<span data-ttu-id="275b0-135">Дополнительные сведения об отключении BranchCache содержатся в руководстве по развертыванию BranchCache, доступном в формате Word в центре загрузки Майкрософт по [https://go.microsoft.com/fwlink/p/?LinkId=268788](https://go.microsoft.com/fwlink/p/?linkid=268788) адресу и в формате HTML в технической библиотеке Windows Server 2008 R2 [https://go.microsoft.com/fwlink/p/?LinkId=268789](https://go.microsoft.com/fwlink/p/?linkid=268789)по адресу.</span><span class="sxs-lookup"><span data-stu-id="275b0-135">For details about disabling BranchCache, see the BranchCache Deployment Guide, which is available in Word format at the Microsoft Download Center at [https://go.microsoft.com/fwlink/p/?LinkId=268788](https://go.microsoft.com/fwlink/p/?linkid=268788) and in HTML format in the Windows Server 2008 R2 Technical Library at [https://go.microsoft.com/fwlink/p/?LinkId=268789](https://go.microsoft.com/fwlink/p/?linkid=268789).</span></span>

</div>

<div>

## <a name="verifying-lync-web-app-deployment"></a><span data-ttu-id="275b0-136">Проверка развертывания Lync Web App</span><span class="sxs-lookup"><span data-stu-id="275b0-136">Verifying Lync Web App Deployment</span></span>

<span data-ttu-id="275b0-137">С помощью командлета Test-CsUcwaConference вы можете проверить возможность участия двух тестовых пользователей в конференции с использованием веб-интерфейса API объединенных коммуникаций (UCWA).</span><span class="sxs-lookup"><span data-stu-id="275b0-137">You can use the Test-CsUcwaConference cmdlet to verify that a pair of test users can participate in a conference using the Unified Communications Web API (UCWA).</span></span> <span data-ttu-id="275b0-138">Подробнее об этом командлете можно узнать в статье [Test-CsUcwaConference](https://docs.microsoft.com/powershell/module/skype/Test-CsUcwaConference) в документации по консоли управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="275b0-138">For details about this cmdlet, see [Test-CsUcwaConference](https://docs.microsoft.com/powershell/module/skype/Test-CsUcwaConference) in the Lync Server Management Shell documentation.</span></span>

</div>

<div>

## <a name="troubleshooting-plug-in-installation-on-windows-server2008r2"></a><span data-ttu-id="275b0-139">Устранение неполадок при установке подключаемого модуля в Windows Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="275b0-139">Troubleshooting Plug-in Installation on Windows Server 2008 R2</span></span>

<span data-ttu-id="275b0-140">Если при установке подключаемого модуля произошел сбой на компьютере под управлением Windows Server 2008 R2, может потребоваться изменить параметр безопасности Internet Explorer или раздел реестра параметр DisableMSI.</span><span class="sxs-lookup"><span data-stu-id="275b0-140">If installation of the plug-in fails on a computer running Windows Server 2008 R2, you may need to modify the Internet Explorer security setting or the DisableMSI registry key setting.</span></span>

<span data-ttu-id="275b0-141">**Изменение параметра безопасности в Internet Explorer**</span><span class="sxs-lookup"><span data-stu-id="275b0-141">**To modify the security setting in Internet Explorer**</span></span>

1.  <span data-ttu-id="275b0-142">Откройте Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="275b0-142">Open Internet Explorer.</span></span>

2.  <span data-ttu-id="275b0-143">В меню **Сервис** выберите пункт **Свойства обозревателя** и перейдите на вкладку **Дополнительно**.</span><span class="sxs-lookup"><span data-stu-id="275b0-143">Click **Tools**, click **Internet Options**, and then click **Advanced**.</span></span>

3.  <span data-ttu-id="275b0-144">Перейдите к разделу **Безопасность**.</span><span class="sxs-lookup"><span data-stu-id="275b0-144">Scroll down to the **Security** section.</span></span>

4.  <span data-ttu-id="275b0-145">Снимите флажок **Не сохранять зашифрованные страницы на диск** и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="275b0-145">Clear **Do not save encrypted pages to disk**, and then click **OK**.</span></span>
    
    <div class=" ">
    

    > [!NOTE]  
    > <span data-ttu-id="275b0-146">Если этот параметр выбран, то при попытке скачать вложение из Lync Web App будет возникнет ошибка.</span><span class="sxs-lookup"><span data-stu-id="275b0-146">If selected, this setting will also cause an error when trying to download an attachment from Lync Web App.</span></span>

    
    </div>

5.  <span data-ttu-id="275b0-147">Присоединитесь к собранию повторно.</span><span class="sxs-lookup"><span data-stu-id="275b0-147">Rejoin the meeting.</span></span> <span data-ttu-id="275b0-148">Подключаемый модуль должен загрузиться без ошибок.</span><span class="sxs-lookup"><span data-stu-id="275b0-148">The plug-in should download without errors.</span></span>

<span data-ttu-id="275b0-149">**Изменение параметра реестра DisableMSI**</span><span class="sxs-lookup"><span data-stu-id="275b0-149">**To modify the DisableMSI Registry setting**</span></span>

1.  <span data-ttu-id="275b0-150">В меню **Пуск** выберите пункт **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="275b0-150">Click **Start**, and then click **Run**.</span></span>

2.  <span data-ttu-id="275b0-151">Чтобы открыть редактор реестра, введите **regedit**.</span><span class="sxs-lookup"><span data-stu-id="275b0-151">To access the Registry Editor, type **regedit**.</span></span>

3.  <span data-ttu-id="275b0-152">Перейдите в раздел\_hKey\_программное\\обеспечение\\локального\\компьютера\\\\, установщик Microsoft Windows.</span><span class="sxs-lookup"><span data-stu-id="275b0-152">Navigate to HKEY\_LOCAL\_MACHINE\\Software\\Policies\\Microsoft\\Windows\\Installer.</span></span>

4.  <span data-ttu-id="275b0-153">Измените или добавьте раздел реестра параметр DisableMSI типа REG\_DWORD и присвойте ему значение 0.</span><span class="sxs-lookup"><span data-stu-id="275b0-153">Edit or add the DisableMSI registry key of type REG\_DWORD and set it to 0.</span></span>

5.  <span data-ttu-id="275b0-154">Присоединитесь к собранию повторно.</span><span class="sxs-lookup"><span data-stu-id="275b0-154">Rejoin the meeting.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="275b0-155">См. также</span><span class="sxs-lookup"><span data-stu-id="275b0-155">See Also</span></span>


[<span data-ttu-id="275b0-156">Настройка страницы присоединения к собранию в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="275b0-156">Configuring the meeting join page in Lync Server 2013</span></span>](lync-server-2013-configuring-the-meeting-join-page.md)  
[<span data-ttu-id="275b0-157">Платформы, поддерживаемые в Lync Web App для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="275b0-157">Lync Web App supported platforms for Lync Server 2013</span></span>](lync-server-2013-lync-web-app-supported-platforms.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

