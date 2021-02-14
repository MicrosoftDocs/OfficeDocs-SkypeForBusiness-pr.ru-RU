---
title: Get-CcCredential
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 8/8/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: b2b5aefb-a08d-4bec-9204-76597d413849
description: Этот Get-CcCredential возвращает учетные данные текущего развертывания Skype для бизнеса Cloud Connector Edition.
ms.openlocfilehash: c4e2d47ffc31eb7afef76c710fc93024ce2c593e
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41800399"
---
# <a name="get-cccredential"></a><span data-ttu-id="07965-103">Get-CcCredential</span><span class="sxs-lookup"><span data-stu-id="07965-103">Get-CcCredential</span></span>
 
<span data-ttu-id="07965-104">Этот Get-CcCredential возвращает учетные данные текущего развертывания Skype для бизнеса Cloud Connector Edition.</span><span class="sxs-lookup"><span data-stu-id="07965-104">The Get-CcCredential cmdlet returns the credential of the current Skype for Business Cloud Connector Edition deployment.</span></span> 
  
<span data-ttu-id="07965-105">В версиях 2.0 и более поздних версий можно также использовать параметр -DisplayPassword для отображения паролей для TenantAdmin, DomainAdmin и VMAdmin.</span><span class="sxs-lookup"><span data-stu-id="07965-105">With Version 2.0 and later, you can also use the -DisplayPassword parameter to show the passwords for TenantAdmin, DomainAdmin, and VMAdmin.</span></span>
  
```powershell
Get-CcCredential [[-AccountType] <string> {VmAdmin | DomainAdmin | SafeModeAdmin | ExternalCert | TenantAdmin}]
```

## <a name="examples"></a><span data-ttu-id="07965-106">Примеры</span><span class="sxs-lookup"><span data-stu-id="07965-106">Examples</span></span>
<span data-ttu-id="07965-107"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="07965-107"><a name="Examples"> </a></span></span>

### <a name="example-1"></a><span data-ttu-id="07965-108">Пример 1</span><span class="sxs-lookup"><span data-stu-id="07965-108">Example 1</span></span>

<span data-ttu-id="07965-109">В следующем примере возвращаются учетные данные администратора домена виртуальной машины Cloud Connector:</span><span class="sxs-lookup"><span data-stu-id="07965-109">The following example returns the credential of the domain administrator of the Cloud Connector virtual machine domain:</span></span>
  
```powershell
Get-CcCredential -AccountType DomainAdmin
```

## <a name="detailed-description"></a><span data-ttu-id="07965-110">Подробное описание</span><span class="sxs-lookup"><span data-stu-id="07965-110">Detailed Description</span></span>
<span data-ttu-id="07965-111"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="07965-111"><a name="DetailedDescription"> </a></span></span>

<span data-ttu-id="07965-112">Этот Get-CcCredential возвращает учетные данные об указанном типе учетной записи.</span><span class="sxs-lookup"><span data-stu-id="07965-112">The Get-CcCredential cmdlet returns the credential information about the specified account type.</span></span> <span data-ttu-id="07965-113">Эти учетные данные заданы администратором, который запускает Register-CcAppliance и Install-CcAppliance при развертывании текущего устройства.</span><span class="sxs-lookup"><span data-stu-id="07965-113">These credentials are specified by the administrator who runs the Register-CcAppliance and Install-CcAppliance cmdlets when deploying the current appliance.</span></span> 
  
<span data-ttu-id="07965-114">Этот Get-CcCredential возвращает экземпляр объекта System.Management.Automation.PSCredential.</span><span class="sxs-lookup"><span data-stu-id="07965-114">The Get-CcCredential cmdlet returns an instance of the System.Management.Automation.PSCredential object.</span></span> <span data-ttu-id="07965-115">Свойство password возвращаемого объекта — System.Security.SecureString.</span><span class="sxs-lookup"><span data-stu-id="07965-115">The password property of the return object is System.Security.SecureString.</span></span>
  
<span data-ttu-id="07965-116">Если вы хотите получить понятный текст пароля администратора домена, убедитесь, что пароль введен текущей учетной записью входа на сервере хост-сервера, а затем откройте консоль PowerShell от имени администратора и запустите сценарий ниже:</span><span class="sxs-lookup"><span data-stu-id="07965-116">If you want to get the clear text of the domain administrator password, be sure the password is input by your current logon account on the host server, and then open a PowerShell console as administrator and run the below script:</span></span>
  
