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
description: 'Узнайте, как настроить Skype для бизнеса позволить пользователям общаться с пользователями в другой организации или позволить внешним контактам общаться с ними. '
ms.openlocfilehash: 3b4aeb2b40cf34579d3d584a50664550cd34038c
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/06/2021
ms.locfileid: "52240007"
---
# <a name="allow-users-to-contact-external-skype-for-business-users"></a><span data-ttu-id="da996-103">Разрешите пользователям связываться с внешними пользователями Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="da996-103">Allow users to contact external Skype for Business users</span></span>

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]
  
<span data-ttu-id="da996-104">Выполните действия, описанные в этой статье, в следующих случаях.</span><span class="sxs-lookup"><span data-stu-id="da996-104">Use the steps in this article when:</span></span>
  
- <span data-ttu-id="da996-105">У вас есть пользователи в разных доменах в вашей компании.</span><span class="sxs-lookup"><span data-stu-id="da996-105">You have users on different domains in your business.</span></span> <span data-ttu-id="da996-106">Например, Rob@ContosoEast.com и Ann@ContosoWest.com.</span><span class="sxs-lookup"><span data-stu-id="da996-106">For example, Rob@ContosoEast.com and Ann@ContosoWest.com.</span></span>

- <span data-ttu-id="da996-107">Вы хотите, чтобы люди в вашей организации использовали Skype для бизнеса для связи с людьми в определенных организациях за пределами организации.</span><span class="sxs-lookup"><span data-stu-id="da996-107">You want the people in your organization to use Skype for Business to contact people in specific businesses outside of your organization.</span></span>

- <span data-ttu-id="da996-108">Вы хотите, чтобы все, кто использует Skype для бизнеса, могли найти вас и связаться с вами, используя ваш адрес электронной почты.</span><span class="sxs-lookup"><span data-stu-id="da996-108">You want anyone else in the world who uses Skype for Business to be able to find and contact you using your email address.</span></span> <span data-ttu-id="da996-109">Если вы и они используете параметры Skype для бизнеса по умолчанию, это будет работать автоматически.</span><span class="sxs-lookup"><span data-stu-id="da996-109">If you and they use the default Skype for Business settings, this will work automatically.</span></span> <span data-ttu-id="da996-110">В этом случае необходимо убедиться, что конфигурация не блокирует ваш домен.</span><span class="sxs-lookup"><span data-stu-id="da996-110">If they don't, then they need to make sure their configuration isn't blocking your domain.</span></span>

## <a name="enable-business-to-business-communications-for-your-users"></a><span data-ttu-id="da996-111">Включить взаимодействие между пользователями</span><span class="sxs-lookup"><span data-stu-id="da996-111">Enable business-to-business communications for your users</span></span>

<span data-ttu-id="da996-112"><a name="bk_preview"> </a></span><span class="sxs-lookup"><span data-stu-id="da996-112"><a name="bk_preview"> </a></span></span>

<span data-ttu-id="da996-113">Для этого у вас [должны](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) быть разрешения администратора Microsoft 365 или Office 365 в обеих организациях.</span><span class="sxs-lookup"><span data-stu-id="da996-113">You must have [admin permissions](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) in Microsoft 365 or Office 365 in both organizations to do this communication.</span></span>

<span data-ttu-id="da996-114">![Значок с логотипом Microsoft Teams ](../images/teams-logo-30x30.png) **с помощью Teams центра администрирования**</span><span class="sxs-lookup"><span data-stu-id="da996-114">![An icon showing the Microsoft Teams logo](../images/teams-logo-30x30.png) **Using the Teams admin center**</span></span>
  
1. <span data-ttu-id="da996-115">Во sign in with your Microsoft 365 or Office 365 admin account.</span><span class="sxs-lookup"><span data-stu-id="da996-115">Sign in with your Microsoft 365 or Office 365 admin account.</span></span>

