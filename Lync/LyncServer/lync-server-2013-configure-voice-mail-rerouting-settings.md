---
title: 'Lync Server 2013: настройка параметров повторной маршрутизации для голосовой почты'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure voice mail rerouting settings
ms:assetid: 7ab6be28-eabb-4a79-a796-648887d71b83
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398606(v=OCS.15)
ms:contentKeyID: 48184593
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 73aa16f7c18665c0b74c1e31e2ce888abdbe1c5a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34841307"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-voice-mail-rerouting-settings-in-lync-server-2013"></a><span data-ttu-id="344ba-102">Настройка параметров повторной маршрутизации для голосовой почты в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="344ba-102">Configure voice mail rerouting settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="344ba-103">_**Тема последнего изменения:** 2012-10-18_</span><span class="sxs-lookup"><span data-stu-id="344ba-103">_**Topic Last Modified:** 2012-10-18_</span></span>

<span data-ttu-id="344ba-104">Бесперебойно доступные устройства филиалов и бесперебойные серверы филиалов могут обеспечивать бесперебойную обработку голосовой почты для пользователей филиалов при отключении глобальной сети, если на центральном сайте установлена служба единой системы обмена сообщениями Exchange (UM) и установлен автоматический секретарь (AA) сообщений Exchange UM.</span><span class="sxs-lookup"><span data-stu-id="344ba-104">Survivable Branch Appliances and Survivable Branch Servers can provide voice mail survivability for branch users during a WAN outage, if Exchange Unified Messaging (UM) is installed at the central site and an Exchange UM Message Auto Attendant (AA) is deployed.</span></span> <span data-ttu-id="344ba-105">Мы рекомендуем администраторам Exchange настроить конфигурацию AA таким образом, чтобы она принимала только сообщения, что отключает другие универсальные функции, такие как передача пользователю или передача оператору.</span><span class="sxs-lookup"><span data-stu-id="344ba-105">We recommend that your Exchange administrator configure the AA to accept messages only, which disables other generic functionality, such as transfer to a user or transfer to an operator.</span></span> <span data-ttu-id="344ba-106">Кроме того, вы можете использовать стандартную AA или AA, настроенные для направления звонка.</span><span class="sxs-lookup"><span data-stu-id="344ba-106">Alternatively, you might use a generic AA or an AA customized to route the call.</span></span>

<span data-ttu-id="344ba-107">Дополнительные сведения можно найти в разделе "Подготовка к бесперебойной работам голосовой почты" [требований к устойчивости сайтов филиалов для Lync Server 2013](lync-server-2013-branch-site-resiliency-requirements.md) в документации по планированию.</span><span class="sxs-lookup"><span data-stu-id="344ba-107">For details, see the “Preparing for Voice Mail Survivability” section of [Branch-site resiliency requirements for Lync Server 2013](lync-server-2013-branch-site-resiliency-requirements.md) in the Planning documentation.</span></span>

<div>

## <a name="to-configure-voice-mail-survivability"></a><span data-ttu-id="344ba-108">Настройка бесперебойной голосовой почты</span><span class="sxs-lookup"><span data-stu-id="344ba-108">To configure voice mail survivability</span></span>

1.  <span data-ttu-id="344ba-109">Попросите администратора Exchange настроить AA таким образом, чтобы она принимала только сообщения (в оболочке Exchange используется следующий командлет: \*\* \<Set-\> умаутоаттендант AA Name-каллсомеонинаблед $false\*\*.</span><span class="sxs-lookup"><span data-stu-id="344ba-109">Ask your Exchange administrator to configure the AA to accept messages only (in the Exchange Shell use the following cmdlet: **Set-UMAutoAttendant \<AA name\> -CallSomeoneEnabled $false**.</span></span> <span data-ttu-id="344ba-110">Параметр, указывающий, что разрешение на выход для сообщений (*сендвоицемсженаблед*) по умолчанию имеет значение истина.</span><span class="sxs-lookup"><span data-stu-id="344ba-110">The parameter that specifies to allow leaving messages (*SendVoiceMsgEnabled*) is true by default.</span></span>

2.  <span data-ttu-id="344ba-111">В командной консоли Lync Server с помощью командлета **New-ксвоицемаилрераутингконфигуратион** Настройте номер телефона для номера AA в качестве номера автосекретаря UM в конфигурации перенаправления голосовой почты в работающем устройстве филиала или Сервер с бесперебойной подразделением.</span><span class="sxs-lookup"><span data-stu-id="344ba-111">In the Lync Server Management Shell, use the **New-CSVoiceMailReroutingConfiguration** cmdlet to set the AA phone number as the Exchange UM Auto Attendant phone number in the voice mail rerouting configuration on the Survivable Branch Appliance or Survivable Branch Server.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="344ba-112">Если позже вам потребуется изменить параметры перенаправления голосовой почты, используйте командлет <STRONG>Set-ксвоицемаилрераутингконфигуратион</STRONG> .</span><span class="sxs-lookup"><span data-stu-id="344ba-112">If you need to modify the voice mail rerouting setting later, use the <STRONG>Set-CsVoiceMailReRoutingConfiguration</STRONG> cmdlet to do so.</span></span> <span data-ttu-id="344ba-113">Сведения о <STRONG>новых</STRONG> и <STRONG>множеств-ксвоицемаилрераутингконфигуратионх</STRONG>можно получить в разделах справки оболочки.</span><span class="sxs-lookup"><span data-stu-id="344ba-113">For details, about <STRONG>New-</STRONG> and <STRONG>Set-CSVoiceMailReroutingConfiguration</STRONG>, in the Shell Help topics.</span></span>

    
    </div>

3.  <span data-ttu-id="344ba-114">Задайте номер доступа к абоненту UM-среде Exchange, соответствующий абоненту Exchange для филиала в качестве номера доступа подписчика UM в конфигурации перенаправления голосовой почты на работающем устройстве филиала или работающем сервере, который находится в бесперебойном подразделении.</span><span class="sxs-lookup"><span data-stu-id="344ba-114">Set the Exchange UM subscriber access number that corresponds to the branch user’s Exchange UM dial plan as the Exchange UM subscriber access number in the voice mail rerouting configuration on the Survivable Branch Appliance or Survivable Branch Server.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="344ba-115">Настройте абонентскую группу Exchange UM так, чтобы была доступна только одна абонентская группа, связанная со всеми пользователями филиалов, которым нужен доступ к функциям получения голосовой почты в случае сбоя в глобальной сети.</span><span class="sxs-lookup"><span data-stu-id="344ba-115">Configure the Exchange UM users’ dial plan so that there is only one dial plan associated with all branch users who need access to the Get Voice Mail functionality during a WAN outage.</span></span>

    
    </div>

<span data-ttu-id="344ba-116">**Следующий шаг** к бесперебойно работающим устройствам филиалов и оставшимся серверам филиалов: [домашние пользователи на устройстве с бесперебойной ветвью или на сервере в Lync Server 2013](lync-server-2013-home-users-on-a-survivable-branch-appliance-or-server.md).</span><span class="sxs-lookup"><span data-stu-id="344ba-116">**Next step** for Survivable Branch Appliances or Survivable Branch Servers: [Home users on a Survivable Branch Appliance or Server in Lync Server 2013](lync-server-2013-home-users-on-a-survivable-branch-appliance-or-server.md).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

