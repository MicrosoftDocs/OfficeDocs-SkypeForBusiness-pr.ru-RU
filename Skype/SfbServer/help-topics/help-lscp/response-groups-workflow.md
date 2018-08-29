---
title: Рабочий процесс групп ответа
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 11/17/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.RgsWorkFlowMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e4ee8abb-e1e5-413c-919d-cd3fb7193840
description: Группы ответа состоят из групп агентов, очереди и рабочие процессы. Рабочие процессы группы ответа определяют действия, предпринимаемые при получении приложения группы ответа на телефонный звонок.
ms.openlocfilehash: c2b57fd156689b5804e2705d79c515ffe52498b6
ms.sourcegitcommit: 08c6fe9955ea61dd9cded2210ae0153e06bdd8a6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/28/2018
ms.locfileid: "23258286"
---
# <a name="response-groups-workflow"></a><span data-ttu-id="be488-104">Рабочий процесс групп ответа</span><span class="sxs-lookup"><span data-stu-id="be488-104">Response Groups Workflow</span></span>

<span data-ttu-id="be488-105">Группы ответа состоят из групп агентов, очереди и рабочие процессы.</span><span class="sxs-lookup"><span data-stu-id="be488-105">Response groups consist of agent groups, queues, and workflows.</span></span> <span data-ttu-id="be488-106">Рабочие процессы группы ответа определяют действия, предпринимаемые при получении приложения группы ответа на телефонный звонок.</span><span class="sxs-lookup"><span data-stu-id="be488-106">Response Group workflows define the actions that are taken when the Response Group application receives a phone call.</span></span>

<span data-ttu-id="be488-107">**Группы ответа** - странице**рабочий процесс** отображается список всех рабочих процессов группы ответа, определенных для вашей организации.</span><span class="sxs-lookup"><span data-stu-id="be488-107">The **Response Groups** - **Workflow** page displays a list of all the Response Group workflows that are defined for your organization.</span></span>

## <a name="tasks-you-can-perform"></a><span data-ttu-id="be488-108">Задачи, которые вы можете выполнить</span><span class="sxs-lookup"><span data-stu-id="be488-108">Tasks you can perform</span></span>

<span data-ttu-id="be488-109">На странице **Группы ответа**можно выполнить следующие задачи - страница**рабочего процесса** :</span><span class="sxs-lookup"><span data-stu-id="be488-109">You can perform the following tasks from the **Response Groups** - **Workflow** page:</span></span>

- <span data-ttu-id="be488-110">Создание или изменение рабочего процесса</span><span class="sxs-lookup"><span data-stu-id="be488-110">Create or change a hunt group workflow</span></span>

- <span data-ttu-id="be488-111">Создание или изменение интерактивного рабочего процесса</span><span class="sxs-lookup"><span data-stu-id="be488-111">Create or change an interactive workflow</span></span>

## <a name="ui-reference"></a><span data-ttu-id="be488-112">Ссылка на пользовательский интерфейс</span><span class="sxs-lookup"><span data-stu-id="be488-112">UI Reference</span></span>

<span data-ttu-id="be488-113">В следующем списке описываются команды на странице.</span><span class="sxs-lookup"><span data-stu-id="be488-113">The following list describes the commands on the page.</span></span>

- <span data-ttu-id="be488-114">**Создание или изменение рабочего процесса** Откроется средство настройки группы ответа для создания или изменения рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="be488-114">**Create or edit a workflow** Opens the Response Group Configuration Tool for creating or editing a workflow.</span></span>

- <span data-ttu-id="be488-115">**Обновление** Обновляет список рабочих процессов.</span><span class="sxs-lookup"><span data-stu-id="be488-115">**Refresh** Refreshes the list of workflows.</span></span>

<span data-ttu-id="be488-116">В следующем списке описываются поля на странице.</span><span class="sxs-lookup"><span data-stu-id="be488-116">The following list describes the fields on the page.</span></span>

- <span data-ttu-id="be488-117">**Имя** Уникальное имя, назначенное рабочему процессу.</span><span class="sxs-lookup"><span data-stu-id="be488-117">**Name** The unique name that is assigned to the workflow.</span></span>

- <span data-ttu-id="be488-118">**Службы** Службы **сервера приложений** , на котором размещается рабочий процесс.</span><span class="sxs-lookup"><span data-stu-id="be488-118">**Service** The **ApplicationServer** service that hosts the workflow.</span></span>

- <span data-ttu-id="be488-119">**SIP-адрес** SIP-адрес группы, которая будет отвечать на звонки в рабочий процесс.</span><span class="sxs-lookup"><span data-stu-id="be488-119">**SIP address** The SIP address of the group that will answer calls to the workflow.</span></span>

- <span data-ttu-id="be488-120">**Телефон** Номер телефона, вызов для обращения в данную группу ответа.</span><span class="sxs-lookup"><span data-stu-id="be488-120">**Telephone** The phone number that is called to reach this response group.</span></span>

- <span data-ttu-id="be488-121">**Язык** Язык, используемый для распознавания речи и преобразования текста в речь.</span><span class="sxs-lookup"><span data-stu-id="be488-121">**Language** The language that is used for speech recognition and text-to-speech.</span></span>

- <span data-ttu-id="be488-122">**IVR** Указывает, является ли рабочий процесс сервисной группой или интерактивного рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="be488-122">**IVR** Indicates whether the workflow is a hunt group or an interactive workflow.</span></span>

- <span data-ttu-id="be488-123">**Включено** Указывает, будет ли данному рабочему процессу будут принимать звонки.</span><span class="sxs-lookup"><span data-stu-id="be488-123">**Enabled** Indicates whether the workflow is activated to receive calls.</span></span>

<span data-ttu-id="be488-124">Для получения дополнительных сведений о группы ответа функций и возможностей см. в документации по планированию [Планирование приложения группы ответа в Скайп для Business Server 2015](../../plan-your-deployment/enterprise-voice-solution/response-group.md) .</span><span class="sxs-lookup"><span data-stu-id="be488-124">For details about Response Group features and capabilities, see [Plan for the Response Group application in Skype for Business Server 2015](../../plan-your-deployment/enterprise-voice-solution/response-group.md) in the Planning documentation.</span></span> <span data-ttu-id="be488-125">Для получения дополнительных сведений о работе с рабочими процессами для группы ответа видеть [Управление рабочими процессами группы ответа](https://technet.microsoft.com/library/42cfccdd-2844-4875-b4e3-813e1df15f08.aspx) в документации по операциям.</span><span class="sxs-lookup"><span data-stu-id="be488-125">For details about working with Response Group workflows, see [Managing Response Group Workflows](https://technet.microsoft.com/library/42cfccdd-2844-4875-b4e3-813e1df15f08.aspx) in the Operations documentation.</span></span>


