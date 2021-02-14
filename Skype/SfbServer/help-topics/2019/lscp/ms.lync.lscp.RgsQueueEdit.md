---
title: 'Очередь групп ответа: создание новой или редактирование существующей'
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.lscp.RgsQueueEdit
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: cbdde536-8668-4a08-9862-8615e8691fd7
ROBOTS: NOINDEX, NOFOLLOW
description: Очереди группы ответа удерживают звонки в группе ответа, пока агент не ответит на вызов.
ms.openlocfilehash: 097c28db7f2ae52d7ab0b362e828c8f05e132481
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49808199"
---
# <a name="response-groups-queue-create-new-or-edit-existing"></a><span data-ttu-id="2205b-103">Очередь группы ответа: создание новой или редактирование существующей</span><span class="sxs-lookup"><span data-stu-id="2205b-103">Response Groups Queue: Create New or Edit Existing</span></span>

<span data-ttu-id="2205b-104">Очереди группы ответа удерживают звонки в группе ответа, пока агент не ответит на вызов.</span><span class="sxs-lookup"><span data-stu-id="2205b-104">Response Group queues hold calls to a response group until an agent answers the call.</span></span>

## <a name="ui-reference"></a><span data-ttu-id="2205b-105">Ссылка на пользовательский интерфейс</span><span class="sxs-lookup"><span data-stu-id="2205b-105">UI Reference</span></span>

<span data-ttu-id="2205b-106">В следующем списке описываются поля на странице.</span><span class="sxs-lookup"><span data-stu-id="2205b-106">The following list describes the fields on the page.</span></span>

- <span data-ttu-id="2205b-107">**Имя** Каждая очередь должна иметь имя.</span><span class="sxs-lookup"><span data-stu-id="2205b-107">**Name** Each queue must have a name.</span></span> <span data-ttu-id="2205b-108">Введите описательное имя для очереди.</span><span class="sxs-lookup"><span data-stu-id="2205b-108">Type a descriptive name for the queue.</span></span>

- <span data-ttu-id="2205b-109">**Описание** Это поле является необязательным.</span><span class="sxs-lookup"><span data-stu-id="2205b-109">**Description** This field is optional.</span></span> <span data-ttu-id="2205b-110">Используйте его для указания дополнительных сведений об очереди.</span><span class="sxs-lookup"><span data-stu-id="2205b-110">Use it to provide additional details about the queue.</span></span>

- <span data-ttu-id="2205b-111">**Группы** Выберите группы агентов, которые нужно назначить очереди.</span><span class="sxs-lookup"><span data-stu-id="2205b-111">**Groups** Select the agent groups that you want to assign to the queue.</span></span> <span data-ttu-id="2205b-112">Нажмите кнопку **Выбрать**, чтобы добавить группы агентов в список.</span><span class="sxs-lookup"><span data-stu-id="2205b-112">Click **Select** to add agent groups to the list.</span></span> <span data-ttu-id="2205b-113">Нажмите кнопку **Удалить**, чтобы удалить выбранную группу агентов из списка.</span><span class="sxs-lookup"><span data-stu-id="2205b-113">Click **Remove** to delete the selected agent group from the list.</span></span>

    <span data-ttu-id="2205b-114">Стрелки вверх и вниз позволяют переместить выбранную группу агентов вверх и вниз в списке агентов.</span><span class="sxs-lookup"><span data-stu-id="2205b-114">The up and down arrows move a selected agent group up and down in the list.</span></span> <span data-ttu-id="2205b-115">Порядок групп агентов влияет на порядок поиска доступного агента в Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="2205b-115">The order of agent groups affects the order in which Skype for Business Server searches for an available agent.</span></span> <span data-ttu-id="2205b-116">Таким образом, первая группа в списке первой просматривается на наличие доступного агента, затем просматривается вторая группа и т. д.</span><span class="sxs-lookup"><span data-stu-id="2205b-116">That is, the first group in the list is searched first for an available agent, followed by the second group, and so on.</span></span>

