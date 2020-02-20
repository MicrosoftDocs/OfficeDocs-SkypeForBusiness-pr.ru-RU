---
title: 'Lync Server 2013: приложение б: Управление устройством для обеспечения связи в филиалах'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: 'Appendix B: Managing a Survivable Branch Appliance'
ms:assetid: 2ec9d505-6d39-491c-9524-8cf36866b855
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425797(v=OCS.15)
ms:contentKeyID: 48183773
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: df6e2dc473da81177dacb8d53ee673c9a5457c98
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42147182"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="appendix-b-managing-a-survivable-branch-appliance-in-lync-server-2013"></a><span data-ttu-id="17451-102">Приложение б. Управление устройством для обеспечения связи в филиалах в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="17451-102">Appendix B: Managing a Survivable Branch Appliance in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="17451-103">_**Последнее изменение темы:** 2012-10-18_</span><span class="sxs-lookup"><span data-stu-id="17451-103">_**Topic Last Modified:** 2012-10-18_</span></span>

<span data-ttu-id="17451-104">В этом разделе описываются процедуры управления устройством для обеспечения связи в филиалах.</span><span class="sxs-lookup"><span data-stu-id="17451-104">This topic describes the procedures for managing a Survivable Branch Appliance.</span></span> <span data-ttu-id="17451-105">В частности, как заменить и переименовать устройство для обеспечения связи в филиалах, а также как изменить интерфейсный пул Lync Server 2013, с которым связано устройство для обеспечения связи в филиалах.</span><span class="sxs-lookup"><span data-stu-id="17451-105">Specifically, how to replace and rename a Survivable Branch Appliance, and how to change the Lync Server 2013 Front End pool that the Survivable Branch Appliance is associated with.</span></span>

<div>

## <a name="to-replace-a-survivable-branch-appliance"></a><span data-ttu-id="17451-106">Замена устройства для обеспечения связи в филиалах</span><span class="sxs-lookup"><span data-stu-id="17451-106">To Replace a Survivable Branch Appliance</span></span>

1.  <span data-ttu-id="17451-107">Остановите все службы Lync Server 2013 на устройстве для обеспечения связи в филиалах.</span><span class="sxs-lookup"><span data-stu-id="17451-107">Stop all Lync Server 2013 services on the Survivable Branch Appliance.</span></span> <span data-ttu-id="17451-108">(Обратитесь к документации производителя устройства для обеспечения связи в филиалах.)</span><span class="sxs-lookup"><span data-stu-id="17451-108">(See the Survivable Branch Appliance vendor documentation.)</span></span>

2.  <span data-ttu-id="17451-109">Предложен Удалите устройство для обеспечения связи в филиалах из домена.</span><span class="sxs-lookup"><span data-stu-id="17451-109">(Recommended) Remove the Survivable Branch Appliance from the domain.</span></span>

3.  <span data-ttu-id="17451-110">Удалите объект компьютера устройства для обеспечения связи в филиалах в доменных службах Active Directory, выполнив указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="17451-110">Delete the Survivable Branch Appliance computer object in Active Directory Domain Services, by following these steps:</span></span>
    
      - <span data-ttu-id="17451-111">Выполните вход на рядовой сервер в качестве члена группы «Администраторы предприятия».</span><span class="sxs-lookup"><span data-stu-id="17451-111">Log on to a member server as a member of the Enterprise Admins group.</span></span>
    
      - <span data-ttu-id="17451-112">Нажмите кнопку **Пуск**, перейдите в пункт **Администрирование** и выберите пункт **Active Directory  пользователи и компьютеры**.</span><span class="sxs-lookup"><span data-stu-id="17451-112">Click **Start**, click **Administrative Tools**, and then click **Active Directory Users and Computers**.</span></span>
    
      - <span data-ttu-id="17451-113">Щелкните правой кнопкой мыши объект устройства для обеспечения связи в филиале и выберите команду **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="17451-113">Right-click the Survivable Branch Appliance object, and click **Delete**.</span></span>

