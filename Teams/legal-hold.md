---
title: Помещение пользователя или команды Microsoft Teams на удержание по юридическим причинам
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
ms.reviewer: anach
search.appverid: MET150
description: Сведения о помещении пользователя или команды Microsoft Teams на удержание по юридическим причинам с помощью Центра безопасности и соответствия требованиям, а также о том, что именно требуется удерживать в зависимости от требований к данным.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 25bd8e235be79ed805a854cbda2b4947f1c1269b
ms.sourcegitcommit: 4a22bf77f529cfc2e68a6498a0c4aa9030ee2168
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/05/2019
ms.locfileid: "37968040"
---
<a name="place-a-microsoft-teams-user-or-team-on-legal-hold"></a><span data-ttu-id="4a9b0-103">Помещение пользователя или команды Microsoft Teams на удержание по юридическим причинам</span><span class="sxs-lookup"><span data-stu-id="4a9b0-103">Place a Microsoft Teams user or team on legal hold</span></span>
==================================================

<span data-ttu-id="4a9b0-104">Чтобы поместить пользователя или команду на удержание по юридическим причинам, перейдите в [Центр безопасности и соответствия требованиям](https://go.microsoft.com/fwlink/?linkid=854628).</span><span class="sxs-lookup"><span data-stu-id="4a9b0-104">To put a user or a team on Legal Hold, navigate to the [Security & Compliance Center](https://go.microsoft.com/fwlink/?linkid=854628).</span></span> <span data-ttu-id="4a9b0-105">При создании нового обращения вы можете поместить почтовые ящики или сайты на удержание.</span><span class="sxs-lookup"><span data-stu-id="4a9b0-105">When you create a new case, you are presented with the option to place mailboxes or sites on hold.</span></span>

> [!NOTE]
> <span data-ttu-id="4a9b0-106">Помещение пользователя на удержание не приводит к автоматическому переводу группы в этот режим, и наоборот.</span><span class="sxs-lookup"><span data-stu-id="4a9b0-106">Placing a user on hold does not automatically place a group on hold or vice-versa.</span></span>

> [!NOTE]
> <span data-ttu-id="4a9b0-107">Мы пока не поддерживаем конфигурацию для юридического удержания сообщений личного канала.</span><span class="sxs-lookup"><span data-stu-id="4a9b0-107">We don’t yet support configuration for legal hold of private channel messages.</span></span> <span data-ttu-id="4a9b0-108">Поддерживается юридическое хранение файлов, которые совместно используются в частных каналах.</span><span class="sxs-lookup"><span data-stu-id="4a9b0-108">Legal hold of files shared in private channels is supported.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="4a9b0-109">Если пользователь или группа помещены на удержание, все копии сообщений будут сохраняться.</span><span class="sxs-lookup"><span data-stu-id="4a9b0-109">When a user or group is placed on hold, all message copies will be retained.</span></span> <span data-ttu-id="4a9b0-110">Например, пользователь Clay опубликовал в канале сообщение и затем отредактировал его.</span><span class="sxs-lookup"><span data-stu-id="4a9b0-110">Example: Clay posted a message in a channel and then modified the message.</span></span> <span data-ttu-id="4a9b0-111">Если включено удержание по юридическим причинам, будут сохранены обе версии сообщения.</span><span class="sxs-lookup"><span data-stu-id="4a9b0-111">In a hold scenario, both copies of the message are retained.</span></span> <span data-ttu-id="4a9b0-112">В противном случае сохраняется только последняя версия.</span><span class="sxs-lookup"><span data-stu-id="4a9b0-112">Without Legal Hold, only the latest message is retained.</span></span>

<span data-ttu-id="4a9b0-113">На рисунке ниже приведено расследование, затрагивающее Clay.</span><span class="sxs-lookup"><span data-stu-id="4a9b0-113">In the figure below, there is an investigation involving Clay.</span></span> <span data-ttu-id="4a9b0-114">Clay является участником группы "Brokers-Dealers" (Брокеры-дилеры).</span><span class="sxs-lookup"><span data-stu-id="4a9b0-114">Clay is a member of the Brokers-Dealers team.</span></span>

<span data-ttu-id="4a9b0-115">Если требуется поместить на удержание по юридическим причинам все расположения, где Clay мог обсуждать планы по работе брокеров, обязательно включите в список удержания сайт SharePoint соответствующей команды, а также сайт OneDrive для бизнеса этого пользователя.</span><span class="sxs-lookup"><span data-stu-id="4a9b0-115">If we needed to Legal Hold all the places Clay could have discussed Brokering plans, ensure that the team’s SharePoint site is added to the Legal Hold site list, as well as Clay’s OneDrive for Business site.</span></span>

![Снимок экрана с диалоговом окном "Создание удержания".](media/Place_a_Microsoft_Teams_user_or_team_on_legal_hold_image3.png)

<span data-ttu-id="4a9b0-117">Краткие сведения о том, что именно требуется удерживать в зависимости от требований к данным, приведены в следующей таблице:</span><span class="sxs-lookup"><span data-stu-id="4a9b0-117">To recap, use the table below to understand what needs to be placed on Legal Hold based on data requirements:</span></span>

|<span data-ttu-id="4a9b0-118">Сценарий</span><span class="sxs-lookup"><span data-stu-id="4a9b0-118">Scenario</span></span>  |<span data-ttu-id="4a9b0-119">Что помещается на удержание</span><span class="sxs-lookup"><span data-stu-id="4a9b0-119">What to place on hold</span></span>  |
|---------|---------|
|<span data-ttu-id="4a9b0-120">**Приватные чаты Microsoft Teams**</span><span class="sxs-lookup"><span data-stu-id="4a9b0-120">**Microsoft Teams Private Chats**</span></span>     |<span data-ttu-id="4a9b0-121">Почтовый ящик пользователя</span><span class="sxs-lookup"><span data-stu-id="4a9b0-121">User mailbox</span></span>         |
|<span data-ttu-id="4a9b0-122">**Чаты каналов Microsoft Teams**</span><span class="sxs-lookup"><span data-stu-id="4a9b0-122">**Microsoft Teams Channel Chats**</span></span>    |<span data-ttu-id="4a9b0-123">Используемый командой почтовый ящик группы</span><span class="sxs-lookup"><span data-stu-id="4a9b0-123">Group mailbox used for the team</span></span>         |
|<span data-ttu-id="4a9b0-124">**Контент Microsoft Teams (например, вики-сайты, файлы)**</span><span class="sxs-lookup"><span data-stu-id="4a9b0-124">**Microsoft Teams Content (e.g. Wiki, Files)**</span></span>     |<span data-ttu-id="4a9b0-125">Используемый командой сайт SharePoint</span><span class="sxs-lookup"><span data-stu-id="4a9b0-125">SharePoint site used by the team</span></span>         |
|<span data-ttu-id="4a9b0-126">**Личное содержимое**</span><span class="sxs-lookup"><span data-stu-id="4a9b0-126">**Private Content**</span></span>     |<span data-ttu-id="4a9b0-127">Сайт пользователя в OneDrive для бизнеса</span><span class="sxs-lookup"><span data-stu-id="4a9b0-127">OneDrive for Business site of the user</span></span>         |
