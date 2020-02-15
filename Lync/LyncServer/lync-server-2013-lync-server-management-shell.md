---
title: 'Lync Server 2013: Командная консоль Lync Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Lync Server Management Shell
ms:assetid: 674b523b-c0b7-4ed6-9e67-afa6e8ac7e12
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398474(v=OCS.15)
ms:contentKeyID: 48184386
ms.date: 09/20/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8d8ba2330e59d4f352407d94c6e73f96a5fff816
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2020
ms.locfileid: "42006165"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="lync-server-2013-management-shell"></a><span data-ttu-id="7f0e9-102">Lync Server 2013 Management Shell</span><span class="sxs-lookup"><span data-stu-id="7f0e9-102">Lync Server 2013 Management Shell</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7f0e9-103">_**Последнее изменение темы:** 2017-09-20_</span><span class="sxs-lookup"><span data-stu-id="7f0e9-103">_**Topic Last Modified:** 2017-09-20_</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="7f0e9-104">Ссылка на командлет Skype для бизнеса перемещена в docs.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="7f0e9-104">Skype for Business cmdlet reference has moved to docs.microsoft.com.</span></span> <span data-ttu-id="7f0e9-105">Перейдя по приведенным ниже ссылкам, вы перейдете на новую страницу docs.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="7f0e9-105">Clicking on the links below will take you to the new docs.microsoft.com page.</span></span> <span data-ttu-id="7f0e9-106">Теперь контент открыт в исходном и доступном для участия в сообществах с помощью GitHub.</span><span class="sxs-lookup"><span data-stu-id="7f0e9-106">The content is now open sourced and available for community contributions through GitHub.</span></span> <span data-ttu-id="7f0e9-107">Интересуетесь участниками?</span><span class="sxs-lookup"><span data-stu-id="7f0e9-107">Interested in contributing?</span></span> <span data-ttu-id="7f0e9-108">Ознакомьтесь со статьей README в репозитории здесь:<A href="https://github.com/microsoftdocs/office-docs-powershell">https://github.com/MicrosoftDocs/office-docs-powershell</A></span><span class="sxs-lookup"><span data-stu-id="7f0e9-108">Check out the README in the repo here: <A href="https://github.com/microsoftdocs/office-docs-powershell">https://github.com/MicrosoftDocs/office-docs-powershell</A></span></span>



</div>

<span data-ttu-id="7f0e9-109">В Microsoft Lync Server 2010 появился большой набор новых и улучшенных функций по сравнению с тем, что было доступно в Microsoft Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="7f0e9-109">Microsoft Lync Server 2010 introduced a large set of new and improved features compared to what was available in Microsoft Office Communications Server 2007 R2.</span></span> <span data-ttu-id="7f0e9-110">Одним из улучшений является способ управления реализацией.</span><span class="sxs-lookup"><span data-stu-id="7f0e9-110">One improvement is the way in which you manage your implementation.</span></span> <span data-ttu-id="7f0e9-111">Например, существует новый пользовательский интерфейс, называемый панелью управления Lync Server, который представляет большой сдвиг от большинства людей, используемых в консоли управления (MMC).</span><span class="sxs-lookup"><span data-stu-id="7f0e9-111">For example, there’s a new user interface, called the Lync Server Control Panel, which represents a big shift from what most people are used to with the Microsoft Management Console.</span></span> <span data-ttu-id="7f0e9-112">Другим важным улучшением управления является включение Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="7f0e9-112">The other major improvement to manageability is the inclusion of Windows PowerShell.</span></span>

