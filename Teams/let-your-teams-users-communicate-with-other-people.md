---
title: Общение с пользователями Teams из других организаций
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 09/12/2018
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
audience: Admin
search.appverid: MET150
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords: ms.teamsadmincenter.externalaccess.overview
description: Узнайте, как настроить группы, чтобы пользователи могли взаимодействовать с пользователями в другой организации.
ms.openlocfilehash: e9e2a60c7f1f93df56408976a92e4aa47f3e486e
ms.sourcegitcommit: 75b2cd0d2d39c50dc1e1513860841e2ae3f84324
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/28/2019
ms.locfileid: "34494692"
---
# <a name="let-your-teams-users-chat-and-communicate-with-users-in-another-teams-organization"></a><span data-ttu-id="c40f7-103">Предоставление пользователям Teams возможности общаться и общаться с пользователями из другой организации группы</span><span class="sxs-lookup"><span data-stu-id="c40f7-103">Let your Teams users chat and communicate with users in another Teams organization</span></span>

<span data-ttu-id="c40f7-104">Выполните действия, описанные в этой статье, в следующих случаях:</span><span class="sxs-lookup"><span data-stu-id="c40f7-104">Use the steps in this article when:</span></span>
  
- <span data-ttu-id="c40f7-105">У вас есть пользователи в разных доменах компании.</span><span class="sxs-lookup"><span data-stu-id="c40f7-105">You have users in different domains in your business.</span></span> <span data-ttu-id="c40f7-106">Например, Rob@ContosoEast.com и Ann@ContosoWest.com.</span><span class="sxs-lookup"><span data-stu-id="c40f7-106">For example, Rob@ContosoEast.com and Ann@ContosoWest.com.</span></span>
    
- <span data-ttu-id="c40f7-107">Вы хотите, чтобы сотрудники вашей организации использовали группы для связи с людьми в конкретных организациях за пределами вашей организации.</span><span class="sxs-lookup"><span data-stu-id="c40f7-107">You want the people in your organization to use Teams to contact people in specific businesses outside of your organization.</span></span>
    
- <span data-ttu-id="c40f7-108">Вы хотите, чтобы кто угодно, кто использует Teams для поиска и связи с вами, используя свой адрес электронной почты.</span><span class="sxs-lookup"><span data-stu-id="c40f7-108">You want anyone else in the world who uses Teams to be able to find and contact you, using your email address.</span></span> <span data-ttu-id="c40f7-109">Если вы и другой пользователь разрешите внешний доступ и разрешите домены других пользователей, это будет работать.</span><span class="sxs-lookup"><span data-stu-id="c40f7-109">If you and another user both enable External Access and allow each other's domains, this will work.</span></span> <span data-ttu-id="c40f7-110">Если это не сработает, другой пользователь должен убедиться, что его конфигурация не блокирует ваш домен.</span><span class="sxs-lookup"><span data-stu-id="c40f7-110">If it doesn't work, the other user should make sure his or her configuration isn't blocking your domain.</span></span>

<span data-ttu-id="c40f7-111">Это позволит пользователям находить, вызывать и отправлять вам мгновенные сообщения, а также настраивать собрания.</span><span class="sxs-lookup"><span data-stu-id="c40f7-111">This will allow users to find, call, and send you instant messages, as well as set up meetings with you.</span></span> <span data-ttu-id="c40f7-112">Если вы хотите, чтобы внешние пользователи могли получать доступ к командам и каналам, гостевой доступ может оказаться более подходящим способом.</span><span class="sxs-lookup"><span data-stu-id="c40f7-112">If you want external users to have access to teams and channels, guest access might be a better way to go.</span></span> <span data-ttu-id="c40f7-113">Выполните действия, описанные в этой статье, и обязательно [включите гостевой доступ](set-up-guests.md) , чтобы пользователи могли общаться.</span><span class="sxs-lookup"><span data-stu-id="c40f7-113">Follow the steps in this article and make sure to [turn on guest access](set-up-guests.md) so that users can communicate.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c40f7-114">Чтобы присвоить в настоящее время Федерации в клиенте Microsoft Teams внешнему пользователю за пределами вашей организации, которая в настоящее время не является Гостевой для вашего AAD или клиента, вы должны быть правильно настроены для гибридного развертывания и перемещены в Skype для бизнеса Online.</span><span class="sxs-lookup"><span data-stu-id="c40f7-114">In order to currently federate within the Microsoft Teams client to an external user outside of your organization who's not currently a Guest of your AAD/Tenant, you must be correctly setup for hybrid and moved to Skype for Business Online.</span></span> <span data-ttu-id="c40f7-115">Как и в 2/25/2019, Teams пока не поддерживает собственную федерацию, но в Skype для бизнеса Online отсутствует пользователь профиля SIP.</span><span class="sxs-lookup"><span data-stu-id="c40f7-115">As of 2/25/2019, Teams doesn't yet support native federation without the user of the SIP profile being homed in Skype for Business Online.</span></span> <span data-ttu-id="c40f7-116">Дополнительные сведения о настройке учетной записи для гибридного развертывания и перемещении в Teams вы можете найти в разделе [Обновление гибридной среды Skype для бизнеса в Teams](https://docs.microsoft.com/en-us/microsoftteams/upgrade-to-teams-execute-skypeforbusinesshybrid).</span><span class="sxs-lookup"><span data-stu-id="c40f7-116">For more on setting up your account for Hybrid and then moved to Teams, please see [Upgrade Skype for Business Hybrid Deployment to Teams](https://docs.microsoft.com/en-us/microsoftteams/upgrade-to-teams-execute-skypeforbusinesshybrid).</span></span>