- <span data-ttu-id="2205b-117">**Включить время ожидания очереди** Чтобы задать максимальный период ожидания вызова на удержании, выбранный агентом.</span><span class="sxs-lookup"><span data-stu-id="2205b-117">**Enable queue time-out** Select this check box to specify a maximum period of time for a caller to wait on hold before an agent answers the call.</span></span> <span data-ttu-id="2205b-118">При выборе данного параметра вам также требуется задать следующее:</span><span class="sxs-lookup"><span data-stu-id="2205b-118">If you select this option, you also need to specify the following:</span></span>

  - <span data-ttu-id="2205b-119">**Период времени ожидания (секунд)** Выберите или введите максимальное количество секунд, в течение которые звоняя может подождать, прежде чем агент ответит на вызов.</span><span class="sxs-lookup"><span data-stu-id="2205b-119">**Time-out period (seconds)** Select or type the maximum number of seconds a caller can wait before an agent answers the call.</span></span>

  - <span data-ttu-id="2205b-120">**Действие вызова** Выберите действие, которое будет происходить, когда время вызова не будет времени действия. У вас есть варианты:</span><span class="sxs-lookup"><span data-stu-id="2205b-120">**Call action** Select the action that occurs when a call times out. Your choices are:</span></span>

  - <span data-ttu-id="2205b-121">**Disconnect**</span><span class="sxs-lookup"><span data-stu-id="2205b-121">**Disconnect**</span></span>

  - <span data-ttu-id="2205b-122">**Пересылать на голосовую почту** При выборе этого параметра в **SIP-адресе** введите адрес голосовой почты в формате sip: <username> @ <domainname> (например, sip:bob@contoso.com).</span><span class="sxs-lookup"><span data-stu-id="2205b-122">**Forward to voice mail** If you select this option, in **SIP address**, type a voice mail address in the format sip:<username>@<domainname> (for example, sip:bob@contoso.com).</span></span>

  - <span data-ttu-id="2205b-123">**Переад вперед на номер телефона** При выборе этого параметра в **SIP-адресе** введите номер телефона в формате SIP: <number> @ <domainname> (например, sip:+14255550121@contoso.com).</span><span class="sxs-lookup"><span data-stu-id="2205b-123">**Forward to telephone number** If you select this option, in **SIP address** type the telephone number in the format sip:<number>@<domainname> (for example, sip:+14255550121@contoso.com).</span></span>

  - <span data-ttu-id="2205b-124">**Переад вперед на SIP-адрес** Выберите этот параметр, чтобы перенаадранить звонок другому пользователю.</span><span class="sxs-lookup"><span data-stu-id="2205b-124">**Forward to SIP address** Select this option to forward the call to another user.</span></span> <span data-ttu-id="2205b-125">В **SIP-адресе** введите URI пользователя в формате sip: <username> @ <domainname> .</span><span class="sxs-lookup"><span data-stu-id="2205b-125">In **SIP address**, type the URI for the user in the format sip:<username>@<domainname>.</span></span>

  - <span data-ttu-id="2205b-126">**Переадстройка в другую очередь** Если выбран этот параметр, перейдите к очереди, которая будет принимать звонки по и время ожидания звонков.</span><span class="sxs-lookup"><span data-stu-id="2205b-126">**Forward to another queue** If you select this option, browse to the queue that is to receive calls when the calls time out.</span></span>

