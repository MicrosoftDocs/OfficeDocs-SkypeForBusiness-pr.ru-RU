---
title: Область поиска в каталоге Microsoft Teams
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.date: 06/21/2019
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: sbhatta
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
description: Узнайте, как использовать поиск по каталогу на сайте Microsoft Teams для предоставления настраиваемых представлений каталога.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: e4f478bba8c396f0f20b95f69f56c2ded556224d
ms.sourcegitcommit: 2300595db7779da7a127ae9ee16e474452df02d3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/07/2021
ms.locfileid: "49779933"
---
# <a name="use-microsoft-teams-scoped-directory-search"></a><span data-ttu-id="101c6-103">Область поиска в каталоге Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="101c6-103">Use Microsoft Teams scoped directory search</span></span>

<span data-ttu-id="101c6-104">Поиск в каталоге Microsoft Teams позволяет организациям создавать виртуальные границы, которые контролируют возможность поиска пользователей и общения с другими пользователями в организации.</span><span class="sxs-lookup"><span data-stu-id="101c6-104">Microsoft Teams scoped directory search allows organizations to create virtual boundaries that control how users can find and communicate with other users in their organization.</span></span> 

<span data-ttu-id="101c6-105">Microsoft Teams позволяет организациям предоставлять пользователям настраиваемые представления каталога.</span><span class="sxs-lookup"><span data-stu-id="101c6-105">Microsoft Teams lets organizations provide custom views of the directory to their users.</span></span> <span data-ttu-id="101c6-106">Microsoft Teams использует [политики информационного барьера](https://docs.microsoft.com/microsoft-365/compliance/information-barriers) для поддержки настраиваемого представления.</span><span class="sxs-lookup"><span data-stu-id="101c6-106">Microsoft Teams uses [Information Barrier policies](https://docs.microsoft.com/microsoft-365/compliance/information-barriers) to support these custom views.</span></span> <span data-ttu-id="101c6-107">После включения политик результаты поиска других пользователей (например, для начала чата или добавления участников в команду) будут масштабироваться в соответствии с настроенными политиками.</span><span class="sxs-lookup"><span data-stu-id="101c6-107">Once the policies are enabled, the results returned by searches for other users (for example, to initiate a chat or to add members to a team) will be scoped according to the configured policies.</span></span> <span data-ttu-id="101c6-108">Пользователи не смогут искать группы, если в них действует область поиска.</span><span class="sxs-lookup"><span data-stu-id="101c6-108">Users will not be able to search or discover teams when scoped search is in effect.</span></span> 

> [!NOTE]
> <span data-ttu-id="101c6-109">В гибридных средах Exchange эта функция работает только с почтовыми ящиками Exchange Online, а не с локальной.</span><span class="sxs-lookup"><span data-stu-id="101c6-109">In Exchange hybrid environments, this feature only works with Exchange Online mailboxes, and not with on-premises mailboxes.</span></span>

## <a name="when-should-you-use-scoped-directory-searches"></a><span data-ttu-id="101c6-110">Когда следует использовать поиск по каталогам с областью действия?</span><span class="sxs-lookup"><span data-stu-id="101c6-110">When should you use scoped directory searches?</span></span>

<span data-ttu-id="101c6-111">Сценарии, которые могут быть преимуществами поиска по объему каталогов, похожи на сценарии политики адресной книги.</span><span class="sxs-lookup"><span data-stu-id="101c6-111">Scenarios that benefit from scoped directory searches are similar to address book policy scenarios.</span></span> <span data-ttu-id="101c6-112">Например, вы можете использовать поиск с областью поиска по каталогу в следующих ситуациях:</span><span class="sxs-lookup"><span data-stu-id="101c6-112">For example, you may want to use scoped directory search in the following situations:</span></span>

- <span data-ttu-id="101c6-113">В рамках клиента организации существует множество компаний, которые должны быть независимы друг от друга.</span><span class="sxs-lookup"><span data-stu-id="101c6-113">Your organization has multiple companies within its tenant that you want to keep separate.</span></span> 
- <span data-ttu-id="101c6-114">В учебном заведении требуется ограничить возможности общения преподавателей с учащимися в чатах.</span><span class="sxs-lookup"><span data-stu-id="101c6-114">Your school wants to limit chats between faculty and students.</span></span> 
 
<span data-ttu-id="101c6-115">Чтобы узнать, как использовать политики адресной книги, ознакомьтесь с политиками [информационного барьера в Exchange Online.](https://docs.microsoft.com/microsoft-365/compliance/information-barriers)</span><span class="sxs-lookup"><span data-stu-id="101c6-115">To learn how to use address book policies, read [Information Barrier policies in Exchange Online](https://docs.microsoft.com/microsoft-365/compliance/information-barriers).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="101c6-116">Политики адресной книги обеспечивают виртуальное разделение пользователей с точки зрения каталогов.</span><span class="sxs-lookup"><span data-stu-id="101c6-116">Address book policies provide only a virtual separation of users from directory perspective.</span></span> <span data-ttu-id="101c6-117">Кроме того, важно отметить, что все пользовательские данные, которые уже были кэшировали до того, как новые или обновленные политики адресной книги были обновлены, останутся доступными пользователям в течение 30 дней.</span><span class="sxs-lookup"><span data-stu-id="101c6-117">It is also important to note that any user data that had already been cached, prior to the enforcement of new or updated address book policies, will remain available to users for up to 30 days.</span></span>

## <a name="turn-on-scoped-directory-search"></a><span data-ttu-id="101c6-118">Включить поиск по каталогу</span><span class="sxs-lookup"><span data-stu-id="101c6-118">Turn on scoped directory search</span></span>

1. <span data-ttu-id="101c6-119">Используйте политики информационного барьера для настройки организации в виртуальных подгруппах.</span><span class="sxs-lookup"><span data-stu-id="101c6-119">Use Information Barrier policies to configure your organization into virtual subgroups.</span></span> <span data-ttu-id="101c6-120">Дополнительные сведения см. в [теме "Определение политик информационного барьера".](https://docs.microsoft.com/microsoft-365/compliance/information-barriers-policies)</span><span class="sxs-lookup"><span data-stu-id="101c6-120">For more information, see [Define Information Barrier policies](https://docs.microsoft.com/microsoft-365/compliance/information-barriers-policies).</span></span>

2. <span data-ttu-id="101c6-121">В Центре администрирования Microsoft Teams выберите параметры Teams для всей  >  **организации.**</span><span class="sxs-lookup"><span data-stu-id="101c6-121">In the Microsoft Teams admin center, select **Org-wide settings** > **Teams settings**.</span></span>

3. <span data-ttu-id="101c6-122">В **поле "Поиск"** рядом с полем "Область поиска по каталогу" в Teams с помощью политики адресной книги **Exchange (ABP)** включите **этот выключаель.**</span><span class="sxs-lookup"><span data-stu-id="101c6-122">Under **Search**, next to **Scope directory search in Teams using an Exchange address book policy (ABP)**, turn the toggle **On**.</span></span>

    ![Поиск по каталогам в Центре администрирования Microsoft Teams](media/teams-scoped-directory-search-image1.png)


> [!IMPORTANT]
> <span data-ttu-id="101c6-124">Репликация этого изменения может занять несколько часов.</span><span class="sxs-lookup"><span data-stu-id="101c6-124">This change can take a few hours to replicate.</span></span>
