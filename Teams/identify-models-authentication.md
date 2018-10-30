---
title: Модели удостоверений и проверка подлинности в Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
ms.reviewer: anach
localization_priority: Normal
search.appverid: MET150
MS.collection: Teams_ITAdmin_Help
description: Сведения о различных моделях удостоверений в Microsoft Teams, таких как облачная, синхронизированная и федеративная, а также о многофакторной проверке подлинности.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 3425cfac168e65cd062af67f7e05727f2fe5a837
ms.sourcegitcommit: 7d65eafd5b0163ece91deb7801458c7a45fcc4f7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/29/2018
ms.locfileid: "25839137"
---
<a name="identity-models-and-authentication-in-microsoft-teams"></a>Модели удостоверений и проверка подлинности в Microsoft Teams
==========================================

Microsoft Teams поддерживает все модели удостоверений, доступные в Office 365. К ним относятся следующие.

-   **Облачное удостоверение**: пользователь создается и управляется в Office 365, данные хранятся в Azure Active Directory, а пароль проверяется также в Azure Active Directory.

-   **Синхронизированное удостоверение**: удостоверение пользователя управляется на локальном сервере, а учетные записи и хэши паролей синхронизируются в облако. Пользователь вводит в локальной среде тот же пароль, что и в облаке, а при входе пароль проверяется в Azure Active Directory. Эта модель использует средство Microsoft Azure Active Directory Connect.

-   **Федеративное удостоверение**: синхронизированное удостоверение с паролем пользователя должно проверяться локальным поставщиком удостоверений. В этой модели хэш пароля не требуется синхронизировать с Azure AD, а для проверки подлинности пользователя в локальном Active Directory используются службы федерации Active Directory (AD FS).

<a name="configurations"></a>Конфигурации
--------------

Конкретные требования могут различаться в зависимости от того, какую модель удостоверений решает внедрить и использовать ваша организация. Чтобы убедиться в соблюдении предварительных условий для развертывания, обратитесь к приведенной ниже таблице с требованиями. Если вы уже развернули Office 365 и внедрили определенный метод работы с удостоверениями и проверки подлинности, можете пропустить эти действия.


