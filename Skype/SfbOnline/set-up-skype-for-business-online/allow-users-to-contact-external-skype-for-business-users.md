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
f1.keywords:
- CSH
ms.custom:
- Setup
- For O365M_ShareLync
- ms.lync.lac.OrgExternalAccess
- ms.lync.lac.skypefederation
- O365E_HRCLYNC _ SipFederationSrvRecordVerified_FL312122
- O365E_ShareLync
- O365M_ShareLync
- O365P_ExternalCommDesc
- O365P_ShareLync
- LIL_Placement
description: 'Узнайте, как настроить Skype для бизнеса, чтобы пользователи общались с пользователями в другой организации или разрешали внешним контактам общаться с ними. '
ms.openlocfilehash: 8acab73fec7337ee70cd8b5059b00df42e836e62
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51093513"
---
# <a name="allow-users-to-contact-external-skype-for-business-users"></a><span data-ttu-id="83575-103">Разрешите пользователям связываться с внешними пользователями Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="83575-103">Allow users to contact external Skype for Business users</span></span>
  
<span data-ttu-id="83575-104">Выполните действия, описанные в этой статье, в следующих случаях.</span><span class="sxs-lookup"><span data-stu-id="83575-104">Use the steps in this article when:</span></span>
  
- <span data-ttu-id="83575-105">У вас есть пользователи в разных доменах вашей компании.</span><span class="sxs-lookup"><span data-stu-id="83575-105">You have users on different domains in your business.</span></span> <span data-ttu-id="83575-106">Например, Rob@ContosoEast.com и Ann@ContosoWest.com.</span><span class="sxs-lookup"><span data-stu-id="83575-106">For example, Rob@ContosoEast.com and Ann@ContosoWest.com.</span></span>

- <span data-ttu-id="83575-107">Вы хотите, чтобы пользователи в вашей организации использовали Skype для бизнеса для связи с людьми в определенных организациях за пределами вашей организации.</span><span class="sxs-lookup"><span data-stu-id="83575-107">You want the people in your organization to use Skype for Business to contact people in specific businesses outside of your organization.</span></span>

- <span data-ttu-id="83575-108">Вы хотите, чтобы все пользователи Skype для бизнеса могли находить вас и связываться с вами, используя ваш адрес электронной почты.</span><span class="sxs-lookup"><span data-stu-id="83575-108">You want anyone else in the world who uses Skype for Business to be able to find and contact you using your email address.</span></span> <span data-ttu-id="83575-109">Если вы и они используют настройки Skype для бизнеса по умолчанию, это будет работать автоматически.</span><span class="sxs-lookup"><span data-stu-id="83575-109">If you and they use the default Skype for Business settings, this will work automatically.</span></span> <span data-ttu-id="83575-110">Если это не так, им необходимо убедиться, что ваш домен не заблокирован в их конфигурации.</span><span class="sxs-lookup"><span data-stu-id="83575-110">If they don't, then they need to make sure their configuration isn't blocking your domain.</span></span>

## <a name="enable-business-to-business-communications-for-your-users"></a><span data-ttu-id="83575-111">Включить связь между бизнес-данными для пользователей</span><span class="sxs-lookup"><span data-stu-id="83575-111">Enable business-to-business communications for your users</span></span>

<span data-ttu-id="83575-112"><a name="bk_preview"> </a></span><span class="sxs-lookup"><span data-stu-id="83575-112"><a name="bk_preview"> </a></span></span>

<span data-ttu-id="83575-113">Для этого необходимо иметь [разрешения](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) администратора в Microsoft 365 или Office 365 в обеих организациях.</span><span class="sxs-lookup"><span data-stu-id="83575-113">You must have [admin permissions](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) in Microsoft 365 or Office 365 in both organizations to do this communication.</span></span>

<span data-ttu-id="83575-114">![Значок логотипа Microsoft Teams ](../images/teams-logo-30x30.png) **с помощью Центра администрирования Teams**</span><span class="sxs-lookup"><span data-stu-id="83575-114">![An icon showing the Microsoft Teams logo](../images/teams-logo-30x30.png) **Using the Teams admin center**</span></span>
  
