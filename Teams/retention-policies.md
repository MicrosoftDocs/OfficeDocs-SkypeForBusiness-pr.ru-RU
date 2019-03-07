---
title: Политики хранения в группами Майкрософт
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/11/2018
ms.topic: article
ms.service: msteams
ms.reviewer: anach
description: Сведения о том, как политики хранения и управление им в группах.
localization_priority: Normal
search.appverid: MET150
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4d07629f41a54dcab1995f2aef2d7536479be25d
ms.sourcegitcommit: 85c34280977fb2c15c8a43874a20e9492bdca57f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/07/2019
ms.locfileid: "30464558"
---
# <a name="retention-policies-in-microsoft-teams"></a><span data-ttu-id="6267f-103">Политики хранения в группами Майкрософт</span><span class="sxs-lookup"><span data-stu-id="6267f-103">Retention policies in Microsoft Teams</span></span>

<span data-ttu-id="6267f-104">Команды беседы являются постоянными и удержания вечность по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="6267f-104">Teams conversations are persistent and retained forever by default.</span></span> <span data-ttu-id="6267f-105">Вследствие внедрения политики хранения администраторы могут настраивать политики хранения (хранения и удаления) в & безопасности центре соответствия требованиям для сообщений группы чата и канала.</span><span class="sxs-lookup"><span data-stu-id="6267f-105">With the introduction of retention policies, admins can configure retention policies (both preservation and deletion) in the Security & Compliance Center for Teams chat and channel messages.</span></span> <span data-ttu-id="6267f-106">Это позволяет организациям хранить сведения для соответствия требованиям (а именно, политика хранения) в течение определенного периода или избавиться от данных (а именно, политики удаления), если он будет считаться ответственности за определенный период.</span><span class="sxs-lookup"><span data-stu-id="6267f-106">This helps organizations either retain data for compliance (namely, preservation policy) for a specific period or get rid of data (namely, deletion policy) if it is considered a liability after a specific period.</span></span> <span data-ttu-id="6267f-107">Политики хранения группы убедитесь, что при удалении данных удаляется из всех места хранения постоянных данных в службе команды.</span><span class="sxs-lookup"><span data-stu-id="6267f-107">Teams retention policies ensure that when you delete data, it is removed from all permanent data storage locations on the Teams service.</span></span> 

<span data-ttu-id="6267f-108">Для управления группами политики хранения, используйте командлеты и параметры в центре соответствия требованиям в области **Управления данными**& безопасности Office 365 > **хранения**.</span><span class="sxs-lookup"><span data-stu-id="6267f-108">To manage Teams retention policies, use the settings and cmdlets in the Office 365 Security & Compliance Center under **Data Governance** > **Retention**.</span></span>

<span data-ttu-id="6267f-109">Политики хранения команды службы поддержки:</span><span class="sxs-lookup"><span data-stu-id="6267f-109">Teams retention policies do support:</span></span> 
    
- <span data-ttu-id="6267f-110">Сохранение: Сохранение данных групп в течение указанного периода времени и ничего не делать</span><span class="sxs-lookup"><span data-stu-id="6267f-110">Preservation: Keep Teams data for a specified duration and then do nothing</span></span>
- <span data-ttu-id="6267f-111">Сохранение и затем удалить: сохранение данных групп в течение указанного периода времени, а затем удалите</span><span class="sxs-lookup"><span data-stu-id="6267f-111">Preservation and then delete: Keep Teams data for a specified duration and then delete</span></span>
- <span data-ttu-id="6267f-112">Удаление: Удаление групп данных через определенное время</span><span class="sxs-lookup"><span data-stu-id="6267f-112">Deletion: Delete Teams data after a specified duration</span></span>

<span data-ttu-id="6267f-113">Политики хранения группы еще не поддерживает:</span><span class="sxs-lookup"><span data-stu-id="6267f-113">Teams retention policies do not yet support:</span></span>

- <span data-ttu-id="6267f-114">Политики хранения расширенной, не применяются к группам чата и расположения сообщение канала группы</span><span class="sxs-lookup"><span data-stu-id="6267f-114">Advanced retention policies don't apply to Teams chat and Teams channel message locations</span></span>
- <span data-ttu-id="6267f-115">Продолжительность менее 30 дней</span><span class="sxs-lookup"><span data-stu-id="6267f-115">Duration of fewer than 30 days</span></span>

