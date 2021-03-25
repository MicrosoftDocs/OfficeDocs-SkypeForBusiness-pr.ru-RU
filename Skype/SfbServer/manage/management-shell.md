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
description: Командная оболочка Skype для бизнес-серверов предоставляет интерфейс командной строки для администрирования и управления серверами. Он построен на Windows PowerShell и включает полный набор команды управления и администрирования, которые специфичен для продуктов Skype и устаревших серверов Lync.
ms.openlocfilehash: 24da9ac341129239399ea17218be8547f3549d6f
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51118588"
---
# <a name="skype-for-business-server-management-shell"></a><span data-ttu-id="021f3-104">Командная консоль Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="021f3-104">Skype for Business Server Management Shell</span></span>
 
<span data-ttu-id="021f3-105">Командная оболочка Skype для бизнес-серверов предоставляет интерфейс командной строки для администрирования и управления серверами.</span><span class="sxs-lookup"><span data-stu-id="021f3-105">The Skype for Business Server Management Shell provides the command line interface for server administration and management.</span></span> <span data-ttu-id="021f3-106">Он построен на Windows PowerShell и включает полный набор команды управления и администрирования, которые специфичен для продуктов Skype и устаревших серверов Lync.</span><span class="sxs-lookup"><span data-stu-id="021f3-106">It is built on Windows PowerShell and includes a comprehensive set of management and administration cmdlets that are specific to Skype and legacy Lync server products.</span></span>
  
<span data-ttu-id="021f3-107">Windows PowerShell позволяет управлять приложениями Майкрософт из командной строки.</span><span class="sxs-lookup"><span data-stu-id="021f3-107">Windows PowerShell allows you to manage Microsoft applications from the command line.</span></span> <span data-ttu-id="021f3-108">Оно предоставляет среду командной строки, команды для определенных продуктов и полноценный язык скриптов.</span><span class="sxs-lookup"><span data-stu-id="021f3-108">It includes a command-line environment, product-specific commands, and a full scripting language.</span></span> <span data-ttu-id="021f3-109">Windows PowerShell была впервые представлена в качестве загружаемого выпуска для операционной системы Windows в конце 2006 г. и была включена в качестве интерфейса командной строки для управляемости Microsoft Exchange Server 2007 г.</span><span class="sxs-lookup"><span data-stu-id="021f3-109">Windows PowerShell was first introduced as a downloadable release for the Windows operating system late in 2006, and was incorporated as the command-line interface for manageability of Microsoft Exchange Server 2007.</span></span> <span data-ttu-id="021f3-110">Он был включен в большинство продуктов Microsoft Server, включая серверы Lync и Skype, начиная с Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="021f3-110">It has been incorporated into most of the Microsoft Server products, including Lync and Skype servers beginning with Lync Server 2010.</span></span> <span data-ttu-id="021f3-111">В оболочке управления Skype для бизнеса серверов доступно более 700 lync и skype.</span><span class="sxs-lookup"><span data-stu-id="021f3-111">There are over 700 Lync and Skype specific cmdlets available in the Skype for Business Server Management Shell.</span></span>
  
