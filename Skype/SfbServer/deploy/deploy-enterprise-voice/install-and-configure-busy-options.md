---
title: Установка и Настройка параметров занятости в Skype для бизнеса Server
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
description: Узнайте, как установить и настроить параметры занятости в Skype для бизнеса Server.
ms.openlocfilehash: 5078041401c710a249470ed6d3871f38a98a7420
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42113122"
---
# <a name="install-and-configure-busy-options-for-skype-for-business-server"></a><span data-ttu-id="f3cda-103">Установка и Настройка параметров занятости в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="f3cda-103">Install and configure Busy Options for Skype for Business Server</span></span>

<span data-ttu-id="f3cda-104">Узнайте, как установить и настроить параметры занятости в Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="f3cda-104">Read about how to install and configure Busy Options in Skype for Business Server.</span></span>

<span data-ttu-id="f3cda-105">Параметры занятости — это новая политика голосовой связи, появившаяся в накопительном пакете обновления 2016 за Июль, которая позволяет настроить способ обработки входящих вызовов, когда пользователь уже находился в вызове или в конференции, или вызов заблокирован.</span><span class="sxs-lookup"><span data-stu-id="f3cda-105">Busy Options is a new voice policy introduced in the July 2016 Cumulative Update that allows you to configure how incoming calls are handled when a user is already in a call or conference or has a call placed on hold.</span></span> <span data-ttu-id="f3cda-106">Новые или входящие звонки могут отклоняться с помощью сигнала "занято" или пересылки на голосовую почту.</span><span class="sxs-lookup"><span data-stu-id="f3cda-106">New or incoming calls can be rejected with a busy signal or forwarded to voice mail.</span></span>

<span data-ttu-id="f3cda-107">Если для организации включены параметры занятости, все пользователи на предприятии, как для корпоративной голосовой связи, так и для пользователей, не являющихся корпоративными, могут использовать следующие параметры конфигурации:</span><span class="sxs-lookup"><span data-stu-id="f3cda-107">If Busy Options is enabled for the organization, all users at the Enterprise, both Enterprise Voice and non-Enterprise Voice users, can use the following configuration options:</span></span>

- <span data-ttu-id="f3cda-108">Занято при занятости, при котором новые входящие звонки отклоняются с сигналом занятости, если пользователь занят.</span><span class="sxs-lookup"><span data-stu-id="f3cda-108">Busy on Busy - In which new incoming calls will be rejected with a busy signal if the user is busy.</span></span>

- <span data-ttu-id="f3cda-109">Голосовая почта (при занятости), при которой новые входящие звонки будут перенаправляться на голосовую почту, если пользователь занят.</span><span class="sxs-lookup"><span data-stu-id="f3cda-109">Voicemail on Busy - In which new incoming calls will be forwarded to voice mail if the user is busy.</span></span>

<span data-ttu-id="f3cda-110">Независимо от того, как настроены параметры занятости, пользователи в вызове или конференции, а также при вызове на удержание не могут инициировать новые вызовы или конференции.</span><span class="sxs-lookup"><span data-stu-id="f3cda-110">Regardless of how their busy options are configured, users in a call or conference, or those with a call on hold, are not prevented from initiating new calls or conferences.</span></span>

<span data-ttu-id="f3cda-111">Дополнительные сведения о функции "занято" можно найти в статье [Планирование возможностей занятости в Skype для бизнеса Server](../../plan-your-deployment/enterprise-voice-solution/busy-options.md).</span><span class="sxs-lookup"><span data-stu-id="f3cda-111">For more information about the Busy Options feature, see [Plan for Busy Options for Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/busy-options.md).</span></span>

## <a name="install"></a><span data-ttu-id="f3cda-112">Установка</span><span class="sxs-lookup"><span data-stu-id="f3cda-112">Install</span></span>

<span data-ttu-id="f3cda-113">Убедитесь, что установлена последняя версия Skype для бизнеса Server и вы установили Последнее исправление.</span><span class="sxs-lookup"><span data-stu-id="f3cda-113">Make sure you have the latest version of Skype for Business Server installed and that you have installed the most recent patch.</span></span> <span data-ttu-id="f3cda-114">Для этого сначала остановите все службы, а затем запустите установщик обновлений Skype для бизнеса Server следующим образом:</span><span class="sxs-lookup"><span data-stu-id="f3cda-114">To do this, first stop all services, and then run the Skype for Business Server update installer as follows:</span></span>

1. <span data-ttu-id="f3cda-115">Выполните команду Stop – CsWindowsService.</span><span class="sxs-lookup"><span data-stu-id="f3cda-115">Run the Stop-CsWindowsService command.</span></span>

