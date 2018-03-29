---
title: Развертывание и настройка служб мобильности в Skype для бизнеса Server 2015
ms.author: heidip
author: microsoftheidi
ms.date: 2/6/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8ec6197a-3d1e-4b42-9465-564044cdab1a
description: В этой статье поможет выполнить действия, чтобы настроить существующий Скайп для установки Business Server 2015 для использования службы мобильности, позволяя мобильными устройствами должны иметь возможность использовать преимущества Скайп для функций мобильной работы Business Server.
ms.openlocfilehash: c23974477ec815fca9c0cd3d78ac7acc0b81912e
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/28/2018
---
# <a name="deploy-and-configure-mobility-for-skype-for-business-server-2015"></a><span data-ttu-id="41041-103">Развертывание и настройка служб мобильности в Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="41041-103">Deploy and Configure Mobility for Skype for Business Server 2015</span></span>
 
<span data-ttu-id="41041-104">В этой статье поможет выполнить действия, чтобы настроить существующий Скайп для установки Business Server 2015 для использования службы мобильности, позволяя мобильными устройствами должны иметь возможность использовать преимущества Скайп для функций мобильной работы Business Server.</span><span class="sxs-lookup"><span data-stu-id="41041-104">This article will walk you through the steps to configure an existing Skype for Business Server 2015 installation to use the Mobility service, allowing your mobile devices to be able to take advantage of Skype for Business Server Mobility features.</span></span>
  
