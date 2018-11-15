---
title: Развертывание веб-загрузки клиентов в Скайп для Business Server
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.reviewer: PhillipGarding
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b6301e98-051c-4e4b-8e10-ec922a8f508a
description: 'Сводка: Развертывание Скайп для бизнеса Web App и использовать приложение Скайп собраний с Скайп для бизнеса.'
ms.openlocfilehash: 7fabbbbd279e2f72f3468fbe73a55b86e532f6cf
ms.sourcegitcommit: 30620021ceba916a505437ab641a23393f55827a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/15/2018
ms.locfileid: "26531547"
---
# <a name="deploy-web-downloadable-clients-in-skype-for-business-server"></a><span data-ttu-id="ef940-103">Развертывание веб-загрузки клиентов в Скайп для Business Server</span><span class="sxs-lookup"><span data-stu-id="ef940-103">Deploy Web downloadable clients in Skype for Business Server</span></span>

<span data-ttu-id="ef940-104">**Сводка:** Развертывание Скайп для бизнеса 2015 Web App и использовать приложения Скайп собраний с Скайп для Business Server.</span><span class="sxs-lookup"><span data-stu-id="ef940-104">**Summary:** Deploy the Skype for Business 2015 Web App and Skype Meetings App used with Skype for Business Server.</span></span>

<span data-ttu-id="ef940-105">Скайп для бизнеса Web App — это клиент web Internet Information Services (IIS), установленной на сервере под управлением Скайп для Business Server и по умолчанию он будет развернут по запросу пользователям собрания, которые еще не Скайп для клиента Business.</span><span class="sxs-lookup"><span data-stu-id="ef940-105">Skype for Business Web App is an Internet Information Services (IIS) web client that is installed on the server running Skype for Business Server and by default it is deployed on demand to meeting users who do not already have the Skype for Business client.</span></span> <span data-ttu-id="ef940-106">Эти пользователи собрания не чаще, чем не подключении за пределами вашей сети.</span><span class="sxs-lookup"><span data-stu-id="ef940-106">These meeting users are more often than not connecting from outside your network.</span></span> <span data-ttu-id="ef940-107">Каждый раз, когда пользователь щелкает URL-адрес собрания, но не имеет Скайп для установки клиента Business, пользователю предоставляется возможность присоединения к собранию с помощью последней версии Скайп для бизнеса веб-приложения или приложения Скайп собрания.</span><span class="sxs-lookup"><span data-stu-id="ef940-107">Whenever a user clicks a meeting URL but does not have the Skype for Business client installed, the user is presented with the option to join the meeting by using the latest version of Skype for Business Web App or Skype Meetings App.</span></span>

<span data-ttu-id="ef940-108">Голосовой связи, видеозаписи и общего доступа компонентов в Скайп Business Web App требуется элемент управления Microsoft ActiveX, который используется в качестве подключаемый модуль, браузер пользователя.</span><span class="sxs-lookup"><span data-stu-id="ef940-108">The voice, video, and sharing features in Skype for Business Web App require a Microsoft ActiveX control that is used as a plugin by the user's browser.</span></span> <span data-ttu-id="ef940-109">Можно установить элемент управления ActiveX заранее или запретить пользователям устанавливать его при получении запроса, что происходит при первом использовании Скайп для бизнеса Web App или первый раз, они получают доступ к компонента, который требуется элемент управления ActiveX.</span><span class="sxs-lookup"><span data-stu-id="ef940-109">You can either install the ActiveX control in advance or allow users to install it when prompted, which happens the first time they use Skype for Business Web App or the first time they access a feature that requires the ActiveX control.</span></span>

