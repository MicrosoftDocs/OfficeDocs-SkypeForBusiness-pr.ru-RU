---
title: 'Lync Server 2013: Удаление рабочего процесса'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Delete a workflow
ms:assetid: 0469a6b8-ce1e-459b-bc3d-4c8adf2d97d5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520944(v=OCS.15)
ms:contentKeyID: 48183274
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1aabb1b46d3f67408d586bada6db3d1efaf0538e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34834637"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="delete-a-workflow-in-lync-server-2013"></a><span data-ttu-id="df752-102">Удаление рабочего процесса в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="df752-102">Delete a workflow in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="df752-103">_**Тема последнего изменения:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="df752-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="df752-104">Для удаления рабочего процесса воспользуйтесь одной из описанных ниже процедур.</span><span class="sxs-lookup"><span data-stu-id="df752-104">Use one of the following procedures to delete a workflow.</span></span>

<div>

## <a name="to-use-lync-server-control-panel-delete-a-workflow"></a><span data-ttu-id="df752-105">Удаление рабочего процесса с помощью панели управления Lync Server</span><span class="sxs-lookup"><span data-stu-id="df752-105">To use Lync Server Control Panel delete a workflow</span></span>

1.  <span data-ttu-id="df752-106">Выполните вход как член группы RTCUniversalServerAdmins или одной из предварительно заданных административных ролей, поддерживающих группу ответа.</span><span class="sxs-lookup"><span data-stu-id="df752-106">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>

2.  <span data-ttu-id="df752-107">Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="df752-107">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="df752-108">Дополнительные сведения о различных способах, которые можно использовать для запуска панели управления Lync Server, приведены в разделе [Открытие меню администрирования Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="df752-108">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="df752-109">В левой области навигации щелкните **Группы ответа**, затем **Рабочий процесс**.</span><span class="sxs-lookup"><span data-stu-id="df752-109">In the left navigation bar, click **Response Groups**, and then click **Workflow**.</span></span>

4.  <span data-ttu-id="df752-110">На странице **Рабочий процесс** щелкните **Создать или редактировать рабочий процесс**.</span><span class="sxs-lookup"><span data-stu-id="df752-110">On the **Workflow** page, click **Create or edit a workflow**.</span></span>

5.  <span data-ttu-id="df752-111">В поле **выберите Поиск службы** введите часть или все имя службы **аппликатионсервер** , в которой размещен рабочий процесс, который вы хотите удалить.</span><span class="sxs-lookup"><span data-stu-id="df752-111">In the **Select a Service** search field, type part or all of the name of the **ApplicationServer** service that hosts the workflow that you want to delete.</span></span>

6.  <span data-ttu-id="df752-112">В списке служб выберите нужную службу и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="df752-112">In the list of services, click the service that you want, and then click **OK**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="df752-113">Откроется веб-страница средства настройки группы ответа.</span><span class="sxs-lookup"><span data-stu-id="df752-113">The Response Group Configuration Tool webpage opens.</span></span> <span data-ttu-id="df752-114">Вы также можете открыть веб-страницу средства настройки группы ответа непосредственно из браузера, подключившись к <STRONG>&lt;HTTPS://вебпулфкдн&gt;/ргсконфиг</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="df752-114">You can also open the Response Group Configuration Tool webpage directly from a web browser by connecting to <STRONG>https://&lt;webPoolFqdn&gt;/RgsConfig</STRONG>.</span></span>

    
    </div>

7.  <span data-ttu-id="df752-115">В разделе **Управление существующим рабочим процессом**найдите рабочий процесс, который вы хотите удалить, а затем в разделе **действие**нажмите кнопку **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="df752-115">Under **Manage an Existing Workflow**, locate the workflow you want to delete, and then under **Action**, click **Delete**.</span></span>

8.  <span data-ttu-id="df752-116">Нажмите **Да**.</span><span class="sxs-lookup"><span data-stu-id="df752-116">Click **Yes**.</span></span>

</div>

<div>

## <a name="to-use-windows-powershell-to-delete-a-workflow"></a><span data-ttu-id="df752-117">Использование Windows PowerShell для удаления рабочего процесса</span><span class="sxs-lookup"><span data-stu-id="df752-117">To use Windows PowerShell to delete a workflow</span></span>

1.  <span data-ttu-id="df752-118">Выполните вход как член группы RTCUniversalServerAdmins или одной из предварительно заданных административных ролей, поддерживающих группу ответа.</span><span class="sxs-lookup"><span data-stu-id="df752-118">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>

2.  <span data-ttu-id="df752-119">Запустите командную консоль Lync Server Management Shell: нажмите кнопку **Пуск**, выберите **все программы**, а затем — **Microsoft Lync Server 2013**, а затем — **Командная консоль Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="df752-119">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="df752-120">В командной строке выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="df752-120">At the command line, run:</span></span>
    
        Get-CsRgsWorkflow -Identity <Application Server service> -Name "<name of workflow>" | Remove-CsRgsWorkflow
    
    <span data-ttu-id="df752-121">Например:</span><span class="sxs-lookup"><span data-stu-id="df752-121">For example:</span></span>
    
        Get-CsRgsWorkflow -Identity service:ApplicationServer:redmond.contoso.com -Name "Help Desk" | Remove-CsRgsWorkflow

</div>

</div>

<span> </span>

</div>

</div>

</div>

