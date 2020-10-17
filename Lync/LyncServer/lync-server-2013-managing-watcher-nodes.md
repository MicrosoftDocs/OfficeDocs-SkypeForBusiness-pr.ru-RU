---
title: 'Lync Server 2013: Управление узлами-наблюдателями'
description: 'Lync Server 2013: Управление узлами-наблюдателями.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Managing watcher nodes
ms:assetid: 66deaf49-a71f-4a6e-ada0-ea8b688ee921
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688078(v=OCS.15)
ms:contentKeyID: 49733674
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1795b09bbca73d8157cf796ceeaaeafb9cc2ebc5
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48556615"
---
# <a name="managing-watcher-nodes-in-lync-server-2013"></a><span data-ttu-id="7d117-103">Управление узлами-наблюдателями в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7d117-103">Managing watcher nodes in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7d117-104">_**Последнее изменение темы:** 2012-10-20_</span><span class="sxs-lookup"><span data-stu-id="7d117-104">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="7d117-105">В дополнение к изменению искусственных транзакций, выполняемых на узле-наблюдателе, администраторы могут также использовать командлет **Set-CsWatcherNodeConfiguration** для выполнения двух других важных задач: включение/отключение узла-наблюдателя и настройка узла-наблюдателя для использования внутренних URL-адресов или внешних URL-адресов при проведении тестирования.</span><span class="sxs-lookup"><span data-stu-id="7d117-105">In addition to modifying the synthetic transactions that are executed on a watcher node, administrators can also use the **Set-CsWatcherNodeConfiguration** cmdlet to carry out two other important tasks: enabling and disabling the watcher node, and configuring the watcher node to use either internal URLs or external URLs when running its tests.</span></span>

<span data-ttu-id="7d117-106">По умолчанию узлы-наблюдатели периодически запускают все включенные искусственные транзакции.</span><span class="sxs-lookup"><span data-stu-id="7d117-106">By default, watcher nodes are designed to periodically run all their enabled synthetic transactions.</span></span> <span data-ttu-id="7d117-107">Однако иногда они могут приостановить выполнение транзакций.</span><span class="sxs-lookup"><span data-stu-id="7d117-107">Sometimes, however, you may need to suspend those transactions.</span></span> <span data-ttu-id="7d117-108">Например, если узел-наблюдатель временно отключился от сети, у него больше нет причин запускать искусственные транзакции.</span><span class="sxs-lookup"><span data-stu-id="7d117-108">For example, if the watcher node is temporarily disconnected from the network, then there is no reason to run the synthetic transactions.</span></span> <span data-ttu-id="7d117-109">Без сетевого подключения эти транзакции заведомо завершатся со сбоем.</span><span class="sxs-lookup"><span data-stu-id="7d117-109">Without network connectivity, those transactions are guaranteed to fail.</span></span> <span data-ttu-id="7d117-110">Если вы хотите временно отключить узел-наблюдатель, выполните следующую команду в командной консоли Lync Server:</span><span class="sxs-lookup"><span data-stu-id="7d117-110">If you want to temporarily disable a watcher node, run a command similar to this from the Lync Server Management Shell:</span></span>

    Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -Enabled $False

<span data-ttu-id="7d117-p102">Эта команда приведет к отключению выполнения искусственных транзакций на узле-наблюдателе. Чтобы возобновить выполнение искусственных транзакций, снова задайте для свойства Enabled значение True ($True):</span><span class="sxs-lookup"><span data-stu-id="7d117-p102">This command will disable the execution of synthetic transactions on the watcher node atl-watcher- 001.litwareinc.com. To resume execution of the synthetic transactions, set the Enabled property back to True ($True):</span></span>

    Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -Enabled $True

<div>


> [!NOTE]  
> <span data-ttu-id="7d117-113">Свойство Enabled может использоваться для включения или отключения узлов-наблюдателей.</span><span class="sxs-lookup"><span data-stu-id="7d117-113">The Enabled property can be used to turn watcher nodes on or off.</span></span> <span data-ttu-id="7d117-114">Если нет необходимости временно удалять узел-наблюдатель, используйте командлет <STRONG>Remove-CsWatcherNodeConfiguration</STRONG>:</span><span class="sxs-lookup"><span data-stu-id="7d117-114">If you want to permanently delete a watcher node, use the <STRONG>Remove-CsWatcherNodeConfiguration</STRONG> cmdlet:</span></span><BR><span data-ttu-id="7d117-115">Remove-CsWatcherNodeConfiguration –Identity "atl-watcher-001.litwareinc.com"</span><span class="sxs-lookup"><span data-stu-id="7d117-115">Remove-CsWatcherNodeConfiguration –Identity "atl-watcher-001.litwareinc.com"</span></span><BR><span data-ttu-id="7d117-116">Эта команда удаляет с указанного компьютера все параметры конфигурации узла-наблюдателя, что препятствует автоматическому запуску на этом компьютере искусственных транзакций.</span><span class="sxs-lookup"><span data-stu-id="7d117-116">That command removes all the watcher node configuration settings from the specified computer, which prevents the computer from automatically running synthetic transactions.</span></span> <span data-ttu-id="7d117-117">Однако команда не удаляет файлы агента System Center и системные файлы Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7d117-117">However, the command does not uninstall the System Center agent files or the Lync Server 2013 system files.</span></span>



</div>

<span data-ttu-id="7d117-p105">По умолчанию узлы-наблюдатели используют при проведении тестов внешние URL-адреса. Однако узлы-наблюдатели можно настроить для использования внутренних URL-адресов организации. Это позволит администраторам проверить доступ к URL-адресам тех пользователей, которые находятся внутри сети периметра. Чтобы настроить узел-наблюдатель для использования внутренних URL-адресов вместо внешних URL-адресов, задайте для свойства UseInternalWebUrls значение True ($True):</span><span class="sxs-lookup"><span data-stu-id="7d117-p105">By default, watcher nodes use an organization's external URLs when conducting their tests. However, watcher nodes can also be configured to use the organization's internal URLs. This enables administrators to verify URL access for users located inside the perimeter network. To configure a watcher node to use internal URLs instead of external URLs, set the UseInternalWebUrls property to True ($True):</span></span>

    Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -UseInternalWebUrls $True

<span data-ttu-id="7d117-122">Если сбросить это свойство до значения по умолчанию False ($False), наблюдатель будет использовать внешние URL-адреса:</span><span class="sxs-lookup"><span data-stu-id="7d117-122">If you reset this property to the default value of False ($False), the watcher will then use the external URLs:</span></span>

    Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -UseInternalWebUrls $False

</div>

<span> </span>

</div>

</div>

</div>

