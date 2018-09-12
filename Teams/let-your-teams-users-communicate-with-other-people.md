---
title: Взаимодействие с объектом с группами пользователей в другой организации
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection: Strat_MT_TeamsAdmin
ms.audience: Admin
search.appverid: MET150
appliesto:
- Microsoft Teams
localization_priority: Normal
description: Узнайте, как настроить группы сотрудников могут пользователи могут взаимодействовать с пользователями в другой организации.
ms.openlocfilehash: da76d75ba44215b11b68550fa06d1fab87f19e56
ms.sourcegitcommit: 6732f56535d60a46e6998cde64103e8530dd6452
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/11/2018
ms.locfileid: "23937829"
---
# <a name="let-your-teams-users-chat-and-communicate-with-users-in-another-teams-organization"></a><span data-ttu-id="6529e-103">Сообщите разговор группам пользователей и взаимодействовать с пользователями в другой организации групп</span><span class="sxs-lookup"><span data-stu-id="6529e-103">Let your Teams users chat and communicate with users in another Teams organization</span></span>

<span data-ttu-id="6529e-104">Действия, описанные в этом приведены в статье случаи использования:</span><span class="sxs-lookup"><span data-stu-id="6529e-104">Use the steps in this article when:</span></span>
  
- <span data-ttu-id="6529e-105">У вас есть пользователи в различных доменах в бизнесе.</span><span class="sxs-lookup"><span data-stu-id="6529e-105">You have users in different domains in your business.</span></span> <span data-ttu-id="6529e-106">Например Rob@ContosoEast.com и Ann@ContosoWest.com.</span><span class="sxs-lookup"><span data-stu-id="6529e-106">For example, Rob@ContosoEast.com and Ann@ContosoWest.com.</span></span>
    
- <span data-ttu-id="6529e-107">Чтобы получатели, в вашей организации для работы групп пользователей в конкретных предприятия за пределами вашей организации.</span><span class="sxs-lookup"><span data-stu-id="6529e-107">You want the people in your organization to use Teams to contact people in specific businesses outside of your organization.</span></span>
    
- <span data-ttu-id="6529e-108">Предполагается, что у других пользователей в мире, который использует группы должны иметь возможность поиска и связи с вами с помощью свой адрес электронной почты.</span><span class="sxs-lookup"><span data-stu-id="6529e-108">You want anyone else in the world who uses Teams to be able to find and contact you, using your email address.</span></span> <span data-ttu-id="6529e-109">Если вы и другой пользователь Включение внешнего доступа и разрешить домены друг друга, будет работать.</span><span class="sxs-lookup"><span data-stu-id="6529e-109">If you and another user both enable External Access and allow each other's domains, this will work.</span></span> <span data-ttu-id="6529e-110">Если это не работает, других пользователей должны убедитесь, что его или ее конфигурации не блокирует вашего домена.</span><span class="sxs-lookup"><span data-stu-id="6529e-110">If it doesn't work, the other user should make sure his or her configuration isn't blocking your domain.</span></span>

<span data-ttu-id="6529e-111">Выполните следующие действия</span><span class="sxs-lookup"><span data-stu-id="6529e-111">Follow these steps:</span></span>

## <a name="let-your-teams-users-chat-and-communicate-with-users-in-another-teams-organization"></a><span data-ttu-id="6529e-112">Сообщите разговор группам пользователей и взаимодействовать с пользователями в другой организации групп</span><span class="sxs-lookup"><span data-stu-id="6529e-112">Let your Teams users chat and communicate with users in another Teams organization</span></span>

### <a name="step-1---make-sure-to-set-up-the-ports-and-urls-that-are-needed"></a><span data-ttu-id="6529e-113">Шаг 1 - Убедитесь в том настроить порты и URL-адресов, которые требуются.</span><span class="sxs-lookup"><span data-stu-id="6529e-113">Step 1 - Make sure to set up the ports and URLs that are needed.</span></span>

