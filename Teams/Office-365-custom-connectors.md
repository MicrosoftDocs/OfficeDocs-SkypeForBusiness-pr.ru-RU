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
description: Соединители помогают поддерживать текущую работу команды, предоставляя контент и обновления из служб, которые вы часто используете, непосредственно в канале.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 100db95adf900a48898515b9bb9a3a753b47de4f
ms.sourcegitcommit: d16fb01f752d186445893ea8e3b0d4450a4a0e67
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/29/2022
ms.locfileid: "65125444"
---
# <a name="manage-microsoft-365-and-custom-connectors"></a>Управление Microsoft 365 и пользовательскими соединителями

Для обновления команды соединители доставлять часто используемые содержимое и обновления служб непосредственно в Teams канале. С помощью соединителей пользователи Teams могут получать обновления из популярных служб, таких как Trello, Wunderlist, GitHub и Azure DevOps Services. Обновления будут публиковаться непосредственно в потоке чата в команде.

Microsoft 365 соединители используются с группами Microsoft Teams и Microsoft 365, что упрощает синхронизацию всех участников и быстрое получение соответствующей информации. Microsoft Teams и Exchange используют одинаковую модель соединителей, что позволяет использовать одни соединители на обеих платформах. Однако при отключении соединителей, настроенных для группы Microsoft 365, она также отключает возможность создания соединителей для Microsoft 365 группы.

Любой член команды может подключить свою команду к популярным облачным службам с помощью соединителей, если это разрешено разрешениями команды, и все участники команды получают уведомления о действиях из этой службы. Соединители продолжают работать после того, как элемент, который изначально настроит соединитель, покинул его. Любой член команды с разрешениями на добавление или удаление может изменять соединители, застроив другие члены.

## <a name="enable-or-disable-connectors-in-teams"></a>Включение или отключение соединителей в Teams

Модуль Exchange Online PowerShell версии 2 использует современную проверку подлинности и работает с многофакторной проверкой подлинности, называемой MFA для подключения ко всем средам PowerShell, связанным Exchange в Microsoft 365. Администраторы могут использовать Exchange Online PowerShell для отключения соединителей для всего клиента или определенного почтового ящика группы, влияя на всех пользователей в этом клиенте или почтовом ящике. Отключение для нескольких определенных пользователей невозможно. Кроме того, соединители по умолчанию отключены для облако сообщества для государственных организаций, называемых GCC клиентами.

Параметр клиента переопределяет параметр группы. Например, если администратор включает соединители для группы и отключает их в клиенте, соединители для группы отключаются. Чтобы включить соединитель в Teams, подключитесь [к Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell?view=exchange-ps#connect-to-exchange-online-powershell-using-modern-authentication-with-or-without-mfa&preserve-view=true) с помощью современной проверки подлинности с MFA или без нее.

### <a name="commands-to-enable-or-disable-connectors"></a>Команды для включения или отключения соединителей

Выполните следующие команды в Exchange Online PowerShell:

* Чтобы отключить соединители для клиента: `Set-OrganizationConfig -ConnectorsEnabled:$false`
* Чтобы отключить интерактивные сообщения для клиента: `Set-OrganizationConfig -ConnectorsActionableMessagesEnabled:$false`
* Чтобы включить соединители для Teams, выполните следующие команды:
  * `Set-OrganizationConfig -ConnectorsEnabled:$true`
  * `Set-OrganizationConfig -ConnectorsEnabledForTeams:$true`
  * `Set-OrganizationConfig -ConnectorsActionableMessagesEnabled:$true`

Дополнительные сведения об обмене модулями PowerShell см. в [разделе Set-OrganizationConfig](/powershell/module/exchange/Set-OrganizationConfig?view=exchange-ps&preserve-view=true). Чтобы включить или отключить Outlook соединители, подключите [приложения к группам в Outlook](https://support.microsoft.com/topic/connect-apps-to-your-groups-in-outlook-ed0ce547-038f-4902-b9b3-9e518ae6fbab).

<!---TBD: Delete this section after customer migration to new Webhook URL is complete --->

#### <a name="connector-url-update-notification"></a>Уведомление об обновлении URL-адреса соединителя

Соединители Teams переходят на новый URL-адрес для повышения безопасности. Во время перехода вы получите уведомление об обновлении настроенного соединителя. Обновите соединитель как можно раньше, чтобы предотвратить прерывания работы служб соединителей. Чтобы обновить соединитель:

1. На странице конфигурации соединителей проверьте наличие  сообщения "Требуется внимание" рядом с настроенным соединителем.

   ![Снимок экрана: сообщение "Требуется внимание".](media/Teams_Attention_Required_message.png)

1. Чтобы повторно создать подключение для входящих соединителей веб-перехватчиков, выберите " **Обновить URL-адрес** " и используйте созданный URL-адрес веб-перехватчика.

   ![Снимок экрана: кнопка "Обновить URL-адрес".](media/Teams_update_URL_button.png)

1. Для других типов соединителей удалите соединитель и повторно создайте конфигурацию соединителя. **Появится сообщение с актуальным URL-адресом**.

   ![Снимок экрана: URL-адрес актуального сообщения.](media/Teams_URL_up_to_date.png)

## <a name="see-also"></a>См. также

* [Общие сведения о пользовательских соединителях и веб-перехватчиках](/microsoftteams/platform/webhooks-and-connectors/what-are-webhooks-and-connectors)
* [Создание Office 365 соединителей](/microsoftteams/platform/webhooks-and-connectors/how-to/connectors-creating)