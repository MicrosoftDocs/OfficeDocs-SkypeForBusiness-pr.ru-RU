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
description: 'Сводка: Сведения о серверов и ролей серверов, необходимо настроить перед установкой Скайп для Business Server 2015. Загрузить бесплатную пробную версию программы Скайп для 2015 Business Server в центре Microsoft оценки по: https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server.'
ms.openlocfilehash: 350f64a2808e51866cd5720cb1955259ff773c81
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/28/2018
---
# <a name="install-prerequisites-for-skype-for-business-server-2015"></a><span data-ttu-id="86221-104">Установка обязательных компонентов для Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="86221-104">Install prerequisites for Skype for Business Server 2015</span></span>
 
<span data-ttu-id="86221-105">**Сводка:** Сведения о серверах и роли сервера, которые необходимо настроить перед установкой Скайп для Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="86221-105">**Summary:** Learn about the servers and server roles you must configure before you install Skype for Business Server 2015.</span></span> <span data-ttu-id="86221-106">Загрузите бесплатную пробную версию программы Скайп для Business Server 2015 [Центр оценки Microsoft](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server).</span><span class="sxs-lookup"><span data-stu-id="86221-106">Download a free trial of Skype for Business Server 2015 from the [Microsoft Evaluation center](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server).</span></span>
  
<span data-ttu-id="86221-107">При настройке Windows Server на каждом из серверов в топологии устанавливаются роли и функции, которые являются необходимыми компонентами.</span><span class="sxs-lookup"><span data-stu-id="86221-107">Installing prerequisites consists of setting up Windows Server by installing the required roles and features on each of the servers in the topology.</span></span> <span data-ttu-id="86221-108">Требования зависят от роли, которую выполняет сервер в топологии.</span><span class="sxs-lookup"><span data-stu-id="86221-108">The requirements are based on the role the server will fulfill in the topology.</span></span> <span data-ttu-id="86221-109">Шаги 1–5 можно выполнять в любом порядке.</span><span class="sxs-lookup"><span data-stu-id="86221-109">You can do steps 1 through 5 in any order.</span></span> <span data-ttu-id="86221-110">Однако шаги 6, 7 и 8 необходимо выполнять в указанном порядке и только после шагов 1–5, как показано на схеме.</span><span class="sxs-lookup"><span data-stu-id="86221-110">However, you must do steps 6, 7, and 8 in order, and after steps 1 through 5, as outlined in the diagram.</span></span> <span data-ttu-id="86221-111">Обязательные компоненты устанавливаются на шаге 1 из 8.</span><span class="sxs-lookup"><span data-stu-id="86221-111">Installing prerequisites is step 1 of 8.</span></span>
  
![Обзорная схема - установка предварительных компонентов.](../../media/0a85349b-b398-4e04-8901-8f4bd25d8afe.png)
  
## <a name="setup-windows-server"></a><span data-ttu-id="86221-113">Настройка Windows Server</span><span class="sxs-lookup"><span data-stu-id="86221-113">Setup Windows Server</span></span>

