---
title: Соответствие требованиям в Microsoft Teams
author: robmazz
ms.author: robmazz
manager: laurawi
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: anwara
description: Обучение обеспечению соответствия требованиям в рамках набора решений для оценки рисков для insider с точки зрения Microsoft Teams (это часть функции соответствия требованиям в связи с M365).
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: bb9400778b8e000a438343e74bc6b030087ff297
ms.sourcegitcommit: 739ffd5893abf6d181877d1110f9dc8230b3bfd2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/01/2020
ms.locfileid: "48328258"
---
# <a name="communication-compliance-with-microsoft-teams"></a><span data-ttu-id="f93f2-103">Соответствие требованиям в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="f93f2-103">Communication compliance with Microsoft Teams</span></span>

<span data-ttu-id="f93f2-104">Соответствие требованиям связи — это решение для оценки рисков в Microsoft 365, помогающее свести к минимуму риски связи, помогая выявлять, фиксировать и действовать с недопустимыми сообщениями в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="f93f2-104">Communication compliance is an insider risk solution in Microsoft 365 that helps minimize communication risks by helping you detect, capture, and act on inappropriate messages in your organization.</span></span>

<span data-ttu-id="f93f2-105">В Microsoft Teams соответствие требованиям [](https://docs.microsoft.com/microsoft-365/compliance/communication-compliance-feature-reference) связи помогает выявлять следующие типы недопустимого содержимого в каналах Teams или в 1:1 и групповых чатах:</span><span class="sxs-lookup"><span data-stu-id="f93f2-105">For Microsoft Teams, communication compliance helps identify the [following types](https://docs.microsoft.com/microsoft-365/compliance/communication-compliance-feature-reference) of inappropriate content in Teams channels or in 1:1 and group chats:</span></span>

- <span data-ttu-id="f93f2-106">Оскорбительные, оскорбительные и уголовные языки</span><span class="sxs-lookup"><span data-stu-id="f93f2-106">Offensive, profane, and harassing language</span></span>
- <span data-ttu-id="f93f2-107">Изображения взрослого, вояжа и рывка</span><span class="sxs-lookup"><span data-stu-id="f93f2-107">Adult, racy, and gory images</span></span>
- <span data-ttu-id="f93f2-108">Общий доступ к конфиденциальной информации</span><span class="sxs-lookup"><span data-stu-id="f93f2-108">Sharing of sensitive information</span></span>

<span data-ttu-id="f93f2-109">Дополнительные сведения о соответствии требованиям связи и настройке политик для организации см. в microsoft [365.](https://docs.microsoft.com/microsoft-365/compliance/communication-compliance)</span><span class="sxs-lookup"><span data-stu-id="f93f2-109">For more information on communication compliance and how to configure policies for your organization, see [Communication compliance in Microsoft 365](https://docs.microsoft.com/microsoft-365/compliance/communication-compliance).</span></span>

## <a name="how-to-use-communication-compliance-in-microsoft-teams"></a><span data-ttu-id="f93f2-110">Использование соответствия требованиям связи в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="f93f2-110">How to use communication compliance in Microsoft Teams</span></span>

<span data-ttu-id="f93f2-111">Соответствие требованиям и Microsoft Teams тесно интегрированы и помогают свести к минимуму коммуникационные риски в организации.</span><span class="sxs-lookup"><span data-stu-id="f93f2-111">Communication compliance and Microsoft Teams are tightly integrated and can help minimize communication risks in your organization.</span></span> <span data-ttu-id="f93f2-112">После настройки первых политик соответствия требованиям связи вы можете активно управлять нежелательными сообщениями и содержимым Microsoft Teams, автоматически помечающимся в оповещениях.</span><span class="sxs-lookup"><span data-stu-id="f93f2-112">After you've configured your first communication compliance policies, you can actively manage inappropriate Microsoft Teams messages and content that is automatically flagged in alerts.</span></span>

### <a name="getting-started"></a><span data-ttu-id="f93f2-113">Начало работы</span><span class="sxs-lookup"><span data-stu-id="f93f2-113">Getting started</span></span>

<span data-ttu-id="f93f2-114">Начало работы с соблюдением требований [](https://docs.microsoft.com/microsoft-365/compliance/communication-compliance-plan) к информационному обеспечению в Microsoft Teams начинается с планирования и создания предопределяемой или настраиваемой политики для выявления нежелательных действий пользователей в каналах Teams или группах 1:1.</span><span class="sxs-lookup"><span data-stu-id="f93f2-114">Getting started with communication compliance in Microsoft Teams begins with [planning](https://docs.microsoft.com/microsoft-365/compliance/communication-compliance-plan) and creating pre-defined or custom policies to identify inappropriate user activities in Teams channels or in 1:1 and groups.</span></span> <span data-ttu-id="f93f2-115">Имейте в виду, что [](https://docs.microsoft.com/microsoft-365/compliance/communication-compliance-configure) в процессе настройки необходимо настроить некоторые разрешения и основные предварительные условия.</span><span class="sxs-lookup"><span data-stu-id="f93f2-115">Keep in mind that you'll need to [configure](https://docs.microsoft.com/microsoft-365/compliance/communication-compliance-configure) some permissions and basic prerequisites as part of the configuration process.</span></span>

<span data-ttu-id="f93f2-116">Администраторы Teams могут настраивать политики соответствия требованиям для связи на следующих уровнях:</span><span class="sxs-lookup"><span data-stu-id="f93f2-116">Teams administrators can configure communication compliance policies at the following levels:</span></span>

- <span data-ttu-id="f93f2-117">**Уровень пользователя:** политики на этом уровне применяются к отдельному пользователю Teams или могут применяться для всех пользователей Teams в организации.</span><span class="sxs-lookup"><span data-stu-id="f93f2-117">**User level**: Policies at this level apply to an individual Teams user or may be applied to all Teams users in your organization.</span></span> <span data-ttu-id="f93f2-118">Эти политики охватывают сообщения, которые пользователи могут отправлять в 1:1 или в групповых чатах.</span><span class="sxs-lookup"><span data-stu-id="f93f2-118">These policies cover messages that these users may send in 1:1 or group chats.</span></span> <span data-ttu-id="f93f2-119">Общение в чате для пользователей автоматически отслеживается во всех службах Microsoft Teams, участником которых они являются.</span><span class="sxs-lookup"><span data-stu-id="f93f2-119">Chat communications for the users are automatically monitored across all Microsoft Teams where the users are a member.</span></span>
- <span data-ttu-id="f93f2-120">**Уровень Teams:** политики на этом уровне применяются к каналу Microsoft Team.</span><span class="sxs-lookup"><span data-stu-id="f93f2-120">**Teams level**: Policies at this level apply to a Microsoft Team channel.</span></span> <span data-ttu-id="f93f2-121">Эти политики охватывают сообщения, отправленные только в канал Teams.</span><span class="sxs-lookup"><span data-stu-id="f93f2-121">These policies cover messages sent in the Teams channel only.</span></span>

### <a name="act-on-inappropriate-messages-in-microsoft-teams"></a><span data-ttu-id="f93f2-122">Действия с недопустимыми сообщениями в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="f93f2-122">Act on inappropriate messages in Microsoft Teams</span></span>

<span data-ttu-id="f93f2-123">После настройки политик и полученных оповещений о соответствии требованиям к информационному обеспечению для сообщений Microsoft Teams необходимо, чтобы проверятели соответствия требованиям в вашей организации приняли меры для этих сообщений.</span><span class="sxs-lookup"><span data-stu-id="f93f2-123">After you have configured your policies and have received communication compliance alerts for Microsoft Teams messages, it's time for compliance reviewers in your organization to take action on these messages.</span></span> <span data-ttu-id="f93f2-124">Проверяющие помогают защитить организацию, проверяя оповещения о соответствии требованиям и удаляя помеченные сообщения из представления в Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="f93f2-124">Reviewers can help safeguard your organization by reviewing communication compliance alerts and removing flagged messages from view in Microsoft Teams.</span></span>

![Удаление сообщения в Teams](./media/communication-compliance-remove-teams-message.png)

<span data-ttu-id="f93f2-126">Удаляемые сообщения и содержимое заменяются уведомлениями, объясняя, что сообщение или содержимое удалено и какая политика применима к удалению.</span><span class="sxs-lookup"><span data-stu-id="f93f2-126">Removed messages and content are replaced with notifications for viewers explaining that the message or content has been removed and what policy is applicable to the removal.</span></span> <span data-ttu-id="f93f2-127">Отправитель сообщения или содержимого также уведомлен о состоянии удаления и предоставляется исходное содержимое для контекста, связанного с удалением.</span><span class="sxs-lookup"><span data-stu-id="f93f2-127">The sender of the removed message or content is also notified of the removal status and provided with original message content for context relating to its removal.</span></span> <span data-ttu-id="f93f2-128">Отправитель также может просмотреть определенное условие политики, применяемое к удалению сообщений.</span><span class="sxs-lookup"><span data-stu-id="f93f2-128">The sender can also view the specific policy condition that applies to the message removal.</span></span>

<span data-ttu-id="f93f2-129">Пример подсказки политики, виден отправителю:</span><span class="sxs-lookup"><span data-stu-id="f93f2-129">Example of policy tip seen by sender:</span></span>

![Подсказка политики для отправщика](./media/communication-compliance-warning-1.png)

<span data-ttu-id="f93f2-131">Пример уведомления об условии политики, которое видно отправителю:</span><span class="sxs-lookup"><span data-stu-id="f93f2-131">Example of policy condition notification seen by the sender:</span></span>

![Сведения об условиях политики для отправщика](./media/communication-compliance-warning-2.png)

<span data-ttu-id="f93f2-133">Пример подсказки политики, виден получателю:</span><span class="sxs-lookup"><span data-stu-id="f93f2-133">Example of policy tip seen by recipient:</span></span>

![Подсказка политики для получателя](./media/communication-compliance-warning-3.png)
