---
title: Объединение командлетов Skype для бизнеса Online с другими командлетами Windows PowerShell в
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Combining Skype for Business Online cmdlets with other Windows PowerShell cmdlets
ms:assetid: 8bb8800a-f966-4570-8c8b-db87a91ad783
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362816(v=OCS.15)
ms:contentKeyID: 56558835
ms.date: 05/04/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: eb395820f9f90060ac24b737fab08c7d615727c2
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48499616"
---
# <a name="combining-skype-for-business-online-cmdlets-with-other-windows-powershell-cmdlets-in"></a><span data-ttu-id="5ee1a-102">Объединение командлетов Skype для бизнеса Online с другими командлетами Windows PowerShell в</span><span class="sxs-lookup"><span data-stu-id="5ee1a-102">Combining Skype for Business Online cmdlets with other Windows PowerShell cmdlets in</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5ee1a-103">_**Последнее изменение темы:** 2013-07-05_</span><span class="sxs-lookup"><span data-stu-id="5ee1a-103">_**Topic Last Modified:** 2013-07-05_</span></span>

<span data-ttu-id="5ee1a-104">При подключении к Skype для бизнеса Online с помощью Windows PowerShell около 40 командлетов Skype для бизнеса Online будут доступны для использования.</span><span class="sxs-lookup"><span data-stu-id="5ee1a-104">When you connect to Skype for Business Online by using Windows PowerShell, approximately 40 Skype for Business Online cmdlets will available for your use.</span></span> <span data-ttu-id="5ee1a-105">Однако при управлении Skype для бизнеса Online не ограничено использование только этих командлетов 40.</span><span class="sxs-lookup"><span data-stu-id="5ee1a-105">However, you are not limited to using just those 40 cmdlets when managing Skype for Business Online.</span></span> <span data-ttu-id="5ee1a-106">Кроме командлетов Skype для бизнеса Online, вы также можете использовать любые другие командлеты Windows PowerShell, установленные на компьютере.</span><span class="sxs-lookup"><span data-stu-id="5ee1a-106">In addition to the Skype for Business Online cmdlets, you can also use any other Windows PowerShell cmdlets that are installed on your computer.</span></span> <span data-ttu-id="5ee1a-107">(При установке Windows PowerShell 3,0 также устанавливаются сотни основных командлетов Windows PowerShell.) Команды могут сочетать и сопоставлять командлеты Skype для бизнеса Online, а также любые другие командлеты, доступные на вашем компьютере.</span><span class="sxs-lookup"><span data-stu-id="5ee1a-107">(When you install Windows PowerShell 3.0, hundreds of core Windows PowerShell cmdlets are installed, as well.) Your commands can mix and match Skype for Business Online cmdlets and any other cmdlets available on your computer.</span></span>

<span data-ttu-id="5ee1a-108">Несмотря на то, что полный курс в Windows PowerShell 3,0 выходит за рамки этой статьи, здесь представлено несколько примеров, в которых показано, что вы можете использовать командлеты для сочетания и сравнения.</span><span class="sxs-lookup"><span data-stu-id="5ee1a-108">Although a complete course in Windows PowerShell 3.0 goes beyond the scope of this article, here are a few examples that show why you might want to mix and match cmdlets.</span></span> <span data-ttu-id="5ee1a-109">Во-первых, ни один из командлетов Skype для бизнеса Online не включает команду "Печать", поэтому в консоли Windows PowerShell не удается найти такую команду:.</span><span class="sxs-lookup"><span data-stu-id="5ee1a-109">First of all, none of the Skype for Business Online cmdlets include a Print command, and no such command can be found in the Windows PowerShell console, either.</span></span> <span data-ttu-id="5ee1a-110">Как получить распечатку информации, полученной командлетом?</span><span class="sxs-lookup"><span data-stu-id="5ee1a-110">So how do you get a printout of the information retrieved by a cmdlet?</span></span> <span data-ttu-id="5ee1a-111">Один способ получить сведения, а затем отправить их в командлет **Out-Printer** :</span><span class="sxs-lookup"><span data-stu-id="5ee1a-111">One way is to retrieve the information, and then send that information to the **Out-Printer** cmdlet:</span></span>

    Get-CsTenant | Out-Printer

<span data-ttu-id="5ee1a-112">Так как дополнительные параметры не включены, все данные, возвращенные командлетом **Out-Printer** , будут распечатаны на принтере по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="5ee1a-112">Because no additional parameters are included, all the information returned by **the Out-Printer** cmdlet will be printed to the default printer.</span></span>

<span data-ttu-id="5ee1a-113">Аналогично, ни один из командлетов Skype для бизнеса Online не содержит параметр, позволяющий сохранять данные в файл.</span><span class="sxs-lookup"><span data-stu-id="5ee1a-113">Likewise, none of the Skype for Business Online cmdlets include a parameter that allows you to save data to a file.</span></span> <span data-ttu-id="5ee1a-114">Но это нормально: Эта команда использует командлет **Out – File** для сохранения возвращенных данных в текстовом файле C: \\ logs \\Tenants.txt:</span><span class="sxs-lookup"><span data-stu-id="5ee1a-114">But that’s OK: this command uses the **Out-File** cmdlet to save the returned information to the text file C:\\Logs\\Tenants.txt:</span></span>

    Get-Tenant | Out-File -FilePath "C:\Logs\Tenants.txt"