2. <span data-ttu-id="f3cda-116">Запустите установщик файл skypeserverupdateinstaller. exe на каждом сервере переднего плана в пуле.</span><span class="sxs-lookup"><span data-stu-id="f3cda-116">Run the SkypeServerUpdateInstaller.exe installer on each Front End server in a pool.</span></span>

3. <span data-ttu-id="f3cda-117">Запустите установщик файл skypeserverupdateinstaller. exe на каждом сервере для обеспечения связи в филиалах (SBS), если вы хотите обеспечить поддержку отработки отказа в SBS.</span><span class="sxs-lookup"><span data-stu-id="f3cda-117">Run the SkypeServerUpdateInstaller.exe installer on each Survivable Branch Server (SBS), if you want to ensure support for failover on SBS.</span></span>

<span data-ttu-id="f3cda-118">Установщик будет развертывать последнюю версию приложения "занято".</span><span class="sxs-lookup"><span data-stu-id="f3cda-118">The installer will deploy the latest version of the Busy Options application.</span></span> <span data-ttu-id="f3cda-119">Однако приложение по умолчанию отключено.</span><span class="sxs-lookup"><span data-stu-id="f3cda-119">However, the application is not enabled by default.</span></span> <span data-ttu-id="f3cda-120">Чтобы включить приложение, выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="f3cda-120">To enable the application, perform the following steps:</span></span>

