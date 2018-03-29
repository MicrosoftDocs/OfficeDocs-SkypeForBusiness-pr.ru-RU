---
title: Командная консоль Skype для бизнеса Server 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 9/20/2017
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 674b523b-c0b7-4ed6-9e67-afa6e8ac7e12
description: Скайп для консоли Business Server содержит интерфейс командной строки для администрирования и управления сервером. Создан на основе Windows PowerShell, а также полный набор командлетов управления и администрирования, относящиеся к Скайп и прежних версий продуктов Lync server.
ms.openlocfilehash: e4eb5f183af29dd5f9932fb15cdb86a0f78e7840
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/28/2018
---
# <a name="skype-for-business-server-2015-management-shell"></a><span data-ttu-id="aa26c-104">Командная консоль Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="aa26c-104">Skype for Business Server 2015 Management Shell</span></span>
 
<span data-ttu-id="aa26c-105">Скайп для консоли Business Server содержит интерфейс командной строки для администрирования и управления сервером.</span><span class="sxs-lookup"><span data-stu-id="aa26c-105">The Skype for Business Server Management Shell provides the command line interface for server administration and management.</span></span> <span data-ttu-id="aa26c-106">Создан на основе Windows PowerShell, а также полный набор командлетов управления и администрирования, относящиеся к Скайп и прежних версий продуктов Lync server.</span><span class="sxs-lookup"><span data-stu-id="aa26c-106">It is built on Windows PowerShell and includes a comprehensive set of management and administration cmdlets that are specific to Skype and legacy Lync server products.</span></span>
  
<span data-ttu-id="aa26c-107">Windows PowerShell позволяет управлять приложениями корпорации Майкрософт с помощью командной строки.</span><span class="sxs-lookup"><span data-stu-id="aa26c-107">Windows PowerShell allows you to manage Microsoft applications from the command line.</span></span> <span data-ttu-id="aa26c-108">Содержит среды командной строки, команды конкретного продукта и полный языка сценариев.</span><span class="sxs-lookup"><span data-stu-id="aa26c-108">It includes a command-line environment, product-specific commands, and a full scripting language.</span></span> <span data-ttu-id="aa26c-109">Windows PowerShell была впервые введена как загружаемая версия для операционной системы Windows позднее в 2006 г. и был включены как интерфейс командной строки для управления Microsoft Exchange Server 2007.</span><span class="sxs-lookup"><span data-stu-id="aa26c-109">Windows PowerShell was first introduced as a downloadable release for the Windows operating system late in 2006, and was incorporated as the command-line interface for manageability of Microsoft Exchange Server 2007.</span></span> <span data-ttu-id="aa26c-110">Он был включен в большинство серверных продуктов Майкрософт, включая Lync и Скайп серверы, Приступая к работе с Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="aa26c-110">It has been incorporated into most of the Microsoft Server products, including Lync and Skype servers beginning with Lync Server 2010.</span></span> <span data-ttu-id="aa26c-111">Около 700 определенные командлеты Lync и Скайп доступны в Скайп для консоли Business Server.</span><span class="sxs-lookup"><span data-stu-id="aa26c-111">There are over 700 Lync and Skype specific cmdlets available in the Skype for Business Server Management Shell.</span></span>
  
