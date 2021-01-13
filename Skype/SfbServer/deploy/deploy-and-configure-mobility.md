---
title: Развертывание и настройка мобильности для Skype для бизнеса Server
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
description: В этой статье представлены по шагам по настройке существующей установки Skype для бизнеса Server для использования службы Mobility Service, что позволит мобильным устройствам использовать функции Skype для бизнеса Server Mobility.
ms.openlocfilehash: 420d34dcf1406df776e438e01007770e515c0d4a
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49820899"
---
# <a name="deploy-and-configure-mobility-for-skype-for-business-server"></a><span data-ttu-id="e134c-103">Развертывание и настройка мобильности для Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="e134c-103">Deploy and Configure Mobility for Skype for Business Server</span></span>  
 
<span data-ttu-id="e134c-104">В этой статье представлены по шагам по настройке существующей установки Skype для бизнеса Server для использования службы Mobility Service, что позволит мобильным устройствам использовать функции Skype для бизнеса Server Mobility.</span><span class="sxs-lookup"><span data-stu-id="e134c-104">This article will walk you through the steps to configure an existing Skype for Business Server installation to use the Mobility service, allowing your mobile devices to be able to take advantage of Skype for Business Server Mobility features.</span></span>
  
<span data-ttu-id="e134c-105">Просмотрев статью "Планирование мобильности для Skype для бизнеса [Server",](../plan-your-deployment/mobility.md) вы должны быть готовы приступить к приведенной ниже работе по развертыванию mobility в среде Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="e134c-105">Having reviewed the [Plan for Mobility for Skype for Business Server](../plan-your-deployment/mobility.md) article, you should be ready to proceed with the steps below to deploy Mobility into your Skype for Business Server environment.</span></span> <span data-ttu-id="e134c-106">Ниже следуют шаги (и мы включаем в эту таблицу список разрешений):</span><span class="sxs-lookup"><span data-stu-id="e134c-106">The steps are as follows (and we're including in this table a permissions list):</span></span>
  
|<span data-ttu-id="e134c-107">**Этап**</span><span class="sxs-lookup"><span data-stu-id="e134c-107">**Phase**</span></span>|<span data-ttu-id="e134c-108">**Разрешения**</span><span class="sxs-lookup"><span data-stu-id="e134c-108">**Permissions**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="e134c-109">Создание записей DNS</span><span class="sxs-lookup"><span data-stu-id="e134c-109">Create DNS records</span></span>](deploy-and-configure-mobility.md#CreateDNSRec) <br/> |<span data-ttu-id="e134c-110">Администраторы домена</span><span class="sxs-lookup"><span data-stu-id="e134c-110">Domain Admins</span></span>  <br/> <span data-ttu-id="e134c-111">DNSAdmins</span><span class="sxs-lookup"><span data-stu-id="e134c-111">DNSAdmins</span></span>  <br/> |
|[<span data-ttu-id="e134c-112">Изменение сертификатов</span><span class="sxs-lookup"><span data-stu-id="e134c-112">Modify certificates</span></span>](deploy-and-configure-mobility.md#ModCerts) <br/> |<span data-ttu-id="e134c-113">Локальный администратор</span><span class="sxs-lookup"><span data-stu-id="e134c-113">Local Administrator</span></span>  <br/> |
|[<span data-ttu-id="e134c-114">Настройка обратного прокси-сервера</span><span class="sxs-lookup"><span data-stu-id="e134c-114">Configure the reverse proxy</span></span>](deploy-and-configure-mobility.md#ConfigRP) <br/> |<span data-ttu-id="e134c-115">Локальный администратор</span><span class="sxs-lookup"><span data-stu-id="e134c-115">Local Administrator</span></span>  <br/> |
|[<span data-ttu-id="e134c-116">Настройка автооружия для мобильной работы с гибридными развертываниями</span><span class="sxs-lookup"><span data-stu-id="e134c-116">Configure Autodiscover for Mobility with hybrid deployments</span></span>](deploy-and-configure-mobility.md#ConfigAutoD) <br/> |<span data-ttu-id="e134c-117">Администраторы домена</span><span class="sxs-lookup"><span data-stu-id="e134c-117">Domain Admins</span></span>  <br/> |
|[<span data-ttu-id="e134c-118">Тестирование развертывания mobility</span><span class="sxs-lookup"><span data-stu-id="e134c-118">Test your Mobility deployment</span></span>](deploy-and-configure-mobility.md#TestMobility) <br/> |<span data-ttu-id="e134c-119">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="e134c-119">CsAdministrator</span></span>  <br/> |
|[<span data-ttu-id="e134c-120">Настройка для использования push-уведомлений</span><span class="sxs-lookup"><span data-stu-id="e134c-120">Configure for push notifications</span></span>](deploy-and-configure-mobility.md#ConfigPush) <br/> |<span data-ttu-id="e134c-121">RtcUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="e134c-121">RtcUniversalServerAdmins</span></span>  <br/> |
|[<span data-ttu-id="e134c-122">Настройка политики мобильности</span><span class="sxs-lookup"><span data-stu-id="e134c-122">Configure Mobility policy</span></span>](deploy-and-configure-mobility.md#ConfigMob) <br/> |<span data-ttu-id="e134c-123">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="e134c-123">CsAdministrator</span></span>  <br/> |
   
<span data-ttu-id="e134c-124">Во всех следующих разделах содержатся действия, предполагая, что вы прочли раздел "Планирование".</span><span class="sxs-lookup"><span data-stu-id="e134c-124">All the following sections contain steps that assume you've read the Planning topic.</span></span> <span data-ttu-id="e134c-125">Если что-то вас запутает, вы можете найти там информацию.</span><span class="sxs-lookup"><span data-stu-id="e134c-125">If anything's confusing you, feel free to check out the information there.</span></span>

> [!NOTE]
> <span data-ttu-id="e134c-126">Поддержка СЛУЖБЫ MCX (Mobility Service) для устаревших мобильных клиентов больше недоступна в Skype для бизнеса Server 2019.</span><span class="sxs-lookup"><span data-stu-id="e134c-126">MCX (Mobility Service) support for legacy mobile clients is no longer available in Skype for Business Server 2019.</span></span> <span data-ttu-id="e134c-127">Все текущие мобильные клиенты Skype для бизнеса уже используют веб-API объединенных коммуникаций (UCWA) для поддержки обмена мгновенными сообщениями, присутствия и контактов.</span><span class="sxs-lookup"><span data-stu-id="e134c-127">All current Skype for Business mobile clients already use Unified Communications Web API (UCWA) to support instant messaging (IM), presence, and contacts.</span></span> <span data-ttu-id="e134c-128">Пользователям с устаревшими клиентами, использующими MCX, потребуется обновиться до текущего клиента.</span><span class="sxs-lookup"><span data-stu-id="e134c-128">Users with legacy clients using MCX will need to upgrade to a current client.</span></span>
  
## <a name="create-dns-records"></a><span data-ttu-id="e134c-129">Создание записей DNS</span><span class="sxs-lookup"><span data-stu-id="e134c-129">Create DNS records</span></span>
<span data-ttu-id="e134c-130"><a name="CreateDNSRec"> </a></span><span class="sxs-lookup"><span data-stu-id="e134c-130"><a name="CreateDNSRec"> </a></span></span>

<span data-ttu-id="e134c-131">Возможно, эти записи уже есть в среде Skype для бизнеса Server, но для работы автоотнаружия необходимо создать следующие записи:</span><span class="sxs-lookup"><span data-stu-id="e134c-131">You may already have these as part of your Skype for Business Server environment, but you do need to create the following records for Autodiscovery to work:</span></span>
  
- <span data-ttu-id="e134c-132">Внутренняя запись DNS для поддержки мобильных пользователей, подключающихся из сети организации.</span><span class="sxs-lookup"><span data-stu-id="e134c-132">An internal DNS record to support mobile users who're connecting from within your organization's network.</span></span>
    
- <span data-ttu-id="e134c-133">Внешняя (или общедоступный) запись DNS для поддержки мобильных пользователей, подключающихся из-за пределов сети организации.</span><span class="sxs-lookup"><span data-stu-id="e134c-133">An external (or public) DNS record to support mobile users who're connecting from outside your organization's network.</span></span>
    
<span data-ttu-id="e134c-134">Эти записи могут быть именами A (host) или CNAME (не нужно делать и то, и другое, мы просто включаем все здесь).</span><span class="sxs-lookup"><span data-stu-id="e134c-134">These records can be either A (host) names or CNAME records (you don't have to make both, we're just including the steps for everything here).</span></span>
  
### <a name="create-an-internal-dns-cname-record"></a><span data-ttu-id="e134c-135">Создание внутренней записи CNAME DNS</span><span class="sxs-lookup"><span data-stu-id="e134c-135">Create an internal DNS CNAME record</span></span>

1. <span data-ttu-id="e134c-136">Войдите на DNS-сервер в своей сети,  который входит в группу администраторов домена или **группу DnsAdmins.**</span><span class="sxs-lookup"><span data-stu-id="e134c-136">Log into a DNS server in your network that's either a member of the **Domain Admins** group or the **DnsAdmins** group.</span></span>
    
2. <span data-ttu-id="e134c-137">Нажмите **кнопку "Пуск"** и  выберите "Администрирование" **(может** потребоваться найти его, если это не выход из меню "Пуск"), а затем щелкните **DNS,** чтобы открыть оснастку администратора DNS.</span><span class="sxs-lookup"><span data-stu-id="e134c-137">Click **Start**, Choose **Administrative Tools** (you may need to **Search** for it if it's not an option off the Start menu), and then click **DNS** to open the DNS administrative snap-in.</span></span>
    
3. <span data-ttu-id="e134c-138">In the left-hand pane of the console window, you'll need to go to the domain that's home to your Skype for Business Server's Front End Servers, and expand the **Forward Lookup Zones** there.</span><span class="sxs-lookup"><span data-stu-id="e134c-138">In the left-hand pane of the console window, you'll need to go to the domain that's home to your Skype for Business Server's Front End Servers, and expand the **Forward Lookup Zones** there.</span></span>
    
4. <span data-ttu-id="e134c-139">У вас есть время, чтобы узнать, что из следующего у вас есть:</span><span class="sxs-lookup"><span data-stu-id="e134c-139">Take a moment to see which of the following you have:</span></span>
    
   - <span data-ttu-id="e134c-140">Любые записи A или AAAA для сервера переднего сервера (стандартного или корпоративного) или пула переднего сервера.</span><span class="sxs-lookup"><span data-stu-id="e134c-140">Any host A or AAAA records for your Front End Server (Standard or Enterprise) or Front End pool(s).</span></span>
    
   - <span data-ttu-id="e134c-141">Все записи A или AAAA для директора или пула директоров (дополнительная конфигурация, которая может быть в развертывании).</span><span class="sxs-lookup"><span data-stu-id="e134c-141">Any host A or AAAA records for a Director or Director pool (an optional configuration you may have in your deployment).</span></span>
    
5. <span data-ttu-id="e134c-142">После этого щелкните правой кнопкой мыши имя домена SIP и выберите в меню новый псевдоним **(CNAME).**</span><span class="sxs-lookup"><span data-stu-id="e134c-142">Once you've noted this, right-click your SIP domain name, and then choose **New Alias (CNAME)** from the menu.</span></span>
    
6. <span data-ttu-id="e134c-143">В **текстовом ящике имени** псевдонима введите lyncdiscoverinternal для имени хоста для внутреннего URL-адреса службы автообнаружия.</span><span class="sxs-lookup"><span data-stu-id="e134c-143">In the **Alias name** textbox, type lyncdiscoverinternal for your host name, for the internal Autodiscover service URL.</span></span>
    
7. <span data-ttu-id="e134c-144">В полное доменное имя **(FQDN** для целевого хоста) необходимо ввести полное доменное имя внутренних веб-служб для пула переднего сервера (или отдельного сервера переднего сервера, пула директоров или директора), которое было определено на шаге 4 выше.</span><span class="sxs-lookup"><span data-stu-id="e134c-144">In the **Fully qualified domain name (FQDN for target host**, you'll need to type or browse to the internal Web Services FQDN for your Front End pool (or single Front End Server, or Director pool or Director), identified in step 4 above.</span></span> <span data-ttu-id="e134c-145">Нажмите кнопку "ОК" при его вжатии.</span><span class="sxs-lookup"><span data-stu-id="e134c-145">Click OK when this is entered.</span></span>
    
8. <span data-ttu-id="e134c-146">Вам потребуется создать новую запись CNAME автооружия в зоне forward lookup для каждого домена SIP, поддерживаемого в среде Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="e134c-146">You'll need to create a new Autodiscover CNAME record in the forward lookup zone for each SIP domain supported in your Skype for Business Server environment.</span></span>
    
### <a name="create-an-external-dns-cname-record"></a><span data-ttu-id="e134c-147">Создание внешней записи CNAME DNS</span><span class="sxs-lookup"><span data-stu-id="e134c-147">Create an external DNS CNAME record</span></span>

1. <span data-ttu-id="e134c-148">Эти действия являются общими, так как мы не можем сообщить, какой общедоступный поставщик DNS вы можете использовать, но мы по-прежнему хотим помочь вам. Войдите в общедоступный поставщик DNS с помощью учетной записи, которая сможет там делать новые записи DNS.</span><span class="sxs-lookup"><span data-stu-id="e134c-148">These steps are generic, because we can't tell what public DNS provider you might be using, but we still want to help you out. Please log into your public DNS provider with an account that will be able to make new DNS records there.</span></span>
    
2. <span data-ttu-id="e134c-149">На этом этапе уже должен существовать домен SIP для Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="e134c-149">At this point in time, a SIP domain should already exist there for Skype for Business Server.</span></span> <span data-ttu-id="e134c-150">**Разкрой зону "Вперед" для** этого домена SIP или откройте ее другим способом.</span><span class="sxs-lookup"><span data-stu-id="e134c-150">Expand the **Forward Lookup Zone** for this SIP domain, or otherwise open it up.</span></span>
    
3. <span data-ttu-id="e134c-151">У вас есть время, чтобы узнать, что из следующего у вас есть:</span><span class="sxs-lookup"><span data-stu-id="e134c-151">Take a moment to see which of the following you have:</span></span>
    
   - <span data-ttu-id="e134c-152">Любые записи A или AAAA для сервера переднего сервера (стандартного или корпоративного) или пула переднего сервера.</span><span class="sxs-lookup"><span data-stu-id="e134c-152">Any host A or AAAA records for your Front End Server (Standard or Enterprise) or Front End pool(s).</span></span>
    
   - <span data-ttu-id="e134c-153">Все записи A или AAAA для директора или пула директоров (дополнительная конфигурация, которая может быть в развертывании).</span><span class="sxs-lookup"><span data-stu-id="e134c-153">Any host A or AAAA records for a Director or Director pool (an optional configuration you may have in your deployment).</span></span>
    
4. <span data-ttu-id="e134c-154">После получения этой информации вы сможете выбрать параметр для создания нового псевдонима **(CNAME).**</span><span class="sxs-lookup"><span data-stu-id="e134c-154">Once you have that information, you should be able to select an option for creating a **New Alias (CNAME)**.</span></span>
    
5. <span data-ttu-id="e134c-155">Теперь у вас должна быть возможность ввести имя псевдонима, необходимо ввести здесь lyncdiscover для внешнего URL-адреса службы автоотнаружия.</span><span class="sxs-lookup"><span data-stu-id="e134c-155">Now you should be able to enter an **Alias Name**, you need to enter lyncdiscover here for the external Autodiscover service URL.</span></span>
    
6. <span data-ttu-id="e134c-156">Далее должна быть область, которая должна вводиться в качестве **FQDN** для целевого хоста. Это должно быть FQDN для пула переднего сервера (или одного сервера переднего сервера, пула директоров или директора), заданной на шаге 3 выше.</span><span class="sxs-lookup"><span data-stu-id="e134c-156">Next there should be an area to enter in a **FQDN for target host**, this will need to be the FQDN for your Front End pool (or single Front End Server, or Director pool or Director), identified in step 3 above.</span></span>
    
7. <span data-ttu-id="e134c-157">Вам может потребоваться сохранить здесь или если вам нужно создать дополнительные записи CNAME в зоне forward lookup каждого домена SIP в среде Skype для бизнеса Server, это необходимо сделать, но когда все будет готово, сохраните свою работу.</span><span class="sxs-lookup"><span data-stu-id="e134c-157">You may need to save here, or if you need to create additional CNAME records in the forward lookup zone of each SIP domain in your Skype for Business Server environment, you should do that, but once you're ready, save your work.</span></span>
    
### <a name="create-an-internal-dns-a-record"></a><span data-ttu-id="e134c-158">Создание внутренней записи A DNS</span><span class="sxs-lookup"><span data-stu-id="e134c-158">Create an internal DNS A record</span></span>

1. <span data-ttu-id="e134c-159">Войдите на DNS-сервер в своей сети,  который входит в группу администраторов домена или **группу DnsAdmins.**</span><span class="sxs-lookup"><span data-stu-id="e134c-159">Log into a DNS server in your network that's either a member of the **Domain Admins** group or the **DnsAdmins** group.</span></span>
    
2. <span data-ttu-id="e134c-160">Нажмите **кнопку "Пуск"** и  выберите "Администрирование" **(может** потребоваться найти его, если это не выход из меню "Пуск"), а затем щелкните **DNS,** чтобы открыть оснастку администратора DNS.</span><span class="sxs-lookup"><span data-stu-id="e134c-160">Click **Start**, Choose **Administrative Tools** (you may need to **Search** for it if it's not an option off the Start menu), and then click **DNS** to open the DNS administrative snap-in.</span></span>
    
3. <span data-ttu-id="e134c-161">In the left-hand pane of the console window, you'll need to go to the domain that's home to your Skype for Business Server's Front End Servers, and expand the **Forward Lookup Zones** there.</span><span class="sxs-lookup"><span data-stu-id="e134c-161">In the left-hand pane of the console window, you'll need to go to the domain that's home to your Skype for Business Server's Front End Servers, and expand the **Forward Lookup Zones** there.</span></span>
    
4. <span data-ttu-id="e134c-162">У вас есть время, чтобы узнать, что из следующего у вас есть:</span><span class="sxs-lookup"><span data-stu-id="e134c-162">Take a moment to see which of the following you have:</span></span>
    
   - <span data-ttu-id="e134c-163">Любые записи A или AAAA для сервера переднего сервера (стандартного или корпоративного) или пула переднего сервера.</span><span class="sxs-lookup"><span data-stu-id="e134c-163">Any host A or AAAA records for your Front End Server (Standard or Enterprise) or Front End pool(s).</span></span>
    
   - <span data-ttu-id="e134c-164">Все записи A или AAAA для директора или пула директоров (дополнительная конфигурация, которая может быть в развертывании).</span><span class="sxs-lookup"><span data-stu-id="e134c-164">Any host A or AAAA records for a Director or Director pool (an optional configuration you may have in your deployment).</span></span>
    
5. <span data-ttu-id="e134c-165">После этого щелкните правой кнопкой мыши имя домена SIP и выберите в меню новый хост (A или **AAAA).**</span><span class="sxs-lookup"><span data-stu-id="e134c-165">Once you've noted this, right-click your SIP domain name, and then choose **New Host (A or AAAA)** from the menu.</span></span>
    
6. <span data-ttu-id="e134c-166">В **текстовом** ящике "Имя" введите lyncdiscoverinternal для имени хоста для внутреннего URL-адреса службы автообнаружия.</span><span class="sxs-lookup"><span data-stu-id="e134c-166">In the **Name** textbox, type lyncdiscoverinternal for your host name, for the internal Autodiscover service URL.</span></span>
    
7. <span data-ttu-id="e134c-167">В **текстовом** ящике IP-адреса введите IP-адрес внутренних веб-служб для пула переднего сервера (или одного сервера переднего сервера, пула директоров или директора), который был определен на шаге 4 выше.</span><span class="sxs-lookup"><span data-stu-id="e134c-167">In the **IP Address** textbox, type the internal Web Services IP address for your Front End pool (or single Front End Server, or Director pool or Director), identified in step 4 above.</span></span>
    
8. <span data-ttu-id="e134c-168">После этого нажмите кнопку **"Добавить хост"** и нажмите кнопку **"ОК".**</span><span class="sxs-lookup"><span data-stu-id="e134c-168">When this is done, click **Add Host**, and then click **OK**.</span></span>
    
9. <span data-ttu-id="e134c-169">Вам потребуется создать новые записи автооружия A или AAAA в зоне forward lookup для каждого домена SIP, поддерживаемого в среде Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="e134c-169">You'll need to create a new Autodiscover A or AAAA records in the forward lookup zone for each SIP domain supported in your Skype for Business Server environment.</span></span> <span data-ttu-id="e134c-170">Для этого повторите шаги с 6 по 8 столько раз, сколько необходимо.</span><span class="sxs-lookup"><span data-stu-id="e134c-170">To do this, repeat steps 6-8 as many times as needed.</span></span>
    
10. <span data-ttu-id="e134c-171">После этого нажмите кнопку **"Готово".**</span><span class="sxs-lookup"><span data-stu-id="e134c-171">When you're done, click **Done**.</span></span>
    
### <a name="create-an-external-dns-a-record"></a><span data-ttu-id="e134c-172">Создание внешней DNS-записи A</span><span class="sxs-lookup"><span data-stu-id="e134c-172">Create an external DNS A record</span></span>

1. <span data-ttu-id="e134c-173">Эти действия являются общими, так как мы не можем сообщить, какой общедоступный поставщик DNS вы можете использовать, но мы по-прежнему хотим помочь вам. Войдите в общедоступный поставщик DNS с помощью учетной записи, которая сможет там делать новые записи DNS.</span><span class="sxs-lookup"><span data-stu-id="e134c-173">These steps are generic, because we can't tell what public DNS provider you might be using, but we still want to help you out. Please log into your public DNS provider with an account that will be able to make new DNS records there.</span></span>
    
2. <span data-ttu-id="e134c-174">На этом этапе уже должен существовать домен SIP для Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="e134c-174">At this point in time, a SIP domain should already exist there for Skype for Business Server.</span></span> <span data-ttu-id="e134c-175">**Разкрой зону "Вперед" для** этого домена SIP или откройте ее другим способом.</span><span class="sxs-lookup"><span data-stu-id="e134c-175">Expand the **Forward Lookup Zone** for this SIP domain, or otherwise open it up.</span></span>
    
3. <span data-ttu-id="e134c-176">У вас есть время, чтобы узнать, что из следующего у вас есть:</span><span class="sxs-lookup"><span data-stu-id="e134c-176">Take a moment to see which of the following you have:</span></span>
    
   - <span data-ttu-id="e134c-177">Любые записи A или AAAA для сервера переднего сервера (стандартного или корпоративного) или пула переднего сервера.</span><span class="sxs-lookup"><span data-stu-id="e134c-177">Any host A or AAAA records for your Front End Server (Standard or Enterprise) or Front End pool(s).</span></span>
    
   - <span data-ttu-id="e134c-178">Все записи A или AAAA для директора или пула директоров (дополнительная конфигурация, которая может быть в развертывании).</span><span class="sxs-lookup"><span data-stu-id="e134c-178">Any host A or AAAA records for a Director or Director pool (an optional configuration you may have in your deployment).</span></span>
    
4. <span data-ttu-id="e134c-179">После получения этой информации вы сможете выбрать вариант создания нового хоста **A или AAAA.**</span><span class="sxs-lookup"><span data-stu-id="e134c-179">Once you have that information, you should be able to select an option for creating a **New Host A or AAAA**.</span></span>
    
5. <span data-ttu-id="e134c-180">Теперь у вас должна быть возможность ввести **имя,** необходимо ввести здесь lyncdiscover для внешнего URL-адреса службы автонаружия.</span><span class="sxs-lookup"><span data-stu-id="e134c-180">Now you should be able to enter a **Name**, you need to enter lyncdiscover here for the external Autodiscover service URL.</span></span>
    
6. <span data-ttu-id="e134c-181">Далее должна быть область для ввода IP-адресов. Это должен быть **IP-адрес** для пула переднего сервера (или одного сервера переднего сервера, пула директоров или директора), который был определен на шаге 3 выше.</span><span class="sxs-lookup"><span data-stu-id="e134c-181">Next there should be an area to enter in a **IP Addresss**, this will need to be the IP for your Front End pool (or single Front End Server, or Director pool or Director), identified in step 3 above.</span></span>
    
7. <span data-ttu-id="e134c-182">Вам может потребоваться сохранить здесь или если вам нужно создать дополнительные записи A или AAAA в зоне forward lookup каждого домена SIP для вашей среды Skype для бизнеса Server, вы должны сделать это, но когда все будет готово, сохраните свою работу.</span><span class="sxs-lookup"><span data-stu-id="e134c-182">You may need to save here, or if you need to create additional A or AAAA records in the forward lookup zone of each SIP domain for your Skype for Business Server environment, you should do that, but once you're ready, save your work.</span></span>
    
## <a name="modify-certificates"></a><span data-ttu-id="e134c-183">Изменение сертификатов</span><span class="sxs-lookup"><span data-stu-id="e134c-183">Modify certificates</span></span>
<span data-ttu-id="e134c-184"><a name="ModCerts"> </a></span><span class="sxs-lookup"><span data-stu-id="e134c-184"><a name="ModCerts"> </a></span></span>

<span data-ttu-id="e134c-185">Если у вас возникли вопросы о планировании сертификатов, мы задокументировали это в статье "Планирование мобильности [для Skype для бизнеса Server".](../plan-your-deployment/mobility.md)</span><span class="sxs-lookup"><span data-stu-id="e134c-185">If you have questions about Planning around certificates, we've documented that in our [Plan for Mobility for Skype for Business Server](../plan-your-deployment/mobility.md) article.</span></span> <span data-ttu-id="e134c-186">После проверки мы проймем следующие вопросы:</span><span class="sxs-lookup"><span data-stu-id="e134c-186">Once you've reviewed that, we'll walk you through the following:</span></span>
  
- <span data-ttu-id="e134c-187">Нужны ли мне новые сертификаты?</span><span class="sxs-lookup"><span data-stu-id="e134c-187">Do I need new certificates?</span></span>
    
- <span data-ttu-id="e134c-188">Запрос новых сертификатов из вашего ЦС.</span><span class="sxs-lookup"><span data-stu-id="e134c-188">Requesting new certificates from your Certificate Authority (CA).</span></span>
    
- <span data-ttu-id="e134c-189">Обновление сертификатов на месте с помощью замены с помощью PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e134c-189">Updating your in-place certificates with the replacements using PowerShell.</span></span>
    
- <span data-ttu-id="e134c-190">Проверка сертификатов с помощью оснастки "Сертификаты" в консоли управления (MMC).</span><span class="sxs-lookup"><span data-stu-id="e134c-190">Checking the certificates using the Certificates snapin in the Microsoft Management Console (MMC).</span></span>
    
### <a name="do-i-need-new-certificates"></a><span data-ttu-id="e134c-191">Нужны ли мне новые сертификаты?</span><span class="sxs-lookup"><span data-stu-id="e134c-191">Do I need new certificates?</span></span>

1. <span data-ttu-id="e134c-192">Во-первых, вам может потребоваться проверить, какие сертификаты находятся на месте и есть ли у них необходимые записи.</span><span class="sxs-lookup"><span data-stu-id="e134c-192">First, you may need to check and see what certificates are in-place, and whether or not they have the entries you need.</span></span> <span data-ttu-id="e134c-193">Для этого необходимо войти в Skype для бизнеса Server с помощью учетной записи локального администратора.</span><span class="sxs-lookup"><span data-stu-id="e134c-193">To do that, you'll need to log into your Skype for Business Server with an account that's a local Administrator.</span></span> <span data-ttu-id="e134c-194">Для некоторых из этих действий этой учетной записи также могут потребоваться права на выдачу ЦС.</span><span class="sxs-lookup"><span data-stu-id="e134c-194">This account may also need to have rights to the issuing Certificate Authority (CA), for some of these steps.</span></span>
    
2. <span data-ttu-id="e134c-195">Откройте оболочку управления Skype для бизнеса Server (ее можно найти с помощью поиска, если она не закреплена в меню "Пуск" или панели задач).</span><span class="sxs-lookup"><span data-stu-id="e134c-195">Open the Skype for Business Server Management Shell (you can use Search to find it if you don't have it pinned to your Start menu or task bar).</span></span>
    
3. <span data-ttu-id="e134c-196">Перед добавлением обновленного сертификата необходимо знать, какие сертификаты были назначены.</span><span class="sxs-lookup"><span data-stu-id="e134c-196">It's going to be essential for you to know what certificates have been assigned before you try adding an updated certificate.</span></span> <span data-ttu-id="e134c-197">Поэтому введите в команду:</span><span class="sxs-lookup"><span data-stu-id="e134c-197">So at the command, type:</span></span>
    
   ```powershell
   Get-CsCertificate
   ```

4. <span data-ttu-id="e134c-198">Сведения из шага 3 будут уникальными для вас.</span><span class="sxs-lookup"><span data-stu-id="e134c-198">The information from Step 3 will be unique to you.</span></span> <span data-ttu-id="e134c-199">Чтобы определить, назначен ли вам один сертификат для нескольких вещей или для различных компонентов, которые в них нуждаются, необходимо найти другой сертификат.</span><span class="sxs-lookup"><span data-stu-id="e134c-199">You need to look it over to determine if you have a single certificate that's been assigned for multiple things, or whether you have a different certificate assigned for the different components that need them.</span></span> <span data-ttu-id="e134c-200">Параметр **Use** покажет, как используется сертификат, а параметр **Thumbprint** – один или несколько сертификатов.</span><span class="sxs-lookup"><span data-stu-id="e134c-200">The **Use** parameter will tell you how a certificate's being used, and the **Thumbprint** parameter will tell you if it's all the same certificate, or multiple certs.</span></span>
    
5. <span data-ttu-id="e134c-201">Если в разделе "Планирование" мы рекомендуем использовать записи SAN, все будет хорошо.</span><span class="sxs-lookup"><span data-stu-id="e134c-201">If you have the SAN entries recommended in our Planning section, you're good.</span></span> <span data-ttu-id="e134c-202">В этом случае вам потребуется запросить новый сертификат или несколько сертификатов (в зависимости от конфигурации) в вашем сертификате.</span><span class="sxs-lookup"><span data-stu-id="e134c-202">If not, you'll need to request a new certificate, or multiple certificates (depending on your configuration) from your Certificate Authority.</span></span>
    
### <a name="request-a-new-certificate-or-certificates-from-your-certificate-authority-ca"></a><span data-ttu-id="e134c-203">Запрос нового сертификата или сертификатов из вашего ЦС</span><span class="sxs-lookup"><span data-stu-id="e134c-203">Request a new certificate, or certificates, from your Certificate Authority (CA)</span></span>

1. <span data-ttu-id="e134c-204">Проверив, какие записи SAN у вас есть, вы знаете, что у вас есть один сертификат **(после** проверки с помощью вышеперечисленной проверки) и узнали, что у вас нет всех необходимых записей.</span><span class="sxs-lookup"><span data-stu-id="e134c-204">After you've checked to see what SAN entries you have, you know you have a **single certificate** (after checking via the steps above), and you learned you don't have all the entries you need.</span></span> <span data-ttu-id="e134c-205">В ваш ЦС должен быть сделан новый запрос на сертификат.</span><span class="sxs-lookup"><span data-stu-id="e134c-205">A new certificate request needs to be made to your CA.</span></span> <span data-ttu-id="e134c-206">Откройте Skype для бизнеса Server PowerShell:</span><span class="sxs-lookup"><span data-stu-id="e134c-206">Open your Skype for Business Server PowerShell:</span></span>
    
   - <span data-ttu-id="e134c-207">For a missing Autodiscover Service SAN (replacing the -Ca parameter with your own Certificate Authority path):</span><span class="sxs-lookup"><span data-stu-id="e134c-207">For a missing Autodiscover Service SAN (replacing the -Ca parameter with your own Certificate Authority path):</span></span>
    
   ```powershell
   Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -Ca dc\myca -AllSipDomain -verbose
   ```

   - <span data-ttu-id="e134c-208">Теперь при использовании нескольких доменов SIP нельзя использовать параметр AllSipDomain, как в примере выше.</span><span class="sxs-lookup"><span data-stu-id="e134c-208">Now, if you have multiple SIP domains, you can't use the AllSipDomain parameter as in the example above.</span></span> <span data-ttu-id="e134c-209">Вместо этого необходимо использовать параметр DomainName.</span><span class="sxs-lookup"><span data-stu-id="e134c-209">You'll need to use the DomainName parameter instead.</span></span> <span data-ttu-id="e134c-210">При использовании параметра DomainName необходимо определить FQDN для записей lyncdiscoverinternal и lyncdiscover.</span><span class="sxs-lookup"><span data-stu-id="e134c-210">And when you use the DomainName parameter, you've got to define the FQDN for the lyncdiscoverinternal and lyncdiscover records.</span></span> <span data-ttu-id="e134c-211">Примером может быть (замена параметра -Ca на собственный путь к ЦС):</span><span class="sxs-lookup"><span data-stu-id="e134c-211">An example would be (replacing the -Ca parameter with your own Certificate Authority path):</span></span>
    
   ```powershell
   Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -Ca dc\myca -DomainName "LyncdiscoverInternal.contoso.com, LyncdiscoverInternal.contoso.net" -verbose
   ```

2. <span data-ttu-id="e134c-212">Или, проверив, какие записи SAN у вас есть, вы обнаружили, что у вас есть несколько сертификатов, которые не имеют всех необходимых записей. </span><span class="sxs-lookup"><span data-stu-id="e134c-212">Or, after you've checked to see what SAN entries you have, you found you have **multiple certificates** that don't have all the entries you need.</span></span> <span data-ttu-id="e134c-213">В ваш ЦС должен быть сделан новый запрос на сертификат.</span><span class="sxs-lookup"><span data-stu-id="e134c-213">A new certificate request needs to be made to your CA.</span></span> <span data-ttu-id="e134c-214">Откройте Skype для бизнеса Server PowerShell:</span><span class="sxs-lookup"><span data-stu-id="e134c-214">Open your Skype for Business Server PowerShell:</span></span>
    
   - <span data-ttu-id="e134c-215">For a missing Autodiscover Service SAN (replacing the -Ca parameter with your own Certificate Authority path):</span><span class="sxs-lookup"><span data-stu-id="e134c-215">For a missing Autodiscover Service SAN (replacing the -Ca parameter with your own Certificate Authority path):</span></span>
    
   ```powershell
   Request-CsCertificate -New -Type WebServicesInternal -Ca dc\myca -AllSipDomain -verbose
   ```

   - <span data-ttu-id="e134c-216">Теперь при использовании нескольких доменов SIP нельзя использовать параметр AllSipDomain, как в примере выше.</span><span class="sxs-lookup"><span data-stu-id="e134c-216">Now, if you have multiple SIP domains, you can't use the AllSipDomain parameter as in the example above.</span></span> <span data-ttu-id="e134c-217">Вместо этого необходимо использовать параметр DomainName.</span><span class="sxs-lookup"><span data-stu-id="e134c-217">You'll need to use the DomainName parameter instead.</span></span> <span data-ttu-id="e134c-218">При использовании параметра DomainName необходимо определить FQDN для записей lyncdiscoverinternal и lyncdiscover.</span><span class="sxs-lookup"><span data-stu-id="e134c-218">And when you use the DomainName parameter, you've got to define the FQDN for the lyncdiscoverinternal and lyncdiscover records.</span></span> <span data-ttu-id="e134c-219">Примерами может быть (замена параметра -Ca на собственный путь к ЦС):</span><span class="sxs-lookup"><span data-stu-id="e134c-219">Examples would be (replacing the -Ca parameter with your own Certificate Authority path):</span></span>
    
   ```powershell
   Request-CsCertificate -New -Type WebServicesInternal -Ca dc\myca -DomainName "LyncdiscoverInternal.contoso.com, LyncdiscoverInternal.contoso.net" -verbose
   ```

   ```powershell
   Request-CsCertificate -New -Type WebServicesExternal -Ca dc\myca -DomainName "Lyncdiscover.contoso.com, Lyncdiscover.contoso.net" -verbose
   ```

   - <span data-ttu-id="e134c-220">После того как ЦС создает новые сертификаты, их необходимо назначить.</span><span class="sxs-lookup"><span data-stu-id="e134c-220">Once the new certificates have been generated by the CA, you're going to need to assign them.</span></span>
    
### <a name="assign-certificates-using-skype-for-business-server-management-shell"></a><span data-ttu-id="e134c-221">Назначение сертификатов с помощью оболочки управления Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="e134c-221">Assign certificates using Skype for Business Server Management Shell</span></span>

- <span data-ttu-id="e134c-222">В зависимости от того, что вы нашли в разделе "Требуются ли новые сертификаты" выше, необходимо выполнить **одно** из следующих запусков.</span><span class="sxs-lookup"><span data-stu-id="e134c-222">Depending on what you found in the Do I need new certifications section above, you need to run **one** of the following.</span></span>
    
  - <span data-ttu-id="e134c-223">Если у вас есть один сертификат для всех (отпечатки идентичны), необходимо выполнить данной действия:</span><span class="sxs-lookup"><span data-stu-id="e134c-223">If you have a single certificate for everything (the thumbprints are identical) then you need to run this:</span></span>
    
  ```powershell
  Set-CsCertificate -Type <certificate(s) from the Use parameter> -Thumbprint <unique identifier>
  ```

  - <span data-ttu-id="e134c-224">Если у вас есть разные сертификаты для вещей (отпечатки отличаются), запустите эту экономию:</span><span class="sxs-lookup"><span data-stu-id="e134c-224">If you've got different certificates for things (the thumbprints are all different), run this instead:</span></span>
    
  ```powershell
  Set-CsCertificate -Type Default -Thumbprint <certificate thumbprint>
  Set-CsCertificate -Type WebServicesInternal -Thumbprint <certificate thumbprint>
  Set-CsCertificate -Type WebServicesExternal -Thumbprint <certificate thumbprint>
  ```

### <a name="viewing-certificates-in-the-microsoft-management-console-mmc"></a><span data-ttu-id="e134c-225">Просмотр сертификатов в консоли управления (MMC)</span><span class="sxs-lookup"><span data-stu-id="e134c-225">Viewing certificates in the Microsoft Management Console (MMC)</span></span>

1. <span data-ttu-id="e134c-226">Вы можете посмотреть на сертификаты с помощью оснастки "Сертификаты" для MMC.</span><span class="sxs-lookup"><span data-stu-id="e134c-226">You have an option to look at your certificates using the Certificates snap-in for the MMC.</span></span> <span data-ttu-id="e134c-227">Просто введите MMC в поиск, и она должна всплывать в виде параметра приложения.</span><span class="sxs-lookup"><span data-stu-id="e134c-227">Simply type MMC into search and it should pop up as an application option,.</span></span>
    
2. <span data-ttu-id="e134c-228">Чтобы добавить оснастку "Сертификаты", необходимо щелкнуть "Файл", а затем добавить или удалить оснастку... (или сочетания клавиш **CTRL+M** также будут работать). </span><span class="sxs-lookup"><span data-stu-id="e134c-228">To add the Certificates snap-in, you'll need to click **File**, and then **Add/Remove Snap-In...** (or keyboard shortcut **Ctrl+M** would also work).</span></span> <span data-ttu-id="e134c-229">**Сертификаты** можно выбрать в области слева, выбрать его, а затем — учетную запись компьютера во всплывающее окно, а затем **— "Далее".** </span><span class="sxs-lookup"><span data-stu-id="e134c-229">**Certificates** will be an option in the left-hand pane, select it and then **Computer Account** in the pop-up window, then **Next**.</span></span>
    
3. <span data-ttu-id="e134c-230">По-прежнему во всплывающее окно, по всей вероятности, вы делаете это на компьютере, на который находятся сертификаты, которые необходимо посмотреть, поэтому оставьте выбор на локальном компьютере, если это так. </span><span class="sxs-lookup"><span data-stu-id="e134c-230">Still in the pop-up window, in all likelihood you're doing this on the computer that's home to the certificates you need to look at, so leave the selection on **Local Computer** if that's so.</span></span> <span data-ttu-id="e134c-231">Если вы работаете на удаленном компьютере,  измените кнопку на другой компьютер, а затем  введите его FQDN или используйте кнопку "Обзор" для поиска этого компьютера через AD.</span><span class="sxs-lookup"><span data-stu-id="e134c-231">If you're working on a remote machine, change the radio button to **Another Computer** and then either enter that computer's FQDN or use the **Browse** button to search for that computer through AD.</span></span> <span data-ttu-id="e134c-232">После выбора компьютера необходимо нажать кнопку **"Готово",** а затем ОК, чтобы добавить оснастку в MMC. </span><span class="sxs-lookup"><span data-stu-id="e134c-232">After selecting the computer, you'll need to click **Finish** when ready, and then **OK** to add the snap-in to the MMC.</span></span>
    
4. <span data-ttu-id="e134c-233">**Разорите раздел** "Сертификаты" на левой области MMC.</span><span class="sxs-lookup"><span data-stu-id="e134c-233">Expand the **Certificates** section in the MMC's left-hand pane.</span></span> <span data-ttu-id="e134c-234">**Разоберем** также личную папку, а затем выберите **"Сертификаты".**</span><span class="sxs-lookup"><span data-stu-id="e134c-234">Expand the **Personal** folder as well, and then select **Certificates**.</span></span> <span data-ttu-id="e134c-235">Это позволяет увидеть сертификаты в этом хранилище.</span><span class="sxs-lookup"><span data-stu-id="e134c-235">This lets you see the certificates in this store.</span></span>
    
5. <span data-ttu-id="e134c-236">Необходимо найти сертификат, который требуется просмотреть, щелкните его правой кнопкой мыши и выберите **"Открыть".**</span><span class="sxs-lookup"><span data-stu-id="e134c-236">You need to locate the certificate you want to view, right-click on it, and choose **Open**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="e134c-237">Как узнать, что это за сертификат?</span><span class="sxs-lookup"><span data-stu-id="e134c-237">How do you know what certificate this is?</span></span> <span data-ttu-id="e134c-238">Это должен быть либо один сертификат, присвоенный для фермы, либо у вас может быть несколько сертификатов для различных функций, таких как default, internal Web Services и т. д. В этом случае может потребоваться просмотр нескольких сертификатов.</span><span class="sxs-lookup"><span data-stu-id="e134c-238">It should be either the single certificate assigned to everything for your farm, or you may have multiple certificates for different things, like Default, Internal Web Services, etc., in which case you may need to look at multiple certificates.</span></span> <span data-ttu-id="e134c-239">Несколько сертификатов будут иметь один и тот же отпечаток.</span><span class="sxs-lookup"><span data-stu-id="e134c-239">Multiple certificates will have the same thumbprint.</span></span> 
  
6. <span data-ttu-id="e134c-240">После просмотра представления **"Сертификат"** выберите **"Сведения".**</span><span class="sxs-lookup"><span data-stu-id="e134c-240">Once you've gotten to the **Certificate** view, choose **Details**.</span></span> <span data-ttu-id="e134c-241">Это позволит увидеть имя субъекта сертификата при выборе **субъекта,** а также будут показаны назначенное имя субъекта и связанные свойства.</span><span class="sxs-lookup"><span data-stu-id="e134c-241">This will let you see the certificate subject name when you select **Subject**, and the assigned subject name and associated properties are shown.</span></span>
    
7. <span data-ttu-id="e134c-242">Вам также потребуется проверить записи **альтернативного имени** субъекта.</span><span class="sxs-lookup"><span data-stu-id="e134c-242">You'll also need to check the **Subject Alternate Name** entries.</span></span> <span data-ttu-id="e134c-243">Вы найдете один или несколько из следующих ок.</span><span class="sxs-lookup"><span data-stu-id="e134c-243">You'll find one or more of the following:</span></span>
    
   - <span data-ttu-id="e134c-244">Имя пула для этого пула или имя одного сервера, если это не пул.</span><span class="sxs-lookup"><span data-stu-id="e134c-244">The pool name for this pool, or the single server name if this isn't a pool.</span></span>
    
   - <span data-ttu-id="e134c-245">Имя сервера, для которого назначен сертификат.</span><span class="sxs-lookup"><span data-stu-id="e134c-245">The server name that the certificate is assigned to.</span></span>
    
   - <span data-ttu-id="e134c-246">Записи простых URL-адресов, как правило, meet и dialin.</span><span class="sxs-lookup"><span data-stu-id="e134c-246">Simple URL records, typically meet and dialin.</span></span>
    
   - <span data-ttu-id="e134c-247">Внутренние и внешние имена веб-служб (например, webpool01.contoso.net, webpool01.contoso.com), основанные на вариантах, сделанных в построителье топологий и выборе перенастроек веб-служб.</span><span class="sxs-lookup"><span data-stu-id="e134c-247">Web Services internal and Web Services external names (for example, webpool01.contoso.net, webpool01.contoso.com), based on choices made in Topology Builder and over-ridden Web Services selections.</span></span>
    
   - <span data-ttu-id="e134c-248">Если уже назначено, lyncdiscover.\<sipdomain\></span><span class="sxs-lookup"><span data-stu-id="e134c-248">If already assigned, the lyncdiscover.\<sipdomain\></span></span> <span data-ttu-id="e134c-249">и lyncdiscoverinternal.\<sipdomain\></span><span class="sxs-lookup"><span data-stu-id="e134c-249">and lyncdiscoverinternal.\<sipdomain\></span></span> <span data-ttu-id="e134c-250">записи.</span><span class="sxs-lookup"><span data-stu-id="e134c-250">records.</span></span>
    
     <span data-ttu-id="e134c-251">Вам потребуется проверить несколько сертификатов, если вам назначено несколько сертификатов (см. примечание выше).</span><span class="sxs-lookup"><span data-stu-id="e134c-251">You'll need to check multiple certificates if you have more than one assigned (check the Note above).</span></span>
    
8. <span data-ttu-id="e134c-252">Поэтому, если вы нашли lyncdiscover.\<sipdomain\></span><span class="sxs-lookup"><span data-stu-id="e134c-252">So, if you find lyncdiscover.\<sipdomain\></span></span> <span data-ttu-id="e134c-253">и lyncdiscoverinternal.\<sipdomain\></span><span class="sxs-lookup"><span data-stu-id="e134c-253">and lyncdiscoverinternal.\<sipdomain\></span></span> <span data-ttu-id="e134c-254">записи, вы уже настроили эту настройку.</span><span class="sxs-lookup"><span data-stu-id="e134c-254">records, you've got this configured already.</span></span> <span data-ttu-id="e134c-255">Можно закрыть MMC.</span><span class="sxs-lookup"><span data-stu-id="e134c-255">You can close the MMC.</span></span>
    
9. <span data-ttu-id="e134c-256">Если они не назначены, вам потребуется либо сделать новый запрос сертификата (описанный выше), либо установить их после запроса (для этого рекомендуется использовать powerShell, описанные выше).</span><span class="sxs-lookup"><span data-stu-id="e134c-256">If they aren't assigned, you'll either need to make a new certificate request (outlined above) or you need to install them post-request (we recommend the following the PowerShell above for that).</span></span>
    
## <a name="configure-the-reverse-proxy"></a><span data-ttu-id="e134c-257">Настройка обратного прокси-сервера</span><span class="sxs-lookup"><span data-stu-id="e134c-257">Configure the reverse proxy</span></span>
<span data-ttu-id="e134c-258"><a name="ConfigRP"> </a></span><span class="sxs-lookup"><span data-stu-id="e134c-258"><a name="ConfigRP"> </a></span></span>

<span data-ttu-id="e134c-259">Шаги ниже не предназначены для точного следованию.</span><span class="sxs-lookup"><span data-stu-id="e134c-259">The steps below are not meant to be followed exactly.</span></span> <span data-ttu-id="e134c-260">Это потому, что в предыдущих версиях продукта мы походили бы на вас, например, на настройку шлюза управления угрозами (TMG), и если вы не использовали его, вам потребуется разработать собственную версию оттуда.</span><span class="sxs-lookup"><span data-stu-id="e134c-260">That's because in previous versions of the product, we'd have walked you through, for example, configuring Threat Management Gateway (TMG) and if you weren't using that, you'd need to work out your own version from there.</span></span>
  
<span data-ttu-id="e134c-261">TMG больше не предлагается корпорацией Майкрософт в качестве продукта, и если вам все еще нужно настроить его, вы можете посмотреть на шаги [Lync Server 2013.](https://technet.microsoft.com/library/hh690011%28v=ocs.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="e134c-261">TMG is no longer being offered by Microsoft as a product, and if you still need to configure it, you can look at the [Lync Server 2013 steps](https://technet.microsoft.com/library/hh690011%28v=ocs.15%29.aspx).</span></span> <span data-ttu-id="e134c-262">Однако следующая информация должна быть более полезной, даже если мы не можем предоставить конкретные по шагам для каждого обратного прокси-сервера.</span><span class="sxs-lookup"><span data-stu-id="e134c-262">But the following information's intended to be more generally helpful, even if there's no way we can provide specific walkthrough steps for every Reverse proxy out there.</span></span>
  
<span data-ttu-id="e134c-263">У нас есть два основных вещи, которые необходимо учитывать:</span><span class="sxs-lookup"><span data-stu-id="e134c-263">We have two main things to consider:</span></span>
  
- <span data-ttu-id="e134c-264">Будете ли вы делать первоначальный запрос автооружия по протоколу HTTPS (что мы рекомендуем)?</span><span class="sxs-lookup"><span data-stu-id="e134c-264">Are you going to be doing your initial Autodiscover request over HTTPS (which we recommend)?</span></span>
    
  - <span data-ttu-id="e134c-265">Если у вас есть правило веб-публикации, его необходимо изменить.</span><span class="sxs-lookup"><span data-stu-id="e134c-265">If you have a web publishing rule, you need to modify it.</span></span>
    
  - <span data-ttu-id="e134c-266">Если у вас еще нет правила веб-публикации, его необходимо создать.</span><span class="sxs-lookup"><span data-stu-id="e134c-266">If you don't have a web publishing rule yet, you need to create it.</span></span>
    
- <span data-ttu-id="e134c-267">Если вы делаете исходный запрос автооружия по протоколу HTTP, вам также потребуется создать или изменить это правило.</span><span class="sxs-lookup"><span data-stu-id="e134c-267">If you're doing your initial Autodiscover request over HTTP, then you'll need to create or modify that rule as well.</span></span>
    
> [!NOTE]
> <span data-ttu-id="e134c-268">**Важно!** Значение времени простоя прокси-сервера — это число, которое зависит от развертывания и развертывания.</span><span class="sxs-lookup"><span data-stu-id="e134c-268">**Important** A Proxy time-out value is a number that will vary from deployment to deployment.</span></span> <span data-ttu-id="e134c-269">Следует отслеживать развертывание и изменять значение для наилучшего работы клиентов.</span><span class="sxs-lookup"><span data-stu-id="e134c-269">You should monitor your deployment and modify the value for the best experience for clients.</span></span> <span data-ttu-id="e134c-270">Вы можете установить значение как низкое, как 200.</span><span class="sxs-lookup"><span data-stu-id="e134c-270">You may be able to set the value as low as 200.</span></span> <span data-ttu-id="e134c-271">Если вы поддерживаете мобильные клиенты Lync в своей среде, следует установить значение 960, чтобы разрешить время простоя push-уведомлений из Office 365, время простоя которых составляет 900.</span><span class="sxs-lookup"><span data-stu-id="e134c-271">If you are supporting Lync mobile clients in your environment, you should set the value to 960 to allow for push notification time-outs from Office 365, which have a time-out value of 900.</span></span> <span data-ttu-id="e134c-272">Очень вероятно, что вам придется увеличить значение времени отключения, чтобы избежать отключения клиента при слишком низком значении, или уменьшить число, если подключения через прокси-сервер не отключались, но очищались долго после отключения клиента.</span><span class="sxs-lookup"><span data-stu-id="e134c-272">It is very likely that you will have to increase the time-out value to avoid client disconnects when the value is too low, or decrease the number if connections through the proxy do not disconnect but clear long after the client has disconnected.</span></span> <span data-ttu-id="e134c-273">Единственный точный способ определить соответствующий параметр для этого значения — мониторинг и создание базовых условий для вашей среды.</span><span class="sxs-lookup"><span data-stu-id="e134c-273">Monitoring and baselining what is usual for your environment is the only accurate way to determine the appropriate setting for this value.</span></span>
  
### <a name="modify-the-existing-web-publishing-rule-for-your-external-autodiscover-san-and-url"></a><span data-ttu-id="e134c-274">Изменение существующего правила веб-публикации для внешнего SAN и URL-адреса автооружия</span><span class="sxs-lookup"><span data-stu-id="e134c-274">Modify the existing web publishing rule for your external Autodiscover SAN and URL</span></span>

1. <span data-ttu-id="e134c-275">Откройте интерфейс обратного прокси-сервера.</span><span class="sxs-lookup"><span data-stu-id="e134c-275">Open your Reverse proxy interface.</span></span>
    
2. <span data-ttu-id="e134c-276">Вам потребуется найти правило веб-публикации и выбрать параметр "Изменить" (он может находиться в меню или вкладке в зависимости от конфигурации обратного прокси-сервера).</span><span class="sxs-lookup"><span data-stu-id="e134c-276">You'll need to locate your web publishing rule, and choose the Edit option (it may be on a menu or tab, depending on your Reverse proxy configuration).</span></span>
    
3. <span data-ttu-id="e134c-277">Должна быть область, в которую должно быть вложено правило веб-публикации.</span><span class="sxs-lookup"><span data-stu-id="e134c-277">There should be an area that states what this web publishing rule is applied to.</span></span> <span data-ttu-id="e134c-278">Это правило необходимо изменить для входящих сайтов или запросов к сайтам.</span><span class="sxs-lookup"><span data-stu-id="e134c-278">You need to modify this rule for incoming sites or requests for sites.</span></span> <span data-ttu-id="e134c-279">Вы добавим **новую** запись.</span><span class="sxs-lookup"><span data-stu-id="e134c-279">You're going to **add** a new entry.</span></span>
    
4. <span data-ttu-id="e134c-280">Введите имя сайта автообнаружния (в качестве примера мы будем  использовать lyncdiscover.contoso.com) и нажмите кнопку "ОК" или "Сохранить" **в** зависимости от формата обратного прокси-сервера.</span><span class="sxs-lookup"><span data-stu-id="e134c-280">Type the name of your Autodiscover site (the example we'll use is lyncdiscover.contoso.com), and click **OK** or **Save**, depending on your Reverse proxy's format.</span></span>
    
5. <span data-ttu-id="e134c-281">Возможно, у вас есть новый сертификат с записью SAN автооружия.</span><span class="sxs-lookup"><span data-stu-id="e134c-281">You may have a new certificate that has the Autodiscover SAN entry in it.</span></span> <span data-ttu-id="e134c-282">Его также необходимо установить и настроить для использования в соответствии с настройками обратного прокси-сервера.</span><span class="sxs-lookup"><span data-stu-id="e134c-282">That needs to be installed as well and configured for use according to your Reverse proxy's settings.</span></span> <span data-ttu-id="e134c-283">Обязательно сохраните все после завершения настройки.</span><span class="sxs-lookup"><span data-stu-id="e134c-283">Be sure to save everything when the configuration is completed.</span></span>
    
6. <span data-ttu-id="e134c-284">Если обратный прокси-сервер имеет функцию **Test,** используйте ее, чтобы убедиться, что все работает правильно.</span><span class="sxs-lookup"><span data-stu-id="e134c-284">If your Reverse proxy has a **Test** functionality, then please make use of it, to ensure everything's working properly.</span></span>
    
7. <span data-ttu-id="e134c-285">Теперь вам может потребоваться повторить эти действия, если в вашей среде есть директор или пул директоров (это означает, что у вас есть второе правило).</span><span class="sxs-lookup"><span data-stu-id="e134c-285">Now, you may need to repeat these steps if you have a Director or Director pool in your environment (this would mean you have a second rule).</span></span>
    
### <a name="create-a-web-publishing-rule-for-the-external-autodiscover-url"></a><span data-ttu-id="e134c-286">Создание правила веб-публикации для внешнего URL-адреса автооружия</span><span class="sxs-lookup"><span data-stu-id="e134c-286">Create a web publishing rule for the external Autodiscover URL</span></span>

1. <span data-ttu-id="e134c-287">Откройте интерфейс обратного прокси-сервера.</span><span class="sxs-lookup"><span data-stu-id="e134c-287">Open your Reverse proxy interface.</span></span>
    
2. <span data-ttu-id="e134c-288">Необходимо определить, где в интерфейсе создаются правила веб-публикации,  и выбрать параметр "Создать" или "Создать" (он может находиться в меню или вкладке в зависимости от конфигурации обратного прокси-сервера). </span><span class="sxs-lookup"><span data-stu-id="e134c-288">You'll need to locate where in the interface you create your web publishing rules, and choose the **New** or **Create** option (it may be on a menu or tab, depending on your Reverse proxy configuration).</span></span> <span data-ttu-id="e134c-289">Вы ищете вариант создания нового правила веб-публикации.</span><span class="sxs-lookup"><span data-stu-id="e134c-289">You are looking for the option to create a new web publishing rule.</span></span>
    
3. <span data-ttu-id="e134c-290">Как правило, необходимо ввести следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="e134c-290">Typically, you will need to enter the following information:</span></span>
    
   - <span data-ttu-id="e134c-291">**Name**: the name for your rule</span><span class="sxs-lookup"><span data-stu-id="e134c-291">**Name**: the name for your rule</span></span>
    
   - <span data-ttu-id="e134c-292">**Действие правила:** в этом случае  это правило "Разрешить", что-то передается через обратный прокси-сервер.</span><span class="sxs-lookup"><span data-stu-id="e134c-292">**Rule Action**: In this case it's an **Allow** rule, you're letting something pass through your Reverse proxy.</span></span>
    
   - <span data-ttu-id="e134c-293">Правило **публикации** или выбираемый вариант — один **веб-сайт или под балансировка нагрузки.**</span><span class="sxs-lookup"><span data-stu-id="e134c-293">The **Publishing** rule or option you're choosing would be **single web site or load balancer**.</span></span>
    
   - <span data-ttu-id="e134c-294">Это должен быть **SSL для** внешнего доступа, выберите этот параметр.</span><span class="sxs-lookup"><span data-stu-id="e134c-294">This needs to be **SSL** for external access, choose that option.</span></span>
    
   - <span data-ttu-id="e134c-295">Вам потребуется опубликовать путь для внутренней публикации и ввести FQDN для внешних веб-служб в под балансиру нагрузки пула переднего конца (или FQDN под баланситора нагрузки пула директоров, если таковой имеется), например sfb_pool01.contoso.local. </span><span class="sxs-lookup"><span data-stu-id="e134c-295">You're going to need to publish a path for **Internal Publishing**, and enter the FQDN for the external Web Services on your Front End pool's load balancer (or the FQDN of the Director pool's load balancer if you have one), an example would be sfb_pool01.contoso.local.</span></span>
    
   - <span data-ttu-id="e134c-296">В качестве пути для публикации необходимо ввести _, но также необходимо **/\\** переадлить исходный заглавный_заданный_заданный_заголок\*\*.</span><span class="sxs-lookup"><span data-stu-id="e134c-296">You should type **/\\** _ as the path to be published, but you also need to _\*forward the original host header\*\*.</span></span>
    
   - <span data-ttu-id="e134c-297">Существует возможность для сведений или сведений об общедоступных **или внешних** именах.</span><span class="sxs-lookup"><span data-stu-id="e134c-297">There will be an option for **public or external name** details or information.</span></span> <span data-ttu-id="e134c-298">В этом месте вы сможете ввести:</span><span class="sxs-lookup"><span data-stu-id="e134c-298">This is the place where you'll be able to enter:</span></span>
    
   - <span data-ttu-id="e134c-299">**Принимать запросы,** но это должно быть имя домена.</span><span class="sxs-lookup"><span data-stu-id="e134c-299">**Accept requests**, but it should be for the domain name.</span></span>
    
   - <span data-ttu-id="e134c-300">Введите **имя** **lyncdiscover.**</span><span class="sxs-lookup"><span data-stu-id="e134c-300">For the **Name**, you should enter **lyncdiscover.**</span></span> <span data-ttu-id="e134c-301"><sipdomain> (это внешний URL-адрес службы автонаружия).</span><span class="sxs-lookup"><span data-stu-id="e134c-301"><sipdomain> (this is the external Autodiscover Service URL).</span></span> <span data-ttu-id="e134c-302">Теперь, если вы создаете правило для URL-адреса внешних веб-служб во внешнем пуле, необходимо ввести FQDN для внешних веб-служб в пуле переднего lyncwebextpool01.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="e134c-302">Now, if you're creating a rule for the external Web Services URL on the Front End pool, you'll need to type the FQDN for the external Web Services on your Front End pool (for example, lyncwebextpool01.contoso.com).</span></span>
    
   - <span data-ttu-id="e134c-303">Будет параметр **Path,** и вам потребуется ввести **/\\** _здесь.</span><span class="sxs-lookup"><span data-stu-id="e134c-303">There will be a **Path** option, and you'll need to enter **/\\** _ here.</span></span>
    
   - <span data-ttu-id="e134c-304">You'll need to select a _ *SSL Listener*\* with your up-to-date public certificate.</span><span class="sxs-lookup"><span data-stu-id="e134c-304">You'll need to select a _ *SSL Listener*\* with your up-to-date public certificate.</span></span>
    
   - <span data-ttu-id="e134c-305">**Для делегирования** проверки подлинности должно быть установлено отсутствие делегирования, но должна быть разрешена прямая проверка **подлинности** клиента.</span><span class="sxs-lookup"><span data-stu-id="e134c-305">**Authentication Delegation** should be set to **No delegation**, but direct client authentication **should** be allowed.</span></span>
    
   - <span data-ttu-id="e134c-306">Правило должно быть установлено для **всех пользователей.**</span><span class="sxs-lookup"><span data-stu-id="e134c-306">The rule should be set to **All users**.</span></span>
    
   - <span data-ttu-id="e134c-307">Это должны быть все сведения, необходимые для создания этого правила и позволяющие продолжить.</span><span class="sxs-lookup"><span data-stu-id="e134c-307">This should be all the information you need to create this rule and allow you to proceed.</span></span>
    
4. <span data-ttu-id="e134c-308">Вам потребуется убедиться, что  исходный заголок хоста переназначен.</span><span class="sxs-lookup"><span data-stu-id="e134c-308">You're going to need to ensure that the **original host header** is forwarded.</span></span>
    
5. <span data-ttu-id="e134c-309">Необходимо **также настроить** порты веб-сервера, вы должны сделать следующее:</span><span class="sxs-lookup"><span data-stu-id="e134c-309">The **Web Server** ports will need to be set as well, you'll need to do the following:</span></span>
    
   - <span data-ttu-id="e134c-310">**Перенаправление запросов на ПОРТ HTTP** и номер порта должен быть **8080.**</span><span class="sxs-lookup"><span data-stu-id="e134c-310">**Redirect requests to HTTP port** and the port number should be **8080**.</span></span>
    
   - <span data-ttu-id="e134c-311">**Запросы на перенаправление на SSL-порт,** а номер порта должен быть **4443.**</span><span class="sxs-lookup"><span data-stu-id="e134c-311">**Redirect requests to SSL port** and the port number should be **4443**.</span></span>
    
6. <span data-ttu-id="e134c-312">Если все настроено, вам потребуется сохранить или применить их, а затем протестировать правило.</span><span class="sxs-lookup"><span data-stu-id="e134c-312">When everything's configured, you'll need to save or apply these, and then you'll want to test the rule.</span></span>
    
### <a name="create-a-web-publishing-rule-for-port-80-optional"></a><span data-ttu-id="e134c-313">Создание правила веб-публикации для порта 80 (необязательно)</span><span class="sxs-lookup"><span data-stu-id="e134c-313">Create a web publishing rule for port 80 (Optional)</span></span>

1. <span data-ttu-id="e134c-314">Откройте интерфейс обратного прокси-сервера.</span><span class="sxs-lookup"><span data-stu-id="e134c-314">Open your Reverse proxy interface.</span></span>
    
2. <span data-ttu-id="e134c-315">Необходимо определить, где в интерфейсе создаются правила веб-публикации,  и выбрать параметр "Создать" или "Создать" (он может находиться в меню или вкладке в зависимости от конфигурации обратного прокси-сервера). </span><span class="sxs-lookup"><span data-stu-id="e134c-315">You'll need to locate where in the interface you create your web publishing rules, and choose the **New** or **Create** option (it may be on a menu or tab, depending on your Reverse proxy configuration).</span></span> <span data-ttu-id="e134c-316">Вы ищете вариант создания нового правила веб-публикации.</span><span class="sxs-lookup"><span data-stu-id="e134c-316">You are looking for the option to create a new web publishing rule.</span></span>
    
3. <span data-ttu-id="e134c-317">Как правило, необходимо ввести следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="e134c-317">Typically, you will need to enter the following information:</span></span>
    
   - <span data-ttu-id="e134c-318">**Name**: the name for your rule</span><span class="sxs-lookup"><span data-stu-id="e134c-318">**Name**: the name for your rule</span></span>
    
   - <span data-ttu-id="e134c-319">**Действие правила:** в этом случае  это правило "Разрешить", что-то передается через обратный прокси-сервер.</span><span class="sxs-lookup"><span data-stu-id="e134c-319">**Rule Action**: In this case it's an **Allow** rule, you're letting something pass through your Reverse proxy.</span></span>
    
   - <span data-ttu-id="e134c-320">Правило **публикации** или выбираемый вариант — один **веб-сайт или под балансировка нагрузки.**</span><span class="sxs-lookup"><span data-stu-id="e134c-320">The **Publishing** rule or option you're choosing would be **single web site or load balancer**.</span></span>
    
   - <span data-ttu-id="e134c-321">Для подключения к опубликованного веб-серверу или ферме это должно быть не **защищенное подключение.**</span><span class="sxs-lookup"><span data-stu-id="e134c-321">This needs to be a **non-secured connection to connect to the published Web server or farm**.</span></span>
    
   - <span data-ttu-id="e134c-322">Вам потребуется опубликовать путь для внутренней публикации и ввести FQDN для **VIP-адреса** балансировки нагрузки пула переднего sfb_pool01.contoso.local. </span><span class="sxs-lookup"><span data-stu-id="e134c-322">You're going to need to publish a path for **Internal Publishing**, and enter the FQDN for the **VIP address** of your Front End pool's load balancer, an example would be sfb_pool01.contoso.local.</span></span>
    
   - <span data-ttu-id="e134c-323">В качестве пути для публикации необходимо ввести _, но также необходимо **/\\** переадлить исходный заглавный_заданный_заданный_заголок\*\*.</span><span class="sxs-lookup"><span data-stu-id="e134c-323">You should type **/\\** _ as the path to be published, but you also need to _\*forward the original host header\*\*.</span></span>
    
   - <span data-ttu-id="e134c-324">Существует возможность для сведений или сведений об общедоступных **или внешних** именах.</span><span class="sxs-lookup"><span data-stu-id="e134c-324">There will be an option for **public or external name** details or information.</span></span> <span data-ttu-id="e134c-325">В этом месте вы сможете ввести:</span><span class="sxs-lookup"><span data-stu-id="e134c-325">This is the place where you'll be able to enter:</span></span>
    
   - <span data-ttu-id="e134c-326">**Принимать запросы,** но это должно быть имя домена.</span><span class="sxs-lookup"><span data-stu-id="e134c-326">**Accept requests**, but it should be for the domain name.</span></span>
    
   - <span data-ttu-id="e134c-327">Введите **имя** **lyncdiscover.**</span><span class="sxs-lookup"><span data-stu-id="e134c-327">For the **Name**, you should enter **lyncdiscover.**</span></span> <span data-ttu-id="e134c-328"><sipdomain> (это внешний URL-адрес службы автонаружия).</span><span class="sxs-lookup"><span data-stu-id="e134c-328"><sipdomain> (this is the external Autodiscover Service URL).</span></span>
    
   - <span data-ttu-id="e134c-329">Будет параметр **Path,** и вам потребуется ввести **/\\** _здесь.</span><span class="sxs-lookup"><span data-stu-id="e134c-329">There will be a **Path** option, and you'll need to enter **/\\** _ here.</span></span>
    
   - <span data-ttu-id="e134c-330">Вам потребуется выбрать веб-прослушиватель или разрешить обратному прокси-серверу создать его для вас.</span><span class="sxs-lookup"><span data-stu-id="e134c-330">You'll need to select a web listener, or allow your Reverse proxy to create one for you.</span></span>
    
   - <span data-ttu-id="e134c-331">*_Authentication Delegation*\* should be set to **No delegation**, but direct client authentication **should not** be allowed.</span><span class="sxs-lookup"><span data-stu-id="e134c-331">_ *Authentication Delegation*\* should be set to **No delegation**, but direct client authentication **should not** be allowed.</span></span>
    
   - <span data-ttu-id="e134c-332">Правило должно быть установлено для **всех пользователей.**</span><span class="sxs-lookup"><span data-stu-id="e134c-332">The rule should be set to **All users**.</span></span>
    
   - <span data-ttu-id="e134c-333">Это должны быть все сведения, необходимые для создания этого правила и позволяющие продолжить.</span><span class="sxs-lookup"><span data-stu-id="e134c-333">This should be all the information you need to create this rule and allow you to proceed.</span></span>
    
4. <span data-ttu-id="e134c-334">Необходимо **настроить порты** веб-сервера. Необходимо сделать следующее:</span><span class="sxs-lookup"><span data-stu-id="e134c-334">The **Web Server** ports will need to be set, you'll need to do the following:</span></span>
    
   - <span data-ttu-id="e134c-335">**Перенаправление запросов на ПОРТ HTTP** и номер порта должен быть **8080.**</span><span class="sxs-lookup"><span data-stu-id="e134c-335">**Redirect requests to HTTP port** and the port number should be **8080**.</span></span>
    
   - <span data-ttu-id="e134c-336">**Запросы на перенаправление на SSL-порт,** а номер порта должен быть **4443.**</span><span class="sxs-lookup"><span data-stu-id="e134c-336">**Redirect requests to SSL port** and the port number should be **4443**.</span></span>
    
5. <span data-ttu-id="e134c-337">Если все настроено, вам потребуется сохранить или применить их, а затем протестировать правило.</span><span class="sxs-lookup"><span data-stu-id="e134c-337">When everything's configured, you'll need to save or apply these, and then you'll want to test the rule.</span></span>
    
## <a name="configure-autodiscover-for-mobility-with-hybrid-deployments"></a><span data-ttu-id="e134c-338">Настройка автооружия для мобильной работы с гибридными развертываниями</span><span class="sxs-lookup"><span data-stu-id="e134c-338">Configure Autodiscover for Mobility with hybrid deployments</span></span>
<span data-ttu-id="e134c-339"><a name="ConfigAutoD"> </a></span><span class="sxs-lookup"><span data-stu-id="e134c-339"><a name="ConfigAutoD"> </a></span></span>

<span data-ttu-id="e134c-340">Гибридные среды в Skype для бизнеса Server — это среды, которые объединяются в локальной среде и среде O365.</span><span class="sxs-lookup"><span data-stu-id="e134c-340">Hybrid environments in Skype for Business Server are environments that combine an on-premises and O365 environment.</span></span> <span data-ttu-id="e134c-341">Если Skype для бизнеса Server работает в гибридной среде, служба автонаружества должна иметь возможность найти пользователя из любой из этих сред.</span><span class="sxs-lookup"><span data-stu-id="e134c-341">When you have Skype for Business Server working in a Hybrid environment, the Autodiscover service needs to be able to locate a user from either of these environments.</span></span>
  
<span data-ttu-id="e134c-342">Чтобы мобильные клиенты обнаруживали, где находится пользователь, необходимо настроить службу автоотнаружия с использованием нового URL-адреса.</span><span class="sxs-lookup"><span data-stu-id="e134c-342">To let mobile clients discover where a user's located, the Autodiscover service needs to be configured with a new uniform resource locator (URL).</span></span> <span data-ttu-id="e134c-343">Ниже описана последовательность действий.</span><span class="sxs-lookup"><span data-stu-id="e134c-343">The steps are:</span></span>
  
1. <span data-ttu-id="e134c-344">Откройте Skype для бизнеса Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="e134c-344">Open Skype for Business Server Management Shell.</span></span>
    
2. <span data-ttu-id="e134c-345">Чтобы получить значение атрибута **ProxyFQDN** для среды Skype для бизнеса Server, запустите следующую среду:</span><span class="sxs-lookup"><span data-stu-id="e134c-345">Run the following to get the value of the attribute **ProxyFQDN** for your Skype for Business Server environment:</span></span>
    
   ```powershell
   Get-CsHostingProvider
   ```

3. <span data-ttu-id="e134c-346">Затем, еще в окне оболочки, запустите:</span><span class="sxs-lookup"><span data-stu-id="e134c-346">Then, still in the shell window, run:</span></span>
    
   ```powershell
   Set-CsHostingProvider -Identity [identity] -AutodiscoverUrl https://webdir.online.lync.com/autodiscover/autodiscoverservice.svc/root
   ```

    <span data-ttu-id="e134c-347">Где [идентификатор] заменяется именем домена общего пространства адресов SIP.</span><span class="sxs-lookup"><span data-stu-id="e134c-347">Where [identity] is replaced with the domain name of the shared SIP address space.</span></span>
    
## <a name="test-your-mobility-deployment"></a><span data-ttu-id="e134c-348">Тестирование развертывания mobility</span><span class="sxs-lookup"><span data-stu-id="e134c-348">Test your Mobility deployment</span></span>
<span data-ttu-id="e134c-349"><a name="TestMobility"> </a></span><span class="sxs-lookup"><span data-stu-id="e134c-349"><a name="TestMobility"> </a></span></span>

<span data-ttu-id="e134c-350">После развертывания Skype для бизнеса Server Mobility Service и службы автообнаружия Skype для бизнеса Server необходимо выполнить тестовую транзакцию, чтобы убедиться, что развертывание работает правильно.</span><span class="sxs-lookup"><span data-stu-id="e134c-350">Once you've deployed Skype for Business Server Mobility Service and Skype for Business Server Autodiscover Service, you'll want to run a test transaction, to make sure your deployment's working right.</span></span> <span data-ttu-id="e134c-351">Вы можете запустить **Test-CsUcwaConference,** чтобы проверить возможность двух пользователей создавать, присоединяться и общаться в конференции.</span><span class="sxs-lookup"><span data-stu-id="e134c-351">You can run **Test-CsUcwaConference** to test the ability of two users to create, join and communicate in a conference.</span></span> <span data-ttu-id="e134c-352">Для этого тестирования вам потребуется два пользователя (реальные или тестовые) с полными учетными данными.</span><span class="sxs-lookup"><span data-stu-id="e134c-352">You will need two users (real or test) and their full credentials to do this testing.</span></span> <span data-ttu-id="e134c-353">Эта команда будет работать как для клиентов Skype для бизнеса, так и для клиентов Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e134c-353">This command will work for both Skype for Business clients as well as Lync Server 2013 clients.</span></span>
  
<span data-ttu-id="e134c-354">For Lync Server 2010 clients on Skype for Business Server 2015, you'll need to run **Test-CsMcxP2PIM** to test.</span><span class="sxs-lookup"><span data-stu-id="e134c-354">For Lync Server 2010 clients on Skype for Business Server 2015, you'll need to run **Test-CsMcxP2PIM** to test.</span></span> <span data-ttu-id="e134c-355">Ваши пользователи Lync Server 2010 по-прежнему должны быть действительными или предварительно заранее протестировать пользователей, и вам потребуется их пароль.</span><span class="sxs-lookup"><span data-stu-id="e134c-355">Your Lync Server 2010 users will still have to be actual users, or predefined test users, and you'll need their password credentials.</span></span>

> [!NOTE]
> <span data-ttu-id="e134c-356">Поддержка СЛУЖБЫ MCX (Mobility Service) для устаревших мобильных клиентов больше недоступна в Skype для бизнеса Server 2019.</span><span class="sxs-lookup"><span data-stu-id="e134c-356">MCX (Mobility Service) support for legacy mobile clients is no longer available in Skype for Business Server 2019.</span></span> <span data-ttu-id="e134c-357">Все текущие мобильные клиенты Skype для бизнеса уже используют веб-API объединенных коммуникаций (UCWA) для поддержки обмена мгновенными сообщениями, присутствия и контактов.</span><span class="sxs-lookup"><span data-stu-id="e134c-357">All current Skype for Business mobile clients already use Unified Communications Web API (UCWA) to support instant messaging (IM), presence, and contacts.</span></span> <span data-ttu-id="e134c-358">Пользователям с устаревшими клиентами, использующими MCX, потребуется обновиться до текущего клиента.</span><span class="sxs-lookup"><span data-stu-id="e134c-358">Users with legacy clients using MCX will need to upgrade to a current client.</span></span>
  
### <a name="test-conferencing-for-skype-for-business-and-lync-2013-mobile-clients"></a><span data-ttu-id="e134c-359">Тестирование услуг для мобильных клиентов Skype для бизнеса и Lync 2013</span><span class="sxs-lookup"><span data-stu-id="e134c-359">Test conferencing for Skype for Business and Lync 2013 mobile clients</span></span>

1. <span data-ttu-id="e134c-360">Войдите как участник роли **CsAdministrator** на любом компьютере, на котором установлены **оболочка** управления Skype для бизнеса Server и **Ocscore.**</span><span class="sxs-lookup"><span data-stu-id="e134c-360">Log on as a member of the **CsAdministrator** role on any computer where **Skype for Business Server Management Shell** and **Ocscore** are installed.</span></span>
    
2. <span data-ttu-id="e134c-361">Запустите **skype для бизнеса Server Management Shell** (вы можете ввести имя в поиске или перейти во все программы и выбрать его). </span><span class="sxs-lookup"><span data-stu-id="e134c-361">Start the **Skype for Business Server Management Shell** (you might type the name in search or go to **All Programs** and choose it).</span></span>
    
3. <span data-ttu-id="e134c-362">В командной строке введите:</span><span class="sxs-lookup"><span data-stu-id="e134c-362">At the command line, enter:</span></span>
    
   ```powershell
   Test-CsUcwaConference -TargetFqdn <FQDN of Front End pool> -Authentication <TrustedServer | Negotiate | ClientCertificate | LiveID> -OrganizerSipAddress sip:<SIP address of test user 1> -OrganizerCredential <test user 1 credentials> -ParticipantSipAddress sip:<SIP address of test user 2> -ParticipantCredential <test user 2 credentials> -v
   ```

   <span data-ttu-id="e134c-363">Кроме того, можно установить учетные данные в сценарии и передать их в тестовый cmdlet.</span><span class="sxs-lookup"><span data-stu-id="e134c-363">It's also possible to set credentials in a script and pass them to the test cmdlet.</span></span> <span data-ttu-id="e134c-364">Ниже приведен пример этого.</span><span class="sxs-lookup"><span data-stu-id="e134c-364">We have an example of this below.</span></span>
    
   ```powershell
   $passwd1 = ConvertTo-SecureString "Password01" -AsPlainText -Force
   $passwd2 = ConvertTo-SecureString "Password02" -AsPlainText -Force
   $testuser1 = New-Object Management.Automation.PSCredential("contoso\UserName1", $passwd1)
   $testuser2 = New-Object Management.Automation.PSCredential("contoso\UserName2", $passwd2)
   Test-CsUcwaConference -TargetFqdn pool01.contoso.com -Authentication Negotiate -OrganizerSipAddress sip:UserName1@contoso.com -OrganizerCredential $testuser1 -ParticipantSipAddress sip:UserName2@contoso.com -ParticipantCredential $testuser2 -v
   ```

### <a name="test-conferencing-for-lync-2010-mobile-clients"></a><span data-ttu-id="e134c-365">Тестирование для мобильных клиентов Lync 2010</span><span class="sxs-lookup"><span data-stu-id="e134c-365">Test conferencing for Lync 2010 mobile clients</span></span>

> [!NOTE]
> <span data-ttu-id="e134c-366">Поддержка СЛУЖБЫ MCX (Mobility Service) для устаревших мобильных клиентов больше недоступна в Skype для бизнеса Server 2019.</span><span class="sxs-lookup"><span data-stu-id="e134c-366">MCX (Mobility Service) support for legacy mobile clients is no longer available in Skype for Business Server 2019.</span></span> <span data-ttu-id="e134c-367">Все текущие мобильные клиенты Skype для бизнеса уже используют веб-API объединенных коммуникаций (UCWA) для поддержки обмена мгновенными сообщениями, присутствия и контактов.</span><span class="sxs-lookup"><span data-stu-id="e134c-367">All current Skype for Business mobile clients already use Unified Communications Web API (UCWA) to support instant messaging (IM), presence, and contacts.</span></span> <span data-ttu-id="e134c-368">Пользователям с устаревшими клиентами, использующими MCX, потребуется обновиться до текущего клиента.</span><span class="sxs-lookup"><span data-stu-id="e134c-368">Users with legacy clients using MCX will need to upgrade to a current client.</span></span>

1. <span data-ttu-id="e134c-369">Войдите в систему с ролью **CsAdministrator** на любом компьютере, на котором установлены **skype для бизнеса Server Management Shell** и **Ocscore.**</span><span class="sxs-lookup"><span data-stu-id="e134c-369">Log on as a member of the **CsAdministrator** role on any computer where **Skype for Business Server Management Shell** and **Ocscore** are installed.</span></span>
    
2. <span data-ttu-id="e134c-370">Запустите **skype для бизнеса Server Management Shell** (вы можете ввести имя в поиске или перейти во все программы и выбрать его). </span><span class="sxs-lookup"><span data-stu-id="e134c-370">Start the **Skype for Business Server Management Shell** (you might type the name in search or go to **All Programs** and choose it).</span></span>
    
3. <span data-ttu-id="e134c-371">В командной строке введите:</span><span class="sxs-lookup"><span data-stu-id="e134c-371">At the command line, enter:</span></span>
    
   ```powershell
   Test-CsMcxP2PIM -TargetFqdn <FQDN of Front End pool> -Authentication <TrustedServer | Negotiate | ClientCertificate | LiveID> -SenderSipAddress sip:<SIP address of test user 1> -SenderCredential <test user 1 credentials> -ReceiverSipAddress sip:<SIP address of test user 2> -ReceiverCredential <test user 2 credentials> -v
   ```

   <span data-ttu-id="e134c-372">Кроме того, можно установить учетные данные в сценарии и передать их в тестовый cmdlet.</span><span class="sxs-lookup"><span data-stu-id="e134c-372">It's also possible to set credentials in a script and pass them to the test cmdlet.</span></span> <span data-ttu-id="e134c-373">Ниже приведен пример этого.</span><span class="sxs-lookup"><span data-stu-id="e134c-373">We have an example of this below.</span></span>
    
   ```powershell
   $passwd1 = ConvertTo-SecureString "Password01" -AsPlainText -Force
   $passwd2 = ConvertTo-SecureString "Password02" -AsPlainText -Force
   $tuc1 = New-Object Management.Automation.PSCredential("contoso\UserName1", $passwd1)
   $tuc2 = New-Object Management.Automation.PSCredential("contoso\UserName2", $passwd2)
   Test-CsMcxP2PIM -TargetFqdn pool01.contoso.com -Authentication Negotiate -SenderSipAddress sip:UserName1@contoso.com -SenderCredential $tuc1 -ReceiverSipAddress sip:UserName2@contoso.com -ReceiverCredential $tuc2 -v
   ```

<span data-ttu-id="e134c-374">Для дальнейшего просмотра процедур команд можно проверить [Test-CsUcwaConference](https://docs.microsoft.com/powershell/module/skype/test-csucwaconference?view=skype-ps) и [Test-CsMcxP2PIM.](https://docs.microsoft.com/powershell/module/skype/test-csmcxp2pim?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="e134c-374">To review the command procedures further, you can check out [Test-CsUcwaConference](https://docs.microsoft.com/powershell/module/skype/test-csucwaconference?view=skype-ps) and [Test-CsMcxP2PIM](https://docs.microsoft.com/powershell/module/skype/test-csmcxp2pim?view=skype-ps).</span></span>
  
## <a name="configure-for-push-notifications"></a><span data-ttu-id="e134c-375">Настройка для использования push-уведомлений</span><span class="sxs-lookup"><span data-stu-id="e134c-375">Configure for push notifications</span></span>
<span data-ttu-id="e134c-376"><a name="ConfigPush"> </a></span><span class="sxs-lookup"><span data-stu-id="e134c-376"><a name="ConfigPush"> </a></span></span>

<span data-ttu-id="e134c-377">Push-уведомления в виде индикаторов событий, значков или оповещений можно отправить на мобильное устройство, даже если приложение Skype или Lync неактивно.</span><span class="sxs-lookup"><span data-stu-id="e134c-377">Push notifications, in the form of badges, icons, or alerts, can be sent to a mobile device even when the Skype or Lync app is inactive.</span></span> <span data-ttu-id="e134c-378">Но что такое push-уведомления?</span><span class="sxs-lookup"><span data-stu-id="e134c-378">But what are push notifications?</span></span> <span data-ttu-id="e134c-379">Это оповещения о событиях, такие как новое или пропущенное приглашение для мгновенных сообщения, или для полученной голосовой почты.</span><span class="sxs-lookup"><span data-stu-id="e134c-379">They are event alerts, like a new or missed IM invitation, or for a received voicemail.</span></span> <span data-ttu-id="e134c-380">Служба Skype для бизнеса Server Mobility отправляет эти уведомления облачной службе push-уведомлений Skype для бизнеса Server, которая затем отправляет уведомления в службу push-уведомлений Майкрософт (MSNS) для пользователей Windows Phone.</span><span class="sxs-lookup"><span data-stu-id="e134c-380">The Skype for Business Server Mobility service sends these notifications to the cloud-based Skype for Business Server Push Notification Service, which then sends the notifications to the Microsoft Push Notification Service (MSNS) for Windows Phone users.</span></span>
  
<span data-ttu-id="e134c-381">Эта функция не изменилась по сравнению с Lync Server 2013, но если у вас есть Skype для бизнеса Server, необходимо сделать следующее:</span><span class="sxs-lookup"><span data-stu-id="e134c-381">This functionality is unchanged from Lync Server 2013, but if you have a Skype for Business Server, you'll want to do the following:</span></span>
  
- <span data-ttu-id="e134c-382">Для skype для бизнеса Server Edge Server добавьте нового поставщика услуг размещения, Microsoft Skype для бизнеса Online, а затем настроите федерацию поставщика услуг размещения между вашей организацией и Skype для бизнеса Online.</span><span class="sxs-lookup"><span data-stu-id="e134c-382">For a Skype for Business Server Edge Server, add a new hosting provider, Microsoft Skype for Business Online, and then set up hosting provider federation between your organization and Skype for Business Online.</span></span>
    
- <span data-ttu-id="e134c-383">Чтобы включить push-уведомления, запустим для этого **cmdlet Set-CsPushNotificationConfiguration.**</span><span class="sxs-lookup"><span data-stu-id="e134c-383">Enable push notifications by running the **Set-CsPushNotificationConfiguration** cmdlet.</span></span> <span data-ttu-id="e134c-384">По умолчанию push-уведомления отключены.</span><span class="sxs-lookup"><span data-stu-id="e134c-384">By default, push notifications are turned off.</span></span>
    
- <span data-ttu-id="e134c-385">Проверьте конфигурацию федерации и push-уведомления.</span><span class="sxs-lookup"><span data-stu-id="e134c-385">Test your federation configuration and push notifications.</span></span>
    
### <a name="configure-your-skype-for-business-edge-server-for-push-notifications"></a><span data-ttu-id="e134c-386">Настройка skype для бизнеса Edge Server для push-уведомлений</span><span class="sxs-lookup"><span data-stu-id="e134c-386">Configure your Skype for Business Edge Server for push notifications</span></span>

1. <span data-ttu-id="e134c-387">Войдите с учетной записью, которая является членом роли **CsAdministrator,** на компьютер, на котором установлены Skype для бизнеса **Server Management Shell** и **Ocscore.**</span><span class="sxs-lookup"><span data-stu-id="e134c-387">Log on, with an account that's a member of the **CsAdministrator** role, to a computer where **Skype for Business Server Management Shell** and **Ocscore** are installed.</span></span>
    
2. <span data-ttu-id="e134c-388">Запустите **оболочку управления Skype для бизнеса Server.**</span><span class="sxs-lookup"><span data-stu-id="e134c-388">Start the **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="e134c-389">Добавление поставщика услуг размещения Skype для бизнеса Server через Интернет.</span><span class="sxs-lookup"><span data-stu-id="e134c-389">Add a Skype for Business Server online hosting provider.</span></span>
    
   ```powershell
   New-CsHostingProvider -Identity <unique identifier for hosting provider> -Enabled $True -ProxyFQDN <FQDN for the Access Server used by the hosting provider> -VerificationLevel UseSourceVerification
   ```

   <span data-ttu-id="e134c-390">Например:</span><span class="sxs-lookup"><span data-stu-id="e134c-390">As an example:</span></span>
    
   ```powershell
   New-CsHostingProvider -Identity "SkypeOnline" -Enabled $True -ProxyFQDN "sipfed.online.lync.com" -VerificationLevel UseSourceVerification
   ```

    > [!NOTE]
    > <span data-ttu-id="e134c-391">Не может быть более одного отношения федерации с одним поставщиком услуг размещения.</span><span class="sxs-lookup"><span data-stu-id="e134c-391">You can't have more than one federation relationship with a single hosting provider.</span></span> <span data-ttu-id="e134c-392">Поэтому, если вы уже настроили поставщика услуг размещения, который имеет отношение федерации с sipfed.online.lync.com, не добавляйте для него другого поставщика услуг размещения, даже если идентификатор поставщика услуг размещения не является SkypeOnline.</span><span class="sxs-lookup"><span data-stu-id="e134c-392">So, if you've already set up a hosting provider that has a federation relationship with sipfed.online.lync.com, don't add another hosting provider for it, even if the identity of the hosting provider is something other than SkypeOnline.</span></span> 
  
4. <span data-ttu-id="e134c-393">Настройка федерации поставщика услуг размещения между организацией и службой push-уведомлений в Skype для бизнеса Online.</span><span class="sxs-lookup"><span data-stu-id="e134c-393">Set up the hosting provider federation between your organization and the Push Notification Service at Skype for Business Online.</span></span> <span data-ttu-id="e134c-394">В командной строке введите:</span><span class="sxs-lookup"><span data-stu-id="e134c-394">At the command line, you'll need to type:</span></span>
    
   ```powershell
    New-CsAllowedDomain -Identity "push.lync.com"
   ```

### <a name="enable-push-notifications"></a><span data-ttu-id="e134c-395">Включить push-уведомления</span><span class="sxs-lookup"><span data-stu-id="e134c-395">Enable push notifications</span></span>

1. <span data-ttu-id="e134c-396">Войдите с учетной записью, которая является членом роли **CsAdministrator,** на компьютер, на котором установлены Skype для бизнеса **Server Management Shell** и **Ocscore.**</span><span class="sxs-lookup"><span data-stu-id="e134c-396">Log on, with an account that's a member of the **CsAdministrator** role, to a computer where **Skype for Business Server Management Shell** and **Ocscore** are installed.</span></span>
    
2. <span data-ttu-id="e134c-397">Запустите **оболочку управления Skype для бизнеса Server.**</span><span class="sxs-lookup"><span data-stu-id="e134c-397">Start the **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="e134c-398">В включить push-уведомления:</span><span class="sxs-lookup"><span data-stu-id="e134c-398">Enable push notifications:</span></span>
    
   ```powershell
   Set-CsPushNotificationConfiguration -EnableMicrosoftPushNotificationService $True
   ```

4. <span data-ttu-id="e134c-399">Включить федерацию:</span><span class="sxs-lookup"><span data-stu-id="e134c-399">Enable Federation:</span></span>
     
   ```powershell
   Set-CsAccessEdgeConfiguration -AllowFederatedUsers $True
   ```

### <a name="test-federation-and-push-notifications"></a><span data-ttu-id="e134c-400">Проверка федерации и push-уведомлений</span><span class="sxs-lookup"><span data-stu-id="e134c-400">Test federation and push notifications</span></span>

1. <span data-ttu-id="e134c-401">Войдите с учетной записью, которая является членом роли **CsAdministrator,** на компьютер, на котором установлены Skype для бизнеса **Server Management Shell** и **Ocscore.**</span><span class="sxs-lookup"><span data-stu-id="e134c-401">Log on, with an account that's a member of the **CsAdministrator** role, to a computer where **Skype for Business Server Management Shell** and **Ocscore** are installed.</span></span>
    
2. <span data-ttu-id="e134c-402">Запустите **оболочку управления Skype для бизнеса Server.**</span><span class="sxs-lookup"><span data-stu-id="e134c-402">Start the **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="e134c-403">Проверьте конфигурацию федерации:</span><span class="sxs-lookup"><span data-stu-id="e134c-403">Test the federation configuration:</span></span>
    
   ```powershell
   Test-CsFederatedPartner -TargetFqdn <FQDN of Access Edge server used for federated SIP traffic> -Domain <FQDN of federated domain> -ProxyFqdn <FQDN of the Access Edge server used by the federated organization>
   ```

    <span data-ttu-id="e134c-404">Например:</span><span class="sxs-lookup"><span data-stu-id="e134c-404">As an example:</span></span>
    
   ```powershell
   Test-CsFederatedPartner -TargetFqdn accessproxy.contoso.com -Domain push.lync.com -ProxyFqdn sipfed.online.lync.com
   ```

4. <span data-ttu-id="e134c-405">Протестировать push-уведомления:</span><span class="sxs-lookup"><span data-stu-id="e134c-405">Test your push notifications:</span></span>
    
   ```powershell
   Test-CsMcxPushNotification -AccessEdgeFqdn <Access Edge service FQDN>
   ```

    <span data-ttu-id="e134c-406">Например:</span><span class="sxs-lookup"><span data-stu-id="e134c-406">As an example:</span></span>
    
   ```powershell
   Test-CsMcxPushNotification -AccessEdgeFqdn accessproxy.contoso.com
   ```

## <a name="configure-mobility-policy"></a><span data-ttu-id="e134c-407">Настройка политики мобильности</span><span class="sxs-lookup"><span data-stu-id="e134c-407">Configure Mobility policy</span></span>
<span data-ttu-id="e134c-408"><a name="ConfigMob"> </a></span><span class="sxs-lookup"><span data-stu-id="e134c-408"><a name="ConfigMob"> </a></span></span>

<span data-ttu-id="e134c-409">С помощью Skype для бизнеса Server вы можете определить, кто может использовать службу Mobility Service, Call via Work, voIP или видеосвязь, а также будет ли требоваться Wi-Fi для VoIP или видео.</span><span class="sxs-lookup"><span data-stu-id="e134c-409">You have the ability with Skype for Business Server to determine who can use your Mobility service, Call via Work, voice over IP (VoIP), or video, as well as whether WiFi will be required for VoIP or video.</span></span> <span data-ttu-id="e134c-410">Звонок с помощью работы позволяет мобильному пользователю использовать свой рабочий номер телефона вместо номера мобильного телефона при размещении и приеме звонков.</span><span class="sxs-lookup"><span data-stu-id="e134c-410">Call via Work lets a mobile user use their work phone number, instead of their mobile phone number, when placing and receiving calls.</span></span> <span data-ttu-id="e134c-411">Пользователь на другом конце линии не увидит номер мобильного пользователя на мобильном телефоне, и это позволяет этому мобильному пользователю избежать расходов на исходяющие звонки.</span><span class="sxs-lookup"><span data-stu-id="e134c-411">The person on the other end of the line won't see that mobile user's cell phone number, and it lets that mobile user avoid outgoing call charges.</span></span> <span data-ttu-id="e134c-412">Когда voIP и видео настроены, пользователи могут принимать и делать voIP-звонки и видео.</span><span class="sxs-lookup"><span data-stu-id="e134c-412">When VoIP and video are set up, users can take and make VoIP calls and video.</span></span> <span data-ttu-id="e134c-413">Параметры использования Wi-Fi определяют, должно ли мобильное устройство пользователя использовать сеть Wi-Fi через сеть передачи данных.</span><span class="sxs-lookup"><span data-stu-id="e134c-413">The settings for WiFi usage determine whether a user's mobile device will be required to use a WiFi network over a cellular data network.</span></span>
  
<span data-ttu-id="e134c-414">Мобильные устройства, функции "Позвонить с работы", а также функции VoIP и видео включены по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="e134c-414">Mobility, Call via Work, and the VoIP and video features are all enabled by default.</span></span> <span data-ttu-id="e134c-415">Параметр, требуя wiFi для VoIP и видео, отключен.</span><span class="sxs-lookup"><span data-stu-id="e134c-415">The setting to require WiFi for VoIP and video are disabled.</span></span> <span data-ttu-id="e134c-416">Администратор может изменить его глобально, по сайту или по пользователю.</span><span class="sxs-lookup"><span data-stu-id="e134c-416">An Admin has the ability to change this, either globally, by site, or by user.</span></span>
  
<span data-ttu-id="e134c-417">Чтобы иметь возможность использовать функции мобильности и функции "Позвонить с работы", пользователям необходимо:</span><span class="sxs-lookup"><span data-stu-id="e134c-417">To be able to use Mobility features and Call via Work, users need to be:</span></span>
  
- <span data-ttu-id="e134c-418">Включено для Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="e134c-418">Enabled for Skype for Business Server</span></span>
    
- <span data-ttu-id="e134c-419">Включено для Корпоративная голосовая связь.</span><span class="sxs-lookup"><span data-stu-id="e134c-419">Enabled for Enterprise Voice.</span></span>
    
- <span data-ttu-id="e134c-420">Назначена политика мобильности, для параметра **EnableMobility** **установлено** true.</span><span class="sxs-lookup"><span data-stu-id="e134c-420">Assigned a Mobility policy that has the **EnableMobility** option set to **True**.</span></span>
    
<span data-ttu-id="e134c-421">Чтобы пользователи могли использовать "Позвонить с работы", им также потребуется:</span><span class="sxs-lookup"><span data-stu-id="e134c-421">For users to be able to use Call via Work, they'll also need to be:</span></span>
  
- <span data-ttu-id="e134c-422">Назначена политика голосовой связи с выбранным параметром **"Включить** одновременные звонки на телефоны".</span><span class="sxs-lookup"><span data-stu-id="e134c-422">Assigned a voice policy that has the **Enable simultaneous ringing of phones** option selected.</span></span>
    
- <span data-ttu-id="e134c-423">Назначена политика мобильности, для **политики EnableOutsideVoice установлено** **true.**</span><span class="sxs-lookup"><span data-stu-id="e134c-423">Assigned a Mobility policy that has the **EnableOutsideVoice** set to **True**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="e134c-424">Пользователи, не включенные в Корпоративная голосовая связь, могут использовать свои мобильные устройства для звонков по Skype по VoIP или присоединяться к конференциям с помощью ссылки "Щелкните, чтобы присоединиться" на мобильных устройствах, если для политики голосовой связи, с которыми они связаны, установлены соответствующие параметры.</span><span class="sxs-lookup"><span data-stu-id="e134c-424">Users who aren't enabled for Enterprise Voice can use their mobile devices to make Skype to Skype VoIP calls or can join conferences by using the Click to Join link while on their mobile devices, if the appropriate options are set for the Voice policy they're associated with.</span></span> <span data-ttu-id="e134c-425">Дополнительные подробности в разделе "ПЛАНИРОВАНИЕ".</span><span class="sxs-lookup"><span data-stu-id="e134c-425">There's more detail in the PLANNING topic.</span></span> 
  
### <a name="modify-global-mobility-policy"></a><span data-ttu-id="e134c-426">Изменение глобальной политики мобильности</span><span class="sxs-lookup"><span data-stu-id="e134c-426">Modify global Mobility policy</span></span>

1. <span data-ttu-id="e134c-427">Войдите с учетной записью, которая является членом роли **CsAdministrator,** на компьютер, на котором установлены Skype для бизнеса **Server Management Shell** и **Ocscore.**</span><span class="sxs-lookup"><span data-stu-id="e134c-427">Log on, with an account that's a member of the **CsAdministrator** role, to a computer where **Skype for Business Server Management Shell** and **Ocscore** are installed.</span></span>
    
2. <span data-ttu-id="e134c-428">Запустите **оболочку управления Skype для бизнеса Server.**</span><span class="sxs-lookup"><span data-stu-id="e134c-428">Start the **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="e134c-429">Отключите доступ к мобильности и вызову с помощью work глобально, введя:</span><span class="sxs-lookup"><span data-stu-id="e134c-429">Turn off access to Mobility and Call via Work globally by typing:</span></span>
    
   ```powershell
   Set-CsMobilityPolicy -EnableMobility $False -EnableOutsideVoice $False
   ```

    > [!NOTE]
    > <span data-ttu-id="e134c-430">Вы можете отключить "Позвонить с работы", не отключая доступ к мобильной работе.</span><span class="sxs-lookup"><span data-stu-id="e134c-430">You can turn off Call via Work without turning off access to Mobility.</span></span> <span data-ttu-id="e134c-431">Но вы не можете отключить мобильность, не отключив также "Позвонить с работы".</span><span class="sxs-lookup"><span data-stu-id="e134c-431">But you can't turn off Mobility without also turning off Call via Work.</span></span> 
  
    <span data-ttu-id="e134c-432">Дополнительные сведения можно узнать в [set-CsMobilityPolicy.](https://docs.microsoft.com/powershell/module/skype/set-csmobilitypolicy?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="e134c-432">For more info, check out [Set-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/set-csmobilitypolicy?view=skype-ps).</span></span>
    
### <a name="modify-mobility-policy-by-site"></a><span data-ttu-id="e134c-433">Изменение политики мобильности по сайту</span><span class="sxs-lookup"><span data-stu-id="e134c-433">Modify Mobility policy by site</span></span>

1. <span data-ttu-id="e134c-434">Войдите с учетной записью, которая является членом роли **CsAdministrator,** на компьютер, на котором установлены Skype для бизнеса **Server Management Shell** и **Ocscore.**</span><span class="sxs-lookup"><span data-stu-id="e134c-434">Log on, with an account that's a member of the **CsAdministrator** role, to a computer where **Skype for Business Server Management Shell** and **Ocscore** are installed.</span></span>
    
2. <span data-ttu-id="e134c-435">Запустите **оболочку управления Skype для бизнеса Server.**</span><span class="sxs-lookup"><span data-stu-id="e134c-435">Start the **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="e134c-436">Вы можете создать политику на уровне сайта, отключить VoIP и видеосвязь, включить "Требовать Wi-Fi для IP-аудио" и "Требовать Wi-Fi для IP-видео по сайту".</span><span class="sxs-lookup"><span data-stu-id="e134c-436">You can create a site-level policy, turn off VoIP and video, enable Require WiFi for IP Audio, and Require WiFi for IP Video by site.</span></span> <span data-ttu-id="e134c-437">Тип:</span><span class="sxs-lookup"><span data-stu-id="e134c-437">Type:</span></span>
    
   ```powershell
   New-CsMobilityPolicy -Identity site:<site identifier> -EnableIPAudioVideo $false -RequireWiFiForIPAudio $True -RequireWiFiforIPVideo $True
   ```

    <span data-ttu-id="e134c-438">Подробнее: [New-CsMobilityPolicy.](https://docs.microsoft.com/powershell/module/skype/new-csmobilitypolicy?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="e134c-438">Learn more at [New-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/new-csmobilitypolicy?view=skype-ps).</span></span>
    
### <a name="modify-mobility-policy-by-user"></a><span data-ttu-id="e134c-439">Изменение политики мобильности для пользователя</span><span class="sxs-lookup"><span data-stu-id="e134c-439">Modify Mobility policy by user</span></span>

1. <span data-ttu-id="e134c-440">Войдите с учетной записью, которая является членом роли **CsAdministrator,** на компьютер, на котором установлены Skype для бизнеса **Server Management Shell** и **Ocscore.**</span><span class="sxs-lookup"><span data-stu-id="e134c-440">Log on, with an account that's a member of the **CsAdministrator** role, to a computer where **Skype for Business Server Management Shell** and **Ocscore** are installed.</span></span>
    
2. <span data-ttu-id="e134c-441">Запустите **оболочку управления Skype для бизнеса Server.**</span><span class="sxs-lookup"><span data-stu-id="e134c-441">Start the **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="e134c-442">Создайте политики мобильности на уровне пользователя и отключите мобильность и звонок с помощью работы для пользователей.</span><span class="sxs-lookup"><span data-stu-id="e134c-442">Create user level Mobility policies and turn off Mobility and Call via Work by user.</span></span> <span data-ttu-id="e134c-443">Тип:</span><span class="sxs-lookup"><span data-stu-id="e134c-443">Type:</span></span>
    
   ```powershell
   New-CsMobilityPolicy -Identity <policy name> -EnableMobility $False -EnableOutsideVoice $False
   Grant-CsMobilityPolicy -Identity <user identifier> -PolicyName <policy name>
   ```

    <span data-ttu-id="e134c-444">Дополнительный пример с примерами данных:</span><span class="sxs-lookup"><span data-stu-id="e134c-444">A further example with sample data:</span></span>
    
   ```powershell
   New-CsMobilityPolicy "tag:disableOutsideVoice" -EnableOutsideVoice $False
   Grant-CsMobilityPolicy -Identity MobileUser1@contoso.com -PolicyName tag:disableOutsideVoice
   ```

    > [!NOTE]
    > <span data-ttu-id="e134c-445">Вы можете отключить "Позвонить с работы", не отключая доступ к мобильной работе.</span><span class="sxs-lookup"><span data-stu-id="e134c-445">You can turn off Call via Work without turning off access to Mobility.</span></span> <span data-ttu-id="e134c-446">Но вы не можете отключить мобильность, не отключив также "Позвонить с работы".</span><span class="sxs-lookup"><span data-stu-id="e134c-446">But you can't turn off Mobility without also turning off Call via Work.</span></span> 
  