```powershell
$cred = Get-CcCredential -AccountType DomainAdmin
$password =  $cred.Password
$bstr = [System.Runtime.InteropServices.Marshal]::SecureStringToBSTR($password);
$text = [System.Runtime.InteropServices.Marshal]::PtrToStringAuto($bstr);
[System.Runtime.InteropServices.Marshal]::ZeroFreeBSTR($bstr);
Write-Host $text
```

## <a name="parameters"></a><span data-ttu-id="07965-117">Параметры</span><span class="sxs-lookup"><span data-stu-id="07965-117">Parameters</span></span>
<span data-ttu-id="07965-118"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="07965-118"><a name="DetailedDescription"> </a></span></span>

|<span data-ttu-id="07965-119">**Параметр**</span><span class="sxs-lookup"><span data-stu-id="07965-119">**Parameter**</span></span>|<span data-ttu-id="07965-120">**Required**</span><span class="sxs-lookup"><span data-stu-id="07965-120">**Required**</span></span>|<span data-ttu-id="07965-121">**Тип**</span><span class="sxs-lookup"><span data-stu-id="07965-121">**Type**</span></span>|<span data-ttu-id="07965-122">**Описание**</span><span class="sxs-lookup"><span data-stu-id="07965-122">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="07965-123">AccountType</span><span class="sxs-lookup"><span data-stu-id="07965-123">AccountType</span></span> <br/> |<span data-ttu-id="07965-124">Обязательный</span><span class="sxs-lookup"><span data-stu-id="07965-124">Required</span></span>  <br/> | <span data-ttu-id="07965-125">System.String</span><span class="sxs-lookup"><span data-stu-id="07965-125">System.String</span></span> <br/> | <span data-ttu-id="07965-126">Значение AccountType может быть одним из следующих значений:</span><span class="sxs-lookup"><span data-stu-id="07965-126">AccountType value can be one of the following:</span></span> <br/>  <span data-ttu-id="07965-127">VmAdmin: локальный администратор виртуальных машин Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="07965-127">VmAdmin: the local administrator of Cloud Connector virtual machines.</span></span> <br/>  <span data-ttu-id="07965-128">DomainAdmin: администратор домена виртуальной машины Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="07965-128">DomainAdmin: Domain administrator of Cloud Connector virtual machine domain.</span></span> <br/>  <span data-ttu-id="07965-129">SafeModeAdmin: SafeModeAdmin контроллера домена виртуальной машины Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="07965-129">SafeModeAdmin: SafeModeAdmin of Cloud Connector virtual machine domain controller.</span></span> <br/>  <span data-ttu-id="07965-130">ExternalCert: учетная запись внешнего сертификата, установленного на edge Server.</span><span class="sxs-lookup"><span data-stu-id="07965-130">ExternalCert: Account of external certificate installed on the Edge Server.</span></span> <br/>  <span data-ttu-id="07965-131">TenantAdmin: администратор клиента O365.</span><span class="sxs-lookup"><span data-stu-id="07965-131">TenantAdmin: Administrator of the O365 tenant.</span></span> <br/> |
   
## <a name="input-types"></a><span data-ttu-id="07965-132">Типы входных данных</span><span class="sxs-lookup"><span data-stu-id="07965-132">Input Types</span></span>
<span data-ttu-id="07965-133"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="07965-133"><a name="InputTypes"> </a></span></span>

<span data-ttu-id="07965-134">Нет.</span><span class="sxs-lookup"><span data-stu-id="07965-134">None.</span></span> <span data-ttu-id="07965-135">Этот Get-CcCredential не принимает конвейерные входные данные.</span><span class="sxs-lookup"><span data-stu-id="07965-135">The Get-CcCredential cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="07965-136">Типы возвращаемых данных</span><span class="sxs-lookup"><span data-stu-id="07965-136">Return Types</span></span>
<span data-ttu-id="07965-137"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="07965-137"><a name="ReturnTypes"> </a></span></span>

<span data-ttu-id="07965-138">Этот Get-CcCredential возвращает экземпляр объекта System.Management.Automation.PSCredential.</span><span class="sxs-lookup"><span data-stu-id="07965-138">The Get-CcCredential cmdlet returns an instance of the System.Management.Automation.PSCredential object.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="07965-139">См. также</span><span class="sxs-lookup"><span data-stu-id="07965-139">See also</span></span>
<span data-ttu-id="07965-140"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="07965-140"><a name="ReturnTypes"> </a></span></span>

[<span data-ttu-id="07965-141">Set-CcCredential</span><span class="sxs-lookup"><span data-stu-id="07965-141">Set-CcCredential</span></span>](set-cccredential.md)
  

