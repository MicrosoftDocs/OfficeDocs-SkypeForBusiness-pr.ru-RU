---
title: 'Lync Server 2013: взаимодействие клиентов в Lync 2013'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Client interoperability in Lync 2013
ms:assetid: 0f126571-91a2-45d5-855c-1e4ddb45fc04
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204672(v=OCS.15)
ms:contentKeyID: 48183417
ms.date: 03/04/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 437051279393b9dedc7c4def0c75cd119cded914
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42197832"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="client-interoperability-in-lync-2013"></a><span data-ttu-id="bd154-102">Взаимодействие клиентов в Lync 2013</span><span class="sxs-lookup"><span data-stu-id="bd154-102">Client interoperability in Lync 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bd154-103">_**Последнее изменение темы:** 2016-03-04_</span><span class="sxs-lookup"><span data-stu-id="bd154-103">_**Topic Last Modified:** 2016-03-04_</span></span>

<span data-ttu-id="bd154-104">В этом разделе рассказывается о возможности совместного использования клиентами Microsoft Lync Server 2013 и взаимодействии с клиентами из более ранних версий Lync Server и Office Communications Server.</span><span class="sxs-lookup"><span data-stu-id="bd154-104">This topic discusses the ability of Microsoft Lync Server 2013 clients to coexist and interact with clients from earlier versions of Lync Server and Office Communications Server.</span></span>

<div>

## <a name="server-and-client-compatibility"></a><span data-ttu-id="bd154-105">Совместимость серверов и клиентов</span><span class="sxs-lookup"><span data-stu-id="bd154-105">Server and Client Compatibility</span></span>

<span data-ttu-id="bd154-106">В следующей таблице показаны поддерживаемые сочетания версий клиентов и серверов.</span><span class="sxs-lookup"><span data-stu-id="bd154-106">The following table shows the supported combinations of client versions and server versions.</span></span> <span data-ttu-id="bd154-107">В этой таблице показано, поддерживается ли вход, когда клиент пытается подключиться к указанному серверу.</span><span class="sxs-lookup"><span data-stu-id="bd154-107">This table indicates whether sign-in is supported when the client attempts to connect to the server indicated.</span></span> <span data-ttu-id="bd154-108">Lync Server 2013 поддерживает предыдущую версию клиента.</span><span class="sxs-lookup"><span data-stu-id="bd154-108">Lync Server 2013 supports the previous client version.</span></span> <span data-ttu-id="bd154-109">Кроме того, в отличие от предыдущих выпусков, Lync Server 2010 поддерживает новые клиенты Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="bd154-109">Also, unlike previous releases, Lync Server 2010 supports the new Lync 2013 clients.</span></span> <span data-ttu-id="bd154-110">Это позволяет организациям, которые обновляются с Lync Server 2010, развертывать новые клиенты независимо от обновлений Lync Server.</span><span class="sxs-lookup"><span data-stu-id="bd154-110">This allows organizations who are upgrading from Lync Server 2010 to roll out new clients independent of Lync Server upgrades.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="bd154-111">Client</span><span class="sxs-lookup"><span data-stu-id="bd154-111">Client</span></span></th>
<th><span data-ttu-id="bd154-112">Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bd154-112">Lync Server 2013</span></span></th>
<th><span data-ttu-id="bd154-113">Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="bd154-113">Lync Server 2010</span></span></th>
<th><span data-ttu-id="bd154-114">Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="bd154-114">Office Communications Server 2007 R2</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="bd154-115">Lync 2013</span><span class="sxs-lookup"><span data-stu-id="bd154-115">Lync 2013</span></span></p></td>
<td><p><span data-ttu-id="bd154-116">Поддерживается</span><span class="sxs-lookup"><span data-stu-id="bd154-116">Supported</span></span></p></td>
<td><p><span data-ttu-id="bd154-117">Supported5</span><span class="sxs-lookup"><span data-stu-id="bd154-117">Supported5</span></span></p></td>
<td><p><span data-ttu-id="bd154-118">Не поддерживается</span><span class="sxs-lookup"><span data-stu-id="bd154-118">Not Supported</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bd154-119">Lync 2013 Basic</span><span class="sxs-lookup"><span data-stu-id="bd154-119">Lync 2013 Basic</span></span></p></td>
<td><p><span data-ttu-id="bd154-120">Поддерживается</span><span class="sxs-lookup"><span data-stu-id="bd154-120">Supported</span></span></p></td>
<td><p><span data-ttu-id="bd154-121">Поддерживается</span><span class="sxs-lookup"><span data-stu-id="bd154-121">Supported</span></span></p></td>
<td><p><span data-ttu-id="bd154-122">Не поддерживается</span><span class="sxs-lookup"><span data-stu-id="bd154-122">Not Supported</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bd154-123">Lync Web App 2013</span><span class="sxs-lookup"><span data-stu-id="bd154-123">Lync Web App 2013</span></span></p></td>
<td><p><span data-ttu-id="bd154-124">Поддерживается</span><span class="sxs-lookup"><span data-stu-id="bd154-124">Supported</span></span></p></td>
<td><p><span data-ttu-id="bd154-125">Не поддерживается</span><span class="sxs-lookup"><span data-stu-id="bd154-125">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="bd154-126">Не поддерживается</span><span class="sxs-lookup"><span data-stu-id="bd154-126">Not Supported</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bd154-127">Lync 2010</span><span class="sxs-lookup"><span data-stu-id="bd154-127">Lync 2010</span></span></p></td>
<td><p><span data-ttu-id="bd154-128">Поддерживается</span><span class="sxs-lookup"><span data-stu-id="bd154-128">Supported</span></span></p></td>
<td><p><span data-ttu-id="bd154-129">Поддерживается</span><span class="sxs-lookup"><span data-stu-id="bd154-129">Supported</span></span></p></td>
<td><p><span data-ttu-id="bd154-130">Не поддерживается</span><span class="sxs-lookup"><span data-stu-id="bd154-130">Not Supported</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bd154-131">Lync 2010 Attendant</span><span class="sxs-lookup"><span data-stu-id="bd154-131">Lync 2010 Attendant</span></span></p></td>
<td><p><span data-ttu-id="bd154-132">Поддерживается</span><span class="sxs-lookup"><span data-stu-id="bd154-132">Supported</span></span></p></td>
<td><p><span data-ttu-id="bd154-133">Поддерживается</span><span class="sxs-lookup"><span data-stu-id="bd154-133">Supported</span></span></p></td>
<td><p><span data-ttu-id="bd154-134">Не поддерживается</span><span class="sxs-lookup"><span data-stu-id="bd154-134">Not Supported</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bd154-135">Lync 2010 Group Chat</span><span class="sxs-lookup"><span data-stu-id="bd154-135">Lync 2010 Group Chat</span></span></p></td>
<td><p><span data-ttu-id="bd154-136">Supported1</span><span class="sxs-lookup"><span data-stu-id="bd154-136">Supported1</span></span></p></td>
<td><p><span data-ttu-id="bd154-137">Supported2</span><span class="sxs-lookup"><span data-stu-id="bd154-137">Supported2</span></span></p></td>
<td><p><span data-ttu-id="bd154-138">Неприменимо</span><span class="sxs-lookup"><span data-stu-id="bd154-138">Not Applicable</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bd154-139">Lync Web App 2010</span><span class="sxs-lookup"><span data-stu-id="bd154-139">Lync Web App 2010</span></span></p></td>
<td><p><span data-ttu-id="bd154-140">Не поддерживается</span><span class="sxs-lookup"><span data-stu-id="bd154-140">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="bd154-141">Поддерживается</span><span class="sxs-lookup"><span data-stu-id="bd154-141">Supported</span></span></p></td>
<td><p><span data-ttu-id="bd154-142">Не поддерживается</span><span class="sxs-lookup"><span data-stu-id="bd154-142">Not Supported</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bd154-143">Lync 2010 Attendee</span><span class="sxs-lookup"><span data-stu-id="bd154-143">Lync 2010 Attendee</span></span></p></td>
<td><p><span data-ttu-id="bd154-144">Не Supported3</span><span class="sxs-lookup"><span data-stu-id="bd154-144">Not Supported3</span></span></p></td>
<td><p><span data-ttu-id="bd154-145">Поддерживается</span><span class="sxs-lookup"><span data-stu-id="bd154-145">Supported</span></span></p></td>
<td><p><span data-ttu-id="bd154-146">Не поддерживается</span><span class="sxs-lookup"><span data-stu-id="bd154-146">Not Supported</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bd154-147">Office Communicator 2007 R2</span><span class="sxs-lookup"><span data-stu-id="bd154-147">Office Communicator 2007 R2</span></span></p></td>
<td><p><span data-ttu-id="bd154-148">Interoperable4</span><span class="sxs-lookup"><span data-stu-id="bd154-148">Interoperable4</span></span></p></td>
<td><p><span data-ttu-id="bd154-149">Поддерживается</span><span class="sxs-lookup"><span data-stu-id="bd154-149">Supported</span></span></p></td>
<td><p><span data-ttu-id="bd154-150">Поддерживается</span><span class="sxs-lookup"><span data-stu-id="bd154-150">Supported</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bd154-151">Помощник Microsoft Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="bd154-151">Microsoft Office Communications Server 2007 R2 Attendant</span></span></p></td>
<td><p><span data-ttu-id="bd154-152">Не поддерживается</span><span class="sxs-lookup"><span data-stu-id="bd154-152">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="bd154-153">Поддерживается</span><span class="sxs-lookup"><span data-stu-id="bd154-153">Supported</span></span></p></td>
<td><p><span data-ttu-id="bd154-154">Поддерживается</span><span class="sxs-lookup"><span data-stu-id="bd154-154">Supported</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bd154-155">Office Communicator 2007</span><span class="sxs-lookup"><span data-stu-id="bd154-155">Office Communicator 2007</span></span></p></td>
<td><p><span data-ttu-id="bd154-156">Не поддерживается</span><span class="sxs-lookup"><span data-stu-id="bd154-156">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="bd154-157">Поддерживается</span><span class="sxs-lookup"><span data-stu-id="bd154-157">Supported</span></span></p></td>
<td><p><span data-ttu-id="bd154-158">Поддерживается</span><span class="sxs-lookup"><span data-stu-id="bd154-158">Supported</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bd154-159">Office Live Meeting 2007</span><span class="sxs-lookup"><span data-stu-id="bd154-159">Office Live Meeting 2007</span></span></p></td>
<td><p><span data-ttu-id="bd154-160">Не поддерживается</span><span class="sxs-lookup"><span data-stu-id="bd154-160">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="bd154-161">Поддерживается</span><span class="sxs-lookup"><span data-stu-id="bd154-161">Supported</span></span></p></td>
<td><p><span data-ttu-id="bd154-162">Поддерживается</span><span class="sxs-lookup"><span data-stu-id="bd154-162">Supported</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bd154-163">Приложение Lync для Магазина Windows</span><span class="sxs-lookup"><span data-stu-id="bd154-163">Lync Windows Store app</span></span></p></td>
<td><p><span data-ttu-id="bd154-164">Поддерживается</span><span class="sxs-lookup"><span data-stu-id="bd154-164">Supported</span></span></p></td>
<td><p><span data-ttu-id="bd154-165">Поддерживается</span><span class="sxs-lookup"><span data-stu-id="bd154-165">Supported</span></span></p></td>
<td><p><span data-ttu-id="bd154-166">Не поддерживается</span><span class="sxs-lookup"><span data-stu-id="bd154-166">Not Supported</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="bd154-167">1For Details: [Migration from Lync server 2010, Group Chat или Office Communications Server 2007 R2 Group Chat to Lync server 2013, сервер сохраняемого чата](migration-from-lync-server-2010-group-chat-or-office-communications-server-2007-r2-group-chat-to-lync-server-2013-persistent-chat-server.md).</span><span class="sxs-lookup"><span data-stu-id="bd154-167">1For details, see [Migration from Lync Server 2010, Group Chat or Office Communications Server 2007 R2 Group Chat to Lync Server 2013, Persistent Chat Server](migration-from-lync-server-2010-group-chat-or-office-communications-server-2007-r2-group-chat-to-lync-server-2013-persistent-chat-server.md).</span></span>

