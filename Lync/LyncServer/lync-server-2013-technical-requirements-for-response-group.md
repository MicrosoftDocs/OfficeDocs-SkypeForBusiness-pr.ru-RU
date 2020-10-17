---
title: 'Lync Server 2013: технические требования для группы ответа'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Technical requirements for Response Group
ms:assetid: 477488bd-124f-437b-9327-732a0d7271ca
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204863(v=OCS.15)
ms:contentKeyID: 48184044
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a0b06176a033c90ff915fccb145dac3b3ed6fe87
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48536126"
---
# <a name="technical-requirements-for-response-group-in-lync-server-2013"></a><span data-ttu-id="4a907-102">Технические требования для группы ответа в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4a907-102">Technical requirements for Response Group in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4a907-103">_**Последнее изменение темы:** 2013-11-07_</span><span class="sxs-lookup"><span data-stu-id="4a907-103">_**Topic Last Modified:** 2013-11-07_</span></span>

<span data-ttu-id="4a907-104">В этом разделе описываются следующие технические требования для приложения группы ответа.</span><span class="sxs-lookup"><span data-stu-id="4a907-104">This section describes the following technical requirements for the Response Group application:</span></span>

  - <span data-ttu-id="4a907-105">Требования к оборудованию</span><span class="sxs-lookup"><span data-stu-id="4a907-105">Hardware requirements</span></span>

  - <span data-ttu-id="4a907-106">Требования к программному обеспечению</span><span class="sxs-lookup"><span data-stu-id="4a907-106">Software requirements</span></span>

  - <span data-ttu-id="4a907-107">Требования к портам</span><span class="sxs-lookup"><span data-stu-id="4a907-107">Port requirements</span></span>

  - <span data-ttu-id="4a907-108">Требования к аудиофайлам</span><span class="sxs-lookup"><span data-stu-id="4a907-108">Audio file requirements</span></span>

  - <span data-ttu-id="4a907-109">Требования к средствам настройки группы ответа</span><span class="sxs-lookup"><span data-stu-id="4a907-109">Response Group configuration tool requirements</span></span>

<div>

## <a name="hardware-requirements"></a><span data-ttu-id="4a907-110">Требования к оборудованию</span><span class="sxs-lookup"><span data-stu-id="4a907-110">Hardware Requirements</span></span>

<span data-ttu-id="4a907-111">Приложение группы ответа имеет те же требования к оборудованию, что и серверы переднего плана.</span><span class="sxs-lookup"><span data-stu-id="4a907-111">The Response Group application has the same hardware requirements as Front End Servers.</span></span> <span data-ttu-id="4a907-112">Сведения о требованиях к оборудованию приведены в статье [Server Hardware Platforms for Lync server 2013](lync-server-2013-server-hardware-platforms.md) в документации по поддержке.</span><span class="sxs-lookup"><span data-stu-id="4a907-112">For details about hardware requirements, see [Server hardware platforms for Lync Server 2013](lync-server-2013-server-hardware-platforms.md) in the Supportability documentation.</span></span>

</div>

<div>

## <a name="software-requirements"></a><span data-ttu-id="4a907-113">Требования к программному обеспечению</span><span class="sxs-lookup"><span data-stu-id="4a907-113">Software Requirements</span></span>

<span data-ttu-id="4a907-114">Приложение группы ответа имеет те же требования к операционной системе и программное обеспечение, что и серверы переднего плана.</span><span class="sxs-lookup"><span data-stu-id="4a907-114">The Response Group application has the same operating system requirements and software prerequisites as Front End Servers.</span></span> <span data-ttu-id="4a907-115">Сведения о требованиях к программному обеспечению приведены в статье [Поддержка серверов и средств операционной системы в Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md) в документации по поддержке.</span><span class="sxs-lookup"><span data-stu-id="4a907-115">For details about software requirements, see [Server and tools operating system support in Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md) in the Supportability documentation.</span></span>

