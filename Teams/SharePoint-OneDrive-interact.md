---
title: "Взаимодействие SharePoint Online и OneDrive для бизнеса с Microsoft Teams"
author: LolaJacobsen
ms.author: lolaj
manager: lolaj
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
description: "Сведения о том, как SharePoint Online и OneDrive для бизнеса работают с Microsoft Teams, включая хранение файлов в приватных чатах, а также взаимодействие между командой, каналом и библиотекой документов."
MS.collection: Strat_MT_TeamsAdmin
ms.openlocfilehash: b7d9ffad23c8f26d7d95c3f31df4ff0307517179
ms.sourcegitcommit: 3faedb6057da8650b06b05f9c9bdd941d5ade175
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/20/2017
---
<a name="how-sharepoint-online-and-onedrive-for-business-interact-with-microsoft-teams"></a><span data-ttu-id="a129d-103">Взаимодействие SharePoint Online и OneDrive для бизнеса с Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="a129d-103">How SharePoint Online and OneDrive for Business interact with Microsoft Teams</span></span>
=============================================================================

<span data-ttu-id="a129d-104">Каждая команда в Microsoft Teams имеет свой сайт в SharePoint Online, а каждому каналу в команде назначается папка в библиотеке документов по умолчанию на этом сайте.</span><span class="sxs-lookup"><span data-stu-id="a129d-104">Each team in Microsoft Teams has a team site in SharePoint Online, and each channel in a team gets a folder within the default team site document library.</span></span> <span data-ttu-id="a129d-105">Файлы, совместно используемые во время беседы, автоматически добавляются в библиотеку документов, а заданные в SharePoint разрешения и параметры безопасности файлов автоматически переносятся в Teams.</span><span class="sxs-lookup"><span data-stu-id="a129d-105">Files shared within a conversation are automatically added to the document library, and permissions and file security options set in SharePoint are automatically reflected within Teams.</span></span>

<span data-ttu-id="a129d-106">Файлы приватного чата хранятся в папке OneDrive для бизнеса **отправителя**, а соответствующие разрешения автоматически предоставляются всем участникам в рамках процедуры общего доступа.</span><span class="sxs-lookup"><span data-stu-id="a129d-106">Private chat files are stored in the **sender’s** OneDrive for Business folder, and permissions are automatically granted to all participants as part of the file sharing process.</span></span>

<span data-ttu-id="a129d-107">Если в вашем клиенте не активировано решение SharePoint Online, пользователи Microsoft Teams не смогут обмениваться файлами в командах.</span><span class="sxs-lookup"><span data-stu-id="a129d-107">If you don't have SharePoint Online enabled in your tenant, Microsoft Teams’ users cannot always share files in teams.</span></span> <span data-ttu-id="a129d-108">Участники личных чатов также не смогут обмениваться файлами, так как для этой функции требуется OneDrive для бизнеса (что привязано к лицензии SharePoint).</span><span class="sxs-lookup"><span data-stu-id="a129d-108">Users in private chat also cannot share files because OneDrive for Business (which is tied to the SharePoint license) is required for that functionality.</span></span>

<span data-ttu-id="a129d-109">При сохранении файлов в библиотеке документов SharePoint Online и OneDrive для бизнеса выполняются все требования по обеспечению соответствия, заданные на уровне клиента.</span><span class="sxs-lookup"><span data-stu-id="a129d-109">By storing the files in the SharePoint Online document library and OneDrive for Business, all compliance rules configured at the tenant level will be followed.</span></span>

<span data-ttu-id="a129d-110">Ниже приведен пример взаимодействия между командой, каналом и библиотекой документов.</span><span class="sxs-lookup"><span data-stu-id="a129d-110">The following is the example of relationships between team, channel, and document library.</span></span>

<span data-ttu-id="a129d-111">Для каждой команды создается сайт SharePoint, а также папка по умолчанию *Общие документы*.</span><span class="sxs-lookup"><span data-stu-id="a129d-111">For every team, a SharePoint site is created, and the *Shared Documents* folder is the default folder created for the team.</span></span> <span data-ttu-id="a129d-112">Каждый канал команды, включая канал по умолчанию **Общие**, имеет свою папку внутри папки *Общие документы*.</span><span class="sxs-lookup"><span data-stu-id="a129d-112">Each channel, including the **General** channel, the default channel for each team, has a folder under the *Shared Documents* folder.</span></span>

![Схема папок "Общие документы" в SharePoint Online для команды и ее каналов в Microsoft Teams.](media/Understand_how_SharePoint_Online_and_OneDrive_for_Business_interact_with_Microsoft_Teams_image1.png)

<span data-ttu-id="a129d-114">У каждого пользователя имеется папка OneDrive *Файлы чатов Microsoft Teams* для хранения всех файлов, предоставленных для общего доступа в приватных чатах с другими пользователями (в формате один к одному или один ко многим). При этом разрешения для ограничения доступа настраиваются автоматически.</span><span class="sxs-lookup"><span data-stu-id="a129d-114">For every user, the OneDrive folder *Microsoft Teams Chat Files* is used to store all files shared within private chats with other users (1:1 or 1:many), with permissions configured automatically to restrict access to the intended user only.</span></span>

![Схема папки OneDrive с именем "Файлы чатов Microsoft Teams" для каждого из чатов пользователя.](media/Understand_how_SharePoint_Online_and_OneDrive_for_Business_interact_with_Microsoft_Teams_image2.png)
