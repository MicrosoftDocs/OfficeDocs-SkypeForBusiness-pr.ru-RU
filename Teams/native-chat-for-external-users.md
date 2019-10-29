---
title: Встроенные функции чата для внешних (Федеративных) пользователей в Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
ms.reviewer: vinbel
search.appverid: MET150
description: Узнайте о том, как работать с другими пользователями в Microsoft Teams с помощью чата, если оба пользователя находятся в режиме обновления Теамсонли.
ms.openlocfilehash: a7a66693bbff98aa707c369a9da08d0ccfe48f69
ms.sourcegitcommit: 09e719ead5c02b3cfa96828841c4905748d192a3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/28/2019
ms.locfileid: "37754345"
---
<a name="native-chat-experience-for-external-federated-users-in-microsoft-teams"></a><span data-ttu-id="87816-103">Встроенные функции чата для внешних (Федеративных) пользователей в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="87816-103">Native chat experience for external (federated) users in Microsoft Teams</span></span>
======================================

[!INCLUDE [preview-feature](includes/preview-feature.md)]

<span data-ttu-id="87816-104">Если пользователи Microsoft Teams находятся в чате с внешним (федеративным) пользователем, вы можете использовать для чата только текст.</span><span class="sxs-lookup"><span data-stu-id="87816-104">When a Microsoft Teams users is chatting with an external (federated) user, the chat experience is limited to text.</span></span> <span data-ttu-id="87816-105">Тем не менее, если как клиент Teams, так и внешний пользователь находятся в режиме обновления Теамсонли, вы можете использовать веб-взаимодействие в машинных группах (в том числе богатые возможности форматирования, @mentions и другие функции чата).</span><span class="sxs-lookup"><span data-stu-id="87816-105">However, if both your Teams tenant and that of the external user is in the TeamsOnly upgrade mode, you can have a "native-Teams chat experience," which includes rich formatting, @mentions, and other chat features.</span></span> <span data-ttu-id="87816-106">Другими словами, вы можете использовать один и тот же внешний чат с пользователями в 1:1 Teams и получить доступ к своим внешним пользователям в Организации.</span><span class="sxs-lookup"><span data-stu-id="87816-106">In other words, you can have the same rich 1:1 Teams chat experience with eligible external users as you'd have with users in your organization.</span></span> <span data-ttu-id="87816-107">Обсуждения в машинных группах с внешними пользователями по-прежнему ограничены только на 1:1 чатов (внешние пользователи не могут делать групповые разговоры).</span><span class="sxs-lookup"><span data-stu-id="87816-107">Native Teams chats with external users are still limited to 1:1 chats only (external users can't do group chats).</span></span>

<span data-ttu-id="87816-108">Встроенные функции чата для внешних пользователей включены для всех клиентов Teams, но не все пользователи могут быть доступны.</span><span class="sxs-lookup"><span data-stu-id="87816-108">The native chat experience for external users is turned on for all Teams tenants, but not all users are eligible.</span></span> <span data-ttu-id="87816-109">Чтобы вы могли предлагать себе собственный чат, как отправитель, так и получатель должны находиться в клиенте Teams, который работает в режиме обновления Теамсонли.</span><span class="sxs-lookup"><span data-stu-id="87816-109">To be offered a native chat experience, both the sender and receiver need to be on a Teams tenant that's running the TeamsOnly upgrade mode.</span></span> <span data-ttu-id="87816-110">Чтобы узнать больше о политиках обновления, ознакомьтесь со статьей [Настройка параметров сосуществования и обновления](setting-your-coexistence-and-upgrade-settings.md).</span><span class="sxs-lookup"><span data-stu-id="87816-110">To learn more about upgrade policies, read [Setting your coexistence and upgrade settings](setting-your-coexistence-and-upgrade-settings.md).</span></span>

