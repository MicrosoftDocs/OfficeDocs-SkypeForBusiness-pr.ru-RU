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
ms.openlocfilehash: c71cb25732a99f207467a988ad0db54c959d15f4
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/06/2021
ms.locfileid: "52254539"
---
# <a name="set-up-call-quality-dashboard-cqd"></a>Настройка панели мониторинга качества звонка (CQD)

Откройте панель мониторинга качества звонка (CQD) Майкрософт по ссылке [https://cqd.teams.microsoft.com](https://cqd.teams.microsoft.com) (войди с учетными данными администратора). Или перейдите в Центр администрирования Teams и выберите **Панель мониторинга качества звонка**. 

:::image type="content" source="media/turning-on-and-using-call-quality-dashboard3.png" alt-text="Снимок экрана: кнопка панели мониторинга качества звонка в Teams администрирования":::

На открываемой странице нажмите кнопку **Войти** и введите учетную запись глобального администратора или Microsoft Teams учетную запись администратора. После первого войти в CQD начнет сбор и обработку данных. Имейте в виду, что обработка достаточного количества данных для отображения осмысленной информации в отчетах может занять несколько часов.

В CQD показаны качество звонка и собрания на уровне организации для Microsoft Teams, Skype для бизнеса Online и Skype для бизнеса Server 2019. 

> [!IMPORTANT]
> Чтобы использовать CQD в Skype для бизнеса Server 2019, необходимо настроить соединители данных [звонка.](/skypeforbusiness/hybrid/configure-call-data-connector) Перед [началом работы см.](/skypeforbusiness/hybrid/plan-call-data-connector) планирование соединитела данных зова.


## <a name="assign-admin-roles-for-access-to-cqd"></a>Назначение ролей администратора для доступа к CQD

[Назначать](/microsoft-365/admin/add-users/about-admin-roles) роли для доступа к CQD людям, которые должны его использовать.

Если вы хотите, чтобы пользователи без администрирования (например, инженеры службы поддержки и агенты службы технической поддержки) использовали панель мониторинга качества звонка, вы можете назначить им одну из следующих ролей, которая обеспечивает доступ к CQD. 


|  |Просмотр отчетов  |Просмотр полей EUII  |Создание отчетов  |Upload данных по зданиям  |
|---------|:-------:|:-------:|:-------:|:-------:|
|Глобальный администратор     |Да         |Да         |Да         |Да         |
|Teams Администратора     |Да         |Да         |Да         |Да         |
|Администратор коммуникаций Teams     |Да         |Да         |Да         |Да         |
|Инженер поддержки по коммуникациям Teams     |Да         |Да         |Да         |Нет         |
|Teams Специалист службы поддержки связи     |Да         |Нет         |Да         |Нет         |
|Skype для бизнеса Администратора     |Да         |Да         |Да         |Да         |
|Global Reader |Да         |Да         |Да         |Нет         |
|Reports Reader<sup>1</sup>     |Да         |Нет         |Да         |Нет         |

<sup>1</sup> Помимо чтения отчетов CQD, читатель отчетов [](https://support.office.com/article/activity-reports-0d6dfb17-8582-4172-a9a9-aed798150263) может просматривать все отчеты об активности в Центре администрирования и отчеты из пакета содержимого для Microsoft 365 [внедрения.](https://support.office.com/article/Office-365-Adoption-content-pack-77ff780d-ab19-4553-adea-09cb65ad0f1f)

> [!NOTE]
> Если вы не видите euII (зависимые сведения для конечного [пользователя)](CQD-data-and-reports.md#euii-data) и у вас есть одна из ролей, которая может видеть эти сведения, имейте в виду, что CQD хранится только в течение 28 дней. Удаляются все данные старше 28 дней.

Дополнительные сведения об этих ролях см. в Office 365 [роли администраторов.](/office365/admin/add-users/about-admin-roles)


После первого войти в CQD начнет сбор и обработку данных. С декабря 2019 г. вы по-прежнему сможете получить доступ к старой версии CQD (cqd.lync.com), хотя на устаревшем портале вы можете получить ссылку на последнюю версию CQD (cqd.teams.microsoft.com). Со временем более старая версия CQD будет списальна. С 1 июля 2020 г. более старая версия CQD будет получать доступ к данным из последней версии CQD.


## <a name="migrate-building-data-and-reports-from-previous-version-of-cqd"></a>Перенос данных здания и отчетов из предыдущей версии CQD

> [!IMPORTANT]
> С 1 июля 2020 г. вы больше не сможете перенести данные о здании и отчеты из старого CQD https://CQD.lync.com) (. 



## <a name="use-power-bi-to-analyze-cqd-data"></a>Использование Power BI для анализа данных CQD

Новое в январе 2020 г.: [скачивание шаблонов Power BI запросов для CQD.](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true) Настраиваемые Power BI шаблоны, которые можно использовать для анализа данных CQD и отчета о них.

Дополнительные сведения Power BI статью Использование Power BI для анализа данных [CQD.](CQD-Power-BI-query-templates.md)


## <a name="related-topics"></a>Статьи по теме

[Улучшение и отслеживание качества звонка для Teams](monitor-call-quality-qos.md)

[Что такое CQD?](CQD-what-is-call-quality-dashboard.md)

[Upload данных о клиенте и здании](CQD-upload-tenant-building-data.md)

[Данные и отчеты CQD](CQD-data-and-reports.md)

[Управление качеством звонка и собрания с помощью CQD](quality-of-experience-review-guide.md)

[Измерения и меры, доступные в CQD](dimensions-and-measures-available-in-call-quality-dashboard.md)

[Классификация потоков в CQD](stream-classification-in-call-quality-dashboard.md)

[Использование Power BI для анализа данных CQD](CQD-Power-BI-query-templates.md)