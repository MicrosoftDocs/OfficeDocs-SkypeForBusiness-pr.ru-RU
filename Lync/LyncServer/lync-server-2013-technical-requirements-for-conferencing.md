---
title: 'Lync Server 2013: технические требования для проведения конференций'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Technical requirements for conferencing
ms:assetid: 3c0d89e1-53e6-46d7-bf8c-491260b292ea
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425889(v=OCS.15)
ms:contentKeyID: 48183923
ms.date: 06/26/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3a275836b940cfe2c56b184d238bc12c432132e6
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41746599"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="technical-requirements-for-conferencing-in-lync-server-2013"></a><span data-ttu-id="a0431-102">Технические требования для проведения конференций в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a0431-102">Technical requirements for conferencing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a0431-103">_**Тема последнего изменения:** 2014-06-25_</span><span class="sxs-lookup"><span data-stu-id="a0431-103">_**Topic Last Modified:** 2014-06-25_</span></span>

<span data-ttu-id="a0431-104">Для Lync Server 2013, Конференц-связь с телефонным подключением, Конференции и конференции с возможностью обмена мгновенными сообщениями и веб-конференций всегда работают на серверах переднего плана.</span><span class="sxs-lookup"><span data-stu-id="a0431-104">For Lync Server 2013, dial-in conferencing, A/V conferencing, instant messaging (IM) conferencing and web conferencing capabilities always run on Front End Servers.</span></span>

<span data-ttu-id="a0431-105">В этом разделе описаны требования к оборудованию и программному обеспечению для этих серверов, а также поддерживаемое расчисление.</span><span class="sxs-lookup"><span data-stu-id="a0431-105">This section details the hardware and software requirements for these servers, along with the supported collocation.</span></span>

<span data-ttu-id="a0431-106">Конференц-связь с телефонным подключением — это функция, которая включает в себя множество компонентов.</span><span class="sxs-lookup"><span data-stu-id="a0431-106">Dial-in conferencing is a feature that includes a variety of components.</span></span> <span data-ttu-id="a0431-107">Некоторые компоненты относятся к конференц-связи с телефонным подключением, а некоторые – к корпоративным голосовым компонентам.</span><span class="sxs-lookup"><span data-stu-id="a0431-107">Some of the components are specific to dial-in conferencing and some are Enterprise Voice components.</span></span> <span data-ttu-id="a0431-108">В этом разделе описаны требования для компонентов, которые относятся к конференц-связи с телефонным подключением.</span><span class="sxs-lookup"><span data-stu-id="a0431-108">This section describes the requirements for the components that are specific to dial-in conferencing.</span></span> <span data-ttu-id="a0431-109">Подробные сведения о требованиях к шлюзам и протоколам PSTN можно найти в разделе сервер- [посредника в Lync server 2013](lync-server-2013-mediation-server-component.md) и [компонентах и топологиях для сервера-посредника в Lync Server 2013](lync-server-2013-components-and-topologies-for-mediation-server.md) в документации по планированию.</span><span class="sxs-lookup"><span data-stu-id="a0431-109">For details about Mediation Server and public switched telephone network (PSTN) gateway requirements, see [Mediation Server component in Lync Server 2013](lync-server-2013-mediation-server-component.md) and [Components and topologies for Mediation Server in Lync Server 2013](lync-server-2013-components-and-topologies-for-mediation-server.md) in the Planning documentation.</span></span>

<div>

## <a name="hardware-requirements"></a><span data-ttu-id="a0431-110">Требования к оборудованию</span><span class="sxs-lookup"><span data-stu-id="a0431-110">Hardware Requirements</span></span>

<span data-ttu-id="a0431-111">Поскольку веб-конференции и конференции/V образныеся на сервере переднего плана, требования к оборудованию сервера такие же, как и для серверов переднего плана.</span><span class="sxs-lookup"><span data-stu-id="a0431-111">Because web conferencing and A/V conferencing are collocated with the Front End Server, the server hardware requirements are the same as for the Front End Servers.</span></span> <span data-ttu-id="a0431-112">Сведения о требованиях к оборудованию можно найти в документации [серверные платформы для Lync server 2013](lync-server-2013-server-hardware-platforms.md) .</span><span class="sxs-lookup"><span data-stu-id="a0431-112">For details about hardware requirements, see [Server hardware platforms for Lync Server 2013](lync-server-2013-server-hardware-platforms.md) in the Supportability documentation.</span></span> <span data-ttu-id="a0431-113">Следующие компоненты, необходимые для конференц-связи с телефонным подключением, также имеют те же аппаратные требования, что и сервер переднего плана:</span><span class="sxs-lookup"><span data-stu-id="a0431-113">The following components required for dial-in conferencing also have the same hardware requirements as Front End Servers:</span></span>

  - <span data-ttu-id="a0431-114">приложения</span><span class="sxs-lookup"><span data-stu-id="a0431-114">Application service</span></span>

  - <span data-ttu-id="a0431-115">помощника по конференц-связи</span><span class="sxs-lookup"><span data-stu-id="a0431-115">Conferencing Attendant application</span></span>

  - <span data-ttu-id="a0431-116">приложение оповещения для конференц-связи;</span><span class="sxs-lookup"><span data-stu-id="a0431-116">Conferencing Announcement application</span></span>

