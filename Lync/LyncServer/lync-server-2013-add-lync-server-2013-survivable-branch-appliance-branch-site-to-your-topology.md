---
title: Добавление в топологию сайта филиала устройства для обеспечения связи в филиалах Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Add Lync Server 2013 Survivable Branch Appliance branch site to your topology
ms:assetid: d3142a37-4606-456d-8ea9-6cc0e51e55f3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721896(v=OCS.15)
ms:contentKeyID: 49733830
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b4fc2dd7426006d0c8f19b38b85ba778744fff2e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41735019"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="add-lync-server-2013-survivable-branch-appliance-branch-site-to-your-topology"></a><span data-ttu-id="a890b-102">Добавление в топологию сайта филиала устройства для обеспечения связи в филиалах Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a890b-102">Add Lync Server 2013 Survivable Branch Appliance branch site to your topology</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a890b-103">_**Тема последнего изменения:** 2012-10-07_</span><span class="sxs-lookup"><span data-stu-id="a890b-103">_**Topic Last Modified:** 2012-10-07_</span></span>

<span data-ttu-id="a890b-104">Microsoft Lync Server 2013 (СБА) не может быть связан с пулом переднего плана Microsoft Lync Server 2010 в качестве регистратора резервных копий.</span><span class="sxs-lookup"><span data-stu-id="a890b-104">Microsoft Lync Server 2013 Survivable Branch Appliances (SBA) cannot be associated to a Microsoft Lync Server 2010 Front End pool as a backup Registrar.</span></span> <span data-ttu-id="a890b-105">СБА должен быть связан с пулом внешних интерфейсов Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a890b-105">The SBA must be associated with a Microsoft Lync Server 2013 Front End pool.</span></span> <span data-ttu-id="a890b-106">Эти действия предполагают наличие Microsoft Lync Server 2013 СБА.</span><span class="sxs-lookup"><span data-stu-id="a890b-106">These steps assume a Microsoft Lync Server 2013 SBA.</span></span> <span data-ttu-id="a890b-107">Выполните эту процедуру на центральном веб-сайте.</span><span class="sxs-lookup"><span data-stu-id="a890b-107">Perform this procedure at the central site.</span></span>

<div>

## <a name="to-add-branch-sites-with-microsoft-lync-server-2013-sba-to-your-topology"></a><span data-ttu-id="a890b-108">Добавление сайтов филиалов с Microsoft Lync Server 2013 СБА в топологию</span><span class="sxs-lookup"><span data-stu-id="a890b-108">To add branch sites with Microsoft Lync Server 2013 SBA to your topology</span></span>

1.  <span data-ttu-id="a890b-109">Запустить построитель топологии: нажмите кнопку **Пуск**, выберите пункт **все программы**, а затем — **Microsoft Lync Server 2013**и нажмите кнопку **Построитель топологии Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="a890b-109">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="a890b-110">В дереве консоли разверните узел центрального сайта, разверните узел **сайты филиалов**и выберите пункт **создать сайт филиала**.</span><span class="sxs-lookup"><span data-stu-id="a890b-110">In the console tree, expand the central site, expand **Branch Sites**, and then click **New Branch Site**.</span></span>

3.  <span data-ttu-id="a890b-111">В диалоговом окне **Определение нового сайта ветви** щелкните **имя**и введите имя для нового сайта ветви.</span><span class="sxs-lookup"><span data-stu-id="a890b-111">In the **Define New Branch Site** dialog box, click **Name**, and then type a name for the new branch site.</span></span>

4.  <span data-ttu-id="a890b-112">Необязательно Нажмите кнопку **Описание**и введите понятное описание сайта филиала.</span><span class="sxs-lookup"><span data-stu-id="a890b-112">(Optional) Click **Description**, and then type a meaningful description for the branch site.</span></span>

5.  <span data-ttu-id="a890b-113">Нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="a890b-113">Click **Next**.</span></span>

