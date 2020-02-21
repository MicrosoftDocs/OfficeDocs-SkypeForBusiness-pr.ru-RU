---
title: 'Lync Server 2013: Настройка диапазонов портов для клиентов Microsoft Lync'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring port ranges for your Microsoft Lync clients
ms:assetid: 287d5cea-7ada-461c-9b4a-9da2af315e71
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204760(v=OCS.15)
ms:contentKeyID: 48183694
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: abfe8c9848e5e015a22bcc7975c6bbdaf1c7465e
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42192942"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-port-ranges-for-your-microsoft-lync-clients-in-lync-server-2013"></a><span data-ttu-id="9f5a2-102">Настройка диапазонов портов для клиентов Microsoft Lync в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9f5a2-102">Configuring port ranges for your Microsoft Lync clients in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9f5a2-103">_**Последнее изменение темы:** 2014-04-22_</span><span class="sxs-lookup"><span data-stu-id="9f5a2-103">_**Topic Last Modified:** 2014-04-22_</span></span>

<span data-ttu-id="9f5a2-104">По умолчанию клиентские приложения Lync могут использовать любой порт между портами 1024 и 65535 при включении в сеанс связи; Это связано с тем, что для определенных диапазонов портов не включены автоматически клиенты.</span><span class="sxs-lookup"><span data-stu-id="9f5a2-104">By default, Lync client applications can use any port between ports 1024 and 65535 when involved in a communication session; this is because specific port ranges are not automatically enabled for clients.</span></span> <span data-ttu-id="9f5a2-105">Однако для использования качества обслуживания необходимо переназначить различные типы трафика (аудио, видео, мультимедиа, общий доступ к приложениям и передачу файлов) для ряда уникальных диапазонов портов.</span><span class="sxs-lookup"><span data-stu-id="9f5a2-105">In order to use Quality of Service, however, you will need to reassign the various traffic types (audio, video, media, application sharing, and file transfer) to a series of unique port ranges.</span></span> <span data-ttu-id="9f5a2-106">Это можно сделать с помощью командлета Set – CsConferencingConfiguration.</span><span class="sxs-lookup"><span data-stu-id="9f5a2-106">This can be done by using the Set-CsConferencingConfiguration cmdlet.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="9f5a2-107">Конечные пользователи не могут вносить эти изменения самостоятельно.</span><span class="sxs-lookup"><span data-stu-id="9f5a2-107">End users cannot make these changes themselves.</span></span> <span data-ttu-id="9f5a2-108">Изменения портов могут выполняться только администраторами с помощью командлета Set – CsConferencingConfiguration.</span><span class="sxs-lookup"><span data-stu-id="9f5a2-108">Port changes can only be made by administrators using the Set-CsConferencingConfiguration cmdlet.</span></span>



</div>

<span data-ttu-id="9f5a2-109">Вы можете определить, какие диапазоны портов используются в данный момент для сеансов связи, выполнив следующую команду в командной консоли управления Microsoft Lync Server 2013:</span><span class="sxs-lookup"><span data-stu-id="9f5a2-109">You can determine which port ranges are currently used for communication sessions by running the following command from within the Microsoft Lync Server 2013 Management Shell:</span></span>

    Get-CsConferencingConfiguration

<span data-ttu-id="9f5a2-110">Если вы не внесли какие-либо изменения в параметры конференц-связи после установки Lync Server 2013, необходимо получить сведения, содержащие следующие значения свойств:</span><span class="sxs-lookup"><span data-stu-id="9f5a2-110">Assuming that you have not made any changes to your conferencing settings since you installed Lync Server 2013, you should get back information that includes these property values:</span></span>

    ClientMediaPortRangeEnabled : False
    ClientAudioPort             : 5350
    ClientAudioPortRange        : 40
    ClientVideoPort             : 5350
    ClientVideoPortRange        : 40
    ClientAppSharingPort        : 5350
    ClientAppSharingPortRange   : 40
    ClientFileTransferPort      : 5350
    ClientTransferPortRange     : 40

