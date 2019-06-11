---
title: 'Lync Server 2013: определение устройства или сервера для обеспечения связи в филиалах'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Define a Survivable Branch Appliance or Server
ms:assetid: 1f49cfbe-30b3-4600-af15-47cb2f58d18a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398280(v=OCS.15)
ms:contentKeyID: 48183583
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dadaa26f6a951995906ed29ffd0615da16066928
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34834719"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="define-a-survivable-branch-appliance-or-server-in-lync-server-2013"></a><span data-ttu-id="e691f-102">Определение устройства или сервера для обеспечения связи в филиалах в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e691f-102">Define a Survivable Branch Appliance or Server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e691f-103">_**Тема последнего изменения:** 2012-10-07_</span><span class="sxs-lookup"><span data-stu-id="e691f-103">_**Topic Last Modified:** 2012-10-07_</span></span>

<span data-ttu-id="e691f-104">Если вы не определили работающее устройство филиала или сервер при добавлении в топологию, выполните эту процедуру на центральном сайте.</span><span class="sxs-lookup"><span data-stu-id="e691f-104">Perform this procedure at the central site if you did not define the Survivable Branch Appliance or Server when you added it to your topology.</span></span>

<div>

## <a name="to-define-a-survivable-branch-appliance-or-survivable-branch-server"></a><span data-ttu-id="e691f-105">Определение бесперебойно работающего устройства филиала или работающего сервера подразделения</span><span class="sxs-lookup"><span data-stu-id="e691f-105">To define a Survivable Branch Appliance or Survivable Branch Server</span></span>

1.  <span data-ttu-id="e691f-106">Нажмите кнопку **Пуск**, выберите **все программы**, а затем — **Microsoft Lync Server 2013**и нажмите кнопку Построитель **топологии Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="e691f-106">Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="e691f-107">В дереве консоли разверните узел центрального сайта, разверните **узлы филиалов**, а затем разверните имя сайта ветви, на котором вы планируете развернуть работающее устройство филиала или его бесперебойный сервер.</span><span class="sxs-lookup"><span data-stu-id="e691f-107">In the console tree, expand the central site, expand **Branch sites**, and then expand the name of the branch site where you plan to deploy the Survivable Branch Appliance or Survivable Branch Server.</span></span>

3.  <span data-ttu-id="e691f-108">Щелкните правой кнопкой \*\*\*\* мыши бесперебойно работающие филиалы, а затем выберите команду создать работающее **устройство филиала**.</span><span class="sxs-lookup"><span data-stu-id="e691f-108">Right-click **Survivable Branch Appliances**, and then click **New Survivable Branch Appliance**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="e691f-109"><STRONG>Бесперебойно</STRONG> работающих филиалы — это область, в которой вы определяете бесперебойные серверы филиалов и бесперебойные устройства ветвления.</span><span class="sxs-lookup"><span data-stu-id="e691f-109"><STRONG>Survivable Branch Appliances</STRONG> is where you define Survivable Branch Servers and Survivable Branch Appliances.</span></span>

    
    </div>

4.  <span data-ttu-id="e691f-110">В диалоговом окне **Определение бесперебойной работы устройства** филиала \*\*\*\* выберите полное доменное имя (FQDN) для работающего устройства филиала или его бесперебойный сервер, который будет развертываться на этом сайте филиала, а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="e691f-110">In the **Define Survivable Branch Appliance** dialog box, click **FQDN**, type the fully qualified domain name (FQDN) of the Survivable Branch Appliance or Survivable Branch Server you will deploy at this branch site, and then click **Next**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="e691f-111">Если вы определяете бесперебойную подстановку, имя, которое вы ввели в <STRONG>полном доменном</STRONG> имени, должно совпадать с именем бесперебойного устройства, которое вы <STRONG></STRONG> назначили атрибуту "пользовательское устройство".</span><span class="sxs-lookup"><span data-stu-id="e691f-111">If you are defining a Survivable Branch Appliance, the name you enter in <STRONG>FQDN</STRONG> must be the same as the Survivable Branch Appliance FQDN you assigned to the <STRONG>servicePrincipalName</STRONG> attribute.</span></span> <span data-ttu-id="e691f-112">Дополнительные сведения можно найти <A href="lync-server-2013-add-a-survivable-branch-appliance-to-active-directory.md">в разделе Добавление работающего устройства филиала в Active Directory в Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="e691f-112">For details, see <A href="lync-server-2013-add-a-survivable-branch-appliance-to-active-directory.md">Add a Survivable Branch Appliance to Active Directory in Lync Server 2013</A>.</span></span>

    
    </div>

