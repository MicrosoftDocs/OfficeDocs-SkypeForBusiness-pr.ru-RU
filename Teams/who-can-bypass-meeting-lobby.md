---
title: Управление тем, кто может обойти зал собраний в Майкрософт Teams
ms.author: mikeplum
author: MikePlumleyMSFT
ms.reviewer: rbronisevsky
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
description: Узнайте, как использовать зал ожидания собрания в Майкрософт Teams, чтобы разрешить только определенным участникам собрания присоединяться непосредственно к собранию.
ms.openlocfilehash: c9073209a329c0d97c7d1951c02194d9924eea76
ms.sourcegitcommit: 0d97dc6616b3d633564409e39c08311af1522705
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/14/2022
ms.locfileid: "69392737"
---
# <a name="control-who-can-bypass-the-meeting-lobby-in-microsoft-teams"></a>Управление тем, кто может обойти зал собраний в Майкрософт Teams

Лобби собраний Teams — это способ запретить определенным типам участников собрания присоединяться к собранию до тех пор, пока организатор собрания, соорганизатор или ведущий не допустит их. Когда участник переходит в зал ожидания, организаторы, соорганизаторы и выступающие получают уведомление и могут принять его на собрание или нет.

С помощью параметров лобби в Центре администрирования Teams можно создать параметры по умолчанию для тех типов участников собрания, которые могут обходить лобби и какие участники должны ждать там, пока не будут допущены к собранию. Вы можете управлять взаимодействием с лобби следующими типами участников:

- Организатор и соорганизаторы собраний
- Люди в организации
- Гости
- Люди в доверенных организациях
- Анонимные участники

Удостоверения людей, присоединяющихся к собраниям, проверяются Майкрософт 365, если участник не является анонимным. Анонимные участники не могут быть проверены.

## <a name="prerequisites-for-meeting-with-people-outside-your-organization"></a>Предварительные требования для встреч с людьми за пределами организации

В Teams есть несколько параметров, которые определяют, могут ли пользователи за пределами организации взаимодействовать с Teams. Чтобы пользователи за пределами организации присоединялись к собраниям, должны быть включены следующие параметры:

- Чтобы гости могли присоединиться к собраниям, необходимо включить [гостевой доступ в Teams](guest-access.md).
- Чтобы пользователи из доверенных организаций присоединялись к собраниям, необходимо включить [внешний доступ](manage-external-access.md). Необходимо настроить взаимное доверие между вашей организацией и внешней организацией, а организатор собраний в вашей организации, а также все участники из внешней организации должны быть включены для внешнего доступа.
- Чтобы анонимные участники могли присоединяться к собранию, должны быть **включено** как параметр **анонимных пользователей** (уровень организации), так и политика собрания (для организатора, создающего собрание).

Если какой-либо из этих параметров отключен, внешний участник этого типа не сможет присоединиться к собраниям независимо от параметров лобби.

## <a name="overview-of-lobby-settings-and-policies"></a>Обзор параметров и политик лобби

В следующей таблице показаны политики собраний Teams, которые влияют на взаимодействие участников собрания с лобби.

