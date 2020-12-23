---
title: Модели удостоверений и проверка подлинности для Microsoft Teams
author: MSFTTracyP
ms.author: tracyp
manager: dansimp
ms.date: 09/25/2020
ms.topic: reference
ms.service: msteams
ms.reviewer: anwara
audience: admin
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
description: Узнайте о различных моделях удостоверений для Microsoft Teams, таких как облачные и гибридные. а также о многофакторной проверке подлинности.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 40a06ce75c3ae7a4f85eb1c93064ba3d80c13fc0
ms.sourcegitcommit: a28232f16bfefe6414d1f5a54d5f8c8665eb0e23
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/25/2020
ms.locfileid: "48277119"
---
# <a name="identity-models-and-authentication-for-microsoft-teams"></a>Модели удостоверений и проверка подлинности для Microsoft Teams

Microsoft Teams поддерживает все модели удостоверений, доступные в Microsoft 365 и Office 365, в том числе:

- **Только в облаке:** учетные записи пользователей создаются и управляются в Microsoft 365 или Office 365 и хранятся в Azure Active Directory (Azure AD). Учетные данные пользователя (имя учетной записи и пароль) проверяются службой Azure AD.

- **Гибридное:** управление учетными записями пользователей обычно происходит в локальном лесу доменных служб Active Directory (AD DS). В зависимости от конфигурации проверку учетных данных может сделать Azure AD, AD DS или федерационный поставщик удостоверений. Эта модель использует синхронизацию службы каталогов из AD DS с Azure AD с Azure AD Connect.

Дополнительные сведения см. в моделях [удостоверений Microsoft 365 и Службе Azure AD.](https://docs.microsoft.com/microsoft-365/enterprise/about-microsoft-365-identity)

## <a name="configurations"></a>Конфигурации

В зависимости от решений организации относительно используемой модели и конфигурации удостоверений действия по внедрению могут различаться.

Если вы еще не развернули Microsoft 365 или Office 365 и модель удостоверений, используйте эту таблицу. 

|Модель удостоверений |Контрольный список развертывания  |Дополнительная информация  |
|---------|---------|---------|
|Все     |<ol type="1"><li>Сравните варианты планов Microsoft 365 и Office 365 и получите подписку и клиент.</li><li>Создайте организацию Microsoft 365 или Office 365 для своего клиента.</li><li>Приобретение лицензий Microsoft 365 или Office 365 для клиента</li><li>Настройте домены и учетные записи администраторов.</li></ol>  |<ul><li>[Варианты плана Office 365](https://technet.microsoft.com/library/office-365-plan-options.aspx)</li><li>[Сравнение планов Microsoft 365 для бизнеса](https://go.microsoft.com/fwlink/?linkid=854617)</li><li>[Покупка и удаление лицензий подписки](https://support.office.com/article/Buy-licenses-for-your-Office-365-for-business-subscription-36081d8d-b3fa-4948-8c34-e217bba825e1)</li><li>[Добавление лицензий в подписку](https://support.office.com/article/Add-licenses-to-a-subscription-paid-for-using-a-product-key-4fb4bd7e-3920-4ce0-98fb-0c06e3fedf53)</li><li>[Настройка Microsoft 365 для бизнеса](https://support.office.com/Article/set-up-Office-365-for-business-6a3a29a0-e616-4713-99d1-15eda62d04fa)</li><li>[Добавление домена с помощью мастера настройки](https://support.office.com/article/Add-users-and-domain-with-the-setup-wizard-6383f56d-3d09-4dcb-9b41-b5f5a5efd611)</li></ul><br>[Служба Microsoft FastTrack](https://www.microsoft.com/fasttrack/microsoft-365) поможет вам.  |
|Облачные удостоверения     |<ul><li>Создание учетных записей пользователей в Центре администрирования Microsoft 365</li></ul> |<ul style="list-style-type:none"><li>[Добавление пользователей и назначение лицензий](https://support.office.com/article/Add-users-individually-or-in-bulk-to-Office-365-Admin-Help-1970f7d6-03b5-442f-b385-5880b9c256ec)</li></ul> |
|Гибридные удостоверения     |<ol type="1"><li>Установите Azure AD Connect.</li><li>Настройте синхронизацию каталогов.</li><li>Управляйте пользователями и группами с помощью средств AD DS.</li></ol> |<ul style="list-style-type:none"><li>[Настройка синхронизации каталогов](https://docs.microsoft.com/microsoft-365/enterprise/set-up-directory-synchronization)</li></ul> |
|Гибридное удостоверение с федерацией проверки подлинности    |<ol type="1"><li>Установите и настройте федератетного поставщика удостоверений, например AD FS.</li><li>Установите Azure AD Connect и настройте синхронизацию службы каталогов и федерационную проверку подлинности.</li><li>Управляйте пользователями и группами с помощью средств AD DS.</li></ol> |<ul><li>[Планирование развертывания AD FS](https://go.microsoft.com/fwlink/?linkid=854619)</li><li>[Контрольный список: Развертывание фермы серверов федерации](https://go.microsoft.com/fwlink/?linkid=854620)</li><li>[Настройка доступа к экстрасети для AD FS](https://go.microsoft.com/fwlink/?linkid=854621)</li><li>[Настройка доверия между AD FS и Azure AD](https://go.microsoft.com/fwlink/?linkid=854622)</li><li>[Проверка единого доступа и управление им с помощью ADFS](https://go.microsoft.com/fwlink/?linkid=854624)</li><li>[Настройка синхронизации каталогов](https://docs.microsoft.com/microsoft-365/enterprise/set-up-directory-synchronization)</li></ul> |
||||

## <a name="multi-factor-authentication"></a>Многофакторная проверка подлинности

Пароли — это наиболее распространенный способ проверки подлинности при входе на компьютер или в веб-службу, но они также наиболее уязвимы. Люди могут выбирать простые пароли и использовать один и тот же пароль для нескольких входов на разные компьютеры и в разные службы. 

Чтобы обеспечить дополнительный уровень безопасности при входе в систему, используйте многофакторную проверку подлинности (MFA), которая требует как пароля, так и дополнительного способа проверки, например:

- Текстовое сообщение, отправленное на телефон, в которое пользователь должен ввести код проверки.
- Телефонный звонок.
- Приложение Microsoft Authenticator для смартфонов.
- Другие способы, доступные при гибридных удостоверениях и федераированной проверке подлинности.

MFA поддерживается в любом плане Microsoft 365 или Office 365, который включает Microsoft Teams. Настоятельно рекомендуется как минимум требовать многофаксную оценку для [](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles?view=o365-worldwide)учетных записей, которые назначены роли администратора, например для администраторов служб Teams.

Кроме того, следует разо свернуть многофайтовую статью для пользователей. После регистрации пользователей в многофаксной проверке данных при следующем входе они увидят сообщение с запросом на настройка дополнительного способа проверки. 

Дополнительные сведения см. в [многофакторной проверке подлинности для Microsoft 365.](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/multi-factor-authentication-microsoft-365)
