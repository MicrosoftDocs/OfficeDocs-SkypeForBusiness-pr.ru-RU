---
title: 'Lync Server 2013: системные требования для серверов, на которых работает Lync Server 2013'
description: 'Lync Server 2013: системные требования для серверов, на которых работает Lync Server 2013.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: System requirements for servers running Lync Server 2013
ms:assetid: 781d487d-5958-416a-becb-904d9af3cc0a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398588(v=OCS.15)
ms:contentKeyID: 48184564
ms.date: 07/24/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7b85940294e35a953d4ffb9c07bfdaba79141485
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48562655"
---
# <a name="system-requirements-for-servers-running-lync-server-2013"></a><span data-ttu-id="442fc-103">Системные требования для серверов, на которых работает Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="442fc-103">System requirements for servers running Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="442fc-104">_**Последнее изменение темы:** 2014-07-24_</span><span class="sxs-lookup"><span data-stu-id="442fc-104">_**Topic Last Modified:** 2014-07-24_</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="442fc-105">Сведения о требованиях к оборудованию приведены в статье <A href="lync-server-2013-server-hardware-platforms.md">Server Hardware Platforms for Lync server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="442fc-105">For details about hardware requirements, see <A href="lync-server-2013-server-hardware-platforms.md">Server hardware platforms for Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="442fc-106">К серверам Standard Edition и Enterprise Edition применяются одинаковые требования к программному обеспечению.</span><span class="sxs-lookup"><span data-stu-id="442fc-106">Standard Edition and Enterprise Edition servers share the same software requirements.</span></span>

<span data-ttu-id="442fc-107">Серверы, работающие под управлением Lync Server 2013, Enterprise Edition, предназначены для крупных организаций в качестве основного организационного развертывания.</span><span class="sxs-lookup"><span data-stu-id="442fc-107">Servers running Lync Server 2013, Enterprise Edition are intended for large organizations as the main organizational deployment.</span></span> <span data-ttu-id="442fc-108">Сервер Enterprise Edition предназначен для масштабирования до приблизительно 80000 пользователей на пул.</span><span class="sxs-lookup"><span data-stu-id="442fc-108">Enterprise Edition server is designed to scale to approximately 80,000 homed users per pool.</span></span> <span data-ttu-id="442fc-109">Серверы, на которых работает Lync Server 2013, Standard Edition, предназначены для небольших организаций и удаленных расположений из основного развертывания Организации.</span><span class="sxs-lookup"><span data-stu-id="442fc-109">Servers running Lync Server 2013, Standard Edition are intended for smaller organizations and remote locations from the main organization deployment.</span></span> <span data-ttu-id="442fc-110">Одна из двух серверов Standard Edition может поддерживать до 5 000 пользователей..</span><span class="sxs-lookup"><span data-stu-id="442fc-110">One pair of Standard Edition servers can support up to 5,000 users..</span></span> <span data-ttu-id="442fc-111">Подробные сведения о различиях между серверами Standard Edition и серверами Enterprise Edition приведены в статье [Обзор развертывания для Lync Server 2013](lync-server-2013-deployment-overview.md).</span><span class="sxs-lookup"><span data-stu-id="442fc-111">For details on the differences between Standard Edition servers and Enterprise Edition servers, see [Deployment overview for Lync Server 2013](lync-server-2013-deployment-overview.md).</span></span>

<div>

## <a name="operating-system-installation"></a><span data-ttu-id="442fc-112">Установка операционной системы</span><span class="sxs-lookup"><span data-stu-id="442fc-112">Operating System Installation</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="442fc-113">Lync Server 2013 доступен только в 64-разрядном выпуске, для которого требуется 64-разрядное оборудование, а также 64-разрядный выпуск операционной системы Windows Server.</span><span class="sxs-lookup"><span data-stu-id="442fc-113">Lync Server 2013 is available only in a 64-bit edition, which requires 64-bit hardware and a 64-bit edition of the Windows Server operating system.</span></span> <span data-ttu-id="442fc-114">32-разрядный выпуск Lync Server 2013 недоступен в этой версии.</span><span class="sxs-lookup"><span data-stu-id="442fc-114">A 32-bit edition of Lync Server 2013 is not available with this release.</span></span>



</div>

<span data-ttu-id="442fc-115">Серверы Standard Edition и Enterprise Edition могут использовать любой из следующих операционных систем:</span><span class="sxs-lookup"><span data-stu-id="442fc-115">Standard Edition and Enterprise Edition server can use any of the following:</span></span>

  - <span data-ttu-id="442fc-116">Windows Server 2008 R2 SP1 или последний пакет обновления.</span><span class="sxs-lookup"><span data-stu-id="442fc-116">Windows Server 2008 R2 SP1 or latest service pack</span></span>

  - <span data-ttu-id="442fc-117">Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="442fc-117">Windows Server 2012</span></span>

  - <span data-ttu-id="442fc-118">Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="442fc-118">Windows Server 2012 R2</span></span>

