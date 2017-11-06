---
title: "Взаимодействие SharePoint Online и OneDrive для бизнеса с Microsoft Teams | Служба поддержки Майкрософт"
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
description: "Сведения о том, как SharePoint Online и OneDrive для бизнеса работают с Microsoft Teams, включая хранение файлов в приватных чатах, а также взаимодействие между командой, каналом и библиотекой документов."
Set_Free_Tag: Strat_MT_TeamsAdmin
ms.openlocfilehash: 1ea55116faa7a998a3b2db0828972424ce3acef8
ms.sourcegitcommit: 8cc7856bb7c305e0e96a4178535b1570cbfc3694
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/28/2017
---
<a name="how-sharepoint-online-and-onedrive-for-business-interact-with-microsoft-teams"></a>Взаимодействие SharePoint Online и OneDrive для бизнеса с Microsoft Teams
=============================================================================

Каждая команда в Microsoft Teams имеет свой сайт в SharePoint Online, а каждому каналу в команде назначается папка в библиотеке документов по умолчанию на этом сайте. Файлы, совместно используемые во время беседы, автоматически добавляются в библиотеку документов, а заданные в SharePoint разрешения и параметры безопасности файлов автоматически переносятся в Teams.

Файлы приватного чата хранятся в папке OneDrive для бизнеса **отправителя**, а соответствующие разрешения автоматически предоставляются всем участникам в рамках процедуры общего доступа.

Если SharePoint Online у вашего клиента отключен, возможности пользователей Microsoft Teams по общему доступу к файлам в командах будут ограничены. Участники приватного чата также не смогут совместно использовать файлы, так как для этого нужен OneDrive для бизнеса (привязанный к лицензии SharePoint).

При сохранении файлов в библиотеке документов SharePoint Online и OneDrive для бизнеса выполняются все требования по обеспечению соответствия, заданные на уровне клиента.

Ниже приведен пример взаимодействия между командой, каналом и библиотекой документов.

Для каждой команды создается сайт SharePoint, а также папка по умолчанию *Общие документы*. Каждый канал команды, включая канал по умолчанию **Общие**, имеет свою папку внутри папки *Общие документы*.

![Схема папок "Общие документы" в SharePoint Online для команды и ее каналов в Microsoft Teams.](media/Understand_how_SharePoint_Online_and_OneDrive_for_Business_interact_with_Microsoft_Teams_image1.png)

У каждого пользователя имеется папка OneDrive *Файлы чатов Microsoft Teams* для хранения всех файлов, предоставленных для общего доступа в приватных чатах с другими пользователями (в формате один к одному или один ко многим). При этом разрешения для ограничения доступа настраиваются автоматически.

![Схема папки OneDrive с именем "Файлы чатов Microsoft Teams" для каждого из чатов пользователя.](media/Understand_how_SharePoint_Online_and_OneDrive_for_Business_interact_with_Microsoft_Teams_image2.png)
