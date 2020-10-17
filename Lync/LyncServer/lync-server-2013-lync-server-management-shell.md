---
title: 'Lync Server 2013: Командная консоль Lync Server'
description: 'Lync Server 2013: Командная консоль Lync Server.'
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
ms.openlocfilehash: 45727c42899defcf20ce36e2a27a9268a52ecd71
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48543185"
---
# <a name="lync-server-2013-management-shell"></a><span data-ttu-id="9eccb-103">Lync Server 2013 Management Shell</span><span class="sxs-lookup"><span data-stu-id="9eccb-103">Lync Server 2013 Management Shell</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9eccb-104">_**Последнее изменение темы:** 2017-09-20_</span><span class="sxs-lookup"><span data-stu-id="9eccb-104">_**Topic Last Modified:** 2017-09-20_</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="9eccb-105">Ссылка на командлет Skype для бизнеса перемещена в docs.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="9eccb-105">Skype for Business cmdlet reference has moved to docs.microsoft.com.</span></span> <span data-ttu-id="9eccb-106">Перейдя по приведенным ниже ссылкам, вы перейдете на новую страницу docs.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="9eccb-106">Clicking on the links below will take you to the new docs.microsoft.com page.</span></span> <span data-ttu-id="9eccb-107">Теперь контент открыт в исходном и доступном для участия в сообществах с помощью GitHub.</span><span class="sxs-lookup"><span data-stu-id="9eccb-107">The content is now open sourced and available for community contributions through GitHub.</span></span> <span data-ttu-id="9eccb-108">Интересуетесь участниками?</span><span class="sxs-lookup"><span data-stu-id="9eccb-108">Interested in contributing?</span></span> <span data-ttu-id="9eccb-109">Ознакомьтесь со статьей README в репозитории здесь: <A href="https://github.com/microsoftdocs/office-docs-powershell">https://github.com/MicrosoftDocs/office-docs-powershell</A></span><span class="sxs-lookup"><span data-stu-id="9eccb-109">Check out the README in the repo here: <A href="https://github.com/microsoftdocs/office-docs-powershell">https://github.com/MicrosoftDocs/office-docs-powershell</A></span></span>



</div>

<span data-ttu-id="9eccb-110">В Microsoft Lync Server 2010 появился большой набор новых и улучшенных функций по сравнению с тем, что было доступно в Microsoft Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="9eccb-110">Microsoft Lync Server 2010 introduced a large set of new and improved features compared to what was available in Microsoft Office Communications Server 2007 R2.</span></span> <span data-ttu-id="9eccb-111">Одним из улучшений является способ управления реализацией.</span><span class="sxs-lookup"><span data-stu-id="9eccb-111">One improvement is the way in which you manage your implementation.</span></span> <span data-ttu-id="9eccb-112">Например, существует новый пользовательский интерфейс, называемый панелью управления Lync Server, который представляет большой сдвиг от большинства людей, используемых в консоли управления (MMC).</span><span class="sxs-lookup"><span data-stu-id="9eccb-112">For example, there’s a new user interface, called the Lync Server Control Panel, which represents a big shift from what most people are used to with the Microsoft Management Console.</span></span> <span data-ttu-id="9eccb-113">Другим важным улучшением управления является включение Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9eccb-113">The other major improvement to manageability is the inclusion of Windows PowerShell.</span></span>

<span data-ttu-id="9eccb-114">Windows PowerShell позволяет управлять приложениями Майкрософт из командной строки.</span><span class="sxs-lookup"><span data-stu-id="9eccb-114">Windows PowerShell allows you to manage Microsoft applications from the command line.</span></span> <span data-ttu-id="9eccb-115">Оно предоставляет среду командной строки, команды для определенных продуктов и полноценный язык скриптов.</span><span class="sxs-lookup"><span data-stu-id="9eccb-115">It includes a command-line environment, product-specific commands, and a full scripting language.</span></span> <span data-ttu-id="9eccb-116">Windows PowerShell впервые появился в качестве загружаемого выпуска для операционной системы Windows с опозданием в 2006 и был включен в качестве интерфейса командной строки для управления Microsoft Exchange Server 2007.</span><span class="sxs-lookup"><span data-stu-id="9eccb-116">Windows PowerShell was first introduced as a downloadable release for the Windows operating system late in 2006, and was incorporated as the command-line interface for manageability of Microsoft Exchange Server 2007.</span></span> <span data-ttu-id="9eccb-117">С этого точки он продолжает расти и включен в большинство серверных продуктов корпорации Майкрософт, самые последние из них — Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="9eccb-117">From that point it continued to grow, and it has been incorporated into most of the Microsoft Server products, the most recent of these being Microsoft Lync Server 2013.</span></span> <span data-ttu-id="9eccb-118">Lync Server 2010 представил более 550 командлетов для конкретных продуктов, которые можно использовать для управления каждым аспектом развертывания.</span><span class="sxs-lookup"><span data-stu-id="9eccb-118">Lync Server 2010 introduced close to 550 product-specific cmdlets that you can use to manage every aspect of your deployment.</span></span>

