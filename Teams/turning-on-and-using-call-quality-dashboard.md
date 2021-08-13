---
title: Настройка панели мониторинга качества вызовов (CQD)
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
description: Узнайте, как включить и использовать панель мониторинга качества вызовов и получать сводные отчеты о качестве вызовов.
ms.openlocfilehash: cf4c6d56e4fa646495383b4998e80789d9cdaca67b9cc35d07f613cda4e70b85
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2021
ms.locfileid: "54300455"
---
# <a name="how-to-set-up-call-quality-dashboard"></a>Настройка панели мониторинга качества вызовов

Откройте панель мониторинга качества вызовов Майкрософт (CQD) по [https://cqd.teams.microsoft.com](https://cqd.teams.microsoft.com) телефону (во входе с учетными данными администратора). Или перейдите в центр администрирования Teams и выберите **панель мониторинга качества вызовов.** 

:::image type="content" source="media/turning-on-and-using-call-quality-dashboard3.png" alt-text="Снимок экрана кнопки панели мониторинга качества вызовов в Teams центре администрирования":::

На открываемой странице нажмите **кнопку Вход** и введите свою учетную запись глобального администратора или Microsoft Teams учетной записи администратора. После первого входного дня CQD начнет сбор и обработку данных. Помните, что обработка достаточного количества данных для отображения значимых результатов в отчетах может занять один или несколько часов.

CQD показывает качество вызовов и собраний на уровне организации для Microsoft Teams, Skype для бизнеса Online и Skype для бизнеса Server 2019 г. 

> [!IMPORTANT]
> Чтобы использовать CQD с Skype для бизнеса Server 2019 г., необходимо настроить соединители данных [вызовов.](/skypeforbusiness/hybrid/configure-call-data-connector) Прежде [чем приступить к запуску, см.](/skypeforbusiness/hybrid/plan-call-data-connector) соединители данные по планированию вызовов.


## <a name="assign-admin-roles-for-access-to-cqd"></a>Назначение ролей администратора для доступа к CQD

Назначение [ролей](/microsoft-365/admin/add-users/about-admin-roles) для доступа к CQD людям, которым необходимо использовать его.

Если вы хотите, чтобы пользователи без администратора (например, инженеры службы поддержки и агенты helpdesk) использовали панель мониторинга качества вызовов, вы можете назначить этим пользователям одну из следующих ролей, которая предоставляет доступ к CQD. 


|&nbsp;  |Просмотр отчетов  |Просмотр полей EUII  |Создание отчетов  |Upload создания данных  |
|---------|:-------:|:-------:|:-------:|:-------:|
|Глобальный администратор     |Да         |Да         |Да         |Да         |
|Teams Администратор     |Да         |Да         |Да         |Да         |
|Администратор связи Teams     |Да         |Да         |Да         |Да         |
|Инженер службы поддержки связи Teams     |Да         |Да         |Да         |Нет         |
|Специалист службы поддержки связи Teams     |Да         |Нет         |Да         |Нет         |
|Администратор Skype для бизнеса     |Да         |Да         |Да         |Да         |
|Глобальный читатель |Да         |Да         |Да         |Нет         |
|Отчеты Reader<sup>1</sup>     |Да         |Нет         |Да         |Нет         |

<sup>1</sup> Помимо чтения отчетов по CQD, читатель отчетов может просматривать все отчеты об активности в центре администрирования и любые отчеты из пакета контента Microsoft 365 [принятия.](https://support.office.com/article/Office-365-Adoption-content-pack-77ff780d-ab19-4553-adea-09cb65ad0f1f) [](https://support.office.com/article/activity-reports-0d6dfb17-8582-4172-a9a9-aed798150263)

> [!NOTE]
> Если вы не видите EUII (идентифицируемую для конечного пользователя информацию) и у вас есть одна из ролей, которая разрешена для просмотра этой информации, имейте в виду, что CQD сохраняет [EUII](CQD-data-and-reports.md#euii-data) только в течение 28 дней. Удаляется все, что старше 28 дней.

Дополнительные сведения об этих ролях см. в [Office 365 роли администратора.](/office365/admin/add-users/about-admin-roles)


После первого входного дня CQD начнет сбор и обработку данных. По данным на декабрь 2019 г., вы можете получить доступ к старой версии CQD (cqd.lync.com), хотя на устаревшем портале вы можете получить ссылку на последний CQD (cqd.teams.microsoft.com). В конце концов, старая версия CQD будет списана. С 1 июля 2020 г. более старая версия CQD имеет доступ к данным из последнего CQD.


## <a name="migrate-building-data-and-reports-from-previous-version-of-cqd"></a>Перенос данных и отчетов по зданиям из предыдущей версии CQD

> [!IMPORTANT]
> С 1 июля 2020 г. вы больше не сможете перенести данные и отчеты из старого CQD ( https://CQD.lync.com) . 



## <a name="use-power-bi-to-analyze-cqd-data"></a>Использование Power BI для анализа данных ПМКЗ

Новое в январе 2020 г.: Power BI шаблоны запросов [для CQD](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true). Настраиваемые Power BI шаблоны, которые можно использовать для анализа и отчета о данных CQD.

Read [Use Power BI для анализа данных CQD,](CQD-Power-BI-query-templates.md) чтобы узнать больше.


## <a name="related-topics"></a>Похожие темы

[Улучшение и отслеживание качества вызовов для Teams](monitor-call-quality-qos.md)

[Что такое ПМКЗ?](CQD-what-is-call-quality-dashboard.md)

[Отправка клиента и создание данных](CQD-upload-tenant-building-data.md)

[Данные и отчеты ПМКЗ](CQD-data-and-reports.md)

[Использование ПМКЗ для управления качеством звонков и собраний](quality-of-experience-review-guide.md)

[Измерения и меры на ПМКЗ](dimensions-and-measures-available-in-call-quality-dashboard.md)

[Классификация потоков в ПМКЗ](stream-classification-in-call-quality-dashboard.md)

[Использование Power BI для анализа данных ПМКЗ](CQD-Power-BI-query-templates.md)