2. <span data-ttu-id="da996-116">В Центре администрирования перейдите в **центр** администрирования  >  Teams.</span><span class="sxs-lookup"><span data-stu-id="da996-116">In the admin center, go to **Admin Centers** > **Teams**.</span></span>

    ![Выберите администратора Teams.](../images/MS-Teams-Admin.png)
  
3. <span data-ttu-id="da996-118">В центре **Teams** выберите **Skype** > **устаревший портал** Выберите 
  ![ устаревший портал SfB.](../images/SFBlegacy-size65.png)</span><span class="sxs-lookup"><span data-stu-id="da996-118">In the **Teams center**, choose **Skype** > **Legacy Portal**
![Choose the SfB Legacy Portal.](../images/SFBlegacy-size65.png)</span></span>

4. <span data-ttu-id="da996-119">В **Центре администрирования Skype для бизнеса** выберите пункт **Организация** > **Внешний обмен данными**.</span><span class="sxs-lookup"><span data-stu-id="da996-119">In the **Skype for Business admin center**, choose **Organization** > **External communications**.</span></span>
5. <span data-ttu-id="da996-120">Чтобы настроить обмен данными с конкретной компанией или с пользователями из другого домена, в раскрывающемся списке выберите **Включить только для разрешенных доменов**.</span><span class="sxs-lookup"><span data-stu-id="da996-120">To set up communication with a specific business or with users in another domain, in the drop-down box, choose **On only for allowed domains**.</span></span>

    <span data-ttu-id="da996-121">Или, если вы хотите включить связь со всеми пользователями в мире, которые открыли политики Skype для бизнеса, выберите В сети, кроме **заблокированных доменов.**</span><span class="sxs-lookup"><span data-stu-id="da996-121">OR, if you want to enable communication with everyone else in the world who has open Skype for Business policies, choose **On except for blocked domains**.</span></span> <span data-ttu-id="da996-122">Это параметр по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="da996-122">This is the default setting.</span></span>

6. <span data-ttu-id="da996-123">В **области Заблокированные или разрешенные домены** выберите и добавьте имя домена, **+** который вы хотите разрешить.</span><span class="sxs-lookup"><span data-stu-id="da996-123">Under **Blocked or allowed domains**, choose **+** and add the name of the domain you want to allow.</span></span>

7. <span data-ttu-id="da996-124">Убедитесь, что администратор другой организации делает те же действия в Skype для бизнеса **администрирования**.</span><span class="sxs-lookup"><span data-stu-id="da996-124">Make sure the admin in the other organization does these same steps in their **Skype for Business admin center**.</span></span> <span data-ttu-id="da996-125">Например, в списке **разрешенных доменов** его администратор должен ввести домен для вашей компании.</span><span class="sxs-lookup"><span data-stu-id="da996-125">For example, in their **allowed domains** list, their admin needs to enter the domain for your business.</span></span>

