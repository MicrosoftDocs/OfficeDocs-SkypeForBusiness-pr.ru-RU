---
title: Командная консоль Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 674b523b-c0b7-4ed6-9e67-afa6e8ac7e12
description: Консоль управления Skype для бизнеса Server предоставляет интерфейс командной строки для администрирования и управления сервером. Он создан на основе Windows PowerShell и содержит полный набор командлетов управления и администрирования, характерных для Skype и устаревших продуктов Lync Server.
ms.openlocfilehash: 085c8f4a8a454f97dc4fbc640a6f5c8a70baec31
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42044261"
---
# <a name="skype-for-business-server-management-shell"></a><span data-ttu-id="5b1b8-104">Командная консоль Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="5b1b8-104">Skype for Business Server Management Shell</span></span>
 
<span data-ttu-id="5b1b8-105">Консоль управления Skype для бизнеса Server предоставляет интерфейс командной строки для администрирования и управления сервером.</span><span class="sxs-lookup"><span data-stu-id="5b1b8-105">The Skype for Business Server Management Shell provides the command line interface for server administration and management.</span></span> <span data-ttu-id="5b1b8-106">Он создан на основе Windows PowerShell и содержит полный набор командлетов управления и администрирования, характерных для Skype и устаревших продуктов Lync Server.</span><span class="sxs-lookup"><span data-stu-id="5b1b8-106">It is built on Windows PowerShell and includes a comprehensive set of management and administration cmdlets that are specific to Skype and legacy Lync server products.</span></span>
  
<span data-ttu-id="5b1b8-107">Windows PowerShell позволяет управлять приложениями Майкрософт из командной строки.</span><span class="sxs-lookup"><span data-stu-id="5b1b8-107">Windows PowerShell allows you to manage Microsoft applications from the command line.</span></span> <span data-ttu-id="5b1b8-108">Оно предоставляет среду командной строки, команды для определенных продуктов и полноценный язык скриптов.</span><span class="sxs-lookup"><span data-stu-id="5b1b8-108">It includes a command-line environment, product-specific commands, and a full scripting language.</span></span> <span data-ttu-id="5b1b8-109">Windows PowerShell впервые появился в качестве загружаемого выпуска для операционной системы Windows с опозданием в 2006 и был включен в качестве интерфейса командной строки для управления Microsoft Exchange Server 2007.</span><span class="sxs-lookup"><span data-stu-id="5b1b8-109">Windows PowerShell was first introduced as a downloadable release for the Windows operating system late in 2006, and was incorporated as the command-line interface for manageability of Microsoft Exchange Server 2007.</span></span> <span data-ttu-id="5b1b8-110">Она включена в большинство серверных продуктов Майкрософт, в том числе серверы Lync и Skype, начиная с Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="5b1b8-110">It has been incorporated into most of the Microsoft Server products, including Lync and Skype servers beginning with Lync Server 2010.</span></span> <span data-ttu-id="5b1b8-111">В командной консоли Skype для бизнеса Server есть более 700 доступных командлетов Lync и Skype.</span><span class="sxs-lookup"><span data-stu-id="5b1b8-111">There are over 700 Lync and Skype specific cmdlets available in the Skype for Business Server Management Shell.</span></span>
  
