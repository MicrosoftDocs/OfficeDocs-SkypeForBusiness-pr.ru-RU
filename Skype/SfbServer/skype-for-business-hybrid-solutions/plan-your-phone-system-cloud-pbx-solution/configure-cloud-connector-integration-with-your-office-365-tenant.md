---
title: Настройка интеграции Cloud Connector с клиентом Office 365
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/15/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 0e2f2395-b890-4d16-aa2d-99d52438b89c
description: Сведения о настройке интеграции Cloud Connector с клиентом Office 365.
ms.openlocfilehash: d5ae0b70a22219ee0430908bd3b3752d6ebd6357
ms.sourcegitcommit: abc0f95ef0efe15a8c38cc27a3991abf7480c30e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/08/2018
ms.locfileid: "20211153"
---
# <a name="configure-cloud-connector-integration-with-your-office-365-tenant"></a><span data-ttu-id="a6483-103">Настройка интеграции Cloud Connector с клиентом Office 365</span><span class="sxs-lookup"><span data-stu-id="a6483-103">Configure Cloud Connector integration with your Office 365 tenant</span></span>
 
<span data-ttu-id="a6483-104">Сведения о настройке интеграции Cloud Connector с клиентом Office 365.</span><span class="sxs-lookup"><span data-stu-id="a6483-104">Learn how to configure Cloud Connector integration with your Office 365 tenant.</span></span>
  
<span data-ttu-id="a6483-105">После завершения установки Skype для бизнеса Cloud Connector Edition выполните приведенные в этом разделе действия для настройки развертывания и подключения к клиенту Office 365.</span><span class="sxs-lookup"><span data-stu-id="a6483-105">Once the Skype for Business Cloud Connector Edition installation is complete, perform the steps in this section to configure your deployment and connect it to your Office 365 tenant.</span></span>
  
## <a name="configure-firewall-settings"></a><span data-ttu-id="a6483-106">Настройка параметров брандмауэра</span><span class="sxs-lookup"><span data-stu-id="a6483-106">Configure firewall settings</span></span>

