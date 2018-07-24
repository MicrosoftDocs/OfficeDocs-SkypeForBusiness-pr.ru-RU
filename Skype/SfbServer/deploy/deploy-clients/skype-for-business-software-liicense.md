---
title: Скайп системы Скайп комнаты для бизнеса лицензии на программное обеспечение
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 78a664ba-fefc-4423-ac8f-b58e6fbc2e55
description: В этом разделе описывается проверка наличия корпоративной лицензии на программное обеспечение Skype для бизнеса.
ms.openlocfilehash: ba582174483eb511387ae085aba97d02631665fc
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/24/2018
ms.locfileid: "20965424"
---
# <a name="skype-room-system-skype-for-business-software-license"></a><span data-ttu-id="f0341-103">Система комнат Skype: лицензия на использование программного обеспечения Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="f0341-103">Skype Room System: Skype for Business software license</span></span>
 
<span data-ttu-id="f0341-104">В этом разделе описывается проверка наличия корпоративной лицензии на программное обеспечение Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="f0341-104">Read this topic to learn how to check whether you have a Skype for Business software volume license.</span></span> 
  
<span data-ttu-id="f0341-105">Система комнаты Скайп использует установленные Скайп для бизнеса клиент, который требуется лицензия корпоративного программного обеспечения.</span><span class="sxs-lookup"><span data-stu-id="f0341-105">Skype Room System uses an installed Skype for Business client, which requires a software volume license.</span></span> <span data-ttu-id="f0341-106">Перед развертыванием первого системы комнаты Скайп Узнайте состояние лицензии корпоративного развертывания — с помощью серверов управления ключами (KMS) или ключи многократной активации (MAK).</span><span class="sxs-lookup"><span data-stu-id="f0341-106">Before deploying the first Skype Room System, find out the volume license state of the deployment - using Key Management Servers (KMS) or Multiple Activation Keys (MAK).</span></span>
  
## <a name="key-management-servers-kms"></a><span data-ttu-id="f0341-107">Серверы управления ключами (KMS)</span><span class="sxs-lookup"><span data-stu-id="f0341-107">Key Management Servers (KMS)</span></span>

<span data-ttu-id="f0341-108">Если будет распространять Скайп для бизнеса многократной активации KMS на месте, система комнаты Скайп автоматически включает Скайп для клиента Business.</span><span class="sxs-lookup"><span data-stu-id="f0341-108">If KMS are in place and will distribute Skype for Business Volume License activations, the Skype Room System will automatically activate the Skype for Business client.</span></span> <span data-ttu-id="f0341-109">Чтобы узнать, настроены ли серверы управления ключами, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="f0341-109">To find out if KMS are in place:</span></span>
  
<span data-ttu-id="f0341-110">В командной строке выполните следующую команду:`nslookup -type=srv _vlmcs._tcp >%temp%\kms.txt`</span><span class="sxs-lookup"><span data-stu-id="f0341-110">From a command prompt, run:  `nslookup -type=srv _vlmcs._tcp >%temp%\kms.txt`</span></span>
  