<span data-ttu-id="4a907-116">Если вы используете файлы Windows Media Audio (WMA) для музыкальных сообщений и оповещений для группы ответа, на всех серверах переднего плана или стандартных выпусках, на которых работает приложение группы ответа, должна быть установлена среда выполнения формата Windows Media для серверов под управлением Windows Server 2008 R2 или Microsoft Media Foundation для серверов под управлением Windows Server 2012 или Windows Server 2012 R2.</span><span class="sxs-lookup"><span data-stu-id="4a907-116">If you use Windows Media Audio (.wma) files for Response Group music and announcements, all Front End Servers or Standard Editions servers that run the Response Group application must have the Windows Media Format Runtime installed for servers running Windows Server 2008 R2, or Microsoft Media Foundation for servers running Windows Server 2012 or Windows Server 2012 R2.</span></span> <span data-ttu-id="4a907-117">Для Windows Server 2008 R2 среда выполнения формата Windows Media устанавливается в составе Windows Desktop Experience.</span><span class="sxs-lookup"><span data-stu-id="4a907-117">For Windows Server 2008 R2, Windows Media Format Runtime is installed as part of Windows Desktop Experience.</span></span>

<span data-ttu-id="4a907-118">Дополнительные сведения о требованиях к звуку см. ниже в подразделе "Требования к звуковым файлам".</span><span class="sxs-lookup"><span data-stu-id="4a907-118">For more details about audio requirements, see "Audio File Requirements" later in this section.</span></span>

</div>

<div>

## <a name="port-requirements"></a><span data-ttu-id="4a907-119">Требования к портам</span><span class="sxs-lookup"><span data-stu-id="4a907-119">Port Requirements</span></span>

<span data-ttu-id="4a907-120">Приложение группы ответа использует следующие порты:</span><span class="sxs-lookup"><span data-stu-id="4a907-120">The Response Group application uses the following ports:</span></span>

  - <span data-ttu-id="4a907-121">**Порт 5071**     Используется для запросов прослушивания SIP</span><span class="sxs-lookup"><span data-stu-id="4a907-121">**Port 5071**   Used for SIP listening requests</span></span>

  - <span data-ttu-id="4a907-122">**Порт 8404**     Используется для межсерверной связи</span><span class="sxs-lookup"><span data-stu-id="4a907-122">**Port 8404**   Used for interserver communications</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="4a907-123">Этот порт используется для службы поиска и является обязательным при развертывании приложения группы ответа в пуле с несколькими серверами переднего плана.</span><span class="sxs-lookup"><span data-stu-id="4a907-123">This port is used for the Match Making service and is required when the Response Group application is deployed in a pool that has more than one Front End Server.</span></span>

    
    </div>

<div>


> [!NOTE]  
> <span data-ttu-id="4a907-124">Эти порты отражают параметры по умолчанию, которые вы можете изменить с помощью командлета <STRONG>Set-CsApplicationServer</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="4a907-124">These ports are default settings that you can change by using the <STRONG>Set-CsApplicationServer</STRONG> cmdlet.</span></span> <span data-ttu-id="4a907-125">Подробнее об этом командлете можно узнать в документации по командной консоли Lync Server.</span><span class="sxs-lookup"><span data-stu-id="4a907-125">For details about this cmdlet, see the Lync Server Management Shell documentation.</span></span>



</div>

</div>

<div>

## <a name="audio-file-requirements"></a><span data-ttu-id="4a907-126">Требования к аудиофайлам</span><span class="sxs-lookup"><span data-stu-id="4a907-126">Audio File Requirements</span></span>

<span data-ttu-id="4a907-127">Приложение группы ответа поддерживает формат WAV-файла и формат файлов Windows Media Audio (WMA) для сообщений группы ответа, музыки на удержании или ответов на интерактивные голосовые вызовы (IVR).</span><span class="sxs-lookup"><span data-stu-id="4a907-127">The Response Group application supports wave (.wav) file format and Windows Media audio (.wma) file format for Response Group messages, on-hold music, or interactive voice response (IVR) questions.</span></span>

<span data-ttu-id="4a907-128">Для формата файлов Windows Media требуется, чтобы среда выполнения формата Windows Media была установлена на серверах переднего плана под управлением Windows Server 2008 R2 и Windows Server 2008.</span><span class="sxs-lookup"><span data-stu-id="4a907-128">The Windows Media audio file format requires that the Windows Media Format Runtime is installed on Front End Servers running Windows Server 2008 R2 and Windows Server 2008.</span></span> <span data-ttu-id="4a907-129">Дополнительные сведения см. выше в подразделе "Требования к программному обеспечению".</span><span class="sxs-lookup"><span data-stu-id="4a907-129">For more details, see "Software Requirements" earlier in this section.</span></span>

