---
title: 'Lync Server 2013: Установка и настройка узлов наблюдения'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Installing and configuring watcher nodes
ms:assetid: 61f6deea-e3ef-4468-9be8-a65705815ebb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204943(v=OCS.15)
ms:contentKeyID: 48184284
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 36d466cbffff1cf1e68eefe120215895e52e7c81
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34834005"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="installing-and-configuring-watcher-nodes-in-lync-server-2013"></a><span data-ttu-id="501a2-102">Установка и настройка узлов наблюдения в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="501a2-102">Installing and configuring watcher nodes in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="501a2-103">_**Тема последнего изменения:** 2013-11-07_</span><span class="sxs-lookup"><span data-stu-id="501a2-103">_**Topic Last Modified:** 2013-11-07_</span></span>

<span data-ttu-id="501a2-104">*Узлы наблюдения* — это компьютеры, периодически выполняющие синтетические транзакции Lync Server.</span><span class="sxs-lookup"><span data-stu-id="501a2-104">*Watcher nodes* are computers that periodically run Lync Server synthetic transactions.</span></span> <span data-ttu-id="501a2-105">*Синтетические транзакции* — это командлеты Windows PowerShell, которые определяют, что ключевые сценарии для конечных пользователей (например, возможность входа в систему или возможности обмена мгновенными сообщениями) работают должным образом.</span><span class="sxs-lookup"><span data-stu-id="501a2-105">*Synthetic transactions* are Windows PowerShell cmdlets that verify that key end user scenarios—such as the ability to sign in to the system, or the ability to exchange instant messages—are working as expected.</span></span> <span data-ttu-id="501a2-106">Для Lync Server 2013 System Center Operations Manager может выполнять синтетические транзакции, показанные в приведенной ниже таблице.</span><span class="sxs-lookup"><span data-stu-id="501a2-106">For Lync Server 2013, System Center Operations Manager can run the synthetic transactions shown in the following table.</span></span> <span data-ttu-id="501a2-107">В таблице ниже показаны три типа виртуальных операций.</span><span class="sxs-lookup"><span data-stu-id="501a2-107">There are three different synthetic transaction types shown in the table:</span></span>

  - <span data-ttu-id="501a2-108">**По умолчанию**.</span><span class="sxs-lookup"><span data-stu-id="501a2-108">**Default**.</span></span> <span data-ttu-id="501a2-109">Это искусственные транзакции, которые по умолчанию будут выполняться узлом-наблюдателем.</span><span class="sxs-lookup"><span data-stu-id="501a2-109">These are the synthetic transactions that a watcher node will run by default.</span></span> <span data-ttu-id="501a2-110">Когда вы создаете новый узел наблюдателя, у вас есть возможность указать, какие искусственные транзакции будет выполнять узел.</span><span class="sxs-lookup"><span data-stu-id="501a2-110">When you create a new watcher node, you have the option of specifying which synthetic transactions that node will run.</span></span> <span data-ttu-id="501a2-111">(Это цель параметра "тесты", используемая командлетом **New-ксватчернодеконфигуратион** .) Если вы не используете параметр "тесты" при создании узла контрольного значения, он будет автоматически запускать все используемые по умолчанию синтетические транзакции и не будет запускать синтетические транзакции, не используемые по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="501a2-111">(That's the purpose of the Tests parameter used by the **New-CsWatcherNodeConfiguration** cmdlet.) If you do not use the Tests parameter when the watcher node is created, it will automatically run all the Default synthetic transactions and will not run any of the Non-default synthetic transactions.</span></span> <span data-ttu-id="501a2-112">Это означает, например, что узел наблюдателя будет настроен для выполнения теста Test-Ксаддрессбуксервице, но не будет настроен для выполнения теста Test-Ксексумконнективити.</span><span class="sxs-lookup"><span data-stu-id="501a2-112">That means, for example, that the watcher node will be configured to run the Test-CsAddressBookService test, but will not be configured to run the Test-CsExumConnectivity test.</span></span>

  - <span data-ttu-id="501a2-113">**Не по умолчанию**.</span><span class="sxs-lookup"><span data-stu-id="501a2-113">**Non-default**.</span></span> <span data-ttu-id="501a2-114">Как и названия, нестандартные искусственные транзакции — это тесты, которые не выполняются по умолчанию узлами наблюдения.</span><span class="sxs-lookup"><span data-stu-id="501a2-114">As the name implies, Non-default synthetic transactions are tests that watcher nodes do not run by default.</span></span> <span data-ttu-id="501a2-115">Тем не менее, узел наблюдателя может быть активирован для выполнения любой из искусственных транзакций, не являющихся по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="501a2-115">However, the watcher node can be enabled to run any of the Non-default synthetic transactions.</span></span> <span data-ttu-id="501a2-116">Это можно сделать, когда вы создаете узел наблюдателя (с помощью командлета **New-ксватчернодеконфигуратион** ) или в любое время после этого.</span><span class="sxs-lookup"><span data-stu-id="501a2-116">You can do this when you create the watcher node (by using the **New-CsWatcherNodeConfiguration** cmdlet), or at any time after that.</span></span> <span data-ttu-id="501a2-117">Многие из искусственных транзакций, не используемых по умолчанию, требуют дополнительных шагов настройки.</span><span class="sxs-lookup"><span data-stu-id="501a2-117">Many of the Non-default synthetic transactions require extra setup steps.</span></span> <span data-ttu-id="501a2-118">Подробности можно найти [в разделе Специальные инструкции по настройке для виртуальных транзакций в Lync Server 2013](lync-server-2013-special-setup-instructions-for-synthetic-transactions.md).</span><span class="sxs-lookup"><span data-stu-id="501a2-118">For details, see [Special setup instructions for synthetic transactions in Lync Server 2013](lync-server-2013-special-setup-instructions-for-synthetic-transactions.md).</span></span>

  - <span data-ttu-id="501a2-119">**Extended**.</span><span class="sxs-lookup"><span data-stu-id="501a2-119">**Extended**.</span></span> <span data-ttu-id="501a2-120">Расширенные тесты — это особый тип искусственной транзакции, не используемой по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="501a2-120">Extended tests are a special type of Non-default synthetic transaction.</span></span> <span data-ttu-id="501a2-121">В отличие от других искусственных транзакций расширенные тесты могут выполняться несколько раз в течение каждого прохода.</span><span class="sxs-lookup"><span data-stu-id="501a2-121">Unlike other synthetic transactions, Extended tests can be run multiple times during each pass.</span></span> <span data-ttu-id="501a2-122">Это может быть полезно для проверки подлинности, например с несколькими коммутируемыми голосовой связью по коммутируемой телефонной сети (PSTN) для пула.</span><span class="sxs-lookup"><span data-stu-id="501a2-122">This can be useful when verifying behavior such as multiple public switched telephone network (PSTN) voice routes for a pool.</span></span> <span data-ttu-id="501a2-123">Это можно настроить, добавив несколько экземпляров расширенного теста на узел-наблюдатель.</span><span class="sxs-lookup"><span data-stu-id="501a2-123">This can be configured simply by adding multiple instances of an Extended test to a watcher node.</span></span>

<span data-ttu-id="501a2-124">Подробнее о том, как добавить другие синтетические транзакции в узел-наблюдатель, можно найти [в разделе Управление узлами-наблюдателями в Lync Server 2013](lync-server-2013-managing-watcher-nodes.md).</span><span class="sxs-lookup"><span data-stu-id="501a2-124">For details about the process of adding other synthetic transactions to a watcher node, see [Managing watcher nodes in Lync Server 2013](lync-server-2013-managing-watcher-nodes.md).</span></span> <span data-ttu-id="501a2-125">Вы можете использовать командную консоль Lync Server для удаления искусственных транзакций из узла-наблюдателя.</span><span class="sxs-lookup"><span data-stu-id="501a2-125">You can use the Lync Server Management Shell to remove synthetic transactions from a watcher node.</span></span>

<span data-ttu-id="501a2-126">Узлам-наблюдателям доступны следующие искусственные транзакции.</span><span class="sxs-lookup"><span data-stu-id="501a2-126">The synthetic transactions available to watcher nodes include the following:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="501a2-127">Имя командлета (название теста)</span><span class="sxs-lookup"><span data-stu-id="501a2-127">Cmdlet Name (Test Name)</span></span></th>
<th><span data-ttu-id="501a2-128">Описание</span><span class="sxs-lookup"><span data-stu-id="501a2-128">Description</span></span></th>
<th><span data-ttu-id="501a2-129">Тип искусственной транзакции</span><span class="sxs-lookup"><span data-stu-id="501a2-129">Synthetic Transaction Type</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="501a2-130">Test-CsAddressBookService (ABS)</span><span class="sxs-lookup"><span data-stu-id="501a2-130">Test-CsAddressBookService (ABS)</span></span></p></td>
<td><p><span data-ttu-id="501a2-131">Подтверждает, что пользователи смогут искать пользователей, которых нет в списке контактов.</span><span class="sxs-lookup"><span data-stu-id="501a2-131">Confirms that users are able to look up users that aren’t in their contact list.</span></span></p></td>
<td><p><span data-ttu-id="501a2-132">По умолчанию</span><span class="sxs-lookup"><span data-stu-id="501a2-132">Default</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="501a2-133">Test-CsAddressBookWebQuery (ABWQ)</span><span class="sxs-lookup"><span data-stu-id="501a2-133">Test-CsAddressBookWebQuery (ABWQ)</span></span></p></td>
<td><p><span data-ttu-id="501a2-134">Подтверждает, что пользователи могут искать пользователей, которых нет в списке контактов по протоколу HTTP.</span><span class="sxs-lookup"><span data-stu-id="501a2-134">Confirms that users are able to look up users that aren’t in their contact list via HTTP.</span></span></p></td>
<td><p><span data-ttu-id="501a2-135">По умолчанию</span><span class="sxs-lookup"><span data-stu-id="501a2-135">Default</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="501a2-136">Test-Ксим (мгновенные сообщения)</span><span class="sxs-lookup"><span data-stu-id="501a2-136">Test-CsIM (IM)</span></span></p></td>
<td><p><span data-ttu-id="501a2-137">Проверяет, могут ли пользователи обмениваться мгновенными сообщениями друг с другом.</span><span class="sxs-lookup"><span data-stu-id="501a2-137">Confirms that users are able to send peer-to-peer instant messages.</span></span></p></td>
<td><p><span data-ttu-id="501a2-138">По умолчанию</span><span class="sxs-lookup"><span data-stu-id="501a2-138">Default</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="501a2-139">Test-CsP2PAV (P2PAV)</span><span class="sxs-lookup"><span data-stu-id="501a2-139">Test-CsP2PAV (P2PAV)</span></span></p></td>
<td><p><span data-ttu-id="501a2-140">Проверяет, могут ли пользователи совершать звонки другим пользователям (только сигнализация).</span><span class="sxs-lookup"><span data-stu-id="501a2-140">Confirms that users are able to place peer-to-peer audio calls (signaling only).</span></span></p></td>
<td><p><span data-ttu-id="501a2-141">По умолчанию</span><span class="sxs-lookup"><span data-stu-id="501a2-141">Default</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="501a2-142">Test-CsPresence (Присутствие)</span><span class="sxs-lookup"><span data-stu-id="501a2-142">Test-CsPresence (Presence)</span></span></p></td>
<td><p><span data-ttu-id="501a2-143">Проверяет, могут ли пользователи просматривать сведения о присутствии других пользователей.</span><span class="sxs-lookup"><span data-stu-id="501a2-143">Confirms that users are able to view other users’ presence.</span></span></p></td>
<td><p><span data-ttu-id="501a2-144">По умолчанию</span><span class="sxs-lookup"><span data-stu-id="501a2-144">Default</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="501a2-145">Test-CsRegistration (Регистрация)</span><span class="sxs-lookup"><span data-stu-id="501a2-145">Test-CsRegistration (Registration)</span></span></p></td>
<td><p><span data-ttu-id="501a2-146">Подтверждает, что пользователи смогут войти в Lync.</span><span class="sxs-lookup"><span data-stu-id="501a2-146">Confirms that users are able sign in to Lync.</span></span></p></td>
<td><p><span data-ttu-id="501a2-147">По умолчанию</span><span class="sxs-lookup"><span data-stu-id="501a2-147">Default</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="501a2-148">Test-КсаудиоконференЦингпровидер (ACP)</span><span class="sxs-lookup"><span data-stu-id="501a2-148">Test-CsAudioConferencingProvider (ACP)</span></span></p></td>
<td><p><span data-ttu-id="501a2-149">Не используется в локальной версии Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="501a2-149">Not used with the on-premises version of Lync Server 2013</span></span></p></td>
<td><p><span data-ttu-id="501a2-150">Расширенная.</span><span class="sxs-lookup"><span data-stu-id="501a2-150">Extended</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="501a2-151">Test-CsPstnPeerToPeerCall (ТСОП)</span><span class="sxs-lookup"><span data-stu-id="501a2-151">Test-CsPstnPeerToPeerCall (PSTN)</span></span></p></td>
<td><p><span data-ttu-id="501a2-152">Проверяет, могут ли пользователи совершать и принимать звонки от людей вне их предприятия (номера ТСОП).</span><span class="sxs-lookup"><span data-stu-id="501a2-152">Confirms that users are able to place and receive calls with people outside of the enterprise (PSTN numbers).</span></span></p></td>
<td><p><span data-ttu-id="501a2-153">Не по умолчанию, расширенные</span><span class="sxs-lookup"><span data-stu-id="501a2-153">Non-default, Extended</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="501a2-154">Test-CsAVConference (AvConference)</span><span class="sxs-lookup"><span data-stu-id="501a2-154">Test-CsAVConference (AvConference)</span></span></p></td>
<td><p><span data-ttu-id="501a2-155">Проверяет, могут ли пользователи создавать аудио- и видеоконференции и принимать в них участие.</span><span class="sxs-lookup"><span data-stu-id="501a2-155">Confirms that users are able to create and participate in an audio/video conference.</span></span></p></td>
<td><p><span data-ttu-id="501a2-156">По умолчанию</span><span class="sxs-lookup"><span data-stu-id="501a2-156">Default</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="501a2-157">Test-CsAVEdgeConnectivity (AVEdgeConnectivity)</span><span class="sxs-lookup"><span data-stu-id="501a2-157">Test-CsAVEdgeConnectivity (AVEdgeConnectivity)</span></span></p></td>
<td><p><span data-ttu-id="501a2-158">Подтверждает, что пограничные серверы A/V смогут получать соединения для одноранговых вызовов и конференций.</span><span class="sxs-lookup"><span data-stu-id="501a2-158">Confirms that the A/V Edge servers are able to accept connections for peer-to-peer calls and conference calls.</span></span></p></td>
<td><p><span data-ttu-id="501a2-159">Не по умолчанию</span><span class="sxs-lookup"><span data-stu-id="501a2-159">Non-default</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="501a2-160">Test-CsDataConference (DataConference)</span><span class="sxs-lookup"><span data-stu-id="501a2-160">Test-CsDataConference (DataConference)</span></span></p></td>
<td><p><span data-ttu-id="501a2-161">Подтверждает, что пользователи могут принимать участие в конференции по совместной работе с данными, собрание по сети, которое включает такие действия, как доски и опросы.</span><span class="sxs-lookup"><span data-stu-id="501a2-161">Confirms that users can participate in a data collaboration conference, an online meeting that includes activities such as whiteboards and polls.</span></span></p></td>
<td><p><span data-ttu-id="501a2-162">Не по умолчанию</span><span class="sxs-lookup"><span data-stu-id="501a2-162">Non-default</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="501a2-163">Test-CsExumConnectivity (ExumConnectivity)</span><span class="sxs-lookup"><span data-stu-id="501a2-163">Test-CsExumConnectivity (ExumConnectivity)</span></span></p></td>
<td><p><span data-ttu-id="501a2-164">Подтверждает, что пользователь может подключаться к единой системе обмена сообщениями Exchange (UM).</span><span class="sxs-lookup"><span data-stu-id="501a2-164">Confirms that a user can connect to Exchange Unified Messaging (UM).</span></span></p></td>
<td><p><span data-ttu-id="501a2-165">Не по умолчанию</span><span class="sxs-lookup"><span data-stu-id="501a2-165">Non-default</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="501a2-166">Test-Ксграупим (Граупим)</span><span class="sxs-lookup"><span data-stu-id="501a2-166">Test-CsGroupIM (GroupIM)</span></span></p></td>
<td><p><span data-ttu-id="501a2-167">Проверяет, могут ли пользователи отправлять мгновенные сообщения в рамках конференций и участвовать в текстовых беседах с тремя и более людьми.</span><span class="sxs-lookup"><span data-stu-id="501a2-167">Confirms that users are able to send instant messages in conferences and participate in instant message conversations with three or more people.</span></span></p></td>
<td><p><span data-ttu-id="501a2-168">По умолчанию</span><span class="sxs-lookup"><span data-stu-id="501a2-168">Default</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="501a2-169">Test-CsGroupIM –TestJoinLauncher (JoinLauncher)</span><span class="sxs-lookup"><span data-stu-id="501a2-169">Test-CsGroupIM –TestJoinLauncher (JoinLauncher)</span></span></p></td>
<td><p><span data-ttu-id="501a2-170">Подтверждает, что пользователи смогут создавать и присоединяться к запланированным собраниям с помощью ссылки на веб-адрес.</span><span class="sxs-lookup"><span data-stu-id="501a2-170">Confirms that users are able to create and join scheduled meetings via a web address link.</span></span></p></td>
<td><p><span data-ttu-id="501a2-171">Не по умолчанию</span><span class="sxs-lookup"><span data-stu-id="501a2-171">Non-default</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="501a2-172">Test-CsMCXP2PIM (MCXP2PIM)</span><span class="sxs-lookup"><span data-stu-id="501a2-172">Test-CsMCXP2PIM (MCXP2PIM)</span></span></p></td>
<td><p><span data-ttu-id="501a2-173">Проверяет, могут ли пользователи мобильных устройств регистрироваться и отправлять мгновенные сообщения.</span><span class="sxs-lookup"><span data-stu-id="501a2-173">Confirms that mobile device users are able to register and send instant messages.</span></span></p></td>
<td><p><span data-ttu-id="501a2-174">Не по умолчанию</span><span class="sxs-lookup"><span data-stu-id="501a2-174">Non-default</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="501a2-175">Test-CsPersistentChatMessage (PersistentChatMessage)</span><span class="sxs-lookup"><span data-stu-id="501a2-175">Test-CsPersistentChatMessage (PersistentChatMessage)</span></span></p></td>
<td><p><span data-ttu-id="501a2-176">Проверяет, могут ли пользователи обмениваться сообщениями с помощью службы сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="501a2-176">Confirms that users can exchange messages by using the Persistent Chat service.</span></span></p></td>
<td><p><span data-ttu-id="501a2-177">Не по умолчанию</span><span class="sxs-lookup"><span data-stu-id="501a2-177">Non-default</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="501a2-178">Test-CsUnifiedContactStore (UnifiedContactStore)</span><span class="sxs-lookup"><span data-stu-id="501a2-178">Test-CsUnifiedContactStore (UnifiedContactStore)</span></span></p></td>
<td><p><span data-ttu-id="501a2-179">Проверяет возможность доступа к контактам пользователя посредством единого хранилища контактов.</span><span class="sxs-lookup"><span data-stu-id="501a2-179">Confirms that a user's contacts can be accessed through the unified contact store.</span></span> <span data-ttu-id="501a2-180">Единое хранилище контактов позволяет пользователям поддерживать один набор контактов, доступ к которому можно получить с помощью Lync 2013, Outlook и Outlook Web Access.</span><span class="sxs-lookup"><span data-stu-id="501a2-180">The unified contact store provides a way for users to maintain a single set of contacts that can be accessed by using Lync 2013, Outlook, and/or Outlook Web Access.</span></span></p></td>
<td><p><span data-ttu-id="501a2-181">Не по умолчанию</span><span class="sxs-lookup"><span data-stu-id="501a2-181">Non-default</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="501a2-182">Test-CsXmppIM (XmppIM)</span><span class="sxs-lookup"><span data-stu-id="501a2-182">Test-CsXmppIM (XmppIM)</span></span></p></td>
<td><p><span data-ttu-id="501a2-183">Подтверждение того, что мгновенное сообщение может быть отправлено через шлюз КСМПП (Extensible Messaging Protocol и протокол присутствия).</span><span class="sxs-lookup"><span data-stu-id="501a2-183">Confirms that an instant message can be sent across the XMPP (Extensible Messaging and Presence Protocol) gateway.</span></span></p></td>
<td><p><span data-ttu-id="501a2-184">Не по умолчанию</span><span class="sxs-lookup"><span data-stu-id="501a2-184">Non-default</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="501a2-185">Для использования System Center Operations Manager вам не нужно устанавливать узлы наблюдателей.</span><span class="sxs-lookup"><span data-stu-id="501a2-185">You do not need to install watcher nodes in order to use System Center Operations Manager.</span></span> <span data-ttu-id="501a2-186">Если вы не установили эти узлы, вы по-прежнему можете получать оповещения в реальном времени от компонентов Lync Server 2013 при возникновении проблем.</span><span class="sxs-lookup"><span data-stu-id="501a2-186">If you do not install these nodes, you can still get real-time alerts from Lync Server 2013 components when an issue occurs.</span></span> <span data-ttu-id="501a2-187">(Пакет управления компонентом и пользовательским интерфейсом не использует узлы-наблюдатели). Однако узлы-наблюдатели необходимы для мониторинга сквозных сценариев с помощью активного пакета управления мониторингом.</span><span class="sxs-lookup"><span data-stu-id="501a2-187">(The Component and User Management Pack does not use watcher nodes.) However, watcher nodes are required if you want to monitor end-to-end scenarios by using the Active Monitoring Management pack.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="501a2-188">Кроме того, администраторы могут выполнять синтетические транзакции вручную, не требуя использования или установки Operations Manager.</span><span class="sxs-lookup"><span data-stu-id="501a2-188">Administrators can also run synthetic transactions manually, without needing to use, or install, Operations Manager.</span></span> <span data-ttu-id="501a2-189">Подробные сведения о различных командлетах тестирования-CS можно найти в <A href="https://docs.microsoft.com/powershell/module/skype/?view=skype-ps">индексе командлетов Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="501a2-189">For details about the various Test-Cs cmdlets, see the <A href="https://docs.microsoft.com/powershell/module/skype/?view=skype-ps">Lync Server 2013 cmdlets index</A>.</span></span>



</div>

<span data-ttu-id="501a2-190">В зависимости от размера вашего развертывания синтетические транзакции могут использовать большой объем памяти компьютера и процессорного времени.</span><span class="sxs-lookup"><span data-stu-id="501a2-190">Depending on the size of your deployment, synthetic transactions may use a large amount of computer memory and processor time.</span></span> <span data-ttu-id="501a2-191">По этой причине мы рекомендуем использовать выделенный компьютер в качестве узла-наблюдателя.</span><span class="sxs-lookup"><span data-stu-id="501a2-191">For this reason, we recommend that you use a dedicated computer as a watcher node.</span></span> <span data-ttu-id="501a2-192">Например, не следует настраивать сервер переднего плана так, чтобы он действовал как узел-наблюдатель.</span><span class="sxs-lookup"><span data-stu-id="501a2-192">For example, you should not configure a Front End Server to act as a watcher node.</span></span> <span data-ttu-id="501a2-193">Узлы наблюдателей должны соответствовать следующим спецификациям оборудования:</span><span class="sxs-lookup"><span data-stu-id="501a2-193">Watcher nodes should meet the following hardware specifications:</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="501a2-194">На том же компьютере, на котором не разразделена версия устаревшего сервера Microsoft Lync Server 2010, с узлом-наблюдателем Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="501a2-194">A legacy Microsoft Lync Server 2010 watcher node cannot be collocated on the same machine with a Lync Server 2013 watcher node.</span></span> <span data-ttu-id="501a2-195">Это связано с тем, что основные системные файлы Lync Server 2010 и Lync Server 2013 нельзя установить на один и тот же компьютер.</span><span class="sxs-lookup"><span data-stu-id="501a2-195">This is because the core system files for Lync Server 2010 and Lync Server 2013 cannot be installed on the same computer.</span></span><BR><span data-ttu-id="501a2-196">Однако узлы Lync Server 2013 могут одновременно отслеживать как Lync Server 2013, так и Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="501a2-196">However, Lync Server 2013 watcher nodes can simultaneously monitor both Lync Server 2013 and Lync Server 2010.</span></span> <span data-ttu-id="501a2-197">Синтетические транзакции по умолчанию поддерживаются для обеих версий продукта.</span><span class="sxs-lookup"><span data-stu-id="501a2-197">The Default synthetic transactions are supported on both product versions.</span></span>



</div>

<span data-ttu-id="501a2-198">Узлы Lync Server 2013 могут развертываться внутри или вне Организации, чтобы убедиться в том, что:</span><span class="sxs-lookup"><span data-stu-id="501a2-198">Lync Server 2013 watcher nodes may be deployed inside or outside of an enterprise to help verify:</span></span>

  - <span></span>  
    <span data-ttu-id="501a2-199">Подключение пользователей внутри предприятия к пулам</span><span class="sxs-lookup"><span data-stu-id="501a2-199">Connectivity to pools for users inside the enterprise.</span></span>

  - <span></span>  
    <span data-ttu-id="501a2-200">Связь через сети периметра для удаленных пользователей, которые работают за пределами Организации.</span><span class="sxs-lookup"><span data-stu-id="501a2-200">Connectivity through perimeter networks for remote users who work outside the enterprise.</span></span>

  - <span></span>  
    <span data-ttu-id="501a2-201">Подключение к устройствам обеспечения связи в филиалах.</span><span class="sxs-lookup"><span data-stu-id="501a2-201">Connectivity to branch office appliances.</span></span>

  - <span></span>  
    <span data-ttu-id="501a2-202">Связь с Lync Server 2010 внутри предприятия и через сети периметра.</span><span class="sxs-lookup"><span data-stu-id="501a2-202">Connectivity to Lync Server 2010 inside the enterprise and through perimeter networks.</span></span>

<span data-ttu-id="501a2-203">Для упрощения администрирования доступны различные варианты проверки подлинности в рамках предприятия и за ее пределами.</span><span class="sxs-lookup"><span data-stu-id="501a2-203">Different authentication options are available for inside and outside of the enterprise to help simplify administration.</span></span> <span data-ttu-id="501a2-204">Подробности можно найти [в разделе Настройка узла-наблюдателя для запуска виртуальных транзакций в Lync Server 2013](lync-server-2013-configuring-a-watcher-node-to-run-synthetic-transactions.md).</span><span class="sxs-lookup"><span data-stu-id="501a2-204">For details, see [Configuring a watcher node to run synthetic transactions in Lync Server 2013](lync-server-2013-configuring-a-watcher-node-to-run-synthetic-transactions.md).</span></span>

<span data-ttu-id="501a2-205">Чтобы настроить компьютер для работы в качестве узла-наблюдателя, необходимо выполнить указанные ниже действия после установки System Center Operations Manager и импорта пакетов управления Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="501a2-205">To configure a computer to act as a watcher node, you must complete the following steps after you have installed System Center Operations Manager and imported the Lync Server 2013 management packs.</span></span>

<span data-ttu-id="501a2-206">Перед установкой основных файлов Lync Server 2013 и файлов агента System Center необходимо также убедиться, что компьютер-узел-наблюдатель отвечает всем требованиям, необходимым для установки Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="501a2-206">Before you install the Lync Server 2013 core files and the System Center agent files, you should also make sure that the watcher node computer meets all the prerequisites for installing Lync Server 2013.</span></span> <span data-ttu-id="501a2-207">Кроме того, на компьютере с узлом-наблюдателем также должны быть установлены следующие компоненты:</span><span class="sxs-lookup"><span data-stu-id="501a2-207">In addition, the watcher node computer should also have the following items installed:</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="501a2-208">Аппаратный компонент</span><span class="sxs-lookup"><span data-stu-id="501a2-208">Hardware component</span></span></th>
<th><span data-ttu-id="501a2-209">Минимальное требование</span><span class="sxs-lookup"><span data-stu-id="501a2-209">Minimum requirement</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="501a2-210">ЦП</span><span class="sxs-lookup"><span data-stu-id="501a2-210">CPU</span></span></p></td>
<td><p><span data-ttu-id="501a2-211">Один из следующих:</span><span class="sxs-lookup"><span data-stu-id="501a2-211">One of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="501a2-212">Четырехъядерный 64-разрядный процессор с частотой 2,33 ГГц или выше</span><span class="sxs-lookup"><span data-stu-id="501a2-212">64-bit processor, quad-core, 2.33 GHz or higher</span></span></p></li>
<li><p><span data-ttu-id="501a2-213">64-разрядный процессор с 2-канальным кэшем, двухъядерный, 2,33 ГГц и выше</span><span class="sxs-lookup"><span data-stu-id="501a2-213">64-bit 2-way processor, dual-core, 2.33 GHz or higher</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="501a2-214">Память</span><span class="sxs-lookup"><span data-stu-id="501a2-214">Memory</span></span></p></td>
<td><p><span data-ttu-id="501a2-215">8 ГБ</span><span class="sxs-lookup"><span data-stu-id="501a2-215">8 GB</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="501a2-216">Сетевая операционная система</span><span class="sxs-lookup"><span data-stu-id="501a2-216">Network operating system</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="501a2-217">1 сетевой адаптер 1 Гбит/с</span><span class="sxs-lookup"><span data-stu-id="501a2-217">1 network adapter 1 Gbps</span></span></p></li>
<li><p><span data-ttu-id="501a2-218">Windows Server 2008 R2, Windows Server 2012 или</span><span class="sxs-lookup"><span data-stu-id="501a2-218">Windows Server 2008 R2, Windows Server 2012, or</span></span></p>
<p><span data-ttu-id="501a2-219">Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="501a2-219">Windows Server 2012 R2</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


  - <span data-ttu-id="501a2-220">Полная версия платформы .NET Framework 4,5.</span><span class="sxs-lookup"><span data-stu-id="501a2-220">The full version of .NET Framework 4.5.</span></span>

  - <span data-ttu-id="501a2-221">Windows Identity Foundation.</span><span class="sxs-lookup"><span data-stu-id="501a2-221">Windows Identity Foundation.</span></span>

  - <span data-ttu-id="501a2-222">Windows PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="501a2-222">Windows PowerShell 3.0.</span></span>

<span data-ttu-id="501a2-223">После того как все необходимые условия будут выполнены, вы можете настроить узел наблюдателя, выполнив указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="501a2-223">As soon as all these prerequisites have been met, you can configure the watcher node by:</span></span>

  - <span data-ttu-id="501a2-224">Установка основных файлов Lync Server 2013 на компьютере с узлом-наблюдателем.</span><span class="sxs-lookup"><span data-stu-id="501a2-224">Installing the Lync Server 2013 core files on the watcher node computer.</span></span>

  - <span data-ttu-id="501a2-225">Установка агента System Center Operations Manager на компьютере с узлом-наблюдателем.</span><span class="sxs-lookup"><span data-stu-id="501a2-225">Installing System Center Operations Manager agent on the watcher node computer.</span></span>

  - <span data-ttu-id="501a2-226">Запуск исполняемого файла Ватчерноде. msi.</span><span class="sxs-lookup"><span data-stu-id="501a2-226">Running the Watchernode.msi executable file.</span></span>

  - <span data-ttu-id="501a2-227">Использование командлетов **ксватчернодеконфигуратион** для настройки тестовых пользователей для использования узлом-наблюдателем.</span><span class="sxs-lookup"><span data-stu-id="501a2-227">Using the **CsWatcherNodeConfiguration** cmdlets to configure test users to be employed by the watcher node.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

