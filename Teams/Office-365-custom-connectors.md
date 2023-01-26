---
title: Управление соединителями Microsoft 365 и пользовательскими соединителями
author: ashishguptaiitb
ms.author: guptaashish
manager: prkosh
ms.topic: article
ms.service: msteams
ms.subservice: teams-apps
audience: admin
ms.date: 01/24/2023
ms.collection:
- M365-collaboration
ms.reviewer: lucarras
search.appverid: MET150
f1.keywords:
- NOCSH
description: Узнайте, как соединители обеспечивают обновление вашей команды, часто доставляя содержимое и обновления непосредственно в канал Teams для используемых служб.
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: bf38711da0205e7c674e769942d00d340d51f66e
ms.sourcegitcommit: 1cb5f7129562eb2b228da23497c0e09e53da3872
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/25/2023
ms.locfileid: "69983687"
---
# <a name="manage-microsoft-365-connectors-and-custom-connectors"></a>Управление соединителями Microsoft 365 и пользовательскими соединителями

Соединители в Microsoft Teams доставляют содержимое и обновления служб непосредственно из сторонних служб в канал Teams. С помощью соединителей пользователи получают обновления из популярных служб, таких как Trello, Wunderlist, GitHub и Azure DevOps Services. Обновления публикуются непосредственно в потоке чата. Это упрощает синхронизацию всех участников и быстро получает соответствующую информацию.

Соединители Microsoft 365 используются с группами Teams и Microsoft 365. Одни и те же соединители можно использовать в Teams и Microsoft Exchange. 

<!--- However, if you disable any connectors configured for a Microsoft 365 group, it also disables the ability for the Microsoft 365 group to create connectors. --->

Если разрешения группы разрешают это, любой член команды может добавить соединитель в команду, и все участники команды получают уведомления о действиях из этой службы. Любой член команды с разрешениями на добавление или удаление может изменять соединители, настроенные другими участниками.

## <a name="enable-or-disable-connectors-in-teams"></a>Включение и отключение соединителей в Teams

Модуль Exchange Online PowerShell версии 2 использует современную проверку подлинности и работает с многофакторной проверкой подлинности (MFA) для подключения ко всем связанным с Exchange средам PowerShell в Microsoft 365. Администраторы могут использовать Exchange Online PowerShell для отключения соединителей для всего клиента или определенного группового почтового ящика, что повлияет на всех пользователей в этом клиенте или почтовом ящике. Это невозможно отключить для нескольких конкретных пользователей.

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

## <a name="considerations-when-using-connectors-in-teams"></a>Рекомендации по использованию соединителей в Teams

* Соединители по умолчанию отключены в средах сообщества облака для государственных организаций (GCC). Чтобы включить эти параметры, установите `ConnectorsEnabled` или `ConnectorsEnabledForTeams` параметры на `$true` с помощью `SetOrganizationConfig` командлета. Подключитесь к [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell?view=exchange-ps&preserve-view=true).

* Если пользователь, добавивший соединитель в команду, покидает команду, соединитель продолжает работать.

* Следующие соединители недоступны для использования в январе 2023 г.:

  * АГА
  * AIRBRAKE
  * AIRCALL
  * APPLINKS
  * APPSIGNAL
  * BEANSTALK
  * BITBUCKET
  * BITBUCKETSERVER
  * ПРИЯТЕЛЬ
  * BUGSNAG
  * BUILDKITE
  * CATSONE
  * CHATRA
  * CIRCLECI
  * CODESHIP
  * GETRESPONSE
  * GHOSTINSPECTOR
  * GROOVE
  * HEROKU
  * HONEYBADGER
  * ДОМОФОН
  * LOGENTRIES
  * NEWRELIC
  * OPSGENIE
  * PAGERDUTY
  * PAPERTRAIL
  * PINGDOM
  * PIVOTALTRACKER
  * RAYGUN
  * ROLLBAR
  * RUNSCOPE
  * SATISMETER
  * СЕМАФОР
  * КАРАУЛ
  * SHAREPOINTNEWS
  * SIMPLEINOUT
  * STATUSPAGEIO
  * SUBVERSION
  * TEAMFOUNDATIONSERVER
  * TESTFAIRY
  * TRAVISCI
  * UPDOWN
  * USERLIKE
  * XPDEV

## <a name="related-articles"></a>Статьи по теме

* [Обзор пользовательских соединителей и веб-перехватчиков](/microsoftteams/platform/webhooks-and-connectors/what-are-webhooks-and-connectors)
* [Создание соединителей Office 365](/microsoftteams/platform/webhooks-and-connectors/how-to/connectors-creating)