<span data-ttu-id="86221-114">Скайп для Business Server 2015 требуется операционная система Windows Server и число необходимых компонентов можно установить.</span><span class="sxs-lookup"><span data-stu-id="86221-114">Skype for Business Server 2015 requires the Windows Server operating system and a number of prerequisites before it can be installed.</span></span> <span data-ttu-id="86221-115">Для получения дополнительных сведений о планировании наличие необходимых компонентов просмотрите [требования к серверу для Скайп для Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="86221-115">For details on planning for prerequisites, see [Server requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md).</span></span> 
  
> [!TIP]
> <span data-ttu-id="86221-p105">Здесь приведена процедура для Windows Server 2012 R2. Процедуры для других версий Windows Server могут незначительно отличаться.</span><span class="sxs-lookup"><span data-stu-id="86221-p105">This procedure uses Windows Server 2012 R2. If you are using a different version of Windows Server, the procedure might be slightly different.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="86221-118">Прежде чем начать, убедитесь, что Windows Server актуальных с помощью центра обновления Windows.</span><span class="sxs-lookup"><span data-stu-id="86221-118">Before you begin, make sure that Windows Server is up-to-date by using Windows Update.</span></span> 
  
![Windows Server обновлен.](../../media/a8d57a97-a55e-443b-b304-c534ae9a71b2.png)
  
<span data-ttu-id="86221-120">Посмотрите видео с инструкциями по **установке необходимых компонентов**:</span><span class="sxs-lookup"><span data-stu-id="86221-120">Watch the video steps for **install prerequisites**:</span></span>
  
![Ваш браузер не поддерживает видео. Установите Microsoft Silverlight, Adobe Flash Player или Internet Explorer 9.](../../media/MSN_Video_Widget.gif)
  
### <a name="install-required-roles-and-features-for-front-end-servers"></a><span data-ttu-id="86221-123">Установка необходимых ролей и компонентов для серверов переднего плана</span><span class="sxs-lookup"><span data-stu-id="86221-123">Install required roles and features for front-end servers</span></span>

1. <span data-ttu-id="86221-124">Откройте диспетчер серверов и щелкните **Добавить роли и компоненты**.</span><span class="sxs-lookup"><span data-stu-id="86221-124">Open Server Manager, and click **Add roles and features**.</span></span>
    
2. <span data-ttu-id="86221-125">Прочитайте страницу **Перед началом работы** для ознакомления с процедурой установки ролей и компонентов в Windows Server, затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="86221-125">Read the **Before You Begin** page to familiarize yourself with installing roles and features in Windows Server, and then click **Next**.</span></span>
    
3. <span data-ttu-id="86221-126">Выберите **Установка ролей или компонентов** и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="86221-126">Select **Role-based or feature-based installation**, and click **Next**.</span></span>
    
4. <span data-ttu-id="86221-127">Выберите сервер, на котором нужно быть установка Скайп для Business Server 2015 и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="86221-127">Select the server on which you will be installing Skype for Business Server 2015, and click **Next**.</span></span>
    
5. <span data-ttu-id="86221-128">Выберите роль **Web Server (IIS)** и при появлении всплывающего окна с обязательными компонентами щелкните **Добавить компоненты**, затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="86221-128">Select the **Web Server (IIS)** role, and when the required features window pops up, click **Add Features**, and then click **Next**.</span></span>
    
6. <span data-ttu-id="86221-129">Убедитесь в том, компоненты программного обеспечения, в списке [программного обеспечения, перед Скайп для развертывания Business Server 2015, должны быть установлены](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md#Software) на сервере, на котором будет запущен Скайп для Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="86221-129">Make sure the software features listed in [Software that should be installed before a Skype for Business Server 2015 deployment](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md#Software) are on the server that will run Skype for Business Server 2015.</span></span> <span data-ttu-id="86221-130">Вот сокращенный список.</span><span class="sxs-lookup"><span data-stu-id="86221-130">Here's an abbreviated list:</span></span>
    
   - <span data-ttu-id="86221-131">Возможности .NET framework</span><span class="sxs-lookup"><span data-stu-id="86221-131">.NET Framework Features</span></span>
    
   - <span data-ttu-id="86221-132">Службы WCF</span><span class="sxs-lookup"><span data-stu-id="86221-132">WCF Services</span></span>
    
   - <span data-ttu-id="86221-133">Активация HTTP</span><span class="sxs-lookup"><span data-stu-id="86221-133">HTTP Activation</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="86221-p108">Для активации HTTP необходимы дополнительные компоненты. Щелкните **Добавить компоненты** в диалоговом окне предупреждения, всплывающем при выборе активации HTTP.</span><span class="sxs-lookup"><span data-stu-id="86221-p108">HTTP Activation requires additional features. Click **Add Features** to the warning dialog box that pops up when you select HTTP Activation.</span></span>
  
   - <span data-ttu-id="86221-136">База мультимедиа (требуется для серверов переднего плана и серверах Standard Edition для конференц-связи).</span><span class="sxs-lookup"><span data-stu-id="86221-136">Media Foundation (required by Front End Servers and Standard Edition servers used for conferencing.)</span></span>
    
   - <span data-ttu-id="86221-137">Средства удаленного администрирования сервера</span><span class="sxs-lookup"><span data-stu-id="86221-137">Remote Server Administration Tools</span></span>
    
   - <span data-ttu-id="86221-138">Средства администрирования ролей</span><span class="sxs-lookup"><span data-stu-id="86221-138">Role Administration Tools</span></span>
    
   - <span data-ttu-id="86221-139">ДОМЕННЫЕ СЛУЖБЫ ACTIVE DIRECTORY</span><span class="sxs-lookup"><span data-stu-id="86221-139">AD DS</span></span> 
    
   - <span data-ttu-id="86221-140">AD LDS</span><span class="sxs-lookup"><span data-stu-id="86221-140">AD LDS</span></span>
    
   - <span data-ttu-id="86221-141">Windows Identity Foundation 3.5</span><span class="sxs-lookup"><span data-stu-id="86221-141">Windows Identity Foundation 3.5</span></span>
    
7. <span data-ttu-id="86221-142">Для продолжения работы с мастером нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="86221-142">Click **Next** to continue through the wizard.</span></span>
    
8. <span data-ttu-id="86221-143">Прочитайте заметки о **роли веб-сервера (IIS)**, затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="86221-143">Read through the notes about the **Web Server Role (IIS)**, and then click **Next**.</span></span>
    
9. <span data-ttu-id="86221-144">Выберите следующие **службы роли веб-сервера (IIS)**.</span><span class="sxs-lookup"><span data-stu-id="86221-144">Select the following **Web Server (IIS) role services**.</span></span>
    
   - <span data-ttu-id="86221-145">Основные возможности HTTP</span><span class="sxs-lookup"><span data-stu-id="86221-145">Common HTTP Features</span></span>
    
   - <span data-ttu-id="86221-146">Документ по умолчанию</span><span class="sxs-lookup"><span data-stu-id="86221-146">Default Document</span></span>
    
   - <span data-ttu-id="86221-147">Просмотр каталога</span><span class="sxs-lookup"><span data-stu-id="86221-147">Directory Browsing</span></span>
    
   - <span data-ttu-id="86221-148">Ошибки HTTP</span><span class="sxs-lookup"><span data-stu-id="86221-148">HTTP Errors</span></span>
    
   - <span data-ttu-id="86221-149">Статическое содержимое</span><span class="sxs-lookup"><span data-stu-id="86221-149">Static Content</span></span>
    
   - <span data-ttu-id="86221-150">Работоспособность и диагностика</span><span class="sxs-lookup"><span data-stu-id="86221-150">Health and Diagnostics</span></span>
    
   - <span data-ttu-id="86221-151">Ведение журнала HTTP</span><span class="sxs-lookup"><span data-stu-id="86221-151">HTTP Logging</span></span>
    
   - <span data-ttu-id="86221-152">Средства ведения журналов</span><span class="sxs-lookup"><span data-stu-id="86221-152">Logging Tools</span></span>
    
   - <span data-ttu-id="86221-153">Трассировка</span><span class="sxs-lookup"><span data-stu-id="86221-153">Tracing</span></span>
    
   - <span data-ttu-id="86221-154">Производительность</span><span class="sxs-lookup"><span data-stu-id="86221-154">Performance</span></span>
    
   - <span data-ttu-id="86221-155">Сжатие статического содержимого</span><span class="sxs-lookup"><span data-stu-id="86221-155">Static Content Compression</span></span>
    
   - <span data-ttu-id="86221-156">Сжатие динамического содержимого</span><span class="sxs-lookup"><span data-stu-id="86221-156">Dynamic Content Compression</span></span>
    
   - <span data-ttu-id="86221-157">Безопасность</span><span class="sxs-lookup"><span data-stu-id="86221-157">Security</span></span>
    
   - <span data-ttu-id="86221-158">Фильтрация запросов</span><span class="sxs-lookup"><span data-stu-id="86221-158">Request Filtering</span></span>
    
   - <span data-ttu-id="86221-159">Проверка подлинности с сопоставлением сертификатов клиентов</span><span class="sxs-lookup"><span data-stu-id="86221-159">Client Certificate Mapping Authentication</span></span>
    
   - <span data-ttu-id="86221-160">Проверка подлинности Windows</span><span class="sxs-lookup"><span data-stu-id="86221-160">Windows Authentication</span></span>
    
   - <span data-ttu-id="86221-161">Разработка приложений</span><span class="sxs-lookup"><span data-stu-id="86221-161">Application Development</span></span>
    
   - <span data-ttu-id="86221-162">.NET Extensibility 3.5</span><span class="sxs-lookup"><span data-stu-id="86221-162">.NET Extensibility 3.5</span></span>
    
   - <span data-ttu-id="86221-163">.NET Extensibility 4.5</span><span class="sxs-lookup"><span data-stu-id="86221-163">.NET Extensibility 4.5</span></span>
    
   - <span data-ttu-id="86221-164">ASP.NET 3.5</span><span class="sxs-lookup"><span data-stu-id="86221-164">ASP.NET 3.5</span></span>
    
   - <span data-ttu-id="86221-165">ASP.NET 4.5</span><span class="sxs-lookup"><span data-stu-id="86221-165">ASP.NET 4.5</span></span>
    
   - <span data-ttu-id="86221-166">Расширения ISAPI</span><span class="sxs-lookup"><span data-stu-id="86221-166">ISAPI Extensions</span></span>
    
   - <span data-ttu-id="86221-167">Фильтры ISAPI</span><span class="sxs-lookup"><span data-stu-id="86221-167">ISAPI Filters</span></span>
    
   - <span data-ttu-id="86221-168">Средства управления</span><span class="sxs-lookup"><span data-stu-id="86221-168">Management Tools</span></span>
    
   - <span data-ttu-id="86221-169">Консоль управления IIS</span><span class="sxs-lookup"><span data-stu-id="86221-169">IIS Management Console</span></span>
    
   - <span data-ttu-id="86221-170">Сценарии и средства управления для служб IIS</span><span class="sxs-lookup"><span data-stu-id="86221-170">IIS Management Scripts and Tools</span></span>
    
10. <span data-ttu-id="86221-171">Для продолжения работы с мастером нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="86221-171">Click **Next** to continue through the wizard.</span></span>
    
11. <span data-ttu-id="86221-172">Проверьте выбор компонентов установки, и убедитесь в том, что все обязательные компоненты выбраны, затем нажмите кнопку **Установить**.</span><span class="sxs-lookup"><span data-stu-id="86221-172">Review the installation selections to make sure all requirements are selected, and then click **Install**.</span></span>
    
    > [!CAUTION]
    > <span data-ttu-id="86221-173">По умолчанию в Windows Server 2012 R2 не устанавливаются все исходные файлы для обязательных компонентов.</span><span class="sxs-lookup"><span data-stu-id="86221-173">Windows Server 2012 R2 does not install all of the source files for the required features by default.</span></span> <span data-ttu-id="86221-174">Если сервер не подключен в сети Интернет, для установки обязательных компонентов потребуется установить носитель Windows Server 2012 R2 и выбрать **Указать альтернативный исходный путь**.</span><span class="sxs-lookup"><span data-stu-id="86221-174">If the server is not connected to the Internet, you will need to insert the Windows Server 2012 R2 media and select **Specify an alternate source path** in order to install the required features.</span></span> <span data-ttu-id="86221-175">Исходные файлы находятся в каталоге sources\sxs.</span><span class="sxs-lookup"><span data-stu-id="86221-175">The source files are located in the sources\sxs directory.</span></span> <span data-ttu-id="86221-176">Например, если носитель Windows Server 2012 R2 установлен в дисковод D, следует указать путь `d:\sources\sxs`.</span><span class="sxs-lookup"><span data-stu-id="86221-176">For example, if the Windows Server 2012 R2 media is in drive D, you would set the path to `d:\sources\sxs`.</span></span> <span data-ttu-id="86221-177">> Не важно, что у вас есть последние обновления из центра обновления Windows.</span><span class="sxs-lookup"><span data-stu-id="86221-177">> It is important that you have the latest updates from Windows Update.</span></span> <span data-ttu-id="86221-178">При отсутствии интернет-подключения потребуется вручную установить все необходимые пакеты обновления, а также обязательные компоненты для этих пакетов.</span><span class="sxs-lookup"><span data-stu-id="86221-178">If you are not connected to the Internet, you will need to manually install all relevant updates as well as any prerequisites to the required updates.</span></span> 
  
12. <span data-ttu-id="86221-179">Когда в диалоговом окне появляется сообщение о завершении установки, для окончательного завершения процесса необходимо перезагрузить сервер.</span><span class="sxs-lookup"><span data-stu-id="86221-179">When the dialog box indicates that the installation has completed, you will need to reboot the server to complete the process.</span></span>
    
13. <span data-ttu-id="86221-180">Снова запустите **центр обновления Windows** и проверьте наличие обновлений для установленных ролей и служб.</span><span class="sxs-lookup"><span data-stu-id="86221-180">Run **Windows Update** again to check if there are any updates to the roles and services that were installed.</span></span>
    
14. <span data-ttu-id="86221-181">Если будет использоваться Скайп для панели управления Business Server на этом сервере необходимо также установить Silverlight.</span><span class="sxs-lookup"><span data-stu-id="86221-181">If you will be using Skype for Business Server Control Panel on this server then you must also install Silverlight.</span></span> <span data-ttu-id="86221-182">Чтобы установить Silverlight, обратитесь к разделу [Microsoft Silverlight](https://www.microsoft.com/silverlight/).</span><span class="sxs-lookup"><span data-stu-id="86221-182">To install Silverlight, see [Microsoft Silverlight](https://www.microsoft.com/silverlight/).</span></span>
    
<span data-ttu-id="86221-183">Обязательные компоненты можно установить с помощью следующей команды PowerShell.</span><span class="sxs-lookup"><span data-stu-id="86221-183">The prerequisites can be installed by running the following PowerShell command.</span></span> <span data-ttu-id="86221-184">Следует учитывать, что при выполнении этой команды поиск исходных файлов осуществляется в определенном порядке.</span><span class="sxs-lookup"><span data-stu-id="86221-184">Note that the command looks for source files in a specific order.</span></span> <span data-ttu-id="86221-185">При наличии интернет-подключения команда обращается к центру обновления Windows.</span><span class="sxs-lookup"><span data-stu-id="86221-185">If you are online, the command accesses Windows Update.</span></span> <span data-ttu-id="86221-186">Однако в автономном режиме необходимо обеспечить доступность исходных файлов для команды.</span><span class="sxs-lookup"><span data-stu-id="86221-186">However, if you are offline, you need to make sure the source files are available to the command.</span></span> <span data-ttu-id="86221-187">Дополнительные сведения об использовании PowerShell для установки роли и компоненты можно [установки или удаления роли, службы ролей или компонентов](https://technet.microsoft.com/en-us/library/hh831809.aspx) и [Install-WindowsFeature](https://technet.microsoft.com/en-us/library/jj205467.aspx).</span><span class="sxs-lookup"><span data-stu-id="86221-187">For more information about using PowerShell to install roles and features, see [Install or Uninstall Roles, Role Services, or Features](https://technet.microsoft.com/en-us/library/hh831809.aspx) and [Install-WindowsFeature](https://technet.microsoft.com/en-us/library/jj205467.aspx).</span></span> <span data-ttu-id="86221-188">Даже в случае установки обязательных компонентов с помощью команды PowerShell не забудьте по завершении установки снова запустить центр обновления Windows.</span><span class="sxs-lookup"><span data-stu-id="86221-188">Don't forget to run Windows Update again after you install prerequisites, even if you use the PowerShell command.</span></span>
```
Add-WindowsFeature NET-Framework-Core, RSAT-ADDS, Windows-Identity-Foundation, Web-Server, Web-Static-Content, Web-Default-Doc, Web-Http-Errors, Web-Dir-Browsing, Web-Asp-Net, Web-Net-Ext, Web-ISAPI-Ext, Web-ISAPI-Filter, Web-Http-Logging, Web-Log-Libraries, Web-Request-Monitor, Web-Http-Tracing, Web-Basic-Auth, Web-Windows-Auth, Web-Client-Auth, Web-Filtering, Web-Stat-Compression, Web-Dyn-Compression, NET-WCF-HTTP-Activation45, Web-Asp-Net45, Web-Mgmt-Tools, Web-Scripting-Tools, Web-Mgmt-Compat, Server-Media-Foundation, BITS
```

> [!IMPORTANT]
> <span data-ttu-id="86221-189">Для серверов, роль которых отличается от роли сервера переднего плана, например для директоров, серверов сохраняемого чата и пограничных серверов, предусмотрены особые наборы обязательных компонентов.</span><span class="sxs-lookup"><span data-stu-id="86221-189">The prerequisites for servers performing roles other than front-end server, such as the role of Director, Persistent Chat, or Edge, have their own prerequisites.</span></span> <span data-ttu-id="86221-190">Сведения на точное необходимого программного обеспечения, необходимые для каждого типа сервера содержатся [требования к серверу для Скайп для Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="86221-190">For details on the exact prerequisites required by each server type, see [Server requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md).</span></span> 
  