> [!NOTE]
> <span data-ttu-id="021f3-112">Ссылки на веб-кодлет Skype для бизнеса перенесены в docs.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="021f3-112">Skype for Business cmdlet reference has moved to docs.microsoft.com.</span></span> <span data-ttu-id="021f3-113">Щелкнув ссылки ниже, вы сможете найти новую страницу docs.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="021f3-113">Clicking on the links below will take you to the new docs.microsoft.com page.</span></span> <span data-ttu-id="021f3-114">Теперь контент открыт и доступен для взносов сообщества через GitHub.</span><span class="sxs-lookup"><span data-stu-id="021f3-114">The content is now open sourced and available for community contributions through GitHub.</span></span> <span data-ttu-id="021f3-115">Заинтересованы в содействии?</span><span class="sxs-lookup"><span data-stu-id="021f3-115">Interested in contributing?</span></span> <span data-ttu-id="021f3-116">Ознакомьтесь с README в репо здесь: [https://github.com/MicrosoftDocs/office-docs-powershell](https://github.com/MicrosoftDocs/office-docs-powershell)</span><span class="sxs-lookup"><span data-stu-id="021f3-116">Check out the README in the repo here: [https://github.com/MicrosoftDocs/office-docs-powershell](https://github.com/MicrosoftDocs/office-docs-powershell)</span></span>
  
<span data-ttu-id="021f3-117">Skype для бизнеса Server использует более 700 смдлетов, которые позволяют администраторам управлять Skype для бизнеса Server с помощью оболочки управления Skype для бизнес-серверов.</span><span class="sxs-lookup"><span data-stu-id="021f3-117">Skype for Business Server ships with more than 700 cmdlets that enable administrators to manage Skype for Business Server using the Skype for Business Server Management Shell.</span></span> <span data-ttu-id="021f3-118">Вы можете получить справку для командлета непосредственно из командной строки, введя команду, аналогичную следующей:</span><span class="sxs-lookup"><span data-stu-id="021f3-118">You can retrieve help for a cmdlet directly from the command line by typing a command similar to the following:</span></span>
  
```PowerShell
Get-Help New-CsVoicePolicy -Full
```

<span data-ttu-id="021f3-119">В предыдущей команде извлекается полная справка, доступная для **командлета New-CsVoicePolicy.**</span><span class="sxs-lookup"><span data-stu-id="021f3-119">The preceding command retrieves the complete help available for the **New-CsVoicePolicy** cmdlet.</span></span> <span data-ttu-id="021f3-120">Чтобы просмотреть справку для другого cmdlet, замените **New-CsVoicePolicy** именем cmdlet, для которого требуется получить справку.</span><span class="sxs-lookup"><span data-stu-id="021f3-120">To view help for a different cmdlet, substitute **New-CsVoicePolicy** with the name of the cmdlet for which you want to retrieve help.</span></span>
  
<span data-ttu-id="021f3-121">Чтобы получить полный список командлетов, доступных для управления Skype для бизнеса Server, введите в командной подсказке оболочки следующее:</span><span class="sxs-lookup"><span data-stu-id="021f3-121">To retrieve a full list of cmdlets available for managing Skype for Business Server, type the following at the shell command prompt:</span></span> 
  
```PowerShell
Get-Command * -Module SkypeforBusiness -CommandType cmdlet
```



<span data-ttu-id="021f3-122">Что нужно знать о Windows PowerShell Skype для бизнеса Server:</span><span class="sxs-lookup"><span data-stu-id="021f3-122">Things to know about Windows PowerShell in Skype for Business Server:</span></span>
  
- <span data-ttu-id="021f3-123">Чтобы запустить команды Skype для бизнеса Server, откройте оболочку управления Skype для бизнес-серверов.</span><span class="sxs-lookup"><span data-stu-id="021f3-123">To run the Skype for Business Server cmdlets, open the Skype for Business Server Management Shell.</span></span>
    
    > [!CAUTION]
    > <span data-ttu-id="021f3-124">Если вы откроете Windows PowerShell, а не оболочку управления skype для бизнес-серверов, по умолчанию вы не сможете запустить команды Skype.</span><span class="sxs-lookup"><span data-stu-id="021f3-124">If you open a Windows PowerShell window rather than the Skype for Business Server Management Shell, by default you may not be able to run the Skype cmdlets.</span></span> <span data-ttu-id="021f3-125">Чтобы запустить командлеты Skype для бизнеса Server из Windows PowerShell, сначала введите следующее в командной Windows PowerShell: >  `Import-Module SkypeforBusiness`</span><span class="sxs-lookup"><span data-stu-id="021f3-125">To run Skype for Business Server cmdlets from within Windows PowerShell, first type the following at the Windows PowerShell command prompt: >  `Import-Module SkypeforBusiness`</span></span>
  
- <span data-ttu-id="021f3-126">Оболочка управления Skype для бизнес-серверов автоматически устанавливается на каждом сервере skype для бизнеса Server Enterprise Edition front End Server или Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="021f3-126">Skype for Business Server Management Shell is automatically installed on every Skype for Business Server Enterprise Edition Front End Server or Standard Edition server.</span></span>
    
- <span data-ttu-id="021f3-127">Вы можете обновить содержимое справки по управлению Skype для бизнес-серверов с помощью команды [Update-Help.](/powershell/module/microsoft.powershell.core/update-help)</span><span class="sxs-lookup"><span data-stu-id="021f3-127">You can update the Skype for Business Server Management Shell help content by running the [Update-Help](/powershell/module/microsoft.powershell.core/update-help) cmdlet.</span></span> <span data-ttu-id="021f3-128">Командлет Update-Help и устанавливает самые новые файлы справки, доступные для всех модулей, установленных на компьютере, включая обновления командлетов Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="021f3-128">The Update-Help cmdlet downloads and installs the newest help files available for all of the modules installed on your computer, including updates to Skype for Business cmdlets.</span></span>
    
    <span data-ttu-id="021f3-129">По умолчанию командлет **Update-Help** обновляет все модули, установленные на сервере Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="021f3-129">By default, the **Update-Help** cmdlet will update all the modules installed on your Skype for Business Server.</span></span> <span data-ttu-id="021f3-130">Если требуется обновить только определенные модули, можно использовать параметр _Module,_ чтобы ограничить область действия командлета.</span><span class="sxs-lookup"><span data-stu-id="021f3-130">If you want to update only certain modules, you can use the _Module_ parameter to limit the scope of the cmdlet.</span></span> <span data-ttu-id="021f3-131">В следующем примере обновляется только модуль Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="021f3-131">The following example updates only the Skype for Business module.</span></span>
    
  ```PowerShell
  Update-Help -Module SkypeforBusiness
  ```

    <span data-ttu-id="021f3-132">Если вам необходимо обновить справку на серверах, не подключенных к Интернету, вы можете использовать комлет [Save-Help,](/powershell/module/microsoft.powershell.core/save-help) чтобы получить последнюю версию справки и сохранить ее в нужном месте.</span><span class="sxs-lookup"><span data-stu-id="021f3-132">If you need to update the Help on servers that are not connected to the internet, you can use the [Save-Help](/powershell/module/microsoft.powershell.core/save-help) cmdlet to get the latest version of the help and save it to a location you specify.</span></span> <span data-ttu-id="021f3-133">Затем можно использовать комлет **Update-Help** с параметром _-SourcePath_ на серверах, не подключенных к Интернету, чтобы получить обновленную справку из выбранного вами расположения.</span><span class="sxs-lookup"><span data-stu-id="021f3-133">You can then use the **Update-Help** cmdlet with the _-SourcePath_ parameter on servers not connected to the internet to get the updated help from the location you selected.</span></span> <span data-ttu-id="021f3-134">В следующем примере показано, как сохранить файлы справки в сетевой файл, а затем обновить справку для модуля Skype для бизнеса из файла.</span><span class="sxs-lookup"><span data-stu-id="021f3-134">The following example shows how to save the help files to a network file share, and then update the help for the Skype for Business module from the file share.</span></span>
    
  ```PowerShell
  // Save the help files
   Save-Help -DestinationPath \\UpdateShare\HelpDownload
  // Run Update-Help against the local help files
   Update-Help -Module SkypeforBusiness -SourcePath \\UpdateShare\HelpDownload
  ```

    <span data-ttu-id="021f3-135">Дополнительные сведения см. в [справке "Updatable Help".](/powershell/module/microsoft.powershell.core/about/about_updatable_help)</span><span class="sxs-lookup"><span data-stu-id="021f3-135">For more detailed information, see [About Updatable Help](/powershell/module/microsoft.powershell.core/about/about_updatable_help).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="021f3-136">Если вы используете PowerShell удаленно, возможно, потребуется разрешить связь через брандмауэр.</span><span class="sxs-lookup"><span data-stu-id="021f3-136">If you are using PowerShell remotely you may need to allow communication through a firewall.</span></span> <span data-ttu-id="021f3-137">Дополнительные данные об использовании повторного использования портов PowerShell см. в этой [ссылке.](/archive/blogs/christwe/what-port-does-powershell-remoting-use)</span><span class="sxs-lookup"><span data-stu-id="021f3-137">To learn more about the ports PowerShell remoting uses, see [What Port Does PowerShell Remoting Use?](/archive/blogs/christwe/what-port-does-powershell-remoting-use).</span></span>
