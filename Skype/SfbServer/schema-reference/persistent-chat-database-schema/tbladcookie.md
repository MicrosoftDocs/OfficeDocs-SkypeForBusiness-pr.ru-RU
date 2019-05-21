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
localization_priority: Normal
ms.assetid: 0a9102c4-47aa-40ea-8a0d-20e72ab09848
description: Тбладкукие включает в себя текущие cookie-файлы для синхронизации протокола Lightweight Directory Access.
ms.openlocfilehash: d75b1dc90d36aa0535fdac62b9e1a7061694cc76
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295533"
---
# <a name="tbladcookie"></a><span data-ttu-id="fb34e-103">tblADCookie</span><span class="sxs-lookup"><span data-stu-id="fb34e-103">tblADCookie</span></span>
 
<span data-ttu-id="fb34e-104">Тбладкукие включает в себя текущие cookie-файлы для синхронизации протокола Lightweight Directory Access.</span><span class="sxs-lookup"><span data-stu-id="fb34e-104">tblADCookie contains the current Lightweight Directory Access Protocol (LDAP) Sync cookies.</span></span>
  
<span data-ttu-id="fb34e-105">**Столбцов**</span><span class="sxs-lookup"><span data-stu-id="fb34e-105">**Columns**</span></span>

|<span data-ttu-id="fb34e-106">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="fb34e-106">**Column**</span></span>|<span data-ttu-id="fb34e-107">**Тип**</span><span class="sxs-lookup"><span data-stu-id="fb34e-107">**Type**</span></span>|<span data-ttu-id="fb34e-108">**Описание**</span><span class="sxs-lookup"><span data-stu-id="fb34e-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="fb34e-109">Прингуид</span><span class="sxs-lookup"><span data-stu-id="fb34e-109">prinGuid</span></span>  <br/> |<span data-ttu-id="fb34e-110">GUID, а не NULL</span><span class="sxs-lookup"><span data-stu-id="fb34e-110">GUID, not null</span></span>  <br/> |<span data-ttu-id="fb34e-111">Идентификатор GUID участника отслеживаемого домена.</span><span class="sxs-lookup"><span data-stu-id="fb34e-111">Principal GUID of the domain being monitored.</span></span>  <br/> |
|<span data-ttu-id="fb34e-112">Приндчост</span><span class="sxs-lookup"><span data-stu-id="fb34e-112">prinDCHost</span></span>  <br/> |<span data-ttu-id="fb34e-113">nvarchar (255)</span><span class="sxs-lookup"><span data-stu-id="fb34e-113">nvarchar (255)</span></span>  <br/> |<span data-ttu-id="fb34e-114">Полное доменное имя (FQDN) текущего контроллера домена, используемого для синхронизации доменных служб Active Directory. Имеет информационное значение.</span><span class="sxs-lookup"><span data-stu-id="fb34e-114">Fully qualified domain name (FQDN) of the current domain controller used for Active Directory Domain Services Sync. Has informational value.</span></span>  <br/> |
|<span data-ttu-id="fb34e-115">Адкконтент</span><span class="sxs-lookup"><span data-stu-id="fb34e-115">adcContent</span></span>  <br/> |<span data-ttu-id="fb34e-116">изображение (двоичное)</span><span class="sxs-lookup"><span data-stu-id="fb34e-116">image (binary)</span></span>  <br/> |<span data-ttu-id="fb34e-117">Cookie синхронизации Active Directory.</span><span class="sxs-lookup"><span data-stu-id="fb34e-117">Active Directory Sync cookie.</span></span>  <br/> |
|<span data-ttu-id="fb34e-118">Ластупдатед</span><span class="sxs-lookup"><span data-stu-id="fb34e-118">lastUpdated</span></span>  <br/> |<span data-ttu-id="fb34e-119">datetime</span><span class="sxs-lookup"><span data-stu-id="fb34e-119">datetime</span></span>  <br/> |<span data-ttu-id="fb34e-120">Метка времени со временем обновления строки.</span><span class="sxs-lookup"><span data-stu-id="fb34e-120">Time stamp with the row update time.</span></span>  <br/> |
|<span data-ttu-id="fb34e-121">Локкедунтил</span><span class="sxs-lookup"><span data-stu-id="fb34e-121">lockedUntil</span></span>  <br/> |<span data-ttu-id="fb34e-122">datetime</span><span class="sxs-lookup"><span data-stu-id="fb34e-122">datetime</span></span>  <br/> |<span data-ttu-id="fb34e-123">Время, по истечении которого изменения строки будут заблокированы.</span><span class="sxs-lookup"><span data-stu-id="fb34e-123">Time until the row is locked for changes.</span></span> <span data-ttu-id="fb34e-124">Это является частью механизма программного обеспечения, который гарантирует, что только одна из служб чата выполняет синхронизацию службы каталогов Active Directory за один раз.</span><span class="sxs-lookup"><span data-stu-id="fb34e-124">This is part of a software interlock mechanism that ensures that only one of the chat services does the Active Directory Sync at a time.</span></span>  <br/> |
   
<span data-ttu-id="fb34e-125">**Параметры**</span><span class="sxs-lookup"><span data-stu-id="fb34e-125">**Keys**</span></span>

|<span data-ttu-id="fb34e-126">**Столбцы (-ы)**</span><span class="sxs-lookup"><span data-stu-id="fb34e-126">**Column(s)**</span></span>|<span data-ttu-id="fb34e-127">**Описание**</span><span class="sxs-lookup"><span data-stu-id="fb34e-127">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="fb34e-128">Прингуид</span><span class="sxs-lookup"><span data-stu-id="fb34e-128">prinGuid</span></span>  <br/> |<span data-ttu-id="fb34e-129">Первичный ключ.</span><span class="sxs-lookup"><span data-stu-id="fb34e-129">Primary key.</span></span>  <br/> |
|<span data-ttu-id="fb34e-130">Прингуид</span><span class="sxs-lookup"><span data-stu-id="fb34e-130">prinGuid</span></span>  <br/> |<span data-ttu-id="fb34e-131">Внешний ключ с подстановкой в таблице Principal. Прингуид.</span><span class="sxs-lookup"><span data-stu-id="fb34e-131">Foreign key with lookup in Principal.prinGuid table.</span></span>  <br/> |
   

