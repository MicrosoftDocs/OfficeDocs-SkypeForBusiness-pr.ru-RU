---
title: Очередь групп отклика Создать новые или изменить существующие
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/24/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.RgsQueueEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: cbdde536-8668-4a08-9862-8615e8691fd7
description: Очереди группы ответов удерживают вызовы в группе ответа до тех пор, пока агент не ответит на вызов.
ms.openlocfilehash: 4226c30ad560d4f5e5396b8af4ab657e55f087c6
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51122560"
---
# <a name="response-groups-queue-create-new-or-edit-existing"></a><span data-ttu-id="d60f0-103">Очередь группы ответа: создание новой или редактирование существующей</span><span class="sxs-lookup"><span data-stu-id="d60f0-103">Response Groups Queue: Create New or Edit Existing</span></span>

<span data-ttu-id="d60f0-104">Очереди группы ответов удерживают вызовы в группе ответа до тех пор, пока агент не ответит на вызов.</span><span class="sxs-lookup"><span data-stu-id="d60f0-104">Response Group queues hold calls to a response group until an agent answers the call.</span></span>

## <a name="ui-reference"></a><span data-ttu-id="d60f0-105">Ссылка на пользовательский интерфейс</span><span class="sxs-lookup"><span data-stu-id="d60f0-105">UI Reference</span></span>

<span data-ttu-id="d60f0-106">В следующем списке описываются поля на странице.</span><span class="sxs-lookup"><span data-stu-id="d60f0-106">The following list describes the fields on the page.</span></span>

- <span data-ttu-id="d60f0-107">**Имя** Каждая очередь должна иметь имя.</span><span class="sxs-lookup"><span data-stu-id="d60f0-107">**Name** Each queue must have a name.</span></span> <span data-ttu-id="d60f0-108">Введите описательное имя для очереди.</span><span class="sxs-lookup"><span data-stu-id="d60f0-108">Type a descriptive name for the queue.</span></span>

- <span data-ttu-id="d60f0-109">**Описание** Это поле является необязательным.</span><span class="sxs-lookup"><span data-stu-id="d60f0-109">**Description** This field is optional.</span></span> <span data-ttu-id="d60f0-110">Используйте его для указания дополнительных сведений об очереди.</span><span class="sxs-lookup"><span data-stu-id="d60f0-110">Use it to provide additional details about the queue.</span></span>

- <span data-ttu-id="d60f0-111">**Группы** Выберите группы агентов, которые необходимо назначить очереди.</span><span class="sxs-lookup"><span data-stu-id="d60f0-111">**Groups** Select the agent groups that you want to assign to the queue.</span></span> <span data-ttu-id="d60f0-112">Нажмите кнопку **Выбрать**, чтобы добавить группы агентов в список.</span><span class="sxs-lookup"><span data-stu-id="d60f0-112">Click **Select** to add agent groups to the list.</span></span> <span data-ttu-id="d60f0-113">Нажмите кнопку **Удалить**, чтобы удалить выбранную группу агентов из списка.</span><span class="sxs-lookup"><span data-stu-id="d60f0-113">Click **Remove** to delete the selected agent group from the list.</span></span>

    <span data-ttu-id="d60f0-114">Стрелки вверх и вниз позволяют переместить выбранную группу агентов вверх и вниз в списке агентов.</span><span class="sxs-lookup"><span data-stu-id="d60f0-114">The up and down arrows move a selected agent group up and down in the list.</span></span> <span data-ttu-id="d60f0-115">Порядок групп агентов влияет на порядок поиска skype для бизнеса Server для доступного агента.</span><span class="sxs-lookup"><span data-stu-id="d60f0-115">The order of agent groups affects the order in which Skype for Business Server searches for an available agent.</span></span> <span data-ttu-id="d60f0-116">Таким образом, первая группа в списке первой просматривается на наличие доступного агента, затем просматривается вторая группа и т. д.</span><span class="sxs-lookup"><span data-stu-id="d60f0-116">That is, the first group in the list is searched first for an available agent, followed by the second group, and so on.</span></span>

