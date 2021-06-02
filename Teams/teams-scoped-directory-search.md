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
description: Узнайте, как Microsoft Teams поиска по каталогу с областью действия для предоставления настраиваемых представлений каталога.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: 1048b6451163cd7b0cdbcd3f52e48c6b0f4811d1
ms.sourcegitcommit: 90615674e9703aa5ea32be64ab3638aa30e83127
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/02/2021
ms.locfileid: "52717800"
---
# <a name="use-microsoft-teams-scoped-directory-search"></a><span data-ttu-id="ddacc-103">Область поиска в каталоге Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="ddacc-103">Use Microsoft Teams scoped directory search</span></span>

<span data-ttu-id="ddacc-104">Microsoft Teams поиска по каталогам позволяет организациям создавать виртуальные границы, которые позволяют пользователям находить других пользователей и общаться с ними.</span><span class="sxs-lookup"><span data-stu-id="ddacc-104">Microsoft Teams scoped directory search allows organizations to create virtual boundaries that control how users can find and communicate with other users in their organization.</span></span> 

<span data-ttu-id="ddacc-105">Microsoft Teams позволяет организациям предоставлять пользователям настраиваемые представления каталога.</span><span class="sxs-lookup"><span data-stu-id="ddacc-105">Microsoft Teams lets organizations provide custom views of the directory to their users.</span></span> <span data-ttu-id="ddacc-106">Microsoft Teams эти [настраиваемые представления поддерживаются политиками](/microsoft-365/compliance/information-barriers) информационного барьера.</span><span class="sxs-lookup"><span data-stu-id="ddacc-106">Microsoft Teams uses [Information Barrier policies](/microsoft-365/compliance/information-barriers) to support these custom views.</span></span> <span data-ttu-id="ddacc-107">После включения политик результаты поиска других пользователей (например, для начала чата или добавления участников в команду) будут отключаться в соответствии с настроенными политиками.</span><span class="sxs-lookup"><span data-stu-id="ddacc-107">Once the policies are enabled, the results returned by searches for other users (for example, to initiate a chat or to add members to a team) will be scoped according to the configured policies.</span></span> <span data-ttu-id="ddacc-108">Пользователи не смогут искать и искать какие-либо команды, когда действует область поиска, но существующие участники в этих командах могут добавлять пользователей, что разрешено активными политиками информационного барьера.</span><span class="sxs-lookup"><span data-stu-id="ddacc-108">Users will not be able to search or discover any teams when scoped search is in effect, but existing members in those teams can add users, as allowed by active Information Barrier policies.</span></span>

> [!NOTE]
> <span data-ttu-id="ddacc-109">В Exchange гибридных средах эта функция работает только с Exchange Online почтовыми ящиками, а не с локальной.</span><span class="sxs-lookup"><span data-stu-id="ddacc-109">In Exchange hybrid environments, this feature only works with Exchange Online mailboxes, and not with on-premises mailboxes.</span></span>

