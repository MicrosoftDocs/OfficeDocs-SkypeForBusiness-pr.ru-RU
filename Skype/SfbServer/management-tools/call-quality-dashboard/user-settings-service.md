---
title: Служба параметров пользователя для панели мониторинга качества звонков (CQD)
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: eafeb54a-2574-415b-b991-a0ff0470d8c3
description: 'Сводка: Сведения о службе параметров пользователя, которая является частью API репозитория для панели мониторинга качества звонков. Панель мониторинга качества звонков — это средство для Скайп для Business Server.'
ms.openlocfilehash: 00d0662e777ef2f13c9783fe4b79d5c582faa8af
ms.sourcegitcommit: b680505c5dad435d98fbd0b235e0e7c67b9d8c9c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/07/2018
ms.locfileid: "26035612"
---
# <a name="user-settings-service-for-call-quality-dashboard-cqd"></a><span data-ttu-id="e3565-104">Служба параметров пользователя для панели мониторинга качества звонков (CQD)</span><span class="sxs-lookup"><span data-stu-id="e3565-104">User Settings Service for Call Quality Dashboard (CQD)</span></span>
 
<span data-ttu-id="e3565-105">**Сводка:** Сведения о службе параметров пользователя, которая является частью API репозитория для панели мониторинга качества звонков.</span><span class="sxs-lookup"><span data-stu-id="e3565-105">**Summary:** Learn about the User Settings Service, which is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="e3565-106">Панель мониторинга качества звонков — это средство для Скайп для Business Server.</span><span class="sxs-lookup"><span data-stu-id="e3565-106">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="e3565-107">Служба параметров пользователя входит в API репозитория для панели мониторинга качества звонков.</span><span class="sxs-lookup"><span data-stu-id="e3565-107">The User Settings Service is part of the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="user-settings-service"></a><span data-ttu-id="e3565-108">Служба параметров пользователя</span><span class="sxs-lookup"><span data-stu-id="e3565-108">User Settings Service</span></span>

<span data-ttu-id="e3565-109">Параметры пользователя, пары "ключ значение", приложения могут использовать для хранения метаданных для различных целей, включая настройки отдельных на пользователя модели поведения приложений.</span><span class="sxs-lookup"><span data-stu-id="e3565-109">User settings are key-value pairs that applications can use to store metadata for various purposes including customization of application behaviors per-user basis.</span></span> <span data-ttu-id="e3565-110">Каждый пользователь получает хранилища для параметров пользователя.</span><span class="sxs-lookup"><span data-stu-id="e3565-110">Each user receives a storage for user settings.</span></span> <span data-ttu-id="e3565-111">Только владелец можно добавлять, изменять и удалять пользовательские параметры.</span><span class="sxs-lookup"><span data-stu-id="e3565-111">Only the owners can add, modify, and remove user settings.</span></span>
  
 <span data-ttu-id="e3565-112">**Глобальные параметры**</span><span class="sxs-lookup"><span data-stu-id="e3565-112">**Global Settings**</span></span>
  
<span data-ttu-id="e3565-113">Глобальные параметры являются параметры пользователя, принадлежащие пользователю системы и все пользователи имеют доступ только для чтения к ним.</span><span class="sxs-lookup"><span data-stu-id="e3565-113">Global settings are the user settings owned by the system user, and all users have read-only access to them.</span></span> <span data-ttu-id="e3565-114">Глобальные параметры, являются константами: созданные ими во время создания репозитория, и они никогда не изменяется.</span><span class="sxs-lookup"><span data-stu-id="e3565-114">Global settings are constants: they are created during the repository creation, and they never change.</span></span>
  
<span data-ttu-id="e3565-115">Каждый пользователь может переопределять значение глобальные параметры путем создания пользовательских параметров с ключами.</span><span class="sxs-lookup"><span data-stu-id="e3565-115">Each user can override global settings by creating user settings with the same keys.</span></span> <span data-ttu-id="e3565-116">Когда приложение запрашивает параметры действующего пользователя, API возвращает набор глобальных параметров объединяются с параметрами пользователей с заменой соответствующих глобальный параметр, если ключи совпадают с каждого из параметров пользователя.</span><span class="sxs-lookup"><span data-stu-id="e3565-116">When application requests the effective user settings, the API returns a set of global settings merged with the user settings, with each user setting superseding the respective global setting if keys are the same.</span></span> <span data-ttu-id="e3565-117">API-Интерфейс может также возвращать только что параметров пользователя, чтобы приложения узнать, какие параметры переопределяются.</span><span class="sxs-lookup"><span data-stu-id="e3565-117">The API can also return just the user settings so that applications can find out which settings are overridden.</span></span> 
  
<span data-ttu-id="e3565-118">В следующей таблице включены операции REST.</span><span class="sxs-lookup"><span data-stu-id="e3565-118">The REST operations are included in the following table.</span></span>

|<span data-ttu-id="e3565-119">**Операция**</span><span class="sxs-lookup"><span data-stu-id="e3565-119">**Operation**</span></span>|<span data-ttu-id="e3565-120">**Описание**</span><span class="sxs-lookup"><span data-stu-id="e3565-120">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="e3565-121">Получение параметров пользователя</span><span class="sxs-lookup"><span data-stu-id="e3565-121">Get User Settings</span></span>](get-user-settings.md) <br/> |<span data-ttu-id="e3565-122">Параметры пользователя Get возвращает список параметров для указанного пользователя.</span><span class="sxs-lookup"><span data-stu-id="e3565-122">Get User Settings returns a list of settings for a specified user.</span></span>  <br/> |
|[<span data-ttu-id="e3565-123">Получить параметры пользователя</span><span class="sxs-lookup"><span data-stu-id="e3565-123">Get User Setting</span></span>](get-user-setting.md) <br/> |<span data-ttu-id="e3565-124">Получите возвращает параметр пользователя параметр с одним пользователем.</span><span class="sxs-lookup"><span data-stu-id="e3565-124">Get User Setting returns a single user setting.</span></span>  <br/> |
   

