---
title: Get-CcCredential
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 8/8/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b2b5aefb-a08d-4bec-9204-76597d413849
description: Командлет Get-CcCredential возвращает учетные данные текущего развертывания Skype для бизнеса Cloud Connector Edition.
ms.openlocfilehash: 4d8c9d95b9de0930e0c332f419f00947ca271821
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/28/2018
---
# <a name="get-cccredential"></a><span data-ttu-id="27004-103">Get-CcCredential</span><span class="sxs-lookup"><span data-stu-id="27004-103">Get-CcCredential</span></span>
 
<span data-ttu-id="27004-104">Командлет Get-CcCredential возвращает учетные данные текущего развертывания Skype для бизнеса Cloud Connector Edition.</span><span class="sxs-lookup"><span data-stu-id="27004-104">The Get-CcCredential cmdlet returns the credential of the current Skype for Business Cloud Connector Edition deployment.</span></span> 
  
<span data-ttu-id="27004-105">С версии 2.0 и более поздних версий можно также использовать параметр - DisplayPassword для отображения пароли для TenantAdmin, страница и VMAdmin.</span><span class="sxs-lookup"><span data-stu-id="27004-105">With Version 2.0 and later, you can also use the -DisplayPassword parameter to show the passwords for TenantAdmin, DomainAdmin, and VMAdmin.</span></span>
  
```
Get-CcCredential [[-AccountType] <string> {VmAdmin | DomainAdmin | SafeModeAdmin | ExternalCert | TenantAdmin}]
```

## <a name="examples"></a><span data-ttu-id="27004-106">Примеры</span><span class="sxs-lookup"><span data-stu-id="27004-106">Examples</span></span>
<span data-ttu-id="27004-107"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="27004-107"></span></span>

### <a name="example-1"></a><span data-ttu-id="27004-108">Пример 1</span><span class="sxs-lookup"><span data-stu-id="27004-108">Example 1</span></span>

<span data-ttu-id="27004-109">В следующем примере возвращаются учетные данные администратора домена виртуальной машины Cloud Connector:</span><span class="sxs-lookup"><span data-stu-id="27004-109">The following example returns the credential of the domain administrator of the Cloud Connector virtual machine domain:</span></span>
  
```
Get-CcCredential -AccountType DomainAdmin
```

## <a name="detailed-description"></a><span data-ttu-id="27004-110">Подробное описание</span><span class="sxs-lookup"><span data-stu-id="27004-110">Detailed Description</span></span>
<span data-ttu-id="27004-111"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="27004-111"></span></span>

<span data-ttu-id="27004-p101">Командлет Get-CcCredential возвращает сведения об учетных данных для указанного типа учетной записи. Эти учетные данные задаются администратором, который выполняет командлеты Register-CcAppliance и Install-CcAppliance при развертывании текущего устройства. </span><span class="sxs-lookup"><span data-stu-id="27004-p101">The Get-CcCredential cmdlet returns the credential information about the specified account type. These credentials are specified by the administrator who runs the Register-CcAppliance and Install-CcAppliance cmdlets when deploying the current appliance.</span></span> 
  
<span data-ttu-id="27004-p102">Командлет Get-CcCredential возвращает экземпляр объекта System.Management.Automation.PSCredential. Свойство password возвращаемого объекта имеет тип System.Security.SecureString.</span><span class="sxs-lookup"><span data-stu-id="27004-p102">The Get-CcCredential cmdlet returns an instance of the System.Management.Automation.PSCredential object. The password property of the return object is System.Security.SecureString.</span></span>
  
<span data-ttu-id="27004-116">Если вы хотите получить пароль администратора домена в открытом виде, введите пароль текущей учетной записи для входа на сервере узла, после чего откройте консоль PowerShell от имени администратора и выполните следующий скрипт:</span><span class="sxs-lookup"><span data-stu-id="27004-116">If you want to get the clear text of the domain administrator password, be sure the password is input by your current logon account on the host server, and then open a PowerShell console as administrator and run the below script:</span></span>
  
```
$cred = Get-CcCredential -AccountType DomainAdmin
$password =  $cred.Password
$bstr = [System.Runtime.InteropServices.Marshal]::SecureStringToBSTR($password);
$text = [System.Runtime.InteropServices.Marshal]::PtrToStringAuto($bstr);
[System.Runtime.InteropServices.Marshal]::ZeroFreeBSTR($bstr);
Write-Host $text

```

