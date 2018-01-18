---
title: "Сообщите Скайп для бизнес-пользователям добавлять контакты Скайп"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 12/15/2017
ms.topic: article
ms.assetid: 08666236-1894-42ae-8846-e49232bbc460
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
ms.appliesto: Skype for Business
localization_priority: Normal
ROBOTS: None
f1keywords: None
ms.custom:
- Setup
- LIL_Placement
description: "Узнайте, как для пользователей, которые используют Скайп для бизнес-контакта Скайп для бизнес-пользователей из других организаций и добавить их в свой список контактов. "
ms.openlocfilehash: 1add1f6e907613d1ac536c92b57cfce7f3cdaf66
ms.sourcegitcommit: 8f2e49bc813125137c90de997fb7a6dd74e6d1d5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/15/2017
---
# <a name="let-skype-for-business-users-add-skype-contacts"></a><span data-ttu-id="106d0-103">Сообщите Скайп для бизнес-пользователям добавлять контакты Скайп</span><span class="sxs-lookup"><span data-stu-id="106d0-103">Let Skype for Business users add Skype contacts</span></span>

<span data-ttu-id="106d0-104">С помощью Скайп для бизнеса вашей пользователи могут искать и обмен мгновенными Сообщениями с всех, кто использует Скайп, бесплатное приложение!</span><span class="sxs-lookup"><span data-stu-id="106d0-104">With Skype for Business, your users can search for and IM with everyone who uses Skype, the free app!</span></span> <span data-ttu-id="106d0-105">В этой статье объясняется, что необходимо для этого они могут добавить контакты Скайп.</span><span class="sxs-lookup"><span data-stu-id="106d0-105">This article explains what you need to do so they can add Skype contacts.</span></span> 
  
