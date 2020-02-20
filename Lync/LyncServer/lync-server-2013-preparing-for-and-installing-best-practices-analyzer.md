---
title: 'Lync Server 2013: подготовка к установке и установка анализатора соответствия рекомендациям'
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
ms.openlocfilehash: 303df28b307a2d23bdc468d1c53977030d0cf8df
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42152587"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="preparing-for-and-installing-best-practices-analyzer-in-lync-server-2013"></a><span data-ttu-id="e8c6a-102">Подготовка и установка анализатора соответствия рекомендациям в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e8c6a-102">Preparing for and installing Best Practices Analyzer in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e8c6a-103">_**Последнее изменение темы:** 2013-11-07_</span><span class="sxs-lookup"><span data-stu-id="e8c6a-103">_**Topic Last Modified:** 2013-11-07_</span></span>

<span data-ttu-id="e8c6a-104">Необходимо выполнить вход в систему как член группы администраторов, чтобы выполнить задачи, приведены в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="e8c6a-104">You must be logged on as a member of the Administrators group to perform the tasks that are described in this topic.</span></span>

<div>

## <a name="system-requirements-for-best-practices-analyzer-installation"></a><span data-ttu-id="e8c6a-105">Системные требования для установки анализатора соответствия рекомендациям</span><span class="sxs-lookup"><span data-stu-id="e8c6a-105">System Requirements for Best Practices Analyzer Installation</span></span>

<span data-ttu-id="e8c6a-106">Чтобы запустить Lync Server 2013, анализатор соответствия рекомендациям для проверки среды, на компьютере должна быть установлена версия 64 (разрядная версия) одной из следующих операционных систем:</span><span class="sxs-lookup"><span data-stu-id="e8c6a-106">To run Lync Server 2013, Best Practices Analyzer to scan your environment, the computer must be running a 64-bit edition of one of the following operating systems:</span></span>

  - <span data-ttu-id="e8c6a-107">Windows Server 2008 R2 с пакетом обновления 1 (SP1) (SP1), стандартная операционная система</span><span class="sxs-lookup"><span data-stu-id="e8c6a-107">Windows Server 2008 R2 with Service Pack 1 (SP1) Standard operating system</span></span>

  - <span data-ttu-id="e8c6a-108">Операционная система Windows Server 2008 R2 с пакетом обновления 1 (SP1)</span><span class="sxs-lookup"><span data-stu-id="e8c6a-108">Windows Server 2008 R2 with SP1 Enterprise operating system</span></span>

  - <span data-ttu-id="e8c6a-109">Операционная система Windows Server 2008 R2 с пакетом обновления 1 (SP1)</span><span class="sxs-lookup"><span data-stu-id="e8c6a-109">Windows Server 2008 R2 with SP1 Datacenter operating system</span></span>

  - <span data-ttu-id="e8c6a-110">Операционная система Windows Server 2012 Datacenter</span><span class="sxs-lookup"><span data-stu-id="e8c6a-110">Windows Server 2012 Datacenter operating system</span></span>

  - <span data-ttu-id="e8c6a-111">Windows Server 2012 Standard операционная система</span><span class="sxs-lookup"><span data-stu-id="e8c6a-111">Windows Server 2012 Standard operating system</span></span>

  - <span data-ttu-id="e8c6a-112">Операционная система Windows Server 2012 Enterprise</span><span class="sxs-lookup"><span data-stu-id="e8c6a-112">Windows Server 2012 Enterprise operating system</span></span>

  - <span data-ttu-id="e8c6a-113">Операционная система Windows Server 2012 R2 Datacenter</span><span class="sxs-lookup"><span data-stu-id="e8c6a-113">Windows Server 2012 R2 Datacenter operating system</span></span>

  - <span data-ttu-id="e8c6a-114">Windows Server 2012 R2 (стандартная операционная система)</span><span class="sxs-lookup"><span data-stu-id="e8c6a-114">Windows Server 2012 R2 Standard operating system</span></span>

  - <span data-ttu-id="e8c6a-115">Операционная система Windows Server 2012 R2 Enterprise</span><span class="sxs-lookup"><span data-stu-id="e8c6a-115">Windows Server 2012 R2 Enterprise operating system</span></span>

  - <span data-ttu-id="e8c6a-116">Операционная система Windows 8</span><span class="sxs-lookup"><span data-stu-id="e8c6a-116">Windows 8 operating system</span></span>

  - <span data-ttu-id="e8c6a-117">Операционная система Windows 7</span><span class="sxs-lookup"><span data-stu-id="e8c6a-117">Windows 7 operating system</span></span>

