---
title: Управление внешним доступом (федерация) в Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 01/30/2019
ms.topic: article
ms.service: msteams
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
ms.reviewer: karvell
search.appverid: MET150
description: ИТ-администратор можно настроить внешний доступ для других доменов (федерации) дать возможность пользователям из этих доменов принимать участие в группах.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 97b322969d3975b6f9ca2b2079d46fe95ef45e52
ms.sourcegitcommit: 85c34280977fb2c15c8a43874a20e9492bdca57f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/07/2019
ms.locfileid: "30459926"
---
<a name="manage-external-access-federation-in-microsoft-teams"></a><span data-ttu-id="9dc21-103">Управление внешним доступом (федерация) в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="9dc21-103">Manage external access (federation) in Microsoft Teams</span></span>
======================================================

<span data-ttu-id="9dc21-104">С помощью внешнего доступа группами Майкрософт пользователей из других доменов могут принимать участие в беседах и звонки.</span><span class="sxs-lookup"><span data-stu-id="9dc21-104">With Microsoft Teams external access, users from other domains can participate in your chats and calls.</span></span> <span data-ttu-id="9dc21-105">Также можно разрешить внешние пользователи, по-прежнему используется Скайп для бизнеса для участия.</span><span class="sxs-lookup"><span data-stu-id="9dc21-105">You can also allow external users who are still using Skype for Business to participate.</span></span> 

<span data-ttu-id="9dc21-106">Внешний доступ (федерации) и доступ в качестве гостя различны:</span><span class="sxs-lookup"><span data-stu-id="9dc21-106">External access (federation) and guest access are different:</span></span>

- <span data-ttu-id="9dc21-107">Доступ в качестве гостя предоставляет разрешение на доступ к физическим.</span><span class="sxs-lookup"><span data-stu-id="9dc21-107">Guest access gives access permission to an individual.</span></span> <span data-ttu-id="9dc21-108">Внешний доступ предоставляет разрешения на доступ к всему домену.</span><span class="sxs-lookup"><span data-stu-id="9dc21-108">External access gives access permission to an entire domain.</span></span>

- <span data-ttu-id="9dc21-109">Гостевой доступ, один раз, предоставленный владельцем группы позволяет гостя для [доступа к ресурсам](guest-experience.md), например канала обсуждений и файлы, конкретными группами и разговора с другим пользователям рабочих групп, которые они были приглашены.</span><span class="sxs-lookup"><span data-stu-id="9dc21-109">Guest access, once granted by a team owner, allows a guest to [access resources](guest-experience.md), such as channel discussions and files, for a specific team, and chat with other users in the team they have been invited to.</span></span> <span data-ttu-id="9dc21-110">С помощью внешнего доступа (федеративных чата) внешние чата участникам не имеют доступа к группам приглашение организации или ресурсы группы.</span><span class="sxs-lookup"><span data-stu-id="9dc21-110">With external access (federated chat), the external chat participants have no access to the inviting organization’s teams or team resources.</span></span> <span data-ttu-id="9dc21-111">Только они могут принимать участие в индивидуального федеративных чата.</span><span class="sxs-lookup"><span data-stu-id="9dc21-111">They can only participate in one-on-one federated chat.</span></span> <span data-ttu-id="9dc21-112">Администраторы клиента можно выбрать между двумя коммуникационными параметры в зависимости от того, какой уровень совместной работы желательно с внешней стороны.</span><span class="sxs-lookup"><span data-stu-id="9dc21-112">Tenant admins can choose between the two communication options depending on which level of collaboration is desirable with the external party.</span></span> <span data-ttu-id="9dc21-113">«Администраторы» можно выбрать методов или оба адресата, в зависимости от своих потребностей организации, но рекомендуется включить гостевой доступ для более полном совместной работы групп.</span><span class="sxs-lookup"><span data-stu-id="9dc21-113">Admins can choose either approaches or both, depending on their organizational needs, but we recommend enabling guest access for a fuller, collaborative Teams experience.</span></span> 

<span data-ttu-id="9dc21-114">Ознакомьтесь со следующей таблицы для сравнения внешних and гостевой доступ к функциям.</span><span class="sxs-lookup"><span data-stu-id="9dc21-114">See the following table for a comparison of external and guest access features.</span></span>

