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
ms.openlocfilehash: 2e00071edd4a3d65e9db763914577983306491fc
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48502676"
---
# <a name="client-interoperability-in-lync-2013"></a><span data-ttu-id="cdf04-102">Взаимодействие клиентов в Lync 2013</span><span class="sxs-lookup"><span data-stu-id="cdf04-102">Client interoperability in Lync 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cdf04-103">_**Последнее изменение темы:** 2016-03-04_</span><span class="sxs-lookup"><span data-stu-id="cdf04-103">_**Topic Last Modified:** 2016-03-04_</span></span>

<span data-ttu-id="cdf04-104">В этом разделе рассказывается о возможности совместного использования клиентами Microsoft Lync Server 2013 и взаимодействии с клиентами из более ранних версий Lync Server и Office Communications Server.</span><span class="sxs-lookup"><span data-stu-id="cdf04-104">This topic discusses the ability of Microsoft Lync Server 2013 clients to coexist and interact with clients from earlier versions of Lync Server and Office Communications Server.</span></span>

<div>

## <a name="server-and-client-compatibility"></a><span data-ttu-id="cdf04-105">Совместимость серверов и клиентов</span><span class="sxs-lookup"><span data-stu-id="cdf04-105">Server and Client Compatibility</span></span>

<span data-ttu-id="cdf04-106">В следующей таблице показаны поддерживаемые сочетания версий клиентов и серверов.</span><span class="sxs-lookup"><span data-stu-id="cdf04-106">The following table shows the supported combinations of client versions and server versions.</span></span> <span data-ttu-id="cdf04-107">В этой таблице показано, поддерживается ли вход, когда клиент пытается подключиться к указанному серверу.</span><span class="sxs-lookup"><span data-stu-id="cdf04-107">This table indicates whether sign-in is supported when the client attempts to connect to the server indicated.</span></span> <span data-ttu-id="cdf04-108">Lync Server 2013 поддерживает предыдущую версию клиента.</span><span class="sxs-lookup"><span data-stu-id="cdf04-108">Lync Server 2013 supports the previous client version.</span></span> <span data-ttu-id="cdf04-109">Кроме того, в отличие от предыдущих выпусков, Lync Server 2010 поддерживает новые клиенты Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="cdf04-109">Also, unlike previous releases, Lync Server 2010 supports the new Lync 2013 clients.</span></span> <span data-ttu-id="cdf04-110">Это позволяет организациям, которые обновляются с Lync Server 2010, развертывать новые клиенты независимо от обновлений Lync Server.</span><span class="sxs-lookup"><span data-stu-id="cdf04-110">This allows organizations who are upgrading from Lync Server 2010 to roll out new clients independent of Lync Server upgrades.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="cdf04-111">Клиент</span><span class="sxs-lookup"><span data-stu-id="cdf04-111">Client</span></span></th>
<th><span data-ttu-id="cdf04-112">Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cdf04-112">Lync Server 2013</span></span></th>
<th><span data-ttu-id="cdf04-113">Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="cdf04-113">Lync Server 2010</span></span></th>
<th><span data-ttu-id="cdf04-114">Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="cdf04-114">Office Communications Server 2007 R2</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="cdf04-115">Lync 2013</span><span class="sxs-lookup"><span data-stu-id="cdf04-115">Lync 2013</span></span></p></td>
<td><p><span data-ttu-id="cdf04-116">Поддерживается</span><span class="sxs-lookup"><span data-stu-id="cdf04-116">Supported</span></span></p></td>
<td><p><span data-ttu-id="cdf04-117">Supported5</span><span class="sxs-lookup"><span data-stu-id="cdf04-117">Supported5</span></span></p></td>
<td><p><span data-ttu-id="cdf04-118">Не поддерживается</span><span class="sxs-lookup"><span data-stu-id="cdf04-118">Not Supported</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cdf04-119">Lync 2013 Basic</span><span class="sxs-lookup"><span data-stu-id="cdf04-119">Lync 2013 Basic</span></span></p></td>
<td><p><span data-ttu-id="cdf04-120">Поддерживается</span><span class="sxs-lookup"><span data-stu-id="cdf04-120">Supported</span></span></p></td>
<td><p><span data-ttu-id="cdf04-121">Поддерживается</span><span class="sxs-lookup"><span data-stu-id="cdf04-121">Supported</span></span></p></td>
<td><p><span data-ttu-id="cdf04-122">Не поддерживается</span><span class="sxs-lookup"><span data-stu-id="cdf04-122">Not Supported</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cdf04-123">Lync Web App 2013</span><span class="sxs-lookup"><span data-stu-id="cdf04-123">Lync Web App 2013</span></span></p></td>
<td><p><span data-ttu-id="cdf04-124">Поддерживается</span><span class="sxs-lookup"><span data-stu-id="cdf04-124">Supported</span></span></p></td>
<td><p><span data-ttu-id="cdf04-125">Не поддерживается</span><span class="sxs-lookup"><span data-stu-id="cdf04-125">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="cdf04-126">Не поддерживается</span><span class="sxs-lookup"><span data-stu-id="cdf04-126">Not Supported</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cdf04-127">Lync 2010</span><span class="sxs-lookup"><span data-stu-id="cdf04-127">Lync 2010</span></span></p></td>
<td><p><span data-ttu-id="cdf04-128">Поддерживается</span><span class="sxs-lookup"><span data-stu-id="cdf04-128">Supported</span></span></p></td>
<td><p><span data-ttu-id="cdf04-129">Поддерживается</span><span class="sxs-lookup"><span data-stu-id="cdf04-129">Supported</span></span></p></td>
<td><p><span data-ttu-id="cdf04-130">Не поддерживается</span><span class="sxs-lookup"><span data-stu-id="cdf04-130">Not Supported</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cdf04-131">Lync 2010 Attendant</span><span class="sxs-lookup"><span data-stu-id="cdf04-131">Lync 2010 Attendant</span></span></p></td>
<td><p><span data-ttu-id="cdf04-132">Поддерживается</span><span class="sxs-lookup"><span data-stu-id="cdf04-132">Supported</span></span></p></td>
<td><p><span data-ttu-id="cdf04-133">Поддерживается</span><span class="sxs-lookup"><span data-stu-id="cdf04-133">Supported</span></span></p></td>
<td><p><span data-ttu-id="cdf04-134">Не поддерживается</span><span class="sxs-lookup"><span data-stu-id="cdf04-134">Not Supported</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cdf04-135">Lync 2010 Group Chat</span><span class="sxs-lookup"><span data-stu-id="cdf04-135">Lync 2010 Group Chat</span></span></p></td>
<td><p><span data-ttu-id="cdf04-136">Supported1</span><span class="sxs-lookup"><span data-stu-id="cdf04-136">Supported1</span></span></p></td>
<td><p><span data-ttu-id="cdf04-137">Supported2</span><span class="sxs-lookup"><span data-stu-id="cdf04-137">Supported2</span></span></p></td>
<td><p><span data-ttu-id="cdf04-138">Неприменимо</span><span class="sxs-lookup"><span data-stu-id="cdf04-138">Not Applicable</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cdf04-139">Lync Web App 2010</span><span class="sxs-lookup"><span data-stu-id="cdf04-139">Lync Web App 2010</span></span></p></td>
<td><p><span data-ttu-id="cdf04-140">Не поддерживается</span><span class="sxs-lookup"><span data-stu-id="cdf04-140">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="cdf04-141">Поддерживается</span><span class="sxs-lookup"><span data-stu-id="cdf04-141">Supported</span></span></p></td>
<td><p><span data-ttu-id="cdf04-142">Не поддерживается</span><span class="sxs-lookup"><span data-stu-id="cdf04-142">Not Supported</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cdf04-143">Lync 2010 Attendee</span><span class="sxs-lookup"><span data-stu-id="cdf04-143">Lync 2010 Attendee</span></span></p></td>
<td><p><span data-ttu-id="cdf04-144">Не Supported3</span><span class="sxs-lookup"><span data-stu-id="cdf04-144">Not Supported3</span></span></p></td>
<td><p><span data-ttu-id="cdf04-145">Поддерживается</span><span class="sxs-lookup"><span data-stu-id="cdf04-145">Supported</span></span></p></td>
<td><p><span data-ttu-id="cdf04-146">Не поддерживается</span><span class="sxs-lookup"><span data-stu-id="cdf04-146">Not Supported</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cdf04-147">Office Communicator 2007 R2</span><span class="sxs-lookup"><span data-stu-id="cdf04-147">Office Communicator 2007 R2</span></span></p></td>
<td><p><span data-ttu-id="cdf04-148">Interoperable4</span><span class="sxs-lookup"><span data-stu-id="cdf04-148">Interoperable4</span></span></p></td>
<td><p><span data-ttu-id="cdf04-149">Поддерживается</span><span class="sxs-lookup"><span data-stu-id="cdf04-149">Supported</span></span></p></td>
<td><p><span data-ttu-id="cdf04-150">Поддерживается</span><span class="sxs-lookup"><span data-stu-id="cdf04-150">Supported</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cdf04-151">Помощник Microsoft Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="cdf04-151">Microsoft Office Communications Server 2007 R2 Attendant</span></span></p></td>
<td><p><span data-ttu-id="cdf04-152">Не поддерживается</span><span class="sxs-lookup"><span data-stu-id="cdf04-152">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="cdf04-153">Поддерживается</span><span class="sxs-lookup"><span data-stu-id="cdf04-153">Supported</span></span></p></td>
<td><p><span data-ttu-id="cdf04-154">Поддерживается</span><span class="sxs-lookup"><span data-stu-id="cdf04-154">Supported</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cdf04-155">Office Communicator 2007</span><span class="sxs-lookup"><span data-stu-id="cdf04-155">Office Communicator 2007</span></span></p></td>
<td><p><span data-ttu-id="cdf04-156">Не поддерживается</span><span class="sxs-lookup"><span data-stu-id="cdf04-156">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="cdf04-157">Поддерживается</span><span class="sxs-lookup"><span data-stu-id="cdf04-157">Supported</span></span></p></td>
<td><p><span data-ttu-id="cdf04-158">Поддерживается</span><span class="sxs-lookup"><span data-stu-id="cdf04-158">Supported</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cdf04-159">Office Live Meeting 2007</span><span class="sxs-lookup"><span data-stu-id="cdf04-159">Office Live Meeting 2007</span></span></p></td>
<td><p><span data-ttu-id="cdf04-160">Не поддерживается</span><span class="sxs-lookup"><span data-stu-id="cdf04-160">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="cdf04-161">Поддерживается</span><span class="sxs-lookup"><span data-stu-id="cdf04-161">Supported</span></span></p></td>
<td><p><span data-ttu-id="cdf04-162">Поддерживается</span><span class="sxs-lookup"><span data-stu-id="cdf04-162">Supported</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cdf04-163">Приложение Lync для Магазина Windows</span><span class="sxs-lookup"><span data-stu-id="cdf04-163">Lync Windows Store app</span></span></p></td>
<td><p><span data-ttu-id="cdf04-164">Поддерживается</span><span class="sxs-lookup"><span data-stu-id="cdf04-164">Supported</span></span></p></td>
<td><p><span data-ttu-id="cdf04-165">Поддерживается</span><span class="sxs-lookup"><span data-stu-id="cdf04-165">Supported</span></span></p></td>
<td><p><span data-ttu-id="cdf04-166">Не поддерживается</span><span class="sxs-lookup"><span data-stu-id="cdf04-166">Not Supported</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="cdf04-167">1For Details: [Migration from Lync server 2010, Group Chat или Office Communications Server 2007 R2 Group Chat to Lync server 2013, сервер сохраняемого чата](migration-from-lync-server-2010-group-chat-or-office-communications-server-2007-r2-group-chat-to-lync-server-2013-persistent-chat-server.md).</span><span class="sxs-lookup"><span data-stu-id="cdf04-167">1For details, see [Migration from Lync Server 2010, Group Chat or Office Communications Server 2007 R2 Group Chat to Lync Server 2013, Persistent Chat Server](migration-from-lync-server-2010-group-chat-or-office-communications-server-2007-r2-group-chat-to-lync-server-2013-persistent-chat-server.md).</span></span>