<span data-ttu-id="e8c6a-118">На компьютере также должны работать следующие компоненты:</span><span class="sxs-lookup"><span data-stu-id="e8c6a-118">The computer must also be running the following:</span></span>

  - <span data-ttu-id="e8c6a-119">Microsoft .NET Framework 4,5.</span><span class="sxs-lookup"><span data-stu-id="e8c6a-119">Microsoft .NET Framework 4.5.</span></span> <span data-ttu-id="e8c6a-120">Для Lync Server 2013 необходимо вручную установить 64 – разрядную версию Microsoft .NET Framework 4,5 на сервере перед установкой Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e8c6a-120">For Lync Server 2013, you must manually install the 64-bit edition of Microsoft .NET Framework 4.5 on the server prior to installing Lync Server 2013.</span></span>

  - <span data-ttu-id="e8c6a-121">Lync Server 2013, основные компоненты.</span><span class="sxs-lookup"><span data-stu-id="e8c6a-121">Lync Server 2013, Core Components.</span></span>

  - <span data-ttu-id="e8c6a-122">Пакет обратной совместимости WMI.</span><span class="sxs-lookup"><span data-stu-id="e8c6a-122">WMI Backward Compatibility Package.</span></span> <span data-ttu-id="e8c6a-123">Для получения дополнительных сведений обратитесь к разделу [Установка обратной СОВМЕСТИМОСТИ WMI](install-wmi-backward-compatibility-package.md) в документации по миграции.</span><span class="sxs-lookup"><span data-stu-id="e8c6a-123">For details, see [Install WMI Backward Compatibility package](install-wmi-backward-compatibility-package.md) in the Migration documentation.</span></span>

  - <span data-ttu-id="e8c6a-124">Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="e8c6a-124">Windows PowerShell 3.0.</span></span> <span data-ttu-id="e8c6a-125">Дополнительные сведения приведены в статье [Установка Windows PowerShell 3,0 для Lync Server 2013](lync-server-2013-installing-windows-powershell-3-0.md) в документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="e8c6a-125">For details, see [Installing Windows PowerShell 3.0 for Lync Server 2013](lync-server-2013-installing-windows-powershell-3-0.md) in the Deployment documentation.</span></span>

<span data-ttu-id="e8c6a-126">Анализатор соответствия рекомендациям можно установить на компьютерах с поддерживаемой операционной системой, не использующей Lync Server 2013, основные компоненты или пакет обратной совместимости WMI, но с помощью анализатора соответствия рекомендациям на этих компьютерах можно просматривать отчеты, а не для запуска проверок.</span><span class="sxs-lookup"><span data-stu-id="e8c6a-126">You can install Best Practices Analyzer on computers with a supported operating system that are not running Lync Server 2013, Core Components or WMI Backward Compatibility Package, but you can use Best Practices Analyzer on those computers only to view reports, not to run scans.</span></span>

</div>

<div>

## <a name="choosing-a-computer-for-installation"></a><span data-ttu-id="e8c6a-127">Выбор компьютера для установки</span><span class="sxs-lookup"><span data-stu-id="e8c6a-127">Choosing a Computer for Installation</span></span>

<span data-ttu-id="e8c6a-128">Мы рекомендуем установить Lync Server 2013, анализатор соответствия рекомендациям на компьютере, выделенном для управления Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e8c6a-128">We recommend that you install Lync Server 2013, Best Practices Analyzer on a computer that is dedicated to Lync Server 2013 management.</span></span> <span data-ttu-id="e8c6a-129">Средство можно установить на сервере, работающем под управлением Lync Server 2013 или на административном компьютере, на котором запущены средства администрирования Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e8c6a-129">You can install the tool on a server running Lync Server 2013 or an administrative computer running Lync Server 2013 administrative tools.</span></span> <span data-ttu-id="e8c6a-130">При установке средства на сервере, на котором работает Lync Server, рекомендуется использовать это средство для сканирования только этого сервера.</span><span class="sxs-lookup"><span data-stu-id="e8c6a-130">If you install the tool on a server that is running Lync Server, we recommend that you use the tool to scan only that server.</span></span>

</div>

<div>

## <a name="installing-best-practices-analyzer"></a><span data-ttu-id="e8c6a-131">Установка анализатора соответствия рекомендациям</span><span class="sxs-lookup"><span data-stu-id="e8c6a-131">Installing Best Practices Analyzer</span></span>

<span data-ttu-id="e8c6a-132">Вы можете скачать анализатор соответствия рекомендациям для Lync Server 2013 по [https://go.microsoft.com/fwlink/p/?linkId=266539](https://go.microsoft.com/fwlink/p/?linkid=266539)адресу.</span><span class="sxs-lookup"><span data-stu-id="e8c6a-132">You can download the Best Practices Analyzer for Lync Server 2013 at [https://go.microsoft.com/fwlink/p/?linkId=266539](https://go.microsoft.com/fwlink/p/?linkid=266539).</span></span>

<span data-ttu-id="e8c6a-133">Чтобы установить анализатор соответствия рекомендациям, запустите файл установщика Microsoft RtcBPA.msi на компьютере, где необходимо установить средство, затем следуйте инструкциям на экране.</span><span class="sxs-lookup"><span data-stu-id="e8c6a-133">To install Best Practices Analyzer, start the Microsoft Installer file RtcBPA.msi on the computer where you want to install the tool, and then follow the instructions on the screen.</span></span> <span data-ttu-id="e8c6a-134">Расположением по умолчанию для установки программных \<файлов являются\>\\файлы\\программ системного диска Lync\\Server 2013 BPA.</span><span class="sxs-lookup"><span data-stu-id="e8c6a-134">The default location for installing the program files is \<system drive\>\\Program Files\\Lync Server 2013\\BPA.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

