---
title: 'Часто задаваемые вопросы: подготовка Lync Server для подключения Skype'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: 'Frequently Asked Questions: Provisioning Lync Server for Skype connectivity'
ms:assetid: 4d1b2bfc-780b-4b8c-afd5-11c2e59203b5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn440172(v=OCS.15)
ms:contentKeyID: 57793362
ms.date: 12/29/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 690eb5631b57a88d207816a01c887c1f94c0eeb2
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42044051"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="frequently-asked-questions-provisioning-lync-server-2013-for-skype-connectivity"></a><span data-ttu-id="8dd4b-102">Вопросы и ответы: подготовка Lync Server 2013 для подключения к Skype</span><span class="sxs-lookup"><span data-stu-id="8dd4b-102">Frequently Asked Questions: Provisioning Lync Server 2013 for Skype connectivity</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8dd4b-103">_**Последнее изменение темы:** 2019-03-22_</span><span class="sxs-lookup"><span data-stu-id="8dd4b-103">_**Topic Last Modified:** 2019-03-22_</span></span>

<span data-ttu-id="8dd4b-104">Начиная с апреля 2019, мы будем останавливать сбор и хранение контактных данных для клиентов, подготовленных для Федерации Skype через веб-сайт pic.lync.com.</span><span class="sxs-lookup"><span data-stu-id="8dd4b-104">Beginning in April 2019, we will stop the collection and retention of contact information for customers who are provisioned for Skype Federation via the pic.lync.com website.</span></span> <span data-ttu-id="8dd4b-105">Это изменение состоит в том, чтобы система подготовки pic.lync.com придерживается политик конфиденциальности корпорации Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="8dd4b-105">This change is being made to ensure that the pic.lync.com provisioning system adheres to Microsoft privacy policies.</span></span> 
 
<span data-ttu-id="8dd4b-106">После того как это изменение будет продолжено, мы больше не сможете предоставлять обновления электронной почты по незавершенным изменениям подготовки.</span><span class="sxs-lookup"><span data-stu-id="8dd4b-106">Once this change goes live, we will no longer be able to provide email updates on pending provisioning changes.</span></span> <span data-ttu-id="8dd4b-107">Изменения подготовки PIC обычно завершаются в течение 24-48 часов после ввода.</span><span class="sxs-lookup"><span data-stu-id="8dd4b-107">PIC provisioning changes typically complete within 24-48 hours after being entered.</span></span> <span data-ttu-id="8dd4b-108">Если у вас по-прежнему возникают проблемы с федерациями Skype 48 часов после отправки запроса на подготовку, обратитесь в службу технической поддержки Майкрософт для дальнейшего изучения.</span><span class="sxs-lookup"><span data-stu-id="8dd4b-108">If you are still experiencing Skype Federation issues 48 hours after submitting a provisioning request, please engage Microsoft Technical Support to investigate further.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="8dd4b-109">В рамках этого изменения все ранее введенные контактные данные будут удалены из нашей системы на конец апреля 2019.</span><span class="sxs-lookup"><span data-stu-id="8dd4b-109">As part of this change, all previously entered contact information will be purged from our system by the end of April, 2019.</span></span>


<span data-ttu-id="8dd4b-110">**Вопрос: какие функции поддерживаются в Microsoft Lync и Skype?**</span><span class="sxs-lookup"><span data-stu-id="8dd4b-110">**Q: What features are supported between Microsoft Lync and Skype?**</span></span>