6.  <span data-ttu-id="a890b-114">Необязательно В диалоговом окне **Определение нового сайта ветви** выполните одно из указанных ниже действий.</span><span class="sxs-lookup"><span data-stu-id="a890b-114">(Optional) In the next **Define New Branch Site** dialog box, do any of the following:</span></span>
    
      - <span data-ttu-id="a890b-115">Щелкните **город**и введите имя города, в котором находится сайт филиала.</span><span class="sxs-lookup"><span data-stu-id="a890b-115">Click **City**, and then type the name of the city in which the branch site is located.</span></span>
    
      - <span data-ttu-id="a890b-116">Щелкните область или **регион**, а затем введите имя состояния или региона, в котором находится сайт филиала.</span><span class="sxs-lookup"><span data-stu-id="a890b-116">Click **State/Region**, and then type the name of the state or region in which the branch site is located.</span></span>
    
      - <span data-ttu-id="a890b-117">Щелкните **код страны**, а затем введите четырехзначный код звонка для страны или региона, в котором расположен сайт филиала.</span><span class="sxs-lookup"><span data-stu-id="a890b-117">Click **Country Code**, and then type the two-digit calling code for the country/region in which the branch site is located.</span></span>

7.  <span data-ttu-id="a890b-118">Нажмите кнопку **Далее**, а затем выполните одно из указанных ниже действий.</span><span class="sxs-lookup"><span data-stu-id="a890b-118">Click **Next**, and then do one of the following:</span></span>
    
      - <span data-ttu-id="a890b-119">Если вы используете работающее работающее устройство филиала или его временный сервер филиала на этом сайте, убедитесь, что установлен флажок **открыть новый бесперебойный мастер при закрытом окне мастера** .</span><span class="sxs-lookup"><span data-stu-id="a890b-119">If you are using a Survivable Branch Appliance or Survivable Branch Server at this site, be sure that the **Open the New Survivable Wizard when this wizard closes** check box is selected.</span></span>
    
      - <span data-ttu-id="a890b-120">Если вы не используете работающее работающее устройство филиала или бесперебойную подразделение сервера на этом сайте, снимите флажок **открыть новый бесперебойный мастер, когда этот мастер закроется** .</span><span class="sxs-lookup"><span data-stu-id="a890b-120">If you are not using a Survivable Branch Appliance or Survivable Branch Server at this site, clear the **Open the New Survivable Wizard when this wizard closes** check box.</span></span>
    
      - <span data-ttu-id="a890b-121">Нажмите кнопку **Готово**, а затем следуйте указаниям в открывшемся мастере.</span><span class="sxs-lookup"><span data-stu-id="a890b-121">Click **Finish**, and then follow the directions in the wizard that opens.</span></span> <span data-ttu-id="a890b-122">Сведения об элементах мастера можно найти [в разделе Определение работающего устройства филиала или сервера в Lync Server 2013](lync-server-2013-define-a-survivable-branch-appliance-or-server.md).</span><span class="sxs-lookup"><span data-stu-id="a890b-122">For information about wizard items, see [Define a Survivable Branch Appliance or Server in Lync Server 2013](lync-server-2013-define-a-survivable-branch-appliance-or-server.md).</span></span>

8.  <span data-ttu-id="a890b-123">Повторите описанные выше действия для всех сайтов филиалов, которые нужно добавить в топологию.</span><span class="sxs-lookup"><span data-stu-id="a890b-123">Repeat the previous steps for each branch site that you want to add to the topology.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="a890b-124">См. также</span><span class="sxs-lookup"><span data-stu-id="a890b-124">See Also</span></span>


[<span data-ttu-id="a890b-125">Определение устройства или сервера для обеспечения связи в филиалах в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a890b-125">Define a Survivable Branch Appliance or Server in Lync Server 2013</span></span>](lync-server-2013-define-a-survivable-branch-appliance-or-server.md)  
[<span data-ttu-id="a890b-126">Определение шлюза ТСОП для сайта филиала в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a890b-126">Define a PSTN gateway for a branch site in Lync Server 2013</span></span>](lync-server-2013-define-a-pstn-gateway-for-a-branch-site.md)  
[<span data-ttu-id="a890b-127">Configure a trunk with media bypass in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a890b-127">Configure a trunk with media bypass in Lync Server 2013</span></span>](lync-server-2013-configure-a-trunk-with-media-bypass.md)  
[<span data-ttu-id="a890b-128">Настройка магистрали без обхода мультимедиа в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a890b-128">Configure a trunk without media bypass in Lync Server 2013</span></span>](lync-server-2013-configure-a-trunk-without-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

