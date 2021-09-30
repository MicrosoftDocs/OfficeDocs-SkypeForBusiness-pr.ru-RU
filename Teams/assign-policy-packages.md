---
title: Назначение пакетов политики пользователям и группам
author: KarliStites
ms.author: kastites
ms.reviewer: tomkau, saragava, ritikag, jastark
manager: serdars
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
search.appverid: MET150
description: Узнайте о различных способах назначения пакетов политики пользователям и группам в Microsoft Teams.
f1keywords:
- ms.teamsadmincenter.bulkoperations.users.edit
- ms.teamsadmincenter.bulkoperations.edit
ms.openlocfilehash: 553e30fa694403b2ad5e2edfd86b53fe8231eed3
ms.sourcegitcommit: efd56988b22189dface73c156f6f8738f273fa61
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/30/2021
ms.locfileid: "60015073"
---
# <a name="assign-policy-packages-to-users-and-groups"></a>Назначение пакетов политики пользователям и группам

В этой статье рассматриваются различные способы назначения пакетов политики пользователям и группам в Microsoft Teams. Перед чтением обязательно прочитайте статью Назначение политик в Teams [- начало работы.](policy-assignment-overview.md)

> [!NOTE]
> Для получения назначенного пользовательского пакета политик каждому пользователю будет необходима надстройка Advanced Communications. Дополнительные сведения см. в статье [Надстройка Advanced Communications для Microsoft Teams](/microsoftteams/teams-add-on-licensing/advanced-communications).

## <a name="assign-a-policy-package-to-users"></a>Назначение пакета политики пользователям

Пакет политики в Teams — это набор предопределевших политик и параметров политики, которые можно назначить пользователям с одинаковыми или похожими ролями в организации. Каждый пакет политики предназначен для роли пользователя и содержит стандартные политики и параметры политики, которые поддерживают типичные для нее действия. Некоторые примеры пакетов политики: пакет для образовательных учреждений (преподаватель) и пакет для медицинского обслуживания (медицинского работника). Дополнительные информации см. в [этой](manage-policy-packages.md)Teams.

### <a name="assign-a-policy-package-to-one-user"></a>Назначение пакета политики одному пользователю

1. В левой области навигации центра администрирования Microsoft Teams перейдите в меню Пользователи **и** выберите пользователя.

2. На странице пользователя выберите Политики **,** а затем рядом с пакетом **политики** выберите **Изменить**.

3. В **области Назначение пакета политики** выберите пакет, который вы хотите назначить, и выберите **сохранить**.

![Teams в Центре администрирования для назначения пользователю пакета политики.](media/assign-policypackages-user.png)

### <a name="assign-a-policy-package-to-multiple-users"></a>Назначение пакета политики нескольким пользователям

1. В левой области навигации центра администрирования Microsoft Teams перейдите в пакеты политики **,** а затем выберите пакет политики, который вы хотите назначить, щелкнув слева от имени пакета.

2. Выберите **Управление пользователями**.

3. В области **Управление пользователями** выполните поиск по отображаемому имени или по имени пользователя, выберите имя и нажмите **Добавить**. Повторите это действие для каждого пользователя, которого нужно добавить.

4. Завершив добавление пользователей, выберите **Сохранить**.


![Teams в Центре администрирования для назначения пакета политики нескольким пользователям.](media/assign-policypackages-multipleusers.png)


## <a name="assign-a-policy-package-to-a-group"></a>Назначение пакета политики группе

Назначение пакетов политики группам позволяет назначать несколько политик группе пользователей, например группе безопасности или группе рассылки. Назначение политики распространяется на участников группы в соответствии с правилами очередности. При добавлении или удалении участников группы, назначения политик для них обновляются соответствующим образом.

Назначение пакета политики группам рекомендуется для групп до 50 000 пользователей, но оно также будет работать с более крупными группами.

При назначении пакета политики он сразу же назначается группе. Однако распространение назначения политики на участников группы выполняется в фоновом режиме и может занять некоторое время в зависимости от размера группы. То же самое происходит, если политика не назначена группе, а также когда участники добавляются в группу или удаляются из нее.

