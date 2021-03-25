---
title: Срок действия и продление подписки команды в Microsoft Teams
author: cichur
ms.author: v-cichur
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: abgupta
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
description: Узнайте об истечении и продлении команды, а также о том, как использовать политику срока действия групп Microsoft 365 для автоматического очистки неиспользимных команд в Microsoft Teams.
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.openlocfilehash: 606d957b703725d631beec38237f4d9b4272433e
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51116957"
---
# <a name="team-expiration-and-renewal-in-microsoft-teams"></a><span data-ttu-id="0d321-103">Срок действия и продление подписки команды в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="0d321-103">Team expiration and renewal in Microsoft Teams</span></span>

<span data-ttu-id="0d321-104">В организациях с большим количеством команд часто есть команды, которые никогда не используются на самом деле.</span><span class="sxs-lookup"><span data-stu-id="0d321-104">Organizations with a large number of teams often have teams that are never actually used.</span></span> <span data-ttu-id="0d321-105">Это может произойти по нескольким причинам, включая эксперименты с продуктами, краткое сотрудничество в команде или уход владельцев команд из организации.</span><span class="sxs-lookup"><span data-stu-id="0d321-105">This can happen because of several reasons including product experimentation, short-term team collaboration, or team owners leaving the organization.</span></span> <span data-ttu-id="0d321-106">Со временем такие группы могут накапливать и создавать трудности на ресурсах клиента.</span><span class="sxs-lookup"><span data-stu-id="0d321-106">Over time, such teams can accumulate and create a burden on tenant resources.</span></span>  

<span data-ttu-id="0d321-107">Чтобы сузить порядок в количестве неиспользимных команд, администратор может использовать политику срока действия групп [Microsoft 365](/microsoft-365/admin/create-groups/office-365-groups-expiration-policy) для автоматической очистки неиспользимных команд.</span><span class="sxs-lookup"><span data-stu-id="0d321-107">To curb the number of unused teams, as an admin, you can use [Microsoft 365 group expiration policy](/microsoft-365/admin/create-groups/office-365-groups-expiration-policy) to automatically clean up unused teams.</span></span> <span data-ttu-id="0d321-108">Так как в командах есть группы, политики срока действия групп также автоматически применяются и к группам.</span><span class="sxs-lookup"><span data-stu-id="0d321-108">Because teams are backed by groups, group expiration policies automatically apply to teams as well.</span></span>

<span data-ttu-id="0d321-109">При применении политики истечения срока действия к команде владелец команды получает уведомление о продлении команды за 30, 15 и 1 день до истечения срока ее действия.</span><span class="sxs-lookup"><span data-stu-id="0d321-109">When you apply an expiration policy to a team, a team owner receives a notification for team renewal 30 days, 15 days and 1 day before the team's expiration date.</span></span> <span data-ttu-id="0d321-110">Когда владелец команды получит уведомление, он может нажать кнопку "Продлить **сейчас"** в параметрах команды, чтобы продлить ее.</span><span class="sxs-lookup"><span data-stu-id="0d321-110">When the team owner receives the notification, they can click **Renew now** in team settings to renew the team.</span></span>

<span data-ttu-id="0d321-111">![Снимок экрана: кнопка "Продлить сейчас", которая обновляет команду в параметрах команды](media/team-expiration.png "Снимок экрана: кнопка "Продлить сейчас", которая обновляет команду в параметрах команды")</span><span class="sxs-lookup"><span data-stu-id="0d321-111">![Screenshot of the Renew Now button to renew a team in team settings](media/team-expiration.png "Screenshot of the Renew Now button to renew a team in team settings")</span></span>

<span data-ttu-id="0d321-112">Если владелец команды не продлевает ее и никаких дополнительных действий с ней не будет вплоть до окончания срока действия политики, то команда будет переналожена в состояние "Неявное удаление", т. е. его можно будет восстановить в течение 30 дней.</span><span class="sxs-lookup"><span data-stu-id="0d321-112">If the team owner doesn't renew the team and there is no further activity on the team until the end of the expiration policy, the team is put in a "soft-deleted" state, which means it can be restored within the next 30 days.</span></span>

## <a name="team-auto-renewal"></a><span data-ttu-id="0d321-113">Автоматическое продление подписки команды</span><span class="sxs-lookup"><span data-stu-id="0d321-113">Team auto-renewal</span></span>

<span data-ttu-id="0d321-114">Иногда владелец команды не может продлить ее, например из-за того, что забыл продлить подписку или не смог ее продлить.</span><span class="sxs-lookup"><span data-stu-id="0d321-114">There can be times when a team owner is unable to renew the team perhaps because they forgot to renew or were away when renewal was due.</span></span> <span data-ttu-id="0d321-115">В таких случаях активное использование группы может быть удалено из-за политик срока действия, которые применяются к группе.</span><span class="sxs-lookup"><span data-stu-id="0d321-115">In these scenarios, a team in active use can get deleted because of expiration policies that apply to the team.</span></span>  

<span data-ttu-id="0d321-116">Чтобы предотвратить случайное удаление, автоматическое продление автоматически включено для группы в политике срока действия группы.</span><span class="sxs-lookup"><span data-stu-id="0d321-116">To prevent accidental deletion, auto-renewal is automatically enabled for a team in the group expiration policy.</span></span> <span data-ttu-id="0d321-117">После того как будет настроена политика истечения срока действия группы, любая команда, посетив по крайней мере один канал у любого участника команды до истечения срока ее действия, автоматически продлевается без вмешательства владельца команды вручную.</span><span class="sxs-lookup"><span data-stu-id="0d321-117">When the group expiration policy is set up, any team that has at least one channel visit from any team member before its expiration date is automatically renewed without any manual intervention from the team owner.</span></span>

## <a name="known-issues"></a><span data-ttu-id="0d321-118">Известные проблемы</span><span class="sxs-lookup"><span data-stu-id="0d321-118">Known issues</span></span>

<span data-ttu-id="0d321-119">**Дата окончания срока действия группы и ее группы не совпадают**</span><span class="sxs-lookup"><span data-stu-id="0d321-119">**Expiration date of team and underlying group don't match**</span></span>

<span data-ttu-id="0d321-120">До продления команды группа, которая будет ее обновлять, сначала продлевается.</span><span class="sxs-lookup"><span data-stu-id="0d321-120">Before a team is renewed, the group that backs the team is renewed first.</span></span> <span data-ttu-id="0d321-121">При продлении для группы устанавливается новая дата окончания срока действия.</span><span class="sxs-lookup"><span data-stu-id="0d321-121">As part of renewal, a new expiry date is set on the group for a future date.</span></span> <span data-ttu-id="0d321-122">Эта новая дата может не быть сразу видна в Teams.</span><span class="sxs-lookup"><span data-stu-id="0d321-122">This new date may not be immediately visible in Teams.</span></span> <span data-ttu-id="0d321-123">Синхронизация может занять до 24 часов. Если вы видите разницу между датой истечения срока действия для группы и ее группой, подождите 24 часа, прежде чем обращаться за дополнительной поддержкой.</span><span class="sxs-lookup"><span data-stu-id="0d321-123">It can take up to 24 hours to sync. If you see a discrepancy between the expiry date for a team and its underlying group, wait 24 hours before seeking further support.</span></span>