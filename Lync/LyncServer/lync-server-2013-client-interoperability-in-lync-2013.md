---
title: 'Lync Server 2013: взаимодействие клиентов в Lync 2013'
description: 'Lync Server 2013: взаимодействие клиентов в Lync 2013.'
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
ms.openlocfilehash: 8ea6e90d9479f03dd6d946787e70a2b3cc078699
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48549615"
---
# <a name="client-interoperability-in-lync-2013"></a><span data-ttu-id="20bc3-103">Взаимодействие клиентов в Lync 2013</span><span class="sxs-lookup"><span data-stu-id="20bc3-103">Client interoperability in Lync 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="20bc3-104">_**Последнее изменение темы:** 2016-03-04_</span><span class="sxs-lookup"><span data-stu-id="20bc3-104">_**Topic Last Modified:** 2016-03-04_</span></span>

<span data-ttu-id="20bc3-105">В этом разделе рассказывается о возможности совместного использования клиентами Microsoft Lync Server 2013 и взаимодействии с клиентами из более ранних версий Lync Server и Office Communications Server.</span><span class="sxs-lookup"><span data-stu-id="20bc3-105">This topic discusses the ability of Microsoft Lync Server 2013 clients to coexist and interact with clients from earlier versions of Lync Server and Office Communications Server.</span></span>

<div>

## <a name="server-and-client-compatibility"></a><span data-ttu-id="20bc3-106">Совместимость серверов и клиентов</span><span class="sxs-lookup"><span data-stu-id="20bc3-106">Server and Client Compatibility</span></span>

<span data-ttu-id="20bc3-107">В следующей таблице показаны поддерживаемые сочетания версий клиентов и серверов.</span><span class="sxs-lookup"><span data-stu-id="20bc3-107">The following table shows the supported combinations of client versions and server versions.</span></span> <span data-ttu-id="20bc3-108">В этой таблице показано, поддерживается ли вход, когда клиент пытается подключиться к указанному серверу.</span><span class="sxs-lookup"><span data-stu-id="20bc3-108">This table indicates whether sign-in is supported when the client attempts to connect to the server indicated.</span></span> <span data-ttu-id="20bc3-109">Lync Server 2013 поддерживает предыдущую версию клиента.</span><span class="sxs-lookup"><span data-stu-id="20bc3-109">Lync Server 2013 supports the previous client version.</span></span> <span data-ttu-id="20bc3-110">Кроме того, в отличие от предыдущих выпусков, Lync Server 2010 поддерживает новые клиенты Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="20bc3-110">Also, unlike previous releases, Lync Server 2010 supports the new Lync 2013 clients.</span></span> <span data-ttu-id="20bc3-111">Это позволяет организациям, которые обновляются с Lync Server 2010, развертывать новые клиенты независимо от обновлений Lync Server.</span><span class="sxs-lookup"><span data-stu-id="20bc3-111">This allows organizations who are upgrading from Lync Server 2010 to roll out new clients independent of Lync Server upgrades.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="20bc3-112">Клиент</span><span class="sxs-lookup"><span data-stu-id="20bc3-112">Client</span></span></th>
<th><span data-ttu-id="20bc3-113">Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="20bc3-113">Lync Server 2013</span></span></th>
<th><span data-ttu-id="20bc3-114">Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="20bc3-114">Lync Server 2010</span></span></th>
<th><span data-ttu-id="20bc3-115">Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="20bc3-115">Office Communications Server 2007 R2</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="20bc3-116">Lync 2013</span><span class="sxs-lookup"><span data-stu-id="20bc3-116">Lync 2013</span></span></p></td>
<td><p><span data-ttu-id="20bc3-117">Поддерживается</span><span class="sxs-lookup"><span data-stu-id="20bc3-117">Supported</span></span></p></td>
<td><p><span data-ttu-id="20bc3-118">Supported5</span><span class="sxs-lookup"><span data-stu-id="20bc3-118">Supported5</span></span></p></td>
<td><p><span data-ttu-id="20bc3-119">Не поддерживается</span><span class="sxs-lookup"><span data-stu-id="20bc3-119">Not Supported</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="20bc3-120">Lync 2013 Basic</span><span class="sxs-lookup"><span data-stu-id="20bc3-120">Lync 2013 Basic</span></span></p></td>
<td><p><span data-ttu-id="20bc3-121">Поддерживается</span><span class="sxs-lookup"><span data-stu-id="20bc3-121">Supported</span></span></p></td>
<td><p><span data-ttu-id="20bc3-122">Поддерживается</span><span class="sxs-lookup"><span data-stu-id="20bc3-122">Supported</span></span></p></td>
<td><p><span data-ttu-id="20bc3-123">Не поддерживается</span><span class="sxs-lookup"><span data-stu-id="20bc3-123">Not Supported</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="20bc3-124">Lync Web App 2013</span><span class="sxs-lookup"><span data-stu-id="20bc3-124">Lync Web App 2013</span></span></p></td>
<td><p><span data-ttu-id="20bc3-125">Поддерживается</span><span class="sxs-lookup"><span data-stu-id="20bc3-125">Supported</span></span></p></td>
<td><p><span data-ttu-id="20bc3-126">Не поддерживается</span><span class="sxs-lookup"><span data-stu-id="20bc3-126">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="20bc3-127">Не поддерживается</span><span class="sxs-lookup"><span data-stu-id="20bc3-127">Not Supported</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="20bc3-128">Lync 2010</span><span class="sxs-lookup"><span data-stu-id="20bc3-128">Lync 2010</span></span></p></td>
<td><p><span data-ttu-id="20bc3-129">Поддерживается</span><span class="sxs-lookup"><span data-stu-id="20bc3-129">Supported</span></span></p></td>
<td><p><span data-ttu-id="20bc3-130">Поддерживается</span><span class="sxs-lookup"><span data-stu-id="20bc3-130">Supported</span></span></p></td>
<td><p><span data-ttu-id="20bc3-131">Не поддерживается</span><span class="sxs-lookup"><span data-stu-id="20bc3-131">Not Supported</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="20bc3-132">Lync 2010 Attendant</span><span class="sxs-lookup"><span data-stu-id="20bc3-132">Lync 2010 Attendant</span></span></p></td>
<td><p><span data-ttu-id="20bc3-133">Поддерживается</span><span class="sxs-lookup"><span data-stu-id="20bc3-133">Supported</span></span></p></td>
<td><p><span data-ttu-id="20bc3-134">Поддерживается</span><span class="sxs-lookup"><span data-stu-id="20bc3-134">Supported</span></span></p></td>
<td><p><span data-ttu-id="20bc3-135">Не поддерживается</span><span class="sxs-lookup"><span data-stu-id="20bc3-135">Not Supported</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="20bc3-136">Lync 2010 Group Chat</span><span class="sxs-lookup"><span data-stu-id="20bc3-136">Lync 2010 Group Chat</span></span></p></td>
<td><p><span data-ttu-id="20bc3-137">Supported1</span><span class="sxs-lookup"><span data-stu-id="20bc3-137">Supported1</span></span></p></td>
<td><p><span data-ttu-id="20bc3-138">Supported2</span><span class="sxs-lookup"><span data-stu-id="20bc3-138">Supported2</span></span></p></td>
<td><p><span data-ttu-id="20bc3-139">Неприменимо</span><span class="sxs-lookup"><span data-stu-id="20bc3-139">Not Applicable</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="20bc3-140">Lync Web App 2010</span><span class="sxs-lookup"><span data-stu-id="20bc3-140">Lync Web App 2010</span></span></p></td>
<td><p><span data-ttu-id="20bc3-141">Не поддерживается</span><span class="sxs-lookup"><span data-stu-id="20bc3-141">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="20bc3-142">Поддерживается</span><span class="sxs-lookup"><span data-stu-id="20bc3-142">Supported</span></span></p></td>
<td><p><span data-ttu-id="20bc3-143">Не поддерживается</span><span class="sxs-lookup"><span data-stu-id="20bc3-143">Not Supported</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="20bc3-144">Lync 2010 Attendee</span><span class="sxs-lookup"><span data-stu-id="20bc3-144">Lync 2010 Attendee</span></span></p></td>
<td><p><span data-ttu-id="20bc3-145">Не Supported3</span><span class="sxs-lookup"><span data-stu-id="20bc3-145">Not Supported3</span></span></p></td>
<td><p><span data-ttu-id="20bc3-146">Поддерживается</span><span class="sxs-lookup"><span data-stu-id="20bc3-146">Supported</span></span></p></td>
<td><p><span data-ttu-id="20bc3-147">Не поддерживается</span><span class="sxs-lookup"><span data-stu-id="20bc3-147">Not Supported</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="20bc3-148">Office Communicator 2007 R2</span><span class="sxs-lookup"><span data-stu-id="20bc3-148">Office Communicator 2007 R2</span></span></p></td>
<td><p><span data-ttu-id="20bc3-149">Interoperable4</span><span class="sxs-lookup"><span data-stu-id="20bc3-149">Interoperable4</span></span></p></td>
<td><p><span data-ttu-id="20bc3-150">Поддерживается</span><span class="sxs-lookup"><span data-stu-id="20bc3-150">Supported</span></span></p></td>
<td><p><span data-ttu-id="20bc3-151">Поддерживается</span><span class="sxs-lookup"><span data-stu-id="20bc3-151">Supported</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="20bc3-152">Помощник Microsoft Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="20bc3-152">Microsoft Office Communications Server 2007 R2 Attendant</span></span></p></td>
<td><p><span data-ttu-id="20bc3-153">Не поддерживается</span><span class="sxs-lookup"><span data-stu-id="20bc3-153">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="20bc3-154">Поддерживается</span><span class="sxs-lookup"><span data-stu-id="20bc3-154">Supported</span></span></p></td>
<td><p><span data-ttu-id="20bc3-155">Поддерживается</span><span class="sxs-lookup"><span data-stu-id="20bc3-155">Supported</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="20bc3-156">Office Communicator 2007</span><span class="sxs-lookup"><span data-stu-id="20bc3-156">Office Communicator 2007</span></span></p></td>
<td><p><span data-ttu-id="20bc3-157">Не поддерживается</span><span class="sxs-lookup"><span data-stu-id="20bc3-157">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="20bc3-158">Поддерживается</span><span class="sxs-lookup"><span data-stu-id="20bc3-158">Supported</span></span></p></td>
<td><p><span data-ttu-id="20bc3-159">Поддерживается</span><span class="sxs-lookup"><span data-stu-id="20bc3-159">Supported</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="20bc3-160">Office Live Meeting 2007</span><span class="sxs-lookup"><span data-stu-id="20bc3-160">Office Live Meeting 2007</span></span></p></td>
<td><p><span data-ttu-id="20bc3-161">Не поддерживается</span><span class="sxs-lookup"><span data-stu-id="20bc3-161">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="20bc3-162">Поддерживается</span><span class="sxs-lookup"><span data-stu-id="20bc3-162">Supported</span></span></p></td>
<td><p><span data-ttu-id="20bc3-163">Поддерживается</span><span class="sxs-lookup"><span data-stu-id="20bc3-163">Supported</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="20bc3-164">Приложение Lync для Магазина Windows</span><span class="sxs-lookup"><span data-stu-id="20bc3-164">Lync Windows Store app</span></span></p></td>
<td><p><span data-ttu-id="20bc3-165">Поддерживается</span><span class="sxs-lookup"><span data-stu-id="20bc3-165">Supported</span></span></p></td>
<td><p><span data-ttu-id="20bc3-166">Поддерживается</span><span class="sxs-lookup"><span data-stu-id="20bc3-166">Supported</span></span></p></td>
<td><p><span data-ttu-id="20bc3-167">Не поддерживается</span><span class="sxs-lookup"><span data-stu-id="20bc3-167">Not Supported</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="20bc3-168">1For Details: [Migration from Lync server 2010, Group Chat или Office Communications Server 2007 R2 Group Chat to Lync server 2013, сервер сохраняемого чата](migration-from-lync-server-2010-group-chat-or-office-communications-server-2007-r2-group-chat-to-lync-server-2013-persistent-chat-server.md).</span><span class="sxs-lookup"><span data-stu-id="20bc3-168">1For details, see [Migration from Lync Server 2010, Group Chat or Office Communications Server 2007 R2 Group Chat to Lync Server 2013, Persistent Chat Server](migration-from-lync-server-2010-group-chat-or-office-communications-server-2007-r2-group-chat-to-lync-server-2013-persistent-chat-server.md).</span></span>