<span data-ttu-id="8dd4b-111">**A:** С помощью Skype в составе семьи вы можете открыть новые возможности для расширения сценариев единой системы обмена сообщениями на сотни миллионов людей, использующих Skype.</span><span class="sxs-lookup"><span data-stu-id="8dd4b-111">**A:** With Skype now part of the Microsoft family, new possibilities open up for extending unified communications scenarios to the hundreds of millions of people who use Skype.</span></span> <span data-ttu-id="8dd4b-112">Это сочетание позволит клиентам Lync подключаться и совместно работать с поставщиками, клиентами и партнерами, которые полагается на полноту Lync и доступ к Skype.</span><span class="sxs-lookup"><span data-stu-id="8dd4b-112">This combination will enable Lync customers to connect and collaborate with suppliers, customers, and partners, relying on the richness of Lync and the reach of Skype.</span></span>

  - <span data-ttu-id="8dd4b-113">Обмен мгновенными сообщениями и аудио-и видеовызовами — Федеративные вызовы и обмен мгновенными сообщениями между Lync и пользователями Skype</span><span class="sxs-lookup"><span data-stu-id="8dd4b-113">Instant Message and Audio and Video Calls—Federated audio and video calling and instant messaging between Lync and Skype users</span></span>

  - <span data-ttu-id="8dd4b-114">Общий доступ к присутствию — сведения о присутствии Exchange между федеративными контактами</span><span class="sxs-lookup"><span data-stu-id="8dd4b-114">Presence Sharing— Exchange presence information between federated contacts</span></span>

  - <span data-ttu-id="8dd4b-115">Простое администрирование — параметры и элементы управления для настройки федеративных коммуникаций в соответствии с политиками и стандартами Организации.</span><span class="sxs-lookup"><span data-stu-id="8dd4b-115">Simple Administration—Settings and controls to configure federated communications in accordance with your organization’s policies and standards</span></span>

<span data-ttu-id="8dd4b-116">**В. как определить, как подключаться к развертыванию Lync с помощью Skype?**</span><span class="sxs-lookup"><span data-stu-id="8dd4b-116">**Q: How do I qualify to connect my Lync deployment with Skype?**</span></span>

<span data-ttu-id="8dd4b-117">**A:** Лицензировано для подключения Skype, если у вас есть:</span><span class="sxs-lookup"><span data-stu-id="8dd4b-117">**A:** You are licensed for Skype connectivity if you have either:</span></span>

  - <span data-ttu-id="8dd4b-118">Lync Server (2010 или 2013) и стандартные клиентские лицензии Lync Server (CAL) (CAL), 2010 или 2013) для пользователей и/или устройств в Организации, которые будут подключаться к Skype.</span><span class="sxs-lookup"><span data-stu-id="8dd4b-118">Lync Server (2010 or 2013) plus Lync Server Standard Client Access Licenses (“CALs”; 2010 or 2013) for the users and/or devices in your organization that will connect to Skype.</span></span> 

  - <span data-ttu-id="8dd4b-119">Lync Online (как отдельные лицензии или в составе пакета Office 365).</span><span class="sxs-lookup"><span data-stu-id="8dd4b-119">Lync Online (as standalone licenses or as part of an Office 365 suite).</span></span><span data-ttu-id="8dd4b-120">Тем не менее, эта служба (pic.lync.com) предназначена только для подготовки Lync Server и гибридного развертывания Lync Server и Lync Online.</span><span class="sxs-lookup"><span data-stu-id="8dd4b-120">  However, this service (pic.lync.com) is only for provisioning Lync Server and hybrid Lync Server and Lync Online deployments.</span></span><span data-ttu-id="8dd4b-121">Подготовка Lync Online PIC выполняется на панели управления Lync Online (ЛОКП).</span><span class="sxs-lookup"><span data-stu-id="8dd4b-121">  Lync Online PIC provisioning is done in Lync Online Control Panel (LOCP).</span></span>

<span data-ttu-id="8dd4b-122">**В. что необходимо пользователям Lync для подключения к контактам Skype?**</span><span class="sxs-lookup"><span data-stu-id="8dd4b-122">**Q: What must Lync end users do to connect to Skype contacts?**</span></span>

<span data-ttu-id="8dd4b-123">**A:** После активации домена и включения функций администратором Lync пользователи в Lync могут добавлять контакты Skype в свои списки контактов в клиенте Lync.</span><span class="sxs-lookup"><span data-stu-id="8dd4b-123">**A:** After a domain is activated and the features are enabled by an organization’s Lync administrator, Lync users can add Skype contacts to their contact lists within the Lync client.</span></span>

<span data-ttu-id="8dd4b-124">**В. что необходимо пользователям Skype для подключения к контактам Lync?**</span><span class="sxs-lookup"><span data-stu-id="8dd4b-124">**Q: What must Skype end users do to connect to Lync contacts?**</span></span>

