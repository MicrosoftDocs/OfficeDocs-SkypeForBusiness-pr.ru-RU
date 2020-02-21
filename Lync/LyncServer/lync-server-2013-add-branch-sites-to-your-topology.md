---
title: 'Lync Server 2013: Добавление сайтов филиалов в топологию'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Add branch sites to your topology
ms:assetid: b9c35fb0-0081-4aeb-8f95-ac2fcc6c3335
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412905(v=OCS.15)
ms:contentKeyID: 48185216
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3d4e024ed5cdb29bb8a8a4170b89399f955254bf
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42181392"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="add-branch-sites-to-your-topology-in-lync-server-2013"></a><span data-ttu-id="fa3e1-102">Добавление сайтов филиалов в топологию в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fa3e1-102">Add branch sites to your topology in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fa3e1-103">_**Последнее изменение темы:** 2012-10-05_</span><span class="sxs-lookup"><span data-stu-id="fa3e1-103">_**Topic Last Modified:** 2012-10-05_</span></span>

<span data-ttu-id="fa3e1-p101">Сайты филиалов представляют отделения организации, подключенные к центральным офисам с помощью канала глобальной сети. Чтобы добавить сайт филиала в топологию Lync, выполните на центральном сайте следующую процедуру.</span><span class="sxs-lookup"><span data-stu-id="fa3e1-p101">Branch sites represent physical branch offices that are connected to your main offices over a WAN link. To add a branch site to your Lync topology, perform this procedure at the central site.</span></span>

<div>

## <a name="to-add-branch-sites-to-your-topology"></a><span data-ttu-id="fa3e1-106">Добавление сайтов филиалов в топологию</span><span class="sxs-lookup"><span data-stu-id="fa3e1-106">To add branch sites to your topology</span></span>

1.  <span data-ttu-id="fa3e1-107">Нажмите кнопку **Пуск** и затем последовательно выберите **Все программы**, **Microsoft Lync Server** и **Lync Server Topology Builder** (Построитель топологий Lync Server).</span><span class="sxs-lookup"><span data-stu-id="fa3e1-107">Click **Start**, click **All Programs**, click **Microsoft Lync Server**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="fa3e1-108">В дереве консоли разверните центральный сайт, щелкните правой кнопкой мыши элемент **Общие компоненты** и выберите команду **Создать сайт филиала**.</span><span class="sxs-lookup"><span data-stu-id="fa3e1-108">In the console tree, expand the central site, right-click **Branch Sites**, and then click **New Branch Site**.</span></span>

3.  <span data-ttu-id="fa3e1-109">В поле **Name** (Имя) диалогового окна **Define New Branch Site** (Определение нового сайта филиала) введите имя сайта филиала.</span><span class="sxs-lookup"><span data-stu-id="fa3e1-109">In the **Define New Branch Site** dialog box, click **Name**, and then type the name of the branch site.</span></span>

4.  <span data-ttu-id="fa3e1-110">(Необязательно) Щелкните элемент **Описание**, а затем введите содержательное описание для сайта филиала.</span><span class="sxs-lookup"><span data-stu-id="fa3e1-110">(Optional) Click **Description**, and then type a meaningful description for the branch site.</span></span>

5.  <span data-ttu-id="fa3e1-111">Нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="fa3e1-111">Click **Next**.</span></span>

6.  <span data-ttu-id="fa3e1-112">(Необязательно) В следующем диалоговом окне **Определение нового сайта филиала для сайта** выполните любое из следующих действий:</span><span class="sxs-lookup"><span data-stu-id="fa3e1-112">(Optional) In the next **Define New Branch Site** dialog box, do any of the following:</span></span>
    
      - <span data-ttu-id="fa3e1-113">Щелкните элемент **Город**, а затем введите название города, в котором расположен сайт филиала.</span><span class="sxs-lookup"><span data-stu-id="fa3e1-113">Click **City**, and then type the name of the city in which the branch site is located.</span></span>
    
      - <span data-ttu-id="fa3e1-114">Щелкните элемент **Регион**, а затем введите название региона или области, где расположен сайт филиала.</span><span class="sxs-lookup"><span data-stu-id="fa3e1-114">Click **State/Region**, and then type the name of the state or region in which the branch site is located.</span></span>
    
      - <span data-ttu-id="fa3e1-115">Щелкните элемент **Код страны**, а затем введите двузначный вызывной код для страны/региона, где расположен сайт филиала.</span><span class="sxs-lookup"><span data-stu-id="fa3e1-115">Click **Country Code**, and then type the two-digit calling code for the country/region in which the branch site is located.</span></span>

