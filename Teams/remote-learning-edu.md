---
title: Начало работы с Microsoft Teams для дистанционного обучения
author: DaniEASmith
ms.author: danismith
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: karsmith, lakuan
description: Руководство по запуску удаленного обучения для Microsoft Teams для EDU.
ms.localizationpriority: high
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- remotework
appliesto:
- Microsoft Teams
ms.openlocfilehash: 231007549102b8cddc02a0d2a5d29266662b4b2f
ms.sourcegitcommit: 7a1fb6e15c21368afa34cd212865437781f721e2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/31/2022
ms.locfileid: "67466027"
---
# <a name="get-started-with-microsoft-teams-for-remote-learning"></a>Начните с Microsoft Teams для дистанционного обучения

В этой статье рассматриваются шаги ИТ-администрирования для настройки учебного заведения для удаленного обучения с помощью Microsoft Teams.

В Teams **преподаватели** могут:

- Быстро общаются со учащимися.
- Предоставление общего доступа к файлам и веб-сайтам.
- Создание записных книжек oneNote для занятий.
  - Упорядочение интерактивных занятий.
  - Предоставьте эффективные и временные отзывы.
- Распределение и оценка заданий.
- Делитесь учебными материалами в профессиональных учебных сообществах.

**Администраторы и сотрудники образовательных учреждений** могут:

- Будьте в курсе событий.
- Совместная работа с помощью Staff Teams для объявлений и тематических бесед.

# <a name="accounts--licenses"></a>[Учетные записи & лицензий](#tab/accounts)

## <a name="user-accounts-licenses-and-identity-security"></a>Учетные записи пользователей, лицензии и безопасность идентификационных данных

Teams использует Microsoft 365 для проверки подлинности пользователей и предоставления служб. Для упрощения совместной работы у всех пользователей должны быть установлены удостоверения Microsoft 365.

Если удостоверения пользователей еще не существуют, выполните следующие действия, чтобы установить их:

1. [Создание пользователей с помощью School Data Sync](/microsoft-365/education/deploy/school-data-sync).
2. [Назначение лицензий пользователям](teams-edu-licensing.md).
3. [Создайте группы Microsoft 365](Office-365-groups.md).
4. [Настройка Exchange](Exchange-Teams-interact.md).
5. [Настройка SharePoint и OneDrive](SharePoint-OneDrive-interact.md).
6. [Настройка пользователей с электронной почтой Google](/microsoft-365/education/deploy/enabling-teams-for-education-for-google-users).

Microsoft Teams входит во все планы Microsoft 365, включая бесплатный план A1 для образования.

Рекомендации по развертыванию Microsoft 365 и настройке Teams см. в статье "Создание клиента [Microsoft 365"](/microsoft-365/education/deploy/create-your-office-365-tenant).

# <a name="set-up-teams"></a>[Настройка Teams](#tab/setup)

## <a name="easily-set-up-teams"></a>Настройте Teams без проблем

Чтобы приступить к работе с Teams, необходимо выполнить следующие два действия:

### <a name="1-allow-users-to-create-teams"></a>1. Разрешить пользователям создавать команды

**По умолчанию все пользователи могут создавать группы Microsoft 365 и Teams**, но эта возможность не всегда подходит.

Например, в некоторых учебных заведениях может потребоваться запретить учащимся создавать Teams без контроля. Создание групп и групп Microsoft 365 может быть [ограничено определенными группами безопасности](/microsoft-365/admin/create-groups/manage-creation-of-groups).

Для образовательных учреждений мы рекомендуем разрешить всем, включая учащихся, создавать команды для занятий, исследований, групповых проектов и учебных групп.

