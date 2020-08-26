---
title: Управление доступом на основе ролей с помощью службы Microsoft Teams в комнате Premium
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: altsou
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Сведения об управлении доступом на основе ролей с помощью управляемой службы комнат Microsoft Teams.
f1keywords: ''
ms.openlocfilehash: ec8bb770f1dd843c569a98dd909c87ef3ca14dd0
ms.sourcegitcommit: d1e4e1105d86745009cf0fdf42d1fc5ad545a952
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/18/2020
ms.locfileid: "46788791"
---
# <a name="role-based-access-control-with-the-microsoft-teams-rooms-managed-service"></a>Управление доступом на основе ролей с помощью управляемой службы комнат Microsoft Teams

Управление доступом на основе ролей (RBAC) в управляемой службе комнат Microsoft Teams помогает управлять доступом пользователей к данным о ресурсах комнаты в Организации. Назначая роли пользователям портала обслуживания, вы можете ограничить их возможности просмотра и изменения. У каждой роли есть набор разрешений, которые определяют, какие пользователи могут получить доступ к этой роли и изменить ее в Организации.

Для создания, изменения или назначения ролей ваша учетная запись должна иметь одно из следующих разрешений:

- Глобальный администратор через Azure Active Directory (Azure AD)
- Управляемый администратор служб на портале управляемых служб комнат Microsoft Teams

## <a name="what-is-a-role"></a>Что такое роль?

Роль определяет набор разрешений, предоставленных пользователям, которым назначена эта роль. Пока у управляемой службы комнат Microsoft Teams есть три встроенные роли: **Администратор управляемых служб**, **ведущий сотрудник**и веб- **сайт**. Они охватывают некоторые распространенные сценарии для пользователей в вашей организации, которые могут быть вовлечены в Управление комнатами.

Чтобы просмотреть роли, в левой области навигации на портале управляемых служб Microsoft Teams откройте вкладку **роли**и выберите любую роль, чтобы просмотреть свойства, разрешения и назначения роли.  

- **Свойства**: имя, тип роли и описание
- **Разрешения**: перечисляет возможности и уровни разрешений, доступ к которым у роли.
- **Задания**: список назначений ролей, определяющих пользователей с настроенными разрешениями в рамках учетных записей ресурсов комнаты. Роль может иметь несколько назначений, и пользователь может находиться в нескольких назначениях.

## <a name="built-in-roles"></a>Встроенные роли

Вы можете назначать встроенные роли группам или пользователям без дополнительной настройки. Имейте в виду, что вы не можете удалить или изменить имя, описание, тип или разрешения встроенной роли.

- **Управляемый администратор служб**: имеет полный доступ к порталу обслуживания в комнате Microsoft Teams Premium.
- **Ведущий сотрудник сайта**: организует помещения, имеет доступ к отчетам и может управлять билетами. Не удается сбросить регистрационный ключ или изменить конфигурацию службы.  
- **Техническая поддержка по сайту**— Управление билетами для определенных комнат. У вас нет разрешений на изменение службы или организацию комнат в службе.

В таблице ниже приведены сведения о возможностях каждой роли.

|Функции |PermissionSet |Управляемый администратор служб  |Ведущий сотрудник сайта  |Техническая поддержка по сайту  |
|---------|---------|---------|---------|---------|
|Помещений     |Просмотр        |&#10004;           |&#10004;           |&#10004;  |
|    |Внести         |&#10004;           |&#10004;           |&#10004; |
|    |Клавиша сброса         |&#10004;           |         ||
|    |Скачать ключ         |&#10004;           |&#10004;          |&#10004; |
|    |Отмена регистрации         |&#10004;           |&#10004;           |&#10004; |
|Управление группами   |Создать         |&#10004;           |&#10004;           ||
|    |Просмотр       |&#10004;          |&#10004;           ||
|    |Внести         |&#10004;           |&#10004;           ||
|Обновление управления звонками    |Создать         |&#10004;           |&#10004;           ||
|    |Просмотр         |&#10004;           |&#10004;           ||
|    |Внести         |&#10004;           |&#10004;           ||
|Об   |Просмотр        |&#10004;           |&#10004;           ||
|Управление билетами   |Создание инцидента клиента         |&#10004;           |&#10004;           |&#10004;  |
|    |Просмотр         |&#10004;           |&#10004;           |&#10004;  |
|    |Обновление         |&#10004;           |&#10004;           |&#10004;  |
|Параметры управляемых служб в комнатах Microsoft Teams    |Просмотр         |&#10004;           |         ||
|    |Внести        |&#10004;           |         ||
|Управление ролями    |Просмотр         |&#10004;           |         ||
|    |Внести         |&#10004;           |         ||

## <a name="assign-a-role"></a>Назначение роли

Для назначения ролей вы должны быть глобальным администратором или администратором управляемой службы.

1. В левой области навигации на портале управляемых служб комнат Microsoft Teams перейдите в раздел **роли**.

    :::image type="content" source="../media/microsoft-teams-rooms-premium-roles.png" alt-text="Снимок экрана: страница управления доступом, на которой показаны роли":::

2. Выберите роль, которую вы хотите назначить.
3. В области роль выберите пункт Добавить **назначения**  >  **Add**.

    :::image type="content" source="../media/microsoft-teams-rooms-premium-role-assignments.png" alt-text="Снимок экрана: команда "Добавить" для добавления роли.":::

4. На странице " **Общие параметры** " в разделе **свойства назначения**введите имя для этого задания. Описание не является обязательным. Нажмите кнопку **Далее.**
5. На странице " **Участники** " в поле " **Поиск пользователей или групп безопасности** " введите имя пользователя или группы безопасности в клиенте, которому вы хотите предоставить разрешения, а затем завершите выбор. Нажмите кнопку **Далее**. 
6. На странице **область** в поле **Поиск помещения или комнаты** введите имя группы, в которой будет разрешено управлять этим пользователем. Нажмите кнопку **Далее**.
7. На странице **"завершение"** проверьте сведения о назначении. Если вы удовлетворены конфигурацией, нажмите кнопку **добавить назначение**. Если вы хотите изменить раздел, нажмите кнопку **назад** или выберите шаг на панели навигации слева.  

## <a name="related-topics"></a>Статьи по теме

- [Управляемая служба комнат Microsoft Teams](microsoft-teams-rooms-premium.md)