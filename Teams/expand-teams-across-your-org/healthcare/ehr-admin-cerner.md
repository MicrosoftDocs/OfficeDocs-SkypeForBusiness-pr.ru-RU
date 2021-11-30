---
title: Виртуальные посещения с Teams интеграция с EHR Cerner
author: LanaChin
ms.author: v-lanachin
manager: samanro
audience: ITPro
ms.topic: conceptual
ms.service: msteams
search.appverid: MET150
searchScope:
- Microsoft Teams
- Microsoft Cloud for Healthcare
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Healthcare
- microsoftcloud-healthcare
- m365solution-healthcare
- m365solution-scenario
appliesto:
- Microsoft Teams
ms.reviewer: ansantam
description: Узнайте, как интегрировать Teams EHR, чтобы поставщики услуг здравоохранения в организации могли проводить виртуальные визиты с пациентами или другими поставщиками услуг в Teams непосредственно из системы EHR Cerner.
ms.openlocfilehash: 7329bd0afacfe941746374cc836203f17a9b5e57
ms.sourcegitcommit: 4df3d144296b9b8982109be7edaffd636aabdf29
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/15/2021
ms.locfileid: "60960145"
---
# <a name="virtual-visits-with-teams---integration-into-cerner-ehr"></a>Виртуальные посещения с Teams интеграция с EHR Cerner

Соединит Microsoft Teams электронной медицинских записей (EHR) позволяет стоматологам легко начать виртуальный визит к пациенту или обратиться к другому поставщику в Microsoft Teams непосредственно из системы EHR Cerner. На основе облака Microsoft 365, Teams обеспечивает простую и безопасную совместную работу и общение с чатом, видео, голосовой связью и средствами здравоохранения в едином центре, который поддерживает соответствие требованиям с сертификатами HIPAA, HITECH и другими решениями.

Платформа для общения и совместной работы Teams упрощает работу с диспансерами, чтобы они могли сосредоточиться на максимальной помощи. С помощью Teams EHR вы можете:

- Проводите Teams виртуальных посещений из системы EHR Cerner с интегрированным медицинским процессом.
- Позволяет пациенту присоединяться к виртуальным Teams из сообщений электронной почты или SMS-уведомлений.
- Просмотр отчетов о расходных данных и настраиваемых сведений о качестве звонка для подключенных к EHR посещений.

В этой статье описано, как настроить соединители Teams EHR для интеграции с платформой Cerner. Здесь также представлен обзор Teams посещений в системе EHR Cerner.

## <a name="before-you-begin"></a>Подготовка к работе

> [!NOTE]
> Перед включением интеграции обязательно поговорите со своим представителем Cerner и просмотрите руководство по интеграции Cerner.

### <a name="prerequisites"></a>Необходимые компоненты

Перед интеграцией Teams EHR в организации здравоохранения необходимо:

- Активная подписка на Microsoft Teams автономных предложений для соединителя EHR (только при тестировании в среде EHR в производственной среде).
- Соответствующая Microsoft 365 или Office 365, которая включает Teams собрания.
- Teams применяется в вашей организации здравоохранения.
- Ваши системы отвечают всем [требованиям к программному](../../hardware-requirements-for-the-teams-app.md) обеспечению и браузеру для Teams.
- Cerner version november 2018 or later

## <a name="set-up-the-teams-ehr-connector"></a>Настройка соединитела Teams EHR

Для настройки соединители необходимо:

- [Запуск портала конфигурации соединителя EHR](#launch-the-ehr-connector-configuration-portal)
- [Введите сведения о конфигурации](#enter-configuration-information)
- [Включить SMS-уведомления (необязательно)](#enable-sms-notifications-optional)
- [Просмотр и завершение конфигурации](ehr-admin-cerner.md#review-and-finish-the-configuration)

> [!IMPORTANT]
> Эти действия должен сделать глобальный Microsoft 365 администратор в вашей организации.  

### <a name="launch-the-ehr-connector-configuration-portal"></a>Запуск портала конфигурации соединителя EHR

Для начала администратор Microsoft 365 запускает портал конфигурации [соединителя EHR](https://ehrconnector.teams.microsoft.com) и войдет с учетными данными Майкрософт.

Администратор Microsoft 365 может настроить один или несколько отделов для проверки интеграции. Настройте тестовый и рабочий URL-адреса на портале конфигурации. Перед переходом на production проверьте интеграцию с тестовой средой Cerner.

### <a name="enter-configuration-information"></a>Введите сведения о конфигурации

Затем, чтобы настроить интеграцию, администратор Microsoft 365 добавляет базовый URL-адрес службы FHIR от Cerner и определяет среду. При необходимости настройте количество базовых URL-адресов FHIR в зависимости от потребностей организации и среды, которые вы хотите протестировать.

:::image type="content" source="media/ehr-admin-cerner-configuration.png" alt-text="Снимок экрана: страница сведений о конфигурации портала Teams EHR." lightbox="media/ehr-admin-cerner-configuration.png":::

- Базовый URL-адрес FHIR — это статический адрес, соответствующий конечной точке API API сервера FHIR. Пример URL-адреса — `https://lamnahealthcare.org/fihr/auth/connect-ocurprd-oauth/api/FHDST`.

- Вы можете настроить интеграцию для тестовой и производственной среды. Для начальной настройки рекомендуется настроить соединитегорию из тестовой среды перед переходом в среду.

После проверки базового URL-адреса FHIR и выбора среды выберите **Готово**. Затем при необходимости добавьте дополнительные базовые URL-адреса FHIR для других сред.

Чтобы **перейти** к следующему шагу, выберите далее.

### <a name="enable-sms-notifications-optional"></a>Включить SMS-уведомления (необязательно)

Выполните это шаг, если ваша организация требует от корпорации Майкрософт управлять SMS-уведомлениями для пациентов. Если включить SMS-уведомления, пациенты получат подтверждение и напоминания о запланированном виртуальном посещении.

Чтобы включить SMS-уведомления, Microsoft 365 администратор делает следующее:

1. На странице SMS-уведомлений выберите оба почтовых ящика согласия, чтобы:

    - Разрешить Корпорации Майкрософт отправлять SMS-уведомления пациенту от имени вашей организации.
    - Подтвердить, что участники согласились отправлять и получать SMS-сообщения.

    :::image type="content" source="media/ehr-admin-cerner-sms-notifications.png" alt-text="Снимок экрана: страница sms-уведомлений с флажками согласия и параметром создания номера телефона." lightbox="media/ehr-admin-cerner-sms-notifications.png":::

1. В **области Ваши номера телефонов** выберите Создать новый номер **телефона,** чтобы создать номер телефона для вашей организации. При этом начнется процесс запроса и создания нового номера телефона. Этот процесс может занять до 2 минут.

    После того как номер телефона будет создан, он будет отображаться на экране. Этот номер будет использоваться для отправки SMS-подтверждений и напоминаний вашим пациентам. Номер уже готов, но еще не связан с базовым URL-адресом FHIR. Это можно сделать на следующем шаге.

    :::image type="content" source="media/ehr-admin-cerner-phone-number.png" alt-text="Снимок экрана: пример сгенерированного номера телефона." lightbox="media/ehr-admin-cerner-phone-number.png":::

    Выберите **Готово**, а затем **далее**.

1. Чтобы связать номер телефона с базовым URL-адресом FHIR, **Телефон в** разделе Конфигурация **SMS** выберите номер. Сделайте это для каждого базового URL-адреса FHIR, для которого вы хотите включить SMS-уведомления.

    :::image type="content" source="media/ehr-admin-cerner-link-phone-number.png" alt-text="Снимок экрана: связывать номер телефона с базовым URL-адресом FHIR." lightbox="media/ehr-admin-cerner-link-phone-number.png":::

    Если вы настраиваете соединитель впервые, вы увидите базовый URL-адрес FHIR, который был введен на более ранней этапе. Один и тот же номер телефона может быть связан с несколькими базовыми URL-адресами FHIR, то есть пациенты будут получать SMS-уведомления с одного и того же номера телефона для разных организаций и отделов.

     Нажмите **Далее**.

### <a name="review-and-finish-the-configuration"></a>Просмотр и завершение конфигурации

Вам будут представлены записи интеграции для запуска пациентов и поставщика услуг. Эти записи необходимы для завершения настройки виртуального посещения в Cerner. Дополнительные сведения см. в Cerner-Microsoft Teams интеграции с телетайлами.

> [!NOTE]
> Администратор вашей учетной записи Microsoft 365 в любое время может войти на портал конфигурации, чтобы просмотреть записи интеграции и при необходимости изменить параметры конфигурации.

## <a name="launch-teams-virtual-visits"></a>Запуск виртуальных посещений Teams

После выполнения действий по подключению eHR и настройке Cerner ваша организация готова поддерживать видео посещения с помощью Teams.

### <a name="virtual-visits-prerequisites"></a>Предварительные условия виртуальных посещений

- Ваши системы должны соответствовать всем [требованиям к программному](../../hardware-requirements-for-the-teams-app.md) обеспечению и браузеру для Teams.
- Настройка интеграции между организацией Cerner и вашей организацией Microsoft 365 завершена.

### <a name="provider-experience"></a>Взаимодействие с поставщиком

Поставщики услуг здравоохранения в вашей организации могут присоединиться к виртуальным посещениям Teams с портала PowerChart. Поставщик должен перейти на доску пациентов, где Teams доступ.

После этого поставщик может просматривать сведения о виртуальном посещении, присоединяться к виртуальным посещениям и отправлять ссылки на собрания. После разового входе поставщик будет сразу перенаться на виртуальную встречу в Teams.

Основные функции взаимодействия с поставщиком:

- Поставщики могут присоединиться к виртуальным посещениям с помощью поддерживаемых браузеров или Teams приложения.
- Поставщики могут использовать все поддерживаемые функции Teams, включая общий доступ к экрану, пользовательский фон и запись.
- Поставщики могут видеть обновления в режиме реального времени для пациентов, подключающихся к виртуальному визиту на данную встречу в PowerChart.
- Во время виртуального посещения пациенты не могут получить информацию о поставщике услуг.

### <a name="patient-experience"></a>Взаимодействие с пациентом

Соединител поддерживает пациентов, которые присоединяются к виртуальным посещениям по ссылке в SMS-сообщении. Во время встречи пациенты могут начать виртуальное посещение, коснувшись ссылки в SMS-сообщении.

Основные функции пациентов

- Пациенты могут присоединиться к виртуальным посещениям из современных веб-браузеров на компьютере и мобильном устройстве, не устанавливая [приложение Teams.](../mobile-browser-join.md)
- Пациенты могут присоединиться к виртуальным посещениям одним щелчком мыши, и для этого не требуется другая учетная запись или вход.
- Для запуска виртуального посещения пациентам не требуется создавать учетную запись Майкрософт или выполнять вход.
- Пациенты помещаются в "большой", пока поставщик не присоединится к встрече и не допустит их в виртуальный визит.
- Перед присоединением к виртуальному посещению пациенты могут проверить видео и микрофон в "оке".

## <a name="privacy-and-location-of-data"></a>Конфиденциальность и расположение данных

Teams интеграция с системами EHR оптимизирует объем данных, которые используются и хранятся во время интеграции и потоков виртуального посещения. Решение соответствует общим принципам и рекомендациям по обеспечению конфиденциальности и управлению данными Teams, изложенным в разделе "Конфиденциальность Teams".

Соединит Teams EHR не хранит и не передает личные личные данные, а также медицинские записи пациентов и поставщиков услуг здравоохранения из системы EHR. Единственными данными, которые хранит соединитектор EHR, является уникальный ИД пользователя EHR, который используется во время Teams собраний.

Уникальный идентификатор пользователя электронной медицинской карты хранится в одном из трех географических регионов, описанных в статье [Где хранятся данные клиентов Microsoft 365](/microsoft-365/enterprise/o365-data-locations). Все чаты, записи и другие данные, Teams участниками собрания, хранятся в соответствии с существующими политиками хранения. Дополнительные сведения о расположении данных в Teams см. в [Teams.](../../location-of-data-in-teams.md)

## <a name="related-articles"></a>Статьи по теме

- [Teams отчеты администратора соединители eHR](ehr-admin-reports.md)
- [Начало работы с Teams для медицинских организаций](teams-in-hc.md)