<span data-ttu-id="ddacc-110">См. также политики адресной книги [в Exchange Online.](https://docs.microsoft.com/exchange/address-books/address-book-policies/address-book-policies)</span><span class="sxs-lookup"><span data-stu-id="ddacc-110">See also [Address book policies in Exchange Online](https://docs.microsoft.com/exchange/address-books/address-book-policies/address-book-policies).</span></span>

## <a name="when-should-you-use-scoped-directory-searches"></a><span data-ttu-id="ddacc-111">Когда следует использовать поиск по каталогу с областью действия?</span><span class="sxs-lookup"><span data-stu-id="ddacc-111">When should you use scoped directory searches?</span></span>

<span data-ttu-id="ddacc-112">Сценарии, которые извлекали выгоду из поиска по области каталогов, похожи на сценарии политики адресной книги.</span><span class="sxs-lookup"><span data-stu-id="ddacc-112">Scenarios that benefit from scoped directory searches are similar to address book policy scenarios.</span></span> <span data-ttu-id="ddacc-113">Например, вы можете использовать поиск по каталогу с областью поиска в следующих ситуациях:</span><span class="sxs-lookup"><span data-stu-id="ddacc-113">For example, you may want to use scoped directory search in the following situations:</span></span>

- <span data-ttu-id="ddacc-114">В рамках клиента организации существует множество компаний, которые должны быть независимы друг от друга.</span><span class="sxs-lookup"><span data-stu-id="ddacc-114">Your organization has multiple companies within its tenant that you want to keep separate.</span></span> 
- <span data-ttu-id="ddacc-115">В учебном заведении требуется ограничить возможности общения преподавателей с учащимися в чатах.</span><span class="sxs-lookup"><span data-stu-id="ddacc-115">Your school wants to limit chats between faculty and students.</span></span> 
 
<span data-ttu-id="ddacc-116">Сведения о том, как использовать политики адресной книги, можно найти в [Exchange Online.](/microsoft-365/compliance/information-barriers)</span><span class="sxs-lookup"><span data-stu-id="ddacc-116">To learn how to use address book policies, read [Information Barrier policies in Exchange Online](/microsoft-365/compliance/information-barriers).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ddacc-117">Политики адресной книги обеспечивают виртуальное разделение пользователей с точки зрения каталога.</span><span class="sxs-lookup"><span data-stu-id="ddacc-117">Address book policies provide only a virtual separation of users from directory perspective.</span></span> <span data-ttu-id="ddacc-118">Кроме того, важно отметить, что все данные пользователей, которые уже были кэшировали до того, как новые или обновленные политики адресной книги были обновлены, будут доступны пользователям в течение 30 дней.</span><span class="sxs-lookup"><span data-stu-id="ddacc-118">It is also important to note that any user data that had already been cached, prior to the enforcement of new or updated address book policies, will remain available to users for up to 30 days.</span></span>

## <a name="turn-on-scoped-directory-search"></a><span data-ttu-id="ddacc-119">Включить поиск по каталогу с областью действия</span><span class="sxs-lookup"><span data-stu-id="ddacc-119">Turn on scoped directory search</span></span>

1. <span data-ttu-id="ddacc-120">Используйте политики информационных барьеров для настройки организации в виртуальных подгруппах.</span><span class="sxs-lookup"><span data-stu-id="ddacc-120">Use Information Barrier policies to configure your organization into virtual subgroups.</span></span> <span data-ttu-id="ddacc-121">Дополнительные сведения см. в [теме Определение политик информационных барьеров.](/microsoft-365/compliance/information-barriers-policies)</span><span class="sxs-lookup"><span data-stu-id="ddacc-121">For more information, see [Define Information Barrier policies](/microsoft-365/compliance/information-barriers-policies).</span></span>

2. <span data-ttu-id="ddacc-122">В Центре Microsoft Teams администрирования **выберите** Параметры для всей организации Teams  >  **параметры**.</span><span class="sxs-lookup"><span data-stu-id="ddacc-122">In the Microsoft Teams admin center, select **Org-wide settings** > **Teams settings**.</span></span>

3. <span data-ttu-id="ddacc-123">В **поле** Поиск рядом с полем Поиск по каталогу Teams с помощью Exchange адресной книги **(ABP)** включите **выключаель**.</span><span class="sxs-lookup"><span data-stu-id="ddacc-123">Under **Search**, next to **Scope directory search in Teams using an Exchange address book policy (ABP)**, turn the toggle **On**.</span></span>

    ![Поиск по области каталогов в Microsoft Teams центре администрирования](media/teams-scoped-directory-search-image1.png)


> [!IMPORTANT]
> <span data-ttu-id="ddacc-125">Репликация этого изменения может занять несколько часов.</span><span class="sxs-lookup"><span data-stu-id="ddacc-125">This change can take a few hours to replicate.</span></span>
