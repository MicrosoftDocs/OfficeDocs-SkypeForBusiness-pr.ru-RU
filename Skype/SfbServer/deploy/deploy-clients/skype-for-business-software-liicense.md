---
title: Скайп системы Скайп комнаты для бизнеса лицензии на программное обеспечение
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.reviewer: davgroom
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 78a664ba-fefc-4423-ac8f-b58e6fbc2e55
description: В этом разделе описывается проверка наличия корпоративной лицензии на программное обеспечение Skype для бизнеса.
ms.openlocfilehash: e4ba03dacdce0056cb130299f551921042a6790d
ms.sourcegitcommit: d3c3467320a2928d3bad14a1a44a31ee5a9a988c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/23/2018
ms.locfileid: "25699261"
---
# <a name="skype-room-system-skype-for-business-software-license"></a><span data-ttu-id="a2cc1-103">Система комнат Skype: лицензия на использование программного обеспечения Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="a2cc1-103">Skype Room System: Skype for Business software license</span></span>
 
<span data-ttu-id="a2cc1-104">В этом разделе описывается проверка наличия корпоративной лицензии на программное обеспечение Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="a2cc1-104">Read this topic to learn how to check whether you have a Skype for Business software volume license.</span></span> 
  
<span data-ttu-id="a2cc1-105">Система комнаты Скайп использует установленные Скайп для бизнеса клиент, который требуется лицензия корпоративного программного обеспечения.</span><span class="sxs-lookup"><span data-stu-id="a2cc1-105">Skype Room System uses an installed Skype for Business client, which requires a software volume license.</span></span> <span data-ttu-id="a2cc1-106">Перед развертыванием первого системы комнаты Скайп Узнайте состояние лицензии корпоративного развертывания — с помощью серверов управления ключами (KMS) или ключи многократной активации (MAK).</span><span class="sxs-lookup"><span data-stu-id="a2cc1-106">Before deploying the first Skype Room System, find out the volume license state of the deployment - using Key Management Servers (KMS) or Multiple Activation Keys (MAK).</span></span>
  
## <a name="key-management-servers-kms"></a><span data-ttu-id="a2cc1-107">Серверы управления ключами (KMS)</span><span class="sxs-lookup"><span data-stu-id="a2cc1-107">Key Management Servers (KMS)</span></span>

<span data-ttu-id="a2cc1-108">Если будет распространять Скайп для бизнеса многократной активации KMS на месте, система комнаты Скайп автоматически включает Скайп для клиента Business.</span><span class="sxs-lookup"><span data-stu-id="a2cc1-108">If KMS are in place and will distribute Skype for Business Volume License activations, the Skype Room System will automatically activate the Skype for Business client.</span></span> <span data-ttu-id="a2cc1-109">Чтобы узнать, настроены ли серверы управления ключами, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="a2cc1-109">To find out if KMS are in place:</span></span>
  
<span data-ttu-id="a2cc1-110">В командной строке выполните следующую команду:`nslookup -type=srv _vlmcs._tcp >%temp%\kms.txt`</span><span class="sxs-lookup"><span data-stu-id="a2cc1-110">From a command prompt, run:  `nslookup -type=srv _vlmcs._tcp >%temp%\kms.txt`</span></span>
  
