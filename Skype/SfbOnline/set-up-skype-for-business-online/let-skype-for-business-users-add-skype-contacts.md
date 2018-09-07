---
title: Разрешение на добавление контактов Skype пользователям Skype для бизнеса
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: 08666236-1894-42ae-8846-e49232bbc460
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Setup
- LIL_Placement
description: 'See how to  let people who are using Skype for Business contact Skype for Business users from outside your organization and add them to their list of contacts. '
ms.openlocfilehash: 98701f55bd1cdf2c6a5f8177d05a95030a4a04a5
ms.sourcegitcommit: 2a6e499165424fe2d189ad140951e222c8ba9c81
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2018
ms.locfileid: "23850092"
---
# <a name="let-skype-for-business-users-add-skype-contacts"></a><span data-ttu-id="a7c52-103">Разрешение на добавление контактов Skype пользователям Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="a7c52-103">Let Skype for Business users add Skype contacts</span></span>

<span data-ttu-id="a7c52-p101">[] В Skype для бизнеса поддерживается поиск любых пользователей бесплатной версии Skype и общение с ними! В этой статье рассказывается о том, как добавлять контакты Skype.</span><span class="sxs-lookup"><span data-stu-id="a7c52-p101">With Skype for Business, your users can search for and IM with everyone who uses Skype, the free app! This article explains what you need to do so they can add Skype contacts.</span></span> 
  
