---
title: Необходимые условия и окружающей среды зависимостей для групп Майкрософт - группами Майкрософт
author: turgayo
ms.author: turgayo
manager: serdars
ms.date: 07/16/2018
ms.topic: article
ms.service: msteams
ms.reviewer: turgayo
description: Используйте данное руководство, чтобы узнать о необходимых компонентов и окружающей среды зависимости, чтобы развернуть группами в организации
localization_priority: Normal
search.appverid: MET150
ms.custom: Teams-upgrade-guidance
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 7b798ae43d7a47543c78ca38a696a2368413539d
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2018
ms.locfileid: "23887509"
---
![Этапы обновления пути с акцентом на стадии технической готовности] (media/upgrade-banner-tech-readiness.png "Этапы обновления пути с акцентом на стадии технической готовности")

В этой статье является частью технической готовности этапа обновления пути, действия, которые выполнить параллельно с рабочей области готовность пользователей. Прежде чем продолжить, убедитесь, что вы выполните эти действия из предыдущих этапов:

-   [Прикреплено другие заинтересованные стороны проекта](upgrade-enlist-stakeholders.md)
-   [Определенные области проекта](https://aka.ms/SkypetoTeams-Scope)
-   [Поняты сосуществования и взаимодействия Скайп для бизнеса и рабочих групп](https://aka.ms/SkypeToTeams-Coexist)
-   [Выбранные обновления пути](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)

# <a name="prerequisites-and-environmental-dependencies-for-teams"></a>Необходимые условия и окружающей среды зависимостей для групп

Команды объединяет несколько служб Office 365 и таким образом, зависит от правильного внедрения и эксплуатации этих служб. Эти службы включают —, но не ограничиваются ими — SharePoint Online, Exchange Online и OneDrive для бизнеса.

Хотя не все службы необходимы, настоятельно рекомендуется реализовать все из них. Реализовать определенных служб не выбрано, будет влияет на функциональность, команды можно предоставить пользователям организации. Например, на то, что у вас нет для реализации SharePoint Online, группами полагаться на SharePoint Online для некоторых возможностей такие как общий доступ к файлам в беседах группы, поэтому не реализация этой службы повлечет за собой уменьшение функциональные возможности, предоставляемые в клиент.

Обратитесь к следующим документам, чтобы узнать о необходимых условиях и взаимодействие с другими технологиями групп:

-   Если ваша организация еще не развернут любой рабочих нагрузок Office 365, ознакомьтесь со [Приступая к работе с Office 365 для бизнеса](https://support.office.com/article/Get-started-with-Office-365-for-Business-d6466f0d-5d13-464a-adcb-00906ae87029).

-   Если ваша организация еще не добавлена или настроен подтвержденным доменом для Office 365, из раздела [Verify вашему домену Office 365](https://support.office.com/article/Verify-your-Office-365-domain-to-prove-ownership-nonprofit-or-education-status-or-to-activate-Yammer-87d1844e-aa47-4dc0-a61b-1b773fd4e590).

-   Если ваша организация не синхронизирована удостоверения для Azure Active Directory, просмотрите [модели идентификации и проверки подлинности в группах Майкрософт](identify-models-authentication.md).

-   Если doesn¹t вашей организации Exchange Online, просмотрите [Общие сведения о взаимодействие Exchange и группами Майкрософт](Exchange-Teams-interact.md).

-   Если организация не имеет SharePoint Online, видеть [тщательно изучите взаимодействия SharePoint Online и OneDrive для бизнеса с группами Майкрософт](SharePoint-OneDrive-interact.md).

-   Узнайте, как [группы Office 365 и группами Майкрософт взаимодействия](Office-365-groups.md).

-   Если ваша организация заведения и используйте систему сведений учебы, [Развертывание синхронизации данных School](https://docs.microsoft.com/schooldatasync) перед развертыванием группами Майкрософт.
                                                                           

По окончании проверки, что среда соответствует всех соответствующих необходимых компонентов, [оценить текущую среду для групп](upgrade-plan-journey-evaluate-environment.md).