---
title: 'Lync Server 2013: определение шлюза ТСОП для сайта филиала'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Define a PSTN gateway for a branch site
ms:assetid: 87be2fe2-1d56-4062-b430-439d4536414c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398689(v=OCS.15)
ms:contentKeyID: 48184724
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c253f82001fef4dd52e19dccb11e7ac77bb12417
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34834717"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="define-a-pstn-gateway-for-a-branch-site-in-lync-server-2013"></a><span data-ttu-id="0d501-102">Определение шлюза ТСОП для сайта филиала в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0d501-102">Define a PSTN gateway for a branch site in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0d501-103">_**Тема последнего изменения:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="0d501-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="0d501-104">Выполните эту процедуру на центральном веб-сайте, который включает по крайней мере один пул переднего плана или сервер Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="0d501-104">Perform this procedure at the central site, which contains at least one Front End pool or Standard Edition server.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="0d501-105">Перед выполнением процедуры должны быть выполнены следующие условия:</span><span class="sxs-lookup"><span data-stu-id="0d501-105">Before you perform the procedure, the following conditions must be in place:</span></span> 
> <UL>
> <LI>
> <P><span data-ttu-id="0d501-106">Программа связи Lync&nbsp;Server 2013 должна быть настроена на центральном сайте.</span><span class="sxs-lookup"><span data-stu-id="0d501-106">Lync Server 2013&nbsp;communications software must be set up at the central site.</span></span></P>
> <LI>
> <P><span data-ttu-id="0d501-107">Сервер-посредник должен быть развернут на центральном сайте.</span><span class="sxs-lookup"><span data-stu-id="0d501-107">Mediation Server must be deployed at the central site.</span></span></P></LI></UL>



</div>

<div>

## <a name="to-define-a-pstn-gateway"></a><span data-ttu-id="0d501-108">Определение шлюза PSTN</span><span class="sxs-lookup"><span data-stu-id="0d501-108">To define a PSTN gateway</span></span>

1.  <span data-ttu-id="0d501-109">Нажмите кнопку **Пуск**, выберите **все программы**, а затем — **Microsoft Lync Server**, а затем — построитель **топологии Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="0d501-109">Click **Start**, click **All Programs**, click **Microsoft Lync Server**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="0d501-110">В дереве консоли разверните узел центрального сайта, разверните **узлы офисов филиалов**, разверните имя сайта филиала, для которого вы хотите определить шлюз для публичной коммутируемой телефонной сети (PSTN), а затем разверните раздел **Общие компоненты**.</span><span class="sxs-lookup"><span data-stu-id="0d501-110">In the console tree, expand the central site, expand **Branch Office Sites**, expand name of the branch site that you want to define a public switched telephone network (PSTN) gateway for, and then expand **Shared Components**.</span></span>

3.  <span data-ttu-id="0d501-111">Щелкните правой кнопкой **шлюзы PSTN**и выберите команду **создать шлюз IP/КТСОП**.</span><span class="sxs-lookup"><span data-stu-id="0d501-111">Right-click **PSTN gateways**, and then click **New IP/PSTN Gateway**.</span></span>

4.  <span data-ttu-id="0d501-112">В диалоговом окне **Определение нового шлюза IP/КТСОП** выберите пункт **FQDN или IP-адрес шлюза**, а затем введите полное доменное имя (FQDN) или IP-адрес шлюза, который вы развертываете на сайте филиала.</span><span class="sxs-lookup"><span data-stu-id="0d501-112">In the **Define New IP/PSTN Gateway** dialog box, click **Gateway FQDN or IP Address**, and then type the fully qualified domain name (FQDN) or IP address of the gateway that you are deploying at the branch site.</span></span>

5.  <span data-ttu-id="0d501-113">Выберите **прослушивающий порт для IP/КТСОП**и подтвердите значения по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="0d501-113">Click **Listening Port for IP/PSTN Gateway**, and then accept the default values.</span></span>

6.  <span data-ttu-id="0d501-114">В списке **транспортный протокол SIP** выберите транспортный протокол, который использует шлюз, и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="0d501-114">In the **SIP Transport Protocol** list, click the transport protocol the gateway uses, and then click **OK**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="0d501-115">Из соображений безопасности мы настоятельно рекомендуем использовать шлюз PSTN, поддерживающий протокол TLS.</span><span class="sxs-lookup"><span data-stu-id="0d501-115">For security reasons, we strongly recommend that you use a PSTN gateway that supports Transport Layer Security (TLS).</span></span>

    
    </div>

<div>


> [!TIP]  
> <span data-ttu-id="0d501-116">Используйте командлет <STRONG>Set-кспстнгатевай</STRONG> , чтобы изменить свойства шлюза PSTN.</span><span class="sxs-lookup"><span data-stu-id="0d501-116">Use the cmdlet <STRONG>Set-CsPstnGateway</STRONG> to modify properties of a PSTN gateway.</span></span> <span data-ttu-id="0d501-117">Подробные сведения об этом можно найти в разделе <A href="https://docs.microsoft.com/powershell/module/skype/Set-CsPstnGateway">Set-кспстнгатевай</A>в справке Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="0d501-117">For details, see <A href="https://docs.microsoft.com/powershell/module/skype/Set-CsPstnGateway">Set-CsPstnGateway</A>, in the Lync Server Management Shell Help.</span></span>



</div>

<span data-ttu-id="0d501-118">**Следующий шаг** для обеспечения устойчивости сайтов филиалов: [Настройка пользователей для обеспечения устойчивости сайтов филиалов в Lync Server 2013](lync-server-2013-configuring-users-for-branch-site-resiliency.md)</span><span class="sxs-lookup"><span data-stu-id="0d501-118">**Next step** for branch-site resiliency: [Configuring users for branch site resiliency in Lync Server 2013](lync-server-2013-configuring-users-for-branch-site-resiliency.md)</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="0d501-119">См. также</span><span class="sxs-lookup"><span data-stu-id="0d501-119">See Also</span></span>


[<span data-ttu-id="0d501-120">Параметры развертывания шлюза ТСОП в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0d501-120">PSTN gateway deployment options in Lync Server 2013</span></span>](lync-server-2013-pstn-gateway-deployment-options.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

