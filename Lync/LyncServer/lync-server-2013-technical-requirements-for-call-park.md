---
title: 'Lync Server 2013: технические требования для парковки вызовов'
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
ms.openlocfilehash: 8b5fb5f86dd575daf603bd0a21235184346bca05
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48533956"
---
# <a name="technical-requirements-for-call-park-in-lync-server-2013"></a><span data-ttu-id="6a304-102">Технические требования для парковки вызовов в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6a304-102">Technical requirements for Call Park in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6a304-103">_**Последнее изменение темы:** 2013-11-07_</span><span class="sxs-lookup"><span data-stu-id="6a304-103">_**Topic Last Modified:** 2013-11-07_</span></span>

<span data-ttu-id="6a304-104">В этом разделе описываются следующие технические требования для парковки вызовов:</span><span class="sxs-lookup"><span data-stu-id="6a304-104">This section describes the following technical requirements for Call Park:</span></span>

  - <span data-ttu-id="6a304-105">Требования к оборудованию</span><span class="sxs-lookup"><span data-stu-id="6a304-105">Hardware requirements</span></span>

  - <span data-ttu-id="6a304-106">Требования к программному обеспечению</span><span class="sxs-lookup"><span data-stu-id="6a304-106">Software requirements</span></span>

  - <span data-ttu-id="6a304-107">Требования к портам</span><span class="sxs-lookup"><span data-stu-id="6a304-107">Port requirements</span></span>

  - <span data-ttu-id="6a304-108">Требования к аудиофайлам</span><span class="sxs-lookup"><span data-stu-id="6a304-108">Audio file requirements</span></span>

<div>

## <a name="hardware-requirements"></a><span data-ttu-id="6a304-109">Требования к оборудованию</span><span class="sxs-lookup"><span data-stu-id="6a304-109">Hardware Requirements</span></span>

<span data-ttu-id="6a304-110">Приложение парковки вызовов имеет те же требования к оборудованию, что и серверы переднего плана.</span><span class="sxs-lookup"><span data-stu-id="6a304-110">The Call Park application has the same hardware requirements as Front End Servers.</span></span> <span data-ttu-id="6a304-111">Сведения о требованиях к оборудованию приведены в статье [Server Hardware Platforms for Lync server 2013](lync-server-2013-server-hardware-platforms.md) в документации по поддержке.</span><span class="sxs-lookup"><span data-stu-id="6a304-111">For details about hardware requirements, see [Server hardware platforms for Lync Server 2013](lync-server-2013-server-hardware-platforms.md) in the Supportability documentation.</span></span>

</div>

<div>

## <a name="software-requirements"></a><span data-ttu-id="6a304-112">Требования к программному обеспечению</span><span class="sxs-lookup"><span data-stu-id="6a304-112">Software Requirements</span></span>

<span data-ttu-id="6a304-113">Приложение парковки вызовов имеет те же требования к операционной системе и программное обеспечение, что и серверы переднего плана.</span><span class="sxs-lookup"><span data-stu-id="6a304-113">The Call Park application has the same operating system requirements and software prerequisites as Front End Servers.</span></span> <span data-ttu-id="6a304-114">Сведения о требованиях к программному обеспечению приведены в статье [Поддержка серверов и средств операционной системы в Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md) в документации по поддержке.</span><span class="sxs-lookup"><span data-stu-id="6a304-114">For details about software requirements, see [Server and tools operating system support in Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md) in the Supportability documentation.</span></span>

<span data-ttu-id="6a304-115">Все серверы переднего плана и серверы Standard Edition, на которых развернуто приложение парковки вызовов, должны иметь среду выполнения формата Windows Media, установленную для серверов под управлением Windows Server 2008 R2 или Microsoft Media Foundation для серверов под управлением Windows Server 2012 или Windows Server 2012 R2.</span><span class="sxs-lookup"><span data-stu-id="6a304-115">All Front End Servers and Standard Edition servers where the Call Park application is deployed must have the Windows Media Format Runtime installed for servers running Windows Server 2008 R2, or Microsoft Media Foundation for servers running Windows Server 2012 or Windows Server 2012 R2.</span></span> <span data-ttu-id="6a304-116">Для Windows Server 2008 R2 среда выполнения формата Windows Media устанавливается в составе Windows Desktop Experience.</span><span class="sxs-lookup"><span data-stu-id="6a304-116">For Windows Server 2008 R2, Windows Media Format Runtime is installed as part of Windows Desktop Experience.</span></span> <span data-ttu-id="6a304-117">Windows Media Format Runtime или Microsoft Media Foundation необходим для файлов Windows Media Audio (WMA), воспроизводимых для прослушивания музыки при удержании.</span><span class="sxs-lookup"><span data-stu-id="6a304-117">Windows Media Format Runtime or Microsoft Media Foundation is required for Windows Media Audio (.wma) files that Call Park plays for music on hold.</span></span>

