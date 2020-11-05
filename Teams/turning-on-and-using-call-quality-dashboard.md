---
title: Настройка панели мониторинга качества звонков (CQD)
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.reviewer: mikedav, siunies, gageames
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
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Reporting
- ms.teamsadmincenter.directrouting.cqd
- ms.lync.lac.ToolsCallQualityDashboard
- seo-marvel-apr2020
description: Сведения о том, как включить и использовать панель мониторинга качества звонков и получить суммарные отчеты о качестве звонков.
ms.openlocfilehash: 9a864b0ad0f48e3a0bd8665b8dfeb917e67f4062
ms.sourcegitcommit: ee217e1d7188842c7becd19387fd421b485c3575
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/04/2020
ms.locfileid: "48918646"
---
# <a name="set-up-call-quality-dashboard-cqd"></a>Настройка панели мониторинга качества звонков (CQD)

Откройте панель мониторинга качества звонков (CQD) на странице [https://cqd.teams.microsoft.com](https://cqd.teams.microsoft.com) (войдите с учетными данными администратора). Или перейдите в центр администрирования Teams и выберите **панель мониторинга качества звонков**. 

:::image type="content" source="media/turning-on-and-using-call-quality-dashboard3.png" alt-text="Снимок экрана: кнопка панели мониторинга качества звонка в центре администрирования Teams":::

На открывшейся странице нажмите **Вход** и введите глобальную учетную запись администратора или сведения об учетной записи администратора Microsoft Teams Service. После первого входа CQD начнет сбор и обработку данных. Имейте в виду, что для обработки достаточного количества данных для отображения значимых результатов в отчетах может потребоваться одно или несколько часов.

CQD отображает качество звонков и собраний на уровне Организации, для Microsoft Teams, Skype для бизнеса Online и Skype для бизнеса Server 2019. 

> [!IMPORTANT]
> Для использования CQD в Skype для бизнеса Server 2019 необходимо [настроить соединитель данных звонка](https://docs.microsoft.com/skypeforbusiness/hybrid/configure-call-data-connector). Прежде чем приступить к работе, ознакомьтесь с [соединителем для связи с данными](https://docs.microsoft.com/skypeforbusiness/hybrid/plan-call-data-connector) .


## <a name="assign-admin-roles-for-access-to-cqd"></a>Назначение ролей администратора для доступа к CQD

Назначение [ролей](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles) для доступа к CQD людям, которым нужно пользоваться.

Если вы хотите, чтобы пользователи, не являющиеся администраторами (например, инженерами службы поддержки и агентами справочных служб) могли использовать панель мониторинга качества звонков, вы можете назначить этих пользователей одну из следующих ролей, которая предоставляет доступ к CQD. 


|  |Просмотр отчетов  |Просмотр полей EUII  |Создание отчетов  |Отправка данных о сборке  |
|---------|:-------:|:-------:|:-------:|:-------:|
|Глобальный администратор Office 365     |Да         |Да         |Да         |Да         |
|Администратор служб Teams     |Да         |Да         |Да         |Да         |
|Администратор коммуникаций Teams     |Да         |Да         |Да         |Да         |
|Инженер поддержки по коммуникациям Teams     |Да         |Да         |Да         |Нет         |
|Специалист по поддержке взаимодействия в Teams     |Да         |Нет         |Да         |Нет         |
|Администратор Skype для бизнеса     |Да         |Да         |Да         |Да         |
|Глобальный читатель Azure AD |Да         |Да         |Да         |Нет         |
|Office 365 сообщает читателям<sup>1</sup>     |Да         |Нет         |Да         |Нет         |

<sup>1</sup> в дополнение к ЧТЕНию CQDных отчетов Office 365 может просматривать все [отчеты об активности](https://support.office.com/article/activity-reports-0d6dfb17-8582-4172-a9a9-aed798150263) в центре администрирования и любые отчеты из пакета содержимого для оценки [внедрения Microsoft 365](https://support.office.com/article/Office-365-Adoption-content-pack-77ff780d-ab19-4553-adea-09cb65ad0f1f).

> [!NOTE]
> Если вы не видите [EUII (сведения для конечных пользователей)](CQD-data-and-reports.md#euii-data) и у вас есть одна из ролей, которые могут просматривать эти данные, имейте в виду, что CQD только в течение 28 дней. Все, более 28 дней, удаляются.

Дополнительные сведения об этих ролях можно найти в разделе [о ролях администратора Office 365](/office365/admin/add-users/about-admin-roles).


После первого входа CQD начнет сбор и обработку данных. По истечении декабря 2019 вы по-прежнему можете получать доступ к более ранней версии CQD (cqd.lync.com), несмотря на то, что на портале Legacy есть ссылка на последнюю версию CQD (cqd.teams.microsoft.com). В конечном итоге старая версия CQD будет списана. По истечении 1 июля 2020 в более ранней версии CQD доступ к данным из последнего CQD.


## <a name="migrate-building-data-and-reports-from-previous-version-of-cqd"></a>Миграция данных и отчетов из предыдущей версии CQD

> [!IMPORTANT]
> Начиная с 1 июля 2020 г., вы больше не сможете переносить данные построения и отчеты из старой CQD ( https://CQD.lync.com) . 



## <a name="use-power-bi-to-analyze-cqd-data"></a>Анализ данных CQD с помощью Power BI

Новые возможности в январе 2020: [Скачайте шаблоны запросов Power BI для CQD](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true). Настраиваемые шаблоны Power BI, которые можно использовать для анализа и составления отчетов о CQD данных.

Чтение с [помощью Power BI для анализа данных CQD](CQD-Power-BI-query-templates.md) для получения дополнительных сведений.


## <a name="related-topics"></a>Статьи по теме

[Улучшение и мониторинг качества связи для Teams](monitor-call-quality-qos.md)

[Что такое CQD?](CQD-what-is-call-quality-dashboard.md)

[Отправка клиента и создание данных](CQD-upload-tenant-building-data.md)

[Данные CQD и отчеты](CQD-data-and-reports.md)

[Использование CQD для управления качеством звонков и собраний](quality-of-experience-review-guide.md)

[Измерения и меры, доступные в CQD](dimensions-and-measures-available-in-call-quality-dashboard.md)

[Классификация потоков в CQD](stream-classification-in-call-quality-dashboard.md)

[Анализ данных CQD с помощью Power BI](CQD-Power-BI-query-templates.md)
