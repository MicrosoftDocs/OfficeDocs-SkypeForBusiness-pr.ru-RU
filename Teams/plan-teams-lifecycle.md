---
title: Планирование управления жизненным циклом в Teams — Microsoft Teams
author: rmw2890
ms.author: MyAdvisor
manager: serdars
ms.date: 09/26/2018
ms.topic: article
ms.service: msteams
ms.reviewer: rowille
description: Узнайте, как запланировать внедрение функций управления жизненным циклом в Teams.
localization_priority: Priority
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: ccd8366b746fe21fcfbe81a3878997e4e1b383bc
ms.sourcegitcommit: 85c34280977fb2c15c8a43874a20e9492bdca57f
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/07/2019
ms.locfileid: "30460390"
---
# <a name="plan-for-lifecycle-management-in-teams"></a>Планирование управления жизненным циклом в Teams

Teams содержит обширный набор инструментов для управления жизненным циклом совместной работы в вашей организации. В этой статье представлены вопросы для ИТ-специалистов по определению требований к управлению жизненным циклом, а также средства, позволяющие выполнить эти требования. 

Планирование управления жизненным циклом имеет большое значение, так как оно создает фундамент для эффективной работы. Большинство проектов можно поделить на начальный, основной и конечный этапы. Это верно и для команд Teams, но их функции настолько обширны, что не всегда очевидно, на каком этапе жизненного цикла они сейчас находятся. План управления жизненным циклом поможет контролировать проекты вашей организации по мере прохождения различных этапов.

