---
title: 'Lync Server 2013: нользователи, работающие дома на устройстве или сервере для обеспечения связи в филиалах'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Home users on a Survivable Branch Appliance or Server
ms:assetid: faf1ebb9-6d7d-4a58-8ff7-801b7b31d3ba
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413066(v=OCS.15)
ms:contentKeyID: 48185926
ms.date: 12/11/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ceabf8fe7d8f9068e60bbc20406d2496f815b04b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34834073"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="home-users-on-a-survivable-branch-appliance-or-server-in-lync-server-2013"></a><span data-ttu-id="dadc0-102">Пользователи, работающие дома на устройстве или сервере для обеспечения связи в филиалах, в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dadc0-102">Home users on a Survivable Branch Appliance or Server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="dadc0-103">_**Тема последнего изменения:** 2014-12-10_</span><span class="sxs-lookup"><span data-stu-id="dadc0-103">_**Topic Last Modified:** 2014-12-10_</span></span>

<span data-ttu-id="dadc0-104">Процесс доступа пользователей к сети с бесперебойной подразделением или работающем на нем сервере аналогичен процессу служб доступа к сети в пуле переднего плана.</span><span class="sxs-lookup"><span data-stu-id="dadc0-104">The process of homing users on a Survivable Branch Appliance or a Survivable Branch Server is similar to the process of homing users on a Front End pool.</span></span> <span data-ttu-id="dadc0-105">Проведите бесперебойную подсеть устройства филиалов или бесперебойно работающую процедуру сервера ветвей на центральном сайте.</span><span class="sxs-lookup"><span data-stu-id="dadc0-105">Perform the Survivable Branch Appliance or Survivable Branch Server procedure at the central site.</span></span>

<div>

## <a name="to-home-users-on-survivable-branch-appliance-or-survivable-branch-server"></a><span data-ttu-id="dadc0-106">Для домашних пользователей на бесперебойно работающем устройстве филиалов или на сервере, который находится в бесперебойном отделении</span><span class="sxs-lookup"><span data-stu-id="dadc0-106">To home users on Survivable Branch Appliance or Survivable Branch Server</span></span>

1.  <span data-ttu-id="dadc0-107">Прежде чем переносить пользователей на сервер или бесперебойную подписку, откройте командную консоль Lync Server Management Shell, а затем выполните одно из указанных ниже действий.</span><span class="sxs-lookup"><span data-stu-id="dadc0-107">Before moving users to the Survivable Branch Server or Survivable Branch Server, open the Lync Server Management Shell, and then do all of the following:</span></span>
    
      - <span data-ttu-id="dadc0-108">Запустите командлет **Test-кспстнаутбаундкалл** , чтобы убедиться в том, что запущенный сервер филиала работает и настроено подключение к телефонной сети общего пользования (PSTN).</span><span class="sxs-lookup"><span data-stu-id="dadc0-108">Run the cmdlet **Test-CsPstnOutboundCall** to verify that the Survivable Branch Server is running and that the public switched telephone network (PSTN) connectivity is configured.</span></span> <span data-ttu-id="dadc0-109">Если вам нужно изменить свойства шлюза PSTN, используйте командлет **Set-кспстнгатевай**.</span><span class="sxs-lookup"><span data-stu-id="dadc0-109">If you need to modify PSTN gateway properties, use the cmdlet **Set-CsPstnGateway**.</span></span>
    
      - <span data-ttu-id="dadc0-110">Запустите командлет **Get-ксвоицеполици** , чтобы убедиться в том, что пользователи, которые будут размещены на сервере для работающего филиала, имеют соответствующую политику маршрутизации VoIP.</span><span class="sxs-lookup"><span data-stu-id="dadc0-110">Run the cmdlet **Get-CsVoicePolicy** to verify that the users who will be homed on the Survivable Branch Server have the appropriate VoIP routing policy.</span></span> <span data-ttu-id="dadc0-111">Если необходимо изменить политику VoIP, используйте командлет **Set-ксвоицеполици**.</span><span class="sxs-lookup"><span data-stu-id="dadc0-111">If you need to modify the VoIP policy, use the cmdlet **Set-CsVoicePolicy**.</span></span>
    
      - <span data-ttu-id="dadc0-112">Запустите командлет **Get-ксвоицемаилрераутингконфигуратион** , чтобы убедиться, что параметры перенаправления голосовой почты настроены.</span><span class="sxs-lookup"><span data-stu-id="dadc0-112">Run the cmdlet **Get-CsVoicemailReroutingConfiguration** to verify that the voice mail rerouting settings are configured.</span></span> <span data-ttu-id="dadc0-113">Если вам нужно изменить параметры перенаправления голосовой почты, используйте командлет **Set-ксвоицемаилрераутингконфигуратион**.</span><span class="sxs-lookup"><span data-stu-id="dadc0-113">If you need to modify the voice mail rerouting settings, use the cmdlet **Set-CsVoicemailReroutingConfiguration**.</span></span>

2.  <span data-ttu-id="dadc0-114">В командной консоли Lync Server выполните командлет **Move-CsUser** , чтобы переместить домашних пользователей.</span><span class="sxs-lookup"><span data-stu-id="dadc0-114">In the Lync Server Management Shell, run the cmdlet **Move-CsUser** to move home users.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="dadc0-115">Вы также можете использовать панель управления Lync Server для проверки необходимых и домашних пользователей.</span><span class="sxs-lookup"><span data-stu-id="dadc0-115">You can also use Lync Server Control Panel to verify prerequisites and home users.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="dadc0-116">Пользователи, расположенные на устройстве с бесперебойной подразделением Lync Server, не могут создавать новые комнаты чата и просматривать открытку для существующих комнат.</span><span class="sxs-lookup"><span data-stu-id="dadc0-116">Users who are homed on a Lync Server Survivable Branch Appliance are unable to create new chat rooms or view the room card for existing rooms.</span></span>



</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="dadc0-117">См. также</span><span class="sxs-lookup"><span data-stu-id="dadc0-117">See Also</span></span>


[<span data-ttu-id="dadc0-118">Test-CsPstnOutboundCall</span><span class="sxs-lookup"><span data-stu-id="dadc0-118">Test-CsPstnOutboundCall</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsPstnOutboundCall)  
[<span data-ttu-id="dadc0-119">Get-Ксвоицеполици</span><span class="sxs-lookup"><span data-stu-id="dadc0-119">Get-CsVoicePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsVoicePolicy)  
[<span data-ttu-id="dadc0-120">Get-CsVoicemailReroutingConfiguration</span><span class="sxs-lookup"><span data-stu-id="dadc0-120">Get-CsVoicemailReroutingConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsVoicemailReroutingConfiguration)  
[<span data-ttu-id="dadc0-121">Move-CsUser</span><span class="sxs-lookup"><span data-stu-id="dadc0-121">Move-CsUser</span></span>](https://docs.microsoft.com/powershell/module/skype/Move-CsUser)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