<span data-ttu-id="87816-111">Список возможностей для пользователей внешнего доступа в Teams можно найти в статье [Сравнение внешних и гостевой доступа](communicate-with-users-from-other-organizations.md#compare-external-and-guest-access).</span><span class="sxs-lookup"><span data-stu-id="87816-111">To see a list of capabilities for external access users in Teams, see [Compare external and guest access](communicate-with-users-from-other-organizations.md#compare-external-and-guest-access).</span></span>

## <a name="how-do-i-know-if-im-in-a-native-chat"></a><span data-ttu-id="87816-112">Как узнать, есть ли у меня собственный чат?</span><span class="sxs-lookup"><span data-stu-id="87816-112">How do I know if I'm in a native chat?</span></span>

<span data-ttu-id="87816-113">Если вы можете обмениваться сообщениями в чате только с внешним пользователем, вы используете стандартный чат для внешнего доступа (федеративного).</span><span class="sxs-lookup"><span data-stu-id="87816-113">If you can only exchange text in your chat with an external user, then you're in a standard external-access (federated) chat.</span></span> <span data-ttu-id="87816-114">Если у вас есть все другие функции чата, в том числе форматирование, @mentions, эмодзи и т. д., то вы находитесь в чате с помощью внешнего пользователя.</span><span class="sxs-lookup"><span data-stu-id="87816-114">If you've got all of the other chat functionality, including formatting, @mentions, emojis, etc., then you're in a native Teams chat with your external user.</span></span> 

<span data-ttu-id="87816-115">Команды периодически проверяют режим обновления для внешних пользователей, и при обнаружении внешнего пользователя, работающего с Teams, в режиме обновления Теамсонли вам будет предложено переключиться на чат в машинных группах и заблокировать первоначальный чат.</span><span class="sxs-lookup"><span data-stu-id="87816-115">Teams periodically checks the upgrade mode for external users and, when it finds an external user running Teams in the TeamsOnly upgrade mode, it'll prompt you to switch to a native Teams chat and lock the original chat.</span></span>

<span data-ttu-id="87816-116">При переключении на чат, работающий в машинных группах, команды не объединяются в двух беседах.</span><span class="sxs-lookup"><span data-stu-id="87816-116">When you switch to a native Teams chat, Teams doesn't merge the two conversations.</span></span> <span data-ttu-id="87816-117">Вместо этого вы увидите оба разговора в своем веб-канале чата.</span><span class="sxs-lookup"><span data-stu-id="87816-117">Instead, you'll see both of the chats in your chat feed.</span></span> <span data-ttu-id="87816-118">Новый чат в машинном коде для Teams активен, но старый чат-текст заблокирован.</span><span class="sxs-lookup"><span data-stu-id="87816-118">The new, native-Teams chat is active, but the old, text-only chat is locked.</span></span>



## <a name="what-happens-if-a-user-isnt-in-teams-only-mode-anymore"></a><span data-ttu-id="87816-119">Что произойдет, если пользователь больше не находится в режиме "только для Teams"?</span><span class="sxs-lookup"><span data-stu-id="87816-119">What happens if a user isn't in Teams Only mode anymore?</span></span>

<span data-ttu-id="87816-120">Если вы столкнулись с собственным сеансом работы с внешним пользователем, а затем один из них выходит из режима обновления Теамсонли, команды заблокируют собственный чат Teams и предоставляет вам ссылку для ограниченного текстового чата.</span><span class="sxs-lookup"><span data-stu-id="87816-120">If you were having a native Teams chat with an external user and then one of you gets switched out of the TeamsOnly upgrade mode, Teams locks the native Teams chat and gives you a link for a limited, text-only chat.</span></span> <span data-ttu-id="87816-121">Вы не сможете продолжить чат в собственной Teams.</span><span class="sxs-lookup"><span data-stu-id="87816-121">You won't be able to continue in the native Teams chat.</span></span> <span data-ttu-id="87816-122">Вы по-прежнему можете прочитать чат в машинных группах, но вы не сможете продолжить беседу.</span><span class="sxs-lookup"><span data-stu-id="87816-122">You can still read the native Teams chat, but you can't continue the conversation there.</span></span>

<span data-ttu-id="87816-123">Если в Teams будет найден старый чат с внешним пользователем, он ревиве этот чат.</span><span class="sxs-lookup"><span data-stu-id="87816-123">If Teams finds an old text-only chat with this external user, it'll revive that chat.</span></span> <span data-ttu-id="87816-124">В противном случае Teams создает новый текстовый чат.</span><span class="sxs-lookup"><span data-stu-id="87816-124">Otherwise, Teams creates a new text-only chat.</span></span>


## <a name="related-topics"></a><span data-ttu-id="87816-125">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="87816-125">Related topics</span></span>

[<span data-ttu-id="87816-126">Управление внешним доступом в Teams</span><span class="sxs-lookup"><span data-stu-id="87816-126">Manage external access in Teams</span></span>](manage-external-access.md)
