---
title: 'Lync Server 2013: определение шлюза PSTN для сайта филиала'
description: 'Lync Server 2013: определение шлюза PSTN для сайта филиала.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Define a PSTN gateway for a branch site
ms:assetid: 87be2fe2-1d56-4062-b430-439d4536414c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398689(v=OCS.15)
ms:contentKeyID: 48184724
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 17fb1004366fef17f57d7e8b7d14696e1e3f0fbe
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48567775"
---
# <a name="define-a-pstn-gateway-for-a-branch-site-in-lync-server-2013"></a><span data-ttu-id="e6895-103">Определение шлюза PSTN для сайта филиала в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e6895-103">Define a PSTN gateway for a branch site in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e6895-104">_**Последнее изменение темы:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="e6895-104">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="e6895-105">Выполните эту процедуру на центральном сайте, который содержит по крайней мере один интерфейсный пул или сервер Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="e6895-105">Perform this procedure at the central site, which contains at least one Front End pool or Standard Edition server.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="e6895-106">Перед выполнением процедуры должны соблюдаться следующие условия.</span><span class="sxs-lookup"><span data-stu-id="e6895-106">Before you perform the procedure, the following conditions must be in place:</span></span> 
> <UL>
> <LI>
> <P><span data-ttu-id="e6895-107">&nbsp;На центральном сайте должно быть настроено коммуникационное программное обеспечение Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e6895-107">Lync Server 2013&nbsp;communications software must be set up at the central site.</span></span></P>
> <LI>
> <P><span data-ttu-id="e6895-108">Сервер-посредник должен быть развернут на центральном сайте.</span><span class="sxs-lookup"><span data-stu-id="e6895-108">Mediation Server must be deployed at the central site.</span></span></P></LI></UL>



</div>

<div>

## <a name="to-define-a-pstn-gateway"></a><span data-ttu-id="e6895-109">Определение шлюза ТСОП</span><span class="sxs-lookup"><span data-stu-id="e6895-109">To define a PSTN gateway</span></span>

1.  <span data-ttu-id="e6895-110">В меню **Пуск** последовательно выберите пункты **Все программы**, **Microsoft Lync Server** и **Построитель топологий**.</span><span class="sxs-lookup"><span data-stu-id="e6895-110">Click **Start**, click **All Programs**, click **Microsoft Lync Server**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="e6895-111">В дереве консоли разверните центральный сайт, разверните узел **Сайты филиалов**, разверните имя сайта филиала, для которого вы хотите определить шлюз ТСОП, а затем разверните узел **Общие компоненты**.</span><span class="sxs-lookup"><span data-stu-id="e6895-111">In the console tree, expand the central site, expand **Branch Office Sites**, expand name of the branch site that you want to define a public switched telephone network (PSTN) gateway for, and then expand **Shared Components**.</span></span>

3.  <span data-ttu-id="e6895-112">Щелкните правой кнопкой мыши элемент **Шлюзы ТСОП** и выберите команду **Создать шлюз IP/ТСОП**.</span><span class="sxs-lookup"><span data-stu-id="e6895-112">Right-click **PSTN gateways**, and then click **New IP/PSTN Gateway**.</span></span>

4.  <span data-ttu-id="e6895-113">В диалоговом окне **Определение нового шлюза IP/ТСОП** щелкните элемент **Полное доменное имя или IP-адрес шлюза** и введите полное доменное имя или IP-адрес шлюза, который вы развертываете на сайте филиала.</span><span class="sxs-lookup"><span data-stu-id="e6895-113">In the **Define New IP/PSTN Gateway** dialog box, click **Gateway FQDN or IP Address**, and then type the fully qualified domain name (FQDN) or IP address of the gateway that you are deploying at the branch site.</span></span>

5.  <span data-ttu-id="e6895-114">Щелкните элемент **Прослушивающий порт для шлюза IP/ТСОП** и примите значения по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="e6895-114">Click **Listening Port for IP/PSTN Gateway**, and then accept the default values.</span></span>

6.  <span data-ttu-id="e6895-115">В списке **Транспортный протокол SIP** выберите транспортный протокол, используемый шлюзом, и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="e6895-115">In the **SIP Transport Protocol** list, click the transport protocol the gateway uses, and then click **OK**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="e6895-116">В целях обеспечения безопасности мы настоятельно рекомендуем использовать шлюз ТСОП, поддерживающий протокол TLS.</span><span class="sxs-lookup"><span data-stu-id="e6895-116">For security reasons, we strongly recommend that you use a PSTN gateway that supports Transport Layer Security (TLS).</span></span>

    
    </div>

<div>


> [!TIP]  
> <span data-ttu-id="e6895-117">Для изменения свойств шлюза ТСОП используйте командлет <STRONG>Set-CsPstnGateway</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="e6895-117">Use the cmdlet <STRONG>Set-CsPstnGateway</STRONG> to modify properties of a PSTN gateway.</span></span> <span data-ttu-id="e6895-118">Дополнительные сведения см. в разделе <A href="https://docs.microsoft.com/powershell/module/skype/Set-CsPstnGateway">Set – CsPstnGateway</A>в справке по консоли управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="e6895-118">For details, see <A href="https://docs.microsoft.com/powershell/module/skype/Set-CsPstnGateway">Set-CsPstnGateway</A>, in the Lync Server Management Shell Help.</span></span>



</div>

<span data-ttu-id="e6895-119">**Следующий шаг** к устойчивости сайта филиала: [Настройка пользователей для обеспечения устойчивости сайта филиала в Lync Server 2013](lync-server-2013-configuring-users-for-branch-site-resiliency.md)</span><span class="sxs-lookup"><span data-stu-id="e6895-119">**Next step** for branch-site resiliency: [Configuring users for branch site resiliency in Lync Server 2013](lync-server-2013-configuring-users-for-branch-site-resiliency.md)</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="e6895-120">См. также</span><span class="sxs-lookup"><span data-stu-id="e6895-120">See Also</span></span>


[<span data-ttu-id="e6895-121">Варианты развертывания шлюза PSTN в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e6895-121">PSTN gateway deployment options in Lync Server 2013</span></span>](lync-server-2013-pstn-gateway-deployment-options.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

