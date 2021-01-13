---
title: Установка и настройка параметров занятости для Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Strat_SB_Admin
ms.custom: ''
ms.assetid: fb0faac8-ca1c-4abb-9959-d19def294c64
description: Узнайте, как установить и настроить параметры занятости в Skype для бизнеса Server.
ms.openlocfilehash: e1480809eb1f14dd25837d11fd54ed6bb5cac534
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49830809"
---
# <a name="install-and-configure-busy-options-for-skype-for-business-server"></a><span data-ttu-id="79e13-103">Установка и настройка параметров занятости для Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="79e13-103">Install and configure Busy Options for Skype for Business Server</span></span>

<span data-ttu-id="79e13-104">Узнайте, как установить и настроить параметры занятости в Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="79e13-104">Read about how to install and configure Busy Options in Skype for Business Server.</span></span>

<span data-ttu-id="79e13-105">Параметры занятости — это новая политика голосовой почты, представленная в накопительном обновлении за июль 2016 г., которая позволяет настроить обработку входящих вызовов, когда пользователь уже находится в звонках или конференциях или находится на удержании.</span><span class="sxs-lookup"><span data-stu-id="79e13-105">Busy Options is a new voice policy introduced in the July 2016 Cumulative Update that allows you to configure how incoming calls are handled when a user is already in a call or conference or has a call placed on hold.</span></span> <span data-ttu-id="79e13-106">Новые или входящие вызовы можно отклонить с сигналом "занято" или переадлить на голосовую почту.</span><span class="sxs-lookup"><span data-stu-id="79e13-106">New or incoming calls can be rejected with a busy signal or forwarded to voice mail.</span></span>

<span data-ttu-id="79e13-107">Если для организации включены параметры занятости, все пользователи предприятия, как Корпоративная голосовая связь, так и пользователи, не Корпоративная голосовая связь, могут использовать следующие параметры конфигурации:</span><span class="sxs-lookup"><span data-stu-id="79e13-107">If Busy Options is enabled for the organization, all users at the Enterprise, both Enterprise Voice and non-Enterprise Voice users, can use the following configuration options:</span></span>

- <span data-ttu-id="79e13-108">Занят в "Занят". При этом новые входящие вызовы будут отклониться с сигналом "занято", если пользователь занят.</span><span class="sxs-lookup"><span data-stu-id="79e13-108">Busy on Busy - In which new incoming calls will be rejected with a busy signal if the user is busy.</span></span>

- <span data-ttu-id="79e13-109">Голосовая почта в службе "Занято". В которой новые входящие вызовы будут переадад частью голосовой почты, если пользователь занят.</span><span class="sxs-lookup"><span data-stu-id="79e13-109">Voicemail on Busy - In which new incoming calls will be forwarded to voice mail if the user is busy.</span></span>

<span data-ttu-id="79e13-110">Независимо от того, как настроены параметры занятости, пользователям в звонках или конференциях или звонках на удержании не помешает инициировать новые вызовы или конференции.</span><span class="sxs-lookup"><span data-stu-id="79e13-110">Regardless of how their busy options are configured, users in a call or conference, or those with a call on hold, are not prevented from initiating new calls or conferences.</span></span>

<span data-ttu-id="79e13-111">Дополнительные сведения о функции "Параметры занятости" см. в дополнительных сведениях о параметрах занятости [Skype для бизнеса Server.](../../plan-your-deployment/enterprise-voice-solution/busy-options.md)</span><span class="sxs-lookup"><span data-stu-id="79e13-111">For more information about the Busy Options feature, see [Plan for Busy Options for Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/busy-options.md).</span></span>

## <a name="install"></a><span data-ttu-id="79e13-112">Установка</span><span class="sxs-lookup"><span data-stu-id="79e13-112">Install</span></span>

<span data-ttu-id="79e13-113">Убедитесь, что установлена последняя версия Skype для бизнеса Server, а также установлено последнее исправление.</span><span class="sxs-lookup"><span data-stu-id="79e13-113">Make sure you have the latest version of Skype for Business Server installed and that you have installed the most recent patch.</span></span> <span data-ttu-id="79e13-114">Для этого сначала остановите все службы, а затем запустите установщик обновления Skype для бизнеса Server следующим образом:</span><span class="sxs-lookup"><span data-stu-id="79e13-114">To do this, first stop all services, and then run the Skype for Business Server update installer as follows:</span></span>

1. <span data-ttu-id="79e13-115">Запустите Stop-CsWindowsService команды.</span><span class="sxs-lookup"><span data-stu-id="79e13-115">Run the Stop-CsWindowsService command.</span></span>

2. <span data-ttu-id="79e13-116">Запустите установщик SkypeServerUpdateInstaller.exe на каждом сервере переднего сервера в пуле.</span><span class="sxs-lookup"><span data-stu-id="79e13-116">Run the SkypeServerUpdateInstaller.exe installer on each Front End server in a pool.</span></span>