<span data-ttu-id="a0431-117">Требования к оборудованию для сервера переднего плана одинаковы для многих других ролей сервера в Lync Server 2013, описанные в таблице ниже.</span><span class="sxs-lookup"><span data-stu-id="a0431-117">The hardware requirements for Front End Server are the same as for many other server roles in Lync Server 2013 are outlined in the following table.</span></span>

</div>

<div>

## <a name="software-requirements"></a><span data-ttu-id="a0431-118">Требования к программному обеспечению</span><span class="sxs-lookup"><span data-stu-id="a0431-118">Software Requirements</span></span>

<span data-ttu-id="a0431-119">Поскольку веб-конференции и конференции/V образныеся на сервере переднего плана, требования к программному обеспечению сервера совпадают с серверами переднего плана.</span><span class="sxs-lookup"><span data-stu-id="a0431-119">Because web conferencing and A/V conferencing are collocated with the Front End Server, the server software requirements are the same as for the Front End Servers.</span></span> <span data-ttu-id="a0431-120">Подробные сведения о требованиях к программному обеспечению можно найти [в разделе Поддержка серверов и средств операционной системы в Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md) в документации по поддержке.</span><span class="sxs-lookup"><span data-stu-id="a0431-120">For details about software requirements, see [Server and tools operating system support in Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md) in the Supportability documentation.</span></span>

<span data-ttu-id="a0431-121">Для веб-конференций в Lync Server 2013 также требуется Office Web Apps и сервер Office Web Apps (прежнее название — сервер ВАК) для обработки презентаций PowerPoint.</span><span class="sxs-lookup"><span data-stu-id="a0431-121">For web conferencing, Lync Server 2013 also requires Office Web Apps and the Office Web Apps Server (formerly known as WAC Server) to handle PowerPoint presentations.</span></span> <span data-ttu-id="a0431-122">Подробности можно найти [в разделе Настройка интеграции с Office Web Apps Server и Lync Server 2013](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md).</span><span class="sxs-lookup"><span data-stu-id="a0431-122">For details, see [Configuring integration with Office Web Apps Server and Lync Server 2013](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md).</span></span>

<span data-ttu-id="a0431-123">Для конференц-связи с телефонным подключением службы приложений, приложения для участников Конференции и объявления конференций имеют те же требования к операционной системе, что и серверы переднего плана.</span><span class="sxs-lookup"><span data-stu-id="a0431-123">For dial-in conferencing, Application service, Conferencing Attendant application, and Conferencing Announcement application have the same operating system requirements as Front End Servers.</span></span> <span data-ttu-id="a0431-124">Подробные сведения о требованиях к программному обеспечению можно найти [в разделе Поддержка серверов и средств операционной системы в Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md) в документации по поддержке.</span><span class="sxs-lookup"><span data-stu-id="a0431-124">For details about software requirements, see [Server and tools operating system support in Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md) in the Supportability documentation.</span></span>

