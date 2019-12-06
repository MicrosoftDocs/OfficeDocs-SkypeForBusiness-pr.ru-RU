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
description: Узнайте, как устранить неполадки с гостевым доступом в Microsoft Teams и устранить проблемы с ним.
appliesto:
- Microsoft Teams
localization_priority: Normal
ms.openlocfilehash: e0a3530b7a1f9029d9f671d0a02ef58cbb7907bf
ms.sourcegitcommit: 96d98e145ff300833d827a7d43b4e4b0331b7538
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/05/2019
ms.locfileid: "39871735"
---
<a name="troubleshoot-problems-with-guest-access-in-microsoft-teams"></a>Устранение неполадок с гостевым доступом в Microsoft Teams
======================================================

> [!IMPORTANT]
> Чтобы изменения вступили в силу, возможно, потребуется подождать до 24 часов. 


- Для проверки текущих проблем с доступом к гостевой службе в Teams перейдите в раздел [Устранение неполадок команды Teams](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/).
- Чтобы узнать, что мы знаем о проблеме, ознакомьтесь со статьей [Известные проблемы в Microsoft Teams](Known-issues.md).
- Гости — это пользователи за пределами вашей организации. Если кто-то входит в вашу организацию (в том числе на ваших сотрудников, подрядчиков или агентах по сайту), их нельзя добавить в качестве гостей. То же касается ваших аффилированных лиц.
- Узнайте о предстоящих новых и обновленных функциях гостевого доступа в [планах Teams](https://aka.ms/teamsroadmap).
- Расскажите нам, что вам нужно, в [Teams UserVoice](https://aka.ms/TeamsUserVoice).

## <a name="if-your-guests-are-seeing-license-errors"></a>Если гости видят ошибки лицензий

Гостевой доступ в Teams использует бизнес-компанию Azure Active Directory (Azure AD) для бизнеса (B2B) и модель лицензирования. Функция гостевого доступа включена во все подписки Office 365 бизнес премиум, Office 365 корпоративный и Office 365 для образования. Дополнительная лицензия Office 365 не требуется.

Если вы видите ошибки лицензирования, ознакомьтесь с [рекомендациями по лицензированию Azure Active Directory B2B](https://docs.microsoft.com/azure/active-directory/b2b/licensing-guidance) , чтобы определить требования к лицензированию в соответствии с вашими потребностями для гостевого доступа в вашей организации.


- Гостевые лицензии подсчитываются с помощью приглашенной Организации. Это следует помнить при расчете количества лицензий, которые вам понадобятся.
- Лицензии будут учитываться в вашей организации, независимо от того, приходят ли приглашенные гости другим клиентам Office 365 или используют их личные адреса электронной почты.

## <a name="support-for-b2b-user-types"></a>Поддержка типов пользователей B2B
В настоящее время поддерживаются только типы "состояние 1" и "состояние 2" для гостевых пользователей [в соответствии с определением Azure B2B](https://docs.microsoft.com/azure/active-directory/b2b/user-properties).

## <a name="related-topics"></a>Статьи по теме

[Гостевой доступ в Teams](guest-access.md)


