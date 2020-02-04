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
ms.openlocfilehash: 8f5992b45d8930bac880f66422d10ddbd4b94f18
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41747419"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="preparing-for-and-installing-best-practices-analyzer-in-lync-server-2013"></a><span data-ttu-id="f4d7d-102">Подготовка и установка анализатора соответствия рекомендациям в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f4d7d-102">Preparing for and installing Best Practices Analyzer in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f4d7d-103">_**Тема последнего изменения:** 2013-11-07_</span><span class="sxs-lookup"><span data-stu-id="f4d7d-103">_**Topic Last Modified:** 2013-11-07_</span></span>

<span data-ttu-id="f4d7d-104">Для выполнения задач, описанных в этом разделе, необходимо войти в систему в качестве члена группы администраторов.</span><span class="sxs-lookup"><span data-stu-id="f4d7d-104">You must be logged on as a member of the Administrators group to perform the tasks that are described in this topic.</span></span>

<div>

## <a name="system-requirements-for-best-practices-analyzer-installation"></a><span data-ttu-id="f4d7d-105">Требования к системе для установки анализатора соответствия рекомендациям</span><span class="sxs-lookup"><span data-stu-id="f4d7d-105">System Requirements for Best Practices Analyzer Installation</span></span>

<span data-ttu-id="f4d7d-106">Для запуска Lync Server 2013, анализатора соответствия рекомендациям для проверки среды на компьютере должна быть установлена версия 64-bit Edition одной из указанных ниже операционных систем.</span><span class="sxs-lookup"><span data-stu-id="f4d7d-106">To run Lync Server 2013, Best Practices Analyzer to scan your environment, the computer must be running a 64-bit edition of one of the following operating systems:</span></span>

  - <span data-ttu-id="f4d7d-107">Стандартная операционная система Windows Server 2008 R2 с пакетом обновления 1 (SP1)</span><span class="sxs-lookup"><span data-stu-id="f4d7d-107">Windows Server 2008 R2 with Service Pack 1 (SP1) Standard operating system</span></span>

  - <span data-ttu-id="f4d7d-108">Операционная система Windows Server 2008 R2 с пакетом обновления 1 (SP1)</span><span class="sxs-lookup"><span data-stu-id="f4d7d-108">Windows Server 2008 R2 with SP1 Enterprise operating system</span></span>

  - <span data-ttu-id="f4d7d-109">Windows Server 2008 R2 с пакетом обновления 1 (SP1) для операционной системы Datacenter</span><span class="sxs-lookup"><span data-stu-id="f4d7d-109">Windows Server 2008 R2 with SP1 Datacenter operating system</span></span>

  - <span data-ttu-id="f4d7d-110">Операционная система Windows Server 2012 Datacenter</span><span class="sxs-lookup"><span data-stu-id="f4d7d-110">Windows Server 2012 Datacenter operating system</span></span>

  - <span data-ttu-id="f4d7d-111">Операционная система Windows Server 2012 Standard</span><span class="sxs-lookup"><span data-stu-id="f4d7d-111">Windows Server 2012 Standard operating system</span></span>

  - <span data-ttu-id="f4d7d-112">Операционная система Windows Server 2012 Enterprise</span><span class="sxs-lookup"><span data-stu-id="f4d7d-112">Windows Server 2012 Enterprise operating system</span></span>

  - <span data-ttu-id="f4d7d-113">Операционная система Windows Server 2012 R2 Datacenter</span><span class="sxs-lookup"><span data-stu-id="f4d7d-113">Windows Server 2012 R2 Datacenter operating system</span></span>

  - <span data-ttu-id="f4d7d-114">Операционная система Windows Server 2012 R2 Standard</span><span class="sxs-lookup"><span data-stu-id="f4d7d-114">Windows Server 2012 R2 Standard operating system</span></span>

  - <span data-ttu-id="f4d7d-115">Операционная система Windows Server 2012 R2 Enterprise</span><span class="sxs-lookup"><span data-stu-id="f4d7d-115">Windows Server 2012 R2 Enterprise operating system</span></span>

  - <span data-ttu-id="f4d7d-116">Операционная система Windows 8</span><span class="sxs-lookup"><span data-stu-id="f4d7d-116">Windows 8 operating system</span></span>

  - <span data-ttu-id="f4d7d-117">Операционная система Windows 7</span><span class="sxs-lookup"><span data-stu-id="f4d7d-117">Windows 7 operating system</span></span>

