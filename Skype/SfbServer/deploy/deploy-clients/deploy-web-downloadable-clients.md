---
title: Развертывание веб-загружаемых клиентов в Skype для бизнеса Server
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.reviewer: PhillipGarding
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: b6301e98-051c-4e4b-8e10-ec922a8f508a
description: Сводка. Развертывание приложения Skype для бизнеса и skype Meetings App, используемая в Skype для бизнеса.
ms.openlocfilehash: 20489dddb244b179908f8c8a565bb1f4d539a5a7
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51122133"
---
# <a name="deploy-web-downloadable-clients-in-skype-for-business-server"></a><span data-ttu-id="98f5b-103">Развертывание веб-загружаемых клиентов в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="98f5b-103">Deploy Web downloadable clients in Skype for Business Server</span></span>

<span data-ttu-id="98f5b-104">**Сводка:** Развертывание приложения Skype для бизнеса 2015 и приложения Skype Meetings, используемой в Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="98f5b-104">**Summary:** Deploy the Skype for Business 2015 Web App and Skype Meetings App used with Skype for Business Server.</span></span>

<span data-ttu-id="98f5b-105">Skype for Business Web App — это веб-клиент Службы интернет-информации (IIS), установленный на сервере Под управлением Skype для бизнеса Server и по умолчанию развертывается по требованию для встреч с пользователями, у которых еще нет клиента Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="98f5b-105">Skype for Business Web App is an Internet Information Services (IIS) web client that is installed on the server running Skype for Business Server and by default it is deployed on demand to meeting users who do not already have the Skype for Business client.</span></span> <span data-ttu-id="98f5b-106">Эти пользователи собраний чаще всего не подключаются из-за вашей сети.</span><span class="sxs-lookup"><span data-stu-id="98f5b-106">These meeting users are more often than not connecting from outside your network.</span></span> <span data-ttu-id="98f5b-107">Всякий раз, когда пользователь щелкает URL-адрес собрания, но не установлен клиент Skype для бизнеса, пользователю будет представлена возможность присоединиться к собранию с помощью последней версии Skype для бизнеса Веб-приложения, Skype Meetings App или Skype для бизнеса для Mac.</span><span class="sxs-lookup"><span data-stu-id="98f5b-107">Whenever a user clicks a meeting URL but does not have the Skype for Business client installed, the user is presented with the option to join the meeting by using the latest version of Skype for Business Web App, Skype Meetings App, or Skype for Business for Mac.</span></span>

<span data-ttu-id="98f5b-108">Функции голосовой, видео- и совместной работы в Веб-приложении Skype для бизнеса требуют ActiveX microsoft, который используется в качестве плагина в браузере пользователя.</span><span class="sxs-lookup"><span data-stu-id="98f5b-108">The voice, video, and sharing features in Skype for Business Web App require a Microsoft ActiveX control that is used as a plugin by the user's browser.</span></span> <span data-ttu-id="98f5b-109">Вы можете установить элемент управления ActiveX заранее или разрешить пользователям устанавливать его по запросу, что происходит при первом использовании Skype для бизнеса веб-приложения или при первом доступе к функции, которая требует ActiveX управления.</span><span class="sxs-lookup"><span data-stu-id="98f5b-109">You can either install the ActiveX control in advance or allow users to install it when prompted, which happens the first time they use Skype for Business Web App or the first time they access a feature that requires the ActiveX control.</span></span>

