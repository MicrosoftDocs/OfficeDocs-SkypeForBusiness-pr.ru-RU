---
title: 'Lync Server 2013: использование Lync-Skype подключения в качестве конечного пользователя'
description: 'Lync Server 2013: использование Lync-Skype подключения в качестве конечного пользователя.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using Lync-Skype connectivity as an end user
ms:assetid: ad22f731-118c-4349-8790-b1a72941cbdd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn440175(v=OCS.15)
ms:contentKeyID: 57793365
ms.date: 12/29/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dd669a5cf0b15f7fb2d411e4456553f5469d9f96
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48580385"
---
# <a name="using-lync-skype-connectivity-in-lync-server-2013-as-an-end-user"></a><span data-ttu-id="d4b65-103">Использование Lync-Skype подключения в Lync Server 2013 в качестве конечного пользователя</span><span class="sxs-lookup"><span data-stu-id="d4b65-103">Using Lync-Skype connectivity in Lync Server 2013 as an end user</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d4b65-104">_**Последнее изменение темы:** 2016-12-27_</span><span class="sxs-lookup"><span data-stu-id="d4b65-104">_**Topic Last Modified:** 2016-12-27_</span></span>

<span data-ttu-id="d4b65-105">Подключение к Lync-Skype позволяет пользователям Skype и пользователям Lync добавлять друг друга в качестве контактов, обмениваться мгновенными сообщениями Exchange и совершать аудио и видеовызовы.</span><span class="sxs-lookup"><span data-stu-id="d4b65-105">Lync-Skype Connectivity enables Skype users and Lync users to add each other as contacts, exchange instant messages and make audio and video calls.</span></span> <span data-ttu-id="d4b65-106">Когда пользователь Skype добавляет пользователя Lync, пользователь Skype создаст контакт в Skype, содержащий универсальный код ресурса (URI) SIP пользователя Lync.</span><span class="sxs-lookup"><span data-stu-id="d4b65-106">When a Skype user adds a Lync user, a Skype user will create a contact in Skype containing the session initiation protocol (SIP) uniform resource identifier (URI) of the Lync user.</span></span> <span data-ttu-id="d4b65-107">И наоборот, когда пользователь Lync добавляет контакт Skype, пользователь Lync создает контакт в Lync, который будет содержать учетную запись Майкрософт (MSA) пользователя Skype, а не имя пользователя Skype.</span><span class="sxs-lookup"><span data-stu-id="d4b65-107">Conversely, when a Lync user adds a Skype contact, the Lync user will create a contact in Lync that will contain the Microsoft Account (MSA) of the Skype user, and not the Skype user name.</span></span>