<span data-ttu-id="f4d7d-118">На компьютере должны быть также запущены следующие возможности:</span><span class="sxs-lookup"><span data-stu-id="f4d7d-118">The computer must also be running the following:</span></span>

  - <span data-ttu-id="f4d7d-119">Microsoft .NET Framework 4,5.</span><span class="sxs-lookup"><span data-stu-id="f4d7d-119">Microsoft .NET Framework 4.5.</span></span> <span data-ttu-id="f4d7d-120">Для Lync Server 2013 необходимо вручную установить 64-разрядную версию Microsoft .NET Framework 4,5 на сервере перед установкой Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f4d7d-120">For Lync Server 2013, you must manually install the 64-bit edition of Microsoft .NET Framework 4.5 on the server prior to installing Lync Server 2013.</span></span>

  - <span data-ttu-id="f4d7d-121">Lync Server 2013, основные компоненты.</span><span class="sxs-lookup"><span data-stu-id="f4d7d-121">Lync Server 2013, Core Components.</span></span>

  - <span data-ttu-id="f4d7d-122">Пакет обратной совместимости WMI.</span><span class="sxs-lookup"><span data-stu-id="f4d7d-122">WMI Backward Compatibility Package.</span></span> <span data-ttu-id="f4d7d-123">Дополнительные сведения можно найти в разделе [Установка пакета обратной СОВМЕСТИМОСТИ WMI](install-wmi-backward-compatibility-package.md) в документации по миграции.</span><span class="sxs-lookup"><span data-stu-id="f4d7d-123">For details, see [Install WMI Backward Compatibility package](install-wmi-backward-compatibility-package.md) in the Migration documentation.</span></span>

  - <span data-ttu-id="f4d7d-124">Windows PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="f4d7d-124">Windows PowerShell 3.0.</span></span> <span data-ttu-id="f4d7d-125">Дополнительные сведения можно найти в разделе [Установка Windows PowerShell 3,0 для Lync Server 2013](lync-server-2013-installing-windows-powershell-3-0.md) в документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="f4d7d-125">For details, see [Installing Windows PowerShell 3.0 for Lync Server 2013](lync-server-2013-installing-windows-powershell-3-0.md) in the Deployment documentation.</span></span>

<span data-ttu-id="f4d7d-126">Вы можете установить анализатор соответствия рекомендациям на компьютерах с поддерживаемой операционной системой, не использующей Lync Server 2013, основные компоненты или пакет обратной совместимости WMI, но вы можете использовать анализатор соответствия рекомендациям только для просмотра отчетов, а не для запуска сканирования.</span><span class="sxs-lookup"><span data-stu-id="f4d7d-126">You can install Best Practices Analyzer on computers with a supported operating system that are not running Lync Server 2013, Core Components or WMI Backward Compatibility Package, but you can use Best Practices Analyzer on those computers only to view reports, not to run scans.</span></span>

</div>

<div>

## <a name="choosing-a-computer-for-installation"></a><span data-ttu-id="f4d7d-127">Выбор компьютера для установки</span><span class="sxs-lookup"><span data-stu-id="f4d7d-127">Choosing a Computer for Installation</span></span>

<span data-ttu-id="f4d7d-128">Мы рекомендуем установить Lync Server 2013, анализатор соответствия рекомендациям на компьютере, специально предназначенном для управления Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f4d7d-128">We recommend that you install Lync Server 2013, Best Practices Analyzer on a computer that is dedicated to Lync Server 2013 management.</span></span> <span data-ttu-id="f4d7d-129">Вы можете установить этот инструмент на сервер, на котором работает Lync Server 2013 или административный компьютер, на котором запущены средства администрирования Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f4d7d-129">You can install the tool on a server running Lync Server 2013 or an administrative computer running Lync Server 2013 administrative tools.</span></span> <span data-ttu-id="f4d7d-130">Если вы установили средство на сервер, на котором работает Lync Server, мы рекомендуем использовать это средство для проверки только этого сервера.</span><span class="sxs-lookup"><span data-stu-id="f4d7d-130">If you install the tool on a server that is running Lync Server, we recommend that you use the tool to scan only that server.</span></span>

</div>

<div>

## <a name="installing-best-practices-analyzer"></a><span data-ttu-id="f4d7d-131">Установка анализатора соответствия рекомендациям</span><span class="sxs-lookup"><span data-stu-id="f4d7d-131">Installing Best Practices Analyzer</span></span>

<span data-ttu-id="f4d7d-132">Вы можете скачать анализатор соответствия рекомендациям для Lync Server 2013 по [http://go.microsoft.com/fwlink/p/?linkId=266539](http://go.microsoft.com/fwlink/p/?linkid=266539)адресу.</span><span class="sxs-lookup"><span data-stu-id="f4d7d-132">You can download the Best Practices Analyzer for Lync Server 2013 at [http://go.microsoft.com/fwlink/p/?linkId=266539](http://go.microsoft.com/fwlink/p/?linkid=266539).</span></span>

<span data-ttu-id="f4d7d-133">Чтобы установить анализатор соответствия рекомендациям, запустите файл установщика Microsoft Рткбпа. msi на компьютере, на котором вы хотите установить средство, и следуйте инструкциям на экране.</span><span class="sxs-lookup"><span data-stu-id="f4d7d-133">To install Best Practices Analyzer, start the Microsoft Installer file RtcBPA.msi on the computer where you want to install the tool, and then follow the instructions on the screen.</span></span> <span data-ttu-id="f4d7d-134">По умолчанию для установки файлов программы устанавливаются \<файлы программы\>\\системного диска\\Lync Server 2013\\BPA.</span><span class="sxs-lookup"><span data-stu-id="f4d7d-134">The default location for installing the program files is \<system drive\>\\Program Files\\Lync Server 2013\\BPA.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