<span data-ttu-id="8dd4b-125">**A:** Все пользователи Skype, желающие подключиться к пользователю Lync, должны иметь учетную запись Майкрософт, связанную со своими идентификаторами Skype, и входить в систему с помощью учетной записи Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="8dd4b-125">**A:** All Skype users wishing to connect to a Lync user must have a Microsoft Account associated with their Skype IDs and sign in using the Microsoft Account.</span></span><span data-ttu-id="8dd4b-126">Эту функцию можно включить в клиенте Skype.</span><span class="sxs-lookup"><span data-stu-id="8dd4b-126">  This can be enabled within the Skype client.</span></span>

<span data-ttu-id="8dd4b-127">**В.: включена ли Федерация с Windows Live?**</span><span class="sxs-lookup"><span data-stu-id="8dd4b-127">**Q: Is federation with Windows Live still available?**</span></span>

<span data-ttu-id="8dd4b-128">**A:** Начиная с октября, 2012, корпорация Майкрософт приступила к использованию Windows Live Messenger (ВЛМ), которые пользователи переходят в Skype, EN-Route, чтобы приступить к отснятию ВЛМ.</span><span class="sxs-lookup"><span data-stu-id="8dd4b-128">**A:** Beginning in October, 2012, Microsoft started helping Windows Live Messenger (WLM) users move to Skype, en route to eventually retiring WLM.</span></span><span data-ttu-id="8dd4b-129">Lync продолжит поддерживать Федерацию с ВЛМ, пока ВЛМ находится на рынке, но никакие дополнительные активации доменов Windows Live не будут разрешены.</span><span class="sxs-lookup"><span data-stu-id="8dd4b-129"> Lync will continue to support federation with WLM as long as WLM is in market, but no additional Windows Live domain activations will be allowed.</span></span><span data-ttu-id="8dd4b-130">Перемещение пользователей ВЛМ включено в Skype 6,0 для Mac и Windows (выпущено 25 октября 2012), что позволяет войти с помощью учетной записи Майкрософт (например, с теми же учетными данными, что и ВЛМ).</span><span class="sxs-lookup"><span data-stu-id="8dd4b-130"> The movement of WLM users is enabled by the Skype 6.0 for Mac and Windows (released October 25, 2012) which allows signing in with a Microsoft Account (i.e., the same credentials as WLM).</span></span> <span data-ttu-id="8dd4b-131">После того как вы просто входите в Skype, ВЛМs Lists автоматически заполняются в Skype, и пользователи могут использовать расширенные возможности общения в Skype, такие как вызов стационарные и мобильные устройства, общий доступ к экрану, видеозвонок в группе и поддержка широкого спектра различные устройства.</span><span class="sxs-lookup"><span data-stu-id="8dd4b-131">After simply signing in to Skype, WLM buddy lists automatically populate into Skype, and users can take advantage of Skype’s expanded communication capabilities such as calling landlines and mobiles, screen sharing, group video calling, and support for a wide variety of devices.</span></span><span data-ttu-id="8dd4b-132">Кроме того, Федеративные контакты Lync пользователей ВЛМ следуют переходу в Skype с остальными своими списками контактов, а обмен мгновенными сообщениями между Skype и Lync для этих контактов будет доступен сразу.</span><span class="sxs-lookup"><span data-stu-id="8dd4b-132"> Moreover, WLM users’ federated Lync contacts follow the transition into Skype with the rest of their buddy lists, and IM between Skype and Lync for these contacts will be available immediately.</span></span> <span data-ttu-id="8dd4b-133">Пользователям Lync не требуется выполнять какие-либо действия для обеспечения бесперебойной работы службы.</span><span class="sxs-lookup"><span data-stu-id="8dd4b-133">Lync customers do not need to do anything to enable this continuity of service.</span></span>

<span data-ttu-id="8dd4b-134">**Вопрос: существует ли Федерация с\! Yahoo или AOL?**</span><span class="sxs-lookup"><span data-stu-id="8dd4b-134">**Q: Is federation with Yahoo\! or AOL still available?**</span></span>

