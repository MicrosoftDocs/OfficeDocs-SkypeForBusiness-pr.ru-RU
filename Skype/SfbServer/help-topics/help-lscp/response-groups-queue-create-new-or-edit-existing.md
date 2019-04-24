---
title: Создание новой или редактирование существующей очереди группы ответа
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 3/24/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.RgsQueueEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: cbdde536-8668-4a08-9862-8615e8691fd7
description: Очереди группы ответа хранят звонки в группу ответа, пока агент отвечает на звонок.
ms.openlocfilehash: d00d43ab50060990341a2071ea68126ebc445a21
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "32200585"
---
# <a name="response-groups-queue-create-new-or-edit-existing"></a><span data-ttu-id="4d098-103">Очередь группы ответа: создание новой или редактирование существующей</span><span class="sxs-lookup"><span data-stu-id="4d098-103">Response Groups Queue: Create New or Edit Existing</span></span>

<span data-ttu-id="4d098-104">Очереди группы ответа хранят звонки в группу ответа, пока агент отвечает на звонок.</span><span class="sxs-lookup"><span data-stu-id="4d098-104">Response Group queues hold calls to a response group until an agent answers the call.</span></span>

## <a name="ui-reference"></a><span data-ttu-id="4d098-105">Ссылка на пользовательский интерфейс</span><span class="sxs-lookup"><span data-stu-id="4d098-105">UI Reference</span></span>

<span data-ttu-id="4d098-106">В следующем списке описываются поля на странице.</span><span class="sxs-lookup"><span data-stu-id="4d098-106">The following list describes the fields on the page.</span></span>

- <span data-ttu-id="4d098-107">**Имя** Каждой очереди должен иметь имя.</span><span class="sxs-lookup"><span data-stu-id="4d098-107">**Name** Each queue must have a name.</span></span> <span data-ttu-id="4d098-108">Введите описательное имя для очереди.</span><span class="sxs-lookup"><span data-stu-id="4d098-108">Type a descriptive name for the queue.</span></span>

- <span data-ttu-id="4d098-109">**Описание** Это поле является необязательным.</span><span class="sxs-lookup"><span data-stu-id="4d098-109">**Description** This field is optional.</span></span> <span data-ttu-id="4d098-110">Используйте его для указания дополнительных сведений об очереди.</span><span class="sxs-lookup"><span data-stu-id="4d098-110">Use it to provide additional details about the queue.</span></span>

- <span data-ttu-id="4d098-111">**Группы** Выбор групп агентов, которые необходимо назначить очереди.</span><span class="sxs-lookup"><span data-stu-id="4d098-111">**Groups** Select the agent groups that you want to assign to the queue.</span></span> <span data-ttu-id="4d098-112">Нажмите кнопку **Выбрать**, чтобы добавить группы агентов в список.</span><span class="sxs-lookup"><span data-stu-id="4d098-112">Click **Select** to add agent groups to the list.</span></span> <span data-ttu-id="4d098-113">Нажмите кнопку **Удалить**, чтобы удалить выбранную группу агентов из списка.</span><span class="sxs-lookup"><span data-stu-id="4d098-113">Click **Remove** to delete the selected agent group from the list.</span></span>

    <span data-ttu-id="4d098-114">Стрелки вверх и вниз позволяют переместить выбранную группу агентов вверх и вниз в списке агентов.</span><span class="sxs-lookup"><span data-stu-id="4d098-114">The up and down arrows move a selected agent group up and down in the list.</span></span> <span data-ttu-id="4d098-115">Порядок групп агентов влияет на порядок, в котором Скайп для Business Server выполняет поиск доступного агента.</span><span class="sxs-lookup"><span data-stu-id="4d098-115">The order of agent groups affects the order in which Skype for Business Server searches for an available agent.</span></span> <span data-ttu-id="4d098-116">Таким образом, первая группа в списке первой просматривается на наличие доступного агента, затем просматривается вторая группа и т. д.</span><span class="sxs-lookup"><span data-stu-id="4d098-116">That is, the first group in the list is searched first for an available agent, followed by the second group, and so on.</span></span>