<span data-ttu-id="442fc-119">Установите операционную систему на сервер Standard Edition или сервер переднего плана Enterprise Edition.</span><span class="sxs-lookup"><span data-stu-id="442fc-119">Install the operating system software on the Standard Edition Server or Enterprise Edition Front End Server.</span></span> <span data-ttu-id="442fc-120">Установите все обновления, чтобы обновить операционную систему до последней версии в соответствии со стандартами организации.</span><span class="sxs-lookup"><span data-stu-id="442fc-120">Apply all updates in order to bring the operating system up to the latest update and required update level consistent with your organization’s standards.</span></span> <span data-ttu-id="442fc-121">Дополнительные сведения о рабочих требованиях приведены в статье поддержка [серверов и средств операционной системы в Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md) в документации по поддержке.</span><span class="sxs-lookup"><span data-stu-id="442fc-121">For more details about the operating requirements, see [Server and tools operating system support in Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md) in the Supportability documentation.</span></span>

> [!NOTE] 
> <span data-ttu-id="442fc-122">Обновление на месте операционной системы не поддерживается в Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="442fc-122">In-place upgrade of the operating system is not supported with Lync Server 2013.</span></span>  <span data-ttu-id="442fc-123">Необходимо развернуть отдельный пул и перенести пользователей в новый пул с другой операционной системой.</span><span class="sxs-lookup"><span data-stu-id="442fc-123">You must deploy a separate pool and migrate users to the new pool with a different operating system.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="442fc-124">Для работы Lync Server 2013 в Windows Server 2012 R2 может потребоваться изменить значение раздела реестра в Windows Server.</span><span class="sxs-lookup"><span data-stu-id="442fc-124">For Lync Server 2013 to work on Windows Server 2012 R2, you may need to change the value of a registry key in Windows Server.</span></span> <span data-ttu-id="442fc-125">Это изменение может потребоваться для правильной работы сертификатов, а также для регистрации клиентов с помощью устройств для обеспечения связи в филиалах.</span><span class="sxs-lookup"><span data-stu-id="442fc-125">This change may be necessary for certificates to work correctly, and for clients to register with Survivable Branch Appliances.</span></span> <span data-ttu-id="442fc-126">Для получения дополнительных сведений см <A class=uri href="https://support.microsoft.com/kb/2901554">https://support.microsoft.com/kb/2901554</A> .</span><span class="sxs-lookup"><span data-stu-id="442fc-126">For more information, see <A class=uri href="https://support.microsoft.com/kb/2901554">https://support.microsoft.com/kb/2901554</A>.</span></span>



</div>

<div>

## <a name="additional-software-for-lync-server-2013"></a><span data-ttu-id="442fc-127">Дополнительное программное обеспечение для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="442fc-127">Additional Software for Lync Server 2013</span></span>

<span data-ttu-id="442fc-128">В дополнение к обновлениям, необходимым для операционной системы, Lync Server 2013 требует, чтобы работали роли операционной системы, компоненты и программное обеспечение.</span><span class="sxs-lookup"><span data-stu-id="442fc-128">In addition to the updates required for the operating system, Lync Server 2013 requires operating system roles, features, and software to operate.</span></span> <span data-ttu-id="442fc-129">Дополнительные сведения о дополнительном программном обеспечении, которое необходимо установить перед публикацией топологии и установкой Lync Server 2013, можно найти в разделе [Дополнительные требования к программному обеспечению для Lync server 2013](lync-server-2013-additional-software-requirements.md) в документации по планированию.</span><span class="sxs-lookup"><span data-stu-id="442fc-129">For details about the additional software that must be installed prior to publishing your topology and installing Lync Server 2013, see [Additional software requirements for Lync Server 2013](lync-server-2013-additional-software-requirements.md) in the Planning documentation.</span></span>

</div>

</div>

<div>

## <a name="additional-software-necessary-for-all-server-roles"></a><span data-ttu-id="442fc-130">Необходимое программное обеспечение для всех ролей сервера</span><span class="sxs-lookup"><span data-stu-id="442fc-130">Additional Software Necessary for All Server Roles</span></span>

<span data-ttu-id="442fc-131">Для всех ролей сервера также необходимо убедиться, что установлены интерфейс командной строки Windows PowerShell 3,0 и Microsoft .NET Framework 4,5.</span><span class="sxs-lookup"><span data-stu-id="442fc-131">On all server roles, you must also make sure that Windows PowerShell command-line interface 3.0 and Microsoft .NET Framework 4.5 are installed.</span></span>

