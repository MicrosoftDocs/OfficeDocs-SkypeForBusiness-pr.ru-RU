---
title: "Разрешение на добавление контактов Skype пользователям Skype для бизнеса"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 01/23/2018
ms.topic: article
ms.assetid: 08666236-1894-42ae-8846-e49232bbc460
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Setup
- LIL_Placement
description: "Информация о том, как настроить для пользователей Skype для бизнеса возможность общаться с пользователями Skype для бизнеса из других компаний и добавлять их в свой список контактов. "
ms.openlocfilehash: 8f6ca948434d9b5a63788cbb5bc54ad6297843e2
ms.sourcegitcommit: 46ca433590a4c3aefbe2fb777542bb0b332563bf
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/09/2018
---
# <a name="let-skype-for-business-users-add-skype-contacts"></a><span data-ttu-id="0f3d9-103">Разрешение на добавление контактов Skype пользователям Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="0f3d9-103">Let Skype for Business users add Skype contacts</span></span>

<span data-ttu-id="0f3d9-104">Skype для бизнеса позволяет вашим пользователям искать контакты и обмениваться мгновенными сообщениями с пользователями бесплатного приложения Skype!</span><span class="sxs-lookup"><span data-stu-id="0f3d9-104">With Skype for Business, your users can search for and IM with everyone who uses Skype, the free app!</span></span> <span data-ttu-id="0f3d9-105">Эта статья расскажет, что нужно сделать пользователям, чтобы добавлять контакты Skype.</span><span class="sxs-lookup"><span data-stu-id="0f3d9-105">This article explains what you need to do so they can add Skype contacts.</span></span> 
  
