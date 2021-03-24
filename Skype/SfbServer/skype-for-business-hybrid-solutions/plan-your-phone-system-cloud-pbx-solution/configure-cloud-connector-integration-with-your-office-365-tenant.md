---
title: Настройка интеграции облачного соединители с организацией Microsoft 365 или Office 365
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
description: Узнайте, как настроить интеграцию облачного соединители с организацией Microsoft 365 или Office 365.
ms.openlocfilehash: 74696023dcffbc91641bb4e9950f2988a89abbdd
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51095093"
---
# <a name="configure-cloud-connector-integration-with-your-microsoft-365-or-office-365-organization"></a><span data-ttu-id="5c60c-103">Настройка интеграции облачного соединители с организацией Microsoft 365 или Office 365</span><span class="sxs-lookup"><span data-stu-id="5c60c-103">Configure Cloud Connector integration with your Microsoft 365 or Office 365 organization</span></span>

> [!Important] 
> <span data-ttu-id="5c60c-104">Cloud Connector Edition завершит карьеру 31 июля 2021 г. вместе со Skype для бизнеса Online.</span><span class="sxs-lookup"><span data-stu-id="5c60c-104">Cloud Connector Edition will retire July 31, 2021 along with Skype for Business Online.</span></span> <span data-ttu-id="5c60c-105">После обновления организации до Teams узнайте, как подключить сеть локальной телефонии к Teams с помощью прямой [маршрутизации.](/MicrosoftTeams/direct-routing-landing-page)</span><span class="sxs-lookup"><span data-stu-id="5c60c-105">Once your organization has upgraded to Teams, learn how to connect your on-premises telephony network to Teams using [Direct Routing](/MicrosoftTeams/direct-routing-landing-page).</span></span>

<span data-ttu-id="5c60c-106">Узнайте, как настроить интеграцию облачного соединители с организацией Microsoft 365 или Office 365.</span><span class="sxs-lookup"><span data-stu-id="5c60c-106">Learn how to configure Cloud Connector integration with your Microsoft 365 or Office 365 organization.</span></span>
  
<span data-ttu-id="5c60c-107">После завершения установки skype for Business Cloud Connector Edition выполните действия в этом разделе, чтобы настроить развертывание и подключить его к организации Microsoft 365 или Office 365.</span><span class="sxs-lookup"><span data-stu-id="5c60c-107">Once the Skype for Business Cloud Connector Edition installation is complete, perform the steps in this section to configure your deployment and connect it to your Microsoft 365 or Office 365 organization.</span></span>
  
## <a name="configure-firewall-settings"></a><span data-ttu-id="5c60c-108">Настройка параметров брандмауэра</span><span class="sxs-lookup"><span data-stu-id="5c60c-108">Configure firewall settings</span></span>

