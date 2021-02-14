---
title: Разрешение на добавление контактов Skype пользователям Skype для бизнеса
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: 08666236-1894-42ae-8846-e49232bbc460
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Setup
- LIL_Placement
description: 'Узнайте, как позволить пользователям Skype для бизнеса связываться с пользователями Skype для бизнеса, которые не являются пользователями вашей организации, и добавлять их в свой список контактов. '
ms.openlocfilehash: 71282fe105c85cadca9aab341fc1b5e6ffbe47d2
ms.sourcegitcommit: 36f7ec432090683aedb77a5bd7856e1b10af2a81
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2020
ms.locfileid: "44164478"
---
# <a name="let-skype-for-business-users-add-skype-contacts"></a><span data-ttu-id="1e6fb-103">Разрешение на добавление контактов Skype пользователям Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="1e6fb-103">Let Skype for Business users add Skype contacts</span></span>

<span data-ttu-id="1e6fb-104">С помощью Skype для бизнеса ваши пользователи могут искать и мгновенные звонки всем пользователям бесплатного приложения Skype!</span><span class="sxs-lookup"><span data-stu-id="1e6fb-104">With Skype for Business, your users can search for and IM with everyone who uses Skype, the free app!</span></span> <span data-ttu-id="1e6fb-105">В этой статье объясняется, что необходимо сделать, чтобы они могли добавлять контакты Skype.</span><span class="sxs-lookup"><span data-stu-id="1e6fb-105">This article explains what you need to do so they can add Skype contacts.</span></span> 
  
<span data-ttu-id="1e6fb-106">Для этого у вас [должны быть](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d?ui=en-US&rs=en-US&ad=US) разрешения администратора в Microsoft 365 или Office 365.</span><span class="sxs-lookup"><span data-stu-id="1e6fb-106">You must have [admin permissions](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d?ui=en-US&rs=en-US&ad=US) in Microsoft 365 or Office 365 to do this.</span></span>

