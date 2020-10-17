---
title: 'Lync Server 2013: Настройка параметров перенаправления голосовой почты'
description: 'Lync Server 2013: Настройка параметров перенаправления голосовой почты.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure voice mail rerouting settings
ms:assetid: 7ab6be28-eabb-4a79-a796-648887d71b83
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398606(v=OCS.15)
ms:contentKeyID: 48184593
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 669ea5585f9e732b6a49d9749b8939c14b4e0d9f
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48566735"
---
# <a name="configure-voice-mail-rerouting-settings-in-lync-server-2013"></a><span data-ttu-id="99e49-103">Настройка параметров перенаправления голосовой почты в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="99e49-103">Configure voice mail rerouting settings in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="99e49-104">_**Последнее изменение темы:** 2012-10-18_</span><span class="sxs-lookup"><span data-stu-id="99e49-104">_**Topic Last Modified:** 2012-10-18_</span></span>

<span data-ttu-id="99e49-105">Устройства для обеспечения связи в филиалах и серверы для обеспечения связи в филиалах могут обеспечить бесперебойную работу голосовой почты для пользователей филиала, если на центральном сайте установлена служба единой системы обмена сообщениями Exchange, а также выполняется развертывание автосекретаря сообщения Exchange единой системы обмена сообщениями (AA).</span><span class="sxs-lookup"><span data-stu-id="99e49-105">Survivable Branch Appliances and Survivable Branch Servers can provide voice mail survivability for branch users during a WAN outage, if Exchange Unified Messaging (UM) is installed at the central site and an Exchange UM Message Auto Attendant (AA) is deployed.</span></span> <span data-ttu-id="99e49-106">Мы рекомендуем, чтобы администратор Exchange настроил автосекретарь только для принятия сообщений, что отключает другие общие функциональные возможности, такие как передача пользователю и передача оператору.</span><span class="sxs-lookup"><span data-stu-id="99e49-106">We recommend that your Exchange administrator configure the AA to accept messages only, which disables other generic functionality, such as transfer to a user or transfer to an operator.</span></span> <span data-ttu-id="99e49-107">Также можно использовать обычный автосекретарь или автосекретарь, настроенный для маршрутизации вызовов.</span><span class="sxs-lookup"><span data-stu-id="99e49-107">Alternatively, you might use a generic AA or an AA customized to route the call.</span></span>

<span data-ttu-id="99e49-108">Для получения дополнительных сведений обратитесь к разделу "Подготовка к обеспечению бесперебойной работы голосовой почты" [требований к устойчивости сайта филиала для Lync Server 2013](lync-server-2013-branch-site-resiliency-requirements.md) в документации по планированию.</span><span class="sxs-lookup"><span data-stu-id="99e49-108">For details, see the “Preparing for Voice Mail Survivability” section of [Branch-site resiliency requirements for Lync Server 2013](lync-server-2013-branch-site-resiliency-requirements.md) in the Planning documentation.</span></span>

<div>

## <a name="to-configure-voice-mail-survivability"></a><span data-ttu-id="99e49-109">Настройка устойчивости голосовой почты</span><span class="sxs-lookup"><span data-stu-id="99e49-109">To configure voice mail survivability</span></span>

1.  <span data-ttu-id="99e49-110">Попросите администратора Exchange настроить AA так, чтобы она принимала только сообщения (в оболочке Exchange используется следующий командлет: **Set-UMAutoAttendant используется \<AA name\> -CallSomeoneEnabled $false**.</span><span class="sxs-lookup"><span data-stu-id="99e49-110">Ask your Exchange administrator to configure the AA to accept messages only (in the Exchange Shell use the following cmdlet: **Set-UMAutoAttendant \<AA name\> -CallSomeoneEnabled $false**.</span></span> <span data-ttu-id="99e49-111">Параметр (*SendVoiceMsgEnabled*), указывающий разрешение передачи сообщений, по умолчанию имеет значение True.</span><span class="sxs-lookup"><span data-stu-id="99e49-111">The parameter that specifies to allow leaving messages (*SendVoiceMsgEnabled*) is true by default.</span></span>

2.  <span data-ttu-id="99e49-112">В командной консоли Lync Server используйте командлет **New – ксвоицемаилрераутингконфигуратион** для установки номера телефона AA в качестве номера автосекретаря единой системы обмена сообщениями Exchange в конфигурации переадресации голосовой почты в устройстве для обеспечения связи в филиалах или сервере для обеспечения связи в филиалах.</span><span class="sxs-lookup"><span data-stu-id="99e49-112">In the Lync Server Management Shell, use the **New-CSVoiceMailReroutingConfiguration** cmdlet to set the AA phone number as the Exchange UM Auto Attendant phone number in the voice mail rerouting configuration on the Survivable Branch Appliance or Survivable Branch Server.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="99e49-113">Если позднее потребуется изменить настройку переадресации голосовой почты, воспользуйтесь командлетом <STRONG>Set-CsVoiceMailReRoutingConfiguration</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="99e49-113">If you need to modify the voice mail rerouting setting later, use the <STRONG>Set-CsVoiceMailReRoutingConfiguration</STRONG> cmdlet to do so.</span></span> <span data-ttu-id="99e49-114">Подробные сведения см. в описаниях командлетов <STRONG>New-</STRONG> и <STRONG>Set-CSVoiceMailReroutingConfiguration</STRONG> в разделах справки Shell.</span><span class="sxs-lookup"><span data-stu-id="99e49-114">For details, about <STRONG>New-</STRONG> and <STRONG>Set-CSVoiceMailReroutingConfiguration</STRONG>, in the Shell Help topics.</span></span>

    
    </div>

3.  <span data-ttu-id="99e49-115">Задайте номер доступа к абонентской группе единой системы обмена сообщениями Exchange, соответствующий абонентской группе единой системы обмена сообщениями Exchange, в качестве номера доступа абонентской группы единой системы обмена сообщениями Exchange в конфигурации переадресации голосовой почты в устройстве для обеспечения связи в филиалах или сервере для обеспечения связи в филиалах.</span><span class="sxs-lookup"><span data-stu-id="99e49-115">Set the Exchange UM subscriber access number that corresponds to the branch user’s Exchange UM dial plan as the Exchange UM subscriber access number in the voice mail rerouting configuration on the Survivable Branch Appliance or Survivable Branch Server.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="99e49-116">Настройте абонентскую группу пользователей единой системы обмена сообщениями Exchange таким образом, чтобы только одна абонентская группа была связана со всеми пользователями филиала, которым необходим доступ к функции получения голосовой почты во время сбоя глобальной сети.</span><span class="sxs-lookup"><span data-stu-id="99e49-116">Configure the Exchange UM users’ dial plan so that there is only one dial plan associated with all branch users who need access to the Get Voice Mail functionality during a WAN outage.</span></span>

    
    </div>

<span data-ttu-id="99e49-117">**Следующий шаг** к устройствам для обеспечения связи в филиалах или серверам для обеспечения связи в филиалах: [домашние пользователи на устройстве или сервере для обеспечения связи в филиалах в Lync Server 2013](lync-server-2013-home-users-on-a-survivable-branch-appliance-or-server.md).</span><span class="sxs-lookup"><span data-stu-id="99e49-117">**Next step** for Survivable Branch Appliances or Survivable Branch Servers: [Home users on a Survivable Branch Appliance or Server in Lync Server 2013](lync-server-2013-home-users-on-a-survivable-branch-appliance-or-server.md).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

