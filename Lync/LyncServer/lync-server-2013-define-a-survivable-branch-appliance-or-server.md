---
title: 'Lync Server 2013: определение устройства или сервера для обеспечения связи в филиалах'
description: 'Lync Server 2013: определение устройства или сервера для обеспечения связи в филиалах.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Define a Survivable Branch Appliance or Server
ms:assetid: 1f49cfbe-30b3-4600-af15-47cb2f58d18a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398280(v=OCS.15)
ms:contentKeyID: 48183583
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 946aec82f33dffe268fefb3548b8db2f5c19e1a8
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48567765"
---
# <a name="define-a-survivable-branch-appliance-or-server-in-lync-server-2013"></a><span data-ttu-id="ac6f7-103">Определение устройства или сервера для обеспечения связи в филиалах в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ac6f7-103">Define a Survivable Branch Appliance or Server in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ac6f7-104">_**Последнее изменение темы:** 2012-10-07_</span><span class="sxs-lookup"><span data-stu-id="ac6f7-104">_**Topic Last Modified:** 2012-10-07_</span></span>

<span data-ttu-id="ac6f7-105">Выполните эту процедуру на центральном сайте, если вы не определили устройство или сервер для обеспечения связи в филиалах при добавлении его в топологию.</span><span class="sxs-lookup"><span data-stu-id="ac6f7-105">Perform this procedure at the central site if you did not define the Survivable Branch Appliance or Server when you added it to your topology.</span></span>

<div>

## <a name="to-define-a-survivable-branch-appliance-or-survivable-branch-server"></a><span data-ttu-id="ac6f7-106">Определение устройства для обеспечения связи в филиалах или сервера для обеспечения связи в филиалах</span><span class="sxs-lookup"><span data-stu-id="ac6f7-106">To define a Survivable Branch Appliance or Survivable Branch Server</span></span>

1.  <span data-ttu-id="ac6f7-107">Нажмите кнопку **Пуск**, последовательно выберите пункты **все программы**, **Microsoft Lync Server 2013**и **Построитель топологий Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="ac6f7-107">Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="ac6f7-108">В дереве консоли разверните узел центрального сайта, разверните узел **сайты филиалов**, а затем — имя сайта филиала, на котором планируется развернуть устройство для обеспечения связи в филиалах или сервер для обеспечения связи в филиалах.</span><span class="sxs-lookup"><span data-stu-id="ac6f7-108">In the console tree, expand the central site, expand **Branch sites**, and then expand the name of the branch site where you plan to deploy the Survivable Branch Appliance or Survivable Branch Server.</span></span>

3.  <span data-ttu-id="ac6f7-109">Щелкните правой кнопкой мыши устройства для обеспечения связи в **филиалах**и выберите команду создать устройство для обеспечения связи в **филиалах**.</span><span class="sxs-lookup"><span data-stu-id="ac6f7-109">Right-click **Survivable Branch Appliances**, and then click **New Survivable Branch Appliance**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="ac6f7-110">Устройства для обеспечения связи в <STRONG>филиалах</STRONG> позволяют определить серверы для обеспечения связи в филиалах и устройства для обеспечения связи в филиалах.</span><span class="sxs-lookup"><span data-stu-id="ac6f7-110"><STRONG>Survivable Branch Appliances</STRONG> is where you define Survivable Branch Servers and Survivable Branch Appliances.</span></span>

    
    </div>

4.  <span data-ttu-id="ac6f7-111">В диалоговом окне **Определение устройства** для обеспечения связи в филиалах **выберите полное доменное имя, введите**полное доменное имя (FQDN) устройства или сервера для обеспечения связи в филиалах, которое будет развернуто на этом сайте филиала, а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="ac6f7-111">In the **Define Survivable Branch Appliance** dialog box, click **FQDN**, type the fully qualified domain name (FQDN) of the Survivable Branch Appliance or Survivable Branch Server you will deploy at this branch site, and then click **Next**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="ac6f7-112">При определении устройства для обеспечения связи в филиалах имя, введенное в поле <STRONG>полное доменное</STRONG> имя, должно совпадать с полным доменным именем устройства для обеспечения связи <STRONG>в</STRONG> филиалах, которое было назначено атрибуту "значение".</span><span class="sxs-lookup"><span data-stu-id="ac6f7-112">If you are defining a Survivable Branch Appliance, the name you enter in <STRONG>FQDN</STRONG> must be the same as the Survivable Branch Appliance FQDN you assigned to the <STRONG>servicePrincipalName</STRONG> attribute.</span></span> <span data-ttu-id="ac6f7-113">Сведения о том, <A href="lync-server-2013-add-a-survivable-branch-appliance-to-active-directory.md">как добавить устройство для обеспечения связи в филиалах, можно найти в Active Directory в Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="ac6f7-113">For details, see <A href="lync-server-2013-add-a-survivable-branch-appliance-to-active-directory.md">Add a Survivable Branch Appliance to Active Directory in Lync Server 2013</A>.</span></span>

    
    </div>