<span data-ttu-id="a7c52-106">Для этого необходимы [Роли администраторов в Office 365](https://support.office.com/en-us/article/da585eea-f576-4f55-a1e0-87090b6aaa9d?ui=en-US&rs=en-US&ad=US) в Office 365.</span><span class="sxs-lookup"><span data-stu-id="a7c52-106">You must have [admin permissions](https://support.office.com/en-us/article/da585eea-f576-4f55-a1e0-87090b6aaa9d?ui=en-US&rs=en-US&ad=US) in Office 365 to do this.</span></span>

<span data-ttu-id="a7c52-107">![sfb логотип 30x30.png](../images/sfb-logo-30x30.png) **с помощью Скайп по центру администрирования бизнеса**</span><span class="sxs-lookup"><span data-stu-id="a7c52-107">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>
  
1. <span data-ttu-id="a7c52-108">Выполните вход с учетной записью администратора Office 365 в [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home#/homepage).</span><span class="sxs-lookup"><span data-stu-id="a7c52-108">Sign in with your Office 365 admin account at [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home#/homepage).</span></span>
    
2. <span data-ttu-id="a7c52-109">В Центр администрирования Office 365 последовательно выберите пункты **Центры администрирования** > **Skype для бизнеса**.</span><span class="sxs-lookup"><span data-stu-id="a7c52-109">In the Office 365 admin center, go to **Admin Centers** > **Skype for Business**.</span></span> 
    
    ![Choose the Skype for Business admin center.](../images/376a7a45-e6e3-4716-be09-d2f294d885a2.png)
  
3. <span data-ttu-id="a7c52-111">В **Центр администрирования Skype для бизнеса**выберите пункты **оОрганизация** > **Ввнешняяие связьи**.</span><span class="sxs-lookup"><span data-stu-id="a7c52-111">In the **Skype for Business admin center**, choose **Organization** > **External communications**.</span></span> 
    
4. <span data-ttu-id="a7c52-112">По умолчанию ваши пользователи могут общаться с другими пользователями Skype для бизнеса (если в брандмауэре настроены эти разрешения).</span><span class="sxs-lookup"><span data-stu-id="a7c52-112">By default, your users can communicate with all other people in the world who use Skype for Business (assuming your firewall has been configured to allow this).</span></span> 
    
    ![Choose Let people use Skype for Business to communicate with Skype.](../images/333789f8-2ea6-4bbd-805b-18130f427999.png)
  
    <span data-ttu-id="a7c52-p102">Если вы хотите, чтобы ваши пользователи общались с пользователями Skype, но не с пользователями Skype для бизнеса, выберите пункт **Включить только для разрешенных доменов**. Домен skype.com будет автоматически добавлен в список разрешенных.</span><span class="sxs-lookup"><span data-stu-id="a7c52-p102">If you want your users to chat with Skype users, BUT you don't want them to chat with others who use Skype for Business, choose **On only for allowed domains**. When you enable contact with Skype users, skype.com is automatically added as an allowed domain behind the scenes.</span></span> 
    
    <span data-ttu-id="a7c52-p103">Если вы хотите разрешить контакту из любой другой организации, кроме указанных, использовать Skype для бизнеса, выберите пункт **Включить для всех, кроме заблокированных доменов** и щелкните знак **+**, чтобы добавить домены. С вами смогут связываться все, кроме пользователей указанных доменов. (Некоторые организации могут выбрать этот вариант, например, на время судебного разбирательства во избежание контакта с другими организациями.)</span><span class="sxs-lookup"><span data-stu-id="a7c52-p103">If you want to allow contact from all other businesses in the world using Skype for Business, except specific ones, choose **On except for blocked domains**, and choose **+** to add those domains. Everyone will be able to contact you except people on those specific domains. (Some businesses might choose this option, for example, if they are in litigation and need to ensure there's no contact with the other business.)</span></span>
    
5. <span data-ttu-id="a7c52-119">Выберите пункт **РазрешитьSkype для бизнеса, чтобы пользователи могли связаться с пользователями Skype за пределами вашей организации**.</span><span class="sxs-lookup"><span data-stu-id="a7c52-119">Choose **Let people use Skype for Business to communicate with Skype users outside your organization**.</span></span> 
    
6.  <span data-ttu-id="a7c52-120">При использовании брандмауэра Windows Skype для бизнеса откроет нужные порты автоматически.</span><span class="sxs-lookup"><span data-stu-id="a7c52-120">If you're using Windows Firewall, Skype for Business opens the required ports automatically.</span></span>
    
    <span data-ttu-id="a7c52-p104">Если в вашей организации используется другое решение для ограничения подключения компьютеров к Интернету, убедитесь, что клиентские компьютеры имеют доступ ко всем [URL-адреса и диапазоны IP-адресов Office 365](https://support.office.com/en-us/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2) для связи по Skype и поиска в каталоге Skype. Для этого может потребоваться добавить их в список внешних разрешений в брандмауэре или в конфигурации инфраструктуры сети.</span><span class="sxs-lookup"><span data-stu-id="a7c52-p104">If your organization uses another solution to restrict computers on your network from connecting to the Internet, ensure client computers are able to access all of the [IP addresses and URLs](https://support.office.com/en-us/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2) for Skype connectivity and Skype Directory Search. This may require adding them to the outbound allow list in your firewall or proxy infrastructure configuration.</span></span>
    
7. <span data-ttu-id="a7c52-p105">**ПЕРЕД ПРОВЕРКОЙ ПОДОЖДИТЕ 24 ЧАСА**. После изменения внешних параметров связи может потребоваться до 24 часов для их распространения по всем центрам обработки данных.</span><span class="sxs-lookup"><span data-stu-id="a7c52-p105">**WAIT UP TO 24 HOURS TO TEST**. Any time you change the external communications settings, it can take up to 24 hours for the changes to populate across all the data centers.</span></span>
    
8. <span data-ttu-id="a7c52-p106">Покажите пользователям, как находить других пользователей Skype и добавлять их в свой список контактов в Skype для бизнеса. Порекомендуйте пользователям ознакомиться с разделом [Поиск пользователей в Skype для бизнеса](https://support.office.com/en-us/article/b12500ef-e37f-4d22-aade-c11277e53f19).</span><span class="sxs-lookup"><span data-stu-id="a7c52-p106">Show your users how to find and add Skype contacts to their list of Skype for Business contacts. Point them to [Search for people in Skype for Business](https://support.office.com/en-us/article/b12500ef-e37f-4d22-aade-c11277e53f19).</span></span>
    
## <a name="test-and-troubleshoot"></a><span data-ttu-id="a7c52-127">Проверка и устранение проблем</span><span class="sxs-lookup"><span data-stu-id="a7c52-127">Test and troubleshoot</span></span>

<span data-ttu-id="a7c52-p107">Чтобы проверить настройки, требуется контакт в Skype, который не защищен брандмауэром компании. Войти в Skype можно с помощью учетной записи Gmail, Outlook.com или другой учетной записи электронной почты.</span><span class="sxs-lookup"><span data-stu-id="a7c52-p107">To test your setup, you need a contact on Skype who's not behind your company firewall. They can be signed in to Skype using a Gmail account, Outlook.com account, or other type of email account.</span></span>
  
1. <span data-ttu-id="a7c52-130">После изменения настроек внешней связи **подождите до 24 часов перед тем, как проверять их**.</span><span class="sxs-lookup"><span data-stu-id="a7c52-130">After you change your external communications settings, **WAIT UP TO 24 HOURS TO TEST**.</span></span>
    
2. <span data-ttu-id="a7c52-131">Выйдите из Skype для бизнеса и снова войдите, чтобы увидеть параметр "Поиск в каталоге Skype".</span><span class="sxs-lookup"><span data-stu-id="a7c52-131">Sign out of Skype for Business and then sign in again so you see the option to search the Skype Directory.</span></span> 
    
    ![When Skype Directory is highlighted, you can search for people who have Skype accounts.](../images/76ee9fab-1ac3-4f4a-9569-f5f2606dbb7a.png)
  
3. <span data-ttu-id="a7c52-133">В Skype для бизнеса найдите контакт со Skype и отправьте ему запрос на беседу.</span><span class="sxs-lookup"><span data-stu-id="a7c52-133">In Skype for Business, search for your contact in Skype, and send a request to chat.</span></span> 
    
    <span data-ttu-id="a7c52-134">Если сообщение не удастся отправить из-за политики компании, нужно проверить [URL-адреса и диапазоны IP-адресов Office 365](https://support.office.com/en-us/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2).</span><span class="sxs-lookup"><span data-stu-id="a7c52-134">If you get the message it couldn't be sent due to company policy, you need to double-check your [firewall settings](https://support.office.com/en-us/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2).</span></span> 
    
4. <span data-ttu-id="a7c52-135">Еще один способ проверить, связано ли это с брандмауэром,  подключиться к сети Wi-Fi, не защищенной брандмауэром, например, в кафе, и отправить в Skype для бизнеса запрос на беседу контакту в Skype.</span><span class="sxs-lookup"><span data-stu-id="a7c52-135">Another way to test whether the problem is your firewall is to go to a wifi location not behind your firewall such as a coffee shop, and use Skype for Business to send a request to your Skype contact to chat.</span></span> 
    
  - <span data-ttu-id="a7c52-p108">**Если вы отправили запрос контакту Skype, но он его не получил**, попросите контакт отправить вам запрос на чат. Если проблема была в установке соединения между Skype и Skype для бизнеса, обычно она устраняется.</span><span class="sxs-lookup"><span data-stu-id="a7c52-p108">**If you sent your Skype contact a request and they never received it**, ask them to send you a request to chat. If the problem was establishing a connection between Skype and Skype for Business, that often solves it.</span></span>
    
  - <span data-ttu-id="a7c52-138">Если сообщение будет доставлено, хотя на работе этого не удается сделать, значит, проблема в брандмауэре.</span><span class="sxs-lookup"><span data-stu-id="a7c52-138">Now if the message goes through at the coffee shop but not when you're at work, then you know the problem is your firewall.</span></span> 
    
## <a name="what-you-can-and-cant-do"></a><span data-ttu-id="a7c52-139">Что можно и что нельзя делать</span><span class="sxs-lookup"><span data-stu-id="a7c52-139">What you can and can't do</span></span>

- <span data-ttu-id="a7c52-140">**Skype для бизнесаВ Mac** не поддерживается поиск контактов Skype и взаимодействие с ними.</span><span class="sxs-lookup"><span data-stu-id="a7c52-140">**Skype for Business on Mac** doesn't have the ability to search for and communicate with Skype contacts.</span></span>
    
- <span data-ttu-id="a7c52-p109">Хотя вы можете искать и находить других пользователей Skype, эти пользователи не могут искать и находить пользователей Skype для бизнеса. Вам нужно отправить им запрос контактных данных, а им следует войти в Skype и принять запрос. Только после этого вы сможете обмениваться с ними сообщениями.</span><span class="sxs-lookup"><span data-stu-id="a7c52-p109">When directory search is enabled, you can search for and find Skype and Skype for Business users. If for some reason you can't find them by searching the directory, you can send them a contact request, and then have them sign in to Skype and accept it, so you can IM with them.</span></span> 
    
- <span data-ttu-id="a7c52-p110">Взаимодействие с другими поставщиками услуг обмена мгновенными сообщениями, такими как Google или Facebook, не поддерживается. Skype для бизнеса нельзя использовать для отправки SMS.</span><span class="sxs-lookup"><span data-stu-id="a7c52-p110">It's not possible to allow IM connectivity with other IM providers such as Google or Facebook. You can't use Skype for Business to send cell phone text messages.</span></span>

- <span data-ttu-id="a7c52-145">Какие возможности доступны при добавлении контактов Skype?</span><span class="sxs-lookup"><span data-stu-id="a7c52-145">It is not possible to record audio or video calls between a Skype Contact and Skype for Business contact.</span></span>
    
## <a name="what-features-are-available-when-adding-skype-contacts"></a><span data-ttu-id="a7c52-146">При общении с пользователями Skype пользователи Skype для бизнеса, выполнившие вход под учетной записью Майкрософт (ранее Windows Live ID), могут получить доступ лишь к некоторым функциям.</span><span class="sxs-lookup"><span data-stu-id="a7c52-146">What features are available when adding Skype contacts?</span></span>

<span data-ttu-id="a7c52-147">Если пользователи Skype входят с учетной записью Майкрософт (в прошлом — Windows Live ID), то при общении с вашими пользователями Skype для бизнеса им будут доступны некоторые, хотя и не все, функции.</span><span class="sxs-lookup"><span data-stu-id="a7c52-147">Skype contacts who signed in with their Microsoft account (formerly Windows Live ID) can get some, but not all, features when they are talking to your Skype for Business users.</span></span>
  
|<span data-ttu-id="a7c52-148">**Недоступно при общении с контактами Skype**</span><span class="sxs-lookup"><span data-stu-id="a7c52-148">**Available with Skype contacts**</span></span>|<span data-ttu-id="a7c52-149">Видеобеседы</span><span class="sxs-lookup"><span data-stu-id="a7c52-149">**Not available with Skype contacts**</span></span>|
|:-----|:-----|
| <span data-ttu-id="a7c52-150">Прямой обмен сообщениями между пользователями</span><span class="sxs-lookup"><span data-stu-id="a7c52-150">Video conversations</span></span> <br/>  <span data-ttu-id="a7c52-151">Информация о присутствии</span><span class="sxs-lookup"><span data-stu-id="a7c52-151">Person-to-person instant messaging</span></span> <br/>  <span data-ttu-id="a7c52-152">Обмен мгновенными сообщениями с несколькими собеседниками</span><span class="sxs-lookup"><span data-stu-id="a7c52-152">Presence</span></span> <br/> | <span data-ttu-id="a7c52-153">Голосовые звонки и видеозвонки с участием трех и более пользователей</span><span class="sxs-lookup"><span data-stu-id="a7c52-153">Multi-party IM conversations</span></span> <br/>  <span data-ttu-id="a7c52-154">Показ рабочего стола и программ</span><span class="sxs-lookup"><span data-stu-id="a7c52-154">Audio and video conversations with three or more people</span></span> <br/>  <span data-ttu-id="a7c52-155">Демонстрация рабочего стола и приложений</span><span class="sxs-lookup"><span data-stu-id="a7c52-155">Desktop and program sharing</span></span> <br/> |
   
[!INCLUDE [LinkedIn Learning Info](../../common/office/linkedin-learning-info.md)]
   
## <a name="related-topics"></a><span data-ttu-id="a7c52-156">См. также:</span><span class="sxs-lookup"><span data-stu-id="a7c52-156">Related topics</span></span>

[<span data-ttu-id="a7c52-157">Разрешение пользователям на связь с внешними пользователями Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="a7c52-157">Allow users to contact external Skype for Business users</span></span>](allow-users-to-contact-external-skype-for-business-users.md)
  
[<span data-ttu-id="a7c52-158">Настройка Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="a7c52-158">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)

  
 