---
title: Lync Server 2013 технические требования для конференц-связи
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
ms.openlocfilehash: d28afb699b63ee3523c7b5d4ae31bf9153459abf
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48533946"
---
# <a name="technical-requirements-for-conferencing-in-lync-server-2013"></a><span data-ttu-id="e186a-102">Технические требования для конференц-связи в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e186a-102">Technical requirements for conferencing in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e186a-103">_**Последнее изменение темы:** 2014-06-25_</span><span class="sxs-lookup"><span data-stu-id="e186a-103">_**Topic Last Modified:** 2014-06-25_</span></span>

<span data-ttu-id="e186a-104">Для Lync Server 2013, конференц-связи с телефонным подключением, аудио-и видеоконференций, конференций обмена мгновенными сообщениями и веб-конференций всегда выполняются на серверах переднего плана.</span><span class="sxs-lookup"><span data-stu-id="e186a-104">For Lync Server 2013, dial-in conferencing, A/V conferencing, instant messaging (IM) conferencing and web conferencing capabilities always run on Front End Servers.</span></span>

<span data-ttu-id="e186a-105">В данном разделе рассматриваются требования к оборудованию и программному обеспечению для этих серверов, а также поддерживаемое выровненное размещение.</span><span class="sxs-lookup"><span data-stu-id="e186a-105">This section details the hardware and software requirements for these servers, along with the supported collocation.</span></span>

<span data-ttu-id="e186a-106">Конференц-связь с телефонным подключением это компонент, включающий множество компонентов.</span><span class="sxs-lookup"><span data-stu-id="e186a-106">Dial-in conferencing is a feature that includes a variety of components.</span></span> <span data-ttu-id="e186a-107">Некоторые компоненты относятся к конференц-связи с телефонным подключением, а некоторые — к корпоративным голосовым компонентам.</span><span class="sxs-lookup"><span data-stu-id="e186a-107">Some of the components are specific to dial-in conferencing and some are Enterprise Voice components.</span></span> <span data-ttu-id="e186a-108">В этом разделе описываются требования для компонентов, характерных для конференц-связи с телефонным подключением.</span><span class="sxs-lookup"><span data-stu-id="e186a-108">This section describes the requirements for the components that are specific to dial-in conferencing.</span></span> <span data-ttu-id="e186a-109">Для получения дополнительных сведений о требованиях к шлюзу для сервера-посредника и телефонной сети общего пользования (PSTN), просмотрите [компонент сервер-посредник в Lync server 2013](lync-server-2013-mediation-server-component.md) и [компоненты и топологии для сервера-посредника в среде Lync Server 2013](lync-server-2013-components-and-topologies-for-mediation-server.md) в документации по планированию.</span><span class="sxs-lookup"><span data-stu-id="e186a-109">For details about Mediation Server and public switched telephone network (PSTN) gateway requirements, see [Mediation Server component in Lync Server 2013](lync-server-2013-mediation-server-component.md) and [Components and topologies for Mediation Server in Lync Server 2013](lync-server-2013-components-and-topologies-for-mediation-server.md) in the Planning documentation.</span></span>

<div>

## <a name="hardware-requirements"></a><span data-ttu-id="e186a-110">Требования к оборудованию</span><span class="sxs-lookup"><span data-stu-id="e186a-110">Hardware Requirements</span></span>

<span data-ttu-id="e186a-111">Так как веб-конференции и аудио-и видеоконференции размещены вместе с сервером переднего плана, серверные требования к оборудованию одинаковы для серверов переднего плана.</span><span class="sxs-lookup"><span data-stu-id="e186a-111">Because web conferencing and A/V conferencing are collocated with the Front End Server, the server hardware requirements are the same as for the Front End Servers.</span></span> <span data-ttu-id="e186a-112">Сведения о требованиях к оборудованию приведены в статье [Server Hardware Platforms for Lync server 2013](lync-server-2013-server-hardware-platforms.md) в документации по поддержке.</span><span class="sxs-lookup"><span data-stu-id="e186a-112">For details about hardware requirements, see [Server hardware platforms for Lync Server 2013](lync-server-2013-server-hardware-platforms.md) in the Supportability documentation.</span></span> <span data-ttu-id="e186a-113">Следующие компоненты, необходимые для конференц-связи с телефонным подключением, также имеют те же требования к оборудованию, что и серверы переднего плана:</span><span class="sxs-lookup"><span data-stu-id="e186a-113">The following components required for dial-in conferencing also have the same hardware requirements as Front End Servers:</span></span>

  - <span data-ttu-id="e186a-114">служба приложения;</span><span class="sxs-lookup"><span data-stu-id="e186a-114">Application service</span></span>

  - <span data-ttu-id="e186a-115">приложение "Помощник по конференц-связи";</span><span class="sxs-lookup"><span data-stu-id="e186a-115">Conferencing Attendant application</span></span>

  - <span data-ttu-id="e186a-116">приложение "Объявления для конференц-связи";</span><span class="sxs-lookup"><span data-stu-id="e186a-116">Conferencing Announcement application</span></span>

