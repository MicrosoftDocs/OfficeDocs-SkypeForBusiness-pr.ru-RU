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
ms.openlocfilehash: 268d97ae92755da336577c3cdee8bd7ca916759c
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/24/2018
ms.locfileid: "21006890"
---
# <a name="response-groups-workflow"></a><span data-ttu-id="691fa-104">Рабочий процесс групп ответа</span><span class="sxs-lookup"><span data-stu-id="691fa-104">Response Groups Workflow</span></span>
 
<span data-ttu-id="691fa-105">Группы ответа состоят из групп агентов, очереди и рабочие процессы.</span><span class="sxs-lookup"><span data-stu-id="691fa-105">Response groups consist of agent groups, queues, and workflows.</span></span> <span data-ttu-id="691fa-106">Рабочие процессы группы ответа определяют действия, предпринимаемые при получении приложения группы ответа на телефонный звонок.</span><span class="sxs-lookup"><span data-stu-id="691fa-106">Response Group workflows define the actions that are taken when the Response Group application receives a phone call.</span></span> 
  
<span data-ttu-id="691fa-107">**Группы ответа** - странице**рабочий процесс** отображается список всех рабочих процессов группы ответа, определенных для вашей организации.</span><span class="sxs-lookup"><span data-stu-id="691fa-107">The **Response Groups** - **Workflow** page displays a list of all the Response Group workflows that are defined for your organization.</span></span>
  
## <a name="tasks-you-can-perform"></a><span data-ttu-id="691fa-108">Задачи, которые вы можете выполнить</span><span class="sxs-lookup"><span data-stu-id="691fa-108">Tasks you can perform</span></span>

<span data-ttu-id="691fa-109">На странице **Группы ответа**можно выполнить следующие задачи - страница**рабочего процесса** :</span><span class="sxs-lookup"><span data-stu-id="691fa-109">You can perform the following tasks from the **Response Groups** - **Workflow** page:</span></span>
  
- <span data-ttu-id="691fa-110">Создание или изменение рабочего процесса</span><span class="sxs-lookup"><span data-stu-id="691fa-110">Create or change a hunt group workflow</span></span>
    
- <span data-ttu-id="691fa-111">Создание или изменение интерактивного рабочего процесса</span><span class="sxs-lookup"><span data-stu-id="691fa-111">Create or change an interactive workflow</span></span>
    
## <a name="ui-reference"></a><span data-ttu-id="691fa-112">Ссылка на пользовательский интерфейс</span><span class="sxs-lookup"><span data-stu-id="691fa-112">UI Reference</span></span>

<span data-ttu-id="691fa-113">В следующем списке описываются команды на странице.</span><span class="sxs-lookup"><span data-stu-id="691fa-113">The following list describes the commands on the page.</span></span>
  
- <span data-ttu-id="691fa-114">**Создание или изменение рабочего процесса** Откроется средство настройки группы ответа для создания или изменения рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="691fa-114">**Create or edit a workflow** Opens the Response Group Configuration Tool for creating or editing a workflow.</span></span>
    
- <span data-ttu-id="691fa-115">**Обновление** Обновляет список рабочих процессов.</span><span class="sxs-lookup"><span data-stu-id="691fa-115">**Refresh** Refreshes the list of workflows.</span></span>
    
<span data-ttu-id="691fa-116">В следующем списке описываются поля на странице.</span><span class="sxs-lookup"><span data-stu-id="691fa-116">The following list describes the fields on the page.</span></span>
  
- <span data-ttu-id="691fa-117">**Имя** Уникальное имя, назначенное рабочему процессу.</span><span class="sxs-lookup"><span data-stu-id="691fa-117">**Name** The unique name that is assigned to the workflow.</span></span>
    
- <span data-ttu-id="691fa-118">**Службы** Службы **сервера приложений** , на котором размещается рабочий процесс.</span><span class="sxs-lookup"><span data-stu-id="691fa-118">**Service** The **ApplicationServer** service that hosts the workflow.</span></span>
    
- <span data-ttu-id="691fa-119">**SIP-адрес** SIP-адрес группы, которая будет отвечать на звонки в рабочий процесс.</span><span class="sxs-lookup"><span data-stu-id="691fa-119">**SIP address** The SIP address of the group that will answer calls to the workflow.</span></span>
    
- <span data-ttu-id="691fa-120">**Телефон** Номер телефона, вызов для обращения в данную группу ответа.</span><span class="sxs-lookup"><span data-stu-id="691fa-120">**Telephone** The phone number that is called to reach this response group.</span></span>
    
- <span data-ttu-id="691fa-121">**Язык** Язык, используемый для распознавания речи и преобразования текста в речь.</span><span class="sxs-lookup"><span data-stu-id="691fa-121">**Language** The language that is used for speech recognition and text-to-speech.</span></span>
    
- <span data-ttu-id="691fa-122">**IVR** Указывает, является ли рабочий процесс сервисной группой или интерактивного рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="691fa-122">**IVR** Indicates whether the workflow is a hunt group or an interactive workflow.</span></span>
    
- <span data-ttu-id="691fa-123">**Включено** Указывает, будет ли данному рабочему процессу будут принимать звонки.</span><span class="sxs-lookup"><span data-stu-id="691fa-123">**Enabled** Indicates whether the workflow is activated to receive calls.</span></span>
    
<span data-ttu-id="691fa-124">Для получения дополнительных сведений о группы ответа функций и возможностей см. в документации по планированию [Планирование приложения группы ответа в Скайп для Business Server 2015](../../plan-your-deployment/enterprise-voice-solution/response-group.md) .</span><span class="sxs-lookup"><span data-stu-id="691fa-124">For details about Response Group features and capabilities, see [Plan for the Response Group application in Skype for Business Server 2015](../../plan-your-deployment/enterprise-voice-solution/response-group.md) in the Planning documentation.</span></span> <span data-ttu-id="691fa-125">Для получения дополнительных сведений о работе с рабочими процессами для группы ответа видеть [Управление рабочими процессами группы ответа](http://technet.microsoft.com/library/42cfccdd-2844-4875-b4e3-813e1df15f08.aspx) в документации по операциям.</span><span class="sxs-lookup"><span data-stu-id="691fa-125">For details about working with Response Group workflows, see [Managing Response Group Workflows](http://technet.microsoft.com/library/42cfccdd-2844-4875-b4e3-813e1df15f08.aspx) in the Operations documentation.</span></span>
  

