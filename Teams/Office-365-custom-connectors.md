---
title: Управление Microsoft 365 и пользовательскими соединителями
author: guptaashish
ms.author: guptaashish
manager: prkosh
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
ms.reviewer: lucarras
search.appverid: MET150
f1.keywords:
- NOCSH
description: Узнайте, как соединители обновляют вашу команду, часто доставляя содержимое и обновления непосредственно в канал Teams для используемых служб.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: fb056cbee4dc1d56a6cd967d3f46c3f0680e9b73
ms.sourcegitcommit: 89904ab4116294ad9e4fd407feba8d7e3eefef10
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/19/2022
ms.locfileid: "66880233"
---
# <a name="manage-microsoft-365-and-custom-connectors"></a>Управление Microsoft 365 и пользовательскими соединителями

Для обновления команды соединители доставлять часто используемые обновления содержимого и служб непосредственно в канал Teams. С помощью соединителей пользователи Teams могут получать обновления из популярных служб, таких как Trello, Wunderlist, GitHub и Azure DevOps Services. Обновления будут публиковаться непосредственно в потоке чата в команде.

Соединители Microsoft 365 используются как с группами Microsoft Teams, так и с группами Microsoft 365, что упрощает синхронизацию всех участников и быстрое получение соответствующей информации. Microsoft Teams и Exchange используют одинаковую модель соединителей, что позволяет использовать одни соединители на обеих платформах. Однако если отключить соединители, настроенные для группы Microsoft 365, это также отключает возможность создания соединителей для группы Microsoft 365.

Любой член команды может подключить свою команду к популярным облачным службам с помощью соединителей, если это разрешено разрешениями команды, и все участники команды получают уведомления о действиях из этой службы. Соединители продолжают работать после того, как член, который изначально настроит соединитель, покидает его. Любой член команды с разрешениями на добавление или удаление может изменять соединители, застроив другие члены.

## <a name="enable-or-disable-connectors-in-teams"></a>Включение и отключение соединителей в Teams

Модуль Exchange Online PowerShell версии 2 использует современную проверку подлинности и работает с многофакторной проверкой подлинности, называемой MFA, для подключения ко всем средам PowerShell, связанным с Exchange в Microsoft 365. Администраторы могут использовать Exchange Online PowerShell для отключения соединителей для всего клиента или определенного почтового ящика группы, влияя на всех пользователей в этом клиенте или почтовом ящике. Отключение для нескольких определенных пользователей невозможно. Кроме того, соединители по умолчанию отключены для облака сообщества для государственных организаций, называемого клиентами GCC.

Параметр клиента переопределяет параметр группы. Например, если администратор включает соединители для группы и отключает их в клиенте, соединители для группы отключаются. Чтобы включить соединитель в Teams, подключитесь [к Exchange Online PowerShell с помощью](/powershell/exchange/connect-to-exchange-online-powershell?view=exchange-ps#connect-to-exchange-online-powershell-using-modern-authentication-with-or-without-mfa&preserve-view=true) современной проверки подлинности с MFA или без нее.

Чтобы включить или отключить соединитель, выполните следующие команды в Exchange Online PowerShell:

* Чтобы отключить соединители для клиента: `Set-OrganizationConfig -ConnectorsEnabled:$false`
* Чтобы отключить интерактивные сообщения для клиента: `Set-OrganizationConfig -ConnectorsActionableMessagesEnabled:$false`
* Чтобы включить соединители для Teams, выполните следующие команды:
  * `Set-OrganizationConfig -ConnectorsEnabled:$true`
  * `Set-OrganizationConfig -ConnectorsEnabledForTeams:$true`
  * `Set-OrganizationConfig -ConnectorsActionableMessagesEnabled:$true`

Дополнительные сведения об обмене модулями PowerShell см. в [разделе Set-OrganizationConfig](/powershell/module/exchange/Set-OrganizationConfig?view=exchange-ps&preserve-view=true). Чтобы включить или отключить соединители Outlook, [подключите приложения к группам в Microsoft Outlook](https://support.microsoft.com/topic/connect-apps-to-your-groups-in-outlook-ed0ce547-038f-4902-b9b3-9e518ae6fbab).

<!--- TBD: Find out how can we get to know about completion of customer migration.
Delete this section after customer migration to new Webhook URL is complete.
--->

## <a name="publish-connectors-for-your-organization"></a>Публикация соединителей для организации

Если вы хотите, чтобы пользовательский соединитель был доступен только пользователям в организации, вы можете отправить приложение пользовательского соединителя в каталог приложений вашей организации. После отправки пакета приложения конечные пользователи могут установить соединитель из каталога приложений организации, а также настроить и использовать соединитель в команде.

<!---TBD: Check if these instructions are for admins or end-users. I cannot find these options either in Teams or in TAC.

To set up a connector:

1. Select **Apps** from the left navigation bar.
1. In the **Apps** section, select **Connectors**.
1. Select the connector that you want to add.
1. From the pop-up menu, select **Add to a team**.
1. In the search box, type a team or channel name.
1. Select **Set up a Connector** from the pop-up menu in the bottom right corner of the dialog window.
--->

> [!IMPORTANT]
> Настраиваемые соединители недоступны в облаке сообщества для государственных организаций (GCC), Cloud-High сообщества (GCCH) и Министерства обороны США (DOD).

Чтобы использовать соединители в команде или канале, откройте меню "Дополнительные параметры" в правом верхнем углу канала. В меню выберите " **Соединители** ", а затем найдите или найдите нужный соединитель. При необходимости настройте выбранный соединитель.

:::image type="content" source="media/connectors-selection-ui.png" alt-text="Добавьте соединители в канал в Teams из параметров &quot;Дополнительно&quot; в правом верхнем углу канала.":::

## <a name="update-url-of-a-connector"></a>Обновление URL-адреса соединителя

Соединители Teams переходят на новый URL-адрес для повышения безопасности. Во время перехода вы получите уведомление об обновлении настроенного соединителя. Обновите соединитель как можно раньше, чтобы предотвратить прерывания работы служб соединителей. Чтобы обновить соединитель:

1. На странице конфигурации соединителей проверьте наличие  сообщения "Требуется внимание" рядом с настроенным соединителем.

   :::image type="content" source="media/Teams_Attention_Required_message.png" alt-text="Снимок экрана: сообщение &quot;Требуется внимание&quot;.":::

1. Чтобы повторно создать подключение для входящих соединителей веб-перехватчиков, выберите " **Обновить URL-адрес** " и используйте созданный URL-адрес веб-перехватчика.

   :::image type="content" source="media/Teams_update_URL_button.png" alt-text="Снимок экрана: кнопка &quot;Обновить URL-адрес&quot;.":::

1. Для других типов соединителей удалите соединитель и повторно создайте конфигурацию соединителя. **Появится сообщение с актуальным URL-адресом**.

   :::image type="content" source="media/Teams_URL_up_to_date.png" alt-text="Снимок экрана: URL-адрес актуального сообщения.":::

## <a name="related-articles"></a>Статьи по теме

* [Общие сведения о пользовательских соединителях и веб-перехватчиках](/microsoftteams/platform/webhooks-and-connectors/what-are-webhooks-and-connectors)
* [Создание Office 365 соединителей](/microsoftteams/platform/webhooks-and-connectors/how-to/connectors-creating)
