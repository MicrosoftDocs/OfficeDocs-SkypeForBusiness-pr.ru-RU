---
title: 'Lync Server 2013: системные требования для серверов, на которых работает Lync Server 2013'
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
ms.openlocfilehash: c6566202dbbfa112f884ac1bb8380d1d554ba994
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41731609"
---
# <a name="system-requirements-for-servers-running-lync-server-2013"></a><span data-ttu-id="587d0-102">Системные требования для серверов, на которых работает Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="587d0-102">System requirements for servers running Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="587d0-103">_**Тема последнего изменения:** 2014-07-24_</span><span class="sxs-lookup"><span data-stu-id="587d0-103">_**Topic Last Modified:** 2014-07-24_</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="587d0-104">Сведения о требованиях к оборудованию можно найти в разделе <A href="lync-server-2013-server-hardware-platforms.md">аппаратные платформы сервера для Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="587d0-104">For details about hardware requirements, see <A href="lync-server-2013-server-hardware-platforms.md">Server hardware platforms for Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="587d0-105">Общие требования к программному обеспечению для серверов Standard Edition и Enterprise Edition.</span><span class="sxs-lookup"><span data-stu-id="587d0-105">Standard Edition and Enterprise Edition servers share the same software requirements.</span></span>

<span data-ttu-id="587d0-106">Серверы Lync Server 2013, Enterprise Edition предназначены для крупных организаций в качестве основных организационных развертываний.</span><span class="sxs-lookup"><span data-stu-id="587d0-106">Servers running Lync Server 2013, Enterprise Edition are intended for large organizations as the main organizational deployment.</span></span> <span data-ttu-id="587d0-107">Корпоративная версия Enterprise Edition разработана таким образом, чтобы она выработала примерно 80 000 на одном пуле.</span><span class="sxs-lookup"><span data-stu-id="587d0-107">Enterprise Edition server is designed to scale to approximately 80,000 homed users per pool.</span></span> <span data-ttu-id="587d0-108">Серверы Lync Server 2013, Standard Edition предназначены для небольших организаций и удаленных местоположений из основного развертывания Организации.</span><span class="sxs-lookup"><span data-stu-id="587d0-108">Servers running Lync Server 2013, Standard Edition are intended for smaller organizations and remote locations from the main organization deployment.</span></span> <span data-ttu-id="587d0-109">Одна пара серверов стандартных выпусков может поддерживать до 5 000 пользователей..</span><span class="sxs-lookup"><span data-stu-id="587d0-109">One pair of Standard Edition servers can support up to 5,000 users..</span></span> <span data-ttu-id="587d0-110">Подробнее о различиях между серверами Standard Edition и корпоративными выпусками можно найти в статье [Обзор развертывания для Lync Server 2013](lync-server-2013-deployment-overview.md).</span><span class="sxs-lookup"><span data-stu-id="587d0-110">For details on the differences between Standard Edition servers and Enterprise Edition servers, see [Deployment overview for Lync Server 2013](lync-server-2013-deployment-overview.md).</span></span>

<div>

## <a name="operating-system-installation"></a><span data-ttu-id="587d0-111">Установка операционной системы</span><span class="sxs-lookup"><span data-stu-id="587d0-111">Operating System Installation</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="587d0-112">Lync Server 2013 доступен только в 64-разрядном выпуске, для которого требуется 64-разрядное оборудование и более 64-разрядный выпуск операционной системы Windows Server.</span><span class="sxs-lookup"><span data-stu-id="587d0-112">Lync Server 2013 is available only in a 64-bit edition, which requires 64-bit hardware and a 64-bit edition of the Windows Server operating system.</span></span> <span data-ttu-id="587d0-113">В этом выпуске недоступен 32-разрядный выпуск Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="587d0-113">A 32-bit edition of Lync Server 2013 is not available with this release.</span></span>



</div>

<span data-ttu-id="587d0-114">Сервер Standard Edition и Enterprise Edition могут использовать любые из указанных ниже вариантов.</span><span class="sxs-lookup"><span data-stu-id="587d0-114">Standard Edition and Enterprise Edition server can use any of the following:</span></span>

  - <span data-ttu-id="587d0-115">Windows Server 2008 R2 с пакетом обновления 1 (SP1) или более поздней версии</span><span class="sxs-lookup"><span data-stu-id="587d0-115">Windows Server 2008 R2 SP1 or latest service pack</span></span>

  - <span data-ttu-id="587d0-116">Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="587d0-116">Windows Server 2012</span></span>

  - <span data-ttu-id="587d0-117">Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="587d0-117">Windows Server 2012 R2</span></span>

