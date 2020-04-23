---
title: Файлы и папки Teams, которые должны быть исключены из проверки на вирусы
author: msdmaguire
ms.author: dmaguire
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: ramesa
audience: admin
description: Улучшите производительность Teams за счет исключения некоторых файлов и папок из обычной проверки антивирусной программы.
localization_priority: Normal
search.appverid: MET150
ROBOTS: NOINDEX, NOFOLLOW
f1.keywords:
- NOCSH
ms.collection:
- Teams_ITAdmin_PracticalGuidance
appliesto:
- Microsoft Teams
ms.openlocfilehash: a1e890509428b3bfba19f6bfb01916e8ea837147
ms.sourcegitcommit: 0fa50d1cf354d79fbaf16b6aaec60e8d3ab852e8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/21/2020
ms.locfileid: "43579595"
---
<a name="teams-files-and-folders-to-exclude-from-antivirus-scanning"></a>Файлы и папки Teams, которые должны быть исключены из проверки на вирусы
=================================

Вы можете повысить общую производительность развертывания Teams, запретив антивирусным программам проверять определенные файлы и папки в группах. Это позволит избежать расхода системных ресурсов на просмотр файлов и папок, которые не требуется сканировать.

> [!NOTE]
> Когда пользователи загружают файлы или совместно с другими файлами, эти файлы не проходят через расположения, указанные в следующем разделе. Антивирусная программа будет регулярно сканировать файлы, в которых ваши пользователи выполняют передачу, скачивание или предоставление общего доступа к файлам.

## <a name="files-and-folders-to-add-to-your-antivirus-safe-lists"></a>Файлы и папки, которые нужно добавить в список надежных антивирусных программ

С помощью процедур, поддерживаемых антивирусной программой, добавьте в списки надежных файлов указанные ниже файлы и папки. Это обеспечит экономию системных ресурсов, устраняя антивирусные проверки этих местоположений.

### <a name="programs"></a>Приложениях

Добавьте следующие программы Teams в список надежных для антивирусных программ.

**%localappdata%\Microsoft\Teams\current\Teams.exe**

**%localappdata%\Microsoft\Teams\Update.exe**

