---
title: Рабочий процесс групп ответа
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.lscp.RgsWorkFlowMain
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: e4ee8abb-e1e5-413c-919d-cd3fb7193840
ROBOTS: NOINDEX, NOFOLLOW
description: Группы ответа состоят из агентов, очередей и рабочих процессов. В рабочего процессах группы реагирования определяются действия, которые принимаются, когда приложение Группы отклика получает телефонный звонок.
ms.openlocfilehash: dc34ec69af86658c6624ada6a9f25ff3aaa61499
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51118768"
---
# <a name="response-groups-workflow"></a><span data-ttu-id="ed697-104">Рабочий процесс групп ответа</span><span class="sxs-lookup"><span data-stu-id="ed697-104">Response Groups Workflow</span></span>

<span data-ttu-id="ed697-105">Группы ответа состоят из агентов, очередей и рабочих процессов.</span><span class="sxs-lookup"><span data-stu-id="ed697-105">Response groups consist of agent groups, queues, and workflows.</span></span> <span data-ttu-id="ed697-106">В рабочего процессах группы реагирования определяются действия, которые принимаются, когда приложение Группы отклика получает телефонный звонок.</span><span class="sxs-lookup"><span data-stu-id="ed697-106">Response Group workflows define the actions that are taken when the Response Group application receives a phone call.</span></span>

<span data-ttu-id="ed697-107">На **странице Рабочий процесс** групп реагирования отображается список всех процессов группы ответов, определенных для  -   организации.</span><span class="sxs-lookup"><span data-stu-id="ed697-107">The **Response Groups** - **Workflow** page displays a list of all the Response Group workflows that are defined for your organization.</span></span>

## <a name="tasks-you-can-perform"></a><span data-ttu-id="ed697-108">Задачи, которые вы можете выполнить</span><span class="sxs-lookup"><span data-stu-id="ed697-108">Tasks you can perform</span></span>

<span data-ttu-id="ed697-109">Следующие задачи можно выполнить на странице Рабочий процесс **групп**  -   реагирования:</span><span class="sxs-lookup"><span data-stu-id="ed697-109">You can perform the following tasks from the **Response Groups** - **Workflow** page:</span></span>

- <span data-ttu-id="ed697-110">создать или изменить рабочий процесс сервисной группы;</span><span class="sxs-lookup"><span data-stu-id="ed697-110">Create or change a hunt group workflow</span></span>

- <span data-ttu-id="ed697-111">создать или изменить интерактивный рабочий процесс;</span><span class="sxs-lookup"><span data-stu-id="ed697-111">Create or change an interactive workflow</span></span>

## <a name="ui-reference"></a><span data-ttu-id="ed697-112">Ссылка на пользовательский интерфейс</span><span class="sxs-lookup"><span data-stu-id="ed697-112">UI Reference</span></span>

<span data-ttu-id="ed697-113">В следующем списке описываются команды на странице.</span><span class="sxs-lookup"><span data-stu-id="ed697-113">The following list describes the commands on the page.</span></span>

- <span data-ttu-id="ed697-114">**Создание или изменение рабочего процесса** Открывает средство конфигурации группы реагирования для создания или редактирования рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="ed697-114">**Create or edit a workflow** Opens the Response Group Configuration Tool for creating or editing a workflow.</span></span>

- <span data-ttu-id="ed697-115">**Обновление** Обновляет список рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="ed697-115">**Refresh** Refreshes the list of workflows.</span></span>

<span data-ttu-id="ed697-116">В следующем списке описываются поля на странице.</span><span class="sxs-lookup"><span data-stu-id="ed697-116">The following list describes the fields on the page.</span></span>

- <span data-ttu-id="ed697-117">**Имя** Уникальное имя, назначенное рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="ed697-117">**Name** The unique name that is assigned to the workflow.</span></span>

- <span data-ttu-id="ed697-118">**Служба** Служба **ApplicationServer,** в котором находится рабочий процесс.</span><span class="sxs-lookup"><span data-stu-id="ed697-118">**Service** The **ApplicationServer** service that hosts the workflow.</span></span>

- <span data-ttu-id="ed697-119">**SIP-адрес** SIP-адрес группы, которая будет отвечать на вызовы в рабочий процесс.</span><span class="sxs-lookup"><span data-stu-id="ed697-119">**SIP address** The SIP address of the group that will answer calls to the workflow.</span></span>

- <span data-ttu-id="ed697-120">**Телефон** Телефонный номер, который вызван для достижения этой группы ответа.</span><span class="sxs-lookup"><span data-stu-id="ed697-120">**Telephone** The phone number that is called to reach this response group.</span></span>

- <span data-ttu-id="ed697-121">**Язык** Язык, используемый для распознавания речи и текстовых сообщений.</span><span class="sxs-lookup"><span data-stu-id="ed697-121">**Language** The language that is used for speech recognition and text-to-speech.</span></span>

- <span data-ttu-id="ed697-122">**IVR** Указывает, является ли рабочий процесс группой охоты или интерактивным процессом.</span><span class="sxs-lookup"><span data-stu-id="ed697-122">**IVR** Indicates whether the workflow is a hunt group or an interactive workflow.</span></span>

- <span data-ttu-id="ed697-123">**Включено** Указывает, активируется ли рабочий процесс для получения вызовов.</span><span class="sxs-lookup"><span data-stu-id="ed697-123">**Enabled** Indicates whether the workflow is activated to receive calls.</span></span>

<span data-ttu-id="ed697-124">Подробные сведения о возможностях и возможностях группы реагирования см. в документации По планированию для группы ответов в [Skype для](../../../plan-your-deployment/enterprise-voice-solution/response-group.md) бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="ed697-124">For details about Response Group features and capabilities, see [Plan for the Response Group application in Skype for Business Server](../../../plan-your-deployment/enterprise-voice-solution/response-group.md) in the Planning documentation.</span></span> <span data-ttu-id="ed697-125">Подробные сведения о работе с рабочими процессами группы реагирования см. в документе ["Управление](/previous-versions/office/lync-server-2013/lync-server-2013-managing-response-group-workflows) рабочими процессами группы реагирования".</span><span class="sxs-lookup"><span data-stu-id="ed697-125">For details about working with Response Group workflows, see [Managing Response Group Workflows](/previous-versions/office/lync-server-2013/lync-server-2013-managing-response-group-workflows) in the Operations documentation.</span></span>