<span data-ttu-id="6529e-114">**Наиболее распространенные проблемы, которые людей возникнуть при настройке бизнес делового общения правильного их [Office 365 URL-адреса и диапазоны IP-адресов](https://docs.microsoft.com/microsoftteams/office-365-urls-ip-address-ranges) .**</span><span class="sxs-lookup"><span data-stu-id="6529e-114">**The most common issue people encounter when setting up business-to-business communication is getting their [Office 365 URLs and IP address ranges](https://docs.microsoft.com/microsoftteams/office-365-urls-ip-address-ranges) right.**</span></span>

### <a name="step-2---enable-your-organization-to-communicate-with-another-teams-organization"></a><span data-ttu-id="6529e-115">Шаг 2 - включить вашей организации для взаимодействия с другой организацией групп</span><span class="sxs-lookup"><span data-stu-id="6529e-115">Step 2 - Enable your organization to communicate with another Teams organization</span></span>

<span data-ttu-id="6529e-116">![команды логотип 30x30.png](media/teams-logo-30x30.png) **с помощью групп Майкрософт и Скайп по центру администрирования бизнеса**</span><span class="sxs-lookup"><span data-stu-id="6529e-116">![teams-logo-30x30.png](media/teams-logo-30x30.png) **Using the Microsoft Teams and Skype for Business Admin Center**</span></span>

   1. <span data-ttu-id="6529e-117">В левой области переходов, перейдите в раздел **масштабе организации параметры** > **внешнего доступа**.</span><span class="sxs-lookup"><span data-stu-id="6529e-117">In the left navigation, go to **Org-wide settings** > **External access**.</span></span> 

   2. <span data-ttu-id="6529e-118">В верхней части страницы **внешнего доступа** нажмите кнопку **внешний доступ** к **на**.</span><span class="sxs-lookup"><span data-stu-id="6529e-118">At the top of the **External access** page, click **External access** to **On**.</span></span> 

   3. <span data-ttu-id="6529e-119">Если вы хотите разрешить всей организации групп для взаимодействия с пользователями в вашей организации, перейдите к действию 5.</span><span class="sxs-lookup"><span data-stu-id="6529e-119">If you want to allow all Teams organizations to communicate with users in your organization, skip to step 5.</span></span> 
   
   4. <span data-ttu-id="6529e-120">Если вы хотите ограничение которого организации могут взаимодействовать с пользователями в вашей организации, добавьте другой организации домен в список разрешенных, нажав кнопку **Добавить домен**.</span><span class="sxs-lookup"><span data-stu-id="6529e-120">If you want to limit which organizations can communicate with users in your organization, add the other organization's domain to the allowed list by clicking **Add domain**.</span></span> <span data-ttu-id="6529e-121">В области **Добавить домен** **разрешено** , а затем **выполнить**поместите в списке выберите имя домена.</span><span class="sxs-lookup"><span data-stu-id="6529e-121">In the **Add a domain** pane, put in the domain name click **Allowed** and then **Done**.</span></span>

   4. <span data-ttu-id="6529e-122">Также можно отправить электронное письмо пользователю с помощью параметров аудиоконференции, выбрав на странице свойств аудиоконференции для пользователя параметр **Отправить информацию о конференции по электронной почте**.</span><span class="sxs-lookup"><span data-stu-id="6529e-122">Click **Save**.</span></span> 

   5. <span data-ttu-id="6529e-123">Убедитесь в том, что эти шаги не администратора в организации других групп.</span><span class="sxs-lookup"><span data-stu-id="6529e-123">Then make sure the admin in the other Teams  organization does these same steps.</span></span> <span data-ttu-id="6529e-124">К примеру в список **разрешенных доменов** их администрирования необходимо войти в домен для бизнеса, если они ограничить которых организации могут взаимодействовать с своим пользователям.</span><span class="sxs-lookup"><span data-stu-id="6529e-124">For example, in their **allowed domains** list, their admin needs to enter the domain for your business if they limit which organizations can communicate with their users.</span></span> 

### <a name="step-3---test-it"></a><span data-ttu-id="6529e-125">Шаг 3 - протестируйте</span><span class="sxs-lookup"><span data-stu-id="6529e-125">Step 3 - Test it</span></span>
<span data-ttu-id="6529e-126">Чтобы проверить настройку, необходимо группы пользователь, который не находится за брандмауэром.</span><span class="sxs-lookup"><span data-stu-id="6529e-126">To test your setup, you need a Teams user who's not behind your firewall.</span></span>
  
   1. <span data-ttu-id="6529e-127">После завершения изменения параметров **внешнего доступа** и администрирования организации должен быть достаточно просто.</span><span class="sxs-lookup"><span data-stu-id="6529e-127">After you and the admin from the organization have changed the **External access** settings, you should be good to go.</span></span>
    
   2. <span data-ttu-id="6529e-128">В окне приложения команды Поиск пользователя с адресом электронной почты и отправить запрос в чате.</span><span class="sxs-lookup"><span data-stu-id="6529e-128">In the Teams app, search for the person by email address, and send a request to chat.</span></span>
    
   3. <span data-ttu-id="6529e-129">Попросите контакт группы отправляет запрос на беседу.</span><span class="sxs-lookup"><span data-stu-id="6529e-129">Ask your Teams contact to send you a request to chat.</span></span> <span data-ttu-id="6529e-130">Если вы не получите свой запрос, проблема заключается в настройках брандмауэра (если они уже подтверждения правильности их параметры брандмауэра).</span><span class="sxs-lookup"><span data-stu-id="6529e-130">If you don't receive their request, the problem is your firewall settings (assuming they've already confirmed their firewall settings are correct).</span></span>
    
   4. <span data-ttu-id="6529e-131">Другой способ проверки, является ли проблема брандмауэра — это расположение wifi не за брандмауэром, таких как кафе и использование команды Отправить запрос контакту чата.</span><span class="sxs-lookup"><span data-stu-id="6529e-131">Another way to test whether the problem is your firewall is to go to a wifi location not behind your firewall such as a coffee shop, and use Teams to send a request to your contact to chat.</span></span> <span data-ttu-id="6529e-132">Если сообщение проходит через существует, но не в том случае, когда вы находитесь на работе, это значит, проблема является брандмауэра.</span><span class="sxs-lookup"><span data-stu-id="6529e-132">If the message goes through there, but not when you're at work, then you know the problem is your firewall.</span></span>

