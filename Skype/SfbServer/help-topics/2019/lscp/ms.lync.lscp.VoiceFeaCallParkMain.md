---
title: Парковка вызовов
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 3/24/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.VoiceFeaCallParkMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b752617d-554d-470e-b17b-387403ac74ed
description: При приостановке звонка его перемещается временные номера которых содержится вызов, пока кто-то извлекает или истечения времени ожидания. Необходимо настроить таблицу с диапазонами добавочные номера, который резервируется для приостановленных звонков. Эти добавочные номера должны быть виртуальными (то есть не иметь назначенного пользователя или назначенный телефон). Каждый пул, на котором выполняется приложение парковки вызовов может содержать один или несколько диапазонов расширений. Эти диапазоны должны быть уникальными в рамках всего развертывания.
ms.openlocfilehash: 64cd83d8efd692b7ac6d221588eb3b56dead2c0b
ms.sourcegitcommit: 9d816453083c26fd24f8a1cdc0f53f3d218c43b3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/25/2018
---
# <a name="call-park"></a><span data-ttu-id="978c2-106">Приостановка вызовов</span><span class="sxs-lookup"><span data-stu-id="978c2-106">Call Park</span></span>
 
<span data-ttu-id="978c2-107">При приостановке звонка его перемещается временные номера которых содержится вызов, пока кто-то извлекает или истечения времени ожидания. Необходимо настроить таблицу с диапазонами добавочные номера, который резервируется для приостановленных звонков.</span><span class="sxs-lookup"><span data-stu-id="978c2-107">When a call is parked, it is transferred to a temporary number where the call is held until someone retrieves it or it times out. You need to configure a table with the ranges of extension numbers that you are reserving for parked calls.</span></span> <span data-ttu-id="978c2-108">Эти добавочные номера должны быть виртуальными (то есть не иметь назначенного пользователя или назначенный телефон).</span><span class="sxs-lookup"><span data-stu-id="978c2-108">These extensions need to be virtual extensions (that is, extensions that have no user or phone assigned to them).</span></span> <span data-ttu-id="978c2-109">Каждый пул, на котором выполняется приложение парковки вызовов может содержать один или несколько диапазонов расширений.</span><span class="sxs-lookup"><span data-stu-id="978c2-109">Each pool that runs the Call Park application can have one or more ranges of extensions.</span></span> <span data-ttu-id="978c2-110">Эти диапазоны должны быть уникальными в рамках всего развертывания.</span><span class="sxs-lookup"><span data-stu-id="978c2-110">These ranges must be globally unique across your deployment.</span></span>
  
<span data-ttu-id="978c2-111">** Парковки вызовов ** странице отображается список всех парковки вызовов диапазонов номеров, определенных для вашей организации.</span><span class="sxs-lookup"><span data-stu-id="978c2-111">The ** Call Park** page displays a list of all the Call Park number ranges that are defined for your organization.</span></span>
  
## <a name="tasks-you-can-perform"></a><span data-ttu-id="978c2-112">Задачи, которые вы можете выполнить</span><span class="sxs-lookup"><span data-stu-id="978c2-112">Tasks you can perform</span></span>

<span data-ttu-id="978c2-113">На странице **Парковка вызовов** можно выполнять следующие задачи:</span><span class="sxs-lookup"><span data-stu-id="978c2-113">You can perform the following tasks from the **Call Park** page:</span></span>
  
- <span data-ttu-id="978c2-114">создать новый диапазон номеров;</span><span class="sxs-lookup"><span data-stu-id="978c2-114">Create a new number range</span></span>
    
- <span data-ttu-id="978c2-115">изменить существующий диапазон номеров;</span><span class="sxs-lookup"><span data-stu-id="978c2-115">Change an existing number range</span></span>
    
- <span data-ttu-id="978c2-116">удалить диапазон номеров.</span><span class="sxs-lookup"><span data-stu-id="978c2-116">Delete a number range</span></span>
    
## <a name="ui-reference"></a><span data-ttu-id="978c2-117">Ссылка на пользовательский интерфейс</span><span class="sxs-lookup"><span data-stu-id="978c2-117">UI Reference</span></span>

<span data-ttu-id="978c2-118">В следующем списке описываются команды на странице.</span><span class="sxs-lookup"><span data-stu-id="978c2-118">The following list describes the commands on the page.</span></span>
  
- <span data-ttu-id="978c2-119">**Новые** Создает новый диапазон номеров парковки вызовов.</span><span class="sxs-lookup"><span data-stu-id="978c2-119">**New** Starts a new Call Park number range.</span></span>
    
- <span data-ttu-id="978c2-120">**Изменение** Открывает выбранный диапазон номеров для правки, выбирает все диапазоны номеров в списке или удаляет выбранный диапазон номеров.</span><span class="sxs-lookup"><span data-stu-id="978c2-120">**Edit** Opens the selected number range for editing, selects all number ranges in the list, or deletes the selected number range.</span></span>
    
- <span data-ttu-id="978c2-121">**Обновление** Обновляет список диапазонов номеров.</span><span class="sxs-lookup"><span data-stu-id="978c2-121">**Refresh** Refreshes the list of number ranges.</span></span>
    
<span data-ttu-id="978c2-122">В следующем списке описываются поля на странице.</span><span class="sxs-lookup"><span data-stu-id="978c2-122">The following list describes the fields on the page.</span></span>
  
- <span data-ttu-id="978c2-123">**Имя** Уникальное имя диапазона номеров.</span><span class="sxs-lookup"><span data-stu-id="978c2-123">**Name** The unique name that identifies the number range.</span></span>
    
- <span data-ttu-id="978c2-124">**Начало диапазона** Первый номер диапазона.</span><span class="sxs-lookup"><span data-stu-id="978c2-124">**Start range** The beginning number of the range.</span></span>
    
- <span data-ttu-id="978c2-125">**Конец диапазона** Конечный номер диапазона.</span><span class="sxs-lookup"><span data-stu-id="978c2-125">**End range** The ending number of the range.</span></span>
    
- <span data-ttu-id="978c2-126">**Назначения** Полное доменное имя (FQDN) или идентификатор службы приложения, на котором размещается приложение парковки вызовов для диапазона номеров службы.</span><span class="sxs-lookup"><span data-stu-id="978c2-126">**Destination** The fully qualified domain name (FQDN) or service ID of the Application service that hosts the Call Park application for the number range.</span></span>
    
<span data-ttu-id="978c2-127">Для получения дополнительных сведений о парковки вызовов функций и возможностей видеть [Планирование парковки вызовов в Скайп для 2015 бизнеса](../../../plan-your-deployment/enterprise-voice-solution/call-park.md).</span><span class="sxs-lookup"><span data-stu-id="978c2-127">For details about Call Park features and capabilities, see [Plan for Call Park in Skype for Business 2015](../../../plan-your-deployment/enterprise-voice-solution/call-park.md).</span></span> <span data-ttu-id="978c2-128">Для получения дополнительных сведений о работе с диапазоны номеров для парковки вызовов видеть [Настройки расширений номер телефона для парковки вызовов](http://technet.microsoft.com/library/fbf97624-9587-42a6-b276-1b69c574a74d.aspx).</span><span class="sxs-lookup"><span data-stu-id="978c2-128">For details about working with Call Park number ranges, see [Configure Phone Number Extensions for Parking Calls](http://technet.microsoft.com/library/fbf97624-9587-42a6-b276-1b69c574a74d.aspx).</span></span>
  