| <span data-ttu-id="9dc21-115">Функция</span><span class="sxs-lookup"><span data-stu-id="9dc21-115">Feature</span></span> | <span data-ttu-id="9dc21-116">Доступ для внешних пользователей</span><span class="sxs-lookup"><span data-stu-id="9dc21-116">External access users</span></span> | <span data-ttu-id="9dc21-117">Гостевая доступа пользователей</span><span class="sxs-lookup"><span data-stu-id="9dc21-117">Guest access users</span></span> |
|---------|-----------------------|--------------------|
| <span data-ttu-id="9dc21-118">Пользователь может общаться с кем-либо в другую компанию</span><span class="sxs-lookup"><span data-stu-id="9dc21-118">User can chat with someone in another company</span></span> | <span data-ttu-id="9dc21-119">Да</span><span class="sxs-lookup"><span data-stu-id="9dc21-119">Yes</span></span> |<span data-ttu-id="9dc21-120">Да </span><span class="sxs-lookup"><span data-stu-id="9dc21-120">Yes</span></span> |
| <span data-ttu-id="9dc21-121">Пользователя можно позвонить кому-либо в другую компанию</span><span class="sxs-lookup"><span data-stu-id="9dc21-121">User can call someone in another company</span></span> | <span data-ttu-id="9dc21-122">Да</span><span class="sxs-lookup"><span data-stu-id="9dc21-122">Yes</span></span> | <span data-ttu-id="9dc21-123">Да </span><span class="sxs-lookup"><span data-stu-id="9dc21-123">Yes</span></span> |
| <span data-ttu-id="9dc21-124">Пользователь может видеть, доступен ли кто-то из другой компании для вызова или чата</span><span class="sxs-lookup"><span data-stu-id="9dc21-124">User can see if someone from another company is available for call or chat</span></span> | <span data-ttu-id="9dc21-125">Да</span><span class="sxs-lookup"><span data-stu-id="9dc21-125">Yes</span></span> | <span data-ttu-id="9dc21-126">Да<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="9dc21-126">Yes<sup>1</sup></span></span> |
| <span data-ttu-id="9dc21-127">Пользователь может найти пользователей внешних клиентов</span><span class="sxs-lookup"><span data-stu-id="9dc21-127">User can search for users across external tenants</span></span> | <span data-ttu-id="9dc21-128">Да,<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="9dc21-128">Yes<sup>2</sup></span></span> | <span data-ttu-id="9dc21-129">Нет</span><span class="sxs-lookup"><span data-stu-id="9dc21-129">No</span></span> |
| <span data-ttu-id="9dc21-130">Пользователя можно совместно использовать файлы</span><span class="sxs-lookup"><span data-stu-id="9dc21-130">User can share files</span></span> | <span data-ttu-id="9dc21-131">Нет</span><span class="sxs-lookup"><span data-stu-id="9dc21-131">No</span></span> | <span data-ttu-id="9dc21-132">Да</span><span class="sxs-lookup"><span data-stu-id="9dc21-132">Yes</span></span> |
| <span data-ttu-id="9dc21-133">Пользователь может получить доступ ресурсы группы</span><span class="sxs-lookup"><span data-stu-id="9dc21-133">User can access Teams resources</span></span> | <span data-ttu-id="9dc21-134">Нет</span><span class="sxs-lookup"><span data-stu-id="9dc21-134">No</span></span> | <span data-ttu-id="9dc21-135">Да</span><span class="sxs-lookup"><span data-stu-id="9dc21-135">Yes</span></span> |
| <span data-ttu-id="9dc21-136">Пользователя можно добавить в групповой беседы</span><span class="sxs-lookup"><span data-stu-id="9dc21-136">User can be added to a group chat</span></span> | <span data-ttu-id="9dc21-137">Нет</span><span class="sxs-lookup"><span data-stu-id="9dc21-137">No</span></span> | <span data-ttu-id="9dc21-138">Да</span><span class="sxs-lookup"><span data-stu-id="9dc21-138">Yes</span></span> |
| <span data-ttu-id="9dc21-139">Можно добавить пользователя к собранию</span><span class="sxs-lookup"><span data-stu-id="9dc21-139">User can be added to a meeting</span></span> | <span data-ttu-id="9dc21-140">Да</span><span class="sxs-lookup"><span data-stu-id="9dc21-140">Yes</span></span> | <span data-ttu-id="9dc21-141">Да </span><span class="sxs-lookup"><span data-stu-id="9dc21-141">Yes</span></span> |
| <span data-ttu-id="9dc21-142">Можно добавить дополнительных пользователей в беседы с помощью внешних пользователей</span><span class="sxs-lookup"><span data-stu-id="9dc21-142">Additional users can be added to a chat with an external user</span></span> | <span data-ttu-id="9dc21-143">Нет<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="9dc21-143">No<sup>3</sup></span></span> | <span data-ttu-id="9dc21-144">Н/Д</span><span class="sxs-lookup"><span data-stu-id="9dc21-144">N/A</span></span> |
| <span data-ttu-id="9dc21-145">Пользователь определяется как внешние стороны</span><span class="sxs-lookup"><span data-stu-id="9dc21-145">User is identified as an external party</span></span> | <span data-ttu-id="9dc21-146">Да</span><span class="sxs-lookup"><span data-stu-id="9dc21-146">Yes</span></span> | <span data-ttu-id="9dc21-147">Да </span><span class="sxs-lookup"><span data-stu-id="9dc21-147">Yes</span></span> |
| <span data-ttu-id="9dc21-148">Отображаются сведения о присутствии</span><span class="sxs-lookup"><span data-stu-id="9dc21-148">Presence is displayed</span></span> | <span data-ttu-id="9dc21-149">Да</span><span class="sxs-lookup"><span data-stu-id="9dc21-149">Yes</span></span> | <span data-ttu-id="9dc21-150">Да </span><span class="sxs-lookup"><span data-stu-id="9dc21-150">Yes</span></span> |
| <span data-ttu-id="9dc21-151">Нет на месте отображается сообщение</span><span class="sxs-lookup"><span data-stu-id="9dc21-151">Out of office message is shown</span></span> | <span data-ttu-id="9dc21-152">Нет</span><span class="sxs-lookup"><span data-stu-id="9dc21-152">No</span></span> | <span data-ttu-id="9dc21-153">Да</span><span class="sxs-lookup"><span data-stu-id="9dc21-153">Yes</span></span> |
| <span data-ttu-id="9dc21-154">Можно заблокировать отдельного пользователя</span><span class="sxs-lookup"><span data-stu-id="9dc21-154">Individual user can be blocked</span></span> | <span data-ttu-id="9dc21-155">Нет</span><span class="sxs-lookup"><span data-stu-id="9dc21-155">No</span></span> | <span data-ttu-id="9dc21-156">Да</span><span class="sxs-lookup"><span data-stu-id="9dc21-156">Yes</span></span> |
| <span data-ttu-id="9dc21-157">поддерживаемые @mentions</span><span class="sxs-lookup"><span data-stu-id="9dc21-157">@mentions are supported</span></span> | <span data-ttu-id="9dc21-158">Нет</span><span class="sxs-lookup"><span data-stu-id="9dc21-158">No</span></span> | <span data-ttu-id="9dc21-159">Да</span><span class="sxs-lookup"><span data-stu-id="9dc21-159">Yes</span></span> |
||||

