---
title: 'Lync Server 2013: Удаление группы агентов'
description: 'Lync Server 2013: Удаление группы агентов.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delete an agent group
ms:assetid: df385fd1-62f4-42b7-a349-4eb38dea50c8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182597(v=OCS.15)
ms:contentKeyID: 48185670
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dded2db0957e37a624d7e8bf3a06e102f8d35cad
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48553685"
---
# <a name="delete-an-agent-group-in-lync-server-2013"></a><span data-ttu-id="ec7bc-103">Удаление группы агентов в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ec7bc-103">Delete an agent group in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ec7bc-104">_**Последнее изменение темы:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="ec7bc-104">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="ec7bc-105">Воспользуйтесь одной из описанных ниже процедур, чтобы удалить группу агентов.</span><span class="sxs-lookup"><span data-stu-id="ec7bc-105">Use one of the following procedures to delete an agent group.</span></span>

<div>

## <a name="to-use-lync-server-control-panel-to-delete-an-agent-group"></a><span data-ttu-id="ec7bc-106">Удаление группы агентов с помощью панели управления Lync Server</span><span class="sxs-lookup"><span data-stu-id="ec7bc-106">To use Lync Server Control Panel to delete an agent group</span></span>

1.  <span data-ttu-id="ec7bc-107">Выполните вход в качестве члена группы RTCUniversalServerAdmins или в качестве участника одной из предварительно заданных административных ролей, поддерживающих группу ответа.</span><span class="sxs-lookup"><span data-stu-id="ec7bc-107">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>

2.  <span data-ttu-id="ec7bc-108">Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="ec7bc-108">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="ec7bc-109">Для получения дополнительных сведений о различных методах, которые можно использовать для запуска панели управления Lync Server, ознакомьтесь со статьей [Open Lync server 2013 администрирование](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="ec7bc-109">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="ec7bc-110">В левой панели навигации щелкните элемент **Response Groups** (Группы ответа), а затем **Group** (Группа).</span><span class="sxs-lookup"><span data-stu-id="ec7bc-110">In the left navigation bar, click **Response Groups**, and then click **Group**.</span></span>

4.  <span data-ttu-id="ec7bc-111">На странице  **Response Groups** (Группы ответа) в поле поиска введите полностью или частично имя группы агентов, которую вы хотите удалить.</span><span class="sxs-lookup"><span data-stu-id="ec7bc-111">On the **Response Groups** page, type all or part of the name of the agent group that you want to delete in the search field.</span></span>

5.  <span data-ttu-id="ec7bc-112">В списке результатов поиска выберите требуемую группу, нажмите кнопку **Изменить**, а затем щелкните элемент **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="ec7bc-112">In the resulting list, click the group that you want to delete, click **Edit**, and then click **Delete**.</span></span>

6.  <span data-ttu-id="ec7bc-113">Click **ОК**.</span><span class="sxs-lookup"><span data-stu-id="ec7bc-113">Click **OK**.</span></span>

</div>

<div>

## <a name="to-use-windows-powershell-to-delete-an-agent-group"></a><span data-ttu-id="ec7bc-114">Удаление группы агентов с помощью Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="ec7bc-114">To use Windows PowerShell to delete an agent group</span></span>

1.  <span data-ttu-id="ec7bc-115">Выполните вход в качестве члена группы RTCUniversalServerAdmins или в качестве участника одной из предварительно заданных административных ролей, поддерживающих группу ответа.</span><span class="sxs-lookup"><span data-stu-id="ec7bc-115">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>

2.  <span data-ttu-id="ec7bc-116">Запустите командную консоль Lync Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Microsoft Lync Server 2013** и щелкните элемент **Командная консоль Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="ec7bc-116">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="ec7bc-117">В командной строке выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="ec7bc-117">At the command line, run:</span></span>
    
        Get-CsRgsAgentGroup -Identity <Application Server service> -Name "<name of agent group>" | Remove-CsRgsAgentGroup
    
    <span data-ttu-id="ec7bc-118">Пример:</span><span class="sxs-lookup"><span data-stu-id="ec7bc-118">For example:</span></span>
    
        Get-CsRgsAgentGroup -Identity service:ApplicationServer:redmond.contoso.com -Name "Human Resources" | Remove-CsRgsAgentGroup

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="ec7bc-119">См. также</span><span class="sxs-lookup"><span data-stu-id="ec7bc-119">See Also</span></span>


[<span data-ttu-id="ec7bc-120">Создание или изменение группы агентов в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ec7bc-120">Create or modify an agent group in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-an-agent-group.md)  


[<span data-ttu-id="ec7bc-121">Remove — CsRgsAgentGroup</span><span class="sxs-lookup"><span data-stu-id="ec7bc-121">Remove-CsRgsAgentGroup</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsRgsAgentGroup)  
[<span data-ttu-id="ec7bc-122">Get — CsRgsAgentGroup</span><span class="sxs-lookup"><span data-stu-id="ec7bc-122">Get-CsRgsAgentGroup</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsRgsAgentGroup)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