<span data-ttu-id="8dd4b-135">**A:** Нет.</span><span class="sxs-lookup"><span data-stu-id="8dd4b-135">**A:** No.</span></span> <span data-ttu-id="8dd4b-136">Федерация с Yahoo\!</span><span class="sxs-lookup"><span data-stu-id="8dd4b-136">Federation with Yahoo\!</span></span> <span data-ttu-id="8dd4b-137">и AOL в зависимости от поддержки Yahoo\!</span><span class="sxs-lookup"><span data-stu-id="8dd4b-137">and AOL were contingent upon support from Yahoo\!</span></span> <span data-ttu-id="8dd4b-138">и AOL.</span><span class="sxs-lookup"><span data-stu-id="8dd4b-138">and AOL.</span></span><span data-ttu-id="8dd4b-139">Как для Yahoo, так и для\!</span><span class="sxs-lookup"><span data-stu-id="8dd4b-139"> For both Yahoo\!</span></span> <span data-ttu-id="8dd4b-140">и AOL служба заканчивается 30 июня 2014 г.</span><span class="sxs-lookup"><span data-stu-id="8dd4b-140">and AOL, the service ended on June 30, 2014.</span></span> 

<span data-ttu-id="8dd4b-141">**Вопрос: можно ли выполнить пробное подключение к Skype перед покупкой Lync?**</span><span class="sxs-lookup"><span data-stu-id="8dd4b-141">**Q: Can I trial Skype connectivity before purchasing Lync?**</span></span>

<span data-ttu-id="8dd4b-142">**A:** Подключение Skype не предоставляется на основе пробной версии.</span><span class="sxs-lookup"><span data-stu-id="8dd4b-142">**A:** Skype connectivity is not offered on a trial basis.</span></span> <span data-ttu-id="8dd4b-143">Вместо пробной версии клиенты Lync с подходящими лицензиями могут просто зарегистрироваться в службе для тестирования.</span><span class="sxs-lookup"><span data-stu-id="8dd4b-143">In place of a trial, Lync customers with eligible licenses are encouraged to simply sign up for the service to test.</span></span>

<span data-ttu-id="8dd4b-144">**Вопрос: какие сведения необходимы для подготовки?**</span><span class="sxs-lookup"><span data-stu-id="8dd4b-144">**Q: What information is required for provisioning?**</span></span>