- <span data-ttu-id="4d098-117">**Включить время ожидания очереди** Установите этот флажок, чтобы указать максимальный период времени для вызывающей стороне дождаться агент отвечает на звонок.</span><span class="sxs-lookup"><span data-stu-id="4d098-117">**Enable queue time-out** Select this check box to specify a maximum period of time for a caller to wait on hold before an agent answers the call.</span></span> <span data-ttu-id="4d098-118">При выборе данного параметра вам также требуется задать следующее:</span><span class="sxs-lookup"><span data-stu-id="4d098-118">If you select this option, you also need to specify the following:</span></span>

  - <span data-ttu-id="4d098-119">**Период времени ожидания (в секундах)** Выберите или введите максимальное число секунд, можно ожидания абонента до агент отвечает на звонок.</span><span class="sxs-lookup"><span data-stu-id="4d098-119">**Time-out period (seconds)** Select or type the maximum number of seconds a caller can wait before an agent answers the call.</span></span>

  - <span data-ttu-id="4d098-120">**Действие вызова** Выберите действие, выполняемое после завершения периода ожидания. Возможны следующие значения.</span><span class="sxs-lookup"><span data-stu-id="4d098-120">**Call action** Select the action that occurs when a call times out. Your choices are:</span></span>

  - <span data-ttu-id="4d098-121">**Отключить**</span><span class="sxs-lookup"><span data-stu-id="4d098-121">**Disconnect**</span></span>

  - <span data-ttu-id="4d098-122">**Переадресовывать на номер голосовой почты** При выборе этого параметра в **SIP-адрес**введите адрес голосовой почты в формате sip:<username> @ <domainname> (например, sip:bob@contoso.com).</span><span class="sxs-lookup"><span data-stu-id="4d098-122">**Forward to voice mail** If you select this option, in **SIP address**, type a voice mail address in the format sip:<username>@<domainname> (for example, sip:bob@contoso.com).</span></span>

  - <span data-ttu-id="4d098-123">**Переадресовывать на номер телефона** При выборе этого параметра в **SIP-адрес** введите номер телефона в формате sip:<number> @ <domainname> (например, sip:+14255550121@contoso.com).</span><span class="sxs-lookup"><span data-stu-id="4d098-123">**Forward to telephone number** If you select this option, in **SIP address** type the telephone number in the format sip:<number>@<domainname> (for example, sip:+14255550121@contoso.com).</span></span>

  - <span data-ttu-id="4d098-124">**Перенаправлять на SIP-адрес** Установите этот флажок, чтобы переадресовать звонок на другого пользователя.</span><span class="sxs-lookup"><span data-stu-id="4d098-124">**Forward to SIP address** Select this option to forward the call to another user.</span></span> <span data-ttu-id="4d098-125">В поле **SIP-адрес**, введите URI для пользователя в формате sip:<username>@<domainname>.</span><span class="sxs-lookup"><span data-stu-id="4d098-125">In **SIP address**, type the URI for the user in the format sip:<username>@<domainname>.</span></span>

  - <span data-ttu-id="4d098-126">**Вперед в другую очередь** Если выбран этот параметр, перейдите в очередь, которая будет получать вызовы при времени ожидания вызовов.</span><span class="sxs-lookup"><span data-stu-id="4d098-126">**Forward to another queue** If you select this option, browse to the queue that is to receive calls when the calls time out.</span></span>

