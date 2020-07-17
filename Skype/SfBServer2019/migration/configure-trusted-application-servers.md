---
title: Настройка доверенных серверов приложений
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Если вы создаете новый доверенный сервер приложений, в смешанной среде необходимо установить пул следующего прыжка в качестве пула Skype для бизнеса Server 2019. В смешанной среде в раскрывающемся списке отображаются пул устаревших и в Skype для бизнеса Server 2019. Предыдущую версию пула выбрать нельзя.
ms.openlocfilehash: 1c0aac1efa4f83a81ccf2f3bb5ecbc925ee58839
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/16/2020
ms.locfileid: "44753949"
---
# <a name="configure-trusted-application-servers"></a><span data-ttu-id="74a2b-105">Настройка доверенных серверов приложений</span><span class="sxs-lookup"><span data-stu-id="74a2b-105">Configure trusted application servers</span></span>

<span data-ttu-id="74a2b-106">Если вы создаете новый доверенный сервер приложений, в смешанной среде необходимо установить пул следующего прыжка в качестве пула Skype для бизнеса Server 2019.</span><span class="sxs-lookup"><span data-stu-id="74a2b-106">In a mixed environment, if you create a new trusted application server, you must set the next hop pool to be a Skype for Business Server 2019 pool.</span></span> <span data-ttu-id="74a2b-107">В смешанной среде в раскрывающемся списке отображаются пул прежних версий и пул Skype для бизнеса Server 2019.</span><span class="sxs-lookup"><span data-stu-id="74a2b-107">In a mixed environment, both the legacy pool and the Skype for Business Server 2019 pool appear in the drop-down list.</span></span> <span data-ttu-id="74a2b-108">Предыдущую версию пула выбрать нельзя.</span><span class="sxs-lookup"><span data-stu-id="74a2b-108">Selecting the legacy pool is not supported.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="74a2b-109">При переносе доверенного сервера приложений также следует обновить используемую версию UCMA.</span><span class="sxs-lookup"><span data-stu-id="74a2b-109">If you are migrating a trusted application server, you should also update the version of UCMA you are using.</span></span> <span data-ttu-id="74a2b-110">При создании нового пула доверенных приложений для Skype для бизнеса Server 2019 необходимо обновить UCMA до версии, входящей в состав Skype для бизнеса Server 2019 или последней доступной версии.</span><span class="sxs-lookup"><span data-stu-id="74a2b-110">If you create a new Trusted Application Pool for Skype for Business Server 2019, you should update UCMA to the version that is included with Skype for Business Server 2019 or the latest version available.</span></span> 
  
### <a name="select-skype-for-business-server-2019-as-next-hop-when-creating-a-trusted-application-server"></a><span data-ttu-id="74a2b-111">Выберите Skype для бизнеса Server 2019 в качестве следующего перехода при создании доверенного сервера приложений</span><span class="sxs-lookup"><span data-stu-id="74a2b-111">Select Skype for Business Server 2019 as next hop when creating a Trusted application server</span></span>

1. <span data-ttu-id="74a2b-112">Откройте построитель топологий.</span><span class="sxs-lookup"><span data-stu-id="74a2b-112">Open Topology Builder.</span></span>
    
2. <span data-ttu-id="74a2b-113">В левой области щелкните правой кнопкой мыши пункт **серверы доверенных приложений** и выберите **создать пул доверенных приложений**.</span><span class="sxs-lookup"><span data-stu-id="74a2b-113">In the left pane, right-click **Trusted application servers** and click **New Trusted Application Pool**.</span></span>
    
3. <span data-ttu-id="74a2b-114">Введите **полное доменное имя пула** доверенного пула приложений и выберите, будет ли он иметь один или несколько серверов.</span><span class="sxs-lookup"><span data-stu-id="74a2b-114">Enter the **Pool FQDN** of the trusted application pool and select whether it will be single-server or multiple-server.</span></span> 
    
4. <span data-ttu-id="74a2b-115">Нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="74a2b-115">Click **Next**.</span></span>
    
5. <span data-ttu-id="74a2b-116">На странице **Выбор следующего прыжка** в списке выберите пул переднего плана Skype для бизнеса Server 2019.</span><span class="sxs-lookup"><span data-stu-id="74a2b-116">On the **Select the next hop** page, from the list, select the Skype for Business Server 2019 Front End pool.</span></span> 
    
6. <span data-ttu-id="74a2b-117">Нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="74a2b-117">Click **Finish**.</span></span>
    
7. <span data-ttu-id="74a2b-118">Выберите верхний узел в **Skype для бизнеса Server**, а затем в меню **действие** выберите пункт **опубликовать**.</span><span class="sxs-lookup"><span data-stu-id="74a2b-118">Select the top node **Skype for Business Server**, and from the **Action** menu select **Publish**.</span></span>
    
    <span data-ttu-id="74a2b-119">Убедитесь, что **пул доверенных приложений** успешно создан и связан с соответствующим интерфейсным пулом.</span><span class="sxs-lookup"><span data-stu-id="74a2b-119">Verify that the **Trusted Application Pool** has been created successfully and is associated with the correct Front End pool.</span></span> 
    