<div>

## <a name="supported-wave-file-formats"></a><span data-ttu-id="4a907-130">Поддерживаемые форматы файлов WAV</span><span class="sxs-lookup"><span data-stu-id="4a907-130">Supported Wave File Formats</span></span>

<span data-ttu-id="4a907-131">Все файлы WAV должны удовлетворять следующим требованиям:</span><span class="sxs-lookup"><span data-stu-id="4a907-131">All wave files must meet the following requirements:</span></span>

  - <span data-ttu-id="4a907-132">8-разрядный или 16-разрядный файл</span><span class="sxs-lookup"><span data-stu-id="4a907-132">8-bit or 16-bit file</span></span>

  - <span data-ttu-id="4a907-133">Формат линейной импульсно-кодовой модуляции, A-Law или mu-Law</span><span class="sxs-lookup"><span data-stu-id="4a907-133">Linear pulse code modulation (LPCM), A-Law, or mu-Law format</span></span>

  - <span data-ttu-id="4a907-134">Моно или стерео</span><span class="sxs-lookup"><span data-stu-id="4a907-134">Mono or stereo</span></span>

  - <span data-ttu-id="4a907-135">4 МБ или меньше</span><span class="sxs-lookup"><span data-stu-id="4a907-135">4MB or less</span></span>

<span data-ttu-id="4a907-136">Для обеспечения наилучшей производительности файлов WAV рекомендуется использовать монофонический 16-разрядный файл WAV с частотой 16 кГц.</span><span class="sxs-lookup"><span data-stu-id="4a907-136">For the best performance of wave files, a 16 kHz, mono, 16-bit Wave file is recommended.</span></span>

</div>

<div>

## <a name="supported-windows-media-audio-file-formats"></a><span data-ttu-id="4a907-137">Поддерживаемые форматы файлов WMA</span><span class="sxs-lookup"><span data-stu-id="4a907-137">Supported Windows Media Audio File Formats</span></span>

<span data-ttu-id="4a907-138">Если вы используете файл WMA рекомендуется применять низкие скорости и проверить производительность системы под нагрузкой.</span><span class="sxs-lookup"><span data-stu-id="4a907-138">If you use a Windows Media audio file, consider using low bit rates, and verify the performance of your system under load.</span></span>

