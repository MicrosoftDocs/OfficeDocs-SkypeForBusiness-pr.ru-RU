---
title: Область поиска в каталоге Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
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
description: Сведения о том, как использовать поиск в каталоге с областью Microsoft Teams для создания настраиваемых представлений каталога.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: 6b06e675e93dd022847fc7af202045c3ecdebe63
ms.sourcegitcommit: 6cfaadec5782ca7316db36472bd0be20217da693
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/29/2020
ms.locfileid: "42341770"
---
# <a name="use-microsoft-teams-scoped-directory-search"></a><span data-ttu-id="66aa5-103">Область поиска в каталоге Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="66aa5-103">Use Microsoft Teams scoped directory search</span></span>

<span data-ttu-id="66aa5-104">Microsoft Teams Search для каталогов позволяет организациям создавать виртуальные границы, которые определяют, как пользователи могут находить и взаимодействовать с другими пользователями в своей организации.</span><span class="sxs-lookup"><span data-stu-id="66aa5-104">Microsoft Teams scoped directory search allows organizations to create virtual boundaries that control how users can find and communicate with other users in their organization.</span></span> 

<span data-ttu-id="66aa5-105">Microsoft Teams позволяет организациям предоставлять своим пользователям пользовательские представления каталога.</span><span class="sxs-lookup"><span data-stu-id="66aa5-105">Microsoft Teams lets organizations provide custom views of the directory to their users.</span></span> <span data-ttu-id="66aa5-106">Для поддержки этих настраиваемых представлений в Microsoft Teams используются [политики барьера данных](https://docs.microsoft.com/microsoft-365/compliance/information-barriers) .</span><span class="sxs-lookup"><span data-stu-id="66aa5-106">Microsoft Teams uses [Information Barrier policies](https://docs.microsoft.com/microsoft-365/compliance/information-barriers) to support these custom views.</span></span> <span data-ttu-id="66aa5-107">После включения политик результаты поиска других пользователей (например, для инициирования чата или добавления участников в группу) будут ограничены в соответствии с настроенными политиками.</span><span class="sxs-lookup"><span data-stu-id="66aa5-107">Once the policies are enabled, the results returned by searches for other users (for example, to initiate a chat or to add members to a team) will be scoped according to the configured policies.</span></span> <span data-ttu-id="66aa5-108">Пользователи не смогут искать и находить группы, когда действует область поиска.</span><span class="sxs-lookup"><span data-stu-id="66aa5-108">Users will not be able to search or discover teams when scoped search is in effect.</span></span> 

> [!NOTE]
> <span data-ttu-id="66aa5-109">В гибридных средах Exchange Эта функция работает только с почтовыми ящиками Exchange Online, а не с локальными почтовыми ящиками.</span><span class="sxs-lookup"><span data-stu-id="66aa5-109">In Exchange hybrid environments, this feature only works with Exchange Online mailboxes, and not with on-premises mailboxes.</span></span>

## <a name="when-should-you-use-scoped-directory-searches"></a><span data-ttu-id="66aa5-110">Когда следует использовать поиск в каталоге с областью?</span><span class="sxs-lookup"><span data-stu-id="66aa5-110">When should you use scoped directory searches?</span></span>

<span data-ttu-id="66aa5-111">Сценарии, выигрывающие от поиска в каталогах, похожи на сценарии политики адресной книги.</span><span class="sxs-lookup"><span data-stu-id="66aa5-111">Scenarios that benefit from scoped directory searches are similar to address book policy scenarios.</span></span> <span data-ttu-id="66aa5-112">Например, вы можете использовать поиск по каталогу в следующих ситуациях:</span><span class="sxs-lookup"><span data-stu-id="66aa5-112">For example, you may want to use scoped directory search in the following situations:</span></span>

- <span data-ttu-id="66aa5-113">В рамках клиента организации существует множество компаний, которые должны быть независимы друг от друга.</span><span class="sxs-lookup"><span data-stu-id="66aa5-113">Your organization has multiple companies within its tenant that you want to keep separate.</span></span> 
- <span data-ttu-id="66aa5-114">В учебном заведении требуется ограничить возможности общения преподавателей с учащимися в чатах.</span><span class="sxs-lookup"><span data-stu-id="66aa5-114">Your school wants to limit chats between faculty and students.</span></span> 
 
<span data-ttu-id="66aa5-115">Чтобы узнать, как использовать политики адресной книги, прочтите [политики барьера информации в Exchange Online](https://docs.microsoft.com/microsoft-365/compliance/information-barriers).</span><span class="sxs-lookup"><span data-stu-id="66aa5-115">To learn how to use address book policies, read [Information Barrier policies in Exchange Online](https://docs.microsoft.com/microsoft-365/compliance/information-barriers).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="66aa5-116">Политики адресной книги предоставляют только виртуальное разделение пользователей с точки зрения службы каталогов.</span><span class="sxs-lookup"><span data-stu-id="66aa5-116">Address book policies provide only a virtual separation of users from directory perspective.</span></span> <span data-ttu-id="66aa5-117">Пользователи по-прежнему могут начать общение с другими пользователями, предоставив полные адреса электронной почты.</span><span class="sxs-lookup"><span data-stu-id="66aa5-117">Users can still initiate communications with others by providing complete email addresses.</span></span> <span data-ttu-id="66aa5-118">Кроме того, обратите внимание на то, что все данные пользователя, которые уже были кэшированы, до принудительного применения новых или обновленных политик адресных книг будут доступны пользователям в течение 30 дней.</span><span class="sxs-lookup"><span data-stu-id="66aa5-118">It is also important to note that any user data that had already been cached, prior to the enforcement of new or updated address book policies, will remain available to users for up to 30 days.</span></span>

## <a name="turn-on-scoped-directory-search"></a><span data-ttu-id="66aa5-119">Включение поиска в каталогах с областью действия</span><span class="sxs-lookup"><span data-stu-id="66aa5-119">Turn on scoped directory search</span></span>

1. <span data-ttu-id="66aa5-120">Для настройки организации на виртуальные подгруппы используйте политики информационных барьеров.</span><span class="sxs-lookup"><span data-stu-id="66aa5-120">Use Information Barrier policies to configure your organization into virtual subgroups.</span></span> <span data-ttu-id="66aa5-121">Дополнительные сведения можно найти в разделе [Определение политик барьера информации](https://docs.microsoft.com/microsoft-365/compliance/information-barriers-policies).</span><span class="sxs-lookup"><span data-stu-id="66aa5-121">For more information, see [Define Information Barrier policies](https://docs.microsoft.com/microsoft-365/compliance/information-barriers-policies).</span></span>

2. <span data-ttu-id="66aa5-122">В центре администрирования Microsoft Teams выберите > **параметры групп** **на уровне Организации**.</span><span class="sxs-lookup"><span data-stu-id="66aa5-122">In the Microsoft Teams admin center, select **Org-wide settings** > **Teams settings**.</span></span>

3. <span data-ttu-id="66aa5-123">В разделе **Поиск**рядом с **областью поиска в каталоге в Teams с помощью политики адресной книги Exchange (АБП)** включите **переключатель.**</span><span class="sxs-lookup"><span data-stu-id="66aa5-123">Under **Search**, next to **Scope directory search in Teams using an Exchange address book policy (ABP)**, turn the toggle **On**.</span></span>

    ![Поиск в каталоге с областью в центре администрирования Microsoft Teams](media/teams-scoped-directory-search-image1.png)


> [!IMPORTANT]
> <span data-ttu-id="66aa5-125">Для репликации этого изменения может потребоваться до 24 часов.</span><span class="sxs-lookup"><span data-stu-id="66aa5-125">This change can take up to 24 hours to replicate.</span></span>