<span data-ttu-id="bd154-168">2In Microsoft Lync Server 2010, доступны функции группового чата с сервером группового чата, доверенным сторонним приложением для Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="bd154-168">2In Microsoft Lync Server 2010, group chat functionality was available with Group Chat Server, a third-party trusted application for Lync Server 2010.</span></span> <span data-ttu-id="bd154-169">Клиенты Lync 2013 несовместимы с Lync Server 2010, группового чата.</span><span class="sxs-lookup"><span data-stu-id="bd154-169">Lync 2013 clients are not compatible with Lync Server 2010, Group Chat.</span></span>

<span data-ttu-id="bd154-170">3Lync Web App 2013 теперь предоставляет полный интерфейс для собраний, включая аудио-и видеоданные, и считается заменой участнику Lync 2010.</span><span class="sxs-lookup"><span data-stu-id="bd154-170">3Lync Web App 2013 now provides a full in-meeting experience, including computer audio and video, and is considered the replacement for Lync 2010 Attendee.</span></span> <span data-ttu-id="bd154-171">Lync 2010 участник будет подключаться к Lync Server 2013 только при использовании неподдерживаемого браузера (Internet Explorer 6 или Internet Explorer 7) и Windows XP.</span><span class="sxs-lookup"><span data-stu-id="bd154-171">Lync 2010 Attendee will connect to Lync Server 2013 only when you are using an unsupported browser (Internet Explorer 6 or Internet Explorer 7) and Windows XP.</span></span>

<span data-ttu-id="bd154-172">4The присутствия и функции обмена мгновенными сообщениями в Office Communicator 2007 R2 совместимы с Lync Server 2013, но функции конференц-связи не поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="bd154-172">4The presence and IM features in Office Communicator 2007 R2 are compatible with Lync Server 2013, but conferencing features are not.</span></span> <span data-ttu-id="bd154-173">Во время миграции с Office Communications Server 2007 R2 приложение Office Communicator 2007 R2 подходит для взаимодействия с присутствием и обменом мгновенными сообщениями, но пользователи должны использовать Lync Web App 2013, чтобы присоединиться к собраниям Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="bd154-173">During migration from Office Communications Server 2007 R2, Office Communicator 2007 R2 is suitable for presence and IM interoperability, but users should use Lync Web App 2013 to join Lync Server 2013 meetings.</span></span>

