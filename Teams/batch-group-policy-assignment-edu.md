---
title: Назначение политик большому набору пользователей в учебном за учебных заведениях
author: DaniEASmith
ms.author: danismith
manager: serdars
ms.reviewer: karsmith, angch, cebulnes
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- remotework
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
search.appverid: MET150
description: Узнайте, как назначать политики большому набору пользователей в учебном заведении на основе участия в группах или непосредственно с помощью пакетного задания для удаленного учебного заведения (телеучреждения, телеучреждения).
f1keywords: ''
ms.openlocfilehash: 3cfde2dc523904f571b696e63ea7a5da16afff26
ms.sourcegitcommit: 1129841e68e927fe7cc31de3ad63a3e9247253cd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2022
ms.locfileid: "62362995"
---
# <a name="assign-policies-to-large-sets-of-users-in-your-school"></a>Назначение политик большому набору пользователей в учебном за учебных заведениях

[!INCLUDE [policy-wizard-edu](includes/policy-wizard-edu.md)]

> [!NOTE]
> Подробнее о назначении политик в Microsoft Teams см. в [Teams.](policy-assignment-overview.md)

## <a name="overview"></a>Обзор

Нужно ли предоставить учащимся и преподавателям доступ к различным функциям в Microsoft Teams? Вы можете быстро определить пользователей в организации по типу лицензии, а затем назначить им соответствующую политику. В этом учебнике показано, как назначить политику собраний большому набору пользователей в вашем учебном за учебных заведениях. Вы можете назначать политики с помощью Microsoft Teams администрирования и PowerShell, и мы покажем вам оба способа.

Вы можете назначить политику собраний группе безопасности, участниками или непосредственно пользователями в масштабе пакета назначения политики. После прочтения этой статьи вы сможете следующее.