<span data-ttu-id="8dd4b-145">**A:** Чтобы отправить запрос на подготовку в квалифицированной лицензии, вам потребуются следующие компоненты:</span><span class="sxs-lookup"><span data-stu-id="8dd4b-145">**A:** To submit a provisioning request under a qualified license, you need the following:</span></span>

  - <span data-ttu-id="8dd4b-146">Номер соглашения корпорации Майкрософт:</span><span class="sxs-lookup"><span data-stu-id="8dd4b-146">Microsoft agreement number:</span></span>
    
      - <span data-ttu-id="8dd4b-147">Поддержка корпоративного лицензирования Майкрософт: номер соглашения о корпоративном лицензировании Майкрософт</span><span class="sxs-lookup"><span data-stu-id="8dd4b-147">Microsoft Volume Licensing Support: Microsoft Volume Licensing Agreement number</span></span>
    
      - <span data-ttu-id="8dd4b-148">Сеть партнера Майкрософт: идентификатор партнера в головном офисе</span><span class="sxs-lookup"><span data-stu-id="8dd4b-148">Microsoft Partner Network: Headquarter partner ID</span></span>
    
      - <span data-ttu-id="8dd4b-149">Лицензионное соглашение для поставщика услуг: первоначальный регистрационный номер</span><span class="sxs-lookup"><span data-stu-id="8dd4b-149">Service Provider Licensing Agreement: Initial enrollment number</span></span>
    
      - <span data-ttu-id="8dd4b-150">High Volume Services: номер регистрации продукта</span><span class="sxs-lookup"><span data-stu-id="8dd4b-150">High Volume Services: Product enrollment number</span></span>

  - <span data-ttu-id="8dd4b-151">Полные доменные имена (FQDN) для службы пограничного доступа.</span><span class="sxs-lookup"><span data-stu-id="8dd4b-151">Fully qualified domain names (FQDNs) for the Access Edge service.</span></span>
    
      - <span data-ttu-id="8dd4b-152">Необходимо указать полное доменное имя по крайней мере одной пограничной службы доступа.</span><span class="sxs-lookup"><span data-stu-id="8dd4b-152">FQDN for at least one Access Edge service is required.</span></span>
    
      - <span data-ttu-id="8dd4b-153">Если в Организации имеется несколько серверов, на которых работает пограничная служба доступа, укажите полные доменные имена для каждой дополнительной службы пограничного доступа.</span><span class="sxs-lookup"><span data-stu-id="8dd4b-153">If your organization has more than one server running the Access Edge service, specify the FQDNs for each additional Access Edge service.</span></span> <span data-ttu-id="8dd4b-154">Важно! Если вы ранее указали полное доменное имя для службы пограничного доступа и хотите изменить его, подготовка к изменению может занять несколько дней, что может привести к нарушению работы службы.</span><span class="sxs-lookup"><span data-stu-id="8dd4b-154">Important: If you previously specified an FQDN for the Access Edge service and want to change it, provisioning for the change can take several days to complete and can result in a disruption in service.</span></span> <span data-ttu-id="8dd4b-155">Чтобы предотвратить перерыв в обслуживании, мы рекомендуем поддерживать ранее указанное полное доменное имя службы пограничного доступа.</span><span class="sxs-lookup"><span data-stu-id="8dd4b-155">To prevent service disruption, we recommend that you maintain the previously specified FQDN of the Access Edge service.</span></span>

  - <span data-ttu-id="8dd4b-156">Домены протокола SIP.</span><span class="sxs-lookup"><span data-stu-id="8dd4b-156">Session Initiation Protocol (SIP) domain(s).</span></span> <span data-ttu-id="8dd4b-157">Это доменный суффикс URI SIP, который пользователи в настоящее время используют для обмена мгновенными сообщениями.</span><span class="sxs-lookup"><span data-stu-id="8dd4b-157">This is the domain suffix of the SIP URI that users currently use for instant messaging.</span></span> <span data-ttu-id="8dd4b-158">Если в Организации имеется несколько доменов SIP, укажите суффикс домена для каждого домена, используемого для обмена мгновенными сообщениями.</span><span class="sxs-lookup"><span data-stu-id="8dd4b-158">If your organization has more than one SIP domain, specify the domain suffix for each domain used for instant messaging.</span></span> <span data-ttu-id="8dd4b-159">Например, для user1@contoso.com укажите contoso.com для домена SIP; в user1@example.fabrikam.com укажите example.fabrikam.com в качестве домена SIP.</span><span class="sxs-lookup"><span data-stu-id="8dd4b-159">For example, for user1@contoso.com, specify contoso.com for the SIP domain; for user1@example.fabrikam.com, specify example.fabrikam.com as the SIP domain.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="8dd4b-160">Укажите только суффикс домена для домена SIP.</span><span class="sxs-lookup"><span data-stu-id="8dd4b-160">Specify only the domain suffix for the SIP domain.</span></span> <span data-ttu-id="8dd4b-161">Не указывайте полные доменные имена, в том числе полное доменное имя для службы пограничного доступа, для домена SIP.</span><span class="sxs-lookup"><span data-stu-id="8dd4b-161">Do not specify any FQDNs, including the FQDN for the Access Edge service, for the SIP domain.</span></span>

    
    </div>

  - <span data-ttu-id="8dd4b-162">Контактные данные.</span><span class="sxs-lookup"><span data-stu-id="8dd4b-162">Contact information.</span></span> <span data-ttu-id="8dd4b-163">Укажите адрес электронной почты администратора каждого указанного SIP домена SIP.</span><span class="sxs-lookup"><span data-stu-id="8dd4b-163">Specify an e-mail address for the administrator of each SIP domain that you specify.</span></span>

<span data-ttu-id="8dd4b-164">**В. как включить подключение Lync — Skype в сценарии с разделенным доменом?**</span><span class="sxs-lookup"><span data-stu-id="8dd4b-164">**Q: How do I enable Lync-Skype Connectivity in a split-domain scenario?**</span></span>

<span data-ttu-id="8dd4b-165">**A:** Если вы используете Lync Online 2013 и Lync Server с локальным доменом с разделенным доменом (с пользователями в Интернете и локально с использованием того же домена SIP), включите Подключение Lync-Skype, выполнив эти два действия в следующем порядке.</span><span class="sxs-lookup"><span data-stu-id="8dd4b-165">**A:** If you have a Lync Online 2013 and Lync Server on-premise split-domain scenario (with users on both online and on-premise using the same SIP domain), enable Lync-Skype Connectivity by doing these two steps in the following order</span></span>

