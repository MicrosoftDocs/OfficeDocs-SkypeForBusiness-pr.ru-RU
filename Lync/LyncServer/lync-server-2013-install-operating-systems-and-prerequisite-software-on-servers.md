---
title: Установка операционных систем и необходимого программного обеспечения на серверы
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
ms.openlocfilehash: 37cfbf02d379a3003338d4eabc7a5ca3c4b49f15
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48498696"
---
# <a name="install-operating-systems-and-prerequisite-software-on-servers-for-lync-server-2013"></a><span data-ttu-id="cbac2-102">Установка операционных систем и необходимого программного обеспечения на серверы для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cbac2-102">Install operating systems and prerequisite software on servers for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cbac2-103">_**Последнее изменение темы:** 2014-07-24_</span><span class="sxs-lookup"><span data-stu-id="cbac2-103">_**Topic Last Modified:** 2014-07-24_</span></span>

<span data-ttu-id="cbac2-104">После настройки аппаратной и системной инфраструктуры необходимо установить соответствующие операционные системы и обновления Windows в дополнение ко всем необходимым программным обеспечением на каждом развертываемом сервере.</span><span class="sxs-lookup"><span data-stu-id="cbac2-104">After you have set up the hardware and system infrastructure, you need to install the appropriate Windows operating systems and updates, in addition to all other prerequisite software on each server that you are deploying.</span></span> <span data-ttu-id="cbac2-105">Сюда входят все роли сервера Lync Server 2013 и все дополнительные серверы инфраструктуры или серверы SQL Server, необходимые для развертывания.</span><span class="sxs-lookup"><span data-stu-id="cbac2-105">This includes each Lync Server 2013 server role and any additional infrastructure servers or servers running SQL Server that are required for your deployment.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="cbac2-106">В этом разделе описывается установка операционных систем и необходимого программного обеспечения для внутренних серверов.</span><span class="sxs-lookup"><span data-stu-id="cbac2-106">This section describes installation of operating systems and prerequisite software for internal servers.</span></span> <span data-ttu-id="cbac2-107">Если вы развертываете пограничные серверы для поддержки доступа внешних пользователей, вам также потребуется установить операционные системы и необходимое программное обеспечение для этих серверов, в том числе пограничных серверов и обратных прокси-серверов.</span><span class="sxs-lookup"><span data-stu-id="cbac2-107">If you are deploying Edge Servers to support external user access, you also need to install operating systems and prerequisite software for those servers, including Edge Servers and reverse proxy servers.</span></span> <span data-ttu-id="cbac2-108">Подробнее о подготовке серверов к поддержке доступа внешних пользователей можно узнать в статье <A href="lync-server-2013-preparing-for-installation-of-servers-in-the-perimeter-network.md">Подготовка к установке серверов в сети периметра для Lync Server 2013</A> в документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="cbac2-108">For details about preparing servers to support external user access, see <A href="lync-server-2013-preparing-for-installation-of-servers-in-the-perimeter-network.md">Preparing for installation of servers in the perimeter network for Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<div>

## <a name="install-windows-operating-systems-on-servers"></a><span data-ttu-id="cbac2-109">Установка операционных систем Windows на серверах</span><span class="sxs-lookup"><span data-stu-id="cbac2-109">Install Windows Operating Systems on Servers</span></span>

