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
description: Узнайте, как добавлять и обновлять метки отчетов, добавляя текстовый файл со списком физических местоположений и связанных подсетей.
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

Метки отчетов используются в организации для обозначения физических местоположений офисов, зданий и сайтов организации. На странице меток отчетов в Центре администрирования Microsoft Teams можно предоставить текстовый файл (CSV- или TSV-файл), содержащий список физических местоположений и связанных с ними сетевых подсетей. Этот файл используется средством аналитики вызовов для создания отчетов. При отправке данных о сопоставлении подсети отчеты, предоставляемые этими службами, будут также содержать названия расположений, что упрощает понимание и использование отчетов для устранения потенциальных проблем.

> [!IMPORTANT]
> Отгрузка меток отчетов  обрабатывается как данные службы поддержки по вашему соглашению для  Office 365, включая любые сведения, которые в противном случае будут считаться данными клиента или личными *данными.* Не включайте в данные, которые не хотите предоставлять корпорации Майкрософт в качестве данных *поддержки,* так как эти сведения будут видны инженерам Майкрософт в целях поддержки.

Метки отчетов и данные о местоположении, которые вы предоставляете, — это единая структура данных, и в настоящее время интерфейса для редактирования отдельных данных не существует.

**Изменение таблицы подсетей и местоположений**

1. В левой области навигации Центра администрирования Microsoft Teams щелкните **метки отчетов**  >  Locations.
2. Нажмите **кнопку "Отправить данные".**
3. В области **"Отправка** данных" щелкните "Выберите файл", а затем перейдите к отредактируемму CSV- или TSV-файлу и загрузите его.
4. Нажмите **кнопку "Отправить".**

Вы можете скачать образец шаблона [здесь.](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/locations-template.zip?raw=true)

Используйте следующий пример для создания файла данных:

> [!IMPORTANT]
> Файл данных не должен содержать столбцов (например, "Сеть", "Сетевое имя" и т. д.). Они используются исключительно в информационных целях. <br>

|Сеть|Network Name|Диапазон сети|Название здания|Тип владения|Тип здания|Тип здания Для Office|City|Почтовый индекс|Страна|State|Region|Inside Corp|Express Route|
|-|-|-|-|-|-|-|-|-|-|-|-|-|-|
|10.0.128.0    |SVC-1|32|USCAMTV001|Contoso Leased RE&F|Office|RE&F|Горный вид|94043|США|CA|США|1|1|
|10.0.130.0    |SVC-1|32|USCAMTV001|Contoso Leased RE&F|Office|RE&F|Горный вид|94043|США|CA|США|1|1|
|10.0.131.0    |SVC-1|32|USCAMTV001|Contoso Leased RE&F|Office|RE&F|Горный вид|94043|США|CA|США|1|1|
|10.0.132.0    |SVC-1|32|USCAMTV001|Contoso Leased RE&F|Office|RE&F|Горный вид|94043|США|CA|США|1|1|

Дополнительные сведения о форматирование файла данных см. в формате файла данных клиента и структуре [файла данных о здании.](CQD-upload-tenant-building-data.md#upload-building-data-file)

## <a name="related-topics"></a>Связанные статьи

[Настройка аналитики звонков](set-up-call-analytics.md)

[Устранение неполадок с качеством звонка с помощью средства аналитики звонка](use-call-analytics-to-troubleshoot-poor-call-quality.md)