> [!IMPORTANT]
> Перед началом работы важно понимать[(правила](assign-policies-users-and-groups.md#precedence-rules)приоритета) и ([ранжирование назначений группы).](assign-policies-users-and-groups.md#group-assignment-ranking) Убедитесь, что вы читаете и понимаете понятия[в](assign-policies-users-and-groups.md#what-you-need-to-know-about-policy-assignment-to-groups)( Что необходимо знать о назначении политик группам) ранее в этой статье.

### <a name="assign-a-policy-package-to-a-group-of-users-in-the-admin-center"></a>Назначение пакета политики группе пользователей в Центре администрирования

1. Войдите в Центр администрирования Teams.

2. На левой странице навигации перейдите на страницу пакета политики.

3. Выберите вкладку Назначение групповой политики.

4. Выберите **Добавить группу,** а затем в области Назначение пакета политики группе сделайте следующее:

    1. Найщите и добавьте группу, для нее нужно назначить пакет политики.

    1. Выберите пакет политики.

    1. Заведите ранжирование для каждого типа политики.

    1. Выберите **Применить**.


       ![показывает назначение групповой политики.](media/group-pkg-assignment.png)

5. Чтобы управлять ранжированием для определенного типа политики, перейдите на страницу политики.

6. Чтобы перена назначение пакета политики группе, сначала удалите назначение групповой политики. Затем следуйте этим шагам, чтобы назначить пакет политики группе.

### <a name="work-with-powershell"></a>Работа с PowerShell

#### <a name="get-the-teams-powershell-module"></a>Получить модуль Teams PowerShell

Пошаговую инструкцию см. в [Teams PowerShell.](teams-powershell-install.md)

#### <a name="assign-a-policy-package-to-a-group-of-users"></a>Назначение пакета политики группе пользователей

Чтобы назначить группе пакет политики, используйте [cmdlet Grant-CsGroupPolicyPackageAssignment.](/powershell/module/teams/grant-csgrouppolicypackageassignment) Группу можно указать с помощью ИД объекта, SIP-адреса или адреса электронной почты. При назначении пакета политики укажите[(ранжирование](assign-policies-users-and-groups.md#group-assignment-ranking)назначений группы) для каждого типа политики в пакете политики.

В этом примере пакет политики Education_Teacher назначается группе с ранжированием заданий 1 для TeamsAppSetupPolicy и TeamsMeetingBroadcastPolicy и 2 для TeamsMeetingPolicy и 2 для TeamsMeetingPolicy.

```powershell
Grant-CsGroupPolicyPackageAssignment -GroupId "dae90bb4-120f-4a3e-a15d-30f142e79f69" -PackageName "Education_Teacher" -PolicyRankings "TeamsAppSetupPolicy, 1", "TeamsMeetingBroadcastPolicy, 1", "TeamsMeetingPolicy, 2"
```

## <a name="assign-a-policy-package-to-a-batch-of-users"></a>Назначение пакета политики пакету пользователей

При назначении пакетного пакета политики вы можете одновременно назначить пакет политики большому набору пользователей, не пользуясь сценарием. С помощью [нового CsBatchPolicyAssignmentOperation](/powershell/module/teams/new-csbatchpolicyassignmentoperation) можно отправить пакет пользователей и пакет политики, который вы хотите назначить. Задания будут обрабатываться в фоновом режиме, а для каждого пакета будет создан идентификатор операции. Затем можно использовать для отслеживания хода выполнения и состояния заданий в пакете с помощью [get-CsBatchPolicyAssignmentOperation.](/powershell/module/teams/get-csbatchpolicyassignmentoperation)

Укажите пользователей по их ИД объекта или SIP-адресу. SIP-адрес пользователя часто имеет то же значение, что и имя пользователя (UPN) или адрес электронной почты, но это не обязательно. Если имя пользователя указано с помощью его имя-пользователя или электронной почты, но его значение отличается от SIP-адреса, назначение политики для него не удастся. Если пакет содержит дубликатов пользователей, они будут удалены из пакета до обработки, а состояние будет предоставлено только для уникальных пользователей, оставшихся в пакете.

Пакет содержит до 5000 пользователей. Для получения наилучших результатов не от отправки нескольких пакетов за один раз. Разрешить обработку пакетов перед отправкой дополнительных пакетов.

### <a name="use-the-teams-powershell-module"></a>Использование модуля Teams PowerShell

Чтобы установить модуль [PowerShell Microsoft Teams PowerShell,](https://www.powershellgallery.com/packages/MicrosoftTeams) запустите следующую следующую командную Microsoft Teams (если вы еще этого не сделали). Установите версию 1.0.5 или более поздней.

```powershell
Install-Module -Name MicrosoftTeams
```

Чтобы подключиться к Teams и начать сеанс, Teams выполнить следующее:

```powershell
Connect-MicrosoftTeams
```

Когда вам будет предложено, войте в учетные данные администратора.

### <a name="assign-policy-packages-to-a-batch-of-users"></a>Назначение пакетов политики для пакета пользователей

В этом примере для назначения пакета политики пакету пользователей используется Education_PrimaryStudent [New-CsBatchPolicyAssignmentOperation.](/powershell/module/teams/new-csbatchpolicyassignmentoperation)

```powershell
New-CsBatchPolicyPackageAssignmentOperation -Identity 1bc0b35f-095a-4a37-a24c-c4b6049816ab,user1@econtoso.com,user2@contoso.com -PackageName Education_PrimaryStudent
```

### <a name="see-the-status-of-a-batch-assignment"></a>См. состояние пакета назначения

Чтобы получить состояние пакета назначения, где OperationId — это код операции, возвращаемый этим cmdlet для заданного пакета, запустите `New-CsBatchPolicyAssignmentOperation` следующую операцию:

```powershell
$Get-CsBatchPolicyAssignmentOperation -OperationId f985e013-0826-40bb-8c94-e5f367076044 | fl
```

Если выходные данные показывают, что произошла ошибка, запустите следующую, чтобы получить дополнительные сведения об ошибках, которые находятся в `UserState` свойстве.

```powershell
Get-CsBatchPolicyAssignmentOperation -OperationId f985e013-0826-40bb-8c94-e5f367076044 | Select -ExpandProperty UserState
```

Подробнее см. в [get-CsBatchPolicyAssignmentOperation.](/powershell/module/teams/get-csbatchpolicyassignmentoperation)

## <a name="related-topics"></a>См. также

- [Управление Teams политиками](manage-teams-with-policies.md)
- [Управление пакетами политик в Microsoft Teams](manage-policy-packages.md)
- [Обзор PowerShell в Teams](teams-powershell-overview.md)
- [Назначение политик в Teams — начало работы](policy-assignment-overview.md)
