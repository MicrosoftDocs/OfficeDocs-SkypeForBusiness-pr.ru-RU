---
title: Взаимодействие SharePoint Online и OneDrive для бизнеса с Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 07/31/2018
ms.topic: article
ms.service: msteams
ms.reviewer: snigdhav
search.appverid: MET150
description: Сведения о том, как SharePoint Online и OneDrive для бизнеса работают с Microsoft Teams, включая хранение файлов в приватных чатах, а также взаимодействие между командой, каналом и библиотекой документов.
localization_priority: Priority
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 7ef9773ce43ce395cd27982eeb91d1c6081a88d4
ms.sourcegitcommit: 2a6e499165424fe2d189ad140951e222c8ba9c81
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2018
ms.locfileid: "23861193"
---
<a name="how-sharepoint-online-and-onedrive-for-business-interact-with-microsoft-teams"></a><span data-ttu-id="83e2d-103">Взаимодействие SharePoint Online и OneDrive для бизнеса с Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="83e2d-103">How SharePoint Online and OneDrive for Business interact with Microsoft Teams</span></span>
=============================================================================

<span data-ttu-id="83e2d-104">Каждая команда в Microsoft Teams имеет свой сайт в SharePoint Online, а каждому каналу в команде назначается папка в библиотеке документов по умолчанию на этом сайте.</span><span class="sxs-lookup"><span data-stu-id="83e2d-104">Each team in Microsoft Teams has a team site in SharePoint Online, and each channel in a team gets a folder within the default team site document library.</span></span> <span data-ttu-id="83e2d-105">Файлы, совместно используемые во время беседы, автоматически добавляются в библиотеку документов, а заданные в SharePoint разрешения и параметры безопасности файлов автоматически переносятся в Teams.</span><span class="sxs-lookup"><span data-stu-id="83e2d-105">Files shared within a conversation are automatically added to the document library, and permissions and file security options set in SharePoint are automatically reflected within Teams.</span></span>

<span data-ttu-id="83e2d-106">Файлы приватного чата хранятся в папке OneDrive для бизнеса отправителя, а соответствующие разрешения автоматически предоставляются всем участникам в рамках процедуры общего доступа.</span><span class="sxs-lookup"><span data-stu-id="83e2d-106">Private chat files are stored in the sender’s OneDrive for Business folder, and permissions are automatically granted to all participants as part of the file sharing process.</span></span>

<span data-ttu-id="83e2d-107">Если пользователям не назначены активные лицензии SharePoint Online, у них нет хранилища OneDrive для бизнеса в Office 365.</span><span class="sxs-lookup"><span data-stu-id="83e2d-107">If users aren't assigned and enabled with SharePoint Online licenses, they don't have OneDrive for Business storage in Office 365.</span></span> <span data-ttu-id="83e2d-108">Общий доступ к файлам будет продолжать работать в каналы, но пользователи не смогут для совместного использования файлов в чаты без OneDrive для бизнеса хранилища в Office 365.</span><span class="sxs-lookup"><span data-stu-id="83e2d-108">File sharing will continue to work in channels, but users won't be able to share files in chats without OneDrive for Business storage in Office 365.</span></span>

<span data-ttu-id="83e2d-109">При сохранении файлов в библиотеке документов SharePoint Online и OneDrive для бизнеса выполняются все требования по обеспечению соответствия, заданные на уровне клиента.</span><span class="sxs-lookup"><span data-stu-id="83e2d-109">By storing the files in the SharePoint Online document library and OneDrive for Business, all compliance rules configured at the tenant level will be followed.</span></span> 

> [!NOTE]
> <span data-ttu-id="83e2d-110">Интеграция с Sharepoint в локальной не поддерживается для групп Майкрософт в данный момент.</span><span class="sxs-lookup"><span data-stu-id="83e2d-110">Integration with Sharepoint On-premises is not supported for Microsoft Teams at this time.</span></span>

