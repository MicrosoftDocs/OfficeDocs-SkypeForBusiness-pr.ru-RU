---
title: Добавление сайта филиала Lync Server 2013 для обеспечения связи в филиалах к топологии
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
ms.openlocfilehash: ad708f2f37b95d970f9c9585730c015ff6798f6a
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48521466"
---
# <a name="add-lync-server-2013-survivable-branch-appliance-branch-site-to-your-topology"></a><span data-ttu-id="4d206-102">Добавление сайта филиала Lync Server 2013 для обеспечения связи в филиалах к топологии</span><span class="sxs-lookup"><span data-stu-id="4d206-102">Add Lync Server 2013 Survivable Branch Appliance branch site to your topology</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4d206-103">_**Последнее изменение темы:** 2012-10-07_</span><span class="sxs-lookup"><span data-stu-id="4d206-103">_**Topic Last Modified:** 2012-10-07_</span></span>

<span data-ttu-id="4d206-104">Устройства для обеспечения связи в филиалах Microsoft Lync Server 2013 не могут быть связаны с пулом переднего плана Microsoft Lync Server 2010 в качестве регистратора резервных копий.</span><span class="sxs-lookup"><span data-stu-id="4d206-104">Microsoft Lync Server 2013 Survivable Branch Appliances (SBA) cannot be associated to a Microsoft Lync Server 2010 Front End pool as a backup Registrar.</span></span> <span data-ttu-id="4d206-105">SBA должен быть связан с интерфейсным пулом Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="4d206-105">The SBA must be associated with a Microsoft Lync Server 2013 Front End pool.</span></span> <span data-ttu-id="4d206-106">Эти действия предполагают использование Microsoft Lync Server 2013 SBA.</span><span class="sxs-lookup"><span data-stu-id="4d206-106">These steps assume a Microsoft Lync Server 2013 SBA.</span></span> <span data-ttu-id="4d206-107">Выполните эту процедуру на центральном сайте.</span><span class="sxs-lookup"><span data-stu-id="4d206-107">Perform this procedure at the central site.</span></span>

<div>

## <a name="to-add-branch-sites-with-microsoft-lync-server-2013-sba-to-your-topology"></a><span data-ttu-id="4d206-108">Добавление сайтов филиалов с помощью Microsoft Lync Server 2013 SBA к топологии</span><span class="sxs-lookup"><span data-stu-id="4d206-108">To add branch sites with Microsoft Lync Server 2013 SBA to your topology</span></span>

1.  <span data-ttu-id="4d206-109">Запустите построитель топологий: нажмите кнопку **Пуск**, последовательно выберите пункты **все программы**, **Microsoft Lync Server 2013**и **Построитель топологий Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="4d206-109">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="4d206-110">В дереве консоли разверните центральный сайт, разверните **сайты филиалов**, а затем щелкните **New Branch Site** (Новый сайт филиала).</span><span class="sxs-lookup"><span data-stu-id="4d206-110">In the console tree, expand the central site, expand **Branch Sites**, and then click **New Branch Site**.</span></span>

3.  <span data-ttu-id="4d206-111">В диалоговом окне **Define New Branch Site** (Задать новый сайт филиала) щелкните **Name** (Имя), а затем введите имя нового сайта филиала.</span><span class="sxs-lookup"><span data-stu-id="4d206-111">In the **Define New Branch Site** dialog box, click **Name**, and then type a name for the new branch site.</span></span>

4.  <span data-ttu-id="4d206-112">(Необязательно) Щелкните **Description** (Описание), а затем введите содержательное описание сайта филиала.</span><span class="sxs-lookup"><span data-stu-id="4d206-112">(Optional) Click **Description**, and then type a meaningful description for the branch site.</span></span>

5.  <span data-ttu-id="4d206-113">Нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="4d206-113">Click **Next**.</span></span>

