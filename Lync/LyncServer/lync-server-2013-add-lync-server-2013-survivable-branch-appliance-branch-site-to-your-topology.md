---
title: Добавление сайта филиала Lync Server 2013 для обеспечения связи в филиалах к топологии
description: Добавьте сайт филиала Lync Server 2013 для обеспечения связи в филиалах к топологии.
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
ms.openlocfilehash: 1b50c03dd53c7637fcf0914db290b3e452b64b83
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48572035"
---
# <a name="add-lync-server-2013-survivable-branch-appliance-branch-site-to-your-topology"></a><span data-ttu-id="3586b-103">Добавление сайта филиала Lync Server 2013 для обеспечения связи в филиалах к топологии</span><span class="sxs-lookup"><span data-stu-id="3586b-103">Add Lync Server 2013 Survivable Branch Appliance branch site to your topology</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3586b-104">_**Последнее изменение темы:** 2012-10-07_</span><span class="sxs-lookup"><span data-stu-id="3586b-104">_**Topic Last Modified:** 2012-10-07_</span></span>

<span data-ttu-id="3586b-105">Устройства для обеспечения связи в филиалах Microsoft Lync Server 2013 не могут быть связаны с пулом переднего плана Microsoft Lync Server 2010 в качестве регистратора резервных копий.</span><span class="sxs-lookup"><span data-stu-id="3586b-105">Microsoft Lync Server 2013 Survivable Branch Appliances (SBA) cannot be associated to a Microsoft Lync Server 2010 Front End pool as a backup Registrar.</span></span> <span data-ttu-id="3586b-106">SBA должен быть связан с интерфейсным пулом Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="3586b-106">The SBA must be associated with a Microsoft Lync Server 2013 Front End pool.</span></span> <span data-ttu-id="3586b-107">Эти действия предполагают использование Microsoft Lync Server 2013 SBA.</span><span class="sxs-lookup"><span data-stu-id="3586b-107">These steps assume a Microsoft Lync Server 2013 SBA.</span></span> <span data-ttu-id="3586b-108">Выполните эту процедуру на центральном сайте.</span><span class="sxs-lookup"><span data-stu-id="3586b-108">Perform this procedure at the central site.</span></span>

<div>

## <a name="to-add-branch-sites-with-microsoft-lync-server-2013-sba-to-your-topology"></a><span data-ttu-id="3586b-109">Добавление сайтов филиалов с помощью Microsoft Lync Server 2013 SBA к топологии</span><span class="sxs-lookup"><span data-stu-id="3586b-109">To add branch sites with Microsoft Lync Server 2013 SBA to your topology</span></span>

1.  <span data-ttu-id="3586b-110">Запустите построитель топологий: нажмите кнопку **Пуск**, последовательно выберите пункты **все программы**, **Microsoft Lync Server 2013**и **Построитель топологий Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="3586b-110">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="3586b-111">В дереве консоли разверните центральный сайт, разверните **сайты филиалов**, а затем щелкните **New Branch Site** (Новый сайт филиала).</span><span class="sxs-lookup"><span data-stu-id="3586b-111">In the console tree, expand the central site, expand **Branch Sites**, and then click **New Branch Site**.</span></span>

3.  <span data-ttu-id="3586b-112">В диалоговом окне **Define New Branch Site** (Задать новый сайт филиала) щелкните **Name** (Имя), а затем введите имя нового сайта филиала.</span><span class="sxs-lookup"><span data-stu-id="3586b-112">In the **Define New Branch Site** dialog box, click **Name**, and then type a name for the new branch site.</span></span>

4.  <span data-ttu-id="3586b-113">(Необязательно) Щелкните **Description** (Описание), а затем введите содержательное описание сайта филиала.</span><span class="sxs-lookup"><span data-stu-id="3586b-113">(Optional) Click **Description**, and then type a meaningful description for the branch site.</span></span>

5.  <span data-ttu-id="3586b-114">Нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="3586b-114">Click **Next**.</span></span>