8. <span data-ttu-id="da996-126">Если вы используете брандмауэр Windows, Skype для бизнеса автоматически открывает необходимые порты.</span><span class="sxs-lookup"><span data-stu-id="da996-126">If you're using Windows Firewall, Skype for Business opens the required ports automatically.</span></span>

    <span data-ttu-id="da996-127">Если в вашей организации используется другое решение брандмауэра для ограничения подключения компьютеров в сети к Интернету, убедитесь, что клиентские компьютеры имеют доступ к следующим [URL Office 365 URL-адресам](/microsoftteams/office-365-urls-ip-address-ranges)и диапазонам IP-адресов.</span><span class="sxs-lookup"><span data-stu-id="da996-127">If your organization is using a different firewall solution to restrict computers on your network from connecting to the Internet, ensure your client computers are able to access the following [Office 365 URLs and IP address ranges](/microsoftteams/office-365-urls-ip-address-ranges).</span></span> <span data-ttu-id="da996-128">Для этого может потребоваться добавить FQDNs в список допустимой исходящие связи в конфигурации брандмауэра или прокси-инфраструктуры: **\* .api.skype.com,** \* *_.users.storage.live.com_* и **graph.skype.com.**</span><span class="sxs-lookup"><span data-stu-id="da996-128">This may require adding the FQDNs to the outbound allow list in your firewall or proxy infrastructure configuration: **\*.api.skype.com**, \**_.users.storage.live.com_*, and **graph.skype.com**.</span></span> <span data-ttu-id="da996-129">Инструкции по открытием этих портов в брандмауэре можно найти в документации к ним.</span><span class="sxs-lookup"><span data-stu-id="da996-129">For instructions on how to open these ports in your firewall, check the documentation that came with it.</span></span>

    <span data-ttu-id="da996-130">Список всех портов, которые нужно открыть, см. в Office 365 [URL-адреса и диапазоны IP-адресов.](/microsoftteams/office-365-urls-ip-address-ranges)</span><span class="sxs-lookup"><span data-stu-id="da996-130">For a list of all ports you need to open, see [Office 365 URLs and IP address ranges](/microsoftteams/office-365-urls-ip-address-ranges).</span></span>

9. <span data-ttu-id="da996-131">Убедитесь, что администратор организации также следовал этим шагам.</span><span class="sxs-lookup"><span data-stu-id="da996-131">Make sure that the administrator in the organization has also followed these steps.</span></span>

10. <span data-ttu-id="da996-132">**ПОДОЖДИТЕ ДО 24 ЧАСОВ.**</span><span class="sxs-lookup"><span data-stu-id="da996-132">**WAIT UP TO 24 HOURS TO TEST**.</span></span> <span data-ttu-id="da996-133">Изменение параметров внешней связи может занять до 24 часов, чтобы изменения были внесены во все центры обработки данных.</span><span class="sxs-lookup"><span data-stu-id="da996-133">When you change the external communications settings, it can take up to 24 hours for the changes to populate across all the data centers.</span></span>

<span data-ttu-id="da996-134">![](../images/58550720-2a68-42d1-a926-1884e6aeb55c.png)Skype Вы можете разрешить пользователям искать и мгновенные мгновенные данные для всех, кто пользуется бесплатным Skype приложением для потребителей!</span><span class="sxs-lookup"><span data-stu-id="da996-134">![Skype](../images/58550720-2a68-42d1-a926-1884e6aeb55c.png) You can allow your users to search for and IM with everyone who uses Skype, the free consumer app!</span></span> <span data-ttu-id="da996-135">Подробнее см. в [Skype для бизнеса пользователям добавлять Skype контактов.](let-skype-for-business-users-add-skype-contacts.md)</span><span class="sxs-lookup"><span data-stu-id="da996-135">To learn more, see [Let Skype for Business users add Skype contacts](let-skype-for-business-users-add-skype-contacts.md).</span></span>
  
## <a name="test-and-troubleshoot"></a><span data-ttu-id="da996-136">Проверка и устранение неполадок</span><span class="sxs-lookup"><span data-stu-id="da996-136">Test and troubleshoot</span></span>

<span data-ttu-id="da996-137"><a name="bk_preview"> </a></span><span class="sxs-lookup"><span data-stu-id="da996-137"><a name="bk_preview"> </a></span></span>

 <span data-ttu-id="da996-138">**Самая распространенная проблема, с которой сталкиваются люди при настройке связи между предприятием, — это правильное Office 365 [URL-адреса и диапазоны IP-адресов.](/microsoftteams/office-365-urls-ip-address-ranges)**</span><span class="sxs-lookup"><span data-stu-id="da996-138">**The most common issue people encounter when setting up business-to-business communication is getting their [Office 365 URLs and IP address ranges](/microsoftteams/office-365-urls-ip-address-ranges) right.**</span></span>
  
