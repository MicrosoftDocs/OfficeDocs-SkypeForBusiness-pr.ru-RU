---
title: 'Lync Server 2013: Управление узлами наблюдения'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Managing watcher nodes
ms:assetid: 66deaf49-a71f-4a6e-ada0-ea8b688ee921
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688078(v=OCS.15)
ms:contentKeyID: 49733674
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e7edddd1a1bb67dc4bf3df5b7809aa76b2397e56
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34827643"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="managing-watcher-nodes-in-lync-server-2013"></a><span data-ttu-id="a79f3-102">Управление узлами наблюдения в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a79f3-102">Managing watcher nodes in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a79f3-103">_**Тема последнего изменения:** 2012-10-20_</span><span class="sxs-lookup"><span data-stu-id="a79f3-103">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="a79f3-104">Помимо изменения искусственных транзакций, которые выполняются на узле-наблюдателе, администраторы также могут использовать командлет **Set-ксватчернодеконфигуратион** , чтобы выполнить две другие важные задачи: Включение и отключение узла-наблюдателя, а также Настройка узла-наблюдателя на использование внутренних URL или внешних URL-адресов при выполнении тестов.</span><span class="sxs-lookup"><span data-stu-id="a79f3-104">In addition to modifying the synthetic transactions that are executed on a watcher node, administrators can also use the **Set-CsWatcherNodeConfiguration** cmdlet to carry out two other important tasks: enabling and disabling the watcher node, and configuring the watcher node to use either internal URLs or external URLs when running its tests.</span></span>

<span data-ttu-id="a79f3-105">По умолчанию узлы-наблюдатели периодически запускают все включенные искусственные транзакции.</span><span class="sxs-lookup"><span data-stu-id="a79f3-105">By default, watcher nodes are designed to periodically run all their enabled synthetic transactions.</span></span> <span data-ttu-id="a79f3-106">Однако иногда вам может потребоваться приостановить эти транзакции.</span><span class="sxs-lookup"><span data-stu-id="a79f3-106">Sometimes, however, you may need to suspend those transactions.</span></span> <span data-ttu-id="a79f3-107">Например, если узел-наблюдатель временно отключился от сети, у него больше нет причин запускать искусственные транзакции.</span><span class="sxs-lookup"><span data-stu-id="a79f3-107">For example, if the watcher node is temporarily disconnected from the network, then there is no reason to run the synthetic transactions.</span></span> <span data-ttu-id="a79f3-108">При отсутствии подключения к сети эти транзакции гарантировано завершаются сбоем.</span><span class="sxs-lookup"><span data-stu-id="a79f3-108">Without network connectivity, those transactions are guaranteed to fail.</span></span> <span data-ttu-id="a79f3-109">Если вы хотите временно отключить узел наблюдателя, выполните следующую команду в командной консоли Lync Server.</span><span class="sxs-lookup"><span data-stu-id="a79f3-109">If you want to temporarily disable a watcher node, run a command similar to this from the Lync Server Management Shell:</span></span>

    Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -Enabled $False

<span data-ttu-id="a79f3-110">Эта команда отключит выполнение виртуальных транзакций на узле наблюдателя ATL-Watch-001.litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="a79f3-110">This command will disable the execution of synthetic transactions on the watcher node atl-watcher- 001.litwareinc.com.</span></span> <span data-ttu-id="a79f3-111">Чтобы возобновить выполнение искусственных транзакций, снова задайте для свойства Enabled значение True ($True):</span><span class="sxs-lookup"><span data-stu-id="a79f3-111">To resume execution of the synthetic transactions, set the Enabled property back to True ($True):</span></span>

    Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -Enabled $True

<div>


> [!NOTE]  
> <span data-ttu-id="a79f3-p103">Свойство Enabled может использоваться для включения или отключения узлов-наблюдателей. Если нет необходимости временно удалять узел-наблюдатель, используйте командлет <STRONG>Remove-CsWatcherNodeConfiguration</STRONG>:</span><span class="sxs-lookup"><span data-stu-id="a79f3-p103">The Enabled property can be used to turn watcher nodes on or off. If you want to permanently delete a watcher node, use the <STRONG>Remove-CsWatcherNodeConfiguration</STRONG> cmdlet:</span></span><BR><span data-ttu-id="a79f3-114">Remove-Ксватчернодеконфигуратион – Identity "atl-watcher-001.litwareinc.com"</span><span class="sxs-lookup"><span data-stu-id="a79f3-114">Remove-CsWatcherNodeConfiguration –Identity "atl-watcher-001.litwareinc.com"</span></span><BR><span data-ttu-id="a79f3-115">Эта команда удаляет все параметры конфигурации узла-наблюдателя с указанного компьютера, что предотвращает автоматическое выполнение виртуальных транзакций на компьютере.</span><span class="sxs-lookup"><span data-stu-id="a79f3-115">That command removes all the watcher node configuration settings from the specified computer, which prevents the computer from automatically running synthetic transactions.</span></span> <span data-ttu-id="a79f3-116">Тем не менее, команда не удаляет файлы агента System Center и системные файлы Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a79f3-116">However, the command does not uninstall the System Center agent files or the Lync Server 2013 system files.</span></span>



</div>

<span data-ttu-id="a79f3-117">По умолчанию узлы-наблюдатели используют внешние URL-адреса организации при проведении тестов.</span><span class="sxs-lookup"><span data-stu-id="a79f3-117">By default, watcher nodes use an organization's external URLs when conducting their tests.</span></span> <span data-ttu-id="a79f3-118">Однако узлы-наблюдатели также могут быть настроены на использование внутренних URL в Организации.</span><span class="sxs-lookup"><span data-stu-id="a79f3-118">However, watcher nodes can also be configured to use the organization's internal URLs.</span></span> <span data-ttu-id="a79f3-119">Это позволит администраторам проверить доступ к URL-адресам тех пользователей, которые находятся внутри сети периметра.</span><span class="sxs-lookup"><span data-stu-id="a79f3-119">This enables administrators to verify URL access for users located inside the perimeter network.</span></span> <span data-ttu-id="a79f3-120">Чтобы настроить узел наблюдателя для использования внутренних URL-адресов вместо внешних URL-адресов, задайте для свойства Усеинтерналвебурлс значение true ($True):</span><span class="sxs-lookup"><span data-stu-id="a79f3-120">To configure a watcher node to use internal URLs instead of external URLs, set the UseInternalWebUrls property to True ($True):</span></span>

    Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -UseInternalWebUrls $True

<span data-ttu-id="a79f3-121">Если вы переустановили для этого свойства значение по умолчанию, равное false ($False), наблюдатель будет использовать внешние URL-адреса:</span><span class="sxs-lookup"><span data-stu-id="a79f3-121">If you reset this property to the default value of False ($False), the watcher will then use the external URLs:</span></span>

    Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -UseInternalWebUrls $False

</div>

<span> </span>

</div>

</div>

</div>

