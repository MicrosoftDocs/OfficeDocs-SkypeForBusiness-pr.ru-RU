---
title: Общедоступная предварительная версия в Microsoft Teams
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
- m365initiative-deployteams
ms.reviewer: dansteve
search.appverid: MET150
f1.keywords:
- NOCSH
description: Learn about the public preview in Microsoft Teams. Try out new features and provide feedback.
appliesto:
- Microsoft Teams
ms.localizationpriority: high
ms.openlocfilehash: ffdd34d8a36726d96bc44ae766e91ca6ae77280b
ms.sourcegitcommit: b535a70df5bc842f597889582df3eb86371f8139
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/07/2022
ms.locfileid: "68869594"
---
# <a name="microsoft-teams-public-preview"></a>Общедоступная предварительная версия Microsoft Teams

> [!NOTE] 
> Функции, включенные в предварительную версию, могут быть неполными и подвергаться изменениям перед общедоступным выпуском. Они предназначены только для оценки и изучения. Предварительные версии функций не поддерживаются в Office 365 для государственных организаций Community Cloud (GCC).

Public Preview for Microsoft Teams provides early access to unreleased features in Teams. Previews allow you to explore and test upcoming features. We also welcome feedback on any feature in public previews. Public preview is enabled per Team user, so you don't need to worry about affecting your entire organization.

Список доступных в общедоступной предварительной версии Teams см. в [технических заметках о общедоступной предварительной версии Microsoft Teams](https://techcommunity.microsoft.com/t5/microsoft-teams-public-preview/bd-p/MicrosoftTeamsPublicPreview), [заметках о выпуске для Teams Администратор функций](/OfficeUpdates/teams-admin) и [заметках о выпуске для Office Current Channel (предварительная версия)](/officeupdates/current-channel-preview) .

## <a name="set-the-update-policy"></a>Настройка политики обновления

Public preview is enabled on a per-user basis, and the option to turn on public preview is controlled in an admin policy. Update policies are used to manage Teams and Office preview users who will see pre-release or preview features in the Teams app. You can use the Global (Org-wide default) policy and customize it, or create one or more custom policies for your users. The policy needs to be assigned to specific users because it doesn't over-write the global policy.

1. Войдите в [Центр администрирования Microsoft Teams](https://admin.teams.microsoft.com/).

2. Выберите **Teams** > **Политики обновления Teams**.

1. Выберите **Добавить**, чтобы создать новую политику, или выберите существующую политику, чтобы открыть **Политика обновления**.

2. Назовите политику обновления, добавьте описание и выберите параметр для **Показать функции предварительного просмотра**.

   -   **Подписка на предварительную версию Office** (по умолчанию)
       - Этот новый стандартный параметр автоматически включает функции общедоступной предварительной версии Teams для всех пользователей, зарегистрированных в Актуальном канале (предварительная версия) Office. 
       - Конечному пользователю больше не требуется никаких действий.
   -   **Включено**
       - Этот параметр включает общедоступную предварительную версию Teams независимо от того, зарегистрирован ли пользователь в Актуальном канале (предварительная версия) Office. 
       - Конечный пользователь также должен согласиться на общедоступную предварительную версию Teams в своем приложении Teams.

   > [!NOTE]  
   > Для существующих пользователей в общедоступной предварительной версии Teams, которые НЕ включены в **Актуальный канал (предварительная версия)**, ИТ-администраторам необходимо переключиться с параметра по умолчанию **Подписка на предварительную версию Office** на **Включено**.
 
   - **Не включено** 
     - Функции общедоступной предварительной версии Teams будут недоступны для пользователей.

    ![открывается диалоговое окно параметров предварительного просмотра.](media/public-preview-policy.png)  

Политику также можно настроить с помощью командлета PowerShell `Set-CsTeamsUpdateManagementPolicy` с параметром `-AllowPublicPreview`.

## <a name="enable-public-preview"></a>Включение общедоступной предварительной версии

Чтобы включить общедоступную предварительную версию в классическом или веб-клиенте, вам требуется выполнить следующие действия:

1. Выберите три точки слева от профиля, чтобы отобразилось меню Teams.
2. Выберите **О программе** > **Общедоступная предварительная версия**.
3. Выберите **Переключиться на общедоступную предварительную версию**.

> [!NOTE]  
> Этот параметр доступен, только если для параметра **Отображать функции предварительной версии** установлено значение **Включено**.

### <a name="public-preview-for-microsoft-teams-rooms-on-windows"></a>Общедоступный предварительный просмотр Комнат Microsoft Teams в Windows

По умолчанию общедоступный предварительный просмотр отключен. Когда включен общедоступный предварительный просмотр, конечные пользователи имеют доступ к функциям, которые находятся в открытой предварительной версии во включенных Комнатах Teams. Чтобы включить общедоступный предварительный просмотр, добавьте ```<EnablePublicPreview>True</EnablePublicPreview>``` в XML-файл конфигурации.

Мы рекомендуем зарегистрировать 5–10 устройств в общедоступных предварительных версиях. 

Все общедоступные функции предварительной версии объявляются на [Microsoft Teams Public Preview — Сообщество Microsoft Tech Community](https://techcommunity.microsoft.com/t5/microsoft-teams-public-preview/bd-p/MicrosoftTeamsPublicPreview)

## <a name="teams-now-follows-office-preview-users"></a>Teams теперь отслеживает пользователей предварительной версии Office

Новая глобальная политика по умолчанию **Подписка на предварительную версию Office** позволяет пользователям автоматически присоединяться к каналу общедоступной предварительной версии Teams, если они находятся в Актуальном канале (предварительная версия) для клиента Office 365 в Windows.

Microsoft Office будет по-прежнему получать обновления из Актуального канала (предварительная версия), а клиент Teams будет получать обновления через общедоступный канал общедоступной предварительной версии. Эта политика НЕ будет переключать каналы Office на основе каналов Teams. 

**Как сохранить существующих пользователей предварительной версии Teams, которые НЕ используют Актуальный канал (предварительная версия) Office?**

Для существующих пользователей, которым вы разрешили включить или отключить общедоступную предварительную версию Teams и хотите сохранить этот параметр в ее текущей форме, вам нужно будет переключиться с нового значения по умолчанию **Подписка на предварительную версию Office** на **Включено** (см. раздел [Настройка политики обновления](#set-the-update-policy))

**Как отказаться от этого параметра?**

Вы можете отключить параметр в Центре администрирования Teams с параметра **Подписка на предварительную версию Office** на **Не включено** (см. раздел [Настройка политики обновления](#set-the-update-policy))

## <a name="related-topics"></a>Статьи по теме

[Предварительная общедоступная версия для разработчиков](/microsoftteams/platform/resources/dev-preview/developer-preview-intro)
