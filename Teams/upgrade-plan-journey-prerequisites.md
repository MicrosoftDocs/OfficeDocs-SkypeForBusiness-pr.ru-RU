---
title: Необходимые условия для Microsoft Teams | Обновление внедрения зависимостей
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: dearbeen
audience: admin
description: В этой статье описаны требования и зависимости окружающей среды для развертывания групп в Организации
localization_priority: Normal
search.appverid: MET150
ms.custom: Teams-upgrade-guidance
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 0da49178a55cc14b98946beb7212a1627829c13e
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/07/2019
ms.locfileid: "36236078"
---
![Обновление схемы поездки с акцентом на этапе технической подготовки] (media/upgrade-banner-tech-readiness.png "Этапы путешествия по обновлению с акцентом на этапе технической подготовки")

Эта статья относится к техническому этапу подготовки к обновлению, действиям, завершенным параллельно с этапом готовности пользователей. Прежде чем продолжить, подтвердите, что вы выполнили следующие действия из предыдущих стадий.

- [Вовлеченные заинтересованные лица в проект](upgrade-enlist-stakeholders.md)
- [Определение области охвата проекта](https://aka.ms/SkypetoTeams-Scope)
- [Сосуществование и взаимодействие Skype для бизнеса и рабочих групп](https://aka.ms/SkypeToTeams-Coexist)
- [Выбрано путешествие с обновлением](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)

# <a name="prerequisites-and-environmental-dependencies-for-teams"></a>Требования и зависимости окружающей среды для Teams

В Teams объединены несколько служб Office 365, поэтому они зависят от правильной реализации и функционирования этих служб. Эти службы включают (но не ограничиваются) SharePoint Online, Exchange Online и OneDrive для бизнеса.

Несмотря на то, что требуется не все службы, мы настоятельно рекомендуем вам реализовать все. Если вы решили не применять определенные службы, это повлияет на функциональность, которую Teams может предложить вашей организации. Например, несмотря на то, что вам не нужно реализовывать SharePoint Online, в Teams для выполнения определенных функций, таких как обмен файлами в групповых беседах, в SharePoint Online используются некоторые функции, поэтому не реализация этой службы сокращает возможности, предоставляемые с помощью клиентами.

Ознакомьтесь со следующими статьями о предварительных требованиях и способах взаимодействия групп с другими технологиями.

- Если в вашей организации не развернуто ни одной рабочей нагрузки Office 365, ознакомьтесь [с раздел Начало работы с office 365 для бизнеса](https://support.office.com/article/Get-started-with-Office-365-for-Business-d6466f0d-5d13-464a-adcb-00906ae87029).

- Если ваша организация не добавила или не настроила проверенный домен для Office 365, ознакомьтесь со сведениями о том, как [проверить свой домен office 365](https://support.office.com/article/Verify-your-Office-365-domain-to-prove-ownership-nonprofit-or-education-status-or-to-activate-Yammer-87d1844e-aa47-4dc0-a61b-1b773fd4e590).

- Если ваша организация не синхронизирует удостоверения с Azure Active Directory, ознакомьтесь с [моделями удостоверений и проверкой подлинности в Microsoft Teams](identify-models-authentication.md).

- Если в вашей организации не удается найти Exchange Online, ознакомьтесь [со сведениями о взаимодействии Exchange и Microsoft Teams](Exchange-Teams-interact.md).

- Если в вашей организации нет SharePoint Online, ознакомьтесь [со сведениями о том, как SharePoint Online и OneDrive для бизнеса могут взаимодействовать с Microsoft Teams](SharePoint-OneDrive-interact.md).

- Сведения о [взаимодействии групп Office 365 и Microsoft Teams](Office-365-groups.md).

- Если ваша организация — образовательное учреждение и вы используете информационную систему учащихся, выполните [развертывание School Data Sync](https://docs.microsoft.com/schooldatasync) перед развертыванием Microsoft Teams.

Убедившись в том, что ваша среда отвечает всем применимым требованиям, [оцените текущую среду для Teams](upgrade-plan-journey-evaluate-environment.md).
