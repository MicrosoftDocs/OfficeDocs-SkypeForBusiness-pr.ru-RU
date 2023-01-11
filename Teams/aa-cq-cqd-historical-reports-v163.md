---
title: Отчеты об истории автосекретаря и очереди вызовов для GCC High и DoD
author: DaniEASmith
ms.author: danismith
manager: serdars
ms.reviewer: colongma
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-voice
search.appverid: MET150
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Reporting
- ms.teamsadmincenter.directrouting.cqd
- ms.lync.lac.ToolsCallQualityDashboard
ROBOTS: NOINDEX, NOFOLLOW
description: Узнайте, как использовать отчет Power BI "Автосекретарь Teams" & отчета Power BI "Очередь вызовов" для просмотра исторических данных автосекретаря и очереди вызовов для клиентов GCC High и DoD.
ms.openlocfilehash: 619be6d7f0f78f67ef2db0f0693de82120d128c4
ms.sourcegitcommit: e9718ad7e23317d490b238b3801267cb2e6b26e2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/28/2022
ms.locfileid: "69176763"
---
# <a name="auto-attendant-and-call-queue-historical-reports-for-gcc-high-and-dod"></a>Отчеты об истории автосекретаря и очереди вызовов для GCC High и DoD

> [!IMPORTANT]
> Поддержка общедоступного облака для шаблона версии 1.63 завершится 25 ноября 2022 г.
>
> Клиенты общедоступного облака должны использовать версию 3.x.x [автосекретаря & исторические отчеты очереди вызовов](aa-cq-cqd-historical-reports.md)

## <a name="v163-published-on-august-24-2022"></a>Версия 1.63 опубликована 24 августа 2022 г.

**Шаблон Power BI "Автосекретарь" & "Очередь вызовов**" предоставляет следующие три отчета:

