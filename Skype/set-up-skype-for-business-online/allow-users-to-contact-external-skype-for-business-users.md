---
title: "Разрешить пользователям контактов внешних Скайп для бизнес-пользователи"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 01/22/2018
ms.topic: article
ms.assetid: b414873a-0059-4cd5-aea1-e5d0857dbc94
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
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
description: "Узнайте, как настроить Скайп для бизнеса дать возможность пользователям обращаться к пользователей в другой организации или разрешить за пределами контактов к ним. "
ms.openlocfilehash: f1dd146a507a1cf6a70b4e30c7da0f2c18d722e7
ms.sourcegitcommit: 94e32f776364b0aaefe2d2d72062ec1c249eaef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2018
---
# <a name="allow-users-to-contact-external-skype-for-business-users"></a><span data-ttu-id="a020f-103">Разрешить пользователям контактов внешних Скайп для бизнес-пользователи</span><span class="sxs-lookup"><span data-stu-id="a020f-103">Allow users to contact external Skype for Business users</span></span>

> [!NOTE]
> <span data-ttu-id="a020f-104">Скайп для федерации Business недоступен для Office 365, которой 21Vianet и организациями Office 365 Германия.</span><span class="sxs-lookup"><span data-stu-id="a020f-104">Skype for Business federation isn't available to Office 365 operated by 21Vianet and Office 365 Germany organizations.</span></span> 
  
<span data-ttu-id="a020f-105">Действия, описанные в этом приведены в статье случаи использования:</span><span class="sxs-lookup"><span data-stu-id="a020f-105">Use the steps in this article when:</span></span>
  
- <span data-ttu-id="a020f-106">У вас есть пользователи в разных доменах в бизнесе.</span><span class="sxs-lookup"><span data-stu-id="a020f-106">You have users on different domains in your business.</span></span> <span data-ttu-id="a020f-107">Например Rob@ContosoEast.com и Ann@ContosoWest.com.</span><span class="sxs-lookup"><span data-stu-id="a020f-107">For example, Rob@ContosoEast.com and Ann@ContosoWest.com.</span></span>
    
- <span data-ttu-id="a020f-108">Требуется людей в организации использование Скайп для бизнеса для контактных лиц в конкретных предприятия за пределами вашей организации.</span><span class="sxs-lookup"><span data-stu-id="a020f-108">You want the people in your organization to use Skype for Business to contact people in specific businesses outside of your organization.</span></span>
    
<span data-ttu-id="a020f-109">-Требуется кому-либо в мире, который использует Скайп для бизнеса должны иметь возможность поиска и связи с вами с помощью свой адрес электронной почты.</span><span class="sxs-lookup"><span data-stu-id="a020f-109">-You want anyone else in the world who uses Skype for Business to be able to find and contact you, using your email address.</span></span> <span data-ttu-id="a020f-110">Если вы и они используют Скайп по умолчанию для параметров Business, этот вариант возможен автоматически.</span><span class="sxs-lookup"><span data-stu-id="a020f-110">If you and they use the default Skype for Business settings, this will work automatically.</span></span> <span data-ttu-id="a020f-111">В противном случае необходимости убедитесь, что их конфигурации не блокирует вашего домена.</span><span class="sxs-lookup"><span data-stu-id="a020f-111">If they don't, then they need to make sure their configuration isn't blocking your domain.</span></span>
    
## <a name="enable-business-to-business-communications-for-your-users"></a><span data-ttu-id="a020f-112">Включить бизнес бизнес связь для пользователей</span><span class="sxs-lookup"><span data-stu-id="a020f-112">Enable business-to-business communications for your users</span></span>
<span data-ttu-id="a020f-113"><a name="bk_preview"> </a></span><span class="sxs-lookup"><span data-stu-id="a020f-113"></span></span>

