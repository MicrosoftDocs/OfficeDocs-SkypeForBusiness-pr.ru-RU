---
title: 'Lync Server 2013: требования к программному обеспечению для административных средств'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Administrative tools software requirements
ms:assetid: 2fb172c3-7b84-4e49-981c-2a17e7a00a29
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg195653(v=OCS.15)
ms:contentKeyID: 48183740
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c8756545969f90cbece7bbac628577a51015e371
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42145097"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="administrative-tools-software-requirements-in-lync-server-2013"></a><span data-ttu-id="0691b-102">Требования к программному обеспечению для средств администрирования в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0691b-102">Administrative tools software requirements in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0691b-103">_**Последнее изменение темы:** 2013-11-07_</span><span class="sxs-lookup"><span data-stu-id="0691b-103">_**Topic Last Modified:** 2013-11-07_</span></span>

<span data-ttu-id="0691b-104">В этом разделе описывается программное обеспечение, необходимое для установки и использования средств администрирования Lync Server 2013 в дополнение к требованиям операционной системы.</span><span class="sxs-lookup"><span data-stu-id="0691b-104">This topic describes the software required to install and use Lync Server 2013 administrative tools in addition to the operating system requirements.</span></span>

<div>

## <a name="microsoft-net-framework-45"></a><span data-ttu-id="0691b-105">Microsoft .NET Framework 4.5</span><span class="sxs-lookup"><span data-stu-id="0691b-105">Microsoft .NET Framework 4.5</span></span>

<span data-ttu-id="0691b-106">64-разрядный выпуск Microsoft .NET Framework 4,5 необходим для Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="0691b-106">The 64-bit edition of Microsoft .NET Framework 4.5 is required for Lync Server 2013.</span></span>

</div>

<div>

## <a name="windows-powershell-30"></a><span data-ttu-id="0691b-107">Windows PowerShell 3.0</span><span class="sxs-lookup"><span data-stu-id="0691b-107">Windows PowerShell 3.0</span></span>

<span data-ttu-id="0691b-108">Windows PowerShell 3,0 необходима для запуска любого компонента Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="0691b-108">Windows PowerShell 3.0 is required for running any component of Microsoft Lync Server 2013.</span></span> <span data-ttu-id="0691b-109">Дополнительные сведения см. в статье [Установка Windows PowerShell 3,0 для Lync Server 2013](lync-server-2013-installing-windows-powershell-3-0.md).</span><span class="sxs-lookup"><span data-stu-id="0691b-109">For more information, see [Installing Windows PowerShell 3.0 for Lync Server 2013](lync-server-2013-installing-windows-powershell-3-0.md).</span></span>

</div>

<div>

## <a name="windows-installer-version-45"></a><span data-ttu-id="0691b-110">Установщик Windows версии 4.5</span><span class="sxs-lookup"><span data-stu-id="0691b-110">Windows Installer Version 4.5</span></span>

<span data-ttu-id="0691b-111">Lync Server 2013 использует технологию установщика Windows для установки, удаления и обслуживания различных ролей сервера.</span><span class="sxs-lookup"><span data-stu-id="0691b-111">Lync Server 2013 uses Windows Installer technology to install, uninstall, and maintain various server roles.</span></span> <span data-ttu-id="0691b-112">Установщик Windows версии 4.5 доступен в виде распространяемого компонента для операционной системы Windows Server.</span><span class="sxs-lookup"><span data-stu-id="0691b-112">Windows Installer version 4.5 is available as a redistributable component for the Windows Server operating system.</span></span> <span data-ttu-id="0691b-113">Установщик Windows 4,5 поставляется с Windows Server 2012 R2, Windows Server 2012 и Windows Server 2008 R2, что означает, что вам не нужно загружать утилиту для всех компьютеров, на которых работает Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="0691b-113">Windows Installer 4.5 ships with Windows Server 2012 R2, Windows Server 2012, and Windows Server 2008 R2 meaning that you do not need to download the utility for any computer that is running Lync Server 2013.</span></span> <span data-ttu-id="0691b-114">(Lync Server 2013 можно установить только на компьютерах под управлением Windows Server 2012 R2, Windows Server 2012 или Windows Server 2008 R2).</span><span class="sxs-lookup"><span data-stu-id="0691b-114">(Lync Server 2013 can only be installed on computers running Windows Server 2012 R2, Windows Server 2012 or Windows Server 2008 R2.)</span></span>

<span data-ttu-id="0691b-115">Тем не менее, если вы хотите установить консоль управления Lync Server или построитель топологий Lync Server на рабочей станции администратора, вам может потребоваться Скачать установщик Windows 4,5.</span><span class="sxs-lookup"><span data-stu-id="0691b-115">However, if you want to install Lync Server Management Shell or Lync Server Topology Builder on an administrator workstation you might need to download Windows Installer 4.5.</span></span> <span data-ttu-id="0691b-116">Эта служебная программа поставляется с Windows 7 и Windows 2008 R2, но не с предыдущими версиями операционной системы Windows.</span><span class="sxs-lookup"><span data-stu-id="0691b-116">That utility ships with Windows 7 and Windows 2008 R2 but not with any previous versions of the Windows operating system.</span></span> <span data-ttu-id="0691b-117">Вы можете скачать установщик Windows 4,5 из центра загрузки Майкрософт по адресу <https://go.microsoft.com/fwlink/p/?linkid=197395>.</span><span class="sxs-lookup"><span data-stu-id="0691b-117">You can download Windows Installer 4.5 from the Microsoft Download Center at <https://go.microsoft.com/fwlink/p/?linkid=197395>.</span></span>

</div>

<div>

## <a name="microsoft-silverlight-5-browser-plug-in"></a><span data-ttu-id="0691b-118">Подключаемый модуль Microsoft Silverlight 5 для браузера</span><span class="sxs-lookup"><span data-stu-id="0691b-118">Microsoft Silverlight 5 browser plug-in</span></span>

<span data-ttu-id="0691b-119">Панель управления Lync Server 2013 — это веб-средство, которое требует установки последней версии подключаемого модуля браузера Microsoft Silverlight 5.</span><span class="sxs-lookup"><span data-stu-id="0691b-119">Lync Server 2013 Control Panel is a web-based tool and requires that you install the latest version of Microsoft Silverlight 5 browser plug-in.</span></span> <span data-ttu-id="0691b-120">Если вы запускаете панель управления Lync Server 2013, если это программное обеспечение не установлено или если установлена более ранняя версия, откроется панель управления Lync Server 2013, предлагающая установить требуемую версию.</span><span class="sxs-lookup"><span data-stu-id="0691b-120">When you start Lync Server 2013 Control Panel, if this software is not installed or if an earlier version is installed, Lync Server 2013 Control Panel prompts you to install the required version.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="0691b-121">См. также</span><span class="sxs-lookup"><span data-stu-id="0691b-121">See Also</span></span>


[<span data-ttu-id="0691b-122">Поддержка серверов и средств операционной системы в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0691b-122">Server and tools operating system support in Lync Server 2013</span></span>](lync-server-2013-server-and-tools-operating-system-support.md)  


[<span data-ttu-id="0691b-123">Требования к инфраструктуре средств администрирования в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0691b-123">Administrative tools infrastructure requirements in Lync Server 2013</span></span>](lync-server-2013-administrative-tools-infrastructure-requirements.md)  
[<span data-ttu-id="0691b-124">Права и разрешения администратора, необходимые для установки и администрирования Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0691b-124">Administrator rights and permissions required for setup and administration of Lync Server 2013</span></span>](lync-server-2013-administrator-rights-and-permissions-required-for-setup-and-administration.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

