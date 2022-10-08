---
title: Управление соединителями и пользовательскими соединителями Microsoft 365
author: ashishguptaiitb
ms.author: guptaashish
manager: prkosh
ms.topic: article
ms.service: msteams
ms.subservice: teams-apps
audience: admin
ms.date: 09/01/2022
ms.collection:
- M365-collaboration
ms.reviewer: lucarras
search.appverid: MET150
f1.keywords:
- NOCSH
description: Узнайте, как соединители обновляют вашу команду, часто доставляя содержимое и обновления непосредственно в канал Teams для используемых служб.
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: fb65e7c91aa7ac0de7c8dade3a442f457d72657f
ms.sourcegitcommit: 6e85f3f70f8488ab827ac352c0f324b6dfd4b856
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/04/2022
ms.locfileid: "68377007"
---
# <a name="manage-microsoft-365-connectors-and-custom-connectors"></a>Управление соединителями и пользовательскими соединителями Microsoft 365

Чтобы держать вашу команду в курсе, соединители доставляют часто используемый контент и обновления служб непосредственно в канал Teams. Благодаря соединителям пользователи Teams могут получать обновления из популярных служб, таких как Trello, Wunderlist, GitHub и Azure DevOps Services. Обновления будут публиковаться непосредственно в потоке чата в команде.

Соединители Microsoft 365 используются как с группами Microsoft Teams, так и с группами Microsoft 365. Они упрощают синхронизацию всех участников и быстрое получение соответствующей информации. Вы можете использовать одинаковые соединители в Microsoft Teams и Microsoft Exchange. Однако если отключить соединители, настроенные для группы Microsoft 365, это также отключает возможность создания соединителей для группы Microsoft 365.

Любой член команды может подключить свою команду к популярным облачным службам с помощью соединителей, если позволяют разрешения группы, и все члены команды будут также уведомлены о действиях этой службы. Если участник, который изначально настроил соединитель, покидает команду, соединители продолжают работать. Любой член команды с разрешениями на добавление или удаление может изменять соединители, настроенные другими участниками.

## <a name="enable-or-disable-connectors-in-teams"></a>Включение и отключение соединителей в Teams

Модуль Exchange Online PowerShell V2 использует современную проверку подлинности и работает с мультифакторной проверкой подлинности (MFA) для подключения ко всем средам PowerShell, связанным с Exchange, в Microsoft 365. Администраторы могут использовать Exchange Online PowerShell для отключения соединителей для всего клиента или определенного группового почтового ящика, что повлияет на всех пользователей в этом клиенте или почтовом ящике. Отключение для нескольких определенных пользователей невозможно. Кроме того, соединители по умолчанию отключены для сред облака сообщества для государственных организаций (GCC).

> [!NOTE]
> Соединители по умолчанию отключены в средах сообщества облака для государственных организаций (GCC). Чтобы включить эти параметры, установите `ConnectorsEnabled` или `ConnectorsEnabledForTeams` параметры на `$true` с помощью `SetOrganizationConfig` командлета. Подключитесь к [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell?view=exchange-ps&preserve-view=true).

Параметр клиента переопределяет параметр группы. Например, если администратор включает соединители для группы и отключает их для клиента, соединители для группы отключаются. Чтобы включить соединитель в Teams, [подключитесь к Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell?view=exchange-ps#connect-to-exchange-online-powershell-using-modern-authentication-with-or-without-mfa&preserve-view=true), используя современную проверку подлинности с MFA или без нее.

Чтобы включить или отключить соединитель, выполните следующие команды в Exchange Online PowerShell:

* Чтобы отключить соединители для клиента: `Set-OrganizationConfig -ConnectorsEnabled:$false`.
* Чтобы отключить интерактивные сообщения для клиента: `Set-OrganizationConfig -ConnectorsActionableMessagesEnabled:$false`.
* Чтобы включить соединители для Teams, выполните следующие команды:
  * `Set-OrganizationConfig -ConnectorsEnabled:$true`
  * `Set-OrganizationConfig -ConnectorsEnabledForTeams:$true`
  * `Set-OrganizationConfig -ConnectorsActionableMessagesEnabled:$true`

Дополнительные сведения об обмене модулями PowerShell см. в разделе [Set-OrganizationConfig](/powershell/module/exchange/Set-OrganizationConfig?view=exchange-ps&preserve-view=true). Чтобы включить или отключить соединители Outlook, [подключите приложения к группам в Microsoft Outlook](https://support.microsoft.com/topic/connect-apps-to-your-groups-in-outlook-ed0ce547-038f-4902-b9b3-9e518ae6fbab).

## <a name="publish-connectors-for-your-organization"></a>Публикация соединителей для организации

Чтобы сделать настраиваемый соединитель доступным для пользователей вашей организации, загрузите приложение настраиваемого соединителя в каталог приложений вашей организации. Конечные пользователи внутри организации могут устанавливать, настраивать и использовать соединитель в команде.

> [!IMPORTANT]
> Пользовательские соединители недоступны в средах Government Community Cloud (GCC), Government Community Cloud-High (GCCH) и Министерства обороны (DOD).

Чтобы использовать соединители в команде или канале, откройте меню "Дополнительные параметры" в правом верхнем углу канала. В меню выберите **Соединители**, а затем укажите или найдите нужный соединитель. При необходимости настройте выбранный соединитель.

:::image type="content" source="media/connectors-selection-ui.png" alt-text="Добавьте соединители в канал в Teams из параметров &quot;Дополнительно&quot; в правом верхнем углу канала.":::

## <a name="update-url-of-a-connector"></a>Обновление URL-адреса соединителя

Соединители Teams переходят на новый URL-адрес для повышения безопасности. Во время перехода вы получите уведомление о необходимости обновить настроенный соединитель. Обновите соединитель как можно раньше, чтобы обеспечить бесперебойную работу служб соединителей. Чтобы обновить соединитель:

1. На странице конфигурации соединителей найдите сообщение **Требуется внимание** рядом с настроенным соединителем.

   :::image type="content" source="media/teams-attention-required-message.png" alt-text="Снимок экрана: сообщение &quot;Требуется внимание&quot;.":::

1. Чтобы повторно создать подключение для входящих соединителей веб-перехватчиков, выберите **Обновить URL-адрес** и используйте созданный URL-адрес веб-перехватчика.

   :::image type="content" source="media/teams-update-url-option.png" alt-text="Снимок экрана: кнопка &quot;Обновить URL-адрес&quot;.":::

1. Для других типов соединителей удалите соединитель и повторно создайте конфигурацию соединителя. Появится сообщение **URL-адрес обновлен**.

   :::image type="content" source="media/teams-url-updated.png" alt-text="Скриншот URL-адреса является актуальным сообщением.":::

## <a name="related-articles"></a>Статьи по теме

* [Обзор настраиваемых соединителей и веб-перехватчиков](/microsoftteams/platform/webhooks-and-connectors/what-are-webhooks-and-connectors)
* [Создание соединителей Office 365](/microsoftteams/platform/webhooks-and-connectors/how-to/connectors-creating)
