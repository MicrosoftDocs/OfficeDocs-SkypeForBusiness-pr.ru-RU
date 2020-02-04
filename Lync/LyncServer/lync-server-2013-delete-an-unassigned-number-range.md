---
title: 'Lync Server 2013: удаление неназначенного диапазона номеров'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delete an unassigned number range
ms:assetid: a8141bfb-b94d-4d0f-a7a9-2e60d10b103a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182565(v=OCS.15)
ms:contentKeyID: 48185090
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0a80a28cf4ee5b310790a057253ea52ca17a14aa
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41734239"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="delete-an-unassigned-number-range-in-lync-server-2013"></a><span data-ttu-id="6e0b1-102">Удаление неназначенного диапазона номеров в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6e0b1-102">Delete an unassigned number range in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6e0b1-103">_**Тема последнего изменения:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="6e0b1-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="6e0b1-104">Чтобы удалить неназначенный диапазон номеров для объявлений, выполните одно из указанных ниже действий.</span><span class="sxs-lookup"><span data-stu-id="6e0b1-104">Use one of the following procedures to delete an unassigned number range for Announcements.</span></span>

<div>

## <a name="to-use-lync-server-control-panel-to-delete-an-unassigned-number-range"></a><span data-ttu-id="6e0b1-105">Удаление неназначенного диапазона номеров с помощью панели управления Lync Server</span><span class="sxs-lookup"><span data-stu-id="6e0b1-105">To use Lync Server Control Panel to delete an unassigned number range</span></span>

1.  <span data-ttu-id="6e0b1-106">Войдите на компьютер как член группы RTCUniversalServerAdmins или роли CsVoiceAdministrator, CsServerAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="6e0b1-106">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="6e0b1-107">Дополнительные сведения можно найти [в разделе Делегирование разрешений на настройку в Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="6e0b1-107">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="6e0b1-108">Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="6e0b1-108">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="6e0b1-109">Дополнительные сведения о различных способах, которые можно использовать для запуска панели управления Lync Server, приведены в разделе [Открытие меню администрирования Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="6e0b1-109">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="6e0b1-110">В левой области навигации щелкните **Функции голосовой связи**, затем **Неназначенный номер**.</span><span class="sxs-lookup"><span data-stu-id="6e0b1-110">In the left navigation bar, click **Voice Features** and then click **Unassigned Number**.</span></span>

4.  <span data-ttu-id="6e0b1-111">На странице **Неназначенный номер** полностью или частично введите в поле поиска имя диапазона неназначенных номеров, который требуется удалить.</span><span class="sxs-lookup"><span data-stu-id="6e0b1-111">On the **Unassigned Number** page, in the search field, type all or part of the name of the unassigned number range you want to delete.</span></span>

5.  <span data-ttu-id="6e0b1-112">В сформированном списке диапазонов номеров выберите требуемое имя и щелкните **Изменить**, затем **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="6e0b1-112">In the resulting list of number ranges, click the name, click **Edit**, and then click **Delete**.</span></span>

6.  <span data-ttu-id="6e0b1-113">Щелкните **Сохранить все**.</span><span class="sxs-lookup"><span data-stu-id="6e0b1-113">Click **Commit all**.</span></span>

</div>

<div>

## <a name="to-use-windows-powershell-to-delete-an-unassigned-number-range"></a><span data-ttu-id="6e0b1-114">Удаление неназначенного числового диапазона с помощью Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="6e0b1-114">To use Windows PowerShell to delete an unassigned number range</span></span>

1.  <span data-ttu-id="6e0b1-115">Войдите на компьютер, на котором установлена командная консоль Lync Server Management Shell, в группу Рткуниверсалсерверадминс или с необходимыми правами пользователя, как описано в разделе [Делегирование разрешений на настройку в Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="6e0b1-115">Log on to the computer where Lync Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="6e0b1-116">Запустите командную консоль Lync Server Management Shell: нажмите кнопку **Пуск**, выберите **все программы**, а затем — **Microsoft Lync Server 2013**, а затем — **Командная консоль Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="6e0b1-116">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="6e0b1-117">В командной строке введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="6e0b1-117">At the command line, type:</span></span>
    
        Remove-CsUnassignedNumber -Identity "<name of unassigned number range>" 
    
    <span data-ttu-id="6e0b1-118">Например:</span><span class="sxs-lookup"><span data-stu-id="6e0b1-118">For example:</span></span>
    
        Remove-CsUnassignedNumber -Identity "Unassigned range 1"
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="6e0b1-119">Подробнее о дополнительных параметрах можно найти в разделе <A href="https://docs.microsoft.com/powershell/module/skype/Remove-CsCallParkOrbit">Remove-кскаллпаркорбит</A>.</span><span class="sxs-lookup"><span data-stu-id="6e0b1-119">For details about more options, see <A href="https://docs.microsoft.com/powershell/module/skype/Remove-CsCallParkOrbit">Remove-CsCallParkOrbit</A>.</span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="6e0b1-120">См. также</span><span class="sxs-lookup"><span data-stu-id="6e0b1-120">See Also</span></span>


[<span data-ttu-id="6e0b1-121">Создание и изменение неназначенного диапазона номеров в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6e0b1-121">Create or modify an unassigned number range in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-an-unassigned-number-range.md)  


[<span data-ttu-id="6e0b1-122">Remove-CsUnassignedNumber</span><span class="sxs-lookup"><span data-stu-id="6e0b1-122">Remove-CsUnassignedNumber</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsUnassignedNumber)  
[<span data-ttu-id="6e0b1-123">Get-CsUnassignedNumber</span><span class="sxs-lookup"><span data-stu-id="6e0b1-123">Get-CsUnassignedNumber</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsUnassignedNumber)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

