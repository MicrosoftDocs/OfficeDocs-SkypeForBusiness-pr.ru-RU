---
title: Update-CcServerCertificate
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 7/11/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: cd2889c4-0eb1-4752-9274-93a5a68a8080
description: 'Командлет Update-CcServerCertificate продлевает сертификаты Skype для бизнеса Cloud Connector Edition, срок действия которых истекает или уже истек. '
ms.openlocfilehash: 920770b4ce77e893a7195d1326ea13ac73e0cc70
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/09/2020
ms.locfileid: "41003119"
---
# <a name="update-ccservercertificate"></a><span data-ttu-id="5046a-103">Update-CcServerCertificate</span><span class="sxs-lookup"><span data-stu-id="5046a-103">Update-CcServerCertificate</span></span>
 
<span data-ttu-id="5046a-104">Командлет Update-CcServerCertificate продлевает сертификаты Skype для бизнеса Cloud Connector Edition, срок действия которых истекает или уже истек. </span><span class="sxs-lookup"><span data-stu-id="5046a-104">The Update-CcServerCertificate cmdlet renews the certificates for Skype for Business Cloud Connector Edition when they are near expiration or already expired.</span></span> 
  
```powershell
Update-CcServerCertificate [[-Roles] <array> {Cms | MS | Edge}]
```

## <a name="examples"></a><span data-ttu-id="5046a-105">Примеры</span><span class="sxs-lookup"><span data-stu-id="5046a-105">Examples</span></span>
<span data-ttu-id="5046a-106"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="5046a-106"></span></span>

### <a name="example-1"></a><span data-ttu-id="5046a-107">Пример 1</span><span class="sxs-lookup"><span data-stu-id="5046a-107">Example 1</span></span>

<span data-ttu-id="5046a-108">В следующем примере продлеваются сертификаты сервера центрального хранилища управления (CMS), сервера-посредника или пограничного сервера, срок действия которых истекает или уже истек.</span><span class="sxs-lookup"><span data-stu-id="5046a-108">The following example renews the certificates for the Central Management Store, Mediation Server, and Edge Server when the certificates are near expiration or already expired:</span></span>
  
```powershell
Update-CcServerCertificate
```

### <a name="example-2"></a><span data-ttu-id="5046a-109">Пример 2</span><span class="sxs-lookup"><span data-stu-id="5046a-109">Example 2</span></span>

<span data-ttu-id="5046a-110">В следующем примере продлеваются сертификаты сервера-посредника или пограничного сервера, срок действия которых истекает или уже истек.</span><span class="sxs-lookup"><span data-stu-id="5046a-110">The next example renews the certificates for Mediation Server and Edge Server when they are near expiration or already expired:</span></span>
  
```powershell
Update-CcServerCertificate-Roles @("MS", "Edge")
```

## <a name="detailed-description"></a><span data-ttu-id="5046a-111">Подробное описание</span><span class="sxs-lookup"><span data-stu-id="5046a-111">Detailed Description</span></span>
<span data-ttu-id="5046a-112"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="5046a-112"></span></span>

<span data-ttu-id="5046a-113">Внутренние сертификаты облачного соединителя, выданные для хранилища центрального управления, сервера-посредника и пограничного сервера, действительны в течение двух лет после того, как они были выпущены в службе сертификации.</span><span class="sxs-lookup"><span data-stu-id="5046a-113">Cloud Connector internal certificates issued to the Central Management Store, Mediation Server, and Edge Server are valid for two years after they are issued from a Certificate Authority service.</span></span> <span data-ttu-id="5046a-114">Если срок действия сертификатов истекает или уже истек, выполните командлет Update-CcServerCertificate для их продления.</span><span class="sxs-lookup"><span data-stu-id="5046a-114">If certificates are near expiration or already expired, run the Update-CcServerCertificate cmdlet to renew the certificates.</span></span> 
  
<span data-ttu-id="5046a-115">Эта команда заменяет командлет Renew-CcServerCertificate в Cloud Connector 2.0 и более поздних выпусков.</span><span class="sxs-lookup"><span data-stu-id="5046a-115">This command replaces the Renew-CcServerCertificate cmdlet in Cloud Connector 2.0 and later releases.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="5046a-116">Параметры</span><span class="sxs-lookup"><span data-stu-id="5046a-116">Parameters</span></span>
<span data-ttu-id="5046a-117"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="5046a-117"></span></span>

|<span data-ttu-id="5046a-118">**Параметр**</span><span class="sxs-lookup"><span data-stu-id="5046a-118">**Parameter**</span></span>|<span data-ttu-id="5046a-119">**Обязательный**</span><span class="sxs-lookup"><span data-stu-id="5046a-119">**Required**</span></span>|<span data-ttu-id="5046a-120">**Тип**</span><span class="sxs-lookup"><span data-stu-id="5046a-120">**Type**</span></span>|<span data-ttu-id="5046a-121">**Описание**</span><span class="sxs-lookup"><span data-stu-id="5046a-121">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="5046a-122">Роли</span><span class="sxs-lookup"><span data-stu-id="5046a-122">Roles</span></span>  <br/> |<span data-ttu-id="5046a-123">Необязательно </span><span class="sxs-lookup"><span data-stu-id="5046a-123">Optional</span></span>  <br/> |<span data-ttu-id="5046a-124">System.Array</span><span class="sxs-lookup"><span data-stu-id="5046a-124">System.Array</span></span>  <br/> | <span data-ttu-id="5046a-125"> Массив ролей сервера Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="5046a-125">Array of Cloud Connector server roles.</span></span> <br/> |
   
## <a name="input-types"></a><span data-ttu-id="5046a-126">Типы входных данных</span><span class="sxs-lookup"><span data-stu-id="5046a-126">Input Types</span></span>
<span data-ttu-id="5046a-127"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="5046a-127"></span></span>

<span data-ttu-id="5046a-p102">Нет. Командлет Update-CcServerCertificate не принимает входные данные по конвейеру.</span><span class="sxs-lookup"><span data-stu-id="5046a-p102">None. The Update-CcServerCertificate cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="5046a-130">Типы возвращаемых данных</span><span class="sxs-lookup"><span data-stu-id="5046a-130">Return Types</span></span>
<span data-ttu-id="5046a-131"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="5046a-131"></span></span>

<span data-ttu-id="5046a-132">Нет</span><span class="sxs-lookup"><span data-stu-id="5046a-132">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="5046a-133">См. также</span><span class="sxs-lookup"><span data-stu-id="5046a-133">See also</span></span>
<span data-ttu-id="5046a-134"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="5046a-134"></span></span>

[<span data-ttu-id="5046a-135">Reset-CcCACertificate</span><span class="sxs-lookup"><span data-stu-id="5046a-135">Reset-CcCACertificate</span></span>](reset-cccacertificate.md)
  
[<span data-ttu-id="5046a-136">Renew-CcServerCertificate</span><span class="sxs-lookup"><span data-stu-id="5046a-136">Renew-CcServerCertificate</span></span>](renew-ccservercertificate.md)
  
[<span data-ttu-id="5046a-137">Export-CcRootCertificate</span><span class="sxs-lookup"><span data-stu-id="5046a-137">Export-CcRootCertificate</span></span>](export-ccrootcertificate.md)
  

