---
title: Установка и настройка параметров занятости в Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: Узнайте о том, как установить и настроить параметры доступности в Skype для бизнеса Server.
ms.openlocfilehash: dd22d07bcabc86b0d16f3ad1029087b659a3e4a5
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41767222"
---
# <a name="install-and-configure-busy-options-for-skype-for-business-server"></a><span data-ttu-id="68df4-103">Установка и настройка параметров занятости в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="68df4-103">Install and configure Busy Options for Skype for Business Server</span></span>

<span data-ttu-id="68df4-104">Узнайте о том, как установить и настроить параметры доступности в Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="68df4-104">Read about how to install and configure Busy Options in Skype for Business Server.</span></span>

<span data-ttu-id="68df4-105">Параметры занятости были представлены в накопительном пакете обновлений за июль 2016 года и определяют политику голосовой связи, которая задает порядок обработки входящих звонков, поступающих во время обычного, удерживаемого или конференц-звонка.</span><span class="sxs-lookup"><span data-stu-id="68df4-105">Busy Options is a new voice policy introduced in the July 2016 Cumulative Update that allows you to configure how incoming calls are handled when a user is already in a call or conference or has a call placed on hold.</span></span> <span data-ttu-id="68df4-106">В зависимости от настроек новые или входящие звонки могут отклоняться с сигналом "занято" или переадресовываться на голосовую почту.</span><span class="sxs-lookup"><span data-stu-id="68df4-106">New or incoming calls can be rejected with a busy signal or forwarded to voice mail.</span></span>

<span data-ttu-id="68df4-107">Если для организации включены параметры занятости, все ее пользователи, независимо от наличия доступа к корпоративной голосовой связи, могут использовать следующие параметры конфигурации:</span><span class="sxs-lookup"><span data-stu-id="68df4-107">If Busy Options is enabled for the organization, all users at the Enterprise, both Enterprise Voice and non-Enterprise Voice users, can use the following configuration options:</span></span>

- <span data-ttu-id="68df4-108">Сигнал занятости — если пользователь занят, все входящие звонки отклоняются и подается сигнал "занято".</span><span class="sxs-lookup"><span data-stu-id="68df4-108">Busy on Busy - In which new incoming calls will be rejected with a busy signal if the user is busy.</span></span>

- <span data-ttu-id="68df4-109">Голосовая почта — если пользователь занят, все входящие звонки переадресуются на голосовую почту.</span><span class="sxs-lookup"><span data-stu-id="68df4-109">Voicemail on Busy - In which new incoming calls will be forwarded to voice mail if the user is busy.</span></span>

<span data-ttu-id="68df4-110">Независимо от установленных параметров занятости, во время обычного, удерживаемого или конференц-звонка пользователи могут выполнять новые звонки.  </span><span class="sxs-lookup"><span data-stu-id="68df4-110">Regardless of how their busy options are configured, users in a call or conference, or those with a call on hold, are not prevented from initiating new calls or conferences.</span></span>

<span data-ttu-id="68df4-111">Дополнительные сведения о функции параметров занятости см. в статье [Plan for Busy Options for Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/busy-options.md).</span><span class="sxs-lookup"><span data-stu-id="68df4-111">For more information about the Busy Options feature, see [Plan for Busy Options for Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/busy-options.md).</span></span>

## <a name="install"></a><span data-ttu-id="68df4-112">Установка </span><span class="sxs-lookup"><span data-stu-id="68df4-112">Install</span></span>

<span data-ttu-id="68df4-113">Убедитесь, что у вас установлена последняя версия Skype для бизнеса Server и что вы установили Последнее исправление.</span><span class="sxs-lookup"><span data-stu-id="68df4-113">Make sure you have the latest version of Skype for Business Server installed and that you have installed the most recent patch.</span></span> <span data-ttu-id="68df4-114">Для этого сначала остановите все службы, а затем запустите программу установки обновления для Skype для Business Server, как описано ниже.</span><span class="sxs-lookup"><span data-stu-id="68df4-114">To do this, first stop all services, and then run the Skype for Business Server update installer as follows:</span></span>

1. <span data-ttu-id="68df4-115">Выполните команду Stop-CsWindowsService.</span><span class="sxs-lookup"><span data-stu-id="68df4-115">Run the Stop-CsWindowsService command.</span></span>

2. <span data-ttu-id="68df4-116">Запустите файл SkypeServerUpdateInstaller.exe для каждого сервера переднего плана в пуле.</span><span class="sxs-lookup"><span data-stu-id="68df4-116">Run the SkypeServerUpdateInstaller.exe installer on each Front End server in a pool.</span></span>

