---
title: Командная консоль Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 674b523b-c0b7-4ed6-9e67-afa6e8ac7e12
description: Командная консоль управления Skype для бизнеса Server предоставляет интерфейс командной строки для администрирования и управления сервером. Она создана на основе Windows PowerShell и содержит полный набор командлетов управления и администрирования, которые относятся к Skype и старым серверным продуктам Lync.
ms.openlocfilehash: 4890194824caaea771d31e008d4546d871d0da8a
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/08/2020
ms.locfileid: "40991594"
---
# <a name="skype-for-business-server-management-shell"></a><span data-ttu-id="d9f04-104">Командная консоль Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="d9f04-104">Skype for Business Server Management Shell</span></span>
 
<span data-ttu-id="d9f04-105">Командная консоль управления Skype для бизнеса Server предоставляет интерфейс командной строки для администрирования и управления сервером.</span><span class="sxs-lookup"><span data-stu-id="d9f04-105">The Skype for Business Server Management Shell provides the command line interface for server administration and management.</span></span> <span data-ttu-id="d9f04-106">Она создана на основе Windows PowerShell и содержит полный набор командлетов управления и администрирования, которые относятся к Skype и старым серверным продуктам Lync.</span><span class="sxs-lookup"><span data-stu-id="d9f04-106">It is built on Windows PowerShell and includes a comprehensive set of management and administration cmdlets that are specific to Skype and legacy Lync server products.</span></span>
  
<span data-ttu-id="d9f04-107">Windows PowerShell позволяет управлять приложениями Майкрософт из командной строки.</span><span class="sxs-lookup"><span data-stu-id="d9f04-107">Windows PowerShell allows you to manage Microsoft applications from the command line.</span></span> <span data-ttu-id="d9f04-108">Она включает среду командной строки, команды для определенного продукта и полный язык сценариев.</span><span class="sxs-lookup"><span data-stu-id="d9f04-108">It includes a command-line environment, product-specific commands, and a full scripting language.</span></span> <span data-ttu-id="d9f04-109">Windows PowerShell впервые была представлена в качестве загружаемого выпуска для операционной системы Windows с опозданием в 2006 и была включена в интерфейс командной строки для управляемости сервера Microsoft Exchange Server 2007.</span><span class="sxs-lookup"><span data-stu-id="d9f04-109">Windows PowerShell was first introduced as a downloadable release for the Windows operating system late in 2006, and was incorporated as the command-line interface for manageability of Microsoft Exchange Server 2007.</span></span> <span data-ttu-id="d9f04-110">Она была включена в большинство серверных продуктов Microsoft, включая Lync и серверы Skype, начиная с Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="d9f04-110">It has been incorporated into most of the Microsoft Server products, including Lync and Skype servers beginning with Lync Server 2010.</span></span> <span data-ttu-id="d9f04-111">В командной консоли Skype для бизнеса Server есть более 700 отдельных командлетов Lync и Skype.</span><span class="sxs-lookup"><span data-stu-id="d9f04-111">There are over 700 Lync and Skype specific cmdlets available in the Skype for Business Server Management Shell.</span></span>
  