1.  <span data-ttu-id="8dd4b-166">Настройка локального подключения Lync — Skype, как описано в руководстве по подготовке PIC.</span><span class="sxs-lookup"><span data-stu-id="8dd4b-166">Set up on-premise Lync-Skype Connectivity as explained in the PIC Provisioning Guide.</span></span>

2.  <span data-ttu-id="8dd4b-167">Подождите, пока не появится подтверждение того, что ваш домен был подготовлен корпорацией Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="8dd4b-167">Wait until you see confirmation that your domain has been provisioned by Microsoft.</span></span>

3.  <span data-ttu-id="8dd4b-168">После просмотра подтверждения используйте центр администрирования Lync, чтобы включить "внешние коммуникации".</span><span class="sxs-lookup"><span data-stu-id="8dd4b-168">After you see the confirmation, use the Lync admin center to turn on “external communications”.</span></span> <span data-ttu-id="8dd4b-169">Дополнительные сведения см.[http://office.microsoft.com/support/configure-external-communications-HA102817865.aspx?CTT=5\&origin=HA102817356](http://office.microsoft.com/support/configure-external-communications-ha102817865.aspx?ctt=5%26origin=ha102817356)</span><span class="sxs-lookup"><span data-stu-id="8dd4b-169">For more information, see [http://office.microsoft.com/support/configure-external-communications-HA102817865.aspx?CTT=5\&origin=HA102817356](http://office.microsoft.com/support/configure-external-communications-ha102817865.aspx?ctt=5%26origin=ha102817356)</span></span>

<span data-ttu-id="8dd4b-170">Этот порядок важен.</span><span class="sxs-lookup"><span data-stu-id="8dd4b-170">This order is important.</span></span><span data-ttu-id="8dd4b-171">Перед включением связи в Lync Online необходимо настроить локальное подключение.</span><span class="sxs-lookup"><span data-stu-id="8dd4b-171">  You must set up the on-premise connectivity before you enable the communications in Lync Online.</span></span> <span data-ttu-id="8dd4b-172">Если порядок обратной, сведения, введенные для локального размещения, не <https://pic.lync.com> будут проходить через.</span><span class="sxs-lookup"><span data-stu-id="8dd4b-172">If the order is reversed, the information entered for on-premise in <https://pic.lync.com> will not go through.</span></span> <span data-ttu-id="8dd4b-173">Если вы уже настроили Lync Online для внешних коммуникаций с этим доменом, необходимо отключить его, подождать 24 часа и затем снова начать работу <https://pic.lync.com> , а затем включить внешние коммуникации для Lync Online.</span><span class="sxs-lookup"><span data-stu-id="8dd4b-173">If you have already set up Lync Online for external communications with this domain, you must turn it off, wait for 24 hours, and start again, first by entering your on-premise information at <https://pic.lync.com> and then turning on external communications for Lync Online.</span></span>

<span data-ttu-id="8dd4b-174">**Вопрос: можно ли подготовить к подключению Skype несколько полных доменных имен пограничной службы доступа?**</span><span class="sxs-lookup"><span data-stu-id="8dd4b-174">**Q: Can I provision multiple Access Edge service FQDNs for Skype connectivity?**</span></span>

<span data-ttu-id="8dd4b-175">**A:** Для одного или нескольких доменов можно подготовить только одно полное доменное имя доступа.</span><span class="sxs-lookup"><span data-stu-id="8dd4b-175">**A:** You can provision only one access edge FQDN for one or more domains.</span></span> <span data-ttu-id="8dd4b-176">Можно подготовить несколько полных доменных имен пограничного доступа, до 10 для каждого запроса, если они имеют разные домены.</span><span class="sxs-lookup"><span data-stu-id="8dd4b-176">You can provision multiple access edge FQDNs, up to 10 per request, if they have distinct domains.</span></span>

<span data-ttu-id="8dd4b-177">**В: можно ли получить список адресов электронной почты Майкрософт, которые вы ищете в Организации, запрашивающей подготовку?**</span><span class="sxs-lookup"><span data-stu-id="8dd4b-177">**Q: Can I obtain the list of Microsoft Account e-mail addresses that you find for the organization requesting provisioning?**</span></span>

<span data-ttu-id="8dd4b-178">**A:** Нет.</span><span class="sxs-lookup"><span data-stu-id="8dd4b-178">**A:** No.</span></span> <span data-ttu-id="8dd4b-179">Эти адреса считаются личными сведениями и не являются общими.</span><span class="sxs-lookup"><span data-stu-id="8dd4b-179">These addresses are considered personally identifiable information and are not shared.</span></span>

<span data-ttu-id="8dd4b-180">**В. как добавить контакт Windows Live Messenger с ИДЕНТИФИКАТОРом, который содержит домен, отличный от того, что поддерживается Windows Live?**</span><span class="sxs-lookup"><span data-stu-id="8dd4b-180">**Q: How do I add a Windows Live Messenger contact that has an ID containing a domain other than those supported by Windows Live?**</span></span>

<span data-ttu-id="8dd4b-181">**A:** Если вы добавляете пользователя Windows Live Messenger с учетной записью или идентификатором в домене, отличном от Windows Live, введите адрес в следующем формате \<: имя\>пользователя\<(доменное имя\>) @msn. com \<, где\> доменное имя — это доменное имя в адресе электронной почты пользователя.</span><span class="sxs-lookup"><span data-stu-id="8dd4b-181">**A:** If you are adding a Windows Live Messenger user with an account or ID with a non-Windows Live domain, enter the address in the following format: \<user name\>(\<domain name\>)@msn.com, where \<domain name\> is the domain name in the e-mail address of the user.</span></span> <span data-ttu-id="8dd4b-182">Например, если вы хотите добавить ted@contoso.com, используйте следующий формат: ", contoso. com) @msn. com.</span><span class="sxs-lookup"><span data-stu-id="8dd4b-182">For example, if you wanted to add ted@contoso.com, you would use the following format: ted(contoso.com)@msn.com.</span></span> <span data-ttu-id="8dd4b-183">Список доменов, администрируемых службой Windows Live, приведен в разделе Поддерживаемые домены в разделе "известные проблемы, возникающие при работе с общедоступной службой обмена мгновенными сообщениями после установки пакета обновления 1 http://support.microsoft.com/?kbid=897567(SP1) для Live Communications Server с пакетом обновления 1 (SP1).</span><span class="sxs-lookup"><span data-stu-id="8dd4b-183">For a list of domains that are administered by Windows Live, see the Supported Domains section in “Known Issues That Occur with Public Instant Messaging After You Install Live Communications Server Service Pack 1” at http://support.microsoft.com/?kbid=897567.</span></span>

<span data-ttu-id="8dd4b-184">**Вопрос: сколько времени занимает процесс подготовки?**</span><span class="sxs-lookup"><span data-stu-id="8dd4b-184">**Q: How long does the provisioning process take?**</span></span>

<span data-ttu-id="8dd4b-185">**A:** Подготовка может занять до 30 дней.</span><span class="sxs-lookup"><span data-stu-id="8dd4b-185">**A:** Provisioning can take up to 30 days.</span></span>

<span data-ttu-id="8dd4b-186">**В. Как узнать, когда будет завершена подготовка?**</span><span class="sxs-lookup"><span data-stu-id="8dd4b-186">**Q: How will I know when provisioning is complete?**</span></span>

<span data-ttu-id="8dd4b-187">**A:** Корпорация Майкрософт будет отправлять уведомления по электронной почте о завершении подготовки.</span><span class="sxs-lookup"><span data-stu-id="8dd4b-187">**A:** Microsoft will send e-mail notification when provisioning is complete.</span></span>

<span data-ttu-id="8dd4b-188">**Вопрос: как обновить сведения о конфигурации или контактах, которые я отправил?**</span><span class="sxs-lookup"><span data-stu-id="8dd4b-188">**Q: How can I update the configuration or contact details that I submit?**</span></span>

<span data-ttu-id="8dd4b-189">**A:** Вы можете обновить сведения на том же веб-сайте, который использовался для запроса подготовки, после завершения подготовки.</span><span class="sxs-lookup"><span data-stu-id="8dd4b-189">**A:** You can update your information at the same web site that you used to request provisioning, after provisioning is complete.</span></span> <span data-ttu-id="8dd4b-190">Введите свой номер соглашения и нажмите кнопку Обновить службу.</span><span class="sxs-lookup"><span data-stu-id="8dd4b-190">Enter your agreement number, and then click Update service.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

