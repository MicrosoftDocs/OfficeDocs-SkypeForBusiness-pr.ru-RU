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
ms.audience: Admin
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
description: 'Узнайте, как настроить Скайп для бизнеса дать возможность пользователям обращаться к пользователей в другой организации или разрешить за пределами контактов к ним. '
ms.openlocfilehash: 352973816e07ce60cff650f43ac6fced7f81e3b1
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "32239220"
---
# <a name="allow-users-to-contact-external-skype-for-business-users"></a><span data-ttu-id="1e3de-103">Разрешите пользователям связываться с внешними пользователями Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="1e3de-103">Allow users to contact external Skype for Business users</span></span>

> [!NOTE]
> <span data-ttu-id="1e3de-104">Скайп для федерации Business недоступен для Office 365, которой 21Vianet и организациями Office 365 Германия.</span><span class="sxs-lookup"><span data-stu-id="1e3de-104">Skype for Business federation isn't available to Office 365 operated by 21Vianet and Office 365 Germany organizations.</span></span> 
  
<span data-ttu-id="1e3de-105">Действия, описанные в этом приведены в статье случаи использования:</span><span class="sxs-lookup"><span data-stu-id="1e3de-105">Use the steps in this article when:</span></span>
  
- <span data-ttu-id="1e3de-106">У вас есть пользователи в разных доменах в бизнесе.</span><span class="sxs-lookup"><span data-stu-id="1e3de-106">You have users on different domains in your business.</span></span> <span data-ttu-id="1e3de-107">Например Rob@ContosoEast.com и Ann@ContosoWest.com.</span><span class="sxs-lookup"><span data-stu-id="1e3de-107">For example, Rob@ContosoEast.com and Ann@ContosoWest.com.</span></span>
    
- <span data-ttu-id="1e3de-108">Требуется людей в организации использование Скайп для бизнеса для контактных лиц в конкретных предприятия за пределами вашей организации.</span><span class="sxs-lookup"><span data-stu-id="1e3de-108">You want the people in your organization to use Skype for Business to contact people in specific businesses outside of your organization.</span></span>
    
- <span data-ttu-id="1e3de-109">Предполагается, что у других пользователей в мире, который использует Скайп для бизнеса должны иметь возможность поиска и связи с вами с помощью свой адрес электронной почты.</span><span class="sxs-lookup"><span data-stu-id="1e3de-109">You want anyone else in the world who uses Skype for Business to be able to find and contact you, using your email address.</span></span> <span data-ttu-id="1e3de-110">Если вы и они используют Скайп по умолчанию для параметров Business, этот вариант возможен автоматически.</span><span class="sxs-lookup"><span data-stu-id="1e3de-110">If you and they use the default Skype for Business settings, this will work automatically.</span></span> <span data-ttu-id="1e3de-111">В противном случае необходимости убедитесь, что их конфигурации не блокирует вашего домена.</span><span class="sxs-lookup"><span data-stu-id="1e3de-111">If they don't, then they need to make sure their configuration isn't blocking your domain.</span></span>
    
## <a name="enable-business-to-business-communications-for-your-users"></a><span data-ttu-id="1e3de-112">Включить бизнес бизнес связь для пользователей</span><span class="sxs-lookup"><span data-stu-id="1e3de-112">Enable business-to-business communications for your users</span></span>
<span data-ttu-id="1e3de-113"><a name="bk_preview"> </a></span><span class="sxs-lookup"><span data-stu-id="1e3de-113"></span></span>