<span data-ttu-id="5ee1a-115">Эта команда использует командлет **Select-Object** для ограничения данных, возвращаемых и отображаемых на экране.</span><span class="sxs-lookup"><span data-stu-id="5ee1a-115">And this command uses the **Select-Object** cmdlet to limit the data that is returned and displayed onscreen.</span></span> <span data-ttu-id="5ee1a-116">В этом примере командлет [Get-CsOnlineUser](https://technet.microsoft.com/library/JJ994026(v=OCS.15)) получает сведения обо всех пользователях Skype для бизнеса Online, а затем используется командлет **Select-Object** , чтобы ограничить отображаемые данные значением удостоверения пользователя и их политикой архивации:</span><span class="sxs-lookup"><span data-stu-id="5ee1a-116">In this example, the [Get-CsOnlineUser](https://technet.microsoft.com/library/JJ994026(v=OCS.15)) cmdlet retrieves information for all of your Skype for Business Online users, and then the **Select-Object** cmdlet is used to limit the displayed data to the user’s Identity value and their archiving policy:</span></span>

    Get-CsOnlineUser | Select-Object Identity, ArchivingPolicy

<span data-ttu-id="5ee1a-117">Так как на компьютере будут доступны сотни командлетов, может быть трудно определить, какие командлеты используются в командлетах Skype для бизнеса Online, а какие нет.</span><span class="sxs-lookup"><span data-stu-id="5ee1a-117">Because there will be hundreds of cmdlets available for use on your computer, you might have difficulty determining which cmdlets are Skype for Business Online cmdlets and which ones are not.</span></span> <span data-ttu-id="5ee1a-118">Чтобы получить список командлетов Skype для бизнеса Online (и только командлетов Skype для бизнеса Online), сначала необходимо определить имя временного модуля Windows PowerShell, содержащего все командлеты Skype для бизнеса Online.</span><span class="sxs-lookup"><span data-stu-id="5ee1a-118">To return a list of the Skype for Business Online cmdlets (and only Skype for Business Online cmdlets), you must first determine the name of the temporary Windows PowerShell module that contains all the Skype for Business Online cmdlets.</span></span> <span data-ttu-id="5ee1a-119">Чтобы сделать это, запустите эту команду в командной строке Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="5ee1a-119">To do that, run this command from the Windows PowerShell prompt:</span></span>

    Get-Module

<span data-ttu-id="5ee1a-120">На экране будут отображаться следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="5ee1a-120">Information similar to the following will appear onscreen:</span></span>

    ModuleType Name                 ExportedCommands
    ---------- ----                 ----------------
    Manifest   Microsoft.PowerS...  {Add-Computer, Add-Content, A...}
    Script     tmp_5astd3uh.m5v     {Disable-CsMeetingRoom, Enabl...}

<span data-ttu-id="5ee1a-121">Модуль с скриптом ModuleType — это модуль, который содержит командлеты Skype для бизнеса Online.</span><span class="sxs-lookup"><span data-stu-id="5ee1a-121">The module with the ModuleType Script is the module that contains the Skype for Business Online cmdlets.</span></span> <span data-ttu-id="5ee1a-122">Чтобы получить список этих командлетов, выполните командлет **Get – Command** , используя имя модуля скрипта в качестве имени модуля:</span><span class="sxs-lookup"><span data-stu-id="5ee1a-122">To return a list of those cmdlets, run the **Get-Command** cmdlet, using the name of the Script module as the module name:</span></span>

    Get-Command -Module tmp_5astd3uh.m5v

<span data-ttu-id="5ee1a-123">Возможно, у вас может быть несколько модулей со значением ModuleType, равным сценарию.</span><span class="sxs-lookup"><span data-stu-id="5ee1a-123">It’s possible that you could have multiple modules with a ModuleType equal to Script.</span></span> <span data-ttu-id="5ee1a-124">В этом случае можно выполнить следующую команду, чтобы узнать, какой модуль включает командлет **Get – CsTenant** :</span><span class="sxs-lookup"><span data-stu-id="5ee1a-124">In that case, you can run the following command to find out which module includes the **Get-CsTenant** cmdlet:</span></span>

    Get-Command Get-CsTenant

<span data-ttu-id="5ee1a-125">Модуль, возвращенный для командлета **Get-CsTenant** , будет модулем, содержащим все командлеты Skype для бизнеса Online:</span><span class="sxs-lookup"><span data-stu-id="5ee1a-125">The module returned for the **Get-CsTenant** cmdlet will be the module containing all the Skype for Business Online cmdlets:</span></span>

    CommandType     Name                                               ModuleName
    -----------     ----                                               ----------
    Function        Get-CsTenant                                       tmp_5astd3uh.m5v

<div>

## <a name="see-also"></a><span data-ttu-id="5ee1a-126">См. также</span><span class="sxs-lookup"><span data-stu-id="5ee1a-126">See Also</span></span>


<span data-ttu-id="5ee1a-127">[Введение в Windows PowerShell и Skype для бизнеса Online](https://technet.microsoft.com/library/Dn362785(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="5ee1a-127">[An introduction to Windows PowerShell and Skype for Business Online](https://technet.microsoft.com/library/Dn362785(v=OCS.15))</span></span>  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