3. <span data-ttu-id="79e13-117">Запустите установщик SkypeServerUpdateInstaller.exe на каждом сервере survivable Branch Server (SBS), если вы хотите обеспечить поддержку отбойной передачи на SBS.</span><span class="sxs-lookup"><span data-stu-id="79e13-117">Run the SkypeServerUpdateInstaller.exe installer on each Survivable Branch Server (SBS), if you want to ensure support for failover on SBS.</span></span>

<span data-ttu-id="79e13-118">Установщик развернет последнюю версию приложения "Параметры занятости".</span><span class="sxs-lookup"><span data-stu-id="79e13-118">The installer will deploy the latest version of the Busy Options application.</span></span> <span data-ttu-id="79e13-119">Однако приложение по умолчанию не включено.</span><span class="sxs-lookup"><span data-stu-id="79e13-119">However, the application is not enabled by default.</span></span> <span data-ttu-id="79e13-120">Чтобы включить приложение, выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="79e13-120">To enable the application, perform the following steps:</span></span>

1. <span data-ttu-id="79e13-121">Запустите [cmdlet Set-CsVoicePolicy,](https://docs.microsoft.com/powershell/module/skype/set-csvoicepolicy?view=skype-ps) чтобы включить параметры занятости глобально, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="79e13-121">Run the [Set-CsVoicePolicy](https://docs.microsoft.com/powershell/module/skype/set-csvoicepolicy?view=skype-ps) cmdlet to globally enable Busy Options as shown in the following example:</span></span>

   ```powershell
   Set-CsVoicePolicy -EnableBusyOptions $true
   ```

2. <span data-ttu-id="79e13-122">Затем, если на сайте есть политика голосовой почты, необходимо включить параметры занятости для политики голосовой почты следующим образом:</span><span class="sxs-lookup"><span data-stu-id="79e13-122">Next, if the site has a voice policy is place, you must enable Busy Options for the voice policy as follows:</span></span>

    <span data-ttu-id="79e13-123">Сначала [запустите get-CsSite,](https://docs.microsoft.com/powershell/module/skype/get-cssite?view=skype-ps) чтобы получить имя сайта:</span><span class="sxs-lookup"><span data-stu-id="79e13-123">First, run [Get-CsSite](https://docs.microsoft.com/powershell/module/skype/get-cssite?view=skype-ps) to retrieve the name of the site:</span></span>

   ```powershell
   Get-CsSite
   ```

    <span data-ttu-id="79e13-124">Используйте значение Identity (например, Site:Redmond1), полученные из Get-CsSite, чтобы получить политику голосовой почты сайта следующим образом:</span><span class="sxs-lookup"><span data-stu-id="79e13-124">Use the Identity value (for example: Site:Redmond1) retrieved from Get-CsSite to retrieve the voice policy of the site as follows:</span></span>

   ```powershell
   Get-CsVoicePolicy -Identity Site:Redmond1
   ```

    <span data-ttu-id="79e13-125">Если для сайта существует политика голосовой почты, запустите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="79e13-125">If a voice policy exists for the site, run the following command:</span></span>

   ```powershell
   Set-CsVoicePolicy -Identity Site:Redmond1 -EnableBusyOptions $true
   ```

3. <span data-ttu-id="79e13-126">Затем запустите cmdlet [New-CsServerApplication,](https://docs.microsoft.com/powershell/module/skype/new-csserverapplication?view=skype-ps) чтобы добавить параметры занятости в список серверных приложений, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="79e13-126">Next, run the [New-CsServerApplication](https://docs.microsoft.com/powershell/module/skype/new-csserverapplication?view=skype-ps) cmdlet to add Busy Options to the list of server applications as shown in the following example:</span></span>

   ```powershell
   New-CsServerApplication -Identity 'Service:Registrar:%FQDN%/BusyOptions' -Uri http://www.microsoft.com/LCS/BusyOptions -Critical $False -Enabled $True -Priority (Get-CsServerApplication -Identity 'Service:Registrar:%FQDN%/UserServices').Priority
   ```

    > [!NOTE]
    > <span data-ttu-id="79e13-127">Необходимо заменить %FQDN% на полное доменное имя определенного пула.</span><span class="sxs-lookup"><span data-stu-id="79e13-127">You must replace %FQDN% with the fully-qualified domain name of a specific pool.</span></span>

4. <span data-ttu-id="79e13-128">Затем запустите cmdlet [Update-CsAdminRole,](https://docs.microsoft.com/powershell/module/skype/update-csadminrole?view=skype-ps) чтобы обновить роли управления доступом на основе ролей (RBAC) для параметров занятости, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="79e13-128">Next, run the [Update-CsAdminRole](https://docs.microsoft.com/powershell/module/skype/update-csadminrole?view=skype-ps) cmdlet to update the Role-based access control (RBAC) roles for the Busy Options cmdlets as shown in the following example:</span></span>

   ```powershell
   Update-CsAdminRole
   ```

5. <span data-ttu-id="79e13-129">Наконец, запустите службы Windows Skype для бизнеса Server на всех серверах переднего сервера во всех пулах, где были установлены и включены параметры занятости, с помощью команды [Start-CsWindowsService:](https://docs.microsoft.com/powershell/module/skype/start-cswindowsservice?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="79e13-129">Finally, start the Skype for Business Server Windows services on all the Front End servers in all the pools where Busy Options was installed and enabled by running the [Start-CsWindowsService](https://docs.microsoft.com/powershell/module/skype/start-cswindowsservice?view=skype-ps) command:</span></span>

   ```powershell
   Start-CsWindowsService
   ```

## <a name="configure"></a><span data-ttu-id="79e13-130">Настройка</span><span class="sxs-lookup"><span data-stu-id="79e13-130">Configure</span></span>

<span data-ttu-id="79e13-131">Чтобы настроить параметры занятости, используйте [cmdlet Set-CsBusyOptions.](https://technet.microsoft.com/library/8ffbb832-3e55-4d6c-9a7c-5ce2df22de2e.aspx)</span><span class="sxs-lookup"><span data-stu-id="79e13-131">To configure Busy Options, use the [Set-CsBusyOptions](https://technet.microsoft.com/library/8ffbb832-3e55-4d6c-9a7c-5ce2df22de2e.aspx) cmdlet.</span></span>

<span data-ttu-id="79e13-132">Например, следующая команда настраивает параметры занятости для пользователя "Ken Myer".</span><span class="sxs-lookup"><span data-stu-id="79e13-132">For example, the following command configures busy options for the user "Ken Myer".</span></span> <span data-ttu-id="79e13-133">В этой конфигурации при любом вызове "Ken Myer" будет возвращен сигнал "занято", когда он уже находится в вызове:</span><span class="sxs-lookup"><span data-stu-id="79e13-133">In this configuration, any call to "Ken Myer" will return a busy signal when he is already in a call:</span></span>

```powershell
Set-CsBusyOptions -Identity "Ken Myer"  -ActionType BusyOnBusy
```

<span data-ttu-id="79e13-134">В следующем примере команда настраивает параметры занятости для пользователя Chrystal Velasquez.</span><span class="sxs-lookup"><span data-stu-id="79e13-134">In the next example, the command configures busy options for the user "Chrystal Velasquez".</span></span> <span data-ttu-id="79e13-135">В этой конфигурации новые входящие вызовы на "Chrystal Velasquez" будут переададации на голосовую почту, когда она уже находится в вызове:</span><span class="sxs-lookup"><span data-stu-id="79e13-135">In this configuration, new incoming calls to "Chrystal Velasquez" will be forwarded to voice mail when she is already in a call:</span></span>

```powershell
Set-CsBusyOptions -Identity "Chrystal Velasquez" -ActionType VoicemailOnBusy
```

<span data-ttu-id="79e13-136">Сведения о конфигурации параметров занятости можно получить с помощью [cmdlet Get-CsBusyOptions.](https://technet.microsoft.com/library/ff0e3b1c-c41d-41e4-9468-0cb057aef9fb.aspx)</span><span class="sxs-lookup"><span data-stu-id="79e13-136">You can retrieve configuration information about Busy Options by using the [Get-CsBusyOptions](https://technet.microsoft.com/library/ff0e3b1c-c41d-41e4-9468-0cb057aef9fb.aspx) cmdlet.</span></span> <span data-ttu-id="79e13-137">В следующем примере возвращается параметр "Параметры занятости" для параметра "KenMyer@Contoso.com":</span><span class="sxs-lookup"><span data-stu-id="79e13-137">The following example returns the Busy Options setting for "KenMyer@Contoso.com":</span></span>

```powershell
Get-CsBusyOptions -Identity sip:KenMyer@Contoso.com
```

<span data-ttu-id="79e13-138">Параметры занятости можно удалить с помощью [cmdlet Remove-CsBusyOptions.](https://technet.microsoft.com/library/159e5931-10f1-4226-bcc4-38548f88f0d4.aspx)</span><span class="sxs-lookup"><span data-stu-id="79e13-138">You can remove Busy Options by using the [Remove-CsBusyOptions](https://technet.microsoft.com/library/159e5931-10f1-4226-bcc4-38548f88f0d4.aspx) cmdlet.</span></span> <span data-ttu-id="79e13-139">Следующая команда удаляет параметры занятости для "Ken Myer":</span><span class="sxs-lookup"><span data-stu-id="79e13-139">The following command removes Busy Options for "Ken Myer":</span></span>

```powershell
Remove-CsBusyOptions -Identity "Ken Myer"
```

<span data-ttu-id="79e13-140">Подробные сведения о cmdlets, которые используются для настройки параметров занятости, см. в техническом справочнике по [set-CsBusyOptions,](https://technet.microsoft.com/library/8ffbb832-3e55-4d6c-9a7c-5ce2df22de2e.aspx) [Get-CsBusyOptions](https://technet.microsoft.com/library/ff0e3b1c-c41d-41e4-9468-0cb057aef9fb.aspx)и [Remove-CsBusyOptions.](https://technet.microsoft.com/library/159e5931-10f1-4226-bcc4-38548f88f0d4.aspx)</span><span class="sxs-lookup"><span data-stu-id="79e13-140">For detailed information about the cmdlets you use to configure Busy Options, see the technical reference content for [Set-CsBusyOptions](https://technet.microsoft.com/library/8ffbb832-3e55-4d6c-9a7c-5ce2df22de2e.aspx), [Get-CsBusyOptions](https://technet.microsoft.com/library/ff0e3b1c-c41d-41e4-9468-0cb057aef9fb.aspx), and [Remove-CsBusyOptions](https://technet.microsoft.com/library/159e5931-10f1-4226-bcc4-38548f88f0d4.aspx).</span></span>

## <a name="enable-logging"></a><span data-ttu-id="79e13-141">Включить ведение журнала</span><span class="sxs-lookup"><span data-stu-id="79e13-141">Enable logging</span></span>

<span data-ttu-id="79e13-142">Чтобы включить ведение журнала параметров занятости с помощью службы централизованного ведения журналов, укажите следующее:</span><span class="sxs-lookup"><span data-stu-id="79e13-142">To enable logging for Busy Options by using the Centralized Logging Service, specify the following:</span></span>

```powershell
$p1 = New-CsClsProvider -Name S4 -Type WPP -Level Info -Flags All
$p2 = New-CsClsProvider -Name Sipstack -Type WPP -Level Info -Flags
 "TF_PROTOCOL,TF_CONNECTION,TF_SECURITY,TF_DIAG,TF_SHOW_CONFERENCE,TF_SHOW_ALLREQUESTS,TF_SHOW_ALLSIPHEADERS" -Role Registrar
$p3 = New-CsClsProvider -Name BusyOptions -Type WPP -Level Verbose -Flags All
New-CsClsScenario -Parent Global -Name BusyOptions -Provider @{Add=$p1,$p2,$p3}
```

## <a name="verify-and-troubleshoot"></a><span data-ttu-id="79e13-143">Проверка и устранение неполадок</span><span class="sxs-lookup"><span data-stu-id="79e13-143">Verify and troubleshoot</span></span>

<span data-ttu-id="79e13-144">После установки параметров занятости вы можете убедиться, что установка прошла успешно, с помощью [cmdlet Get-CsServerApplication](https://docs.microsoft.com/powershell/module/skype/get-csserverapplication?view=skype-ps) для получения списка серверных приложений.</span><span class="sxs-lookup"><span data-stu-id="79e13-144">After installing Busy Options, you can verify that the installation was successful by using the [Get-CsServerApplication](https://docs.microsoft.com/powershell/module/skype/get-csserverapplication?view=skype-ps) cmdlet to retrieve the list of server applications.</span></span> <span data-ttu-id="79e13-145">Если параметры занятости установлены надлежащим образом, в выходных данных этого параметра должна быть установлена конфигурация параметров занятости следующим образом:</span><span class="sxs-lookup"><span data-stu-id="79e13-145">If Busy Options is installed properly, the output of the cmdlet should show the Busy Options configuration as follows:</span></span>

<pre>
Identity   : Service:Registrar:pool0.vdomain.com/BusyOptions
Priority   : 5
Uri        : https://www.microsoft.com/LCS/BusyOptions
Name       : BusyOptions
Enabled    : True
Critical   : False
ScriptName :
Script     :
</pre>

<span data-ttu-id="79e13-146">Кроме того, с помощью просмотра событий Windows можно проверить успешность установки параметров занятости и загрузку параметров занятости в Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="79e13-146">You can also use Windows Event Viewer to verify that the Busy Options installation was successful and that Skype for Business Server successfully loaded Busy Options.</span></span> <span data-ttu-id="79e13-147">To verify Busy Options, open **Event Viewer - \> Application and Services Logs - \> Skype (or Lync) Server** and search for Event ID = 30253.</span><span class="sxs-lookup"><span data-stu-id="79e13-147">To verify Busy Options, open **Event Viewer -\> Application and Services Logs -\> Skype (or Lync) Server** and search for Event ID = 30253.</span></span>
