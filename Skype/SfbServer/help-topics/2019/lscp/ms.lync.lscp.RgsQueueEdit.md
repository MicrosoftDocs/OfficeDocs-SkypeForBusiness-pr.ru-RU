---
title: Очередь групп ответа создание нового или изменение существующего
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: Очереди групп ответа содержат звонки в группу ответа до тех пор, пока агент не ответит на звонок.
ms.openlocfilehash: 9cf88e66886794ee016f1faa03c4ee773ea568b7
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41793497"
---
# <a name="response-groups-queue-create-new-or-edit-existing"></a><span data-ttu-id="fd382-103">Очередь группы ответа: создание новой или редактирование существующей</span><span class="sxs-lookup"><span data-stu-id="fd382-103">Response Groups Queue: Create New or Edit Existing</span></span>

<span data-ttu-id="fd382-104">Очереди групп ответа содержат звонки в группу ответа до тех пор, пока агент не ответит на звонок.</span><span class="sxs-lookup"><span data-stu-id="fd382-104">Response Group queues hold calls to a response group until an agent answers the call.</span></span>

## <a name="ui-reference"></a><span data-ttu-id="fd382-105">Ссылка на пользовательский интерфейс</span><span class="sxs-lookup"><span data-stu-id="fd382-105">UI Reference</span></span>

<span data-ttu-id="fd382-106">В следующем списке описываются поля на странице.</span><span class="sxs-lookup"><span data-stu-id="fd382-106">The following list describes the fields on the page.</span></span>

- <span data-ttu-id="fd382-107">**Name (имя** ) Каждая очередь должна иметь имя.</span><span class="sxs-lookup"><span data-stu-id="fd382-107">**Name** Each queue must have a name.</span></span> <span data-ttu-id="fd382-108">Введите описательное имя для очереди.</span><span class="sxs-lookup"><span data-stu-id="fd382-108">Type a descriptive name for the queue.</span></span>

- <span data-ttu-id="fd382-109">**Description (описание** ) Это поле является необязательным.</span><span class="sxs-lookup"><span data-stu-id="fd382-109">**Description** This field is optional.</span></span> <span data-ttu-id="fd382-110">Используйте его для указания дополнительных сведений об очереди.</span><span class="sxs-lookup"><span data-stu-id="fd382-110">Use it to provide additional details about the queue.</span></span>

- <span data-ttu-id="fd382-111">**Групп** Выберите группы агентов, которые вы хотите назначить очереди.</span><span class="sxs-lookup"><span data-stu-id="fd382-111">**Groups** Select the agent groups that you want to assign to the queue.</span></span> <span data-ttu-id="fd382-112">Нажмите кнопку **Выбрать**, чтобы добавить группы агентов в список.</span><span class="sxs-lookup"><span data-stu-id="fd382-112">Click **Select** to add agent groups to the list.</span></span> <span data-ttu-id="fd382-113">Нажмите кнопку **Удалить**, чтобы удалить выбранную группу агентов из списка.</span><span class="sxs-lookup"><span data-stu-id="fd382-113">Click **Remove** to delete the selected agent group from the list.</span></span>

    <span data-ttu-id="fd382-114">Стрелки вверх и вниз позволяют переместить выбранную группу агентов вверх и вниз в списке агентов.</span><span class="sxs-lookup"><span data-stu-id="fd382-114">The up and down arrows move a selected agent group up and down in the list.</span></span> <span data-ttu-id="fd382-115">Порядок групп агентов влияет на порядок, в котором сервер Skype для бизнеса Server ищет доступный агент.</span><span class="sxs-lookup"><span data-stu-id="fd382-115">The order of agent groups affects the order in which Skype for Business Server searches for an available agent.</span></span> <span data-ttu-id="fd382-116">Таким образом, первая группа в списке первой просматривается на наличие доступного агента, затем просматривается вторая группа и т. д.</span><span class="sxs-lookup"><span data-stu-id="fd382-116">That is, the first group in the list is searched first for an available agent, followed by the second group, and so on.</span></span>