<span data-ttu-id="bd154-174">5 для получения ограничений обратитесь к разделу "Поддержка функций конференц-связи для клиентов Lync 2013 в Lync Server 2010 для собраний" Далее в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="bd154-174">5 For limitations, see "Conferencing Feature Support for Lync 2013 Clients in Lync Server 2010 Meetings" later in this topic.</span></span>

</div>

<div>

## <a name="interoperability-among-clients"></a><span data-ttu-id="bd154-175">Взаимодействие между клиентами</span><span class="sxs-lookup"><span data-stu-id="bd154-175">Interoperability among Clients</span></span>

<span data-ttu-id="bd154-176">В выпуске Lync Server 2013 различные клиентские версии могут беспрепятственно взаимодействовать как в одноранговых, так и в сценариях конференц-связи.</span><span class="sxs-lookup"><span data-stu-id="bd154-176">With the Lync Server 2013 release, various client versions can interact seamlessly in both peer-to-peer and conferencing scenarios.</span></span> <span data-ttu-id="bd154-177">В этом разделе описывается доступность функций, когда пользователи взаимодействуют с другими пользователями, использующими разные версии клиентов и серверов.</span><span class="sxs-lookup"><span data-stu-id="bd154-177">This section discusses feature availability when users interact with other users who are using different versions of clients and servers.</span></span>

<div>

## <a name="peer-to-peer-feature-support"></a><span data-ttu-id="bd154-178">Поддержка одноранговых функций</span><span class="sxs-lookup"><span data-stu-id="bd154-178">Peer-to-Peer Feature Support</span></span>