<span data-ttu-id="a0431-125">Приложение для рекламы в конференц-связи с приложениями и конференц-связь требуется, чтобы на серверах переднего плана была установлена среда выполнения формата Windows Media Format.</span><span class="sxs-lookup"><span data-stu-id="a0431-125">Conferencing Attendant application and Conferencing Announcement application require that Windows Media Format Runtime is installed on Front End Servers.</span></span> <span data-ttu-id="a0431-126">Среда выполнения формата Windows Media требуется для воспроизведения WMA-файлов, которые используются для музыки на удержании, записанных имен и запросов.</span><span class="sxs-lookup"><span data-stu-id="a0431-126">The Windows Media Format Runtime is required to play Windows Media audio (WMA) files that are used for music on hold, recorded names, and prompts.</span></span> <span data-ttu-id="a0431-127">За исключением Windows Server 2012 и Windows Server 2012 R2, среда выполнения формата Windows Media устанавливается автоматически как часть рабочего стола Windows при запуске программы установки, но вам может потребоваться перезагрузить компьютер.</span><span class="sxs-lookup"><span data-stu-id="a0431-127">Except for Windows Server 2012 and Windows Server 2012 R2, the Windows Media Format Runtime is installed automatically as part of the Windows Desktop Experience when you run Setup, but you might need to restart the computer.</span></span> <span data-ttu-id="a0431-128">Поэтому мы рекомендуем установить в качестве части рабочего стола Windows, которая включает в себя среду выполнения формата Windows Media, прежде чем запускать программу установки.</span><span class="sxs-lookup"><span data-stu-id="a0431-128">Therefore, we recommend that you install as part of the Windows Desktop Experience, which includes Windows Media Format Runtime before you run Setup.</span></span> <span data-ttu-id="a0431-129">Для Windows Server 2012 и Windows Server 2012 R2 требуется Microsoft Media Foundation.</span><span class="sxs-lookup"><span data-stu-id="a0431-129">Windows Server 2012 and Windows Server 2012 R2 requires Microsoft Media Foundation.</span></span>

</div>

<div>

## <a name="port-requirements-for-dial-in-conferencing"></a><span data-ttu-id="a0431-130">Требования к портам для конференц-связи с телефонным подключением</span><span class="sxs-lookup"><span data-stu-id="a0431-130">Port Requirements for dial-in conferencing</span></span>

<span data-ttu-id="a0431-131">В таблице ниже описаны порты, которые используются в конференц-связи с телефонным подключением.</span><span class="sxs-lookup"><span data-stu-id="a0431-131">The following table describes the ports that are used by dial-in conferencing.</span></span> <span data-ttu-id="a0431-132">Если вы используете подсистему балансировки нагрузки, убедитесь в том, что подсистема балансировки нагрузки настроена для портов, используемых приложениями, которые будут выполняться в пуле.</span><span class="sxs-lookup"><span data-stu-id="a0431-132">If you use a load balancer, ensure that the load balancer is configured for the ports used by any applications that will run in the pool.</span></span>

<span data-ttu-id="a0431-133">Эти порты являются установками по умолчанию, которые можно изменить с помощью командлета **Set-CsApplicationServer**.</span><span class="sxs-lookup"><span data-stu-id="a0431-133">These ports are default settings that you can change by using the **Set-CsApplicationServer** cmdlet.</span></span> <span data-ttu-id="a0431-134">Подробные сведения об этом командлете можно найти в документации по оболочке Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="a0431-134">For details about this cmdlet, see the Lync Server Management Shell documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="a0431-135">Все экземпляры одного и того же приложения в пуле используют один и тот же прослушивающий порт SIP.</span><span class="sxs-lookup"><span data-stu-id="a0431-135">All instances of the same application in a pool use the same SIP listening port.</span></span>



</div>

### <a name="ports-used-by-dial-in-conferencing"></a><span data-ttu-id="a0431-136">Порты, используемые в конференц-связи с телефонным подключением</span><span class="sxs-lookup"><span data-stu-id="a0431-136">Ports used by dial-in conferencing</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a0431-137">Номер порта</span><span class="sxs-lookup"><span data-stu-id="a0431-137">Port number</span></span></th>
<th><span data-ttu-id="a0431-138">Описание</span><span class="sxs-lookup"><span data-stu-id="a0431-138">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a0431-139">5072</span><span class="sxs-lookup"><span data-stu-id="a0431-139">5072</span></span></p></td>
<td><p><span data-ttu-id="a0431-140">Используется приложением-помощником по конференциям для запросов прослушивания SIP</span><span class="sxs-lookup"><span data-stu-id="a0431-140">Used by Conferencing Attendant application for SIP listening requests</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a0431-141">5073</span><span class="sxs-lookup"><span data-stu-id="a0431-141">5073</span></span></p></td>
<td><p><span data-ttu-id="a0431-142">Используется приложением объявления конференций для запросов прослушивания SIP</span><span class="sxs-lookup"><span data-stu-id="a0431-142">Used by Conferencing Announcement application for SIP listening requests</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="supported-clients-for-dial-in-conferencing"></a><span data-ttu-id="a0431-143">Поддерживаемые клиенты для конференц-связи с телефонным подключением</span><span class="sxs-lookup"><span data-stu-id="a0431-143">Supported Clients for Dial-In Conferencing</span></span>

