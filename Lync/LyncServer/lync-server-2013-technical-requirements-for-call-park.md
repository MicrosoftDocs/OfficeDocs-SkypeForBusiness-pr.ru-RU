---
title: 'Lync Server 2013: технические требования к парковке вызовов'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Technical requirements for Call Park
ms:assetid: 38bcf302-2b72-4492-9266-f6dc31b566e1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204818(v=OCS.15)
ms:contentKeyID: 48183897
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 742d6ef62068e3e6e3bbd953e078b186e86bb497
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41746609"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="technical-requirements-for-call-park-in-lync-server-2013"></a><span data-ttu-id="015c0-102">Технические требования к парковке вызовов в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="015c0-102">Technical requirements for Call Park in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="015c0-103">_**Тема последнего изменения:** 2013-11-07_</span><span class="sxs-lookup"><span data-stu-id="015c0-103">_**Topic Last Modified:** 2013-11-07_</span></span>

<span data-ttu-id="015c0-104">В этом разделе описаны указанные ниже технические требования к приостановке звонков.</span><span class="sxs-lookup"><span data-stu-id="015c0-104">This section describes the following technical requirements for Call Park:</span></span>

  - <span data-ttu-id="015c0-105">Требования к оборудованию</span><span class="sxs-lookup"><span data-stu-id="015c0-105">Hardware requirements</span></span>

  - <span data-ttu-id="015c0-106">Требования к программному обеспечению</span><span class="sxs-lookup"><span data-stu-id="015c0-106">Software requirements</span></span>

  - <span data-ttu-id="015c0-107">Требования к портам</span><span class="sxs-lookup"><span data-stu-id="015c0-107">Port requirements</span></span>

  - <span data-ttu-id="015c0-108">Требования к звуковым файлам</span><span class="sxs-lookup"><span data-stu-id="015c0-108">Audio file requirements</span></span>

<div>

## <a name="hardware-requirements"></a><span data-ttu-id="015c0-109">Требования к оборудованию</span><span class="sxs-lookup"><span data-stu-id="015c0-109">Hardware Requirements</span></span>

<span data-ttu-id="015c0-110">Приложение для парковки звонков имеет те же аппаратные требования, что и внешние серверы.</span><span class="sxs-lookup"><span data-stu-id="015c0-110">The Call Park application has the same hardware requirements as Front End Servers.</span></span> <span data-ttu-id="015c0-111">Сведения о требованиях к оборудованию можно найти в документации [серверные платформы для Lync server 2013](lync-server-2013-server-hardware-platforms.md) .</span><span class="sxs-lookup"><span data-stu-id="015c0-111">For details about hardware requirements, see [Server hardware platforms for Lync Server 2013](lync-server-2013-server-hardware-platforms.md) in the Supportability documentation.</span></span>

</div>

<div>

## <a name="software-requirements"></a><span data-ttu-id="015c0-112">Требования к программному обеспечению</span><span class="sxs-lookup"><span data-stu-id="015c0-112">Software Requirements</span></span>

<span data-ttu-id="015c0-113">Приложение для парковки звонков имеет те же требования к операционной системе и необходимые компоненты по отношению к серверам переднего плана.</span><span class="sxs-lookup"><span data-stu-id="015c0-113">The Call Park application has the same operating system requirements and software prerequisites as Front End Servers.</span></span> <span data-ttu-id="015c0-114">Подробные сведения о требованиях к программному обеспечению можно найти [в разделе Поддержка серверов и средств операционной системы в Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md) в документации по поддержке.</span><span class="sxs-lookup"><span data-stu-id="015c0-114">For details about software requirements, see [Server and tools operating system support in Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md) in the Supportability documentation.</span></span>