<span data-ttu-id="da996-139">Чтобы проверить настройку, вам нужен контакт Skype для бизнеса, который не работает в брандмауэре вашей компании.</span><span class="sxs-lookup"><span data-stu-id="da996-139">To test your setup, you need a contact on Skype for Business who's not behind your company firewall.</span></span>
  
1. <span data-ttu-id="da996-140">После изменения параметров внешней связи подождите **до 24 ЧАСОВ.**</span><span class="sxs-lookup"><span data-stu-id="da996-140">After you change your external communications settings, **WAIT UP TO 24 HOURS TO TEST**.</span></span>

2. <span data-ttu-id="da996-141">В Skype для бизнеса найщите контакт в Skype для бизнеса и отправьте запрос на чат.</span><span class="sxs-lookup"><span data-stu-id="da996-141">In Skype for Business, search for your contact in Skype for Business, and send a request to chat.</span></span>

    <span data-ttu-id="da996-142">Если вы получаете сообщение о том, что не удалось отправить его из-за политики компании, необходимо перепроверим URL-Office 365 и [диапазоны IP-адресов.](/microsoftteams/office-365-urls-ip-address-ranges)</span><span class="sxs-lookup"><span data-stu-id="da996-142">If you get a message that it couldn't be sent due to company policy, you need to double-check your [Office 365 URLs and IP address ranges](/microsoftteams/office-365-urls-ip-address-ranges).</span></span>

3. <span data-ttu-id="da996-143">Попросите контакт Skype для бизнеса отправить вам запрос на чат.</span><span class="sxs-lookup"><span data-stu-id="da996-143">Ask your Skype for Business contact to send you a request to chat.</span></span> <span data-ttu-id="da996-144">Если вы не получили его запрос, проблема в настройках вашего брандмауэра (предполагается, что он подтвердил корректность настроек своего брандмауэра).</span><span class="sxs-lookup"><span data-stu-id="da996-144">If you don't receive their request, the problem is your firewall settings (assuming they've already confirmed their firewall settings are correct).</span></span>

4. <span data-ttu-id="da996-145">Еще один способ проверить, есть ли проблема в брандмауэре, — перейти в расположение Wi-Fi, не расположенную за брандмауэром, например в кафе.</span><span class="sxs-lookup"><span data-stu-id="da996-145">Another way to test whether the problem is your firewall is to go to a wifi location not behind your firewall, such as a coffee shop.</span></span> <span data-ttu-id="da996-146">Используйте Skype для бизнеса, чтобы отправить контакту запрос на чат.</span><span class="sxs-lookup"><span data-stu-id="da996-146">Use Skype for Business to send a request to your contact to chat.</span></span> <span data-ttu-id="da996-147">Если сообщение там проходит, но не на работе, то вы знаете, что проблема в брандмауэре.</span><span class="sxs-lookup"><span data-stu-id="da996-147">If the message goes through there, but not when you're at work, then you know the problem is your firewall.</span></span>

## <a name="how-to-find-others-and-be-found-when-connecting-with-another-business"></a><span data-ttu-id="da996-148">Как найти других людей и найти их при подключении к другой компании</span><span class="sxs-lookup"><span data-stu-id="da996-148">How to find others, and be found, when connecting with another business</span></span>

<span data-ttu-id="da996-149"><a name="bk_preview"> </a></span><span class="sxs-lookup"><span data-stu-id="da996-149"><a name="bk_preview"> </a></span></span>

<span data-ttu-id="da996-150">После того как вы ввяжете внешнюю связь с другими Skype для бизнеса пользователями, пользователи смогут находить федеративную Skype для бизнеса пользователей, ища их имена для входов.</span><span class="sxs-lookup"><span data-stu-id="da996-150">After you enable external communication with other Skype for Business users, your users can find federated Skype for Business users by searching for their sign-in names.</span></span> <span data-ttu-id="da996-151">Например, Rob@contoso.com.</span><span class="sxs-lookup"><span data-stu-id="da996-151">An example is Rob@contoso.com.</span></span> <span data-ttu-id="da996-152">Затем нужно будет добавить этого человека в свой список контактов.</span><span class="sxs-lookup"><span data-stu-id="da996-152">Then they will need to add the person to their list of contacts.</span></span>
  