<span data-ttu-id="7f0e9-113">Windows PowerShell позволяет управлять приложениями Майкрософт из командной строки.</span><span class="sxs-lookup"><span data-stu-id="7f0e9-113">Windows PowerShell allows you to manage Microsoft applications from the command line.</span></span> <span data-ttu-id="7f0e9-114">Оно предоставляет среду командной строки, команды для определенных продуктов и полноценный язык скриптов.</span><span class="sxs-lookup"><span data-stu-id="7f0e9-114">It includes a command-line environment, product-specific commands, and a full scripting language.</span></span> <span data-ttu-id="7f0e9-115">Windows PowerShell впервые появился в качестве загружаемого выпуска для операционной системы Windows с опозданием в 2006 и был включен в качестве интерфейса командной строки для управления Microsoft Exchange Server 2007.</span><span class="sxs-lookup"><span data-stu-id="7f0e9-115">Windows PowerShell was first introduced as a downloadable release for the Windows operating system late in 2006, and was incorporated as the command-line interface for manageability of Microsoft Exchange Server 2007.</span></span> <span data-ttu-id="7f0e9-116">С этого точки он продолжает расти и включен в большинство серверных продуктов корпорации Майкрософт, самые последние из них — Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7f0e9-116">From that point it continued to grow, and it has been incorporated into most of the Microsoft Server products, the most recent of these being Microsoft Lync Server 2013.</span></span> <span data-ttu-id="7f0e9-117">Lync Server 2010 представил более 550 командлетов для конкретных продуктов, которые можно использовать для управления каждым аспектом развертывания.</span><span class="sxs-lookup"><span data-stu-id="7f0e9-117">Lync Server 2010 introduced close to 550 product-specific cmdlets that you can use to manage every aspect of your deployment.</span></span>

<span data-ttu-id="7f0e9-118">В следующих разделах представлен список командлетов и их описание.</span><span class="sxs-lookup"><span data-stu-id="7f0e9-118">The following sections contain a list of cmdlets and their descriptions.</span></span> <span data-ttu-id="7f0e9-119">Эта информация также доступна напрямую из командной строки.</span><span class="sxs-lookup"><span data-stu-id="7f0e9-119">This information is also available directly from the command line.</span></span> <span data-ttu-id="7f0e9-120">Просто введите в командной строке Командная консоль Lync Server следующую команду:</span><span class="sxs-lookup"><span data-stu-id="7f0e9-120">Simply type the following at the Lync Server Management Shell command prompt:</span></span>

    Get-Help <cmdlet name> -Full

<span data-ttu-id="7f0e9-121">Например, чтобы получить справку по командлету **New-CsVoicePolicy** из командной строки, введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="7f0e9-121">For example, to retrieve help from the command prompt on the **New-CsVoicePolicy** cmdlet, type the following:</span></span>

    Get-Help New-CsVoicePolicy -Full

<span data-ttu-id="7f0e9-122">Что нужно знать о Windows PowerShell в Lync Server 2013:</span><span class="sxs-lookup"><span data-stu-id="7f0e9-122">Things to know about Windows PowerShell in Lync Server 2013:</span></span>

  - <span data-ttu-id="7f0e9-123">Чтобы запустить командлеты Lync Server, откройте консоль управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="7f0e9-123">To run the Lync Server cmdlets, open the Lync Server Management Shell.</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="7f0e9-124">Если открыть окно Windows PowerShell, а не командную консоль Lync Server, по умолчанию командлеты Lync Server не будут доступны.</span><span class="sxs-lookup"><span data-stu-id="7f0e9-124">If you open a Windows PowerShell window rather than the Lync Server Management Shell, by default you will not be able to run the Lync Server cmdlets.</span></span> <span data-ttu-id="7f0e9-125">Чтобы запустить командлеты Lync Server в Windows PowerShell, сначала введите следующую команду в командной строку Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="7f0e9-125">To run the Lync Server cmdlets from within Windows PowerShell, first type the following at the Windows PowerShell command prompt:</span></span><BR><span data-ttu-id="7f0e9-126">Import-Module Lync</span><span class="sxs-lookup"><span data-stu-id="7f0e9-126">Import-Module Lync</span></span>

    
    </div>

  - <span data-ttu-id="7f0e9-127">Консоль управления Lync Server автоматически устанавливается на каждом сервере переднего плана Lync Server Enterprise Edition или на сервере Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="7f0e9-127">Lync Server Management Shell is automatically installed on every Lync Server Enterprise Edition Front End Server or Standard Edition server.</span></span>

  - <span data-ttu-id="7f0e9-128">Новые и обновленные сведения, примеры сценариев и Справка по началу работы и дополнительные сведения о командлетах Windows PowerShell и Microsoft Lync Server 2013 доступны в блоге [https://go.microsoft.com/fwlink/p/?linkId=203150](https://go.microsoft.com/fwlink/p/?linkid=203150)Lync Server Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="7f0e9-128">New and updated information, sample scripts, and help for getting started and learning more about Windows PowerShell and Microsoft Lync Server 2013 cmdlets is available at the Lync Server Windows PowerShell Blog [https://go.microsoft.com/fwlink/p/?linkId=203150](https://go.microsoft.com/fwlink/p/?linkid=203150).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