- **Назначение [политик группам используется](#assign-a-policy-to-a-group) для назначения политики собраний группе безопасности (рекомендуется).** Этот способ позволяет назначить политику на основе участия в группах. Политику можно назначить группе безопасности или списку рассылки. По мере того как участники добавляются в группу или удаляются из нее, их унаследованные назначения политики обновляются соответствующим образом. Мы рекомендуем использовать этот метод, так как он сокращает время на управление политиками для новых пользователей или изменение ролей пользователей. Этот метод лучше всего работает для групп до 50 000 пользователей, но также работает с более крупными группами.

- **Назначение [пакетной политики позволяет](assign-policies-users-and-groups.md#assign-a-policy-to-a-batch-of-users) массово** назначать политику собраний пользователям. Одновременно можно назначить политику для 5000 пользователей. Если у вас более 5000 пользователей, вы можете отправить несколько пакетов. При этом способе при новых пользователях потребуется повторно запустить пакетное назначение, чтобы назначить политику новым пользователям.

Помните, Teams пользователи автоматически получают глобальную политику (стандартную для всей организации) для типа политики Teams, если не создать и не назначить настраиваемую политику. Так как среди учащихся часто самый большой набор пользователей и они часто получают самые строгие параметры, рекомендуем сделать следующее:

- Создайте настраиваемую политику, которая позволяет использовать основные возможности, такие как частный чат и планирование собраний, а также назначить политику сотрудникам и преподавателям.
- Назначьте настраиваемую политику сотрудникам и преподавателям.
- Изменение и применение глобальной политики (по умолчанию в организации) для ограничения возможностей учащихся.

Имейте в виду, что глобальная политика будет применяться к всем пользователям в вашем учебном за заведениях, пока вы не создайте настраиваемую политику и не назначите ее сотрудникам и преподавателям.

В этом учебнике учащиеся получат глобальную политику собраний, и мы назначим сотрудникам и преподавателям настраиваемую политику собраний с именем EducatorMeetingPolicy. Предполагается, что вы влияли на глобальную политику, чтобы настроить параметры собраний для учащихся, и создали настраиваемую политику, которая определяет параметров собраний для преподавателей и преподавателей.[](policy-packages-edu.md)

![Снимок экрана: страница "Политики собраний" в Teams администрирования.](media/batch-group-policy-assignment-edu-meeting-policies.png)

## <a name="assign-a-policy-to-a-group"></a>Назначение политики группе

Выполните эти действия, чтобы создать группу безопасности для сотрудников и преподавателей, а затем назначить для нее настраиваемую политику собраний с именем EducatorMeetingPolicy.

### <a name="before-you-get-started"></a>С чего начать

> [!IMPORTANT]
> При назначении группе политики назначение распространяется на ее участников в соответствии с правилами приоритета. Например, если пользователю непосредственно назначена политика (по отдельности или с помощью пакетного назначения), она имеет приоритет над политикой, наследуемой от группы. Это также означает, что если пользователю назначена политика собраний, вам придется удалить ее у пользователя, прежде чем он сможет наследовать политику собраний от группы безопасности.

Перед началом работы важно разобраться в правилах приоритета [и ранжирования](policy-assignment-overview.md#which-policy-takes-precedence) [заданий групп](assign-policies-users-and-groups.md#group-assignment-ranking). **Убедитесь в том, что вы читаете [](assign-policies-users-and-groups.md#what-you-need-to-know-about-policy-assignment-to-groups)** и понимаете понятия в области Что необходимо знать о назначении политик группам.

Чтобы наследовать политику собраний от группы безопасности, необходимо выполнить все эти действия для преподавателей и сотрудников.

1. [Создавайте группы безопасности](#create-security-groups).
2. [Назначьте политику группе безопасности](#assign-a-policy-to-a-security-group).
3. [Удалите политику, которая была непосредственно назначена пользователям](#remove-a-policy-that-was-directly-assigned-to-users).

### <a name="create-security-groups"></a>Создание групп безопасности

Сначала создайте группу безопасности для сотрудников и преподавателей.

С [Синхронизация сведений о школе](/SchoolDataSync/) (SDS) вы можете легко создавать группы безопасности для преподавателей и [учащихся](/SchoolDataSync/edu-security-groups) в вашем учебном за учебных заведениях. Мы рекомендуем использовать SDS для создания групп безопасности, необходимых для управления политиками для вашего учебного заведения.

Если вам не удается развернуть SDS в своей среде, используйте этот сценарий [PowerShell](scripts/powershell-script-security-groups-edu.md) , чтобы создать две группы безопасности: одну для всех сотрудников и преподавателей, которым назначена лицензия преподавателя, а другую — для всех студентов, которым назначена лицензия "Студент". Этот сценарий необходимо регулярно запускать, чтобы группы всегда были в курсе.

### <a name="assign-a-policy-to-a-security-group"></a>Назначение политики группе безопасности

#### <a name="using-the-microsoft-teams-admin-center"></a>С помощью Центра администрирования Microsoft Teams

> [!NOTE]
> В настоящее время назначение политик группам, использующим Центр администрирования Microsoft Teams, доступно только для политик Teams звонков, политики Teams парк звонков, политики Teams, политики трансляций Teams, политики собраний Teams и политики Teams сообщений. Для других типов политик используйте PowerShell.

1. В Центре администрирования Microsoft Teams в области навигации слева выберите **Собрания** > **Политики собраний**.
2. Выберите **вкладку Назначение групповой** политики.
3. Выберите **добавить группу**, а затем в области **Назначение** политики группе сделайте следующее:

    ![Снимок экрана: в области "Изменение параметров" отображается политика собрания.](media/batch-group-policy-assignment-edu-group.png)
    1. В поле **Выберите группу** найщите и добавьте группу безопасности, которая содержит сотрудников и преподавателей.
    2. В поле **Выбрать ранг** введите **1**.
    3. В поле **Выберите политику выберите** **EducatorMeetingPolicy**.
    4. Выберите **Применить**.

Чтобы удалить назначение групповой политики, на вкладке Назначение групповой политики страницы политики выберите назначение группы, а затем выберите **Удалить**.

Чтобы изменить ранжирование назначения группы, необходимо сначала удалить назначение групповой политики. Затем, следуя этим шагам, назначьте политику группе.

#### <a name="using-powershell"></a>С помощью PowerShell

> [!NOTE]
> В настоящее время назначения политик группам, использующим PowerShell, доступны не для Teams типов политик. Список поддерживаемых типов политик см. в списке [New-CsGroupPolicyAssignment](/powershell/module/teams/new-csgrouppolicyassignment) .

##### <a name="install-and-connect-to-the-microsoft-teams-powershell-module"></a>Установка и подключение к Microsoft Teams PowerShell

Чтобы установить модуль [PowerShell Teams PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams), запустите следующую: Установите версию 1.0.5 или более поздней.

```powershell
Install-Module -Name MicrosoftTeams
```

Чтобы подключиться к Teams и начать сеанс, запустите следующую:

```powershell
Connect-MicrosoftTeams
```

Когда вам будет предложено, войте в учетные данные администратора.

##### <a name="assign-a-policy-to-a-group"></a>Назначение политики группе

Чтобы назначить политику собраний с именем EducatorMeetingPolicy группе безопасности, которая содержит сотрудников и преподавателей, и задайте для ранжирования заданий 1. Группу безопасности можно указать с помощью ИД объекта, SIP-адреса или адреса электронной почты. В этом примере используется адрес электронной почты (staff-faculty@contoso.com).

```powershell
New-CsGroupPolicyAssignment -GroupId staff-faculty@contoso.com -PolicyType TeamsMeetingPolicy -PolicyName "EducatorMeetingPolicy" -Rank 1
```

### <a name="remove-a-policy-that-was-directly-assigned-to-users"></a>Удаление политики, которая была непосредственно назначена пользователям

Помните, что если пользователю была непосредственно назначена политика (по отдельности или с помощью пакетного назначения), она имеет приоритет. Это означает, что если пользователю назначена политика собраний, вам придется удалить ее у пользователя, прежде чем он сможет наследовать политику собраний от группы безопасности.

Дополнительные информацию см. в том, [что нужно знать о назначении политик группам](assign-policies-users-and-groups.md#what-you-need-to-know-about-policy-assignment-to-groups).

Выполните эти действия, чтобы удалить политику собраний, которая была непосредственно назначена вашим сотрудникам и преподавателям.

#### <a name="install-and-connect-to-the-microsoft-teams-powershell-module"></a>Установка и подключение к Microsoft Teams PowerShell

Чтобы установить модуль [PowerShell Teams PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams), запустите следующую: Установите версию 1.0.5 или более поздней.

```powershell
Install-Module -Name MicrosoftTeams
```

Чтобы подключиться к Teams и начать сеанс, запустите следующую:

```powershell
Connect-MicrosoftTeams
```

В окне запроса войтесь в службу с помощью учетных данных администратора, которые использовались для подключения к Azure AD.

#### <a name="unassign-a-policy-that-was-directly-assigned-to-users"></a>Отогнание политики, которая была непосредственно назначена пользователям

Чтобы удалить политику собраний у пользователей, которым она была непосредственно назначена, запустите следующую политику: Вы можете указать пользователей по адресу электронной почты или ид объекта.

В этом примере политика собраний удаляется с пользователей, указанных по их адресам электронной почты.

```powershell
$users_ids = @("reda@contoso.com", "nikica@contoso.com", "jamie@contoso.com")
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsMeetingPolicy -PolicyName $null -Identity $users_ids -OperationName "Unassign meeting policy"
```

В этом примере политика собрания удаляется из списка пользователей в текстовом файле с именем user_ids.txt.

```powershell
$user_ids = Get-Content .\users_ids.txt
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsMeetingPolicy -PolicyName $null -Identity $users_ids -OperationName "Unassign meeting policy"
```

##### <a name="get-policy-assignments-for-a-group"></a>Получить назначения политик для группы

Чтобы увидеть все политики, которые назначены определенной группе безопасности, запустите следующую: Обратите внимание, что группы всегда указаны по их групповому ИД, даже если для назначения политики использовался SIP-адрес или адрес электронной почты.

```powershell
Get-CsGroupPolicyAssignment -GroupId staff-faculty@contoso.com

```

##### <a name="get-the-policies-assigned-to-a-user"></a>Получить политики, которые назначены пользователю

Чтобы увидеть все политики, которые назначены конкретному пользователю, запустите следующую: В следующем примере показано, как получить политики, которые назначены reda@contoso.com.

```powershell
Get-CsUserPolicyAssignment -Identity reda@contoso.com
```

## <a name="assign-a-policy-to-a-batch-of-users"></a>Назначение политики для пакета пользователей

Чтобы массово назначить сотрудникам и преподавателям настраиваемую политику собраний с именем EducatorMeetingPolicy, выполните указанные здесь действия.

### <a name="using-powershell"></a>С помощью PowerShell

#### <a name="connect-to-the-azure-ad-powershell-for-graph-module-and-the-teams-powershell-module"></a>Подключение в azure AD PowerShell для Graph и Teams PowerShell

Перед выполнением действий, которые были выполнены в этой статье, необходимо установить модуль Azure AD PowerShell для Graph (для идентификации пользователей по назначенной лицензии) и модуль PowerShell Microsoft Teams (чтобы назначить политики этим пользователям).

##### <a name="install-and-connect-to-the-azure-ad-powershell-for-graph-module"></a>Установка и подключение к Azure AD PowerShell для Graph windows

Откройте командную Windows PowerShell с повышенными Windows PowerShell (запустите его от Windows PowerShell администратора) и запустите следующую команду, чтобы установить Azure Active Directory PowerShell для Graph PowerShell.

```powershell
Install-Module -Name AzureAD
```

Чтобы подключиться к Azure AD, запустите следующую службу:

```powershell
Connect-AzureAD
```

Когда вам будет предложено, войте в учетные данные администратора.

Дополнительные дополнительные Подключение [с помощью Azure Active Directory PowerShell для Graph powershell](/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module).

##### <a name="install-and-connect-to-the-microsoft-teams-powershell-module"></a>Установка и подключение к Microsoft Teams PowerShell

Чтобы установить модуль [PowerShell Teams PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams), запустите следующую: Установите версию 1.0.5 или более поздней.

```powershell
Install-Module -Name MicrosoftTeams
```

Чтобы подключиться к Teams и начать сеанс, запустите следующую:

```powershell
Connect-MicrosoftTeams
```

В окне запроса войтесь в службу с помощью учетных данных администратора, которые использовались для подключения к Azure AD.

#### <a name="identify-your-users"></a>Определение пользователей

Сначала запустите следующую, чтобы определить сотрудников и преподавателей по типу лицензии. Это указывает, какие skus используются в вашей организации. Затем вы сможете определить сотрудников и преподавателей, которые имеют SKU преподавателей.

```powershell
Get-AzureAdSubscribedSku | Select-Object -Property SkuPartNumber,SkuId
```

Возвращает:

```
SkuPartNumber      SkuId
-------------      -----
M365EDU_A5_FACULTY e97c048c-37a4-45fb-ab50-922fbf07a370
M365EDU_A5_STUDENT 46c119d4-0379-4a9d-85e4-97c66d3f909e
```

В этом примере показано, что SKUId лицензии преподавателей — e97c048c-37a4-45fb-ab50-922fbf07a370".

> [!NOTE]
> Список SKU и SKU для образования см. в справке [по SKU для образования](sku-reference-edu.md).

Затем мы запускаем следующую, чтобы определить пользователей, у которых есть эта лицензия, и собрать их вместе.

```powershell
$faculty = Get-AzureADUser -All $true | Where-Object {($_.assignedLicenses).SkuId -contains "e97c048c-37a4-45fb-ab50-922fbf07a370"}
```

#### <a name="assign-a-policy-in-bulk"></a>Массовое назначение политики

Теперь мы массово назначаем пользователям подходящие политики. Максимальное количество пользователей, для которых можно назначить или обновить политики, составляет 5000 за раз. Например, если у вас более 5000 сотрудников и преподавателей, вам потребуется отправить несколько пакетов.

Чтобы назначить сотрудникам и преподавателям настраиваемую политику собраний с именем EducatorMeetingPolicy, запустите следующую:

```powershell
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsMeetingPolicy -PolicyName EducatorMeetingPolicy -Identity $faculty.ObjectId
```

> [!NOTE]
> Чтобы массово назначить другой тип политики, например TeamsMessagingPolicy, необходимо изменить политику, которую назначаете, ```PolicyType``` ```PolicyName``` и имя политики.

#### <a name="get-the-status-of-a-bulk-assignment"></a>Получить состояние массовой рассылки

Каждое массовое назначение возвращает ИД операции, который можно использовать для отслеживания хода выполнения назначений политики или выявления сбоев, которые могут возникнуть. Например, запустите следующую:

```powershell
Get-CsBatchPolicyAssignmentOperation -OperationId 3964004e-caa8-4eb4-b0d2-7dd2c8173c8c | fl
```

Чтобы просмотреть состояние назначения для каждого пользователя в пакетной операции, запустите следующую операцию: Сведения о каждом пользователе находятся в свойстве ```UserState``` .

```powershell
Get-CsBatchPolicyAssignmentOperation -OperationId 3964004e-caa8-4eb4-b0d2-7dd2c8173c8c | Select -ExpandProperty UserState
```

#### <a name="assign-a-policy-in-bulk-if-you-have-more-than-5000-users"></a>Массовое назначение политики, если у вас более 5000 пользователей

Сначала запустите следующую, чтобы узнать, сколько у вас сотрудников и преподавателей:

```powershell
$faculty.count
```

Вместо того чтобы предоставлять весь список ИД пользователей, укажите первые 5000, а затем следующие 5000 и так далее:

```powershell
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsMeetingPolicy -PolicyName EducatorMeetingPolicy -Identity $faculty[0..19999].ObjectId
```

Вы можете изменить диапазон ид пользователей, пока не достигнете полного списка пользователей. Например, введите ```$faculty[0..4999``` для первого пакета, ```$faculty[5000..9999``` для второго — второй, ```$faculty[10000..14999``` для третьего — и так далее.

#### <a name="get-the-policies-assigned-to-a-user"></a>Получить политики, которые назначены пользователю

Чтобы увидеть все политики, которые назначены конкретному пользователю, запустите следующую: В следующем примере показано, как получить политики, которые назначены hannah@contoso.com.

```powershell
Get-CsUserPolicyAssignment -Identity hannah@contoso.com
```

## <a name="faq"></a>Вопросы и ответы

**Я не знаком с PowerShell для Teams. Где можно узнать больше?**

Общие сведения об использовании PowerShell для управления Teams см. в Teams [PowerShell](teams-powershell-overview.md). Дополнительные сведения о используемых в этой статье cmdlets см. в статьях:

- [New-CsGroupPolicyAssignment](/powershell/module/teams/new-csgrouppolicyassignment)
- [Get-CsGroupPolicyAssignment](/powershell/module/teams/get-csgrouppolicyassignment)
- [New-CsBatchPolicyAssignmentOperation](/powershell/module/teams/new-csbatchpolicyassignmentoperation)
- [Get-CsBatchPolicyAssignmentOperation](/powershell/module/teams/get-csbatchpolicyassignmentoperation)
- [Get-CsUserPolicyAssignment](/powershell/module/teams/get-csuserpolicyassignment)

## <a name="related-topics"></a>Статьи по теме

- [Назначение политик пользователям](policy-assignment-overview.md)
- [Политики и пакеты политик Teams для образования](policy-packages-edu.md)
- [Управление политиками собраний в Teams](meeting-policies-overview.md)