<span data-ttu-id="4a907-139">Преобразовать файл в формат WMA вы можете с помощью Microsoft Expression Encoder 4.</span><span class="sxs-lookup"><span data-stu-id="4a907-139">You can use the Microsoft Expression Encoder 4 to convert a file to the Windows Media Audio format.</span></span> <span data-ttu-id="4a907-140">Чтобы скачать Expression Encoder 4, ознакомьтесь со статьей [https://go.microsoft.com/fwlink/p/?linkId=202843](https://go.microsoft.com/fwlink/p/?linkid=202843) .</span><span class="sxs-lookup"><span data-stu-id="4a907-140">To download Expression Encoder 4, see [https://go.microsoft.com/fwlink/p/?linkId=202843](https://go.microsoft.com/fwlink/p/?linkid=202843).</span></span>

</div>

</div>

<div>

## <a name="response-group-configuration-tool-requirements"></a><span data-ttu-id="4a907-141">Требования к средствам настройки группы ответа</span><span class="sxs-lookup"><span data-stu-id="4a907-141">Response Group Configuration Tool Requirements</span></span>

<span data-ttu-id="4a907-142">Средство настройки группы ответа поддерживает сочетания операционных систем и веб-браузеров, описанные в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="4a907-142">The Response Group Configuration Tool supports the combinations of operating systems and web browsers described in the following table.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="4a907-p107">Поддерживаются 32-разрядная или 64-разрядная версии операционных систем. Поддерживаются только 32-разрядные версии Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="4a907-p107">32-bit or 64-bit versions of the operating systems are supported. Only 32-bit versions of Internet Explorer are supported.</span></span>



</div>

### <a name="supported-operating-systems-and-web-browsers"></a><span data-ttu-id="4a907-145">Поддерживаемые операционные системы и веб-браузеры</span><span class="sxs-lookup"><span data-stu-id="4a907-145">Supported Operating Systems and Web Browsers</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4a907-146">Операционная система</span><span class="sxs-lookup"><span data-stu-id="4a907-146">Operating system</span></span></th>
<th><span data-ttu-id="4a907-147">Веб-браузер</span><span class="sxs-lookup"><span data-stu-id="4a907-147">Web browser</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4a907-148">Windows Vista с пакетом обновления 2 (SP2)</span><span class="sxs-lookup"><span data-stu-id="4a907-148">Windows Vista with Service Pack (SP) 2</span></span></p></td>
<td><p><span data-ttu-id="4a907-149">Internet Explorer 7</span><span class="sxs-lookup"><span data-stu-id="4a907-149">Internet Explorer 7</span></span></p>
<p><span data-ttu-id="4a907-150">Internet Explorer 8 (основной режим)</span><span class="sxs-lookup"><span data-stu-id="4a907-150">Internet Explorer 8 (native mode)</span></span></p>
<p><span data-ttu-id="4a907-151">Internet Explorer 9 (основной режим)</span><span class="sxs-lookup"><span data-stu-id="4a907-151">Internet Explorer 9 (native mode)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4a907-152">Windows 7</span><span class="sxs-lookup"><span data-stu-id="4a907-152">Windows 7</span></span></p>
<p><span data-ttu-id="4a907-153">Windows 7 с пакетом обновления 1 (SP1)</span><span class="sxs-lookup"><span data-stu-id="4a907-153">Windows 7 with Service Pack 1</span></span></p></td>
<td><p><span data-ttu-id="4a907-154">Internet Explorer 8 (основной режим)</span><span class="sxs-lookup"><span data-stu-id="4a907-154">Internet Explorer 8 (native mode)</span></span></p>
<p><span data-ttu-id="4a907-155">Internet Explorer 9 (основной режим)</span><span class="sxs-lookup"><span data-stu-id="4a907-155">Internet Explorer 9 (native mode)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4a907-156">Windows Server 2008 с пакетом обновления 2 (SP2)</span><span class="sxs-lookup"><span data-stu-id="4a907-156">Windows Server 2008 with Service Pack 2</span></span></p></td>
<td><p><span data-ttu-id="4a907-157">Internet Explorer 7</span><span class="sxs-lookup"><span data-stu-id="4a907-157">Internet Explorer 7</span></span></p>
<p><span data-ttu-id="4a907-158">Internet Explorer 8 (основной режим)</span><span class="sxs-lookup"><span data-stu-id="4a907-158">Internet Explorer 8 (native mode)</span></span></p>
<p><span data-ttu-id="4a907-159">Internet Explorer 9 (основной режим)</span><span class="sxs-lookup"><span data-stu-id="4a907-159">Internet Explorer 9 (native mode)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4a907-160">Windows Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="4a907-160">Windows Server 2008 R2</span></span></p>
<p><span data-ttu-id="4a907-161">Windows Server 2008 R2 с пакетом обновления 1 (SP1)</span><span class="sxs-lookup"><span data-stu-id="4a907-161">Windows Server 2008 R2 with Service Pack 1</span></span></p></td>
<td><p><span data-ttu-id="4a907-162">Internet Explorer 8 (основной режим)</span><span class="sxs-lookup"><span data-stu-id="4a907-162">Internet Explorer 8 (native mode)</span></span></p>
<p><span data-ttu-id="4a907-163">Internet Explorer 9 (основной режим)</span><span class="sxs-lookup"><span data-stu-id="4a907-163">Internet Explorer 9 (native mode)</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="response-group-agent-console"></a><span data-ttu-id="4a907-164">Консоль агента группы ответа</span><span class="sxs-lookup"><span data-stu-id="4a907-164">Response Group Agent Console</span></span>

<span data-ttu-id="4a907-165">Консоль агента поддерживает сочетания операционной системы и веб-браузера, перечисленные в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="4a907-165">The agent console supports the combinations of operating systems and web browsers described in the following table.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="4a907-p108">Поддерживаются 32-разрядная или 64-разрядная версии операционных систем. Поддерживаются только 32-разрядные версии Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="4a907-p108">32-bit or 64-bit versions of the operating systems are supported. Only 32-bit versions of Internet Explorer are supported.</span></span>



</div>

### <a name="supported-operating-systems-and-web-browsers"></a><span data-ttu-id="4a907-168">Поддерживаемые операционные системы и веб-браузеры</span><span class="sxs-lookup"><span data-stu-id="4a907-168">Supported Operating Systems and Web Browsers</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4a907-169">Операционная система</span><span class="sxs-lookup"><span data-stu-id="4a907-169">Operating system</span></span></th>
<th><span data-ttu-id="4a907-170">Веб-браузер</span><span class="sxs-lookup"><span data-stu-id="4a907-170">Web browser</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4a907-171">Windows Vista с пакетом обновления 2 (SP2)</span><span class="sxs-lookup"><span data-stu-id="4a907-171">Windows Vista with Service Pack (SP) 2</span></span></p></td>
<td><p><span data-ttu-id="4a907-172">Internet Explorer 7</span><span class="sxs-lookup"><span data-stu-id="4a907-172">Internet Explorer 7</span></span></p>
<p><span data-ttu-id="4a907-173">Internet Explorer 8 (основной режим)</span><span class="sxs-lookup"><span data-stu-id="4a907-173">Internet Explorer 8 (native mode)</span></span></p>
<p><span data-ttu-id="4a907-174">Internet Explorer 9 (основной режим)</span><span class="sxs-lookup"><span data-stu-id="4a907-174">Internet Explorer 9 (native mode)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4a907-175">Windows 7</span><span class="sxs-lookup"><span data-stu-id="4a907-175">Windows 7</span></span></p>
<p><span data-ttu-id="4a907-176">Windows 7 с пакетом обновления 1 (SP1)</span><span class="sxs-lookup"><span data-stu-id="4a907-176">Windows 7 with Service Pack 1</span></span></p></td>
<td><p><span data-ttu-id="4a907-177">Internet Explorer 8 (основной режим)</span><span class="sxs-lookup"><span data-stu-id="4a907-177">Internet Explorer 8 (native mode)</span></span></p>
<p><span data-ttu-id="4a907-178">Internet Explorer 9 (основной режим)</span><span class="sxs-lookup"><span data-stu-id="4a907-178">Internet Explorer 9 (native mode)</span></span></p>
<p><span data-ttu-id="4a907-179">Firefox 10.0</span><span class="sxs-lookup"><span data-stu-id="4a907-179">Firefox 10.0</span></span></p>
<p><span data-ttu-id="4a907-180">Chrome 18.0</span><span class="sxs-lookup"><span data-stu-id="4a907-180">Chrome 18.0</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4a907-181">Windows Server 2008 с пакетом обновления 2 (SP2)</span><span class="sxs-lookup"><span data-stu-id="4a907-181">Windows Server 2008 with Service Pack 2</span></span></p></td>
<td><p><span data-ttu-id="4a907-182">Internet Explorer 7</span><span class="sxs-lookup"><span data-stu-id="4a907-182">Internet Explorer 7</span></span></p>
<p><span data-ttu-id="4a907-183">Internet Explorer 8 (основной режим)</span><span class="sxs-lookup"><span data-stu-id="4a907-183">Internet Explorer 8 (native mode)</span></span></p>
<p><span data-ttu-id="4a907-184">Internet Explorer 9 (основной режим)</span><span class="sxs-lookup"><span data-stu-id="4a907-184">Internet Explorer 9 (native mode)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4a907-185">Windows Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="4a907-185">Windows Server 2008 R2</span></span></p>
<p><span data-ttu-id="4a907-186">Windows Server 2008 R2 с пакетом обновления 1 (SP1)</span><span class="sxs-lookup"><span data-stu-id="4a907-186">Windows Server 2008 R2 with Service Pack 1</span></span></p></td>
<td><p><span data-ttu-id="4a907-187">Internet Explorer 8 (основной режим)</span><span class="sxs-lookup"><span data-stu-id="4a907-187">Internet Explorer 8 (native mode)</span></span></p>
<p><span data-ttu-id="4a907-188">Internet Explorer 9 (основной режим)</span><span class="sxs-lookup"><span data-stu-id="4a907-188">Internet Explorer 9 (native mode)</span></span></p>
<p><span data-ttu-id="4a907-189">Firefox 10.0</span><span class="sxs-lookup"><span data-stu-id="4a907-189">Firefox 10.0</span></span></p>
<p><span data-ttu-id="4a907-190">Chrome 18.0</span><span class="sxs-lookup"><span data-stu-id="4a907-190">Chrome 18.0</span></span></p></td>
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

