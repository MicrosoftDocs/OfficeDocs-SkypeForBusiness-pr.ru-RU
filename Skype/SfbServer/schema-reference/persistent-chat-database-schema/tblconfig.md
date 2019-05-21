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
localization_priority: Normal
ms.assetid: 7445e7db-c574-46fa-b964-8640d77047a8
description: Тблконфиг включает в себя неподдерживаемую конфигурацию сервера чатов в одной строке.
ms.openlocfilehash: 244eebcb88c67b521022f9d64888678f221d2369
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295456"
---
# <a name="tblconfig"></a><span data-ttu-id="52302-103">tblConfig</span><span class="sxs-lookup"><span data-stu-id="52302-103">tblConfig</span></span>
 
<span data-ttu-id="52302-104">Тблконфиг включает в себя неподдерживаемую конфигурацию сервера чатов в одной строке.</span><span class="sxs-lookup"><span data-stu-id="52302-104">tblConfig contains some Persistent Chat Server unsupported configuration, in one row.</span></span>
  
<span data-ttu-id="52302-105">**Столбцов**</span><span class="sxs-lookup"><span data-stu-id="52302-105">**Columns**</span></span>

|<span data-ttu-id="52302-106">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="52302-106">**Column**</span></span>|<span data-ttu-id="52302-107">**Тип**</span><span class="sxs-lookup"><span data-stu-id="52302-107">**Type**</span></span>|<span data-ttu-id="52302-108">**Описание**</span><span class="sxs-lookup"><span data-stu-id="52302-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="52302-109">Конфиглабел</span><span class="sxs-lookup"><span data-stu-id="52302-109">configLabel</span></span>  <br/> |<span data-ttu-id="52302-110">nvarchar (255), NOT NULL</span><span class="sxs-lookup"><span data-stu-id="52302-110">nvarchar (255), not null</span></span>  <br/> |<span data-ttu-id="52302-111">Группа "пул".</span><span class="sxs-lookup"><span data-stu-id="52302-111">Contains "pool."</span></span>  <br/> |
|<span data-ttu-id="52302-112">Конфигконтент</span><span class="sxs-lookup"><span data-stu-id="52302-112">configContent</span></span>  <br/> |<span data-ttu-id="52302-113">nvarchar (max)</span><span class="sxs-lookup"><span data-stu-id="52302-113">nvarchar (max)</span></span>  <br/> |<span data-ttu-id="52302-114">Содержимое конфигурации.</span><span class="sxs-lookup"><span data-stu-id="52302-114">Configuration content.</span></span>  <br/> |
|<span data-ttu-id="52302-115">Конфигпулид</span><span class="sxs-lookup"><span data-stu-id="52302-115">configPoolID</span></span>  <br/> |<span data-ttu-id="52302-116">GUID, а не NULL</span><span class="sxs-lookup"><span data-stu-id="52302-116">GUID, not null</span></span>  <br/> |<span data-ttu-id="52302-117">Уникальный идентификатор экземпляра базы данных.</span><span class="sxs-lookup"><span data-stu-id="52302-117">Unique ID of the database instance.</span></span>  <br/> |
   
<span data-ttu-id="52302-118">**Ключ**</span><span class="sxs-lookup"><span data-stu-id="52302-118">**Key**</span></span>

|<span data-ttu-id="52302-119">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="52302-119">**Column**</span></span>|<span data-ttu-id="52302-120">**Описание**</span><span class="sxs-lookup"><span data-stu-id="52302-120">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="52302-121">Конфиглабел</span><span class="sxs-lookup"><span data-stu-id="52302-121">configLabel</span></span>  <br/> |<span data-ttu-id="52302-122">Первичный ключ.</span><span class="sxs-lookup"><span data-stu-id="52302-122">Primary key.</span></span>  <br/> |
   

