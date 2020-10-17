---
title: 'Lync Server 2013: подготовка к установке и установка анализатора соответствия рекомендациям'
description: 'Lync Server 2013: подготовка к установке и установка анализатора соответствия рекомендациям.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Preparing for and installing Best Practices Analyzer
ms:assetid: 550613dd-dc08-482e-9980-a3fe187cd162
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg591347(v=OCS.15)
ms:contentKeyID: 48184149
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 005c5ac372a3564e74af549832830ebae899e9d3
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48549935"
---
# <a name="preparing-for-and-installing-best-practices-analyzer-in-lync-server-2013"></a><span data-ttu-id="803f3-103">Подготовка и установка анализатора соответствия рекомендациям в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="803f3-103">Preparing for and installing Best Practices Analyzer in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="803f3-104">_**Последнее изменение темы:** 2013-11-07_</span><span class="sxs-lookup"><span data-stu-id="803f3-104">_**Topic Last Modified:** 2013-11-07_</span></span>

<span data-ttu-id="803f3-105">Необходимо выполнить вход в систему как член группы администраторов, чтобы выполнить задачи, приведены в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="803f3-105">You must be logged on as a member of the Administrators group to perform the tasks that are described in this topic.</span></span>

<div>

## <a name="system-requirements-for-best-practices-analyzer-installation"></a><span data-ttu-id="803f3-106">Системные требования для установки анализатора соответствия рекомендациям</span><span class="sxs-lookup"><span data-stu-id="803f3-106">System Requirements for Best Practices Analyzer Installation</span></span>

<span data-ttu-id="803f3-107">Чтобы запустить Lync Server 2013, анализатор соответствия рекомендациям для проверки среды, на компьютере должна быть установлена версия 64 (разрядная версия) одной из следующих операционных систем:</span><span class="sxs-lookup"><span data-stu-id="803f3-107">To run Lync Server 2013, Best Practices Analyzer to scan your environment, the computer must be running a 64-bit edition of one of the following operating systems:</span></span>

  - <span data-ttu-id="803f3-108">Windows Server 2008 R2 с пакетом обновления 1 (SP1) (SP1), стандартная операционная система</span><span class="sxs-lookup"><span data-stu-id="803f3-108">Windows Server 2008 R2 with Service Pack 1 (SP1) Standard operating system</span></span>

  - <span data-ttu-id="803f3-109">Операционная система Windows Server 2008 R2 с пакетом обновления 1 (SP1)</span><span class="sxs-lookup"><span data-stu-id="803f3-109">Windows Server 2008 R2 with SP1 Enterprise operating system</span></span>

  - <span data-ttu-id="803f3-110">Операционная система Windows Server 2008 R2 с пакетом обновления 1 (SP1)</span><span class="sxs-lookup"><span data-stu-id="803f3-110">Windows Server 2008 R2 with SP1 Datacenter operating system</span></span>

  - <span data-ttu-id="803f3-111">Операционная система Windows Server 2012 Datacenter</span><span class="sxs-lookup"><span data-stu-id="803f3-111">Windows Server 2012 Datacenter operating system</span></span>

  - <span data-ttu-id="803f3-112">Windows Server 2012 Standard операционная система</span><span class="sxs-lookup"><span data-stu-id="803f3-112">Windows Server 2012 Standard operating system</span></span>

  - <span data-ttu-id="803f3-113">Операционная система Windows Server 2012 Enterprise</span><span class="sxs-lookup"><span data-stu-id="803f3-113">Windows Server 2012 Enterprise operating system</span></span>

  - <span data-ttu-id="803f3-114">Операционная система Windows Server 2012 R2 Datacenter</span><span class="sxs-lookup"><span data-stu-id="803f3-114">Windows Server 2012 R2 Datacenter operating system</span></span>

  - <span data-ttu-id="803f3-115">Windows Server 2012 R2 (стандартная операционная система)</span><span class="sxs-lookup"><span data-stu-id="803f3-115">Windows Server 2012 R2 Standard operating system</span></span>

  - <span data-ttu-id="803f3-116">Операционная система Windows Server 2012 R2 Enterprise</span><span class="sxs-lookup"><span data-stu-id="803f3-116">Windows Server 2012 R2 Enterprise operating system</span></span>

  - <span data-ttu-id="803f3-117">Операционная система Windows 8</span><span class="sxs-lookup"><span data-stu-id="803f3-117">Windows 8 operating system</span></span>

  - <span data-ttu-id="803f3-118">Операционная система Windows 7</span><span class="sxs-lookup"><span data-stu-id="803f3-118">Windows 7 operating system</span></span>

