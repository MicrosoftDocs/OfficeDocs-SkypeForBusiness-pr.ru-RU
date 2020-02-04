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
ms.openlocfilehash: b28d0de09a46a2be8b968e55c8f551e397da6ae8
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756763"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="client-interoperability-in-lync-2013"></a><span data-ttu-id="53436-102">Взаимодействие клиентов в Lync 2013</span><span class="sxs-lookup"><span data-stu-id="53436-102">Client interoperability in Lync 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="53436-103">_**Тема последнего изменения:** 2016-03-04_</span><span class="sxs-lookup"><span data-stu-id="53436-103">_**Topic Last Modified:** 2016-03-04_</span></span>

<span data-ttu-id="53436-104">В этой статье рассказывается о том, как использовать клиенты Microsoft Lync Server 2013 для совместной работы и взаимодействия с клиентами из более ранних версий Lync Server и Office Communications Server.</span><span class="sxs-lookup"><span data-stu-id="53436-104">This topic discusses the ability of Microsoft Lync Server 2013 clients to coexist and interact with clients from earlier versions of Lync Server and Office Communications Server.</span></span>

<div>

## <a name="server-and-client-compatibility"></a><span data-ttu-id="53436-105">Совместимость сервера и клиента</span><span class="sxs-lookup"><span data-stu-id="53436-105">Server and Client Compatibility</span></span>

<span data-ttu-id="53436-106">В следующей таблице показаны поддерживаемые комбинации версий клиентов и сервера.</span><span class="sxs-lookup"><span data-stu-id="53436-106">The following table shows the supported combinations of client versions and server versions.</span></span> <span data-ttu-id="53436-107">В этой таблице показано, поддерживается ли вход, когда клиент пытается подключиться к указанному серверу.</span><span class="sxs-lookup"><span data-stu-id="53436-107">This table indicates whether sign-in is supported when the client attempts to connect to the server indicated.</span></span> <span data-ttu-id="53436-108">Lync Server 2013 поддерживает предыдущую версию клиента.</span><span class="sxs-lookup"><span data-stu-id="53436-108">Lync Server 2013 supports the previous client version.</span></span> <span data-ttu-id="53436-109">Кроме того, в отличие от предыдущих выпусков, Lync Server 2010 поддерживает новые клиенты Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="53436-109">Also, unlike previous releases, Lync Server 2010 supports the new Lync 2013 clients.</span></span> <span data-ttu-id="53436-110">Это позволяет организациям, работающим с Lync Server 2010, развертывать новые клиенты независимо от того, как Lync Server выполняет обновление.</span><span class="sxs-lookup"><span data-stu-id="53436-110">This allows organizations who are upgrading from Lync Server 2010 to roll out new clients independent of Lync Server upgrades.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="53436-111">Клиент</span><span class="sxs-lookup"><span data-stu-id="53436-111">Client</span></span></th>
<th><span data-ttu-id="53436-112">Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="53436-112">Lync Server 2013</span></span></th>
<th><span data-ttu-id="53436-113">Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="53436-113">Lync Server 2010</span></span></th>
<th><span data-ttu-id="53436-114">Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="53436-114">Office Communications Server 2007 R2</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="53436-115">Lync 2013</span><span class="sxs-lookup"><span data-stu-id="53436-115">Lync 2013</span></span></p></td>
<td><p><span data-ttu-id="53436-116">Поддерживается</span><span class="sxs-lookup"><span data-stu-id="53436-116">Supported</span></span></p></td>
<td><p><span data-ttu-id="53436-117">Supported5</span><span class="sxs-lookup"><span data-stu-id="53436-117">Supported5</span></span></p></td>
<td><p><span data-ttu-id="53436-118">Не поддерживается</span><span class="sxs-lookup"><span data-stu-id="53436-118">Not Supported</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="53436-119">Lync 2013 Basic</span><span class="sxs-lookup"><span data-stu-id="53436-119">Lync 2013 Basic</span></span></p></td>
<td><p><span data-ttu-id="53436-120">Поддерживается</span><span class="sxs-lookup"><span data-stu-id="53436-120">Supported</span></span></p></td>
<td><p><span data-ttu-id="53436-121">Поддерживается</span><span class="sxs-lookup"><span data-stu-id="53436-121">Supported</span></span></p></td>
<td><p><span data-ttu-id="53436-122">Не поддерживается</span><span class="sxs-lookup"><span data-stu-id="53436-122">Not Supported</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="53436-123">Lync Web App 2013</span><span class="sxs-lookup"><span data-stu-id="53436-123">Lync Web App 2013</span></span></p></td>
<td><p><span data-ttu-id="53436-124">Поддерживается</span><span class="sxs-lookup"><span data-stu-id="53436-124">Supported</span></span></p></td>
<td><p><span data-ttu-id="53436-125">Не поддерживается</span><span class="sxs-lookup"><span data-stu-id="53436-125">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="53436-126">Не поддерживается</span><span class="sxs-lookup"><span data-stu-id="53436-126">Not Supported</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="53436-127">Lync 2010</span><span class="sxs-lookup"><span data-stu-id="53436-127">Lync 2010</span></span></p></td>
<td><p><span data-ttu-id="53436-128">Поддерживается</span><span class="sxs-lookup"><span data-stu-id="53436-128">Supported</span></span></p></td>
<td><p><span data-ttu-id="53436-129">Поддерживается</span><span class="sxs-lookup"><span data-stu-id="53436-129">Supported</span></span></p></td>
<td><p><span data-ttu-id="53436-130">Не поддерживается</span><span class="sxs-lookup"><span data-stu-id="53436-130">Not Supported</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="53436-131">Lync 2010 Attendant</span><span class="sxs-lookup"><span data-stu-id="53436-131">Lync 2010 Attendant</span></span></p></td>
<td><p><span data-ttu-id="53436-132">Поддерживается</span><span class="sxs-lookup"><span data-stu-id="53436-132">Supported</span></span></p></td>
<td><p><span data-ttu-id="53436-133">Поддерживается</span><span class="sxs-lookup"><span data-stu-id="53436-133">Supported</span></span></p></td>
<td><p><span data-ttu-id="53436-134">Не поддерживается</span><span class="sxs-lookup"><span data-stu-id="53436-134">Not Supported</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="53436-135">Lync 2010</span><span class="sxs-lookup"><span data-stu-id="53436-135">Lync 2010 Group Chat</span></span></p></td>
<td><p><span data-ttu-id="53436-136">Supported1</span><span class="sxs-lookup"><span data-stu-id="53436-136">Supported1</span></span></p></td>
<td><p><span data-ttu-id="53436-137">Supported2</span><span class="sxs-lookup"><span data-stu-id="53436-137">Supported2</span></span></p></td>
<td><p><span data-ttu-id="53436-138">Неприменимо</span><span class="sxs-lookup"><span data-stu-id="53436-138">Not Applicable</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="53436-139">Lync Web App 2010</span><span class="sxs-lookup"><span data-stu-id="53436-139">Lync Web App 2010</span></span></p></td>
<td><p><span data-ttu-id="53436-140">Не поддерживается</span><span class="sxs-lookup"><span data-stu-id="53436-140">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="53436-141">Поддерживается</span><span class="sxs-lookup"><span data-stu-id="53436-141">Supported</span></span></p></td>
<td><p><span data-ttu-id="53436-142">Не поддерживается</span><span class="sxs-lookup"><span data-stu-id="53436-142">Not Supported</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="53436-143">Участник Lync 2010</span><span class="sxs-lookup"><span data-stu-id="53436-143">Lync 2010 Attendee</span></span></p></td>
<td><p><span data-ttu-id="53436-144">Не Supported3</span><span class="sxs-lookup"><span data-stu-id="53436-144">Not Supported3</span></span></p></td>
<td><p><span data-ttu-id="53436-145">Поддерживается</span><span class="sxs-lookup"><span data-stu-id="53436-145">Supported</span></span></p></td>
<td><p><span data-ttu-id="53436-146">Не поддерживается</span><span class="sxs-lookup"><span data-stu-id="53436-146">Not Supported</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="53436-147">Office Communicator 2007 R2</span><span class="sxs-lookup"><span data-stu-id="53436-147">Office Communicator 2007 R2</span></span></p></td>
<td><p><span data-ttu-id="53436-148">Interoperable4</span><span class="sxs-lookup"><span data-stu-id="53436-148">Interoperable4</span></span></p></td>
<td><p><span data-ttu-id="53436-149">Поддерживается</span><span class="sxs-lookup"><span data-stu-id="53436-149">Supported</span></span></p></td>
<td><p><span data-ttu-id="53436-150">Поддерживается</span><span class="sxs-lookup"><span data-stu-id="53436-150">Supported</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="53436-151">Microsoft Office Communications Server 2007 R2 Attendant</span><span class="sxs-lookup"><span data-stu-id="53436-151">Microsoft Office Communications Server 2007 R2 Attendant</span></span></p></td>
<td><p><span data-ttu-id="53436-152">Не поддерживается</span><span class="sxs-lookup"><span data-stu-id="53436-152">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="53436-153">Поддерживается</span><span class="sxs-lookup"><span data-stu-id="53436-153">Supported</span></span></p></td>
<td><p><span data-ttu-id="53436-154">Поддерживается</span><span class="sxs-lookup"><span data-stu-id="53436-154">Supported</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="53436-155">Office Communicator 2007</span><span class="sxs-lookup"><span data-stu-id="53436-155">Office Communicator 2007</span></span></p></td>
<td><p><span data-ttu-id="53436-156">Не поддерживается</span><span class="sxs-lookup"><span data-stu-id="53436-156">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="53436-157">Поддерживается</span><span class="sxs-lookup"><span data-stu-id="53436-157">Supported</span></span></p></td>
<td><p><span data-ttu-id="53436-158">Поддерживается</span><span class="sxs-lookup"><span data-stu-id="53436-158">Supported</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="53436-159">Office Live Meeting 2007</span><span class="sxs-lookup"><span data-stu-id="53436-159">Office Live Meeting 2007</span></span></p></td>
<td><p><span data-ttu-id="53436-160">Не поддерживается</span><span class="sxs-lookup"><span data-stu-id="53436-160">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="53436-161">Поддерживается</span><span class="sxs-lookup"><span data-stu-id="53436-161">Supported</span></span></p></td>
<td><p><span data-ttu-id="53436-162">Поддерживается</span><span class="sxs-lookup"><span data-stu-id="53436-162">Supported</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="53436-163">Приложение Lync из Магазина Windows</span><span class="sxs-lookup"><span data-stu-id="53436-163">Lync Windows Store app</span></span></p></td>
<td><p><span data-ttu-id="53436-164">Поддерживается</span><span class="sxs-lookup"><span data-stu-id="53436-164">Supported</span></span></p></td>
<td><p><span data-ttu-id="53436-165">Поддерживается</span><span class="sxs-lookup"><span data-stu-id="53436-165">Supported</span></span></p></td>
<td><p><span data-ttu-id="53436-166">Не поддерживается</span><span class="sxs-lookup"><span data-stu-id="53436-166">Not Supported</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="53436-167">1For подробные сведения можно найти в разделе [Миграция с Lync server 2010, группового чата или Office Communications Server 2007 R2 Group Chat на Lync server 2013 и на сервер сохраняемого чата](migration-from-lync-server-2010-group-chat-or-office-communications-server-2007-r2-group-chat-to-lync-server-2013-persistent-chat-server.md).</span><span class="sxs-lookup"><span data-stu-id="53436-167">1For details, see [Migration from Lync Server 2010, Group Chat or Office Communications Server 2007 R2 Group Chat to Lync Server 2013, Persistent Chat Server](migration-from-lync-server-2010-group-chat-or-office-communications-server-2007-r2-group-chat-to-lync-server-2013-persistent-chat-server.md).</span></span>