<span data-ttu-id="442fc-132">Кроме того, интерфейс командной строки Windows PowerShell 3,0 и Microsoft .NET Framework 4,5 необходимы на компьютере, на котором будут выполняться средства администрирования Lync Server.</span><span class="sxs-lookup"><span data-stu-id="442fc-132">Additionally, Windows PowerShell command-line interface 3.0 and Microsoft .NET Framework 4.5 are required on any computer where you will run the Lync Server administrative tools.</span></span>

<div>

## <a name="windows-powershell-30"></a><span data-ttu-id="442fc-133">Windows PowerShell 3.0</span><span class="sxs-lookup"><span data-stu-id="442fc-133">Windows PowerShell 3.0</span></span>

<span data-ttu-id="442fc-134">Lync Server 2013 требует установки Windows PowerShell 3,0 на каждом компьютере, который входит в топологию Lync Server.</span><span class="sxs-lookup"><span data-stu-id="442fc-134">Lync Server 2013 requires you to install Windows PowerShell 3.0 on each computer that will take part in your Lync Server topology.</span></span> <span data-ttu-id="442fc-135">Более подробную информацию об установке Windows PowerShell 3,0 можно узнать в статье [Установка Windows powershell 3,0 для Lync Server 2013](lync-server-2013-installing-windows-powershell-3-0.md).</span><span class="sxs-lookup"><span data-stu-id="442fc-135">For details about installing Windows PowerShell 3.0, see [Installing Windows PowerShell 3.0 for Lync Server 2013](lync-server-2013-installing-windows-powershell-3-0.md).</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="442fc-136">В Windows Server &nbsp; 2008 &nbsp; R2 с пакетом обновления 1 (SP1) интерфейс командной строки Windows PowerShell 3,0 не может быть установлен перед установкой Microsoft .net Framework 4,5.</span><span class="sxs-lookup"><span data-stu-id="442fc-136">On Windows Server&nbsp;2008&nbsp;R2 with SP1, Windows PowerShell command-line interface 3.0 cannot be installed before installing Microsoft .NET Framework 4.5.</span></span>



</div>

</div>

<div>

## <a name="microsoft-net-framework-45"></a><span data-ttu-id="442fc-137">Microsoft .NET Framework 4.5</span><span class="sxs-lookup"><span data-stu-id="442fc-137">Microsoft .NET Framework 4.5</span></span>

<span data-ttu-id="442fc-138">При установке Microsoft .NET Framework 4,5 на серверах, на которых будет выполняться Lync Server 2013 в Windows Server 2012 или Windows Server 2012 R2, необходимо выполнить одно из дополнительных действий.</span><span class="sxs-lookup"><span data-stu-id="442fc-138">When you install Microsoft .NET Framework 4.5 on servers that will run Lync Server 2013 on Windows Server 2012 or Windows Server 2012 R2, you must perform one additional step.</span></span> <span data-ttu-id="442fc-139">После установки пакета .NET Framework 4.5 используйте диспетчер сервера для установки службы HTTP-активации.</span><span class="sxs-lookup"><span data-stu-id="442fc-139">After .NET Framework 4.5 is installed, use Server Manager to install HTTP Activation.</span></span>

<span data-ttu-id="442fc-140">**Установка HTTP-активации .NET 4,5 в Windows Server 2012 или Windows Server 2012 R2**</span><span class="sxs-lookup"><span data-stu-id="442fc-140">**To Install .NET 4.5 HTTP Activation on Windows Server 2012 or Windows Server 2012 R2**</span></span>

1.  <span data-ttu-id="442fc-141">В меню **Пуск** последовательно выберите пункты **Программы**, **Администрирование**, **Диспетчер сервера**.</span><span class="sxs-lookup"><span data-stu-id="442fc-141">From the **Start** menu, click **Programs**, then click **Administrative Tools**, then click **Server Manager**.</span></span>

2.  <span data-ttu-id="442fc-142">В диспетчере сервера в области **Сводка компонентов** выберите **Добавить компоненты**.</span><span class="sxs-lookup"><span data-stu-id="442fc-142">In Server Manager, under **Features Summary**, choose **Add Features**.</span></span>

3.  <span data-ttu-id="442fc-143">Разверните **.NET Framework 4.5**.</span><span class="sxs-lookup"><span data-stu-id="442fc-143">Expand **.NET Framework 4.5**.</span></span>

4.  <span data-ttu-id="442fc-p109">Выберите пункт **WCF-активация**, если он еще не выбран. Затем выберите **HTTP-активация**.</span><span class="sxs-lookup"><span data-stu-id="442fc-p109">Select **WCF Activation** if it isn’t already selected. Then select **HTTP Activation**.</span></span>

5.  <span data-ttu-id="442fc-146">Нажмите кнопку **Далее** и следуйте инструкциям для завершения установки.</span><span class="sxs-lookup"><span data-stu-id="442fc-146">Click **Next** and follow the prompts to finish the installation.</span></span>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

