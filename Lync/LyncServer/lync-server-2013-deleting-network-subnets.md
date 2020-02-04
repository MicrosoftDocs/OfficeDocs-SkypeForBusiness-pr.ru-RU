---
title: 'Lync Server 2013: удаление подсетей сети'
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
ms.openlocfilehash: 0c87ca1cfd91344d8f8cbb0b320c70def47bf5ac
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41740969"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deleting-network-subnets-in-lync-server-2013"></a><span data-ttu-id="8c788-102">Удаление подсетей сети в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8c788-102">Deleting network subnets in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8c788-103">_**Тема последнего изменения:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="8c788-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="8c788-104">Для удаления подсети вы можете использовать описанную ниже процедуру.</span><span class="sxs-lookup"><span data-stu-id="8c788-104">You can use the following procedure to delete a subnet.</span></span> <span data-ttu-id="8c788-105">С помощью панели управления Lync Server вы можете создавать, изменять и удалять сетевые подсети.</span><span class="sxs-lookup"><span data-stu-id="8c788-105">From the Lync Server Control Panel, you can create, modify, or delete a network subnet.</span></span> <span data-ttu-id="8c788-106">Сведения о создании и изменении подсетей сети можно найти [в разделе Создание или изменение подсетей сети в Lync Server 2013](lync-server-2013-create-or-modify-network-subnets.md).</span><span class="sxs-lookup"><span data-stu-id="8c788-106">For details on creating or modifying network subnets, see [Create or modify network subnets in Lync Server 2013](lync-server-2013-create-or-modify-network-subnets.md).</span></span>

<span data-ttu-id="8c788-107">В большинстве развертываний Microsoft Lync Server 2013 там, где реализовано управление допуском звонков (CAC), обычно это большое количество подсетей.</span><span class="sxs-lookup"><span data-stu-id="8c788-107">In most deployments of Microsoft Lync Server 2013 where call admission control (CAC) is implemented, there will typically be a large number of subnets.</span></span> <span data-ttu-id="8c788-108">По этой причине лучше всего настроить подсети из командной консоли Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="8c788-108">Because of this, it is often best to configure subnets from the Lync Server Management Shell.</span></span> <span data-ttu-id="8c788-109">Из него вы можете вызвать **New-кснетворксубнет** в сочетании с командлетом Windows PowerShell **Import-CSV**.</span><span class="sxs-lookup"><span data-stu-id="8c788-109">From there you can call **New-CsNetworkSubnet** in conjunction with the Windows PowerShell cmdlet **Import-CSV**.</span></span> <span data-ttu-id="8c788-110">Используя эти командлеты вместе, вы можете прочитать параметры подсети из CSV-файла и одновременно создать несколько подсетей.</span><span class="sxs-lookup"><span data-stu-id="8c788-110">By using these cmdlets together, you can read in subnet settings from a comma-separated values (.csv) file and create multiple subnets at the same time.</span></span> <span data-ttu-id="8c788-111">Примеры создания подсетей из CSV-файла можно найти в разделе [New-кснетворксубнет](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet).</span><span class="sxs-lookup"><span data-stu-id="8c788-111">For examples of how to create subnets from a .csv file, see [New-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet).</span></span>

<div>

## <a name="to-delete-a-network-subnet"></a><span data-ttu-id="8c788-112">Удаление сетевой подсети</span><span class="sxs-lookup"><span data-stu-id="8c788-112">To delete a network subnet</span></span>

1.  <span data-ttu-id="8c788-113">Войдите на любой компьютер, находящийся во внутреннем развертывании, с использованием учетной записи, входящей в группу RTCUniversalServerAdmins (или имеющей равнозначные права пользователя) либо назначенной роли CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="8c788-113">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="8c788-114">Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="8c788-114">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="8c788-115">Дополнительные сведения о различных способах, которые можно использовать для запуска панели управления Lync Server, приведены в разделе [Открытие меню администрирования Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="8c788-115">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="8c788-116">На панели навигации слева выберите пункт **Настройка сети** , а затем — **подсеть**.</span><span class="sxs-lookup"><span data-stu-id="8c788-116">In the left navigation bar, click **Network Configuration** and then click **Subnet**.</span></span>

4.  <span data-ttu-id="8c788-117">На странице **Subnet (подсеть** ) выберите подсеть, которую вы хотите удалить.</span><span class="sxs-lookup"><span data-stu-id="8c788-117">On the **Subnet** page, click the subnet that you want to delete.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="8c788-118">Вы можете удалить более одной подсети за один раз.</span><span class="sxs-lookup"><span data-stu-id="8c788-118">You can delete more than one subnet at a time.</span></span> <span data-ttu-id="8c788-119">Для этого нажмите клавишу CTRL и выберите несколько подсетей, удерживая нажатой клавишу CTRL.</span><span class="sxs-lookup"><span data-stu-id="8c788-119">To do this, press CTRL and select multiple subnets while holding down the CTRL key.</span></span> <span data-ttu-id="8c788-120">Кроме того, чтобы выбрать все подсети, в меню <STRONG>Правка</STRONG> выберите команду <STRONG>выделить все</STRONG> .</span><span class="sxs-lookup"><span data-stu-id="8c788-120">Or, to select all subnets, click <STRONG>Select all</STRONG> on the <STRONG>Edit</STRONG> menu.</span></span>

    
    </div>

5.  <span data-ttu-id="8c788-121">В меню **Правка** выберите команду **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="8c788-121">On the **Edit** menu, click **Delete**.</span></span>

6.  <span data-ttu-id="8c788-122">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="8c788-122">Click **OK**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="8c788-123">См. также</span><span class="sxs-lookup"><span data-stu-id="8c788-123">See Also</span></span>


[<span data-ttu-id="8c788-124">Создание и изменение подсетей сети в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8c788-124">Create or modify network subnets in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-network-subnets.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

