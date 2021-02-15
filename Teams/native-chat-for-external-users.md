---
title: Возможность чата для внешних (федеративных) пользователей в Microsoft Teams
ms.author: mikeplum
author: MikePlumleyMSFT
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
description: Узнайте о чате Teams для внешних пользователей (федеративов) в Microsoft Teams, где оба пользователя находятся в режиме обновления TeamsOnly.
ms.openlocfilehash: df9e1e41992e105937deacf898833995cdfb7714
ms.sourcegitcommit: 2639da2c9f903a9a82866be9db2b69a705c54200
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/29/2021
ms.locfileid: "50055661"
---
# <a name="native-chat-experience-for-external-federated-users-in-microsoft-teams"></a><span data-ttu-id="f44b5-103">Возможность чата для внешних (федеративных) пользователей в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="f44b5-103">Native chat experience for external (federated) users in Microsoft Teams</span></span>

<span data-ttu-id="f44b5-104">Когда пользователь Microsoft Teams разговаривает с внешним (федератеренным) пользователем, возможности чата ограничены текстом.</span><span class="sxs-lookup"><span data-stu-id="f44b5-104">When a Microsoft Teams user is chatting with an external (federated) user, the chat experience is limited to text.</span></span> <span data-ttu-id="f44b5-105">Однако если как пользователь Teams, так и пользователь из другой организации работают в режиме обновления TeamsOnly, вы можете использовать интерфейс чата Native-Teams, который включает в себя форматирование, @mentions и другие функции чата.</span><span class="sxs-lookup"><span data-stu-id="f44b5-105">However, if both your Teams user and the person in another organization is in the TeamsOnly upgrade mode, you can have a "native-Teams chat experience," which includes rich formatting, @mentions, and other chat features.</span></span> <span data-ttu-id="f44b5-106">Другими словами, вы можете использовать такой же опыт чата Teams 1:1 с подходящими пользователями в других организациях, что и с пользователями в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="f44b5-106">In other words, you can have the same rich 1:1 Teams chat experience with eligible people in other organizations as you'd have with users in your organization.</span></span> <span data-ttu-id="f44b5-107">Чаты в Языке Teams с людьми из других организаций ограничены только чатами 1:1.</span><span class="sxs-lookup"><span data-stu-id="f44b5-107">Native Teams chats with people in other organizations are limited to 1:1 chats only.</span></span>

<span data-ttu-id="f44b5-108">Для пользователей из других организаций включена родной чат для всех клиентов Teams, но не у всех пользователей есть права.</span><span class="sxs-lookup"><span data-stu-id="f44b5-108">The native chat experience for people in other organizations is turned on for all Teams tenants, but not all people are eligible.</span></span> <span data-ttu-id="f44b5-109">Чтобы получить возможность использовать чат в обычном режиме, необходимо настроить как отправитель, так и приемник для режима обновления TeamsOnly.</span><span class="sxs-lookup"><span data-stu-id="f44b5-109">To be offered a native chat experience, both the sender and receiver need to be configured for TeamsOnly upgrade mode.</span></span> <span data-ttu-id="f44b5-110">Чтобы узнать больше о политиках обновления, ознакомьтесь с настройкой сосуществования и [параметров обновления.](setting-your-coexistence-and-upgrade-settings.md)</span><span class="sxs-lookup"><span data-stu-id="f44b5-110">To learn more about upgrade policies, read [Setting your coexistence and upgrade settings](setting-your-coexistence-and-upgrade-settings.md).</span></span>

