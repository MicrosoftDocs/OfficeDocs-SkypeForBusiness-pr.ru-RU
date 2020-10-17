---
title: 'Lync Server 2013: удаление сетевых подсетей'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deleting network subnets
ms:assetid: c1850f38-40a3-48c9-b6f1-f181c5e63b6b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721873(v=OCS.15)
ms:contentKeyID: 49733806
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 013de3ae58424473aa42aee767982fd84a9d651e
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48504276"
---
# <a name="deleting-network-subnets-in-lync-server-2013"></a><span data-ttu-id="449c4-102">Удаление сетевых подсетей в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="449c4-102">Deleting network subnets in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="449c4-103">_**Последнее изменение темы:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="449c4-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="449c4-104">Для удаления подсети можно использовать следующую процедуру.</span><span class="sxs-lookup"><span data-stu-id="449c4-104">You can use the following procedure to delete a subnet.</span></span> <span data-ttu-id="449c4-105">С помощью панели управления Lync Server можно создавать, изменять и удалять подсеть.</span><span class="sxs-lookup"><span data-stu-id="449c4-105">From the Lync Server Control Panel, you can create, modify, or delete a network subnet.</span></span> <span data-ttu-id="449c4-106">Дополнительные сведения о создании или изменении подсетей сети приведены [в статье Создание или изменение подсетей сети в Lync Server 2013](lync-server-2013-create-or-modify-network-subnets.md).</span><span class="sxs-lookup"><span data-stu-id="449c4-106">For details on creating or modifying network subnets, see [Create or modify network subnets in Lync Server 2013](lync-server-2013-create-or-modify-network-subnets.md).</span></span>

<span data-ttu-id="449c4-107">В большинстве развертываний Microsoft Lync Server 2013, где реализован контроль допуска звонков (CAC), как правило, существует большое количество подсетей.</span><span class="sxs-lookup"><span data-stu-id="449c4-107">In most deployments of Microsoft Lync Server 2013 where call admission control (CAC) is implemented, there will typically be a large number of subnets.</span></span> <span data-ttu-id="449c4-108">Поэтому часто лучше настроить подсети из командной консоли Lync Server.</span><span class="sxs-lookup"><span data-stu-id="449c4-108">Because of this, it is often best to configure subnets from the Lync Server Management Shell.</span></span> <span data-ttu-id="449c4-109">Отсюда вы можете вызвать командлет **New-CsNetworkSubnet** в сочетании с командлетом Windows PowerShell **Import-CSV**.</span><span class="sxs-lookup"><span data-stu-id="449c4-109">From there you can call **New-CsNetworkSubnet** in conjunction with the Windows PowerShell cmdlet **Import-CSV**.</span></span> <span data-ttu-id="449c4-110">Используя эти командлеты, вы можете считывать параметры подсетей из файла данных с разделителями-запятыми  (CSV) и одновременно создавать несколько сетей.</span><span class="sxs-lookup"><span data-stu-id="449c4-110">By using these cmdlets together, you can read in subnet settings from a comma-separated values (.csv) file and create multiple subnets at the same time.</span></span> <span data-ttu-id="449c4-111">Примеры создания подсетей из CSV-файла см. в разделе [New-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet).</span><span class="sxs-lookup"><span data-stu-id="449c4-111">For examples of how to create subnets from a .csv file, see [New-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet).</span></span>

<div>

## <a name="to-delete-a-network-subnet"></a><span data-ttu-id="449c4-112">Удаление подсети</span><span class="sxs-lookup"><span data-stu-id="449c4-112">To delete a network subnet</span></span>

1.  <span data-ttu-id="449c4-113">Из учетной записи пользователя, которая является членом группы RTCUniversalServerAdmins (или имеет эквивалентные права пользователя) или назначается роли CsAdministrator, войдите на любой компьютер во внутреннем развертывании.</span><span class="sxs-lookup"><span data-stu-id="449c4-113">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="449c4-114">Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="449c4-114">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="449c4-115">Для получения дополнительных сведений о различных методах, которые можно использовать для запуска панели управления Lync Server, ознакомьтесь со статьей [Open Lync server 2013 администрирование](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="449c4-115">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="449c4-116">В левой панели навигации щелкните элемент **Конфигурация сети** и выберите элемент **Подсеть**.</span><span class="sxs-lookup"><span data-stu-id="449c4-116">In the left navigation bar, click **Network Configuration** and then click **Subnet**.</span></span>

4.  <span data-ttu-id="449c4-117">На странице **подсетей** щелкните подсеть, которую следует удалить.</span><span class="sxs-lookup"><span data-stu-id="449c4-117">On the **Subnet** page, click the subnet that you want to delete.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="449c4-p104">Можно одновременно удалять несколько подсетей. Для этого нажмите клавишу CTRL и выберите несколько подсетей, удерживая клавишу CTRL нажатой. Можно также выбрать все подсети, нажав пункт <STRONG>Выбрать все</STRONG> в меню <STRONG>Правка</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="449c4-p104">You can delete more than one subnet at a time. To do this, press CTRL and select multiple subnets while holding down the CTRL key. Or, to select all subnets, click <STRONG>Select all</STRONG> on the <STRONG>Edit</STRONG> menu.</span></span>

    
    </div>

5.  <span data-ttu-id="449c4-121">В меню **Правка** выберите команду **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="449c4-121">On the **Edit** menu, click **Delete**.</span></span>

6.  <span data-ttu-id="449c4-122">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="449c4-122">Click **OK**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="449c4-123">См. также</span><span class="sxs-lookup"><span data-stu-id="449c4-123">See Also</span></span>


[<span data-ttu-id="449c4-124">Создание или изменение сетевых подсетей в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="449c4-124">Create or modify network subnets in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-network-subnets.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

