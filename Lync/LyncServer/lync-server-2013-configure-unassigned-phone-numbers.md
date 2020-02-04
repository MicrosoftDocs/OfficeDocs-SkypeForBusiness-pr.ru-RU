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
ms.openlocfilehash: 02dd4f71b3bc9d53fcbd65f4e143fec550c6a528
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41736469"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-unassigned-phone-numbers-in-lync-server-2013"></a><span data-ttu-id="4e9c5-102">Настройка неназначенных номеров телефонов в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4e9c5-102">Configure unassigned phone numbers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4e9c5-103">_**Тема последнего изменения:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="4e9c5-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="4e9c5-104">Lync Server позволяет настроить действия, которые будут происходить на входящие звонки на номера телефонов, которые действительны для вашей организации, но не назначены пользователю или телефону.</span><span class="sxs-lookup"><span data-stu-id="4e9c5-104">Lync Server lets you configure what happens to incoming calls to phone numbers that are valid for your organization, but are not assigned to a user or a phone.</span></span> <span data-ttu-id="4e9c5-105">Для настройки обработки таких звонков вы настроили таблицу неназначенных номеров.</span><span class="sxs-lookup"><span data-stu-id="4e9c5-105">To configure the handling of such calls, you set up an unassigned number table.</span></span> <span data-ttu-id="4e9c5-106">Вы можете использовать таблицу для маршрутизации вызовов в приложение объявлений или на сервер Exchange UM.</span><span class="sxs-lookup"><span data-stu-id="4e9c5-106">You can use the table to route the calls to an Announcement application or to an Exchange UM server.</span></span>

<span data-ttu-id="4e9c5-p102">Настройка таблицы неназначенных номеров зависит от способа ее использования. В эту таблицу можно добавить все добавочные номера, используемые в организации, добавить только неназначенные добавочные номера или добавить номера обоих типов. Таблица неназначенных номеров может содержать назначенные и неназначенные номера, но вызывается только в том случае, если звонящий набирает номер, который в настоящее время не назначен. Если вы добавили в таблицу неназначенных номеров все допустимые добавочные номера, то вы можете указать действие, выполняемое при выходе сотрудника в отпуск без необходимости дополнительной настройки таблицы. Если вы добавили в таблицу неназначенные добавочные номера, то вы можете указать действие, выполняемое для определенных номеров. Например, при изменении добавочного номера службы поддержки клиентов вы можете добавить в таблицу старый номер службы поддержки и назначить ему оповещение, которое сообщает новый номер.</span><span class="sxs-lookup"><span data-stu-id="4e9c5-p102">How you configure the unassigned number table depends on how you want to use it. You can configure the table with all the valid extensions for your organization, with only unassigned extensions, or with a combination of both types of numbers. The unassigned number table can include both assigned and unassigned numbers, but it is invoked only when a caller dials a number that is not currently assigned. If you include all the valid extensions in the unassigned number table, you can specify the action that occurs whenever someone leaves your organization, without needing to reconfigure the table. If you include unassigned extensions in the table, you can tailor the action that occurs for specific numbers. For example, if you change the extension for your customer service desk, you can include the old customer service number in the table and assign it to an announcement that provides the new number.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="4e9c5-113">Перед настройкой таблицы неназначенные номера необходимо, чтобы в ней уже было определено одно или несколько объявлений либо настроен автоматический секретарь UM Exchange.</span><span class="sxs-lookup"><span data-stu-id="4e9c5-113">Before you configure the unassigned number table, you must already have either one or more announcements defined or an Exchange UM Auto Attendant set up.</span></span> <span data-ttu-id="4e9c5-114">Подробнее о создании извещений можно узнать <A href="lync-server-2013-create-an-announcement.md">в статьях создание объявления в Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="4e9c5-114">For details about creating announcements, see <A href="lync-server-2013-create-an-announcement.md">Create an announcement in Lync Server 2013</A>.</span></span> <span data-ttu-id="4e9c5-115">Чтобы узнать, настроены ли параметры Exchange UM, запустите командлет <STRONG>Get-ксексумконтакт</STRONG> .</span><span class="sxs-lookup"><span data-stu-id="4e9c5-115">To see if you have configured Exchange UM settings, run the <STRONG>Get-CsExUmContact</STRONG> cmdlet.</span></span> <span data-ttu-id="4e9c5-116">Подробности можно найти в <A href="https://docs.microsoft.com/powershell/module/skype/Get-CsExUmContact">статьях Get-ксексумконтакт</A>.</span><span class="sxs-lookup"><span data-stu-id="4e9c5-116">For details, see <A href="https://docs.microsoft.com/powershell/module/skype/Get-CsExUmContact">Get-CsExUmContact</A>.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="4e9c5-117">Содержание</span><span class="sxs-lookup"><span data-stu-id="4e9c5-117">In This Section</span></span>

  - [<span data-ttu-id="4e9c5-118">Создание и изменение неназначенного диапазона номеров в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4e9c5-118">Create or modify an unassigned number range in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-an-unassigned-number-range.md)

  - [<span data-ttu-id="4e9c5-119">Удаление неназначенного диапазона номеров в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4e9c5-119">Delete an unassigned number range in Lync Server 2013</span></span>](lync-server-2013-delete-an-unassigned-number-range.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

