---
title: Срок действия и продление подписки для группы в Microsoft Teams
author: LanaChin
ms.author: v-lanac
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: abgupta
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
description: Сведения об истечении срока действия и возобновлении работы группы и о том, как использовать политику срока действия групп Microsoft 365 или Microsoft 365 для автоматической очистки неиспользуемых команд в Microsoft Teams.
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.openlocfilehash: 34984c545e3e6593c9d5168a81d3465ce391dab2
ms.sourcegitcommit: 3323c86f31c5ab304944a34892601fcc7b448025
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/09/2020
ms.locfileid: "44638558"
---
# <a name="team-expiration-and-renewal-in-microsoft-teams"></a><span data-ttu-id="a7b76-103">Срок действия и продление подписки для группы в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="a7b76-103">Team expiration and renewal in Microsoft Teams</span></span>

<span data-ttu-id="a7b76-104">Организации с большим количеством групп часто содержат команды, которые никогда не использовались в действительности.</span><span class="sxs-lookup"><span data-stu-id="a7b76-104">Organizations with a large number of teams often have teams that are never actually used.</span></span> <span data-ttu-id="a7b76-105">Это может быть вызвано несколькими причинами, в том числе экспериментом с продуктом, краткосрочной совместной работой в команде или владельцами групп, которые разработали организацию.</span><span class="sxs-lookup"><span data-stu-id="a7b76-105">This can happen because of several reasons including product experimentation, short-term team collaboration, or team owners leaving the organization.</span></span> <span data-ttu-id="a7b76-106">С течением времени такие команды могут накапливать и создавать косвенные ресурсы на ресурсах клиентов.</span><span class="sxs-lookup"><span data-stu-id="a7b76-106">Over time, such teams can accumulate and create a burden on tenant resources.</span></span>  

<span data-ttu-id="a7b76-107">Чтобы намыть количество неиспользуемых команд в качестве администратора, вы можете использовать [политику срока действия групп microsoft 365 или microsoft 365](https://docs.microsoft.com/office365/admin/create-groups/office-365-groups-expiration-policy) для автоматической очистки неиспользуемых групп.</span><span class="sxs-lookup"><span data-stu-id="a7b76-107">To curb the number of unused teams, as an admin, you can use [Microsoft 365 or Microsoft 365 group expiration policy](https://docs.microsoft.com/office365/admin/create-groups/office-365-groups-expiration-policy) to automatically clean up unused teams.</span></span> <span data-ttu-id="a7b76-108">Так как команды группируются по группам, политики срока действия групп автоматически применяются и к группам.</span><span class="sxs-lookup"><span data-stu-id="a7b76-108">Because teams are backed by groups, group expiration policies automatically apply to teams as well.</span></span>

<span data-ttu-id="a7b76-109">Когда вы применяете политику срока действия к группе, владелец группы получает уведомление о продлении подписки на обновления команды в течение 30 дней, 15 дней и 1 дня до окончания срока действия команды.</span><span class="sxs-lookup"><span data-stu-id="a7b76-109">When you apply an expiration policy to a team, a team owner receives a notification for team renewal 30 days, 15 days and 1 day before the team's expiration date.</span></span> <span data-ttu-id="a7b76-110">Когда владелец группы получает уведомление, он может нажать кнопку **Обновить сейчас** в разделе Параметры группы, чтобы продлить команду.</span><span class="sxs-lookup"><span data-stu-id="a7b76-110">When the team owner receives the notification, they can click **Renew now** in team settings to renew the team.</span></span>

<span data-ttu-id="a7b76-111">![Снимок экрана: кнопка "продлите" для возобновления работы группы в параметрах группы](media/team-expiration.png "Снимок экрана: кнопка "продлите" для возобновления работы группы в параметрах группы")</span><span class="sxs-lookup"><span data-stu-id="a7b76-111">![Screenshot of the Renew Now button to renew a team in team settings](media/team-expiration.png "Screenshot of the Renew Now button to renew a team in team settings")</span></span>

<span data-ttu-id="a7b76-112">Если владелец команды не продлит команду, она будет переведена в состояние "soft-deleted" (это значит, что она может быть восстановлена в течение следующих 30 дней).</span><span class="sxs-lookup"><span data-stu-id="a7b76-112">If the team owner doesn't renew the team, the team is put in a "soft-deleted" state, which means it can be restored within the next 30 days.</span></span>

## <a name="team-auto-renewal"></a><span data-ttu-id="a7b76-113">Автоматическое продление группы</span><span class="sxs-lookup"><span data-stu-id="a7b76-113">Team auto-renewal</span></span>

<span data-ttu-id="a7b76-114">Может быть, когда владелец команды не может возобновить команду, возможно, из-за того, что они забыли продлить или не проходили, когда продление было завершено.</span><span class="sxs-lookup"><span data-stu-id="a7b76-114">There can be times when a team owner is unable to renew the team perhaps because they forgot to renew or were away when renewal was due.</span></span> <span data-ttu-id="a7b76-115">В этих сценариях команда, используемая в активном состоянии, может быть удалена из-за политик срока действия, которые применяются к группе.</span><span class="sxs-lookup"><span data-stu-id="a7b76-115">In these scenarios, a team in active use can get deleted because of expiration policies that apply to the team.</span></span>  

<span data-ttu-id="a7b76-116">Чтобы предотвратить случайное удаление, автоматическое продление автоматически включается для группы в политике срока действия групп.</span><span class="sxs-lookup"><span data-stu-id="a7b76-116">To prevent accidental deletion, auto-renewal is automatically enabled for a team in the group expiration policy.</span></span> <span data-ttu-id="a7b76-117">После настройки политики истечения срока действия групп все участники группы, у которых есть по крайней мере один канал, будут автоматически обновлены от любого участника до того момента, когда они не поступать от владельца группы вручную.</span><span class="sxs-lookup"><span data-stu-id="a7b76-117">When the group expiration policy is set up, any team that has at least one channel visit from any team member before its expiration date is automatically renewed without any manual intervention from the team owner.</span></span>

## <a name="known-issues"></a><span data-ttu-id="a7b76-118">Известные проблемы</span><span class="sxs-lookup"><span data-stu-id="a7b76-118">Known issues</span></span>

<span data-ttu-id="a7b76-119">**Дата окончания срока действия группы и базовой группы не совпадают**</span><span class="sxs-lookup"><span data-stu-id="a7b76-119">**Expiration date of team and underlying group don't match**</span></span>

<span data-ttu-id="a7b76-120">Перед тем как команда будет обновлена, сначала будет обновлена группа, в которую входит группа.</span><span class="sxs-lookup"><span data-stu-id="a7b76-120">Before a team is renewed, the group that backs the team is renewed first.</span></span> <span data-ttu-id="a7b76-121">В ходе продления в будущем для группы будет задана новая дата окончания срока действия.</span><span class="sxs-lookup"><span data-stu-id="a7b76-121">As part of renewal, a new expiry date is set on the group for a future date.</span></span> <span data-ttu-id="a7b76-122">Эта новая дата может не отображаться сразу в Teams.</span><span class="sxs-lookup"><span data-stu-id="a7b76-122">This new date may not be immediately visible in Teams.</span></span> <span data-ttu-id="a7b76-123">Синхронизация может занять до 24 часов. Если вы видите расхождение между датой окончания срока действия команды и ее базовой группой, подождите 24 часа, прежде чем получать дополнительные сведения о поддержке.</span><span class="sxs-lookup"><span data-stu-id="a7b76-123">It can take up to 24 hours to sync. If you see a discrepancy between the expiry date for a team and its underlying group, wait 24 hours before seeking further support.</span></span>