> [!NOTE]
> <span data-ttu-id="d9f04-112">Справочник по командлетам Skype для бизнеса перенесен на веб-сайт docs.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="d9f04-112">Skype for Business cmdlet reference has moved to docs.microsoft.com.</span></span> <span data-ttu-id="d9f04-113">По представленным ниже ссылкам вы можете перейти на новую страницу портала docs.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="d9f04-113">Clicking on the links below will take you to the new docs.microsoft.com page.</span></span> <span data-ttu-id="d9f04-114">Теперь весь контент предлагается с открытым исходным кодом и доступен в сообществе GitHub.</span><span class="sxs-lookup"><span data-stu-id="d9f04-114">The content is now open sourced and available for community contributions through GitHub.</span></span> <span data-ttu-id="d9f04-115">Хотите принять участие в работе с ним?</span><span class="sxs-lookup"><span data-stu-id="d9f04-115">Interested in contributing?</span></span> <span data-ttu-id="d9f04-116">Ознакомьтесь с ФАЙЛОМ README в репозитории здесь:[https://github.com/MicrosoftDocs/office-docs-powershell](https://github.com/MicrosoftDocs/office-docs-powershell)</span><span class="sxs-lookup"><span data-stu-id="d9f04-116">Check out the README in the repo here: [https://github.com/MicrosoftDocs/office-docs-powershell](https://github.com/MicrosoftDocs/office-docs-powershell)</span></span>
  
<span data-ttu-id="d9f04-117">В Skype для бизнеса Server входит более 700 командлетов, позволяющих администраторам управлять Skype для бизнеса Server с помощью командной консоли Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="d9f04-117">Skype for Business Server ships with more than 700 cmdlets that enable administrators to manage Skype for Business Server using the Skype for Business Server Management Shell.</span></span> <span data-ttu-id="d9f04-118">Вы можете получить справку по командлету непосредственно в командной строке, введя следующую команду:</span><span class="sxs-lookup"><span data-stu-id="d9f04-118">You can retrieve help for a cmdlet directly from the command line by typing a command similar to the following:</span></span>
  
```PowerShell
Get-Help New-CsVoicePolicy -Full
```

<span data-ttu-id="d9f04-119">Предыдущая команда получает полную справку, доступную для командлета **New-CsVoicePolicy**.</span><span class="sxs-lookup"><span data-stu-id="d9f04-119">The preceding command retrieves the complete help available for the **New-CsVoicePolicy** cmdlet.</span></span> <span data-ttu-id="d9f04-120">Чтобы просмотреть справку для другого командлета, замените **New-CsVoicePolicy** на имя нужного командлета.</span><span class="sxs-lookup"><span data-stu-id="d9f04-120">To view help for a different cmdlet, substitute **New-CsVoicePolicy** with the name of the cmdlet for which you want to retrieve help.</span></span>
  
<span data-ttu-id="d9f04-121">Чтобы получить полный список доступных командлетов для управления Skype для бизнеса Server, введите в командной строке оболочки следующую команду. </span><span class="sxs-lookup"><span data-stu-id="d9f04-121">To retrieve a full list of cmdlets available for managing Skype for Business Server, type the following at the shell command prompt:</span></span> 
  
```PowerShell
Get-Command * -Module SkypeforBusiness -CommandType cmdlet
```



<span data-ttu-id="d9f04-122">Что нужно знать о Windows PowerShell в Skype для бизнеса Server:</span><span class="sxs-lookup"><span data-stu-id="d9f04-122">Things to know about Windows PowerShell in Skype for Business Server:</span></span>
  
- <span data-ttu-id="d9f04-123">Чтобы запустить командлеты Skype для бизнеса Server, откройте командную консоль управления "Skype для бизнеса".</span><span class="sxs-lookup"><span data-stu-id="d9f04-123">To run the Skype for Business Server cmdlets, open the Skype for Business Server Management Shell.</span></span>
    
    > [!CAUTION]
    > <span data-ttu-id="d9f04-124">Если вы открыли окно Windows PowerShell вместо командной консоли Skype для бизнеса Server, по умолчанию вы не сможете запускать командлеты Skype.</span><span class="sxs-lookup"><span data-stu-id="d9f04-124">If you open a Windows PowerShell window rather than the Skype for Business Server Management Shell, by default you may not be able to run the Skype cmdlets.</span></span> <span data-ttu-id="d9f04-125">Чтобы запустить командлеты Skype для бизнеса Server в Windows PowerShell, сначала введите в командной строке Windows PowerShell следующее: >`Import-Module SkypeforBusiness`</span><span class="sxs-lookup"><span data-stu-id="d9f04-125">To run Skype for Business Server cmdlets from within Windows PowerShell, first type the following at the Windows PowerShell command prompt: >  `Import-Module SkypeforBusiness`</span></span>
  
- <span data-ttu-id="d9f04-126">Консоль управления Skype для бизнеса Server автоматически устанавливается на каждый сервер переднего плана Skype для бизнеса Server Enterprise Edition или Standard Edition Server.</span><span class="sxs-lookup"><span data-stu-id="d9f04-126">Skype for Business Server Management Shell is automatically installed on every Skype for Business Server Enterprise Edition Front End Server or Standard Edition server.</span></span>
    
- <span data-ttu-id="d9f04-127">Вы можете обновить содержимое справки командной консоли Skype для бизнеса Server, запустив командлет [Update-Help](https://technet.microsoft.com/en-us/library/hh849720.aspx) .</span><span class="sxs-lookup"><span data-stu-id="d9f04-127">You can update the Skype for Business Server Management Shell help content by running the [Update-Help](https://technet.microsoft.com/en-us/library/hh849720.aspx) cmdlet.</span></span> <span data-ttu-id="d9f04-128">С помощью командлета Update-Help загружаются и устанавливаются самые новые файлы справки для всех модулей, установленных на компьютере, в том числе обновления командлетов Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="d9f04-128">The Update-Help cmdlet downloads and installs the newest help files available for all of the modules installed on your computer, including updates to Skype for Business cmdlets.</span></span>
    
    <span data-ttu-id="d9f04-129">По умолчанию командлет **Update-Help** обновит все модули, установленные на сервере Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="d9f04-129">By default, the **Update-Help** cmdlet will update all the modules installed on your Skype for Business Server.</span></span> <span data-ttu-id="d9f04-130">Если требуется обновить лишь определенные модули, с помощью параметра _Module_ можно ограничить область применения данного командлета.</span><span class="sxs-lookup"><span data-stu-id="d9f04-130">If you want to update only certain modules, you can use the _Module_ parameter to limit the scope of the cmdlet.</span></span> <span data-ttu-id="d9f04-131">В следующем примере обновляется только модуль Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="d9f04-131">The following example updates only the Skype for Business module.</span></span>
    
  ```PowerShell
  Update-Help -Module SkypeforBusiness
  ```

    <span data-ttu-id="d9f04-132">Если вам нужно обновить справку на серверах, не подключенных к Интернету, вы можете воспользоваться командлетом [Save-Help](https://technet.microsoft.com/en-us/library/hh849724.aspx) , чтобы получить последнюю версию справки и сохранить ее в указанном месте.</span><span class="sxs-lookup"><span data-stu-id="d9f04-132">If you need to update the Help on servers that are not connected to the internet, you can use the [Save-Help](https://technet.microsoft.com/en-us/library/hh849724.aspx) cmdlet to get the latest version of the help and save it to a location you specify.</span></span> <span data-ttu-id="d9f04-133">Затем вы можете использовать командлет **Update-Help** с параметром _-SourcePath_ на серверах, не подключенных к Интернету, чтобы получить обновленную справку из выбранного местоположения.</span><span class="sxs-lookup"><span data-stu-id="d9f04-133">You can then use the **Update-Help** cmdlet with the _-SourcePath_ parameter on servers not connected to the internet to get the updated help from the location you selected.</span></span> <span data-ttu-id="d9f04-134">В следующем примере показано, как сохранить файлы справки в общем сетевом файле, а затем обновить справку для модуля Skype для бизнеса в общей папке.</span><span class="sxs-lookup"><span data-stu-id="d9f04-134">The following example shows how to save the help files to a network file share, and then update the help for the Skype for Business module from the file share.</span></span>
    
  ```PowerShell
  // Save the help files
   Save-Help -DestinationPath \\UpdateShare\HelpDownload
  // Run Update-Help against the local help files
   Update-Help -Module SkypeforBusiness -SourcePath \\UpdateShare\HelpDownload
  ```

    <span data-ttu-id="d9f04-135">Более подробную информацию можно найти в разделе [об обновляемой справке](https://technet.microsoft.com/library/hh847735.aspx).</span><span class="sxs-lookup"><span data-stu-id="d9f04-135">For more detailed information, see [About Updatable Help](https://technet.microsoft.com/library/hh847735.aspx).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="d9f04-136">Если вы используете PowerShell удаленно, вам может потребоваться разрешить связь через брандмауэр.</span><span class="sxs-lookup"><span data-stu-id="d9f04-136">If you are using PowerShell remotely you may need to allow communication through a firewall.</span></span> <span data-ttu-id="d9f04-137">Чтобы узнать больше о портах оболочки PowerShell, используемых удаленным взаимодействием, посмотрите, [какой порт используется в PowerShell](https://blogs.technet.microsoft.com/christwe/2012/06/20/what-port-does-powershell-remoting-use/).</span><span class="sxs-lookup"><span data-stu-id="d9f04-137">To learn more about the ports PowerShell remoting uses, see [What Port Does PowerShell Remoting Use?](https://blogs.technet.microsoft.com/christwe/2012/06/20/what-port-does-powershell-remoting-use/).</span></span>
    