- <span data-ttu-id="2205b-127">**Включить переполнение очереди** Чтобы указать максимальное количество звонков, которые могут быть в очереди, выберите этот контроль.</span><span class="sxs-lookup"><span data-stu-id="2205b-127">**Enable queue overflow** Select this check box to specify a maximum number of calls that the queue can hold.</span></span> <span data-ttu-id="2205b-128">При выборе данного параметра вам также требуется задать следующее:</span><span class="sxs-lookup"><span data-stu-id="2205b-128">If you select this option, you also need to specify the following:</span></span>

  - <span data-ttu-id="2205b-129">**Максимальное количество вызовов** Выберите или введите максимальное число вызовов, которые может удерживать очередь.</span><span class="sxs-lookup"><span data-stu-id="2205b-129">**Maximum number of calls** Select or type the maximum number of calls the queue can hold.</span></span>

  - <span data-ttu-id="2205b-130">**Переад вперед вызов** Выберите вызов, который будет принимать действие при превышении порогового значения переполнения очереди.</span><span class="sxs-lookup"><span data-stu-id="2205b-130">**Forward the call** Select which call is to take action when the queue overflow threshold is met.</span></span>

  - <span data-ttu-id="2205b-131">**Действие вызова** Выберите действие, которое происходит при превышении порогового значения переполнения очереди.</span><span class="sxs-lookup"><span data-stu-id="2205b-131">**Call action** Select the action that occurs when the queue overflow threshold is met.</span></span> <span data-ttu-id="2205b-132">Доступные варианты:</span><span class="sxs-lookup"><span data-stu-id="2205b-132">Your choices are:</span></span>

  - <span data-ttu-id="2205b-133">**Disconnect**</span><span class="sxs-lookup"><span data-stu-id="2205b-133">**Disconnect**</span></span>

  - <span data-ttu-id="2205b-134">**Пересылать на голосовую почту** При выборе этого параметра в **SIP-адресе** введите адрес голосовой почты в формате sip: <username> @ <domainname> (например, sip:bob@contoso.com).</span><span class="sxs-lookup"><span data-stu-id="2205b-134">**Forward to voice mail** If you select this option, in **SIP address**, type a voice mail address in the format sip:<username>@<domainname> (for example, sip:bob@contoso.com).</span></span>

  - <span data-ttu-id="2205b-135">**Переад вперед на номер телефона** При выборе этого параметра в **SIP-адресе** введите номер телефона в формате SIP: <number> @ <domainname> (например, sip:+14255550121@contoso.com).</span><span class="sxs-lookup"><span data-stu-id="2205b-135">**Forward to telephone number** If you select this option, in **SIP address** type the telephone number in the format sip:<number>@<domainname> (for example, sip:+14255550121@contoso.com).</span></span>

  - <span data-ttu-id="2205b-136">**Переад вперед на SIP-адрес** Выберите этот параметр, чтобы перенаадранить звонок другому пользователю.</span><span class="sxs-lookup"><span data-stu-id="2205b-136">**Forward to SIP address** Select this option to forward the call to another user.</span></span> <span data-ttu-id="2205b-137">В **SIP-адресе** введите URI пользователя в формате sip: <username> @ <domainname> .</span><span class="sxs-lookup"><span data-stu-id="2205b-137">In **SIP address**, type the URI for the user in the format sip:<username>@<domainname>.</span></span>

  - <span data-ttu-id="2205b-138">**Переадстройка в другую очередь** При выборе этого параметра перейдите к очереди, которая будет принимать вызовы при превышении порогового значения переполнения очереди.</span><span class="sxs-lookup"><span data-stu-id="2205b-138">**Forward to another queue** If you select this option, browse to the queue that is to receive calls when the queue overflow threshold is met.</span></span>

<span data-ttu-id="2205b-139">For details about Response Group features and capabilities, see [Plan for the Response Group application in Skype for Business Server](../../../plan-your-deployment/enterprise-voice-solution/response-group.md) in the Planning documentation.</span><span class="sxs-lookup"><span data-stu-id="2205b-139">For details about Response Group features and capabilities, see [Plan for the Response Group application in Skype for Business Server](../../../plan-your-deployment/enterprise-voice-solution/response-group.md) in the Planning documentation.</span></span> <span data-ttu-id="2205b-140">Дополнительные сведения о работе с очередями см. в разделе [Managing Response Group Queues](https://technet.microsoft.com/library/1e91720c-ab67-4dfb-b30c-0ef2a8012310.aspx) документации по использованию.</span><span class="sxs-lookup"><span data-stu-id="2205b-140">For details about working with queues, see [Managing Response Group Queues](https://technet.microsoft.com/library/1e91720c-ab67-4dfb-b30c-0ef2a8012310.aspx) in the Operations documentation.</span></span>


