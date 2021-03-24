---
title: Развертывание и настройка мобильности для Skype для бизнес-сервера
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 8ec6197a-3d1e-4b42-9465-564044cdab1a
description: В этой статье вы сможете настроить существующую установку Skype для бизнес-сервера для использования службы мобильности, что позволит мобильным устройствам использовать функции мобильности Skype для бизнес-серверов.
ms.openlocfilehash: 2ba0a81350dac6e47f4e909b4cfba256ee90de18
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51103865"
---
# <a name="deploy-and-configure-mobility-for-skype-for-business-server"></a><span data-ttu-id="901e3-103">Развертывание и настройка мобильности для Skype для бизнес-сервера</span><span class="sxs-lookup"><span data-stu-id="901e3-103">Deploy and Configure Mobility for Skype for Business Server</span></span>  
 
<span data-ttu-id="901e3-104">В этой статье вы сможете настроить существующую установку Skype для бизнес-сервера для использования службы мобильности, что позволит мобильным устройствам использовать функции мобильности Skype для бизнес-серверов.</span><span class="sxs-lookup"><span data-stu-id="901e3-104">This article will walk you through the steps to configure an existing Skype for Business Server installation to use the Mobility service, allowing your mobile devices to be able to take advantage of Skype for Business Server Mobility features.</span></span>
  