<span data-ttu-id="20bc3-169">2In Microsoft Lync Server 2010, доступны функции группового чата с сервером группового чата, доверенным сторонним приложением для Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="20bc3-169">2In Microsoft Lync Server 2010, group chat functionality was available with Group Chat Server, a third-party trusted application for Lync Server 2010.</span></span> <span data-ttu-id="20bc3-170">Клиенты Lync 2013 несовместимы с Lync Server 2010, группового чата.</span><span class="sxs-lookup"><span data-stu-id="20bc3-170">Lync 2013 clients are not compatible with Lync Server 2010, Group Chat.</span></span>

<span data-ttu-id="20bc3-171">3Lync Web App 2013 теперь предоставляет полный интерфейс для собраний, включая аудио-и видеоданные, и считается заменой участнику Lync 2010.</span><span class="sxs-lookup"><span data-stu-id="20bc3-171">3Lync Web App 2013 now provides a full in-meeting experience, including computer audio and video, and is considered the replacement for Lync 2010 Attendee.</span></span> <span data-ttu-id="20bc3-172">Lync 2010 участник будет подключаться к Lync Server 2013 только при использовании неподдерживаемого браузера (Internet Explorer 6 или Internet Explorer 7) и Windows XP.</span><span class="sxs-lookup"><span data-stu-id="20bc3-172">Lync 2010 Attendee will connect to Lync Server 2013 only when you are using an unsupported browser (Internet Explorer 6 or Internet Explorer 7) and Windows XP.</span></span>

<span data-ttu-id="20bc3-173">4The присутствия и функции обмена мгновенными сообщениями в Office Communicator 2007 R2 совместимы с Lync Server 2013, но функции конференц-связи не поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="20bc3-173">4The presence and IM features in Office Communicator 2007 R2 are compatible with Lync Server 2013, but conferencing features are not.</span></span> <span data-ttu-id="20bc3-174">Во время миграции с Office Communications Server 2007 R2 приложение Office Communicator 2007 R2 подходит для взаимодействия с присутствием и обменом мгновенными сообщениями, но пользователи должны использовать Lync Web App 2013, чтобы присоединиться к собраниям Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="20bc3-174">During migration from Office Communications Server 2007 R2, Office Communicator 2007 R2 is suitable for presence and IM interoperability, but users should use Lync Web App 2013 to join Lync Server 2013 meetings.</span></span>