1. <span data-ttu-id="83575-115">Во sign in with your Microsoft 365 or Office 365 admin account.</span><span class="sxs-lookup"><span data-stu-id="83575-115">Sign in with your Microsoft 365 or Office 365 admin account.</span></span>

2. <span data-ttu-id="83575-116">В Центре администрирования перейдите в **Teams для центров**  >  **администрирования.**</span><span class="sxs-lookup"><span data-stu-id="83575-116">In the admin center, go to **Admin Centers** > **Teams**.</span></span>

    ![Выберите администратора Teams.](../images/MS-Teams-Admin.png)
  
3. <span data-ttu-id="83575-118">В центре **Teams выберите** устаревший портал **Skype** и >  
  ![ выберите устаревший портал SfB.](../images/SFBlegacy-size65.png)</span><span class="sxs-lookup"><span data-stu-id="83575-118">In the **Teams center**, choose **Skype** > **Legacy Portal**
![Choose the SfB Legacy Portal.](../images/SFBlegacy-size65.png)</span></span>

4. <span data-ttu-id="83575-119">В **Центре администрирования Skype для бизнеса** выберите пункт **Организация** > **Внешний обмен данными**.</span><span class="sxs-lookup"><span data-stu-id="83575-119">In the **Skype for Business admin center**, choose **Organization** > **External communications**.</span></span>
5. <span data-ttu-id="83575-120">Чтобы настроить обмен данными с конкретной компанией или с пользователями из другого домена, в раскрывающемся списке выберите **Включить только для разрешенных доменов**.</span><span class="sxs-lookup"><span data-stu-id="83575-120">To set up communication with a specific business or with users in another domain, in the drop-down box, choose **On only for allowed domains**.</span></span>

    <span data-ttu-id="83575-121">Если вы хотите включить взаимодействие со всеми пользователями, у которых есть политики Skype для бизнеса, выберите "Включить" (за исключением **заблокированных доменов).**</span><span class="sxs-lookup"><span data-stu-id="83575-121">OR, if you want to enable communication with everyone else in the world who has open Skype for Business policies, choose **On except for blocked domains**.</span></span> <span data-ttu-id="83575-122">Это настройка по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="83575-122">This is the default setting.</span></span>

6. <span data-ttu-id="83575-123">В **области "Заблокированные или разрешенные домены"** выберите и добавьте имя домена, **+** который вы хотите разрешить.</span><span class="sxs-lookup"><span data-stu-id="83575-123">Under **Blocked or allowed domains**, choose **+** and add the name of the domain you want to allow.</span></span>

7. <span data-ttu-id="83575-124">Убедитесь, что администратор другой организации делает те же действия в центре администрирования **Skype для бизнеса.**</span><span class="sxs-lookup"><span data-stu-id="83575-124">Make sure the admin in the other organization does these same steps in their **Skype for Business admin center**.</span></span> <span data-ttu-id="83575-125">Например, в списке **разрешенных доменов** администратор должен ввести домен для вашей компании.</span><span class="sxs-lookup"><span data-stu-id="83575-125">For example, in their **allowed domains** list, their admin needs to enter the domain for your business.</span></span>

