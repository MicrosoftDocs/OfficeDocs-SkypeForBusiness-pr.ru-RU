---
title: Настройка интеграции Cloud Connector с организацией Microsoft 365 или Office 365
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/15/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 0e2f2395-b890-4d16-aa2d-99d52438b89c
description: Узнайте, как настроить интеграцию Cloud Connector с вашей организацией Microsoft 365 или Office 365.
ms.openlocfilehash: bf5d8c4fb9684a205670701428fa8db30835a871
ms.sourcegitcommit: b424ab14683ab5080ebfd085adff7c0dbe1be84c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/03/2020
ms.locfileid: "47359075"
---
# <a name="configure-cloud-connector-integration-with-your-microsoft-365-or-office-365-organization"></a><span data-ttu-id="a43c4-103">Настройка интеграции Cloud Connector с организацией Microsoft 365 или Office 365</span><span class="sxs-lookup"><span data-stu-id="a43c4-103">Configure Cloud Connector integration with your Microsoft 365 or Office 365 organization</span></span>

> [!Important] 
> <span data-ttu-id="a43c4-104">Выпуск Cloud Connector Edition завершится 31 июля 2021 г. вместе со Skype для бизнеса Online.</span><span class="sxs-lookup"><span data-stu-id="a43c4-104">Cloud Connector Edition will retire July 31, 2021 along with Skype for Business Online.</span></span> <span data-ttu-id="a43c4-105">После обновления вашей организации до Teams узнайте, как подключить свою локальной телефонной сети к Teams с помощью [прямой маршрутизации.](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page)</span><span class="sxs-lookup"><span data-stu-id="a43c4-105">Once your organization has upgraded to Teams, learn how to connect your on-premises telephony network to Teams using [Direct Routing](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page).</span></span>

<span data-ttu-id="a43c4-106">Узнайте, как настроить интеграцию Cloud Connector с вашей организацией Microsoft 365 или Office 365.</span><span class="sxs-lookup"><span data-stu-id="a43c4-106">Learn how to configure Cloud Connector integration with your Microsoft 365 or Office 365 organization.</span></span>
  
<span data-ttu-id="a43c4-107">После завершения установки Skype для бизнеса Cloud Connector Edition выполните действия, которые необходимо выполнить в этом разделе, чтобы настроить развертывание и подключить его к организации Microsoft 365 или Office 365.</span><span class="sxs-lookup"><span data-stu-id="a43c4-107">Once the Skype for Business Cloud Connector Edition installation is complete, perform the steps in this section to configure your deployment and connect it to your Microsoft 365 or Office 365 organization.</span></span>
  
## <a name="configure-firewall-settings"></a><span data-ttu-id="a43c4-108">Настройка параметров брандмауэра</span><span class="sxs-lookup"><span data-stu-id="a43c4-108">Configure firewall settings</span></span>

