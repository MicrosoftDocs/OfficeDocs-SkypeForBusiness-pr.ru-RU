---
title: Политики хранения в Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: prvijay
description: Узнайте, как использовать политики хранения и как управлять ими в Teams.
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.openlocfilehash: 6adaee32648a6ec522098d90fd3c90ff161ef00e
ms.sourcegitcommit: ed3d7ebb193229cab9e0e5be3dc1c28c3f622c1b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41838199"
---
# <a name="retention-policies-in-microsoft-teams"></a><span data-ttu-id="71a0e-103">Политики хранения в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="71a0e-103">Retention policies in Microsoft Teams</span></span>

<span data-ttu-id="71a0e-104">Беседы по группам по умолчанию сохраняются постоянно и остаются неизменными.</span><span class="sxs-lookup"><span data-stu-id="71a0e-104">Teams conversations are persistent and retained forever by default.</span></span> <span data-ttu-id="71a0e-105">С появлением политик хранения администраторы могут настроить политики хранения (как сохранение, так и удаление) в центре безопасности & соответствия требованиям для собеседников групп и сообщений каналов.</span><span class="sxs-lookup"><span data-stu-id="71a0e-105">With the introduction of retention policies, admins can configure retention policies (both preservation and deletion) in the Security & Compliance Center for Teams chat and channel messages.</span></span> <span data-ttu-id="71a0e-106">Это позволяет организациям хранить данные для соответствия требованиям (например, политика хранения) для определенного периода или избавиться от данных (а именно, политику удаления), если она считается ответственностью за определенный период.</span><span class="sxs-lookup"><span data-stu-id="71a0e-106">This helps organizations either retain data for compliance (namely, preservation policy) for a specific period or get rid of data (namely, deletion policy) if it is considered a liability after a specific period.</span></span> <span data-ttu-id="71a0e-107">Политики хранения в Teams гарантируют, что при удалении данных они удаляются из всех областей хранения данных в службе Teams.</span><span class="sxs-lookup"><span data-stu-id="71a0e-107">Teams retention policies ensure that when you delete data, it is removed from all permanent data storage locations on the Teams service.</span></span>

> [!NOTE]
> <span data-ttu-id="71a0e-108">Мы пока не поддерживаем конфигурацию для хранения сообщений частных каналов.</span><span class="sxs-lookup"><span data-stu-id="71a0e-108">We don’t yet support configuration for retention of private channel messages.</span></span> <span data-ttu-id="71a0e-109">Поддерживается хранение файлов, общих для частных каналов.</span><span class="sxs-lookup"><span data-stu-id="71a0e-109">Retention of files shared in private channels is supported.</span></span>

<span data-ttu-id="71a0e-110">Для управления политиками хранения в Teams используйте параметры и командлеты в центре & безопасности Office 365 в разделе**Хранение** **информации** > .</span><span class="sxs-lookup"><span data-stu-id="71a0e-110">To manage Teams retention policies, use the settings and cmdlets in the Office 365 Security & Compliance Center under **Information governance** > **Retention**.</span></span>

<span data-ttu-id="71a0e-111">Поддерживаемые политики хранения teams:</span><span class="sxs-lookup"><span data-stu-id="71a0e-111">Teams retention policies do support:</span></span> 
    
- <span data-ttu-id="71a0e-112">Сохранение: хранение данных Teams за указанную длительность и не предпринимайте никаких действий</span><span class="sxs-lookup"><span data-stu-id="71a0e-112">Preservation: Keep Teams data for a specified duration and then do nothing</span></span>
- <span data-ttu-id="71a0e-113">Сохранение и удаление: хранение данных группы на указанную длительность и затем удаление</span><span class="sxs-lookup"><span data-stu-id="71a0e-113">Preservation and then delete: Keep Teams data for a specified duration and then delete</span></span>
- <span data-ttu-id="71a0e-114">Удаление: удаление данных команды после указанной длительности</span><span class="sxs-lookup"><span data-stu-id="71a0e-114">Deletion: Delete Teams data after a specified duration</span></span>

<span data-ttu-id="71a0e-115">Политики хранения в Teams пока не поддерживаются:</span><span class="sxs-lookup"><span data-stu-id="71a0e-115">Teams retention policies do not yet support:</span></span>

- <span data-ttu-id="71a0e-116">Дополнительные политики хранения не применяются к адресам чата Teams и сообщениям каналов Teams</span><span class="sxs-lookup"><span data-stu-id="71a0e-116">Advanced retention policies don't apply to Teams chat and Teams channel message locations</span></span>