<span data-ttu-id="a0431-144">Вы можете использовать следующий клиент для планирования локальных конференций, поддерживающих доступ к телефонным подключениям:</span><span class="sxs-lookup"><span data-stu-id="a0431-144">You can use the following client to schedule on-premises conferences that support dial-in access:</span></span>

  - <span data-ttu-id="a0431-145">Надстройка "собрание по сети" для Lync 2013 (устанавливается автоматически при установке Lync 2013 или участник)</span><span class="sxs-lookup"><span data-stu-id="a0431-145">Online Meeting Add-in for Lync 2013 (installed automatically when you install Lync 2013 or Attendee)</span></span>

</div>

<div>

## <a name="dial-in-conferencing-settings-page-requirements"></a><span data-ttu-id="a0431-146">Требования к странице параметров конференц-связи с телефонным подключением</span><span class="sxs-lookup"><span data-stu-id="a0431-146">Dial-in Conferencing Settings page Requirements</span></span>

<span data-ttu-id="a0431-147">Страница параметров конференц-связи с телефонным подключением поддерживает комбинации операционных систем и веб-браузеров, описанные в приведенной ниже таблице.</span><span class="sxs-lookup"><span data-stu-id="a0431-147">The Dial-in Conferencing Settings page supports the combinations of operating systems and web browsers described in the following table.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="a0431-148">поддерживаются 32-разрядные и 64-разрядные версии операционной системы.</span><span class="sxs-lookup"><span data-stu-id="a0431-148">32-bit and 64-bit versions of the operating systems are supported.</span></span>



</div>

### <a name="supported-operating-systems-and-web-browsers"></a><span data-ttu-id="a0431-149">Поддерживаемые операционные системы и веб-браузеры</span><span class="sxs-lookup"><span data-stu-id="a0431-149">Supported Operating Systems and Web Browsers</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a0431-150">Операционная система</span><span class="sxs-lookup"><span data-stu-id="a0431-150">Operating system</span></span></th>
<th><span data-ttu-id="a0431-151">Веб-браузер</span><span class="sxs-lookup"><span data-stu-id="a0431-151">Web browser</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a0431-152">Windows 7</span><span class="sxs-lookup"><span data-stu-id="a0431-152">Windows 7</span></span></p></td>
<td><p><span data-ttu-id="a0431-153">Internet Explorer 9</span><span class="sxs-lookup"><span data-stu-id="a0431-153">Internet Explorer 9</span></span></p>
<p><span data-ttu-id="a0431-154">Internet Explorer 8</span><span class="sxs-lookup"><span data-stu-id="a0431-154">Internet Explorer 8</span></span></p>
<p><span data-ttu-id="a0431-155">Браузере</span><span class="sxs-lookup"><span data-stu-id="a0431-155">Firefox</span></span></p></td>
</tr>
<tr class="even">
<td> </td>
<td> </td>
</tr>
<tr class="odd">
<td> </td>
<td> </td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a0431-156">Windows Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="a0431-156">Windows Server 2008 R2</span></span></p></td>
<td><p><span data-ttu-id="a0431-157">Internet Explorer 9</span><span class="sxs-lookup"><span data-stu-id="a0431-157">Internet Explorer 9</span></span></p>
<p><span data-ttu-id="a0431-158">Internet Explorer 8</span><span class="sxs-lookup"><span data-stu-id="a0431-158">Internet Explorer 8</span></span></p>
<p><span data-ttu-id="a0431-159">Internet Explorer 7</span><span class="sxs-lookup"><span data-stu-id="a0431-159">Internet Explorer 7</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a0431-160">Mac OS</span><span class="sxs-lookup"><span data-stu-id="a0431-160">Mac OS</span></span></p></td>
<td><p><span data-ttu-id="a0431-161">Браузере</span><span class="sxs-lookup"><span data-stu-id="a0431-161">Firefox</span></span></p>
<p><span data-ttu-id="a0431-162">Обозревателе</span><span class="sxs-lookup"><span data-stu-id="a0431-162">Safari</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="audio-file-requirements-for-dial-in-conferencing"></a><span data-ttu-id="a0431-163">Требования к звуковым файлам для конференц-связи с телефонным подключением</span><span class="sxs-lookup"><span data-stu-id="a0431-163">Audio File Requirements for dial-in conferencing</span></span>

