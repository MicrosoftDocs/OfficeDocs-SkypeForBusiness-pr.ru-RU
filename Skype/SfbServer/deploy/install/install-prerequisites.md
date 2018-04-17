---
title: Установка обязательных компонентов для Skype для бизнеса Server 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 2/7/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: 2ef91a1e-2899-44c8-8e2c-527cb9114a0a
description: 'Summary: Learn about the servers and server roles you must configure before you install Skype for Business Server 2015. Download a free trial of Skype for Business Server 2015 from the Microsoft Evaluation center at: https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server.'
ms.openlocfilehash: 6f84b4f0a95c45297ad809e6b04217e711c3dd5e
ms.sourcegitcommit: dea27df69d948b7b9cc017b7023c4013cee8e4d1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/16/2018
---
# <a name="install-prerequisites-for-skype-for-business-server-2015"></a><span data-ttu-id="b9f61-104">Установка обязательных компонентов для Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="b9f61-104">Install prerequisites for Skype for Business Server 2015</span></span>
 
<span data-ttu-id="b9f61-105">**Summary:** Learn about the servers and server roles you must configure before you install Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="b9f61-105">**Summary:** Learn about the servers and server roles you must configure before you install Skype for Business Server 2015.</span></span> <span data-ttu-id="b9f61-106">Download a free trial of Skype for Business Server 2015 from the [Microsoft Evaluation center](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server).</span><span class="sxs-lookup"><span data-stu-id="b9f61-106">Download a free trial of Skype for Business Server 2015 from the [Microsoft Evaluation center](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server).</span></span>
  
<span data-ttu-id="b9f61-107">При настройке Windows Server на каждом из серверов в топологии устанавливаются роли и функции, которые являются необходимыми компонентами.</span><span class="sxs-lookup"><span data-stu-id="b9f61-107">Installing prerequisites consists of setting up Windows Server by installing the required roles and features on each of the servers in the topology.</span></span> <span data-ttu-id="b9f61-108">Требования зависят от роли, которую выполняет сервер в топологии.</span><span class="sxs-lookup"><span data-stu-id="b9f61-108">The requirements are based on the role the server will fulfill in the topology.</span></span> <span data-ttu-id="b9f61-109">Шаги 1–5 можно выполнять в любом порядке.</span><span class="sxs-lookup"><span data-stu-id="b9f61-109">You can do steps 1 through 5 in any order.</span></span> <span data-ttu-id="b9f61-110">Однако шаги 6, 7 и 8 необходимо выполнять в указанном порядке и только после шагов 1–5, как показано на схеме.</span><span class="sxs-lookup"><span data-stu-id="b9f61-110">However, you must do steps 6, 7, and 8 in order, and after steps 1 through 5, as outlined in the diagram.</span></span> <span data-ttu-id="b9f61-111">Обязательные компоненты устанавливаются на шаге 1 из 8.</span><span class="sxs-lookup"><span data-stu-id="b9f61-111">Installing prerequisites is step 1 of 8.</span></span>
  
![Обзорная схема - установка предварительных компонентов.](../../media/0a85349b-b398-4e04-8901-8f4bd25d8afe.png)
  
## <a name="setup-windows-server"></a><span data-ttu-id="b9f61-113">Настройка Windows Server</span><span class="sxs-lookup"><span data-stu-id="b9f61-113">Setup Windows Server</span></span>

