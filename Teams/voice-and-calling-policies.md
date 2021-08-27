---
title: Управление политиками голосовой и голосовой Teams
author: karlistites
ms.author: kastites
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: ''
search.appverid: ''
description: Узнайте, Teams политик голосовой и голосовой почты.
audience: admin
ms.localizationpriority: medium
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 2c5207f9bbfc7212d09394f5b507559c715e561b
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/26/2021
ms.locfileid: "58577743"
---
# <a name="manage-voice-and-calling-policies-in-microsoft-teams"></a>Управление политиками голосовой и голосовой Microsoft Teams

Политики голосовых и звонков используются для управления голосовой и голосовой Microsoft Teams.

## <a name="emergency-calling-policies"></a>Политики экстренных вызовов

Политики [экстренных вызовов](manage-emergency-calling-policies.md) используются для настройки того, что происходит при звонке пользователем в организации. Управление этими политиками можно Teams центре администрирования или с помощью Windows PowerShell.

![Снимок экрана: политика экстренных вызовов.](media/emergency-calling-policy2.png)

## <a name="emergency-call-routing-policies"></a>Политики маршрутизов экстренных вызовов

Если ваша организация развернула телефонная система Direct **Routing,** [](manage-emergency-call-routing-policies.md) вы можете использовать политики маршрутизации экстренных вызовов, чтобы определить, куда перенаправят экстренные вызовы, включены ли улучшенные экстренные службы и какие номера используются для экстренных служб. Управление этими политиками можно управлять с помощью PowerShell или Microsoft Teams центре администрирования.

![Снимок экрана: политика маршрутизов экстренных вызовов.](media/emergency-call-routing-policy.png)

## <a name="caller-id-policies"></a>Политики ИД вызываемой вызовы

[Для изменения или блокировки](caller-id-policies.md) ИД вызываемой вызываемой вызовы применяются политики.

![Снимок экрана: политика "ИД звоняка".](media/caller-id-policy.png)

## <a name="voice-routing-policies"></a>Политики маршрутов голосовой маршрутии

Политика [голосовой маршрутистики](manage-voice-routing-policies.md) является контейнером для записей использования телефонной сети общего пользования (STN). Эти политики можно использовать, если в вашей организации развернута прямая **телефонная система маршрутизации.** Управление политиками маршрутинга голосовой почты можно управлять с помощью PowerShell или Teams центре администрирования.

![Снимок экрана: политика маршрутинга голосовой почты.](media/voice-routing-policy.png)

## <a name="calling-policies"></a>Политики звонков

[Политики звонков](teams-calling-policy.md) контролируют, какие функции переад сообщения и вызовы доступны пользователям, включая возможность личных звонков, отправки звонков в группы звонков и перенаправка звонков на голосовую почту.

![Снимок экрана: политика звонков.](media/calling-policy.png)

## <a name="call-park-and-retrieve-policies"></a>Парк вызовов и извлечение политик

[Парк вызовов и извлечение](call-park-and-retrieve.md) позволяет пользователям помещать других пользователей на удержание и позволяет тому же пользователю или другому пользователю продолжить звонок.

![Снимок экрана: парк вызовов и извлечение политики.](media/call-park-policy.png)

## <a name="create-and-manage-dial-plans"></a>Создание и использование абонентских групп

[В планах набора](create-and-manage-dial-plans.md) можно переводить номера телефонов для авторизации звонков и маршрутизации. Вы можете создавать наборные группы и управлять ими с помощью PowerShell или Microsoft Teams центре администрирования.

![Снимок экрана: план набора номера.](media/dial-plans.png)

## <a name="related-topics"></a>Статьи по теме

* [Управление политиками экстренных вызовов в Microsoft Teams](manage-emergency-calling-policies.md)
* [Управление политиками маршрутизации экстренных вызовов](manage-emergency-call-routing-policies.md)
* [Управление политиками идентификации вызывающего абонента в Microsoft Teams](caller-id-policies.md)
* [Управление политиками перенаправки голосовой почты](manage-voice-routing-policies.md)
* [Политики звонков в Microsoft Teams](teams-calling-policy.md)
* [Парковка и восстановление звонков в Microsoft Teams](call-park-and-retrieve.md)
* [Создание и использование абонентских групп](create-and-manage-dial-plans.md)
* [Управление Teams политиками](manage-teams-with-policies.md)
