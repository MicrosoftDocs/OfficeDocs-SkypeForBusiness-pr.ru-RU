---
title: Управление приложением Bookings в Microsoft Teams
author: guptaashish
ms.author: guptaashish
manager: prkosh
audience: ITPro
ms.topic: article
ms.service: msteams
search.appverid: ''
searchScope:
- Microsoft Teams
- Microsoft Cloud for Healthcare
- Microsoft Cloud for Retail
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- microsoftcloud-healthcare
- microsoftcloud-retail
- m365solution-healthcare
- m365solution-scenario
ms.reviewer: ''
description: Узнайте, как управлять приложением Bookings в Teams для пользователей в организации.
ms.openlocfilehash: 3032704fe935f1d4d316741400e8a4b5841f8685
ms.sourcegitcommit: de6eb0478a79e178c5d02cdab8cca44a88beb853
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/07/2022
ms.locfileid: "63070588"
---
# <a name="manage-the-bookings-app-in-microsoft-teams"></a>Управление приложением Bookings в Microsoft Teams

Приложение Bookings в Microsoft Teams предлагает простой способ запланировать  личное и виртуальное время встречи. Например, посещения здравоохранения, финансовые консультации, собеседования, поддержка клиентов и часы работы в образовательных учреждениях. Подробнее см. в [виртуальных посещениях Teams и приложении Bookings](expand-teams-across-your-org/bookings-virtual-visits.md).

Планиры могут управлять несколькими календарями отделов и сотрудников, а также общением с внутренними и внешними участниками с помощью единого взаимодействия. Виртуальные встречи проводятся Microsoft Teams собраниях с надежными возможностями видеоконференции.

> [!NOTE]
> Приложение Bookings необходимо устанавливать только для планировщиков в Teams. Сотрудники, которые проводят виртуальные встречи или участвуют в них, не требуют приложения. Они могут просто присоединяться к встречам из своего Outlook или Teams или из ссылки на Teams в сообщении с подтверждением резервирования.

## <a name="prerequisites-to-use-the-bookings-app-in-teams"></a>Необходимые условия для использования приложения Bookings в Teams

* Почтовый Exchange находится в Exchange Online. Локальное Exchange Server не поддерживается.
* Служба Microsoft Bookings доступна для организации.
* У пользователей есть соответствующая лицензия. Office 365 A3, A5, E3, E5, F1, F3, Microsoft 365 A3, A5, E3, E5, F1, F3 и Business Standard.
* У всех пользователей приложения Bookings и всех сотрудников, участвующих в собраниях, есть лицензия, которая Teams планирования собраний.
* [Необходимые условия для программного обеспечения и браузера](hardware-requirements-for-the-teams-app.md).

## <a name="availability-of-bookings-in-teams"></a>Доступность Bookings в Teams

Приложение Microsoft Bookings для Teams доступно на компьютере и в Интернете. Его можно найти в статье Приложения [Teams](https://teams.microsoft.com/l/app/4c4ec2e8-4a2c-4bce-8d8f-00fc664a4e5b?source=store-copy-link) **и Управление** приложениями в центре Teams администрирования.

### <a name="control-access-to-bookings-within-your-organization"></a>Управление доступом к Bookings в организации

Существует несколько способов управления доступом к приложению Bookings и определенным функциям приложения. Вы можете сделать приложение Microsoft Bookings доступным или отключить его в Центр администрирования Microsoft 365. Кроме того, вы можете создать политику приложения Bookings, чтобы разрешить выбору пользователей создавать календари Bookings. См [. получить доступ к Microsoft Bookings](/microsoft-365/bookings/get-access).

Вы также [можете создать политику Teams приложения, чтобы закрепить приложение Bookings для некоторых пользователей](teams-app-setup-policies.md).

## <a name="recommended-meeting-policy-settings"></a>Рекомендуемые параметры политики собраний

Чтобы обеспечить оптимальный опыт работы с Bookings, создайте политику Teams собрания, чтобы автоматически допустить всех пользователей  в организации и назначить ее сотрудникам. Политика позволяет сотрудникам автоматически присоединяться к встрече и включить возможности "lobby" для внешних участников. Узнайте [, как автоматически допустить людей на собрания](meeting-policies-participants-and-guests.md#automatically-admit-people).

## <a name="optional-staff-approvals-setting"></a>Дополнительная настройка согласования с сотрудниками

Вы можете потребовать от сотрудников сделать это перед тем, как Bookings будет информировать о доступности своего расписания и чтобы другие люди могли запланировать встречу с ним.

Чтобы включить этот параметр, перейдите **в** \> Центр администрирования Microsoft 365 **Параметры** \> **Параметры** и выберите **Bookings**.

Если этот параметр включен, сотрудники получают по электронной почте запрос на утверждение членства в календаре резервирования.  

Эта функция будет постепенно развертываться по всему миру для пользователей Microsoft 365 и Office 365. Если в вашей среде пока недоступны все параметры, проверьте это в ближайшее время.

## <a name="changing-your-default-domain-when-setting-up-bookings-mailbox"></a>Изменение домена по умолчанию при настройке почтового ящика Bookings

При настройке почтового ящика Bookings используется домен электронной почты по умолчанию вашей организации Microsoft 365 или Office 365. Однако домен по умолчанию может вызывать проблемы при отправке приглашений на собрания внешним получателям. Например, ваше приглашение может быть помечено как спам и перемещено в папку нежелательной почты получателя, чтобы получатель не видел ваше приглашение.

Рекомендуем изменить домен по умолчанию перед созданием почтового ящика Bookings. См. [вопрос и о доменах](/microsoft-365/admin/setup/domains-faq#how-do-i-set-or-change-the-default-domain-in-office-365).

Если вам нужно изменить домен по умолчанию после создания почтового ящика Bookings, используйте PowerShell.

```PowerShell
Set-Mailbox -identity business@domain.onmicrosoft.com -WindowsEmailAddress business@domain.com -EmailAddresses business@domain.com
```

См. документацию PowerShell, чтобы [узнать, как настроить](/powershell/module/exchange/mailboxes/set-mailbox) почтовый ящик.

> [!NOTE]
> Если вы используете гибридную конфигурацию Exchange, мы рекомендуем тщательно проверить потоки почты между локальной Exchange и Exchange Online при изменении домена по умолчанию.

## <a name="send-feedback"></a>Отправка отзыва

Отзывы можно отправлять по адресу:

* Впечатления от использования или удобство использования
* Пробелы в функциях или отсутствие функций
* Дефекты и проблемы
  
Чтобы отправить отзыв, выберите в  нижней части панели навигации Teams справки и выберите Сообщить о проблеме **для ВСЕХ**. Указать в начале отчета о отзывах, что вы отправляете отзыв о "Bookings", чтобы мы могли легко определить проблемы с Bookings.

## <a name="related-articles"></a>Статьи по теме

[Управление опытом  join for Teams посещений в мобильных браузерах](expand-teams-across-your-org/mobile-browser-join.md)


  [Документация по Bookings для конечных пользователей](https://support.office.com/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b?ui=en-US&rs=en-US&ad=US#PickTab=Bookings)
