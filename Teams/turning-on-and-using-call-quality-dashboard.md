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
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Reporting
- ms.teamsadmincenter.directrouting.cqd
- ms.lync.lac.ToolsCallQualityDashboard
- seo-marvel-apr2020
description: Узнайте, как включить и использовать панель мониторинга качества звонков и получить сводные отчеты о качестве звонков.
ms.openlocfilehash: 2d671de0e2ddc5d4c2a4e321cf90e2e2f0dbe770
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51162666"
---
# <a name="set-up-call-quality-dashboard-cqd"></a>Настройка панели мониторинга качества звонка (CQD)

Откройте панель мониторинга качества звонка Майкрософт (CQD) на странице (во sign [https://cqd.teams.microsoft.com](https://cqd.teams.microsoft.com) in with your admin credentials). Или перейдите в Центр администрирования Teams и выберите **панель мониторинга качества звонка.** 

:::image type="content" source="media/turning-on-and-using-call-quality-dashboard3.png" alt-text="Снимок экрана: кнопка панели мониторинга качества звонка в Центре администрирования Teams":::

На открываемой  странице щелкните "Вход" и введите данные учетной записи глобального администратора или учетной записи администратора служб Microsoft Teams. После первого входа В CQD начнется сбор и обработка данных. Имейте в виду, что обработка достаточного количества данных для получения осмысленной информации в отчетах может занять несколько часов.

CQD показывает качество звонков и собраний на уровне организации для Microsoft Teams, Skype для бизнеса Online и Skype для бизнеса Server 2019. 

> [!IMPORTANT]
> Чтобы использовать CQD в Skype для бизнеса Server 2019, необходимо настроить соединители данных [звонков.](/skypeforbusiness/hybrid/configure-call-data-connector) Перед [началом работы см.](/skypeforbusiness/hybrid/plan-call-data-connector) соединители данных для планирования зовов.


## <a name="assign-admin-roles-for-access-to-cqd"></a>Назначение ролей администратора для доступа к CQD

[Назначать](/microsoft-365/admin/add-users/about-admin-roles) роли для доступа к CQD людям, которые должны его использовать.

Если вы хотите, чтобы панель мониторинга качества звонка была нужна пользователям без администрирования (например, инженерам службы поддержки и агентам службы технической поддержки), можно назначить им одну из следующих ролей, которая обеспечивает доступ к панели мониторинга качества звонка. 


|  |Просмотр отчетов  |Просмотр полей EUII  |Создание отчетов  |Отправка данных о здании  |
|---------|:-------:|:-------:|:-------:|:-------:|
|Глобальный администратор     |Да         |Да         |Да         |Да         |
|Администратор служб Teams     |Да         |Да         |Да         |Да         |
|Администратор коммуникаций Teams     |Да         |Да         |Да         |Да         |
|Инженер поддержки по коммуникациям Teams     |Да         |Да         |Да         |Нет         |
|Специалист по поддержке связи в Teams     |Да         |Нет         |Да         |Нет         |
|Администратор Skype для бизнеса     |Да         |Да         |Да         |Да         |
|Global Reader |Да         |Да         |Да         |Нет         |
|Читатель отчетов<sup>1</sup>     |Да         |Нет         |Да         |Нет         |

<sup>1</sup> В дополнение к чтению отчетов CQD читатель [](https://support.office.com/article/activity-reports-0d6dfb17-8582-4172-a9a9-aed798150263) отчетов может просматривать все отчеты об активности в Центре администрирования и все отчеты из пакета содержимого для внедрения [Microsoft 365.](https://support.office.com/article/Office-365-Adoption-content-pack-77ff780d-ab19-4553-adea-09cb65ad0f1f)

> [!NOTE]
> Если вы не видите EUII (идентифицируемую информацию конечных пользователей) и у вас есть одна из ролей, которая может видеть эту информацию, имейте в виду, что CQD хранит [euII](CQD-data-and-reports.md#euii-data) только в течение 28 дней. Все данные старше 28 дней будут удалены.

Дополнительные сведения об этих ролях см. в сведениях о ролях администраторов [в Office 365.](/office365/admin/add-users/about-admin-roles)


После первого входа В CQD начнется сбор и обработка данных. С декабря 2019 г. вы по-прежнему сможете использовать более старую версию CQD (cqd.lync.com), однако старый портал предоставляет ссылку на последнюю версию CQD (cqd.teams.microsoft.com). Со временем более старая версия CQD будет списальна. С 1 июля 2020 г. более старая версия CQD будет получать доступ к данным из последней версии CQD.


## <a name="migrate-building-data-and-reports-from-previous-version-of-cqd"></a>Перенос данных здания и отчетов из предыдущей версии CQD

> [!IMPORTANT]
> С 1 июля 2020 г. вы больше не сможете перенести данные о здании и отчеты из старого CQD ( https://CQD.lync.com) . 



## <a name="use-power-bi-to-analyze-cqd-data"></a>Анализ данных CQD с помощью Power BI

Новое в январе 2020 г.: скачивание шаблонов [запросов Power BI для CQD.](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true) Настраиваемые шаблоны Power BI, которые можно использовать для анализа данных CQD и отчетов о них.

Дополнительные сведения об использовании Power BI для [анализа данных CQD.](CQD-Power-BI-query-templates.md)


## <a name="related-topics"></a>Статьи по теме

[Улучшение и отслеживание качества вызовов в Teams](monitor-call-quality-qos.md)

[Что такое CQD?](CQD-what-is-call-quality-dashboard.md)

[Отправка данных о клиенте и здании](CQD-upload-tenant-building-data.md)

[Данные и отчеты CQD](CQD-data-and-reports.md)

[Управление звонками и качеством собраний с помощью CQD](quality-of-experience-review-guide.md)

[Измерения и меры, доступные в CQD](dimensions-and-measures-available-in-call-quality-dashboard.md)

[Классификация потоков в CQD](stream-classification-in-call-quality-dashboard.md)

[Анализ данных CQD с помощью Power BI](CQD-Power-BI-query-templates.md)