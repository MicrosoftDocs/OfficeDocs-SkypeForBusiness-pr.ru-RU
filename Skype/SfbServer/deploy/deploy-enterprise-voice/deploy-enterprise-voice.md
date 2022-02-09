---
title: Развертывание Корпоративная голосовая связь в Skype для бизнеса Server
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: b5b593a6-ac30-461c-8c8c-0041e2c9ab04
description: Сводка. Сведения о развертывании Корпоративная голосовая связь для Skype для бизнеса Server на центральном сайте.
ms.openlocfilehash: a1d8452524a7de116866b8e27b2d8288321ce727
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/05/2022
ms.locfileid: "62417292"
---
# <a name="deploy-enterprise-voice-in-skype-for-business-server"></a>Развертывание Корпоративная голосовая связь в Skype для бизнеса Server

**Сводка:** Узнайте, как развернуть Корпоративная голосовая связь для Skype для бизнеса Server на центральном сайте.

Используйте эту тему для развертывания Корпоративная голосовая связь на центральном сайте. Чтобы развернуть Корпоративная голосовая связь на сайте филиала, переперейти к [развертыванию сайтов филиалов](/previous-versions/office/lync-server-2013/lync-server-2013-deploying-branch-sites).

В этом разделе содержатся процедуры развертывания, в которых сервер-посредник находится на каждом переднем или выпуск Standard сервере, как рекомендуется, а также для развертывания с автономным пулом серверов-посредников. Вы можете пропустить следующий контент, если вы использовали Topology Builder для определения и публикации топологии, которая коллокирует сервер-посредник на каждом переднем или выпуск Standard сервере, так как мастер развертывания уже автоматически установил файлы для сервера-посредника при установке файлов для пула переднего конечного сервера или выпуск Standard сервера:
## <a name="in-this-section"></a>В этой статье

- [Условия безопасности и конфигурации для Корпоративная голосовая связь в Skype для бизнеса Server](enterprise-voice-security.md)

- [Развертывание сервера-посредника в topology Builder в Skype для бизнеса Server](deploy-a-mediation-server.md)

- [Определение шлюза в Topology Builder в Skype для бизнеса Server](define-a-gateway.md)

- [Определите дополнительные магистрали в Topology Builder в Skype для бизнеса Server](define-additional-trunks.md)

- [Установите файлы для сервера-посредника в Skype для бизнеса Server](install-mediation-server.md)

- [Настройка магистрали в Skype для бизнеса Server](configure-trunks.md)

- [Создание или изменение правила перевода для презентации ID вызываемой Skype для бизнеса Server](caller-id-presentation-rules.md)

- [Создание или изменение правила перевода для так называемой презентации ID в Skype для бизнеса Server](called-id-presentation-rules.md)

- [Создание или изменение правила нормализации в Skype для бизнеса](normalization-rules.md)

- [Создание или изменение набора номера в Skype для бизнеса Server](dial-plans.md)

- [Настройка голосовых политик, записей использования PSTN и голосовых маршрутов в Skype для бизнеса](voice-and-pstn.md)

- [Включить пользователей для Корпоративная голосовая связь в Skype для бизнеса Server](enable-users-for-enterprise-voice.md)

- [Развертывание расширенных Корпоративная голосовая связь в Skype для бизнеса Server](deploy-advanced-enterprise-voice-features.md)

- [Развертывание функций управления вызовами в Skype для бизнеса](deploy-call-management-features.md)

## <a name="see-also"></a>См. также

[Планирование Корпоративная голосовая связь в Skype для бизнеса Server](../../plan-your-deployment/enterprise-voice-solution/enterprise-voice.md)