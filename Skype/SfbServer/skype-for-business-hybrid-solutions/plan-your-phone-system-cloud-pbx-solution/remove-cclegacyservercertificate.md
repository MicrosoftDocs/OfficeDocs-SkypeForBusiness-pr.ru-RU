---
title: Remove-CcLegacyServerCertificate
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 6/22/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: ff21cecb-5035-48fd-9705-11ea81ce7df6
description: Командлет Remove-CcLegacyServerCertificate удаляет прежние версии сертификатов сервера центрального хранилища управления, сервера-посредника и пограничного сервера после выполнения командлетов Renew-CcCACertificate или Renew CcServerCertificate.
ms.openlocfilehash: f23a753df1a5c9f81b81bc0f1d7d33c01020b489
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/28/2018
---
# <a name="remove-cclegacyservercertificate"></a><span data-ttu-id="d8af4-103">Remove-CcLegacyServerCertificate</span><span class="sxs-lookup"><span data-stu-id="d8af4-103">Remove-CcLegacyServerCertificate</span></span>
 
<span data-ttu-id="d8af4-104">Командлет Remove-CcLegacyServerCertificate удаляет прежние версии сертификатов сервера центрального хранилища управления, сервера-посредника и пограничного сервера после выполнения командлетов Renew-CcCACertificate или Renew CcServerCertificate.</span><span class="sxs-lookup"><span data-stu-id="d8af4-104">The Remove-CcLegacyServerCertificate cmdlet removes legacy server certificates on the Central Management Store, Mediation Server, and Edge Server after you execute the Renew-CcCACertificate or Renew CcServerCertificate cmdlets.</span></span>
  
```
Remove-CcLegacyServerCertificate [[-Roles] <array> {Cms | MS | Edge}] 
```

## <a name="examples"></a><span data-ttu-id="d8af4-105">Примеры</span><span class="sxs-lookup"><span data-stu-id="d8af4-105">Examples</span></span>
<span data-ttu-id="d8af4-106"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="d8af4-106"></span></span>

### <a name="example-1"></a><span data-ttu-id="d8af4-107">Пример 1</span><span class="sxs-lookup"><span data-stu-id="d8af4-107">Example 1</span></span>

<span data-ttu-id="d8af4-108">В следующем примере удаляются прежние версии сертификатов сервера центрального хранилища управления, сервера-посредника и пограничного сервера после продления сертификатов.</span><span class="sxs-lookup"><span data-stu-id="d8af4-108">The following example removes legacy certificates issued for the Central Management Store, Mediation Server, and Edge Server after you have renewed the certificates:</span></span>
  
```
Remove-CcLegacyServerCertificate
```

### <a name="example-2"></a><span data-ttu-id="d8af4-109">Пример 2</span><span class="sxs-lookup"><span data-stu-id="d8af4-109">Example 2</span></span>

<span data-ttu-id="d8af4-110">В следующем примере удаляются прежние версии сертификатов сервера-посредника и пограничного сервера после продления сертификатов. </span><span class="sxs-lookup"><span data-stu-id="d8af4-110">The next example removes certificates issued for Mediation Server and Edge Server after you have renewed the certificates:</span></span> 
  
```
Remove-CcLegacyServerCertificate -Roles @("MS", "Edge") 

```

## <a name="parameters"></a><span data-ttu-id="d8af4-111">Параметры</span><span class="sxs-lookup"><span data-stu-id="d8af4-111">Parameters</span></span>
<span data-ttu-id="d8af4-112"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="d8af4-112"></span></span>

|<span data-ttu-id="d8af4-113">**Параметр**</span><span class="sxs-lookup"><span data-stu-id="d8af4-113">**Parameter**</span></span>|<span data-ttu-id="d8af4-114">**Обязательно**</span><span class="sxs-lookup"><span data-stu-id="d8af4-114">**Required**</span></span>|<span data-ttu-id="d8af4-115">**Тип**</span><span class="sxs-lookup"><span data-stu-id="d8af4-115">**Type**</span></span>|<span data-ttu-id="d8af4-116">**Описание**</span><span class="sxs-lookup"><span data-stu-id="d8af4-116">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="d8af4-117">Роли </span><span class="sxs-lookup"><span data-stu-id="d8af4-117">Roles</span></span> <br/> |<span data-ttu-id="d8af4-118">Необязательно</span><span class="sxs-lookup"><span data-stu-id="d8af4-118">Optional</span></span>  <br/> |<span data-ttu-id="d8af4-119">System.Array</span><span class="sxs-lookup"><span data-stu-id="d8af4-119">System.Array</span></span>  <br/> | <span data-ttu-id="d8af4-120">Массив ролей сервера Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="d8af4-120">Array of Cloud Connector server roles.</span></span> <br/> |
   
## <a name="input-types"></a><span data-ttu-id="d8af4-121">Типы входных данных</span><span class="sxs-lookup"><span data-stu-id="d8af4-121">Input Types</span></span>
<span data-ttu-id="d8af4-122"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="d8af4-122"></span></span>

<span data-ttu-id="d8af4-p101">Нет. Командлет Remove-CcLegacyServerCertificate не принимает входные данные по конвейеру.</span><span class="sxs-lookup"><span data-stu-id="d8af4-p101">None. The Remove-CcLegacyServerCertificate cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="d8af4-125">Типы возвращаемых данных</span><span class="sxs-lookup"><span data-stu-id="d8af4-125">Return Types</span></span>
<span data-ttu-id="d8af4-126"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="d8af4-126"></span></span>

<span data-ttu-id="d8af4-127">Нет</span><span class="sxs-lookup"><span data-stu-id="d8af4-127">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="d8af4-128">См. также</span><span class="sxs-lookup"><span data-stu-id="d8af4-128">See also</span></span>
<span data-ttu-id="d8af4-129"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="d8af4-129"></span></span>

[<span data-ttu-id="d8af4-130">Обновить CcServerCertificate</span><span class="sxs-lookup"><span data-stu-id="d8af4-130">Renew-CcServerCertificate</span></span>](renew-ccservercertificate.md)
  
[<span data-ttu-id="d8af4-131">Сброс CcCACertificate</span><span class="sxs-lookup"><span data-stu-id="d8af4-131">Reset-CcCACertificate</span></span>](reset-cccacertificate.md)
  
[<span data-ttu-id="d8af4-132">Обновить CcCACertificate</span><span class="sxs-lookup"><span data-stu-id="d8af4-132">Renew-CcCACertificate</span></span>](renew-cccacertificate.md)
  
[<span data-ttu-id="d8af4-133">Обновление CcCACertificate</span><span class="sxs-lookup"><span data-stu-id="d8af4-133">Update-CcCACertificate</span></span>](update-cccacertificate.md)
  

