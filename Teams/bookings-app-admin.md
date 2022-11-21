---
title: Управление приложением Bookings в Microsoft Teams
author: LanaChin
ms.author: v-lanachin
manager: samanro
audience: ITPro
ms.topic: how-to
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
- m365-frontline
- tier2
- highpri
ms.reviewer: ''
description: Узнайте, как управлять приложением Bookings в Teams для пользователей в вашей организации.
ms.openlocfilehash: 4669b27efb351c375d5d5fd1104843e21c6f5ba9
ms.sourcegitcommit: ff161779577ce9cc892f1b6b8861ad49ff4c3ca3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2022
ms.locfileid: "69131308"
---
# <a name="manage-the-bookings-app-in-microsoft-teams"></a>Управление приложением Bookings в Microsoft Teams

Приложение Bookings в Microsoft Teams предлагает простой способ планировать очно и виртуальные встречи. Например, визиты в медицинские учреждения, финансовые консультации, собеседования, поддержка клиентов и учебные часы. Дополнительные сведения см. в статье [Виртуальные встречи с Teams и приложение Bookings](/microsoft-365/frontline/bookings-virtual-visits).

Планировщики могут управлять несколькими календарями отделов и сотрудников, а также взаимодействием с внутренними и внешними участниками из одного интерфейса. Виртуальные встречи проводятся с помощью собраний Microsoft Teams, которые предоставляют надежные возможности видеоконференций.

> [!NOTE]
> Приложение Bookings необходимо устанавливать только для планировщиков в Teams. Сотрудникам, которые проводят или участвуют в виртуальных встречах, приложение не требуется. Они могут просто присоединиться к встречам из своего календаря Outlook или Teams или по ссылке на собрание Teams в сообщении электронной почты с подтверждением бронирования.

## <a name="prerequisites-to-use-the-bookings-app-in-teams"></a>Предварительные требования для использования приложения Bookings в Teams

* Почтовый ящик Exchange находится в Exchange Online. Локальные почтовые ящики Exchange Server не поддерживаются.
* Microsoft Bookings доступно для организации.
* У пользователей есть соответствующая лицензия. поддерживаются Office 365 A3, A5, E1, E3, E5, F1, F3, Microsoft 365 A3, A5, E3, E5, F1, F3 и Business Standard.
* Все пользователи приложения Bookings и все сотрудники, участвующие в собраниях, имеют лицензию, которая поддерживает планирование собраний Teams.
* [Предварительные требования к программному обеспечению и браузеру](hardware-requirements-for-the-teams-app.md).

## <a name="availability-of-bookings-in-teams"></a>Доступность Bookings в Teams

Microsoft Bookings приложение для Teams доступно на рабочем столе и в Интернете. Его можно найти в разделе [Приложения в Teams](https://teams.microsoft.com/l/app/4c4ec2e8-4a2c-4bce-8d8f-00fc664a4e5b?source=store-copy-link) и **в разделе Управление приложениями** в Центре администрирования Teams.

### <a name="control-access-to-bookings-within-your-organization"></a>Управление доступом к Bookings в организации

Существует несколько способов управления доступом к приложению Bookings и определенным функциям приложения. Вы можете сделать приложение Microsoft Bookings доступным или отключить его в Центр администрирования Microsoft 365. Кроме того, можно создать политику приложения Bookings, чтобы разрешить избранным пользователям создавать календари Bookings. См[. статью Получение доступа к Microsoft Bookings](/microsoft-365/bookings/get-access).

Вы также можете [создать политику настройки приложения Teams, чтобы закрепить приложение Bookings для избранных пользователей](teams-app-setup-policies.md).

## <a name="recommended-meeting-policy-settings"></a>Рекомендуемые параметры политики собраний

Чтобы обеспечить оптимальное взаимодействие с Bookings, создайте политику собраний Teams, чтобы автоматически принимать **всех пользователей в вашей организации** и назначить ее сотрудникам. Эта политика позволяет сотрудникам автоматически присоединиться к встрече и включить функцию лобби для внешних участников. Узнайте [, как автоматически принимать людей на собрания](meeting-policies-participants-and-guests.md#automatically-admit-people).

Дополнительные сведения о политиках собраний см. [в разделах Управление политиками собраний в Teams](meeting-policies-in-teams.md) и [Политики собраний и истечение срока действия собрания в Teams](meeting-expiration.md).

## <a name="optional-staff-approvals-setting"></a>Дополнительная настройка согласования с сотрудниками

Вы можете потребовать, чтобы сотрудники согласились на участие, прежде чем Bookings пошлет им сведения о доступности расписания, и прежде чем другие смогут запланировать встречу с ними.

Чтобы включить этот параметр, перейдите в **Центр администрирования Microsoft 365** \> **Параметры** \> **Параметры**, а затем выберите **Резервирования**.

Если этот параметр включен, сотрудники получают электронное письмо, в котором им предлагается утвердить членство в календаре бронирования.  

Эта функция будет постепенно развертываться по всему миру для пользователей Microsoft 365 и Office 365. Если все параметры еще не доступны в вашей среде, проверьте его в ближайшее время.

## <a name="changing-your-default-domain-when-setting-up-bookings-mailbox"></a>Изменение домена по умолчанию при настройке почтового ящика Bookings

При настройке почтового ящика Bookings используется домен электронной почты по умолчанию вашей организации Microsoft 365 или Office 365. Однако домен по умолчанию может вызвать проблемы при отправке приглашений на собрание внешним получателям. Например, ваше приглашение может быть помечено как спам и перемещено в папку нежелательной почты получателя, поэтому получатель может никогда не увидеть ваше приглашение.

Перед созданием почтового ящика Bookings рекомендуется изменить домен по умолчанию. См. [раздел Вопросы и ответы о доменах](/microsoft-365/admin/setup/domains-faq#how-do-i-set-or-change-the-default-domain-in-microsoft-365).

Если вам нужно изменить домен по умолчанию после создания почтового ящика Bookings, используйте PowerShell.

```PowerShell
Set-Mailbox -identity business@domain.onmicrosoft.com -WindowsEmailAddress business@domain.com -EmailAddresses business@domain.com
```

См. документацию по PowerShell по [командлету Set Mailbox](/powershell/module/exchange/mailboxes/set-mailbox) .

> [!NOTE]
> Если вы используете гибридную конфигурацию Exchange, рекомендуется тщательно протестировать поток обработки почты между локальной средой Exchange и Exchange Online при изменении домена по умолчанию.

## <a name="send-feedback"></a>Отправка отзывов

Отзывы можно отправлять по адресу:

* Впечатления от использования или удобство использования
* Пробелы в функциях или отсутствие функций
* Дефекты и проблемы
  
Чтобы отправить отзыв, выберите параметр **Справка** в нижней части левой панели навигации Teams, а затем выберите **Сообщить о проблеме** для **всех** проблем. Укажите в начале отчета о отзывах, что вы отправляете отзыв о "Bookings", чтобы мы могли легко выявлять проблемы с Bookings.

## <a name="related-articles"></a>Статьи по теме

[Управление интерфейсом присоединения для виртуальных встреч Teams в браузерах](/microsoft-365/frontline/browser-join)


  [Документация по Bookings для конечных пользователей](https://support.office.com/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b?ui=en-US&rs=en-US&ad=US#PickTab=Bookings)
