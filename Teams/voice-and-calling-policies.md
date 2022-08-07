---
title: Управление политиками голосовых вызовов и голосовых вызовов в Teams
author: mkbond007
ms.author: mabond
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: ''
search.appverid: ''
description: Узнайте о политиках голосовой связи и звонков Teams.
audience: admin
ms.localizationpriority: medium
ms.collection:
- M365-voice
ms.openlocfilehash: 5a6676d29a439ed978385d096c6e8b0584049557
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/07/2022
ms.locfileid: "67270294"
---
# <a name="manage-voice-and-calling-policies-in-microsoft-teams"></a>Управление политиками голосовых вызовов и голосовых вызовов в Microsoft Teams

Политики голосовой связи и звонков используются для управления голосовой связью и звонками в Microsoft Teams.

## <a name="emergency-calling-policies"></a>Политики экстренных вызовов

Политики [экстренных вызовов используются](manage-emergency-calling-policies.md) для настройки того, что происходит, когда пользователь в вашей организации совершает экстренный вызов. Управление этими политиками можно выполнить в Центре администрирования Teams или с помощью Windows PowerShell.

![Снимок экрана: политика экстренных вызовов.](media/emergency-calling-policy2.png)

## <a name="emergency-call-routing-policies"></a>Политики маршрутизации экстренных вызовов

Если в вашей организации развернута прямая маршрутизация телефонной **системы, вы** можете использовать [](manage-emergency-call-routing-policies.md) политики маршрутизации экстренных вызовов, чтобы определить, куда направляются экстренные вызовы, включены ли расширенные экстренные службы и какие номера используются для экстренных служб. Управление этими политиками можно выполнить с помощью PowerShell или Центра администрирования Microsoft Teams.

![Снимок экрана: политика маршрутизации экстренных вызовов.](media/emergency-call-routing-policy.png)

## <a name="caller-id-policies"></a>Политики идентификаторов вызывающих абонентов

[Политики идентификатора вызывающего](caller-id-policies.md) абонента используются для изменения или блокировки идентификатора вызывающего абонента.

![Снимок экрана: политика идентификатора вызывающего абонента.](media/caller-id-policy.png)

## <a name="voice-routing-policies"></a>Политики маршрутизации голосовой связи

Политика [маршрутизации голосовой связи](manage-voice-routing-policies.md) — это контейнер для записей об использовании телефонной сети общего пользования (ТСОП). Эти политики можно использовать, если в вашей организации развернута прямая **маршрутизация телефонной системы**. Управление политиками маршрутизации голосовой связи можно выполнять с помощью PowerShell или Центра администрирования Teams.

![Снимок экрана: политика маршрутизации голосовой связи.](media/voice-routing-policy.png)

## <a name="calling-policies"></a>Политики звонков

[Политики](teams-calling-policy.md) звонков позволяют контролировать, какие функции переадресации звонков и звонков доступны пользователям, включая возможность личных звонков, отправки звонков в группы звонков и маршрутизации звонков в голосовую почту.

![Снимок экрана: политика вызова.](media/calling-policy.png)

## <a name="call-park-and-retrieve-policies"></a>Парковка вызовов и получение политик

[Приостановка и извлечение](call-park-and-retrieve.md) звонков позволяет пользователям помещать других пользователей на удержание и позволяет одному пользователю или другому пользователю продолжить звонок.

![Снимок экрана: парковка вызовов и получение политики.](media/call-park-policy.png)

## <a name="create-and-manage-dial-plans"></a>Создание и использование абонентских групп

[Абонентские группы](create-and-manage-dial-plans.md) преобразовывают номера телефонов с телефонным подключением для авторизации и маршрутизации звонков. Вы можете создавать абонентские группы и управлять ими с помощью PowerShell или Центра администрирования Microsoft Teams.

![Снимок экрана: абонентской группы.](media/dial-plans.png)

## <a name="related-topics"></a>Статьи по теме

* [Управление политиками экстренных вызовов в Microsoft Teams](manage-emergency-calling-policies.md)
* [Управление политиками маршрутизации экстренных вызовов](manage-emergency-call-routing-policies.md)
* [Управление политиками идентификации вызывающего абонента в Microsoft Teams](caller-id-policies.md)
* [Управление политиками маршрутизации голосовой связи](manage-voice-routing-policies.md)
* [Политики звонков в Microsoft Teams](teams-calling-policy.md)
* [Парковка и восстановление звонков в Microsoft Teams](call-park-and-retrieve.md)
* [Создание и использование абонентских групп](create-and-manage-dial-plans.md)
* [Управление Teams с помощью политик](manage-teams-with-policies.md)