<span data-ttu-id="015c0-115">Все серверы переднего плана и стандартные серверы выпусков, на которых развернуто приложение для остановки приема звонков, должны иметь установленную среду выполнения формата Windows Media для серверов под управлением Windows Server 2008 R2 или Microsoft Media Foundation для серверов под управлением Windows Server 2012 или Windows Server 2012 R2.</span><span class="sxs-lookup"><span data-stu-id="015c0-115">All Front End Servers and Standard Edition servers where the Call Park application is deployed must have the Windows Media Format Runtime installed for servers running Windows Server 2008 R2, or Microsoft Media Foundation for servers running Windows Server 2012 or Windows Server 2012 R2.</span></span> <span data-ttu-id="015c0-116">В операционной системе Windows Server 2008 R2 на компьютере с Windows можно установить среду выполнения формата Windows Media Format.</span><span class="sxs-lookup"><span data-stu-id="015c0-116">For Windows Server 2008 R2, Windows Media Format Runtime is installed as part of Windows Desktop Experience.</span></span> <span data-ttu-id="015c0-117">Формат среды выполнения Windows Media Audio (WMA), необходимый для воспроизведений музыкальных файлов, используется для воспроизведения музыки на удержании.</span><span class="sxs-lookup"><span data-stu-id="015c0-117">Windows Media Format Runtime or Microsoft Media Foundation is required for Windows Media Audio (.wma) files that Call Park plays for music on hold.</span></span>

</div>

<div>

## <a name="port-requirements"></a><span data-ttu-id="015c0-118">Требования к портам</span><span class="sxs-lookup"><span data-stu-id="015c0-118">Port Requirements</span></span>

<span data-ttu-id="015c0-119">Приложение для парковки звонков использует следующий порт:</span><span class="sxs-lookup"><span data-stu-id="015c0-119">The Call Park application uses the following port:</span></span>

  - <span data-ttu-id="015c0-120">**Порт 5075**   , используемый для запросов прослушивания SIP.</span><span class="sxs-lookup"><span data-stu-id="015c0-120">**Port 5075**   Used for SIP listening requests.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="015c0-121">Этот порт — это параметр по умолчанию, который можно изменить с помощью командлета <STRONG>Set-ксаппликатионсервер</STRONG> .</span><span class="sxs-lookup"><span data-stu-id="015c0-121">This port is a default setting that you can change by using the <STRONG>Set-CsApplicationServer</STRONG> cmdlet.</span></span> <span data-ttu-id="015c0-122">Подробные сведения об этом командлете можно найти в документации по оболочке Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="015c0-122">For details about this cmdlet, see the Lync Server Management Shell documentation.</span></span>



</div>

</div>

<div>

## <a name="audio-file-requirements"></a><span data-ttu-id="015c0-123">Требования к аудиофайлам</span><span class="sxs-lookup"><span data-stu-id="015c0-123">Audio File Requirements</span></span>

<span data-ttu-id="015c0-124">Приложение для парковки звонков поддерживает только файлы Windows Media Audio (WMA) для музыки на удержании.</span><span class="sxs-lookup"><span data-stu-id="015c0-124">The Call Park application supports only Windows Media Audio (.wma) files for music on hold.</span></span> <span data-ttu-id="015c0-125">Чтобы настроить файлы для воспроизведения в качестве музыки в режиме удержания, можно использовать Microsoft Expression Encoder 4.</span><span class="sxs-lookup"><span data-stu-id="015c0-125">You can use the Microsoft Expression Encoder 4 to customize files for music on hold.</span></span> <span data-ttu-id="015c0-126">Загрузить Expression Encoder 4 можно в [http://go.microsoft.com/fwlink/p/?linkId=202843](http://go.microsoft.com/fwlink/p/?linkid=202843)разделе "Expression Encoder 4".</span><span class="sxs-lookup"><span data-stu-id="015c0-126">To download Expression Encoder 4, see "Expression Encoder 4" at [http://go.microsoft.com/fwlink/p/?linkId=202843](http://go.microsoft.com/fwlink/p/?linkid=202843).</span></span> <span data-ttu-id="015c0-127">Это средство используется для преобразования файлов в формат WMA.</span><span class="sxs-lookup"><span data-stu-id="015c0-127">Use the tool to convert the file to a .wma format.</span></span> <span data-ttu-id="015c0-128">Рекомендуемый формат музыкальных файлов на входе в службу для парковки — это Media Audio 9, 44 кГц, 16 бит, моно, КБР, 32 кбит/с.</span><span class="sxs-lookup"><span data-stu-id="015c0-128">The recommended format for Call Park music-on-hold files is Media Audio 9, 44 kHz, 16 bits, Mono, CBR, 32 kbps.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="015c0-129">Преобразованный файл воспроизводится на телефоне только при 16 кГц, даже если он был записан при 44 кГц.</span><span class="sxs-lookup"><span data-stu-id="015c0-129">The converted file plays over the phone only at 16 kHz, even if it was recorded at 44 kHz.</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