|Параметр|Описание|
|:------|:----------|
|**Анонимные пользователи и абоненты могут начать собрание**|Это политика для каждого организатора, которая позволяет проводить собрания без лидеров. Этот параметр определяет, могут ли анонимные участники и пользователи с телефонным подключением присоединиться к собранию без участия проверенного участника. Этот параметр применяется только в том случае, если для **параметра Кто может обойти лобби** задано значение **Все**. Если параметр **Анонимные пользователи могут присоединиться к организации собрания** или собранию имеет значение **Выкл**., этот параметр применяется только к абонентам с телефонным подключением. По умолчанию этот параметр отключен, чтобы предотвратить потенциальное злоупотребление ссылками на собрания анонимными пользователями. <br><br> В **режиме Off** анонимные участники и пользователи с телефонным подключением будут ждать в зале ожидания, пока проверенный участник (включая организатор телефонного подключения) не присоединится к собранию, после чего они будут автоматически допущены. После начала собрания анонимные участники и пользователи с телефонным подключением присоединятся к вызову автоматически, даже если организатор покидает его. <br><br> Если этот параметр имеет значение **Включено**, анонимные участники и участники с телефонным подключением могут начать собрание и присоединиться к нему без участия проверенного участника.|
|**Люди при звонке в можно обойти лобби**|Это политика для организатора. Этот параметр определяет, присоединяются ли люди, набравшие телефон, к собранию напрямую или ждут в вестибюле. Если этот параметр имеет **значение Выкл**., пользователи с телефонным подключением будут ждать в зале ожидания, пока организатор, соорганизатор или выступающий не присоединится к собранию и не примет их. Если этот параметр имеет значение **Включено**, пользователи с телефонным подключением будут автоматически присоединяться к собранию, не проходя через зал ожидания. (Если **анонимные пользователи и абоненты могут начать собрание** с **параметром Off**, они будут ждать в зале ожидания, пока собрание не начнется.)|
|**Кто может обойти лобби**|Это политика для организатора. Этот параметр определяет, какие типы участников (за исключением тех, кто звонит по телефону) присоединяются к собранию напрямую и какие типы участников ждут в зале ожидания, пока они не будут допущены организатором, соорганизатором или выступающим.|

В следующей таблице показано, как каждый параметр для политики **"Кто может обойти лобби"** влияет на каждый *тип участников собрания*.

|Значение политики:|Все|Люди в моей организации, доверенные организации и гости|Люди в моей организации и гости|Люди в моей организации|Только приглашенные люди|Только организаторы и соорганизаторы|
|:--------|:------|:-----|:-----|:------|:-------|:---------------|
|*Организатор и соорганизаторы*|Обхода|Обхода|Обхода|Обхода|Обхода|Обхода|
|*Люди в организации*|Обхода|Обхода|Обхода|Обхода|Люди, которые были отправлены или переадресованы приглашение, будут обходить стороной; другие ждут в вестибюле|Лобби|
|*Гости*|Обхода|Обхода|Обхода|Лобби|Люди, которые были отправлены или переадресованы приглашение, будут обходить стороной; другие ждут в вестибюле|Лобби|
|*Люди в доверенных организациях*|Обхода|Обхода|Лобби|Лобби|Люди, которые были отправлены или переадресованы приглашение, будут обходить стороной; другие ждут в вестибюле|Лобби|
|*Анонимные участники*|Обхода|Лобби|Лобби|Лобби|Лобби|Лобби|

**Только приглашенные люди** относятся только к проверенным участникам, которым было отправлено приглашение или которым было перенаправлено приглашение. Пользователи, добавленные в группу рассылки, будут ждать в зале ожидания.

## <a name="choose-who-can-bypass-the-lobby-in-meetings-hosted-by-your-organization"></a>Выберите, кто может обойти лобби на собраниях, размещенных в вашей организации

Параметры и политики, описанные выше, можно настроить в Центре администрирования Teams. Инструкции по выбору параметра для различных обстоятельств см. в разделах ниже. Сведения о том, как работают политики собраний, см. [в статье Управление политиками собраний в Майкрософт Teams](/microsoftteams/meeting-policies-overview).

> [!Important]
> Организаторы собраний могут изменять значения по умолчанию, выбранные для **Люди при звонке в может обходить лобби** и **кто может обходить параметры лобби**. Если необходимо применить эти параметры к определенному значению, можно использовать шаблон собрания или метку конфиденциальности (требуется Teams Premium).  Дополнительные сведения см. [в разделе Настройка лобби собраний Майкрософт Teams для конфиденциальных собраний](configure-lobby-sensitive-meetings.md).

