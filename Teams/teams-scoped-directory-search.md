---
title: Использование групп Майкрософт областью действия поиск в каталоге
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 10/09/2018
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: sbhatta
localization_priority: Normal
search.appverid: MET150
description: Узнайте, как использовать поиск в каталоге с областью группами Майкрософт для обеспечения настраиваемого представления каталога.
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: 1b62b3e27cf0aa10ea6719cb1f27980ee83f4421
ms.sourcegitcommit: c4254b6119bbce274f895e20d30cb3c513d5a2de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/09/2018
ms.locfileid: "25455972"
---
# <a name="use-microsoft-teams-scoped-directory-search"></a><span data-ttu-id="43b08-103">Использование групп Майкрософт областью действия поиск в каталоге</span><span class="sxs-lookup"><span data-stu-id="43b08-103">Use Microsoft Teams scoped directory search</span></span>

<span data-ttu-id="43b08-104">Поиск в каталоге с областью группами Майкрософт позволяет организациям создавать виртуальные границы, которые управляют как пользователи могут находить и общаться с другими пользователями в своей организации.</span><span class="sxs-lookup"><span data-stu-id="43b08-104">Microsoft Teams scoped directory search allows organizations to create virtual boundaries that control how users can find and communicate with other users in their organization.</span></span> 

