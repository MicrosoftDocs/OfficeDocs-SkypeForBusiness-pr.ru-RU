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
ms.openlocfilehash: 98834770d48e0fd35f146b155e4970df7ddaaba3
ms.sourcegitcommit: 1e8cff687b12348d4ecc538084ab57bbba23b523
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/07/2022
ms.locfileid: "64703615"
---
# <a name="manage-the-bookings-app-in-microsoft-teams"></a>Управление приложением Bookings в Microsoft Teams

Приложение Bookings в Microsoft Teams предлагает простой способ планирования  person и виртуальных встреч. Например, посещения здравоохранения, финансовые консультации, собеседования, поддержка клиентов и рабочее время для образовательных учреждений. Дополнительные сведения см. в [статье о виртуальных посещениях Teams и Bookings приложения](expand-teams-across-your-org/bookings-virtual-visits.md).

Планировщики могут управлять несколькими календарями отделов и сотрудников, а также взаимодействием с внутренними и внешними участниками в одном интерфейсе. Виртуальные встречи проводится через Microsoft Teams, которые предоставляют надежные возможности видеоконференций.

> [!NOTE]
> Приложение Bookings необходимо устанавливать только для планировщиков в Teams. Сотрудникам, которые проводят или участвуют в виртуальных встречах, это приложение не требуется. Они могут просто присоединяться к встречам из Outlook или Teams календаря или по ссылке Teams в сообщении электронной почты с подтверждением резервирования.

## <a name="prerequisites-to-use-the-bookings-app-in-teams"></a>Необходимые условия для использования Bookings в Teams

* Почтовый Exchange находится в Exchange Online. Локальные почтовые Exchange Server не поддерживаются.
* Microsoft Bookings доступен для организации.
* У пользователей есть соответствующая лицензия. Office 365 A3 поддерживаются A5, E3, E5, F1, F3, Microsoft 365 A3, A5, E3, E5, F1, F3 и Business Standard.
* Все пользователи приложения Bookings и все сотрудники, участвующие в собраниях, имеют лицензию, которая Teams планирования собраний.
* [Необходимые условия для программного обеспечения и браузера](hardware-requirements-for-the-teams-app.md).

## <a name="availability-of-bookings-in-teams"></a>Доступность Bookings в Teams

Microsoft Bookings приложение для Teams доступно на рабочем столе и в Интернете. Его можно найти в разделе "Приложения[" Teams](https://teams.microsoft.com/l/app/4c4ec2e8-4a2c-4bce-8d8f-00fc664a4e5b?source=store-copy-link) в разделе "Управление  приложениями" Teams центре администрирования.

### <a name="control-access-to-bookings-within-your-organization"></a>Управление доступом к Bookings в организации

Существует несколько способов управления доступом к приложению Bookings и определенным функциям приложения. Вы можете сделать Microsoft Bookings доступным или отключить его из Центр администрирования Microsoft 365. Кроме того, можно создать политику Bookings, чтобы разрешить выбранным пользователям создавать Bookings календари. См[. раздел "Получение доступа к Microsoft Bookings](/microsoft-365/bookings/get-access)".

Вы также можете [создать политику Teams приложения](teams-app-setup-policies.md), чтобы закрепить Bookings для выбранных пользователей.

## <a name="recommended-meeting-policy-settings"></a>Рекомендуемые параметры политики собраний

Чтобы обеспечить наилучшее взаимодействие Bookings, создайте политику Teams собрания, чтобы автоматически допускать всех пользователей в организации и назначать ее сотрудникам. Политика позволяет сотрудникам автоматически присоединяться к встрече и включить "зал ожидания" для внешних участников. Узнайте [, как автоматически допускать пользователей к собраниям](meeting-policies-participants-and-guests.md#automatically-admit-people).

## <a name="optional-staff-approvals-setting"></a>Дополнительная настройка согласования с сотрудниками

Вы можете потребовать, чтобы сотрудники согласились на участие, Bookings предоставить им сведения о доступности по расписанию, а также перед тем, как другие пользователи могут запланировать встречу с ними.

Чтобы включить этот параметр, перейдите **Центр администрирования Microsoft 365** \> **Параметры** \> **Параметры** и выберите **Bookings**.

Если этот параметр включен, сотрудники получают сообщение электронной почты, в котором ему будет отправлен запрос на утверждение членства в календаре резервирования.  

Эта функция будет постепенно развертываться по всему миру для пользователей Microsoft 365 и Office 365. Если все параметры еще не доступны в вашей среде, проверьте это в ближайшее время.

## <a name="changing-your-default-domain-when-setting-up-bookings-mailbox"></a>Изменение домена по умолчанию при настройке Bookings почтового ящика

При настройке почтового ящика Bookings используется домен электронной почты по умолчанию вашей организации Microsoft 365 или Office 365. Однако домен по умолчанию может вызвать проблемы при отправке приглашений на собрание внешним получателям. Например, ваше приглашение может быть помечено как спам и перемещено в папку нежелательной почты получателя, поэтому получатель может никогда не увидеть ваше приглашение.

Мы рекомендуем изменить домен по умолчанию перед созданием Bookings почтового ящика. См. часто [задаваемые вопросы о доменах](/microsoft-365/admin/setup/domains-faq#how-do-i-set-or-change-the-default-domain-in-office-365).

Если после создания почтового ящика Bookings домен по умолчанию, используйте PowerShell.

```PowerShell
Set-Mailbox -identity business@domain.onmicrosoft.com -WindowsEmailAddress business@domain.com -EmailAddresses business@domain.com
```

См. документацию по PowerShell для [задания командлета почтового](/powershell/module/exchange/mailboxes/set-mailbox) ящика.

> [!NOTE]
> Если вы используете гибридную конфигурацию Exchange, рекомендуется тщательно протестировать поток обработки почты между локальными Exchange и Exchange Online при изменении домена по умолчанию.

## <a name="send-feedback"></a>Отправка отзывов

Отзывы можно отправлять по адресу:

* Впечатления от использования или удобство использования
* Пробелы в функциях или отсутствие функций
* Дефекты и проблемы
  
Чтобы отправить отзыв, выберите пункт  "Справка" в нижней Teams панели навигации, а затем выберите "Сообщить  о проблеме для **всех** проблем". Укажите в начале отчета о отзывах, что вы отправляете отзыв о "Bookings", чтобы мы могли легко определить Bookings проблемы.

## <a name="related-articles"></a>Статьи по теме

[Управление интерфейсом присоединения для Teams виртуальных посещений в браузерах](expand-teams-across-your-org/browser-join.md)


  [Документация по Bookings для конечных пользователей](https://support.office.com/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b?ui=en-US&rs=en-US&ad=US#PickTab=Bookings)