<span data-ttu-id="a6483-107">Настройте параметры брандмауэра для внутренних и внешних настройках брандмауэра для сети периметра откройте необходимые порты, как описано в [порты и протоколы](plan-skype-for-business-cloud-connector-edition.md#BKMB_Ports) в [Plan for Скайп облаке соединитель для выпуска для бизнеса](plan-skype-for-business-cloud-connector-edition.md).</span><span class="sxs-lookup"><span data-stu-id="a6483-107">Configure the firewall settings for your internal and external firewall settings for you perimeter network to open the required ports as described in [Ports and protocols](plan-skype-for-business-cloud-connector-edition.md#BKMB_Ports) in [Plan for Skype for Business Cloud Connector Edition](plan-skype-for-business-cloud-connector-edition.md).</span></span>
  
## <a name="set-up-public-switched-telephone-network-pstn-gateways"></a><span data-ttu-id="a6483-108">Установите шлюзы телефонной сети общего пользования (ТСОП).</span><span class="sxs-lookup"><span data-stu-id="a6483-108">Set up Public Switched Telephone Network (PSTN) gateways</span></span>

<span data-ttu-id="a6483-p101">Настройте магистраль для каждого шлюза ТСОП таким образом, чтобы задавались обратные связи с серверами-посредниками для всех устройств. Так как все серверы в пуле используют одинаковое полное доменное имя пула, каждая магистраль должна указывать на одно полное доменное имя или один IP-адрес сервера-посредника, а не на пул серверов-посредников. При настройке магистралей необходимо использовать одинаковые приоритеты.</span><span class="sxs-lookup"><span data-stu-id="a6483-p101">Set up trunks on each PSTN gateway to point back to Mediation Servers for all appliances. Because the pool FQDN is the same for all servers in the pool, each trunk should point to one Mediation Server FQDN or IP address instead of the Mediation Server pool FQDN. Trunks should be set in the same priority.</span></span>
  
<span data-ttu-id="a6483-112">Если между серверами-посредниками и шлюзами используется протокол TLS, потребуется настроить для них поддержку MTLS следующим образом.</span><span class="sxs-lookup"><span data-stu-id="a6483-112">If you are using TLS between Mediation Servers and gateways, you will need to configure the gateways and Mediation Servers to support MTLS as follows:</span></span>
  
1. <span data-ttu-id="a6483-113">Экспортируйте корневой ЦС с компьютера Active Directory Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="a6483-113">Export the Root CA from the Cloud Connector Active Directory computer.</span></span>
    
2. <span data-ttu-id="a6483-114">Выполните инструкции поставщика шлюза ТСОП для импорта корневого ЦС.</span><span class="sxs-lookup"><span data-stu-id="a6483-114">Follow the PSTN gateway vendor instructions for importing the Root CA.</span></span>
    
3. <span data-ttu-id="a6483-p102">Импортируйте сертификат корневого ЦС для сертификата, выданного для вашего шлюза на сервере-посреднике. Если вам требуется получить SSL-сертификат для шлюза, это можно сделать с помощью службы ЦС, выполняющейся на компьютере Active Directory Cloud Connector, следующим образом.</span><span class="sxs-lookup"><span data-stu-id="a6483-p102">Import the Root CA certificate for the certificate issued to your gateway on the Mediation Servers. If you need to obtain an SSL certificate for the gateway, you may do this using the Certificate Authority service running on the Cloud Connector Active Directory computer as follows:</span></span>
    
  - <span data-ttu-id="a6483-117">Измените существующий шаблон веб-сервера, чтобы разрешить регистрацию пользователям, прошедшим проверку подлинности, или создайте новый шаблон, чтобы настроить другие свойства и разрешить регистрацию для таких пользователей.</span><span class="sxs-lookup"><span data-stu-id="a6483-117">Modify the existing Web Server template to enable Authenticated users to enroll, or create a new Web Server template to configure other properties and enable Authenticated users to enroll.</span></span> <span data-ttu-id="a6483-118">[Подробные инструкции см.](https://technet.microsoft.com/en-us/library/cc730705.aspx)</span><span class="sxs-lookup"><span data-stu-id="a6483-118">For detailed instructions, see [Certificate Templates](https://technet.microsoft.com/en-us/library/cc730705.aspx).</span></span>
    
  - <span data-ttu-id="a6483-119">Запросите сертификат с помощью оснастки «Сертификаты», выбрав включенный шаблон веб-сервера.</span><span class="sxs-lookup"><span data-stu-id="a6483-119">Request a certificate using Certificate snap-in selecting the Web Server template that you have enabled.</span></span> <span data-ttu-id="a6483-120">В поле «Субъект» укажите общее имя, а в поле «Дополнительное имя» — DNS-имя с полным доменным именем шлюза и убедитесь, что в разделе параметров закрытого ключа установлен флажок «Сделать закрытый ключ экспортируемым».</span><span class="sxs-lookup"><span data-stu-id="a6483-120">Be sure to add Common name in Subject and DNS name in Alternative name with FQDN of the gateway, and confirm on the Private Key that Make private key exportable is selected under key options.</span></span> 
    
4. <span data-ttu-id="a6483-121">Экспортируйте SSL-сертификат с закрытым ключом и выполните инструкции поставщика шлюза ТСОП по импорту сертификатов.</span><span class="sxs-lookup"><span data-stu-id="a6483-121">Export the SSL certificate with Private key and follow the instructions from your PSTN gateway vendor for importing the certificate.</span></span>
    
## <a name="update-the-domain-for-your-tenant"></a><span data-ttu-id="a6483-122">Изменение домена для клиента</span><span class="sxs-lookup"><span data-stu-id="a6483-122">Update the domain for your tenant</span></span>

<span data-ttu-id="a6483-123">Вам потребуется выполнить процедуру по изменению домена в Office 365 и убедиться, что вы можете добавлять записи DNS.</span><span class="sxs-lookup"><span data-stu-id="a6483-123">Make sure that you've completed the steps to update your domain in Office 365 and have the ability to add DNS records.</span></span> <span data-ttu-id="a6483-124">Дополнительные сведения о том, как настроить свой домен в Office 365 можно [Добавить домен в Office 365](https://support.office.com/en-us/article/Add-a-domain-to-Office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611).</span><span class="sxs-lookup"><span data-stu-id="a6483-124">For more information about how to set up your domain in Office 365, see [Add a domain to Office 365](https://support.office.com/en-us/article/Add-a-domain-to-Office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611).</span></span>
  
## <a name="add-dns-records-in-office-365-for-your-edge"></a><span data-ttu-id="a6483-125">Добавление записей DNS в Office 365 для пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="a6483-125">Add DNS records in Office 365 for your Edge</span></span>

<span data-ttu-id="a6483-126">Добавьте следующие записи DNS в клиент Office 365.</span><span class="sxs-lookup"><span data-stu-id="a6483-126">Add the following DNS records to your Office 365 tenant.</span></span> <span data-ttu-id="a6483-127">Сведения о добавлении записи DNS для клиента Office 365 можно [добавления или изменения настраиваемых DNS-записи в Office 365](https://support.office.com/en-us/article/Add-or-edit-custom-DNS-records-in-Office-365-AF00A516-DD39-4EDA-AF3E-1EAF686C8DC9?ui=en-US&amp;rs=en-US&amp;ad=US&amp;fromAR=1).</span><span class="sxs-lookup"><span data-stu-id="a6483-127">For information about how to add DNS records to your Office 365 tenant, see [Add or edit custom DNS records in Office 365](https://support.office.com/en-us/article/Add-or-edit-custom-DNS-records-in-Office-365-AF00A516-DD39-4EDA-AF3E-1EAF686C8DC9?ui=en-US&amp;rs=en-US&amp;ad=US&amp;fromAR=1).</span></span>
  
1. <span data-ttu-id="a6483-128">Добавьте запись DNS A для пограничной службы доступа.</span><span class="sxs-lookup"><span data-stu-id="a6483-128">Add a DNS A record for Access Edge.</span></span>
    
2. <span data-ttu-id="a6483-p107">Записи SRV будут автоматически созданы скриптами развертывания и Office 365. Убедитесь, что на пограничном компоненте можно найти следующие две службы SIP: _sip и _sipfederationtls.</span><span class="sxs-lookup"><span data-stu-id="a6483-p107">SRV records will automatically be created by Office 365 and the deployment scripts. Confirm that you can look up the following two SIP services on the Edge: _sip and _sipfederationtls.</span></span>
    
     ![Подтверждение записей SRV](../../media/3c353a29-6dcc-4ed3-98db-3a6bed3e929e.png)
  
## <a name="set-up-hybrid-connectivity-between-cloud-connector-edition-and-office-365"></a><span data-ttu-id="a6483-132">Настройка гибридных подключений между Cloud Connector Edition и Office 365</span><span class="sxs-lookup"><span data-stu-id="a6483-132">Set up hybrid connectivity between Cloud Connector Edition and Office 365</span></span>

<span data-ttu-id="a6483-133">Чтобы настроить гибридного подключения между вашей Скайп для развертывания Business Cloud соединителя Edition и клиента Office 365, выполните следующий командлет в удаленный сеанс PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a6483-133">To configure hybrid connectivity between your Skype for Business Cloud Connector Edition deployment and your Office 365 tenant, run the following cmdlet in a remote PowerShell session.</span></span> <span data-ttu-id="a6483-134">Чтобы узнать, как установить удаленный сеанс PowerShell, обратитесь к разделу: [Настройка компьютера для Windows PowerShell](https://technet.microsoft.com/en-us/library/dn362831%28v=ocs.15%29.aspx).</span><span class="sxs-lookup"><span data-stu-id="a6483-134">To learn how to establish a remote PowerShell session, see: [Set up your computer for Windows PowerShell](https://technet.microsoft.com/en-us/library/dn362831%28v=ocs.15%29.aspx).</span></span>
  
<span data-ttu-id="a6483-135">Этот командлет задает внешнее полное доменное имя пограничного сервера доступа.</span><span class="sxs-lookup"><span data-stu-id="a6483-135">The cmdlet sets the Access Edge external FQDN.</span></span> <span data-ttu-id="a6483-136">В первом команды \<внешнее полное доменное имя пограничного сервера доступа\> , должен быть для роли SIP пограничного сервера доступа.</span><span class="sxs-lookup"><span data-stu-id="a6483-136">In the first of the commands, the \<External Access Edge FQDN\> should be the one for the SIP Access Edge role.</span></span> <span data-ttu-id="a6483-137">По умолчанию это должен быть ap.\<доменное имя\>.</span><span class="sxs-lookup"><span data-stu-id="a6483-137">By default, this should be ap.\<Domain Name\>.</span></span>
  
```
Set-CsTenantHybridConfiguration -PeerDestination <External Access Edge FQDN> -UseOnPremDialPlan $false
Set-CsTenantFederationConfiguration -SharedSipAddressSpace $True
```

> [!NOTE]
> <span data-ttu-id="a6483-138">Полное доменное имя пограничного внешнего доступа используется для назначения Peer необходимо задать для сайта ТСОП, который будет использоваться только как возврат в случае, если пользователь не будет назначен на сайт PSTN.</span><span class="sxs-lookup"><span data-stu-id="a6483-138">The External Access Edge FQDN used for Peer Destination should be set to a PSTN site that will only be used as a fallback in case a user isn't assigned to a PSTN site.</span></span> <span data-ttu-id="a6483-139">Дополнительные сведения можно [Развернуть один сайт в облаке соединителя](deploy-a-single-site-in-cloud-connector.md) и [развертывания нескольких сайтов в облаке соединителя](deploy-multiple-sites-in-cloud-connector.md).</span><span class="sxs-lookup"><span data-stu-id="a6483-139">For more information, see [Deploy a single site in Cloud Connector](deploy-a-single-site-in-cloud-connector.md) and [Deploy multiple sites in Cloud Connector](deploy-multiple-sites-in-cloud-connector.md).</span></span> 
  
## <a name="set-up-pstn-gateways"></a><span data-ttu-id="a6483-140">Настройка шлюзов ТСОП</span><span class="sxs-lookup"><span data-stu-id="a6483-140">Set up PSTN gateways</span></span>

<span data-ttu-id="a6483-p111">Настройте магистраль для каждого шлюза ТСОП таким образом, чтобы задавались обратные связи с серверами-посредниками для всех устройств. Так как все серверы в пуле используют одинаковое полное доменное имя пула, каждая магистраль должна указывать на одно полное доменное имя или один IP-адрес сервера-посредника, а не на пул серверов-посредников. При настройке магистралей необходимо использовать одинаковые приоритеты.</span><span class="sxs-lookup"><span data-stu-id="a6483-p111">Set up trunks on each PSTN gateway to point back to Mediation Servers for all appliances. Each trunk should point to one Mediation Server FQDN or IP address instead of the Mediation Server pool FQDN because the pool FQDN is the same for all servers in the pool. Trunks should be set in the same priority.</span></span>
  
<span data-ttu-id="a6483-144">Если между серверами-посредниками и шлюзами используется протокол TLS, потребуется настроить для них поддержку MTLS следующим образом.</span><span class="sxs-lookup"><span data-stu-id="a6483-144">If you are using TLS between Mediation Servers and gateways, you will need to configure the gateways and Mediation Servers to support MTLS as follows:</span></span>
  
1. <span data-ttu-id="a6483-145">Экспортируйте корневой ЦС с компьютера Active Directory Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="a6483-145">Export the Root CA from the Cloud Connector Active Directory computer.</span></span>
    
2. <span data-ttu-id="a6483-146">Выполните инструкции поставщика шлюза ТСОП для импорта корневого ЦС.</span><span class="sxs-lookup"><span data-stu-id="a6483-146">Follow the PSTN gateway vendor instructions for importing the Root CA.</span></span>
    
3. <span data-ttu-id="a6483-p112">Импортируйте сертификат корневого ЦС для сертификата, выданного для вашего шлюза на сервере-посреднике. Если вам требуется получить SSL-сертификат для шлюза, это можно сделать с помощью службы ЦС, выполняющейся на компьютере Active Directory Cloud Connector, следующим образом.</span><span class="sxs-lookup"><span data-stu-id="a6483-p112">Import the Root CA certificate for the certificate issued to your gateway on the Mediation Servers. If you need to obtain an SSL certificate for the gateway, you may do this using the Certificate Authority service running on the Cloud Connector Active Directory computer as follows:</span></span>
    
  - <span data-ttu-id="a6483-149">Измените существующий шаблон веб-сервера, чтобы разрешить регистрацию пользователям, прошедшим проверку подлинности, или создайте новый шаблон, чтобы настроить другие свойства и разрешить регистрацию для таких пользователей.</span><span class="sxs-lookup"><span data-stu-id="a6483-149">Modify the existing Web Server template to enable Authenticated users to Enroll, or create a new Web Server template to configure other properties and enable Authenticated users to enroll.</span></span> <span data-ttu-id="a6483-150">[Подробные инструкции см.](https://technet.microsoft.com/library/cc730705.aspx)</span><span class="sxs-lookup"><span data-stu-id="a6483-150">For detailed instructions, see [Certificate Templates](https://technet.microsoft.com/library/cc730705.aspx).</span></span>
    
  - <span data-ttu-id="a6483-151">Запросите сертификат с помощью оснастки «Сертификаты», выбрав включенный шаблон веб-сервера.</span><span class="sxs-lookup"><span data-stu-id="a6483-151">Request a certificate using Certificate snap-in selecting the Web Server template that you have enabled.</span></span> <span data-ttu-id="a6483-152">В поле «Субъект» укажите общее имя, а в поле «Дополнительное имя» — DNS-имя с полным доменным именем шлюза и убедитесь, что в разделе параметров закрытого ключа установлен флажок «Сделать закрытый ключ экспортируемым».</span><span class="sxs-lookup"><span data-stu-id="a6483-152">Be sure to add Common name in Subject and DNS name in Alternative name with FQDN of the gateway, and confirm on the Private Key that Make private key exportable is selected under key options.</span></span> 
    
4. <span data-ttu-id="a6483-153">Экспортируйте SSL-сертификат с закрытым ключом и выполните инструкции поставщика шлюза ТСОП по импорту сертификатов.</span><span class="sxs-lookup"><span data-stu-id="a6483-153">Export the SSL certificate with Private key and follow the instructions from your PSTN gateway vendor for importing the certificate.</span></span>
    
5. <span data-ttu-id="a6483-154">Шлюзы ТСОП на одном сайте ТСОП должны подключаться только к серверам-посредникам на том же сайте.</span><span class="sxs-lookup"><span data-stu-id="a6483-154">PSTN gateway(s) in one PSTN site should only connect to the Mediation Server(s) in the same site.</span></span>
    
## <a name="set-up-your-users-in-office-365"></a><span data-ttu-id="a6483-155">Настройка пользователей Office 365</span><span class="sxs-lookup"><span data-stu-id="a6483-155">Set up your users in Office 365</span></span>

<span data-ttu-id="a6483-156">Войдите на портал администрирования Office 365, добавьте пользователей, для которых будут включены службы голосовой связи через Интернет, после чего назначьте этим пользователям лицензию E5 или лицензию E3 на подключаемый модуль телефонной системы Office 365.</span><span class="sxs-lookup"><span data-stu-id="a6483-156">Log in to the Office 365 admin portal, add the users that will be enabled for online voice services, and assign an E5 license or Phone System in Office 365 add-on to the E3 license to these users.</span></span> <span data-ttu-id="a6483-157">Сведения о добавлении пользователей можно [Добавить пользователей в Office 365 для бизнеса](https://support.office.com/en-US/article/Add-users-to-Office-365-for-business-435ccec3-09dd-4587-9ebd-2f3cad6bc2bc).</span><span class="sxs-lookup"><span data-stu-id="a6483-157">For information about adding users, see [Add users to Office 365 for business](https://support.office.com/en-US/article/Add-users-to-Office-365-for-business-435ccec3-09dd-4587-9ebd-2f3cad6bc2bc).</span></span>
  
## <a name="enable-users-for-phone-system-in-office-365-voice-and-voicemail-services"></a><span data-ttu-id="a6483-158">Включение голосовых служб и голосовой почты телефонной системы в Office 365 для пользователей</span><span class="sxs-lookup"><span data-stu-id="a6483-158">Enable users for Phone System in Office 365 voice and voicemail services</span></span>

<span data-ttu-id="a6483-159">Добавив пользователей в Office 365, включите для их учетных записей голосовые службы телефонной системы в Office 365, включая голосовую почту.</span><span class="sxs-lookup"><span data-stu-id="a6483-159">After adding your users to Office 365, enable their accounts for Phone System in Office 365 voice services, including voicemail.</span></span> <span data-ttu-id="a6483-160">Для этого необходимо войти в клиент Office 365, используя учетную запись с ролью глобального администратора Office 365, которой разрешено выполнение удаленных команд PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a6483-160">To enable these capabilities, you must log in to your Office 365 tenant with an account that is an Office 365 Global Administrator role, and be able to run remote PowerShell.</span></span> <span data-ttu-id="a6483-161">Чтобы узнать, как установить удаленный сеанс PowerShell, обратитесь к разделу: [Настройка компьютера для Windows PowerShell](https://technet.microsoft.com/en-us/library/dn362831%28v=ocs.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="a6483-161">To learn how to establish a remote PowerShell session, see: [Set up your computer for Windows PowerShell](https://technet.microsoft.com/en-us/library/dn362831%28v=ocs.15%29.aspx)</span></span>
  
- <span data-ttu-id="a6483-162">Назначьте политику для пользователя и задайте пользователя business голосовой связи телефонного номера, которые можно указать в значение параметра **Identity** .</span><span class="sxs-lookup"><span data-stu-id="a6483-162">Assign the policy to your user and configure the user's business voice phone number, which you specify with the value of the **Identity** parameter:</span></span>
    
  ```
  Set-CsUser -Identity "<User name>" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true -OnPremLineURI <tel:+phonenumber>
  ```

    > [!NOTE]
    > <span data-ttu-id="a6483-163">Удостоверение (Identity) пользователя можно также задать по его адресу SIP, имени участника-пользователя (UPN), имени домена и имени пользователя (домен\имя_пользователя) и по отображаемому имени Active Directory (Bob Kelly). </span><span class="sxs-lookup"><span data-stu-id="a6483-163">You can also specify a user's Identity by their SIP address, User Principal name (UPN), domain name and username (domain\username), and display name in Active Directory ("Bob Kelly").</span></span> 
  
<span data-ttu-id="a6483-164">Чтобы убедиться, что пользователи добавлены и включены, можно выполнить следующий сценарий:</span><span class="sxs-lookup"><span data-stu-id="a6483-164">You can then verify that the users were added and enabled using the following script:</span></span>
  
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

<span data-ttu-id="a6483-p117">Вам потребуется решить, могут ли пользователи выполнять международные звонки. По умолчанию эта возможность включена. Для включения и отключения международных звонков используется центр администрирования Skype для бизнеса в Интернете.</span><span class="sxs-lookup"><span data-stu-id="a6483-p117">You'll need to decide whether your users should be able to make international calls. By default, international calling is enabled. You can disable or enable users for international dialing using the online Skype for Business admin center.</span></span>
  
<span data-ttu-id="a6483-168">Чтобы отключить международные звонки для отдельных пользователей, выполните следующий командлет в консоли PowerShell Skype для бизнеса Online:</span><span class="sxs-lookup"><span data-stu-id="a6483-168">To disable international calling on a per user basis, run the following cmdlet in Skype for Business Online PowerShell:</span></span>
  
```
Grant-CsVoiceRoutingPolicy -PolicyName InternationalCallsDisallowed -Identity $user
```

<span data-ttu-id="a6483-169">Чтобы повторно включить международных вызов на уровне пользователя после он отключен, выполните командлет же, но измените значение параметра **PolicyName** *InternationalCallsAllowed* .</span><span class="sxs-lookup"><span data-stu-id="a6483-169">To re-enable international calling on a per user basis after it has been disabled, run the same cmdlet, but change the value for **PolicyName** to *InternationalCallsAllowed*  .</span></span>
  
## <a name="assign-users-to-pstn-sites"></a><span data-ttu-id="a6483-170">Назначение пользователей сайтам ТСОП</span><span class="sxs-lookup"><span data-stu-id="a6483-170">Assign users to PSTN sites</span></span>

<span data-ttu-id="a6483-171">Используйте удаленную консоль PowerShell клиента, чтобы назначить сайт пользователям, даже если развернут только один сайт.</span><span class="sxs-lookup"><span data-stu-id="a6483-171">Use tenant remote PowerShell to assign a site to users even if you only deployed a single site.</span></span> <span data-ttu-id="a6483-172">Чтобы узнать, как установить удаленный сеанс PowerShell, обратитесь к разделу: [Настройка компьютера для Windows PowerShell](https://technet.microsoft.com/en-us/library/dn362831%28v=ocs.15%29.aspx).</span><span class="sxs-lookup"><span data-stu-id="a6483-172">To learn how to establish a remote PowerShell session, see: [Set up your computer for Windows PowerShell](https://technet.microsoft.com/en-us/library/dn362831%28v=ocs.15%29.aspx).</span></span>
  
```
# Set the site to users
Set-CsUserPstnSettings -Identity <User Name> -HybridPstnSite <PSTN Site Name>

# Review the site setting for a user
Get-CsUserPstnSettings -Identity <User Name> 

# See all the user settings in one tenant
Get-CsOnlineUser | Get-CsUserPstnSettings
```

> [!NOTE]
> <span data-ttu-id="a6483-173">Если пользователю не назначен сайт ТСОП, при гибридном подключении между развертыванием Skype для бизнеса Cloud Connector Edition и клиентом Office 365 будет выполнен откат до использования сайта по умолчанию уровня клиента (одноранговое назначение), чтобы пользователи могли выполнять звонки.</span><span class="sxs-lookup"><span data-stu-id="a6483-173">If no PSTN site is assigned to a user, hybrid connectivity between your Skype for Business Cloud Connector Edition deployment and your Office 365 tenant will fall back to use the tenant level default one (Peer Destination) so that calls can be completed.</span></span> 
  
## <a name="configure-online-hybrid-mediation-server-settings"></a><span data-ttu-id="a6483-174">Настройка параметров гибридного сервера-посредника в Интернете</span><span class="sxs-lookup"><span data-stu-id="a6483-174">Configure online hybrid Mediation Server Settings</span></span>
<span data-ttu-id="a6483-175"><a name="BKMK_ConfigureMediationServer"> </a></span><span class="sxs-lookup"><span data-stu-id="a6483-175"></span></span>

<span data-ttu-id="a6483-176">При звонка P2P перерастает в сеанс конференции PSTN, Скайп для бизнеса в Интернет сервера конференц-связи отправляет приглашение сервера-посредника соединителя облака.</span><span class="sxs-lookup"><span data-stu-id="a6483-176">When a P2P call is escalated to a PSTN conference, the Skype for Business Online conferencing server will send an invite to the Cloud Connector Mediation Server.</span></span> <span data-ttu-id="a6483-177">Убедитесь, что Office 365 могут перенаправлять этой пригласить успешно, необходимо настроить параметр интерактивного клиента для каждого сервера-посредника соединителя облачных следующим образом:</span><span class="sxs-lookup"><span data-stu-id="a6483-177">To ensure that Office 365 can route this invite successfully, you need to configure a setting in your online tenant for each Cloud Connector Mediation Server as follows:</span></span> 
  
1. <span data-ttu-id="a6483-178">Создайте пользователя на портале администрирования Office 365.</span><span class="sxs-lookup"><span data-stu-id="a6483-178">Create a user in the Office 365 admin portal.</span></span> <span data-ttu-id="a6483-179">Используйте любое имя пользователя, который будет, например «MediationServer1».</span><span class="sxs-lookup"><span data-stu-id="a6483-179">Use any user name you want, such as "MediationServer1."</span></span>
    
    <span data-ttu-id="a6483-180">Используйте домен SIP по умолчанию соединителя облака (первого домена SIP в INI-файл) в качестве пользователя домена.</span><span class="sxs-lookup"><span data-stu-id="a6483-180">Use the default SIP domain of Cloud Connector (the first SIP domain in the .ini file) as the user domain.</span></span>
    
    <span data-ttu-id="a6483-181">Обратите внимание, что назначение лицензий только необходимые для распространения пользователя в Скайп для бизнеса online directory.</span><span class="sxs-lookup"><span data-stu-id="a6483-181">Please note that license assignment is only required for the user propagation into the Skype for Business online directory.</span></span> <span data-ttu-id="a6483-182">Назначение лицензии Office 365 (например, E5) для учетной записи необходимо создать разрешить до одного часа для передачи изменений, затем удалите лицензию с этой учетной записи.</span><span class="sxs-lookup"><span data-stu-id="a6483-182">Assign an Office 365 licenses (such as E5) to the account you create, allow up to one hour for the changes to propagate, then remove the license from this account.</span></span>
    
2. <span data-ttu-id="a6483-183">Клиент удаленного сеанса PowerShell с помощью вашего клиента учетные данные администратора и выполните следующий командлет, чтобы задать сервер-посредник и полное доменное имя пограничного сервера для этого пользователя учетной записи, замена \<DisplayName\> с отображаемым именем пользователя Учетная запись, которую вы создали:</span><span class="sxs-lookup"><span data-stu-id="a6483-183">Start a tenant remote PowerShell session using your tenant admin credentials, and then run the following cmdlet to set the Mediation Server and Edge Server FQDN to that user account, replacing \<DisplayName\> with the Display Name of the user for the account you created:</span></span>
    
  ```
  Set-CsHybridMediationServer -Identity <DisplayName> -Fqdn <MediationServerFQDN> -AccessProxyExternalFqdn <EdgeServerExternalFQDN>
  ```

    <span data-ttu-id="a6483-184">В качестве параметра Identity укажите отображаемое имя учетной записи пользователя Office 365, которая была создана для этого сервера-посредника.</span><span class="sxs-lookup"><span data-stu-id="a6483-184">For Identity, use the Display Name of the Office 365 user account you created for this Mediation Server.</span></span>
    
    <span data-ttu-id="a6483-185">Для *MediationServerFQDN* можно используйте внутреннее полное доменное имя, определенное для сервера-посредника.</span><span class="sxs-lookup"><span data-stu-id="a6483-185">For  *MediationServerFQDN*  , use the internal FQDN defined for your Mediation Server.</span></span>
    
    <span data-ttu-id="a6483-186">Для *EdgeServerExternalFQDN* можно используйте внешнее полное доменное имя, определенное для прокси-сервера доступа пограничного сервера.</span><span class="sxs-lookup"><span data-stu-id="a6483-186">For  *EdgeServerExternalFQDN*  , use the external FQDN defined for Edge Server Access Proxy.</span></span> <span data-ttu-id="a6483-187">При наличии нескольких сайтов ТСОП выберите полное доменное имя пограничного прокси-сервера доступа, назначенное сайту, на котором размещается сервер-посредник.</span><span class="sxs-lookup"><span data-stu-id="a6483-187">If there are multiple Cloud Connector PSTN sites, choose the Edge Server Access Proxy FQDN assigned to the site where the Mediation Server is located.</span></span>
    
3. <span data-ttu-id="a6483-188">	При наличии нескольких серверов-посредников Cloud Connector (несколько сайтов, высокая доступность) повторите предыдущие шаги для каждого из них.</span><span class="sxs-lookup"><span data-stu-id="a6483-188">If there are multiple Cloud Connector Mediation Servers (multiple-site, HA), please repeat the previous steps for each of them.</span></span>
    