![Чтобы найти пользователя в федераированной компании, необходимо найти его адрес электронной почты (как правило, это также имя для регистрации).](../images/20242f85-0636-463b-8df3-1e123784d7fa.png)
  
## <a name="tips-on-setting-up-communications-with-federated-businesses"></a><span data-ttu-id="da996-154">Советы о настройке связи с федеративными организациями</span><span class="sxs-lookup"><span data-stu-id="da996-154">Tips on setting up communications with federated businesses</span></span>

<span data-ttu-id="da996-155"><a name="bk_preview"> </a></span><span class="sxs-lookup"><span data-stu-id="da996-155"><a name="bk_preview"> </a></span></span>

- <span data-ttu-id="da996-156">Чтобы настроить федерацию между Skype для бизнеса 2015 и Skype для бизнеса Online, см. статью Настройка федерации с [Skype для бизнеса Online.](../../SfbHybrid/hybrid/configure-federation-with-skype-for-business-online.md?bc=%2fSkypeForBusiness%2fbreadcrumb%2ftoc.json&toc=%2fSkypeForBusiness%2ftoc.json)</span><span class="sxs-lookup"><span data-stu-id="da996-156">To configure federation between Skype for Business 2015 and Skype for Business Online, see this  article: [Configure federation with Skype for Business Online](../../SfbHybrid/hybrid/configure-federation-with-skype-for-business-online.md?bc=%2fSkypeForBusiness%2fbreadcrumb%2ftoc.json&toc=%2fSkypeForBusiness%2ftoc.json).</span></span>

- <span data-ttu-id="da996-157">Чтобы настроить федерацию между Lync и Skype для бизнеса Online, см. статью Настройка поддержки федерации для [клиента Lync Online.](/previous-versions/office/lync-server-2013/lync-server-2013-configuring-federation-support-for-a-lync-online-customer)</span><span class="sxs-lookup"><span data-stu-id="da996-157">To configure federation between Lync and Skype for Business Online, see this  article: [Configuring Federation Support for a Lync Online Customer](/previous-versions/office/lync-server-2013/lync-server-2013-configuring-federation-support-for-a-lync-online-customer).</span></span>

- <span data-ttu-id="da996-158">Когда два Skype для бизнеса в Microsoft 365 или Office 365 общаются друг с другом в разных доменах, они могут использовать только функции Skype для бизнеса (например, видеособрания или совместный доступ к рабочему столу), которые включены в обеих организациях.</span><span class="sxs-lookup"><span data-stu-id="da996-158">When two Skype for Business users in Microsoft 365 or Office 365 are communicating with each other on separate domains, they can only use Skype for Business features (for example, video conversations or desktop sharing) that are turned on in both organizations.</span></span>

- <span data-ttu-id="da996-159">Если Skype для бизнеса пользователя в вашей организации поставлен на удержание In-Place или для судебного разбирательства, все мгновенные беседы между  ним и другими пользователями Skype для бизнеса или Skype сохраняются в почтовом ящике в элементе с возможностью восстановления.</span><span class="sxs-lookup"><span data-stu-id="da996-159">If a Skype for Business user in your organization is put on an In-Place or Litigation Hold, any IM conversations between that user and other Skype for Business or Skype users will be saved in **Recoverable Items** in their mailbox.</span></span> <span data-ttu-id="da996-160">Эти беседы не сохраняются в **папке** "История бесед" их почтового ящика.</span><span class="sxs-lookup"><span data-stu-id="da996-160">These conversations aren't saved in the **Conversations History** folder in their mailbox.</span></span>

## <a name="turn-off-external-communication-for-specific-individuals"></a><span data-ttu-id="da996-161">Отключение внешней связи для определенных пользователей</span><span class="sxs-lookup"><span data-stu-id="da996-161">Turn off external communication for specific individuals</span></span>

