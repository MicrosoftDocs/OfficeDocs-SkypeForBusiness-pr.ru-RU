---
title: Разрешить внешним пользователям группы контактов
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
description: 'Узнайте, как Настройка групп, чтобы дать возможность пользователям обращаться к пользователей в другой организации или разрешить за пределами talk контактов к ним. '
ms.openlocfilehash: af4b6a61117e96fdbdf869b2bf7fc54c286b42f0
ms.sourcegitcommit: c05731b8a757864c0f6620bfeda3ae28a3582011
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/12/2018
ms.locfileid: "19863397"
---
# <a name="allow-users-to-contact-external-teams-users"></a><span data-ttu-id="ca2da-103">Разрешить внешним пользователям группы контактов</span><span class="sxs-lookup"><span data-stu-id="ca2da-103">Allow users to contact external Teams users</span></span>
  
<span data-ttu-id="ca2da-104">Действия, описанные в этом приведены в статье случаи использования:</span><span class="sxs-lookup"><span data-stu-id="ca2da-104">Use the steps in this article when:</span></span>
  
- <span data-ttu-id="ca2da-105">У вас есть пользователи в разных доменах в бизнесе.</span><span class="sxs-lookup"><span data-stu-id="ca2da-105">You have users on different domains in your business.</span></span> <span data-ttu-id="ca2da-106">Например Rob@ContosoEast.com и Ann@ContosoWest.com.</span><span class="sxs-lookup"><span data-stu-id="ca2da-106">For example, Rob@ContosoEast.com and Ann@ContosoWest.com.</span></span>
    
- <span data-ttu-id="ca2da-107">Чтобы получатели, в вашей организации для работы групп пользователей в конкретных предприятия за пределами вашей организации.</span><span class="sxs-lookup"><span data-stu-id="ca2da-107">You want the people in your organization to use Teams to contact people in specific businesses outside of your organization.</span></span>
    
- <span data-ttu-id="ca2da-108">Предполагается, что у других пользователей в мире, который использует группы должны иметь возможность поиска и связи с вами с помощью свой адрес электронной почты.</span><span class="sxs-lookup"><span data-stu-id="ca2da-108">You want anyone else in the world who uses Teams to be able to find and contact you, using your email address.</span></span> <span data-ttu-id="ca2da-109">Если вы и они используют параметры по умолчанию, этот вариант возможен автоматически.</span><span class="sxs-lookup"><span data-stu-id="ca2da-109">If you and they use the default settings, this will work automatically.</span></span> <span data-ttu-id="ca2da-110">В противном случае необходимости убедитесь, что их конфигурации не блокирует вашего домена.</span><span class="sxs-lookup"><span data-stu-id="ca2da-110">If they don't, then they need to make sure their configuration isn't blocking your domain.</span></span>
    
## <a name="enable-business-to-business-communications-for-your-users"></a><span data-ttu-id="ca2da-111">Включить бизнес бизнес связь для пользователей</span><span class="sxs-lookup"><span data-stu-id="ca2da-111">Enable business-to-business communications for your users</span></span>
<span data-ttu-id="ca2da-112"><a name="bk_preview"> </a></span><span class="sxs-lookup"><span data-stu-id="ca2da-112"></span></span>

<span data-ttu-id="ca2da-113">В обеих организациях для этого необходимо иметь [разрешения администратора](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) в Office 365.</span><span class="sxs-lookup"><span data-stu-id="ca2da-113">You must have [admin permissions](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) in Office 365 in both organizations to do this.</span></span>

<span data-ttu-id="ca2da-114">![команды логотип 30x30.png](media/teams-logo-30x30.png)**с помощью групп Майкрософт и Скайп по центру администрирования бизнеса**.</span><span class="sxs-lookup"><span data-stu-id="ca2da-114">![teams-logo-30x30.png](media/teams-logo-30x30.png)**Using the Microsoft Teams and Skype for Business Admin Center**.</span></span>
1. <span data-ttu-id="ca2da-115">В левой области переходов, перейдите в раздел **масштабе организации параметры** > **внешнего доступа**.</span><span class="sxs-lookup"><span data-stu-id="ca2da-115">In the left navigation, go to **Org-wide settings** > **External access**.</span></span> 

