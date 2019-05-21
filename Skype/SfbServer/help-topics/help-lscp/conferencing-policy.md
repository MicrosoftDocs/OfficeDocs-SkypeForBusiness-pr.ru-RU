---
title: Политика конференц-связи
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.ConfMeetingPolicyMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 90eaa64e-369e-448d-bac4-2574c7c598b8
description: Политика конференц-связи определяет возможности и возможности, которые пользователи смогут использовать во время конференции (также называемой собранием).
ms.openlocfilehash: 8ac4bb4f33cecef97e3299a993fc21e81af8ad1e
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "34286082"
---
# <a name="conferencing-policy"></a><span data-ttu-id="f9847-103">Политика конференц-связи</span><span class="sxs-lookup"><span data-stu-id="f9847-103">Conferencing Policy</span></span>

<span data-ttu-id="f9847-104">Политика конференц-связи определяет возможности и возможности, которые пользователи смогут использовать во время конференции (также называемой собранием).</span><span class="sxs-lookup"><span data-stu-id="f9847-104">Conferencing policy defines the features and capabilities that users have available during a conference (also known as a meeting).</span></span>

<span data-ttu-id="f9847-105">Политики конференций включают глобальную политику и (необязательно) один или несколько политик сайта и пользователей.</span><span class="sxs-lookup"><span data-stu-id="f9847-105">Conferencing policies include the global policy and, optionally, one or more site and user policies:</span></span>

- <span data-ttu-id="f9847-106">**Глобальная политика:** Глобальная политика создается по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="f9847-106">**Global policy:** The global policy is created by default.</span></span> <span data-ttu-id="f9847-107">Вы можете изменить ее, но не можете удалить.</span><span class="sxs-lookup"><span data-stu-id="f9847-107">You can edit the global policy, but you cannot delete it.</span></span> <span data-ttu-id="f9847-108">Если попытаться удалить глобальную политику, для всех параметров восстанавливаются значения по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="f9847-108">If you try to remove the global policy, all the settings are reset to the default values.</span></span>

- <span data-ttu-id="f9847-109">**Политики сайта (необязательно):** Вы можете создать одну или несколько политик конференц-связи сайтов, каждый из которых будет применяться к определенному сайту.</span><span class="sxs-lookup"><span data-stu-id="f9847-109">**Site policies (optional):** You can create one or more site conferencing policies, each of which applies to a specific site.</span></span> <span data-ttu-id="f9847-110">Политики для сайтов переопределяют глобальную политику.</span><span class="sxs-lookup"><span data-stu-id="f9847-110">Site policies override the global policy.</span></span>

- <span data-ttu-id="f9847-111">**Пользовательские политики (необязательно):** Вы можете создать одну или несколько политик конференц-связи пользователей, каждый из которых будет применяться к определенному пользователю или группе пользователей.</span><span class="sxs-lookup"><span data-stu-id="f9847-111">**User policies (optional):** You can create one or more user conferencing policies, each of which applies to a specific user or group of users.</span></span> <span data-ttu-id="f9847-112">Политики для пользователей переопределяют глобальную политику и политики для сайтов.</span><span class="sxs-lookup"><span data-stu-id="f9847-112">User policies override the global policy and site policies.</span></span>

<span data-ttu-id="f9847-113">На странице " **Политика конференции** " отображается список всех политик конференц-связи, определенных для вашей организации.</span><span class="sxs-lookup"><span data-stu-id="f9847-113">The **Conferencing Policy** page displays a list of all the conferencing policies that are defined for your organization.</span></span>

## <a name="tasks-you-can-perform"></a><span data-ttu-id="f9847-114">Задачи, которые вы можете выполнить</span><span class="sxs-lookup"><span data-stu-id="f9847-114">Tasks you can perform</span></span>

<span data-ttu-id="f9847-115">На странице **Политика расположения** можно выполнить следующие задачи:</span><span class="sxs-lookup"><span data-stu-id="f9847-115">You can perform the following tasks from the **Location Policy** page:</span></span>

- <span data-ttu-id="f9847-116">Создание новой политики конференций сайтов или политики конференц-связи пользователей</span><span class="sxs-lookup"><span data-stu-id="f9847-116">Create a new site conferencing policy or user conferencing policy</span></span>

- <span data-ttu-id="f9847-117">изменить глобальную политику или существующую политику сайта или пользователя;</span><span class="sxs-lookup"><span data-stu-id="f9847-117">Change the global policy or an existing site policy or user policy</span></span>

- <span data-ttu-id="f9847-118">удалить политику сайта или пользователя.</span><span class="sxs-lookup"><span data-stu-id="f9847-118">Delete a site policy or user policy</span></span>

## <a name="ui-reference"></a><span data-ttu-id="f9847-119">Ссылка на пользовательский интерфейс</span><span class="sxs-lookup"><span data-stu-id="f9847-119">UI Reference</span></span>

