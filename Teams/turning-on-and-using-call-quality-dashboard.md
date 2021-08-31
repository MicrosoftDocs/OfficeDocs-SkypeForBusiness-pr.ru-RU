---
title: Настройка панели мониторинга качества звонка (CQD)
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
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Reporting
- ms.teamsadmincenter.directrouting.cqd
- ms.lync.lac.ToolsCallQualityDashboard
- seo-marvel-apr2020
description: Узнайте, как включить и использовать панель мониторинга качества звонков и получить сводные отчеты о качестве звонков.
ms.openlocfilehash: 292fa240b9298bd60715d812ec95d8e53403c489
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/30/2021
ms.locfileid: "58750059"
---
# <a name="how-to-set-up-call-quality-dashboard"></a>Настройка панели мониторинга качества звонка

Откройте панель мониторинга качества звонка (CQD) Майкрософт по ссылке [https://cqd.teams.microsoft.com](https://cqd.teams.microsoft.com) (войди с учетными данными администратора). Или перейдите в Центр администрирования Teams и выберите Панель мониторинга **качества звонка**. 

:::image type="content" source="media/turning-on-and-using-call-quality-dashboard3.png" alt-text="Снимок экрана: кнопка панели мониторинга качества Teams центре администрирования.":::

На открываемой странице нажмите кнопку **Войти** и введите учетную запись глобального администратора или Microsoft Teams учетную запись администратора. После первого входе CQD начнет сбор и обработку данных. Имейте в виду, что обработка достаточного количества данных для отображения осмысленной информации в отчетах может занять несколько часов.

В CQD показаны качество звонка и собрания на уровне организации для Microsoft Teams, Skype для бизнеса Online и Skype для бизнеса Server 2019. 

> [!IMPORTANT]
> Чтобы использовать CQD Skype для бизнеса Server 2019, необходимо настроить соединители данных [звонка.](/skypeforbusiness/hybrid/configure-call-data-connector) Перед [началом работы см. планирование соединитела](/skypeforbusiness/hybrid/plan-call-data-connector) данных зова.


## <a name="assign-admin-roles-for-access-to-cqd"></a>Назначение ролей администратора для доступа к CQD

[Назначать](/microsoft-365/admin/add-users/about-admin-roles) роли для доступа к CQD людям, которые должны его использовать.

Если вы хотите, чтобы пользователи без администрирования (например, инженеры службы поддержки и агенты службы технической поддержки) использовали панель мониторинга качества звонка, вы можете назначить им одну из следующих ролей, которая обеспечивает доступ к CQD. 


|&nbsp;  |Просмотр отчетов  |Просмотр полей EUII  |Создание отчетов  |Upload данных о здании  |
|---------|:-------:|:-------:|:-------:|:-------:|
|Глобальный администратор     |Да         |Да         |Да         |Да         |
|Администратор Teams     |Да         |Да         |Да         |Да         |
|Администратор коммуникаций Teams     |Да         |Да         |Да         |Да         |
|Инженер поддержки по коммуникациям Teams     |Да         |Да         |Да         |Нет         |
|Teams Специалист службы поддержки связи     |Да         |Нет         |Да         |Нет         |
|Skype для бизнеса Администратора     |Да         |Да         |Да         |Да         |
|Global Reader |Да         |Да         |Да         |Нет         |
|Reports Reader<sup>1</sup>     |Да         |Нет         |Да         |Нет         |

<sup>1</sup> Помимо чтения отчетов CQD, читатель отчетов [](https://support.office.com/article/activity-reports-0d6dfb17-8582-4172-a9a9-aed798150263) может просматривать все отчеты об активности в Центре администрирования и отчеты из пакета содержимого для Microsoft 365 [внедрения.](https://support.office.com/article/Office-365-Adoption-content-pack-77ff780d-ab19-4553-adea-09cb65ad0f1f)

> [!NOTE]
> Если вы не видите EUII (зависимые сведения [пользователя)](CQD-data-and-reports.md#euii-data) и у вас есть одна из ролей, которая разрешает просмотр этих сведений, имейте в виду, что CQD хранится только в течение 28 дней. Удаляются все данные старше 28 дней.

Дополнительные сведения об этих ролях см. в Office 365 [роли администраторов.](/office365/admin/add-users/about-admin-roles)


После первого входе CQD начнет сбор и обработку данных.




## <a name="use-power-bi-to-analyze-cqd-data"></a>Использование Power BI для анализа данных CQD

Новые возможности в январе 2020 г.: [скачивание шаблонов Power BI запросов для CQD.](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true) Настраиваемые Power BI шаблоны, которые можно использовать для анализа данных CQD и отчета о них.

Дополнительные сведения Power BI статью Использование Power BI данных [CQD.](CQD-Power-BI-query-templates.md)


## <a name="related-topics"></a>Статьи по теме

[Улучшение и отслеживание качества звонка для Teams](monitor-call-quality-qos.md)

[Что такое CQD?](CQD-what-is-call-quality-dashboard.md)

[Upload клиента и здания](CQD-upload-tenant-building-data.md)

[Данные и отчеты CQD](CQD-data-and-reports.md)

[Управление качеством звонка и собрания с помощью CQD](quality-of-experience-review-guide.md)

[Измерения и меры, доступные в CQD](dimensions-and-measures-available-in-call-quality-dashboard.md)

[Классификация потоков в CQD](stream-classification-in-call-quality-dashboard.md)

[Использование Power BI для анализа данных CQD](CQD-Power-BI-query-templates.md)
