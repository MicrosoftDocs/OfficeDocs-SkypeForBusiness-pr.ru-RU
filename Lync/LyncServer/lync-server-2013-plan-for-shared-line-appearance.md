---
title: 'Lync Server 2013: планирование отображения общей линии'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Plan for Shared Line Appearance
ms:assetid: a35c83d8-f531-445b-a8d2-d5d8cec77c6b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Mt712151(v=OCS.15)
ms:contentKeyID: 72522136
ms.date: 03/21/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 938bc723d9803acc955899a2b625f983d860b421
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34825137"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="plan-for-shared-line-appearance-in-lync-server-2013"></a><span data-ttu-id="3bf8f-102">Планирование отображения общего вида линии в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3bf8f-102">Plan for Shared Line Appearance in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3bf8f-103">_**Тема последнего изменения:** 2016-03-21_</span><span class="sxs-lookup"><span data-stu-id="3bf8f-103">_**Topic Last Modified:** 2016-03-21_</span></span>

<span data-ttu-id="3bf8f-104">В этой статье рассказывается, как запланировать общий вид линии (SLA) в Lync Server 2013, Накопительное обновление от апреля 2016 г.</span><span class="sxs-lookup"><span data-stu-id="3bf8f-104">Read this topic to learn how to plan for Shared Line Appearance (SLA) in Lync Server 2013, Cumulative Update April 2016.</span></span>

<span data-ttu-id="3bf8f-105">Общий внешний вид линии — это функция, которая входит в состав Lync Server 2013, накопительного обновления за Апрель 2016 для обработки нескольких звонков по определенному номеру, именуемому общим номером.</span><span class="sxs-lookup"><span data-stu-id="3bf8f-105">Shared Line Appearance is a feature in Lync Server 2013, Cumulative Update April 2016 for handling multiple calls on a specific number called a shared number.</span></span> <span data-ttu-id="3bf8f-106">SLA может настроить любой пользователь Lync Enterprise голосовой связи в качестве общего номера с несколькими строками для ответа на несколько звонков.</span><span class="sxs-lookup"><span data-stu-id="3bf8f-106">SLA can configure any enterprise voice enabled Lync user as a shared number with multiple lines to respond to multiple calls.</span></span> <span data-ttu-id="3bf8f-107">Фактически вызовы не принимаются общим номером, а направляются пользователям, выступающим в роли делегатов общего номера.</span><span class="sxs-lookup"><span data-stu-id="3bf8f-107">The calls are not actually received on the shared number, instead they are forwarded to users that act as delegates for the shared number.</span></span> <span data-ttu-id="3bf8f-108">Любой из делегатов может принять вызов, после чего остальные делегаты получать уведомление на телефон о том, кто принял вызов и какая линия теперь занята.</span><span class="sxs-lookup"><span data-stu-id="3bf8f-108">Any one of the delegates can pick up the call while the rest of the delegates get a notification on their phone about who picked up the call and which line has become busy as a result.</span></span> <span data-ttu-id="3bf8f-109">Количество линий и делегатов можно настроить для общего номера в SLA.</span><span class="sxs-lookup"><span data-stu-id="3bf8f-109">Both the number of lines and the delegates are configurable for a shared number in SLA.</span></span> <span data-ttu-id="3bf8f-110">Кроме того, для общего номера можно настроить такие расширенные параметры, как опции "Занято" (используется в ситуации, когда все линии заняты) и "Пропущенный вызов" (используется, когда ни один из делегатов не ответил на звонок).</span><span class="sxs-lookup"><span data-stu-id="3bf8f-110">In addition, advanced options, such as BusyOption (what happens in a situation when all lines are busy) and MissedCallOption (the case in which none of the delegates pick up a call), can also be configured for a shared number.</span></span>

<span data-ttu-id="3bf8f-111">SLA поддерживается только на указанных ниже телефонных устройствах (оно не поддерживается для клиентов Lync на компьютерах, мобильных телефонах и других устройствах).</span><span class="sxs-lookup"><span data-stu-id="3bf8f-111">SLA is supported only on the following phone devices (it is not supported for Lync clients on computers, mobile phones, or other devices):</span></span>

  - <span data-ttu-id="3bf8f-112">Polycom VVX300 с обновлением встроенного ПО 5.4.1</span><span class="sxs-lookup"><span data-stu-id="3bf8f-112">Polycom VVX300 with firmware update 5.4.1</span></span>

  - <span data-ttu-id="3bf8f-113">Polycom VVX400 с обновлением встроенного ПО 5.4.1</span><span class="sxs-lookup"><span data-stu-id="3bf8f-113">Polycom VVX400 with firmware update 5.4.1</span></span>

  - <span data-ttu-id="3bf8f-114">Polycom VVX500 с обновлением встроенного ПО 5.4.1</span><span class="sxs-lookup"><span data-stu-id="3bf8f-114">Polycom VVX500 with firmware update 5.4.1</span></span>

  - <span data-ttu-id="3bf8f-115">Polycom VVX600 с обновлением встроенного ПО 5.4.1</span><span class="sxs-lookup"><span data-stu-id="3bf8f-115">Polycom VVX600 with firmware update 5.4.1</span></span>