<span data-ttu-id="53436-168">2In Microsoft Lync Server 2010 вы можете воспользоваться функцией группового чата с помощью сервера группового чата, стороннего надежного приложения для Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="53436-168">2In Microsoft Lync Server 2010, group chat functionality was available with Group Chat Server, a third-party trusted application for Lync Server 2010.</span></span> <span data-ttu-id="53436-169">Клиенты Lync 2013 несовместимы с Lync Server 2010, групповой чат.</span><span class="sxs-lookup"><span data-stu-id="53436-169">Lync 2013 clients are not compatible with Lync Server 2010, Group Chat.</span></span>

<span data-ttu-id="53436-170">3Lync веб-приложение 2013 теперь обеспечивает полное участие в собрании, в том числе звуковое сопровождение и видео компьютера, и считается заменой для участника Lync 2010.</span><span class="sxs-lookup"><span data-stu-id="53436-170">3Lync Web App 2013 now provides a full in-meeting experience, including computer audio and video, and is considered the replacement for Lync 2010 Attendee.</span></span> <span data-ttu-id="53436-171">Участники Lync 2010 будут подключаться к Lync Server 2013 только в том случае, если вы используете неподдерживаемый браузер (Internet Explorer 6 или Internet Explorer 7) и Windows XP.</span><span class="sxs-lookup"><span data-stu-id="53436-171">Lync 2010 Attendee will connect to Lync Server 2013 only when you are using an unsupported browser (Internet Explorer 6 or Internet Explorer 7) and Windows XP.</span></span>

<span data-ttu-id="53436-172">4The функции присутствия и обмена мгновенными сообщениями в Office Communicator 2007 R2 совместимы с Lync Server 2013, но возможности конференции не поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="53436-172">4The presence and IM features in Office Communicator 2007 R2 are compatible with Lync Server 2013, but conferencing features are not.</span></span> <span data-ttu-id="53436-173">При переходе с Office Communications Server 2007 R2 подходящими для обеспечения взаимодействия и обмена мгновенными сообщениями является Office Communicator 2007 R2, но пользователи должны использовать Lync Web App 2013, чтобы присоединиться к собраниям Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="53436-173">During migration from Office Communications Server 2007 R2, Office Communicator 2007 R2 is suitable for presence and IM interoperability, but users should use Lync Web App 2013 to join Lync Server 2013 meetings.</span></span>