> [!NOTE]
> <span data-ttu-id="98f5b-110">В развертываниях Skype для бизнес-сервера Edge Server для клиентского доступа к Skype для бизнеса требуется обратный прокси-сервер HTTPS в сети периметра.</span><span class="sxs-lookup"><span data-stu-id="98f5b-110">In Skype for Business Server Edge Server deployments, an HTTPS reverse proxy in the perimeter network is required for Skype for Business Web App client access.</span></span> <span data-ttu-id="98f5b-111">Вам также нужно опубликовать простые URL-адреса.</span><span class="sxs-lookup"><span data-stu-id="98f5b-111">You must also publish simple URLs.</span></span> <span data-ttu-id="98f5b-112">Подробные сведения см. [в материале Настройка требований к](/previous-versions/office/lync-server-2013/lync-server-2013-setting-up-reverse-proxy-servers) обратным прокси-серверам и DNS для простых URL-адресов [в Skype для бизнеса Server.](../../plan-your-deployment/network-requirements/simple-urls.md)</span><span class="sxs-lookup"><span data-stu-id="98f5b-112">For details, see [Setting Up Reverse Proxy Servers](/previous-versions/office/lync-server-2013/lync-server-2013-setting-up-reverse-proxy-servers) and [DNS requirements for simple URLs in Skype for Business Server](../../plan-your-deployment/network-requirements/simple-urls.md).</span></span>

## <a name="enable-multi-factor-authentication-for-skype-for-business-web-app"></a><span data-ttu-id="98f5b-113">Включить многофакторную проверку подлинности для Веб-приложения Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="98f5b-113">Enable Multi-Factor Authentication for Skype for Business Web App</span></span>
<span data-ttu-id="98f5b-114"><a name="MFA"> </a></span><span class="sxs-lookup"><span data-stu-id="98f5b-114"><a name="MFA"> </a></span></span>

<span data-ttu-id="98f5b-115">Skype для бизнеса Веб-приложение, Skype Meetings App и Skype для бизнеса для Mac поддерживают многофакторную проверку подлинности.</span><span class="sxs-lookup"><span data-stu-id="98f5b-115">Skype for Business Web App,  Skype Meetings App, and Skype for Business for Mac support multi-factor authentication.</span></span> <span data-ttu-id="98f5b-116">Помимо имени пользователя и пароля, вам могут потребоваться дополнительные методы проверки подлинности, такие как смарт-карты или ПИН-коды, для проверки подлинности пользователей, присоединявшихся к внешним сетям при входе на собрания Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="98f5b-116">In addition to user name and password, you can require additional authentication methods, such as smart cards or PINs, to authenticate users who are joining from external networks when they sign in to Skype for Business meetings.</span></span> <span data-ttu-id="98f5b-117">Можно включить многофакторную проверку подлинности, развернув сервер федерации Active Directory Federation Service (AD FS) и включив пассивную проверку подлинности в Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="98f5b-117">You can enable multi-factor authentication by deploying Active Directory Federation Service (AD FS) federation server and enabling passive authentication in Skype for Business Server.</span></span> <span data-ttu-id="98f5b-118">После настройки AD FS внешним пользователям, пытающихся присоединиться к собраниям Skype для бизнеса, будет представлена веб-страница многофакторной проверки подлинности AD FS, которая содержит имя пользователя и вызов пароля, а также дополнительные методы проверки подлинности, которые вы настроили.</span><span class="sxs-lookup"><span data-stu-id="98f5b-118">After AD FS is configured, external users who attempt to join Skype for Business meetings are presented with an AD FS multi-factor authentication webpage that contains the user name and password challenge along with any additional authentication methods that you have configured.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="98f5b-119">Если вы планируете настроить службу федерации Active Directory для многофакторной проверки подлинности, учтите следующие рекомендации.</span><span class="sxs-lookup"><span data-stu-id="98f5b-119">The following are important considerations if you plan to configure AD FS for multi-factor authentication:</span></span>

- <span data-ttu-id="98f5b-120">Многофакторная проверка подлинности ADFS работает, если участник и организатор собрания находятся в одной организации или оба из федераированной организации AD FS.</span><span class="sxs-lookup"><span data-stu-id="98f5b-120">Multi-factor ADFS authentication works if the meeting participant and organizer are both in the same organization or are both from an AD FS federated organization.</span></span> <span data-ttu-id="98f5b-121">Многофакторная проверка подлинности ADFS не работает для федерационных пользователей Lync, так как веб-инфраструктура сервера Lync в настоящее время не поддерживает ее.</span><span class="sxs-lookup"><span data-stu-id="98f5b-121">Multi-factor ADFS authentication does not work for Lync federated users because the Lync server web infrastructure does not currently support it.</span></span>

