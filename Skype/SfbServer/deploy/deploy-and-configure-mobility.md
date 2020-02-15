---
title: Развертывание и настройка мобильной работы для Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 8ec6197a-3d1e-4b42-9465-564044cdab1a
description: В этой статье описано, как настроить существующую установку Skype для бизнеса Server для использования службы Mobility Service, позволяя мобильным устройствам использовать функции мобильной работы Skype для бизнеса Server.
ms.openlocfilehash: 457eeff39c87f20326d64cc5227745b43e0af5f8
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42029070"
---
# <a name="deploy-and-configure-mobility-for-skype-for-business-server"></a><span data-ttu-id="5db54-103">Развертывание и настройка мобильной работы для Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="5db54-103">Deploy and Configure Mobility for Skype for Business Server</span></span>  
 
<span data-ttu-id="5db54-104">В этой статье описано, как настроить существующую установку Skype для бизнеса Server для использования службы Mobility Service, позволяя мобильным устройствам использовать функции мобильной работы Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="5db54-104">This article will walk you through the steps to configure an existing Skype for Business Server installation to use the Mobility service, allowing your mobile devices to be able to take advantage of Skype for Business Server Mobility features.</span></span>
  
<span data-ttu-id="5db54-105">Получив статью [о планировании мобильной работы для Skype для бизнеса Server](../plan-your-deployment/mobility.md) , необходимо выполнить указанные ниже действия, чтобы развернуть мобильную среду в среде Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="5db54-105">Having reviewed the [Plan for Mobility for Skype for Business Server](../plan-your-deployment/mobility.md) article, you should be ready to proceed with the steps below to deploy Mobility into your Skype for Business Server environment.</span></span> <span data-ttu-id="5db54-106">Для этого необходимо выполнить указанные ниже действия (в этом случае список разрешений включается в эту таблицу).</span><span class="sxs-lookup"><span data-stu-id="5db54-106">The steps are as follows (and we're including in this table a permissions list):</span></span>
  
|<span data-ttu-id="5db54-107">**Этап**</span><span class="sxs-lookup"><span data-stu-id="5db54-107">**Phase**</span></span>|<span data-ttu-id="5db54-108">**Разрешения**</span><span class="sxs-lookup"><span data-stu-id="5db54-108">**Permissions**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="5db54-109">Создание записей DNS</span><span class="sxs-lookup"><span data-stu-id="5db54-109">Create DNS records</span></span>](deploy-and-configure-mobility.md#CreateDNSRec) <br/> |<span data-ttu-id="5db54-110">Администраторы домена</span><span class="sxs-lookup"><span data-stu-id="5db54-110">Domain Admins</span></span>  <br/> <span data-ttu-id="5db54-111">DNSAdmins</span><span class="sxs-lookup"><span data-stu-id="5db54-111">DNSAdmins</span></span>  <br/> |
|[<span data-ttu-id="5db54-112">Изменение сертификатов</span><span class="sxs-lookup"><span data-stu-id="5db54-112">Modify certificates</span></span>](deploy-and-configure-mobility.md#ModCerts) <br/> |<span data-ttu-id="5db54-113">Локальный администратор</span><span class="sxs-lookup"><span data-stu-id="5db54-113">Local Administrator</span></span>  <br/> |
|[<span data-ttu-id="5db54-114">Настройка обратного прокси-сервера</span><span class="sxs-lookup"><span data-stu-id="5db54-114">Configure the reverse proxy</span></span>](deploy-and-configure-mobility.md#ConfigRP) <br/> |<span data-ttu-id="5db54-115">Локальный администратор</span><span class="sxs-lookup"><span data-stu-id="5db54-115">Local Administrator</span></span>  <br/> |
|[<span data-ttu-id="5db54-116">Настройка службы автообнаружения для мобильной работы с гибридными развертываниями</span><span class="sxs-lookup"><span data-stu-id="5db54-116">Configure Autodiscover for Mobility with hybrid deployments</span></span>](deploy-and-configure-mobility.md#ConfigAutoD) <br/> |<span data-ttu-id="5db54-117">Администраторы домена</span><span class="sxs-lookup"><span data-stu-id="5db54-117">Domain Admins</span></span>  <br/> |
|[<span data-ttu-id="5db54-118">Тестирование развертывания мобильности</span><span class="sxs-lookup"><span data-stu-id="5db54-118">Test your Mobility deployment</span></span>](deploy-and-configure-mobility.md#TestMobility) <br/> |<span data-ttu-id="5db54-119">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="5db54-119">CsAdministrator</span></span>  <br/> |
|[<span data-ttu-id="5db54-120">Настройка для использования push-уведомлений</span><span class="sxs-lookup"><span data-stu-id="5db54-120">Configure for push notifications</span></span>](deploy-and-configure-mobility.md#ConfigPush) <br/> |<span data-ttu-id="5db54-121">RtcUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="5db54-121">RtcUniversalServerAdmins</span></span>  <br/> |
|[<span data-ttu-id="5db54-122">Настройка политики мобильности</span><span class="sxs-lookup"><span data-stu-id="5db54-122">Configure Mobility policy</span></span>](deploy-and-configure-mobility.md#ConfigMob) <br/> |<span data-ttu-id="5db54-123">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="5db54-123">CsAdministrator</span></span>  <br/> |
   
<span data-ttu-id="5db54-124">В следующих разделах содержатся действия, которые предполагают, что вы прочитали раздел Planning.</span><span class="sxs-lookup"><span data-stu-id="5db54-124">All the following sections contain steps that assume you've read the Planning topic.</span></span> <span data-ttu-id="5db54-125">Если что-то не так, вы можете бесплатно извлекать информацию.</span><span class="sxs-lookup"><span data-stu-id="5db54-125">If anything's confusing you, feel free to check out the information there.</span></span>

> [!NOTE]
> <span data-ttu-id="5db54-126">MCX (служба Mobility Service) поддержка устаревших мобильных клиентов больше недоступна в Skype для бизнеса Server 2019.</span><span class="sxs-lookup"><span data-stu-id="5db54-126">MCX (Mobility Service) support for legacy mobile clients is no longer available in Skype for Business Server 2019.</span></span> <span data-ttu-id="5db54-127">Все текущие мобильные клиенты Skype для бизнеса уже используют веб-API объединенных коммуникаций (UCWA), чтобы поддерживать обмен мгновенными сообщениями, сведения о присутствии и контакты.</span><span class="sxs-lookup"><span data-stu-id="5db54-127">All current Skype for Business mobile clients already use Unified Communications Web API (UCWA) to support instant messaging (IM), presence, and contacts.</span></span> <span data-ttu-id="5db54-128">Пользователям прежних версий клиентов, использующих MCX, необходимо выполнить обновление до текущего клиента.</span><span class="sxs-lookup"><span data-stu-id="5db54-128">Users with legacy clients using MCX will need to upgrade to a current client.</span></span>
  
## <a name="create-dns-records"></a><span data-ttu-id="5db54-129">Создание записей DNS</span><span class="sxs-lookup"><span data-stu-id="5db54-129">Create DNS records</span></span>
<span data-ttu-id="5db54-130"><a name="CreateDNSRec"> </a></span><span class="sxs-lookup"><span data-stu-id="5db54-130"><a name="CreateDNSRec"> </a></span></span>

<span data-ttu-id="5db54-131">Они уже могут применяться в среде Skype для бизнеса Server, но для работы с автообнаружением необходимо создать следующие записи:</span><span class="sxs-lookup"><span data-stu-id="5db54-131">You may already have these as part of your Skype for Business Server environment, but you do need to create the following records for Autodiscovery to work:</span></span>
  
- <span data-ttu-id="5db54-132">Внутренняя запись DNS для поддержки мобильных пользователей, подключающихся из сети Организации.</span><span class="sxs-lookup"><span data-stu-id="5db54-132">An internal DNS record to support mobile users who're connecting from within your organization's network.</span></span>
    
- <span data-ttu-id="5db54-133">Внешняя (или общедоступная) запись DNS для поддержки мобильных пользователей, подключающихся из-за пределами сети Организации.</span><span class="sxs-lookup"><span data-stu-id="5db54-133">An external (or public) DNS record to support mobile users who're connecting from outside your organization's network.</span></span>
    
<span data-ttu-id="5db54-134">Эти записи могут быть либо именами (узла), либо записями CNAME (их не нужно делать, мы просто включая все необходимые действия).</span><span class="sxs-lookup"><span data-stu-id="5db54-134">These records can be either A (host) names or CNAME records (you don't have to make both, we're just including the steps for everything here).</span></span>
  
### <a name="create-an-internal-dns-cname-record"></a><span data-ttu-id="5db54-135">Создание внутренней записи CNAME DNS</span><span class="sxs-lookup"><span data-stu-id="5db54-135">Create an internal DNS CNAME record</span></span>

1. <span data-ttu-id="5db54-136">Войдите на DNS-сервер в сети, который является членом группы **администраторов домена** или группы **DnsAdmins** .</span><span class="sxs-lookup"><span data-stu-id="5db54-136">Log into a DNS server in your network that's either a member of the **Domain Admins** group or the **DnsAdmins** group.</span></span>
    
2. <span data-ttu-id="5db54-137">Нажмите кнопку **Пуск**, выберите пункт **Администрирование** (возможно, вам потребуется **найти** его, если он не входит в меню "Пуск"), а затем нажмите кнопку **DNS** , чтобы открыть оснастку администрирования DNS.</span><span class="sxs-lookup"><span data-stu-id="5db54-137">Click **Start**, Choose **Administrative Tools** (you may need to **Search** for it if it's not an option off the Start menu), and then click **DNS** to open the DNS administrative snap-in.</span></span>
    
3. <span data-ttu-id="5db54-138">В левой области окна консоли необходимо перейти к домену, который находится дома, на серверы переднего плана Skype для бизнеса Server, а также развернуть **зоны прямого просмотра** .</span><span class="sxs-lookup"><span data-stu-id="5db54-138">In the left-hand pane of the console window, you'll need to go to the domain that's home to your Skype for Business Server's Front End Servers, and expand the **Forward Lookup Zones** there.</span></span>
    
4. <span data-ttu-id="5db54-139">Проведите несколько минут, чтобы узнать, какие из следующих компонентов:</span><span class="sxs-lookup"><span data-stu-id="5db54-139">Take a moment to see which of the following you have:</span></span>
    
   - <span data-ttu-id="5db54-140">Любые записи A или AAAA для узла сервера переднего плана (стандартного или корпоративного) или пула переднего плана.</span><span class="sxs-lookup"><span data-stu-id="5db54-140">Any host A or AAAA records for your Front End Server (Standard or Enterprise) or Front End pool(s).</span></span>
    
   - <span data-ttu-id="5db54-141">Записи A или AAAA для директора или пула директоров (Необязательная конфигурация, которая может возникнуть в развертывании).</span><span class="sxs-lookup"><span data-stu-id="5db54-141">Any host A or AAAA records for a Director or Director pool (an optional configuration you may have in your deployment).</span></span>
    
5. <span data-ttu-id="5db54-142">После этого щелкните правой кнопкой мыши имя домена SIP и выберите в меню пункт **создать псевдоним (CNAME)** .</span><span class="sxs-lookup"><span data-stu-id="5db54-142">Once you've noted this, right-click your SIP domain name, and then choose **New Alias (CNAME)** from the menu.</span></span>
    
6. <span data-ttu-id="5db54-143">В текстовом поле **псевдоним** введите lyncdiscoverinternal в качестве имени узла для внутреннего URL-адреса службы автообнаружения.</span><span class="sxs-lookup"><span data-stu-id="5db54-143">In the **Alias name** textbox, type lyncdiscoverinternal for your host name, for the internal Autodiscover service URL.</span></span>
    
7. <span data-ttu-id="5db54-144">В **полном доменном имени (полное доменное имя для целевого узла**) необходимо ввести полное доменное имя внутренних веб-служб для пула переднего плана (или одного сервера переднего плана или директора), указанного на шаге 4 выше.</span><span class="sxs-lookup"><span data-stu-id="5db54-144">In the **Fully qualified domain name (FQDN for target host**, you'll need to type or browse to the internal Web Services FQDN for your Front End pool (or single Front End Server, or Director pool or Director), identified in step 4 above.</span></span> <span data-ttu-id="5db54-145">Нажмите кнопку ОК при вводе.</span><span class="sxs-lookup"><span data-stu-id="5db54-145">Click OK when this is entered.</span></span>
    
8. <span data-ttu-id="5db54-146">Вам потребуется создать новую запись CNAME автообнаружения в зоне прямого просмотра для каждого домена SIP, поддерживаемого в среде Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="5db54-146">You'll need to create a new Autodiscover CNAME record in the forward lookup zone for each SIP domain supported in your Skype for Business Server environment.</span></span>
    
### <a name="create-an-external-dns-cname-record"></a><span data-ttu-id="5db54-147">Создание внешней записи CNAME DNS</span><span class="sxs-lookup"><span data-stu-id="5db54-147">Create an external DNS CNAME record</span></span>

1. <span data-ttu-id="5db54-148">Эти действия являются общими, так как мы не можем определить, какой общедоступный поставщик DNS вы можете использовать, но мы хотим помочь вам. Выполните вход в общедоступный поставщик DNS с учетной записью, которая будет иметь возможность делать новые записи DNS.</span><span class="sxs-lookup"><span data-stu-id="5db54-148">These steps are generic, because we can't tell what public DNS provider you might be using, but we still want to help you out. Please log into your public DNS provider with an account that will be able to make new DNS records there.</span></span>
    
2. <span data-ttu-id="5db54-149">На данный момент времени для Skype для бизнеса Server уже должен существовать домен SIP.</span><span class="sxs-lookup"><span data-stu-id="5db54-149">At this point in time, a SIP domain should already exist there for Skype for Business Server.</span></span> <span data-ttu-id="5db54-150">Разверните **зону прямого просмотра** для этого домена SIP или откройте ее другим способом.</span><span class="sxs-lookup"><span data-stu-id="5db54-150">Expand the **Forward Lookup Zone** for this SIP domain, or otherwise open it up.</span></span>
    
3. <span data-ttu-id="5db54-151">Проведите несколько минут, чтобы узнать, какие из следующих компонентов:</span><span class="sxs-lookup"><span data-stu-id="5db54-151">Take a moment to see which of the following you have:</span></span>
    
   - <span data-ttu-id="5db54-152">Любые записи A или AAAA для узла сервера переднего плана (стандартного или корпоративного) или пула переднего плана.</span><span class="sxs-lookup"><span data-stu-id="5db54-152">Any host A or AAAA records for your Front End Server (Standard or Enterprise) or Front End pool(s).</span></span>
    
   - <span data-ttu-id="5db54-153">Записи A или AAAA для директора или пула директоров (Необязательная конфигурация, которая может возникнуть в развертывании).</span><span class="sxs-lookup"><span data-stu-id="5db54-153">Any host A or AAAA records for a Director or Director pool (an optional configuration you may have in your deployment).</span></span>
    
4. <span data-ttu-id="5db54-154">После получения этих сведений вы сможете выбрать вариант для создания **нового псевдонима (CNAME)**.</span><span class="sxs-lookup"><span data-stu-id="5db54-154">Once you have that information, you should be able to select an option for creating a **New Alias (CNAME)**.</span></span>
    
5. <span data-ttu-id="5db54-155">Теперь вы можете ввести **имя псевдонима**, вам нужно ввести lyncdiscover здесь для внешнего URL-адреса службы автообнаружения.</span><span class="sxs-lookup"><span data-stu-id="5db54-155">Now you should be able to enter an **Alias Name**, you need to enter lyncdiscover here for the external Autodiscover service URL.</span></span>
    
6. <span data-ttu-id="5db54-156">Далее должна быть область для ввода в **полное доменное имя конечного узла**, для этого потребуется указать полное доменное имя для пула переднего плана (или одного сервера переднего плана или директора), указанного на шаге 3.</span><span class="sxs-lookup"><span data-stu-id="5db54-156">Next there should be an area to enter in a **FQDN for target host**, this will need to be the FQDN for your Front End pool (or single Front End Server, or Director pool or Director), identified in step 3 above.</span></span>
    
7. <span data-ttu-id="5db54-157">Возможно, вам потребуется сохранить эту ссылку или создать дополнительные записи CNAME в зоне прямого просмотра для каждого домена SIP в среде Skype для бизнеса Server, но после того как все будет готово, сохраните работу.</span><span class="sxs-lookup"><span data-stu-id="5db54-157">You may need to save here, or if you need to create additional CNAME records in the forward lookup zone of each SIP domain in your Skype for Business Server environment, you should do that, but once you're ready, save your work.</span></span>
    
### <a name="create-an-internal-dns-a-record"></a><span data-ttu-id="5db54-158">Создание записи A внутренней DNS</span><span class="sxs-lookup"><span data-stu-id="5db54-158">Create an internal DNS A record</span></span>

1. <span data-ttu-id="5db54-159">Войдите на DNS-сервер в сети, который является членом группы **администраторов домена** или группы **DnsAdmins** .</span><span class="sxs-lookup"><span data-stu-id="5db54-159">Log into a DNS server in your network that's either a member of the **Domain Admins** group or the **DnsAdmins** group.</span></span>
    
2. <span data-ttu-id="5db54-160">Нажмите кнопку **Пуск**, выберите пункт **Администрирование** (возможно, вам потребуется **найти** его, если он не входит в меню "Пуск"), а затем нажмите кнопку **DNS** , чтобы открыть оснастку администрирования DNS.</span><span class="sxs-lookup"><span data-stu-id="5db54-160">Click **Start**, Choose **Administrative Tools** (you may need to **Search** for it if it's not an option off the Start menu), and then click **DNS** to open the DNS administrative snap-in.</span></span>
    
3. <span data-ttu-id="5db54-161">В левой области окна консоли необходимо перейти к домену, который находится дома, на серверы переднего плана Skype для бизнеса Server, а также развернуть **зоны прямого просмотра** .</span><span class="sxs-lookup"><span data-stu-id="5db54-161">In the left-hand pane of the console window, you'll need to go to the domain that's home to your Skype for Business Server's Front End Servers, and expand the **Forward Lookup Zones** there.</span></span>
    
4. <span data-ttu-id="5db54-162">Проведите несколько минут, чтобы узнать, какие из следующих компонентов:</span><span class="sxs-lookup"><span data-stu-id="5db54-162">Take a moment to see which of the following you have:</span></span>
    
   - <span data-ttu-id="5db54-163">Любые записи A или AAAA для узла сервера переднего плана (стандартного или корпоративного) или пула переднего плана.</span><span class="sxs-lookup"><span data-stu-id="5db54-163">Any host A or AAAA records for your Front End Server (Standard or Enterprise) or Front End pool(s).</span></span>
    
   - <span data-ttu-id="5db54-164">Записи A или AAAA для директора или пула директоров (Необязательная конфигурация, которая может возникнуть в развертывании).</span><span class="sxs-lookup"><span data-stu-id="5db54-164">Any host A or AAAA records for a Director or Director pool (an optional configuration you may have in your deployment).</span></span>
    
5. <span data-ttu-id="5db54-165">После этого щелкните правой кнопкой мыши имя домена SIP и выберите в меню пункт **создать узел (A или AAAA)** .</span><span class="sxs-lookup"><span data-stu-id="5db54-165">Once you've noted this, right-click your SIP domain name, and then choose **New Host (A or AAAA)** from the menu.</span></span>
    
6. <span data-ttu-id="5db54-166">В текстовом поле **имя** введите lyncdiscoverinternal для имени узла для внутреннего URL-адреса службы автообнаружения.</span><span class="sxs-lookup"><span data-stu-id="5db54-166">In the **Name** textbox, type lyncdiscoverinternal for your host name, for the internal Autodiscover service URL.</span></span>
    
7. <span data-ttu-id="5db54-167">В текстовом поле **IP-адрес** введите IP-адрес внутренних веб-служб для пула переднего плана (или одного сервера переднего плана или директора), указанного на шаге 4 выше.</span><span class="sxs-lookup"><span data-stu-id="5db54-167">In the **IP Address** textbox, type the internal Web Services IP address for your Front End pool (or single Front End Server, or Director pool or Director), identified in step 4 above.</span></span>
    
8. <span data-ttu-id="5db54-168">По завершении нажмите кнопку **Добавить узел**, а затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="5db54-168">When this is done, click **Add Host**, and then click **OK**.</span></span>
    
9. <span data-ttu-id="5db54-169">Вам потребуется создать новые записи A или AAAA для автообнаружения в зоне прямого просмотра для каждого домена SIP, поддерживаемого в среде Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="5db54-169">You'll need to create a new Autodiscover A or AAAA records in the forward lookup zone for each SIP domain supported in your Skype for Business Server environment.</span></span> <span data-ttu-id="5db54-170">Для этого повторите шаги 6-8 столько раз, сколько необходимо.</span><span class="sxs-lookup"><span data-stu-id="5db54-170">To do this, repeat steps 6-8 as many times as needed.</span></span>
    
10. <span data-ttu-id="5db54-171">Когда все будет готово, нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="5db54-171">When you're done, click **Done**.</span></span>
    
### <a name="create-an-external-dns-a-record"></a><span data-ttu-id="5db54-172">Создание записи A внешней DNS</span><span class="sxs-lookup"><span data-stu-id="5db54-172">Create an external DNS A record</span></span>

1. <span data-ttu-id="5db54-173">Эти действия являются общими, так как мы не можем определить, какой общедоступный поставщик DNS вы можете использовать, но мы хотим помочь вам. Выполните вход в общедоступный поставщик DNS с учетной записью, которая будет иметь возможность делать новые записи DNS.</span><span class="sxs-lookup"><span data-stu-id="5db54-173">These steps are generic, because we can't tell what public DNS provider you might be using, but we still want to help you out. Please log into your public DNS provider with an account that will be able to make new DNS records there.</span></span>
    
2. <span data-ttu-id="5db54-174">На данный момент времени для Skype для бизнеса Server уже должен существовать домен SIP.</span><span class="sxs-lookup"><span data-stu-id="5db54-174">At this point in time, a SIP domain should already exist there for Skype for Business Server.</span></span> <span data-ttu-id="5db54-175">Разверните **зону прямого просмотра** для этого домена SIP или откройте ее другим способом.</span><span class="sxs-lookup"><span data-stu-id="5db54-175">Expand the **Forward Lookup Zone** for this SIP domain, or otherwise open it up.</span></span>
    
3. <span data-ttu-id="5db54-176">Проведите несколько минут, чтобы узнать, какие из следующих компонентов:</span><span class="sxs-lookup"><span data-stu-id="5db54-176">Take a moment to see which of the following you have:</span></span>
    
   - <span data-ttu-id="5db54-177">Любые записи A или AAAA для узла сервера переднего плана (стандартного или корпоративного) или пула переднего плана.</span><span class="sxs-lookup"><span data-stu-id="5db54-177">Any host A or AAAA records for your Front End Server (Standard or Enterprise) or Front End pool(s).</span></span>
    
   - <span data-ttu-id="5db54-178">Записи A или AAAA для директора или пула директоров (Необязательная конфигурация, которая может возникнуть в развертывании).</span><span class="sxs-lookup"><span data-stu-id="5db54-178">Any host A or AAAA records for a Director or Director pool (an optional configuration you may have in your deployment).</span></span>
    
4. <span data-ttu-id="5db54-179">После получения этих сведений вы сможете выбрать вариант для создания **нового узла a или AAAA**.</span><span class="sxs-lookup"><span data-stu-id="5db54-179">Once you have that information, you should be able to select an option for creating a **New Host A or AAAA**.</span></span>
    
5. <span data-ttu-id="5db54-180">Теперь вы можете ввести **имя**, введите lyncdiscover здесь для внешнего URL-адреса службы автообнаружения.</span><span class="sxs-lookup"><span data-stu-id="5db54-180">Now you should be able to enter a **Name**, you need to enter lyncdiscover here for the external Autodiscover service URL.</span></span>
    
6. <span data-ttu-id="5db54-181">Далее должна быть область для ввода в **IP-адреса**, она должна быть IP-адресом для пула переднего плана (или одного сервера переднего плана или директора), указанного на шаге 3.</span><span class="sxs-lookup"><span data-stu-id="5db54-181">Next there should be an area to enter in a **IP Addresss**, this will need to be the IP for your Front End pool (or single Front End Server, or Director pool or Director), identified in step 3 above.</span></span>
    
7. <span data-ttu-id="5db54-182">Вам может потребоваться сохранить эту ссылку или создать дополнительные записи A или AAAA в зоне прямого просмотра для каждого домена SIP в среде Skype для бизнеса Server, но после того как все будет готово, сохраните работу.</span><span class="sxs-lookup"><span data-stu-id="5db54-182">You may need to save here, or if you need to create additional A or AAAA records in the forward lookup zone of each SIP domain for your Skype for Business Server environment, you should do that, but once you're ready, save your work.</span></span>
    
## <a name="modify-certificates"></a><span data-ttu-id="5db54-183">Изменение сертификатов</span><span class="sxs-lookup"><span data-stu-id="5db54-183">Modify certificates</span></span>
<span data-ttu-id="5db54-184"><a name="ModCerts"> </a></span><span class="sxs-lookup"><span data-stu-id="5db54-184"><a name="ModCerts"> </a></span></span>

<span data-ttu-id="5db54-185">Если у вас есть вопросы по планированию сертификатов, мы задокументировани, что в нашем [плане для статьи по мобильности в Skype для бизнеса Server](../plan-your-deployment/mobility.md) .</span><span class="sxs-lookup"><span data-stu-id="5db54-185">If you have questions about Planning around certificates, we've documented that in our [Plan for Mobility for Skype for Business Server](../plan-your-deployment/mobility.md) article.</span></span> <span data-ttu-id="5db54-186">После того как вы проверили это, мы поможем вам выполнить следующие действия:</span><span class="sxs-lookup"><span data-stu-id="5db54-186">Once you've reviewed that, we'll walk you through the following:</span></span>
  
- <span data-ttu-id="5db54-187">Требуются ли новые сертификаты?</span><span class="sxs-lookup"><span data-stu-id="5db54-187">Do I need new certificates?</span></span>
    
- <span data-ttu-id="5db54-188">Запрос новых сертификатов из центра сертификации (CA).</span><span class="sxs-lookup"><span data-stu-id="5db54-188">Requesting new certificates from your Certificate Authority (CA).</span></span>
    
- <span data-ttu-id="5db54-189">Обновление сертификатов на месте с заменой с помощью PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5db54-189">Updating your in-place certificates with the replacements using PowerShell.</span></span>
    
- <span data-ttu-id="5db54-190">Проверка сертификатов с помощью оснастки "сертификаты" в консоли управления (MMC).</span><span class="sxs-lookup"><span data-stu-id="5db54-190">Checking the certificates using the Certificates snapin in the Microsoft Management Console (MMC).</span></span>
    
### <a name="do-i-need-new-certificates"></a><span data-ttu-id="5db54-191">Требуются ли новые сертификаты?</span><span class="sxs-lookup"><span data-stu-id="5db54-191">Do I need new certificates?</span></span>

1. <span data-ttu-id="5db54-192">Для начала вам может потребоваться проверить, какие сертификаты имеются на месте, а какие — нет, а также указать, есть ли у них нужные записи.</span><span class="sxs-lookup"><span data-stu-id="5db54-192">First, you may need to check and see what certificates are in-place, and whether or not they have the entries you need.</span></span> <span data-ttu-id="5db54-193">Для этого необходимо выполнить вход в Skype для бизнеса Server с учетной записью, которая является локальным администратором.</span><span class="sxs-lookup"><span data-stu-id="5db54-193">To do that, you'll need to log into your Skype for Business Server with an account that's a local Administrator.</span></span> <span data-ttu-id="5db54-194">Эта учетная запись может также требовать права на выдающий центр сертификации (CA), чтобы выполнить некоторые из этих действий.</span><span class="sxs-lookup"><span data-stu-id="5db54-194">This account may also need to have rights to the issuing Certificate Authority (CA), for some of these steps.</span></span>
    
2. <span data-ttu-id="5db54-195">Откройте командную консоль Skype для бизнеса Server (можно использовать поиск, чтобы найти ее, если она не закреплена в меню "Пуск" или панели задач).</span><span class="sxs-lookup"><span data-stu-id="5db54-195">Open the Skype for Business Server Management Shell (you can use Search to find it if you don't have it pinned to your Start menu or task bar).</span></span>
    
3. <span data-ttu-id="5db54-196">Необходимо знать, какие сертификаты были назначены, прежде чем вы попробуете добавить обновленный сертификат.</span><span class="sxs-lookup"><span data-stu-id="5db54-196">It's going to be essential for you to know what certificates have been assigned before you try adding an updated certificate.</span></span> <span data-ttu-id="5db54-197">В командной команде введите:</span><span class="sxs-lookup"><span data-stu-id="5db54-197">So at the command, type:</span></span>
    
   ```powershell
   Get-CsCertificate
   ```

4. <span data-ttu-id="5db54-198">Сведения, приведенные в шаге 3, будут уникальными.</span><span class="sxs-lookup"><span data-stu-id="5db54-198">The information from Step 3 will be unique to you.</span></span> <span data-ttu-id="5db54-199">Чтобы определить, есть ли один сертификат, назначенный для нескольких вещей, или у вас есть другой сертификат, назначенный для разных компонентов.</span><span class="sxs-lookup"><span data-stu-id="5db54-199">You need to look it over to determine if you have a single certificate that's been assigned for multiple things, or whether you have a different certificate assigned for the different components that need them.</span></span> <span data-ttu-id="5db54-200">С **помощью параметра Use** вы узнаете, как будет использоваться сертификат, а параметр **Thumbprint** будет указывать на то, что все это один и тот же сертификат, или несколько сертификатов.</span><span class="sxs-lookup"><span data-stu-id="5db54-200">The **Use** parameter will tell you how a certificate's being used, and the **Thumbprint** parameter will tell you if it's all the same certificate, or multiple certs.</span></span>
    
5. <span data-ttu-id="5db54-201">Если у вас есть записи SAN, Рекомендуемые в нашем разделе планирования, это хорошо.</span><span class="sxs-lookup"><span data-stu-id="5db54-201">If you have the SAN entries recommended in our Planning section, you're good.</span></span> <span data-ttu-id="5db54-202">В противном случае вам потребуется запросить новый сертификат или несколько сертификатов (в зависимости от конфигурации) от вашего центра сертификации.</span><span class="sxs-lookup"><span data-stu-id="5db54-202">If not, you'll need to request a new certificate, or multiple certificates (depending on your configuration) from your Certificate Authority.</span></span>
    
### <a name="request-a-new-certificate-or-certificates-from-your-certificate-authority-ca"></a><span data-ttu-id="5db54-203">Запрос нового сертификата или сертификатов из центра сертификации (ЦС)</span><span class="sxs-lookup"><span data-stu-id="5db54-203">Request a new certificate, or certificates, from your Certificate Authority (CA)</span></span>

1. <span data-ttu-id="5db54-204">После проверки наличия записей в сети SAN вы знаете, что у вас есть **один сертификат** (после выполнения описанных выше действий), и вы узнали, что у вас нет необходимых записей.</span><span class="sxs-lookup"><span data-stu-id="5db54-204">After you've checked to see what SAN entries you have, you know you have a **single certificate** (after checking via the steps above), and you learned you don't have all the entries you need.</span></span> <span data-ttu-id="5db54-205">В ЦС должен быть создан новый запрос на сертификат.</span><span class="sxs-lookup"><span data-stu-id="5db54-205">A new certificate request needs to be made to your CA.</span></span> <span data-ttu-id="5db54-206">Откройте PowerShell Skype для бизнеса Server:</span><span class="sxs-lookup"><span data-stu-id="5db54-206">Open your Skype for Business Server PowerShell:</span></span>
    
   - <span data-ttu-id="5db54-207">Для отсутствующей сети хранения данных службы автообнаружения (замените параметр-CA на собственный путь к центру сертификации):</span><span class="sxs-lookup"><span data-stu-id="5db54-207">For a missing Autodiscover Service SAN (replacing the -Ca parameter with your own Certificate Authority path):</span></span>
    
   ```powershell
   Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -Ca dc\myca -AllSipDomain -verbose
   ```

   - <span data-ttu-id="5db54-208">Теперь, если у вас несколько доменов SIP, вы не можете использовать параметр Аллсипдомаин, как в приведенном выше примере.</span><span class="sxs-lookup"><span data-stu-id="5db54-208">Now, if you have multiple SIP domains, you can't use the AllSipDomain parameter as in the example above.</span></span> <span data-ttu-id="5db54-209">Вместо этого необходимо использовать параметр DomainName.</span><span class="sxs-lookup"><span data-stu-id="5db54-209">You'll need to use the DomainName parameter instead.</span></span> <span data-ttu-id="5db54-210">При использовании параметра имя_домена необходимо определить полное доменное имя для записей lyncdiscoverinternal и lyncdiscover.</span><span class="sxs-lookup"><span data-stu-id="5db54-210">And when you use the DomainName parameter, you've got to define the FQDN for the lyncdiscoverinternal and lyncdiscover records.</span></span> <span data-ttu-id="5db54-211">В качестве примера можно привести (заменив параметр-CA на свой собственный путь к центру сертификации):</span><span class="sxs-lookup"><span data-stu-id="5db54-211">An example would be (replacing the -Ca parameter with your own Certificate Authority path):</span></span>
    
   ```powershell
   Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -Ca dc\myca -DomainName "LyncdiscoverInternal.contoso.com, LyncdiscoverInternal.contoso.net" -verbose
   ```

2. <span data-ttu-id="5db54-212">После того как вы проверили наличие записей в сети SAN, вы обнаружили **несколько сертификатов** , у которых нет нужных записей.</span><span class="sxs-lookup"><span data-stu-id="5db54-212">Or, after you've checked to see what SAN entries you have, you found you have **multiple certificates** that don't have all the entries you need.</span></span> <span data-ttu-id="5db54-213">В ЦС должен быть создан новый запрос на сертификат.</span><span class="sxs-lookup"><span data-stu-id="5db54-213">A new certificate request needs to be made to your CA.</span></span> <span data-ttu-id="5db54-214">Откройте PowerShell Skype для бизнеса Server:</span><span class="sxs-lookup"><span data-stu-id="5db54-214">Open your Skype for Business Server PowerShell:</span></span>
    
   - <span data-ttu-id="5db54-215">Для отсутствующей сети хранения данных службы автообнаружения (замените параметр-CA на собственный путь к центру сертификации):</span><span class="sxs-lookup"><span data-stu-id="5db54-215">For a missing Autodiscover Service SAN (replacing the -Ca parameter with your own Certificate Authority path):</span></span>
    
   ```powershell
   Request-CsCertificate -New -Type WebServicesInternal -Ca dc\myca -AllSipDomain -verbose
   ```

   - <span data-ttu-id="5db54-216">Теперь, если у вас несколько доменов SIP, вы не можете использовать параметр Аллсипдомаин, как в приведенном выше примере.</span><span class="sxs-lookup"><span data-stu-id="5db54-216">Now, if you have multiple SIP domains, you can't use the AllSipDomain parameter as in the example above.</span></span> <span data-ttu-id="5db54-217">Вместо этого необходимо использовать параметр DomainName.</span><span class="sxs-lookup"><span data-stu-id="5db54-217">You'll need to use the DomainName parameter instead.</span></span> <span data-ttu-id="5db54-218">При использовании параметра имя_домена необходимо определить полное доменное имя для записей lyncdiscoverinternal и lyncdiscover.</span><span class="sxs-lookup"><span data-stu-id="5db54-218">And when you use the DomainName parameter, you've got to define the FQDN for the lyncdiscoverinternal and lyncdiscover records.</span></span> <span data-ttu-id="5db54-219">В качестве примера можно привести (заменив параметр-CA на свой собственный путь к центру сертификации):</span><span class="sxs-lookup"><span data-stu-id="5db54-219">Examples would be (replacing the -Ca parameter with your own Certificate Authority path):</span></span>
    
   ```powershell
   Request-CsCertificate -New -Type WebServicesInternal -Ca dc\myca -DomainName "LyncdiscoverInternal.contoso.com, LyncdiscoverInternal.contoso.net" -verbose
   ```

   ```powershell
   Request-CsCertificate -New -Type WebServicesExternal -Ca dc\myca -DomainName "Lyncdiscover.contoso.com, Lyncdiscover.contoso.net" -verbose
   ```

   - <span data-ttu-id="5db54-220">После того как ЦС создал новые сертификаты, вам потребуется назначить их.</span><span class="sxs-lookup"><span data-stu-id="5db54-220">Once the new certificates have been generated by the CA, you're going to need to assign them.</span></span>
    
### <a name="assign-certificates-using-skype-for-business-server-management-shell"></a><span data-ttu-id="5db54-221">Назначение сертификатов с помощью командной консоли Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="5db54-221">Assign certificates using Skype for Business Server Management Shell</span></span>

- <span data-ttu-id="5db54-222">В зависимости от того, что вы нашли в разделе сделать так, что вам нужны новые сертификаты, необходимо выполнить **одно** из следующих действий.</span><span class="sxs-lookup"><span data-stu-id="5db54-222">Depending on what you found in the Do I need new certifications section above, you need to run **one** of the following.</span></span>
    
  - <span data-ttu-id="5db54-223">Если у вас есть один сертификат для всех (одинаковые отпечатки), необходимо выполнить следующую команду:</span><span class="sxs-lookup"><span data-stu-id="5db54-223">If you have a single certificate for everything (the thumbprints are identical) then you need to run this:</span></span>
    
  ```powershell
  Set-CsCertificate -Type <certificate(s) from the Use parameter> -Thumbprint <unique identifier>
  ```

  - <span data-ttu-id="5db54-224">Если у вас есть разные сертификаты для тех вещей (отпечатки отличаются), выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="5db54-224">If you've got different certificates for things (the thumbprints are all different), run this instead:</span></span>
    
  ```powershell
  Set-CsCertificate -Type Default -Thumbprint <certificate thumbprint>
  Set-CsCertificate -Type WebServicesInternal -Thumbprint <certificate thumbprint>
  Set-CsCertificate -Type WebServicesExternal -Thumbprint <certificate thumbprint>
  ```

### <a name="viewing-certificates-in-the-microsoft-management-console-mmc"></a><span data-ttu-id="5db54-225">Просмотр сертификатов в консоли управления (MMC)</span><span class="sxs-lookup"><span data-stu-id="5db54-225">Viewing certificates in the Microsoft Management Console (MMC)</span></span>

1. <span data-ttu-id="5db54-226">Вы можете просмотреть свои сертификаты с помощью оснастки "сертификаты" для консоли управления (MMC).</span><span class="sxs-lookup"><span data-stu-id="5db54-226">You have an option to look at your certificates using the Certificates snap-in for the MMC.</span></span> <span data-ttu-id="5db54-227">Просто введите MMC в область поиска, и она должна быть в качестве параметра приложения.</span><span class="sxs-lookup"><span data-stu-id="5db54-227">Simply type MMC into search and it should pop up as an application option,.</span></span>
    
2. <span data-ttu-id="5db54-228">Чтобы добавить оснастку "сертификаты", необходимо щелкнуть **файл**, а затем **Добавить или удалить оснастку...** (или сочетание клавиш **CTRL + M** также будет работать).</span><span class="sxs-lookup"><span data-stu-id="5db54-228">To add the Certificates snap-in, you'll need to click **File**, and then **Add/Remove Snap-In...** (or keyboard shortcut **Ctrl+M** would also work).</span></span> <span data-ttu-id="5db54-229">В левой области будут выбраны **Сертификаты** , выберите его, а затем нажмите **учетную запись компьютера** во всплывающем окне, а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="5db54-229">**Certificates** will be an option in the left-hand pane, select it and then **Computer Account** in the pop-up window, then **Next**.</span></span>
    
3. <span data-ttu-id="5db54-230">По-прежнему во всплывающем окне все это можно сделать на локальном компьютере, который необходимо просматривать, поэтому оставьте выбор на **локальном компьютере** , если это так.</span><span class="sxs-lookup"><span data-stu-id="5db54-230">Still in the pop-up window, in all likelihood you're doing this on the computer that's home to the certificates you need to look at, so leave the selection on **Local Computer** if that's so.</span></span> <span data-ttu-id="5db54-231">Если вы работаете на удаленном компьютере, измените переключатель переключателя на **другой компьютер** , а затем введите полное доменное имя компьютера или воспользуйтесь кнопкой **Обзор** , чтобы выполнить поиск этого компьютера через AD.</span><span class="sxs-lookup"><span data-stu-id="5db54-231">If you're working on a remote machine, change the radio button to **Another Computer** and then either enter that computer's FQDN or use the **Browse** button to search for that computer through AD.</span></span> <span data-ttu-id="5db54-232">Выбрав компьютер, нажмите кнопку **Готово** при готовности, а затем нажмите кнопку **ОК** , чтобы добавить оснастку в консоль управления (MMC).</span><span class="sxs-lookup"><span data-stu-id="5db54-232">After selecting the computer, you'll need to click **Finish** when ready, and then **OK** to add the snap-in to the MMC.</span></span>
    
4. <span data-ttu-id="5db54-233">Разверните раздел **Сертификаты** в левой области консоли управления (MMC).</span><span class="sxs-lookup"><span data-stu-id="5db54-233">Expand the **Certificates** section in the MMC's left-hand pane.</span></span> <span data-ttu-id="5db54-234">Разверните также **личную** папку, а затем выберите пункт **Сертификаты**.</span><span class="sxs-lookup"><span data-stu-id="5db54-234">Expand the **Personal** folder as well, and then select **Certificates**.</span></span> <span data-ttu-id="5db54-235">Это позволяет просматривать сертификаты в этом хранилище.</span><span class="sxs-lookup"><span data-stu-id="5db54-235">This lets you see the certificates in this store.</span></span>
    
5. <span data-ttu-id="5db54-236">Необходимо выбрать нужный сертификат, щелкните его правой кнопкой мыши и выберите команду **Открыть**.</span><span class="sxs-lookup"><span data-stu-id="5db54-236">You need to locate the certificate you want to view, right-click on it, and choose **Open**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="5db54-237">Как узнать, какой сертификат это такое?</span><span class="sxs-lookup"><span data-stu-id="5db54-237">How do you know what certificate this is?</span></span> <span data-ttu-id="5db54-238">Это должен быть один и тот же сертификат, назначенный всем для фермы, или несколько сертификатов для разных целей, например, по умолчанию, внутренние веб-службы и т. д., в таком случае вам может потребоваться просмотреть несколько сертификатов.</span><span class="sxs-lookup"><span data-stu-id="5db54-238">It should be either the single certificate assigned to everything for your farm, or you may have multiple certificates for different things, like Default, Internal Web Services, etc., in which case you may need to look at multiple certificates.</span></span> <span data-ttu-id="5db54-239">Несколько сертификатов будут иметь один и тот же отпечаток.</span><span class="sxs-lookup"><span data-stu-id="5db54-239">Multiple certificates will have the same thumbprint.</span></span> 
  
6. <span data-ttu-id="5db54-240">После получения представления " **сертификат** " нажмите кнопку **сведения**.</span><span class="sxs-lookup"><span data-stu-id="5db54-240">Once you've gotten to the **Certificate** view, choose **Details**.</span></span> <span data-ttu-id="5db54-241">Это позволит увидеть имя субъекта сертификата при выборе параметра **Тема**, а также отображаются назначенные имя субъекта и связанные свойства.</span><span class="sxs-lookup"><span data-stu-id="5db54-241">This will let you see the certificate subject name when you select **Subject**, and the assigned subject name and associated properties are shown.</span></span>
    
7. <span data-ttu-id="5db54-242">Кроме того, необходимо проверить записи **альтернативного имени субъекта** .</span><span class="sxs-lookup"><span data-stu-id="5db54-242">You'll also need to check the **Subject Alternate Name** entries.</span></span> <span data-ttu-id="5db54-243">Вы найдете один из следующих элементов:</span><span class="sxs-lookup"><span data-stu-id="5db54-243">You'll find one or more of the following:</span></span>
    
   - <span data-ttu-id="5db54-244">Имя пула для этого пула или имя отдельного сервера, если это не пул.</span><span class="sxs-lookup"><span data-stu-id="5db54-244">The pool name for this pool, or the single server name if this isn't a pool.</span></span>
    
   - <span data-ttu-id="5db54-245">Имя сервера, которому назначен сертификат.</span><span class="sxs-lookup"><span data-stu-id="5db54-245">The server name that the certificate is assigned to.</span></span>
    
   - <span data-ttu-id="5db54-246">Записи простых URL-адресов, как правило, удовлетворяют и набираемые.</span><span class="sxs-lookup"><span data-stu-id="5db54-246">Simple URL records, typically meet and dialin.</span></span>
    
   - <span data-ttu-id="5db54-247">Внутренние имена веб-служб и внешние имена веб-служб (например, webpool01.contoso.net, webpool01.contoso.com), основанные на вариантах, сделанных в построителе топологий и переопределенных на выборе веб-службах.</span><span class="sxs-lookup"><span data-stu-id="5db54-247">Web Services internal and Web Services external names (for example, webpool01.contoso.net, webpool01.contoso.com), based on choices made in Topology Builder and over-ridden Web Services selections.</span></span>
    
   - <span data-ttu-id="5db54-248">Если уже назначено, lyncdiscover. \<sipdomain\> и lyncdiscoverinternal. \<записи\> sipdomain.</span><span class="sxs-lookup"><span data-stu-id="5db54-248">If already assigned, the lyncdiscover.\<sipdomain\> and lyncdiscoverinternal.\<sipdomain\> records.</span></span>
    
     <span data-ttu-id="5db54-249">Вам потребуется проверить несколько сертификатов, если у вас больше одного назначения (проверьте заметку выше).</span><span class="sxs-lookup"><span data-stu-id="5db54-249">You'll need to check multiple certificates if you have more than one assigned (check the Note above).</span></span>
    
8. <span data-ttu-id="5db54-250">Итак, если вы нашли lyncdiscover. \<sipdomain\> и lyncdiscoverinternal. \<записи\> sipdomain. это уже настроено.</span><span class="sxs-lookup"><span data-stu-id="5db54-250">So, if you find lyncdiscover.\<sipdomain\> and lyncdiscoverinternal.\<sipdomain\> records, you've got this configured already.</span></span> <span data-ttu-id="5db54-251">Вы можете закрыть консоль управления (MMC).</span><span class="sxs-lookup"><span data-stu-id="5db54-251">You can close the MMC.</span></span>
    
9. <span data-ttu-id="5db54-252">Если они не назначены, вам потребуется создать новый запрос на сертификат (описанный выше) или необходимо установить их после запроса (для этого мы рекомендуем использовать приведенный выше пример PowerShell).</span><span class="sxs-lookup"><span data-stu-id="5db54-252">If they aren't assigned, you'll either need to make a new certificate request (outlined above) or you need to install them post-request (we recommend the following the PowerShell above for that).</span></span>
    
## <a name="configure-the-reverse-proxy"></a><span data-ttu-id="5db54-253">Настройка обратного прокси-сервера</span><span class="sxs-lookup"><span data-stu-id="5db54-253">Configure the reverse proxy</span></span>
<span data-ttu-id="5db54-254"><a name="ConfigRP"> </a></span><span class="sxs-lookup"><span data-stu-id="5db54-254"><a name="ConfigRP"> </a></span></span>

<span data-ttu-id="5db54-255">Приведенные ниже шаги не предназначены для выполнения в точности.</span><span class="sxs-lookup"><span data-stu-id="5db54-255">The steps below are not meant to be followed exactly.</span></span> <span data-ttu-id="5db54-256">Это вызвано тем, что в предыдущих версиях продукта мы прочитали вас, например, настроили шлюз управления угрозами (TMG), и если вы не использовали его, вам потребуется использовать собственную версию.</span><span class="sxs-lookup"><span data-stu-id="5db54-256">That's because in previous versions of the product, we'd have walked you through, for example, configuring Threat Management Gateway (TMG) and if you weren't using that, you'd need to work out your own version from there.</span></span>
  
<span data-ttu-id="5db54-257">TMG больше не предлагается корпорацией Майкрософт в качестве продукта, и если вам по-прежнему нужно настроить его, вы можете ознакомиться с [этапами Lync Server 2013](https://technet.microsoft.com/library/hh690011%28v=ocs.15%29.aspx).</span><span class="sxs-lookup"><span data-stu-id="5db54-257">TMG is no longer being offered by Microsoft as a product, and if you still need to configure it, you can look at the [Lync Server 2013 steps](https://technet.microsoft.com/library/hh690011%28v=ocs.15%29.aspx).</span></span> <span data-ttu-id="5db54-258">Но приведенные ниже сведения предназначены для более широкого использования, даже если не существует способа, который можно использовать для каждого обратного прокси-сервера.</span><span class="sxs-lookup"><span data-stu-id="5db54-258">But the following information's intended to be more generally helpful, even if there's no way we can provide specific walkthrough steps for every Reverse proxy out there.</span></span>
  
<span data-ttu-id="5db54-259">Мы рассмотрим два основных фактора:</span><span class="sxs-lookup"><span data-stu-id="5db54-259">We have two main things to consider:</span></span>
  
- <span data-ttu-id="5db54-260">Планируется ли выполнять исходный запрос автообнаружения по протоколу HTTPS (рекомендуемый)?</span><span class="sxs-lookup"><span data-stu-id="5db54-260">Are you going to be doing your initial Autodiscover request over HTTPS (which we recommend)?</span></span>
    
  - <span data-ttu-id="5db54-261">Если у вас есть правило веб-публикации, его необходимо изменить.</span><span class="sxs-lookup"><span data-stu-id="5db54-261">If you have a web publishing rule, you need to modify it.</span></span>
    
  - <span data-ttu-id="5db54-262">Если у вас еще нет правила веб-публикации, его необходимо создать.</span><span class="sxs-lookup"><span data-stu-id="5db54-262">If you don't have a web publishing rule yet, you need to create it.</span></span>
    
- <span data-ttu-id="5db54-263">Если вы выполняете исходный запрос автообнаружения по протоколу HTTP, необходимо также создать или изменить это правило.</span><span class="sxs-lookup"><span data-stu-id="5db54-263">If you're doing your initial Autodiscover request over HTTP, then you'll need to create or modify that rule as well.</span></span>
    
> [!NOTE]
> <span data-ttu-id="5db54-264">**Важно!** Значение времени ожидания прокси-сервера — это число, которое будет отличаться в зависимости от развертывания до развертывания.</span><span class="sxs-lookup"><span data-stu-id="5db54-264">**Important** A Proxy time-out value is a number that will vary from deployment to deployment.</span></span> <span data-ttu-id="5db54-265">Необходимо следить за развертыванием и изменять значение для лучшего взаимодействия с клиентами.</span><span class="sxs-lookup"><span data-stu-id="5db54-265">You should monitor your deployment and modify the value for the best experience for clients.</span></span> <span data-ttu-id="5db54-266">Вы можете задать значение, равное 200.</span><span class="sxs-lookup"><span data-stu-id="5db54-266">You may be able to set the value as low as 200.</span></span> <span data-ttu-id="5db54-267">Если вы поддерживаете мобильные клиенты Lync в вашей среде, необходимо задать для этого параметра значение 960, чтобы разрешить время ожидания push-уведомлений в Office 365, для которого значение времени ожидания равно 900.</span><span class="sxs-lookup"><span data-stu-id="5db54-267">If you are supporting Lync mobile clients in your environment, you should set the value to 960 to allow for push notification time-outs from Office 365, which have a time-out value of 900.</span></span> <span data-ttu-id="5db54-268">Очень вероятно, что вам потребуется увеличить значение времени ожидания, чтобы избежать отключения клиента, если значение слишком мало, или уменьшить число, если подключения через прокси-сервер не будут отключаться, но очистить до отключения клиента.</span><span class="sxs-lookup"><span data-stu-id="5db54-268">It is very likely that you will have to increase the time-out value to avoid client disconnects when the value is too low, or decrease the number if connections through the proxy do not disconnect but clear long after the client has disconnected.</span></span> <span data-ttu-id="5db54-269">Мониторинг и базовая то, что обычно используется в вашей среде, — единственный точный способ определить соответствующий параметр для этого значения.</span><span class="sxs-lookup"><span data-stu-id="5db54-269">Monitoring and baselining what is usual for your environment is the only accurate way to determine the appropriate setting for this value.</span></span>
  
### <a name="modify-the-existing-web-publishing-rule-for-your-external-autodiscover-san-and-url"></a><span data-ttu-id="5db54-270">Изменение существующего правила веб-публикации для внешнего адреса SAN и URL-адреса службы автообнаружения</span><span class="sxs-lookup"><span data-stu-id="5db54-270">Modify the existing web publishing rule for your external Autodiscover SAN and URL</span></span>

1. <span data-ttu-id="5db54-271">Откройте интерфейс обратного прокси-сервера.</span><span class="sxs-lookup"><span data-stu-id="5db54-271">Open your Reverse proxy interface.</span></span>
    
2. <span data-ttu-id="5db54-272">Необходимо указать правило веб-публикации и нажать кнопку Изменить (оно может находиться в меню или на вкладке, в зависимости от конфигурации обратного прокси-сервера).</span><span class="sxs-lookup"><span data-stu-id="5db54-272">You'll need to locate your web publishing rule, and choose the Edit option (it may be on a menu or tab, depending on your Reverse proxy configuration).</span></span>
    
3. <span data-ttu-id="5db54-273">Необходимо указать область, к которой применяется это правило веб-публикации.</span><span class="sxs-lookup"><span data-stu-id="5db54-273">There should be an area that states what this web publishing rule is applied to.</span></span> <span data-ttu-id="5db54-274">Это правило необходимо изменить для входящих сайтов или запросов для сайтов.</span><span class="sxs-lookup"><span data-stu-id="5db54-274">You need to modify this rule for incoming sites or requests for sites.</span></span> <span data-ttu-id="5db54-275">Вы собираетесь **Добавить** новую запись.</span><span class="sxs-lookup"><span data-stu-id="5db54-275">You're going to **add** a new entry.</span></span>
    
4. <span data-ttu-id="5db54-276">Введите имя сайта автообнаружения (для примера мы будем использовать lyncdiscover.contoso.com), а затем нажмите кнопку **ОК** или **сохранить**, в зависимости от формата обратного прокси-сервера.</span><span class="sxs-lookup"><span data-stu-id="5db54-276">Type the name of your Autodiscover site (the example we'll use is lyncdiscover.contoso.com), and click **OK** or **Save**, depending on your Reverse proxy's format.</span></span>
    
5. <span data-ttu-id="5db54-277">У вас может быть новый сертификат, в котором есть запись SAN автообнаружения.</span><span class="sxs-lookup"><span data-stu-id="5db54-277">You may have a new certificate that has the Autodiscover SAN entry in it.</span></span> <span data-ttu-id="5db54-278">, Которые необходимо установить и настроить для использования в соответствии с параметрами обратного прокси-сервера.</span><span class="sxs-lookup"><span data-stu-id="5db54-278">That needs to be installed as well and configured for use according to your Reverse proxy's settings.</span></span> <span data-ttu-id="5db54-279">Не забудьте сохранить все после завершения настройки.</span><span class="sxs-lookup"><span data-stu-id="5db54-279">Be sure to save everything when the configuration is completed.</span></span>
    
6. <span data-ttu-id="5db54-280">Если у обратного прокси-сервера есть **Тестовая** функциональность, выполните его, чтобы убедиться, что все работает должным образом.</span><span class="sxs-lookup"><span data-stu-id="5db54-280">If your Reverse proxy has a **Test** functionality, then please make use of it, to ensure everything's working properly.</span></span>
    
7. <span data-ttu-id="5db54-281">Теперь вам может потребоваться повторить эти действия, если в вашей среде используется директор или директор пула (это означает, что у вас есть второе правило).</span><span class="sxs-lookup"><span data-stu-id="5db54-281">Now, you may need to repeat these steps if you have a Director or Director pool in your environment (this would mean you have a second rule).</span></span>
    
### <a name="create-a-web-publishing-rule-for-the-external-autodiscover-url"></a><span data-ttu-id="5db54-282">Создание правила веб-публикации для внешнего URL-адреса автообнаружения</span><span class="sxs-lookup"><span data-stu-id="5db54-282">Create a web publishing rule for the external Autodiscover URL</span></span>

1. <span data-ttu-id="5db54-283">Откройте интерфейс обратного прокси-сервера.</span><span class="sxs-lookup"><span data-stu-id="5db54-283">Open your Reverse proxy interface.</span></span>
    
2. <span data-ttu-id="5db54-284">Вам потребуется определить, где в интерфейсе создаются правила веб-публикации, и выберите команду Создать или **создать** (может находиться в **меню или на** вкладке, в зависимости от конфигурации обратного прокси-сервера).</span><span class="sxs-lookup"><span data-stu-id="5db54-284">You'll need to locate where in the interface you create your web publishing rules, and choose the **New** or **Create** option (it may be on a menu or tab, depending on your Reverse proxy configuration).</span></span> <span data-ttu-id="5db54-285">Вы ищете вариант для создания нового правила веб-публикации.</span><span class="sxs-lookup"><span data-stu-id="5db54-285">You are looking for the option to create a new web publishing rule.</span></span>
    
3. <span data-ttu-id="5db54-286">Как правило, необходимо ввести следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="5db54-286">Typically, you will need to enter the following information:</span></span>
    
   - <span data-ttu-id="5db54-287">**Name**: имя правила.</span><span class="sxs-lookup"><span data-stu-id="5db54-287">**Name**: the name for your rule</span></span>
    
   - <span data-ttu-id="5db54-288">**Действие правила**: в этом случае это правило разрешения, что вы **разрешаете** прохождение через обратный прокси-сервер.</span><span class="sxs-lookup"><span data-stu-id="5db54-288">**Rule Action**: In this case it's an **Allow** rule, you're letting something pass through your Reverse proxy.</span></span>
    
   - <span data-ttu-id="5db54-289">Выбранным правилом **публикации** является **один веб-сайт или подсистема балансировки нагрузки**.</span><span class="sxs-lookup"><span data-stu-id="5db54-289">The **Publishing** rule or option you're choosing would be **single web site or load balancer**.</span></span>
    
   - <span data-ttu-id="5db54-290">Это должен быть **SSL** для внешнего доступа, выберите этот параметр.</span><span class="sxs-lookup"><span data-stu-id="5db54-290">This needs to be **SSL** for external access, choose that option.</span></span>
    
   - <span data-ttu-id="5db54-291">Необходимо опубликовать путь для **внутренней публикации**и ввести полное доменное имя для внешних веб-служб в подсистеме балансировки нагрузки пула переднего плана (или полное доменное имя балансировщика пула директоров, если таковой имеется), пример sfb_pool01. contoso. local.</span><span class="sxs-lookup"><span data-stu-id="5db54-291">You're going to need to publish a path for **Internal Publishing**, and enter the FQDN for the external Web Services on your Front End pool's load balancer (or the FQDN of the Director pool's load balancer if you have one), an example would be sfb_pool01.contoso.local.</span></span>
    
   - <span data-ttu-id="5db54-292">Необходимо ввести \*\* / \*\*\* в качестве пути для публикации, но также необходимо **переадресовать исходный заголовок узла**.</span><span class="sxs-lookup"><span data-stu-id="5db54-292">You should type **/\\**\* as the path to be published, but you also need to **forward the original host header**.</span></span>
    
   - <span data-ttu-id="5db54-293">Сведения об **общедоступных или внешних именах** , а также сведения о них.</span><span class="sxs-lookup"><span data-stu-id="5db54-293">There will be an option for **public or external name** details or information.</span></span> <span data-ttu-id="5db54-294">Это место, где вы сможете вводить:</span><span class="sxs-lookup"><span data-stu-id="5db54-294">This is the place where you'll be able to enter:</span></span>
    
   - <span data-ttu-id="5db54-295">**Принимать запросы**, но должно быть для доменного имени.</span><span class="sxs-lookup"><span data-stu-id="5db54-295">**Accept requests**, but it should be for the domain name.</span></span>
    
   - <span data-ttu-id="5db54-296">Введите lyncdiscover в поле **имя** **.**</span><span class="sxs-lookup"><span data-stu-id="5db54-296">For the **Name**, you should enter **lyncdiscover.**</span></span> <span data-ttu-id="5db54-297"><sipdomain>(это URL-адрес внешней службы автообнаружения).</span><span class="sxs-lookup"><span data-stu-id="5db54-297"><sipdomain> (this is the external Autodiscover Service URL).</span></span> <span data-ttu-id="5db54-298">Теперь, если вы создаете правило для URL-адреса внешних веб-служб в интерфейсном пуле, необходимо ввести полное доменное имя для внешних веб-служб в интерфейсном пуле (например, lyncwebextpool01.contoso.com).</span><span class="sxs-lookup"><span data-stu-id="5db54-298">Now, if you're creating a rule for the external Web Services URL on the Front End pool, you'll need to type the FQDN for the external Web Services on your Front End pool (for example, lyncwebextpool01.contoso.com).</span></span>
    
   - <span data-ttu-id="5db54-299">Будет выбран **путь** , и вам потребуется ввести \*\* / \*\*\* здесь.</span><span class="sxs-lookup"><span data-stu-id="5db54-299">There will be a **Path** option, and you'll need to enter **/\\**\* here.</span></span>
    
   - <span data-ttu-id="5db54-300">Вам потребуется выбрать **прослушиватель SSL** с общедоступным общедоступным сертификатом.</span><span class="sxs-lookup"><span data-stu-id="5db54-300">You'll need to select a **SSL Listener** with your up-to-date public certificate.</span></span>
    
   - <span data-ttu-id="5db54-301">Для **делегирования проверки подлинности** должно быть задано значение **без делегирования**, но проверка подлинности клиента **должна** быть разрешена.</span><span class="sxs-lookup"><span data-stu-id="5db54-301">**Authentication Delegation** should be set to **No delegation**, but direct client authentication **should** be allowed.</span></span>
    
   - <span data-ttu-id="5db54-302">Правило должно быть задано для **всех пользователей**.</span><span class="sxs-lookup"><span data-stu-id="5db54-302">The rule should be set to **All users**.</span></span>
    
   - <span data-ttu-id="5db54-303">Это должно быть все сведения, необходимые для создания этого правила и предоставления возможности продолжения.</span><span class="sxs-lookup"><span data-stu-id="5db54-303">This should be all the information you need to create this rule and allow you to proceed.</span></span>
    
4. <span data-ttu-id="5db54-304">Необходимо обеспечить перенаправление **исходного заголовка узла** .</span><span class="sxs-lookup"><span data-stu-id="5db54-304">You're going to need to ensure that the **original host header** is forwarded.</span></span>
    
5. <span data-ttu-id="5db54-305">Необходимо также настроить порты **веб-сервера** , выполнив следующие действия:</span><span class="sxs-lookup"><span data-stu-id="5db54-305">The **Web Server** ports will need to be set as well, you'll need to do the following:</span></span>
    
   - <span data-ttu-id="5db54-306">**Запросы на перенаправление на HTTP-порт** и номер порта должны быть **8080**.</span><span class="sxs-lookup"><span data-stu-id="5db54-306">**Redirect requests to HTTP port** and the port number should be **8080**.</span></span>
    
   - <span data-ttu-id="5db54-307">**Запросы на перенаправление на порт SSL** и номер порта должны быть **4443**.</span><span class="sxs-lookup"><span data-stu-id="5db54-307">**Redirect requests to SSL port** and the port number should be **4443**.</span></span>
    
6. <span data-ttu-id="5db54-308">Если все настроено, необходимо сохранить или применить их, а затем проверить правило.</span><span class="sxs-lookup"><span data-stu-id="5db54-308">When everything's configured, you'll need to save or apply these, and then you'll want to test the rule.</span></span>
    
### <a name="create-a-web-publishing-rule-for-port-80-optional"></a><span data-ttu-id="5db54-309">Создание правила веб-публикации для порта 80 (необязательно)</span><span class="sxs-lookup"><span data-stu-id="5db54-309">Create a web publishing rule for port 80 (Optional)</span></span>

1. <span data-ttu-id="5db54-310">Откройте интерфейс обратного прокси-сервера.</span><span class="sxs-lookup"><span data-stu-id="5db54-310">Open your Reverse proxy interface.</span></span>
    
2. <span data-ttu-id="5db54-311">Вам потребуется определить, где в интерфейсе создаются правила веб-публикации, и выберите команду Создать или **создать** (может находиться в **меню или на** вкладке, в зависимости от конфигурации обратного прокси-сервера).</span><span class="sxs-lookup"><span data-stu-id="5db54-311">You'll need to locate where in the interface you create your web publishing rules, and choose the **New** or **Create** option (it may be on a menu or tab, depending on your Reverse proxy configuration).</span></span> <span data-ttu-id="5db54-312">Вы ищете вариант для создания нового правила веб-публикации.</span><span class="sxs-lookup"><span data-stu-id="5db54-312">You are looking for the option to create a new web publishing rule.</span></span>
    
3. <span data-ttu-id="5db54-313">Как правило, необходимо ввести следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="5db54-313">Typically, you will need to enter the following information:</span></span>
    
   - <span data-ttu-id="5db54-314">**Name**: имя правила.</span><span class="sxs-lookup"><span data-stu-id="5db54-314">**Name**: the name for your rule</span></span>
    
   - <span data-ttu-id="5db54-315">**Действие правила**: в этом случае это правило разрешения, что вы **разрешаете** прохождение через обратный прокси-сервер.</span><span class="sxs-lookup"><span data-stu-id="5db54-315">**Rule Action**: In this case it's an **Allow** rule, you're letting something pass through your Reverse proxy.</span></span>
    
   - <span data-ttu-id="5db54-316">Выбранным правилом **публикации** является **один веб-сайт или подсистема балансировки нагрузки**.</span><span class="sxs-lookup"><span data-stu-id="5db54-316">The **Publishing** rule or option you're choosing would be **single web site or load balancer**.</span></span>
    
   - <span data-ttu-id="5db54-317">Для **подключения к опубликованному веб-серверу или ферме это должно быть незащищенное подключение**.</span><span class="sxs-lookup"><span data-stu-id="5db54-317">This needs to be a **non-secured connection to connect to the published Web server or farm**.</span></span>
    
   - <span data-ttu-id="5db54-318">Необходимо опубликовать путь для **внутренней публикации**и ввести полное доменное имя для **виртуального IP-адреса** подсистемы балансировки нагрузки пула переднего плана, например sfb_pool01. contoso. local.</span><span class="sxs-lookup"><span data-stu-id="5db54-318">You're going to need to publish a path for **Internal Publishing**, and enter the FQDN for the **VIP address** of your Front End pool's load balancer, an example would be sfb_pool01.contoso.local.</span></span>
    
   - <span data-ttu-id="5db54-319">Необходимо ввести \*\* / \*\*\* в качестве пути для публикации, но также необходимо **переадресовать исходный заголовок узла**.</span><span class="sxs-lookup"><span data-stu-id="5db54-319">You should type **/\\**\* as the path to be published, but you also need to **forward the original host header**.</span></span>
    
   - <span data-ttu-id="5db54-320">Сведения об **общедоступных или внешних именах** , а также сведения о них.</span><span class="sxs-lookup"><span data-stu-id="5db54-320">There will be an option for **public or external name** details or information.</span></span> <span data-ttu-id="5db54-321">Это место, где вы сможете вводить:</span><span class="sxs-lookup"><span data-stu-id="5db54-321">This is the place where you'll be able to enter:</span></span>
    
   - <span data-ttu-id="5db54-322">**Принимать запросы**, но должно быть для доменного имени.</span><span class="sxs-lookup"><span data-stu-id="5db54-322">**Accept requests**, but it should be for the domain name.</span></span>
    
   - <span data-ttu-id="5db54-323">Введите lyncdiscover в поле **имя** **.**</span><span class="sxs-lookup"><span data-stu-id="5db54-323">For the **Name**, you should enter **lyncdiscover.**</span></span> <span data-ttu-id="5db54-324"><sipdomain>(это URL-адрес внешней службы автообнаружения).</span><span class="sxs-lookup"><span data-stu-id="5db54-324"><sipdomain> (this is the external Autodiscover Service URL).</span></span>
    
   - <span data-ttu-id="5db54-325">Будет выбран **путь** , и вам потребуется ввести \*\* / \*\*\* здесь.</span><span class="sxs-lookup"><span data-stu-id="5db54-325">There will be a **Path** option, and you'll need to enter **/\\**\* here.</span></span>
    
   - <span data-ttu-id="5db54-326">Необходимо выбрать веб-прослушиватель или разрешить обратному прокси-серверу создать его.</span><span class="sxs-lookup"><span data-stu-id="5db54-326">You'll need to select a web listener, or allow your Reverse proxy to create one for you.</span></span>
    
   - <span data-ttu-id="5db54-327">Для **делегирования проверки подлинности** должно быть задано значение **без делегирования**, но проверка подлинности прямого клиента **не** разрешена.</span><span class="sxs-lookup"><span data-stu-id="5db54-327">**Authentication Delegation** should be set to **No delegation**, but direct client authentication **should not** be allowed.</span></span>
    
   - <span data-ttu-id="5db54-328">Правило должно быть задано для **всех пользователей**.</span><span class="sxs-lookup"><span data-stu-id="5db54-328">The rule should be set to **All users**.</span></span>
    
   - <span data-ttu-id="5db54-329">Это должно быть все сведения, необходимые для создания этого правила и предоставления возможности продолжения.</span><span class="sxs-lookup"><span data-stu-id="5db54-329">This should be all the information you need to create this rule and allow you to proceed.</span></span>
    
4. <span data-ttu-id="5db54-330">Необходимо настроить порты **веб-сервера** , выполнив следующие действия:</span><span class="sxs-lookup"><span data-stu-id="5db54-330">The **Web Server** ports will need to be set, you'll need to do the following:</span></span>
    
   - <span data-ttu-id="5db54-331">**Запросы на перенаправление на HTTP-порт** и номер порта должны быть **8080**.</span><span class="sxs-lookup"><span data-stu-id="5db54-331">**Redirect requests to HTTP port** and the port number should be **8080**.</span></span>
    
   - <span data-ttu-id="5db54-332">**Запросы на перенаправление на порт SSL** и номер порта должны быть **4443**.</span><span class="sxs-lookup"><span data-stu-id="5db54-332">**Redirect requests to SSL port** and the port number should be **4443**.</span></span>
    
5. <span data-ttu-id="5db54-333">Если все настроено, необходимо сохранить или применить их, а затем проверить правило.</span><span class="sxs-lookup"><span data-stu-id="5db54-333">When everything's configured, you'll need to save or apply these, and then you'll want to test the rule.</span></span>
    
## <a name="configure-autodiscover-for-mobility-with-hybrid-deployments"></a><span data-ttu-id="5db54-334">Настройка службы автообнаружения для мобильной работы с гибридными развертываниями</span><span class="sxs-lookup"><span data-stu-id="5db54-334">Configure Autodiscover for Mobility with hybrid deployments</span></span>
<span data-ttu-id="5db54-335"><a name="ConfigAutoD"> </a></span><span class="sxs-lookup"><span data-stu-id="5db54-335"><a name="ConfigAutoD"> </a></span></span>

<span data-ttu-id="5db54-336">Гибридные среды в Skype для бизнеса Server представляют собой среды, сочетающие в себе локальную среду и среду O365.</span><span class="sxs-lookup"><span data-stu-id="5db54-336">Hybrid environments in Skype for Business Server are environments that combine an on-premises and O365 environment.</span></span> <span data-ttu-id="5db54-337">Если в гибридной среде работает Skype для бизнеса Server, служба автообнаружения должна иметь возможность обнаружения пользователя в любой из этих сред.</span><span class="sxs-lookup"><span data-stu-id="5db54-337">When you have Skype for Business Server working in a Hybrid environment, the Autodiscover service needs to be able to locate a user from either of these environments.</span></span>
  
<span data-ttu-id="5db54-338">Чтобы мобильные клиенты могли обнаруживать, где находится пользователь, служба автообнаружения должна быть настроена с помощью нового URL-адреса.</span><span class="sxs-lookup"><span data-stu-id="5db54-338">To let mobile clients discover where a user's located, the Autodiscover service needs to be configured with a new uniform resource locator (URL).</span></span> <span data-ttu-id="5db54-339">Ниже описана последовательность действий.</span><span class="sxs-lookup"><span data-stu-id="5db54-339">The steps are:</span></span>
  
1. <span data-ttu-id="5db54-340">Откройте консоль управления Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="5db54-340">Open Skype for Business Server Management Shell.</span></span>
    
2. <span data-ttu-id="5db54-341">Выполните следующую команду, чтобы получить значение атрибута **ProxyFQDN** для среды Skype для бизнеса Server:</span><span class="sxs-lookup"><span data-stu-id="5db54-341">Run the following to get the value of the attribute **ProxyFQDN** for your Skype for Business Server environment:</span></span>
    
   ```powershell
   Get-CsHostingProvider
   ```

3. <span data-ttu-id="5db54-342">Затем в окне командной консоли выполните команду:</span><span class="sxs-lookup"><span data-stu-id="5db54-342">Then, still in the shell window, run:</span></span>
    
   ```powershell
   Set-CsHostingProvider -Identity [identity] -AutodiscoverUrl https://webdir.online.lync.com/autodiscover/autodiscoverservice.svc/root
   ```

    <span data-ttu-id="5db54-343">Где [идентификатор] заменяется именем домена общего пространства адресов SIP.</span><span class="sxs-lookup"><span data-stu-id="5db54-343">Where [identity] is replaced with the domain name of the shared SIP address space.</span></span>
    
## <a name="test-your-mobility-deployment"></a><span data-ttu-id="5db54-344">Тестирование развертывания мобильности</span><span class="sxs-lookup"><span data-stu-id="5db54-344">Test your Mobility deployment</span></span>
<span data-ttu-id="5db54-345"><a name="TestMobility"> </a></span><span class="sxs-lookup"><span data-stu-id="5db54-345"><a name="TestMobility"> </a></span></span>

<span data-ttu-id="5db54-346">После того как вы развернули службу Mobility Service для Skype для бизнеса Server и службу автообнаружения Skype для бизнеса Server, вам потребуется выполнить тестовую транзакцию, чтобы убедиться, что ваше развертывание работает правильно.</span><span class="sxs-lookup"><span data-stu-id="5db54-346">Once you've deployed Skype for Business Server Mobility Service and Skype for Business Server Autodiscover Service, you'll want to run a test transaction, to make sure your deployment's working right.</span></span> <span data-ttu-id="5db54-347">С помощью командлета **Test-CsUcwaConference** можно проверить возможность создания, присоединения и общения двух пользователей в Конференции.</span><span class="sxs-lookup"><span data-stu-id="5db54-347">You can run **Test-CsUcwaConference** to test the ability of two users to create, join and communicate in a conference.</span></span> <span data-ttu-id="5db54-348">Для выполнения этого тестирования потребуются два пользователя (реальный или тестовый) и их полные учетные данные.</span><span class="sxs-lookup"><span data-stu-id="5db54-348">You will need two users (real or test) and their full credentials to do this testing.</span></span> <span data-ttu-id="5db54-349">Эта команда будет работать как для клиентов Skype для бизнеса, так и для клиентов Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="5db54-349">This command will work for both Skype for Business clients as well as Lync Server 2013 clients.</span></span>
  
<span data-ttu-id="5db54-350">Для пользователей Lync Server 2010 в Skype для бизнеса Server 2015 вам потребуется выполнить **Test-CsMcxP2PIM** для тестирования.</span><span class="sxs-lookup"><span data-stu-id="5db54-350">For Lync Server 2010 clients on Skype for Business Server 2015, you'll need to run **Test-CsMcxP2PIM** to test.</span></span> <span data-ttu-id="5db54-351">Пользователи Lync Server 2010 по-прежнему должны быть реальными пользователями или предварительно определенными тестовыми пользователями, и вам понадобятся учетные данные их паролей.</span><span class="sxs-lookup"><span data-stu-id="5db54-351">Your Lync Server 2010 users will still have to be actual users, or predefined test users, and you'll need their password credentials.</span></span>

> [!NOTE]
> <span data-ttu-id="5db54-352">MCX (служба Mobility Service) поддержка устаревших мобильных клиентов больше недоступна в Skype для бизнеса Server 2019.</span><span class="sxs-lookup"><span data-stu-id="5db54-352">MCX (Mobility Service) support for legacy mobile clients is no longer available in Skype for Business Server 2019.</span></span> <span data-ttu-id="5db54-353">Все текущие мобильные клиенты Skype для бизнеса уже используют веб-API объединенных коммуникаций (UCWA), чтобы поддерживать обмен мгновенными сообщениями, сведения о присутствии и контакты.</span><span class="sxs-lookup"><span data-stu-id="5db54-353">All current Skype for Business mobile clients already use Unified Communications Web API (UCWA) to support instant messaging (IM), presence, and contacts.</span></span> <span data-ttu-id="5db54-354">Пользователям прежних версий клиентов, использующих MCX, необходимо выполнить обновление до текущего клиента.</span><span class="sxs-lookup"><span data-stu-id="5db54-354">Users with legacy clients using MCX will need to upgrade to a current client.</span></span>
  
### <a name="test-conferencing-for-skype-for-business-and-lync-2013-mobile-clients"></a><span data-ttu-id="5db54-355">Тестирование конференц-связи для мобильных клиентов Skype для бизнеса и Lync 2013</span><span class="sxs-lookup"><span data-stu-id="5db54-355">Test conferencing for Skype for Business and Lync 2013 mobile clients</span></span>

1. <span data-ttu-id="5db54-356">Выполните вход в качестве члена роли **CsAdministrator** на любом компьютере, на котором установлены **Командная консоль и OCSCore для управления Skype для бизнеса Server** . \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="5db54-356">Log on as a member of the **CsAdministrator** role on any computer where **Skype for Business Server Management Shell** and **Ocscore** are installed.</span></span>
    
2. <span data-ttu-id="5db54-357">Запустите **командную консоль Skype для бизнеса Server** (введите имя в поле Поиск или выберите **все программы** и выберите ее).</span><span class="sxs-lookup"><span data-stu-id="5db54-357">Start the **Skype for Business Server Management Shell** (you might type the name in search or go to **All Programs** and choose it).</span></span>
    
3. <span data-ttu-id="5db54-358">В командной строке введите:</span><span class="sxs-lookup"><span data-stu-id="5db54-358">At the command line, enter:</span></span>
    
   ```powershell
   Test-CsUcwaConference -TargetFqdn <FQDN of Front End pool> -Authentication <TrustedServer | Negotiate | ClientCertificate | LiveID> -OrganizerSipAddress sip:<SIP address of test user 1> -OrganizerCredential <test user 1 credentials> -ParticipantSipAddress sip:<SIP address of test user 2> -ParticipantCredential <test user 2 credentials> -v
   ```

   <span data-ttu-id="5db54-359">Кроме того, можно задать учетные данные в сценарии и передать их в командлет Test.</span><span class="sxs-lookup"><span data-stu-id="5db54-359">It's also possible to set credentials in a script and pass them to the test cmdlet.</span></span> <span data-ttu-id="5db54-360">Ниже приведен пример.</span><span class="sxs-lookup"><span data-stu-id="5db54-360">We have an example of this below.</span></span>
    
   ```powershell
   $passwd1 = ConvertTo-SecureString "Password01" -AsPlainText -Force
   $passwd2 = ConvertTo-SecureString "Password02" -AsPlainText -Force
   $testuser1 = New-Object Management.Automation.PSCredential("contoso\UserName1", $passwd1)
   $testuser2 = New-Object Management.Automation.PSCredential("contoso\UserName2", $passwd2)
   Test-CsUcwaConference -TargetFqdn pool01.contoso.com -Authentication Negotiate -OrganizerSipAddress sip:UserName1@contoso.com -OrganizerCredential $testuser1 -ParticipantSipAddress sip:UserName2@contoso.com -ParticipantCredential $testuser2 -v
   ```

### <a name="test-conferencing-for-lync-2010-mobile-clients"></a><span data-ttu-id="5db54-361">Проверка конференц-связи для мобильных клиентов Lync 2010</span><span class="sxs-lookup"><span data-stu-id="5db54-361">Test conferencing for Lync 2010 mobile clients</span></span>

> [!NOTE]
> <span data-ttu-id="5db54-362">MCX (служба Mobility Service) поддержка устаревших мобильных клиентов больше недоступна в Skype для бизнеса Server 2019.</span><span class="sxs-lookup"><span data-stu-id="5db54-362">MCX (Mobility Service) support for legacy mobile clients is no longer available in Skype for Business Server 2019.</span></span> <span data-ttu-id="5db54-363">Все текущие мобильные клиенты Skype для бизнеса уже используют веб-API объединенных коммуникаций (UCWA), чтобы поддерживать обмен мгновенными сообщениями, сведения о присутствии и контакты.</span><span class="sxs-lookup"><span data-stu-id="5db54-363">All current Skype for Business mobile clients already use Unified Communications Web API (UCWA) to support instant messaging (IM), presence, and contacts.</span></span> <span data-ttu-id="5db54-364">Пользователям прежних версий клиентов, использующих MCX, необходимо выполнить обновление до текущего клиента.</span><span class="sxs-lookup"><span data-stu-id="5db54-364">Users with legacy clients using MCX will need to upgrade to a current client.</span></span>

1. <span data-ttu-id="5db54-365">Выполните вход в качестве члена роли **CsAdministrator** на любом компьютере, на котором установлены **Командная консоль и OCSCore для управления Skype для бизнеса Server** . \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="5db54-365">Log on as a member of the **CsAdministrator** role on any computer where **Skype for Business Server Management Shell** and **Ocscore** are installed.</span></span>
    
2. <span data-ttu-id="5db54-366">Запустите **командную консоль Skype для бизнеса Server** (введите имя в поле Поиск или выберите **все программы** и выберите ее).</span><span class="sxs-lookup"><span data-stu-id="5db54-366">Start the **Skype for Business Server Management Shell** (you might type the name in search or go to **All Programs** and choose it).</span></span>
    
3. <span data-ttu-id="5db54-367">В командной строке введите:</span><span class="sxs-lookup"><span data-stu-id="5db54-367">At the command line, enter:</span></span>
    
   ```powershell
   Test-CsMcxP2PIM -TargetFqdn <FQDN of Front End pool> -Authentication <TrustedServer | Negotiate | ClientCertificate | LiveID> -SenderSipAddress sip:<SIP address of test user 1> -SenderCredential <test user 1 credentials> -ReceiverSipAddress sip:<SIP address of test user 2> -ReceiverCredential <test user 2 credentials> -v
   ```

   <span data-ttu-id="5db54-368">Кроме того, можно задать учетные данные в сценарии и передать их в командлет Test.</span><span class="sxs-lookup"><span data-stu-id="5db54-368">It's also possible to set credentials in a script and pass them to the test cmdlet.</span></span> <span data-ttu-id="5db54-369">Ниже приведен пример.</span><span class="sxs-lookup"><span data-stu-id="5db54-369">We have an example of this below.</span></span>
    
   ```powershell
   $passwd1 = ConvertTo-SecureString "Password01" -AsPlainText -Force
   $passwd2 = ConvertTo-SecureString "Password02" -AsPlainText -Force
   $tuc1 = New-Object Management.Automation.PSCredential("contoso\UserName1", $passwd1)
   $tuc2 = New-Object Management.Automation.PSCredential("contoso\UserName2", $passwd2)
   Test-CsMcxP2PIM -TargetFqdn pool01.contoso.com -Authentication Negotiate -SenderSipAddress sip:UserName1@contoso.com -SenderCredential $tuc1 -ReceiverSipAddress sip:UserName2@contoso.com -ReceiverCredential $tuc2 -v
   ```

<span data-ttu-id="5db54-370">Для дальнейшей проверки процедур командной строки можно извлечь [тест-CsUcwaConference](https://docs.microsoft.com/powershell/module/skype/test-csucwaconference?view=skype-ps) и [Test-CsMcxP2PIM](https://docs.microsoft.com/powershell/module/skype/test-csmcxp2pim?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="5db54-370">To review the command procedures further, you can check out [Test-CsUcwaConference](https://docs.microsoft.com/powershell/module/skype/test-csucwaconference?view=skype-ps) and [Test-CsMcxP2PIM](https://docs.microsoft.com/powershell/module/skype/test-csmcxp2pim?view=skype-ps).</span></span>
  
## <a name="configure-for-push-notifications"></a><span data-ttu-id="5db54-371">Настройка для использования push-уведомлений</span><span class="sxs-lookup"><span data-stu-id="5db54-371">Configure for push notifications</span></span>
<span data-ttu-id="5db54-372"><a name="ConfigPush"> </a></span><span class="sxs-lookup"><span data-stu-id="5db54-372"><a name="ConfigPush"> </a></span></span>

<span data-ttu-id="5db54-373">Push-уведомления, в форме эмблем, значков или оповещений, могут быть отправлены на мобильное устройство, даже если приложение Skype или Lync неактивно.</span><span class="sxs-lookup"><span data-stu-id="5db54-373">Push notifications, in the form of badges, icons, or alerts, can be sent to a mobile device even when the Skype or Lync app is inactive.</span></span> <span data-ttu-id="5db54-374">Но что такое push-уведомления?</span><span class="sxs-lookup"><span data-stu-id="5db54-374">But what are push notifications?</span></span> <span data-ttu-id="5db54-375">Они представляют собой оповещения о событиях, такие как новое или пропущенное приглашение на обмен мгновенными сообщениями, а также на получение голосовой почты.</span><span class="sxs-lookup"><span data-stu-id="5db54-375">They are event alerts, like a new or missed IM invitation, or for a received voicemail.</span></span> <span data-ttu-id="5db54-376">Служба Mobility Server для Skype для бизнеса Server отправляет эти уведомления в облачную службу push-уведомлений Skype для бизнеса Server, которая затем отправляет уведомления в службу push-уведомлений Майкрософт (МСНС) для пользователей Windows Phone.</span><span class="sxs-lookup"><span data-stu-id="5db54-376">The Skype for Business Server Mobility service sends these notifications to the cloud-based Skype for Business Server Push Notification Service, which then sends the notifications to the Microsoft Push Notification Service (MSNS) for Windows Phone users.</span></span>
  
<span data-ttu-id="5db54-377">Эта функция не изменилась с Lync Server 2013, но если у вас есть Skype для бизнеса Server, вам потребуется выполнить следующие действия:</span><span class="sxs-lookup"><span data-stu-id="5db54-377">This functionality is unchanged from Lync Server 2013, but if you have a Skype for Business Server, you'll want to do the following:</span></span>
  
- <span data-ttu-id="5db54-378">Для пограничного сервера Skype для бизнеса Server добавьте нового поставщика услуг хостинга, Microsoft Skype для бизнеса Online, а затем настройте Федерацию поставщика услуг хранения между вашей организацией и Skype для бизнеса Online.</span><span class="sxs-lookup"><span data-stu-id="5db54-378">For a Skype for Business Server Edge Server, add a new hosting provider, Microsoft Skype for Business Online, and then set up hosting provider federation between your organization and Skype for Business Online.</span></span>
    
- <span data-ttu-id="5db54-379">Включите push-уведомления, выполнив командлет **Set-CsPushNotificationConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="5db54-379">Enable push notifications by running the **Set-CsPushNotificationConfiguration** cmdlet.</span></span> <span data-ttu-id="5db54-380">По умолчанию push-уведомления отключены.</span><span class="sxs-lookup"><span data-stu-id="5db54-380">By default, push notifications are turned off.</span></span>
    
- <span data-ttu-id="5db54-381">Протестируйте конфигурацию Федерации и Push-уведомления.</span><span class="sxs-lookup"><span data-stu-id="5db54-381">Test your federation configuration and push notifications.</span></span>
    
### <a name="configure-your-skype-for-business-edge-server-for-push-notifications"></a><span data-ttu-id="5db54-382">Настройка пограничного сервера Skype для бизнеса для push-уведомлений</span><span class="sxs-lookup"><span data-stu-id="5db54-382">Configure your Skype for Business Edge Server for push notifications</span></span>

1. <span data-ttu-id="5db54-383">Войдите в систему, используя учетную запись, которая является участником роли **CsAdministrator** , на компьютер, на котором установлены Командная консоль и **OCSCore** **консоли управления Skype для бизнеса Server** .</span><span class="sxs-lookup"><span data-stu-id="5db54-383">Log on, with an account that's a member of the **CsAdministrator** role, to a computer where **Skype for Business Server Management Shell** and **Ocscore** are installed.</span></span>
    
2. <span data-ttu-id="5db54-384">Запустите **консоль управления Skype для бизнеса Server**.</span><span class="sxs-lookup"><span data-stu-id="5db54-384">Start the **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="5db54-385">Добавьте поставщик услуг хостинга Skype для бизнеса Server Online.</span><span class="sxs-lookup"><span data-stu-id="5db54-385">Add a Skype for Business Server online hosting provider.</span></span>
    
   ```powershell
   New-CsHostingProvider -Identity <unique identifier for hosting provider> -Enabled $True -ProxyFQDN <FQDN for the Access Server used by the hosting provider> -VerificationLevel UseSourceVerification
   ```

   <span data-ttu-id="5db54-386">Например:</span><span class="sxs-lookup"><span data-stu-id="5db54-386">As an example:</span></span>
    
   ```powershell
   New-CsHostingProvider -Identity "SkypeOnline" -Enabled $True -ProxyFQDN "sipfed.online.lync.com" -VerificationLevel UseSourceVerification
   ```

    > [!NOTE]
    > <span data-ttu-id="5db54-387">Вы не можете использовать несколько отношений Федерации с одним поставщиком услуг хостинга.</span><span class="sxs-lookup"><span data-stu-id="5db54-387">You can't have more than one federation relationship with a single hosting provider.</span></span> <span data-ttu-id="5db54-388">Таким образом, если вы уже настроили поставщика услуг хостинга с отношением Федерации с sipfed.online.lync.com, не добавляйте для него другого поставщика услуг хостинга, даже если идентификатор поставщика услуг хостинга не является Скипеонлине.</span><span class="sxs-lookup"><span data-stu-id="5db54-388">So, if you've already set up a hosting provider that has a federation relationship with sipfed.online.lync.com, don't add another hosting provider for it, even if the identity of the hosting provider is something other than SkypeOnline.</span></span> 
  
4. <span data-ttu-id="5db54-389">Настройте федерацию поставщика услуг хостинга между вашей организацией и службой push-уведомлений в Skype для бизнеса Online.</span><span class="sxs-lookup"><span data-stu-id="5db54-389">Set up the hosting provider federation between your organization and the Push Notification Service at Skype for Business Online.</span></span> <span data-ttu-id="5db54-390">В командной строке необходимо ввести:</span><span class="sxs-lookup"><span data-stu-id="5db54-390">At the command line, you'll need to type:</span></span>
    
   ```powershell
    New-CsAllowedDomain -Identity "push.lync.com"
   ```

### <a name="enable-push-notifications"></a><span data-ttu-id="5db54-391">Включение push-уведомлений</span><span class="sxs-lookup"><span data-stu-id="5db54-391">Enable push notifications</span></span>

1. <span data-ttu-id="5db54-392">Войдите в систему, используя учетную запись, которая является участником роли **CsAdministrator** , на компьютер, на котором установлены Командная консоль и **OCSCore** **консоли управления Skype для бизнеса Server** .</span><span class="sxs-lookup"><span data-stu-id="5db54-392">Log on, with an account that's a member of the **CsAdministrator** role, to a computer where **Skype for Business Server Management Shell** and **Ocscore** are installed.</span></span>
    
2. <span data-ttu-id="5db54-393">Запустите **консоль управления Skype для бизнеса Server**.</span><span class="sxs-lookup"><span data-stu-id="5db54-393">Start the **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="5db54-394">Включить push-уведомления:</span><span class="sxs-lookup"><span data-stu-id="5db54-394">Enable push notifications:</span></span>
    
   ```powershell
   Set-CsPushNotificationConfiguration -EnableMicrosoftPushNotificationService $True
   ```

4. <span data-ttu-id="5db54-395">Включение Федерации:</span><span class="sxs-lookup"><span data-stu-id="5db54-395">Enable Federation:</span></span>
     
   ```powershell
   Set-CsAccessEdgeConfiguration -AllowFederatedUsers $True
   ```

### <a name="test-federation-and-push-notifications"></a><span data-ttu-id="5db54-396">Тестирование Федерации и push-уведомлений</span><span class="sxs-lookup"><span data-stu-id="5db54-396">Test federation and push notifications</span></span>

1. <span data-ttu-id="5db54-397">Войдите в систему, используя учетную запись, которая является участником роли **CsAdministrator** , на компьютер, на котором установлены Командная консоль и **OCSCore** **консоли управления Skype для бизнеса Server** .</span><span class="sxs-lookup"><span data-stu-id="5db54-397">Log on, with an account that's a member of the **CsAdministrator** role, to a computer where **Skype for Business Server Management Shell** and **Ocscore** are installed.</span></span>
    
2. <span data-ttu-id="5db54-398">Запустите **консоль управления Skype для бизнеса Server**.</span><span class="sxs-lookup"><span data-stu-id="5db54-398">Start the **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="5db54-399">Тестирование конфигурации федерации:</span><span class="sxs-lookup"><span data-stu-id="5db54-399">Test the federation configuration:</span></span>
    
   ```powershell
   Test-CsFederatedPartner -TargetFqdn <FQDN of Access Edge server used for federated SIP traffic> -Domain <FQDN of federated domain> -ProxyFqdn <FQDN of the Access Edge server used by the federated organization>
   ```

    <span data-ttu-id="5db54-400">Например:</span><span class="sxs-lookup"><span data-stu-id="5db54-400">As an example:</span></span>
    
   ```powershell
   Test-CsFederatedPartner -TargetFqdn accessproxy.contoso.com -Domain push.lync.com -ProxyFqdn sipfed.online.lync.com
   ```

4. <span data-ttu-id="5db54-401">Протестируйте push-уведомления:</span><span class="sxs-lookup"><span data-stu-id="5db54-401">Test your push notifications:</span></span>
    
   ```powershell
   Test-CsMcxPushNotification -AccessEdgeFqdn <Access Edge service FQDN>
   ```

    <span data-ttu-id="5db54-402">Например:</span><span class="sxs-lookup"><span data-stu-id="5db54-402">As an example:</span></span>
    
   ```powershell
   Test-CsMcxPushNotification -AccessEdgeFqdn accessproxy.contoso.com
   ```

## <a name="configure-mobility-policy"></a><span data-ttu-id="5db54-403">Настройка политики мобильности</span><span class="sxs-lookup"><span data-stu-id="5db54-403">Configure Mobility policy</span></span>
<span data-ttu-id="5db54-404"><a name="ConfigMob"> </a></span><span class="sxs-lookup"><span data-stu-id="5db54-404"><a name="ConfigMob"> </a></span></span>

<span data-ttu-id="5db54-405">С помощью Skype для бизнеса Server можно определить, кто может использовать службу Mobility Service, позвонить через Works, Voice over IP (VoIP) или видео, а также требуется ли WiFi для VoIP или видео.</span><span class="sxs-lookup"><span data-stu-id="5db54-405">You have the ability with Skype for Business Server to determine who can use your Mobility service, Call via Work, voice over IP (VoIP), or video, as well as whether WiFi will be required for VoIP or video.</span></span> <span data-ttu-id="5db54-406">"Позвонить с рабочего" — позволяет мобильному пользователю использовать номер рабочего телефона, а не номер мобильного телефона при размещении и получении звонков.</span><span class="sxs-lookup"><span data-stu-id="5db54-406">Call via Work lets a mobile user use their work phone number, instead of their mobile phone number, when placing and receiving calls.</span></span> <span data-ttu-id="5db54-407">Пользователь, находящийся на другом конце строки, не увидит номер сотового телефона пользователя мобильного устройства, и он позволяет пользователям мобильных устройств избежать оплаты исходящих звонков.</span><span class="sxs-lookup"><span data-stu-id="5db54-407">The person on the other end of the line won't see that mobile user's cell phone number, and it lets that mobile user avoid outgoing call charges.</span></span> <span data-ttu-id="5db54-408">Когда VoIP и видео настроены, пользователи могут совершать и совершать звонки и видео по VoIP.</span><span class="sxs-lookup"><span data-stu-id="5db54-408">When VoIP and video are set up, users can take and make VoIP calls and video.</span></span> <span data-ttu-id="5db54-409">Параметры использования Wi-Fi определяют, потребуется ли мобильному устройству пользователя использовать сеть Wi-Fi через сотовую сеть передачи данных.</span><span class="sxs-lookup"><span data-stu-id="5db54-409">The settings for WiFi usage determine whether a user's mobile device will be required to use a WiFi network over a cellular data network.</span></span>
  
<span data-ttu-id="5db54-410">По умолчанию включены мобильные устройства, звонки через работу и функции VoIP и видео.</span><span class="sxs-lookup"><span data-stu-id="5db54-410">Mobility, Call via Work, and the VoIP and video features are all enabled by default.</span></span> <span data-ttu-id="5db54-411">Параметр требования WiFi для VoIP и Video отключены.</span><span class="sxs-lookup"><span data-stu-id="5db54-411">The setting to require WiFi for VoIP and video are disabled.</span></span> <span data-ttu-id="5db54-412">Администратор может изменять это, как глобально, по сайту или по пользователю.</span><span class="sxs-lookup"><span data-stu-id="5db54-412">An Admin has the ability to change this, either globally, by site, or by user.</span></span>
  
<span data-ttu-id="5db54-413">Чтобы иметь возможность использовать функции мобильной связи и звонить через работу, пользователям необходимо:</span><span class="sxs-lookup"><span data-stu-id="5db54-413">To be able to use Mobility features and Call via Work, users need to be:</span></span>
  
- <span data-ttu-id="5db54-414">Включен для Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="5db54-414">Enabled for Skype for Business Server</span></span>
    
- <span data-ttu-id="5db54-415">Включено для корпоративной голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="5db54-415">Enabled for Enterprise Voice.</span></span>
    
- <span data-ttu-id="5db54-416">Назначена политика мобильности с установленным значением **true**для параметра **енаблемобилити** .</span><span class="sxs-lookup"><span data-stu-id="5db54-416">Assigned a Mobility policy that has the **EnableMobility** option set to **True**.</span></span>
    
<span data-ttu-id="5db54-417">Чтобы пользователи могли использовать функцию "позвонить с рабочего", они также должны быть:</span><span class="sxs-lookup"><span data-stu-id="5db54-417">For users to be able to use Call via Work, they'll also need to be:</span></span>
  
- <span data-ttu-id="5db54-418">Назначена политика голосовой связи, в которой выбран параметр **включить Одновременный звонок для телефонов** .</span><span class="sxs-lookup"><span data-stu-id="5db54-418">Assigned a voice policy that has the **Enable simultaneous ringing of phones** option selected.</span></span>
    
- <span data-ttu-id="5db54-419">Назначена политика мобильности со свойством **енаблеаутсидевоице** , равным **true**.</span><span class="sxs-lookup"><span data-stu-id="5db54-419">Assigned a Mobility policy that has the **EnableOutsideVoice** set to **True**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="5db54-420">Пользователи, не поддерживающие корпоративную голосовую связь, могут использовать свои мобильные устройства для совершения звонков в Skype для VoIP или присоединяться к конференциям с помощью ссылки щелкните, чтобы присоединиться на мобильных устройствах, если соответствующие параметры настроены для соответствующей политики голосовой связи. у.</span><span class="sxs-lookup"><span data-stu-id="5db54-420">Users who aren't enabled for Enterprise Voice can use their mobile devices to make Skype to Skype VoIP calls or can join conferences by using the Click to Join link while on their mobile devices, if the appropriate options are set for the Voice policy they're associated with.</span></span> <span data-ttu-id="5db54-421">В разделе Планирование есть более подробные сведения.</span><span class="sxs-lookup"><span data-stu-id="5db54-421">There's more detail in the PLANNING topic.</span></span> 
  
### <a name="modify-global-mobility-policy"></a><span data-ttu-id="5db54-422">Изменение глобальной политики мобильности</span><span class="sxs-lookup"><span data-stu-id="5db54-422">Modify global Mobility policy</span></span>

1. <span data-ttu-id="5db54-423">Войдите в систему, используя учетную запись, которая является участником роли **CsAdministrator** , на компьютер, на котором установлены Командная консоль и **OCSCore** **консоли управления Skype для бизнеса Server** .</span><span class="sxs-lookup"><span data-stu-id="5db54-423">Log on, with an account that's a member of the **CsAdministrator** role, to a computer where **Skype for Business Server Management Shell** and **Ocscore** are installed.</span></span>
    
2. <span data-ttu-id="5db54-424">Запустите **консоль управления Skype для бизнеса Server**.</span><span class="sxs-lookup"><span data-stu-id="5db54-424">Start the **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="5db54-425">Отключите доступ к мобильному и мобильному телефону, введя:</span><span class="sxs-lookup"><span data-stu-id="5db54-425">Turn off access to Mobility and Call via Work globally by typing:</span></span>
    
   ```powershell
   Set-CsMobilityPolicy -EnableMobility $False -EnableOutsideVoice $False
   ```

    > [!NOTE]
    > <span data-ttu-id="5db54-426">Вы можете отключить функцию "позвонить с рабочего", не отключив доступ к мобильному режиму.</span><span class="sxs-lookup"><span data-stu-id="5db54-426">You can turn off Call via Work without turning off access to Mobility.</span></span> <span data-ttu-id="5db54-427">Но вы не можете отключить мобильное взаимодействие, не отключая функцию "позвонить через".</span><span class="sxs-lookup"><span data-stu-id="5db54-427">But you can't turn off Mobility without also turning off Call via Work.</span></span> 
  
    <span data-ttu-id="5db54-428">Для получения дополнительных сведений ознакомьтесь со статьей [Set — CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/set-csmobilitypolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="5db54-428">For more info, check out [Set-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/set-csmobilitypolicy?view=skype-ps).</span></span>
    
### <a name="modify-mobility-policy-by-site"></a><span data-ttu-id="5db54-429">Изменение политики мобильности по сайту</span><span class="sxs-lookup"><span data-stu-id="5db54-429">Modify Mobility policy by site</span></span>

1. <span data-ttu-id="5db54-430">Войдите в систему, используя учетную запись, которая является участником роли **CsAdministrator** , на компьютер, на котором установлены Командная консоль и **OCSCore** **консоли управления Skype для бизнеса Server** .</span><span class="sxs-lookup"><span data-stu-id="5db54-430">Log on, with an account that's a member of the **CsAdministrator** role, to a computer where **Skype for Business Server Management Shell** and **Ocscore** are installed.</span></span>
    
2. <span data-ttu-id="5db54-431">Запустите **консоль управления Skype для бизнеса Server**.</span><span class="sxs-lookup"><span data-stu-id="5db54-431">Start the **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="5db54-432">Вы можете создать политику на уровне сайта, отключить VoIP и видео, включить параметр требовать WiFi для IP-звука и требовать WiFi для IP-видео по сайту.</span><span class="sxs-lookup"><span data-stu-id="5db54-432">You can create a site-level policy, turn off VoIP and video, enable Require WiFi for IP Audio, and Require WiFi for IP Video by site.</span></span> <span data-ttu-id="5db54-433">Тип:</span><span class="sxs-lookup"><span data-stu-id="5db54-433">Type:</span></span>
    
   ```powershell
   New-CsMobilityPolicy -Identity site:<site identifier> -EnableIPAudioVideo $false -RequireWiFiForIPAudio $True -RequireWiFiforIPVideo $True
   ```

    <span data-ttu-id="5db54-434">Узнайте больше в статье [New – CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/new-csmobilitypolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="5db54-434">Learn more at [New-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/new-csmobilitypolicy?view=skype-ps).</span></span>
    
### <a name="modify-mobility-policy-by-user"></a><span data-ttu-id="5db54-435">Изменение политики мобильности по пользователям</span><span class="sxs-lookup"><span data-stu-id="5db54-435">Modify Mobility policy by user</span></span>

1. <span data-ttu-id="5db54-436">Войдите в систему, используя учетную запись, которая является участником роли **CsAdministrator** , на компьютер, на котором установлены Командная консоль и **OCSCore** **консоли управления Skype для бизнеса Server** .</span><span class="sxs-lookup"><span data-stu-id="5db54-436">Log on, with an account that's a member of the **CsAdministrator** role, to a computer where **Skype for Business Server Management Shell** and **Ocscore** are installed.</span></span>
    
2. <span data-ttu-id="5db54-437">Запустите **консоль управления Skype для бизнеса Server**.</span><span class="sxs-lookup"><span data-stu-id="5db54-437">Start the **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="5db54-438">Создание политик мобильности на уровне пользователей и выключение мобильности и звонки через работу по пользователям.</span><span class="sxs-lookup"><span data-stu-id="5db54-438">Create user level Mobility policies and turn off Mobility and Call via Work by user.</span></span> <span data-ttu-id="5db54-439">Тип:</span><span class="sxs-lookup"><span data-stu-id="5db54-439">Type:</span></span>
    
   ```powershell
   New-CsMobilityPolicy -Identity <policy name> -EnableMobility $False -EnableOutsideVoice $False
   Grant-CsMobilityPolicy -Identity <user identifier> -PolicyName <policy name>
   ```

    <span data-ttu-id="5db54-440">Ниже приведен пример с примерами данных.</span><span class="sxs-lookup"><span data-stu-id="5db54-440">A further example with sample data:</span></span>
    
   ```powershell
   New-CsMobilityPolicy "tag:disableOutsideVoice" -EnableOutsideVoice $False
   Grant-CsMobilityPolicy -Identity MobileUser1@contoso.com -PolicyName tag:disableOutsideVoice
   ```

    > [!NOTE]
    > <span data-ttu-id="5db54-441">Вы можете отключить функцию "позвонить с рабочего", не отключив доступ к мобильному режиму.</span><span class="sxs-lookup"><span data-stu-id="5db54-441">You can turn off Call via Work without turning off access to Mobility.</span></span> <span data-ttu-id="5db54-442">Но вы не можете отключить мобильное взаимодействие, не отключая функцию "позвонить через".</span><span class="sxs-lookup"><span data-stu-id="5db54-442">But you can't turn off Mobility without also turning off Call via Work.</span></span> 
  

