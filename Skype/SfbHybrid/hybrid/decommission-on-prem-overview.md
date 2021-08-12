---
title: Прекращение использования локальной среды Skype для бизнеса
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: bjwhalen
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
description: Инструкции по выводу из эксплуатации локальной Skype для бизнеса среды.
ms.openlocfilehash: 0f1b25c6960739992913f31a89a9f554fb180e949df3e6dd213b5fbe14c4af82
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2021
ms.locfileid: "54280356"
---
# <a name="decommission-your-on-premises-skype-for-business-environment"></a>Прекращение использования локальной среды Skype для бизнеса

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

Если организация использует Teams локальное развертывание Skype для бизнеса Server, эти среды можно полностью перенести в облако, а затем завершить локальное развертывание Skype для бизнеса Server. 

> [!NOTE]
> Перед выводом из эксплуатации локальной среды [](configure-hybrid-connectivity.md) необходимо настроить гибридную связь между локальной развертыванием и Microsoft 365. После настройки гибридного подключения можно перенести пользователей в облако, перенося собрания из локального и перенося все контакты из Skype для бизнеса Server в Teams. Настройка гибридного подключения — это необходимый шаг для переноса пользователей из локального в облако и обеспечения полного Teams функций.

Чтобы завершить перемещение из локальной среды в облако и списание локальной Skype для бизнеса Server среды, необходимо выполнить следующие действия в следующем порядке:

- **Этап 1.** [Перемещение всех необходимых пользователей из локального в интернет.](decommission-move-on-prem-users.md)

- **Этап 2.** [Отключите гибридную конфигурацию.](cloud-consolidation-disabling-hybrid.md)

- **Этап 3.** [Перемещение конечных точек гибридного приложения из локального в интернет.](decommission-move-on-prem-endpoints.md)

- **Этап 4.** [Удалите локальное развертывание Skype для бизнеса.](decommission-remove-on-prem.md)

