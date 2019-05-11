---
title: Интеграция между Скайп для бизнеса в Интернет и Exchange server
ms.reviewer: cbland
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 4/2/2019
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: ffe4c3ba-7bab-49f1-b229-5142a87f94e6
description: Настройка OAuth проверки подлинности между Exchange при локальном и Скайп для бизнеса в Интернет позволяет Скайп для бизнеса и интеграция с Exchange, описанными в поддержка функции.
ms.openlocfilehash: c6a3819c9ec6ae0c207307a23f67bf04e4f07ac0
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "33894241"
---
# <a name="configure-integration-between-skype-for-business-online-or-microsoft-teams-and-exchange-server"></a>Настройка интеграции между Скайп для бизнеса в Интернете или группами Майкрософт и Exchange Server 

Настройка интеграции между сервером Exchange и Скайп для бизнеса в Интернет позволяет Скайп для бизнеса и интеграция с Exchange, описанными в [функции поддержки](../../plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md#feature_support).

Этот раздел предназначен для интеграции с Exchange Server 2013 через 2019.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Что нужно знать перед началом работы?

- Предполагаемое время выполнения этой задачи: 15 минут

-  Перед выполнением этих процедур вы должны получить разрешения. Какие нужны разрешения см в разделе [Exchange and Shell infrastructure permissions](https://go.microsoft.com/fwlink/p/?LinkId=746511) .

- Сведения о сочетаниях клавиш, которые могут относиться к процедур, описанных в этом разделе содержатся [сочетаний клавиш в центре администрирования Exchange]( https://go.microsoft.com/fwlink/p/?LinkId=746512).

## <a name="configure-integration-between-exchange-server-and-o365"></a>Настройка интеграции между сервером Exchange и O365

### <a name="step-1-configure-oauth-authentication-between-exchange-server-and-o365"></a>Этап 1: Настройка проверки подлинности OAuth между сервером Exchange и O365

Выполните действия, описанные в следующей статье:

[Настройка проверки подлинности OAuth между организациями Exchange и Exchange Online](https://docs.microsoft.com/en-us/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help)

### <a name="step-2-create-a-new-mail-user-account-for-the-skype-for-business-online-or-teams-partner-application"></a>Шаг 2: Создание новой учетной записи пользователя почты для Скайп для бизнеса в Интернет или группами партнерского приложения

Этот шаг выполняется на сервере Exchange. На этом шаге создается пользователь почты, которому назначаются соответствующие права роли управления. Затем эта учетная запись используется на следующем шаге.

Укажите подтвержденным доменом в организации Exchange. Этот домен должен быть того же домена, используется в качестве основного домена SMTP, используемый для учетных записей Exchange в локальной. В этом домене называется \<домена проверены\> в следующей процедуре. Кроме того \<DomainControllerFQDN\> должно быть полное доменное имя контроллера домена.

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

### <a name="step-3-create-and-enable-a-partner-application-for-skype-for-business-online-or-teams"></a>Шаг 3: Создание и включить партнерское приложение для Скайп для бизнеса в Интернет или группами

Создайте новое партнерское приложение и начните использовать созданную учетную запись. Выполните следующую команду в Exchange PowerShell в своей локальной организации Exchange.

``` Powershell
New-PartnerApplication -Name SfBOnline -ApplicationIdentifier 00000004-0000-0ff1-ce00-000000000000 -Enabled $True -LinkedAccount $user.Identity
```

### <a name="verify-your-success"></a>Проверка успешности выполнения

Проверьте правильность конфигурации убедитесь, что некоторые функции работают успешно. 

1. Убедитесь, что в диапазоне от двух групп пользователей с Exchange Server 2016 или почтовые ящики 2019 работает делегирование календаря Outlook.

2. Убедитесь, что журнал бесед для мобильных клиентов, в папке журнала бесед программы Outlook.

Кроме того Обратите внимание на трафик. Трафик в подтверждении OAuth действительно особый (и не выглядит как обычная проверка подлинности), особенно вокруг сфер, где вы начнете видеть трафика издателя, которая выглядит следующим образом: 00000004-0000-0ff1-ce00-000000000000 @ (иногда с аудио- и перед знак @), в маркеры, которые передаются. Вы не увидите имя пользователя или пароль, который является точка OAuth. Но вы увидите издателя «Office» — в данном случае является Скайп для бизнеса – и область действия подписки "4".

Если необходимо, чтобы что успешно вы используете OAuth, убедитесь, что вы знаете, что следует ожидать и знать, как должны выглядеть трафика. Да, [Вот, что следует ожидать](https://tools.ietf.org/html/draft-ietf-oauth-v2-23#page-34), вот стандартный [Пример трафика OAuth в приложении Microsoft](https://download.microsoft.com/download/8/5/8/858F2155-D48D-4C68-9205-29460FD7698F/[MS-SPS2SAUTH].pdf) (действительно полезен для чтения, хотя он не использует маркеры обновления) и существуют Fiddler расширения, которые можно найти в вашей OAuth JWT (JSON Веб-маркера).

Ниже приведен [Пример настройки один](https://blogs.msdn.microsoft.com/kaevans/2015/03/30/updated-fiddler-oauth-inspector/), но можно использовать любое средство сетевой трассировки, как для выполнения этого процесса.

## <a name="related-topics"></a>Статьи по теме

[Настройка проверки подлинности OAuth между организациями Exchange и Exchange Online](https://docs.microsoft.com/en-us/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help)