<span data-ttu-id="e186a-117">Требования к оборудованию для сервера переднего плана те же, что и для многих других ролей серверов в Lync Server 2013, описанные в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="e186a-117">The hardware requirements for Front End Server are the same as for many other server roles in Lync Server 2013 are outlined in the following table.</span></span>

</div>

<div>

## <a name="software-requirements"></a><span data-ttu-id="e186a-118">Требования к программному обеспечению</span><span class="sxs-lookup"><span data-stu-id="e186a-118">Software Requirements</span></span>

<span data-ttu-id="e186a-119">Так как веб-конференции и аудио-и видеоконференции размещены вместе с сервером переднего плана, серверные требования к программному обеспечению одинаковы для серверов переднего плана.</span><span class="sxs-lookup"><span data-stu-id="e186a-119">Because web conferencing and A/V conferencing are collocated with the Front End Server, the server software requirements are the same as for the Front End Servers.</span></span> <span data-ttu-id="e186a-120">Сведения о требованиях к программному обеспечению приведены в статье [Поддержка серверов и средств операционной системы в Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md) в документации по поддержке.</span><span class="sxs-lookup"><span data-stu-id="e186a-120">For details about software requirements, see [Server and tools operating system support in Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md) in the Supportability documentation.</span></span>

<span data-ttu-id="e186a-121">Для веб-конференций Lync Server 2013 также требует Office Web Apps и сервера Office Web Apps (прежнее название — WAC Server) для обработки презентаций PowerPoint.</span><span class="sxs-lookup"><span data-stu-id="e186a-121">For web conferencing, Lync Server 2013 also requires Office Web Apps and the Office Web Apps Server (formerly known as WAC Server) to handle PowerPoint presentations.</span></span> <span data-ttu-id="e186a-122">Дополнительные сведения: [Настройка интеграции с сервером Office Web Apps и Lync Server 2013](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md).</span><span class="sxs-lookup"><span data-stu-id="e186a-122">For details, see [Configuring integration with Office Web Apps Server and Lync Server 2013](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md).</span></span>

<span data-ttu-id="e186a-123">Для конференц-связи с телефонным подключением, службы приложений, приложения "помощник по конференц-связи" и "объявление конференц-связи" для серверов переднего плана необходимы те же требования к операционной системе.</span><span class="sxs-lookup"><span data-stu-id="e186a-123">For dial-in conferencing, Application service, Conferencing Attendant application, and Conferencing Announcement application have the same operating system requirements as Front End Servers.</span></span> <span data-ttu-id="e186a-124">Сведения о требованиях к программному обеспечению приведены в статье [Поддержка серверов и средств операционной системы в Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md) в документации по поддержке.</span><span class="sxs-lookup"><span data-stu-id="e186a-124">For details about software requirements, see [Server and tools operating system support in Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md) in the Supportability documentation.</span></span>

