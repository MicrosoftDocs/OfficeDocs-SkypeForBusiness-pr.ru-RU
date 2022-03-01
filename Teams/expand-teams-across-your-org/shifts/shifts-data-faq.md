---
title: 'Смены данных: faq'
author: lanachin
ms.author: v-lanachin
ms.reviewer: aaku
manager: samanro
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
searchScope:
- Microsoft Teams
- Microsoft Cloud for Healthcare
description: Ответы на часто задаваемые вопросы о данных Shifts, в том числе о том, где хранятся данные Shifts, где хранятся данные, где хранятся данные, как хранение, ища и шифрование.
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
- Teams_ITAdmin_FLW
- microsoftcloud-healthcare
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 3f26413aa746b37474e7035e313fc8ffff2fb93c
ms.sourcegitcommit: 2044fdcb0c5db10dbc77c5d66e382c1b927ccdc4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/01/2022
ms.locfileid: "63039957"
---
# <a name="shifts-data-faq"></a>Смены данных: faq

В этой статье часто задаваются вопросы о данных Shifts, в том числе о том, где хранятся данные Shifts, где хранятся данные, как хранение, ища и шифрование.

## <a name="where-is-shifts-data-stored"></a>Где хранятся данные Shifts?

Данные shifts хранятся в одном из трех географических географических данных: Азиатско-Тихоокеанском регионе (APAC), Европейском союзе (ЕС) или США. Каждый регион хранит данные по крайней мере в двух регионах центра обработки данных Azure для высокого уровня доступности (HA) и аварийного восстановления (DR). В настоящее время в США и Северной Америке используются центры обработки данных в Северной центральной и Юго-Центральной америке. Дополнительные сведения см. в [Microsoft 365 данных клиента](/microsoft-365/enterprise/o365-data-locations).

В настоящее время в shifts есть возможность переноса данных в Австралии, Канаде, Франции, Японии и Великобритании. Мы активно работаем над расширением поддержки на другие расположения.

## <a name="can-i-choose-where-shifts-data-is-stored"></a>Можно ли выбрать, где хранятся данные Shifts?

При первой Teams вы выбираете страну или регион, которые установлены на уровне подписки. Shifts чтим этот выбор и использует региональные органы и регион, заданной в Teams, если мы поддерживаем этот регион. Если мы еще не в этом регионе, мы храним данные в ближайшем регионе, который мы поддерживаем. В будущем мы планируем перенести существующие данные, хранимые в ближайшем регионе, в регион, который Teams.

## <a name="can-i-access-and-export-or-delete-a-users-personal-data-in-shifts"></a>Можно ли получать и экспортировать или удалять личные данные пользователя в shifts?

Shifts соответствует Общему регламенту по защите данных (GDPR).Формальный запрос от лица (субъекта данных) на действие с персональными данными называется запросом субъекта данных (DSR). Вы можете находить личные данные и действовать с их учетом в shifts в ответ на DSR.

С помощью средства eDiscovery поиска контента в Центр соответствия требованиям Microsoft 365 можно искать и экспортировать данные расписания и часов для Excel. Для всех остальных данных Shifts можно делать снимки экрана.

Дополнительные сведения см. [Office 365 запросы субъекта данных для GDPR и CCPA](/microsoft-365/compliance/gdpr-dsr-office365).

## <a name="what-happens-to-shifts-data-if-i-turn-off-shifts-for-my-organization"></a>Что произойдет с данными Shifts, если отключить shifts для моей организации?

При отключлении shifts в организации данные *не* удаляются. Если вы отключите shifts, а затем включите shifts, ваши данные о сменах по-прежнему будут доступны.

При удалении клиента все данные Shifts удаляются по и после окончания периода хранения.

Удалить только данные shifts не существует. При удалении группы в Teams, связанные с ней данные расписания shifts удаляются после окончания периода хранения. Дополнительные сведения см. в [Microsoft 365](/compliance/assurance/assurance-data-retention-deletion-and-destruction-overview).

## <a name="can-i-recover-a-shifts-schedule-that-was-deleted"></a>Можно ли восстановить удаленное расписание смен?

Вы можете восстановить удаленное расписание, Microsoft 365 группу, которая его Teams.

По умолчанию удаленная группа Microsoft 365 сохраняется в течение 30 дней. Этот 30-дневный период называется "неявным удалением", так как вы по-прежнему можете восстановить группу. Дополнительные данные см. [в Microsoft 365 удаленных групп](/microsoft-365/admin/create-groups/restore-deleted-group?view=o365-worldwide&tabs=admin-center).

