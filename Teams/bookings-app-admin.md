---
title: Виртуальные посещения с помощью Microsoft Teams и приложения Bookings
author: msdmaguire
ms.author: dmaguire
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
localization_priority: Normal
ms.collection:
- microsoftcloud-healthcare
ms.reviewer: ''
description: Microsoft Teams и виртуальные посещения с помощью приложения Bookings
ms.openlocfilehash: 684c442765b868ca96e9d1bf243817f9378f0b5d
ms.sourcegitcommit: 62d5ccf10202a50755166e3b8de0bd31d1f94fef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/28/2020
ms.locfileid: "48790621"
---
# <a name="virtual-visits-with-microsoft-teams-and-the-bookings-app"></a>Виртуальные посещения с помощью Microsoft Teams и приложения Bookings

Приложение Bookings в Microsoft Teams позволяет легко запланировать линую и виртуальную встречу, например посещение здравоохранения, консультации по финансам, собеседования, поддержку клиентов, учебные часы и многое другое.

Планиры могут управлять несколькими календарями отделов и сотрудников, а также общением с внутренними и внешними участниками из единого взаимодействия. Виртуальные встречи проводятся с помощью собраний Microsoft Teams, что обеспечивает надежные возможности видеоконференции.

> [!NOTE]
> Только планиры должны иметь приложение Bookings, установленное в Teams. Приложение не требуется для проведения виртуальных встреч и участия в них сотрудников. Они могут просто присоединиться к встречам из календаря Outlook или Teams или по ссылке в сообщении с подтверждением резервирования.

## <a name="prerequisites-for-using-the-bookings-app-in-teams"></a>Предварительные условия для использования приложения Bookings в Teams

- Почтовый ящик Exchange должен быть в Exchange Online. Локальное Exchange Server не поддерживается.

- Для организации должна быть включена служба Microsoft Bookings.

- У пользователей должна быть соответствующая лицензия. Поддерживаются Office 365 A3, A5, E3 и E5, а также Microsoft 365 бизнес стандартный, A3, A5, E3 и E5.

- У всех пользователей приложения Bookings и всех сотрудников, участвующих в собраниях, должна быть лицензия, которая поддерживает планирование собраний Teams.

- Ваши системы должны соответствовать всем требованиям [к Программному обеспечению и браузеру.](hardware-requirements-for-the-teams-app.md)

## <a name="availability-of-bookings-in-teams"></a>Доступность Bookings в Teams

Приложение Microsoft Bookings для Teams доступно в классических и веб-приложениях. Его можно найти в приложениях [в Microsoft Teams](https://teams.microsoft.com/l/app/4c4ec2e8-4a2c-4bce-8d8f-00fc664a4e5b?source=store-copy-link) и в области **"Управление** приложениями" в Центре администрирования Teams.

### <a name="control-access-to-bookings-within-your-organization"></a>Управление доступом к Bookings в организации

Существует несколько способов контроля доступа к приложению Bookings и его функциям. Чтобы узнать, как включить или отключить Microsoft Bookings в Центре администрирования Microsoft 365, а также как создать политику приложения Bookings, разрешаемую выбранным пользователям создавать календари [Bookings,](https://support.microsoft.com/en-us/office/get-access-to-microsoft-bookings-5382dc07-aaa5-45c9-8767-502333b214ce)см. в этом случае. Вы также можете узнать, как создать политику приложения Teams, чтобы закрепить [приложение Bookings для некоторых пользователей.](teams-app-setup-policies.md)

## <a name="recommended-meeting-policy-settings"></a>Рекомендуемые параметры политики собраний

Чтобы обеспечить наилучшее впечатление от работы с Bookings, создайте политику собраний для сотрудников, чтобы автоматически допустить всех сотрудников **в организации.** Это позволит сотрудникам автоматически присоединяться к встрече и разрешит участникам внешних участников в "вестибюле". Вы можете подробнее узнать об [автоматическом допуске людей к собраниям.](meeting-policies-in-teams.md#automatically-admit-people)

### <a name="optional-staff-approvals-setting"></a>Необязательный параметр утверждения сотрудников

В качестве дополнительного параметра конфиденциальности вы можете потребовать от сотрудников делиться сведениями о доступности по расписанию в Службе Bookings и запланировать их на встречу.  

Чтобы включить этот параметр, перейдите в параметры Центра администрирования **Microsoft 365** и выберите \>  \>  **"Bookings".**

Если этот параметр включен, сотрудники получают сообщение электронной почты, в котором им будет предложено утвердить членство в календаре резервирования.  

Эта функция постепенно становится общенародной для клиентов Microsoft 365 и Office 365. Если в вашей среде пока нет всех параметров, проверьте их в ближайшее время.

## <a name="changing-your-default-domain-when-setting-up-bookings-mailboxes"></a>Изменение домена по умолчанию при настройке почтовых ящиков Bookings

При настройке почтового ящика Bookings используется стандартный домен электронной почты вашей организации Microsoft 365 или Office 365. Однако это может привести к проблемам при отправке приглашений на собрания внешним получателям. Ваше приглашение может быть помечено как нежелательное и перемещено в папку нежелательной почты получателя, чтобы получатель не видел ваше приглашение.

Рекомендуем изменить домен по умолчанию перед созданием почтового ящика Bookings. Сведения о том, как это сделать, см. в вопросе и вопросе о [доменах.](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq#how-do-i-set-or-change-the-default-domain-in-office-365)

Если вам нужно изменить домен по умолчанию после создания почтового ящика Bookings, вы можете сделать это с помощью PowerShell:

```PowerShell
Set-Mailbox -identity business@domain.onmicrosoft.com -WindowsEmailAddress business@domain.com -EmailAddresses business@domain.com
```

Дополнительные сведения см. в документации PowerShell для [cmdlet Set-Mailbox.](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-mailbox)

> [!NOTE]
> Если используется гибридная конфигурация Exchange, мы рекомендуем тщательно проверить потоки почты между локальной сетью Exchange и Exchange Online при изменении домена по умолчанию.

## <a name="sending-feedback"></a>Отправка отзыва

Мы будем рады вашим отзывам о:

  - Пользовательский интерфейс и простота использования
  - Недочеты функций или отсутствие функций
  - Ошибки и проблемы
  
Чтобы отправить отзыв, нажмите кнопку **"Справка"** в нижней части левой панели навигации Teams, а затем выберите "Сообщить о проблеме для **ВСЕХ** проблем".  Обратите внимание в начале отчета о том, что вы отправляете отзыв о bookings, чтобы мы могли легко определить проблемы с Bookings.

## <a name="related-topics"></a>Статьи по теме

[Документация по Bookings для конечных пользователей](https://support.office.com/en-us/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b?ui=en-US&rs=en-US&ad=US#PickTab=Bookings)
