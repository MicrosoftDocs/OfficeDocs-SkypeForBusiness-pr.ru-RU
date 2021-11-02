---
title: Устранение неполадок с гостевым доступом в Microsoft Teams
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
ms.reviewer: corbinm
search.appverid: MET150
description: Справка по устранению неполадок и исправлению проблем с гостевым доступом в Microsoft Teams
f1.keywords:
- NOCSH
ms.localizationpriority: medium
appliesto:
- Microsoft Teams
ms.openlocfilehash: c8d54e236583211c2a8169987bf03ceba756facf
ms.sourcegitcommit: 1957a06d4bae3d42b4e3b6d4bd8ff2752a19d377
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/02/2021
ms.locfileid: "60641219"
---
# <a name="troubleshoot-problems-with-guest-access-in-microsoft-teams"></a>Устранение неполадок с гостевым доступом в Microsoft Teams

- Чтобы узнать, знаем ли мы о вашей проблеме, см. Teams [службу поддержки в вашей организации.](/MicrosoftTeams/troubleshoot/teams-welcome)
- Чтобы ознакомиться с текущими проблемами поддержки с гостевым доступом в Teams, перейдите в раздел [устранения неполадок в Teams](/MicrosoftTeams/troubleshoot/).
- Гости — это люди за пределами вашей организации. Если пользователь находится внутри вашей организации (включая ваших сотрудников, подрядчиков на площадке или агентов на площадке), его нельзя добавить в качестве гостя. То же касается ваших аффилированных лиц.
- Узнавайте о новых и обновленных функциях гостевого доступа из [Дорожной карты Teams](https://aka.ms/teamsroadmap).
- Сообщите, какие функции нужны вам, на сайте [UserVoice, посвященном Teams](https://aka.ms/TeamsUserVoice).

[!INCLUDE [uservoice-disclaimer-note](includes/uservoice-disclaimer-note.md)]

## <a name="if-your-guests-are-seeing-license-errors"></a>Если у гостей возникают ошибки лицензирования

Гостевой доступ в Teams использует взаимодействие "бизнес-бизнес" (B2B) Azure Active Directory (Azure AD) и соответствующую модель лицензирования. Функция гостевого доступа включена во все подписки Microsoft 365 бизнес стандарт, Office 365 корпоративный и Office 365 для образования. Дополнительная лицензия Microsoft 365 или Office 365 не требуется.

> [!NOTE]
> Teams гостевом клиенте для гостей должна быть включена возможность входа и использования Teams в другом (ресурсе) клиенте.

Если вы видите ошибки лицензирования, ознакомьтесь с моделью вы выставления счета для внешних удостоверений [Azure AD,](/azure/active-directory/external-identities/external-identities-pricing) чтобы определить требования лицензирования для гостевого доступа в организации.

- Гостевые лицензии учитываются в приглашающей организации. Это следует иметь в виду при подсчете количества необходимых лицензий.
- Лицензии учитываются в вашей организации независимо от того, являются ли приглашенные гости Microsoft 365 организации или используют свои личные адреса электронной почты.

## <a name="related-topics"></a>Статьи по теме

[Гостевой доступ в Teams](guest-access.md)

[Устранение неполадок Teams](/MicrosoftTeams/troubleshoot/teams)
