---
title: Командная консоль Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 674b523b-c0b7-4ed6-9e67-afa6e8ac7e12
description: Командная оболочка Skype для бизнеса Server предоставляет интерфейс командной строки для администрирования и управления сервером. Он построен на Windows PowerShell и включает полный набор средств управления и администрирования, которые относятся к Skype и устаревшим серверным продуктам Lync.
ms.openlocfilehash: 0653faa542bc9bc579bd7617e40d3efed030569f
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816539"
---
# <a name="skype-for-business-server-management-shell"></a><span data-ttu-id="ca9f4-104">Командная консоль Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="ca9f4-104">Skype for Business Server Management Shell</span></span>
 
<span data-ttu-id="ca9f4-105">Командная оболочка Skype для бизнеса Server предоставляет интерфейс командной строки для администрирования и управления сервером.</span><span class="sxs-lookup"><span data-stu-id="ca9f4-105">The Skype for Business Server Management Shell provides the command line interface for server administration and management.</span></span> <span data-ttu-id="ca9f4-106">Он построен на Windows PowerShell и включает полный набор средств управления и администрирования, которые относятся к Skype и устаревшим серверным продуктам Lync.</span><span class="sxs-lookup"><span data-stu-id="ca9f4-106">It is built on Windows PowerShell and includes a comprehensive set of management and administration cmdlets that are specific to Skype and legacy Lync server products.</span></span>
  
<span data-ttu-id="ca9f4-107">Windows PowerShell позволяет управлять приложениями Майкрософт из командной строки.</span><span class="sxs-lookup"><span data-stu-id="ca9f4-107">Windows PowerShell allows you to manage Microsoft applications from the command line.</span></span> <span data-ttu-id="ca9f4-108">Оно предоставляет среду командной строки, команды для определенных продуктов и полноценный язык скриптов.</span><span class="sxs-lookup"><span data-stu-id="ca9f4-108">It includes a command-line environment, product-specific commands, and a full scripting language.</span></span> <span data-ttu-id="ca9f4-109">Windows PowerShell впервые была представлена в качестве загружаемого выпуска для операционной системы Windows в конце 2006 г. и была включена в качестве интерфейса командной строки для управления Microsoft Exchange Server 2007.</span><span class="sxs-lookup"><span data-stu-id="ca9f4-109">Windows PowerShell was first introduced as a downloadable release for the Windows operating system late in 2006, and was incorporated as the command-line interface for manageability of Microsoft Exchange Server 2007.</span></span> <span data-ttu-id="ca9f4-110">Она была включена в большинство продуктов Microsoft Server, включая серверы Lync и Skype, начиная с Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="ca9f4-110">It has been incorporated into most of the Microsoft Server products, including Lync and Skype servers beginning with Lync Server 2010.</span></span> <span data-ttu-id="ca9f4-111">В оболочке управления Skype для бизнеса Server доступно более 700 специальных cmdlets для Lync и Skype.</span><span class="sxs-lookup"><span data-stu-id="ca9f4-111">There are over 700 Lync and Skype specific cmdlets available in the Skype for Business Server Management Shell.</span></span>
  