<span data-ttu-id="da996-162"><a name="bk_preview"> </a></span><span class="sxs-lookup"><span data-stu-id="da996-162"><a name="bk_preview"> </a></span></span>

<span data-ttu-id="da996-163">После того как вы включите внешнюю связь для всей компании, вы можете отключить ее только для определенных пользователей.</span><span class="sxs-lookup"><span data-stu-id="da996-163">After you enable external communication for your entire business, you can turn it off for only specific individuals.</span></span>
  
1. <span data-ttu-id="da996-164">Во sign in with your Microsoft 365 or Office 365 admin account.</span><span class="sxs-lookup"><span data-stu-id="da996-164">Sign in with your Microsoft 365 or Office 365 admin account.</span></span>

2. <span data-ttu-id="da996-165">В Центре администрирования перейдите в группу **Пользователи**  >  **Активные пользователи**.</span><span class="sxs-lookup"><span data-stu-id="da996-165">In the admin center, go to **Users** > **Active users**.</span></span>

3. <span data-ttu-id="da996-166">В списке пользователей выберите пользователя, а затем в списке Дополнительные Параметры **щелкните** **Изменить** свойства Skype для бизнеса .</span><span class="sxs-lookup"><span data-stu-id="da996-166">In the list of users, choose the user, and then, under **More Settings**, click **Edit Skype for Business properties**.</span></span>

    ![Выберите Skype для бизнеса](../images/2b0f9a7b-3fee-4f4b-968a-68c429eeb395.png)
  
4. <span data-ttu-id="da996-168">В Центре **администрирования Skype для бизнеса выберите** **Внешняя связь**.</span><span class="sxs-lookup"><span data-stu-id="da996-168">In the **Skype for Business admin center**, choose **External communications**.</span></span>

    <span data-ttu-id="da996-169">На странице **Параметры** будут выбраны все варианты.</span><span class="sxs-lookup"><span data-stu-id="da996-169">On the **Options** page, all of the choices will be selected.</span></span> <span data-ttu-id="da996-170">Очистка сообщений, которые вы хотите отключить.</span><span class="sxs-lookup"><span data-stu-id="da996-170">Clear the communications you want to disable.</span></span> <span data-ttu-id="da996-171">На рисунке ниже показано, что пользователь Jakob сможет общаться с людьми из других доверенных компаний, но не с другими Skype пользователями.</span><span class="sxs-lookup"><span data-stu-id="da996-171">The following image shows that Jakob will be able to communicate with people in other trusted businesses, but not with other Skype users.</span></span>

    ![Выбор внешних контактов](../images/4e546321-a065-48ed-8ac7-1e112a780eab.png)
  
5. <span data-ttu-id="da996-173">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="da996-173">Choose **Save**.</span></span>

> [!NOTE]
> <span data-ttu-id="da996-174">Чтобы изменения вступили в силу, может потребоваться до 24 часов.</span><span class="sxs-lookup"><span data-stu-id="da996-174">You may have to wait for up to 24 hours for your changes to take effect.</span></span>
  
[!INCLUDE [LinkedIn Learning Info](../../common/office/linkedin-learning-info.md)]

## <a name="related-topics"></a><span data-ttu-id="da996-175">См. также</span><span class="sxs-lookup"><span data-stu-id="da996-175">Related topics</span></span>

<span data-ttu-id="da996-176"><a name="bk_preview"> </a></span><span class="sxs-lookup"><span data-stu-id="da996-176"><a name="bk_preview"> </a></span></span>

[<span data-ttu-id="da996-177">Настройка Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="da996-177">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)
  
[<span data-ttu-id="da996-178">Разрешение на добавление контактов Skype пользователям Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="da996-178">Let Skype for Business users add Skype contacts</span></span>](let-skype-for-business-users-add-skype-contacts.md)
