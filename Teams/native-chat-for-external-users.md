---
title: Возможность чата для внешних (федеративных) пользователей в Microsoft Teams
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
- m365initiative-externalcollab
ms.reviewer: vinbel
search.appverid: MET150
f1.keywords:
- NOCSH
description: Узнайте о возможности чата Teams для внешних (федеративов) пользователей в Microsoft Teams, которые доступны между внешними пользователями в режиме обновления TeamsOnly.
ms.openlocfilehash: d3ff414420f8d1d68965307e9303aed4b5cf00ff
ms.sourcegitcommit: 57fddb045f4a9df14cc421b1f6a228df91f334de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/13/2020
ms.locfileid: "49030605"
---
<a name="native-chat-experience-for-external-federated-users-in-microsoft-teams"></a><span data-ttu-id="fdaca-103">Возможность чата для внешних (федеративных) пользователей в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="fdaca-103">Native chat experience for external (federated) users in Microsoft Teams</span></span>
======================================

<span data-ttu-id="fdaca-104">Когда пользователь Microsoft Teams разговаривает с внешним (федератеренным) пользователем, возможности чата ограничены текстом.</span><span class="sxs-lookup"><span data-stu-id="fdaca-104">When a Microsoft Teams user is chatting with an external (federated) user, the chat experience is limited to text.</span></span> <span data-ttu-id="fdaca-105">Однако если как пользователь Teams, так и внешний пользователь находится в режиме обновления TeamsOnly, вы можете использовать "интерфейс чата native-Teams", который включает форматирование, @mentions и другие функции чата.</span><span class="sxs-lookup"><span data-stu-id="fdaca-105">However, if both your Teams user and the external user is in the TeamsOnly upgrade mode, you can have a "native-Teams chat experience," which includes rich formatting, @mentions, and other chat features.</span></span> <span data-ttu-id="fdaca-106">Другими словами, вы можете использовать такой же опыт чата Teams 1:1 с подходящими внешними пользователями, как и с пользователями в организации.</span><span class="sxs-lookup"><span data-stu-id="fdaca-106">In other words, you can have the same rich 1:1 Teams chat experience with eligible external users as you'd have with users in your organization.</span></span> <span data-ttu-id="fdaca-107">Групповые чаты Teams с внешними пользователями по-прежнему ограничены 1:1 (внешние пользователи не могут делать групповые чаты).</span><span class="sxs-lookup"><span data-stu-id="fdaca-107">Native Teams chats with external users are still limited to 1:1 chats only (external users can't do group chats).</span></span>

<span data-ttu-id="fdaca-108">Возможность чата для внешних пользователей включена для всех клиентов Teams, но не у всех пользователей есть права.</span><span class="sxs-lookup"><span data-stu-id="fdaca-108">The native chat experience for external users is turned on for all Teams tenants, but not all users are eligible.</span></span> <span data-ttu-id="fdaca-109">Чтобы получить возможность использовать чат в обычном режиме, необходимо настроить как отправитель, так и приемник для режима обновления TeamsOnly.</span><span class="sxs-lookup"><span data-stu-id="fdaca-109">To be offered a native chat experience, both the sender and receiver need to be configured for TeamsOnly upgrade mode.</span></span> <span data-ttu-id="fdaca-110">Чтобы узнать больше о политиках обновления, ознакомьтесь с настройкой сосуществования и [параметров обновления.](setting-your-coexistence-and-upgrade-settings.md)</span><span class="sxs-lookup"><span data-stu-id="fdaca-110">To learn more about upgrade policies, read [Setting your coexistence and upgrade settings](setting-your-coexistence-and-upgrade-settings.md).</span></span>