<span data-ttu-id="3bf8f-116">SLA — это новая функция в Lync Server 2013, Накопительное обновление от 12 апреля 2016 г.</span><span class="sxs-lookup"><span data-stu-id="3bf8f-116">SLA is a new feature in Lync Server 2013, Cumulative Update April 2016.</span></span>

<span data-ttu-id="3bf8f-117">Сведения о развертывании SLA можно найти [в статьях развертывание общей линии в Lync Server 2013](lync-server-2013-deploy-shared-line-appearance.md).</span><span class="sxs-lookup"><span data-stu-id="3bf8f-117">For information about deploying SLA, see [Deploy Shared Line Appearance in Lync Server 2013](lync-server-2013-deploy-shared-line-appearance.md).</span></span>

<div>

## <a name="feature-list"></a><span data-ttu-id="3bf8f-118">Список функций</span><span class="sxs-lookup"><span data-stu-id="3bf8f-118">Feature List</span></span>

<span data-ttu-id="3bf8f-119">Настройка группы SLA предоставляет следующие возможности.</span><span class="sxs-lookup"><span data-stu-id="3bf8f-119">Setting up an SLA group enables the following:</span></span>

  - <span data-ttu-id="3bf8f-p102">Все делегаты в группы могут отвечать на входящие вызовы, поступающие на один общий номер. Эти вызовы могут быть как на базе ТСОП, так и на базе SIP.</span><span class="sxs-lookup"><span data-stu-id="3bf8f-p102">All delegates in the group can answer inbound calls to the same shared number. The calls can be PSTN-based or SIP-based.</span></span>

  - <span data-ttu-id="3bf8f-122">Делегаты могут переводить вызовы в режим удержания и затем принимать их.</span><span class="sxs-lookup"><span data-stu-id="3bf8f-122">Delegates can hold and pick up calls.</span></span>

  - <span data-ttu-id="3bf8f-123">Делегаты могут передавать вызовы за пределы группы SLA.</span><span class="sxs-lookup"><span data-stu-id="3bf8f-123">Delegates can transfer calls to a number outside of the SLA group.</span></span>

  - <span data-ttu-id="3bf8f-124">Делегаты могут посмотреть количество вызовов, одновременно поступающих на общий номер, а также состояние каждого из этих вызовов.</span><span class="sxs-lookup"><span data-stu-id="3bf8f-124">Delegates can see how many calls are currently on the shared number, and view the status of each of those calls.</span></span>

  - <span data-ttu-id="3bf8f-p103">Можно настроить максимальное количество одновременных вызов для общего номера. Кроме того, можно определить способ обработки дополнительных вызовов после достижения максимального значения. Лишние вызовы могут быть отклонены сигналом "занято", перенаправлены на другой номер или в голосовую почту.</span><span class="sxs-lookup"><span data-stu-id="3bf8f-p103">You can configure a maximum number of concurrent calls for the shared number. You can also set how you want additional calls to be handled after this maximum is reached. Excess calls can be rejected with a busy signal, forwarded to an alternate number, or forwarded to voice mail.</span></span>

  - <span data-ttu-id="3bf8f-p104">Можно настроить способ обработки пропущенных вызовов (вызовы, на которые не ответили в течение определенного времени). Если включить голосовую почту для идентификатора группы, пропущенные звонки автоматически отправляются на голосовую почту. Если голосовая почта не включена для идентификатора группы (общий номер), пропущенный вызов можно отклонить сигналом "занято", переадресовать на другой номер или отсоединить.</span><span class="sxs-lookup"><span data-stu-id="3bf8f-p104">You can configure how you want missed calls (calls not picked up after a certain time) to be handled. If you enable voice mail for the group identity, missed calls automatically go to voice mail. If you do not have voice mail enabled for the group identity (shared number), you can choose for missed calls to be rejected with a busy signal, forwarded to an alternate number, or disconnected.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