<span data-ttu-id="6267f-116">«Администраторы» можно настроить политики отдельные хранения для групп закрытый беседах (1:1 или 1 этапе: возможности чаты) и группами сообщения.</span><span class="sxs-lookup"><span data-stu-id="6267f-116">Admins can set up separate retention policies for Teams private chats (1:1 or 1:Many chats) and Teams channel messages.</span></span> <span data-ttu-id="6267f-117">Во многих случаях организациям необходимо учитывать частной беседы данные в виде нескольких ответственности, чем канала сообщений, которые, как правило, более бесед, связанными с проектом.</span><span class="sxs-lookup"><span data-stu-id="6267f-117">In many cases, organizations consider private chat data as more of a liability than channel messages, which are usually more project-related conversations.</span></span> <span data-ttu-id="6267f-118">Настройка этих политик безопасности & центре соответствия требованиям **управления данными** > **хранения**.</span><span class="sxs-lookup"><span data-stu-id="6267f-118">Set up these policies in the Security & Compliance Center, **Data governance** > **Retention**.</span></span> <span data-ttu-id="6267f-119">Включите **сообщения канала команд** и **групп обсуждений** и затем определите политики хранения для этих расположения (также как показано на следующем рисунке).</span><span class="sxs-lookup"><span data-stu-id="6267f-119">Turn on **Teams channel messages** and **Teams chats** and then define retention policies for these locations (also shown in the diagram below).</span></span> 

<span data-ttu-id="6267f-120">При включении **сообщения канала команд**, можно указать группы, к которым будет применяться эта политика.</span><span class="sxs-lookup"><span data-stu-id="6267f-120">When you turn on **Teams channel messages**, you can specify Teams to which this policy will apply.</span></span> <span data-ttu-id="6267f-121">Например для групп X, Y и Z, администратор может задать политики удаления за 1 год (выбрав эти группы по отдельности) и применения политики удаления 3 года к остальной части группы.</span><span class="sxs-lookup"><span data-stu-id="6267f-121">For example, for teams X, Y, and Z, the admin can set the deletion policies for 1 year (by selecting those teams individually), and apply a 3-year deletion policy to the rest of the teams.</span></span> 

<span data-ttu-id="6267f-122">То же самое можно сделать для **групп обсуждений** , выбрав конкретных пользователей и применение политик хранения уникальных.</span><span class="sxs-lookup"><span data-stu-id="6267f-122">You can do the same thing for **Teams chats** by selecting specific users and applying unique retention policies.</span></span> 

![Схема рабочего процесса для данных Teams в Exchange и SharePoint.](media/Retention-Policies.png)


> [!IMPORTANT]
> <span data-ttu-id="6267f-124">Команды канала сообщение расположений и расположений чаты групп только устранения бесед групп, хранящиеся в почтовые ящики Exchange Online (почтовые ящики пользователей и групп).</span><span class="sxs-lookup"><span data-stu-id="6267f-124">The Teams channel message locations and Teams chats locations only address the Teams conversations stored in Exchange Online mailboxes (user and group mailboxes).</span></span> <span data-ttu-id="6267f-125">Сообщения удаляются из всех расположений соответствующих хранения, а именно почтовые ящики, подложки и служба чата.</span><span class="sxs-lookup"><span data-stu-id="6267f-125">The messages are deleted from all relevant storage locations, namely the mailboxes, substrate, and chat service.</span></span> 
> 
> <span data-ttu-id="6267f-126">Чтобы управлять политиками хранения для групп файлов, которые хранятся в OneDrive для бизнеса и SharePoint, используйте их политики хранения.</span><span class="sxs-lookup"><span data-stu-id="6267f-126">To manage retention policies for Teams files, which are stored in OneDrive for Business and SharePoint, use their retention policies.</span></span>

<span data-ttu-id="6267f-127">По умолчанию политики удаления группы файлов настраиваются через SharePoint Online и OneDrive для предприятий.</span><span class="sxs-lookup"><span data-stu-id="6267f-127">By design, deletion policies for Teams files are configured through SharePoint Online and OneDrive for Business locations.</span></span> <span data-ttu-id="6267f-128">В результате возможна, что политика может удалить файл, указанный в группы чата или канала сообщения, перед удалением получение этих сообщений.</span><span class="sxs-lookup"><span data-stu-id="6267f-128">As a result, it's possible that a policy could delete a file referenced in a Teams chat or channel message before those messages get deleted.</span></span> <span data-ttu-id="6267f-129">В этом случае файл по-прежнему будут отображаться в группы сообщений, но если щелкнуть файл, вы получите ошибку «Файл не найден» (это может также произойти при отсутствии политики, если кто-то вручную удаляет файл из SharePoint Online или OneDrive для бизнеса).</span><span class="sxs-lookup"><span data-stu-id="6267f-129">In this case, the file will still show up in the Teams message, but if you click the file, you'll get a "File not found" error (this could also happen in the absence of a policy, if someone manually deletes a file from SharePoint Online or OneDrive for Business).</span></span>

<span data-ttu-id="6267f-130">Получить подробные сведения о настройке политик хранения для Office 365 прочитайте [Обзор политик хранения](https://support.office.com/article/overview-of-retention-policies-5e377752-700d-4870-9b6d-12bfc12d2423).</span><span class="sxs-lookup"><span data-stu-id="6267f-130">For detailed information about configuring retention policies for Office 365, read [Overview of retention policies](https://support.office.com/article/overview-of-retention-policies-5e377752-700d-4870-9b6d-12bfc12d2423).</span></span>
 
