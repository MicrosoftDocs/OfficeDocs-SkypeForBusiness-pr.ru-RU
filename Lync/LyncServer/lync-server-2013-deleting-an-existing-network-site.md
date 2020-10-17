---
title: 'Lync Server 2013: удаление существующего сетевого сайта'
description: 'Lync Server 2013: удаление существующего сетевого сайта.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deleting an existing network site
ms:assetid: 2762149b-3572-4513-b838-beda7fa9e81e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688001(v=OCS.15)
ms:contentKeyID: 49733589
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7cef4774ee71aaf6851757d5b88d30138fc34997
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48551075"
---
# <a name="deleting-an-existing-network-site-in-lync-server-2013"></a><span data-ttu-id="99860-103">Удаление существующего сетевого сайта в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="99860-103">Deleting an existing network site in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="99860-104">_**Последнее изменение темы:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="99860-104">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="99860-105">Сетевые узлы — это офисы или места, настроенные в каждой области развертывания контроля допуска звонков (CAC) или Enhanced 9-1-1.</span><span class="sxs-lookup"><span data-stu-id="99860-105">Network sites are the offices or locations configured within each region of a call admission control (CAC) or Enhanced 9-1-1 deployment.</span></span> <span data-ttu-id="99860-106">С помощью панели управления Lync Server 2013 можно настраивать сайты и связывать их с областями.</span><span class="sxs-lookup"><span data-stu-id="99860-106">You can use the Lync Server 2013 Control Panel to configure sites and associate them with regions.</span></span> <span data-ttu-id="99860-107">Например, сетевую область для Северной Америки можно связать с такими сетевыми узлами, как Чикаго, Редмонд и Ванкувер.</span><span class="sxs-lookup"><span data-stu-id="99860-107">For example, a network region for North America might be associated with networks sites such as Chicago, Redmond, and Vancouver.</span></span> <span data-ttu-id="99860-108">Сетевой узел CAC необходимо создать для каждого узла в организации, даже если у этого узла нет ограничений по пропускной способности.</span><span class="sxs-lookup"><span data-stu-id="99860-108">A CAC network site must be created for every site within an organization, even if that site has no bandwidth limitations.</span></span> <span data-ttu-id="99860-109">С помощью панели управления Lync Server вы можете создавать, изменять и удалять сетевые сайты.</span><span class="sxs-lookup"><span data-stu-id="99860-109">From the Lync Server Control Panel you can create, modify, and delete network sites.</span></span> <span data-ttu-id="99860-110">Используйте следующую процедуру для удаления существующего сетевого сайта.</span><span class="sxs-lookup"><span data-stu-id="99860-110">Use the following procedure to delete an existing network site.</span></span> <span data-ttu-id="99860-111">Дополнительные сведения о создании или изменении сетевых сайтов можно найти [в статье Создание или изменение сетевых сайтов в Lync Server 2013](lync-server-2013-creating-or-modifying-network-sites.md)</span><span class="sxs-lookup"><span data-stu-id="99860-111">For details about creating or modifying network sites, see [Creating or modifying network sites in Lync Server 2013](lync-server-2013-creating-or-modifying-network-sites.md)</span></span>

<div>

## <a name="to-delete-a-network-site"></a><span data-ttu-id="99860-112">Удаление сетевого узла</span><span class="sxs-lookup"><span data-stu-id="99860-112">To delete a network site</span></span>

1.  <span data-ttu-id="99860-113">Из учетной записи пользователя, которая является членом группы RTCUniversalServerAdmins (или имеет эквивалентные права пользователя) или назначается роли CsAdministrator, войдите на любой компьютер во внутреннем развертывании.</span><span class="sxs-lookup"><span data-stu-id="99860-113">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="99860-114">Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="99860-114">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="99860-115">Для получения дополнительных сведений о различных методах, которые можно использовать для запуска панели управления Lync Server, ознакомьтесь со статьей [Open Lync server 2013 администрирование](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="99860-115">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="99860-116">В левой панели навигации щелкните **Конфигурация сети**, а затем щелкните **Узел**.</span><span class="sxs-lookup"><span data-stu-id="99860-116">In the left navigation bar, click **Network Configuration** and then click **Site**.</span></span>

4.  <span data-ttu-id="99860-117">На странице **Узел** щелкните узел, который требуется удалить.</span><span class="sxs-lookup"><span data-stu-id="99860-117">On the **Site** page, click the site that you want to delete.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="99860-p103">Вы можете удалить несколько узлов за раз. Для этого нажмите клавишу CTRL и выберите несколько узлов, удерживая клавишу CTRL нажатой. Или, чтобы выбрать все узлы, щелкните <STRONG>Выбрать все</STRONG> в меню <STRONG>Правка</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="99860-p103">You can delete more than one site at a time. To do this, press CTRL and select multiple sites while holding down the CTRL key. Or, to select all sites, click <STRONG>Select all</STRONG> on the <STRONG>Edit</STRONG> menu.</span></span>

    
    </div>

5.  <span data-ttu-id="99860-121">В меню **Правка** выберите команду **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="99860-121">On the **Edit** menu, click **Delete**.</span></span>

6.  <span data-ttu-id="99860-122">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="99860-122">Click **OK**.</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="99860-p104">Сетевой сайт нельзя удалить, если он связан с подсетью. При попытке удаления сайта, связанного с подсетью, появится сообщение об ошибке. Чтобы проверить, связан ли сайт с подсетями, щелкните сайт и выберите <STRONG>Подробнее</STRONG> в меню <STRONG>Изменить</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="99860-p104">You cannot remove a network site if it is associated with a network subnet. If you attempt to remove a site associated with a subnet you will receive an error message. To see if a site is associated with any subnets, click the site and then click <STRONG>Show details</STRONG> on the <STRONG>Edit</STRONG> menu.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

