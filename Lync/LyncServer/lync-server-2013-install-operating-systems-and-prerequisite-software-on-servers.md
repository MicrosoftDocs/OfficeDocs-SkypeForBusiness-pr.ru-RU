---
title: Установка операционных систем и необходимого программного обеспечения на серверы
description: Установка операционных систем и необходимого программного обеспечения на серверы.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Install operating systems and prerequisite software on servers
ms:assetid: 055991e0-5aeb-43fc-a7ba-d4b02316d73b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398103(v=OCS.15)
ms:contentKeyID: 48183288
ms.date: 07/24/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2bae9e57db9c2f1d3f3bde7ce9cc7071b73aa01d
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48574135"
---
# <a name="install-operating-systems-and-prerequisite-software-on-servers-for-lync-server-2013"></a><span data-ttu-id="6e30f-103">Установка операционных систем и необходимого программного обеспечения на серверы для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6e30f-103">Install operating systems and prerequisite software on servers for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6e30f-104">_**Последнее изменение темы:** 2014-07-24_</span><span class="sxs-lookup"><span data-stu-id="6e30f-104">_**Topic Last Modified:** 2014-07-24_</span></span>

<span data-ttu-id="6e30f-105">После настройки аппаратной и системной инфраструктуры необходимо установить соответствующие операционные системы и обновления Windows в дополнение ко всем необходимым программным обеспечением на каждом развертываемом сервере.</span><span class="sxs-lookup"><span data-stu-id="6e30f-105">After you have set up the hardware and system infrastructure, you need to install the appropriate Windows operating systems and updates, in addition to all other prerequisite software on each server that you are deploying.</span></span> <span data-ttu-id="6e30f-106">Сюда входят все роли сервера Lync Server 2013 и все дополнительные серверы инфраструктуры или серверы SQL Server, необходимые для развертывания.</span><span class="sxs-lookup"><span data-stu-id="6e30f-106">This includes each Lync Server 2013 server role and any additional infrastructure servers or servers running SQL Server that are required for your deployment.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="6e30f-107">В этом разделе описывается установка операционных систем и необходимого программного обеспечения для внутренних серверов.</span><span class="sxs-lookup"><span data-stu-id="6e30f-107">This section describes installation of operating systems and prerequisite software for internal servers.</span></span> <span data-ttu-id="6e30f-108">Если вы развертываете пограничные серверы для поддержки доступа внешних пользователей, вам также потребуется установить операционные системы и необходимое программное обеспечение для этих серверов, в том числе пограничных серверов и обратных прокси-серверов.</span><span class="sxs-lookup"><span data-stu-id="6e30f-108">If you are deploying Edge Servers to support external user access, you also need to install operating systems and prerequisite software for those servers, including Edge Servers and reverse proxy servers.</span></span> <span data-ttu-id="6e30f-109">Подробнее о подготовке серверов к поддержке доступа внешних пользователей можно узнать в статье <A href="lync-server-2013-preparing-for-installation-of-servers-in-the-perimeter-network.md">Подготовка к установке серверов в сети периметра для Lync Server 2013</A> в документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="6e30f-109">For details about preparing servers to support external user access, see <A href="lync-server-2013-preparing-for-installation-of-servers-in-the-perimeter-network.md">Preparing for installation of servers in the perimeter network for Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<div>

## <a name="install-windows-operating-systems-on-servers"></a><span data-ttu-id="6e30f-110">Установка операционных систем Windows на серверах</span><span class="sxs-lookup"><span data-stu-id="6e30f-110">Install Windows Operating Systems on Servers</span></span>

