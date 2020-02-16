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
description: 'Узнайте, как разрешить людям, которые пользуются Skype для бизнеса, общаться с пользователями Skype для бизнеса за пределами Организации и добавлять их в список контактов. '
ms.openlocfilehash: ffefa664845f5dbe06b064e0a197a28d8df2c3da
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42010812"
---
# <a name="let-skype-for-business-users-add-skype-contacts"></a><span data-ttu-id="0c3cd-103">Разрешение на добавление контактов Skype пользователям Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="0c3cd-103">Let Skype for Business users add Skype contacts</span></span>

<span data-ttu-id="0c3cd-104">С помощью Skype для бизнеса ваши пользователи могут выполнять поиск и обмен мгновенными сообщениями со всеми пользователями Skype — бесплатным приложением!</span><span class="sxs-lookup"><span data-stu-id="0c3cd-104">With Skype for Business, your users can search for and IM with everyone who uses Skype, the free app!</span></span> <span data-ttu-id="0c3cd-105">В этой статье объясняется, что нужно сделать, чтобы они могли добавить контакты Skype.</span><span class="sxs-lookup"><span data-stu-id="0c3cd-105">This article explains what you need to do so they can add Skype contacts.</span></span> 
  
<span data-ttu-id="0c3cd-106">Для этого необходимы [разрешения администратора](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d?ui=en-US&rs=en-US&ad=US) в Office 365.</span><span class="sxs-lookup"><span data-stu-id="0c3cd-106">You must have [admin permissions](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d?ui=en-US&rs=en-US&ad=US) in Office 365 to do this.</span></span>

