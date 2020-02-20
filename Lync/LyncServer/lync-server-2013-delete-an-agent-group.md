---
title: 'Lync Server 2013: Удаление группы агентов'
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
ms.openlocfilehash: 4ed86d1f7b9476626fe00e733407cd821c279cef
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42154551"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="delete-an-agent-group-in-lync-server-2013"></a><span data-ttu-id="2ba12-102">Удаление группы агентов в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2ba12-102">Delete an agent group in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2ba12-103">_**Последнее изменение темы:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="2ba12-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="2ba12-104">Воспользуйтесь одной из описанных ниже процедур, чтобы удалить группу агентов.</span><span class="sxs-lookup"><span data-stu-id="2ba12-104">Use one of the following procedures to delete an agent group.</span></span>

<div>

## <a name="to-use-lync-server-control-panel-to-delete-an-agent-group"></a><span data-ttu-id="2ba12-105">Удаление группы агентов с помощью панели управления Lync Server</span><span class="sxs-lookup"><span data-stu-id="2ba12-105">To use Lync Server Control Panel to delete an agent group</span></span>

1.  <span data-ttu-id="2ba12-106">Выполните вход в качестве члена группы RTCUniversalServerAdmins или в качестве участника одной из предварительно заданных административных ролей, поддерживающих группу ответа.</span><span class="sxs-lookup"><span data-stu-id="2ba12-106">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>

2.  <span data-ttu-id="2ba12-107">Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="2ba12-107">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="2ba12-108">Для получения дополнительных сведений о различных методах, которые можно использовать для запуска панели управления Lync Server, ознакомьтесь со статьей [Open Lync server 2013 администрирование](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="2ba12-108">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="2ba12-109">В левой панели навигации щелкните элемент **Response Groups** (Группы ответа), а затем **Group** (Группа).</span><span class="sxs-lookup"><span data-stu-id="2ba12-109">In the left navigation bar, click **Response Groups**, and then click **Group**.</span></span>

4.  <span data-ttu-id="2ba12-110">На странице  **Response Groups** (Группы ответа) в поле поиска введите полностью или частично имя группы агентов, которую вы хотите удалить.</span><span class="sxs-lookup"><span data-stu-id="2ba12-110">On the **Response Groups** page, type all or part of the name of the agent group that you want to delete in the search field.</span></span>

5.  <span data-ttu-id="2ba12-111">В списке результатов поиска выберите требуемую группу, нажмите кнопку **Изменить**, а затем щелкните элемент **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="2ba12-111">In the resulting list, click the group that you want to delete, click **Edit**, and then click **Delete**.</span></span>

6.  <span data-ttu-id="2ba12-112">Click **ОК**.</span><span class="sxs-lookup"><span data-stu-id="2ba12-112">Click **OK**.</span></span>

</div>

<div>

## <a name="to-use-windows-powershell-to-delete-an-agent-group"></a><span data-ttu-id="2ba12-113">Удаление группы агентов с помощью Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="2ba12-113">To use Windows PowerShell to delete an agent group</span></span>

1.  <span data-ttu-id="2ba12-114">Выполните вход в качестве члена группы RTCUniversalServerAdmins или в качестве участника одной из предварительно заданных административных ролей, поддерживающих группу ответа.</span><span class="sxs-lookup"><span data-stu-id="2ba12-114">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>

2.  <span data-ttu-id="2ba12-115">Запустите командную консоль Lync Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Microsoft Lync Server 2013** и щелкните элемент **Командная консоль Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="2ba12-115">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="2ba12-116">В командной строке выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="2ba12-116">At the command line, run:</span></span>
    
        Get-CsRgsAgentGroup -Identity <Application Server service> -Name "<name of agent group>" | Remove-CsRgsAgentGroup
    
    <span data-ttu-id="2ba12-117">Пример:</span><span class="sxs-lookup"><span data-stu-id="2ba12-117">For example:</span></span>
    
        Get-CsRgsAgentGroup -Identity service:ApplicationServer:redmond.contoso.com -Name "Human Resources" | Remove-CsRgsAgentGroup

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="2ba12-118">См. также</span><span class="sxs-lookup"><span data-stu-id="2ba12-118">See Also</span></span>


[<span data-ttu-id="2ba12-119">Создание или изменение группы агентов в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2ba12-119">Create or modify an agent group in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-an-agent-group.md)  


[<span data-ttu-id="2ba12-120">Remove — CsRgsAgentGroup</span><span class="sxs-lookup"><span data-stu-id="2ba12-120">Remove-CsRgsAgentGroup</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsRgsAgentGroup)  
[<span data-ttu-id="2ba12-121">Get — CsRgsAgentGroup</span><span class="sxs-lookup"><span data-stu-id="2ba12-121">Get-CsRgsAgentGroup</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsRgsAgentGroup)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