<span data-ttu-id="f9847-120">В следующем списке описываются команды на странице.</span><span class="sxs-lookup"><span data-stu-id="f9847-120">The following list describes the commands on the page.</span></span>

- <span data-ttu-id="f9847-121">**Новые** Запускает новую политику конференций сайтов или политику конференций пользователей.</span><span class="sxs-lookup"><span data-stu-id="f9847-121">**New** Starts a new site conferencing policy or user conferencing policy.</span></span>

- <span data-ttu-id="f9847-122">**Изменить** Открытие выбранной политики конференций для редактирования, выбор всех политик конференц-связи в списке или удаление выбранной политики сайта или политики пользователей.</span><span class="sxs-lookup"><span data-stu-id="f9847-122">**Edit** Opens the selected conferencing policy to edit it, selects all conferencing policies in the list, or deletes the selected site policy or user policy.</span></span>

    > [!NOTE]
    > <span data-ttu-id="f9847-123">Для глобальной политики команда **Удалить** восстанавливает значения параметров по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="f9847-123">For the global policy, **Delete** resets the settings to the default values.</span></span>

- <span data-ttu-id="f9847-124">**Обновить** Обновляет список политик конференц-связи.</span><span class="sxs-lookup"><span data-stu-id="f9847-124">**Refresh** Refreshes the list of conferencing policies.</span></span>

<span data-ttu-id="f9847-125">В следующем списке описываются поля на странице.</span><span class="sxs-lookup"><span data-stu-id="f9847-125">The following list describes the fields on the page.</span></span>

- <span data-ttu-id="f9847-126">**Name (имя** ) Определяет политику конференц-связи.</span><span class="sxs-lookup"><span data-stu-id="f9847-126">**Name** Identifies the conferencing policy.</span></span>

- <span data-ttu-id="f9847-127">**Область действия** Определяет область действия политики конференц-связи: глобально, с сайтом или пользователем.</span><span class="sxs-lookup"><span data-stu-id="f9847-127">**Scope** Identifies the scope of the conferencing policy: global, site, or user.</span></span>

- <span data-ttu-id="f9847-128">**Совместная работа с данными** Флажок установлен, если в параметрах конференции разрешена совместная работа с данными.</span><span class="sxs-lookup"><span data-stu-id="f9847-128">**Data collaboration** Checked if the conferencing policy specifies that data collaboration is allowed in conferences.</span></span>

- <span data-ttu-id="f9847-129">**Общий доступ к приложениям** Флажок установлен, если в параметрах конференции указано, что общий доступ к приложениям разрешен в конференциях.</span><span class="sxs-lookup"><span data-stu-id="f9847-129">**Application sharing** Checked if the conferencing policy specifies that application sharing is allowed in conferences.</span></span>

- <span data-ttu-id="f9847-130">**Audio (звук** ) Флажок установлен, если в параметрах конференции указано, что звук разрешен в конференциях.</span><span class="sxs-lookup"><span data-stu-id="f9847-130">**Audio** Checked if the conferencing policy specifies that audio is allowed in conferences.</span></span>

- <span data-ttu-id="f9847-131">**Видео** Флажок установлен, если в параметрах конференции указано, разрешено ли видео в конференциях.</span><span class="sxs-lookup"><span data-stu-id="f9847-131">**Video** Checked if the conferencing policy specifies that video is allowed in conferences.</span></span>

- <span data-ttu-id="f9847-132">**PSTN** Флажок установлен, если в политике конференций разрешена Конференц-связь с телефонным подключением PSTN.</span><span class="sxs-lookup"><span data-stu-id="f9847-132">**PSTN** Checked if the conferencing policy specifies that PSTN dial-in conferencing is allowed.</span></span>

- <span data-ttu-id="f9847-133">**Запись** Флажок установлен, если в параметрах конференции указана запись разрешена в конференциях.</span><span class="sxs-lookup"><span data-stu-id="f9847-133">**Recording** Checked if the conferencing policy specifies that recording is allowed in conferences.</span></span>

<span data-ttu-id="f9847-p104">Дополнительные сведения о компонентах и возможностях конференц-связи см. в разделе [Overview of Conferencing](https://technet.microsoft.com/library/5bb90e69-3d4f-4d59-a1ee-2550de84439f.aspx) документации по планированию. Дополнительные сведения о работе с политиками конференц-связи см. в разделе [Conferencing Policies](https://technet.microsoft.com/library/8f92eb7c-ee66-4df6-a726-4bff93b122cb.aspx) документации по использованию.</span><span class="sxs-lookup"><span data-stu-id="f9847-p104">For details about conferencing features and capabilities, see [Overview of Conferencing](https://technet.microsoft.com/library/5bb90e69-3d4f-4d59-a1ee-2550de84439f.aspx) in the Planning documentation. For details about working with conferencing policies, see [Conferencing Policies](https://technet.microsoft.com/library/8f92eb7c-ee66-4df6-a726-4bff93b122cb.aspx) in the Operations documentation.</span></span>