<span data-ttu-id="803f3-119">На компьютере также должны работать следующие компоненты:</span><span class="sxs-lookup"><span data-stu-id="803f3-119">The computer must also be running the following:</span></span>

  - <span data-ttu-id="803f3-120">Microsoft .NET Framework 4,5.</span><span class="sxs-lookup"><span data-stu-id="803f3-120">Microsoft .NET Framework 4.5.</span></span> <span data-ttu-id="803f3-121">Для Lync Server 2013 необходимо вручную установить 64 – разрядную версию Microsoft .NET Framework 4,5 на сервере перед установкой Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="803f3-121">For Lync Server 2013, you must manually install the 64-bit edition of Microsoft .NET Framework 4.5 on the server prior to installing Lync Server 2013.</span></span>

  - <span data-ttu-id="803f3-122">Lync Server 2013, основные компоненты.</span><span class="sxs-lookup"><span data-stu-id="803f3-122">Lync Server 2013, Core Components.</span></span>

  - <span data-ttu-id="803f3-123">Пакет обратной совместимости WMI.</span><span class="sxs-lookup"><span data-stu-id="803f3-123">WMI Backward Compatibility Package.</span></span> <span data-ttu-id="803f3-124">Для получения дополнительных сведений обратитесь к разделу [Установка обратной СОВМЕСТИМОСТИ WMI](install-wmi-backward-compatibility-package.md) в документации по миграции.</span><span class="sxs-lookup"><span data-stu-id="803f3-124">For details, see [Install WMI Backward Compatibility package](install-wmi-backward-compatibility-package.md) in the Migration documentation.</span></span>

  - <span data-ttu-id="803f3-125">Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="803f3-125">Windows PowerShell 3.0.</span></span> <span data-ttu-id="803f3-126">Дополнительные сведения приведены в статье [Установка Windows PowerShell 3,0 для Lync Server 2013](lync-server-2013-installing-windows-powershell-3-0.md) в документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="803f3-126">For details, see [Installing Windows PowerShell 3.0 for Lync Server 2013](lync-server-2013-installing-windows-powershell-3-0.md) in the Deployment documentation.</span></span>

<span data-ttu-id="803f3-127">Анализатор соответствия рекомендациям можно установить на компьютерах с поддерживаемой операционной системой, не использующей Lync Server 2013, основные компоненты или пакет обратной совместимости WMI, но вы можете использовать анализатор соответствия рекомендациям только для просмотра отчетов, а не для запуска проверок.</span><span class="sxs-lookup"><span data-stu-id="803f3-127">You can install Best Practices Analyzer on computers with a supported operating system that are not running Lync Server 2013, Core Components or WMI Backward Compatibility Package, but you can use Best Practices Analyzer on those computers only to view reports, not to run scans.</span></span>

</div>

<div>

## <a name="choosing-a-computer-for-installation"></a><span data-ttu-id="803f3-128">Выбор компьютера для установки</span><span class="sxs-lookup"><span data-stu-id="803f3-128">Choosing a Computer for Installation</span></span>

<span data-ttu-id="803f3-129">Мы рекомендуем установить Lync Server 2013, анализатор соответствия рекомендациям на компьютере, выделенном для управления Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="803f3-129">We recommend that you install Lync Server 2013, Best Practices Analyzer on a computer that is dedicated to Lync Server 2013 management.</span></span> <span data-ttu-id="803f3-130">Средство можно установить на сервере, работающем под управлением Lync Server 2013 или на административном компьютере, на котором запущены средства администрирования Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="803f3-130">You can install the tool on a server running Lync Server 2013 or an administrative computer running Lync Server 2013 administrative tools.</span></span> <span data-ttu-id="803f3-131">При установке средства на сервере, на котором работает Lync Server, рекомендуется использовать это средство для сканирования только этого сервера.</span><span class="sxs-lookup"><span data-stu-id="803f3-131">If you install the tool on a server that is running Lync Server, we recommend that you use the tool to scan only that server.</span></span>

</div>

<div>

## <a name="installing-best-practices-analyzer"></a><span data-ttu-id="803f3-132">Установка анализатора соответствия рекомендациям</span><span class="sxs-lookup"><span data-stu-id="803f3-132">Installing Best Practices Analyzer</span></span>

<span data-ttu-id="803f3-133">Вы можете скачать анализатор соответствия рекомендациям для Lync Server 2013 по адресу [https://go.microsoft.com/fwlink/p/?linkId=266539](https://go.microsoft.com/fwlink/p/?linkid=266539) .</span><span class="sxs-lookup"><span data-stu-id="803f3-133">You can download the Best Practices Analyzer for Lync Server 2013 at [https://go.microsoft.com/fwlink/p/?linkId=266539](https://go.microsoft.com/fwlink/p/?linkid=266539).</span></span>

<span data-ttu-id="803f3-134">Чтобы установить анализатор соответствия рекомендациям, запустите файл установщика Microsoft RtcBPA.msi на компьютере, где необходимо установить средство, затем следуйте инструкциям на экране.</span><span class="sxs-lookup"><span data-stu-id="803f3-134">To install Best Practices Analyzer, start the Microsoft Installer file RtcBPA.msi on the computer where you want to install the tool, and then follow the instructions on the screen.</span></span> <span data-ttu-id="803f3-135">В качестве расположения по умолчанию для установки программных файлов задается \<system drive\> \\ программный файл \\ Lync Server 2013 \\ BPA.</span><span class="sxs-lookup"><span data-stu-id="803f3-135">The default location for installing the program files is \<system drive\>\\Program Files\\Lync Server 2013\\BPA.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