4.  <span data-ttu-id="17451-114">Снова добавьте объект компьютера для устройства для обеспечения связи в филиале.</span><span class="sxs-lookup"><span data-stu-id="17451-114">Add the Survivable Branch Appliance computer object again.</span></span> <span data-ttu-id="17451-115">(См. раздел [Добавление устройства для обеспечения связи в филиалах в Active Directory в Lync Server 2013](lync-server-2013-add-a-survivable-branch-appliance-to-active-directory.md).)</span><span class="sxs-lookup"><span data-stu-id="17451-115">(See [Add a Survivable Branch Appliance to Active Directory in Lync Server 2013](lync-server-2013-add-a-survivable-branch-appliance-to-active-directory.md).)</span></span>

5.  <span data-ttu-id="17451-116">Дождитесь выполнения репликации Active Directory.</span><span class="sxs-lookup"><span data-stu-id="17451-116">Wait for Active Directory replication to take place.</span></span>

6.  <span data-ttu-id="17451-117">Откройте командную консоль Lync Server и введите **Enable – CSTopology**.</span><span class="sxs-lookup"><span data-stu-id="17451-117">Open the Lync Server Management Shell, and type **Enable-CSTopology**.</span></span>

7.  <span data-ttu-id="17451-118">Подключите к сети новое устройство для обеспечения связи в филиалах и выполните действия, описанные в статье [развертывание устройства или сервера для обеспечения связи в филиалах с помощью Lync server 2013-Central Site Tasks](lync-server-2013-deploying-a-survivable-branch-appliance-or-server-central-site-tasks.md) и [развертывание устройства или сервера для обеспечения связи в филиалах с задачей Lync Server 2013-Branch site](lync-server-2013-deploy-a-survivable-branch-appliance-or-server-branch-site-task.md).</span><span class="sxs-lookup"><span data-stu-id="17451-118">Connect the new Survivable Branch Appliance to the network, and follow the steps in [Deploying a Survivable Branch Appliance or Server with Lync Server 2013 - central site tasks](lync-server-2013-deploying-a-survivable-branch-appliance-or-server-central-site-tasks.md) and [Deploy a Survivable Branch Appliance or Server with Lync Server 2013 - branch site task](lync-server-2013-deploy-a-survivable-branch-appliance-or-server-branch-site-task.md).</span></span>

</div>

<div>

## <a name="to-rename-a-survivable-branch-appliance"></a><span data-ttu-id="17451-119">Переименование устройства для обеспечения связи в филиалах</span><span class="sxs-lookup"><span data-stu-id="17451-119">To Rename a Survivable Branch Appliance</span></span>

1.  <span data-ttu-id="17451-120">Переместите пользователей на центральный сайт.</span><span class="sxs-lookup"><span data-stu-id="17451-120">Move users to the central site.</span></span> <span data-ttu-id="17451-121">Дополнительную информацию можно узнать [в статье перемещение пользователей в другой пул в Lync Server 2013](lync-server-2013-move-users-to-another-pool.md).</span><span class="sxs-lookup"><span data-stu-id="17451-121">For details, see [Move users to another pool in Lync Server 2013](lync-server-2013-move-users-to-another-pool.md).</span></span>

2.  <span data-ttu-id="17451-122">Остановите все службы Lync Server 2013 на устройстве для обеспечения связи в филиалах.</span><span class="sxs-lookup"><span data-stu-id="17451-122">Stop all Lync Server 2013 services on the Survivable Branch Appliance.</span></span> <span data-ttu-id="17451-123">(Обратитесь к документации производителя устройства для обеспечения связи в филиалах.)</span><span class="sxs-lookup"><span data-stu-id="17451-123">(See the Survivable Branch Appliance vendor documentation.)</span></span>

3.  <span data-ttu-id="17451-124">Удалите устройство для обеспечения связи в филиалах из топологии, выполнив указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="17451-124">Remove the Survivable Branch Appliance from the topology, by following these steps:</span></span>
    
      - <span data-ttu-id="17451-125">В меню **Пуск** последовательно выберите пункты **Все программы**, **Microsoft Lync Server** и **Построитель топологий**.</span><span class="sxs-lookup"><span data-stu-id="17451-125">Click **Start**, click **All Programs**, click **Microsoft Lync Server**, and then click **Lync Server Topology Builder**.</span></span>
    
      - <span data-ttu-id="17451-126">В дереве консоли разверните узел **сайты филиалов**, выберите устройство для обеспечения связи в филиалах, а затем нажмите кнопку **Удалить** на панели действий.</span><span class="sxs-lookup"><span data-stu-id="17451-126">In the console tree, expand **Branch Sites**, click the Survivable Branch Appliance, and then click **Delete** on the Action pane.</span></span>

