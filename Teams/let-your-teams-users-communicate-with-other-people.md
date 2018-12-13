---
title: Взаимодействие с объектом с группами пользователей в другой организации
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 09/12/2018
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection: Teams_ITAdmin_Help
ms.audience: Admin
search.appverid: MET150
appliesto:
- Microsoft Teams
localization_priority: Normal
description: Узнайте, как настроить группы сотрудников могут пользователи могут взаимодействовать с пользователями в другой организации.
ms.openlocfilehash: 6fb71e4c9e1461ca920d480336288b06e3111eb2
ms.sourcegitcommit: 1ad4120af98240f1b54c0ca18286598b289a97f1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/12/2018
ms.locfileid: "27240842"
---
# <a name="let-your-teams-users-chat-and-communicate-with-users-in-another-teams-organization"></a><span data-ttu-id="0d3e8-103">Сообщите разговор группам пользователей и взаимодействовать с пользователями в другой организации групп</span><span class="sxs-lookup"><span data-stu-id="0d3e8-103">Let your Teams users chat and communicate with users in another Teams organization</span></span>

<span data-ttu-id="0d3e8-104">Действия, описанные в этом приведены в статье случаи использования:</span><span class="sxs-lookup"><span data-stu-id="0d3e8-104">Use the steps in this article when:</span></span>
  
- <span data-ttu-id="0d3e8-105">У вас есть пользователи в различных доменах в бизнесе.</span><span class="sxs-lookup"><span data-stu-id="0d3e8-105">You have users in different domains in your business.</span></span> <span data-ttu-id="0d3e8-106">Например Rob@ContosoEast.com и Ann@ContosoWest.com.</span><span class="sxs-lookup"><span data-stu-id="0d3e8-106">For example, Rob@ContosoEast.com and Ann@ContosoWest.com.</span></span>
    
- <span data-ttu-id="0d3e8-107">Чтобы получатели, в вашей организации для работы групп пользователей в конкретных предприятия за пределами вашей организации.</span><span class="sxs-lookup"><span data-stu-id="0d3e8-107">You want the people in your organization to use Teams to contact people in specific businesses outside of your organization.</span></span>
    
- <span data-ttu-id="0d3e8-108">Предполагается, что у других пользователей в мире, который использует группы должны иметь возможность поиска и связи с вами с помощью свой адрес электронной почты.</span><span class="sxs-lookup"><span data-stu-id="0d3e8-108">You want anyone else in the world who uses Teams to be able to find and contact you, using your email address.</span></span> <span data-ttu-id="0d3e8-109">Если вы и другой пользователь Включение внешнего доступа и разрешить домены друг друга, будет работать.</span><span class="sxs-lookup"><span data-stu-id="0d3e8-109">If you and another user both enable External Access and allow each other's domains, this will work.</span></span> <span data-ttu-id="0d3e8-110">Если это не работает, других пользователей должны убедитесь, что его или ее конфигурации не блокирует вашего домена.</span><span class="sxs-lookup"><span data-stu-id="0d3e8-110">If it doesn't work, the other user should make sure his or her configuration isn't blocking your domain.</span></span>

<span data-ttu-id="0d3e8-111">Это позволит пользователям находить, позвонить и отправлять вам мгновенные сообщения, а также назначать собрания с вами.</span><span class="sxs-lookup"><span data-stu-id="0d3e8-111">This will allow users to find, call, and send you instant messages, as well as set up meetings with you.</span></span> <span data-ttu-id="0d3e8-112">Если необходимо, чтобы внешние пользователи должны иметь доступ к группам и каналы, доступ к гостевой может быть лучший способ перехода.</span><span class="sxs-lookup"><span data-stu-id="0d3e8-112">If you want external users to have access to teams and channels, guest access might be a better way to go.</span></span> <span data-ttu-id="0d3e8-113">Выполните действия, описанные в данной статье, убедитесь, что для [включения доступа](set-up-guests.md) , чтобы пользователи могут взаимодействовать.</span><span class="sxs-lookup"><span data-stu-id="0d3e8-113">Follow the steps in this article and make sure to [turn on guest access](set-up-guests.md) so that users can communicate.</span></span>

