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
description: Группы ответа состоят из агентов, очередей и рабочих процессов. Рабочий процесс группы ответа определяет действия, которые принимаются приложением группы ответа при приеме телефонного звонка.
ms.openlocfilehash: b4f9a80be55e00d5874c79cf426e331a464d0e2c
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49820269"
---
# <a name="response-groups-workflow"></a><span data-ttu-id="fc113-104">Рабочий процесс групп ответа</span><span class="sxs-lookup"><span data-stu-id="fc113-104">Response Groups Workflow</span></span>

<span data-ttu-id="fc113-105">Группы ответа состоят из агентов, очередей и рабочих процессов.</span><span class="sxs-lookup"><span data-stu-id="fc113-105">Response groups consist of agent groups, queues, and workflows.</span></span> <span data-ttu-id="fc113-106">Рабочий процесс группы ответа определяет действия, которые принимаются приложением группы ответа при приеме телефонного звонка.</span><span class="sxs-lookup"><span data-stu-id="fc113-106">Response Group workflows define the actions that are taken when the Response Group application receives a phone call.</span></span>

<span data-ttu-id="fc113-107">На **странице "Рабочий** процесс групп ответа" отображается список всех процессов группы ответа, определенных  -   для организации.</span><span class="sxs-lookup"><span data-stu-id="fc113-107">The **Response Groups** - **Workflow** page displays a list of all the Response Group workflows that are defined for your organization.</span></span>

## <a name="tasks-you-can-perform"></a><span data-ttu-id="fc113-108">Задачи, которые вы можете выполнить</span><span class="sxs-lookup"><span data-stu-id="fc113-108">Tasks you can perform</span></span>

<span data-ttu-id="fc113-109">На странице "Рабочий процесс групп ответа" можно выполнить следующие  -   задачи:</span><span class="sxs-lookup"><span data-stu-id="fc113-109">You can perform the following tasks from the **Response Groups** - **Workflow** page:</span></span>

- <span data-ttu-id="fc113-110">создать или изменить рабочий процесс сервисной группы;</span><span class="sxs-lookup"><span data-stu-id="fc113-110">Create or change a hunt group workflow</span></span>

- <span data-ttu-id="fc113-111">создать или изменить интерактивный рабочий процесс;</span><span class="sxs-lookup"><span data-stu-id="fc113-111">Create or change an interactive workflow</span></span>

## <a name="ui-reference"></a><span data-ttu-id="fc113-112">Ссылка на пользовательский интерфейс</span><span class="sxs-lookup"><span data-stu-id="fc113-112">UI Reference</span></span>

<span data-ttu-id="fc113-113">В следующем списке описываются команды на странице.</span><span class="sxs-lookup"><span data-stu-id="fc113-113">The following list describes the commands on the page.</span></span>

- <span data-ttu-id="fc113-114">**Создание или изменение рабочего процесса** Открывает средство настройки группы ответа для создания или редактирования рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="fc113-114">**Create or edit a workflow** Opens the Response Group Configuration Tool for creating or editing a workflow.</span></span>

- <span data-ttu-id="fc113-115">**Обновление** Обновляет список рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="fc113-115">**Refresh** Refreshes the list of workflows.</span></span>

<span data-ttu-id="fc113-116">В следующем списке описываются поля на странице.</span><span class="sxs-lookup"><span data-stu-id="fc113-116">The following list describes the fields on the page.</span></span>

- <span data-ttu-id="fc113-117">**Имя** Уникальное имя, назначенное для рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="fc113-117">**Name** The unique name that is assigned to the workflow.</span></span>

- <span data-ttu-id="fc113-118">**Служба** Служба **ApplicationServer,** в котором размещен рабочий процесс.</span><span class="sxs-lookup"><span data-stu-id="fc113-118">**Service** The **ApplicationServer** service that hosts the workflow.</span></span>

- <span data-ttu-id="fc113-119">**SIP-адрес** SIP-адрес группы, которая будет отвечать на вызовы рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="fc113-119">**SIP address** The SIP address of the group that will answer calls to the workflow.</span></span>

- <span data-ttu-id="fc113-120">**Телефон** Номер телефона, который будет вызван для данной группы ответа.</span><span class="sxs-lookup"><span data-stu-id="fc113-120">**Telephone** The phone number that is called to reach this response group.</span></span>

- <span data-ttu-id="fc113-121">**Язык** Язык, используемый для распознавания речи и текста в речь.</span><span class="sxs-lookup"><span data-stu-id="fc113-121">**Language** The language that is used for speech recognition and text-to-speech.</span></span>

- <span data-ttu-id="fc113-122">**IVR** Указывает, является ли рабочий процесс сервисной группой или интерактивным.</span><span class="sxs-lookup"><span data-stu-id="fc113-122">**IVR** Indicates whether the workflow is a hunt group or an interactive workflow.</span></span>

- <span data-ttu-id="fc113-123">**Включено** Указывает, активирован ли рабочий процесс для получения вызовов.</span><span class="sxs-lookup"><span data-stu-id="fc113-123">**Enabled** Indicates whether the workflow is activated to receive calls.</span></span>

<span data-ttu-id="fc113-124">For details about Response Group features and capabilities, see [Plan for the Response Group application in Skype for Business Server](../../../plan-your-deployment/enterprise-voice-solution/response-group.md) in the Planning documentation.</span><span class="sxs-lookup"><span data-stu-id="fc113-124">For details about Response Group features and capabilities, see [Plan for the Response Group application in Skype for Business Server](../../../plan-your-deployment/enterprise-voice-solution/response-group.md) in the Planning documentation.</span></span> <span data-ttu-id="fc113-125">Подробные сведения о работе с рабочими [](https://technet.microsoft.com/library/42cfccdd-2844-4875-b4e3-813e1df15f08.aspx) процессами группы ответа см. в документации по управлению рабочими процессами группы ответа.</span><span class="sxs-lookup"><span data-stu-id="fc113-125">For details about working with Response Group workflows, see [Managing Response Group Workflows](https://technet.microsoft.com/library/42cfccdd-2844-4875-b4e3-813e1df15f08.aspx) in the Operations documentation.</span></span>


