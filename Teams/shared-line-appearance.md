---
title: Функция Shared Line Appearance в Microsoft Teams
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 02/19/2019
ms.reviewer: jenstr
ms.topic: conceptual
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Phone System
- ms.teamsadmincenter.users.voice.calldelegation.tooltip
- seo-marvel-apr2020
description: Сведения о функции внешнего вида строки "Общий доступ" в Microsoft Teams.
ms.openlocfilehash: 7e3259e948e5a3443d5959eef693416ca3d754ca
ms.sourcegitcommit: f0e2a5928e9b959daf45202b9f256f65c2087195
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/20/2022
ms.locfileid: "68614101"
---
# <a name="shared-line-appearance-in-microsoft-teams"></a>Функция Shared Line Appearance в Microsoft Teams

Внешний вид общей строки позволяет пользователю выбрать делегата для ответа или обработки звонков от его имени. Эта функция полезна, если у пользователя есть помощник по администрированию, который регулярно обрабатывает его вызовы. В контексте общего внешнего вида строки руководитель — это человек, который разрешает делегату совершать или принимать звонки от его имени. Делегат может совершать или принимать звонки от имени делегатора.

> [!IMPORTANT]
> Эта функция доступна только в режиме развертывания "Только Teams". Дополнительные сведения о режимах развертывания Teams см. в статье "Общие сведения о [Microsoft Teams и](teams-and-skypeforbusiness-coexistence-and-interoperability.md) Skype для бизнеса сосуществование и взаимодействие".

## <a name="license-required"></a>Требуется лицензия

Как руководители, так и делегаты должны иметь лицензию телефонной системы с подключением к ТСОП (план звонков, подключение оператора или прямая маршрутизация). Общий интерфейс строки является частью делегирования и входит в состав телефонной системы. Дополнительные сведения о лицензировании см. в описании [службы Microsoft Teams](/office365/servicedescriptions/teams-service-description).

## <a name="shared-line-appearance-feature-availability"></a>Доступность функции общего внешнего вида строки

Внешний вид общей строки в настоящее время поддерживается следующими приложениями и устройствами.

| Возможность | Рабочий стол Teams | Приложение Teams для Mac | Teams Web App (Edge) |Мобильное приложение Teams для iOS или Android | IP-телефон Teams |
|------------|---------------|---------------|----------------------|-----------------------------|----------------|
| Настройка делегирования | Да | Да | Да | Нет | Да |
| Получение вызовов от имени другого пользователя | Да | Да | Да | Да | Да |
| Вызов номера телефона от имени другого пользователя | Да | Да | Да | Да | Да |
| Вызов пользователя Teams от имени другого пользователя | Да | Да | Да | Да | Да |
| Просмотр представления делегата общих строк | Да | Да | Да | Нет | Да |
| Просмотр представления делегата для действий вызова руководителя | Да | Да | Да | Нет | Да |
| Просмотр представления руководителя делегатов | Да | Да | Да | Нет | Да |
| Делегат или руководитель может хранить или возобновлять работу | Да | Да | Да | Нет | Да |

## <a name="limitations"></a>Ограничения

Руководители могут добавить до 25 делегатов, а делегаты могут иметь до 25 руководителей. Количество связей делегирования, которые могут быть созданы в клиенте, не ограничивается. 
 
Если делегатор и делегат находятся не в одном географическом расположении, поставщик ТСОП должен разрешить отображение идентификатора вызывающего абонента из другого географического расположения для делегированного вызова. 

Конфигурация циклического делегирования не разрешена. Если делегированные пользователи также имеют делегирование между ними, они смогут видеть только свое делегирование, а не первоначальное делегирование.

## <a name="enable-delegation-and-shared-line-appearance"></a>Включение делегирования и общего внешнего вида строки

Делегирование включается с помощью **параметра AllowDelegation в TeamsCallingPolicy** . Вы можете использовать Центр администрирования Teams или Teamms PowerShell. 

Если этот параметр включен, конечный пользователь может настроить отношения делегирования непосредственно в Teams. 

> [!IMPORTANT]
> При отключении делегирования для пользователя необходимо также очистить связи делегирования для этого пользователя в Центре администрирования Teams, чтобы избежать неправильной маршрутизации вызовов.

## <a name="use-teams-admin-center"></a>Использование Центра администрирования Teams

Сведения о настройке делегирования и внешнего вида общей строки с помощью Центра администрирования Teams см. в разделе "Настройка параметров параметров зова [для пользователей"](/MicrosoftTeams/user-call-settings).

## <a name="use-powershell"></a>Использование PowerShell

Чтобы настроить делегирование и внешний вид общей строки с помощью Teams PowerShell, используйте следующие командлеты:

- [New-CsUserCallingDelegate](/powershell/module/teams/new-csusercallingdelegate)

- [Set-CsUserCallingDelegate](/powershell/module/teams/set-csusercallingdelegate)

- [Remove-CsUserCallingDelegate](/powershell/module/teams/remove-csusercallingdelegate)

### <a name="examples"></a>Примеры

В следующем примере user2@contoso.com в качестве делегата user1@contoso.com с разрешениями на выполнение и получение звонка от имени пользователя user1 и изменение параметров для других делегатов:

```powershell
New-CsUserCallingDelegate -Identity user1@contoso.com -Delegate user2@contoso.com -MakeCalls $true -ReceiveCalls $true -ManageSettings $true
```

В следующем примере делегату user2@contoso.com больше не разрешено совершать вызовы от имени пользователя user1:

```powershell
Set-CsUserCallingDelegate -Identity user1@contoso.com -Delegate user2@contoso.com -MakeCalls $false
```

В следующем примере user2@contoso.com удаляется как делегат user1@contoso.com:

```powershell
Remove-CsUserCallingDelegate -Identity user1@contoso.com -Delegate user2@contoso.com
```
 
## <a name="more-information"></a>Дополнительные сведения

[Предоставление общего доступа к телефонной линии делегату](https://support.office.com/article/share-a-phone-line-with-a-delegate-16307929-a51f-43fc-8323-3b1bf115e5a8)

[Политика звонков Teams](/MicrosoftTeams/teams-calling-policy)

[New-CsTeamsCallingPolicy](/powershell/module/skype/new-csteamscallingpolicy)

[Set-CsTeamsCallingPolicy](/powershell/module/skype/set-csteamscallingpolicy)