</div>

<div>

## <a name="port-requirements"></a><span data-ttu-id="6a304-118">Требования к портам</span><span class="sxs-lookup"><span data-stu-id="6a304-118">Port Requirements</span></span>

<span data-ttu-id="6a304-119">Приложение парковки вызовов использует следующий порт:</span><span class="sxs-lookup"><span data-stu-id="6a304-119">The Call Park application uses the following port:</span></span>

  - <span data-ttu-id="6a304-120">**Порт 5075**     Используется для запросов прослушивания SIP.</span><span class="sxs-lookup"><span data-stu-id="6a304-120">**Port 5075**   Used for SIP listening requests.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="6a304-121">Этот порт является установкой по умолчанию, которую можно изменить с помощью командлета <STRONG>Set-CsApplicationServer</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="6a304-121">This port is a default setting that you can change by using the <STRONG>Set-CsApplicationServer</STRONG> cmdlet.</span></span> <span data-ttu-id="6a304-122">Подробнее об этом командлете можно узнать в документации по командной консоли Lync Server.</span><span class="sxs-lookup"><span data-stu-id="6a304-122">For details about this cmdlet, see the Lync Server Management Shell documentation.</span></span>



</div>

</div>

<div>

## <a name="audio-file-requirements"></a><span data-ttu-id="6a304-123">Требования к аудиофайлам</span><span class="sxs-lookup"><span data-stu-id="6a304-123">Audio File Requirements</span></span>

<span data-ttu-id="6a304-124">Приложение парковки вызовов поддерживает только файлы Windows Media Audio (WMA) для музыки при удержании.</span><span class="sxs-lookup"><span data-stu-id="6a304-124">The Call Park application supports only Windows Media Audio (.wma) files for music on hold.</span></span> <span data-ttu-id="6a304-125">Вы можете использовать Microsoft Expression Encoder 4 для настройки файлов для музыкальных файлов на удержании.</span><span class="sxs-lookup"><span data-stu-id="6a304-125">You can use the Microsoft Expression Encoder 4 to customize files for music on hold.</span></span> <span data-ttu-id="6a304-126">Чтобы скачать Expression Encoder 4, обратитесь к разделу "Expression Encoder 4" на странице [https://go.microsoft.com/fwlink/p/?linkId=202843](https://go.microsoft.com/fwlink/p/?linkid=202843) .</span><span class="sxs-lookup"><span data-stu-id="6a304-126">To download Expression Encoder 4, see "Expression Encoder 4" at [https://go.microsoft.com/fwlink/p/?linkId=202843](https://go.microsoft.com/fwlink/p/?linkid=202843).</span></span> <span data-ttu-id="6a304-127">Используйте средство, чтобы преобразовать файл в формат WMA.</span><span class="sxs-lookup"><span data-stu-id="6a304-127">Use the tool to convert the file to a .wma format.</span></span> <span data-ttu-id="6a304-128">Рекомендуемый формат для файлов музыки для парковки на удержание вызовов — Media Audio 9, 44 кГц, 16 бит, моно, CBR, 32 кбит/с.</span><span class="sxs-lookup"><span data-stu-id="6a304-128">The recommended format for Call Park music-on-hold files is Media Audio 9, 44 kHz, 16 bits, Mono, CBR, 32 kbps.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="6a304-129">Преобразованный файл воспроизводится на телефоне только на 16 кГц, даже если он был записан на 44 кГц.</span><span class="sxs-lookup"><span data-stu-id="6a304-129">The converted file plays over the phone only at 16 kHz, even if it was recorded at 44 kHz.</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