4.  <span data-ttu-id="17451-127">Удалите устройство для обеспечения связи в филиалах из домена.</span><span class="sxs-lookup"><span data-stu-id="17451-127">Remove the Survivable Branch Appliance from the domain.</span></span>

5.  <span data-ttu-id="17451-128">Удалите объект компьютера устройства для обеспечения связи в филиале в Active Directory, выполнив следующие действия:</span><span class="sxs-lookup"><span data-stu-id="17451-128">Delete the Survivable Branch Appliance computer object in Active Directory, by following these steps:</span></span>
    
      - <span data-ttu-id="17451-129">Выполните вход на контроллер домена в качестве члена группы «Администраторы предприятия».</span><span class="sxs-lookup"><span data-stu-id="17451-129">Log on to a domain controller as a member of the Enterprise Admins group.</span></span>
    
      - <span data-ttu-id="17451-130">Нажмите кнопку **Пуск**, выберите **Администрирование** и затем **Пользователи и компьютеры Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="17451-130">Click **Start**, click **Administrative Tools**, and then click **Active Directory Users and Computers**.</span></span>
    
      - <span data-ttu-id="17451-131">Щелкните правой кнопкой мыши объект устройства для обеспечения связи в филиале и выберите команду **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="17451-131">Right-click the Survivable Branch Appliance object, and click **Delete**.</span></span>

6.  <span data-ttu-id="17451-132">Восстановите устройства для обеспечения связи в филиалах до заводских настроек по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="17451-132">Restore the Survivable Branch Appliance to factory defaults.</span></span> <span data-ttu-id="17451-133">(Обратитесь к документации производителя устройства для обеспечения связи в филиалах.)</span><span class="sxs-lookup"><span data-stu-id="17451-133">(See the Survivable Branch Appliance vendor documentation.)</span></span>

7.  <span data-ttu-id="17451-134">Выполните действия, описанные в статье [развертывание устройства или сервера для обеспечения связи в филиалах с помощью задач Lync server 2013-Central](lync-server-2013-deploying-a-survivable-branch-appliance-or-server-central-site-tasks.md) и [развертывание устройства или сервера для обеспечения связи в филиалах с помощью Lync Server 2013 — задача сайта филиала](lync-server-2013-deploy-a-survivable-branch-appliance-or-server-branch-site-task.md).</span><span class="sxs-lookup"><span data-stu-id="17451-134">Follow the steps in [Deploying a Survivable Branch Appliance or Server with Lync Server 2013 - central site tasks](lync-server-2013-deploying-a-survivable-branch-appliance-or-server-central-site-tasks.md) and [Deploy a Survivable Branch Appliance or Server with Lync Server 2013 - branch site task](lync-server-2013-deploy-a-survivable-branch-appliance-or-server-branch-site-task.md).</span></span>

8.  <span data-ttu-id="17451-135">Переместите пользователей на переименованное устройство для обеспечения связи в филиалах.</span><span class="sxs-lookup"><span data-stu-id="17451-135">Move users to the renamed Survivable Branch Appliance.</span></span> <span data-ttu-id="17451-136">Дополнительную информацию можно узнать [в статье перемещение пользователей в другой пул в Lync Server 2013](lync-server-2013-move-users-to-another-pool.md).</span><span class="sxs-lookup"><span data-stu-id="17451-136">For details, see [Move users to another pool in Lync Server 2013](lync-server-2013-move-users-to-another-pool.md).</span></span>

</div>

<div>

## <a name="to-change-the-lync-server-front-end-pool-that-the-survivable-branch-appliance-is-associated-with"></a><span data-ttu-id="17451-137">Изменение интерфейсного пула Lync Server, с которым сопоставлено устройство для обеспечения связи в филиалах</span><span class="sxs-lookup"><span data-stu-id="17451-137">To Change the Lync Server Front End Pool that the Survivable Branch Appliance Is Associated With</span></span>

