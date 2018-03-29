---
title: Резервное копирование CcCertificationAuthority
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/31/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 47ed4559-fb63-42cd-8ecd-b7d1617e91d3
description: Командлет Backup-CcCertificationAuthority выполняет резервное копирование службы центра сертификации Skype для бизнеса Cloud Connector Edition в файл и сохраняет папку CA в общем каталоге сайта.
ms.openlocfilehash: b3cb566dc72b3966eaa1480f3e17e4d6b46c06a2
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/28/2018
---
# <a name="backup-cccertificationauthority"></a><span data-ttu-id="ffc66-103">Резервное копирование CcCertificationAuthority</span><span class="sxs-lookup"><span data-stu-id="ffc66-103">Backup-CcCertificationAuthority</span></span>
 
<span data-ttu-id="ffc66-104">Командлет Backup-CcCertificationAuthority выполняет резервное копирование службы центра сертификации Skype для бизнеса Cloud Connector Edition в файл и сохраняет папку CA в общем каталоге сайта.</span><span class="sxs-lookup"><span data-stu-id="ffc66-104">The Backup-CcCertificationAuthority cmdlet backs up the Skype for Business Cloud Connector Edition certification authority service to a file and saves it to the CA folder under the site share directory.</span></span>
  
```
Backup-CcCertificationAuthority 
```

## <a name="parameters"></a><span data-ttu-id="ffc66-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="ffc66-105">Parameters</span></span>

<span data-ttu-id="ffc66-106">Нет</span><span class="sxs-lookup"><span data-stu-id="ffc66-106">None</span></span>
  
## <a name="examples"></a><span data-ttu-id="ffc66-107">Примеры</span><span class="sxs-lookup"><span data-stu-id="ffc66-107">Examples</span></span>
<span data-ttu-id="ffc66-108"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="ffc66-108"></span></span>

### <a name="example-1"></a><span data-ttu-id="ffc66-109">Пример 1</span><span class="sxs-lookup"><span data-stu-id="ffc66-109">Example 1</span></span>

<span data-ttu-id="ffc66-110">В следующем примере выполняется резервное копирование службы центра сертификации в файл и сохранение папки CA в общем каталоге сайта.</span><span class="sxs-lookup"><span data-stu-id="ffc66-110">The following example backs up the certification authority service to a file and saves it to the CA folder under the site share directory:</span></span>
  
```
Backup-CcCertificationAuthority 
```

## <a name="detailed-description"></a><span data-ttu-id="ffc66-111">Подробное описание</span><span class="sxs-lookup"><span data-stu-id="ffc66-111">Detailed Description</span></span>
<span data-ttu-id="ffc66-112"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="ffc66-112"></span></span>

<span data-ttu-id="ffc66-113">Резервное копирование центра сертификации можно использовать, если необходимо выполнить заново appliance облачных соединителя с тот же сертификат в случае сбоя, или если вы хотите переместить устройства для обеспечения связи в новое оборудование.</span><span class="sxs-lookup"><span data-stu-id="ffc66-113">Certification authority backup can be useful if you plan to redeploy a Cloud Connector appliance with the same certificate in case of a disaster, or if you want to move the appliance to new hardware.</span></span> <span data-ttu-id="ffc66-114">Команда сохраняет копию служба центра сертификации облачных соединителя с сервера AD для "\<SiteRootDirectory\>\CA\SfB системы CCE Root.p12».</span><span class="sxs-lookup"><span data-stu-id="ffc66-114">The command saves the copy of the Cloud Connector certification authority service from the AD Server to  "\<SiteRootDirectory\>\CA\SfB CCE Root.p12".</span></span>
  
## <a name="input-types"></a><span data-ttu-id="ffc66-115">Типы входных данных</span><span class="sxs-lookup"><span data-stu-id="ffc66-115">Input Types</span></span>
<span data-ttu-id="ffc66-116"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="ffc66-116"></span></span>

<span data-ttu-id="ffc66-p102">Нет. Командлет Backup-CcCertificationAuthority не принимает входные данные по конвейеру.</span><span class="sxs-lookup"><span data-stu-id="ffc66-p102">None. The Backup-CcCertificationAuthority cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="ffc66-119">Типы возвращаемых данных</span><span class="sxs-lookup"><span data-stu-id="ffc66-119">Return Types</span></span>
<span data-ttu-id="ffc66-120"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="ffc66-120"></span></span>

<span data-ttu-id="ffc66-121">Нет</span><span class="sxs-lookup"><span data-stu-id="ffc66-121">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="ffc66-122">См. также</span><span class="sxs-lookup"><span data-stu-id="ffc66-122">See also</span></span>
<span data-ttu-id="ffc66-123"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="ffc66-123"></span></span>

[<span data-ttu-id="ffc66-124">Remove-CcCertificationAuthorityFile</span><span class="sxs-lookup"><span data-stu-id="ffc66-124">Remove-CcCertificationAuthorityFile</span></span>](remove-cccertificationauthorityfile.md)
  