|Модель удостоверений |Контрольный список развертывания  |Дополнительная информация  |
|---------|---------|---------|
|Все     |<ol type="1"><li>Сравните варианты планов Office 365 и получите подписку</li><li>Создайте клиент Office 365</li><li>Назначьте лицензии Office 365 клиенту</li><li>Настройте домены и администраторов</li><li>Следуйте инструкциям для конкретной модели удостоверений</li></ol>          |<ul style="list-style-type:none"><li>[Варианты планов Office 365](https://technet.microsoft.com/library/office-365-plan-options.aspx)</li><li>[Сравнение планов Office 365 бизнес](https://go.microsoft.com/fwlink/?linkid=854617)</li><li>[Покупка лицензий для подписки Office 365 бизнес](https://support.office.com/article/Buy-licenses-for-your-Office-365-for-business-subscription-36081d8d-b3fa-4948-8c34-e217bba825e1)</li><li>[Добавление лицензий в подписку](https://support.office.com/article/Add-licenses-to-a-subscription-paid-for-using-a-product-key-4fb4bd7e-3920-4ce0-98fb-0c06e3fedf53)</li><li>[Настройка Office 365 бизнес](https://support.office.com/Article/set-up-Office-365-for-business-6a3a29a0-e616-4713-99d1-15eda62d04fa)</li><li>[Добавление пользователей и домена с помощью мастера установки](https://support.office.com/article/Add-users-and-domain-with-the-setup-wizard-6383f56d-3d09-4dcb-9b41-b5f5a5efd611)</li><li>Примечание. Если вам требуется помощь, обратитесь к [команде Microsoft FastTrack для Office 365](https://go.microsoft.com/fwlink/?linkid=854618).</li></ul>          |
|Облачное удостоверение     |<ol type="1"><li>Создайте пользователей с помощью портала администрирования Office 365</li></ol>           |<ul style="list-style-type:none"><li>[Одиночное или массовое добавление пользователей в Office 365](https://support.office.com/article/Add-users-individually-or-in-bulk-to-Office-365-Admin-Help-1970f7d6-03b5-442f-b385-5880b9c256ec)</li></ul>         |
|Синхронизированное удостоверение     |<ol type="1"><li>Установите Azure AD Connect</li><li>Настройте синхронизацию службы каталогов</li><li>Создайте пользователей с помощью средств управления локальной версии Active Directory</li></ol>         |<ul style="list-style-type:none"><li>[Настройка синхронизации службы каталогов для Office 365](https://support.office.com/article/Set-up-directory-synchronization-for-Office-365-1b3b5318-6977-42ed-b5c7-96fa74b08846)</li><li>Примечание. Чтобы Office 365 мог проверить подлинность, требуется синхронизировать хэши паролей.</li></ul>         |
|Федеративное удостоверение    |<ol type="1"><li>Установите Azure AD Connect</li><li>Настройте синхронизацию службы каталогов</li><li>Установите и настройте поставщик федеративных удостоверений (рекомендуются службы ADFS)</li><li>Создайте пользователей с помощью средств управления локальной версии Active Directory</li></ol>           |<ul style="list-style-type:none"><li>[Настройка синхронизации службы каталогов для Office 365](https://support.office.com/article/Set-up-directory-synchronization-for-Office-365-1b3b5318-6977-42ed-b5c7-96fa74b08846)</li><li>[Планирование развертывания AD FS](https://go.microsoft.com/fwlink/?linkid=854619)</li><li>[Контрольный список: Развертывание фермы серверов федерации](https://go.microsoft.com/fwlink/?linkid=854620)</li><li>[Настройка доступа к экстрасети для AD FS](https://go.microsoft.com/fwlink/?linkid=854621)</li><li>[Настройка доверия между AD FS и Azure AD](https://go.microsoft.com/fwlink/?linkid=854622)</li><li>[Проверка единого доступа и управление им с помощью ADFS](https://go.microsoft.com/fwlink/?linkid=854624)</li><li>[Список совместимости для федерации Azure AD](https://go.microsoft.com/fwlink/?linkid=854625)</li><li>Примечание. Хэши паролей не требуется синхронизировать с Azure Active Directory.</li></ul>         |

Дополнительные сведения см. в руководствах [Выбор модели входа для Office 365](https://go.microsoft.com/fwlink/?linkid=854626) и [Общие сведения об удостоверении Office 365 и Azure Active Directory](https://support.office.com/article/Understanding-Office-365-identity-and-Azure-Active-Directory-06a189e7-5ec6-4af2-94bf-a22ea225a7a9).

<a name="multi-factor-authentication"></a>Многофакторная проверка подлинности
----------------------------

Планы Office 365 поддерживают многофакторную проверку подлинности (MFA), которая повышает безопасность при входе пользователя в службы Office 365. После ввода правильного пароля пользователю требуется подтвердить его с помощью телефонного звонка, SMS или уведомления в приложении на своем смартфоне. Вход выполняется только после подтверждения подлинности с помощью этого второго фактора.

Настройка проверки подлинности поддерживается в любой план Office 365, которая включает в себя группами Майкрософт. Планы подписки Office 365 с Microsoft Teams указаны ниже в разделе "Лицензирование".

Когда для пользователя активируется MFA, при следующем входе ему предлагается настроить второй фактор проверки подлинности. Поддерживаемые методы проверки подлинности:


|Тип клиента  |Доступные вторые факторы MFA  |Примечания  |
|---------|---------|---------|
|**Только в облаке**     |MFA для Office 365 <ul><li>Телефонный звонок</li><li>SMS</li><li>Уведомление в мобильном приложении</li><li>Код проверки в мобильном приложении</li></ul>        |[План с многофакторной проверкой подлинности для развертываний Office 365](https://support.office.com/article/Plan-for-multi-factor-authentication-for-Office-365-Deployments-043807b2-21db-4d5c-b430-c8a6dee0e6ba)         |
|**Гибридная установка (синхронизированная или федеративная модель удостоверений)**     |<ul><li>MFA для Office 365</li><li>Модуль Azure MFA (интеграция с ADFS)</li><li>Физическая или виртуальная смарт-карта (интеграция с ADFS)</li></ul>         |Примечание. Доступны и другие решения MFA для [поставщиков удостоверений, совместимых с федерацией Azure AD](https://go.microsoft.com/fwlink/p/?LinkId=510953).         |
