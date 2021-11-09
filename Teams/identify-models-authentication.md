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
ms.localizationpriority: medium
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
description: Узнайте о различных моделях удостоверений для Microsoft Teams, таких как облачные и гибридные. а также о многофакторной проверке подлинности.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: c12e7242241c8c6d7ac03bc3c66804198acd746e
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/08/2021
ms.locfileid: "60836067"
---
# <a name="identity-models-and-authentication-for-microsoft-teams"></a>Модели удостоверений и проверка подлинности для Microsoft Teams

Microsoft Teams поддерживает все модели удостоверений, доступные в Microsoft 365 и Office 365, в том числе:

- **Только в облаке:** учетные записи пользователей создаются и управляются в Microsoft 365 или Office 365 и хранятся в Azure Active Directory (Azure AD). Учетные данные пользователя для входа (имя учетной записи и пароль) проверяются службой Azure AD.

- **Гибридное** гибридное управление учетными записями пользователей обычно происходит в локальном лесу доменных служб Active Directory (AD DS). В зависимости от конфигурации проверку учетных данных может сделать Azure AD, AD DS или федерарная служба удостоверений. В этой модели используется синхронизация службы каталогов AD DS с Azure AD с azure AD Подключение.

Дополнительные сведения см. в Microsoft 365 [удостоверений и Azure AD.](/microsoft-365/enterprise/about-microsoft-365-identity)

## <a name="configurations"></a>Конфигурации

В зависимости от того, какую модель и конфигурацию удостоверений вы используете в организации, действия по внедрению могут различаться.

Если вы еще не развернули Microsoft 365 или Office 365 и модель удостоверений, воспользуйтесь этой таблицей. 

|Модель удостоверений |Контрольный список развертывания  |Дополнительная информация  |
|---------|---------|---------|
|Все     |<ol type="1"><li>Сравните Microsoft 365 и Office 365 плана и получите подписку и клиент.</li><li>Создайте Microsoft 365 или Office 365 для своего клиента.</li><li>Приобретение Microsoft 365 Office 365 лицензий для клиента</li><li>Настройка доменов и учетных записей администраторов.</li></ol>  |<ul><li>[Office 365 плана](/office365/servicedescriptions/office-365-platform-service-description/office-365-plan-options)</li><li>[Сравнение Microsoft 365 планов для бизнеса](https://go.microsoft.com/fwlink/?linkid=854617)</li><li>[Покупка и удаление лицензий на подписку](https://support.office.com/article/Buy-licenses-for-your-Office-365-for-business-subscription-36081d8d-b3fa-4948-8c34-e217bba825e1)</li><li>[Добавление лицензий в подписку](https://support.office.com/article/Add-licenses-to-a-subscription-paid-for-using-a-product-key-4fb4bd7e-3920-4ce0-98fb-0c06e3fedf53)</li><li>[Настройка Microsoft 365 для бизнеса](https://support.office.com/Article/set-up-Office-365-for-business-6a3a29a0-e616-4713-99d1-15eda62d04fa)</li><li>[Добавление домена с помощью мастера настройки](https://support.office.com/article/Add-users-and-domain-with-the-setup-wizard-6383f56d-3d09-4dcb-9b41-b5f5a5efd611)</li></ul><br>[Служба FastTrack](https://www.microsoft.com/fasttrack/microsoft-365) майкрософт доступна для оказания помощи.  |
|Облачные удостоверения     |<ul><li>Создание учетных записей пользователей с помощью Центр администрирования Microsoft 365</li></ul> |<ul><li>[Добавление пользователей и назначение лицензий](https://support.office.com/article/Add-users-individually-or-in-bulk-to-Office-365-Admin-Help-1970f7d6-03b5-442f-b385-5880b9c256ec)</li></ul> |
|Гибридное удостоверение     |<ol type="1"><li>Установите Azure AD Подключение.</li><li>Настройка синхронизации каталогов.</li><li>Управляйте пользователями и группами с помощью средств AD DS.</li></ol> |<ul><li>[Настройка синхронизации каталогов](/microsoft-365/enterprise/set-up-directory-synchronization)</li></ul> |
|Гибридное удостоверение с федерацией проверки подлинности    |<ol type="1"><li>Установите и настройте федераированный поставщик удостоверений, например AD FS.</li><li>Установите Azure AD Подключение и настройте синхронизацию службы каталогов и федерационную проверку подлинности.</li><li>Управляйте пользователями и группами с помощью средств AD DS.</li></ol> |<ul><li>[Планирование развертывания AD FS](/previous-versions/azure/azure-services/dn151324(v=azure.100))</li><li>[Контрольный список: Развертывание фермы серверов федерации](/previous-versions/azure/azure-services/dn528856(v=azure.100))</li><li>[Настройка доступа к экстрасети для AD FS](/previous-versions/azure/azure-services/dn528859(v=azure.100))</li><li>[Настройка доверия между AD FS и Azure AD](/previous-versions/azure/azure-services/jj205461(v=azure.100))</li><li>[Проверка единого доступа и управление им с помощью ADFS](/previous-versions/azure/azure-services/jj151809(v=azure.100))</li><li>[Настройка синхронизации каталогов](/microsoft-365/enterprise/set-up-directory-synchronization)</li></ul> |
||||

## <a name="multi-factor-authentication"></a>Многофакторная проверка подлинности

Пароли — это самый распространенный способ проверки подлинности при входе в компьютер или веб-службу, но они также наиболее уязвимы. Люди могут выбирать простые пароли и использовать одинаковые пароли для нескольких входов на разные компьютеры и службы. 

Чтобы обеспечить дополнительный уровень безопасности для входов, используйте многофакторную проверку подлинности (MFA), которая требует как пароля, так и дополнительного способа проверки, например:

- Текстовое сообщение, отправленное на телефон, в которое пользователь должен ввести проверочные коды.
- Телефонный звонок.
- Приложение Microsoft Authenticator смартфона.
- Другие способы, доступные при гибридной идентификации и федерационной проверке подлинности.

MFA поддерживается для Microsoft 365 или Office 365, который включает Microsoft Teams. Настоятельно рекомендуется как минимум требовать многофаксную оценку для [](/microsoft-365/admin/add-users/about-admin-roles)учетных записей, для которых назначены роли администратора, например для Teams службы.

Кроме того, следует разо свернуть многофаку для пользователей. После регистрации пользователей в многофаксной проверке при следующем входе они увидят сообщение с запросом на настройка дополнительного способа проверки. 

Дополнительные сведения см. в [этой](/microsoft-365/admin/security-and-compliance/multi-factor-authentication-microsoft-365)Microsoft 365.