> [!NOTE]
> <span data-ttu-id="5b1b8-112">Ссылка на командлет Skype для бизнеса перемещена в docs.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="5b1b8-112">Skype for Business cmdlet reference has moved to docs.microsoft.com.</span></span> <span data-ttu-id="5b1b8-113">Перейдя по приведенным ниже ссылкам, вы перейдете на новую страницу docs.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="5b1b8-113">Clicking on the links below will take you to the new docs.microsoft.com page.</span></span> <span data-ttu-id="5b1b8-114">Теперь контент открыт в исходном и доступном для участия в сообществах с помощью GitHub.</span><span class="sxs-lookup"><span data-stu-id="5b1b8-114">The content is now open sourced and available for community contributions through GitHub.</span></span> <span data-ttu-id="5b1b8-115">Интересуетесь участниками?</span><span class="sxs-lookup"><span data-stu-id="5b1b8-115">Interested in contributing?</span></span> <span data-ttu-id="5b1b8-116">Ознакомьтесь со статьей README в репозитории здесь:[https://github.com/MicrosoftDocs/office-docs-powershell](https://github.com/MicrosoftDocs/office-docs-powershell)</span><span class="sxs-lookup"><span data-stu-id="5b1b8-116">Check out the README in the repo here: [https://github.com/MicrosoftDocs/office-docs-powershell](https://github.com/MicrosoftDocs/office-docs-powershell)</span></span>
  
<span data-ttu-id="5b1b8-117">Skype для бизнеса Server поставляется с более чем 700 командлетами, которые позволяют администраторам управлять Skype для бизнеса Server с помощью командной консоли Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="5b1b8-117">Skype for Business Server ships with more than 700 cmdlets that enable administrators to manage Skype for Business Server using the Skype for Business Server Management Shell.</span></span> <span data-ttu-id="5b1b8-118">Чтобы получить справку по командлету непосредственно из командной строки, введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="5b1b8-118">You can retrieve help for a cmdlet directly from the command line by typing a command similar to the following:</span></span>
  
```PowerShell
Get-Help New-CsVoicePolicy -Full
```

<span data-ttu-id="5b1b8-119">Предыдущая команда получает полную справку, доступную для командлета **New – CsVoicePolicy** .</span><span class="sxs-lookup"><span data-stu-id="5b1b8-119">The preceding command retrieves the complete help available for the **New-CsVoicePolicy** cmdlet.</span></span> <span data-ttu-id="5b1b8-120">Для просмотра справки по другому командлету замените **New-CsVoicePolicy** на имя командлета, для которого требуется получить справку.</span><span class="sxs-lookup"><span data-stu-id="5b1b8-120">To view help for a different cmdlet, substitute **New-CsVoicePolicy** with the name of the cmdlet for which you want to retrieve help.</span></span>
  
<span data-ttu-id="5b1b8-121">Чтобы получить полный список доступных командлетов для управления Skype для бизнеса Server, введите в командной строке командной консоли следующую команду:</span><span class="sxs-lookup"><span data-stu-id="5b1b8-121">To retrieve a full list of cmdlets available for managing Skype for Business Server, type the following at the shell command prompt:</span></span> 
  
```PowerShell
Get-Command * -Module SkypeforBusiness -CommandType cmdlet
```



<span data-ttu-id="5b1b8-122">Сведения о Windows PowerShell в Skype для бизнеса Server:</span><span class="sxs-lookup"><span data-stu-id="5b1b8-122">Things to know about Windows PowerShell in Skype for Business Server:</span></span>
  
- <span data-ttu-id="5b1b8-123">Чтобы запустить командлеты Skype для бизнеса Server, откройте консоль управления Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="5b1b8-123">To run the Skype for Business Server cmdlets, open the Skype for Business Server Management Shell.</span></span>
    
    > [!CAUTION]
    > <span data-ttu-id="5b1b8-124">Если открыть окно Windows PowerShell, а не командную консоль Skype для бизнеса Server, по умолчанию командлеты Skype могут оказаться недоступными.</span><span class="sxs-lookup"><span data-stu-id="5b1b8-124">If you open a Windows PowerShell window rather than the Skype for Business Server Management Shell, by default you may not be able to run the Skype cmdlets.</span></span> <span data-ttu-id="5b1b8-125">Чтобы запустить командлеты Skype для бизнеса Server в Windows PowerShell, сначала введите в командной строку Windows PowerShell следующую команду: >`Import-Module SkypeforBusiness`</span><span class="sxs-lookup"><span data-stu-id="5b1b8-125">To run Skype for Business Server cmdlets from within Windows PowerShell, first type the following at the Windows PowerShell command prompt: >  `Import-Module SkypeforBusiness`</span></span>
  
- <span data-ttu-id="5b1b8-126">Консоль управления Skype для бизнеса Server автоматически устанавливается на каждом сервере переднего плана Skype для бизнеса Server Enterprise Edition или на сервере Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="5b1b8-126">Skype for Business Server Management Shell is automatically installed on every Skype for Business Server Enterprise Edition Front End Server or Standard Edition server.</span></span>
    
- <span data-ttu-id="5b1b8-127">Вы можете обновить контент справки по командной консоли Skype для бизнеса Server, выполнив командлет [Update-Help](https://technet.microsoft.com/library/hh849720.aspx) .</span><span class="sxs-lookup"><span data-stu-id="5b1b8-127">You can update the Skype for Business Server Management Shell help content by running the [Update-Help](https://technet.microsoft.com/library/hh849720.aspx) cmdlet.</span></span> <span data-ttu-id="5b1b8-128">Командлет Update-Help загружает и устанавливает последние файлы справки, доступные для всех установленных на компьютере модулей, в том числе обновлений командлетов Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="5b1b8-128">The Update-Help cmdlet downloads and installs the newest help files available for all of the modules installed on your computer, including updates to Skype for Business cmdlets.</span></span>
    
    <span data-ttu-id="5b1b8-129">По умолчанию командлет **Update-Help** обновит все модули, установленные на сервере Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="5b1b8-129">By default, the **Update-Help** cmdlet will update all the modules installed on your Skype for Business Server.</span></span> <span data-ttu-id="5b1b8-130">Если необходимо обновить только определенные модули, можно использовать параметр _module_ , чтобы ограничить область действия командлета.</span><span class="sxs-lookup"><span data-stu-id="5b1b8-130">If you want to update only certain modules, you can use the _Module_ parameter to limit the scope of the cmdlet.</span></span> <span data-ttu-id="5b1b8-131">В следующем примере обновляется только модуль Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="5b1b8-131">The following example updates only the Skype for Business module.</span></span>
    
  ```PowerShell
  Update-Help -Module SkypeforBusiness
  ```

    <span data-ttu-id="5b1b8-132">Если вам нужно обновить справку на серверах, которые не подключены к Интернету, вы можете использовать командлет [Save — Help](https://technet.microsoft.com/library/hh849724.aspx) , чтобы получить последнюю версию справки и сохранить ее в указанном расположении.</span><span class="sxs-lookup"><span data-stu-id="5b1b8-132">If you need to update the Help on servers that are not connected to the internet, you can use the [Save-Help](https://technet.microsoft.com/library/hh849724.aspx) cmdlet to get the latest version of the help and save it to a location you specify.</span></span> <span data-ttu-id="5b1b8-133">Затем можно использовать командлет **Update – Help** с параметром _– SourcePath_ на серверах, не подключенных к Интернету, чтобы получить обновленную справку из выбранного расположения.</span><span class="sxs-lookup"><span data-stu-id="5b1b8-133">You can then use the **Update-Help** cmdlet with the _-SourcePath_ parameter on servers not connected to the internet to get the updated help from the location you selected.</span></span> <span data-ttu-id="5b1b8-134">В приведенном ниже примере показано, как сохранить файлы справки в сетевую общую папку, а затем обновить справку для модуля Skype для бизнеса из общей папки.</span><span class="sxs-lookup"><span data-stu-id="5b1b8-134">The following example shows how to save the help files to a network file share, and then update the help for the Skype for Business module from the file share.</span></span>
    
  ```PowerShell
  // Save the help files
   Save-Help -DestinationPath \\UpdateShare\HelpDownload
  // Run Update-Help against the local help files
   Update-Help -Module SkypeforBusiness -SourcePath \\UpdateShare\HelpDownload
  ```

    <span data-ttu-id="5b1b8-135">Более подробную информацию можно узнать в статье [сведения об обновляемой справке](https://technet.microsoft.com/library/hh847735.aspx).</span><span class="sxs-lookup"><span data-stu-id="5b1b8-135">For more detailed information, see [About Updatable Help](https://technet.microsoft.com/library/hh847735.aspx).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="5b1b8-136">Если вы используете PowerShell удаленно, вам может потребоваться разрешить связь через брандмауэр.</span><span class="sxs-lookup"><span data-stu-id="5b1b8-136">If you are using PowerShell remotely you may need to allow communication through a firewall.</span></span> <span data-ttu-id="5b1b8-137">Чтобы узнать больше о портах PowerShell, используемых удаленным взаимодействием PowerShell, посмотрите, [какой порт использует удаленное взаимодействие PowerShell?](https://blogs.technet.microsoft.com/christwe/2012/06/20/what-port-does-powershell-remoting-use/).</span><span class="sxs-lookup"><span data-stu-id="5b1b8-137">To learn more about the ports PowerShell remoting uses, see [What Port Does PowerShell Remoting Use?](https://blogs.technet.microsoft.com/christwe/2012/06/20/what-port-does-powershell-remoting-use/).</span></span>
    