<span data-ttu-id="bd154-179">Одноранговые функции поддерживаются для пользователей, размещенных в различных версиях сервера и использующих разные версии клиентов.</span><span class="sxs-lookup"><span data-stu-id="bd154-179">Peer-to-peer features are supported for users who are homed on different versions of the server and who are using different client versions.</span></span> <span data-ttu-id="bd154-180">Функции конечного пользователя и доступные функции соответствуют возможностям клиента пользователя и версии сервера, на котором выполнен вход пользователя.</span><span class="sxs-lookup"><span data-stu-id="bd154-180">The end-user experience and available features are consistent with the capabilities of the user’s client and the version of the server the user is signed in to.</span></span> <span data-ttu-id="bd154-181">Другими словами:</span><span class="sxs-lookup"><span data-stu-id="bd154-181">In other words:</span></span>

  - <span data-ttu-id="bd154-182">Если пользователь вошел в Lync Server 2013 с более старым клиентом, он будет иметь такой же интерфейс, что и для пользователя.</span><span class="sxs-lookup"><span data-stu-id="bd154-182">If a user is signed in to Lync Server 2013 with an older client, the user will have the same experience he or she is used to.</span></span> <span data-ttu-id="bd154-183">Никакие новые функции, введенные в Lync Server 2013, будут недоступны до тех пор, пока клиент пользователя не будет обновлен.</span><span class="sxs-lookup"><span data-stu-id="bd154-183">None of the new features introduced in Lync Server 2013 will be available until the user’s client is upgraded.</span></span> <span data-ttu-id="bd154-184">Примеры включают представление "Коллекция видео", видео в формате HD, обновленный общий доступ к PowerPoint и возможность отключения звука и видео участников при вводе собрания.</span><span class="sxs-lookup"><span data-stu-id="bd154-184">Examples include video gallery view, HD video, updated PowerPoint sharing, and the option to mute all attendee audio and video upon meeting entry.</span></span> <span data-ttu-id="bd154-185">Новые возможности, описанные в разделе [новые функции конференц-связи в Lync server 2013](lync-server-2013-new-conferencing-features.md) , а также новые возможности [для клиентов в Lync Server 2013](lync-server-2013-what-s-new-for-clients.md).</span><span class="sxs-lookup"><span data-stu-id="bd154-185">The new features are outlined in [New conferencing features in Lync Server 2013](lync-server-2013-new-conferencing-features.md) and [What's new for clients in Lync Server 2013](lync-server-2013-what-s-new-for-clients.md).</span></span>

  - <span data-ttu-id="bd154-186">Если пользователь вошел в Lync Server 2010 с клиентом Lync 2013, все новые функции, не поддерживаемые в Lync Server 2010, будут недоступны до тех пор, пока пользователь не будет перемещен в Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="bd154-186">If a user is signed in to Lync Server 2010 with a Lync 2013 client, any new features not supported by Lync Server 2010 will be unavailable until the user is moved to Lync Server 2013.</span></span>

<span data-ttu-id="bd154-187">В следующей таблице сравнивается доступность функций в одноранговых сеансах, где клиент входит в состав Lync Server 2013 или Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="bd154-187">The following table compares feature availability in peer-to-peer sessions where the client is signed in to either Lync Server 2013 or Lync Server 2010.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="bd154-188">Lync Web App и Lync 2010 участник являются клиентами только для собраний и не включены в эту таблицу.</span><span class="sxs-lookup"><span data-stu-id="bd154-188">Lync Web App and Lync 2010 Attendee are meeting-only clients and aren’t included in this table.</span></span>



</div>


<table style="width:100%;">
<colgroup>
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="bd154-189">Client</span><span class="sxs-lookup"><span data-stu-id="bd154-189">Client</span></span></th>
<th><span data-ttu-id="bd154-190">Обмен мгновенными сообщениями</span><span class="sxs-lookup"><span data-stu-id="bd154-190">Instant Messaging</span></span></th>
<th><span data-ttu-id="bd154-191">Присутствие</span><span class="sxs-lookup"><span data-stu-id="bd154-191">Presence</span></span></th>
<th><span data-ttu-id="bd154-192">Голос</span><span class="sxs-lookup"><span data-stu-id="bd154-192">Voice</span></span></th>
<th><span data-ttu-id="bd154-193">Видео</span><span class="sxs-lookup"><span data-stu-id="bd154-193">Video</span></span></th>
<th><span data-ttu-id="bd154-194">Совместное использование приложений</span><span class="sxs-lookup"><span data-stu-id="bd154-194">Application Sharing</span></span></th>
<th><span data-ttu-id="bd154-195">Передача файлов</span><span class="sxs-lookup"><span data-stu-id="bd154-195">File Transfer</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="bd154-196">Lync 2013</span><span class="sxs-lookup"><span data-stu-id="bd154-196">Lync 2013</span></span></p></td>
<td><p><span data-ttu-id="bd154-197">Да</span><span class="sxs-lookup"><span data-stu-id="bd154-197">Yes</span></span></p></td>
<td><p><span data-ttu-id="bd154-198">Да</span><span class="sxs-lookup"><span data-stu-id="bd154-198">Yes</span></span></p></td>
<td><p><span data-ttu-id="bd154-199">Да</span><span class="sxs-lookup"><span data-stu-id="bd154-199">Yes</span></span></p></td>
<td><p><span data-ttu-id="bd154-200">Да</span><span class="sxs-lookup"><span data-stu-id="bd154-200">Yes</span></span></p></td>
<td><p><span data-ttu-id="bd154-201">Да</span><span class="sxs-lookup"><span data-stu-id="bd154-201">Yes</span></span></p></td>
<td><p><span data-ttu-id="bd154-202">Да</span><span class="sxs-lookup"><span data-stu-id="bd154-202">Yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bd154-203">Lync 2013 Basic</span><span class="sxs-lookup"><span data-stu-id="bd154-203">Lync 2013 Basic</span></span></p></td>
<td><p><span data-ttu-id="bd154-204">Да</span><span class="sxs-lookup"><span data-stu-id="bd154-204">Yes</span></span></p></td>
<td><p><span data-ttu-id="bd154-205">Да</span><span class="sxs-lookup"><span data-stu-id="bd154-205">Yes</span></span></p></td>
<td><p><span data-ttu-id="bd154-206">Да</span><span class="sxs-lookup"><span data-stu-id="bd154-206">Yes</span></span></p></td>
<td><p><span data-ttu-id="bd154-207">Да</span><span class="sxs-lookup"><span data-stu-id="bd154-207">Yes</span></span></p></td>
<td><p><span data-ttu-id="bd154-208">Да</span><span class="sxs-lookup"><span data-stu-id="bd154-208">Yes</span></span></p></td>
<td><p><span data-ttu-id="bd154-209">Да</span><span class="sxs-lookup"><span data-stu-id="bd154-209">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bd154-210">Lync 2010</span><span class="sxs-lookup"><span data-stu-id="bd154-210">Lync 2010</span></span></p></td>
<td><p><span data-ttu-id="bd154-211">Да</span><span class="sxs-lookup"><span data-stu-id="bd154-211">Yes</span></span></p></td>
<td><p><span data-ttu-id="bd154-212">Да</span><span class="sxs-lookup"><span data-stu-id="bd154-212">Yes</span></span></p></td>
<td><p><span data-ttu-id="bd154-213">Да</span><span class="sxs-lookup"><span data-stu-id="bd154-213">Yes</span></span></p></td>
<td><p><span data-ttu-id="bd154-214">Да</span><span class="sxs-lookup"><span data-stu-id="bd154-214">Yes</span></span></p></td>
<td><p><span data-ttu-id="bd154-215">Да</span><span class="sxs-lookup"><span data-stu-id="bd154-215">Yes</span></span></p></td>
<td><p><span data-ttu-id="bd154-216">Да</span><span class="sxs-lookup"><span data-stu-id="bd154-216">Yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bd154-217">Lync 2010 Attendant</span><span class="sxs-lookup"><span data-stu-id="bd154-217">Lync 2010 Attendant</span></span></p></td>
<td><p><span data-ttu-id="bd154-218">Да</span><span class="sxs-lookup"><span data-stu-id="bd154-218">Yes</span></span></p></td>
<td><p><span data-ttu-id="bd154-219">Да</span><span class="sxs-lookup"><span data-stu-id="bd154-219">Yes</span></span></p></td>
<td><p><span data-ttu-id="bd154-220">Да</span><span class="sxs-lookup"><span data-stu-id="bd154-220">Yes</span></span></p></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bd154-221">Lync 2010 Mobile</span><span class="sxs-lookup"><span data-stu-id="bd154-221">Lync 2010 Mobile</span></span></p></td>
<td><p><span data-ttu-id="bd154-222">Да</span><span class="sxs-lookup"><span data-stu-id="bd154-222">Yes</span></span></p></td>
<td><p><span data-ttu-id="bd154-223">Да</span><span class="sxs-lookup"><span data-stu-id="bd154-223">Yes</span></span></p></td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bd154-224">Lync Phone Edition</span><span class="sxs-lookup"><span data-stu-id="bd154-224">Lync Phone Edition</span></span></p></td>
<td><p><span data-ttu-id="bd154-225">Да</span><span class="sxs-lookup"><span data-stu-id="bd154-225">Yes</span></span></p></td>
<td><p><span data-ttu-id="bd154-226">Да</span><span class="sxs-lookup"><span data-stu-id="bd154-226">Yes</span></span></p></td>
<td><p><span data-ttu-id="bd154-227">Да</span><span class="sxs-lookup"><span data-stu-id="bd154-227">Yes</span></span></p></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bd154-228">Office Communicator 2007 R2</span><span class="sxs-lookup"><span data-stu-id="bd154-228">Office Communicator 2007 R2</span></span></p></td>
<td><p><span data-ttu-id="bd154-229">Да</span><span class="sxs-lookup"><span data-stu-id="bd154-229">Yes</span></span></p></td>
<td><p><span data-ttu-id="bd154-230">Да</span><span class="sxs-lookup"><span data-stu-id="bd154-230">Yes</span></span></p></td>
<td><p><span data-ttu-id="bd154-231">Да</span><span class="sxs-lookup"><span data-stu-id="bd154-231">Yes</span></span></p></td>
<td><p><span data-ttu-id="bd154-232">Да</span><span class="sxs-lookup"><span data-stu-id="bd154-232">Yes</span></span></p></td>
<td><p><span data-ttu-id="bd154-233">Yes1</span><span class="sxs-lookup"><span data-stu-id="bd154-233">Yes1</span></span></p></td>
<td><p><span data-ttu-id="bd154-234">Да</span><span class="sxs-lookup"><span data-stu-id="bd154-234">Yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bd154-235">Общедоступная служба обмена мгновенными сообщениями (AOL, Yahoo!)</span><span class="sxs-lookup"><span data-stu-id="bd154-235">Public IM (AOL, Yahoo!)</span></span></p></td>
<td><p><span data-ttu-id="bd154-236">Да</span><span class="sxs-lookup"><span data-stu-id="bd154-236">Yes</span></span></p></td>
<td><p><span data-ttu-id="bd154-237">Да</span><span class="sxs-lookup"><span data-stu-id="bd154-237">Yes</span></span></p></td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bd154-238">Общедоступная служба обмена мгновенными сообщениями (MSN, Windows Live Messenger)</span><span class="sxs-lookup"><span data-stu-id="bd154-238">Public IM (MSN, Windows Live Messenger)</span></span></p></td>
<td><p><span data-ttu-id="bd154-239">Да</span><span class="sxs-lookup"><span data-stu-id="bd154-239">Yes</span></span></p></td>
<td><p><span data-ttu-id="bd154-240">Да</span><span class="sxs-lookup"><span data-stu-id="bd154-240">Yes</span></span></p></td>
<td><p><span data-ttu-id="bd154-241">Да</span><span class="sxs-lookup"><span data-stu-id="bd154-241">Yes</span></span></p></td>
<td><p><span data-ttu-id="bd154-242">Да</span><span class="sxs-lookup"><span data-stu-id="bd154-242">Yes</span></span></p></td>
<td></td>
<td></td>
</tr>
</tbody>
</table>


<div>


> [!IMPORTANT]  
> <UL>
> <LI>
> <P><span data-ttu-id="bd154-243">С 1 сентября 2012 г. Лицензия на подписку общедоступных служб обмена мгновенными сообщениями Microsoft Lync (PIC усл) больше недоступна для приобретения новых или обновленных договоров.</span><span class="sxs-lookup"><span data-stu-id="bd154-243">As of September 1st, 2012, the Microsoft Lync Public IM Connectivity User Subscription License (PIC USL) is no longer available for the purchase for new or renewing agreements.</span></span> <span data-ttu-id="bd154-244">Клиенты с активными лицензиями смогут продолжать Федерацию с помощью Yahoo!</span><span class="sxs-lookup"><span data-stu-id="bd154-244">Customers with active licenses will be able to continue to federate with Yahoo!</span></span> <span data-ttu-id="bd154-245">Messenger до даты завершения работы службы.</span><span class="sxs-lookup"><span data-stu-id="bd154-245">Messenger until the service shutdown date.</span></span> <span data-ttu-id="bd154-246">Дата окончания срока жизни 2014 для AOL и Yahoo!</span><span class="sxs-lookup"><span data-stu-id="bd154-246">An end of life date of June 2014 for AOL and Yahoo!</span></span> <span data-ttu-id="bd154-247">объявлено.</span><span class="sxs-lookup"><span data-stu-id="bd154-247">has been announced.</span></span> <span data-ttu-id="bd154-248">Дополнительные сведения см <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">в разделе Поддержка общедоступной службы обмена мгновенными сообщениями в Lync Server 2013</A>..</span><span class="sxs-lookup"><span data-stu-id="bd154-248">For details, see <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Support for public instant messenger connectivity in Lync Server 2013</A>..</span></span></P>
> <LI>
> <P><span data-ttu-id="bd154-249">УСЛ PIC — это лицензия на помесячную подписку на уровне пользователя, которая требуется для Lync Server или Office Communications Server для Федерации с Yahoo!</span><span class="sxs-lookup"><span data-stu-id="bd154-249">The PIC USL is a per-user, per-month subscription license that is required for Lync Server or Office Communications Server to federate with Yahoo!</span></span> <span data-ttu-id="bd154-250">Messenger.</span><span class="sxs-lookup"><span data-stu-id="bd154-250">Messenger.</span></span> <span data-ttu-id="bd154-251">Способность корпорации Майкрософт предоставлять эту службу зависит от поддержки компании Yahoo!, основного соглашения, для которого обновление не выполняется.</span><span class="sxs-lookup"><span data-stu-id="bd154-251">Microsoft’s ability to provide this service has been contingent upon support from Yahoo!, the underlying agreement for which will not be renewed.</span></span></P>
> <LI>
> <P><span data-ttu-id="bd154-252">Lync — это мощное средство для связи между организациями и пользователями мира.</span><span class="sxs-lookup"><span data-stu-id="bd154-252">More than ever, Lync is a powerful tool for connecting across organizations and with individuals around the world.</span></span> <span data-ttu-id="bd154-253">Для Федерации с Windows Live Messenger не требуется дополнительных лицензий на пользователей и устройств, не относящихся к стандарту Lync CAL.</span><span class="sxs-lookup"><span data-stu-id="bd154-253">Federation with Windows Live Messenger requires no additional user/device licenses beyond the Lync Standard CAL.</span></span> <span data-ttu-id="bd154-254">В этот список будет добавлена Федерация Skype, которая позволяет пользователям Lync достигать сотни миллионов людей с помощью обмена мгновенными сообщениями и голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="bd154-254">Skype federation will be added to this list, enabling Lync users to reach hundreds of millions of people through IM and voice.</span></span></P></LI></UL>



</div>

<span data-ttu-id="bd154-255">1 в Office Communicator 2007 R2 доступен только общий доступ к рабочему столу (а не к совместному использованию программ).</span><span class="sxs-lookup"><span data-stu-id="bd154-255">1 In Office Communicator 2007 R2, only desktop sharing (and not program sharing) is available.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="bd154-256">Общий доступ к рабочему столу Office Communicator 2007 R2 и Skype для бизнеса 2015 невозможно инициировать из нового клиента, когда применяется пользовательский интерфейс клиента Skype для бизнеса 2015.</span><span class="sxs-lookup"><span data-stu-id="bd154-256">Desktop sharing between Office Communicator 2007 R2 and Skype for Business 2015 cannot be initiated from the newer client when the Skype for Business 2015 client user interface is enforced.</span></span>



</div>

</div>

<div>

## <a name="conferencing-feature-support-for-lync-2013-clients-in-lync-server-2010-meetings"></a><span data-ttu-id="bd154-257">Поддержка функций конференц-связи для клиентов Lync 2013 в Lync Server 2010 для собраний</span><span class="sxs-lookup"><span data-stu-id="bd154-257">Conferencing Feature Support for Lync 2013 Clients in Lync Server 2010 Meetings</span></span>

<span data-ttu-id="bd154-258">Когда пользователи присоединяются к Lync Server 2010 meetings с клиентом Lync 2013, у них есть доступ к клиентским функциям Lync 2013 со следующими исключениями:</span><span class="sxs-lookup"><span data-stu-id="bd154-258">When users join Lync Server 2010 meetings with a Lync 2013 client, they have access to Lync 2013 client features with the following exceptions:</span></span>

  - <span data-ttu-id="bd154-259">В параметрах управления **участниками** , доступ к которым осуществляется путем указания значка "люди" в окне собрания, параметр "не вести **мгновенный обмен мгновенными сообщениями** " не работает.</span><span class="sxs-lookup"><span data-stu-id="bd154-259">In the **Participants** management options, which are accessible by pointing to the people icon in the meeting window, the **No Meeting IM** option does not function.</span></span>

  - <span data-ttu-id="bd154-260">Представление галереи не работает в видеоконференциях.</span><span class="sxs-lookup"><span data-stu-id="bd154-260">Gallery View does not function in video conferences.</span></span> <span data-ttu-id="bd154-261">Пользователю развидится только активный динамик, а не все динамики.</span><span class="sxs-lookup"><span data-stu-id="bd154-261">The user sees only the active speaker instead of all speakers.</span></span> <span data-ttu-id="bd154-262">В списке выберите параметры **макета** недоступно **представление "коллекция** "</span><span class="sxs-lookup"><span data-stu-id="bd154-262">In the list of **Pick a Layout** options, **Gallery View** is unavailable</span></span>

  - <span data-ttu-id="bd154-263">Список участников по умолчанию отображается в видеоконференциях.</span><span class="sxs-lookup"><span data-stu-id="bd154-263">The participant list displays by default in video conferences.</span></span>

  - <span data-ttu-id="bd154-264">Когда вы щелкаете правой кнопкой мыши пользователя в списке участников, вы не сможете получить доступ к параметрам управления участниками **коллекции и закрепить** **его** в коллекции.</span><span class="sxs-lookup"><span data-stu-id="bd154-264">When right-clicking a user in the participants list, the **Lock the Video Spotlight** and **Pin to Gallery** participant management options are unavailable.</span></span>

</div>

<div>

## <a name="conferencing-feature-support-in-lync-server-2013-meetings"></a><span data-ttu-id="bd154-265">Поддержка функций конференц-связи в Lync Server 2013 meetings</span><span class="sxs-lookup"><span data-stu-id="bd154-265">Conferencing Feature Support in Lync Server 2013 Meetings</span></span>

<span data-ttu-id="bd154-266">Lync Server 2013 предоставляет новые функции конференц-связи, которые становятся доступными пользователям после перемещения их учетных записей в Lync Server 2013 и входе в систему с помощью клиента Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="bd154-266">Lync Server 2013 provides new conferencing features that become available to users after their accounts are moved to Lync Server 2013 and they sign in with the Lync 2013 client.</span></span> <span data-ttu-id="bd154-267">К примерам относится представление "Коллекция видео", видео высокой четкости, общий доступ к PowerPoint и возможность отключения звука и видео участников при вводе собрания.</span><span class="sxs-lookup"><span data-stu-id="bd154-267">Examples include video gallery view, HD video, PowerPoint sharing, and the option to mute all attendee audio and video upon meeting entry.</span></span> <span data-ttu-id="bd154-268">Новые возможности, описанные в разделе [новые функции конференц-связи в Lync server 2013](lync-server-2013-new-conferencing-features.md) , а также новые возможности [для клиентов в Lync Server 2013](lync-server-2013-what-s-new-for-clients.md).</span><span class="sxs-lookup"><span data-stu-id="bd154-268">The new features are outlined in [New conferencing features in Lync Server 2013](lync-server-2013-new-conferencing-features.md) and [What's new for clients in Lync Server 2013](lync-server-2013-what-s-new-for-clients.md).</span></span>

<span data-ttu-id="bd154-269">В Lync Server 2013 для собраний некоторые функции конференций поддерживаются для пользователей, размещенных в различных версиях сервера и использующих разные клиенты и клиентские версии.</span><span class="sxs-lookup"><span data-stu-id="bd154-269">In Lync Server 2013 meetings, certain conferencing features are supported for users who are homed on different versions of the server and who are using different clients and client versions.</span></span> <span data-ttu-id="bd154-270">Когда клиенты присоединяются к собранию Lync Server 2013, у пользователей есть доступ к функциям и функциям, представленным в этой таблице.</span><span class="sxs-lookup"><span data-stu-id="bd154-270">When clients join a Lync Server 2013 meeting, users have access to the features and capabilities shown in this table.</span></span>


<table style="width:100%;">
<colgroup>
<col style="width: 11%" />
<col style="width: 11%" />
<col style="width: 11%" />
<col style="width: 11%" />
<col style="width: 11%" />
<col style="width: 11%" />
<col style="width: 11%" />
<col style="width: 11%" />
<col style="width: 11%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="bd154-271">Client</span><span class="sxs-lookup"><span data-stu-id="bd154-271">Client</span></span></th>
<th><span data-ttu-id="bd154-272">Обмен мгновенными сообщениями в одноранговой сети</span><span class="sxs-lookup"><span data-stu-id="bd154-272">Peer-to-peer IM</span></span></th>
<th><span data-ttu-id="bd154-273">Голос</span><span class="sxs-lookup"><span data-stu-id="bd154-273">Voice</span></span></th>
<th><span data-ttu-id="bd154-274">Видео</span><span class="sxs-lookup"><span data-stu-id="bd154-274">Video</span></span></th>
<th><span data-ttu-id="bd154-275">Совместное использование приложений</span><span class="sxs-lookup"><span data-stu-id="bd154-275">Application Sharing</span></span></th>
<th><span data-ttu-id="bd154-276">PowerPoint</span><span class="sxs-lookup"><span data-stu-id="bd154-276">PowerPoint</span></span></th>
<th><span data-ttu-id="bd154-277">Передача файлов</span><span class="sxs-lookup"><span data-stu-id="bd154-277">File Transfer</span></span></th>
<th><span data-ttu-id="bd154-278">Доска</span><span class="sxs-lookup"><span data-stu-id="bd154-278">Whiteboard</span></span></th>
<th><span data-ttu-id="bd154-279">Опрос</span><span class="sxs-lookup"><span data-stu-id="bd154-279">Polling</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="bd154-280">Lync 2013</span><span class="sxs-lookup"><span data-stu-id="bd154-280">Lync 2013</span></span></p></td>
<td><p><span data-ttu-id="bd154-281">Да</span><span class="sxs-lookup"><span data-stu-id="bd154-281">Yes</span></span></p></td>
<td><p><span data-ttu-id="bd154-282">Да</span><span class="sxs-lookup"><span data-stu-id="bd154-282">Yes</span></span></p></td>
<td><p><span data-ttu-id="bd154-283">Да</span><span class="sxs-lookup"><span data-stu-id="bd154-283">Yes</span></span></p></td>
<td><p><span data-ttu-id="bd154-284">Да</span><span class="sxs-lookup"><span data-stu-id="bd154-284">Yes</span></span></p></td>
<td><p><span data-ttu-id="bd154-285">Да</span><span class="sxs-lookup"><span data-stu-id="bd154-285">Yes</span></span></p></td>
<td><p><span data-ttu-id="bd154-286">Да</span><span class="sxs-lookup"><span data-stu-id="bd154-286">Yes</span></span></p></td>
<td><p><span data-ttu-id="bd154-287">Да</span><span class="sxs-lookup"><span data-stu-id="bd154-287">Yes</span></span></p></td>
<td><p><span data-ttu-id="bd154-288">Да</span><span class="sxs-lookup"><span data-stu-id="bd154-288">Yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bd154-289">Lync 2013 Basic</span><span class="sxs-lookup"><span data-stu-id="bd154-289">Lync 2013 Basic</span></span></p></td>
<td><p><span data-ttu-id="bd154-290">Да</span><span class="sxs-lookup"><span data-stu-id="bd154-290">Yes</span></span></p></td>
<td><p><span data-ttu-id="bd154-291">Да</span><span class="sxs-lookup"><span data-stu-id="bd154-291">Yes</span></span></p></td>
<td><p><span data-ttu-id="bd154-292">Да</span><span class="sxs-lookup"><span data-stu-id="bd154-292">Yes</span></span></p></td>
<td><p><span data-ttu-id="bd154-293">Да</span><span class="sxs-lookup"><span data-stu-id="bd154-293">Yes</span></span></p></td>
<td><p><span data-ttu-id="bd154-294">Да</span><span class="sxs-lookup"><span data-stu-id="bd154-294">Yes</span></span></p></td>
<td><p><span data-ttu-id="bd154-295">Да</span><span class="sxs-lookup"><span data-stu-id="bd154-295">Yes</span></span></p></td>
<td><p><span data-ttu-id="bd154-296">Да</span><span class="sxs-lookup"><span data-stu-id="bd154-296">Yes</span></span></p></td>
<td><p><span data-ttu-id="bd154-297">Да</span><span class="sxs-lookup"><span data-stu-id="bd154-297">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bd154-298">Lync Web App</span><span class="sxs-lookup"><span data-stu-id="bd154-298">Lync Web App</span></span></p></td>
<td><p><span data-ttu-id="bd154-299">Да</span><span class="sxs-lookup"><span data-stu-id="bd154-299">Yes</span></span></p></td>
<td><p><span data-ttu-id="bd154-300">Да</span><span class="sxs-lookup"><span data-stu-id="bd154-300">Yes</span></span></p></td>
<td><p><span data-ttu-id="bd154-301">Да</span><span class="sxs-lookup"><span data-stu-id="bd154-301">Yes</span></span></p></td>
<td><p><span data-ttu-id="bd154-302">Да</span><span class="sxs-lookup"><span data-stu-id="bd154-302">Yes</span></span></p></td>
<td><p><span data-ttu-id="bd154-303">Да2</span><span class="sxs-lookup"><span data-stu-id="bd154-303">Yes2</span></span></p></td>
<td><p><span data-ttu-id="bd154-304">Да</span><span class="sxs-lookup"><span data-stu-id="bd154-304">Yes</span></span></p></td>
<td><p><span data-ttu-id="bd154-305">Да</span><span class="sxs-lookup"><span data-stu-id="bd154-305">Yes</span></span></p></td>
<td><p><span data-ttu-id="bd154-306">Да</span><span class="sxs-lookup"><span data-stu-id="bd154-306">Yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bd154-307">Lync 2010</span><span class="sxs-lookup"><span data-stu-id="bd154-307">Lync 2010</span></span></p></td>
<td><p><span data-ttu-id="bd154-308">Да</span><span class="sxs-lookup"><span data-stu-id="bd154-308">Yes</span></span></p></td>
<td><p><span data-ttu-id="bd154-309">Да</span><span class="sxs-lookup"><span data-stu-id="bd154-309">Yes</span></span></p></td>
<td><p><span data-ttu-id="bd154-310">Да</span><span class="sxs-lookup"><span data-stu-id="bd154-310">Yes</span></span></p></td>
<td><p><span data-ttu-id="bd154-311">Да</span><span class="sxs-lookup"><span data-stu-id="bd154-311">Yes</span></span></p></td>
<td><p><span data-ttu-id="bd154-312">Yes3</span><span class="sxs-lookup"><span data-stu-id="bd154-312">Yes3</span></span></p></td>
<td><p><span data-ttu-id="bd154-313">Да</span><span class="sxs-lookup"><span data-stu-id="bd154-313">Yes</span></span></p></td>
<td><p><span data-ttu-id="bd154-314">Да</span><span class="sxs-lookup"><span data-stu-id="bd154-314">Yes</span></span></p></td>
<td><p><span data-ttu-id="bd154-315">Да</span><span class="sxs-lookup"><span data-stu-id="bd154-315">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bd154-316">Office Communicator 2007 R2 4</span><span class="sxs-lookup"><span data-stu-id="bd154-316">Office Communicator 2007 R2 4</span></span></p></td>
<td><p><span data-ttu-id="bd154-317">Да</span><span class="sxs-lookup"><span data-stu-id="bd154-317">Yes</span></span></p></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
</tbody>
</table>


<span data-ttu-id="bd154-318">1 в Office Communicator 2007 R2 доступен только общий доступ к рабочему столу (а не к совместному использованию программ).</span><span class="sxs-lookup"><span data-stu-id="bd154-318">1 In Office Communicator 2007 R2, only desktop sharing (and not program sharing) is available.</span></span>

<span data-ttu-id="bd154-319">2 Lync Server 2013 использует обновленный механизм для отправки файлов PowerPoint.</span><span class="sxs-lookup"><span data-stu-id="bd154-319">2 Lync Server 2013 uses an updated mechanism for uploading PowerPoint files.</span></span> <span data-ttu-id="bd154-320">Пользователи Lync Web App, присоединяющиеся к собранию, изначально запланированному на Lync Server 2010, могут просматривать презентации PowerPoint и перемещаться по ним, но не могут отправлять файлы PowerPoint.</span><span class="sxs-lookup"><span data-stu-id="bd154-320">Lync Web App users who join a meeting that was originally scheduled on Lync Server 2010 can view and navigate PowerPoint presentations, but cannot upload PowerPoint files.</span></span>

<span data-ttu-id="bd154-321">3 Если собрание было запланировано на Lync Server 2013, а слайды PowerPoint были отправлены клиентом Lync 2013, пользователи Lync 2010 имеют доступ к слайдам только для просмотра.</span><span class="sxs-lookup"><span data-stu-id="bd154-321">3 If the meeting was scheduled on Lync Server 2013 and PowerPoint slides were uploaded by a Lync 2013 client, Lync 2010 users have view-only access to the slides.</span></span> <span data-ttu-id="bd154-322">И наоборот, если слайды PowerPoint были отправлены пользователем Lync 2010, пользователи Lync Server 2013 смогут просматривать и просматривать слайды и, если сервер Office Web Apps настроен, получать доступ к новым возможностям, таким как более высокое разрешение, анимацию, переходы слайдов и внедренный видеоролик.</span><span class="sxs-lookup"><span data-stu-id="bd154-322">Conversely, if the PowerPoint slides were uploaded by a Lync 2010 user, Lync Server 2013 users will be able to view and slides and, if Office Web Apps Server is configured, access new capabilities such as higher resolution display, animations, slide transitions, and embedded video.</span></span> <span data-ttu-id="bd154-323">Дополнительную информацию можно узнать в статье [Настройка интеграции с сервером Office Web Apps и Lync Server 2013](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md).</span><span class="sxs-lookup"><span data-stu-id="bd154-323">For more information, see [Configuring integration with Office Web Apps Server and Lync Server 2013](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md).</span></span>

<span data-ttu-id="bd154-324">4The присутствия и функции обмена мгновенными сообщениями в Office Communicator 2007 R2 совместимы с Lync Server 2013, но функции конференц-связи не поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="bd154-324">4The presence and IM features in Office Communicator 2007 R2 are compatible with Lync Server 2013, but conferencing features are not.</span></span> <span data-ttu-id="bd154-325">Во время миграции с Office Communications Server 2007 R2 приложение Office Communicator 2007 R2 подходит для взаимодействия с присутствием и обменом мгновенными сообщениями, но пользователи должны использовать Lync Web App 2013, чтобы присоединиться к собраниям Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="bd154-325">During migration from Office Communications Server 2007 R2, Office Communicator 2007 R2 is suitable for presence and IM interoperability, but users should use Lync Web App 2013 to join Lync Server 2013 meetings.</span></span>

</div>

</div>

<div>

## <a name="scheduling-add-in-support"></a><span data-ttu-id="bd154-326">Планирование поддержки надстроек</span><span class="sxs-lookup"><span data-stu-id="bd154-326">Scheduling Add-in Support</span></span>

<span data-ttu-id="bd154-327">Серверная поддержка различных надстроек планирования согласуется с совместимостью версий сервера и клиентов.</span><span class="sxs-lookup"><span data-stu-id="bd154-327">Server support for the various scheduling add-ins is consistent with server and client version compatibility.</span></span> <span data-ttu-id="bd154-328">Как правило, в Lync Server 2013 поддерживаются следующие надстройки планирования.</span><span class="sxs-lookup"><span data-stu-id="bd154-328">In general, the following scheduling add-ins are supported on Lync Server 2013.</span></span> <span data-ttu-id="bd154-329">Однако предыдущие версии надстроек не предоставляют новые функции надстройки Lync 2013, такие как возможность отключения всех звуков и видео участников при вводе собрания.</span><span class="sxs-lookup"><span data-stu-id="bd154-329">However, previous versions of add-ins do not provide new Lync 2013 add-in features, such as the option to mute all attendee audio and video upon meeting entry.</span></span>

  - <span data-ttu-id="bd154-330">**Надстройка "собрание по сети" для Lync 2013**   предоставляет те же функции, что и надстройка "собрание по сети" для Lync 2010 с добавлением элементов управления для участников собрания, которые позволяют организаторов по умолчанию планировать конференции, для которых по умолчанию отключен звук участника и видео.</span><span class="sxs-lookup"><span data-stu-id="bd154-330">**Online Meeting Add-in for Lync 2013**   Provides the same features as the Online Meeting Add-in for Lync 2010, with the addition of attendee mute controls, which allow meeting organizers to schedule conferences that have attendee audio and video muted by default.</span></span> <span data-ttu-id="bd154-331">Кроме того, администраторы могут настроить приглашения на собрание Организации, добавив настраиваемую эмблему, URL-адрес, юридический URL-адрес или текст нижнего колонтитула.</span><span class="sxs-lookup"><span data-stu-id="bd154-331">Administrators can also customize the organization’s meeting invitations by adding a custom logo, a support URL, a legal disclaimer URL, or custom footer text.</span></span>

  - <span data-ttu-id="bd154-332">**Надстройка "собрание по сети" для Lync 2010**   предоставляет планирование для собраний Lync и удаляет возможность планирования конференций Office Live Meeting.</span><span class="sxs-lookup"><span data-stu-id="bd154-332">**Online Meeting Add-in for Lync 2010**   Provides scheduling for Lync meetings and removes the capability to schedule Office Live Meeting conferences.</span></span>

  - <span data-ttu-id="bd154-333">**Надстройка конференц-связи Office Communicator 2007 R2**   предоставляет планирование для конференций Office Live Meeting и конференций Office Communicator 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="bd154-333">**Office Communicator 2007 R2 Conferencing Add-in**   Provides scheduling for both Office Live Meeting conferences and Office Communicator 2007 R2 conferences.</span></span> 

<div>


> [!NOTE]  
> <span data-ttu-id="bd154-334">В Lync Server 2013 невозможно планировать конференции Live Meeting.</span><span class="sxs-lookup"><span data-stu-id="bd154-334">Live Meeting conferences cannot be scheduled on Lync Server 2013.</span></span>



</div>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="bd154-335">Планирование клиента</span><span class="sxs-lookup"><span data-stu-id="bd154-335">Scheduling Client</span></span></th>
<th><span data-ttu-id="bd154-336">Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bd154-336">Lync Server 2013</span></span></th>
<th><span data-ttu-id="bd154-337">Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="bd154-337">Lync Server 2010</span></span></th>
<th><span data-ttu-id="bd154-338">Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="bd154-338">Office Communications Server 2007 R2</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="bd154-339">Надстройка "собрание по сети" для Lync 2013 (может использоваться с Office 2013, Outlook 2010 и Outlook 2007)</span><span class="sxs-lookup"><span data-stu-id="bd154-339">Online Meeting Add-in for Lync 2013 (can be used with Office 2013, Outlook 2010, and Outlook 2007)</span></span></p></td>
<td><p><span data-ttu-id="bd154-340">Поддерживается</span><span class="sxs-lookup"><span data-stu-id="bd154-340">Supported</span></span></p></td>
<td><p><span data-ttu-id="bd154-341">Поддерживается (новые функции надстроек недоступны)</span><span class="sxs-lookup"><span data-stu-id="bd154-341">Supported (new add-in features not available)</span></span></p></td>
<td><p><span data-ttu-id="bd154-342">Не поддерживается</span><span class="sxs-lookup"><span data-stu-id="bd154-342">Not Supported</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bd154-343">Веб-планировщик Lync 2013</span><span class="sxs-lookup"><span data-stu-id="bd154-343">Lync 2013 Web Scheduler</span></span></p></td>
<td><p><span data-ttu-id="bd154-344">Поддерживается</span><span class="sxs-lookup"><span data-stu-id="bd154-344">Supported</span></span></p></td>
<td><p><span data-ttu-id="bd154-345">Не поддерживается</span><span class="sxs-lookup"><span data-stu-id="bd154-345">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="bd154-346">Не поддерживается</span><span class="sxs-lookup"><span data-stu-id="bd154-346">Not Supported</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bd154-347">Надстройка "собрание по сети" для Lync 2010</span><span class="sxs-lookup"><span data-stu-id="bd154-347">Online Meeting Add-in for Lync 2010</span></span></p></td>
<td><p><span data-ttu-id="bd154-348">Поддерживается</span><span class="sxs-lookup"><span data-stu-id="bd154-348">Supported</span></span></p></td>
<td><p><span data-ttu-id="bd154-349">Поддерживается</span><span class="sxs-lookup"><span data-stu-id="bd154-349">Supported</span></span></p></td>
<td><p><span data-ttu-id="bd154-350">Не поддерживается</span><span class="sxs-lookup"><span data-stu-id="bd154-350">Not Supported</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bd154-351">Надстройка конференц-связи Office Communicator 2007 R2</span><span class="sxs-lookup"><span data-stu-id="bd154-351">Office Communicator 2007 R2 Conferencing Add-in</span></span></p></td>
<td><p><span data-ttu-id="bd154-352">Не поддерживается</span><span class="sxs-lookup"><span data-stu-id="bd154-352">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="bd154-353">Поддерживается</span><span class="sxs-lookup"><span data-stu-id="bd154-353">Supported</span></span></p></td>
<td><p><span data-ttu-id="bd154-354">Поддерживается</span><span class="sxs-lookup"><span data-stu-id="bd154-354">Supported</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="support-for-joining-meetings"></a><span data-ttu-id="bd154-355">Поддержка присоединения к собраниям</span><span class="sxs-lookup"><span data-stu-id="bd154-355">Support for Joining Meetings</span></span>

<span data-ttu-id="bd154-356">Все клиенты, поддерживаемые Lync Server 2013, могут присоединяться к собраниям Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="bd154-356">All of the clients that Lync Server 2013 supports are allowed to join Lync 2013 meetings.</span></span> <span data-ttu-id="bd154-357">Так как Lync Web App является веб-компонентом сервера, то в тех случаях, когда Lync Web App используется для присоединения к собранию Lync Server 2013, всегда используется более новая версия Lync Web App.</span><span class="sxs-lookup"><span data-stu-id="bd154-357">Because Lync Web App is a web component of the server, in cases where Lync Web App is used to join a Lync Server 2013 meeting, the newer version of Lync Web App is always used.</span></span>

<span data-ttu-id="bd154-358">Пользователи Lync 2013 могут присоединяться к собраниям, размещенным на Lync 2010 и Office Communications Server 2007 R2, с возможностью масштабирования.</span><span class="sxs-lookup"><span data-stu-id="bd154-358">Lync 2013 clients can join meetings hosted on Lync 2010 and Office Communications Server 2007 R2 with scaled-down functionality.</span></span> <span data-ttu-id="bd154-359">Функции для собраний ограничены версией сервера, на котором размещается собрание.</span><span class="sxs-lookup"><span data-stu-id="bd154-359">In-meeting features are limited by the version of the server on which the meeting is hosted.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="bd154-360">См. также</span><span class="sxs-lookup"><span data-stu-id="bd154-360">See Also</span></span>


[<span data-ttu-id="bd154-361">Требования к приложению для Магазина Windows Lync для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bd154-361">Lync Windows Store app requirements for Lync Server 2013</span></span>](lync-server-2013-lync-windows-store-app-requirements.md)  
[<span data-ttu-id="bd154-362">Новые возможности конференц-связи в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bd154-362">New conferencing features in Lync Server 2013</span></span>](lync-server-2013-new-conferencing-features.md)  
[<span data-ttu-id="bd154-363">Новые возможности для клиентов в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bd154-363">What's new for clients in Lync Server 2013</span></span>](lync-server-2013-what-s-new-for-clients.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