> [!NOTE]
> <span data-ttu-id="ef940-110">В Скайп для развертываний пограничного сервера Business Server HTTPS обратного прокси-сервер в сети периметра необходим для Скайп для бизнес-приложение Web клиентского доступа.</span><span class="sxs-lookup"><span data-stu-id="ef940-110">In Skype for Business Server Edge Server deployments, an HTTPS reverse proxy in the perimeter network is required for Skype for Business Web App client access.</span></span> <span data-ttu-id="ef940-111">Помимо этого, необходимо опубликовать простые URL-адреса.</span><span class="sxs-lookup"><span data-stu-id="ef940-111">You must also publish simple URLs.</span></span> <span data-ttu-id="ef940-112">Дополнительные сведения см [Параметр копирование обратного прокси-серверы](https://technet.microsoft.com/library/00bc138a-243f-4389-bfa5-9c62fcc95132.aspx) и [требования к DNS для простых URL-адресов в Скайп для Business Server](../../plan-your-deployment/network-requirements/simple-urls.md).</span><span class="sxs-lookup"><span data-stu-id="ef940-112">For details, see [Setting Up Reverse Proxy Servers](https://technet.microsoft.com/library/00bc138a-243f-4389-bfa5-9c62fcc95132.aspx) and [DNS requirements for simple URLs in Skype for Business Server](../../plan-your-deployment/network-requirements/simple-urls.md).</span></span>

## <a name="enable-multi-factor-authentication-for-skype-for-business-web-app"></a><span data-ttu-id="ef940-113">Включение многофакторной проверки подлинности для Скайп для бизнеса Web App</span><span class="sxs-lookup"><span data-stu-id="ef940-113">Enable Multi-Factor Authentication for Skype for Business Web App</span></span>
<span data-ttu-id="ef940-114"><a name="MFA"> </a></span><span class="sxs-lookup"><span data-stu-id="ef940-114"></span></span>

<span data-ttu-id="ef940-115">Скайп для бизнеса Web App и Скайп собраний App поддерживает многофакторной проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="ef940-115">The Skype for Business Web App and Skype Meetings App support multi-factor authentication.</span></span> <span data-ttu-id="ef940-116">В дополнение к имени пользователя и пароля может потребовать дополнительную проверку подлинности методы, такие как смарт-карты или ПИН-коды, для проверки подлинности пользователей, у которых присоединение из внешних сетей, когда выполняют вход в систему Скайп для собраний Business.</span><span class="sxs-lookup"><span data-stu-id="ef940-116">In addition to user name and password, you can require additional authentication methods, such as smart cards or PINs, to authenticate users who are joining from external networks when they sign in to Skype for Business meetings.</span></span> <span data-ttu-id="ef940-117">Можно включить многофакторной проверки подлинности, развертывания сервера федерации службы федерации Active Directory (AD FS), а также включение пассивной проверки подлинности в Скайп для Business Server.</span><span class="sxs-lookup"><span data-stu-id="ef940-117">You can enable multi-factor authentication by deploying Active Directory Federation Service (AD FS) federation server and enabling passive authentication in Skype for Business Server.</span></span> <span data-ttu-id="ef940-118">После настройки AD FS внешние пользователи, попытались присоединиться к Скайп для деловых встреч, изучите AD FS многофакторной проверки подлинности веб-страница, содержащая имя пользователя и пароль вызов вместе с любые дополнительные методы проверки подлинности, которые вы настроены.</span><span class="sxs-lookup"><span data-stu-id="ef940-118">After AD FS is configured, external users who attempt to join Skype for Business meetings are presented with an AD FS multi-factor authentication webpage that contains the user name and password challenge along with any additional authentication methods that you have configured.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ef940-119">Если вы планируете настроить службу федерации Active Directory для многофакторной проверки подлинности, учтите следующие рекомендации.</span><span class="sxs-lookup"><span data-stu-id="ef940-119">The following are important considerations if you plan to configure AD FS for multi-factor authentication:</span></span>

- <span data-ttu-id="ef940-p105">Многофакторная проверка подлинности службы федерации Active Directory действует в том случае, если как участник, так и организатор собрания относятся к одной организации (в том числе с федерацией AD FS). Многофакторная проверка подлинности службы федерации Active Directory не действует для федеративных пользователей Lync, так как веб-инфраструктура сервера Lync не поддерживает такую возможность в настоящий момент.</span><span class="sxs-lookup"><span data-stu-id="ef940-p105">Multi-factor ADFS authentication works if the meeting participant and organizer are both in the same organization or are both from an AD FS federated organization. Multi-factor ADFS authentication does not work for Lync federated users because the Lync server web infrastructure does not currently support it.</span></span>

- <span data-ttu-id="ef940-122">Если вы используете аппаратных балансировщиков нагрузки, включите сохраняемость файлов cookie на подсистемы балансировки нагрузки, чтобы все запросы от Скайп для клиентов, деловых веб-приложения или приложения собраний обрабатывались одним сервером переднего плана.</span><span class="sxs-lookup"><span data-stu-id="ef940-122">If you use hardware load balancers, enable cookie persistence on the load balancers so that all requests from the Skype for Business Web App or Meetings App clients are handled by the same Front End Server.</span></span>

- <span data-ttu-id="ef940-123">При создании доверия с проверяющей стороной между Скайп для серверов Business Server и служб AD FS назначение маркеров жизненного, являющийся достаточно охватывать Максимальная длина вашей Скайп для деловых встреч.</span><span class="sxs-lookup"><span data-stu-id="ef940-123">When you establish a relying party trust between Skype for Business Server and AD FS servers, assign a token life that is long enough to span the maximum length of your Skype for Business meetings.</span></span> <span data-ttu-id="ef940-124">Как правило, 240 минут бывает достаточно.</span><span class="sxs-lookup"><span data-stu-id="ef940-124">Typically, a token life of 240 minutes is sufficient.</span></span>

- <span data-ttu-id="ef940-125">Эта конфигурация не действует для мобильных клиентов Lync.</span><span class="sxs-lookup"><span data-stu-id="ef940-125">This configuration does not apply to Lync mobile clients.</span></span>

### <a name="configure-multi-factor-authentication"></a><span data-ttu-id="ef940-126">Настройка многофакторной проверки подлинности</span><span class="sxs-lookup"><span data-stu-id="ef940-126">Configure Multi-Factor Authentication</span></span>

1. <span data-ttu-id="ef940-127">Установите роль сервера федерации служб федерации Active Directory.</span><span class="sxs-lookup"><span data-stu-id="ef940-127">Install an AD FS federation server role.</span></span> <span data-ttu-id="ef940-128">Дополнительные сведения можно найти в [Active Directory Federation Services 2.0 руководство по развертыванию](https://go.microsoft.com/fwlink/p/?linkid=267511)</span><span class="sxs-lookup"><span data-stu-id="ef940-128">For details, see the [Active Directory Federation Services 2.0 Deployment Guide](https://go.microsoft.com/fwlink/p/?linkid=267511)</span></span>

2. <span data-ttu-id="ef940-129">Создайте сертификаты для служб федерации Active Directory.</span><span class="sxs-lookup"><span data-stu-id="ef940-129">Create certificates for AD FS.</span></span> <span data-ttu-id="ef940-130">Для получения дополнительных сведений см раздел [«Сертификаты сервера федерации»](https://go.microsoft.com/fwlink/p/?LinkId=285376) планирование для и развертывание службы федерации Active Directory для использования с разделом единого входа.</span><span class="sxs-lookup"><span data-stu-id="ef940-130">For more information, see ["Federation server certificates"](https://go.microsoft.com/fwlink/p/?LinkId=285376) section of the Plan for and deploy AD FS for use with single sign-on topic.</span></span>

3. <span data-ttu-id="ef940-131">Интерфейс командной строки Windows PowerShell выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="ef940-131">From the Windows PowerShell command-line interface, run the following command:</span></span>

    ```
    add-pssnapin Microsoft.Adfs.powershell
    ```

4. <span data-ttu-id="ef940-132">Установите партнерство, выполнив следующую команду:</span><span class="sxs-lookup"><span data-stu-id="ef940-132">Establish a partnership by running the following command:</span></span>

    ```
    Add-ADFSRelyingPartyTrust -Name ContosoApp -MetadataURL https://lyncpool.contoso.com/passiveauth/federationmetadata/2007-06/federationmetadata.xml
    ```

5. <span data-ttu-id="ef940-133">Настройте следующие правила проверяющей стороны:</span><span class="sxs-lookup"><span data-stu-id="ef940-133">Set the following relying party rules:</span></span>

    ```
   $IssuanceAuthorizationRules = '@RuleTemplate = "AllowAllAuthzRule" => issue(Type = "http://schemas.contoso.com/authorization/claims/permit", Value = "true");'$IssuanceTransformRules = '@RuleTemplate = "PassThroughClaims" @RuleName = "Sid" c:[Type == "http://schemas.contoso.com/ws/2008/06/identity/claims/primarysid"]=> issue(claim = c);'
   Set-ADFSRelyingPartyTrust -TargetName ContosoApp -IssuanceAuthorizationRules $IssuanceAuthorizationRules -IssuanceTransformRules $IssuanceTransformRules
   Set-CsWebServiceConfiguration -UseWsFedPassiveAuth $true -WsFedPassiveMetadataUri https://dc.contoso.com/federationmetadata/2007-06/federationmetadata.xml
   ```

## <a name="disable-branchcache"></a><span data-ttu-id="ef940-134">Отключить функцию BranchCache </span><span class="sxs-lookup"><span data-stu-id="ef940-134">Disable BranchCache</span></span>
<span data-ttu-id="ef940-135"><a name="MFA"> </a></span><span class="sxs-lookup"><span data-stu-id="ef940-135"></span></span>

<span data-ttu-id="ef940-136">Компонент BranchCache в Windows 7 и Windows Server 2008 R2 могут мешать Скайп для веб-компонентов Business Web App.</span><span class="sxs-lookup"><span data-stu-id="ef940-136">The BranchCache feature in Windows 7 and Windows Server 2008 R2 can interfere with Skype for Business Web App web components.</span></span> <span data-ttu-id="ef940-137">Чтобы предотвратить проблемы для Скайп для пользователей Business Web App, убедитесь, что не включен компонент BranchCache.</span><span class="sxs-lookup"><span data-stu-id="ef940-137">To prevent issues for Skype for Business Web App users, make sure that BranchCache is not enabled.</span></span>

<span data-ttu-id="ef940-138">Для получения дополнительных сведений об отключении BranchCache можно найти [В руководстве по развертыванию BranchCache](https://docs.microsoft.com/windows-server/networking/branchcache/deploy/branchcache-deployment-guide).</span><span class="sxs-lookup"><span data-stu-id="ef940-138">For details about disabling BranchCache, see the [BranchCache Deployment Guide](https://docs.microsoft.com/windows-server/networking/branchcache/deploy/branchcache-deployment-guide).</span></span>

## <a name="verifying-skype-for-business-web-app-deployment"></a><span data-ttu-id="ef940-139">Проверка Скайп по развертыванию Web App</span><span class="sxs-lookup"><span data-stu-id="ef940-139">Verifying Skype for Business Web App Deployment</span></span>
<span data-ttu-id="ef940-140"><a name="MFA"> </a></span><span class="sxs-lookup"><span data-stu-id="ef940-140"></span></span>

<span data-ttu-id="ef940-141">С помощью командлета Test-CsUcwaConference вы можете проверить возможность участия двух тестовых пользователей в конференции с использованием веб-API объединенных коммуникаций (UCWA).</span><span class="sxs-lookup"><span data-stu-id="ef940-141">You can use the Test-CsUcwaConference cmdlet to verify that a pair of test users can participate in a conference using the Unified Communications Web API (UCWA).</span></span> <span data-ttu-id="ef940-142">Подробные сведения о этот командлет [Test-CsUcwaConference](https://docs.microsoft.com/powershell/module/skype/test-csucwaconference?view=skype-ps) в Скайп для документации по консоли управления Business Server см.</span><span class="sxs-lookup"><span data-stu-id="ef940-142">For details about this cmdlet, see [Test-CsUcwaConference](https://docs.microsoft.com/powershell/module/skype/test-csucwaconference?view=skype-ps) in the Skype for Business Server Management Shell documentation.</span></span>

## <a name="troubleshooting-plug-in-installation-on-windows-server-2008-r2"></a><span data-ttu-id="ef940-143">Устранение неполадок при установке подключаемого модуля на Windows Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="ef940-143">Troubleshooting Plug-in Installation on Windows Server 2008 R2</span></span>
<span data-ttu-id="ef940-144"><a name="MFA"> </a></span><span class="sxs-lookup"><span data-stu-id="ef940-144"></span></span>

<span data-ttu-id="ef940-145">Если не удается установить подключаемый модуль на компьютере под управлением Windows Server 2008 R2, может потребоваться изменить параметр безопасности Internet Explorer или реестра DisableMSI.</span><span class="sxs-lookup"><span data-stu-id="ef940-145">If installation of the plug-in fails on a computer running Windows Server 2008 R2, you may need to modify the Internet Explorer security setting or the DisableMSI registry key setting.</span></span>

### <a name="modify-the-security-setting-in-internet-explorer"></a><span data-ttu-id="ef940-146">Изменение параметра безопасности в Internet Explorer</span><span class="sxs-lookup"><span data-stu-id="ef940-146">Modify the security setting in Internet Explorer</span></span>

1. <span data-ttu-id="ef940-147">Откройте Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="ef940-147">Open Internet Explorer.</span></span>

2. <span data-ttu-id="ef940-148">В меню **Сервис** выберите пункт **Свойства обозревателя** и перейдите на вкладку **Дополнительно**.</span><span class="sxs-lookup"><span data-stu-id="ef940-148">Click **Tools**, click **Internet Options**, and then click **Advanced**.</span></span>

3. <span data-ttu-id="ef940-149">Перейдите к разделу **Безопасность**.</span><span class="sxs-lookup"><span data-stu-id="ef940-149">Scroll down to the **Security** section.</span></span>

4. <span data-ttu-id="ef940-150">Снимите флажок **Не сохранять зашифрованные страницы на диск** и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="ef940-150">Clear **Do not save encrypted pages to disk**, and then click **OK**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="ef940-151">Если выбрано, этот параметр также приведет к ошибке при попытке загрузки вложения из Скайп для бизнеса Web App.</span><span class="sxs-lookup"><span data-stu-id="ef940-151">If selected, this setting will also cause an error when trying to download an attachment from Skype for Business Web App.</span></span>

5. <span data-ttu-id="ef940-p111">Присоединитесь к собранию повторно. Подключаемый модуль должен загрузиться без ошибок.</span><span class="sxs-lookup"><span data-stu-id="ef940-p111">Rejoin the meeting. The plug-in should download without errors.</span></span>

### <a name="modify-the-disablemsi-registry-setting"></a><span data-ttu-id="ef940-154">Изменение параметра реестра DisableMSI</span><span class="sxs-lookup"><span data-stu-id="ef940-154">Modify the DisableMSI Registry setting</span></span>

1. <span data-ttu-id="ef940-155">В меню **Пуск** выберите пункт **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="ef940-155">Click **Start**, and then click **Run**.</span></span>

2. <span data-ttu-id="ef940-156">Чтобы открыть редактор реестра, введите команду **regedit**.</span><span class="sxs-lookup"><span data-stu-id="ef940-156">To access the Registry Editor, type **regedit**.</span></span>

3. <span data-ttu-id="ef940-157">Перейдите к разделу HKEY_LOCAL_MACHINE\Software\Policies\Microsoft\Windows\Installer.</span><span class="sxs-lookup"><span data-stu-id="ef940-157">Navigate to HKEY_LOCAL_MACHINE\Software\Policies\Microsoft\Windows\Installer.</span></span>

4. <span data-ttu-id="ef940-158">Измените или добавьте параметр реестра DisableMSI типа REG_DWORD и задайте для него значение 0.</span><span class="sxs-lookup"><span data-stu-id="ef940-158">Edit or add the DisableMSI registry key of type REG_DWORD and set it to 0.</span></span>

5. <span data-ttu-id="ef940-159">Присоединитесь к собранию повторно.</span><span class="sxs-lookup"><span data-stu-id="ef940-159">Rejoin the meeting.</span></span>

## <a name="enable-skype-meetings-app-to-replace-skype-for-business-web-app-optional-skype-for-business-server-2015-only"></a><span data-ttu-id="ef940-160">Включение приложения Скайп собраний для замены Скайп для бизнеса веб-приложения (необязательно, Скайп для Business Server 2015 только)</span><span class="sxs-lookup"><span data-stu-id="ef940-160">Enable Skype Meetings App to replace Skype for Business Web App (Optional, Skype for Business Server 2015 only)</span></span>
<span data-ttu-id="ef940-161"><a name="SMA_Enable"> </a></span><span class="sxs-lookup"><span data-stu-id="ef940-161"></span></span>

<span data-ttu-id="ef940-162">Эта процедура является необязательной и применяется к Скайп для Business Server 2015 накопительным пакетом обновления 5 и более поздних версий.</span><span class="sxs-lookup"><span data-stu-id="ef940-162">This procedure is optional, and applies to Skype for Business Server 2015 CU5 and later.</span></span> <span data-ttu-id="ef940-163">Если он не используется, для присоединения к собраниям с помощью Скайп для бизнеса Web App будет предоставляться внешних пользователей.</span><span class="sxs-lookup"><span data-stu-id="ef940-163">If you do not use it, external users will continue to join meetings using Skype for Business Web App.</span></span>

### <a name="enable-simplified-meeting-join-and-skype-meetings-app"></a><span data-ttu-id="ef940-164">Включение упрощенного присоединения к собранию и приложения для собраний Skype</span><span class="sxs-lookup"><span data-stu-id="ef940-164">Enable simplified meeting join and Skype Meetings App</span></span>

1. <span data-ttu-id="ef940-165">При включении доступа для доставки содержимого сети (CDN), пользователи будут иметь возможность подключения к сети CDN Интернет-версия и получить приложение Скайп собраний и будет использовать упрощенный интерфейса присоединения к собранию.</span><span class="sxs-lookup"><span data-stu-id="ef940-165">When you enable access to the Content Delivery Network (CDN), users will have the ability to connect to CDN online and get Skype Meetings App, and will use the simplified meeting join experience.</span></span>

   ```
   Set-CsWebServiceConfiguration -MeetingUxUseCdn $True
   ```

2. <span data-ttu-id="ef940-166">Разрешить клиенту со стороны ведение журнала телеметрии из собрания присоединиться к веб-страницу или приложение собраний Скайп отправку для серверов Microsoft (команду Параметры по умолчанию значение false).</span><span class="sxs-lookup"><span data-stu-id="ef940-166">Allow client side logging telemetry from the meeting join web page or the Skype Meetings App to be sent to Microsoft servers (the command defaults to false).</span></span>

   ```
   Set-CsWebServiceConfiguration -MeetingUxEnableTelemetry $True
   ```

    <span data-ttu-id="ef940-167">Сведения, отправленные Microsoft, строго соответствуют [рекомендациям по сбору данных в Skype для бизнеса](https://docs.microsoft.com/skypeforbusiness/legal-and-regulatory/data-collection-practices).</span><span class="sxs-lookup"><span data-stu-id="ef940-167">Information sent to Microsoft is in strict compliance with [Skype for Business data collection practices](https://docs.microsoft.com/skypeforbusiness/legal-and-regulatory/data-collection-practices).</span></span>

3. <span data-ttu-id="ef940-168">Задайте время ожидания перед попадающих вернуться к локально размещаемого Скайп для бизнес-приложение Web программой Если CDN недоступен.</span><span class="sxs-lookup"><span data-stu-id="ef940-168">Set the timeout before fall back to the locally hosted Skype for Business Web App experience if CDN isn't available.</span></span> <span data-ttu-id="ef940-169">По умолчанию установлено значение 6 с.</span><span class="sxs-lookup"><span data-stu-id="ef940-169">The default value is 6 seconds.</span></span> <span data-ttu-id="ef940-170">Если установлено значение 0, никакого времени ожидания не будет.</span><span class="sxs-lookup"><span data-stu-id="ef940-170">If this value is set to 0, there will be no timeout.</span></span>

   ```
   Set-CsWebServiceConfiguration -JoinLauncherCdnTimeout (New-TimeSpan -Seconds 10)
   ```

## <a name="see-also"></a><span data-ttu-id="ef940-171">Были ли эти инструкции полезны? Если да, укажите это в конце статьи. Если нет, сообщите нам о недочетах, и мы постараемся найти решение.</span><span class="sxs-lookup"><span data-stu-id="ef940-171">See also</span></span>
<span data-ttu-id="ef940-172"><a name="SMA_Enable"> </a></span><span class="sxs-lookup"><span data-stu-id="ef940-172"></span></span>

[<span data-ttu-id="ef940-173">Планирование для клиентов собрания (веб-приложения и приложения собрания)</span><span class="sxs-lookup"><span data-stu-id="ef940-173">Plan for Meetings clients (Web App and Meetings App)</span></span>](../../plan-your-deployment/clients-and-devices/meetings-clients.md)

[<span data-ttu-id="ef940-174">Настройка собрания страницы присоединения к в Скайп для Business Server</span><span class="sxs-lookup"><span data-stu-id="ef940-174">Configure the meeting join page in Skype for Business Server</span></span>](../../manage/conferencing/meeting-join-page.md)

[<span data-ttu-id="ef940-175">Заявление о конфиденциальности Microsoft Online Services</span><span class="sxs-lookup"><span data-stu-id="ef940-175">Microsoft Online Services Privacy Statement</span></span>](https://www.microsoft.com/en-us/privacystatement/OnlineServices/Default.aspx)

[<span data-ttu-id="ef940-176">Условия лицензионного соглашения и документация</span><span class="sxs-lookup"><span data-stu-id="ef940-176">Licensing Terms and Documentation</span></span>](http://www.microsoftvolumelicensing.com/DocumentSearch.aspx?Mode=3&amp;amp;DocumentTypeId=31)