8. <span data-ttu-id="83575-126">Если вы используете брандмауэр Windows, Skype для бизнеса автоматически открывает требуемые порты.</span><span class="sxs-lookup"><span data-stu-id="83575-126">If you're using Windows Firewall, Skype for Business opens the required ports automatically.</span></span>

    <span data-ttu-id="83575-127">Если в вашей организации используется другое брандмауэр для ограничения подключения компьютеров в сети к Интернету, убедитесь, что клиентские компьютеры имеют доступ к следующим URL-адресам и диапазонам IP-адресов [Office 365.](/microsoftteams/office-365-urls-ip-address-ranges)</span><span class="sxs-lookup"><span data-stu-id="83575-127">If your organization is using a different firewall solution to restrict computers on your network from connecting to the Internet, ensure your client computers are able to access the following [Office 365 URLs and IP address ranges](/microsoftteams/office-365-urls-ip-address-ranges).</span></span> <span data-ttu-id="83575-128">Для этого может потребоваться добавить FQDNs в список исходящие списки разрешаний в брандмауэре или конфигурации инфраструктуры прокси-сервера: **\* .api.skype.com,** \* *_.users.storage.live.com_* и **graph.skype.com.**</span><span class="sxs-lookup"><span data-stu-id="83575-128">This may require adding the FQDNs to the outbound allow list in your firewall or proxy infrastructure configuration: **\*.api.skype.com**, \**_.users.storage.live.com_*, and **graph.skype.com**.</span></span> <span data-ttu-id="83575-129">Инструкции о том, как открыть эти порты в брандмауэре, можно найти в документации, документации к ним.</span><span class="sxs-lookup"><span data-stu-id="83575-129">For instructions on how to open these ports in your firewall, check the documentation that came with it.</span></span>

    <span data-ttu-id="83575-130">Список всех портов, которые нужно открыть, см. в URL-адресах и диапазонах IP-адресов [Office 365.](/microsoftteams/office-365-urls-ip-address-ranges)</span><span class="sxs-lookup"><span data-stu-id="83575-130">For a list of all ports you need to open, see [Office 365 URLs and IP address ranges](/microsoftteams/office-365-urls-ip-address-ranges).</span></span>

9. <span data-ttu-id="83575-131">Убедитесь, что администратор организации также следовал этим шагам.</span><span class="sxs-lookup"><span data-stu-id="83575-131">Make sure that the administrator in the organization has also followed these steps.</span></span>

10. <span data-ttu-id="83575-132">**ПОДОЖДИТЕ ДО 24 ЧАСОВ.**</span><span class="sxs-lookup"><span data-stu-id="83575-132">**WAIT UP TO 24 HOURS TO TEST**.</span></span> <span data-ttu-id="83575-133">На их заполнение во всех центрах обработки данных может занять до 24 часов.</span><span class="sxs-lookup"><span data-stu-id="83575-133">When you change the external communications settings, it can take up to 24 hours for the changes to populate across all the data centers.</span></span>

<span data-ttu-id="83575-134">![Skype Вы можете разрешить своим пользователям искать и мгновенные звонки всем пользователям ](../images/58550720-2a68-42d1-a926-1884e6aeb55c.png) Бесплатного потребительского приложения Skype!</span><span class="sxs-lookup"><span data-stu-id="83575-134">![Skype](../images/58550720-2a68-42d1-a926-1884e6aeb55c.png) You can allow your users to search for and IM with everyone who uses Skype, the free consumer app!</span></span> <span data-ttu-id="83575-135">Подробнее см. в видео "Позволить пользователям Skype для [бизнеса добавлять контакты Skype".](let-skype-for-business-users-add-skype-contacts.md)</span><span class="sxs-lookup"><span data-stu-id="83575-135">To learn more, see [Let Skype for Business users add Skype contacts](let-skype-for-business-users-add-skype-contacts.md).</span></span>
  
## <a name="test-and-troubleshoot"></a><span data-ttu-id="83575-136">Проверка и устранение неполадок</span><span class="sxs-lookup"><span data-stu-id="83575-136">Test and troubleshoot</span></span>

<span data-ttu-id="83575-137"><a name="bk_preview"> </a></span><span class="sxs-lookup"><span data-stu-id="83575-137"><a name="bk_preview"> </a></span></span>

 <span data-ttu-id="83575-138">**Наиболее распространенная проблема, которая встречается при настройке связи между офисами, — это правильное получение URL-адресов [и диапазонов IP-адресов Office 365.](/microsoftteams/office-365-urls-ip-address-ranges)**</span><span class="sxs-lookup"><span data-stu-id="83575-138">**The most common issue people encounter when setting up business-to-business communication is getting their [Office 365 URLs and IP address ranges](/microsoftteams/office-365-urls-ip-address-ranges) right.**</span></span>
  