<span data-ttu-id="e186a-125">Приложение "помощник по конференц-связи и конференц-связь" необходимо, чтобы на серверах переднего плана была установлена среда выполнения формата Windows Media.</span><span class="sxs-lookup"><span data-stu-id="e186a-125">Conferencing Attendant application and Conferencing Announcement application require that Windows Media Format Runtime is installed on Front End Servers.</span></span> <span data-ttu-id="e186a-126">Windows Media Format Runtime необходим для воспроизведения звуковых файлов Windows Media (WMA), используемых для музыки при удержании, записанных имен и запросов.</span><span class="sxs-lookup"><span data-stu-id="e186a-126">The Windows Media Format Runtime is required to play Windows Media audio (WMA) files that are used for music on hold, recorded names, and prompts.</span></span> <span data-ttu-id="e186a-127">За исключением Windows Server 2012 и Windows Server 2012 R2, среда выполнения формата Windows Media устанавливается автоматически в составе рабочего стола Windows при запуске программы установки, но может потребоваться перезагрузка компьютера.</span><span class="sxs-lookup"><span data-stu-id="e186a-127">Except for Windows Server 2012 and Windows Server 2012 R2, the Windows Media Format Runtime is installed automatically as part of the Windows Desktop Experience when you run Setup, but you might need to restart the computer.</span></span> <span data-ttu-id="e186a-128">Таким образом, перед запуском программы установки мы рекомендуем установить компонент «Возможности рабочего стола Windows», включающий в себя Windows Media Format Runtime.</span><span class="sxs-lookup"><span data-stu-id="e186a-128">Therefore, we recommend that you install as part of the Windows Desktop Experience, which includes Windows Media Format Runtime before you run Setup.</span></span> <span data-ttu-id="e186a-129">Для Windows Server 2012 и Windows Server 2012 R2 требуется Microsoft Media Foundation.</span><span class="sxs-lookup"><span data-stu-id="e186a-129">Windows Server 2012 and Windows Server 2012 R2 requires Microsoft Media Foundation.</span></span>

</div>

<div>

## <a name="port-requirements-for-dial-in-conferencing"></a><span data-ttu-id="e186a-130">Требования к портам для конференц-связи с телефонным подключением</span><span class="sxs-lookup"><span data-stu-id="e186a-130">Port Requirements for dial-in conferencing</span></span>

<span data-ttu-id="e186a-p107">В следующей таблице описываются порты, используемые конференц-связью с телефонным подключением. Если вы используете подсистему балансировки нагрузки, убедитесь, что она настроена для портов, используемых любым из приложений, которые выполняются в пуле.</span><span class="sxs-lookup"><span data-stu-id="e186a-p107">The following table describes the ports that are used by dial-in conferencing. If you use a load balancer, ensure that the load balancer is configured for the ports used by any applications that will run in the pool.</span></span>

<span data-ttu-id="e186a-133">Эти порты отражают параметры по умолчанию, которые вы можете изменить с помощью командлета **Set-CsApplicationServer**.</span><span class="sxs-lookup"><span data-stu-id="e186a-133">These ports are default settings that you can change by using the **Set-CsApplicationServer** cmdlet.</span></span> <span data-ttu-id="e186a-134">Подробнее об этом командлете можно узнать в документации по командной консоли Lync Server.</span><span class="sxs-lookup"><span data-stu-id="e186a-134">For details about this cmdlet, see the Lync Server Management Shell documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="e186a-135">Все экземпляры одного приложения в пуле используют один прослушивающий порт SIP.</span><span class="sxs-lookup"><span data-stu-id="e186a-135">All instances of the same application in a pool use the same SIP listening port.</span></span>



</div>

### <a name="ports-used-by-dial-in-conferencing"></a><span data-ttu-id="e186a-136">Порты, используемые для конференц-связи с телефонным подключением</span><span class="sxs-lookup"><span data-stu-id="e186a-136">Ports used by dial-in conferencing</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e186a-137">Номер порта</span><span class="sxs-lookup"><span data-stu-id="e186a-137">Port number</span></span></th>
<th><span data-ttu-id="e186a-138">Описание</span><span class="sxs-lookup"><span data-stu-id="e186a-138">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e186a-139">5072</span><span class="sxs-lookup"><span data-stu-id="e186a-139">5072</span></span></p></td>
<td><p><span data-ttu-id="e186a-140">Используется приложением помощника по конференц-связи для запросов прослушивания SIP</span><span class="sxs-lookup"><span data-stu-id="e186a-140">Used by Conferencing Attendant application for SIP listening requests</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e186a-141">5073</span><span class="sxs-lookup"><span data-stu-id="e186a-141">5073</span></span></p></td>
<td><p><span data-ttu-id="e186a-142">Используется приложением объявления конференц-связи для запросов прослушивания SIP</span><span class="sxs-lookup"><span data-stu-id="e186a-142">Used by Conferencing Announcement application for SIP listening requests</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="supported-clients-for-dial-in-conferencing"></a><span data-ttu-id="e186a-143">Поддерживаемые клиенты для конференц-связи с телефонным подключением</span><span class="sxs-lookup"><span data-stu-id="e186a-143">Supported Clients for Dial-In Conferencing</span></span>

