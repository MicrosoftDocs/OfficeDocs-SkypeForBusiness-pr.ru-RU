---
title: Взаимодействие SharePoint Online и OneDrive для бизнеса с Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 07/31/2018
ms.topic: article
ms.service: msteams
ms.reviewer: snigdhav
description: Сведения о том, как SharePoint Online и OneDrive для бизнеса работают с Microsoft Teams, включая хранение файлов в приватных чатах, а также взаимодействие между командой, каналом и библиотекой документов.
localization_priority: Priority
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: f91836848f6a7698025e118542628cbce44166c6
ms.sourcegitcommit: 046cc4a880f3b6b5f912278483cf28fa25619b6e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/31/2018
ms.locfileid: "21597585"
---
<a name="how-sharepoint-online-and-onedrive-for-business-interact-with-microsoft-teams"></a>Взаимодействие SharePoint Online и OneDrive для бизнеса с Microsoft Teams
=============================================================================

Каждая команда в Microsoft Teams имеет свой сайт в SharePoint Online, а каждому каналу в команде назначается папка в библиотеке документов по умолчанию на этом сайте. Файлы, совместно используемые во время беседы, автоматически добавляются в библиотеку документов, а заданные в SharePoint разрешения и параметры безопасности файлов автоматически переносятся в Teams.

Файлы приватного чата хранятся в папке OneDrive для бизнеса отправителя, а соответствующие разрешения автоматически предоставляются всем участникам в рамках процедуры общего доступа.

Если пользователям не назначены активные лицензии SharePoint Online, у них нет хранилища OneDrive для бизнеса в Office 365. Общий доступ к файлам будет продолжать работать в каналы, но пользователи не смогут для совместного использования файлов в чаты без OneDrive для бизнеса хранилища в Office 365.

При сохранении файлов в библиотеке документов SharePoint Online и OneDrive для бизнеса выполняются все требования по обеспечению соответствия, заданные на уровне клиента. 

> [!NOTE]
> Интеграция с Sharepoint в локальной не поддерживается для групп Майкрософт в данный момент.

Ниже приведен пример взаимодействия между командой, каналом и библиотекой документов.

Для каждой команды создается сайт SharePoint, а также папка по умолчанию **Общие документы**. Каждый канал команды, включая канал по умолчанию **Общие**, имеет свою папку внутри папки **Общие документы**.

![Схема папок "Общие документы" в SharePoint Online для команды и ее каналов в Microsoft Teams.](media/Understand_how_SharePoint_Online_and_OneDrive_for_Business_interact_with_Microsoft_Teams_image1.png)

> [!NOTE]
> В настоящее время вы не можете заменить библиотеку документов и сайт SharePoint по умолчанию. Нас часто спрашивают об этой возможности, и мы рассматриваем пути ее внедрения. Обо всех готовящихся изменениях вы можете узнать в [Стратегии развития Teams](https://aka.ms/teamsroadmap) и в [посвященном Teams разделе UserVoice](https://aka.ms/TeamsUserVoice).

У каждого пользователя имеется папка OneDrive **Файлы чатов Microsoft Teams** для хранения всех файлов, предоставленных для общего доступа в приватных чатах с другими пользователями (в формате один к одному или один ко многим). При этом разрешения для ограничения доступа настраиваются автоматически.

![Схема папки OneDrive с именем "Файлы чатов Microsoft Teams" для каждого из чатов пользователя.](media/Understand_how_SharePoint_Online_and_OneDrive_for_Business_interact_with_Microsoft_Teams_image2.png)