<span data-ttu-id="83575-139">Чтобы проверить конфигурацию, вам нужен контакт в Skype для бизнеса, который не работает в брандмауэре вашей компании.</span><span class="sxs-lookup"><span data-stu-id="83575-139">To test your setup, you need a contact on Skype for Business who's not behind your company firewall.</span></span>
  
1. <span data-ttu-id="83575-140">После изменения параметров внешней связи подождите **до 24 ЧАСОВ для проверки.**</span><span class="sxs-lookup"><span data-stu-id="83575-140">After you change your external communications settings, **WAIT UP TO 24 HOURS TO TEST**.</span></span>

2. <span data-ttu-id="83575-141">В Skype для бизнеса наищите контакт в Skype для бизнеса и отправьте запрос на чат.</span><span class="sxs-lookup"><span data-stu-id="83575-141">In Skype for Business, search for your contact in Skype for Business, and send a request to chat.</span></span>

    <span data-ttu-id="83575-142">Если вы получаете сообщение о том, что не удалось отправить сообщение из-за политики компании, проверьте [URL-адреса и диапазоны IP-адресов Office 365.](/microsoftteams/office-365-urls-ip-address-ranges)</span><span class="sxs-lookup"><span data-stu-id="83575-142">If you get a message that it couldn't be sent due to company policy, you need to double-check your [Office 365 URLs and IP address ranges](/microsoftteams/office-365-urls-ip-address-ranges).</span></span>

3. <span data-ttu-id="83575-143">Попросите контакт Skype для бизнеса отправить вам запрос на чат.</span><span class="sxs-lookup"><span data-stu-id="83575-143">Ask your Skype for Business contact to send you a request to chat.</span></span> <span data-ttu-id="83575-144">Если вы не получили его запрос, проблема в настройках вашего брандмауэра (предполагается, что он подтвердил корректность настроек своего брандмауэра).</span><span class="sxs-lookup"><span data-stu-id="83575-144">If you don't receive their request, the problem is your firewall settings (assuming they've already confirmed their firewall settings are correct).</span></span>

4. <span data-ttu-id="83575-145">Еще один способ проверить, есть ли проблема с брандмауэром, — перейти в сеть Wi-Fi, не расположенную за брандмауэром, например в кафе.</span><span class="sxs-lookup"><span data-stu-id="83575-145">Another way to test whether the problem is your firewall is to go to a wifi location not behind your firewall, such as a coffee shop.</span></span> <span data-ttu-id="83575-146">Используйте Skype для бизнеса, чтобы отправить контакту запрос на чат.</span><span class="sxs-lookup"><span data-stu-id="83575-146">Use Skype for Business to send a request to your contact to chat.</span></span> <span data-ttu-id="83575-147">Если сообщение там находится, но не на работе, значит проблема в брандмауэре.</span><span class="sxs-lookup"><span data-stu-id="83575-147">If the message goes through there, but not when you're at work, then you know the problem is your firewall.</span></span>

## <a name="how-to-find-others-and-be-found-when-connecting-with-another-business"></a><span data-ttu-id="83575-148">Как найти других людей и найти их при подключении к другой компании</span><span class="sxs-lookup"><span data-stu-id="83575-148">How to find others, and be found, when connecting with another business</span></span>

<span data-ttu-id="83575-149"><a name="bk_preview"> </a></span><span class="sxs-lookup"><span data-stu-id="83575-149"><a name="bk_preview"> </a></span></span>

<span data-ttu-id="83575-150">После того как вы ввяжете внешнюю связь с другими пользователями Skype для бизнеса, ваши пользователи смогут находить федеративную учетную запись пользователей Skype для бизнеса по их именам для регистрации.</span><span class="sxs-lookup"><span data-stu-id="83575-150">After you enable external communication with other Skype for Business users, your users can find federated Skype for Business users by searching for their sign-in names.</span></span> <span data-ttu-id="83575-151">Пример: Rob@contoso.com.</span><span class="sxs-lookup"><span data-stu-id="83575-151">An example is Rob@contoso.com.</span></span> <span data-ttu-id="83575-152">Затем нужно будет добавить этого человека в свой список контактов.</span><span class="sxs-lookup"><span data-stu-id="83575-152">Then they will need to add the person to their list of contacts.</span></span>
  