<span data-ttu-id="cdf04-168">2In Microsoft Lync Server 2010, доступны функции группового чата с сервером группового чата, доверенным сторонним приложением для Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="cdf04-168">2In Microsoft Lync Server 2010, group chat functionality was available with Group Chat Server, a third-party trusted application for Lync Server 2010.</span></span> <span data-ttu-id="cdf04-169">Клиенты Lync 2013 несовместимы с Lync Server 2010, группового чата.</span><span class="sxs-lookup"><span data-stu-id="cdf04-169">Lync 2013 clients are not compatible with Lync Server 2010, Group Chat.</span></span>

<span data-ttu-id="cdf04-170">3Lync Web App 2013 теперь предоставляет полный интерфейс для собраний, включая аудио-и видеоданные, и считается заменой участнику Lync 2010.</span><span class="sxs-lookup"><span data-stu-id="cdf04-170">3Lync Web App 2013 now provides a full in-meeting experience, including computer audio and video, and is considered the replacement for Lync 2010 Attendee.</span></span> <span data-ttu-id="cdf04-171">Lync 2010 участник будет подключаться к Lync Server 2013 только при использовании неподдерживаемого браузера (Internet Explorer 6 или Internet Explorer 7) и Windows XP.</span><span class="sxs-lookup"><span data-stu-id="cdf04-171">Lync 2010 Attendee will connect to Lync Server 2013 only when you are using an unsupported browser (Internet Explorer 6 or Internet Explorer 7) and Windows XP.</span></span>

<span data-ttu-id="cdf04-172">4The присутствия и функции обмена мгновенными сообщениями в Office Communicator 2007 R2 совместимы с Lync Server 2013, но функции конференц-связи не поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="cdf04-172">4The presence and IM features in Office Communicator 2007 R2 are compatible with Lync Server 2013, but conferencing features are not.</span></span> <span data-ttu-id="cdf04-173">Во время миграции с Office Communications Server 2007 R2 приложение Office Communicator 2007 R2 подходит для взаимодействия с присутствием и обменом мгновенными сообщениями, но пользователи должны использовать Lync Web App 2013, чтобы присоединиться к собраниям Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="cdf04-173">During migration from Office Communications Server 2007 R2, Office Communicator 2007 R2 is suitable for presence and IM interoperability, but users should use Lync Web App 2013 to join Lync Server 2013 meetings.</span></span>

