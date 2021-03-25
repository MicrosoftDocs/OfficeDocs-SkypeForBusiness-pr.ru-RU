---
title: Планирование использования групп Microsoft 365 при создании команд
ms.reviewer: ''
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.date: 08/29/2018
ms.topic: conceptual
ms.service: msteams
audience: admin
description: Узнайте, как планировать группы Microsoft 365 в Teams, в том числе о различиях между группами & беседах Teams и о том, как Teams соблюдает политику именования групп.
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- m365initiative-deployteams
appliesto:
- Microsoft Teams
ms.custom:
- seo-marvel-mar2020
ms.openlocfilehash: 1acde038bc2df64d7cf35828bf0b08273bf1f095
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51108355"
---
<a name="plan-for-microsoft-365-groups-when-creating-teams-in-microsoft-teams"></a><span data-ttu-id="56d8c-103">Планирование групп Microsoft 365 при создании команд в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="56d8c-103">Plan for Microsoft 365 Groups when creating teams in Microsoft Teams</span></span>
==========================================================

<span data-ttu-id="56d8c-104">Принимая во внимание использование групп Microsoft 365 или создавая команды, подумайте, для чего будет использоваться команда, кто должен иметь доступ и какие результаты она ожидать.</span><span class="sxs-lookup"><span data-stu-id="56d8c-104">When considering the use of Microsoft 365 Groups or when creating teams, consider what the team will be used for, who should have access, and what outcome the team will expect to achieve.</span></span> <span data-ttu-id="56d8c-105">Особое внимание уделите числу создаваемых каналов, так как слишком сильное дробление контента (то есть разнесение его по большому числу каналов) быстро утомляет людей.</span><span class="sxs-lookup"><span data-stu-id="56d8c-105">Pay special attention to the number of channels you create as people can quickly become overrun by content spread too thin (across too many channels).</span></span>

<span data-ttu-id="56d8c-106">Существует два сценария, в которые можно обсудить планирование групп Microsoft 365 и их влияние на Microsoft Teams (или на него).</span><span class="sxs-lookup"><span data-stu-id="56d8c-106">There are two scenarios that warrant some discussion around planning of Microsoft 365 Groups and their impact on (or by) Microsoft Teams:</span></span>

-   <span data-ttu-id="56d8c-107">Во-первых, поскольку у клиентов могут быть инвестиции в Группы, в настоящее время мы поддерживаем как общедоступные, так и закрытые группы. Количество поддерживаемых в настоящее время участников см. в спецификациях и ограничениях [для Microsoft Teams.](./limits-specifications-teams.md)</span><span class="sxs-lookup"><span data-stu-id="56d8c-107">First, since customers could have existing investments in Groups, we currently support both Public and Private groups, for the number of members currently supported, please see [Limits and specifications for Microsoft Teams](./limits-specifications-teams.md).</span></span> <span data-ttu-id="56d8c-108">Как упоминалось выше, вам нужно управлять членством людей в команде с помощью клиента Teams, а не Центра администрирования Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="56d8c-108">As mentioned previously, you want to manage the membership of people to a team using the Teams client rather than the Microsoft 365 admin center.</span></span> <span data-ttu-id="56d8c-109">В данном случае, если люди привыкли к цепочкам бесед в Группах Microsoft 365, имеет смысл заметить, что беседа "Группы" по сути является электронной почтой, а не сообщением чата в канале Teams.</span><span class="sxs-lookup"><span data-stu-id="56d8c-109">Given this scenario, if people are used to threaded conversations in Microsoft 365 Groups, it is worthwhile noting that a Groups conversation is essentially email and not the same as a chat message in a Teams channel.</span></span> <span data-ttu-id="56d8c-110">Сообщите людям об этом различии и порекомендуйте освоить более гибкий формат сообщений чата в Teams вместо электронной почты на базе Outlook или OWA.</span><span class="sxs-lookup"><span data-stu-id="56d8c-110">Educate your people about this difference and suggest they adopt the more flexible chat message format in Teams versus emailing the Group using Outlook or OWA.</span></span>