- <span data-ttu-id="fd382-117">**Включить время ожидания очереди** Установите этот флажок, чтобы задать максимальный период времени, в течение которого вызывающий абонент ждет удержания, прежде чем агент ответит на звонок.</span><span class="sxs-lookup"><span data-stu-id="fd382-117">**Enable queue time-out** Select this check box to specify a maximum period of time for a caller to wait on hold before an agent answers the call.</span></span> <span data-ttu-id="fd382-118">При выборе данного параметра вам также требуется задать следующее:</span><span class="sxs-lookup"><span data-stu-id="fd382-118">If you select this option, you also need to specify the following:</span></span>

  - <span data-ttu-id="fd382-119">**Время ожидания (в секундах)** Выберите или введите максимальное количество секунд, в течение которого вызывающий абонент может подождать, пока агент ответит на звонок.</span><span class="sxs-lookup"><span data-stu-id="fd382-119">**Time-out period (seconds)** Select or type the maximum number of seconds a caller can wait before an agent answers the call.</span></span>

  - <span data-ttu-id="fd382-120">**Действие звонка** Выберите действие, которое будет выполняться при истечении времени ожидания звонка. Доступны следующие варианты:</span><span class="sxs-lookup"><span data-stu-id="fd382-120">**Call action** Select the action that occurs when a call times out. Your choices are:</span></span>

  - <span data-ttu-id="fd382-121">**Отключить**</span><span class="sxs-lookup"><span data-stu-id="fd382-121">**Disconnect**</span></span>

  - <span data-ttu-id="fd382-122">**Пересылка на голосовую почту** Если выбрать этот параметр, в поле **адрес SIP**введите адрес голосовой почты в формате SIP:<username> @ <domainname> (например, SIP:Bob@contoso.com).</span><span class="sxs-lookup"><span data-stu-id="fd382-122">**Forward to voice mail** If you select this option, in **SIP address**, type a voice mail address in the format sip:<username>@<domainname> (for example, sip:bob@contoso.com).</span></span>

  - <span data-ttu-id="fd382-123">**Переадресовать на номер телефона** Если выбрать этот параметр, в поле **адрес SIP** введите номер телефона в формате SIP:<number> @ <domainname> (например, SIP:+14255550121@contoso.com).</span><span class="sxs-lookup"><span data-stu-id="fd382-123">**Forward to telephone number** If you select this option, in **SIP address** type the telephone number in the format sip:<number>@<domainname> (for example, sip:+14255550121@contoso.com).</span></span>

  - <span data-ttu-id="fd382-124">**Переадресация на адрес SIP** Выберите этот параметр, чтобы переслать звонок другому пользователю.</span><span class="sxs-lookup"><span data-stu-id="fd382-124">**Forward to SIP address** Select this option to forward the call to another user.</span></span> <span data-ttu-id="fd382-125">В поле **адрес SIP**введите URI для пользователя в формате SIP:<username>@<domainname>.</span><span class="sxs-lookup"><span data-stu-id="fd382-125">In **SIP address**, type the URI for the user in the format sip:<username>@<domainname>.</span></span>

  - <span data-ttu-id="fd382-126">**Пересылка в другую очередь** Если выбрать этот параметр, перейдите в очередь, которая должна принимать звонки при истечении времени ожидания звонков.</span><span class="sxs-lookup"><span data-stu-id="fd382-126">**Forward to another queue** If you select this option, browse to the queue that is to receive calls when the calls time out.</span></span>

