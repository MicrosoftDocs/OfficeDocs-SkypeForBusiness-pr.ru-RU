---
title: Настройка интеграции Cloud Connector с клиентом Office 365
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/15/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.custom: Strat_SB_Hybrid
ms.assetid: 0e2f2395-b890-4d16-aa2d-99d52438b89c
description: Сведения о настройке интеграции Cloud Connector с клиентом Office 365.
ms.openlocfilehash: c8e74353bc9b1201d8e4ff11f27a3542f24cb373
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/28/2018
---
# <a name="configure-cloud-connector-integration-with-your-office-365-tenant"></a><span data-ttu-id="e4b69-103">Настройка интеграции Cloud Connector с клиентом Office 365</span><span class="sxs-lookup"><span data-stu-id="e4b69-103">Configure Cloud Connector integration with your Office 365 tenant</span></span>
 
<span data-ttu-id="e4b69-104">Сведения о настройке интеграции Cloud Connector с клиентом Office 365.</span><span class="sxs-lookup"><span data-stu-id="e4b69-104">Learn how to configure Cloud Connector integration with your Office 365 tenant.</span></span>
  
<span data-ttu-id="e4b69-105">После завершения установки Skype для бизнеса Cloud Connector Edition выполните приведенные в этом разделе действия для настройки развертывания и подключения к клиенту Office 365.</span><span class="sxs-lookup"><span data-stu-id="e4b69-105">Once the Skype for Business Cloud Connector Edition installation is complete, perform the steps in this section to configure your deployment and connect it to your Office 365 tenant.</span></span>
  
## <a name="configure-firewall-settings"></a><span data-ttu-id="e4b69-106">Настройка параметров брандмауэра</span><span class="sxs-lookup"><span data-stu-id="e4b69-106">Configure firewall settings</span></span>

