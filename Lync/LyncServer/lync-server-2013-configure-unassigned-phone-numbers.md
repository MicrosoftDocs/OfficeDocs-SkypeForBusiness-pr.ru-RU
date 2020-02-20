---
title: 'Lync Server 2013: Настройка неназначенных телефонных номеров'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure unassigned phone numbers
ms:assetid: a0650659-dce7-455f-8977-02454bbfa400
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182559(v=OCS.15)
ms:contentKeyID: 48185009
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 920dc38010aa82f7c3f970a76f78c23bbf2a486a
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42145628"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-unassigned-phone-numbers-in-lync-server-2013"></a><span data-ttu-id="8414b-102">Настройка неназначенных телефонных номеров в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8414b-102">Configure unassigned phone numbers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8414b-103">_**Последнее изменение темы:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="8414b-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="8414b-104">Lync Server позволяет настраивать действия, выполняемые для входящих вызовов на номера телефонов, действительные для вашей организации, но не назначенные пользователю или телефону.</span><span class="sxs-lookup"><span data-stu-id="8414b-104">Lync Server lets you configure what happens to incoming calls to phone numbers that are valid for your organization, but are not assigned to a user or a phone.</span></span> <span data-ttu-id="8414b-105">Чтобы настроить обработку таких вызовов, следует задать таблицу неназначенных номеров.</span><span class="sxs-lookup"><span data-stu-id="8414b-105">To configure the handling of such calls, you set up an unassigned number table.</span></span> <span data-ttu-id="8414b-106">Вы можете использовать таблицу для маршрутизации вызовов в приложение извещения или на сервер единой системы обмена сообщениями Exchange.</span><span class="sxs-lookup"><span data-stu-id="8414b-106">You can use the table to route the calls to an Announcement application or to an Exchange UM server.</span></span>

<span data-ttu-id="8414b-p102">Способ настройки таблицы неназначенных номеров зависит от того, как вы хотите ее использовать. Вы можете настроить таблицу с учетом всех допустимых добавочных номеров для своей организации, только неназначенных добавочных номеров или сочетания обоих типов номеров. Таблица неназначенных номеров может включать в себя как назначенные, так и неназначенные номера, но она вызывается только в том случае, когда звонящий набирает номер, который в данный момент не назначен. Если вы включаете в таблицу неназначенных номеров все допустимые добавочные номера, то можете указать действие, которое выполняется при увольнении человека из организации, благодаря чему вам не требуется изменять настройку данной таблицы. Если вы включаете в таблицу неназначенные добавочные номера, то можете настроить действие, выполняемое для отдельных номеров. Например, если вы изменяете добавочный номер для своего отдела обслуживания клиентов, то можете включить таблицу старый номер этого отдела и назначить ему извещение, содержащее новый номер.</span><span class="sxs-lookup"><span data-stu-id="8414b-p102">How you configure the unassigned number table depends on how you want to use it. You can configure the table with all the valid extensions for your organization, with only unassigned extensions, or with a combination of both types of numbers. The unassigned number table can include both assigned and unassigned numbers, but it is invoked only when a caller dials a number that is not currently assigned. If you include all the valid extensions in the unassigned number table, you can specify the action that occurs whenever someone leaves your organization, without needing to reconfigure the table. If you include unassigned extensions in the table, you can tailor the action that occurs for specific numbers. For example, if you change the extension for your customer service desk, you can include the old customer service number in the table and assign it to an announcement that provides the new number.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="8414b-113">Перед настройкой таблицы неназначенных номеров необходимо, чтобы уже было определено одно или несколько объявлений или настроен автосекретарь единой системы обмена сообщениями Exchange.</span><span class="sxs-lookup"><span data-stu-id="8414b-113">Before you configure the unassigned number table, you must already have either one or more announcements defined or an Exchange UM Auto Attendant set up.</span></span> <span data-ttu-id="8414b-114">Более подробную информацию о создании <A href="lync-server-2013-create-an-announcement.md">оповещений можно узнать в статье Create a извещения в Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="8414b-114">For details about creating announcements, see <A href="lync-server-2013-create-an-announcement.md">Create an announcement in Lync Server 2013</A>.</span></span> <span data-ttu-id="8414b-115">Чтобы проверить, настроены ли параметры единой системы обмена сообщениями Exchange, выполните командлет <STRONG>Get – CsExUmContact</STRONG> .</span><span class="sxs-lookup"><span data-stu-id="8414b-115">To see if you have configured Exchange UM settings, run the <STRONG>Get-CsExUmContact</STRONG> cmdlet.</span></span> <span data-ttu-id="8414b-116">Дополнительные сведения см. в разделе <A href="https://docs.microsoft.com/powershell/module/skype/Get-CsExUmContact">Get-CsExUmContact</A>.</span><span class="sxs-lookup"><span data-stu-id="8414b-116">For details, see <A href="https://docs.microsoft.com/powershell/module/skype/Get-CsExUmContact">Get-CsExUmContact</A>.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="8414b-117">Содержание</span><span class="sxs-lookup"><span data-stu-id="8414b-117">In This Section</span></span>

  - [<span data-ttu-id="8414b-118">Создание или изменение диапазона неназначенных номеров в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8414b-118">Create or modify an unassigned number range in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-an-unassigned-number-range.md)

  - [<span data-ttu-id="8414b-119">Удаление диапазона неназначенных номеров в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8414b-119">Delete an unassigned number range in Lync Server 2013</span></span>](lync-server-2013-delete-an-unassigned-number-range.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