<span data-ttu-id="1e6fb-107">![Значок с логотипом Skype для бизнеса](../images/sfb-logo-30x30.png) **Использование центра администрирования Skype для бизнеса**</span><span class="sxs-lookup"><span data-stu-id="1e6fb-107">![An icon showing the Skype for Business logo](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>
  
1. <span data-ttu-id="1e6fb-108">Во sign in with your Microsoft 365 or Office 365 admin account [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home#/homepage) at.</span><span class="sxs-lookup"><span data-stu-id="1e6fb-108">Sign in with your Microsoft 365 or Office 365 admin account at [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home#/homepage).</span></span>
    
2. <span data-ttu-id="1e6fb-109">В Центре администрирования перейдите **в** центры администрирования  >  **Skype для бизнеса.**</span><span class="sxs-lookup"><span data-stu-id="1e6fb-109">In the admin center, go to **Admin Centers** > **Skype for Business**.</span></span> 
    
    ![Выберите Центр администрирования Skype для бизнеса.](../images/376a7a45-e6e3-4716-be09-d2f294d885a2.png)
  
3. <span data-ttu-id="1e6fb-111">В **Центре администрирования Skype для бизнеса** выберите пункт **Организация** > **Внешний обмен данными**.</span><span class="sxs-lookup"><span data-stu-id="1e6fb-111">In the **Skype for Business admin center**, choose **Organization** > **External communications**.</span></span> 
    
4. <span data-ttu-id="1e6fb-112">По умолчанию ваши пользователи могут общаться с другими пользователями Skype для бизнеса (предполагается, что ваш брандмауэр разрешил это).</span><span class="sxs-lookup"><span data-stu-id="1e6fb-112">By default, your users can communicate with all other people in the world who use Skype for Business (assuming your firewall has been configured to allow this).</span></span> 
    
    ![Выберите "Позволить людям использовать Skype для бизнеса для связи со Skype".](../images/333789f8-2ea6-4bbd-805b-18130f427999.png)
  
    <span data-ttu-id="1e6fb-114">Если вы хотите, чтобы пользователи общались с пользователями Skype, но не с пользователями Skype для бизнеса, выберите "В сети" только для **разрешенных доменов.**</span><span class="sxs-lookup"><span data-stu-id="1e6fb-114">If you want your users to chat with Skype users, BUT you don't want them to chat with others who use Skype for Business, choose **On only for allowed domains**.</span></span> <span data-ttu-id="1e6fb-115">Когда вы включаете контакты с пользователями Skype, skype.com автоматически добавляется в качестве разрешенного домена.</span><span class="sxs-lookup"><span data-stu-id="1e6fb-115">When you enable contact with Skype users, skype.com is automatically added as an allowed domain behind the scenes.</span></span> 
    
    <span data-ttu-id="1e6fb-116">Если вы хотите разрешить использование Skype для бизнеса для контактов из других компаний мира, кроме конкретных, выберите "В сети" (за исключением заблокированных доменов) и добавьте **+** эти домены.</span><span class="sxs-lookup"><span data-stu-id="1e6fb-116">If you want to allow contact from all other businesses in the world using Skype for Business, except specific ones, choose **On except for blocked domains**, and choose **+** to add those domains.</span></span> <span data-ttu-id="1e6fb-117">С вами смогут связаться все, кроме людей из этих доменов.</span><span class="sxs-lookup"><span data-stu-id="1e6fb-117">Everyone will be able to contact you except people on those specific domains.</span></span> <span data-ttu-id="1e6fb-118">(Некоторые организации могут выбрать этот вариант, например в случае судебного разбирательства и убедиться, что нет контактов с другими организациями.)</span><span class="sxs-lookup"><span data-stu-id="1e6fb-118">(Some businesses might choose this option, for example, if they are in litigation and need to ensure there's no contact with the other business.)</span></span>
    
5. <span data-ttu-id="1e6fb-119">Выберите "Разрешите пользователям использовать Skype для бизнеса" для общения **с пользователями Skype за пределами вашей организации.**</span><span class="sxs-lookup"><span data-stu-id="1e6fb-119">Choose **Let people use Skype for Business to communicate with Skype users outside your organization**.</span></span> 
    
6.  <span data-ttu-id="1e6fb-120">Если вы используете брандмауэр Windows, Skype для бизнеса автоматически открывает требуемые порты.</span><span class="sxs-lookup"><span data-stu-id="1e6fb-120">If you're using Windows Firewall, Skype for Business opens the required ports automatically.</span></span>
    
    <span data-ttu-id="1e6fb-121">Если в вашей организации используется другое решение для ограничения подключения компьютеров в сети к Интернету, [](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2) убедитесь, что клиентские компьютеры имеют доступ ко всем IP-адресам и URL-адресам для подключения к Skype и поиска в каталоге Skype.</span><span class="sxs-lookup"><span data-stu-id="1e6fb-121">If your organization uses another solution to restrict computers on your network from connecting to the Internet, ensure client computers are able to access all of the [IP addresses and URLs](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2) for Skype connectivity and Skype Directory Search.</span></span> <span data-ttu-id="1e6fb-122">Для этого может потребоваться добавить их в список исходящие разрешение в брандмауэре или конфигурации инфраструктуры прокси-сервера.</span><span class="sxs-lookup"><span data-stu-id="1e6fb-122">This may require adding them to the outbound allow list in your firewall or proxy infrastructure configuration.</span></span>
    
7. <span data-ttu-id="1e6fb-123">**ПОДОЖДИТЕ ДО 24 ЧАСОВ.**</span><span class="sxs-lookup"><span data-stu-id="1e6fb-123">**WAIT UP TO 24 HOURS TO TEST**.</span></span> <span data-ttu-id="1e6fb-124">После изменения параметров внешней связи может занять до 24 часов, чтобы изменения во всех центрах обработки данных заполнялись.</span><span class="sxs-lookup"><span data-stu-id="1e6fb-124">Any time you change the external communications settings, it can take up to 24 hours for the changes to populate across all the data centers.</span></span>
    
8. <span data-ttu-id="1e6fb-125">Покажите пользователям, как находить и добавлять контакты Skype в свой список контактов Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="1e6fb-125">Show your users how to find and add Skype contacts to their list of Skype for Business contacts.</span></span> <span data-ttu-id="1e6fb-126">На этом этапе [можно найти людей в Skype для бизнеса.](https://support.office.com/article/b12500ef-e37f-4d22-aade-c11277e53f19)</span><span class="sxs-lookup"><span data-stu-id="1e6fb-126">Point them to [Search for people in Skype for Business](https://support.office.com/article/b12500ef-e37f-4d22-aade-c11277e53f19).</span></span>
    
## <a name="test-and-troubleshoot"></a><span data-ttu-id="1e6fb-127">Проверка и устранение неполадок</span><span class="sxs-lookup"><span data-stu-id="1e6fb-127">Test and troubleshoot</span></span>

<span data-ttu-id="1e6fb-128">Чтобы проверить настройку, вам понадобится контакт в Skype, который не работает в брандмауэре вашей компании.</span><span class="sxs-lookup"><span data-stu-id="1e6fb-128">To test your setup, you need a contact on Skype who's not behind your company firewall.</span></span> <span data-ttu-id="1e6fb-129">Можно ввести учетную запись Gmail, учетную запись Outlook.com или учетную запись электронной почты другого типа.</span><span class="sxs-lookup"><span data-stu-id="1e6fb-129">They can be signed in to Skype using a Gmail account, Outlook.com account, or other type of email account.</span></span>
  
1. <span data-ttu-id="1e6fb-130">После изменения параметров внешней связи подождите **до 24 ЧАСОВ для проверки.**</span><span class="sxs-lookup"><span data-stu-id="1e6fb-130">After you change your external communications settings, **WAIT UP TO 24 HOURS TO TEST**.</span></span>
    
2. <span data-ttu-id="1e6fb-131">Вы можете выйти из Skype для бизнеса, а затем снова войти, чтобы увидеть параметр поиска в каталоге Skype.</span><span class="sxs-lookup"><span data-stu-id="1e6fb-131">Sign out of Skype for Business and then sign in again so you see the option to search the Skype Directory.</span></span> 
    
    ![Когда выделен каталог Skype, вы можете искать людей, у которых есть учетные записи Скайпа.](../images/76ee9fab-1ac3-4f4a-9569-f5f2606dbb7a.png)
  
3. <span data-ttu-id="1e6fb-133">В Skype для бизнеса наищите контакт в Скайпе и отправьте запрос на чат.</span><span class="sxs-lookup"><span data-stu-id="1e6fb-133">In Skype for Business, search for your contact in Skype, and send a request to chat.</span></span> 
    
    <span data-ttu-id="1e6fb-134">Если вы получаете сообщение, что сообщение не удалось отправить из-за политики компании, необходимо проверить параметры [брандмауэра.](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2)</span><span class="sxs-lookup"><span data-stu-id="1e6fb-134">If you get the message it couldn't be sent due to company policy, you need to double-check your [firewall settings](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2).</span></span> 
    
4. <span data-ttu-id="1e6fb-135">Еще один способ проверить, есть ли проблема в брандмауэре, — перейти в сеть Wi-Fi, не расположенную за брандмауэром, например в кафе, и отправить контакту Skype запрос на чат с помощью Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="1e6fb-135">Another way to test whether the problem is your firewall is to go to a wifi location not behind your firewall such as a coffee shop, and use Skype for Business to send a request to your Skype contact to chat.</span></span> 
    
   - <span data-ttu-id="1e6fb-136">**Если вы отправили запрос контакту Skype,** но он его не получил, попросите контакт отправить вам запрос на чат.</span><span class="sxs-lookup"><span data-stu-id="1e6fb-136">**If you sent your Skype contact a request and they never received it**, ask them to send you a request to chat.</span></span> <span data-ttu-id="1e6fb-137">Если проблема была в создании соединения между Skype и Skype для бизнеса, она часто решается.</span><span class="sxs-lookup"><span data-stu-id="1e6fb-137">If the problem was establishing a connection between Skype and Skype for Business, that often solves it.</span></span>
    
   - <span data-ttu-id="1e6fb-138">Теперь, если сообщение отправляется в кафе, но не на работе, значит проблема в брандмауэре.</span><span class="sxs-lookup"><span data-stu-id="1e6fb-138">Now if the message goes through at the coffee shop but not when you're at work, then you know the problem is your firewall.</span></span> 
    
## <a name="what-you-can-and-cant-do"></a><span data-ttu-id="1e6fb-139">Что можно и что нельзя делать</span><span class="sxs-lookup"><span data-stu-id="1e6fb-139">What you can and can't do</span></span>

- <span data-ttu-id="1e6fb-140">**Skype для бизнеса на Mac** не имеет возможности искать контакты Skype и общаться с ними.</span><span class="sxs-lookup"><span data-stu-id="1e6fb-140">**Skype for Business on Mac** doesn't have the ability to search for and communicate with Skype contacts.</span></span>
    
- <span data-ttu-id="1e6fb-141">Если поиск в каталоге включен, вы можете искать и находить пользователей Skype и Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="1e6fb-141">When directory search is enabled, you can search for and find Skype and Skype for Business users.</span></span> <span data-ttu-id="1e6fb-142">Если по какой-либо причине вам не получается найти их в каталоге, вы можете отправить ему запрос на контакт, а затем попросить его войти в Skype и принять его, чтобы вы могли отправлять им мгновенные сообщение.</span><span class="sxs-lookup"><span data-stu-id="1e6fb-142">If for some reason you can't find them by searching the directory, you can send them a contact request, and then have them sign in to Skype and accept it, so you can IM with them.</span></span> 
    
- <span data-ttu-id="1e6fb-143">Невозможно разрешить подключение с другими поставщиками услуг мгновенных услуг, такими как Google или Facebook.</span><span class="sxs-lookup"><span data-stu-id="1e6fb-143">It's not possible to allow IM connectivity with other IM providers such as Google or Facebook.</span></span> <span data-ttu-id="1e6fb-144">Вы не можете использовать Skype для бизнеса для отправки текстовых сообщений на мобильный телефон.</span><span class="sxs-lookup"><span data-stu-id="1e6fb-144">You can't use Skype for Business to send cell phone text messages.</span></span>

- <span data-ttu-id="1e6fb-145">Запись звука и видеозвонков между контактом Skype и контактом Skype для бизнеса невозможен.</span><span class="sxs-lookup"><span data-stu-id="1e6fb-145">It is not possible to record audio or video calls between a Skype Contact and Skype for Business contact.</span></span>
    
## <a name="what-features-are-available-when-adding-skype-contacts"></a><span data-ttu-id="1e6fb-146">Какие функции доступны при добавлении контактов Skype?</span><span class="sxs-lookup"><span data-stu-id="1e6fb-146">What features are available when adding Skype contacts?</span></span>

<span data-ttu-id="1e6fb-147">Контакты Skype, которые въехались со своей учетной записью Майкрософт (прежнее Windows Live ID), могут получить некоторые функции (но не все) при разговоре с пользователями Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="1e6fb-147">Skype contacts who signed in with their Microsoft account (formerly Windows Live ID) can get some, but not all, features when they are talking to your Skype for Business users.</span></span>
  
|<span data-ttu-id="1e6fb-148">**Доступно для контактов Skype**</span><span class="sxs-lookup"><span data-stu-id="1e6fb-148">**Available with Skype contacts**</span></span>|<span data-ttu-id="1e6fb-149">**Недоступны для контактов Skype**</span><span class="sxs-lookup"><span data-stu-id="1e6fb-149">**Not available with Skype contacts**</span></span>|
|:-----|:-----|
| <span data-ttu-id="1e6fb-150">Видеосвязь</span><span class="sxs-lookup"><span data-stu-id="1e6fb-150">Video conversations</span></span> <br/>  <span data-ttu-id="1e6fb-151">Личных мгновенных сообщений</span><span class="sxs-lookup"><span data-stu-id="1e6fb-151">Person-to-person instant messaging</span></span> <br/>  <span data-ttu-id="1e6fb-152">Присутствие</span><span class="sxs-lookup"><span data-stu-id="1e6fb-152">Presence</span></span> <br/> | <span data-ttu-id="1e6fb-153">Мгновенные беседы с несколькими собеседниками</span><span class="sxs-lookup"><span data-stu-id="1e6fb-153">Multi-party IM conversations</span></span> <br/>  <span data-ttu-id="1e6fb-154">Аудио- и видеозвук с тремя и более собеседниками</span><span class="sxs-lookup"><span data-stu-id="1e6fb-154">Audio and video conversations with three or more people</span></span> <br/>  <span data-ttu-id="1e6fb-155">Общий доступ к рабочему столу и программам</span><span class="sxs-lookup"><span data-stu-id="1e6fb-155">Desktop and program sharing</span></span> <br/> |
   
[!INCLUDE [LinkedIn Learning Info](../../common/office/linkedin-learning-info.md)]
   
## <a name="related-topics"></a><span data-ttu-id="1e6fb-156">См. также:</span><span class="sxs-lookup"><span data-stu-id="1e6fb-156">Related topics</span></span>

[<span data-ttu-id="1e6fb-157">Разрешение пользователям на связь с внешними пользователями Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="1e6fb-157">Allow users to contact external Skype for Business users</span></span>](allow-users-to-contact-external-skype-for-business-users.md)
  
[<span data-ttu-id="1e6fb-158">Настройка Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="1e6fb-158">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)

  
 