6.  <span data-ttu-id="4d206-114">(Необязательно) В следующем диалоговом окне **Определение нового сайта филиала для сайта** выполните любое из следующих действий:</span><span class="sxs-lookup"><span data-stu-id="4d206-114">(Optional) In the next **Define New Branch Site** dialog box, do any of the following:</span></span>
    
      - <span data-ttu-id="4d206-115">Щелкните элемент **Город**, а затем введите название города, в котором расположен сайт филиала.</span><span class="sxs-lookup"><span data-stu-id="4d206-115">Click **City**, and then type the name of the city in which the branch site is located.</span></span>
    
      - <span data-ttu-id="4d206-116">Щелкните элемент **Регион**, а затем введите название региона или области, где расположен сайт филиала.</span><span class="sxs-lookup"><span data-stu-id="4d206-116">Click **State/Region**, and then type the name of the state or region in which the branch site is located.</span></span>
    
      - <span data-ttu-id="4d206-117">Щелкните элемент **Код страны**, а затем введите двузначный вызывной код для страны/региона, где расположен сайт филиала.</span><span class="sxs-lookup"><span data-stu-id="4d206-117">Click **Country Code**, and then type the two-digit calling code for the country/region in which the branch site is located.</span></span>

7.  <span data-ttu-id="4d206-118">Нажмите кнопку **Далее**, а затем выполните одно из следующих действий:</span><span class="sxs-lookup"><span data-stu-id="4d206-118">Click **Next**, and then do one of the following:</span></span>
    
      - <span data-ttu-id="4d206-119">Если вы используете устройство для обеспечения связи в филиалах или сервер для обеспечения связи в филиалах на этом сайте, убедитесь, что установлен флажок Открыть новый список для установки, **когда этот мастер закроется** .</span><span class="sxs-lookup"><span data-stu-id="4d206-119">If you are using a Survivable Branch Appliance or Survivable Branch Server at this site, be sure that the **Open the New Survivable Wizard when this wizard closes** check box is selected.</span></span>
    
      - <span data-ttu-id="4d206-120">Если вы не используете устройство для обеспечения связи в филиалах или сервер для обеспечения связи в филиалах на этом сайте, снимите флажок **открыть мастер создания для обеспечения связи после закрытия этого мастера** .</span><span class="sxs-lookup"><span data-stu-id="4d206-120">If you are not using a Survivable Branch Appliance or Survivable Branch Server at this site, clear the **Open the New Survivable Wizard when this wizard closes** check box.</span></span>
    
      - <span data-ttu-id="4d206-121">Нажмите кнопку **Готово**, а затем следуйте инструкциям в открывшемся мастере.</span><span class="sxs-lookup"><span data-stu-id="4d206-121">Click **Finish**, and then follow the directions in the wizard that opens.</span></span> <span data-ttu-id="4d206-122">Сведения об элементах мастера можно найти [в разделе Определение устройства или сервера для обеспечения связи в филиалах в Lync Server 2013](lync-server-2013-define-a-survivable-branch-appliance-or-server.md).</span><span class="sxs-lookup"><span data-stu-id="4d206-122">For information about wizard items, see [Define a Survivable Branch Appliance or Server in Lync Server 2013](lync-server-2013-define-a-survivable-branch-appliance-or-server.md).</span></span>

8.  <span data-ttu-id="4d206-123">Повторите предыдущие действия для каждого сайта филиала, который вы хотите добавить в топологию.</span><span class="sxs-lookup"><span data-stu-id="4d206-123">Repeat the previous steps for each branch site that you want to add to the topology.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="4d206-124">См. также</span><span class="sxs-lookup"><span data-stu-id="4d206-124">See Also</span></span>


[<span data-ttu-id="4d206-125">Определение устройства или сервера для обеспечения связи в филиалах в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4d206-125">Define a Survivable Branch Appliance or Server in Lync Server 2013</span></span>](lync-server-2013-define-a-survivable-branch-appliance-or-server.md)  
[<span data-ttu-id="4d206-126">Определение шлюза PSTN для сайта филиала в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4d206-126">Define a PSTN gateway for a branch site in Lync Server 2013</span></span>](lync-server-2013-define-a-pstn-gateway-for-a-branch-site.md)  
[<span data-ttu-id="4d206-127">Настройка магистрали с обходом сервера мультимедиа в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4d206-127">Configure a trunk with media bypass in Lync Server 2013</span></span>](lync-server-2013-configure-a-trunk-with-media-bypass.md)  
[<span data-ttu-id="4d206-128">Настройка магистрали без обхода сервера мультимедиа в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4d206-128">Configure a trunk without media bypass in Lync Server 2013</span></span>](lync-server-2013-configure-a-trunk-without-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

