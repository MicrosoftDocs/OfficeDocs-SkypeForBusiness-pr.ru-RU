---
title: Установка и настройка параметров занятости в Skype для бизнеса Server
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 7/6/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- Strat_SB_Admin
ms.custom: ''
ms.assetid: fb0faac8-ca1c-4abb-9959-d19def294c64
description: Прочитайте о том, как установить и настроить параметры «занят» в Скайп для Business Server 2015.
ms.openlocfilehash: ff0f9a892d0882adcc2af0c4c41c1177b3488520
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="install-and-configure-busy-options-for-skype-for-business-server"></a><span data-ttu-id="57302-103">Установка и настройка параметров занятости в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="57302-103">Install and configure Busy Options for Skype for Business Server</span></span>
 
<span data-ttu-id="57302-104">Прочитайте о том, как установить и настроить параметры «занят» в Скайп для Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="57302-104">Read about how to install and configure Busy Options in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="57302-105">Параметры занятости были представлены в накопительном пакете обновлений за июль 2016 года и определяют политику голосовой связи, которая задает порядок обработки входящих звонков, поступающих во время обычного, удерживаемого или конференц-звонка.</span><span class="sxs-lookup"><span data-stu-id="57302-105">Busy Options is a new voice policy introduced in the July 2016 Cumulative Update that allows you to configure how incoming calls are handled when a user is already in a call or conference or has a call placed on hold.</span></span> <span data-ttu-id="57302-106">В зависимости от настроек новые или входящие звонки могут отклоняться с сигналом "занято" или переадресовываться на голосовую почту.</span><span class="sxs-lookup"><span data-stu-id="57302-106">New or incoming calls can be rejected with a busy signal or forwarded to voice mail.</span></span> 
  
<span data-ttu-id="57302-107">Если для организации включены параметры занятости, все ее пользователи, независимо от наличия доступа к корпоративной голосовой связи, могут использовать следующие параметры конфигурации:</span><span class="sxs-lookup"><span data-stu-id="57302-107">If Busy Options is enabled for the organization, all users at the Enterprise, both Enterprise Voice and non-Enterprise Voice users, can use the following configuration options:</span></span>
  
- <span data-ttu-id="57302-108">Сигнал занятости — если пользователь занят, все входящие звонки отклоняются и подается сигнал "занято".</span><span class="sxs-lookup"><span data-stu-id="57302-108">Busy on Busy - In which new incoming calls will be rejected with a busy signal if the user is busy.</span></span>
    
- <span data-ttu-id="57302-109">Голосовая почта — если пользователь занят, все входящие звонки переадресуются на голосовую почту.</span><span class="sxs-lookup"><span data-stu-id="57302-109">Voicemail on Busy - In which new incoming calls will be forwarded to voice mail if the user is busy.</span></span>
    
<span data-ttu-id="57302-110">Независимо от установленных параметров занятости, во время обычного, удерживаемого или конференц-звонка пользователи могут выполнять новые звонки.  </span><span class="sxs-lookup"><span data-stu-id="57302-110">Regardless of how their busy options are configured, users in a call or conference, or those with a call on hold, are not prevented from initiating new calls or conferences.</span></span> 
  
<span data-ttu-id="57302-111">Дополнительные сведения о функции «занят» параметры в разделе [Планирование занят параметры Скайп для Business Server](../../plan-your-deployment/enterprise-voice-solution/busy-options.md).</span><span class="sxs-lookup"><span data-stu-id="57302-111">For more information about the Busy Options feature, see [Plan for Busy Options for Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/busy-options.md).</span></span>
  
## <a name="install"></a><span data-ttu-id="57302-112">Установка </span><span class="sxs-lookup"><span data-stu-id="57302-112">Install</span></span>

<span data-ttu-id="57302-113">Убедитесь, что у вас есть последней версии Скайп для установки Business Server и, что установлены последние обновления.</span><span class="sxs-lookup"><span data-stu-id="57302-113">Make sure you have the latest version of Skype for Business Server installed and that you have installed the most recent patch.</span></span> <span data-ttu-id="57302-114">Для этого сначала остановите все службы и запустите Скайп для установки обновлений Business Server следующим образом:</span><span class="sxs-lookup"><span data-stu-id="57302-114">To do this, first stop all services, and then run the Skype for Business Server update installer as follows:</span></span>
  