<span data-ttu-id="e186a-144">Вы можете использовать следующие клиенты для планирования локальных конференций, поддерживающих доступ с телефонным подключением:</span><span class="sxs-lookup"><span data-stu-id="e186a-144">You can use the following client to schedule on-premises conferences that support dial-in access:</span></span>

  - <span data-ttu-id="e186a-145">Надстройка "собрание по сети" для Lync 2013 (устанавливается автоматически при установке Lync 2013 или участник)</span><span class="sxs-lookup"><span data-stu-id="e186a-145">Online Meeting Add-in for Lync 2013 (installed automatically when you install Lync 2013 or Attendee)</span></span>

</div>

<div>

## <a name="dial-in-conferencing-settings-page-requirements"></a><span data-ttu-id="e186a-146">Требования к странице параметров конференц-связи с телефонным подключением</span><span class="sxs-lookup"><span data-stu-id="e186a-146">Dial-in Conferencing Settings page Requirements</span></span>

<span data-ttu-id="e186a-147">Страница параметров конференц-связи с телефонным подключением поддерживает сочетания операционных систем и веб-браузеров, описанные в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="e186a-147">The Dial-in Conferencing Settings page supports the combinations of operating systems and web browsers described in the following table.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="e186a-148">32-разрядные и 64-разрядные версии операционных систем поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="e186a-148">32-bit and 64-bit versions of the operating systems are supported.</span></span>



</div>

### <a name="supported-operating-systems-and-web-browsers"></a><span data-ttu-id="e186a-149">Поддерживаемые операционные системы и браузеры</span><span class="sxs-lookup"><span data-stu-id="e186a-149">Supported Operating Systems and Web Browsers</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e186a-150">Операционная система</span><span class="sxs-lookup"><span data-stu-id="e186a-150">Operating system</span></span></th>
<th><span data-ttu-id="e186a-151">Веб-браузер</span><span class="sxs-lookup"><span data-stu-id="e186a-151">Web browser</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e186a-152">Windows 7</span><span class="sxs-lookup"><span data-stu-id="e186a-152">Windows 7</span></span></p></td>
<td><p><span data-ttu-id="e186a-153">Internet Explorer 9</span><span class="sxs-lookup"><span data-stu-id="e186a-153">Internet Explorer 9</span></span></p>
<p><span data-ttu-id="e186a-154">Internet Explorer 8</span><span class="sxs-lookup"><span data-stu-id="e186a-154">Internet Explorer 8</span></span></p>
<p><span data-ttu-id="e186a-155">Firefox</span><span class="sxs-lookup"><span data-stu-id="e186a-155">Firefox</span></span></p></td>
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
<td><p><span data-ttu-id="e186a-156">Windows Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="e186a-156">Windows Server 2008 R2</span></span></p></td>
<td><p><span data-ttu-id="e186a-157">Internet Explorer 9</span><span class="sxs-lookup"><span data-stu-id="e186a-157">Internet Explorer 9</span></span></p>
<p><span data-ttu-id="e186a-158">Internet Explorer 8</span><span class="sxs-lookup"><span data-stu-id="e186a-158">Internet Explorer 8</span></span></p>
<p><span data-ttu-id="e186a-159">Internet Explorer 7</span><span class="sxs-lookup"><span data-stu-id="e186a-159">Internet Explorer 7</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e186a-160">Mac OS</span><span class="sxs-lookup"><span data-stu-id="e186a-160">Mac OS</span></span></p></td>
<td><p><span data-ttu-id="e186a-161">Firefox</span><span class="sxs-lookup"><span data-stu-id="e186a-161">Firefox</span></span></p>
<p><span data-ttu-id="e186a-162">Safari</span><span class="sxs-lookup"><span data-stu-id="e186a-162">Safari</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="audio-file-requirements-for-dial-in-conferencing"></a><span data-ttu-id="e186a-163">Требования звуковым файлам для конференц-связи с телефонным подключением</span><span class="sxs-lookup"><span data-stu-id="e186a-163">Audio File Requirements for dial-in conferencing</span></span>