- <span data-ttu-id="98f5b-122">Если вы используете балансиры нагрузки оборудования, в используйте сохранение файлов cookie на балансире нагрузки, чтобы все запросы от клиентов Skype для бизнес-веб-приложения или приложений meetings обрабатывались тем же сервером переднего входа.</span><span class="sxs-lookup"><span data-stu-id="98f5b-122">If you use hardware load balancers, enable cookie persistence on the load balancers so that all requests from the Skype for Business Web App or Meetings App clients are handled by the same Front End Server.</span></span>

- <span data-ttu-id="98f5b-123">При создании доверительной группы между серверами Skype для бизнеса Server и AD FS назначьте срок службы маркера, который будет достаточно длительным для максимальной продолжительности собраний Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="98f5b-123">When you establish a relying party trust between Skype for Business Server and AD FS servers, assign a token life that is long enough to span the maximum length of your Skype for Business meetings.</span></span> <span data-ttu-id="98f5b-124">Как правило, 240 минут бывает достаточно.</span><span class="sxs-lookup"><span data-stu-id="98f5b-124">Typically, a token life of 240 minutes is sufficient.</span></span>

- <span data-ttu-id="98f5b-125">Эта конфигурация не применяется к мобильным клиентам Lync.</span><span class="sxs-lookup"><span data-stu-id="98f5b-125">This configuration does not apply to Lync mobile clients.</span></span>

### <a name="configure-multi-factor-authentication"></a><span data-ttu-id="98f5b-126">Настройка многофакторной проверки подлинности</span><span class="sxs-lookup"><span data-stu-id="98f5b-126">Configure Multi-Factor Authentication</span></span>

1. <span data-ttu-id="98f5b-127">Установите роль сервера федерации службы федерации Active Directory.</span><span class="sxs-lookup"><span data-stu-id="98f5b-127">Install an AD FS federation server role.</span></span> <span data-ttu-id="98f5b-128">Сведения см. в руководстве по развертыванию [Active Directory Federation Services 2.0](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/dd807092(v=ws.10))</span><span class="sxs-lookup"><span data-stu-id="98f5b-128">For details, see the [Active Directory Federation Services 2.0 Deployment Guide](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/dd807092(v=ws.10))</span></span>

