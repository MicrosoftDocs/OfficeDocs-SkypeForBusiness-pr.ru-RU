---
title: 'Lync Server 2013: развертывание устройства или сервера для обеспечения связи в филиалах'
description: 'Lync Server 2013: развертывание устройства или сервера для обеспечения связи в филиалах.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying a Survivable Branch Appliance or Server
ms:assetid: cb780c14-dc5f-41ba-8092-f20ae905bd16
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398849(v=OCS.15)
ms:contentKeyID: 48185643
ms.date: 12/11/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b8c8610ab85b61d33a5f181f1d5f51d0e5095f49
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48558595"
---
# <a name="deploying-a-survivable-branch-appliance-or-server-with-lync-server-2013"></a><span data-ttu-id="652e1-103">Развертывание устройства или сервера для обеспечения связи в филиалах с помощью Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="652e1-103">Deploying a Survivable Branch Appliance or Server with Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="652e1-104">_**Последнее изменение темы:** 2014-12-10_</span><span class="sxs-lookup"><span data-stu-id="652e1-104">_**Topic Last Modified:** 2014-12-10_</span></span>

<span data-ttu-id="652e1-105">Отказоустойчивая Корпоративная голосовая связь относится к устойчивости сайта филиала, то есть возможность предоставлять непрерывную службу голосовой связи пользователям сайта филиала в случае, если ссылка на центральный сайт становится недоступна.</span><span class="sxs-lookup"><span data-stu-id="652e1-105">Resilient Enterprise Voice refers to branch-site resiliency, that is, the ability to provide continuous Enterprise Voice service to branch site users in the event that the link to the central site becomes unavailable.</span></span>

<span data-ttu-id="652e1-106">Для малых и средних сайтов филиалов (сайты филиалов с 25 до 1 000 пользователей) рекомендуется развернуть устройство для обеспечения связи в филиалах, которое будет завершать вызовы по телефонной сети общего пользования с помощью встроенного шлюза PSTN или магистрали SIP поставщику услуг телефонной связи.</span><span class="sxs-lookup"><span data-stu-id="652e1-106">For small and medium-sized branch sites (branch sites with 25 to 1,000 users), we recommend deploying a Survivable Branch Appliance, which will terminate public switched telephone network (PSTN) calls by using its built-in PSTN gateway or a SIP trunk to a telephone service provider.</span></span> <span data-ttu-id="652e1-107">Устройство для обеспечения связи в филиалах — это стороннее устройство, включающее в себя блейд-сервер, на котором работает операционная система Windows Server 2008 R2, регистратор Lync Server 2013, программное обеспечение сервера-посредника и шлюз PSTN, все в корпусах с одним устройством.</span><span class="sxs-lookup"><span data-stu-id="652e1-107">A Survivable Branch Appliance is a third-party device that includes a blade server running the Windows Server 2008 R2 operating system, Lync Server 2013 Registrar, Mediation Server software, and a PSTN gateway, all in a single appliance chassis.</span></span>

<span data-ttu-id="652e1-108">Для сайтов филиалов с 1 000 до 5 000 и без отказоустойчивой глобальной сети рекомендуется подключить к поставщику телефонной связи сервер для обеспечения связи в филиалах с шлюзом PSTN или магистральной магистралью SIP.</span><span class="sxs-lookup"><span data-stu-id="652e1-108">For branch sites with 1,000 to 5,000 users and no resilient WAN, we recommend a Survivable Branch Server connected to either a PSTN gateway or a SIP trunk to a telephone service provider.</span></span> <span data-ttu-id="652e1-109">Сервер для обеспечения связи в филиалах — это компьютер с Windows Server, на котором установлено программное обеспечение регистратора и сервер-посредник.</span><span class="sxs-lookup"><span data-stu-id="652e1-109">A Survivable Branch Server is a Windows Server-based computer that has Registrar and Mediation Server software installed on it.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="652e1-110">Для сайтов филиалов с более чем 5 000 пользователями и выделенными администраторами Lync Server рекомендуется использовать полное развертывание Lync Server 2013, отделенное от центрального сайта.</span><span class="sxs-lookup"><span data-stu-id="652e1-110">For branch sites with more than 5,000 users and dedicated Lync Server administrators, we recommend a full Lync Server 2013 deployment, separate from that of the central site.</span></span><BR><span data-ttu-id="652e1-111">Дополнительные сведения о выборе оптимального решения устойчивости для сайтов филиалов в Организации, в том числе необходимых условий и рекомендаций по планированию, приведены в разделе <A href="lync-server-2013-branch-site-resiliency-requirements.md">требования к устойчивости сайтов филиалов для Lync Server 2013</A> в документации по планированию.</span><span class="sxs-lookup"><span data-stu-id="652e1-111">For details about choosing the best resiliency solution for the branch sites in your organization, including prerequisites and planning considerations, see <A href="lync-server-2013-branch-site-resiliency-requirements.md">Branch-site resiliency requirements for Lync Server 2013</A> in the Planning documentation.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="652e1-112">Пользователи, размещенные на устройстве для обеспечения связи в филиалах Lync Server, не могут создавать новые комнаты чата или просматривать карточку комнаты для существующих комнат.</span><span class="sxs-lookup"><span data-stu-id="652e1-112">Users who are homed on a Lync Server Survivable Branch Appliance are unable to create new chat rooms or view the room card for existing rooms.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="652e1-113">Содержание</span><span class="sxs-lookup"><span data-stu-id="652e1-113">In This Section</span></span>

  - [<span data-ttu-id="652e1-114">Развертывание устройства или сервера для обеспечения связи в филиалах с помощью Lync Server 2013-Central Site Tasks</span><span class="sxs-lookup"><span data-stu-id="652e1-114">Deploying a Survivable Branch Appliance or Server with Lync Server 2013 - central site tasks</span></span>](lync-server-2013-deploying-a-survivable-branch-appliance-or-server-central-site-tasks.md)

  - [<span data-ttu-id="652e1-115">Развертывание устройства или сервера для обеспечения связи в филиалах с помощью Lync Server 2013 — задача сайта филиала</span><span class="sxs-lookup"><span data-stu-id="652e1-115">Deploy a Survivable Branch Appliance or Server with Lync Server 2013 - branch site task</span></span>](lync-server-2013-deploy-a-survivable-branch-appliance-or-server-branch-site-task.md)

  - [<span data-ttu-id="652e1-116">Настройка пользователей для обеспечения устойчивости сайта филиала в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="652e1-116">Configuring users for branch site resiliency in Lync Server 2013</span></span>](lync-server-2013-configuring-users-for-branch-site-resiliency.md)

  - [<span data-ttu-id="652e1-117">Домашние пользователи на устройстве или сервере для обеспечения связи в филиалах в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="652e1-117">Home users on a Survivable Branch Appliance or Server in Lync Server 2013</span></span>](lync-server-2013-home-users-on-a-survivable-branch-appliance-or-server.md)

  - [<span data-ttu-id="652e1-118">Приложения: устройства и серверы для обеспечения связи в филиалах в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="652e1-118">Appendices: Survivable Branch Appliances and Servers in Lync Server 2013</span></span>](lync-server-2013-appendices-survivable-branch-appliances-and-servers.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="652e1-119">См. также</span><span class="sxs-lookup"><span data-stu-id="652e1-119">See Also</span></span>


[<span data-ttu-id="652e1-120">Развертывание Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="652e1-120">Deploying Lync Server 2013</span></span>](lync-server-2013-deploying-lync-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

