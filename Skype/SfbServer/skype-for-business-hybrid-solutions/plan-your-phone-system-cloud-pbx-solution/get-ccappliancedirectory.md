---
title: Get-CcApplianceDirectory
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/31/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c2fda202-db2f-4122-b630-7df11a697c5f
description: 'Командлет Get-CcApplianceDirectory извлекает рабочий каталог на сервере узла Skype для бизнеса Cloud Connector Edition. В этом каталоге хранятся все файлы развертывания.  '
ms.openlocfilehash: c5c445e6017d8af81b681b70bbabcf2ba8bedd78
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/28/2018
---
# <a name="get-ccappliancedirectory"></a><span data-ttu-id="a1f92-104">Get-CcApplianceDirectory</span><span class="sxs-lookup"><span data-stu-id="a1f92-104">Get-CcApplianceDirectory</span></span>
 
<span data-ttu-id="a1f92-p102">Командлет Get-CcApplianceDirectory извлекает рабочий каталог на сервере узла Skype для бизнеса Cloud Connector Edition. В этом каталоге хранятся все файлы развертывания.  </span><span class="sxs-lookup"><span data-stu-id="a1f92-p102">The Get-CcApplianceDirectory cmdlet retrieves the working directory on the Skype for Business Cloud Connector Edition host server. All deployment files are stored in this directory.</span></span> 
  
<span data-ttu-id="a1f92-107">Этот командлет применяется к версии Skype для бизнеса Cloud Connector Edition 1.4.1, 1.4.2.</span><span class="sxs-lookup"><span data-stu-id="a1f92-107">This cmdlet applies to Skype for Business Cloud Connector Edition 1.4.1, 1.4.2.</span></span>
  
```
Get-CcApplianceDirectory
```

## <a name="parameters"></a><span data-ttu-id="a1f92-108">Параметры</span><span class="sxs-lookup"><span data-stu-id="a1f92-108">Parameters</span></span>

<span data-ttu-id="a1f92-109">Нет</span><span class="sxs-lookup"><span data-stu-id="a1f92-109">None</span></span>
  
## <a name="examples"></a><span data-ttu-id="a1f92-110">Примеры</span><span class="sxs-lookup"><span data-stu-id="a1f92-110">Examples</span></span>
<span data-ttu-id="a1f92-111"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="a1f92-111"></span></span>

### <a name="example-1"></a><span data-ttu-id="a1f92-112">Пример 1</span><span class="sxs-lookup"><span data-stu-id="a1f92-112">Example 1</span></span>

<span data-ttu-id="a1f92-113">В следующем примере показано текущую папку, где хранятся файлы конфигурации и виртуальной машины из облака соединитель компонентов:</span><span class="sxs-lookup"><span data-stu-id="a1f92-113">The following example shows the current folder where configuration and virtual machine files of Cloud Connector components are stored:</span></span>
  
```
Get-CcApplianceDirectory
```

## <a name="detailed-description"></a><span data-ttu-id="a1f92-114">Подробное описание</span><span class="sxs-lookup"><span data-stu-id="a1f92-114">Detailed Description</span></span>
<span data-ttu-id="a1f92-115"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="a1f92-115"></span></span>

<span data-ttu-id="a1f92-116">Показывает командлет Get-CcApplianceDirectory, где хранятся все файлы конфигурации и виртуальной машины, журналы и внешние сертификаты для устройства соединителя облачных.</span><span class="sxs-lookup"><span data-stu-id="a1f92-116">The Get-CcApplianceDirectory cmdlet shows where all configuration and virtual machine files, logs, and external certificates are stored for the Cloud Connector appliance.</span></span>
  
<span data-ttu-id="a1f92-117">Устройство для каждого соединителя облачных состоит из четырех компонентов: сервер-посредник, центрального хранилища управления, пограничный сервер и контроллер домена.</span><span class="sxs-lookup"><span data-stu-id="a1f92-117">Each Cloud Connector appliance has four components: Mediation Server, Central Management Store, Edge Server, and a Domain Controller.</span></span> <span data-ttu-id="a1f92-118">Папка по умолчанию является C:\Users\%userprofile%\CloudConnector\ApplianceRoot.</span><span class="sxs-lookup"><span data-stu-id="a1f92-118">The default folder is C:\Users\%userprofile%\CloudConnector\ApplianceRoot.</span></span> <span data-ttu-id="a1f92-119">Чтобы изменить этот каталог, выполните командлет Set-CcApplianceDirectory.</span><span class="sxs-lookup"><span data-stu-id="a1f92-119">You can change this folder by using the Set-CCApplianceDirectory cmdlet.</span></span>
  
## <a name="input-types"></a><span data-ttu-id="a1f92-120">Типы входных данных</span><span class="sxs-lookup"><span data-stu-id="a1f92-120">Input Types</span></span>
<span data-ttu-id="a1f92-121"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="a1f92-121"></span></span>

<span data-ttu-id="a1f92-p104">Нет. Командлет Get-CCApplianceDirectory не принимает входные данные по конвейеру.</span><span class="sxs-lookup"><span data-stu-id="a1f92-p104">None. The Get-CCApplianceDirectory cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="a1f92-124">Типы возвращаемых данных</span><span class="sxs-lookup"><span data-stu-id="a1f92-124">Return Types</span></span>
<span data-ttu-id="a1f92-125"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="a1f92-125"></span></span>

<span data-ttu-id="a1f92-126">Команда возвращает путь к файлу.</span><span class="sxs-lookup"><span data-stu-id="a1f92-126">The command returns a file path.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="a1f92-127">См. также</span><span class="sxs-lookup"><span data-stu-id="a1f92-127">See also</span></span>
<span data-ttu-id="a1f92-128"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="a1f92-128"></span></span>

[<span data-ttu-id="a1f92-129">SET-CcApplianceDirectory</span><span class="sxs-lookup"><span data-stu-id="a1f92-129">Set-CcApplianceDirectory</span></span>](set-ccappliancedirectory.md)
  

