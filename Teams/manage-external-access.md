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
description: Ваш ИТ-администратор может настроить внешний доступ для других доменов (Федерации), чтобы пользователи из этих доменов могли участвовать в Teams.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 3f6a3dc6016eb52d58e82e9e9022d1bb8575404b
ms.sourcegitcommit: b9e7a11d8332a029a4f1cd4e396787f5a74f0a44
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2019
ms.locfileid: "34702722"
---
<a name="manage-external-access-federation-in-microsoft-teams"></a><span data-ttu-id="e93de-103">Управление внешним доступом (федерация) в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="e93de-103">Manage external access (federation) in Microsoft Teams</span></span>
======================================================

<span data-ttu-id="e93de-104">При использовании Microsoft Teams External Access пользователи из других доменов могут принимать участие в беседах и звонках.</span><span class="sxs-lookup"><span data-stu-id="e93de-104">With Microsoft Teams external access, users from other domains can participate in your chats and calls.</span></span> <span data-ttu-id="e93de-105">Кроме того, вы можете использовать внешних пользователей Skype для бизнеса Online или Skype для бизнеса в локальной системе для участия.</span><span class="sxs-lookup"><span data-stu-id="e93de-105">You can also allow external users who are still using Skype for Business Online or Skype for Business on-prem to participate.</span></span> 

<span data-ttu-id="e93de-106">Внешний доступ (Федерация) и гостевой доступ различаются.</span><span class="sxs-lookup"><span data-stu-id="e93de-106">External access (federation) and guest access are different:</span></span>

- <span data-ttu-id="e93de-107">Гостевой доступ — это разрешение на доступ к отдельным сотрудникам.</span><span class="sxs-lookup"><span data-stu-id="e93de-107">Guest access gives access permission to an individual.</span></span> <span data-ttu-id="e93de-108">Внешний доступ позволяет получить доступ ко всему домену.</span><span class="sxs-lookup"><span data-stu-id="e93de-108">External access gives access permission to an entire domain.</span></span>

- <span data-ttu-id="e93de-109">Гостевой доступ, предоставленный владельцем группы, позволяет гостевым пользователям [получать доступ к ресурсам](guest-experience.md), например к обсуждениям каналов и файлам, к определенным командам, а также общаться с другими пользователями в группе, на которые они были приглашены.</span><span class="sxs-lookup"><span data-stu-id="e93de-109">Guest access, once granted by a team owner, allows a guest to [access resources](guest-experience.md), such as channel discussions and files, for a specific team, and chat with other users in the team they have been invited to.</span></span> <span data-ttu-id="e93de-110">При использовании внешнего доступа (федеративного чата) участники внешнего чата не имеют доступа к командам и ресурсам группы в приглашенной Организации.</span><span class="sxs-lookup"><span data-stu-id="e93de-110">With external access (federated chat), the external chat participants have no access to the inviting organization’s teams or team resources.</span></span> <span data-ttu-id="e93de-111">Они могут принимать участие только в одном объединенном чате.</span><span class="sxs-lookup"><span data-stu-id="e93de-111">They can only participate in one-on-one federated chat.</span></span> <span data-ttu-id="e93de-112">Администраторы клиентов могут выбрать один из двух вариантов общения в зависимости от того, какой уровень совместной работы является желательным для внешней стороны.</span><span class="sxs-lookup"><span data-stu-id="e93de-112">Tenant admins can choose between the two communication options depending on which level of collaboration is desirable with the external party.</span></span> <span data-ttu-id="e93de-113">Администраторы могут выбрать один из вариантов или оба варианта, в зависимости от потребностей Организации, но мы рекомендуем включить гостевой доступ для более комфортной совместной работы в коллективной работе.</span><span class="sxs-lookup"><span data-stu-id="e93de-113">Admins can choose either approaches or both, depending on their organizational needs, but we recommend enabling guest access for a fuller, collaborative Teams experience.</span></span> 

<span data-ttu-id="e93de-114">В таблице ниже приведены сведения о сравнении внешних функций и возможностей гостевой доступа.</span><span class="sxs-lookup"><span data-stu-id="e93de-114">See the following table for a comparison of external and guest access features.</span></span>