<span data-ttu-id="f44b5-111">Список возможностей для пользователей с внешним доступом в Teams см. в средстве сравнения [внешнего и гостевого доступа.](communicate-with-users-from-other-organizations.md#compare-external-and-guest-access)</span><span class="sxs-lookup"><span data-stu-id="f44b5-111">To see a list of capabilities for external access users in Teams, see [Compare external and guest access](communicate-with-users-from-other-organizations.md#compare-external-and-guest-access).</span></span>

## <a name="how-do-i-know-if-im-in-a-native-chat"></a><span data-ttu-id="f44b5-112">Как узнать, что я в чате?</span><span class="sxs-lookup"><span data-stu-id="f44b5-112">How do I know if I'm in a native chat?</span></span>

<span data-ttu-id="f44b5-113">Если вы можете обмениваться текстом в чате только с людьми из других организаций, то вы в стандартном (федеративном) чате с внешним доступом.</span><span class="sxs-lookup"><span data-stu-id="f44b5-113">If you can only exchange text in your chat with people in other organizations, then you're in a standard external-access (federated) chat.</span></span> <span data-ttu-id="f44b5-114">Если у вас есть все остальные функции чата, включая форматирование, @mentions, эмодзи и т. д., вы уже в чате Teams.</span><span class="sxs-lookup"><span data-stu-id="f44b5-114">If you've got all of the other chat functionality, including formatting, @mentions, emojis, etc., then you're in a native Teams chat.</span></span> 

<span data-ttu-id="f44b5-115">Teams периодически проверяет режим обновления для людей из других организаций и при поиске команды, запускаемой в режиме обновления TeamsOnly, вам будет предложено переключиться в чат Teams и заблокировать исходный чат.</span><span class="sxs-lookup"><span data-stu-id="f44b5-115">Teams periodically checks the upgrade mode for people in other organizations and, when it finds an them running Teams in the TeamsOnly upgrade mode, it'll prompt you to switch to a native Teams chat and lock the original chat.</span></span>

<span data-ttu-id="f44b5-116">При переключении в чат Teams, Teams не объединяет две беседы.</span><span class="sxs-lookup"><span data-stu-id="f44b5-116">When you switch to a native Teams chat, Teams doesn't merge the two conversations.</span></span> <span data-ttu-id="f44b5-117">Вместо этого вы увидите оба чата в своем веб-канале чата.</span><span class="sxs-lookup"><span data-stu-id="f44b5-117">Instead, you'll see both of the chats in your chat feed.</span></span> <span data-ttu-id="f44b5-118">Новый чат Teams активен, но старый текстовый чат заблокирован.</span><span class="sxs-lookup"><span data-stu-id="f44b5-118">The new, native-Teams chat is active, but the old, text-only chat is locked.</span></span>



## <a name="what-happens-if-a-user-isnt-in-teams-only-mode-anymore"></a><span data-ttu-id="f44b5-119">Что произойдет, если пользователь больше не работает в режиме "Только Teams"?</span><span class="sxs-lookup"><span data-stu-id="f44b5-119">What happens if a user isn't in Teams Only mode anymore?</span></span>

<span data-ttu-id="f44b5-120">Если у вас был чат Teams с людьми из других организаций, а затем один из вас выходит из режима обновления TeamsOnly, Teams блокирует чат Teams и предоставляет ссылку на ограниченный текстовый чат.</span><span class="sxs-lookup"><span data-stu-id="f44b5-120">If you were having a native Teams chat with people in other organizations and then one of you gets switched out of the TeamsOnly upgrade mode, Teams locks the native Teams chat and gives you a link for a limited, text-only chat.</span></span> <span data-ttu-id="f44b5-121">Вы не сможете продолжить в чате Teams.</span><span class="sxs-lookup"><span data-stu-id="f44b5-121">You won't be able to continue in the native Teams chat.</span></span> <span data-ttu-id="f44b5-122">Вы по-прежнему можете читать чат Teams, но не можете продолжить беседу в этом месте.</span><span class="sxs-lookup"><span data-stu-id="f44b5-122">You can still read the native Teams chat, but you can't continue the conversation there.</span></span>

<span data-ttu-id="f44b5-123">Если Teams найдет старый текстовый чат с этим человеком, он будет обурочат этот чат.</span><span class="sxs-lookup"><span data-stu-id="f44b5-123">If Teams finds an old text-only chat with this person, it'll revive that chat.</span></span> <span data-ttu-id="f44b5-124">В противном случае Teams создаст новый текстовый чат.</span><span class="sxs-lookup"><span data-stu-id="f44b5-124">Otherwise, Teams creates a new text-only chat.</span></span>


## <a name="related-topics"></a><span data-ttu-id="f44b5-125">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="f44b5-125">Related topics</span></span>

[<span data-ttu-id="f44b5-126">Управление внешним доступом в Teams</span><span class="sxs-lookup"><span data-stu-id="f44b5-126">Manage external access in Teams</span></span>](manage-external-access.md)