7.  <span data-ttu-id="fa3e1-116">Нажмите кнопку **Далее**, а затем выполните одно из следующих действий:</span><span class="sxs-lookup"><span data-stu-id="fa3e1-116">Click **Next**, and then do one of the following:</span></span>
    
      - <span data-ttu-id="fa3e1-117">Если вы используете устройство или сервер для обеспечения связи в филиалах на этом сайте, убедитесь, что установлен флажок **открыть новый бесперебойный мастер, когда этот мастер закроется** , нажмите кнопку **Готово**, а затем следуйте инструкциям в открывшемся мастере.</span><span class="sxs-lookup"><span data-stu-id="fa3e1-117">If you are using a Survivable Branch Appliance or Server at this site, be sure that the **Open the New Survivable Wizard when this wizard closes** check box is selected, click **Finish**, and then follow the directions in the wizard that opens.</span></span> <span data-ttu-id="fa3e1-118">Сведения об элементах мастера можно найти [в разделе Определение устройства или сервера для обеспечения связи в филиалах в Lync Server 2013](lync-server-2013-define-a-survivable-branch-appliance-or-server.md).</span><span class="sxs-lookup"><span data-stu-id="fa3e1-118">For information about wizard items, see [Define a Survivable Branch Appliance or Server in Lync Server 2013](lync-server-2013-define-a-survivable-branch-appliance-or-server.md).</span></span>
    
      - <span data-ttu-id="fa3e1-119">Если вы не используете на этом сайте устройство или сервер для обеспечения связи в филиалах, снимите флажок **Открыть мастер создания устройства для обеспечения связи в филиалах после завершения работы этого мастера**. а затем нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="fa3e1-119">If you are not using a Survivable Branch Appliance or Server at this site, clear the **Open the New Survivable Wizard when this wizard closes** check box, and then click **Finish**.</span></span>

8.  <span data-ttu-id="fa3e1-120">Повторите предыдущие действия для каждого сайта филиала, который вы хотите добавить в топологию.</span><span class="sxs-lookup"><span data-stu-id="fa3e1-120">Repeat the previous steps for each branch site that you want to add to the topology.</span></span>

<span data-ttu-id="fa3e1-121">**Следующий шаг:**</span><span class="sxs-lookup"><span data-stu-id="fa3e1-121">**Next step:**</span></span>

<span data-ttu-id="fa3e1-122">Для устройств или серверов для обеспечения связи в филиалах: [Определение устройства или сервера для обеспечения связи в филиалах в Lync Server 2013](lync-server-2013-define-a-survivable-branch-appliance-or-server.md)</span><span class="sxs-lookup"><span data-stu-id="fa3e1-122">For Survivable Branch Appliances or Servers: [Define a Survivable Branch Appliance or Server in Lync Server 2013](lync-server-2013-define-a-survivable-branch-appliance-or-server.md)</span></span>

<span data-ttu-id="fa3e1-123">Для неустойчивых подключений PSTN: [определение шлюза PSTN для сайта филиала в Lync server 2013](lync-server-2013-define-a-pstn-gateway-for-a-branch-site.md), [Настройка магистрали с обходом сервера-посредника в Lync Server 2013](lync-server-2013-configure-a-trunk-with-media-bypass.md)или [Настройка магистрали без обхода сервера-посредника в Lync Server 2013](lync-server-2013-configure-a-trunk-without-media-bypass.md)</span><span class="sxs-lookup"><span data-stu-id="fa3e1-123">For non-resilient PSTN connectivity: [Define a PSTN gateway for a branch site in Lync Server 2013](lync-server-2013-define-a-pstn-gateway-for-a-branch-site.md), [Configure a trunk with media bypass in Lync Server 2013](lync-server-2013-configure-a-trunk-with-media-bypass.md), or [Configure a trunk without media bypass in Lync Server 2013](lync-server-2013-configure-a-trunk-without-media-bypass.md)</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

