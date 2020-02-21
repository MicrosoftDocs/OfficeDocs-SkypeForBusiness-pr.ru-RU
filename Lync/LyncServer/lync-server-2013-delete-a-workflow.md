---
title: 'Lync Server 2013: Удаление рабочего процесса'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delete a workflow
ms:assetid: 0469a6b8-ce1e-459b-bc3d-4c8adf2d97d5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520944(v=OCS.15)
ms:contentKeyID: 48183274
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e1f3265591b1beb7180864b8e3a613989dfca397
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42213995"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="delete-a-workflow-in-lync-server-2013"></a><span data-ttu-id="a1222-102">Удаление рабочего процесса в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a1222-102">Delete a workflow in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a1222-103">_**Последнее изменение темы:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="a1222-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="a1222-104">Для удаления рабочего процесса воспользуйтесь одной из следующих процедур.</span><span class="sxs-lookup"><span data-stu-id="a1222-104">Use one of the following procedures to delete a workflow.</span></span>

<div>

## <a name="to-use-lync-server-control-panel-delete-a-workflow"></a><span data-ttu-id="a1222-105">Удаление рабочего процесса с помощью панели управления Lync Server</span><span class="sxs-lookup"><span data-stu-id="a1222-105">To use Lync Server Control Panel delete a workflow</span></span>

1.  <span data-ttu-id="a1222-106">Выполните вход в качестве члена группы RTCUniversalServerAdmins или в качестве участника одной из предварительно заданных административных ролей, поддерживающих группу ответа.</span><span class="sxs-lookup"><span data-stu-id="a1222-106">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>

2.  <span data-ttu-id="a1222-107">Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="a1222-107">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="a1222-108">Для получения дополнительных сведений о различных методах, которые можно использовать для запуска панели управления Lync Server, ознакомьтесь со статьей [Open Lync server 2013 администрирование](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="a1222-108">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="a1222-109">В левой панели навигации щелкните **Response Groups** (Группы ответа), а затем **Workflow** (Рабочий процесс).</span><span class="sxs-lookup"><span data-stu-id="a1222-109">In the left navigation bar, click **Response Groups**, and then click **Workflow**.</span></span>

4.  <span data-ttu-id="a1222-110">На странице **Workflow** (Рабочий процесс) щелкните **Create or edit a workflow** (Создание или изменение рабочего процесса).</span><span class="sxs-lookup"><span data-stu-id="a1222-110">On the **Workflow** page, click **Create or edit a workflow**.</span></span>

5.  <span data-ttu-id="a1222-111">В поле поиска **Выбрать услугу** введите часть имени или полное имя службы **ApplicationServer**, где размещается рабочий процесс, который нужно удалить.</span><span class="sxs-lookup"><span data-stu-id="a1222-111">In the **Select a Service** search field, type part or all of the name of the **ApplicationServer** service that hosts the workflow that you want to delete.</span></span>

6.  <span data-ttu-id="a1222-112">В списке найденных служб выберите нужную и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="a1222-112">In the list of services, click the service that you want, and then click **OK**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="a1222-113">Откроется веб-страница средства настройки группы ответа.</span><span class="sxs-lookup"><span data-stu-id="a1222-113">The Response Group Configuration Tool webpage opens.</span></span> <span data-ttu-id="a1222-114">Вы также можете открыть веб-страницу средства настройки группы ответа непосредственно из веб-браузера, подключившись к <STRONG>https://&lt;вебпулфкдн&gt;/ргсконфиг</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="a1222-114">You can also open the Response Group Configuration Tool webpage directly from a web browser by connecting to <STRONG>https://&lt;webPoolFqdn&gt;/RgsConfig</STRONG>.</span></span>

    
    </div>

7.  <span data-ttu-id="a1222-115">В окне **Управление существующим рабочим процессом** найдите рабочий процесс, который нужно удалить, а затем в разделе **Действие** нажмите кнопку **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="a1222-115">Under **Manage an Existing Workflow**, locate the workflow you want to delete, and then under **Action**, click **Delete**.</span></span>

8.  <span data-ttu-id="a1222-116">Нажмите кнопку **Да**.</span><span class="sxs-lookup"><span data-stu-id="a1222-116">Click **Yes**.</span></span>

</div>

<div>

## <a name="to-use-windows-powershell-to-delete-a-workflow"></a><span data-ttu-id="a1222-117">Использование Windows PowerShell для удаления рабочего процесса</span><span class="sxs-lookup"><span data-stu-id="a1222-117">To use Windows PowerShell to delete a workflow</span></span>

1.  <span data-ttu-id="a1222-118">Выполните вход в качестве члена группы RTCUniversalServerAdmins или в качестве участника одной из предварительно заданных административных ролей, поддерживающих группу ответа.</span><span class="sxs-lookup"><span data-stu-id="a1222-118">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>

2.  <span data-ttu-id="a1222-119">Запустите командную консоль Lync Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Microsoft Lync Server 2013** и щелкните элемент **Командная консоль Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="a1222-119">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="a1222-120">В командной строке выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="a1222-120">At the command line, run:</span></span>
    
        Get-CsRgsWorkflow -Identity <Application Server service> -Name "<name of workflow>" | Remove-CsRgsWorkflow
    
    <span data-ttu-id="a1222-121">Пример:</span><span class="sxs-lookup"><span data-stu-id="a1222-121">For example:</span></span>
    
        Get-CsRgsWorkflow -Identity service:ApplicationServer:redmond.contoso.com -Name "Help Desk" | Remove-CsRgsWorkflow

</div>

</div>

<span> </span>

</div>

</div>

</div>