<span data-ttu-id="901e3-105">Рассмотрев статью Plan [for Mobility for Skype for Business Server,](../plan-your-deployment/mobility.md) вы должны быть готовы приступить к приведенным ниже шагам, чтобы развернуть Mobility в среде Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="901e3-105">Having reviewed the [Plan for Mobility for Skype for Business Server](../plan-your-deployment/mobility.md) article, you should be ready to proceed with the steps below to deploy Mobility into your Skype for Business Server environment.</span></span> <span data-ttu-id="901e3-106">Действия следующие (и мы включаем в эту таблицу список разрешений):</span><span class="sxs-lookup"><span data-stu-id="901e3-106">The steps are as follows (and we're including in this table a permissions list):</span></span>
  
|<span data-ttu-id="901e3-107">**Этап**</span><span class="sxs-lookup"><span data-stu-id="901e3-107">**Phase**</span></span>|<span data-ttu-id="901e3-108">**Разрешения**</span><span class="sxs-lookup"><span data-stu-id="901e3-108">**Permissions**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="901e3-109">Создание записей DNS</span><span class="sxs-lookup"><span data-stu-id="901e3-109">Create DNS records</span></span>](deploy-and-configure-mobility.md#CreateDNSRec) <br/> |<span data-ttu-id="901e3-110">Администраторы домена</span><span class="sxs-lookup"><span data-stu-id="901e3-110">Domain Admins</span></span>  <br/> <span data-ttu-id="901e3-111">DNSAdmins</span><span class="sxs-lookup"><span data-stu-id="901e3-111">DNSAdmins</span></span>  <br/> |
|[<span data-ttu-id="901e3-112">Изменение сертификатов</span><span class="sxs-lookup"><span data-stu-id="901e3-112">Modify certificates</span></span>](deploy-and-configure-mobility.md#ModCerts) <br/> |<span data-ttu-id="901e3-113">Локальный администратор</span><span class="sxs-lookup"><span data-stu-id="901e3-113">Local Administrator</span></span>  <br/> |
|[<span data-ttu-id="901e3-114">Настройка обратного прокси-сервера</span><span class="sxs-lookup"><span data-stu-id="901e3-114">Configure the reverse proxy</span></span>](deploy-and-configure-mobility.md#ConfigRP) <br/> |<span data-ttu-id="901e3-115">Локальный администратор</span><span class="sxs-lookup"><span data-stu-id="901e3-115">Local Administrator</span></span>  <br/> |
|[<span data-ttu-id="901e3-116">Настройка автооткрытия для мобильности с помощью гибридных развертывания</span><span class="sxs-lookup"><span data-stu-id="901e3-116">Configure Autodiscover for Mobility with hybrid deployments</span></span>](deploy-and-configure-mobility.md#ConfigAutoD) <br/> |<span data-ttu-id="901e3-117">Администраторы домена</span><span class="sxs-lookup"><span data-stu-id="901e3-117">Domain Admins</span></span>  <br/> |
|[<span data-ttu-id="901e3-118">Тестирование развертывания мобильности</span><span class="sxs-lookup"><span data-stu-id="901e3-118">Test your Mobility deployment</span></span>](deploy-and-configure-mobility.md#TestMobility) <br/> |<span data-ttu-id="901e3-119">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="901e3-119">CsAdministrator</span></span>  <br/> |
|[<span data-ttu-id="901e3-120">Настройка для использования push-уведомлений</span><span class="sxs-lookup"><span data-stu-id="901e3-120">Configure for push notifications</span></span>](deploy-and-configure-mobility.md#ConfigPush) <br/> |<span data-ttu-id="901e3-121">RtcUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="901e3-121">RtcUniversalServerAdmins</span></span>  <br/> |
|[<span data-ttu-id="901e3-122">Настройка политики мобильности</span><span class="sxs-lookup"><span data-stu-id="901e3-122">Configure Mobility policy</span></span>](deploy-and-configure-mobility.md#ConfigMob) <br/> |<span data-ttu-id="901e3-123">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="901e3-123">CsAdministrator</span></span>  <br/> |
   
<span data-ttu-id="901e3-124">Во всех следующих разделах содержатся действия, которые предполагают, что вы читали тему Планирования.</span><span class="sxs-lookup"><span data-stu-id="901e3-124">All the following sections contain steps that assume you've read the Planning topic.</span></span> <span data-ttu-id="901e3-125">Если что-то вас сбивает с толку, не стесняйся проверять сведения.</span><span class="sxs-lookup"><span data-stu-id="901e3-125">If anything's confusing you, feel free to check out the information there.</span></span>

> [!NOTE]
> <span data-ttu-id="901e3-126">Поддержка mcX (Mobility Service) для устаревших мобильных клиентов больше недоступна в Skype для бизнеса Server 2019.</span><span class="sxs-lookup"><span data-stu-id="901e3-126">MCX (Mobility Service) support for legacy mobile clients is no longer available in Skype for Business Server 2019.</span></span> <span data-ttu-id="901e3-127">Все текущие мобильные клиенты Skype для бизнеса уже используют веб-API единой связи (UCWA) для поддержки обмена мгновенными сообщениями, присутствия и контактов.</span><span class="sxs-lookup"><span data-stu-id="901e3-127">All current Skype for Business mobile clients already use Unified Communications Web API (UCWA) to support instant messaging (IM), presence, and contacts.</span></span> <span data-ttu-id="901e3-128">Пользователям с устаревшими клиентами, использующими MCX, потребуется обновиться до текущего клиента.</span><span class="sxs-lookup"><span data-stu-id="901e3-128">Users with legacy clients using MCX will need to upgrade to a current client.</span></span>
  
## <a name="create-dns-records"></a><span data-ttu-id="901e3-129">Создание записей DNS</span><span class="sxs-lookup"><span data-stu-id="901e3-129">Create DNS records</span></span>
<span data-ttu-id="901e3-130"><a name="CreateDNSRec"> </a></span><span class="sxs-lookup"><span data-stu-id="901e3-130"><a name="CreateDNSRec"> </a></span></span>

<span data-ttu-id="901e3-131">Возможно, они уже есть в среде Skype для бизнеса Server, но для работы с автооткрытием необходимо создать следующие записи:</span><span class="sxs-lookup"><span data-stu-id="901e3-131">You may already have these as part of your Skype for Business Server environment, but you do need to create the following records for Autodiscovery to work:</span></span>
  
- <span data-ttu-id="901e3-132">Внутренняя запись DNS для поддержки мобильных пользователей, подключающихся из сети организации.</span><span class="sxs-lookup"><span data-stu-id="901e3-132">An internal DNS record to support mobile users who're connecting from within your organization's network.</span></span>
    
- <span data-ttu-id="901e3-133">Внешняя (или публичная) запись DNS для поддержки мобильных пользователей, подключающихся за пределами сети организации.</span><span class="sxs-lookup"><span data-stu-id="901e3-133">An external (or public) DNS record to support mobile users who're connecting from outside your organization's network.</span></span>
    
<span data-ttu-id="901e3-134">Эти записи могут быть именами A (host) или CNAME (вам не нужно делать обе записи, мы просто включаем шаги для всего здесь).</span><span class="sxs-lookup"><span data-stu-id="901e3-134">These records can be either A (host) names or CNAME records (you don't have to make both, we're just including the steps for everything here).</span></span>
  
### <a name="create-an-internal-dns-cname-record"></a><span data-ttu-id="901e3-135">Создание внутренней записи CNAME DNS</span><span class="sxs-lookup"><span data-stu-id="901e3-135">Create an internal DNS CNAME record</span></span>

1. <span data-ttu-id="901e3-136">Войдите на DNS-сервер в вашей сети, который является членом группы **администраторов** домена или **группы DnsAdmins.**</span><span class="sxs-lookup"><span data-stu-id="901e3-136">Log into a DNS server in your network that's either a member of the **Domain Admins** group or the **DnsAdmins** group.</span></span>
    
2. <span data-ttu-id="901e3-137">Нажмите **кнопку** Пуск , Выберите  административные средства **(возможно,** потребуется искать его, если это не вариант из меню "Пуск"), а затем нажмите **кнопку DNS,** чтобы открыть административную оснастку DNS.</span><span class="sxs-lookup"><span data-stu-id="901e3-137">Click **Start**, Choose **Administrative Tools** (you may need to **Search** for it if it's not an option off the Start menu), and then click **DNS** to open the DNS administrative snap-in.</span></span>
    
3. <span data-ttu-id="901e3-138">В левом окне консоли необходимо перейти к домену, который является домом для переднего конечного сервера Skype для  бизнеса Server, и расширить зоны передовой смотровой зоны.</span><span class="sxs-lookup"><span data-stu-id="901e3-138">In the left-hand pane of the console window, you'll need to go to the domain that's home to your Skype for Business Server's Front End Servers, and expand the **Forward Lookup Zones** there.</span></span>
    
4. <span data-ttu-id="901e3-139">У вас есть момент, чтобы узнать, какой из следующих ниже.</span><span class="sxs-lookup"><span data-stu-id="901e3-139">Take a moment to see which of the following you have:</span></span>
    
   - <span data-ttu-id="901e3-140">Любые записи хостов A или AAAA для переднего сервера (стандартный или корпоративный) или пула переднего конца (s).</span><span class="sxs-lookup"><span data-stu-id="901e3-140">Any host A or AAAA records for your Front End Server (Standard or Enterprise) or Front End pool(s).</span></span>
    
   - <span data-ttu-id="901e3-141">Любые записи хостов A или AAAA для пула директоров или директоров (необязательная конфигурация, которая может иметься в развертывании).</span><span class="sxs-lookup"><span data-stu-id="901e3-141">Any host A or AAAA records for a Director or Director pool (an optional configuration you may have in your deployment).</span></span>
    
5. <span data-ttu-id="901e3-142">После этого щелкните правой кнопкой мыши доменное имя SIP и выберите **New Alias (CNAME)** из меню.</span><span class="sxs-lookup"><span data-stu-id="901e3-142">Once you've noted this, right-click your SIP domain name, and then choose **New Alias (CNAME)** from the menu.</span></span>
    
6. <span data-ttu-id="901e3-143">В **текстовом** ящике имени Alias введите lyncdiscoverinternal для имени хозяина, для внутреннего URL-адреса службы автообнаружия.</span><span class="sxs-lookup"><span data-stu-id="901e3-143">In the **Alias name** textbox, type lyncdiscoverinternal for your host name, for the internal Autodiscover service URL.</span></span>
    
7. <span data-ttu-id="901e3-144">В полностью квалифицированном доменном имени **(FQDN** для целевого хоста) необходимо ввести или просмотреть внутренний FQDN веб-служб для вашего пула переднего конца (или одного переднего сервера, пула директора или директора), идентифицированного на шаге 4 выше.</span><span class="sxs-lookup"><span data-stu-id="901e3-144">In the **Fully qualified domain name (FQDN for target host**, you'll need to type or browse to the internal Web Services FQDN for your Front End pool (or single Front End Server, or Director pool or Director), identified in step 4 above.</span></span> <span data-ttu-id="901e3-145">Нажмите кнопку ОК, когда она будет введена.</span><span class="sxs-lookup"><span data-stu-id="901e3-145">Click OK when this is entered.</span></span>
    
8. <span data-ttu-id="901e3-146">Для каждого домена SIP, поддерживаемого в среде Skype для бизнеса Server, необходимо создать новую запись CNAME автооткрытки в зоне передающегося смотра.</span><span class="sxs-lookup"><span data-stu-id="901e3-146">You'll need to create a new Autodiscover CNAME record in the forward lookup zone for each SIP domain supported in your Skype for Business Server environment.</span></span>
    
### <a name="create-an-external-dns-cname-record"></a><span data-ttu-id="901e3-147">Создание внешней записи CNAME DNS</span><span class="sxs-lookup"><span data-stu-id="901e3-147">Create an external DNS CNAME record</span></span>

1. <span data-ttu-id="901e3-148">Эти действия являются общими, так как мы не можем сказать, какой общедоступный поставщик DNS вы можете использовать, но мы по-прежнему хотим помочь вам. Войдите в общедоступный поставщик DNS с учетной записью, которая сможет делать там новые записи DNS.</span><span class="sxs-lookup"><span data-stu-id="901e3-148">These steps are generic, because we can't tell what public DNS provider you might be using, but we still want to help you out. Please log into your public DNS provider with an account that will be able to make new DNS records there.</span></span>
    
2. <span data-ttu-id="901e3-149">На данный момент домен SIP уже должен существовать для Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="901e3-149">At this point in time, a SIP domain should already exist there for Skype for Business Server.</span></span> <span data-ttu-id="901e3-150">**Расширь зону forward Lookup** для этого домена SIP или откройте его иначе.</span><span class="sxs-lookup"><span data-stu-id="901e3-150">Expand the **Forward Lookup Zone** for this SIP domain, or otherwise open it up.</span></span>
    
3. <span data-ttu-id="901e3-151">У вас есть момент, чтобы узнать, какой из следующих ниже.</span><span class="sxs-lookup"><span data-stu-id="901e3-151">Take a moment to see which of the following you have:</span></span>
    
   - <span data-ttu-id="901e3-152">Любые записи хостов A или AAAA для переднего сервера (стандартный или корпоративный) или пула переднего конца (s).</span><span class="sxs-lookup"><span data-stu-id="901e3-152">Any host A or AAAA records for your Front End Server (Standard or Enterprise) or Front End pool(s).</span></span>
    
   - <span data-ttu-id="901e3-153">Любые записи хостов A или AAAA для пула директоров или директоров (необязательная конфигурация, которая может иметься в развертывании).</span><span class="sxs-lookup"><span data-stu-id="901e3-153">Any host A or AAAA records for a Director or Director pool (an optional configuration you may have in your deployment).</span></span>
    
4. <span data-ttu-id="901e3-154">После получения этой информации вы сможете выбрать вариант создания нового псевдонима **(CNAME).**</span><span class="sxs-lookup"><span data-stu-id="901e3-154">Once you have that information, you should be able to select an option for creating a **New Alias (CNAME)**.</span></span>
    
5. <span data-ttu-id="901e3-155">Теперь вы должны иметь возможность ввести имя **псевдонима,** необходимо ввести lyncdiscover здесь для внешнего URL-адреса службы автооткрытия.</span><span class="sxs-lookup"><span data-stu-id="901e3-155">Now you should be able to enter an **Alias Name**, you need to enter lyncdiscover here for the external Autodiscover service URL.</span></span>
    
6. <span data-ttu-id="901e3-156">Далее должна быть область для входа в **FQDN** для целевого хоста, это должен быть FQDN для вашего пула переднего конца (или одного переднего end Server, или пул директор или директор), определены в шаге 3 выше.</span><span class="sxs-lookup"><span data-stu-id="901e3-156">Next there should be an area to enter in a **FQDN for target host**, this will need to be the FQDN for your Front End pool (or single Front End Server, or Director pool or Director), identified in step 3 above.</span></span>
    
7. <span data-ttu-id="901e3-157">Возможно, вам потребуется сохранить здесь, или если вам потребуется создать дополнительные записи CNAME в зоне передовая смотровая зона каждого домена SIP в среде Skype для бизнеса Server, вы должны сделать это, но как только вы будете готовы, сохраните свою работу.</span><span class="sxs-lookup"><span data-stu-id="901e3-157">You may need to save here, or if you need to create additional CNAME records in the forward lookup zone of each SIP domain in your Skype for Business Server environment, you should do that, but once you're ready, save your work.</span></span>
    
### <a name="create-an-internal-dns-a-record"></a><span data-ttu-id="901e3-158">Создание внутренней записи DNS A</span><span class="sxs-lookup"><span data-stu-id="901e3-158">Create an internal DNS A record</span></span>

1. <span data-ttu-id="901e3-159">Войдите на DNS-сервер в вашей сети, который является членом группы **администраторов** домена или **группы DnsAdmins.**</span><span class="sxs-lookup"><span data-stu-id="901e3-159">Log into a DNS server in your network that's either a member of the **Domain Admins** group or the **DnsAdmins** group.</span></span>
    
2. <span data-ttu-id="901e3-160">Нажмите **кнопку** Пуск , Выберите  административные средства **(возможно,** потребуется искать его, если это не вариант из меню "Пуск"), а затем нажмите **кнопку DNS,** чтобы открыть административную оснастку DNS.</span><span class="sxs-lookup"><span data-stu-id="901e3-160">Click **Start**, Choose **Administrative Tools** (you may need to **Search** for it if it's not an option off the Start menu), and then click **DNS** to open the DNS administrative snap-in.</span></span>
    
3. <span data-ttu-id="901e3-161">В левом окне консоли необходимо перейти к домену, который является домом для переднего конечного сервера Skype для  бизнеса Server, и расширить зоны передовой смотровой зоны.</span><span class="sxs-lookup"><span data-stu-id="901e3-161">In the left-hand pane of the console window, you'll need to go to the domain that's home to your Skype for Business Server's Front End Servers, and expand the **Forward Lookup Zones** there.</span></span>
    
4. <span data-ttu-id="901e3-162">У вас есть момент, чтобы узнать, какой из следующих ниже.</span><span class="sxs-lookup"><span data-stu-id="901e3-162">Take a moment to see which of the following you have:</span></span>
    
   - <span data-ttu-id="901e3-163">Любые записи хостов A или AAAA для переднего сервера (стандартный или корпоративный) или пула переднего конца (s).</span><span class="sxs-lookup"><span data-stu-id="901e3-163">Any host A or AAAA records for your Front End Server (Standard or Enterprise) or Front End pool(s).</span></span>
    
   - <span data-ttu-id="901e3-164">Любые записи хостов A или AAAA для пула директоров или директоров (необязательная конфигурация, которая может иметься в развертывании).</span><span class="sxs-lookup"><span data-stu-id="901e3-164">Any host A or AAAA records for a Director or Director pool (an optional configuration you may have in your deployment).</span></span>
    
5. <span data-ttu-id="901e3-165">После этого щелкните правой кнопкой мыши доменное имя SIP и выберите новый хост **(A или AAAA)** из меню.</span><span class="sxs-lookup"><span data-stu-id="901e3-165">Once you've noted this, right-click your SIP domain name, and then choose **New Host (A or AAAA)** from the menu.</span></span>
    
6. <span data-ttu-id="901e3-166">В **текстовом** ящике Имя введите lyncdiscoverinternal для вашего имени хост-сайта, для внутреннего URL-адреса службы автообнаружа.</span><span class="sxs-lookup"><span data-stu-id="901e3-166">In the **Name** textbox, type lyncdiscoverinternal for your host name, for the internal Autodiscover service URL.</span></span>
    
7. <span data-ttu-id="901e3-167">В **текстовом** ящике IP-адреса введите внутренний IP-адрес веб-служб для переднего пула (или одного переднего сервера, пула директора или директора), который был определен на шаге 4 выше.</span><span class="sxs-lookup"><span data-stu-id="901e3-167">In the **IP Address** textbox, type the internal Web Services IP address for your Front End pool (or single Front End Server, or Director pool or Director), identified in step 4 above.</span></span>
    
8. <span data-ttu-id="901e3-168">После этого щелкните **Добавить хост** и нажмите **кнопку ОК.**</span><span class="sxs-lookup"><span data-stu-id="901e3-168">When this is done, click **Add Host**, and then click **OK**.</span></span>
    
9. <span data-ttu-id="901e3-169">Для каждого домена SIP, поддерживаемого в среде Skype для бизнеса Server, необходимо создать новые записи автооткрывающего или AAAA в зоне передовой смотровой деятельности.</span><span class="sxs-lookup"><span data-stu-id="901e3-169">You'll need to create a new Autodiscover A or AAAA records in the forward lookup zone for each SIP domain supported in your Skype for Business Server environment.</span></span> <span data-ttu-id="901e3-170">Для этого повторите действия в 6-8 раз больше, чем необходимо.</span><span class="sxs-lookup"><span data-stu-id="901e3-170">To do this, repeat steps 6-8 as many times as needed.</span></span>
    
10. <span data-ttu-id="901e3-171">Когда вы закончили, нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="901e3-171">When you're done, click **Done**.</span></span>
    
### <a name="create-an-external-dns-a-record"></a><span data-ttu-id="901e3-172">Создание внешней записи DNS A</span><span class="sxs-lookup"><span data-stu-id="901e3-172">Create an external DNS A record</span></span>

1. <span data-ttu-id="901e3-173">Эти действия являются общими, так как мы не можем сказать, какой общедоступный поставщик DNS вы можете использовать, но мы по-прежнему хотим помочь вам. Войдите в общедоступный поставщик DNS с учетной записью, которая сможет делать там новые записи DNS.</span><span class="sxs-lookup"><span data-stu-id="901e3-173">These steps are generic, because we can't tell what public DNS provider you might be using, but we still want to help you out. Please log into your public DNS provider with an account that will be able to make new DNS records there.</span></span>
    
2. <span data-ttu-id="901e3-174">На данный момент домен SIP уже должен существовать для Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="901e3-174">At this point in time, a SIP domain should already exist there for Skype for Business Server.</span></span> <span data-ttu-id="901e3-175">**Расширь зону forward Lookup** для этого домена SIP или откройте его иначе.</span><span class="sxs-lookup"><span data-stu-id="901e3-175">Expand the **Forward Lookup Zone** for this SIP domain, or otherwise open it up.</span></span>
    
3. <span data-ttu-id="901e3-176">У вас есть момент, чтобы узнать, какой из следующих ниже.</span><span class="sxs-lookup"><span data-stu-id="901e3-176">Take a moment to see which of the following you have:</span></span>
    
   - <span data-ttu-id="901e3-177">Любые записи хостов A или AAAA для переднего сервера (стандартный или корпоративный) или пула переднего конца (s).</span><span class="sxs-lookup"><span data-stu-id="901e3-177">Any host A or AAAA records for your Front End Server (Standard or Enterprise) or Front End pool(s).</span></span>
    
   - <span data-ttu-id="901e3-178">Любые записи хостов A или AAAA для пула директоров или директоров (необязательная конфигурация, которая может иметься в развертывании).</span><span class="sxs-lookup"><span data-stu-id="901e3-178">Any host A or AAAA records for a Director or Director pool (an optional configuration you may have in your deployment).</span></span>
    
4. <span data-ttu-id="901e3-179">После получения этой информации вы сможете выбрать вариант создания нового хоста **A или AAAA.**</span><span class="sxs-lookup"><span data-stu-id="901e3-179">Once you have that information, you should be able to select an option for creating a **New Host A or AAAA**.</span></span>
    
5. <span data-ttu-id="901e3-180">Теперь вы должны иметь возможность ввести **имя,** вам нужно ввести lyncdiscover здесь для внешнего URL-адреса службы автооткрытия.</span><span class="sxs-lookup"><span data-stu-id="901e3-180">Now you should be able to enter a **Name**, you need to enter lyncdiscover here for the external Autodiscover service URL.</span></span>
    
6. <span data-ttu-id="901e3-181">Далее должна быть область для ввода IP-адресов, это должен быть IP-адрес для вашего пула переднего конца (или одного переднего end Server, или пула директора или директора), определенного на шаге 3 выше.</span><span class="sxs-lookup"><span data-stu-id="901e3-181">Next there should be an area to enter in a **IP Addresss**, this will need to be the IP for your Front End pool (or single Front End Server, or Director pool or Director), identified in step 3 above.</span></span>
    
7. <span data-ttu-id="901e3-182">Возможно, вам потребуется сохранить здесь, или если вам потребуется создать дополнительные записи A или AAAA в зоне передовой проверки каждого домена SIP для среды Skype для бизнеса Server, вы должны сделать это, но как только вы будете готовы, сохраните свою работу.</span><span class="sxs-lookup"><span data-stu-id="901e3-182">You may need to save here, or if you need to create additional A or AAAA records in the forward lookup zone of each SIP domain for your Skype for Business Server environment, you should do that, but once you're ready, save your work.</span></span>
    
## <a name="modify-certificates"></a><span data-ttu-id="901e3-183">Изменение сертификатов</span><span class="sxs-lookup"><span data-stu-id="901e3-183">Modify certificates</span></span>
<span data-ttu-id="901e3-184"><a name="ModCerts"> </a></span><span class="sxs-lookup"><span data-stu-id="901e3-184"><a name="ModCerts"> </a></span></span>

<span data-ttu-id="901e3-185">Если у вас есть вопросы по планированию вокруг сертификатов, мы задокументировали это в статье [Plan for Mobility for Skype for Business Server.](../plan-your-deployment/mobility.md)</span><span class="sxs-lookup"><span data-stu-id="901e3-185">If you have questions about Planning around certificates, we've documented that in our [Plan for Mobility for Skype for Business Server](../plan-your-deployment/mobility.md) article.</span></span> <span data-ttu-id="901e3-186">После того, как вы рассмотрите этот вопрос, мы пройдите по следующим ниже.</span><span class="sxs-lookup"><span data-stu-id="901e3-186">Once you've reviewed that, we'll walk you through the following:</span></span>
  
- <span data-ttu-id="901e3-187">Нужны ли мне новые сертификаты?</span><span class="sxs-lookup"><span data-stu-id="901e3-187">Do I need new certificates?</span></span>
    
- <span data-ttu-id="901e3-188">Запрос новых сертификатов в Вашем органе сертификации (CA).</span><span class="sxs-lookup"><span data-stu-id="901e3-188">Requesting new certificates from your Certificate Authority (CA).</span></span>
    
- <span data-ttu-id="901e3-189">Обновление сертификатов на месте с помощью замены с помощью PowerShell.</span><span class="sxs-lookup"><span data-stu-id="901e3-189">Updating your in-place certificates with the replacements using PowerShell.</span></span>
    
- <span data-ttu-id="901e3-190">Проверка сертификатов с помощью snapin сертификатов в консоли управления Майкрософт (MMC).</span><span class="sxs-lookup"><span data-stu-id="901e3-190">Checking the certificates using the Certificates snapin in the Microsoft Management Console (MMC).</span></span>
    
### <a name="do-i-need-new-certificates"></a><span data-ttu-id="901e3-191">Нужны ли мне новые сертификаты?</span><span class="sxs-lookup"><span data-stu-id="901e3-191">Do I need new certificates?</span></span>

1. <span data-ttu-id="901e3-192">Во-первых, может потребоваться проверить и узнать, какие сертификаты находятся на месте, и есть ли у них необходимые записи.</span><span class="sxs-lookup"><span data-stu-id="901e3-192">First, you may need to check and see what certificates are in-place, and whether or not they have the entries you need.</span></span> <span data-ttu-id="901e3-193">Для этого необходимо войти в Skype для бизнеса Server с учетной записью местного администратора.</span><span class="sxs-lookup"><span data-stu-id="901e3-193">To do that, you'll need to log into your Skype for Business Server with an account that's a local Administrator.</span></span> <span data-ttu-id="901e3-194">Эта учетная запись может также иметь права на выдачу сертификата (CA), для некоторых из этих действий.</span><span class="sxs-lookup"><span data-stu-id="901e3-194">This account may also need to have rights to the issuing Certificate Authority (CA), for some of these steps.</span></span>
    
2. <span data-ttu-id="901e3-195">Откройте оболочку управления Skype для бизнес-серверов (поиск можно найти, если его не прикрепили к меню "Пуск" или панели задач).</span><span class="sxs-lookup"><span data-stu-id="901e3-195">Open the Skype for Business Server Management Shell (you can use Search to find it if you don't have it pinned to your Start menu or task bar).</span></span>
    
3. <span data-ttu-id="901e3-196">Необходимо знать, какие сертификаты были назначены перед добавлением обновленного сертификата.</span><span class="sxs-lookup"><span data-stu-id="901e3-196">It's going to be essential for you to know what certificates have been assigned before you try adding an updated certificate.</span></span> <span data-ttu-id="901e3-197">Поэтому в команду введите:</span><span class="sxs-lookup"><span data-stu-id="901e3-197">So at the command, type:</span></span>
    
   ```powershell
   Get-CsCertificate
   ```

4. <span data-ttu-id="901e3-198">Сведения из шага 3 будут уникальными для вас.</span><span class="sxs-lookup"><span data-stu-id="901e3-198">The information from Step 3 will be unique to you.</span></span> <span data-ttu-id="901e3-199">Чтобы определить, есть ли у вас один сертификат, который назначен для нескольких вещей, или вам назначен другой сертификат для различных компонентов, которые в них нуждаются.</span><span class="sxs-lookup"><span data-stu-id="901e3-199">You need to look it over to determine if you have a single certificate that's been assigned for multiple things, or whether you have a different certificate assigned for the different components that need them.</span></span> <span data-ttu-id="901e3-200">Параметр **Use** расскажет вам, как используется сертификат, а параметр **Thumbprint** покажет, является ли он все тем же сертификатом или несколькими сертификатами.</span><span class="sxs-lookup"><span data-stu-id="901e3-200">The **Use** parameter will tell you how a certificate's being used, and the **Thumbprint** parameter will tell you if it's all the same certificate, or multiple certs.</span></span>
    
5. <span data-ttu-id="901e3-201">Если у вас есть записи SAN, рекомендуемые в разделе Планирование, вы хороши.</span><span class="sxs-lookup"><span data-stu-id="901e3-201">If you have the SAN entries recommended in our Planning section, you're good.</span></span> <span data-ttu-id="901e3-202">Если нет, вам потребуется запросить новый сертификат или несколько сертификатов (в зависимости от конфигурации) в вашем органе сертификации.</span><span class="sxs-lookup"><span data-stu-id="901e3-202">If not, you'll need to request a new certificate, or multiple certificates (depending on your configuration) from your Certificate Authority.</span></span>
    
### <a name="request-a-new-certificate-or-certificates-from-your-certificate-authority-ca"></a><span data-ttu-id="901e3-203">Запрос нового сертификата или сертификатов в вашем органе сертификации (CA)</span><span class="sxs-lookup"><span data-stu-id="901e3-203">Request a new certificate, or certificates, from your Certificate Authority (CA)</span></span>

1. <span data-ttu-id="901e3-204">После проверки, чтобы узнать, какие записи san у вас есть, вы знаете, что у вас есть один сертификат **(после** проверки с помощью шагов выше), и вы узнали, что у вас нет всех записей, которые вам нужно.</span><span class="sxs-lookup"><span data-stu-id="901e3-204">After you've checked to see what SAN entries you have, you know you have a **single certificate** (after checking via the steps above), and you learned you don't have all the entries you need.</span></span> <span data-ttu-id="901e3-205">Необходимо сделать новый запрос сертификата в ЦС.</span><span class="sxs-lookup"><span data-stu-id="901e3-205">A new certificate request needs to be made to your CA.</span></span> <span data-ttu-id="901e3-206">Откройте Skype для бизнеса Server PowerShell:</span><span class="sxs-lookup"><span data-stu-id="901e3-206">Open your Skype for Business Server PowerShell:</span></span>
    
   - <span data-ttu-id="901e3-207">Для отсутствующих служб автооткрытия SAN (замена параметра -Ca на собственный путь сертификации).</span><span class="sxs-lookup"><span data-stu-id="901e3-207">For a missing Autodiscover Service SAN (replacing the -Ca parameter with your own Certificate Authority path):</span></span>
    
   ```powershell
   Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -Ca dc\myca -AllSipDomain -verbose
   ```

   - <span data-ttu-id="901e3-208">Теперь, если у вас несколько доменов SIP, вы не можете использовать параметр AllSipDomain, как в примере выше.</span><span class="sxs-lookup"><span data-stu-id="901e3-208">Now, if you have multiple SIP domains, you can't use the AllSipDomain parameter as in the example above.</span></span> <span data-ttu-id="901e3-209">Вместо этого необходимо использовать параметр DomainName.</span><span class="sxs-lookup"><span data-stu-id="901e3-209">You'll need to use the DomainName parameter instead.</span></span> <span data-ttu-id="901e3-210">При использовании параметра DomainName необходимо определить FQDN для записей lyncdiscoverinternal и lyncdiscover.</span><span class="sxs-lookup"><span data-stu-id="901e3-210">And when you use the DomainName parameter, you've got to define the FQDN for the lyncdiscoverinternal and lyncdiscover records.</span></span> <span data-ttu-id="901e3-211">Примером может быть (замена параметра -Ca на собственный путь сертификации):</span><span class="sxs-lookup"><span data-stu-id="901e3-211">An example would be (replacing the -Ca parameter with your own Certificate Authority path):</span></span>
    
   ```powershell
   Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -Ca dc\myca -DomainName "LyncdiscoverInternal.contoso.com, LyncdiscoverInternal.contoso.net" -verbose
   ```

2. <span data-ttu-id="901e3-212">Или, после проверки, чтобы узнать, какие записи SAN  у вас есть, вы обнаружили, что у вас есть несколько сертификатов, которые не имеют всех записей, которые вам нужно.</span><span class="sxs-lookup"><span data-stu-id="901e3-212">Or, after you've checked to see what SAN entries you have, you found you have **multiple certificates** that don't have all the entries you need.</span></span> <span data-ttu-id="901e3-213">Необходимо сделать новый запрос сертификата в ЦС.</span><span class="sxs-lookup"><span data-stu-id="901e3-213">A new certificate request needs to be made to your CA.</span></span> <span data-ttu-id="901e3-214">Откройте Skype для бизнеса Server PowerShell:</span><span class="sxs-lookup"><span data-stu-id="901e3-214">Open your Skype for Business Server PowerShell:</span></span>
    
   - <span data-ttu-id="901e3-215">Для отсутствующих служб автооткрытия SAN (замена параметра -Ca на собственный путь сертификации).</span><span class="sxs-lookup"><span data-stu-id="901e3-215">For a missing Autodiscover Service SAN (replacing the -Ca parameter with your own Certificate Authority path):</span></span>
    
   ```powershell
   Request-CsCertificate -New -Type WebServicesInternal -Ca dc\myca -AllSipDomain -verbose
   ```

   - <span data-ttu-id="901e3-216">Теперь, если у вас несколько доменов SIP, вы не можете использовать параметр AllSipDomain, как в примере выше.</span><span class="sxs-lookup"><span data-stu-id="901e3-216">Now, if you have multiple SIP domains, you can't use the AllSipDomain parameter as in the example above.</span></span> <span data-ttu-id="901e3-217">Вместо этого необходимо использовать параметр DomainName.</span><span class="sxs-lookup"><span data-stu-id="901e3-217">You'll need to use the DomainName parameter instead.</span></span> <span data-ttu-id="901e3-218">При использовании параметра DomainName необходимо определить FQDN для записей lyncdiscoverinternal и lyncdiscover.</span><span class="sxs-lookup"><span data-stu-id="901e3-218">And when you use the DomainName parameter, you've got to define the FQDN for the lyncdiscoverinternal and lyncdiscover records.</span></span> <span data-ttu-id="901e3-219">Примерами может быть (замена параметра -Ca на собственный путь сертификации).</span><span class="sxs-lookup"><span data-stu-id="901e3-219">Examples would be (replacing the -Ca parameter with your own Certificate Authority path):</span></span>
    
   ```powershell
   Request-CsCertificate -New -Type WebServicesInternal -Ca dc\myca -DomainName "LyncdiscoverInternal.contoso.com, LyncdiscoverInternal.contoso.net" -verbose
   ```

   ```powershell
   Request-CsCertificate -New -Type WebServicesExternal -Ca dc\myca -DomainName "Lyncdiscover.contoso.com, Lyncdiscover.contoso.net" -verbose
   ```

   - <span data-ttu-id="901e3-220">После того как новые сертификаты будут созданы ЦС, вам потребуется назначить их.</span><span class="sxs-lookup"><span data-stu-id="901e3-220">Once the new certificates have been generated by the CA, you're going to need to assign them.</span></span>
    
### <a name="assign-certificates-using-skype-for-business-server-management-shell"></a><span data-ttu-id="901e3-221">Назначение сертификатов с помощью оболочки управления Skype для бизнес-серверов</span><span class="sxs-lookup"><span data-stu-id="901e3-221">Assign certificates using Skype for Business Server Management Shell</span></span>

- <span data-ttu-id="901e3-222">В зависимости от того, что вы нашли в разделе Do I need new certifications above, необходимо выполнить один **из** следующих разделов.</span><span class="sxs-lookup"><span data-stu-id="901e3-222">Depending on what you found in the Do I need new certifications section above, you need to run **one** of the following.</span></span>
    
  - <span data-ttu-id="901e3-223">Если у вас есть один сертификат для всего (отпечатки пальцев идентичны), необходимо выполнить это:</span><span class="sxs-lookup"><span data-stu-id="901e3-223">If you have a single certificate for everything (the thumbprints are identical) then you need to run this:</span></span>
    
  ```powershell
  Set-CsCertificate -Type <certificate(s) from the Use parameter> -Thumbprint <unique identifier>
  ```

  - <span data-ttu-id="901e3-224">Если у вас есть разные сертификаты для вещей (отпечатки пальцев все разные), запустите это вместо этого:</span><span class="sxs-lookup"><span data-stu-id="901e3-224">If you've got different certificates for things (the thumbprints are all different), run this instead:</span></span>
    
  ```powershell
  Set-CsCertificate -Type Default -Thumbprint <certificate thumbprint>
  Set-CsCertificate -Type WebServicesInternal -Thumbprint <certificate thumbprint>
  Set-CsCertificate -Type WebServicesExternal -Thumbprint <certificate thumbprint>
  ```

### <a name="viewing-certificates-in-the-microsoft-management-console-mmc"></a><span data-ttu-id="901e3-225">Просмотр сертификатов в консоли управления Майкрософт (MMC)</span><span class="sxs-lookup"><span data-stu-id="901e3-225">Viewing certificates in the Microsoft Management Console (MMC)</span></span>

1. <span data-ttu-id="901e3-226">У вас есть возможность посмотреть на сертификаты с помощью оснастки Сертификаты для MMC.</span><span class="sxs-lookup"><span data-stu-id="901e3-226">You have an option to look at your certificates using the Certificates snap-in for the MMC.</span></span> <span data-ttu-id="901e3-227">Просто введите MMC в поиск, и он должен всплывать в качестве параметра приложения,.</span><span class="sxs-lookup"><span data-stu-id="901e3-227">Simply type MMC into search and it should pop up as an application option,.</span></span>
    
2. <span data-ttu-id="901e3-228">Чтобы добавить оснастку Сертификаты, необходимо щелкнуть **Файл,** а затем добавить или удалить клавишу **Snap-In...** (или клавиша **ярлыка Ctrl+M** также будет работать).</span><span class="sxs-lookup"><span data-stu-id="901e3-228">To add the Certificates snap-in, you'll need to click **File**, and then **Add/Remove Snap-In...** (or keyboard shortcut **Ctrl+M** would also work).</span></span> <span data-ttu-id="901e3-229">**Сертификаты** будут параметром в левой области, выберите его и затем **учетную** запись компьютера в всплывающее окно, а затем **далее**.</span><span class="sxs-lookup"><span data-stu-id="901e3-229">**Certificates** will be an option in the left-hand pane, select it and then **Computer Account** in the pop-up window, then **Next**.</span></span>
    
3. <span data-ttu-id="901e3-230">По-прежнему в всплывающее окно, по всей вероятности, вы делаете это на компьютере, где находятся  сертификаты, которые необходимо посмотреть, поэтому оставьте выбор на локальном компьютере, если это так.</span><span class="sxs-lookup"><span data-stu-id="901e3-230">Still in the pop-up window, in all likelihood you're doing this on the computer that's home to the certificates you need to look at, so leave the selection on **Local Computer** if that's so.</span></span> <span data-ttu-id="901e3-231">Если вы работаете на удаленном компьютере,  измените кнопку радио на другой компьютер, а затем введите FQDN компьютера или используйте кнопку **Просмотр** для поиска этого компьютера через AD.</span><span class="sxs-lookup"><span data-stu-id="901e3-231">If you're working on a remote machine, change the radio button to **Another Computer** and then either enter that computer's FQDN or use the **Browse** button to search for that computer through AD.</span></span> <span data-ttu-id="901e3-232">После выбора компьютера необходимо нажать кнопку **Готово,** когда  она будет готова, а затем ОК, чтобы добавить привязку к MMC.</span><span class="sxs-lookup"><span data-stu-id="901e3-232">After selecting the computer, you'll need to click **Finish** when ready, and then **OK** to add the snap-in to the MMC.</span></span>
    
4. <span data-ttu-id="901e3-233">**Расширь** раздел Сертификаты на левой области MMC.</span><span class="sxs-lookup"><span data-stu-id="901e3-233">Expand the **Certificates** section in the MMC's left-hand pane.</span></span> <span data-ttu-id="901e3-234">**Расширь также** личную папку, а затем выберите **Сертификаты.**</span><span class="sxs-lookup"><span data-stu-id="901e3-234">Expand the **Personal** folder as well, and then select **Certificates**.</span></span> <span data-ttu-id="901e3-235">Это позволяет увидеть сертификаты в этом магазине.</span><span class="sxs-lookup"><span data-stu-id="901e3-235">This lets you see the certificates in this store.</span></span>
    
5. <span data-ttu-id="901e3-236">Необходимо найти нужный сертификат, щелкнуть правой кнопкой мыши по ней и выбрать **Open.**</span><span class="sxs-lookup"><span data-stu-id="901e3-236">You need to locate the certificate you want to view, right-click on it, and choose **Open**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="901e3-237">Как узнать, что это за сертификат?</span><span class="sxs-lookup"><span data-stu-id="901e3-237">How do you know what certificate this is?</span></span> <span data-ttu-id="901e3-238">Это должен быть либо единственный сертификат, присвоенный всем для вашей фермы, либо у вас может быть несколько сертификатов для различных вещей, таких как Default, Внутренние веб-службы и т.д., в этом случае вам может потребоваться посмотреть несколько сертификатов.</span><span class="sxs-lookup"><span data-stu-id="901e3-238">It should be either the single certificate assigned to everything for your farm, or you may have multiple certificates for different things, like Default, Internal Web Services, etc., in which case you may need to look at multiple certificates.</span></span> <span data-ttu-id="901e3-239">Несколько сертификатов будут иметь один и тот же отпечатки пальцев.</span><span class="sxs-lookup"><span data-stu-id="901e3-239">Multiple certificates will have the same thumbprint.</span></span> 
  
6. <span data-ttu-id="901e3-240">После того, как вы добрались до **представления сертификата,** выберите **Сведения**.</span><span class="sxs-lookup"><span data-stu-id="901e3-240">Once you've gotten to the **Certificate** view, choose **Details**.</span></span> <span data-ttu-id="901e3-241">Это позволит вам увидеть имя субъекта сертификата при выборе **Subject,** а также будет показано назначенное имя субъекта и связанные свойства.</span><span class="sxs-lookup"><span data-stu-id="901e3-241">This will let you see the certificate subject name when you select **Subject**, and the assigned subject name and associated properties are shown.</span></span>
    
7. <span data-ttu-id="901e3-242">Кроме того, необходимо проверить записи **альтернативного имени субъекта.**</span><span class="sxs-lookup"><span data-stu-id="901e3-242">You'll also need to check the **Subject Alternate Name** entries.</span></span> <span data-ttu-id="901e3-243">Вы найдете один или несколько из следующих ниже.</span><span class="sxs-lookup"><span data-stu-id="901e3-243">You'll find one or more of the following:</span></span>
    
   - <span data-ttu-id="901e3-244">Имя пула для этого пула или имя одного сервера, если это не пул.</span><span class="sxs-lookup"><span data-stu-id="901e3-244">The pool name for this pool, or the single server name if this isn't a pool.</span></span>
    
   - <span data-ttu-id="901e3-245">Имя сервера, заданное сертификату.</span><span class="sxs-lookup"><span data-stu-id="901e3-245">The server name that the certificate is assigned to.</span></span>
    
   - <span data-ttu-id="901e3-246">Простые записи URL-адресов, как правило, встречаются и диалоговые номера.</span><span class="sxs-lookup"><span data-stu-id="901e3-246">Simple URL records, typically meet and dialin.</span></span>
    
   - <span data-ttu-id="901e3-247">Внешние имена внутренних и веб-служб веб-служб (например, webpool01.contoso.net, webpool01.contoso.com), основанные на вариантах, сделанных в topology Builder и перенастроеченных выборах веб-служб.</span><span class="sxs-lookup"><span data-stu-id="901e3-247">Web Services internal and Web Services external names (for example, webpool01.contoso.net, webpool01.contoso.com), based on choices made in Topology Builder and over-ridden Web Services selections.</span></span>
    
   - <span data-ttu-id="901e3-248">Если уже назначено, lyncdiscover.\<sipdomain\></span><span class="sxs-lookup"><span data-stu-id="901e3-248">If already assigned, the lyncdiscover.\<sipdomain\></span></span> <span data-ttu-id="901e3-249">и lyncdiscoverinternal.\<sipdomain\></span><span class="sxs-lookup"><span data-stu-id="901e3-249">and lyncdiscoverinternal.\<sipdomain\></span></span> <span data-ttu-id="901e3-250">записи.</span><span class="sxs-lookup"><span data-stu-id="901e3-250">records.</span></span>
    
     <span data-ttu-id="901e3-251">Вам потребуется проверить несколько сертификатов, если вам назначено несколько сертификатов (проверьте примечание выше).</span><span class="sxs-lookup"><span data-stu-id="901e3-251">You'll need to check multiple certificates if you have more than one assigned (check the Note above).</span></span>
    
8. <span data-ttu-id="901e3-252">Итак, если вы найдете lyncdiscover.\<sipdomain\></span><span class="sxs-lookup"><span data-stu-id="901e3-252">So, if you find lyncdiscover.\<sipdomain\></span></span> <span data-ttu-id="901e3-253">и lyncdiscoverinternal.\<sipdomain\></span><span class="sxs-lookup"><span data-stu-id="901e3-253">and lyncdiscoverinternal.\<sipdomain\></span></span> <span data-ttu-id="901e3-254">записи, вы получили это уже настроено.</span><span class="sxs-lookup"><span data-stu-id="901e3-254">records, you've got this configured already.</span></span> <span data-ttu-id="901e3-255">MMC можно закрыть.</span><span class="sxs-lookup"><span data-stu-id="901e3-255">You can close the MMC.</span></span>
    
9. <span data-ttu-id="901e3-256">Если они не назначены, вам потребуется либо сделать новый запрос сертификата (описанный выше), либо установить их после запроса (для этого рекомендуется следующее выше PowerShell).</span><span class="sxs-lookup"><span data-stu-id="901e3-256">If they aren't assigned, you'll either need to make a new certificate request (outlined above) or you need to install them post-request (we recommend the following the PowerShell above for that).</span></span>
    
## <a name="configure-the-reverse-proxy"></a><span data-ttu-id="901e3-257">Настройка обратного прокси-сервера</span><span class="sxs-lookup"><span data-stu-id="901e3-257">Configure the reverse proxy</span></span>
<span data-ttu-id="901e3-258"><a name="ConfigRP"> </a></span><span class="sxs-lookup"><span data-stu-id="901e3-258"><a name="ConfigRP"> </a></span></span>

<span data-ttu-id="901e3-259">Шаги ниже не предназначены для точного следованию.</span><span class="sxs-lookup"><span data-stu-id="901e3-259">The steps below are not meant to be followed exactly.</span></span> <span data-ttu-id="901e3-260">Это потому, что в предыдущих версиях продукта, мы бы прошли вас через, например, настройка шлюза управления угрозами (TMG), и если вы не используете это, вам потребуется выработать собственную версию оттуда.</span><span class="sxs-lookup"><span data-stu-id="901e3-260">That's because in previous versions of the product, we'd have walked you through, for example, configuring Threat Management Gateway (TMG) and if you weren't using that, you'd need to work out your own version from there.</span></span>
  
<span data-ttu-id="901e3-261">TMG больше не предлагается Корпорацией Майкрософт в качестве продукта, и если вам все еще нужно настроить его, вы можете посмотреть на шаги [Lync Server 2013](/previous-versions/office/lync-server-2013/lync-server-2013-configuring-the-reverse-proxy-for-mobility).</span><span class="sxs-lookup"><span data-stu-id="901e3-261">TMG is no longer being offered by Microsoft as a product, and if you still need to configure it, you can look at the [Lync Server 2013 steps](/previous-versions/office/lync-server-2013/lync-server-2013-configuring-the-reverse-proxy-for-mobility).</span></span> <span data-ttu-id="901e3-262">Но следующие сведения должны быть более общими, даже если мы не можем предоставить конкретные шаги по погонам для каждого обратного прокси там.</span><span class="sxs-lookup"><span data-stu-id="901e3-262">But the following information's intended to be more generally helpful, even if there's no way we can provide specific walkthrough steps for every Reverse proxy out there.</span></span>
  
<span data-ttu-id="901e3-263">У нас есть две основные вещи, которые следует учитывать:</span><span class="sxs-lookup"><span data-stu-id="901e3-263">We have two main things to consider:</span></span>
  
- <span data-ttu-id="901e3-264">Собираетесь ли вы делать ваш первоначальный запрос автооткрытия по HTTPS (который мы рекомендуем)?</span><span class="sxs-lookup"><span data-stu-id="901e3-264">Are you going to be doing your initial Autodiscover request over HTTPS (which we recommend)?</span></span>
    
  - <span data-ttu-id="901e3-265">Если у вас есть правило веб-публикации, его необходимо изменить.</span><span class="sxs-lookup"><span data-stu-id="901e3-265">If you have a web publishing rule, you need to modify it.</span></span>
    
  - <span data-ttu-id="901e3-266">Если у вас еще нет правила веб-публикации, его необходимо создать.</span><span class="sxs-lookup"><span data-stu-id="901e3-266">If you don't have a web publishing rule yet, you need to create it.</span></span>
    
- <span data-ttu-id="901e3-267">Если вы делаете первоначальный запрос автооткрытия по http, вам также потребуется создать или изменить это правило.</span><span class="sxs-lookup"><span data-stu-id="901e3-267">If you're doing your initial Autodiscover request over HTTP, then you'll need to create or modify that rule as well.</span></span>
    
> [!NOTE]
> <span data-ttu-id="901e3-268">**Важно** Значение прокси-времени — это число, которое будет отличаться от развертывания к развертыванию.</span><span class="sxs-lookup"><span data-stu-id="901e3-268">**Important** A Proxy time-out value is a number that will vary from deployment to deployment.</span></span> <span data-ttu-id="901e3-269">Необходимо отслеживать развертывание и изменять значение для наилучшего опыта для клиентов.</span><span class="sxs-lookup"><span data-stu-id="901e3-269">You should monitor your deployment and modify the value for the best experience for clients.</span></span> <span data-ttu-id="901e3-270">Возможно, вам удастся установить значение не более 200.</span><span class="sxs-lookup"><span data-stu-id="901e3-270">You may be able to set the value as low as 200.</span></span> <span data-ttu-id="901e3-271">Если вы поддерживаете мобильные клиенты Lync в вашей среде, необходимо установить значение 960, чтобы разрешить время отжима уведомлений из Office 365, которое имеет значение времени от времени 900.</span><span class="sxs-lookup"><span data-stu-id="901e3-271">If you are supporting Lync mobile clients in your environment, you should set the value to 960 to allow for push notification time-outs from Office 365, which have a time-out value of 900.</span></span> <span data-ttu-id="901e3-272">Вполне вероятно, что вам придется увеличить значение времени, чтобы избежать отключений клиента, когда значение слишком низкое, или уменьшить число, если подключения через прокси-сервер не отключается, но ясно долго после отключения клиента.</span><span class="sxs-lookup"><span data-stu-id="901e3-272">It is very likely that you will have to increase the time-out value to avoid client disconnects when the value is too low, or decrease the number if connections through the proxy do not disconnect but clear long after the client has disconnected.</span></span> <span data-ttu-id="901e3-273">Мониторинг и базовая настройка обычной среды — это единственный точный способ определения соответствующего параметра для этого значения.</span><span class="sxs-lookup"><span data-stu-id="901e3-273">Monitoring and baselining what is usual for your environment is the only accurate way to determine the appropriate setting for this value.</span></span>
  
### <a name="modify-the-existing-web-publishing-rule-for-your-external-autodiscover-san-and-url"></a><span data-ttu-id="901e3-274">Изменение существующего правила веб-публикации для внешнего SAN и URL-адреса автооткрытия</span><span class="sxs-lookup"><span data-stu-id="901e3-274">Modify the existing web publishing rule for your external Autodiscover SAN and URL</span></span>

1. <span data-ttu-id="901e3-275">Откройте обратный прокси-интерфейс.</span><span class="sxs-lookup"><span data-stu-id="901e3-275">Open your Reverse proxy interface.</span></span>
    
2. <span data-ttu-id="901e3-276">Вам потребуется найти правило веб-публикации и выбрать параметр Edit (он может находиться в меню или вкладке в зависимости от конфигурации обратного прокси-сервера).</span><span class="sxs-lookup"><span data-stu-id="901e3-276">You'll need to locate your web publishing rule, and choose the Edit option (it may be on a menu or tab, depending on your Reverse proxy configuration).</span></span>
    
3. <span data-ttu-id="901e3-277">Должна быть область, в которую должно быть задано, к чему применяется это правило веб-публикации.</span><span class="sxs-lookup"><span data-stu-id="901e3-277">There should be an area that states what this web publishing rule is applied to.</span></span> <span data-ttu-id="901e3-278">Необходимо изменить это правило для входящих сайтов или запросов для сайтов.</span><span class="sxs-lookup"><span data-stu-id="901e3-278">You need to modify this rule for incoming sites or requests for sites.</span></span> <span data-ttu-id="901e3-279">Вы собираетесь добавить **новую** запись.</span><span class="sxs-lookup"><span data-stu-id="901e3-279">You're going to **add** a new entry.</span></span>
    
4. <span data-ttu-id="901e3-280">Введите имя сайта автообнаружение (пример, который мы будем использовать lyncdiscover.contoso.com), и нажмите кнопку **ОК** или **Сохранить**, в зависимости от формата обратного прокси-сервера.</span><span class="sxs-lookup"><span data-stu-id="901e3-280">Type the name of your Autodiscover site (the example we'll use is lyncdiscover.contoso.com), and click **OK** or **Save**, depending on your Reverse proxy's format.</span></span>
    
5. <span data-ttu-id="901e3-281">Возможно, у вас есть новый сертификат с записью SAN с автозакрытием.</span><span class="sxs-lookup"><span data-stu-id="901e3-281">You may have a new certificate that has the Autodiscover SAN entry in it.</span></span> <span data-ttu-id="901e3-282">Это также необходимо установить и настроить для использования в соответствии с настройками обратного прокси-сервера.</span><span class="sxs-lookup"><span data-stu-id="901e3-282">That needs to be installed as well and configured for use according to your Reverse proxy's settings.</span></span> <span data-ttu-id="901e3-283">Обязательно сохраните все после завершения конфигурации.</span><span class="sxs-lookup"><span data-stu-id="901e3-283">Be sure to save everything when the configuration is completed.</span></span>
    
6. <span data-ttu-id="901e3-284">Если обратный прокси-сервер имеет функцию **Test,** используйте ее, чтобы убедиться, что все работает правильно.</span><span class="sxs-lookup"><span data-stu-id="901e3-284">If your Reverse proxy has a **Test** functionality, then please make use of it, to ensure everything's working properly.</span></span>
    
7. <span data-ttu-id="901e3-285">Возможно, вам потребуется повторить эти действия, если в вашей среде есть пул директоров или директоров (это означает, что у вас есть второе правило).</span><span class="sxs-lookup"><span data-stu-id="901e3-285">Now, you may need to repeat these steps if you have a Director or Director pool in your environment (this would mean you have a second rule).</span></span>
    
### <a name="create-a-web-publishing-rule-for-the-external-autodiscover-url"></a><span data-ttu-id="901e3-286">Создание правила веб-публикации для внешнего URL-адреса автооткрытия</span><span class="sxs-lookup"><span data-stu-id="901e3-286">Create a web publishing rule for the external Autodiscover URL</span></span>

1. <span data-ttu-id="901e3-287">Откройте обратный прокси-интерфейс.</span><span class="sxs-lookup"><span data-stu-id="901e3-287">Open your Reverse proxy interface.</span></span>
    
2. <span data-ttu-id="901e3-288">Необходимо определить, где в интерфейсе создаются правила веб-публикации, и выбрать параметр **New** или **Create** (он может находиться в меню или вкладке в зависимости от конфигурации обратного прокси-сервера).</span><span class="sxs-lookup"><span data-stu-id="901e3-288">You'll need to locate where in the interface you create your web publishing rules, and choose the **New** or **Create** option (it may be on a menu or tab, depending on your Reverse proxy configuration).</span></span> <span data-ttu-id="901e3-289">Вы ищете вариант создания нового правила веб-публикации.</span><span class="sxs-lookup"><span data-stu-id="901e3-289">You are looking for the option to create a new web publishing rule.</span></span>
    
3. <span data-ttu-id="901e3-290">Как правило, необходимо ввести следующую информацию:</span><span class="sxs-lookup"><span data-stu-id="901e3-290">Typically, you will need to enter the following information:</span></span>
    
   - <span data-ttu-id="901e3-291">**Имя:** имя правила</span><span class="sxs-lookup"><span data-stu-id="901e3-291">**Name**: the name for your rule</span></span>
    
   - <span data-ttu-id="901e3-292">**Действие правила.** В этом случае это правило **Разрешить,** вы позволяете что-то пройти через обратный прокси.</span><span class="sxs-lookup"><span data-stu-id="901e3-292">**Rule Action**: In this case it's an **Allow** rule, you're letting something pass through your Reverse proxy.</span></span>
    
   - <span data-ttu-id="901e3-293">Правило **публикации** или вариант, который вы выбираете, будет иметь один **веб-сайт или балансировку нагрузки.**</span><span class="sxs-lookup"><span data-stu-id="901e3-293">The **Publishing** rule or option you're choosing would be **single web site or load balancer**.</span></span>
    
   - <span data-ttu-id="901e3-294">Это должен быть **SSL для** внешнего доступа, выберите этот параметр.</span><span class="sxs-lookup"><span data-stu-id="901e3-294">This needs to be **SSL** for external access, choose that option.</span></span>
    
   - <span data-ttu-id="901e3-295">Вам потребуется опубликовать путь для внутренней публикации и ввести FQDN для внешних веб-служб в балансире нагрузки пула переднего конечного (или FQDN баланситора нагрузки пула директоров, если он есть), примером может быть sfb_pool01.contoso.local. </span><span class="sxs-lookup"><span data-stu-id="901e3-295">You're going to need to publish a path for **Internal Publishing**, and enter the FQDN for the external Web Services on your Front End pool's load balancer (or the FQDN of the Director pool's load balancer if you have one), an example would be sfb_pool01.contoso.local.</span></span>
    
   - <span data-ttu-id="901e3-296">Вы должны ввести _ в качестве пути к публикации, но вам также необходимо переназначить **/\\** исходный заглавный сайт\*\*.</span><span class="sxs-lookup"><span data-stu-id="901e3-296">You should type **/\\** _ as the path to be published, but you also need to _\*forward the original host header\*\*.</span></span>
    
   - <span data-ttu-id="901e3-297">Там будет возможность для **общедоступных или внешних сведений имя** или сведения.</span><span class="sxs-lookup"><span data-stu-id="901e3-297">There will be an option for **public or external name** details or information.</span></span> <span data-ttu-id="901e3-298">Это место, в которое вы сможете ввести:</span><span class="sxs-lookup"><span data-stu-id="901e3-298">This is the place where you'll be able to enter:</span></span>
    
   - <span data-ttu-id="901e3-299">**Принимать запросы,** но это должно быть для доменного имени.</span><span class="sxs-lookup"><span data-stu-id="901e3-299">**Accept requests**, but it should be for the domain name.</span></span>
    
   - <span data-ttu-id="901e3-300">Для **имени** необходимо ввести **lyncdiscover.**</span><span class="sxs-lookup"><span data-stu-id="901e3-300">For the **Name**, you should enter **lyncdiscover.**</span></span> <span data-ttu-id="901e3-301"><sipdomain> (это внешний URL-адрес службы автооткрытия).</span><span class="sxs-lookup"><span data-stu-id="901e3-301"><sipdomain> (this is the external Autodiscover Service URL).</span></span> <span data-ttu-id="901e3-302">Теперь, если создается правило для внешнего URL-адреса веб-служб в пуле переднего конца, необходимо ввести FQDN для внешних веб-служб в пуле переднего конца (например, lyncwebextpool01.contoso.com).</span><span class="sxs-lookup"><span data-stu-id="901e3-302">Now, if you're creating a rule for the external Web Services URL on the Front End pool, you'll need to type the FQDN for the external Web Services on your Front End pool (for example, lyncwebextpool01.contoso.com).</span></span>
    
   - <span data-ttu-id="901e3-303">Будет параметр **Path,** и вам потребуется ввести **/\\** \* здесь.</span><span class="sxs-lookup"><span data-stu-id="901e3-303">There will be a **Path** option, and you'll need to enter **/\\**\* here.</span></span>
    
   - <span data-ttu-id="901e3-304">Вам необходимо выбрать **SSL-слушатель** с вашим новым общедоступным сертификатом.</span><span class="sxs-lookup"><span data-stu-id="901e3-304">You'll need to select a **SSL Listener** with your up-to-date public certificate.</span></span>
    
   - <span data-ttu-id="901e3-305">**Делегирование проверки** подлинности должно быть настроено на **отсутствие делегирования,** но должна быть разрешена прямая проверка **подлинности** клиента.</span><span class="sxs-lookup"><span data-stu-id="901e3-305">**Authentication Delegation** should be set to **No delegation**, but direct client authentication **should** be allowed.</span></span>
    
   - <span data-ttu-id="901e3-306">Правило должно быть за установлено для **всех пользователей.**</span><span class="sxs-lookup"><span data-stu-id="901e3-306">The rule should be set to **All users**.</span></span>
    
   - <span data-ttu-id="901e3-307">Это должна быть вся информация, необходимая для создания этого правила и позволяет продолжить.</span><span class="sxs-lookup"><span data-stu-id="901e3-307">This should be all the information you need to create this rule and allow you to proceed.</span></span>
    
4. <span data-ttu-id="901e3-308">Необходимо убедиться в том, что исходный заглавный хозяйский **заглавник** будет переназначен.</span><span class="sxs-lookup"><span data-stu-id="901e3-308">You're going to need to ensure that the **original host header** is forwarded.</span></span>
    
5. <span data-ttu-id="901e3-309">Необходимо **также** настроить порты веб-сервера, чтобы сделать следующее:</span><span class="sxs-lookup"><span data-stu-id="901e3-309">The **Web Server** ports will need to be set as well, you'll need to do the following:</span></span>
    
   - <span data-ttu-id="901e3-310">**Перенаправление запросов в порт HTTP** и номер порта должен быть **8080**.</span><span class="sxs-lookup"><span data-stu-id="901e3-310">**Redirect requests to HTTP port** and the port number should be **8080**.</span></span>
    
   - <span data-ttu-id="901e3-311">**Запросы на перенаправление в порт SSL** и номер порта должен быть **4443**.</span><span class="sxs-lookup"><span data-stu-id="901e3-311">**Redirect requests to SSL port** and the port number should be **4443**.</span></span>
    
6. <span data-ttu-id="901e3-312">Когда все настроено, необходимо сохранить или применить их, а затем проверить правило.</span><span class="sxs-lookup"><span data-stu-id="901e3-312">When everything's configured, you'll need to save or apply these, and then you'll want to test the rule.</span></span>
    
### <a name="create-a-web-publishing-rule-for-port-80-optional"></a><span data-ttu-id="901e3-313">Создание правила веб-публикации для порта 80 (необязательный)</span><span class="sxs-lookup"><span data-stu-id="901e3-313">Create a web publishing rule for port 80 (Optional)</span></span>

1. <span data-ttu-id="901e3-314">Откройте обратный прокси-интерфейс.</span><span class="sxs-lookup"><span data-stu-id="901e3-314">Open your Reverse proxy interface.</span></span>
    
2. <span data-ttu-id="901e3-315">Необходимо определить, где в интерфейсе создаются правила веб-публикации, и выбрать параметр **New** или **Create** (он может находиться в меню или вкладке в зависимости от конфигурации обратного прокси-сервера).</span><span class="sxs-lookup"><span data-stu-id="901e3-315">You'll need to locate where in the interface you create your web publishing rules, and choose the **New** or **Create** option (it may be on a menu or tab, depending on your Reverse proxy configuration).</span></span> <span data-ttu-id="901e3-316">Вы ищете вариант создания нового правила веб-публикации.</span><span class="sxs-lookup"><span data-stu-id="901e3-316">You are looking for the option to create a new web publishing rule.</span></span>
    
3. <span data-ttu-id="901e3-317">Как правило, необходимо ввести следующую информацию:</span><span class="sxs-lookup"><span data-stu-id="901e3-317">Typically, you will need to enter the following information:</span></span>
    
   - <span data-ttu-id="901e3-318">**Имя:** имя правила</span><span class="sxs-lookup"><span data-stu-id="901e3-318">**Name**: the name for your rule</span></span>
    
   - <span data-ttu-id="901e3-319">**Действие правила.** В этом случае это правило **Разрешить,** вы позволяете что-то пройти через обратный прокси.</span><span class="sxs-lookup"><span data-stu-id="901e3-319">**Rule Action**: In this case it's an **Allow** rule, you're letting something pass through your Reverse proxy.</span></span>
    
   - <span data-ttu-id="901e3-320">Правило **публикации** или вариант, который вы выбираете, будет иметь один **веб-сайт или балансировку нагрузки.**</span><span class="sxs-lookup"><span data-stu-id="901e3-320">The **Publishing** rule or option you're choosing would be **single web site or load balancer**.</span></span>
    
   - <span data-ttu-id="901e3-321">Это должно быть не защищенное подключение, чтобы подключиться к **опубликованной веб-сервер или ферму**.</span><span class="sxs-lookup"><span data-stu-id="901e3-321">This needs to be a **non-secured connection to connect to the published Web server or farm**.</span></span>
    
   - <span data-ttu-id="901e3-322">Вам потребуется опубликовать путь для внутренней публикации **и** ввести FQDN для **VIP-адреса** балансира нагрузки вашего переднего конечного пула, пример будет sfb_pool01.contoso.local.</span><span class="sxs-lookup"><span data-stu-id="901e3-322">You're going to need to publish a path for **Internal Publishing**, and enter the FQDN for the **VIP address** of your Front End pool's load balancer, an example would be sfb_pool01.contoso.local.</span></span>
    
   - <span data-ttu-id="901e3-323">Вы должны ввести _ в качестве пути к публикации, но вам также необходимо переназначить **/\\** исходный заглавный сайт\*\*.</span><span class="sxs-lookup"><span data-stu-id="901e3-323">You should type **/\\** _ as the path to be published, but you also need to _\*forward the original host header\*\*.</span></span>
    
   - <span data-ttu-id="901e3-324">Там будет возможность для **общедоступных или внешних сведений имя** или сведения.</span><span class="sxs-lookup"><span data-stu-id="901e3-324">There will be an option for **public or external name** details or information.</span></span> <span data-ttu-id="901e3-325">Это место, в которое вы сможете ввести:</span><span class="sxs-lookup"><span data-stu-id="901e3-325">This is the place where you'll be able to enter:</span></span>
    
   - <span data-ttu-id="901e3-326">**Принимать запросы,** но это должно быть для доменного имени.</span><span class="sxs-lookup"><span data-stu-id="901e3-326">**Accept requests**, but it should be for the domain name.</span></span>
    
   - <span data-ttu-id="901e3-327">Для **имени** необходимо ввести **lyncdiscover.**</span><span class="sxs-lookup"><span data-stu-id="901e3-327">For the **Name**, you should enter **lyncdiscover.**</span></span> <span data-ttu-id="901e3-328"><sipdomain> (это внешний URL-адрес службы автооткрытия).</span><span class="sxs-lookup"><span data-stu-id="901e3-328"><sipdomain> (this is the external Autodiscover Service URL).</span></span>
    
   - <span data-ttu-id="901e3-329">Будет параметр **Path,** и вам потребуется ввести **/\\** \* здесь.</span><span class="sxs-lookup"><span data-stu-id="901e3-329">There will be a **Path** option, and you'll need to enter **/\\**\* here.</span></span>
    
   - <span data-ttu-id="901e3-330">Вам потребуется выбрать веб-слушателя или разрешить обратному прокси-серверу создать его для вас.</span><span class="sxs-lookup"><span data-stu-id="901e3-330">You'll need to select a web listener, or allow your Reverse proxy to create one for you.</span></span>
    
   - <span data-ttu-id="901e3-331">**Делегирование проверки** подлинности должно быть настроено на **"Нет** делегирования", но прямая проверка подлинности клиента **не** должна быть разрешена.</span><span class="sxs-lookup"><span data-stu-id="901e3-331">**Authentication Delegation** should be set to **No delegation**, but direct client authentication **should not** be allowed.</span></span>
    
   - <span data-ttu-id="901e3-332">Правило должно быть за установлено для **всех пользователей.**</span><span class="sxs-lookup"><span data-stu-id="901e3-332">The rule should be set to **All users**.</span></span>
    
   - <span data-ttu-id="901e3-333">Это должна быть вся информация, необходимая для создания этого правила и позволяет продолжить.</span><span class="sxs-lookup"><span data-stu-id="901e3-333">This should be all the information you need to create this rule and allow you to proceed.</span></span>
    
4. <span data-ttu-id="901e3-334">Необходимо **установить** порты веб-сервера, чтобы сделать следующее:</span><span class="sxs-lookup"><span data-stu-id="901e3-334">The **Web Server** ports will need to be set, you'll need to do the following:</span></span>
    
   - <span data-ttu-id="901e3-335">**Перенаправление запросов в порт HTTP** и номер порта должен быть **8080**.</span><span class="sxs-lookup"><span data-stu-id="901e3-335">**Redirect requests to HTTP port** and the port number should be **8080**.</span></span>
    
   - <span data-ttu-id="901e3-336">**Запросы на перенаправление в порт SSL** и номер порта должен быть **4443**.</span><span class="sxs-lookup"><span data-stu-id="901e3-336">**Redirect requests to SSL port** and the port number should be **4443**.</span></span>
    
5. <span data-ttu-id="901e3-337">Когда все настроено, необходимо сохранить или применить их, а затем проверить правило.</span><span class="sxs-lookup"><span data-stu-id="901e3-337">When everything's configured, you'll need to save or apply these, and then you'll want to test the rule.</span></span>
    
## <a name="configure-autodiscover-for-mobility-with-hybrid-deployments"></a><span data-ttu-id="901e3-338">Настройка автооткрытия для мобильности с помощью гибридных развертывания</span><span class="sxs-lookup"><span data-stu-id="901e3-338">Configure Autodiscover for Mobility with hybrid deployments</span></span>
<span data-ttu-id="901e3-339"><a name="ConfigAutoD"> </a></span><span class="sxs-lookup"><span data-stu-id="901e3-339"><a name="ConfigAutoD"> </a></span></span>

<span data-ttu-id="901e3-340">Гибридные среды в Skype для бизнеса Server — это среды, которые объединяют локальное пространство и среду O365.</span><span class="sxs-lookup"><span data-stu-id="901e3-340">Hybrid environments in Skype for Business Server are environments that combine an on-premises and O365 environment.</span></span> <span data-ttu-id="901e3-341">Когда Skype для бизнеса Server работает в гибридной среде, служба автооткрытия должна быть в состоянии найти пользователя из любой из этих сред.</span><span class="sxs-lookup"><span data-stu-id="901e3-341">When you have Skype for Business Server working in a Hybrid environment, the Autodiscover service needs to be able to locate a user from either of these environments.</span></span>
  
<span data-ttu-id="901e3-342">Чтобы мобильные клиенты узнали, где находится пользователь, службу автооткрытия необходимо настроить с помощью нового единого локатора ресурсов (URL-адрес).</span><span class="sxs-lookup"><span data-stu-id="901e3-342">To let mobile clients discover where a user's located, the Autodiscover service needs to be configured with a new uniform resource locator (URL).</span></span> <span data-ttu-id="901e3-343">Ниже описана последовательность действий.</span><span class="sxs-lookup"><span data-stu-id="901e3-343">The steps are:</span></span>
  
1. <span data-ttu-id="901e3-344">Откройте оболочку управления Skype для бизнес-серверов.</span><span class="sxs-lookup"><span data-stu-id="901e3-344">Open Skype for Business Server Management Shell.</span></span>
    
2. <span data-ttu-id="901e3-345">Запустите следующее, чтобы получить значение атрибута **ProxyFQDN** для среды Skype для бизнеса Server:</span><span class="sxs-lookup"><span data-stu-id="901e3-345">Run the following to get the value of the attribute **ProxyFQDN** for your Skype for Business Server environment:</span></span>
    
   ```powershell
   Get-CsHostingProvider
   ```

3. <span data-ttu-id="901e3-346">Затем, еще в окне оболочки, запустите:</span><span class="sxs-lookup"><span data-stu-id="901e3-346">Then, still in the shell window, run:</span></span>
    
   ```powershell
   Set-CsHostingProvider -Identity [identity] -AutodiscoverUrl https://webdir.online.lync.com/autodiscover/autodiscoverservice.svc/root
   ```

    <span data-ttu-id="901e3-347">Где [идентификатор] заменяется именем домена общего пространства адресов SIP.</span><span class="sxs-lookup"><span data-stu-id="901e3-347">Where [identity] is replaced with the domain name of the shared SIP address space.</span></span>
    
## <a name="test-your-mobility-deployment"></a><span data-ttu-id="901e3-348">Тестирование развертывания мобильности</span><span class="sxs-lookup"><span data-stu-id="901e3-348">Test your Mobility deployment</span></span>
<span data-ttu-id="901e3-349"><a name="TestMobility"> </a></span><span class="sxs-lookup"><span data-stu-id="901e3-349"><a name="TestMobility"> </a></span></span>

<span data-ttu-id="901e3-350">После развертывания службы мобильности Skype для бизнес-серверов и службы автообнаружия Skype для бизнес-серверов необходимо выполнить тестовую транзакцию, чтобы убедиться, что развертывание работает правильно.</span><span class="sxs-lookup"><span data-stu-id="901e3-350">Once you've deployed Skype for Business Server Mobility Service and Skype for Business Server Autodiscover Service, you'll want to run a test transaction, to make sure your deployment's working right.</span></span> <span data-ttu-id="901e3-351">Вы можете запустить **Test-CsUcwaConference,** чтобы проверить способность двух пользователей создавать, присоединяться и общаться на конференции.</span><span class="sxs-lookup"><span data-stu-id="901e3-351">You can run **Test-CsUcwaConference** to test the ability of two users to create, join and communicate in a conference.</span></span> <span data-ttu-id="901e3-352">Для этого тестирования потребуется два пользователя (реальные или тестовые) и полные учетные данные.</span><span class="sxs-lookup"><span data-stu-id="901e3-352">You will need two users (real or test) and their full credentials to do this testing.</span></span> <span data-ttu-id="901e3-353">Эта команда будет работать как для клиентов Skype для бизнеса, так и для клиентов Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="901e3-353">This command will work for both Skype for Business clients as well as Lync Server 2013 clients.</span></span>
  
<span data-ttu-id="901e3-354">Для клиентов Lync Server 2010 в Skype для бизнеса Server 2015 необходимо выполнить **тестирование Test-CsMcxP2PIM.**</span><span class="sxs-lookup"><span data-stu-id="901e3-354">For Lync Server 2010 clients on Skype for Business Server 2015, you'll need to run **Test-CsMcxP2PIM** to test.</span></span> <span data-ttu-id="901e3-355">Пользователи Lync Server 2010 по-прежнему должны быть реальными пользователями или заранее задав свои учетные данные паролей.</span><span class="sxs-lookup"><span data-stu-id="901e3-355">Your Lync Server 2010 users will still have to be actual users, or predefined test users, and you'll need their password credentials.</span></span>

> [!NOTE]
> <span data-ttu-id="901e3-356">Поддержка mcX (Mobility Service) для устаревших мобильных клиентов больше недоступна в Skype для бизнеса Server 2019.</span><span class="sxs-lookup"><span data-stu-id="901e3-356">MCX (Mobility Service) support for legacy mobile clients is no longer available in Skype for Business Server 2019.</span></span> <span data-ttu-id="901e3-357">Все текущие мобильные клиенты Skype для бизнеса уже используют веб-API единой связи (UCWA) для поддержки обмена мгновенными сообщениями, присутствия и контактов.</span><span class="sxs-lookup"><span data-stu-id="901e3-357">All current Skype for Business mobile clients already use Unified Communications Web API (UCWA) to support instant messaging (IM), presence, and contacts.</span></span> <span data-ttu-id="901e3-358">Пользователям с устаревшими клиентами, использующими MCX, потребуется обновиться до текущего клиента.</span><span class="sxs-lookup"><span data-stu-id="901e3-358">Users with legacy clients using MCX will need to upgrade to a current client.</span></span>
  
### <a name="test-conferencing-for-skype-for-business-and-lync-2013-mobile-clients"></a><span data-ttu-id="901e3-359">Тестирование для мобильных клиентов Skype для бизнеса и Lync 2013</span><span class="sxs-lookup"><span data-stu-id="901e3-359">Test conferencing for Skype for Business and Lync 2013 mobile clients</span></span>

1. <span data-ttu-id="901e3-360">Войдите в систему в качестве члена **роли CsAdministrator** на любом компьютере, на котором установлены **Оболочка** управления Skype для бизнес-серверов и **Ocscore.**</span><span class="sxs-lookup"><span data-stu-id="901e3-360">Log on as a member of the **CsAdministrator** role on any computer where **Skype for Business Server Management Shell** and **Ocscore** are installed.</span></span>
    
2. <span data-ttu-id="901e3-361">Запустите **оболочку управления Skype для** бизнес-серверов (вы можете ввести имя в поиске или перейти во все программы и выбрать его). </span><span class="sxs-lookup"><span data-stu-id="901e3-361">Start the **Skype for Business Server Management Shell** (you might type the name in search or go to **All Programs** and choose it).</span></span>
    
3. <span data-ttu-id="901e3-362">В командной строке введите:</span><span class="sxs-lookup"><span data-stu-id="901e3-362">At the command line, enter:</span></span>
    
   ```powershell
   Test-CsUcwaConference -TargetFqdn <FQDN of Front End pool> -Authentication <TrustedServer | Negotiate | ClientCertificate | LiveID> -OrganizerSipAddress sip:<SIP address of test user 1> -OrganizerCredential <test user 1 credentials> -ParticipantSipAddress sip:<SIP address of test user 2> -ParticipantCredential <test user 2 credentials> -v
   ```

   <span data-ttu-id="901e3-363">Также можно установить учетные данные в скрипте и передать их в тестовый комдлет.</span><span class="sxs-lookup"><span data-stu-id="901e3-363">It's also possible to set credentials in a script and pass them to the test cmdlet.</span></span> <span data-ttu-id="901e3-364">Ниже приведен пример этого.</span><span class="sxs-lookup"><span data-stu-id="901e3-364">We have an example of this below.</span></span>
    
   ```powershell
   $passwd1 = ConvertTo-SecureString "Password01" -AsPlainText -Force
   $passwd2 = ConvertTo-SecureString "Password02" -AsPlainText -Force
   $testuser1 = New-Object Management.Automation.PSCredential("contoso\UserName1", $passwd1)
   $testuser2 = New-Object Management.Automation.PSCredential("contoso\UserName2", $passwd2)
   Test-CsUcwaConference -TargetFqdn pool01.contoso.com -Authentication Negotiate -OrganizerSipAddress sip:UserName1@contoso.com -OrganizerCredential $testuser1 -ParticipantSipAddress sip:UserName2@contoso.com -ParticipantCredential $testuser2 -v
   ```

### <a name="test-conferencing-for-lync-2010-mobile-clients"></a><span data-ttu-id="901e3-365">Тестирование для мобильных клиентов Lync 2010</span><span class="sxs-lookup"><span data-stu-id="901e3-365">Test conferencing for Lync 2010 mobile clients</span></span>

> [!NOTE]
> <span data-ttu-id="901e3-366">Поддержка mcX (Mobility Service) для устаревших мобильных клиентов больше недоступна в Skype для бизнеса Server 2019.</span><span class="sxs-lookup"><span data-stu-id="901e3-366">MCX (Mobility Service) support for legacy mobile clients is no longer available in Skype for Business Server 2019.</span></span> <span data-ttu-id="901e3-367">Все текущие мобильные клиенты Skype для бизнеса уже используют веб-API единой связи (UCWA) для поддержки обмена мгновенными сообщениями, присутствия и контактов.</span><span class="sxs-lookup"><span data-stu-id="901e3-367">All current Skype for Business mobile clients already use Unified Communications Web API (UCWA) to support instant messaging (IM), presence, and contacts.</span></span> <span data-ttu-id="901e3-368">Пользователям с устаревшими клиентами, использующими MCX, потребуется обновиться до текущего клиента.</span><span class="sxs-lookup"><span data-stu-id="901e3-368">Users with legacy clients using MCX will need to upgrade to a current client.</span></span>

1. <span data-ttu-id="901e3-369">Войдите в систему в качестве члена **роли CsAdministrator** на любом компьютере, на котором установлены **Оболочка** управления Skype для бизнес-серверов и **Ocscore.**</span><span class="sxs-lookup"><span data-stu-id="901e3-369">Log on as a member of the **CsAdministrator** role on any computer where **Skype for Business Server Management Shell** and **Ocscore** are installed.</span></span>
    
2. <span data-ttu-id="901e3-370">Запустите **оболочку управления Skype для** бизнес-серверов (вы можете ввести имя в поиске или перейти во все программы и выбрать его). </span><span class="sxs-lookup"><span data-stu-id="901e3-370">Start the **Skype for Business Server Management Shell** (you might type the name in search or go to **All Programs** and choose it).</span></span>
    
3. <span data-ttu-id="901e3-371">В командной строке введите:</span><span class="sxs-lookup"><span data-stu-id="901e3-371">At the command line, enter:</span></span>
    
   ```powershell
   Test-CsMcxP2PIM -TargetFqdn <FQDN of Front End pool> -Authentication <TrustedServer | Negotiate | ClientCertificate | LiveID> -SenderSipAddress sip:<SIP address of test user 1> -SenderCredential <test user 1 credentials> -ReceiverSipAddress sip:<SIP address of test user 2> -ReceiverCredential <test user 2 credentials> -v
   ```

   <span data-ttu-id="901e3-372">Также можно установить учетные данные в скрипте и передать их в тестовый комдлет.</span><span class="sxs-lookup"><span data-stu-id="901e3-372">It's also possible to set credentials in a script and pass them to the test cmdlet.</span></span> <span data-ttu-id="901e3-373">Ниже приведен пример этого.</span><span class="sxs-lookup"><span data-stu-id="901e3-373">We have an example of this below.</span></span>
    
   ```powershell
   $passwd1 = ConvertTo-SecureString "Password01" -AsPlainText -Force
   $passwd2 = ConvertTo-SecureString "Password02" -AsPlainText -Force
   $tuc1 = New-Object Management.Automation.PSCredential("contoso\UserName1", $passwd1)
   $tuc2 = New-Object Management.Automation.PSCredential("contoso\UserName2", $passwd2)
   Test-CsMcxP2PIM -TargetFqdn pool01.contoso.com -Authentication Negotiate -SenderSipAddress sip:UserName1@contoso.com -SenderCredential $tuc1 -ReceiverSipAddress sip:UserName2@contoso.com -ReceiverCredential $tuc2 -v
   ```

<span data-ttu-id="901e3-374">Чтобы просмотреть процедуры команд, вы можете проверить [Test-CsUcwaConference](/powershell/module/skype/test-csucwaconference?view=skype-ps) и [Test-CsMcxP2PIM.](/powershell/module/skype/test-csmcxp2pim?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="901e3-374">To review the command procedures further, you can check out [Test-CsUcwaConference](/powershell/module/skype/test-csucwaconference?view=skype-ps) and [Test-CsMcxP2PIM](/powershell/module/skype/test-csmcxp2pim?view=skype-ps).</span></span>
  
## <a name="configure-for-push-notifications"></a><span data-ttu-id="901e3-375">Настройка для использования push-уведомлений</span><span class="sxs-lookup"><span data-stu-id="901e3-375">Configure for push notifications</span></span>
<span data-ttu-id="901e3-376"><a name="ConfigPush"> </a></span><span class="sxs-lookup"><span data-stu-id="901e3-376"><a name="ConfigPush"> </a></span></span>

<span data-ttu-id="901e3-377">Push-уведомления в виде значков, значков или оповещений можно отправить на мобильное устройство, даже если приложение Skype или Lync неактивно.</span><span class="sxs-lookup"><span data-stu-id="901e3-377">Push notifications, in the form of badges, icons, or alerts, can be sent to a mobile device even when the Skype or Lync app is inactive.</span></span> <span data-ttu-id="901e3-378">Но что такое push-уведомления?</span><span class="sxs-lookup"><span data-stu-id="901e3-378">But what are push notifications?</span></span> <span data-ttu-id="901e3-379">Они являются оповещениями о событиях, например новым или пропущенным приглашением для чата, или для полученной голосовой почты.</span><span class="sxs-lookup"><span data-stu-id="901e3-379">They are event alerts, like a new or missed IM invitation, or for a received voicemail.</span></span> <span data-ttu-id="901e3-380">Служба мобильности бизнес-серверов Skype отправляет эти уведомления в облачную службу push-уведомлений Skype для бизнес-сервера, которая затем отправляет уведомления пользователям Windows Phone в Службу push-уведомлений Майкрософт (MSNS).</span><span class="sxs-lookup"><span data-stu-id="901e3-380">The Skype for Business Server Mobility service sends these notifications to the cloud-based Skype for Business Server Push Notification Service, which then sends the notifications to the Microsoft Push Notification Service (MSNS) for Windows Phone users.</span></span>
  
<span data-ttu-id="901e3-381">Эта функция не изменилась с Lync Server 2013, но если у вас есть Skype для бизнеса Server, вы хотите сделать следующее:</span><span class="sxs-lookup"><span data-stu-id="901e3-381">This functionality is unchanged from Lync Server 2013, but if you have a Skype for Business Server, you'll want to do the following:</span></span>
  
- <span data-ttu-id="901e3-382">Для сервера Skype для бизнеса Server Edge Server добавьте нового поставщика хостинга Microsoft Skype для бизнеса Online, а затем настроите федерацию поставщиков хостинга между организацией и Skype для бизнеса Online.</span><span class="sxs-lookup"><span data-stu-id="901e3-382">For a Skype for Business Server Edge Server, add a new hosting provider, Microsoft Skype for Business Online, and then set up hosting provider federation between your organization and Skype for Business Online.</span></span>
    
- <span data-ttu-id="901e3-383">Включить push-уведомления, запуская комлет **Set-CsPushNotificationConfiguration.**</span><span class="sxs-lookup"><span data-stu-id="901e3-383">Enable push notifications by running the **Set-CsPushNotificationConfiguration** cmdlet.</span></span> <span data-ttu-id="901e3-384">По умолчанию push-уведомления отключены.</span><span class="sxs-lookup"><span data-stu-id="901e3-384">By default, push notifications are turned off.</span></span>
    
- <span data-ttu-id="901e3-385">Проверьте конфигурацию федерации и push-уведомления.</span><span class="sxs-lookup"><span data-stu-id="901e3-385">Test your federation configuration and push notifications.</span></span>
    
### <a name="configure-your-skype-for-business-edge-server-for-push-notifications"></a><span data-ttu-id="901e3-386">Настройка сервера Skype для бизнеса для push-уведомлений</span><span class="sxs-lookup"><span data-stu-id="901e3-386">Configure your Skype for Business Edge Server for push notifications</span></span>

1. <span data-ttu-id="901e3-387">Войдите в систему с учетной записью, которая входит в роль **CsAdministrator,** на компьютер, на котором установлены **оболочка** управления Skype для бизнес-серверов и **Ocscore.**</span><span class="sxs-lookup"><span data-stu-id="901e3-387">Log on, with an account that's a member of the **CsAdministrator** role, to a computer where **Skype for Business Server Management Shell** and **Ocscore** are installed.</span></span>
    
2. <span data-ttu-id="901e3-388">Запустите **оболочку управления Skype для бизнес-серверов.**</span><span class="sxs-lookup"><span data-stu-id="901e3-388">Start the **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="901e3-389">Добавьте поставщика веб-хостинга Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="901e3-389">Add a Skype for Business Server online hosting provider.</span></span>
    
   ```powershell
   New-CsHostingProvider -Identity <unique identifier for hosting provider> -Enabled $True -ProxyFQDN <FQDN for the Access Server used by the hosting provider> -VerificationLevel UseSourceVerification
   ```

   <span data-ttu-id="901e3-390">Например:</span><span class="sxs-lookup"><span data-stu-id="901e3-390">As an example:</span></span>
    
   ```powershell
   New-CsHostingProvider -Identity "SkypeOnline" -Enabled $True -ProxyFQDN "sipfed.online.lync.com" -VerificationLevel UseSourceVerification
   ```

    > [!NOTE]
    > <span data-ttu-id="901e3-391">Вы не можете иметь несколько отношений федерации с одним поставщиком хостинга.</span><span class="sxs-lookup"><span data-stu-id="901e3-391">You can't have more than one federation relationship with a single hosting provider.</span></span> <span data-ttu-id="901e3-392">Таким образом, если вы уже создали поставщика хостинга, который имеет отношение федерации с sipfed.online.lync.com, не добавляйте другого поставщика хостинга для него, даже если удостоверение поставщика хостинга является чем-то иным, чем SkypeOnline.</span><span class="sxs-lookup"><span data-stu-id="901e3-392">So, if you've already set up a hosting provider that has a federation relationship with sipfed.online.lync.com, don't add another hosting provider for it, even if the identity of the hosting provider is something other than SkypeOnline.</span></span> 
  
4. <span data-ttu-id="901e3-393">Настройка федерации поставщиков хостинга между организацией и службой push-уведомлений в Skype для бизнеса Online.</span><span class="sxs-lookup"><span data-stu-id="901e3-393">Set up the hosting provider federation between your organization and the Push Notification Service at Skype for Business Online.</span></span> <span data-ttu-id="901e3-394">В командной строке необходимо ввести:</span><span class="sxs-lookup"><span data-stu-id="901e3-394">At the command line, you'll need to type:</span></span>
    
   ```powershell
    New-CsAllowedDomain -Identity "push.lync.com"
   ```

### <a name="enable-push-notifications"></a><span data-ttu-id="901e3-395">Включить push-уведомления</span><span class="sxs-lookup"><span data-stu-id="901e3-395">Enable push notifications</span></span>

1. <span data-ttu-id="901e3-396">Войдите в систему с учетной записью, которая входит в роль **CsAdministrator,** на компьютер, на котором установлены **оболочка** управления Skype для бизнес-серверов и **Ocscore.**</span><span class="sxs-lookup"><span data-stu-id="901e3-396">Log on, with an account that's a member of the **CsAdministrator** role, to a computer where **Skype for Business Server Management Shell** and **Ocscore** are installed.</span></span>
    
2. <span data-ttu-id="901e3-397">Запустите **оболочку управления Skype для бизнес-серверов.**</span><span class="sxs-lookup"><span data-stu-id="901e3-397">Start the **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="901e3-398">Включить push-уведомления:</span><span class="sxs-lookup"><span data-stu-id="901e3-398">Enable push notifications:</span></span>
    
   ```powershell
   Set-CsPushNotificationConfiguration -EnableMicrosoftPushNotificationService $True
   ```

4. <span data-ttu-id="901e3-399">Включить Федерацию:</span><span class="sxs-lookup"><span data-stu-id="901e3-399">Enable Federation:</span></span>
     
   ```powershell
   Set-CsAccessEdgeConfiguration -AllowFederatedUsers $True
   ```

### <a name="test-federation-and-push-notifications"></a><span data-ttu-id="901e3-400">Тестирование федерации и push-уведомлений</span><span class="sxs-lookup"><span data-stu-id="901e3-400">Test federation and push notifications</span></span>

1. <span data-ttu-id="901e3-401">Войдите в систему с учетной записью, которая входит в роль **CsAdministrator,** на компьютер, на котором установлены **оболочка** управления Skype для бизнес-серверов и **Ocscore.**</span><span class="sxs-lookup"><span data-stu-id="901e3-401">Log on, with an account that's a member of the **CsAdministrator** role, to a computer where **Skype for Business Server Management Shell** and **Ocscore** are installed.</span></span>
    
2. <span data-ttu-id="901e3-402">Запустите **оболочку управления Skype для бизнес-серверов.**</span><span class="sxs-lookup"><span data-stu-id="901e3-402">Start the **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="901e3-403">Проверьте конфигурацию федерации:</span><span class="sxs-lookup"><span data-stu-id="901e3-403">Test the federation configuration:</span></span>
    
   ```powershell
   Test-CsFederatedPartner -TargetFqdn <FQDN of Access Edge server used for federated SIP traffic> -Domain <FQDN of federated domain> -ProxyFqdn <FQDN of the Access Edge server used by the federated organization>
   ```

    <span data-ttu-id="901e3-404">Например:</span><span class="sxs-lookup"><span data-stu-id="901e3-404">As an example:</span></span>
    
   ```powershell
   Test-CsFederatedPartner -TargetFqdn accessproxy.contoso.com -Domain push.lync.com -ProxyFqdn sipfed.online.lync.com
   ```

4. <span data-ttu-id="901e3-405">Проверьте push-уведомления:</span><span class="sxs-lookup"><span data-stu-id="901e3-405">Test your push notifications:</span></span>
    
   ```powershell
   Test-CsMcxPushNotification -AccessEdgeFqdn <Access Edge service FQDN>
   ```

    <span data-ttu-id="901e3-406">Например:</span><span class="sxs-lookup"><span data-stu-id="901e3-406">As an example:</span></span>
    
   ```powershell
   Test-CsMcxPushNotification -AccessEdgeFqdn accessproxy.contoso.com
   ```

## <a name="configure-mobility-policy"></a><span data-ttu-id="901e3-407">Настройка политики мобильности</span><span class="sxs-lookup"><span data-stu-id="901e3-407">Configure Mobility policy</span></span>
<span data-ttu-id="901e3-408"><a name="ConfigMob"> </a></span><span class="sxs-lookup"><span data-stu-id="901e3-408"><a name="ConfigMob"> </a></span></span>

<span data-ttu-id="901e3-409">У вас есть возможность с Помощью Skype для бизнес-сервера определить, кто может использовать службу мобильности, звонок через работу, голос через IP (VoIP) или видео, а также потребуется ли Wi-Fi для VoIP или видео.</span><span class="sxs-lookup"><span data-stu-id="901e3-409">You have the ability with Skype for Business Server to determine who can use your Mobility service, Call via Work, voice over IP (VoIP), or video, as well as whether WiFi will be required for VoIP or video.</span></span> <span data-ttu-id="901e3-410">Вызов через Work позволяет мобильному пользователю использовать рабочий номер телефона, а не номер мобильного телефона при размещении и приеме вызовов.</span><span class="sxs-lookup"><span data-stu-id="901e3-410">Call via Work lets a mobile user use their work phone number, instead of their mobile phone number, when placing and receiving calls.</span></span> <span data-ttu-id="901e3-411">Пользователь на другом конце строки не увидит номер мобильного телефона пользователя, и это позволяет мобильному пользователю избегать исходяющих звонков.</span><span class="sxs-lookup"><span data-stu-id="901e3-411">The person on the other end of the line won't see that mobile user's cell phone number, and it lets that mobile user avoid outgoing call charges.</span></span> <span data-ttu-id="901e3-412">При настройках VoIP и видео пользователи могут принимать и делать voIP-звонки и видео.</span><span class="sxs-lookup"><span data-stu-id="901e3-412">When VoIP and video are set up, users can take and make VoIP calls and video.</span></span> <span data-ttu-id="901e3-413">Параметры использования Wi-Fi определяют, потребуется ли мобильному устройству пользователя использовать сеть Wi-Fi через сеть сотовых данных.</span><span class="sxs-lookup"><span data-stu-id="901e3-413">The settings for WiFi usage determine whether a user's mobile device will be required to use a WiFi network over a cellular data network.</span></span>
  
<span data-ttu-id="901e3-414">Мобильные устройства, вызовы с помощью work и функции VoIP и видео включены по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="901e3-414">Mobility, Call via Work, and the VoIP and video features are all enabled by default.</span></span> <span data-ttu-id="901e3-415">Параметр, в котором требуется Wi-Fi для VoIP и видео, отключен.</span><span class="sxs-lookup"><span data-stu-id="901e3-415">The setting to require WiFi for VoIP and video are disabled.</span></span> <span data-ttu-id="901e3-416">Администратор имеет возможность изменять это как глобально, так и по сайту, или по пользователю.</span><span class="sxs-lookup"><span data-stu-id="901e3-416">An Admin has the ability to change this, either globally, by site, or by user.</span></span>
  
<span data-ttu-id="901e3-417">Чтобы иметь возможность использовать функции Mobility и Call via Work, пользователям необходимо:</span><span class="sxs-lookup"><span data-stu-id="901e3-417">To be able to use Mobility features and Call via Work, users need to be:</span></span>
  
- <span data-ttu-id="901e3-418">Включен для Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="901e3-418">Enabled for Skype for Business Server</span></span>
    
- <span data-ttu-id="901e3-419">Включено для Корпоративная голосовая связь.</span><span class="sxs-lookup"><span data-stu-id="901e3-419">Enabled for Enterprise Voice.</span></span>
    
- <span data-ttu-id="901e3-420">Назначена политика мобильности с параметром **EnableMobility** для **True**.</span><span class="sxs-lookup"><span data-stu-id="901e3-420">Assigned a Mobility policy that has the **EnableMobility** option set to **True**.</span></span>
    
<span data-ttu-id="901e3-421">Чтобы пользователи могли использовать Call via Work, им также необходимо:</span><span class="sxs-lookup"><span data-stu-id="901e3-421">For users to be able to use Call via Work, they'll also need to be:</span></span>
  
- <span data-ttu-id="901e3-422">Назначена политика голосовой связи с выбранным параметром **Включить одновременный** звон телефонов.</span><span class="sxs-lookup"><span data-stu-id="901e3-422">Assigned a voice policy that has the **Enable simultaneous ringing of phones** option selected.</span></span>
    
- <span data-ttu-id="901e3-423">Назначена политика мобильности с набором **EnableOutsideVoice** для **True**.</span><span class="sxs-lookup"><span data-stu-id="901e3-423">Assigned a Mobility policy that has the **EnableOutsideVoice** set to **True**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="901e3-424">Пользователи, которые не включены для Корпоративная голосовая связь, могут использовать свои мобильные устройства для звонков Skype в VoIP Skype или присоединяться к конференциям с помощью ссылки Нажмите кнопку Присоединиться на мобильных устройствах, если для политики голосовой связи, с которыми они связаны, установлены соответствующие параметры.</span><span class="sxs-lookup"><span data-stu-id="901e3-424">Users who aren't enabled for Enterprise Voice can use their mobile devices to make Skype to Skype VoIP calls or can join conferences by using the Click to Join link while on their mobile devices, if the appropriate options are set for the Voice policy they're associated with.</span></span> <span data-ttu-id="901e3-425">Дополнительные подробности в разделе PLANNING.</span><span class="sxs-lookup"><span data-stu-id="901e3-425">There's more detail in the PLANNING topic.</span></span> 
  
### <a name="modify-global-mobility-policy"></a><span data-ttu-id="901e3-426">Изменение глобальной политики мобильности</span><span class="sxs-lookup"><span data-stu-id="901e3-426">Modify global Mobility policy</span></span>

1. <span data-ttu-id="901e3-427">Войдите в систему с учетной записью, которая входит в роль **CsAdministrator,** на компьютер, на котором установлены **оболочка** управления Skype для бизнес-серверов и **Ocscore.**</span><span class="sxs-lookup"><span data-stu-id="901e3-427">Log on, with an account that's a member of the **CsAdministrator** role, to a computer where **Skype for Business Server Management Shell** and **Ocscore** are installed.</span></span>
    
2. <span data-ttu-id="901e3-428">Запустите **оболочку управления Skype для бизнес-серверов.**</span><span class="sxs-lookup"><span data-stu-id="901e3-428">Start the **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="901e3-429">Отключите доступ к мобильности и вызову с помощью work глобально, введя:</span><span class="sxs-lookup"><span data-stu-id="901e3-429">Turn off access to Mobility and Call via Work globally by typing:</span></span>
    
   ```powershell
   Set-CsMobilityPolicy -EnableMobility $False -EnableOutsideVoice $False
   ```

    > [!NOTE]
    > <span data-ttu-id="901e3-430">Вы можете отключить вызов с помощью Work, не отключив доступ к Mobility.</span><span class="sxs-lookup"><span data-stu-id="901e3-430">You can turn off Call via Work without turning off access to Mobility.</span></span> <span data-ttu-id="901e3-431">Но вы не можете отключить Мобильность, не отключив вызов с помощью work.</span><span class="sxs-lookup"><span data-stu-id="901e3-431">But you can't turn off Mobility without also turning off Call via Work.</span></span> 
  
    <span data-ttu-id="901e3-432">Дополнительные сведения можно получить в [set-CsMobilityPolicy.](/powershell/module/skype/set-csmobilitypolicy?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="901e3-432">For more info, check out [Set-CsMobilityPolicy](/powershell/module/skype/set-csmobilitypolicy?view=skype-ps).</span></span>
    
### <a name="modify-mobility-policy-by-site"></a><span data-ttu-id="901e3-433">Изменение политики мобильности по сайту</span><span class="sxs-lookup"><span data-stu-id="901e3-433">Modify Mobility policy by site</span></span>

1. <span data-ttu-id="901e3-434">Войдите в систему с учетной записью, которая входит в роль **CsAdministrator,** на компьютер, на котором установлены **оболочка** управления Skype для бизнес-серверов и **Ocscore.**</span><span class="sxs-lookup"><span data-stu-id="901e3-434">Log on, with an account that's a member of the **CsAdministrator** role, to a computer where **Skype for Business Server Management Shell** and **Ocscore** are installed.</span></span>
    
2. <span data-ttu-id="901e3-435">Запустите **оболочку управления Skype для бизнес-серверов.**</span><span class="sxs-lookup"><span data-stu-id="901e3-435">Start the **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="901e3-436">Вы можете создать политику на уровне сайта, отключить VoIP и видео, включить require WiFi для IP-аудио и требовать Wi-Fi для IP-видео по сайту.</span><span class="sxs-lookup"><span data-stu-id="901e3-436">You can create a site-level policy, turn off VoIP and video, enable Require WiFi for IP Audio, and Require WiFi for IP Video by site.</span></span> <span data-ttu-id="901e3-437">Тип:</span><span class="sxs-lookup"><span data-stu-id="901e3-437">Type:</span></span>
    
   ```powershell
   New-CsMobilityPolicy -Identity site:<site identifier> -EnableIPAudioVideo $false -RequireWiFiForIPAudio $True -RequireWiFiforIPVideo $True
   ```

    <span data-ttu-id="901e3-438">Дополнительные новости в [New-CsMobilityPolicy](/powershell/module/skype/new-csmobilitypolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="901e3-438">Learn more at [New-CsMobilityPolicy](/powershell/module/skype/new-csmobilitypolicy?view=skype-ps).</span></span>
    
### <a name="modify-mobility-policy-by-user"></a><span data-ttu-id="901e3-439">Изменение политики мобильности пользователем</span><span class="sxs-lookup"><span data-stu-id="901e3-439">Modify Mobility policy by user</span></span>

1. <span data-ttu-id="901e3-440">Войдите в систему с учетной записью, которая входит в роль **CsAdministrator,** на компьютер, на котором установлены **оболочка** управления Skype для бизнес-серверов и **Ocscore.**</span><span class="sxs-lookup"><span data-stu-id="901e3-440">Log on, with an account that's a member of the **CsAdministrator** role, to a computer where **Skype for Business Server Management Shell** and **Ocscore** are installed.</span></span>
    
2. <span data-ttu-id="901e3-441">Запустите **оболочку управления Skype для бизнес-серверов.**</span><span class="sxs-lookup"><span data-stu-id="901e3-441">Start the **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="901e3-442">Создайте политики мобильности уровня пользователя и отключите мобильность и вызов с помощью work пользователем.</span><span class="sxs-lookup"><span data-stu-id="901e3-442">Create user level Mobility policies and turn off Mobility and Call via Work by user.</span></span> <span data-ttu-id="901e3-443">Тип:</span><span class="sxs-lookup"><span data-stu-id="901e3-443">Type:</span></span>
    
   ```powershell
   New-CsMobilityPolicy -Identity <policy name> -EnableMobility $False -EnableOutsideVoice $False
   Grant-CsMobilityPolicy -Identity <user identifier> -PolicyName <policy name>
   ```

    <span data-ttu-id="901e3-444">Дополнительный пример с примерами данных:</span><span class="sxs-lookup"><span data-stu-id="901e3-444">A further example with sample data:</span></span>
    
   ```powershell
   New-CsMobilityPolicy "tag:disableOutsideVoice" -EnableOutsideVoice $False
   Grant-CsMobilityPolicy -Identity MobileUser1@contoso.com -PolicyName tag:disableOutsideVoice
   ```

    > [!NOTE]
    > <span data-ttu-id="901e3-445">Вы можете отключить вызов с помощью Work, не отключив доступ к Mobility.</span><span class="sxs-lookup"><span data-stu-id="901e3-445">You can turn off Call via Work without turning off access to Mobility.</span></span> <span data-ttu-id="901e3-446">Но вы не можете отключить Мобильность, не отключив вызов с помощью work.</span><span class="sxs-lookup"><span data-stu-id="901e3-446">But you can't turn off Mobility without also turning off Call via Work.</span></span> 
