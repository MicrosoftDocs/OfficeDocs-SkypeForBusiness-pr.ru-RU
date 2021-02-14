---
title: Обновление до Teams из локального развертывания Skype для бизнеса — Microsoft Teams
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 09/16/2020
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: bjwhalen
description: Переход со Skype для бизнеса на Teams
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: bec5c2b10dc2e09092cd7c26284c04868982e287
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48533606"
---
# <a name="implement-your-upgrade-from-skype-for-business-to-teams-mdash-for-it-administrators"></a>Реализация обновления Skype для бизнеса до Teams &mdash; для ИТ-администраторов

В этой статье описано, как реализовать обновление. Эта пятая статья посвящена понятиям обновления и внедрению для ИТ-администраторов.  

- [Обзор](upgrade-to-teams-on-prem-overview.md)
- [Способы обновления](upgrade-to-teams-on-prem-upgrade-methods.md)
- [Инструменты для управления обновлением](upgrade-to-teams-on-prem-tools.md)
- [Дополнительные соображения для организаций с локальной учетной записью Skype для бизнеса](upgrade-to-teams-on-prem-considerations.md)
- **Реализация обновления** (эта статья)
- [Вопросы, которые следует учесть при переходе на телефонную сеть общего перейти на телефонную сеть (ПС)](upgrade-to-teams-on-prem-pstn-considerations.md)

Кроме того, в следующих статьях описаны важные понятия обновления и принципы сосуществования.

- [Совместное сосуществование Teams и Skype для бизнеса](upgrade-to-teams-on-prem-coexistence.md)
- [Режимы сосуществования — ссылки](migration-interop-guidance-for-teams-with-skype.md)
- [Взаимодействие с клиентом Teams и соответствие режимам сосуществования](teams-client-experience-and-conformance-to-coexistence-modes.md)

## <a name="upgrade-options"></a>Варианты обновления

В этом разделе описано, как реализовать обновление с помощью одного из следующих вариантов:

- [Обновление перекрывающихся возможностей (в режиме "О-ва")](#overlapping-capabilities-upgrade-using-islands-mode)
- [Обновление некоторых возможностей для организации, которая еще не начала использовать Teams](#a-select-capabilities-upgrade-for-an-organization-that-has-not-yet-started-using-teams)
- [Обновление некоторых возможностей для организации, которая уже использует Teams в режиме "О-ва"](#a-select-capabilities-upgrade-for-an-organization-that-is-already-using-teams-in-islands-mode)

Если вам нужны дополнительные сведения о параметрах, убедитесь, что методы обновления уже [прочитали.](upgrade-to-teams-on-prem-upgrade-methods.md)

## <a name="overlapping-capabilities-upgrade-using-islands-mode"></a>Обновление перекрывающихся возможностей (в режиме "О-ва")

Для варианта обновления перекрывающихся возможностей:

- Учитывайте этот вариант, если вы можете быстро обновить систему для всей организации.  Поскольку существует риск путаницы с запуском обоих клиентов, лучше всего свести к минимуму период времени, в течение которого пользователи должны запускать оба клиента. Убедитесь, что пользователи знают, как запустить оба клиента.

- Этот вариант является заданной моделью и не требует действий администратора, чтобы начать работу с Teams, кроме назначения лицензии на Microsoft 365 или Office 365. Если у ваших пользователей уже есть Skype для бизнеса Online, возможно, вы уже стали использовать эту модель.

- Выход из режима перекрывания возможностей и переход в TeamsOnly может быть сложной задачей. Так как обновленные пользователи общаются только через Teams, все другие пользователи в организации, с кем общаются, должны использовать Teams.  Если у вас есть пользователи, которые не начали использовать Teams, они будут выявлены из-за отсутствующих сообщений. Более того, они не будут видеть пользователей TeamsOnly в Интернете в Skype для бизнеса. В некоторых организациях обновление на уровне клиента возможно с помощью глобальной политики клиента, но для этого требуется прямое планирование и ожидание обновления всех пользователей.


## <a name="a-select-capabilities-upgrade-for-an-organization-that-has-not-yet-started-using-teams"></a>Обновление некоторых возможностей для организации, которая еще не начала использовать Teams

Если в вашей организации пока нет активных пользователей в Teams, сначала нужно настроить политику клиента по умолчанию для TeamsUpgradePolicy на один из режимов Skype для бизнеса, например SfbWithTeamsCollab.  Пользователи, которые еще не начали использовать Teams, не заметят никакой разницы в работе. Однако настройка этой политики на уровне клиента позволяет начать обновление пользователей до режима TeamsOnly и гарантирует, что обновленные пользователи по-прежнему смогут общаться с пользователями, которые не были обновлены.  Означив пилотных пользователей, вы можете обновить их до TeamsOnly.  Если они являются локальной, используйте Move-CsUser. Если они находятся в сети, просто назначьте им режим TeamsOnly с помощью Grant-CsTeamsUpgradePolicy. По умолчанию все собрания Skype для бизнеса, запланированные этими пользователями, переносются в Teams.

Ниже ключевых команд:

1. Задайте для клиента режим SfbWithTeamsCollab следующим образом:

   ```PowerShell
   Grant-CsTeamsUpgradePolicy -PolicyName SfbWithTeamsCollab -Global
   ```

2. Обновим пилотных пользователей до TeamsOnly следующим образом:

   - Для пользователя, который находится в сети:

     ```PowerShell
     Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity $username 
     ```

   - Для локального пользователя:

     ```PowerShell
     Move-CsUser -identity $user -Target sipfed.online.lync.com -MoveToTeams -credential $cred 
     ```

Notes
 
- Вместо того чтобы настраивать политику клиента на SfbWithTeamsCollab, можно настроить ее на SfbWithTeamsCollabAndMeetings. В результате все пользователи будут планировать все новые собрания в Teams.
- `Move-CsUser` — это cmdlet в локальном средстве. Для `MoveToTeams` перехода требуется Skype для бизнеса Server 2019 или Skype для бизнеса Server 2015 с CU8 или более поздней. Если вы используете более новую версию, вы можете сначала переместить пользователя в Skype для бизнеса Online, а затем предоставить ему режим TeamsOnly.
- По умолчанию собрания Skype для бизнеса переносются в Teams при обновлении до режима TeamsOnly или при назначении режима SfbWithTeamsCollabAndMeetings.  

На схеме ниже показаны концептуальные этапы обновления функций выбора для организации без предварительного использования Teams. Высота столбцов представляет количество пользователей. На любом этапе обновления все пользователи могут общаться друг с другом.  Пользователи Skype для бизнеса общаются с пользователями TeamsOnly с помощью Interop и наоборот. Пользователи в режиме "О-ва" должны обязательно запустить оба клиента.

![Схема, показывающая обновление некоторых возможностей без предварительного использования Teams](media/teams-upgrade-1.png)


## <a name="a-select-capabilities-upgrade-for-an-organization-that-is-already-using-teams-in-islands-mode"></a>Обновление некоторых возможностей для организации, которая уже использует Teams в режиме "О-ва"

Если некоторые пользователи в вашей организации активно используют Teams в режиме "О-ва", вероятно, вы не хотите удалять функции существующих пользователей. Таким образом, прежде чем изменять политику клиента, необходимо сделать дополнительное. Решение заключается в том, чтобы захотеть закорестить существующих активных пользователей Teams в режиме "Острова", прежде чем настраивать политику для всего клиента на SfbWithTeamsCollab.  После этого вы можете продолжить развертывание, как было выше, однако у вас будет две группы пользователей, которые переходят в TeamsOnly: пользователи, которые были активны в Teams, будут работать в режиме "О-ва", а остальные — в режиме SfbWithTeamsCollab. Вы можете постепенно перемещать этих пользователей в режим TeamsOnly.

1. Найдите пользователей, активных в Teams, следующим образом:

   1. В Центре администрирования Microsoft 365 на левой навигации перейдите к области "Отчеты", а затем "Использование". 
   2. В dropdown "Select a report" (Выберите отчет) выберите Microsoft Teams, а затем — "Действия пользователя". Это позволит обеспечить экспортируемую таблицу пользователей, которые были активны в Teams. 
   3. Нажмите кнопку "Экспорт", откройте Excel и выберите фильтр, чтобы отфильтровать только активных пользователей Teams.

2. Для каждого активного пользователя Teams, найденного на шаге 1, назначьте ему режим "Острова" в удаленной командной командной команде PowerShell. Это позволит вам перейти к следующему шагу и не изменять пользовательский интерфейс.  

   ```PowerShell
   $users=get-content “C:\MyPath\users.txt” 
    foreach ($user in $users){ 
    Grant-CsTeamsUpgradePolicy -identity $user -PolicyName Islands} 
   ```

3. Задайте для политики клиента SfbWithTeamsCollab:

   ```PowerShell
   Grant-CsTeamsUpgradePolicy -Global -PolicyName SfbWithTeamsCollab 
   ```

4. Обновление выбранных пользователей до режима TeamsOnly. Вы можете обновить либо пользователей в режиме "Острова", либо в режиме SfbWithTeamsCollab, хотя сначала может потребоваться расставить приоритеты при обновлении пользователей в режиме "О-ва", чтобы свести к минимуму вероятность путаницы, которая может возникнуть, когда пользователи находятся в режиме "О-ва".   

   Для пользователей Skype для бизнеса Online:  

   ```PowerShell
   Grant-CsTeamsUpgradePolicy -Identity $user -PolicyName UpgradeToTeams 
   ```

   Для пользователей, которые могут использовать локальное серверное приложение Skype для бизнеса:  

   ```PowerShell
   Move-CsUser -Identity $user -Target sipfed.online.lync.com -MoveToTeams -credential $cred 
   ```

На приведенной ниже схеме показаны концептуальные этапы перехода между возможностями выбора, при котором в начале есть активные пользователи островов. Высота столбцов представляет количество пользователей. На любом этапе обновления все пользователи могут общаться друг с другом.  Пользователи Skype для бизнеса общаются с пользователями TeamsOnly с помощью взаимодействия и наоборот. 


![Схема, показывающая обновление некоторых возможностей с активными пользователями в режиме "О-ва"](media/teams-upgrade-2.png)

   



## <a name="related-links"></a>Связанные ссылки

[Руководство по миграции и взаимодействию для организаций, использующих Teams вместе со Skype для бизнеса](migration-interop-guidance-for-teams-with-skype.md) 

[Настройка гибридного подключения между Skype для бизнеса Server и Microsoft 365 или Office 365](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

[Перемещение пользователей между локальной средой и облаком](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)

[Настройка сосуществования и обновления](setting-your-coexistence-and-upgrade-settings.md)

[Grant-CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

[Использование службы переноса собраний (MMS)](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)