![Чтобы найти пользователя в федераированной компании, необходимо найти его адрес электронной почты (обычно это имя для регистрации).](../images/20242f85-0636-463b-8df3-1e123784d7fa.png)
  
## <a name="tips-on-setting-up-communications-with-federated-businesses"></a><span data-ttu-id="83575-154">Советы по настройке связи с федеративными организациями</span><span class="sxs-lookup"><span data-stu-id="83575-154">Tips on setting up communications with federated businesses</span></span>

<span data-ttu-id="83575-155"><a name="bk_preview"> </a></span><span class="sxs-lookup"><span data-stu-id="83575-155"><a name="bk_preview"> </a></span></span>

- <span data-ttu-id="83575-156">Чтобы настроить федерацию между Skype для бизнеса 2015 и Skype для бизнеса Online, см. статью "Настройка федерации в [Skype для бизнеса Online".](../../SfbHybrid/hybrid/configure-federation-with-skype-for-business-online.md?bc=%2fSkypeForBusiness%2fbreadcrumb%2ftoc.json&toc=%2fSkypeForBusiness%2ftoc.json)</span><span class="sxs-lookup"><span data-stu-id="83575-156">To configure federation between Skype for Business 2015 and Skype for Business Online, see this  article: [Configure federation with Skype for Business Online](../../SfbHybrid/hybrid/configure-federation-with-skype-for-business-online.md?bc=%2fSkypeForBusiness%2fbreadcrumb%2ftoc.json&toc=%2fSkypeForBusiness%2ftoc.json).</span></span>

- <span data-ttu-id="83575-157">Чтобы настроить федерацию между Lync и Skype для бизнеса Online, см. статью "Настройка поддержки федерации для клиента [Lync Online".](/previous-versions/office/lync-server-2013/lync-server-2013-configuring-federation-support-for-a-lync-online-customer)</span><span class="sxs-lookup"><span data-stu-id="83575-157">To configure federation between Lync and Skype for Business Online, see this  article: [Configuring Federation Support for a Lync Online Customer](/previous-versions/office/lync-server-2013/lync-server-2013-configuring-federation-support-for-a-lync-online-customer).</span></span>

- <span data-ttu-id="83575-158">Когда два пользователя Skype для бизнеса в Microsoft 365 или Office 365 общаются друг с другом в разных доменах, они могут использовать только функции Skype для бизнеса (например, видеосвязь или совместный доступ к рабочему столу), которые были включены в обеих организациях.</span><span class="sxs-lookup"><span data-stu-id="83575-158">When two Skype for Business users in Microsoft 365 or Office 365 are communicating with each other on separate domains, they can only use Skype for Business features (for example, video conversations or desktop sharing) that are turned on in both organizations.</span></span>

- <span data-ttu-id="83575-159">Если пользователь Skype для бизнеса в вашей организации поставлен на удержание In-Place или для судебного разбирательства, все мгновенные  сообщения между ним и другими пользователями Skype для бизнеса или Skype будут сохранены в элементе с возможностью восстановления в его почтовом ящике.</span><span class="sxs-lookup"><span data-stu-id="83575-159">If a Skype for Business user in your organization is put on an In-Place or Litigation Hold, any IM conversations between that user and other Skype for Business or Skype users will be saved in **Recoverable Items** in their mailbox.</span></span> <span data-ttu-id="83575-160">Эти беседы не сохраняются в папке **"История** бесед" их почтового ящика.</span><span class="sxs-lookup"><span data-stu-id="83575-160">These conversations aren't saved in the **Conversations History** folder in their mailbox.</span></span>