<span data-ttu-id="106d0-106">В Office 365 для этого необходимо иметь [разрешения администратора](https://support.office.com/en-us/article/da585eea-f576-4f55-a1e0-87090b6aaa9d?ui=en-US&rs=en-US&ad=US) .</span><span class="sxs-lookup"><span data-stu-id="106d0-106">You must have [admin permissions](https://support.office.com/en-us/article/da585eea-f576-4f55-a1e0-87090b6aaa9d?ui=en-US&rs=en-US&ad=US) in Office 365 to do this.</span></span>
  
1. <span data-ttu-id="106d0-107">Выполните вход с учетной записью администратора Office 365 в [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home#/homepage).</span><span class="sxs-lookup"><span data-stu-id="106d0-107">Sign in with your Office 365 admin account at [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home#/homepage).</span></span>
    
2. <span data-ttu-id="106d0-108">В центре администрирования Office 365 перейдите на **Центры администрирования** > **Скайп для бизнеса**.</span><span class="sxs-lookup"><span data-stu-id="106d0-108">In the Office 365 admin center, go to **Admin Centers** > **Skype for Business**.</span></span> 
    
    ![Выберите Скайп по центру администрирования бизнеса.](../images/376a7a45-e6e3-4716-be09-d2f294d885a2.png)
  
3. <span data-ttu-id="106d0-110">В **Скайп по центру администрирования бизнеса**, выберите **организации** > **внешних коммуникаций**.</span><span class="sxs-lookup"><span data-stu-id="106d0-110">In the **Skype for Business admin center**, choose **Organization** > **External communications**.</span></span> 
    
4. <span data-ttu-id="106d0-111">По умолчанию пользователи могут обмениваться данными всех других пользователей в мире Скайп для бизнеса (предполагается, что брандмауэр настроен для этого).</span><span class="sxs-lookup"><span data-stu-id="106d0-111">By default, your users can communicate with all other people in the world who use Skype for Business (assuming your firewall has been configured to allow this).</span></span> 
    
    ![Выберите Let людей используют для взаимодействия с Скайп Скайп для бизнеса.](../images/333789f8-2ea6-4bbd-805b-18130f427999.png)
  
    <span data-ttu-id="106d0-113">Разрешить пользователям общаться с пользователями Скайп, но не требуется их общаться с другими пользователями Скайп для бизнеса, выберите **на только для разрешенных доменов**.</span><span class="sxs-lookup"><span data-stu-id="106d0-113">If you want your users to chat with Skype users, BUT you don't want them to chat with others who use Skype for Business, choose **On only for allowed domains**.</span></span> <span data-ttu-id="106d0-114">При включении контакт с пользователями Скайп skype.com автоматически добавляется в качестве разрешенных доменов в фоновом режиме.</span><span class="sxs-lookup"><span data-stu-id="106d0-114">When you enable contact with Skype users, skype.com is automatically added as an allowed domain behind the scenes.</span></span> 
    
    <span data-ttu-id="106d0-115">Если вы хотите разрешить контакта из других организаций в мире, с помощью Скайп для бизнеса, за исключением конкретного из них, выберите **на за исключением заблокированных доменов**и выберите пункт **+** для добавления эти домены.</span><span class="sxs-lookup"><span data-stu-id="106d0-115">If you want to allow contact from all other businesses in the world using Skype for Business, except specific ones, choose **On except for blocked domains**, and choose **+** to add those domains.</span></span> <span data-ttu-id="106d0-116">Все могут обращаться к вам за исключением людей в этих определенных доменов.</span><span class="sxs-lookup"><span data-stu-id="106d0-116">Everyone will be able to contact you except people on those specific domains.</span></span> <span data-ttu-id="106d0-117">(Некоторые предприятия могут выберите этот параметр, например, если они находятся в судебного и необходимы для обеспечения нет связи с другими бизнес-).</span><span class="sxs-lookup"><span data-stu-id="106d0-117">(Some businesses might choose this option, for example, if they are in litigation and need to ensure there's no contact with the other business.)</span></span>
    
5. <span data-ttu-id="106d0-118">Выберите **, позволяет людям использовать Скайп для бизнеса для взаимодействия с пользователями Скайп за пределами вашей организации**.</span><span class="sxs-lookup"><span data-stu-id="106d0-118">Choose **Let people use Skype for Business to communicate with Skype users outside your organization**.</span></span> 
    
6.  <span data-ttu-id="106d0-119">Если вы используете брандмауэр Windows в режиме, Скайп для бизнеса автоматически открывает необходимые порты.</span><span class="sxs-lookup"><span data-stu-id="106d0-119">If you're using Windows Firewall, Skype for Business opens the required ports automatically.</span></span>
    
    <span data-ttu-id="106d0-120">Если организация использует другое решение для ограничения компьютеры в сети с подключением к Интернету, убедитесь, что существует возможность получить доступ ко всем [IP-адресов и URL-адреса](https://support.office.com/en-us/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2) для подключения к Скайп и поиск в каталоге Скайп клиентских компьютеров.</span><span class="sxs-lookup"><span data-stu-id="106d0-120">If your organization uses another solution to restrict computers on your network from connecting to the Internet, ensure client computers are able to access all of the [IP addresses and URLs](https://support.office.com/en-us/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2) for Skype connectivity and Skype Directory Search.</span></span> <span data-ttu-id="106d0-121">Для этого может потребоваться добавление их в исходящих белый список в конфигурации инфраструктуры брандмауэр или прокси-сервера.</span><span class="sxs-lookup"><span data-stu-id="106d0-121">This may require adding them to the outbound allow list in your firewall or proxy infrastructure configuration.</span></span>
    
7. <span data-ttu-id="106d0-122">**ПОДОЖДИТЕ до 24 часов для тестирования**.</span><span class="sxs-lookup"><span data-stu-id="106d0-122">**WAIT UP TO 24 HOURS TO TEST**.</span></span> <span data-ttu-id="106d0-123">При изменении параметров внешних коммуникаций, может потребоваться до 24 часов для изменения для заполнения в центрах обработки данных.</span><span class="sxs-lookup"><span data-stu-id="106d0-123">Any time you change the external communications settings, it can take up to 24 hours for the changes to populate across all the data centers.</span></span>
    
8. <span data-ttu-id="106d0-124">Показывать пользователям как поиск и добавление Скайп контактов в список Скайп для бизнес-контактами.</span><span class="sxs-lookup"><span data-stu-id="106d0-124">Show your users how to find and add Skype contacts to their list of Skype for Business contacts.</span></span> <span data-ttu-id="106d0-125">Укажите их [Поиск людей в Скайп для бизнеса](https://support.office.com/en-us/article/b12500ef-e37f-4d22-aade-c11277e53f19).</span><span class="sxs-lookup"><span data-stu-id="106d0-125">Point them to [Search for people in Skype for Business](https://support.office.com/en-us/article/b12500ef-e37f-4d22-aade-c11277e53f19).</span></span>
    
## <a name="test-and-troubleshoot"></a><span data-ttu-id="106d0-126">Тестирование и устранение неполадок</span><span class="sxs-lookup"><span data-stu-id="106d0-126">Test and troubleshoot</span></span>

<span data-ttu-id="106d0-127">Чтобы проверить настройки, необходимо контакта на Скайп, который не является за брандмауэром вашей компании.</span><span class="sxs-lookup"><span data-stu-id="106d0-127">To test your setup, you need a contact on Skype who's not behind your company firewall.</span></span> <span data-ttu-id="106d0-128">Они могут входить в систему с помощью учетной записи Gmail, Outlook.com учетной записи или другой тип учетной записи электронной почты Скайп.</span><span class="sxs-lookup"><span data-stu-id="106d0-128">They can be signed in to Skype using a Gmail account, Outlook.com account, or other type of email account.</span></span>
  
1. <span data-ttu-id="106d0-129">После можно изменить параметры внешних коммуникаций, **TEST кому ОЖИДАТЬ до 24 часов**.</span><span class="sxs-lookup"><span data-stu-id="106d0-129">After you change your external communications settings, **WAIT UP TO 24 HOURS TO TEST**.</span></span>
    
2. <span data-ttu-id="106d0-130">Выполните выход из Скайп для бизнеса, а затем снова выполните вход, параметр для поиска в каталоге Скайп.</span><span class="sxs-lookup"><span data-stu-id="106d0-130">Sign out of Skype for Business and then sign in again so you see the option to search the Skype Directory.</span></span> 
    
    ![Когда выделено Скайп каталогов, можно выполнить поиск для пользователей, имеющих учетные записи Скайп.](../images/76ee9fab-1ac3-4f4a-9569-f5f2606dbb7a.png)
  
3. <span data-ttu-id="106d0-132">В Скайп для бизнеса поиск контакта в Скайп и отправить запрос в чате.</span><span class="sxs-lookup"><span data-stu-id="106d0-132">In Skype for Business, search for your contact in Skype, and send a request to chat.</span></span> 
    
    <span data-ttu-id="106d0-133">Если вы получаете сообщение, которое он не доставлено из-за политики компании, необходимо повторно проверьте [параметры брандмауэра](https://support.office.com/en-us/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2).</span><span class="sxs-lookup"><span data-stu-id="106d0-133">If you get the message it couldn't be sent due to company policy, you need to double-check your [firewall settings](https://support.office.com/en-us/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2).</span></span> 
    
4. <span data-ttu-id="106d0-134">Другой способ проверки, является ли проблема в том, что брандмауэр — расположение wifi не за брандмауэром, таких как кафе и использовать Скайп для бизнеса отправляет запрос на Скайп обратитесь к разговору.</span><span class="sxs-lookup"><span data-stu-id="106d0-134">Another way to test whether the problem is your firewall is to go to a wifi location not behind your firewall such as a coffee shop, and use Skype for Business to send a request to your Skype contact to chat.</span></span> 
    
  - <span data-ttu-id="106d0-135">**Если контакт Скайп отправил запрос, и они никогда не получено**, попросить отправляет запрос на беседу.</span><span class="sxs-lookup"><span data-stu-id="106d0-135">**If you sent your Skype contact a request and they never received it**, ask them to send you a request to chat.</span></span> <span data-ttu-id="106d0-136">Если проблема при установке соединения между Скайп и Скайп для бизнеса, часто решает ее.</span><span class="sxs-lookup"><span data-stu-id="106d0-136">If the problem was establishing a connection between Skype and Skype for Business, that often solves it.</span></span>
    
  - <span data-ttu-id="106d0-137">Если сообщение проходит через в кафе, но не в том случае, когда вы находитесь на работе, это значит, проблема пришло брандмауэра.</span><span class="sxs-lookup"><span data-stu-id="106d0-137">Now if the message goes through at the coffee shop but not when you're at work, then you know the problem is your firewall.</span></span> 
    
## <a name="what-you-can-and-cant-do"></a><span data-ttu-id="106d0-138">Которые можно и нельзя выполнять</span><span class="sxs-lookup"><span data-stu-id="106d0-138">What you can and can't do</span></span>

- <span data-ttu-id="106d0-139">**Скайп для бизнеса в Mac** не имеют возможности для поиска и общаться с контактами Скайп.</span><span class="sxs-lookup"><span data-stu-id="106d0-139">**Skype for Business on Mac** doesn't have the ability to search for and communicate with Skype contacts.</span></span>
    
- <span data-ttu-id="106d0-140">Можно искать и найти Скайп пользователей, не может искать и поиск Скайп для коммерческих пользователей.</span><span class="sxs-lookup"><span data-stu-id="106d0-140">While you can search for and find Skype users, they cannot search for and find Skype for Business users.</span></span> <span data-ttu-id="106d0-141">Вы должны отправлять их контакта запроса, и у них для входа в Скайп и примите его, прежде чем обмен мгновенными Сообщениями с ними.</span><span class="sxs-lookup"><span data-stu-id="106d0-141">You have to send them a contact request, and they have to sign in to Skype and accept it, before you can IM with them.</span></span> 
    
- <span data-ttu-id="106d0-142">Не удается разрешить службы обмена Мгновенными сообщениями с другими поставщиками обмена мгновенными Сообщениями, например Google или Facebook.</span><span class="sxs-lookup"><span data-stu-id="106d0-142">It's not possible to allow IM connectivity with other IM providers such as Google or Facebook.</span></span> <span data-ttu-id="106d0-143">Нельзя использовать Скайп для бизнеса на отправку сообщений текст мобильный телефон.</span><span class="sxs-lookup"><span data-stu-id="106d0-143">You can't use Skype for Business to send cell phone text messages.</span></span>
    
## <a name="what-features-are-available-when-adding-skype-contacts"></a><span data-ttu-id="106d0-144">Какие возможности поддерживаются при добавлении контактов Скайп?</span><span class="sxs-lookup"><span data-stu-id="106d0-144">What features are available when adding Skype contacts?</span></span>

<span data-ttu-id="106d0-145">Скайп контакты, выполнил вход с помощью своей учетной записи Майкрософт (ранее — Windows Live ID) можно получить некоторые, но не все возможности, когда будет общаться с вашей Скайп для коммерческих пользователей.</span><span class="sxs-lookup"><span data-stu-id="106d0-145">Skype contacts who signed in with their Microsoft account (formerly Windows Live ID) can get some, but not all, features when they are talking to your Skype for Business users.</span></span>
  
|<span data-ttu-id="106d0-146">**Доступные с контактами Скайп**</span><span class="sxs-lookup"><span data-stu-id="106d0-146">**Available with Skype contacts**</span></span>|<span data-ttu-id="106d0-147">**Недоступно с контактами Скайп**</span><span class="sxs-lookup"><span data-stu-id="106d0-147">**Not available with Skype contacts**</span></span>|
|:-----|:-----|
| <span data-ttu-id="106d0-148">Видеобеседы</span><span class="sxs-lookup"><span data-stu-id="106d0-148">Video conversations</span></span> <br/>  <span data-ttu-id="106d0-149">Между двумя пользователями обмена мгновенными сообщениями</span><span class="sxs-lookup"><span data-stu-id="106d0-149">Person-to-person instant messaging</span></span> <br/>  <span data-ttu-id="106d0-150">Присутствие</span><span class="sxs-lookup"><span data-stu-id="106d0-150">Presence</span></span> <br/> | <span data-ttu-id="106d0-151">Многосторонние Текстовых бесед</span><span class="sxs-lookup"><span data-stu-id="106d0-151">Multi-party IM conversations</span></span> <br/>  <span data-ttu-id="106d0-152">Аудио- и видеоконференций бесед с тремя или более людьми</span><span class="sxs-lookup"><span data-stu-id="106d0-152">Audio and video conversations with three or more people</span></span> <br/>  <span data-ttu-id="106d0-153">Рабочий стол и общий доступ к программам</span><span class="sxs-lookup"><span data-stu-id="106d0-153">Desktop and program sharing</span></span> <br/> |
   
[!INCLUDE [LinkedIn Learning Info](../common/office/linkedin-learning-info.md)]
   
## <a name="related-topics"></a><span data-ttu-id="106d0-154">См. также:</span><span class="sxs-lookup"><span data-stu-id="106d0-154">Related topics</span></span>

[<span data-ttu-id="106d0-155">Разрешите пользователям связываться с внешними пользователями Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="106d0-155">Allow users to contact external Skype for Business users</span></span>](allow-users-to-contact-external-skype-for-business-users.md)
  
[<span data-ttu-id="106d0-156">Настройка Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="106d0-156">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)
