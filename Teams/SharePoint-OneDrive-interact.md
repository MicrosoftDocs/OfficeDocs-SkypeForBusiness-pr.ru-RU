---
title: Взаимодействие SharePoint Online и OneDrive для бизнеса с Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 11/12/2018
ms.topic: conceptual
ms.service: msteams
ms.reviewer: snigdhav
search.appverid: MET150
description: Сведения о том, как SharePoint Online и OneDrive для бизнеса работают с Microsoft Teams, включая хранение файлов в приватных чатах, а также взаимодействие между командой, каналом и библиотекой документов.
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9aba8bba3f2b00e00bae2a38d4b1cc7954cffe06
ms.sourcegitcommit: 3014331fff89a0842c4db0b9adf0ef32f9728ade
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2019
ms.locfileid: "30640692"
---
<a name="how-sharepoint-online-and-onedrive-for-business-interact-with-microsoft-teams"></a>Взаимодействие SharePoint Online и OneDrive для бизнеса с Microsoft Teams
=============================================================================

> [!Tip]
> Просмотрите следующие сеанса, чтобы узнать, как группы взаимодействует с Azure Active Directory (AAD), группы Office 365, Exchange, SharePoint и OneDrive для бизнеса: [Основы группами Майкрософт](https://aka.ms/teams-foundations)

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

> [!TIP]
> Добавление вкладки в группу, приведены ссылки на существующие страницы сайта SharePoint или для вашей существующей библиотеки документов SharePoint:
> 1. Выберите значок "плюс" рядом с вкладками.
> 2. Выберите **SharePoint** для существующей страницы сайта SharePoint или **Библиотеки документов** для существующей библиотеки документов.
> 3. Выберите соответствующую библиотеку страницы или документа.

У каждого пользователя имеется папка OneDrive **Файлы чатов Microsoft Teams** для хранения всех файлов, предоставленных для общего доступа в приватных чатах с другими пользователями (в формате один к одному или один ко многим). При этом разрешения для ограничения доступа настраиваются автоматически.

![Схема папки OneDrive с именем "Файлы чатов Microsoft Teams" для каждого из чатов пользователя.](media/Understand_how_SharePoint_Online_and_OneDrive_for_Business_interact_with_Microsoft_Teams_image2.png)

<a name="more-information"></a>Дополнительные сведения
----------------

Дополнительные сведения о работе с группами SharePoint можно [SharePoint и рабочих групп: эффективная совместная работа](https://techcommunity.microsoft.com/t5/Microsoft-SharePoint-Blog/SharePoint-and-Teams-Better-Together/ba-p/189593).