<span data-ttu-id="b9f61-114">Skype for Business Server 2015 requires the Windows Server operating system and a number of prerequisites before it can be installed.</span><span class="sxs-lookup"><span data-stu-id="b9f61-114">Skype for Business Server 2015 requires the Windows Server operating system and a number of prerequisites before it can be installed.</span></span> <span data-ttu-id="b9f61-115">For details on planning for prerequisites, see [Server requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b9f61-115">For details on planning for prerequisites, see [Server requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md).</span></span> 
  
> [!TIP]
> <span data-ttu-id="b9f61-p105">Здесь приведена процедура для Windows Server 2012 R2. Процедуры для других версий Windows Server могут незначительно отличаться.</span><span class="sxs-lookup"><span data-stu-id="b9f61-p105">This procedure uses Windows Server 2012 R2. If you are using a different version of Windows Server, the procedure might be slightly different.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="b9f61-118">Before you begin, make sure that Windows Server is up-to-date by using Windows Update.</span><span class="sxs-lookup"><span data-stu-id="b9f61-118">Before you begin, make sure that Windows Server is up-to-date by using Windows Update.</span></span> 
  
![Windows Server обновлен.](../../media/a8d57a97-a55e-443b-b304-c534ae9a71b2.png)
  
<span data-ttu-id="b9f61-120">Посмотрите видео с инструкциями по **установке необходимых компонентов**:</span><span class="sxs-lookup"><span data-stu-id="b9f61-120">Watch the video steps for **install prerequisites**:</span></span>
  
> [!video https://www.microsoft.com/en-us/videoplayer/embed/02447c2a-5b26-432f-aad6-b9b05cc93478?autoplay=false]
  
### <a name="install-required-roles-and-features-for-front-end-servers"></a><span data-ttu-id="b9f61-121">Установка необходимых ролей и компонентов для серверов переднего плана</span><span class="sxs-lookup"><span data-stu-id="b9f61-121">Install required roles and features for front-end servers</span></span>

1. <span data-ttu-id="b9f61-122">Откройте диспетчер серверов и щелкните **Добавить роли и компоненты**.</span><span class="sxs-lookup"><span data-stu-id="b9f61-122">Open Server Manager, and click **Add roles and features**.</span></span>
    
2. <span data-ttu-id="b9f61-123">Прочитайте страницу **Перед началом работы** для ознакомления с процедурой установки ролей и компонентов в Windows Server, затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="b9f61-123">Read the **Before You Begin** page to familiarize yourself with installing roles and features in Windows Server, and then click **Next**.</span></span>
    
3. <span data-ttu-id="b9f61-124">Выберите **Установка ролей или компонентов** и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="b9f61-124">Select **Role-based or feature-based installation**, and click **Next**.</span></span>
    
4. <span data-ttu-id="b9f61-125">Select the server on which you will be installing Skype for Business Server 2015, and click **Next**.</span><span class="sxs-lookup"><span data-stu-id="b9f61-125">Select the server on which you will be installing Skype for Business Server 2015, and click **Next**.</span></span>
    
5. <span data-ttu-id="b9f61-126">Выберите роль **Web Server (IIS)** и при появлении всплывающего окна с обязательными компонентами щелкните **Добавить компоненты**, затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="b9f61-126">Select the **Web Server (IIS)** role, and when the required features window pops up, click **Add Features**, and then click **Next**.</span></span>
    
6. <span data-ttu-id="b9f61-127">Make sure the software features listed in [Software that should be installed before a Skype for Business Server 2015 deployment](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md#Software) are on the server that will run Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="b9f61-127">Make sure the software features listed in [Software that should be installed before a Skype for Business Server 2015 deployment](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md#Software) are on the server that will run Skype for Business Server 2015.</span></span> <span data-ttu-id="b9f61-128">Here's an abbreviated list:</span><span class="sxs-lookup"><span data-stu-id="b9f61-128">Here's an abbreviated list:</span></span>
    
   - <span data-ttu-id="b9f61-129">.NET Framework Features</span><span class="sxs-lookup"><span data-stu-id="b9f61-129">.NET Framework Features</span></span>
    
   - <span data-ttu-id="b9f61-130">Службы WCF</span><span class="sxs-lookup"><span data-stu-id="b9f61-130">WCF Services</span></span>
    
   - <span data-ttu-id="b9f61-131">Активация HTTP</span><span class="sxs-lookup"><span data-stu-id="b9f61-131">HTTP Activation</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="b9f61-p107">Для активации HTTP необходимы дополнительные компоненты. Щелкните **Добавить компоненты** в диалоговом окне предупреждения, всплывающем при выборе активации HTTP.</span><span class="sxs-lookup"><span data-stu-id="b9f61-p107">HTTP Activation requires additional features. Click **Add Features** to the warning dialog box that pops up when you select HTTP Activation.</span></span>
  
   - <span data-ttu-id="b9f61-134">Media Foundation (required by Front End Servers and Standard Edition servers used for conferencing.)</span><span class="sxs-lookup"><span data-stu-id="b9f61-134">Media Foundation (required by Front End Servers and Standard Edition servers used for conferencing.)</span></span>
    
   - <span data-ttu-id="b9f61-135">Средства удаленного администрирования сервера</span><span class="sxs-lookup"><span data-stu-id="b9f61-135">Remote Server Administration Tools</span></span>
    
   - <span data-ttu-id="b9f61-136">Средства администрирования ролей</span><span class="sxs-lookup"><span data-stu-id="b9f61-136">Role Administration Tools</span></span>
    
   - <span data-ttu-id="b9f61-137">AD DS</span><span class="sxs-lookup"><span data-stu-id="b9f61-137">AD DS</span></span> 
    
   - <span data-ttu-id="b9f61-138">AD LDS</span><span class="sxs-lookup"><span data-stu-id="b9f61-138">AD LDS</span></span>
    
   - <span data-ttu-id="b9f61-139">Windows Identity Foundation 3.5</span><span class="sxs-lookup"><span data-stu-id="b9f61-139">Windows Identity Foundation 3.5</span></span>
    
7. <span data-ttu-id="b9f61-140">Для продолжения работы с мастером нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="b9f61-140">Click **Next** to continue through the wizard.</span></span>
    
8. <span data-ttu-id="b9f61-141">Прочитайте заметки о **роли веб-сервера (IIS)**, затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="b9f61-141">Read through the notes about the **Web Server Role (IIS)**, and then click **Next**.</span></span>
    
9. <span data-ttu-id="b9f61-142">Выберите следующие **службы роли веб-сервера (IIS)**.</span><span class="sxs-lookup"><span data-stu-id="b9f61-142">Select the following **Web Server (IIS) role services**.</span></span>
    
   - <span data-ttu-id="b9f61-143">Основные возможности HTTP</span><span class="sxs-lookup"><span data-stu-id="b9f61-143">Common HTTP Features</span></span>
    
   - <span data-ttu-id="b9f61-144">Документ по умолчанию</span><span class="sxs-lookup"><span data-stu-id="b9f61-144">Default Document</span></span>
    
   - <span data-ttu-id="b9f61-145">Просмотр каталога</span><span class="sxs-lookup"><span data-stu-id="b9f61-145">Directory Browsing</span></span>
    
   - <span data-ttu-id="b9f61-146">Ошибки HTTP</span><span class="sxs-lookup"><span data-stu-id="b9f61-146">HTTP Errors</span></span>
    
   - <span data-ttu-id="b9f61-147">Статическое содержимое</span><span class="sxs-lookup"><span data-stu-id="b9f61-147">Static Content</span></span>
    
   - <span data-ttu-id="b9f61-148">Работоспособность и диагностика</span><span class="sxs-lookup"><span data-stu-id="b9f61-148">Health and Diagnostics</span></span>
    
   - <span data-ttu-id="b9f61-149">Ведение журнала HTTP</span><span class="sxs-lookup"><span data-stu-id="b9f61-149">HTTP Logging</span></span>
    
   - <span data-ttu-id="b9f61-150">Средства ведения журналов</span><span class="sxs-lookup"><span data-stu-id="b9f61-150">Logging Tools</span></span>
    
   - <span data-ttu-id="b9f61-151">Трассировка</span><span class="sxs-lookup"><span data-stu-id="b9f61-151">Tracing</span></span>
    
   - <span data-ttu-id="b9f61-152">Производительность</span><span class="sxs-lookup"><span data-stu-id="b9f61-152">Performance</span></span>
    
   - <span data-ttu-id="b9f61-153">Сжатие статического содержимого</span><span class="sxs-lookup"><span data-stu-id="b9f61-153">Static Content Compression</span></span>
    
   - <span data-ttu-id="b9f61-154">Сжатие динамического содержимого</span><span class="sxs-lookup"><span data-stu-id="b9f61-154">Dynamic Content Compression</span></span>
    
   - <span data-ttu-id="b9f61-155">Безопасность</span><span class="sxs-lookup"><span data-stu-id="b9f61-155">Security</span></span>
    
   - <span data-ttu-id="b9f61-156">Фильтрация запросов</span><span class="sxs-lookup"><span data-stu-id="b9f61-156">Request Filtering</span></span>
    
   - <span data-ttu-id="b9f61-157">Проверка подлинности с сопоставлением сертификатов клиентов</span><span class="sxs-lookup"><span data-stu-id="b9f61-157">Client Certificate Mapping Authentication</span></span>
    
   - <span data-ttu-id="b9f61-158">Проверка подлинности Windows</span><span class="sxs-lookup"><span data-stu-id="b9f61-158">Windows Authentication</span></span>
    
   - <span data-ttu-id="b9f61-159">Разработка приложений</span><span class="sxs-lookup"><span data-stu-id="b9f61-159">Application Development</span></span>
    
   - <span data-ttu-id="b9f61-160">.NET Extensibility 3.5</span><span class="sxs-lookup"><span data-stu-id="b9f61-160">.NET Extensibility 3.5</span></span>
    
   - <span data-ttu-id="b9f61-161">.NET Extensibility 4.5</span><span class="sxs-lookup"><span data-stu-id="b9f61-161">.NET Extensibility 4.5</span></span>
    
   - <span data-ttu-id="b9f61-162">ASP.NET 3.5</span><span class="sxs-lookup"><span data-stu-id="b9f61-162">ASP.NET 3.5</span></span>
    
   - <span data-ttu-id="b9f61-163">ASP.NET 4.5</span><span class="sxs-lookup"><span data-stu-id="b9f61-163">ASP.NET 4.5</span></span>
    
   - <span data-ttu-id="b9f61-164">Расширения ISAPI</span><span class="sxs-lookup"><span data-stu-id="b9f61-164">ISAPI Extensions</span></span>
    
   - <span data-ttu-id="b9f61-165">Фильтры ISAPI</span><span class="sxs-lookup"><span data-stu-id="b9f61-165">ISAPI Filters</span></span>
    
   - <span data-ttu-id="b9f61-166">Средства управления</span><span class="sxs-lookup"><span data-stu-id="b9f61-166">Management Tools</span></span>
    
   - <span data-ttu-id="b9f61-167">Консоль управления IIS</span><span class="sxs-lookup"><span data-stu-id="b9f61-167">IIS Management Console</span></span>
    
   - <span data-ttu-id="b9f61-168">Сценарии и средства управления для служб IIS</span><span class="sxs-lookup"><span data-stu-id="b9f61-168">IIS Management Scripts and Tools</span></span>
    
10. <span data-ttu-id="b9f61-169">Для продолжения работы с мастером нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="b9f61-169">Click **Next** to continue through the wizard.</span></span>
    
11. <span data-ttu-id="b9f61-170">Проверьте выбор компонентов установки, и убедитесь в том, что все обязательные компоненты выбраны, затем нажмите кнопку **Установить**.</span><span class="sxs-lookup"><span data-stu-id="b9f61-170">Review the installation selections to make sure all requirements are selected, and then click **Install**.</span></span>
    
    > [!CAUTION]
    > <span data-ttu-id="b9f61-171">По умолчанию в Windows Server 2012 R2 не устанавливаются все исходные файлы для обязательных компонентов.</span><span class="sxs-lookup"><span data-stu-id="b9f61-171">Windows Server 2012 R2 does not install all of the source files for the required features by default.</span></span> <span data-ttu-id="b9f61-172">Если сервер не подключен в сети Интернет, для установки обязательных компонентов потребуется установить носитель Windows Server 2012 R2 и выбрать **Указать альтернативный исходный путь**.</span><span class="sxs-lookup"><span data-stu-id="b9f61-172">If the server is not connected to the Internet, you will need to insert the Windows Server 2012 R2 media and select **Specify an alternate source path** in order to install the required features.</span></span> <span data-ttu-id="b9f61-173">Исходные файлы находятся в каталоге sources\sxs.</span><span class="sxs-lookup"><span data-stu-id="b9f61-173">The source files are located in the sources\sxs directory.</span></span> <span data-ttu-id="b9f61-174">Например, если носитель Windows Server 2012 R2 установлен в дисковод D, следует указать путь `d:\sources\sxs`.</span><span class="sxs-lookup"><span data-stu-id="b9f61-174">For example, if the Windows Server 2012 R2 media is in drive D, you would set the path to `d:\sources\sxs`.</span></span> <span data-ttu-id="b9f61-175">> It is important that you have the latest updates from Windows Update.</span><span class="sxs-lookup"><span data-stu-id="b9f61-175">> It is important that you have the latest updates from Windows Update.</span></span> <span data-ttu-id="b9f61-176">При отсутствии интернет-подключения потребуется вручную установить все необходимые пакеты обновления, а также обязательные компоненты для этих пакетов.</span><span class="sxs-lookup"><span data-stu-id="b9f61-176">If you are not connected to the Internet, you will need to manually install all relevant updates as well as any prerequisites to the required updates.</span></span> 
  
12. <span data-ttu-id="b9f61-177">Когда в диалоговом окне появляется сообщение о завершении установки, для окончательного завершения процесса необходимо перезагрузить сервер.</span><span class="sxs-lookup"><span data-stu-id="b9f61-177">When the dialog box indicates that the installation has completed, you will need to reboot the server to complete the process.</span></span>
    
13. <span data-ttu-id="b9f61-178">Снова запустите **центр обновления Windows** и проверьте наличие обновлений для установленных ролей и служб.</span><span class="sxs-lookup"><span data-stu-id="b9f61-178">Run **Windows Update** again to check if there are any updates to the roles and services that were installed.</span></span>
    
14. <span data-ttu-id="b9f61-179">If you will be using Skype for Business Server Control Panel on this server then you must also install Silverlight.</span><span class="sxs-lookup"><span data-stu-id="b9f61-179">If you will be using Skype for Business Server Control Panel on this server then you must also install Silverlight.</span></span> <span data-ttu-id="b9f61-180">To install Silverlight, see [Microsoft Silverlight](https://www.microsoft.com/silverlight/).</span><span class="sxs-lookup"><span data-stu-id="b9f61-180">To install Silverlight, see [Microsoft Silverlight](https://www.microsoft.com/silverlight/).</span></span>
    
<span data-ttu-id="b9f61-181">Обязательные компоненты можно установить с помощью следующей команды PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b9f61-181">The prerequisites can be installed by running the following PowerShell command.</span></span> <span data-ttu-id="b9f61-182">Следует учитывать, что при выполнении этой команды поиск исходных файлов осуществляется в определенном порядке.</span><span class="sxs-lookup"><span data-stu-id="b9f61-182">Note that the command looks for source files in a specific order.</span></span> <span data-ttu-id="b9f61-183">При наличии интернет-подключения команда обращается к центру обновления Windows.</span><span class="sxs-lookup"><span data-stu-id="b9f61-183">If you are online, the command accesses Windows Update.</span></span> <span data-ttu-id="b9f61-184">Однако в автономном режиме необходимо обеспечить доступность исходных файлов для команды.</span><span class="sxs-lookup"><span data-stu-id="b9f61-184">However, if you are offline, you need to make sure the source files are available to the command.</span></span> <span data-ttu-id="b9f61-185">For more information about using PowerShell to install roles and features, see [Install or Uninstall Roles, Role Services, or Features](https://technet.microsoft.com/en-us/library/hh831809.aspx) and [Install-WindowsFeature](https://technet.microsoft.com/en-us/library/jj205467.aspx).</span><span class="sxs-lookup"><span data-stu-id="b9f61-185">For more information about using PowerShell to install roles and features, see [Install or Uninstall Roles, Role Services, or Features](https://technet.microsoft.com/en-us/library/hh831809.aspx) and [Install-WindowsFeature](https://technet.microsoft.com/en-us/library/jj205467.aspx).</span></span> <span data-ttu-id="b9f61-186">Даже в случае установки обязательных компонентов с помощью команды PowerShell не забудьте по завершении установки снова запустить центр обновления Windows.</span><span class="sxs-lookup"><span data-stu-id="b9f61-186">Don't forget to run Windows Update again after you install prerequisites, even if you use the PowerShell command.</span></span>
```
Add-WindowsFeature NET-Framework-Core, RSAT-ADDS, Windows-Identity-Foundation, Web-Server, Web-Static-Content, Web-Default-Doc, Web-Http-Errors, Web-Dir-Browsing, Web-Asp-Net, Web-Net-Ext, Web-ISAPI-Ext, Web-ISAPI-Filter, Web-Http-Logging, Web-Log-Libraries, Web-Request-Monitor, Web-Http-Tracing, Web-Basic-Auth, Web-Windows-Auth, Web-Client-Auth, Web-Filtering, Web-Stat-Compression, Web-Dyn-Compression, NET-WCF-HTTP-Activation45, Web-Asp-Net45, Web-Mgmt-Tools, Web-Scripting-Tools, Web-Mgmt-Compat, Server-Media-Foundation, BITS
```

> [!IMPORTANT]
> <span data-ttu-id="b9f61-187">Для серверов, роль которых отличается от роли сервера переднего плана, например для директоров, серверов сохраняемого чата и пограничных серверов, предусмотрены особые наборы обязательных компонентов.</span><span class="sxs-lookup"><span data-stu-id="b9f61-187">The prerequisites for servers performing roles other than front-end server, such as the role of Director, Persistent Chat, or Edge, have their own prerequisites.</span></span> <span data-ttu-id="b9f61-188">For details on the exact prerequisites required by each server type, see [Server requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b9f61-188">For details on the exact prerequisites required by each server type, see [Server requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md).</span></span> 
  