1. <span data-ttu-id="f3cda-121">Выполните командлет [Set – CsVoicePolicy](https://docs.microsoft.com/powershell/module/skype/set-csvoicepolicy?view=skype-ps) для глобального включения параметров занятости, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="f3cda-121">Run the [Set-CsVoicePolicy](https://docs.microsoft.com/powershell/module/skype/set-csvoicepolicy?view=skype-ps) cmdlet to globally enable Busy Options as shown in the following example:</span></span>

   ```powershell
   Set-CsVoicePolicy -EnableBusyOptions $true
   ```

2. <span data-ttu-id="f3cda-122">После этого, если на сайте имеется политика голосовой связи, необходимо включить параметры занятости для политики голосовой связи следующим образом.</span><span class="sxs-lookup"><span data-stu-id="f3cda-122">Next, if the site has a voice policy is place, you must enable Busy Options for the voice policy as follows:</span></span>

    <span data-ttu-id="f3cda-123">Сначала выполните командлет [Get-CsSite](https://docs.microsoft.com/powershell/module/skype/get-cssite?view=skype-ps) , чтобы получить имя сайта:</span><span class="sxs-lookup"><span data-stu-id="f3cda-123">First, run [Get-CsSite](https://docs.microsoft.com/powershell/module/skype/get-cssite?view=skype-ps) to retrieve the name of the site:</span></span>

   ```powershell
   Get-CsSite
   ```

    <span data-ttu-id="f3cda-124">Используйте значение идентификатора (например: site: Redmond1), полученное из Get-CsSite, чтобы получить политику голосовой связи для сайта следующим образом:</span><span class="sxs-lookup"><span data-stu-id="f3cda-124">Use the Identity value (for example: Site:Redmond1) retrieved from Get-CsSite to retrieve the voice policy of the site as follows:</span></span>

   ```powershell
   Get-CsVoicePolicy -Identity Site:Redmond1
   ```

    <span data-ttu-id="f3cda-125">Если для сайта существует политика голосовой связи, выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="f3cda-125">If a voice policy exists for the site, run the following command:</span></span>

   ```powershell
   Set-CsVoicePolicy -Identity Site:Redmond1 -EnableBusyOptions $true
   ```

3. <span data-ttu-id="f3cda-126">Затем выполните командлет [New – CsServerApplication](https://docs.microsoft.com/powershell/module/skype/new-csserverapplication?view=skype-ps) , чтобы добавить параметры занятости в список серверных приложений, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="f3cda-126">Next, run the [New-CsServerApplication](https://docs.microsoft.com/powershell/module/skype/new-csserverapplication?view=skype-ps) cmdlet to add Busy Options to the list of server applications as shown in the following example:</span></span>

   ```powershell
   New-CsServerApplication -Identity 'Service:Registrar:%FQDN%/BusyOptions' -Uri https://www.microsoft.com/LCS/BusyOptions -Critical $False -Enabled $True -Priority (Get-CsServerApplication -Identity 'Service:Registrar:%FQDN%/UserServices').Priority
   ```

    > [!NOTE]
    > <span data-ttu-id="f3cda-127">Необходимо заменить% FQDN% на полное доменное имя определенного пула.</span><span class="sxs-lookup"><span data-stu-id="f3cda-127">You must replace %FQDN% with the fully-qualified domain name of a specific pool.</span></span>

4. <span data-ttu-id="f3cda-128">Затем выполните командлет [Update-CsAdminRole](https://docs.microsoft.com/powershell/module/skype/update-csadminrole?view=skype-ps) , чтобы обновить роли управления доступом на основе РОЛЕЙ (RBAC) для командлетов параметров занятости, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="f3cda-128">Next, run the [Update-CsAdminRole](https://docs.microsoft.com/powershell/module/skype/update-csadminrole?view=skype-ps) cmdlet to update the Role-based access control (RBAC) roles for the Busy Options cmdlets as shown in the following example:</span></span>

   ```powershell
   Update-CsAdminRole
   ```

5. <span data-ttu-id="f3cda-129">Наконец, запустите службы Windows Skype для бизнеса Server на всех серверах переднего плана во всех пулах, где были установлены и включены параметры занятости, выполнив команду [Start-CsWindowsService](https://docs.microsoft.com/powershell/module/skype/start-cswindowsservice?view=skype-ps) :</span><span class="sxs-lookup"><span data-stu-id="f3cda-129">Finally, start the Skype for Business Server Windows services on all the Front End servers in all the pools where Busy Options was installed and enabled by running the [Start-CsWindowsService](https://docs.microsoft.com/powershell/module/skype/start-cswindowsservice?view=skype-ps) command:</span></span>

   ```powershell
   Start-CsWindowsService
   ```

## <a name="configure"></a><span data-ttu-id="f3cda-130">Configure (Настроить)</span><span class="sxs-lookup"><span data-stu-id="f3cda-130">Configure</span></span>

<span data-ttu-id="f3cda-131">Чтобы настроить параметры занятости, используйте командлет [Set – CsBusyOptions](https://technet.microsoft.com/library/8ffbb832-3e55-4d6c-9a7c-5ce2df22de2e.aspx) .</span><span class="sxs-lookup"><span data-stu-id="f3cda-131">To configure Busy Options, use the [Set-CsBusyOptions](https://technet.microsoft.com/library/8ffbb832-3e55-4d6c-9a7c-5ce2df22de2e.aspx) cmdlet.</span></span>

<span data-ttu-id="f3cda-132">Например, следующая команда настраивает параметры занятости для пользователя "Ken Myer".</span><span class="sxs-lookup"><span data-stu-id="f3cda-132">For example, the following command configures busy options for the user "Ken Myer".</span></span> <span data-ttu-id="f3cda-133">В этой конфигурации любой вызов "Ken Myer" возвратит сигнал занятости, когда он уже находился в вызове:</span><span class="sxs-lookup"><span data-stu-id="f3cda-133">In this configuration, any call to "Ken Myer" will return a busy signal when he is already in a call:</span></span>

```powershell
Set-CsBusyOptions -Identity "Ken Myer"  -ActionType BusyOnBusy
```

<span data-ttu-id="f3cda-134">В следующем примере команда настраивает параметры занятости для пользователя "Чристал переадресуются".</span><span class="sxs-lookup"><span data-stu-id="f3cda-134">In the next example, the command configures busy options for the user "Chrystal Velasquez".</span></span> <span data-ttu-id="f3cda-135">В этой конфигурации новые входящие вызовы "Чристал переадресуются" будут пересылаться в голосовую почту, когда она уже находится в вызове:</span><span class="sxs-lookup"><span data-stu-id="f3cda-135">In this configuration, new incoming calls to "Chrystal Velasquez" will be forwarded to voice mail when she is already in a call:</span></span>

```powershell
Set-CsBusyOptions -Identity "Chrystal Velasquez" -ActionType VoicemailOnBusy
```

<span data-ttu-id="f3cda-136">Сведения о конфигурации для параметров занятости можно получить с помощью командлета [Get – CsBusyOptions](https://technet.microsoft.com/library/ff0e3b1c-c41d-41e4-9468-0cb057aef9fb.aspx) .</span><span class="sxs-lookup"><span data-stu-id="f3cda-136">You can retrieve configuration information about Busy Options by using the [Get-CsBusyOptions](https://technet.microsoft.com/library/ff0e3b1c-c41d-41e4-9468-0cb057aef9fb.aspx) cmdlet.</span></span> <span data-ttu-id="f3cda-137">В следующем примере возвращаются параметры занятости для "KenMyer@Contoso.com":</span><span class="sxs-lookup"><span data-stu-id="f3cda-137">The following example returns the Busy Options setting for "KenMyer@Contoso.com":</span></span>

```powershell
Get-CsBusyOptions -Identity sip:KenMyer@Contoso.com
```

<span data-ttu-id="f3cda-138">Параметры занятости можно удалить с помощью командлета [Remove – CsBusyOptions](https://technet.microsoft.com/library/159e5931-10f1-4226-bcc4-38548f88f0d4.aspx) .</span><span class="sxs-lookup"><span data-stu-id="f3cda-138">You can remove Busy Options by using the [Remove-CsBusyOptions](https://technet.microsoft.com/library/159e5931-10f1-4226-bcc4-38548f88f0d4.aspx) cmdlet.</span></span> <span data-ttu-id="f3cda-139">Следующая команда удаляет параметры занятости для "Ken Myer":</span><span class="sxs-lookup"><span data-stu-id="f3cda-139">The following command removes Busy Options for "Ken Myer":</span></span>

```powershell
Remove-CsBusyOptions -Identity "Ken Myer"
```

<span data-ttu-id="f3cda-140">Подробные сведения о командлетах, используемых для настройки параметров занятости, приведены в статье справочные материалы по командлетам [Set — CsBusyOptions](https://technet.microsoft.com/library/8ffbb832-3e55-4d6c-9a7c-5ce2df22de2e.aspx), [Get/CsBusyOptions](https://technet.microsoft.com/library/ff0e3b1c-c41d-41e4-9468-0cb057aef9fb.aspx)и [Remove/CsBusyOptions](https://technet.microsoft.com/library/159e5931-10f1-4226-bcc4-38548f88f0d4.aspx).</span><span class="sxs-lookup"><span data-stu-id="f3cda-140">For detailed information about the cmdlets you use to configure Busy Options, see the technical reference content for [Set-CsBusyOptions](https://technet.microsoft.com/library/8ffbb832-3e55-4d6c-9a7c-5ce2df22de2e.aspx), [Get-CsBusyOptions](https://technet.microsoft.com/library/ff0e3b1c-c41d-41e4-9468-0cb057aef9fb.aspx), and [Remove-CsBusyOptions](https://technet.microsoft.com/library/159e5931-10f1-4226-bcc4-38548f88f0d4.aspx).</span></span>

## <a name="enable-logging"></a><span data-ttu-id="f3cda-141">Включение ведения журнала</span><span class="sxs-lookup"><span data-stu-id="f3cda-141">Enable logging</span></span>

<span data-ttu-id="f3cda-142">Чтобы включить ведение журнала для параметров занятости с помощью централизованной службы ведения журналов, укажите следующее:</span><span class="sxs-lookup"><span data-stu-id="f3cda-142">To enable logging for Busy Options by using the Centralized Logging Service, specify the following:</span></span>

```powershell
$p1 = New-CsClsProvider -Name S4 -Type WPP -Level Info -Flags All
$p2 = New-CsClsProvider -Name Sipstack -Type WPP -Level Info -Flags
 "TF_PROTOCOL,TF_CONNECTION,TF_SECURITY,TF_DIAG,TF_SHOW_CONFERENCE,TF_SHOW_ALLREQUESTS,TF_SHOW_ALLSIPHEADERS" -Role Registrar
$p3 = New-CsClsProvider -Name BusyOptions -Type WPP -Level Verbose -Flags All
New-CsClsScenario -Parent Global -Name BusyOptions -Provider @{Add=$p1,$p2,$p3}
```

## <a name="verify-and-troubleshoot"></a><span data-ttu-id="f3cda-143">Проверка и устранение неполадок</span><span class="sxs-lookup"><span data-stu-id="f3cda-143">Verify and troubleshoot</span></span>

<span data-ttu-id="f3cda-144">После установки параметров занятости можно убедиться, что установка прошла успешно, с помощью командлета [Get – CsServerApplication](https://docs.microsoft.com/powershell/module/skype/get-csserverapplication?view=skype-ps) для получения списка серверных приложений.</span><span class="sxs-lookup"><span data-stu-id="f3cda-144">After installing Busy Options, you can verify that the installation was successful by using the [Get-CsServerApplication](https://docs.microsoft.com/powershell/module/skype/get-csserverapplication?view=skype-ps) cmdlet to retrieve the list of server applications.</span></span> <span data-ttu-id="f3cda-145">Если параметры занятости установлены правильно, выходные данные командлета должны показывать конфигурацию "занято", как показано ниже.</span><span class="sxs-lookup"><span data-stu-id="f3cda-145">If Busy Options is installed properly, the output of the cmdlet should show the Busy Options configuration as follows:</span></span>

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

<span data-ttu-id="f3cda-146">Кроме того, с помощью средства просмотра событий Windows можно проверить успешность установки параметров занятости и успешной загрузки Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="f3cda-146">You can also use Windows Event Viewer to verify that the Busy Options installation was successful and that Skype for Business Server successfully loaded Busy Options.</span></span> <span data-ttu-id="f3cda-147">Чтобы проверить параметры занятости, откройте **окно просмотра событий\> — журналы приложений и служб\> — Skype (или Lync) Server** и выполните поиск по идентификатору события 30253.</span><span class="sxs-lookup"><span data-stu-id="f3cda-147">To verify Busy Options, open **Event Viewer -\> Application and Services Logs -\> Skype (or Lync) Server** and search for Event ID = 30253.</span></span>
