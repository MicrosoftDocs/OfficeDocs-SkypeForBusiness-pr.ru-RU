---
title: Управление политиками голосовой и голосовой почты в Teams
author: karlistites
ms.author: kastites
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: ''
search.appverid: ''
description: ''
audience: admin
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 7d0ea4db57fbfdc3ab76e8c6c9991e032103b260
ms.sourcegitcommit: e72599d5437773322ae6ef985f804a19101ed84f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/26/2021
ms.locfileid: "50348094"
---
# <a name="manage-voice-and-calling-policies-in-microsoft-teams"></a>Управление политиками голосовой и голосовой почты в Microsoft Teams

Политики голосовых и звонков используются для управления голосовой и голосовой почтой в Microsoft Teams.

## <a name="emergency-calling-policies"></a>Политики экстренных вызовов

Политики [экстренных вызовов](manage-emergency-calling-policies.md) используются для настройки того, что происходит, когда пользователь в вашей организации звонит. Эти политики управляются в Центре администрирования Teams или с помощью Windows PowerShell.

![Снимок экрана: политика для экстренных вызовов.](media/emergency-calling-policy2.png)

## <a name="emergency-call-routing-policies"></a>Политики маршрутинга экстренных вызовов

Если в вашей организации развернута прямая маршрутия [](manage-emergency-call-routing-policies.md) телефонной **системы,** вы можете использовать политики маршрутизации экстренных вызовов, чтобы определить, куда перенаправят экстренные вызовы, включены ли улучшенные экстренные службы и какие номера используются для экстренных служб. Управление этими политиками можно с помощью PowerShell или Центра администрирования Microsoft Teams.

![Снимок экрана: политика маршрутинга экстренных вызовов.](media/emergency-call-routing-policy.png)

## <a name="caller-id-policies"></a>Политики ИД вызываемой вызовы

[Политики, используемые для изменения](caller-id-policies.md) или блокировки этих политик, применяются для их изменения.

![Снимок экрана: политика "ИД звоня"](media/caller-id-policy.png)

## <a name="voice-routing-policies"></a>Политики маршрутинга голосовой почты

Политика [голосовой маршрутки —](manage-voice-routing-policies.md) это контейнер для записей об использовании телефонной сети общего пользования (ННР). Эти политики можно использовать, если в вашей организации развернута прямая маршрутия телефонной **системы.** Для управления политиками маршрутинга голосовой связи можно использовать PowerShell или Центр администрирования Teams.

![Снимок экрана: политика маршрутинга голосовой почты.](media/voice-routing-policy.png)

## <a name="calling-policies"></a>Политики звонков

[Политики звонков](teams-calling-policy.md) контролируют, какие функции переад управление звонками и переад управлением звонками доступны пользователям, включая возможность частных звонков, отправки звонков в группы звонков и перенаправка звонков на голосовую почту.

![Снимок экрана: политика звонков.](media/calling-policy.png)

## <a name="call-park-and-retrieve-policies"></a>Парковка вызовов и извлечение политик

[Если сделать это,](call-park-and-retrieve.md) другие пользователи будут поставлены на удержание и смогут продолжать звонок тому же или другому пользователю.

![Снимок экрана: парк вызовов и извлечение политики.](media/call-park-policy.png)

## <a name="create-and-manage-dial-plans"></a>Создание и использование абонентских групп

[В наборах](create-and-manage-dial-plans.md) можно переводить номера телефонов для авторизации и маршрутизации звонков. Создавать наборные группы и управлять ими можно с помощью PowerShell или Центра администрирования Microsoft Teams.

![Снимок экрана: набор номеров.](media/dial-plans.png)

## <a name="related-topics"></a>Статьи по теме

* [Управление политиками экстренных вызовов в Microsoft Teams](manage-emergency-calling-policies.md)
* [Управление политиками маршрутизации экстренных вызовов](manage-emergency-call-routing-policies.md)
* [Управление политиками ИД звоня в Microsoft Teams](caller-id-policies.md)
* [Управление политиками маршрутинга голосовой почты](manage-voice-routing-policies.md)
* [Политики звонков в Microsoft Teams](teams-calling-policy.md)
* [Парковка и восстановление звонков в Microsoft Teams](call-park-and-retrieve.md)
* [Создание и использование абонентских групп](create-and-manage-dial-plans.md)
* [Управление командами с помощью политик](manage-teams-with-policies.md)
