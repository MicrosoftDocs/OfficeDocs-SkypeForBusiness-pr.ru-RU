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
localization_priority: Normal
search.appverid: MET150
description: Узнайте о различных способах назначения пакетов политики пользователям и группам в Microsoft Teams.
f1keywords:
- ms.teamsadmincenter.bulkoperations.users.edit
- ms.teamsadmincenter.bulkoperations.edit
ms.openlocfilehash: 0266cb5c34a13df0dac62be2258134e553a357d8
ms.sourcegitcommit: 2bb8556650120b4f7cf509d8ff93d7e4d058829b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/02/2021
ms.locfileid: "51574350"
---
# <a name="assign-policy-packages-to-users-and-groups"></a>Назначение пакетов политики пользователям и группам

В этой статье рассматриваются различные способы назначения пакетов политики пользователям и группам в Microsoft Teams. Прежде чем читать, прочитайте статью ["Назначение политик в Teams — начало работы".](policy-assignment-overview.md)

## <a name="assign-a-policy-package-to-users"></a>Назначение пакета политики пользователям

Пакет политики в Teams — это набор предопределельных политик и параметров политики, которые можно назначать пользователям с одинаковыми или похожими ролями в организации. Каждый пакет политики предназначен для роли пользователя и содержит предопределять политики и параметры политики, которые поддерживают типичные для нее действия. Примерами пакетов политики могут быть пакеты для образовательных учреждений (для преподавателей) и медицинских учреждений (клинические работники). Дополнительные узнать см. в [подмносях "Управление пакетами политики в Teams".](manage-policy-packages.md)

### <a name="assign-a-policy-package-to-one-user"></a>Назначение пакета политики одному пользователю

1. В левой области навигации Центра администрирования Microsoft Teams перейдите в меню **"Пользователи"** и выберите пользователя.
2. На странице пользователя выберите "Политики", а затем рядом с пакетом политики **выберите** **"Изменить".**
3. В области **назначения пакета политики** выберите пакет, который вы хотите назначить, и выберите **"Сохранить".**

![Снимок экрана Центра администрирования Teams для назначения пакета политики пользователю](media/assign-policypackages-user.png)

### <a name="assign-a-policy-package-to-multiple-users"></a>Назначение пакета политики нескольким пользователям

1. В левой области навигации Центра администрирования Microsoft Teams перейдите к пакетам **политики,** а затем выберите пакет политики, который вы хотите назначить, щелкнув слева от его имени.
2. Выберите **Управление пользователями**.
3. В области **Управление пользователями** выполните поиск по отображаемому имени или по имени пользователя, выберите имя и нажмите **Добавить**. Повторите это действие для каждого пользователя, которого нужно добавить.
4. Завершив добавление пользователей, выберите **"Сохранить".**

![Снимок экрана Центра администрирования Teams для назначения пакета политики нескольким пользователям](media/assign-policypackages-multipleusers.png)

## <a name="assign-a-policy-package-to-a-group"></a>Назначение пакета политики группе

Назначение пакетов политики группам позволяет назначать несколько политик группе пользователей, например группе безопасности или группе рассылки. Назначение политики распространяется на участников группы в соответствии с правилами очередности. При добавлении или удалении участников группы, назначения политик для них обновляются соответствующим образом.

Назначение пакетов политики группам рекомендуется для групп до 50 000 пользователей, но оно также будет работать с более крупными группами.

Когда вы назначаете пакет политики, он сразу же назначается группе. Однако распространение назначения политики на участников группы выполняется в фоновом режиме и может занять некоторое время в зависимости от размера группы. То же самое происходит, если политика не назначена группе, а также когда участники добавляются в группу или удаляются из нее.

> [!IMPORTANT]
> Прежде чем начать, важно понимать (правила[приоритета)](assign-policies-users-and-groups.md#precedence-rules)и (ранжирование[назначений группы).](assign-policies-users-and-groups.md#group-assignment-ranking) Убедитесь, что вы читаете и понимаете понятия в документе[(что](assign-policies-users-and-groups.md#what-you-need-to-know-about-policy-assignment-to-groups)необходимо знать о назначении политик группам) ранее в этой статье.

### <a name="assign-a-policy-package-to-a-group-of-users-in-the-admin-center"></a>Назначение пакета политики группе пользователей в Центре администрирования

1. Войдите в Центр администрирования Teams.
2. В области навигации слева перейдите на страницу пакета политики.
3. Выберите вкладку назначения групповой политики.
4. Выберите **"Добавить** группу", а затем в области "Назначение пакета политики группе" сделайте следующее:

    а) Найщите и добавьте группу, для нее нужно назначить пакет политики.

    б) Выберите пакет политики.

    в. Заведите ранжирование для каждого типа политики.

    г. Выберите **"Применить".**

![показывает назначение групповой политики.](media/group-pkg-assignment.png)

5. Чтобы управлять ранжированием для определенного типа политики, перейдите на страницу политики.
6. Чтобы перена назначение пакета политики группе, сначала удалите назначение групповой политики. Затем следуйте этим шагам, чтобы назначить пакет политики группе.