<span data-ttu-id="cbac2-110">На каждом развертываемом сервере установите соответствующую операционную систему Windows следующим образом.</span><span class="sxs-lookup"><span data-stu-id="cbac2-110">On each server that you are deploying, install the appropriate Windows operating system as follows:</span></span>

  - <span data-ttu-id="cbac2-111">**Серверы, на которых работает Lync Server 2013**     Для получения дополнительных сведений о требованиях к операционной системе для серверов, на которых работает Lync Server 2013, обратитесь к разделу [Поддержка серверов и средств операционной системы в Lync server 2013](lync-server-2013-server-and-tools-operating-system-support.md) в документации по поддержке.</span><span class="sxs-lookup"><span data-stu-id="cbac2-111">**Servers running Lync Server 2013**   For details about the operating system requirements for servers running Lync Server 2013, see [Server and tools operating system support in Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md) in the Supportability documentation.</span></span>

  - <span data-ttu-id="cbac2-112">**Серверы**     баз данных Сведения о требованиях к операционной системе для серверов баз данных, в том числе серверной базы данных, архивной базы данных и базы данных мониторинга, представлены в документации по SQL Server.</span><span class="sxs-lookup"><span data-stu-id="cbac2-112">**Database servers**   For details about operating system requirements for database servers, including the back-end database, Archiving database, and Monitoring database, see the SQL Server documentation.</span></span> <span data-ttu-id="cbac2-113">Для SQL Server 2012 ознакомьтесь с электронной документацией по SQL Server 2012 по адресу [https://go.microsoft.com/fwlink/p/?linkId=218015](https://go.microsoft.com/fwlink/p/?linkid=218015) .</span><span class="sxs-lookup"><span data-stu-id="cbac2-113">For SQL Server 2012, see the SQL Server 2012 Books Online at [https://go.microsoft.com/fwlink/p/?linkId=218015](https://go.microsoft.com/fwlink/p/?linkid=218015).</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="cbac2-114">При установке Lync Server 2013 на Windows Server &nbsp; 2008 &nbsp; R2 с пакетом обновления 1 (SP1) необходимо сначала установить обновление, описанное в статье базы знаний Майкрософт 2646886, "исправить: повреждение кучи возникает, когда модуль вызывает метод INSERTENTITYBODY Method в службах IIS 7,5", где <A class=uri href="https://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=2646886"> https://go.microsoft.com/fwlink/p/?linkid=3052&amp ; kbid = 2646886</A>.</span><span class="sxs-lookup"><span data-stu-id="cbac2-114">If you are installing Lync Server 2013 on Windows Server&nbsp;2008&nbsp;R2 with SP1, you must first install the update described in the Microsoft Knowledge Based article 2646886, “FIX: Heap corruption occurs when a module calls the InsertEntityBody method in IIS 7.5”, at <A class=uri href="https://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=2646886">https://go.microsoft.com/fwlink/p/?linkid=3052&amp;kbid=2646886</A>.</span></span><BR><span data-ttu-id="cbac2-115">Кроме того, необходимо внести изменения в реестр, как описано в статье базы знаний, <A href="https://go.microsoft.com/fwlink/p/?linkid=506893">идентификаторы событий 32402, 61045 заносятся в журнал на серверах переднего плана Lync Server 2013, установленных в Windows server 2012 R2</A>.</span><span class="sxs-lookup"><span data-stu-id="cbac2-115">You must also modify the registry as described in the KB article, <A href="https://go.microsoft.com/fwlink/p/?linkid=506893">Event IDs 32402, 61045 are logged in Lync Server 2013 Front End servers that are installed in Windows Server 2012 R2</A>.</span></span>



</div>

</div>

<div>

## <a name="install-windows-update-on-servers"></a><span data-ttu-id="cbac2-116">Установка центра обновления Windows на серверах</span><span class="sxs-lookup"><span data-stu-id="cbac2-116">Install Windows Update on Servers</span></span>

<span data-ttu-id="cbac2-117">Установите на каждом сервере следующие обновления из центра обновления Windows:</span><span class="sxs-lookup"><span data-stu-id="cbac2-117">Install the following updates from Windows Update on each server:</span></span>

  - <span data-ttu-id="cbac2-118">**Обновление Windows для серверов, на которых работает Lync Server 2013**     Для получения дополнительных сведений об обновлениях из центра обновления Windows, необходимых для серверов, на которых работает Lync Server 2013, обратитесь к разделу [Дополнительные требования к программному обеспечению для Lync server 2013](lync-server-2013-additional-software-requirements.md) в документации по планированию.</span><span class="sxs-lookup"><span data-stu-id="cbac2-118">**Windows Update for servers running Lync Server 2013**   For details about the updates from Windows Update that are required for servers running Lync Server 2013, see [Additional software requirements for Lync Server 2013](lync-server-2013-additional-software-requirements.md) in the Planning documentation.</span></span>

  - <span data-ttu-id="cbac2-119">**Серверы**     баз данных Для получения сведений об обновлениях из центра обновления Windows, которые необходимы для серверов баз данных, в том числе серверной базы данных, архивной базы данных и базы данных мониторинга, ознакомьтесь с документацией по SQL Server 2012.</span><span class="sxs-lookup"><span data-stu-id="cbac2-119">**Database servers**   For details about the updates from Windows Update that are required for database servers, including the back-end database, Archiving database, and Monitoring database, see the SQL Server 2012 documentation.</span></span> <span data-ttu-id="cbac2-120">Для SQL Server 2012 ознакомьтесь с электронной документацией по SQL Server 2012 по адресу [https://go.microsoft.com/fwlink/p/?linkId=218015](https://go.microsoft.com/fwlink/p/?linkid=218015) .</span><span class="sxs-lookup"><span data-stu-id="cbac2-120">For SQL Server 2012, see the SQL Server 2012 Books Online at [https://go.microsoft.com/fwlink/p/?linkId=218015](https://go.microsoft.com/fwlink/p/?linkid=218015).</span></span>

</div>

<div>

## <a name="install-other-prerequisite-software-on-servers"></a><span data-ttu-id="cbac2-121">Установка другого необходимого программного обеспечения на серверах</span><span class="sxs-lookup"><span data-stu-id="cbac2-121">Install Other Prerequisite Software on Servers</span></span>

<span data-ttu-id="cbac2-122">Lync Server 2013 требует установки следующего дополнительного программного обеспечения на серверах:</span><span class="sxs-lookup"><span data-stu-id="cbac2-122">Lync Server 2013 requires the installation of the following additional software on servers:</span></span>

  - <span data-ttu-id="cbac2-123">**Необходимое программное обеспечение для серверов, на которых работает Lync Server 2013**     Дополнительные требования к программному обеспечению для серверов, на которых работает Lync Server 2013, зависят от развертываемой роли сервера.</span><span class="sxs-lookup"><span data-stu-id="cbac2-123">**Prerequisite software for servers running Lync Server 2013**   The additional software prerequisites for servers running Lync Server 2013 depend on the server role being deployed.</span></span> <span data-ttu-id="cbac2-124">Сведения о конкретных требованиях к программному обеспечению для каждого сервера приведены в разделе [Дополнительные требования к программному обеспечению для Lync server 2013](lync-server-2013-additional-software-requirements.md) в документации по планированию.</span><span class="sxs-lookup"><span data-stu-id="cbac2-124">For details about the specific software requirements for each server, see [Additional software requirements for Lync Server 2013](lync-server-2013-additional-software-requirements.md) in the Planning documentation.</span></span>

  - <span data-ttu-id="cbac2-125">**Windows Identity Foundation**     Для поддержки сценариев проверки подлинности между серверами в Lync Server 2013 требуется установка Windows Identity Foundation.</span><span class="sxs-lookup"><span data-stu-id="cbac2-125">**Windows Identity Foundation**   Lync Server 2013 requires the installation of Windows Identity Foundation in order to support server-to-server authentication scenarios.</span></span> <span data-ttu-id="cbac2-126">Чтобы проверить, установлена ли эта платформа уже на компьютере, откройте панель управления, щелкните **Программы и компоненты**, **Просмотр установленных обновлений** и убедитесь в наличии Windows Identity Foundation в разделе **Microsoft Windows**.</span><span class="sxs-lookup"><span data-stu-id="cbac2-126">To verify that it has already been installed on your computer, go to Control Panel, click **Programs and Features**, **View installed updates**, and look under **Microsoft Windows**.</span></span> <span data-ttu-id="cbac2-127">Подробные сведения об установке Windows Identity Foundation можно найти в разделе [https://go.microsoft.com/fwlink/p/?linkId=204657](https://go.microsoft.com/fwlink/p/?linkid=204657) .</span><span class="sxs-lookup"><span data-stu-id="cbac2-127">For details about installing Windows Identity Foundation, see [https://go.microsoft.com/fwlink/p/?linkId=204657](https://go.microsoft.com/fwlink/p/?linkid=204657).</span></span>

  - <span data-ttu-id="cbac2-128">**Microsoft .NET Framework 4,5**     64-разрядный выпуск Microsoft .NET Framework 4,5 необходим для Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="cbac2-128">**Microsoft .NET Framework 4.5**   The 64-bit edition of Microsoft .NET Framework 4.5 is required for Lync Server 2013.</span></span>

  - <span data-ttu-id="cbac2-129">**Необходимое программное обеспечение для серверов**     баз данных Дополнительные сведения об обновлении Windows, которое необходимо для серверов баз данных, в том числе серверной базы данных, архивной базы данных и базы данных мониторинга, представлены в документации по SQL Server 2012 [https://go.microsoft.com/fwlink/p/?linkId=218015](https://go.microsoft.com/fwlink/p/?linkid=218015) .</span><span class="sxs-lookup"><span data-stu-id="cbac2-129">**Prerequisite software for database servers**   For details about the Windows Update required for database servers, including the back-end database, Archiving database, and Monitoring database, see the SQL Server 2012 documentation at [https://go.microsoft.com/fwlink/p/?linkId=218015](https://go.microsoft.com/fwlink/p/?linkid=218015).</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="cbac2-130">Lync Server 2013 автоматически устанавливает Microsoft SQL Server 2012 Express на каждом сервере Standard Edition и на каждом сервере, на котором работает Lync Server 2013, на котором расположено локальное хранилище конфигурации.</span><span class="sxs-lookup"><span data-stu-id="cbac2-130">Lync Server 2013 automatically installs Microsoft SQL Server 2012 Express on each Standard Edition server and each server running Lync Server 2013 on which the local configuration store is located.</span></span>

    
    </div>

  - <span data-ttu-id="cbac2-131">**Среда выполнения**     формата Windows Media На всех серверах переднего плана и серверах Standard Edition, на которых будет развернута конференция, должна быть установлена среда выполнения формата Windows Media Format.</span><span class="sxs-lookup"><span data-stu-id="cbac2-131">**Windows Media Format Runtime**   All Front End Servers and Standard Edition servers where conferencing will be deployed must have the Windows Media Format Runtime installed.</span></span> <span data-ttu-id="cbac2-132">Компонент Windows Media Format Runtime необходим для воспроизведения файлов Windows Media Audio (WMA-файлов) приложениями "Парковка вызовов", "Оповещение" и "Группа ответа" при проигрывании оповещений и музыки.</span><span class="sxs-lookup"><span data-stu-id="cbac2-132">The Windows Media Format Runtime is required to run the Windows Media Audio (.wma) files that the Call Park, Announcement, and Response Group applications play for announcements and music.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="cbac2-133">Для Windows Server 2012 и Windows Server 2012 R2 среда выполнения Windows Media Format устанавливается вместе с Microsoft Media Foundation.</span><span class="sxs-lookup"><span data-stu-id="cbac2-133">For Windows Server 2012 and Windows Server 2012 R2 the Windows Media Format Runtime installs with Microsoft Media Foundation.</span></span>

    
    </div>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="cbac2-134">Для Windows Server &nbsp; 2008 и Windows server &nbsp; 2008 &nbsp; R2 среда выполнения формата Windows Media устанавливается в составе рабочего стола Windows.</span><span class="sxs-lookup"><span data-stu-id="cbac2-134">For Windows Server&nbsp;2008 and Windows Server&nbsp;2008&nbsp;R2 the Windows Media Format Runtime installs as part of the Windows Desktop Experience.</span></span> <span data-ttu-id="cbac2-135">Рекомендуется установить возможности рабочего стола Windows перед установкой Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="cbac2-135">It is recommended that you install Windows Desktop Experience before you install Lync Server 2013.</span></span> <span data-ttu-id="cbac2-136">Если Lync Server 2013 не находит это программное обеспечение на сервере, будет предложено установить его, а затем необходимо перезапустить сервер для завершения установки.</span><span class="sxs-lookup"><span data-stu-id="cbac2-136">If Lync Server 2013 does not find this software on the server, it will prompt you to install it, and then you must restart the server to complete installation.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