Пошаговое руководство по созданию Teams см. в статье "Создание команды [класса в Microsoft Teams"](https://support.office.com/article/create-a-class-team-in-microsoft-teams-preview-fae422eb-58b7-4431-9ff2-a4b9b6ae7c5b).

### <a name="2-configure-user-experiences-using-policies"></a>2. Настройте взаимодействие с пользователем с помощью политик

[!INCLUDE [policy-wizard-edu](includes/policy-wizard-edu.md)]

> [!NOTE]
> Узнайте, [как обеспечить безопасность учащихся в Teams для дистанционного обучения](https://support.office.com/article/f00fa399-0473-4d31-ab72-644c137e11c8).
>
> Если вы хотите просмотреть наши рекомендации по политике EDU, ознакомьтесь с политиками и пакетами политик [Teams для образовательных учреждений](policy-packages-edu.md).

Политики Teams управляет возможностями, доступными для определенных пользователей или групп. Политики могут определять, кому следует разрешить использовать частный чат, частные звонки, планирование собраний, типы контента, к которым можно использовать общий доступ, и т. д.

**Сотрудники высшего образования, преподаватели и учащиеся** могут использовать глобальные политики по умолчанию. Вы можете настроить политики, чтобы добавить дополнительные функциональные возможности в Teams, включая возможности [перевода и](messaging-policies-in-teams.md#messaging-policy-settings) автоматическое [транскрибирование собраний](meetings-policies-recording-and-transcription.md#transcription).

**Учащимся в основном и дополнительном** учебном заведении могут потребоваться ограниченные возможности. Рекомендуется внести изменения в политику учащихся в политику "Глобальная (по умолчанию для всей организации)".

**Сотрудникам и преподавателям** основного и дополнительного учебного заведения следует назначить политики, которые предоставляют ключевые возможности, такие как разрешение частного чата и планирования собраний. [Назначьте эти политики всем вашим сотрудникам и преподавателям](batch-group-policy-assignment-edu.md).

> [!IMPORTANT]
> Для политик собраний, назначенных всем пользователям, рекомендуется установить для параметра "Автоматически допускать пользователей" значение **"Все в организации"**. Это гарантирует, что пользователи, не прошедшие проверку подлинности, должны быть допущены из "зала ожидания", прежде чем они смогут присоединиться к собраниям Teams.
>
> Дополнительные сведения см. в статье [Управление политиками собраний в Teams](meeting-policies-participants-and-guests.md#automatically-admit-people).

# <a name="class-teams"></a>[Команды классов](#tab/class-teams)

## <a name="create-class-teams-for-secure-classroom-use"></a>Создайте команды класса для безопасного использования в классе

Microsoft Teams для Education предлагает [конкретные типы команд](https://support.office.com/article/choose-a-team-type-to-collaborate-in-microsoft-teams-0a971053-d640-4555-9fd7-f785c2b99e67) для использования в образовательных целях. [Тип команды класса](https://support.office.com/article/create-a-class-team-in-microsoft-teams-fae422eb-58b7-4431-9ff2-a4b9b6ae7c5b) предназначен для использования в классах и обладает специальными функциями, соответствующими потребностям учебных заведений:

- Назначения.
- Классов.
- Записная книжка OneNote для аудитории.
- [Папка "Материалы для занятий"](https://support.office.com/article/Use-folders-to-create-read-only-files-for-students-or-other-team-members-0e7791d7-8c9c-4749-9bca-984289477988)  для защиты содержимого, доступного только для чтения, для учащихся.
- [аналитика](./class-insights.md) для предоставления данных в режиме реального времени, связанных с активностью учащихся, заданиями и атмосферой в каждом классе;
- [Ранний доступ преподавателя](https://support.microsoft.com/article/activate-early-access-class-teams-created-with-school-data-sync-0d154696-66ab-4fcf-b22f-c3d9a82aaf78) к настройке класса перед добавлением учащихся.
- Возможность отключения отключения работы учащихся и других специальных разрешений.

Группы классов можно создавать с помощью:

- [School Data Sync (SDS).](#automatic-team-creation-using-sds)
- [Создание под руководством преподавателя с помощью групп классов Microsoft 365](#educator-led-team-creation-from-microsoft-365-class-groups).
- [Скрипты PowerShell, использующие API Graph](#powershell-script-using-graph-apis).
- [Создание команды вручную](#manual-team-creation).

Мы рассмотрим различные варианты, чтобы помочь вам выбрать способ развертывания, наиболее соответствующий вашим потребностям.

### <a name="automatic-team-creation-using-sds"></a>Автоматическое создание команды с помощью SDS

[School Data Sync (SDS)](/SchoolDataSync) считывает данные из системы записей учебного заведения, например системы информационной системы учащихся (SIS) или системы управления обучением (LMS).

SDS может импортировать данные из любой системы записи и имеет встроенные соединители для многих [поставщиков служб SIS](/schooldatasync/frequently-asked-questions#what-sismis-vendors-does-school-data-sync-support).  

#### <a name="benefits-of-sds"></a>Преимущества SDS

- Автоматически создает пользователей и применяет лицензии.
- Автоматически создает и обслуживает команды классов.
- Синхронизируется с SIS/LMS для сохранения изменений членства учащихся.
- [Позволяет преподавателям подготавливать классы перед добавлением учащихся](https://support.office.com/article/activate-early-access-class-teams-created-with-school-data-sync-0d154696-66ab-4fcf-b22f-c3d9a82aaf78).
- Может автоматически создавать группы безопасности.
- Создает административные единицы для ограниченного административного делегирования.
- [Разрешает сброс пароля преподавателя](/schooldatasync/how-to-enable-teacher-password-reset).
- Имеет встроенные возможности очистки для переименования и архивации групп и команд.
- [Синхронизирует оценки из Teams в SIS](/schooldatasync/grade-sync).
- [Защищает персональные данные учащихся](/schooldatasync/protecting-student-personal-data).
- Отслеживает согласие защитника и управляет ими.
- Предоставляет более Insights для образования данных.

#### <a name="considerations-for-sds"></a>Рекомендации по SDS

SDS создает команды в два этапа:

1. SDS создает группу Microsoft 365 в Azure Active Directory (Azure AD).
2. SDS автоматически преобразует эту группу в команду.

Второй этап создания команд в SDS является необязательным. Администратор может решить не создавать команды автоматически в зависимости от того, сколько времени это займет и сколько неиспользуемых групп получится в результате. Вместо этого ознакомьтесь с [методом создания команды под руководством преподавателя](#educator-led-team-creation-from-microsoft-365-class-groups).  

#### <a name="get-started-with-sds"></a>Начало работы с SDS

Чтобы приступить к работе, перейдите в [School Data Sync (SDS)](/SchoolDataSync) [https://aka.ms/sdssupport](https://aka.ms/sdssupport) и обратитесь за бесплатной помощью по развертыванию.  

### <a name="educator-led-team-creation-from-microsoft-365-class-groups"></a>Создание команды под руководством преподавателя из групп классов Microsoft 365

Создание команд под руководством преподавателя позволяет преподавателям легко создавать необходимые классы.  

Этот подход позволяет использовать SDS для создания групп для каждого класса (рекомендуется) или использовать API Graph для их создания самостоятельно[](/graph/api/educationroot-post-classes).

После подготовки групп классов преподаватели могут преобразовать свои группы в команды:

1. Выберите вкладку Teams в Teams.
2. В верхней части клиента щелкните значок **предлагаемых классов** .

#### <a name="benefits-of-educator-led-team-creation"></a>Преимущества создания команды под руководством преподавателя

- Классы подготовлены и предложены, но не созданы, если преподаватель не собирается их использовать.
- Для учреждений с более чем 500 000 команд этот метод сокращает количество ненужных команд.
- [Преимущества SDS](#benefits-of-sds).
- API Graph преимущества.
  - Предоставляет преподавателям возможность управлять созданием классов.
  - Не требуется интеграция с SDS.

#### <a name="considerations-for-educator-led-team-creation"></a>Рекомендации по созданию команд под руководством преподавателя

- Не полностью автоматизирован и требует действий преподавателя.
- Преподаватели, у которых нет разрешения на создание команд, по-прежнему [могут создавать команды из существующих групп](https://support.office.com/article/create-a-class-team-in-microsoft-teams-preview-fae422eb-58b7-4431-9ff2-a4b9b6ae7c5b).
- API Graph требуются высокий уровень технических знаний, время на создание и запуск скрипта, а также время на устранение любых проблем.

#### <a name="get-started-with-educator-led-team-creation"></a>Начало работы с созданием команды под руководством преподавателя

Чтобы приступить к работе с методом SDS, перейдите в [School Data Sync (SDS)](/SchoolDataSync) [https://aka.ms/sdssupport](https://aka.ms/sdssupport) и обратитесь за бесплатной помощью по развертыванию.

- Необходимо отключить автоматическое создание команды в профиле SDS.
- Вы можете использовать сочетание автоматического и командного создания под руководством преподавателя для команд классов с помощью двух профилей SDS.

Инструкции по использованию API Graph см. в статьях [API Graph](/graph/api/educationroot-post-classes?tabs=http&view=graph-rest-1.0&preserve-view=true) и [Создание команды класса](/graph/api/educationroot-post-classes?tabs=http&view=graph-rest-beta&preserve-view=true).  

### <a name="powershell-script-using-graph-apis"></a>Скрипт PowerShell с использованием интерфейсов API Graph

С помощью PowerShell можно написать сценарий для создания команд и каналов, а также настроить параметры автоматически.

Для этого метода администратор должен сначала создать группу [, добавить преподавателей](/graph/teams-create-group-and-team) и учащихся, а затем создать команду.

Вы также можете использовать [microsoft API Graph для создания, настройки, клонирования и архивации команд](/graph/api/resources/teams-api-overview).

#### <a name="benefits-of-powershell-scripts"></a>Преимущества сценариев PowerShell

- Предоставляет ИТ-администраторам контроль над созданием класса.
- Возможность создания команд с ранним доступом преподавателей или мгновенным доступом учащихся.
- [Синхронизирует изменения членства учащихся в Azure AD группу](/graph/api/team-post?tabs=http&view=graph-rest-beta#example-4-create-a-team-from-group&preserve-view=true).

#### <a name="considerations-for-powershell-scripts"></a>Рекомендации по сценариям PowerShell

- Требуется высокий уровень технической квалификации, а также время на создание и запуск скрипта и исправление ошибок при создании групп классов.
- Логика обработки ошибок и повторных попыток отсутствует.
- Изменения членства не синхронизируются с SIS.

> [!NOTE]
> Командам классов необходимо членство в скрытых группах, чтобы только преподавателям и учащимся из класса были видны участники учебной группы. Сведения о создании группы классов Microsoft 365 см. в [](/graph/api/educationroot-post-classes?tabs=http&view=graph-rest-beta&preserve-view=true) статье "Создание группы классов в соответствии с требованиями к конфиденциальности".

### <a name="manual-team-creation"></a>Создание команды вручную

Пользователи могут адаптировать свой интерфейс Teams, имея возможность создавать собственные команды.

В зависимости от разрешений пользователя он может:

- [Настройка собственных команд и приглашение пользователей, включая учащихся](https://support.microsoft.com/article/create-a-class-team-in-microsoft-teams-fae422eb-58b7-4431-9ff2-a4b9b6ae7c5b#ID0EADAAA=Create_a_team_from_scratch).
- [Вручную добавьте пользователей в команду](https://support.office.com/article/add-a-student-to-a-class-team-b88263bb-ace1-4702-8a48-f8a2cf4af954).
- [Совместное использование кода соединения](https://support.office.com/article/Create-a-link-or-a-code-for-joining-a-team-11b0de3b-9288-4cb4-bc49-795e7028296f).
- [Поделитесь ссылкой на команду](https://support.office.com/article/Create-a-link-or-a-code-for-joining-a-team-11b0de3b-9288-4cb4-bc49-795e7028296f).

Лучше всего, чтобы преподаватели добавляли своих учащихся в команду, чтобы учащиеся получили доступ и были уведомлены о добавлении.

#### <a name="benefits-of-manual-team-creation"></a>Преимущества создания команды вручную

- Предоставляет преподавателям полный контроль над созданием класса.
- Команды классов создаются немедленно.

#### <a name="considerations-for-manual-team-creation"></a>Рекомендации по созданию команды вручную

- Требуются действия и затраты времени со стороны преподавателя.
- Членство учащихся не синхронизируется с SIS и требует ручного управления.
- Учащиеся получат непосредственный доступ к командам для занятий.

### <a name="recommended-best-practices"></a>Рекомендации

- Разверните команды заранее, чтобы убедиться в их надежной работе и готовности к первому дню учебы.

- При проблемах с автоматическим созданием команд SDS преподаватели могут использовать метод создания команды под руководством преподавателя [, чтобы повторить](#educator-led-team-creation-from-microsoft-365-class-groups) попытку. [Создание команды вручную](#manual-team-creation) — это еще одно решение, но классы не синхронизируются с SIS.

- Максимальное количество команд в клиенте — 500 000. Таким образом, администраторам следует сократить количество неиспользуемых команд, чтобы избежать достижения этих ограничений. Дополнительные сведения см. [в разделе "Ограничения и спецификации для Microsoft Teams"](limits-specifications-teams.md).  

# <a name="educator-early-access"></a>[Ранний доступ для преподавателей](#tab/early-access)

## <a name="early-access-to-class-teams"></a>Ранний доступ к командам классов

Ранний доступ к классам Teams позволяет преподавателям получать доступ к своим командам для занятий, прежде чем учащиеся смогут их просматривать. У преподавателей будет время на настройку, добавление файлов и упорядочение перед предоставлением доступа учащимся.

Когда учащиеся смогут получить доступ к команде, они смогут [активировать свой класс](https://support.office.com/article/activate-early-access-class-teams-created-with-school-data-sync-0d154696-66ab-4fcf-b22f-c3d9a82aaf78).

### <a name="how-do-i-create-class-teams-that-allow-educators-early-access-to-set-up-a-team-before-admitting-students"></a>Как создавать команды классов, позволяющие преподавателям предварительно настроить команду перед добавлением учащихся?

При создании команд из групп (с помощью SDS, API Graph или под руководством преподавателя) по умолчанию автоматически создаются команды с ранним доступом.

Для создания собственных команд с ранним доступом с использованием API Graph вам потребуется [создать класс](/graph/api/educationroot-post-classes?tabs=http&view=graph-rest-beta&preserve-view=true) и [создать команду из группы](/graph/api/team-post?tabs=http&view=graph-rest-beta#example-4-create-a-team-from-group&preserve-view=true).

### <a name="how-do-i-check-if-a-class-is-activated"></a>Как проверить, активирован ли класс?

В [типе ресурса группы](/graph/api/resources/team?view=graph-rest-beta&preserve-view=true) просмотрите свойство [isMembershipLimitedToOwners](/graph/api/resources/team?view=graph-rest-beta#properties&preserve-view=true), чтобы узнать, активирован ли класс.

С помощью [API Get Team](/graph/api/team-get?tabs=http&view=graph-rest-beta&preserve-view=true) запросите свойство ```isMembershipLimitedToOwners``` для конкретного класса. Если команда активирована, будет возвращено значение false. Если команда не была активирована, она вернет значение true.

### <a name="how-do-i-activate-a-class-for-an-educator"></a>Как активировать класс для преподавателя?

Используйте [API команды](/graph/api/team-update?tabs=http&view=graph-rest-beta&preserve-view=true) обновления и задайте ```isMembershipLimitedToOwners``` для свойства значение false, чтобы активировать команду от имени преподавателя. После активации команды ее невозможно отменить.

### <a name="create-staff-teams-for-staff-communication-and-collaboration"></a>Создание команд персонала для общения и совместной работы персонала.

[Команды по типу персонала](https://support.office.com/article/create-a-staff-team-in-microsoft-teams-314ac9d5-36a9-408e-8ae4-7ef20e9f1ddf) предназначены для администраторов и сотрудников образовательных учреждений для совместного использования информации и совместной работы над инициативами на уровне учреждений.

Администраторы образовательных учреждений могут добавлять сотрудников в команду с помощью мастера создания команды [, добавлять](https://support.office.com/article/add-members-to-a-team-in-teams-aff2249d-b456-4bc3-81e7-52327b6b38e9) участников после создания команды или делиться кодом присоединения или ссылкой [на команду](https://support.office.com/article/create-a-link-or-a-code-for-joining-a-team-11b0de3b-9288-4cb4-bc49-795e7028296f).

# <a name="meeting-scenarios"></a>[Сценарии собраний](#tab/scenarios)

## <a name="teams-meeting-scenarios"></a>Сценарии Собрании Teams

### <a name="collaborative-meetings-for-virtual-classes"></a>Совместные встречи для виртуальных классов

[Совещания Microsoft Teams](./tutorial-meetings-in-teams.yml) поддерживают до 250 одновременных участников, включая возможность иметь аудио, видео, [обмен контентом](https://support.office.com/article/show-your-screen-during-a-meeting-90c84e5a-b6fe-4ed4-9687-5923d230d3a7), доски и общие заметки.

Собрания могут быть:

- [Запланировано в клиенте Teams](./tutorial-meetings-in-teams.yml).
- Записано и сохранено для участников для последующей проверки.
- [Транскрибирование для простого поиска содержимого](https://support.office.com/article/Microsoft-Stream-automatically-creates-closed-captions-for-videos-8d6ac353-9ff2-4e2b-bca1-329499455308).
- Доступ к нему можно получить с помощью ноутбука или веб-камеры мобильного телефона, микрофона и динамика.
- [Оптимизировано для определенных устройств](https://products.office.com/microsoft-teams/across-devices/devices).
- Завершено для всех участников, чтобы убедиться, что учащиеся не находятся на собрании без защиты.

### <a name="districtuniversity-events-or-updates"></a>Район / университет события или обновления

Некоторые собрания имеют большую аудиторию и дополнительные рабочие потребности. Эти встречи часто определяют докладчиков, продюсеров и модерируемых вопросов и ответов.

Проведение этих собраний поддерживается в Teams с помощью [трансляций Microsoft Teams](teams-live-events/what-are-teams-live-events.md).

Трансляции можно использовать для таких сценариев, как:

- Обновления для всего округа или университета.
- Адреса руководства.
- Инструкции для больших классов или групп учащихся.
- Расширение сообщества.

Сведения о проведении динамических сеансов:

- [Планирование и планирование трансляции](https://support.office.com/article/video-plan-and-schedule-a-live-event-f92363a0-6d98-46d2-bdd9-f2248075e502).
- [Создание трансляции](https://support.office.com/article/video-produce-a-live-event-34c89e79-ffd4-4a6a-baf6-77055e0709cb).
- [Посетите трансляцию](https://support.office.com/article/video-attend-a-live-event-d837ad8d-ce34-44d0-9744-9beb50e943ac).
- [Модерация Q&A](https://support.office.com/article/video-moderating-a-q-a-4984e582-8c66-4ea3-aaaf-d93cf62e1b76).

# <a name="resources"></a>[Ресурсы](#tab/resources)

## <a name="support-resources"></a>Ресурсы поддержки

Общие сведения о переходе на удаленное обучение см. [здесь](https://www.microsoft.com/education/remote-learning)

Если вы ИТ-администратор, преподаватель, учащийся или опекун, эти ресурсы могут помочь вам использовать Teams:

- **ИТ-администраторы**
  - [Функции Teams по платформам](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3).
  - [Скачайте и распространите клиенты Teams](get-clients.md).
  - [Устранение неполадок Teams](/MicrosoftTeams/troubleshoot/teams).
  - [Teams для инфраструктуры виртуализированных рабочих столов](./teams-for-vdi.md).
  - [Мониторинг качества звонков и управление ими](monitor-call-quality-qos.md).
  - [Проверка работоспособности службы для Teams](service-health.md).
  - [Оптимизируйте трафик Microsoft 365 для удаленных сотрудников](https://techcommunity.microsoft.com/t5/office-365-blog/how-to-quickly-optimize-office-365-traffic-for-remote-staff-amp/ba-p/1214571).
  - [Контакты службы поддержки для Teams](/microsoft-365/admin/contact-support-for-business-products).
  - [Teams для образования вебинары](https://aka.ms/TeamsEDUWebinars).

- **Преподаватели**
  - [Центр справки для преподавателей](https://support.office.com/article/microsoft-teams-5aa4431a-8a3c-4aa5-87a6-b6401abea114).
  - [Справка по удаленному обучению](https://aka.ms/RemoteLearningHelp).
  - [Скачайте Teams](get-clients.md).
  - [Teams для образования вебинары](https://aka.ms/TeamsEDUWebinars).
  - [Онлайн-курс для преподавателей, использующих Teams](https://education.microsoft.com/course/9c9f5c11/overview).
  - [Онлайн-курс по разработке сред совместного обучения с помощью Teams](https://education.microsoft.com/course/b1e15cfc/overview).
  - [Подайте запрос в службу поддержки](https://www.microsoft.com/microsoft-teams/download-app).

- **Студентов**
  - [Центр справки для учащихся](https://support.office.com/article/student-help-center-395ab230-55bf-44c6-b265-e832d729b694).
  - [Справка по удаленному обучению](https://aka.ms/RemoteLearningHelp).
  - [Скачайте Teams](https://www.microsoft.com/microsoft-teams/download-app).

- **Опекунов**
  - [Справка по удаленному обучению](https://aka.ms/RemoteLearningHelp).
  - [Скачайте Teams](https://www.microsoft.com/microsoft-teams/download-app).

---