<span data-ttu-id="53436-174">5 об ограничениях читайте в статье поддержка функции Конференции для клиентов Lync 2013 в Lync Server 2010 для собраний ниже.</span><span class="sxs-lookup"><span data-stu-id="53436-174">5 For limitations, see "Conferencing Feature Support for Lync 2013 Clients in Lync Server 2010 Meetings" later in this topic.</span></span>

</div>

<div>

## <a name="interoperability-among-clients"></a><span data-ttu-id="53436-175">Взаимодействие между клиентами</span><span class="sxs-lookup"><span data-stu-id="53436-175">Interoperability among Clients</span></span>

<span data-ttu-id="53436-176">Благодаря выпуску Lync Server 2013 различные клиентские версии могут беспрепятственно взаимодействовать в одноранговых сценариях и конференц-связи.</span><span class="sxs-lookup"><span data-stu-id="53436-176">With the Lync Server 2013 release, various client versions can interact seamlessly in both peer-to-peer and conferencing scenarios.</span></span> <span data-ttu-id="53436-177">Этот раздел содержит сведения о доступности функций при взаимодействии пользователей с другими пользователями, использующими разные версии клиентов и серверов.</span><span class="sxs-lookup"><span data-stu-id="53436-177">This section discusses feature availability when users interact with other users who are using different versions of clients and servers.</span></span>

<div>

## <a name="peer-to-peer-feature-support"></a><span data-ttu-id="53436-178">Поддержка одноранговых функций</span><span class="sxs-lookup"><span data-stu-id="53436-178">Peer-to-Peer Feature Support</span></span>