<span data-ttu-id="71a0e-117">Администраторы могут настроить отдельные политики хранения для частных сеансов работы с группами (1:1 или 1: большое количество чатов) и сообщения каналов Teams.</span><span class="sxs-lookup"><span data-stu-id="71a0e-117">Admins can set up separate retention policies for Teams private chats (1:1 or 1:Many chats) and Teams channel messages.</span></span> <span data-ttu-id="71a0e-118">Во многих случаях организации считают конфиденциальные данные чата более конкретными обязательствами, чем сообщения канала, которые обычно являются более связанными с проектом обсуждениями.</span><span class="sxs-lookup"><span data-stu-id="71a0e-118">In many cases, organizations consider private chat data as more of a liability than channel messages, which are usually more project-related conversations.</span></span> <span data-ttu-id="71a0e-119">Настройте эти политики в центре безопасности & соответствия требованиям: хранение **данных** > \*\*\*\*.</span><span class="sxs-lookup"><span data-stu-id="71a0e-119">Set up these policies in the Security & Compliance Center, **Information governance** > **Retention**.</span></span> <span data-ttu-id="71a0e-120">Включите **сообщения канала групп** и **разговоры команд** , а затем определите политики хранения для этих расположений (также показано на рисунке ниже).</span><span class="sxs-lookup"><span data-stu-id="71a0e-120">Turn on **Teams channel messages** and **Teams chats** and then define retention policies for these locations (also shown in the diagram below).</span></span> 

<span data-ttu-id="71a0e-121">При включении командных **сообщений для канала**можно выбрать группы, к которым будет применяться эта политика.</span><span class="sxs-lookup"><span data-stu-id="71a0e-121">When you turn on **Teams channel messages**, you can specify Teams to which this policy will apply.</span></span> <span data-ttu-id="71a0e-122">Например, для команд X, Y и Z администратор может установить политики удаления в течение 1 года (выбирая эти группы по отдельности) и применяйте политику удаления 3 лет к другим группам.</span><span class="sxs-lookup"><span data-stu-id="71a0e-122">For example, for teams X, Y, and Z, the admin can set the deletion policies for 1 year (by selecting those teams individually), and apply a 3-year deletion policy to the rest of the teams.</span></span> 

<span data-ttu-id="71a0e-123">Вы можете сделать то же самое для **сеансов команд** , выбирая конкретных пользователей и применяя уникальные политики хранения.</span><span class="sxs-lookup"><span data-stu-id="71a0e-123">You can do the same thing for **Teams chats** by selecting specific users and applying unique retention policies.</span></span> 

![Схема рабочего процесса для данных Teams в Exchange и SharePoint.](media/Retention-Policies.png)


> [!IMPORTANT]
> <span data-ttu-id="71a0e-125">Расположение сообщений в каналах Teams и Teams в рабочих группах — это только те, которые хранятся в почтовых ящиках Exchange Online (пользователям и группам).</span><span class="sxs-lookup"><span data-stu-id="71a0e-125">The Teams channel message locations and Teams chats locations only address the Teams conversations stored in Exchange Online mailboxes (user and group mailboxes).</span></span> <span data-ttu-id="71a0e-126">Сообщения удаляются из всех подходящих местоположений хранилища, а именно — для почтового ящика, подложки и службы чата.</span><span class="sxs-lookup"><span data-stu-id="71a0e-126">The messages are deleted from all relevant storage locations, namely the mailboxes, substrate, and chat service.</span></span> 
> 
> <span data-ttu-id="71a0e-127">Чтобы управлять политиками хранения для файлов Teams, которые хранятся в OneDrive для бизнеса и SharePoint, используйте их политики хранения.</span><span class="sxs-lookup"><span data-stu-id="71a0e-127">To manage retention policies for Teams files, which are stored in OneDrive for Business and SharePoint, use their retention policies.</span></span>

<span data-ttu-id="71a0e-128">По шаблону политики удаления для файлов Teams настраиваются с помощью SharePoint Online и расположений OneDrive для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="71a0e-128">By design, deletion policies for Teams files are configured through SharePoint Online and OneDrive for Business locations.</span></span> <span data-ttu-id="71a0e-129">В результате, возможно, что политика может удалить файл, на который ссылается собеседник Teams, или сообщение канала, прежде чем эти сообщения удаляются.</span><span class="sxs-lookup"><span data-stu-id="71a0e-129">As a result, it's possible that a policy could delete a file referenced in a Teams chat or channel message before those messages get deleted.</span></span> <span data-ttu-id="71a0e-130">В этом случае файл будет по-прежнему отображаться в сообщении Teams, но если щелкнуть файл, появится сообщение об ошибке "файл не найден" (это может быть также вызвано отсутствием политики, если кто-либо вручную удаляет файл из SharePoint Online или OneDrive для бизнеса).</span><span class="sxs-lookup"><span data-stu-id="71a0e-130">In this case, the file will still show up in the Teams message, but if you click the file, you'll get a "File not found" error (this could also happen in the absence of a policy, if someone manually deletes a file from SharePoint Online or OneDrive for Business).</span></span>

<span data-ttu-id="71a0e-131">Подробные сведения о настройке политик хранения для Office 365 читайте в статье [Общие сведения о политиках хранения](https://support.office.com/article/overview-of-retention-policies-5e377752-700d-4870-9b6d-12bfc12d2423).</span><span class="sxs-lookup"><span data-stu-id="71a0e-131">For detailed information about configuring retention policies for Office 365, read [Overview of retention policies](https://support.office.com/article/overview-of-retention-policies-5e377752-700d-4870-9b6d-12bfc12d2423).</span></span>
 
