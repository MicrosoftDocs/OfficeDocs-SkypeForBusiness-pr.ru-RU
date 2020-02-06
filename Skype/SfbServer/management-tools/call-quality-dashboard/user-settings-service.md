---
title: Служба параметров пользователя для панели мониторинга качества звонков (CQD)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: eafeb54a-2574-415b-b991-a0ff0470d8c3
description: 'Сводка: сведения о службе параметров пользователя, которая входит в состав API репозитория для панели мониторинга качества звонков. Панель мониторинга качества звонков — это средство для Skype для бизнеса Server.'
ms.openlocfilehash: 1eef869523bf1590a00ca199727b33ec9e13ccba
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816648"
---
# <a name="user-settings-service-for-call-quality-dashboard-cqd"></a><span data-ttu-id="28465-104">Служба параметров пользователя для панели мониторинга качества звонков (CQD)</span><span class="sxs-lookup"><span data-stu-id="28465-104">User Settings Service for Call Quality Dashboard (CQD)</span></span>
 
<span data-ttu-id="28465-105">**Сводка:** Сведения о службе параметров пользователя, которая входит в состав API репозитория для панели мониторинга качества звонков.</span><span class="sxs-lookup"><span data-stu-id="28465-105">**Summary:** Learn about the User Settings Service, which is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="28465-106">Панель мониторинга качества звонков — это средство для Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="28465-106">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="28465-107">Служба параметров пользователя входит в API репозитория для панели мониторинга качества звонков.</span><span class="sxs-lookup"><span data-stu-id="28465-107">The User Settings Service is part of the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="user-settings-service"></a><span data-ttu-id="28465-108">Служба параметров пользователя</span><span class="sxs-lookup"><span data-stu-id="28465-108">User Settings Service</span></span>

<span data-ttu-id="28465-109">Пользовательские настройки — это пары "ключ-значение", которые могут использоваться приложениями для хранения метаданных для различных целей, включая настройку поведения приложения для каждого пользователя.</span><span class="sxs-lookup"><span data-stu-id="28465-109">User settings are key-value pairs that applications can use to store metadata for various purposes including customization of application behaviors per-user basis.</span></span> <span data-ttu-id="28465-110">Каждый пользователь получает хранилище для параметров пользователя.</span><span class="sxs-lookup"><span data-stu-id="28465-110">Each user receives a storage for user settings.</span></span> <span data-ttu-id="28465-111">Только владельцы могут добавлять, изменять и удалять параметры пользователей.</span><span class="sxs-lookup"><span data-stu-id="28465-111">Only the owners can add, modify, and remove user settings.</span></span>
  
 <span data-ttu-id="28465-112">**Глобальные параметры**</span><span class="sxs-lookup"><span data-stu-id="28465-112">**Global Settings**</span></span>
  
<span data-ttu-id="28465-113">Глобальные параметры — это пользовательские параметры, принадлежащие пользователю системы, и все пользователи имеют к ним доступ только для чтения.</span><span class="sxs-lookup"><span data-stu-id="28465-113">Global settings are the user settings owned by the system user, and all users have read-only access to them.</span></span> <span data-ttu-id="28465-114">Глобальные параметры являются константами: они создаются во время создания репозитория, и они никогда не изменяются.</span><span class="sxs-lookup"><span data-stu-id="28465-114">Global settings are constants: they are created during the repository creation, and they never change.</span></span>
  
<span data-ttu-id="28465-115">Каждый пользователь может переопределить глобальные параметры, создав параметры пользователя с теми же ключами.</span><span class="sxs-lookup"><span data-stu-id="28465-115">Each user can override global settings by creating user settings with the same keys.</span></span> <span data-ttu-id="28465-116">Когда приложение запрашивает действующие параметры пользователя, API возвращает набор глобальных параметров, Объединенных с параметрами пользователя, при этом каждый параметр пользователя заменяет соответствующий глобальный параметр в том случае, если клавиши совпадают.</span><span class="sxs-lookup"><span data-stu-id="28465-116">When application requests the effective user settings, the API returns a set of global settings merged with the user settings, with each user setting superseding the respective global setting if keys are the same.</span></span> <span data-ttu-id="28465-117">API также может возвращать только параметры пользователя, чтобы приложения могли узнать, какие параметры переопределены.</span><span class="sxs-lookup"><span data-stu-id="28465-117">The API can also return just the user settings so that applications can find out which settings are overridden.</span></span> 
  
<span data-ttu-id="28465-118">Операции RESTFUL включены в таблицу ниже.</span><span class="sxs-lookup"><span data-stu-id="28465-118">The REST operations are included in the following table.</span></span>

|<span data-ttu-id="28465-119">**Операция**</span><span class="sxs-lookup"><span data-stu-id="28465-119">**Operation**</span></span>|<span data-ttu-id="28465-120">**Описание**</span><span class="sxs-lookup"><span data-stu-id="28465-120">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="28465-121">Получение параметров пользователя</span><span class="sxs-lookup"><span data-stu-id="28465-121">Get User Settings</span></span>](get-user-settings.md) <br/> |<span data-ttu-id="28465-122">Получить параметры пользователя возвращает список параметров для указанного пользователя.</span><span class="sxs-lookup"><span data-stu-id="28465-122">Get User Settings returns a list of settings for a specified user.</span></span>  <br/> |
|[<span data-ttu-id="28465-123">Получение параметра пользователя</span><span class="sxs-lookup"><span data-stu-id="28465-123">Get User Setting</span></span>](get-user-setting.md) <br/> |<span data-ttu-id="28465-124">Параметр получить параметры пользователя возвращает один пользовательский параметр.</span><span class="sxs-lookup"><span data-stu-id="28465-124">Get User Setting returns a single user setting.</span></span>  <br/> |
   

