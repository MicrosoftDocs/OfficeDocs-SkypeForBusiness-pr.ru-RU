---
title: Модели удостоверений и проверка подлинности
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/25/2017
ms.topic: reference
ms.service: msteams
ms.reviewer: anach
audience: admin
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
description: Сведения о различных моделях удостоверений в Microsoft Teams, таких как облачная, синхронизированная и федеративная, а также о многофакторной проверке подлинности.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 6c32783b96e5fdfe8c0f783a0fd27fd58a7f04c1
ms.sourcegitcommit: f586d2765195dbd5b7cf65615a03a1cb098c5466
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/09/2020
ms.locfileid: "44665681"
---
<a name="identity-models-and-authentication-in-microsoft-teams"></a>Модели удостоверений и проверка подлинности в Microsoft Teams
==========================================

Microsoft Teams поддерживает все модели удостоверений, доступные в Microsoft 365 и Office 365. К ним относятся следующие.

-   **Облачное удостоверение**: в этой модели пользователь создается и управляется в Microsoft 365 или Office 365 и хранится в Azure Active Directory, и пароль проверяются службой Azure Active Directory.

-   **Синхронизированное удостоверение**: удостоверение пользователя управляется на локальном сервере, а учетные записи и хэши паролей синхронизируются в облако. Пользователь вводит в локальной среде тот же пароль, что и в облаке, а при входе пароль проверяется в Azure Active Directory. Эта модель использует средство Microsoft Azure Active Directory Connect.

-   **Федеративное удостоверение**: синхронизированное удостоверение с паролем пользователя должно проверяться локальным поставщиком удостоверений. В этой модели хэш пароля не требуется синхронизировать с Azure AD, а для проверки подлинности пользователя в локальном Active Directory используются службы федерации Active Directory (AD FS).

<a name="configurations"></a>Конфигурации
--------------

Требования к реализации могут различаться в зависимости от того, какие модели идентификации необходимо реализовать и использовать в Организации. Чтобы убедиться в соблюдении предварительных условий для развертывания, обратитесь к приведенной ниже таблице с требованиями. Если вы уже развернули Microsoft 365 или Office 365 и уже реализовали этот метод идентификации и проверки подлинности, вы можете пропустить эти действия.