5.  <span data-ttu-id="ac6f7-114">Щелкните **интерфейсный пул**, выберите сервер переднего плана (пул служб пользователей) на центральном сайте, с которым будет подключаться это устройство для обеспечения связи в филиалах или сервером для обеспечения связи в филиалах, а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="ac6f7-114">Click **Front End pool**, click the Front End Server (User Services pool) at the central site that this Survivable Branch Appliance or Survivable Branch Server will connect to, and then click **Next**.</span></span>

6.  <span data-ttu-id="ac6f7-115">Щелкните **пограничный сервер**, выберите Пограничный пул, который будет подключаться к этому устройству для обеспечения связи в филиалах или сервере для обеспечения связи в филиалах для предоставления доступа к PSTN удаленным пользователям сайта филиала, а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="ac6f7-115">Click **Edge Server**, click the Edge pool that this Survivable Branch Appliance or Survivable Branch Server will connect to provide PSTN connectivity to remote users of the branch site, and then click **Next**.</span></span>

7.  <span data-ttu-id="ac6f7-116">Выберите **полное доменное имя шлюза или IP-адрес**, а затем введите полное доменное имя или IP-адрес узла шлюза, с которым связано устройство для обеспечения связи в филиалах или сервер для обеспечения связи в филиалах, с целью маршрутизации входящих или исходящих вызовов PSTN.</span><span class="sxs-lookup"><span data-stu-id="ac6f7-116">Click **Gateway FQDN or IP Address**, and then type the FQDN or IP address of the gateway peer that the Survivable Branch Appliance or Survivable Branch Server is associated with for routing inbound or outbound PSTN calls.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="ac6f7-117">При определении устройства обеспечения связи на филиалах здесь указывается шлюз, к которому подключается сервер-посредник в устройстве обеспечения связи для выхода в ТСОП.</span><span class="sxs-lookup"><span data-stu-id="ac6f7-117">If you are defining a Survivable Branch Appliance, this is the gateway to which the Mediation Server inside the Survivable Branch Appliance will connect for PSTN connectivity.</span></span>

    
    </div>

8.  <span data-ttu-id="ac6f7-118">Щелкните элемент **Listening Port for IP/PSTN Gateway** (Прослушивающий порт для шлюза IP/ТСОП), а затем подтвердите порт по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="ac6f7-118">Click **Listening Port for IP/PSTN Gateway**, and then accept the default port.</span></span>

9.  <span data-ttu-id="ac6f7-119">В разделе **транспортный протокол SIP**выберите транспортный протокол, который будет использоваться устройством для обеспечения связи в филиалах или сервером для обеспечения связи в филиалах, а затем нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="ac6f7-119">In **Sip Transport Protocol**, click the transport protocol the Survivable Branch Appliance or Survivable Branch Server will use, and then click **Finish**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="ac6f7-120">В целях безопасности мы настоятельно рекомендуем вам использовать протокол TLS.</span><span class="sxs-lookup"><span data-stu-id="ac6f7-120">For security reasons, we strongly recommend that you use Transport Layer Security (TLS).</span></span> <span data-ttu-id="ac6f7-121">Если необходимо определить устройство обеспечения связи на филиалах, обратитесь к документации производителей этих устройств, чтобы убедиться в поддержке протокола TLS.</span><span class="sxs-lookup"><span data-stu-id="ac6f7-121">If you are defining a Survivable Branch Appliance, refer to your Survivable Branch Appliance vendor documentation to verify that your Survivable Branch Appliance supports the TLS protocol.</span></span>

    
    </div>

10. <span data-ttu-id="ac6f7-122">В дереве консоли щелкните новое устройство или новый сервер для обеспечения связи в филиалах правой кнопкой мыши, выберите пункт **Topology** (Топология) и затем щелкните элемент **Publish** (Опубликовать).</span><span class="sxs-lookup"><span data-stu-id="ac6f7-122">In the console tree, right-click the new Survivable Branch Appliance or Server, click **Topology**, and then click **Publish**.</span></span>

<span data-ttu-id="ac6f7-123">**Следующий шаг**: [развертывание устройства или сервера для обеспечения связи в филиалах с помощью Lync Server 2013 — задача сайта филиала](lync-server-2013-deploy-a-survivable-branch-appliance-or-server-branch-site-task.md)</span><span class="sxs-lookup"><span data-stu-id="ac6f7-123">**Next step**: [Deploy a Survivable Branch Appliance or Server with Lync Server 2013 - branch site task](lync-server-2013-deploy-a-survivable-branch-appliance-or-server-branch-site-task.md)</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