<span data-ttu-id="f0341-111">Для получения дополнительных сведений см [Обнаружение узлов Windows KMS и Office с помощью DNS и удаление несанкционированного экземпляров](https://blogs.technet.com/b/odsupport/archive/2011/11/14/how-to-discover-kms-hosts-via-a-dns-query-and-remove-them-if-need-be.aspx).</span><span class="sxs-lookup"><span data-stu-id="f0341-111">For more information, see [How to discover Office and Windows KMS hosts via DNS and remove unauthorized instances](https://blogs.technet.com/b/odsupport/archive/2011/11/14/how-to-discover-kms-hosts-via-a-dns-query-and-remove-them-if-need-be.aspx).</span></span> 
  
<span data-ttu-id="f0341-112">Настройка сервера KMS, в разделе [службы KMS для активации Office 2013](https://technet.microsoft.com/library/ee624357.aspx) и [Gvlk для активации KMS и Active Directory Office 2013](https://technet.microsoft.com/library/dn385360.aspx)</span><span class="sxs-lookup"><span data-stu-id="f0341-112">To set up a KMS, see [KMS activation of Office 2013](https://technet.microsoft.com/library/ee624357.aspx) and [GVLKs for KMS and Active Directory activation of Office 2013](https://technet.microsoft.com/library/dn385360.aspx)</span></span>
  
<span data-ttu-id="f0341-113">Office 2013 универсальный ключ многократной установки для Lync: 2MG3G-3BNTT-3MFW9-KDQW3-TCK7R (этот ключ система Скайп комнаты следует искать KMS в сети.)</span><span class="sxs-lookup"><span data-stu-id="f0341-113">Office 2013 Generic Volume License Key for Lync: 2MG3G-3BNTT-3MFW9-KDQW3-TCK7R (This key causes the Skype Room System to look for a KMS on the network.)</span></span>
  
## <a name="multiple-activation-keys-mak-from-the-volume-license-service-center-vlsc"></a><span data-ttu-id="f0341-114">Ключи многократной активации (MAK) из Volume Licensing Service Center (VLSC)</span><span class="sxs-lookup"><span data-stu-id="f0341-114">Multiple Activation Keys (MAK) from the Volume License Service Center (VLSC)</span></span>

<span data-ttu-id="f0341-115">Если клиент использует любое другое программное обеспечение лицензии том, как ИТ-отдел будет управлять активаций программного обеспечения и корпоративного лицензионного соглашения (VLA) с помощью центра поддержки корпоративных лицензий.</span><span class="sxs-lookup"><span data-stu-id="f0341-115">If the customer uses any other volume license software, the IT department will manage the software activations and Volume License Agreement (VLA) using the VLSC.</span></span> <span data-ttu-id="f0341-116">Это также включает компании на покупку Скайп для активации корпоративного лицензирования бизнеса, после которого компании могут получить MAK для ввода данных в консоль администратора системы Скайп помещений.</span><span class="sxs-lookup"><span data-stu-id="f0341-116">This will also enable the company to purchase Skype for Business VL activations, after which the company can obtain a MAK for input in the Skype Room System Admin Console.</span></span>
  
<span data-ttu-id="f0341-117">Клиент с VLA должен знать свои учетные данные VLSC, которые будут использоваться для администрирования соглашения и получения MAK.</span><span class="sxs-lookup"><span data-stu-id="f0341-117">A customer with a VLA must know their VLSC credentials, which will be used to administer the agreement and obtain MAK.</span></span> <span data-ttu-id="f0341-118">Если определен, должна появиться возможность подтверждение, если клиент оплату за VLA клиента финансового отдела.</span><span class="sxs-lookup"><span data-stu-id="f0341-118">If uncertain, the customer's finance department should be able to confirm if the customer has paid for a VLA.</span></span>
  
<span data-ttu-id="f0341-119">Для получения MAK необходимо перейти в Volume Licensing Service Center для просмотра соглашения и загрузки ключей продукта (MAK).</span><span class="sxs-lookup"><span data-stu-id="f0341-119">To obtain a MAK, access the Volume Licensing Service Center to view agreements and download product keys (MAK).</span></span> <span data-ttu-id="f0341-120">Для получения дополнительных сведений перейдите в [Volume Licensing Service Center](https://www.microsoft.com/Licensing/servicecenter/default.aspx).</span><span class="sxs-lookup"><span data-stu-id="f0341-120">For more information, go to the [Volume Licensing Service Center](https://www.microsoft.com/Licensing/servicecenter/default.aspx).</span></span> 
  
## <a name="mak-for-office-365-without-vlsc-access"></a><span data-ttu-id="f0341-121">MAK для Office 365 без получения доступа к VLSC</span><span class="sxs-lookup"><span data-stu-id="f0341-121">MAK for Office 365 without VLSC access</span></span>

<span data-ttu-id="f0341-122">Если клиент не имеет корпоративного лицензирования, будет гораздо сложнее управлять Скайп для активации бизнеса.</span><span class="sxs-lookup"><span data-stu-id="f0341-122">If the customer doesn't have a Volume License Agreement, Skype for Business activations will be much more difficult to manage.</span></span> <span data-ttu-id="f0341-123">Тем не менее пользователи Office 365 без доступа к VLSC могут получить рекламное MAK с указанием следующих сведений ПВТ система комнаты Скайп продажи:</span><span class="sxs-lookup"><span data-stu-id="f0341-123">However, Office 365 customers without VLSC access can obtain a promotional MAK by providing the following information to the OEM selling the Skype Room System:</span></span>
  
- <span data-ttu-id="f0341-124">Название компании</span><span class="sxs-lookup"><span data-stu-id="f0341-124">Company name</span></span>
    
- <span data-ttu-id="f0341-125">Имя, адрес электронной почты и номер телефона контактного лица по вопросам развертывания</span><span class="sxs-lookup"><span data-stu-id="f0341-125">Deployment contact name, email, and phone number</span></span>
    
- <span data-ttu-id="f0341-126">Число систем</span><span class="sxs-lookup"><span data-stu-id="f0341-126">Number of systems deployed</span></span>
    
- <span data-ttu-id="f0341-127">Дата развертывания</span><span class="sxs-lookup"><span data-stu-id="f0341-127">Deployment date</span></span>
    
- <span data-ttu-id="f0341-128">Если клиент имеет Microsoft технического специалиста, СПЕЦИАЛИСТ по имени и контактной информации</span><span class="sxs-lookup"><span data-stu-id="f0341-128">If the customer has a Microsoft Technical Account Manager, the TAM's name and contact information</span></span>
    