-   <span data-ttu-id="56d8c-111">Во-вторых, для клиентов, у которых нет существующих групп, определенных в Microsoft 365, вы можете создать их с помощью Центра администрирования Microsoft 365, веб-приложения Teams или классических клиентов.</span><span class="sxs-lookup"><span data-stu-id="56d8c-111">Second, for customers who don't have existing Groups defined in Microsoft 365, you can either create them using the Microsoft 365 admin center, the Teams web, or desktop clients.</span></span> <span data-ttu-id="56d8c-112">Как упоминалось выше, управлять всеми будущими членством в группе Microsoft 365 с помощью клиента Teams.</span><span class="sxs-lookup"><span data-stu-id="56d8c-112">As mentioned previously, manage all future membership to the Microsoft 365 group using the Teams client.</span></span> <span data-ttu-id="56d8c-113">Так как членство в группе также определяет членство в Группах Microsoft 365, следует подготовить пользователей к этому изменению.</span><span class="sxs-lookup"><span data-stu-id="56d8c-113">Since membership to a team is also defining membership to Microsoft 365 Groups, you should prepare people for this change.</span></span>

## <a name="teams-respects-microsoft-365-groups-naming-policy-in-private-preview"></a><span data-ttu-id="56d8c-114">Teams соблюдает политику именования групп Microsoft 365 (в режиме личной предварительной версии)</span><span class="sxs-lookup"><span data-stu-id="56d8c-114">Teams respects Microsoft 365 Groups naming policy (in private preview)</span></span>

<span data-ttu-id="56d8c-115">Любая политика именования групп Microsoft 365, настроенная администратором, применяется в Teams при создании или редактировании имен групп пользователями.</span><span class="sxs-lookup"><span data-stu-id="56d8c-115">Any Microsoft 365 Groups naming policy that has been set by your admin will be applied in Teams when users create or edit team names.</span></span> <span data-ttu-id="56d8c-116">Сюда входят такие аспекты, как обязательные префиксы или суффиксы, а также исключение запрещенных слов.</span><span class="sxs-lookup"><span data-stu-id="56d8c-116">This includes things like mandatory prefixes or suffixes and excluding banned words.</span></span>

> [!NOTE]
> <span data-ttu-id="56d8c-117">Эта функция находится в режиме личной предварительной версии, то есть, если вы не входите в эту предварительную версию, Teams пока не соблюдает эту политику именования Групп Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="56d8c-117">This feature is in private preview, which means that if you're not part of this preview, Teams doesn't yet adhere to this Microsoft 365 Groups naming policy.</span></span>

<span data-ttu-id="56d8c-118">Чтобы узнать больше, ознакомьтесь с политикой именования [групп Microsoft 365 в Teams.](https://support.office.com/article/Office-365-Groups-Naming-Policy-6ceca4d3-cad1-4532-9f0f-d469dfbbb552)</span><span class="sxs-lookup"><span data-stu-id="56d8c-118">To learn more, read [Microsoft 365 Groups naming policy in Teams](https://support.office.com/article/Office-365-Groups-Naming-Policy-6ceca4d3-cad1-4532-9f0f-d469dfbbb552).</span></span>

<span data-ttu-id="56d8c-119">В следующих статьях вы найдете материалы о готовности и внедрении для групп Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="56d8c-119">The following articles are a good place to find readiness and adoption content for your Microsoft 365 Groups:</span></span>

-   [<span data-ttu-id="56d8c-120">Дополнительные возможности работы с группами в Outlook</span><span class="sxs-lookup"><span data-stu-id="56d8c-120">Get more with groups in Outlook</span></span>](https://support.office.com/article/Get-more-with-Office-365-Groups-in-Outlook-93132800-5b11-49de-8cc2-605b6075b2b9)

-   [<span data-ttu-id="56d8c-121">Добавление и удаление участников групп Microsoft 365 с помощью Центра администрирования Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="56d8c-121">Add or remove members from Microsoft 365 Groups using the Microsoft 365 admin center</span></span>](https://support.office.com/article/Manage-Group-membership-in-the-Office-365-admin-center-e186d224-a324-4afa-8300-0e4fc0c3000a)

-   [<span data-ttu-id="56d8c-122">Восстановление удаленной группы</span><span class="sxs-lookup"><span data-stu-id="56d8c-122">Restore a deleted group</span></span>](/microsoft-365/admin/create-groups/restore-deleted-group)