---
title: Парковка вызовов
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/24/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.VoiceFeaCallParkMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b752617d-554d-470e-b17b-387403ac74ed
description: Когда вызов припаркован, он передается на временный номер, где вызов проводится до тех пор, пока кто-то не извлекает его или не разовьется. Вам необходимо настроить таблицу с диапазонами номеров расширения, которые вы reserving для припаркованных вызовов. Эти добавочные номера должны быть виртуальными (то есть не иметь назначенного пользователя или назначенный телефон). Каждый пул, который запускает приложение Call Park, может иметь один или несколько диапазонов расширений. Эти диапазоны должны быть уникальными в рамках всего развертывания.
ms.openlocfilehash: 30e0493c065c8bcd16b8d18a625c2650522ee8ee
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51095403"
---
# <a name="call-park"></a><span data-ttu-id="19663-106">Парковка вызовов</span><span class="sxs-lookup"><span data-stu-id="19663-106">Call Park</span></span>

<span data-ttu-id="19663-107">Когда вызов припаркован, он передается на временный номер, где вызов проводится до тех пор, пока кто-то не извлекает его или не разовьется. Вам необходимо настроить таблицу с диапазонами номеров расширения, которые вы reserving для припаркованных вызовов.</span><span class="sxs-lookup"><span data-stu-id="19663-107">When a call is parked, it is transferred to a temporary number where the call is held until someone retrieves it or it times out. You need to configure a table with the ranges of extension numbers that you are reserving for parked calls.</span></span> <span data-ttu-id="19663-108">Эти добавочные номера должны быть виртуальными (то есть не иметь назначенного пользователя или назначенный телефон).</span><span class="sxs-lookup"><span data-stu-id="19663-108">These extensions need to be virtual extensions (that is, extensions that have no user or phone assigned to them).</span></span> <span data-ttu-id="19663-109">Каждый пул, который запускает приложение Call Park, может иметь один или несколько диапазонов расширений.</span><span class="sxs-lookup"><span data-stu-id="19663-109">Each pool that runs the Call Park application can have one or more ranges of extensions.</span></span> <span data-ttu-id="19663-110">Эти диапазоны должны быть уникальными в рамках всего развертывания.</span><span class="sxs-lookup"><span data-stu-id="19663-110">These ranges must be globally unique across your deployment.</span></span>

<span data-ttu-id="19663-111">На **странице Call Park** отображается список всех диапазонов номеров Call Park, определенных для вашей организации.</span><span class="sxs-lookup"><span data-stu-id="19663-111">The **Call Park** page displays a list of all the Call Park number ranges that are defined for your organization.</span></span>

## <a name="tasks-you-can-perform"></a><span data-ttu-id="19663-112">Задачи, которые вы можете выполнить</span><span class="sxs-lookup"><span data-stu-id="19663-112">Tasks you can perform</span></span>

<span data-ttu-id="19663-113">На странице **Парковка звонков** можно выполнить следующие задачи:</span><span class="sxs-lookup"><span data-stu-id="19663-113">You can perform the following tasks from the **Call Park** page:</span></span>

- <span data-ttu-id="19663-114">создать новый диапазон номеров;</span><span class="sxs-lookup"><span data-stu-id="19663-114">Create a new number range</span></span>

- <span data-ttu-id="19663-115">изменить существующий диапазон номеров;</span><span class="sxs-lookup"><span data-stu-id="19663-115">Change an existing number range</span></span>

- <span data-ttu-id="19663-116">удалить диапазон номеров.</span><span class="sxs-lookup"><span data-stu-id="19663-116">Delete a number range</span></span>

## <a name="ui-reference"></a><span data-ttu-id="19663-117">Ссылка на пользовательский интерфейс</span><span class="sxs-lookup"><span data-stu-id="19663-117">UI Reference</span></span>

<span data-ttu-id="19663-118">В следующем списке описываются команды на странице.</span><span class="sxs-lookup"><span data-stu-id="19663-118">The following list describes the commands on the page.</span></span>

- <span data-ttu-id="19663-119">**Новые** Запускает новый диапазон номеров Call Park.</span><span class="sxs-lookup"><span data-stu-id="19663-119">**New** Starts a new Call Park number range.</span></span>

- <span data-ttu-id="19663-120">**Изменение** Открывает выбранный диапазон номеров для редактирования, выбирает все диапазоны номеров в списке или удаляет выбранный диапазон номеров.</span><span class="sxs-lookup"><span data-stu-id="19663-120">**Edit** Opens the selected number range for editing, selects all number ranges in the list, or deletes the selected number range.</span></span>

- <span data-ttu-id="19663-121">**Обновление** Обновляет список диапазонов номеров.</span><span class="sxs-lookup"><span data-stu-id="19663-121">**Refresh** Refreshes the list of number ranges.</span></span>

<span data-ttu-id="19663-122">В следующем списке описываются поля на странице.</span><span class="sxs-lookup"><span data-stu-id="19663-122">The following list describes the fields on the page.</span></span>

- <span data-ttu-id="19663-123">**Имя** Уникальное имя, которое определяет диапазон номеров.</span><span class="sxs-lookup"><span data-stu-id="19663-123">**Name** The unique name that identifies the number range.</span></span>

- <span data-ttu-id="19663-124">**Диапазон запуска** Начало номера диапазона.</span><span class="sxs-lookup"><span data-stu-id="19663-124">**Start range** The beginning number of the range.</span></span>

- <span data-ttu-id="19663-125">**Конечный диапазон** Конечное число диапазона.</span><span class="sxs-lookup"><span data-stu-id="19663-125">**End range** The ending number of the range.</span></span>

- <span data-ttu-id="19663-126">**Назначение** Полное доменное имя (FQDN) или номер службы службы приложений, в котором размещено приложение Call Park для диапазона номеров.</span><span class="sxs-lookup"><span data-stu-id="19663-126">**Destination** The fully qualified domain name (FQDN) or service ID of the Application service that hosts the Call Park application for the number range.</span></span>

<span data-ttu-id="19663-127">Подробные сведения о возможностях и возможностях Call Park см. в материале [Plan for Call Park in Skype for Business 2015.](../../plan-your-deployment/enterprise-voice-solution/call-park.md)</span><span class="sxs-lookup"><span data-stu-id="19663-127">For details about Call Park features and capabilities, see [Plan for Call Park in Skype for Business 2015](../../plan-your-deployment/enterprise-voice-solution/call-park.md).</span></span> <span data-ttu-id="19663-128">Сведения о работе с диапазонами номеров Call Park см. в материале [Configure Phone Number Extensions for Parking Calls.](/previous-versions/office/lync-server-2013/lync-server-2013-configure-phone-number-extensions-for-parking-calls)</span><span class="sxs-lookup"><span data-stu-id="19663-128">For details about working with Call Park number ranges, see [Configure Phone Number Extensions for Parking Calls](/previous-versions/office/lync-server-2013/lync-server-2013-configure-phone-number-extensions-for-parking-calls).</span></span>