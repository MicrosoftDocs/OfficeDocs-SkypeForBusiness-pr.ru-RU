---
title: 'Lync Server 2013: технические требования для групп ответа'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Technical requirements for Response Group
ms:assetid: 477488bd-124f-437b-9327-732a0d7271ca
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204863(v=OCS.15)
ms:contentKeyID: 48184044
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2dd87cb270d527753d9c6404ded4162791b542f7
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34849500"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="technical-requirements-for-response-group-in-lync-server-2013"></a><span data-ttu-id="eb837-102">Технические требования для групп ответа в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="eb837-102">Technical requirements for Response Group in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="eb837-103">_**Тема последнего изменения:** 2013-11-07_</span><span class="sxs-lookup"><span data-stu-id="eb837-103">_**Topic Last Modified:** 2013-11-07_</span></span>

<span data-ttu-id="eb837-104">В этом разделе описаны указанные ниже технические требования к приложению группы ответа.</span><span class="sxs-lookup"><span data-stu-id="eb837-104">This section describes the following technical requirements for the Response Group application:</span></span>

  - <span data-ttu-id="eb837-105">Требования к оборудованию</span><span class="sxs-lookup"><span data-stu-id="eb837-105">Hardware requirements</span></span>

  - <span data-ttu-id="eb837-106">Требования к программному обеспечению </span><span class="sxs-lookup"><span data-stu-id="eb837-106">Software requirements</span></span>

  - <span data-ttu-id="eb837-107">Требования к портам</span><span class="sxs-lookup"><span data-stu-id="eb837-107">Port requirements</span></span>

  - <span data-ttu-id="eb837-108">Требования к звуковым файлам</span><span class="sxs-lookup"><span data-stu-id="eb837-108">Audio file requirements</span></span>

  - <span data-ttu-id="eb837-109">Требования к инструментам настройки группы ответа</span><span class="sxs-lookup"><span data-stu-id="eb837-109">Response Group configuration tool requirements</span></span>

<div>

## <a name="hardware-requirements"></a><span data-ttu-id="eb837-110">Требования к оборудованию</span><span class="sxs-lookup"><span data-stu-id="eb837-110">Hardware Requirements</span></span>

<span data-ttu-id="eb837-111">Приложение группы ответа имеет те же аппаратные требования, что и сервер переднего плана.</span><span class="sxs-lookup"><span data-stu-id="eb837-111">The Response Group application has the same hardware requirements as Front End Servers.</span></span> <span data-ttu-id="eb837-112">Сведения о требованиях к оборудованию можно найти в документации [серверные платформы для Lync server 2013](lync-server-2013-server-hardware-platforms.md) .</span><span class="sxs-lookup"><span data-stu-id="eb837-112">For details about hardware requirements, see [Server hardware platforms for Lync Server 2013](lync-server-2013-server-hardware-platforms.md) in the Supportability documentation.</span></span>

</div>

<div>

## <a name="software-requirements"></a><span data-ttu-id="eb837-113">Требования к программному обеспечению</span><span class="sxs-lookup"><span data-stu-id="eb837-113">Software Requirements</span></span>

<span data-ttu-id="eb837-114">Приложение группы ответа имеет те же требования к операционной системе и необходимые компоненты по отношению к серверам переднего плана.</span><span class="sxs-lookup"><span data-stu-id="eb837-114">The Response Group application has the same operating system requirements and software prerequisites as Front End Servers.</span></span> <span data-ttu-id="eb837-115">Подробные сведения о требованиях к программному обеспечению можно найти [в разделе Поддержка серверов и средств операционной системы в Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md) в документации по поддержке.</span><span class="sxs-lookup"><span data-stu-id="eb837-115">For details about software requirements, see [Server and tools operating system support in Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md) in the Supportability documentation.</span></span>