## <a name="let-your-teams-users-chat-and-communicate-with-users-in-another-teams-organization"></a><span data-ttu-id="c40f7-117">Предоставление пользователям Teams возможности общаться и общаться с пользователями из другой организации группы</span><span class="sxs-lookup"><span data-stu-id="c40f7-117">Let your Teams users chat and communicate with users in another Teams organization</span></span>

<span data-ttu-id="c40f7-118">Выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="c40f7-118">Follow these steps.</span></span>

### <a name="step-1---make-sure-to-set-up-the-ports-and-urls-that-are-needed"></a><span data-ttu-id="c40f7-119">Шаг 1. Убедитесь, что вы установили нужные порты и URL-адреса.</span><span class="sxs-lookup"><span data-stu-id="c40f7-119">Step 1 - Make sure to set up the ports and URLs that are needed.</span></span>

<span data-ttu-id="c40f7-120">**Наиболее распространенные вопросы, возникающие при настройке обмена данными между деловыми организациями, получают [URL-адреса и диапазоны IP-адресов для Office 365](https://docs.microsoft.com/microsoftteams/office-365-urls-ip-address-ranges) прямо сейчас.**</span><span class="sxs-lookup"><span data-stu-id="c40f7-120">**The most common issue people encounter when setting up business-to-business communication is getting their [Office 365 URLs and IP address ranges](https://docs.microsoft.com/microsoftteams/office-365-urls-ip-address-ranges) right.**</span></span>

### <a name="step-2---enable-your-organization-to-communicate-with-another-teams-organization"></a><span data-ttu-id="c40f7-121">Шаг 2: предоставление Организации возможности общаться с другой организацией группы</span><span class="sxs-lookup"><span data-stu-id="c40f7-121">Step 2 - Enable your organization to communicate with another Teams organization</span></span>

<span data-ttu-id="c40f7-122">![Значок с логотипом](media/teams-logo-30x30.png) Microsoft Teams, в котором **используется центр администрирования Microsoft Teams**</span><span class="sxs-lookup"><span data-stu-id="c40f7-122">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

   1. <span data-ttu-id="c40f7-123">На панели навигации слева перейдите к параметрам >  **уровня Организации\*\*\*\*внешний доступ**.</span><span class="sxs-lookup"><span data-stu-id="c40f7-123">In the left navigation, go to **Org-wide settings** > **External access**.</span></span> 

   2. <span data-ttu-id="c40f7-124">В верхней части страницы **внешнего доступа** нажмите кнопку **внешний доступ** в. \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="c40f7-124">At the top of the **External access** page, click **External access** to **On**.</span></span> 

   3. <span data-ttu-id="c40f7-125">Если вы хотите разрешить всем организациям группы общаться с пользователями в вашей организации, перейдите к действию 5.</span><span class="sxs-lookup"><span data-stu-id="c40f7-125">If you want to allow all Teams organizations to communicate with users in your organization, skip to step 5.</span></span> 
   
   4. <span data-ttu-id="c40f7-126">Если вы хотите ограничить возможности связи с пользователями в Организации, вы можете разрешить доступ только к некоторым доменам, кроме некоторых, или только для определенных организаций.</span><span class="sxs-lookup"><span data-stu-id="c40f7-126">If you want to limit which organizations can communicate with users in your organization you can either allow all but some domains, or only allow specific organizations.</span></span> <span data-ttu-id="c40f7-127">Чтобы разрешить все домены, кроме некоторых, выберите команду **Добавить домен**, чтобы заблокировать их.</span><span class="sxs-lookup"><span data-stu-id="c40f7-127">To allow all but some domains, add the domains you want to block by clicking **Add domain**.</span></span> <span data-ttu-id="c40f7-128">В области **Добавить домен** введите доменное имя, нажмите кнопку заблокировано, \*\*\*\* а затем — **Готово**.</span><span class="sxs-lookup"><span data-stu-id="c40f7-128">In the **Add a domain** pane, put in the domain name, click **Blocked** and then **Done**.</span></span> <span data-ttu-id="c40f7-129">Чтобы ограничить связь с определенным организатиоинс, добавьте эти домены в список с **разрешенным**состоянием.</span><span class="sxs-lookup"><span data-stu-id="c40f7-129">To limit communications to specific organizatioins, add those domains to the list with a status of **Allowed**.</span></span> <span data-ttu-id="c40f7-130">После того как вы добавите в список разрешений какой – либо домен, связь с другими организациями будет ограничена только теми организациями, домены которых находятся в списке разрешенных.</span><span class="sxs-lookup"><span data-stu-id="c40f7-130">Once you have added any domain to the Allow list, communications to other organizations will be limited to only those organizations whose domains are in the Allow list.</span></span> 
   
   5. <span data-ttu-id="c40f7-131">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="c40f7-131">Click **Save**.</span></span> 

   6. <span data-ttu-id="c40f7-132">Убедитесь в том, что администратор в организации "другие команды" производит те же действия.</span><span class="sxs-lookup"><span data-stu-id="c40f7-132">Then make sure the admin in the other Teams  organization does these same steps.</span></span> <span data-ttu-id="c40f7-133">Например, в списке **разрешенных доменов** администратор должен ввести домен для своей организации, если он не ограничивает возможности взаимодействия с пользователями.</span><span class="sxs-lookup"><span data-stu-id="c40f7-133">For example, in their **allowed domains** list, their admin needs to enter the domain for your business if they limit which organizations can communicate with their users.</span></span> 

### <a name="step-3---test-it"></a><span data-ttu-id="c40f7-134">Шаг 3-Проверка</span><span class="sxs-lookup"><span data-stu-id="c40f7-134">Step 3 - Test it</span></span>
<span data-ttu-id="c40f7-135">Для проверки настройки вам понадобится пользователь Teams, который не защищен брандмауэром.</span><span class="sxs-lookup"><span data-stu-id="c40f7-135">To test your setup, you need a Teams user who's not behind your firewall.</span></span>
  
   1. <span data-ttu-id="c40f7-136">После того как вы и администратор вашей организации изменили настройки **внешнего доступа** , вы должны быть хорошо доступны.</span><span class="sxs-lookup"><span data-stu-id="c40f7-136">After you and the admin from the organization have changed the **External access** settings, you should be good to go.</span></span>
    
   2. <span data-ttu-id="c40f7-137">В приложении Teams найдите пользователя по адресу электронной почты и отправьте запрос на чат.</span><span class="sxs-lookup"><span data-stu-id="c40f7-137">In the Teams app, search for the person by email address, and send a request to chat.</span></span>
    
   3. <span data-ttu-id="c40f7-138">Попросите контакта группы отправить вам запрос на чат.</span><span class="sxs-lookup"><span data-stu-id="c40f7-138">Ask your Teams contact to send you a request to chat.</span></span> <span data-ttu-id="c40f7-139">Если вы не получили запрос, проблема заключается в параметрах брандмауэра (предполагая, что параметры брандмауэра уже подтверждены).</span><span class="sxs-lookup"><span data-stu-id="c40f7-139">If you don't receive their request, the problem is your firewall settings (assuming they've already confirmed their firewall settings are correct).</span></span>
    
   4. <span data-ttu-id="c40f7-140">Еще один способ проверить, является ли проблема брандмауэром, — это перейти к расположению Wi-Fi, а не за брандмауэром, например кафе, и с помощью Teams отправьте запрос на ваш собеседник в чат.</span><span class="sxs-lookup"><span data-stu-id="c40f7-140">Another way to test whether the problem is your firewall is to go to a wifi location not behind your firewall such as a coffee shop, and use Teams to send a request to your contact to chat.</span></span> <span data-ttu-id="c40f7-141">Если сообщение находится на рабочем этапе, но не на работе, вы знаете, что проблема связана с брандмауэром.</span><span class="sxs-lookup"><span data-stu-id="c40f7-141">If the message goes through there, but not when you're at work, then you know the problem is your firewall.</span></span>

