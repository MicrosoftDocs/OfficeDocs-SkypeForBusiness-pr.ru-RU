---
title: Управление приложением Bookings в Microsoft Teams
author: dmaguire
ms.author: serdars
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
search.appverid: ''
searchScope:
- Microsoft Teams
- Microsoft Cloud for Healthcare
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- microsoftcloud-healthcare
- m365solution-healthcare
- m365solution-scenario
ms.reviewer: ''
description: Узнайте, как управлять приложением Bookings в Teams для пользователей в организации.
ms.openlocfilehash: ae471bfee1901396ee3419380fcd7620e21231fe
ms.sourcegitcommit: 5c88a07f07f9faad294d614d507e43173efc5f46
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/19/2021
ms.locfileid: "61111979"
---
# <a name="manage-the-bookings-app-in-microsoft-teams"></a>Управление приложением Bookings в Microsoft Teams

Приложение Bookings в Microsoft Teams предлагает простой способ запланировать личные и виртуальные встречи, например посещение врача, финансовые консультации, собеседования, поддержку клиентов, учебные часы и многое другое. Подробнее см. в [виртуальных посещениях Teams и приложении Bookings.](expand-teams-across-your-org/bookings-virtual-visits.md)

Планировщики могут управлять несколькими календарями отделов и сотрудников, а также взаимодействием с внутренними и внешними участниками одной встречи. Виртуальные встречи проводятся через Microsoft Teams, что обеспечивает надежные возможности видеоконференции.

> [!NOTE]
> Приложение Bookings необходимо устанавливать только для планировщиков в Teams. Сотрудники, которые проводят виртуальные встречи или участвуют в них, не требуют приложения. Они могут просто присоединяться к встречам из своего Outlook или Teams или из ссылки на Teams в сообщении с подтверждением резервирования.

## <a name="prerequisites-for-using-the-bookings-app-in-teams"></a>Необходимые условия для использования приложения Bookings в Teams

- Почтовый ящик Exchange должен быть в Exchange Online. Локальное Exchange Server не поддерживается.

- Для организации должна быть включена служба Microsoft Bookings.

- У пользователей должна быть соответствующая лицензия. Office 365 A3, A5, E3, E5, F1, F3, Microsoft 365 A3, A5, E3, E5, F1, F3 и Business Standard.

- У всех пользователей приложения Bookings и всех сотрудников, участвующих в собраниях, должна быть лицензия, которая Teams планирования собраний.

- Ваши системы должны соответствовать всем [требованиям к программному обеспечению и браузеру](hardware-requirements-for-the-teams-app.md).

## <a name="availability-of-bookings-in-teams"></a>Доступность Bookings в Teams

Приложение Microsoft Bookings для Teams доступно на компьютере и в Интернете. Его можно найти в статье Приложения [в Teams](https://teams.microsoft.com/l/app/4c4ec2e8-4a2c-4bce-8d8f-00fc664a4e5b?source=store-copy-link) и **в** статье Управление приложениями в Teams центре администрирования.

### <a name="control-access-to-bookings-within-your-organization"></a>Управление доступом к Bookings в организации

Существует несколько способов управления доступом к приложению Bookings и определенным функциям приложения.

Чтобы узнать, как включить или отключить Microsoft Bookings в Центр администрирования Microsoft 365 и как создать политику приложения Bookings, позволяющую выбранным пользователям создавать календари [Bookings,](https://support.microsoft.com/en-us/office/get-access-to-microsoft-bookings-5382dc07-aaa5-45c9-8767-502333b214ce)см. в этой теме.

Вы также можете создать политику Teams приложения, чтобы [закрепить приложение Bookings для некоторых пользователей.](teams-app-setup-policies.md)

## <a name="recommended-meeting-policy-settings"></a>Рекомендуемые параметры политики собраний

Чтобы обеспечить оптимальный опыт работы с Bookings, создайте политику  Teams собрания, чтобы автоматически допустить всех пользователей в организации и назначить ее сотрудникам. Это позволит сотрудникам автоматически присоединяться к встрече и включить работу с "lobby" для внешних участников. Подробнее об автоматическом допуске людей [к собраниям.](meeting-policies-participants-and-guests.md#automatically-admit-people)

## <a name="optional-staff-approvals-setting"></a>Дополнительная настройка согласования с сотрудниками

В качестве дополнительного параметра конфиденциальности вы можете указать, что сотрудники должны выразить свое согласие на участие прежде, чем сведения о доступности расписания будут опубликованы через Bookings и для этих сотрудников может быть запланировано собрание.  

Чтобы включить этот параметр, перейдите **в** Центр администрирования Microsoft 365 \> **Параметры** \> **Параметры** и выберите **Bookings**.

Если этот параметр включен, сотрудники получат сообщение электронной почты, в котором им будет предложено утвердить членство в календаре резервирования.  

Эта функция будет постепенно развертываться по всему миру для пользователей Microsoft 365 и Office 365. Если в вашей среде пока недоступны все параметры, проверьте это в ближайшее время.

## <a name="changing-your-default-domain-when-setting-up-bookings-mailboxes"></a>Изменение домена по умолчанию при настройке почтовых ящиков Bookings

При настройке почтового ящика Bookings используется домен электронной почты по умолчанию вашей организации Microsoft 365 или Office 365. Однако это может привести к проблемам при отправке приглашений на собрание внешним получателям; ваше приглашение может быть помечено как спам и перемещено в папку нежелательной почты, и получатель может никогда не увидеть ваше приглашение.

Рекомендуем изменить домен по умолчанию перед созданием почтового ящика Bookings. Сведения о том, как это сделать, см. в разделе [Вопросы и ответы по доменам](/microsoft-365/admin/setup/domains-faq#how-do-i-set-or-change-the-default-domain-in-office-365).

Если после создания почтового ящика Bookings нужно изменить домен по умолчанию, это можно сделать с помощью PowerShell:

```PowerShell
Set-Mailbox -identity business@domain.onmicrosoft.com -WindowsEmailAddress business@domain.com -EmailAddresses business@domain.com
```

Дополнительные сведения см. в документации по PowerShell для командлета [Set-Mailbox](/powershell/module/exchange/mailboxes/set-mailbox).

> [!NOTE]
> Если вы используете гибридную конфигурацию Exchange, мы рекомендуем тщательно проверить потоки почты между локальной Exchange и Exchange Online при изменении домена по умолчанию.

## <a name="sending-feedback"></a>Отправка отзывов

Отзывы можно отправлять по адресу:

  - Впечатления от использования или удобство использования
  - Пробелы в функциях или отсутствие функций
  - Дефекты и проблемы
  
Чтобы отправить отзыв,  в нижней части панели навигации слева Teams  кнопку Справка, а затем выберите Сообщить о проблеме **для ВСЕХ.** Указать в начале отчета о отзывах, что вы отправляете отзыв о "Bookings", чтобы мы могли легко определить проблемы с Bookings.

## <a name="related-articles"></a>Статьи по теме

[Управление опытом присоединиться к Teams виртуальных посещений в мобильных браузерах](expand-teams-across-your-org/mobile-browser-join.md)


  [Документация по Bookings для конечных пользователей](https://support.office.com/en-us/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b?ui=en-US&rs=en-US&ad=US#PickTab=Bookings)
