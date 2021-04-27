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
description: Узнайте о чате Teams для пользователей внешнего доступа (федеративен) в Microsoft Teams, где оба пользователя находятся в режиме обновления TeamsOnly.
ms.openlocfilehash: a06532ab4cd1d1c5ffe3f30d2a6036b2c34c716f
ms.sourcegitcommit: 5a39061c2156531f4b7f5f69eecf81a8c8b238d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/27/2021
ms.locfileid: "52030119"
---
# <a name="native-chat-experience-for-external-federated-users-in-microsoft-teams"></a><span data-ttu-id="f1237-103">Возможность чата для внешних (федеративных) пользователей в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="f1237-103">Native chat experience for external (federated) users in Microsoft Teams</span></span>

<span data-ttu-id="f1237-104">Когда пользователь Microsoft Teams общается с внешним (федератеренным) пользователем, возможности чата ограничены текстом.</span><span class="sxs-lookup"><span data-stu-id="f1237-104">When a Microsoft Teams user is chatting with an external (federated) user, the chat experience is limited to text.</span></span> <span data-ttu-id="f1237-105">Однако если как пользователь Teams, так и пользователь из другой организации находятся в режиме обновления TeamsOnly, вы можете использовать интерфейс чата native-Teams, который включает в себя форматирование, @mentions и другие функции чата.</span><span class="sxs-lookup"><span data-stu-id="f1237-105">However, if both your Teams user and the person in another organization are in the TeamsOnly upgrade mode, you can have a "native-Teams chat experience," which includes rich formatting, @mentions, and other chat features.</span></span> <span data-ttu-id="f1237-106">Чаты Teams с людьми из других организаций ограничены только 1:1 чатами.</span><span class="sxs-lookup"><span data-stu-id="f1237-106">Native Teams chats with people in other organizations are limited to 1:1 chats only.</span></span>

<span data-ttu-id="f1237-107">Для всех клиентов Teams включена родной чат для пользователей из других организаций, но не у всех пользователей есть права.</span><span class="sxs-lookup"><span data-stu-id="f1237-107">The native chat experience for people in other organizations is turned on for all Teams tenants, but not all people are eligible.</span></span> <span data-ttu-id="f1237-108">Чтобы получить возможность использовать свой чат, необходимо настроить как отправитель, так и приемник для режима обновления TeamsOnly.</span><span class="sxs-lookup"><span data-stu-id="f1237-108">To be offered a native chat experience, both the sender and receiver need to be configured for TeamsOnly upgrade mode.</span></span> <span data-ttu-id="f1237-109">Дополнительные информацию о политиках обновления можно найти в документе Настройка параметров сосуществования [и обновления.](setting-your-coexistence-and-upgrade-settings.md)</span><span class="sxs-lookup"><span data-stu-id="f1237-109">To learn more about upgrade policies, read [Setting your coexistence and upgrade settings](setting-your-coexistence-and-upgrade-settings.md).</span></span>

