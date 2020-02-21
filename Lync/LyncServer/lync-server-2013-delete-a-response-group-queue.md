---
title: 'Lync Server 2013: удаление очереди группы ответа'
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
ms.openlocfilehash: d3e79a2d5ba9eeb21cf437eb643a8a12c3c64b61
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42190762"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="delete-a-response-group-queue-in-lync-server-2013"></a><span data-ttu-id="74a93-102">Удаление очереди группы ответа в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="74a93-102">Delete a Response Group queue in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="74a93-103">_**Последнее изменение темы:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="74a93-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="74a93-104">Используйте одну из следующих процедур для удаления очереди.</span><span class="sxs-lookup"><span data-stu-id="74a93-104">Use one of the following procedures to delete a queue.</span></span>

<div>

## <a name="to-use-lync-server-control-panel-to-delete-a-queue"></a><span data-ttu-id="74a93-105">Удаление очереди с помощью панели управления Lync Server</span><span class="sxs-lookup"><span data-stu-id="74a93-105">To use Lync Server Control Panel to delete a queue</span></span>

1.  <span data-ttu-id="74a93-106">Выполните вход в качестве члена группы RTCUniversalServerAdmins или в качестве участника одной из предварительно заданных административных ролей, поддерживающих группу ответа.</span><span class="sxs-lookup"><span data-stu-id="74a93-106">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>

2.  <span data-ttu-id="74a93-107">Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="74a93-107">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="74a93-108">Для получения дополнительных сведений о различных методах, которые можно использовать для запуска панели управления Lync Server, ознакомьтесь со статьей [Open Lync server 2013 администрирование](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="74a93-108">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="74a93-109">На панели навигации слева выберите пункт **Группы ответа** и щелкните **Очередь**.</span><span class="sxs-lookup"><span data-stu-id="74a93-109">In the left navigation bar, click **Response Groups**, and then click **Queue**.</span></span>

4.  <span data-ttu-id="74a93-110">В поле поиска введите имя очереди, которую вы хотите удалить, или его часть.</span><span class="sxs-lookup"><span data-stu-id="74a93-110">In the search field, type part or all of the name of the queue you want to delete.</span></span>

5.  <span data-ttu-id="74a93-111">В списке очередей выберите нужную очередь, нажмите кнопку **Изменить**, а затем щелкните **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="74a93-111">In the list of queues, click the queue that you want, click **Edit**, and then click **Delete**.</span></span>

6.  <span data-ttu-id="74a93-112">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="74a93-112">Click **OK**.</span></span>

</div>

<div>

## <a name="to-use-windows-powershell-to-delete-a-queue"></a><span data-ttu-id="74a93-113">Использование Windows PowerShell для удаления очереди</span><span class="sxs-lookup"><span data-stu-id="74a93-113">To use Windows PowerShell to delete a queue</span></span>

1.  <span data-ttu-id="74a93-114">Выполните вход в качестве члена группы RTCUniversalServerAdmins или в качестве участника одной из предварительно заданных административных ролей, поддерживающих группу ответа.</span><span class="sxs-lookup"><span data-stu-id="74a93-114">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>

2.  <span data-ttu-id="74a93-115">Запустите командную консоль Lync Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Microsoft Lync Server 2013** и щелкните элемент **Командная консоль Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="74a93-115">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="74a93-116">В командной строке выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="74a93-116">At the command line, run:</span></span>
    
        Get-CsRgsQueue -Identity <Application Server service> -Name "<name of queue>" | Remove-CsRgsQueue
    
    <span data-ttu-id="74a93-117">Пример:</span><span class="sxs-lookup"><span data-stu-id="74a93-117">For example:</span></span>
    
        Get-CsRgsQueue -Identity service:ApplicationServer:redmond.contoso.com -Name "Help Desk" | Remove-CsRgsQueue

</div>

</div>

<span> </span>

</div>

</div>

</div>