1.  <span data-ttu-id="17451-138">Переместите пользователей из устройства для обеспечения связи в филиалах в пул переднего плана Lync Server на центральном сайте.</span><span class="sxs-lookup"><span data-stu-id="17451-138">Move users from the Survivable Branch Appliance to the Lync Server Front End pool at the central site.</span></span> <span data-ttu-id="17451-139">Дополнительную информацию можно узнать [в статье перемещение пользователей в другой пул в Lync Server 2013](lync-server-2013-move-users-to-another-pool.md).</span><span class="sxs-lookup"><span data-stu-id="17451-139">For details, see [Move users to another pool in Lync Server 2013](lync-server-2013-move-users-to-another-pool.md).</span></span>

2.  <span data-ttu-id="17451-140">Остановите все службы Lync Server в устройстве для обеспечения связи в филиалах.</span><span class="sxs-lookup"><span data-stu-id="17451-140">Stop all Lync Server services on the Survivable Branch Appliance.</span></span> <span data-ttu-id="17451-141">(Обратитесь к документации производителя устройства для обеспечения связи в филиалах).</span><span class="sxs-lookup"><span data-stu-id="17451-141">(See the Survivable Branch Appliance vendor documentation).</span></span>

3.  <span data-ttu-id="17451-142">Обновите интерфейсный пул Lync Server, с которым связано устройство для обеспечения связи в филиалах, выполнив указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="17451-142">Update the Lync Server Front End pool that the Survivable Branch Appliance is associated with, by following these steps:</span></span>
    
      - <span data-ttu-id="17451-143">Нажмите кнопку **Пуск**, выберите **Все программы**, **Microsoft Lync Server** и **Lync Server Topology Builder**.</span><span class="sxs-lookup"><span data-stu-id="17451-143">Click **Start**, click **All Programs**, click **Microsoft Lync Server**, and then click **Lync Server Topology Builder**.</span></span>
    
      - <span data-ttu-id="17451-144">Разверните узел **Сайты филиалов**.</span><span class="sxs-lookup"><span data-stu-id="17451-144">Expand **Branch Sites**.</span></span>
    
      - <span data-ttu-id="17451-145">Щелкните правой кнопкой мыши объект устройства для обеспечения связи в филиале, который необходимо изменить, и выберите команду **изменить свойства** .</span><span class="sxs-lookup"><span data-stu-id="17451-145">Right-click the Survivable Branch Appliance object to modify, and click **Edit Properties**</span></span>
    
      - <span data-ttu-id="17451-146">В разделе устойчивость выберите новый интерфейсный пул, с которым необходимо связать устройство для обеспечения связи в филиалах, а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="17451-146">Under Resiliency, select the new Front End pool the Survivable Branch Appliance is to be associated to, and then click **Next**.</span></span>
    
      - <span data-ttu-id="17451-147">В дереве консоли щелкните правой кнопкой мыши новое устройство для обеспечения связи в филиалах, выберите **топология**, а затем нажмите кнопку **опубликовать**.</span><span class="sxs-lookup"><span data-stu-id="17451-147">In the console tree, right-click the new Survivable Branch Appliance, click **Topology**, and then click **Publish**.</span></span>

4.  <span data-ttu-id="17451-148">Перезапустите все службы Lync Server на устройстве для обеспечения связи в филиалах.</span><span class="sxs-lookup"><span data-stu-id="17451-148">Restart all Lync Server Services on the Survivable Branch Appliance.</span></span>

5.  <span data-ttu-id="17451-149">Протестируйте устройство для обеспечения связи в филиалах.</span><span class="sxs-lookup"><span data-stu-id="17451-149">Test the Survivable Branch Appliance.</span></span> <span data-ttu-id="17451-150">Дополнительные сведения можно найти в статье [домашние пользователи на устройстве или сервере для обеспечения связи в филиалах в Lync Server 2013](lync-server-2013-home-users-on-a-survivable-branch-appliance-or-server.md).</span><span class="sxs-lookup"><span data-stu-id="17451-150">For details, see [Home users on a Survivable Branch Appliance or Server in Lync Server 2013](lync-server-2013-home-users-on-a-survivable-branch-appliance-or-server.md).</span></span>

6.  <span data-ttu-id="17451-151">Перемещение пользователей из пула переднего плана Lync Server на центральном сайте в устройство для обеспечения связи в филиалах.</span><span class="sxs-lookup"><span data-stu-id="17451-151">Move users from the Lync Server Front End pool at the central site to the Survivable Branch Appliance.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