> [!Tip]
> Дополнительные сведения о жизненном цикле в Microsoft Teams см. в следующем видео: [Governance, management and lifecycle in Microsoft Teams](https://aka.ms/teams-governance) (Администрирование, управление и жизненный цикл в Microsoft Teams).


## <a name="lifecycle-concepts"></a>Понятия жизненного цикла

Принимая решения по управлению жизненным циклом, вы будете опираться на следующие понятия и определения.

**Teams**

A _team_ is a collection of people, content, and tools that facilitate collaboration. A team defines who its members are, and the permissions and policies that apply to those members. Teams are built on Office 365 Groups, and changes to Office 365 group membership sync to the team. Like other Office 365 Groups, Teams come auto-provisioned with an Exchange mailbox, a SharePoint site, a OneNote notebook, and other assets within Office 365. [Learn more about Office 365 Groups](https://support.office.com/article/Learn-about-Office-365-groups-b565caa1-5c40-40ef-9915-60fdb2d97fa2).

**Каналы**

Channels are the collaboration spaces within a team where the actual work is done. Each channel represents a different topic or workstream within the overall team. For each channel, a folder is automatically created on the SharePoint site to store all files shared to that channel, making it easy for users to find and work on the documents they care about. Channels can also be extended with apps that are relevant to the particular workstream—for example, you can add a Power BI dashboard to a channel to track the success of one aspect of your project.

**Типы доступа к командам**

Типы доступа определяют, кто может присоединяться к командам:

-   _Private_ teams are restricted to team members approved by the team owner(s). This is a typical setting for project teams and virtual teams in a large organization.
-   _Public_ teams are open for anyone in the organization to join directly. This is useful for collaboration on topics of general interest to people in different departments working on different projects. This is a good default setting for smaller organizations.

**Типы пользователей команд и роли администратора** 

Тип пользователя команды определяет доступные ему возможности управления:

-   _Team creator_ has permissions to create a group or team in the directory. The admin can constrain this user type to a subset of admins or users. For more information, see [Manage who can create Office 365 Groups](https://support.office.com/article/Manage-who-can-create-Office-365-Groups-4c46c8cb-17d0-44b5-9776-005fced8e618). 
-   _Team owner_ manages membership and settings for the team. There can be as many as 10 team owners per team.
-   _Участник команды_ — это сотрудник вашей организации, который принимает участие в команде.
-   _Guest_ is a user who’s external to your organization. Anyone with an email address can be invited as a guest if your organization has enabled [guest access](guest-access.md).

> [!Note]
> Дополнительные сведения о владельцах команд и возможностях участников: [Назначение ролей и разрешений в Microsoft Teams](assign-roles-permissions.md).

Teams admin roles determine what capabilities each admin role holder has. These are described in the following table.

<table>
 <thead>
  <tr>
    <th width="0.5%"></th>
    <th width="15.5%">Роль&nbsp;&nbsp;</th>
    <th width="25%">Описание</th>
    <th width="60%">Может делать следующее с использованием указанных инструментов</th>
  </tr>
</thead>
<tbody>
   <tr>
    <td valign="top" colspan="2">Администратор служб Teams</td>
    <td valign="top">Управление службой Teams, создание и изменение групп Office 365</td>
    <td valign="top">Управление собраниями, включая политики собраний, конфигурации и мосты конференций<sup>1</sup><br><br>Управление голосовыми звонками, включая политики звонков, учет и назначение телефонных номеров, очереди звонков и автосекретари<sup>1</sup><br><br>Управление сообщениями, включая политики обмена сообщениями<sup>1</sup><br><br>Управление параметрами на уровне организации, включая федерацию, переход на Teams и параметры клиентов Teams<sup>1</sup><br><br>Управление командами в организации и их настройка, включая членство<sup>2</sup><br><br>Просмотр страницы профиля пользователя и устранение проблем с качеством звонка при помощи расширенного набора инструментов<sup>3</sup></td>
</tr>
<tr>
<td valign="top" colspan="2">Администратор коммуникаций Teams</td>
<td valign="top">Управление функциями звонков и собраний в службе Microsoft Teams</td>
<td valign="top">Управление собраниями, включая политики собраний, конфигурации и мосты конференций<sup>1</sup><br><br>Управление голосовыми звонками, включая политики звонков, учет и назначение телефонных номеров, очереди звонков и автосекретари<sup>1</sup><br><br>Просмотр страницы профиля пользователя и устранение проблем с качеством звонка при помощи расширенного набора инструментов<sup>1</sup></td>
</tr>
<tr>
<td valign="top" colspan="2">Специалист по коммуникациям Teams</td>
<td valign="top">Устранение проблем со связью в Teams при помощи базовых инструментов</td>
<td valign="top">Access to the user profile page for troubleshooting calls in Call Analytics. Can only view user information for the specific user being searched for.<sup>3</sup></td>
</tr>
<tr>
<td valign="top" colspan="2">Инженер поддержки по коммуникациям Teams</td>
<td valign="top">Устранение проблем со связью в Teams при помощи расширенных инструментов</td>
<td valign="top">Access to the user profile page for troubleshooting calls in Call Analytics. Can view the full call record information.<sup>3</sup></td>
</tr>
<tr>
</tbody>
<tfoot>
<tr><td align="right"><sup>1</sup></td><td colspan="3"><a href="https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell
">Модуль PowerShell — Skype для бизнеса</a> или <a href="https://docs.microsoft.com/microsoftteams/manage-teams-skypeforbusiness-admin-center">Центр администрирования Microsoft Teams</a></td></tr>
<tr><td align="right"><sup>2</sup></td><td colspan="3"><a href="https://www.powershellgallery.com/packages/MicrosoftTeams/0.9.3">Модуль PowerShell — Microsoft Teams</a> или <a href="https://docs.microsoft.com/microsoftteams/manage-teams-skypeforbusiness-admin-center">Центр администрирования Microsoft Teams</a></td></tr>
<tr><td align="right"><sup>3</sup></td><td colspan="3">Только <a href="https://docs.microsoft.com/microsoftteams/manage-teams-skypeforbusiness-admin-center">Центр администрирования Microsoft Teams</a></td>
</tr>
</tfoot>
</table>


## <a name="it-decisions-to-make-before-getting-started"></a>Решения по ИТ, которые нужно принять перед началом работы

Before you roll Teams out to your organization, implement any governance policies that your organization has decided it requires. These can include items like naming conventions, expiration policies, retention policies, and more. Generally speaking, it’s much easier to implement these requirements prior to scaling your deployment across your organization.

Дополнительные сведения: [Планирование управления в Teams](plan-teams-governance.md).

## <a name="teams-lifecycle-stages"></a>Этапы жизненного цикла команд

Generally speaking, a team has a purpose that’s aligned with a project or accomplishing a goal. Even if a team was formed based on a shared interest, the team membership will probably change over time and the discussion might grow stale—only to surface again in a slightly different way in a different team.

Каждая из команд проходит через три этапа: начало, когда команда создается и настраиваются каналы; основной этап использования, когда в команде ведется совместная работа в соответствии с ритмом рабочего процесса; и иногда — окончание, когда команда выполнила свою задачу и больше не приносит пользы. 

Дополнительные сведения см. в статье [Управление командами в Центре администрирования Microsoft Teams](manage-teams-in-modern-portal.md).

### <a name="stage-1-beginning"></a>Этап 1: начало

#### <a name="create-the-team"></a>Создание команды

The first step is to define the goal of the team (which can range from business processes to org structure to projects, or simply creating an open, unstructured collaboration hub). Defining the team goal goes hand in hand with identifying the right people. As far as practicable, it’s a good idea to foster open collaboration by aiming for broad membership. 

Владельцы команды приглашают участников, устанавливают ее аватар и описание, а также задают разрешения для каждого участника. 

> [!Tip]
>  Рекомендуем назначить не менее двух владельцев, чтобы застраховаться от возможного отсутствия или ухода кого-то из них.

#### <a name="team-origins"></a>Основы формирования команд

Команды могут создаваться различными способами, например:

-   Create the team from scratch. Add members by using individual email aliases or usernames, or expand a distribution list.
-   Create the team from an existing team, and use its channel configuration and any app configuration as a template. You can optionally also use its membership list.
-   Добавление команды в существующую группу Office 365. При этом команда также получит доступ к почтовому ящику и сайту SharePoint этой группы.
-   Use the Microsoft Graph Teams APIs or PowerShell cmdlets to create teams. The APIs can programmatically create teams based on Global Address Book attributes (such as region or department) or business processes (client engagements or classroom rosters, for example).

Дополнительные сведения об организации команд:

-   [Рекомендации по работе с командами в Teams](best-practices-organizing.md)
-   [Развертывание чата, команды, канала и приложений](deploy-chat-teams-channels-microsoft-teams-landing-page.md)
-   [Развертывание собраний и конференций](deploy-meetings-microsoft-teams-landing-page.md)
-   [Развертывание голосовой связи в облаке](cloud-voice-landing-page.md)


|    |     |
|-----------|------------|
| ![](media/audio_conferencing_image7.png) <br/>Точки принятия решений|<ul><li>Каково назначение команды?</li><li>Кто входит в команду?</li><li>Будет ли команда открытой или закрытой?</li><li>Могут ли новые участники сами вступать в команду, или их должны добавлять владельцы?</li><li>У кого будут разрешения на создание каналов и добавление вкладок, ботов или соединителей?</li></ul> |
| ![](media/audio_conferencing_image9.png)<br/>Дальнейшие действия|<ul><li>Создание команды.</li><li>Планирование каналов.</li></ul>|


#### <a name="set-up-channels"></a>Настройка каналов

Любой владелец или участник команды может создавать в ней каналы при наличии соответствующих разрешений. Важно определить цель каждого канала, например совместную работу над проектами, обсуждения конкретных тем или сферы общих интересов. По умолчанию каждая команда включает канал "Общее". Большинству команд этого недостаточно, и их участники создают другие каналы. Набор каналов скорее всего будет органично расширяться с появлением новых тем и проектов, и обсуждения могут даже выйти за рамки канала, в котором они начались.

Чтобы подогреть интерес, владелец канала может разместить приветственное сообщение, загрузить актуальные документы на вкладку **Файлы** или добавить в канал вкладки или соединители. Владелец также задает описание канала и может автоматически добавлять важные каналы в избранное, чтобы они отображались по умолчанию для всех участников команды.

|    |     |
|-----------|------------|
| ![](media/audio_conferencing_image7.png) <br/>Точки принятия решений|<ul><li>Какие каналы будут первыми добавлены в команду?</li><li>Требуются ли какие-то указания по добавлению новых каналов? (Нужно ли создавать их по проектам, темам или другим критериям?)</li></ul> |
| ![](media/audio_conferencing_image9.png)<br/>Дальнейшие действия|<ul><li>Создание первых каналов.</li><li>Приветственное сообщение.</li><li>Начало совместной работы.</li></ul>|

### <a name="stage-2-middle"></a>Этап 2: использование

С началом работы в команде список ее участников скорее всего начнет меняться, равно как и иерархия канала. Если команду не нужно строго контролировать и ограничивать, стоит поощрять эксперименты, даже ни к чему не приводящие. Когда пользователи почувствуют себя увереннее, они могут попробовать \@упоминания, начать добавлять каналы в избранное или публиковать записи в канал "Общее". Команды бывают разные, поэтому позвольте им развиваться самим по мере работы. Вы можете отслеживать использование и работоспособность команды с помощью функций отчетности Teams.

Доверие, уважение к чужому мнению и дух совместной работы будут естественным образом развиваться по мере создания и поддержания значимых групповых диалогов в Teams. Участники команды могут оценить преимущества групповых бесед над личными чатами. У отдельных команд обычно появляется собственный стиль с собственными "фишками", например стикерами и Giphy. В то же время важно противодействовать всем попыткам грубого или бесконтрольного поведения.

Команда — это живой организм, за которым нужно периодически следить и ухаживать. Существует несколько основных рекомендаций:

-   Назначьте "энтузиастов", которые будут поддерживать активность команды, а также находить и продвигать новые приемы работы. 
-   Внимательно следите за гостями: их доступ должен строго ограничиваться бизнес-потребностями.
-   Давайте каналам развиваться вместе с бизнес-потребностями, добавляя новые каналы по мере необходимости и позволяя старым каналам постепенно уходить в тень (а если они содержат конфиденциальные или временные данные, подумайте об их архивации или удалении в зависимости от ваших требований к хранению данных).
-   Создавайте новые команды при появлении крупных групп или объединений по интересам.
-   Попробуйте использовать в каналах различные средства совместной работы, например собрания в каналах или обсуждения во вкладках по важным документам.

Если активность в команде начинает снижаться, попробуйте предпринять следующие меры:

-   Настаивайте на общении в командах, а не по электронной почте.
-   Используйте мобильные приложения, чтобы стимулировать участие.
-   Удалите лишние каналы.

|    |     |
|-----------|------------|
| ![](media/audio_conferencing_image7.png) <br/>Точки принятия решений|<ul><li>Кто будет отслеживать использование для выявления проблем?</li><li>По каким показателям будет оцениваться работоспособность команды?</li><li>Определите команды, использование которых подошло к концу.</li><li>Определите угасшие команды, которые по-прежнему выполняют свою задачу, но которые нужно оживить.</li></ul> |
| ![](media/audio_conferencing_image9.png)<br/>Следующий шаг|<ul><li>Внедрите процедуры мониторинга работоспособности отдельных команд.</li></ul>|

### <a name="stage-3-end"></a>Этап 3: окончание

Когда работа команды достигла своей цели, важно формально подвести под ней черту. Это дает участникам ощущение выполненной работы и гарантирует, что никто больше не будет впустую обращаться к устаревшей информации. Вы также можете провести какие-нибудь заключительные мероприятия, например итоговые совещания и составление сводного резюме.

Вы можете удалить команды, которые больше не потребуются (например, созданные исключительно для тестирования или содержащие конфиденциальные данные). Команды удаляются с использованием "мягкого удаления", при котором ИТ-отдел может восстановить команду в течение 21 дня (или 30 дней для групп Office 365). Удаление команд не влияет на чаты или контент, которые были сохранены согласно политикам соответствия.

Вы также можете использовать политики срока действия или политики хранения в дополнение к функциям архивирования, чтобы дополнительно защитить данные команд, которые больше не активны или чьи владельцы покинули организацию.

Сведения о настройке политик срока действия и политик хранения: [Обзор обеспечения безопасности и соответствия в Microsoft Teams](security-compliance-overview.md).

|    |     |
|-----------|------------|
| ![](media/audio_conferencing_image7.png) <br/>Точки принятия решений|<ul><li>Определите, как будет выглядеть завершение жизненного цикла команды.</li><li>Определите, следует ли сохранять содержимое команды и на какой срок.</li></ul> |
| ![](media/audio_conferencing_image9.png)<br/>Дальнейшие действия|<ul><li>Задокументируйте полученный опыт.</li><li>При необходимости заархивируйте нужные данные.</li></ul>|

