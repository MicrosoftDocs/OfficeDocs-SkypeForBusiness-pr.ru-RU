---
title: Парковка вызовов
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.lscp.VoiceFeaCallParkMain
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: b752617d-554d-470e-b17b-387403ac74ed
ROBOTS: NOINDEX, NOFOLLOW
description: Когда звонок приостанавливается, он передается во временный номер, в котором звонок удерживается до тех пор, пока кто-то не загружает его или не истечет время ожидания. Вы должны настроить таблицу с диапазонами добавочных номеров, которые вы сохраняете для приостановки звонка. Эти добавочные номера должны быть виртуальными (то есть не иметь назначенного пользователя или назначенный телефон). Каждый пул, на котором запущено приложение для парковки, может иметь один или несколько диапазонов расширений. Эти диапазоны должны быть уникальными в рамках всего развертывания.
ms.openlocfilehash: 7f4a660c3fdd1dbba5080b93bec0aac116d453ea
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41797816"
---
# <a name="call-park"></a><span data-ttu-id="888da-106">Приостановка вызовов</span><span class="sxs-lookup"><span data-stu-id="888da-106">Call Park</span></span>

<span data-ttu-id="888da-107">Когда звонок приостанавливается, он передается во временный номер, в котором звонок удерживается до тех пор, пока кто-то не загружает его или не истечет время ожидания. Вы должны настроить таблицу с диапазонами добавочных номеров, которые вы сохраняете для приостановки звонка.</span><span class="sxs-lookup"><span data-stu-id="888da-107">When a call is parked, it is transferred to a temporary number where the call is held until someone retrieves it or it times out. You need to configure a table with the ranges of extension numbers that you are reserving for parked calls.</span></span> <span data-ttu-id="888da-108">Эти добавочные номера должны быть виртуальными (то есть не иметь назначенного пользователя или назначенный телефон).</span><span class="sxs-lookup"><span data-stu-id="888da-108">These extensions need to be virtual extensions (that is, extensions that have no user or phone assigned to them).</span></span> <span data-ttu-id="888da-109">Каждый пул, на котором запущено приложение для парковки, может иметь один или несколько диапазонов расширений.</span><span class="sxs-lookup"><span data-stu-id="888da-109">Each pool that runs the Call Park application can have one or more ranges of extensions.</span></span> <span data-ttu-id="888da-110">Эти диапазоны должны быть уникальными в рамках всего развертывания.</span><span class="sxs-lookup"><span data-stu-id="888da-110">These ranges must be globally unique across your deployment.</span></span>

<span data-ttu-id="888da-111">На странице "Приостановка **звонка** " отображается список всех диапазонов номеров для приостановки звонка, определенных для вашей организации.</span><span class="sxs-lookup"><span data-stu-id="888da-111">The **Call Park** page displays a list of all the Call Park number ranges that are defined for your organization.</span></span>

## <a name="tasks-you-can-perform"></a><span data-ttu-id="888da-112">Задачи, которые вы можете выполнить</span><span class="sxs-lookup"><span data-stu-id="888da-112">Tasks you can perform</span></span>

<span data-ttu-id="888da-113">На странице **Парковка вызовов** можно выполнять следующие задачи:</span><span class="sxs-lookup"><span data-stu-id="888da-113">You can perform the following tasks from the **Call Park** page:</span></span>

- <span data-ttu-id="888da-114">создать новый диапазон номеров;</span><span class="sxs-lookup"><span data-stu-id="888da-114">Create a new number range</span></span>

- <span data-ttu-id="888da-115">изменить существующий диапазон номеров;</span><span class="sxs-lookup"><span data-stu-id="888da-115">Change an existing number range</span></span>

- <span data-ttu-id="888da-116">удалить диапазон номеров.</span><span class="sxs-lookup"><span data-stu-id="888da-116">Delete a number range</span></span>

## <a name="ui-reference"></a><span data-ttu-id="888da-117">Ссылка на пользовательский интерфейс</span><span class="sxs-lookup"><span data-stu-id="888da-117">UI Reference</span></span>

<span data-ttu-id="888da-118">В следующем списке описываются команды на странице.</span><span class="sxs-lookup"><span data-stu-id="888da-118">The following list describes the commands on the page.</span></span>

- <span data-ttu-id="888da-119">**Новые** Начало нового диапазона номеров для приостановки вызова.</span><span class="sxs-lookup"><span data-stu-id="888da-119">**New** Starts a new Call Park number range.</span></span>

- <span data-ttu-id="888da-120">**Изменить** Открытие выделенного диапазона номеров для редактирования, выделение всех диапазонов номеров в списке или удаление выделенного диапазона номеров.</span><span class="sxs-lookup"><span data-stu-id="888da-120">**Edit** Opens the selected number range for editing, selects all number ranges in the list, or deletes the selected number range.</span></span>

- <span data-ttu-id="888da-121">**Обновить** Обновляет список диапазонов номеров.</span><span class="sxs-lookup"><span data-stu-id="888da-121">**Refresh** Refreshes the list of number ranges.</span></span>

<span data-ttu-id="888da-122">В следующем списке описываются поля на странице.</span><span class="sxs-lookup"><span data-stu-id="888da-122">The following list describes the fields on the page.</span></span>

- <span data-ttu-id="888da-123">**Name (имя** ) Уникальное имя, определяющее диапазон номеров.</span><span class="sxs-lookup"><span data-stu-id="888da-123">**Name** The unique name that identifies the number range.</span></span>

- <span data-ttu-id="888da-124">**Начальный диапазон** Начальный номер диапазона.</span><span class="sxs-lookup"><span data-stu-id="888da-124">**Start range** The beginning number of the range.</span></span>

- <span data-ttu-id="888da-125">**Конечный диапазон** Конечный номер диапазона.</span><span class="sxs-lookup"><span data-stu-id="888da-125">**End range** The ending number of the range.</span></span>

- <span data-ttu-id="888da-126">**Destination (назначение** ) Полное доменное имя (FQDN) или идентификатор службы приложения, в котором размещается номер диапазона, заданное приложением парковки.</span><span class="sxs-lookup"><span data-stu-id="888da-126">**Destination** The fully qualified domain name (FQDN) or service ID of the Application service that hosts the Call Park application for the number range.</span></span>

<span data-ttu-id="888da-127">Дополнительные сведения о функциях и возможностях приостановки звонка можно найти [в разделе Планирование приостановки звонков в Skype для бизнеса](../../../plan-your-deployment/enterprise-voice-solution/call-park.md).</span><span class="sxs-lookup"><span data-stu-id="888da-127">For details about Call Park features and capabilities, see [Plan for Call Park in Skype for Business](../../../plan-your-deployment/enterprise-voice-solution/call-park.md).</span></span> <span data-ttu-id="888da-128">Подробнее о работе с диапазонами номеров для присоединения к абоненту можно узнать в разделе [Настройка расширений номеров телефонов для вызовов парковки](https://technet.microsoft.com/library/fbf97624-9587-42a6-b276-1b69c574a74d.aspx).</span><span class="sxs-lookup"><span data-stu-id="888da-128">For details about working with Call Park number ranges, see [Configure Phone Number Extensions for Parking Calls](https://technet.microsoft.com/library/fbf97624-9587-42a6-b276-1b69c574a74d.aspx).</span></span>


