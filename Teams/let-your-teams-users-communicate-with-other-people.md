---
title: Общение с пользователями Teams из других организаций
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
ms.audience: Admin
search.appverid: MET150
appliesto:
- Microsoft Teams
localization_priority: Normal
description: Узнайте, как настроить группы сотрудников могут пользователи могут взаимодействовать с пользователями в другой организации.
ms.openlocfilehash: 6c61c8d932dfe72c1d7764ce78701c0b1e3acfc0
ms.sourcegitcommit: 85c34280977fb2c15c8a43874a20e9492bdca57f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/07/2019
ms.locfileid: "30460302"
---
# <a name="let-your-teams-users-chat-and-communicate-with-users-in-another-teams-organization"></a><span data-ttu-id="9f191-103">Сообщите разговор группам пользователей и взаимодействовать с пользователями в другой организации групп</span><span class="sxs-lookup"><span data-stu-id="9f191-103">Let your Teams users chat and communicate with users in another Teams organization</span></span>

<span data-ttu-id="9f191-104">Действия, описанные в этом приведены в статье случаи использования:</span><span class="sxs-lookup"><span data-stu-id="9f191-104">Use the steps in this article when:</span></span>
  
- <span data-ttu-id="9f191-105">У вас есть пользователи в различных доменах в бизнесе.</span><span class="sxs-lookup"><span data-stu-id="9f191-105">You have users in different domains in your business.</span></span> <span data-ttu-id="9f191-106">Например Rob@ContosoEast.com и Ann@ContosoWest.com.</span><span class="sxs-lookup"><span data-stu-id="9f191-106">For example, Rob@ContosoEast.com and Ann@ContosoWest.com.</span></span>
    
- <span data-ttu-id="9f191-107">Чтобы получатели, в вашей организации для работы групп пользователей в конкретных предприятия за пределами вашей организации.</span><span class="sxs-lookup"><span data-stu-id="9f191-107">You want the people in your organization to use Teams to contact people in specific businesses outside of your organization.</span></span>
    
- <span data-ttu-id="9f191-108">Предполагается, что у других пользователей в мире, который использует группы должны иметь возможность поиска и связи с вами с помощью свой адрес электронной почты.</span><span class="sxs-lookup"><span data-stu-id="9f191-108">You want anyone else in the world who uses Teams to be able to find and contact you, using your email address.</span></span> <span data-ttu-id="9f191-109">Если вы и другой пользователь Включение внешнего доступа и разрешить домены друг друга, будет работать.</span><span class="sxs-lookup"><span data-stu-id="9f191-109">If you and another user both enable External Access and allow each other's domains, this will work.</span></span> <span data-ttu-id="9f191-110">Если это не работает, других пользователей должны убедитесь, что его или ее конфигурации не блокирует вашего домена.</span><span class="sxs-lookup"><span data-stu-id="9f191-110">If it doesn't work, the other user should make sure his or her configuration isn't blocking your domain.</span></span>