> [!NOTE]
> <span data-ttu-id="aa26c-112">Скайп для бизнеса Справочник командлетов перемещен в docs.microsoft.com. Нажатие на приведенные ниже ссылки вы перейдете к новой страницы docs.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="aa26c-112">Skype for Business cmdlet reference has moved to docs.microsoft.com. Clicking on the links below will take you to the new docs.microsoft.com page.</span></span> <span data-ttu-id="aa26c-113">Теперь весь контент предлагается с открытым исходным кодом и доступен в сообществе GitHub.</span><span class="sxs-lookup"><span data-stu-id="aa26c-113">The content is now open sourced and available for community contributions through GitHub.</span></span> <span data-ttu-id="aa26c-114">Хотите принять участие в работе с ним?</span><span class="sxs-lookup"><span data-stu-id="aa26c-114">Interested in contributing?</span></span> <span data-ttu-id="aa26c-115">Извлечение сведений в repo здесь:[https://github.com/MicrosoftDocs/office-docs-powershell](https://github.com/MicrosoftDocs/office-docs-powershell)</span><span class="sxs-lookup"><span data-stu-id="aa26c-115">Check out the README in the repo here: [https://github.com/MicrosoftDocs/office-docs-powershell](https://github.com/MicrosoftDocs/office-docs-powershell)</span></span>
  
<span data-ttu-id="aa26c-116">Скайп для Business Server 2015 поставляется с более чем 700 командлетов, которые позволяют администраторам управлять Скайп для Business Server, с помощью Скайп для консоли Business Server.</span><span class="sxs-lookup"><span data-stu-id="aa26c-116">Skype for Business Server 2015 ships with more than 700 cmdlets that enable administrators to manage Skype for Business Server using the Skype for Business Server Management Shell.</span></span> <span data-ttu-id="aa26c-117">Вы можете получить справку по командлету непосредственно в командной строке, введя следующую команду:</span><span class="sxs-lookup"><span data-stu-id="aa26c-117">You can retrieve help for a cmdlet directly from the command line by typing a command similar to the following:</span></span>
  
```
Get-Help New-CsVoicePolicy -Full
```

<span data-ttu-id="aa26c-118">Предыдущая команда извлекает всю справку, доступные для командлета **New-CsVoicePolicy** .</span><span class="sxs-lookup"><span data-stu-id="aa26c-118">The preceding command retrieves the complete help available for the **New-CsVoicePolicy** cmdlet.</span></span> <span data-ttu-id="aa26c-119">Чтобы просмотреть справку для разных командлета, замените **New-CsVoicePolicy** с именем командлета, для которого требуется получить справку.</span><span class="sxs-lookup"><span data-stu-id="aa26c-119">To view help for a different cmdlet, substitute **New-CsVoicePolicy** with the name of the cmdlet for which you want to retrieve help.</span></span>
  
<span data-ttu-id="aa26c-120">Чтобы получить полный список доступных командлетов для управления Skype для бизнеса Server, введите в командной строке оболочки следующую команду. </span><span class="sxs-lookup"><span data-stu-id="aa26c-120">To retrieve a full list of cmdlets available for managing Skype for Business Server, type the following at the shell command prompt:</span></span> 
  
```
Get-Command * -Module SkypeforBusiness -CommandType cmdlet
```



<span data-ttu-id="aa26c-121">Что нужно знать о Windows PowerShell в Скайп для Business Server:</span><span class="sxs-lookup"><span data-stu-id="aa26c-121">Things to know about Windows PowerShell in Skype for Business Server:</span></span>
  
- <span data-ttu-id="aa26c-122">Чтобы запустить Скайп по командлетам Business Server, откройте Скайп для консоли Business Server.</span><span class="sxs-lookup"><span data-stu-id="aa26c-122">To run the Skype for Business Server cmdlets, open the Skype for Business Server Management Shell.</span></span>
    
    > [!CAUTION]
    > <span data-ttu-id="aa26c-123">При открытии окна Windows PowerShell, а не Скайп для консоли Business Server по умолчанию не можно для запуска командлетов Скайп.</span><span class="sxs-lookup"><span data-stu-id="aa26c-123">If you open a Windows PowerShell window rather than the Skype for Business Server Management Shell, by default you may not be able to run the Skype cmdlets.</span></span> <span data-ttu-id="aa26c-124">Чтобы запустить Скайп по командлетам Business Server из в Windows PowerShell, сначала введите следующее в командной строке Windows PowerShell: >`Import-Module SkypeforBusiness`</span><span class="sxs-lookup"><span data-stu-id="aa26c-124">To run Skype for Business Server cmdlets from within Windows PowerShell, first type the following at the Windows PowerShell command prompt: >  `Import-Module SkypeforBusiness`</span></span>
  
- <span data-ttu-id="aa26c-125">Скайп для консоли Business Server автоматически устанавливается на каждом Скайп для Business Server Enterprise Edition сервера переднего плана или сервере Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="aa26c-125">Skype for Business Server Management Shell is automatically installed on every Skype for Business Server Enterprise Edition Front End Server or Standard Edition server.</span></span>
    
- <span data-ttu-id="aa26c-126">Скайп для содержимого справки консоли Business Server можно обновить с помощью командлета [Update-Help](https://technet.microsoft.com/en-us/library/hh849720.aspx) .</span><span class="sxs-lookup"><span data-stu-id="aa26c-126">You can update the Skype for Business Server Management Shell help content by running the [Update-Help](https://technet.microsoft.com/en-us/library/hh849720.aspx) cmdlet.</span></span> <span data-ttu-id="aa26c-127">Командлет Update-Help загружает и устанавливает новые файлы справки доступны для всех модулей, установленный на компьютере, включая обновления Скайп для бизнеса командлетов.</span><span class="sxs-lookup"><span data-stu-id="aa26c-127">The Update-Help cmdlet downloads and installs the newest help files available for all of the modules installed on your computer, including updates to Skype for Business cmdlets.</span></span>
    
    <span data-ttu-id="aa26c-128">По умолчанию командлет **Update-Help** приведут к обновлению всех модулей, установленные на ваш Скайп для Business Server.</span><span class="sxs-lookup"><span data-stu-id="aa26c-128">By default, the **Update-Help** cmdlet will update all the modules installed on your Skype for Business Server.</span></span> <span data-ttu-id="aa26c-129">Если вы хотите обновить только определенные модули, параметр _модуль_ можно использовать для ограничения области командлета.</span><span class="sxs-lookup"><span data-stu-id="aa26c-129">If you want to update only certain modules, you can use the _Module_ parameter to limit the scope of the cmdlet.</span></span> <span data-ttu-id="aa26c-130">В следующем примере обновляются только Скайп для бизнес-модуля.</span><span class="sxs-lookup"><span data-stu-id="aa26c-130">The following example updates only the Skype for Business module.</span></span>
    
  ```
  Update-Help -Module SkypeforBusiness
  ```

    <span data-ttu-id="aa26c-131">Если вам потребуется обновить справки на серверах, не подключенные к Интернету, командлет [Сохранить справки](https://technet.microsoft.com/en-us/library/hh849724.aspx) для получения последней версии справки и сохраните его в папку, в которой указан.</span><span class="sxs-lookup"><span data-stu-id="aa26c-131">If you need to update the Help on servers that are not connected to the internet, you can use the [Save-Help](https://technet.microsoft.com/en-us/library/hh849724.aspx) cmdlet to get the latest version of the help and save it to a location you specify.</span></span> <span data-ttu-id="aa26c-132">Затем можно использовать командлет **Update-Help** с параметром _- SourcePath_ на серверах, не подключенных к Интернету для получения обновленной справки с выбранной папке.</span><span class="sxs-lookup"><span data-stu-id="aa26c-132">You can then use the **Update-Help** cmdlet with the _-SourcePath_ parameter on servers not connected to the internet to get the updated help from the location you selected.</span></span> <span data-ttu-id="aa26c-133">Следующем примере показано, как сохранить файлы справки в сетевую общую папку, а затем обновить справку по Скайп для бизнес-модуля из общей папки.</span><span class="sxs-lookup"><span data-stu-id="aa26c-133">The following example shows how to save the help files to a network file share, and then update the help for the Skype for Business module from the file share.</span></span>
    
  ```
  // Save the help files
   Save-Help -DestinationPath \\UpdateShare\HelpDownload
// Run Update-Help against the local help files
   Update-Help -Module SkypeforBusiness -SourcePath \\UpdateShare\HelpDownload
  ```

    <span data-ttu-id="aa26c-134">Для получения дополнительных сведений см [о обновляемым](https://technet.microsoft.com/library/hh847735.aspx).</span><span class="sxs-lookup"><span data-stu-id="aa26c-134">For more detailed information, see [About Updatable Help](https://technet.microsoft.com/library/hh847735.aspx).</span></span>
    