- В отчете [Автосекретарь](media/aa-cq-historical-report-sample-aa-v163.png) отображается аналитика звонков, поступающих в автосекретаря.
- В отчете ["Очередь вызовов](media/aa-cq-historical-report-sample-cq-v163.png) " отображается аналитика звонков, поступающих в очереди звонков.
- В отчете ["Временная шкала агента"](media/aa-cq-historical-report-sample-at-v163.png) отображается представление временной шкалы агентов, активных в вызовах очереди вызовов.

В этих отчетах используются данные из хранилища данных [панели мониторинга качества звонков (CQD).](CQD-Power-BI-query-templates.md) 

## <a name="v163-prerequisites"></a>Предварительные требования для версии 1.63

### <a name="power-bi-desktop"></a>Power BI Desktop
Необходимо установить Power BI Desktop. Вы можете установить и использовать бесплатную версию из [Майкрософт Магазина Windows](https://aka.ms/pbidesktopstore).

Минимальная совместимая версия — 2.85.681.0 (сентябрь 2020 г.).

### <a name="permissions-to-access-the-cqd-pipeline"></a>Разрешения на доступ к конвейеру CQD

Учетная запись, используемая для просмотра исторического отчета, должна иметь разрешения на доступ к конвейеру данных CQD. Дополнительные сведения см. в разделе [Роль доступа CQD](./turning-on-and-using-call-quality-dashboard.md#assign-admin-roles-for-access-to-cqd).

## <a name="v163-installation"></a>Установка версии 1.63 

В следующих шагах предполагается, что вы уже установили Power BI Desktop на компьютере и что у вашей учетной записи есть необходимые разрешения для доступа к конвейеру данных CQD.

Выполните следующие действия.

1. Скачайте и сохраните ZIP-файл [шаблонов запросов CQD Power BI](https://www.microsoft.com/download/details.aspx?id=102291) на компьютере.

1. Откройте ZIP-файл.

1. `CQD Teams Auto Attendant & Call Queue Historical Report V1.60.pbit` Откройте файл шаблона. Power BI Desktop должно запуститься.

1. Вам будет предложено выбрать регион конвейера данных CQD. Выберите регион, в котором находится клиент.

  :::image type="content" source="media/aa-cq-historical-report-01-v163.png" alt-text="Снимок экрана: выбор области конвейера данных CQD.":::

1. Регион, в котором находится клиент, можно получить с помощью командлета [Get-CsTenant](/powershell/module/skype/get-cstenant) .

    ```powershell
    (Get-CsTenant).ServiceInstance

    microsoftcommunicationsonline/noam-4a-s7
    ```

    1. Регион будет отображаться после **/** , как в приведенном выше примере, где регион — `noam`.

 1. Отчет будет запущен с примерами данных.
 
 1. Чтобы просмотреть собственные данные, выберите **Обновить** на вкладке **Главная** в разделе **Запросы** в Power BI Desktop.

   :::image type="content" source="media/aa-cq-historical-report-02-v163.png" alt-text="Снимок экрана: выбор параметра обновления.":::

1. Вам будет предложено войти. Выберите **Учетная запись организации**, а затем — **Войти**.

  :::image type="content" source="media/aa-cq-historical-report-03-v163.png" alt-text="Снимок экрана: вход для версии 1.63.":::

1. Выберите **Подключиться**, и данные обновятся.

## <a name="data-latency-for-aa-and-cq-analytics"></a>Задержка данных для аналитики AA и CQ

Данные обычно доступны в течение 30 минут после завершения вызова; однако бывают случаи, когда на появление данных может потребоваться несколько часов.

Вам потребуется обновить данные, чтобы увидеть новые данные.

## <a name="customization"></a>Настройки

Вы можете настроить определенные аспекты визуализации отчетов, такие как добавление или удаление полей для отображения в различных визуализациях, изменение типа диаграммы и т. д.

Отчет содержит все доступные метрики данных.

### <a name="change-color-schema"></a>Изменение цветовой схемы

При выполнении следующих действий предполагается, что вы уже выполнили установку.

Выполните следующие действия.

1. Выберите **вкладку Вид** на ленте.

  :::image type="content" source="media/aa-cq-historical-report-04.png" alt-text="Снимок экрана: выбор вкладки представления для изменения цветовой схемы.":::

2. Выберите цветовую схему в раскрывающемся списке.

  :::image type="content" source="media/aa-cq-historical-report-05.png" alt-text="Снимок экрана: различные цветовые схемы.":::
  
## <a name="auto-attendant-and-call-queue-historical-reports-definitions"></a>Определения журналов отчетов автосекретаря и очереди вызовов

### <a name="cloud-auto-attendant-analytics-report"></a>Отчет аналитики облачного автосекретаря

#### <a name="report-description"></a>Описание отчета

|Раздел отчета                          |Описание                                                       |
|:---------------------------------------|:-----------------------------------------------------------------|
|Источник входящих звонков<sup>1</sup>        |Распределение вызовов по внутреннему или внешнему источнику вызовов            |
|Метод поиска в каталоге                 |Распределение вызовов по типу поиска                              |
|Количество действий вызывающего объекта                     |Распределение вызовов по числу действий, используемых во время вызова       |
|Среднее значение секунд в AA                   |Среднее количество секунд, в течение которых абоненты проводят в AA                 |
|Средние действия вызывающего абонента                  |Среднее число действий, выполняемых вызывающими в AA               |
|Результаты вызова                            |Распределение вызовов по состоянию конечного вызова                         |
|Нижний раздел отчета                 |Разбивка потока вызовов                                               |



#### <a name="report-to-cqd-table-and-field-mapping"></a>Сопоставление таблиц и полей CQD

|Вкладка "Отчет"            |Имя таблицы отчета     |Имя исходной таблицы            |Глобальный фильтр                          |
|:---------------------|:---------------------|:----------------------------|:--------------------------------------|
|Автосекретаря        |fAutoAttendant        |AutoAttendant                |Нет                                   |

|Раздел отчета                                  |Используемые поля                              |Примененные фильтры     |
|:-----------------------------------------------|:------------------------------------------|:-------------------|
|Селектор даты                                   |AAStartTime                                |Нет                |
|Селектор диапазона времени                             |AAStartHour                                |Нет                |
|Автосекретаря                                  |Имя AA                                    |Нет                |
|Источник входящих звонков<sup>1</sup>                |Тип вызова<br>Сумма totalCallCount (Measure) |Внешние вызовы: тип вызова — external<br>Внутренние вызовы: тип вызова — internal |
|Метод поиска в каталоге                         |AADirectorySearchMethod<br>TotalCallCount  |AADirectorySearchMethod является abs_search_dtmf или abs_search_name    |
|Количество действий вызывающего объекта                             |AACallerActionCount<br>TotalCallCount      |Нет                                                             |
|Среднее значение секунд в AA                           |AAChainDuration (Measure)                  |Нет                                                             |
|Средние действия вызывающего абонента                          |AACallerActionCount (Measure)              |Нет                                                             |
|Результаты вызова                                    |AACallResult<br>AACallResultLegend<br>TotalCallCount             |Нет                                       |
|Нижний раздел отчета                         |Имя AA<br>AACallFlow<br>AACallResult<br>AAChainDuration<br>Тип вызова<br>ММ-ДД<br>TotalCallCount |Нет       |

#### <a name="fautoattendant-cqd-fields-description"></a>Описание полей CQD fAutoAttendant

|Имя                                    |Тип данных                |Описание                            |
|:---------------------------------------|:------------------------|:--------------------------------------|
|Имя AA                                 |Текст                     |Имя учетной записи ресурса, присоединенной к автосекретарю<br><br>Если полное имя учетной записи ресурса **aa_test@microsoft.com**, то это значение будет следующим: **aa_test** |
|AACallerActionCount                     |Целое число             |Суммирование: Сумма<br>Количество действий, выбранных вызывающим в автосекретаре во время вызова  |
|AACallerActionCount (Measure)          |Целое число             |То же самое, что и выше, за исключением того, что будет равно 0, если нет вызовов вместо пустых                              |
|AACallFlow                              |Текст                     |Инкапсулирует различные состояния возможных значений вызова автосекретаря:<br><br>§ abs_search<br>§ объявление<br>§ automatic_menu<br>§ call_termination<br>§ call_transfer<br>§ first_level_menu<br>§ main_menu<br>§ speech_input_confirmation<br>§ user_selection |
|AACallResult                            |Текст                     |Конечный результат вызова — возможные значения:<br><br>§ failed_to_establish_media (не удалось установить часть вызова мультимедиа)<br>§ failover_to_operator (вызов, передаваемый оператору, как правило, из-за системной ошибки)<br>§ oaa_chain_too_long (слишком много ног в AA)<br>§ oaa_session_too_long (сеанс AA длился слишком долго)<br>§ service_declined (AA не принял вызов)<br>§ service_terminated (конфигурация AA отключает вызов или завис вызов)<br>§ terminated_automatic_selection (конфигурация AA отключает вызовы)<br>§ terminated_no_operator (вызов завершается из-за ошибки, оператор не определен) <br>§ terminated_transfer_failed (вызов прерван из-за сбоя передачи , как правило, на внешний номер)<br>§ transfer_in_progress (передача AA->AA)<br>§ transferred_to_operator (вызов был передан оператору , как правило, из-за ошибки пользователя)<br>§ transferred_to_receptionist (то же, что и transferred_to_operator)<br>§ transferred_to_self (вызов был возвращен в начало AA — обычно из пункта извещения меню)<br>§ transferred_to_shared_voicemail (звонок был передан на общую голосовую почту)<br>§ transferred_to_user (звонок был передан пользователю — включает очереди звонков)<br>§ unknown (произошло неизвестное условие)<br>§ user_terminated (вызывающий повесил трубку) |
|Условные обозначения вызова AA                          |Текст                     |Настройка элементов условных обозначений на основе AACallResult                               |
|AAChainDuration                         |Десятичное число           |Суммирование: Сумма<br>Длительность вызова в автосекретаре                     |
|AAChainDuration (Measure)               |Десятичное число           |То же самое, что и выше, за исключением того, что будет равно 0, если нет вызовов вместо пустых              |
|AAChainIndex                            |Текст                     |                                                                         |
|AAConnectivityType                      |Текст                     |Тип значений, возможных для вызова:<br><br>§ ExternalCall<br>§ InternalCall |
|AACount                                 |Текст                     |Количество автосекретарей, участвующих в вызове                               |
|AADirectorySearchMethod                 |Текст                     |Метод поиска последней адресной книги — возможные значения:<br><br>§ abs_search_dtmf<br>§ abs_search_extension_x<br>§ abs_search_name |
|AAStartHour                             |Десятичное число           |Час начала вызова автосекретаря                                           |
|AAStartTime                             |Дата и время                |Время начала вызова автосекретаря                                           |
|AATransferAction                        |Текст                     |Возможные значения типа целевого объекта передачи:<br><br>§ application — сущность голосового приложения<br>§ external_pstn<br>§ hunt_group — сущность очереди вызовов<br>§ orgaa — сущность автосекретаря<br>§ shared_voicemail<br>§ unknown<br>§ пользователь |
|Тип вызова<sup>1</sup>                   |Текст                     |Тип значений, возможных для вызова:<br><br>§ Внешний<br>§ Внутренний           |
|IsAAInvolved                            |Текст                     |Всегда 1                                                                 |
|ММ-ДД                                   |Текст                     |Вызов автосекретаря месяц-день                                            |
|PSTNMinutes                             |Целое число             |Суммирование: Сумма<br>Общее использование минут                                     |
|TotalCallCount                          |Целое число             |Суммирование: Сумма<br>Всегда 1 — используется для предоставления суммы всех вызовов            |
|Сумма totalCallCount (Measure)         |Целое число             |То же самое, что и выше, за исключением того, что будет равно 0, если нет вызовов вместо пустых              |


### <a name="cloud-call-queue-analytics-report"></a>Отчет аналитики очереди вызовов в облаке

#### <a name="report-description"></a>Описание отчета

|Раздел отчета                          |Описание                                                        |
|:---------------------------------------|:------------------------------------------------------------------|
|Источник входящих звонков<sup>1</sup>        |Распределение вызовов по внутреннему или внешнему источнику вызовов             |
|Среднее время ожидания (в секундах)             |Время ожидания ответов и отмененных вызовов                          |
|Количество звонков и количество согласия агента      |Распределение вызовов по очередям вызовов / Максимальное число согласия агента  |
|Результаты вызова                            |Распределение вызовов по результату вызова                               |
|Отмененные вызовы                         |Распределение отмененных вызовов по очередям вызовов                     |
|Средняя продолжительность сеанса (в секундах)        |Длительность вызова в секундах сгруппирована по результату вызова                      |
|Назначения переполнения и времени ожидания вызовов      |Распределение вызовов, которые истекли или переполнены                 |


#### <a name="report-to-cqd-table-and-field-mapping"></a>Сопоставление таблиц и полей CQD

|Вкладка "Отчет"            |Имя таблицы отчета                                   |Имя исходной таблицы                               |Глобальный фильтр       |
|:---------------------|:---------------------------------------------------|:-----------------------------------------------|:-------------------|
|Очередь вызовов            |fCallQueueAnalytics<br>fCallQueueFinalStateAction   |CallQueueAnalytics<br>CallQueueFinalStateAction |Нет                |

|Раздел отчета                      |Используемые поля таблицы >                |Примененные фильтры       |
|:-----------------------------------|:-------------------------------------|:---------------------|
|Селектор даты                       |fCallQueueAnalytics -> дата           |Нет                  |
|Селектор диапазона времени                 |fCallQueueAnalytics -> CQHour         |Нет                  |
|Учетная запись ресурса очереди вызовов         |fCallQueueAnalytics -> имя CQ        |Нет                  |
|Источник входящего звонка<sup>1</sup>    |fCallQueueAnalytics -> сумма количества вызовов (мера)<br>fCallQueueAnalytics -> тип вызова    |Внешние вызовы: тип вызова — external<br>Внутренние вызовы: тип вызова — internal |
|Среднее время ожидания (в секундах) — до ответа |fCallQueueFinalStateAction -> среднее среднее значение средней длительности CQ (measure) |Результат вызова очереди звонков agent_joined_conference или transferred_to_agent|
|Среднее время ожидания (в секундах) — до отмены |fCallQueueFinalStateAction -> среднее среднее время вызова (мера) |Результат вызова очереди вызовов не agent_joined_conference, transferred_to_agent, переполнен, timed_out |
|Число Opt-In вызовов и Opt-In агента   |fCallQueueAnalytics -> число вызовов<br>fCallQueueAnalytics -> число согласия агента очереди вызовов<br>fCallQueueAnalytics -> имя CQ<br>fCallQueueAnalytics -> дата |Нет |
|Отмененные вызовы                     |fCallQueueAnalytics -> дата<br>fCallQueueAnalytics -> TotalCallCount | Условные обозначения результата вызова очереди вызовов отброшены |
|Средняя продолжительность сеанса (в секундах)    |fCallQueueFinalStateAction -> средняя длительность очереди звонков (с)<br>Условные обозначения результата вызова очереди вызовов |Средняя длительность очереди звонков (с) > 0 |
|Назначения переполнения и времени ожидания вызовов  |fCallQueueAnalytics -> число вызовов<br>Тип целевого объекта очереди вызовов fCallQueueAnalytics -><br>Условные обозначения целевого типа fCallQueue |Условные обозначения целевого типа очереди вызовов не содержат отказов и ответ агента |


#### <a name="fcallqueueanalytics-cqd-fields-description"></a>Описание полей CQD fCallQueueAnalytics

|Имя                                    |Тип данных                |Описание                                                                |
|:---------------------------------------|:------------------------|:--------------------------------------------------------------------------|
|Число вызовов                              |Целое число             |Суммирование: Сумма<br>Число звонков                                          |
|Число агентов очереди вызовов                  |Целое число             |Суммирование: Сумма<br>Число агентов, настроенных в очереди вызовов            |
|Количество согласия агента очереди вызовов           |Целое число             |Суммирование: Сумма<br>Количество агентов, согласились на очередь вызовов              |
|Результат вызова очереди вызовов                  |Текст                     |Конечное состояние вызова очереди вызовов — возможные значения:<br><br>§ agent_joined_conference (ответы на звонки в режиме конференции)<br>§ отклонено<br>§ отключено<br>§ ошибка<br>сбой §<br>§ недопустимый<br>§ переполнение (выполнено условие переполнения)<br>§ timed_out (условие ожидания выполнено)<br>§ transferred_to_agent (вызовы в режиме передачи ответов {default}) |
|Условные обозначения результата вызова очереди вызовов           |Текст                     |Настройка элементов условных обозначений на основе результата очереди вызовов                             |
|Тип целевого объекта очереди вызовов                  |Текст                     |***Возможные значения целевого типа перенаправления:***<br><br>§ ApplicationEndpoint<br>§ Почтовый ящик<br>§ Прочее<br>§ Пользователь |
|Условные обозначения типа целевого объекта очереди вызовов           |Текст                     |Настройка элементов условных обозначений на основе типа целевого объекта очереди вызовов                        |
|Тип вызова<sup>1</sup>                   |Текст                     |Тип значений, возможных для вызова:<br><br>§ Внешний<br>§ Внутренний             |
|Имя CQ                                 |Текст                     |Имя учетной записи ресурса, присоединенной к очереди вызовов<br><br>Если полное имя учетной записи ресурса **cq_test@microsoft.com**, то это значение будет следующим: **cq_test** |
|Час CQ                                 |Целое число             |Час начала вызова очереди звонков                                                 |
|Дата                                    |Дата и время                |Дата и время начала вызова очереди вызовов (час)                                 | 
|DateTimeCQName                          |Текст                     |Уникальный ключ для фильтрации в fCallQueueFinalStateAction                     |
|Тип подключения ТСОП                  |Текст                     |Тип значений, возможных для вызова:<br><br>§ ExternalCall<br>§ InternalCall     |
|Общее количество минут ТСОП                      |Целое число             |Суммирование: Сумма<br>Общее использование минут для вызовов ТСОП                       |
|Сумма количества вызовов (мера)             |Целое число             |То же самое, что и число вызовов, однако будет равно 0, если вызов отсутствует                          |
|TotalCallCount (Measure)                |Целое число             |Суммирование: Сумма<br>Число вызовов                                                |


#### <a name="fcallqueuefinalstateaction-cqd-fields-description"></a>Описание полей CQD fCallQueueFinalStateAction

|Имя                                    |Тип данных                |Описание                                        |
|:---------------------------------------|:------------------------|:--------------------------------------------------|
|Средняя длительность вызова (в секундах)         |Десятичное число           |Суммирование: Сумма<br>Средняя длительность вызова в секундах для отмененных вызовов    |
|Средняя длительность очереди звонков (с)       |Десятичное число           |Суммирование: Сумма<br>Среднее ожидание в секундах для ответов на звонки           |
|Среднее значение средней продолжительности звонка (мера)  |Целое число             |То же самое, что и средняя длительность звонка (в секундах), однако будет равно 0, если вызовы отсутствуют   |
|Среднее значение средней продолжительности CQ (мера)    |Целое число             |То же самое, что и средняя длительность очереди звонков (с), однако будет равно 0, если вызовы отсутствуют. |
|Число вызовов                              |Целое число             |Суммирование: Сумма<br>Число звонков                                         |
|Результат вызова очереди вызовов                  |Текст                     |Конечное состояние вызова очереди вызовов — возможные значения:<br><br>§ agent_joined_conference (ответы на звонки в режиме конференции)<br>§ отклонено<br>§ отключено<br>§ ошибка<br>сбой §<br>§ недопустимый<br>§ переполнение (выполнено условие переполнения)<br>§ timed_out (условие ожидания выполнено)<br>§ transferred_to_agent (вызовы режима передачи с ответами {default} |
|Условные обозначения результата вызова очереди вызовов           |Текст                     |Настройка элементов условных обозначений на основе результата вызова очереди вызовов                      |
|Действие конечного состояния очереди вызовов           |Текст                     |Вызов конечного действия очереди — возможные значения:<br><br>§ отключение (timed_out вызовы)<br>§ disconnect_with_busy (переполненные вызовы)<br>§ failed_to_accept_call<br>§ переадресация<br>§ shared_voicemail<br>§ другое<br>§ голосовая почта                |
|Имя CQ                                 |Текст                     |Имя учетной записи ресурса, присоединенной к очереди вызовов<br><br>Если полное имя учетной записи ресурса **cq_test@microsoft.com**, то это значение будет следующим: **cq_test** |
|Дата                                    |Дата и время                |Дата и время начала вызова очереди вызовов (час)                                 |
|DateTimeCQName                          |Текст                     |Уникальный ключ для фильтрации в fCallQueueFinalStateAction                     |
|IsAbandoned                             |Значение true/false               |Значение true, если агент не ответил на вызов                                   |


### <a name="cloud-call-queue-agent-timeline-report"></a>Отчет о временной шкале агента очереди вызовов в облаке

#### <a name="report-description"></a>Описание отчета

|Раздел отчета                                          |Описание                                                  |
|:-------------------------------------------------------|:------------------------------------------------------------|
|Количество вызовов по агенту                                |Распределение вызовов по очереди вызовов и агенту                |
|Распределение по агенту и всем очередям                     |Распределение вызовов по агенту и очереди вызовов                |
|Таблица (справа внизу)                                    |Распределение вызовов по агенту со средней и общей длительностью вызова |
|Средняя длительность вызова (в секундах) по агенту                |Средняя длительность (в секундах) вызова по агенту                  |

#### <a name="report-to-cqd-table-and-field-mapping"></a>Сопоставление таблиц и полей CQD

|Вкладка "Отчет"            |Имя таблицы отчета           |Имя исходной таблицы         |Глобальный фильтр       |
|:---------------------|:---------------------------|:-------------------------|:-------------------|
|Временная шкала агента        |fAgentTimelineAnalytics     |fAgentTimelineAnalytics   |Нет                |


|Раздел отчета                                |Используемые поля                         |Примененные фильтры       |
|:---------------------------------------------|:-------------------------------------|:---------------------|
|Селектор даты                                 |Datetime                              |Нет                  |
|Селектор имени агента                       |Имя агента                            |Нет                  |
|Селектор учетных записей ресурсов очереди вызовов          |Имя CQ                               |Нет                  |
|Количество вызовов по агенту                      |Имя агента<br>Число вызовов<br>Hour      |Нет                  |
|Распределение по агенту и очереди вызовов          |Имя агента<br>Средняя длительность вызовов (в секундах)<br>Число вызовов<br>Имя CQ |Нет                      |
|Нижний левый                                   |Имя агента<br>Средняя длительность вызова (в секундах)<br>Число вызовов<br>Длительность звонка (минута)<br>Имя CQ<br>Hour<br>ММ-ДД | Нет |
|Средняя длительность вызова (в секундах) по агенту      |Имя агента<br>Средняя длительность вызова (в секундах) | Нет |

#### <a name="fagenttimelineanalytics-cqd-fields-description"></a>Описание полей CQD fAgentTimelineAnalytics

|Имя                                    |Тип данных                |Описание                                         |
|:---------------------------------------|:------------------------|:---------------------------------------------------|
|Имя агента                              |Текст                     |Имя участника-пользователя<br>Если полное имя пользователя — **user@microsoft.com**, это значение будет: **user** |
|Средняя длительность вызова (в секундах)         |Десятичное число           |Суммирование: Сумма<br>Средняя продолжительность вызовов очереди ответов в секундах |
|Число вызовов                              |Целое число             |Суммирование: Сумма<br>Количество вызовов, на которые ответил агент     |
|Длительность звонка (в минутах)                 |Целое число             |Суммирование: Сумма<br>Общая продолжительность звонков в очереди вызовов с ответами в минутах (округляется до ближайшей минуты)  |
|Имя CQ                                 |Текст                     |Имя учетной записи ресурса, присоединенной к очереди вызовов<br><br>Если полное имя учетной записи ресурса **cq_test@microsoft.com**, то это значение будет следующим: **cq_test** |
|Дата                                    |Дата                     |Дата звонка                                             |
|Datetime                                |Datetime                 |Дата звонка                                             |
|Hour                                    |Целое число             |Час звонка                                             |
|ММ-ДД                                   |Текст                     |Месяц и день звонка                                    |


> [!NOTE]
> При поступлении звонка в первую очередь звонков, если количество вызовов, уже ожидающих в этой очереди, достигло предела **обработки переполнения вызовов** и если параметр перенаправления отправляет новые вызовы во вторую очередь звонков, агенты во второй очереди вызовов будут отображаться как в первой очереди вызовов в этом отчете. 

## <a name="known-issues"></a>Известные проблемы

- Очередь вызовов и автосекретари отображаются по идентификатору учетной записи ресурса вместо имен очереди вызовов или автосекретаря.  Чтобы отобразить весь трафик для автосекретаря или очереди вызовов, необходимо выбрать все учетные записи ресурсов, назначенные автосекретарю или очереди вызовов.

- На панели мониторинга доступно только 28 дней журнала, так как данные очереди вызовов или автосекретаря считаются персональными данными и регулируются политиками конфиденциальности данных.

- В некоторых сценариях количество ответных вызовов агента на **временной шкале агента очереди облачных вызовов** может отличаться от количества вызовов, указанного в журнале вызовов клиента Teams. Журнал вызовов клиента Teams является правильным. Поддержка изучается, но в настоящее время не существует предполагаемого времени на восстановление.

- <sup>1</sup> **Источник входящих вызовов** в автосекретаре и графах очереди вызовов отображается последний источник этапа вызова, а не исходный источник этапа вызова. Например, если автосекретарь получает внешний вызов и передает его другому автосекретарю или очереди вызовов, **источник входящих звонков** будет сообщаться как внутренний.

## <a name="version-1xx-history"></a>Журнал версии 1.xx

Подробный список изменений см. в статье Автосекретарь CQD Teams & отчеты об изменении Log.docx в скачанном ZIP-файле                         

|Версия  |Дата публикации     |Имени файла                                                           |Описание                                         |
|:--------|:------------------|:------------------------------------------------------------------|:---------------------------------------------------
|1.63     |24 августа 2022 г.    |Автосекретарь CQD Teams & отчет об истории очереди вызовов v1.63.pbit |                                                    |
|1.60     |22 июля 2022 г.      |Автосекретарь CQD Teams & отчет об истории очереди вызовов версии 1.60.pbit |                                                    |
|1.00     |5 ноября 2020 г.   |Объединенная аналитика CQ и AA 20201105.pbit                         |Первоначальный выпуск                                     |