Настройка политик присоединения к собранию и лобби
1. В Центре администрирования Teams разверните узел **Собрания** , а затем выберите **Политики собраний**.
1. Выберите политику, которую требуется обновить.
1. В разделах **Участник & гостей** обновите параметры, которые нужно изменить:
   - **Предоставление анонимным пользователям присоединения к собранию**
   - **Разрешать анонимным пользователям начинать собрания**
   - **Автоматическое допуск людей** (кто может обойти лобби)
   - **Пользователи с телефонным подключением могут обойти лобби**

    ![Снимок экрана: политика присоединения к собранию и лобби в Центре администрирования Teams.](media/meeting-join-and-lobby-tac-settings.png)
1. Нажмите **Сохранить**.

Обратите внимание, что в силу изменений может потребоваться до двадцати четырех часов.

Если вы хотите разрешить анонимный доступ к собранию, убедитесь, что параметр **Анонимные пользователи могут присоединиться к собранию** также включен.

Настройка параметра собрания на уровне организации для анонимного присоединения к собранию
1. В Центре администрирования Teams разверните узел **Собрания** , а затем выберите **Параметры собрания**.
1. В разделе **Участники** установите для значения **Анонимные пользователи могут присоединиться к собранию** **значение Вкл** . или **Выкл**.
    ![Снимок экрана: параметры присоединения к собранию и лобби в Центре администрирования Teams.](media/anonymous-users-can-join-meetings-org-setting.png)
1. Нажмите **Сохранить**.

## <a name="control-access-to-meetings-by-anonymous-participants"></a>Управление доступом к собраниям анонимными участниками

Анонимные участники являются анонимными, так как они не вошли в учетную запись, которую можно проверить Майкрософт 365. Сюда могут входить:

- Люди, которые не вошли в Майкрософт 365 с помощью рабочей или учебной учетной записи 
- Люди из ненадежных организаций (как настроено во [внешнем доступе](manage-external-access.md)).
- Люди из организаций, которым вы доверяете, но которые не доверяют вашей организации

Если вы хотите полностью запретить анонимным участникам присоединяться к собранию, можно отключить параметр **Анонимные пользователи могут присоединяться к собранию** в масштабах всей организации. Вы также можете отключить анонимное присоединение для определенных организаторов собраний с помощью политики **Анонимные пользователи могут присоединяться к собранию** .

Если вы хотите, чтобы пользователи, присоединяющиеся анонимно, ждали в зале ожидания, можно задать для политики **"Кто может обойти собрание в лобби** " любой параметр, кроме **"Все**". (Этот параметр не влияет на людей, набирающих телефон.)

По умолчанию для политики **Анонимные пользователи и абоненты с телефонным подключением могут запускать собрание** , имеет значение **Выкл**. Это означает, что анонимные участники и люди, звонив по телефону, всегда будут ждать в зале ожидания, если проверенный участник еще не начал собрание. Хотя этот параметр можно включить, если существуют обстоятельства, в которых вы хотите разрешить анонимным участникам и людям, которые звонят по телефону для начала собраний, рекомендуется оставить его отключенным.  Если параметр включен, пользователи с непроверенными учетными записями могут начинать собрания, в том числе использовать ссылку на собрание для проведения собраний в незапланированные периоды.

## <a name="control-access-to-meetings-by-people-dialing-in-by-phone"></a>Управление доступом к собраниям людьми, набирающими по телефону

По умолчанию **Люди набора номера в может обходить политику лобби****, но** организаторы собраний могут изменить это при настройке собрания. Вы можете изменить значение по умолчанию, **обновив Люди при звонке в можно обойти политику лобби** или применить определенное значение с помощью шаблона собрания.

## <a name="control-access-to-meetings-by-guests-and-people-from-trusted-organizations"></a>Управление доступом к собраниям гостями и людьми из доверенных организаций

Существует два типа людей за пределами организации, которые могут присоединяться к собраниям в качестве проверенных участников:

