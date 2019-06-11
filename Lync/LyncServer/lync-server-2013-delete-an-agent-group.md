---
title: 'Lync Server 2013: Удаление группы агента'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Delete an agent group
ms:assetid: df385fd1-62f4-42b7-a349-4eb38dea50c8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182597(v=OCS.15)
ms:contentKeyID: 48185670
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: adcdc0245f6fdd835492084fcae91389409f52c8
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34834631"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="delete-an-agent-group-in-lync-server-2013"></a><span data-ttu-id="348ce-102">Удаление группы агента в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="348ce-102">Delete an agent group in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="348ce-103">_**Тема последнего изменения:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="348ce-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="348ce-104">Для удаления группы агента воспользуйтесь одной из описанных ниже процедур.</span><span class="sxs-lookup"><span data-stu-id="348ce-104">Use one of the following procedures to delete an agent group.</span></span>

<div>

## <a name="to-use-lync-server-control-panel-to-delete-an-agent-group"></a><span data-ttu-id="348ce-105">Удаление группы агента с помощью панели управления Lync Server</span><span class="sxs-lookup"><span data-stu-id="348ce-105">To use Lync Server Control Panel to delete an agent group</span></span>

1.  <span data-ttu-id="348ce-106">Выполните вход как член группы RTCUniversalServerAdmins или одной из предварительно заданных административных ролей, поддерживающих группу ответа.</span><span class="sxs-lookup"><span data-stu-id="348ce-106">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>

2.  <span data-ttu-id="348ce-107">Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="348ce-107">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="348ce-108">Дополнительные сведения о различных способах, которые можно использовать для запуска панели управления Lync Server, приведены в разделе [Открытие меню администрирования Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="348ce-108">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="348ce-109">В левой области навигации щелкните **Группы ответа**, затем **Группа**.</span><span class="sxs-lookup"><span data-stu-id="348ce-109">In the left navigation bar, click **Response Groups**, and then click **Group**.</span></span>

4.  <span data-ttu-id="348ce-110">На странице **группы ответа** введите имя или часть имени группы агента, которую вы хотите удалить, в поле поиска.</span><span class="sxs-lookup"><span data-stu-id="348ce-110">On the **Response Groups** page, type all or part of the name of the agent group that you want to delete in the search field.</span></span>

5.  <span data-ttu-id="348ce-111">В списке результатов выберите группу, которую вы хотите удалить, и нажмите кнопку **изменить**, а затем — **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="348ce-111">In the resulting list, click the group that you want to delete, click **Edit**, and then click **Delete**.</span></span>

6.  <span data-ttu-id="348ce-112">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="348ce-112">Click **OK**.</span></span>

</div>

<div>

## <a name="to-use-windows-powershell-to-delete-an-agent-group"></a><span data-ttu-id="348ce-113">Использование Windows PowerShell для удаления группы агента</span><span class="sxs-lookup"><span data-stu-id="348ce-113">To use Windows PowerShell to delete an agent group</span></span>

1.  <span data-ttu-id="348ce-114">Выполните вход как член группы RTCUniversalServerAdmins или одной из предварительно заданных административных ролей, поддерживающих группу ответа.</span><span class="sxs-lookup"><span data-stu-id="348ce-114">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>

2.  <span data-ttu-id="348ce-115">Запустите командную консоль Lync Server Management Shell: нажмите кнопку **Пуск**, выберите **все программы**, а затем — **Microsoft Lync Server 2013**, а затем — **Командная консоль Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="348ce-115">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="348ce-116">В командной строке выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="348ce-116">At the command line, run:</span></span>
    
        Get-CsRgsAgentGroup -Identity <Application Server service> -Name "<name of agent group>" | Remove-CsRgsAgentGroup
    
    <span data-ttu-id="348ce-117">Например:</span><span class="sxs-lookup"><span data-stu-id="348ce-117">For example:</span></span>
    
        Get-CsRgsAgentGroup -Identity service:ApplicationServer:redmond.contoso.com -Name "Human Resources" | Remove-CsRgsAgentGroup

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="348ce-118">См. также</span><span class="sxs-lookup"><span data-stu-id="348ce-118">See Also</span></span>


[<span data-ttu-id="348ce-119">Создание или изменение группы агента в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="348ce-119">Create or modify an agent group in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-an-agent-group.md)  


[<span data-ttu-id="348ce-120">Remove-CsRgsAgentGroup</span><span class="sxs-lookup"><span data-stu-id="348ce-120">Remove-CsRgsAgentGroup</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsRgsAgentGroup)  
[<span data-ttu-id="348ce-121">Get-CsRgsAgentGroup</span><span class="sxs-lookup"><span data-stu-id="348ce-121">Get-CsRgsAgentGroup</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsRgsAgentGroup)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