## <a name="communicate-with-users-in-a-skype-for-business-online-organization"></a><span data-ttu-id="c40f7-142">Общение с пользователями в Организации Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="c40f7-142">Communicate with users in a Skype for Business Online organization</span></span>

<span data-ttu-id="c40f7-143">Если вы настраиваете, чтобы пользователи Teams могли находить и общаться с пользователями в Организации Skype для бизнеса, которые ограничивают круг лиц, которые могут обращаться к своим пользователям, вам будет предложено администратору этой Организации выполнить указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="c40f7-143">If you are setting it up to let your Teams users find and contact users that are in a Skype for Business organization that limits who can contact their users, you will ask the admin in that organization to follow these steps.</span></span>

<span data-ttu-id="c40f7-144">![Значок, показывающий логотип](media/sfb-logo-30x30.png) Skype для бизнеса, **с помощью центра администрирования Skype для бизнеса**</span><span class="sxs-lookup"><span data-stu-id="c40f7-144">![An icon showing the Skype for Business logo](media/sfb-logo-30x30.png) **Using Skype for Business admin center**</span></span> 

<span data-ttu-id="c40f7-145">У администратора в этой Организации выполняются следующие действия:</span><span class="sxs-lookup"><span data-stu-id="c40f7-145">Have the admin in that organization do these steps:</span></span>
    
