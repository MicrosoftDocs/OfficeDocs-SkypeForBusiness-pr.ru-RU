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
description: Инструкции по выводу из эксплуатации локальной среды Skype для бизнеса.
ms.openlocfilehash: 46848c6730d37f549a8d5ee16f066fa67c789873
ms.sourcegitcommit: 71d90f0a0056f7604109f64e9722c80cf0eda47d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/09/2021
ms.locfileid: "51656685"
---
# <a name="decommission-your-on-premises-skype-for-business-environment"></a>Прекращение использования локальной среды Skype для бизнеса

Если ваша организация использует Teams или Skype для бизнеса Online с локальной развертыванием Skype для бизнеса Server, вы можете полностью перенести эти среды в облако, а затем завершить локальное развертывание Skype для бизнеса Server. 

> [!NOTE]
> Перед выводом из эксплуатации локальной среды [](configure-hybrid-connectivity.md) необходимо настроить гибридную связь между локальной развертыванием и Microsoft 365. После настройки гибридного подключения можно перенести пользователей в облако, перенося собрания из локального и перенося любые контакты из Skype для бизнеса Server в Teams. Настройка гибридного подключения — это необходимый шаг для переноса пользователей из локального в облако и обеспечения полной функциональности Teams.

Чтобы завершить переход из локальной среды в облако и вычистить локальное окружение Skype для бизнеса Server, необходимо выполнить следующие действия в следующем порядке:

- **Этап 1.** [Перемещение всех необходимых пользователей из локального в интернет.](decommission-move-on-prem-users.md)

- **Шаг 2.** [Отключите гибридную конфигурацию.](cloud-consolidation-disabling-hybrid.md)

- **Шаг 3.** [Перемещение конечных точек гибридного приложения из локального в интернет.](decommission-move-on-prem-endpoints.md)

- **Этап 4.** [Удалите локальное развертывание Skype для бизнеса.](decommission-remove-on-prem.md)

