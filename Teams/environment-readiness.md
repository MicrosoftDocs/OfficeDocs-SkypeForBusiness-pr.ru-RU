---
title: Проверка готовности среды для Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 5/11/2018
ms.topic: article
ms.service: msteams
ms.reviewer: dansteve
description: Сведения о проверке готовности среды для Microsoft Teams.
localization_priority: Normal
search.appverid: MET150
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 1794b87beb1c6b1f1e499c214cde8d3e0b9b0a34
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "32235407"
---
<a name="check-your-environments-readiness-for-microsoft-teams"></a>Проверка готовности среды для Microsoft Teams
===========================================

Каждая организация переходит в облако по-своему, а текущее состояние среды может влиять на работу Teams.

Учебные заведения, настоятельно рекомендуется для [развертывания синхронизации данных School](https://docs.microsoft.com/schooldatasync/) перед развертыванием группами Майкрософт. Синхронизация данных School использует данные участников SIS вашей школы для автоматического создания классов и группы для групп Майкрософт и другими приложениями.

Чтобы обеспечить оптимальное взаимодействие с Teams, вашей организации следует сначала развернуть Exchange Online и SharePoint Online. Также необходимо убедиться, что текущая среда готова для групп.  Ссылаться на эти ссылки для получения справки:

-   Если ваша организация не развернула никакие рабочие нагрузки Office 365, см. статью [Приступая к работе с Office 365 бизнес](https://support.office.com/article/Get-started-with-Office-365-for-Business-d6466f0d-5d13-464a-adcb-00906ae87029).

-   Если ваша организация не добавила или не настроила проверенный домен для Office 365, см. статью [Проверка домена Office 365](https://support.office.com/article/Verify-your-Office-365-domain-to-prove-ownership-nonprofit-or-education-status-or-to-activate-Yammer-87d1844e-aa47-4dc0-a61b-1b773fd4e590).

-   Если ваша организация не синхронизировала удостоверения в Azure Active Directory, см. статью [Модели удостоверений и проверка подлинности в Microsoft Teams](identify-models-authentication.md).

-   Если ваша организация не использует Exchange Online, см. статью [Взаимодействие Exchange и Microsoft Teams](Exchange-Teams-interact.md).

-   Если ваша организация не использует SharePoint Online, см. статью [Взаимодействие SharePoint Online и OneDrive для бизнеса с Microsoft Teams](SharePoint-OneDrive-interact.md).

- Если ваша организация заведения и использовать учебы сведения о системе (SIS), [Развертывание синхронизации данных School](https://docs.microsoft.com/schooldatasync/) перед развертыванием группами Майкрософт.

- Если в вашей организации есть существующих Скайп локального развертывания Business Server (или Lync Server), необходимо настроить подключение Azure AD для синхронизации локального каталога с Office 365.  Для получения дополнительных сведений см [Настройка Azure AD для групп и Скайп для бизнеса](https://docs.microsoft.com/en-us/skypeforbusiness/hybrid/configure-azure-ad-connect).