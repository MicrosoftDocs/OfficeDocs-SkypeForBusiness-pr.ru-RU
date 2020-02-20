---
title: 'Lync Server 2013: удаление извещения'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delete an announcement
ms:assetid: 26ea7149-4470-4c22-9bab-8a4065aca44e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687998(v=OCS.15)
ms:contentKeyID: 49733588
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 66d10f53f89690a25860ba403ed7a8b21f7a1d4d
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42154791"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="delete-an-announcement-in-lync-server-2013"></a><span data-ttu-id="dfd07-102">Удаление объявления в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dfd07-102">Delete an announcement in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="dfd07-103">_**Последнее изменение темы:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="dfd07-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="dfd07-104">Используйте следующую процедуру для удаления оповещения о вызовах на неназначенные номера.</span><span class="sxs-lookup"><span data-stu-id="dfd07-104">Use the following procedure to delete an announcement that is used for calls to unassigned numbers.</span></span>

<div>

## <a name="to-delete-an-announcement"></a><span data-ttu-id="dfd07-105">Порядок удаления оповещения</span><span class="sxs-lookup"><span data-stu-id="dfd07-105">To delete an announcement</span></span>

1.  <span data-ttu-id="dfd07-106">Выполните вход на компьютер, на котором установлена командная консоль Lync Server, в качестве члена группы RTCUniversalServerAdmins или с необходимыми правами пользователя, как описано в разделе [Делегирование разрешений на установку в Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="dfd07-106">Log on to the computer where Lync Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="dfd07-107">Запустите командную консоль Lync Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Microsoft Lync Server 2013** и щелкните элемент **Командная консоль Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="dfd07-107">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="dfd07-p101">Получите список всех оповещений, используемых в организации. Выполните в командной строке следующую команду:</span><span class="sxs-lookup"><span data-stu-id="dfd07-p101">List all the announcements in your organization. At the command line, run:</span></span>
    
        Get-CsAnnouncement

4.  <span data-ttu-id="dfd07-p102">В полученном списке найдите оповещение, которое требуется удалить, и скопируйте его идентификатор GUID. Затем выполните в командной строке следующую команду:</span><span class="sxs-lookup"><span data-stu-id="dfd07-p102">In the resulting list, locate the announcement you want to delete, and copy the GUID. Then, at the command line, run:</span></span>
    
        Remove-CsAnnouncement -Identity "<Service:service ID/guid>" 
    
    <span data-ttu-id="dfd07-112">Пример:</span><span class="sxs-lookup"><span data-stu-id="dfd07-112">For example:</span></span>
    
        Remove-CsAnnouncement -Identity "ApplicationServer:Redmond.contoso.com/1951f734-c80f-4fb2-965d-51807c792b90"
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="dfd07-113">Дополнительные сведения о параметрах: <A href="https://docs.microsoft.com/powershell/module/skype/Get-CsAnnouncement">Get – ксаннаунцемент</A> и <A href="https://docs.microsoft.com/powershell/module/skype/Remove-CsAnnouncement">Remove — ксаннаунцемент</A>.</span><span class="sxs-lookup"><span data-stu-id="dfd07-113">For details about more options, see <A href="https://docs.microsoft.com/powershell/module/skype/Get-CsAnnouncement">Get-CsAnnouncement</A> and <A href="https://docs.microsoft.com/powershell/module/skype/Remove-CsAnnouncement">Remove-CsAnnouncement</A>.</span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="dfd07-114">См. также</span><span class="sxs-lookup"><span data-stu-id="dfd07-114">See Also</span></span>


[<span data-ttu-id="dfd07-115">Создание извещения в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dfd07-115">Create an announcement in Lync Server 2013</span></span>](lync-server-2013-create-an-announcement.md)  


[<span data-ttu-id="dfd07-116">Remove — Ксаннаунцемент</span><span class="sxs-lookup"><span data-stu-id="dfd07-116">Remove-CsAnnouncement</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsAnnouncement)  
[<span data-ttu-id="dfd07-117">Get — Ксаннаунцемент</span><span class="sxs-lookup"><span data-stu-id="dfd07-117">Get-CsAnnouncement</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsAnnouncement)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