<span data-ttu-id="9f5a2-111">Если внимательно посмотреть на предыдущие данные, можно увидеть две важных вещи.</span><span class="sxs-lookup"><span data-stu-id="9f5a2-111">If you look closely at the preceding output, you'll see two things of importance.</span></span> <span data-ttu-id="9f5a2-112">Во-первых, для свойства ClientMediaPortRangeEnabled задано значение False:</span><span class="sxs-lookup"><span data-stu-id="9f5a2-112">First, the ClientMediaPortRangeEnabled property is set to False:</span></span>

    ClientMediaPortRangeEnabled : False

<span data-ttu-id="9f5a2-113">Это важно, так как если для этого свойства задано значение false, клиенты Lync будут использовать любой доступный порт между портами 1024 и 65535 при включении в сеанс связи; Это справедливо независимо от других параметров порта (например, ClientMediaPort или Клиентвидеопорт).</span><span class="sxs-lookup"><span data-stu-id="9f5a2-113">That's important because, when this property is set to False, Lync clients will use any available port between ports 1024 and 65535 when involved in a communication session; this is true regardless of any other port settings (for example, ClientMediaPort or ClientVideoPort).</span></span> <span data-ttu-id="9f5a2-114">Если вы хотите ограничить использование указанного набора портов (и это нужно сделать при планировании реализации качества обслуживания), необходимо сначала включить диапазоны портов клиента для передачи данных.</span><span class="sxs-lookup"><span data-stu-id="9f5a2-114">If you want to restrict usage to a specified set of ports (and this is something you do want to do if you plan on implementing Quality of Service) then you must first enable client media port ranges.</span></span> <span data-ttu-id="9f5a2-115">Это можно сделать с помощью следующей команды Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="9f5a2-115">That can be done using the following Windows PowerShell command:</span></span>

    Set-CsConferencingConfiguration -ClientMediaPortRangeEnabled $True

<span data-ttu-id="9f5a2-p105">Приведенная выше команда активирует диапазоны портов мультимедиа клиентов для глобальной коллекции параметров конфигурации конференций. Однако данные настройки также могут применяться к области сайта или службы (только для службы сервера конференций). Чтобы включить диапазоны портов мультимедиа клиентов для определенного сайта или сервера, укажите идентификатор этого сайта или сервера при вызове команды Set-CsConferencingConfiguration:</span><span class="sxs-lookup"><span data-stu-id="9f5a2-p105">The preceding command enables client media port ranges for the global collection of conferencing configuration settings; however, these settings can also be applied to the site scope and/or the service scope (for the Conferencing Server service only). To enable client media port ranges for a specific site or server, specify the Identity of that site or server when calling Set-CsConferencingConfiguration:</span></span>

    Set-CsConferencingConfiguration -Identity "site:Redmond" -ClientMediaPortRangeEnabled $True

<span data-ttu-id="9f5a2-118">Или же вы можете использовать следующую команду, чтобы одновременно включить диапазоны порты для всех параметров конфигурации конференций:</span><span class="sxs-lookup"><span data-stu-id="9f5a2-118">Alternatively, you can use this command to simultaneously enable port ranges for all your conferencing configuration settings:</span></span>

    Get-CsConferencingConfiguration | Set-CsConferencingConfiguration  -ClientMediaPortRangeEnabled $True

<span data-ttu-id="9f5a2-119">Второй важный момент — в примере выходных данных показано, что по умолчанию набор диапазонов портов мультимедиа для каждого типа сетевого трафика идентичны:</span><span class="sxs-lookup"><span data-stu-id="9f5a2-119">The second thing of importance you will notice is that the sample output shows that, by default, the media port ranges set for each type of network traffic are identical:</span></span>

    ClientAudioPort             : 5350
    ClientVideoPort             : 5350
    ClientAppSharingPort        : 5350
    ClientFileTransferPort      : 5350

