---
title: 'Lync Server 2013: обзор приложения "объявление"'
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
ms.openlocfilehash: d0bceaef7a165f4594d825a80b93ee167b68c85a
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48520816"
---
# <a name="overview-of-the-announcement-application-in-lync-server-2013"></a><span data-ttu-id="f3866-102">Обзор приложения "объявление" в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f3866-102">Overview of the Announcement application in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f3866-103">_**Последнее изменение темы:** 2012-09-13_</span><span class="sxs-lookup"><span data-stu-id="f3866-103">_**Topic Last Modified:** 2012-09-13_</span></span>

<span data-ttu-id="f3866-104">При развертывании приложения извещения необходимо настроить таблицу неназначенных номеров, определяющую действие, выполняемое при набираемом неназначенном номере.</span><span class="sxs-lookup"><span data-stu-id="f3866-104">When you deploy the Announcement application, you need to configure an unassigned number table that determines the action to be taken when someone dials an unassigned number.</span></span> <span data-ttu-id="f3866-105">Таблица неназначенных номеров содержит диапазоны телефонных номеров, допустимых для Организации, и указывает, какое приложение оповещений обрабатывает каждый диапазон.</span><span class="sxs-lookup"><span data-stu-id="f3866-105">The unassigned number table contains ranges of phone numbers that are valid for the organization and specifies which Announcement application handles each range.</span></span> <span data-ttu-id="f3866-106">Когда вызывающий абонент набирает номер телефона, действительный для вашей организации, но не назначенный никому, Lync Server ищет номер в таблице маршрутизации неназначенных номеров, определяет диапазон, на который приходится число, и направляет вызов приложению, указанному для этого диапазона.</span><span class="sxs-lookup"><span data-stu-id="f3866-106">When a caller dials a telephone number that is valid for your organization but is not assigned to anyone, Lync Server looks up the number in the unassigned number routing table, identifies which range the number falls in, and routes the call to the Announcement application specified for that range.</span></span> <span data-ttu-id="f3866-107">Приложение извещения отвечает на вызов и воспроизводит звуковое сообщение (если оно настроено таким образом), а затем либо отсоединяет вызов, либо передает его предварительно определенному назначению, например оператору.</span><span class="sxs-lookup"><span data-stu-id="f3866-107">The Announcement application answers the call and plays an audio message (if you configured it to do so) and then either disconnects the call or transfers it to a predetermined destination, such as to an operator.</span></span> <span data-ttu-id="f3866-108">Командлеты командной консоли Lync Server можно использовать для настройки нескольких звуковых сообщений или для передачи назначений.</span><span class="sxs-lookup"><span data-stu-id="f3866-108">You can use Lync Server Management Shell cmdlets to configure multiple audio messages or to transfer destinations.</span></span>

<span data-ttu-id="f3866-p102">Способ настройки таблица неназначенных номеров зависит от ее последующего использования. Если у вас имеются определенные номера, которые больше не используются, и вы хотите воспроизводить для каждого номера индивидуальные сообщения, то можете ввести эти номера в таблицу неназначенных номеров. Например, если вы изменили номер отдела обслуживания клиентов, вы можете ввести старый номер обслуживания клиентов и сопоставить его с оповещением, в котором указывается новый номер. Если вы хотите воспроизвести сообщение общего характера любому человеку, позвонившему по неназначенному номеру, например номеру уволившегося сотрудника, то можете ввести диапазоны для всех допустимых добавочных номеров в организации. Таблица неназначенных номеров вызывается при наборе звонящим номера, который в данный момент не назначен.</span><span class="sxs-lookup"><span data-stu-id="f3866-p102">How you configure the unassigned number table depends on how you want to use it. If you have specific numbers that are no longer in use and you want to play messages that are tailored for each number, you can enter those specific numbers in the unassigned number table. For example, if you changed the number for your customer service desk, you can enter the old customer service number and associate it with an announcement that gives the new number. If you want to play a general message to anyone who calls a number that is not assigned, such as for employees who have left your organization, you can enter ranges for all the valid extensions in your organization. The unassigned number table is invoked whenever the caller dials a number that is not currently assigned.</span></span>

<span data-ttu-id="f3866-114">В Lync Server 2013 приложение извещения автоматически устанавливается вместе с приложением группы ответа.</span><span class="sxs-lookup"><span data-stu-id="f3866-114">In Lync Server 2013, the Announcement application is automatically installed with the Response Group application.</span></span> <span data-ttu-id="f3866-115">Приложения группы оповещений и ответов являются стандартными компонентами развертывания корпоративной голосовой связи: при развертывании корпоративной голосовой связи оба этих приложения автоматически развертываются.</span><span class="sxs-lookup"><span data-stu-id="f3866-115">The Announcement and Response Group applications are standard components of an Enterprise Voice deployment: When you deploy Enterprise Voice, both of these applications are automatically deployed.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