<span data-ttu-id="20bc3-175">5 для получения ограничений обратитесь к разделу "Поддержка функций конференц-связи для клиентов Lync 2013 в Lync Server 2010 для собраний" Далее в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="20bc3-175">5 For limitations, see "Conferencing Feature Support for Lync 2013 Clients in Lync Server 2010 Meetings" later in this topic.</span></span>

</div>

<div>

## <a name="interoperability-among-clients"></a><span data-ttu-id="20bc3-176">Взаимодействие между клиентами</span><span class="sxs-lookup"><span data-stu-id="20bc3-176">Interoperability among Clients</span></span>

<span data-ttu-id="20bc3-177">В выпуске Lync Server 2013 различные клиентские версии могут беспрепятственно взаимодействовать как в одноранговых, так и в сценариях конференц-связи.</span><span class="sxs-lookup"><span data-stu-id="20bc3-177">With the Lync Server 2013 release, various client versions can interact seamlessly in both peer-to-peer and conferencing scenarios.</span></span> <span data-ttu-id="20bc3-178">В этом разделе описывается доступность функций, когда пользователи взаимодействуют с другими пользователями, использующими разные версии клиентов и серверов.</span><span class="sxs-lookup"><span data-stu-id="20bc3-178">This section discusses feature availability when users interact with other users who are using different versions of clients and servers.</span></span>

<div>

## <a name="peer-to-peer-feature-support"></a><span data-ttu-id="20bc3-179">Поддержка одноранговых функций</span><span class="sxs-lookup"><span data-stu-id="20bc3-179">Peer-to-Peer Feature Support</span></span>