## <a name="parameters"></a><span data-ttu-id="27004-117">Параметры</span><span class="sxs-lookup"><span data-stu-id="27004-117">Parameters</span></span>
<span data-ttu-id="27004-118"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="27004-118"></span></span>

|<span data-ttu-id="27004-119">**Параметр**</span><span class="sxs-lookup"><span data-stu-id="27004-119">**Parameter**</span></span>|<span data-ttu-id="27004-120">**Обязательно**</span><span class="sxs-lookup"><span data-stu-id="27004-120">**Required**</span></span>|<span data-ttu-id="27004-121">**Тип**</span><span class="sxs-lookup"><span data-stu-id="27004-121">**Type**</span></span>|<span data-ttu-id="27004-122">**Описание**</span><span class="sxs-lookup"><span data-stu-id="27004-122">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="27004-123">AccountType</span><span class="sxs-lookup"><span data-stu-id="27004-123">AccountType</span></span> <br/> |<span data-ttu-id="27004-124">Обязательно</span><span class="sxs-lookup"><span data-stu-id="27004-124">Required</span></span>  <br/> | <span data-ttu-id="27004-125">System.String</span><span class="sxs-lookup"><span data-stu-id="27004-125">System.String</span></span> <br/> | <span data-ttu-id="27004-126">AccountType значение может быть одним из следующих:</span><span class="sxs-lookup"><span data-stu-id="27004-126">AccountType value can be one of the following:</span></span> <br/>  <span data-ttu-id="27004-127">VmAdmin: локальный администратор соединителя облачных виртуальных машин.</span><span class="sxs-lookup"><span data-stu-id="27004-127">VmAdmin: the local administrator of Cloud Connector virtual machines.</span></span> <br/>  <span data-ttu-id="27004-128">Страница: Администратора соединителя облачных виртуальной машины домена.</span><span class="sxs-lookup"><span data-stu-id="27004-128">DomainAdmin: Domain administrator of Cloud Connector virtual machine domain.</span></span> <br/>  <span data-ttu-id="27004-129">SafeModeAdmin. Администратор безопасного режима для контроллера домена виртуальных машин Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="27004-129">SafeModeAdmin: SafeModeAdmin of Cloud Connector virtual machine domain controller.</span></span> <br/>  <span data-ttu-id="27004-130">ExternalCert. Учетная запись для внешнего сертификата, установленного на пограничном сервере.</span><span class="sxs-lookup"><span data-stu-id="27004-130">ExternalCert: Account of external certificate installed on the Edge Server.</span></span> <br/>  <span data-ttu-id="27004-131">TenantAdmin. Администратор клиента O365.</span><span class="sxs-lookup"><span data-stu-id="27004-131">TenantAdmin: Administrator of the O365 tenant.</span></span> <br/> |
   
## <a name="input-types"></a><span data-ttu-id="27004-132">Типы входных данных</span><span class="sxs-lookup"><span data-stu-id="27004-132">Input Types</span></span>
<span data-ttu-id="27004-133"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="27004-133"></span></span>

<span data-ttu-id="27004-p103">Нет. Командлет Get-CcCredential не принимает входные данные по конвейеру.</span><span class="sxs-lookup"><span data-stu-id="27004-p103">None. The Get-CcCredential cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="27004-136">Типы возвращаемых данных</span><span class="sxs-lookup"><span data-stu-id="27004-136">Return Types</span></span>
<span data-ttu-id="27004-137"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="27004-137"></span></span>

<span data-ttu-id="27004-138">Командлет Get-CcCredential возвращает экземпляр объекта System.Management.Automation.PSCredential.</span><span class="sxs-lookup"><span data-stu-id="27004-138">The Get-CcCredential cmdlet returns an instance of the System.Management.Automation.PSCredential object.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="27004-139">См. также</span><span class="sxs-lookup"><span data-stu-id="27004-139">See also</span></span>
<span data-ttu-id="27004-140"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="27004-140"></span></span>

[<span data-ttu-id="27004-141">SET-CcCredential</span><span class="sxs-lookup"><span data-stu-id="27004-141">Set-CcCredential</span></span>](set-cccredential.md)
  

