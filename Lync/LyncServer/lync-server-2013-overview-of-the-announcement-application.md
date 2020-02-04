---
title: 'Lync Server 2013: Общие сведения о приложении объявления'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of the Announcement application
ms:assetid: 2abee804-2599-48bb-90b2-15df0bae5e20
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204757(v=OCS.15)
ms:contentKeyID: 48183689
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a4c1b9210fcb0734b305a30d27c77b4e81257909
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755463"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-the-announcement-application-in-lync-server-2013"></a><span data-ttu-id="5f3bd-102">Общие сведения о приложении объявления в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5f3bd-102">Overview of the Announcement application in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5f3bd-103">_**Тема последнего изменения:** 2012-09-13_</span><span class="sxs-lookup"><span data-stu-id="5f3bd-103">_**Topic Last Modified:** 2012-09-13_</span></span>

<span data-ttu-id="5f3bd-104">При развертывании приложения объявления необходимо настроить таблицу неназначенных номеров, которая определяет действие, которое будет выполняться при наборе номера абонентом без назначения.</span><span class="sxs-lookup"><span data-stu-id="5f3bd-104">When you deploy the Announcement application, you need to configure an unassigned number table that determines the action to be taken when someone dials an unassigned number.</span></span> <span data-ttu-id="5f3bd-105">Таблица неназначенные номера содержит диапазоны номеров телефонов, действительные для Организации, и определяет, какое приложение будет обрабатывать каждый диапазон.</span><span class="sxs-lookup"><span data-stu-id="5f3bd-105">The unassigned number table contains ranges of phone numbers that are valid for the organization and specifies which Announcement application handles each range.</span></span> <span data-ttu-id="5f3bd-106">Когда вызывающий абонент набирает номер телефона, который является действительным для вашей организации, но не назначается никому, Lync Server ищет номер в таблице неназначенные номера, определяет, какой диапазон будет находиться в списке, и направляет Звонок на объявление. приложение, указанное для этого диапазона.</span><span class="sxs-lookup"><span data-stu-id="5f3bd-106">When a caller dials a telephone number that is valid for your organization but is not assigned to anyone, Lync Server looks up the number in the unassigned number routing table, identifies which range the number falls in, and routes the call to the Announcement application specified for that range.</span></span> <span data-ttu-id="5f3bd-107">Приложение извещения отвечает на вызов и воспроизводит звуковое сообщение (если вы настроили его), а затем либо отключает звонок, либо передает его в предварительно определенный конечный объект, например оператор.</span><span class="sxs-lookup"><span data-stu-id="5f3bd-107">The Announcement application answers the call and plays an audio message (if you configured it to do so) and then either disconnects the call or transfers it to a predetermined destination, such as to an operator.</span></span> <span data-ttu-id="5f3bd-108">Вы можете использовать командлеты командной консоли Lync Server для настройки нескольких звуковых сообщений или перемещения адресатов.</span><span class="sxs-lookup"><span data-stu-id="5f3bd-108">You can use Lync Server Management Shell cmdlets to configure multiple audio messages or to transfer destinations.</span></span>

<span data-ttu-id="5f3bd-p102">Способ настройки таблица неназначенных номеров зависит от ее последующего использования. Если у вас имеются определенные номера, которые больше не используются, и вы хотите воспроизводить для каждого номера индивидуальные сообщения, то можете ввести эти номера в таблицу неназначенных номеров. Например, если вы изменили номер отдела обслуживания клиентов, вы можете ввести старый номер обслуживания клиентов и сопоставить его с оповещением, в котором указывается новый номер. Если вы хотите воспроизвести сообщение общего характера любому человеку, позвонившему по неназначенному номеру, например номеру уволившегося сотрудника, то можете ввести диапазоны для всех допустимых добавочных номеров в организации. Таблица неназначенных номеров вызывается при наборе звонящим номера, который в данный момент не назначен.</span><span class="sxs-lookup"><span data-stu-id="5f3bd-p102">How you configure the unassigned number table depends on how you want to use it. If you have specific numbers that are no longer in use and you want to play messages that are tailored for each number, you can enter those specific numbers in the unassigned number table. For example, if you changed the number for your customer service desk, you can enter the old customer service number and associate it with an announcement that gives the new number. If you want to play a general message to anyone who calls a number that is not assigned, such as for employees who have left your organization, you can enter ranges for all the valid extensions in your organization. The unassigned number table is invoked whenever the caller dials a number that is not currently assigned.</span></span>

<span data-ttu-id="5f3bd-114">В Lync Server 2013 приложение извещения автоматически устанавливается вместе с приложением группы ответа.</span><span class="sxs-lookup"><span data-stu-id="5f3bd-114">In Lync Server 2013, the Announcement application is automatically installed with the Response Group application.</span></span> <span data-ttu-id="5f3bd-115">Приложения группы "объявление" и "ответ" — это стандартные компоненты корпоративного развертывания для предприятий: при развертывании Enterprise Voice оба эти приложения автоматически развертываются.</span><span class="sxs-lookup"><span data-stu-id="5f3bd-115">The Announcement and Response Group applications are standard components of an Enterprise Voice deployment: When you deploy Enterprise Voice, both of these applications are automatically deployed.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