## <a name="let-your-teams-users-chat-and-communicate-with-users-in-another-teams-organization"></a><span data-ttu-id="0d3e8-114">Сообщите разговор группам пользователей и взаимодействовать с пользователями в другой организации групп</span><span class="sxs-lookup"><span data-stu-id="0d3e8-114">Let your Teams users chat and communicate with users in another Teams organization</span></span>

<span data-ttu-id="0d3e8-115">Выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="0d3e8-115">Follow these steps.</span></span>

### <a name="step-1---make-sure-to-set-up-the-ports-and-urls-that-are-needed"></a><span data-ttu-id="0d3e8-116">Шаг 1 - Убедитесь в том настроить порты и URL-адресов, которые требуются.</span><span class="sxs-lookup"><span data-stu-id="0d3e8-116">Step 1 - Make sure to set up the ports and URLs that are needed.</span></span>

<span data-ttu-id="0d3e8-117">**Наиболее распространенные проблемы, которые людей возникнуть при настройке бизнес делового общения правильного их [Office 365 URL-адреса и диапазоны IP-адресов](https://docs.microsoft.com/microsoftteams/office-365-urls-ip-address-ranges) .**</span><span class="sxs-lookup"><span data-stu-id="0d3e8-117">**The most common issue people encounter when setting up business-to-business communication is getting their [Office 365 URLs and IP address ranges](https://docs.microsoft.com/microsoftteams/office-365-urls-ip-address-ranges) right.**</span></span>

### <a name="step-2---enable-your-organization-to-communicate-with-another-teams-organization"></a><span data-ttu-id="0d3e8-118">Шаг 2 - включить вашей организации для взаимодействия с другой организацией групп</span><span class="sxs-lookup"><span data-stu-id="0d3e8-118">Step 2 - Enable your organization to communicate with another Teams organization</span></span>

<span data-ttu-id="0d3e8-119">![команды логотип 30x30.png](media/teams-logo-30x30.png) **с помощью групп Майкрософт и Скайп по центру администрирования бизнеса**</span><span class="sxs-lookup"><span data-stu-id="0d3e8-119">![teams-logo-30x30.png](media/teams-logo-30x30.png) **Using the Microsoft Teams and Skype for Business Admin Center**</span></span>

   1. <span data-ttu-id="0d3e8-120">В левой области переходов, перейдите в раздел **масштабе организации параметры** > **внешнего доступа**.</span><span class="sxs-lookup"><span data-stu-id="0d3e8-120">In the left navigation, go to **Org-wide settings** > **External access**.</span></span> 

   2. <span data-ttu-id="0d3e8-121">В верхней части страницы **внешнего доступа** нажмите кнопку **внешний доступ** к **на**.</span><span class="sxs-lookup"><span data-stu-id="0d3e8-121">At the top of the **External access** page, click **External access** to **On**.</span></span> 

   3. <span data-ttu-id="0d3e8-122">Если вы хотите разрешить всей организации групп для взаимодействия с пользователями в вашей организации, перейдите к действию 5.</span><span class="sxs-lookup"><span data-stu-id="0d3e8-122">If you want to allow all Teams organizations to communicate with users in your organization, skip to step 5.</span></span> 
   
   4. <span data-ttu-id="0d3e8-123">Если предполагается ограничить какие организации могут взаимодействовать с пользователями в организации можно разрешить лишь некоторые домены или разрешить только определенные организаций.</span><span class="sxs-lookup"><span data-stu-id="0d3e8-123">If you want to limit which organizations can communicate with users in your organization you can either allow all but some domains, or only allow specific organizations.</span></span> <span data-ttu-id="0d3e8-124">Чтобы разрешить лишь несколько доменов, добавьте домены, которые необходимо заблокировать, нажав кнопку **Добавить домен**.</span><span class="sxs-lookup"><span data-stu-id="0d3e8-124">To allow all but some domains, add the domains you want to block by clicking **Add domain**.</span></span> <span data-ttu-id="0d3e8-125">В области **Добавить домен** , поместите в поле имя домена нажмите кнопку **заблокирован** , а затем **выполнить**.</span><span class="sxs-lookup"><span data-stu-id="0d3e8-125">In the **Add a domain** pane, put in the domain name, click **Blocked** and then **Done**.</span></span> <span data-ttu-id="0d3e8-126">Чтобы ограничить коммуникаций для определенных organizatioins, добавьте эти домены в список с состоянием **Alowed**.</span><span class="sxs-lookup"><span data-stu-id="0d3e8-126">To limit communications to specific organizatioins, add those domains to the list with a status of **Alowed**.</span></span> <span data-ttu-id="0d3e8-127">После добавления любого домена в список разрешенных связь с другими организациями возможен только организациям, домены, в списке разрешенных.</span><span class="sxs-lookup"><span data-stu-id="0d3e8-127">Once you have added any domain to the Allow list, communications to other organizations will be limited to only those organizations whose domains are in the Allow list.</span></span> 
   
   5. <span data-ttu-id="0d3e8-128">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="0d3e8-128">Click **Save**.</span></span> 

   6. <span data-ttu-id="0d3e8-129">Убедитесь в том, что эти шаги не администратора в организации других групп.</span><span class="sxs-lookup"><span data-stu-id="0d3e8-129">Then make sure the admin in the other Teams  organization does these same steps.</span></span> <span data-ttu-id="0d3e8-130">К примеру в список **разрешенных доменов** их администрирования необходимо войти в домен для бизнеса, если они ограничить которых организации могут взаимодействовать с своим пользователям.</span><span class="sxs-lookup"><span data-stu-id="0d3e8-130">For example, in their **allowed domains** list, their admin needs to enter the domain for your business if they limit which organizations can communicate with their users.</span></span> 

### <a name="step-3---test-it"></a><span data-ttu-id="0d3e8-131">Шаг 3 - протестируйте</span><span class="sxs-lookup"><span data-stu-id="0d3e8-131">Step 3 - Test it</span></span>
<span data-ttu-id="0d3e8-132">Чтобы проверить настройку, необходимо группы пользователь, который не находится за брандмауэром.</span><span class="sxs-lookup"><span data-stu-id="0d3e8-132">To test your setup, you need a Teams user who's not behind your firewall.</span></span>
  
   1. <span data-ttu-id="0d3e8-133">После завершения изменения параметров **внешнего доступа** и администрирования организации должен быть достаточно просто.</span><span class="sxs-lookup"><span data-stu-id="0d3e8-133">After you and the admin from the organization have changed the **External access** settings, you should be good to go.</span></span>
    
   2. <span data-ttu-id="0d3e8-134">В окне приложения команды Поиск пользователя с адресом электронной почты и отправить запрос в чате.</span><span class="sxs-lookup"><span data-stu-id="0d3e8-134">In the Teams app, search for the person by email address, and send a request to chat.</span></span>
    
   3. <span data-ttu-id="0d3e8-135">Попросите контакт группы отправляет запрос на беседу.</span><span class="sxs-lookup"><span data-stu-id="0d3e8-135">Ask your Teams contact to send you a request to chat.</span></span> <span data-ttu-id="0d3e8-136">Если вы не получите свой запрос, проблема заключается в настройках брандмауэра (если они уже подтверждения правильности их параметры брандмауэра).</span><span class="sxs-lookup"><span data-stu-id="0d3e8-136">If you don't receive their request, the problem is your firewall settings (assuming they've already confirmed their firewall settings are correct).</span></span>
    
   4. <span data-ttu-id="0d3e8-137">Другой способ проверки, является ли проблема брандмауэра — это расположение wifi не за брандмауэром, таких как кафе и использование команды Отправить запрос контакту чата.</span><span class="sxs-lookup"><span data-stu-id="0d3e8-137">Another way to test whether the problem is your firewall is to go to a wifi location not behind your firewall such as a coffee shop, and use Teams to send a request to your contact to chat.</span></span> <span data-ttu-id="0d3e8-138">Если сообщение проходит через существует, но не в том случае, когда вы находитесь на работе, это значит, проблема является брандмауэра.</span><span class="sxs-lookup"><span data-stu-id="0d3e8-138">If the message goes through there, but not when you're at work, then you know the problem is your firewall.</span></span>