6.  <span data-ttu-id="3586b-115">(Необязательно) В следующем диалоговом окне **Определение нового сайта филиала для сайта** выполните любое из следующих действий:</span><span class="sxs-lookup"><span data-stu-id="3586b-115">(Optional) In the next **Define New Branch Site** dialog box, do any of the following:</span></span>
    
      - <span data-ttu-id="3586b-116">Щелкните элемент **Город**, а затем введите название города, в котором расположен сайт филиала.</span><span class="sxs-lookup"><span data-stu-id="3586b-116">Click **City**, and then type the name of the city in which the branch site is located.</span></span>
    
      - <span data-ttu-id="3586b-117">Щелкните элемент **Регион**, а затем введите название региона или области, где расположен сайт филиала.</span><span class="sxs-lookup"><span data-stu-id="3586b-117">Click **State/Region**, and then type the name of the state or region in which the branch site is located.</span></span>
    
      - <span data-ttu-id="3586b-118">Щелкните элемент **Код страны**, а затем введите двузначный вызывной код для страны/региона, где расположен сайт филиала.</span><span class="sxs-lookup"><span data-stu-id="3586b-118">Click **Country Code**, and then type the two-digit calling code for the country/region in which the branch site is located.</span></span>

7.  <span data-ttu-id="3586b-119">Нажмите кнопку **Далее**, а затем выполните одно из следующих действий:</span><span class="sxs-lookup"><span data-stu-id="3586b-119">Click **Next**, and then do one of the following:</span></span>
    
      - <span data-ttu-id="3586b-120">Если вы используете устройство для обеспечения связи в филиалах или сервер для обеспечения связи в филиалах на этом сайте, убедитесь, что установлен флажок Открыть новый список для установки, **когда этот мастер закроется** .</span><span class="sxs-lookup"><span data-stu-id="3586b-120">If you are using a Survivable Branch Appliance or Survivable Branch Server at this site, be sure that the **Open the New Survivable Wizard when this wizard closes** check box is selected.</span></span>
    
      - <span data-ttu-id="3586b-121">Если вы не используете устройство для обеспечения связи в филиалах или сервер для обеспечения связи в филиалах на этом сайте, снимите флажок **открыть мастер создания для обеспечения связи после закрытия этого мастера** .</span><span class="sxs-lookup"><span data-stu-id="3586b-121">If you are not using a Survivable Branch Appliance or Survivable Branch Server at this site, clear the **Open the New Survivable Wizard when this wizard closes** check box.</span></span>
    
      - <span data-ttu-id="3586b-122">Нажмите кнопку **Готово**, а затем следуйте инструкциям в открывшемся мастере.</span><span class="sxs-lookup"><span data-stu-id="3586b-122">Click **Finish**, and then follow the directions in the wizard that opens.</span></span> <span data-ttu-id="3586b-123">Сведения об элементах мастера можно найти [в разделе Определение устройства или сервера для обеспечения связи в филиалах в Lync Server 2013](lync-server-2013-define-a-survivable-branch-appliance-or-server.md).</span><span class="sxs-lookup"><span data-stu-id="3586b-123">For information about wizard items, see [Define a Survivable Branch Appliance or Server in Lync Server 2013](lync-server-2013-define-a-survivable-branch-appliance-or-server.md).</span></span>

8.  <span data-ttu-id="3586b-124">Повторите предыдущие действия для каждого сайта филиала, который вы хотите добавить в топологию.</span><span class="sxs-lookup"><span data-stu-id="3586b-124">Repeat the previous steps for each branch site that you want to add to the topology.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="3586b-125">См. также</span><span class="sxs-lookup"><span data-stu-id="3586b-125">See Also</span></span>


[<span data-ttu-id="3586b-126">Определение устройства или сервера для обеспечения связи в филиалах в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3586b-126">Define a Survivable Branch Appliance or Server in Lync Server 2013</span></span>](lync-server-2013-define-a-survivable-branch-appliance-or-server.md)  
[<span data-ttu-id="3586b-127">Определение шлюза PSTN для сайта филиала в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3586b-127">Define a PSTN gateway for a branch site in Lync Server 2013</span></span>](lync-server-2013-define-a-pstn-gateway-for-a-branch-site.md)  
[<span data-ttu-id="3586b-128">Настройка магистрали с обходом сервера мультимедиа в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3586b-128">Configure a trunk with media bypass in Lync Server 2013</span></span>](lync-server-2013-configure-a-trunk-with-media-bypass.md)  
[<span data-ttu-id="3586b-129">Настройка магистрали без обхода сервера мультимедиа в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3586b-129">Configure a trunk without media bypass in Lync Server 2013</span></span>](lync-server-2013-configure-a-trunk-without-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

