---
title: Возможность чата на языке внешних (федеративных) пользователей в Microsoft Teams
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
description: Узнайте о том, как Teams чата для пользователей внешнего доступа (федеративен) в Microsoft Teams, где оба пользователя находятся в режиме обновления TeamsOnly.
ms.openlocfilehash: 992b4dd28d17f1ba8abf7217d622da18813c3118
ms.sourcegitcommit: 74d3ab35c344d70b2399bc46a6ced3ab2762a470
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/06/2021
ms.locfileid: "60138235"
---
# <a name="native-chat-experience-for-external-federated-users-in-microsoft-teams"></a>Возможность чата на языке внешних (федеративных) пользователей в Microsoft Teams

Когда пользователь Microsoft Teams разговаривает с внешним (федератеренным) пользователем, возможности чата ограничены текстом. Однако если ваш Teams и пользователь из другой организации находятся в режиме обновления TeamsOnly, вы можете использовать чат в режиме "собственный Teams", который включает в себя форматирование, @mentions и другие функции чата.

Для всех клиентов Teams, но не у всех пользователей включена чатная беседа. Чтобы получить возможность использовать чат в обычном режиме, необходимо настроить как отправитель, так и приемник для режима обновления TeamsOnly. Дополнительные информацию о политиках обновления можно найти в документе Настройка параметров сосуществования [и обновления.](setting-your-coexistence-and-upgrade-settings.md)

Список возможностей для пользователей внешнего доступа в Teams см. в этой [Teams.](communicate-with-users-from-other-organizations.md#compare-external-and-guest-access)

## <a name="how-do-i-know-if-im-in-a-native-chat"></a>Как узнать, есть ли у меня чат?

Если вы можете обмениваться текстом только в чате с людьми из других организаций, это значит, что вы общались в стандартном (федеративном) чате с внешним доступом. Если у вас есть другие функции чата, в том числе форматирование, @mentions, эмодзи и т. д., вы в Teams чате. 

Teams время от времени проверяет режим обновления для людей из других организаций, а когда в режиме обновления TeamsOnly обнаруживается запущенный Teams, вам будет предложено переключиться на Teams чат и заблокировать исходный чат.

При переходе в Teams чат Teams не объединяет эти две беседы. Вместо этого вы увидите оба чата в своем веб-канале чата. Новый чат с Teams, но старый чат, только текст, заблокирован.



## <a name="what-happens-if-a-user-isnt-in-teams-only-mode-anymore"></a>Что произойдет, если пользователь больше не Teams режиме?

Если у вас был Teams чат с людьми из других организаций, а затем один из вас выходит из режима обновления TeamsOnly, Teams блокирует чат Teams и предоставляет ссылку на ограниченный текстовый чат. Вы не сможете продолжить в чате Teams чате. Вы по-прежнему сможете читать Teams чат, но не сможете продолжить беседу в этом чате.

Если Teams найдет старый текстовый чат с этим человеком, он будет в нем заготавлиться. В противном Teams создается новый текстовый чат.


## <a name="related-topics"></a>Статьи по теме

[Управление внешним доступом в Teams](manage-external-access.md)
