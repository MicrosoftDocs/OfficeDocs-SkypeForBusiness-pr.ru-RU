---
title: Требования и зависимости окружающей среды для перехода на Teams
author: msdmaguire
ms.author: dmaguire
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: landerl
audience: admin
description: В этой статье описаны требования и зависимости окружающей среды для развертывания групп в Организации
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: bcd3de45954ea500a6be0d325370ab0660604a65
ms.sourcegitcommit: 1e16c6c7112bdde03209c12468b5705ddd116a62
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/05/2020
ms.locfileid: "49578282"
---
# <a name="prerequisites-and-environmental-dependencies-for-teams"></a>Требования и зависимости окружающей среды для Teams

![Обновление схемы поездки с акцентом на этапе технической подготовки](media/upgrade-banner-tech-readiness.png "Этапы путешествия по обновлению с акцентом на этапе технической подготовки")

Эта статья относится к техническому этапу подготовки к обновлению, действиям, завершенным параллельно с этапом готовности пользователей. Прежде чем продолжить, подтвердите, что вы выполнили следующие действия из предыдущих стадий.

- [Вовлеченные заинтересованные лица в проект](upgrade-enlist-stakeholders.md)
- [Определение области охвата проекта](https://aka.ms/SkypetoTeams-Scope)
- [Сосуществование и взаимодействие Skype для бизнеса и рабочих групп](https://aka.ms/SkypeToTeams-Coexist)
- [Выбрано путешествие с обновлением](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)

В Teams объединены различные службы Microsoft 365 и Office 365, поэтому они зависят от правильной реализации и функционирования этих служб. Эти службы включают (но не ограничиваются) SharePoint Online, Exchange Online и OneDrive для бизнеса.

Несмотря на то, что требуется не все службы, мы настоятельно рекомендуем вам реализовать все. Если вы решили не применять определенные службы, это повлияет на функциональность, которую Teams может предложить вашей организации. Например, несмотря на то, что вам не нужно реализовывать SharePoint Online, в Teams в SharePoint Online используются определенные функции, такие как общий доступ к файлам во время групповых разговоров, поэтому не реализация этой службы уменьшает функциональность, предоставляемую клиентом.

Ознакомьтесь со следующими статьями о предварительных требованиях и способах взаимодействия групп с другими технологиями.

- Если ваша организация не развернула рабочие нагрузки Microsoft 365 или Office 365, ознакомьтесь со [статьей начало работы](https://support.office.com/article/Get-started-with-Office-365-for-Business-d6466f0d-5d13-464a-adcb-00906ae87029).

- Если ваша организация не добавила или не настроила проверенный домен для Microsoft 365 или Office 365, ознакомьтесь с разделами [вопросы и ответы о доменах](https://support.office.com/article/Verify-your-Office-365-domain-to-prove-ownership-nonprofit-or-education-status-or-to-activate-Yammer-87d1844e-aa47-4dc0-a61b-1b773fd4e590).

- Если ваша организация не синхронизирует удостоверения с Azure Active Directory, ознакомьтесь с [моделями удостоверений и проверкой подлинности в Microsoft Teams](identify-models-authentication.md).

- Если в вашей организации нет Exchange Online, ознакомьтесь [со сведениями о взаимодействии Exchange и Microsoft Teams](Exchange-Teams-interact.md).

- Если в вашей организации нет SharePoint Online, ознакомьтесь [со сведениями о том, как SharePoint Online и OneDrive для бизнеса могут взаимодействовать с Microsoft Teams](SharePoint-OneDrive-interact.md).

- Сведения о [взаимодействии групп microsoft 365 и Microsoft Teams](Office-365-groups.md).

- Если ваша организация является образовательным учреждением и вы используете информационную систему учащихся, ознакомьтесь со сведениями о [Microsoft School Data Sync](https://docs.microsoft.com/schooldatasync) перед развертыванием Microsoft Teams.

- Если ваша организация рассматривает параметры звонков по коммутируемой телефонной сети, ознакомьтесь со сведениями о [телефонном звонке и PSTN](cloud-voice-landing-page.md), о том, [какой тарифный план вам подойдет для вас](calling-plan-landing-page.md), и [прямую маршрутизацию на телефонную систему](direct-routing-landing-page.md).

- Чтобы убедиться в том, что все сетевые требования выполнены перед развертыванием групп, ознакомьтесь со статьей [Подготовка сети организации для Microsoft Teams](prepare-network.md).

Убедившись в том, что ваша среда отвечает всем применимым требованиям, [оцените текущую среду для Teams](upgrade-plan-journey-evaluate-environment.md).
