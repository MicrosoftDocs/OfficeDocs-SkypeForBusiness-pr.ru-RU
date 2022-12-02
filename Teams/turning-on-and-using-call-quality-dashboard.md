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
ms.openlocfilehash: 5f3b9fbb42199892136569ac179907b18da4e460
ms.sourcegitcommit: aef1ab47fb9cb4502cb49bc3c7ffafcd62e54c82
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2022
ms.locfileid: "69245795"
---
# <a name="set-up-the-call-quality-dashboard"></a>Настройка панели мониторинга качества звонков

Откройте Майкрософт панель мониторинга качества звонков (CQD) на странице [https://cqd.teams.microsoft.com](https://cqd.teams.microsoft.com) (войдите с учетными данными администратора). Или перейдите в Центр администрирования Teams и выберите **Аналитика & отчеты** > **Панель мониторинга качества звонков**.

:::image type="content" source="media/turning-on-and-using-call-quality-dashboard3.png" alt-text="Снимок экрана: кнопка панели мониторинга качества звонков в Центре администрирования Teams.":::

На открывающейся странице щелкните **Войти и введите** учетную запись глобального администратора или Майкрософт сведения об учетной записи администратора Teams. После первого входа CQD начнет сбор и обработку данных. Помните, что обработка достаточного количества данных для отображения значимых результатов в отчетах может занять один или несколько часов.

CQD показывает качество звонков и собраний на уровне всей организации для Майкрософт Teams, Skype для бизнеса Online и Skype для бизнеса Server 2019. 

> [!IMPORTANT]
> Чтобы использовать CQD с Skype для бизнеса Server 2019, необходимо [настроить соединитель данных вызова](/skypeforbusiness/hybrid/configure-call-data-connector). Перед началом работы см [. раздел Планирование соединителя данных звонков](/skypeforbusiness/hybrid/plan-call-data-connector) .


## <a name="assign-admin-roles-for-access-to-cqd"></a>Назначение ролей администратора для доступа к CQD

Назначьте [роли](/microsoft-365/admin/add-users/about-admin-roles) для доступа к CQD людям, которым нужно его использовать.

Если вы хотите, чтобы пользователи, не являющиеся администраторами (например, инженеры поддержки и агенты службы поддержки), использовали панель мониторинга качества вызовов, вы можете назначить этим пользователям одну из следующих ролей, которая предоставляет доступ к CQD. 


|&nbsp;  |Просмотр отчетов  |Просмотр полей EUII  |Создание отчетов  |Отправка данных о сборке  |
|---------|:-------:|:-------:|:-------:|:-------:|
|Глобальный администратор     |Да         |Да         |Да         |Да         |
|Администратор Teams     |Да         |Да         |Да         |Да         |
|Администратор коммуникаций Teams     |Да         |Да         |Да         |Да         |
|Инженер поддержки по коммуникациям Teams     |Да         |Да         |Да         |Нет         |
|Специалист по поддержке коммуникаций Teams     |Да         |Нет         |Да         |Нет         |
|Администратор Skype для бизнеса     |Да         |Да         |Да         |Да         |
|Глобальное средство чтения |Да         |Да         |Да         |Нет         |
|Читатель отчетов<sup>1</sup>     |Да         |Нет         |Да         |Нет         |

<sup>1</sup> Помимо чтения отчетов CQD, читатель отчетов может просматривать все [отчеты о действиях](https://support.office.com/article/activity-reports-0d6dfb17-8582-4172-a9a9-aed798150263) в Центре администрирования и любые отчеты из [пакета содержимого Майкрософт 365 Adoption](https://support.office.com/article/Office-365-Adoption-content-pack-77ff780d-ab19-4553-adea-09cb65ad0f1f).

> [!NOTE]
> Если вы не видите [EUII (сведения, идентифицируемые пользователем)](CQD-data-and-reports.md#euii-data) и у вас есть одна из ролей, которая может просматривать эту информацию, имейте в виду, что CQD хранит EUII только в течение 28 дней. Все, что старше 28 дней, удаляется.

Дополнительные сведения об этих ролях см. в разделе [Сведения об Office 365 роли администратора](/office365/admin/add-users/about-admin-roles).


После первого входа CQD начнет сбор и обработку данных.

## <a name="use-power-bi-to-analyze-cqd-data"></a>Использование Power BI для анализа данных CQD

Новые возможности в январе 2020 г [.: скачивание шаблонов запросов Power BI для CQD](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true). Настраиваемые шаблоны Power BI, которые можно использовать для анализа данных CQD и создания отчетов.

Дополнительные сведения см. в статье [Использование Power BI для анализа данных CQD](CQD-Power-BI-query-templates.md) .

## <a name="related-topics"></a>См. также

[Улучшение и мониторинг качества звонков для Teams](monitor-call-quality-qos.md)

[Что такое CQD?](CQD-what-is-call-quality-dashboard.md)

[Отправка данных о клиенте и сборке](CQD-upload-tenant-building-data.md)

[Данные и отчеты CQD](CQD-data-and-reports.md)

[Использование CQD для управления качеством звонков и собраний](quality-of-experience-review-guide.md)

[Измерения и меры, доступные в CQD](dimensions-and-measures-available-in-call-quality-dashboard.md)

[Классификация потоков в CQD](stream-classification-in-call-quality-dashboard.md)

[Использование Power BI для анализа данных CQD](CQD-Power-BI-query-templates.md)