<span data-ttu-id="9f5a2-p106">Чтобы реализовать QoS, каждый из этих диапазонов портов должен быть уникальным. Например, вы можете настроить следующие диапазоны портов:</span><span class="sxs-lookup"><span data-stu-id="9f5a2-p106">In order to implement QoS, each of these port ranges will need to be unique. For example, you might configure the port ranges like this:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9f5a2-122">Тип клиентского трафика</span><span class="sxs-lookup"><span data-stu-id="9f5a2-122">Client Traffic Type</span></span></th>
<th><span data-ttu-id="9f5a2-123">Начальный порт</span><span class="sxs-lookup"><span data-stu-id="9f5a2-123">Port Start</span></span></th>
<th><span data-ttu-id="9f5a2-124">Диапазон портов</span><span class="sxs-lookup"><span data-stu-id="9f5a2-124">Port Range</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9f5a2-125">"Audio" (Аудио);</span><span class="sxs-lookup"><span data-stu-id="9f5a2-125">Audio</span></span></p></td>
<td><p><span data-ttu-id="9f5a2-126">50020</span><span class="sxs-lookup"><span data-stu-id="9f5a2-126">50020</span></span></p></td>
<td><p><span data-ttu-id="9f5a2-127">двадцать</span><span class="sxs-lookup"><span data-stu-id="9f5a2-127">20</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9f5a2-128">Видео</span><span class="sxs-lookup"><span data-stu-id="9f5a2-128">Video</span></span></p></td>
<td><p><span data-ttu-id="9f5a2-129">58000</span><span class="sxs-lookup"><span data-stu-id="9f5a2-129">58000</span></span></p></td>
<td><p><span data-ttu-id="9f5a2-130">двадцать</span><span class="sxs-lookup"><span data-stu-id="9f5a2-130">20</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9f5a2-131">Общий доступ к приложениям</span><span class="sxs-lookup"><span data-stu-id="9f5a2-131">Application sharing</span></span></p></td>
<td><p><span data-ttu-id="9f5a2-132">42000</span><span class="sxs-lookup"><span data-stu-id="9f5a2-132">42000</span></span></p></td>
<td><p><span data-ttu-id="9f5a2-133">двадцать</span><span class="sxs-lookup"><span data-stu-id="9f5a2-133">20</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9f5a2-134">Передача файлов</span><span class="sxs-lookup"><span data-stu-id="9f5a2-134">File transfer</span></span></p></td>
<td><p><span data-ttu-id="9f5a2-135">42020</span><span class="sxs-lookup"><span data-stu-id="9f5a2-135">42020</span></span></p></td>
<td><p><span data-ttu-id="9f5a2-136">двадцать</span><span class="sxs-lookup"><span data-stu-id="9f5a2-136">20</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="9f5a2-p107">В приведенной выше таблице диапазоны портов клиента представляют подмножество диапазонов портов, настроенных для ваших серверов. Например, на серверах для совместного использования приложений были настроены порты с 40803 по 49151. На клиентских компьютерах для совместного использования приложений были настроены порты с 42000 по 42019. Это, в основном, сделано для упрощения управления QoS: клиентские порты не должны представлять подмножество портов, используемых на сервере. (Например, на клиентских компьютерах можно настроить для совместного использования приложений, скажем, порты 10000-10019) Однако рекомендуется сделать диапазоны портов клиента подмножеством диапазонов портов сервера.</span><span class="sxs-lookup"><span data-stu-id="9f5a2-p107">In the preceding table, client port ranges represent a subset of the port ranges configured for your servers. For example, on the servers, application sharing was configured to use ports 40803 through 49151; on the client computers, application sharing is configured to use ports 42000 through 42019. This, too is done primarily to make administration of QoS easier: client ports do not have to represent a subset of the ports used on the server. (For example, on the client computers you could configure application sharing to use, say, ports 10000 through 10019.) However, it is recommended that you make your client port ranges a subset of your server port ranges.</span></span>