- <span data-ttu-id="d60f0-117">**Включить время ожидания очереди** Выберите этот контрольный ящик, чтобы указать максимальный период времени ожидания вызываемого до ответа агента на вызов.</span><span class="sxs-lookup"><span data-stu-id="d60f0-117">**Enable queue time-out** Select this check box to specify a maximum period of time for a caller to wait on hold before an agent answers the call.</span></span> <span data-ttu-id="d60f0-118">При выборе данного параметра вам также требуется задать следующее:</span><span class="sxs-lookup"><span data-stu-id="d60f0-118">If you select this option, you also need to specify the following:</span></span>

  - <span data-ttu-id="d60f0-119">**Период ожидания (секунд)** Выберите или введите максимальное количество секунд, которые вызываемая может подождать, прежде чем агент ответит на вызов.</span><span class="sxs-lookup"><span data-stu-id="d60f0-119">**Time-out period (seconds)** Select or type the maximum number of seconds a caller can wait before an agent answers the call.</span></span>

  - <span data-ttu-id="d60f0-120">**Действие вызова** Выберите действие, которое происходит при разовом вызове. Ваши варианты:</span><span class="sxs-lookup"><span data-stu-id="d60f0-120">**Call action** Select the action that occurs when a call times out. Your choices are:</span></span>

  - <span data-ttu-id="d60f0-121">**Disconnect**</span><span class="sxs-lookup"><span data-stu-id="d60f0-121">**Disconnect**</span></span>

  - <span data-ttu-id="d60f0-122">**Пересылать голосовую почту** При выборе этого параметра в **SIP-адресе** введите адрес голосовой почты в формате SIP: <username> @ <domainname> (например, sip:bob@contoso.com).</span><span class="sxs-lookup"><span data-stu-id="d60f0-122">**Forward to voice mail** If you select this option, in **SIP address**, type a voice mail address in the format sip:<username>@<domainname> (for example, sip:bob@contoso.com).</span></span>

  - <span data-ttu-id="d60f0-123">**Переад. на телефонный номер** При выборе этого параметра в **SIP-адресе** введите номер телефона в формате SIP: <number> @ <domainname> (например, sip:+14255550121@contoso.com).</span><span class="sxs-lookup"><span data-stu-id="d60f0-123">**Forward to telephone number** If you select this option, in **SIP address** type the telephone number in the format sip:<number>@<domainname> (for example, sip:+14255550121@contoso.com).</span></span>

  - <span data-ttu-id="d60f0-124">**Forward to SIP address** Выберите этот параметр, чтобы переадлить вызов другому пользователю.</span><span class="sxs-lookup"><span data-stu-id="d60f0-124">**Forward to SIP address** Select this option to forward the call to another user.</span></span> <span data-ttu-id="d60f0-125">В **SIP-адресе** введите URI для пользователя в формате SIP: <username> @ <domainname> .</span><span class="sxs-lookup"><span data-stu-id="d60f0-125">In **SIP address**, type the URI for the user in the format sip:<username>@<domainname>.</span></span>

  - <span data-ttu-id="d60f0-126">**Переадстройка в другую очередь** Если вы выберете этот параметр, просмотрите очередь, которая будет принимать вызовы при выходе вызовов.</span><span class="sxs-lookup"><span data-stu-id="d60f0-126">**Forward to another queue** If you select this option, browse to the queue that is to receive calls when the calls time out.</span></span>