1. <span data-ttu-id="c40f7-146">В центре администрирования Office 365 перейдите в раздел **центры** > администрирования**Teams _амп_ Skype** > **Legacy Portal**.</span><span class="sxs-lookup"><span data-stu-id="c40f7-146">In the Office 365 admin center, go to **Admin Centers** > **Teams & Skype** > **Legacy portal**.</span></span>
  
2. <span data-ttu-id="c40f7-147">В **центре администрирования Skype для бизнеса выберите "\*\*\*\*внешняя связь** **Организации** > ".</span><span class="sxs-lookup"><span data-stu-id="c40f7-147">In the **Skype for Business admin center**, choose **Organization** > **External communications**.</span></span>
    
3. <span data-ttu-id="c40f7-148">Чтобы настроить связь с конкретными организациями или пользователями в другом домене, в раскрывающемся списке выберите **только для разрешенных доменов**.</span><span class="sxs-lookup"><span data-stu-id="c40f7-148">To set up communication with a specific business or with users in another domain, in the drop-down box, choose **On only for allowed domains**.</span></span>
    
    <span data-ttu-id="c40f7-149">Кроме того, если вы хотите включить связь с другими пользователями в мире, у которых есть открытые политики Skype для бизнеса, выберите включить для всех пользователей, **за исключением заблокированных доменов**.</span><span class="sxs-lookup"><span data-stu-id="c40f7-149">OR, if they want to enable communication with everyone else in the world who has open Skype for Business policies, choose **On except for blocked domains**.</span></span> <span data-ttu-id="c40f7-150">Это значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="c40f7-150">This is the default setting.</span></span>
    
4. <span data-ttu-id="c40f7-151">В разделе **Заблокированные или разрешенные домены**выберите **+** и добавьте имя домена, который вы хотите разрешить.</span><span class="sxs-lookup"><span data-stu-id="c40f7-151">Under **Blocked or allowed domains**, choose **+** and add the name of the domain you want to allow.</span></span> <span data-ttu-id="c40f7-152">Убедитесь, что администратор из другой организации производит те же действия.</span><span class="sxs-lookup"><span data-stu-id="c40f7-152">Make sure the admin in the other organization does these same steps.</span></span> <span data-ttu-id="c40f7-153">Например, в списке **разрешенных доменов** администратор должен ввести домен для вашего бизнеса.</span><span class="sxs-lookup"><span data-stu-id="c40f7-153">For example, in their **allowed domains** list, their admin needs to enter the domain for your business.</span></span>
    
### <a name="related-topics"></a><span data-ttu-id="c40f7-154">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="c40f7-154">Related topics</span></span>

<span data-ttu-id="c40f7-155">[Вход в Microsoft Teams](sign-in-teams.md)
[для конечных пользователей](enduser-training.md) в Teams</span><span class="sxs-lookup"><span data-stu-id="c40f7-155">[Sign in to Microsoft Teams](sign-in-teams.md)
[End user training for Teams](enduser-training.md)</span></span>

