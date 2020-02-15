---
title: 'Lync Server 2013: домашние пользователи на устройстве или сервере для обеспечения связи в филиалах'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Home users on a Survivable Branch Appliance or Server
ms:assetid: faf1ebb9-6d7d-4a58-8ff7-801b7b31d3ba
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413066(v=OCS.15)
ms:contentKeyID: 48185926
ms.date: 12/11/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c6efd5991260ffeec3c6279857625eadfe34eca4
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42047457"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="home-users-on-a-survivable-branch-appliance-or-server-in-lync-server-2013"></a><span data-ttu-id="b7edb-102">Домашние пользователи на устройстве или сервере для обеспечения связи в филиалах в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b7edb-102">Home users on a Survivable Branch Appliance or Server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b7edb-103">_**Последнее изменение темы:** 2014-12-10_</span><span class="sxs-lookup"><span data-stu-id="b7edb-103">_**Topic Last Modified:** 2014-12-10_</span></span>

<span data-ttu-id="b7edb-104">Процесс, который пользователи могут обслуживать для обеспечения связи в филиалах или на сервере для обеспечения связи в филиалах, аналогичен процессу "пользователи из пула переднего плана".</span><span class="sxs-lookup"><span data-stu-id="b7edb-104">The process of homing users on a Survivable Branch Appliance or a Survivable Branch Server is similar to the process of homing users on a Front End pool.</span></span> <span data-ttu-id="b7edb-105">Выполните на центральном сайте устройство для обеспечения связи в филиалах или процесс обеспечения связи в филиалах.</span><span class="sxs-lookup"><span data-stu-id="b7edb-105">Perform the Survivable Branch Appliance or Survivable Branch Server procedure at the central site.</span></span>

<div>

## <a name="to-home-users-on-survivable-branch-appliance-or-survivable-branch-server"></a><span data-ttu-id="b7edb-106">Размещение пользователей на устройстве для обеспечения связи в филиалах или сервере для обеспечения связи в филиалах</span><span class="sxs-lookup"><span data-stu-id="b7edb-106">To home users on Survivable Branch Appliance or Survivable Branch Server</span></span>

1.  <span data-ttu-id="b7edb-107">Перед перемещением пользователей на сервер для обеспечения связи в филиалах или для обеспечения связи в филиалах откройте командную консоль Lync Server, а затем выполните все указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="b7edb-107">Before moving users to the Survivable Branch Server or Survivable Branch Server, open the Lync Server Management Shell, and then do all of the following:</span></span>
    
      - <span data-ttu-id="b7edb-108">Запустите командлет **Test-CsPstnOutboundCall** , чтобы убедиться в том, что сервер для обеспечения связи работает и настроено подключение к телефонной сети общего пользования (PSTN).</span><span class="sxs-lookup"><span data-stu-id="b7edb-108">Run the cmdlet **Test-CsPstnOutboundCall** to verify that the Survivable Branch Server is running and that the public switched telephone network (PSTN) connectivity is configured.</span></span> <span data-ttu-id="b7edb-109">Если требуется изменить свойства шлюза ТСОП, используйте командлет **Set-CsPstnGateway**.</span><span class="sxs-lookup"><span data-stu-id="b7edb-109">If you need to modify PSTN gateway properties, use the cmdlet **Set-CsPstnGateway**.</span></span>
    
      - <span data-ttu-id="b7edb-110">Выполните командлет **Get – CsVoicePolicy** , чтобы убедиться, что пользователи, которые будут размещены на сервере для обеспечения связи в филиале, имеют соответствующую политику маршрутизации VoIP.</span><span class="sxs-lookup"><span data-stu-id="b7edb-110">Run the cmdlet **Get-CsVoicePolicy** to verify that the users who will be homed on the Survivable Branch Server have the appropriate VoIP routing policy.</span></span> <span data-ttu-id="b7edb-111">Если требуется изменить политику VoIP, используйте командлет **Set-CsVoicePolicy**.</span><span class="sxs-lookup"><span data-stu-id="b7edb-111">If you need to modify the VoIP policy, use the cmdlet **Set-CsVoicePolicy**.</span></span>
    
      - <span data-ttu-id="b7edb-112">Запустите командлет **Get-CsVoicemailReroutingConfiguration**, чтобы убедиться, что настроены параметры перенаправления голосовой почты.</span><span class="sxs-lookup"><span data-stu-id="b7edb-112">Run the cmdlet **Get-CsVoicemailReroutingConfiguration** to verify that the voice mail rerouting settings are configured.</span></span> <span data-ttu-id="b7edb-113">Если требуется изменить параметры перенаправления голосовой почты, используйте командлет **Set-CsVoicemailReroutingConfiguration**.</span><span class="sxs-lookup"><span data-stu-id="b7edb-113">If you need to modify the voice mail rerouting settings, use the cmdlet **Set-CsVoicemailReroutingConfiguration**.</span></span>

2.  <span data-ttu-id="b7edb-114">В командной консоли Lync Server выполните командлет **Move – CsUser** , чтобы переместить домашние пользователи.</span><span class="sxs-lookup"><span data-stu-id="b7edb-114">In the Lync Server Management Shell, run the cmdlet **Move-CsUser** to move home users.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="b7edb-115">Вы также можете использовать панель управления Lync Server, чтобы проверить необходимые компоненты и домашние пользователи.</span><span class="sxs-lookup"><span data-stu-id="b7edb-115">You can also use Lync Server Control Panel to verify prerequisites and home users.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="b7edb-116">Пользователи, размещенные на устройстве для обеспечения связи в филиалах Lync Server, не могут создавать новые комнаты чата или просматривать карточку комнаты для существующих комнат.</span><span class="sxs-lookup"><span data-stu-id="b7edb-116">Users who are homed on a Lync Server Survivable Branch Appliance are unable to create new chat rooms or view the room card for existing rooms.</span></span>



</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="b7edb-117">См. также</span><span class="sxs-lookup"><span data-stu-id="b7edb-117">See Also</span></span>


[<span data-ttu-id="b7edb-118">Test-CsPstnOutboundCall</span><span class="sxs-lookup"><span data-stu-id="b7edb-118">Test-CsPstnOutboundCall</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsPstnOutboundCall)  
[<span data-ttu-id="b7edb-119">Get-CsVoicePolicy</span><span class="sxs-lookup"><span data-stu-id="b7edb-119">Get-CsVoicePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsVoicePolicy)  
[<span data-ttu-id="b7edb-120">Get — Ксвоицемаилрераутингконфигуратион</span><span class="sxs-lookup"><span data-stu-id="b7edb-120">Get-CsVoicemailReroutingConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsVoicemailReroutingConfiguration)  
[<span data-ttu-id="b7edb-121">Move — CsUser</span><span class="sxs-lookup"><span data-stu-id="b7edb-121">Move-CsUser</span></span>](https://docs.microsoft.com/powershell/module/skype/Move-CsUser)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