<span data-ttu-id="d4b65-108">**Что такое MSA?**</span><span class="sxs-lookup"><span data-stu-id="d4b65-108">**What is an MSA?**</span></span> <span data-ttu-id="d4b65-109">Пользователи Skype должны войти в Skype с помощью учетной записи Майкрософт (ранее именуемой Windows Live ID), чтобы общаться с контактами Lync.</span><span class="sxs-lookup"><span data-stu-id="d4b65-109">Skype users must sign in to Skype with a Microsoft account (previously called Windows Live ID) in order to communicate with Lync contacts.</span></span><span data-ttu-id="d4b65-110">Учетная запись Майкрософт состоит из сочетания адреса электронной почты и пароля, которые можно также использовать для входа в службы, такие как технология хранения данных Microsoft OneDrive, Windows Phone, Microsoft Xbox LIVE Game Service и клиент Microsoft Outlook для обмена сообщениями и совместной работы (и ранее, веб-службы электронной почты Microsoft Hotmail или Windows Live Messenger).</span><span class="sxs-lookup"><span data-stu-id="d4b65-110"> A Microsoft account consists of the combination of an email address and a password, which you can also use to sign in to services such as Microsoft OneDrive storage technology, Windows Phone, Microsoft Xbox LIVE online game service, and Microsoft Outlook messaging and collaboration client (and, previously, Microsoft Hotmail web-based e-mail service or Windows Live Messenger).</span></span><span data-ttu-id="d4b65-111">Если вы используете адрес электронной почты и пароль для входа в эти или другие службы, у вас уже есть учетная запись Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="d4b65-111"> If you use an email address and a password to sign in to these or other services, you already have a Microsoft account.</span></span><span data-ttu-id="d4b65-112">Для получения дополнительных сведений о создании учетной записи Майкрософт посетите страницу регистрации учетной записи Майкрософт по адресу [https://go.microsoft.com/fwlink/p/?LinkId=306061](https://go.microsoft.com/fwlink/p/?linkid=306061) .</span><span class="sxs-lookup"><span data-stu-id="d4b65-112"> For details about creating a Microsoft Account, see the Microsoft account sign-up page at [https://go.microsoft.com/fwlink/p/?LinkId=306061](https://go.microsoft.com/fwlink/p/?linkid=306061).</span></span> <span data-ttu-id="d4b65-113">Вы можете объединить существующую учетную запись Skype с учетной записью Майкрософт для единого входа, в различных приложениях и службах.</span><span class="sxs-lookup"><span data-stu-id="d4b65-113">You can merge your existing Skype account with your Microsoft account for single sign-on, across a variety of applications and services.</span></span> <span data-ttu-id="d4b65-114">После объединения учетной записи пользователь Skype может отправить запрос контакта пользователям Lync.</span><span class="sxs-lookup"><span data-stu-id="d4b65-114">Once the account is merged a Skype user can send a contact request to Lync users.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="d4b65-115">Чтобы пользователи Lync и Skype могли полностью общаться друг с другом, должны выполняться следующие требования:</span><span class="sxs-lookup"><span data-stu-id="d4b65-115">In order for Lync and Skype users to fully communicate with each other, the following requirements must be met:</span></span> 
> <UL>
> <LI>
> <P><span data-ttu-id="d4b65-116">Пользователи Skype должны войти в свой клиент Skype с помощью учетной записи Майкрософт (MSA).</span><span class="sxs-lookup"><span data-stu-id="d4b65-116">Skype users must be logged into their Skype client with a Microsoft Account (MSA).</span></span></P>
> <LI>
> <P><span data-ttu-id="d4b65-117">Пользователям Lync необходимо разрешить доступ к общедоступным службам обмена мгновенными сообщениями с помощью своего администратора Lync.</span><span class="sxs-lookup"><span data-stu-id="d4b65-117">Lync users must be enabled for public IM connectivity by their Lync administrator.</span></span></P>
> <LI>
> <P><span data-ttu-id="d4b65-118">Когда пользователь Skype добавляет контакт Lync, убедитесь, что под именем контакта отображается слово Lync.</span><span class="sxs-lookup"><span data-stu-id="d4b65-118">When a Skype user adds a Lync contact, verify that the word Lync appears below the contact’s name.</span></span> <span data-ttu-id="d4b65-119">Это означает, что найден URI Lync.</span><span class="sxs-lookup"><span data-stu-id="d4b65-119">This indicates that a Lync URI has been found.</span></span></P>
> <LI>
> <P><span data-ttu-id="d4b65-120">Когда пользователь Skype добавляет контакт Lync и нулевые результаты поиска для этого домена Lync, процесс подготовки PIC может быть не завершен или еще не настроен домен Lync.</span><span class="sxs-lookup"><span data-stu-id="d4b65-120">When a Skype user adds a Lync contact and zero search results are returned for that Lync domain, the PIC provisioning process may not have completed, or the Lync domain has not yet been set up.</span></span></P>
> <LI>
> <P><span data-ttu-id="d4b65-121">В зависимости от параметров конфиденциальности пользователей Lync и Skype, обмена мгновенными сообщениями, видео и присутствия могут работать только после того, как новые контакты будут приниматься каждым пользователем.</span><span class="sxs-lookup"><span data-stu-id="d4b65-121">Depending on the privacy settings of the Lync and Skype users, IM, video, and presence may not work until the new contacts are accepted by each user.</span></span></P></LI></UL>



</div>

<span data-ttu-id="d4b65-122">**Добавление контакта Skype в Lync 2013**</span><span class="sxs-lookup"><span data-stu-id="d4b65-122">**To add a Skype contact to Lync 2013**</span></span>

1.  <span data-ttu-id="d4b65-123">В Lync нажмите кнопку **Добавить контакт, а затем добавьте в мою организацию контакт**.</span><span class="sxs-lookup"><span data-stu-id="d4b65-123">From Lync, click **Add a Contact, Add a Contact Not in My Organization**.</span></span>

2.  <span data-ttu-id="d4b65-124">В списке доступных поставщиков контактов выберите **Skype**.</span><span class="sxs-lookup"><span data-stu-id="d4b65-124">From the list of available contact providers, select **Skype**.</span></span>

3.  <span data-ttu-id="d4b65-125">В поле **адрес для обмена мгновенными сообщениями** введите учетную запись Майкрософт (MSA) пользователя Skype.</span><span class="sxs-lookup"><span data-stu-id="d4b65-125">In the **IM Address** field, enter the Microsoft Account (MSA) of the Skype user.</span></span>

4.  <span data-ttu-id="d4b65-126">В раскрывающемся списке **Добавить в группу контактов** выберите группу контактов, в которую нужно добавить пользователя.</span><span class="sxs-lookup"><span data-stu-id="d4b65-126">In the **Add to contact group** dropdown box, select a contact group to add the user to.</span></span>

5.  <span data-ttu-id="d4b65-127">В раскрывающемся списке **установить отношение конфиденциальности** выберите соответствующий параметр контакта и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="d4b65-127">In the **Set privacy relationship** dropdown box, select the appropriate contact setting and then click **OK**.</span></span>

6.  <span data-ttu-id="d4b65-128">Теперь пользователь будет отображаться как контакт в Lync.</span><span class="sxs-lookup"><span data-stu-id="d4b65-128">The user will now appear as a contact in Lync.</span></span> <span data-ttu-id="d4b65-129">Выберите пользователя, щелкните правой кнопкой мыши имя пользователя и выберите команду **просмотреть карточку контакта** , чтобы просмотреть свойства пользователя.</span><span class="sxs-lookup"><span data-stu-id="d4b65-129">Select the user, right-click the user name, and click **See Contact Card** to view the user properties.</span></span> <span data-ttu-id="d4b65-130">Теперь вы можете создать звуковой или видеозвонок с недавно добавленным пользователем Skype.</span><span class="sxs-lookup"><span data-stu-id="d4b65-130">You can now establish an audio or video call with the newly added Skype user.</span></span>

<span data-ttu-id="d4b65-131">Дополнительную информацию о поддержке контактов можно узнать в статье [Добавление контакта в Lync](https://support.office.com/article/add-a-contact-ae55b88d-b9af-48da-bffe-7cc720a5059a).</span><span class="sxs-lookup"><span data-stu-id="d4b65-131">For additional information on support for contacts, see [Add a contact in Lync](https://support.office.com/article/add-a-contact-ae55b88d-b9af-48da-bffe-7cc720a5059a).</span></span>

<span data-ttu-id="d4b65-132">Когда учетная запись Майкрософт пользователя Skype использует собственное доменное имя, например <strong>Bob@contoso.com</strong> , пользователь Lync может добавить эту учетную запись Майкрософт в Lync двумя способами:</span><span class="sxs-lookup"><span data-stu-id="d4b65-132">When a Skype user’s Microsoft account uses a custom domain name, such as <strong>bob@contoso.com</strong> , a Lync user can add that Microsoft account to Lync in two ways:</span></span>

1.  <span data-ttu-id="d4b65-133">Используйте значок **добавления контакта** или</span><span class="sxs-lookup"><span data-stu-id="d4b65-133">Use the **Add a Contact** icon, or</span></span>

2.  <span data-ttu-id="d4b65-134">Используйте поле **найти человека или комнату или наберите номер** .</span><span class="sxs-lookup"><span data-stu-id="d4b65-134">Use the **Find someone or a room, or a dial a number** field.</span></span>

<span data-ttu-id="d4b65-135">В каждом экземпляре пользователь Lync должен ввести электронную почту пользователя Skype в следующем формате: <strong>User (Domain Name) @msn. com</strong> .</span><span class="sxs-lookup"><span data-stu-id="d4b65-135">In each instance, the Lync user must enter the Skype user’s email in the following format: <strong>user(domain name)@msn.com</strong> .</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="d4b65-136">Это действие не является обязательным для учетных записей Майкрософт, использующих следующие имена доменов: <STRONG>@live. com, @hotmail. com или @outlook. com</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="d4b65-136">This step is not required for Microsoft accounts that use the following domain names: <STRONG>@live.com, @hotmail.com or @outlook.com</STRONG>.</span></span> <span data-ttu-id="d4b65-137">Дополнительные сведения о поддерживаемых доменных именах см в разделе <A href="https://support.microsoft.com/kb/897567">Поддерживаемые общедоступные домены обмена мгновенными сообщениями</A>.</span><span class="sxs-lookup"><span data-stu-id="d4b65-137">For more information on supported custom domain names, see <A href="https://support.microsoft.com/kb/897567">Supported public IM domains</A>.</span></span>



</div>

<span data-ttu-id="d4b65-138">**Добавление контакта Skype в Lync при использовании настраиваемого имени домена**</span><span class="sxs-lookup"><span data-stu-id="d4b65-138">**To add a Skype contact to Lync when using a custom domain name**</span></span>

1.  <span data-ttu-id="d4b65-139">В Lync нажмите кнопку **Добавить контакт, а затем добавьте в мою организацию контакт**.</span><span class="sxs-lookup"><span data-stu-id="d4b65-139">From Lync, click **Add a Contact, Add a Contact Not in My Organization**.</span></span>

2.  <span data-ttu-id="d4b65-140">В списке доступных поставщиков контактов выберите **Skype**.</span><span class="sxs-lookup"><span data-stu-id="d4b65-140">From the list of available contact providers, select **Skype**.</span></span>

3.  <span data-ttu-id="d4b65-141">В поле **адрес для обмена мгновенными сообщениями** введите учетную запись Майкрософт (MSA) пользователя Skype в формате <strong>User (доменное имя) @msn. com</strong>.</span><span class="sxs-lookup"><span data-stu-id="d4b65-141">In the **IM Address** field, enter the Microsoft Account (MSA) of the Skype user in the format <strong>user(domain name)@msn.com</strong>.</span></span> <span data-ttu-id="d4b65-142">Таким образом, для пользователя bob@contoso.com запись будет иметь значение <strong> Bob (contoso. com) @msn. com <strong> .</span><span class="sxs-lookup"><span data-stu-id="d4b65-142">So for user bob@contoso.com, the entry would be <strong>bob(contoso.com)@msn.com<strong> .</span></span>

4.  <span data-ttu-id="d4b65-143">В раскрывающемся списке **Добавить в группу контактов** выберите группу контактов, в которую нужно добавить пользователя.</span><span class="sxs-lookup"><span data-stu-id="d4b65-143">In the **Add to contact group** drop-down list box, select a contact group to add the user to.</span></span>

5.  <span data-ttu-id="d4b65-144">В раскрывающемся списке **установить отношение конфиденциальности** выберите соответствующий параметр контакта и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="d4b65-144">In the **Set privacy relationship** drop-down list box, select the appropriate contact setting and then click **OK**.</span></span>

6.  <span data-ttu-id="d4b65-145">Пользователь Lync также может использовать поле **найти кого-либо или комнаты либо набрать номер** в Lync, а также добавить адрес, похожий на приведенный ниже <strong>пользователь (доменное имя) @msn. com</strong> .</span><span class="sxs-lookup"><span data-stu-id="d4b65-145">A Lync user can also use the **Find someone or a room, or dial a number** field in Lync, and add an address that resembles the following <strong>user(domain name)@msn.com</strong> .</span></span> <span data-ttu-id="d4b65-146">Таким образом, для учетной записи Майкрософт bob@contoso.com запись будет иметь значение <strong>Bob (contoso. com) @msn. com</strong> .</span><span class="sxs-lookup"><span data-stu-id="d4b65-146">So for the bob@contoso.com Microsoft account, the entry would be <strong>bob(contoso.com)@msn.com</strong> .</span></span>

7.  <span data-ttu-id="d4b65-147">Выполните шаги 4 и 5, приведенные в этой процедуре, чтобы добавить контакт в группу контактов и выбрать соответствующее отношение конфиденциальности.</span><span class="sxs-lookup"><span data-stu-id="d4b65-147">Follow steps 4 and 5 earlier in this procedure to add the contact to a contact group and to select the appropriate privacy relationship.</span></span>

<span data-ttu-id="d4b65-148">**Добавление контакта Lync в Skype**</span><span class="sxs-lookup"><span data-stu-id="d4b65-148">**To add a Lync contact to Skype**</span></span>

1.  <span data-ttu-id="d4b65-149">Войдите в Skype.</span><span class="sxs-lookup"><span data-stu-id="d4b65-149">Sign in to Skype.</span></span> <span data-ttu-id="d4b65-150">Пользователь Skype должен быть зарегистрирован в своем клиенте Skype с помощью учетной записи Майкрософт (MSA).</span><span class="sxs-lookup"><span data-stu-id="d4b65-150">The Skype user must be logged into their Skype client with a Microsoft Account (MSA).</span></span>

2.  <span data-ttu-id="d4b65-151">Выберите значок Добавить контакты.</span><span class="sxs-lookup"><span data-stu-id="d4b65-151">Select the Add Contacts icon.</span></span>

3.  <span data-ttu-id="d4b65-152">Введите универсальный код ресурса (URI) SIP пользователя Lync.</span><span class="sxs-lookup"><span data-stu-id="d4b65-152">Enter the SIP URI of the Lync user.</span></span> <span data-ttu-id="d4b65-153">Например, bob@contoso.com.</span><span class="sxs-lookup"><span data-stu-id="d4b65-153">For example, bob@contoso.com.</span></span>

4.  <span data-ttu-id="d4b65-154">Когда Skype находит найденные результаты в результатах поиска, найдите слово **Lync** под именем пользователя Lync.</span><span class="sxs-lookup"><span data-stu-id="d4b65-154">When Skype finds the match in the search results, look for the word **Lync** below the Lync user’s name.</span></span> <span data-ttu-id="d4b65-155">Это указывает на то, что Skype успешно размещал URI SIP клиента Lync.</span><span class="sxs-lookup"><span data-stu-id="d4b65-155">This indicates Skype successfully located the Lync client’s SIP URI.</span></span> <span data-ttu-id="d4b65-156">Щелкните имя.</span><span class="sxs-lookup"><span data-stu-id="d4b65-156">Click the name.</span></span>

5.  <span data-ttu-id="d4b65-157">В правом верхнем углу окна щелкните Добавить в контакты.</span><span class="sxs-lookup"><span data-stu-id="d4b65-157">In the top right corner of the window, click Add to Contacts.</span></span>

6.  <span data-ttu-id="d4b65-158">Теперь новый контакт добавляется в список контактов, но вместо значка его состояния отображается вопросительный знак, пока не будет принят ваш запрос.</span><span class="sxs-lookup"><span data-stu-id="d4b65-158">The new contact is now added to your contact list, but you’ll see a question mark instead of their status icon until they accept your request.</span></span> <span data-ttu-id="d4b65-159">Когда новый контакт принимает ваш запрос, вы сможете видеть, когда он находится в сети, инициировать обмен мгновенными сообщениями и совершать аудио-и видеовызовы.</span><span class="sxs-lookup"><span data-stu-id="d4b65-159">When your new contact accepts your request, you will be able to see when they are online, initiate IM conversations, and make audio and video calls.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="d4b65-160">Администратор Lync Server должен настроить параметры политики пользователя Lync, чтобы разрешить входящие запросы.</span><span class="sxs-lookup"><span data-stu-id="d4b65-160">The Lync Server administrator must configure the Lync user’s policy settings to allow incoming requests.</span></span> <span data-ttu-id="d4b65-161">В противном случае пользователь Lync не будет получать запросы контакта от пользователя Skype.</span><span class="sxs-lookup"><span data-stu-id="d4b65-161">If not, the Lync user will not receive contact requests from the Skype user.</span></span> <span data-ttu-id="d4b65-162">В зависимости от конфигурации параметров политики пользователя Lync запрос на добавление пользователя Skype будет отображаться на <STRONG>новой</STRONG> вкладке клиента Lync. Чтобы начать общение с пользователем Skype, пользователь Lync должен добавить пользователя Skype в список "Избранное" или список контактов.</span><span class="sxs-lookup"><span data-stu-id="d4b65-162">Depending on the configuration of the Lync user’s policy settings, the request to add the Skype user will appear on the Lync client’s <STRONG>New</STRONG> tab. To begin communicating with the Skype user, the Lync user must add the Skype user to either the Favorites list or a contact list.</span></span> <span data-ttu-id="d4b65-163">На изображении ниже показано расположение <STRONG>новой</STRONG> вкладки в клиенте Lync.</span><span class="sxs-lookup"><span data-stu-id="d4b65-163">The image below shows the location of the <STRONG>New</STRONG> tab in the Lync client.</span></span>

    
    </div>

<span data-ttu-id="d4b65-164">Пользователь Lync должен настроить оповещения Lync, чтобы убедиться, что запросы, отправляемые пользователем Skype, отображаются и могут обнаруживаться пользователем Lync.</span><span class="sxs-lookup"><span data-stu-id="d4b65-164">A Lync user must configure Lync alerts to ensure that requests sent from a Skype user appear and are discoverable by the Lync user.</span></span> <span data-ttu-id="d4b65-165">Чтобы настроить оповещения Lync, выполните приведенную ниже процедуру.</span><span class="sxs-lookup"><span data-stu-id="d4b65-165">To configure Lync alerts, complete the procedure that follows.</span></span>

<span data-ttu-id="d4b65-166">**Настройка оповещений Lync**</span><span class="sxs-lookup"><span data-stu-id="d4b65-166">**To configure Lync Alerts**</span></span>

1.  <span data-ttu-id="d4b65-167">В клиенте Lync щелкните значок **Параметры** .</span><span class="sxs-lookup"><span data-stu-id="d4b65-167">From the Lync client, click the **Options** icon.</span></span>

2.  <span data-ttu-id="d4b65-168">Выберите **оповещения**.</span><span class="sxs-lookup"><span data-stu-id="d4b65-168">Select **Alerts**.</span></span>

3.  <span data-ttu-id="d4b65-169">В разделе **Общие оповещения**установите флажок **сообщить, когда кто-то добавляет меня в свой список контактов**.</span><span class="sxs-lookup"><span data-stu-id="d4b65-169">Under **General alerts**, check **Tell me when someone adds me to his or her contact list**.</span></span>

4.  <span data-ttu-id="d4b65-170">В разделе **Контакты, не использующие Lync**выберите **Разрешить приглашения, но блокировать все остальные виды связи**.</span><span class="sxs-lookup"><span data-stu-id="d4b65-170">Under **Contacts not using Lync**, select **Allow invites but block all other communications**.</span></span>

5.  <span data-ttu-id="d4b65-171">Нажмите кнопку **ОК** , чтобы закрыть окно Параметры.</span><span class="sxs-lookup"><span data-stu-id="d4b65-171">Click **OK** to close the Options window.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

