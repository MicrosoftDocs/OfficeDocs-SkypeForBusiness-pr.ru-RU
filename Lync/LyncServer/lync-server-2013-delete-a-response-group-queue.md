---
title: 'Lync Server 2013: удаление очереди групп ответов'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delete a Response Group queue
ms:assetid: 67c7a489-8c5f-4c6b-9387-9d4c11d43695
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521008(v=OCS.15)
ms:contentKeyID: 48184356
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6d78b1396d92b16be120484f5bf1b40ef2e47a81
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41740989"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="delete-a-response-group-queue-in-lync-server-2013"></a><span data-ttu-id="ba4ab-102">Удаление очереди групп ответов в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ba4ab-102">Delete a Response Group queue in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ba4ab-103">_**Тема последнего изменения:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="ba4ab-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="ba4ab-104">Для удаления очереди воспользуйтесь одной из описанных ниже процедур.</span><span class="sxs-lookup"><span data-stu-id="ba4ab-104">Use one of the following procedures to delete a queue.</span></span>

<div>

## <a name="to-use-lync-server-control-panel-to-delete-a-queue"></a><span data-ttu-id="ba4ab-105">Удаление очереди с помощью панели управления Lync Server</span><span class="sxs-lookup"><span data-stu-id="ba4ab-105">To use Lync Server Control Panel to delete a queue</span></span>

1.  <span data-ttu-id="ba4ab-106">Выполните вход как член группы RTCUniversalServerAdmins или одной из предварительно заданных административных ролей, поддерживающих группу ответа.</span><span class="sxs-lookup"><span data-stu-id="ba4ab-106">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>

2.  <span data-ttu-id="ba4ab-107">Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="ba4ab-107">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="ba4ab-108">Дополнительные сведения о различных способах, которые можно использовать для запуска панели управления Lync Server, приведены в разделе [Открытие меню администрирования Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="ba4ab-108">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="ba4ab-109">В левой панели навигации щелкните **Группы ответа**, затем щелкните **Очередь**.</span><span class="sxs-lookup"><span data-stu-id="ba4ab-109">In the left navigation bar, click **Response Groups**, and then click **Queue**.</span></span>

4.  <span data-ttu-id="ba4ab-110">В поле Поиск введите часть или все имя очереди, которую вы хотите удалить.</span><span class="sxs-lookup"><span data-stu-id="ba4ab-110">In the search field, type part or all of the name of the queue you want to delete.</span></span>

5.  <span data-ttu-id="ba4ab-111">В списке очередей выберите нужную очередь и нажмите кнопку **изменить**, а затем — **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="ba4ab-111">In the list of queues, click the queue that you want, click **Edit**, and then click **Delete**.</span></span>

6.  <span data-ttu-id="ba4ab-112">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="ba4ab-112">Click **OK**.</span></span>

</div>

<div>

## <a name="to-use-windows-powershell-to-delete-a-queue"></a><span data-ttu-id="ba4ab-113">Использование Windows PowerShell для удаления очереди</span><span class="sxs-lookup"><span data-stu-id="ba4ab-113">To use Windows PowerShell to delete a queue</span></span>

1.  <span data-ttu-id="ba4ab-114">Выполните вход как член группы RTCUniversalServerAdmins или одной из предварительно заданных административных ролей, поддерживающих группу ответа.</span><span class="sxs-lookup"><span data-stu-id="ba4ab-114">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>

2.  <span data-ttu-id="ba4ab-115">Запустите командную консоль Lync Server Management Shell: нажмите кнопку **Пуск**, выберите **все программы**, а затем — **Microsoft Lync Server 2013**, а затем — **Командная консоль Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="ba4ab-115">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="ba4ab-116">В командной строке выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="ba4ab-116">At the command line, run:</span></span>
    
        Get-CsRgsQueue -Identity <Application Server service> -Name "<name of queue>" | Remove-CsRgsQueue
    
    <span data-ttu-id="ba4ab-117">Например:</span><span class="sxs-lookup"><span data-stu-id="ba4ab-117">For example:</span></span>
    
        Get-CsRgsQueue -Identity service:ApplicationServer:redmond.contoso.com -Name "Help Desk" | Remove-CsRgsQueue

</div>

</div>

<span> </span>

</div>

</div>

</div>