2. <span data-ttu-id="ca2da-116">В верхней части страницы **внешнего доступа** Включение **внешнего доступа**.</span><span class="sxs-lookup"><span data-stu-id="ca2da-116">At the top of the **External access** page, turn on **External access**.</span></span> 

3. <span data-ttu-id="ca2da-117">Также можно отправить электронное письмо пользователю с помощью параметров аудиоконференции, выбрав на странице свойств аудиоконференции для пользователя параметр **Отправить информацию о конференции по электронной почте**.</span><span class="sxs-lookup"><span data-stu-id="ca2da-117">Click **Save**.</span></span> 

4. <span data-ttu-id="ca2da-118">Убедитесь, что администратор другой организации образом те же действия и вводит домена для бизнеса, как разрешенных доменов.</span><span class="sxs-lookup"><span data-stu-id="ca2da-118">Make sure the admin in the other organization follows the same steps and enters the domain for your business as an allowed domain.</span></span>
 
5. <span data-ttu-id="ca2da-p103">**ПЕРЕД ПРОВЕРКОЙ ПОДОЖДИТЕ 24 ЧАСА**. После изменения внешних параметров связи может потребоваться до 24 часов для их распространения по всем центрам обработки данных.</span><span class="sxs-lookup"><span data-stu-id="ca2da-p103">**WAIT UP TO 24 HOURS TO TEST**. Any time you change the external communications settings, it can take up to 24 hours for the changes to populate across all the data centers.</span></span>

  
## <a name="test-and-troubleshoot"></a><span data-ttu-id="ca2da-121">Проверка и устранение проблем</span><span class="sxs-lookup"><span data-stu-id="ca2da-121">Test and troubleshoot</span></span>
<span data-ttu-id="ca2da-122"><a name="bk_preview"> </a></span><span class="sxs-lookup"><span data-stu-id="ca2da-122"></span></span>

 <span data-ttu-id="ca2da-123">**Наиболее распространенные проблемы, которые людей возникнуть при настройке бизнес делового общения правильного их [Office 365 URL-адреса и диапазоны IP-адресов](https://docs.microsoft.com/en-us/microsoftteams/office-365-urls-ip-address-ranges) .**</span><span class="sxs-lookup"><span data-stu-id="ca2da-123">**The most common issue people encounter when setting up business-to-business communication is getting their [Office 365 URLs and IP address ranges](https://docs.microsoft.com/en-us/microsoftteams/office-365-urls-ip-address-ranges) right.**</span></span>
  
<span data-ttu-id="ca2da-124">Чтобы проверить настройки, необходимо контакт в группах, который не является за брандмауэром вашей компании.</span><span class="sxs-lookup"><span data-stu-id="ca2da-124">To test your setup, you need a contact on Teams who's not behind your company firewall.</span></span>
  
1. <span data-ttu-id="ca2da-125">После можно изменить параметры внешнего доступа, **TEST кому ОЖИДАТЬ до 24 часов**.</span><span class="sxs-lookup"><span data-stu-id="ca2da-125">After you change your External Access settings, **WAIT UP TO 24 HOURS TO TEST**.</span></span>
    
2. <span data-ttu-id="ca2da-126">Поиск контактов в группах и отправить запрос в чате.</span><span class="sxs-lookup"><span data-stu-id="ca2da-126">Search for your contact in Teams, and send a request to chat.</span></span>
    
    <span data-ttu-id="ca2da-127">Если вы получаете сообщение, оно не доставлено из-за политики компании, необходимо еще раз проверьте к [Office 365 URL-адреса и диапазоны IP-адресов](https://docs.microsoft.com/en-us/microsoftteams/office-365-urls-ip-address-ranges).</span><span class="sxs-lookup"><span data-stu-id="ca2da-127">If you get a message that it couldn't be sent due to company policy, you need to double-check your [Office 365 URLs and IP address ranges](https://docs.microsoft.com/en-us/microsoftteams/office-365-urls-ip-address-ranges).</span></span>
    
3. <span data-ttu-id="ca2da-128">Попросите контакт для отправки запроса в чате.</span><span class="sxs-lookup"><span data-stu-id="ca2da-128">Ask your contact to send you a request to chat.</span></span> <span data-ttu-id="ca2da-129">Если вы не получите свой запрос, проблема заключается в настройках брандмауэра (если они уже подтверждения правильности их параметры брандмауэра).</span><span class="sxs-lookup"><span data-stu-id="ca2da-129">If you don't receive their request, the problem is your firewall settings (assuming they've already confirmed their firewall settings are correct).</span></span>
    
4. <span data-ttu-id="ca2da-130">Другой способ проверки, является ли проблема брандмауэра — это расположение wifi не за брандмауэром, таких как кафе и использование команды Отправить запрос контакту чата.</span><span class="sxs-lookup"><span data-stu-id="ca2da-130">Another way to test whether the problem is your firewall is to go to a wifi location not behind your firewall such as a coffee shop, and use Teams to send a request to your contact to chat.</span></span> <span data-ttu-id="ca2da-131">Если сообщение проходит через существует, но не в том случае, когда вы находитесь на работе, это значит, проблема является брандмауэра.</span><span class="sxs-lookup"><span data-stu-id="ca2da-131">If the message goes through there, but not when you're at work, then you know the problem is your firewall.</span></span>
    
## <a name="how-to-find-others-and-be-found-when-connecting-with-another-business"></a><span data-ttu-id="ca2da-132">Как найти других пользователей и найти, при подключении через другой компании</span><span class="sxs-lookup"><span data-stu-id="ca2da-132">How to find others, and be found, when connecting with another business</span></span>
<span data-ttu-id="ca2da-133"><a name="bk_preview"> </a></span><span class="sxs-lookup"><span data-stu-id="ca2da-133"></span></span>

<span data-ttu-id="ca2da-134">При включении внешнего доступа с другими пользователями группами пользователей можно найти федеративных пользователей группам поиск по ключевым словам их учетное имя: например, Rob@contoso.com.</span><span class="sxs-lookup"><span data-stu-id="ca2da-134">After you enable External Access with other Teams users, your users can find federated Teams users by searching for their sign-in name: for example, Rob@contoso.com.</span></span> <span data-ttu-id="ca2da-135">Затем необходимо добавить пользователя в свой список контактов.</span><span class="sxs-lookup"><span data-stu-id="ca2da-135">Then they will need to add the person to their list of contacts.</span></span>
  
  
## <a name="tips-on-setting-up-communications-with-federated-businesses"></a><span data-ttu-id="ca2da-136">Советы по настройке связь с федеративными бизнеса</span><span class="sxs-lookup"><span data-stu-id="ca2da-136">Tips on setting up communications with federated businesses</span></span>
<span data-ttu-id="ca2da-137"><a name="bk_preview"> </a></span><span class="sxs-lookup"><span data-stu-id="ca2da-137"></span></span>
    
- <span data-ttu-id="ca2da-138">Когда двух групп пользователей с Office 365 доменами обмениваются данными друг с другом в разных доменах, их можно использовать только функции группы (например, видеобеседы или рабочему столу), которые включены в обеих организациях.</span><span class="sxs-lookup"><span data-stu-id="ca2da-138">When two Teams users with Office 365 domains are communicating with each other on separate domains, they can only use Teams features (for example, video conversations or desktop sharing) that are turned on in both organizations.</span></span>
    
- <span data-ttu-id="ca2da-139">Если группы пользователей в вашей организации поместить на месте или хранение для судебного разбирательства, любой мгновенные сообщения от этого пользователя и другие Скайп для бизнеса или Скайп пользователей будут сохраняться **Восстанавливаемых элементов** в почтовом ящике.</span><span class="sxs-lookup"><span data-stu-id="ca2da-139">If Teams users in your organization is put on an In-Place or Litigation Hold, any IM conversations between that user and other Skype for Business or Skype users will be saved in **Recoverable Items** in their mailbox.</span></span> <span data-ttu-id="ca2da-140">Эти беседы не сохраняются в папке **Журнала бесед** в почтовом ящике.</span><span class="sxs-lookup"><span data-stu-id="ca2da-140">These conversations aren't saved in the **Conversations History** folder in their mailbox.</span></span>
  
<span data-ttu-id="ca2da-141"><a name="bk_preview"> </a></span><span class="sxs-lookup"><span data-stu-id="ca2da-141"></span></span>
 