<span data-ttu-id="a0431-164">Lync Server 2013 не поддерживает настройку голосовых запросов и музыки для конференц-связи с телефонным подключением.</span><span class="sxs-lookup"><span data-stu-id="a0431-164">Lync Server 2013 does not support customization of voice prompts and music for dial-in conferencing.</span></span> <span data-ttu-id="a0431-165">Тем не менее, если вам нужно изменить аудиофайлы по умолчанию, ознакомьтесь со статьей Microsoft Knowledge Base 961177, [Настройка голосовых запросов и музыкальных файлов для голосовой связи с телефонным подключением в Microsoft Office Communications Server 2007 R2](http://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=961177).</span><span class="sxs-lookup"><span data-stu-id="a0431-165">However, if you have a strong business need that requires you to change the default audio files, see Microsoft Knowledge Base article 961177, [How to customize voice prompts or music files for dial-in audio conferencing in Microsoft Office Communications Server 2007 R2](http://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=961177).</span></span>

<span data-ttu-id="a0431-166">Вы также можете использовать служебную программу [помощника по конференциям Microsoft Lync Server](http://go.microsoft.com/fwlink/p/?linkid=396880) , которая позволяет администраторам заменить голосовые запросы, используемые по умолчанию при присоединении к собранию Lync с помощью настраиваемых запросов, для предоставления другим пользователям возможности ввода собраний.</span><span class="sxs-lookup"><span data-stu-id="a0431-166">You can also use the [Microsoft Lync Server Conferencing Attendant Custom Voice Prompts](http://go.microsoft.com/fwlink/p/?linkid=396880) management utility, which enables administrators to replace the default voice prompts used when a phone caller joins a Lync meeting with custom prompts to provide a different meeting entry experience.</span></span> <span data-ttu-id="a0431-167">Пользовательские голосовые подсказки можно установить на сервер, на котором установлен Lync Server 2010 или Lync Server 2013 либо Enterprise, либо Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="a0431-167">The custom voice prompts can be installed on a server that is running Lync Server 2010 or Lync Server 2013, either Enterprise or Standard Edition.</span></span>

<span data-ttu-id="a0431-168">Участие в программе для конференц-связи с приложениями и конференциями для музыки на удержании, записанных именах и файлах звуковых файлов не имеет приведенных ниже требований.</span><span class="sxs-lookup"><span data-stu-id="a0431-168">Conferencing Attendant application and Conferencing Announcement application have the following requirements for music on hold, recorded name, and audio prompt files:</span></span>

  - <span data-ttu-id="a0431-169">Формат файлов WMA (Windows Media Audio)</span><span class="sxs-lookup"><span data-stu-id="a0431-169">Windows Media Audio (WMA) file format</span></span>

  - <span data-ttu-id="a0431-170">Моно 16 бит</span><span class="sxs-lookup"><span data-stu-id="a0431-170">16-bit mono</span></span>

  - <span data-ttu-id="a0431-171">48 Кбит/с, 2 прохода, CBR (постоянная скорость)</span><span class="sxs-lookup"><span data-stu-id="a0431-171">48 kbps 2-pass CBR (constant bit rate)</span></span>

  - <span data-ttu-id="a0431-172">Уровень речи на -24 дБ</span><span class="sxs-lookup"><span data-stu-id="a0431-172">Speech level at -24DB</span></span>

</div>

<div>

## <a name="user-requirements-for-dial-in-conferencing"></a><span data-ttu-id="a0431-173">Требования пользователей к конференц-связи с телефонным подключением</span><span class="sxs-lookup"><span data-stu-id="a0431-173">User Requirements for Dial-In Conferencing</span></span>

<span data-ttu-id="a0431-174">Учетным записям пользователей конференц-связи с телефонным подключением должны быть назначены уникальные номера телефонов или добавочные номера.</span><span class="sxs-lookup"><span data-stu-id="a0431-174">Dial-in conferencing users must have a unique phone number or extension assigned to their account.</span></span> <span data-ttu-id="a0431-175">Это необходимо для проверки подлинности во время конференц-связи с телефонным подключением.</span><span class="sxs-lookup"><span data-stu-id="a0431-175">This requirement supports authentication during dial-in conferencing.</span></span> <span data-ttu-id="a0431-176">Корпоративные пользователи (то есть пользователи, у которых есть учетные данные доменных служб Active Directory и учетные записи Lync Server в вашей организации) вводят номер телефона (или расширение) и персональный идентификационный номер (ПИН-код) для подключения к конференциям в виде пользователь, прошедший проверку подлинности.</span><span class="sxs-lookup"><span data-stu-id="a0431-176">Enterprise users (that is, users who have Active Directory Domain Services credentials and Lync Server accounts within your organization) enter their phone number (or extension) and a personal identification number (PIN) to dial in to conferences as an authenticated user.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

