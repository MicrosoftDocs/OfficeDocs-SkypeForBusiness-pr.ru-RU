---
title: Настройка панели мониторинга качества звонков (CQD)
author: CarolynRowe
ms.author: crowe
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
ms.openlocfilehash: 052b38634d17aa6d0086c80ed2a638a7818a729f
ms.sourcegitcommit: 4d88637f510a78d5709d1213c3e285d83a022014
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/14/2022
ms.locfileid: "66797384"
---
# <a name="set-up-call-quality-dashboard"></a>Настройка панели мониторинга качества звонков

Откройте панель мониторинга качества звонков (CQD) [https://cqd.teams.microsoft.com](https://cqd.teams.microsoft.com) Майкрософт по адресу (войдите с учетными данными администратора). Или перейдите в Центр администрирования Teams и выберите **Analytics & панели мониторинга** >  качества **вызовов**.

:::image type="content" source="media/turning-on-and-using-call-quality-dashboard3.png" alt-text="Снимок экрана: кнопка панели мониторинга качества звонков в Центре администрирования Teams.":::

На открываемой странице щелкните **"Войти"** и введите учетную запись глобального администратора или учетную запись администратора Microsoft Teams. После первого входа CQD начнет сбор и обработку данных. Помните, что обработка достаточного количества данных для отображения значимых результатов в отчетах может занять один или несколько часов.

CQD показывает качество звонков и собраний на уровне организации для Microsoft Teams, Skype для бизнеса Online и Skype для бизнеса Server 2019. 

> [!IMPORTANT]
> Чтобы использовать CQD Skype для бизнеса Server 2019, необходимо настроить соединитель данных [вызовов](/skypeforbusiness/hybrid/configure-call-data-connector). Перед [началом работы см. раздел Plan Call Data Connector](/skypeforbusiness/hybrid/plan-call-data-connector) .


## <a name="assign-admin-roles-for-access-to-cqd"></a>Назначение ролей администратора для доступа к CQD

[Назначьте](/microsoft-365/admin/add-users/about-admin-roles) роли для доступа к CQD пользователям, которым он нужен.

Если вы хотите, чтобы пользователи без прав администратора (например, инженеры службы поддержки и агенты службы технической поддержки) могли использовать панель мониторинга качества звонков, вы можете назначить этим пользователям одну из следующих ролей, которая предоставляет доступ к CQD. 


|&nbsp;  |Просмотр отчетов  |Просмотр полей EUII  |Создание отчетов  |Отправка данных сборки  |
|---------|:-------:|:-------:|:-------:|:-------:|
|Глобальный администратор     |Да         |Да         |Да         |Да         |
|Администратор Teams     |Да         |Да         |Да         |Да         |
|Администратор коммуникаций Teams     |Да         |Да         |Да         |Да         |
|Инженер поддержки по коммуникациям Teams     |Да         |Да         |Да         |Нет         |
|Специалист службы поддержки связи Teams     |Да         |Нет         |Да         |Нет         |
|Skype для бизнеса администратора     |Да         |Да         |Да         |Да         |
|Глобальный читатель |Да         |Да         |Да         |Нет         |
|Читатель отчетов<sup>1</sup>     |Да         |Нет         |Да         |Нет         |

<sup>1</sup> В дополнение к чтению отчетов CQD средство чтения отчетов может просматривать все отчеты [](https://support.office.com/article/activity-reports-0d6dfb17-8582-4172-a9a9-aed798150263) об активности в Центре администрирования и любые отчеты из пакета содержимого [внедрения Microsoft 365](https://support.office.com/article/Office-365-Adoption-content-pack-77ff780d-ab19-4553-adea-09cb65ad0f1f).

> [!NOTE]
> Если вы не видите [EUII (](CQD-data-and-reports.md#euii-data) идентифицируемые сведения для конечных пользователей) и у вас есть одна из ролей, которым разрешено просматривать эти сведения, помните, что CQD хранит EUII только в течение 28 дней. Удаляются все данные старше 28 дней.

Дополнительные сведения об этих ролях см. в разделе [Office 365 роли администратора](/office365/admin/add-users/about-admin-roles).


После первого входа CQD начнет сбор и обработку данных.

## <a name="use-power-bi-to-analyze-cqd-data"></a>Анализ данных CQD с помощью Power BI

Новые возможности в январе 2020 г [.: скачивание шаблонов запросов Power BI для CQD](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true). Настраиваемые шаблоны Power BI, которые можно использовать для анализа данных CQD и создания отчетов о них.

Дополнительные сведения см. в описании использования [Power BI для анализа данных CQD](CQD-Power-BI-query-templates.md) .

## <a name="related-topics"></a>См. также

[Улучшение и мониторинг качества звонков для Teams](monitor-call-quality-qos.md)

[Что такое CQD?](CQD-what-is-call-quality-dashboard.md)

[Отправка данных о клиенте и сборке](CQD-upload-tenant-building-data.md)

[Данные и отчеты CQD](CQD-data-and-reports.md)

[Управление качеством звонков и собраний с помощью CQD](quality-of-experience-review-guide.md)

[Измерения и меры, доступные в CQD](dimensions-and-measures-available-in-call-quality-dashboard.md)

[Классификация потоков в CQD](stream-classification-in-call-quality-dashboard.md)

[Анализ данных CQD с помощью Power BI](CQD-Power-BI-query-templates.md)