<span data-ttu-id="e4b69-107">Настройте параметры брандмауэра для внутренних и внешних настройках брандмауэра для сети периметра откройте необходимые порты, как описано в [порты и протоколы](plan-skype-for-business-cloud-connector-edition.md#BKMB_Ports) в [Plan for Скайп облаке соединитель для выпуска для бизнеса](plan-skype-for-business-cloud-connector-edition.md).</span><span class="sxs-lookup"><span data-stu-id="e4b69-107">Configure the firewall settings for your internal and external firewall settings for you perimeter network to open the required ports as described in [Ports and protocols](plan-skype-for-business-cloud-connector-edition.md#BKMB_Ports) in [Plan for Skype for Business Cloud Connector Edition](plan-skype-for-business-cloud-connector-edition.md).</span></span>
  
## <a name="set-up-public-switched-telephone-network-pstn-gateways"></a><span data-ttu-id="e4b69-108">Установите шлюзы телефонной сети общего пользования (ТСОП).</span><span class="sxs-lookup"><span data-stu-id="e4b69-108">Set up Public Switched Telephone Network (PSTN) gateways</span></span>

<span data-ttu-id="e4b69-p101">Настройте магистраль для каждого шлюза ТСОП таким образом, чтобы задавались обратные связи с серверами-посредниками для всех устройств. Так как все серверы в пуле используют одинаковое полное доменное имя пула, каждая магистраль должна указывать на одно полное доменное имя или один IP-адрес сервера-посредника, а не на пул серверов-посредников. При настройке магистралей необходимо использовать одинаковые приоритеты.</span><span class="sxs-lookup"><span data-stu-id="e4b69-p101">Set up trunks on each PSTN gateway to point back to Mediation Servers for all appliances. Because the pool FQDN is the same for all servers in the pool, each trunk should point to one Mediation Server FQDN or IP address instead of the Mediation Server pool FQDN. Trunks should be set in the same priority.</span></span>
  
<span data-ttu-id="e4b69-112">Если между серверами-посредниками и шлюзами используется протокол TLS, потребуется настроить для них поддержку MTLS следующим образом.</span><span class="sxs-lookup"><span data-stu-id="e4b69-112">If you are using TLS between Mediation Servers and gateways, you will need to configure the gateways and Mediation Servers to support MTLS as follows:</span></span>
  
1. <span data-ttu-id="e4b69-113">Экспортируйте корневой ЦС с компьютера Active Directory Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="e4b69-113">Export the Root CA from the Cloud Connector Active Directory computer.</span></span>
    
2. <span data-ttu-id="e4b69-114">Выполните инструкции поставщика шлюза ТСОП для импорта корневого ЦС.</span><span class="sxs-lookup"><span data-stu-id="e4b69-114">Follow the PSTN gateway vendor instructions for importing the Root CA.</span></span>
    
3. <span data-ttu-id="e4b69-p102">Импортируйте сертификат корневого ЦС для сертификата, выданного для вашего шлюза на сервере-посреднике. Если вам требуется получить SSL-сертификат для шлюза, это можно сделать с помощью службы ЦС, выполняющейся на компьютере Active Directory Cloud Connector, следующим образом.</span><span class="sxs-lookup"><span data-stu-id="e4b69-p102">Import the Root CA certificate for the certificate issued to your gateway on the Mediation Servers. If you need to obtain an SSL certificate for the gateway, you may do this using the Certificate Authority service running on the Cloud Connector Active Directory computer as follows:</span></span>
    
  - <span data-ttu-id="e4b69-117">Измените существующий шаблон веб-сервера, чтобы разрешить регистрацию пользователям, прошедшим проверку подлинности, или создайте новый шаблон, чтобы настроить другие свойства и разрешить регистрацию для таких пользователей.</span><span class="sxs-lookup"><span data-stu-id="e4b69-117">Modify the existing Web Server template to enable Authenticated users to enroll, or create a new Web Server template to configure other properties and enable Authenticated users to enroll.</span></span> <span data-ttu-id="e4b69-118">[Подробные инструкции см.](https://technet.microsoft.com/en-us/library/cc730705.aspx)</span><span class="sxs-lookup"><span data-stu-id="e4b69-118">For detailed instructions, see [Certificate Templates](https://technet.microsoft.com/en-us/library/cc730705.aspx).</span></span>
    
  - <span data-ttu-id="e4b69-119">Запросите сертификат с помощью оснастки «Сертификаты», выбрав включенный шаблон веб-сервера.</span><span class="sxs-lookup"><span data-stu-id="e4b69-119">Request a certificate using Certificate snap-in selecting the Web Server template that you have enabled.</span></span> <span data-ttu-id="e4b69-120">В поле «Субъект» укажите общее имя, а в поле «Дополнительное имя» — DNS-имя с полным доменным именем шлюза и убедитесь, что в разделе параметров закрытого ключа установлен флажок «Сделать закрытый ключ экспортируемым».</span><span class="sxs-lookup"><span data-stu-id="e4b69-120">Be sure to add Common name in Subject and DNS name in Alternative name with FQDN of the gateway, and confirm on the Private Key that Make private key exportable is selected under key options.</span></span> <span data-ttu-id="e4b69-121">Подробные сведения содержатся в разделе [запрос сертификата](https://technet.microsoft.com/en-us/library/cc730689.aspx).</span><span class="sxs-lookup"><span data-stu-id="e4b69-121">For detailed instructions, see [Request a Certificate](https://technet.microsoft.com/en-us/library/cc730689.aspx).</span></span>
    
4. <span data-ttu-id="e4b69-122">Экспортируйте SSL-сертификат с закрытым ключом и выполните инструкции поставщика шлюза ТСОП по импорту сертификатов.</span><span class="sxs-lookup"><span data-stu-id="e4b69-122">Export the SSL certificate with Private key and follow the instructions from your PSTN gateway vendor for importing the certificate.</span></span>
    
## <a name="update-the-domain-for-your-tenant"></a><span data-ttu-id="e4b69-123">Изменение домена для клиента</span><span class="sxs-lookup"><span data-stu-id="e4b69-123">Update the domain for your tenant</span></span>

<span data-ttu-id="e4b69-124">Вам потребуется выполнить процедуру по изменению домена в Office 365 и убедиться, что вы можете добавлять записи DNS.</span><span class="sxs-lookup"><span data-stu-id="e4b69-124">Make sure that you've completed the steps to update your domain in Office 365 and have the ability to add DNS records.</span></span> <span data-ttu-id="e4b69-125">Дополнительные сведения о том, как настроить свой домен в Office 365 можно [видео: Настройка домена в Office 365](https://support.office.com/en-us/article/Video-Set-up-your-domain-in-Office-365-703dfec1-882d-4e33-b647-937f731887b7?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="e4b69-125">For more information about how to set up your domain in Office 365, see [Video: Set up your domain in Office 365](https://support.office.com/en-us/article/Video-Set-up-your-domain-in-Office-365-703dfec1-882d-4e33-b647-937f731887b7?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
## <a name="add-dns-records-in-office-365-for-your-edge"></a><span data-ttu-id="e4b69-126">Добавление записей DNS в Office 365 для пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="e4b69-126">Add DNS records in Office 365 for your Edge</span></span>

<span data-ttu-id="e4b69-127">Добавьте следующие записи DNS в клиент Office 365.</span><span class="sxs-lookup"><span data-stu-id="e4b69-127">Add the following DNS records to your Office 365 tenant.</span></span> <span data-ttu-id="e4b69-128">Сведения о добавлении записи DNS для клиента Office 365 можно [добавления или изменения настраиваемых DNS-записи в Office 365](https://support.office.com/en-us/article/Add-or-edit-custom-DNS-records-in-Office-365-AF00A516-DD39-4EDA-AF3E-1EAF686C8DC9?ui=en-US&amp;rs=en-US&amp;ad=US&amp;fromAR=1).</span><span class="sxs-lookup"><span data-stu-id="e4b69-128">For information about how to add DNS records to your Office 365 tenant, see [Add or edit custom DNS records in Office 365](https://support.office.com/en-us/article/Add-or-edit-custom-DNS-records-in-Office-365-AF00A516-DD39-4EDA-AF3E-1EAF686C8DC9?ui=en-US&amp;rs=en-US&amp;ad=US&amp;fromAR=1).</span></span>
  
1. <span data-ttu-id="e4b69-129">Добавьте запись DNS A для пограничной службы доступа.</span><span class="sxs-lookup"><span data-stu-id="e4b69-129">Add a DNS A record for Access Edge.</span></span>
    
2. <span data-ttu-id="e4b69-p107">Записи SRV будут автоматически созданы скриптами развертывания и Office 365. Убедитесь, что на пограничном компоненте можно найти следующие две службы SIP: _sip и _sipfederationtls.</span><span class="sxs-lookup"><span data-stu-id="e4b69-p107">SRV records will automatically be created by Office 365 and the deployment scripts. Confirm that you can look up the following two SIP services on the Edge: _sip and _sipfederationtls.</span></span>
    
     ![Подтверждение записей SRV](../../media/3c353a29-6dcc-4ed3-98db-3a6bed3e929e.png)
  
## <a name="set-up-hybrid-connectivity-between-cloud-connector-edition-and-office-365"></a><span data-ttu-id="e4b69-133">Настройка гибридных подключений между Cloud Connector Edition и Office 365</span><span class="sxs-lookup"><span data-stu-id="e4b69-133">Set up hybrid connectivity between Cloud Connector Edition and Office 365</span></span>

<span data-ttu-id="e4b69-134">Чтобы настроить гибридного подключения между вашей Скайп для развертывания Business Cloud соединителя Edition и клиента Office 365, выполните следующий командлет в удаленный сеанс PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e4b69-134">To configure hybrid connectivity between your Skype for Business Cloud Connector Edition deployment and your Office 365 tenant, run the following cmdlet in a remote PowerShell session.</span></span> <span data-ttu-id="e4b69-135">Чтобы узнать, как установить удаленный сеанс PowerShell, обратитесь к разделу: [С помощью Windows PowerShell для управления Скайп для бизнеса в Интернет](https://technet.microsoft.com/en-us/library/dn362831%28v=ocs.15%29.aspx).</span><span class="sxs-lookup"><span data-stu-id="e4b69-135">To learn how to establish a remote PowerShell session, see: [Using Windows PowerShell to manage Skype for Business Online](https://technet.microsoft.com/en-us/library/dn362831%28v=ocs.15%29.aspx).</span></span>
  
<span data-ttu-id="e4b69-136">Этот командлет задает внешнее полное доменное имя пограничного сервера доступа.</span><span class="sxs-lookup"><span data-stu-id="e4b69-136">The cmdlet sets the Access Edge external FQDN.</span></span> <span data-ttu-id="e4b69-137">В первом команды \<внешнее полное доменное имя пограничного сервера доступа\> , должен быть для роли SIP пограничного сервера доступа.</span><span class="sxs-lookup"><span data-stu-id="e4b69-137">In the first of the commands, the \<External Access Edge FQDN\> should be the one for the SIP Access Edge role.</span></span> <span data-ttu-id="e4b69-138">По умолчанию это должен быть ap.\<доменное имя\>.</span><span class="sxs-lookup"><span data-stu-id="e4b69-138">By default, this should be ap.\<Domain Name\>.</span></span>
  
```
Set-CsTenantHybridConfiguration -PeerDestination <External Access Edge FQDN> -UseOnPremDialPlan $false
Set-CsTenantFederationConfiguration -SharedSipAddressSpace $True
```

> [!NOTE]
> <span data-ttu-id="e4b69-139">Полное доменное имя пограничного внешнего доступа используется для назначения Peer необходимо задать для сайта ТСОП, который будет использоваться только как возврат в случае, если пользователь не будет назначен на сайт PSTN.</span><span class="sxs-lookup"><span data-stu-id="e4b69-139">The External Access Edge FQDN used for Peer Destination should be set to a PSTN site that will only be used as a fallback in case a user isn't assigned to a PSTN site.</span></span> <span data-ttu-id="e4b69-140">Дополнительные сведения можно [Развернуть один сайт в облаке соединителя](deploy-a-single-site-in-cloud-connector.md) и [развертывания нескольких сайтов в облаке соединителя](deploy-multiple-sites-in-cloud-connector.md).</span><span class="sxs-lookup"><span data-stu-id="e4b69-140">For more information, see [Deploy a single site in Cloud Connector](deploy-a-single-site-in-cloud-connector.md) and [Deploy multiple sites in Cloud Connector](deploy-multiple-sites-in-cloud-connector.md).</span></span> 
  
## <a name="set-up-pstn-gateways"></a><span data-ttu-id="e4b69-141">Настройка шлюзов ТСОП</span><span class="sxs-lookup"><span data-stu-id="e4b69-141">Set up PSTN gateways</span></span>

<span data-ttu-id="e4b69-p111">Настройте магистраль для каждого шлюза ТСОП таким образом, чтобы задавались обратные связи с серверами-посредниками для всех устройств. Так как все серверы в пуле используют одинаковое полное доменное имя пула, каждая магистраль должна указывать на одно полное доменное имя или один IP-адрес сервера-посредника, а не на пул серверов-посредников. При настройке магистралей необходимо использовать одинаковые приоритеты.</span><span class="sxs-lookup"><span data-stu-id="e4b69-p111">Set up trunks on each PSTN gateway to point back to Mediation Servers for all appliances. Each trunk should point to one Mediation Server FQDN or IP address instead of the Mediation Server pool FQDN because the pool FQDN is the same for all servers in the pool. Trunks should be set in the same priority.</span></span>
  
<span data-ttu-id="e4b69-145">Если между серверами-посредниками и шлюзами используется протокол TLS, потребуется настроить для них поддержку MTLS следующим образом.</span><span class="sxs-lookup"><span data-stu-id="e4b69-145">If you are using TLS between Mediation Servers and gateways, you will need to configure the gateways and Mediation Servers to support MTLS as follows:</span></span>
  
1. <span data-ttu-id="e4b69-146">Экспортируйте корневой ЦС с компьютера Active Directory Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="e4b69-146">Export the Root CA from the Cloud Connector Active Directory computer.</span></span>
    
2. <span data-ttu-id="e4b69-147">Выполните инструкции поставщика шлюза ТСОП для импорта корневого ЦС.</span><span class="sxs-lookup"><span data-stu-id="e4b69-147">Follow the PSTN gateway vendor instructions for importing the Root CA.</span></span>
    
3. <span data-ttu-id="e4b69-p112">Импортируйте сертификат корневого ЦС для сертификата, выданного для вашего шлюза на сервере-посреднике. Если вам требуется получить SSL-сертификат для шлюза, это можно сделать с помощью службы ЦС, выполняющейся на компьютере Active Directory Cloud Connector, следующим образом.</span><span class="sxs-lookup"><span data-stu-id="e4b69-p112">Import the Root CA certificate for the certificate issued to your gateway on the Mediation Servers. If you need to obtain an SSL certificate for the gateway, you may do this using the Certificate Authority service running on the Cloud Connector Active Directory computer as follows:</span></span>
    
  - <span data-ttu-id="e4b69-150">Измените существующий шаблон веб-сервера, чтобы разрешить регистрацию пользователям, прошедшим проверку подлинности, или создайте новый шаблон, чтобы настроить другие свойства и разрешить регистрацию для таких пользователей.</span><span class="sxs-lookup"><span data-stu-id="e4b69-150">Modify the existing Web Server template to enable Authenticated users to Enroll, or create a new Web Server template to configure other properties and enable Authenticated users to enroll.</span></span> <span data-ttu-id="e4b69-151">[Подробные инструкции см.](https://technet.microsoft.com/library/cc730705.aspx)</span><span class="sxs-lookup"><span data-stu-id="e4b69-151">For detailed instructions, see [Certificate Templates](https://technet.microsoft.com/library/cc730705.aspx).</span></span>
    
  - <span data-ttu-id="e4b69-152">Запросите сертификат с помощью оснастки «Сертификаты», выбрав включенный шаблон веб-сервера.</span><span class="sxs-lookup"><span data-stu-id="e4b69-152">Request a certificate using Certificate snap-in selecting the Web Server template that you have enabled.</span></span> <span data-ttu-id="e4b69-153">В поле «Субъект» укажите общее имя, а в поле «Дополнительное имя» — DNS-имя с полным доменным именем шлюза и убедитесь, что в разделе параметров закрытого ключа установлен флажок «Сделать закрытый ключ экспортируемым».</span><span class="sxs-lookup"><span data-stu-id="e4b69-153">Be sure to add Common name in Subject and DNS name in Alternative name with FQDN of the gateway, and confirm on the Private Key that Make private key exportable is selected under key options.</span></span> <span data-ttu-id="e4b69-154">Подробные сведения содержатся в разделе [запрос сертификата](https://technet.microsoft.com/library/cc730689.aspx).</span><span class="sxs-lookup"><span data-stu-id="e4b69-154">For detailed instructions, see [Request a Certificate](https://technet.microsoft.com/library/cc730689.aspx).</span></span>
    
4. <span data-ttu-id="e4b69-155">Экспортируйте SSL-сертификат с закрытым ключом и выполните инструкции поставщика шлюза ТСОП по импорту сертификатов.</span><span class="sxs-lookup"><span data-stu-id="e4b69-155">Export the SSL certificate with Private key and follow the instructions from your PSTN gateway vendor for importing the certificate.</span></span>
    
5. <span data-ttu-id="e4b69-156">Шлюзы ТСОП на одном сайте ТСОП должны подключаться только к серверам-посредникам на том же сайте.</span><span class="sxs-lookup"><span data-stu-id="e4b69-156">PSTN gateway(s) in one PSTN site should only connect to the Mediation Server(s) in the same site.</span></span>
    
## <a name="set-up-your-users-in-office-365"></a><span data-ttu-id="e4b69-157">Настройка пользователей Office 365</span><span class="sxs-lookup"><span data-stu-id="e4b69-157">Set up your users in Office 365</span></span>

<span data-ttu-id="e4b69-158">Войдите на портал администрирования Office 365, добавьте пользователей, для которых будут включены службы голосовой связи через Интернет, после чего назначьте этим пользователям лицензию E5 или лицензию E3 на подключаемый модуль телефонной системы Office 365.</span><span class="sxs-lookup"><span data-stu-id="e4b69-158">Log in to the Office 365 admin portal, add the users that will be enabled for online voice services, and assign an E5 license or Phone System in Office 365 add-on to the E3 license to these users.</span></span> <span data-ttu-id="e4b69-159">Сведения о добавлении пользователей можно [Добавить пользователей в Office 365 для бизнеса](https://support.office.com/en-US/article/Add-users-to-Office-365-for-business-435ccec3-09dd-4587-9ebd-2f3cad6bc2bc).</span><span class="sxs-lookup"><span data-stu-id="e4b69-159">For information about adding users, see [Add users to Office 365 for business](https://support.office.com/en-US/article/Add-users-to-Office-365-for-business-435ccec3-09dd-4587-9ebd-2f3cad6bc2bc).</span></span>
  
## <a name="enable-users-for-phone-system-in-office-365-voice-and-voicemail-services"></a><span data-ttu-id="e4b69-160">Включение голосовых служб и голосовой почты телефонной системы в Office 365 для пользователей</span><span class="sxs-lookup"><span data-stu-id="e4b69-160">Enable users for Phone System in Office 365 voice and voicemail services</span></span>

<span data-ttu-id="e4b69-161">Добавив пользователей в Office 365, включите для их учетных записей голосовые службы телефонной системы в Office 365, включая голосовую почту.</span><span class="sxs-lookup"><span data-stu-id="e4b69-161">After adding your users to Office 365, enable their accounts for Phone System in Office 365 voice services, including voicemail.</span></span> <span data-ttu-id="e4b69-162">Для этого необходимо войти в клиент Office 365, используя учетную запись с ролью глобального администратора Office 365, которой разрешено выполнение удаленных команд PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e4b69-162">To enable these capabilities, you must log in to your Office 365 tenant with an account that is an Office 365 Global Administrator role, and be able to run remote PowerShell.</span></span> <span data-ttu-id="e4b69-163">Чтобы узнать, как установить удаленный сеанс PowerShell, обратитесь к разделу: [С помощью Windows PowerShell для управления Скайп для бизнеса в Интернет](https://technet.microsoft.com/en-us/library/dn362831%28v=ocs.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="e4b69-163">To learn how to establish a remote PowerShell session, see: [Using Windows PowerShell to manage Skype for Business Online](https://technet.microsoft.com/en-us/library/dn362831%28v=ocs.15%29.aspx)</span></span>
  
- <span data-ttu-id="e4b69-164">Назначьте политику для пользователя и задайте пользователя business голосовой связи телефонного номера, которые можно указать в значение параметра **Identity** .</span><span class="sxs-lookup"><span data-stu-id="e4b69-164">Assign the policy to your user and configure the user's business voice phone number, which you specify with the value of the **Identity** parameter:</span></span>
    
  ```
  Set-CsUser -Identity "<User name>" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true -OnPremLineURI <tel:+phonenumber>
  ```

    > [!NOTE]
    > <span data-ttu-id="e4b69-165">Удостоверение (Identity) пользователя можно также задать по его адресу SIP, имени участника-пользователя (UPN), имени домена и имени пользователя (домен\имя_пользователя) и по отображаемому имени Active Directory (Bob Kelly). </span><span class="sxs-lookup"><span data-stu-id="e4b69-165">You can also specify a user's Identity by their SIP address, User Principal name (UPN), domain name and username (domain\username), and display name in Active Directory ("Bob Kelly").</span></span> 
  
<span data-ttu-id="e4b69-166">Чтобы убедиться, что пользователи добавлены и включены, можно выполнить следующий сценарий:</span><span class="sxs-lookup"><span data-stu-id="e4b69-166">You can then verify that the users were added and enabled using the following script:</span></span>
  
```
# Input the user name you want to verify
$user = Get-CsOnlineUser <User name>

# For a hybrid user, the value of $user.EnterpriseVoiceEnabled should be True
$user.EnterpriseVoiceEnabled

# For a hybrid user, the value of $user.HostedVoiceMail should be True
$user.HostedVoiceMail

# For a hybrid user, the value of $user.VoicePolicy should be "HybridVoice"
$user.VoicePolicy
```

<span data-ttu-id="e4b69-p117">Вам потребуется решить, могут ли пользователи выполнять международные звонки. По умолчанию эта возможность включена. Для включения и отключения международных звонков используется центр администрирования Skype для бизнеса в Интернете.</span><span class="sxs-lookup"><span data-stu-id="e4b69-p117">You'll need to decide whether your users should be able to make international calls. By default, international calling is enabled. You can disable or enable users for international dialing using the online Skype for Business admin center.</span></span>
  
<span data-ttu-id="e4b69-170">Чтобы отключить международные звонки для отдельных пользователей, выполните следующий командлет в консоли PowerShell Skype для бизнеса Online:</span><span class="sxs-lookup"><span data-stu-id="e4b69-170">To disable international calling on a per user basis, run the following cmdlet in Skype for Business Online PowerShell:</span></span>
  
```
Grant-CsVoiceRoutingPolicy -PolicyName InternationalCallsDisallowed -Identity $user
```

<span data-ttu-id="e4b69-171">Чтобы повторно включить международных вызов на уровне пользователя после он отключен, выполните командлет же, но измените значение параметра **PolicyName** *InternationalCallsAllowed* .</span><span class="sxs-lookup"><span data-stu-id="e4b69-171">To re-enable international calling on a per user basis after it has been disabled, run the same cmdlet, but change the value for **PolicyName** to *InternationalCallsAllowed*  .</span></span>
  
## <a name="assign-users-to-pstn-sites"></a><span data-ttu-id="e4b69-172">Назначение пользователей сайтам ТСОП</span><span class="sxs-lookup"><span data-stu-id="e4b69-172">Assign users to PSTN sites</span></span>

<span data-ttu-id="e4b69-173">Используйте удаленную консоль PowerShell клиента, чтобы назначить сайт пользователям, даже если развернут только один сайт.</span><span class="sxs-lookup"><span data-stu-id="e4b69-173">Use tenant remote PowerShell to assign a site to users even if you only deployed a single site.</span></span> <span data-ttu-id="e4b69-174">Чтобы узнать, как установить удаленный сеанс PowerShell, обратитесь к разделу: [С помощью Windows PowerShell для управления Скайп для бизнеса в Интернет](https://technet.microsoft.com/en-us/library/dn362831%28v=ocs.15%29.aspx).</span><span class="sxs-lookup"><span data-stu-id="e4b69-174">To learn how to establish a remote PowerShell session, see: [Using Windows PowerShell to manage Skype for Business Online](https://technet.microsoft.com/en-us/library/dn362831%28v=ocs.15%29.aspx).</span></span>
  
```
# Set the site to users
Set-CsUserPstnSettings -Identity <User Name> -HybridPstnSite <PSTN Site Name>

# Review the site setting for a user
Get-CsUserPstnSettings -Identity <User Name> 

# See all the user settings in one tenant
Get-CsOnlineUser | Get-CsUserPstnSettings
```

> [!NOTE]
> <span data-ttu-id="e4b69-175">Если пользователю не назначен сайт ТСОП, при гибридном подключении между развертыванием Skype для бизнеса Cloud Connector Edition и клиентом Office 365 будет выполнен откат до использования сайта по умолчанию уровня клиента (одноранговое назначение), чтобы пользователи могли выполнять звонки.</span><span class="sxs-lookup"><span data-stu-id="e4b69-175">If no PSTN site is assigned to a user, hybrid connectivity between your Skype for Business Cloud Connector Edition deployment and your Office 365 tenant will fall back to use the tenant level default one (Peer Destination) so that calls can be completed.</span></span> 
  
## <a name="configure-online-hybrid-mediation-server-settings"></a><span data-ttu-id="e4b69-176">Настройка параметров гибридного сервера-посредника в Интернете</span><span class="sxs-lookup"><span data-stu-id="e4b69-176">Configure online hybrid Mediation Server Settings</span></span>
<span data-ttu-id="e4b69-177"><a name="BKMK_ConfigureMediationServer"> </a></span><span class="sxs-lookup"><span data-stu-id="e4b69-177"></span></span>

<span data-ttu-id="e4b69-178">При звонка P2P перерастает в сеанс конференции PSTN, Скайп для бизнеса в Интернет сервера конференц-связи отправляет приглашение сервера-посредника соединителя облака.</span><span class="sxs-lookup"><span data-stu-id="e4b69-178">When a P2P call is escalated to a PSTN conference, the Skype for Business Online conferencing server will send an invite to the Cloud Connector Mediation Server.</span></span> <span data-ttu-id="e4b69-179">Убедитесь, что Office 365 могут перенаправлять этой пригласить успешно, необходимо настроить параметр интерактивного клиента для каждого сервера-посредника соединителя облачных следующим образом:</span><span class="sxs-lookup"><span data-stu-id="e4b69-179">To ensure that Office 365 can route this invite successfully, you need to configure a setting in your online tenant for each Cloud Connector Mediation Server as follows:</span></span> 
  
1. <span data-ttu-id="e4b69-180">Создайте пользователя на портале администрирования Office 365.</span><span class="sxs-lookup"><span data-stu-id="e4b69-180">Create a user in the Office 365 admin portal.</span></span> <span data-ttu-id="e4b69-181">Используйте любое имя пользователя, который будет, например «MediationServer1».</span><span class="sxs-lookup"><span data-stu-id="e4b69-181">Use any user name you want, such as "MediationServer1."</span></span>
    
    <span data-ttu-id="e4b69-182">Используйте домен SIP по умолчанию соединителя облака (первого домена SIP в INI-файл) в качестве пользователя домена.</span><span class="sxs-lookup"><span data-stu-id="e4b69-182">Use the default SIP domain of Cloud Connector (the first SIP domain in the .ini file) as the user domain.</span></span>
    
    <span data-ttu-id="e4b69-p121">Не назначайте созданной учетной записи лицензии Office 365 (например, E5). Сначала дождитесь, пока завершится синхронизация с Office 365 Active Directory.</span><span class="sxs-lookup"><span data-stu-id="e4b69-p121">Do not assign any Office 365 licenses (such as E5) to the account you create. Wait for Office 365 AD sync to complete.</span></span>
    
2. <span data-ttu-id="e4b69-185">Клиент удаленного сеанса PowerShell с помощью вашего клиента учетные данные администратора и выполните следующий командлет, чтобы задать сервер-посредник и полное доменное имя пограничного сервера для этого пользователя учетной записи, замена \<DisplayName\> с отображаемым именем пользователя Учетная запись, которую вы создали:</span><span class="sxs-lookup"><span data-stu-id="e4b69-185">Start a tenant remote PowerShell session using your tenant admin credentials, and then run the following cmdlet to set the Mediation Server and Edge Server FQDN to that user account, replacing \<DisplayName\> with the Display Name of the user for the account you created:</span></span>
    
  ```
  Set-CsHybridMediationServer -Identity <DisplayName> -Fqdn <MediationServerFQDN> -AccessProxyExternalFqdn <EdgeServerExternalFQDN>
  ```

    <span data-ttu-id="e4b69-186">В качестве параметра Identity укажите отображаемое имя учетной записи пользователя Office 365, которая была создана для этого сервера-посредника.</span><span class="sxs-lookup"><span data-stu-id="e4b69-186">For Identity, use the Display Name of the Office 365 user account you created for this Mediation Server.</span></span>
    
    <span data-ttu-id="e4b69-187">Для *MediationServerFQDN* можно используйте внутреннее полное доменное имя, определенное для сервера-посредника.</span><span class="sxs-lookup"><span data-stu-id="e4b69-187">For  *MediationServerFQDN*  , use the internal FQDN defined for your Mediation Server.</span></span>
    
    <span data-ttu-id="e4b69-188">Для *EdgeServerExternalFQDN* можно используйте внешнее полное доменное имя, определенное для прокси-сервера доступа пограничного сервера.</span><span class="sxs-lookup"><span data-stu-id="e4b69-188">For  *EdgeServerExternalFQDN*  , use the external FQDN defined for Edge Server Access Proxy.</span></span> <span data-ttu-id="e4b69-189">При наличии нескольких сайтов ТСОП выберите полное доменное имя пограничного прокси-сервера доступа, назначенное сайту, на котором размещается сервер-посредник.</span><span class="sxs-lookup"><span data-stu-id="e4b69-189">If there are multiple Cloud Connector PSTN sites, choose the Edge Server Access Proxy FQDN assigned to the site where the Mediation Server is located.</span></span>
    
3. <span data-ttu-id="e4b69-190">	При наличии нескольких серверов-посредников Cloud Connector (несколько сайтов, высокая доступность) повторите предыдущие шаги для каждого из них.</span><span class="sxs-lookup"><span data-stu-id="e4b69-190">If there are multiple Cloud Connector Mediation Servers (multiple-site, HA), please repeat the previous steps for each of them.</span></span>
    