<span data-ttu-id="0c3cd-107">![Значок с логотипом Skype для бизнеса](../images/sfb-logo-30x30.png) **Использование центра администрирования Skype для бизнеса**</span><span class="sxs-lookup"><span data-stu-id="0c3cd-107">![An icon showing the Skype for Business logo](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>
  
1. <span data-ttu-id="0c3cd-108">Войдите в систему с помощью учетной записи администратора [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home#/homepage)Office 365 по адресу.</span><span class="sxs-lookup"><span data-stu-id="0c3cd-108">Sign in with your Office 365 admin account at [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home#/homepage).</span></span>
    
2. <span data-ttu-id="0c3cd-109">В центре администрирования перейдите в раздел >  **"центры администрирования"\*\*\*\*Skype для бизнеса**.</span><span class="sxs-lookup"><span data-stu-id="0c3cd-109">In the admin center, go to **Admin Centers** > **Skype for Business**.</span></span> 
    
    ![Выберите центр администрирования Skype для бизнеса.](../images/376a7a45-e6e3-4716-be09-d2f294d885a2.png)
  
3. <span data-ttu-id="0c3cd-111">В **Центре администрирования Skype для бизнеса** выберите пункт **Организация** > **Внешний обмен данными**.</span><span class="sxs-lookup"><span data-stu-id="0c3cd-111">In the **Skype for Business admin center**, choose **Organization** > **External communications**.</span></span> 
    
4. <span data-ttu-id="0c3cd-112">По умолчанию пользователи могут общаться с другими людьми в мире, использующих Skype для бизнеса (если брандмауэр настроен таким образом, что это разрешено).</span><span class="sxs-lookup"><span data-stu-id="0c3cd-112">By default, your users can communicate with all other people in the world who use Skype for Business (assuming your firewall has been configured to allow this).</span></span> 
    
    ![Выберите параметр Разрешить пользователям использовать Skype для бизнеса для общения через Skype.](../images/333789f8-2ea6-4bbd-805b-18130f427999.png)
  
    <span data-ttu-id="0c3cd-114">Если вы хотите, чтобы ваши пользователи могли общаться с пользователями Skype, но вы не хотите, чтобы они были общаться с другими людьми, использующими Skype для бизнеса, выберите параметр **включить только для разрешенных доменов**.</span><span class="sxs-lookup"><span data-stu-id="0c3cd-114">If you want your users to chat with Skype users, BUT you don't want them to chat with others who use Skype for Business, choose **On only for allowed domains**.</span></span> <span data-ttu-id="0c3cd-115">Когда вы включаете контакт с пользователями Skype, skype.com автоматически добавляется в качестве разрешенного домена в фоновом режиме.</span><span class="sxs-lookup"><span data-stu-id="0c3cd-115">When you enable contact with Skype users, skype.com is automatically added as an allowed domain behind the scenes.</span></span> 
    
    <span data-ttu-id="0c3cd-116">Если вы хотите разрешить контакт из других организаций в мире с помощью Skype для бизнеса, кроме определенных, выберите параметр Вкл., **кроме заблокированных доменов**, а **+** затем добавьте эти домены.</span><span class="sxs-lookup"><span data-stu-id="0c3cd-116">If you want to allow contact from all other businesses in the world using Skype for Business, except specific ones, choose **On except for blocked domains**, and choose **+** to add those domains.</span></span> <span data-ttu-id="0c3cd-117">Все пользователи смогут общаться с вами за исключением тех, кто указан в указанных доменах.</span><span class="sxs-lookup"><span data-stu-id="0c3cd-117">Everyone will be able to contact you except people on those specific domains.</span></span> <span data-ttu-id="0c3cd-118">(В некоторых организациях этот вариант может быть выбран, например, если он находится в судебном разбирательстве, и вам нужно убедиться, что вы не хотите общаться с другими компаниями.)</span><span class="sxs-lookup"><span data-stu-id="0c3cd-118">(Some businesses might choose this option, for example, if they are in litigation and need to ensure there's no contact with the other business.)</span></span>
    
5. <span data-ttu-id="0c3cd-119">Выберите **Разрешить пользователям использовать Skype для бизнеса для связи с пользователями Skype за пределами вашей организации**.</span><span class="sxs-lookup"><span data-stu-id="0c3cd-119">Choose **Let people use Skype for Business to communicate with Skype users outside your organization**.</span></span> 
    
6.  <span data-ttu-id="0c3cd-120">Если вы используете брандмауэр Windows, в Skype для бизнеса автоматически открываются нужные порты.</span><span class="sxs-lookup"><span data-stu-id="0c3cd-120">If you're using Windows Firewall, Skype for Business opens the required ports automatically.</span></span>
    
    <span data-ttu-id="0c3cd-121">Если ваша организация использует другое решение для ограничения доступа компьютеров сети к Интернету, убедитесь, что клиентские компьютеры имеют доступ ко всем [IP-адресам и URL-адресам](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2) для подключения к Skype и поиска в справочнике Skype.</span><span class="sxs-lookup"><span data-stu-id="0c3cd-121">If your organization uses another solution to restrict computers on your network from connecting to the Internet, ensure client computers are able to access all of the [IP addresses and URLs](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2) for Skype connectivity and Skype Directory Search.</span></span> <span data-ttu-id="0c3cd-122">Возможно, потребуется добавить их в список разрешенных исходящих подключений в конфигурации брандмауэра или прокси-инфраструктуры.</span><span class="sxs-lookup"><span data-stu-id="0c3cd-122">This may require adding them to the outbound allow list in your firewall or proxy infrastructure configuration.</span></span>
    
7. <span data-ttu-id="0c3cd-123">**Подождите до 24 часов, чтобы ПРОтестировать**.</span><span class="sxs-lookup"><span data-stu-id="0c3cd-123">**WAIT UP TO 24 HOURS TO TEST**.</span></span> <span data-ttu-id="0c3cd-124">Каждый раз при изменении параметров внешней связи может потребоваться до 24 часов, чтобы изменения настроились между всеми центрами обработки данных.</span><span class="sxs-lookup"><span data-stu-id="0c3cd-124">Any time you change the external communications settings, it can take up to 24 hours for the changes to populate across all the data centers.</span></span>
    
8. <span data-ttu-id="0c3cd-125">Покажите своим пользователям, как найти и добавить контакты Skype в список контактов Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="0c3cd-125">Show your users how to find and add Skype contacts to their list of Skype for Business contacts.</span></span> <span data-ttu-id="0c3cd-126">Наведите указатель мыши на [раздел для поиска людей в Skype для бизнеса](https://support.office.com/article/b12500ef-e37f-4d22-aade-c11277e53f19).</span><span class="sxs-lookup"><span data-stu-id="0c3cd-126">Point them to [Search for people in Skype for Business](https://support.office.com/article/b12500ef-e37f-4d22-aade-c11277e53f19).</span></span>
    
## <a name="test-and-troubleshoot"></a><span data-ttu-id="0c3cd-127">Проверка и устранение неполадок</span><span class="sxs-lookup"><span data-stu-id="0c3cd-127">Test and troubleshoot</span></span>

<span data-ttu-id="0c3cd-128">Для проверки настройки вам потребуется контакт в Skype, который не защищен брандмауэром компании.</span><span class="sxs-lookup"><span data-stu-id="0c3cd-128">To test your setup, you need a contact on Skype who's not behind your company firewall.</span></span> <span data-ttu-id="0c3cd-129">Они могут войти в Skype с помощью учетной записи Gmail, учетной записи Outlook.com или другого типа учетной записи электронной почты.</span><span class="sxs-lookup"><span data-stu-id="0c3cd-129">They can be signed in to Skype using a Gmail account, Outlook.com account, or other type of email account.</span></span>
  
1. <span data-ttu-id="0c3cd-130">После изменения параметров внешней связи **Подождите до 24 часов перед тем, как ПРОтестировать**.</span><span class="sxs-lookup"><span data-stu-id="0c3cd-130">After you change your external communications settings, **WAIT UP TO 24 HOURS TO TEST**.</span></span>
    
2. <span data-ttu-id="0c3cd-131">Выйдите из Skype для бизнеса, а затем снова войдите, чтобы увидеть, как искать в справочнике Skype.</span><span class="sxs-lookup"><span data-stu-id="0c3cd-131">Sign out of Skype for Business and then sign in again so you see the option to search the Skype Directory.</span></span> 
    
    ![Если выделена кнопка "Каталог Skype", вы можете найти пользователей, у которых есть учетные записи в Skype.](../images/76ee9fab-1ac3-4f4a-9569-f5f2606dbb7a.png)
  
3. <span data-ttu-id="0c3cd-133">В Skype для бизнеса выполните поиск контакта в Skype и отправьте запрос на чат.</span><span class="sxs-lookup"><span data-stu-id="0c3cd-133">In Skype for Business, search for your contact in Skype, and send a request to chat.</span></span> 
    
    <span data-ttu-id="0c3cd-134">Если вы получили сообщение о том, что оно не было отправлено из-за политики компании, необходимо дважды проверить [Параметры брандмауэра](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2).</span><span class="sxs-lookup"><span data-stu-id="0c3cd-134">If you get the message it couldn't be sent due to company policy, you need to double-check your [firewall settings](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2).</span></span> 
    
4. <span data-ttu-id="0c3cd-135">Кроме того, вы можете проверить, является ли проблема брандмауэром, чтобы перейти к расположению в сети Wi-Fi, не защищенному брандмауэром, например кафе, и использовать Skype для бизнеса для отправки запроса на ваш абонент Skype в чат.</span><span class="sxs-lookup"><span data-stu-id="0c3cd-135">Another way to test whether the problem is your firewall is to go to a wifi location not behind your firewall such as a coffee shop, and use Skype for Business to send a request to your Skype contact to chat.</span></span> 
    
   - <span data-ttu-id="0c3cd-136">**Если вы отправили ответ на запрос Skype и не получили его**, попросите его отправить вам запрос на чат.</span><span class="sxs-lookup"><span data-stu-id="0c3cd-136">**If you sent your Skype contact a request and they never received it**, ask them to send you a request to chat.</span></span> <span data-ttu-id="0c3cd-137">Если у вас возникла проблема с подключением между Skype и Skype для бизнеса, это часто решает проблему.</span><span class="sxs-lookup"><span data-stu-id="0c3cd-137">If the problem was establishing a connection between Skype and Skype for Business, that often solves it.</span></span>
    
   - <span data-ttu-id="0c3cd-138">Если сообщение перейдет в Интернет-магазин, но не работает, вы знаете, что проблема связана с брандмауэром.</span><span class="sxs-lookup"><span data-stu-id="0c3cd-138">Now if the message goes through at the coffee shop but not when you're at work, then you know the problem is your firewall.</span></span> 
    
## <a name="what-you-can-and-cant-do"></a><span data-ttu-id="0c3cd-139">Что можно и что делать?</span><span class="sxs-lookup"><span data-stu-id="0c3cd-139">What you can and can't do</span></span>

- <span data-ttu-id="0c3cd-140">**Skype для бизнеса на Mac** не может находить контакты Skype и общаться с ними.</span><span class="sxs-lookup"><span data-stu-id="0c3cd-140">**Skype for Business on Mac** doesn't have the ability to search for and communicate with Skype contacts.</span></span>
    
- <span data-ttu-id="0c3cd-141">При включенном поиске в каталоге вы можете найти пользователей Skype и Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="0c3cd-141">When directory search is enabled, you can search for and find Skype and Skype for Business users.</span></span> <span data-ttu-id="0c3cd-142">Если по какой-либо причине вы не можете найти их с помощью поиска в каталоге, вы можете отправить ему запрос контактных данных, а затем войти в Skype и согласиться, чтобы вы могли обмениваться сообщениями.</span><span class="sxs-lookup"><span data-stu-id="0c3cd-142">If for some reason you can't find them by searching the directory, you can send them a contact request, and then have them sign in to Skype and accept it, so you can IM with them.</span></span> 
    
- <span data-ttu-id="0c3cd-143">Не разрешается использовать возможности обмена мгновенными сообщениями с другими поставщиками обмена мгновенными сообщениями, такими как Google и Facebook.</span><span class="sxs-lookup"><span data-stu-id="0c3cd-143">It's not possible to allow IM connectivity with other IM providers such as Google or Facebook.</span></span> <span data-ttu-id="0c3cd-144">Вы не можете использовать Skype для бизнеса, чтобы отправлять текстовые сообщения в Сотовые телефоны.</span><span class="sxs-lookup"><span data-stu-id="0c3cd-144">You can't use Skype for Business to send cell phone text messages.</span></span>

- <span data-ttu-id="0c3cd-145">Невозможно записывать голосовые и видеозвонки между контактами Skype и контактами Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="0c3cd-145">It is not possible to record audio or video calls between a Skype Contact and Skype for Business contact.</span></span>
    
## <a name="what-features-are-available-when-adding-skype-contacts"></a><span data-ttu-id="0c3cd-146">Какие функции доступны при добавлении контактов Skype?</span><span class="sxs-lookup"><span data-stu-id="0c3cd-146">What features are available when adding Skype contacts?</span></span>

<span data-ttu-id="0c3cd-147">Контакты Skype, выполнившие вход под учетной записью Майкрософт (ранее Windows Live ID), могут получить некоторые (но не все) возможности при общении с пользователями Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="0c3cd-147">Skype contacts who signed in with their Microsoft account (formerly Windows Live ID) can get some, but not all, features when they are talking to your Skype for Business users.</span></span>
  
|<span data-ttu-id="0c3cd-148">**Доступно в контактах Skype**</span><span class="sxs-lookup"><span data-stu-id="0c3cd-148">**Available with Skype contacts**</span></span>|<span data-ttu-id="0c3cd-149">**Недоступно с контактами Skype**</span><span class="sxs-lookup"><span data-stu-id="0c3cd-149">**Not available with Skype contacts**</span></span>|
|:-----|:-----|
| <span data-ttu-id="0c3cd-150">Видеобеседы</span><span class="sxs-lookup"><span data-stu-id="0c3cd-150">Video conversations</span></span> <br/>  <span data-ttu-id="0c3cd-151">Обмен мгновенными сообщениями между пользователями</span><span class="sxs-lookup"><span data-stu-id="0c3cd-151">Person-to-person instant messaging</span></span> <br/>  <span data-ttu-id="0c3cd-152">Присутствие</span><span class="sxs-lookup"><span data-stu-id="0c3cd-152">Presence</span></span> <br/> | <span data-ttu-id="0c3cd-153">Текстовые беседы с несколькими участниками</span><span class="sxs-lookup"><span data-stu-id="0c3cd-153">Multi-party IM conversations</span></span> <br/>  <span data-ttu-id="0c3cd-154">Аудио и видеобеседы с тремя и более собеседниками</span><span class="sxs-lookup"><span data-stu-id="0c3cd-154">Audio and video conversations with three or more people</span></span> <br/>  <span data-ttu-id="0c3cd-155">Рабочий стол и совместный доступ к программам</span><span class="sxs-lookup"><span data-stu-id="0c3cd-155">Desktop and program sharing</span></span> <br/> |
   
[!INCLUDE [LinkedIn Learning Info](../../common/office/linkedin-learning-info.md)]
   
## <a name="related-topics"></a><span data-ttu-id="0c3cd-156">См. также:</span><span class="sxs-lookup"><span data-stu-id="0c3cd-156">Related topics</span></span>

[<span data-ttu-id="0c3cd-157">Разрешение пользователям на связь с внешними пользователями Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="0c3cd-157">Allow users to contact external Skype for Business users</span></span>](allow-users-to-contact-external-skype-for-business-users.md)
  
[<span data-ttu-id="0c3cd-158">Настройка Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="0c3cd-158">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)

  
 