## <a name="communicate-with-users-in-a-skype-for-business-online-organization"></a><span data-ttu-id="0d3e8-139">Взаимодействие с пользователями в Скайп для бизнеса сети организации</span><span class="sxs-lookup"><span data-stu-id="0d3e8-139">Communicate with users in a Skype for Business Online organization</span></span>

<span data-ttu-id="0d3e8-140">Если вы настраиваете его сообщите поиска группам пользователей и контактов пользователей, расположенных в Скайп для организации, которая ограничивает пользователей, которые смогут связаться своим пользователям, будет попросите администратора в организации необходимо выполнить следующие действия.</span><span class="sxs-lookup"><span data-stu-id="0d3e8-140">If you are setting it up to let your Teams users find and contact users that are in a Skype for Business organization that limits who can contact their users, you will ask the admin in that organization to follow these steps.</span></span>

<span data-ttu-id="0d3e8-141">![sfb логотип 30x30.png](media/sfb-logo-30x30.png) **С помощью Скайп по центру администрирования бизнеса**</span><span class="sxs-lookup"><span data-stu-id="0d3e8-141">![sfb-logo-30x30.png](media/sfb-logo-30x30.png) **Using Skype for Business admin center**</span></span> 

<span data-ttu-id="0d3e8-142">У администратора, то организация выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="0d3e8-142">Have the admin in that organization do these steps:</span></span>
    