## <a name="turn-off-external-communication-for-specific-individuals"></a><span data-ttu-id="83575-161">Отключение внешней связи для определенных пользователей</span><span class="sxs-lookup"><span data-stu-id="83575-161">Turn off external communication for specific individuals</span></span>

<span data-ttu-id="83575-162"><a name="bk_preview"> </a></span><span class="sxs-lookup"><span data-stu-id="83575-162"><a name="bk_preview"> </a></span></span>

<span data-ttu-id="83575-163">Включив внешнюю связь для всей компании, вы можете отключить ее только для отдельных пользователей.</span><span class="sxs-lookup"><span data-stu-id="83575-163">After you enable external communication for your entire business, you can turn it off for only specific individuals.</span></span>
  
1. <span data-ttu-id="83575-164">Во sign in with your Microsoft 365 or Office 365 admin account.</span><span class="sxs-lookup"><span data-stu-id="83575-164">Sign in with your Microsoft 365 or Office 365 admin account.</span></span>

2. <span data-ttu-id="83575-165">В Центре администрирования перейдите в группу **"Пользователи,**  >  **активные пользователи".**</span><span class="sxs-lookup"><span data-stu-id="83575-165">In the admin center, go to **Users** > **Active users**.</span></span>

3. <span data-ttu-id="83575-166">В списке пользователей выберите пользователя, а затем в списке "Дополнительные параметры" щелкните "Изменить свойства **Skype для бизнеса".**</span><span class="sxs-lookup"><span data-stu-id="83575-166">In the list of users, choose the user, and then, under **More Settings**, click **Edit Skype for Business properties**.</span></span>

    ![Выберите Skype для бизнеса](../images/2b0f9a7b-3fee-4f4b-968a-68c429eeb395.png)
  
4. <span data-ttu-id="83575-168">В Центре **администрирования Skype для бизнеса выберите**"Внешняя **связь".**</span><span class="sxs-lookup"><span data-stu-id="83575-168">In the **Skype for Business admin center**, choose **External communications**.</span></span>

    <span data-ttu-id="83575-169">На  странице "Параметры" будут выбраны все варианты.</span><span class="sxs-lookup"><span data-stu-id="83575-169">On the **Options** page, all of the choices will be selected.</span></span> <span data-ttu-id="83575-170">Очистка сообщений, которые вы хотите отключить.</span><span class="sxs-lookup"><span data-stu-id="83575-170">Clear the communications you want to disable.</span></span> <span data-ttu-id="83575-171">На рисунке ниже показано, что пользователь Jakob сможет общаться с людьми в других доверенных компаниях, но не с другими пользователями Skype.</span><span class="sxs-lookup"><span data-stu-id="83575-171">The following image shows that Jakob will be able to communicate with people in other trusted businesses, but not with other Skype users.</span></span>

    ![Выбор внешних контактов](../images/4e546321-a065-48ed-8ac7-1e112a780eab.png)
  
5. <span data-ttu-id="83575-173">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="83575-173">Choose **Save**.</span></span>

> [!NOTE]
> <span data-ttu-id="83575-174">Чтобы изменения вступили в силу, может потребоваться до 24 часов.</span><span class="sxs-lookup"><span data-stu-id="83575-174">You may have to wait for up to 24 hours for your changes to take effect.</span></span>
  
[!INCLUDE [LinkedIn Learning Info](../../common/office/linkedin-learning-info.md)]

## <a name="related-topics"></a><span data-ttu-id="83575-175">См. также</span><span class="sxs-lookup"><span data-stu-id="83575-175">Related topics</span></span>

<span data-ttu-id="83575-176"><a name="bk_preview"> </a></span><span class="sxs-lookup"><span data-stu-id="83575-176"><a name="bk_preview"> </a></span></span>

[<span data-ttu-id="83575-177">Настройка Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="83575-177">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)
  
[<span data-ttu-id="83575-178">Разрешение на добавление контактов Skype пользователям Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="83575-178">Let Skype for Business users add Skype contacts</span></span>](let-skype-for-business-users-add-skype-contacts.md)