- <span data-ttu-id="d60f0-127">**Включить переполнение очереди** Выберите этот контрольный ящик, чтобы указать максимальное количество вызовов, которые может держать очередь.</span><span class="sxs-lookup"><span data-stu-id="d60f0-127">**Enable queue overflow** Select this check box to specify a maximum number of calls that the queue can hold.</span></span> <span data-ttu-id="d60f0-128">При выборе данного параметра вам также требуется задать следующее:</span><span class="sxs-lookup"><span data-stu-id="d60f0-128">If you select this option, you also need to specify the following:</span></span>

  - <span data-ttu-id="d60f0-129">**Максимальное количество вызовов** Выберите или введите максимальное количество вызовов, которые может держать очередь.</span><span class="sxs-lookup"><span data-stu-id="d60f0-129">**Maximum number of calls** Select or type the maximum number of calls the queue can hold.</span></span>

  - <span data-ttu-id="d60f0-130">**Переад.** Выберите, какой вызов должен принять действие при превышении порогового значения переполнения очереди.</span><span class="sxs-lookup"><span data-stu-id="d60f0-130">**Forward the call** Select which call is to take action when the queue overflow threshold is met.</span></span>

  - <span data-ttu-id="d60f0-131">**Действие вызова** Выберите действие, которое происходит при превышении порогового значения переполнения очереди.</span><span class="sxs-lookup"><span data-stu-id="d60f0-131">**Call action** Select the action that occurs when the queue overflow threshold is met.</span></span> <span data-ttu-id="d60f0-132">Доступные варианты:</span><span class="sxs-lookup"><span data-stu-id="d60f0-132">Your choices are:</span></span>

  - <span data-ttu-id="d60f0-133">**Disconnect**</span><span class="sxs-lookup"><span data-stu-id="d60f0-133">**Disconnect**</span></span>

  - <span data-ttu-id="d60f0-134">**Пересылать голосовую почту** При выборе этого параметра в **SIP-адресе** введите адрес голосовой почты в формате SIP: <username> @ <domainname> (например, sip:bob@contoso.com).</span><span class="sxs-lookup"><span data-stu-id="d60f0-134">**Forward to voice mail** If you select this option, in **SIP address**, type a voice mail address in the format sip:<username>@<domainname> (for example, sip:bob@contoso.com).</span></span>

  - <span data-ttu-id="d60f0-135">**Переад. на телефонный номер** При выборе этого параметра в **SIP-адресе** введите номер телефона в формате SIP: <number> @ <domainname> (например, sip:+14255550121@contoso.com).</span><span class="sxs-lookup"><span data-stu-id="d60f0-135">**Forward to telephone number** If you select this option, in **SIP address** type the telephone number in the format sip:<number>@<domainname> (for example, sip:+14255550121@contoso.com).</span></span>

  - <span data-ttu-id="d60f0-136">**Forward to SIP address** Выберите этот параметр, чтобы переадлить вызов другому пользователю.</span><span class="sxs-lookup"><span data-stu-id="d60f0-136">**Forward to SIP address** Select this option to forward the call to another user.</span></span> <span data-ttu-id="d60f0-137">В **SIP-адресе** введите URI для пользователя в формате SIP: <username> @ <domainname> .</span><span class="sxs-lookup"><span data-stu-id="d60f0-137">In **SIP address**, type the URI for the user in the format sip:<username>@<domainname>.</span></span>

  - <span data-ttu-id="d60f0-138">**Переадстройка в другую очередь** Если выбран этот параметр, просмотрите очередь, которая будет принимать вызовы при превышении порога переполнения очереди.</span><span class="sxs-lookup"><span data-stu-id="d60f0-138">**Forward to another queue** If you select this option, browse to the queue that is to receive calls when the queue overflow threshold is met.</span></span>

<span data-ttu-id="d60f0-139">Подробные сведения о возможностях и возможностях группы реагирования см. в документе [Plan for the Response Group application in Skype for Business Server 2015.](../../plan-your-deployment/enterprise-voice-solution/response-group.md)</span><span class="sxs-lookup"><span data-stu-id="d60f0-139">For details about Response Group features and capabilities, see [Plan for the Response Group application in Skype for Business Server 2015](../../plan-your-deployment/enterprise-voice-solution/response-group.md) in the Planning documentation.</span></span> <span data-ttu-id="d60f0-140">Дополнительные сведения о работе с очередями см. в разделе [Managing Response Group Queues](/previous-versions/office/lync-server-2013/lync-server-2013-managing-response-group-queues) документации по использованию.</span><span class="sxs-lookup"><span data-stu-id="d60f0-140">For details about working with queues, see [Managing Response Group Queues](/previous-versions/office/lync-server-2013/lync-server-2013-managing-response-group-queues) in the Operations documentation.</span></span>