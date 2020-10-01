---
title: Соответствие требованиям к общению с Microsoft Teams
author: robmazz
ms.author: robmazz
manager: laurawi
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: anwara
description: Сведения о требованиях к общению, части набора решений для участников программы предварительной оценки с точки зрения Microsoft Teams (это часть функции соответствия требованиям для связи M365).
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
# <a name="communication-compliance-with-microsoft-teams"></a><span data-ttu-id="1caa8-103">Соответствие требованиям к общению с Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="1caa8-103">Communication compliance with Microsoft Teams</span></span>

<span data-ttu-id="1caa8-104">Соответствие требованиям к связи — это решение в Microsoft 365, позволяющее свести к минимуму риски в общении, помогая определять, фиксировать и исполнить нежелательные сообщения в Организации.</span><span class="sxs-lookup"><span data-stu-id="1caa8-104">Communication compliance is an insider risk solution in Microsoft 365 that helps minimize communication risks by helping you detect, capture, and act on inappropriate messages in your organization.</span></span>

<span data-ttu-id="1caa8-105">В Microsoft Teams соответствие требованиям помогает идентифицировать [следующие типы](https://docs.microsoft.com/microsoft-365/compliance/communication-compliance-feature-reference) неуместного содержимого в каналах Teams, а также в 1:1 и групповых чатах.</span><span class="sxs-lookup"><span data-stu-id="1caa8-105">For Microsoft Teams, communication compliance helps identify the [following types](https://docs.microsoft.com/microsoft-365/compliance/communication-compliance-feature-reference) of inappropriate content in Teams channels or in 1:1 and group chats:</span></span>

- <span data-ttu-id="1caa8-106">Оскорбительный, нецензурный и преследованиющий язык</span><span class="sxs-lookup"><span data-stu-id="1caa8-106">Offensive, profane, and harassing language</span></span>
- <span data-ttu-id="1caa8-107">Для взрослых, racyов и goryных изображений</span><span class="sxs-lookup"><span data-stu-id="1caa8-107">Adult, racy, and gory images</span></span>
- <span data-ttu-id="1caa8-108">Совместное использование конфиденциальной информации</span><span class="sxs-lookup"><span data-stu-id="1caa8-108">Sharing of sensitive information</span></span>

<span data-ttu-id="1caa8-109">Дополнительные сведения о требованиях к общению и настройке политик для организации можно найти [в разделе соответствие требованиям в Microsoft 365](https://docs.microsoft.com/microsoft-365/compliance/communication-compliance).</span><span class="sxs-lookup"><span data-stu-id="1caa8-109">For more information on communication compliance and how to configure policies for your organization, see [Communication compliance in Microsoft 365](https://docs.microsoft.com/microsoft-365/compliance/communication-compliance).</span></span>

## <a name="how-to-use-communication-compliance-in-microsoft-teams"></a><span data-ttu-id="1caa8-110">Использование соответствия связью в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="1caa8-110">How to use communication compliance in Microsoft Teams</span></span>

<span data-ttu-id="1caa8-111">Соответствие требованиям к общению и Microsoft Teams тесно интегрировано и может помочь минимизировать риски связи в Организации.</span><span class="sxs-lookup"><span data-stu-id="1caa8-111">Communication compliance and Microsoft Teams are tightly integrated and can help minimize communication risks in your organization.</span></span> <span data-ttu-id="1caa8-112">После настройки первой политики соответствия требованиям вы можете активно управлять неуместными сообщениями Microsoft Teams и содержимым, которое автоматически помечается в оповещениях.</span><span class="sxs-lookup"><span data-stu-id="1caa8-112">After you've configured your first communication compliance policies, you can actively manage inappropriate Microsoft Teams messages and content that is automatically flagged in alerts.</span></span>

### <a name="getting-started"></a><span data-ttu-id="1caa8-113">Начало работы</span><span class="sxs-lookup"><span data-stu-id="1caa8-113">Getting started</span></span>

<span data-ttu-id="1caa8-114">Приступая к работе с обеспечением соответствия требованиям в Microsoft Teams, вы начнете [планировать](https://docs.microsoft.com/microsoft-365/compliance/communication-compliance-plan) и создавать предопределенные или пользовательские политики для выявления нежелательных действий пользователей в каналах Teams, а также в 1:1 и группах.</span><span class="sxs-lookup"><span data-stu-id="1caa8-114">Getting started with communication compliance in Microsoft Teams begins with [planning](https://docs.microsoft.com/microsoft-365/compliance/communication-compliance-plan) and creating pre-defined or custom policies to identify inappropriate user activities in Teams channels or in 1:1 and groups.</span></span> <span data-ttu-id="1caa8-115">Имейте в виду, что в процессе настройки вам потребуется [настроить](https://docs.microsoft.com/microsoft-365/compliance/communication-compliance-configure) некоторые разрешения и базовые компоненты.</span><span class="sxs-lookup"><span data-stu-id="1caa8-115">Keep in mind that you'll need to [configure](https://docs.microsoft.com/microsoft-365/compliance/communication-compliance-configure) some permissions and basic prerequisites as part of the configuration process.</span></span>

<span data-ttu-id="1caa8-116">Администраторы Teams могут настроить политики соответствия требованиям к связи на следующих уровнях:</span><span class="sxs-lookup"><span data-stu-id="1caa8-116">Teams administrators can configure communication compliance policies at the following levels:</span></span>

- <span data-ttu-id="1caa8-117">**Пользовательский уровень**: политики на этом уровне применяются к отдельным пользователям Teams или могут быть применены для всех пользователей Teams в Организации.</span><span class="sxs-lookup"><span data-stu-id="1caa8-117">**User level**: Policies at this level apply to an individual Teams user or may be applied to all Teams users in your organization.</span></span> <span data-ttu-id="1caa8-118">Эти политики охватывают сообщения, которые могут отправлять пользователи в 1:1 или групповых чатах.</span><span class="sxs-lookup"><span data-stu-id="1caa8-118">These policies cover messages that these users may send in 1:1 or group chats.</span></span> <span data-ttu-id="1caa8-119">Обмен сообщениями в чате для пользователей автоматически контролируется во всех Microsoft Teams, в которых пользователи являются участниками.</span><span class="sxs-lookup"><span data-stu-id="1caa8-119">Chat communications for the users are automatically monitored across all Microsoft Teams where the users are a member.</span></span>
- <span data-ttu-id="1caa8-120">**Уровень Teams**: политики на этом уровне применяются к каналу команды Microsoft.</span><span class="sxs-lookup"><span data-stu-id="1caa8-120">**Teams level**: Policies at this level apply to a Microsoft Team channel.</span></span> <span data-ttu-id="1caa8-121">Эти политики охватывают сообщения, отправляемые только в канале Teams.</span><span class="sxs-lookup"><span data-stu-id="1caa8-121">These policies cover messages sent in the Teams channel only.</span></span>

### <a name="act-on-inappropriate-messages-in-microsoft-teams"></a><span data-ttu-id="1caa8-122">Работа с недопустимыми сообщениями в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="1caa8-122">Act on inappropriate messages in Microsoft Teams</span></span>

<span data-ttu-id="1caa8-123">После того как вы настроили политики и получили уведомления о соответствии требованиям в сообщениях Microsoft Teams, вы можете сделать так, чтобы проверяющие на соответствие в вашей организации предприняли необходимые меры для этих сообщений.</span><span class="sxs-lookup"><span data-stu-id="1caa8-123">After you have configured your policies and have received communication compliance alerts for Microsoft Teams messages, it's time for compliance reviewers in your organization to take action on these messages.</span></span> <span data-ttu-id="1caa8-124">С помощью рецензентов можно защитить вашу организацию, изменив уведомления о соответствии на связи и удалив помеченные сообщения в Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="1caa8-124">Reviewers can help safeguard your organization by reviewing communication compliance alerts and removing flagged messages from view in Microsoft Teams.</span></span>

![Удаление сообщения в Teams](./media/communication-compliance-remove-teams-message.png)

<span data-ttu-id="1caa8-126">Удаленные сообщения и содержимое заменяются уведомлениями для посетителей о том, что сообщение или содержимое было удалено и какая политика применяется к удалению.</span><span class="sxs-lookup"><span data-stu-id="1caa8-126">Removed messages and content are replaced with notifications for viewers explaining that the message or content has been removed and what policy is applicable to the removal.</span></span> <span data-ttu-id="1caa8-127">Отправитель удаляемого сообщения или содержимого также уведомлен о состоянии удаления и содержит исходное содержимое сообщения для контекста, связанного с его удалением.</span><span class="sxs-lookup"><span data-stu-id="1caa8-127">The sender of the removed message or content is also notified of the removal status and provided with original message content for context relating to its removal.</span></span> <span data-ttu-id="1caa8-128">Отправитель также может просмотреть определенные условия политики, которые применяются к удалению сообщения.</span><span class="sxs-lookup"><span data-stu-id="1caa8-128">The sender can also view the specific policy condition that applies to the message removal.</span></span>

<span data-ttu-id="1caa8-129">Пример подсказки политики для отправителя:</span><span class="sxs-lookup"><span data-stu-id="1caa8-129">Example of policy tip seen by sender:</span></span>

![Подсказка политики для отправителя](./media/communication-compliance-warning-1.png)

<span data-ttu-id="1caa8-131">Пример уведомления о состоянии политики, отображаемого отправителем:</span><span class="sxs-lookup"><span data-stu-id="1caa8-131">Example of policy condition notification seen by the sender:</span></span>

![Сведения о условии политики для отправителя](./media/communication-compliance-warning-2.png)

<span data-ttu-id="1caa8-133">Пример подсказки политики, которую появлял получатель:</span><span class="sxs-lookup"><span data-stu-id="1caa8-133">Example of policy tip seen by recipient:</span></span>

![Подсказка политики для получателя](./media/communication-compliance-warning-3.png)