<span data-ttu-id="f1237-110">Список возможностей для пользователей внешнего доступа в Teams см. в списке Сравнение внешнего [и гостевого доступа.](communicate-with-users-from-other-organizations.md#compare-external-and-guest-access)</span><span class="sxs-lookup"><span data-stu-id="f1237-110">To see a list of capabilities for external access users in Teams, see [Compare external and guest access](communicate-with-users-from-other-organizations.md#compare-external-and-guest-access).</span></span>

## <a name="how-do-i-know-if-im-in-a-native-chat"></a><span data-ttu-id="f1237-111">Как узнать, есть ли у меня чат?</span><span class="sxs-lookup"><span data-stu-id="f1237-111">How do I know if I'm in a native chat?</span></span>

<span data-ttu-id="f1237-112">Если вы можете обмениваться текстом только в чате с людьми из других организаций, это значит, что вы общались в стандартном (федеративном) чате.</span><span class="sxs-lookup"><span data-stu-id="f1237-112">If you can only exchange text in your chat with people in other organizations, then you're in a standard external-access (federated) chat.</span></span> <span data-ttu-id="f1237-113">Если у вас есть все остальные функции чата, включая форматирование, @mentions, эмодзи и т. д., вы в чате Teams.</span><span class="sxs-lookup"><span data-stu-id="f1237-113">If you've got all of the other chat functionality, including formatting, @mentions, emojis, etc., then you're in a native Teams chat.</span></span> 

<span data-ttu-id="f1237-114">В Teams периодически проверяется режим обновления для людей из других организаций, а при поиске команды, запущенной в режиме обновления TeamsOnly, вам будет предложено переключиться в чат Teams и заблокировать исходный чат.</span><span class="sxs-lookup"><span data-stu-id="f1237-114">Teams periodically checks the upgrade mode for people in other organizations and, when it finds an them running Teams in the TeamsOnly upgrade mode, it'll prompt you to switch to a native Teams chat and lock the original chat.</span></span>

<span data-ttu-id="f1237-115">При переходе в чат Teams Teams не объединяет две беседы.</span><span class="sxs-lookup"><span data-stu-id="f1237-115">When you switch to a native Teams chat, Teams doesn't merge the two conversations.</span></span> <span data-ttu-id="f1237-116">Вместо этого вы увидите оба чата в своем веб-канале чата.</span><span class="sxs-lookup"><span data-stu-id="f1237-116">Instead, you'll see both of the chats in your chat feed.</span></span> <span data-ttu-id="f1237-117">Новый чат Teams активен, но старый чат, только текстовый, заблокирован.</span><span class="sxs-lookup"><span data-stu-id="f1237-117">The new, native-Teams chat is active, but the old, text-only chat is locked.</span></span>



## <a name="what-happens-if-a-user-isnt-in-teams-only-mode-anymore"></a><span data-ttu-id="f1237-118">Что произойдет, если пользователь больше не работает в режиме "Только Teams"?</span><span class="sxs-lookup"><span data-stu-id="f1237-118">What happens if a user isn't in Teams Only mode anymore?</span></span>

<span data-ttu-id="f1237-119">Если у вас был чат Teams с людьми из других организаций, а затем один из вас выходит из режима обновления TeamsOnly, Teams блокирует чат Teams и предоставляет ссылку на ограниченный текстовый чат.</span><span class="sxs-lookup"><span data-stu-id="f1237-119">If you were having a native Teams chat with people in other organizations and then one of you gets switched out of the TeamsOnly upgrade mode, Teams locks the native Teams chat and gives you a link for a limited, text-only chat.</span></span> <span data-ttu-id="f1237-120">Вы не сможете продолжить в чате Teams.</span><span class="sxs-lookup"><span data-stu-id="f1237-120">You won't be able to continue in the native Teams chat.</span></span> <span data-ttu-id="f1237-121">Вы по-прежнему можете читать чат Teams, но не можете продолжить беседу в этом чате.</span><span class="sxs-lookup"><span data-stu-id="f1237-121">You can still read the native Teams chat, but you can't continue the conversation there.</span></span>

<span data-ttu-id="f1237-122">Если Teams найдет старый текстовый чат с этим человеком, он будет совме речью.</span><span class="sxs-lookup"><span data-stu-id="f1237-122">If Teams finds an old text-only chat with this person, it'll revive that chat.</span></span> <span data-ttu-id="f1237-123">В противном случае Teams создаст новый текстовый чат.</span><span class="sxs-lookup"><span data-stu-id="f1237-123">Otherwise, Teams creates a new text-only chat.</span></span>


## <a name="related-topics"></a><span data-ttu-id="f1237-124">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="f1237-124">Related topics</span></span>

[<span data-ttu-id="f1237-125">Управление внешним доступом в Teams</span><span class="sxs-lookup"><span data-stu-id="f1237-125">Manage external access in Teams</span></span>](manage-external-access.md)