<span data-ttu-id="9f5a2-p108">Кроме того, вы могли заметить, что 8348 портов было выделено для совместного использования приложений на серверах, но всего 20 портов было выделено для совместного использования приложений на клиентах. Это также рекомендуется, но не является строго обязательным. В общем, можно рассмотреть каждый доступный порт для представления отдельного сеанса связи: если у вас 100 портов в диапазоне, что означает, что компьютер может участвовать максимум в 100 сеансах связи в любой момент времени. Поскольку серверы, вероятно, будут участвовать в большем числе сеансов, чем клиенты, имеет смысл открыть намного больше портов на серверах, чем на клиентах. Выделение 20 портов для совместного использования приложений на клиентах означает, что пользователь одновременно может участвовать в 20 сеансах совместного применения приложений на указанном устройстве. Если должно быть достаточно для подавляющего большинства пользователей.</span><span class="sxs-lookup"><span data-stu-id="9f5a2-p108">In addition, you might have noticed that 8348 ports were set aside for application sharing on the servers, but only 20 ports were set aside for application sharing on the clients. This, too is recommended, but is not a hard-and-fast rule. In general, you can consider each available port to represent a single communication session: if you have 100 ports available in a port range that means that the computer in question could participate in, at most, 100 communication sessions at any given time. Because servers will likely take part in many more conversations than clients, it makes sense to open many more ports on servers than on clients. Setting aside 20 ports for application sharing on a client means that a user could participate in 20 application sharing sessions on the specified device, and all at the same time. That should prove sufficient for the vast majority of your users.</span></span>

<span data-ttu-id="9f5a2-147">Чтобы назначить предыдущие диапазоны портов глобальной коллекции параметров конфигурации конференц-связи, можно использовать следующую команду в командной консоли Lync Server:</span><span class="sxs-lookup"><span data-stu-id="9f5a2-147">To assign the preceding port ranges to your global collection of conferencing configuration settings you can use the following Lync Server Management Shell command:</span></span>

    Set-CsConferencingConfiguration -Identity global -ClientAudioPort 50020 -ClientAudioPortRange 20 -ClientVideoPort 58000 -ClientVideoPortRange 20 -ClientAppSharingPort 42000 -ClientAppSharingPortRange 20 - ClientFileTransferPort 42020 -ClientFileTransferPortRange 20

<span data-ttu-id="9f5a2-148">Или с помощью этой команды можно назначить эти же диапазоны портов всем параметрам конфигурации конференций:</span><span class="sxs-lookup"><span data-stu-id="9f5a2-148">Or, use this command to assign these same port ranges for all your conferencing configuration settings:</span></span>

    Get-CsConferencingConfiguration | Set-CsConferencingConfiguration -ClientAudioPort 50020 -ClientAudioPortRange 20 -ClientVideoPort 58000 -ClientVideoPortRange 20 -ClientAppSharingPort 42000 -ClientAppSharingPortRange 20 - ClientFileTransferPort 42020 -ClientFileTransferPortRange 20

<span data-ttu-id="9f5a2-149">Отдельные пользователи должны выйти из Lync, а затем снова войти в систему, чтобы изменения вступили в силу.</span><span class="sxs-lookup"><span data-stu-id="9f5a2-149">Individual users must log off from Lync and then log back on before these changes will actually take effect.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="9f5a2-150">Вы также можете включить диапазоны портов мультимедиа клиентов, а затем назначить эти диапазоны портов с помощью одной команды.</span><span class="sxs-lookup"><span data-stu-id="9f5a2-150">You can also enable client media port ranges, and then assign those port ranges, using a single command.</span></span> <span data-ttu-id="9f5a2-151">Пример:</span><span class="sxs-lookup"><span data-stu-id="9f5a2-151">For example:</span></span><BR><CODE>Set-CsConferencingConfiguration -ClientMediaPortRangeEnabled $True -ClientAudioPort 50020 -ClientAudioPortRange 20 -ClientVideoPort 58000 -ClientVideoPortRange 20 -ClientAppSharingPort 42000 -ClientAppSharingPortRange 20 -ClientFileTransferPort 42020 -ClientFileTransferPortRange 20</CODE>



</div>

</div>

<span> </span>

</div>

</div>

</div>

