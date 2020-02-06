---
title: tblConfig
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
ms.assetid: 7445e7db-c574-46fa-b964-8640d77047a8
description: Тблконфиг включает в себя неподдерживаемую конфигурацию сервера чатов в одной строке.
ms.openlocfilehash: f79af00d6a9f97f0ce0836684a284779be662c1d
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814627"
---
# <a name="tblconfig"></a><span data-ttu-id="78447-103">tblConfig</span><span class="sxs-lookup"><span data-stu-id="78447-103">tblConfig</span></span>
 
<span data-ttu-id="78447-104">Тблконфиг включает в себя неподдерживаемую конфигурацию сервера чатов в одной строке.</span><span class="sxs-lookup"><span data-stu-id="78447-104">tblConfig contains some Persistent Chat Server unsupported configuration, in one row.</span></span>
  
<span data-ttu-id="78447-105">**Столбцов**</span><span class="sxs-lookup"><span data-stu-id="78447-105">**Columns**</span></span>

|<span data-ttu-id="78447-106">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="78447-106">**Column**</span></span>|<span data-ttu-id="78447-107">**Тип**</span><span class="sxs-lookup"><span data-stu-id="78447-107">**Type**</span></span>|<span data-ttu-id="78447-108">**Описание**</span><span class="sxs-lookup"><span data-stu-id="78447-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="78447-109">конфиглабел</span><span class="sxs-lookup"><span data-stu-id="78447-109">configLabel</span></span>  <br/> |<span data-ttu-id="78447-110">nvarchar (255), NOT NULL</span><span class="sxs-lookup"><span data-stu-id="78447-110">nvarchar (255), not null</span></span>  <br/> |<span data-ttu-id="78447-111">Группа "пул".</span><span class="sxs-lookup"><span data-stu-id="78447-111">Contains "pool."</span></span>  <br/> |
|<span data-ttu-id="78447-112">конфигконтент</span><span class="sxs-lookup"><span data-stu-id="78447-112">configContent</span></span>  <br/> |<span data-ttu-id="78447-113">nvarchar (max)</span><span class="sxs-lookup"><span data-stu-id="78447-113">nvarchar (max)</span></span>  <br/> |<span data-ttu-id="78447-114">Содержимое конфигурации.</span><span class="sxs-lookup"><span data-stu-id="78447-114">Configuration content.</span></span>  <br/> |
|<span data-ttu-id="78447-115">конфигпулид</span><span class="sxs-lookup"><span data-stu-id="78447-115">configPoolID</span></span>  <br/> |<span data-ttu-id="78447-116">GUID, а не NULL</span><span class="sxs-lookup"><span data-stu-id="78447-116">GUID, not null</span></span>  <br/> |<span data-ttu-id="78447-117">Уникальный идентификатор экземпляра базы данных.</span><span class="sxs-lookup"><span data-stu-id="78447-117">Unique ID of the database instance.</span></span>  <br/> |
   
<span data-ttu-id="78447-118">**Ключ**</span><span class="sxs-lookup"><span data-stu-id="78447-118">**Key**</span></span>

|<span data-ttu-id="78447-119">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="78447-119">**Column**</span></span>|<span data-ttu-id="78447-120">**Описание**</span><span class="sxs-lookup"><span data-stu-id="78447-120">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="78447-121">конфиглабел</span><span class="sxs-lookup"><span data-stu-id="78447-121">configLabel</span></span>  <br/> |<span data-ttu-id="78447-122">Первичный ключ.</span><span class="sxs-lookup"><span data-stu-id="78447-122">Primary key.</span></span>  <br/> |
   