## <a name="communicate-with-users-in-a-skype-for-business-online-organization"></a><span data-ttu-id="6529e-133">Взаимодействие с пользователями в Скайп для бизнеса сети организации</span><span class="sxs-lookup"><span data-stu-id="6529e-133">Communicate with users in a Skype for Business Online organization</span></span>

<span data-ttu-id="6529e-134">Если вы настраиваете его сообщите поиска группам пользователей и контактов пользователей, расположенных в Скайп для организации, которая ограничивает пользователей, которые смогут связаться своим пользователям, будет попросите администратора в организации необходимо выполнить следующие действия.</span><span class="sxs-lookup"><span data-stu-id="6529e-134">If you are setting it up to let your Teams users find and contact users that are in a Skype for Business organization that limits who can contact their users, you will ask the admin in that organization to follow these steps.</span></span>

<span data-ttu-id="6529e-135">![sfb логотип 30x30.png](media/sfb-logo-30x30.png) **С помощью Скайп по центру администрирования бизнеса**</span><span class="sxs-lookup"><span data-stu-id="6529e-135">![sfb-logo-30x30.png](media/sfb-logo-30x30.png) **Using Skype for Business admin center**</span></span> 

<span data-ttu-id="6529e-136">У администратора, то организация выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="6529e-136">Have the admin in that organization do these steps:</span></span>
    
1. <span data-ttu-id="6529e-137">В центре администрирования Office 365 перейдите на **Центры администрирования** > **группами & Скайп** > **портала прежних версий**.</span><span class="sxs-lookup"><span data-stu-id="6529e-137">In the Office 365 admin center, go to **Admin Centers** > **Teams & Skype** > **Legacy portal**.</span></span>
  
2. <span data-ttu-id="6529e-138">В **Центр администрирования Skype для бизнеса**выберите пункты **оОрганизация** > **Ввнешняяие связьи**.</span><span class="sxs-lookup"><span data-stu-id="6529e-138">In the **Skype for Business admin center**, choose **Organization** > **External communications**.</span></span>
    
3. <span data-ttu-id="6529e-139">Чтобы настроить связь с определенным бизнес- или с пользователями в другом домене, в раскрывающемся списке выберите **на только для разрешенных доменов**.</span><span class="sxs-lookup"><span data-stu-id="6529e-139">To set up communication with a specific business or with users in another domain, in the drop-down box, choose **On only for allowed domains**.</span></span>
    
    <span data-ttu-id="6529e-140">ИЛИ, если требуется разрешить связь с все остальные в мире, имеющий открыть Скайп для бизнес-политик, выберите **на за исключением заблокированных доменов**.</span><span class="sxs-lookup"><span data-stu-id="6529e-140">OR, if they want to enable communication with everyone else in the world who has open Skype for Business policies, choose **On except for blocked domains**.</span></span> <span data-ttu-id="6529e-141">Это значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="6529e-141">This is the default setting.</span></span>
    
4. <span data-ttu-id="6529e-142">В списке **заблокированных или разрешенных доменов**, выберите **+** и добавьте имя домена, чтобы разрешить.</span><span class="sxs-lookup"><span data-stu-id="6529e-142">Under **Blocked or allowed domains**, choose **+** and add the name of the domain you want to allow.</span></span> <span data-ttu-id="6529e-143">Убедитесь в том, что эти шаги не администратора в другой организации.</span><span class="sxs-lookup"><span data-stu-id="6529e-143">Make sure the admin in the other organization does these same steps.</span></span> <span data-ttu-id="6529e-144">К примеру в список **разрешенных доменов** их администрирования необходимо войти в домен для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="6529e-144">For example, in their **allowed domains** list, their admin needs to enter the domain for your business.</span></span>
    
### <a name="related-topics"></a><span data-ttu-id="6529e-145">См. также:</span><span class="sxs-lookup"><span data-stu-id="6529e-145">Related topics</span></span>

<span data-ttu-id="6529e-146">[Вход на портал группами Майкрософт](sign-in-teams.md)
[Обучение конечных пользователей для групп](enduser-training.md)</span><span class="sxs-lookup"><span data-stu-id="6529e-146">[Sign in to Microsoft Teams](sign-in-teams.md)
[End user training for Teams](enduser-training.md)</span></span>