<span data-ttu-id="9eccb-119">В следующих разделах представлен список командлетов и их описание.</span><span class="sxs-lookup"><span data-stu-id="9eccb-119">The following sections contain a list of cmdlets and their descriptions.</span></span> <span data-ttu-id="9eccb-120">Эта информация также доступна напрямую из командной строки.</span><span class="sxs-lookup"><span data-stu-id="9eccb-120">This information is also available directly from the command line.</span></span> <span data-ttu-id="9eccb-121">Просто введите в командной строке Командная консоль Lync Server следующую команду:</span><span class="sxs-lookup"><span data-stu-id="9eccb-121">Simply type the following at the Lync Server Management Shell command prompt:</span></span>

    Get-Help <cmdlet name> -Full

<span data-ttu-id="9eccb-122">Например, чтобы получить справку по командлету **New-CsVoicePolicy** из командной строки, введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="9eccb-122">For example, to retrieve help from the command prompt on the **New-CsVoicePolicy** cmdlet, type the following:</span></span>

    Get-Help New-CsVoicePolicy -Full

<span data-ttu-id="9eccb-123">Что нужно знать о Windows PowerShell в Lync Server 2013:</span><span class="sxs-lookup"><span data-stu-id="9eccb-123">Things to know about Windows PowerShell in Lync Server 2013:</span></span>

  - <span data-ttu-id="9eccb-124">Чтобы запустить командлеты Lync Server, откройте консоль управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="9eccb-124">To run the Lync Server cmdlets, open the Lync Server Management Shell.</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="9eccb-125">Если открыть окно Windows PowerShell, а не командную консоль Lync Server, по умолчанию командлеты Lync Server не будут доступны.</span><span class="sxs-lookup"><span data-stu-id="9eccb-125">If you open a Windows PowerShell window rather than the Lync Server Management Shell, by default you will not be able to run the Lync Server cmdlets.</span></span> <span data-ttu-id="9eccb-126">Чтобы запустить командлеты Lync Server в Windows PowerShell, сначала введите следующую команду в командной строку Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="9eccb-126">To run the Lync Server cmdlets from within Windows PowerShell, first type the following at the Windows PowerShell command prompt:</span></span><BR><span data-ttu-id="9eccb-127">Import-Module Lync</span><span class="sxs-lookup"><span data-stu-id="9eccb-127">Import-Module Lync</span></span>

    
    </div>

  - <span data-ttu-id="9eccb-128">Консоль управления Lync Server автоматически устанавливается на каждом сервере переднего плана Lync Server Enterprise Edition или на сервере Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="9eccb-128">Lync Server Management Shell is automatically installed on every Lync Server Enterprise Edition Front End Server or Standard Edition server.</span></span>

  - <span data-ttu-id="9eccb-129">Новые и обновленные сведения, примеры сценариев и Справка по началу работы и дополнительные сведения о командлетах Windows PowerShell и Microsoft Lync Server 2013 доступны в блоге Lync Server Windows PowerShell [https://go.microsoft.com/fwlink/p/?linkId=203150](https://go.microsoft.com/fwlink/p/?linkid=203150) .</span><span class="sxs-lookup"><span data-stu-id="9eccb-129">New and updated information, sample scripts, and help for getting started and learning more about Windows PowerShell and Microsoft Lync Server 2013 cmdlets is available at the Lync Server Windows PowerShell Blog [https://go.microsoft.com/fwlink/p/?linkId=203150](https://go.microsoft.com/fwlink/p/?linkid=203150).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