<span data-ttu-id="eb837-116">Если вы используете файлы Windows Media Audio (WMA) для музыкального сопровождения и объявлений группы ответа, на всех серверах переднего плана или стандартных выпусках, запускающих приложение группы ответа, должна быть установлена среда выполнения формата Windows Media для серверов под управлением Windows Сервер 2008 R2 или Microsoft Media Foundation для серверов под управлением Windows Server 2012 или Windows Server 2012 R2.</span><span class="sxs-lookup"><span data-stu-id="eb837-116">If you use Windows Media Audio (.wma) files for Response Group music and announcements, all Front End Servers or Standard Editions servers that run the Response Group application must have the Windows Media Format Runtime installed for servers running Windows Server 2008 R2, or Microsoft Media Foundation for servers running Windows Server 2012 or Windows Server 2012 R2.</span></span> <span data-ttu-id="eb837-117">В операционной системе Windows Server 2008 R2 на компьютере с Windows можно установить среду выполнения формата Windows Media Format.</span><span class="sxs-lookup"><span data-stu-id="eb837-117">For Windows Server 2008 R2, Windows Media Format Runtime is installed as part of Windows Desktop Experience.</span></span>

<span data-ttu-id="eb837-118">Дополнительные сведения о требованиях к аудио можно найти в разделе "требования к звуковым файлам" ниже.</span><span class="sxs-lookup"><span data-stu-id="eb837-118">For more details about audio requirements, see "Audio File Requirements" later in this section.</span></span>

</div>

<div>

## <a name="port-requirements"></a><span data-ttu-id="eb837-119">Требования к портам</span><span class="sxs-lookup"><span data-stu-id="eb837-119">Port Requirements</span></span>

<span data-ttu-id="eb837-120">Приложение "группа ответа" использует следующие порты:</span><span class="sxs-lookup"><span data-stu-id="eb837-120">The Response Group application uses the following ports:</span></span>

  - <span data-ttu-id="eb837-121">**Порт 5071**   , используемый для запросов прослушивания SIP</span><span class="sxs-lookup"><span data-stu-id="eb837-121">**Port 5071**   Used for SIP listening requests</span></span>

  - <span data-ttu-id="eb837-122">**Порт 8404**   , используемый для межсерверной связи</span><span class="sxs-lookup"><span data-stu-id="eb837-122">**Port 8404**   Used for interserver communications</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="eb837-123">Этот порт используется для проверки соответствия требованиям и является обязательным, если приложение группы ответа развернуто в пуле, который содержит более одного сервера переднего плана.</span><span class="sxs-lookup"><span data-stu-id="eb837-123">This port is used for the Match Making service and is required when the Response Group application is deployed in a pool that has more than one Front End Server.</span></span>

    
    </div>

<div>


> [!NOTE]  
> <span data-ttu-id="eb837-124">Эти порты являются установками по умолчанию, которые можно изменить с помощью командлета <STRONG>Set-CsApplicationServer</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="eb837-124">These ports are default settings that you can change by using the <STRONG>Set-CsApplicationServer</STRONG> cmdlet.</span></span> <span data-ttu-id="eb837-125">Подробные сведения об этом командлете можно найти в документации по оболочке Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="eb837-125">For details about this cmdlet, see the Lync Server Management Shell documentation.</span></span>



</div>

</div>

<div>

## <a name="audio-file-requirements"></a><span data-ttu-id="eb837-126">Требования к аудиофайлам</span><span class="sxs-lookup"><span data-stu-id="eb837-126">Audio File Requirements</span></span>

<span data-ttu-id="eb837-127">Приложение "группа ответа" поддерживает формат файла Wave (WAV) и формат Windows Media Audio (WMA) для сообщений группы ответа, хранения музыки и интерактивных голосовых ответов (интерактивный автоответчик).</span><span class="sxs-lookup"><span data-stu-id="eb837-127">The Response Group application supports wave (.wav) file format and Windows Media audio (.wma) file format for Response Group messages, on-hold music, or interactive voice response (IVR) questions.</span></span>

<span data-ttu-id="eb837-128">Для формата звуковых файлов Windows Media требуется, чтобы среда выполнения формата Windows Media была установлена на серверах переднего плана под управлением Windows Server 2008 R2 и Windows Server 2008.</span><span class="sxs-lookup"><span data-stu-id="eb837-128">The Windows Media audio file format requires that the Windows Media Format Runtime is installed on Front End Servers running Windows Server 2008 R2 and Windows Server 2008.</span></span> <span data-ttu-id="eb837-129">Более подробно см. выше в подразделе "Требования к программному обеспечению".</span><span class="sxs-lookup"><span data-stu-id="eb837-129">For more details, see "Software Requirements" earlier in this section.</span></span>

<div>

