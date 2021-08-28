---
title: Отключение гибридной среды для завершения миграции в режим "Только Teams"
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: bjwhalen
ms.topic: article
ms.prod: skype-for-business-itpro
search.appverid: MET150
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
audience: ITPro
f1.keywords:
- NOCSH
appliesto:
- Skype for Business
- Microsoft Teams
ms.localizationpriority: medium
description: В этой статье содержатся подробные действия по отключению гибрида в рамках консолидации облачных Teams и Skype для бизнеса.
ms.openlocfilehash: 06d8980a14944004b22fbacc0aecef453d49123e
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/26/2021
ms.locfileid: "58619315"
---
# <a name="disable-your-hybrid-configuration-to-complete-migration-to-teams-only"></a>Отключение гибридной конфигурации для завершения миграции в Teams Only 

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]


В этой статье описывается отключение гибридной конфигурации перед выводом из эксплуатации локальной Skype для бизнеса среды. Это шаг 2 из следующих действий по выводу из эксплуатации локальной среды:

- Этап 1. [Перемещение всех необходимых пользователей из локального в интернет.](decommission-move-on-prem-users.md)

- **Шаг 2. Отключите гибридную конфигурацию.** (В этой статье)

- Этап 3. [Перенос конечных точек](decommission-move-on-prem-endpoints.md)гибридных приложений из локального в онлайн.

- Этап 4. [Удалите локальное развертывание Skype для бизнеса.](decommission-remove-on-prem.md)

> [!NOTE]
> Этапы 2 и 3 должны быть сделаны в одном окне обслуживания, так как существующие конечные точки гибридного приложения не будут обнаружены между этапами 2 и завершением шага 3.


## <a name="summary"></a>Сводка

После обновления всех пользователей из локального Skype для бизнеса до Teams только в Microsoft 365, вы можете списание локального Skype для бизнеса развертывания.

Прежде чем отключать локальное развертывание Skype для бизнеса и удалять оборудование, необходимо логически отделить локальное развертывание от Microsoft 365 путем отключения гибрида. Отключение гибрида состоит из следующих четырех действий:

1. [Обновление записей DNS, чтобы указать на Microsoft 365](#update-dns-to-point-to-microsoft-365).

2. [Измените режим сосуществования для организации](#change-the-coexistence-mode-for-your-organization-to-teams-only)на Teams только .

3. Отключение общего пространства адресов SIP (также известного как ["раздельный домен")](#disable-shared-sip-address-space-in-microsoft-365-organization)в Microsoft 365 организации.

4. [Отключение связи между локальной и Microsoft 365](#disable-communication-between-on-premises-and-microsoft-365)

Эти действия логически отделяют локальное развертывание Skype для бизнеса Server от Microsoft 365 и гарантируют полную Teams только. После завершения этих действий можно списать локальное развертывание Skype для бизнеса с помощью одного из двух [](cloud-consolidation-managing-attributes.md)методов, на которые ссылается в "Решение об управлении атрибутами после вывода из эксплуатации".

> [!Important] 
> После завершения этого логического разделения атрибуты msRTCSIP из локального Active Directory по-прежнему будут иметь значения и будут синхронизироваться с помощью Azure AD Подключение в Azure AD. Вывод локальной среды из эксплуатации зависит от того, собираетесь ли вы оставить эти атрибуты на месте или сначала очистить их от локального Active Directory. Следует помнить, что очистка атрибутов msRTCSIP на месте после миграции из локального помещения может привести к потере службы для пользователей! Подробные сведения и компромиссы двух подходов к выводу из эксплуатации описаны в "Решение об управлении атрибутами после вывода [из эксплуатации".](cloud-consolidation-managing-attributes.md)

## <a name="update-dns-to-point-to-microsoft-365"></a>Обновление DNS, чтобы указать на Microsoft 365

Внешние DNS организации для локальной организации должны быть обновлены таким образом, чтобы Skype для бизнеса записи указывают на Microsoft 365 вместо локального развертывания. 

Кроме того, записи CNAME для встречи или диалогов (если присутствуют) могут быть удалены. Наконец, все записи DNS для Skype для бизнеса во внутренней сети должны быть удалены.

Сведения об обновлении записей DNS см. в [статьях Обновление записей DNS,](decommission-manage-dns-entries.md)чтобы позволить организации быть Teams только .

## <a name="change-the-coexistence-mode-for-your-organization-to-teams-only"></a>Измените режим сосуществования для организации на Teams Только

Этот шаг гарантирует, что любой новый пользователь в организации всегда создается как Teams только пользователь. 

Попытка изменить режим клиента на Teams только автоматически проверит наличие каких-либо локальной DNS-записей, которые могли быть пропущены на шаге 1, и определит эти записи в выходе. Изменение режима клиента на Teams только не удастся до тех пор, пока не будут обновлены все записи DNS для вашей организации. 

Чтобы изменить режим клиента на Teams выполнить только следующую команду из окна Teams PowerShell.

```PowerShell
Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Global
```

Кроме того, вы можете использовать центр администрирования Teams для изменения режима сосуществования клиента на TeamsOnly в соответствии с "Настройками на всей организации" -> "Teams обновление".    

## <a name="disable-shared-sip-address-space-in-microsoft-365-organization"></a>Отключение общего пространства адресов sip в Microsoft 365 организации
    
Чтобы отключить общее пространство адресов sip, запустите следующую команду из окна Teams PowerShell.

```PowerShell
Set-CsTenantFederationConfiguration -SharedSipAddressSpace $false
```
 
## <a name="disable-communication-between-on-premises-and-microsoft-365"></a>Отключение связи между локальной и Microsoft 365

Чтобы отключить связь между локальной средой и Microsoft 365, запустите следующую команду из локального окна PowerShell:

```PowerShell
Get-CsHostingProvider|Set-CsHostingProvider -Enabled $false
```


## <a name="see-also"></a>См. также

- [Консолидация облаков для Teams и Skype для бизнеса](cloud-consolidation.md)

- [Прекращение использования локальной среды Skype для бизнеса](decommission-on-prem-overview.md)

