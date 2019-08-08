---
title: Развертывание загружаемых веб-клиентов в Skype для бизнеса Server
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: PhillipGarding
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b6301e98-051c-4e4b-8e10-ec922a8f508a
description: 'Сводка: развертывание приложения Skype для бизнеса Web App и собраний Skype, которое используется в Skype для бизнеса.'
ms.openlocfilehash: 8f2449fde2f270834bda50602fe163829f3b725f
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/07/2019
ms.locfileid: "36234397"
---
# <a name="deploy-web-downloadable-clients-in-skype-for-business-server"></a><span data-ttu-id="0a0d0-103">Развертывание загружаемых веб-клиентов в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="0a0d0-103">Deploy Web downloadable clients in Skype for Business Server</span></span>

<span data-ttu-id="0a0d0-104">**Сводка:** Развертывание приложения Skype для бизнеса 2015 веб-приложения и собраний Skype, которое используется в Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="0a0d0-104">**Summary:** Deploy the Skype for Business 2015 Web App and Skype Meetings App used with Skype for Business Server.</span></span>

<span data-ttu-id="0a0d0-105">Skype для бизнеса Web App — это веб-клиент служб IIS, установленный на сервере, на котором работает Skype для бизнеса Server, и по умолчанию он развертывается по запросу для пользователей собраний, у которых еще нет клиента Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="0a0d0-105">Skype for Business Web App is an Internet Information Services (IIS) web client that is installed on the server running Skype for Business Server and by default it is deployed on demand to meeting users who do not already have the Skype for Business client.</span></span> <span data-ttu-id="0a0d0-106">Эти пользователи собраний чаще всего, чем подключение к сети извне.</span><span class="sxs-lookup"><span data-stu-id="0a0d0-106">These meeting users are more often than not connecting from outside your network.</span></span> <span data-ttu-id="0a0d0-107">Каждый раз, когда пользователь щелкает URL-адрес собрания, но на нем не установлен клиент Skype для бизнеса, пользователю предоставляется возможность присоединиться к собранию с помощью последней версии Skype для бизнеса Web App, приложения для собраний Skype или Skype для бизнеса для Mac.</span><span class="sxs-lookup"><span data-stu-id="0a0d0-107">Whenever a user clicks a meeting URL but does not have the Skype for Business client installed, the user is presented with the option to join the meeting by using the latest version of Skype for Business Web App, Skype Meetings App, or Skype for Business for Mac.</span></span>

<span data-ttu-id="0a0d0-108">Функции голосового и видеосвязи в Skype для бизнеса Web App требуют наличия элемента управления Microsoft ActiveX, который используется в качестве подключаемого модуля браузера пользователя.</span><span class="sxs-lookup"><span data-stu-id="0a0d0-108">The voice, video, and sharing features in Skype for Business Web App require a Microsoft ActiveX control that is used as a plugin by the user's browser.</span></span> <span data-ttu-id="0a0d0-109">Вы можете либо установить элемент ActiveX заранее, либо разрешить пользователям устанавливать его при появлении соответствующего запроса, что происходит при первом использовании Skype для бизнеса Web App или при первом доступе к функции, для которой требуется элемент ActiveX.</span><span class="sxs-lookup"><span data-stu-id="0a0d0-109">You can either install the ActiveX control in advance or allow users to install it when prompted, which happens the first time they use Skype for Business Web App or the first time they access a feature that requires the ActiveX control.</span></span>