<span data-ttu-id="9f191-111">Это позволит пользователям находить, позвонить и отправлять вам мгновенные сообщения, а также назначать собрания с вами.</span><span class="sxs-lookup"><span data-stu-id="9f191-111">This will allow users to find, call, and send you instant messages, as well as set up meetings with you.</span></span> <span data-ttu-id="9f191-112">Если необходимо, чтобы внешние пользователи должны иметь доступ к группам и каналы, доступ к гостевой может быть лучший способ перехода.</span><span class="sxs-lookup"><span data-stu-id="9f191-112">If you want external users to have access to teams and channels, guest access might be a better way to go.</span></span> <span data-ttu-id="9f191-113">Выполните действия, описанные в данной статье, убедитесь, что для [включения доступа](set-up-guests.md) , чтобы пользователи могут взаимодействовать.</span><span class="sxs-lookup"><span data-stu-id="9f191-113">Follow the steps in this article and make sure to [turn on guest access](set-up-guests.md) so that users can communicate.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="9f191-114">Чтобы в настоящее время федерацию в клиенте группами Майкрософт для внешних пользователей за пределами вашей организации, который не является в настоящее время гостя AAD/клиента, необходимо правильно настроить для гибридной среды и перемещено в Скайп для бизнеса в Интернет.</span><span class="sxs-lookup"><span data-stu-id="9f191-114">In order to currently federate within the Microsoft Teams client to an external user outside of your organization who's not currently a Guest of your AAD/Tenant, you must be correctly setup for hybrid and moved to Skype for Business Online.</span></span> <span data-ttu-id="9f191-115">По состоянию на 2/25/2019 группы еще не поддерживает собственный федерации без уведомления пользователя, профиль SIP расположенным в Скайп для бизнеса в Интернет.</span><span class="sxs-lookup"><span data-stu-id="9f191-115">As of 2/25/2019, Teams doesn't yet support native federation without the user of the SIP profile being homed in Skype for Business Online.</span></span> <span data-ttu-id="9f191-116">Для получения дополнительных на параметр вверх свою учетную запись для гибридной среды и затем перемещен в группы, можно найти в [Обновление Скайп для бизнеса гибридного развертывания для группы](https://docs.microsoft.com/en-us/microsoftteams/upgrade-to-teams-execute-skypeforbusinesshybrid).</span><span class="sxs-lookup"><span data-stu-id="9f191-116">For more on setting up your account for Hybrid and then moved to Teams, please see [Upgrade Skype for Business Hybrid Deployment to Teams](https://docs.microsoft.com/en-us/microsoftteams/upgrade-to-teams-execute-skypeforbusinesshybrid).</span></span>

## <a name="let-your-teams-users-chat-and-communicate-with-users-in-another-teams-organization"></a><span data-ttu-id="9f191-117">Сообщите разговор группам пользователей и взаимодействовать с пользователями в другой организации групп</span><span class="sxs-lookup"><span data-stu-id="9f191-117">Let your Teams users chat and communicate with users in another Teams organization</span></span>

<span data-ttu-id="9f191-118">Выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="9f191-118">Follow these steps.</span></span>

### <a name="step-1---make-sure-to-set-up-the-ports-and-urls-that-are-needed"></a><span data-ttu-id="9f191-119">Шаг 1 - Убедитесь в том настроить порты и URL-адресов, которые требуются.</span><span class="sxs-lookup"><span data-stu-id="9f191-119">Step 1 - Make sure to set up the ports and URLs that are needed.</span></span>

<span data-ttu-id="9f191-120">**Наиболее распространенные проблемы, которые людей возникнуть при настройке бизнес делового общения правильного их [Office 365 URL-адреса и диапазоны IP-адресов](https://docs.microsoft.com/microsoftteams/office-365-urls-ip-address-ranges) .**</span><span class="sxs-lookup"><span data-stu-id="9f191-120">**The most common issue people encounter when setting up business-to-business communication is getting their [Office 365 URLs and IP address ranges](https://docs.microsoft.com/microsoftteams/office-365-urls-ip-address-ranges) right.**</span></span>

### <a name="step-2---enable-your-organization-to-communicate-with-another-teams-organization"></a><span data-ttu-id="9f191-121">Шаг 2 - включить вашей организации для взаимодействия с другой организацией групп</span><span class="sxs-lookup"><span data-stu-id="9f191-121">Step 2 - Enable your organization to communicate with another Teams organization</span></span>

<span data-ttu-id="9f191-122">![команды логотип 30x30.png](media/teams-logo-30x30.png) **с помощью центра администрирования группами Майкрософт**</span><span class="sxs-lookup"><span data-stu-id="9f191-122">![teams-logo-30x30.png](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

   1. <span data-ttu-id="9f191-123">В левой области переходов, перейдите в раздел **масштабе организации параметры** > **внешнего доступа**.</span><span class="sxs-lookup"><span data-stu-id="9f191-123">In the left navigation, go to **Org-wide settings** > **External access**.</span></span> 

   2. <span data-ttu-id="9f191-124">В верхней части страницы **внешнего доступа** нажмите кнопку **внешний доступ** к **на**.</span><span class="sxs-lookup"><span data-stu-id="9f191-124">At the top of the **External access** page, click **External access** to **On**.</span></span> 

   3. <span data-ttu-id="9f191-125">Если вы хотите разрешить всей организации групп для взаимодействия с пользователями в вашей организации, перейдите к действию 5.</span><span class="sxs-lookup"><span data-stu-id="9f191-125">If you want to allow all Teams organizations to communicate with users in your organization, skip to step 5.</span></span> 
   
   4. <span data-ttu-id="9f191-126">Если предполагается ограничить какие организации могут взаимодействовать с пользователями в организации можно разрешить лишь некоторые домены или разрешить только определенные организаций.</span><span class="sxs-lookup"><span data-stu-id="9f191-126">If you want to limit which organizations can communicate with users in your organization you can either allow all but some domains, or only allow specific organizations.</span></span> <span data-ttu-id="9f191-127">Чтобы разрешить лишь несколько доменов, добавьте домены, которые необходимо заблокировать, нажав кнопку **Добавить домен**.</span><span class="sxs-lookup"><span data-stu-id="9f191-127">To allow all but some domains, add the domains you want to block by clicking **Add domain**.</span></span> <span data-ttu-id="9f191-128">В области **Добавить домен** , поместите в поле имя домена нажмите кнопку **заблокирован** , а затем **выполнить**.</span><span class="sxs-lookup"><span data-stu-id="9f191-128">In the **Add a domain** pane, put in the domain name, click **Blocked** and then **Done**.</span></span> <span data-ttu-id="9f191-129">Чтобы ограничить коммуникаций для определенных organizatioins, добавьте эти домены в список с состоянием **Alowed**.</span><span class="sxs-lookup"><span data-stu-id="9f191-129">To limit communications to specific organizatioins, add those domains to the list with a status of **Alowed**.</span></span> <span data-ttu-id="9f191-130">После добавления любого домена в список разрешенных связь с другими организациями возможен только организациям, домены, в списке разрешенных.</span><span class="sxs-lookup"><span data-stu-id="9f191-130">Once you have added any domain to the Allow list, communications to other organizations will be limited to only those organizations whose domains are in the Allow list.</span></span> 
   
   5. <span data-ttu-id="9f191-131">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="9f191-131">Click **Save**.</span></span> 

   6. <span data-ttu-id="9f191-132">Убедитесь в том, что эти шаги не администратора в организации других групп.</span><span class="sxs-lookup"><span data-stu-id="9f191-132">Then make sure the admin in the other Teams  organization does these same steps.</span></span> <span data-ttu-id="9f191-133">К примеру в список **разрешенных доменов** их администрирования необходимо войти в домен для бизнеса, если они ограничить которых организации могут взаимодействовать с своим пользователям.</span><span class="sxs-lookup"><span data-stu-id="9f191-133">For example, in their **allowed domains** list, their admin needs to enter the domain for your business if they limit which organizations can communicate with their users.</span></span> 

### <a name="step-3---test-it"></a><span data-ttu-id="9f191-134">Шаг 3 - протестируйте</span><span class="sxs-lookup"><span data-stu-id="9f191-134">Step 3 - Test it</span></span>
<span data-ttu-id="9f191-135">Чтобы проверить настройку, необходимо группы пользователь, который не находится за брандмауэром.</span><span class="sxs-lookup"><span data-stu-id="9f191-135">To test your setup, you need a Teams user who's not behind your firewall.</span></span>
  
   1. <span data-ttu-id="9f191-136">После завершения изменения параметров **внешнего доступа** и администрирования организации должен быть достаточно просто.</span><span class="sxs-lookup"><span data-stu-id="9f191-136">After you and the admin from the organization have changed the **External access** settings, you should be good to go.</span></span>
    
   2. <span data-ttu-id="9f191-137">В окне приложения команды Поиск пользователя с адресом электронной почты и отправить запрос в чате.</span><span class="sxs-lookup"><span data-stu-id="9f191-137">In the Teams app, search for the person by email address, and send a request to chat.</span></span>
    
   3. <span data-ttu-id="9f191-138">Попросите контакт группы отправляет запрос на беседу.</span><span class="sxs-lookup"><span data-stu-id="9f191-138">Ask your Teams contact to send you a request to chat.</span></span> <span data-ttu-id="9f191-139">Если вы не получите свой запрос, проблема заключается в настройках брандмауэра (если они уже подтверждения правильности их параметры брандмауэра).</span><span class="sxs-lookup"><span data-stu-id="9f191-139">If you don't receive their request, the problem is your firewall settings (assuming they've already confirmed their firewall settings are correct).</span></span>
    
   4. <span data-ttu-id="9f191-140">Другой способ проверки, является ли проблема брандмауэра — это расположение wifi не за брандмауэром, таких как кафе и использование команды Отправить запрос контакту чата.</span><span class="sxs-lookup"><span data-stu-id="9f191-140">Another way to test whether the problem is your firewall is to go to a wifi location not behind your firewall such as a coffee shop, and use Teams to send a request to your contact to chat.</span></span> <span data-ttu-id="9f191-141">Если сообщение проходит через существует, но не в том случае, когда вы находитесь на работе, это значит, проблема является брандмауэра.</span><span class="sxs-lookup"><span data-stu-id="9f191-141">If the message goes through there, but not when you're at work, then you know the problem is your firewall.</span></span>

## <a name="communicate-with-users-in-a-skype-for-business-online-organization"></a><span data-ttu-id="9f191-142">Взаимодействие с пользователями в Скайп для бизнеса сети организации</span><span class="sxs-lookup"><span data-stu-id="9f191-142">Communicate with users in a Skype for Business Online organization</span></span>

<span data-ttu-id="9f191-143">Если вы настраиваете его сообщите поиска группам пользователей и контактов пользователей, расположенных в Скайп для организации, которая ограничивает пользователей, которые смогут связаться своим пользователям, будет попросите администратора в организации необходимо выполнить следующие действия.</span><span class="sxs-lookup"><span data-stu-id="9f191-143">If you are setting it up to let your Teams users find and contact users that are in a Skype for Business organization that limits who can contact their users, you will ask the admin in that organization to follow these steps.</span></span>

<span data-ttu-id="9f191-144">![sfb логотип 30x30.png](media/sfb-logo-30x30.png) **С помощью Скайп по центру администрирования бизнеса**</span><span class="sxs-lookup"><span data-stu-id="9f191-144">![sfb-logo-30x30.png](media/sfb-logo-30x30.png) **Using Skype for Business admin center**</span></span> 

<span data-ttu-id="9f191-145">У администратора, то организация выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="9f191-145">Have the admin in that organization do these steps:</span></span>
    
1. <span data-ttu-id="9f191-146">В центре администрирования Office 365 перейдите на **Центры администрирования** > **команды & Скайп** > **портала прежних версий**.</span><span class="sxs-lookup"><span data-stu-id="9f191-146">In the Office 365 admin center, go to **Admin Centers** > **Teams & Skype** > **Legacy portal**.</span></span>
  
2. <span data-ttu-id="9f191-147">В **Центр администрирования Skype для бизнеса**выберите пункты **оОрганизация** > **Ввнешняяие связьи**.</span><span class="sxs-lookup"><span data-stu-id="9f191-147">In the **Skype for Business admin center**, choose **Organization** > **External communications**.</span></span>
    
3. <span data-ttu-id="9f191-148">Чтобы настроить связь с определенным бизнес- или с пользователями в другом домене, в раскрывающемся списке выберите **на только для разрешенных доменов**.</span><span class="sxs-lookup"><span data-stu-id="9f191-148">To set up communication with a specific business or with users in another domain, in the drop-down box, choose **On only for allowed domains**.</span></span>
    
    <span data-ttu-id="9f191-149">ИЛИ, если требуется разрешить связь с все остальные в мире, имеющий открыть Скайп для бизнес-политик, выберите **на за исключением заблокированных доменов**.</span><span class="sxs-lookup"><span data-stu-id="9f191-149">OR, if they want to enable communication with everyone else in the world who has open Skype for Business policies, choose **On except for blocked domains**.</span></span> <span data-ttu-id="9f191-150">Это параметр по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="9f191-150">This is the default setting.</span></span>
    
4. <span data-ttu-id="9f191-151">В списке **заблокированных или разрешенных доменов**, выберите **+** и добавьте имя домена, чтобы разрешить.</span><span class="sxs-lookup"><span data-stu-id="9f191-151">Under **Blocked or allowed domains**, choose **+** and add the name of the domain you want to allow.</span></span> <span data-ttu-id="9f191-152">Убедитесь в том, что эти шаги не администратора в другой организации.</span><span class="sxs-lookup"><span data-stu-id="9f191-152">Make sure the admin in the other organization does these same steps.</span></span> <span data-ttu-id="9f191-153">К примеру в список **разрешенных доменов** их администрирования необходимо войти в домен для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="9f191-153">For example, in their **allowed domains** list, their admin needs to enter the domain for your business.</span></span>
    
### <a name="related-topics"></a><span data-ttu-id="9f191-154">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="9f191-154">Related topics</span></span>

<span data-ttu-id="9f191-155">[Вход на портал группами Майкрософт](sign-in-teams.md)
[Обучение конечных пользователей для групп](enduser-training.md)</span><span class="sxs-lookup"><span data-stu-id="9f191-155">[Sign in to Microsoft Teams](sign-in-teams.md)
[End user training for Teams](enduser-training.md)</span></span>

