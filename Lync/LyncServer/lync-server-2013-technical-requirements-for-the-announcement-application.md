---
title: 'Lync Server 2013: технические требования для приложения "оповещение"'
description: 'Lync Server 2013: технические требования для приложения "извещения".'
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
ms.openlocfilehash: adc5019408b79301bbcda3993ceb7d96ee4d9b7d
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48550315"
---
# <a name="technical-requirements-for-the-announcement-application-in-lync-server-2013"></a><span data-ttu-id="29336-103">Технические требования для приложения "объявление" в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="29336-103">Technical requirements for the Announcement application in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="29336-104">_**Последнее изменение темы:** 2013-11-07_</span><span class="sxs-lookup"><span data-stu-id="29336-104">_**Topic Last Modified:** 2013-11-07_</span></span>

<span data-ttu-id="29336-105">В этом разделе описываются следующие технические требования для приложения "извещения".</span><span class="sxs-lookup"><span data-stu-id="29336-105">This section describes the following technical requirements for the Announcement application:</span></span>

  - <span data-ttu-id="29336-106">Требования к оборудованию</span><span class="sxs-lookup"><span data-stu-id="29336-106">Hardware requirements</span></span>

  - <span data-ttu-id="29336-107">Требования к программному обеспечению</span><span class="sxs-lookup"><span data-stu-id="29336-107">Software requirements</span></span>

  - <span data-ttu-id="29336-108">Требования к портам</span><span class="sxs-lookup"><span data-stu-id="29336-108">Port requirements</span></span>

  - <span data-ttu-id="29336-109">Требования к аудиофайлам</span><span class="sxs-lookup"><span data-stu-id="29336-109">Audio file requirements</span></span>

<div>

## <a name="hardware-requirements"></a><span data-ttu-id="29336-110">Требования к оборудованию</span><span class="sxs-lookup"><span data-stu-id="29336-110">Hardware Requirements</span></span>

<span data-ttu-id="29336-111">Приложение извещения имеет те же требования к оборудованию, что и серверы переднего плана.</span><span class="sxs-lookup"><span data-stu-id="29336-111">The Announcement application has the same hardware requirements as Front End Servers.</span></span> <span data-ttu-id="29336-112">Сведения о требованиях к оборудованию приведены в статье [Server Hardware Platforms for Lync server 2013](lync-server-2013-server-hardware-platforms.md) в документации по поддержке.</span><span class="sxs-lookup"><span data-stu-id="29336-112">For details about hardware requirements, see [Server hardware platforms for Lync Server 2013](lync-server-2013-server-hardware-platforms.md) in the Supportability documentation.</span></span>

</div>

<div>

## <a name="software-requirements"></a><span data-ttu-id="29336-113">Требования к программному обеспечению</span><span class="sxs-lookup"><span data-stu-id="29336-113">Software Requirements</span></span>

<span data-ttu-id="29336-114">Приложение извещения имеет те же требования к операционной системе и программное обеспечение, что и серверы переднего плана.</span><span class="sxs-lookup"><span data-stu-id="29336-114">The Announcement application has the same operating system requirements and software prerequisites as Front End Servers.</span></span> <span data-ttu-id="29336-115">Сведения о требованиях к программному обеспечению приведены в статье [Поддержка серверов и средств операционной системы в Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md) в документации по поддержке.</span><span class="sxs-lookup"><span data-stu-id="29336-115">For details about software requirements, see [Server and tools operating system support in Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md) in the Supportability documentation.</span></span>

<span data-ttu-id="29336-116">На всех серверах переднего плана или серверах Standard Edition, на которых работает приложение для извещения, должна быть установлена среда выполнения формата Windows Media для серверов под управлением Windows Server 2008 R2 или Microsoft Media Foundation для серверов под управлением Windows Server 2012 или Windows Server 2012 R2.</span><span class="sxs-lookup"><span data-stu-id="29336-116">All Front End Servers or Standard Edition servers that run the Announcement application must have the Windows Media Format Runtime installed for servers running Windows Server 2008 R2, or Microsoft Media Foundation for servers running Windows Server 2012 or Windows Server 2012 R2.</span></span> <span data-ttu-id="29336-117">Для Windows Server 2008 R2 среда выполнения формата Windows Media устанавливается в составе Windows Desktop Experience.</span><span class="sxs-lookup"><span data-stu-id="29336-117">For Windows Server 2008 R2, the Windows Media Format Runtime is installed as part of Windows Desktop Experience.</span></span> <span data-ttu-id="29336-118">Windows Media Format Runtime или Microsoft Media Foundation необходим для файлов Windows Media Audio (WMA), которые приложение для оповещений воспроизводится для оповещений и музыки.</span><span class="sxs-lookup"><span data-stu-id="29336-118">Windows Media Format Runtime or Microsoft Media Foundation is required for Windows Media Audio (.wma) files that the Announcement application plays for announcements and music.</span></span>

</div>

<div>

## <a name="port-requirements"></a><span data-ttu-id="29336-119">Требования к портам</span><span class="sxs-lookup"><span data-stu-id="29336-119">Port Requirements</span></span>

<span data-ttu-id="29336-120">Приложение извещения использует следующий порт:</span><span class="sxs-lookup"><span data-stu-id="29336-120">The Announcement application uses the following port:</span></span>

  - <span data-ttu-id="29336-121">**Порт 5071**     Используется для запросов прослушивания SIP</span><span class="sxs-lookup"><span data-stu-id="29336-121">**Port 5071**   Used for SIP listening requests</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="29336-122">Этот порт указан в параметрах по умолчанию, которые можно изменить с помощью командлета <STRONG>Set-CsApplicationServer</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="29336-122">This port is the default setting, which you can change by using the <STRONG>Set-CsApplicationServer</STRONG> cmdlet.</span></span> <span data-ttu-id="29336-123">Подробнее об этом командлете можно узнать в документации по командной консоли Lync Server.</span><span class="sxs-lookup"><span data-stu-id="29336-123">For details about this cmdlet, see the Lync Server Management Shell documentation.</span></span>



</div>

</div>

<div>

## <a name="audio-file-requirements"></a><span data-ttu-id="29336-124">Требования к аудиофайлам</span><span class="sxs-lookup"><span data-stu-id="29336-124">Audio File Requirements</span></span>

<span data-ttu-id="29336-125">Приложение извещения поддерживает формат файлов WAV и Windows Media Audio (WMA) для музыкальных сообщений и объявлений.</span><span class="sxs-lookup"><span data-stu-id="29336-125">The Announcement application supports Wave (.wav) file format and Windows Media audio (.wma) file format for music and announcements.</span></span> <span data-ttu-id="29336-126">Требования к звуковым файлам для приложения оповещений совпадают с требованиями приложения группы ответа.</span><span class="sxs-lookup"><span data-stu-id="29336-126">Audio file requirements for the Announcement application are the same as for the Response Group application.</span></span> <span data-ttu-id="29336-127">Подробные сведения см. [в статье технические требования для группы ответа в Lync Server 2013](lync-server-2013-technical-requirements-for-response-group.md).</span><span class="sxs-lookup"><span data-stu-id="29336-127">For details, see [Technical requirements for Response Group in Lync Server 2013](lync-server-2013-technical-requirements-for-response-group.md).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