1. <span data-ttu-id="57302-115">Выполните команду Stop-CsWindowsService.</span><span class="sxs-lookup"><span data-stu-id="57302-115">Run the Stop-CsWindowsService command.</span></span>
    
2. <span data-ttu-id="57302-116">Запустите файл SkypeServerUpdateInstaller.exe для каждого сервера переднего плана в пуле.</span><span class="sxs-lookup"><span data-stu-id="57302-116">Run the SkypeServerUpdateInstaller.exe installer on each Front End server in a pool.</span></span>
    
3. <span data-ttu-id="57302-117">Если необходимо реализовать отработку отказа на серверах обеспечения связи в филиалах, запустите установщик SkypeServerUpdateInstaller.exe на каждом из таких серверов.</span><span class="sxs-lookup"><span data-stu-id="57302-117">Run the SkypeServerUpdateInstaller.exe installer on each Survivable Branch Server (SBS), if you want to ensure support for failover on SBS.</span></span>
    
<span data-ttu-id="57302-p103">Установщик разворачивает последнюю версию приложения параметров занятости, однако оно не будет включено по умолчанию. Для его включения необходимо выполнить приведенные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="57302-p103">The installer will deploy the latest version of the Busy Options application. However, the application is not enabled by default. To enable the application, perform the following steps:</span></span>
  
