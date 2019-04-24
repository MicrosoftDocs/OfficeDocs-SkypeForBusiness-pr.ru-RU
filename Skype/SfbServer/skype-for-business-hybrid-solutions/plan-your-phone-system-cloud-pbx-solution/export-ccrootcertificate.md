---
title: Export-CcRootCertificate
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 9/20/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 1499e33c-6a7c-46b9-b9a1-f78d7853b45d
description: 'Командлет Export-CcRootCertificate экспортирует корневой сертификат ЦС в локальный файл на сервере узла Skype для бизнеса Cloud Connector Edition. '
ms.openlocfilehash: c2647baa9ab6762feb8f550e0d726b18ab5d3090
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "32233983"
---
# <a name="export-ccrootcertificate"></a><span data-ttu-id="d8ea4-103">Export-CcRootCertificate</span><span class="sxs-lookup"><span data-stu-id="d8ea4-103">Export-CcRootCertificate</span></span>
 
<span data-ttu-id="d8ea4-104">Командлет Export-CcRootCertificate экспортирует корневой сертификат ЦС в локальный файл на сервере узла Skype для бизнеса Cloud Connector Edition. </span><span class="sxs-lookup"><span data-stu-id="d8ea4-104">The Export-CcRootCertificate cmdlet exports the root CA certificate to a local file on the Skype for Business Cloud Connector Edition host server.</span></span> 
  
```
Export-CcRootCertificate [[-Path] <string>]
```

## <a name="examples"></a><span data-ttu-id="d8ea4-105">Примеры</span><span class="sxs-lookup"><span data-stu-id="d8ea4-105">Examples</span></span>
<span data-ttu-id="d8ea4-106"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="d8ea4-106"></span></span>

### <a name="example-1"></a><span data-ttu-id="d8ea4-107">Пример 1</span><span class="sxs-lookup"><span data-stu-id="d8ea4-107">Example 1</span></span>

<span data-ttu-id="d8ea4-p101">В следующем примере параметр Path задается как путь к каталогу, а не к файлу. В нем создается файл c:\test\CCERootCertificates.p7b.</span><span class="sxs-lookup"><span data-stu-id="d8ea4-p101">The following example sets the Path parameter as a directory path—not a file path. It generates the file c:\test\CCERootCertificates.p7b.</span></span>
  
```
Export-CcRootCertificate -Path "C:\test" 
```

## <a name="detailed-description"></a><span data-ttu-id="d8ea4-110">Подробное описание</span><span class="sxs-lookup"><span data-stu-id="d8ea4-110">Detailed Description</span></span>
<span data-ttu-id="d8ea4-111"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="d8ea4-111"></span></span>

<span data-ttu-id="d8ea4-p102">Командлет Export-CcRootCertificate позволяет вам сохранять корневые и промежуточные сертификаты, указав путь к файлу. Это может помочь при аварийном восстановлении. </span><span class="sxs-lookup"><span data-stu-id="d8ea4-p102">The Export-CcRootCertificate cmdlet allows you to save the root and intermediate certificates to a file path. This can be useful in case of a disaster recovery scenario.</span></span> 
  
## <a name="parameters"></a><span data-ttu-id="d8ea4-114">Параметры</span><span class="sxs-lookup"><span data-stu-id="d8ea4-114">Parameters</span></span>
<span data-ttu-id="d8ea4-115"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="d8ea4-115"></span></span>

|<span data-ttu-id="d8ea4-116">**Параметр**</span><span class="sxs-lookup"><span data-stu-id="d8ea4-116">**Parameter**</span></span>|<span data-ttu-id="d8ea4-117">**Обязательно**</span><span class="sxs-lookup"><span data-stu-id="d8ea4-117">**Required**</span></span>|<span data-ttu-id="d8ea4-118">**Тип**</span><span class="sxs-lookup"><span data-stu-id="d8ea4-118">**Type**</span></span>|<span data-ttu-id="d8ea4-119">**Описание**</span><span class="sxs-lookup"><span data-stu-id="d8ea4-119">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="d8ea4-120">Путь</span><span class="sxs-lookup"><span data-stu-id="d8ea4-120">Path</span></span>  <br/> |<span data-ttu-id="d8ea4-121">Обязательно</span><span class="sxs-lookup"><span data-stu-id="d8ea4-121">Required</span></span>  <br/> |<span data-ttu-id="d8ea4-122">System.String</span><span class="sxs-lookup"><span data-stu-id="d8ea4-122">System.String</span></span>  <br/> |<span data-ttu-id="d8ea4-123">Путь к файлу, где будет сохранен сертификат. </span><span class="sxs-lookup"><span data-stu-id="d8ea4-123">File path where the certificate will be stored.</span></span>  <br/> |
   
## <a name="input-types"></a><span data-ttu-id="d8ea4-124">Типы входных данных</span><span class="sxs-lookup"><span data-stu-id="d8ea4-124">Input Types</span></span>
<span data-ttu-id="d8ea4-125"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="d8ea4-125"></span></span>

<span data-ttu-id="d8ea4-p103">Нет. Командлет Export-CcRootCertificate не принимает входные данные из конвейера. </span><span class="sxs-lookup"><span data-stu-id="d8ea4-p103">None. The Export-CcRootCertificate cmdlet does not accept pipelined input.</span></span> 
  
## <a name="return-types"></a><span data-ttu-id="d8ea4-128">Типы возвращаемых данных</span><span class="sxs-lookup"><span data-stu-id="d8ea4-128">Return Types</span></span>
<span data-ttu-id="d8ea4-129"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="d8ea4-129"></span></span>

<span data-ttu-id="d8ea4-130">Отсутствуют</span><span class="sxs-lookup"><span data-stu-id="d8ea4-130">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="d8ea4-131">См. также</span><span class="sxs-lookup"><span data-stu-id="d8ea4-131">See also</span></span>
<span data-ttu-id="d8ea4-132"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="d8ea4-132"></span></span>

<span data-ttu-id="d8ea4-133">Нет</span><span class="sxs-lookup"><span data-stu-id="d8ea4-133">None</span></span>
  