<span data-ttu-id="a020f-114">Для этого необходимы [Роли администраторов в Office 365](https://support.office.com/en-us/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) в Office 365.</span><span class="sxs-lookup"><span data-stu-id="a020f-114">You must have [admin permissions](https://support.office.com/en-us/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) in Office 365 to do this.</span></span>
  
1. <span data-ttu-id="a020f-115">Выполните вход с учетной записью администратора Office 365.</span><span class="sxs-lookup"><span data-stu-id="a020f-115">Sign in with your Office 365 admin account.</span></span> 
    
2. <span data-ttu-id="a020f-116">В Центр администрирования Office 365 последовательно выберите пункты **Центры администрирования** > **Skype для бизнеса**.</span><span class="sxs-lookup"><span data-stu-id="a020f-116">In the Office 365 admin center, go to **Admin Centers** > **Skype for Business**.</span></span>
    
    ![Choose the Skype for Business admin center.](../images/376a7a45-e6e3-4716-be09-d2f294d885a2.png)
  
3. <span data-ttu-id="a020f-118">В **Центр администрирования Skype для бизнеса**выберите пункты **оОрганизация** > **Ввнешняяие связьи**.</span><span class="sxs-lookup"><span data-stu-id="a020f-118">In the **Skype for Business admin center**, choose **Organization** > **External communications**.</span></span>
    
4. <span data-ttu-id="a020f-119">Чтобы настроить связь с определенным бизнес- или с пользователями в другом домене, в раскрывающемся списке выберите **на только для разрешенных доменов**.</span><span class="sxs-lookup"><span data-stu-id="a020f-119">To set up communication with a specific business or with users in another domain, in the drop-down box, choose **On only for allowed domains**.</span></span>
    
    <span data-ttu-id="a020f-120">ИЛИ, если необходимо включить связь с все остальные в мире, имеющий открыть Скайп для бизнес-политик, выберите **на за исключением заблокированных доменов**.</span><span class="sxs-lookup"><span data-stu-id="a020f-120">OR, if you want to enable communication with everyone else in the world who has open Skype for Business policies, choose **On except for blocked domains**.</span></span> <span data-ttu-id="a020f-121">Это значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="a020f-121">This is the default setting.</span></span>
    
5. <span data-ttu-id="a020f-122">В списке **заблокированных или разрешенных доменов**, выберите **+** и добавьте имя домена, чтобы разрешить.</span><span class="sxs-lookup"><span data-stu-id="a020f-122">Under **Blocked or allowed domains**, choose **+** and add the name of the domain you want to allow.</span></span>
    
6. <span data-ttu-id="a020f-123">Убедитесь в том, что администратор другой организации не эти же действия в их **Скайп по центру администрирования бизнес**.</span><span class="sxs-lookup"><span data-stu-id="a020f-123">Make sure the admin in the other organization does these same steps in their **Skype for Business admin center**.</span></span> <span data-ttu-id="a020f-124">К примеру в список **разрешенных доменов** их администрирования необходимо войти в домен для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="a020f-124">For example, in their **allowed domains** list, their admin needs to enter the domain for your business.</span></span>
    
7. <span data-ttu-id="a020f-125">При использовании брандмауэра Windows Skype для бизнеса откроет нужные порты автоматически.</span><span class="sxs-lookup"><span data-stu-id="a020f-125">If you're using Windows Firewall, Skype for Business opens the required ports automatically.</span></span>
    
    <span data-ttu-id="a020f-126">Если ваша организация использует решения различных брандмауэра для ограничения компьютеры в сети с подключением к Интернету, убедитесь, что на клиентских компьютерах, могут получить доступ к следующие [URL-адреса Office 365 и диапазоны IP-адресов](https://docs.microsoft.com/en-us/microsoftteams/office-365-urls-ip-address-ranges).</span><span class="sxs-lookup"><span data-stu-id="a020f-126">If your organization is using a different firewall solution to restrict computers on your network from connecting to the Internet, ensure your client computers are able to access the following [Office 365 URLs and IP address ranges](https://docs.microsoft.com/en-us/microsoftteams/office-365-urls-ip-address-ranges).</span></span> <span data-ttu-id="a020f-127">Возможно, потребуется добавить полные доменные имена для исходящих белого списка в брандмауэр или прокси-сервера конфигурации инфраструктуры: ** \*. api.skype.com**, \* **. users.storage.live.com**и **graph.skype.com**. За инструкциями о том, как открыть эти порты в брандмауэре обратитесь к документации, поставляемой с ним.</span><span class="sxs-lookup"><span data-stu-id="a020f-127">This may require adding the FQDNs to the outbound allow list in your firewall or proxy infrastructure configuration: **\*.api.skype.com**, \***.users.storage.live.com**, and **graph.skype.com**. For instructions on how to open these ports in your firewall, check the documentation that came with it.</span></span>
    
    <span data-ttu-id="a020f-128">Список всех портов, которые должны быть открыты в разделе [URL-адреса Office 365 и диапазоны IP-адресов](https://docs.microsoft.com/en-us/microsoftteams/office-365-urls-ip-address-ranges).</span><span class="sxs-lookup"><span data-stu-id="a020f-128">For a list of all ports you need to open, see [Office 365 URLs and IP address ranges](https://docs.microsoft.com/en-us/microsoftteams/office-365-urls-ip-address-ranges).</span></span>
    
8. <span data-ttu-id="a020f-p106">**ПЕРЕД ПРОВЕРКОЙ ПОДОЖДИТЕ 24 ЧАСА**. После изменения внешних параметров связи может потребоваться до 24 часов для их распространения по всем центрам обработки данных.</span><span class="sxs-lookup"><span data-stu-id="a020f-p106">**WAIT UP TO 24 HOURS TO TEST**. Any time you change the external communications settings, it can take up to 24 hours for the changes to populate across all the data centers.</span></span>
    
<span data-ttu-id="a020f-131">![Скайп](../images/58550720-2a68-42d1-a926-1884e6aeb55c.png) можно разрешить пользователям искать и обмена мгновенными Сообщениями со всех, кто использует Скайп, приложение бесплатное потребителей!</span><span class="sxs-lookup"><span data-stu-id="a020f-131">![Skype](../images/58550720-2a68-42d1-a926-1884e6aeb55c.png) You can allow your users to search for and IM with everyone who uses Skype, the free consumer app!</span></span> <span data-ttu-id="a020f-132">Для получения дополнительных сведений см [Let Скайп для бизнес-пользователям добавлять контакты Скайп](let-skype-for-business-users-add-skype-contacts.md).</span><span class="sxs-lookup"><span data-stu-id="a020f-132">To learn more, see [Let Skype for Business users add Skype contacts](let-skype-for-business-users-add-skype-contacts.md).</span></span>
  
## <a name="test-and-troubleshoot"></a><span data-ttu-id="a020f-133">Проверка и устранение проблем</span><span class="sxs-lookup"><span data-stu-id="a020f-133">Test and troubleshoot</span></span>
<span data-ttu-id="a020f-134"><a name="bk_preview"> </a></span><span class="sxs-lookup"><span data-stu-id="a020f-134"></span></span>

 <span data-ttu-id="a020f-135">**Наиболее распространенные проблемы, которые людей возникнуть при настройке бизнес делового общения правильного их [Office 365 URL-адреса и диапазоны IP-адресов](https://docs.microsoft.com/en-us/microsoftteams/office-365-urls-ip-address-ranges) .**</span><span class="sxs-lookup"><span data-stu-id="a020f-135">**The most common issue people encounter when setting up business-to-business communication is getting their [Office 365 URLs and IP address ranges](https://docs.microsoft.com/en-us/microsoftteams/office-365-urls-ip-address-ranges) right.**</span></span>
  
<span data-ttu-id="a020f-136">Чтобы проверить настройки, необходимо контакта на Скайп для бизнеса, который не является за брандмауэром вашей компании.</span><span class="sxs-lookup"><span data-stu-id="a020f-136">To test your setup, you need a contact on Skype for Business who's not behind your company firewall.</span></span>
  
1. <span data-ttu-id="a020f-137">После изменения настроек внешней связи **подождите до 24 часов перед тем, как проверять их**.</span><span class="sxs-lookup"><span data-stu-id="a020f-137">After you change your external communications settings, **WAIT UP TO 24 HOURS TO TEST**.</span></span>
    
2. <span data-ttu-id="a020f-138">В Скайп для бизнеса поиск контакта в Скайп для бизнеса и отправить запрос в чате.</span><span class="sxs-lookup"><span data-stu-id="a020f-138">In Skype for Business, search for your contact in Skype for Business, and send a request to chat.</span></span>
    
    <span data-ttu-id="a020f-139">Если вы получаете сообщение, оно не доставлено из-за политики компании, необходимо еще раз проверьте к [Office 365 URL-адреса и диапазоны IP-адресов](https://docs.microsoft.com/en-us/microsoftteams/office-365-urls-ip-address-ranges).</span><span class="sxs-lookup"><span data-stu-id="a020f-139">If you get a message that it couldn't be sent due to company policy, you need to double-check your [Office 365 URLs and IP address ranges](https://docs.microsoft.com/en-us/microsoftteams/office-365-urls-ip-address-ranges).</span></span>
    
3. <span data-ttu-id="a020f-140">Попросите Скайп для бизнес-контакта отправляет запрос на беседу.</span><span class="sxs-lookup"><span data-stu-id="a020f-140">Ask your Skype for Business contact to send you a request to chat.</span></span> <span data-ttu-id="a020f-141">Если вы не получите свой запрос, проблема заключается в настройках брандмауэра (если они уже подтверждения правильности их параметры брандмауэра).</span><span class="sxs-lookup"><span data-stu-id="a020f-141">If you don't receive their request, the problem is your firewall settings (assuming they've already confirmed their firewall settings are correct).</span></span>
    
4. <span data-ttu-id="a020f-142">Другой способ проверки, является ли проблема брандмауэра — это расположение wifi не за брандмауэром, таких как кафе и использовать Скайп для бизнеса отправить запрос контакту чата.</span><span class="sxs-lookup"><span data-stu-id="a020f-142">Another way to test whether the problem is your firewall is to go to a wifi location not behind your firewall such as a coffee shop, and use Skype for Business to send a request to your contact to chat.</span></span> <span data-ttu-id="a020f-143">Если сообщение проходит через существует, но не в том случае, когда вы находитесь на работе, это значит, проблема является брандмауэра.</span><span class="sxs-lookup"><span data-stu-id="a020f-143">If the message goes through there, but not when you're at work, then you know the problem is your firewall.</span></span>
    
## <a name="how-to-find-others-and-be-found-when-connecting-with-another-business"></a><span data-ttu-id="a020f-144">Как найти других пользователей и найти, при подключении через другой компании</span><span class="sxs-lookup"><span data-stu-id="a020f-144">How to find others, and be found, when connecting with another business</span></span>
<span data-ttu-id="a020f-145"><a name="bk_preview"> </a></span><span class="sxs-lookup"><span data-stu-id="a020f-145"></span></span>

<span data-ttu-id="a020f-146">После включения внешнего обмена данными с другими Скайп для бизнес-пользователи пользователям найти федеративных Скайп для бизнес-пользователей по ключевым словам их учетное имя: например, Rob@contoso.com. Затем необходимо добавить пользователя в свой список контактов.</span><span class="sxs-lookup"><span data-stu-id="a020f-146">After you enable external communication with other Skype for Business users, your users can find federated Skype for Business users by searching for their sign-in name: for example, Rob@contoso.com. Then they will need to add the person to their list of contacts.</span></span>
  
![Для поиска пользователя в федеративных бизнеса, необходимо найти их адреса электронной почты (обычно это также их учетное имя).](../images/20242f85-0636-463b-8df3-1e123784d7fa.png)
  
## <a name="tips-on-setting-up-communications-with-federated-businesses"></a><span data-ttu-id="a020f-148">Советы по настройке связь с федеративными бизнеса</span><span class="sxs-lookup"><span data-stu-id="a020f-148">Tips on setting up communications with federated businesses</span></span>
<span data-ttu-id="a020f-149"><a name="bk_preview"> </a></span><span class="sxs-lookup"><span data-stu-id="a020f-149"></span></span>

- <span data-ttu-id="a020f-150">Чтобы настроить федерацию между Скайп для бизнеса 2015 и Скайп для бизнеса в Интернет, обратитесь к разделу в этой статье TechNet: [Настройка федерации с Скайп для бизнеса в Интернет](https://technet.microsoft.com/en-us/library/jj205126.aspx).</span><span class="sxs-lookup"><span data-stu-id="a020f-150">To configure federation between Skype for Business 2015 and Skype for Business Online, see this TechNet article: [Configure federation with Skype for Business Online](https://technet.microsoft.com/en-us/library/jj205126.aspx).</span></span>
    
- <span data-ttu-id="a020f-151">Чтобы настроить федерации между Lync и Скайп для бизнеса в Интернет, обратитесь к разделу в этой статье TechNet: [Настройка поддержки федерации для клиента Lync Online](https://technet.microsoft.com/en-us/library/hh202193.aspx).</span><span class="sxs-lookup"><span data-stu-id="a020f-151">To configure federation between Lync and Skype for Business Online, see this TechNet article: [Configuring Federation Support for a Lync Online Customer](https://technet.microsoft.com/en-us/library/hh202193.aspx).</span></span>
    
- <span data-ttu-id="a020f-152">Когда два Скайп для бизнес-пользователей в Office 365 обмениваются данными друг с другом в разных доменах, их можно использовать Скайп только для функции бизнес-(например, видеобеседы или рабочему столу), которые включены в обеих организациях.</span><span class="sxs-lookup"><span data-stu-id="a020f-152">When two Skype for Business users in Office 365 are communicating with each other on separate domains, they can only use Skype for Business features (for example, video conversations or desktop sharing) that are turned on in both organizations.</span></span>
    
- <span data-ttu-id="a020f-153">Если на месте или хранение для судебного разбирательства находится в состоянии Скайп для корпоративных пользователей в вашей организации, любой мгновенные сообщения от этого пользователя и другие Скайп для бизнеса или Скайп пользователей будут сохраняться **Восстанавливаемых элементов** в почтовом ящике.</span><span class="sxs-lookup"><span data-stu-id="a020f-153">If a Skype for Business user in your organization is put on an In-Place or Litigation Hold, any IM conversations between that user and other Skype for Business or Skype users will be saved in **Recoverable Items** in their mailbox.</span></span> <span data-ttu-id="a020f-154">Эти беседы не сохраняются в папке **Журнала бесед** в почтовом ящике.</span><span class="sxs-lookup"><span data-stu-id="a020f-154">These conversations aren't saved in the **Conversations History** folder in their mailbox.</span></span>
    
## <a name="turn-off-external-communication-for-specific-individuals"></a><span data-ttu-id="a020f-155">Отключение внешнего обмена данными для определенных пользователей</span><span class="sxs-lookup"><span data-stu-id="a020f-155">Turn off external communication for specific individuals</span></span>
<span data-ttu-id="a020f-156"><a name="bk_preview"> </a></span><span class="sxs-lookup"><span data-stu-id="a020f-156"></span></span>

<span data-ttu-id="a020f-157">После включения внешнего обмена данными для всего предприятия, можно отключить его только определенным лицам.</span><span class="sxs-lookup"><span data-stu-id="a020f-157">After you enable external communication for your entire business, you can turn it off for only specific individuals.</span></span>
  
1. <span data-ttu-id="a020f-158">Выполните вход с учетной записью администратора Office 365.</span><span class="sxs-lookup"><span data-stu-id="a020f-158">Sign in with your Office 365 admin account.</span></span>
    
2. <span data-ttu-id="a020f-159">В центре администрирования Office 365 перейдите к **пользователям** > **Активные пользователи**.</span><span class="sxs-lookup"><span data-stu-id="a020f-159">In the Office 365 admin center, go to **Users** > **Active users**.</span></span>
    
3. <span data-ttu-id="a020f-160">В список пользователей выберите пользователя и в разделе **Дополнительные параметры**, нажмите кнопку **Изменить Скайп для свойства Business**.</span><span class="sxs-lookup"><span data-stu-id="a020f-160">In the list of users, choose the user, and then, under **More Settings**, click **Edit Skype for Business properties**.</span></span>
    
    ![Выберите Скайп для бизнеса](../images/2b0f9a7b-3fee-4f4b-968a-68c429eeb395.png)
  
4. <span data-ttu-id="a020f-162">В **Скайп по центру администрирования бизнеса**выберите **внешних коммуникаций**.</span><span class="sxs-lookup"><span data-stu-id="a020f-162">In the **Skype for Business admin center**, choose **External communications**.</span></span>
    
    <span data-ttu-id="a020f-163">На странице " **Параметры** " будут выбраны все варианты.</span><span class="sxs-lookup"><span data-stu-id="a020f-163">On the **Options** page, all of the choices will be selected.</span></span> <span data-ttu-id="a020f-164">Снимите флажок коммуникаций, которые необходимо отключить.</span><span class="sxs-lookup"><span data-stu-id="a020f-164">Clear the communications you want to disable.</span></span> <span data-ttu-id="a020f-165">На следующем рисунке показана, что Джейкоба будет иметь возможность обмениваться данными с пользователями в других надежных бизнеса, но не с другими пользователями Скайп.</span><span class="sxs-lookup"><span data-stu-id="a020f-165">The following image shows that Jakob will be able to communicate with people in other trusted businesses, but not with other Skype users.</span></span>
    
    ![Выберите внешние контакты](../images/4e546321-a065-48ed-8ac7-1e112a780eab.png)
  
5. <span data-ttu-id="a020f-167">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="a020f-167">Choose **Save**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="a020f-168">Может потребоваться ожидать в течение 24 часов, чтобы изменения вступили в силу.</span><span class="sxs-lookup"><span data-stu-id="a020f-168">You may have to wait for up to 24 hours for your changes to take effect.</span></span> 
  


[!INCLUDE [LinkedIn Learning Info](../common/office/linkedin-learning-info.md)]
   
   
## <a name="related-topics"></a><span data-ttu-id="a020f-169">См. также:</span><span class="sxs-lookup"><span data-stu-id="a020f-169">Related topics</span></span>
<span data-ttu-id="a020f-170"><a name="bk_preview"> </a></span><span class="sxs-lookup"><span data-stu-id="a020f-170"></span></span>

[<span data-ttu-id="a020f-171">Настройка Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="a020f-171">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)
  
[<span data-ttu-id="a020f-172">Разрешение на добавление контактов Skype пользователям Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="a020f-172">Let Skype for Business users add Skype contacts</span></span>](let-skype-for-business-users-add-skype-contacts.md)
  

