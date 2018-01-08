---
title: "Поиск событий Microsoft Teams в журнале аудита"
author: LolaJacobsen
ms.author: lolaj
manager: lolaj
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
description: "Сведения об извлечении данных Microsoft Teams из журнала аудита."
ms.openlocfilehash: bea1a808fd92d3b43caf8ee61152a999ca3af8a3
ms.sourcegitcommit: 3faedb6057da8650b06b05f9c9bdd941d5ade175
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/20/2017
---
<a name="search-the-audit-log-for-events-in-microsoft-teams"></a>Поиск событий Microsoft Teams в журнале аудита
==================================================

Журнал аудита предоставляет особые возможности для поиска событий в службах Office 365. Ниже представлено несколько примеров событий специально для Microsoft Teams:

-   Создание команды

-   Удаление команды

-   Добавление канала

-   Изменение параметра

Полный список событий для Office 365 довольно велик и приведен [здесь](https://support.office.com/en-us/article/Search-the-audit-log-in-the-Office-365-Security-Compliance-Center-0d4d0f35-390b-4518-800e-0c7ec95e946c?ui=en-US&rs=en-US&ad=US#ID0EABAAA=Audited_activities).

Прежде чем просмотреть сведения аудита, нужно включить соответствующую функцию. Чтобы включить аудит, перейдите в Центр администрирования *Безопасность и соответствие требованиям*. В области *Search for activity* (Поиск действия) выберите **Start recording now** (Начать запись). Через 24 часа данные аудита будут доступны в области *Audit Log Search* (Поиск в журнале аудита) на вкладке *Search & Investigation* (Поиск и анализ).


> [!IMPORTANT]
> Эти данные начинаются с момента включения аудита.



![Снимок экрана со страницей поиска журнала аудита в Центре безопасности и соответствия требованиям.](media/Search_the_audit_log_for_events_in_Microsoft_Teams_image2.png)

А теперь рассмотрим, как извлечь данные Microsoft Teams из журнала аудита:

1.  Чтобы извлечь сведения из журнала аудита, перейдите в Центр [безопасности и соответствия требованиям](https://go.microsoft.com/fwlink/?linkid=855775). На вкладке *Search & Investigation* (Поиск и анализ) выберите **Audit log search** (Поиск в журнале аудита).

    а.  Microsoft Teams имеет определенные действия аудита, которые можно выбрать, как показано ниже.

![Снимок экрана со страницей поиска журнала аудита в Центре безопасности и соответствия требованиям.](media/Search_the_audit_log_for_events_in_Microsoft_Teams_image3.png)

2.  Выбрав нужные действия, укажите диапазон дат и пользователей, для которых нужно получить сведения Microsoft Teams. Нажмите кнопку **Найти** для получения результатов.

3.  Эти сведения можно экспортировать в Excel и при необходимости отфильтровать.


> [!IMPORTANT]
> Если функция аудита не была включена ранее, ее нужно включить, чтобы в журнале аудита появились данные.