- <span data-ttu-id="4d098-127">**Включить Переполнение очереди** Установите этот флажок, чтобы указать максимальное число вызовов в очереди.</span><span class="sxs-lookup"><span data-stu-id="4d098-127">**Enable queue overflow** Select this check box to specify a maximum number of calls that the queue can hold.</span></span> <span data-ttu-id="4d098-128">При выборе данного параметра вам также требуется задать следующее:</span><span class="sxs-lookup"><span data-stu-id="4d098-128">If you select this option, you also need to specify the following:</span></span>

  - <span data-ttu-id="4d098-129">**Максимальное число звонков** Выберите или введите максимальное число звонков в очереди.</span><span class="sxs-lookup"><span data-stu-id="4d098-129">**Maximum number of calls** Select or type the maximum number of calls the queue can hold.</span></span>

  - <span data-ttu-id="4d098-130">**Переадресация звонка** Выберите звонок, который выполнение действий при превышении очереди.</span><span class="sxs-lookup"><span data-stu-id="4d098-130">**Forward the call** Select which call is to take action when the queue overflow threshold is met.</span></span>

  - <span data-ttu-id="4d098-131">**Действие вызова** Выберите действие, выполняемое при превышении очереди.</span><span class="sxs-lookup"><span data-stu-id="4d098-131">**Call action** Select the action that occurs when the queue overflow threshold is met.</span></span> <span data-ttu-id="4d098-132">Доступные варианты:</span><span class="sxs-lookup"><span data-stu-id="4d098-132">Your choices are:</span></span>

  - <span data-ttu-id="4d098-133">**Отключить**</span><span class="sxs-lookup"><span data-stu-id="4d098-133">**Disconnect**</span></span>

  - <span data-ttu-id="4d098-134">**Переадресовывать на номер голосовой почты** При выборе этого параметра в **SIP-адрес**введите адрес голосовой почты в формате sip:<username> @ <domainname> (например, sip:bob@contoso.com).</span><span class="sxs-lookup"><span data-stu-id="4d098-134">**Forward to voice mail** If you select this option, in **SIP address**, type a voice mail address in the format sip:<username>@<domainname> (for example, sip:bob@contoso.com).</span></span>

  - <span data-ttu-id="4d098-135">**Переадресовывать на номер телефона** При выборе этого параметра в **SIP-адрес** введите номер телефона в формате sip:<number> @ <domainname> (например, sip:+14255550121@contoso.com).</span><span class="sxs-lookup"><span data-stu-id="4d098-135">**Forward to telephone number** If you select this option, in **SIP address** type the telephone number in the format sip:<number>@<domainname> (for example, sip:+14255550121@contoso.com).</span></span>

  - <span data-ttu-id="4d098-136">**Перенаправлять на SIP-адрес** Установите этот флажок, чтобы переадресовать звонок на другого пользователя.</span><span class="sxs-lookup"><span data-stu-id="4d098-136">**Forward to SIP address** Select this option to forward the call to another user.</span></span> <span data-ttu-id="4d098-137">В поле **SIP-адрес**, введите URI для пользователя в формате sip:<username>@<domainname>.</span><span class="sxs-lookup"><span data-stu-id="4d098-137">In **SIP address**, type the URI for the user in the format sip:<username>@<domainname>.</span></span>

  - <span data-ttu-id="4d098-138">**Вперед в другую очередь** Если выбран этот параметр, перейдите в очередь, который должен принимать звонки, при превышении очереди.</span><span class="sxs-lookup"><span data-stu-id="4d098-138">**Forward to another queue** If you select this option, browse to the queue that is to receive calls when the queue overflow threshold is met.</span></span>

<span data-ttu-id="4d098-139">Для получения дополнительных сведений о группы ответа функций и возможностей см. в документации по планированию [Планирование приложения группы ответа в Скайп для Business Server 2015](../../plan-your-deployment/enterprise-voice-solution/response-group.md) .</span><span class="sxs-lookup"><span data-stu-id="4d098-139">For details about Response Group features and capabilities, see [Plan for the Response Group application in Skype for Business Server 2015](../../plan-your-deployment/enterprise-voice-solution/response-group.md) in the Planning documentation.</span></span> <span data-ttu-id="4d098-140">Дополнительные сведения о работе с очередями см. в разделе [Managing Response Group Queues](https://technet.microsoft.com/library/1e91720c-ab67-4dfb-b30c-0ef2a8012310.aspx) документации по использованию.</span><span class="sxs-lookup"><span data-stu-id="4d098-140">For details about working with queues, see [Managing Response Group Queues](https://technet.microsoft.com/library/1e91720c-ab67-4dfb-b30c-0ef2a8012310.aspx) in the Operations documentation.</span></span>