<span data-ttu-id="5c60c-109">Настройка параметров брандмауэра для внутренних и внешних параметров брандмауэра для [](plan-skype-for-business-cloud-connector-edition.md#BKMB_Ports) сети периметра для открытия необходимых портов, как описано в портах и протоколах в [Plan for Skype for Business Cloud Connector Edition](plan-skype-for-business-cloud-connector-edition.md).</span><span class="sxs-lookup"><span data-stu-id="5c60c-109">Configure the firewall settings for your internal and external firewall settings for you perimeter network to open the required ports as described in [Ports and protocols](plan-skype-for-business-cloud-connector-edition.md#BKMB_Ports) in [Plan for Skype for Business Cloud Connector Edition](plan-skype-for-business-cloud-connector-edition.md).</span></span>
  
## <a name="set-up-public-switched-telephone-network-pstn-gateways"></a><span data-ttu-id="5c60c-110">Настройка шлюзов общедоступных переключеных телефонных сетей (PSTN)</span><span class="sxs-lookup"><span data-stu-id="5c60c-110">Set up Public Switched Telephone Network (PSTN) gateways</span></span>

<span data-ttu-id="5c60c-111">Настройка магистрали на каждом шлюзе PSTN, чтобы указать обратно на серверы-посредники для всех устройств.</span><span class="sxs-lookup"><span data-stu-id="5c60c-111">Set up trunks on each PSTN gateway to point back to Mediation Servers for all appliances.</span></span> <span data-ttu-id="5c60c-112">Так как FQDN пула является одинаковым для всех серверов пула, каждый магистраль должен указать на один FQDN или IP-адрес сервера-посредника вместо FQDN пула посредников.</span><span class="sxs-lookup"><span data-stu-id="5c60c-112">Because the pool FQDN is the same for all servers in the pool, each trunk should point to one Mediation Server FQDN or IP address instead of the Mediation Server pool FQDN.</span></span> <span data-ttu-id="5c60c-113">Магистрали должны быть настроены в том же приоритете.</span><span class="sxs-lookup"><span data-stu-id="5c60c-113">Trunks should be set in the same priority.</span></span>
  
<span data-ttu-id="5c60c-114">Если вы используете TLS между серверами-посредниками и шлюзами, вам потребуется настроить шлюзы и серверы-посредники для поддержки MTLS следующим образом:</span><span class="sxs-lookup"><span data-stu-id="5c60c-114">If you are using TLS between Mediation Servers and gateways, you will need to configure the gateways and Mediation Servers to support MTLS as follows:</span></span>
  
1. <span data-ttu-id="5c60c-115">Экспорт корневого ЦС с компьютера Cloud Connector Active Directory.</span><span class="sxs-lookup"><span data-stu-id="5c60c-115">Export the Root CA from the Cloud Connector Active Directory computer.</span></span>
    
2. <span data-ttu-id="5c60c-116">Следуйте инструкциям поставщика шлюза PSTN для импорта корневого ЦС.</span><span class="sxs-lookup"><span data-stu-id="5c60c-116">Follow the PSTN gateway vendor instructions for importing the Root CA.</span></span>
    
3. <span data-ttu-id="5c60c-117">Импорт сертификата Root CA для сертификата, выданного шлюзу на серверах-посредниках.</span><span class="sxs-lookup"><span data-stu-id="5c60c-117">Import the Root CA certificate for the certificate issued to your gateway on the Mediation Servers.</span></span> <span data-ttu-id="5c60c-118">Если вам необходимо получить сертификат SSL для шлюза, вы можете сделать это с помощью службы Authority сертификата, запущенной на компьютере Active Directory облачного соединителя следующим образом:</span><span class="sxs-lookup"><span data-stu-id="5c60c-118">If you need to obtain an SSL certificate for the gateway, you may do this using the Certificate Authority service running on the Cloud Connector Active Directory computer as follows:</span></span>
    
   - <span data-ttu-id="5c60c-119">Измените существующий шаблон веб-сервера, чтобы пользователи могли зарегистрироваться с проверкой подлинности, или создать новый шаблон веб-сервера для настройки других свойств и обеспечения регистрации пользователей с проверкой подлинности.</span><span class="sxs-lookup"><span data-stu-id="5c60c-119">Modify the existing Web Server template to enable Authenticated users to enroll, or create a new Web Server template to configure other properties and enable Authenticated users to enroll.</span></span> <span data-ttu-id="5c60c-120">Подробные инструкции см. [в справке Шаблоны сертификатов.](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc730705(v=ws.11))</span><span class="sxs-lookup"><span data-stu-id="5c60c-120">For detailed instructions, see [Certificate Templates](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc730705(v=ws.11)).</span></span>
    
   - <span data-ttu-id="5c60c-121">Запрос сертификата с помощью оснастки сертификата для выбора шаблона веб-сервера, который вы включили.</span><span class="sxs-lookup"><span data-stu-id="5c60c-121">Request a certificate using Certificate snap-in selecting the Web Server template that you have enabled.</span></span> <span data-ttu-id="5c60c-122">Обязательно добавьте имя Common в Subject и DNS в Альтернативное имя с FQDN шлюза и убедитесь в частном ключе, что при ключевых параметрах выбирается частный ключ, экспортируемый.</span><span class="sxs-lookup"><span data-stu-id="5c60c-122">Be sure to add Common name in Subject and DNS name in Alternative name with FQDN of the gateway, and confirm on the Private Key that Make private key exportable is selected under key options.</span></span> 
    
4. <span data-ttu-id="5c60c-123">Экспорт сертификата SSL с закрытым ключом и следуйте инструкциям поставщика шлюза PSTN для импорта сертификата.</span><span class="sxs-lookup"><span data-stu-id="5c60c-123">Export the SSL certificate with Private key and follow the instructions from your PSTN gateway vendor for importing the certificate.</span></span>
    
## <a name="update-the-domain-for-your-tenant"></a><span data-ttu-id="5c60c-124">Обновление домена для клиента</span><span class="sxs-lookup"><span data-stu-id="5c60c-124">Update the domain for your tenant</span></span>

<span data-ttu-id="5c60c-125">Убедитесь, что вы выполнили действия по обновлению домена в Microsoft 365 или Office 365 и получили возможность добавлять записи DNS.</span><span class="sxs-lookup"><span data-stu-id="5c60c-125">Make sure that you've completed the steps to update your domain in Microsoft 365 or Office 365 and have the ability to add DNS records.</span></span> <span data-ttu-id="5c60c-126">Дополнительные сведения о том, как настроить домен в Microsoft 365 или Office 365, см. в добавлении домена в [Microsoft 365 или Office 365.](https://support.office.com/article/Add-a-domain-to-Office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611)</span><span class="sxs-lookup"><span data-stu-id="5c60c-126">For more information about how to set up your domain in Microsoft 365 or Office 365, see [Add a domain to Microsoft 365 or Office 365](https://support.office.com/article/Add-a-domain-to-Office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611).</span></span>
  
## <a name="add-dns-records-for-your-edge"></a><span data-ttu-id="5c60c-127">Добавление записей DNS для edge</span><span class="sxs-lookup"><span data-stu-id="5c60c-127">Add DNS records for your Edge</span></span>

<span data-ttu-id="5c60c-128">Добавьте следующие записи DNS в организацию Microsoft 365 или Office 365.</span><span class="sxs-lookup"><span data-stu-id="5c60c-128">Add the following DNS records to your Microsoft 365 or Office 365 organization.</span></span> <span data-ttu-id="5c60c-129">Сведения о добавлении записей DNS см. в статью Добавление или изменение пользовательских [записей DNS в Microsoft 365 или Office 365.](https://support.office.com/article/Add-or-edit-custom-DNS-records-in-Office-365-AF00A516-DD39-4EDA-AF3E-1EAF686C8DC9?ui=en-US&amp;rs=en-US&amp;ad=US&amp;fromAR=1)</span><span class="sxs-lookup"><span data-stu-id="5c60c-129">For information about how to add DNS records, see [Add or edit custom DNS records in Microsoft 365 or Office 365](https://support.office.com/article/Add-or-edit-custom-DNS-records-in-Office-365-AF00A516-DD39-4EDA-AF3E-1EAF686C8DC9?ui=en-US&amp;rs=en-US&amp;ad=US&amp;fromAR=1).</span></span>
  
1. <span data-ttu-id="5c60c-130">Добавление записи DNS Для края доступа.</span><span class="sxs-lookup"><span data-stu-id="5c60c-130">Add a DNS A record for Access Edge.</span></span>
    
2. <span data-ttu-id="5c60c-131">Записи SRV автоматически создаются Microsoft 365 или Office 365 и скриптами развертывания.</span><span class="sxs-lookup"><span data-stu-id="5c60c-131">SRV records will automatically be created by Microsoft 365 or Office 365 and the deployment scripts.</span></span> <span data-ttu-id="5c60c-132">Подтверди, что на границе можно найти следующие две службы SIP: \_ sip и \_ sipfederationtls.</span><span class="sxs-lookup"><span data-stu-id="5c60c-132">Confirm that you can look up the following two SIP services on the Edge: \_sip and \_sipfederationtls.</span></span>
    
     ![Подтверждение записей SRV](../../media/3c353a29-6dcc-4ed3-98db-3a6bed3e929e.png)
  
## <a name="set-up-hybrid-connectivity-between-cloud-connector-edition-and-microsoft-365-or-office-365"></a><span data-ttu-id="5c60c-134">Настройка гибридного подключения между Cloud Connector Edition и Microsoft 365 или Office 365</span><span class="sxs-lookup"><span data-stu-id="5c60c-134">Set up hybrid connectivity between Cloud Connector Edition and Microsoft 365 or Office 365</span></span>

<span data-ttu-id="5c60c-135">Чтобы настроить гибридное подключение между развертыванием Skype для бизнеса cloud Connector Edition и организацией Microsoft 365 или Office 365, запустите следующий комдлет в удаленном сеансе PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5c60c-135">To configure hybrid connectivity between your Skype for Business Cloud Connector Edition deployment and your Microsoft 365 or Office 365 organization, run the following cmdlet in a remote PowerShell session.</span></span> <span data-ttu-id="5c60c-136">Чтобы узнать, как установить удаленный сеанс PowerShell, см. в рубке: Настройка компьютера [для Windows PowerShell.](../../../SfbOnline/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)</span><span class="sxs-lookup"><span data-stu-id="5c60c-136">To learn how to establish a remote PowerShell session, see: [Set up your computer for Windows PowerShell](../../../SfbOnline/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span></span>
  
<span data-ttu-id="5c60c-137">В этом комлете задаваем внешний FQDN Access Edge.</span><span class="sxs-lookup"><span data-stu-id="5c60c-137">The cmdlet sets the Access Edge external FQDN.</span></span> <span data-ttu-id="5c60c-138">В первой из команд должна быть роль \<External Access Edge FQDN\> SIP Access Edge.</span><span class="sxs-lookup"><span data-stu-id="5c60c-138">In the first of the commands, the \<External Access Edge FQDN\> should be the one for the SIP Access Edge role.</span></span> <span data-ttu-id="5c60c-139">По умолчанию это должно быть ap. \<Domain Name\> .</span><span class="sxs-lookup"><span data-stu-id="5c60c-139">By default, this should be ap.\<Domain Name\>.</span></span>
  
```powershell
Set-CsTenantHybridConfiguration -PeerDestination <External Access Edge FQDN> -UseOnPremDialPlan $false
Set-CsTenantFederationConfiguration -SharedSipAddressSpace $True
```

> [!NOTE]
> <span data-ttu-id="5c60c-140">Внешний FQDN edge access, используемый для одноранговых назначений, должен быть установлен на сайте PSTN, который будет использоваться только в качестве отката в случае, если пользователь не назначен сайту PSTN.</span><span class="sxs-lookup"><span data-stu-id="5c60c-140">The External Access Edge FQDN used for Peer Destination should be set to a PSTN site that will only be used as a fallback in case a user isn't assigned to a PSTN site.</span></span> <span data-ttu-id="5c60c-141">Дополнительные сведения см. в [веб-сайте Развертывание](deploy-a-single-site-in-cloud-connector.md) одного сайта в облачном соединители и развертывание нескольких сайтов [в облачном соединители.](deploy-multiple-sites-in-cloud-connector.md)</span><span class="sxs-lookup"><span data-stu-id="5c60c-141">For more information, see [Deploy a single site in Cloud Connector](deploy-a-single-site-in-cloud-connector.md) and [Deploy multiple sites in Cloud Connector](deploy-multiple-sites-in-cloud-connector.md).</span></span> 
  
## <a name="set-up-pstn-gateways"></a><span data-ttu-id="5c60c-142">Настройка шлюзов PSTN</span><span class="sxs-lookup"><span data-stu-id="5c60c-142">Set up PSTN gateways</span></span>

<span data-ttu-id="5c60c-143">Настройка магистрали на каждом шлюзе PSTN, чтобы указать обратно на серверы-посредники для всех устройств.</span><span class="sxs-lookup"><span data-stu-id="5c60c-143">Set up trunks on each PSTN gateway to point back to Mediation Servers for all appliances.</span></span> <span data-ttu-id="5c60c-144">Каждый магистраль должен указать на один FQDN или IP-адрес сервера-посредника вместо пула FQDN пула посредников, так как FQDN пула является одинаковым для всех серверов пула.</span><span class="sxs-lookup"><span data-stu-id="5c60c-144">Each trunk should point to one Mediation Server FQDN or IP address instead of the Mediation Server pool FQDN because the pool FQDN is the same for all servers in the pool.</span></span> <span data-ttu-id="5c60c-145">Магистрали должны быть настроены в том же приоритете.</span><span class="sxs-lookup"><span data-stu-id="5c60c-145">Trunks should be set in the same priority.</span></span>
  
<span data-ttu-id="5c60c-146">Если вы используете TLS между серверами-посредниками и шлюзами, вам потребуется настроить шлюзы и серверы-посредники для поддержки MTLS следующим образом:</span><span class="sxs-lookup"><span data-stu-id="5c60c-146">If you are using TLS between Mediation Servers and gateways, you will need to configure the gateways and Mediation Servers to support MTLS as follows:</span></span>
  
1. <span data-ttu-id="5c60c-147">Экспорт корневого ЦС с компьютера Cloud Connector Active Directory.</span><span class="sxs-lookup"><span data-stu-id="5c60c-147">Export the Root CA from the Cloud Connector Active Directory computer.</span></span>
    
2. <span data-ttu-id="5c60c-148">Следуйте инструкциям поставщика шлюза PSTN для импорта корневого ЦС.</span><span class="sxs-lookup"><span data-stu-id="5c60c-148">Follow the PSTN gateway vendor instructions for importing the Root CA.</span></span>
    
3. <span data-ttu-id="5c60c-149">Импорт сертификата Root CA для сертификата, выданного шлюзу на серверах-посредниках.</span><span class="sxs-lookup"><span data-stu-id="5c60c-149">Import the Root CA certificate for the certificate issued to your gateway on the Mediation Servers.</span></span> <span data-ttu-id="5c60c-150">Если вам необходимо получить сертификат SSL для шлюза, вы можете сделать это с помощью службы Authority сертификата, запущенной на компьютере Active Directory облачного соединителя следующим образом:</span><span class="sxs-lookup"><span data-stu-id="5c60c-150">If you need to obtain an SSL certificate for the gateway, you may do this using the Certificate Authority service running on the Cloud Connector Active Directory computer as follows:</span></span>
    
   - <span data-ttu-id="5c60c-151">Измените существующий шаблон веб-сервера, чтобы пользователи могли зарегистрироваться на проверку подлинности, или создать новый шаблон веб-сервера для настройки других свойств и регистрации с проверкой подлинности.</span><span class="sxs-lookup"><span data-stu-id="5c60c-151">Modify the existing Web Server template to enable Authenticated users to Enroll, or create a new Web Server template to configure other properties and enable Authenticated users to enroll.</span></span> <span data-ttu-id="5c60c-152">Подробные инструкции см. [в справке Шаблоны сертификатов.](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc730705(v=ws.11))</span><span class="sxs-lookup"><span data-stu-id="5c60c-152">For detailed instructions, see [Certificate Templates](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc730705(v=ws.11)).</span></span>
    
   - <span data-ttu-id="5c60c-153">Запрос сертификата с помощью оснастки сертификата для выбора шаблона веб-сервера, который вы включили.</span><span class="sxs-lookup"><span data-stu-id="5c60c-153">Request a certificate using Certificate snap-in selecting the Web Server template that you have enabled.</span></span> <span data-ttu-id="5c60c-154">Обязательно добавьте имя Common в Subject и DNS в Альтернативное имя с FQDN шлюза и убедитесь в частном ключе, что при ключевых параметрах выбирается частный ключ, экспортируемый.</span><span class="sxs-lookup"><span data-stu-id="5c60c-154">Be sure to add Common name in Subject and DNS name in Alternative name with FQDN of the gateway, and confirm on the Private Key that Make private key exportable is selected under key options.</span></span> 
    
4. <span data-ttu-id="5c60c-155">Экспорт сертификата SSL с закрытым ключом и следуйте инструкциям поставщика шлюза PSTN для импорта сертификата.</span><span class="sxs-lookup"><span data-stu-id="5c60c-155">Export the SSL certificate with Private key and follow the instructions from your PSTN gateway vendor for importing the certificate.</span></span>
    
5. <span data-ttu-id="5c60c-156">Шлюз PSTN(ы) на одном сайте PSTN должен подключаться только к серверу-посреднику(ы) на том же сайте.</span><span class="sxs-lookup"><span data-stu-id="5c60c-156">PSTN gateway(s) in one PSTN site should only connect to the Mediation Server(s) in the same site.</span></span>
    
## <a name="set-up-your-users"></a><span data-ttu-id="5c60c-157">Настройка пользователей</span><span class="sxs-lookup"><span data-stu-id="5c60c-157">Set up your users</span></span>

<span data-ttu-id="5c60c-158">Войдите в центр администрирования Microsoft 365, добавьте пользователей, которые будут включены для голосовых служб в Интернете, и назначьте этим пользователям лицензию E5 или надстройки телефонной системы для лицензии E3.</span><span class="sxs-lookup"><span data-stu-id="5c60c-158">Log in to the Microsoft 365 admin center, add the users that will be enabled for online voice services, and assign an E5 license or Phone System add-on to the E3 license to these users.</span></span> <span data-ttu-id="5c60c-159">Сведения о добавлении пользователей см. в добавлении пользователей [в Microsoft 365 для бизнеса.](https://support.office.com/article/Add-users-to-Office-365-for-business-435ccec3-09dd-4587-9ebd-2f3cad6bc2bc)</span><span class="sxs-lookup"><span data-stu-id="5c60c-159">For information about adding users, see [Add users to Microsoft 365 for business](https://support.office.com/article/Add-users-to-Office-365-for-business-435ccec3-09dd-4587-9ebd-2f3cad6bc2bc).</span></span>
  
## <a name="enable-users-for-phone-system-voice-and-voicemail-services"></a><span data-ttu-id="5c60c-160">Включить пользователей для служб голосовой и голосовой почты телефонной системы</span><span class="sxs-lookup"><span data-stu-id="5c60c-160">Enable users for Phone System voice and voicemail services</span></span>
 
<span data-ttu-id="5c60c-161">После добавления пользователей в Microsoft 365 или Office 365 включите учетные записи для голосовых служб телефонной системы, в том числе голосовой почты.</span><span class="sxs-lookup"><span data-stu-id="5c60c-161">After adding your users to Microsoft 365 or Office 365, enable their accounts for Phone System voice services, including voicemail.</span></span> <span data-ttu-id="5c60c-162">Чтобы включить эти возможности, необходимо войти в свою организацию Microsoft 365 или Office 365 с учетной записью, которая является ролью глобального администратора, и иметь возможность запуска удаленной PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5c60c-162">To enable these capabilities, you must log in to your Microsoft 365 or Office 365 organization with an account that is a Global Administrator role, and be able to run remote PowerShell.</span></span> <span data-ttu-id="5c60c-163">Чтобы узнать, как установить удаленный сеанс PowerShell, см. в рубке: Настройка компьютера [для Windows PowerShell](../../../SfbOnline/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)</span><span class="sxs-lookup"><span data-stu-id="5c60c-163">To learn how to establish a remote PowerShell session, see: [Set up your computer for Windows PowerShell](../../../SfbOnline/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)</span></span>
  
- <span data-ttu-id="5c60c-164">Назначьте политику пользователю и настройте номер делового голосового телефона пользователя, который указан со значением **параметра Identity:**</span><span class="sxs-lookup"><span data-stu-id="5c60c-164">Assign the policy to your user and configure the user's business voice phone number, which you specify with the value of the **Identity** parameter:</span></span>
    
  ```powershell
  Set-CsUser -Identity "<User name>" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true -OnPremLineURI <tel:+phonenumber>
  ```

    > [!NOTE]
    > <span data-ttu-id="5c60c-165">Идентификация пользователя может быть указана с помощью SIP-адреса пользователя, имени основного пользователя (UPN) или имени отображения Active Directory пользователя (например, "Bob Kelly").</span><span class="sxs-lookup"><span data-stu-id="5c60c-165">A user identity can be specified using the user's SIP address, user principal name (UPN), or the user's Active Directory display name (for example, "Bob Kelly").</span></span> <span data-ttu-id="5c60c-166">Символ звездочки () также можно использовать с именем \* display в качестве идентификатора пользователя.</span><span class="sxs-lookup"><span data-stu-id="5c60c-166">The asterisk (\*) character can also be used with the Display Name as the user Identity.</span></span> <span data-ttu-id="5c60c-167">Например, идентификатор "Smith" возвращает всех пользователей, у которых есть имя отображения, которое заканчивается значением \* строки "Smith".</span><span class="sxs-lookup"><span data-stu-id="5c60c-167">For example, the Identity "\*Smith" returns all the users who have a display name that ends with the string value "Smith".</span></span>
  
<span data-ttu-id="5c60c-168">Затем можно убедиться, что пользователи были добавлены и включены с помощью следующего сценария:</span><span class="sxs-lookup"><span data-stu-id="5c60c-168">You can then verify that the users were added and enabled using the following script:</span></span>
  
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

<span data-ttu-id="5c60c-169">Необходимо решить, смогут ли пользователи принимать международные вызовы.</span><span class="sxs-lookup"><span data-stu-id="5c60c-169">You'll need to decide whether your users should be able to make international calls.</span></span> <span data-ttu-id="5c60c-170">По умолчанию включен международный вызов.</span><span class="sxs-lookup"><span data-stu-id="5c60c-170">By default, international calling is enabled.</span></span> <span data-ttu-id="5c60c-171">Вы можете отключить или включить пользователей для международного набора с помощью центра администрирования Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="5c60c-171">You can disable or enable users for international dialing using the online Skype for Business admin center.</span></span>
  
<span data-ttu-id="5c60c-172">Чтобы отключить международные вызовы для каждого пользователя, запустите следующий кодлет в Skype для бизнеса Online PowerShell:</span><span class="sxs-lookup"><span data-stu-id="5c60c-172">To disable international calling on a per user basis, run the following cmdlet in Skype for Business Online PowerShell:</span></span>
  
```powershell
Grant-CsVoiceRoutingPolicy -PolicyName InternationalCallsDisallowed -Identity $user
```

<span data-ttu-id="5c60c-173">Чтобы повторно включить международные вызовы для каждого пользователя после отключения, запустите тот же кодлет, но измените значение **для PolicyName** на *InternationalCallsAllowed*  .</span><span class="sxs-lookup"><span data-stu-id="5c60c-173">To re-enable international calling on a per user basis after it has been disabled, run the same cmdlet, but change the value for **PolicyName** to *InternationalCallsAllowed*  .</span></span>
  
## <a name="assign-users-to-pstn-sites"></a><span data-ttu-id="5c60c-174">Назначение пользователей сайтам PSTN</span><span class="sxs-lookup"><span data-stu-id="5c60c-174">Assign users to PSTN sites</span></span>

<span data-ttu-id="5c60c-175">Используйте удаленный powerShell клиента для назначения сайта пользователям, даже если вы развернули только один сайт.</span><span class="sxs-lookup"><span data-stu-id="5c60c-175">Use tenant remote PowerShell to assign a site to users even if you only deployed a single site.</span></span> <span data-ttu-id="5c60c-176">Чтобы узнать, как установить удаленный сеанс PowerShell, см. в рубке: Настройка компьютера [для Windows PowerShell.](../../../SfbOnline/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)</span><span class="sxs-lookup"><span data-stu-id="5c60c-176">To learn how to establish a remote PowerShell session, see: [Set up your computer for Windows PowerShell](../../../SfbOnline/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span></span>
  
```powershell
# Set the site to users
Set-CsUserPstnSettings -Identity <User Name> -HybridPstnSite <PSTN Site Name>

# Review the site setting for a user
Get-CsUserPstnSettings -Identity <User Name> 

# See all the user settings in one tenant
Get-CsOnlineUser | Get-CsUserPstnSettings
```

> [!NOTE]
> <span data-ttu-id="5c60c-177">Если пользователю не назначен сайт PSTN, гибридное подключение между развертыванием Skype для бизнеса cloud Connector Edition и организацией Microsoft 365 или Office 365 отпадет для использования по умолчанию уровня клиента (одноранговой пункт назначения), чтобы можно было завершить вызовы.</span><span class="sxs-lookup"><span data-stu-id="5c60c-177">If no PSTN site is assigned to a user, hybrid connectivity between your Skype for Business Cloud Connector Edition deployment and your Microsoft 365 or Office 365 organization will fall back to use the tenant level default one (Peer Destination) so that calls can be completed.</span></span> 
  
## <a name="configure-online-hybrid-mediation-server-settings"></a><span data-ttu-id="5c60c-178">Настройка сетевых параметров гибридного сервера-посредника</span><span class="sxs-lookup"><span data-stu-id="5c60c-178">Configure online hybrid Mediation Server Settings</span></span>
<span data-ttu-id="5c60c-179"><a name="BKMK_ConfigureMediationServer"> </a></span><span class="sxs-lookup"><span data-stu-id="5c60c-179"><a name="BKMK_ConfigureMediationServer"> </a></span></span>

<span data-ttu-id="5c60c-180">Когда вызов P2P перенаправят на конференцию PSTN, сервер конференц-связи Skype для бизнеса Online отправит приглашение на сервер посредников облачного соединиттеля.</span><span class="sxs-lookup"><span data-stu-id="5c60c-180">When a P2P call is escalated to a PSTN conference, the Skype for Business Online conferencing server will send an invite to the Cloud Connector Mediation Server.</span></span> <span data-ttu-id="5c60c-181">Чтобы microsoft 365 или Office 365 могли успешно маршрутировать это приглашение, необходимо настроить параметр в клиенте для каждого сервера-посредника облачного соединители следующим образом:</span><span class="sxs-lookup"><span data-stu-id="5c60c-181">To ensure that Microsoft 365 or Office 365 can route this invite successfully, you need to configure a setting in your online tenant for each Cloud Connector Mediation Server as follows:</span></span> 
  
1. <span data-ttu-id="5c60c-182">Создайте пользователя в центре администрирования Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="5c60c-182">Create a user in the Microsoft 365 admin center.</span></span> <span data-ttu-id="5c60c-183">Используйте любое нужное имя пользователя, например "MediationServer1".</span><span class="sxs-lookup"><span data-stu-id="5c60c-183">Use any user name you want, such as "MediationServer1."</span></span>
    
    <span data-ttu-id="5c60c-184">Используйте по умолчанию SIP-домен Cloud Connector (первый домен SIP в файле .ini) в качестве пользовательского домена.</span><span class="sxs-lookup"><span data-stu-id="5c60c-184">Use the default SIP domain of Cloud Connector (the first SIP domain in the .ini file) as the user domain.</span></span>
    
    <span data-ttu-id="5c60c-185">Обратите внимание, что назначение лицензии требуется только для распространения пользователя в онлайн-каталог Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="5c60c-185">Please note that license assignment is only required for the user propagation into the Skype for Business online directory.</span></span> <span data-ttu-id="5c60c-186">Назначьте создаемой учетной записи лицензию Microsoft 365 или Office 365 (например, E5), разрешить до одного часа для распространения изменений, убедитесь, что учетные записи пользователей были правильно заданной в онлайн-каталог Skype для бизнеса, запустив следующий кодлет, а затем удалите лицензию из этой учетной записи.</span><span class="sxs-lookup"><span data-stu-id="5c60c-186">Assign a Microsoft 365 or Office 365 license (such as E5) to the account you create, allow up to one hour for the changes to propagate,verify the user accounts has been provisioned correctly to the Skype for Business online directory by running following cmdlet, then remove the license from this account.</span></span>
    ```powershell
   Get-CsOnlineUser -Identity <UserPrincipalName>
   ```
    
2. <span data-ttu-id="5c60c-187">Запустите удаленный сеанс PowerShell Azure AD с использованием учетных данных глобального или пользовательского администратора, а затем запустите следующий кодлет, чтобы задать отдел учетной записи пользователя Azure AD, настроенной в шаге 1 на "HybridMediationServer":</span><span class="sxs-lookup"><span data-stu-id="5c60c-187">Start a tenant Azure AD remote PowerShell session using your global or user admin credentials, and then run the following cmdlet to set the department for the Azure AD user account configured in step 1 to "HybridMediationServer":</span></span>

   ```powershell
   Set-MsolUser -UserPrincipalName <UserPrincipalName> -Department "HybridMediationServer"
   ```

3. <span data-ttu-id="5c60c-188">Запустите сеанс удаленной службы PowerShell для клиента Skype для бизнеса с помощью учетных данных администратора клиента Skype для бизнеса, а затем запустите следующий комдлет, чтобы настроить сервер-посредник и FQDN edge Server для этой учетной записи пользователя, заменив имя пользователя для учетной записи, созданной на \<DisplayName\> шаге 1:</span><span class="sxs-lookup"><span data-stu-id="5c60c-188">Start a tenant Skype for Business remote PowerShell session using your Skype for Business tenant admin credentials, and then run the following cmdlet to set the Mediation Server and Edge Server FQDN to that user account, replacing \<DisplayName\> with the Display Name of the user for the account you created in step 1:</span></span>
    
   ```powershell
   Set-CsHybridMediationServer -Identity <DisplayName> -Fqdn <MediationServerFQDN> -AccessProxyExternalFqdn <EdgeServerExternalFQDN>
   ```

    <span data-ttu-id="5c60c-189">Для identity используйте имя отображения учетной записи пользователя, созданной для этого сервера-посредника.</span><span class="sxs-lookup"><span data-stu-id="5c60c-189">For Identity, use the Display Name of the user account you created for this Mediation Server.</span></span>
    
    <span data-ttu-id="5c60c-190">Для  *mediationServerFQDN*  используйте внутренний FQDN, определенный для сервера-посредника.</span><span class="sxs-lookup"><span data-stu-id="5c60c-190">For  *MediationServerFQDN*  , use the internal FQDN defined for your Mediation Server.</span></span>
    
    <span data-ttu-id="5c60c-191">Для  *EdgeServerExternalFQDN*  используйте внешний FQDN, определенный для прокси-сервера edge Server Access.</span><span class="sxs-lookup"><span data-stu-id="5c60c-191">For  *EdgeServerExternalFQDN*  , use the external FQDN defined for Edge Server Access Proxy.</span></span> <span data-ttu-id="5c60c-192">Если имеется несколько сайтов PSTN с облачным соединитетелем, выберите сервер edge Server Access Proxy FQDN, назначенный сайту, на котором расположен сервер-посредник.</span><span class="sxs-lookup"><span data-stu-id="5c60c-192">If there are multiple Cloud Connector PSTN sites, choose the Edge Server Access Proxy FQDN assigned to the site where the Mediation Server is located.</span></span>
    
4. <span data-ttu-id="5c60c-193">Если существует несколько серверов-посредников облачного соединителя (несколько сайтов, ha), повторите предыдущие действия для каждого из них.</span><span class="sxs-lookup"><span data-stu-id="5c60c-193">If there are multiple Cloud Connector Mediation Servers (multiple-site, HA), please repeat the previous steps for each of them.</span></span>