<span data-ttu-id="cdf04-174">5 для получения ограничений обратитесь к разделу "Поддержка функций конференц-связи для клиентов Lync 2013 в Lync Server 2010 для собраний" Далее в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="cdf04-174">5 For limitations, see "Conferencing Feature Support for Lync 2013 Clients in Lync Server 2010 Meetings" later in this topic.</span></span>

</div>

<div>

## <a name="interoperability-among-clients"></a><span data-ttu-id="cdf04-175">Взаимодействие между клиентами</span><span class="sxs-lookup"><span data-stu-id="cdf04-175">Interoperability among Clients</span></span>

<span data-ttu-id="cdf04-176">В выпуске Lync Server 2013 различные клиентские версии могут беспрепятственно взаимодействовать как в одноранговых, так и в сценариях конференц-связи.</span><span class="sxs-lookup"><span data-stu-id="cdf04-176">With the Lync Server 2013 release, various client versions can interact seamlessly in both peer-to-peer and conferencing scenarios.</span></span> <span data-ttu-id="cdf04-177">В этом разделе описывается доступность функций, когда пользователи взаимодействуют с другими пользователями, использующими разные версии клиентов и серверов.</span><span class="sxs-lookup"><span data-stu-id="cdf04-177">This section discusses feature availability when users interact with other users who are using different versions of clients and servers.</span></span>

<div>

## <a name="peer-to-peer-feature-support"></a><span data-ttu-id="cdf04-178">Поддержка одноранговых функций</span><span class="sxs-lookup"><span data-stu-id="cdf04-178">Peer-to-Peer Feature Support</span></span>