<span data-ttu-id="0f3d9-106">Для этого требуются [права администратора](https://support.office.com/en-us/article/da585eea-f576-4f55-a1e0-87090b6aaa9d?ui=en-US&rs=en-US&ad=US) в Office 365.</span><span class="sxs-lookup"><span data-stu-id="0f3d9-106">You must have [admin permissions](https://support.office.com/en-us/article/da585eea-f576-4f55-a1e0-87090b6aaa9d?ui=en-US&rs=en-US&ad=US) in Office 365 to do this.</span></span>
  
1. <span data-ttu-id="0f3d9-107">Войдите с учетной записью администратора Office 365 на сайт [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home#/homepage).</span><span class="sxs-lookup"><span data-stu-id="0f3d9-107">Sign in with your Office 365 global admin account at [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home#/homepage).</span></span>
    
2. <span data-ttu-id="0f3d9-108">В Центре администрирования Office 365 перейдите в раздел **Центры администрирования**  >  **Skype для бизнеса**.</span><span class="sxs-lookup"><span data-stu-id="0f3d9-108">In the Office 365 admin center, go to **Admin Centers** > **Skype for Business**.</span></span> 
    
    ![Выберите Центр администрирования Skype для бизнеса.](../images/376a7a45-e6e3-4716-be09-d2f294d885a2.png)
  
3. <span data-ttu-id="0f3d9-110">В **Центре администрирования Skype для бизнеса** выберите пункты **Организация**  >  **Внешние связи**.</span><span class="sxs-lookup"><span data-stu-id="0f3d9-110">In the **Skype for Business admin center**, choose **Organization** > **External communications**.</span></span> 
    
4. <span data-ttu-id="0f3d9-111">По умолчанию ваши пользователи могут общаться с другими пользователями Skype для бизнеса (если в брандмауэре настроены эти разрешения).</span><span class="sxs-lookup"><span data-stu-id="0f3d9-111">By default, your users can communicate with all other people in the world who use Skype for Business (assuming your firewall has been configured to allow this).</span></span> 
    
    ![Выберите пункт "Разрешить сотрудникам использовать Skype для бизнеса для связи с пользователями Skype".](../images/333789f8-2ea6-4bbd-805b-18130f427999.png)
  
    <span data-ttu-id="0f3d9-113">Если вы хотите, чтобы ваши пользователи общались с пользователями Skype, НО не с другими пользователями Skype для бизнеса, выберите пункт **Включить только для разрешенных доменов**.</span><span class="sxs-lookup"><span data-stu-id="0f3d9-113">If you want your users to chat with Skype users, BUT you don't want them to chat with others who use Skype for Business, choose **On only for allowed domains**.</span></span> <span data-ttu-id="0f3d9-114">Домен skype.com будет автоматически добавлен в список разрешенных.</span><span class="sxs-lookup"><span data-stu-id="0f3d9-114">When you enable contact with Skype users, skype.com is automatically added as an allowed domain behind the scenes.</span></span> 
    
    <span data-ttu-id="0f3d9-115">Если вы хотите разрешить связь с пользователями Skype для бизнеса из любых организаций в мире, кроме строго определенных, выберите пункт **Включить для всех, кроме заблокированных доменов** и щелкните знак **+**, чтобы добавить такие домены.</span><span class="sxs-lookup"><span data-stu-id="0f3d9-115">If you want to allow contact from all other businesses in the world using Skype for Business, except specific ones, choose **On except for blocked domains**, and choose **+** to add those domains.</span></span> <span data-ttu-id="0f3d9-116">С вами смогут связываться все, кроме пользователей указанных доменов.</span><span class="sxs-lookup"><span data-stu-id="0f3d9-116">Everyone will be able to contact you except people on those specific domains.</span></span> <span data-ttu-id="0f3d9-117">(Некоторые организации могут выбрать этот вариант, например, на время судебного разбирательства во избежание контакта с другими организациями.)</span><span class="sxs-lookup"><span data-stu-id="0f3d9-117">(Some businesses might choose this option, for example, if they are in litigation and need to ensure there's no contact with the other business.)</span></span>
    
5. <span data-ttu-id="0f3d9-118">Выберите пункт **Разрешить сотрудникам использовать Skype для бизнеса для связи с пользователями Skype вне организации**.</span><span class="sxs-lookup"><span data-stu-id="0f3d9-118">Choose **Let people use Skype for Business to communicate with Skype users outside your organization**.</span></span> 
    
6.  <span data-ttu-id="0f3d9-119">Если вы используете брандмауэр Windows, Skype для бизнеса откроет нужные порты автоматически.</span><span class="sxs-lookup"><span data-stu-id="0f3d9-119">If you're using Windows Firewall, Skype for Business opens the required ports automatically.</span></span>
    
    <span data-ttu-id="0f3d9-120">Если ваша организация использует другое решение для ограничения подключения компьютеров к Интернету, обязательно откройте клиентским компьютерам доступ к следующим [IP- и URL-адресам](https://support.office.com/en-us/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2) для подключения к Skype и поиска в каталоге Skype.</span><span class="sxs-lookup"><span data-stu-id="0f3d9-120">If your organization uses another solution to restrict computers on your network from connecting to the Internet, ensure client computers are able to access all of the [IP addresses and URLs](https://support.office.com/en-us/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2) for Skype connectivity and Skype Directory Search.</span></span> <span data-ttu-id="0f3d9-121">Возможно, для этого нужно будет добавить их в список разрешенных исходящих подключений в конфигурации брандмауэра или прокси-сервера.</span><span class="sxs-lookup"><span data-stu-id="0f3d9-121">This may require adding them to the outbound allow list in your firewall or proxy infrastructure configuration.</span></span>
    
7. <span data-ttu-id="0f3d9-122">**Перед проверкой подождите  24 часа**.</span><span class="sxs-lookup"><span data-stu-id="0f3d9-122">**WAIT UP TO 24 HOURS TO TEST**.</span></span> <span data-ttu-id="0f3d9-123">После изменения параметров внешней связи может потребоваться до 24 часов, чтобы изменения распространились на все центры обработки данных.</span><span class="sxs-lookup"><span data-stu-id="0f3d9-123">Any time you change the external communications settings, it can take up to 24 hours for the changes to populate across all the data centers.</span></span>
    
8. <span data-ttu-id="0f3d9-124">Продемонстрируйте пользователям, как находить и добавлять контакты Skype в списки контактов Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="0f3d9-124">Show your users how to find and add Skype contacts to their list of Skype for Business contacts.</span></span> <span data-ttu-id="0f3d9-125">Порекомендуйте им статью [Поиск пользователей в Skype для бизнеса](https://support.office.com/en-us/article/b12500ef-e37f-4d22-aade-c11277e53f19).</span><span class="sxs-lookup"><span data-stu-id="0f3d9-125">Point them to [Search for people in Skype for Business](https://support.office.com/en-us/article/b12500ef-e37f-4d22-aade-c11277e53f19).</span></span>
    
## <a name="test-and-troubleshoot"></a><span data-ttu-id="0f3d9-126">Проверка и устранение проблем</span><span class="sxs-lookup"><span data-stu-id="0f3d9-126">Test and troubleshoot</span></span>

<span data-ttu-id="0f3d9-127">Чтобы проверить настройки, требуется контакт в Skype, который не защищен брандмауэром компании.</span><span class="sxs-lookup"><span data-stu-id="0f3d9-127">To test your setup, you need a contact on Skype who's not behind your company firewall.</span></span> <span data-ttu-id="0f3d9-128">Войти в Skype можно с помощью учетной записи Gmail, Outlook.com или другой учетной записи электронной почты.</span><span class="sxs-lookup"><span data-stu-id="0f3d9-128">They can be signed in to Skype using a Gmail account, Outlook.com account, or other type of email account.</span></span>
  
1. <span data-ttu-id="0f3d9-129">После изменения настроек внешней связи **перед проверкой подождите 24 часа**.</span><span class="sxs-lookup"><span data-stu-id="0f3d9-129">After you change your external communications settings, **WAIT UP TO 24 HOURS TO TEST**.</span></span>
    
2. <span data-ttu-id="0f3d9-130">Выйдите из Skype для бизнеса и войдите снова, чтобы увидеть параметр "Поиск в каталоге Skype".</span><span class="sxs-lookup"><span data-stu-id="0f3d9-130">Sign out of Skype for Business and then sign in again so you see the option to search the Skype Directory.</span></span> 
    
    ![Выделив каталог Skype, вы можете выполнять поиск пользователей с учетными записями Skype.](../images/76ee9fab-1ac3-4f4a-9569-f5f2606dbb7a.png)
  
3. <span data-ttu-id="0f3d9-132">В Skype для бизнеса найдите контакт Skype и отправьте ему запрос на чат.</span><span class="sxs-lookup"><span data-stu-id="0f3d9-132">In Skype for Business, search for your contact in Skype, and send a request to chat.</span></span> 
    
    <span data-ttu-id="0f3d9-133">Если сообщение не удастся отправить из-за политики компании, проверьте [настройки брандмауэра](https://support.office.com/en-us/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2).</span><span class="sxs-lookup"><span data-stu-id="0f3d9-133">If you get the message it couldn't be sent due to company policy, you need to double-check your [firewall settings](https://support.office.com/en-us/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2).</span></span> 
    
4. <span data-ttu-id="0f3d9-134">Еще один способ проверить, связана ли проблема с брандмауэром, — подключиться к сети Wi-Fi, не защищенной брандмауэром, например в кафе, и отправить в Skype для бизнеса запрос на чат контакту Skype.</span><span class="sxs-lookup"><span data-stu-id="0f3d9-134">Another way to test whether the problem is your firewall is to go to a wifi location not behind your firewall such as a coffee shop, and use Skype for Business to send a request to your Skype contact to chat.</span></span> 
    
  - <span data-ttu-id="0f3d9-135">**Если вы отправили запрос контакту Skype, но он его не получил**, попросите контакта отправить вам запрос на чат.</span><span class="sxs-lookup"><span data-stu-id="0f3d9-135">**If you sent your Skype contact a request and they never received it**, ask them to send you a request to chat.</span></span> <span data-ttu-id="0f3d9-136">Если проблема была в установке соединения между Skype и Skype для бизнеса, обычно это позволяет решить ее.</span><span class="sxs-lookup"><span data-stu-id="0f3d9-136">If the problem was establishing a connection between Skype and Skype for Business, that often solves it.</span></span>
    
  - <span data-ttu-id="0f3d9-137">Если сообщение будет доставлено в кафе, хотя на работе сделать это не удается, значит, проблема в брандмауэре.</span><span class="sxs-lookup"><span data-stu-id="0f3d9-137">Now if the message goes through at the coffee shop but not when you're at work, then you know the problem is your firewall.</span></span> 
    
## <a name="what-you-can-and-cant-do"></a><span data-ttu-id="0f3d9-138">Доступные и недоступные действия</span><span class="sxs-lookup"><span data-stu-id="0f3d9-138">What you can and can't do</span></span>

- <span data-ttu-id="0f3d9-139">**Skype для бизнеса на Mac** не поддерживает поиск контактов Skype и общение с ними.</span><span class="sxs-lookup"><span data-stu-id="0f3d9-139">**Skype for Business on Mac** doesn't have the ability to search for and communicate with Skype contacts.</span></span>
    
- <span data-ttu-id="0f3d9-140">Если включен поиск в каталоге, вы можете искать пользователей Skype и Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="0f3d9-140">When directory search is enabled, you can search for and find Skype and Skype for Business users.</span></span> <span data-ttu-id="0f3d9-141">Если по какой-либо причине найти их в каталоге не удается, вы можете отправить им запрос на добавление в контакты, а затем попросить их зайти в Skype и принять его. Это позволит вам обмениваться с ними мгновенными сообщениями.</span><span class="sxs-lookup"><span data-stu-id="0f3d9-141">If for some reason you can't find them by searching the directory, you can send them a contact request, and then have them sign in to Skype and accept it, so you can IM with them.</span></span> 
    
- <span data-ttu-id="0f3d9-142">Вы не можете обмениваться мгновенными сообщениями с другими решениями для мгновенных сообщений, например от Google или Facebook.</span><span class="sxs-lookup"><span data-stu-id="0f3d9-142">It's not possible to allow IM connectivity with other IM providers such as Google or Facebook.</span></span> <span data-ttu-id="0f3d9-143">Вы не можете использовать Skype для бизнеса для отправки SMS.</span><span class="sxs-lookup"><span data-stu-id="0f3d9-143">You can't use Skype for Business to send cell phone text messages.</span></span>

- <span data-ttu-id="0f3d9-144">Вы не можете записывать голосовые или видеозвонки между пользователями Skype и Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="0f3d9-144">It is not possible to record audio or video calls between a Skype Contact and Skype for Business contact.</span></span>
    
## <a name="what-features-are-available-when-adding-skype-contacts"></a><span data-ttu-id="0f3d9-145">Какие функции доступны при добавлении контактов Skype?</span><span class="sxs-lookup"><span data-stu-id="0f3d9-145">What features are available when adding Skype contacts?</span></span>

<span data-ttu-id="0f3d9-146">Если пользователи Skype входят с учетной записью Майкрософт (в прошлом — Windows Live ID), то при общении с вашими пользователями Skype для бизнеса им будут доступны некоторые, хотя и не все, функции.</span><span class="sxs-lookup"><span data-stu-id="0f3d9-146">Skype contacts who signed in with their Microsoft account (formerly Windows Live ID) can get some, but not all, features when they are talking to your Skype for Business users.</span></span>
  
|<span data-ttu-id="0f3d9-147">**Доступно для контактов Skype**</span><span class="sxs-lookup"><span data-stu-id="0f3d9-147">**Available with Skype contacts**</span></span>|<span data-ttu-id="0f3d9-148">**Недоступно для контактов Skype**</span><span class="sxs-lookup"><span data-stu-id="0f3d9-148">**Not available with Skype contacts**</span></span>|
|:-----|:-----|
| <span data-ttu-id="0f3d9-149">Видеосвязь</span><span class="sxs-lookup"><span data-stu-id="0f3d9-149">Video conversations</span></span> <br/>  <span data-ttu-id="0f3d9-150">Личный обмен мгновенными сообщениями</span><span class="sxs-lookup"><span data-stu-id="0f3d9-150">Person-to-person instant messaging</span></span> <br/>  <span data-ttu-id="0f3d9-151">Отображение присутствия</span><span class="sxs-lookup"><span data-stu-id="0f3d9-151">Presence</span></span> <br/> | <span data-ttu-id="0f3d9-152">Многосторонние текстовые беседы</span><span class="sxs-lookup"><span data-stu-id="0f3d9-152">Multi-party IM conversations</span></span> <br/>  <span data-ttu-id="0f3d9-153">Голосовые и видеобеседы с тремя и более участниками</span><span class="sxs-lookup"><span data-stu-id="0f3d9-153">Audio and video conversations with three or more people</span></span> <br/>  <span data-ttu-id="0f3d9-154">Демонстрация рабочего стола и приложений</span><span class="sxs-lookup"><span data-stu-id="0f3d9-154">Desktop and program sharing</span></span> <br/> |
   
[!INCLUDE [LinkedIn Learning Info](../common/office/linkedin-learning-info.md)]
   
## <a name="related-topics"></a><span data-ttu-id="0f3d9-155">См. также:</span><span class="sxs-lookup"><span data-stu-id="0f3d9-155">Related topics</span></span>

[<span data-ttu-id="0f3d9-156">Разрешение пользователям на связь с внешними пользователями Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="0f3d9-156">Allow users to contact external Skype for Business users</span></span>](allow-users-to-contact-external-skype-for-business-users.md)
  
[<span data-ttu-id="0f3d9-157">Настройка Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="0f3d9-157">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)
