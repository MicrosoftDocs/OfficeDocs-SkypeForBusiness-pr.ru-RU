---
title: tblADCookie
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 0a9102c4-47aa-40ea-8a0d-20e72ab09848
description: Тбладкукие включает в себя текущие cookie-файлы для синхронизации протокола Lightweight Directory Access.
ms.openlocfilehash: c9a4c666a5fe4a76ecb3685f60f1208ec3ea88ed
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814707"
---
# <a name="tbladcookie"></a><span data-ttu-id="fb59b-103">tblADCookie</span><span class="sxs-lookup"><span data-stu-id="fb59b-103">tblADCookie</span></span>
 
<span data-ttu-id="fb59b-104">Тбладкукие включает в себя текущие cookie-файлы для синхронизации протокола Lightweight Directory Access.</span><span class="sxs-lookup"><span data-stu-id="fb59b-104">tblADCookie contains the current Lightweight Directory Access Protocol (LDAP) Sync cookies.</span></span>
  
<span data-ttu-id="fb59b-105">**Столбцов**</span><span class="sxs-lookup"><span data-stu-id="fb59b-105">**Columns**</span></span>

|<span data-ttu-id="fb59b-106">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="fb59b-106">**Column**</span></span>|<span data-ttu-id="fb59b-107">**Тип**</span><span class="sxs-lookup"><span data-stu-id="fb59b-107">**Type**</span></span>|<span data-ttu-id="fb59b-108">**Описание**</span><span class="sxs-lookup"><span data-stu-id="fb59b-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="fb59b-109">прингуид</span><span class="sxs-lookup"><span data-stu-id="fb59b-109">prinGuid</span></span>  <br/> |<span data-ttu-id="fb59b-110">GUID, а не NULL</span><span class="sxs-lookup"><span data-stu-id="fb59b-110">GUID, not null</span></span>  <br/> |<span data-ttu-id="fb59b-111">Идентификатор GUID участника отслеживаемого домена.</span><span class="sxs-lookup"><span data-stu-id="fb59b-111">Principal GUID of the domain being monitored.</span></span>  <br/> |
|<span data-ttu-id="fb59b-112">приндчост</span><span class="sxs-lookup"><span data-stu-id="fb59b-112">prinDCHost</span></span>  <br/> |<span data-ttu-id="fb59b-113">nvarchar (255)</span><span class="sxs-lookup"><span data-stu-id="fb59b-113">nvarchar (255)</span></span>  <br/> |<span data-ttu-id="fb59b-114">Полное доменное имя (FQDN) текущего контроллера домена, используемого для синхронизации доменных служб Active Directory. Имеет информационное значение.</span><span class="sxs-lookup"><span data-stu-id="fb59b-114">Fully qualified domain name (FQDN) of the current domain controller used for Active Directory Domain Services Sync. Has informational value.</span></span>  <br/> |
|<span data-ttu-id="fb59b-115">адкконтент</span><span class="sxs-lookup"><span data-stu-id="fb59b-115">adcContent</span></span>  <br/> |<span data-ttu-id="fb59b-116">изображение (двоичное)</span><span class="sxs-lookup"><span data-stu-id="fb59b-116">image (binary)</span></span>  <br/> |<span data-ttu-id="fb59b-117">Cookie синхронизации Active Directory.</span><span class="sxs-lookup"><span data-stu-id="fb59b-117">Active Directory Sync cookie.</span></span>  <br/> |
|<span data-ttu-id="fb59b-118">ластупдатед</span><span class="sxs-lookup"><span data-stu-id="fb59b-118">lastUpdated</span></span>  <br/> |<span data-ttu-id="fb59b-119">datetime</span><span class="sxs-lookup"><span data-stu-id="fb59b-119">datetime</span></span>  <br/> |<span data-ttu-id="fb59b-120">Метка времени со временем обновления строки.</span><span class="sxs-lookup"><span data-stu-id="fb59b-120">Time stamp with the row update time.</span></span>  <br/> |
|<span data-ttu-id="fb59b-121">локкедунтил</span><span class="sxs-lookup"><span data-stu-id="fb59b-121">lockedUntil</span></span>  <br/> |<span data-ttu-id="fb59b-122">datetime</span><span class="sxs-lookup"><span data-stu-id="fb59b-122">datetime</span></span>  <br/> |<span data-ttu-id="fb59b-123">Время, по истечении которого изменения строки будут заблокированы.</span><span class="sxs-lookup"><span data-stu-id="fb59b-123">Time until the row is locked for changes.</span></span> <span data-ttu-id="fb59b-124">Это является частью механизма программного обеспечения, который гарантирует, что только одна из служб чата выполняет синхронизацию службы каталогов Active Directory за один раз.</span><span class="sxs-lookup"><span data-stu-id="fb59b-124">This is part of a software interlock mechanism that ensures that only one of the chat services does the Active Directory Sync at a time.</span></span>  <br/> |
   
<span data-ttu-id="fb59b-125">**Параметры**</span><span class="sxs-lookup"><span data-stu-id="fb59b-125">**Keys**</span></span>

|<span data-ttu-id="fb59b-126">**Столбцы (-ы)**</span><span class="sxs-lookup"><span data-stu-id="fb59b-126">**Column(s)**</span></span>|<span data-ttu-id="fb59b-127">**Описание**</span><span class="sxs-lookup"><span data-stu-id="fb59b-127">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="fb59b-128">прингуид</span><span class="sxs-lookup"><span data-stu-id="fb59b-128">prinGuid</span></span>  <br/> |<span data-ttu-id="fb59b-129">Первичный ключ.</span><span class="sxs-lookup"><span data-stu-id="fb59b-129">Primary key.</span></span>  <br/> |
|<span data-ttu-id="fb59b-130">прингуид</span><span class="sxs-lookup"><span data-stu-id="fb59b-130">prinGuid</span></span>  <br/> |<span data-ttu-id="fb59b-131">Внешний ключ с подстановкой в таблице Principal. Прингуид.</span><span class="sxs-lookup"><span data-stu-id="fb59b-131">Foreign key with lookup in Principal.prinGuid table.</span></span>  <br/> |
   

