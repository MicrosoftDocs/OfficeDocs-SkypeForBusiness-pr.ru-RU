---
title: Проверка готовности среды для Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 5/11/2018
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: dansteve
description: Сведения о проверке готовности среды для Microsoft Teams.
localization_priority: Normal
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: c0609efd8ac0286857b44996939378e57ce2702f
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/07/2019
ms.locfileid: "36234923"
---
<a name="check-your-environments-readiness-for-microsoft-teams"></a>Проверка готовности среды для Microsoft Teams
===========================================

Каждая организация переходит в облако по-своему, а текущее состояние среды может влиять на работу Teams.

Образовательные учреждения настоятельно рекомендуется [развертывать School Data Sync](https://docs.microsoft.com/schooldatasync/) перед развертыванием Microsoft Teams. School Data Sync использует данные подсписка SIS для учебного заведения, чтобы автоматически создавать классы и группы для Microsoft Teams и других приложений.

Чтобы обеспечить оптимальное взаимодействие с Teams, вашей организации следует сначала развернуть Exchange Online и SharePoint Online. Кроме того, необходимо убедиться, что текущая среда готова для Teams.  Дополнительные сведения можно найти по следующим ссылкам:

-   Если ваша организация не развернула никакие рабочие нагрузки Office 365, см. статью [Приступая к работе с Office 365 бизнес](https://support.office.com/article/Get-started-with-Office-365-for-Business-d6466f0d-5d13-464a-adcb-00906ae87029).

-   Если ваша организация не добавила или не настроила проверенный домен для Office 365, см. статью [Проверка домена Office 365](https://support.office.com/article/Verify-your-Office-365-domain-to-prove-ownership-nonprofit-or-education-status-or-to-activate-Yammer-87d1844e-aa47-4dc0-a61b-1b773fd4e590).

-   Если ваша организация не синхронизировала удостоверения в Azure Active Directory, см. статью [Модели удостоверений и проверка подлинности в Microsoft Teams](identify-models-authentication.md).

-   Если ваша организация не использует Exchange Online, см. статью [Взаимодействие Exchange и Microsoft Teams](Exchange-Teams-interact.md).

-   Если ваша организация не использует SharePoint Online, см. статью [Взаимодействие SharePoint Online и OneDrive для бизнеса с Microsoft Teams](SharePoint-OneDrive-interact.md).

- Если ваша организация — образовательное учреждение и вы используете систему информации об учащихся (SIS), выполните [развертывание School Data Sync](https://docs.microsoft.com/schooldatasync/) перед развертыванием Microsoft Teams.

- Если в вашей организации есть локальное развертывание Skype для бизнеса Server (или Lync Server), необходимо настроить Azure AD Connect для синхронизации локального каталога с Office 365.  Дополнительные сведения можно найти в разделе [Настройка Azure AD Connect для Teams и Skype для бизнеса](https://docs.microsoft.com/en-us/skypeforbusiness/hybrid/configure-azure-ad-connect).