| <span data-ttu-id="e93de-115">Функция</span><span class="sxs-lookup"><span data-stu-id="e93de-115">Feature</span></span> | <span data-ttu-id="e93de-116">Пользователи внешнего доступа</span><span class="sxs-lookup"><span data-stu-id="e93de-116">External access users</span></span> | <span data-ttu-id="e93de-117">Пользователи гостевого доступа</span><span class="sxs-lookup"><span data-stu-id="e93de-117">Guest access users</span></span> |
|---------|-----------------------|--------------------|
| <span data-ttu-id="e93de-118">Пользователь может общаться с кем-либо в другой компании</span><span class="sxs-lookup"><span data-stu-id="e93de-118">User can chat with someone in another company</span></span> | <span data-ttu-id="e93de-119">Да</span><span class="sxs-lookup"><span data-stu-id="e93de-119">Yes</span></span> |<span data-ttu-id="e93de-120">Да </span><span class="sxs-lookup"><span data-stu-id="e93de-120">Yes</span></span> |
| <span data-ttu-id="e93de-121">Пользователь может позвонить кому-либо в другой компании</span><span class="sxs-lookup"><span data-stu-id="e93de-121">User can call someone in another company</span></span> | <span data-ttu-id="e93de-122">Да</span><span class="sxs-lookup"><span data-stu-id="e93de-122">Yes</span></span> | <span data-ttu-id="e93de-123">Да </span><span class="sxs-lookup"><span data-stu-id="e93de-123">Yes</span></span> |
| <span data-ttu-id="e93de-124">Пользователь может видеть, доступен ли кто-то из другой компании для звонков или общения</span><span class="sxs-lookup"><span data-stu-id="e93de-124">User can see if someone from another company is available for call or chat</span></span> | <span data-ttu-id="e93de-125">Да</span><span class="sxs-lookup"><span data-stu-id="e93de-125">Yes</span></span> | <span data-ttu-id="e93de-126">Да,<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="e93de-126">Yes<sup>1</sup></span></span> |
| <span data-ttu-id="e93de-127">Пользователь может искать пользователей на внешних клиентах</span><span class="sxs-lookup"><span data-stu-id="e93de-127">User can search for users across external tenants</span></span> | <span data-ttu-id="e93de-128">Да,<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="e93de-128">Yes<sup>2</sup></span></span> | <span data-ttu-id="e93de-129">Нет</span><span class="sxs-lookup"><span data-stu-id="e93de-129">No</span></span> |
| <span data-ttu-id="e93de-130">Пользователь может предоставлять общий доступ к файлам</span><span class="sxs-lookup"><span data-stu-id="e93de-130">User can share files</span></span> | <span data-ttu-id="e93de-131">Нет</span><span class="sxs-lookup"><span data-stu-id="e93de-131">No</span></span> | <span data-ttu-id="e93de-132">Да</span><span class="sxs-lookup"><span data-stu-id="e93de-132">Yes</span></span> |
| <span data-ttu-id="e93de-133">Пользователь может получить доступ к ресурсам Teams</span><span class="sxs-lookup"><span data-stu-id="e93de-133">User can access Teams resources</span></span> | <span data-ttu-id="e93de-134">Нет</span><span class="sxs-lookup"><span data-stu-id="e93de-134">No</span></span> | <span data-ttu-id="e93de-135">Да</span><span class="sxs-lookup"><span data-stu-id="e93de-135">Yes</span></span> |
| <span data-ttu-id="e93de-136">Возможность добавления пользователя в групповой чат</span><span class="sxs-lookup"><span data-stu-id="e93de-136">User can be added to a group chat</span></span> | <span data-ttu-id="e93de-137">Нет</span><span class="sxs-lookup"><span data-stu-id="e93de-137">No</span></span> | <span data-ttu-id="e93de-138">Да</span><span class="sxs-lookup"><span data-stu-id="e93de-138">Yes</span></span> |
| <span data-ttu-id="e93de-139">Пользователь может быть добавлен на собрание</span><span class="sxs-lookup"><span data-stu-id="e93de-139">User can be added to a meeting</span></span> | <span data-ttu-id="e93de-140">Да</span><span class="sxs-lookup"><span data-stu-id="e93de-140">Yes</span></span> | <span data-ttu-id="e93de-141">Да </span><span class="sxs-lookup"><span data-stu-id="e93de-141">Yes</span></span> |
| <span data-ttu-id="e93de-142">Дополнительные пользователи могут быть добавлены в чат с внешним пользователем</span><span class="sxs-lookup"><span data-stu-id="e93de-142">Additional users can be added to a chat with an external user</span></span> | <span data-ttu-id="e93de-143">No<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="e93de-143">No<sup>3</sup></span></span> | <span data-ttu-id="e93de-144">Н/Д</span><span class="sxs-lookup"><span data-stu-id="e93de-144">N/A</span></span> |
| <span data-ttu-id="e93de-145">Пользователь идентифицирован как внешний абонент</span><span class="sxs-lookup"><span data-stu-id="e93de-145">User is identified as an external party</span></span> | <span data-ttu-id="e93de-146">Да</span><span class="sxs-lookup"><span data-stu-id="e93de-146">Yes</span></span> | <span data-ttu-id="e93de-147">Да </span><span class="sxs-lookup"><span data-stu-id="e93de-147">Yes</span></span> |
| <span data-ttu-id="e93de-148">Отображается состояние присутствия</span><span class="sxs-lookup"><span data-stu-id="e93de-148">Presence is displayed</span></span> | <span data-ttu-id="e93de-149">Да</span><span class="sxs-lookup"><span data-stu-id="e93de-149">Yes</span></span> | <span data-ttu-id="e93de-150">Да </span><span class="sxs-lookup"><span data-stu-id="e93de-150">Yes</span></span> |
| <span data-ttu-id="e93de-151">Сообщение об отсутствии на рабочем месте отображается</span><span class="sxs-lookup"><span data-stu-id="e93de-151">Out of office message is shown</span></span> | <span data-ttu-id="e93de-152">Нет</span><span class="sxs-lookup"><span data-stu-id="e93de-152">No</span></span> | <span data-ttu-id="e93de-153">Да</span><span class="sxs-lookup"><span data-stu-id="e93de-153">Yes</span></span> |
| <span data-ttu-id="e93de-154">Вы можете заблокировать отдельного пользователя</span><span class="sxs-lookup"><span data-stu-id="e93de-154">Individual user can be blocked</span></span> | <span data-ttu-id="e93de-155">Нет</span><span class="sxs-lookup"><span data-stu-id="e93de-155">No</span></span> | <span data-ttu-id="e93de-156">Да</span><span class="sxs-lookup"><span data-stu-id="e93de-156">Yes</span></span> |
| <span data-ttu-id="e93de-157">@mentions поддерживаются</span><span class="sxs-lookup"><span data-stu-id="e93de-157">@mentions are supported</span></span> | <span data-ttu-id="e93de-158">Нет</span><span class="sxs-lookup"><span data-stu-id="e93de-158">No</span></span> | <span data-ttu-id="e93de-159">Да</span><span class="sxs-lookup"><span data-stu-id="e93de-159">Yes</span></span> |
| <span data-ttu-id="e93de-160">Совершение частных звонков</span><span class="sxs-lookup"><span data-stu-id="e93de-160">Make Private Calls</span></span> | <span data-ttu-id="e93de-161">Да</span><span class="sxs-lookup"><span data-stu-id="e93de-161">Yes</span></span> | <span data-ttu-id="e93de-162">Да </span><span class="sxs-lookup"><span data-stu-id="e93de-162">Yes</span></span> |
| <span data-ttu-id="e93de-163">Разрешить IP-видео</span><span class="sxs-lookup"><span data-stu-id="e93de-163">Allow IP Video</span></span> | <span data-ttu-id="e93de-164">Да</span><span class="sxs-lookup"><span data-stu-id="e93de-164">Yes</span></span> | <span data-ttu-id="e93de-165">Да </span><span class="sxs-lookup"><span data-stu-id="e93de-165">Yes</span></span> |
| <span data-ttu-id="e93de-166">Режим демонстрации экрана</span><span class="sxs-lookup"><span data-stu-id="e93de-166">Screen Sharing Mode</span></span> | <span data-ttu-id="e93de-167">Да</span><span class="sxs-lookup"><span data-stu-id="e93de-167">Yes</span></span> | <span data-ttu-id="e93de-168">Да </span><span class="sxs-lookup"><span data-stu-id="e93de-168">Yes</span></span> |
| <span data-ttu-id="e93de-169">Разрешить собрание прямо сейчас</span><span class="sxs-lookup"><span data-stu-id="e93de-169">Allow Meet Now</span></span> | <span data-ttu-id="e93de-170">Нет</span><span class="sxs-lookup"><span data-stu-id="e93de-170">No</span></span> | <span data-ttu-id="e93de-171">Да</span><span class="sxs-lookup"><span data-stu-id="e93de-171">Yes</span></span> |
| <span data-ttu-id="e93de-172">Изменение отправленных сообщений</span><span class="sxs-lookup"><span data-stu-id="e93de-172">Edit Sent Messages</span></span> | <span data-ttu-id="e93de-173">Да</span><span class="sxs-lookup"><span data-stu-id="e93de-173">Yes</span></span> | <span data-ttu-id="e93de-174">Да </span><span class="sxs-lookup"><span data-stu-id="e93de-174">Yes</span></span> |
| <span data-ttu-id="e93de-175">Можно удалять отправленные сообщения</span><span class="sxs-lookup"><span data-stu-id="e93de-175">Can Delete Sent Messages</span></span> | <span data-ttu-id="e93de-176">Да</span><span class="sxs-lookup"><span data-stu-id="e93de-176">Yes</span></span> | <span data-ttu-id="e93de-177">Да </span><span class="sxs-lookup"><span data-stu-id="e93de-177">Yes</span></span> |
| <span data-ttu-id="e93de-178">Использование GIF в беседе</span><span class="sxs-lookup"><span data-stu-id="e93de-178">Use Giphy In Conversation</span></span> | <span data-ttu-id="e93de-179">Да</span><span class="sxs-lookup"><span data-stu-id="e93de-179">Yes</span></span> | <span data-ttu-id="e93de-180">Да </span><span class="sxs-lookup"><span data-stu-id="e93de-180">Yes</span></span> |
| <span data-ttu-id="e93de-181">Использование мемов в беседе</span><span class="sxs-lookup"><span data-stu-id="e93de-181">Use Memes In Conversation</span></span> | <span data-ttu-id="e93de-182">Да</span><span class="sxs-lookup"><span data-stu-id="e93de-182">Yes</span></span> | <span data-ttu-id="e93de-183">Да </span><span class="sxs-lookup"><span data-stu-id="e93de-183">Yes</span></span> |
| <span data-ttu-id="e93de-184">Использование наклеек в беседе</span><span class="sxs-lookup"><span data-stu-id="e93de-184">Use Stickers In Conversation</span></span> | <span data-ttu-id="e93de-185">Да</span><span class="sxs-lookup"><span data-stu-id="e93de-185">Yes</span></span> | <span data-ttu-id="e93de-186">Да </span><span class="sxs-lookup"><span data-stu-id="e93de-186">Yes</span></span> |
||||

