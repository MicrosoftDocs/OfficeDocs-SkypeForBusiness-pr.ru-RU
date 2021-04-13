---
title: Перемещение пользователей в облако
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
description: Перемещение пользователей до вывода из эксплуатации локальной среды Skype для бизнеса.
ms.openlocfilehash: f04ebeec51b739faa89f907de6c363f0ef70a78e
ms.sourcegitcommit: 71d90f0a0056f7604109f64e9722c80cf0eda47d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/09/2021
ms.locfileid: "51656675"
---
# <a name="move-required-users-before-decommissioning-your-on-premises-environment"></a>Перемещение необходимых пользователей до вывода из эксплуатации локальной среды

В этой статье описывается, как переместить необходимых пользователей в облако Microsoft до вывода из эксплуатации локальной среды Skype для бизнеса. Это шаг 1 из следующих действий по выводу из эксплуатации локальной среды:

- **Шаг 1. Перемещение всех необходимых пользователей из локальной сети в интернет.** (В этой статье)

- Шаг 2. [Отключите гибридную конфигурацию.](cloud-consolidation-disabling-hybrid.md)

- Шаг 3. [Перемещение конечных точек гибридного приложения из локального в интернет.](decommission-move-on-prem-endpoints.md)

- Этап 4. [Удалите локальное развертывание Skype для бизнеса.](decommission-remove-on-prem.md)


## <a name="move-all-required-users-from-on-premises-to-the-cloud"></a>Перемещение всех необходимых пользователей из локального в облако

Все пользователи, которые будут продолжать использовать после завершения миграции, сначала должны быть перемещены из локального в облако. Перемещение пользователей с помощью средств администрирования на месте. Подробные сведения см. в [материале Перемещение пользователей между локальной и облачной.](move-users-between-on-premises-and-cloud.md)

Несмотря на то, что пользователи с учетными записями Skype для бизнеса Server могут использовать Teams, эти пользователи не имеют полных функциональных возможностей Teams. Эти пользователи не могут скооперироваться или федератироваться с любым другим пользователем, все еще использующим Skype для бизнеса (будь то онлайн или локально). Эти пользователи также не могут принимать вызовы PSTN в клиенте Teams. Поэтому необходимо переместить этих пользователей в интернет. Этот шаг также обеспечивает перенос контактов или собраний, созданных в Skype для бизнеса Server, в Teams.

Чтобы проверить, есть ли в локальном развертывании оставшиеся пользователи, запустите следующий комдлет в окне Skype для бизнеса Server PowerShell.

```PowerShell
Get-CsUser -Filter { HostingProvider -eq "SRV:"}
```

Если какие-либо пользователи возвращаются, просмотрите вывод, чтобы определить, следует ли какие-либо учетные записи быть перемещены в облако, и для любых таких пользователей выполните действия [здесь](move-users-between-on-premises-and-cloud.md). Для учетных записей пользователей, которые больше не нужны, запустите следующий комдлет Skype для бизнеса Server PowerShell:

```PowerShell
Get-CsUser -Filter { HostingProvider -eq "SRV:"} | Disable-CsUser
```

> [!NOTE]
> Запуск Disable-CsUser удаляет все атрибуты Skype для бизнеса для всех пользователей, которые соответствуют критериям фильтрации. Перед началом процедуры подтвердим, что эти учетные записи больше не нужны.


Теперь вы готовы отключить [гибридную конфигурацию.](cloud-consolidation-disabling-hybrid.md)

## <a name="see-also"></a>См. также

- [Прекращение использования локальной среды Skype для бизнеса](decommission-on-prem-overview.md)

- [Отключение гибридной конфигурации](cloud-consolidation-disabling-hybrid.md)

- [Перемещение конечных точек гибридного приложения из локального в online](decommission-move-on-prem-endpoints.md)

- [Удаление локального развертывания Skype для бизнеса](decommission-remove-on-prem.md)




