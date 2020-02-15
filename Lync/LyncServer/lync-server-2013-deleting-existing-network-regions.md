---
title: 'Lync Server 2013: удаление существующих областей сети'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deleting existing network regions
ms:assetid: c7293a2f-2b49-4c4a-903f-f7edcea2bc5f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721882(v=OCS.15)
ms:contentKeyID: 49733815
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 664eea747c9cea637b86377760f30c59bb21e7e7
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42042921"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deleting-existing-network-regions-in-lync-server-2013"></a><span data-ttu-id="d61d0-102">Удаление существующих областей сети в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d61d0-102">Deleting existing network regions in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d61d0-103">_**Последнее изменение темы:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="d61d0-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="d61d0-104">Область сети связывает части сети, расположенные в различных географических районах.</span><span class="sxs-lookup"><span data-stu-id="d61d0-104">A network region interconnects various parts of a network across multiple geographic areas.</span></span> <span data-ttu-id="d61d0-105">Каждый регион сети должен быть связан с центральным сайтом.</span><span class="sxs-lookup"><span data-stu-id="d61d0-105">Every network region must be associated with a central site.</span></span> <span data-ttu-id="d61d0-106">Центральный сайт — это сайт центра обработки данных, на котором выполняется служба политики пропускной способности для контроля допуска звонков.</span><span class="sxs-lookup"><span data-stu-id="d61d0-106">The central site is the data center site on which the call admission control (CAC) bandwidth policy service is running.</span></span> <span data-ttu-id="d61d0-107">Для настройки областей сети можно использовать панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="d61d0-107">You can use Lync Server Control Panel to configure network regions.</span></span> <span data-ttu-id="d61d0-108">Области сети включают параметры, которые определяют, разрешены ли альтернативные пути через Интернет для аудио- и видеоподключений.</span><span class="sxs-lookup"><span data-stu-id="d61d0-108">Network regions include settings that determine whether alternate paths through the Internet are allowed for audio and video connections.</span></span> <span data-ttu-id="d61d0-109">С помощью панели управления Lync Server можно создавать, изменять и удалять области сети.</span><span class="sxs-lookup"><span data-stu-id="d61d0-109">From the Lync Server Control Panel, you can create, modify, or delete a network region.</span></span> <span data-ttu-id="d61d0-110">Используйте этот раздел для удаления существующих областей сети.</span><span class="sxs-lookup"><span data-stu-id="d61d0-110">Use this topic to delete existing network regions.</span></span> <span data-ttu-id="d61d0-111">Сведения о создании или изменении существующих областей сети приведены в статье [Создание или изменение областей сети в Lync Server 2013](lync-server-2013-creating-or-modifying-network-regions.md).</span><span class="sxs-lookup"><span data-stu-id="d61d0-111">For details about creating or modifying existing network regions, see [Creating or modifying network regions in Lync Server 2013](lync-server-2013-creating-or-modifying-network-regions.md).</span></span>

<div>

## <a name="to-delete-a-network-region"></a><span data-ttu-id="d61d0-112">Удаление области сети</span><span class="sxs-lookup"><span data-stu-id="d61d0-112">To delete a network region</span></span>

1.  <span data-ttu-id="d61d0-113">Из учетной записи пользователя, которая является членом группы RTCUniversalServerAdmins (или имеет эквивалентные права пользователя) или назначается роли CsAdministrator, войдите на любой компьютер во внутреннем развертывании.</span><span class="sxs-lookup"><span data-stu-id="d61d0-113">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="d61d0-114">Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="d61d0-114">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="d61d0-115">Для получения дополнительных сведений о различных методах, которые можно использовать для запуска панели управления Lync Server, ознакомьтесь со статьей [Open Lync server 2013 администрирование](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="d61d0-115">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="d61d0-116">В левой панели навигации щелкните элемент **Конфигурация сети** и выберите элемент **Область**.</span><span class="sxs-lookup"><span data-stu-id="d61d0-116">In the left navigation bar, click **Network Configuration** and then click **Region**.</span></span>

4.  <span data-ttu-id="d61d0-117">На странице **областей** щелкните область, которую следует удалить.</span><span class="sxs-lookup"><span data-stu-id="d61d0-117">On the **Region** page, click the region you want to delete.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="d61d0-p103">Можно одновременно удалять несколько областей. Для этого нажмите клавишу CTRL и выберите несколько областей, удерживая клавишу CTRL нажатой. Можно также выбрать все области, нажав пункт <STRONG>Выбрать все</STRONG> в меню <STRONG>Правка</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="d61d0-p103">You can delete more than one region at a time. To do this, press CTRL and select multiple regions while holding down the CTRL key. Or, to select all regions, click <STRONG>Select all</STRONG> on the <STRONG>Edit</STRONG> menu.</span></span>

    
    </div>

5.  <span data-ttu-id="d61d0-121">В меню **Правка** выберите команду **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="d61d0-121">On the **Edit** menu, click **Delete**.</span></span>

6.  <span data-ttu-id="d61d0-122">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="d61d0-122">Click **OK**.</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="d61d0-p104">Нельзя удалить область сети, если она связана с сетевым сайтом. При попытке удалить область, связанную с сайтом, отображается сообщение об ошибке. Чтобы увидеть, связана ли область с какими-либо сайтами, выделите эту область и выберите команду <STRONG>Показать подробности</STRONG> в меню <STRONG>Правка</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="d61d0-p104">A network region cannot be removed if it is associated with a network site. If you attempt to remove a region associated with a site you will receive an error message. To see if a region is associated with any sites, select the region and then click <STRONG>Show details</STRONG> on the <STRONG>Edit</STRONG> menu.</span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="d61d0-126">См. также</span><span class="sxs-lookup"><span data-stu-id="d61d0-126">See Also</span></span>


[<span data-ttu-id="d61d0-127">Создание или изменение областей сети в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d61d0-127">Creating or modifying network regions in Lync Server 2013</span></span>](lync-server-2013-creating-or-modifying-network-regions.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