3. <span data-ttu-id="68df4-117">Если необходимо реализовать отработку отказа на серверах обеспечения связи в филиалах, запустите установщик SkypeServerUpdateInstaller.exe на каждом из таких серверов.</span><span class="sxs-lookup"><span data-stu-id="68df4-117">Run the SkypeServerUpdateInstaller.exe installer on each Survivable Branch Server (SBS), if you want to ensure support for failover on SBS.</span></span>

<span data-ttu-id="68df4-p103">Установщик разворачивает последнюю версию приложения параметров занятости, однако оно не будет включено по умолчанию. Для его включения необходимо выполнить приведенные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="68df4-p103">The installer will deploy the latest version of the Busy Options application. However, the application is not enabled by default. To enable the application, perform the following steps:</span></span>

1. <span data-ttu-id="68df4-121">Запустите командлет [Set-ксвоицеполици](https://docs.microsoft.com/powershell/module/skype/set-csvoicepolicy?view=skype-ps) , чтобы включить параметры доступности, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="68df4-121">Run the [Set-CsVoicePolicy](https://docs.microsoft.com/powershell/module/skype/set-csvoicepolicy?view=skype-ps) cmdlet to globally enable Busy Options as shown in the following example:</span></span>

   ```powershell
   Set-CsVoicePolicy -EnableBusyOptions $true
   ```

2. <span data-ttu-id="68df4-122">Затем, если для сайта настроена политика голосовой связи, необходимо включить параметры занятости для этой политики следующим образом.</span><span class="sxs-lookup"><span data-stu-id="68df4-122">Next, if the site has a voice policy is place, you must enable Busy Options for the voice policy as follows:</span></span>

    <span data-ttu-id="68df4-123">Сначала запустите [Get-кссите](https://docs.microsoft.com/powershell/module/skype/get-cssite?view=skype-ps) , чтобы получить имя сайта:</span><span class="sxs-lookup"><span data-stu-id="68df4-123">First, run [Get-CsSite](https://docs.microsoft.com/powershell/module/skype/get-cssite?view=skype-ps) to retrieve the name of the site:</span></span>

   ```powershell
   Get-CsSite
   ```

    <span data-ttu-id="68df4-124">Используйте значение удостоверения (например, сайт: Redmond1), полученное из Get-Кссите, чтобы получить политику голосовой связи для сайта, как описано ниже.</span><span class="sxs-lookup"><span data-stu-id="68df4-124">Use the Identity value (for example: Site:Redmond1) retrieved from Get-CsSite to retrieve the voice policy of the site as follows:</span></span>

   ```powershell
   Get-CsVoicePolicy -Identity Site:Redmond1
   ```

    <span data-ttu-id="68df4-125">Если для сайта существует политика голосовой связи, выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="68df4-125">If a voice policy exists for the site, run the following command:</span></span>

   ```powershell
   Set-CsVoicePolicy -Identity Site:Redmond1 -EnableBusyOptions $true
   ```

3. <span data-ttu-id="68df4-126">Затем выполните командлет [New-кссервераппликатион](https://docs.microsoft.com/powershell/module/skype/new-csserverapplication?view=skype-ps) , чтобы добавить параметры Busy в список серверных приложений, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="68df4-126">Next, run the [New-CsServerApplication](https://docs.microsoft.com/powershell/module/skype/new-csserverapplication?view=skype-ps) cmdlet to add Busy Options to the list of server applications as shown in the following example:</span></span>

   ```powershell
   New-CsServerApplication -Identity 'Service:Registrar:%FQDN%/BusyOptions' -Uri http://www.microsoft.com/LCS/BusyOptions -Critical $False -Enabled $True -Priority (Get-CsServerApplication -Identity 'Service:Registrar:%FQDN%/UserServices').Priority
   ```

    > [!NOTE]
    > <span data-ttu-id="68df4-127">Вы должны заменить% FQDN% полным доменным именем определенного пула.</span><span class="sxs-lookup"><span data-stu-id="68df4-127">You must replace %FQDN% with the fully-qualified domain name of a specific pool.</span></span>

4. <span data-ttu-id="68df4-128">Затем выполните командлет [Update-ксадминроле](https://docs.microsoft.com/powershell/module/skype/update-csadminrole?view=skype-ps) , чтобы обновить роли управления доступом на основе РОЛЕЙ (RBAC) для командлетов параметров Busy, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="68df4-128">Next, run the [Update-CsAdminRole](https://docs.microsoft.com/powershell/module/skype/update-csadminrole?view=skype-ps) cmdlet to update the Role-based access control (RBAC) roles for the Busy Options cmdlets as shown in the following example:</span></span>

   ```powershell
   Update-CsAdminRole
   ```

5. <span data-ttu-id="68df4-129">Наконец, запустите команду [Start-ксвиндовссервице](https://docs.microsoft.com/powershell/module/skype/start-cswindowsservice?view=skype-ps) на всех серверах, на которых установлены и включены службы Windows для бизнеса Server, на все серверы переднего плана, на которых установлен и включен параметр Busy.</span><span class="sxs-lookup"><span data-stu-id="68df4-129">Finally, start the Skype for Business Server Windows services on all the Front End servers in all the pools where Busy Options was installed and enabled by running the [Start-CsWindowsService](https://docs.microsoft.com/powershell/module/skype/start-cswindowsservice?view=skype-ps) command:</span></span>

   ```powershell
   Start-CsWindowsService
   ```

## <a name="configure"></a><span data-ttu-id="68df4-130">Настройка</span><span class="sxs-lookup"><span data-stu-id="68df4-130">Configure</span></span>

<span data-ttu-id="68df4-131">Для настройки параметров занятости используйте командлет [Set-CsBusyOptions](https://technet.microsoft.com/library/8ffbb832-3e55-4d6c-9a7c-5ce2df22de2e.aspx).  </span><span class="sxs-lookup"><span data-stu-id="68df4-131">To configure Busy Options, use the [Set-CsBusyOptions](https://technet.microsoft.com/library/8ffbb832-3e55-4d6c-9a7c-5ce2df22de2e.aspx) cmdlet.</span></span>

<span data-ttu-id="68df4-p104">Например, следующая команда задает параметры занятости для пользователя "Ken Myer". В такой конфигурации при поступлении звонка этому пользователю во время активного звонка возвращается сигнал "занято":</span><span class="sxs-lookup"><span data-stu-id="68df4-p104">For example, the following command configures busy options for the user "Ken Myer". In this configuration, any call to "Ken Myer" will return a busy signal when he is already in a call:</span></span>

```powershell
Set-CsBusyOptions -Identity "Ken Myer"  -ActionType BusyOnBusy
```

<span data-ttu-id="68df4-134">В следующем примере эта команда задает параметры занятости для пользователя "Chrystal Velasquez".</span><span class="sxs-lookup"><span data-stu-id="68df4-134">In the next example, the command configures busy options for the user "Chrystal Velasquez".</span></span> <span data-ttu-id="68df4-135">В такой конфигурации новые входящие звонки, поступающие этому пользователю во время активного звонка, переадресуются на голосовую почту:</span><span class="sxs-lookup"><span data-stu-id="68df4-135">In this configuration, new incoming calls to "Chrystal Velasquez" will be forwarded to voice mail when she is already in a call:</span></span>

```powershell
Set-CsBusyOptions -Identity "Chrystal Velasquez" -ActionType VoicemailOnBusy
```

<span data-ttu-id="68df4-136">Чтобы извлечь сведения о конфигурации параметров занятости, используйте командлет [Get-CsBusyOptions](https://technet.microsoft.com/library/ff0e3b1c-c41d-41e4-9468-0cb057aef9fb.aspx).</span><span class="sxs-lookup"><span data-stu-id="68df4-136">You can retrieve configuration information about Busy Options by using the [Get-CsBusyOptions](https://technet.microsoft.com/library/ff0e3b1c-c41d-41e4-9468-0cb057aef9fb.aspx) cmdlet.</span></span> <span data-ttu-id="68df4-137">В следующем примере возвращаются значения параметров Busy для "KenMyer@Contoso.com":</span><span class="sxs-lookup"><span data-stu-id="68df4-137">The following example returns the Busy Options setting for "KenMyer@Contoso.com":</span></span>

```powershell
Get-CsBusyOptions -Identity sip:KenMyer@Contoso.com
```

<span data-ttu-id="68df4-138">Чтобы удалить параметры занятости, используйте командлет [Remove-CsBusyOptions](https://technet.microsoft.com/library/159e5931-10f1-4226-bcc4-38548f88f0d4.aspx).</span><span class="sxs-lookup"><span data-stu-id="68df4-138">You can remove Busy Options by using the [Remove-CsBusyOptions](https://technet.microsoft.com/library/159e5931-10f1-4226-bcc4-38548f88f0d4.aspx) cmdlet.</span></span> <span data-ttu-id="68df4-139">Следующая команда удаляет параметры занятости для пользователя "Ken Myer":</span><span class="sxs-lookup"><span data-stu-id="68df4-139">The following command removes Busy Options for "Ken Myer":</span></span>

```powershell
Remove-CsBusyOptions -Identity "Ken Myer"
```

<span data-ttu-id="68df4-140">Подробные сведения о командлетах, используемых для настройки параметров доступности, приведены в справочных материалах для [Set-ксбусйоптионс](https://technet.microsoft.com/library/8ffbb832-3e55-4d6c-9a7c-5ce2df22de2e.aspx), [Get-Ксбусйоптионс](https://technet.microsoft.com/library/ff0e3b1c-c41d-41e4-9468-0cb057aef9fb.aspx)и [Remove-ксбусйоптионс](https://technet.microsoft.com/library/159e5931-10f1-4226-bcc4-38548f88f0d4.aspx).</span><span class="sxs-lookup"><span data-stu-id="68df4-140">For detailed information about the cmdlets you use to configure Busy Options, see the technical reference content for [Set-CsBusyOptions](https://technet.microsoft.com/library/8ffbb832-3e55-4d6c-9a7c-5ce2df22de2e.aspx), [Get-CsBusyOptions](https://technet.microsoft.com/library/ff0e3b1c-c41d-41e4-9468-0cb057aef9fb.aspx), and [Remove-CsBusyOptions](https://technet.microsoft.com/library/159e5931-10f1-4226-bcc4-38548f88f0d4.aspx).</span></span>

## <a name="enable-logging"></a><span data-ttu-id="68df4-141">Включение ведения журналов</span><span class="sxs-lookup"><span data-stu-id="68df4-141">Enable logging</span></span>

<span data-ttu-id="68df4-142">Чтобы включить ведение журналов с использованием соответствующей централизованной службы, введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="68df4-142">To enable logging for Busy Options by using the Centralized Logging Service, specify the following:</span></span>

```powershell
$p1 = New-CsClsProvider -Name S4 -Type WPP -Level Info -Flags All
$p2 = New-CsClsProvider -Name Sipstack -Type WPP -Level Info -Flags
 "TF_PROTOCOL,TF_CONNECTION,TF_SECURITY,TF_DIAG,TF_SHOW_CONFERENCE,TF_SHOW_ALLREQUESTS,TF_SHOW_ALLSIPHEADERS" -Role Registrar
$p3 = New-CsClsProvider -Name BusyOptions -Type WPP -Level Verbose -Flags All
New-CsClsScenario -Parent Global -Name BusyOptions -Provider @{Add=$p1,$p2,$p3}
```

## <a name="verify-and-troubleshoot"></a><span data-ttu-id="68df4-143">Проверка и устранение неполадок</span><span class="sxs-lookup"><span data-stu-id="68df4-143">Verify and troubleshoot</span></span>

<span data-ttu-id="68df4-144">После установки параметров доступности вы можете убедиться, что установка выполнена успешно с помощью командлета [Get-кссервераппликатион](https://docs.microsoft.com/powershell/module/skype/get-csserverapplication?view=skype-ps) , чтобы получить список серверных приложений.</span><span class="sxs-lookup"><span data-stu-id="68df4-144">After installing Busy Options, you can verify that the installation was successful by using the [Get-CsServerApplication](https://docs.microsoft.com/powershell/module/skype/get-csserverapplication?view=skype-ps) cmdlet to retrieve the list of server applications.</span></span> <span data-ttu-id="68df4-145">Если параметры занятости установлены надлежащим образом, этот командлет вернет следующую конфигурацию этой функции:</span><span class="sxs-lookup"><span data-stu-id="68df4-145">If Busy Options is installed properly, the output of the cmdlet should show the Busy Options configuration as follows:</span></span>

<pre>
Identity   : Service:Registrar:pool0.vdomain.com/BusyOptions
Priority   : 5
Uri        : http://www.microsoft.com/LCS/BusyOptions
Name       : BusyOptions
Enabled    : True
Critical   : False
ScriptName :
Script     :
</pre>

<span data-ttu-id="68df4-146">Кроме того, можно использовать средство просмотра событий Windows, чтобы убедиться, что установка параметров доступности успешно завершилась, и что параметры доступности в Skype для бизнеса Server успешно загружены.</span><span class="sxs-lookup"><span data-stu-id="68df4-146">You can also use Windows Event Viewer to verify that the Busy Options installation was successful and that Skype for Business Server successfully loaded Busy Options.</span></span> <span data-ttu-id="68df4-147">Чтобы проверить параметры доступности, откройте **окно просмотра событий\> — журналы приложений и служб\> — Skype (или LYNC)** и найдите событие ID = 30253.</span><span class="sxs-lookup"><span data-stu-id="68df4-147">To verify Busy Options, open **Event Viewer -\> Application and Services Logs -\> Skype (or Lync) Server** and search for Event ID = 30253.</span></span>