## <a name="supported-wave-file-formats"></a><span data-ttu-id="eb837-130">Поддерживаемые форматы файлов WAV</span><span class="sxs-lookup"><span data-stu-id="eb837-130">Supported Wave File Formats</span></span>

<span data-ttu-id="eb837-131">Все файлы WAV должны удовлетворять следующим требованиям.</span><span class="sxs-lookup"><span data-stu-id="eb837-131">All wave files must meet the following requirements:</span></span>

  - <span data-ttu-id="eb837-132">8-разрядный или 16-разрядный файл</span><span class="sxs-lookup"><span data-stu-id="eb837-132">8-bit or 16-bit file</span></span>

  - <span data-ttu-id="eb837-133">Формат линейной импульсно-кодовой модуляции, A-Law или mu-Law</span><span class="sxs-lookup"><span data-stu-id="eb837-133">Linear pulse code modulation (LPCM), A-Law, or mu-Law format</span></span>

  - <span data-ttu-id="eb837-134">Моно или стерео</span><span class="sxs-lookup"><span data-stu-id="eb837-134">Mono or stereo</span></span>

  - <span data-ttu-id="eb837-135">4 МБ или меньше</span><span class="sxs-lookup"><span data-stu-id="eb837-135">4MB or less</span></span>

<span data-ttu-id="eb837-136">Для обеспечения наилучшей производительности файлов WAV рекомендуется использовать монофонический 16-разрядный файл WAV с частотой 16 кГц.</span><span class="sxs-lookup"><span data-stu-id="eb837-136">For the best performance of wave files, a 16 kHz, mono, 16-bit Wave file is recommended.</span></span>

</div>

<div>

## <a name="supported-windows-media-audio-file-formats"></a><span data-ttu-id="eb837-137">Поддерживаемые форматы файлов WMA</span><span class="sxs-lookup"><span data-stu-id="eb837-137">Supported Windows Media Audio File Formats</span></span>

<span data-ttu-id="eb837-138">Если вы используете файл WMA, рекомендуется применять низкие скорости и проверить производительность системы под нагрузкой.</span><span class="sxs-lookup"><span data-stu-id="eb837-138">If you use a Windows Media audio file, consider using low bit rates, and verify the performance of your system under load.</span></span>