<span data-ttu-id="e186a-164">Lync Server 2013 не поддерживает настройку голосовых приглашений и музыки для конференц-связи с телефонным подключением.</span><span class="sxs-lookup"><span data-stu-id="e186a-164">Lync Server 2013 does not support customization of voice prompts and music for dial-in conferencing.</span></span> <span data-ttu-id="e186a-165">Тем не менее, если требуется изменить аудиофайлы по умолчанию, ознакомьтесь со статьей базы знаний Майкрософт 961177, [как настроить голосовые запросы и музыкальные файлы для конференц-связи с телефонным подключением в Microsoft Office Communications Server 2007 R2](https://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=961177).</span><span class="sxs-lookup"><span data-stu-id="e186a-165">However, if you have a strong business need that requires you to change the default audio files, see Microsoft Knowledge Base article 961177, [How to customize voice prompts or music files for dial-in audio conferencing in Microsoft Office Communications Server 2007 R2](https://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=961177).</span></span>

<span data-ttu-id="e186a-166">Вы также можете использовать программу управления [помощником по конференц-связи Microsoft Lync Server](https://go.microsoft.com/fwlink/p/?linkid=396880) , которая позволяет администраторам заменять голосовые сообщения по умолчанию, используемые при подключении абонента к собранию Lync с настраиваемыми приглашениями, для предоставления другим пользователям возможности ввода собраний.</span><span class="sxs-lookup"><span data-stu-id="e186a-166">You can also use the [Microsoft Lync Server Conferencing Attendant Custom Voice Prompts](https://go.microsoft.com/fwlink/p/?linkid=396880) management utility, which enables administrators to replace the default voice prompts used when a phone caller joins a Lync meeting with custom prompts to provide a different meeting entry experience.</span></span> <span data-ttu-id="e186a-167">Настраиваемые голосовые приглашения можно установить на сервере, на котором работает Lync Server 2010 или Lync Server 2013, либо Enterprise, либо Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="e186a-167">The custom voice prompts can be installed on a server that is running Lync Server 2010 or Lync Server 2013, either Enterprise or Standard Edition.</span></span>

<span data-ttu-id="e186a-168">Приложение для конференц-связи "помощник по конференциям и конференц-связь" имеет следующие требования к музыке при удержании, записанных именах и файлах звуковых приглашений:</span><span class="sxs-lookup"><span data-stu-id="e186a-168">Conferencing Attendant application and Conferencing Announcement application have the following requirements for music on hold, recorded name, and audio prompt files:</span></span>

  - <span data-ttu-id="e186a-169">Формат файлов WMA (Windows Media Audio)</span><span class="sxs-lookup"><span data-stu-id="e186a-169">Windows Media Audio (WMA) file format</span></span>

  - <span data-ttu-id="e186a-170">Моно 16 бит</span><span class="sxs-lookup"><span data-stu-id="e186a-170">16-bit mono</span></span>

  - <span data-ttu-id="e186a-171">48 Кбит/с, 2 прохода, CBR (постоянная скорость)</span><span class="sxs-lookup"><span data-stu-id="e186a-171">48 kbps 2-pass CBR (constant bit rate)</span></span>

  - <span data-ttu-id="e186a-172">Уровень речи на -24 дБ</span><span class="sxs-lookup"><span data-stu-id="e186a-172">Speech level at -24DB</span></span>

</div>

<div>

## <a name="user-requirements-for-dial-in-conferencing"></a><span data-ttu-id="e186a-173">Требования к пользователям для конференц-связи с телефонным подключением</span><span class="sxs-lookup"><span data-stu-id="e186a-173">User Requirements for Dial-In Conferencing</span></span>

<span data-ttu-id="e186a-174">Учетным записям пользователей конференц-связи с телефонным подключением должны быть уникальные номера телефонов или добавочные номера.</span><span class="sxs-lookup"><span data-stu-id="e186a-174">Dial-in conferencing users must have a unique phone number or extension assigned to their account.</span></span> <span data-ttu-id="e186a-175">Благодаря этому требованию становится возможным выполнять проверку подлинности во время телефонного подключения.</span><span class="sxs-lookup"><span data-stu-id="e186a-175">This requirement supports authentication during dial-in conferencing.</span></span> <span data-ttu-id="e186a-176">Корпоративные пользователи (то есть пользователи, у которых есть учетные данные доменных служб Active Directory и учетные записи Lync Server в вашей организации) вводят номер телефона (или добавочный номер) и персональный идентификационный номер (ПИН-код) для подключения к конференциям в качестве пользователя, прошедшего проверку подлинности.</span><span class="sxs-lookup"><span data-stu-id="e186a-176">Enterprise users (that is, users who have Active Directory Domain Services credentials and Lync Server accounts within your organization) enter their phone number (or extension) and a personal identification number (PIN) to dial in to conferences as an authenticated user.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