<span data-ttu-id="fdaca-111">Список возможностей для пользователей с внешним доступом в Teams см. в средстве сравнения [внешнего и гостевого доступа.](communicate-with-users-from-other-organizations.md#compare-external-and-guest-access)</span><span class="sxs-lookup"><span data-stu-id="fdaca-111">To see a list of capabilities for external access users in Teams, see [Compare external and guest access](communicate-with-users-from-other-organizations.md#compare-external-and-guest-access).</span></span>

## <a name="how-do-i-know-if-im-in-a-native-chat"></a><span data-ttu-id="fdaca-112">Как узнать, что я в чате?</span><span class="sxs-lookup"><span data-stu-id="fdaca-112">How do I know if I'm in a native chat?</span></span>

<span data-ttu-id="fdaca-113">Если вы можете обмениваться только текстом в чате с внешним пользователем, то вы в стандартном (федеративном) чате.</span><span class="sxs-lookup"><span data-stu-id="fdaca-113">If you can only exchange text in your chat with an external user, then you're in a standard external-access (federated) chat.</span></span> <span data-ttu-id="fdaca-114">Если у вас есть все остальные функции чата, включая форматирование, @mentions, эмодзи и т. д., вы в чате Teams со своим внешним пользователем.</span><span class="sxs-lookup"><span data-stu-id="fdaca-114">If you've got all of the other chat functionality, including formatting, @mentions, emojis, etc., then you're in a native Teams chat with your external user.</span></span> 

<span data-ttu-id="fdaca-115">Teams периодически проверяет режим обновления для внешних пользователей и при поиске внешнего пользователя, который работает с Teams, в режиме обновления TeamsOnly, вам будет предложено переключиться в чат Teams и заблокировать исходный чат.</span><span class="sxs-lookup"><span data-stu-id="fdaca-115">Teams periodically checks the upgrade mode for external users and, when it finds an external user running Teams in the TeamsOnly upgrade mode, it'll prompt you to switch to a native Teams chat and lock the original chat.</span></span>

<span data-ttu-id="fdaca-116">При переключении в чат Teams, Teams не объединяет две беседы.</span><span class="sxs-lookup"><span data-stu-id="fdaca-116">When you switch to a native Teams chat, Teams doesn't merge the two conversations.</span></span> <span data-ttu-id="fdaca-117">Вместо этого вы увидите оба чата в своем веб-канале чата.</span><span class="sxs-lookup"><span data-stu-id="fdaca-117">Instead, you'll see both of the chats in your chat feed.</span></span> <span data-ttu-id="fdaca-118">Новый чат Teams активен, но старый текстовый чат заблокирован.</span><span class="sxs-lookup"><span data-stu-id="fdaca-118">The new, native-Teams chat is active, but the old, text-only chat is locked.</span></span>



## <a name="what-happens-if-a-user-isnt-in-teams-only-mode-anymore"></a><span data-ttu-id="fdaca-119">Что произойдет, если пользователь больше не работает в режиме "Только Teams"?</span><span class="sxs-lookup"><span data-stu-id="fdaca-119">What happens if a user isn't in Teams Only mode anymore?</span></span>

<span data-ttu-id="fdaca-120">Если у вас был чат Teams с внешним пользователем, а затем один из вас выходит из режима обновления TeamsOnly, Teams блокирует чат Teams и предоставляет ссылку на ограниченный текстовый чат.</span><span class="sxs-lookup"><span data-stu-id="fdaca-120">If you were having a native Teams chat with an external user and then one of you gets switched out of the TeamsOnly upgrade mode, Teams locks the native Teams chat and gives you a link for a limited, text-only chat.</span></span> <span data-ttu-id="fdaca-121">Вы не сможете продолжить в чате Teams.</span><span class="sxs-lookup"><span data-stu-id="fdaca-121">You won't be able to continue in the native Teams chat.</span></span> <span data-ttu-id="fdaca-122">Вы по-прежнему сможете читать чат Teams, но не сможете продолжить беседу в этом чате.</span><span class="sxs-lookup"><span data-stu-id="fdaca-122">You can still read the native Teams chat, but you can't continue the conversation there.</span></span>

<span data-ttu-id="fdaca-123">Если Teams обнаружит старый текстовый чат с этим внешним пользователем, он будет работать в нем.</span><span class="sxs-lookup"><span data-stu-id="fdaca-123">If Teams finds an old text-only chat with this external user, it'll revive that chat.</span></span> <span data-ttu-id="fdaca-124">В противном случае Teams создаст новый текстовый чат.</span><span class="sxs-lookup"><span data-stu-id="fdaca-124">Otherwise, Teams creates a new text-only chat.</span></span>


## <a name="related-topics"></a><span data-ttu-id="fdaca-125">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="fdaca-125">Related topics</span></span>

[<span data-ttu-id="fdaca-126">Управление внешним доступом в Teams</span><span class="sxs-lookup"><span data-stu-id="fdaca-126">Manage external access in Teams</span></span>](manage-external-access.md)
