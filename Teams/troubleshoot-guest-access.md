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
localization_priority: Normal
appliesto:
- Microsoft Teams
ms.openlocfilehash: 0ce7744aa18fe8ffe3fc83ca40649672f521bbba
ms.sourcegitcommit: 43e5a4aac11c20dd5a4c35b59695f309e1559e82
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/03/2020
ms.locfileid: "48346360"
---
# <a name="troubleshoot-problems-with-guest-access-in-microsoft-teams"></a>Устранение неполадок с гостевым доступом в Microsoft Teams

- Чтобы узнать, знаем ли мы о вашей проблеме, ознакомьтесь со службой [поддержки Teams в вашей организации.](Known-issues.md)
- Чтобы ознакомиться с текущими проблемами поддержки с гостевым доступом в Teams, перейдите в раздел [устранения неполадок в Teams](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/).
- Гости — это люди за пределами вашей организации. Если пользователь находится внутри вашей организации (включая ваших сотрудников, подрядчиков на площадке или агентов на площадке), его нельзя добавить в качестве гостя. То же касается ваших аффилированных лиц.
- Узнавайте о новых и обновленных функциях гостевого доступа из [Дорожной карты Teams](https://aka.ms/teamsroadmap).
- Сообщите, какие функции нужны вам, на сайте [UserVoice, посвященном Teams](https://aka.ms/TeamsUserVoice).

## <a name="if-your-guests-are-seeing-license-errors"></a>Если у гостей возникают ошибки лицензирования

Гостевой доступ в Teams использует взаимодействие "бизнес-бизнес" (B2B) Azure Active Directory (Azure AD) и соответствующую модель лицензирования. Функция гостевого доступа включена во все подписки Microsoft 365 бизнес стандарт, Office 365 корпоративный и Office 365 для образования. Дополнительная лицензия Microsoft 365 или Office 365 не требуется.

> [!NOTE]
> Для входа и использования Teams в качестве гостя в другом (ресурсе) клиенте для гостей должна быть включена возможность использования Teams в качестве гостя.

Если вы видите ошибки лицензирования, обязательно ознакомьтесь с моделью вы выставления счета для внешних удостоверений [Azure AD,](https://docs.microsoft.com/azure/active-directory/external-identities/external-identities-pricing) чтобы определить требования лицензирования для гостевого доступа в вашей организации.

- Гостевые лицензии учитываются в приглашающей организации. Это следует иметь в виду при подсчете количества необходимых лицензий.
- Лицензии учитываются в вашей организации независимо от того, были ли приглашенные гости из другой организации Microsoft 365 или используют их личные адреса электронной почты.

## <a name="support-for-b2b-user-types"></a>Поддержка типов пользователей B2B

В настоящее время Teams поддерживает гостевых пользователей только с состояниями 1 и 2 [согласно определению Azure B2B](https://docs.microsoft.com/azure/active-directory/b2b/user-properties).

## <a name="related-topics"></a>Статьи по теме

[Гостевой доступ в Teams](guest-access.md)

[Устранение неполадок Teams](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/teams)