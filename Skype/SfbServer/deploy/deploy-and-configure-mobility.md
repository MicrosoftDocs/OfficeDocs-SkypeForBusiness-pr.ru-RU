---
title: Развертывание и Настройка мобильных устройств для Скайп для Business Server
ms.author: heidip
author: microsoftheidi
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8ec6197a-3d1e-4b42-9465-564044cdab1a
description: В этой статье поможет выполнить действия, чтобы настроить существующий Скайп для установки Business Server для использования службы мобильности, позволяя мобильными устройствами должны иметь возможность использовать преимущества Скайп для функций мобильной работы Business Server.
ms.openlocfilehash: e1799459d2e7723298aa7fdda17f89a9041efd15
ms.sourcegitcommit: e93b12f5ebaad1140d7df798b5e0647197b9213d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2018
ms.locfileid: "26649717"
---
# <a name="deploy-and-configure-mobility-for-skype-for-business-server"></a><span data-ttu-id="b7686-103">Развертывание и Настройка мобильных устройств для Скайп для Business Server</span><span class="sxs-lookup"><span data-stu-id="b7686-103">Deploy and Configure Mobility for Skype for Business Server</span></span>  
 
<span data-ttu-id="b7686-104">В этой статье поможет выполнить действия, чтобы настроить существующий Скайп для установки Business Server для использования службы мобильности, позволяя мобильными устройствами должны иметь возможность использовать преимущества Скайп для функций мобильной работы Business Server.</span><span class="sxs-lookup"><span data-stu-id="b7686-104">This article will walk you through the steps to configure an existing Skype for Business Server installation to use the Mobility service, allowing your mobile devices to be able to take advantage of Skype for Business Server Mobility features.</span></span>
  
