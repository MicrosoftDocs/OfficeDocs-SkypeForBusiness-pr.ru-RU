---
title: Export-CcRootCertificate
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 9/20/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 1499e33c-6a7c-46b9-b9a1-f78d7853b45d
description: 'Командлет Export-CcRootCertificate экспортирует корневой сертификат ЦС в локальный файл на сервере узла Skype для бизнеса Cloud Connector Edition. '
ms.openlocfilehash: 7d6d0978698b4b20b570107b51c9a89ff237b730
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "34287385"
---
# <a name="export-ccrootcertificate"></a><span data-ttu-id="38924-103">Export-CcRootCertificate</span><span class="sxs-lookup"><span data-stu-id="38924-103">Export-CcRootCertificate</span></span>
 
<span data-ttu-id="38924-104">Командлет Export-CcRootCertificate экспортирует корневой сертификат ЦС в локальный файл на сервере узла Skype для бизнеса Cloud Connector Edition. </span><span class="sxs-lookup"><span data-stu-id="38924-104">The Export-CcRootCertificate cmdlet exports the root CA certificate to a local file on the Skype for Business Cloud Connector Edition host server.</span></span> 
  
```
Export-CcRootCertificate [[-Path] <string>]
```

## <a name="examples"></a><span data-ttu-id="38924-105">Примеры</span><span class="sxs-lookup"><span data-stu-id="38924-105">Examples</span></span>
<span data-ttu-id="38924-106"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="38924-106"></span></span>

### <a name="example-1"></a><span data-ttu-id="38924-107">Пример 1</span><span class="sxs-lookup"><span data-stu-id="38924-107">Example 1</span></span>

<span data-ttu-id="38924-p101">В следующем примере параметр Path задается как путь к каталогу, а не к файлу. В нем создается файл c:\test\CCERootCertificates.p7b.</span><span class="sxs-lookup"><span data-stu-id="38924-p101">The following example sets the Path parameter as a directory path—not a file path. It generates the file c:\test\CCERootCertificates.p7b.</span></span>
  
```
Export-CcRootCertificate -Path "C:\test" 
```

## <a name="detailed-description"></a><span data-ttu-id="38924-110">Подробное описание</span><span class="sxs-lookup"><span data-stu-id="38924-110">Detailed Description</span></span>
<span data-ttu-id="38924-111"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="38924-111"></span></span>

<span data-ttu-id="38924-p102">Командлет Export-CcRootCertificate позволяет вам сохранять корневые и промежуточные сертификаты, указав путь к файлу. Это может помочь при аварийном восстановлении. </span><span class="sxs-lookup"><span data-stu-id="38924-p102">The Export-CcRootCertificate cmdlet allows you to save the root and intermediate certificates to a file path. This can be useful in case of a disaster recovery scenario.</span></span> 
  
## <a name="parameters"></a><span data-ttu-id="38924-114">Параметры</span><span class="sxs-lookup"><span data-stu-id="38924-114">Parameters</span></span>
<span data-ttu-id="38924-115"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="38924-115"></span></span>

|<span data-ttu-id="38924-116">**Параметр**</span><span class="sxs-lookup"><span data-stu-id="38924-116">**Parameter**</span></span>|<span data-ttu-id="38924-117">**Обязательно**</span><span class="sxs-lookup"><span data-stu-id="38924-117">**Required**</span></span>|<span data-ttu-id="38924-118">**Тип**</span><span class="sxs-lookup"><span data-stu-id="38924-118">**Type**</span></span>|<span data-ttu-id="38924-119">**Описание**</span><span class="sxs-lookup"><span data-stu-id="38924-119">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="38924-120">Путь</span><span class="sxs-lookup"><span data-stu-id="38924-120">Path</span></span>  <br/> |<span data-ttu-id="38924-121">Обязательно</span><span class="sxs-lookup"><span data-stu-id="38924-121">Required</span></span>  <br/> |<span data-ttu-id="38924-122">System.String</span><span class="sxs-lookup"><span data-stu-id="38924-122">System.String</span></span>  <br/> |<span data-ttu-id="38924-123">Путь к файлу, где будет сохранен сертификат. </span><span class="sxs-lookup"><span data-stu-id="38924-123">File path where the certificate will be stored.</span></span>  <br/> |
   
## <a name="input-types"></a><span data-ttu-id="38924-124">Типы входных данных</span><span class="sxs-lookup"><span data-stu-id="38924-124">Input Types</span></span>
<span data-ttu-id="38924-125"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="38924-125"></span></span>

<span data-ttu-id="38924-p103">Нет. Командлет Export-CcRootCertificate не принимает входные данные из конвейера. </span><span class="sxs-lookup"><span data-stu-id="38924-p103">None. The Export-CcRootCertificate cmdlet does not accept pipelined input.</span></span> 
  
## <a name="return-types"></a><span data-ttu-id="38924-128">Типы возвращаемых данных</span><span class="sxs-lookup"><span data-stu-id="38924-128">Return Types</span></span>
<span data-ttu-id="38924-129"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="38924-129"></span></span>

<span data-ttu-id="38924-130">Отсутствуют</span><span class="sxs-lookup"><span data-stu-id="38924-130">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="38924-131">См. также</span><span class="sxs-lookup"><span data-stu-id="38924-131">See also</span></span>
<span data-ttu-id="38924-132"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="38924-132"></span></span>

<span data-ttu-id="38924-133">Нет</span><span class="sxs-lookup"><span data-stu-id="38924-133">None</span></span>
  