5.  <span data-ttu-id="e691f-113">Щелкните элемент **пул переднего плана**, щелкните сервер переднего плана (пул служб пользователей) на центральном сайте, к которому можно подключиться, и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="e691f-113">Click **Front End pool**, click the Front End Server (User Services pool) at the central site that this Survivable Branch Appliance or Survivable Branch Server will connect to, and then click **Next**.</span></span>

6.  <span data-ttu-id="e691f-114">Щелкните **граничный сервер**, выберите пул пограничного пула, который будет подключаться к сети, чтобы обеспечить подключение к ним для удаленных пользователей на сайте филиала, а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="e691f-114">Click **Edge Server**, click the Edge pool that this Survivable Branch Appliance or Survivable Branch Server will connect to provide PSTN connectivity to remote users of the branch site, and then click **Next**.</span></span>

7.  <span data-ttu-id="e691f-115">Выберите **полное доменное имя или IP-адрес шлюза**, а затем введите полное доменное имя или IP-адрес узла шлюза, с которым может быть установлено подключение для входящей или исходящей маршрутизации по протоколу PSTN.</span><span class="sxs-lookup"><span data-stu-id="e691f-115">Click **Gateway FQDN or IP Address**, and then type the FQDN or IP address of the gateway peer that the Survivable Branch Appliance or Survivable Branch Server is associated with for routing inbound or outbound PSTN calls.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="e691f-116">Если вы определяете бесперебойно работающее устройство ветвления, это шлюз, на который сервер-посредник может находиться в работающем устройстве филиала, подключается к сети PSTN.</span><span class="sxs-lookup"><span data-stu-id="e691f-116">If you are defining a Survivable Branch Appliance, this is the gateway to which the Mediation Server inside the Survivable Branch Appliance will connect for PSTN connectivity.</span></span>

    
    </div>

8.  <span data-ttu-id="e691f-117">Выберите **прослушивающий порт для IP/КТСОП**и подтвердите порт по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="e691f-117">Click **Listening Port for IP/PSTN Gateway**, and then accept the default port.</span></span>

9.  <span data-ttu-id="e691f-118">В **транспортном протоколе SIP**выберите транспортный протокол, который будет использоваться для работающего устройства филиала или для работающего филиала, а затем нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="e691f-118">In **Sip Transport Protocol**, click the transport protocol the Survivable Branch Appliance or Survivable Branch Server will use, and then click **Finish**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="e691f-119">По соображениям безопасности мы настоятельно рекомендуем использовать TLS-защиту.</span><span class="sxs-lookup"><span data-stu-id="e691f-119">For security reasons, we strongly recommend that you use Transport Layer Security (TLS).</span></span> <span data-ttu-id="e691f-120">Если вы определяете работающее устройство филиала, ознакомьтесь с соответствующей документацией поставщика филиала, чтобы убедиться в том, что устройство, поддерживающее бесперебойную ветвь, поддерживает протокол TLS.</span><span class="sxs-lookup"><span data-stu-id="e691f-120">If you are defining a Survivable Branch Appliance, refer to your Survivable Branch Appliance vendor documentation to verify that your Survivable Branch Appliance supports the TLS protocol.</span></span>

    
    </div>

10. <span data-ttu-id="e691f-121">В дереве консоли щелкните правой кнопкой мыши новое работающее устройство или сервер филиала, выберите пункт **топология**и нажмите кнопку **опубликовать**.</span><span class="sxs-lookup"><span data-stu-id="e691f-121">In the console tree, right-click the new Survivable Branch Appliance or Server, click **Topology**, and then click **Publish**.</span></span>

<span data-ttu-id="e691f-122">**Следующий этап**: [развертывание бесперебойно работающего устройства филиала или сервера с помощью Lync Server 2013 — задачи сайта ответвления](lync-server-2013-deploy-a-survivable-branch-appliance-or-server-branch-site-task.md)</span><span class="sxs-lookup"><span data-stu-id="e691f-122">**Next step**: [Deploy a Survivable Branch Appliance or Server with Lync Server 2013 - branch site task](lync-server-2013-deploy-a-survivable-branch-appliance-or-server-branch-site-task.md)</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