1. <span data-ttu-id="0d3e8-143">В центре администрирования Office 365 перейдите на **Центры администрирования** > **группами & Скайп** > **портала прежних версий**.</span><span class="sxs-lookup"><span data-stu-id="0d3e8-143">In the Office 365 admin center, go to **Admin Centers** > **Teams & Skype** > **Legacy portal**.</span></span>
  
2. <span data-ttu-id="0d3e8-144">В **Центр администрирования Skype для бизнеса**выберите пункты **оОрганизация** > **Ввнешняяие связьи**.</span><span class="sxs-lookup"><span data-stu-id="0d3e8-144">In the **Skype for Business admin center**, choose **Organization** > **External communications**.</span></span>
    
3. <span data-ttu-id="0d3e8-145">Чтобы настроить связь с определенным бизнес- или с пользователями в другом домене, в раскрывающемся списке выберите **на только для разрешенных доменов**.</span><span class="sxs-lookup"><span data-stu-id="0d3e8-145">To set up communication with a specific business or with users in another domain, in the drop-down box, choose **On only for allowed domains**.</span></span>
    
    <span data-ttu-id="0d3e8-146">ИЛИ, если требуется разрешить связь с все остальные в мире, имеющий открыть Скайп для бизнес-политик, выберите **на за исключением заблокированных доменов**.</span><span class="sxs-lookup"><span data-stu-id="0d3e8-146">OR, if they want to enable communication with everyone else in the world who has open Skype for Business policies, choose **On except for blocked domains**.</span></span> <span data-ttu-id="0d3e8-147">Это параметр по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="0d3e8-147">This is the default setting.</span></span>
    
4. <span data-ttu-id="0d3e8-148">В списке **заблокированных или разрешенных доменов**, выберите **+** и добавьте имя домена, чтобы разрешить.</span><span class="sxs-lookup"><span data-stu-id="0d3e8-148">Under **Blocked or allowed domains**, choose **+** and add the name of the domain you want to allow.</span></span> <span data-ttu-id="0d3e8-149">Убедитесь в том, что эти шаги не администратора в другой организации.</span><span class="sxs-lookup"><span data-stu-id="0d3e8-149">Make sure the admin in the other organization does these same steps.</span></span> <span data-ttu-id="0d3e8-150">К примеру в список **разрешенных доменов** их администрирования необходимо войти в домен для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="0d3e8-150">For example, in their **allowed domains** list, their admin needs to enter the domain for your business.</span></span>
    
### <a name="related-topics"></a><span data-ttu-id="0d3e8-151">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="0d3e8-151">Related topics</span></span>

<span data-ttu-id="0d3e8-152">[Вход на портал группами Майкрософт](sign-in-teams.md)
[Обучение конечных пользователей для групп](enduser-training.md)</span><span class="sxs-lookup"><span data-stu-id="0d3e8-152">[Sign in to Microsoft Teams](sign-in-teams.md)
[End user training for Teams](enduser-training.md)</span></span>