<span data-ttu-id="a2cc1-111">Для получения дополнительных сведений см [Обнаружение узлов Windows KMS и Office с помощью DNS и удаление несанкционированного экземпляров](https://blogs.technet.com/b/odsupport/archive/2011/11/14/how-to-discover-kms-hosts-via-a-dns-query-and-remove-them-if-need-be.aspx).</span><span class="sxs-lookup"><span data-stu-id="a2cc1-111">For more information, see [How to discover Office and Windows KMS hosts via DNS and remove unauthorized instances](https://blogs.technet.com/b/odsupport/archive/2011/11/14/how-to-discover-kms-hosts-via-a-dns-query-and-remove-them-if-need-be.aspx).</span></span> 
  
<span data-ttu-id="a2cc1-112">Сведения о настройке KMS см. в разделах [Активация Office 2013 с помощью KMS](https://technet.microsoft.com/library/ee624357.aspx) и [Ключи GVLK для KMS и активации Active Directory в Office 2013](https://technet.microsoft.com/library/dn385360.aspx)</span><span class="sxs-lookup"><span data-stu-id="a2cc1-112">To set up a KMS, see [KMS activation of Office 2013](https://technet.microsoft.com/library/ee624357.aspx) and [GVLKs for KMS and Active Directory activation of Office 2013](https://technet.microsoft.com/library/dn385360.aspx)</span></span>
  
<span data-ttu-id="a2cc1-113">Office 2013 универсальный ключ многократной установки для Lync: 2MG3G-3BNTT-3MFW9-KDQW3-TCK7R (этот ключ система Скайп комнаты следует искать KMS в сети.)</span><span class="sxs-lookup"><span data-stu-id="a2cc1-113">Office 2013 Generic Volume License Key for Lync: 2MG3G-3BNTT-3MFW9-KDQW3-TCK7R (This key causes the Skype Room System to look for a KMS on the network.)</span></span>
  
## <a name="multiple-activation-keys-mak-from-the-volume-license-service-center-vlsc"></a><span data-ttu-id="a2cc1-114">Ключи многократной активации (MAK) из Volume Licensing Service Center (VLSC)</span><span class="sxs-lookup"><span data-stu-id="a2cc1-114">Multiple Activation Keys (MAK) from the Volume License Service Center (VLSC)</span></span>

<span data-ttu-id="a2cc1-115">If the customer uses any other volume license software, the IT department will manage the software activations and Volume License Agreement (VLA) using the VLSC.</span><span class="sxs-lookup"><span data-stu-id="a2cc1-115">If the customer uses any other volume license software, the IT department will manage the software activations and Volume License Agreement (VLA) using the VLSC.</span></span> <span data-ttu-id="a2cc1-116">Это также включает компании на покупку Скайп для активации корпоративного лицензирования бизнеса, после которого компании могут получить MAK для ввода данных в консоль администратора системы Скайп помещений.</span><span class="sxs-lookup"><span data-stu-id="a2cc1-116">This will also enable the company to purchase Skype for Business VL activations, after which the company can obtain a MAK for input in the Skype Room System Admin Console.</span></span>
  
<span data-ttu-id="a2cc1-117">Клиент с VLA должен знать свои учетные данные VLSC, которые будут использоваться для администрирования соглашения и получения MAK.</span><span class="sxs-lookup"><span data-stu-id="a2cc1-117">A customer with a VLA must know their VLSC credentials, which will be used to administer the agreement and obtain MAK.</span></span> <span data-ttu-id="a2cc1-118">Если определен, должна появиться возможность подтверждение, если клиент оплату за VLA клиента финансового отдела.</span><span class="sxs-lookup"><span data-stu-id="a2cc1-118">If uncertain, the customer's finance department should be able to confirm if the customer has paid for a VLA.</span></span>
  
<span data-ttu-id="a2cc1-119">Для получения MAK необходимо перейти в Volume Licensing Service Center для просмотра соглашения и загрузки ключей продукта (MAK).</span><span class="sxs-lookup"><span data-stu-id="a2cc1-119">To obtain a MAK, access the Volume Licensing Service Center to view agreements and download product keys (MAK).</span></span> <span data-ttu-id="a2cc1-120">Дополнительные сведения см. в [Volume Licensing Service Center](https://www.microsoft.com/Licensing/servicecenter/default.aspx).</span><span class="sxs-lookup"><span data-stu-id="a2cc1-120">For more information, go to the [Volume Licensing Service Center](https://www.microsoft.com/Licensing/servicecenter/default.aspx).</span></span> 
  
## <a name="mak-for-office-365-without-vlsc-access"></a><span data-ttu-id="a2cc1-121">MAK для Office 365 без получения доступа к VLSC</span><span class="sxs-lookup"><span data-stu-id="a2cc1-121">MAK for Office 365 without VLSC access</span></span>

<span data-ttu-id="a2cc1-122">Если клиент не имеет корпоративного лицензирования, будет гораздо сложнее управлять Скайп для активации бизнеса.</span><span class="sxs-lookup"><span data-stu-id="a2cc1-122">If the customer doesn't have a Volume License Agreement, Skype for Business activations will be much more difficult to manage.</span></span> <span data-ttu-id="a2cc1-123">Тем не менее пользователи Office 365 без доступа к VLSC могут получить рекламное MAK с указанием следующих сведений ПВТ система комнаты Скайп продажи:</span><span class="sxs-lookup"><span data-stu-id="a2cc1-123">However, Office 365 customers without VLSC access can obtain a promotional MAK by providing the following information to the OEM selling the Skype Room System:</span></span>
  
- <span data-ttu-id="a2cc1-124">Название компании</span><span class="sxs-lookup"><span data-stu-id="a2cc1-124">Company name</span></span>
    
- <span data-ttu-id="a2cc1-125">Имя, адрес электронной почты и номер телефона контактного лица по вопросам развертывания</span><span class="sxs-lookup"><span data-stu-id="a2cc1-125">Deployment contact name, email, and phone number</span></span>
    
- <span data-ttu-id="a2cc1-126">Число систем</span><span class="sxs-lookup"><span data-stu-id="a2cc1-126">Number of systems deployed</span></span>
    
- <span data-ttu-id="a2cc1-127">Дата развертывания</span><span class="sxs-lookup"><span data-stu-id="a2cc1-127">Deployment date</span></span>
    
- <span data-ttu-id="a2cc1-128">Если клиент имеет Microsoft технического специалиста, СПЕЦИАЛИСТ по имени и контактной информации</span><span class="sxs-lookup"><span data-stu-id="a2cc1-128">If the customer has a Microsoft Technical Account Manager, the TAM's name and contact information</span></span>
    

