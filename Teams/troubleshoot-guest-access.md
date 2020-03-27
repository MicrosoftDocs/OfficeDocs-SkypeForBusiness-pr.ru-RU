---
title: Устранение неполадок с гостевым доступом в Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
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
appliesto:
- Microsoft Teams
localization_priority: Normal
ms.openlocfilehash: 0c0f65f7026e6c083d9230551d689f0dd19d6b0d
ms.sourcegitcommit: ed3d7ebb193229cab9e0e5be3dc1c28c3f622c1b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41837639"
---
<a name="troubleshoot-problems-with-guest-access-in-microsoft-teams"></a>Устранение неполадок с гостевым доступом в Microsoft Teams
======================================================

> [!IMPORTANT]
> Чтобы изменения вступили в силу, может потребоваться до 24 часов. 


- Чтобы ознакомиться с текущими проблемами поддержки с гостевым доступом в Teams, перейдите в раздел [устранения неполадок в Teams](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/).
- Чтобы узнать, известно ли нам о вашей проблеме, ознакомьтесь со статьей [Известные проблемы для Microsoft Teams](Known-issues.md).
- Гости — это пользователи из-за пределов вашей организации. Если пользователь находится внутри вашей организации (включая ваших сотрудников, подрядчиков на площадке или агентов на площадке), его нельзя добавить в качестве гостя. То же касается ваших аффилированных лиц.
- Узнавайте о новых и обновленных функциях гостевого доступа из [Дорожной карты Teams](https://aka.ms/teamsroadmap).
- Сообщите, какие функции нужны вам, на сайте [UserVoice, посвященном Teams](https://aka.ms/TeamsUserVoice).

## <a name="if-your-guests-are-seeing-license-errors"></a>Если у гостей возникают ошибки лицензирования

Гостевой доступ в Teams использует взаимодействие "бизнес-бизнес" (B2B) Azure Active Directory (Azure AD) и соответствующую модель лицензирования. Функция гостевого доступа включена во все подписки Office 365 бизнес премиум, Office 365 корпоративный и Office 365 для образования. Дополнительная лицензия Office 365 не требуется.

Если у вас возникают ошибки лицензирования, ознакомьтесь с [руководством по лицензированию Azure Active Directory B2B](https://docs.microsoft.com/azure/active-directory/b2b/licensing-guidance), чтобы определить лицензионные требования, соответствующие потребностями гостевого доступа в вашей организации.


- Гостевые лицензии учитываются в приглашающей организации. Это следует иметь в виду при подсчете количества необходимых лицензий.
- Лицензии учитываются в вашей организации, если приглашенные гости относятся к другому клиенту Office 365 или используют свои личные адреса электронной почты.

## <a name="support-for-b2b-user-types"></a>Поддержка типов пользователей B2B
В настоящее время Teams поддерживает гостевых пользователей только с состояниями 1 и 2 [согласно определению Azure B2B](https://docs.microsoft.com/azure/active-directory/b2b/user-properties).

## <a name="related-topics"></a>Статьи по теме

[Гостевой доступ в Teams](guest-access.md)