<span data-ttu-id="1e3de-114">В обеих организациях для этого необходимо иметь [разрешения администратора](https://support.office.com/en-us/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) в Office 365.</span><span class="sxs-lookup"><span data-stu-id="1e3de-114">You must have [admin permissions](https://support.office.com/en-us/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) in Office 365 in both organizations to do this.</span></span>

<span data-ttu-id="1e3de-115">![команды логотип 30x30.png](../images/teams-logo-30x30.png) **с помощью центра администрирования группы**</span><span class="sxs-lookup"><span data-stu-id="1e3de-115">![teams-logo-30x30.png](../images/teams-logo-30x30.png) **Using the Teams admin center**</span></span>
  
1. <span data-ttu-id="1e3de-116">Выполните вход с учетной записью администратора Office 365.</span><span class="sxs-lookup"><span data-stu-id="1e3de-116">Sign in with your Office 365 admin account.</span></span> 
    
2. <span data-ttu-id="1e3de-117">В центре администрирования Office 365 перейдите на **Центры администрирования** > **группами**.</span><span class="sxs-lookup"><span data-stu-id="1e3de-117">In the Office 365 admin center, go to **Admin Centers** > **Teams**.</span></span>
    
    ![Выберите команды администратор.](../images/MS-Teams-Admin.png)
  
3. <span data-ttu-id="1e3de-119">**Центр группы**выберите **Скайп** > **Портала прежних версий** 
 ![выберите портала SfB прежних версий.](../images/SFBlegacy-size65.png)</span><span class="sxs-lookup"><span data-stu-id="1e3de-119">In the **Teams center**, choose **Skype** > **Legacy Portal** 
![Choose the SfB Legacy Portal.](../images/SFBlegacy-size65.png)</span></span>
 
4. <span data-ttu-id="1e3de-120">В **Скайп по центру администрирования бизнеса** , выберите **организации** > **внешних коммуникаций**.</span><span class="sxs-lookup"><span data-stu-id="1e3de-120">In the **Skype for Business admin center** , choose **Organization** > **External communications**.</span></span>
5. <span data-ttu-id="1e3de-121">Чтобы настроить связь с определенным бизнес- или с пользователями в другом домене, в раскрывающемся списке выберите **на только для разрешенных доменов**.</span><span class="sxs-lookup"><span data-stu-id="1e3de-121">To set up communication with a specific business or with users in another domain, in the drop-down box, choose **On only for allowed domains**.</span></span>
    
    <span data-ttu-id="1e3de-122">ИЛИ, если необходимо включить связь с все остальные в мире, имеющий открыть Скайп для бизнес-политик, выберите **на за исключением заблокированных доменов**.</span><span class="sxs-lookup"><span data-stu-id="1e3de-122">OR, if you want to enable communication with everyone else in the world who has open Skype for Business policies, choose **On except for blocked domains**.</span></span> <span data-ttu-id="1e3de-123">Это значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="1e3de-123">This is the default setting.</span></span>
    
6. <span data-ttu-id="1e3de-124">В списке **заблокированных или разрешенных доменов**, выберите **+** и добавьте имя домена, чтобы разрешить.</span><span class="sxs-lookup"><span data-stu-id="1e3de-124">Under **Blocked or allowed domains**, choose **+** and add the name of the domain you want to allow.</span></span>
    
7. <span data-ttu-id="1e3de-125">Убедитесь в том, что администратор другой организации не эти же действия в их **Скайп по центру администрирования бизнес**.</span><span class="sxs-lookup"><span data-stu-id="1e3de-125">Make sure the admin in the other organization does these same steps in their **Skype for Business admin center**.</span></span> <span data-ttu-id="1e3de-126">К примеру в список **разрешенных доменов** их администрирования необходимо войти в домен для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="1e3de-126">For example, in their **allowed domains** list, their admin needs to enter the domain for your business.</span></span>
    
8. <span data-ttu-id="1e3de-127">Если вы используете брандмауэр Windows в режиме, Скайп для бизнеса автоматически открывает необходимые порты.</span><span class="sxs-lookup"><span data-stu-id="1e3de-127">If you're using Windows Firewall, Skype for Business opens the required ports automatically.</span></span>
    
    <span data-ttu-id="1e3de-128">Если ваша организация использует решения различных брандмауэра для ограничения компьютеры в сети с подключением к Интернету, убедитесь, что на клиентских компьютерах, могут получить доступ к следующие [URL-адреса Office 365 и диапазоны IP-адресов](https://docs.microsoft.com/microsoftteams/office-365-urls-ip-address-ranges).</span><span class="sxs-lookup"><span data-stu-id="1e3de-128">If your organization is using a different firewall solution to restrict computers on your network from connecting to the Internet, ensure your client computers are able to access the following [Office 365 URLs and IP address ranges](https://docs.microsoft.com/microsoftteams/office-365-urls-ip-address-ranges).</span></span> <span data-ttu-id="1e3de-129">Возможно, потребуется добавить полные доменные имена для исходящих белого списка в брандмауэр или прокси-сервера конфигурации инфраструктуры: \*\* \*. api.skype.com\*\*, \* **. users.storage.live.com**и **graph.skype.com**.</span><span class="sxs-lookup"><span data-stu-id="1e3de-129">This may require adding the FQDNs to the outbound allow list in your firewall or proxy infrastructure configuration: **\*.api.skype.com**, \***.users.storage.live.com**, and **graph.skype.com**.</span></span> <span data-ttu-id="1e3de-130">За инструкциями о том, как открыть эти порты в брандмауэре обратитесь к документации, поставляемой с ним.</span><span class="sxs-lookup"><span data-stu-id="1e3de-130">For instructions on how to open these ports in your firewall, check the documentation that came with it.</span></span>
    
    <span data-ttu-id="1e3de-131">Список всех портов, которые должны быть открыты в разделе [URL-адреса Office 365 и диапазоны IP-адресов](https://docs.microsoft.com/microsoftteams/office-365-urls-ip-address-ranges).</span><span class="sxs-lookup"><span data-stu-id="1e3de-131">For a list of all ports you need to open, see [Office 365 URLs and IP address ranges](https://docs.microsoft.com/microsoftteams/office-365-urls-ip-address-ranges).</span></span>

9. <span data-ttu-id="1e3de-132">Убедитесь в том, что администратор организации также выполнил следующие действия.</span><span class="sxs-lookup"><span data-stu-id="1e3de-132">Make sure that the administrator in the organization has also followed these steps.</span></span>
    
10. <span data-ttu-id="1e3de-133">**ПОДОЖДИТЕ до 24 часов для тестирования**.</span><span class="sxs-lookup"><span data-stu-id="1e3de-133">**WAIT UP TO 24 HOURS TO TEST**.</span></span> <span data-ttu-id="1e3de-134">При изменении параметров внешних коммуникаций, может потребоваться до 24 часов для изменения для заполнения в центрах обработки данных.</span><span class="sxs-lookup"><span data-stu-id="1e3de-134">Any time you change the external communications settings, it can take up to 24 hours for the changes to populate across all the data centers.</span></span>
    
<span data-ttu-id="1e3de-135">![Скайп](../images/58550720-2a68-42d1-a926-1884e6aeb55c.png) можно разрешить пользователям искать и обмена мгновенными Сообщениями со всех, кто использует Скайп, приложение бесплатное потребителей!</span><span class="sxs-lookup"><span data-stu-id="1e3de-135">![Skype](../images/58550720-2a68-42d1-a926-1884e6aeb55c.png) You can allow your users to search for and IM with everyone who uses Skype, the free consumer app!</span></span> <span data-ttu-id="1e3de-136">Для получения дополнительных сведений см [Let Скайп для бизнес-пользователям добавлять контакты Скайп](let-skype-for-business-users-add-skype-contacts.md).</span><span class="sxs-lookup"><span data-stu-id="1e3de-136">To learn more, see [Let Skype for Business users add Skype contacts](let-skype-for-business-users-add-skype-contacts.md).</span></span>
  
## <a name="test-and-troubleshoot"></a><span data-ttu-id="1e3de-137">Тестирование и устранение неполадок</span><span class="sxs-lookup"><span data-stu-id="1e3de-137">Test and troubleshoot</span></span>
<span data-ttu-id="1e3de-138"><a name="bk_preview"> </a></span><span class="sxs-lookup"><span data-stu-id="1e3de-138"></span></span>

 <span data-ttu-id="1e3de-139">**Наиболее распространенные проблемы, которые людей возникнуть при настройке бизнес делового общения правильного их [Office 365 URL-адреса и диапазоны IP-адресов](https://docs.microsoft.com/microsoftteams/office-365-urls-ip-address-ranges) .**</span><span class="sxs-lookup"><span data-stu-id="1e3de-139">**The most common issue people encounter when setting up business-to-business communication is getting their [Office 365 URLs and IP address ranges](https://docs.microsoft.com/microsoftteams/office-365-urls-ip-address-ranges) right.**</span></span>
  
<span data-ttu-id="1e3de-140">Чтобы проверить настройки, необходимо контакта на Скайп для бизнеса, который не является за брандмауэром вашей компании.</span><span class="sxs-lookup"><span data-stu-id="1e3de-140">To test your setup, you need a contact on Skype for Business who's not behind your company firewall.</span></span>
  
1. <span data-ttu-id="1e3de-141">После можно изменить параметры внешних коммуникаций, **TEST кому ОЖИДАТЬ до 24 часов**.</span><span class="sxs-lookup"><span data-stu-id="1e3de-141">After you change your external communications settings, **WAIT UP TO 24 HOURS TO TEST**.</span></span>
    
2. <span data-ttu-id="1e3de-142">В Скайп для бизнеса поиск контакта в Скайп для бизнеса и отправить запрос в чате.</span><span class="sxs-lookup"><span data-stu-id="1e3de-142">In Skype for Business, search for your contact in Skype for Business, and send a request to chat.</span></span>
    
    <span data-ttu-id="1e3de-143">Если вы получаете сообщение, оно не доставлено из-за политики компании, необходимо еще раз проверьте к [Office 365 URL-адреса и диапазоны IP-адресов](https://docs.microsoft.com/microsoftteams/office-365-urls-ip-address-ranges).</span><span class="sxs-lookup"><span data-stu-id="1e3de-143">If you get a message that it couldn't be sent due to company policy, you need to double-check your [Office 365 URLs and IP address ranges](https://docs.microsoft.com/microsoftteams/office-365-urls-ip-address-ranges).</span></span>
    
3. <span data-ttu-id="1e3de-144">Попросите Скайп для бизнес-контакта отправляет запрос на беседу.</span><span class="sxs-lookup"><span data-stu-id="1e3de-144">Ask your Skype for Business contact to send you a request to chat.</span></span> <span data-ttu-id="1e3de-145">Если вы не получите свой запрос, проблема заключается в настройках брандмауэра (если они уже подтверждения правильности их параметры брандмауэра).</span><span class="sxs-lookup"><span data-stu-id="1e3de-145">If you don't receive their request, the problem is your firewall settings (assuming they've already confirmed their firewall settings are correct).</span></span>
    
4. <span data-ttu-id="1e3de-146">Другой способ проверки, является ли проблема брандмауэра — это расположение wifi не за брандмауэром, таких как кафе и использовать Скайп для бизнеса отправить запрос контакту чата.</span><span class="sxs-lookup"><span data-stu-id="1e3de-146">Another way to test whether the problem is your firewall is to go to a wifi location not behind your firewall such as a coffee shop, and use Skype for Business to send a request to your contact to chat.</span></span> <span data-ttu-id="1e3de-147">Если сообщение проходит через существует, но не в том случае, когда вы находитесь на работе, это значит, проблема является брандмауэра.</span><span class="sxs-lookup"><span data-stu-id="1e3de-147">If the message goes through there, but not when you're at work, then you know the problem is your firewall.</span></span>
    
## <a name="how-to-find-others-and-be-found-when-connecting-with-another-business"></a><span data-ttu-id="1e3de-148">Как найти других пользователей и найти, при подключении через другой компании</span><span class="sxs-lookup"><span data-stu-id="1e3de-148">How to find others, and be found, when connecting with another business</span></span>
<span data-ttu-id="1e3de-149"><a name="bk_preview"> </a></span><span class="sxs-lookup"><span data-stu-id="1e3de-149"></span></span>

<span data-ttu-id="1e3de-150">После включения внешнего обмена данными с другими Скайп для бизнес-пользователи пользователям найти федеративных Скайп для бизнес-пользователей по ключевым словам их учетное имя: например, Rob@contoso.com.</span><span class="sxs-lookup"><span data-stu-id="1e3de-150">After you enable external communication with other Skype for Business users, your users can find federated Skype for Business users by searching for their sign-in name: for example, Rob@contoso.com.</span></span> <span data-ttu-id="1e3de-151">Затем необходимо добавить пользователя в свой список контактов.</span><span class="sxs-lookup"><span data-stu-id="1e3de-151">Then they will need to add the person to their list of contacts.</span></span>
  
![Для поиска пользователя в федеративных бизнеса, необходимо найти их адреса электронной почты (обычно это также их учетное имя).](../images/20242f85-0636-463b-8df3-1e123784d7fa.png)
  
## <a name="tips-on-setting-up-communications-with-federated-businesses"></a><span data-ttu-id="1e3de-153">Советы по настройке связь с федеративными бизнеса</span><span class="sxs-lookup"><span data-stu-id="1e3de-153">Tips on setting up communications with federated businesses</span></span>
<span data-ttu-id="1e3de-154"><a name="bk_preview"> </a></span><span class="sxs-lookup"><span data-stu-id="1e3de-154"></span></span>

- <span data-ttu-id="1e3de-155">Чтобы настроить федерацию между Скайп для бизнеса 2015 и Скайп для бизнеса в Интернет, обратитесь к разделу в этой статье: [Настройка федерации с Скайп для бизнеса в Интернет](https://technet.microsoft.com/en-us/library/jj205126.aspx).</span><span class="sxs-lookup"><span data-stu-id="1e3de-155">To configure federation between Skype for Business 2015 and Skype for Business Online, see this  article: [Configure federation with Skype for Business Online](https://technet.microsoft.com/en-us/library/jj205126.aspx).</span></span>
    
- <span data-ttu-id="1e3de-156">Чтобы настроить федерации между Lync и Скайп для бизнеса в Интернет, обратитесь к разделу в этой статье: [Настройка поддержки федерации для клиента Lync Online](https://technet.microsoft.com/en-us/library/hh202193.aspx).</span><span class="sxs-lookup"><span data-stu-id="1e3de-156">To configure federation between Lync and Skype for Business Online, see this  article: [Configuring Federation Support for a Lync Online Customer](https://technet.microsoft.com/en-us/library/hh202193.aspx).</span></span>
    
- <span data-ttu-id="1e3de-157">Когда два Скайп для бизнес-пользователей в Office 365 обмениваются данными друг с другом в разных доменах, их можно использовать Скайп только для функции бизнес-(например, видеобеседы или рабочему столу), которые включены в обеих организациях.</span><span class="sxs-lookup"><span data-stu-id="1e3de-157">When two Skype for Business users in Office 365 are communicating with each other on separate domains, they can only use Skype for Business features (for example, video conversations or desktop sharing) that are turned on in both organizations.</span></span>
    
- <span data-ttu-id="1e3de-158">Если на месте или хранение для судебного разбирательства находится в состоянии Скайп для корпоративных пользователей в вашей организации, любой мгновенные сообщения от этого пользователя и другие Скайп для бизнеса или Скайп пользователей будут сохраняться **Восстанавливаемых элементов** в почтовом ящике.</span><span class="sxs-lookup"><span data-stu-id="1e3de-158">If a Skype for Business user in your organization is put on an In-Place or Litigation Hold, any IM conversations between that user and other Skype for Business or Skype users will be saved in **Recoverable Items** in their mailbox.</span></span> <span data-ttu-id="1e3de-159">Эти беседы не сохраняются в папке **Журнала бесед** в почтовом ящике.</span><span class="sxs-lookup"><span data-stu-id="1e3de-159">These conversations aren't saved in the **Conversations History** folder in their mailbox.</span></span>
    
## <a name="turn-off-external-communication-for-specific-individuals"></a><span data-ttu-id="1e3de-160">Отключение внешнего обмена данными для определенных пользователей</span><span class="sxs-lookup"><span data-stu-id="1e3de-160">Turn off external communication for specific individuals</span></span>
<span data-ttu-id="1e3de-161"><a name="bk_preview"> </a></span><span class="sxs-lookup"><span data-stu-id="1e3de-161"></span></span>

<span data-ttu-id="1e3de-162">После включения внешнего обмена данными для всего предприятия, можно отключить его только определенным лицам.</span><span class="sxs-lookup"><span data-stu-id="1e3de-162">After you enable external communication for your entire business, you can turn it off for only specific individuals.</span></span>
  
1. <span data-ttu-id="1e3de-163">Выполните вход с учетной записью администратора Office 365.</span><span class="sxs-lookup"><span data-stu-id="1e3de-163">Sign in with your Office 365 admin account.</span></span>
    
2. <span data-ttu-id="1e3de-164">В центре администрирования Office 365 перейдите к **пользователям** > **Активные пользователи**.</span><span class="sxs-lookup"><span data-stu-id="1e3de-164">In the Office 365 admin center, go to **Users** > **Active users**.</span></span>
    
3. <span data-ttu-id="1e3de-165">В список пользователей выберите пользователя и в разделе **Дополнительные параметры**, нажмите кнопку **Изменить Скайп для свойства Business**.</span><span class="sxs-lookup"><span data-stu-id="1e3de-165">In the list of users, choose the user, and then, under **More Settings**, click **Edit Skype for Business properties**.</span></span>
    
    ![Выберите Скайп для бизнеса](../images/2b0f9a7b-3fee-4f4b-968a-68c429eeb395.png)
  
4. <span data-ttu-id="1e3de-167">В **Скайп по центру администрирования бизнеса**выберите **внешних коммуникаций**.</span><span class="sxs-lookup"><span data-stu-id="1e3de-167">In the **Skype for Business admin center**, choose **External communications**.</span></span>
    
    <span data-ttu-id="1e3de-168">На странице " **Параметры** " будут выбраны все варианты.</span><span class="sxs-lookup"><span data-stu-id="1e3de-168">On the **Options** page, all of the choices will be selected.</span></span> <span data-ttu-id="1e3de-169">Снимите флажок коммуникаций, которые необходимо отключить.</span><span class="sxs-lookup"><span data-stu-id="1e3de-169">Clear the communications you want to disable.</span></span> <span data-ttu-id="1e3de-170">На следующем рисунке показана, что Джейкоба будет иметь возможность обмениваться данными с пользователями в других надежных бизнеса, но не с другими пользователями Скайп.</span><span class="sxs-lookup"><span data-stu-id="1e3de-170">The following image shows that Jakob will be able to communicate with people in other trusted businesses, but not with other Skype users.</span></span>
    
    ![Выберите внешние контакты](../images/4e546321-a065-48ed-8ac7-1e112a780eab.png)
  
5. <span data-ttu-id="1e3de-172">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="1e3de-172">Choose **Save**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="1e3de-173">Может потребоваться ожидать в течение 24 часов, чтобы изменения вступили в силу.</span><span class="sxs-lookup"><span data-stu-id="1e3de-173">You may have to wait for up to 24 hours for your changes to take effect.</span></span> 
  


[!INCLUDE [LinkedIn Learning Info](../../common/office/linkedin-learning-info.md)]
   
   
## <a name="related-topics"></a><span data-ttu-id="1e3de-174">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="1e3de-174">Related topics</span></span>
<span data-ttu-id="1e3de-175"><a name="bk_preview"> </a></span><span class="sxs-lookup"><span data-stu-id="1e3de-175"></span></span>

[<span data-ttu-id="1e3de-176">Настройка Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="1e3de-176">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)
  
[<span data-ttu-id="1e3de-177">Разрешение на добавление контактов Skype пользователям Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="1e3de-177">Let Skype for Business users add Skype contacts</span></span>](let-skype-for-business-users-add-skype-contacts.md)
  
  
 
