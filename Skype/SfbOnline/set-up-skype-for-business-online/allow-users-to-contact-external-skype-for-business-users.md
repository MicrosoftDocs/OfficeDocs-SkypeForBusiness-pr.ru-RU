---
title: Разрешите пользователям связываться с внешними пользователями Skype для бизнеса
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: b414873a-0059-4cd5-aea1-e5d0857dbc94
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1_keywords:
- For O365M_ShareLync
- ms.lync.lac.OrgExternalAccess
- ms.lync.lac.skypefederation
- O365E_HRCLYNC _ SipFederationSrvRecordVerified_FL312122
- O365E_ShareLync
- O365M_ShareLync
- O365P_ExternalCommDesc
- O365P_ShareLync
ms.custom:
- Setup
- LIL_Placement
description: 'Узнайте, как настроить Skype для бизнеса, чтобы пользователи могли общаться с пользователями в другой организации, или разрешать им доступ к внешним контактам. '
ms.openlocfilehash: 570861f532371dc8eca253956ffdd200e60f5990
ms.sourcegitcommit: 4c041e8a7c39bd6517605ed7fc9aab18cf466596
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/18/2019
ms.locfileid: "35792687"
---
# <a name="allow-users-to-contact-external-skype-for-business-users"></a><span data-ttu-id="9f4ed-103">Разрешите пользователям связываться с внешними пользователями Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="9f4ed-103">Allow users to contact external Skype for Business users</span></span>

> [!NOTE]
> <span data-ttu-id="9f4ed-104">Федерация Skype для бизнеса недоступна для Office 365, предоставляемых 21Vianet и организациями Office 365 для Германии.</span><span class="sxs-lookup"><span data-stu-id="9f4ed-104">Skype for Business federation isn't available to Office 365 operated by 21Vianet and Office 365 Germany organizations.</span></span> 
  
<span data-ttu-id="9f4ed-105">Выполните действия, описанные в этой статье, в следующих случаях:</span><span class="sxs-lookup"><span data-stu-id="9f4ed-105">Use the steps in this article when:</span></span>
  
- <span data-ttu-id="9f4ed-106">У вас есть пользователи в разных доменах вашего бизнеса.</span><span class="sxs-lookup"><span data-stu-id="9f4ed-106">You have users on different domains in your business.</span></span> <span data-ttu-id="9f4ed-107">Например, Rob@ContosoEast.com и Ann@ContosoWest.com.</span><span class="sxs-lookup"><span data-stu-id="9f4ed-107">For example, Rob@ContosoEast.com and Ann@ContosoWest.com.</span></span>
    
- <span data-ttu-id="9f4ed-108">Вы хотите, чтобы сотрудники вашей организации использовали Skype для бизнеса для общения с людьми в конкретных организациях за пределами вашей организации.</span><span class="sxs-lookup"><span data-stu-id="9f4ed-108">You want the people in your organization to use Skype for Business to contact people in specific businesses outside of your organization.</span></span>
    
- <span data-ttu-id="9f4ed-109">Вы хотите, чтобы любой человек в мире, использующий Skype для бизнеса, мог находить вас и общаться с вами, используя свой адрес электронной почты.</span><span class="sxs-lookup"><span data-stu-id="9f4ed-109">You want anyone else in the world who uses Skype for Business to be able to find and contact you, using your email address.</span></span> <span data-ttu-id="9f4ed-110">Если вы и используете параметры Skype для бизнеса по умолчанию, это будет работать автоматически.</span><span class="sxs-lookup"><span data-stu-id="9f4ed-110">If you and they use the default Skype for Business settings, this will work automatically.</span></span> <span data-ttu-id="9f4ed-111">В противном случае необходимо убедиться в том, что их конфигурация не блокирует ваш домен.</span><span class="sxs-lookup"><span data-stu-id="9f4ed-111">If they don't, then they need to make sure their configuration isn't blocking your domain.</span></span>
    
## <a name="enable-business-to-business-communications-for-your-users"></a><span data-ttu-id="9f4ed-112">Включение деловых связей между пользователями</span><span class="sxs-lookup"><span data-stu-id="9f4ed-112">Enable business-to-business communications for your users</span></span>
<span data-ttu-id="9f4ed-113"><a name="bk_preview"> </a></span><span class="sxs-lookup"><span data-stu-id="9f4ed-113"></span></span>