<span data-ttu-id="6e30f-111">На каждом развертываемом сервере установите соответствующую операционную систему Windows следующим образом.</span><span class="sxs-lookup"><span data-stu-id="6e30f-111">On each server that you are deploying, install the appropriate Windows operating system as follows:</span></span>

  - <span data-ttu-id="6e30f-112">**Серверы, на которых работает Lync Server 2013**     Для получения дополнительных сведений о требованиях к операционной системе для серверов, на которых работает Lync Server 2013, обратитесь к разделу [Поддержка серверов и средств операционной системы в Lync server 2013](lync-server-2013-server-and-tools-operating-system-support.md) в документации по поддержке.</span><span class="sxs-lookup"><span data-stu-id="6e30f-112">**Servers running Lync Server 2013**   For details about the operating system requirements for servers running Lync Server 2013, see [Server and tools operating system support in Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md) in the Supportability documentation.</span></span>

  - <span data-ttu-id="6e30f-113">**Серверы**     баз данных Сведения о требованиях к операционной системе для серверов баз данных, в том числе серверной базы данных, архивной базы данных и базы данных мониторинга, представлены в документации по SQL Server.</span><span class="sxs-lookup"><span data-stu-id="6e30f-113">**Database servers**   For details about operating system requirements for database servers, including the back-end database, Archiving database, and Monitoring database, see the SQL Server documentation.</span></span> <span data-ttu-id="6e30f-114">Для SQL Server 2012 ознакомьтесь с электронной документацией по SQL Server 2012 по адресу [https://go.microsoft.com/fwlink/p/?linkId=218015](https://go.microsoft.com/fwlink/p/?linkid=218015) .</span><span class="sxs-lookup"><span data-stu-id="6e30f-114">For SQL Server 2012, see the SQL Server 2012 Books Online at [https://go.microsoft.com/fwlink/p/?linkId=218015](https://go.microsoft.com/fwlink/p/?linkid=218015).</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="6e30f-115">При установке Lync Server 2013 на Windows Server &nbsp; 2008 &nbsp; R2 с пакетом обновления 1 (SP1) необходимо сначала установить обновление, описанное в статье базы знаний Майкрософт 2646886, "исправить: повреждение кучи возникает, когда модуль вызывает метод INSERTENTITYBODY Method в службах IIS 7,5", где <A class=uri href="https://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=2646886"> https://go.microsoft.com/fwlink/p/?linkid=3052&amp ; kbid = 2646886</A>.</span><span class="sxs-lookup"><span data-stu-id="6e30f-115">If you are installing Lync Server 2013 on Windows Server&nbsp;2008&nbsp;R2 with SP1, you must first install the update described in the Microsoft Knowledge Based article 2646886, “FIX: Heap corruption occurs when a module calls the InsertEntityBody method in IIS 7.5”, at <A class=uri href="https://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=2646886">https://go.microsoft.com/fwlink/p/?linkid=3052&amp;kbid=2646886</A>.</span></span><BR><span data-ttu-id="6e30f-116">Кроме того, необходимо внести изменения в реестр, как описано в статье базы знаний, <A href="https://go.microsoft.com/fwlink/p/?linkid=506893">идентификаторы событий 32402, 61045 заносятся в журнал на серверах переднего плана Lync Server 2013, установленных в Windows server 2012 R2</A>.</span><span class="sxs-lookup"><span data-stu-id="6e30f-116">You must also modify the registry as described in the KB article, <A href="https://go.microsoft.com/fwlink/p/?linkid=506893">Event IDs 32402, 61045 are logged in Lync Server 2013 Front End servers that are installed in Windows Server 2012 R2</A>.</span></span>



</div>

</div>

<div>

## <a name="install-windows-update-on-servers"></a><span data-ttu-id="6e30f-117">Установка центра обновления Windows на серверах</span><span class="sxs-lookup"><span data-stu-id="6e30f-117">Install Windows Update on Servers</span></span>

<span data-ttu-id="6e30f-118">Установите на каждом сервере следующие обновления из центра обновления Windows:</span><span class="sxs-lookup"><span data-stu-id="6e30f-118">Install the following updates from Windows Update on each server:</span></span>

  - <span data-ttu-id="6e30f-119">**Обновление Windows для серверов, на которых работает Lync Server 2013**     Для получения дополнительных сведений об обновлениях из центра обновления Windows, необходимых для серверов, на которых работает Lync Server 2013, обратитесь к разделу [Дополнительные требования к программному обеспечению для Lync server 2013](lync-server-2013-additional-software-requirements.md) в документации по планированию.</span><span class="sxs-lookup"><span data-stu-id="6e30f-119">**Windows Update for servers running Lync Server 2013**   For details about the updates from Windows Update that are required for servers running Lync Server 2013, see [Additional software requirements for Lync Server 2013](lync-server-2013-additional-software-requirements.md) in the Planning documentation.</span></span>

  - <span data-ttu-id="6e30f-120">**Серверы**     баз данных Для получения сведений об обновлениях из центра обновления Windows, которые необходимы для серверов баз данных, в том числе серверной базы данных, архивной базы данных и базы данных мониторинга, ознакомьтесь с документацией по SQL Server 2012.</span><span class="sxs-lookup"><span data-stu-id="6e30f-120">**Database servers**   For details about the updates from Windows Update that are required for database servers, including the back-end database, Archiving database, and Monitoring database, see the SQL Server 2012 documentation.</span></span> <span data-ttu-id="6e30f-121">Для SQL Server 2012 ознакомьтесь с электронной документацией по SQL Server 2012 по адресу [https://go.microsoft.com/fwlink/p/?linkId=218015](https://go.microsoft.com/fwlink/p/?linkid=218015) .</span><span class="sxs-lookup"><span data-stu-id="6e30f-121">For SQL Server 2012, see the SQL Server 2012 Books Online at [https://go.microsoft.com/fwlink/p/?linkId=218015](https://go.microsoft.com/fwlink/p/?linkid=218015).</span></span>

</div>

<div>

## <a name="install-other-prerequisite-software-on-servers"></a><span data-ttu-id="6e30f-122">Установка другого необходимого программного обеспечения на серверах</span><span class="sxs-lookup"><span data-stu-id="6e30f-122">Install Other Prerequisite Software on Servers</span></span>

<span data-ttu-id="6e30f-123">Lync Server 2013 требует установки следующего дополнительного программного обеспечения на серверах:</span><span class="sxs-lookup"><span data-stu-id="6e30f-123">Lync Server 2013 requires the installation of the following additional software on servers:</span></span>

  - <span data-ttu-id="6e30f-124">**Необходимое программное обеспечение для серверов, на которых работает Lync Server 2013**     Дополнительные требования к программному обеспечению для серверов, на которых работает Lync Server 2013, зависят от развертываемой роли сервера.</span><span class="sxs-lookup"><span data-stu-id="6e30f-124">**Prerequisite software for servers running Lync Server 2013**   The additional software prerequisites for servers running Lync Server 2013 depend on the server role being deployed.</span></span> <span data-ttu-id="6e30f-125">Сведения о конкретных требованиях к программному обеспечению для каждого сервера приведены в разделе [Дополнительные требования к программному обеспечению для Lync server 2013](lync-server-2013-additional-software-requirements.md) в документации по планированию.</span><span class="sxs-lookup"><span data-stu-id="6e30f-125">For details about the specific software requirements for each server, see [Additional software requirements for Lync Server 2013](lync-server-2013-additional-software-requirements.md) in the Planning documentation.</span></span>

  - <span data-ttu-id="6e30f-126">**Windows Identity Foundation**     Для поддержки сценариев проверки подлинности между серверами в Lync Server 2013 требуется установка Windows Identity Foundation.</span><span class="sxs-lookup"><span data-stu-id="6e30f-126">**Windows Identity Foundation**   Lync Server 2013 requires the installation of Windows Identity Foundation in order to support server-to-server authentication scenarios.</span></span> <span data-ttu-id="6e30f-127">Чтобы проверить, установлена ли эта платформа уже на компьютере, откройте панель управления, щелкните **Программы и компоненты**, **Просмотр установленных обновлений** и убедитесь в наличии Windows Identity Foundation в разделе **Microsoft Windows**.</span><span class="sxs-lookup"><span data-stu-id="6e30f-127">To verify that it has already been installed on your computer, go to Control Panel, click **Programs and Features**, **View installed updates**, and look under **Microsoft Windows**.</span></span> <span data-ttu-id="6e30f-128">Подробные сведения об установке Windows Identity Foundation можно найти в разделе [https://go.microsoft.com/fwlink/p/?linkId=204657](https://go.microsoft.com/fwlink/p/?linkid=204657) .</span><span class="sxs-lookup"><span data-stu-id="6e30f-128">For details about installing Windows Identity Foundation, see [https://go.microsoft.com/fwlink/p/?linkId=204657](https://go.microsoft.com/fwlink/p/?linkid=204657).</span></span>

  - <span data-ttu-id="6e30f-129">**Microsoft .NET Framework 4,5**     64-разрядный выпуск Microsoft .NET Framework 4,5 необходим для Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="6e30f-129">**Microsoft .NET Framework 4.5**   The 64-bit edition of Microsoft .NET Framework 4.5 is required for Lync Server 2013.</span></span>

  - <span data-ttu-id="6e30f-130">**Необходимое программное обеспечение для серверов**     баз данных Дополнительные сведения об обновлении Windows, которое необходимо для серверов баз данных, в том числе серверной базы данных, архивной базы данных и базы данных мониторинга, представлены в документации по SQL Server 2012 [https://go.microsoft.com/fwlink/p/?linkId=218015](https://go.microsoft.com/fwlink/p/?linkid=218015) .</span><span class="sxs-lookup"><span data-stu-id="6e30f-130">**Prerequisite software for database servers**   For details about the Windows Update required for database servers, including the back-end database, Archiving database, and Monitoring database, see the SQL Server 2012 documentation at [https://go.microsoft.com/fwlink/p/?linkId=218015](https://go.microsoft.com/fwlink/p/?linkid=218015).</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="6e30f-131">Lync Server 2013 автоматически устанавливает Microsoft SQL Server 2012 Express на каждом сервере Standard Edition и на каждом сервере, на котором работает Lync Server 2013, на котором расположено локальное хранилище конфигурации.</span><span class="sxs-lookup"><span data-stu-id="6e30f-131">Lync Server 2013 automatically installs Microsoft SQL Server 2012 Express on each Standard Edition server and each server running Lync Server 2013 on which the local configuration store is located.</span></span>

    
    </div>

  - <span data-ttu-id="6e30f-132">**Среда выполнения**     формата Windows Media На всех серверах переднего плана и серверах Standard Edition, на которых будет развернута конференция, должна быть установлена среда выполнения формата Windows Media Format.</span><span class="sxs-lookup"><span data-stu-id="6e30f-132">**Windows Media Format Runtime**   All Front End Servers and Standard Edition servers where conferencing will be deployed must have the Windows Media Format Runtime installed.</span></span> <span data-ttu-id="6e30f-133">Компонент Windows Media Format Runtime необходим для воспроизведения файлов Windows Media Audio (WMA-файлов) приложениями "Парковка вызовов", "Оповещение" и "Группа ответа" при проигрывании оповещений и музыки.</span><span class="sxs-lookup"><span data-stu-id="6e30f-133">The Windows Media Format Runtime is required to run the Windows Media Audio (.wma) files that the Call Park, Announcement, and Response Group applications play for announcements and music.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="6e30f-134">Для Windows Server 2012 и Windows Server 2012 R2 среда выполнения Windows Media Format устанавливается вместе с Microsoft Media Foundation.</span><span class="sxs-lookup"><span data-stu-id="6e30f-134">For Windows Server 2012 and Windows Server 2012 R2 the Windows Media Format Runtime installs with Microsoft Media Foundation.</span></span>

    
    </div>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="6e30f-135">Для Windows Server &nbsp; 2008 и Windows server &nbsp; 2008 &nbsp; R2 среда выполнения формата Windows Media устанавливается в составе рабочего стола Windows.</span><span class="sxs-lookup"><span data-stu-id="6e30f-135">For Windows Server&nbsp;2008 and Windows Server&nbsp;2008&nbsp;R2 the Windows Media Format Runtime installs as part of the Windows Desktop Experience.</span></span> <span data-ttu-id="6e30f-136">Рекомендуется установить возможности рабочего стола Windows перед установкой Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="6e30f-136">It is recommended that you install Windows Desktop Experience before you install Lync Server 2013.</span></span> <span data-ttu-id="6e30f-137">Если Lync Server 2013 не находит это программное обеспечение на сервере, будет предложено установить его, а затем необходимо перезапустить сервер для завершения установки.</span><span class="sxs-lookup"><span data-stu-id="6e30f-137">If Lync Server 2013 does not find this software on the server, it will prompt you to install it, and then you must restart the server to complete installation.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