<span data-ttu-id="b7686-105">Просмотра статьи [Планирование для мобильных устройств для Скайп для Business Server](../plan-your-deployment/mobility.md) , можно для перехода с указанные ниже действия для развертывания мобильности в вашей Скайп среды Business Server.</span><span class="sxs-lookup"><span data-stu-id="b7686-105">Having reviewed the [Plan for Mobility for Skype for Business Server](../plan-your-deployment/mobility.md) article, you should be ready to proceed with the steps below to deploy Mobility into your Skype for Business Server environment.</span></span> <span data-ttu-id="b7686-106">Ниже перечислены шаги (, мы в случае включительно, в этой таблице список разрешений):</span><span class="sxs-lookup"><span data-stu-id="b7686-106">The steps are as follows (and we're including in this table a permissions list):</span></span>
  
|<span data-ttu-id="b7686-107">**Этап**</span><span class="sxs-lookup"><span data-stu-id="b7686-107">**Phase**</span></span>|<span data-ttu-id="b7686-108">**Разрешения**</span><span class="sxs-lookup"><span data-stu-id="b7686-108">**Permissions**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="b7686-109">Создание записей DNS</span><span class="sxs-lookup"><span data-stu-id="b7686-109">Create DNS records</span></span>](deploy-and-configure-mobility.md#CreateDNSRec) <br/> |<span data-ttu-id="b7686-110">Администраторы домена</span><span class="sxs-lookup"><span data-stu-id="b7686-110">Domain Admins</span></span>  <br/> <span data-ttu-id="b7686-111">DNSAdmins</span><span class="sxs-lookup"><span data-stu-id="b7686-111">DNSAdmins</span></span>  <br/> |
|[<span data-ttu-id="b7686-112">Изменение сертификатов</span><span class="sxs-lookup"><span data-stu-id="b7686-112">Modify certificates</span></span>](deploy-and-configure-mobility.md#ModCerts) <br/> |<span data-ttu-id="b7686-113">Локальный администратор</span><span class="sxs-lookup"><span data-stu-id="b7686-113">Local Administrator</span></span>  <br/> |
|[<span data-ttu-id="b7686-114">Настройка обратного прокси-сервера</span><span class="sxs-lookup"><span data-stu-id="b7686-114">Configure the reverse proxy</span></span>](deploy-and-configure-mobility.md#ConfigRP) <br/> |<span data-ttu-id="b7686-115">Локальный администратор</span><span class="sxs-lookup"><span data-stu-id="b7686-115">Local Administrator</span></span>  <br/> |
|[<span data-ttu-id="b7686-116">Настройка службы автообнаружения для мобильной работы с гибридными развертываниями</span><span class="sxs-lookup"><span data-stu-id="b7686-116">Configure Autodiscover for Mobility with hybrid deployments</span></span>](deploy-and-configure-mobility.md#ConfigAutoD) <br/> |<span data-ttu-id="b7686-117">Администраторы домена</span><span class="sxs-lookup"><span data-stu-id="b7686-117">Domain Admins</span></span>  <br/> |
|[<span data-ttu-id="b7686-118">Тестирование развертывания мобильности</span><span class="sxs-lookup"><span data-stu-id="b7686-118">Test your Mobility deployment</span></span>](deploy-and-configure-mobility.md#TestMobility) <br/> |<span data-ttu-id="b7686-119">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="b7686-119">CsAdministrator</span></span>  <br/> |
|[<span data-ttu-id="b7686-120">Настройка для использования push-уведомлений</span><span class="sxs-lookup"><span data-stu-id="b7686-120">Configure for push notifications</span></span>](deploy-and-configure-mobility.md#ConfigPush) <br/> |<span data-ttu-id="b7686-121">RtcUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="b7686-121">RtcUniversalServerAdmins</span></span>  <br/> |
|[<span data-ttu-id="b7686-122">Настройка политики мобильности</span><span class="sxs-lookup"><span data-stu-id="b7686-122">Configure Mobility policy</span></span>](deploy-and-configure-mobility.md#ConfigMob) <br/> |<span data-ttu-id="b7686-123">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="b7686-123">CsAdministrator</span></span>  <br/> |
   
<span data-ttu-id="b7686-p102">Перед выполнением действий, описываемых в следующих разделах, необходимо ознакомиться с разделом, посвященным планированию. Если у вас возникают какие-либо вопросы, обращайтесь к этому разделу.</span><span class="sxs-lookup"><span data-stu-id="b7686-p102">All the following sections contain steps that assume you've read the Planning topic. If anything's confusing you, feel free to check out the information there.</span></span>

> [!NOTE]
> <span data-ttu-id="b7686-126">Поддержка устаревших мобильных клиентов MCX (Mobility Service) больше не доступен в Скайп для Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="b7686-126">MCX (Mobility Service) support for legacy mobile clients is no longer available in Skype for Business Server 2019.</span></span> <span data-ttu-id="b7686-127">Все текущей Скайп для мобильных клиентов Business уже используете Unified Communications Web API (UCWA) для поддержки мгновенного обмена Мгновенными сообщениями, сведения о присутствии и контакты.</span><span class="sxs-lookup"><span data-stu-id="b7686-127">All current Skype for Business mobile clients already use Unified Communications Web API (UCWA) to support instant messaging (IM), presence, and contacts.</span></span> <span data-ttu-id="b7686-128">Пользователи с прежних версий клиентов, использующих MCX потребуется обновить до текущего клиента.</span><span class="sxs-lookup"><span data-stu-id="b7686-128">Users with legacy clients using MCX will need to upgrade to a current client.</span></span>
  
## <a name="create-dns-records"></a><span data-ttu-id="b7686-129">Создание записей DNS</span><span class="sxs-lookup"><span data-stu-id="b7686-129">Create DNS records</span></span>
<span data-ttu-id="b7686-130"><a name="CreateDNSRec"> </a></span><span class="sxs-lookup"><span data-stu-id="b7686-130"></span></span>

<span data-ttu-id="b7686-131">Уже может быть их как часть вашего Скайп для среды Business Server, но необходимо создать следующие записи для автоматического обнаружения для работы:</span><span class="sxs-lookup"><span data-stu-id="b7686-131">You may already have these as part of your Skype for Business Server environment, but you do need to create the following records for Autodiscovery to work:</span></span>
  
- <span data-ttu-id="b7686-132">Внутренняя DNS-запись для поддержки мобильных пользователей, которые подключаются изнутри сети организации</span><span class="sxs-lookup"><span data-stu-id="b7686-132">An internal DNS record to support mobile users who're connecting from within your organization's network.</span></span>
    
- <span data-ttu-id="b7686-133">Внутренняя DNS-запись для поддержки мобильных пользователей, которые подключаются из-за пределов сети организации</span><span class="sxs-lookup"><span data-stu-id="b7686-133">An external (or public) DNS record to support mobile users who're connecting from outside your organization's network.</span></span>
    
<span data-ttu-id="b7686-134">Это могут быть записи имен A (узел) или CNAME. Обратите внимание, что создавать записи обоих типов не обязательно, поскольку в этой статье описываются все возможные варианты действий.</span><span class="sxs-lookup"><span data-stu-id="b7686-134">These records can be either A (host) names or CNAME records (you don't have to make both, we're just including the steps for everything here).</span></span>
  
### <a name="create-an-internal-dns-cname-record"></a><span data-ttu-id="b7686-135">Создание внутренней DNS-записи CNAME</span><span class="sxs-lookup"><span data-stu-id="b7686-135">Create an internal DNS CNAME record</span></span>

1. <span data-ttu-id="b7686-136">Войдите в систему DNS-сервера в сети, который входит в группу **Администраторы домена** или **DnsAdmins**.</span><span class="sxs-lookup"><span data-stu-id="b7686-136">Log into a DNS server in your network that's either a member of the **Domain Admins** group or the **DnsAdmins** group.</span></span>
    
2. <span data-ttu-id="b7686-137">Нажмите кнопку **Пуск** и выберите **Администрирование**. Если этот компонент отсутствует в меню "Пуск", воспользуйтесь полем **Поиск**. Затем щелкните **DNS**, чтобы открыть административную оснастку DNS.</span><span class="sxs-lookup"><span data-stu-id="b7686-137">Click **Start**, Choose **Administrative Tools** (you may need to **Search** for it if it's not an option off the Start menu), and then click **DNS** to open the DNS administrative snap-in.</span></span>
    
3. <span data-ttu-id="b7686-138">В левой панели окна консоли, вам потребуется перейти к домену на номер домашнего для вашей Скайп для серверов переднего плана Business Server и разверните узел **Зоны прямого просмотра** существует.</span><span class="sxs-lookup"><span data-stu-id="b7686-138">In the left-hand pane of the console window, you'll need to go to the domain that's home to your Skype for Business Server's Front End Servers, and expand the **Forward Lookup Zones** there.</span></span>
    
4. <span data-ttu-id="b7686-139">Проверьте, какие из следующих записей присутствуют в этом узле:</span><span class="sxs-lookup"><span data-stu-id="b7686-139">Take a moment to see which of the following you have:</span></span>
    
   - <span data-ttu-id="b7686-140">Любой A или AAAA записи узлов для сервера переднего плана (Standard или Enterprise) или pool(s) переднего плана.</span><span class="sxs-lookup"><span data-stu-id="b7686-140">Any host A or AAAA records for your Front End Server (Standard or Enterprise) or Front End pool(s).</span></span>
    
   - <span data-ttu-id="b7686-141">Любой узел A или AAAA записи для директора или директора пула (необязательные конфигурация которые могут возникнуть в вашем развертывании).</span><span class="sxs-lookup"><span data-stu-id="b7686-141">Any host A or AAAA records for a Director or Director pool (an optional configuration you may have in your deployment).</span></span>
    
5. <span data-ttu-id="b7686-142">После этого щелкните правой кнопкой мыши имя домена SIP и выберите в меню пункт **Создать псевдоним (CNAME)**.</span><span class="sxs-lookup"><span data-stu-id="b7686-142">Once you've noted this, right-click your SIP domain name, and then choose **New Alias (CNAME)** from the menu.</span></span>
    
6. <span data-ttu-id="b7686-143">В текстовое поле **Имя псевдонима** введите lyncdiscoverinternal в качестве имени узла для URL-адреса внутренней службы автообнаружения.</span><span class="sxs-lookup"><span data-stu-id="b7686-143">In the **Alias name** textbox, type lyncdiscoverinternal for your host name, for the internal Autodiscover service URL.</span></span>
    
7. <span data-ttu-id="b7686-144">В **полное доменное имя (полное доменное имя для целевого узла**, вам потребуется введите или укажите внутренний Web Services полное доменное имя для переднего плана пула (или один сервер переднего плана, или пул директоров или директора), определенный в шаге 4.</span><span class="sxs-lookup"><span data-stu-id="b7686-144">In the **Fully qualified domain name (FQDN for target host**, you'll need to type or browse to the internal Web Services FQDN for your Front End pool (or single Front End Server, or Director pool or Director), identified in step 4 above.</span></span> <span data-ttu-id="b7686-145">Click OK when this is entered.</span><span class="sxs-lookup"><span data-stu-id="b7686-145">Click OK when this is entered.</span></span>
    
8. <span data-ttu-id="b7686-146">Вам потребуется создать запись CNAME автообнаружения в зоне прямого просмотра для каждого домена SIP, поддерживаемые в вашей Скайп среды Business Server.</span><span class="sxs-lookup"><span data-stu-id="b7686-146">You'll need to create a new Autodiscover CNAME record in the forward lookup zone for each SIP domain supported in your Skype for Business Server environment.</span></span>
    
### <a name="create-an-external-dns-cname-record"></a><span data-ttu-id="b7686-147">Создание внешней DNS-записи CNAME</span><span class="sxs-lookup"><span data-stu-id="b7686-147">Create an external DNS CNAME record</span></span>

1. <span data-ttu-id="b7686-148">Поскольку вы можете использовать разных общедоступных поставщиков DNS, в этом разделе приводятся универсальные действия. Войдите в систему общедоступного поставщика DNS с использованием учетной записи с правами на создание новых записей DNS.</span><span class="sxs-lookup"><span data-stu-id="b7686-148">These steps are generic, because we can't tell what public DNS provider you might be using, but we still want to help you out. Please log into your public DNS provider with an account that will be able to make new DNS records there.</span></span>
    
2. <span data-ttu-id="b7686-149">В этот момент SIP-домена должна уже существовать существует для Скайп для Business Server.</span><span class="sxs-lookup"><span data-stu-id="b7686-149">At this point in time, a SIP domain should already exist there for Skype for Business Server.</span></span> <span data-ttu-id="b7686-150">Разверните узел **Зоны прямого просмотра** для этого домена SIP или откройте его любым другим способом.</span><span class="sxs-lookup"><span data-stu-id="b7686-150">Expand the **Forward Lookup Zone** for this SIP domain, or otherwise open it up.</span></span>
    
3. <span data-ttu-id="b7686-151">Проверьте, какие из следующих записей присутствуют в этом узле:</span><span class="sxs-lookup"><span data-stu-id="b7686-151">Take a moment to see which of the following you have:</span></span>
    
   - <span data-ttu-id="b7686-152">Любой A или AAAA записи узлов для сервера переднего плана (Standard или Enterprise) или pool(s) переднего плана.</span><span class="sxs-lookup"><span data-stu-id="b7686-152">Any host A or AAAA records for your Front End Server (Standard or Enterprise) or Front End pool(s).</span></span>
    
   - <span data-ttu-id="b7686-153">Любой узел A или AAAA записи для директора или директора пула (необязательные конфигурация которые могут возникнуть в вашем развертывании).</span><span class="sxs-lookup"><span data-stu-id="b7686-153">Any host A or AAAA records for a Director or Director pool (an optional configuration you may have in your deployment).</span></span>
    
4. <span data-ttu-id="b7686-154">Имея на руках эти сведения, вы можете выбрать команду **Создать псевдоним (CNAME)**.</span><span class="sxs-lookup"><span data-stu-id="b7686-154">Once you have that information, you should be able to select an option for creating a **New Alias (CNAME)**.</span></span>
    
5. <span data-ttu-id="b7686-155">В поле **Имя псевдонима** введите lyncdiscover в качестве URL-адреса внешней службы автообнаружения.</span><span class="sxs-lookup"><span data-stu-id="b7686-155">Now you should be able to enter an **Alias Name**, you need to enter lyncdiscover here for the external Autodiscover service URL.</span></span>
    
6. <span data-ttu-id="b7686-156">Далее следует область ввода в **поле полное доменное имя для целевого узла**, это должно быть полное доменное имя для вашего переднего плана пула (или одним сервером переднего плана, или пул директоров или Director), определенного в шаге 3 выше.</span><span class="sxs-lookup"><span data-stu-id="b7686-156">Next there should be an area to enter in a **FQDN for target host**, this will need to be the FQDN for your Front End pool (or single Front End Server, or Director pool or Director), identified in step 3 above.</span></span>
    
7. <span data-ttu-id="b7686-157">Может потребоваться сохранить здесь, или если вам потребуется создать дополнительные записи CNAME в зоне прямого просмотра каждого SIP-домена в вашей Скайп среды Business Server, необходимо сделать, но как только вы будете готовы, сохраните данные.</span><span class="sxs-lookup"><span data-stu-id="b7686-157">You may need to save here, or if you need to create additional CNAME records in the forward lookup zone of each SIP domain in your Skype for Business Server environment, you should do that, but once you're ready, save your work.</span></span>
    
### <a name="create-an-internal-dns-a-record"></a><span data-ttu-id="b7686-158">Создание записи A внутреннего DNS</span><span class="sxs-lookup"><span data-stu-id="b7686-158">Create an internal DNS A record</span></span>

1. <span data-ttu-id="b7686-159">Войдите в систему DNS-сервера в сети, который входит в группу **Администраторы домена** или **DnsAdmins**.</span><span class="sxs-lookup"><span data-stu-id="b7686-159">Log into a DNS server in your network that's either a member of the **Domain Admins** group or the **DnsAdmins** group.</span></span>
    
2. <span data-ttu-id="b7686-160">Нажмите кнопку **Пуск** и выберите **Администрирование**. Если этот компонент отсутствует в меню "Пуск", воспользуйтесь полем **Поиск**. Затем щелкните **DNS**, чтобы открыть административную оснастку DNS.</span><span class="sxs-lookup"><span data-stu-id="b7686-160">Click **Start**, Choose **Administrative Tools** (you may need to **Search** for it if it's not an option off the Start menu), and then click **DNS** to open the DNS administrative snap-in.</span></span>
    
3. <span data-ttu-id="b7686-161">В левой панели окна консоли, вам потребуется перейти к домену на номер домашнего для вашей Скайп для серверов переднего плана Business Server и разверните узел **Зоны прямого просмотра** существует.</span><span class="sxs-lookup"><span data-stu-id="b7686-161">In the left-hand pane of the console window, you'll need to go to the domain that's home to your Skype for Business Server's Front End Servers, and expand the **Forward Lookup Zones** there.</span></span>
    
4. <span data-ttu-id="b7686-162">Проверьте, какие из следующих записей присутствуют в этом узле:</span><span class="sxs-lookup"><span data-stu-id="b7686-162">Take a moment to see which of the following you have:</span></span>
    
   - <span data-ttu-id="b7686-163">Любой A или AAAA записи узлов для сервера переднего плана (Standard или Enterprise) или pool(s) переднего плана.</span><span class="sxs-lookup"><span data-stu-id="b7686-163">Any host A or AAAA records for your Front End Server (Standard or Enterprise) or Front End pool(s).</span></span>
    
   - <span data-ttu-id="b7686-164">Любой узел A или AAAA записи для директора или директора пула (необязательные конфигурация которые могут возникнуть в вашем развертывании).</span><span class="sxs-lookup"><span data-stu-id="b7686-164">Any host A or AAAA records for a Director or Director pool (an optional configuration you may have in your deployment).</span></span>
    
5. <span data-ttu-id="b7686-165">После этого щелкните правой кнопкой мыши имя домена SIP и выберите в меню пункт **Создать узел (A или AAAA)**.</span><span class="sxs-lookup"><span data-stu-id="b7686-165">Once you've noted this, right-click your SIP domain name, and then choose **New Host (A or AAAA)** from the menu.</span></span>
    
6. <span data-ttu-id="b7686-166">В текстовое поле **Имя** введите lyncdiscoverinternal в качестве имени узла для URL-адреса внутренней службы автообнаружения.</span><span class="sxs-lookup"><span data-stu-id="b7686-166">In the **Name** textbox, type lyncdiscoverinternal for your host name, for the internal Autodiscover service URL.</span></span>
    
7. <span data-ttu-id="b7686-167">В текстовом поле **IP-адрес** типа Web Services IP-адрес внутреннего для переднего плана пула (или один сервер переднего плана, или пул директоров или директоров), определенный в приведенном выше шаге 4.</span><span class="sxs-lookup"><span data-stu-id="b7686-167">In the **IP Address** textbox, type the internal Web Services IP address for your Front End pool (or single Front End Server, or Director pool or Director), identified in step 4 above.</span></span>
    
8. <span data-ttu-id="b7686-168">Затем щелкните **Добавить узел** и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="b7686-168">When this is done, click **Add Host**, and then click **OK**.</span></span>
    
9. <span data-ttu-id="b7686-169">Вам потребуется создать новые записи автообнаружения A или AAAA в зоне прямого просмотра для каждого домена SIP, поддерживаемые в вашей Скайп среды Business Server.</span><span class="sxs-lookup"><span data-stu-id="b7686-169">You'll need to create a new Autodiscover A or AAAA records in the forward lookup zone for each SIP domain supported in your Skype for Business Server environment.</span></span> <span data-ttu-id="b7686-170">Для этого повторяйте шаги с 6 по 8 необходимое число раз.</span><span class="sxs-lookup"><span data-stu-id="b7686-170">To do this, repeat steps 6-8 as many times as needed.</span></span>
    
10. <span data-ttu-id="b7686-171">По завершении нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="b7686-171">When you're done, click **Done**.</span></span>
    
### <a name="create-an-external-dns-a-record"></a><span data-ttu-id="b7686-172">Создание записи A внешнего DNS</span><span class="sxs-lookup"><span data-stu-id="b7686-172">Create an external DNS A record</span></span>

1. <span data-ttu-id="b7686-173">Поскольку вы можете использовать разных общедоступных поставщиков DNS, в этом разделе приводятся универсальные действия. Войдите в систему общедоступного поставщика DNS с использованием учетной записи с правами на создание новых записей DNS.</span><span class="sxs-lookup"><span data-stu-id="b7686-173">These steps are generic, because we can't tell what public DNS provider you might be using, but we still want to help you out. Please log into your public DNS provider with an account that will be able to make new DNS records there.</span></span>
    
2. <span data-ttu-id="b7686-174">В этот момент SIP-домена должна уже существовать существует для Скайп для Business Server.</span><span class="sxs-lookup"><span data-stu-id="b7686-174">At this point in time, a SIP domain should already exist there for Skype for Business Server.</span></span> <span data-ttu-id="b7686-175">Разверните узел **Зоны прямого просмотра** для этого домена SIP или откройте его любым другим способом.</span><span class="sxs-lookup"><span data-stu-id="b7686-175">Expand the **Forward Lookup Zone** for this SIP domain, or otherwise open it up.</span></span>
    
3. <span data-ttu-id="b7686-176">Проверьте, какие из следующих записей присутствуют в этом узле:</span><span class="sxs-lookup"><span data-stu-id="b7686-176">Take a moment to see which of the following you have:</span></span>
    
   - <span data-ttu-id="b7686-177">Любой A или AAAA записи узлов для сервера переднего плана (Standard или Enterprise) или pool(s) переднего плана.</span><span class="sxs-lookup"><span data-stu-id="b7686-177">Any host A or AAAA records for your Front End Server (Standard or Enterprise) or Front End pool(s).</span></span>
    
   - <span data-ttu-id="b7686-178">Любой узел A или AAAA записи для директора или директора пула (необязательные конфигурация которые могут возникнуть в вашем развертывании).</span><span class="sxs-lookup"><span data-stu-id="b7686-178">Any host A or AAAA records for a Director or Director pool (an optional configuration you may have in your deployment).</span></span>
    
4. <span data-ttu-id="b7686-179">Имея на руках эти сведения, вы можете выбрать команду **Создать узел (A или AAAA)**.</span><span class="sxs-lookup"><span data-stu-id="b7686-179">Once you have that information, you should be able to select an option for creating a **New Host A or AAAA**.</span></span>
    
5. <span data-ttu-id="b7686-180">В поле **Имя** введите lyncdiscover в качестве URL-адреса внешней службы автообнаружения.</span><span class="sxs-lookup"><span data-stu-id="b7686-180">Now you should be able to enter a **Name**, you need to enter lyncdiscover here for the external Autodiscover service URL.</span></span>
    
6. <span data-ttu-id="b7686-181">Теперь должен появиться область ввода в **IP-адреса**, это должно быть IP-адресов для переднего плана пула (или одним сервером переднего плана, или пул директоров или директоров), определенный в шаге 3.</span><span class="sxs-lookup"><span data-stu-id="b7686-181">Next there should be an area to enter in a **IP Addresss**, this will need to be the IP for your Front End pool (or single Front End Server, or Director pool or Director), identified in step 3 above.</span></span>
    
7. <span data-ttu-id="b7686-182">Может потребоваться сохранить здесь, или если вам необходимо создать дополнительные A или AAAA-записи в зоне прямого просмотра каждого SIP-домена для вашей Скайп среды Business Server, это следует сделать, но один раз вы будете готовы, сохранение результатов работы.</span><span class="sxs-lookup"><span data-stu-id="b7686-182">You may need to save here, or if you need to create additional A or AAAA records in the forward lookup zone of each SIP domain for your Skype for Business Server environment, you should do that, but once you're ready, save your work.</span></span>
    
## <a name="modify-certificates"></a><span data-ttu-id="b7686-183">Изменение сертификатов</span><span class="sxs-lookup"><span data-stu-id="b7686-183">Modify certificates</span></span>
<span data-ttu-id="b7686-184"><a name="ModCerts"> </a></span><span class="sxs-lookup"><span data-stu-id="b7686-184"></span></span>

<span data-ttu-id="b7686-185">Если у вас есть вопросы о планировании вокруг сертификаты, мы документированы, в нашем статье [Планирование для мобильных устройств для Скайп для Business Server](../plan-your-deployment/mobility.md) .</span><span class="sxs-lookup"><span data-stu-id="b7686-185">If you have questions about Planning around certificates, we've documented that in our [Plan for Mobility for Skype for Business Server](../plan-your-deployment/mobility.md) article.</span></span> <span data-ttu-id="b7686-186">После этого вы можете продолжать знакомство с этим пошаговым руководством:</span><span class="sxs-lookup"><span data-stu-id="b7686-186">Once you've reviewed that, we'll walk you through the following:</span></span>
  
- <span data-ttu-id="b7686-187">Требуются ли новые сертификаты?</span><span class="sxs-lookup"><span data-stu-id="b7686-187">Do I need new certificates?</span></span>
    
- <span data-ttu-id="b7686-188">Запрос новых сертификатов из центра сертификации.</span><span class="sxs-lookup"><span data-stu-id="b7686-188">Requesting new certificates from your Certificate Authority (CA).</span></span>
    
- <span data-ttu-id="b7686-189">Замена существующих сертификатов новыми с помощью PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b7686-189">Updating your in-place certificates with the replacements using PowerShell.</span></span>
    
- <span data-ttu-id="b7686-190">Проверка сертификатов, с помощью оснастки сертификатов в консоль управления (MMC).</span><span class="sxs-lookup"><span data-stu-id="b7686-190">Checking the certificates using the Certificates snapin in the Microsoft Management Console (MMC).</span></span>
    
### <a name="do-i-need-new-certificates"></a><span data-ttu-id="b7686-191">Требуются ли новые сертификаты?</span><span class="sxs-lookup"><span data-stu-id="b7686-191">Do I need new certificates?</span></span>

1. <span data-ttu-id="b7686-192">Сначала требуется проверить существующие сертификаты и наличие в них необходимых записей.</span><span class="sxs-lookup"><span data-stu-id="b7686-192">First, you may need to check and see what certificates are in-place, and whether or not they have the entries you need.</span></span> <span data-ttu-id="b7686-193">Для этого необходимо войти в вашей Скайп Business Server с использованием учетной записи, которая является учетной записью локального администратора.</span><span class="sxs-lookup"><span data-stu-id="b7686-193">To do that, you'll need to log into your Skype for Business Server with an account that's a local Administrator.</span></span> <span data-ttu-id="b7686-194">Кроме того, для выполнения некоторых действий этой учетной записи могут потребоваться права на доступ к выдающему центру сертификации.</span><span class="sxs-lookup"><span data-stu-id="b7686-194">This account may also need to have rights to the issuing Certificate Authority (CA), for some of these steps.</span></span>
    
2. <span data-ttu-id="b7686-195">Откройте Скайп оболочки управления Business Server (можно выполнить поиск их расположение, если у вас нет его прикрепленных на панель задач и меню Пуск).</span><span class="sxs-lookup"><span data-stu-id="b7686-195">Open the Skype for Business Server Management Shell (you can use Search to find it if you don't have it pinned to your Start menu or task bar).</span></span>
    
3. <span data-ttu-id="b7686-p110">Важно знать, какие сертификаты были назначены до того, как вы попытаетесь добавить или обновить сертификат. В командной строке введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="b7686-p110">It's going to be essential for you to know what certificates have been assigned before you try adding an updated certificate. So at the command, type:</span></span>
    
   ```
   Get-CsCertificate
   ```

4. <span data-ttu-id="b7686-p111">На шаге 3 вы получите сведения, относящиеся к вашей уникальной среде. Опираясь на них, определите, используются ли у вас один или несколько сертификатов для нескольких компонентов. Параметр **Использование** содержит информацию об использовании сертификата, а параметр **Отпечаток** определяет, применяются ли для этих целей один или несколько сертификатов.</span><span class="sxs-lookup"><span data-stu-id="b7686-p111">The information from Step 3 will be unique to you. You need to look it over to determine if you have a single certificate that's been assigned for multiple things, or whether you have a different certificate assigned for the different components that need them. The **Use** parameter will tell you how a certificate's being used, and the **Thumbprint** parameter will tell you if it's all the same certificate, or multiple certs.</span></span>
    
5. <span data-ttu-id="b7686-p112">Если вы не настроили записи альтернативного имени субъекта согласно рекомендациям в разделе "Планирование", вам необходимо запросить один или несколько новых сертификатов (в зависимости от конфигурации) из центра сертификации.</span><span class="sxs-lookup"><span data-stu-id="b7686-p112">If you have the SAN entries recommended in our Planning section, you're good. If not, you'll need to request a new certificate, or multiple certificates (depending on your configuration) from your Certificate Authority.</span></span>
    
### <a name="request-a-new-certificate-or-certificates-from-your-certificate-authority-ca"></a><span data-ttu-id="b7686-203">Запрос одного или нескольких новых сертификатов из центра сертификации.</span><span class="sxs-lookup"><span data-stu-id="b7686-203">Request a new certificate, or certificates, from your Certificate Authority (CA)</span></span>

1. <span data-ttu-id="b7686-204">Проверив существующие записи альтернативного имени субъекта по описанной выше процедуре, вы определили наличие **одного сертификата** и обнаружили, что некоторые необходимые записи отсутствуют.</span><span class="sxs-lookup"><span data-stu-id="b7686-204">After you've checked to see what SAN entries you have, you know you have a **single certificate** (after checking via the steps above), and you learned you don't have all the entries you need.</span></span> <span data-ttu-id="b7686-205">В этом случае вам необходимо запросить новый сертификат в центре сертификации.</span><span class="sxs-lookup"><span data-stu-id="b7686-205">A new certificate request needs to be made to your CA.</span></span> <span data-ttu-id="b7686-206">Откройте вашей Скайп для Business Server PowerShell:</span><span class="sxs-lookup"><span data-stu-id="b7686-206">Open your Skype for Business Server PowerShell:</span></span>
    
   - <span data-ttu-id="b7686-207">Для отсутствующей записи альтернативного имени субъекта для службы автообнаружения (замените параметр -Ca путем к вашему центру сертификации):</span><span class="sxs-lookup"><span data-stu-id="b7686-207">For a missing Autodiscover Service SAN (replacing the -Ca parameter with your own Certificate Authority path):</span></span>
    
   ```
   Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -Ca dc\myca -AllSipDomain -verbose
   ```

   - <span data-ttu-id="b7686-208">Теперь если у вас есть несколько доменов SIP, нельзя использовать параметр AllSipDomain, как показано в приведенном выше примере.</span><span class="sxs-lookup"><span data-stu-id="b7686-208">Now, if you have multiple SIP domains, you can't use the AllSipDomain parameter as in the example above.</span></span> <span data-ttu-id="b7686-209">Вам потребуется вместо этого использовать параметр DomainName.</span><span class="sxs-lookup"><span data-stu-id="b7686-209">You'll need to use the DomainName parameter instead.</span></span> <span data-ttu-id="b7686-210">И, если используется параметр DomainName, у вас есть определение полного доменного ИМЕНИ для записи lyncdiscover и lyncdiscoverinternal.</span><span class="sxs-lookup"><span data-stu-id="b7686-210">And when you use the DomainName parameter, you've got to define the FQDN for the lyncdiscoverinternal and lyncdiscover records.</span></span> <span data-ttu-id="b7686-211">Пример может быть (Замените параметр -Ca путь сертификации):</span><span class="sxs-lookup"><span data-stu-id="b7686-211">An example would be (replacing the -Ca parameter with your own Certificate Authority path):</span></span>
    
   ```
   Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -Ca dc\myca -DomainName "LyncdiscoverInternal.contoso.com, LyncdiscoverInternal.contoso.net" -verbose
   ```

2. <span data-ttu-id="b7686-212">Проверив существующие записи альтернативного имени субъекта по описанной выше процедуре, вы определили наличие **нескольких сертификатов** и обнаружили, что некоторые необходимые записи отсутствуют.</span><span class="sxs-lookup"><span data-stu-id="b7686-212">Or, after you've checked to see what SAN entries you have, you found you have **multiple certificates** that don't have all the entries you need.</span></span> <span data-ttu-id="b7686-213">В этом случае вам необходимо запросить новый сертификат в центре сертификации.</span><span class="sxs-lookup"><span data-stu-id="b7686-213">A new certificate request needs to be made to your CA.</span></span> <span data-ttu-id="b7686-214">Откройте вашей Скайп для Business Server PowerShell:</span><span class="sxs-lookup"><span data-stu-id="b7686-214">Open your Skype for Business Server PowerShell:</span></span>
    
   - <span data-ttu-id="b7686-215">Для отсутствующей записи альтернативного имени субъекта для службы автообнаружения (замените параметр -Ca путем к вашему центру сертификации):</span><span class="sxs-lookup"><span data-stu-id="b7686-215">For a missing Autodiscover Service SAN (replacing the -Ca parameter with your own Certificate Authority path):</span></span>
    
   ```
   Request-CsCertificate -New -Type WebServicesInternal -Ca dc\myca -AllSipDomain -verbose
   ```

   - <span data-ttu-id="b7686-216">Теперь если у вас есть несколько доменов SIP, нельзя использовать параметр AllSipDomain, как показано в приведенном выше примере.</span><span class="sxs-lookup"><span data-stu-id="b7686-216">Now, if you have multiple SIP domains, you can't use the AllSipDomain parameter as in the example above.</span></span> <span data-ttu-id="b7686-217">Вам потребуется вместо этого использовать параметр DomainName.</span><span class="sxs-lookup"><span data-stu-id="b7686-217">You'll need to use the DomainName parameter instead.</span></span> <span data-ttu-id="b7686-218">И, если используется параметр DomainName, у вас есть определение полного доменного ИМЕНИ для записи lyncdiscover и lyncdiscoverinternal.</span><span class="sxs-lookup"><span data-stu-id="b7686-218">And when you use the DomainName parameter, you've got to define the FQDN for the lyncdiscoverinternal and lyncdiscover records.</span></span> <span data-ttu-id="b7686-219">Примеры бы (Замените параметр -Ca путь сертификации):</span><span class="sxs-lookup"><span data-stu-id="b7686-219">Examples would be (replacing the -Ca parameter with your own Certificate Authority path):</span></span>
    
   ```
   Request-CsCertificate -New -Type WebServicesInternal -Ca dc\myca -DomainName "LyncdiscoverInternal.contoso.com, LyncdiscoverInternal.contoso.net" -verbose
   ```

   ```
   Request-CsCertificate -New -Type WebServicesExternal -Ca dc\myca -DomainName "Lyncdiscover.contoso.com, Lyncdiscover.contoso.net" -verbose
   ```

   - <span data-ttu-id="b7686-220">После создания новых сертификатов в центре сертификации вам необходимо назначить их.</span><span class="sxs-lookup"><span data-stu-id="b7686-220">Once the new certificates have been generated by the CA, you're going to need to assign them.</span></span>
    
### <a name="assign-certificates-using-skype-for-business-server-management-shell"></a><span data-ttu-id="b7686-221">Назначение сертификатов с помощью командной консоли Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="b7686-221">Assign certificates using Skype for Business Server Management Shell</span></span>

- <span data-ttu-id="b7686-222">В зависимости от результатов анализа среды, проведенного в разделе "Требуются ли новые сертификаты?", вам необходимо выполнить **одно** из следующих действий.</span><span class="sxs-lookup"><span data-stu-id="b7686-222">Depending on what you found in the Do I need new certifications section above, you need to run **one** of the following.</span></span>
    
  - <span data-ttu-id="b7686-223">Если вы используете для всех компонентов один и тот же сертификат (одинаковые отпечатки), выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="b7686-223">If you have a single certificate for everything (the thumbprints are identical) then you need to run this:</span></span>
    
  ```
  Set-CsCertificate -Type <certificate(s) from the Use parameter> -Thumbprint <unique identifier>
  ```

  - <span data-ttu-id="b7686-224">Если вы используете несколько сертификатов с разными отпечатками, выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="b7686-224">If you've got different certificates for things (the thumbprints are all different), run this instead:</span></span>
    
  ```
  Set-CsCertificate -Type Default -Thumbprint <certificate thumbprint>
  Set-CsCertificate -Type WebServicesInternal -Thumbprint <certificate thumbprint>
  Set-CsCertificate -Type WebServicesExternal -Thumbprint <certificate thumbprint>
  ```

### <a name="viewing-certificates-in-the-microsoft-management-console-mmc"></a><span data-ttu-id="b7686-225">Просмотр сертификатов с помощью консоли управления (MMC)</span><span class="sxs-lookup"><span data-stu-id="b7686-225">Viewing certificates in the Microsoft Management Console (MMC)</span></span>

1. <span data-ttu-id="b7686-p117">Для просмотра всех сертификатов вы можете использовать оснастку сертификатов в консоли MMC. Чтобы открыть это приложение во всплывающем окне, достаточно ввести "MMC" в поле поиска.</span><span class="sxs-lookup"><span data-stu-id="b7686-p117">You have an option to look at your certificates using the Certificates snap-in for the MMC. Simply type MMC into search and it should pop up as an application option,.</span></span>
    
2. <span data-ttu-id="b7686-p118">Чтобы добавить оснастку сертификатов, щелкните **Файл** и выберите **Добавить или удалить оснастку** (также можно использовать сочетание клавиш **CTRL+M**). Выберите элемент **Сертификаты** в панели слева, щелкните **Учетная запись компьютера** во всплывающем окне и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="b7686-p118">To add the Certificates snap-in, you'll need to click **File**, and then **Add/Remove Snap-In...** (or keyboard shortcut **Ctrl+M** would also work). **Certificates** will be an option in the left-hand pane, select it and then **Computer Account** in the pop-up window, then **Next**.</span></span>
    
3. <span data-ttu-id="b7686-230">По-прежнему во всплывающем окне в все вероятность при выполнении этого компьютера, который имеет номер домашнего сертификаты, необходимые для поиска в таком выходе выбора на **локальном компьютере** Если это так.</span><span class="sxs-lookup"><span data-stu-id="b7686-230">Still in the pop-up window, in all likelihood you're doing this on the computer that's home to the certificates you need to look at, so leave the selection on **Local Computer** if that's so.</span></span> <span data-ttu-id="b7686-231">Если вы работаете на удаленном компьютере, измените переключатель на **Другом компьютере** и затем введите полное доменное имя компьютера или нажмите кнопку **Обзор** для поиска этим компьютером через AD.</span><span class="sxs-lookup"><span data-stu-id="b7686-231">If you're working on a remote machine, change the radio button to **Another Computer** and then either enter that computer's FQDN or use the **Browse** button to search for that computer through AD.</span></span> <span data-ttu-id="b7686-232">После выбора компьютера, вам потребуются нажмите кнопку **Готово** , когда все будет готово, а затем **кнопку ОК** для добавьте оснастку консоли Управления.</span><span class="sxs-lookup"><span data-stu-id="b7686-232">After selecting the computer, you'll need to click **Finish** when ready, and then **OK** to add the snap-in to the MMC.</span></span>
    
4. <span data-ttu-id="b7686-233">Разверните раздел **сертификаты** в левой панели консоли Управления.</span><span class="sxs-lookup"><span data-stu-id="b7686-233">Expand the **Certificates** section in the MMC's left-hand pane.</span></span> <span data-ttu-id="b7686-234">Разверните узел **личных** папок также и выберите **сертификаты**.</span><span class="sxs-lookup"><span data-stu-id="b7686-234">Expand the **Personal** folder as well, and then select **Certificates**.</span></span> <span data-ttu-id="b7686-235">Это позволяет просмотреть сертификаты в это хранилище.</span><span class="sxs-lookup"><span data-stu-id="b7686-235">This lets you see the certificates in this store.</span></span>
    
5. <span data-ttu-id="b7686-236">Найдите нужный сертификат, щелкните его правой кнопкой мыши и выберите пункт **Открыть**.</span><span class="sxs-lookup"><span data-stu-id="b7686-236">You need to locate the certificate you want to view, right-click on it, and choose **Open**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="b7686-237">How do you know what certificate this is?</span><span class="sxs-lookup"><span data-stu-id="b7686-237">How do you know what certificate this is?</span></span> <span data-ttu-id="b7686-238">Он должен содержать либо один сертификат, назначенных для всех компонентов фермы, или имеется несколько сертификатов для выполнения различных задач, например по умолчанию, внутренних веб-служб, и т.д., в этом случае необходимо рассмотреть несколько сертификатов.</span><span class="sxs-lookup"><span data-stu-id="b7686-238">It should be either the single certificate assigned to everything for your farm, or you may have multiple certificates for different things, like Default, Internal Web Services, etc., in which case you may need to look at multiple certificates.</span></span> <span data-ttu-id="b7686-239">Multiple certificates will have the same thumbprint.</span><span class="sxs-lookup"><span data-stu-id="b7686-239">Multiple certificates will have the same thumbprint.</span></span> 
  
6. <span data-ttu-id="b7686-p122">В представлении **Сертификат** выберите **Сведения**. В этом разделе вы сможете просмотреть имя субъекта сертификата (выберите **Subject**), назначенное имя субъекта, а также связанные свойства.</span><span class="sxs-lookup"><span data-stu-id="b7686-p122">Once you've gotten to the **Certificate** view, choose **Details**. This will let you see the certificate subject name when you select **Subject**, and the assigned subject name and associated properties are shown.</span></span>
    
7. <span data-ttu-id="b7686-p123">Также следует проверить записи **Альтернативное имя субъекта**. В них вы можете найти следующую информацию:</span><span class="sxs-lookup"><span data-stu-id="b7686-p123">You'll also need to check the **Subject Alternate Name** entries. You'll find one or more of the following:</span></span>
    
   - <span data-ttu-id="b7686-244">Имя пула для этого пула или имя отдельного сервера, если это не пул.</span><span class="sxs-lookup"><span data-stu-id="b7686-244">The pool name for this pool, or the single server name if this isn't a pool.</span></span>
    
   - <span data-ttu-id="b7686-245">Имя сервера, которому назначен сертификат.</span><span class="sxs-lookup"><span data-stu-id="b7686-245">The server name that the certificate is assigned to.</span></span>
    
   - <span data-ttu-id="b7686-246">Записи простых URL-адресов (обычно meet и dialin).</span><span class="sxs-lookup"><span data-stu-id="b7686-246">Simple URL records, typically meet and dialin.</span></span>
    
   - <span data-ttu-id="b7686-247">Веб-службы внутренних и веб-служб внешних имен (например, webpool01.contoso.net, webpool01.contoso.com), основанные на в построителе топологий и выборе выбранных элементов для веб-служб.</span><span class="sxs-lookup"><span data-stu-id="b7686-247">Web Services internal and Web Services external names (for example, webpool01.contoso.net, webpool01.contoso.com), based on choices made in Topology Builder and over-ridden Web Services selections.</span></span>
    
   - <span data-ttu-id="b7686-248">Если они уже назначены, lyncdiscover. \<sipdomain\> и lyncdiscoverinternal. \<sipdomain\> записей.</span><span class="sxs-lookup"><span data-stu-id="b7686-248">If already assigned, the lyncdiscover.\<sipdomain\> and lyncdiscoverinternal.\<sipdomain\> records.</span></span>
    
     <span data-ttu-id="b7686-249">Если назначено несколько сертификатов, необходимо проверить наличие множественных сертификатов (см. примечание выше).</span><span class="sxs-lookup"><span data-stu-id="b7686-249">You'll need to check multiple certificates if you have more than one assigned (check the Note above).</span></span>
    
8. <span data-ttu-id="b7686-250">Таким образом, если находит lyncdiscover. \<sipdomain\> и lyncdiscoverinternal. \<sipdomain\> записей, у вас это уже настроен.</span><span class="sxs-lookup"><span data-stu-id="b7686-250">So, if you find lyncdiscover.\<sipdomain\> and lyncdiscoverinternal.\<sipdomain\> records, you've got this configured already.</span></span> <span data-ttu-id="b7686-251">Закройте консоль MMC.</span><span class="sxs-lookup"><span data-stu-id="b7686-251">You can close the MMC.</span></span>
    
9. <span data-ttu-id="b7686-252">Если они не назначены, необходимо запросить новый сертификат (см. выше) или установить их после запроса (для этого рекомендуется использовать представленный выше командлет PowerShell).</span><span class="sxs-lookup"><span data-stu-id="b7686-252">If they aren't assigned, you'll either need to make a new certificate request (outlined above) or you need to install them post-request (we recommend the following the PowerShell above for that).</span></span>
    
## <a name="configure-the-reverse-proxy"></a><span data-ttu-id="b7686-253">Настройка обратного прокси-сервера</span><span class="sxs-lookup"><span data-stu-id="b7686-253">Configure the reverse proxy</span></span>
<span data-ttu-id="b7686-254"><a name="ConfigRP"> </a></span><span class="sxs-lookup"><span data-stu-id="b7686-254"></span></span>

<span data-ttu-id="b7686-p125">Представленные ниже шаги не обязательно выполнять в точности. Например, в предыдущих версиях продукта требовалась настройка Threat Management Gateway (TMG), поэтому если этот компонент не используется, вы можете пропустить соответствующие действия.</span><span class="sxs-lookup"><span data-stu-id="b7686-p125">The steps below are not meant to be followed exactly. That's because in previous versions of the product, we'd have walked you through, for example, configuring Threat Management Gateway (TMG) and if you weren't using that, you'd need to work out your own version from there.</span></span>
  
<span data-ttu-id="b7686-257">TMG is no longer being offered by Microsoft as a product, and if you still need to configure it, you can look at the [Lync Server 2013 steps](https://technet.microsoft.com/en-us/library/hh690011%28v=ocs.15%29.aspx).</span><span class="sxs-lookup"><span data-stu-id="b7686-257">TMG is no longer being offered by Microsoft as a product, and if you still need to configure it, you can look at the [Lync Server 2013 steps](https://technet.microsoft.com/en-us/library/hh690011%28v=ocs.15%29.aspx).</span></span> <span data-ttu-id="b7686-258">Но со следующими сведениями предназначенного для формирования более полезным, даже в том случае, если нет возможности мы можем предоставить определенные шаги для каждого обратного прокси-сервера.</span><span class="sxs-lookup"><span data-stu-id="b7686-258">But the following information's intended to be more generally helpful, even if there's no way we can provide specific walkthrough steps for every Reverse proxy out there.</span></span>
  
<span data-ttu-id="b7686-259">Необходимо учитывать два основных момента:</span><span class="sxs-lookup"><span data-stu-id="b7686-259">We have two main things to consider:</span></span>
  
- <span data-ttu-id="b7686-260">Будет ли выполняться первоначальный запрос службы автообнаружения по протоколу HTTPS (рекомендуется)?</span><span class="sxs-lookup"><span data-stu-id="b7686-260">Are you going to be doing your initial Autodiscover request over HTTPS (which we recommend)?</span></span>
    
  - <span data-ttu-id="b7686-261">Если у вас есть правило веб-публикации, его необходимо изменить.</span><span class="sxs-lookup"><span data-stu-id="b7686-261">If you have a web publishing rule, you need to modify it.</span></span>
    
  - <span data-ttu-id="b7686-262">Если у вас нет правила веб-публикации, его необходимо создать.</span><span class="sxs-lookup"><span data-stu-id="b7686-262">If you don't have a web publishing rule yet, you need to create it.</span></span>
    
- <span data-ttu-id="b7686-263">Если первоначальный запрос службы автообнаружения выполняется по протоколу HTTP, также необходимо создать или изменить это правило.</span><span class="sxs-lookup"><span data-stu-id="b7686-263">If you're doing your initial Autodiscover request over HTTP, then you'll need to create or modify that rule as well.</span></span>
    
> [!NOTE]
> <span data-ttu-id="b7686-264">**Важные** Значение времени ожидания прокси-сервер — это число, которое будут зависеть от развертывания для развертывания.</span><span class="sxs-lookup"><span data-stu-id="b7686-264">**Important** A Proxy time-out value is a number that will vary from deployment to deployment.</span></span> <span data-ttu-id="b7686-265">Проверяйте развертывания и измените значение для обеспечения наилучшего взаимодействия для клиентов.</span><span class="sxs-lookup"><span data-stu-id="b7686-265">You should monitor your deployment and modify the value for the best experience for clients.</span></span> <span data-ttu-id="b7686-266">Можно задать значение как меньше 200.</span><span class="sxs-lookup"><span data-stu-id="b7686-266">You may be able to set the value as low as 200.</span></span> <span data-ttu-id="b7686-267">Если вы поддерживаете мобильных клиентов Lync в вашей среде, следует устанавливать значение для 960 для разрешения для времени ожидания push notification из Office 365, что значение времени ожидания 900.</span><span class="sxs-lookup"><span data-stu-id="b7686-267">If you are supporting Lync mobile clients in your environment, you should set the value to 960 to allow for push notification time-outs from Office 365, which have a time-out value of 900.</span></span> <span data-ttu-id="b7686-268">Скорее всего, что необходимо увеличить значение времени ожидания, чтобы избежать клиента отключается, если установлено слишком низкое значение или уменьшите значение, если подключения через прокси-сервер не отключаться, но снимите долго после отключения клиента.</span><span class="sxs-lookup"><span data-stu-id="b7686-268">It is very likely that you will have to increase the time-out value to avoid client disconnects when the value is too low, or decrease the number if connections through the proxy do not disconnect but clear long after the client has disconnected.</span></span> <span data-ttu-id="b7686-269">Мониторинг и определение базовых показателей обычным для вашей среды является только точных способом определения подходящей настройки для этого значения.</span><span class="sxs-lookup"><span data-stu-id="b7686-269">Monitoring and baselining what is usual for your environment is the only accurate way to determine the appropriate setting for this value.</span></span>
  
### <a name="modify-the-existing-web-publishing-rule-for-your-external-autodiscover-san-and-url"></a><span data-ttu-id="b7686-270">Изменение существующего правила веб-публикации для внешних альтернативного имени субъекта и URL-адреса автообнаружения</span><span class="sxs-lookup"><span data-stu-id="b7686-270">Modify the existing web publishing rule for your external Autodiscover SAN and URL</span></span>

1. <span data-ttu-id="b7686-271">Откройте интерфейс обратного прокси-сервера.</span><span class="sxs-lookup"><span data-stu-id="b7686-271">Open your Reverse proxy interface.</span></span>
    
2. <span data-ttu-id="b7686-272">Вам потребуется найдите вашей правило веб-публикации и выберите пункт Правка (возможно, в меню или вкладки, в зависимости от конфигурации обратного прокси-сервера).</span><span class="sxs-lookup"><span data-stu-id="b7686-272">You'll need to locate your web publishing rule, and choose the Edit option (it may be on a menu or tab, depending on your Reverse proxy configuration).</span></span>
    
3. <span data-ttu-id="b7686-273">Должен появиться о том, что это правило веб-публикации применяется к области.</span><span class="sxs-lookup"><span data-stu-id="b7686-273">There should be an area that states what this web publishing rule is applied to.</span></span> <span data-ttu-id="b7686-274">Вам необходимо изменить это правило для входящих сайтов или запросов сайтов.</span><span class="sxs-lookup"><span data-stu-id="b7686-274">You need to modify this rule for incoming sites or requests for sites.</span></span> <span data-ttu-id="b7686-275">В этом случае необходимо **добавить** новую запись.</span><span class="sxs-lookup"><span data-stu-id="b7686-275">You're going to **add** a new entry.</span></span>
    
4. <span data-ttu-id="b7686-276">Введите имя узла автообнаружения (пример, который будет использоваться — lyncdiscover.contoso.com) и нажмите кнопку **ОК** или **Сохранить**, в зависимости от формата обратного прокси-сервера.</span><span class="sxs-lookup"><span data-stu-id="b7686-276">Type the name of your Autodiscover site (the example we'll use is lyncdiscover.contoso.com), and click **OK** or **Save**, depending on your Reverse proxy's format.</span></span>
    
5. <span data-ttu-id="b7686-277">You may have a new certificate that has the Autodiscover SAN entry in it.</span><span class="sxs-lookup"><span data-stu-id="b7686-277">You may have a new certificate that has the Autodiscover SAN entry in it.</span></span> <span data-ttu-id="b7686-278">Который необходимо также установить и настроить для использования в соответствии с параметрами обратного прокси-сервера.</span><span class="sxs-lookup"><span data-stu-id="b7686-278">That needs to be installed as well and configured for use according to your Reverse proxy's settings.</span></span> <span data-ttu-id="b7686-279">Be sure to save everything when the configuration is completed.</span><span class="sxs-lookup"><span data-stu-id="b7686-279">Be sure to save everything when the configuration is completed.</span></span>
    
6. <span data-ttu-id="b7686-280">Если обратный прокси-сервер имеет **проверки** возможности, затем убедитесь, использование его на все работает должным образом.</span><span class="sxs-lookup"><span data-stu-id="b7686-280">If your Reverse proxy has a **Test** functionality, then please make use of it, to ensure everything's working properly.</span></span>
    
7. <span data-ttu-id="b7686-281">Теперь, может потребоваться повторите эти шаги, если у вас есть директора или директора пула в вашей среде (это будет означать, у вас есть второе правило).</span><span class="sxs-lookup"><span data-stu-id="b7686-281">Now, you may need to repeat these steps if you have a Director or Director pool in your environment (this would mean you have a second rule).</span></span>
    
### <a name="create-a-web-publishing-rule-for-the-external-autodiscover-url"></a><span data-ttu-id="b7686-282">Создание правила веб-публикации для внешнего URL-адреса автообнаружения</span><span class="sxs-lookup"><span data-stu-id="b7686-282">Create a web publishing rule for the external Autodiscover URL</span></span>

1. <span data-ttu-id="b7686-283">Откройте интерфейс обратного прокси-сервера.</span><span class="sxs-lookup"><span data-stu-id="b7686-283">Open your Reverse proxy interface.</span></span>
    
2. <span data-ttu-id="b7686-284">Вам потребуется найдите которых в интерфейсе создания вашего правила веб-публикации и выберите пункт **New** или **Создать** (возможно, в меню или вкладки, в зависимости от конфигурации обратного прокси-сервера).</span><span class="sxs-lookup"><span data-stu-id="b7686-284">You'll need to locate where in the interface you create your web publishing rules, and choose the **New** or **Create** option (it may be on a menu or tab, depending on your Reverse proxy configuration).</span></span> <span data-ttu-id="b7686-285">You are looking for the option to create a new web publishing rule.</span><span class="sxs-lookup"><span data-stu-id="b7686-285">You are looking for the option to create a new web publishing rule.</span></span>
    
3. <span data-ttu-id="b7686-286">Как правило, требуется ввести следующие данные:</span><span class="sxs-lookup"><span data-stu-id="b7686-286">Typically, you will need to enter the following information:</span></span>
    
   - <span data-ttu-id="b7686-287">**Имя** — имя правила.</span><span class="sxs-lookup"><span data-stu-id="b7686-287">**Name**: the name for your rule</span></span>
    
   - <span data-ttu-id="b7686-288">**Действие правила**: В этом случае правило **Разрешить** , а вы даете что-то проходить через обратный прокси-сервер.</span><span class="sxs-lookup"><span data-stu-id="b7686-288">**Rule Action**: In this case it's an **Allow** rule, you're letting something pass through your Reverse proxy.</span></span>
    
   - <span data-ttu-id="b7686-289">Правило **публикации** или выбираемый параметр (**отдельный веб-сайт или подсистема балансировки нагрузки**).</span><span class="sxs-lookup"><span data-stu-id="b7686-289">The **Publishing** rule or option you're choosing would be **single web site or load balancer**.</span></span>
    
   - <span data-ttu-id="b7686-290">Для внешнего доступа необходимо выбрать **SSL**.</span><span class="sxs-lookup"><span data-stu-id="b7686-290">This needs to be **SSL** for external access, choose that option.</span></span>
    
   - <span data-ttu-id="b7686-291">Вы собираетесь необходимо опубликовать путь для **Внутренней публикации**и введите полное доменное имя для внешних веб-служб на балансировки нагрузки для пула переднего плана (или полное доменное имя пула директоров балансировки нагрузки, если такой существует), пример будет sfb_ pool01.contoso.local.</span><span class="sxs-lookup"><span data-stu-id="b7686-291">You're going to need to publish a path for **Internal Publishing**, and enter the FQDN for the external Web Services on your Front End pool's load balancer (or the FQDN of the Director pool's load balancer if you have one), an example would be sfb_pool01.contoso.local.</span></span>
    
   - <span data-ttu-id="b7686-292">Необходимо ввести \*\* / \*\*\* как путь, который требуется опубликовать, но также требуется **пересылать исходный заголовок узла**.</span><span class="sxs-lookup"><span data-stu-id="b7686-292">You should type **/\\**\* as the path to be published, but you also need to **forward the original host header**.</span></span>
    
   - <span data-ttu-id="b7686-p131">Кроме того, будет представлен параметр для ввода сведений о **публикации или внешнем имени**:</span><span class="sxs-lookup"><span data-stu-id="b7686-p131">There will be an option for **public or external name** details or information. This is the place where you'll be able to enter:</span></span>
    
   - <span data-ttu-id="b7686-295">**Принимать запросы** (должно задаваться для доменного имени).</span><span class="sxs-lookup"><span data-stu-id="b7686-295">**Accept requests**, but it should be for the domain name.</span></span>
    
   - <span data-ttu-id="b7686-296">В поле **Имя** введите **lyncdiscover.**</span><span class="sxs-lookup"><span data-stu-id="b7686-296">For the **Name**, you should enter **lyncdiscover.**</span></span> <span data-ttu-id="b7686-297"><sipdomain>(это внешний URL-адрес службы автообнаружения).</span><span class="sxs-lookup"><span data-stu-id="b7686-297"><sipdomain> (this is the external Autodiscover Service URL).</span></span> <span data-ttu-id="b7686-298">Теперь при создании правила для внешних Web Services URL-адреса в пуле переднего плана, необходимо ввести полное доменное имя для внешних веб-служб в пуле переднего плана (например, lyncwebextpool01.contoso.com).</span><span class="sxs-lookup"><span data-stu-id="b7686-298">Now, if you're creating a rule for the external Web Services URL on the Front End pool, you'll need to type the FQDN for the external Web Services on your Front End pool (for example, lyncwebextpool01.contoso.com).</span></span>
    
   - <span data-ttu-id="b7686-299">Параметр **путь** будет и вам потребуется ввести \*\* / \*\*\* здесь.</span><span class="sxs-lookup"><span data-stu-id="b7686-299">There will be a **Path** option, and you'll need to enter **/\\**\* here.</span></span>
    
   - <span data-ttu-id="b7686-300">Выберите **прослушиватель SSL** с актуальным общим сертификатом.</span><span class="sxs-lookup"><span data-stu-id="b7686-300">You'll need to select a **SSL Listener** with your up-to-date public certificate.</span></span>
    
   - <span data-ttu-id="b7686-301">**Делегирование проверки подлинности** — выберите **Без делегирования**, но **разрешите** прямую проверку подлинности клиента.</span><span class="sxs-lookup"><span data-stu-id="b7686-301">**Authentication Delegation** should be set to **No delegation**, but direct client authentication **should** be allowed.</span></span>
    
   - <span data-ttu-id="b7686-302">Настройте применение правила ко **всем пользователям**.</span><span class="sxs-lookup"><span data-stu-id="b7686-302">The rule should be set to **All users**.</span></span>
    
   - <span data-ttu-id="b7686-303">На этом этапе должна быть введена вся необходимая информация.</span><span class="sxs-lookup"><span data-stu-id="b7686-303">This should be all the information you need to create this rule and allow you to proceed.</span></span>
    
4. <span data-ttu-id="b7686-304">Далее необходимо убедиться, что выполняется пересылка **исходного заголовка узла**.</span><span class="sxs-lookup"><span data-stu-id="b7686-304">You're going to need to ensure that the **original host header** is forwarded.</span></span>
    
5. <span data-ttu-id="b7686-305">Кроме того, требуется задать порты **веб-сервера** следующим образом:</span><span class="sxs-lookup"><span data-stu-id="b7686-305">The **Web Server** ports will need to be set as well, you'll need to do the following:</span></span>
    
   - <span data-ttu-id="b7686-306">**Перенаправлять запросы на HTTP-порт** — укажите порт **8080**.</span><span class="sxs-lookup"><span data-stu-id="b7686-306">**Redirect requests to HTTP port** and the port number should be **8080**.</span></span>
    
   - <span data-ttu-id="b7686-307">**Перенаправлять запросы на SSL-порт** — укажите порт **4443**.</span><span class="sxs-lookup"><span data-stu-id="b7686-307">**Redirect requests to SSL port** and the port number should be **4443**.</span></span>
    
6. <span data-ttu-id="b7686-308">По завершении настройки сохраните и примените изменения, после чего протестируйте правило.</span><span class="sxs-lookup"><span data-stu-id="b7686-308">When everything's configured, you'll need to save or apply these, and then you'll want to test the rule.</span></span>
    
### <a name="create-a-web-publishing-rule-for-port-80-optional"></a><span data-ttu-id="b7686-309">Создание правила веб-публикации для порта 80 (опционально)</span><span class="sxs-lookup"><span data-stu-id="b7686-309">Create a web publishing rule for port 80 (Optional)</span></span>

1. <span data-ttu-id="b7686-310">Откройте интерфейс обратного прокси-сервера.</span><span class="sxs-lookup"><span data-stu-id="b7686-310">Open your Reverse proxy interface.</span></span>
    
2. <span data-ttu-id="b7686-311">Вам потребуется найдите которых в интерфейсе создания вашего правила веб-публикации и выберите пункт **New** или **Создать** (возможно, в меню или вкладки, в зависимости от конфигурации обратного прокси-сервера).</span><span class="sxs-lookup"><span data-stu-id="b7686-311">You'll need to locate where in the interface you create your web publishing rules, and choose the **New** or **Create** option (it may be on a menu or tab, depending on your Reverse proxy configuration).</span></span> <span data-ttu-id="b7686-312">You are looking for the option to create a new web publishing rule.</span><span class="sxs-lookup"><span data-stu-id="b7686-312">You are looking for the option to create a new web publishing rule.</span></span>
    
3. <span data-ttu-id="b7686-313">Как правило, требуется ввести следующие данные:</span><span class="sxs-lookup"><span data-stu-id="b7686-313">Typically, you will need to enter the following information:</span></span>
    
   - <span data-ttu-id="b7686-314">**Имя** — имя правила.</span><span class="sxs-lookup"><span data-stu-id="b7686-314">**Name**: the name for your rule</span></span>
    
   - <span data-ttu-id="b7686-315">**Действие правила**: В этом случае правило **Разрешить** , а вы даете что-то проходить через обратный прокси-сервер.</span><span class="sxs-lookup"><span data-stu-id="b7686-315">**Rule Action**: In this case it's an **Allow** rule, you're letting something pass through your Reverse proxy.</span></span>
    
   - <span data-ttu-id="b7686-316">Правило **публикации** или выбираемый параметр (**отдельный веб-сайт или подсистема балансировки нагрузки**).</span><span class="sxs-lookup"><span data-stu-id="b7686-316">The **Publishing** rule or option you're choosing would be **single web site or load balancer**.</span></span>
    
   - <span data-ttu-id="b7686-317">Это должно быть **незащищенное подключение к опубликованным веб-серверу или ферме**.</span><span class="sxs-lookup"><span data-stu-id="b7686-317">This needs to be a **non-secured connection to connect to the published Web server or farm**.</span></span>
    
   - <span data-ttu-id="b7686-318">Вы собираетесь необходимо опубликовать путь для **Внутренней публикации**и введите полное доменное имя для **виртуальный IP-адрес** балансировщика нагрузки пула переднего плана, пример бы sfb_pool01.contoso.local.</span><span class="sxs-lookup"><span data-stu-id="b7686-318">You're going to need to publish a path for **Internal Publishing**, and enter the FQDN for the **VIP address** of your Front End pool's load balancer, an example would be sfb_pool01.contoso.local.</span></span>
    
   - <span data-ttu-id="b7686-319">Необходимо ввести \*\* / \*\*\* как путь, который требуется опубликовать, но также требуется **пересылать исходный заголовок узла**.</span><span class="sxs-lookup"><span data-stu-id="b7686-319">You should type **/\\**\* as the path to be published, but you also need to **forward the original host header**.</span></span>
    
   - <span data-ttu-id="b7686-p134">Кроме того, будет представлен параметр для ввода сведений о **публикации или внешнем имени**:</span><span class="sxs-lookup"><span data-stu-id="b7686-p134">There will be an option for **public or external name** details or information. This is the place where you'll be able to enter:</span></span>
    
   - <span data-ttu-id="b7686-322">**Принимать запросы** (должно задаваться для доменного имени).</span><span class="sxs-lookup"><span data-stu-id="b7686-322">**Accept requests**, but it should be for the domain name.</span></span>
    
   - <span data-ttu-id="b7686-323">В поле **Имя** введите **lyncdiscover.**</span><span class="sxs-lookup"><span data-stu-id="b7686-323">For the **Name**, you should enter **lyncdiscover.**</span></span> <span data-ttu-id="b7686-324"><sipdomain>(это внешний URL-адрес службы автообнаружения).</span><span class="sxs-lookup"><span data-stu-id="b7686-324"><sipdomain> (this is the external Autodiscover Service URL).</span></span>
    
   - <span data-ttu-id="b7686-325">Параметр **путь** будет и вам потребуется ввести \*\* / \*\*\* здесь.</span><span class="sxs-lookup"><span data-stu-id="b7686-325">There will be a **Path** option, and you'll need to enter **/\\**\* here.</span></span>
    
   - <span data-ttu-id="b7686-326">Вам потребуется выбрать веб-прослушиватель или разрешить обратного прокси-сервера для его создания.</span><span class="sxs-lookup"><span data-stu-id="b7686-326">You'll need to select a web listener, or allow your Reverse proxy to create one for you.</span></span>
    
   - <span data-ttu-id="b7686-327">**Делегирование проверки подлинности** — выберите **Без делегирования**, но **запретите** прямую проверку подлинности клиента.</span><span class="sxs-lookup"><span data-stu-id="b7686-327">**Authentication Delegation** should be set to **No delegation**, but direct client authentication **should not** be allowed.</span></span>
    
   - <span data-ttu-id="b7686-328">Настройте применение правила ко **всем пользователям**.</span><span class="sxs-lookup"><span data-stu-id="b7686-328">The rule should be set to **All users**.</span></span>
    
   - <span data-ttu-id="b7686-329">На этом этапе должна быть введена вся необходимая информация.</span><span class="sxs-lookup"><span data-stu-id="b7686-329">This should be all the information you need to create this rule and allow you to proceed.</span></span>
    
4. <span data-ttu-id="b7686-330">Требуется также задать порты **веб-сервера** следующим образом:</span><span class="sxs-lookup"><span data-stu-id="b7686-330">The **Web Server** ports will need to be set, you'll need to do the following:</span></span>
    
   - <span data-ttu-id="b7686-331">**Перенаправлять запросы на HTTP-порт** — укажите порт **8080**.</span><span class="sxs-lookup"><span data-stu-id="b7686-331">**Redirect requests to HTTP port** and the port number should be **8080**.</span></span>
    
   - <span data-ttu-id="b7686-332">**Перенаправлять запросы на SSL-порт** — укажите порт **4443**.</span><span class="sxs-lookup"><span data-stu-id="b7686-332">**Redirect requests to SSL port** and the port number should be **4443**.</span></span>
    
5. <span data-ttu-id="b7686-333">По завершении настройки сохраните и примените изменения, после чего протестируйте правило.</span><span class="sxs-lookup"><span data-stu-id="b7686-333">When everything's configured, you'll need to save or apply these, and then you'll want to test the rule.</span></span>
    
## <a name="configure-autodiscover-for-mobility-with-hybrid-deployments"></a><span data-ttu-id="b7686-334">Настройка службы автообнаружения для мобильной работы с гибридными развертываниями</span><span class="sxs-lookup"><span data-stu-id="b7686-334">Configure Autodiscover for Mobility with hybrid deployments</span></span>
<span data-ttu-id="b7686-335"><a name="ConfigAutoD"> </a></span><span class="sxs-lookup"><span data-stu-id="b7686-335"></span></span>

<span data-ttu-id="b7686-336">Гибридные среды в Скайп для Business Server являются среды, в которых объединить локальный и O365 среды.</span><span class="sxs-lookup"><span data-stu-id="b7686-336">Hybrid environments in Skype for Business Server are environments that combine an on-premises and O365 environment.</span></span> <span data-ttu-id="b7686-337">При наличии Скайп для работы в гибридной среде Business Server службы автообнаружения должен иметь возможность найти пользователя с помощью одной из следующих сред.</span><span class="sxs-lookup"><span data-stu-id="b7686-337">When you have Skype for Business Server working in a Hybrid environment, the Autodiscover service needs to be able to locate a user from either of these environments.</span></span>
  
<span data-ttu-id="b7686-p137">Чтобы мобильный клиенты могли определять местоположение пользователя, необходимо настроить новый URL-адрес для службы автообнаружения. Для этого требуется выполнить следующие действия:</span><span class="sxs-lookup"><span data-stu-id="b7686-p137">To let mobile clients discover where a user's located, the Autodiscover service needs to be configured with a new uniform resource locator (URL). The steps are:</span></span>
  
1. <span data-ttu-id="b7686-340">Откройте Скайп для консоли Business Server.</span><span class="sxs-lookup"><span data-stu-id="b7686-340">Open Skype for Business Server Management Shell.</span></span>
    
2. <span data-ttu-id="b7686-341">Выполните следующие действия, чтобы получить значение атрибута **ProxyFQDN** для вашей Скайп среды Business Server.</span><span class="sxs-lookup"><span data-stu-id="b7686-341">Run the following to get the value of the attribute **ProxyFQDN** for your Skype for Business Server environment:</span></span>
    
   ```
   Get-CsHostingProvider
   ```

3. <span data-ttu-id="b7686-342">Затем, не закрывая окно оболочки, выполните следующий командлет:</span><span class="sxs-lookup"><span data-stu-id="b7686-342">Then, still in the shell window, run:</span></span>
    
   ```
   Set-CsHostingProvider -Identity [identity] -AutodiscoverUrl https://webdir.online.lync.com/autodiscover/autodiscoverservice.svc/root
   ```

    <span data-ttu-id="b7686-343">Где [идентификатор] заменяется именем домена общего пространства адресов SIP.</span><span class="sxs-lookup"><span data-stu-id="b7686-343">Where [identity] is replaced with the domain name of the shared SIP address space.</span></span>
    
## <a name="test-your-mobility-deployment"></a><span data-ttu-id="b7686-344">Тестирование развертывания мобильности</span><span class="sxs-lookup"><span data-stu-id="b7686-344">Test your Mobility deployment</span></span>
<span data-ttu-id="b7686-345"><a name="TestMobility"> </a></span><span class="sxs-lookup"><span data-stu-id="b7686-345"></span></span>

<span data-ttu-id="b7686-346">После развертывания Скайп для службы Mobility Business Server и Скайп для службы автообнаружения Business Server, может потребоваться для запуска транзакции test, чтобы убедитесь, что работа развертывания вправо.</span><span class="sxs-lookup"><span data-stu-id="b7686-346">Once you've deployed Skype for Business Server Mobility Service and Skype for Business Server Autodiscover Service, you'll want to run a test transaction, to make sure your deployment's working right.</span></span> <span data-ttu-id="b7686-347">Выполните команду **Test-CsUcwaConference**, чтобы проверить возможность создания конференции двумя пользователями, присоединения к ней и общения.</span><span class="sxs-lookup"><span data-stu-id="b7686-347">You can run **Test-CsUcwaConference** to test the ability of two users to create, join and communicate in a conference.</span></span> <span data-ttu-id="b7686-348">Для этого вам потребуются два реальных или тестовых пользователя с полными учетными данными.</span><span class="sxs-lookup"><span data-stu-id="b7686-348">You will need two users (real or test) and their full credentials to do this testing.</span></span> <span data-ttu-id="b7686-349">Эта команда будет работать для обоих Скайп для пользователей, а также клиенты Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b7686-349">This command will work for both Skype for Business clients as well as Lync Server 2013 clients.</span></span>
  
<span data-ttu-id="b7686-350">Для клиентов Lync Server 2010 на Скайп для Business Server 2015 вам потребуются для запуска **Test-CsMcxP2PIM** , чтобы протестировать.</span><span class="sxs-lookup"><span data-stu-id="b7686-350">For Lync Server 2010 clients on Skype for Business Server 2015, you'll need to run **Test-CsMcxP2PIM** to test.</span></span> <span data-ttu-id="b7686-351">Lync Server 2010 пользователи по-прежнему необходимо будет реальных пользователей или предварительно заданных тестовых пользователей, а вам потребуются их учетных данных пароль.</span><span class="sxs-lookup"><span data-stu-id="b7686-351">Your Lync Server 2010 users will still have to be actual users, or predefined test users, and you'll need their password credentials.</span></span>

> [!NOTE]
> <span data-ttu-id="b7686-352">Поддержка устаревших мобильных клиентов MCX (Mobility Service) больше не доступен в Скайп для Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="b7686-352">MCX (Mobility Service) support for legacy mobile clients is no longer available in Skype for Business Server 2019.</span></span> <span data-ttu-id="b7686-353">Все текущей Скайп для мобильных клиентов Business уже используете Unified Communications Web API (UCWA) для поддержки мгновенного обмена Мгновенными сообщениями, сведения о присутствии и контакты.</span><span class="sxs-lookup"><span data-stu-id="b7686-353">All current Skype for Business mobile clients already use Unified Communications Web API (UCWA) to support instant messaging (IM), presence, and contacts.</span></span> <span data-ttu-id="b7686-354">Пользователи с прежних версий клиентов, использующих MCX потребуется обновить до текущего клиента.</span><span class="sxs-lookup"><span data-stu-id="b7686-354">Users with legacy clients using MCX will need to upgrade to a current client.</span></span>
  
### <a name="test-conferencing-for-skype-for-business-and-lync-2013-mobile-clients"></a><span data-ttu-id="b7686-355">Тестирование конференц-связи для мобильных клиентов Skype для бизнеса и Lync 2013</span><span class="sxs-lookup"><span data-stu-id="b7686-355">Test conferencing for Skype for Business and Lync 2013 mobile clients</span></span>

1. <span data-ttu-id="b7686-356">Выполните вход как член роли **CsAdministrator** на любой компьютер, где установлена **Скайп для консоли Business Server** и **Ocscore** .</span><span class="sxs-lookup"><span data-stu-id="b7686-356">Log on as a member of the **CsAdministrator** role on any computer where **Skype for Business Server Management Shell** and **Ocscore** are installed.</span></span>
    
2. <span data-ttu-id="b7686-357">Запустите **Скайп для консоли Business Server** (может введите имя в поле поиска или перейти на **Все программы** и выберите ее).</span><span class="sxs-lookup"><span data-stu-id="b7686-357">Start the **Skype for Business Server Management Shell** (you might type the name in search or go to **All Programs** and choose it).</span></span>
    
3. <span data-ttu-id="b7686-358">В командной строке введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="b7686-358">At the command line, enter:</span></span>
    
   ```
   Test-CsUcwaConference -TargetFqdn <FQDN of Front End pool> -Authentication <TrustedServer | Negotiate | ClientCertificate | LiveID> -OrganizerSipAddress sip:<SIP address of test user 1> -OrganizerCredential <test user 1 credentials> -ParticipantSipAddress sip:<SIP address of test user 2> -ParticipantCredential <test user 2 credentials> -v
   ```

   <span data-ttu-id="b7686-p141">Кроме того, можно задать учетные данные в скрипте и передать их в тестовый командлет (см. пример ниже).</span><span class="sxs-lookup"><span data-stu-id="b7686-p141">It's also possible to set credentials in a script and pass them to the test cmdlet. We have an example of this below.</span></span>
    
   ```
   $passwd1 = ConvertTo-SecureString "Password01" -AsPlainText -Force
   $passwd2 = ConvertTo-SecureString "Password02" -AsPlainText -Force
   $testuser1 = New-Object Management.Automation.PSCredential("contoso\UserName1", $passwd1)
   $testuser2 = New-Object Management.Automation.PSCredential("contoso\UserName2", $passwd2)
   Test-CsUcwaConference -TargetFqdn pool01.contoso.com -Authentication Negotiate -OrganizerSipAddress sip:UserName1@contoso.com -OrganizerCredential $testuser1 -ParticipantSipAddress sip:UserName2@contoso.com -ParticipantCredential $testuser2 -v
   ```

### <a name="test-conferencing-for-lync-2010-mobile-clients"></a><span data-ttu-id="b7686-361">Тестирование конференц-связи для мобильных клиентов Lync 2010</span><span class="sxs-lookup"><span data-stu-id="b7686-361">Test conferencing for Lync 2010 mobile clients</span></span>

> [!NOTE]
> <span data-ttu-id="b7686-362">Поддержка устаревших мобильных клиентов MCX (Mobility Service) больше не доступен в Скайп для Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="b7686-362">MCX (Mobility Service) support for legacy mobile clients is no longer available in Skype for Business Server 2019.</span></span> <span data-ttu-id="b7686-363">Все текущей Скайп для мобильных клиентов Business уже используете Unified Communications Web API (UCWA) для поддержки мгновенного обмена Мгновенными сообщениями, сведения о присутствии и контакты.</span><span class="sxs-lookup"><span data-stu-id="b7686-363">All current Skype for Business mobile clients already use Unified Communications Web API (UCWA) to support instant messaging (IM), presence, and contacts.</span></span> <span data-ttu-id="b7686-364">Пользователи с прежних версий клиентов, использующих MCX потребуется обновить до текущего клиента.</span><span class="sxs-lookup"><span data-stu-id="b7686-364">Users with legacy clients using MCX will need to upgrade to a current client.</span></span>

1. <span data-ttu-id="b7686-365">Выполните вход как член роли **CsAdministrator** на любой компьютер, где установлена **Скайп для консоли Business Server** и **Ocscore** .</span><span class="sxs-lookup"><span data-stu-id="b7686-365">Log on as a member of the **CsAdministrator** role on any computer where **Skype for Business Server Management Shell** and **Ocscore** are installed.</span></span>
    
2. <span data-ttu-id="b7686-366">Запустите **Скайп для консоли Business Server** (может введите имя в поле поиска или перейти на **Все программы** и выберите ее).</span><span class="sxs-lookup"><span data-stu-id="b7686-366">Start the **Skype for Business Server Management Shell** (you might type the name in search or go to **All Programs** and choose it).</span></span>
    
3. <span data-ttu-id="b7686-367">В командной строке введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="b7686-367">At the command line, enter:</span></span>
    
   ```
   Test-CsMcxP2PIM -TargetFqdn <FQDN of Front End pool> -Authentication <TrustedServer | Negotiate | ClientCertificate | LiveID> -SenderSipAddress sip:<SIP address of test user 1> -SenderCredential <test user 1 credentials> -ReceiverSipAddress sip:<SIP address of test user 2> -ReceiverCredential <test user 2 credentials> -v
   ```

   <span data-ttu-id="b7686-p143">Кроме того, можно задать учетные данные в скрипте и передать их в тестовый командлет (см. пример ниже).</span><span class="sxs-lookup"><span data-stu-id="b7686-p143">It's also possible to set credentials in a script and pass them to the test cmdlet. We have an example of this below.</span></span>
    
   ```
   $passwd1 = ConvertTo-SecureString "Password01" -AsPlainText -Force
   $passwd2 = ConvertTo-SecureString "Password02" -AsPlainText -Force
   $tuc1 = New-Object Management.Automation.PSCredential("contoso\UserName1", $passwd1)
   $tuc2 = New-Object Management.Automation.PSCredential("contoso\UserName2", $passwd2)
   Test-CsMcxP2PIM -TargetFqdn pool01.contoso.com -Authentication Negotiate -SenderSipAddress sip:UserName1@contoso.com -SenderCredential $tuc1 -ReceiverSipAddress sip:UserName2@contoso.com -ReceiverCredential $tuc2 -v
   ```

<span data-ttu-id="b7686-370">Дополнительные сведения см. в разделах, посвященных командлетам [Test-CsUcwaConference](https://docs.microsoft.com/powershell/module/skype/test-csucwaconference?view=skype-ps) и [Test-CsMcxP2PIM](https://docs.microsoft.com/powershell/module/skype/test-csmcxp2pim?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="b7686-370">To review the command procedures further, you can check out [Test-CsUcwaConference](https://docs.microsoft.com/powershell/module/skype/test-csucwaconference?view=skype-ps) and [Test-CsMcxP2PIM](https://docs.microsoft.com/powershell/module/skype/test-csmcxp2pim?view=skype-ps).</span></span>
  
## <a name="configure-for-push-notifications"></a><span data-ttu-id="b7686-371">Настройка для использования push-уведомлений</span><span class="sxs-lookup"><span data-stu-id="b7686-371">Configure for push notifications</span></span>
<span data-ttu-id="b7686-372"><a name="ConfigPush"> </a></span><span class="sxs-lookup"><span data-stu-id="b7686-372"></span></span>

<span data-ttu-id="b7686-373">Push notifications, in the form of badges, icons, or alerts, can be sent to a mobile device even when the Skype or Lync app is inactive.</span><span class="sxs-lookup"><span data-stu-id="b7686-373">Push notifications, in the form of badges, icons, or alerts, can be sent to a mobile device even when the Skype or Lync app is inactive.</span></span> <span data-ttu-id="b7686-374">But what are pusn notifications?</span><span class="sxs-lookup"><span data-stu-id="b7686-374">But what are pusn notifications?</span></span> <span data-ttu-id="b7686-375">They are event alerts, like a new or missed IM invitation, or for a received voicemail.</span><span class="sxs-lookup"><span data-stu-id="b7686-375">They are event alerts, like a new or missed IM invitation, or for a received voicemail.</span></span> <span data-ttu-id="b7686-376">Скайп для службы Business Server Mobility отправляет такие уведомления Скайп облачной для Business Server службы Push-уведомлений, который отправляет уведомления для Microsoft Push-уведомлений службы (MSNS) для пользователей Windows Phone.</span><span class="sxs-lookup"><span data-stu-id="b7686-376">The Skype for Business Server Mobility service sends these notifications to the cloud-based Skype for Business Server Push Notification Service, which then sends the notifications to the Microsoft Push Notification Service (MSNS) for Windows Phone users.</span></span>
  
<span data-ttu-id="b7686-377">Данная функциональная возможность не изменяется с Lync Server 2013, но при наличии Скайп для Business Server, необходимо выполнить следующие:</span><span class="sxs-lookup"><span data-stu-id="b7686-377">This functionality is unchanged from Lync Server 2013, but if you have a Skype for Business Server, you'll want to do the following:</span></span>
  
- <span data-ttu-id="b7686-378">Для Скайп для пограничного сервера Business Server добавить нового поставщика услуг размещения Скайп Майкрософт для бизнеса в Интернет, а затем настроить федерацию между вашей организацией и Скайп для бизнеса в Интернет для поставщиков услуг размещения.</span><span class="sxs-lookup"><span data-stu-id="b7686-378">For a Skype for Business Server Edge Server, add a new hosting provider, Microsoft Skype for Business Online, and then set up hosting provider federation between your organization and Skype for Business Online.</span></span>
    
- <span data-ttu-id="b7686-p145">Включите push-уведомления с помощью командлета **Set-CsPushNotificationConfiguration**. По умолчанию push-уведомления отключены.</span><span class="sxs-lookup"><span data-stu-id="b7686-p145">Enable push notifications by running the **Set-CsPushNotificationConfiguration** cmdlet. By default, push notifications are turned off.</span></span>
    
- <span data-ttu-id="b7686-381">Протестируйте конфигурацию федерации и push-уведомлений.</span><span class="sxs-lookup"><span data-stu-id="b7686-381">Test your federation configuration and push notifications.</span></span>
    
### <a name="configure-your-skype-for-business-edge-server-for-push-notifications"></a><span data-ttu-id="b7686-382">Настройка пограничного сервера Skype для бизнеса для использования push-уведомлений</span><span class="sxs-lookup"><span data-stu-id="b7686-382">Configure your Skype for Business Edge Server for push notifications</span></span>

1. <span data-ttu-id="b7686-383">Выполните вход, если учетная запись не должна быть членом роли **CsAdministrator** на компьютер, где установлены **Скайп для консоли Business Server** и **Ocscore** .</span><span class="sxs-lookup"><span data-stu-id="b7686-383">Log on, with an account that's a member of the **CsAdministrator** role, to a computer where **Skype for Business Server Management Shell** and **Ocscore** are installed.</span></span>
    
2. <span data-ttu-id="b7686-384">Запустите **Скайп для консоли Business Server**.</span><span class="sxs-lookup"><span data-stu-id="b7686-384">Start the **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="b7686-385">Добавление Скайп для сети поставщика услуг размещения Business Server.</span><span class="sxs-lookup"><span data-stu-id="b7686-385">Add a Skype for Business Server online hosting provider.</span></span>
    
   ```
   New-CsHostingProvider -Identity <unique identifier for hosting provider> -Enabled $True -ProxyFQDN <FQDN for the Access Server used by the hosting provider> -VerificationLevel UseSourceVerification
   ```

   <span data-ttu-id="b7686-386">Пример:</span><span class="sxs-lookup"><span data-stu-id="b7686-386">As an example:</span></span>
    
   ```
   New-CsHostingProvider -Identity "SkypeOnline" -Enabled $True -ProxyFQDN "sipfed.online.lync.com" -VerificationLevel UseSourceVerification
   ```

    > [!NOTE]
    > <span data-ttu-id="b7686-p146">Нельзя настраивать несколько отношений федерации с одним поставщиком услуг размещения. То есть, настроив поставщик услуг размещения, имеющий отношения федерации с sipfed.online.lync.com, не добавляйте для этого сайта другой поставщик услуг размещения, даже если удостоверение поставщика отличается от SkypeOnline.</span><span class="sxs-lookup"><span data-stu-id="b7686-p146">You can't have more than one federation relationship with a single hosting provider. So, if you've already set up a hosting provider that has a federation relationship with sipfed.online.lync.com, don't add another hosting provider for it, even if the identity of the hosting provider is something other than SkypeOnline.</span></span> 
  
4. <span data-ttu-id="b7686-389">Настройте федерацию поставщика услуг размещения между вашей организацией и службы Push-уведомлений в Скайп для бизнеса в Интернет.</span><span class="sxs-lookup"><span data-stu-id="b7686-389">Set up the hosting provider federation between your organization and the Push Notification Service at Skype for Business Online.</span></span> <span data-ttu-id="b7686-390">В командной строке введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="b7686-390">At the command line, you'll need to type:</span></span>
    
   ```
    New-CsAllowedDomain -Identity "push.lync.com"
   ```

### <a name="enable-push-notifications"></a><span data-ttu-id="b7686-391">Включение push-уведомлений</span><span class="sxs-lookup"><span data-stu-id="b7686-391">Enable push notifications</span></span>

1. <span data-ttu-id="b7686-392">Выполните вход, если учетная запись не должна быть членом роли **CsAdministrator** на компьютер, где установлены **Скайп для консоли Business Server** и **Ocscore** .</span><span class="sxs-lookup"><span data-stu-id="b7686-392">Log on, with an account that's a member of the **CsAdministrator** role, to a computer where **Skype for Business Server Management Shell** and **Ocscore** are installed.</span></span>
    
2. <span data-ttu-id="b7686-393">Запустите **Скайп для консоли Business Server**.</span><span class="sxs-lookup"><span data-stu-id="b7686-393">Start the **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="b7686-394">Включите push-уведомления:</span><span class="sxs-lookup"><span data-stu-id="b7686-394">Enable push notifications:</span></span>
    
   ```
   Set-CsPushNotificationConfiguration -EnableMicrosoftPushNotificationService $True
   ```

4. <span data-ttu-id="b7686-395">Включите федерацию:</span><span class="sxs-lookup"><span data-stu-id="b7686-395">Enable Federation:</span></span>
     
   ```
   Set-CsAccessEdgeConfiguration -AllowFederatedUsers $True
   ```

### <a name="test-federation-and-push-notifications"></a><span data-ttu-id="b7686-396">Тестирование федерации и push-уведомлений</span><span class="sxs-lookup"><span data-stu-id="b7686-396">Test federation and push notifications</span></span>

1. <span data-ttu-id="b7686-397">Выполните вход, если учетная запись не должна быть членом роли **CsAdministrator** на компьютер, где установлены **Скайп для консоли Business Server** и **Ocscore** .</span><span class="sxs-lookup"><span data-stu-id="b7686-397">Log on, with an account that's a member of the **CsAdministrator** role, to a computer where **Skype for Business Server Management Shell** and **Ocscore** are installed.</span></span>
    
2. <span data-ttu-id="b7686-398">Запустите **Скайп для консоли Business Server**.</span><span class="sxs-lookup"><span data-stu-id="b7686-398">Start the **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="b7686-399">Проверьте конфигурацию федерации:</span><span class="sxs-lookup"><span data-stu-id="b7686-399">Test the federation configuration:</span></span>
    
   ```
   Test-CsFederatedPartner -TargetFqdn <FQDN of Access Edge server used for federated SIP traffic> -Domain <FQDN of federated domain> -ProxyFqdn <FQDN of the Access Edge server used by the federated organization>
   ```

    <span data-ttu-id="b7686-400">Пример:</span><span class="sxs-lookup"><span data-stu-id="b7686-400">As an example:</span></span>
    
   ```
   Test-CsFederatedPartner -TargetFqdn accessproxy.contoso.com -Domain push.lync.com -ProxyFqdn sipfed.online.lync.com
   ```

4. <span data-ttu-id="b7686-401">Протестируйте push-уведомления:</span><span class="sxs-lookup"><span data-stu-id="b7686-401">Test your push notifications:</span></span>
    
   ```
   Test-CsMcxPushNotification -AccessEdgeFqdn <Access Edge service FQDN>
   ```

    <span data-ttu-id="b7686-402">Пример:</span><span class="sxs-lookup"><span data-stu-id="b7686-402">As an example:</span></span>
    
   ```
   Test-CsMcxPushNotification -AccessEdgeFqdn accessproxy.contoso.com
   ```

## <a name="configure-mobility-policy"></a><span data-ttu-id="b7686-403">Настройка политики мобильности</span><span class="sxs-lookup"><span data-stu-id="b7686-403">Configure Mobility policy</span></span>
<span data-ttu-id="b7686-404"><a name="ConfigMob"> </a></span><span class="sxs-lookup"><span data-stu-id="b7686-404"></span></span>

<span data-ttu-id="b7686-405">У вас есть возможность с Скайп Business Server определить, кто может использовать Mobility service, звонок через работу, передачи голоса по протоколу IP (VoIP), или видео, а также будет ли необходимые для VoIP или видео WiFi.</span><span class="sxs-lookup"><span data-stu-id="b7686-405">You have the ability with Skype for Business Server to determine who can use your Mobility service, Call via Work, voice over IP (VoIP), or video, as well as whether WiFi will be required for VoIP or video.</span></span> <span data-ttu-id="b7686-406">Call via Work lets a mobile user use their work phone number, instead of their mobile phone number, when placing and receiving calls.</span><span class="sxs-lookup"><span data-stu-id="b7686-406">Call via Work lets a mobile user use their work phone number, instead of their mobile phone number, when placing and receiving calls.</span></span> <span data-ttu-id="b7686-407">The person on the other end of the line won't see that mobile user's cell phone number, and it lets that mobile user avoid outgoing call charges.</span><span class="sxs-lookup"><span data-stu-id="b7686-407">The person on the other end of the line won't see that mobile user's cell phone number, and it lets that mobile user avoid outgoing call charges.</span></span> <span data-ttu-id="b7686-408">When VoIP and video are set up, users can take and make VoIP calls and video.</span><span class="sxs-lookup"><span data-stu-id="b7686-408">When VoIP and video are set up, users can take and make VoIP calls and video.</span></span> <span data-ttu-id="b7686-409">The settings for WiFi usage determine whether a user's mobile device will be required to use a WiFi network over a cellular data network.</span><span class="sxs-lookup"><span data-stu-id="b7686-409">The settings for WiFi usage determine whether a user's mobile device will be required to use a WiFi network over a cellular data network.</span></span>
  
<span data-ttu-id="b7686-410">Мобильность, позвонить с рабочего, VoIP и функции видео включены по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="b7686-410">Mobility, Call via Work, and the VoIP and video features are all enabled by default.</span></span> <span data-ttu-id="b7686-411">Параметры запроса на использование сети Wi-Fi для протокола VoIP и видеосвязи отключены.</span><span class="sxs-lookup"><span data-stu-id="b7686-411">The setting to require WiFi for VoIP and video are disabled.</span></span> <span data-ttu-id="b7686-412">Администратор может изменять эти настройки глобально, а также на уровне сайта или пользователя.</span><span class="sxs-lookup"><span data-stu-id="b7686-412">An Admin has the ability to change this, either globally, by site, or by user.</span></span>
  
<span data-ttu-id="b7686-413">Должны иметь возможность использовать функции мобильности и вызов с рабочего, пользователи должны быть:</span><span class="sxs-lookup"><span data-stu-id="b7686-413">To be able to use Mobility features and Call via Work, users need to be:</span></span>
  
- <span data-ttu-id="b7686-414">Включена поддержка Скайп для Business Server</span><span class="sxs-lookup"><span data-stu-id="b7686-414">Enabled for Skype for Business Server</span></span>
    
- <span data-ttu-id="b7686-415">Активированы для корпоративной голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="b7686-415">Enabled for Enterprise Voice.</span></span>
    
- <span data-ttu-id="b7686-416">Назначить политику мобильности, которая имеет значение **True**для параметра **EnableMobility** .</span><span class="sxs-lookup"><span data-stu-id="b7686-416">Assigned a Mobility policy that has the **EnableMobility** option set to **True**.</span></span>
    
<span data-ttu-id="b7686-417">Чтобы использовать функцию "Позвонить с рабочего", пользователи должны отвечать следующим требованиям:</span><span class="sxs-lookup"><span data-stu-id="b7686-417">For users to be able to use Call via Work, they'll also need to be:</span></span>
  
- <span data-ttu-id="b7686-418">Иметь назначенную политику голосовой связи с выбранной функцией  **Разрешить одновременный звонок на несколько телефонов**.</span><span class="sxs-lookup"><span data-stu-id="b7686-418">Assigned a voice policy that has the **Enable simultaneous ringing of phones** option selected.</span></span>
    
- <span data-ttu-id="b7686-419">Назначить политику мобильности с **EnableOutsideVoice** присвоено **значение True**.</span><span class="sxs-lookup"><span data-stu-id="b7686-419">Assigned a Mobility policy that has the **EnableOutsideVoice** set to **True**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="b7686-p150">Пользователи, для которых не включена поддержка системы корпоративной голосовой связи, могут использовать мобильные устройства для выполнения звонков Skype–Skype по протоколу VoIP или могут присоединиться к конференциям с помощью ссылки "Щелкните для присоединения" на мобильном устройстве, если вы назначили этим пользователям соответствующие возможности в политике голосовой связи. Дополнительные сведения см. в разделе "Планирование".</span><span class="sxs-lookup"><span data-stu-id="b7686-p150">Users who aren't enabled for Enterprise Voice can use their mobile devices to make Skype to Skype VoIP calls or can join conferences by using the Click to Join link while on their mobile devices, if the appropriate options are set for the Voice policy they're associated with. There's more detail in the PLANNING topic.</span></span> 
  
### <a name="modify-global-mobility-policy"></a><span data-ttu-id="b7686-422">Изменение глобальной политики мобильности</span><span class="sxs-lookup"><span data-stu-id="b7686-422">Modify global Mobility policy</span></span>

1. <span data-ttu-id="b7686-423">Выполните вход, если учетная запись не должна быть членом роли **CsAdministrator** на компьютер, где установлены **Скайп для консоли Business Server** и **Ocscore** .</span><span class="sxs-lookup"><span data-stu-id="b7686-423">Log on, with an account that's a member of the **CsAdministrator** role, to a computer where **Skype for Business Server Management Shell** and **Ocscore** are installed.</span></span>
    
2. <span data-ttu-id="b7686-424">Запустите **Скайп для консоли Business Server**.</span><span class="sxs-lookup"><span data-stu-id="b7686-424">Start the **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="b7686-425">Глобально отключение доступа для мобильных устройств и позвонить с рабочего с помощью следующей команды:</span><span class="sxs-lookup"><span data-stu-id="b7686-425">Turn off access to Mobility and Call via Work globally by typing:</span></span>
    
   ```
   Set-CsMobilityPolicy -EnableMobility $False -EnableOutsideVoice $False
   ```

    > [!NOTE]
    > <span data-ttu-id="b7686-426">Можно отключить позвонить с рабочего без отключения доступа для мобильных устройств.</span><span class="sxs-lookup"><span data-stu-id="b7686-426">You can turn off Call via Work without turning off access to Mobility.</span></span> <span data-ttu-id="b7686-427">Однако нельзя отключить мобильности без также отключение позвонить с рабочего.</span><span class="sxs-lookup"><span data-stu-id="b7686-427">But you can't turn off Mobility without also turning off Call via Work.</span></span> 
  
    <span data-ttu-id="b7686-428">Дополнительные сведения о Извлеките [Set-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/set-csmobilitypolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="b7686-428">For more info, check out [Set-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/set-csmobilitypolicy?view=skype-ps).</span></span>
    
### <a name="modify-mobility-policy-by-site"></a><span data-ttu-id="b7686-429">Изменение мобильной политики на сайт</span><span class="sxs-lookup"><span data-stu-id="b7686-429">Modify Mobility policy by site</span></span>

1. <span data-ttu-id="b7686-430">Выполните вход, если учетная запись не должна быть членом роли **CsAdministrator** на компьютер, где установлены **Скайп для консоли Business Server** и **Ocscore** .</span><span class="sxs-lookup"><span data-stu-id="b7686-430">Log on, with an account that's a member of the **CsAdministrator** role, to a computer where **Skype for Business Server Management Shell** and **Ocscore** are installed.</span></span>
    
2. <span data-ttu-id="b7686-431">Запустите **Скайп для консоли Business Server**.</span><span class="sxs-lookup"><span data-stu-id="b7686-431">Start the **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="b7686-p152">В можете создать политику на уровне сайта, отключить VoIP и видеосвязь и включить параметр "Запрашивать Wi-Fi для IP-аудио/видео" для отдельных сайтов. Для этого введите:</span><span class="sxs-lookup"><span data-stu-id="b7686-p152">You can create a site-level policy, turn off VoIP and video, enable Require WiFi for IP Audio, and Require WiFi for IP Video by site. Type:</span></span>
    
   ```
   New-CsMobilityPolicy -Identity site:<site identifier> -EnableIPAudioVideo $false -RequireWiFiForIPAudio $True -RequireWiFiforIPVideo $True
   ```

    <span data-ttu-id="b7686-434">Дополнительные сведения см. в статье [New-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/new-csmobilitypolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="b7686-434">Learn more at [New-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/new-csmobilitypolicy?view=skype-ps).</span></span>
    
### <a name="modify-mobility-policy-by-user"></a><span data-ttu-id="b7686-435">Изменение мобильной политики на пользователя</span><span class="sxs-lookup"><span data-stu-id="b7686-435">Modify Mobility policy by user</span></span>

1. <span data-ttu-id="b7686-436">Выполните вход, если учетная запись не должна быть членом роли **CsAdministrator** на компьютер, где установлены **Скайп для консоли Business Server** и **Ocscore** .</span><span class="sxs-lookup"><span data-stu-id="b7686-436">Log on, with an account that's a member of the **CsAdministrator** role, to a computer where **Skype for Business Server Management Shell** and **Ocscore** are installed.</span></span>
    
2. <span data-ttu-id="b7686-437">Запустите **Скайп для консоли Business Server**.</span><span class="sxs-lookup"><span data-stu-id="b7686-437">Start the **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="b7686-438">Создание политики мобильности на уровне пользователя и отключить мобильности и вызов с рабочего пользователем.</span><span class="sxs-lookup"><span data-stu-id="b7686-438">Create user level Mobility policies and turn off Mobility and Call via Work by user.</span></span> <span data-ttu-id="b7686-439">Type:</span><span class="sxs-lookup"><span data-stu-id="b7686-439">Type:</span></span>
    
   ```
   New-CsMobilityPolicy -Identity <policy name> -EnableMobility $False -EnableOutsideVoice $False
   Grant-CsMobilityPolicy -Identity <user identifier> -PolicyName <policy name>
   ```

    <span data-ttu-id="b7686-440">Дополнительный пример (используется образец данных):</span><span class="sxs-lookup"><span data-stu-id="b7686-440">A further example with sample data:</span></span>
    
   ```
   New-CsMobilityPolicy "tag:disableOutsideVoice" -EnableOutsideVoice $False
   Grant-CsMobilityPolicy -Identity MobileUser1@contoso.com -PolicyName tag:disableOutsideVoice
   ```

    > [!NOTE]
    > <span data-ttu-id="b7686-441">Можно отключить позвонить с рабочего без отключения доступа для мобильных устройств.</span><span class="sxs-lookup"><span data-stu-id="b7686-441">You can turn off Call via Work without turning off access to Mobility.</span></span> <span data-ttu-id="b7686-442">Однако нельзя отключить мобильности без также отключение позвонить с рабочего.</span><span class="sxs-lookup"><span data-stu-id="b7686-442">But you can't turn off Mobility without also turning off Call via Work.</span></span> 
  