<span data-ttu-id="587d0-118">Установка программного обеспечения операционной системы на стандартном сервере выпуска Standard Edition или корпоративном выпуске.</span><span class="sxs-lookup"><span data-stu-id="587d0-118">Install the operating system software on the Standard Edition Server or Enterprise Edition Front End Server.</span></span> <span data-ttu-id="587d0-119">Примените все обновления, чтобы обновить операционную систему до последнего обновления и требуемый уровень обновления в соответствии со стандартами Организации.</span><span class="sxs-lookup"><span data-stu-id="587d0-119">Apply all updates in order to bring the operating system up to the latest update and required update level consistent with your organization’s standards.</span></span> <span data-ttu-id="587d0-120">Дополнительные сведения о требованиях, предъявляемых к операционной системе, можно найти в документации поддержка [серверов и средств операционной системы в Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md) .</span><span class="sxs-lookup"><span data-stu-id="587d0-120">For more details about the operating requirements, see [Server and tools operating system support in Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md) in the Supportability documentation.</span></span>

> [!NOTE] <span data-ttu-id="587d0-121">Обновление операционной системы на месте для Lync Server 2013 не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="587d0-121">In-place upgrade of the operating system is not supported with Lync Server 2013.</span></span>  <span data-ttu-id="587d0-122">Необходимо развернуть отдельный пул и перенести пользователей в новый пул с другой операционной системой.</span><span class="sxs-lookup"><span data-stu-id="587d0-122">You must deploy a separate pool and migrate users to the new pool with a different operating system.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="587d0-123">Для Lync Server 2013 для работы с Windows Server 2012 R2 может потребоваться изменить значение раздела реестра в Windows Server.</span><span class="sxs-lookup"><span data-stu-id="587d0-123">For Lync Server 2013 to work on Windows Server 2012 R2, you may need to change the value of a registry key in Windows Server.</span></span> <span data-ttu-id="587d0-124">Это изменение может потребоваться для правильной работы сертификатов и для того, чтобы клиенты могли регистрироваться с бесперебойно работающими управляющими филиалами.</span><span class="sxs-lookup"><span data-stu-id="587d0-124">This change may be necessary for certificates to work correctly, and for clients to register with Survivable Branch Appliances.</span></span> <span data-ttu-id="587d0-125">Дополнительные сведения см. в статье <A class=uri href="https://support.microsoft.com/kb/2901554">https://support.microsoft.com/kb/2901554</A>.</span><span class="sxs-lookup"><span data-stu-id="587d0-125">For more information, see <A class=uri href="https://support.microsoft.com/kb/2901554">https://support.microsoft.com/kb/2901554</A>.</span></span>



</div>

<div>

## <a name="additional-software-for-lync-server-2013"></a><span data-ttu-id="587d0-126">Дополнительное программное обеспечение для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="587d0-126">Additional Software for Lync Server 2013</span></span>

<span data-ttu-id="587d0-127">В дополнение к обновлениям, которые необходимы для операционной системы, Lync Server 2013 требует наличия ролей операционной системы, функций и программного обеспечения для работы.</span><span class="sxs-lookup"><span data-stu-id="587d0-127">In addition to the updates required for the operating system, Lync Server 2013 requires operating system roles, features, and software to operate.</span></span> <span data-ttu-id="587d0-128">Дополнительные сведения о дополнительном программном обеспечении, которое должно быть установлено перед публикацией топологии и установкой Lync Server 2013, можно найти в разделе [Дополнительные требования к программному обеспечению для Lync server 2013](lync-server-2013-additional-software-requirements.md) в документации по планированию.</span><span class="sxs-lookup"><span data-stu-id="587d0-128">For details about the additional software that must be installed prior to publishing your topology and installing Lync Server 2013, see [Additional software requirements for Lync Server 2013](lync-server-2013-additional-software-requirements.md) in the Planning documentation.</span></span>

</div>

</div>

<div>

## <a name="additional-software-necessary-for-all-server-roles"></a><span data-ttu-id="587d0-129">Дополнительное программное обеспечение, необходимое для всех ролей сервера</span><span class="sxs-lookup"><span data-stu-id="587d0-129">Additional Software Necessary for All Server Roles</span></span>

<span data-ttu-id="587d0-130">На всех ролях сервера также необходимо убедиться, что установлен интерфейс командной строки Windows PowerShell 3,0 и Microsoft .NET Framework 4,5.</span><span class="sxs-lookup"><span data-stu-id="587d0-130">On all server roles, you must also make sure that Windows PowerShell command-line interface 3.0 and Microsoft .NET Framework 4.5 are installed.</span></span>

<span data-ttu-id="587d0-131">Кроме того, интерфейс командной строки Windows PowerShell 3,0 и Microsoft .NET Framework 4,5 необходимы на любом компьютере, на котором выполняются средства администрирования Lync Server.</span><span class="sxs-lookup"><span data-stu-id="587d0-131">Additionally, Windows PowerShell command-line interface 3.0 and Microsoft .NET Framework 4.5 are required on any computer where you will run the Lync Server administrative tools.</span></span>

