---
title: 'Lync Server 2013: Настройка таблицы неназначенных номеров'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure the unassigned number table
ms:assetid: eaa01986-e92f-4328-acf6-4e46c4306a04
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399053(v=OCS.15)
ms:contentKeyID: 48185908
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4c73027511ec8798010f1d22fb9bd19eeab27a7f
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48520256"
---
# <a name="configure-the-unassigned-number-table-in-lync-server-2013"></a><span data-ttu-id="11cc4-102">Настройка таблицы неназначенных номеров в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="11cc4-102">Configure the unassigned number table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="11cc4-103">_**Последнее изменение темы:** 2012-10-30_</span><span class="sxs-lookup"><span data-stu-id="11cc4-103">_**Topic Last Modified:** 2012-10-30_</span></span>

<span data-ttu-id="11cc4-104">В Lync Server 2013 вы можете указать, что происходит с входящими вызовами на номера телефонов, действительные для вашей организации, но не назначенные пользователю или телефону.</span><span class="sxs-lookup"><span data-stu-id="11cc4-104">In Lync Server 2013, you can specify what happens to incoming calls to phone numbers that are valid for your organization, but are not assigned to a user or phone.</span></span> <span data-ttu-id="11cc4-105">Можно задать воспроизведение сообщения для вызывающего абонента, или перенаправление в другое место назначения, или и то, и другое.</span><span class="sxs-lookup"><span data-stu-id="11cc4-105">Callers can hear a message, or can be routed to another destination, or both.</span></span>

<span data-ttu-id="11cc4-p102">Настройка таблицы неназначенных номеров зависит от того, как ее планируется использовать. Можно включить в эту таблицу все действительные добавочные номера для организации, только неназначенные добавочные номера или оба типа номеров. Таблица неназначенных номеров может включать как назначенные, так и неназначенные номера, но вызывается только в том случае, если вызывающий абонент набирает номер, который в текущий момент не назначен. Если в таблицу неназначенных номеров включить все действительные добавочные номера, то можно указать действие, которое должно выполняться, когда кто-либо увольняется из организации, и тогда не придется заново настраивать таблицу. Если в таблицу включить неназначенные добавочные номера, то можно настраивать действие, выполняющееся для определенных номеров. Например, если добавочный номер службы поддержки клиентов изменился, то старый номер можно включить в эту таблицу и назначить его объявлению, которое сообщает новый номер.</span><span class="sxs-lookup"><span data-stu-id="11cc4-p102">How you configure the unassigned number table depends on how you want to use it. You can configure the table with all the valid extensions for your organization, with only unassigned extensions, or with a combination of both types of numbers. The unassigned number table can include both assigned and unassigned numbers, but it is invoked only when a caller dials a number that is not currently assigned. If you include all the valid extensions in the unassigned number table, you can specify the action that occurs whenever someone leaves your organization, without needing to reconfigure the table. If you include unassigned extensions in the table, you can modify the action that occurs for specific numbers. For example, if you change the extension for your customer service desk, you can include the old customer service number in the table and then assign it to an announcement that provides the new number.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="11cc4-112">Перед настройкой таблицы неназначенных номеров в системе должны уже быть определены объявления или настроен автосекретарь единой системы обмена сообщениями Exchange.</span><span class="sxs-lookup"><span data-stu-id="11cc4-112">Before you configure the unassigned number table, your system must already either have Announcements defined or an Exchange Unified Messaging (UM) Auto Attendant set up.</span></span>



</div>

<div>


> [!TIP]  
> <span data-ttu-id="11cc4-113">Когда кто-то звонит по неназначенному номеру, Lync Server выполняет поиск в таблице неназначенных номеров сверху вниз и использует первый совпадающий диапазон.</span><span class="sxs-lookup"><span data-stu-id="11cc4-113">When someone calls an unassigned number, Lync Server searches the unassigned number table from top to bottom and uses the first matching range.</span></span> <span data-ttu-id="11cc4-114">Таким образом, действие, которое должно выполняться последним, должно быть задано для последнего диапазона в таблице.</span><span class="sxs-lookup"><span data-stu-id="11cc4-114">Therefore, an action that you want to be performed as a last resort should be specified for the last range in the table.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="11cc4-115">Содержание</span><span class="sxs-lookup"><span data-stu-id="11cc4-115">In This Section</span></span>

<span data-ttu-id="11cc4-116">[Создание или изменение диапазона неназначенных номеров в Lync server 2013](lync-server-2013-create-or-modify-an-unassigned-number-range.md) [Создание извещения в Lync Server 2013](lync-server-2013-create-an-announcement.md)</span><span class="sxs-lookup"><span data-stu-id="11cc4-116">[Create or modify an unassigned number range in Lync Server 2013](lync-server-2013-create-or-modify-an-unassigned-number-range.md) [Create an announcement in Lync Server 2013](lync-server-2013-create-an-announcement.md)</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