<span data-ttu-id="83e2d-111">Ниже приведен пример взаимодействия между командой, каналом и библиотекой документов.</span><span class="sxs-lookup"><span data-stu-id="83e2d-111">The following is the example of relationships between team, channel, and document library.</span></span>

<span data-ttu-id="83e2d-112">Для каждой команды создается сайт SharePoint, а также папка по умолчанию **Общие документы**.</span><span class="sxs-lookup"><span data-stu-id="83e2d-112">For every team, a SharePoint site is created, and the **Shared Documents** folder is the default folder created for the team.</span></span> <span data-ttu-id="83e2d-113">Каждый канал команды, включая канал по умолчанию **Общие**, имеет свою папку внутри папки **Общие документы**.</span><span class="sxs-lookup"><span data-stu-id="83e2d-113">Each channel, including the **General** channel (the default channel for each team) has a folder in **Shared Documents**.</span></span>

![Схема папок "Общие документы" в SharePoint Online для команды и ее каналов в Microsoft Teams.](media/Understand_how_SharePoint_Online_and_OneDrive_for_Business_interact_with_Microsoft_Teams_image1.png)

> [!NOTE]
> <span data-ttu-id="83e2d-115">В настоящее время вы не можете заменить библиотеку документов и сайт SharePoint по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="83e2d-115">It's not currently possible to replace the default SharePoint site and document library with another one.</span></span> <span data-ttu-id="83e2d-116">Нас часто спрашивают об этой возможности, и мы рассматриваем пути ее внедрения.</span><span class="sxs-lookup"><span data-stu-id="83e2d-116">We've heard from you that you want it, and we're considering it.</span></span> <span data-ttu-id="83e2d-117">Обо всех готовящихся изменениях вы можете узнать в [Стратегии развития Teams](https://aka.ms/teamsroadmap) и в [посвященном Teams разделе UserVoice](https://aka.ms/TeamsUserVoice).</span><span class="sxs-lookup"><span data-stu-id="83e2d-117">Check the [Teams Roadmap](https://aka.ms/teamsroadmap) or [Teams UserVoice](https://aka.ms/TeamsUserVoice) to stay on top of upcoming features.</span></span>

> [!TIP]
> <span data-ttu-id="83e2d-118">Добавление вкладки в группу, что ссылки на существующие SharePoint веб-сайтов или к существующей SharePoint библиотеки документов:</span><span class="sxs-lookup"><span data-stu-id="83e2d-118">To add a tab to your team that links to an existing SharePoint site or to your existing SharePoint document library:</span></span>
> 1. <span data-ttu-id="83e2d-119">Выберите значок "плюс" рядом с вкладками.</span><span class="sxs-lookup"><span data-stu-id="83e2d-119">Select the  plus sign next to the tabs.</span></span>
> 2. <span data-ttu-id="83e2d-120">Выберите **веб-сайт**.</span><span class="sxs-lookup"><span data-stu-id="83e2d-120">Select **Website**.</span></span>
> 3. <span data-ttu-id="83e2d-121">Введите имя и введите URL-адрес библиотеки документов или сайт SharePoint.</span><span class="sxs-lookup"><span data-stu-id="83e2d-121">Type a name and enter the URL of your SharePoint site or document library.</span></span>

<span data-ttu-id="83e2d-122">У каждого пользователя имеется папка OneDrive **Файлы чатов Microsoft Teams** для хранения всех файлов, предоставленных для общего доступа в приватных чатах с другими пользователями (в формате один к одному или один ко многим). При этом разрешения для ограничения доступа настраиваются автоматически.</span><span class="sxs-lookup"><span data-stu-id="83e2d-122">For every user, the OneDrive folder **Microsoft Teams Chat Files** is used to store all files shared within private chats with other users (1:1 or 1:many), with permissions configured automatically to restrict access to the intended user only.</span></span>

![Схема папки OneDrive с именем "Файлы чатов Microsoft Teams" для каждого из чатов пользователя.](media/Understand_how_SharePoint_Online_and_OneDrive_for_Business_interact_with_Microsoft_Teams_image2.png)