<span data-ttu-id="a43c4-109">Настройте параметры брандмауэра для внутренних и внешних параметров брандмауэра [](plan-skype-for-business-cloud-connector-edition.md#BKMB_Ports) для сети периметра, чтобы открыть необходимые порты, как описано в описании портов и протоколов в plan [for Skype for Business Cloud Connector Edition.](plan-skype-for-business-cloud-connector-edition.md)</span><span class="sxs-lookup"><span data-stu-id="a43c4-109">Configure the firewall settings for your internal and external firewall settings for you perimeter network to open the required ports as described in [Ports and protocols](plan-skype-for-business-cloud-connector-edition.md#BKMB_Ports) in [Plan for Skype for Business Cloud Connector Edition](plan-skype-for-business-cloud-connector-edition.md).</span></span>
  
## <a name="set-up-public-switched-telephone-network-pstn-gateways"></a><span data-ttu-id="a43c4-110">Настройка шлюзов телефонной сети общего слева (PSTN)</span><span class="sxs-lookup"><span data-stu-id="a43c4-110">Set up Public Switched Telephone Network (PSTN) gateways</span></span>

<span data-ttu-id="a43c4-111">Установите магистрали на каждом шлюзе STN так, чтобы они возвращались на серверы-посредники для всех устройств.</span><span class="sxs-lookup"><span data-stu-id="a43c4-111">Set up trunks on each PSTN gateway to point back to Mediation Servers for all appliances.</span></span> <span data-ttu-id="a43c4-112">Поскольку FQDN пула одинаково для всех серверов в пуле, каждая магистраль должна указать на одно FQDN сервера-посредника или IP-адрес вместо пула серверов-посредников.</span><span class="sxs-lookup"><span data-stu-id="a43c4-112">Because the pool FQDN is the same for all servers in the pool, each trunk should point to one Mediation Server FQDN or IP address instead of the Mediation Server pool FQDN.</span></span> <span data-ttu-id="a43c4-113">Магистрали должны иметь одинаковый приоритет.</span><span class="sxs-lookup"><span data-stu-id="a43c4-113">Trunks should be set in the same priority.</span></span>
  
<span data-ttu-id="a43c4-114">При использовании TLS между серверами-посредниками и шлюзами необходимо настроить шлюзы и серверы-посредники для поддержки MTLS следующим образом:</span><span class="sxs-lookup"><span data-stu-id="a43c4-114">If you are using TLS between Mediation Servers and gateways, you will need to configure the gateways and Mediation Servers to support MTLS as follows:</span></span>
  
1. <span data-ttu-id="a43c4-115">Экспорт корневого ЦС с компьютера Cloud Connector Active Directory.</span><span class="sxs-lookup"><span data-stu-id="a43c4-115">Export the Root CA from the Cloud Connector Active Directory computer.</span></span>
    
2. <span data-ttu-id="a43c4-116">Следуйте инструкциям поставщика шлюза STN для импорта корневого ЦС.</span><span class="sxs-lookup"><span data-stu-id="a43c4-116">Follow the PSTN gateway vendor instructions for importing the Root CA.</span></span>
    
3. <span data-ttu-id="a43c4-117">Импортировать сертификат корневого ЦС для сертификата, выданного шлюзу на серверах-посредниках.</span><span class="sxs-lookup"><span data-stu-id="a43c4-117">Import the Root CA certificate for the certificate issued to your gateway on the Mediation Servers.</span></span> <span data-ttu-id="a43c4-118">Если вам нужно получить SSL-сертификат для шлюза, это можно сделать с помощью службы центра сертификации, запущенной на компьютере Active Directory Cloud Connector следующим образом:</span><span class="sxs-lookup"><span data-stu-id="a43c4-118">If you need to obtain an SSL certificate for the gateway, you may do this using the Certificate Authority service running on the Cloud Connector Active Directory computer as follows:</span></span>
    
   - <span data-ttu-id="a43c4-119">Измените существующий шаблон веб-сервера, чтобы включить регистрацию для пользователей, для проверки подлинности, или создайте новый шаблон веб-сервера, чтобы настроить другие свойства и включить регистрацию для пользователей, подлинность и подлинность пользователей.</span><span class="sxs-lookup"><span data-stu-id="a43c4-119">Modify the existing Web Server template to enable Authenticated users to enroll, or create a new Web Server template to configure other properties and enable Authenticated users to enroll.</span></span> <span data-ttu-id="a43c4-120">Подробные инструкции [см. в описании шаблонов сертификатов.](https://technet.microsoft.com/library/cc730705.aspx)</span><span class="sxs-lookup"><span data-stu-id="a43c4-120">For detailed instructions, see [Certificate Templates](https://technet.microsoft.com/library/cc730705.aspx).</span></span>
    
   - <span data-ttu-id="a43c4-121">Запрос сертификата с помощью оснастки "Сертификат" для выбора включенного шаблона веб-сервера.</span><span class="sxs-lookup"><span data-stu-id="a43c4-121">Request a certificate using Certificate snap-in selecting the Web Server template that you have enabled.</span></span> <span data-ttu-id="a43c4-122">Обязательно добавьте общее имя в subject и DNS-имя в альтернативном имени с FQDN шлюза и убедитесь, что в закрытом ключе выбран параметр "Сделать закрытый ключ экспортируемым".</span><span class="sxs-lookup"><span data-stu-id="a43c4-122">Be sure to add Common name in Subject and DNS name in Alternative name with FQDN of the gateway, and confirm on the Private Key that Make private key exportable is selected under key options.</span></span> 
    
4. <span data-ttu-id="a43c4-123">Экспортировать SSL-сертификат с закрытым ключом и следуйте инструкциям поставщика шлюза STN для импорта сертификата.</span><span class="sxs-lookup"><span data-stu-id="a43c4-123">Export the SSL certificate with Private key and follow the instructions from your PSTN gateway vendor for importing the certificate.</span></span>
    
## <a name="update-the-domain-for-your-tenant"></a><span data-ttu-id="a43c4-124">Обновление домена для клиента</span><span class="sxs-lookup"><span data-stu-id="a43c4-124">Update the domain for your tenant</span></span>

<span data-ttu-id="a43c4-125">Убедитесь, что вы выполнили действия по обновлению домена в Microsoft 365 или Office 365 и добавили записи DNS.</span><span class="sxs-lookup"><span data-stu-id="a43c4-125">Make sure that you've completed the steps to update your domain in Microsoft 365 or Office 365 and have the ability to add DNS records.</span></span> <span data-ttu-id="a43c4-126">Дополнительные сведения о том, как настроить домен в Microsoft 365 или Office 365, см. в подстройки "Добавление домена в [Microsoft 365" или "Office 365".](https://support.office.com/article/Add-a-domain-to-Office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611)</span><span class="sxs-lookup"><span data-stu-id="a43c4-126">For more information about how to set up your domain in Microsoft 365 or Office 365, see [Add a domain to Microsoft 365 or Office 365](https://support.office.com/article/Add-a-domain-to-Office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611).</span></span>
  
## <a name="add-dns-records-for-your-edge"></a><span data-ttu-id="a43c4-127">Добавление записей DNS для edge</span><span class="sxs-lookup"><span data-stu-id="a43c4-127">Add DNS records for your Edge</span></span>

<span data-ttu-id="a43c4-128">Добавьте следующие записи DNS в организацию Microsoft 365 или Office 365.</span><span class="sxs-lookup"><span data-stu-id="a43c4-128">Add the following DNS records to your Microsoft 365 or Office 365 organization.</span></span> <span data-ttu-id="a43c4-129">Дополнительные сведения о добавлении записей DNS см. в подстройки и редактировании пользовательских [записей DNS в Microsoft 365 или Office 365.](https://support.office.com/article/Add-or-edit-custom-DNS-records-in-Office-365-AF00A516-DD39-4EDA-AF3E-1EAF686C8DC9?ui=en-US&amp;rs=en-US&amp;ad=US&amp;fromAR=1)</span><span class="sxs-lookup"><span data-stu-id="a43c4-129">For information about how to add DNS records, see [Add or edit custom DNS records in Microsoft 365 or Office 365](https://support.office.com/article/Add-or-edit-custom-DNS-records-in-Office-365-AF00A516-DD39-4EDA-AF3E-1EAF686C8DC9?ui=en-US&amp;rs=en-US&amp;ad=US&amp;fromAR=1).</span></span>
  
1. <span data-ttu-id="a43c4-130">Добавьте запись A DNS для access Edge.</span><span class="sxs-lookup"><span data-stu-id="a43c4-130">Add a DNS A record for Access Edge.</span></span>
    
2. <span data-ttu-id="a43c4-131">Записи SRV автоматически создаются в Microsoft 365 или Office 365 и сценариях развертывания.</span><span class="sxs-lookup"><span data-stu-id="a43c4-131">SRV records will automatically be created by Microsoft 365 or Office 365 and the deployment scripts.</span></span> <span data-ttu-id="a43c4-132">Подтвердим, что на границе можно найти две службы SIP: \_ sip и \_ sipfederationtls.</span><span class="sxs-lookup"><span data-stu-id="a43c4-132">Confirm that you can look up the following two SIP services on the Edge: \_sip and \_sipfederationtls.</span></span>
    
     ![Подтверждение записей SRV](../../media/3c353a29-6dcc-4ed3-98db-3a6bed3e929e.png)
  
## <a name="set-up-hybrid-connectivity-between-cloud-connector-edition-and-microsoft-365-or-office-365"></a><span data-ttu-id="a43c4-134">Настройка гибридного подключения между Cloud Connector Edition и Microsoft 365 или Office 365</span><span class="sxs-lookup"><span data-stu-id="a43c4-134">Set up hybrid connectivity between Cloud Connector Edition and Microsoft 365 or Office 365</span></span>

<span data-ttu-id="a43c4-135">Чтобы настроить гибридное подключение между развертыванием Skype для бизнеса Cloud Connector Edition и организацией Microsoft 365 или Office 365, запустите следующий cmdlet в удаленном сеансе PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a43c4-135">To configure hybrid connectivity between your Skype for Business Cloud Connector Edition deployment and your Microsoft 365 or Office 365 organization, run the following cmdlet in a remote PowerShell session.</span></span> <span data-ttu-id="a43c4-136">Чтобы узнать, как установить удаленный сеанс PowerShell, см. в этой [Windows PowerShell.](https://technet.microsoft.com/library/dn362831%28v=ocs.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="a43c4-136">To learn how to establish a remote PowerShell session, see: [Set up your computer for Windows PowerShell](https://technet.microsoft.com/library/dn362831%28v=ocs.15%29.aspx).</span></span>
  
<span data-ttu-id="a43c4-137">Этот cmdlet задает внешнее FQDN edge доступа.</span><span class="sxs-lookup"><span data-stu-id="a43c4-137">The cmdlet sets the Access Edge external FQDN.</span></span> <span data-ttu-id="a43c4-138">В первой команде должна быть роль для роли \<External Access Edge FQDN\> SIP Access Edge.</span><span class="sxs-lookup"><span data-stu-id="a43c4-138">In the first of the commands, the \<External Access Edge FQDN\> should be the one for the SIP Access Edge role.</span></span> <span data-ttu-id="a43c4-139">По умолчанию это значение должно быть ap. \<Domain Name\> .</span><span class="sxs-lookup"><span data-stu-id="a43c4-139">By default, this should be ap.\<Domain Name\>.</span></span>
  
```powershell
Set-CsTenantHybridConfiguration -PeerDestination <External Access Edge FQDN> -UseOnPremDialPlan $false
Set-CsTenantFederationConfiguration -SharedSipAddressSpace $True
```

> [!NOTE]
> <span data-ttu-id="a43c4-140">В качестве FQDN внешнего доступа, используемого для одноранговой цели, следует установить сайт PSTN, который будет использоваться в качестве отката только в случае, если пользователь не назначен сайту STN.</span><span class="sxs-lookup"><span data-stu-id="a43c4-140">The External Access Edge FQDN used for Peer Destination should be set to a PSTN site that will only be used as a fallback in case a user isn't assigned to a PSTN site.</span></span> <span data-ttu-id="a43c4-141">Дополнительные сведения см. в сведениях о развертывании одного сайта в [Cloud Connector](deploy-a-single-site-in-cloud-connector.md) и развертывании нескольких сайтов [в Cloud Connector.](deploy-multiple-sites-in-cloud-connector.md)</span><span class="sxs-lookup"><span data-stu-id="a43c4-141">For more information, see [Deploy a single site in Cloud Connector](deploy-a-single-site-in-cloud-connector.md) and [Deploy multiple sites in Cloud Connector](deploy-multiple-sites-in-cloud-connector.md).</span></span> 
  
## <a name="set-up-pstn-gateways"></a><span data-ttu-id="a43c4-142">Настройка шлюзов STN</span><span class="sxs-lookup"><span data-stu-id="a43c4-142">Set up PSTN gateways</span></span>

<span data-ttu-id="a43c4-143">Установите магистрали на каждом шлюзе STN так, чтобы они возвращались на серверы-посредники для всех устройств.</span><span class="sxs-lookup"><span data-stu-id="a43c4-143">Set up trunks on each PSTN gateway to point back to Mediation Servers for all appliances.</span></span> <span data-ttu-id="a43c4-144">Каждая магистраль должна указать на одно FQDN сервера-посредника или IP-адрес, а не на пул серверов-посредников, поскольку это одно и то же FQDN пула для всех серверов в пуле.</span><span class="sxs-lookup"><span data-stu-id="a43c4-144">Each trunk should point to one Mediation Server FQDN or IP address instead of the Mediation Server pool FQDN because the pool FQDN is the same for all servers in the pool.</span></span> <span data-ttu-id="a43c4-145">Магистрали должны иметь одинаковый приоритет.</span><span class="sxs-lookup"><span data-stu-id="a43c4-145">Trunks should be set in the same priority.</span></span>
  
<span data-ttu-id="a43c4-146">При использовании TLS между серверами-посредниками и шлюзами необходимо настроить шлюзы и серверы-посредники для поддержки MTLS следующим образом:</span><span class="sxs-lookup"><span data-stu-id="a43c4-146">If you are using TLS between Mediation Servers and gateways, you will need to configure the gateways and Mediation Servers to support MTLS as follows:</span></span>
  
1. <span data-ttu-id="a43c4-147">Экспорт корневого ЦС с компьютера Cloud Connector Active Directory.</span><span class="sxs-lookup"><span data-stu-id="a43c4-147">Export the Root CA from the Cloud Connector Active Directory computer.</span></span>
    
2. <span data-ttu-id="a43c4-148">Следуйте инструкциям поставщика шлюза STN для импорта корневого ЦС.</span><span class="sxs-lookup"><span data-stu-id="a43c4-148">Follow the PSTN gateway vendor instructions for importing the Root CA.</span></span>
    
3. <span data-ttu-id="a43c4-149">Импортировать сертификат корневого ЦС для сертификата, выданного шлюзу на серверах-посредниках.</span><span class="sxs-lookup"><span data-stu-id="a43c4-149">Import the Root CA certificate for the certificate issued to your gateway on the Mediation Servers.</span></span> <span data-ttu-id="a43c4-150">Если вам нужно получить SSL-сертификат для шлюза, это можно сделать с помощью службы центра сертификации, запущенной на компьютере Active Directory Cloud Connector следующим образом:</span><span class="sxs-lookup"><span data-stu-id="a43c4-150">If you need to obtain an SSL certificate for the gateway, you may do this using the Certificate Authority service running on the Cloud Connector Active Directory computer as follows:</span></span>
    
   - <span data-ttu-id="a43c4-151">Измените существующий шаблон веб-сервера, чтобы включить регистрацию для пользователей, для проверки подлинности, или создайте новый шаблон веб-сервера, чтобы настроить другие свойства и включить регистрацию пользователей, подлинность и подлинность пользователей.</span><span class="sxs-lookup"><span data-stu-id="a43c4-151">Modify the existing Web Server template to enable Authenticated users to Enroll, or create a new Web Server template to configure other properties and enable Authenticated users to enroll.</span></span> <span data-ttu-id="a43c4-152">Подробные инструкции [см. в описании шаблонов сертификатов.](https://technet.microsoft.com/library/cc730705.aspx)</span><span class="sxs-lookup"><span data-stu-id="a43c4-152">For detailed instructions, see [Certificate Templates](https://technet.microsoft.com/library/cc730705.aspx).</span></span>
    
   - <span data-ttu-id="a43c4-153">Запрос сертификата с помощью оснастки "Сертификат" для выбора включенного шаблона веб-сервера.</span><span class="sxs-lookup"><span data-stu-id="a43c4-153">Request a certificate using Certificate snap-in selecting the Web Server template that you have enabled.</span></span> <span data-ttu-id="a43c4-154">Обязательно добавьте общее имя в subject и DNS-имя в альтернативном имени с FQDN шлюза и убедитесь, что в закрытом ключе выбран параметр "Сделать закрытый ключ экспортируемым".</span><span class="sxs-lookup"><span data-stu-id="a43c4-154">Be sure to add Common name in Subject and DNS name in Alternative name with FQDN of the gateway, and confirm on the Private Key that Make private key exportable is selected under key options.</span></span> 
    
4. <span data-ttu-id="a43c4-155">Экспортировать SSL-сертификат с закрытым ключом и следуйте инструкциям поставщика шлюза STN для импорта сертификата.</span><span class="sxs-lookup"><span data-stu-id="a43c4-155">Export the SSL certificate with Private key and follow the instructions from your PSTN gateway vendor for importing the certificate.</span></span>
    
5. <span data-ttu-id="a43c4-156">Шлюзы STN на одном сайте STN должны подключаться только к серверам-посредникам на том же сайте.</span><span class="sxs-lookup"><span data-stu-id="a43c4-156">PSTN gateway(s) in one PSTN site should only connect to the Mediation Server(s) in the same site.</span></span>
    
## <a name="set-up-your-users"></a><span data-ttu-id="a43c4-157">Настройка пользователей</span><span class="sxs-lookup"><span data-stu-id="a43c4-157">Set up your users</span></span>

<span data-ttu-id="a43c4-158">Войдите в Центр администрирования Microsoft 365, добавьте пользователей, для которых будут включены веб-службы голосовой связи, и назначьте этим пользователям лицензию E5 или надстройки телефонной системы.</span><span class="sxs-lookup"><span data-stu-id="a43c4-158">Log in to the Microsoft 365 admin center, add the users that will be enabled for online voice services, and assign an E5 license or Phone System add-on to the E3 license to these users.</span></span> <span data-ttu-id="a43c4-159">Дополнительные сведения о добавлении пользователей см. в подсети "Добавление пользователей [в Microsoft 365 для бизнеса".](https://support.office.com/article/Add-users-to-Office-365-for-business-435ccec3-09dd-4587-9ebd-2f3cad6bc2bc)</span><span class="sxs-lookup"><span data-stu-id="a43c4-159">For information about adding users, see [Add users to Microsoft 365 for business](https://support.office.com/article/Add-users-to-Office-365-for-business-435ccec3-09dd-4587-9ebd-2f3cad6bc2bc).</span></span>
  
## <a name="enable-users-for-phone-system-voice-and-voicemail-services"></a><span data-ttu-id="a43c4-160">Включить для пользователей службы голосовой и голосовой почты телефонной системы</span><span class="sxs-lookup"><span data-stu-id="a43c4-160">Enable users for Phone System voice and voicemail services</span></span>
 
<span data-ttu-id="a43c4-161">После добавления пользователей в Microsoft 365 или Office 365 включите их учетные записи для голосовых служб телефонной системы, включая голосовую почту.</span><span class="sxs-lookup"><span data-stu-id="a43c4-161">After adding your users to Microsoft 365 or Office 365, enable their accounts for Phone System voice services, including voicemail.</span></span> <span data-ttu-id="a43c4-162">Чтобы включить эти возможности, необходимо войти в свою организацию Microsoft 365 или Office 365 с учетной записью, которая является ролью глобального администратора, и иметь возможность запускать удаленную powerShell.</span><span class="sxs-lookup"><span data-stu-id="a43c4-162">To enable these capabilities, you must log in to your Microsoft 365 or Office 365 organization with an account that is a Global Administrator role, and be able to run remote PowerShell.</span></span> <span data-ttu-id="a43c4-163">Чтобы узнать, как установить удаленный сеанс [](https://technet.microsoft.com/library/dn362831%28v=ocs.15%29.aspx) PowerShell, см. в этой Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="a43c4-163">To learn how to establish a remote PowerShell session, see: [Set up your computer for Windows PowerShell](https://technet.microsoft.com/library/dn362831%28v=ocs.15%29.aspx)</span></span>
  
- <span data-ttu-id="a43c4-164">Назначьте политику пользователю и настройте номер телефона бизнес-голосовой связи, который указывается в параметре **Identity:**</span><span class="sxs-lookup"><span data-stu-id="a43c4-164">Assign the policy to your user and configure the user's business voice phone number, which you specify with the value of the **Identity** parameter:</span></span>
    
  ```powershell
  Set-CsUser -Identity "<User name>" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true -OnPremLineURI <tel:+phonenumber>
  ```

    > [!NOTE]
    > <span data-ttu-id="a43c4-165">Удостоверение пользователя может быть задано с помощью SIP-адреса пользователя, имени пользователя-директора или отображаемого имени Active Directory пользователя (например, "Bob Kelly").</span><span class="sxs-lookup"><span data-stu-id="a43c4-165">A user identity can be specified using the user's SIP address, user principal name (UPN), or the user's Active Directory display name (for example, "Bob Kelly").</span></span> <span data-ttu-id="a43c4-166">Звездочка () также может использоваться вместе с \* отображаемой именем в качестве удостоверения пользователя.</span><span class="sxs-lookup"><span data-stu-id="a43c4-166">The asterisk (\*) character can also be used with the Display Name as the user Identity.</span></span> <span data-ttu-id="a43c4-167">Например, идентификатор "Smith" возвращает всех пользователей, отображаемого имени которых заканчивается строкой \* "Smith".</span><span class="sxs-lookup"><span data-stu-id="a43c4-167">For example, the Identity "\*Smith" returns all the users who have a display name that ends with the string value "Smith".</span></span>
  
<span data-ttu-id="a43c4-168">Затем можно проверить, были ли добавлены и включены пользователи, с помощью следующего скрипта:</span><span class="sxs-lookup"><span data-stu-id="a43c4-168">You can then verify that the users were added and enabled using the following script:</span></span>
  
```powershell
# Input the user name you want to verify
$user = Get-CsOnlineUser <User name>

# For a hybrid user, the value of $user.EnterpriseVoiceEnabled should be True
$user.EnterpriseVoiceEnabled

# For a hybrid user, the value of $user.HostedVoiceMail should be True
$user.HostedVoiceMail

# For a hybrid user, the value of $user.VoicePolicy should be "HybridVoice"
$user.VoicePolicy
```

<span data-ttu-id="a43c4-169">Необходимо решить, смогут ли ваши пользователи делать международные звонки.</span><span class="sxs-lookup"><span data-stu-id="a43c4-169">You'll need to decide whether your users should be able to make international calls.</span></span> <span data-ttu-id="a43c4-170">По умолчанию международные вызовы включены.</span><span class="sxs-lookup"><span data-stu-id="a43c4-170">By default, international calling is enabled.</span></span> <span data-ttu-id="a43c4-171">You can disable or enable users for international dialing using the online Skype for Business admin center.</span><span class="sxs-lookup"><span data-stu-id="a43c4-171">You can disable or enable users for international dialing using the online Skype for Business admin center.</span></span>
  
<span data-ttu-id="a43c4-172">Чтобы отключить международные звонки для каждого пользователя, запустите следующий cmdlet в Skype для бизнеса Online PowerShell:</span><span class="sxs-lookup"><span data-stu-id="a43c4-172">To disable international calling on a per user basis, run the following cmdlet in Skype for Business Online PowerShell:</span></span>
  
```powershell
Grant-CsVoiceRoutingPolicy -PolicyName InternationalCallsDisallowed -Identity $user
```

<span data-ttu-id="a43c4-173">Чтобы повторно включить международные вызовы для каждого пользователя после его отключения, запустите тот же самый cmdlet, но измените значение **для PolicyName** на *InternationalCallsAllowed.*</span><span class="sxs-lookup"><span data-stu-id="a43c4-173">To re-enable international calling on a per user basis after it has been disabled, run the same cmdlet, but change the value for **PolicyName** to *InternationalCallsAllowed*  .</span></span>
  
## <a name="assign-users-to-pstn-sites"></a><span data-ttu-id="a43c4-174">Назначение пользователей сайтам STN</span><span class="sxs-lookup"><span data-stu-id="a43c4-174">Assign users to PSTN sites</span></span>

<span data-ttu-id="a43c4-175">Используйте удаленную powerShell клиента, чтобы назначить сайт пользователям, даже если развернут только один сайт.</span><span class="sxs-lookup"><span data-stu-id="a43c4-175">Use tenant remote PowerShell to assign a site to users even if you only deployed a single site.</span></span> <span data-ttu-id="a43c4-176">Чтобы узнать, как установить удаленный сеанс PowerShell, см. в этой [Windows PowerShell.](https://technet.microsoft.com/library/dn362831%28v=ocs.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="a43c4-176">To learn how to establish a remote PowerShell session, see: [Set up your computer for Windows PowerShell](https://technet.microsoft.com/library/dn362831%28v=ocs.15%29.aspx).</span></span>
  
```powershell
# Set the site to users
Set-CsUserPstnSettings -Identity <User Name> -HybridPstnSite <PSTN Site Name>

# Review the site setting for a user
Get-CsUserPstnSettings -Identity <User Name> 

# See all the user settings in one tenant
Get-CsOnlineUser | Get-CsUserPstnSettings
```

> [!NOTE]
> <span data-ttu-id="a43c4-177">Если пользователю не назначен сайт STN, гибридное подключение между развертыванием Skype для бизнеса Cloud Connector Edition и организацией Microsoft 365 или Office 365 будет возвращаться к использованию стандартного уровня клиента (одноранговая цель), чтобы можно было завершить вызовы.</span><span class="sxs-lookup"><span data-stu-id="a43c4-177">If no PSTN site is assigned to a user, hybrid connectivity between your Skype for Business Cloud Connector Edition deployment and your Microsoft 365 or Office 365 organization will fall back to use the tenant level default one (Peer Destination) so that calls can be completed.</span></span> 
  
## <a name="configure-online-hybrid-mediation-server-settings"></a><span data-ttu-id="a43c4-178">Настройка параметров сетевого гибридного сервера-посредника</span><span class="sxs-lookup"><span data-stu-id="a43c4-178">Configure online hybrid Mediation Server Settings</span></span>
<span data-ttu-id="a43c4-179"><a name="BKMK_ConfigureMediationServer"> </a></span><span class="sxs-lookup"><span data-stu-id="a43c4-179"><a name="BKMK_ConfigureMediationServer"> </a></span></span>

<span data-ttu-id="a43c4-180">Когда вызов P2P перенаправлен на конференцию STN, сервер конференц-связи Skype для бизнеса Online отправит приглашение серверу-посреднику Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="a43c4-180">When a P2P call is escalated to a PSTN conference, the Skype for Business Online conferencing server will send an invite to the Cloud Connector Mediation Server.</span></span> <span data-ttu-id="a43c4-181">Чтобы убедиться, что Microsoft 365 или Office 365 могут успешно маршрутировать это приглашение, необходимо настроить параметр в сетевом клиенте для каждого сервера-посредника Cloud Connector следующим образом:</span><span class="sxs-lookup"><span data-stu-id="a43c4-181">To ensure that Microsoft 365 or Office 365 can route this invite successfully, you need to configure a setting in your online tenant for each Cloud Connector Mediation Server as follows:</span></span> 
  
1. <span data-ttu-id="a43c4-182">Создайте пользователя в Центре администрирования Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="a43c4-182">Create a user in the Microsoft 365 admin center.</span></span> <span data-ttu-id="a43c4-183">Используйте любое нужное имя пользователя, например "MediationServer1".</span><span class="sxs-lookup"><span data-stu-id="a43c4-183">Use any user name you want, such as "MediationServer1."</span></span>
    
    <span data-ttu-id="a43c4-184">Используйте SIP-домен Cloud Connector по умолчанию (первый домен SIP в INI-файле) в качестве домена пользователя.</span><span class="sxs-lookup"><span data-stu-id="a43c4-184">Use the default SIP domain of Cloud Connector (the first SIP domain in the .ini file) as the user domain.</span></span>
    
    <span data-ttu-id="a43c4-185">Обратите внимание, что назначение лицензии требуется только для распространения пользователя в каталог Skype для бизнеса Online.</span><span class="sxs-lookup"><span data-stu-id="a43c4-185">Please note that license assignment is only required for the user propagation into the Skype for Business online directory.</span></span> <span data-ttu-id="a43c4-186">Assign a Microsoft 365 or Office 365 license (such as E5) to the account you create, allow up to one hour for the changes to propagate, verify the user accounts has been provisioned correctly to the Skype for Business online directory by running following cmdlet, then remove the license from this account.</span><span class="sxs-lookup"><span data-stu-id="a43c4-186">Assign a Microsoft 365 or Office 365 license (such as E5) to the account you create, allow up to one hour for the changes to propagate,verify the user accounts has been provisioned correctly to the Skype for Business online directory by running following cmdlet, then remove the license from this account.</span></span>
    ```powershell
   Get-CsOnlineUser -Identity <UserPrincipalName>
   ```
    
2. <span data-ttu-id="a43c4-187">Запустите удаленный сеанс PowerShell azure AD клиента с использованием учетных данных глобального администратора или администратора пользователя, а затем запустите следующий cmdlet, чтобы настроить отдел для учетной записи пользователя Azure AD, настроенной на шаге 1, на "HybridMediationServer":</span><span class="sxs-lookup"><span data-stu-id="a43c4-187">Start a tenant Azure AD remote PowerShell session using your global or user admin credentials, and then run the following cmdlet to set the department for the Azure AD user account configured in step 1 to "HybridMediationServer":</span></span>

   ```powershell
   Set-MsolUser -UserPrincipalName <UserPrincipalName> -Department "HybridMediationServer"
   ```

3. <span data-ttu-id="a43c4-188">Запустите удаленный сеанс PowerShell клиента Skype для бизнеса, используя учетные данные администратора клиента Skype для бизнеса, а затем запустите следующий cmdlet, чтобы установить для этой учетной записи пользователя имя FQDN сервера-посредника и сервера-посредника, заменив отображаемого имени пользователя для учетной записи, созданной на шаге \<DisplayName\> 1:</span><span class="sxs-lookup"><span data-stu-id="a43c4-188">Start a tenant Skype for Business remote PowerShell session using your Skype for Business tenant admin credentials, and then run the following cmdlet to set the Mediation Server and Edge Server FQDN to that user account, replacing \<DisplayName\> with the Display Name of the user for the account you created in step 1:</span></span>
    
   ```powershell
   Set-CsHybridMediationServer -Identity <DisplayName> -Fqdn <MediationServerFQDN> -AccessProxyExternalFqdn <EdgeServerExternalFQDN>
   ```

    <span data-ttu-id="a43c4-189">Для удостоверения используйте отображаемую имя учетной записи пользователя, созданной для этого сервера-посредника.</span><span class="sxs-lookup"><span data-stu-id="a43c4-189">For Identity, use the Display Name of the user account you created for this Mediation Server.</span></span>
    
    <span data-ttu-id="a43c4-190">Для  *mediationServerFQDN*  используйте внутреннее FQDN, определенное для сервера-посредника.</span><span class="sxs-lookup"><span data-stu-id="a43c4-190">For  *MediationServerFQDN*  , use the internal FQDN defined for your Mediation Server.</span></span>
    
    <span data-ttu-id="a43c4-191">Для  *EdgeServerExternalFQDN*  используйте внешнее FQDN, определенное для прокси-сервера доступа к серверу.</span><span class="sxs-lookup"><span data-stu-id="a43c4-191">For  *EdgeServerExternalFQDN*  , use the external FQDN defined for Edge Server Access Proxy.</span></span> <span data-ttu-id="a43c4-192">Если имеется несколько сайтов STN Cloud Connector, выберите FQDN прокси-сервера доступа к серверу, назначенное сайту, на котором расположен сервер-посредник.</span><span class="sxs-lookup"><span data-stu-id="a43c4-192">If there are multiple Cloud Connector PSTN sites, choose the Edge Server Access Proxy FQDN assigned to the site where the Mediation Server is located.</span></span>
    
4. <span data-ttu-id="a43c4-193">Если имеется несколько серверов-посредников Cloud Connector (с несколькими сайтами, ha), повторите предыдущие шаги для каждого из них.</span><span class="sxs-lookup"><span data-stu-id="a43c4-193">If there are multiple Cloud Connector Mediation Servers (multiple-site, HA), please repeat the previous steps for each of them.</span></span>
    