<span data-ttu-id="e93de-187"><sup>1</sup> предоставил, что пользователь был добавлен в качестве гостя и выполнил вход в качестве гостя для гостевого клиента.</span><span class="sxs-lookup"><span data-stu-id="e93de-187"><sup>1</sup> Provided that the user has been added as a guest and is signed in as a guest to the guest tenant.</span></span><br>
<span data-ttu-id="e93de-188"><sup>2</sup> только по электронной почте или по протоколу SIP.</span><span class="sxs-lookup"><span data-stu-id="e93de-188"><sup>2</sup> Only by email or Session Initiation Protocol (SIP) address.</span></span><br>
<span data-ttu-id="e93de-189"><sup>3</sup> внешний (федеративный) чат — только 1:1.</span><span class="sxs-lookup"><span data-stu-id="e93de-189"><sup>3</sup> External (federated) chat is 1:1 only.</span></span>

> [!NOTE]
> <span data-ttu-id="e93de-190">Дополнительные сведения о гостевых функциях и работе гостя можно найти в разделе [Включение и отключение гостевого доступа к Microsoft Teams](https://docs.microsoft.com/microsoftteams/set-up-guests) и [назначение гостевой работы](https://docs.microsoft.com/microsoftteams/guest-experience).</span><span class="sxs-lookup"><span data-stu-id="e93de-190">For more information on guest features and the guest experience, see [Turn on or off guest access to Microsoft Teams](https://docs.microsoft.com/microsoftteams/set-up-guests) and [What the guest experience is like](https://docs.microsoft.com/microsoftteams/guest-experience).</span></span>

## <a name="turn-on-or-turn-off-external-access-users-can-communicate-with-skype-for-business-and-teams-users"></a><span data-ttu-id="e93de-191">Включение и отключение внешнего доступа (пользователи могут общаться с пользователями Skype для бизнеса и Teams)</span><span class="sxs-lookup"><span data-stu-id="e93de-191">Turn on or turn off external access (Users can communicate with Skype for Business and Teams users)</span></span>

<span data-ttu-id="e93de-192">Вы можете использовать Microsoft Teams & центре администрирования Skype для бизнеса для управления внешним доступом.</span><span class="sxs-lookup"><span data-stu-id="e93de-192">You can use the Microsoft Teams & Skype for Business Admin Center to manage external access.</span></span>

1. <span data-ttu-id="e93de-193">В Microsoft Teams & центре администрирования Skype для бизнеса выберите параметры "**внешний доступ**" для **организационной настройки** > .</span><span class="sxs-lookup"><span data-stu-id="e93de-193">In the Microsoft Teams & Skype for Business Admin Center, select **Org-wide settings** > **External access**.</span></span>

     ![Снимок экрана: параметры внешнего доступа в масштабах Организации](media/manage-external-access-1.png)<span data-ttu-id="e93de-195">.</span><span class="sxs-lookup"><span data-stu-id="e93de-195"></span></span>

2. <span data-ttu-id="e93de-196">Переключение **пользователей на возможность общения с пользователями Skype для бизнеса и командами** " **вкл** " или " **выкл**".</span><span class="sxs-lookup"><span data-stu-id="e93de-196">Toggle the **Users can communicate with Skype for Business and Teams users** switch to **On** or **Off**.</span></span>

     ![Снимок экрана с включенным параметром внешнего доступа](media/manage-external-access-2.png)<span data-ttu-id="e93de-198">.</span><span class="sxs-lookup"><span data-stu-id="e93de-198"></span></span>

3. <span data-ttu-id="e93de-199">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="e93de-199">Click **Save**.</span></span> 

## <a name="add-or-block-a-domain"></a><span data-ttu-id="e93de-200">Добавление или блокировка домена</span><span class="sxs-lookup"><span data-stu-id="e93de-200">Add or block a domain</span></span>

<span data-ttu-id="e93de-201">Выполните указанные ниже действия, чтобы добавить домен или отключить внешний доступ для домена.</span><span class="sxs-lookup"><span data-stu-id="e93de-201">Follow these steps to add a domain or turn off external access for a domain.</span></span>

1. <span data-ttu-id="e93de-202">В Microsoft Teams & центре администрирования Skype для бизнеса выберите параметры "**внешний доступ**" для **организационной настройки** > .</span><span class="sxs-lookup"><span data-stu-id="e93de-202">In the Microsoft Teams & Skype for Business Admin Center, select **Org-wide settings** > **External access**.</span></span>

2. <span data-ttu-id="e93de-203">Выберите пункт **Добавить домен**.</span><span class="sxs-lookup"><span data-stu-id="e93de-203">Select **Add a domain**.</span></span> 
 
    ![Снимок экрана: страница внешнего доступа с ссылкой "добавить домен"](media/manage-external-access-3.png)<span data-ttu-id="e93de-205">.</span><span class="sxs-lookup"><span data-stu-id="e93de-205"></span></span>

   <span data-ttu-id="e93de-206">Появится область **Добавить домен** .</span><span class="sxs-lookup"><span data-stu-id="e93de-206">The **Add a domain** pane appears.</span></span>

    ![Снимок экрана: область "добавить домен"](media/manage-external-access-4.png)<span data-ttu-id="e93de-208">.</span><span class="sxs-lookup"><span data-stu-id="e93de-208"></span></span>


3. <span data-ttu-id="e93de-209">В разделе **Добавление домена**введите имя домена; Например, введите Contoso.com.</span><span class="sxs-lookup"><span data-stu-id="e93de-209">Under **Add a domain**, type the name of the domain; for example, type Contoso.com.</span></span>

4. <span data-ttu-id="e93de-210">Выберите параметр **Разрешен** или **Заблокирован**.</span><span class="sxs-lookup"><span data-stu-id="e93de-210">Select **Allowed** or **Blocked**.</span></span> <span data-ttu-id="e93de-211">Этот параметр можно изменить в любое время.</span><span class="sxs-lookup"><span data-stu-id="e93de-211">You can change this setting at any time.</span></span>

2. <span data-ttu-id="e93de-212">Нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="e93de-212">Select **Done**.</span></span>

<span data-ttu-id="e93de-213">После того как вы добавите домен, вы увидите имя домена и его состояние, которое вы добавите в список доменов на внешней странице доступа.</span><span class="sxs-lookup"><span data-stu-id="e93de-213">After you add a domain, you will see the domain name and status added to the list of domains on the External access page.</span></span>

## <a name="more-information"></a><span data-ttu-id="e93de-214">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="e93de-214">More information</span></span>

<span data-ttu-id="e93de-215">Сведения о гостевом доступе в Microsoft Teams можно найти в разделе [Управление гостевым доступом в Microsoft Teams](manage-guests.md).</span><span class="sxs-lookup"><span data-stu-id="e93de-215">For information about guest access in Microsoft Teams, see [Manage guest access in Microsoft Teams](manage-guests.md).</span></span>
