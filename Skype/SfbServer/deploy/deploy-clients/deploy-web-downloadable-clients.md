---
title: Развертывание загружаемых веб-клиентов в Skype для бизнеса Server
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
description: Сводка. Развертывание Skype для бизнеса Web App и приложения "Собрания Skype", используемой вместе со Skype для бизнеса.
ms.openlocfilehash: afab5d0977adb8749fb514f946b676598d42ea32
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49805929"
---
# <a name="deploy-web-downloadable-clients-in-skype-for-business-server"></a><span data-ttu-id="e167d-103">Развертывание загружаемых веб-клиентов в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="e167d-103">Deploy Web downloadable clients in Skype for Business Server</span></span>

<span data-ttu-id="e167d-104">**Сводка:** Развертывание Skype для бизнеса 2015 Web App и приложения собраний Skype, используемых вместе со Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="e167d-104">**Summary:** Deploy the Skype for Business 2015 Web App and Skype Meetings App used with Skype for Business Server.</span></span>

<span data-ttu-id="e167d-105">Skype для бизнеса Web App — это веб-клиент служб IIS, установленный на сервере Skype для бизнеса Server и по умолчанию развернутый по требованию для собраний пользователей, у которых еще нет клиента Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="e167d-105">Skype for Business Web App is an Internet Information Services (IIS) web client that is installed on the server running Skype for Business Server and by default it is deployed on demand to meeting users who do not already have the Skype for Business client.</span></span> <span data-ttu-id="e167d-106">Эти пользователи собраний чаще, чем не подключаются из-за пределов вашей сети.</span><span class="sxs-lookup"><span data-stu-id="e167d-106">These meeting users are more often than not connecting from outside your network.</span></span> <span data-ttu-id="e167d-107">Каждый раз, когда пользователь щелкает URL-адрес собрания, но не имеет установленного клиента Skype для бизнеса, ему будет доступно присоединиться к собранию с помощью последней версии Skype для бизнеса Web App, приложения "Собрания Skype" или Skype для бизнеса для Mac.</span><span class="sxs-lookup"><span data-stu-id="e167d-107">Whenever a user clicks a meeting URL but does not have the Skype for Business client installed, the user is presented with the option to join the meeting by using the latest version of Skype for Business Web App, Skype Meetings App, or Skype for Business for Mac.</span></span>

<span data-ttu-id="e167d-108">Для работы функций голосовой и видеосвязи и общего доступа в Skype для бизнеса Web App требуется ActiveX Microsoft ActiveX, используемый браузером пользователя в качестве подключаемого модуль.</span><span class="sxs-lookup"><span data-stu-id="e167d-108">The voice, video, and sharing features in Skype for Business Web App require a Microsoft ActiveX control that is used as a plugin by the user's browser.</span></span> <span data-ttu-id="e167d-109">Можно либо установить элемент управления ActiveX заранее, либо разрешить пользователям устанавливать его по запросу, что происходит при первом использовании Skype для бизнеса Web App или при первом доступе к функции, для которой требуется ActiveX управления.</span><span class="sxs-lookup"><span data-stu-id="e167d-109">You can either install the ActiveX control in advance or allow users to install it when prompted, which happens the first time they use Skype for Business Web App or the first time they access a feature that requires the ActiveX control.</span></span>