<div>

## <a name="windows-powershell-30"></a><span data-ttu-id="587d0-132">Windows PowerShell 3.0</span><span class="sxs-lookup"><span data-stu-id="587d0-132">Windows PowerShell 3.0</span></span>

<span data-ttu-id="587d0-133">Lync Server 2013 требует установки Windows PowerShell 3,0 на всех компьютерах, которые участвуют в вашей топологии Lync Server.</span><span class="sxs-lookup"><span data-stu-id="587d0-133">Lync Server 2013 requires you to install Windows PowerShell 3.0 on each computer that will take part in your Lync Server topology.</span></span> <span data-ttu-id="587d0-134">Подробнее об установке Windows PowerShell 3,0 можно узнать в разделе [Установка Windows powershell 3,0 для Lync Server 2013](lync-server-2013-installing-windows-powershell-3-0.md).</span><span class="sxs-lookup"><span data-stu-id="587d0-134">For details about installing Windows PowerShell 3.0, see [Installing Windows PowerShell 3.0 for Lync Server 2013](lync-server-2013-installing-windows-powershell-3-0.md).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="587d0-135">В Windows Server&nbsp;2008&nbsp;R2 с пакетом обновления 1 (SP1) не удается установить интерфейс командной строки Windows PowerShell 3,0 перед установкой Microsoft .NET Framework 4,5.</span><span class="sxs-lookup"><span data-stu-id="587d0-135">On Windows Server&nbsp;2008&nbsp;R2 with SP1, Windows PowerShell command-line interface 3.0 cannot be installed before installing Microsoft .NET Framework 4.5.</span></span>



</div>

</div>

<div>

## <a name="microsoft-net-framework-45"></a><span data-ttu-id="587d0-136">Платформа Microsoft .NET Framework 4.5.</span><span class="sxs-lookup"><span data-stu-id="587d0-136">Microsoft .NET Framework 4.5</span></span>

<span data-ttu-id="587d0-137">При установке Microsoft .NET Framework 4,5 на сервер, на котором работает Lync Server 2013 на платформе Windows Server 2012 или Windows Server 2012 R2, необходимо выполнить одно из дополнительных действий.</span><span class="sxs-lookup"><span data-stu-id="587d0-137">When you install Microsoft .NET Framework 4.5 on servers that will run Lync Server 2013 on Windows Server 2012 or Windows Server 2012 R2, you must perform one additional step.</span></span> <span data-ttu-id="587d0-138">После установки .NET Framework 4,5 Используйте Диспетчер серверов для установки активации HTTP.</span><span class="sxs-lookup"><span data-stu-id="587d0-138">After .NET Framework 4.5 is installed, use Server Manager to install HTTP Activation.</span></span>

<span data-ttu-id="587d0-139">**Установка активации .NET 4,5 HTTP в Windows Server 2012 или Windows Server 2012 R2**</span><span class="sxs-lookup"><span data-stu-id="587d0-139">**To Install .NET 4.5 HTTP Activation on Windows Server 2012 or Windows Server 2012 R2**</span></span>

1.  <span data-ttu-id="587d0-140">В меню **Пуск** выберите пункт **программы**, а затем — **Администрирование**, а затем — **Диспетчер серверов**.</span><span class="sxs-lookup"><span data-stu-id="587d0-140">From the **Start** menu, click **Programs**, then click **Administrative Tools**, then click **Server Manager**.</span></span>

2.  <span data-ttu-id="587d0-141">В диспетчере серверов в разделе **Сводка по компонентам**выберите **Добавить функции**.</span><span class="sxs-lookup"><span data-stu-id="587d0-141">In Server Manager, under **Features Summary**, choose **Add Features**.</span></span>

3.  <span data-ttu-id="587d0-142">Разверните **.NET Framework 4,5**.</span><span class="sxs-lookup"><span data-stu-id="587d0-142">Expand **.NET Framework 4.5**.</span></span>

4.  <span data-ttu-id="587d0-143">Выберите **Активация WCF** , если она еще не выбрана.</span><span class="sxs-lookup"><span data-stu-id="587d0-143">Select **WCF Activation** if it isn’t already selected.</span></span> <span data-ttu-id="587d0-144">Затем выберите **Активация HTTP**.</span><span class="sxs-lookup"><span data-stu-id="587d0-144">Then select **HTTP Activation**.</span></span>

5.  <span data-ttu-id="587d0-145">Нажмите кнопку **Далее** и следуйте инструкциям, чтобы завершить установку.</span><span class="sxs-lookup"><span data-stu-id="587d0-145">Click **Next** and follow the prompts to finish the installation.</span></span>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

