---
title: 'Lync Server 2013: планирование отображения общей линии'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Plan for Shared Line Appearance
ms:assetid: a35c83d8-f531-445b-a8d2-d5d8cec77c6b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Mt712151(v=OCS.15)
ms:contentKeyID: 72522136
ms.date: 03/21/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fdb4f8ad407950f8d3180d030ede03a1e93cf0b3
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42050601"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="plan-for-shared-line-appearance-in-lync-server-2013"></a><span data-ttu-id="1d4af-102">Планирование общего внешнего вида линии в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1d4af-102">Plan for Shared Line Appearance in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1d4af-103">_**Последнее изменение темы:** 2016-03-21_</span><span class="sxs-lookup"><span data-stu-id="1d4af-103">_**Topic Last Modified:** 2016-03-21_</span></span>

<span data-ttu-id="1d4af-104">В этом разделе рассказывается, как спланировать общий внешний вид линии (SLA) в Lync Server 2013, накопительный пакет обновления от 2016 апреля.</span><span class="sxs-lookup"><span data-stu-id="1d4af-104">Read this topic to learn how to plan for Shared Line Appearance (SLA) in Lync Server 2013, Cumulative Update April 2016.</span></span>

<span data-ttu-id="1d4af-105">Общий внешний вид линии — это функция в Lync Server 2013, накопительный пакет обновления за Апрель 2016 для обработки нескольких звонков по определенному номеру, называемому общим номером.</span><span class="sxs-lookup"><span data-stu-id="1d4af-105">Shared Line Appearance is a feature in Lync Server 2013, Cumulative Update April 2016 for handling multiple calls on a specific number called a shared number.</span></span> <span data-ttu-id="1d4af-106">SLA может настроить любой пользователь Lync для корпоративной голосовой связи как общий номер с несколькими строками для ответа на несколько вызовов.</span><span class="sxs-lookup"><span data-stu-id="1d4af-106">SLA can configure any enterprise voice enabled Lync user as a shared number with multiple lines to respond to multiple calls.</span></span> <span data-ttu-id="1d4af-107">Вызовы на самом деле не приходятся на общий номер, вместо этого они пересылаются пользователям, которые действуют как делегаты для общего номера.</span><span class="sxs-lookup"><span data-stu-id="1d4af-107">The calls are not actually received on the shared number, instead they are forwarded to users that act as delegates for the shared number.</span></span> <span data-ttu-id="1d4af-108">Любой из представителей может получить вызов, пока остальные делегаты получат уведомление на своем телефоне о том, кто получил вызов, и какая строка стала занятой в результате.</span><span class="sxs-lookup"><span data-stu-id="1d4af-108">Any one of the delegates can pick up the call while the rest of the delegates get a notification on their phone about who picked up the call and which line has become busy as a result.</span></span> <span data-ttu-id="1d4af-109">Число строк и делегатов можно настраивать для общего числа в SLA.</span><span class="sxs-lookup"><span data-stu-id="1d4af-109">Both the number of lines and the delegates are configurable for a shared number in SLA.</span></span> <span data-ttu-id="1d4af-110">Кроме того, дополнительные параметры, такие как Бусйоптион (что происходит в ситуации, когда все линии заняты) и Мисседкаллоптион (случаи, когда ни один из представителей не берет вызов), также могут быть настроены для общего номера.</span><span class="sxs-lookup"><span data-stu-id="1d4af-110">In addition, advanced options, such as BusyOption (what happens in a situation when all lines are busy) and MissedCallOption (the case in which none of the delegates pick up a call), can also be configured for a shared number.</span></span>

<span data-ttu-id="1d4af-111">Соглашение об уровне обслуживания поддерживается только на следующих телефонных устройствах (оно не поддерживается для клиентов Lync на компьютерах, мобильных телефонах и других устройствах):</span><span class="sxs-lookup"><span data-stu-id="1d4af-111">SLA is supported only on the following phone devices (it is not supported for Lync clients on computers, mobile phones, or other devices):</span></span>

  - <span data-ttu-id="1d4af-112">Polycom VVX300 с обновлением встроенного по 5.4.1</span><span class="sxs-lookup"><span data-stu-id="1d4af-112">Polycom VVX300 with firmware update 5.4.1</span></span>

  - <span data-ttu-id="1d4af-113">Polycom VVX400 с обновлением встроенного по 5.4.1</span><span class="sxs-lookup"><span data-stu-id="1d4af-113">Polycom VVX400 with firmware update 5.4.1</span></span>

  - <span data-ttu-id="1d4af-114">Polycom VVX500 с обновлением встроенного по 5.4.1</span><span class="sxs-lookup"><span data-stu-id="1d4af-114">Polycom VVX500 with firmware update 5.4.1</span></span>

  - <span data-ttu-id="1d4af-115">Polycom VVX600 с обновлением встроенного по 5.4.1</span><span class="sxs-lookup"><span data-stu-id="1d4af-115">Polycom VVX600 with firmware update 5.4.1</span></span>

