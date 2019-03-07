---
title: Обнаружение электронных данных в Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/12/2018
ms.topic: article
ms.service: msteams
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
ms.reviewer: anach
search.appverid: MET150
description: Сведения о том, когда требуется обнаружение электронных данных, например при передаче всей информации, хранящейся в электронной форме, для судебных разбирательств.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 54ccb21e33c6acc1747023fc7c3eb174040d5746
ms.sourcegitcommit: 85c34280977fb2c15c8a43874a20e9492bdca57f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/07/2019
ms.locfileid: "30461806"
---
<a name="conduct-an-ediscovery-investigation-of-content-in-microsoft-teams"></a><span data-ttu-id="2d94e-103">Обнаружение электронных данных в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="2d94e-103">Conduct an eDiscovery investigation of content in Microsoft Teams</span></span>
============================

<span data-ttu-id="2d94e-104">Крупным предприятиям часто предоставляются для судебного разбирательства высокой производительности, которые требуют отправки из всех электронном виде хранятся сведения о помощью.</span><span class="sxs-lookup"><span data-stu-id="2d94e-104">Large Enterprises are often exposed to high penalty legal proceedings that demand submission of all Electronically Stored Information (ESI).</span></span>

<span data-ttu-id="2d94e-105">Все группы 1:1 или групповой беседы не регистрировать через к почтовым ящикам пользователей, а все сообщения регистрировать через почтовый ящик группы, представляющий группу.</span><span class="sxs-lookup"><span data-stu-id="2d94e-105">All Teams 1:1 or group chats are journaled through to the respective users’ mailboxes, and all channel messages are journaled through to the group mailbox representing the team.</span></span> <span data-ttu-id="2d94e-106">Отправленные файлы собираются с помощью функций по обнаружению электронных данных в SharePoint Online и OneDrive для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="2d94e-106">Files uploaded are covered under the eDiscovery functionality for SharePoint Online and OneDrive for Business.</span></span>

1.  <span data-ttu-id="2d94e-107">Для проведения расследования обнаружения электронных данных с содержимым группами Майкрософт, просмотрите шаг 1 в [эту](https://support.office.com/article/Manage-eDiscovery-cases-in-the-Office-365-Security-Compliance-Center-edea80d6-20a7-40fb-b8c4-5e8c8395f6da) ссылку.</span><span class="sxs-lookup"><span data-stu-id="2d94e-107">To conduct an eDiscovery investigation with Microsoft Teams content, review step 1 in [this](https://support.office.com/article/Manage-eDiscovery-cases-in-the-Office-365-Security-Compliance-Center-edea80d6-20a7-40fb-b8c4-5e8c8395f6da) link.</span></span>

2.  <span data-ttu-id="2d94e-108">Группами Майкрософт данные отображаются как обмен мгновенными Сообщениями или бесед в обнаружении электронных данных Excel экспорт выходные данные и можно подключить. PST-файлов в Outlook для просмотра этих сообщений отправлять сообщения экспорт.</span><span class="sxs-lookup"><span data-stu-id="2d94e-108">Microsoft Teams data will appear as IM or Conversations in the Excel eDiscovery export output, and you can mount the .PST in Outlook to view those messages post export.</span></span>

    <span data-ttu-id="2d94e-109">При подключении PST-файла для команды обратите внимание, что все беседы хранятся в папке "Чат группы" журнала бесед.</span><span class="sxs-lookup"><span data-stu-id="2d94e-109">When mounting the .PST for the Team, note that all conversations are kept in the Team Chat folder under Conversation History.</span></span> <span data-ttu-id="2d94e-110">Заголовок сообщения содержит команду и канал.</span><span class="sxs-lookup"><span data-stu-id="2d94e-110">The title of the message aligns to Team and Channel.</span></span> <span data-ttu-id="2d94e-111">На изображении ниже вы можете видеть, что пользователь Bob отправил сообщение в канал "Project 7" команды "Manufacturing Specs".</span><span class="sxs-lookup"><span data-stu-id="2d94e-111">From reviewing the image below, you can see this message from Bob who messaged the Project 7 channel of the Manufacturing Specs team.</span></span>

    ![Снимок экрана с группы чата папки в почтовом ящике пользователя в Outlook](media/Conduct_an_eDiscovery_investigation_of_content_in_Microsoft_Teams_image1.png)

3.  <span data-ttu-id="2d94e-113">Чтобы приватные чаты можно было просмотреть в почтовом ящике пользователя, они также размещаются в папке "Чат группы" журнала бесед.</span><span class="sxs-lookup"><span data-stu-id="2d94e-113">To see private chats in a user’s Mailbox, they are also located inside the Team Chat folder under Conversation History.</span></span>

## <a name="ediscovery-of-guest-to-guest-chats"></a><span data-ttu-id="2d94e-114">обнаружение электронных данных гостевая гостевой бесед</span><span class="sxs-lookup"><span data-stu-id="2d94e-114">eDiscovery of guest-to-guest chats</span></span>

<span data-ttu-id="2d94e-115">Без почтового ящика обсуждений гостевая Гость (1xN бесед, в которых нет пользователей Домашняя страница клиента) не будет индексироваться и поэтому не будет включен в обнаружении электронных данных.</span><span class="sxs-lookup"><span data-stu-id="2d94e-115">Without a mailbox, guest-to-guest chats (1xN chats in which there are no home tenant users) would not be indexed, and as a result, would not be included in eDiscovery.</span></span> <span data-ttu-id="2d94e-116">Для упрощения обнаружения электронных данных для чаты гостя и виртуальных облачного почтового ящика (или фантомных почтовых ящиков) создается для хранения данных, 1xN.</span><span class="sxs-lookup"><span data-stu-id="2d94e-116">To facilitate eDiscovery for guest-to-guest chats, a cloud-based mailbox (or phantom mailbox) is created to store the 1xN data.</span></span> <span data-ttu-id="2d94e-117">После данных чата группы хранится в облачного почтового ящика, будет индексирован для поиска контента обнаружения электронных данных и обеспечения соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="2d94e-117">After the Teams chat data is stored in the cloud-based mailbox, it is indexed for eDiscovery and compliance content search.</span></span>

<span data-ttu-id="2d94e-118">На следующем рисунке показана как eDiscovery работает для Гостевая гостевой бесед, в которых еще нет почтового ящика.</span><span class="sxs-lookup"><span data-stu-id="2d94e-118">The following illustration shows how eDiscovery works for guest-to-guest chats in which there isn’t a mailbox.</span></span>

![Guest-to-Guest-Chats-WITH-NO-Mailbox](media/conduct-an-ediscovery-investigation-of-content-in-microsoft-teams-image2.png)
