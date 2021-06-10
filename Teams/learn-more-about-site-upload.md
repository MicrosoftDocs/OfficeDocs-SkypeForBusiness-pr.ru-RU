---
title: Добавление и обновление наклеек для отчетов
author: tonysmit
ms.author: tonysmit
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: ''
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
description: Узнайте, как добавлять и обновлять метки отчетов, загрузив текстовый файл со списком физических местоположений и связанных подсетей.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- ms.teamsadmincenter.locations.reportinglabels.overview
- ms.teamsadmincenter.voice.phonenumbers.searchacquire.tooltip.location
- ms.teamsadmincenter.locations.overview
- seo-marvel-mar2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 481e087a6cfe2b641f6b81fcfc893d50f27cbf47
ms.sourcegitcommit: 75ccb8cda9e6dd900df93a2d856ff5f7682ac623
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2021
ms.locfileid: "50237489"
---
<a name="add-and-update-reporting-labels"></a>Добавление и обновление наклеек для отчетов
============================

Метки отчетов используются в организации для обозначения физических местоположений офисов, зданий или сайтов организации. На странице Метки отчетов в Центре администрирования Microsoft Teams вы можете предоставить текстовый файл (.csv или TSV), содержащий список физических местоположений и связанных с ними сетевых подсетей. Этот файл используется средством аналитики вызовов для создания отчетов. При отправке сопоставления подсети отчеты, предоставленные этими службами, также будут содержать имена расположений, что упрощает их понимание и использование для устранения потенциальных проблем.

> [!IMPORTANT]
> Отложенные метки отчетов обрабатываются как данные поддержки в соответствии с соглашением о  Office 365, включая любые сведения, которые в противном случае считались данными клиента или *личными данными.*  Не включайте данные, которые вы не хотите предоставлять корпорации Майкрософт в качестве данных *поддержки,* так как эти сведения будут видны инженерам Майкрософт в целях поддержки.

Метки отчетов и данные о расположениях, которые вы предоставляете, — это единая структура данных, и в настоящее время интерфейса для отдельных изменений данных не существует.

**Изменение таблицы подсетей и местоположений**

1. В левой области навигации Центра администрирования Microsoft Teams щелкните **Метки** отчетов  >  **о расположениях**.
2. Щелкните **Upload данные**.
3. В области **Upload** выберите выберите файл **,** а затем перейдите к отредактируемой .csv или TSV-файлу.
4. Нажмите **Upload**.

Пример шаблона можно скачать [здесь.](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/locations-template.zip?raw=true)

Чтобы создать файл данных, воспользуйтесь следующим примером:

> [!IMPORTANT]
> Файл данных не должен содержать столбцов (например, Network, Network Name и т. д.). Они используются исключительно в информационных целях. <br>

|Сеть|Network Name|Диапазон сети|Название здания|Тип владения|Тип здания|Тип Office здания|City|Почтовый индекс|Страны|State|Region|Inside Corp|Express Route|
|-|-|-|-|-|-|-|-|-|-|-|-|-|-|
|10.0.128.0    |SVC-1|32|USCAMTV001|Contoso Leased RE&F|Office|RE&F|Горный вид|94043|Нам|Ca|Нам|1|1|
|10.0.130.0    |SVC-1|32|USCAMTV001|Contoso Leased RE&F|Office|RE&F|Горный вид|94043|Нам|Ca|Нам|1|1|
|10.0.131.0    |SVC-1|32|USCAMTV001|Contoso Leased RE&F|Office|RE&F|Горный вид|94043|Нам|Ca|Нам|1|1|
|10.0.132.0    |SVC-1|32|USCAMTV001|Contoso Leased RE&F|Office|RE&F|Горный вид|94043|Нам|Ca|Нам|1|1|

Дополнительные сведения о форматирование файла данных см. в материалах Формат файла данных клиента и [Структура файла данных здания.](CQD-upload-tenant-building-data.md#upload-building-data-file)

## <a name="related-topics"></a>Статьи по теме

[Настройка аналитики звонков](set-up-call-analytics.md)

[Использование аналитики вызовов для устранения неполадок с качеством звонка](use-call-analytics-to-troubleshoot-poor-call-quality.md)