1. <span data-ttu-id="57302-121">Выполните командлет [Set-CsVoicePolicy](https://docs.microsoft.com/powershell/module/skype/set-csvoicepolicy?view=skype-ps) глобально Включение параметров «занят», как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="57302-121">Run the [Set-CsVoicePolicy](https://docs.microsoft.com/powershell/module/skype/set-csvoicepolicy?view=skype-ps) cmdlet to globally enable Busy Options as shown in the following example:</span></span>
    
  ```
  Set-CsVoicePolicy -EnableBusyOptions $true
  ```

2. <span data-ttu-id="57302-122">Затем, если для сайта настроена политика голосовой связи, необходимо включить параметры занятости для этой политики следующим образом.</span><span class="sxs-lookup"><span data-stu-id="57302-122">Next, if the site has a voice policy is place, you must enable Busy Options for the voice policy as follows:</span></span>
    
    <span data-ttu-id="57302-123">Во-первых выполните [Командлет Get-CsSite](https://docs.microsoft.com/powershell/module/skype/get-cssite?view=skype-ps) для получения имени узла.</span><span class="sxs-lookup"><span data-stu-id="57302-123">First, run [Get-CsSite](https://docs.microsoft.com/powershell/module/skype/get-cssite?view=skype-ps) to retrieve the name of the site:</span></span>
    
   ```
   Get-CsSite
   ```

    <span data-ttu-id="57302-124">Используйте значение Identity (например: Site: Redmond1) извлекается из командлет Get-CsSite для получения политики голосовой связи сайта, как показано ниже:</span><span class="sxs-lookup"><span data-stu-id="57302-124">Use the Identity value (for example: Site:Redmond1) retrieved from Get-CsSite to retrieve the voice policy of the site as follows:</span></span>
    
   ```
   Get-CsVoicePolicy -Identity Site:Redmond1
   ```

    <span data-ttu-id="57302-125">Если для сайта существует политика голосовой связи, выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="57302-125">If a voice policy exists for the site, run the following command:</span></span>
    
   ```
   Set-CsVoicePolicy -Identity Site:Redmond1 -EnableBusyOptions $true
   ```

3. <span data-ttu-id="57302-126">Затем выполните командлет [New-CsServerApplication](https://docs.microsoft.com/powershell/module/skype/new-csserverapplication?view=skype-ps) , чтобы добавить параметры «занят» в список серверных приложений, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="57302-126">Next, run the [New-CsServerApplication](https://docs.microsoft.com/powershell/module/skype/new-csserverapplication?view=skype-ps) cmdlet to add Busy Options to the list of server applications as shown in the following example:</span></span>
    
   ```
   New-CsServerApplication -Identity 'Service:Registrar:%FQDN%/BusyOptions' -Uri http://www.microsoft.com/LCS/BusyOptions -Critical $False -Enabled $True -Priority (Get-CsServerApplication -Identity 'Service:Registrar:%FQDN%/UserServices').Priority
   ```

    > [!NOTE]
    > <span data-ttu-id="57302-127">Полное доменное имя % необходимо заменить на полное доменное имя конкретного пула.</span><span class="sxs-lookup"><span data-stu-id="57302-127">You must replace %FQDN% with the fully-qualified domain name of a specific pool.</span></span> 
  
4. <span data-ttu-id="57302-128">Затем выполните командлет [Update-CsAdminRole](https://docs.microsoft.com/powershell/module/skype/update-csadminrole?view=skype-ps) , чтобы обновить роли управления ДОСТУПОМ на основе ролей доступ по командлетам занят параметры, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="57302-128">Next, run the [Update-CsAdminRole](https://docs.microsoft.com/powershell/module/skype/update-csadminrole?view=skype-ps) cmdlet to update the Role-based access control (RBAC) roles for the Busy Options cmdlets as shown in the following example:</span></span>
    
   ```
   Update-CsAdminRole
   ```

5. <span data-ttu-id="57302-129">И, наконец запустите Скайп для служб Business Server Windows на всех серверах переднего плана во всех пулах, где «занят» параметры была установлена и включена, выполнив команду [Start-CsWindowsService](https://docs.microsoft.com/powershell/module/skype/start-cswindowsservice?view=skype-ps) :</span><span class="sxs-lookup"><span data-stu-id="57302-129">Finally, start the Skype for Business Server Windows services on all the Front End servers in all the pools where Busy Options was installed and enabled by running the [Start-CsWindowsService](https://docs.microsoft.com/powershell/module/skype/start-cswindowsservice?view=skype-ps) command:</span></span>
    
   ```
   Start-CsWindowsService
   ```

## <a name="configure"></a><span data-ttu-id="57302-130">Настройка</span><span class="sxs-lookup"><span data-stu-id="57302-130">Configure</span></span>

<span data-ttu-id="57302-131">Чтобы настроить параметры «занят», используйте командлет [Set-CsBusyOptions](http://technet.microsoft.com/library/8ffbb832-3e55-4d6c-9a7c-5ce2df22de2e.aspx) .</span><span class="sxs-lookup"><span data-stu-id="57302-131">To configure Busy Options, use the [Set-CsBusyOptions](http://technet.microsoft.com/library/8ffbb832-3e55-4d6c-9a7c-5ce2df22de2e.aspx) cmdlet.</span></span>
  
<span data-ttu-id="57302-p104">Например, следующая команда задает параметры занятости для пользователя "Ken Myer". В такой конфигурации при поступлении звонка этому пользователю во время активного звонка возвращается сигнал "занято":</span><span class="sxs-lookup"><span data-stu-id="57302-p104">For example, the following command configures busy options for the user "Ken Myer". In this configuration, any call to "Ken Myer" will return a busy signal when he is already in a call:</span></span>
  
```
Set-CsBusyOptions -Identity "Ken Myer"  -ActionType BusyOnBusy

```

<span data-ttu-id="57302-134">В следующем примере эта команда задает параметры занятости для пользователя "Chrystal Velasquez".</span><span class="sxs-lookup"><span data-stu-id="57302-134">In the next example, the command configures busy options for the user "Chrystal Velasquez".</span></span> <span data-ttu-id="57302-135">В такой конфигурации новые входящие звонки, поступающие этому пользователю во время активного звонка, переадресуются на голосовую почту:</span><span class="sxs-lookup"><span data-stu-id="57302-135">In this configuration, new incoming calls to "Chrystal Velasquez" will be forwarded to voice mail when she is already in a call:</span></span>
  
```
Set-CsBusyOptions -Identity "Chrystal Velasquez" -ActionType VoicemailOnBusy 

```

<span data-ttu-id="57302-136">Сведения о занятости параметры конфигурации можно извлечь с помощью командлета [Get-CsBusyOptions](http://technet.microsoft.com/library/ff0e3b1c-c41d-41e4-9468-0cb057aef9fb.aspx) .</span><span class="sxs-lookup"><span data-stu-id="57302-136">You can retrieve configuration information about Busy Options by using the [Get-CsBusyOptions](http://technet.microsoft.com/library/ff0e3b1c-c41d-41e4-9468-0cb057aef9fb.aspx) cmdlet.</span></span> <span data-ttu-id="57302-137">В следующем примере возвращается текущее значение «занят» параметры «KenMyer@Contoso.com»:</span><span class="sxs-lookup"><span data-stu-id="57302-137">The following example returns the Busy Options setting for "KenMyer@Contoso.com":</span></span>
  
```
Get-CsBusyOptions -Identity sip:KenMyer@Contoso.com
```

<span data-ttu-id="57302-138">Параметры «занят» можно удалить с помощью командлета [Remove-CsBusyOptions](http://technet.microsoft.com/library/159e5931-10f1-4226-bcc4-38548f88f0d4.aspx) .</span><span class="sxs-lookup"><span data-stu-id="57302-138">You can remove Busy Options by using the [Remove-CsBusyOptions](http://technet.microsoft.com/library/159e5931-10f1-4226-bcc4-38548f88f0d4.aspx) cmdlet.</span></span> <span data-ttu-id="57302-139">Следующая команда удаляет параметры занятости для пользователя "Ken Myer":</span><span class="sxs-lookup"><span data-stu-id="57302-139">The following command removes Busy Options for "Ken Myer":</span></span>
  
```
Remove-CsBusyOptions -Identity "Ken Myer"

```

<span data-ttu-id="57302-140">Подробные сведения о командлетах, используется для настройки параметров «занят» см в разделе справочные материалы для [Набора CsBusyOptions](http://technet.microsoft.com/library/8ffbb832-3e55-4d6c-9a7c-5ce2df22de2e.aspx), [Get-CsBusyOptions](http://technet.microsoft.com/library/ff0e3b1c-c41d-41e4-9468-0cb057aef9fb.aspx)и [Remove-CsBusyOptions](http://technet.microsoft.com/library/159e5931-10f1-4226-bcc4-38548f88f0d4.aspx).</span><span class="sxs-lookup"><span data-stu-id="57302-140">For detailed information about the cmdlets you use to configure Busy Options, see the technical reference content for [Set-CsBusyOptions](http://technet.microsoft.com/library/8ffbb832-3e55-4d6c-9a7c-5ce2df22de2e.aspx), [Get-CsBusyOptions](http://technet.microsoft.com/library/ff0e3b1c-c41d-41e4-9468-0cb057aef9fb.aspx), and [Remove-CsBusyOptions](http://technet.microsoft.com/library/159e5931-10f1-4226-bcc4-38548f88f0d4.aspx).</span></span>
  
## <a name="enable-logging"></a><span data-ttu-id="57302-141">Включение ведения журналов</span><span class="sxs-lookup"><span data-stu-id="57302-141">Enable logging</span></span>

<span data-ttu-id="57302-142">Чтобы включить ведение журналов с использованием соответствующей централизованной службы, введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="57302-142">To enable logging for Busy Options by using the Centralized Logging Service, specify the following:</span></span>
  
```
$p1 = New-CsClsProvider -Name S4 -Type WPP -Level Info -Flags All
$p2 = New-CsClsProvider -Name Sipstack -Type WPP -Level Info -Flags
 "TF_PROTOCOL,TF_CONNECTION,TF_SECURITY,TF_DIAG,TF_SHOW_CONFERENCE,TF_SHOW_ALLREQUESTS,TF_SHOW_ALLSIPHEADERS" -Role Registrar
$p3 = New-CsClsProvider -Name BusyOptions -Type WPP -Level Verbose -Flags All
New-CsClsScenario -Parent Global -Name BusyOptions -Provider @{Add=$p1,$p2,$p3} 

```

## <a name="verify-and-troubleshoot"></a><span data-ttu-id="57302-143">Проверка и устранение неполадок</span><span class="sxs-lookup"><span data-stu-id="57302-143">Verify and troubleshoot</span></span>

<span data-ttu-id="57302-144">После установки параметров «занят», вы можете проверить, что установка прошла успешно, с помощью командлета [Get-CsServerApplication](https://docs.microsoft.com/powershell/module/skype/get-csserverapplication?view=skype-ps) для получения списка серверов приложений.</span><span class="sxs-lookup"><span data-stu-id="57302-144">After installing Busy Options, you can verify that the installation was successful by using the [Get-CsServerApplication](https://docs.microsoft.com/powershell/module/skype/get-csserverapplication?view=skype-ps) cmdlet to retrieve the list of server applications.</span></span> <span data-ttu-id="57302-145">Если параметры занятости установлены надлежащим образом, этот командлет вернет следующую конфигурацию этой функции:</span><span class="sxs-lookup"><span data-stu-id="57302-145">If Busy Options is installed properly, the output of the cmdlet should show the Busy Options configuration as follows:</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="57302-146">Identity </span><span class="sxs-lookup"><span data-stu-id="57302-146">Identity</span></span>  <br/> | <span data-ttu-id="57302-147"> : Service:Registrar:pool0.vdomain.com/BusyOptions</span><span class="sxs-lookup"><span data-stu-id="57302-147">: Service:Registrar:pool0.vdomain.com/BusyOptions</span></span> <br/> |
|<span data-ttu-id="57302-148">Priority</span><span class="sxs-lookup"><span data-stu-id="57302-148">Priority</span></span>  <br/> | <span data-ttu-id="57302-149">: 5</span><span class="sxs-lookup"><span data-stu-id="57302-149">: 5</span></span> <br/> |
|<span data-ttu-id="57302-150">Uri </span><span class="sxs-lookup"><span data-stu-id="57302-150">Uri</span></span>  <br/> |<span data-ttu-id="57302-151">: http://www.microsoft.com/LCS/BusyOptions</span><span class="sxs-lookup"><span data-stu-id="57302-151"></span></span>  <br/> |
|<span data-ttu-id="57302-152">Имя</span><span class="sxs-lookup"><span data-stu-id="57302-152">Name</span></span>  <br/> | <span data-ttu-id="57302-153"> : BusyOptions</span><span class="sxs-lookup"><span data-stu-id="57302-153">: BusyOptions</span></span> <br/> |
|<span data-ttu-id="57302-154">Включено</span><span class="sxs-lookup"><span data-stu-id="57302-154">Enabled</span></span>  <br/> |<span data-ttu-id="57302-155">: True</span><span class="sxs-lookup"><span data-stu-id="57302-155">: True</span></span>  <br/> |
|<span data-ttu-id="57302-156">Critical</span><span class="sxs-lookup"><span data-stu-id="57302-156">Critical</span></span>  <br/> |<span data-ttu-id="57302-157">: False</span><span class="sxs-lookup"><span data-stu-id="57302-157">: False</span></span>  <br/> |
|<span data-ttu-id="57302-158">Имя_сценария</span><span class="sxs-lookup"><span data-stu-id="57302-158">ScriptName</span></span>  <br/> | <span data-ttu-id="57302-159">:</span><span class="sxs-lookup"><span data-stu-id="57302-159"></span></span> <br/> |
|<span data-ttu-id="57302-160">Script </span><span class="sxs-lookup"><span data-stu-id="57302-160">Script</span></span>  <br/> | <span data-ttu-id="57302-161">:</span><span class="sxs-lookup"><span data-stu-id="57302-161"></span></span> <br/> |
   
<span data-ttu-id="57302-162">Также можно использовать средство просмотра событий Windows для проверки успешности установки параметров «занят» и что Скайп для Business Server успешно загружен параметры «занят».</span><span class="sxs-lookup"><span data-stu-id="57302-162">You can also use Windows Event Viewer to verify that the Busy Options installation was successful and that Skype for Business Server successfully loaded Busy Options.</span></span> <span data-ttu-id="57302-163">Чтобы проверить параметры «занят», откройте **окно просмотра событий -\> журналы служб - приложений и\> Скайп (или Lync) сервера** и выполните поиск события ID = 30253.</span><span class="sxs-lookup"><span data-stu-id="57302-163">To verify Busy Options, open **Event Viewer -\> Application and Services Logs -\> Skype (or Lync) Server** and search for Event ID = 30253.</span></span>
  

