---
title: 'Lync Server 2013: удаление ссылок на сетевой регион'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deleting network region links
ms:assetid: 839273cd-d23f-4b38-84e6-d2dc972f49cd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688114(v=OCS.15)
ms:contentKeyID: 49733712
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a097626f6e5eb5de8e3503baab0f1ab9ce462549
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34834582"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deleting-network-region-links-in-lync-server-2013"></a><span data-ttu-id="c5664-102">Удаление ссылок на сетевой регион в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c5664-102">Deleting network region links in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c5664-103">_**Тема последнего изменения:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="c5664-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="c5664-104">Вы можете настроить связи между двумя сетевыми областями в рамках управления допуском звонков (CAC).</span><span class="sxs-lookup"><span data-stu-id="c5664-104">You can configure links between two network regions as part of call admission control (CAC).</span></span> <span data-ttu-id="c5664-105">Регионы в сети связаны по ГЛОБАЛЬным сетевым подключениям.</span><span class="sxs-lookup"><span data-stu-id="c5664-105">Regions within a network are linked through physical wide area network (WAN) connectivity.</span></span> <span data-ttu-id="c5664-106">Вы можете удалить существующую связь между двумя сетевыми областями с помощью панели управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="c5664-106">You can use the Lync Server Control Panel to delete an existing link between two network regions.</span></span> <span data-ttu-id="c5664-107">Дополнительные сведения о создании и изменении ссылки на сетевой регион можно найти [в разделе Настройка ссылок на сетевой регион в Lync Server 2013](lync-server-2013-configuring-network-region-links.md)</span><span class="sxs-lookup"><span data-stu-id="c5664-107">For details about creating or modifying network region link, see [Configuring network region links in Lync Server 2013](lync-server-2013-configuring-network-region-links.md)</span></span>

<div>

## <a name="to-delete-a-network-region-link"></a><span data-ttu-id="c5664-108">Удаление ссылки на сетевой регион</span><span class="sxs-lookup"><span data-stu-id="c5664-108">To delete a network region link</span></span>

1.  <span data-ttu-id="c5664-109">Войдите на любой компьютер, находящийся во внутреннем развертывании, с использованием учетной записи, входящей в группу RTCUniversalServerAdmins (или имеющей равнозначные права пользователя) либо назначенной роли CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="c5664-109">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="c5664-110">Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="c5664-110">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="c5664-111">Дополнительные сведения о различных способах, которые можно использовать для запуска панели управления Lync Server, приведены в разделе [Открытие меню администрирования Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="c5664-111">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="c5664-112">На панели навигации слева выберите пункт **Настройка сети** , а затем щелкните **ссылку Region (регион**).</span><span class="sxs-lookup"><span data-stu-id="c5664-112">In the left navigation bar, click **Network Configuration** and then click **Region Link**.</span></span>

4.  <span data-ttu-id="c5664-113">На странице " **ссылка на регион** " щелкните ссылку "регион", которую вы хотите удалить.</span><span class="sxs-lookup"><span data-stu-id="c5664-113">On the **Region Link** page, click the region link that you want to delete.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="c5664-114">Вы можете удалить несколько ссылок на регион за один раз.</span><span class="sxs-lookup"><span data-stu-id="c5664-114">You can delete more than one region link at a time.</span></span> <span data-ttu-id="c5664-115">Для этого нажмите клавишу CTRL и, удерживая нажатой клавишу CTRL, щелкните ссылки несколько областей.</span><span class="sxs-lookup"><span data-stu-id="c5664-115">To do this, press CTRL and select multiple region links while holding down the CTRL key.</span></span> <span data-ttu-id="c5664-116">Кроме того, чтобы выделить все ссылки на регион, в меню <STRONG>Правка</STRONG> выберите команду <STRONG>выделить все</STRONG> .</span><span class="sxs-lookup"><span data-stu-id="c5664-116">Or, to select all region links, click <STRONG>Select all</STRONG> on the <STRONG>Edit</STRONG> menu.</span></span>

    
    </div>

5.  <span data-ttu-id="c5664-117">В меню **Правка** выберите команду **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="c5664-117">From the **Edit** menu, select **Delete**.</span></span>

6.  <span data-ttu-id="c5664-118">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="c5664-118">Click **OK**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="c5664-119">См. также</span><span class="sxs-lookup"><span data-stu-id="c5664-119">See Also</span></span>


[<span data-ttu-id="c5664-120">Настройка ссылок на сетевой регион в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c5664-120">Configuring network region links in Lync Server 2013</span></span>](lync-server-2013-configuring-network-region-links.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