<span data-ttu-id="53436-179">Одноранговые функции поддерживаются для пользователей, которые находятся в разных версиях сервера и используют разные клиентские версии.</span><span class="sxs-lookup"><span data-stu-id="53436-179">Peer-to-peer features are supported for users who are homed on different versions of the server and who are using different client versions.</span></span> <span data-ttu-id="53436-180">Взаимодействие с конечным пользователем и доступные возможности соответствуют возможностям клиента пользователя и версии сервера, на котором пользователь вошел в систему.</span><span class="sxs-lookup"><span data-stu-id="53436-180">The end-user experience and available features are consistent with the capabilities of the user’s client and the version of the server the user is signed in to.</span></span> <span data-ttu-id="53436-181">Другими словами:</span><span class="sxs-lookup"><span data-stu-id="53436-181">In other words:</span></span>

  - <span data-ttu-id="53436-182">Если пользователь вошел в Lync Server 2013 с более ранней версией клиента, он будет использовать тот же интерфейс, что и для этого пользователя.</span><span class="sxs-lookup"><span data-stu-id="53436-182">If a user is signed in to Lync Server 2013 with an older client, the user will have the same experience he or she is used to.</span></span> <span data-ttu-id="53436-183">Новые функции, представленные в Lync Server 2013, будут недоступны до тех пор, пока клиент пользователя не будет обновлен.</span><span class="sxs-lookup"><span data-stu-id="53436-183">None of the new features introduced in Lync Server 2013 will be available until the user’s client is upgraded.</span></span> <span data-ttu-id="53436-184">Примеры: Просмотр коллекции видео, видео в формате HD, обновленный общий доступ к PowerPoint, а также возможность отключения звука и видео всех участников во время ввода собрания.</span><span class="sxs-lookup"><span data-stu-id="53436-184">Examples include video gallery view, HD video, updated PowerPoint sharing, and the option to mute all attendee audio and video upon meeting entry.</span></span> <span data-ttu-id="53436-185">Новые функции, описанные в разделе [новые возможности конференции в Lync server 2013](lync-server-2013-new-conferencing-features.md) , и [новые возможности для клиентов в Lync Server 2013](lync-server-2013-what-s-new-for-clients.md).</span><span class="sxs-lookup"><span data-stu-id="53436-185">The new features are outlined in [New conferencing features in Lync Server 2013](lync-server-2013-new-conferencing-features.md) and [What's new for clients in Lync Server 2013](lync-server-2013-what-s-new-for-clients.md).</span></span>

  - <span data-ttu-id="53436-186">Если пользователь вошел в Lync Server 2010 с помощью клиента Lync 2013, все новые возможности, не поддерживаемые Lync Server 2010, будут недоступны до тех пор, пока пользователь не будет перенесен на Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="53436-186">If a user is signed in to Lync Server 2010 with a Lync 2013 client, any new features not supported by Lync Server 2010 will be unavailable until the user is moved to Lync Server 2013.</span></span>

<span data-ttu-id="53436-187">В следующей таблице сравниваются возможности, доступные в одноранговых сеансах, в которых клиент вошел на сервер Lync Server 2013 или Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="53436-187">The following table compares feature availability in peer-to-peer sessions where the client is signed in to either Lync Server 2013 or Lync Server 2010.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="53436-188">Участники Lync Web App и Lync 2010 относятся к клиентам только для собраний и не включены в эту таблицу.</span><span class="sxs-lookup"><span data-stu-id="53436-188">Lync Web App and Lync 2010 Attendee are meeting-only clients and aren’t included in this table.</span></span>



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
<th><span data-ttu-id="53436-189">Клиент</span><span class="sxs-lookup"><span data-stu-id="53436-189">Client</span></span></th>
<th><span data-ttu-id="53436-190">Обмен мгновенными сообщениями</span><span class="sxs-lookup"><span data-stu-id="53436-190">Instant Messaging</span></span></th>
<th><span data-ttu-id="53436-191">Присутствие</span><span class="sxs-lookup"><span data-stu-id="53436-191">Presence</span></span></th>
<th><span data-ttu-id="53436-192">Голосовая связь</span><span class="sxs-lookup"><span data-stu-id="53436-192">Voice</span></span></th>
<th><span data-ttu-id="53436-193">Видеосвязь</span><span class="sxs-lookup"><span data-stu-id="53436-193">Video</span></span></th>
<th><span data-ttu-id="53436-194">Общий доступ к приложениям</span><span class="sxs-lookup"><span data-stu-id="53436-194">Application Sharing</span></span></th>
<th><span data-ttu-id="53436-195">Передача файлов</span><span class="sxs-lookup"><span data-stu-id="53436-195">File Transfer</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="53436-196">Lync 2013</span><span class="sxs-lookup"><span data-stu-id="53436-196">Lync 2013</span></span></p></td>
<td><p><span data-ttu-id="53436-197">Да</span><span class="sxs-lookup"><span data-stu-id="53436-197">Yes</span></span></p></td>
<td><p><span data-ttu-id="53436-198">Да</span><span class="sxs-lookup"><span data-stu-id="53436-198">Yes</span></span></p></td>
<td><p><span data-ttu-id="53436-199">Да</span><span class="sxs-lookup"><span data-stu-id="53436-199">Yes</span></span></p></td>
<td><p><span data-ttu-id="53436-200">Да</span><span class="sxs-lookup"><span data-stu-id="53436-200">Yes</span></span></p></td>
<td><p><span data-ttu-id="53436-201">Да </span><span class="sxs-lookup"><span data-stu-id="53436-201">Yes</span></span></p></td>
<td><p><span data-ttu-id="53436-202">Да</span><span class="sxs-lookup"><span data-stu-id="53436-202">Yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="53436-203">Lync 2013 Basic</span><span class="sxs-lookup"><span data-stu-id="53436-203">Lync 2013 Basic</span></span></p></td>
<td><p><span data-ttu-id="53436-204">Да </span><span class="sxs-lookup"><span data-stu-id="53436-204">Yes</span></span></p></td>
<td><p><span data-ttu-id="53436-205">Да </span><span class="sxs-lookup"><span data-stu-id="53436-205">Yes</span></span></p></td>
<td><p><span data-ttu-id="53436-206">Да </span><span class="sxs-lookup"><span data-stu-id="53436-206">Yes</span></span></p></td>
<td><p><span data-ttu-id="53436-207">Да </span><span class="sxs-lookup"><span data-stu-id="53436-207">Yes</span></span></p></td>
<td><p><span data-ttu-id="53436-208">Да </span><span class="sxs-lookup"><span data-stu-id="53436-208">Yes</span></span></p></td>
<td><p><span data-ttu-id="53436-209">Да</span><span class="sxs-lookup"><span data-stu-id="53436-209">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="53436-210">Lync 2010</span><span class="sxs-lookup"><span data-stu-id="53436-210">Lync 2010</span></span></p></td>
<td><p><span data-ttu-id="53436-211">Да </span><span class="sxs-lookup"><span data-stu-id="53436-211">Yes</span></span></p></td>
<td><p><span data-ttu-id="53436-212">Да </span><span class="sxs-lookup"><span data-stu-id="53436-212">Yes</span></span></p></td>
<td><p><span data-ttu-id="53436-213">Да </span><span class="sxs-lookup"><span data-stu-id="53436-213">Yes</span></span></p></td>
<td><p><span data-ttu-id="53436-214">Да </span><span class="sxs-lookup"><span data-stu-id="53436-214">Yes</span></span></p></td>
<td><p><span data-ttu-id="53436-215">Да </span><span class="sxs-lookup"><span data-stu-id="53436-215">Yes</span></span></p></td>
<td><p><span data-ttu-id="53436-216">Да</span><span class="sxs-lookup"><span data-stu-id="53436-216">Yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="53436-217">Lync 2010 Attendant</span><span class="sxs-lookup"><span data-stu-id="53436-217">Lync 2010 Attendant</span></span></p></td>
<td><p><span data-ttu-id="53436-218">Да </span><span class="sxs-lookup"><span data-stu-id="53436-218">Yes</span></span></p></td>
<td><p><span data-ttu-id="53436-219">Да </span><span class="sxs-lookup"><span data-stu-id="53436-219">Yes</span></span></p></td>
<td><p><span data-ttu-id="53436-220">Да</span><span class="sxs-lookup"><span data-stu-id="53436-220">Yes</span></span></p></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="53436-221">Lync 2010 Mobile</span><span class="sxs-lookup"><span data-stu-id="53436-221">Lync 2010 Mobile</span></span></p></td>
<td><p><span data-ttu-id="53436-222">Да </span><span class="sxs-lookup"><span data-stu-id="53436-222">Yes</span></span></p></td>
<td><p><span data-ttu-id="53436-223">Да</span><span class="sxs-lookup"><span data-stu-id="53436-223">Yes</span></span></p></td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="53436-224">Lync Phone Edition</span><span class="sxs-lookup"><span data-stu-id="53436-224">Lync Phone Edition</span></span></p></td>
<td><p><span data-ttu-id="53436-225">Да </span><span class="sxs-lookup"><span data-stu-id="53436-225">Yes</span></span></p></td>
<td><p><span data-ttu-id="53436-226">Да </span><span class="sxs-lookup"><span data-stu-id="53436-226">Yes</span></span></p></td>
<td><p><span data-ttu-id="53436-227">Да</span><span class="sxs-lookup"><span data-stu-id="53436-227">Yes</span></span></p></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="53436-228">Office Communicator 2007 R2</span><span class="sxs-lookup"><span data-stu-id="53436-228">Office Communicator 2007 R2</span></span></p></td>
<td><p><span data-ttu-id="53436-229">Да </span><span class="sxs-lookup"><span data-stu-id="53436-229">Yes</span></span></p></td>
<td><p><span data-ttu-id="53436-230">Да </span><span class="sxs-lookup"><span data-stu-id="53436-230">Yes</span></span></p></td>
<td><p><span data-ttu-id="53436-231">Да </span><span class="sxs-lookup"><span data-stu-id="53436-231">Yes</span></span></p></td>
<td><p><span data-ttu-id="53436-232">Да</span><span class="sxs-lookup"><span data-stu-id="53436-232">Yes</span></span></p></td>
<td><p><span data-ttu-id="53436-233">Да1</span><span class="sxs-lookup"><span data-stu-id="53436-233">Yes1</span></span></p></td>
<td><p><span data-ttu-id="53436-234">Да</span><span class="sxs-lookup"><span data-stu-id="53436-234">Yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="53436-235">Общедоступная служба обмена мгновенными сообщениями (AOL, Yahoo!)</span><span class="sxs-lookup"><span data-stu-id="53436-235">Public IM (AOL, Yahoo!)</span></span></p></td>
<td><p><span data-ttu-id="53436-236">Да </span><span class="sxs-lookup"><span data-stu-id="53436-236">Yes</span></span></p></td>
<td><p><span data-ttu-id="53436-237">Да</span><span class="sxs-lookup"><span data-stu-id="53436-237">Yes</span></span></p></td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="53436-238">Общедоступная служба обмена мгновенными сообщениями (MSN, Windows Live Messenger)</span><span class="sxs-lookup"><span data-stu-id="53436-238">Public IM (MSN, Windows Live Messenger)</span></span></p></td>
<td><p><span data-ttu-id="53436-239">Да </span><span class="sxs-lookup"><span data-stu-id="53436-239">Yes</span></span></p></td>
<td><p><span data-ttu-id="53436-240">Да </span><span class="sxs-lookup"><span data-stu-id="53436-240">Yes</span></span></p></td>
<td><p><span data-ttu-id="53436-241">Да </span><span class="sxs-lookup"><span data-stu-id="53436-241">Yes</span></span></p></td>
<td><p><span data-ttu-id="53436-242">Да</span><span class="sxs-lookup"><span data-stu-id="53436-242">Yes</span></span></p></td>
<td></td>
<td></td>
</tr>
</tbody>
</table>


<div>


> [!IMPORTANT]  
> <UL>
> <LI>
> <P><span data-ttu-id="53436-243">За Сентябрь 1 сентября 2012 г. Лицензия на подписку на общедоступные пользователи Microsoft Lync (PIC усл) больше не доступна для приобретения новых или обновленных договоров.</span><span class="sxs-lookup"><span data-stu-id="53436-243">As of September 1st, 2012, the Microsoft Lync Public IM Connectivity User Subscription License (PIC USL) is no longer available for the purchase for new or renewing agreements.</span></span> <span data-ttu-id="53436-244">Пользователи с активными лицензиями смогут продолжать использовать федерацию с помощью Yahoo!</span><span class="sxs-lookup"><span data-stu-id="53436-244">Customers with active licenses will be able to continue to federate with Yahoo!</span></span> <span data-ttu-id="53436-245">Messenger, пока не зайдет Дата завершения обслуживания.</span><span class="sxs-lookup"><span data-stu-id="53436-245">Messenger until the service shutdown date.</span></span> <span data-ttu-id="53436-246">Дата окончания жизненного цикла 2014 для AOL и Yahoo! в течение июня.</span><span class="sxs-lookup"><span data-stu-id="53436-246">An end of life date of June 2014 for AOL and Yahoo!</span></span> <span data-ttu-id="53436-247">было объявлено.</span><span class="sxs-lookup"><span data-stu-id="53436-247">has been announced.</span></span> <span data-ttu-id="53436-248">Подробности можно найти <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">в разделе Поддержка общедоступной службы обмена мгновенными сообщениями в Lync Server 2013</A>..</span><span class="sxs-lookup"><span data-stu-id="53436-248">For details, see <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Support for public instant messenger connectivity in Lync Server 2013</A>..</span></span></P>
> <LI>
> <P><span data-ttu-id="53436-249">УСЛ PIC является лицензией на подписку "на пользователя", которая требуется для использования Lync Server или Office Communications Server для Федерации с помощью Yahoo!</span><span class="sxs-lookup"><span data-stu-id="53436-249">The PIC USL is a per-user, per-month subscription license that is required for Lync Server or Office Communications Server to federate with Yahoo!</span></span> <span data-ttu-id="53436-250">Messenger.</span><span class="sxs-lookup"><span data-stu-id="53436-250">Messenger.</span></span> <span data-ttu-id="53436-251">Возможность предоставления этой услуги корпорацией Майкрософт зависит от поддержки компании Yahoo!, основного соглашения, для которого она не будет продлена.</span><span class="sxs-lookup"><span data-stu-id="53436-251">Microsoft’s ability to provide this service has been contingent upon support from Yahoo!, the underlying agreement for which will not be renewed.</span></span></P>
> <LI>
> <P><span data-ttu-id="53436-252">В некоторых случаях Lync — это мощный инструмент для связи между организациями и людьми по всему миру.</span><span class="sxs-lookup"><span data-stu-id="53436-252">More than ever, Lync is a powerful tool for connecting across organizations and with individuals around the world.</span></span> <span data-ttu-id="53436-253">Для интеграции с Windows Live Messenger не требуется дополнительных лицензий на пользователей и устройств за пределами стандартной клиентской лицензии Lync.</span><span class="sxs-lookup"><span data-stu-id="53436-253">Federation with Windows Live Messenger requires no additional user/device licenses beyond the Lync Standard CAL.</span></span> <span data-ttu-id="53436-254">В этот список будет добавлена Федерация Skype, благодаря чему пользователи Lync смогут получать сотни миллионов людей с помощью голосовой почты и голосовых сообщений.</span><span class="sxs-lookup"><span data-stu-id="53436-254">Skype federation will be added to this list, enabling Lync users to reach hundreds of millions of people through IM and voice.</span></span></P></LI></UL>



</div>

<span data-ttu-id="53436-255">1 в Office Communicator 2007 R2 доступен только общий доступ к рабочему столу (и не общий доступ к программам).</span><span class="sxs-lookup"><span data-stu-id="53436-255">1 In Office Communicator 2007 R2, only desktop sharing (and not program sharing) is available.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="53436-256">Общий доступ к рабочему столу между Office Communicator 2007 R2 и Skype для бизнеса 2015 нельзя инициировать из нового клиента, если пользовательским интерфейсом клиента Skype для бизнеса 2015 является принудительно.</span><span class="sxs-lookup"><span data-stu-id="53436-256">Desktop sharing between Office Communicator 2007 R2 and Skype for Business 2015 cannot be initiated from the newer client when the Skype for Business 2015 client user interface is enforced.</span></span>



</div>

</div>

<div>

## <a name="conferencing-feature-support-for-lync-2013-clients-in-lync-server-2010-meetings"></a><span data-ttu-id="53436-257">Поддержка функций конференций для клиентов Lync 2013 в Lync Server 2010 для собраний</span><span class="sxs-lookup"><span data-stu-id="53436-257">Conferencing Feature Support for Lync 2013 Clients in Lync Server 2010 Meetings</span></span>

<span data-ttu-id="53436-258">Когда пользователь присоединяется к собранию Lync Server 2010 с помощью клиента Lync 2013, у него есть доступ к функциям клиента Lync 2013 со следующими исключениями:</span><span class="sxs-lookup"><span data-stu-id="53436-258">When users join Lync Server 2010 meetings with a Lync 2013 client, they have access to Lync 2013 client features with the following exceptions:</span></span>

  - <span data-ttu-id="53436-259">В параметрах управления **участниками** , доступ к которым осуществляется с помощью значка "люди" в окне собрания, не будет работать параметр " **мгновенное сообщение о собрании** ".</span><span class="sxs-lookup"><span data-stu-id="53436-259">In the **Participants** management options, which are accessible by pointing to the people icon in the meeting window, the **No Meeting IM** option does not function.</span></span>

  - <span data-ttu-id="53436-260">Представление коллекции не может работать в видеоконференциях.</span><span class="sxs-lookup"><span data-stu-id="53436-260">Gallery View does not function in video conferences.</span></span> <span data-ttu-id="53436-261">Пользователь видит только активный динамик, а не все динамики.</span><span class="sxs-lookup"><span data-stu-id="53436-261">The user sees only the active speaker instead of all speakers.</span></span> <span data-ttu-id="53436-262">В списке выбора параметров **разметки** недоступен **режим коллекции**</span><span class="sxs-lookup"><span data-stu-id="53436-262">In the list of **Pick a Layout** options, **Gallery View** is unavailable</span></span>

  - <span data-ttu-id="53436-263">Список участников по умолчанию отображается в видеоконференциях.</span><span class="sxs-lookup"><span data-stu-id="53436-263">The participant list displays by default in video conferences.</span></span>

  - <span data-ttu-id="53436-264">Если щелкнуть пользователя правой кнопкой мыши в списке участников, вы не **сможете получить** **доступ к** параметрам управления участниками коллекции.</span><span class="sxs-lookup"><span data-stu-id="53436-264">When right-clicking a user in the participants list, the **Lock the Video Spotlight** and **Pin to Gallery** participant management options are unavailable.</span></span>

</div>

<div>

## <a name="conferencing-feature-support-in-lync-server-2013-meetings"></a><span data-ttu-id="53436-265">Поддержка функций конференций в Lync Server 2013 для собраний</span><span class="sxs-lookup"><span data-stu-id="53436-265">Conferencing Feature Support in Lync Server 2013 Meetings</span></span>

<span data-ttu-id="53436-266">Lync Server 2013 предлагает новые функции для конференций, которые становятся доступны пользователям после перемещения учетных записей на Lync Server 2013 и входа в систему с помощью клиента Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="53436-266">Lync Server 2013 provides new conferencing features that become available to users after their accounts are moved to Lync Server 2013 and they sign in with the Lync 2013 client.</span></span> <span data-ttu-id="53436-267">В качестве примеров можно привести представление коллекции видео, видео в формате HD, общий доступ к PowerPoint, а также возможность отключить звук и видео всех участников во время ввода собрания.</span><span class="sxs-lookup"><span data-stu-id="53436-267">Examples include video gallery view, HD video, PowerPoint sharing, and the option to mute all attendee audio and video upon meeting entry.</span></span> <span data-ttu-id="53436-268">Новые функции, описанные в разделе [новые возможности конференции в Lync server 2013](lync-server-2013-new-conferencing-features.md) , и [новые возможности для клиентов в Lync Server 2013](lync-server-2013-what-s-new-for-clients.md).</span><span class="sxs-lookup"><span data-stu-id="53436-268">The new features are outlined in [New conferencing features in Lync Server 2013](lync-server-2013-new-conferencing-features.md) and [What's new for clients in Lync Server 2013](lync-server-2013-what-s-new-for-clients.md).</span></span>

<span data-ttu-id="53436-269">В Lync Server 2013 для собраний некоторые возможности конференции поддерживаются для пользователей, использующих разные версии сервера, и которые используют разные клиенты и клиентские версии.</span><span class="sxs-lookup"><span data-stu-id="53436-269">In Lync Server 2013 meetings, certain conferencing features are supported for users who are homed on different versions of the server and who are using different clients and client versions.</span></span> <span data-ttu-id="53436-270">Когда клиенты присоединяются к собранию Lync Server 2013, пользователи имеют доступ к функциям и возможностям, представленным в этой таблице.</span><span class="sxs-lookup"><span data-stu-id="53436-270">When clients join a Lync Server 2013 meeting, users have access to the features and capabilities shown in this table.</span></span>


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
<th><span data-ttu-id="53436-271">Клиент</span><span class="sxs-lookup"><span data-stu-id="53436-271">Client</span></span></th>
<th><span data-ttu-id="53436-272">Обмен мгновенными сообщениями в одноранговой сети</span><span class="sxs-lookup"><span data-stu-id="53436-272">Peer-to-peer IM</span></span></th>
<th><span data-ttu-id="53436-273">Голосовая связь</span><span class="sxs-lookup"><span data-stu-id="53436-273">Voice</span></span></th>
<th><span data-ttu-id="53436-274">Видеосвязь</span><span class="sxs-lookup"><span data-stu-id="53436-274">Video</span></span></th>
<th><span data-ttu-id="53436-275">Общий доступ к приложениям</span><span class="sxs-lookup"><span data-stu-id="53436-275">Application Sharing</span></span></th>
<th><span data-ttu-id="53436-276">PowerPoint</span><span class="sxs-lookup"><span data-stu-id="53436-276">PowerPoint</span></span></th>
<th><span data-ttu-id="53436-277">Передача файлов</span><span class="sxs-lookup"><span data-stu-id="53436-277">File Transfer</span></span></th>
<th><span data-ttu-id="53436-278">Доска</span><span class="sxs-lookup"><span data-stu-id="53436-278">Whiteboard</span></span></th>
<th><span data-ttu-id="53436-279">Опрос</span><span class="sxs-lookup"><span data-stu-id="53436-279">Polling</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="53436-280">Lync 2013</span><span class="sxs-lookup"><span data-stu-id="53436-280">Lync 2013</span></span></p></td>
<td><p><span data-ttu-id="53436-281">Да </span><span class="sxs-lookup"><span data-stu-id="53436-281">Yes</span></span></p></td>
<td><p><span data-ttu-id="53436-282">Да </span><span class="sxs-lookup"><span data-stu-id="53436-282">Yes</span></span></p></td>
<td><p><span data-ttu-id="53436-283">Да </span><span class="sxs-lookup"><span data-stu-id="53436-283">Yes</span></span></p></td>
<td><p><span data-ttu-id="53436-284">Да </span><span class="sxs-lookup"><span data-stu-id="53436-284">Yes</span></span></p></td>
<td><p><span data-ttu-id="53436-285">Да </span><span class="sxs-lookup"><span data-stu-id="53436-285">Yes</span></span></p></td>
<td><p><span data-ttu-id="53436-286">Да </span><span class="sxs-lookup"><span data-stu-id="53436-286">Yes</span></span></p></td>
<td><p><span data-ttu-id="53436-287">Да </span><span class="sxs-lookup"><span data-stu-id="53436-287">Yes</span></span></p></td>
<td><p><span data-ttu-id="53436-288">Да</span><span class="sxs-lookup"><span data-stu-id="53436-288">Yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="53436-289">Lync 2013 Basic</span><span class="sxs-lookup"><span data-stu-id="53436-289">Lync 2013 Basic</span></span></p></td>
<td><p><span data-ttu-id="53436-290">Да </span><span class="sxs-lookup"><span data-stu-id="53436-290">Yes</span></span></p></td>
<td><p><span data-ttu-id="53436-291">Да </span><span class="sxs-lookup"><span data-stu-id="53436-291">Yes</span></span></p></td>
<td><p><span data-ttu-id="53436-292">Да </span><span class="sxs-lookup"><span data-stu-id="53436-292">Yes</span></span></p></td>
<td><p><span data-ttu-id="53436-293">Да </span><span class="sxs-lookup"><span data-stu-id="53436-293">Yes</span></span></p></td>
<td><p><span data-ttu-id="53436-294">Да </span><span class="sxs-lookup"><span data-stu-id="53436-294">Yes</span></span></p></td>
<td><p><span data-ttu-id="53436-295">Да </span><span class="sxs-lookup"><span data-stu-id="53436-295">Yes</span></span></p></td>
<td><p><span data-ttu-id="53436-296">Да </span><span class="sxs-lookup"><span data-stu-id="53436-296">Yes</span></span></p></td>
<td><p><span data-ttu-id="53436-297">Да</span><span class="sxs-lookup"><span data-stu-id="53436-297">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="53436-298">Lync Web App</span><span class="sxs-lookup"><span data-stu-id="53436-298">Lync Web App</span></span></p></td>
<td><p><span data-ttu-id="53436-299">Да </span><span class="sxs-lookup"><span data-stu-id="53436-299">Yes</span></span></p></td>
<td><p><span data-ttu-id="53436-300">Да </span><span class="sxs-lookup"><span data-stu-id="53436-300">Yes</span></span></p></td>
<td><p><span data-ttu-id="53436-301">Да</span><span class="sxs-lookup"><span data-stu-id="53436-301">Yes</span></span></p></td>
<td><p><span data-ttu-id="53436-302">Да</span><span class="sxs-lookup"><span data-stu-id="53436-302">Yes</span></span></p></td>
<td><p><span data-ttu-id="53436-303">Да2</span><span class="sxs-lookup"><span data-stu-id="53436-303">Yes2</span></span></p></td>
<td><p><span data-ttu-id="53436-304">Да</span><span class="sxs-lookup"><span data-stu-id="53436-304">Yes</span></span></p></td>
<td><p><span data-ttu-id="53436-305">Да</span><span class="sxs-lookup"><span data-stu-id="53436-305">Yes</span></span></p></td>
<td><p><span data-ttu-id="53436-306">Да</span><span class="sxs-lookup"><span data-stu-id="53436-306">Yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="53436-307">Lync 2010</span><span class="sxs-lookup"><span data-stu-id="53436-307">Lync 2010</span></span></p></td>
<td><p><span data-ttu-id="53436-308">Да</span><span class="sxs-lookup"><span data-stu-id="53436-308">Yes</span></span></p></td>
<td><p><span data-ttu-id="53436-309">Да</span><span class="sxs-lookup"><span data-stu-id="53436-309">Yes</span></span></p></td>
<td><p><span data-ttu-id="53436-310">Да</span><span class="sxs-lookup"><span data-stu-id="53436-310">Yes</span></span></p></td>
<td><p><span data-ttu-id="53436-311">Да</span><span class="sxs-lookup"><span data-stu-id="53436-311">Yes</span></span></p></td>
<td><p><span data-ttu-id="53436-312">Yes3</span><span class="sxs-lookup"><span data-stu-id="53436-312">Yes3</span></span></p></td>
<td><p><span data-ttu-id="53436-313">Да</span><span class="sxs-lookup"><span data-stu-id="53436-313">Yes</span></span></p></td>
<td><p><span data-ttu-id="53436-314">Да</span><span class="sxs-lookup"><span data-stu-id="53436-314">Yes</span></span></p></td>
<td><p><span data-ttu-id="53436-315">Да</span><span class="sxs-lookup"><span data-stu-id="53436-315">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="53436-316">Office Communicator 2007 R2 4</span><span class="sxs-lookup"><span data-stu-id="53436-316">Office Communicator 2007 R2 4</span></span></p></td>
<td><p><span data-ttu-id="53436-317">Да</span><span class="sxs-lookup"><span data-stu-id="53436-317">Yes</span></span></p></td>
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


<span data-ttu-id="53436-318">1 в Office Communicator 2007 R2 доступен только общий доступ к рабочему столу (и не общий доступ к программам).</span><span class="sxs-lookup"><span data-stu-id="53436-318">1 In Office Communicator 2007 R2, only desktop sharing (and not program sharing) is available.</span></span>

<span data-ttu-id="53436-319">2 Lync Server 2013 использует обновленный механизм для отправки файлов PowerPoint.</span><span class="sxs-lookup"><span data-stu-id="53436-319">2 Lync Server 2013 uses an updated mechanism for uploading PowerPoint files.</span></span> <span data-ttu-id="53436-320">Пользователи Lync Web App, присоединяющиеся к собранию, изначально запланированному на Lync Server 2010, могут просматривать презентации PowerPoint и перемещаться по ним, но не могут загружать файлы PowerPoint.</span><span class="sxs-lookup"><span data-stu-id="53436-320">Lync Web App users who join a meeting that was originally scheduled on Lync Server 2010 can view and navigate PowerPoint presentations, but cannot upload PowerPoint files.</span></span>

<span data-ttu-id="53436-321">3. Если собрание запланировано на Lync Server 2013, а слайды PowerPoint были отправлены клиентом Lync 2013, пользователи Lync 2010 смогут получить доступ к слайдам только для просмотра.</span><span class="sxs-lookup"><span data-stu-id="53436-321">3 If the meeting was scheduled on Lync Server 2013 and PowerPoint slides were uploaded by a Lync 2013 client, Lync 2010 users have view-only access to the slides.</span></span> <span data-ttu-id="53436-322">И наоборот, если слайды PowerPoint были отправлены пользователем Lync 2010, пользователи Lync Server 2013 смогут просматривать и делать слайды и, если настроены сервер Office Web Apps, получать доступ к новым возможностям, таким как отображение более высоком разрешающей способности, анимацию, переходы слайдов и Внедренное видео.</span><span class="sxs-lookup"><span data-stu-id="53436-322">Conversely, if the PowerPoint slides were uploaded by a Lync 2010 user, Lync Server 2013 users will be able to view and slides and, if Office Web Apps Server is configured, access new capabilities such as higher resolution display, animations, slide transitions, and embedded video.</span></span> <span data-ttu-id="53436-323">Дополнительные сведения можно найти [в разделе Настройка интеграции с Office Web Apps Server и Lync Server 2013](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md).</span><span class="sxs-lookup"><span data-stu-id="53436-323">For more information, see [Configuring integration with Office Web Apps Server and Lync Server 2013](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md).</span></span>

<span data-ttu-id="53436-324">4The функции присутствия и обмена мгновенными сообщениями в Office Communicator 2007 R2 совместимы с Lync Server 2013, но возможности конференции не поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="53436-324">4The presence and IM features in Office Communicator 2007 R2 are compatible with Lync Server 2013, but conferencing features are not.</span></span> <span data-ttu-id="53436-325">При переходе с Office Communications Server 2007 R2 подходящими для обеспечения взаимодействия и обмена мгновенными сообщениями является Office Communicator 2007 R2, но пользователи должны использовать Lync Web App 2013, чтобы присоединиться к собраниям Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="53436-325">During migration from Office Communications Server 2007 R2, Office Communicator 2007 R2 is suitable for presence and IM interoperability, but users should use Lync Web App 2013 to join Lync Server 2013 meetings.</span></span>

</div>

</div>

<div>

## <a name="scheduling-add-in-support"></a><span data-ttu-id="53436-326">Поддержка планирования надстроек</span><span class="sxs-lookup"><span data-stu-id="53436-326">Scheduling Add-in Support</span></span>

<span data-ttu-id="53436-327">Поддержка различных надстроек для планирования в соответствии с серверной и клиентской версиями обеспечивается совместимостью.</span><span class="sxs-lookup"><span data-stu-id="53436-327">Server support for the various scheduling add-ins is consistent with server and client version compatibility.</span></span> <span data-ttu-id="53436-328">Как правило, в Lync Server 2013 поддерживаются следующие надстройки для планирования.</span><span class="sxs-lookup"><span data-stu-id="53436-328">In general, the following scheduling add-ins are supported on Lync Server 2013.</span></span> <span data-ttu-id="53436-329">Несмотря на то, что предыдущие версии надстроек не предоставляют новые функции надстройки Lync 2013, такие как возможность отключить Микрофоны всех участников и звуков видео при вводе собрания.</span><span class="sxs-lookup"><span data-stu-id="53436-329">However, previous versions of add-ins do not provide new Lync 2013 add-in features, such as the option to mute all attendee audio and video upon meeting entry.</span></span>

  - <span data-ttu-id="53436-330">**Надстройка "собрание по сети" для Lync 2013**   предоставляет те же функции, что и надстройка "собрание по сети" для Lync 2010, при добавлении элементов управления для участников, которые разрешают организаторов на собрание, чтобы запланировать конференции, в которых по умолчанию включены звук и видео для участников.</span><span class="sxs-lookup"><span data-stu-id="53436-330">**Online Meeting Add-in for Lync 2013**   Provides the same features as the Online Meeting Add-in for Lync 2010, with the addition of attendee mute controls, which allow meeting organizers to schedule conferences that have attendee audio and video muted by default.</span></span> <span data-ttu-id="53436-331">Администраторы также могут настроить приглашения на собрание Организации, добавив собственный логотип, URL-адрес службы поддержки, URL-адрес юридического лица или настраиваемый текст нижнего колонтитула.</span><span class="sxs-lookup"><span data-stu-id="53436-331">Administrators can also customize the organization’s meeting invitations by adding a custom logo, a support URL, a legal disclaimer URL, or custom footer text.</span></span>

  - <span data-ttu-id="53436-332">**Надстройка "собрание по сети" для Lync 2010**   — Планирование собраний Lync и удаление возможности планирования конференций Office Live Meeting.</span><span class="sxs-lookup"><span data-stu-id="53436-332">**Online Meeting Add-in for Lync 2010**   Provides scheduling for Lync meetings and removes the capability to schedule Office Live Meeting conferences.</span></span>

  - <span data-ttu-id="53436-333">**Надстройка Office Communicator 2007 R2**   обеспечивает планирование как для конференций Office Live Meeting, так и для конференций Office Communicator 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="53436-333">**Office Communicator 2007 R2 Conferencing Add-in**   Provides scheduling for both Office Live Meeting conferences and Office Communicator 2007 R2 conferences.</span></span> 

<div>


> [!NOTE]  
> <span data-ttu-id="53436-334">Конференции Live Meeting невозможно запланировать на Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="53436-334">Live Meeting conferences cannot be scheduled on Lync Server 2013.</span></span>



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
<th><span data-ttu-id="53436-335">Планирование клиента</span><span class="sxs-lookup"><span data-stu-id="53436-335">Scheduling Client</span></span></th>
<th><span data-ttu-id="53436-336">Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="53436-336">Lync Server 2013</span></span></th>
<th><span data-ttu-id="53436-337">Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="53436-337">Lync Server 2010</span></span></th>
<th><span data-ttu-id="53436-338">Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="53436-338">Office Communications Server 2007 R2</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="53436-339">Надстройка "собрание по сети" для Lync 2013 (может использоваться с Office 2013, Outlook 2010 и Outlook 2007)</span><span class="sxs-lookup"><span data-stu-id="53436-339">Online Meeting Add-in for Lync 2013 (can be used with Office 2013, Outlook 2010, and Outlook 2007)</span></span></p></td>
<td><p><span data-ttu-id="53436-340">Поддерживается</span><span class="sxs-lookup"><span data-stu-id="53436-340">Supported</span></span></p></td>
<td><p><span data-ttu-id="53436-341">Поддерживается (недоступна новая функция надстроек)</span><span class="sxs-lookup"><span data-stu-id="53436-341">Supported (new add-in features not available)</span></span></p></td>
<td><p><span data-ttu-id="53436-342">Не поддерживается</span><span class="sxs-lookup"><span data-stu-id="53436-342">Not Supported</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="53436-343">Веб-планировщик Lync 2013</span><span class="sxs-lookup"><span data-stu-id="53436-343">Lync 2013 Web Scheduler</span></span></p></td>
<td><p><span data-ttu-id="53436-344">Поддерживается</span><span class="sxs-lookup"><span data-stu-id="53436-344">Supported</span></span></p></td>
<td><p><span data-ttu-id="53436-345">Не поддерживается</span><span class="sxs-lookup"><span data-stu-id="53436-345">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="53436-346">Не поддерживается</span><span class="sxs-lookup"><span data-stu-id="53436-346">Not Supported</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="53436-347">собраний по сети для Lync 2010</span><span class="sxs-lookup"><span data-stu-id="53436-347">Online Meeting Add-in for Lync 2010</span></span></p></td>
<td><p><span data-ttu-id="53436-348">Поддерживается</span><span class="sxs-lookup"><span data-stu-id="53436-348">Supported</span></span></p></td>
<td><p><span data-ttu-id="53436-349">Поддерживается</span><span class="sxs-lookup"><span data-stu-id="53436-349">Supported</span></span></p></td>
<td><p><span data-ttu-id="53436-350">Не поддерживается</span><span class="sxs-lookup"><span data-stu-id="53436-350">Not Supported</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="53436-351">Надстройка для конференц-связи Office Communicator 2007 R2</span><span class="sxs-lookup"><span data-stu-id="53436-351">Office Communicator 2007 R2 Conferencing Add-in</span></span></p></td>
<td><p><span data-ttu-id="53436-352">Не поддерживается</span><span class="sxs-lookup"><span data-stu-id="53436-352">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="53436-353">Поддерживается</span><span class="sxs-lookup"><span data-stu-id="53436-353">Supported</span></span></p></td>
<td><p><span data-ttu-id="53436-354">Поддерживается</span><span class="sxs-lookup"><span data-stu-id="53436-354">Supported</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="support-for-joining-meetings"></a><span data-ttu-id="53436-355">Поддержка присоединения к собраниям</span><span class="sxs-lookup"><span data-stu-id="53436-355">Support for Joining Meetings</span></span>

<span data-ttu-id="53436-356">Все клиенты, поддерживаемые Lync Server 2013, могут присоединиться к собраниям Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="53436-356">All of the clients that Lync Server 2013 supports are allowed to join Lync 2013 meetings.</span></span> <span data-ttu-id="53436-357">Поскольку Lync Web App — это веб-компонент сервера, то в тех случаях, когда Lync Web App используется для присоединения к собранию Lync Server 2013, всегда используется новая версия Lync Web App.</span><span class="sxs-lookup"><span data-stu-id="53436-357">Because Lync Web App is a web component of the server, in cases where Lync Web App is used to join a Lync Server 2013 meeting, the newer version of Lync Web App is always used.</span></span>

<span data-ttu-id="53436-358">Пользователи Lync 2013 могут присоединяться к собраниям, размещенным на Lync 2010 и Office Communications Server 2007 R2, с масштабированием функций.</span><span class="sxs-lookup"><span data-stu-id="53436-358">Lync 2013 clients can join meetings hosted on Lync 2010 and Office Communications Server 2007 R2 with scaled-down functionality.</span></span> <span data-ttu-id="53436-359">Возможности, доступные в собрании, ограничиваются версией сервера, на котором размещается собрание.</span><span class="sxs-lookup"><span data-stu-id="53436-359">In-meeting features are limited by the version of the server on which the meeting is hosted.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="53436-360">См. также</span><span class="sxs-lookup"><span data-stu-id="53436-360">See Also</span></span>


[<span data-ttu-id="53436-361">Требования к приложению Lync из Магазина Windows для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="53436-361">Lync Windows Store app requirements for Lync Server 2013</span></span>](lync-server-2013-lync-windows-store-app-requirements.md)  
[<span data-ttu-id="53436-362">Новые возможности конференц-связи в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="53436-362">New conferencing features in Lync Server 2013</span></span>](lync-server-2013-new-conferencing-features.md)  
[<span data-ttu-id="53436-363">Новые возможности для клиентов в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="53436-363">What's new for clients in Lync Server 2013</span></span>](lync-server-2013-what-s-new-for-clients.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