<span data-ttu-id="9dc21-160"><sup>1</sup> входящего, что пользователь был добавлен в качестве гостя и вход в качестве гостя к клиенту гостя.</span><span class="sxs-lookup"><span data-stu-id="9dc21-160"><sup>1</sup> Provided that the user has been added as a guest and is signed in as a guest to the guest tenant.</span></span><br>
<span data-ttu-id="9dc21-161"><sup>2</sup> только по электронной почте или адрес Session Initiation Protocol (SIP).</span><span class="sxs-lookup"><span data-stu-id="9dc21-161"><sup>2</sup> Only by email or Session Initiation Protocol (SIP) address.</span></span><br>
<span data-ttu-id="9dc21-162"><sup>3</sup> внешних чата (федеративных) — 1:1 только.</span><span class="sxs-lookup"><span data-stu-id="9dc21-162"><sup>3</sup> External (federated) chat is 1:1 only.</span></span>

## <a name="turn-on-or-turn-off-external-access"></a><span data-ttu-id="9dc21-163">Включить или отключить внешний доступ</span><span class="sxs-lookup"><span data-stu-id="9dc21-163">Turn on or turn off external access</span></span>

<span data-ttu-id="9dc21-164">_AMP_ группами Майкрософт Скайп по центру администрирования Business можно использовать для управления внешнего доступа.</span><span class="sxs-lookup"><span data-stu-id="9dc21-164">You can use the Microsoft Teams & Skype for Business Admin Center to manage external access.</span></span>

