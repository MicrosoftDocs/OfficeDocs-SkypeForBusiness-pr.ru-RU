---
title: Управление политиками голосовой связи и звонков в Teams
author: mkbond007
ms.author: mabond
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: ''
search.appverid: ''
description: Узнайте о Teams голосовых вызовов и политиках звонков.
audience: admin
ms.localizationpriority: medium
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 8a63aa772d94a4a385301315d1c1bd3b6488fa3b
ms.sourcegitcommit: 9532eb79310cd653010565607fa394f2b8dd182d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/23/2022
ms.locfileid: "65646468"
---
# <a name="manage-voice-and-calling-policies-in-microsoft-teams"></a>Управление политиками голосовой связи и звонков в Microsoft Teams

Политики голосовой связи и звонков используются для управления голосовой связью и вызовами в Microsoft Teams.

## <a name="emergency-calling-policies"></a>Политики экстренных вызовов

Политики [экстренных вызовов используются](manage-emergency-calling-policies.md) для настройки того, что происходит, когда пользователь в вашей организации совершает экстренный вызов. Эти политики управляются в центре администрирования Teams или с помощью Windows PowerShell.

![Снимок экрана: политика экстренных вызовов.](media/emergency-calling-policy2.png)

## <a name="emergency-call-routing-policies"></a>Политики маршрутизации экстренных вызовов

Если ваша организация развернула прямую маршрутизацию **телефонная система**, можно использовать политики маршрутизации экстренных вызовов, чтобы определить, куда направляются экстренные вызовы, включены ли расширенные экстренные службы и какие номера используются для экстренных служб.[](manage-emergency-call-routing-policies.md) Управление этими политиками можно выполнить с помощью PowerShell или Microsoft Teams центра администрирования.

![Снимок экрана: политика маршрутизации экстренных вызовов.](media/emergency-call-routing-policy.png)

## <a name="caller-id-policies"></a>Политики идентификаторов вызывающих абонентов

[Политики идентификатора вызывающего](caller-id-policies.md) абонента используются для изменения или блокировки идентификатора вызывающего абонента.

![Снимок экрана: политика идентификатора вызывающего абонента.](media/caller-id-policy.png)

## <a name="voice-routing-policies"></a>Политики маршрутизации голосовой связи

Политика [маршрутизации голосовой связи](manage-voice-routing-policies.md) — это контейнер для записей об использовании телефонной сети общего пользования (ТСОП). Эти политики можно использовать, если ваша организация развернула телефонная система **прямой маршрутизации**. Управление политиками маршрутизации голосовой связи можно выполнять с помощью PowerShell или Teams центра администрирования.

![Снимок экрана: политика маршрутизации голосовой связи.](media/voice-routing-policy.png)

## <a name="calling-policies"></a>Политики звонков

[Политики](teams-calling-policy.md) звонков позволяют контролировать, какие функции переадресации звонков и звонков доступны пользователям, включая возможность личных звонков, отправки звонков в группы звонков и маршрутизации звонков в голосовую почту.

![Снимок экрана: политика вызова.](media/calling-policy.png)

## <a name="call-park-and-retrieve-policies"></a>Парковка вызовов и получение политик

[Приостановка и извлечение](call-park-and-retrieve.md) звонков позволяет пользователям помещать других пользователей на удержание и позволяет одному пользователю или другому пользователю продолжить звонок.

![Снимок экрана: парковка вызовов и получение политики.](media/call-park-policy.png)

## <a name="create-and-manage-dial-plans"></a>Создание и использование абонентских групп

[Абонентские группы](create-and-manage-dial-plans.md) преобразовывают номера телефонов с телефонным подключением для авторизации и маршрутизации звонков. Вы можете создавать абонентские группы и управлять ими с помощью PowerShell или Microsoft Teams центра администрирования.

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