<span data-ttu-id="1d4af-116">SLA — это новая функция в Lync Server 2013, накопительный пакет обновления от 2016 апреля.</span><span class="sxs-lookup"><span data-stu-id="1d4af-116">SLA is a new feature in Lync Server 2013, Cumulative Update April 2016.</span></span>

<span data-ttu-id="1d4af-117">Сведения о развертывании SLA приведены [в статье Deploy Sharing Line Appearance in Lync Server 2013](lync-server-2013-deploy-shared-line-appearance.md).</span><span class="sxs-lookup"><span data-stu-id="1d4af-117">For information about deploying SLA, see [Deploy Shared Line Appearance in Lync Server 2013](lync-server-2013-deploy-shared-line-appearance.md).</span></span>

<div>

## <a name="feature-list"></a><span data-ttu-id="1d4af-118">Список компонентов</span><span class="sxs-lookup"><span data-stu-id="1d4af-118">Feature List</span></span>

<span data-ttu-id="1d4af-119">Настройка группы SLA позволяет выполнять указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="1d4af-119">Setting up an SLA group enables the following:</span></span>

  - <span data-ttu-id="1d4af-120">Все делегаты в группе могут отвечать на входящие звонки с одним и тем же общим номером.</span><span class="sxs-lookup"><span data-stu-id="1d4af-120">All delegates in the group can answer inbound calls to the same shared number.</span></span> <span data-ttu-id="1d4af-121">Звонки могут быть на основе PSTN или SIP.</span><span class="sxs-lookup"><span data-stu-id="1d4af-121">The calls can be PSTN-based or SIP-based.</span></span>

  - <span data-ttu-id="1d4af-122">Представители могут удерживать и принимать звонки.</span><span class="sxs-lookup"><span data-stu-id="1d4af-122">Delegates can hold and pick up calls.</span></span>

  - <span data-ttu-id="1d4af-123">Делегаты могут передавать звонки на номер, находящийся вне группы SLA.</span><span class="sxs-lookup"><span data-stu-id="1d4af-123">Delegates can transfer calls to a number outside of the SLA group.</span></span>

  - <span data-ttu-id="1d4af-124">Представители могут видеть количество звонков в данный момент, а также просматривать состояние каждого из этих вызовов.</span><span class="sxs-lookup"><span data-stu-id="1d4af-124">Delegates can see how many calls are currently on the shared number, and view the status of each of those calls.</span></span>

  - <span data-ttu-id="1d4af-125">Можно настроить максимальное количество одновременных вызовов для общего номера.</span><span class="sxs-lookup"><span data-stu-id="1d4af-125">You can configure a maximum number of concurrent calls for the shared number.</span></span> <span data-ttu-id="1d4af-126">Вы также можете задать способ обработки дополнительных звонков после достижения этого максимального значения.</span><span class="sxs-lookup"><span data-stu-id="1d4af-126">You can also set how you want additional calls to be handled after this maximum is reached.</span></span> <span data-ttu-id="1d4af-127">Лишние звонки могут отклоняться с помощью сигнала "занято", пересылки на другой номер или переадресация на голосовую почту.</span><span class="sxs-lookup"><span data-stu-id="1d4af-127">Excess calls can be rejected with a busy signal, forwarded to an alternate number, or forwarded to voice mail.</span></span>

  - <span data-ttu-id="1d4af-128">Вы можете настроить способ обработки пропущенных вызовов (вызовы, не выбранные в течение определенного времени).</span><span class="sxs-lookup"><span data-stu-id="1d4af-128">You can configure how you want missed calls (calls not picked up after a certain time) to be handled.</span></span> <span data-ttu-id="1d4af-129">Если для удостоверения группы включена голосовая почта, пропущенные звонки автоматически переходят на голосовую почту.</span><span class="sxs-lookup"><span data-stu-id="1d4af-129">If you enable voice mail for the group identity, missed calls automatically go to voice mail.</span></span> <span data-ttu-id="1d4af-130">Если для удостоверения группы (общего номера) не включена поддержка голосовой почты, вы можете отклонить пропущенные звонки с помощью сигнала "занято", пересылаться на другой номер или отключаться.</span><span class="sxs-lookup"><span data-stu-id="1d4af-130">If you do not have voice mail enabled for the group identity (shared number), you can choose for missed calls to be rejected with a busy signal, forwarded to an alternate number, or disconnected.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

