---
title: Интеграция Skype для бизнеса Online и Exchange Server
ms.reviewer: cbland
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 4/2/2019
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: ffe4c3ba-7bab-49f1-b229-5142a87f94e6
description: Настройка проверки подлинности OAuth между Exchange на локальном и Skype для бизнеса Online включает возможности интеграции Skype для бизнеса и Exchange, описанные в разделе Поддержка функций.
ms.openlocfilehash: be1fd4ae0c1a1046a8da1d9a30550ac238a4034a
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "34278128"
---
# <a name="configure-integration-between-skype-for-business-online-or-microsoft-teams-and-exchange-server"></a>Настройка интеграции между Skype для бизнеса Online и Microsoft Teams и Exchange Server 

Настройка интеграции между Exchange Server и Skype для бизнеса Online включает возможности интеграции Skype для бизнеса и Exchange, описанные в разделе [Поддержка функций](../../plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md#feature_support).

Эта статья относится к интеграции с Exchange Server 2013 – 2019.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Что нужно знать перед началом работы?

- Предполагаемое время выполнения этой задачи: 15 минут

-  Перед выполнением этих процедур вы должны получить разрешения. Чтобы узнать, какие разрешения вам нужны, ознакомьтесь с разделом [разрешения для инфраструктуры Exchange и оболочки](https://go.microsoft.com/fwlink/p/?LinkId=746511) .

- Сведения о сочетаниях клавиш, которые могут применяться к процедурам, описанным в этой статье, приведены в разделе сочетания [клавиш в центре администрирования Exchange]( https://go.microsoft.com/fwlink/p/?LinkId=746512).

## <a name="configure-integration-between-exchange-server-and-o365"></a>Настройка интеграции между сервером Exchange Server и Office 365

### <a name="step-1-configure-oauth-authentication-between-exchange-server-and-o365"></a>Действие 1: Настройка проверки подлинности OAuth между Exchange Server и O365

Выполните действия, описанные в приведенной ниже статье.

[Настройка проверки подлинности OAuth между организациями Exchange и Exchange Online](https://docs.microsoft.com/en-us/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help)

### <a name="step-2-create-a-new-mail-user-account-for-the-skype-for-business-online-or-teams-partner-application"></a>Действие 2: создание учетной записи пользователя для партнерской программы Skype для бизнеса Online или Teams

Это действие выполняется на сервере Exchange Server. На этом шаге создается пользователь почты, которому назначаются соответствующие права роли управления. Затем эта учетная запись используется на следующем шаге.

Укажите проверенный домен для организации Exchange. Этот домен должен быть тем же доменом, который используется в качестве основного домена SMTP для локальных учетных записей Exchange. Этот домен называется \<проверяемым доменом\> в описанной ниже процедуре. Кроме того, \<домаинконтроллерфкдн\> должно быть полным доменным именем контроллера домена.

``` Powershell
$user = New-MailUser -Name O365-ApplicationAccount -ExternalEmailAddress O365-ApplicationAccount@<your Verified Domain> -DomainController <DomainControllerFQDN>
```

Эта команда скрывает нового пользователя почты из списка адресов.

``` Powershell
Set-MailUser -Identity $user.Identity -HiddenFromAddressListsEnabled $True -DomainController <DomainControllerFQDN>
```

Следующие две команды назначают новой учетной записи роль управления UserApplication и ArchiveApplication.

``` Powershell
New-ManagementRoleAssignment -Role UserApplication -User $user.Identity -DomainController <DomainControllerFQDN>
```

``` Powershell
New-ManagementRoleAssignment -Role ArchiveApplication -User $user.Identity -DomainController <DomainControllerFQDN>
```

### <a name="step-3-create-and-enable-a-partner-application-for-skype-for-business-online-or-teams"></a>Шаг 3: создание и включение приложения-партнера для Skype для бизнеса Online или Teams

Создайте новое партнерское приложение и начните использовать созданную учетную запись. Выполните следующую команду в PowerShell Exchange в локальной организации Exchange.

``` Powershell
New-PartnerApplication -Name SfBOnline -ApplicationIdentifier 00000004-0000-0ff1-ce00-000000000000 -Enabled $True -LinkedAccount $user.Identity
```

### <a name="verify-your-success"></a>Проверка успешности выполнения

Убедитесь в том, что конфигурация верна, проверьте, успешно ли работают некоторые функции. 

1. Убедитесь в том, что делегирование календаря Outlook работает в бетвиен двух пользователей Teams с Exchange Server 2016 или 2019.

2. Убедитесь в том, что в папке "Журнал бесед" Outlook отображается журнал бесед для мобильных клиентов.

Кроме того, Взгляните на трафик. Трафик в подтверждении OAuth является весьма отличительным (и не рассматривается как обычная проверка подлинности), особенно вокруг сфер, где вы начнете просматривать трафик поставщика, выглядящий следующим образом: 00000004-0000-0ff1-ce00-000000000000 @ (иногда с a/Before знак "@") в токенах, которые передаются. Вы не увидите имя пользователя или пароль, который является точкой OAuth. Но вы увидите, что в этом случае это "4" — Skype для бизнеса — и сфера подписки.

Если вы хотите, чтобы вы успешно использовали OAuth, убедитесь, что вы знаете, что нужно ожидать и что нужно знать, как выглядит трафик. Итак, вот [что нужно ожидать](https://tools.ietf.org/html/draft-ietf-oauth-v2-23#page-34): Вот стандартный [пример трафика OAuth в приложении Microsoft](https://download.microsoft.com/download/8/5/8/858F2155-D48D-4C68-9205-29460FD7698F/[MS-SPS2SAUTH].pdf) (это может оказаться полезным для чтения, но не использует маркеры обновления), и есть расширения Fiddler, позволяющие найти OAuth JWT (JSON). Веб-токен).

Ниже приведен [Пример настройки одного из них](https://blogs.msdn.microsoft.com/kaevans/2015/03/30/updated-fiddler-oauth-inspector/), но вы можете использовать любой сетевой инструмент трассировки, который вы хотите предпринять.

## <a name="related-topics"></a>Статьи по теме

[Настройка проверки подлинности OAuth между организациями Exchange и Exchange Online](https://docs.microsoft.com/en-us/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help)