<span data-ttu-id="cdf04-179">Одноранговые функции поддерживаются для пользователей, размещенных в различных версиях сервера и использующих разные версии клиентов.</span><span class="sxs-lookup"><span data-stu-id="cdf04-179">Peer-to-peer features are supported for users who are homed on different versions of the server and who are using different client versions.</span></span> <span data-ttu-id="cdf04-180">Функции конечного пользователя и доступные функции соответствуют возможностям клиента пользователя и версии сервера, на котором выполнен вход пользователя.</span><span class="sxs-lookup"><span data-stu-id="cdf04-180">The end-user experience and available features are consistent with the capabilities of the user’s client and the version of the server the user is signed in to.</span></span> <span data-ttu-id="cdf04-181">Другими словами:</span><span class="sxs-lookup"><span data-stu-id="cdf04-181">In other words:</span></span>

  - <span data-ttu-id="cdf04-182">Если пользователь вошел в Lync Server 2013 с более старым клиентом, он будет иметь такой же интерфейс, что и для пользователя.</span><span class="sxs-lookup"><span data-stu-id="cdf04-182">If a user is signed in to Lync Server 2013 with an older client, the user will have the same experience he or she is used to.</span></span> <span data-ttu-id="cdf04-183">Никакие новые функции, введенные в Lync Server 2013, будут недоступны до тех пор, пока клиент пользователя не будет обновлен.</span><span class="sxs-lookup"><span data-stu-id="cdf04-183">None of the new features introduced in Lync Server 2013 will be available until the user’s client is upgraded.</span></span> <span data-ttu-id="cdf04-184">Примеры включают представление "Коллекция видео", видео в формате HD, обновленный общий доступ к PowerPoint и возможность отключения звука и видео участников при вводе собрания.</span><span class="sxs-lookup"><span data-stu-id="cdf04-184">Examples include video gallery view, HD video, updated PowerPoint sharing, and the option to mute all attendee audio and video upon meeting entry.</span></span> <span data-ttu-id="cdf04-185">Новые возможности, описанные в разделе [новые функции конференц-связи в Lync server 2013](lync-server-2013-new-conferencing-features.md) , а также новые возможности [для клиентов в Lync Server 2013](lync-server-2013-what-s-new-for-clients.md).</span><span class="sxs-lookup"><span data-stu-id="cdf04-185">The new features are outlined in [New conferencing features in Lync Server 2013](lync-server-2013-new-conferencing-features.md) and [What's new for clients in Lync Server 2013](lync-server-2013-what-s-new-for-clients.md).</span></span>

  - <span data-ttu-id="cdf04-186">Если пользователь вошел в Lync Server 2010 с клиентом Lync 2013, все новые функции, не поддерживаемые в Lync Server 2010, будут недоступны до тех пор, пока пользователь не будет перемещен в Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="cdf04-186">If a user is signed in to Lync Server 2010 with a Lync 2013 client, any new features not supported by Lync Server 2010 will be unavailable until the user is moved to Lync Server 2013.</span></span>

<span data-ttu-id="cdf04-187">В следующей таблице сравнивается доступность функций в одноранговых сеансах, где клиент входит в состав Lync Server 2013 или Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="cdf04-187">The following table compares feature availability in peer-to-peer sessions where the client is signed in to either Lync Server 2013 or Lync Server 2010.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="cdf04-188">Lync Web App и Lync 2010 участник являются клиентами только для собраний и не включены в эту таблицу.</span><span class="sxs-lookup"><span data-stu-id="cdf04-188">Lync Web App and Lync 2010 Attendee are meeting-only clients and aren’t included in this table.</span></span>



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
<th><span data-ttu-id="cdf04-189">Клиент</span><span class="sxs-lookup"><span data-stu-id="cdf04-189">Client</span></span></th>
<th><span data-ttu-id="cdf04-190">Обмен мгновенными сообщениями</span><span class="sxs-lookup"><span data-stu-id="cdf04-190">Instant Messaging</span></span></th>
<th><span data-ttu-id="cdf04-191">Присутствие</span><span class="sxs-lookup"><span data-stu-id="cdf04-191">Presence</span></span></th>
<th><span data-ttu-id="cdf04-192">Голос</span><span class="sxs-lookup"><span data-stu-id="cdf04-192">Voice</span></span></th>
<th><span data-ttu-id="cdf04-193">Видео</span><span class="sxs-lookup"><span data-stu-id="cdf04-193">Video</span></span></th>
<th><span data-ttu-id="cdf04-194">Совместное использование приложений</span><span class="sxs-lookup"><span data-stu-id="cdf04-194">Application Sharing</span></span></th>
<th><span data-ttu-id="cdf04-195">Передача файлов</span><span class="sxs-lookup"><span data-stu-id="cdf04-195">File Transfer</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="cdf04-196">Lync 2013</span><span class="sxs-lookup"><span data-stu-id="cdf04-196">Lync 2013</span></span></p></td>
<td><p><span data-ttu-id="cdf04-197">Да</span><span class="sxs-lookup"><span data-stu-id="cdf04-197">Yes</span></span></p></td>
<td><p><span data-ttu-id="cdf04-198">Да</span><span class="sxs-lookup"><span data-stu-id="cdf04-198">Yes</span></span></p></td>
<td><p><span data-ttu-id="cdf04-199">Да</span><span class="sxs-lookup"><span data-stu-id="cdf04-199">Yes</span></span></p></td>
<td><p><span data-ttu-id="cdf04-200">Да</span><span class="sxs-lookup"><span data-stu-id="cdf04-200">Yes</span></span></p></td>
<td><p><span data-ttu-id="cdf04-201">Да</span><span class="sxs-lookup"><span data-stu-id="cdf04-201">Yes</span></span></p></td>
<td><p><span data-ttu-id="cdf04-202">Да</span><span class="sxs-lookup"><span data-stu-id="cdf04-202">Yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cdf04-203">Lync 2013 Basic</span><span class="sxs-lookup"><span data-stu-id="cdf04-203">Lync 2013 Basic</span></span></p></td>
<td><p><span data-ttu-id="cdf04-204">Да</span><span class="sxs-lookup"><span data-stu-id="cdf04-204">Yes</span></span></p></td>
<td><p><span data-ttu-id="cdf04-205">Да</span><span class="sxs-lookup"><span data-stu-id="cdf04-205">Yes</span></span></p></td>
<td><p><span data-ttu-id="cdf04-206">Да</span><span class="sxs-lookup"><span data-stu-id="cdf04-206">Yes</span></span></p></td>
<td><p><span data-ttu-id="cdf04-207">Да</span><span class="sxs-lookup"><span data-stu-id="cdf04-207">Yes</span></span></p></td>
<td><p><span data-ttu-id="cdf04-208">Да</span><span class="sxs-lookup"><span data-stu-id="cdf04-208">Yes</span></span></p></td>
<td><p><span data-ttu-id="cdf04-209">Да</span><span class="sxs-lookup"><span data-stu-id="cdf04-209">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cdf04-210">Lync 2010</span><span class="sxs-lookup"><span data-stu-id="cdf04-210">Lync 2010</span></span></p></td>
<td><p><span data-ttu-id="cdf04-211">Да</span><span class="sxs-lookup"><span data-stu-id="cdf04-211">Yes</span></span></p></td>
<td><p><span data-ttu-id="cdf04-212">Да</span><span class="sxs-lookup"><span data-stu-id="cdf04-212">Yes</span></span></p></td>
<td><p><span data-ttu-id="cdf04-213">Да</span><span class="sxs-lookup"><span data-stu-id="cdf04-213">Yes</span></span></p></td>
<td><p><span data-ttu-id="cdf04-214">Да</span><span class="sxs-lookup"><span data-stu-id="cdf04-214">Yes</span></span></p></td>
<td><p><span data-ttu-id="cdf04-215">Да</span><span class="sxs-lookup"><span data-stu-id="cdf04-215">Yes</span></span></p></td>
<td><p><span data-ttu-id="cdf04-216">Да</span><span class="sxs-lookup"><span data-stu-id="cdf04-216">Yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cdf04-217">Lync 2010 Attendant</span><span class="sxs-lookup"><span data-stu-id="cdf04-217">Lync 2010 Attendant</span></span></p></td>
<td><p><span data-ttu-id="cdf04-218">Да</span><span class="sxs-lookup"><span data-stu-id="cdf04-218">Yes</span></span></p></td>
<td><p><span data-ttu-id="cdf04-219">Да</span><span class="sxs-lookup"><span data-stu-id="cdf04-219">Yes</span></span></p></td>
<td><p><span data-ttu-id="cdf04-220">Да</span><span class="sxs-lookup"><span data-stu-id="cdf04-220">Yes</span></span></p></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cdf04-221">Lync 2010 Mobile</span><span class="sxs-lookup"><span data-stu-id="cdf04-221">Lync 2010 Mobile</span></span></p></td>
<td><p><span data-ttu-id="cdf04-222">Да</span><span class="sxs-lookup"><span data-stu-id="cdf04-222">Yes</span></span></p></td>
<td><p><span data-ttu-id="cdf04-223">Да</span><span class="sxs-lookup"><span data-stu-id="cdf04-223">Yes</span></span></p></td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cdf04-224">Lync Phone Edition</span><span class="sxs-lookup"><span data-stu-id="cdf04-224">Lync Phone Edition</span></span></p></td>
<td><p><span data-ttu-id="cdf04-225">Да</span><span class="sxs-lookup"><span data-stu-id="cdf04-225">Yes</span></span></p></td>
<td><p><span data-ttu-id="cdf04-226">Да</span><span class="sxs-lookup"><span data-stu-id="cdf04-226">Yes</span></span></p></td>
<td><p><span data-ttu-id="cdf04-227">Да</span><span class="sxs-lookup"><span data-stu-id="cdf04-227">Yes</span></span></p></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cdf04-228">Office Communicator 2007 R2</span><span class="sxs-lookup"><span data-stu-id="cdf04-228">Office Communicator 2007 R2</span></span></p></td>
<td><p><span data-ttu-id="cdf04-229">Да</span><span class="sxs-lookup"><span data-stu-id="cdf04-229">Yes</span></span></p></td>
<td><p><span data-ttu-id="cdf04-230">Да</span><span class="sxs-lookup"><span data-stu-id="cdf04-230">Yes</span></span></p></td>
<td><p><span data-ttu-id="cdf04-231">Да</span><span class="sxs-lookup"><span data-stu-id="cdf04-231">Yes</span></span></p></td>
<td><p><span data-ttu-id="cdf04-232">Да</span><span class="sxs-lookup"><span data-stu-id="cdf04-232">Yes</span></span></p></td>
<td><p><span data-ttu-id="cdf04-233">Yes1</span><span class="sxs-lookup"><span data-stu-id="cdf04-233">Yes1</span></span></p></td>
<td><p><span data-ttu-id="cdf04-234">Да</span><span class="sxs-lookup"><span data-stu-id="cdf04-234">Yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cdf04-235">Общедоступная служба обмена мгновенными сообщениями (AOL, Yahoo!)</span><span class="sxs-lookup"><span data-stu-id="cdf04-235">Public IM (AOL, Yahoo!)</span></span></p></td>
<td><p><span data-ttu-id="cdf04-236">Да</span><span class="sxs-lookup"><span data-stu-id="cdf04-236">Yes</span></span></p></td>
<td><p><span data-ttu-id="cdf04-237">Да</span><span class="sxs-lookup"><span data-stu-id="cdf04-237">Yes</span></span></p></td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cdf04-238">Общедоступная служба обмена мгновенными сообщениями (MSN, Windows Live Messenger)</span><span class="sxs-lookup"><span data-stu-id="cdf04-238">Public IM (MSN, Windows Live Messenger)</span></span></p></td>
<td><p><span data-ttu-id="cdf04-239">Да</span><span class="sxs-lookup"><span data-stu-id="cdf04-239">Yes</span></span></p></td>
<td><p><span data-ttu-id="cdf04-240">Да</span><span class="sxs-lookup"><span data-stu-id="cdf04-240">Yes</span></span></p></td>
<td><p><span data-ttu-id="cdf04-241">Да</span><span class="sxs-lookup"><span data-stu-id="cdf04-241">Yes</span></span></p></td>
<td><p><span data-ttu-id="cdf04-242">Да</span><span class="sxs-lookup"><span data-stu-id="cdf04-242">Yes</span></span></p></td>
<td></td>
<td></td>
</tr>
</tbody>
</table>


<div>


> [!IMPORTANT]  
> <UL>
> <LI>
> <P><span data-ttu-id="cdf04-243">С 1 сентября 2012 г. Лицензия на подписку общедоступных служб обмена мгновенными сообщениями Microsoft Lync (PIC усл) больше недоступна для приобретения новых или обновленных договоров.</span><span class="sxs-lookup"><span data-stu-id="cdf04-243">As of September 1st, 2012, the Microsoft Lync Public IM Connectivity User Subscription License (PIC USL) is no longer available for the purchase for new or renewing agreements.</span></span> <span data-ttu-id="cdf04-244">Клиенты с активными лицензиями смогут продолжать Федерацию с помощью Yahoo!</span><span class="sxs-lookup"><span data-stu-id="cdf04-244">Customers with active licenses will be able to continue to federate with Yahoo!</span></span> <span data-ttu-id="cdf04-245">Messenger до даты завершения работы службы.</span><span class="sxs-lookup"><span data-stu-id="cdf04-245">Messenger until the service shutdown date.</span></span> <span data-ttu-id="cdf04-246">Дата окончания срока жизни 2014 для AOL и Yahoo!</span><span class="sxs-lookup"><span data-stu-id="cdf04-246">An end of life date of June 2014 for AOL and Yahoo!</span></span> <span data-ttu-id="cdf04-247">объявлено.</span><span class="sxs-lookup"><span data-stu-id="cdf04-247">has been announced.</span></span> <span data-ttu-id="cdf04-248">Дополнительные сведения см <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">в разделе Поддержка общедоступной службы обмена мгновенными сообщениями в Lync Server 2013</A>..</span><span class="sxs-lookup"><span data-stu-id="cdf04-248">For details, see <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Support for public instant messenger connectivity in Lync Server 2013</A>..</span></span></P>
> <LI>
> <P><span data-ttu-id="cdf04-249">УСЛ PIC — это лицензия на помесячную подписку на уровне пользователя, которая требуется для Lync Server или Office Communications Server для Федерации с Yahoo!</span><span class="sxs-lookup"><span data-stu-id="cdf04-249">The PIC USL is a per-user, per-month subscription license that is required for Lync Server or Office Communications Server to federate with Yahoo!</span></span> <span data-ttu-id="cdf04-250">Messenger.</span><span class="sxs-lookup"><span data-stu-id="cdf04-250">Messenger.</span></span> <span data-ttu-id="cdf04-251">Способность корпорации Майкрософт предоставлять эту службу зависит от поддержки компании Yahoo!, основного соглашения, для которого обновление не выполняется.</span><span class="sxs-lookup"><span data-stu-id="cdf04-251">Microsoft’s ability to provide this service has been contingent upon support from Yahoo!, the underlying agreement for which will not be renewed.</span></span></P>
> <LI>
> <P><span data-ttu-id="cdf04-252">Lync — это мощное средство для связи между организациями и пользователями мира.</span><span class="sxs-lookup"><span data-stu-id="cdf04-252">More than ever, Lync is a powerful tool for connecting across organizations and with individuals around the world.</span></span> <span data-ttu-id="cdf04-253">Для Федерации с Windows Live Messenger не требуется дополнительных лицензий на пользователей и устройств, не относящихся к стандарту Lync CAL.</span><span class="sxs-lookup"><span data-stu-id="cdf04-253">Federation with Windows Live Messenger requires no additional user/device licenses beyond the Lync Standard CAL.</span></span> <span data-ttu-id="cdf04-254">В этот список будет добавлена Федерация Skype, которая позволяет пользователям Lync достигать сотни миллионов людей с помощью обмена мгновенными сообщениями и голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="cdf04-254">Skype federation will be added to this list, enabling Lync users to reach hundreds of millions of people through IM and voice.</span></span></P></LI></UL>



</div>

<span data-ttu-id="cdf04-255">1 в Office Communicator 2007 R2 доступен только общий доступ к рабочему столу (а не к совместному использованию программ).</span><span class="sxs-lookup"><span data-stu-id="cdf04-255">1 In Office Communicator 2007 R2, only desktop sharing (and not program sharing) is available.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="cdf04-256">Общий доступ к рабочему столу Office Communicator 2007 R2 и Skype для бизнеса 2015 невозможно инициировать из нового клиента, когда применяется пользовательский интерфейс клиента Skype для бизнеса 2015.</span><span class="sxs-lookup"><span data-stu-id="cdf04-256">Desktop sharing between Office Communicator 2007 R2 and Skype for Business 2015 cannot be initiated from the newer client when the Skype for Business 2015 client user interface is enforced.</span></span>



</div>

</div>

<div>

## <a name="conferencing-feature-support-for-lync-2013-clients-in-lync-server-2010-meetings"></a><span data-ttu-id="cdf04-257">Поддержка функций конференц-связи для клиентов Lync 2013 в Lync Server 2010 для собраний</span><span class="sxs-lookup"><span data-stu-id="cdf04-257">Conferencing Feature Support for Lync 2013 Clients in Lync Server 2010 Meetings</span></span>

<span data-ttu-id="cdf04-258">Когда пользователи присоединяются к Lync Server 2010 meetings с клиентом Lync 2013, у них есть доступ к клиентским функциям Lync 2013 со следующими исключениями:</span><span class="sxs-lookup"><span data-stu-id="cdf04-258">When users join Lync Server 2010 meetings with a Lync 2013 client, they have access to Lync 2013 client features with the following exceptions:</span></span>

  - <span data-ttu-id="cdf04-259">В параметрах управления **участниками** , доступ к которым осуществляется путем указания значка "люди" в окне собрания, параметр "не вести **мгновенный обмен мгновенными сообщениями** " не работает.</span><span class="sxs-lookup"><span data-stu-id="cdf04-259">In the **Participants** management options, which are accessible by pointing to the people icon in the meeting window, the **No Meeting IM** option does not function.</span></span>

  - <span data-ttu-id="cdf04-260">Представление галереи не работает в видеоконференциях.</span><span class="sxs-lookup"><span data-stu-id="cdf04-260">Gallery View does not function in video conferences.</span></span> <span data-ttu-id="cdf04-261">Пользователю развидится только активный динамик, а не все динамики.</span><span class="sxs-lookup"><span data-stu-id="cdf04-261">The user sees only the active speaker instead of all speakers.</span></span> <span data-ttu-id="cdf04-262">В списке выберите параметры **макета** недоступно **представление "коллекция** "</span><span class="sxs-lookup"><span data-stu-id="cdf04-262">In the list of **Pick a Layout** options, **Gallery View** is unavailable</span></span>

  - <span data-ttu-id="cdf04-263">Список участников по умолчанию отображается в видеоконференциях.</span><span class="sxs-lookup"><span data-stu-id="cdf04-263">The participant list displays by default in video conferences.</span></span>

  - <span data-ttu-id="cdf04-264">Когда вы щелкаете правой кнопкой мыши пользователя в списке участников, вы не сможете получить доступ к параметрам управления участниками **коллекции и закрепить** **его** в коллекции.</span><span class="sxs-lookup"><span data-stu-id="cdf04-264">When right-clicking a user in the participants list, the **Lock the Video Spotlight** and **Pin to Gallery** participant management options are unavailable.</span></span>

</div>

<div>

## <a name="conferencing-feature-support-in-lync-server-2013-meetings"></a><span data-ttu-id="cdf04-265">Поддержка функций конференц-связи в Lync Server 2013 meetings</span><span class="sxs-lookup"><span data-stu-id="cdf04-265">Conferencing Feature Support in Lync Server 2013 Meetings</span></span>

<span data-ttu-id="cdf04-266">Lync Server 2013 предоставляет новые функции конференц-связи, которые становятся доступными пользователям после перемещения их учетных записей в Lync Server 2013 и входе в систему с помощью клиента Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="cdf04-266">Lync Server 2013 provides new conferencing features that become available to users after their accounts are moved to Lync Server 2013 and they sign in with the Lync 2013 client.</span></span> <span data-ttu-id="cdf04-267">К примерам относится представление "Коллекция видео", видео высокой четкости, общий доступ к PowerPoint и возможность отключения звука и видео участников при вводе собрания.</span><span class="sxs-lookup"><span data-stu-id="cdf04-267">Examples include video gallery view, HD video, PowerPoint sharing, and the option to mute all attendee audio and video upon meeting entry.</span></span> <span data-ttu-id="cdf04-268">Новые возможности, описанные в разделе [новые функции конференц-связи в Lync server 2013](lync-server-2013-new-conferencing-features.md) , а также новые возможности [для клиентов в Lync Server 2013](lync-server-2013-what-s-new-for-clients.md).</span><span class="sxs-lookup"><span data-stu-id="cdf04-268">The new features are outlined in [New conferencing features in Lync Server 2013](lync-server-2013-new-conferencing-features.md) and [What's new for clients in Lync Server 2013](lync-server-2013-what-s-new-for-clients.md).</span></span>

<span data-ttu-id="cdf04-269">В Lync Server 2013 для собраний некоторые функции конференций поддерживаются для пользователей, размещенных в различных версиях сервера и использующих разные клиенты и клиентские версии.</span><span class="sxs-lookup"><span data-stu-id="cdf04-269">In Lync Server 2013 meetings, certain conferencing features are supported for users who are homed on different versions of the server and who are using different clients and client versions.</span></span> <span data-ttu-id="cdf04-270">Когда клиенты присоединяются к собранию Lync Server 2013, у пользователей есть доступ к функциям и функциям, представленным в этой таблице.</span><span class="sxs-lookup"><span data-stu-id="cdf04-270">When clients join a Lync Server 2013 meeting, users have access to the features and capabilities shown in this table.</span></span>


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
<th><span data-ttu-id="cdf04-271">Клиент</span><span class="sxs-lookup"><span data-stu-id="cdf04-271">Client</span></span></th>
<th><span data-ttu-id="cdf04-272">Обмен мгновенными сообщениями в одноранговой сети</span><span class="sxs-lookup"><span data-stu-id="cdf04-272">Peer-to-peer IM</span></span></th>
<th><span data-ttu-id="cdf04-273">Голос</span><span class="sxs-lookup"><span data-stu-id="cdf04-273">Voice</span></span></th>
<th><span data-ttu-id="cdf04-274">Видео</span><span class="sxs-lookup"><span data-stu-id="cdf04-274">Video</span></span></th>
<th><span data-ttu-id="cdf04-275">Совместное использование приложений</span><span class="sxs-lookup"><span data-stu-id="cdf04-275">Application Sharing</span></span></th>
<th><span data-ttu-id="cdf04-276">PowerPoint</span><span class="sxs-lookup"><span data-stu-id="cdf04-276">PowerPoint</span></span></th>
<th><span data-ttu-id="cdf04-277">Передача файлов</span><span class="sxs-lookup"><span data-stu-id="cdf04-277">File Transfer</span></span></th>
<th><span data-ttu-id="cdf04-278">Доска</span><span class="sxs-lookup"><span data-stu-id="cdf04-278">Whiteboard</span></span></th>
<th><span data-ttu-id="cdf04-279">Опрос</span><span class="sxs-lookup"><span data-stu-id="cdf04-279">Polling</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="cdf04-280">Lync 2013</span><span class="sxs-lookup"><span data-stu-id="cdf04-280">Lync 2013</span></span></p></td>
<td><p><span data-ttu-id="cdf04-281">Да</span><span class="sxs-lookup"><span data-stu-id="cdf04-281">Yes</span></span></p></td>
<td><p><span data-ttu-id="cdf04-282">Да</span><span class="sxs-lookup"><span data-stu-id="cdf04-282">Yes</span></span></p></td>
<td><p><span data-ttu-id="cdf04-283">Да</span><span class="sxs-lookup"><span data-stu-id="cdf04-283">Yes</span></span></p></td>
<td><p><span data-ttu-id="cdf04-284">Да</span><span class="sxs-lookup"><span data-stu-id="cdf04-284">Yes</span></span></p></td>
<td><p><span data-ttu-id="cdf04-285">Да</span><span class="sxs-lookup"><span data-stu-id="cdf04-285">Yes</span></span></p></td>
<td><p><span data-ttu-id="cdf04-286">Да</span><span class="sxs-lookup"><span data-stu-id="cdf04-286">Yes</span></span></p></td>
<td><p><span data-ttu-id="cdf04-287">Да</span><span class="sxs-lookup"><span data-stu-id="cdf04-287">Yes</span></span></p></td>
<td><p><span data-ttu-id="cdf04-288">Да</span><span class="sxs-lookup"><span data-stu-id="cdf04-288">Yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cdf04-289">Lync 2013 Basic</span><span class="sxs-lookup"><span data-stu-id="cdf04-289">Lync 2013 Basic</span></span></p></td>
<td><p><span data-ttu-id="cdf04-290">Да</span><span class="sxs-lookup"><span data-stu-id="cdf04-290">Yes</span></span></p></td>
<td><p><span data-ttu-id="cdf04-291">Да</span><span class="sxs-lookup"><span data-stu-id="cdf04-291">Yes</span></span></p></td>
<td><p><span data-ttu-id="cdf04-292">Да</span><span class="sxs-lookup"><span data-stu-id="cdf04-292">Yes</span></span></p></td>
<td><p><span data-ttu-id="cdf04-293">Да</span><span class="sxs-lookup"><span data-stu-id="cdf04-293">Yes</span></span></p></td>
<td><p><span data-ttu-id="cdf04-294">Да</span><span class="sxs-lookup"><span data-stu-id="cdf04-294">Yes</span></span></p></td>
<td><p><span data-ttu-id="cdf04-295">Да</span><span class="sxs-lookup"><span data-stu-id="cdf04-295">Yes</span></span></p></td>
<td><p><span data-ttu-id="cdf04-296">Да</span><span class="sxs-lookup"><span data-stu-id="cdf04-296">Yes</span></span></p></td>
<td><p><span data-ttu-id="cdf04-297">Да</span><span class="sxs-lookup"><span data-stu-id="cdf04-297">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cdf04-298">Lync Web App</span><span class="sxs-lookup"><span data-stu-id="cdf04-298">Lync Web App</span></span></p></td>
<td><p><span data-ttu-id="cdf04-299">Да</span><span class="sxs-lookup"><span data-stu-id="cdf04-299">Yes</span></span></p></td>
<td><p><span data-ttu-id="cdf04-300">Да</span><span class="sxs-lookup"><span data-stu-id="cdf04-300">Yes</span></span></p></td>
<td><p><span data-ttu-id="cdf04-301">Да</span><span class="sxs-lookup"><span data-stu-id="cdf04-301">Yes</span></span></p></td>
<td><p><span data-ttu-id="cdf04-302">Да</span><span class="sxs-lookup"><span data-stu-id="cdf04-302">Yes</span></span></p></td>
<td><p><span data-ttu-id="cdf04-303">Да2</span><span class="sxs-lookup"><span data-stu-id="cdf04-303">Yes2</span></span></p></td>
<td><p><span data-ttu-id="cdf04-304">Да</span><span class="sxs-lookup"><span data-stu-id="cdf04-304">Yes</span></span></p></td>
<td><p><span data-ttu-id="cdf04-305">Да</span><span class="sxs-lookup"><span data-stu-id="cdf04-305">Yes</span></span></p></td>
<td><p><span data-ttu-id="cdf04-306">Да</span><span class="sxs-lookup"><span data-stu-id="cdf04-306">Yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cdf04-307">Lync 2010</span><span class="sxs-lookup"><span data-stu-id="cdf04-307">Lync 2010</span></span></p></td>
<td><p><span data-ttu-id="cdf04-308">Да</span><span class="sxs-lookup"><span data-stu-id="cdf04-308">Yes</span></span></p></td>
<td><p><span data-ttu-id="cdf04-309">Да</span><span class="sxs-lookup"><span data-stu-id="cdf04-309">Yes</span></span></p></td>
<td><p><span data-ttu-id="cdf04-310">Да</span><span class="sxs-lookup"><span data-stu-id="cdf04-310">Yes</span></span></p></td>
<td><p><span data-ttu-id="cdf04-311">Да</span><span class="sxs-lookup"><span data-stu-id="cdf04-311">Yes</span></span></p></td>
<td><p><span data-ttu-id="cdf04-312">Yes3</span><span class="sxs-lookup"><span data-stu-id="cdf04-312">Yes3</span></span></p></td>
<td><p><span data-ttu-id="cdf04-313">Да</span><span class="sxs-lookup"><span data-stu-id="cdf04-313">Yes</span></span></p></td>
<td><p><span data-ttu-id="cdf04-314">Да</span><span class="sxs-lookup"><span data-stu-id="cdf04-314">Yes</span></span></p></td>
<td><p><span data-ttu-id="cdf04-315">Да</span><span class="sxs-lookup"><span data-stu-id="cdf04-315">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cdf04-316">Office Communicator 2007 R2 4</span><span class="sxs-lookup"><span data-stu-id="cdf04-316">Office Communicator 2007 R2 4</span></span></p></td>
<td><p><span data-ttu-id="cdf04-317">Да</span><span class="sxs-lookup"><span data-stu-id="cdf04-317">Yes</span></span></p></td>
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


<span data-ttu-id="cdf04-318">1 в Office Communicator 2007 R2 доступен только общий доступ к рабочему столу (а не к совместному использованию программ).</span><span class="sxs-lookup"><span data-stu-id="cdf04-318">1 In Office Communicator 2007 R2, only desktop sharing (and not program sharing) is available.</span></span>

<span data-ttu-id="cdf04-319">2 Lync Server 2013 использует обновленный механизм для отправки файлов PowerPoint.</span><span class="sxs-lookup"><span data-stu-id="cdf04-319">2 Lync Server 2013 uses an updated mechanism for uploading PowerPoint files.</span></span> <span data-ttu-id="cdf04-320">Пользователи Lync Web App, присоединяющиеся к собранию, изначально запланированному на Lync Server 2010, могут просматривать презентации PowerPoint и перемещаться по ним, но не могут отправлять файлы PowerPoint.</span><span class="sxs-lookup"><span data-stu-id="cdf04-320">Lync Web App users who join a meeting that was originally scheduled on Lync Server 2010 can view and navigate PowerPoint presentations, but cannot upload PowerPoint files.</span></span>

<span data-ttu-id="cdf04-321">3 Если собрание было запланировано на Lync Server 2013, а слайды PowerPoint были отправлены клиентом Lync 2013, пользователи Lync 2010 имеют доступ к слайдам только для просмотра.</span><span class="sxs-lookup"><span data-stu-id="cdf04-321">3 If the meeting was scheduled on Lync Server 2013 and PowerPoint slides were uploaded by a Lync 2013 client, Lync 2010 users have view-only access to the slides.</span></span> <span data-ttu-id="cdf04-322">И наоборот, если слайды PowerPoint были отправлены пользователем Lync 2010, пользователи Lync Server 2013 смогут просматривать и просматривать слайды, а если сервер Office Web Apps настроен, доступ к новым возможностям, таким как отображение, анимация, переходы слайдов и встроенное видео.</span><span class="sxs-lookup"><span data-stu-id="cdf04-322">Conversely, if the PowerPoint slides were uploaded by a Lync 2010 user, Lync Server 2013 users will be able to view and slides and, if Office Web Apps Server is configured, access new capabilities such as higher resolution display, animations, slide transitions, and embedded video.</span></span> <span data-ttu-id="cdf04-323">Дополнительную информацию можно узнать в статье [Настройка интеграции с сервером Office Web Apps и Lync Server 2013](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md).</span><span class="sxs-lookup"><span data-stu-id="cdf04-323">For more information, see [Configuring integration with Office Web Apps Server and Lync Server 2013](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md).</span></span>

<span data-ttu-id="cdf04-324">4The присутствия и функции обмена мгновенными сообщениями в Office Communicator 2007 R2 совместимы с Lync Server 2013, но функции конференц-связи не поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="cdf04-324">4The presence and IM features in Office Communicator 2007 R2 are compatible with Lync Server 2013, but conferencing features are not.</span></span> <span data-ttu-id="cdf04-325">Во время миграции с Office Communications Server 2007 R2 приложение Office Communicator 2007 R2 подходит для взаимодействия с присутствием и обменом мгновенными сообщениями, но пользователи должны использовать Lync Web App 2013, чтобы присоединиться к собраниям Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="cdf04-325">During migration from Office Communications Server 2007 R2, Office Communicator 2007 R2 is suitable for presence and IM interoperability, but users should use Lync Web App 2013 to join Lync Server 2013 meetings.</span></span>

</div>

</div>

<div>

## <a name="scheduling-add-in-support"></a><span data-ttu-id="cdf04-326">Планирование поддержки надстроек</span><span class="sxs-lookup"><span data-stu-id="cdf04-326">Scheduling Add-in Support</span></span>

<span data-ttu-id="cdf04-327">Серверная поддержка различных надстроек планирования согласуется с совместимостью версий сервера и клиентов.</span><span class="sxs-lookup"><span data-stu-id="cdf04-327">Server support for the various scheduling add-ins is consistent with server and client version compatibility.</span></span> <span data-ttu-id="cdf04-328">Как правило, в Lync Server 2013 поддерживаются следующие надстройки планирования.</span><span class="sxs-lookup"><span data-stu-id="cdf04-328">In general, the following scheduling add-ins are supported on Lync Server 2013.</span></span> <span data-ttu-id="cdf04-329">Однако предыдущие версии надстроек не предоставляют новые функции надстройки Lync 2013, такие как возможность отключения всех звуков и видео участников при вводе собрания.</span><span class="sxs-lookup"><span data-stu-id="cdf04-329">However, previous versions of add-ins do not provide new Lync 2013 add-in features, such as the option to mute all attendee audio and video upon meeting entry.</span></span>

  - <span data-ttu-id="cdf04-330">**Надстройка "собрание по сети" для Lync 2013**     Предоставляет те же функции, что и надстройка "собрание по сети" для Lync 2010, с добавлением элементов управления для участников собрания, которые позволяют организаторов по умолчанию планировать конференции, для которых по умолчанию отключен звук участника и видео.</span><span class="sxs-lookup"><span data-stu-id="cdf04-330">**Online Meeting Add-in for Lync 2013**   Provides the same features as the Online Meeting Add-in for Lync 2010, with the addition of attendee mute controls, which allow meeting organizers to schedule conferences that have attendee audio and video muted by default.</span></span> <span data-ttu-id="cdf04-331">Кроме того, администраторы могут настроить приглашения на собрание Организации, добавив настраиваемую эмблему, URL-адрес, юридический URL-адрес или текст нижнего колонтитула.</span><span class="sxs-lookup"><span data-stu-id="cdf04-331">Administrators can also customize the organization’s meeting invitations by adding a custom logo, a support URL, a legal disclaimer URL, or custom footer text.</span></span>

  - <span data-ttu-id="cdf04-332">**Надстройка "собрание по сети" для Lync 2010**     Предоставляет планирование для собраний Lync и удаляет возможность планирования конференций Office Live Meeting.</span><span class="sxs-lookup"><span data-stu-id="cdf04-332">**Online Meeting Add-in for Lync 2010**   Provides scheduling for Lync meetings and removes the capability to schedule Office Live Meeting conferences.</span></span>

  - <span data-ttu-id="cdf04-333">**Надстройка Конференц-**     связи Office Communicator 2007 R2 Предоставляет планирование для конференций Office Live Meeting и конференций Office Communicator 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="cdf04-333">**Office Communicator 2007 R2 Conferencing Add-in**   Provides scheduling for both Office Live Meeting conferences and Office Communicator 2007 R2 conferences.</span></span> 

<div>


> [!NOTE]  
> <span data-ttu-id="cdf04-334">В Lync Server 2013 невозможно планировать конференции Live Meeting.</span><span class="sxs-lookup"><span data-stu-id="cdf04-334">Live Meeting conferences cannot be scheduled on Lync Server 2013.</span></span>



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
<th><span data-ttu-id="cdf04-335">Планирование клиента</span><span class="sxs-lookup"><span data-stu-id="cdf04-335">Scheduling Client</span></span></th>
<th><span data-ttu-id="cdf04-336">Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cdf04-336">Lync Server 2013</span></span></th>
<th><span data-ttu-id="cdf04-337">Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="cdf04-337">Lync Server 2010</span></span></th>
<th><span data-ttu-id="cdf04-338">Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="cdf04-338">Office Communications Server 2007 R2</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="cdf04-339">Надстройка "собрание по сети" для Lync 2013 (может использоваться с Office 2013, Outlook 2010 и Outlook 2007)</span><span class="sxs-lookup"><span data-stu-id="cdf04-339">Online Meeting Add-in for Lync 2013 (can be used with Office 2013, Outlook 2010, and Outlook 2007)</span></span></p></td>
<td><p><span data-ttu-id="cdf04-340">Поддерживается</span><span class="sxs-lookup"><span data-stu-id="cdf04-340">Supported</span></span></p></td>
<td><p><span data-ttu-id="cdf04-341">Поддерживается (новые функции надстроек недоступны)</span><span class="sxs-lookup"><span data-stu-id="cdf04-341">Supported (new add-in features not available)</span></span></p></td>
<td><p><span data-ttu-id="cdf04-342">Не поддерживается</span><span class="sxs-lookup"><span data-stu-id="cdf04-342">Not Supported</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cdf04-343">Веб-планировщик Lync 2013</span><span class="sxs-lookup"><span data-stu-id="cdf04-343">Lync 2013 Web Scheduler</span></span></p></td>
<td><p><span data-ttu-id="cdf04-344">Поддерживается</span><span class="sxs-lookup"><span data-stu-id="cdf04-344">Supported</span></span></p></td>
<td><p><span data-ttu-id="cdf04-345">Не поддерживается</span><span class="sxs-lookup"><span data-stu-id="cdf04-345">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="cdf04-346">Не поддерживается</span><span class="sxs-lookup"><span data-stu-id="cdf04-346">Not Supported</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cdf04-347">Надстройка "собрание по сети" для Lync 2010</span><span class="sxs-lookup"><span data-stu-id="cdf04-347">Online Meeting Add-in for Lync 2010</span></span></p></td>
<td><p><span data-ttu-id="cdf04-348">Поддерживается</span><span class="sxs-lookup"><span data-stu-id="cdf04-348">Supported</span></span></p></td>
<td><p><span data-ttu-id="cdf04-349">Поддерживается</span><span class="sxs-lookup"><span data-stu-id="cdf04-349">Supported</span></span></p></td>
<td><p><span data-ttu-id="cdf04-350">Не поддерживается</span><span class="sxs-lookup"><span data-stu-id="cdf04-350">Not Supported</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cdf04-351">Надстройка конференц-связи Office Communicator 2007 R2</span><span class="sxs-lookup"><span data-stu-id="cdf04-351">Office Communicator 2007 R2 Conferencing Add-in</span></span></p></td>
<td><p><span data-ttu-id="cdf04-352">Не поддерживается</span><span class="sxs-lookup"><span data-stu-id="cdf04-352">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="cdf04-353">Поддерживается</span><span class="sxs-lookup"><span data-stu-id="cdf04-353">Supported</span></span></p></td>
<td><p><span data-ttu-id="cdf04-354">Поддерживается</span><span class="sxs-lookup"><span data-stu-id="cdf04-354">Supported</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="support-for-joining-meetings"></a><span data-ttu-id="cdf04-355">Поддержка присоединения к собраниям</span><span class="sxs-lookup"><span data-stu-id="cdf04-355">Support for Joining Meetings</span></span>

<span data-ttu-id="cdf04-356">Все клиенты, поддерживаемые Lync Server 2013, могут присоединяться к собраниям Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="cdf04-356">All of the clients that Lync Server 2013 supports are allowed to join Lync 2013 meetings.</span></span> <span data-ttu-id="cdf04-357">Так как Lync Web App является веб-компонентом сервера, то в тех случаях, когда Lync Web App используется для присоединения к собранию Lync Server 2013, всегда используется более новая версия Lync Web App.</span><span class="sxs-lookup"><span data-stu-id="cdf04-357">Because Lync Web App is a web component of the server, in cases where Lync Web App is used to join a Lync Server 2013 meeting, the newer version of Lync Web App is always used.</span></span>

<span data-ttu-id="cdf04-358">Пользователи Lync 2013 могут присоединяться к собраниям, размещенным на Lync 2010 и Office Communications Server 2007 R2, с возможностью масштабирования.</span><span class="sxs-lookup"><span data-stu-id="cdf04-358">Lync 2013 clients can join meetings hosted on Lync 2010 and Office Communications Server 2007 R2 with scaled-down functionality.</span></span> <span data-ttu-id="cdf04-359">Функции для собраний ограничены версией сервера, на котором размещается собрание.</span><span class="sxs-lookup"><span data-stu-id="cdf04-359">In-meeting features are limited by the version of the server on which the meeting is hosted.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="cdf04-360">См. также</span><span class="sxs-lookup"><span data-stu-id="cdf04-360">See Also</span></span>


[<span data-ttu-id="cdf04-361">Требования к приложению для Магазина Windows Lync для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cdf04-361">Lync Windows Store app requirements for Lync Server 2013</span></span>](lync-server-2013-lync-windows-store-app-requirements.md)  
[<span data-ttu-id="cdf04-362">Новые возможности конференц-связи в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cdf04-362">New conferencing features in Lync Server 2013</span></span>](lync-server-2013-new-conferencing-features.md)  
[<span data-ttu-id="cdf04-363">Новые возможности для клиентов в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cdf04-363">What's new for clients in Lync Server 2013</span></span>](lync-server-2013-what-s-new-for-clients.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

