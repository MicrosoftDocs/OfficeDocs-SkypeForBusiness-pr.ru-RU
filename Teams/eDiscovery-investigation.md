---
title: Обнаружение электронных данных в Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/12/2018
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
ms.reviewer: anach
search.appverid: MET150
description: Сведения о том, когда требуется обнаружение электронных данных, например при передаче всей информации, хранящейся в электронной форме, для судебных разбирательств.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 42a9f9cc011d050e540eef3ff87d9cd839cc2819
ms.sourcegitcommit: 0dcd078947a455a388729fd50c7a939dd93b0b61
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2019
ms.locfileid: "37564034"
---
<a name="conduct-an-ediscovery-investigation-of-content-in-microsoft-teams"></a><span data-ttu-id="175ea-103">Обнаружение электронных данных в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="175ea-103">Conduct an eDiscovery investigation of content in Microsoft Teams</span></span>
============================

<span data-ttu-id="175ea-104">Крупные предприятия часто открываются в юридическом лице процессы, требующем отправки всей информации, хранящейся в электронном виде (еси).</span><span class="sxs-lookup"><span data-stu-id="175ea-104">Large Enterprises are often exposed to high penalty legal proceedings that demand submission of all Electronically Stored Information (ESI).</span></span>

<span data-ttu-id="175ea-105">Все команды 1:1 и групповые разговоры записываются в почтовые ящики соответствующих пользователей, и все сообщения каналов записываются в почтовый ящик группы, который представляет группу.</span><span class="sxs-lookup"><span data-stu-id="175ea-105">All Teams 1:1 or group chats are journaled through to the respective users’ mailboxes, and all channel messages are journaled through to the group mailbox representing the team.</span></span> <span data-ttu-id="175ea-106">Отправленные файлы собираются с помощью функций по обнаружению электронных данных в SharePoint Online и OneDrive для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="175ea-106">Files uploaded are covered under the eDiscovery functionality for SharePoint Online and OneDrive for Business.</span></span>

1.  <span data-ttu-id="175ea-107">Чтобы провести исследование обнаружения электронных данных с содержимым Microsoft Teams, ознакомьтесь с шагом 1 в [этой](https://support.office.com/article/Manage-eDiscovery-cases-in-the-Office-365-Security-Compliance-Center-edea80d6-20a7-40fb-b8c4-5e8c8395f6da) ссылке.</span><span class="sxs-lookup"><span data-stu-id="175ea-107">To conduct an eDiscovery investigation with Microsoft Teams content, review step 1 in [this](https://support.office.com/article/Manage-eDiscovery-cases-in-the-Office-365-Security-Compliance-Center-edea80d6-20a7-40fb-b8c4-5e8c8395f6da) link.</span></span>

2.  <span data-ttu-id="175ea-108">Данные Microsoft Teams будут отображаться в виде мгновенных сообщений или бесед в выходных данных экспорта eDiscovery Excel, и вы можете подключить. PST-файл в Outlook, чтобы просмотреть эти сообщения после экспорта.</span><span class="sxs-lookup"><span data-stu-id="175ea-108">Microsoft Teams data will appear as IM or Conversations in the Excel eDiscovery export output, and you can mount the .PST in Outlook to view those messages post export.</span></span>

    <span data-ttu-id="175ea-109">При подключении PST-файла для команды обратите внимание, что все беседы хранятся в папке "Чат группы" журнала бесед.</span><span class="sxs-lookup"><span data-stu-id="175ea-109">When mounting the .PST for the Team, note that all conversations are kept in the Team Chat folder under Conversation History.</span></span> <span data-ttu-id="175ea-110">Заголовок сообщения содержит команду и канал.</span><span class="sxs-lookup"><span data-stu-id="175ea-110">The title of the message aligns to Team and Channel.</span></span> <span data-ttu-id="175ea-111">На изображении ниже вы можете видеть, что пользователь Bob отправил сообщение в канал "Project 7" команды "Manufacturing Specs".</span><span class="sxs-lookup"><span data-stu-id="175ea-111">From reviewing the image below, you can see this message from Bob who messaged the Project 7 channel of the Manufacturing Specs team.</span></span>

    ![Снимок экрана: папка чата команды в почтовом ящике пользователя в Outlook](media/Conduct_an_eDiscovery_investigation_of_content_in_Microsoft_Teams_image1.png)

3.  <span data-ttu-id="175ea-113">Чтобы приватные чаты можно было просмотреть в почтовом ящике пользователя, они также размещаются в папке "Чат группы" журнала бесед.</span><span class="sxs-lookup"><span data-stu-id="175ea-113">To see private chats in a user’s Mailbox, they are also located inside the Team Chat folder under Conversation History.</span></span>

## <a name="ediscovery-of-guest-to-guest-chats"></a><span data-ttu-id="175ea-114">Обнаружение электронных чатов "гость – гость"</span><span class="sxs-lookup"><span data-stu-id="175ea-114">eDiscovery of guest-to-guest chats</span></span>

<span data-ttu-id="175ea-115">Без почтового ящика (например, если в 1xN сеансы, в которых нет пользователей клиентов домашних компьютеров) не будут индексироваться, и в результате они не будут включены в eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="175ea-115">Without a mailbox, guest-to-guest chats (1xN chats in which there are no home tenant users) would not be indexed, and as a result, would not be included in eDiscovery.</span></span> <span data-ttu-id="175ea-116">Чтобы облегчить обнаружение электронных данных для гостевых чатов, создается почтовый ящик на основе облака (или фиктивный почтовый ящик), в котором хранятся данные 1xN.</span><span class="sxs-lookup"><span data-stu-id="175ea-116">To facilitate eDiscovery for guest-to-guest chats, a cloud-based mailbox (or phantom mailbox) is created to store the 1xN data.</span></span> <span data-ttu-id="175ea-117">После того как данные чата в Teams будут сохранены в облачном почтовом ящике, она индексируется для поиска в электронных данных и для соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="175ea-117">After the Teams chat data is stored in the cloud-based mailbox, it is indexed for eDiscovery and compliance content search.</span></span>

<span data-ttu-id="175ea-118">На приведенном ниже рисунке показано, как обнаружение электронных данных работает для гостевых чатов, в которых нет почтового ящика.</span><span class="sxs-lookup"><span data-stu-id="175ea-118">The following illustration shows how eDiscovery works for guest-to-guest chats in which there isn’t a mailbox.</span></span>

![Гостевая — разговоры в чате-без почтового ящика](media/conduct-an-ediscovery-investigation-of-content-in-microsoft-teams-image2.png)
