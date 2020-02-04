---
title: 'Lync Server 2013: технические требования для приложения "Объявление"'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Technical requirements for the Announcement application
ms:assetid: fbd8c204-3765-4b22-a0c9-a781b5126366
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205413(v=OCS.15)
ms:contentKeyID: 48185944
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8812dca81d656e68fc506c4a87c3c80481040bf6
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41746519"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="technical-requirements-for-the-announcement-application-in-lync-server-2013"></a><span data-ttu-id="c63a2-102">Технические требования для приложения "Объявление" в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c63a2-102">Technical requirements for the Announcement application in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c63a2-103">_**Тема последнего изменения:** 2013-11-07_</span><span class="sxs-lookup"><span data-stu-id="c63a2-103">_**Topic Last Modified:** 2013-11-07_</span></span>

<span data-ttu-id="c63a2-104">В этом разделе описаны следующие технические требования для приложения извещения.</span><span class="sxs-lookup"><span data-stu-id="c63a2-104">This section describes the following technical requirements for the Announcement application:</span></span>

  - <span data-ttu-id="c63a2-105">Требования к оборудованию</span><span class="sxs-lookup"><span data-stu-id="c63a2-105">Hardware requirements</span></span>

  - <span data-ttu-id="c63a2-106">Требования к программному обеспечению</span><span class="sxs-lookup"><span data-stu-id="c63a2-106">Software requirements</span></span>

  - <span data-ttu-id="c63a2-107">Требования к портам</span><span class="sxs-lookup"><span data-stu-id="c63a2-107">Port requirements</span></span>

  - <span data-ttu-id="c63a2-108">Требования к звуковым файлам</span><span class="sxs-lookup"><span data-stu-id="c63a2-108">Audio file requirements</span></span>

<div>

## <a name="hardware-requirements"></a><span data-ttu-id="c63a2-109">Требования к оборудованию</span><span class="sxs-lookup"><span data-stu-id="c63a2-109">Hardware Requirements</span></span>

<span data-ttu-id="c63a2-110">Приложение извещения имеет те же аппаратные требования, что и сервер переднего плана.</span><span class="sxs-lookup"><span data-stu-id="c63a2-110">The Announcement application has the same hardware requirements as Front End Servers.</span></span> <span data-ttu-id="c63a2-111">Сведения о требованиях к оборудованию можно найти в документации [серверные платформы для Lync server 2013](lync-server-2013-server-hardware-platforms.md) .</span><span class="sxs-lookup"><span data-stu-id="c63a2-111">For details about hardware requirements, see [Server hardware platforms for Lync Server 2013](lync-server-2013-server-hardware-platforms.md) in the Supportability documentation.</span></span>

</div>

<div>

## <a name="software-requirements"></a><span data-ttu-id="c63a2-112">Требования к программному обеспечению</span><span class="sxs-lookup"><span data-stu-id="c63a2-112">Software Requirements</span></span>

<span data-ttu-id="c63a2-113">Приложение извещения имеет те же требования к операционной системе и необходимые компоненты по отношению к серверам переднего плана.</span><span class="sxs-lookup"><span data-stu-id="c63a2-113">The Announcement application has the same operating system requirements and software prerequisites as Front End Servers.</span></span> <span data-ttu-id="c63a2-114">Подробные сведения о требованиях к программному обеспечению можно найти [в разделе Поддержка серверов и средств операционной системы в Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md) в документации по поддержке.</span><span class="sxs-lookup"><span data-stu-id="c63a2-114">For details about software requirements, see [Server and tools operating system support in Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md) in the Supportability documentation.</span></span>

<span data-ttu-id="c63a2-115">Все серверы переднего плана и стандартные серверы выпуска, на которых запущено приложение для объявления, должны установить среду выполнения формата Windows Media для серверов под управлением Windows Server 2008 R2 или Microsoft Media Foundation для серверов под управлением Windows Server 2012 или Windows Server 2012 R2.</span><span class="sxs-lookup"><span data-stu-id="c63a2-115">All Front End Servers or Standard Edition servers that run the Announcement application must have the Windows Media Format Runtime installed for servers running Windows Server 2008 R2, or Microsoft Media Foundation for servers running Windows Server 2012 or Windows Server 2012 R2.</span></span> <span data-ttu-id="c63a2-116">В Windows Server 2008 R2 среда выполнения формата Windows Media устанавливается как часть рабочего стола Windows.</span><span class="sxs-lookup"><span data-stu-id="c63a2-116">For Windows Server 2008 R2, the Windows Media Format Runtime is installed as part of Windows Desktop Experience.</span></span> <span data-ttu-id="c63a2-117">Для файлов Windows Media Audio (WMA), которые воспринимаются для объявлений и музыки, требуется приложение для работы с форматами среды предвыполнения Windows Media.</span><span class="sxs-lookup"><span data-stu-id="c63a2-117">Windows Media Format Runtime or Microsoft Media Foundation is required for Windows Media Audio (.wma) files that the Announcement application plays for announcements and music.</span></span>

</div>

<div>

## <a name="port-requirements"></a><span data-ttu-id="c63a2-118">Требования к портам</span><span class="sxs-lookup"><span data-stu-id="c63a2-118">Port Requirements</span></span>

<span data-ttu-id="c63a2-119">Приложение извещения использует следующий порт:</span><span class="sxs-lookup"><span data-stu-id="c63a2-119">The Announcement application uses the following port:</span></span>

  - <span data-ttu-id="c63a2-120">**Порт 5071**   , используемый для запросов прослушивания SIP</span><span class="sxs-lookup"><span data-stu-id="c63a2-120">**Port 5071**   Used for SIP listening requests</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="c63a2-121">Этот порт указан в параметрах по умолчанию, которые можно изменить с помощью командлета <STRONG>Set-CsApplicationServer</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="c63a2-121">This port is the default setting, which you can change by using the <STRONG>Set-CsApplicationServer</STRONG> cmdlet.</span></span> <span data-ttu-id="c63a2-122">Подробные сведения об этом командлете можно найти в документации по оболочке Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="c63a2-122">For details about this cmdlet, see the Lync Server Management Shell documentation.</span></span>



</div>

</div>

<div>

## <a name="audio-file-requirements"></a><span data-ttu-id="c63a2-123">Требования к аудиофайлам</span><span class="sxs-lookup"><span data-stu-id="c63a2-123">Audio File Requirements</span></span>

<span data-ttu-id="c63a2-124">Приложение извещения поддерживает формат файла Wave (WAV) и формат Windows Media Audio (WMA) для музыки и объявлений.</span><span class="sxs-lookup"><span data-stu-id="c63a2-124">The Announcement application supports Wave (.wav) file format and Windows Media audio (.wma) file format for music and announcements.</span></span> <span data-ttu-id="c63a2-125">Требования к звуковым файлам для приложения для объявления совпадают с требованиями приложения группы ответа.</span><span class="sxs-lookup"><span data-stu-id="c63a2-125">Audio file requirements for the Announcement application are the same as for the Response Group application.</span></span> <span data-ttu-id="c63a2-126">Подробности можно найти [в разделе Технические требования для группы ответа в Lync Server 2013](lync-server-2013-technical-requirements-for-response-group.md).</span><span class="sxs-lookup"><span data-stu-id="c63a2-126">For details, see [Technical requirements for Response Group in Lync Server 2013](lync-server-2013-technical-requirements-for-response-group.md).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

