---
title: Виртуальные визиты с помощью Microsoft Teams и приложения Bookings
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
description: Приложение Bookings и виртуальные визиты в Microsoft Teams
ms.openlocfilehash: cf6154099db5b6c6b52b9d82b4e58cd6c00c07b3
ms.sourcegitcommit: 1c2364fbefd95151f0847a35e8bc7c4c1b3892f5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/08/2021
ms.locfileid: "58935865"
---
# <a name="virtual-visits-with-microsoft-teams-and-the-bookings-app"></a>Виртуальные визиты с помощью Microsoft Teams и приложения Bookings

Приложение Bookings в Microsoft Teams предлагает простой способ запланировать личные и виртуальные встречи, например посещение врача, финансовые консультации, собеседования, поддержку клиентов, учебные часы и многое другое.

Планировщики могут управлять несколькими календарями отделов и сотрудников, а также взаимодействием с внутренними и внешними участниками одной встречи. Сами виртуальные встречи проводятся с помощью собраний Microsoft Teams, что обеспечивает надежные возможности видеоконференции.

> [!NOTE]
> Приложение Bookings необходимо устанавливать только для планировщиков в Teams. Сотрудники, участвующие в виртуальных встречах или проводящие их, не нуждаются в этом приложении. Они могут просто присоединяться к встречам из календаря Outlook или Teams или по ссылке в электронном письме с подтверждением резервирования.

## <a name="prerequisites-for-using-the-bookings-app-in-teams"></a>Необходимые условия для использования приложения Bookings в Teams

- Почтовый ящик Exchange должен быть в Exchange Online. Почтовые ящики, размещенные на локальном сервере Exchange Server, не поддерживаются.

- Для организации должна быть включена служба Microsoft Bookings.

- У пользователей должна быть соответствующая лицензия. Office 365 A3, A5, E3, E5, F1, F3, Microsoft 365 A3, A5, E3 и E5, бизнес-стандарт.

- У всех пользователей приложения Bookings и всех сотрудников, участвующих в собраниях, должна быть лицензия, которая поддерживает планирование собраний Teams.

- Ваши системы должны соответствовать всем [требованиям к программному обеспечению и браузеру](hardware-requirements-for-the-teams-app.md).

## <a name="availability-of-bookings-in-teams"></a>Доступность Bookings в Teams

Приложение Microsoft Bookings для Teams доступно в классической и Интернет-версии. Его можно найти в [приложениях в Microsoft Teams](https://teams.microsoft.com/l/app/4c4ec2e8-4a2c-4bce-8d8f-00fc664a4e5b?source=store-copy-link) и в разделе **Управление приложениями** в Центре администрирования Teams.

### <a name="control-access-to-bookings-within-your-organization"></a>Управление доступом к Bookings в организации

Существует несколько способов управления доступом к приложению Bookings и определенным функциям приложения. Чтобы узнать, как включить или отключить Microsoft Bookings в Центре администрирования Microsoft 365, а также как создать политику приложения Bookings, чтобы разрешить выбранным пользователям создавать календари Bookings, см. [Получить доступ к Microsoft Bookings](https://support.microsoft.com/en-us/office/get-access-to-microsoft-bookings-5382dc07-aaa5-45c9-8767-502333b214ce). Вы также можете узнать, как [создать политику приложений Teams, чтобы закрепить приложение Bookings для выбранных пользователей](teams-app-setup-policies.md).

## <a name="recommended-meeting-policy-settings"></a>Рекомендуемые параметры политики собраний

Чтобы было удобнее всего работать с Bookings, создайте политику собраний персонала, которая автоматически допустит **Всех сотрудников организации**. Это позволит сотрудникам автоматически присоединяться к встрече и обеспечит возможность присоединения для внешних участников. Узнайте больше об [автоматическом допуске на собрания](meeting-policies-participants-and-guests.md#automatically-admit-people).

### <a name="optional-staff-approvals-setting"></a>Дополнительная настройка согласования с сотрудниками

В качестве дополнительного параметра конфиденциальности вы можете указать, что сотрудники должны выразить свое согласие на участие прежде, чем сведения о доступности расписания будут опубликованы через Bookings и для этих сотрудников может быть запланировано собрание.  

Чтобы включить эту настройку, перейдите в **Центр администрирования Microsoft 365** \> **Параметры** \> **Параметры**, а затем выберите **Bookings**.

Если этот параметр включен, сотрудники получат сообщение электронной почты, в котором им предложат согласиться на участие в календаре резервирования.  

Эта функция будет постепенно развертываться по всему миру для пользователей Microsoft 365 и Office 365. Если в вашей среде пока доступны не все возможности, проверяйте время от времени, не изменилась ли ситуация.

## <a name="changing-your-default-domain-when-setting-up-bookings-mailboxes"></a>Изменение домена по умолчанию при настройке почтовых ящиков Bookings

При настройке почтового ящика Bookings используется домен электронной почты по умолчанию вашей организации Microsoft 365 или Office 365. Однако это может привести к проблемам при отправке приглашений на собрание внешним получателям; ваше приглашение может быть помечено как спам и перемещено в папку нежелательной почты, и получатель может никогда не увидеть ваше приглашение.

Перед созданием почтового ящика Bookings рекомендуется изменить домен по умолчанию. Сведения о том, как это сделать, см. в разделе [Вопросы и ответы по доменам](/microsoft-365/admin/setup/domains-faq#how-do-i-set-or-change-the-default-domain-in-office-365).

Если после создания почтового ящика Bookings нужно изменить домен по умолчанию, это можно сделать с помощью PowerShell:

```PowerShell
Set-Mailbox -identity business@domain.onmicrosoft.com -WindowsEmailAddress business@domain.com -EmailAddresses business@domain.com
```

Дополнительные сведения см. в документации по PowerShell для командлета [Set-Mailbox](/powershell/module/exchange/mailboxes/set-mailbox).

> [!NOTE]
> Если вы используете гибридную конфигурацию Exchange, рекомендуем тщательно проверить движение почты между локальной версией Exchange и Exchange Online при изменении домена по умолчанию.

## <a name="sending-feedback"></a>Отправка отзывов

Отзывы можно отправлять по адресу:

  - Впечатления от использования или удобство использования
  - Пробелы в функциях или отсутствие функций
  - Дефекты и проблемы
  
Чтобы отправить сообщение, для **ВСЕХ** проблем нажмите кнопку **Справка** в нижней части левой панели навигации Teams, а затем **Сообщить о проблеме**. В самом начале отзыва просим указать, что это отзыв по приложению Bookings - тогда мы сможем легко отличать сообщения, касающиеся приложения Bookings.

## <a name="related-topics"></a>Родственные темы

[Управление опытом join для Teams виртуальных посещений в мобильных браузерах](expand-teams-across-your-org/mobile-browser-join.md)


  [Документация по Bookings для конечных пользователей](https://support.office.com/en-us/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b?ui=en-US&rs=en-US&ad=US#PickTab=Bookings)
