---
title: Вывод из эксплуатации локальной среды Skype для бизнеса
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
description: Инструкции по выводу из эксплуатации локальной среды Skype для бизнеса.
ms.openlocfilehash: 7f5109661fc7d29d83172489dd987b96cb7e87fd
ms.sourcegitcommit: f223b5f3735f165d46bb611a52fcdfb0f4b88f66
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/06/2021
ms.locfileid: "51593902"
---
# <a name="decommission-your-on-premises-skype-for-business-environment"></a>Вывод из эксплуатации локальной среды Skype для бизнеса

Если ваша организация использует Teams или Skype для бизнеса Online с локальной развертыванием Skype для бизнеса Server, вы можете полностью перенести эти среды в облако, а затем завершить локальное развертывание Skype для бизнеса Server. 

> [!NOTE]
> Перед выводом из эксплуатации локальной среды [](configure-hybrid-connectivity.md) необходимо настроить гибридную связь между локальной развертыванием и Microsoft 365. После настройки гибридного подключения можно перенести пользователей в облако, перенося собрания из локального и перенося любые контакты из Skype для бизнеса Server в Teams. Настройка гибридного подключения — это необходимый шаг для переноса пользователей из локального в облако и обеспечения полной функциональности Teams.

Чтобы завершить переход из локальной среды в облако и вычистить локальное окружение Skype для бизнеса Server, необходимо выполнить следующие действия в следующем порядке:

- **Этап 1.** [Перемещение всех необходимых пользователей и конечных точек приложения](decommission-move-on-prem-users.md)из локального в интернет.

- **Шаг 2.** [Отключите гибридную конфигурацию.](cloud-consolidation-disabling-hybrid.md)

- **Шаг 3.** [Удалите локальное развертывание Skype для бизнеса.](decommission-remove-on-prem.md)