> [!NOTE]
> <span data-ttu-id="0a0d0-110">В развертывании приложения пограничного сервера в Skype для бизнеса Server требуется обратный прокси-сервер HTTPS в демилитаризованной зоне, необходимый для доступа клиента Skype для бизнеса Web App.</span><span class="sxs-lookup"><span data-stu-id="0a0d0-110">In Skype for Business Server Edge Server deployments, an HTTPS reverse proxy in the perimeter network is required for Skype for Business Web App client access.</span></span> <span data-ttu-id="0a0d0-111">Помимо этого, необходимо опубликовать простые URL-адреса.</span><span class="sxs-lookup"><span data-stu-id="0a0d0-111">You must also publish simple URLs.</span></span> <span data-ttu-id="0a0d0-112">Подробности можно найти в разделе [Настройка обратных прокси-серверов](https://technet.microsoft.com/library/00bc138a-243f-4389-bfa5-9c62fcc95132.aspx) и [требований DNS к простым URL-адресам в Skype для бизнеса Server](../../plan-your-deployment/network-requirements/simple-urls.md).</span><span class="sxs-lookup"><span data-stu-id="0a0d0-112">For details, see [Setting Up Reverse Proxy Servers](https://technet.microsoft.com/library/00bc138a-243f-4389-bfa5-9c62fcc95132.aspx) and [DNS requirements for simple URLs in Skype for Business Server](../../plan-your-deployment/network-requirements/simple-urls.md).</span></span>

## <a name="enable-multi-factor-authentication-for-skype-for-business-web-app"></a><span data-ttu-id="0a0d0-113">Включение многофакторной проверки подлинности для Skype для бизнеса Web App</span><span class="sxs-lookup"><span data-stu-id="0a0d0-113">Enable Multi-Factor Authentication for Skype for Business Web App</span></span>
<span data-ttu-id="0a0d0-114"><a name="MFA"> </a></span><span class="sxs-lookup"><span data-stu-id="0a0d0-114"></span></span>

<span data-ttu-id="0a0d0-115">Веб-приложение Skype для бизнеса, приложение "собрания Skype" и Skype для бизнеса для Mac поддерживают многофакторную проверку подлинности.</span><span class="sxs-lookup"><span data-stu-id="0a0d0-115">Skype for Business Web App,  Skype Meetings App, and Skype for Business for Mac support multi-factor authentication.</span></span> <span data-ttu-id="0a0d0-116">Помимо имени пользователя и пароля, для проверки подлинности пользователей, присоединяющихся к собраниям Skype для бизнеса, вы можете потребовать дополнительных способов проверки подлинности, например смарт-карт или контактов.</span><span class="sxs-lookup"><span data-stu-id="0a0d0-116">In addition to user name and password, you can require additional authentication methods, such as smart cards or PINs, to authenticate users who are joining from external networks when they sign in to Skype for Business meetings.</span></span> <span data-ttu-id="0a0d0-117">Вы можете включить многофакторную проверку подлинности, развернув сервер федерации служб федерации Active Directory (AD FS) и включив пассивную проверку подлинности в Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="0a0d0-117">You can enable multi-factor authentication by deploying Active Directory Federation Service (AD FS) federation server and enabling passive authentication in Skype for Business Server.</span></span> <span data-ttu-id="0a0d0-118">После настройки службы AD FS внешние пользователи, пытающиеся присоединиться к собраниям в Skype для бизнеса, будут представлены с помощью веб-страницы многофакторной проверки подлинности AD FS, которая содержит имя пользователя и пароль, а также дополнительные способы проверки подлинности, которые вы настроен.</span><span class="sxs-lookup"><span data-stu-id="0a0d0-118">After AD FS is configured, external users who attempt to join Skype for Business meetings are presented with an AD FS multi-factor authentication webpage that contains the user name and password challenge along with any additional authentication methods that you have configured.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="0a0d0-119">Если вы планируете настроить службу федерации Active Directory для многофакторной проверки подлинности, учтите следующие рекомендации.</span><span class="sxs-lookup"><span data-stu-id="0a0d0-119">The following are important considerations if you plan to configure AD FS for multi-factor authentication:</span></span>

- <span data-ttu-id="0a0d0-p105">Многофакторная проверка подлинности службы федерации Active Directory действует в том случае, если как участник, так и организатор собрания относятся к одной организации (в том числе с федерацией AD FS). Многофакторная проверка подлинности службы федерации Active Directory не действует для федеративных пользователей Lync, так как веб-инфраструктура сервера Lync не поддерживает такую возможность в настоящий момент.</span><span class="sxs-lookup"><span data-stu-id="0a0d0-p105">Multi-factor ADFS authentication works if the meeting participant and organizer are both in the same organization or are both from an AD FS federated organization. Multi-factor ADFS authentication does not work for Lync federated users because the Lync server web infrastructure does not currently support it.</span></span>

- <span data-ttu-id="0a0d0-122">Если вы используете подсистемы балансировки нагрузки для оборудования, включите сохраняемость файлов cookie для подсистем балансировки нагрузки, чтобы все запросы из клиентов приложений Skype для бизнеса Web App или собраний обрабатывались на одном и том же внешнем сервере.</span><span class="sxs-lookup"><span data-stu-id="0a0d0-122">If you use hardware load balancers, enable cookie persistence on the load balancers so that all requests from the Skype for Business Web App or Meetings App clients are handled by the same Front End Server.</span></span>

- <span data-ttu-id="0a0d0-123">Если вы устанавливаете отношение доверия проверяющей стороны между серверами Skype для бизнеса Server и AD FS, назначьте жизненный цикл, достаточно длинный, чтобы занимать максимальную длину собраний Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="0a0d0-123">When you establish a relying party trust between Skype for Business Server and AD FS servers, assign a token life that is long enough to span the maximum length of your Skype for Business meetings.</span></span> <span data-ttu-id="0a0d0-124">Как правило, 240 минут бывает достаточно.</span><span class="sxs-lookup"><span data-stu-id="0a0d0-124">Typically, a token life of 240 minutes is sufficient.</span></span>

- <span data-ttu-id="0a0d0-125">Эта конфигурация не действует для мобильных клиентов Lync.</span><span class="sxs-lookup"><span data-stu-id="0a0d0-125">This configuration does not apply to Lync mobile clients.</span></span>

### <a name="configure-multi-factor-authentication"></a><span data-ttu-id="0a0d0-126">Настройка многофакторной проверки подлинности</span><span class="sxs-lookup"><span data-stu-id="0a0d0-126">Configure Multi-Factor Authentication</span></span>

1. <span data-ttu-id="0a0d0-127">Установите роль сервера федерации служб федерации Active Directory.</span><span class="sxs-lookup"><span data-stu-id="0a0d0-127">Install an AD FS federation server role.</span></span> <span data-ttu-id="0a0d0-128">Дополнительные сведения можно найти в [руководстве по развертыванию служб федерации Active Directory 2,0](https://go.microsoft.com/fwlink/p/?linkid=267511)</span><span class="sxs-lookup"><span data-stu-id="0a0d0-128">For details, see the [Active Directory Federation Services 2.0 Deployment Guide](https://go.microsoft.com/fwlink/p/?linkid=267511)</span></span>

2. <span data-ttu-id="0a0d0-129">Создайте сертификаты для служб федерации Active Directory.</span><span class="sxs-lookup"><span data-stu-id="0a0d0-129">Create certificates for AD FS.</span></span> <span data-ttu-id="0a0d0-130">Дополнительные сведения можно найти в разделе ["сертификаты серверов федерации"](https://go.microsoft.com/fwlink/p/?LinkId=285376) плана и развертывания AD FS для использования с одним разделом входа.</span><span class="sxs-lookup"><span data-stu-id="0a0d0-130">For more information, see ["Federation server certificates"](https://go.microsoft.com/fwlink/p/?LinkId=285376) section of the Plan for and deploy AD FS for use with single sign-on topic.</span></span>

3. <span data-ttu-id="0a0d0-131">В интерфейсе командной строки Windows PowerShell выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="0a0d0-131">From the Windows PowerShell command-line interface, run the following command:</span></span>

    ```
    add-pssnapin Microsoft.Adfs.powershell
    ```

4. <span data-ttu-id="0a0d0-132">Установите партнерство, выполнив следующую команду:</span><span class="sxs-lookup"><span data-stu-id="0a0d0-132">Establish a partnership by running the following command:</span></span>

    ```
    Add-ADFSRelyingPartyTrust -Name ContosoApp -MetadataURL https://lyncpool.contoso.com/passiveauth/federationmetadata/2007-06/federationmetadata.xml
    ```

5. <span data-ttu-id="0a0d0-133">Настройте следующие правила проверяющей стороны:</span><span class="sxs-lookup"><span data-stu-id="0a0d0-133">Set the following relying party rules:</span></span>

    ```
   $IssuanceAuthorizationRules = '@RuleTemplate = "AllowAllAuthzRule" => issue(Type = "http://schemas.contoso.com/authorization/claims/permit", Value = "true");'$IssuanceTransformRules = '@RuleTemplate = "PassThroughClaims" @RuleName = "Sid" c:[Type == "http://schemas.contoso.com/ws/2008/06/identity/claims/primarysid"]=> issue(claim = c);'
   Set-ADFSRelyingPartyTrust -TargetName ContosoApp -IssuanceAuthorizationRules $IssuanceAuthorizationRules -IssuanceTransformRules $IssuanceTransformRules
   Set-CsWebServiceConfiguration -UseWsFedPassiveAuth $true -WsFedPassiveMetadataUri https://dc.contoso.com/federationmetadata/2007-06/federationmetadata.xml
   ```

## <a name="disable-branchcache"></a><span data-ttu-id="0a0d0-134">Отключить функцию BranchCache </span><span class="sxs-lookup"><span data-stu-id="0a0d0-134">Disable BranchCache</span></span>
<span data-ttu-id="0a0d0-135"><a name="MFA"> </a></span><span class="sxs-lookup"><span data-stu-id="0a0d0-135"></span></span>

<span data-ttu-id="0a0d0-136">Функция BranchCache в Windows 7 и Windows Server 2008 R2 может повлиять на веб-компоненты Skype для бизнеса Web App.</span><span class="sxs-lookup"><span data-stu-id="0a0d0-136">The BranchCache feature in Windows 7 and Windows Server 2008 R2 can interfere with Skype for Business Web App web components.</span></span> <span data-ttu-id="0a0d0-137">Чтобы предотвратить проблемы для пользователей Skype для бизнеса Web App, убедитесь, что служба BranchCache не включена.</span><span class="sxs-lookup"><span data-stu-id="0a0d0-137">To prevent issues for Skype for Business Web App users, make sure that BranchCache is not enabled.</span></span>

<span data-ttu-id="0a0d0-138">Подробнее об отключении BranchCache можно узнать в [руководстве по развертыванию BranchCache](https://docs.microsoft.com/windows-server/networking/branchcache/deploy/branchcache-deployment-guide).</span><span class="sxs-lookup"><span data-stu-id="0a0d0-138">For details about disabling BranchCache, see the [BranchCache Deployment Guide](https://docs.microsoft.com/windows-server/networking/branchcache/deploy/branchcache-deployment-guide).</span></span>

## <a name="verifying-skype-for-business-web-app-deployment"></a><span data-ttu-id="0a0d0-139">Проверка развертывания Skype для бизнеса Web App</span><span class="sxs-lookup"><span data-stu-id="0a0d0-139">Verifying Skype for Business Web App Deployment</span></span>
<span data-ttu-id="0a0d0-140"><a name="MFA"> </a></span><span class="sxs-lookup"><span data-stu-id="0a0d0-140"></span></span>

<span data-ttu-id="0a0d0-141">С помощью командлета Test-CsUcwaConference вы можете проверить возможность участия двух тестовых пользователей в конференции с использованием веб-API объединенных коммуникаций (UCWA).</span><span class="sxs-lookup"><span data-stu-id="0a0d0-141">You can use the Test-CsUcwaConference cmdlet to verify that a pair of test users can participate in a conference using the Unified Communications Web API (UCWA).</span></span> <span data-ttu-id="0a0d0-142">Подробные сведения об этом командлете можно найти в разделе [Test-ксукваконференце](https://docs.microsoft.com/powershell/module/skype/test-csucwaconference?view=skype-ps) в документации по среде управления в Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="0a0d0-142">For details about this cmdlet, see [Test-CsUcwaConference](https://docs.microsoft.com/powershell/module/skype/test-csucwaconference?view=skype-ps) in the Skype for Business Server Management Shell documentation.</span></span>

## <a name="troubleshooting-plug-in-installation-on-windows-server-2008-r2"></a><span data-ttu-id="0a0d0-143">Устранение неполадок при установке модулей в Windows Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="0a0d0-143">Troubleshooting Plug-in Installation on Windows Server 2008 R2</span></span>
<span data-ttu-id="0a0d0-144"><a name="MFA"> </a></span><span class="sxs-lookup"><span data-stu-id="0a0d0-144"></span></span>

<span data-ttu-id="0a0d0-145">Если установка надстройки завершается сбоем на компьютере под управлением Windows Server 2008 R2, возможно, потребуется изменить параметр безопасности Internet Explorer или параметр раздела реестра Дисаблемси.</span><span class="sxs-lookup"><span data-stu-id="0a0d0-145">If installation of the plug-in fails on a computer running Windows Server 2008 R2, you may need to modify the Internet Explorer security setting or the DisableMSI registry key setting.</span></span>

### <a name="modify-the-security-setting-in-internet-explorer"></a><span data-ttu-id="0a0d0-146">Изменение параметра безопасности в Internet Explorer</span><span class="sxs-lookup"><span data-stu-id="0a0d0-146">Modify the security setting in Internet Explorer</span></span>

1. <span data-ttu-id="0a0d0-147">Откройте Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="0a0d0-147">Open Internet Explorer.</span></span>

2. <span data-ttu-id="0a0d0-148">В меню **Сервис** выберите пункт **Свойства обозревателя** и перейдите на вкладку **Дополнительно**.</span><span class="sxs-lookup"><span data-stu-id="0a0d0-148">Click **Tools**, click **Internet Options**, and then click **Advanced**.</span></span>

3. <span data-ttu-id="0a0d0-149">Перейдите к разделу **Безопасность**.</span><span class="sxs-lookup"><span data-stu-id="0a0d0-149">Scroll down to the **Security** section.</span></span>

4. <span data-ttu-id="0a0d0-150">Снимите флажок **Не сохранять зашифрованные страницы на диск** и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="0a0d0-150">Clear **Do not save encrypted pages to disk**, and then click **OK**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="0a0d0-151">Если этот параметр установлен, при попытке загрузить вложение из Skype для бизнеса Web App может возникнуть ошибка.</span><span class="sxs-lookup"><span data-stu-id="0a0d0-151">If selected, this setting will also cause an error when trying to download an attachment from Skype for Business Web App.</span></span>

5. <span data-ttu-id="0a0d0-p111">Присоединитесь к собранию повторно. Подключаемый модуль должен загрузиться без ошибок.</span><span class="sxs-lookup"><span data-stu-id="0a0d0-p111">Rejoin the meeting. The plug-in should download without errors.</span></span>

### <a name="modify-the-disablemsi-registry-setting"></a><span data-ttu-id="0a0d0-154">Изменение параметра реестра DisableMSI</span><span class="sxs-lookup"><span data-stu-id="0a0d0-154">Modify the DisableMSI Registry setting</span></span>

1. <span data-ttu-id="0a0d0-155">В меню **Пуск** выберите пункт **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="0a0d0-155">Click **Start**, and then click **Run**.</span></span>

2. <span data-ttu-id="0a0d0-156">Чтобы открыть редактор реестра, введите команду **regedit**.</span><span class="sxs-lookup"><span data-stu-id="0a0d0-156">To access the Registry Editor, type **regedit**.</span></span>

3. <span data-ttu-id="0a0d0-157">Перейдите к разделу HKEY_LOCAL_MACHINE\Software\Policies\Microsoft\Windows\Installer.</span><span class="sxs-lookup"><span data-stu-id="0a0d0-157">Navigate to HKEY_LOCAL_MACHINE\Software\Policies\Microsoft\Windows\Installer.</span></span>

4. <span data-ttu-id="0a0d0-158">Измените или добавьте параметр реестра DisableMSI типа REG_DWORD и задайте для него значение 0.</span><span class="sxs-lookup"><span data-stu-id="0a0d0-158">Edit or add the DisableMSI registry key of type REG_DWORD and set it to 0.</span></span>

5. <span data-ttu-id="0a0d0-159">Присоединитесь к собранию повторно.</span><span class="sxs-lookup"><span data-stu-id="0a0d0-159">Rejoin the meeting.</span></span>

## <a name="enable-skype-meetings-app-to-replace-skype-for-business-web-app-optional-skype-for-business-server-2015-only"></a><span data-ttu-id="0a0d0-160">Включение возможности замены Skype для бизнеса Web App приложением "собрания Skype" (необязательно, Skype для бизнеса Server 2015)</span><span class="sxs-lookup"><span data-stu-id="0a0d0-160">Enable Skype Meetings App to replace Skype for Business Web App (Optional, Skype for Business Server 2015 only)</span></span>
<span data-ttu-id="0a0d0-161"><a name="SMA_Enable"> </a></span><span class="sxs-lookup"><span data-stu-id="0a0d0-161"></span></span>

<span data-ttu-id="0a0d0-162">Эта процедура необязательна и применима к Skype для бизнеса Server 2015 CU5 и более поздних версий.</span><span class="sxs-lookup"><span data-stu-id="0a0d0-162">This procedure is optional, and applies to Skype for Business Server 2015 CU5 and later.</span></span> <span data-ttu-id="0a0d0-163">Если вы не используете его, внешние пользователи продолжат присоединяться к собраниям с помощью Skype для бизнеса Web App.</span><span class="sxs-lookup"><span data-stu-id="0a0d0-163">If you do not use it, external users will continue to join meetings using Skype for Business Web App.</span></span>

### <a name="enable-simplified-meeting-join-and-skype-meetings-app"></a><span data-ttu-id="0a0d0-164">Включение упрощенного присоединения к собранию и приложения для собраний Skype</span><span class="sxs-lookup"><span data-stu-id="0a0d0-164">Enable simplified meeting join and Skype Meetings App</span></span>

1. <span data-ttu-id="0a0d0-165">При включении доступа к сети доставки содержимого (CDN) пользователи получат возможность подключаться к CDN Online и получать приложения для собраний Skype (в Windows) и Skype для бизнеса для Mac (на Mac) и использовать упрощенное соединение для собраний.</span><span class="sxs-lookup"><span data-stu-id="0a0d0-165">When you enable access to the Content Delivery Network (CDN), users will have the ability to connect to CDN online and get Skype Meetings App (on Windows) and Skype for Business for Mac (on Mac), and will use the simplified meeting join experience.</span></span>

   ```
   Set-CsWebServiceConfiguration -MeetingUxUseCdn $True
   ```

2. <span data-ttu-id="0a0d0-166">Разрешить отправку журнала на стороне клиента с веб-страницы присоединения к собранию или из приложения "собрания Skype" для отправки на серверы Майкрософт (по умолчанию для команды задано значение "ложь").</span><span class="sxs-lookup"><span data-stu-id="0a0d0-166">Allow client side logging telemetry from the meeting join web page or the Skype Meetings App to be sent to Microsoft servers (the command defaults to false).</span></span>

   ```
   Set-CsWebServiceConfiguration -MeetingUxEnableTelemetry $True
   ```

    <span data-ttu-id="0a0d0-167">Сведения, отправляемые в корпорацию Майкрософт, строго соответствуют рекомендациям по [сбору данных в Skype для бизнеса](https://docs.microsoft.com/skypeforbusiness/legal-and-regulatory/data-collection-practices).</span><span class="sxs-lookup"><span data-stu-id="0a0d0-167">Information sent to Microsoft is in strict compliance with [Skype for Business data collection practices](https://docs.microsoft.com/skypeforbusiness/legal-and-regulatory/data-collection-practices).</span></span>

3. <span data-ttu-id="0a0d0-168">Установите время ожидания перед переходом на локальное веб-приложение Skype для бизнеса, если сеть CDN недоступна.</span><span class="sxs-lookup"><span data-stu-id="0a0d0-168">Set the timeout before fall back to the locally hosted Skype for Business Web App experience if CDN isn't available.</span></span> <span data-ttu-id="0a0d0-169">По умолчанию установлено значение 6 с.</span><span class="sxs-lookup"><span data-stu-id="0a0d0-169">The default value is 6 seconds.</span></span> <span data-ttu-id="0a0d0-170">Если установлено значение 0, никакого времени ожидания не будет.</span><span class="sxs-lookup"><span data-stu-id="0a0d0-170">If this value is set to 0, there will be no timeout.</span></span>

   ```
   Set-CsWebServiceConfiguration -JoinLauncherCdnTimeout (New-TimeSpan -Seconds 10)
   ```

## <a name="see-also"></a><span data-ttu-id="0a0d0-171">См. также</span><span class="sxs-lookup"><span data-stu-id="0a0d0-171">See also</span></span>
<span data-ttu-id="0a0d0-172"><a name="SMA_Enable"> </a></span><span class="sxs-lookup"><span data-stu-id="0a0d0-172"></span></span>

[<span data-ttu-id="0a0d0-173">Планирование клиентов собраний (приложение для веб-приложений и собраний)</span><span class="sxs-lookup"><span data-stu-id="0a0d0-173">Plan for Meetings clients (Web App and Meetings App)</span></span>](../../plan-your-deployment/clients-and-devices/meetings-clients.md)

[<span data-ttu-id="0a0d0-174">Настройка страницы присоединения к собранию в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="0a0d0-174">Configure the meeting join page in Skype for Business Server</span></span>](../../manage/conferencing/meeting-join-page.md)

[<span data-ttu-id="0a0d0-175">Заявление о конфиденциальности Microsoft Online Services</span><span class="sxs-lookup"><span data-stu-id="0a0d0-175">Microsoft Online Services Privacy Statement</span></span>](https://www.microsoft.com/en-us/privacystatement/OnlineServices/Default.aspx)

[<span data-ttu-id="0a0d0-176">Условия лицензионного соглашения и документация</span><span class="sxs-lookup"><span data-stu-id="0a0d0-176">Licensing Terms and Documentation</span></span>](http://www.microsoftvolumelicensing.com/DocumentSearch.aspx?Mode=3&amp;amp;DocumentTypeId=31)