## <a name="can-i-use-custom-retention-policies-for-shifts-data"></a>Можно ли использовать настраиваемые политики хранения для данных Shifts?

В настоящее время Shifts не поддерживает настраиваемые политики хранения.

Дополнительные информацию о политиках хранения в Teams см. в Teams и [](/microsoft-365/compliance/retention-policies-teams) Управление политиками хранения для [Teams.](../../retention-policies.md)

## <a name="can-i-retrieve-shifts-data-for-a-user-whose-license-was-revoked"></a>Можно ли получить данные shifts для пользователя, лицензия которого была отозвана?

На сегодняшний день мы не предлагаем возможность получения данных для пользователя, лицензия которого была отозвана. Мы работаем над этой возможностью.

## <a name="what-type-of-encryption-does-shifts-use-for-data-at-rest-and-in-transit"></a>Какой тип шифрования использует shifts для хранения и передачи данных?

Данные shifts шифруются неавтохими от Azure Cosmos DB и Azure служба хранилища. Дополнительные сведения см. в неавтетном шифровании данных [Azure](/azure/security/fundamentals/encryption-atrest) и Шифрование данных в [Azure Cosmos DB](/azure/cosmos-db/database-encryption-at-rest).

Смены: Microsoft 365 правила шифрования данных во время передачи. Дополнительные сведения см. в [теме Шифрование для передачи данных](/compliance/assurance/assurance-encryption-in-transit).

Проверка соответствия требованиям SOC2 ежегодно проверяет шифрование неавтифицированных и перемещаемой данных.

## <a name="can-i-access-immutable-copies-of-shifts-data"></a>Можно ли получить доступ к неоменяемым копиям данных Shifts?

Мы не храним неоплачимые копии данных Shifts. Например, руководитель может вносить изменения в расписание, например добавлять заметки, изменять время смен, назначать задачи и так далее.

## <a name="can-shifts-data-be-edited"></a>Можно ли изменять данные Shifts?

Есть определенные аспекты смен, которые нельзя изменить, и некоторые аспекты, которые можно изменить. Например, сведения о сменах, такие как заметки и цвета, можно изменять так же, как в приложении "Смены". Запросы на смену нельзя редактировать, если они не соблюсти.

Чтобы узнать, какие поля были изменены, в журнале Microsoft 365 поиска событий Shifts. Дополнительные данные о событиях, регистрируются в действиях shifts в журнале Microsoft 365 аудита, см. в Teams [действиях](../../audit-log-events.md#shifts-in-teams-activities).

## <a name="my-organization-uses-a-workforce-management-system-for-scheduling-can-we-integrate-with-and-access-shifts-data"></a>В моей организации для планирования используется система управления трудовыми ресурсами. Можно ли интегрироваться с данными Shifts и получить к ним доступ?

Смены Graph API-систем, которые можно интегрировать с системами управления внешними ресурсами (WFM). Дополнительные информации см. в [Graph API shifts](/graph/api/resources/shift).

Мы также предлагаем управляемые соединители Shifts и соединители Shifts с открытым кодом. С помощью этих соедините вкладок вы можете интегрировать свою систему WFM непосредственно со сменами. Дополнительные информацию о соединителах shifts и поддерживаемых WFM-системах см. в этой [теме](shifts-connectors.md).

## <a name="can-shifts-data-be-deleted-permanently-after-a-specified-period-of-time"></a>Можно ли окончательно удалять данные shifts через заданный период времени?

На сегодняшний день мы не удаляем ваши данные Shifts. С [помощью Graph shifts](/graph/api/resources/shift) можно создать приложение с помощью Power Apps хранения данных в течение [](/powerapps/maker/) заданного периода времени. Однако мы не поддерживаем эту поддержку по своей языке.

## <a name="can-shifts-data-be-moved-in-a-tenant-to-tenant-migration"></a>Можно ли переносить данные Shifts при миграции между клиентом и клиентом?

Данные shifts можно перенести из одного клиента в другой по определенному запросу. Имейте в виду, что миграция "клиент-клиент" не поддерживается в клиенте, но ее можно повысить в качестве запроса клиента.

## <a name="related-articles"></a>Статьи по теме

- ["Смены" для Teams](../shifts-for-teams-landing-page.md)
- [Управление приложением "Смены"](manage-the-shifts-app-for-your-organization-in-teams.md)
