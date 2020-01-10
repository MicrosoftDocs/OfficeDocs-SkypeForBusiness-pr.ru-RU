---
title: Get-CcApplianceDirectory
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/31/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c2fda202-db2f-4122-b630-7df11a697c5f
description: 'Командлет Get-CcApplianceDirectory извлекает рабочий каталог на сервере узла Skype для бизнеса Cloud Connector Edition. В этом каталоге хранятся все файлы развертывания.  '
ms.openlocfilehash: 77064676062411c3417e554e422b0ffaae461191
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/09/2020
ms.locfileid: "41003409"
---
# <a name="get-ccappliancedirectory"></a><span data-ttu-id="b7144-104">Get-CcApplianceDirectory</span><span class="sxs-lookup"><span data-stu-id="b7144-104">Get-CcApplianceDirectory</span></span>
 
<span data-ttu-id="b7144-p102">Командлет Get-CcApplianceDirectory извлекает рабочий каталог на сервере узла Skype для бизнеса Cloud Connector Edition. В этом каталоге хранятся все файлы развертывания.  </span><span class="sxs-lookup"><span data-stu-id="b7144-p102">The Get-CcApplianceDirectory cmdlet retrieves the working directory on the Skype for Business Cloud Connector Edition host server. All deployment files are stored in this directory.</span></span> 
  
<span data-ttu-id="b7144-107">Этот командлет применяется к версии Skype для бизнеса Cloud Connector Edition 1.4.1, 1.4.2.</span><span class="sxs-lookup"><span data-stu-id="b7144-107">This cmdlet applies to Skype for Business Cloud Connector Edition 1.4.1, 1.4.2.</span></span>
  
```powershell
Get-CcApplianceDirectory
```

## <a name="parameters"></a><span data-ttu-id="b7144-108">Параметры</span><span class="sxs-lookup"><span data-stu-id="b7144-108">Parameters</span></span>

<span data-ttu-id="b7144-109">Нет</span><span class="sxs-lookup"><span data-stu-id="b7144-109">None</span></span>
  
## <a name="examples"></a><span data-ttu-id="b7144-110">Примеры</span><span class="sxs-lookup"><span data-stu-id="b7144-110">Examples</span></span>
<span data-ttu-id="b7144-111"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="b7144-111"></span></span>

### <a name="example-1"></a><span data-ttu-id="b7144-112">Пример 1</span><span class="sxs-lookup"><span data-stu-id="b7144-112">Example 1</span></span>

<span data-ttu-id="b7144-113">В следующем примере показана текущая папка, в которой хранятся файлы конфигурации и виртуальных машин в компонентах облачного соединителя.</span><span class="sxs-lookup"><span data-stu-id="b7144-113">The following example shows the current folder where configuration and virtual machine files of Cloud Connector components are stored:</span></span>
  
```powershell
Get-CcApplianceDirectory
```

## <a name="detailed-description"></a><span data-ttu-id="b7144-114">Подробное описание</span><span class="sxs-lookup"><span data-stu-id="b7144-114">Detailed Description</span></span>
<span data-ttu-id="b7144-115"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="b7144-115"></span></span>

<span data-ttu-id="b7144-116">Командлет Get-Ккапплианцедиректори показывает, какие файлы конфигурации и виртуальных машин, журналы и внешние сертификаты хранятся для устройства облачного соединителя.</span><span class="sxs-lookup"><span data-stu-id="b7144-116">The Get-CcApplianceDirectory cmdlet shows where all configuration and virtual machine files, logs, and external certificates are stored for the Cloud Connector appliance.</span></span>
  
<span data-ttu-id="b7144-117">У каждого устройства облачного соединителя есть четыре компонента: сервер-посредник, хранилище Центрального управления, пограничный сервер и контроллер домена.</span><span class="sxs-lookup"><span data-stu-id="b7144-117">Each Cloud Connector appliance has four components: Mediation Server, Central Management Store, Edge Server, and a Domain Controller.</span></span> <span data-ttu-id="b7144-118">По умолчанию используется папка\%к:\усерс усерпрофиле%\клаудконнектор\апплианцерут.</span><span class="sxs-lookup"><span data-stu-id="b7144-118">The default folder is C:\Users\%userprofile%\CloudConnector\ApplianceRoot.</span></span> <span data-ttu-id="b7144-119">Чтобы изменить этот каталог, выполните командлет Set-CcApplianceDirectory.</span><span class="sxs-lookup"><span data-stu-id="b7144-119">You can change this folder by using the Set-CCApplianceDirectory cmdlet.</span></span>
  
## <a name="input-types"></a><span data-ttu-id="b7144-120">Типы входных данных</span><span class="sxs-lookup"><span data-stu-id="b7144-120">Input Types</span></span>
<span data-ttu-id="b7144-121"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="b7144-121"></span></span>

<span data-ttu-id="b7144-p104">Нет. Командлет Get-CCApplianceDirectory не принимает входные данные по конвейеру.</span><span class="sxs-lookup"><span data-stu-id="b7144-p104">None. The Get-CCApplianceDirectory cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="b7144-124">Типы возвращаемых данных</span><span class="sxs-lookup"><span data-stu-id="b7144-124">Return Types</span></span>
<span data-ttu-id="b7144-125"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="b7144-125"></span></span>

<span data-ttu-id="b7144-126">Команда возвращает путь к файлу.</span><span class="sxs-lookup"><span data-stu-id="b7144-126">The command returns a file path.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="b7144-127">См. также</span><span class="sxs-lookup"><span data-stu-id="b7144-127">See also</span></span>
<span data-ttu-id="b7144-128"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="b7144-128"></span></span>

[<span data-ttu-id="b7144-129">Set-CcApplianceDirectory</span><span class="sxs-lookup"><span data-stu-id="b7144-129">Set-CcApplianceDirectory</span></span>](set-ccappliancedirectory.md)
  