> [!NOTE]
> <span data-ttu-id="ca9f4-112">Справочник по cmdlet skype для бизнеса перемещен в docs.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="ca9f4-112">Skype for Business cmdlet reference has moved to docs.microsoft.com.</span></span> <span data-ttu-id="ca9f4-113">Щелкнув ссылки ниже, вы перейдите на новую docs.microsoft.com страницу.</span><span class="sxs-lookup"><span data-stu-id="ca9f4-113">Clicking on the links below will take you to the new docs.microsoft.com page.</span></span> <span data-ttu-id="ca9f4-114">Теперь содержимое доступно с открытым исходным кодом и доступно для сообщества с помощью GitHub.</span><span class="sxs-lookup"><span data-stu-id="ca9f4-114">The content is now open sourced and available for community contributions through GitHub.</span></span> <span data-ttu-id="ca9f4-115">Заинтересованы в том, чтобы вносить свой вклад?</span><span class="sxs-lookup"><span data-stu-id="ca9f4-115">Interested in contributing?</span></span> <span data-ttu-id="ca9f4-116">Ознакомьтесь с readME в репо здесь: [https://github.com/MicrosoftDocs/office-docs-powershell](https://github.com/MicrosoftDocs/office-docs-powershell)</span><span class="sxs-lookup"><span data-stu-id="ca9f4-116">Check out the README in the repo here: [https://github.com/MicrosoftDocs/office-docs-powershell](https://github.com/MicrosoftDocs/office-docs-powershell)</span></span>
  
<span data-ttu-id="ca9f4-117">Skype для бизнеса Server включает более 700 cmdlets, позволяющих администраторам управлять Skype для бизнеса Server с помощью оболочки управления Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="ca9f4-117">Skype for Business Server ships with more than 700 cmdlets that enable administrators to manage Skype for Business Server using the Skype for Business Server Management Shell.</span></span> <span data-ttu-id="ca9f4-118">Справку по командлету можно получить непосредственно из командной строки, введя команду, аналогичную следующей:</span><span class="sxs-lookup"><span data-stu-id="ca9f4-118">You can retrieve help for a cmdlet directly from the command line by typing a command similar to the following:</span></span>
  
```PowerShell
Get-Help New-CsVoicePolicy -Full
```

<span data-ttu-id="ca9f4-119">В предыдущей команде извлекалась полная справка, доступная для командлета **New-CsVoicePolicy.**</span><span class="sxs-lookup"><span data-stu-id="ca9f4-119">The preceding command retrieves the complete help available for the **New-CsVoicePolicy** cmdlet.</span></span> <span data-ttu-id="ca9f4-120">Чтобы просмотреть справку для другого cmdlet, замените **New-CsVoicePolicy** именем, для которого требуется получить справку.</span><span class="sxs-lookup"><span data-stu-id="ca9f4-120">To view help for a different cmdlet, substitute **New-CsVoicePolicy** with the name of the cmdlet for which you want to retrieve help.</span></span>
  
<span data-ttu-id="ca9f4-121">Чтобы получить полный список командлетов, доступных для управления Skype для бизнеса Server, введите в командной области оболочки следующую команду:</span><span class="sxs-lookup"><span data-stu-id="ca9f4-121">To retrieve a full list of cmdlets available for managing Skype for Business Server, type the following at the shell command prompt:</span></span> 
  
```PowerShell
Get-Command * -Module SkypeforBusiness -CommandType cmdlet
```



<span data-ttu-id="ca9f4-122">Что нужно знать о Windows PowerShell в Skype для бизнеса Server:</span><span class="sxs-lookup"><span data-stu-id="ca9f4-122">Things to know about Windows PowerShell in Skype for Business Server:</span></span>
  
- <span data-ttu-id="ca9f4-123">Чтобы запустить команды Skype для бизнеса Server, откройте оболочку управления Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="ca9f4-123">To run the Skype for Business Server cmdlets, open the Skype for Business Server Management Shell.</span></span>
    
    > [!CAUTION]
    > <span data-ttu-id="ca9f4-124">If you open a Windows PowerShell rather than the Skype for Business Server Management Shell, by default you may not be able to run the Skype cmdlets.</span><span class="sxs-lookup"><span data-stu-id="ca9f4-124">If you open a Windows PowerShell window rather than the Skype for Business Server Management Shell, by default you may not be able to run the Skype cmdlets.</span></span> <span data-ttu-id="ca9f4-125">Чтобы запустить командлеты Skype для бизнеса Server из Windows PowerShell, введите в командной Windows PowerShell следующую команду: >  `Import-Module SkypeforBusiness`</span><span class="sxs-lookup"><span data-stu-id="ca9f4-125">To run Skype for Business Server cmdlets from within Windows PowerShell, first type the following at the Windows PowerShell command prompt: >  `Import-Module SkypeforBusiness`</span></span>
  
- <span data-ttu-id="ca9f4-126">Skype для бизнеса Server Management Shell автоматически устанавливается на каждом сервере переднего сервера Skype для бизнеса Server Enterprise Edition или сервере Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="ca9f4-126">Skype for Business Server Management Shell is automatically installed on every Skype for Business Server Enterprise Edition Front End Server or Standard Edition server.</span></span>
    
- <span data-ttu-id="ca9f4-127">You can update the Skype for Business Server Management Shell help content by running the [Update-Help](https://technet.microsoft.com/library/hh849720.aspx) cmdlet.</span><span class="sxs-lookup"><span data-stu-id="ca9f4-127">You can update the Skype for Business Server Management Shell help content by running the [Update-Help](https://technet.microsoft.com/library/hh849720.aspx) cmdlet.</span></span> <span data-ttu-id="ca9f4-128">Командлет Update-Help загружает и устанавливает самые новые файлы справки, доступные для всех модулей, установленных на компьютере, включая обновления командлетов Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="ca9f4-128">The Update-Help cmdlet downloads and installs the newest help files available for all of the modules installed on your computer, including updates to Skype for Business cmdlets.</span></span>
    
    <span data-ttu-id="ca9f4-129">По умолчанию **командлет Update-Help** обновляет все модули, установленные в Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="ca9f4-129">By default, the **Update-Help** cmdlet will update all the modules installed on your Skype for Business Server.</span></span> <span data-ttu-id="ca9f4-130">Чтобы обновить только определенные модули, можно использовать параметр _Module,_ чтобы ограничить область действия командлета.</span><span class="sxs-lookup"><span data-stu-id="ca9f4-130">If you want to update only certain modules, you can use the _Module_ parameter to limit the scope of the cmdlet.</span></span> <span data-ttu-id="ca9f4-131">В следующем примере обновляется только модуль Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="ca9f4-131">The following example updates only the Skype for Business module.</span></span>
    
  ```PowerShell
  Update-Help -Module SkypeforBusiness
  ```

    <span data-ttu-id="ca9f4-132">Если требуется обновить справку на серверах, не подключенных к [](https://technet.microsoft.com/library/hh849724.aspx) Интернету, вы можете использовать для получения последней версии справки и сохранения ее в задаемом расположении.</span><span class="sxs-lookup"><span data-stu-id="ca9f4-132">If you need to update the Help on servers that are not connected to the internet, you can use the [Save-Help](https://technet.microsoft.com/library/hh849724.aspx) cmdlet to get the latest version of the help and save it to a location you specify.</span></span> <span data-ttu-id="ca9f4-133">Затем можно использовать  для получения обновленной справки из выбранного расположения с помощью параметра _-SourcePath_ на серверах, не подключенных к Интернету.</span><span class="sxs-lookup"><span data-stu-id="ca9f4-133">You can then use the **Update-Help** cmdlet with the _-SourcePath_ parameter on servers not connected to the internet to get the updated help from the location you selected.</span></span> <span data-ttu-id="ca9f4-134">В следующем примере показано, как сохранить файлы справки в сетевой папке, а затем обновить справку для модуля Skype для бизнеса из файловой папки.</span><span class="sxs-lookup"><span data-stu-id="ca9f4-134">The following example shows how to save the help files to a network file share, and then update the help for the Skype for Business module from the file share.</span></span>
    
  ```PowerShell
  // Save the help files
   Save-Help -DestinationPath \\UpdateShare\HelpDownload
  // Run Update-Help against the local help files
   Update-Help -Module SkypeforBusiness -SourcePath \\UpdateShare\HelpDownload
  ```

    <span data-ttu-id="ca9f4-135">Дополнительные сведения см. в [справке по updatable.](https://technet.microsoft.com/library/hh847735.aspx)</span><span class="sxs-lookup"><span data-stu-id="ca9f4-135">For more detailed information, see [About Updatable Help](https://technet.microsoft.com/library/hh847735.aspx).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="ca9f4-136">При удаленном использовании PowerShell может потребоваться разрешить взаимодействие через брандмауэр.</span><span class="sxs-lookup"><span data-stu-id="ca9f4-136">If you are using PowerShell remotely you may need to allow communication through a firewall.</span></span> <span data-ttu-id="ca9f4-137">Дополнительные информацию о портах, которые использует для ремотивирования PowerShell, см. в этой [теме.](https://blogs.technet.microsoft.com/christwe/2012/06/20/what-port-does-powershell-remoting-use/)</span><span class="sxs-lookup"><span data-stu-id="ca9f4-137">To learn more about the ports PowerShell remoting uses, see [What Port Does PowerShell Remoting Use?](https://blogs.technet.microsoft.com/christwe/2012/06/20/what-port-does-powershell-remoting-use/).</span></span>
    