### <a name="work-with-powershell"></a>Работа с PowerShell

#### <a name="get-the-teams-powershell-module"></a>Получить модуль Teams PowerShell

Пошаговую инструкцию см. в [руководстве по установке Teams PowerShell.](teams-powershell-install.md)

#### <a name="assign-a-policy-package-to-a-group-of-users"></a>Назначение пакета политики группе пользователей

Для назначения пакета политики группе используйте cmdlet [Grant-CsGroupPolicyPackageAssignment.](https://docs.microsoft.com/powershell/module/teams/grant-csgrouppolicypackageassignment) Группу можно указать с помощью ИД объекта, SIP-адреса или адреса электронной почты. При назначении пакета политики укажите[](assign-policies-users-and-groups.md#group-assignment-ranking)(ранжирование назначений групп) для каждого типа политики в пакете политики.

В этом примере пакет политики Education_Teacher назначается группе со ранжированием заданий 1 для TeamsAppSetupPolicy и TeamsMeetingBroadcastPolicy и 2 для TeamsMeetingPolicy.

```powershell
Grant-CsGroupPolicyPackageAssignment -GroupId "dae90bb4-120f-4a3e-a15d-30f142e79f69" -PackageName "Education_Teacher" -PolicyRankings "TeamsAppSetupPolicy, 1", "TeamsMeetingBroadcastPolicy, 1", "TeamsMeetingPolicy, 2"
```

## <a name="assign-a-policy-package-to-a-batch-of-users"></a>Назначение пакета политики пакету пользователей

При назначении пакетов пакетов политики вы можете назначать пакет политики большому набору пользователей одновременно, не пользуясь сценарием. Для отправки пакета пользователей и пакета политики, который вы хотите назначить, используется cmdlet [New-CsBatchPolicyAssignmentOperation.](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation) Задания будут обрабатываться в фоновом режиме, а для каждого пакета будет создан идентификатор операции. Затем можно использовать для отслеживания хода выполнения и состояния назначений в пакете с помощью выполнения и выполнения задач [Get-CsBatchPolicyAssignmentOperation.](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation)

Укажите пользователей по их ИД объекта или SIP-адресу. SIP-адрес пользователя часто имеет то же значение, что и имя пользователя-пользователя (UPN) или адрес электронной почты, но это не требуется. Если имя пользователя указано с помощью upN или электронной почты, но его значение отличается от SIP-адреса, назначение политики для пользователя не удастся. Если пакет включает дублирующихся пользователей, повторяющиеся записи удаляются из пакета до обработки, а состояние будет предоставлено только для уникальных пользователей, оставшихся в пакете.

Пакет содержит до 5000 пользователей. Для получения наилучших результатов не от отправьте несколько пакетов за один раз. Разрешить обработку пакетов перед отправкой дополнительных пакетов.

### <a name="use-the-teams-powershell-module"></a>Использование модуля Teams PowerShell

Чтобы установить модуль [Microsoft Teams PowerShell,](https://www.powershellgallery.com/packages/MicrosoftTeams) запустите следующую команду: Установите версию 1.0.5 или более поздней.

```powershell
Install-Module -Name MicrosoftTeams
```

Чтобы подключиться к Teams и начать сеанс, запустите следующую команду:

```powershell
Connect-MicrosoftTeams
```

Когда вам будет предложено, войте учетные данные администратора.

### <a name="assign-policy-packages-to-a-batch-of-users"></a>Назначение пакетов политики для пакета пользователей

В этом примере с помощью Education_PrimaryStudent пакета политики [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation) назначается пакет политики Education_PrimaryStudent пакету пользователей.

```powershell
New-CsBatchPolicyPackageAssignmentOperation -Identity 1bc0b35f-095a-4a37-a24c-c4b6049816ab,user1@econtoso.com,user2@contoso.com -PackageName Education_PrimaryStudent
```

### <a name="see-the-status-of-a-batch-assignment"></a>См. состояние пакета назначения

Чтобы получить состояние пакета назначения, где OperationId — это код операции, возвращаемой этим cmdlet для данного пакета, запустите ```New-CsBatchPolicyAssignmentOperation``` следующую операцию:

```powershell
$Get-CsBatchPolicyAssignmentOperation -OperationId f985e013-0826-40bb-8c94-e5f367076044 | fl
```

Если в результате будет показана ошибка, запустите следующую статью, чтобы получить дополнительные сведения об ошибках, которые находятся в ```UserState``` свойстве.

```powershell
Get-CsBatchPolicyAssignmentOperation -OperationId f985e013-0826-40bb-8c94-e5f367076044 | Select -ExpandProperty UserState
```

Подробнее см. в [get-CsBatchPolicyAssignmentOperation.](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation)

## <a name="related-topics"></a>Статьи по теме

- [Управление teams с помощью политик](manage-teams-with-policies.md)
- [Управление пакетами политики в Microsoft Teams](manage-policy-packages.md)
- [Обзор PowerShell в Teams](teams-powershell-overview.md)
- [Назначение политик в Teams — начало работы](policy-assignment-overview.md)