<span data-ttu-id="eb837-139">Вы можете использовать Microsoft Expression Encoder 4 для преобразования файла в звуковой формат Windows Media.</span><span class="sxs-lookup"><span data-stu-id="eb837-139">You can use the Microsoft Expression Encoder 4 to convert a file to the Windows Media Audio format.</span></span> <span data-ttu-id="eb837-140">Чтобы скачать Expression Encoder 4, ознакомьтесь [http://go.microsoft.com/fwlink/p/?linkId=202843](http://go.microsoft.com/fwlink/p/?linkid=202843)с разрядом.</span><span class="sxs-lookup"><span data-stu-id="eb837-140">To download Expression Encoder 4, see [http://go.microsoft.com/fwlink/p/?linkId=202843](http://go.microsoft.com/fwlink/p/?linkid=202843).</span></span>

</div>

</div>

<div>

## <a name="response-group-configuration-tool-requirements"></a><span data-ttu-id="eb837-141">Требования к средствам настройки группы ответа</span><span class="sxs-lookup"><span data-stu-id="eb837-141">Response Group Configuration Tool Requirements</span></span>

<span data-ttu-id="eb837-142">Средство настройки группы ответа поддерживает комбинации операционных систем и веб-браузеров, описанные в приведенной ниже таблице.</span><span class="sxs-lookup"><span data-stu-id="eb837-142">The Response Group Configuration Tool supports the combinations of operating systems and web browsers described in the following table.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="eb837-p107">Поддерживаются 32-разрядная или 64-разрядная версии операционных систем. Поддерживаются только 32-разрядные версии Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="eb837-p107">32-bit or 64-bit versions of the operating systems are supported. Only 32-bit versions of Internet Explorer are supported.</span></span>



</div>

### <a name="supported-operating-systems-and-web-browsers"></a><span data-ttu-id="eb837-145">Поддерживаемые операционные системы и веб-браузеры</span><span class="sxs-lookup"><span data-stu-id="eb837-145">Supported Operating Systems and Web Browsers</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="eb837-146">Операционная система</span><span class="sxs-lookup"><span data-stu-id="eb837-146">Operating system</span></span></th>
<th><span data-ttu-id="eb837-147">Веб-браузер</span><span class="sxs-lookup"><span data-stu-id="eb837-147">Web browser</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="eb837-148">Windows Vista с пакетом обновления 2 (SP2)</span><span class="sxs-lookup"><span data-stu-id="eb837-148">Windows Vista with Service Pack (SP) 2</span></span></p></td>
<td><p><span data-ttu-id="eb837-149">Internet Explorer 7</span><span class="sxs-lookup"><span data-stu-id="eb837-149">Internet Explorer 7</span></span></p>
<p><span data-ttu-id="eb837-150">Internet Explorer 8 (основной режим)</span><span class="sxs-lookup"><span data-stu-id="eb837-150">Internet Explorer 8 (native mode)</span></span></p>
<p><span data-ttu-id="eb837-151">Internet Explorer 9 (основной режим)</span><span class="sxs-lookup"><span data-stu-id="eb837-151">Internet Explorer 9 (native mode)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eb837-152">Windows 7</span><span class="sxs-lookup"><span data-stu-id="eb837-152">Windows 7</span></span></p>
<p><span data-ttu-id="eb837-153">Windows 7 с пакетом обновления 1 (SP1)</span><span class="sxs-lookup"><span data-stu-id="eb837-153">Windows 7 with Service Pack 1</span></span></p></td>
<td><p><span data-ttu-id="eb837-154">Internet Explorer 8 (основной режим)</span><span class="sxs-lookup"><span data-stu-id="eb837-154">Internet Explorer 8 (native mode)</span></span></p>
<p><span data-ttu-id="eb837-155">Internet Explorer 9 (основной режим)</span><span class="sxs-lookup"><span data-stu-id="eb837-155">Internet Explorer 9 (native mode)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eb837-156">Windows Server 2008 с пакетом обновления 2 (SP2)</span><span class="sxs-lookup"><span data-stu-id="eb837-156">Windows Server 2008 with Service Pack 2</span></span></p></td>
<td><p><span data-ttu-id="eb837-157">Internet Explorer 7</span><span class="sxs-lookup"><span data-stu-id="eb837-157">Internet Explorer 7</span></span></p>
<p><span data-ttu-id="eb837-158">Internet Explorer 8 (основной режим)</span><span class="sxs-lookup"><span data-stu-id="eb837-158">Internet Explorer 8 (native mode)</span></span></p>
<p><span data-ttu-id="eb837-159">Internet Explorer 9 (основной режим)</span><span class="sxs-lookup"><span data-stu-id="eb837-159">Internet Explorer 9 (native mode)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eb837-160">Windows Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="eb837-160">Windows Server 2008 R2</span></span></p>
<p><span data-ttu-id="eb837-161">Windows Server 2008 R2 с пакетом обновления 1 (SP1)</span><span class="sxs-lookup"><span data-stu-id="eb837-161">Windows Server 2008 R2 with Service Pack 1</span></span></p></td>
<td><p><span data-ttu-id="eb837-162">Internet Explorer 8 (основной режим)</span><span class="sxs-lookup"><span data-stu-id="eb837-162">Internet Explorer 8 (native mode)</span></span></p>
<p><span data-ttu-id="eb837-163">Internet Explorer 9 (основной режим)</span><span class="sxs-lookup"><span data-stu-id="eb837-163">Internet Explorer 9 (native mode)</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="response-group-agent-console"></a><span data-ttu-id="eb837-164">Консоль агента группы ответа</span><span class="sxs-lookup"><span data-stu-id="eb837-164">Response Group Agent Console</span></span>

<span data-ttu-id="eb837-165">Консоль агента поддерживает сочетания операционной системы и веб-браузера, перечисленные в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="eb837-165">The agent console supports the combinations of operating systems and web browsers described in the following table.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="eb837-p108">Поддерживаются 32-разрядная или 64-разрядная версии операционных систем. Поддерживаются только 32-разрядные версии Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="eb837-p108">32-bit or 64-bit versions of the operating systems are supported. Only 32-bit versions of Internet Explorer are supported.</span></span>



</div>

### <a name="supported-operating-systems-and-web-browsers"></a><span data-ttu-id="eb837-168">Поддерживаемые операционные системы и веб-браузеры</span><span class="sxs-lookup"><span data-stu-id="eb837-168">Supported Operating Systems and Web Browsers</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="eb837-169">Операционная система</span><span class="sxs-lookup"><span data-stu-id="eb837-169">Operating system</span></span></th>
<th><span data-ttu-id="eb837-170">Веб-браузер</span><span class="sxs-lookup"><span data-stu-id="eb837-170">Web browser</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="eb837-171">Windows Vista с пакетом обновления 2 (SP2)</span><span class="sxs-lookup"><span data-stu-id="eb837-171">Windows Vista with Service Pack (SP) 2</span></span></p></td>
<td><p><span data-ttu-id="eb837-172">Internet Explorer 7</span><span class="sxs-lookup"><span data-stu-id="eb837-172">Internet Explorer 7</span></span></p>
<p><span data-ttu-id="eb837-173">Internet Explorer 8 (основной режим)</span><span class="sxs-lookup"><span data-stu-id="eb837-173">Internet Explorer 8 (native mode)</span></span></p>
<p><span data-ttu-id="eb837-174">Internet Explorer 9 (основной режим)</span><span class="sxs-lookup"><span data-stu-id="eb837-174">Internet Explorer 9 (native mode)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eb837-175">Windows 7</span><span class="sxs-lookup"><span data-stu-id="eb837-175">Windows 7</span></span></p>
<p><span data-ttu-id="eb837-176">Windows 7 с пакетом обновления 1 (SP1)</span><span class="sxs-lookup"><span data-stu-id="eb837-176">Windows 7 with Service Pack 1</span></span></p></td>
<td><p><span data-ttu-id="eb837-177">Internet Explorer 8 (основной режим)</span><span class="sxs-lookup"><span data-stu-id="eb837-177">Internet Explorer 8 (native mode)</span></span></p>
<p><span data-ttu-id="eb837-178">Internet Explorer 9 (основной режим)</span><span class="sxs-lookup"><span data-stu-id="eb837-178">Internet Explorer 9 (native mode)</span></span></p>
<p><span data-ttu-id="eb837-179">Firefox 10.0</span><span class="sxs-lookup"><span data-stu-id="eb837-179">Firefox 10.0</span></span></p>
<p><span data-ttu-id="eb837-180">Chrome 18.0</span><span class="sxs-lookup"><span data-stu-id="eb837-180">Chrome 18.0</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eb837-181">Windows Server 2008 с пакетом обновления 2 (SP2)</span><span class="sxs-lookup"><span data-stu-id="eb837-181">Windows Server 2008 with Service Pack 2</span></span></p></td>
<td><p><span data-ttu-id="eb837-182">Internet Explorer 7</span><span class="sxs-lookup"><span data-stu-id="eb837-182">Internet Explorer 7</span></span></p>
<p><span data-ttu-id="eb837-183">Internet Explorer 8 (основной режим)</span><span class="sxs-lookup"><span data-stu-id="eb837-183">Internet Explorer 8 (native mode)</span></span></p>
<p><span data-ttu-id="eb837-184">Internet Explorer 9 (основной режим)</span><span class="sxs-lookup"><span data-stu-id="eb837-184">Internet Explorer 9 (native mode)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eb837-185">Windows Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="eb837-185">Windows Server 2008 R2</span></span></p>
<p><span data-ttu-id="eb837-186">Windows Server 2008 R2 с пакетом обновления 1 (SP1)</span><span class="sxs-lookup"><span data-stu-id="eb837-186">Windows Server 2008 R2 with Service Pack 1</span></span></p></td>
<td><p><span data-ttu-id="eb837-187">Internet Explorer 8 (основной режим)</span><span class="sxs-lookup"><span data-stu-id="eb837-187">Internet Explorer 8 (native mode)</span></span></p>
<p><span data-ttu-id="eb837-188">Internet Explorer 9 (основной режим)</span><span class="sxs-lookup"><span data-stu-id="eb837-188">Internet Explorer 9 (native mode)</span></span></p>
<p><span data-ttu-id="eb837-189">Firefox 10.0</span><span class="sxs-lookup"><span data-stu-id="eb837-189">Firefox 10.0</span></span></p>
<p><span data-ttu-id="eb837-190">Chrome 18.0</span><span class="sxs-lookup"><span data-stu-id="eb837-190">Chrome 18.0</span></span></p></td>
</tr>
<tr class="odd">
<td></td>
<td></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