<span data-ttu-id="20bc3-180">Одноранговые функции поддерживаются для пользователей, размещенных в различных версиях сервера и использующих разные версии клиентов.</span><span class="sxs-lookup"><span data-stu-id="20bc3-180">Peer-to-peer features are supported for users who are homed on different versions of the server and who are using different client versions.</span></span> <span data-ttu-id="20bc3-181">Функции конечного пользователя и доступные функции соответствуют возможностям клиента пользователя и версии сервера, на котором выполнен вход пользователя.</span><span class="sxs-lookup"><span data-stu-id="20bc3-181">The end-user experience and available features are consistent with the capabilities of the user’s client and the version of the server the user is signed in to.</span></span> <span data-ttu-id="20bc3-182">Другими словами:</span><span class="sxs-lookup"><span data-stu-id="20bc3-182">In other words:</span></span>

  - <span data-ttu-id="20bc3-183">Если пользователь вошел в Lync Server 2013 с более старым клиентом, он будет иметь такой же интерфейс, что и для пользователя.</span><span class="sxs-lookup"><span data-stu-id="20bc3-183">If a user is signed in to Lync Server 2013 with an older client, the user will have the same experience he or she is used to.</span></span> <span data-ttu-id="20bc3-184">Никакие новые функции, введенные в Lync Server 2013, будут недоступны до тех пор, пока клиент пользователя не будет обновлен.</span><span class="sxs-lookup"><span data-stu-id="20bc3-184">None of the new features introduced in Lync Server 2013 will be available until the user’s client is upgraded.</span></span> <span data-ttu-id="20bc3-185">Примеры включают представление "Коллекция видео", видео в формате HD, обновленный общий доступ к PowerPoint и возможность отключения звука и видео участников при вводе собрания.</span><span class="sxs-lookup"><span data-stu-id="20bc3-185">Examples include video gallery view, HD video, updated PowerPoint sharing, and the option to mute all attendee audio and video upon meeting entry.</span></span> <span data-ttu-id="20bc3-186">Новые возможности, описанные в разделе [новые функции конференц-связи в Lync server 2013](lync-server-2013-new-conferencing-features.md) , а также новые возможности [для клиентов в Lync Server 2013](lync-server-2013-what-s-new-for-clients.md).</span><span class="sxs-lookup"><span data-stu-id="20bc3-186">The new features are outlined in [New conferencing features in Lync Server 2013](lync-server-2013-new-conferencing-features.md) and [What's new for clients in Lync Server 2013](lync-server-2013-what-s-new-for-clients.md).</span></span>

  - <span data-ttu-id="20bc3-187">Если пользователь вошел в Lync Server 2010 с клиентом Lync 2013, все новые функции, не поддерживаемые в Lync Server 2010, будут недоступны до тех пор, пока пользователь не будет перемещен в Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="20bc3-187">If a user is signed in to Lync Server 2010 with a Lync 2013 client, any new features not supported by Lync Server 2010 will be unavailable until the user is moved to Lync Server 2013.</span></span>

<span data-ttu-id="20bc3-188">В следующей таблице сравнивается доступность функций в одноранговых сеансах, где клиент входит в состав Lync Server 2013 или Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="20bc3-188">The following table compares feature availability in peer-to-peer sessions where the client is signed in to either Lync Server 2013 or Lync Server 2010.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="20bc3-189">Lync Web App и Lync 2010 участник являются клиентами только для собраний и не включены в эту таблицу.</span><span class="sxs-lookup"><span data-stu-id="20bc3-189">Lync Web App and Lync 2010 Attendee are meeting-only clients and aren’t included in this table.</span></span>



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
<th><span data-ttu-id="20bc3-190">Клиент</span><span class="sxs-lookup"><span data-stu-id="20bc3-190">Client</span></span></th>
<th><span data-ttu-id="20bc3-191">Обмен мгновенными сообщениями</span><span class="sxs-lookup"><span data-stu-id="20bc3-191">Instant Messaging</span></span></th>
<th><span data-ttu-id="20bc3-192">Присутствие</span><span class="sxs-lookup"><span data-stu-id="20bc3-192">Presence</span></span></th>
<th><span data-ttu-id="20bc3-193">Голос</span><span class="sxs-lookup"><span data-stu-id="20bc3-193">Voice</span></span></th>
<th><span data-ttu-id="20bc3-194">Видео</span><span class="sxs-lookup"><span data-stu-id="20bc3-194">Video</span></span></th>
<th><span data-ttu-id="20bc3-195">Совместное использование приложений</span><span class="sxs-lookup"><span data-stu-id="20bc3-195">Application Sharing</span></span></th>
<th><span data-ttu-id="20bc3-196">Передача файлов</span><span class="sxs-lookup"><span data-stu-id="20bc3-196">File Transfer</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="20bc3-197">Lync 2013</span><span class="sxs-lookup"><span data-stu-id="20bc3-197">Lync 2013</span></span></p></td>
<td><p><span data-ttu-id="20bc3-198">Да</span><span class="sxs-lookup"><span data-stu-id="20bc3-198">Yes</span></span></p></td>
<td><p><span data-ttu-id="20bc3-199">Да</span><span class="sxs-lookup"><span data-stu-id="20bc3-199">Yes</span></span></p></td>
<td><p><span data-ttu-id="20bc3-200">Да</span><span class="sxs-lookup"><span data-stu-id="20bc3-200">Yes</span></span></p></td>
<td><p><span data-ttu-id="20bc3-201">Да</span><span class="sxs-lookup"><span data-stu-id="20bc3-201">Yes</span></span></p></td>
<td><p><span data-ttu-id="20bc3-202">Да</span><span class="sxs-lookup"><span data-stu-id="20bc3-202">Yes</span></span></p></td>
<td><p><span data-ttu-id="20bc3-203">Да</span><span class="sxs-lookup"><span data-stu-id="20bc3-203">Yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="20bc3-204">Lync 2013 Basic</span><span class="sxs-lookup"><span data-stu-id="20bc3-204">Lync 2013 Basic</span></span></p></td>
<td><p><span data-ttu-id="20bc3-205">Да</span><span class="sxs-lookup"><span data-stu-id="20bc3-205">Yes</span></span></p></td>
<td><p><span data-ttu-id="20bc3-206">Да</span><span class="sxs-lookup"><span data-stu-id="20bc3-206">Yes</span></span></p></td>
<td><p><span data-ttu-id="20bc3-207">Да</span><span class="sxs-lookup"><span data-stu-id="20bc3-207">Yes</span></span></p></td>
<td><p><span data-ttu-id="20bc3-208">Да</span><span class="sxs-lookup"><span data-stu-id="20bc3-208">Yes</span></span></p></td>
<td><p><span data-ttu-id="20bc3-209">Да</span><span class="sxs-lookup"><span data-stu-id="20bc3-209">Yes</span></span></p></td>
<td><p><span data-ttu-id="20bc3-210">Да</span><span class="sxs-lookup"><span data-stu-id="20bc3-210">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="20bc3-211">Lync 2010</span><span class="sxs-lookup"><span data-stu-id="20bc3-211">Lync 2010</span></span></p></td>
<td><p><span data-ttu-id="20bc3-212">Да</span><span class="sxs-lookup"><span data-stu-id="20bc3-212">Yes</span></span></p></td>
<td><p><span data-ttu-id="20bc3-213">Да</span><span class="sxs-lookup"><span data-stu-id="20bc3-213">Yes</span></span></p></td>
<td><p><span data-ttu-id="20bc3-214">Да</span><span class="sxs-lookup"><span data-stu-id="20bc3-214">Yes</span></span></p></td>
<td><p><span data-ttu-id="20bc3-215">Да</span><span class="sxs-lookup"><span data-stu-id="20bc3-215">Yes</span></span></p></td>
<td><p><span data-ttu-id="20bc3-216">Да</span><span class="sxs-lookup"><span data-stu-id="20bc3-216">Yes</span></span></p></td>
<td><p><span data-ttu-id="20bc3-217">Да</span><span class="sxs-lookup"><span data-stu-id="20bc3-217">Yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="20bc3-218">Lync 2010 Attendant</span><span class="sxs-lookup"><span data-stu-id="20bc3-218">Lync 2010 Attendant</span></span></p></td>
<td><p><span data-ttu-id="20bc3-219">Да</span><span class="sxs-lookup"><span data-stu-id="20bc3-219">Yes</span></span></p></td>
<td><p><span data-ttu-id="20bc3-220">Да</span><span class="sxs-lookup"><span data-stu-id="20bc3-220">Yes</span></span></p></td>
<td><p><span data-ttu-id="20bc3-221">Да</span><span class="sxs-lookup"><span data-stu-id="20bc3-221">Yes</span></span></p></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="20bc3-222">Lync 2010 Mobile</span><span class="sxs-lookup"><span data-stu-id="20bc3-222">Lync 2010 Mobile</span></span></p></td>
<td><p><span data-ttu-id="20bc3-223">Да</span><span class="sxs-lookup"><span data-stu-id="20bc3-223">Yes</span></span></p></td>
<td><p><span data-ttu-id="20bc3-224">Да</span><span class="sxs-lookup"><span data-stu-id="20bc3-224">Yes</span></span></p></td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="20bc3-225">Lync Phone Edition</span><span class="sxs-lookup"><span data-stu-id="20bc3-225">Lync Phone Edition</span></span></p></td>
<td><p><span data-ttu-id="20bc3-226">Да</span><span class="sxs-lookup"><span data-stu-id="20bc3-226">Yes</span></span></p></td>
<td><p><span data-ttu-id="20bc3-227">Да</span><span class="sxs-lookup"><span data-stu-id="20bc3-227">Yes</span></span></p></td>
<td><p><span data-ttu-id="20bc3-228">Да</span><span class="sxs-lookup"><span data-stu-id="20bc3-228">Yes</span></span></p></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="20bc3-229">Office Communicator 2007 R2</span><span class="sxs-lookup"><span data-stu-id="20bc3-229">Office Communicator 2007 R2</span></span></p></td>
<td><p><span data-ttu-id="20bc3-230">Да</span><span class="sxs-lookup"><span data-stu-id="20bc3-230">Yes</span></span></p></td>
<td><p><span data-ttu-id="20bc3-231">Да</span><span class="sxs-lookup"><span data-stu-id="20bc3-231">Yes</span></span></p></td>
<td><p><span data-ttu-id="20bc3-232">Да</span><span class="sxs-lookup"><span data-stu-id="20bc3-232">Yes</span></span></p></td>
<td><p><span data-ttu-id="20bc3-233">Да</span><span class="sxs-lookup"><span data-stu-id="20bc3-233">Yes</span></span></p></td>
<td><p><span data-ttu-id="20bc3-234">Yes1</span><span class="sxs-lookup"><span data-stu-id="20bc3-234">Yes1</span></span></p></td>
<td><p><span data-ttu-id="20bc3-235">Да</span><span class="sxs-lookup"><span data-stu-id="20bc3-235">Yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="20bc3-236">Общедоступная служба обмена мгновенными сообщениями (AOL, Yahoo!)</span><span class="sxs-lookup"><span data-stu-id="20bc3-236">Public IM (AOL, Yahoo!)</span></span></p></td>
<td><p><span data-ttu-id="20bc3-237">Да</span><span class="sxs-lookup"><span data-stu-id="20bc3-237">Yes</span></span></p></td>
<td><p><span data-ttu-id="20bc3-238">Да</span><span class="sxs-lookup"><span data-stu-id="20bc3-238">Yes</span></span></p></td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="20bc3-239">Общедоступная служба обмена мгновенными сообщениями (MSN, Windows Live Messenger)</span><span class="sxs-lookup"><span data-stu-id="20bc3-239">Public IM (MSN, Windows Live Messenger)</span></span></p></td>
<td><p><span data-ttu-id="20bc3-240">Да</span><span class="sxs-lookup"><span data-stu-id="20bc3-240">Yes</span></span></p></td>
<td><p><span data-ttu-id="20bc3-241">Да</span><span class="sxs-lookup"><span data-stu-id="20bc3-241">Yes</span></span></p></td>
<td><p><span data-ttu-id="20bc3-242">Да</span><span class="sxs-lookup"><span data-stu-id="20bc3-242">Yes</span></span></p></td>
<td><p><span data-ttu-id="20bc3-243">Да</span><span class="sxs-lookup"><span data-stu-id="20bc3-243">Yes</span></span></p></td>
<td></td>
<td></td>
</tr>
</tbody>
</table>


<div>


> [!IMPORTANT]  
> <UL>
> <LI>
> <P><span data-ttu-id="20bc3-244">С 1 сентября 2012 г. Лицензия на подписку общедоступных служб обмена мгновенными сообщениями Microsoft Lync (PIC усл) больше недоступна для приобретения новых или обновленных договоров.</span><span class="sxs-lookup"><span data-stu-id="20bc3-244">As of September 1st, 2012, the Microsoft Lync Public IM Connectivity User Subscription License (PIC USL) is no longer available for the purchase for new or renewing agreements.</span></span> <span data-ttu-id="20bc3-245">Клиенты с активными лицензиями смогут продолжать Федерацию с помощью Yahoo!</span><span class="sxs-lookup"><span data-stu-id="20bc3-245">Customers with active licenses will be able to continue to federate with Yahoo!</span></span> <span data-ttu-id="20bc3-246">Messenger до даты завершения работы службы.</span><span class="sxs-lookup"><span data-stu-id="20bc3-246">Messenger until the service shutdown date.</span></span> <span data-ttu-id="20bc3-247">Дата окончания срока жизни 2014 для AOL и Yahoo!</span><span class="sxs-lookup"><span data-stu-id="20bc3-247">An end of life date of June 2014 for AOL and Yahoo!</span></span> <span data-ttu-id="20bc3-248">объявлено.</span><span class="sxs-lookup"><span data-stu-id="20bc3-248">has been announced.</span></span> <span data-ttu-id="20bc3-249">Дополнительные сведения см <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">в разделе Поддержка общедоступной службы обмена мгновенными сообщениями в Lync Server 2013</A>..</span><span class="sxs-lookup"><span data-stu-id="20bc3-249">For details, see <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Support for public instant messenger connectivity in Lync Server 2013</A>..</span></span></P>
> <LI>
> <P><span data-ttu-id="20bc3-250">УСЛ PIC — это лицензия на помесячную подписку на уровне пользователя, которая требуется для Lync Server или Office Communications Server для Федерации с Yahoo!</span><span class="sxs-lookup"><span data-stu-id="20bc3-250">The PIC USL is a per-user, per-month subscription license that is required for Lync Server or Office Communications Server to federate with Yahoo!</span></span> <span data-ttu-id="20bc3-251">Messenger.</span><span class="sxs-lookup"><span data-stu-id="20bc3-251">Messenger.</span></span> <span data-ttu-id="20bc3-252">Способность корпорации Майкрософт предоставлять эту службу зависит от поддержки компании Yahoo!, основного соглашения, для которого обновление не выполняется.</span><span class="sxs-lookup"><span data-stu-id="20bc3-252">Microsoft’s ability to provide this service has been contingent upon support from Yahoo!, the underlying agreement for which will not be renewed.</span></span></P>
> <LI>
> <P><span data-ttu-id="20bc3-253">Lync — это мощное средство для связи между организациями и пользователями мира.</span><span class="sxs-lookup"><span data-stu-id="20bc3-253">More than ever, Lync is a powerful tool for connecting across organizations and with individuals around the world.</span></span> <span data-ttu-id="20bc3-254">Для Федерации с Windows Live Messenger не требуется дополнительных лицензий на пользователей и устройств, не относящихся к стандарту Lync CAL.</span><span class="sxs-lookup"><span data-stu-id="20bc3-254">Federation with Windows Live Messenger requires no additional user/device licenses beyond the Lync Standard CAL.</span></span> <span data-ttu-id="20bc3-255">В этот список будет добавлена Федерация Skype, которая позволяет пользователям Lync достигать сотни миллионов людей с помощью обмена мгновенными сообщениями и голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="20bc3-255">Skype federation will be added to this list, enabling Lync users to reach hundreds of millions of people through IM and voice.</span></span></P></LI></UL>



</div>

<span data-ttu-id="20bc3-256">1 в Office Communicator 2007 R2 доступен только общий доступ к рабочему столу (а не к совместному использованию программ).</span><span class="sxs-lookup"><span data-stu-id="20bc3-256">1 In Office Communicator 2007 R2, only desktop sharing (and not program sharing) is available.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="20bc3-257">Общий доступ к рабочему столу Office Communicator 2007 R2 и Skype для бизнеса 2015 невозможно инициировать из нового клиента, когда применяется пользовательский интерфейс клиента Skype для бизнеса 2015.</span><span class="sxs-lookup"><span data-stu-id="20bc3-257">Desktop sharing between Office Communicator 2007 R2 and Skype for Business 2015 cannot be initiated from the newer client when the Skype for Business 2015 client user interface is enforced.</span></span>



</div>

</div>

<div>

## <a name="conferencing-feature-support-for-lync-2013-clients-in-lync-server-2010-meetings"></a><span data-ttu-id="20bc3-258">Поддержка функций конференц-связи для клиентов Lync 2013 в Lync Server 2010 для собраний</span><span class="sxs-lookup"><span data-stu-id="20bc3-258">Conferencing Feature Support for Lync 2013 Clients in Lync Server 2010 Meetings</span></span>

<span data-ttu-id="20bc3-259">Когда пользователи присоединяются к Lync Server 2010 meetings с клиентом Lync 2013, у них есть доступ к клиентским функциям Lync 2013 со следующими исключениями:</span><span class="sxs-lookup"><span data-stu-id="20bc3-259">When users join Lync Server 2010 meetings with a Lync 2013 client, they have access to Lync 2013 client features with the following exceptions:</span></span>

  - <span data-ttu-id="20bc3-260">В параметрах управления **участниками** , доступ к которым осуществляется путем указания значка "люди" в окне собрания, параметр "не вести **мгновенный обмен мгновенными сообщениями** " не работает.</span><span class="sxs-lookup"><span data-stu-id="20bc3-260">In the **Participants** management options, which are accessible by pointing to the people icon in the meeting window, the **No Meeting IM** option does not function.</span></span>

  - <span data-ttu-id="20bc3-261">Представление галереи не работает в видеоконференциях.</span><span class="sxs-lookup"><span data-stu-id="20bc3-261">Gallery View does not function in video conferences.</span></span> <span data-ttu-id="20bc3-262">Пользователю развидится только активный динамик, а не все динамики.</span><span class="sxs-lookup"><span data-stu-id="20bc3-262">The user sees only the active speaker instead of all speakers.</span></span> <span data-ttu-id="20bc3-263">В списке выберите параметры **макета** недоступно **представление "коллекция** "</span><span class="sxs-lookup"><span data-stu-id="20bc3-263">In the list of **Pick a Layout** options, **Gallery View** is unavailable</span></span>

  - <span data-ttu-id="20bc3-264">Список участников по умолчанию отображается в видеоконференциях.</span><span class="sxs-lookup"><span data-stu-id="20bc3-264">The participant list displays by default in video conferences.</span></span>

  - <span data-ttu-id="20bc3-265">Когда вы щелкаете правой кнопкой мыши пользователя в списке участников, вы не сможете получить доступ к параметрам управления участниками **коллекции и закрепить** **его** в коллекции.</span><span class="sxs-lookup"><span data-stu-id="20bc3-265">When right-clicking a user in the participants list, the **Lock the Video Spotlight** and **Pin to Gallery** participant management options are unavailable.</span></span>

</div>

<div>

## <a name="conferencing-feature-support-in-lync-server-2013-meetings"></a><span data-ttu-id="20bc3-266">Поддержка функций конференц-связи в Lync Server 2013 meetings</span><span class="sxs-lookup"><span data-stu-id="20bc3-266">Conferencing Feature Support in Lync Server 2013 Meetings</span></span>

<span data-ttu-id="20bc3-267">Lync Server 2013 предоставляет новые функции конференц-связи, которые становятся доступными пользователям после перемещения их учетных записей в Lync Server 2013 и входе в систему с помощью клиента Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="20bc3-267">Lync Server 2013 provides new conferencing features that become available to users after their accounts are moved to Lync Server 2013 and they sign in with the Lync 2013 client.</span></span> <span data-ttu-id="20bc3-268">К примерам относится представление "Коллекция видео", видео высокой четкости, общий доступ к PowerPoint и возможность отключения звука и видео участников при вводе собрания.</span><span class="sxs-lookup"><span data-stu-id="20bc3-268">Examples include video gallery view, HD video, PowerPoint sharing, and the option to mute all attendee audio and video upon meeting entry.</span></span> <span data-ttu-id="20bc3-269">Новые возможности, описанные в разделе [новые функции конференц-связи в Lync server 2013](lync-server-2013-new-conferencing-features.md) , а также новые возможности [для клиентов в Lync Server 2013](lync-server-2013-what-s-new-for-clients.md).</span><span class="sxs-lookup"><span data-stu-id="20bc3-269">The new features are outlined in [New conferencing features in Lync Server 2013](lync-server-2013-new-conferencing-features.md) and [What's new for clients in Lync Server 2013](lync-server-2013-what-s-new-for-clients.md).</span></span>

<span data-ttu-id="20bc3-270">В Lync Server 2013 для собраний некоторые функции конференций поддерживаются для пользователей, размещенных в различных версиях сервера и использующих разные клиенты и клиентские версии.</span><span class="sxs-lookup"><span data-stu-id="20bc3-270">In Lync Server 2013 meetings, certain conferencing features are supported for users who are homed on different versions of the server and who are using different clients and client versions.</span></span> <span data-ttu-id="20bc3-271">Когда клиенты присоединяются к собранию Lync Server 2013, у пользователей есть доступ к функциям и функциям, представленным в этой таблице.</span><span class="sxs-lookup"><span data-stu-id="20bc3-271">When clients join a Lync Server 2013 meeting, users have access to the features and capabilities shown in this table.</span></span>


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
<th><span data-ttu-id="20bc3-272">Клиент</span><span class="sxs-lookup"><span data-stu-id="20bc3-272">Client</span></span></th>
<th><span data-ttu-id="20bc3-273">Обмен мгновенными сообщениями в одноранговой сети</span><span class="sxs-lookup"><span data-stu-id="20bc3-273">Peer-to-peer IM</span></span></th>
<th><span data-ttu-id="20bc3-274">Голос</span><span class="sxs-lookup"><span data-stu-id="20bc3-274">Voice</span></span></th>
<th><span data-ttu-id="20bc3-275">Видео</span><span class="sxs-lookup"><span data-stu-id="20bc3-275">Video</span></span></th>
<th><span data-ttu-id="20bc3-276">Совместное использование приложений</span><span class="sxs-lookup"><span data-stu-id="20bc3-276">Application Sharing</span></span></th>
<th><span data-ttu-id="20bc3-277">PowerPoint</span><span class="sxs-lookup"><span data-stu-id="20bc3-277">PowerPoint</span></span></th>
<th><span data-ttu-id="20bc3-278">Передача файлов</span><span class="sxs-lookup"><span data-stu-id="20bc3-278">File Transfer</span></span></th>
<th><span data-ttu-id="20bc3-279">Доска</span><span class="sxs-lookup"><span data-stu-id="20bc3-279">Whiteboard</span></span></th>
<th><span data-ttu-id="20bc3-280">Опрос</span><span class="sxs-lookup"><span data-stu-id="20bc3-280">Polling</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="20bc3-281">Lync 2013</span><span class="sxs-lookup"><span data-stu-id="20bc3-281">Lync 2013</span></span></p></td>
<td><p><span data-ttu-id="20bc3-282">Да</span><span class="sxs-lookup"><span data-stu-id="20bc3-282">Yes</span></span></p></td>
<td><p><span data-ttu-id="20bc3-283">Да</span><span class="sxs-lookup"><span data-stu-id="20bc3-283">Yes</span></span></p></td>
<td><p><span data-ttu-id="20bc3-284">Да</span><span class="sxs-lookup"><span data-stu-id="20bc3-284">Yes</span></span></p></td>
<td><p><span data-ttu-id="20bc3-285">Да</span><span class="sxs-lookup"><span data-stu-id="20bc3-285">Yes</span></span></p></td>
<td><p><span data-ttu-id="20bc3-286">Да</span><span class="sxs-lookup"><span data-stu-id="20bc3-286">Yes</span></span></p></td>
<td><p><span data-ttu-id="20bc3-287">Да</span><span class="sxs-lookup"><span data-stu-id="20bc3-287">Yes</span></span></p></td>
<td><p><span data-ttu-id="20bc3-288">Да</span><span class="sxs-lookup"><span data-stu-id="20bc3-288">Yes</span></span></p></td>
<td><p><span data-ttu-id="20bc3-289">Да</span><span class="sxs-lookup"><span data-stu-id="20bc3-289">Yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="20bc3-290">Lync 2013 Basic</span><span class="sxs-lookup"><span data-stu-id="20bc3-290">Lync 2013 Basic</span></span></p></td>
<td><p><span data-ttu-id="20bc3-291">Да</span><span class="sxs-lookup"><span data-stu-id="20bc3-291">Yes</span></span></p></td>
<td><p><span data-ttu-id="20bc3-292">Да</span><span class="sxs-lookup"><span data-stu-id="20bc3-292">Yes</span></span></p></td>
<td><p><span data-ttu-id="20bc3-293">Да</span><span class="sxs-lookup"><span data-stu-id="20bc3-293">Yes</span></span></p></td>
<td><p><span data-ttu-id="20bc3-294">Да</span><span class="sxs-lookup"><span data-stu-id="20bc3-294">Yes</span></span></p></td>
<td><p><span data-ttu-id="20bc3-295">Да</span><span class="sxs-lookup"><span data-stu-id="20bc3-295">Yes</span></span></p></td>
<td><p><span data-ttu-id="20bc3-296">Да</span><span class="sxs-lookup"><span data-stu-id="20bc3-296">Yes</span></span></p></td>
<td><p><span data-ttu-id="20bc3-297">Да</span><span class="sxs-lookup"><span data-stu-id="20bc3-297">Yes</span></span></p></td>
<td><p><span data-ttu-id="20bc3-298">Да</span><span class="sxs-lookup"><span data-stu-id="20bc3-298">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="20bc3-299">Lync Web App</span><span class="sxs-lookup"><span data-stu-id="20bc3-299">Lync Web App</span></span></p></td>
<td><p><span data-ttu-id="20bc3-300">Да</span><span class="sxs-lookup"><span data-stu-id="20bc3-300">Yes</span></span></p></td>
<td><p><span data-ttu-id="20bc3-301">Да</span><span class="sxs-lookup"><span data-stu-id="20bc3-301">Yes</span></span></p></td>
<td><p><span data-ttu-id="20bc3-302">Да</span><span class="sxs-lookup"><span data-stu-id="20bc3-302">Yes</span></span></p></td>
<td><p><span data-ttu-id="20bc3-303">Да</span><span class="sxs-lookup"><span data-stu-id="20bc3-303">Yes</span></span></p></td>
<td><p><span data-ttu-id="20bc3-304">Да2</span><span class="sxs-lookup"><span data-stu-id="20bc3-304">Yes2</span></span></p></td>
<td><p><span data-ttu-id="20bc3-305">Да</span><span class="sxs-lookup"><span data-stu-id="20bc3-305">Yes</span></span></p></td>
<td><p><span data-ttu-id="20bc3-306">Да</span><span class="sxs-lookup"><span data-stu-id="20bc3-306">Yes</span></span></p></td>
<td><p><span data-ttu-id="20bc3-307">Да</span><span class="sxs-lookup"><span data-stu-id="20bc3-307">Yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="20bc3-308">Lync 2010</span><span class="sxs-lookup"><span data-stu-id="20bc3-308">Lync 2010</span></span></p></td>
<td><p><span data-ttu-id="20bc3-309">Да</span><span class="sxs-lookup"><span data-stu-id="20bc3-309">Yes</span></span></p></td>
<td><p><span data-ttu-id="20bc3-310">Да</span><span class="sxs-lookup"><span data-stu-id="20bc3-310">Yes</span></span></p></td>
<td><p><span data-ttu-id="20bc3-311">Да</span><span class="sxs-lookup"><span data-stu-id="20bc3-311">Yes</span></span></p></td>
<td><p><span data-ttu-id="20bc3-312">Да</span><span class="sxs-lookup"><span data-stu-id="20bc3-312">Yes</span></span></p></td>
<td><p><span data-ttu-id="20bc3-313">Yes3</span><span class="sxs-lookup"><span data-stu-id="20bc3-313">Yes3</span></span></p></td>
<td><p><span data-ttu-id="20bc3-314">Да</span><span class="sxs-lookup"><span data-stu-id="20bc3-314">Yes</span></span></p></td>
<td><p><span data-ttu-id="20bc3-315">Да</span><span class="sxs-lookup"><span data-stu-id="20bc3-315">Yes</span></span></p></td>
<td><p><span data-ttu-id="20bc3-316">Да</span><span class="sxs-lookup"><span data-stu-id="20bc3-316">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="20bc3-317">Office Communicator 2007 R2 4</span><span class="sxs-lookup"><span data-stu-id="20bc3-317">Office Communicator 2007 R2 4</span></span></p></td>
<td><p><span data-ttu-id="20bc3-318">Да</span><span class="sxs-lookup"><span data-stu-id="20bc3-318">Yes</span></span></p></td>
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


<span data-ttu-id="20bc3-319">1 в Office Communicator 2007 R2 доступен только общий доступ к рабочему столу (а не к совместному использованию программ).</span><span class="sxs-lookup"><span data-stu-id="20bc3-319">1 In Office Communicator 2007 R2, only desktop sharing (and not program sharing) is available.</span></span>

<span data-ttu-id="20bc3-320">2 Lync Server 2013 использует обновленный механизм для отправки файлов PowerPoint.</span><span class="sxs-lookup"><span data-stu-id="20bc3-320">2 Lync Server 2013 uses an updated mechanism for uploading PowerPoint files.</span></span> <span data-ttu-id="20bc3-321">Пользователи Lync Web App, присоединяющиеся к собранию, изначально запланированному на Lync Server 2010, могут просматривать презентации PowerPoint и перемещаться по ним, но не могут отправлять файлы PowerPoint.</span><span class="sxs-lookup"><span data-stu-id="20bc3-321">Lync Web App users who join a meeting that was originally scheduled on Lync Server 2010 can view and navigate PowerPoint presentations, but cannot upload PowerPoint files.</span></span>

<span data-ttu-id="20bc3-322">3 Если собрание было запланировано на Lync Server 2013, а слайды PowerPoint были отправлены клиентом Lync 2013, пользователи Lync 2010 имеют доступ к слайдам только для просмотра.</span><span class="sxs-lookup"><span data-stu-id="20bc3-322">3 If the meeting was scheduled on Lync Server 2013 and PowerPoint slides were uploaded by a Lync 2013 client, Lync 2010 users have view-only access to the slides.</span></span> <span data-ttu-id="20bc3-323">И наоборот, если слайды PowerPoint были отправлены пользователем Lync 2010, пользователи Lync Server 2013 смогут просматривать и просматривать слайды, а если сервер Office Web Apps настроен, доступ к новым возможностям, таким как отображение, анимация, переходы слайдов и встроенное видео.</span><span class="sxs-lookup"><span data-stu-id="20bc3-323">Conversely, if the PowerPoint slides were uploaded by a Lync 2010 user, Lync Server 2013 users will be able to view and slides and, if Office Web Apps Server is configured, access new capabilities such as higher resolution display, animations, slide transitions, and embedded video.</span></span> <span data-ttu-id="20bc3-324">Дополнительную информацию можно узнать в статье [Настройка интеграции с сервером Office Web Apps и Lync Server 2013](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md).</span><span class="sxs-lookup"><span data-stu-id="20bc3-324">For more information, see [Configuring integration with Office Web Apps Server and Lync Server 2013](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md).</span></span>

<span data-ttu-id="20bc3-325">4The присутствия и функции обмена мгновенными сообщениями в Office Communicator 2007 R2 совместимы с Lync Server 2013, но функции конференц-связи не поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="20bc3-325">4The presence and IM features in Office Communicator 2007 R2 are compatible with Lync Server 2013, but conferencing features are not.</span></span> <span data-ttu-id="20bc3-326">Во время миграции с Office Communications Server 2007 R2 приложение Office Communicator 2007 R2 подходит для взаимодействия с присутствием и обменом мгновенными сообщениями, но пользователи должны использовать Lync Web App 2013, чтобы присоединиться к собраниям Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="20bc3-326">During migration from Office Communications Server 2007 R2, Office Communicator 2007 R2 is suitable for presence and IM interoperability, but users should use Lync Web App 2013 to join Lync Server 2013 meetings.</span></span>

</div>

</div>

<div>

## <a name="scheduling-add-in-support"></a><span data-ttu-id="20bc3-327">Планирование поддержки надстроек</span><span class="sxs-lookup"><span data-stu-id="20bc3-327">Scheduling Add-in Support</span></span>

<span data-ttu-id="20bc3-328">Серверная поддержка различных надстроек планирования согласуется с совместимостью версий сервера и клиентов.</span><span class="sxs-lookup"><span data-stu-id="20bc3-328">Server support for the various scheduling add-ins is consistent with server and client version compatibility.</span></span> <span data-ttu-id="20bc3-329">Как правило, в Lync Server 2013 поддерживаются следующие надстройки планирования.</span><span class="sxs-lookup"><span data-stu-id="20bc3-329">In general, the following scheduling add-ins are supported on Lync Server 2013.</span></span> <span data-ttu-id="20bc3-330">Однако предыдущие версии надстроек не предоставляют новые функции надстройки Lync 2013, такие как возможность отключения всех звуков и видео участников при вводе собрания.</span><span class="sxs-lookup"><span data-stu-id="20bc3-330">However, previous versions of add-ins do not provide new Lync 2013 add-in features, such as the option to mute all attendee audio and video upon meeting entry.</span></span>

  - <span data-ttu-id="20bc3-331">**Надстройка "собрание по сети" для Lync 2013**     Предоставляет те же функции, что и надстройка "собрание по сети" для Lync 2010, с добавлением элементов управления для участников собрания, которые позволяют организаторов по умолчанию планировать конференции, для которых по умолчанию отключен звук участника и видео.</span><span class="sxs-lookup"><span data-stu-id="20bc3-331">**Online Meeting Add-in for Lync 2013**   Provides the same features as the Online Meeting Add-in for Lync 2010, with the addition of attendee mute controls, which allow meeting organizers to schedule conferences that have attendee audio and video muted by default.</span></span> <span data-ttu-id="20bc3-332">Кроме того, администраторы могут настроить приглашения на собрание Организации, добавив настраиваемую эмблему, URL-адрес, юридический URL-адрес или текст нижнего колонтитула.</span><span class="sxs-lookup"><span data-stu-id="20bc3-332">Administrators can also customize the organization’s meeting invitations by adding a custom logo, a support URL, a legal disclaimer URL, or custom footer text.</span></span>

  - <span data-ttu-id="20bc3-333">**Надстройка "собрание по сети" для Lync 2010**     Предоставляет планирование для собраний Lync и удаляет возможность планирования конференций Office Live Meeting.</span><span class="sxs-lookup"><span data-stu-id="20bc3-333">**Online Meeting Add-in for Lync 2010**   Provides scheduling for Lync meetings and removes the capability to schedule Office Live Meeting conferences.</span></span>

  - <span data-ttu-id="20bc3-334">**Надстройка Конференц-**     связи Office Communicator 2007 R2 Предоставляет планирование для конференций Office Live Meeting и конференций Office Communicator 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="20bc3-334">**Office Communicator 2007 R2 Conferencing Add-in**   Provides scheduling for both Office Live Meeting conferences and Office Communicator 2007 R2 conferences.</span></span> 

<div>


> [!NOTE]  
> <span data-ttu-id="20bc3-335">В Lync Server 2013 невозможно планировать конференции Live Meeting.</span><span class="sxs-lookup"><span data-stu-id="20bc3-335">Live Meeting conferences cannot be scheduled on Lync Server 2013.</span></span>



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
<th><span data-ttu-id="20bc3-336">Планирование клиента</span><span class="sxs-lookup"><span data-stu-id="20bc3-336">Scheduling Client</span></span></th>
<th><span data-ttu-id="20bc3-337">Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="20bc3-337">Lync Server 2013</span></span></th>
<th><span data-ttu-id="20bc3-338">Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="20bc3-338">Lync Server 2010</span></span></th>
<th><span data-ttu-id="20bc3-339">Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="20bc3-339">Office Communications Server 2007 R2</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="20bc3-340">Надстройка "собрание по сети" для Lync 2013 (может использоваться с Office 2013, Outlook 2010 и Outlook 2007)</span><span class="sxs-lookup"><span data-stu-id="20bc3-340">Online Meeting Add-in for Lync 2013 (can be used with Office 2013, Outlook 2010, and Outlook 2007)</span></span></p></td>
<td><p><span data-ttu-id="20bc3-341">Поддерживается</span><span class="sxs-lookup"><span data-stu-id="20bc3-341">Supported</span></span></p></td>
<td><p><span data-ttu-id="20bc3-342">Поддерживается (новые функции надстроек недоступны)</span><span class="sxs-lookup"><span data-stu-id="20bc3-342">Supported (new add-in features not available)</span></span></p></td>
<td><p><span data-ttu-id="20bc3-343">Не поддерживается</span><span class="sxs-lookup"><span data-stu-id="20bc3-343">Not Supported</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="20bc3-344">Веб-планировщик Lync 2013</span><span class="sxs-lookup"><span data-stu-id="20bc3-344">Lync 2013 Web Scheduler</span></span></p></td>
<td><p><span data-ttu-id="20bc3-345">Поддерживается</span><span class="sxs-lookup"><span data-stu-id="20bc3-345">Supported</span></span></p></td>
<td><p><span data-ttu-id="20bc3-346">Не поддерживается</span><span class="sxs-lookup"><span data-stu-id="20bc3-346">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="20bc3-347">Не поддерживается</span><span class="sxs-lookup"><span data-stu-id="20bc3-347">Not Supported</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="20bc3-348">Надстройка "собрание по сети" для Lync 2010</span><span class="sxs-lookup"><span data-stu-id="20bc3-348">Online Meeting Add-in for Lync 2010</span></span></p></td>
<td><p><span data-ttu-id="20bc3-349">Поддерживается</span><span class="sxs-lookup"><span data-stu-id="20bc3-349">Supported</span></span></p></td>
<td><p><span data-ttu-id="20bc3-350">Поддерживается</span><span class="sxs-lookup"><span data-stu-id="20bc3-350">Supported</span></span></p></td>
<td><p><span data-ttu-id="20bc3-351">Не поддерживается</span><span class="sxs-lookup"><span data-stu-id="20bc3-351">Not Supported</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="20bc3-352">Надстройка конференц-связи Office Communicator 2007 R2</span><span class="sxs-lookup"><span data-stu-id="20bc3-352">Office Communicator 2007 R2 Conferencing Add-in</span></span></p></td>
<td><p><span data-ttu-id="20bc3-353">Не поддерживается</span><span class="sxs-lookup"><span data-stu-id="20bc3-353">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="20bc3-354">Поддерживается</span><span class="sxs-lookup"><span data-stu-id="20bc3-354">Supported</span></span></p></td>
<td><p><span data-ttu-id="20bc3-355">Поддерживается</span><span class="sxs-lookup"><span data-stu-id="20bc3-355">Supported</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="support-for-joining-meetings"></a><span data-ttu-id="20bc3-356">Поддержка присоединения к собраниям</span><span class="sxs-lookup"><span data-stu-id="20bc3-356">Support for Joining Meetings</span></span>

<span data-ttu-id="20bc3-357">Все клиенты, поддерживаемые Lync Server 2013, могут присоединяться к собраниям Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="20bc3-357">All of the clients that Lync Server 2013 supports are allowed to join Lync 2013 meetings.</span></span> <span data-ttu-id="20bc3-358">Так как Lync Web App является веб-компонентом сервера, то в тех случаях, когда Lync Web App используется для присоединения к собранию Lync Server 2013, всегда используется более новая версия Lync Web App.</span><span class="sxs-lookup"><span data-stu-id="20bc3-358">Because Lync Web App is a web component of the server, in cases where Lync Web App is used to join a Lync Server 2013 meeting, the newer version of Lync Web App is always used.</span></span>

<span data-ttu-id="20bc3-359">Пользователи Lync 2013 могут присоединяться к собраниям, размещенным на Lync 2010 и Office Communications Server 2007 R2, с возможностью масштабирования.</span><span class="sxs-lookup"><span data-stu-id="20bc3-359">Lync 2013 clients can join meetings hosted on Lync 2010 and Office Communications Server 2007 R2 with scaled-down functionality.</span></span> <span data-ttu-id="20bc3-360">Функции для собраний ограничены версией сервера, на котором размещается собрание.</span><span class="sxs-lookup"><span data-stu-id="20bc3-360">In-meeting features are limited by the version of the server on which the meeting is hosted.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="20bc3-361">См. также</span><span class="sxs-lookup"><span data-stu-id="20bc3-361">See Also</span></span>


[<span data-ttu-id="20bc3-362">Требования к приложению для Магазина Windows Lync для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="20bc3-362">Lync Windows Store app requirements for Lync Server 2013</span></span>](lync-server-2013-lync-windows-store-app-requirements.md)  
[<span data-ttu-id="20bc3-363">Новые возможности конференц-связи в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="20bc3-363">New conferencing features in Lync Server 2013</span></span>](lync-server-2013-new-conferencing-features.md)  
[<span data-ttu-id="20bc3-364">Новые возможности для клиентов в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="20bc3-364">What's new for clients in Lync Server 2013</span></span>](lync-server-2013-what-s-new-for-clients.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

