---
title: Обнаружение электронных данных в Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
ms.reviewer: anach
description: Сведения о том, когда требуется обнаружение электронных данных, например при передаче всей информации, хранящейся в электронной форме, для судебных разбирательств.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 02efc096362c194d580edc259f9afa5c65fd1cda
ms.sourcegitcommit: 33966ebb9ca3d922d47aaa9b9e3a2ddd26c320ca
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/06/2018
ms.locfileid: "23843711"
---
<a name="conduct-an-ediscovery-investigation-of-content-in-microsoft-teams"></a><span data-ttu-id="5a322-103">Обнаружение электронных данных в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="5a322-103">Conduct an eDiscovery investigation of content in Microsoft Teams</span></span>
============================

<span data-ttu-id="5a322-104">Крупные предприятия часто участвуют в судебных разбирательствах, в рамках которых требуется предоставить всю информацию, хранящуюся в электронной форме.</span><span class="sxs-lookup"><span data-stu-id="5a322-104">Large Enterprises are often exposed to high penalty legal proceedings which demand submission of all Electronically Stored Information (ESI).</span></span>

<span data-ttu-id="5a322-105">Все индивидуальные или групповые чаты в Teams собираются через почтовые ящики пользователей, а все сообщения в каналах — через почтовый ящик группы, представляющий соответствующую команду.</span><span class="sxs-lookup"><span data-stu-id="5a322-105">All Teams 1:1 or group chats are journaled through to the respective users’ mailboxes and all channel messages are journaled through to the group mailbox representing the Team.</span></span> <span data-ttu-id="5a322-106">Отправленные файлы собираются с помощью функций по обнаружению электронных данных в SharePoint Online и OneDrive для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="5a322-106">Files uploaded are covered under the eDiscovery functionality for SharePoint Online and OneDrive for Business.</span></span>

1.  <span data-ttu-id="5a322-107">Для проведения расследования обнаружения электронных данных с содержимым группами Майкрософт, просмотрите шаг 1 в [эту](https://support.office.com/article/Manage-eDiscovery-cases-in-the-Office-365-Security-Compliance-Center-edea80d6-20a7-40fb-b8c4-5e8c8395f6da) ссылку.</span><span class="sxs-lookup"><span data-stu-id="5a322-107">To conduct an eDiscovery investigation with Microsoft Teams content, review step 1 in [this](https://support.office.com/article/Manage-eDiscovery-cases-in-the-Office-365-Security-Compliance-Center-edea80d6-20a7-40fb-b8c4-5e8c8395f6da) link.</span></span>

2.  <span data-ttu-id="5a322-108">В выходных данных Excel сведения Microsoft Teams отображаются в виде **мгновенных сообщений или бесед**, кроме того, можно подключить **PST-файл** в Outlook.</span><span class="sxs-lookup"><span data-stu-id="5a322-108">Microsoft Teams data will appear as **IM or Conversations** in the Excel output, or you can mount the **.PST** in Outlook.</span></span>

    <span data-ttu-id="5a322-109">а.</span><span class="sxs-lookup"><span data-stu-id="5a322-109">a.</span></span>  <span data-ttu-id="5a322-110">При подключении PST-файла для команды обратите внимание, что все беседы хранятся в папке "Чат группы" журнала бесед.</span><span class="sxs-lookup"><span data-stu-id="5a322-110">When mounting the .PST for the Team, note that all conversations are kept in the Team Chat folder under Conversation History.</span></span> <span data-ttu-id="5a322-111">Заголовок сообщения содержит команду и канал.</span><span class="sxs-lookup"><span data-stu-id="5a322-111">The title of the message aligns to Team and Channel.</span></span> <span data-ttu-id="5a322-112">На изображении ниже вы можете видеть, что пользователь Bob отправил сообщение в канал "Project 7" команды "Manufacturing Specs".</span><span class="sxs-lookup"><span data-stu-id="5a322-112">From reviewing the image below, you can see this message from Bob who messaged the Project 7 channel of the Manufacturing Specs team.</span></span>
<span data-ttu-id="5a322-113">![Снимок экрана с папкой "Чат группы" в почтовом ящике пользователя в Outlook.](media/Conduct_an_eDiscovery_investigation_of_content_in_Microsoft_Teams_image1.png)</span><span class="sxs-lookup"><span data-stu-id="5a322-113">![Screenshot of a Team Chat folder in a user's mailbox in Outlook.](media/Conduct_an_eDiscovery_investigation_of_content_in_Microsoft_Teams_image1.png)</span></span>

3.  <span data-ttu-id="5a322-114">Чтобы приватные чаты можно было просмотреть в почтовом ящике пользователя, они также размещаются в папке "Чат группы" журнала бесед.</span><span class="sxs-lookup"><span data-stu-id="5a322-114">To see private chats in a user’s Mailbox, they are also located inside the Team Chat folder under Conversation History.</span></span>