> [!NOTE]
> <span data-ttu-id="e167d-110">В развертываниях Skype для бизнеса Server Edge Server обратный прокси-сервер HTTPS в сети периметра необходим для клиентского доступа Skype для бизнеса Web App.</span><span class="sxs-lookup"><span data-stu-id="e167d-110">In Skype for Business Server Edge Server deployments, an HTTPS reverse proxy in the perimeter network is required for Skype for Business Web App client access.</span></span> <span data-ttu-id="e167d-111">Вам также нужно опубликовать простые URL-адреса.</span><span class="sxs-lookup"><span data-stu-id="e167d-111">You must also publish simple URLs.</span></span> <span data-ttu-id="e167d-112">For details, see [Setting Up Reverse Proxy Servers](https://technet.microsoft.com/library/00bc138a-243f-4389-bfa5-9c62fcc95132.aspx) and [DNS requirements for simple URLs in Skype for Business Server.](../../plan-your-deployment/network-requirements/simple-urls.md)</span><span class="sxs-lookup"><span data-stu-id="e167d-112">For details, see [Setting Up Reverse Proxy Servers](https://technet.microsoft.com/library/00bc138a-243f-4389-bfa5-9c62fcc95132.aspx) and [DNS requirements for simple URLs in Skype for Business Server](../../plan-your-deployment/network-requirements/simple-urls.md).</span></span>

## <a name="enable-multi-factor-authentication-for-skype-for-business-web-app"></a><span data-ttu-id="e167d-113">Включить многофакторную проверку подлинности для Skype для бизнеса Web App</span><span class="sxs-lookup"><span data-stu-id="e167d-113">Enable Multi-Factor Authentication for Skype for Business Web App</span></span>
<span data-ttu-id="e167d-114"><a name="MFA"> </a></span><span class="sxs-lookup"><span data-stu-id="e167d-114"><a name="MFA"> </a></span></span>

<span data-ttu-id="e167d-115">Skype для бизнеса Web App, приложение "Собрания Skype" и Skype для бизнеса для Mac поддерживают многофакторную проверку подлинности.</span><span class="sxs-lookup"><span data-stu-id="e167d-115">Skype for Business Web App,  Skype Meetings App, and Skype for Business for Mac support multi-factor authentication.</span></span> <span data-ttu-id="e167d-116">Помимо имени пользователя и пароля, для проверки подлинности пользователей, которые присоединяются из внешних сетей при входе в собрания Skype для бизнеса, могут потребоваться дополнительные методы проверки подлинности, например смарт-карты или ПИН-коды.</span><span class="sxs-lookup"><span data-stu-id="e167d-116">In addition to user name and password, you can require additional authentication methods, such as smart cards or PINs, to authenticate users who are joining from external networks when they sign in to Skype for Business meetings.</span></span> <span data-ttu-id="e167d-117">Чтобы включить многофакторную проверку подлинности, развернем сервер федерации службы федерации Active Directory (AD FS) и включив пассивную проверку подлинности в Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="e167d-117">You can enable multi-factor authentication by deploying Active Directory Federation Service (AD FS) federation server and enabling passive authentication in Skype for Business Server.</span></span> <span data-ttu-id="e167d-118">После настройки AD FS внешние пользователи, пытаемые присоединиться к собраниям Skype для бизнеса, будут представлены на веб-странице многофакторной проверки подлинности AD FS, которая содержит имя пользователя и пароль, а также любые дополнительные настроенные методы проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="e167d-118">After AD FS is configured, external users who attempt to join Skype for Business meetings are presented with an AD FS multi-factor authentication webpage that contains the user name and password challenge along with any additional authentication methods that you have configured.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e167d-119">Если вы планируете настроить службу федерации Active Directory для многофакторной проверки подлинности, учтите следующие рекомендации.</span><span class="sxs-lookup"><span data-stu-id="e167d-119">The following are important considerations if you plan to configure AD FS for multi-factor authentication:</span></span>

- <span data-ttu-id="e167d-120">Многофакторная проверка подлинности ADFS работает, если участник и организатор собрания находятся в одной организации или оба являются участниками федерационной организации AD FS.</span><span class="sxs-lookup"><span data-stu-id="e167d-120">Multi-factor ADFS authentication works if the meeting participant and organizer are both in the same organization or are both from an AD FS federated organization.</span></span> <span data-ttu-id="e167d-121">Многофакторная проверка подлинности ADFS не работает для федераированных пользователей Lync, так как веб-инфраструктура сервера Lync в настоящее время не поддерживает ее.</span><span class="sxs-lookup"><span data-stu-id="e167d-121">Multi-factor ADFS authentication does not work for Lync federated users because the Lync server web infrastructure does not currently support it.</span></span>

- <span data-ttu-id="e167d-122">Если вы используете аппаратные балансиры нагрузки, в течение сохраняемого файла cookie в них можно включить сохраняемость файлов cookie, чтобы все запросы от клиентов Skype для бизнеса Web App или приложений для собраний обрабатывались на одном сервере переднего сервера.</span><span class="sxs-lookup"><span data-stu-id="e167d-122">If you use hardware load balancers, enable cookie persistence on the load balancers so that all requests from the Skype for Business Web App or Meetings App clients are handled by the same Front End Server.</span></span>

- <span data-ttu-id="e167d-123">When you establish a relying party trust between Skype for Business Server and AD FS servers, assign a token life that is long enough to span the maximum length of your Skype for Business meetings.</span><span class="sxs-lookup"><span data-stu-id="e167d-123">When you establish a relying party trust between Skype for Business Server and AD FS servers, assign a token life that is long enough to span the maximum length of your Skype for Business meetings.</span></span> <span data-ttu-id="e167d-124">Как правило, 240 минут бывает достаточно.</span><span class="sxs-lookup"><span data-stu-id="e167d-124">Typically, a token life of 240 minutes is sufficient.</span></span>

- <span data-ttu-id="e167d-125">Эта конфигурация не применяется к мобильным клиентам Lync.</span><span class="sxs-lookup"><span data-stu-id="e167d-125">This configuration does not apply to Lync mobile clients.</span></span>

### <a name="configure-multi-factor-authentication"></a><span data-ttu-id="e167d-126">Настройка многофакторной проверки подлинности</span><span class="sxs-lookup"><span data-stu-id="e167d-126">Configure Multi-Factor Authentication</span></span>

1. <span data-ttu-id="e167d-127">Установите роль сервера федерации службы федерации Active Directory.</span><span class="sxs-lookup"><span data-stu-id="e167d-127">Install an AD FS federation server role.</span></span> <span data-ttu-id="e167d-128">Подробные сведения см. в руководстве по развертыванию служб федерации [Active Directory 2.0](https://go.microsoft.com/fwlink/p/?linkid=267511)</span><span class="sxs-lookup"><span data-stu-id="e167d-128">For details, see the [Active Directory Federation Services 2.0 Deployment Guide](https://go.microsoft.com/fwlink/p/?linkid=267511)</span></span>

2. <span data-ttu-id="e167d-129">Создание сертификатов для AD FS.</span><span class="sxs-lookup"><span data-stu-id="e167d-129">Create certificates for AD FS.</span></span> <span data-ttu-id="e167d-130">Дополнительные сведения см. в разделе ["Сертификаты](https://go.microsoft.com/fwlink/p/?LinkId=285376) сервера федерации" статьи "Планирование и развертывание AD FS для использования с единым входом".</span><span class="sxs-lookup"><span data-stu-id="e167d-130">For more information, see ["Federation server certificates"](https://go.microsoft.com/fwlink/p/?LinkId=285376) section of the Plan for and deploy AD FS for use with single sign-on topic.</span></span>

3. <span data-ttu-id="e167d-131">В интерфейсе Windows PowerShell командной строки запустите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="e167d-131">From the Windows PowerShell command-line interface, run the following command:</span></span>

    ```powershell
    add-pssnapin Microsoft.Adfs.powershell
    ```

4. <span data-ttu-id="e167d-132">Установите отношение доверия, выполнив следующую команду.</span><span class="sxs-lookup"><span data-stu-id="e167d-132">Establish a partnership by running the following command:</span></span>

    ```powershell
    Add-ADFSRelyingPartyTrust -Name ContosoApp -MetadataURL https://lyncpool.contoso.com/passiveauth/federationmetadata/2007-06/federationmetadata.xml
    ```

5. <span data-ttu-id="e167d-133">Настройте правила проверяющей стороны.</span><span class="sxs-lookup"><span data-stu-id="e167d-133">Set the following relying party rules:</span></span>

    ```powershell
   $IssuanceAuthorizationRules = '@RuleTemplate = "AllowAllAuthzRule" => issue(Type = "http://schemas.contoso.com/authorization/claims/permit", Value = "true");'$IssuanceTransformRules = '@RuleTemplate = "PassThroughClaims" @RuleName = "Sid" c:[Type == "http://schemas.contoso.com/ws/2008/06/identity/claims/primarysid"]=> issue(claim = c);'
   Set-ADFSRelyingPartyTrust -TargetName ContosoApp -IssuanceAuthorizationRules $IssuanceAuthorizationRules -IssuanceTransformRules $IssuanceTransformRules
   Set-CsWebServiceConfiguration -UseWsFedPassiveAuth $true -WsFedPassiveMetadataUri https://dc.contoso.com/federationmetadata/2007-06/federationmetadata.xml
   ```

## <a name="disable-branchcache"></a><span data-ttu-id="e167d-134">Отключение BranchCache</span><span class="sxs-lookup"><span data-stu-id="e167d-134">Disable BranchCache</span></span>
<span data-ttu-id="e167d-135"><a name="MFA"> </a></span><span class="sxs-lookup"><span data-stu-id="e167d-135"><a name="MFA"> </a></span></span>

<span data-ttu-id="e167d-136">Функция BranchCache в Windows 7 и Windows Server 2008 R2 может мешать веб-компонентам Skype для бизнеса Web App.</span><span class="sxs-lookup"><span data-stu-id="e167d-136">The BranchCache feature in Windows 7 and Windows Server 2008 R2 can interfere with Skype for Business Web App web components.</span></span> <span data-ttu-id="e167d-137">Чтобы предотвратить проблемы для пользователей Skype для бизнеса Web App, убедитесь, что BranchCache не включен.</span><span class="sxs-lookup"><span data-stu-id="e167d-137">To prevent issues for Skype for Business Web App users, make sure that BranchCache is not enabled.</span></span>

<span data-ttu-id="e167d-138">Подробные сведения об отключке BranchCache см. в руководстве [по развертыванию BranchCache.](https://docs.microsoft.com/windows-server/networking/branchcache/deploy/branchcache-deployment-guide)</span><span class="sxs-lookup"><span data-stu-id="e167d-138">For details about disabling BranchCache, see the [BranchCache Deployment Guide](https://docs.microsoft.com/windows-server/networking/branchcache/deploy/branchcache-deployment-guide).</span></span>

## <a name="verifying-skype-for-business-web-app-deployment"></a><span data-ttu-id="e167d-139">Проверка развертывания Skype для бизнеса Web App</span><span class="sxs-lookup"><span data-stu-id="e167d-139">Verifying Skype for Business Web App Deployment</span></span>
<span data-ttu-id="e167d-140"><a name="MFA"> </a></span><span class="sxs-lookup"><span data-stu-id="e167d-140"><a name="MFA"> </a></span></span>

<span data-ttu-id="e167d-141">С помощью командлета Test-CsUcwaConference вы можете проверить возможность участия двух тестовых пользователей в конференции с использованием веб-интерфейса API объединенных коммуникаций (UCWA).</span><span class="sxs-lookup"><span data-stu-id="e167d-141">You can use the Test-CsUcwaConference cmdlet to verify that a pair of test users can participate in a conference using the Unified Communications Web API (UCWA).</span></span> <span data-ttu-id="e167d-142">For details about this cmdlet, see [Test-CsUcwaConference](https://docs.microsoft.com/powershell/module/skype/test-csucwaconference?view=skype-ps) in the Skype for Business Server Management Shell documentation.</span><span class="sxs-lookup"><span data-stu-id="e167d-142">For details about this cmdlet, see [Test-CsUcwaConference](https://docs.microsoft.com/powershell/module/skype/test-csucwaconference?view=skype-ps) in the Skype for Business Server Management Shell documentation.</span></span>

## <a name="troubleshooting-plug-in-installation-on-windows-server-2008-r2"></a><span data-ttu-id="e167d-143">Устранение неполадок при установке подключаемого Windows Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="e167d-143">Troubleshooting Plug-in Installation on Windows Server 2008 R2</span></span>
<span data-ttu-id="e167d-144"><a name="MFA"> </a></span><span class="sxs-lookup"><span data-stu-id="e167d-144"><a name="MFA"> </a></span></span>

<span data-ttu-id="e167d-145">Если установка подключаемого модуль не удается на компьютере, на Windows Server 2008 R2, может потребоваться изменить параметры безопасности Internet Explorer или Параметры реестра DisableMSI.</span><span class="sxs-lookup"><span data-stu-id="e167d-145">If installation of the plug-in fails on a computer running Windows Server 2008 R2, you may need to modify the Internet Explorer security setting or the DisableMSI registry key setting.</span></span>

### <a name="modify-the-security-setting-in-internet-explorer"></a><span data-ttu-id="e167d-146">Изменение параметра безопасности в Internet Explorer</span><span class="sxs-lookup"><span data-stu-id="e167d-146">Modify the security setting in Internet Explorer</span></span>

1. <span data-ttu-id="e167d-147">Откройте Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="e167d-147">Open Internet Explorer.</span></span>

2. <span data-ttu-id="e167d-148">В меню **Сервис** выберите пункт **Свойства обозревателя** и перейдите на вкладку **Дополнительно**.</span><span class="sxs-lookup"><span data-stu-id="e167d-148">Click **Tools**, click **Internet Options**, and then click **Advanced**.</span></span>

3. <span data-ttu-id="e167d-149">Перейдите к разделу **Безопасность**.</span><span class="sxs-lookup"><span data-stu-id="e167d-149">Scroll down to the **Security** section.</span></span>

4. <span data-ttu-id="e167d-150">Снимите флажок **Не сохранять зашифрованные страницы на диск** и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="e167d-150">Clear **Do not save encrypted pages to disk**, and then click **OK**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="e167d-151">Если этот параметр выбран, при попытке скачать вложение из Skype для бизнеса Web App также будет происходить ошибка.</span><span class="sxs-lookup"><span data-stu-id="e167d-151">If selected, this setting will also cause an error when trying to download an attachment from Skype for Business Web App.</span></span>

5. <span data-ttu-id="e167d-152">Присоединитесь к собранию повторно.</span><span class="sxs-lookup"><span data-stu-id="e167d-152">Rejoin the meeting.</span></span> <span data-ttu-id="e167d-153">Подключаемый модуль должен загрузиться без ошибок.</span><span class="sxs-lookup"><span data-stu-id="e167d-153">The plug-in should download without errors.</span></span>

### <a name="modify-the-disablemsi-registry-setting"></a><span data-ttu-id="e167d-154">Изменение параметра реестра DisableMSI</span><span class="sxs-lookup"><span data-stu-id="e167d-154">Modify the DisableMSI Registry setting</span></span>

1. <span data-ttu-id="e167d-155">В меню **Пуск** выберите пункт **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="e167d-155">Click **Start**, and then click **Run**.</span></span>

2. <span data-ttu-id="e167d-156">Чтобы открыть редактор реестра, введите **regedit**.</span><span class="sxs-lookup"><span data-stu-id="e167d-156">To access the Registry Editor, type **regedit**.</span></span>

3. <span data-ttu-id="e167d-157">Перейдите к разделу HKEY_LOCAL_MACHINE\Software\Policies\Microsoft\Windows\Installer.</span><span class="sxs-lookup"><span data-stu-id="e167d-157">Navigate to HKEY_LOCAL_MACHINE\Software\Policies\Microsoft\Windows\Installer.</span></span>

4. <span data-ttu-id="e167d-158">Измените или добавьте параметр реестра DisableMSI типа REG_DWORD и задайте для него значение 0.</span><span class="sxs-lookup"><span data-stu-id="e167d-158">Edit or add the DisableMSI registry key of type REG_DWORD and set it to 0.</span></span>

5. <span data-ttu-id="e167d-159">Присоединитесь к собранию повторно.</span><span class="sxs-lookup"><span data-stu-id="e167d-159">Rejoin the meeting.</span></span>

## <a name="enable-skype-meetings-app-to-replace-skype-for-business-web-app-optional-skype-for-business-server-2015-only"></a><span data-ttu-id="e167d-160">Enable Skype Meetings App to replace Skype for Business Web App (Optional, Skype for Business Server 2015 only)</span><span class="sxs-lookup"><span data-stu-id="e167d-160">Enable Skype Meetings App to replace Skype for Business Web App (Optional, Skype for Business Server 2015 only)</span></span>
<span data-ttu-id="e167d-161"><a name="SMA_Enable"> </a></span><span class="sxs-lookup"><span data-stu-id="e167d-161"><a name="SMA_Enable"> </a></span></span>

<span data-ttu-id="e167d-162">Эта процедура является необязательной и применяется к Skype для бизнеса Server 2015 CU5 и более поздним.</span><span class="sxs-lookup"><span data-stu-id="e167d-162">This procedure is optional, and applies to Skype for Business Server 2015 CU5 and later.</span></span> <span data-ttu-id="e167d-163">Если вы не используете его, внешние пользователи продолжат присоединяться к собраниям с помощью Skype для бизнеса Web App.</span><span class="sxs-lookup"><span data-stu-id="e167d-163">If you do not use it, external users will continue to join meetings using Skype for Business Web App.</span></span>

### <a name="enable-simplified-meeting-join-and-skype-meetings-app"></a><span data-ttu-id="e167d-164">Enable simplified meeting join and Skype Meetings App</span><span class="sxs-lookup"><span data-stu-id="e167d-164">Enable simplified meeting join and Skype Meetings App</span></span>

1. <span data-ttu-id="e167d-165">При включении доступа к сети доставки содержимого (CDN) пользователи смогут подключаться к сети CDN и получать приложение "Собрания Skype" (в Windows) и Skype для бизнеса для Mac (на Mac) и будут использовать упрощенное присоединение к собранию.</span><span class="sxs-lookup"><span data-stu-id="e167d-165">When you enable access to the Content Delivery Network (CDN), users will have the ability to connect to CDN online and get Skype Meetings App (on Windows) and Skype for Business for Mac (on Mac), and will use the simplified meeting join experience.</span></span>

   ```powershell
   Set-CsWebServiceConfiguration -MeetingUxUseCdn $True
   ```

2. <span data-ttu-id="e167d-166">Разрешить серверы Майкрософт отослать телеметрию ведения журнала на стороне клиента с веб-страницы присоединить к собранию или приложение "Собрания Skype" (команда по умолчанию имеет значение false).</span><span class="sxs-lookup"><span data-stu-id="e167d-166">Allow client side logging telemetry from the meeting join web page or the Skype Meetings App to be sent to Microsoft servers (the command defaults to false).</span></span>

   ```powershell
   Set-CsWebServiceConfiguration -MeetingUxEnableTelemetry $True
   ```

    <span data-ttu-id="e167d-167">Информация, отданная в корпорацию Майкрософт, строго соответствует методикам сбора данных Skype для [бизнеса.](https://docs.microsoft.com/skypeforbusiness/legal-and-regulatory/data-collection-practices)</span><span class="sxs-lookup"><span data-stu-id="e167d-167">Information sent to Microsoft is in strict compliance with [Skype for Business data collection practices](https://docs.microsoft.com/skypeforbusiness/legal-and-regulatory/data-collection-practices).</span></span>

3. <span data-ttu-id="e167d-168">Задайте время, прежде чем вернуться к локально размещенной сети Skype для бизнеса Web App, если сеть CDN недоступна.</span><span class="sxs-lookup"><span data-stu-id="e167d-168">Set the timeout before fall back to the locally hosted Skype for Business Web App experience if CDN isn't available.</span></span> <span data-ttu-id="e167d-169">Значение по умолчанию — 6 секунд.</span><span class="sxs-lookup"><span data-stu-id="e167d-169">The default value is 6 seconds.</span></span> <span data-ttu-id="e167d-170">Если за установлено значение 0, время не будет установлено.</span><span class="sxs-lookup"><span data-stu-id="e167d-170">If this value is set to 0, there will be no timeout.</span></span>

   ```powershell
   Set-CsWebServiceConfiguration -JoinLauncherCdnTimeout (New-TimeSpan -Seconds 10)
   ```

> [!NOTE]
> <span data-ttu-id="e167d-171">With MeetingUxUseCdn in Skype for Business Server 2015 Cumulative Update 5, the default value is set to False.</span><span class="sxs-lookup"><span data-stu-id="e167d-171">With MeetingUxUseCdn in Skype for Business Server 2015 Cumulative Update 5, the default value is set to False.</span></span> <span data-ttu-id="e167d-172">Это приводит к проблеме, из-за которой клиент Skype для бизнеса для Mac не может присоединяться к собраниям не федерационных партнеров в качестве гостя, даже если администратор Skype для бизнеса установил для MeetingUxUseCdn true.</span><span class="sxs-lookup"><span data-stu-id="e167d-172">This causes an issue where Skype for Business for Mac client is unable to join non-federated partners' meetings as a guest, even if Skype for Business Admin has set MeetingUxUseCdn to True.</span></span> <span data-ttu-id="e167d-173">Для этого Skype для бизнеса Server 2015 должен иметь накопительный обновления 7, 6.0.9319.534 или более поздней версии.</span><span class="sxs-lookup"><span data-stu-id="e167d-173">For this to work, Skype for Business Server 2015 must have the Cumulative Update 7, 6.0.9319.534, or later.</span></span> <span data-ttu-id="e167d-174">См. ["Приложение "Включить собрания Skype" для замены Skype для бизнеса Web App в Skype для бизнеса Server 2015.](https://support.microsoft.com/kb/4132312)</span><span class="sxs-lookup"><span data-stu-id="e167d-174">See [Enable Skype Meetings App to replace Skype for Business Web App in Skype for Business Server 2015](https://support.microsoft.com/kb/4132312).</span></span>


## <a name="see-also"></a><span data-ttu-id="e167d-175">См. также</span><span class="sxs-lookup"><span data-stu-id="e167d-175">See also</span></span>
<span data-ttu-id="e167d-176"><a name="SMA_Enable"> </a></span><span class="sxs-lookup"><span data-stu-id="e167d-176"><a name="SMA_Enable"> </a></span></span>

[<span data-ttu-id="e167d-177">Планирование клиентов собраний (Веб-приложение и приложение для собраний)</span><span class="sxs-lookup"><span data-stu-id="e167d-177">Plan for Meetings clients (Web App and Meetings App)</span></span>](../../plan-your-deployment/clients-and-devices/meetings-clients.md)

[<span data-ttu-id="e167d-178">Настройка страницы присоединить к собранию в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="e167d-178">Configure the meeting join page in Skype for Business Server</span></span>](../../manage/conferencing/meeting-join-page.md)

[<span data-ttu-id="e167d-179">Заявление о конфиденциальности корпорации Microsoft</span><span class="sxs-lookup"><span data-stu-id="e167d-179">Microsoft Online Services Privacy Statement</span></span>](https://www.microsoft.com/privacystatement/OnlineServices/Default.aspx)

[<span data-ttu-id="e167d-180">Условия лицензирования и документация</span><span class="sxs-lookup"><span data-stu-id="e167d-180">Licensing Terms and Documentation</span></span>](http://www.microsoftvolumelicensing.com/DocumentSearch.aspx?Mode=3&amp;amp;DocumentTypeId=31)