- Гости — пользователи с [учетной записью совместной работы Azure Active Directory (Azure AD) B2B](/azure/active-directory/external-identities/what-is-b2b) в вашей организации
- Пользователи внешнего доступа — пользователи, у которых Azure AD учетные записи в доверенной организации, [определенной во внешнем доступе](manage-external-access.md) Teams

Если вы хотите, чтобы все проверенные участники собрания из-за пределов вашей организации ждали в зале ожидания, можно задать политику "Кто может обойти лобби", чтобы **Люди в моей организации** или **Только организаторы и соорганизаторы** (при условии, что гость не является организатором или соорганизатором). Если вы хотите, чтобы только пользователи из доверенных организаций (внешние пользователи доступа) ждали в зале ожидания, вы можете выбрать **Люди в моей организации и гостей**.

## <a name="control-access-to-meetings-by-people-without-invitations"></a>Управление доступом к собраниям людьми без приглашений

Если вы хотите разрешить только пользователям, которые имеют приглашения, присоединяться к собраниям напрямую и ждать всех остальных участников в зале ожидания, установите для параметра **Кто может обойти лобби** **значение Только приглашенные люди**. (Люди, приглашенные через список рассылки, не включены.)

Параметр **Только приглашенные люди** включают проверенных участников, которым было перенаправлено приглашение, а не только приглашенных непосредственно организатором. В нее не входят люди, у которых есть ссылка на присоединение к собранию, но не само приглашение и непроверенные (анонимные) участники. Они должны ждать в вестибюле.

Обратите внимание, что организаторы собраний могут отключить перенаправление приглашения на собрание, если они хотят, чтобы на собрание присутствовали только те, кто непосредственно приглашен.

## <a name="control-access-to-meetings-by-non-organizers"></a>Управление доступом к собраниям неорганизаторами

Если у вас есть собрания, на которых предоставляется общий доступ к конфиденциальной информации или на которые распространяются нормативные требования, может потребоваться, чтобы все участники ждали в зале ожидания, пока они не будут допущены организатором собрания или соорганизаторами. В этом случае можно задать для **параметра Кто может обойти лобби** **значение Только организаторы и соорганизаторы**.

Так как **кто может обойти только лобби** , устанавливает значение по умолчанию, которое могут изменить организаторы собраний, при наличии требований к соответствию в этой области рекомендуется применить значение с помощью метки конфиденциальности или шаблона собрания. Дополнительные сведения см. [в разделе Настройка лобби собраний Майкрософт Teams для конфиденциальных собраний](configure-lobby-sensitive-meetings.md).

## <a name="set-meeting-policies-by-using-powershell"></a>Настройка политик собраний с помощью PowerShell

Политики собраний, описанные в этой статье, можно задать с помощью [командлета PowerShell Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy) со следующими параметрами:

- [-AllowAnonymousUsersToJoinMeeting](/powershell/module/skype/set-csteamsmeetingpolicy?#-allowanonymoususerstojoinmeeting) для управления тем, могут ли анонимные пользователи присоединяться к собраниям
- [-AllowPSTNUsersToBypassLobby](/powershell/module/skype/set-csteamsmeetingpolicy#-allowpstnuserstobypasslobby) , чтобы контролировать, могут ли люди, набирающие по телефону, обходить лобби
- [-AutoAdmittedUsers](/powershell/module/skype/set-csteamsmeetingpolicy?#-autoadmittedusers) для контроля того, кто может обходить лобби

## <a name="related-topics"></a>См. также

[Присоединение к собранию без учетной записи Teams](https://support.microsoft.com/office/c6efc38f-4e03-4e79-b28f-e65a4c039508)

[Настройка политики для всей организации с помощью Центра администрирования Microsoft Teams](meeting-settings-in-teams.md#allow-anonymous-users-to-join-meetings)

[Внешние участники получают сообщение "Войти в Teams, чтобы присоединиться или связаться с организатором собрания"](/microsoftteams/troubleshoot/meetings/external-participants-join-meeting-blocked)