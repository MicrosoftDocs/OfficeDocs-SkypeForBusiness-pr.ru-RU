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
ms.openlocfilehash: 20204d0c766a9ff248ff8354d9367a9903149d46
ms.sourcegitcommit: 97c2faab08ec9b8fc9967827883308733ec162ea
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/13/2021
ms.locfileid: "58235014"
---
# <a name="add-and-update-reporting-labels"></a>Добавление и обновление наклеек для отчетов

Метки отчетов используются в организации для обозначения физических местоположений офисов, зданий или сайтов организации. На странице Метки отчетов в Центре администрирования Microsoft Teams вы можете предоставить текстовый файл (.csv или TSV), содержащий список физических местоположений и связанных с ними сетевых подсетей. Этот файл используется средством аналитики вызовов для создания отчетов. При отправке сопоставления подсети отчеты, предоставленные этими службами, также будут содержать имена расположений, что упрощает их понимание и использование для устранения потенциальных проблем.

> [!IMPORTANT]
> Отложенные метки отчетов обрабатываются как данные поддержки в соответствии с соглашением о Office 365, включая любые сведения, которые в противном случае считались данными клиента или   *личными данными.* Не включайте данные, которые вы не хотите предоставлять корпорации Майкрософт в качестве данных *поддержки,* так как эти сведения будут видны инженерам Майкрософт в целях поддержки.

Метки отчетов и данные о расположениях, которые вы предоставляете, — это единая структура данных, так как в настоящее время интерфейса для отдельных изменений данных не существует.

**Изменение таблицы подсетей и местоположений**

1. В левой области навигации Центра администрирования Microsoft Teams щелкните **Метки** отчетов о  >  **расположениях**.
2. Щелкните **Upload данных**.
3. В Upload **данных** щелкните Выбрать файл **,** а затем найдите и загрузите измененный .csv или TSV-файл.
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
