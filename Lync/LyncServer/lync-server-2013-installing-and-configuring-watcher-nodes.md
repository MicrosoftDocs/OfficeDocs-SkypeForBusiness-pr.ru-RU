---
title: 'Lync Server 2013: Установка и настройка узлов-наблюдателей'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Installing and configuring watcher nodes
ms:assetid: 61f6deea-e3ef-4468-9be8-a65705815ebb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204943(v=OCS.15)
ms:contentKeyID: 48184284
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1765e9108619c5947eda02dd758aa764b0b407e6
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42197062"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="installing-and-configuring-watcher-nodes-in-lync-server-2013"></a><span data-ttu-id="b5333-102">Установка и настройка узлов-наблюдателей в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b5333-102">Installing and configuring watcher nodes in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b5333-103">_**Последнее изменение темы:** 2013-11-07_</span><span class="sxs-lookup"><span data-stu-id="b5333-103">_**Topic Last Modified:** 2013-11-07_</span></span>

<span data-ttu-id="b5333-104">*Узлы-наблюдатели* — это компьютеры, периодически выполняющие синтетические транзакции Lync Server.</span><span class="sxs-lookup"><span data-stu-id="b5333-104">*Watcher nodes* are computers that periodically run Lync Server synthetic transactions.</span></span> <span data-ttu-id="b5333-105">*Искусственные транзакции* — это командлеты Windows PowerShell, которые проверяют, что ключевые сценарии конечного пользователя (например, возможность входа в систему или возможность обмениваться мгновенными сообщениями) работают должным образом.</span><span class="sxs-lookup"><span data-stu-id="b5333-105">*Synthetic transactions* are Windows PowerShell cmdlets that verify that key end user scenarios—such as the ability to sign in to the system, or the ability to exchange instant messages—are working as expected.</span></span> <span data-ttu-id="b5333-106">Для Lync Server 2013 System Center Operations Manager может выполнять синтетические транзакции, показанные в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="b5333-106">For Lync Server 2013, System Center Operations Manager can run the synthetic transactions shown in the following table.</span></span> <span data-ttu-id="b5333-107">Здесь показаны три разных типа искусственных транзакций.</span><span class="sxs-lookup"><span data-stu-id="b5333-107">There are three different synthetic transaction types shown in the table:</span></span>

  - <span data-ttu-id="b5333-108">**По умолчанию**.</span><span class="sxs-lookup"><span data-stu-id="b5333-108">**Default**.</span></span> <span data-ttu-id="b5333-109">Это искусственные транзакции, которые узел-наблюдатель будет выполнять по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="b5333-109">These are the synthetic transactions that a watcher node will run by default.</span></span> <span data-ttu-id="b5333-110">При создании нового узла-наблюдателя имеется возможность указать, какие искусственные транзакции будет запускать этот узел.</span><span class="sxs-lookup"><span data-stu-id="b5333-110">When you create a new watcher node, you have the option of specifying which synthetic transactions that node will run.</span></span> <span data-ttu-id="b5333-111">(Это назначение параметра Tests, используемого командлетом **New-CsWatcherNodeConfiguration** .) Если вы не используете параметр Tests при создании узла-наблюдателя, он будет автоматически выполнять все синтетические транзакции по умолчанию и не будет выполнять искусственные транзакции, не связанные с по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="b5333-111">(That's the purpose of the Tests parameter used by the **New-CsWatcherNodeConfiguration** cmdlet.) If you do not use the Tests parameter when the watcher node is created, it will automatically run all the Default synthetic transactions and will not run any of the Non-default synthetic transactions.</span></span> <span data-ttu-id="b5333-112">То есть, к примеру, узел-наблюдатель будет настроен для запуска теста Test-CsAddressBookService, но не сможет запускать тест Test-CsExumConnectivity.</span><span class="sxs-lookup"><span data-stu-id="b5333-112">That means, for example, that the watcher node will be configured to run the Test-CsAddressBookService test, but will not be configured to run the Test-CsExumConnectivity test.</span></span>

  - <span data-ttu-id="b5333-113">**Не по умолчанию**.</span><span class="sxs-lookup"><span data-stu-id="b5333-113">**Non-default**.</span></span> <span data-ttu-id="b5333-114">Как следует из названия, не по умолчанию искусственные транзакции — это тесты, которые не запускаются по умолчанию узлами-наблюдателями.</span><span class="sxs-lookup"><span data-stu-id="b5333-114">As the name implies, Non-default synthetic transactions are tests that watcher nodes do not run by default.</span></span> <span data-ttu-id="b5333-115">Однако узел-наблюдатель можно включить для запуска любой из искусственных транзакций, не являющихся по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="b5333-115">However, the watcher node can be enabled to run any of the Non-default synthetic transactions.</span></span> <span data-ttu-id="b5333-116">Это можно сделать при создании узла-наблюдателя (с помощью командлета **New-CsWatcherNodeConfiguration** ) или в любое время после этого.</span><span class="sxs-lookup"><span data-stu-id="b5333-116">You can do this when you create the watcher node (by using the **New-CsWatcherNodeConfiguration** cmdlet), or at any time after that.</span></span> <span data-ttu-id="b5333-117">Многие из искусственных транзакций по умолчанию требуют дополнительных действий по настройке.</span><span class="sxs-lookup"><span data-stu-id="b5333-117">Many of the Non-default synthetic transactions require extra setup steps.</span></span> <span data-ttu-id="b5333-118">Дополнительные сведения см. [в статье специальные инструкции по настройке для искусственных транзакций в Lync Server 2013](lync-server-2013-special-setup-instructions-for-synthetic-transactions.md).</span><span class="sxs-lookup"><span data-stu-id="b5333-118">For details, see [Special setup instructions for synthetic transactions in Lync Server 2013](lync-server-2013-special-setup-instructions-for-synthetic-transactions.md).</span></span>

  - <span data-ttu-id="b5333-119">**Расширенный**.</span><span class="sxs-lookup"><span data-stu-id="b5333-119">**Extended**.</span></span> <span data-ttu-id="b5333-120">Расширенные тесты являются специальным типом искусственных транзакций не по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="b5333-120">Extended tests are a special type of Non-default synthetic transaction.</span></span> <span data-ttu-id="b5333-121">В отличие от других искусственных транзакций расширенные тесты могут выполняться несколько раз в течение каждого прохода.</span><span class="sxs-lookup"><span data-stu-id="b5333-121">Unlike other synthetic transactions, Extended tests can be run multiple times during each pass.</span></span> <span data-ttu-id="b5333-122">Это может оказаться полезным при проверке поведения, например при наличии в пуле нескольких маршрутов голосовой связи в ТСОП.</span><span class="sxs-lookup"><span data-stu-id="b5333-122">This can be useful when verifying behavior such as multiple public switched telephone network (PSTN) voice routes for a pool.</span></span> <span data-ttu-id="b5333-123">В этом случае настройка заключается в простом добавлении нескольких экземпляров расширенного теста в узел-наблюдатель.</span><span class="sxs-lookup"><span data-stu-id="b5333-123">This can be configured simply by adding multiple instances of an Extended test to a watcher node.</span></span>

<span data-ttu-id="b5333-124">Сведения о процессе добавления других искусственных транзакций на узел-наблюдатель можно найти [в разделе Управление узлами-наблюдателями в Lync Server 2013](lync-server-2013-managing-watcher-nodes.md).</span><span class="sxs-lookup"><span data-stu-id="b5333-124">For details about the process of adding other synthetic transactions to a watcher node, see [Managing watcher nodes in Lync Server 2013](lync-server-2013-managing-watcher-nodes.md).</span></span> <span data-ttu-id="b5333-125">Можно использовать командную консоль Lync Server для удаления искусственных транзакций из узла-наблюдателя.</span><span class="sxs-lookup"><span data-stu-id="b5333-125">You can use the Lync Server Management Shell to remove synthetic transactions from a watcher node.</span></span>

<span data-ttu-id="b5333-126">Узлам-наблюдателям доступны следующие искусственные транзакции.</span><span class="sxs-lookup"><span data-stu-id="b5333-126">The synthetic transactions available to watcher nodes include the following:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b5333-127">Имя командлета (название теста)</span><span class="sxs-lookup"><span data-stu-id="b5333-127">Cmdlet Name (Test Name)</span></span></th>
<th><span data-ttu-id="b5333-128">Описание</span><span class="sxs-lookup"><span data-stu-id="b5333-128">Description</span></span></th>
<th><span data-ttu-id="b5333-129">Тип искусственной транзакции</span><span class="sxs-lookup"><span data-stu-id="b5333-129">Synthetic Transaction Type</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b5333-130">Test-CsAddressBookService (ABS)</span><span class="sxs-lookup"><span data-stu-id="b5333-130">Test-CsAddressBookService (ABS)</span></span></p></td>
<td><p><span data-ttu-id="b5333-131">Проверяет, могут ли пользователи искать других пользователей, которых нет в их списках контактов.</span><span class="sxs-lookup"><span data-stu-id="b5333-131">Confirms that users are able to look up users that aren’t in their contact list.</span></span></p></td>
<td><p><span data-ttu-id="b5333-132">По умолчанию</span><span class="sxs-lookup"><span data-stu-id="b5333-132">Default</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b5333-133">Test-CsAddressBookWebQuery (ABWQ)</span><span class="sxs-lookup"><span data-stu-id="b5333-133">Test-CsAddressBookWebQuery (ABWQ)</span></span></p></td>
<td><p><span data-ttu-id="b5333-134">Проверяет, могут ли пользователи искать других пользователей, которых нет в их списках контактов, по протоколу HTTP.</span><span class="sxs-lookup"><span data-stu-id="b5333-134">Confirms that users are able to look up users that aren’t in their contact list via HTTP.</span></span></p></td>
<td><p><span data-ttu-id="b5333-135">По умолчанию</span><span class="sxs-lookup"><span data-stu-id="b5333-135">Default</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b5333-136">Test-CsIM (IM)</span><span class="sxs-lookup"><span data-stu-id="b5333-136">Test-CsIM (IM)</span></span></p></td>
<td><p><span data-ttu-id="b5333-137">Проверяет, могут ли пользователи обмениваться мгновенными сообщениями друг с другом.</span><span class="sxs-lookup"><span data-stu-id="b5333-137">Confirms that users are able to send peer-to-peer instant messages.</span></span></p></td>
<td><p><span data-ttu-id="b5333-138">По умолчанию</span><span class="sxs-lookup"><span data-stu-id="b5333-138">Default</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b5333-139">Test-CsP2PAV (P2PAV)</span><span class="sxs-lookup"><span data-stu-id="b5333-139">Test-CsP2PAV (P2PAV)</span></span></p></td>
<td><p><span data-ttu-id="b5333-140">Проверяет, могут ли пользователи совершать звонки другим пользователям (только сигнализация).</span><span class="sxs-lookup"><span data-stu-id="b5333-140">Confirms that users are able to place peer-to-peer audio calls (signaling only).</span></span></p></td>
<td><p><span data-ttu-id="b5333-141">По умолчанию</span><span class="sxs-lookup"><span data-stu-id="b5333-141">Default</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b5333-142">Test-CsPresence (Presence)</span><span class="sxs-lookup"><span data-stu-id="b5333-142">Test-CsPresence (Presence)</span></span></p></td>
<td><p><span data-ttu-id="b5333-143">Проверяет, могут ли пользователи просматривать сведения о присутствии других пользователей.</span><span class="sxs-lookup"><span data-stu-id="b5333-143">Confirms that users are able to view other users’ presence.</span></span></p></td>
<td><p><span data-ttu-id="b5333-144">По умолчанию</span><span class="sxs-lookup"><span data-stu-id="b5333-144">Default</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b5333-145">Test-CsRegistration (Registration)</span><span class="sxs-lookup"><span data-stu-id="b5333-145">Test-CsRegistration (Registration)</span></span></p></td>
<td><p><span data-ttu-id="b5333-146">Проверяет, могут ли пользователи входить в Lync.</span><span class="sxs-lookup"><span data-stu-id="b5333-146">Confirms that users are able sign in to Lync.</span></span></p></td>
<td><p><span data-ttu-id="b5333-147">По умолчанию</span><span class="sxs-lookup"><span data-stu-id="b5333-147">Default</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b5333-148">Test-CsAudioConferencingProvider (ACP)</span><span class="sxs-lookup"><span data-stu-id="b5333-148">Test-CsAudioConferencingProvider (ACP)</span></span></p></td>
<td><p><span data-ttu-id="b5333-149">Не используется с локальной версией Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b5333-149">Not used with the on-premises version of Lync Server 2013</span></span></p></td>
<td><p><span data-ttu-id="b5333-150">Долго</span><span class="sxs-lookup"><span data-stu-id="b5333-150">Extended</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b5333-151">Test-CsPstnPeerToPeerCall (ТСОП)</span><span class="sxs-lookup"><span data-stu-id="b5333-151">Test-CsPstnPeerToPeerCall (PSTN)</span></span></p></td>
<td><p><span data-ttu-id="b5333-152">Проверяет, могут ли пользователи совершать и принимать звонки от людей вне их предприятия (номера ТСОП).</span><span class="sxs-lookup"><span data-stu-id="b5333-152">Confirms that users are able to place and receive calls with people outside of the enterprise (PSTN numbers).</span></span></p></td>
<td><p><span data-ttu-id="b5333-153">Не по умолчанию, Расширенная</span><span class="sxs-lookup"><span data-stu-id="b5333-153">Non-default, Extended</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b5333-154">Test-Ксавконференце (Авконференце)</span><span class="sxs-lookup"><span data-stu-id="b5333-154">Test-CsAVConference (AvConference)</span></span></p></td>
<td><p><span data-ttu-id="b5333-155">Проверяет, могут ли пользователи создавать аудио- и видеоконференции и принимать в них участие.</span><span class="sxs-lookup"><span data-stu-id="b5333-155">Confirms that users are able to create and participate in an audio/video conference.</span></span></p></td>
<td><p><span data-ttu-id="b5333-156">По умолчанию</span><span class="sxs-lookup"><span data-stu-id="b5333-156">Default</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b5333-157">Test-CsAVEdgeConnectivity (Аведжеконнективити)</span><span class="sxs-lookup"><span data-stu-id="b5333-157">Test-CsAVEdgeConnectivity (AVEdgeConnectivity)</span></span></p></td>
<td><p><span data-ttu-id="b5333-158">Проверяет, что пограничные серверы звука и видео могут принимать подключения для выполнения одноранговых вызовов и вызовов конференц-связи.</span><span class="sxs-lookup"><span data-stu-id="b5333-158">Confirms that the A/V Edge servers are able to accept connections for peer-to-peer calls and conference calls.</span></span></p></td>
<td><p><span data-ttu-id="b5333-159">Не по умолчанию</span><span class="sxs-lookup"><span data-stu-id="b5333-159">Non-default</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b5333-160">Test-CsDataConference (конференция)</span><span class="sxs-lookup"><span data-stu-id="b5333-160">Test-CsDataConference (DataConference)</span></span></p></td>
<td><p><span data-ttu-id="b5333-161">Проверяет, могут ли пользователи участвовать в конференциях совместной работы с данными — собраниях по сети, включающих такие возможности, как доски и опросы.</span><span class="sxs-lookup"><span data-stu-id="b5333-161">Confirms that users can participate in a data collaboration conference, an online meeting that includes activities such as whiteboards and polls.</span></span></p></td>
<td><p><span data-ttu-id="b5333-162">Не по умолчанию</span><span class="sxs-lookup"><span data-stu-id="b5333-162">Non-default</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b5333-163">Test-CsExumConnectivity (ExumConnectivity)</span><span class="sxs-lookup"><span data-stu-id="b5333-163">Test-CsExumConnectivity (ExumConnectivity)</span></span></p></td>
<td><p><span data-ttu-id="b5333-164">Подтверждает, что пользователь может подключаться к единой системе обмена сообщениями Exchange (единой системы обмена сообщениями).</span><span class="sxs-lookup"><span data-stu-id="b5333-164">Confirms that a user can connect to Exchange Unified Messaging (UM).</span></span></p></td>
<td><p><span data-ttu-id="b5333-165">Не по умолчанию</span><span class="sxs-lookup"><span data-stu-id="b5333-165">Non-default</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b5333-166">Test-CsGroupIM (Граупим)</span><span class="sxs-lookup"><span data-stu-id="b5333-166">Test-CsGroupIM (GroupIM)</span></span></p></td>
<td><p><span data-ttu-id="b5333-167">Проверяет, могут ли пользователи отправлять мгновенные сообщения в рамках конференций и участвовать в текстовых беседах с тремя и более людьми.</span><span class="sxs-lookup"><span data-stu-id="b5333-167">Confirms that users are able to send instant messages in conferences and participate in instant message conversations with three or more people.</span></span></p></td>
<td><p><span data-ttu-id="b5333-168">По умолчанию</span><span class="sxs-lookup"><span data-stu-id="b5333-168">Default</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b5333-169">Test-CsGroupIM – Тестжоинлаунчер (Жоинлаунчер)</span><span class="sxs-lookup"><span data-stu-id="b5333-169">Test-CsGroupIM –TestJoinLauncher (JoinLauncher)</span></span></p></td>
<td><p><span data-ttu-id="b5333-170">Подтверждает, что пользователи могут создавать запланированные собрания по веб-ссылке и присоединяться к ним.</span><span class="sxs-lookup"><span data-stu-id="b5333-170">Confirms that users are able to create and join scheduled meetings via a web address link.</span></span></p></td>
<td><p><span data-ttu-id="b5333-171">Не по умолчанию</span><span class="sxs-lookup"><span data-stu-id="b5333-171">Non-default</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b5333-172">Test-CsMCXP2PIM (MCXP2PIM)</span><span class="sxs-lookup"><span data-stu-id="b5333-172">Test-CsMCXP2PIM (MCXP2PIM)</span></span></p></td>
<td><p><span data-ttu-id="b5333-173">Проверяет, могут ли пользователи мобильных устройств регистрироваться и отправлять мгновенные сообщения.</span><span class="sxs-lookup"><span data-stu-id="b5333-173">Confirms that mobile device users are able to register and send instant messages.</span></span></p></td>
<td><p><span data-ttu-id="b5333-174">Не по умолчанию</span><span class="sxs-lookup"><span data-stu-id="b5333-174">Non-default</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b5333-175">Test-CsPersistentChatMessage (Персистентчатмессаже)</span><span class="sxs-lookup"><span data-stu-id="b5333-175">Test-CsPersistentChatMessage (PersistentChatMessage)</span></span></p></td>
<td><p><span data-ttu-id="b5333-176">Подтверждает, что пользователи могут обмениваться сообщениями с помощью службы сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="b5333-176">Confirms that users can exchange messages by using the Persistent Chat service.</span></span></p></td>
<td><p><span data-ttu-id="b5333-177">Не по умолчанию</span><span class="sxs-lookup"><span data-stu-id="b5333-177">Non-default</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b5333-178">Test-CsUnifiedContactStore (Унифиедконтактсторе)</span><span class="sxs-lookup"><span data-stu-id="b5333-178">Test-CsUnifiedContactStore (UnifiedContactStore)</span></span></p></td>
<td><p><span data-ttu-id="b5333-179">Проверяет возможность доступа к контактам пользователя посредством единого хранилища контактов.</span><span class="sxs-lookup"><span data-stu-id="b5333-179">Confirms that a user's contacts can be accessed through the unified contact store.</span></span> <span data-ttu-id="b5333-180">Единое хранилище контактов предоставляет пользователям способ обслуживания одного набора контактов, доступ к которому можно получить с помощью Lync 2013, Outlook и/или Outlook Web Access.</span><span class="sxs-lookup"><span data-stu-id="b5333-180">The unified contact store provides a way for users to maintain a single set of contacts that can be accessed by using Lync 2013, Outlook, and/or Outlook Web Access.</span></span></p></td>
<td><p><span data-ttu-id="b5333-181">Не по умолчанию</span><span class="sxs-lookup"><span data-stu-id="b5333-181">Non-default</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b5333-182">Test-CsXmppIM (Ксмппим)</span><span class="sxs-lookup"><span data-stu-id="b5333-182">Test-CsXmppIM (XmppIM)</span></span></p></td>
<td><p><span data-ttu-id="b5333-183">Проверяет возможность отправки мгновенного сообщения через шлюз XMPP.</span><span class="sxs-lookup"><span data-stu-id="b5333-183">Confirms that an instant message can be sent across the XMPP (Extensible Messaging and Presence Protocol) gateway.</span></span></p></td>
<td><p><span data-ttu-id="b5333-184">Не по умолчанию</span><span class="sxs-lookup"><span data-stu-id="b5333-184">Non-default</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="b5333-185">Чтобы использовать System Center Operations Manager, не нужно устанавливать узлы-наблюдатели.</span><span class="sxs-lookup"><span data-stu-id="b5333-185">You do not need to install watcher nodes in order to use System Center Operations Manager.</span></span> <span data-ttu-id="b5333-186">Если вы не установите эти узлы, вы по-прежнему можете получать оповещения в режиме реального времени от компонентов Lync Server 2013 при возникновении проблемы.</span><span class="sxs-lookup"><span data-stu-id="b5333-186">If you do not install these nodes, you can still get real-time alerts from Lync Server 2013 components when an issue occurs.</span></span> <span data-ttu-id="b5333-187">(Пакет управления компонентом и пользовательским пакетом не использует узлы-наблюдатели.) Однако узлы-наблюдатели необходимы для мониторинга сквозных сценариев с помощью пакета управления Active Monitoring Management Pack.</span><span class="sxs-lookup"><span data-stu-id="b5333-187">(The Component and User Management Pack does not use watcher nodes.) However, watcher nodes are required if you want to monitor end-to-end scenarios by using the Active Monitoring Management pack.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="b5333-188">Администраторы могут также выполнять искусственные транзакции вручную, не используя и не устанавливая Operations Manager.</span><span class="sxs-lookup"><span data-stu-id="b5333-188">Administrators can also run synthetic transactions manually, without needing to use, or install, Operations Manager.</span></span> <span data-ttu-id="b5333-189">Подробнее о различных командлетах Test-CS можно узнать в <A href="https://docs.microsoft.com/powershell/module/skype/?view=skype-ps">индексе командлетов Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="b5333-189">For details about the various Test-Cs cmdlets, see the <A href="https://docs.microsoft.com/powershell/module/skype/?view=skype-ps">Lync Server 2013 cmdlets index</A>.</span></span>



</div>

<span data-ttu-id="b5333-190">В зависимости от размера развертывания искусственные транзакции могут использовать большой объем памяти компьютера и процессорного времени.</span><span class="sxs-lookup"><span data-stu-id="b5333-190">Depending on the size of your deployment, synthetic transactions may use a large amount of computer memory and processor time.</span></span> <span data-ttu-id="b5333-191">По этой причине мы рекомендуем использовать выделенный компьютер в качестве узла-наблюдателя.</span><span class="sxs-lookup"><span data-stu-id="b5333-191">For this reason, we recommend that you use a dedicated computer as a watcher node.</span></span> <span data-ttu-id="b5333-192">Например, не следует настраивать сервер переднего плана для работы в качестве узла-наблюдателя.</span><span class="sxs-lookup"><span data-stu-id="b5333-192">For example, you should not configure a Front End Server to act as a watcher node.</span></span> <span data-ttu-id="b5333-193">Узлы-наблюдатели должны соответствовать следующим спецификациям оборудования:</span><span class="sxs-lookup"><span data-stu-id="b5333-193">Watcher nodes should meet the following hardware specifications:</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="b5333-194">Невозможно совместное размещение устаревшего узла-наблюдателя Microsoft Lync Server 2010 на одном компьютере с узлом-наблюдателем Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b5333-194">A legacy Microsoft Lync Server 2010 watcher node cannot be collocated on the same machine with a Lync Server 2013 watcher node.</span></span> <span data-ttu-id="b5333-195">Это связано с тем, что основные системные файлы для Lync Server 2010 и Lync Server 2013 не могут быть установлены на одном компьютере.</span><span class="sxs-lookup"><span data-stu-id="b5333-195">This is because the core system files for Lync Server 2010 and Lync Server 2013 cannot be installed on the same computer.</span></span><BR><span data-ttu-id="b5333-196">Однако узлы-наблюдатели Lync Server 2013 могут одновременно отслеживать как Lync Server 2013, так и Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="b5333-196">However, Lync Server 2013 watcher nodes can simultaneously monitor both Lync Server 2013 and Lync Server 2010.</span></span> <span data-ttu-id="b5333-197">Искусственные транзакции по умолчанию поддерживаются для обеих версий продукта.</span><span class="sxs-lookup"><span data-stu-id="b5333-197">The Default synthetic transactions are supported on both product versions.</span></span>



</div>

<span data-ttu-id="b5333-198">Узлы-наблюдатели Lync Server 2013 могут быть развернуты внутри или за пределами предприятия, чтобы проверить следующее:</span><span class="sxs-lookup"><span data-stu-id="b5333-198">Lync Server 2013 watcher nodes may be deployed inside or outside of an enterprise to help verify:</span></span>

  - <span></span>  
    <span data-ttu-id="b5333-199">Подключение пользователей внутри предприятия к пулам</span><span class="sxs-lookup"><span data-stu-id="b5333-199">Connectivity to pools for users inside the enterprise.</span></span>

  - <span></span>  
    <span data-ttu-id="b5333-200">Подключение через сети периметра удаленных пользователей, которые работают за пределами предприятия.</span><span class="sxs-lookup"><span data-stu-id="b5333-200">Connectivity through perimeter networks for remote users who work outside the enterprise.</span></span>

  - <span></span>  
    <span data-ttu-id="b5333-201">Подключение к устройствам обеспечения связи в филиалах.</span><span class="sxs-lookup"><span data-stu-id="b5333-201">Connectivity to branch office appliances.</span></span>

  - <span></span>  
    <span data-ttu-id="b5333-202">Подключение к Lync Server 2010 внутри предприятия и через сети периметра.</span><span class="sxs-lookup"><span data-stu-id="b5333-202">Connectivity to Lync Server 2010 inside the enterprise and through perimeter networks.</span></span>

<span data-ttu-id="b5333-203">Различные методы проверки подлинности доступны как внутри, так и снаружи предприятия, что упрощает администрирования.</span><span class="sxs-lookup"><span data-stu-id="b5333-203">Different authentication options are available for inside and outside of the enterprise to help simplify administration.</span></span> <span data-ttu-id="b5333-204">Дополнительные сведения см. в разделе [Настройка узла-наблюдателя для запуска искусственных транзакций в Lync Server 2013](lync-server-2013-configuring-a-watcher-node-to-run-synthetic-transactions.md).</span><span class="sxs-lookup"><span data-stu-id="b5333-204">For details, see [Configuring a watcher node to run synthetic transactions in Lync Server 2013](lync-server-2013-configuring-a-watcher-node-to-run-synthetic-transactions.md).</span></span>

<span data-ttu-id="b5333-205">Чтобы настроить компьютер в качестве узла-наблюдателя, необходимо выполнить следующие действия после установки System Center Operations Manager и импортировать пакеты управления Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b5333-205">To configure a computer to act as a watcher node, you must complete the following steps after you have installed System Center Operations Manager and imported the Lync Server 2013 management packs.</span></span>

<span data-ttu-id="b5333-206">Перед установкой основных файлов Lync Server 2013 и файлов агента System Center необходимо убедиться, что компьютер узла-наблюдателя соответствует всем требованиям для установки Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b5333-206">Before you install the Lync Server 2013 core files and the System Center agent files, you should also make sure that the watcher node computer meets all the prerequisites for installing Lync Server 2013.</span></span> <span data-ttu-id="b5333-207">Кроме того, на этом компьютере должны быть установлены следующие компоненты:</span><span class="sxs-lookup"><span data-stu-id="b5333-207">In addition, the watcher node computer should also have the following items installed:</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b5333-208">Компонент оборудования</span><span class="sxs-lookup"><span data-stu-id="b5333-208">Hardware component</span></span></th>
<th><span data-ttu-id="b5333-209">Минимальное требование</span><span class="sxs-lookup"><span data-stu-id="b5333-209">Minimum requirement</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b5333-210">ЦП</span><span class="sxs-lookup"><span data-stu-id="b5333-210">CPU</span></span></p></td>
<td><p><span data-ttu-id="b5333-211">Один из следующих:</span><span class="sxs-lookup"><span data-stu-id="b5333-211">One of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="b5333-212">64 – разрядный процессор, четырехъядерный, 2,33 ГГц или выше</span><span class="sxs-lookup"><span data-stu-id="b5333-212">64-bit processor, quad-core, 2.33 GHz or higher</span></span></p></li>
<li><p><span data-ttu-id="b5333-213">64 бит, Двухъядерный процессор, 2,33 ГГц или выше</span><span class="sxs-lookup"><span data-stu-id="b5333-213">64-bit 2-way processor, dual-core, 2.33 GHz or higher</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b5333-214">Память</span><span class="sxs-lookup"><span data-stu-id="b5333-214">Memory</span></span></p></td>
<td><p><span data-ttu-id="b5333-215">8 ГБ</span><span class="sxs-lookup"><span data-stu-id="b5333-215">8 GB</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b5333-216">Сетевая операционная система</span><span class="sxs-lookup"><span data-stu-id="b5333-216">Network operating system</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="b5333-217">1 сетевой адаптер 1 Гбит/с</span><span class="sxs-lookup"><span data-stu-id="b5333-217">1 network adapter 1 Gbps</span></span></p></li>
<li><p><span data-ttu-id="b5333-218">Windows Server 2008 R2, Windows Server 2012 или</span><span class="sxs-lookup"><span data-stu-id="b5333-218">Windows Server 2008 R2, Windows Server 2012, or</span></span></p>
<p><span data-ttu-id="b5333-219">Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="b5333-219">Windows Server 2012 R2</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


  - <span data-ttu-id="b5333-220">полная версия .NET Framework 4.5;</span><span class="sxs-lookup"><span data-stu-id="b5333-220">The full version of .NET Framework 4.5.</span></span>

  - <span data-ttu-id="b5333-221">Windows Identity Foundation;</span><span class="sxs-lookup"><span data-stu-id="b5333-221">Windows Identity Foundation.</span></span>

  - <span data-ttu-id="b5333-222">Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="b5333-222">Windows PowerShell 3.0.</span></span>

<span data-ttu-id="b5333-223">Если все эти предварительные требования выполнены, вы можете настроить компьютер узла-наблюдателя следующим образом.</span><span class="sxs-lookup"><span data-stu-id="b5333-223">As soon as all these prerequisites have been met, you can configure the watcher node by:</span></span>

  - <span data-ttu-id="b5333-224">Установка основных файлов Lync Server 2013 на компьютере узла-наблюдателя.</span><span class="sxs-lookup"><span data-stu-id="b5333-224">Installing the Lync Server 2013 core files on the watcher node computer.</span></span>

  - <span data-ttu-id="b5333-225">Установка агента System Center Operations Manager на компьютере узла-наблюдателя.</span><span class="sxs-lookup"><span data-stu-id="b5333-225">Installing System Center Operations Manager agent on the watcher node computer.</span></span>

  - <span data-ttu-id="b5333-226">Запустите исполняемый файл Watchernode.msi.</span><span class="sxs-lookup"><span data-stu-id="b5333-226">Running the Watchernode.msi executable file.</span></span>

  - <span data-ttu-id="b5333-227">С помощью командлетов **CsWatcherNodeConfiguration** настройте тестовых пользователей, которые будут использоваться узлом-наблюдателем.</span><span class="sxs-lookup"><span data-stu-id="b5333-227">Using the **CsWatcherNodeConfiguration** cmdlets to configure test users to be employed by the watcher node.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