<span data-ttu-id="41041-105">Просмотра статьи [Планирование для мобильных устройств для Скайп для Business Server 2015](../plan-your-deployment/mobility.md) , можно для перехода с указанные ниже действия для развертывания мобильности в вашей Скайп среды Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="41041-105">Having reviewed the [Plan for Mobility for Skype for Business Server 2015](../plan-your-deployment/mobility.md) article, you should be ready to proceed with the steps below to deploy Mobility into your Skype for Business Server 2015 environment.</span></span> <span data-ttu-id="41041-106">Ниже перечислены шаги (, мы в случае включительно, в этой таблице список разрешений):</span><span class="sxs-lookup"><span data-stu-id="41041-106">The steps are as follows (and we're including in this table a permissions list):</span></span>
  
|<span data-ttu-id="41041-107">**Этап**</span><span class="sxs-lookup"><span data-stu-id="41041-107">**Phase**</span></span>|<span data-ttu-id="41041-108">**Разрешения**</span><span class="sxs-lookup"><span data-stu-id="41041-108">**Permissions**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="41041-109">Создание записей DNS</span><span class="sxs-lookup"><span data-stu-id="41041-109">Create DNS records</span></span>](deploy-and-configure-mobility.md#CreateDNSRec) <br/> |<span data-ttu-id="41041-110">Администраторы домена</span><span class="sxs-lookup"><span data-stu-id="41041-110">Domain Admins</span></span>  <br/> <span data-ttu-id="41041-111">DNSAdmins</span><span class="sxs-lookup"><span data-stu-id="41041-111">DNSAdmins</span></span>  <br/> |
|[<span data-ttu-id="41041-112">Изменение сертификатов</span><span class="sxs-lookup"><span data-stu-id="41041-112">Modify certificates</span></span>](deploy-and-configure-mobility.md#ModCerts) <br/> |<span data-ttu-id="41041-113">Локальный администратор</span><span class="sxs-lookup"><span data-stu-id="41041-113">Local Administrator</span></span>  <br/> |
|[<span data-ttu-id="41041-114">Настройка обратного прокси-сервера</span><span class="sxs-lookup"><span data-stu-id="41041-114">Configure the reverse proxy</span></span>](deploy-and-configure-mobility.md#ConfigRP) <br/> |<span data-ttu-id="41041-115">Локальный администратор</span><span class="sxs-lookup"><span data-stu-id="41041-115">Local Administrator</span></span>  <br/> |
|[<span data-ttu-id="41041-116">Настройка службы автообнаружения для мобильной работы с гибридными развертываниями</span><span class="sxs-lookup"><span data-stu-id="41041-116">Configure Autodiscover for Mobility with hybrid deployments</span></span>](deploy-and-configure-mobility.md#ConfigAutoD) <br/> |<span data-ttu-id="41041-117">Администраторы домена</span><span class="sxs-lookup"><span data-stu-id="41041-117">Domain Admins</span></span>  <br/> |
|[<span data-ttu-id="41041-118">Тестирование развертывания мобильности</span><span class="sxs-lookup"><span data-stu-id="41041-118">Test your Mobility deployment</span></span>](deploy-and-configure-mobility.md#TestMobility) <br/> |<span data-ttu-id="41041-119">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="41041-119">CsAdministrator</span></span>  <br/> |
|[<span data-ttu-id="41041-120">Настройка для использования push-уведомлений</span><span class="sxs-lookup"><span data-stu-id="41041-120">Configure for push notifications</span></span>](deploy-and-configure-mobility.md#ConfigPush) <br/> |<span data-ttu-id="41041-121">RtcUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="41041-121">RtcUniversalServerAdmins</span></span>  <br/> |
|[<span data-ttu-id="41041-122">Настройка политики мобильности</span><span class="sxs-lookup"><span data-stu-id="41041-122">Configure Mobility policy</span></span>](deploy-and-configure-mobility.md#ConfigMob) <br/> |<span data-ttu-id="41041-123">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="41041-123">CsAdministrator</span></span>  <br/> |
   
<span data-ttu-id="41041-p102">Перед выполнением действий, описываемых в следующих разделах, необходимо ознакомиться с разделом, посвященным планированию. Если у вас возникают какие-либо вопросы, обращайтесь к этому разделу.</span><span class="sxs-lookup"><span data-stu-id="41041-p102">All the following sections contain steps that assume you've read the Planning topic. If anything's confusing you, feel free to check out the information there.</span></span>
  
## <a name="create-dns-records"></a><span data-ttu-id="41041-126">Создание записей DNS</span><span class="sxs-lookup"><span data-stu-id="41041-126">Create DNS records</span></span>
<span data-ttu-id="41041-127"><a name="CreateDNSRec"> </a></span><span class="sxs-lookup"><span data-stu-id="41041-127"></span></span>

<span data-ttu-id="41041-128">Уже может быть их как часть вашего Скайп для среды Business Server, но необходимо создать следующие записи для автоматического обнаружения для работы:</span><span class="sxs-lookup"><span data-stu-id="41041-128">You may already have these as part of your Skype for Business Server environment, but you do need to create the following records for Autodiscovery to work:</span></span>
  
- <span data-ttu-id="41041-129">Внутренняя DNS-запись для поддержки мобильных пользователей, которые подключаются изнутри сети организации</span><span class="sxs-lookup"><span data-stu-id="41041-129">An internal DNS record to support mobile users who're connecting from within your organization's network.</span></span>
    
- <span data-ttu-id="41041-130">Внутренняя DNS-запись для поддержки мобильных пользователей, которые подключаются из-за пределов сети организации</span><span class="sxs-lookup"><span data-stu-id="41041-130">An external (or public) DNS record to support mobile users who're connecting from outside your organization's network.</span></span>
    
<span data-ttu-id="41041-131">Это могут быть записи имен A (узел) или CNAME. Обратите внимание, что создавать записи обоих типов не обязательно, поскольку в этой статье описываются все возможные варианты действий.</span><span class="sxs-lookup"><span data-stu-id="41041-131">These records can be either A (host) names or CNAME records (you don't have to make both, we're just including the steps for everything here).</span></span>
  
### <a name="create-an-internal-dns-cname-record"></a><span data-ttu-id="41041-132">Создание внутренней DNS-записи CNAME</span><span class="sxs-lookup"><span data-stu-id="41041-132">Create an internal DNS CNAME record</span></span>

1. <span data-ttu-id="41041-133">Войдите в систему DNS-сервера в сети, который входит в группу **Администраторы домена** или **DnsAdmins**.</span><span class="sxs-lookup"><span data-stu-id="41041-133">Log into a DNS server in your network that's either a member of the **Domain Admins** group or the **DnsAdmins** group.</span></span>
    
2. <span data-ttu-id="41041-134">Нажмите кнопку **Пуск** и выберите **Администрирование**. Если этот компонент отсутствует в меню "Пуск", воспользуйтесь полем **Поиск**. Затем щелкните **DNS**, чтобы открыть административную оснастку DNS.</span><span class="sxs-lookup"><span data-stu-id="41041-134">Click **Start**, Choose **Administrative Tools** (you may need to **Search** for it if it's not an option off the Start menu), and then click **DNS** to open the DNS administrative snap-in.</span></span>
    
3. <span data-ttu-id="41041-135">В левой панели окна консоли, вам потребуется перейти к домену на номер домашнего для вашей Скайп для серверов переднего плана Business Server и разверните узел **Зоны прямого просмотра** существует.</span><span class="sxs-lookup"><span data-stu-id="41041-135">In the left-hand pane of the console window, you'll need to go to the domain that's home to your Skype for Business Server's Front End Servers, and expand the **Forward Lookup Zones** there.</span></span>
    
4. <span data-ttu-id="41041-136">Проверьте, какие из следующих записей присутствуют в этом узле:</span><span class="sxs-lookup"><span data-stu-id="41041-136">Take a moment to see which of the following you have:</span></span>
    
   - <span data-ttu-id="41041-137">Любой A или AAAA записи узлов для сервера переднего плана (Standard или Enterprise) или pool(s) переднего плана.</span><span class="sxs-lookup"><span data-stu-id="41041-137">Any host A or AAAA records for your Front End Server (Standard or Enterprise) or Front End pool(s).</span></span>
    
   - <span data-ttu-id="41041-138">Любой узел A или AAAA записи для директора или директора пула (необязательные конфигурация которые могут возникнуть в вашем развертывании).</span><span class="sxs-lookup"><span data-stu-id="41041-138">Any host A or AAAA records for a Director or Director pool (an optional configuration you may have in your deployment).</span></span>
    
5. <span data-ttu-id="41041-139">После этого щелкните правой кнопкой мыши имя домена SIP и выберите в меню пункт **Создать псевдоним (CNAME)**.</span><span class="sxs-lookup"><span data-stu-id="41041-139">Once you've noted this, right-click your SIP domain name, and then choose **New Alias (CNAME)** from the menu.</span></span>
    
6. <span data-ttu-id="41041-140">В текстовое поле **Имя псевдонима** введите lyncdiscoverinternal в качестве имени узла для URL-адреса внутренней службы автообнаружения.</span><span class="sxs-lookup"><span data-stu-id="41041-140">In the **Alias name** textbox, type lyncdiscoverinternal for your host name, for the internal Autodiscover service URL.</span></span>
    
7. <span data-ttu-id="41041-141">В **полное доменное имя (полное доменное имя для целевого узла**, вам потребуется введите или укажите внутренний Web Services полное доменное имя для переднего плана пула (или один сервер переднего плана, или пул директоров или директора), определенный в шаге 4.</span><span class="sxs-lookup"><span data-stu-id="41041-141">In the **Fully qualified domain name (FQDN for target host**, you'll need to type or browse to the internal Web Services FQDN for your Front End pool (or single Front End Server, or Director pool or Director), identified in step 4 above.</span></span> <span data-ttu-id="41041-142">Это имя вводится нажмите кнопку ОК.</span><span class="sxs-lookup"><span data-stu-id="41041-142">Click OK when this is entered.</span></span>
    
8. <span data-ttu-id="41041-143">Вам потребуется создать запись CNAME автообнаружения в зоне прямого просмотра для каждого домена SIP, поддерживаемые в вашей Скайп среды Business Server.</span><span class="sxs-lookup"><span data-stu-id="41041-143">You'll need to create a new Autodiscover CNAME record in the forward lookup zone for each SIP domain supported in your Skype for Business Server environment.</span></span>
    
### <a name="create-an-external-dns-cname-record"></a><span data-ttu-id="41041-144">Создание внешней DNS-записи CNAME</span><span class="sxs-lookup"><span data-stu-id="41041-144">Create an external DNS CNAME record</span></span>

1. <span data-ttu-id="41041-145">Поскольку вы можете использовать разных общедоступных поставщиков DNS, в этом разделе приводятся универсальные действия. Войдите в систему общедоступного поставщика DNS с использованием учетной записи с правами на создание новых записей DNS.</span><span class="sxs-lookup"><span data-stu-id="41041-145">These steps are generic, because we can't tell what public DNS provider you might be using, but we still want to help you out. Please log into your public DNS provider with an account that will be able to make new DNS records there.</span></span>
    
2. <span data-ttu-id="41041-146">На данный момент времени SIP-домена должна уже существовать существует для Скайп для Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="41041-146">At this point in time, a SIP domain should already exist there for Skype for Business Server 2015.</span></span> <span data-ttu-id="41041-147">Разверните узел **Зоны прямого просмотра** для этого домена SIP или откройте его любым другим способом.</span><span class="sxs-lookup"><span data-stu-id="41041-147">Expand the **Forward Lookup Zone** for this SIP domain, or otherwise open it up.</span></span>
    
3. <span data-ttu-id="41041-148">Проверьте, какие из следующих записей присутствуют в этом узле:</span><span class="sxs-lookup"><span data-stu-id="41041-148">Take a moment to see which of the following you have:</span></span>
    
   - <span data-ttu-id="41041-149">Любой A или AAAA записи узлов для сервера переднего плана (Standard или Enterprise) или pool(s) переднего плана.</span><span class="sxs-lookup"><span data-stu-id="41041-149">Any host A or AAAA records for your Front End Server (Standard or Enterprise) or Front End pool(s).</span></span>
    
   - <span data-ttu-id="41041-150">Любой узел A или AAAA записи для директора или директора пула (необязательные конфигурация которые могут возникнуть в вашем развертывании).</span><span class="sxs-lookup"><span data-stu-id="41041-150">Any host A or AAAA records for a Director or Director pool (an optional configuration you may have in your deployment).</span></span>
    
4. <span data-ttu-id="41041-151">Имея на руках эти сведения, вы можете выбрать команду **Создать псевдоним (CNAME)**.</span><span class="sxs-lookup"><span data-stu-id="41041-151">Once you have that information, you should be able to select an option for creating a **New Alias (CNAME)**.</span></span>
    
5. <span data-ttu-id="41041-152">В поле **Имя псевдонима** введите lyncdiscover в качестве URL-адреса внешней службы автообнаружения.</span><span class="sxs-lookup"><span data-stu-id="41041-152">Now you should be able to enter an **Alias Name**, you need to enter lyncdiscover here for the external Autodiscover service URL.</span></span>
    
6. <span data-ttu-id="41041-153">Далее следует область ввода в **поле полное доменное имя для целевого узла**, это должно быть полное доменное имя для вашего переднего плана пула (или одним сервером переднего плана, или пул директоров или Director), определенного в шаге 3 выше.</span><span class="sxs-lookup"><span data-stu-id="41041-153">Next there should be an area to enter in a **FQDN for target host**, this will need to be the FQDN for your Front End pool (or single Front End Server, or Director pool or Director), identified in step 3 above.</span></span>
    
7. <span data-ttu-id="41041-154">Может потребоваться сохранить здесь, или если вам потребуется создать дополнительные записи CNAME в зоне прямого просмотра каждого SIP-домена в вашей Скайп среды Business Server, необходимо сделать, но как только вы будете готовы, сохраните данные.</span><span class="sxs-lookup"><span data-stu-id="41041-154">You may need to save here, or if you need to create additional CNAME records in the forward lookup zone of each SIP domain in your Skype for Business Server environment, you should do that, but once you're ready, save your work.</span></span>
    
### <a name="create-an-internal-dns-a-record"></a><span data-ttu-id="41041-155">Создание записи A внутреннего DNS</span><span class="sxs-lookup"><span data-stu-id="41041-155">Create an internal DNS A record</span></span>

1. <span data-ttu-id="41041-156">Войдите в систему DNS-сервера в сети, который входит в группу **Администраторы домена** или **DnsAdmins**.</span><span class="sxs-lookup"><span data-stu-id="41041-156">Log into a DNS server in your network that's either a member of the **Domain Admins** group or the **DnsAdmins** group.</span></span>
    
2. <span data-ttu-id="41041-157">Нажмите кнопку **Пуск** и выберите **Администрирование**. Если этот компонент отсутствует в меню "Пуск", воспользуйтесь полем **Поиск**. Затем щелкните **DNS**, чтобы открыть административную оснастку DNS.</span><span class="sxs-lookup"><span data-stu-id="41041-157">Click **Start**, Choose **Administrative Tools** (you may need to **Search** for it if it's not an option off the Start menu), and then click **DNS** to open the DNS administrative snap-in.</span></span>
    
3. <span data-ttu-id="41041-158">В левой панели окна консоли, вам потребуется перейти к домену на номер домашнего для вашей Скайп для серверов переднего плана Business Server и разверните узел **Зоны прямого просмотра** существует.</span><span class="sxs-lookup"><span data-stu-id="41041-158">In the left-hand pane of the console window, you'll need to go to the domain that's home to your Skype for Business Server's Front End Servers, and expand the **Forward Lookup Zones** there.</span></span>
    
4. <span data-ttu-id="41041-159">Проверьте, какие из следующих записей присутствуют в этом узле:</span><span class="sxs-lookup"><span data-stu-id="41041-159">Take a moment to see which of the following you have:</span></span>
    
   - <span data-ttu-id="41041-160">Любой A или AAAA записи узлов для сервера переднего плана (Standard или Enterprise) или pool(s) переднего плана.</span><span class="sxs-lookup"><span data-stu-id="41041-160">Any host A or AAAA records for your Front End Server (Standard or Enterprise) or Front End pool(s).</span></span>
    
   - <span data-ttu-id="41041-161">Любой узел A или AAAA записи для директора или директора пула (необязательные конфигурация которые могут возникнуть в вашем развертывании).</span><span class="sxs-lookup"><span data-stu-id="41041-161">Any host A or AAAA records for a Director or Director pool (an optional configuration you may have in your deployment).</span></span>
    
5. <span data-ttu-id="41041-162">После этого щелкните правой кнопкой мыши имя домена SIP и выберите в меню пункт **Создать узел (A или AAAA)**.</span><span class="sxs-lookup"><span data-stu-id="41041-162">Once you've noted this, right-click your SIP domain name, and then choose **New Host (A or AAAA)** from the menu.</span></span>
    
6. <span data-ttu-id="41041-163">В текстовое поле **Имя** введите lyncdiscoverinternal в качестве имени узла для URL-адреса внутренней службы автообнаружения.</span><span class="sxs-lookup"><span data-stu-id="41041-163">In the **Name** textbox, type lyncdiscoverinternal for your host name, for the internal Autodiscover service URL.</span></span>
    
7. <span data-ttu-id="41041-164">В текстовом поле **IP-адрес** типа Web Services IP-адрес внутреннего для переднего плана пула (или один сервер переднего плана, или пул директоров или директоров), определенный в приведенном выше шаге 4.</span><span class="sxs-lookup"><span data-stu-id="41041-164">In the **IP Address** textbox, type the internal Web Services IP address for your Front End pool (or single Front End Server, or Director pool or Director), identified in step 4 above.</span></span>
    
8. <span data-ttu-id="41041-165">Затем щелкните **Добавить узел** и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="41041-165">When this is done, click **Add Host**, and then click **OK**.</span></span>
    
9. <span data-ttu-id="41041-166">Вам потребуется создать новые записи автообнаружения A или AAAA в зоне прямого просмотра для каждого домена SIP, поддерживаемые в вашей Скайп среды Business Server.</span><span class="sxs-lookup"><span data-stu-id="41041-166">You'll need to create a new Autodiscover A or AAAA records in the forward lookup zone for each SIP domain supported in your Skype for Business Server environment.</span></span> <span data-ttu-id="41041-167">Для этого повторяйте шаги с 6 по 8 необходимое число раз.</span><span class="sxs-lookup"><span data-stu-id="41041-167">To do this, repeat steps 6-8 as many times as needed.</span></span>
    
10. <span data-ttu-id="41041-168">По завершении нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="41041-168">When you're done, click **Done**.</span></span>
    
### <a name="create-an-external-dns-a-record"></a><span data-ttu-id="41041-169">Создание записи A внешнего DNS</span><span class="sxs-lookup"><span data-stu-id="41041-169">Create an external DNS A record</span></span>

1. <span data-ttu-id="41041-170">Поскольку вы можете использовать разных общедоступных поставщиков DNS, в этом разделе приводятся универсальные действия. Войдите в систему общедоступного поставщика DNS с использованием учетной записи с правами на создание новых записей DNS.</span><span class="sxs-lookup"><span data-stu-id="41041-170">These steps are generic, because we can't tell what public DNS provider you might be using, but we still want to help you out. Please log into your public DNS provider with an account that will be able to make new DNS records there.</span></span>
    
2. <span data-ttu-id="41041-171">На данный момент времени SIP-домена должна уже существовать существует для Скайп для Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="41041-171">At this point in time, a SIP domain should already exist there for Skype for Business Server 2015.</span></span> <span data-ttu-id="41041-172">Разверните узел **Зоны прямого просмотра** для этого домена SIP или откройте его любым другим способом.</span><span class="sxs-lookup"><span data-stu-id="41041-172">Expand the **Forward Lookup Zone** for this SIP domain, or otherwise open it up.</span></span>
    
3. <span data-ttu-id="41041-173">Проверьте, какие из следующих записей присутствуют в этом узле:</span><span class="sxs-lookup"><span data-stu-id="41041-173">Take a moment to see which of the following you have:</span></span>
    
   - <span data-ttu-id="41041-174">Любой A или AAAA записи узлов для сервера переднего плана (Standard или Enterprise) или pool(s) переднего плана.</span><span class="sxs-lookup"><span data-stu-id="41041-174">Any host A or AAAA records for your Front End Server (Standard or Enterprise) or Front End pool(s).</span></span>
    
   - <span data-ttu-id="41041-175">Любой узел A или AAAA записи для директора или директора пула (необязательные конфигурация которые могут возникнуть в вашем развертывании).</span><span class="sxs-lookup"><span data-stu-id="41041-175">Any host A or AAAA records for a Director or Director pool (an optional configuration you may have in your deployment).</span></span>
    
4. <span data-ttu-id="41041-176">Имея на руках эти сведения, вы можете выбрать команду **Создать узел (A или AAAA)**.</span><span class="sxs-lookup"><span data-stu-id="41041-176">Once you have that information, you should be able to select an option for creating a **New Host A or AAAA**.</span></span>
    
5. <span data-ttu-id="41041-177">В поле **Имя** введите lyncdiscover в качестве URL-адреса внешней службы автообнаружения.</span><span class="sxs-lookup"><span data-stu-id="41041-177">Now you should be able to enter a **Name**, you need to enter lyncdiscover here for the external Autodiscover service URL.</span></span>
    
6. <span data-ttu-id="41041-178">Теперь должен появиться область ввода в **IP-адреса**, это должно быть IP-адресов для переднего плана пула (или одним сервером переднего плана, или пул директоров или директоров), определенный в шаге 3.</span><span class="sxs-lookup"><span data-stu-id="41041-178">Next there should be an area to enter in a **IP Addresss**, this will need to be the IP for your Front End pool (or single Front End Server, or Director pool or Director), identified in step 3 above.</span></span>
    
7. <span data-ttu-id="41041-179">Может потребоваться сохранить здесь, или если вам необходимо создать дополнительные A или AAAA-записи в зоне прямого просмотра каждого SIP-домена для вашей Скайп среды Business Server, это следует сделать, но один раз вы будете готовы, сохранение результатов работы.</span><span class="sxs-lookup"><span data-stu-id="41041-179">You may need to save here, or if you need to create additional A or AAAA records in the forward lookup zone of each SIP domain for your Skype for Business Server environment, you should do that, but once you're ready, save your work.</span></span>
    
## <a name="modify-certificates"></a><span data-ttu-id="41041-180">Изменение сертификатов</span><span class="sxs-lookup"><span data-stu-id="41041-180">Modify certificates</span></span>
<span data-ttu-id="41041-181"><a name="ModCerts"> </a></span><span class="sxs-lookup"><span data-stu-id="41041-181"></span></span>

<span data-ttu-id="41041-182">Если у вас есть вопросы о планировании вокруг сертификаты, мы документированы, в нашем статье [Планирование для мобильных устройств для Скайп для Business Server 2015](../plan-your-deployment/mobility.md) .</span><span class="sxs-lookup"><span data-stu-id="41041-182">If you have questions about Planning around certificates, we've documented that in our [Plan for Mobility for Skype for Business Server 2015](../plan-your-deployment/mobility.md) article.</span></span> <span data-ttu-id="41041-183">После этого вы можете продолжать знакомство с этим пошаговым руководством:</span><span class="sxs-lookup"><span data-stu-id="41041-183">Once you've reviewed that, we'll walk you through the following:</span></span>
  
- <span data-ttu-id="41041-184">Требуются ли новые сертификаты?</span><span class="sxs-lookup"><span data-stu-id="41041-184">Do I need new certificates?</span></span>
    
- <span data-ttu-id="41041-185">Запрос новых сертификатов из центра сертификации.</span><span class="sxs-lookup"><span data-stu-id="41041-185">Requesting new certificates from your Certificate Authority (CA).</span></span>
    
- <span data-ttu-id="41041-186">Замена существующих сертификатов новыми с помощью PowerShell.</span><span class="sxs-lookup"><span data-stu-id="41041-186">Updating your in-place certificates with the replacements using PowerShell.</span></span>
    
- <span data-ttu-id="41041-187">Проверка сертификатов, с помощью оснастки сертификатов в консоль управления (MMC).</span><span class="sxs-lookup"><span data-stu-id="41041-187">Checking the certificates using the Certificates snapin in the Microsoft Management Console (MMC).</span></span>
    
### <a name="do-i-need-new-certificates"></a><span data-ttu-id="41041-188">Требуются ли новые сертификаты?</span><span class="sxs-lookup"><span data-stu-id="41041-188">Do I need new certificates?</span></span>

1. <span data-ttu-id="41041-189">Сначала требуется проверить существующие сертификаты и наличие в них необходимых записей.</span><span class="sxs-lookup"><span data-stu-id="41041-189">First, you may need to check and see what certificates are in-place, and whether or not they have the entries you need.</span></span> <span data-ttu-id="41041-190">Для этого необходимо войти в вашей Скайп для сервера Business Server 2015 с использованием учетной записи, которая является учетной записью локального администратора.</span><span class="sxs-lookup"><span data-stu-id="41041-190">To do that, you'll need to log into your Skype for Business Server 2015 server with an account that's a local Administrator.</span></span> <span data-ttu-id="41041-191">Кроме того, для выполнения некоторых действий этой учетной записи могут потребоваться права на доступ к выдающему центру сертификации.</span><span class="sxs-lookup"><span data-stu-id="41041-191">This account may also need to have rights to the issuing Certificate Authority (CA), for some of these steps.</span></span>
    
2. <span data-ttu-id="41041-192">Откройте Скайп оболочки управления Business Server (можно выполнить поиск их расположение, если у вас нет его прикрепленных на панель задач и меню Пуск).</span><span class="sxs-lookup"><span data-stu-id="41041-192">Open the Skype for Business Server Management Shell (you can use Search to find it if you don't have it pinned to your Start menu or task bar).</span></span>
    
3. <span data-ttu-id="41041-p109">Важно знать, какие сертификаты были назначены до того, как вы попытаетесь добавить или обновить сертификат. В командной строке введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="41041-p109">It's going to be essential for you to know what certificates have been assigned before you try adding an updated certificate. So at the command, type:</span></span>
    
   ```
   Get-CsCertificate
   ```

4. <span data-ttu-id="41041-p110">На шаге 3 вы получите сведения, относящиеся к вашей уникальной среде. Опираясь на них, определите, используются ли у вас один или несколько сертификатов для нескольких компонентов. Параметр **Использование** содержит информацию об использовании сертификата, а параметр **Отпечаток** определяет, применяются ли для этих целей один или несколько сертификатов.</span><span class="sxs-lookup"><span data-stu-id="41041-p110">The information from Step 3 will be unique to you. You need to look it over to determine if you have a single certificate that's been assigned for multiple things, or whether you have a different certificate assigned for the different components that need them. The **Use** parameter will tell you how a certificate's being used, and the **Thumbprint** parameter will tell you if it's all the same certificate, or multiple certs.</span></span>
    
5. <span data-ttu-id="41041-p111">Если вы не настроили записи альтернативного имени субъекта согласно рекомендациям в разделе "Планирование", вам необходимо запросить один или несколько новых сертификатов (в зависимости от конфигурации) из центра сертификации.</span><span class="sxs-lookup"><span data-stu-id="41041-p111">If you have the SAN entries recommended in our Planning section, you're good. If not, you'll need to request a new certificate, or multiple certificates (depending on your configuration) from your Certificate Authority.</span></span>
    
### <a name="request-a-new-certificate-or-certificates-from-your-certificate-authority-ca"></a><span data-ttu-id="41041-200">Запрос одного или нескольких новых сертификатов из центра сертификации.</span><span class="sxs-lookup"><span data-stu-id="41041-200">Request a new certificate, or certificates, from your Certificate Authority (CA)</span></span>

1. <span data-ttu-id="41041-201">Проверив существующие записи альтернативного имени субъекта по описанной выше процедуре, вы определили наличие **одного сертификата** и обнаружили, что некоторые необходимые записи отсутствуют.</span><span class="sxs-lookup"><span data-stu-id="41041-201">After you've checked to see what SAN entries you have, you know you have a **single certificate** (after checking via the steps above), and you learned you don't have all the entries you need.</span></span> <span data-ttu-id="41041-202">В этом случае вам необходимо запросить новый сертификат в центре сертификации.</span><span class="sxs-lookup"><span data-stu-id="41041-202">A new certificate request needs to be made to your CA.</span></span> <span data-ttu-id="41041-203">Откройте вашей Скайп для Business Server PowerShell:</span><span class="sxs-lookup"><span data-stu-id="41041-203">Open your Skype for Business Server PowerShell:</span></span>
    
   - <span data-ttu-id="41041-204">Для отсутствующей записи альтернативного имени субъекта для службы автообнаружения (замените параметр -Ca путем к вашему центру сертификации):</span><span class="sxs-lookup"><span data-stu-id="41041-204">For a missing Autodiscover Service SAN (replacing the -Ca parameter with your own Certificate Authority path):</span></span>
    
   ```
   Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -Ca dc\myca -AllSipDomain -verbose
   ```

   - <span data-ttu-id="41041-p113">Если в вашей среде присутствует несколько доменов SIP, вы не можете использовать параметр AllSipDomain, как показано в примере выше. Вместо него вам потребуется параметр DomainName, при выборе которого требуется определить полное доменное имя для записей lyncdiscoverinternal и lyncdiscover. В этом случае пример будет иметь следующий вид (замените параметр -Ca путем к вашему центру сертификации):</span><span class="sxs-lookup"><span data-stu-id="41041-p113">Now, if you have multiple SIP domains, you can't use the AllSipDomain paramater as in the example above. You'll need to use the DomainName parameter instead. And when you use the DomainName parameter, you've got to define the FQDN for the lyncdiscoverinternal and lyncdiscover records. An example would be (replacing the -Ca parameter with your own Certificate Authority path):</span></span>
    
   ```
   Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -Ca dc\myca -DomainName "LyncdiscoverInternal.contoso.com, LyncdiscoverInternal.contoso.net" -verbose
   ```

2. <span data-ttu-id="41041-209">Проверив существующие записи альтернативного имени субъекта по описанной выше процедуре, вы определили наличие **нескольких сертификатов** и обнаружили, что некоторые необходимые записи отсутствуют.</span><span class="sxs-lookup"><span data-stu-id="41041-209">Or, after you've checked to see what SAN entries you have, you found you have **multiple certificates** that don't have all the entries you need.</span></span> <span data-ttu-id="41041-210">В этом случае вам необходимо запросить новый сертификат в центре сертификации.</span><span class="sxs-lookup"><span data-stu-id="41041-210">A new certificate request needs to be made to your CA.</span></span> <span data-ttu-id="41041-211">Откройте вашей Скайп для Business Server PowerShell:</span><span class="sxs-lookup"><span data-stu-id="41041-211">Open your Skype for Business Server PowerShell:</span></span>
    
   - <span data-ttu-id="41041-212">Для отсутствующей записи альтернативного имени субъекта для службы автообнаружения (замените параметр -Ca путем к вашему центру сертификации):</span><span class="sxs-lookup"><span data-stu-id="41041-212">For a missing Autodiscover Service SAN (replacing the -Ca parameter with your own Certificate Authority path):</span></span>
    
   ```
   Request-CsCertificate -New -Type WebServicesInternal -Ca dc\myca -AllSipDomain -verbose
   ```

   - <span data-ttu-id="41041-p115">Если в вашей среде присутствует несколько доменов SIP, вы не можете использовать параметр AllSipDomain, как показано в примере выше. Вместо него вам потребуется параметр DomainName, при выборе которого требуется определить полное доменное имя для записей lyncdiscoverinternal и lyncdiscover. В этом случае примеры будут иметь следующий вид (замените параметр -Ca путем к вашему центру сертификации):</span><span class="sxs-lookup"><span data-stu-id="41041-p115">Now, if you have multiple SIP domains, you can't use the AllSipDomain paramater as in the example above. You'll need to use the DomainName parameter instead. And when you use the DomainName parameter, you've got to define the FQDN for the lyncdiscoverinternal and lyncdiscover records. Examples would be (replacing the -Ca parameter with your own Certificate Authority path):</span></span>
    
   ```
   Request-CsCertificate -New -Type WebServicesInternal -Ca dc\myca -DomainName "LyncdiscoverInternal.contoso.com, LyncdiscoverInternal.contoso.net" -verbose
   ```

   ```
   Request-CsCertificate -New -Type WebServicesExternal -Ca dc\myca -DomainName "Lyncdiscover.contoso.com, Lyncdiscover.contoso.net" -verbose
   ```

   - <span data-ttu-id="41041-217">После создания новых сертификатов в центре сертификации вам необходимо назначить их.</span><span class="sxs-lookup"><span data-stu-id="41041-217">Once the new certificates have been generated by the CA, you're going to need to assign them.</span></span>
    
### <a name="assign-certificates-using-skype-for-business-server-management-shell"></a><span data-ttu-id="41041-218">Назначение сертификатов с помощью командной консоли Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="41041-218">Assign certificates using Skype for Business Server Management Shell</span></span>

- <span data-ttu-id="41041-219">В зависимости от результатов анализа среды, проведенного в разделе "Требуются ли новые сертификаты?", вам необходимо выполнить **одно** из следующих действий.</span><span class="sxs-lookup"><span data-stu-id="41041-219">Depending on what you found in the Do I need new certifications section above, you need to run **one** of the following.</span></span>
    
  - <span data-ttu-id="41041-220">Если вы используете для всех компонентов один и тот же сертификат (одинаковые отпечатки), выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="41041-220">If you have a single certificate for everything (the thumbprints are identical) then you need to run this:</span></span>
    
  ```
  Set-CsCertificate -Type <certificate(s) from the Use parameter> -Thumbprint <unique identifier>
  ```

  - <span data-ttu-id="41041-221">Если вы используете несколько сертификатов с разными отпечатками, выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="41041-221">If you've got different certificates for things (the thumbprints are all different), run this instead:</span></span>
    
  ```
  Set-CsCertificate -Type Default -Thumbprint <certificate thumbprint>
  Set-CsCertificate -Type WebServicesInternal -Thumbprint <certificate thumbprint>
  Set-CsCertificate -Type WebServicesExternal -Thumbprint <certificate thumbprint>
  ```

### <a name="viewing-certificates-in-the-microsoft-management-console-mmc"></a><span data-ttu-id="41041-222">Просмотр сертификатов с помощью консоли управления (MMC)</span><span class="sxs-lookup"><span data-stu-id="41041-222">Viewing certificates in the Microsoft Management Console (MMC)</span></span>

1. <span data-ttu-id="41041-p116">Для просмотра всех сертификатов вы можете использовать оснастку сертификатов в консоли MMC. Чтобы открыть это приложение во всплывающем окне, достаточно ввести "MMC" в поле поиска.</span><span class="sxs-lookup"><span data-stu-id="41041-p116">You have an option to look at your certificates using the Certificates snap-in for the MMC. Simply type MMC into search and it should pop up as an application option,.</span></span>
    
2. <span data-ttu-id="41041-p117">Чтобы добавить оснастку сертификатов, щелкните **Файл** и выберите **Добавить или удалить оснастку** (также можно использовать сочетание клавиш **CTRL+M**). Выберите элемент **Сертификаты** в панели слева, щелкните **Учетная запись компьютера** во всплывающем окне и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="41041-p117">To add the Certificates snap-in, you'll need to click **File**, and then **Add/Remove Snap-In...** (or keyboard shortcut **Ctrl+M** would also work). **Certificates** will be an option in the left-hand pane, select it and then **Computer Account** in the pop-up window, then **Next**.</span></span>
    
3. <span data-ttu-id="41041-227">По-прежнему во всплывающем окне в все вероятность при выполнении этого компьютера, который имеет номер домашнего сертификаты, необходимые для поиска в таком выходе выбора на **локальном компьютере** Если это так.</span><span class="sxs-lookup"><span data-stu-id="41041-227">Still in the pop-up window, in all likelihood you're doing this on the computer that's home to the certificates you need to look at, so leave the selection on **Local Computer** if that's so.</span></span> <span data-ttu-id="41041-228">Если вы работаете на удаленном компьютере, измените переключатель на **Другом компьютере** и затем введите полное доменное имя компьютера или нажмите кнопку **Обзор** для поиска этим компьютером через AD.</span><span class="sxs-lookup"><span data-stu-id="41041-228">If you're working on a remote machine, change the radio button to **Another Computer** and then either enter that computer's FQDN or use the **Browse** button to search for that computer through AD.</span></span> <span data-ttu-id="41041-229">После выбора компьютера, вам потребуются нажмите кнопку **Готово** , когда все будет готово, а затем **кнопку ОК** для добавьте оснастку консоли Управления.</span><span class="sxs-lookup"><span data-stu-id="41041-229">After selecting the computer, you'll need to click **Finish** when ready, and then **OK** to add the snap-in to the MMC.</span></span>
    
4. <span data-ttu-id="41041-230">Разверните раздел **сертификаты** в левой панели консоли Управления.</span><span class="sxs-lookup"><span data-stu-id="41041-230">Expand the **Certificates** section in the MMC's left-hand pane.</span></span> <span data-ttu-id="41041-231">Разверните узел **личных** папок также и выберите **сертификаты**.</span><span class="sxs-lookup"><span data-stu-id="41041-231">Expand the **Personal** folder as well, and then select **Certificates**.</span></span> <span data-ttu-id="41041-232">Это позволяет просмотреть сертификаты в это хранилище.</span><span class="sxs-lookup"><span data-stu-id="41041-232">This lets you see the certificates in this store.</span></span>
    
5. <span data-ttu-id="41041-233">Найдите нужный сертификат, щелкните его правой кнопкой мыши и выберите пункт **Открыть**.</span><span class="sxs-lookup"><span data-stu-id="41041-233">You need to locate the certificate you want to view, right-click on it, and choose **Open**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="41041-234">Как узнать, какой сертификат, это?</span><span class="sxs-lookup"><span data-stu-id="41041-234">How do you know what certificate this is?</span></span> <span data-ttu-id="41041-235">Он должен содержать либо один сертификат, назначенных для всех компонентов фермы, или имеется несколько сертификатов для выполнения различных задач, например по умолчанию, внутренних веб-служб, и т.д., в этом случае необходимо рассмотреть несколько сертификатов.</span><span class="sxs-lookup"><span data-stu-id="41041-235">It should be either the single certificate assigned to everything for your farm, or you may have multiple certificates for different things, like Default, Internal Web Services, etc., in which case you may need to look at multiple certificates.</span></span> <span data-ttu-id="41041-236">Несколько сертификатов будут иметь одинаковые отпечаток.</span><span class="sxs-lookup"><span data-stu-id="41041-236">Multiple certificates will have the same thumbprint.</span></span> 
  
6. <span data-ttu-id="41041-p121">В представлении **Сертификат** выберите **Сведения**. В этом разделе вы сможете просмотреть имя субъекта сертификата (выберите **Subject**), назначенное имя субъекта, а также связанные свойства.</span><span class="sxs-lookup"><span data-stu-id="41041-p121">Once you've gotten to the **Certificate** view, choose **Details**. This will let you see the certificate subject name when you select **Subject**, and the assigned subject name and associated properties are shown.</span></span>
    
7. <span data-ttu-id="41041-p122">Также следует проверить записи **Альтернативное имя субъекта**. В них вы можете найти следующую информацию:</span><span class="sxs-lookup"><span data-stu-id="41041-p122">You'll also need to check the **Subject Alternate Name** entries. You'll find one or more of the following:</span></span>
    
   - <span data-ttu-id="41041-241">Имя пула для этого пула или имя отдельного сервера, если это не пул.</span><span class="sxs-lookup"><span data-stu-id="41041-241">The pool name for this pool, or the single server name if this isn't a pool.</span></span>
    
   - <span data-ttu-id="41041-242">Имя сервера, которому назначен сертификат.</span><span class="sxs-lookup"><span data-stu-id="41041-242">The server name that the certificate is assigned to.</span></span>
    
   - <span data-ttu-id="41041-243">Записи простых URL-адресов (обычно meet и dialin).</span><span class="sxs-lookup"><span data-stu-id="41041-243">Simple URL records, typically meet and dialin.</span></span>
    
   - <span data-ttu-id="41041-244">Веб-службы внутренних и веб-служб внешних имен (например, webpool01.contoso.net, webpool01.contoso.com), основанные на в построителе топологий и выборе выбранных элементов для веб-служб.</span><span class="sxs-lookup"><span data-stu-id="41041-244">Web Services internal and Web Services external names (for example, webpool01.contoso.net, webpool01.contoso.com), based on choices made in Topology Builder and over-ridden Web Services selections.</span></span>
    
   - <span data-ttu-id="41041-245">Если они уже назначены, lyncdiscover. \<sipdomain\> и lyncdiscoverinternal. \<sipdomain\> записей.</span><span class="sxs-lookup"><span data-stu-id="41041-245">If already assigned, the lyncdiscover.\<sipdomain\> and lyncdiscoverinternal.\<sipdomain\> records.</span></span>
    
    <span data-ttu-id="41041-246">Если назначено несколько сертификатов, необходимо проверить наличие множественных сертификатов (см. примечание выше).</span><span class="sxs-lookup"><span data-stu-id="41041-246">You'll need to check multiple certificates if you have more than one assigned (check the Note above).</span></span>
    
8. <span data-ttu-id="41041-247">Таким образом, если находит lyncdiscover. \<sipdomain\> и lyncdiscoverinternal. \<sipdomain\> записей, у вас это уже настроен.</span><span class="sxs-lookup"><span data-stu-id="41041-247">So, if you find lyncdiscover.\<sipdomain\> and lyncdiscoverinternal.\<sipdomain\> records, you've got this configured already.</span></span> <span data-ttu-id="41041-248">Закройте консоль MMC.</span><span class="sxs-lookup"><span data-stu-id="41041-248">You can close the MMC.</span></span>
    
9. <span data-ttu-id="41041-249">Если они не назначены, необходимо запросить новый сертификат (см. выше) или установить их после запроса (для этого рекомендуется использовать представленный выше командлет PowerShell).</span><span class="sxs-lookup"><span data-stu-id="41041-249">If they aren't assigned, you'll either need to make a new certificate request (outlined above) or you need to install them post-request (we recommend the following the PowerShell above for that).</span></span>
    
## <a name="configure-the-reverse-proxy"></a><span data-ttu-id="41041-250">Настройка обратного прокси-сервера</span><span class="sxs-lookup"><span data-stu-id="41041-250">Configure the reverse proxy</span></span>
<span data-ttu-id="41041-251"><a name="ConfigRP"> </a></span><span class="sxs-lookup"><span data-stu-id="41041-251"></span></span>

<span data-ttu-id="41041-p124">Представленные ниже шаги не обязательно выполнять в точности. Например, в предыдущих версиях продукта требовалась настройка Threat Management Gateway (TMG), поэтому если этот компонент не используется, вы можете пропустить соответствующие действия.</span><span class="sxs-lookup"><span data-stu-id="41041-p124">The steps below are not meant to be followed exactly. That's because in previous versions of the product, we'd have walked you through, for example, configuring Threat Management Gateway (TMG) and if you weren't using that, you'd need to work out your own version from there.</span></span>
  
<span data-ttu-id="41041-254">TMG больше не является, предлагаемые Майкрософт как продукт, и если по-прежнему необходимо настроить его, вы откроете [действия Lync Server 2013](https://technet.microsoft.com/en-us/library/hh690011%28v=ocs.15%29.aspx).</span><span class="sxs-lookup"><span data-stu-id="41041-254">TMG is no longer being offered by Microsoft as a product, and if you still need to configure it, you can look at the [Lync Server 2013 steps](https://technet.microsoft.com/en-us/library/hh690011%28v=ocs.15%29.aspx).</span></span> <span data-ttu-id="41041-255">Но со следующими сведениями предназначенного для формирования более полезным, даже в том случае, если нет возможности мы можем предоставить определенные шаги для каждого обратного прокси-сервера.</span><span class="sxs-lookup"><span data-stu-id="41041-255">But the following information's intended to be more generally helpful, even if there's no way we can provide specific walkthrough steps for every Reverse proxy out there.</span></span>
  
<span data-ttu-id="41041-256">Необходимо учитывать два основных момента:</span><span class="sxs-lookup"><span data-stu-id="41041-256">We have two main things to consider:</span></span>
  
- <span data-ttu-id="41041-257">Будет ли выполняться первоначальный запрос службы автообнаружения по протоколу HTTPS (рекомендуется)?</span><span class="sxs-lookup"><span data-stu-id="41041-257">Are you going to be doing your initial Autodiscover request over HTTPS (which we recommend)?</span></span>
    
  - <span data-ttu-id="41041-258">Если у вас есть правило веб-публикации, его необходимо изменить.</span><span class="sxs-lookup"><span data-stu-id="41041-258">If you have a web publishing rule, you need to modify it.</span></span>
    
  - <span data-ttu-id="41041-259">Если у вас нет правила веб-публикации, его необходимо создать.</span><span class="sxs-lookup"><span data-stu-id="41041-259">If you don't have a web publishing rule yet, you need to create it.</span></span>
    
- <span data-ttu-id="41041-260">Если первоначальный запрос службы автообнаружения выполняется по протоколу HTTP, также необходимо создать или изменить это правило.</span><span class="sxs-lookup"><span data-stu-id="41041-260">If you're doing your initial Autodiscover request over HTTP, then you'll need to create or modify that rule as well.</span></span>
    
> [!NOTE]
> <span data-ttu-id="41041-261">**Важные** Значение времени ожидания прокси-сервер — это число, которое будут зависеть от развертывания для развертывания.</span><span class="sxs-lookup"><span data-stu-id="41041-261">**Important** A Proxy time-out value is a number that will vary from deployment to deployment.</span></span> <span data-ttu-id="41041-262">Проверяйте развертывания и измените значение для обеспечения наилучшего взаимодействия для клиентов.</span><span class="sxs-lookup"><span data-stu-id="41041-262">You should monitor your deployment and modify the value for the best experience for clients.</span></span> <span data-ttu-id="41041-263">Можно задать значение как меньше 200.</span><span class="sxs-lookup"><span data-stu-id="41041-263">You may be able to set the value as low as 200.</span></span> <span data-ttu-id="41041-264">Если вы поддерживаете мобильных клиентов Lync в вашей среде, следует устанавливать значение для 960 для разрешения для времени ожидания push notification из Office 365, что значение времени ожидания 900.</span><span class="sxs-lookup"><span data-stu-id="41041-264">If you are supporting Lync mobile clients in your environment, you should set the value to 960 to allow for push notification time-outs from Office 365, which have a time-out value of 900.</span></span> <span data-ttu-id="41041-265">Скорее всего, что необходимо увеличить значение времени ожидания, чтобы избежать клиента отключается, если установлено слишком низкое значение или уменьшите значение, если подключения через прокси-сервер не отключаться, но снимите долго после отключения клиента.</span><span class="sxs-lookup"><span data-stu-id="41041-265">It is very likely that you will have to increase the time-out value to avoid client disconnects when the value is too low, or decrease the number if connections through the proxy do not disconnect but clear long after the client has disconnected.</span></span> <span data-ttu-id="41041-266">Мониторинг и определение базовых показателей обычным для вашей среды является только точных способом определения подходящей настройки для этого значения.</span><span class="sxs-lookup"><span data-stu-id="41041-266">Monitoring and baselining what is usual for your environment is the only accurate way to determine the appropriate setting for this value.</span></span>
  
### <a name="modify-the-existing-web-publishing-rule-for-your-external-autodiscover-san-and-url"></a><span data-ttu-id="41041-267">Изменение существующего правила веб-публикации для внешних альтернативного имени субъекта и URL-адреса автообнаружения</span><span class="sxs-lookup"><span data-stu-id="41041-267">Modify the existing web publishing rule for your external Autodiscover SAN and URL</span></span>

1. <span data-ttu-id="41041-268">Откройте интерфейс обратного прокси-сервера.</span><span class="sxs-lookup"><span data-stu-id="41041-268">Open your Reverse proxy interface.</span></span>
    
2. <span data-ttu-id="41041-269">Вам потребуется найдите вашей правило веб-публикации и выберите пункт Правка (возможно, в меню или вкладки, в зависимости от конфигурации обратного прокси-сервера).</span><span class="sxs-lookup"><span data-stu-id="41041-269">You'll need to locate your web publishing rule, and choose the Edit option (it may be on a menu or tab, depending on your Reverse proxy configuration).</span></span>
    
3. <span data-ttu-id="41041-270">Должен появиться о том, что это правило веб-публикации применяется к области.</span><span class="sxs-lookup"><span data-stu-id="41041-270">There should be an area that states what this web publishing rule is applied to.</span></span> <span data-ttu-id="41041-271">Вам необходимо изменить это правило для входящих сайтов или запросов сайтов.</span><span class="sxs-lookup"><span data-stu-id="41041-271">You need to modify this rule for incoming sites or requests for sites.</span></span> <span data-ttu-id="41041-272">В этом случае необходимо **добавить** новую запись.</span><span class="sxs-lookup"><span data-stu-id="41041-272">You're going to **add** a new entry.</span></span>
    
4. <span data-ttu-id="41041-273">Введите имя узла автообнаружения (пример, который будет использоваться — lyncdiscover.contoso.com) и нажмите кнопку **ОК** или **Сохранить**, в зависимости от формата обратного прокси-сервера.</span><span class="sxs-lookup"><span data-stu-id="41041-273">Type the name of your Autodiscover site (the example we'll use is lyncdiscover.contoso.com), and click **OK** or **Save**, depending on your Reverse proxy's format.</span></span>
    
5. <span data-ttu-id="41041-274">Новый сертификат, содержащую запись альтернативного имени СУБЪЕКТА автообнаружения может иметь.</span><span class="sxs-lookup"><span data-stu-id="41041-274">You may have a new certificate that has the Autodiscover SAN entry in it.</span></span> <span data-ttu-id="41041-275">Который необходимо также установить и настроить для использования в соответствии с параметрами обратного прокси-сервера.</span><span class="sxs-lookup"><span data-stu-id="41041-275">That needs to be installed as well and configured for use according to your Reverse proxy's settings.</span></span> <span data-ttu-id="41041-276">Не забудьте сохранить все, что после завершения настройки.</span><span class="sxs-lookup"><span data-stu-id="41041-276">Be sure to save everything when the configuration is completed.</span></span>
    
6. <span data-ttu-id="41041-277">Если обратный прокси-сервер имеет **проверки** возможности, затем убедитесь, использование его на все работает должным образом.</span><span class="sxs-lookup"><span data-stu-id="41041-277">If your Reverse proxy has a **Test** functionality, then please make use of it, to ensure everything's working properly.</span></span>
    
7. <span data-ttu-id="41041-278">Теперь, может потребоваться повторите эти шаги, если у вас есть директора или директора пула в вашей среде (это будет означать, у вас есть второе правило).</span><span class="sxs-lookup"><span data-stu-id="41041-278">Now, you may need to repeat these steps if you have a Director or Director pool in your environment (this would mean you have a second rule).</span></span>
    
### <a name="create-a-web-publishing-rule-for-the-external-autodiscover-url"></a><span data-ttu-id="41041-279">Создание правила веб-публикации для внешнего URL-адреса автообнаружения</span><span class="sxs-lookup"><span data-stu-id="41041-279">Create a web publishing rule for the external Autodiscover URL</span></span>

1. <span data-ttu-id="41041-280">Откройте интерфейс обратного прокси-сервера.</span><span class="sxs-lookup"><span data-stu-id="41041-280">Open your Reverse proxy interface.</span></span>
    
2. <span data-ttu-id="41041-281">Вам потребуется найдите которых в интерфейсе создания вашего правила веб-публикации и выберите пункт **New** или **Создать** (возможно, в меню или вкладки, в зависимости от конфигурации обратного прокси-сервера).</span><span class="sxs-lookup"><span data-stu-id="41041-281">You'll need to locate where in the interface you create your web publishing rules, and choose the **New** or **Create** option (it may be on a menu or tab, depending on your Reverse proxy configuration).</span></span> <span data-ttu-id="41041-282">Вы ищете параметр, чтобы создать новые правила веб-публикации.</span><span class="sxs-lookup"><span data-stu-id="41041-282">You are looking for the option to create a new web publishing rule.</span></span>
    
3. <span data-ttu-id="41041-283">Как правило, требуется ввести следующие данные:</span><span class="sxs-lookup"><span data-stu-id="41041-283">Typically, you will need to enter the following information:</span></span>
    
   - <span data-ttu-id="41041-284">**Имя** — имя правила.</span><span class="sxs-lookup"><span data-stu-id="41041-284">**Name**: the name for your rule</span></span>
    
   - <span data-ttu-id="41041-285">**Действие правила**: В этом случае правило **Разрешить** , а вы даете что-то проходить через обратный прокси-сервер.</span><span class="sxs-lookup"><span data-stu-id="41041-285">**Rule Action**: In this case it's an **Allow** rule, you're letting something pass through your Reverse proxy.</span></span>
    
   - <span data-ttu-id="41041-286">Правило **публикации** или выбираемый параметр (**отдельный веб-сайт или подсистема балансировки нагрузки**).</span><span class="sxs-lookup"><span data-stu-id="41041-286">The **Publishing** rule or option you're choosing would be **single web site or load balancer**.</span></span>
    
   - <span data-ttu-id="41041-287">Для внешнего доступа необходимо выбрать **SSL**.</span><span class="sxs-lookup"><span data-stu-id="41041-287">This needs to be **SSL** for external access, choose that option.</span></span>
    
   - <span data-ttu-id="41041-288">Вы собираетесь необходимо опубликовать путь для **Внутренней публикации**и введите полное доменное имя для внешних веб-служб на балансировки нагрузки для пула переднего плана (или полное доменное имя пула директоров балансировки нагрузки, если такой существует), пример будет sfb_ pool01.contoso.local.</span><span class="sxs-lookup"><span data-stu-id="41041-288">You're going to need to publish a path for **Internal Publishing**, and enter the FQDN for the external Web Services on your Front End pool's load balancer (or the FQDN of the Director pool's load balancer if you have one), an example would be sfb_pool01.contoso.local.</span></span>
    
   - <span data-ttu-id="41041-289">Необходимо ввести ** / ** как путь, который требуется опубликовать, но также требуется **пересылать исходный заголовок узла**.</span><span class="sxs-lookup"><span data-stu-id="41041-289">You should type **/\*** as the path to be published, but you also need to **forward the original host header**.</span></span>
    
   - <span data-ttu-id="41041-p130">Кроме того, будет представлен параметр для ввода сведений о **публикации или внешнем имени**:</span><span class="sxs-lookup"><span data-stu-id="41041-p130">There will be an option for **public or external name** details or information. This is the place where you'll be able to enter:</span></span>
    
   - <span data-ttu-id="41041-292">**Принимать запросы** (должно задаваться для доменного имени).</span><span class="sxs-lookup"><span data-stu-id="41041-292">**Accept requests**, but it should be for the domain name.</span></span>
    
   - <span data-ttu-id="41041-293">В поле **Имя** введите **lyncdiscover.**</span><span class="sxs-lookup"><span data-stu-id="41041-293">For the **Name**, you should enter **lyncdiscover.**</span></span> <span data-ttu-id="41041-294"><sipdomain>(это внешний URL-адрес службы автообнаружения).</span><span class="sxs-lookup"><span data-stu-id="41041-294"><sipdomain> (this is the external Autodiscover Service URL).</span></span> <span data-ttu-id="41041-295">Теперь при создании правила для внешних Web Services URL-адреса в пуле переднего плана, необходимо ввести полное доменное имя для внешних веб-служб в пуле переднего плана (например, lyncwebextpool01.contoso.com).</span><span class="sxs-lookup"><span data-stu-id="41041-295">Now, if you're creating a rule for the external Web Services URL on the Front End pool, you'll need to type the FQDN for the external Web Services on your Front End pool (for example, lyncwebextpool01.contoso.com).</span></span>
    
   - <span data-ttu-id="41041-296">Параметр **путь** будет и вам потребуется ввести ** / ** здесь.</span><span class="sxs-lookup"><span data-stu-id="41041-296">There will be a **Path** option, and you'll need to enter **/\*** here.</span></span>
    
   - <span data-ttu-id="41041-297">Выберите **прослушиватель SSL** с актуальным общим сертификатом.</span><span class="sxs-lookup"><span data-stu-id="41041-297">You'll need to select a **SSL Listener** with your up-to-date public certificate.</span></span>
    
   - <span data-ttu-id="41041-298">**Делегирование проверки подлинности** — выберите **Без делегирования**, но **разрешите** прямую проверку подлинности клиента.</span><span class="sxs-lookup"><span data-stu-id="41041-298">**Authentication Delegation** should be set to **No delegation**, but direct client authentication **should** be allowed.</span></span>
    
   - <span data-ttu-id="41041-299">Настройте применение правила ко **всем пользователям**.</span><span class="sxs-lookup"><span data-stu-id="41041-299">The rule should be set to **All users**.</span></span>
    
   - <span data-ttu-id="41041-300">На этом этапе должна быть введена вся необходимая информация.</span><span class="sxs-lookup"><span data-stu-id="41041-300">This should be all the information you need to create this rule and allow you to proceed.</span></span>
    
4. <span data-ttu-id="41041-301">Далее необходимо убедиться, что выполняется пересылка **исходного заголовка узла**.</span><span class="sxs-lookup"><span data-stu-id="41041-301">You're going to need to ensure that the **original host header** is forwarded.</span></span>
    
5. <span data-ttu-id="41041-302">Кроме того, требуется задать порты **веб-сервера** следующим образом:</span><span class="sxs-lookup"><span data-stu-id="41041-302">The **Web Server** ports will need to be set as well, you'll need to do the following:</span></span>
    
   - <span data-ttu-id="41041-303">**Перенаправлять запросы на HTTP-порт** — укажите порт **8080**.</span><span class="sxs-lookup"><span data-stu-id="41041-303">**Redirect requests to HTTP port** and the port number should be **8080**.</span></span>
    
   - <span data-ttu-id="41041-304">**Перенаправлять запросы на SSL-порт** — укажите порт **4443**.</span><span class="sxs-lookup"><span data-stu-id="41041-304">**Redirect requests to SSL port** and the port number should be **4443**.</span></span>
    
6. <span data-ttu-id="41041-305">По завершении настройки сохраните и примените изменения, после чего протестируйте правило.</span><span class="sxs-lookup"><span data-stu-id="41041-305">When everything's configured, you'll need to save or apply these, and then you'll want to test the rule.</span></span>
    
### <a name="create-a-web-publishing-rule-for-port-80-optional"></a><span data-ttu-id="41041-306">Создание правила веб-публикации для порта 80 (опционально)</span><span class="sxs-lookup"><span data-stu-id="41041-306">Create a web publishing rule for port 80 (Optional)</span></span>

1. <span data-ttu-id="41041-307">Откройте интерфейс обратного прокси-сервера.</span><span class="sxs-lookup"><span data-stu-id="41041-307">Open your Reverse proxy interface.</span></span>
    
2. <span data-ttu-id="41041-308">Вам потребуется найдите которых в интерфейсе создания вашего правила веб-публикации и выберите пункт **New** или **Создать** (возможно, в меню или вкладки, в зависимости от конфигурации обратного прокси-сервера).</span><span class="sxs-lookup"><span data-stu-id="41041-308">You'll need to locate where in the interface you create your web publishing rules, and choose the **New** or **Create** option (it may be on a menu or tab, depending on your Reverse proxy configuration).</span></span> <span data-ttu-id="41041-309">Вы ищете параметр, чтобы создать новые правила веб-публикации.</span><span class="sxs-lookup"><span data-stu-id="41041-309">You are looking for the option to create a new web publishing rule.</span></span>
    
3. <span data-ttu-id="41041-310">Как правило, требуется ввести следующие данные:</span><span class="sxs-lookup"><span data-stu-id="41041-310">Typically, you will need to enter the following information:</span></span>
    
   - <span data-ttu-id="41041-311">**Имя** — имя правила.</span><span class="sxs-lookup"><span data-stu-id="41041-311">**Name**: the name for your rule</span></span>
    
   - <span data-ttu-id="41041-312">**Действие правила**: В этом случае правило **Разрешить** , а вы даете что-то проходить через обратный прокси-сервер.</span><span class="sxs-lookup"><span data-stu-id="41041-312">**Rule Action**: In this case it's an **Allow** rule, you're letting something pass through your Reverse proxy.</span></span>
    
   - <span data-ttu-id="41041-313">Правило **публикации** или выбираемый параметр (**отдельный веб-сайт или подсистема балансировки нагрузки**).</span><span class="sxs-lookup"><span data-stu-id="41041-313">The **Publishing** rule or option you're choosing would be **single web site or load balancer**.</span></span>
    
   - <span data-ttu-id="41041-314">Это должно быть **незащищенное подключение к опубликованным веб-серверу или ферме**.</span><span class="sxs-lookup"><span data-stu-id="41041-314">This needs to be a **non-secured connection to connect to the published Web server or farm**.</span></span>
    
   - <span data-ttu-id="41041-315">Вы собираетесь необходимо опубликовать путь для **Внутренней публикации**и введите полное доменное имя для **виртуальный IP-адрес** балансировщика нагрузки пула переднего плана, пример бы sfb_pool01.contoso.local.</span><span class="sxs-lookup"><span data-stu-id="41041-315">You're going to need to publish a path for **Internal Publishing**, and enter the FQDN for the **VIP address** of your Front End pool's load balancer, an example would be sfb_pool01.contoso.local.</span></span>
    
   - <span data-ttu-id="41041-316">Необходимо ввести ** / ** как путь, который требуется опубликовать, но также требуется **пересылать исходный заголовок узла**.</span><span class="sxs-lookup"><span data-stu-id="41041-316">You should type **/\*** as the path to be published, but you also need to **forward the original host header**.</span></span>
    
   - <span data-ttu-id="41041-p133">Кроме того, будет представлен параметр для ввода сведений о **публикации или внешнем имени**:</span><span class="sxs-lookup"><span data-stu-id="41041-p133">There will be an option for **public or external name** details or information. This is the place where you'll be able to enter:</span></span>
    
   - <span data-ttu-id="41041-319">**Принимать запросы** (должно задаваться для доменного имени).</span><span class="sxs-lookup"><span data-stu-id="41041-319">**Accept requests**, but it should be for the domain name.</span></span>
    
   - <span data-ttu-id="41041-320">В поле **Имя** введите **lyncdiscover.**</span><span class="sxs-lookup"><span data-stu-id="41041-320">For the **Name**, you should enter **lyncdiscover.**</span></span> <span data-ttu-id="41041-321"><sipdomain>(это внешний URL-адрес службы автообнаружения).</span><span class="sxs-lookup"><span data-stu-id="41041-321"><sipdomain> (this is the external Autodiscover Service URL).</span></span>
    
   - <span data-ttu-id="41041-322">Параметр **путь** будет и вам потребуется ввести ** / ** здесь.</span><span class="sxs-lookup"><span data-stu-id="41041-322">There will be a **Path** option, and you'll need to enter **/\*** here.</span></span>
    
   - <span data-ttu-id="41041-323">Вам потребуется выбрать веб-прослушиватель или разрешить обратного прокси-сервера для его создания.</span><span class="sxs-lookup"><span data-stu-id="41041-323">You'll need to select a web listener, or allow your Reverse proxy to create one for you.</span></span>
    
   - <span data-ttu-id="41041-324">**Делегирование проверки подлинности** — выберите **Без делегирования**, но **запретите** прямую проверку подлинности клиента.</span><span class="sxs-lookup"><span data-stu-id="41041-324">**Authentication Delegation** should be set to **No delegation**, but direct client authentication **should not** be allowed.</span></span>
    
   - <span data-ttu-id="41041-325">Настройте применение правила ко **всем пользователям**.</span><span class="sxs-lookup"><span data-stu-id="41041-325">The rule should be set to **All users**.</span></span>
    
   - <span data-ttu-id="41041-326">На этом этапе должна быть введена вся необходимая информация.</span><span class="sxs-lookup"><span data-stu-id="41041-326">This should be all the information you need to create this rule and allow you to proceed.</span></span>
    
4. <span data-ttu-id="41041-327">Требуется также задать порты **веб-сервера** следующим образом:</span><span class="sxs-lookup"><span data-stu-id="41041-327">The **Web Server** ports will need to be set, you'll need to do the following:</span></span>
    
   - <span data-ttu-id="41041-328">**Перенаправлять запросы на HTTP-порт** — укажите порт **8080**.</span><span class="sxs-lookup"><span data-stu-id="41041-328">**Redirect requests to HTTP port** and the port number should be **8080**.</span></span>
    
   - <span data-ttu-id="41041-329">**Перенаправлять запросы на SSL-порт** — укажите порт **4443**.</span><span class="sxs-lookup"><span data-stu-id="41041-329">**Redirect requests to SSL port** and the port number should be **4443**.</span></span>
    
5. <span data-ttu-id="41041-330">По завершении настройки сохраните и примените изменения, после чего протестируйте правило.</span><span class="sxs-lookup"><span data-stu-id="41041-330">When everything's configured, you'll need to save or apply these, and then you'll want to test the rule.</span></span>
    
## <a name="configure-autodiscover-for-mobility-with-hybrid-deployments"></a><span data-ttu-id="41041-331">Настройка службы автообнаружения для мобильной работы с гибридными развертываниями</span><span class="sxs-lookup"><span data-stu-id="41041-331">Configure Autodiscover for Mobility with hybrid deployments</span></span>
<span data-ttu-id="41041-332"><a name="ConfigAutoD"> </a></span><span class="sxs-lookup"><span data-stu-id="41041-332"></span></span>

<span data-ttu-id="41041-333">Гибридные среды в Скайп для Business Server 2015: среды, в которых объединить локальный и O365 среды.</span><span class="sxs-lookup"><span data-stu-id="41041-333">Hybrid environments in Skype for Business Server 2015 are environments that combine an on-premises and O365 environment.</span></span> <span data-ttu-id="41041-334">При наличии Скайп для работы в гибридной среде Business Server службы автообнаружения должен иметь возможность найти пользователя с помощью одной из следующих сред.</span><span class="sxs-lookup"><span data-stu-id="41041-334">When you have Skype for Business Server working in a Hybrid environment, the Autodiscover service needs to be able to locate a user from either of these environments.</span></span>
  
<span data-ttu-id="41041-p136">Чтобы мобильный клиенты могли определять местоположение пользователя, необходимо настроить новый URL-адрес для службы автообнаружения. Для этого требуется выполнить следующие действия:</span><span class="sxs-lookup"><span data-stu-id="41041-p136">To let mobile clients discover where a user's located, the Autodiscover service needs to be configured with a new uniform resource locator (URL). The steps are:</span></span>
  
1. <span data-ttu-id="41041-337">Откройте Скайп для консоли Business Server.</span><span class="sxs-lookup"><span data-stu-id="41041-337">Open Skype for Business Server Management Shell.</span></span>
    
2. <span data-ttu-id="41041-338">Выполните следующие действия, чтобы получить значение атрибута **ProxyFQDN** для вашей Скайп среды Business Server.</span><span class="sxs-lookup"><span data-stu-id="41041-338">Run the following to get the value of the attribute **ProxyFQDN** for your Skype for Business Server environment:</span></span>
    
  ```
  Get-CsHostingProvider
  ```

3. <span data-ttu-id="41041-339">Затем, не закрывая окно оболочки, выполните следующий командлет:</span><span class="sxs-lookup"><span data-stu-id="41041-339">Then, still in the shell window, run:</span></span>
    
  ```
  Set-CsHostingProvider -Identity [identity] -AutodiscoverUrl https://webdir.online.lync.com/autodiscover/autodiscoverservice.svc/root
  ```

    <span data-ttu-id="41041-340">Где [идентификатор] заменяется именем домена общего пространства адресов SIP.</span><span class="sxs-lookup"><span data-stu-id="41041-340">Where [identity] is replaced with the domain name of the shared SIP address space.</span></span>
    
## <a name="test-your-mobility-deployment"></a><span data-ttu-id="41041-341">Тестирование развертывания мобильности</span><span class="sxs-lookup"><span data-stu-id="41041-341">Test your Mobility deployment</span></span>
<span data-ttu-id="41041-342"><a name="TestMobility"> </a></span><span class="sxs-lookup"><span data-stu-id="41041-342"></span></span>

<span data-ttu-id="41041-343">После развертывания Скайп для службы Mobility Business Server и Скайп для службы автообнаружения Business Server, может потребоваться для запуска транзакции test, чтобы убедитесь, что работа развертывания вправо.</span><span class="sxs-lookup"><span data-stu-id="41041-343">Once you've deployed Skype for Business Server Mobility Service and Skype for Business Server Autodiscover Service, you'll want to run a test transaction, to make sure your deployment's working right.</span></span> <span data-ttu-id="41041-344">Выполните команду **Test-CsUcwaConference**, чтобы проверить возможность создания конференции двумя пользователями, присоединения к ней и общения.</span><span class="sxs-lookup"><span data-stu-id="41041-344">You can run **Test-CsUcwaConference** to test the ability of two users to create, join and communicate in a conference.</span></span> <span data-ttu-id="41041-345">Для этого вам потребуются два реальных или тестовых пользователя с полными учетными данными.</span><span class="sxs-lookup"><span data-stu-id="41041-345">You will need two users (real or test) and their full credentials to do this testing.</span></span> <span data-ttu-id="41041-346">Эта команда будет работать для обоих Скайп для пользователей, а также клиенты Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="41041-346">This command will work for both Skype for Business clients as well as Lync Server 2013 clients.</span></span>
  
<span data-ttu-id="41041-347">Для клиентов Lync Server 2010 необходимо запустить **Test-CsMcxP2PIM** , чтобы протестировать.</span><span class="sxs-lookup"><span data-stu-id="41041-347">For Lync Server 2010 clients, you'll need to run **Test-CsMcxP2PIM** to test.</span></span> <span data-ttu-id="41041-348">Lync Server 2010 пользователи по-прежнему необходимо будет реальных пользователей или предварительно заданных тестовых пользователей, а вам потребуются их учетных данных пароль.</span><span class="sxs-lookup"><span data-stu-id="41041-348">Your Lync Server 2010 users will still have to be actual users, or predefined test users, and you'll need their password credentials.</span></span>
  
### <a name="test-conferencing-for-skype-for-business-and-lync-2013-mobile-clients"></a><span data-ttu-id="41041-349">Тестирование конференц-связи для мобильных клиентов Skype для бизнеса и Lync 2013</span><span class="sxs-lookup"><span data-stu-id="41041-349">Test conferencing for Skype for Business and Lync 2013 mobile clients</span></span>

1. <span data-ttu-id="41041-350">Выполните вход как член роли **CsAdministrator** на любой компьютер, где установлена **Скайп для консоли Business Server** и **Ocscore** .</span><span class="sxs-lookup"><span data-stu-id="41041-350">Log on as a member of the **CsAdministrator** role on any computer where **Skype for Business Server Management Shell** and **Ocscore** are installed.</span></span>
    
2. <span data-ttu-id="41041-351">Запустите **Скайп для консоли Business Server** (может введите имя в поле поиска или перейти на **Все программы** и выберите ее).</span><span class="sxs-lookup"><span data-stu-id="41041-351">Start the **Skype for Business Server Management Shell** (you might type the name in search or go to **All Programs** and choose it).</span></span>
    
3. <span data-ttu-id="41041-352">В командной строке введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="41041-352">At the command line, enter:</span></span>
    
   ```
   Test-CsUcwaConference -TargetFqdn <FQDN of Front End pool> -Authentication <TrustedServer | Negotiate | ClientCertificate | LiveID> -OrganizerSipAddress sip:<SIP address of test user 1> -OrganizerCredential <test user 1 credentials> -ParticipantSipAddress sip:<SIP address of test user 2> -ParticipantCredential <test user 2 credentials> -v
   ```

   <span data-ttu-id="41041-p139">Кроме того, можно задать учетные данные в скрипте и передать их в тестовый командлет (см. пример ниже).</span><span class="sxs-lookup"><span data-stu-id="41041-p139">It's also possible to set credentials in a script and pass them to the test cmdlet. We have an example of this below.</span></span>
    
   ```
   $passwd1 = ConvertTo-SecureString "Password01" -AsPlainText -Force
   $passwd2 = ConvertTo-SecureString "Password02" -AsPlainText -Force
   $testuser1 = New-Object Management.Automation.PSCredential("contoso\UserName1", $passwd1)
   $testuser2 = New-Object Management.Automation.PSCredential("contoso\UserName2", $passwd2)
   Test-CsUcwaConference -TargetFqdn pool01.contoso.com -Authentication Negotiate -OrganizerSipAddress sip:UserName1@contoso.com -OrganizerCredential $testuser1 -ParticipantSipAddress sip:UserName2@contoso.com -ParticipantCredential $testuser2 -v
   ```

### <a name="test-conferencing-for-lync-2010-mobile-clients"></a><span data-ttu-id="41041-355">Тестирование конференц-связи для мобильных клиентов Lync 2010</span><span class="sxs-lookup"><span data-stu-id="41041-355">Test conferencing for Lync 2010 mobile clients</span></span>

1. <span data-ttu-id="41041-356">Выполните вход как член роли **CsAdministrator** на любой компьютер, где установлена **Скайп для консоли Business Server** и **Ocscore** .</span><span class="sxs-lookup"><span data-stu-id="41041-356">Log on as a member of the **CsAdministrator** role on any computer where **Skype for Business Server Management Shell** and **Ocscore** are installed.</span></span>
    
2. <span data-ttu-id="41041-357">Запустите **Скайп для консоли Business Server** (может введите имя в поле поиска или перейти на **Все программы** и выберите ее).</span><span class="sxs-lookup"><span data-stu-id="41041-357">Start the **Skype for Business Server Management Shell** (you might type the name in search or go to **All Programs** and choose it).</span></span>
    
3. <span data-ttu-id="41041-358">В командной строке введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="41041-358">At the command line, enter:</span></span>
    
   ```
   Test-CsMcxP2PIM -TargetFqdn <FQDN of Front End pool> -Authentication <TrustedServer | Negotiate | ClientCertificate | LiveID> -SenderSipAddress sip:<SIP address of test user 1> -SenderCredential <test user 1 credentials> -ReceiverSipAddress sip:<SIP address of test user 2> -ReceiverCredential <test user 2 credentials> -v
   ```

   <span data-ttu-id="41041-p140">Кроме того, можно задать учетные данные в скрипте и передать их в тестовый командлет (см. пример ниже).</span><span class="sxs-lookup"><span data-stu-id="41041-p140">It's also possible to set credentials in a script and pass them to the test cmdlet. We have an example of this below.</span></span>
    
  ```
  $passwd1 = ConvertTo-SecureString "Password01" -AsPlainText -Force
  $passwd2 = ConvertTo-SecureString "Password02" -AsPlainText -Force
  $tuc1 = New-Object Management.Automation.PSCredential("contoso\UserName1", $passwd1)
  $tuc2 = New-Object Management.Automation.PSCredential("contoso\UserName2", $passwd2)
  Test-CsMcxP2PIM -TargetFqdn pool01.contoso.com -Authentication Negotiate -SenderSipAddress sip:UserName1@contoso.com -SenderCredential $tuc1 -ReceiverSipAddress sip:UserName2@contoso.com -ReceiverCredential $tuc2 -v
  ```

<span data-ttu-id="41041-361">Для просмотра процедур команду более того, можно извлечь [Test-CsUcwaConference](https://docs.microsoft.com/powershell/module/skype/test-csucwaconference?view=skype-ps) и [Test-CsMcxP2PIM](https://docs.microsoft.com/powershell/module/skype/test-csmcxp2pim?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="41041-361">To review the command procedures further, you can check out [Test-CsUcwaConference](https://docs.microsoft.com/powershell/module/skype/test-csucwaconference?view=skype-ps) and [Test-CsMcxP2PIM](https://docs.microsoft.com/powershell/module/skype/test-csmcxp2pim?view=skype-ps).</span></span>
  
## <a name="configure-for-push-notifications"></a><span data-ttu-id="41041-362">Настройка для использования push-уведомлений</span><span class="sxs-lookup"><span data-stu-id="41041-362">Configure for push notifications</span></span>
<span data-ttu-id="41041-363"><a name="ConfigPush"> </a></span><span class="sxs-lookup"><span data-stu-id="41041-363"></span></span>

<span data-ttu-id="41041-364">Push-уведомлений, в виде значки, значки или оповещения, можно отправить на мобильное устройство, даже в том случае, если приложение Скайп или Lync неактивна.</span><span class="sxs-lookup"><span data-stu-id="41041-364">Push notifications, in the form of badges, icons, or alerts, can be sent to a mobile device even when the Skype or Lync app is inactive.</span></span> <span data-ttu-id="41041-365">Но что такое pusn уведомления?</span><span class="sxs-lookup"><span data-stu-id="41041-365">But what are pusn notifications?</span></span> <span data-ttu-id="41041-366">Это событие предупреждения, как приглашения на новый или пропущенных обмена мгновенными Сообщениями или для полученной голосовой почты.</span><span class="sxs-lookup"><span data-stu-id="41041-366">They are event alerts, like a new or missed IM invitation, or for a received voicemail.</span></span> <span data-ttu-id="41041-367">Скайп для службы Business Server 2015 Mobility отправляет такие уведомления Скайп облачной для Business Server службы Push-уведомлений, который отправляет уведомления для Microsoft Push-уведомлений службы (MSNS) для пользователей Windows Phone.</span><span class="sxs-lookup"><span data-stu-id="41041-367">The Skype for Business Server 2015 Mobility service sends these notifications to the cloud-based Skype for Business Server Push Notification Service, which then sends the notifications to the Microsoft Push Notification Service (MSNS) for Windows Phone users.</span></span>
  
<span data-ttu-id="41041-368">Данная функциональная возможность не изменяется с Lync Server 2013, но при наличии Скайп для Business Server, необходимо выполнить следующие:</span><span class="sxs-lookup"><span data-stu-id="41041-368">This functionality is unchanged from Lync Server 2013, but if you have a Skype for Business Server, you'll want to do the following:</span></span>
  
- <span data-ttu-id="41041-369">Для Скайп для пограничного сервера Business Server 2015 добавить нового поставщика услуг размещения Скайп Майкрософт для бизнеса в Интернет и затем настроить федерацию между вашей организацией и Скайп для бизнеса в Интернет для поставщиков услуг размещения.</span><span class="sxs-lookup"><span data-stu-id="41041-369">For a Skype for Business Server 2015 Edge Server, add a new hosting provider, Microsoft Skype for Business Online, and then set up hosting provider federation between your organization and Skype for Business Online.</span></span>
    
- <span data-ttu-id="41041-p142">Включите push-уведомления с помощью командлета **Set-CsPushNotificationConfiguration**. По умолчанию push-уведомления отключены.</span><span class="sxs-lookup"><span data-stu-id="41041-p142">Enable push notifications by running the **Set-CsPushNotificationConfiguration** cmdlet. By default, push notifications are turned off.</span></span>
    
- <span data-ttu-id="41041-372">Протестируйте конфигурацию федерации и push-уведомлений.</span><span class="sxs-lookup"><span data-stu-id="41041-372">Test your federation configuration and push notifications.</span></span>
    
### <a name="configure-your-skype-for-business-edge-server-for-push-notifications"></a><span data-ttu-id="41041-373">Настройка пограничного сервера Skype для бизнеса для использования push-уведомлений</span><span class="sxs-lookup"><span data-stu-id="41041-373">Configure your Skype for Business Edge Server for push notifications</span></span>

1. <span data-ttu-id="41041-374">Выполните вход, если учетная запись не должна быть членом роли **CsAdministrator** на компьютер, где установлены **Скайп для консоли Business Server** и **Ocscore** .</span><span class="sxs-lookup"><span data-stu-id="41041-374">Log on, with an account that's a member of the **CsAdministrator** role, to a computer where **Skype for Business Server Management Shell** and **Ocscore** are installed.</span></span>
    
2. <span data-ttu-id="41041-375">Запустите **Скайп для консоли Business Server**.</span><span class="sxs-lookup"><span data-stu-id="41041-375">Start the **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="41041-376">Добавление Скайп для сети поставщика услуг размещения Business Server.</span><span class="sxs-lookup"><span data-stu-id="41041-376">Add a Skype for Business Server online hosting provider.</span></span>
    
   ```
   New-CsHostingProvider -Identity <unique identifier for hosting provider> -Enabled $True -ProxyFQDN <FQDN for the Access Server used by the hosting provider> -VerificationLevel UseSourceVerification
   ```

   <span data-ttu-id="41041-377">Пример:</span><span class="sxs-lookup"><span data-stu-id="41041-377">As an example:</span></span>
    
   ```
   New-CsHostingProvider -Identity "SkypeOnline" -Enabled $True -ProxyFQDN "sipfed.online.lync.com" -VerificationLevel UseSourceVerification
   ```

    > [!NOTE]
    > <span data-ttu-id="41041-p143">Нельзя настраивать несколько отношений федерации с одним поставщиком услуг размещения. То есть, настроив поставщик услуг размещения, имеющий отношения федерации с sipfed.online.lync.com, не добавляйте для этого сайта другой поставщик услуг размещения, даже если удостоверение поставщика отличается от SkypeOnline.</span><span class="sxs-lookup"><span data-stu-id="41041-p143">You can't have more than one federation relationship with a single hosting provider. So, if you've already set up a hosting provider that has a federation relationship with sipfed.online.lync.com, don't add another hosting provider for it, even if the identity of the hosting provider is something other than SkypeOnline.</span></span> 
  
4. <span data-ttu-id="41041-380">Настройте федерацию поставщика услуг размещения между вашей организацией и службы Push-уведомлений в Скайп для бизнеса в Интернет.</span><span class="sxs-lookup"><span data-stu-id="41041-380">Set up the hosting provider federation between your organization and the Push Notification Service at Skype for Business Online.</span></span> <span data-ttu-id="41041-381">В командной строке введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="41041-381">At the command line, you'll need to type:</span></span>
    
   ```
    New-CsAllowedDomain -Identity "push.lync.com"
   ```

### <a name="enable-push-notifications"></a><span data-ttu-id="41041-382">Включение push-уведомлений</span><span class="sxs-lookup"><span data-stu-id="41041-382">Enable push notifications</span></span>

1. <span data-ttu-id="41041-383">Выполните вход, если учетная запись не должна быть членом роли **CsAdministrator** на компьютер, где установлены **Скайп для консоли Business Server** и **Ocscore** .</span><span class="sxs-lookup"><span data-stu-id="41041-383">Log on, with an account that's a member of the **CsAdministrator** role, to a computer where **Skype for Business Server Management Shell** and **Ocscore** are installed.</span></span>
    
2. <span data-ttu-id="41041-384">Запустите **Скайп для консоли Business Server**.</span><span class="sxs-lookup"><span data-stu-id="41041-384">Start the **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="41041-385">Включите push-уведомления:</span><span class="sxs-lookup"><span data-stu-id="41041-385">Enable push notifications:</span></span>
    
   ```
   Set-CsPushNotificationConfiguration -EnableMicrosoftPushNotificationService $True
   ```

4. <span data-ttu-id="41041-386">Включите федерацию:</span><span class="sxs-lookup"><span data-stu-id="41041-386">Enable Federation:</span></span>
     
   ```
   Set-CsAccessEdgeConfiguration -AllowFederatedUsers $True
   ```

### <a name="test-federation-and-push-notifications"></a><span data-ttu-id="41041-387">Тестирование федерации и push-уведомлений</span><span class="sxs-lookup"><span data-stu-id="41041-387">Test federation and push notifications</span></span>

1. <span data-ttu-id="41041-388">Выполните вход, если учетная запись не должна быть членом роли **CsAdministrator** на компьютер, где установлены **Скайп для консоли Business Server** и **Ocscore** .</span><span class="sxs-lookup"><span data-stu-id="41041-388">Log on, with an account that's a member of the **CsAdministrator** role, to a computer where **Skype for Business Server Management Shell** and **Ocscore** are installed.</span></span>
    
2. <span data-ttu-id="41041-389">Запустите **Скайп для консоли Business Server**.</span><span class="sxs-lookup"><span data-stu-id="41041-389">Start the **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="41041-390">Проверьте конфигурацию федерации:</span><span class="sxs-lookup"><span data-stu-id="41041-390">Test the federation configuration:</span></span>
    
   ```
   Test-CsFederatedPartner -TargetFqdn <FQDN of Access Edge server used for federated SIP traffic> -Domain <FQDN of federated domain> -ProxyFqdn <FQDN of the Access Edge server used by the federated organization>
   ```

    <span data-ttu-id="41041-391">Пример:</span><span class="sxs-lookup"><span data-stu-id="41041-391">As an example:</span></span>
    
   ```
   Test-CsFederatedPartner -TargetFqdn accessproxy.contoso.com -Domain push.lync.com -ProxyFqdn sipfed.online.lync.com
   ```

4. <span data-ttu-id="41041-392">Протестируйте push-уведомления:</span><span class="sxs-lookup"><span data-stu-id="41041-392">Test your push notifications:</span></span>
    
   ```
   Test-CsMcxPushNotification -AccessEdgeFqdn <Access Edge service FQDN>
   ```

    <span data-ttu-id="41041-393">Пример:</span><span class="sxs-lookup"><span data-stu-id="41041-393">As an example:</span></span>
    
   ```
   Test-CsMcxPushNotification -AccessEdgeFqdn accessproxy.contoso.com
   ```

## <a name="configure-mobility-policy"></a><span data-ttu-id="41041-394">Настройка политики мобильности</span><span class="sxs-lookup"><span data-stu-id="41041-394">Configure Mobility policy</span></span>
<span data-ttu-id="41041-395"><a name="ConfigMob"> </a></span><span class="sxs-lookup"><span data-stu-id="41041-395"></span></span>

<span data-ttu-id="41041-396">У вас есть возможность с Скайп 2015 Business Server для определения пользователей, которые можно использовать Mobility service, звонок через работу, передачи голоса по протоколу IP (VoIP), или видео, также будут ли WiFi необходимые для VoIP или видео.</span><span class="sxs-lookup"><span data-stu-id="41041-396">You have the ability with Skype for Business Server 2015 to determine who can use your Mobility service, Call via Work, voice over IP (VoIP), or video, as well as whether WiFi will be required for VoIP or video.</span></span> <span data-ttu-id="41041-397">Позвонить с рабочего позволяет мобильных пользователей используйте свой номер рабочего телефона вместо их номер мобильного телефона, когда для выполнения и приема звонков.</span><span class="sxs-lookup"><span data-stu-id="41041-397">Call via Work lets a mobile user use their work phone number, instead of their mobile phone number, when placing and receiving calls.</span></span> <span data-ttu-id="41041-398">Лицо на других конца строки не будут отображаться номер мобильного телефона, мобильных пользователей и позволяет избежать исходящих расходов на проведение конференций мобильных устройств пользователя.</span><span class="sxs-lookup"><span data-stu-id="41041-398">The person on the other end of the line won't see that mobile user's cell phone number, and it lets that mobile user avoid outgoing call charges.</span></span> <span data-ttu-id="41041-399">Когда VoIP и видео Настройка, пользователи могут занять и звонки по протоколу VoIP и видео.</span><span class="sxs-lookup"><span data-stu-id="41041-399">When VoIP and video are set up, users can take and make VoIP calls and video.</span></span> <span data-ttu-id="41041-400">Параметры для использования WiFi определение ли мобильное устройство пользователя должны использовать WiFi сети сотовой сети.</span><span class="sxs-lookup"><span data-stu-id="41041-400">The settings for WiFi usage determine whether a user's mobile device will be required to use a WiFi network over a cellular data network.</span></span>
  
<span data-ttu-id="41041-401">Мобильность, позвонить с рабочего, VoIP и функции видео включены по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="41041-401">Mobility, Call via Work, and the VoIP and video features are all enabled by default.</span></span> <span data-ttu-id="41041-402">Параметры запроса на использование сети Wi-Fi для протокола VoIP и видеосвязи отключены.</span><span class="sxs-lookup"><span data-stu-id="41041-402">The setting to require WiFi for VoIP and video are disabled.</span></span> <span data-ttu-id="41041-403">Администратор может изменять эти настройки глобально, а также на уровне сайта или пользователя.</span><span class="sxs-lookup"><span data-stu-id="41041-403">An Admin has the ability to change this, either globally, by site, or by user.</span></span>
  
<span data-ttu-id="41041-404">Должны иметь возможность использовать функции мобильности и вызов с рабочего, пользователи должны быть:</span><span class="sxs-lookup"><span data-stu-id="41041-404">To be able to use Mobility features and Call via Work, users need to be:</span></span>
  
- <span data-ttu-id="41041-405">Включена поддержка Скайп для Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="41041-405">Enabled for Skype for Business Server 2015</span></span>
    
- <span data-ttu-id="41041-406">Активированы для корпоративной голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="41041-406">Enabled for Enterprise Voice.</span></span>
    
- <span data-ttu-id="41041-407">Назначить политику мобильности, которая имеет значение **True**для параметра **EnableMobility** .</span><span class="sxs-lookup"><span data-stu-id="41041-407">Assigned a Mobility policy that has the **EnableMobility** option set to **True**.</span></span>
    
<span data-ttu-id="41041-408">Чтобы использовать функцию "Позвонить с рабочего", пользователи должны отвечать следующим требованиям:</span><span class="sxs-lookup"><span data-stu-id="41041-408">For users to be able to use Call via Work, they'll also need to be:</span></span>
  
- <span data-ttu-id="41041-409">Иметь назначенную политику голосовой связи с выбранной функцией  **Разрешить одновременный звонок на несколько телефонов**.</span><span class="sxs-lookup"><span data-stu-id="41041-409">Assigned a voice policy that has the **Enable simultaneous ringing of phones** option selected.</span></span>
    
- <span data-ttu-id="41041-410">Назначить политику мобильности с **EnableOutsideVoice** присвоено **значение True**.</span><span class="sxs-lookup"><span data-stu-id="41041-410">Assigned a Mobility policy that has the **EnableOutsideVoice** set to **True**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="41041-p147">Пользователи, для которых не включена поддержка системы корпоративной голосовой связи, могут использовать мобильные устройства для выполнения звонков Skype–Skype по протоколу VoIP или могут присоединиться к конференциям с помощью ссылки "Щелкните для присоединения" на мобильном устройстве, если вы назначили этим пользователям соответствующие возможности в политике голосовой связи. Дополнительные сведения см. в разделе "Планирование".</span><span class="sxs-lookup"><span data-stu-id="41041-p147">Users who aren't enabled for Enterprise Voice can use their mobile devices to make Skype to Skype VoIP calls or can join conferences by using the Click to Join link while on their mobile devices, if the appropriate options are set for the Voice policy they're associated with. There's more detail in the PLANNING topic.</span></span> 
  
### <a name="modify-global-mobility-policy"></a><span data-ttu-id="41041-413">Изменение глобальной политики мобильности</span><span class="sxs-lookup"><span data-stu-id="41041-413">Modify global Mobility policy</span></span>

1. <span data-ttu-id="41041-414">Выполните вход, если учетная запись не должна быть членом роли **CsAdministrator** на компьютер, где установлены **Скайп для консоли Business Server** и **Ocscore** .</span><span class="sxs-lookup"><span data-stu-id="41041-414">Log on, with an account that's a member of the **CsAdministrator** role, to a computer where **Skype for Business Server Management Shell** and **Ocscore** are installed.</span></span>
    
2. <span data-ttu-id="41041-415">Запустите **Скайп для консоли Business Server**.</span><span class="sxs-lookup"><span data-stu-id="41041-415">Start the **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="41041-416">Глобально отключение доступа для мобильных устройств и позвонить с рабочего с помощью следующей команды:</span><span class="sxs-lookup"><span data-stu-id="41041-416">Turn off access to Mobility and Call via Work globally by typing:</span></span>
    
   ```
   Set-CsMobilityPolicy -EnableMobility $False -EnableOutsideVoice $False
   ```

    > [!NOTE]
    > <span data-ttu-id="41041-417">Можно отключить позвонить с рабочего без отключения доступа для мобильных устройств.</span><span class="sxs-lookup"><span data-stu-id="41041-417">You can turn off Call via Work without turning off access to Mobility.</span></span> <span data-ttu-id="41041-418">Однако нельзя отключить мобильности без также отключение позвонить с рабочего.</span><span class="sxs-lookup"><span data-stu-id="41041-418">But you can't turn off Mobility without also turning off Call via Work.</span></span> 
  
    <span data-ttu-id="41041-419">Дополнительные сведения о Извлеките [Set-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/set-csmobilitypolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="41041-419">For more info, check out [Set-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/set-csmobilitypolicy?view=skype-ps).</span></span>
    
### <a name="modify-mobility-policy-by-site"></a><span data-ttu-id="41041-420">Изменение мобильной политики на сайт</span><span class="sxs-lookup"><span data-stu-id="41041-420">Modify Mobility policy by site</span></span>

1. <span data-ttu-id="41041-421">Выполните вход, если учетная запись не должна быть членом роли **CsAdministrator** на компьютер, где установлены **Скайп для консоли Business Server** и **Ocscore** .</span><span class="sxs-lookup"><span data-stu-id="41041-421">Log on, with an account that's a member of the **CsAdministrator** role, to a computer where **Skype for Business Server Management Shell** and **Ocscore** are installed.</span></span>
    
2. <span data-ttu-id="41041-422">Запустите **Скайп для консоли Business Server**.</span><span class="sxs-lookup"><span data-stu-id="41041-422">Start the **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="41041-p149">В можете создать политику на уровне сайта, отключить VoIP и видеосвязь и включить параметр "Запрашивать Wi-Fi для IP-аудио/видео" для отдельных сайтов. Для этого введите:</span><span class="sxs-lookup"><span data-stu-id="41041-p149">You can create a site-level policy, turn off VoIP and video, enable Require WiFi for IP Audio, and Require WiFi for IP Video by site. Type:</span></span>
    
   ```
   New-CsMobilityPolicy -Identity site:<site identifier> -EnableIPAudioVideo $false -RequireWiFiForIPAudio $True -RequireWiFiforIPVideo $True
   ```

    <span data-ttu-id="41041-425">Дополнительные [New-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/new-csmobilitypolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="41041-425">Learn more at [New-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/new-csmobilitypolicy?view=skype-ps).</span></span>
    
### <a name="modify-mobility-policy-by-user"></a><span data-ttu-id="41041-426">Изменение мобильной политики на пользователя</span><span class="sxs-lookup"><span data-stu-id="41041-426">Modify Mobility policy by user</span></span>

1. <span data-ttu-id="41041-427">Выполните вход, если учетная запись не должна быть членом роли **CsAdministrator** на компьютер, где установлены **Скайп для консоли Business Server** и **Ocscore** .</span><span class="sxs-lookup"><span data-stu-id="41041-427">Log on, with an account that's a member of the **CsAdministrator** role, to a computer where **Skype for Business Server Management Shell** and **Ocscore** are installed.</span></span>
    
2. <span data-ttu-id="41041-428">Запустите **Скайп для консоли Business Server**.</span><span class="sxs-lookup"><span data-stu-id="41041-428">Start the **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="41041-429">Создание политики мобильности на уровне пользователя и отключить мобильности и вызов с рабочего пользователем.</span><span class="sxs-lookup"><span data-stu-id="41041-429">Create user level Mobility policies and turn off Mobility and Call via Work by user.</span></span> <span data-ttu-id="41041-430">Для этого введите:</span><span class="sxs-lookup"><span data-stu-id="41041-430">Type:</span></span>
    
   ```
   New-CsMobilityPolicy -Identity <policy name> -EnableMobility $False -EnableOutsideVoice $False
   Grant-CsMobilityPolicy -Identity <user identifier> -PolicyName <policy name>
   ```

    <span data-ttu-id="41041-431">Дополнительный пример (используется образец данных):</span><span class="sxs-lookup"><span data-stu-id="41041-431">A further example with sample data:</span></span>
    
   ```
   New-CsMobilityPolicy "tag:disableOutsideVoice" -EnableOutsideVoice $False
   Grant-CsMobilityPolicy -Identity MobileUser1@contoso.com -PolicyName tag:disableOutsideVoice
   ```

    > [!NOTE]
    > <span data-ttu-id="41041-432">Можно отключить позвонить с рабочего без отключения доступа для мобильных устройств.</span><span class="sxs-lookup"><span data-stu-id="41041-432">You can turn off Call via Work without turning off access to Mobility.</span></span> <span data-ttu-id="41041-433">Однако нельзя отключить мобильности без также отключение позвонить с рабочего.</span><span class="sxs-lookup"><span data-stu-id="41041-433">But you can't turn off Mobility without also turning off Call via Work.</span></span> 
  