<span data-ttu-id="43b08-105">Группами Майкрософт позволяет организациям предоставлять своим пользователям настраиваемых представлений каталога.</span><span class="sxs-lookup"><span data-stu-id="43b08-105">Microsoft Teams lets organizations provide custom views of the directory to their users.</span></span> <span data-ttu-id="43b08-106">Группами Майкрософт использует [политики адресных книг Exchange](https://docs.microsoft.com/en-us/Exchange/email-addresses-and-address-books/address-book-policies/address-book-policies?view=exchserver-2019) для поддержки этих настраиваемых представлений.</span><span class="sxs-lookup"><span data-stu-id="43b08-106">Microsoft Teams uses [Exchange address book policies](https://docs.microsoft.com/en-us/Exchange/email-addresses-and-address-books/address-book-policies/address-book-policies?view=exchserver-2019) to support these custom views.</span></span> <span data-ttu-id="43b08-107">После включения политики будут область результатов, возвращаемых выполняет поиск других пользователей (например, для запуска в чате или для добавления членов в группы), соответствующую настроенные политики.</span><span class="sxs-lookup"><span data-stu-id="43b08-107">Once the policies are enabled, the results returned by searches for other users (for example, to initiate a chat or to add members to a team) will be scoped according to the configured policies.</span></span> <span data-ttu-id="43b08-108">Пользователи не смогут найти или обнаружение и присоединение к новых рабочих групп за пределами этих политик.</span><span class="sxs-lookup"><span data-stu-id="43b08-108">Users will not be able to search or discover and join new teams outside of these policies.</span></span> 

## <a name="when-should-you-use-scroped-directory-searches"></a><span data-ttu-id="43b08-109">Когда следует использовать поиска в каталоге scroped?</span><span class="sxs-lookup"><span data-stu-id="43b08-109">When should you use scroped directory searches?</span></span>

<span data-ttu-id="43b08-110">Сценарии, в которых были поиска в каталоге с областью похожи на сценарии политики адресной книги.</span><span class="sxs-lookup"><span data-stu-id="43b08-110">Scenarios that benefit from scoped directory searches are similar to address book policy scenarios.</span></span> <span data-ttu-id="43b08-111">Например можно использовать поиск в каталоге с областью в следующих ситуациях:</span><span class="sxs-lookup"><span data-stu-id="43b08-111">For example, you may want to use scoped directory search in the following situations:</span></span>

- <span data-ttu-id="43b08-112">Вашей организации есть несколько компаний в его клиентов, вам необходимо хранить отдельно.</span><span class="sxs-lookup"><span data-stu-id="43b08-112">Your organization has multiple companies within its tenant that you want to keep separate.</span></span> 
- <span data-ttu-id="43b08-113">Школа требуется ограничение чаты между преподавателей и учащихся.</span><span class="sxs-lookup"><span data-stu-id="43b08-113">Your school wants to limit chats between faculty and students.</span></span> 
 
<span data-ttu-id="43b08-114">Дополнительные сведения о том, как можно использовать политики адресных книг [здесь](https://docs.microsoft.com/en-us/Exchange/email-addresses-and-address-books/address-book-policies/abp-scenarios?view=exchserver-2019).</span><span class="sxs-lookup"><span data-stu-id="43b08-114">You can learn more about how address book policies can be used [here](https://docs.microsoft.com/en-us/Exchange/email-addresses-and-address-books/address-book-policies/abp-scenarios?view=exchserver-2019).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="43b08-115">Политики адресных книг обеспечивают только виртуальный разделение пользователей с точки зрения каталогов.</span><span class="sxs-lookup"><span data-stu-id="43b08-115">Address book policies provide only a virtual separation of users from directory perspective.</span></span> <span data-ttu-id="43b08-116">Пользователи по-прежнему можно инициировать связь с другими пользователями с указанием адреса электронной почты завершена.</span><span class="sxs-lookup"><span data-stu-id="43b08-116">Users can still initiate communications with others by providing complete email addresses.</span></span> 

## <a name="enable-scoped-directory-search"></a><span data-ttu-id="43b08-117">Поиск в каталоге Enable областью действия</span><span class="sxs-lookup"><span data-stu-id="43b08-117">Enable scoped directory search</span></span>

1.  <span data-ttu-id="43b08-118">Используйте политики адресных книг для вашей организации на виртуальный подгруппы.</span><span class="sxs-lookup"><span data-stu-id="43b08-118">Use address book policies to configure your organization into virtual subgroups.</span></span> <span data-ttu-id="43b08-119">Для получения дополнительных сведений см [процедуры для политики адресных книг](https://docs.microsoft.com/en-us/Exchange/email-addresses-and-address-books/address-book-policies/abp-procedures?view=exchserver-2019).</span><span class="sxs-lookup"><span data-stu-id="43b08-119">For more information, see [Procedures for address book policies](https://docs.microsoft.com/en-us/Exchange/email-addresses-and-address-books/address-book-policies/abp-procedures?view=exchserver-2019).</span></span>

2.  <span data-ttu-id="43b08-120">Войдите Центр администрирования Microsoft 365, выберите **центры администрирования**и выберите **команды & Скайп**.</span><span class="sxs-lookup"><span data-stu-id="43b08-120">Sign in to the Microsoft 365 admin center, select **Admin centers**, and then select **Teams & Skype**.</span></span>
 
3.  <span data-ttu-id="43b08-121">В группами Майкрософт & Скайп по центру администрирования бизнеса, выберите пункт **Параметры масштабе организации** > **Параметры группы**.</span><span class="sxs-lookup"><span data-stu-id="43b08-121">In the Microsoft Teams & Skype for Business admin center, select **Org-wide settings** > **Teams settings**.</span></span>

4.  <span data-ttu-id="43b08-122">В области **поиска**, рядом с полем **Поиск в каталоге областей в группах, с помощью политики адресной книги Exchange (aPb в качестве)** включите переключить **на**.</span><span class="sxs-lookup"><span data-stu-id="43b08-122">Under **Search**, next to **Scope directory search in Teams using an Exchange address book policy (APB)**, turn the toggle **On**.</span></span> 

    ![Поиск в каталоге в группы & Скайп по центру администрирования Business областью действия](media/teams-scoped-directory-search-image1.png)

> [!NOTE]
> <span data-ttu-id="43b08-124">Гибридные конфигурации (рабочие группы, локальную систему Exchange) не поддерживают режим поиска с заданной областью.</span><span class="sxs-lookup"><span data-stu-id="43b08-124">Hybrid configurations (Teams with Exchange on-premises) do not support scoped search mode.</span></span> 

