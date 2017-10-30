---
title: "Поиск событий Microsoft Teams в журнале аудита | Служба поддержки Майкрософт"
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
description: "Сведения об извлечении данных Microsoft Teams из журнала аудита."
Set_Free_Tag: Strat_MT_TeamsAdmin
ms.openlocfilehash: 558db88d32229fcaef70ea5278d7437fbea92198
ms.sourcegitcommit: 2e557e90b4e30fe99ff9df3897b8e54f38ea2f2e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/22/2017
---
<a name="search-the-audit-log-for-events-in-microsoft-teams"></a>Поиск событий Microsoft Teams в журнале аудита
==================================================

Журнал аудита предоставляет особые возможности для поиска событий в службах Office 365. Ниже представлено несколько примеров событий специально для Microsoft Teams:

-   Создание команды

-   Удаление команды

-   Добавление канала

-   Изменение параметра

Полный список событий для Office 365 довольно велик и приведен [здесь](https://support.office.com/en-us/article/Search-the-audit-log-in-the-Office-365-Security-Compliance-Center-0d4d0f35-390b-4518-800e-0c7ec95e946c?ui=en-US&rs=en-US&ad=US#ID0EABAAA=Audited_activities).

Прежде чем просмотреть сведения аудита, нужно включить соответствующую функцию. Чтобы включить аудит, перейдите в Центр *безопасности и соответствия требованиям*. В области *Search for activity* (Поиск действия) выберите **Start recording now** (Начать запись). Через 24 часа данные аудита будут доступны в области *Audit Log Search* (Поиск в журнале аудита) на вкладке *Search & Investigation* (Поиск и анализ).


| |  |
|---------|---------|
|![](media/Search_the_audit_log_for_events_in_Microsoft_Teams_image1.png)<br></br>Важно.     |Эти данные начинаются с момента включения аудита.         |

![](media/Search_the_audit_log_for_events_in_Microsoft_Teams_image2.png)

А теперь рассмотрим, как извлечь данные Microsoft Teams из журнала аудита:

1.  Чтобы извлечь сведения из журнала аудита, перейдите в Центр [безопасности и соответствия требованиям](https://go.microsoft.com/fwlink/?linkid=855775). На вкладке *Search & Investigation* (Поиск и анализ) выберите **Audit log search** (Поиск в журнале аудита).

    а.  Microsoft Teams имеет определенные действия аудита, которые можно выбрать, как показано ниже.

![](media/Search_the_audit_log_for_events_in_Microsoft_Teams_image3.png)

2.  Выбрав нужные действия, укажите диапазон дат и пользователей, для которых нужно получить сведения Microsoft Teams. Нажмите кнопку **Найти** для получения результатов.

3.  Эти сведения можно экспортировать в Excel и при необходимости отфильтровать.


|  | |
|---------|---------|
|![](media/Search_the_audit_log_for_events_in_Microsoft_Teams_image1.png)<br></br>Важно. |Если функция аудита отключена, ее нужно включить, прежде чем в журнале аудита появятся данные.         |
