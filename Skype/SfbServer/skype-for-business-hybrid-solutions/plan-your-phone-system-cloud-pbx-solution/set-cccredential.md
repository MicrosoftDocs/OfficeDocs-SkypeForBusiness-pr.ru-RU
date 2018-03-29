---
title: SET-CcCredential
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 8/8/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 784ff94a-4b33-4dbd-ba74-27acc3eb6954
description: 'Командлет Set-CcCredential задает учетные данные текущего развертывания Skype для бизнеса Cloud Connector Edition. '
ms.openlocfilehash: 7680f863ccf082ddb8359c7d3fcefc2c058b6a40
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/28/2018
---
# <a name="set-cccredential"></a><span data-ttu-id="81168-103">SET-CcCredential</span><span class="sxs-lookup"><span data-stu-id="81168-103">Set-CcCredential</span></span>
 
<span data-ttu-id="81168-104">Командлет Set-CcCredential задает учетные данные текущего развертывания Skype для бизнеса Cloud Connector Edition. </span><span class="sxs-lookup"><span data-stu-id="81168-104">The Set-CcCredential cmdlet sets the credential of the current Skype for Business Cloud Connector Edition deployment.</span></span> 
  
<span data-ttu-id="81168-105">С соединителем облачных версии 2.0 и более поздних версий этот командлет также можно настроить учетные данные администратора виртуальной машины, а также для администратора домена.</span><span class="sxs-lookup"><span data-stu-id="81168-105">With Cloud Connector version 2.0 and later, this cmdlet can also set the account information for the virtual machine administrator and for the domain administrator.</span></span>
  
```
Set-CcCredential [[-AccountType] <string> {TenantAdmin}]
```

## <a name="examples"></a><span data-ttu-id="81168-106">Примеры</span><span class="sxs-lookup"><span data-stu-id="81168-106">Examples</span></span>
<span data-ttu-id="81168-107"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="81168-107"></span></span>

### <a name="example-1"></a><span data-ttu-id="81168-108">Пример 1</span><span class="sxs-lookup"><span data-stu-id="81168-108">Example 1</span></span>

<span data-ttu-id="81168-109">В следующем примере задаются имя и пароль учетной записи для администратора клиента.</span><span class="sxs-lookup"><span data-stu-id="81168-109">The following example specifies the account name and password for the tenant administrator:</span></span>
  
```
Set-CcCredential -AccountType "TenantAdmin"
```

## <a name="detailed-description"></a><span data-ttu-id="81168-110">Подробное описание</span><span class="sxs-lookup"><span data-stu-id="81168-110">Detailed Description</span></span>
<span data-ttu-id="81168-111"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="81168-111"></span></span>

<span data-ttu-id="81168-112">Командлет Set-CcCredential задает имя и пароль учетной записи для администратора клиента.</span><span class="sxs-lookup"><span data-stu-id="81168-112">The Set-CcCredential cmdlet sets the account name and password for the tenant administrator.</span></span> <span data-ttu-id="81168-113">Для выпусков до 2.0 этот администратор должен быть глобального администратора Office 365.</span><span class="sxs-lookup"><span data-stu-id="81168-113">For releases prior to 2.0, this administrator must be an Office 365 Global Administrator.</span></span> <span data-ttu-id="81168-114">Облако соединитель использует эту учетную запись для получения сведений о конфигурации, задайте параметры конфигурации, а состояние обновления устройства для обеспечения связи в конфигурации клиента Office 365.</span><span class="sxs-lookup"><span data-stu-id="81168-114">Cloud Connector uses this account to get configuration information, set configuration parameters, and update appliance status to the Office 365 tenant configuration.</span></span> <span data-ttu-id="81168-115">В версии 2.0 и более поздних версий, можно также использовать этот командлет для обновления паролей для учетных записей VmAdmin и страница.</span><span class="sxs-lookup"><span data-stu-id="81168-115">With release 2.0 and later, you can also use this cmdlet to update the passwords for the VmAdmin and DomainAdmin accounts.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="81168-116">Параметры</span><span class="sxs-lookup"><span data-stu-id="81168-116">Parameters</span></span>
<span data-ttu-id="81168-117"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="81168-117"></span></span>

|<span data-ttu-id="81168-118">**Параметр**</span><span class="sxs-lookup"><span data-stu-id="81168-118">**Parameter**</span></span>|<span data-ttu-id="81168-119">**Обязательно**</span><span class="sxs-lookup"><span data-stu-id="81168-119">**Required**</span></span>|<span data-ttu-id="81168-120">**Тип**</span><span class="sxs-lookup"><span data-stu-id="81168-120">**Type**</span></span>|<span data-ttu-id="81168-121">**Описание**</span><span class="sxs-lookup"><span data-stu-id="81168-121">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="81168-122">AccountType</span><span class="sxs-lookup"><span data-stu-id="81168-122">AccountType</span></span> <br/> | <span data-ttu-id="81168-123">Обязательно</span><span class="sxs-lookup"><span data-stu-id="81168-123">Required</span></span> <br/> |<span data-ttu-id="81168-124">System.String</span><span class="sxs-lookup"><span data-stu-id="81168-124">System.String</span></span>  <br/> | <span data-ttu-id="81168-125"> Параметр должен иметь значение "TenantAdmin", "VmAdmin" или "DomainAdmin".</span><span class="sxs-lookup"><span data-stu-id="81168-125">Parameter value must be "TenantAdmin", "VmAdmin", or "DomainAdmin".</span></span> <br/> |
   
## <a name="input-types"></a><span data-ttu-id="81168-126">Типы входных данных</span><span class="sxs-lookup"><span data-stu-id="81168-126">Input Types</span></span>
<span data-ttu-id="81168-127"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="81168-127"></span></span>

<span data-ttu-id="81168-p102">Отсутствуют. Командлет Set-CcCredential не принимает входные данные по конвейеру.</span><span class="sxs-lookup"><span data-stu-id="81168-p102">None. The Set-CcCredential cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="81168-130">Типы возвращаемых данных</span><span class="sxs-lookup"><span data-stu-id="81168-130">Return Types</span></span>
<span data-ttu-id="81168-131"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="81168-131"></span></span>

<span data-ttu-id="81168-132">Нет</span><span class="sxs-lookup"><span data-stu-id="81168-132">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="81168-133">См. также</span><span class="sxs-lookup"><span data-stu-id="81168-133">See also</span></span>
<span data-ttu-id="81168-134"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="81168-134"></span></span>

[<span data-ttu-id="81168-135">Get-CcCredential</span><span class="sxs-lookup"><span data-stu-id="81168-135">Get-CcCredential</span></span>](get-cccredential.md)
  