- <span data-ttu-id="fd382-127">**Включить переполнение очереди** Установите этот флажок, чтобы указать максимальное количество звонков, которые может содержать очередь.</span><span class="sxs-lookup"><span data-stu-id="fd382-127">**Enable queue overflow** Select this check box to specify a maximum number of calls that the queue can hold.</span></span> <span data-ttu-id="fd382-128">При выборе данного параметра вам также требуется задать следующее:</span><span class="sxs-lookup"><span data-stu-id="fd382-128">If you select this option, you also need to specify the following:</span></span>

  - <span data-ttu-id="fd382-129">**Максимальное количество звонков** Выберите или введите максимальное количество звонков, которое может содержать очередь.</span><span class="sxs-lookup"><span data-stu-id="fd382-129">**Maximum number of calls** Select or type the maximum number of calls the queue can hold.</span></span>

  - <span data-ttu-id="fd382-130">**Переадресация звонка** Выберите, какой из вызовов должен выполняться при выполнении порогового значения переполнения очереди.</span><span class="sxs-lookup"><span data-stu-id="fd382-130">**Forward the call** Select which call is to take action when the queue overflow threshold is met.</span></span>

  - <span data-ttu-id="fd382-131">**Действие звонка** Выберите действие, которое выполняется при выполнении порогового значения переполнения очереди.</span><span class="sxs-lookup"><span data-stu-id="fd382-131">**Call action** Select the action that occurs when the queue overflow threshold is met.</span></span> <span data-ttu-id="fd382-132">Доступные варианты:</span><span class="sxs-lookup"><span data-stu-id="fd382-132">Your choices are:</span></span>

  - <span data-ttu-id="fd382-133">**Отключить**</span><span class="sxs-lookup"><span data-stu-id="fd382-133">**Disconnect**</span></span>

  - <span data-ttu-id="fd382-134">**Пересылка на голосовую почту** Если выбрать этот параметр, в поле **адрес SIP**введите адрес голосовой почты в формате SIP:<username> @ <domainname> (например, SIP:Bob@contoso.com).</span><span class="sxs-lookup"><span data-stu-id="fd382-134">**Forward to voice mail** If you select this option, in **SIP address**, type a voice mail address in the format sip:<username>@<domainname> (for example, sip:bob@contoso.com).</span></span>

  - <span data-ttu-id="fd382-135">**Переадресовать на номер телефона** Если выбрать этот параметр, в поле **адрес SIP** введите номер телефона в формате SIP:<number> @ <domainname> (например, SIP:+14255550121@contoso.com).</span><span class="sxs-lookup"><span data-stu-id="fd382-135">**Forward to telephone number** If you select this option, in **SIP address** type the telephone number in the format sip:<number>@<domainname> (for example, sip:+14255550121@contoso.com).</span></span>

  - <span data-ttu-id="fd382-136">**Переадресация на адрес SIP** Выберите этот параметр, чтобы переслать звонок другому пользователю.</span><span class="sxs-lookup"><span data-stu-id="fd382-136">**Forward to SIP address** Select this option to forward the call to another user.</span></span> <span data-ttu-id="fd382-137">В поле **адрес SIP**введите URI для пользователя в формате SIP:<username>@<domainname>.</span><span class="sxs-lookup"><span data-stu-id="fd382-137">In **SIP address**, type the URI for the user in the format sip:<username>@<domainname>.</span></span>

  - <span data-ttu-id="fd382-138">**Пересылка в другую очередь** Если выбрать этот параметр, перейдите в очередь, которая должна получать вызовы при выполнении порогового значения переполнения очереди.</span><span class="sxs-lookup"><span data-stu-id="fd382-138">**Forward to another queue** If you select this option, browse to the queue that is to receive calls when the queue overflow threshold is met.</span></span>

<span data-ttu-id="fd382-139">Дополнительные сведения о функциях и возможностях групп ответов можно найти [в разделе Планирование приложения группы ответа в Skype для бизнеса Server](../../../plan-your-deployment/enterprise-voice-solution/response-group.md) в документации по планированию.</span><span class="sxs-lookup"><span data-stu-id="fd382-139">For details about Response Group features and capabilities, see [Plan for the Response Group application in Skype for Business Server](../../../plan-your-deployment/enterprise-voice-solution/response-group.md) in the Planning documentation.</span></span> <span data-ttu-id="fd382-140">Дополнительные сведения о работе с очередями см. в разделе [Managing Response Group Queues](https://technet.microsoft.com/library/1e91720c-ab67-4dfb-b30c-0ef2a8012310.aspx) документации по использованию.</span><span class="sxs-lookup"><span data-stu-id="fd382-140">For details about working with queues, see [Managing Response Group Queues](https://technet.microsoft.com/library/1e91720c-ab67-4dfb-b30c-0ef2a8012310.aspx) in the Operations documentation.</span></span>