|Модель удостоверений |Контрольный список развертывания  |Дополнительная информация  |
|---------|---------|---------|
|Все     |<ol type="1"><li>Сравните параметры плана Microsoft 365 и Office 365 и получите подписку.</li><li>Создание организации Microsoft 365 или Office 365</li><li>Назначение лицензий Microsoft 365 или Office 365 клиенту</li><li>Настройте домены и администраторов</li><li>Следуйте инструкциям для конкретной модели удостоверений</li></ol>          |<ul style="list-style-type:none"><li>[Параметры плана Microsoft 365 и Office 365](https://technet.microsoft.com/library/office-365-plan-options.aspx)</li><li>[Сравнение приложений Microsoft 365 для бизнес-планов](https://go.microsoft.com/fwlink/?linkid=854617)</li><li>[Управление лицензиями на подписку](https://support.office.com/article/Buy-licenses-for-your-Office-365-for-business-subscription-36081d8d-b3fa-4948-8c34-e217bba825e1)</li><li>[Добавление лицензий в подписку](https://support.office.com/article/Add-licenses-to-a-subscription-paid-for-using-a-product-key-4fb4bd7e-3920-4ce0-98fb-0c06e3fedf53)</li><li>[Настройка Microsoft 365 для бизнеса](https://support.office.com/Article/set-up-Office-365-for-business-6a3a29a0-e616-4713-99d1-15eda62d04fa)</li><li>[Добавление пользователей и домена с помощью мастера установки](https://support.office.com/article/Add-users-and-domain-with-the-setup-wizard-6383f56d-3d09-4dcb-9b41-b5f5a5efd611)</li><li>Примечание: Если вам нужна помощь, обратитесь [в службу поддержки Microsoft FastTrack](https://go.microsoft.com/fwlink/?linkid=854618) .</li></ul>          |
|Облачное удостоверение     |<ol type="1"><li>Создание пользователей с помощью центра администрирования Microsoft 365</li></ol>           |<ul style="list-style-type:none"><li>[Добавление пользователей по отдельности или массово](https://support.office.com/article/Add-users-individually-or-in-bulk-to-Office-365-Admin-Help-1970f7d6-03b5-442f-b385-5880b9c256ec)</li></ul>         |
|Синхронизированное удостоверение     |<ol type="1"><li>Установите Azure AD Connect</li><li>Настройте синхронизацию службы каталогов</li><li>Создайте пользователей с помощью средств управления локальной версии Active Directory</li></ol>         |<ul style="list-style-type:none"><li>[Настройка синхронизации службы каталогов](https://support.office.com/article/Set-up-directory-synchronization-for-Office-365-1b3b5318-6977-42ed-b5c7-96fa74b08846)</li><li>Примечание. хэши паролей должны быть синхронизированы для Microsoft 365 и Office 365 для проверки подлинности.</li></ul>         |
|Федеративное удостоверение    |<ol type="1"><li>Установите Azure AD Connect</li><li>Настройте синхронизацию службы каталогов</li><li>Установите и настройте поставщик федеративных удостоверений (рекомендуются службы ADFS)</li><li>Создайте пользователей с помощью средств управления локальной версии Active Directory</li></ol>           |<ul style="list-style-type:none"><li>[Настройка синхронизации службы каталогов](https://support.office.com/article/Set-up-directory-synchronization-for-Office-365-1b3b5318-6977-42ed-b5c7-96fa74b08846)</li><li>[Планирование развертывания AD FS](https://go.microsoft.com/fwlink/?linkid=854619)</li><li>[Контрольный список: Развертывание фермы серверов федерации](https://go.microsoft.com/fwlink/?linkid=854620)</li><li>[Настройка доступа к экстрасети для AD FS](https://go.microsoft.com/fwlink/?linkid=854621)</li><li>[Настройка доверия между AD FS и Azure AD](https://go.microsoft.com/fwlink/?linkid=854622)</li><li>[Проверка единого доступа и управление им с помощью ADFS](https://go.microsoft.com/fwlink/?linkid=854624)</li><li>[Список совместимости для федерации Azure AD](https://go.microsoft.com/fwlink/?linkid=854625)</li><li>Примечание. Хэши паролей не требуется синхронизировать с Azure Active Directory.</li></ul>         |

Дополнительные сведения можно найти в разделе [Выбор модели входа](https://go.microsoft.com/fwlink/?linkid=854626) и [понимания моделей удостоверений и руководств по Azure Active Directory](https://support.office.com/article/Understanding-Office-365-identity-and-Azure-Active-Directory-06a189e7-5ec6-4af2-94bf-a22ea225a7a9) .


<a name="multi-factor-authentication"></a>Многофакторная проверка подлинности
----------------------------

Планы Microsoft 365 и Office 365 поддерживают многофакторную проверку подлинности (MFA), которая повышает безопасность имен пользователей для служб. С помощью MFA пользователи обязаны подтверждать телефонный звонок, текстовое сообщение или уведомление приложения на смартфоне после правильного ввода пароля. Вход выполняется только после подтверждения подлинности с помощью этого второго фактора.

Многофакторная проверка подлинности поддерживается любым планом Microsoft 365 или Office 365, включающим Microsoft Teams. Планы подписки, включающие Microsoft Teams, обсуждаются далее в разделе лицензирования ниже.

После того как пользователи будут зарегистрированы на MFA, при следующем входе пользователя будет выводится сообщение о том, как настроить второй фактор проверки подлинности. Поддерживаемые методы проверки подлинности:


|Тип клиента  |Доступные вторые факторы MFA  |Примечания  |
|---------|---------|---------|
|**Только в облаке**     |MFA для Microsoft 365 или Office 365 <ul><li>Телефонный звонок</li><li>SMS</li><li>Уведомление в мобильном приложении</li><li>Код проверки в мобильном приложении</li></ul>        | |
|**Гибридная установка (синхронизированная или федеративная модель удостоверений)**     |<ul><li>MFA для Microsoft 365 или Office 365</li><li>Модуль Azure MFA (интеграция с ADFS)</li><li>Физическая или виртуальная смарт-карта (интеграция с ADFS)</li></ul>         |Примечание. Дополнительные решения MFA доступны в [документах с совместимостью поставщика удостоверений Azure AD](https://www.microsoft.com/download/details.aspx?id=56843)         |
