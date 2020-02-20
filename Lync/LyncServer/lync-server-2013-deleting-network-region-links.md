---
title: 'Lync Server 2013: удаление связей между сетевыми областями'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deleting network region links
ms:assetid: 839273cd-d23f-4b38-84e6-d2dc972f49cd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688114(v=OCS.15)
ms:contentKeyID: 49733712
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8587e0a07e4e6bdb0e2231d557e0d475152daa16
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42146152"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deleting-network-region-links-in-lync-server-2013"></a><span data-ttu-id="97296-102">Удаление связей между областями сети в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="97296-102">Deleting network region links in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="97296-103">_**Последнее изменение темы:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="97296-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="97296-104">Вы можете настроить канал между двумя областями сети как часть контроля допуска звонков (CAC).</span><span class="sxs-lookup"><span data-stu-id="97296-104">You can configure links between two network regions as part of call admission control (CAC).</span></span> <span data-ttu-id="97296-105">Регионы в сети связываются с помощью физического подключения глобальной сети.</span><span class="sxs-lookup"><span data-stu-id="97296-105">Regions within a network are linked through physical wide area network (WAN) connectivity.</span></span> <span data-ttu-id="97296-106">Вы можете удалить существующую ссылку между двумя областями сети с помощью панели управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="97296-106">You can use the Lync Server Control Panel to delete an existing link between two network regions.</span></span> <span data-ttu-id="97296-107">Дополнительные сведения о создании или изменении связи между областями сети см [в разделе Настройка связей между областями сети в Lync Server 2013](lync-server-2013-configuring-network-region-links.md)</span><span class="sxs-lookup"><span data-stu-id="97296-107">For details about creating or modifying network region link, see [Configuring network region links in Lync Server 2013](lync-server-2013-configuring-network-region-links.md)</span></span>

<div>

## <a name="to-delete-a-network-region-link"></a><span data-ttu-id="97296-108">Удаление канала области сети</span><span class="sxs-lookup"><span data-stu-id="97296-108">To delete a network region link</span></span>

1.  <span data-ttu-id="97296-109">Из учетной записи пользователя, которая является членом группы RTCUniversalServerAdmins (или имеет эквивалентные права пользователя) или назначается роли CsAdministrator, войдите на любой компьютер во внутреннем развертывании.</span><span class="sxs-lookup"><span data-stu-id="97296-109">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="97296-110">Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="97296-110">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="97296-111">Для получения дополнительных сведений о различных методах, которые можно использовать для запуска панели управления Lync Server, ознакомьтесь со статьей [Open Lync server 2013 администрирование](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="97296-111">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="97296-112">В левой панели навигации щелкните **Конфигурация сети**, а затем щелкните **Связь между областями**.</span><span class="sxs-lookup"><span data-stu-id="97296-112">In the left navigation bar, click **Network Configuration** and then click **Region Link**.</span></span>

4.  <span data-ttu-id="97296-113">На странице **Канал области** щелкните канал области, который нужно удалить.</span><span class="sxs-lookup"><span data-stu-id="97296-113">On the **Region Link** page, click the region link that you want to delete.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="97296-p103">За один раз вы можете удалить несколько каналов. Для этого нажмите клавишу CTRL и, удерживая ее, выберите несколько каналов. Чтобы выбрать все каналы, щелкните пункт <STRONG>Выбрать все</STRONG> в меню <STRONG>Правка</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="97296-p103">You can delete more than one region link at a time. To do this, press CTRL and select multiple region links while holding down the CTRL key. Or, to select all region links, click <STRONG>Select all</STRONG> on the <STRONG>Edit</STRONG> menu.</span></span>

    
    </div>

5.  <span data-ttu-id="97296-117">В меню **Правка** щелкните пункт **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="97296-117">From the **Edit** menu, select **Delete**.</span></span>

6.  <span data-ttu-id="97296-118">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="97296-118">Click **OK**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="97296-119">См. также</span><span class="sxs-lookup"><span data-stu-id="97296-119">See Also</span></span>


[<span data-ttu-id="97296-120">Настройка связей между областями сети в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="97296-120">Configuring network region links in Lync Server 2013</span></span>](lync-server-2013-configuring-network-region-links.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