<span data-ttu-id="9f4ed-114">Для этого вы должны иметь [разрешения администратора](https://support.office.com/en-us/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) в Office 365 в обеих организациях.</span><span class="sxs-lookup"><span data-stu-id="9f4ed-114">You must have [admin permissions](https://support.office.com/en-us/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) in Office 365 in both organizations to do this.</span></span>

<span data-ttu-id="9f4ed-115">![Значок с логотипом](../images/teams-logo-30x30.png) Microsoft Teams **, в котором используется центр администрирования Teams**</span><span class="sxs-lookup"><span data-stu-id="9f4ed-115">![An icon showing the Microsoft Teams logo](../images/teams-logo-30x30.png) **Using the Teams admin center**</span></span>
  
1. <span data-ttu-id="9f4ed-116">Войдите в систему с помощью учетной записи администратора Office 365.</span><span class="sxs-lookup"><span data-stu-id="9f4ed-116">Sign in with your Office 365 admin account.</span></span> 
    
2. <span data-ttu-id="9f4ed-117">В центре администрирования перейдите в раздел **центры** > администрирования**Teams**.</span><span class="sxs-lookup"><span data-stu-id="9f4ed-117">In the admin center, go to **Admin Centers** > **Teams**.</span></span>
    
    ![Выберите администратора Teams.](../images/MS-Teams-Admin.png)
  
3. <span data-ttu-id="9f4ed-119">В **центре Teams**выберите собственный \*\*\*\* > **портал** 
 ![Skype выберите устаревший портал SfB.](../images/SFBlegacy-size65.png)</span><span class="sxs-lookup"><span data-stu-id="9f4ed-119">In the **Teams center**, choose **Skype** > **Legacy Portal** 
![Choose the SfB Legacy Portal.](../images/SFBlegacy-size65.png)</span></span>
 
4. <span data-ttu-id="9f4ed-120">В **центре администрирования Skype для бизнеса выберите "** **внешняя связь** **Организации** > ".</span><span class="sxs-lookup"><span data-stu-id="9f4ed-120">In the **Skype for Business admin center** , choose **Organization** > **External communications**.</span></span>
5. <span data-ttu-id="9f4ed-121">Чтобы настроить связь с конкретными организациями или пользователями в другом домене, в раскрывающемся списке выберите **только для разрешенных доменов**.</span><span class="sxs-lookup"><span data-stu-id="9f4ed-121">To set up communication with a specific business or with users in another domain, in the drop-down box, choose **On only for allowed domains**.</span></span>
    
    <span data-ttu-id="9f4ed-122">Кроме того, если вы хотите разрешить связь со всеми другими людьми в мире с открытыми политиками Skype для бизнеса, выберите **включить для**всех пользователей, за исключением заблокированных доменов.</span><span class="sxs-lookup"><span data-stu-id="9f4ed-122">OR, if you want to enable communication with everyone else in the world who has open Skype for Business policies, choose **On except for blocked domains**.</span></span> <span data-ttu-id="9f4ed-123">Это значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="9f4ed-123">This is the default setting.</span></span>
    
6. <span data-ttu-id="9f4ed-124">В разделе **Заблокированные или разрешенные домены**выберите **+** и добавьте имя домена, который вы хотите разрешить.</span><span class="sxs-lookup"><span data-stu-id="9f4ed-124">Under **Blocked or allowed domains**, choose **+** and add the name of the domain you want to allow.</span></span>
    
7. <span data-ttu-id="9f4ed-125">Убедитесь, что администратор из другой организации производит те же действия, что и в **центре администрирования Skype для бизнеса**.</span><span class="sxs-lookup"><span data-stu-id="9f4ed-125">Make sure the admin in the other organization does these same steps in their **Skype for Business admin center**.</span></span> <span data-ttu-id="9f4ed-126">Например, в списке **разрешенных доменов** администратор должен ввести домен для вашего бизнеса.</span><span class="sxs-lookup"><span data-stu-id="9f4ed-126">For example, in their **allowed domains** list, their admin needs to enter the domain for your business.</span></span>
    
8. <span data-ttu-id="9f4ed-127">Если вы используете брандмауэр Windows, в Skype для бизнеса автоматически открываются нужные порты.</span><span class="sxs-lookup"><span data-stu-id="9f4ed-127">If you're using Windows Firewall, Skype for Business opens the required ports automatically.</span></span>
    
    <span data-ttu-id="9f4ed-128">Если в вашей организации используется другой брандмауэр для ограничения доступа компьютеров сети к Интернету, убедитесь, что клиентские компьютеры имеют доступ к следующим адресам URL-адреса [Office 365 и диапазоны IP-адресов](https://docs.microsoft.com/microsoftteams/office-365-urls-ip-address-ranges).</span><span class="sxs-lookup"><span data-stu-id="9f4ed-128">If your organization is using a different firewall solution to restrict computers on your network from connecting to the Internet, ensure your client computers are able to access the following [Office 365 URLs and IP address ranges](https://docs.microsoft.com/microsoftteams/office-365-urls-ip-address-ranges).</span></span> <span data-ttu-id="9f4ed-129">Возможно, потребуется добавить полные доменные имена в список разрешенных исходящих подключений в конфигурации брандмауэра или прокси-сервера \*: \*\* \*. API.Skype.com\*\*, **. Users.Storage.Live.com**и **Graph.Skype.com**.</span><span class="sxs-lookup"><span data-stu-id="9f4ed-129">This may require adding the FQDNs to the outbound allow list in your firewall or proxy infrastructure configuration: **\*.api.skype.com**, \***.users.storage.live.com**, and **graph.skype.com**.</span></span> <span data-ttu-id="9f4ed-130">Инструкции по открытию этих портов в брандмауэре можно найти в документации, поставляемой с ним.</span><span class="sxs-lookup"><span data-stu-id="9f4ed-130">For instructions on how to open these ports in your firewall, check the documentation that came with it.</span></span>
    
    <span data-ttu-id="9f4ed-131">Список всех нужных портов можно найти в разделе [URL-адреса и диапазоны IP-адресов Office 365](https://docs.microsoft.com/microsoftteams/office-365-urls-ip-address-ranges).</span><span class="sxs-lookup"><span data-stu-id="9f4ed-131">For a list of all ports you need to open, see [Office 365 URLs and IP address ranges](https://docs.microsoft.com/microsoftteams/office-365-urls-ip-address-ranges).</span></span>

9. <span data-ttu-id="9f4ed-132">Убедитесь в том, что администратор организации также выполнил следующие действия.</span><span class="sxs-lookup"><span data-stu-id="9f4ed-132">Make sure that the administrator in the organization has also followed these steps.</span></span>
    
10. <span data-ttu-id="9f4ed-133">**Подождите до 24 часов, чтобы**протестировать.</span><span class="sxs-lookup"><span data-stu-id="9f4ed-133">**WAIT UP TO 24 HOURS TO TEST**.</span></span> <span data-ttu-id="9f4ed-134">Каждый раз при изменении параметров внешней связи может потребоваться до 24 часов, чтобы изменения настроились между всеми центрами обработки данных.</span><span class="sxs-lookup"><span data-stu-id="9f4ed-134">Any time you change the external communications settings, it can take up to 24 hours for the changes to populate across all the data centers.</span></span>
    
<span data-ttu-id="9f4ed-135">![Skype](../images/58550720-2a68-42d1-a926-1884e6aeb55c.png) вы можете разрешить вашим пользователям искать и обмениваться мгновенными сообщениями со всеми пользователями Skype — бесплатным приложением для потребителей!</span><span class="sxs-lookup"><span data-stu-id="9f4ed-135">![Skype](../images/58550720-2a68-42d1-a926-1884e6aeb55c.png) You can allow your users to search for and IM with everyone who uses Skype, the free consumer app!</span></span> <span data-ttu-id="9f4ed-136">Дополнительные сведения можно найти в статье предоставление [пользователям Skype для бизнеса контактов Skype](let-skype-for-business-users-add-skype-contacts.md).</span><span class="sxs-lookup"><span data-stu-id="9f4ed-136">To learn more, see [Let Skype for Business users add Skype contacts](let-skype-for-business-users-add-skype-contacts.md).</span></span>
  
## <a name="test-and-troubleshoot"></a><span data-ttu-id="9f4ed-137">Проверка и устранение неполадок</span><span class="sxs-lookup"><span data-stu-id="9f4ed-137">Test and troubleshoot</span></span>
<span data-ttu-id="9f4ed-138"><a name="bk_preview"> </a></span><span class="sxs-lookup"><span data-stu-id="9f4ed-138"></span></span>

 <span data-ttu-id="9f4ed-139">**Наиболее распространенные вопросы, возникающие при настройке обмена данными между деловыми организациями, получают [URL-адреса и диапазоны IP-адресов для Office 365](https://docs.microsoft.com/microsoftteams/office-365-urls-ip-address-ranges) прямо сейчас.**</span><span class="sxs-lookup"><span data-stu-id="9f4ed-139">**The most common issue people encounter when setting up business-to-business communication is getting their [Office 365 URLs and IP address ranges](https://docs.microsoft.com/microsoftteams/office-365-urls-ip-address-ranges) right.**</span></span>
  
<span data-ttu-id="9f4ed-140">Для проверки настройки вам потребуется контакт в Skype для бизнеса, который не защищен брандмауэром компании.</span><span class="sxs-lookup"><span data-stu-id="9f4ed-140">To test your setup, you need a contact on Skype for Business who's not behind your company firewall.</span></span>
  
1. <span data-ttu-id="9f4ed-141">После изменения параметров внешней связи **Подождите до 24 часов перед**тем, как протестировать.</span><span class="sxs-lookup"><span data-stu-id="9f4ed-141">After you change your external communications settings, **WAIT UP TO 24 HOURS TO TEST**.</span></span>
    
2. <span data-ttu-id="9f4ed-142">В Skype для бизнеса выполните поиск контакта в Skype для бизнеса и отправьте запрос на чат.</span><span class="sxs-lookup"><span data-stu-id="9f4ed-142">In Skype for Business, search for your contact in Skype for Business, and send a request to chat.</span></span>
    
    <span data-ttu-id="9f4ed-143">Если появляется сообщение о том, что его не удалось послать из-за политики компании, необходимо проверить, какие URL-адреса [и диапазоны IP-адресов Office 365](https://docs.microsoft.com/microsoftteams/office-365-urls-ip-address-ranges).</span><span class="sxs-lookup"><span data-stu-id="9f4ed-143">If you get a message that it couldn't be sent due to company policy, you need to double-check your [Office 365 URLs and IP address ranges](https://docs.microsoft.com/microsoftteams/office-365-urls-ip-address-ranges).</span></span>
    
3. <span data-ttu-id="9f4ed-144">Попросите контакта Skype для бизнеса отправить вам запрос на чат.</span><span class="sxs-lookup"><span data-stu-id="9f4ed-144">Ask your Skype for Business contact to send you a request to chat.</span></span> <span data-ttu-id="9f4ed-145">Если вы не получили запрос, проблема заключается в параметрах брандмауэра (предполагая, что параметры брандмауэра уже подтверждены).</span><span class="sxs-lookup"><span data-stu-id="9f4ed-145">If you don't receive their request, the problem is your firewall settings (assuming they've already confirmed their firewall settings are correct).</span></span>
    
4. <span data-ttu-id="9f4ed-146">Кроме того, вы можете проверить, является ли проблема брандмауэром, чтобы перейти к расположению в сети Wi-Fi, не защищенному брандмауэром, например кафе, и использовать Skype для бизнеса для отправки запроса на ваш собеседник в чат.</span><span class="sxs-lookup"><span data-stu-id="9f4ed-146">Another way to test whether the problem is your firewall is to go to a wifi location not behind your firewall such as a coffee shop, and use Skype for Business to send a request to your contact to chat.</span></span> <span data-ttu-id="9f4ed-147">Если сообщение находится на рабочем этапе, но не на работе, вы знаете, что проблема связана с брандмауэром.</span><span class="sxs-lookup"><span data-stu-id="9f4ed-147">If the message goes through there, but not when you're at work, then you know the problem is your firewall.</span></span>
    
## <a name="how-to-find-others-and-be-found-when-connecting-with-another-business"></a><span data-ttu-id="9f4ed-148">Как найти других пользователей и найти их при подключении к другому бизнес-</span><span class="sxs-lookup"><span data-stu-id="9f4ed-148">How to find others, and be found, when connecting with another business</span></span>
<span data-ttu-id="9f4ed-149"><a name="bk_preview"> </a></span><span class="sxs-lookup"><span data-stu-id="9f4ed-149"></span></span>

<span data-ttu-id="9f4ed-150">После включения внешней связи с другими пользователями Skype для бизнеса пользователи смогут находить федеративных пользователей Skype для бизнеса, выполняя поиск по имени для входа в систему: например, Rob@contoso.com.</span><span class="sxs-lookup"><span data-stu-id="9f4ed-150">After you enable external communication with other Skype for Business users, your users can find federated Skype for Business users by searching for their sign-in name: for example, Rob@contoso.com.</span></span> <span data-ttu-id="9f4ed-151">Тогда они должны будут добавить пользователя в список контактов.</span><span class="sxs-lookup"><span data-stu-id="9f4ed-151">Then they will need to add the person to their list of contacts.</span></span>
  
![Чтобы найти пользователя в Федеративной компании, необходимо найти его адрес электронной почты (обычно это также имя для входа).](../images/20242f85-0636-463b-8df3-1e123784d7fa.png)
  
## <a name="tips-on-setting-up-communications-with-federated-businesses"></a><span data-ttu-id="9f4ed-153">Советы по настройке связи с федеративными организациями</span><span class="sxs-lookup"><span data-stu-id="9f4ed-153">Tips on setting up communications with federated businesses</span></span>
<span data-ttu-id="9f4ed-154"><a name="bk_preview"> </a></span><span class="sxs-lookup"><span data-stu-id="9f4ed-154"></span></span>

- <span data-ttu-id="9f4ed-155">Чтобы настроить федерацию между Skype для бизнеса 2015 и Skype для бизнеса Online, ознакомьтесь с этой статьей: [Настройка Федерации в Skype для бизнеса Online](https://technet.microsoft.com/en-us/library/jj205126.aspx).</span><span class="sxs-lookup"><span data-stu-id="9f4ed-155">To configure federation between Skype for Business 2015 and Skype for Business Online, see this  article: [Configure federation with Skype for Business Online](https://technet.microsoft.com/en-us/library/jj205126.aspx).</span></span>
    
- <span data-ttu-id="9f4ed-156">Чтобы настроить федерацию между Lync и Skype для бизнеса Online, ознакомьтесь с этой статьей: [Настройка поддержки федерации для клиента Lync Online](https://technet.microsoft.com/en-us/library/hh202193.aspx).</span><span class="sxs-lookup"><span data-stu-id="9f4ed-156">To configure federation between Lync and Skype for Business Online, see this  article: [Configuring Federation Support for a Lync Online Customer](https://technet.microsoft.com/en-us/library/hh202193.aspx).</span></span>
    
- <span data-ttu-id="9f4ed-157">Если два пользователя Skype для бизнеса в Office 365 взаимодействуют друг с другом в разных доменах, они могут использовать только функции Skype для бизнеса (например, видеобеседы или совместный доступ к рабочему столу), которые включены в обеих организациях.</span><span class="sxs-lookup"><span data-stu-id="9f4ed-157">When two Skype for Business users in Office 365 are communicating with each other on separate domains, they can only use Skype for Business features (for example, video conversations or desktop sharing) that are turned on in both organizations.</span></span>
    
- <span data-ttu-id="9f4ed-158">Если пользователь Skype для бизнеса в Организации размещается на месте или на удержании судебного разбирательства, любые текстовые беседы между этим пользователем и другими пользователями Skype для бизнеса или Skype будут сохранены в элементах почтового ящика с **возможностью восстановления** .</span><span class="sxs-lookup"><span data-stu-id="9f4ed-158">If a Skype for Business user in your organization is put on an In-Place or Litigation Hold, any IM conversations between that user and other Skype for Business or Skype users will be saved in **Recoverable Items** in their mailbox.</span></span> <span data-ttu-id="9f4ed-159">Эти беседы не сохраняются в папке " **Журнал бесед** " в почтовом ящике.</span><span class="sxs-lookup"><span data-stu-id="9f4ed-159">These conversations aren't saved in the **Conversations History** folder in their mailbox.</span></span>
    
## <a name="turn-off-external-communication-for-specific-individuals"></a><span data-ttu-id="9f4ed-160">Отключение внешней связи для определенных пользователей</span><span class="sxs-lookup"><span data-stu-id="9f4ed-160">Turn off external communication for specific individuals</span></span>
<span data-ttu-id="9f4ed-161"><a name="bk_preview"> </a></span><span class="sxs-lookup"><span data-stu-id="9f4ed-161"></span></span>

<span data-ttu-id="9f4ed-162">После включения внешней связи для всего бизнеса вы можете отключить его только для определенных пользователей.</span><span class="sxs-lookup"><span data-stu-id="9f4ed-162">After you enable external communication for your entire business, you can turn it off for only specific individuals.</span></span>
  
1. <span data-ttu-id="9f4ed-163">Войдите в систему с помощью учетной записи администратора Office 365.</span><span class="sxs-lookup"><span data-stu-id="9f4ed-163">Sign in with your Office 365 admin account.</span></span>
    
2. <span data-ttu-id="9f4ed-164">В центре администрирования перейдите в раздел**Активные пользователи** **пользователей** > .</span><span class="sxs-lookup"><span data-stu-id="9f4ed-164">In the admin center, go to **Users** > **Active users**.</span></span>
    
3. <span data-ttu-id="9f4ed-165">В списке пользователей выберите пользователя, а затем в разделе **Дополнительные параметры**выберите команду **изменить свойства Skype для бизнеса**.</span><span class="sxs-lookup"><span data-stu-id="9f4ed-165">In the list of users, choose the user, and then, under **More Settings**, click **Edit Skype for Business properties**.</span></span>
    
    ![Выберите Skype для бизнеса](../images/2b0f9a7b-3fee-4f4b-968a-68c429eeb395.png)
  
4. <span data-ttu-id="9f4ed-167">В **центре администрирования Skype для бизнеса**выберите элемент **внешняя связь**.</span><span class="sxs-lookup"><span data-stu-id="9f4ed-167">In the **Skype for Business admin center**, choose **External communications**.</span></span>
    
    <span data-ttu-id="9f4ed-168">На странице " **Параметры** " будут выделены все варианты.</span><span class="sxs-lookup"><span data-stu-id="9f4ed-168">On the **Options** page, all of the choices will be selected.</span></span> <span data-ttu-id="9f4ed-169">Снимите флажки для тех сообщений, которые вы хотите отключить.</span><span class="sxs-lookup"><span data-stu-id="9f4ed-169">Clear the communications you want to disable.</span></span> <span data-ttu-id="9f4ed-170">На приведенном ниже рисунке показано, что Жакоб сможет общаться с людьми из других доверенных компаний, но не с другими пользователями Skype.</span><span class="sxs-lookup"><span data-stu-id="9f4ed-170">The following image shows that Jakob will be able to communicate with people in other trusted businesses, but not with other Skype users.</span></span>
    
    ![Выберите Внешние контакты](../images/4e546321-a065-48ed-8ac7-1e112a780eab.png)
  
5. <span data-ttu-id="9f4ed-172">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="9f4ed-172">Choose **Save**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="9f4ed-173">Чтобы изменения вступили в силу, возможно, потребуется подождать не более 24 часов.</span><span class="sxs-lookup"><span data-stu-id="9f4ed-173">You may have to wait for up to 24 hours for your changes to take effect.</span></span> 
  


[!INCLUDE [LinkedIn Learning Info](../../common/office/linkedin-learning-info.md)]
   
   
## <a name="related-topics"></a><span data-ttu-id="9f4ed-174">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="9f4ed-174">Related topics</span></span>
<span data-ttu-id="9f4ed-175"><a name="bk_preview"> </a></span><span class="sxs-lookup"><span data-stu-id="9f4ed-175"></span></span>

[<span data-ttu-id="9f4ed-176">Настройка Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="9f4ed-176">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)
  
[<span data-ttu-id="9f4ed-177">Разрешение на добавление контактов Skype пользователям Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="9f4ed-177">Let Skype for Business users add Skype contacts</span></span>](let-skype-for-business-users-add-skype-contacts.md)
  
  
 