2. <span data-ttu-id="98f5b-129">Создание сертификатов для AD FS.</span><span class="sxs-lookup"><span data-stu-id="98f5b-129">Create certificates for AD FS.</span></span> <span data-ttu-id="98f5b-130">Дополнительные сведения см. в разделе ["Сертификаты](/previous-versions/azure/azure-services/jj205462(v=azure.100)) сервера Федерации" в разделе Plan for and deploy AD FS for use with single sign-on topic.</span><span class="sxs-lookup"><span data-stu-id="98f5b-130">For more information, see ["Federation server certificates"](/previous-versions/azure/azure-services/jj205462(v=azure.100)) section of the Plan for and deploy AD FS for use with single sign-on topic.</span></span>

3. <span data-ttu-id="98f5b-131">Из интерфейса Windows PowerShell командной строки запустите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="98f5b-131">From the Windows PowerShell command-line interface, run the following command:</span></span>

    ```powershell
    add-pssnapin Microsoft.Adfs.powershell
    ```

4. <span data-ttu-id="98f5b-132">Установите отношение доверия, выполнив следующую команду.</span><span class="sxs-lookup"><span data-stu-id="98f5b-132">Establish a partnership by running the following command:</span></span>

    ```powershell
    Add-ADFSRelyingPartyTrust -Name ContosoApp -MetadataURL https://lyncpool.contoso.com/passiveauth/federationmetadata/2007-06/federationmetadata.xml
    ```

5. <span data-ttu-id="98f5b-133">Настройте правила проверяющей стороны.</span><span class="sxs-lookup"><span data-stu-id="98f5b-133">Set the following relying party rules:</span></span>

    ```powershell
   $IssuanceAuthorizationRules = '@RuleTemplate = "AllowAllAuthzRule" => issue(Type = "http://schemas.contoso.com/authorization/claims/permit", Value = "true");'$IssuanceTransformRules = '@RuleTemplate = "PassThroughClaims" @RuleName = "Sid" c:[Type == "http://schemas.contoso.com/ws/2008/06/identity/claims/primarysid"]=> issue(claim = c);'
   Set-ADFSRelyingPartyTrust -TargetName ContosoApp -IssuanceAuthorizationRules $IssuanceAuthorizationRules -IssuanceTransformRules $IssuanceTransformRules
   Set-CsWebServiceConfiguration -UseWsFedPassiveAuth $true -WsFedPassiveMetadataUri https://dc.contoso.com/federationmetadata/2007-06/federationmetadata.xml
   ```

## <a name="disable-branchcache"></a><span data-ttu-id="98f5b-134">Отключение BranchCache</span><span class="sxs-lookup"><span data-stu-id="98f5b-134">Disable BranchCache</span></span>
<span data-ttu-id="98f5b-135"><a name="MFA"> </a></span><span class="sxs-lookup"><span data-stu-id="98f5b-135"><a name="MFA"> </a></span></span>

<span data-ttu-id="98f5b-136">Функция BranchCache в Windows 7 и Windows Server 2008 R2 может мешать веб-компонентам Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="98f5b-136">The BranchCache feature in Windows 7 and Windows Server 2008 R2 can interfere with Skype for Business Web App web components.</span></span> <span data-ttu-id="98f5b-137">Чтобы предотвратить проблемы для пользователей веб-приложений Skype для бизнеса, убедитесь, что BranchCache не включен.</span><span class="sxs-lookup"><span data-stu-id="98f5b-137">To prevent issues for Skype for Business Web App users, make sure that BranchCache is not enabled.</span></span>

<span data-ttu-id="98f5b-138">Сведения об отключении BranchCache см. в руководстве по развертыванию [BranchCache.](/windows-server/networking/branchcache/deploy/branchcache-deployment-guide)</span><span class="sxs-lookup"><span data-stu-id="98f5b-138">For details about disabling BranchCache, see the [BranchCache Deployment Guide](/windows-server/networking/branchcache/deploy/branchcache-deployment-guide).</span></span>

## <a name="verifying-skype-for-business-web-app-deployment"></a><span data-ttu-id="98f5b-139">Проверка развертывания веб-приложений Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="98f5b-139">Verifying Skype for Business Web App Deployment</span></span>
<span data-ttu-id="98f5b-140"><a name="MFA"> </a></span><span class="sxs-lookup"><span data-stu-id="98f5b-140"><a name="MFA"> </a></span></span>

<span data-ttu-id="98f5b-141">С помощью командлета Test-CsUcwaConference вы можете проверить возможность участия двух тестовых пользователей в конференции с использованием веб-интерфейса API объединенных коммуникаций (UCWA).</span><span class="sxs-lookup"><span data-stu-id="98f5b-141">You can use the Test-CsUcwaConference cmdlet to verify that a pair of test users can participate in a conference using the Unified Communications Web API (UCWA).</span></span> <span data-ttu-id="98f5b-142">Подробные сведения об этом комлете см. в документации [Test-CsUcwaConference](/powershell/module/skype/test-csucwaconference?view=skype-ps) в документации skype for Business Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="98f5b-142">For details about this cmdlet, see [Test-CsUcwaConference](/powershell/module/skype/test-csucwaconference?view=skype-ps) in the Skype for Business Server Management Shell documentation.</span></span>

## <a name="troubleshooting-plug-in-installation-on-windows-server-2008-r2"></a><span data-ttu-id="98f5b-143">Устранение неполадок в установке подключаемого Windows Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="98f5b-143">Troubleshooting Plug-in Installation on Windows Server 2008 R2</span></span>
<span data-ttu-id="98f5b-144"><a name="MFA"> </a></span><span class="sxs-lookup"><span data-stu-id="98f5b-144"><a name="MFA"> </a></span></span>

<span data-ttu-id="98f5b-145">Если установка подключаемого плагина не удается на компьютере с Windows Server 2008 R2, возможно, потребуется изменить параметр безопасности Internet Explorer или параметр параметра отключения ключевых реестров DisableMSI.</span><span class="sxs-lookup"><span data-stu-id="98f5b-145">If installation of the plug-in fails on a computer running Windows Server 2008 R2, you may need to modify the Internet Explorer security setting or the DisableMSI registry key setting.</span></span>

### <a name="modify-the-security-setting-in-internet-explorer"></a><span data-ttu-id="98f5b-146">Изменение параметра безопасности в Internet Explorer</span><span class="sxs-lookup"><span data-stu-id="98f5b-146">Modify the security setting in Internet Explorer</span></span>

1. <span data-ttu-id="98f5b-147">Откройте Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="98f5b-147">Open Internet Explorer.</span></span>

2. <span data-ttu-id="98f5b-148">В меню **Сервис** выберите пункт **Свойства обозревателя** и перейдите на вкладку **Дополнительно**.</span><span class="sxs-lookup"><span data-stu-id="98f5b-148">Click **Tools**, click **Internet Options**, and then click **Advanced**.</span></span>

3. <span data-ttu-id="98f5b-149">Перейдите к разделу **Безопасность**.</span><span class="sxs-lookup"><span data-stu-id="98f5b-149">Scroll down to the **Security** section.</span></span>

4. <span data-ttu-id="98f5b-150">Снимите флажок **Не сохранять зашифрованные страницы на диск** и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="98f5b-150">Clear **Do not save encrypted pages to disk**, and then click **OK**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="98f5b-151">При выборе этого параметра также может быть допущена ошибка при попытке скачать вложение из Веб-приложения Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="98f5b-151">If selected, this setting will also cause an error when trying to download an attachment from Skype for Business Web App.</span></span>

5. <span data-ttu-id="98f5b-152">Присоединитесь к собранию повторно.</span><span class="sxs-lookup"><span data-stu-id="98f5b-152">Rejoin the meeting.</span></span> <span data-ttu-id="98f5b-153">Подключаемый модуль должен загрузиться без ошибок.</span><span class="sxs-lookup"><span data-stu-id="98f5b-153">The plug-in should download without errors.</span></span>

### <a name="modify-the-disablemsi-registry-setting"></a><span data-ttu-id="98f5b-154">Изменение параметра реестра DisableMSI</span><span class="sxs-lookup"><span data-stu-id="98f5b-154">Modify the DisableMSI Registry setting</span></span>

1. <span data-ttu-id="98f5b-155">В меню **Пуск** выберите пункт **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="98f5b-155">Click **Start**, and then click **Run**.</span></span>

2. <span data-ttu-id="98f5b-156">Чтобы открыть редактор реестра, введите **regedit**.</span><span class="sxs-lookup"><span data-stu-id="98f5b-156">To access the Registry Editor, type **regedit**.</span></span>

3. <span data-ttu-id="98f5b-157">Перейдите к разделу HKEY_LOCAL_MACHINE\Software\Policies\Microsoft\Windows\Installer.</span><span class="sxs-lookup"><span data-stu-id="98f5b-157">Navigate to HKEY_LOCAL_MACHINE\Software\Policies\Microsoft\Windows\Installer.</span></span>

4. <span data-ttu-id="98f5b-158">Измените или добавьте параметр реестра DisableMSI типа REG_DWORD и задайте для него значение 0.</span><span class="sxs-lookup"><span data-stu-id="98f5b-158">Edit or add the DisableMSI registry key of type REG_DWORD and set it to 0.</span></span>

5. <span data-ttu-id="98f5b-159">Присоединитесь к собранию повторно.</span><span class="sxs-lookup"><span data-stu-id="98f5b-159">Rejoin the meeting.</span></span>

## <a name="enable-skype-meetings-app-to-replace-skype-for-business-web-app-optional-skype-for-business-server-2015-only"></a><span data-ttu-id="98f5b-160">Включить приложение Skype Meetings для замены Веб-приложения Skype для бизнеса (необязательно, только Skype для бизнеса Server 2015)</span><span class="sxs-lookup"><span data-stu-id="98f5b-160">Enable Skype Meetings App to replace Skype for Business Web App (Optional, Skype for Business Server 2015 only)</span></span>
<span data-ttu-id="98f5b-161"><a name="SMA_Enable"> </a></span><span class="sxs-lookup"><span data-stu-id="98f5b-161"><a name="SMA_Enable"> </a></span></span>

<span data-ttu-id="98f5b-162">Эта процедура необязательна и применяется к Skype для бизнеса Server 2015 CU5 и более поздней.</span><span class="sxs-lookup"><span data-stu-id="98f5b-162">This procedure is optional, and applies to Skype for Business Server 2015 CU5 and later.</span></span> <span data-ttu-id="98f5b-163">Если вы не используете его, внешние пользователи будут продолжать присоединяться к собраниям с помощью Skype для бизнеса веб-приложения.</span><span class="sxs-lookup"><span data-stu-id="98f5b-163">If you do not use it, external users will continue to join meetings using Skype for Business Web App.</span></span>

### <a name="enable-simplified-meeting-join-and-skype-meetings-app"></a><span data-ttu-id="98f5b-164">Включить упрощенное приложение для собраний и собраний Skype</span><span class="sxs-lookup"><span data-stu-id="98f5b-164">Enable simplified meeting join and Skype Meetings App</span></span>

1. <span data-ttu-id="98f5b-165">При включении доступа к сети доставки контента (CDN) пользователи смогут подключаться к CDN в Интернете и получать приложение Skype Meetings App (на Windows) и Skype для бизнеса для Mac (на Mac), а также использовать упрощенную процедуру подключения к собраниям.</span><span class="sxs-lookup"><span data-stu-id="98f5b-165">When you enable access to the Content Delivery Network (CDN), users will have the ability to connect to CDN online and get Skype Meetings App (on Windows) and Skype for Business for Mac (on Mac), and will use the simplified meeting join experience.</span></span>

   ```powershell
   Set-CsWebServiceConfiguration -MeetingUxUseCdn $True
   ```

2. <span data-ttu-id="98f5b-166">Разрешить абонентской стороне ведения журнала телеметрии с веб-страницы собрания присоединиться к веб-странице или Skype Meetings App, которые будут отправлены на серверы Майкрософт (команда по умолчанию является ложной).</span><span class="sxs-lookup"><span data-stu-id="98f5b-166">Allow client side logging telemetry from the meeting join web page or the Skype Meetings App to be sent to Microsoft servers (the command defaults to false).</span></span>

   ```powershell
   Set-CsWebServiceConfiguration -MeetingUxEnableTelemetry $True
   ```

    <span data-ttu-id="98f5b-167">Информация, отправленная в Корпорацию Майкрософт, строго соответствует практикам сбора данных [Skype для бизнеса.](/skypeforbusiness/legal-and-regulatory/data-collection-practices)</span><span class="sxs-lookup"><span data-stu-id="98f5b-167">Information sent to Microsoft is in strict compliance with [Skype for Business data collection practices](/skypeforbusiness/legal-and-regulatory/data-collection-practices).</span></span>

3. <span data-ttu-id="98f5b-168">Задайте время перед тем, как вернуться к локально размещенной службе Skype для бизнес-веб-приложения, если cdN не доступен.</span><span class="sxs-lookup"><span data-stu-id="98f5b-168">Set the timeout before fall back to the locally hosted Skype for Business Web App experience if CDN isn't available.</span></span> <span data-ttu-id="98f5b-169">Значение по умолчанию — 6 секунд.</span><span class="sxs-lookup"><span data-stu-id="98f5b-169">The default value is 6 seconds.</span></span> <span data-ttu-id="98f5b-170">Если это значение установлено до 0, время не будет.</span><span class="sxs-lookup"><span data-stu-id="98f5b-170">If this value is set to 0, there will be no timeout.</span></span>

   ```powershell
   Set-CsWebServiceConfiguration -JoinLauncherCdnTimeout (New-TimeSpan -Seconds 10)
   ```

> [!NOTE]
> <span data-ttu-id="98f5b-171">Благодаря meetingUxUseCdn в Skype для бизнеса Server 2015 Кумулятивное обновление 5 значение по умолчанию задается значением False.</span><span class="sxs-lookup"><span data-stu-id="98f5b-171">With MeetingUxUseCdn in Skype for Business Server 2015 Cumulative Update 5, the default value is set to False.</span></span> <span data-ttu-id="98f5b-172">Это приводит к проблеме, из-за которой клиент Skype для бизнеса для Mac не может присоединяться к собраниям партнеров, не вступив в качестве гостя, даже если Skype для бизнеса администратор установил MeetingUxUseCdn для True.</span><span class="sxs-lookup"><span data-stu-id="98f5b-172">This causes an issue where Skype for Business for Mac client is unable to join non-federated partners' meetings as a guest, even if Skype for Business Admin has set MeetingUxUseCdn to True.</span></span> <span data-ttu-id="98f5b-173">Для этого Skype для бизнеса Server 2015 должен иметь накопительное обновление 7, 6.0.9319.534 или более позднее.</span><span class="sxs-lookup"><span data-stu-id="98f5b-173">For this to work, Skype for Business Server 2015 must have the Cumulative Update 7, 6.0.9319.534, or later.</span></span> <span data-ttu-id="98f5b-174">См. [в приложении Enable Skype Meetings App для замены Skype для бизнеса в Skype для бизнеса Server 2015.](https://support.microsoft.com/kb/4132312)</span><span class="sxs-lookup"><span data-stu-id="98f5b-174">See [Enable Skype Meetings App to replace Skype for Business Web App in Skype for Business Server 2015](https://support.microsoft.com/kb/4132312).</span></span>


## <a name="see-also"></a><span data-ttu-id="98f5b-175">См. также</span><span class="sxs-lookup"><span data-stu-id="98f5b-175">See also</span></span>
<span data-ttu-id="98f5b-176"><a name="SMA_Enable"> </a></span><span class="sxs-lookup"><span data-stu-id="98f5b-176"><a name="SMA_Enable"> </a></span></span>

[<span data-ttu-id="98f5b-177">Планирование для клиентов собраний (Web App и Meetings App)</span><span class="sxs-lookup"><span data-stu-id="98f5b-177">Plan for Meetings clients (Web App and Meetings App)</span></span>](../../plan-your-deployment/clients-and-devices/meetings-clients.md)

[<span data-ttu-id="98f5b-178">Настройка страницы присоединиться к собранию в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="98f5b-178">Configure the meeting join page in Skype for Business Server</span></span>](../../manage/conferencing/meeting-join-page.md)

[<span data-ttu-id="98f5b-179">Заявление о конфиденциальности корпорации Microsoft</span><span class="sxs-lookup"><span data-stu-id="98f5b-179">Microsoft Online Services Privacy Statement</span></span>](https://www.microsoft.com/privacystatement/OnlineServices/Default.aspx)

[<span data-ttu-id="98f5b-180">Условия лицензирования и документация</span><span class="sxs-lookup"><span data-stu-id="98f5b-180">Licensing Terms and Documentation</span></span>](http://www.microsoftvolumelicensing.com/DocumentSearch.aspx?Mode=3&amp;amp;DocumentTypeId=31)