1. <span data-ttu-id="9dc21-165">В Скайп по центру администрирования Business & группами Майкрософт, выберите **Параметры масштабе организации** > **внешнего доступа**.</span><span class="sxs-lookup"><span data-stu-id="9dc21-165">In the Microsoft Teams & Skype for Business Admin Center, select **Org-wide settings** > **External access**.</span></span>

     ![Снимок экрана с масштабе организации параметры внешнего доступа](media/manage-external-access-1.png)<span data-ttu-id="9dc21-167">.</span><span class="sxs-lookup"><span data-stu-id="9dc21-167"></span></span>

2. <span data-ttu-id="9dc21-168">Переключение к переходу **внешнего доступа** на **включено** или **отключено**.</span><span class="sxs-lookup"><span data-stu-id="9dc21-168">Toggle the **External access** switch to **On** or **Off**.</span></span>

     ![Снимок экрана с включенным переключатель внешнего доступа](media/manage-external-access-2.png)<span data-ttu-id="9dc21-170">.</span><span class="sxs-lookup"><span data-stu-id="9dc21-170"></span></span>

3. <span data-ttu-id="9dc21-171">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="9dc21-171">Click **Save**.</span></span> 

## <a name="add-or-block-a-domain"></a><span data-ttu-id="9dc21-172">Добавление или блокирование домена</span><span class="sxs-lookup"><span data-stu-id="9dc21-172">Add or block a domain</span></span>

<span data-ttu-id="9dc21-173">Выполните следующие действия, чтобы добавить домен или отключить внешний доступ для домена.</span><span class="sxs-lookup"><span data-stu-id="9dc21-173">Follow these steps to add a domain or turn off external access for a domain.</span></span>

1. <span data-ttu-id="9dc21-174">В Скайп по центру администрирования Business & группами Майкрософт, выберите **Параметры масштабе организации** > **внешнего доступа**.</span><span class="sxs-lookup"><span data-stu-id="9dc21-174">In the Microsoft Teams & Skype for Business Admin Center, select **Org-wide settings** > **External access**.</span></span>

2. <span data-ttu-id="9dc21-175">Выберите **Добавить домен**.</span><span class="sxs-lookup"><span data-stu-id="9dc21-175">Select **Add a domain**.</span></span> 
 
    ![Снимок экрана внешнего доступа страница с добавить ссылку домена](media/manage-external-access-3.png)<span data-ttu-id="9dc21-177">.</span><span class="sxs-lookup"><span data-stu-id="9dc21-177"></span></span>

   <span data-ttu-id="9dc21-178">Появится в области **Добавить домен** .</span><span class="sxs-lookup"><span data-stu-id="9dc21-178">The **Add a domain** pane appears.</span></span>

    ![Снимок экрана с добавить область домена](media/manage-external-access-4.png)<span data-ttu-id="9dc21-180">.</span><span class="sxs-lookup"><span data-stu-id="9dc21-180"></span></span>


3. <span data-ttu-id="9dc21-181">В поле **Добавить домен**введите имя домена; Например введите Contoso.com.</span><span class="sxs-lookup"><span data-stu-id="9dc21-181">Under **Add a domain**, type the name of the domain; for example, type Contoso.com.</span></span>

4. <span data-ttu-id="9dc21-182">Выберите **Разрешить** или **заблокировать**.</span><span class="sxs-lookup"><span data-stu-id="9dc21-182">Select **Allowed** or **Blocked**.</span></span> <span data-ttu-id="9dc21-183">Можно изменить этот параметр в любое время.</span><span class="sxs-lookup"><span data-stu-id="9dc21-183">You can change this setting at any time.</span></span>

2. <span data-ttu-id="9dc21-184">Выберите **выполнить**.</span><span class="sxs-lookup"><span data-stu-id="9dc21-184">Select **Done**.</span></span>

<span data-ttu-id="9dc21-185">После добавления домена, вы увидите доменное имя и состояние, добавляемого в список доменов на странице внешнего доступа.</span><span class="sxs-lookup"><span data-stu-id="9dc21-185">After you add a domain, you will see the domain name and status added to the list of domains on the External access page.</span></span>

## <a name="more-information"></a><span data-ttu-id="9dc21-186">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="9dc21-186">More information</span></span>

<span data-ttu-id="9dc21-187">Сведения о гостевой доступ в группах Microsoft содержатся [гостевой управление доступом в группах Майкрософт](manage-guests.md).</span><span class="sxs-lookup"><span data-stu-id="9dc21-187">For information about guest access in Microsoft Teams, see [Manage guest access in Microsoft Teams](manage-guests.md).</span></span>